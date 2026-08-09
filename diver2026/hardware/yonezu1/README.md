# yonezu 1 (100pt / 316 solves)

## 問題文

音楽家の米津玄師は、サメを模した乗り物を用いたパフォーマンスを行った。  
公開情報から判断できる限りで、この乗り物の駆動プラットフォームはどの企業の製品を利用していると考えられるか。**英語表記** で答えよ。  
例えばボーイング社が答えの場合、flag は `Diver26{Boeing}` となる。

The musician Kenshi Yonezu (米津玄師) conducted a performance featuring a vehicle modeled after a shark.   
Based on publicly available information, which company's products are believed to be used in the drive platform of this vehicle? Answer with the company name in **English**.
For example, if that company is Boeing, the flag should be `Diver26{Boeing}`.


## 解法

`Kenshi Yonezu Shark` などとGoogle検索すると、「IRIS OUT」という楽曲のパフォーマンスでサメ形の乗り物に搭乗したことがわかります。

- [Kenshi Yonezu Rides a Shark in Chainsaw Man “IRIS OUT” Performance as Full Video Is Released, Fireworks Archive Also Unveiled](https://us.oricon-group.com/news/7410/)
- [米津玄師、サメに乗る!『紅白』チェンソーマン「IRIS OUT」パフォーマンス映像解禁 花火のアーカイブも公開](https://www.oricon.co.jp/news/2429847/photo/1/)

上記の記事では、2025年末に開催された「紅白歌合戦」における、サメ形乗り物の高解像度の画像が掲載されています。

また、`kenshi yonezu shark iris out` といった検索ワードで[YouTubeを検索する](https://www.youtube.com/results?search_query=kenshi+yonezu+iris+out+shark)と、2026年に開催された「MUSIC AWARDS JAPAN 2026」におけるパフォーマンスの動画もヒットします。

- https://youtu.be/GZwnre6Skm0?t=129

高画質で確認すると、特徴的な車輪を搭載していることがわかります。
特に「MUSIC AWARDS JAPAN 2026」では、サメ形乗り物がpivot turn（信地旋回）のような挙動をすることが確認できます。  

車輪部分に着目してGoogle Lens による Reverse Image Search を行い、"wheel" といった単語を加えて検索を行うと、「オムニホイール（omni wheel）」ではないかという情報がヒットします。

- [電動車椅子だけではない。WHILLのオムニホイールが配送ロボットにも採用](https://smart-mobility.jp/_ct/17727791)

[オムニホイール](https://en.wikipedia.org/wiki/Omni_wheel)について調べてみると、全方向移動型車輪であり、信地旋回が可能であることがわかります。これはサメ形乗り物の挙動と符合します。

そして、上記の記事には「WHILL」という会社のオムニホイールが登場していました。WHILL社の特許を確認すると、同様の意匠のオムニホイールが存在していることが判明します。

- [Omni-directional wheels](https://patents.google.com/patent/JP6914088B2/en)

これより、WHILL社のオムニホイールが採用されていると判断できます。

Flag: **Diver26{WHILL}**（Diver26{WHILL Inc.} も正解）