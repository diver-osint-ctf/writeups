# lilica_04_domain (100pt / 443 solves)

## 問題文

`lilica` は個人のWebサイトを運営していたようです。  
このWebサイトのドメイン名が取得された日付が知りたいです。`YYYY/MM/DD` の形式で解答してください。  

例えば、2026年1月2日 がドメイン取得日の場合、Flagは `SWIMMER{2026/01/02}` となります。

`lilica` ran a personal website.  
When was its domain name registered? Answer in the `YYYY/MM/DD` format.  
For example, if the domain was registered on January 2, 2026, the flag would be `SWIMMER{2026/01/02}`.


## 解法

lilica はXにおいて、以下の投稿でWebサイトについて言及しています。

- [そういやお友達にお願いしてHP作ってもらいました 全然工事中です（本業のこと話したし）（2025年12月13日）](https://x.com/twilight_lilica/status/1999551960341496014)


Webサイトは以下の通りです。`twilight-lilica.com` が[ドメイン名](https://ja.wikipedia.org/wiki/%E3%83%89%E3%83%A1%E3%82%A4%E3%83%B3%E5%90%8D)です。

- [https://twilight-lilica.com/](https://twilight-lilica.com/)

さて、`ドメイン名 取得日` などとGoogle検索してみましょう。すると、 **Whois情報** というものが存在することがわかります。

そこで、`Whois 検索サイト` などとGoogle検索すると、いくつかの検索サイトがヒットします。ここでは「[さくらのドメイン](https://domain.sakura.ad.jp/domain-lookup/)」で公開されている検索ページを使ってみます。

すると、登録年月日として **2025-10-05T07:08:47Z**  と表示されます。これより、2025年10月5日であると判明します。

Flag: **`SWIMMER{2025/10/05}`**