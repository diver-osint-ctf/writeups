# lattice_tower (100pt / 286 solves)

## 問題文

2025年12月、日本で地震が発生し、ある通信施設の鉄塔が被害を受けました。  
主要ニュースで報じられた名称以外に、このビルには通信施設としての別の公式な名前があるようです。  
その正式名称を日本語で解答してください。  

ただし、解答にアルファベットや数字が含まれている場合はそのまま答えてください（ただし、 **半角英数字** にしてください）。  
また、そのビルを保有している会社名は含まず、ビル名だけがFlagになります。  

例えば、「SWIMMER OSINT CTF株式会社　台場SWIMMER2026ビル」だった場合、Flagは `SWIMMER{台場SWIMMER2026ビル}` となります。

In December 2025, an earthquake struck Japan and damaged the lattice tower of a communications facility.  
In addition to the name reported in the major news articles, the building appears to have another official name as a communications facility.

Please answer that official name in **Japanese**.  
If the answer contains letters or numbers, keep them as they are, but use ASCII alphanumerics.

Do not include the company that owns the building; only the building name should be in the flag.  
For example, if the building were called "SWIMMER OSINT CTF株式会社　台場SWIMMER2026ビル" the flag would be `SWIMMER{台場SWIMMER2026ビル}`.


## 解法

2025年12月の地震で被災した鉄塔について調べると、ニュース記事がヒットします。  
「ＮＴＴ青森八戸ビル」と記載されています。
https://www.yomiuri.co.jp/national/20251211-GYT1T00434/

「ntt 鉄塔 一覧」で検索すると、NTT東日本の鉄塔情報が表示されます。

- https://www.ntt-east.co.jp/info-st/mutial/teltower/
- https://www.ntt-east.co.jp/info-st/mutial/teltower/tt-aomori.pdf

Flag: **`SWIMMER{八戸NW3棟}`** （全角表記も正答）