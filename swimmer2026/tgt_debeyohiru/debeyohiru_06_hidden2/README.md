# debeyohiru_06_hidden2 (100pt / 258 solves)

## 問題文

`debeyohiru` が **2025年12月** 時点で使用していたと考えられるスマートフォンの機種が知りたいです。  
なお、複数の端末を使用していたと考えられる場合は、アンダーバー（`_`）で繋いで全てを解答してください。この場合、回答順序は問いません。  
また、メーカー名は不要です。

例えば、Xperia 10 VIIとiPhone 17を使用していた場合、
Flagは `SWIMMER{Xperia 10 VII_iPhone 17}` となります。

We want to know the smartphone models `debeyohiru` is believed to have used as of **December 2025**.  
If you believe they used multiple devices, answer all of them connected with underscores (`_`). In this case, the order does not matter.  
You do not need to include the manufacturer name.

For example, if they used Xperia 10 VII and iPhone 17, the flag would be `SWIMMER{Xperia 10 VII_iPhone 17}`.


## 解法

furaigo5 のサイトを見ると、使用している環境が記載されています。

> スマートフォン: Xiaomi 15 Ultra / iPhone 13 mini（検証用）

2026年1月10日に「[初売りでスマートフォンを買い替えた](https://bsky.app/profile/debeyohiru.bsky.social/post/3mc2lwrkq2s2c)」と投稿しており、これは更新されたものだと考えられます。2025年12月時点の情報を反映している表記が確認できればよいのですが、過去のWebサイトを見る方法はないでしょうか。

過去のWebサイトを見る方法として、アーカイブサイト（いわゆる「魚拓」サイト）が考えられます。主要なアーカイブサイトとして、以下の2つが挙げられます。

- [Wayback Machine](https://web.archive.org/)
- [archive.today](https://archive.today/)

furaigo5 のサイトを検索してみましょう。   
Wayback Machineでは古い情報を記録したアーカイブが存在していません。しかし、archive.todayには2026年1月2日の記録が残っています。

- [https://archive.md/https://furaigo5.github.io/profile/](https://archive.md/https://furaigo5.github.io/profile/)

このアーカイブされたページを見てみると、古い使用機種が記載されています。

Flag: **`SWIMMER{Pixel 8 Pro_iPhone 13 mini}`** （逆順や表記ゆれも許容）