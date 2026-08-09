# 8pm (100pt / 387 solves)

## 問題文

朝鮮中央テレビにおいて、2026年7月2日午後8時（現地時間）に放映されたニュース番組で、最初に取り上げられた **具体的な施設** はどこか。  
OpenStreetMap のウェイ（Way）番号で答えよ。ただし、個別の建物ではなく、**敷地全体を示す Way** を解答すること。  
例えば、Way 番号が `1234567890` であったとき、Flagは `Diver26{1234567890}` となる。

What was the first **specific facility** featured in the news program broadcast on Korean Central Television at 8:00 PM (local time) on July 2, 2026?
Answer using the OpenStreetMap Way ID. However, provide **the Way ID representing the entire site**, not an individual building.  
For example, if the way number is `1234567890`, the flag should be `Diver26{1234567890}`.


## 解法

朝鮮中央テレビをオンラインで視聴する方法を調べてみましょう。  
`朝鮮中央テレビ オンライン` などとGoogle検索すると、[NK News](https://en.wikipedia.org/wiki/NK_News)によって運営されている「[KCNA Watch](https://kcnawatch.org/)」で過去のものを含めて、朝鮮中央テレビ（Korea Central TV）の番組が視聴できることがわかります。

KCNA Watchのアカウントを作成し、[アーカイブページ](https://kcnawatch.org/kctv-archive/)から問題の条件に合致する番組を探すと、1件ヒットします。

- [Thursday July 02, 2026 8pm Bulletin](https://kcnawatch.org/kctv-archive/6a466fef0bc8c/)

38秒あたりから、学校のような施設が紹介されています。  
このシーンをGoogle LensでReverse Image Searchをすると、「平壌中等学院」であるとわかります。

この名前でGoogle Mapsを検索してもヒットしにくいですが、Wikimapiaなどには座標が記されています。

- https://wikimapia.org/35336513/ja/%E5%B9%B3%E5%A3%8C%E4%B8%AD%E7%AD%89%E5%AD%A6%E9%99%A2

`39°0'58"N   125°49'37"E` をOpenStreetMapで検索すると、学校らしき地物がヒットします。  
[SWIMMER OSINT CTF 2026/flag_on_the_don](https://github.com/diver-osint-ctf/writeups/tree/main/swimmer2026/research_2025/flag_on_the_don)などと同様の方法で、地物のウェイ番号を取得することができます。

- [ウェイ: Pyongyang Middle School for Orphans (1137349515)](https://www.openstreetmap.org/way/1137349515)
