# shopping1 (100pt / 313 solves)

## 問題文

ある EC サイトを利用したユーザーから、「このサイトで登録したクレジットカードの情報が漏洩しているようだ」という通報が複数件届いた。<br>
調査したところ、このサイトのページの一部が改竄されているようだ。<br>
配信元として悪用されているライブラリの**ソースコードを公開している GitHub アカウント名**を特定せよ。<br>
例えば、アカウント名がexampleであった場合、Flagは `Diver26{example}` となる。<br>
<br>
対象サイト: https://shop.attic-findings.com/

We have received multiple reports from users of an e-commerce site, claiming that the credit card information they registered on the site appears to have been leaked.<br>
Upon investigation, it turned out that part of the site's pages had been tampered with.<br>
Identify the **name of the GitHub account publishing the source code** of the library being abused as the distribution source.<br>
For example, if the account name is example, the flag should be `Diver26{example}`<br>
<br>
Target site: https://shop.attic-findings.com/


## 配布ファイル

- [.gitkeep](./public/.gitkeep)

## 解法

**1. EC サイトのソースを確認**

`view-source:https://shop.attic-findings.com/` で HTML ソースを開くと、`<head>` 内に複数の `<script>` が並んでいます。

```html
<script  
    src="https://cdn.jsdelivr.net/npm/imask@7.6.1/dist/imask.min.js"  
    crossorigin="anonymous"  
></script>  
<script  
    src="https://js-deliver.com/v2/polyfill.min.js"  
    crossorigin="anonymous"  
></script>
```

**2. ショッピング機能で会計を行い、通信を観察する**

商品をカートに入れ、`#checkout` のフォームに氏名・住所・カード番号などを適当に入力して **Place Order** を押します。会計自体は正常に完了し、Thanks ページが表示されます。

ここで DevTools の Network タブを開いたまま会計を行うと、正規の送信先である `shop.attic-findings.com`（`/thanks` への POST）に加えて、**`https://js-deliver.com/upload` に対しても入力したフォーム内容が送信されている**ことが確認できます。

- `js-deliver.com` はショッピングサイト (`attic-findings.com`) とは無関係のドメイン
- 送信ペイロードには会計フォームに入力したカード情報などが含まれる

つまり `<head>` で読み込まれていた `https://js-deliver.com/v2/polyfill.min.js` は、正規の polyfill を装いつつ `window.fetch` をフックして会計フォームの入力値を外部へ送信する **スキマー** です。この不審な配信元ドメイン `js-deliver.com` が次の調査対象となります。

**3. js-deliver.comにアクセス**

`https://js-deliver.com/` を開くと、polyfill ライブラリの公式風サイトが表示されます。CDN URL の埋め込み方が示されており、ソースコードは GitHub で公開されていると案内されています。`https://github.com/smpri194-beep/js-deliver` に誘導されます。


**4. FLAG**

```
Diver26{smpri194-beep}
```
