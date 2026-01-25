# debeyohiru_04_meal (194pt / 198 solves)

## 問題文

`debeyohiru` はある料理が好物で、よく食べているようです。
直近では2026年1月10日の夕食にその料理を食べたことが確認されています。
この人物がこの日の夕食に食べたメニューを特定し、店舗のメニューに記載された名前で解答してください。

例えば、マクドナルドでビッグマックを食べたことが特定できた場合、Flagは `SWIMMER{ビッグマック}` になります。 
メニュー名の表記は店舗のメニューの **日本語** 表記に準拠してください。


`debeyohiru` has a favorite dish and seems to eat it frequently.
Most recently, it was confirmed that they ate this dish for dinner on January 10, 2026.

Identify the menu item they ate for dinner on this day and answer with the name exactly as listed on the restaurant's menu.

For example, if it is determined that they ate a Big Mac at McDonald's, the Flag would be `SWIMMER{ビッグマック}`.
Please ensure the menu item name follows the **Japanese** notation used on the restaurant's menu.


## 解法

debeyohiru のBlueskyを参照すると、2026年1月10日に以下の投稿が見つかります。

- [今宵も来たぞ。今日は単品でいいや](https://bsky.app/profile/debeyohiru.bsky.social/post/3mc2utbra622w)

この投稿は別の[投稿](https://bsky.app/profile/debeyohiru.bsky.social/post/3mazue5yqdc2n)のリプライであり、元の投稿にはオムライスの写真が添付されています。
皿に映ったロゴから調査を行うことで、これは「ポムの樹」というチェーン店のオムライスであることがわかります。

以上のことから、彼がこの日の夕食に「ポムの樹」でオムライスを食べたことは間違いないようです。


また、Bluesky上の投稿やプロフィールページの記載から、彼は渋谷を中心に行動していることが推測できます。
ポムの樹の店舗の所在地を確認していくと、渋谷には「[ポムの樹 渋谷スペイン坂店](https://www.pomunoki.com/shop/kanto/tokyo/shop-0424.html)」が存在するようです。

この店舗についてGoogle Mapで調査してみると、「ふらいご」を名乗るアカウントからのレビュー投稿が発見できます。

- [2026/1/10 冬限定メニューを食べました。](https://maps.app.goo.gl/PVChg7MuExPjmEvJA)

掲載されている画像から、メニューを特定しましょう。レビューには限定メニューであると記載されていることから、 `ポムの樹　限定メニュー` とGoogle検索すると、以下のページがヒットします。

- [「冬のごちそうフェア」「チョコレートフェア」のご案内（2025年12月10日から）](https://www.pomunoki.com/pomunoki/fairmenu/)

Flag: **`SWIMMER{豚肉とリンゴのホタテトマトクリームオムライス}`**

