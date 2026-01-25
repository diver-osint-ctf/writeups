# paint (100pt / 282 solves)

## 問題文

添付画像に写っている航空機は、ある映画にちなんだ特別塗装機です。  
この特別塗装機は、2017年3月21日に就航開始しましたが、2025年に引退が発表され、去る2026年1月9日、この塗装での最後の運航を終了しました。

さて、2017年にこの特別塗装が行われた建物はどこでしょうか。座標を地図上で示してください。

The aircraft in the attached image features a special livery themed after a movie.  
This livery entered service on March 21, 2017, and its retirement was announced in 2025.  
The final flight with this livery took place on January 9, 2026 (JST).

Where was this special livery applied back in 2017? Please answer the building's coordinates on a map.


## 配布ファイル

- [paint.jpg](./public/paint.jpg)

## 解法

Google Lensなどで検索してみると、この機体の番号（機体記号）は **JA743A** であり、ANAの「[C-3PO ANA JET (B777-200ER)](https://flyteam.jp/registration/JA743A/livery/101)」であることがわかります。

就航した日を調べると、何か記事が出てくるかもしれません。  
`C-3PO ANA JET　2017年3月21日` で検索してみましょう。すると、以下の記事がヒットするはずです。

- [ANA、スター・ウォーズ特別塗装機第4弾「C-3PO ANA JET」を公開 - トラベルWatch](https://travel.watch.impress.co.jp/docs/news/1050316.html)

記事には以下のように書かれています。

> 伊丹空港に隣接するMRO Japanで塗装作業が進められた同機は、3月19日にドックアウト。その姿を披露した。

また、以下のYouTube動画も埋め込まれています。

- https://www.youtube.com/watch?v=Ko0SRkR00F0

なお、[MRO Japanは伊丹空港から那覇空港に2019年に移転しました](https://travel.watch.impress.co.jp/docs/news/1172249.html)が、問題文は2017年の事を聞いているので、「伊丹空港に隣接する」という条件で探すといいでしょう。


さて、記事に埋め込まれたYouTube動画を見てみましょう。いくつか分かることがありそうです。

- 「C-3PO ANA JET」は、青い屋根の大きな建物から出現しました。ここで塗装が行われた可能性が高そうです。
- 青い屋根の大きな建物は、飛行機が出入りするサイズの大きなドアがあります。
- 右側に青と白の特徴的な建物が見えます。衛星画像からでも分かるかもしれません。
- 画面の左側に飛行機が並んでいることがわかります。ここにターミナルがあるのかもしれません。
- 左下には地面にマークが描かれていることがわかります。丸の中に「H」と見えるので、ヘリポートのマークかもしれません。

これらの情報を整理して、伊丹空港付近を Google Maps で見てみましょう。  
すると、ターミナルの南東部分に条件を満たす建物があることがわかります。

3D表示してみると、一致すると言えそうです。

これより、この建物の位置が正解となります。

Flag: **`34.78500453255155, 135.4454791050576`**  （許容誤差: 160m）

（なお、上記の座標は正誤判定に用いるための設定値であり、このオーダーでの解答を要求しているものではありません。許容誤差円内に収まっていれば問題ありません。）