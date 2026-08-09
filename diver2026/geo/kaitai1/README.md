# kaitai1 (450pt / 81 solves)

## 問題文

この電柱の、すぐ奥に見えている土地の **[地番](https://ja.wikipedia.org/wiki/%E5%9C%B0%E7%95%AA)** を **半角数字** で答えよ。  
なお、[住居表示](https://ja.wikipedia.org/wiki/%E4%BD%8F%E5%B1%85%E8%A1%A8%E7%A4%BA) の実施状況にかかわらず **地番** で解答せよ。  
例えば、`東京都新宿区西新宿二丁目318-18` の場合、Flag は `Diver26{318-18}` となる。

Answer the ["land lot number" (地番, chiban)](https://ja.wikipedia.org/wiki/%E5%9C%B0%E7%95%AA) in **numeric** form for the plot of land visible just behind this utility pole.  
Use the "land lot number," regardless of the status of the [residential addressing system (住居表示, jūkyo-hyōji)](https://ja.wikipedia.org/wiki/%E4%BD%8F%E5%B1%85%E8%A1%A8%E7%A4%BA).  
For example, if the address were `318-18 Nishi-Shinjuku 2-chome, Shinjuku-ku, Tokyo`, the flag should be `Diver26{318-18}`.


## 配布ファイル

- [kaitai.jpg](./public/kaitai.jpg)

## 解法

Google Lens で逆画像検索を行うと、この落書きがソーシャルメディア上で複数の人に言及されていることがわかります。

- https://x.com/mitanimmk/status/1964671758197498128
- https://x.com/mametaro_1016/status/1965048676008825136
- https://x.com/Blackkaya/status/2065671954879897950
- https://x.com/Bashamichi_H/status/2074354336306749693
- https://www.instagram.com/p/DZZi3yHjzlC/?img_index=3

写真を拡大すると、電柱の看板に "...AGAYA" という文字が見えます。また、前述のソーシャルメディアには東京にあるという言及もあります。  
これらから、[東京都の特別区の一覧](https://en.wikipedia.org/wiki/Special_wards_of_Tokyo) を確認すると、「世田谷」（Setagaya）にあるのではないかと考えられます。

先ほどのソーシャルメディア上の投稿を調べると、背景に「パチンコ　ミナミ」と書かれた青い看板が写っているものもあります。

`"世田谷区" "ミナミ"` で Google 検索すると、[東京都世田谷区北沢2丁目に存在するパチンコ関連企業](https://www.navitime.co.jp/poi?spot=01376-19020301004)が見つかります。

これをもとに、世田谷区北沢付近を Google Earth の 3D 表示で確認すると、35.662237, 139.669114 付近に「パチンコ　ミナミ」の看板を確認できます。看板が写る画角や背景の建物などから、「ねこかいたいね」という落書きがある電柱は、35.662699, 139.668415（北沢2丁目32付近）にあると判断できます。

ここで求められているのは「地番」です。`北沢2丁目 地番` などで Google 検索を行うと、東京都主税局の[地籍図](https://www.tax1.metro.tokyo.lg.jp/chisekizu/data/setagaya/index2.html)が見つかります。

そのうち、北沢2丁目を示すファイル（以下の PDF）にアクセスします。地図や衛星画像と比較すると、`959-23` が電柱の背景にある空き地のような場所を示しているとわかります。  
https://www.tax1.metro.tokyo.lg.jp/chisekizu/data/setagaya/040.pdf

Flag: **Diver26{959-23}**