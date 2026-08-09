# momo (100pt / 558 solves)

## 問題文

2026年4月に航空機の写真を撮影していたが、機体記号を写し忘れてしまった。写真が示す航空機の機体記号を調べて答えよ。  
もし機体記号が `JA380A` であれば、Flagは `Diver26{JA380A}` となる。  

I took a photo of an aircraft in April 2026, but I forgot to photograph its registration number. Find out and answer the registration number of the aircraft shown in the photo.  
If the registration number is `JA380A`, the flag should be `Diver26{JA380A}`.


## 配布ファイル

- [momo.jpg](./public/momo.jpg)

## 解法

航空機の後方部分に広告が掲載されています。Google Lens で読み取ると「太平電業」という企業のものであることがわかります。

また、航空機は Peach の機体であることがわかります。

日本語表記の `太平電業 Peach` で検索してみましょう。すると、太平電業の広告を施したPeach機として "JA828P" と "JA823P" の2つがヒットします。

[JA828Pの写真を Planespotters などで検索する](https://www.planespotters.net/search?q=JA828P)と、2023年ごろは太平電業の広告を掲載していたことが確認できますが、2026年に撮影された写真では広告無しに戻っていることがわかります。

JA823Pの2026年の写真はPlanespottersに掲載されていないものの、[Flyteamなど別のサイトを検索する](https://flyteam.jp/registration/JA823P)と、2026年4月に太平電業の広告を掲載した姿が撮影されていることがわかります。

ソースが1枚だけであれば情報が間違っている可能性もありますが、複数の投稿者・複数のサイトで2機の状態が確認できることから、これらの情報は正しいと考えてよいでしょう。

Flag: **Diver26{JA823P}** 