# air2air2 (445pt / 85 solves)

## 問題文

動画 / Video: https://www.youtube.com/watch?v=Mm3CgN6mbVU

この動画は現地時間の2026年1月9日に撮影された。  
この動画に映っている航空機の機体記号（登録番号）と、コールサインは何か。アンダースコア (`_`) で繋いで解答せよ。  
たとえば、機体記号が F-WWJJ で、コールサインが AIB789 のとき、Flagは `Diver26{F-WWJJ_AIB789}` となる。  
**注意**:撮影者が搭乗している機体ではない。また、コールサインはICAOコードを使用すること。

This video was filmed on January 9, 2026, in local time.  
Answer with the aircraft registration number and call sign shown in this video, connected with an underscore (`_`).   
For example, if the registration number is F-WWJJ and the call sign is AIB789, the flag should be `Diver26{F-WWJJ_AIB789}`.   
**Note**: This does not refer to the aircraft the person filming is on board. Also, use the ICAO code for the callsign.


## 解法

映っている飛行機を判別しましょう。動画後半を拡大してみると、"AIR CANADA" と書かれています。[エア・カナダの機種一覧ページ](https://www.aircanada.com/ca/en/aco/home/fly/onboard/fleet.html#/)を見てみると、横から見た航空機のイラストが掲載されています。これを見ると、胴体の長さやロゴの配置から、映っているのはB777-300ER（77W）であると考えられます。

続いて、撮影者の搭乗機も判別しましょう。  
主翼が映っている部分をGoogle Lensに掛けると、ボーイング787であるとわかります。また、ピンクと紺色・青色と思われるデザインが写った、安全のしおり（Safety Instructions）らしきものが冒頭に写り込んでおり、航空機の一部を描いたようなイラストも見切れた（何かで隠れた）状態で映っています。

[B787を運航している航空会社の一覧](https://en.wikipedia.org/wiki/List_of_Boeing_787_operators)を探してみましょう。これらのリストの中から、サーモンピンクと紺色のデザインの機体を持つのは[Air Japan（AJX/NQ）](https://en.wikipedia.org/wiki/Air_Japan)だけであり、同社は "Air Japan"ブランドを2026年3月まで運航していたことから、撮影時期と合致します。また、Air Japanの写真を見てみると、「航空機の一部を描いたようなイラスト」は同社の機体の垂直尾翼の塗装パターンと一致します。

[公式サイトによれば、同社はANAの子会社である](https://www.air-japan.co.jp/)ため、ANA塗装の航空機を多数保有しているようです。[Planespotters](https://www.planespotters.net/airline/Air-Japan)や[Flyteam](https://flyteam.jp/airline/air-japan/aircrafts)などで、AirJapanの機材一覧を見てみると、JA801A、JA802A、JA803Aの3機のみが「AirJapan」としての塗装が施されていたことが分かります。

対象日が1日であり、対象機が3機であれば人力で総当たりできる範囲です（必要であれば総当たりする根性もOSINTに必要なことです）。また、機窓から地面が見えていることから、着陸態勢のものに絞れるでしょう。

Flightradar24では過去のデータは課金が必要なので、ADS-B Exchangeを使いましょう。

すると、成田空港に着陸するJA803A（AJX122）の航跡が条件と合いそうです。また、成田空港は滑走路が2本あることが衛星画像や各種資料から確認でき、「2機並んで着陸している」状況とも符合します。

- https://globe.adsbexchange.com/?icao=86ceb0&lat=35.656&lon=140.398&zoom=11.0&showTrace=2026-01-09&leg=2&trackLabels

この日付・時刻に遡ると、AJX122の右側を飛行するエア・カナダのB777-300ERが確認できます。

https://globe.adsbexchange.com/?replay=2026-01-09-06:52&icao=86ceb0&lat=35.664&lon=140.459&zoom=12.2

Flag: **Diver26{C-FIVW_ACA9}**