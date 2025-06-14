# sanction

## 問題文

2024年10月25日、制裁下にあるロシア船籍のRORO船「ANGARA」がある港湾に停泊していることが衛星画像で確認された。  
停泊位置を答えよ。

On 25 October 2024, satellite imagery confirmed that the Russian-flagged RORO vessel "ANGARA", which is under sanctions, was anchored in a certain port.  
Answer the position of the anchorage.


## 難易度

easy / 375 point (112 solves)

## 解法

"ANGARA" とはどのような船舶なのでしょうか。`Angara Russia ship` で Google 検索してみます。すると、以下のような記事がヒットします。

- [Sanctioned Russian Smuggling Ship Spotted at China's Biggest Repair Yard](https://maritime-executive.com/article/sanctioned-russian-smuggling-ship-spotted-at-china-s-biggest-repair-yard)

記事を読むと、ANGARA が 2023 年 8 月から 2024 年 2 月の間に兵器を北朝鮮からロシアに輸送していたことが確認されているようです。  
こういった輸送を行う場合、使用する港湾はロジスティクスや設備の関係で限定的になるのではと考えられます。そのため、過去に寄港した港湾の情報が参考になるはずです。

そこで、`Angara North Korea` で Google 検索を行うと、以下の記事がヒットします。

- [Thousands of troops, millions of shells](https://www.reuters.com/graphics/UKRAINE-CRISIS/NORTHKOREA-RUSSIA/lgvdxqjwbvo/)

この中で、以下のような記載があります。

> 64 shipments transporting millions of North Korean munitions
> OSC tracked 64 trips to the North Korean port Rajin between September 2023 and March 2025, made by four Russian-flagged container ships: the Angara, Maria, Maia-1 and Lady R. The ships transported North Korean artillery and mortar shells from Rajin to the Russian ports of Vostochny and Dunai before they were transported by train to ammunition depots near Ukraine.

これより、**Rajin** （[羅津港](https://ja.wikipedia.org/wiki/%E7%BE%85%E6%B4%A5%E6%B8%AF)）が利用されていたことがわかります。また、この記事には "Oct. 26, 2024" の Angara の写真も掲載されています。

ここで `Angara North Korea Rajin` と Google 検索すると、以下の資料がヒットします。

- [Unlawful Military Cooperation including Arms Transfers between North Korea and Russia](https://www.mofa.go.jp/mofaj/press/release/pressit_000001_02208.html)

これは日本も参加している[多国間制裁監視チーム（Multilateral Sanctions Monitoring Team）](https://msmt.info/)によって公開された資料で、武器移転を含む北朝鮮とロシアとの間の不法な軍事協力に関する分析レポートとなっています。この資料の 18 ページ目にある "Figure 11: Russia-flagged ANGARA at Rajin Port, DPRK (Oct. 25, 2024)" と題された画像を見ると、羅津港における ANGARA の停泊位置が示されています。

これより、 42.2271, 130.2826 近傍が Flag となります。

## 出題意図

MSMTのような、国際的なレポートもOSINTを活用した情報が含まれています。この問題自体は新しい情報を見つけるものではありませんが、既にレポートしてまとまっているものから必要な情報を得る営みを体験すること、そして実際のインテリジェンスの結果としてまとまった文献に触れることをねらいとしています。

競技時間中にMSMTのレポートを読む時間はなかったと思いますが、競技終了後には、ぜひ時間をとって目を通してみてください。