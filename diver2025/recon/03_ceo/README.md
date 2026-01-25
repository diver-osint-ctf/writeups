# ceo

## 問題文

**"00_engineer"** の問題で見つかった会社の、CEOのメールアドレス（Gmail）を答えよ。  
Answer the email address (Gmail) of the CEO of the company found in **"00_engineer"** challenge?  
Flag 形式 / Flag Format: `Diver25{example@gmail.com}`


## 難易度

medium / 302 point (142 solves)

## 解法

engineer の問題で見つかった Kodai Shinonome の X アカウントによると、彼は社内向けに git のハンズオンを実施しています。
彼は、その際の資料を Speaker Deck に投稿したようです。

https://x.com/kodai_sn/status/1896794735219445938

その中に、[GitHub 上でリポジトリをフォークすることを促す手順が記載されています](https://speakerdeck.com/kodaisn/githanzuon-c9889490-d454-4b2b-a971-458150bc4099?slide=11)。彼が練習用として参加者のために用意したリポジトリは以下のようです。

https://github.com/kodai-sn/fork-practice

このリポジトリを開き、[フォーク一覧](https://github.com/kodai-sn/fork-practice/forks)を表示すると、mizuki1206edelweiss というユーザによるフォークが存在することが分かります。

https://github.com/mizuki1206edelweiss/fork-practice

このリポジトリを手元に clone して、git log を叩いてみましょう。

```bash
$ git clone https://github.com/mizuki1206edelweiss/fork-practice
$ cd fork-practice
$ git log
commit 803a933d2b63da88e57433142c4d78a7837e51e8 (HEAD -> main, origin/main, origin/HEAD)
Author: mizuki1206edelweiss <mizuki1206anemone@gmail.com>
Date:   Mon Apr 21 17:55:41 2025 +0000

    add "YUKI-ONNA" story

commit 099ade8d13924a5bc298004ddf23f0370a32aafe
Author: Kodai.S <kodaisn.development@gmail.com>
Date:   Sat Mar 1 11:56:20 2025 +0000

    Add a text file (Novel "The Restaurant of Many Orders" by Kenji Miyazawa)

commit 82952d0917f20bea3f2d23b971cf560ae1abdba0
Author: Kodai.S <kodaisn.development@gmail.com>
Date:   Sat Mar 1 20:54:13 2025 +0900

    Initial commit
```

`mizuki1206anemone@gmail.com` というメールアドレスが得られます。Epieos や GHunt からカレンダーの情報が得られ、Magneight 社の Web サイトに記載されている CEO の氏名と一致することが分かります。

**Diver25{mmizuki1206anemone@gmail.com}**

