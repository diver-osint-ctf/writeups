# chiban

## 問題文
画像の中央に写っている道路の地番は何か。  
たとえば住所が `仙台市宮城野区二十人町 303-8` の場合、Flagは `Diver24{303-8}` となる。  
また、地番には数字だけでなく漢字が含まれることもある。その場合は漢字表記のまま解答せよ。

What is the land lot number (地番, *chiban*) of the road in centre of image? Answer in Japanese.  
For examle, if the address is `仙台市宮城野区二十人町 303-8`, the flag should be `Diver24{303-8}`.  
Also, some land lot number includes not only numbers but also Kanji (Chinese characters). In that case, please answer as is in Kanji.

## 難易度

medium / 184 point (90 solves)

## 解法

<details>

<summary>クリックで表示</summary>

まずは撮影地を特定します。

いくつか使えるものがあるのですが、一例として一番大きく写り込んでいる「サンディ」を使ってみましょう。

CTF開催時点では「サンディ　7号店」でGoogle検索しても結果に結びつかないのですが、画像検索をすると「7号店」の画像がいくつかヒットします。

https://www.pinterest.jp/pin/582442164309737754/
https://www.ekiten.jp/shop_590950/

これより、7号店が「双葉店」であることが判明します。

また、Google Lensを使うという手もあります。
このような街並みの画像では、同じ構図の画像は出にくいため、全体を囲っても有用な結果は出ません。  
しかし、ビルや店舗単位で囲うと、その店舗や建物を紹介するWebサイトの画像がヒットするケースがあります。

今回の場合、中央右側に写っているマンションを囲うことで[不動産情報がヒット](https://www.cjs.ne.jp/chintai/detail_b/T0000344986.html)することがレビュー時点で確認されています。

いずれにせよ、この写真の撮影場所は大阪府茨木市双葉町であると判断できます。
https://maps.app.goo.gl/hqYSUqwWvrfqHcjb9

Google Mapsに住所や番地は表示されていますが、「[地番](https://www.zenrin-datacom.net/solution/blog/chiban-address-difference)」は表示されていません。しかし、地番の情報を管轄する法務局がデータを公開しており、その一部はオンラインでも参照できます。  
`地番　検索` などとGoogle検索すると、地図に重ね合わせたサイトが閲覧できます。以下はその一例です。

https://labs.mapple.com/mapplexml.html#18.66/34.8161147/135.5790964

ここで確認できる情報より、`筆界未定地-6` が道路の地番となります。

**Diver24{筆界未定地-6}**

この問題はジオロケーションを経て公的なデータにアクセスしてもらうことを意図しています。  
特に一次ソースとして公的データは利用価値が高く、OSINTを行う際には情報源として頭に入れておいてほしいと願っています。

</details>