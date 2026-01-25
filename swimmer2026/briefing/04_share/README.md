# 04_share (10pt / 665 solves)

## 問題文

【協力者】の皆さんにとって、調査は苦労を伴うものになるでしょう。  
解答できたこと、発見して嬉しかったこと、苦戦したこと、そういったことを人と分かち合いたくなるかもしれません。  
あなた達はそんなとき、どうするべきでしょうか？

- A: 調査を手伝ってくれる人が現れるかもしれないので、SNSやDiscordに状況を書き込む。
- B: SNSは誰でも読めてしまうが、Discordはクローズドなので、秘密が守られる。SWIMMER OSINT CTFや他のDiscordサーバーに書き込みを行う。
- C: [スポイラー](https://support.discord.com/hc/ja/articles/360022320632--%E3%82%B9%E3%83%9D%E3%82%A4%E3%83%A9%E3%83%BC%E3%82%BF%E3%82%B0)をした上でDiscordに書き込めば「ネタバレ」にならない。きちんと配慮して書き込みを行う。
- D: 調査は秘密の下で行うものである。競技が終わるまでは、チーム内以外に情報を漏らさないように徹底する。

`SWIMMER{A}`、`SWIMMER{B}`、`SWIMMER{C}`、`SWIMMER{D}` のいずれかで答えてください。

Investigations will be challenging for all Collaborators.  
You might want to share your successes, exciting finds, or struggles with others. What should you do in that situation?

- A: Post updates on social media or Discord; someone might step in to help the investigation.
- B: Social media is public, but Discord is closed, so secrets are safe. Post in the SWIMMER OSINT CTF server or other Discord servers.
- C: If you mark posts as [spoilers](https://support.discord.com/hc/en-us/articles/360022320632-Spoiler-Tags) on Discord, it's fine. Post with care and consideration.
- D: Investigations must stay confidential. Until the competition ends, strictly avoid leaking information outside your team.

Answer with one of `SWIMMER{A}`, `SWIMMER{B}`, `SWIMMER{C}`, or `SWIMMER{D}`.


## 解法

ルールには以下のような記載があります。

> 競技中にあなたが得た問題・解答（Flag）・解法・ヒントなど、CTF に関するあらゆる情報を第三者（自分のチームメンバー除く）に共有する行為は禁止されています。他の参加者からこれらを得ようとする行為も禁止されています。
>
> また、公開・非公開を問わず、問題・解答（Flag）・解法・ヒントなどを外部（Web サイトや SNS、Discord、チャット、掲示板、動画配信など）に流出させてはいけません。 例えば、競技に参加していない知人などに問題やその一部を提示し、解答に際して補助を求める行為などはこの規定に該当し、違反となります。

> It is forbidden to share any CTF-related information obtained during the competition with third parties (excluding your own team members), including challenge text, answers (flags), solutions, and hints. Attempts to obtain such information from other participants are also prohibited.
>
> Regardless of whether it is public or private, you must not leak challenges, answers (flags), solutions, hints, etc. to external places (websites, social media, Discord, chats, forums, video streams, etc.). For example, showing a challenge (or part of it) to someone who is not participating and asking for help in solving it falls under this rule.

これより、Dが正解となります。

> D: 調査は秘密の下で行うものである。競技が終わるまでは、チーム内以外に情報を漏らさないように徹底する。
> D: Investigations must stay confidential. Until the competition ends, strictly avoid leaking information outside your team.

Flag: **`SWIMMER{D}`**