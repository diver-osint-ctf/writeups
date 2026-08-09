# dx (162pt / 208 solves)

## 問題文

2026年2～3月、グリッド `31FEV` の中に存在する陸地でイベントが実施されたようだ。  
このイベントに関して利用された船舶が、最後に停泊していた港を地図で示せ。  
もし、いま現在も船舶がどこかの港に停泊していることが確認できる場合、その港を示せ。

It appears that an event took place on land within grid `31FEV` between February and March 2026.  
Indicate on the map the last port where the vessel used for this event stayed.
If the vessel can currently be confirmed to be staying at a port, indicate that port.


## 解法

まず、`31FEV` という「グリッド」とは何でしょうか。「陸地がある」ということから、地理空間情報システムにおけるグリッドを指していると考えられます。

`geospatial grid system` などで検索すると、以下のような情報が得られるはずです。  
https://en.wikipedia.org/wiki/Category:Geographic_coordinate_systems

この中にある **MGRS**（Military Grid Reference System）が `31FEV` という記法と一致していることがわかります。
また、LLMを用いても、MGRSに関する情報は容易に得られ、事実の確認も容易です。

さて、MGRSを用いて `31FEV` というグリッドがどこであるかを確認します。`MGRS map` などで検索すると、[Web上でMGRSのグリッドを重ねた地図が閲覧できるサービス](https://mappingsupport.com/p2/gissurfer.php?center=14SQH05239974&zoom=4&basemap=USA_basemap)がヒットします。
地図を見ると、ここにはブーベ島（Bouvet Island）という島があることが確認できます。

`Bouvet Island 2026` といった検索ワードでGoogle検索すると、"Bouvet Island DXpedition 2026 (3Y0K)" というイベントが実施されていたことがわかります。

- https://3y0k.com/

これは[遠距離無線通信 (DX)](https://en.wikipedia.org/wiki/DXing)を行う、アマチュア無線の[DXペディション](https://en.wikipedia.org/wiki/DX-pedition)です。

`3Y0K vessel` といった検索ワードでGoogle検索すると、"ARGUS" という砕氷船が利用された事がわかります。

- https://www.n0un.net/3y0k-vessel-docked-in-south-africa/
- https://www.classic-charters.com/classic-yacht/icebreaker-argus/

船舶追跡サイトを用いて、船舶の"ARGUS"を検索すると、CTF開催時点ではレイキャビクのとある港湾に停泊していることがわかるようになっていました。
現在は移動していますが、遡って確認することができます。

https://www.vesselfinder.com/?imo=7104752
