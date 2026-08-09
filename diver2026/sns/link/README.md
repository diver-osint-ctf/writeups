# link (493pt / 32 solves)

## 問題文

以下のURLが示す人物が、2023年9月17日に訪れた場所およびその場所で割り当てられた座席番号を調査せよ。<br>
https://www.linkedin.com/in/tongtong-peng-35288b366/

場所の名称は、 **現地語** で記載せよ。<br>
座席番号は、要素となる全ての文字列をハイフンでつないで示せ。<br>
例えば、場所が「日本武道館」、座席番号が「1階 南ブロック A列 7番」だった場合、<br>
Flagは `Diver26{日本武道館_1-南-A-7}`となる。<br>

**注意**: 特定の人物および団体に直接連絡を取ることは禁止されています。<br>
Flagは公開されている情報のみから取得可能です。<br>
**writeup規定**: writeupを記載する場合、人物の氏名やLinkedInのURLは必ず伏せるようにしてください（テキスト・画像の両方）。

Investigate the location visited on September 17, 2023, by the person identified by the following URL, along with the seat number assigned to them at that location.<br>
https://www.linkedin.com/in/tongtong-peng-35288b366/

Write the location name in **the local language**.<br>
For the seat number, join all of its component strings with hyphens.<br>
For example, if the location is "Nippon Budokan (日本武道館)" and the seat number is "1st Floor, South (南) Block, Row A, Seat 7,"<br>
the flag should be `Diver26{日本武道館_1-南-A-7}`.

**Note**: Directly contacting the individual or any organization is prohibited.<br>
The flag can be obtained using publicly available information only.<br>
**Writeup rule**: If you publish a writeup, be sure to redact the person's name and the LinkedIn URL (both from text and screenshot).


## 解法

LinkedInのページが指定されています。  
LinkedInのページには動画が投稿されており、この人物が最近大学を卒業したことがわかります。  
動画の内容などから調査を進めると、Instagram や TikTok のアカウントを発見できるでしょう。これらのアカウントにはLinkedInと同様の動画が投稿されています。  
SNSの活動内容から、この人物がある名前で活動するインフルエンサーであることが判明します。

投稿内容などから、この人物は中国出身と推定されるため、中国系のSNSで活動がないか調査します。  
RED（小红书）で該当のアカウントを探し、投稿をさかのぼると、2023年10月12日に韓国を訪問したVlogがあります。

この動画の後半では、この人物が2023年9月17日に行われたBLACKPINKのワールドツアーのソウル公演に参加したことがわかり、`02:16`にはチケットの券面も映り込んでいます。  
チケットから読み取れる内容を当てはめると、Flagとなります。

## 出題対象について

実在の人物を題材とするにあたり、writeupルールを明確にしました。また、CTFによるSNS調査がdoxxingに繋がらないように「本名を自身で積極的に公開しているインフルエンサーが数年前に参加したイベント」を題材として選定しました。

（なお、REDのプロフィール欄にはInstagramのアカウント名の記載があり、Instagramに投稿された動画内でも本名が開示されていることから、指定したLinkedInのアカウントは本人のものであると推定できます。）