# debeyohiru_01_social (100pt / 429 solves)

## 問題文

調査対象の人物はソフトウェアエンジニアで、2026年以降には `debeyohiru` というIDでの活動が確認されています。  
この人物がこのIDでの活動を開始したのは2026年1月のようです。この人物がこれ以前に使用していたIDを特定できないでしょうか？  

2026年1月時点で、[note](https://note.com/)というサービスに古いIDのアカウントが残存しているようです。  
このアカウントのIDを解答してください。

例えば、`digital_jpn_gc` が対象のアカウントの場合、 Flag は `SWIMMER{digital_jpn_gc}` となります。

The person under investigation is a software engineer, and from 2026 onward has been active under the ID `debeyohiru` .  
They appear to have started using this ID in January 2026. Can you identify the ID they used before that?  

As of January 2026, an account with their old ID still exists on the service [note](https://note.com/).  
Please answer that account ID.

For example, if the account was `digital_jpn_gc`, the flag would be `SWIMMER{digital_jpn_gc}`.


## 解法

note.com 上で直接検索してみても、 `debeyohiru` というアカウントは見つかりません。また、GoogleやBingなどで検索をしても、直接的に役立ちそうな情報はありません。このようなとき、他の場所に何か情報があるのかもしれません。

SNSを横断して検索するツールとして **[WhatsMyName](https://whatsmyname.app/)** や **[Sherlock](https://github.com/sherlock-project/sherlock)** というものがあり、ソーシャルメディアを探索するOSINTにおいてよく利用されています（類題: [DIVER OSINT CTF 2025 recon/00_engineer](https://github.com/diver-osint-ctf/writeups/tree/main/2025/recon/00_engineer)）。

こういったツールで `debeyohiru` と検索してみると、BlueskyというSNSにアカウントが存在していることが判明します。

- [https://bsky.app/profile/debeyohiru.bsky.social](https://bsky.app/profile/debeyohiru.bsky.social)

debeyohiru による以下の投稿に添付されているスクリーンショットに、note.com のURLが映り込んでいます。どうやら debeyohiru は[Blueskyのアカウント名を変えた](https://bsky.app/profile/debeyohiru.bsky.social/post/3mbbljxdixs23)ようですが、noteのアカウント名は変更していないようです。

- [これも全然反響なかったな。正直寂しい。（2025年12月27日）](https://bsky.app/profile/debeyohiru.bsky.social/post/3mavlx6v3ak2c)

- [https://note.com/furaigo5](https://note.com/furaigo5)

Flag: **`SWIMMER{furaigo5}`**