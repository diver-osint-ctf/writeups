# internal

## 問題文

**"00_engineer"** の問題で見つかった会社では、Webブラウザからアクセス可能な社内用のDevOpsプラットフォームが運用されている。  
そのシステムのバージョン名を、表記されている通りに答えよ。  
Flag 形式: `Diver25{135.0.1-f2+nightly}`

The company found in the **"00_engineer"** challenge operates an internal DevOps platform which can be accessed from web browsers.  
Answer the name of the version of the system as it is displayed.  
Flag Format: `Diver25{135.0.1-f2+nightly}`


## 難易度

medium / 416 point (93 solves)

## 解法

magneight 社の Web サイトは `magneight.com` で、IP を逆引きすると `202.212.71.93` となります。

この IP を ViewDNS などのツールに通すと、 `magn8soft.tokyo` という別のドメインがヒットします。

https://viewdns.info/reverseip/?host=202.212.71.93&t=1

続いて、[crt.sh で `magn8soft.tokyo` の証明書を探す](https://crt.sh/?q=magn8soft.tokyo)と、 `gitea.magn8soft.tokyo` というサブドメインがヒットします。  
https://gitea.magn8soft.tokyo/ にアクセスすると、[Gitea](https://about.gitea.com/)が動作しており、バージョンが画面下部に記載されています。

また、[shodan で 202.212.71.93](https://www.shodan.io/host/202.212.71.93)にアクセスすると、「Gitea: Git with a cup of tea」が動作していることが示されています。上記の `gitea.magn8soft.tokyo` はリバースプロキシによるものなのですが、magneight 社の環境では 3000 番ポートへ直接アクセスが塞がれている訳ではないため、こちらからもアクセスが可能です。

**Diver25{1.24.0+dev-303-gd88b012525}**

