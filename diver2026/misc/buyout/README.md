# buyout (320pt / 152 solves)

## 問題文

2024年4月、ザンビアにて大規模な詐欺拠点が摘発された。
高級住宅地に立地するこの拠点は、2026年現在ではホテルとして営業しているようだ。
このホテルの屋号を答えよ。
例えば、屋号が `Diver Premiere Hotel` であったとき、Flagは `Diver26{Diver Premiere Hotel}` となる。

In April 2024, a large-scale fraud operation was raided in Zambia.
Located in an upscale residential area, this former base appears to be operating as a hotel as of 2026.
Answer the name of this hotel.
For example, if the name of the hotel is `Diver Premiere Hotel`, the flag should be `Diver26{Diver Premiere Hotel}`.


## 解法
`Zambia scam 2024`といった検索ワードで、各種の事件を報道する記事を見つけることができます。また、実際の取り締まり時の写真を転載した記事も確認できます。  

- https://www.facebook.com/100070332720612/photos/473740671647020/
- https://www.facebook.com/watch/?v=757917159656347/
- https://x.com/zadama24/status/1777689616008515773/

これらの写真を見ると、緑色の切妻破風や白石を敷き詰めた駐車場、プールの存在が確認できるため、Google mapなどから取得できるルサカ・ローマ地区周辺の航空写真から、これらの特徴を満たす建築物を探します。すると、`-15.383224, 28.317284`にそれらしい物件を見つけることができます。  

Google mapにはこの物件のホテルとしての情報は記載されていませんが、Bing mapやYandex mapといった地図サイトにおいては、"Le Dolphin's Grand Paradiso"という屋号が掲載されています。また、この屋号および住所をもとにさらに検索すると、"Gianpiero's bed and breakfast"という古い屋号を確認することもできます。  

これらのホテル名で検索して画像を見ると、[レストランに飾られている絵](https://q-xx.bstatic.com/xdata/images/hotel/1280x964/495613305.webp?k=81c236faf37ac8c253eb8686403a51e99161eb1e0fed832570607c87a0836d3b&o=&a=2195102)や[プール周辺のタイル](https://content.skyscnr.com/available/2662701587/2662701587_960x960.jpg)といった細部意匠についても、詐欺事件の取り締まり時に撮影されたものと一致していることが確認できます。

Flag: **Diver26{Le Dolphin's Grand Paradiso}**（"Gianpiero's bed and breakfast"も可）
