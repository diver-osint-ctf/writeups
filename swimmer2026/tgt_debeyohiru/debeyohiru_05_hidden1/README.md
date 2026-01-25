# debeyohiru_05_hidden1 (100pt / 276 solves)

## 問題文

`debeyohiru` の本名が知りたいです。  
この人物の実名と考えられるものを解答してください。
ローマ字（アルファベット）表記で入力してください。漢字の表記を考慮する必要はありません。

例えば、`Sanae Takaichi`が実名の場合、Flagは `SWIMMER{Sanae Takaichi}` となります。

We want to know `debeyohiru`'s real name.  
Answer the name you believe is their legal name.

For example, if their real name were `Sanae Takaichi`, the flag would be `SWIMMER{Sanae Takaichi}`.  
Please answer in Latin alphabet; you do not need to consider Kanji or Hiragana.


## 解法

[furaigo5 のWebサイト](https://furaigo5.github.io/profile/)を見てみても、特に氏名は記載されていません。しかし、Webサイトのソースに何か残っていないでしょうか？

PC版のブラウザでWebサイトを開き、[開発者ツールを開いてみましょう](https://developer.chrome.com/docs/devtools/open?hl=ja)。WindowsであればF12キー、MacであればFn + F12を押すと開きます。

中には `script.js` というファイルが呼び出されているようです。ここを見てみると、冒頭に以下のようなコメントがあり、[JSDoc](https://ja.wikipedia.org/wiki/JSDoc)形式でスクリプトの説明が書かれています。この `@author` は作者を表すもので、「furaigo5 Workspace」のために書かれていることを考えると、この人物がfuraigo5だと推定できます。

```js
/**
 * @fileoverview furaigo5 Workspace - メインスクリプト
 * ナビゲーションのスムーズスクロールとモバイルメニューの制御を担当
 * @author Gotanno Tsubasa
 */
```

Flag: **`SWIMMER{Gotanno Tsubasa}`** （Tsubasa Gotanno表記なども可）