# p2t

## 問題文

この写真の左側に掲示されている写真には、ある動物が写っている。その名前を、日本語で書かれている通りに答えよ。  
Flag 形式: `Diver25{シバイヌ}`

The photo posted to the left of this photo shows an animal. Answer its name as it is written in Japanese.  
Flag Format: `Diver25{シバイヌ}`



[配布ファイル](./public)

## 難易度

introduction / 377 point (112 solves)

## 解法

どこかに掲示されているハシブトガラスの写真ですが、Google レンズなどの画像検索にかけても同じ写真は見つかりません。そこで、写真が撮られた場所を推定するために別のアプローチを行う必要があります。

画像の右側に「時に」「立山」「われ」「ボソ」「いま」と書かれています。**立山** という地名から「立山 ハシブトガラス」で検索し、画像を調査すると、同様の写真が掲載されているブログが見つかります（https://yachou.info/murodoudaira-raichou/ ）。

ブログで「室堂平｜立山自然保護センター　野鳥の紹介」と書かれている画像を確認すると、左側に **トビ** の写真が見つかります。

**Diver25{トビ}**

## 出題意図

introductionレベルとして、単に画像検索をするだけでなく、画像の中の特徴的な単語を検索することを学習してほしいというねらいで出題しました。画像検索では直接情報が得られないケースも多く、このような場合にどうアプローチするかを考える力を身に着けてほしいと考えています。