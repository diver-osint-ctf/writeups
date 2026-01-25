# 06_leaked

## 問題文

**"00_engineer"** の問題で見つかったソフトウェアエンジニアのパスワードが漏洩して公開されてしまったらしい。彼はパスワードを変更して事なきを得たようだが、漏洩したパスワードは何だっただろうか。  
Flag 形式: `Diver25{his_password}`

The password of the software engineer found in the **"00_engineer"** challenge has apparently been compromised and became public.  
He seems to have changed his password and got away with it, but what was the compromised password?  
Flag Format: `Diver25{his_password}`


## 難易度

medium / 499 point (12 solves)

## 解法

GitHub で kodai-sn のリポジトリを見ると（[例](https://github.com/kodai-sn/kodai-sn.github.io)）、2 つのメールアドレスが確認できます。

```
commit 1e2fb627cf786098ea11d76c21e6506d3d007124 (HEAD -> main, origin/main, origin/HEAD)
Author: Kodai.S <kodaisn.development@gmail.com>
Date:   Sat Feb 1 04:20:16 2025 +0900

    Update index.html

commit 665f5726609b05eac33e4cb9a8698323d59775ae
Author: Kodai.S <shinonomekodai@gmail.com>
Date:   Sat Feb 1 04:08:54 2025 +0900

    Create index.html
```

漏洩した情報が投稿される古典的な場所として、[Pastebin](https://www.sompocybersecurity.com/column/glossary/pastebin)が存在します（国内外の CTF にもよく登場します）。

このうち、`kodaisn.development@gmail.com`を Pasatebin で検索すると、以下のものがヒットします。

https://pastebin.com/eHzc8rmB

これより、Flag は以下の通りとなります。

**Diver25{1_4m_fr0m_h0kk41d0_4nd_l0v3_54un4}**

