# bid

## 問題文
2023年、オマーンにおいて、ある施設に関連するニュースが報じられた。  
https://www.youtube.com/watch?v=TFdubskF9Kw  

その後、2024年10～11月に、この施設に関連すると推定される、井戸およびパイプラインを建設するための入札が実施された。  
このとき、3位の金額で入札した企業のCEOの名前を、Webサイトに掲載されている英語表記で答えよ。  
Flag形式: `Diver25{Kelly Ortberg}`

In 2023, news related to a facility was reported in Oman. 
https://www.youtube.com/watch?v=TFdubskF9Kw 

A tender was subsequently issued in October-November 2024 for the construction of wells and pipelines, presumably associated with this facility.
Answer the name of the CEO of the company that bid for the third highest amount in this tender.  
(In English. Also follow the format in the company's official site.)  
Flag Format: `Diver25{Kelly Ortberg}`

## 難易度

medium / 491 point (31 solves)

## 解法

ニュース動画のタイトルはアラビア語で以下のように書かれています。

> توقيع اتفاقية لإدارة وتشغيل المستشفى البيطري بمنطقة البشائر بولاية أدم.

これを Google 翻訳などを用いることで、以下のような訳文が得られます。

> Signing an agreement to manage and operate the veterinary hospital in Al-Bashir area in Adam State.
> （アダム州アルバシル地区の獣医病院の管理運営に関する協定に署名。）

しかし、日本語や英語で検索しても当該の地区を見つけるのは難しいかもしれません。特に行政区画の訳が正確ではないためです。  
そこで、アラビア語での検索を試みます。しかし、アラビア語話者ではない場合、これは容易ではないので、Google 翻訳などの力を借りましょう。

先ほどの文章から単語を削って訳したり、一部の単語だけを訳したりということを繰り返すと、**البشائر** が **Al-Bashir** を意味し、**أدم** が **Adam** を意味することがわかります。**Al-Bashir** は"Good news"と直訳されるかもしれませんが、前の単語を繋げると "Al-Bashir area" という訳が出てくるため、これが地名であるとわかるはずです。

`Adam Oman` などと検索すると、これは Ad Dakhiliyah 行政区に属する行政区画（ウィラーヤ、wilayah）であることがわかります。  
https://en.wikipedia.org/wiki/Adam,_Oman

さらに、`البشائر أدم` (Al-Bashir Adam) と検索すると、アラビア語版 Wikipedia がヒットし、Al-Bashir は Adam 内に位置する人口 75 人ほどの地域であることが分かります。

https://ar.wikipedia.org/wiki/%D8%A7%D9%84%D8%A8%D8%B4%D8%A7%D8%A6%D8%B1_(%D8%A3%D8%AF%D9%85)

このページから、さらに[アラビア語エジプト語方言版 Wikipedia](https://arz.wikipedia.org/wiki/%D8%A7%D9%84%D8%A8%D8%B4%D8%A7%D8%A6%D8%B1)に飛ぶと、[Google のナレッジグラフへのリンク](https://www.google.com/search?kgmid=/g/11cp7h3ccl)があり、 **Al-Bashair** という別の英語表記が確認できます。

これより、 `Al-Bashair Oman` で検索すると、以下のサイトがヒットし、Ad Dakhiliyah 行政区 の Adam の中にある Al-Bashair の場所が確認できます。  
https://www.citypopulation.de/en/oman/dakhiliyah/%C4%81dam/050520310__al_bashair/

近隣にはラクダの競馬場があるようで、ニュースで触れられていたように、ラクダに関する獣医病院が建設される場所としては十分合理的であると考えられます。

さて、大まかな位置関係が分かったところで、オマーンの公共入札情報を入手する方法を探します。  
素直に `Oman Tender`（オマーン　入札） と Google 検索すると、公共入札の検索サイトがヒットします。

https://etendering.tenderboard.gov.om/

Floated（公告された案件）、Opened（開札された案件）、Awarded（契約者が決まった案件）などのカテゴリが示されており、それぞれ検索可能になっています。  
英語に対応しているため、Awarded の検索ページで `veterinary hospital` と検索すると、以下の番号・タイトルを持つ入札情報が確認できます。

- Tender No. : 1190/2023/MAFWR/DGAWRDK-94- Recall - 1
- Tender Title : DRILLING WELL BORE SUPPLY& INSTALLATION OF PUMP AND PIPELINE FOR AL-BASHAYER VETERINARY HOSPITAL IN WILAYAT ADAM AT AL-DAKHLIAH GOVERNORAT

検索画面右側の View Tender Opening Status をクリックすると、入札順位を閲覧できます。3 位には **GOLDENSANDSTRANSPORTSERVICESLLC** と記載された会社が表示されています。

なぜか英語表記がスペース抜きになっているので、`GOLDEN SANDS TRANSPORT SERVICES LLC` と分割して検索すると、以下のサイトがヒットします。  
事業内容からも、掘削事業を手がけていることが確認でき、先ほど表示されていた会社のことだと考えて差し支えないでしょう。

https://goldensandsoman.com/

[会社情報のページ](https://goldensandsoman.com/about-us/)には CEO の名前が記載されています。これが Flag になります。

**Diver25{Bader Al Malki}**

### 出題意図

さまざまな国の公共データを確認してもらう練習として出題しました。参加者の多くにとってアラビア語は馴染みがないと考えられますが、翻訳ツールを使いつつ対処できるようになってほしいと考えています。
