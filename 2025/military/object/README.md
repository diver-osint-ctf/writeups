# object

## 問題文

69.216246, 33.378242 には大きな構造物が存在する。この構造物のプロジェクト番号および、構造物の名称（固有名詞）を **現地語** で答えよ。  
Flag形式: `Diver25{プロジェクト番号_名称}`（例: `Diver25{955А_Борей-А}`）

There is a large object at 69.216246, 33.378242. Answer the project number and particular name of that object in **local language**.
Flag Format: `Diver25{PROJECT NUMBER_NAME}` (e.g. `Diver25{955А_Борей-А}`)


## ヒント

1. プロジェクト番号は工場の番号ではない。 / Project number does NOT mean the number of a factory.

## 難易度

medium / 359 point (120 solves)

## 解法

69.216246, 33.378242 を Google Maps で表示すると、近傍に Olenya Guba Naval Base というロシアの海軍基地が存在することが分かります。構造物の近くには桟橋が存在しており、なおかつ柵やゲートが存在していることから、この構造物が海軍基地内に存在しているものではないかと推測できます。

この基地の名称で Google 検索すると、以下のような記事がヒットします。

- [Is this the top secret base that Russian 'spy' beluga came from? Satellite photos reveal Russians built a new whale pen at Arctic base around time the beluga 'defected' to Norway](https://www.dailymail.co.uk/news/article-7075547/Is-secret-base-Russian-spy-beluga-came-Photos-reveal-Russians-built-new-whale-pen.html)
- [Spy sub base must get facelift, says Murmansk governor](https://www.thebarentsobserver.com/security/spy-sub-base-must-get-facelift-says-murmansk-governor/161069)
- [Russia_Navy_Beluga_Whale_update](http://www.hisutton.com/Russia_Navy_Beluga_Whale_update.html)

様々な記事によって、この基地には「潜水艦用の（浮き）ドック」があり、当該の構造物がそれであると指摘されています。

情報を精査するため、Google 翻訳などで「潜水艦用ドック」と翻訳し、地名を加えて Google や Yandex で検索してみましょう。

`док для подводных лодок Оленья Губа` (submarine dock Olenya Guba)

すると、以下のような記事がヒットします。

- [пр.13560 / ПД-72 | MilitaryRussia.Ru — отечественная военная техника (после 1945г.)](http://militaryrussia.ru/blog/archive/military.tomsk.ru/blog/category/76/topic/topic/topic/topic-822.html)
- [пр.19100 / ПД-78 | MilitaryRussia.Ru — отечественная военная техника (после 1945г.)](http://militaryrussia.ru/blog/category/133/topic/224/topic/224/topic/topic-823.html)

これらの情報より、Olenya Guba Naval Base には ПД-78 と ПД-72 という浮きドックが存在していることがわかります。  
`ПД-72` や `ПД-78` で検索すると、小さいもの（衛星画像で左に映っているもの）が **ПД-78** で、大きいもの（当該の構造物）が **ПД-72** であることがわかります。

また、Google や Yandex で ПД-72 について検索すると、プロジェクト番号についてもいくつかの情報源（[fleetphoto.ru](https://fleetphoto.ru/vessel/83897/), [RussianShips.info](https://russianships.info/vspomog/13560.htm)）から確認が可能です。

これより、以下が Flag となります。

**Diver25{13560_ПД-72}**

なお、英語で検索しても [ПД-72](https://wikimapia.org/916185/Guba-Olenya-Naval-Base-Deer-Bay) に言及したページは存在しているため、本問の解き方は複数存在すると考えられます。

## 出題意図

衛星画像をそのまま Google Lens などの画像検索に入れて情報が得られることはまれであるため、対象の正体や動向を分析するためには、文献の調査が必要となります。  
写っている物体を識別するための名称を、周辺の地名や報道などの情報を元に特定する作業はその足がかりとなる営みであり、競技参加者にそのノウハウを得てもらうための問題として出題しました。

なお、本問の出題に際して、[DEEP DIVE](https://deepdive.or.jp/)の[小泉先生](https://x.com/OKB1917)にご助言をいただきました。ただし、出題に際する責任はすべてDIVER OSINT CTFにあります。