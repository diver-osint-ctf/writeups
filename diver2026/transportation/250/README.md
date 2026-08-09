# 250 (461pt / 72 solves)

## 問題文

SNS投稿 / Social Media Post: https://www.facebook.com/reel/1181612624131449

2026年7月4日18:00（現地時間）ごろ、このバスはどこにいたか。地図上で示せ。  

Where was this bus around 18:00 on July 4th, 2026 (local time)? Indicate its location on the map.


## 解法

投稿者から Broward County Transit のバスであることがわかり、動画中で車番 "20094" が見えます。

バスの現在位置を記録しているデータや、過去のものを記録しているデータセットはないでしょうか。

`Broward County Transit bus location data` でGoogle検索すると、GTFSに言及するものがあります。また、GTFSについて調べてみると、バスの現在位置データはGTFS-RTという形式で配信されることがわかります（LLMに「バスの過去の位置情報」について聞いてたどり着いた方もいるでしょう）。

GTFS-RTのアーカイブデータが存在していないか調べると、以下のサイトにアーカイブが存在していることがわかります。

https://gtfsrt.io/#inventory

ブラウザから閲覧はできないので、データを取得するファイルのコードをLLMを用いて実装するとよいでしょう。  
以下にその例を示します。

```py
from __future__ import annotations

import base64
import re
from datetime import datetime, timedelta, timezone
from pathlib import Path
from urllib.parse import quote

import requests
from google.protobuf.json_format import MessageToJson
from google.transit import gtfs_realtime_pb2


EDT = timezone(timedelta(hours=-4), "EDT")
TARGET_LOCAL = datetime(2026, 7, 4, 18, 0, 0, tzinfo=EDT)

FEED_TYPE = "vehicle_positions"
FEED_URL = "https://bctmyride-buspas.com:8080/GTFS/VehiclePositions"
PROTOBUF_BUCKET = "protobuf.gtfsrt.io"
PARQUET_BUCKET = "parquet.gtfsrt.io"

OUTPUT_DIR = Path("bct_vehicle_positions_2026-07-04_1800_EDT")
OUTPUT_STEM = "bct_vehicle_positions_2026-07-04_1800_EDT"


def encode_feed_url(url: str) -> str:
    """Convert the original feed URL to the base64url key used by gtfsrt.io."""
    return (
        base64.urlsafe_b64encode(url.encode("utf-8"))
        .decode("ascii")
        .rstrip("=")
    )


def parse_object_timestamp(object_name: str) -> datetime:
    """Parse the UTC timestamp from a gtfsrt.io raw protobuf object path."""
    filename = object_name.rsplit("/", 1)[-1]
    timestamp_text = filename.removesuffix(".pb")
    return datetime.strptime(timestamp_text, "%Y-%m-%dT%H:%M:%S.%fZ").replace(
        tzinfo=timezone.utc
    )


def parquet_index_url(date_partition: str, encoded_feed_url: str) -> str:
    """Build the public daily Parquet URL for this feed and date."""
    return (
        f"http://{PARQUET_BUCKET}/{FEED_TYPE}/"
        f"date={date_partition}/"
        f"base64url={encoded_feed_url}/"
        "data.parquet"
    )


def scan_parquet_for_source_files(
    date_partition: str,
    encoded_feed_url: str,
) -> list[str]:
    """Find raw .pb source_file paths by scanning gtfsrt.io's public Parquet file.

    The raw protobuf bucket currently denies anonymous directory listing, but
    the public Parquet file contains source_file values. Those values point to
    the original raw protobuf object paths.
    """
    url = parquet_index_url(date_partition, encoded_feed_url)
    response = requests.get(url, timeout=120)
    response.raise_for_status()

    encoded_feed_url_bytes = encoded_feed_url.encode("ascii")
    prefix = f"{FEED_TYPE}/date={date_partition}/hour=".encode("ascii")

    object_path_pattern = (
        re.escape(prefix)
        + rb"\d{4}-\d{2}-\d{2}T\d{2}:00:00Z"
        + rb"/base64url="
        + re.escape(encoded_feed_url_bytes)
        + rb"/"
        + rb"\d{4}-\d{2}-\d{2}T\d{2}:\d{2}:\d{2}\.\d+Z\.pb"
    )

    return sorted(
        {
            match.decode("ascii")
            for match in re.findall(object_path_pattern, response.content)
        }
    )


def select_closest_source_file(encoded_feed_url: str) -> tuple[str, datetime]:
    """Select the archived snapshot nearest to TARGET_LOCAL."""
    target_utc = TARGET_LOCAL.astimezone(timezone.utc)
    date_partition = target_utc.strftime("%Y-%m-%d")
    source_files = scan_parquet_for_source_files(date_partition, encoded_feed_url)

    if not source_files:
        raise RuntimeError(f"No source files found for {date_partition}")

    selected = min(
        source_files,
        key=lambda object_name: abs(parse_object_timestamp(object_name) - target_utc),
    )
    return selected, parse_object_timestamp(selected)


def download_raw_protobuf(object_name: str) -> bytes:
    """Try to download the raw archived protobuf from Google Cloud Storage."""
    encoded_name = quote(object_name, safe="/=:.")
    url = f"https://storage.googleapis.com/{PROTOBUF_BUCKET}/{encoded_name}"
    response = requests.get(url, timeout=60)
    response.raise_for_status()
    return response.content


def set_if_present(message, field_name: str, value) -> None:
    """Set a protobuf field only when the Parquet value is not NULL."""
    if value is not None:
        setattr(message, field_name, value)


def reconstruct_protobuf_from_parquet(
    object_name: str,
    encoded_feed_url: str,
) -> bytes:
    """Rebuild a GTFS-RT FeedMessage from the public Parquet rows.

    This is the fallback path used when the raw .pb object returns 403. It is
    still a GTFS-RT protobuf at the end; it is just reconstructed from the
    normalized gtfsrt.io Parquet representation.
    """
    try:
        import duckdb
    except ImportError as exc:
        raise RuntimeError(
            "duckdb is required when raw .pb download is denied. Run with: "
            "uv run --with requests --with gtfs-realtime-bindings "
            "--with duckdb python fetch_bct_vehicle_positions_20260704_1800_edt.py"
        ) from exc

    date_partition = parse_object_timestamp(object_name).strftime("%Y-%m-%d")
    url = parquet_index_url(date_partition, encoded_feed_url)

    con = duckdb.connect()
    con.execute("INSTALL httpfs; LOAD httpfs;")
    rows = con.execute(
        """
        SELECT
            feed_timestamp,
            entity_id,
            trip_id,
            route_id,
            direction_id,
            start_time,
            start_date,
            schedule_relationship,
            vehicle_id,
            vehicle_label,
            license_plate,
            latitude,
            longitude,
            bearing,
            odometer,
            speed,
            current_stop_sequence,
            stop_id,
            current_status,
            timestamp,
            congestion_level,
            occupancy_status,
            occupancy_percentage
        FROM read_parquet(?)
        WHERE source_file = ?
        ORDER BY entity_id
        """,
        [url, object_name],
    ).fetchall()

    if not rows:
        raise RuntimeError(f"No Parquet rows found for source_file: {object_name}")

    feed = gtfs_realtime_pb2.FeedMessage()
    feed.header.gtfs_realtime_version = "2.0"

    # feed_timestamp is the timestamp from the GTFS-RT header.
    if rows[0][0] is not None:
        feed.header.timestamp = int(rows[0][0])

    for row in rows:
        (
            _feed_timestamp,
            entity_id,
            trip_id,
            route_id,
            direction_id,
            start_time,
            start_date,
            schedule_relationship,
            vehicle_id,
            vehicle_label,
            license_plate,
            latitude,
            longitude,
            bearing,
            odometer,
            speed,
            current_stop_sequence,
            stop_id,
            current_status,
            timestamp,
            congestion_level,
            occupancy_status,
            occupancy_percentage,
        ) = row

        entity = feed.entity.add()
        entity.id = entity_id or ""

        vehicle = entity.vehicle
        set_if_present(vehicle.trip, "trip_id", trip_id)
        set_if_present(vehicle.trip, "route_id", route_id)
        set_if_present(vehicle.trip, "direction_id", direction_id)
        set_if_present(vehicle.trip, "start_time", start_time)
        set_if_present(vehicle.trip, "start_date", start_date)
        set_if_present(vehicle.trip, "schedule_relationship", schedule_relationship)

        set_if_present(vehicle.vehicle, "id", vehicle_id)
        set_if_present(vehicle.vehicle, "label", vehicle_label)
        set_if_present(vehicle.vehicle, "license_plate", license_plate)

        if latitude is not None and longitude is not None:
            vehicle.position.latitude = latitude
            vehicle.position.longitude = longitude
            set_if_present(vehicle.position, "bearing", bearing)
            set_if_present(vehicle.position, "odometer", odometer)
            set_if_present(vehicle.position, "speed", speed)

        set_if_present(vehicle, "current_stop_sequence", current_stop_sequence)
        set_if_present(vehicle, "stop_id", stop_id)
        set_if_present(vehicle, "current_status", current_status)
        set_if_present(vehicle, "timestamp", timestamp)
        set_if_present(vehicle, "congestion_level", congestion_level)
        set_if_present(vehicle, "occupancy_status", occupancy_status)
        set_if_present(vehicle, "occupancy_percentage", occupancy_percentage)

    return feed.SerializeToString()


def get_protobuf_data(object_name: str, encoded_feed_url: str) -> tuple[bytes, str]:
    """Prefer raw .pb; fall back to Parquet reconstruction if GCS denies access."""
    try:
        return download_raw_protobuf(object_name), "raw protobuf"
    except requests.HTTPError as exc:
        status_code = exc.response.status_code if exc.response is not None else None
        if status_code != 403:
            raise
        return (
            reconstruct_protobuf_from_parquet(object_name, encoded_feed_url),
            "reconstructed protobuf",
        )


def main() -> None:
    encoded_feed_url = encode_feed_url(FEED_URL)
    target_utc = TARGET_LOCAL.astimezone(timezone.utc)

    print(f"Target local : {TARGET_LOCAL.isoformat()}")
    print(f"Target UTC   : {target_utc.isoformat()}")
    print(f"Feed URL     : {FEED_URL}")

    object_name, selected_utc = select_closest_source_file(encoded_feed_url)
    protobuf_data, source_kind = get_protobuf_data(object_name, encoded_feed_url)

    feed = gtfs_realtime_pb2.FeedMessage()
    feed.ParseFromString(protobuf_data)

    OUTPUT_DIR.mkdir(parents=True, exist_ok=True)
    pb_path = OUTPUT_DIR / f"{OUTPUT_STEM}.pb"
    json_path = OUTPUT_DIR / f"{OUTPUT_STEM}.json"

    pb_path.write_bytes(protobuf_data)
    json_path.write_text(
        MessageToJson(feed, preserving_proto_field_name=True, indent=2),
        encoding="utf-8",
    )

    header_timestamp = None
    if feed.header.HasField("timestamp"):
        header_timestamp = datetime.fromtimestamp(
            feed.header.timestamp,
            tz=timezone.utc,
        ).isoformat()

    print(f"Selected UTC : {selected_utc.isoformat()}")
    print(f"Difference   : {abs(selected_utc - target_utc)}")
    print(f"Object       : {object_name}")
    print(f"Source kind  : {source_kind}")
    print(f"Entities     : {len(feed.entity)}")
    print(f"Header time  : {header_timestamp}")
    print(f"PB           : {pb_path.resolve()}")
    print(f"JSON         : {json_path.resolve()}")


if __name__ == "__main__":
    main()
```

以下のようなJSONが得られます。

```json
    {
      "id": "26MAY_36-01_8_s",
      "vehicle": {
        "trip": {
          "trip_id": "26MAY_36-01_8_s",
          "start_time": "",
          "start_date": "",
          "schedule_relationship": "SCHEDULED",
          "route_id": "BCT36"
        },
        "position": {
          "latitude": 26.145458,
          "longitude": -80.211624
        },
        "timestamp": "1783202393",
        "vehicle": {
          "id": "20094",
          "label": "BCT36 SUNRISE - A1A via LAUDERHILL TRANSIT CENTER",
          "license_plate": ""
        }
      }
    },
```

この周辺がFlagとなります。

Flag設定値: 26.145481, -80.211137 （許容誤差: 70m）

## お詫び

もっとも18時に近いデータとして17:59:53に由来する座標と許容範囲を設定しておりましたが、18:00:11のデータが存在していることを考えると、Flagの設定が不十分でした。ご指摘をもとに、競技中に座標を修正したほか、遡及対応を行いました。  
ご不便をおかけしたことをお詫び申し上げます。
