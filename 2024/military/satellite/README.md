# satellite

## 問題文

2023年11月、北朝鮮が偵察衛星を打ち上げた。2024-06-07T05:01:07Z時点で、この衛星から最も近い位置にあった軍用飛行場はどこか。  
また、その時点の衛星の高度（単位:キロメートル）はいくつか。  
Flag形式: `Diver24{基地名_高度}`

解答に際しては、 **2024-06-06T04:41:45.620Z** に発行されたデータを用いよ。

基地名はGoogle MapsやWikipediaで確認できる **現地語表記** で答えよ。また、高度は小数点以下を切り捨てた値を答えよ。  
例えば、トルコのインジルリク空軍基地が最も近い位置で、その際の高度が613.65kmであった場合、flagは `Diver24{İncirlik Hava Üssü_613}` となる。

In November 2023, North Korea launched a reconnaissance satellite. At 2024-06-07T05:01:07Z, which military airfield was closest to this satellite?  
Also, what is the altitude (unit: kilometer) of this satellite at that time.  
Flag format: `Diver24{airbase name_altitude}`

In answering the challenge, use the data which is issued at **2024-06-06T04:41:45.620Z**.

The airbase name should be answered with the **local language name** which can be seen on Google Maps or Wikipedia. For altitude, answer the value rounded down to the nearest whole number.  
For example, if the Inzilik Air Base in Turkey is the closest position and the altitude at that time is 613.65 km, the flag should be `Diver24{İncirlik Hava Üssü_613}`.

### Hint

- 民間の空港や飛行場ではない / Not a civil airport or airfield

## 難易度
hard / 489 point (18 solves)

## 解法

<details>

<summary>クリックで表示</summary>

まずは人工衛星の名称を特定しましょう。

