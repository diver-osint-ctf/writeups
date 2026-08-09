# kaitai2 (390pt / 119 solves)

## 問題文

kaitai1 の土地は、ある建物が解体され、更地になっているようだ。この解体はある計画に起因すると推定される。  
その計画が完了した時、この場所に建設される物は何だろうか。  
その事物を示す Wikidata IDを答えよ。例えば、`Q57965` が答えの場合、Flagは `Diver26{Q57965}` となる。

- 可能な限り具体的な事物を示せ。例えば、「東京スカイツリー」が答えであるとき、「建物」「塔」「電波塔」などは答えとして認められない。
- 競技開始後に作成されたIDは解答にならない。

The site of "kaitai1" appears to have been cleared following the demolition of a building. This demolition is presumed to be part of a specific project.   
What will be constructed on this site once the project is complete?   
Answer the Wikidata ID for that entity. For example, if the answer were `Q57965`, the flag should be `Diver26{Q57965}`.  

- Provide specific items whenever possible. For example, if the answer is `Tokyo Skytree`, terms such as `building`, `tower`, or `broadcast tower` will not be accepted as correct answers.  
- Wikidata IDs created after this competition has started will not be accepted as valid answers.


## 解法

下北沢駅近辺をGoogle Earthで確認すると、工事によって解体されている区画が目立ちます。

`下北沢 工事` と Google 検索すると、行政の資料や個人のブログがヒットします。

- https://www.city.setagaya.lg.jp/documents/4006/shiryou-3.pdf
- https://urban-development.jp/road/shimokitazawa-202512/

「補助第54号線」といった言葉が確認できるため、これでGoogle検索すると、以下のような世田谷区のWebサイトがヒットします。

https://www.city.setagaya.lg.jp/01205/4565.html

添付されている資料を見ると、この付近（北沢2-32）を通過する「幹線街路補助線街路第54号線」が建設される予定であるとわかります。

https://www.city.setagaya.lg.jp/documents/4565/news7.pdf


[幹線街路補助線街路第54号線のWikipedia記事](https://ja.wikipedia.org/wiki/%E6%9D%B1%E4%BA%AC%E9%83%BD%E5%B8%82%E8%A8%88%E7%94%BB%E9%81%93%E8%B7%AF%E5%B9%B9%E7%B7%9A%E8%A1%97%E8%B7%AF%E8%A3%9C%E5%8A%A9%E7%B7%9A%E8%A1%97%E8%B7%AF%E7%AC%AC54%E5%8F%B7%E7%B7%9A)から[Wikidata項目](https://www.wikidata.org/wiki/Q11525315)にアクセスすると、`Q11525315` というIDが割り振られていることがわかります。

Flag: **Diver26{Q11525315}**
