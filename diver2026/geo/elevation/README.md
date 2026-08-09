# elevation (481pt / 51 solves)

## 問題文

Aidu風力発電所の建設が長年差し止められた原因の一つであった軍事レーダーのレドームについて、公的情報から入手可能な絶対標高（m）の最高値を示せ。データから得られた値を小数第二位まで回答すること。
例えば、東京タワーについて入手できたデータが351mだった場合、Flagは `Diver26{351.00}` である。

The construction of the Aidu wind farm in Estonia was blocked for years, partly due to a military radar. What is the highest absolute elevation (in meters) of the radome of this radar obtainable from publicly available data? Submit the value obtained from the data to two decimal places.
For example, if the available data for Tokyo Tower indicated 351 m, the flag should be `Diver26{351.00}`.


## 解法

Aidu Wind Farmと検索すると、 https://www.eleon.ee/projects/aidu-wind-farm/ などの情報が見つかります。これにより、発電所の具体的な場所を特定できます。
また、 https://news.err.ee/988416/estonian-court-prohibition-on-stay-on-aidu-wind-farm-is-valid などのニュース記事では、エストニア国防軍によって、レーダーの動作の妨げになるため、建設許可の差し止めが求められていることがわかります。
自動翻訳などを用いると、エストニア語ではAidu tuuleparkと呼ばれていることもわかります。これで検索すると国防省の記事も見つかります（ https://www.kaitseministeerium.ee/en/news/11-statements-regarding-aidu-wind-farm-which-require-correcting ）。ただし、具体的なレーダーサイト名は不明です。関連するニュースや記事で、 https://www.postimees.ee/6832159/uue-radariga-saaks-rohelise-tule-kolm-tuulearendust に掲載されている図中にはKellavere õhuseire-radarとあります。https://et.wikipedia.org/wiki/Kellavere_radarijaam を検索すると、2003年にレーダー基地が設置されていることがわかります。エストニアの公営放送の記事（ https://news.err.ee/1608933098/ida-viru-residents-want-more-details-about-new-aerial-surveillance-radar ）によれば、"An aerial surveillance radar, which is currently located in Kellavere, Lääne-Viru County, gained notoriety following a dispute between the Ministry of Defense and the Sõnajalg brothers, Andres and Oleg, who own green energy company Roheline Elekter AS."とのことであり、Kellavereのレーダーサイトが対象施設であることがわかります。

そこで、具体的な座標データを得る方法を検討します。一般に、公的機関から得られる建造物の実際の高さに関する情報は、1. 建築許可などの建設に関わる届出、2. 測量データなどの地図関連情報、3. 航空障害の情報、4. 裁判記録内の実データ部分、5. 環境アセスメント関連データが考えられます。
1. エストニアの Ehitisregister という建築許可等の情報を公開しているサイトで検索します。例えば地図を用いて探すと、建物番号 120796965 の施設であることがわかります。2003年から存在することから、レーダーサイトの設置時期と一致します。ここで、 https://livekluster.ehr.ee/ui/ehr/v1/building/120796965 上の絶対標高は174.5mとなっています。また、建設許可申請時の絶対標高は177.3mです。
2. Maa-ametという政府のジオポータルサイト（ https://geoportaal.maaamet.ee/ ）があり、その中で標高データを含む3次元点群データ（LAZ形式）やDSM、DTM（GeoTIFF形式）が公開されていることがわかります。1:2000、1:10000の当該施設を含む地域の地図番号をMaa-ametのWeb地図（ https://xgis.maaamet.ee/xgis2/page/app/maainfo ）から探し（ 551644 と64541）、ダウンロードします。そのうえで、何らかの方法でレドームの位置のポイントデータやDSMデータを読み取ります。なお、DSMの場合、斜め方向に補正されている可能性がある点に十分注意が必要です。
例えば、QGIS上でデータを読み込み、投影座標系を適切に設定してレドームの位置をクリップし、標高を調べます。すると、2009～2022年の3次元点群データにのみ、レドームの絶対標高の実測値が入っていることがわかります（他ではマスキングされているか、地表面の標高のみが入っているため、周辺と高さのずれがありません）。各年のデータを比較すると、2013年の178.02mが最高値であることがわかります。
なお、例えば、https://geoportaal.maaamet.ee/est/ruumiandmed/korgusandmed/aerolaserskaneerimise-korguspunktid/als-ii-ring-20122015-p626.html にあるように、過去のデータは現在のエストニアにおける鉛直座標系のデータに変換されており、データ内のZ値を回答して差し支えありません。
また、測定誤差については、公的情報から直接入手できるデータの組合せによって明確に除去できるものではないと考えられるため、運営としては想定していません。
3. レーダーサイト内の電波塔については高さ情報があります（ https://aim.eans.ee/en/obstacles ）が、レーダーに関する情報は特にないため、データは得られません。
このほかに公的に公開されている情報（例えば裁判記録）等からは、レドームの絶対標高はわかりません。
4. エストニアの裁判所で Aidu tuulepark についての裁判資料を検索しても、特段、絶対標高の実データに関わるものは見つかりません。
5. 環境アセスメント等に関する情報でも、特段、絶対標高の実データに関わるものは見つかりません。

よって、最高値は178.02となります。

Flag: **Diver26{178.02}**

### フラグミスの原因とお詫び

本問題については、運営チームの作問・レビュー時に参照すべきデータの中で2013年次のデータ見落としがあり、正答とすべきflagを誤っていました。申し訳ございません。
検証を行い、根拠を示してお問い合わせいただいた参加者にはお礼申し上げます。お問い合わせと並行して確認し、問題を修正することができました。
また、いくつかのチームから指摘があったように、問題文の構成については、根拠ある回答を判別するために、より正確を期する方法があったと考えており、いただいたご意見を含めて、今後の改善につなげたいと考えております。

