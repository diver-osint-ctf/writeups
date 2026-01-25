# osprey2

## 問題文

2024年2月15日、ある米軍基地でこの事故に関する追悼式典が実施された。16:46:37ごろ、その式典はどこで実施されていたか。  
OpenStreetMapのWay番号で答えよ。  
Flag例: `Diver24{123456789}`

On 15 February 2024, a memorial service concerning this accident was held at a US military base. At approximately 16:46:37, where was the ceremony taking place?  
Answer using the OpenStreetMap Way number.  
Flag example: `Diver24{123456789}`

### Hint

 基地全体ではなく、基地内の特定の区画・地点を示してください。 / Not an entire air base. Plase designate the specific area/point in the airbase

## 難易度

easy / 100 point (114 solves)

## 解法

<details>

<summary>クリックで表示</summary>

前問で分かった `GUNDAM22` でGoogleやDuckDuckGoを検索すると、[**Yokota honors the fallen crew of Gundam 22**](https://www.kadena.af.mil/News/Article/3691731/yokota-honors-the-fallen-crew-of-gundam-22/) と題した記事がヒットします。この記事に掲載されている写真は「DOWNLOAD HI-RES」のリンクから、高画質版がダウンロードできます。

この画像 `240215-F-JB191-1025.jpg` をダウンロードしてExifを確認すると、`2024年2月15日 16:47` というタイムスタンプが確認でき、問題の条件を満たしていることが分かります。
（なお、作問時に参照した画像はほぼ同時刻に撮影された[こちら](https://www.yokota.af.mil/News/Photos/igphoto/2003401188/)です）

画像において、兵士の奥には **Chilis** と描かれたトウガラシの看板が写っています。`Yokota Air base Chilis` で検索すると、 Chili's Grill & Bar という横田基地内の店舗がヒットします。この店舗をGoogle Mapsで確認すると、店舗の位置を考慮し、 `35.74180, 139.34273` 付近の運動場が撮影地であると判断できます。

OpenStreetMapで同一の地点を開き、運動場を右クリックして「地物を検索（Query Features）」をクリックすると、[recreation_ground](https://wiki.openstreetmap.org/wiki/Tag:landuse=recreation%20ground?uselang=en)タグがついている[Way 810021666](https://www.openstreetmap.org/way/810021666)が見つかります。これがFlagです。

**Diver24{810021666}**

なお、[810021665](https://www.openstreetmap.org/way/810021665)ではないのかという問い合わせが多く寄せられましたが、こちらはタグからも確認できるように、運動場を取り囲んでいる[track（競技トラック）](https://wiki.openstreetmap.org/wiki/Tag:leisure=track?uselang=en)であることから、正解の扱いにはしていなません。

本問でOpenStreetMap（OSM）の Way 番号をFlagにした理由はいくつかあります。

- 座標で指定する場合、想定しないズレが発生して解答者が戸惑う可能性があり、一意なidentifierを採用したかった。
- HEXA OSINT CTFなど、海外のOSINT CTFではOSMが利用されることが多々あり、あまり馴染みがない人にはこの機会に知ってほしい。
- OSMは各地物にタグがついており、これは外部の検索ツールなどから活用できる。そのため、形状や場所だけでなく、タグを確認する習慣を身につけてほしい。

</details>