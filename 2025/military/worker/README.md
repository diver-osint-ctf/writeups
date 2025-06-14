# worker

## 問題文

"object" の問題で示された構造物で仕事をしていた1964年生まれのある人物は、Akhtubinskに居住しているとされる。  
この人物が1987年～2009年にかけて勤務していた組織のOGRNを答えよ。  
Flag形式: `Diver25{1234567890123}`

A person born in 1964 who worked at the object indicated in the "object" challenge is said to reside in Akhtubinsk.  
Answer the OGRN of the organisation where this person worked between 1987 and 2009.  
Flag format: `Diver25{1234567890123}`


## 難易度

easy / 499 point (12 solves)

## 解法

まず、Akhtubinsk とはどこでしょうか。検索してみると[ロシアの都市](https://en.wikipedia.org/wiki/Akhtubinsk)がヒットし、現地語表記は **Ахтубинск** であるとわかります。また、OGRN についても検索してみると、[ロシアの法人登録番号（ОГРН）](https://docs.trellix.com/ja-JP/bundle/data-loss-prevention-11.10.x-classification-definitions-reference-guide/page/GUID-945B4343-861E-4A57-8E60-8B6028871BA1.html)を意味することが分かります。

`Оленья губа ПД-72` や `ПД-72 Ахтубинск` などといった地名と関連するワードを含めて Yandex で検索すると、以下のようなサイトがヒットします。

https://v2.namebook.club/military/rossiya/13090-olenya-guba-pd-72/

どうやら退役軍人が繋がるための同窓会的なサイトのようです。

さて、このページで最初に記載されている人物（Игорь 氏）は 1964 年生まれで Akhtubinsk に在住していることが分かります。  
彼のページの勤務歴には、1987 年～ 2009 年にかけて "26273" という場所に軍人として勤務していたことが示されています。  
軍人の勤務歴が記されていることから。これは軍隊における部隊の番号（Войсковая часть、В/Ч）を示していると考えられます。

そこで、"Russian Army 26273" をロシア語に翻訳した "Армия России 26273" などで検索すると、法人情報がヒットします。

https://www.rusprofile.ru/id/9757601

ОГРН（OGRN）の欄には **1023000507936** と記載されており、これが Flag となります。

**Diver25{1023000507936}**

## 出題意図

ロシアに限らず、現役軍人・退役軍人が、ソーシャルメディアにその所属を公開しているケースは多々あります。
これらの情報を分析することにより、部隊の異動の傾向を掴むことが可能になったり、（今回はその意図はありませんが）HUMINTの足がかりになったりといった可能性が考えられます。  
軍隊の情報というと兵器などに目が向きがちですが、どのような組織であろうと人間の存在は不可欠であり、そこに何らかの情報が潜んでいる可能性は十二分にあります。この問題はそういった視点を持ってもらう意図で作成されています。

なお、本問の出題に際して、[DEEP DIVE](https://deepdive.or.jp/)の[小泉先生](https://x.com/OKB1917)にご助言をいただきました。ただし、出題に際する責任はすべてDIVER OSINT CTFにあります。