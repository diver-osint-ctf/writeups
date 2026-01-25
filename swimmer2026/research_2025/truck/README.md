# truck (100pt / 257 solves)

## 問題文

あるトラックが `8773X3XQ+JWQ` を2025年6月21日 13:39:54（現地時間）ごろに通過しました。このトラックの車体に書かれていたFQDNを解答してください。  
たとえば、`www.google.com` の場合、Flagは `SWIMMER{www.google.com}` となります。

A truck passed `8773X3XQ+JWQ` around June 21, 2025 at 13:39:54 (local time). Please identify the FQDN written on the body of this truck.  
For example, if that was `www.google.com`, the flag would be `SWIMMER{www.google.com}`.


## 解法

`8773X3XQ+JWQ` でGoogle検索すると、アメリカ合衆国ノースカロライナ州ダーラムにある橋「[11–foot–8 Bridge](https://ja.wikipedia.org/wiki/11%E3%83%95%E3%82%A3%E3%83%BC%E3%83%888%E3%83%96%E3%83%AA%E3%83%83%E3%82%B8)」（正式名称: Norfolk Southern–Gregson Street Overpass）がヒットします。

橋の通称でGoogle検索すると、この橋は背の高いトラックが事故を起こすことで有名であり、近くで働くJürgen Henn氏が定点カメラを設置していることでも知られているとわかります。

[Jürgen Hennのサイト](https://11foot8.com/)にアクセスすると、YouTubeチャンネルの動画が掲載されています。日付が一致する動画を探すと、以下のものが見つかります。

- [Moving truck runs red light and scrapes the 11foot8+8 bridge](https://www.youtube.com/watch?v=MJ4tpEhQ86g)

トラックに書かれている[FQDN（完全修飾ドメイン名）](https://www.nic.ad.jp/ja/basics/terms/fqdn.html)は `www.miraclemoversusa.com` となります。

Flag: **`SWIMMER{www.MiracleMoversUSA.com}`** (`SWIMMER{www.MiracleMoversUSA.com.}` なども可。大文字小文字は問わない。)