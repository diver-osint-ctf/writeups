# 06_ask_for_admin (10pt / 663 solves)

## 問題文

【協力者】の皆さんには、このCTFプラットフォーム上で情報を提出していただきます。  
しかし、時には正しい情報を送信したのに incorrect（不正解）と表示されることがあるかもしれません。  
このような場合、どうするべきでしょうか。

- A: CTFプラットフォームの不具合はやむを得ないので、連絡せずに修正されるのを待つ。
- B: すぐに管理者へDMで連絡する。
- C: 自分が入力した形式や情報が正しいかを確認した上で、自分が送信した内容や根拠を添えて Discordの `#ask-for-admin` チャンネルで問い合わせる。DMは使わない。
- D: 不具合が発生しているということを全体で共有するべきなので、 `#general-日本語` チャンネルやSNSで報告する。

All Collaborators will submit information on this CTF platform.  
Sometimes, even correct submissions may be marked as "incorrect." What should you do in such cases?

- A: Assume platform bugs are unavoidable and wait for a fix without contacting anyone.
- B: Immediately DM the admins.
- C: After verifying your format and information, contact Discord `#ask-for-admin` channel (instead of DM) with what you submitted and the supporting evidence.
- D: Because everyone should know about the issue, report it in `#general-english` or on social media.

Answer with one of `SWIMMER{A}`, `SWIMMER{B}`, `SWIMMER{C}`, or `SWIMMER{D}`.


## 解法

ルールには以下のような記載があります。

> Discord の #ask-for-admin チャンネルから問い合わせを行ってください。 CTF 競技中、チケットシステムの不具合を除いて Discord DM や X での対応は致しません。また、運営メンバー個人の DM での対応はいたしません。

> Contact the admins via the #ask-for-admin channel on Discord. During the competition, we will not respond via Discord DMs or X except for ticket system issues. We also do not respond via admins' personal DMs.

これより、Cが正解となります。

> C: 自分が入力した形式や情報が正しいかを確認した上で、自分が送信した内容や根拠を添えて Discordの `#ask-for-admin` チャンネルで問い合わせる。DMは使わない。
> C: After verifying your format and information, contact Discord `#ask-for-admin` channel (instead of DM) with what you submitted and the supporting evidence.

Flag: **`WIMMER{C}`**