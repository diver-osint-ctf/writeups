# louvre

## 問題文

ルーブル美術館の公共Wi-Fiアクセスポイントのうち、以下の条件を満たすもののベンダーを答えよ。

- 情報は2025年2月28日に収集されており、オンライン上で確認できる。
- ベンダーはBSSIDに準拠して判定せよ。

Flag形式: `Diver25{Company Name}` (例: Apple Inc.の場合、`Diver25{Apple Inc.}` となる。)

Answer the vendor of one of the Louvre's public Wi-Fi access points that meets the following criteria.

- Information was collected on 28 February 2025. This can be accessed via online.
- Determine the vendor according to the BSSID.

Flag format: `Diver25{Company Name}` (e.g. If the company is Apple Inc., the flag should be `Diver25{Apple Inc.}`.)


## ヒント

1. Wi-Fiアクセスポイントに関して、有名なサイトがあるはずです。 / There should be a well-known website on Wi-Fi access points.
2. BSSIDの仕様について調べてみましょう。 /Find out about the BSSID specifications.

## 難易度

introduction / 176 point (181 solves)

## 解法

`Louvre wifi` で Google 検索を行うと、ルーブル美術館の公式サイトで **Louvre_Wifi_Gratuit** という SSID が示されています。

https://contact.louvre.fr/hc/en-gb/articles/12853523479453-Do-you-offer-WiFi

Wi-Fi アクセスポイントの情報を調査する場合、WiGLE を使用します（知らない場合でも、`Wi-Fi OSINT`などと Google 検索するとヒットします）。

WiGLE の[検索ページ](https://wigle.net/mapsearch)で、ルーブル美術館近辺を表示して SSID `Louvre_Wifi_Gratuit` を検索すると、以下の 2 件がヒットします。

- Louvre_Wifi_Gratuit (50:60:28:4E:17:E0) ch:1 2001-01-01 - 2025-02-28
- Louvre_Wifi_Gratuit (50:60:28:4E:17:F0) ch:40 2001-01-01 - 2025-02-28

さて、BSSID とは何でしょうか。調べてみると、無線ネットワーク内の特定のアクセスポイントに固有の識別子であり、通常は MAC アドレスをそのまま使うことがわかります。

- https://www.atera.com/blog/computer-terms-unwrapped-what-is-bssid/
- https://e-words.jp/w/BSSID.html

[MAC アドレス](https://en.wikipedia.org/wiki/MAC_address)について調べると、最初の 3 オクテットがベンダーを示す [Organizationally unique identifier](https://en.wikipedia.org/wiki/Organizationally_unique_identifier) (OUI) であるとわかります。  
つまり、`00:00:5E:00:53:AA` という MAC アドレスがあった場合、`00:00:5E` がベンダーを示すことになります。

MAC アドレスの OUI からベンダー名を検索するサイトは多数存在しており、`MAC address vendor` などで検索するとヒットします。以下にその一例を示します。

- https://macvendors.com/
- https://uic.jp/mac/address/506028/

複数のソースより **Xirrus Inc.** という情報が得られます。これより、Flag はこの社名となります。

**Diver25{Xirrus Inc.}** (**Diver25{Xirrus Inc}**, **Diver25{Xirrus}** なども正解)

## 出題意図

Wi-Fi 関連の OSINT ツールとして定番である、WiGLEについて知ってもらうための問題です。また、OUIといった技術的仕様についても知ってもらうきっかけになることも意図しています。

## 競技中の対応

`*Louvre_Wifi_Gratuit` というアスタリスクを含んだSSIDが存在しており、そちらはHewlett Packard Enterpriseのものでした。そのため、競技中に以下のFlagを追加し、遡及して正解として取り扱っています。

- **Diver25{Hewlett Packard Enterprise}**