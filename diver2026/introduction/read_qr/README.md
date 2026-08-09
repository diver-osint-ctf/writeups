# read_qr (100pt / 547 solves)

## 問題文

このQRコードには何というURLが記録されているのだろうか。  
例えば `https://x.com/DIVER_OSINT_CTF` というURLが記録されていた場合、flag は `Diver26{https://x.com/DIVER_OSINT_CTF}` となる。

What URL is stored in this QR code?  
If it is `https://x.com/DIVER_OSINT_CTF`, the flag should be `Diver26{https://x.com/DIVER_OSINT_CTF}`.


## 配布ファイル

- [read_qr.jpg](./public/read_qr.jpg)

## 解法

この QR コードにはある URL が記録されているのですが、その URL にアクセスすると、`https://qr.intro26.workers.dev/` にリダイレクトされてしまい、元のURLは表示されません。

[QRQR](https://www.qrqrq.com/)など、アクセス前にQRコードの読み取り結果を表示してくれるアプリを使うと、以下のURLが取得できます。

Flag: **Diver26{https://qr.intro26.workers.dev/q/y0u_r34d_7h3_qr_wi7h0u7_4cc3ss}**

## 出題の背景

スマートフォン上のQRコードリーダーでは、QRコードにURLが含まれていると、そのままブラウザでWebページを表示してくれるものがあります。  
確かに便利ですが、近年増加している[クイッシング](https://www.ibm.com/jp-ja/think/insights/quishing-growing-threat-hiding-plain-sight)のリスクなどを考慮すると、自動でアクセスせず、まずはQRコードの内容を確認すべきです。