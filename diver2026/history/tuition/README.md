# tuition (483pt / 48 solves)

## 問題文

添付画像で示されているロボットは、ある現代芸術家の作品である。この芸術家が、1961年2月20日に教育機関へ支払った金銭はいくらか。   
通貨コード（ **ISO 4217コード** ）と共に答えよ。
たとえば、123.40米ドルの場合、Flagは `Diver26{123.40USD}` となる。通貨コードと数値の間にスペースは不要である。

The robot shown in the attached image is the work of a contemporary artist. How much money did this artist pay to an educational institution on February 20, 1961?  
Answer with the amount and the currency code (**ISO 4217 code**).  
For example, if the answer is 123.40 US dollars, the flag should be `Diver26{123.40USD}`. No space is needed between the currency code and the value.


## 配布ファイル

- [tuition.jpg](./public/tuition.jpg)

## 解法

"Robot" や "Artist" というワードとともに Reverse Image Searchを行うと、**ナム・ジュン・パイク** （Nam June Paik）の作品であることがわかります（なお、Google Lensの言語設定によって検索結果は変わります）。

これはナム・ジュン・パイクの「Robot K-567」という作品です。「Robot K-456」に関する情報は画像も含めてオンライン上に多数存在していますが、本作品の情報は少ないです。しかしながら、アート関係の情報がまとめられているサイトや、ブログなどでその姿を確認することができます。

- [Robot K 567 (1994) by Nam June Paik | Artsy](https://www.artsy.net/artwork/nam-june-paik-robot-k-567)
- [プレイプレイアート展＠ワタリウム美術館の覚書 | 美術覚書](https://ameblo.jp/about-art/entry-12808153769.html)

さて、ナム・ジュン・パイクは複数の教育機関に在籍していました。有名なものは東京大学とミュンヘン大学ですが、`Nam June Paik University lang:en` などと検索すると、彼は1961年に[ケルン大学](https://en.wikipedia.org/wiki/University_of_Cologne)に在学していたこともわかります。

> 1956: Studied Western architecture, music history, and philosophy at the University of Munich and the University of Cologne.  
>   
> [Nam June Paik: Opening the Age of Digital Art through Satellites - KU Academy of Mobility Humanities](https://mobilityhumanities.org/en/ih-public-lecture/nam-june-paik-opening-the-age-of-digital-art-through-satellites/)

`Nam June Paik Universität zu Köln` で検索すると、彼の[成績証明書（Studienbuch）](https://en.wikipedia.org/wiki/Transcript_(education))をスキャンしたものが文献としてヒットします。

- https://monoskop.org/images/d/d9/Paik_Nam_June_Studienbuch_ausgestellt_von_der_Universitaet_Koeln.pdf

11ページ目に、20 Feb 1961 に、**Universitätskasse und Quästur**（大学出納課および会計課）宛に **[DM](https://en.wikipedia.org/wiki/Deutsche_Mark) 97.50** の支払いを行った記録が貼付されています。

問題の指示通り、[ISO 4217 コード](https://en.wikipedia.org/wiki/ISO_4217)を利用した表記に改め、Flagは以下の通りになります。

Flag: **Diver26{97.50DEM}**（Diver26{97.5DEM}も可）