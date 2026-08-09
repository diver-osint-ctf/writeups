# container (100pt / 463 solves)

## 問題文

この黄色いコンテナを最近まで運んでいた船のIMO番号を答えよ。  
例えば、IMO番号が1234567だった場合、Flagは `Diver26{1234567}` となる。

Answer the IMO number of the ship that was transporting this yellow container until recently.  
For example, if the IMO number were 1234567, the flag should be `Diver26{1234567}`.


## 配布ファイル

- [container.jpg](./public/container.jpg)

## 解法

拡大してみると、コンテナには `MSMU1452969` という番号が記載されています。  
Googleで `Container tracking` などと検索し、追跡サイトに入力すると、大阪からロンドンに輸送された記録が残っていることがわかります。

https://www.msc.com/ja/track-a-shipment

大阪～釜山はJULIE、釜山～寧波はMSC RAYA、寧波～ル・アーヴルはMSC ROME、ル・アーヴル～ロンドンはMSC BENINという船に搭載されたことが記録されており、題意を満たすのはMSC BENINです。この船舶名で検索すると以下のページがヒットします。

https://www.marinetraffic.com/en/ais/details/ships/shipid:9542393/mmsi:636025252/imo:9974565/vessel:MSC%20BENIN

Flag: **Diver26{9974565}**