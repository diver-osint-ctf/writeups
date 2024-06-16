# Office

## 問題文

ファイルから得られるFlagを入力してください。  
Input the flag obtained from the file.

添付ファイル: [mudai.odt](./mudai.odt)

## 難易度

introduction / 100 point (229 solves)

## 解法

<details>

<summary>クリックで表示</summary>


[OpenDocument（ODT）形式](https://support.microsoft.com/ja-jp/office/opendocument-%E3%83%86%E3%82%AD%E3%82%B9%E3%83%88-odt-%E5%BD%A2%E5%BC%8F%E3%81%A8-word-docx-%E5%BD%A2%E5%BC%8F%E3%81%AE%E7%9B%B8%E9%81%95%E7%82%B9-d9d51a92-56d1-4794-8b68-5efb57aebfdc)は文書ファイルの一つです。Wordなどで開くことができます。しかし、ただ開いてもFlagは掲載されていません。

出題意図は、よくわからないファイルに行き当たったときには検索またはテストして何者かを理解してほしい、ということです。仮にテストの方法を知らなくても、検索すれば簡単に対処方法がわかります。  
文書ファイルによくあることですが、ODTファイルも複数のファイルを圧縮して1つのファイルのように見せています。そこで、zipファイルとして解凍すると、Thumbnailsというフォルダに `thumbnail.png` という画像が入っていることがわかります。この画像にFlagが掲載されています。

![](./thumbnail.png)

**Diver24{World Ocean Day}**

これは、ODTファイルを作成した後で内部の文書データ部分のみを編集することで作成できます。

</details>