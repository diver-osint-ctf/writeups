# station

## 問題文

この写真が撮影された駅はどこか。駅名を答えよ（日本語でも英語でも可）。  
（駅名は鉄道会社の公式サイトやWikipediaに記載されている表記とする）  
Flag形式: `Diver25{京都駅}`

Which station was this photograph taken at? Answer the name of the station.  
(The station name should be as it appears on the official website of the railway company or on Wikipedia.)  
Either Japanese or English are okay.  
Flag Format: `Diver25{Kyoto Station}`



[配布ファイル](./public)

## ヒント

1. `10両 9号車乗車口` means ` No.9 car's door of 10-cars train` 
2. `弱冷房車` means `mildly air-conditioned train car` 

## 難易度

easy / 136 point (192 solves)

## 解法

足下のオレンジ色の帯を Google Lens で画像検索すると、JR 東日本の中央線に関する情報がヒットします。

JR 中央線について[Wikipedia の記事](https://ja.wikipedia.org/wiki/%E4%B8%AD%E5%A4%AE%E7%B7%9A%E5%BF%AB%E9%80%9F)などを参照すると、「[E233 系 0 番台](https://ja.wikipedia.org/wiki/JR%E6%9D%B1%E6%97%A5%E6%9C%ACE233%E7%B3%BB%E9%9B%BB%E8%BB%8A#0%E7%95%AA%E5%8F%B0)」という車両が使われていることがわかります。

Wikipedia の記事を確認すると

> 青梅線・五日市線での運用を基本とする **6 両編成** 10 本（青 600 番台編成・60 両）と **4 両編成** 8 本（青 400 番台編成・32 両）がある

という記述が確認できます（[英語版 Wikipedia](https://en.wikipedia.org/wiki/E233_series#E233-0_series)にも、6 両編成と 4 両編成の記載があります）。

ここで[青梅線](https://ja.wikipedia.org/wiki/%E9%9D%92%E6%A2%85%E7%B7%9A)（[英語版](https://en.wikipedia.org/wiki/%C5%8Cme_Line)）について検索すると、10 両編成・6+4 両編成の列車が運用されていることが記載されています。一方で、[五日市線](https://ja.wikipedia.org/wiki/%E4%BA%94%E6%97%A5%E5%B8%82%E7%B7%9A)（[英語版](https://en.wikipedia.org/wiki/Itsukaichi_Line)）について検索すると、6 両または 4 両の列車が運用されていることが記載されています。

写真のオレンジ色の帯には「10 両編成」「6 両編成」の両方の記載があったので、青梅線が条件を満たすと考えられます。立川駅から順に青梅線の駅を Google Maps とストリートビューで確認すると、牛浜駅の前に「らいと」という店が確認でき、この駅で撮影されたものだと分かります。

**Diver25{牛浜駅}**

## 出題意図

交通機関は場所や路線ごとに特徴が多いほか、オンラインから得られる情報も数多くあります。画像から得られる文字情報と、オンラインから得られる情報を組み合わせて場所を絞り込んでもらうことを意図しています。