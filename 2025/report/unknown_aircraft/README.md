# unknown_aircraft

## 問題文

**記述問題**  
これらは2025年5月10日 19:00UTC ごろに Flightradar24 上で確認された航空機の様子です。  
画面上で選択されている航空機（赤いアイコンの航空機）について、公開情報から分かる範囲で、調査を行って説明してください。  
記述に関する詳細は添付しているルール（PDF）を参照してください。

**Descriptive Form Challenge**  
These are the aircraft identified on Flightradar24 at 19:00UTC on 10 May 2025.  
Please investigate and describe the aircraft selected on the screen (aircraft with red icons), as far as you can tell from the publicly available information.  
See attached rules (PDF) for further information on the description.



[配布ファイル](./public)

## 難易度

hard / 300 point (1 solves)

## 解法

結論として、中国の海上プラットフォームが衝突防止のために ADS-B の信号を送出しているものだと考えられます。

### 最初に確認すること

画像から、以下のことが判断できます。

- "N" で始まるアメリカ籍の航空機が表示されている
- いくつかの航空機はコールサインと登録記号が表示されていない
- 航空機の種類はヘリコプターから小型プロペラ機、ジェット機まで様々である
- すべての航空機が海上の低高度（50ft、75ft、150ft）に存在している
- コールサインが通常の航空機とは異なる

### 本当に「航空機」なのか？

