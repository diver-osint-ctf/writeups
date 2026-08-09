# sprej (178pt / 203 solves)

## 問題文

映像 / Video : https://www.youtube.com/watch?v=RzIPP5BcsyI&t=73s

この動画の1:13に映る落書きされた物件の、2026年時点での所有者は誰か。  
名字を答えよ。  
名義人が複数存在する場合は、すべての名前をアンダーバー（`_`）で繋ぐこと（順不同）。  
例えば、Morisaki、Tanioki、Yorukawaが名義人の場合、Flagは `Diver26{Morisaki_Tanioki_Yorukawa}` となる。

**writeup規定**: writeupを記載する場合、もし個人の氏名や電話番号、住所などの情報がある場合は伏せてください（店舗に関する情報は問題ありません）。

Who is the owner of the vandalized property shown at 1:13 in this video as of 2026?  
Answer their last name.  
If there are multiple registered owners, connect all names with an underscore (_) in any order.  
For example, if the owners are Morisaki, Tanioki and Yorukawa, the flag should be `Diver26{Morisaki_Tanioki_Yorukawa}`.

**Writeup Rule:** If you publish a writeup, redact any personal information such as names, phone numbers, or addresses (information regarding the store itself is okay).


## 解法
動画はチェコ・プラハ5区の落書きについてのニュースであり、撮影地もプラハ5区であると考えられます。また、石畳が敷かれていることから、おそらく市街の中心部であると想定できます。

当該場面の右上に映るロゴを画像検索すると、銀行チェーンである"Raiffeisen Bank"のロゴであることがわかります。[公式サイト](https://www.rb.cz/en)の支店・ATM一覧を確認すると、ここにうつる看板がプラハ5区中心部の[Raiffeisenbank a.s., Praha 5, Lidická I](https://www.rb.cz/en/about-us/contacts/branches-and-atms/atm-detail?atmId=102)のものであることがわかります。

次に、[チェコの登記閲覧サイト](https://nahlizenidokn.cuzk.gov.cz/VyberParcelu/Parcela/InformaceO)を確認し、当該の物件の所有者情報を確認すると、情報を得ることができます。

（個人の氏名につきFlagを掲載していません）