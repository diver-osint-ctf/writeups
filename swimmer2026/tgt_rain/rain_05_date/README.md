# rain_05_date (100pt / 283 solves)

## 問題文

`rain` は2025年12月25日 (JST)、ある場所に来たことをX上で投稿しています。  
しかし、この画像は2025年の別の日に撮影された写真のようで、事実とは異なるようです。
この写真が本当に撮影された日を `YYYY/MM/DD` の形式で解答してください。  
ただし、撮影日は日本時間（JST）を基準とします。
例えば、答えが2025年6月8日の場合、Flagは `SWIMMER{2025/06/08}` となります。

`rain` posted on X that they visited a certain place on December 25, 2025 (JST).  
However, the image seems to have been taken on a different day in 2025. Please answer the actual date the photo was taken in `YYYY/MM/DD` format.  
Use Japan Standard Time (JST) for the date.  
For example, if the correct date were June 8, 2025 in JST, the flag would be `SWIMMER{2025/06/08}`.


## 解法

該当する投稿はこちらです。

- [さっき関西着いた　週末までこっち居ます（2025年12月25日）](https://x.com/bruto_rain/status/2004085702469075019)

画像を拡大してみると、大阪城ホールの前で撮影されたことがわかります。  
ホールであれば、イベントが開催された記録と突き合わせることで何かわかるかもしれません。

看板やポスターなどを探してみると、画像の中央に「ご招待・報道受付（南事務所口）」と記載されています。  
上にロゴらしきものが記載されていますが、はっきりと読み取れません。

この部分をトリミングしてGoogle Lensに通してみましょう。しかし、解像度が低いこともあって、似たようなロゴがたくさんヒットしてしまいます。

ここで、Google Lensで「大阪城」というワードを追加するとどうでしょうか？

すると、「サントリー1万人の第九」というイベントのロゴがヒットするようになります。確かにこのロゴと類似しているように思われます。

なお、このロゴがうまく見つからない場合でも、 `ご招待・報道受付　南事務所口　大阪城ホール` と検索すると「サントリー1万人の第九」がヒットします。

その[イベントのページ](https://www.suntory.co.jp/culture-sports/daiku/)を見てみると、2025年12月7日に大阪城ホールで実施されたことがわかり、画像の撮影日もこの日であると推定できます。

Flag: **`SWIMMER{2025/12/07}`**
