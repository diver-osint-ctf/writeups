# engineer

## 問題文

東京駅の近くでソフトウェアエンジニアの名札を拾った。おそらく落とし物だろう。  
このエンジニアが勤務している会社のWebサイト（トップページ）のURLを答えよ。  
Flag 形式: `Diver25{https://google.com}`

An software engineer's nameplate was picked up near Tokyo Station. This should be a lost item.  
Answer the URL of the website (index page) of the company where this engineer works.  
Flag Format: `Diver25{https://google.com}`

**recon** カテゴリの問題を解答するには、この問題の情報が必要となる。ただし、この問題を除き、どの順序で解答しても構わない。  
To answer the challenges in the **recon** category, information on this challenge is required. However, the challenges can be answered in any order except this one.



[配布ファイル](./public)

## ヒント

1. この名札が東京駅近くで見つかったことから、日本の会社だろう。 / This should be Japanese company because this nameplate was found nearby Tokyo Station, Tokyo, Japan.

## 難易度

easy / 100 point (346 solves)

## 解法

添付された名札には **kodai_sn** と書かれています。[Sherlock](https://github.com/sherlock-project/sherlock)などを使って SNS を検索すると、"Kodai.S"と名乗る SNS アカウントがヒットします。

https://x.com/kodai_sn

このアカウントに記載されている URL にアクセスすると、彼のプロフィールサイトがヒットします。

https://kodai-sn.github.io/

このソフトウェアエンジニアのフルネームが **Kodai Shinonome** であることがわかり、勤務先の Magneight Software 社のリンクが記載されています。

これより、Flag は以下の通りとなります。

**Diver25{https://magneight.com}**

