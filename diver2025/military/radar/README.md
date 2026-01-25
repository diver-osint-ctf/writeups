# radar

## 問題文

画像 / Image:  
https://drive.google.com/file/d/1hHoRFkG3ZpiQvgBN5wN9BMIkiF5WSIB1/view?usp=sharing

画像に写っているものは、福建省に存在する、中国人民解放軍東部戦区のレーダー施設であると考えられる。  
公式な情報は明らかにされていないものの、オンライン上で中国の軍事を分析している人々がこの基地を運用する部隊と分隊の番号を特定しているらしい。  
もちろん、オンライン上の情報だけを鵜呑みにするわけにはいかないが、ひとまず検討する価値はあるだろう。  
その情報を探り当て、教えてほしい。  
Flag形式: `Diver25{部隊番号_分隊番号}`（例えば12345部隊の56分隊のとき、`Diver25{12345_56}` となる）

The facility in the image is believed to be a radar facility in the Chinese People's Liberation Army's Eastern War Zone, located in Fujian Province.  
Although no official information has been revealed, people analysing PLA on the internet have apparently identified the unit and squad numbers that operate this base.
Of course, we cannot just rely on those information on the internet, but it is worth considering at least.  
Flag Format: `Diver25{Unit Number_Squad Number}` (e.g. If the answer is Squad 56 of Unit 12345, the flag should be `Diver25{12345_56}`)

Image source: Google Earth


## ヒント

1. 画像はノースアップである。 / The image is north-up.
2. オンライン上には誤った情報も存在しています。注意してください。一方、信憑性を高める公的な情報も存在しています。 / There is also incorrect information online. Please be aware of that. On the other hand, there is also public (official) information that adds credibility.

## 難易度

easy / 481 point (45 solves)

## 解法

「[中国人民解放軍東部戦区](https://en.wikipedia.org/wiki/Eastern_Theater_Command)」について検索すると、文字通り中国の東部を管轄する[戦区](https://en.wikipedia.org/wiki/Theater_command)であり、福建省もそこに含まれているとわかります。

画像を見る限り、右側には水面がありますから、まずは福建省で海沿いの地域を地道に探します。すると、25.797522, 119.612144 付近に当該の施設が見つかります。

Google Maps で 近隣の住所を引くと、「福建省 福州市 长乐市 下沙村」であると表示されます。正確には「长乐市」は「长乐区」に変更されたため、「福建省 福州市 长乐区 江田镇市 江田镇 下沙村」あるいは「福建省 福州市 长乐区 下沙村」となります（Baidu Maps ではこちらが表示されるはずです）。

Google 翻訳などを通すと、「レーダー」は中国語で **雷達** と訳されることがわかります。

そこで、 `下沙村 雷達` と検索してみると、以下のような Web サイトがヒットします。

https://redtsai.blogspot.com/2019/12/blog-post_97.html

> 92985 部队 84 分队 福建省福州市長樂市下沙村\*

また、2018 年頃に出された、下沙村付近を含む計画停電の情報に **92985 部队 84 分队** が含まれており、比較的確度が高い情報であると判断できます。

- https://www.sohu.com/a/271841818_349455
- https://www.clnews.com.cn/html/3/2018-10-20/223221136540.shtml

**Diver25{92985_84}**

## 出題意図

座標なしで示された衛星画像から場所を探し出し、その座標に基づく地名を調べ、そこから軍事に関する情報を見つけてもらう問題です。

外国メディアが中国軍の動向を扱う際、衛星画像をソースとしたものは多数見られます。

- [中国が「軍民両用艦」建造、台湾有事には兵員・兵器輸送に利用か…読売新聞など衛星画像分析（読売新聞）](https://www.yomiuri.co.jp/world/20250501-OYT1T50183/)
- [中国、空自機形のミサイル標的設置か　衛星写真で初確認（日本経済新聞）](https://www.nikkei.com/telling/DGXZTS00001510X10C22A5000000/)

このような報道は非常に有益であるのですが、大まかな地名のみで座標が示されないことがよくあります。分析したい内容によっては具体的な座標を確認し、自分でその場所を認識する必要が発生します。

そこで、本問の前半では、実際に「福建省」という情報だけから基地の場所を探してもらう問題としました。

一方で、逆に住所を使わないと引けない情報も存在します。後半では、住所を基に情報を探索し、確認してもらうようにしました。PLAは部隊や分隊の公式サイトはなくても、民間や行政のサイトに痕跡が残っていることがあり（今回の場合は停電情報）、そういった情報源を知ってもらうという狙いもあります。