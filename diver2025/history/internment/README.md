# Internment

## 問題文

著名な木曜島の真珠採りダイバーであった藤井富太郎氏は、第二次世界大戦中、強制収容されました。彼が釈放された収容所と釈放の年月日を明らかにしてください。  
Flag 形式: `Diver25{YYYY-MM-DD_キャンプ番号_キャンプ地名_州名}`

例えば、「2025年6月1日に、キャンプ番号7番のDiver州Daibaキャンプ」から釈放されたならば、 `Diver25{2025-06-01_7_Daiba_Diver}` となります。なお、キャンプ番号がない場合はX（大文字のX）を入れてください。例えば、`Diver25{2025-06-01_X_Daiba_Diver}` となります。

Tomitaro Fujii(藤井富太郎), a prominent Thursday Island pearl diver, was interned during World War II. Please identify the camp from which he was released and the date of his release.  
Flag Format: `Diver25{YYYY-MM-DD_CampNumber_CampPlaceName_State}`

For example, if he was released from the Camp 7 (Daiba Camp) in Diver State, on June 1, 2025, the flag should be `Diver25{2025-06-01_7_Daiba_Diver}`. If the camp doesn't have a number, please use `X` (capital Latin alphabet X). For example, `Diver25{2025-06-01_X_Daiba_Diver}`.


## 難易度

hard / 478 point (48 solves)

## 解法

藤井富太郎氏は非常に著名な人物で、伝記が日本やオーストラリアで刊行されていたり、論文で取り上げられたり、彼をモデルにした小説までもが制作されています。

無償で入手可能な情報としては、「[オーストラリア・木曜島に渡った日本人の足跡を追う](https://fujijoshi.repo.nii.ac.jp/record/412/files/KJ00007823821.pdf)」という紀要論文が存在し、彼の略歴が巻末に記されています。しかし、日本語で無償で入手できる情報の中には、詳細な彼の行動歴は記載されていません。おおざっぱには、和歌山県で生まれ、木曜島に渡って真珠貝を採取する潜水士をしていたようです。戦時中には、1941 年にヘイ収容所に強制収容され、戦後釈放されて木曜島に戻り家族と暮らしたということがわかります。

ここで、オーストラリアにおける日本人の強制収容に関する資料を調査する方法を調べられないか、と考えてみましょう。強制収容をしていたということは、軍や政府にそれなりに情報が蓄積されているはずであり、戦後長らく経過したことで公開されている可能性もあるからです。すると、[オーストラリア国立公文書館（NAA）](https://www.naa.gov.au/students-and-teachers/student-research-portal/wartime-internment-japanese-australians)に、関連して概要を掲載した記事があります。どうやら、この手の情報は NAA がアーカイブしているようです。また、サイト上部には RecordSearch というリンクもあります。

この検索機能を利用して、Keywords として `Fujii Tomitaro` を調査すると、7 件のレコードがヒットします。この中で、Item ID **8610767** の Digitised item を開くと、木曜島で囚われた、Fujii Tomitaro 氏の拘束から釈放までの記録が記されています。下 3 行を読むと、下から 3 行目が釈放日で「10.12.46」とあります。その下の行に **Transferred to 3 (???) Camp Rushworth** 、その下の行には、 **all to ex 4 Camp** とあります。ここで、`4 camp rushworth` などと検索すると、確かに Camp 4 Rushworth が存在したようです（例えば、[CAMP 4 - RUSHWORTH INTERNMENT AND POW CAMP TATURA, VICTORIA](https://www.ozatwar.com/pow/camp4rushworth.htm) など）。また、この収容所は Victoria 州の Tatura にあったこともわかります。

**Diver25{1946-12-10_4_Rushworth_Victoria}** (case insensitive)

余談ですが、日本語版の伝記には明確な釈放日や場所は書いてありません。

なお、Tatura は Rushhworth を含む収容所群を統括する収容所で、釈放命令は Camp3 Tatura の名の下に出ています。
移送記録本体を見ると Release は **Camp 4 Rushworth** とあるので、こちらが想定解です。

Camp 4 Tatura は許容、Camp 3 は命令者のいる収容所なので不適当と考えていましたが、運営側のリソース上の制約により（作問担当者の休憩中に問い合わせがあり、レビュー者が対応することになった）、競技時間中にそれが完全な間違いであると確認できなかったため、Flag に追加しています。

## 出題意図

日本語話者にとっては言語バリアとなる、海外の英文の手書き史料を参照してもらう問題として出題しています。

## 競技中の対応

前述の通り、下記のFlag（case insensitive）を追加しています。

- `Diver25{1946-12-10_4_Tatura_Victoria}`
- `Diver25{1946-12-10_3_Tatura_Victoria}`