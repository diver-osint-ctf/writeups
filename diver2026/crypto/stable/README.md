# stable (339pt / 144 solves)

## 問題文

**`0x5Ec2bb2D56FC8CC4d05110211EcaBDC8fAe3B128`**

お店の名前を現地語で答えよ。<br>
たとえば、店名が現地語で향택 부산전포점のとき、Flagは `Diver26{향택 부산전포점}` となる。
  
Answer the name of the shop in the local language.<br>
For example, if the name of the shop is 향택 부산전포점, the flag should be `Diver26{향택 부산전포점}`.


## 解法

与えられたアドレスをスキャンすると、Polygonチェーンでよく使われているウォレットであることが分かります。  
また、トランザクションを見ると、JPYCで取引していることが分かります。

ここで、JPYCが使えるお店について調べると、以下のようなサイトが見つかります。

https://jpyc-map.jp/

また、JPYC決済利用状況というページもあり、累計、先月、今月の売上が分かります。

https://jpyc-map.jp/jpyc-usage/

そこで、該当ウォレットの先月の売上の合計を計算して、その金額を探すと、「千房 有楽町ビックカメラ支店」と一致します。

Diver26{千房 有楽町ビックカメラ支店}