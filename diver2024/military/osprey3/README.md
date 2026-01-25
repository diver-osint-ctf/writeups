# osprey3

## 問題文

墜落した機体は2018年11月15日の夜、ある空港に駐機していたらしい。その地点の標高（**フィート**）を整数で答えよ。なお、各種データソースの時刻にズレはないと仮定してよい。また、空港に関する情報は最新のものを参照してよい（2018年時点のデータを用いる必要はない）。  
Flag例: `Diver24{250}`

この"osprey3"がこのCTFにおけるオスプレイの事故に関する最後の問題です。

The crashed aircraft was apparently parked at some airport on the night of 15 November 2018. Give the elevation (in feet and integer) of that point. You can consider there are no discrepancies in the times of the various data sources. Also you can refer the latest information about the airport (no need to use data as of 2018).  
Flag example: `Diver24{250}`

This "osprey3" is the last challenges about the Osprey crash in this CTF.

### Hint

- 空港全体の標高ではなく、駐機していた地点の標高である。 / Not an altitude of entire airport but an altitude of parking spot.
- 変換、四捨五入などを行う必要はありません。問題文に合致した明確な数値を見つけることができます。 / No need to convert, round and so on. You will see an obvious number which matches the statement.

## 難易度
medium / 479 point (24 solves)

## 解法

<details>

<summary>クリックで表示</summary>

引き続き、osprey1で調べた機体記号を用います。「12-0065」で検索すると、[航空機の写真を投稿するサイト](https://www.jetphotos.com/registration/12-0065)がヒットし、この中に[2018年11月15日の画像](https://www.jetphotos.com/photo/9144357)があります。

撮影地の欄に **Kraków John Paul II Balice Int'l - EPKK** と書かれており、ポーランドのクラクフにある[Kraków John Paul II International Airport](https://en.wikipedia.org/wiki/Krak%C3%B3w_John_Paul_II_International_Airport)で撮影された写真であるとわかります。機体の後ろには管制塔らしい建物、右側には格納庫が写っています。

Google Mapsから判読する限り、管制塔は `50.074402, 19.795526` 付近に存在する建物であると確認できます。また、滑走路を挟んだ反対側の道路から[ストリートビュー](https://maps.app.goo.gl/YgCoY9ihykLvaj7J8)を眺めると、似た構図が確認できます。これより、2018年11月15日、12-0065は管制塔前の駐機場（エプロン）に駐機していたことがわかります。

さて、ここでKraków John Paul II International Airportの詳細な情報を得たいため、空港名ではなく空港コードを使って `EPKK elevation` と検索してみましょう。
[SkyVector](https://skyvector.com/airport/EPKK/Krakow-Balice-Airport)のようなサイトがヒットしますが、そこには**空港全体**や滑走路の標高しか記載されておらず、Flagの要件を満たしません。

正しい情報を見つけるには、もしかすると飛行場に関する知識が必要となるかもしれません。

まず、空港は大きい施設であるため、一見すると平面に見えても、場所によって標高はわずかに異なります。例えば、先ほどのSkyVectorで確認する限りでも滑走路の両端（07と25）で異なる標高が記載されています。そして、このような情報は**AIP**（Aeronautical Information Publication, 航空路誌）と呼ばれるドキュメントに記載されています。AIPは各国の航空当局から公開されており、電子版はeAIPと呼ばれます。

正攻法としては `AIP Poland` で検索して、ポーランド航空当局から公開されている情報を探してほしいのですが、実は `EPKK elevation` で検索した際にもAIPを掲載（転載）しているサイトがヒットします。

https://plvacc.pl/pilots/airports/EPKK

こちらは "Poland VACC" と記載されているのですが、実は公的機関のサイトではなくゲーマー向けの情報です、
PC向けフライトシミュレーターの世界では、単に飛行するだけでなく、オンラインで管制官担当・パイロット担当に分かれて擬似的な航空管制を行うというプレイスタイルが存在します（[VATSIM](https://vatsim.net/)）。VATSIMプレイヤーは基本的に現実世界の航空路や管制空域に準拠してバーチャル航空管制を行うため、公共機関からの実際のAIPを転載している例が多く見られます。VATSIM関係のサイトはゲーム用ではあるものの、よく整理されていて検索でヒットすることは多く、調査の足がかりになるかもしれません（1次ソースではないことには留意してください）。

"Poland VACC"のサイトでは `1-1-1 - Aerodrome Chart - ICAO` というリンクから飛行場全体の図がPDFで入手できます。

とはいえ、本来ならば情報源としてはあまりおすすめできないので、一応ポーランド航空当局のサイトを利用する前提で進めます。
`AIP Poland` のGoogle検索結果より、以下のサイトに辿り着けます。

https://www.ais.pansa.pl/publikacje/aip-ifr/

`EPKK`でページ内を検索し、**1-1-1 - Mapa lotniska - ICAO** のリンクから飛行場の全体図を得ることができます。
航空分野の知識がある方であれば、ここまで `EPKK Aerodrome chart` などと検索するだけですぐに辿り着けたかもしれません（飛行場の平面図は "Aerodrome Chart" と称されます）。

https://www.ais.pansa.pl/aip/pliki/EP_AD_2_EPKK_1-1-1_en.pdf

いずれにせよ、PDFから、先ほどの衛星画像で確認した駐機場（エプロン、apron）の名称が **MILITARY APRON 3** であったことがわかります。
名前の下に**ELEV** (elevation)が **774** であると書かれており、これがFlagです。

**Diver24{774}**

本問では、航空ファンによって非公式に投稿された情報と、当局の公式情報を突き合わせて情報を探索する過程を擬似的に体験してもらうことを狙いとしています。

軍事的な動向はすべて公式の発表があるわけではありませんし、都合よくFlightradar24に写る訳でもありません。
そのため、航空ファンによって現地から投稿された写真が「その地点にその航空機がいた証拠」「その時点で航空機に塗装や装備の変化があった証拠」となるケースがあります。

マニアックですが、具体例を挙げてみましょう。最近、以前まではロシア空軍に所属していたIl-62M（[RA-86540](https://www.planespotters.net/photos/reg/RA-86540)）が、[2024年4月に撮影された画像](https://www.jetphotos.com/photo/11300065)から海軍に転籍したことが判明しました。このような情報は些細ではあるのですが、積み重ねていくことで各国軍の配置・戦略の推測に役立ちます。しかし、公表したところで何らメリットがないため、プレスリリースなどは発表されません。

しかし、これらの写真はあくまで民間人から投稿された非公式の情報です。有益ではあるものの、複数の情報と照合が必要なケースも多いといえます。

今回の後半パートはそれにあたります。AIPに代表される航空機の運航に関する情報はある程度公開されているものが多く、Web上からそれらを取得することが可能です。  
今年1月に羽田空港で発生した事故のファクトチェックなどにおいても、このようなAIPを基にした検証が大いに役立ちました。

</details>