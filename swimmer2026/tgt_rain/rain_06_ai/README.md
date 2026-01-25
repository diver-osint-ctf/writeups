# rain_06_ai (100pt / 248 solves)

## 問題文

`rain` のブログには、東京駅の画像があります。しかし、これは実際に撮影したものではなく、AIで作成された画像のようです。  
この画像が何というツールで作成されたのか特定し、解答してください。  
例えば、答えが `Adobe Firefly` の場合、Flagは `SWIMMER{Adobe Firefly}` となります。

There is an image of Tokyo Station on `rain`'s blog, but it appears to be AI-generated rather than an actual photo.  
Answer which tool was used to create it.  
For example, if the answer is `Adobe Firefly`, the flag would be `SWIMMER{Adobe Firefly}`.


## 解法

rainのブログにある「日常を記録する」という記事を見てみると、「新しいカメラを使って撮影した画像」が掲載されています。

PC上のブラウザで画像を右クリックして新しいタブで開くと、以下のような画像にジャンプします。

```
https://brutorain.wordpress.com/wp-content/uploads/2026/01/tokyo_0003.jpeg?w=1024
```

この画像（WebP形式）をダウンロードしてみても、特に記録は残っていません。

しかし、以下のようにURLの末尾にあるパラメータを削ってみるとどうでしょうか？

```
https://brutorain.wordpress.com/wp-content/uploads/2026/01/tokyo_0003.jpeg
```

すると、JPEG形式でデータをダウンロードできます。  
JPEG形式の画像には、Exifとよばれる情報を記録できます。これは様々なツールで確認できますが、もっとも簡易的なものとしてWindowsでファイルを右クリックしたときに表示される「プロパティ」があります。

実際に確認してみると、「コメント」の欄に以下の情報が残っています。

```json
{"aigc_info":{"aigc_label_type":0,"source_info":"dreamina"},"data":{"os":"web","product":"dreamina","exportType":"generation","pictureId":"0"},"trace_info":{"originItemId":"7590949739743448328"}}
```

`source_info` として `dreamina` と書かれているので、これを検索してみましょう。すると、以下のサイトがヒットし、そのような名前のAI画像生成サイトがあることが確認できます。

- https://dreamina.capcut.com/ja-jp/

Flag: **`SWIMMER{Dreamina}`** (`SWIMMER{Dreamina Web}` なども正解)