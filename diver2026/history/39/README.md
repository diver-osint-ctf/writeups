# 39 (296pt / 162 solves)

## 問題文

1970年の冬、36.535, 139.186 付近で自動車の競技会が行われました。  
この競技会で、39番のゼッケンを付けていた車両は、ある市販車を利用してレースに参戦したと考えられる。  
その市販車の車種名を答えよ（メーカー名を除く）。  
例えば、マツダ社の「ロードスターRF」が答えであれば、Flagは `Diver26{ロードスターRF}` となる。

In the winter of 1970, an automobile competition was held near 36.535, 139.186.  
In this competition, the vehicle bearing race number 39 is believed to have entered the race using a certain commercially available car.  
Answer with the model name of that commercially available car, excluding the manufacturer name.  
For example, if the answer is Mazda’s “Roadster RF,” the flag should be `Diver26{Roadster RF}`.


## 解法

Google Mapsで座標を検索すると、「小沼（この）」という湖であることがわかります。

`小沼 自動車 競技` などとGoogleで検索すると「[赤城氷上トライアル](https://www.n-mosco.com/jac/hyozyo/hyozyo.html)」と呼ばれる競技会が開催されていたことがわかります。

しかし、1970年のような古い年代のイベントでは、記録がオンラインに掲載されていないことも多々あります。また、この競技会は公的機関が実施していたものではないため、公文書のようなデータベースを遡るのも望み薄でしょう。  

そこで、別の切り口を試してみましょう。  
昨今は一部のメディアが古い記録映像をオンラインに公開していることがあります。  
`1970 小沼 自動車` などとYouTubeで検索してみると、テレビ東京が運営している「Japan’s Nostalgic Films」というチャンネルに投稿されている以下の動画がヒットします。

- [【昭和の日本】凍った湖で日本初の氷上カーレース開催！群馬県赤城山の山頂に集った58人がスピードを競う | 1970年](https://www.youtube.com/watch?v=3uFqEu3dvzA)

映像をよく見ると、0:40ごろに登場するオープンカーに「39」というゼッケン番号が描かれています。

0:40ごろの車両をスクリーンショットしてGoogle Lensに通すと、その特徴的なボディ形状から、[ダイハツ・フェローバギィ](https://ja.wikipedia.org/wiki/%E3%83%80%E3%82%A4%E3%83%8F%E3%83%84%E3%83%BB%E3%83%95%E3%82%A7%E3%83%AD%E3%83%BC%E3%83%90%E3%82%AE%E3%82%A3)であると考えられます。

Flag: **Diver26{フェローバギィ}** （Diver26{フェロー・バギィ}、Diver26{Fellow Buggy} なども正解）