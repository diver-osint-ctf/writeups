# flight_from

## 問題文

画像 / Image:  
https://drive.google.com/file/d/14LSICiwmUqG9xqAfAm75IVdGd7P12uoy/view?usp=sharing

このヘリコプターが出発した飛行場のICAOコード（4レターコード）で答えよ。  
Flag形式: `Diver25{RJTT}`

Answer with the ICAO code (4 letter code) of the airfield from which this helicopter departed.  
Flag Format: `Diver25{RJTT}`


## ヒント

1. データを入念に確認してください。あなたのOSINT能力を期待しています。 / Confirm the data carefully. We expect your OSINT ability.

## 難易度

introduction / 100 point (362 solves)

## 解法

Flightradar24 のスクリーンショットが与えられます。

画像には **OKO (TOKYO)** と表示されています。これは東京にある横田飛行場を示しているのですが、スクリーンショットの航跡を拡大すると、横田飛行場ではない場所から線が延びていることが分かります。"立川（Tachikawa）" など、周辺の地名を手がかりに、この地点を Google Maps で表示すると、別の飛行場が存在していることが分かります。

つまり、"OKO" は Flightradar24 によって誤認識されたものであると判明します。

`Tachikawa airport`（`立川　飛行場`）などと Google 検索すると、「[立川飛行場](https://en.wikipedia.org/wiki/Tachikawa_Airfield)」が存在することが判明します。この飛行場の ICAO コードは **RJTC** であることから、Flag は以下の通りとなります。

**Diver25{RJTC}**

## 出題意図

Flightradar24のような、公開されたデータソースは非常に便利です。しかし、誤りが含まれている可能性を常に考慮する必要があります。時にはこのような表示エラーから勘違いが発生し、偽情報が拡散することもあります。  
与えられたデータが本当に信頼できるものであるか確認し、時には訂正することもOSINTの初歩であると考え、introductionカテゴリで出題しました。