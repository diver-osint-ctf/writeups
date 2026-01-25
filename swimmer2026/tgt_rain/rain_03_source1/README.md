# rain_03_source1 (256pt / 177 solves)

## 問題文

`rain` は、目を引くタイトルの記事を書くことで閲覧数が多くなると考えたようです。  
この人物はこれをきっかけとして偽情報の作成・流布にのめり込んでしまったと考えられます。

この人物が一番最初に投稿した偽記事では、ある画像に全く関係ないキャプションが付けられています。
本来の出典を探し、この画像がどこの市区町村にまつわる資料に掲載されたものか解答してください。  
都道府県名を含む必要はありません。  

例えば、`平塚市` の資料に掲載されていた場合、Flagは `SWIMMER{平塚市}` となります。

`rain` believed that writing clickbait article titles would boost views.  
They then became engrossed in creating and spreading disinformation.  
In their very first fake article, an unrelated caption was attached to an image. Find the original source and answer which municipality's materials this image appeared in.  
You do not need to include the prefecture name.  

For example, if the picture were on the document about `平塚市` (Hiratsuka City), the flag would be `SWIMMER{平塚市}`.


## 解法

rainのブログで「気付いてしまった！！」という記事に投稿された画像には、写真だけではなく文字列も含まれています。

古い写真らしく、"工事中ノ濾過池（其一）" が `池過濾ノ中事工` と左右逆に書かれています。  
（参考：右横書きについて: [日本語の文字組みについて（印刷博物館）](https://www.printing-museum.org/etc/pnews/08602.php)）

しかし、この文字列だけを検索してもヒットしません。日本の古い写真であると仮定すると、どこの情報を検索するとよいでしょうか。

日本国内で発行されたすべての出版物は、国立国会図書館法に基づき、国立国会図書館への納入が義務付けられています。そして、国立国会図書館には「[デジタルコレクション](https://dl.ndl.go.jp/)」があります。

デジタルコレクションで `池過濾ノ中事工` と検索してみましょう。すると、3つの書籍がヒットするはずです。
そのうち、昭和5年に発行された「[豊橋市水道誌](https://dl.ndl.go.jp/pid/1225183)」の該当箇所（28コマ目）を見ると、ブログと一致する画像が存在するとわかります。

Flag: **`SWIMMER{豊橋市}`**