# italy

## 問題文

2023年10月27日、新潟大学に通う学生が「珍しいことにイタリアのヘリコプターがキャンパスの上空を通った」と話していた。  
しかし、周囲からは「ヘリコプターは長距離を飛べない。イタリアから新潟に来られるわけがない」と一蹴されてしまった。  
彼の主張を裏付けるため、以下のものを調べてほしい  

- ヘリコプターの保有者（社名）
- キャンパス上空を通過した時刻（JST）と、そのときの時の気圧高度

Flag形式: `Diver24{社名_hh:mm:ss(JST)_高度}`  
たとえば、"Diver"社のヘリが9:10:12(JST)に高度1000ftで通過した場合、Flagは `Diver24{Diver_09:10:12_1000}` となる。

On 27 October 2023, a student from Niigata University said "Unusually, an Italian helicopter passed over our campus".  
However, those around him brushed it off, saying that helicopters cannot fly long distances. There is no way they could come to Niigata, Japan from Italy’.  
To corroborate his claims, we would like you to look into the following information

- Owner of the helicopter (company name)
- Time of passage over the campus (in JST) and the barometric altitude at the time

Flag format: `Diver24{company name_hh:mm:ss(JST)_altitude}`  
For example, on 9:10:12 JST ,the helicopter which is owned by the company named "Diver" passed over there in 1000ft, the flag will be `Diver24{Diver_09:10:12_1000}`


## 難易度
hard/ 481 point (23 solves)

## 解法

<details>

<summary>クリックで表示</summary>

まず、イタリア国籍の航空機には　`I-****` という機体記号（機体番号）が割り当てられていることが分かります（参考:[Wikipedia](https://ja.wikipedia.org/wiki/%E6%A9%9F%E4%BD%93%E8%A8%98%E5%8F%B7)）。

航空機の航跡データというとFlightradar24が有名ですが、過去のデータを遡るには課金アカウントが必要です。このような場合は代替サービスを探してみましょう。

`flightradar alternative` で検索すると、いくつかのサイトで [ADS-B Exchange](https://globe.adsbexchange.com/) が紹介されています。

続いて、特定の日時が示されていることから、ADS-B Exchangeの[Replay機能](https://globe.adsbexchange.com/?replay)で2023年10月27日の新潟大学付近のフライト記録を探します。

[新潟大学のキャンパス](https://www.niigata-u.ac.jp/university/map/)は2つありますが、いずれも新潟市に位置しているため、新潟市付近を広めに見てヘリコプターが出現する時間を探ります。早送りでしばらく眺めていると、UTCで4時台ごろに`I-LIDI` というヘリコプターが新潟上空を通過したことがわかります。

`I-LIDI` をGoogle検索すると、[Flyteam](https://flyteam.jp/photo/3809625)や[Flightradar24](https://www.flightradar24.com/data/aircraft/i-lidi)などの記載から、[Alidaunia](https://alidaunia.it/)の機材であることがわかります。

また、`I-LIDI`をADS-B Exchange内の検索から[個別に遡る](https://globe.adsbexchange.com/?icao=3007a7&lat=37.868&lon=138.934&zoom=14.9&showTrace=2023-10-27&timestamp=1698381947)と、04:45:46Z（日本時間13:45:46）に1600ftで新潟大学の五十嵐キャンパス上空を飛行していることが確認でき、これがFlagとなります。

**Diver24{Alidaunia_13:45:46_1600}**（表記揺れやデータソースによる誤差も考慮）

なお、Flightradar24に課金している場合、ADS-B Exchangeと同様にプレイバック機能から確認できます。こちらは秒単位の記録がブラウザ上では確認できないため、`I-LIDI`の記録ページからKMLファイルをダウンロードして位置を確認できます。

本問題では、航空機の航跡情報としてADS-B Exchangeを参照することをねらいとしています。ADS-B Exchangeはカバレッジ（カバーしているエリア）こそFlightradar24に比べて狭いものの、[軍用機やプライベートジェットであっても検閲を行わないという方針](https://www.adsbexchange.com/faq/)をとっており、調査報道においてよく用いられます。

- [衝突した海保機、事故前24時間以内に震災対応で2回飛行＝関係者（ロイター）](https://jp.reuters.com/world/japan/GFJU5P3EXBO5LMGCMXKL5SVXUM-2024-01-05/)
- [米軍ヘリ、スカイツリー周辺で飛行　ルートに設定か　目的は明かさず（毎日新聞）](https://mainichi.jp/articles/20230613/k00/00m/040/100000c)
- [サウスウエスト航空の旅客機、４月に海面寸前まで急降下－無事に着陸（ブルームバーグ）](https://www.bloomberg.co.jp/news/articles/2024-06-14/SF31ENT0G1KW00)
- [A 17-minute flight? The super-rich who have ‘absolute disregard for the plane（The Guardian）](https://www.theguardian.com/environment/2022/jul/21/kylie-jenner-short-private-jet-flights-super-rich-climate-crisis)

</details>