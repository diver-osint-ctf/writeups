# lilica_05_hosting (100pt / 333 solves)

## 問題文

`lilica` が運営している個人サイトは、あるホスティングサービス上に存在しています。  
このサイトは規約違反を行っているわけではないので何かできるわけではありませんが…… 念の為、連絡先を知っておきたいです。  
このホスティングサービスの規約違反通報メールアドレスを解答してください。  
例えば、メールアドレスが `foobar@example.com` の場合、Flagは `SWIMMER{foobar@example.com}` となります。

**警告** : このアドレスに対してメールを送信してはなりません。 **解答に際して、メールを送る必要は一切ありません**。

`lilica` hosts a personal site on a hosting service.  
The site itself is not violating any terms, but for caution, we want to know the contact address of the hosting service.  
Please answer the abuse-reporting email address for this hosting service.  
For example, if the address were `foobar@example.com`, the flag would be `SWIMMER{foobar@example.com}`.

**Warning**: DO NOT SEND EMAIL to this address. **You do not need to send any emails to answer.**


## 解法

この文脈において「ホスティングサービス」とは、レンタルサーバなどのことを指していると考えて構いません。  
Webサーバであれば、何らかのIPアドレスが割り当てられているはずです。IPアドレスから、その保有者（ここではホスティングサービスの運営会社）がわかると考えられます。

さて、ドメイン名とIPアドレスを紐づける情報はないでしょうか？検索してみると、DNSというシステムによってドメイン名とIPアドレスが相互変換されているといった解説が多く見つかります。

`ドメイン名 DNS 検索` などとGoogle検索してみると、以下のようなサイトが見つかります。ここで lilica のサイトで使われていた `twilight-lilica.com` を入力してみましょう。

- [nslookup(dig)テスト【DNSサーバ接続確認】](https://cman.jp/network/support/nslookup.html)

すると、以下のように `45.77.129.141` というIPがヒットします。

```
対象ドメイン または IPアドレス
対象ホスト名(FQDN) または IPアドレス
twilight-lilica.com

入力の逆引き または 正引き
45.77.129.141
```

このIPアドレスの保有者を確認しましょう。`IPアドレス 検索` などと検索すると以下のサイトがヒットします。

- [ドメイン/IPアドレス サーチ 【whois情報検索】](https://www.cman.jp/network/support/ip.html)

すると、以下のような情報がヒットし、 `Vultr Holdings, LLC` という組織がこのIPアドレスを利用しており、`abuse@vultr.com` が規約違反（abuse）時の連絡先であると判明します。

```
OrgName:        Vultr Holdings, LLC
（省略）
OrgAbuseEmail:  abuse@vultr.com
```

このメールアドレスで Google 検索すると、[Vultrというホスティングサービスの利用規約ページ](https://www.vultr.com/legal/tos/)にも記載があることから、これが「規約違反通報メールアドレス」であると判断できます。

Flag: **`SWIMMER{abuse@vultr.com}`**