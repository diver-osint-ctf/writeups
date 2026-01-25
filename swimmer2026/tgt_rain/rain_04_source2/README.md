# rain_04_source2 (100pt / 414 solves)

## 問題文

`rain` が2番目に作成した偽記事には、「rainが未公開の情報を見つけた」ということが書かれているようです。しかし、これは虚偽だと思われます。  
この人物の嘘を暴くには、正確な出典を探す必要があります。  

この画像の出典となる古い書籍は電子化されており、詳細が参照できるはずです。  
その資料のデジタルオブジェクト識別子（DOI）を解答してください。  
例えば、答えが `12.34567/890123` の場合、Flagは `SWIMMER{12.34567/890123}` となります。

In `rain`'s second fake article, it claims they found unpublished information, but this is likely false.  
To debunk it, you need to find the original source.  
The image comes from an old book that has been digitized, so you should be able to view the details.  
Please answer the digital object identifier (DOI) of that source.  
For example, if the answer were `12.34567/890123`, the flag would be `SWIMMER{12.34567/890123}`.


## 解法

rainのブログにある「誰も知らない真実を発見」という記事をチェックしてみましょう。  
この画像をGoogle Lensに通すと、日本の国会議事堂のものであることがわかります。

[国会図書館のサイト](https://www.ndl.go.jp/kaleido/entry/28/2.html)や[Wikimedia Commons](https://commons.wikimedia.org/wiki/File:National_Diet_Building_Competition_Submission_Watanabe_Fukuzo.jpg)で画像が引用されており、いずれも大正9年発行の「[議院建築意匠設計競技図集](https://dl.ndl.go.jp/pid/967480/1/7)」という書籍に掲載されていたものだと確認できます。

識別子（DOI）はそのページに記載されている通りです。

Flag: **`SWIMMER{10.11501/967480}`**