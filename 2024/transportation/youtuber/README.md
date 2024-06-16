# youtuber

## 問題文

2023年、あるYouTuberが日本で無賃乗車や無銭飲食を行い、その様子を投稿したことで問題となった。  
彼は日本である列車に無賃乗車をしていたところ、九州地方のある駅で一度捕まったが、そのまま逃走して別の列車に再び無賃乗車をした。  
彼が捕まった駅と、乗り継いだ列車の列車番号を教えてほしい。なお、列車番号は時刻表に掲載されている形式で回答せよ。

Flag形式: `Diver24{駅名_列車番号}`  
例えば、折尾駅で捕まり、456Mという列車に乗り換えた場合、`Diver24{折尾_456M}` となる。

In 2023, a YouTuber became a problem when he posted a video of himself and his mates riding for free and eating for free in Japan.  
He was once caught riding a train in Japan without paying at a station in the Kyushu region, but he escaped and ride another train without paying again.  
I would like to know the station where he was caught and the number of the train to which he changed. Please answer with the train number (列車番号) in the format shown on the timetable (時刻表).

Flag Format: `Diver24{station name_train number}`  
For example, if he was caught at Orio Station and ride 456M train, the flag should be `Diver24{Orio_456M}`.


## 難易度

medium / 211 point (86 solves)

## 解法

<details>

<summary>クリックで表示</summary>

`2023年　無賃乗車　YouTuber` で検索すると、Fidiasという人物であるとわかります。

問題の動画は削除されたものの、複数転載されている（[一例](https://www.youtube.com/watch?v=YzUDKBolwXY)）ほか、日本のメディアが報道で引用している例もあります。

上記の動画では、Fidiasは列車内でトイレに立てこもっていましたが、乗務員に捕まるシーンが記録されています（3分27秒ごろ）。

続いて4分25秒ごろ、「さくら572　新大阪　次は博多」と表示された新幹線を指差し、そのまま乗車しています（この文字列はGoogle Lensで読み取ることができます）。

`さくら572 列車番号` や `さくら572 時刻表` で[検索](https://duckduckgo.com/?t=h_&q=%E3%81%95%E3%81%8F%E3%82%89572+%E5%88%97%E8%BB%8A%E7%95%AA%E5%8F%B7&ia=web)すると、[詳細な時刻表](https://timetable.jr-odekake.net/train-timetable/104121?date=20240217)がヒットし、列車番号が **572A** であるとわかります。

次は、この駅がどこであったかを考えてみましょう。こちらもいくつかの方法があります。

1つは先ほど表示されていた「さくら572　新大阪　次は博多」という文字列から考えることです。「次は博多」と表示されていることから、この駅は「博多」の1つ前である可能性が高いといえます。さくら572号の時刻表を確認すると、博多の1つ前は**新鳥栖駅**であることがわかります。確認のため[Wikipedia](https://ja.wikipedia.org/wiki/%E6%96%B0%E9%B3%A5%E6%A0%96%E9%A7%85)やGoogle Mapsに投稿されている写真を見てみると、投稿されている駅の画像がFidiasの動画に登場した駅と同一のものであるとわかります。

もう1つは、捕まるシーンの列車を確認する方法です。 `885 LIMITED EXPRESS` と書かれています。[検索](https://duckduckgo.com/?t=h_&q=885+LIMITED+EXPRESS&ia=web)すると、これはJR九州の[885系電車](https://ja.wikipedia.org/wiki/JR%E4%B9%9D%E5%B7%9E885%E7%B3%BB%E9%9B%BB%E8%BB%8A)であることがわかります。Wikipediaの記事やJRの公式サイトから、この列車は「きらめき」「リレーかもめ」「みどり」「かささぎ」「ソニック」のいずれかの特急列車で運用されていることがわかります。

先ほどの「さくら572号」の停車駅と、これらの列車の停車駅が重複する地点を確認すると

- 小倉
- 博多
- 新鳥栖

のいずれかに絞り込めます。Google Mapsに投稿された写真などを見比べると、捕まって乗り換えた駅は**新鳥栖駅**であると確認できます。

**Diver24{新鳥栖_572A}**

交通機関が写り込んだ画像や映像は情報の宝庫です。時刻表から撮影時間も推測できますし、車両や座席から路線・地域も絞り込めます。また、交通マニアの方々によって、このような情報はオンライン上にたくさん投稿されているほか、交通機関が公式に公開している情報も豊富にあります。

また、他のOSINT CTFでも時刻表を用いた問題は時折出題されるため、こういった情報の探り方はある程度知っておくと役立つと思われます。

</details>