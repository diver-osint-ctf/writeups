# kaitai3 (498pt / 19 solves)

## 問題文

kaitai1 の土地に、昭和後期に存在していた店舗の名前を日本語で答えよ。  
**店名のみ** を答えよ。例えば 「株式会社万世」が運営する `肉の万世 秋葉原本店` が存在していた場合、Flagは `Diver26{肉の万世}` となる。

**writeup規定**: writeupを記載する場合、もし個人の氏名や電話番号、住所などの情報がある場合は伏せてください（店舗に関する情報は問題ありません）。

Answer the name (**in Japanese**) of the store that existed at the location of kaitai1 during the late [Shōwa era](https://en.wikipedia.org/wiki/Sh%C5%8Dwa_era).  
Provide **only the store name** . For example, if `肉の万世 秋葉原本店` (Niku no Mansei Akihabara Main Store) operated by Mansei Co., Ltd. had been located there, the flag should be `Diver26{肉の万世}`.

**Writeup Rule:** If you publish a writeup, redact any personal information such as names, phone numbers, or addresses (information regarding the store itself is okay).


## 解法

過去の Google ストリートビューを確認しても、特に店名が確認できるものは残っていません。

しかし、古い文献に何かが残っている可能性があります。  
日本の古い文献は[国立国会図書館デジタルコレクション](https://dl.ndl.go.jp/)で閲覧できるものも多くあります。

この土地の住所（住居表示によるもの）はGoogle Mapsによれば "東京都世田谷区北沢2丁目32-5" です。

検索欄で `世田谷区北沢2丁目32-5`, `世田谷区北沢2-32-5`, `北沢2-32-5`, `北沢2-32` など、様々な表記を試してみると「全国工場通覧 昭和43年版」という書籍がヒットします。  
この1036コマ目に「（株）久保田製菓つくしや」という会社の「つくしや北沢工場」があったことが確認できます。

https://dl.ndl.go.jp/pid/8312450/1/1036?keyword=%E5%8C%97%E6%B2%A22-32

「つくしや」のWebサイトを確認すると、以下の記述が確認できます。北沢2-32-5は下北沢駅の北口からアクセス可能であり、「下北沢北口のお店」が立地していたのではないかと考えられます。

> 現在、下北沢北口のお店はなく、下北沢南口の売店１店舗になっております。  
> https://tsukushiya.com/history/

Flag: **Diver26{つくしや}**