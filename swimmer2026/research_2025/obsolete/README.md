# obsolete (100pt / 349 solves)

## 問題文

2025年11月、「台湾有事」を巡って日中関係が悪化しました。  
その中で、在日本中国大使館のSNSアカウントは国連憲章の「敵国条項」について言及する投稿を行いました。  
これに対し、日本の外務省は「その条項は **1995年の国連決議** によって死文化（obsolete）している」と反論したことが報じられています。  

さて、この決議において、投票を **棄権** した国がいくつかあります。それはどこの国か、解答してください。  
決議に関する公式記録に記載されている国名をアンダーバー (`_`) で区切ったもの（順不同）をFlagとします。

たとえば、UNITED STATES（アメリカ合衆国）とRUSSIAN FEDERATION（ロシア連邦）と記載されていた場合、Flagは `SWIMMER{UNITED STATES_RUSSIAN FEDERATION}` となります。

In November 2025, relations between Japan and China worsened over a potential contingency in Taiwan (referred as "台湾有事").  
During this argument, the Chinese Embassy in Japan posted on social media about the "Enemy Clauses (敵国条項)" of the UN Charter.  
Japan's Ministry of Foreign Affairs reportedly countered that the clause had become obsolete due to a **1995 UN resolution**.  

In that resolution, several countries **abstained** from the vote. Answer which countries they were.  
Use the country names as written in the official record of the resolution, separated by underscores `_` (any order), for the flag.

For example, if the record listed UNITED STATES and RUSSIAN FEDERATION, the flag would be `SWIMMER{UNITED STATES_RUSSIAN FEDERATION}`.


## 解法

たとえば `敵国条項 死文化` と検索すると、以下のような報道がヒットし、問題文で述べられていることの事実確認ができます。

- [外務省、中国の旧敵国条項発信に反論　「既に死文化」](https://www.nikkei.com/article/DGXZQOUA231KL0T21C25A1000000/)

続いて、この決議自体が何だったかについて調べてみましょう。きちんとした公式の原典にたどり着けるのであれば、WikipediaやAIを活用しても結構です。いずれにせよ `敵国条項 決議` などと検索すると、 **国際連合総会決議50/52** がこの決議を指していることがわかります。決議番号は外務省のWebサイトなどにも記載されていることから、信頼性が高い情報だと考えられます。

- [国連改革：日本の優先事項](https://www.mofa.go.jp/mofaj/gaiko/un_kaikaku/j_yusen.html)

Wikisourceに日本語訳が掲載されています。しかし、原典は英語など国連公用語で記載されているようです。

- [国際連合総会決議50/52](https://ja.wikisource.org/wiki/%E5%9B%BD%E9%9A%9B%E9%80%A3%E5%90%88%E7%B7%8F%E4%BC%9A%E6%B1%BA%E8%AD%B050/52)

Wikisourceの上に記載されているリンクから、[国連の公式情報](https://docs.un.org/en/A/RES/50/52)に飛ぶと、資料の右側に **A/RES/50/52** と記載されています。これが決議番号の英語表記のようです。

資料が英語なら、英語で検索したほうがよいかもしれません。  
Google翻訳などで `投票結果` を英語に翻訳すると `voting results` であるとわかります。 

`A/RES/50/52 voting results` で検索すると、国連デジタルライブラリー（United Nation Digital Library）の資料がヒットします。

- https://digitallibrary.un.org/record/192213

ページ上の方の Result 1 of 2 と書かれているところから、次のページ（Next）に進むと、投票結果の一覧が表示されます。

Vote summaryという欄には Yes（賛成）は155カ国、No（反対）が0カ国、Abstentions（棄権）が3カ国、投票なしが27カ国あります。  
国のリストを見ると、**Y** が Yes の略で、**A** が Abstentionsの略であると判断できます。

Aがついているのは以下の3カ国です。

- CUBA
- DEMOCRATIC PEOPLE'S REPUBLIC OF KOREA
- LIBYAN ARAB JAMAHIRIYA

**Flag**: `SWIMMER{CUBA_DEMOCRATIC PEOPLE'S REPUBLIC OF KOREA_LIBYAN ARAB JAMAHIRIYA}`

なお、[国連のプレスリリース](https://press.un.org/en/1995/19951211.ga9031.html)には "Libya" とだけ記載されていますが、この文書が "For information media. Not an official record." と記載されていることを鑑みて、公式記録のみを答えとしています。

## 競技中の対応について

文字コードの異なるアポストロフィ（`'`）もFlagとして追加し、すでに送信された解答についても遡及して正解扱いにする対応を行っています。ご迷惑をおかけして申し訳ありませんでした。