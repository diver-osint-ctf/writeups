# rch (500pt / 124 solves)

## 問題文

**この問題に限り、7月26日（日曜日） AM 8:00 (JST) で解答を締め切ります。それ以降の送信は採点されません。**

OSINTリサーチャーであるあなた宛に、メッセージが送られてきたようだ。

> これは米軍機が北朝鮮か中国に荷物を運んでいる秘密のフライトの証拠だ！彼らは対立しているかのように見せかけ、実際には裏で繋がっているんだ！

この主張は正しくない。実際には何のために何を運んでいると推定されるか。

採点基準:  
* 「何のため」（目的）および「何を運んでいるか」（貨物）を **1文で簡潔に** 明記せよ。貨物の名称は原則として正式名称を用いること。
* もっとも主要な貨物を答えよ。例えば、貨物の輸送に際して、書類が同時に運ばれているとしても、「紙」「書類」などと答えたものは得点にならない。
* 解答は英語または日本語で行うこと
* この問題に関しては"Diver26{}"のフォーマットは不要である

**なお、この問題の提出可能な回数は、1 回のみとなります。**  
もし誤送信をした場合、この問題については手動で取り消し対応を行います（1度のみ）。その場合は #ask-for-admin から問い合わせてください。

---

**Only for this challenge, the deadline for submitting answers is 23:00 (UTC) on Saturday, July 25. Submissions received after this time will not be graded.**

It appears a message has been sent to you, an OSINT researcher.

> This is proof of a secret flight where a U.S. military aircraft is transporting cargo to North Korea or China! They pretend to be adversaries, but in reality, they are colluding behind the scenes! 

This claim is incorrect. What is actually presumed to be the purpose of the transport, and what is being carried?

Grading Criteria:
* Clearly state the purpose ("what it is for") and the cargo ("what is being transported") **in one concise sentence** . As a general rule, use the cargo's official name.
* State the primary cargo. For example, if documents are being transported alongside the cargo, answers such as "paper" or "documents" will not receive points.
* Answers must be provided in English or Japanese.
* For this challenge, the flag format "Diver26{}" is not necessary.

**Please note that you can only submit this challenge once.**
If you submit an answer by mistake, we can manually cancel the submission **once only for this challenge**. Please contact us through #ask-for-admin.


## 配布ファイル

- [rch.png](./public/rch.png)

## 解法

短文記述問題です。

ログの日付に着目し、`2026 May China US` などと検索します。  
すると、[米中首脳会談](https://en.wikipedia.org/wiki/2026_state_visit_by_Donald_Trump_to_China)が実施され、アメリカのドナルド・トランプ大統領が北京を訪問し、中国の習近平国家首席と北京で会談した時期であることがわかります。

米国大統領の海外訪問に関して調べると、[大統領専用車](https://en.wikipedia.org/wiki/United_States_presidential_state_car)が輸送機（C-17）を利用して訪問先に持ち込まれることがわかります。

- [Presidential state car (United States)](https://en.wikipedia.org/wiki/Presidential_state_car_(United_States))
- [Secret Service releases photos on Twitter of US presidential cars carried on plane](https://mainichi.jp/english/articles/20171106/p2a/00m/0na/019000c)

実際、今回も現地報道においてC-17輸送機および大統領専用車がトランプ大統領に先立って現地入りしていることが報じられています。また、South China Morning Postでは機体の番号（08-8204および05-5140）が報じられており、Flightradar24のスクリーンショットと一致します。

- [Are US Air Force C-17s flying cars into Beijing for Trump’s China trip? - South China Morning Post](https://www.scmp.com/news/china/diplomacy/article/3352263/are-us-air-force-c-17s-flying-cars-beijing-trumps-china-trip)
- [Has ‘the Beast’ arrived in Beijing? Trump’s motorcade SUVs spotted before visit - South China Morning Post](https://www.scmp.com/news/china/diplomacy/article/3352682/has-beast-arrived-beijing-trumps-motorcade-suvs-spotted-visit)
- [米軍の大型輸送機が北京に着陸、トランプ大統領の訪中準備か…香港紙 - 読売新聞](https://www.yomiuri.co.jp/world/20260503-GYT1T00170/)

これより、**米中首脳会談に伴って、アメリカ大統領専用車が輸送された**（The U.S. presidential state car was transported in connection with the U.S.-China summit.）といったものが答えとなります。

なお、本問ではすべての解答はLLMによって一度評価され、その内容の妥当性を作問者が採点する構造をとっています。これはLLMによるハルシネーションや、不正プロンプトによる採点誤りを防ぐとともに、今後に向けたCTFにおけるLLMの有用性を検証するための取り組みです。