たとえば **KL61WHPD** というコールサインを発出している "N1LY" について、[AirNav Radar](https://www.airnavradar.com/data/registration/N1LY)のような航空機追跡サイトで確認してみましょう。すると、同一のコールサインで度々追跡されていることが確認できますが、どうやら同じ地点からほぼ動いておらず、航跡が表示されません。"[N1NX](https://www.airnavradar.com/data/registration/N1NX)" も同様です。

少なくともこの 2 機は機種名の表示を信じるのであれば固定翼機、つまりヘリコプター（回転翼機）ではない通常の航空機のはずです。それなら、同一の位置に留まり続ける信号が発出されるのは不自然です（ご存じの通り、通常の航空機は同じ場所に留まることが物理的に不可能です）。

加えて、その高度が 50ft や 75ft となると、海面できわめて低空飛行をした状態で位置を維持しているということになります。

これらの状況から、これらの信号は通常の航空機ではないという可能性が浮上します。

### コールサインは何を意味している？

#### KL61CEP, KL61WHPD

Flightradar24 を開いてみると、"KL61CEP" や "KL61WHPD" のような形になるコールサインはあまり見かけられません。  
中国近辺を「飛行」しているので、Baidu を使って検索してみましょう。

`KL61CEP` と検索しても何も得られませんが、`KL 61 CEP` と検索してみるとどうでしょうか。  
以下のような記事がヒットします。

```
关于划定垦利 6-1 油田 5-1 、5-2、 6-1 区块开发项目海缆施工(KL6-1CEP-KL6-1WHPB，KL6-1CEP-KL6-1WHPC)临时安全作业区的补充通告——鲁航通〔2023〕0614号
https://www.msa.gov[.]cn/page/article.do?articleId=0DAF5169-A1A6-41A4-8DC6-A194FE81A7DE
```

どうやら油田に関する記事のようで、**KL6-1CEP** や **KL6-1WHPB** という表記が確認されます。例えば `6-1 油田` で検索すると、以下のような記事がヒットします。

- [垦利 6-1 油田 (Baidu)](https://baike.baidu.com/item/%E5%9E%A6%E5%88%A96-1%E6%B2%B9%E7%94%B0/24609608)

垦利 6-1 油田は[渤海](https://en.wikipedia.org/wiki/Bohai_Sea)にあるため、この「航空機」のコールサインと一致するのは偶然ではなさそうです。また、[垦利 (Kenli) ](https://en.wikipedia.org/wiki/Kenli,_Dongying)は渤海付近に位置する地名で、**KL** は "Kenli" に由来する可能性が高いと考えてよいでしょう。

さて、これらは渤海の海上にある垦利 6-1 油田に関連するものだと分かりましたが、"CEP" "WHPB" "WHPB" は何を意味しているのでしょうか？

素直に `oil field CEP` と検索してみましょう。すると、以下の記事がヒットします。

- [Central hub sets sail for major Chinese offshore field](https://www.upstreamonline.com/field-development/central-hub-sets-sail-for-major-chinese-offshore-field/2-1-1825500)

この記事では "Kenli 10-2 CEP" が完成し、垦利の沖合に向けて出航したことが記されており、CEP が"central equipment platform"であることがわかります。

また、これらは "platform" の一種である可能性が高いことが上記の記事から分かったので、続いて `oil platform WHPB` でも Google 検索してみましょう。すると、以下のような記事がヒットします（一例）。

- [Study of Thermal Supply Mode of Floating Nuclear Power Plant in Offshore Oil and Gas Fields](https://www.researchgate.net/figure/LD-27-2-32-2-oil-fields-platform-models-from-network-resources_fig4_350302596)
- [中国海域の航行警報 No.100](https://www.piclub.or.jp/wp-content/uploads/2021/02/No.1110_%E4%B8%AD%E5%9B%BD%E6%B5%B7%E5%9F%9F%E3%81%AE%E8%88%AA%E8%A1%8C%E8%AD%A6%E5%A0%B1No.100.pdf)

どうやら "WHPB" だけでなく、 "WHPA" も存在するようです。Google 検索のクエリを色々試してみると、 "WHPC" "WHPD" も見つかるでしょう。  
ということで、`WHP` に意味がありそうです。`oil platform WHP` で Google 検索すると、 **Wellhead Platform** であるとわかります。

#### B352WHPB

こちらは何を意味するのでしょうか。先ほどの "Kenli" が "KL" になっていたことを考えると、"B" も地名の可能性が高いと言えるでしょう。  
そこで、渤海（Bohai）にあることを鑑みて、`渤海 352 WHPB` で Baidu 検索をしてみます。すると、「渤海南堡 35-2CEP/WHPB」に関する論文の情報が見つかります。

- [国内浅海规模最大平台——渤海南堡 35—2 平台组块实现主体完工](https://xueshu.baidu.com/usercenter/paper/show?paperid=71cb463ec6a9e539568c95df3b033256&site=xueshu_se) (Baidu)

これから、渤海南堡（Bohai Nanpu）35-2 WHPB を意味している可能性が高いと言えるでしょう。

#### PL193HPC

こちらも "PL" が同様に地名を意味する可能性が高いと考えられます。 `PL 193 油田` で Baidu 検索をしてみると、以下の記事がヒットします。

- [蓬莱 19-3 油田](https://baike.baidu.com/item/%E8%93%AC%E8%8E%B119-3%E6%B2%B9%E7%94%B0/8828303) (Baidu)

蓬莱（Penglai）は "PL" と略されても不自然ではないでしょう。  
ただ、"HPC" が不明ですので検索してみます。すると、以下のような記事がヒットするはずです。すなわち、WHPC を "HPC" と略していた可能性が高いといえます。

- [蓬莱 19-3 油田 WHPC 平台](https://www.chinabidding.com/bidDetail/251017079.html) (chinabidding.com)

### 海上交通のデータ

他のデータセットも参照してみます。たとえば、`KL6-1CEP` と Google 検索すると、MarineTraffic のページがヒットします。また、ここには明確に "PLATFORM" と書かれています。

https://www.marinetraffic.com/zh/ais/details/ships/shipid:8860098/mmsi:413513220/imo:0/vessel:KL6_1_CEP_PLATFORM

これを基に、MarineTraffic 上で `KL6 P` と検索すると、"WHPD" は見つかりませんが、それ以外の番号の複数のプラットフォームが「船舶」としてヒットします。

- [KL6_1_WHPG_PLATFORM](https://www.marinetraffic.com/en/ais/details/ships/shipid:8873443/mmsi:413565590/imo:0/vessel:KL6_1_WHPG_PLATFORM)
- [PL19_3WHPC](https://www.marinetraffic.com/en/ais/details/ships/shipid:9019517/mmsi:413274550/imo:0/vessel:PL19_3WHPC)

また、"B352WHPB"は少し異なる名前の "BZ 35-2 WHPB"としてヒットします。

- [BZ35_2WHPBPLATFORM](https://www.marinetraffic.com/en/ais/details/ships/shipid:8966569/mmsi:413277570/imo:0/vessel:BZ35_2WHPBPLATFORM)

マップ上でそれぞれの位置を見てみると、FR24 に登場するものとおおよそ一致していると言えるでしょう。

### なぜ米国籍の航空機の ADS-B の信号が送出されているのか？

海上プラットフォームでは、ヘリコプターを用いた物資・人員輸送が行われます。海上プラットフォームは航空管制レーダーのカバレッジ外になりやすい低空に存在しているため、衝突防止の観点から ADS-B を利用する事例がみられます。

- https://www.icao.int/NACC/Documents/Meetings/2019/ADSBOUT/ADSB-OUT-M-WP11.pdf
- https://www.icao.int/APAC/Meetings/2014%20ADSBSITF13/SP07_AUS%20-%20ADSB%20on%20offshore%20platforms.pdf

ただし、これらの例では実際に「航空機」としての信号を発信するわけではないようです。  
今回の例についてはトランスポンダのコードを見てみるとその状況が推測できます。以下の通り、機体記号が判明しているものに関してトランスポンダのコード（ModeS Code）を調べてみると、`A00xxx` というレンジに収まっています。

- N1NX: A00144
- N1FU: A00092
- N1LY: A00113
- N1WT: A00208

トランスポンダのコードにおいて、`A00000 - AFFFFF` のレンジは[アメリカ国籍の航空機に割り当てられています](https://www.aerotransport.org/html/ICAO_hex_decode.html)。そのため、実際にはあまり深いは意図なく設定されたにもかかわらず、対応する N レジ（米国籍）の航空機として FR24 で認識されたものであると考えられます。なお、FR24 上で機体記号が表示されていない PA-12 や Global 6000 についても、おそらくこのレンジに含まれているであると考えられますが、偶然[LADD 機](https://support.fr24.com/support/solutions/articles/3000117426-why-is-some-aircraft-information-limited-or-not-visible-)に合致したため、FR24 でブロックされた（非表示にされた）ようです。

実験用航空機や軍用機が無効なトランスポンダのコードを設定したり、あえて別のトランスポンダのコードを設定する例は以下で示すように、頻繁に見られるのですが、今回の例ではコールサインから素性が判明しやすいこともあり、おそらく秘匿する（or 米国籍に偽装する）意図はほぼないであろうと考えられます。

（参考例）

- [Invalid Transponder Code に関する FR24 の解説（Flightradar24 公式による解説）](https://x.com/flightradar24/status/1638988806706855936)
- [「スイスの気球」が中国上空に表示された例（作問者が発見したもの）](https://x.com/geo_vitya/status/1816921315208532451)
- [「イギリス軍の Eurofighter Typhoon」が中国上空に表示された例（作問者が発見したもの）](https://x.com/geo_vitya/status/1819697985393148114)

## 採点基準

- 航空機ではないことが証拠とともに示されていること（最大100点）
  - 高度、速度、移動していないこと。
    - 高度、速度、移動の有無のうち、2つ以上が根拠とともに記載されていれば100点を与える（ただし、高度と速度は問題画像のみを根拠としてよい）。
- 油田の海上プラットフォームであると考えられることが、何らかの証拠とともに示されていること（最大100点）
  - KL61CEP, KL61WHPD, B352WHPB, PL193HPC について、3つ以上のプラットフォームについて正体と推定されるものが示されていれば100点とする。2つであれば75点、1つであれば50点とする。
  - AISとの一致、公文書との一致など、信頼性が十分で考えられるものについてはいずれかのソースで可。
- 根拠となる事象とともに、ADS-B信号を送出している理由が示されていること（最大100点）
  - 海上における回転翼機とプラットフォームの衝突防止であることを想定の解とする。
  - これに関してその裏付けとなる情報（他のプラットフォームでの事例など）が示されていれば100点とする。示されておらず、「回転翼機とプラットフォームの衝突防止」とだけ記述されている場合は30点とする。
  - もし他に理由がある場合、信用に足る根拠が示されていれば正解とする。ただし、根拠が示されていない場合は0点とする。

証拠や根拠が示されていない場合、その項目を採点しない。もし、出題者が想定していないものの、重要である情報が分析されていた場合、100点を限度に加点を行う（例: LADD扱いになっているレジに対応するプラットフォームの正体や、それから送出されているコールサインなど）。

## 出題意図

OSINT (Open Source Intelligence) とは、本来は公開情報を検索して情報を得ることだけではなく、それを基にして分析を行い、意思決定につなげることです。CTFは競技としての形式を取ることもあり、この営みを再現することは容易ではないのですが、何らかの形でそれを取り入れたいと考えていました。

今回は実験的な取り組みとして、作問者が確証を得ることのできる（＝レポートとして採点できる）領域を題材として、CTFdのプラグインを利用して自由記述形式の問題を設定しました。

実験的ゆえにまだ至らない点も多かったのですが、今後も分野の幅を広げた上でレポート形式の問題を取り扱っていきたいと考えています。