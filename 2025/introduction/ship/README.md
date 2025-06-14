# ship

## 問題文

これは、ある組織が運用する船舶である。もし将来、この船が外国に売却されたとしても、変わらない番号を答えよ。  
Flag 形式: `Diver25{現地語での船名_番号}`（例: 船名が「ペンギン饅頭号」で番号が `1234567` の場合、Flag は `Diver25{ペンギン饅頭号_1234567}` となる）

This is a vessel operated by a some organisation. Answer the number that would remain the same if this vessel were to be sold to a foreign country in the future.  
Flag Format: `Diver25{ship name in **the local language**_number}` (e.g. If the ship name is "ペンギン饅頭号" and the number is `1234567`, the flag should be `Diver25{ペンギン饅頭号_1234567}`.)


[配布ファイル](./public)

## ヒント

1. 船名には記号を含まない。 / The ship name doesn't contain symbols.

## 難易度

introduction / 100 point (363 solves)

## 解法

Google Lens を用いたり、船舶の側面に記載されている **7JVV** という文字列を検索すると、東京海洋大学が運用する「神鷹丸」という船であるとわかります。

- https://ja.wikipedia.org/wiki/%E7%A5%9E%E9%B7%B9%E4%B8%B8_(4%E4%BB%A3)
- https://www.marinetraffic.com/en/ais/details/ships/shipid:3897814/mmsi:431328000/imo:9767675/vessel:SHINYO_MARU

ここで、船舶に関する番号を調べてみましょう。`vessel number` で検索してみると、様々な種類の番号が存在していることが分かります。その中で[IMO number](https://en.wikipedia.org/wiki/IMO_number)は、船籍が変わった場合でも変わらないことが分かります。

先ほどヒットした神鷹丸に関する情報を確認すると、IMO number は **9767675** であることが分かります。

なお、英語表記 "SHINYO MARU" で検索すると、別の船もヒットしますが、運用者の東京海洋大学（Tokyo University of Marine Science and Technology）で検索することで、正しい「神鷹丸」に辿り着けます。

**Diver25{神鷹丸\_9767675}**

## 出題意図

船舶を示す際、IMO 番号は MMSI と並んでよく利用されるものであるため、その概念に触れてもらうために introduction カテゴリで出題しました。