問題文の情報、`North Korea Reconnaissance Satellite 2023 November` と検索すると、[38 Northの記事](https://www.38north.org/2023/11/modest-beginnings-north-korea-launches-its-first-reconnaissance-satellite/)などがヒットします。このような情報から、衛星の名称が Malligyong-1 （万里鏡1号）であることが分かります。

続いて、この衛星について検索すると、[Wikipedia](https://en.wikipedia.org/wiki/Malligyong-1)や報道などから、この人工衛星の国際標識番号（COSPAR ID）が`2023-179A`、衛星カタログ番号（Satellite Catalog Number）が`58400`であると分かります。 

続いて、「この衛星から最も近い位置にあった軍用飛行場」を求めるには、人工衛星の位置を特定する必要があります。そのためには衛星の軌道計算方法を確認しましょう。  
`人工衛星　軌道計算` と検索すると、様々なサイトや論文がヒットします。以下はその一例です。

- [人工衛星の高精度軌道計算](https://stage.tksc.jaxa.jp/taurus/member/miyazaki/old/publication/B_2013_masafumi_morimoto.pdf) 
- [Pythonを使って人工衛星の軌道を表現する～軌道６要素、TLE～](https://sorabatake.jp/23655/)

ここから、人工衛星にはTLE（Two-line elements、2行軌道要素形式）と称される軌道要素のフォーマットが存在することがわかります。

`TLE database` で検索すると、NORADが管理しているCelesTrakがヒットします。
https://celestrak.org/NORAD/elements/

現在アクティブな人工衛星のTLE一覧は、CelesTrakの"Active Satellites"から表示できます。
https://celestrak.org/NORAD/elements/gp.php?GROUP=active&FORMAT=tle

先ほど確認したCOSPAR IDやSatellite Catalog Numberで検索すると、以下のような形式でTLEが見つかります。衛星名も一致していることがわかります。

```
MALLIGYONG-1            
1 58400U 23179A   24164.24788005  .00007135  00000+0  32465-3 0  9998
2 58400  97.4040  51.1823 0001996 152.6365 207.4976 15.21013721 30973
```

しかし、注意してほしいのは衛星の軌道は変化するということです。宇宙空間といえども低軌道の衛星は空気抵抗を受けているほか、人為的に軌道変更が実施されることもあります。そのため、衛星の軌道データは更新されるものであると理解する必要があります。

TLEに何が書いてあるかを調べると、上記で `24164.24788005` と書かれている部分はエポック（epoch）であり、いわゆるタイムスタンプに相当するものであるとわかります（参考：[JAXAの資料](https://gportal.jaxa.jp/gpr/assets/mng_upload/GCOM-W/TLE.pdf)）。  
これは1月1日からの経過日・時間なので自力でも計算できますが、便利なツールを探してもよいでしょう。 `TLE epoch to utc` などで計算すると、[まさにそのためのツール](https://mason.gmu.edu/~mlyons3/tle_epoch.html)がヒットします。  
たとえば上記の例 `24164.24788005` は 2024-06-12T05:56:56.836Z を意味することになり、問題文で示された以下の条件に一致しません。

> 解答に際しては、 **2024-06-06T04:41:45.620Z** に発行されたデータを用いよ。

先ほどのCelesTrakで示されているのはアクセス時点の最新データです。
そこで、`satellite TLE past` などといったワードで過去のTLEが取得できないか探します。
すると、[StackOverFlow](https://space.stackexchange.com/questions/26290/obtain-archived-tle-data)の投稿などがヒットし、[space-track.org](https://www.space-track.org/auth/login)というサイトの存在がわかります。

要ログインですが、このサイトで過去のTLEを入手できます。Malligyong-1は以下のURLの通りです。

https://www.space-track.org/basicspacedata/query/class/tle/NORAD_CAT_ID/58400/orderby/epoch/format/3le

CTF開催日は日本時間で6月8日～9日でしたので、最下部のいくつかを調べるとエポックが `24158.19566690` になっているものが `2024-06-06T04:41:45.620Z` を示しているとわかり、このTLEデータを計算に利用します。

```
MALLIGYONG-1
1 58400U 23179A   24158.19566690  .00000871  00000-0  41535-4 0  9999
2 58400  97.4052  45.2326 0002221 305.1745  54.9283 15.21704003 30052
```

Pythonの[Pyorbital](https://pyorbital.readthedocs.io/en/latest/)や[Skyfield](https://rhodesmill.org/skyfield/)といったライブラリで軌道を計算できます。以下はその例です。

```py
from pyorbital.orbital import Orbital
from datetime import datetime

tle_line1 = "1 58400U 23179A   24158.19566690  .00000871  00000-0  41535-4 0  9999"
tle_line2 = "2 58400  97.4052  45.2326 0002221 305.1745  54.9283 15.21704003 30052"

orb = Orbital("MALLIGYONG-1 ", line1=tle_line1, line2=tle_line2)

date_time = datetime(2024, 6, 7, 5, 1, 7)

lng, lat, alt = orb.get_lonlatalt(date_time)

print(str(lat) + ','+ str(lng))
print(str(alt) + 'km')
```

ライブラリによってわずかな差があるが、アメリカ合衆国にある `31.4519,-100.6058` 付近の座標と、`506` km という高度が得られます。
Google Mapsで最寄りの空軍基地を確認すると、約20kmほど離れた場所にアメリカ空軍の `Scott Air Force Base` が確認できます。

**Diver24{Goodfellow Air Force Base_506}**

本問題は以下の報道に着想を得ています。当初、北朝鮮の偵察衛星開発・運用能力には疑問が持たれていましたが、軌道の変化を観測することにより、制御・運用が実施されていることがわかったというものです。

[北朝鮮の偵察衛星に制御能力、日韓上空を安定周回…軌道データ解析](https://www.yomiuri.co.jp/politics/20240310-OYT1T50148/)（読売新聞）

「偵察衛星の軌道情報」と聞くと、そんなものが一般人にわかるわけないと思われるかもしれませんが、このように公開データから一定の分析が可能であるわけです。  

なお、[Malligyong-1はこの出題の数日前に軌道変更を実施している](https://twitter.com/TMU_SSL/status/1798890882189705693)ため、古いデータを用いて計算を行った場合、位置が合わなかったのではと思われます。

</details>