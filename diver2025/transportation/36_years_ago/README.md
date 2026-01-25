# 36_years_ago

## 問題文

このニュース動画に映っている航空機に、1989年8月時点で割り当てられていたトランスポンダのMode Sコードを16進数表記で答えてください。  
https://www.youtube.com/watch?v=OvR2O_Vpwc0  
Flag形式: `Diver25{1234AB}`  
**content warning**: この映像は軽微な航空事故の様子を含みます。

Answer the transponder Mode S code assigned to the aircraft shown in this news video as of August 1989 in hexadecimal notation.  
https://www.youtube.com/watch?v=OvR2O_Vpwc0  
Flag Format: `Diver25{1234AB}`  
**content warning**: This video contains footage of minor aviation accident.


## 難易度

easy / 347 point (125 solves)

## 解法

与えられたニュース映像の 13 秒頃に、機体に **JA4098** と書かれている様子が確認できます。`JA4098 accident` などと Google 検索すると、[Aviation Safety Network](https://asn.flightsafety.org/wikibase/456571)の記事がヒットするほか、[JA Search](https://jasearch.info/aircraft_hist.html?r_number=JA4098)の情報もヒットします。

Aviation Safety Network の記事には、機体のシリアル番号（MSN）が **17276610** であると記載されています。また、機種は**Cessna 172P Skyhawk** と記載されています。また、JA Search には 1990 年に日本へ輸入された際、その前まで使われていた **N9768L** というアメリカ籍時代の番号が記載されています。

さて、`N9768L` で Google 検索すると、以下のようなサイトがヒットします。

https://www.aviationdb.com/Aviation/Aircraft/9/N9768L.shtm

ここに Mode S Code として `53316552` が記載されています。これは 8 進数表示であるため、16 進数に変換すると題意を満たす数値が得られます。

これより、Flag は以下の通りです。  
**Diver25{AD9D6A}**

## 出題意図

昨年に引き続き、航空機の登録履歴を遡ってもらう問題です。航空機は所有者が移転した記録が明確に残っていることが多く、時にはこれらが重要な情報源になることもあります。また、ModeSのトランスポンダコードはFlightradar24やADS-B Exchangeといった追跡サイトでも使用する値であり、こちらに慣れ親しんでもらうねらいもあります。