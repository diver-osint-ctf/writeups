# diode (460pt / 73 solves)

## 問題文

Geran-4のフライトコントロールユニットに搭載されている、ショットキーバリアダイオードを製造したと思われる企業は何か。所在国・地域における法人番号（またはそれに相当する番号、最新のもの）を各国・地域の政府機関により公開されている情報から解答せよ。  
たとえば、法人番号が 123456789ABC であった場合、Flagは `Diver26{123456789ABC}` となる。

What is the corporate registration number (or its equivalent official identifier, most recent) in the home country/region of the company presumed to have manufactured the Schottky barrier diode mounted on the flight control unit of the Geran-4? Provide the number based solely on information publicly disclosed by government agencies.  
For example, if the corporate registration number is 123456789ABC, the flag should be `Diver26{123456789ABC}`.


## 解法

Geran-4 Flight control unit等と検索すると、 https://war-sanctions.gur.gov.ua/en/page-geran-4 が見つかります。Flight controller unitの中では、ショットキーバリアダイオードは https://war-sanctions.gur.gov.ua/en/components/7142 のみであり、製造者は不明です。

ただし、Google Lensで検索しただけでは、各社サービスでロゴらしき部分を検索しても完全一致する企業は見つかりません。SS54がショットキーバリアダイオードの規格であることが検索結果からわかります。

安価な攻撃用ドローンには民生品も多く用いられており、制裁の関係から、ロシア国内や中華人民共和国の製造品が多いと考えられます。さらに、このような小部品を製造・販売する企業も多いと考えられるため、中国の通販サイトで検索します。

Alibabaでは画像検索が可能であるため、この画像を直接入力して検索しますが、完全一致するものは見つかりません。また、電子部品の購入先としてよく知られるdigikeyでも不発です。
しかし、aliexpress（ aliexpress.com ）で画像検索すると、ベストマッチで3ページ目ほど（執筆当時）に、 https://ja.aliexpress.com/item/1005009053305300.html というアイテムがあります。同じロゴが掲載されていることがわかります。main land chinaで作られたことはわかりますが、メーカー名等の記載はありません。

データシートの画像が添付されているため、これをGoogle Lensで検索し、"公司"とともに検索すると、JingDao Microelectronicsが候補にあがります。実際に会社HPを確認すると、同じロゴマークであることがわかります。<img width="3750" height="1871" alt="image" src="https://github.com/user-attachments/assets/9408c689-070f-47a2-9227-82548d419307" />

また、製品一覧からショットキーバリアダイオードの一覧を開き、SS54の条件に合致するデータシートを確認すると、いくつかには実際にマークとしてSS54と入っていることがわかります。（ https://sc.sdjingdao.cn/Upload/6a60e99f-8dac-434c-91c5-eb608ba65c97_SMAF-C-S-SS52F~SS520F-5A200V-A%20Rev%202.1.pdf 等。なお、PDFのリンクに問題があるため、https:// 前の部分を削除すると正しくデータシートを開けます）。

会社名がわかったので、国家企业信用信息公示系统（ https://www.gsxt.gov.cn/index.html ）で中国語会社名「山东晶导微电子股份有限公司」を入力すると、「统一社会信用代码：91370881074437184X」とあり、Flagとなります。

Flag: **Diver26{91370881074437184X}**

なお、電子部品のパッケージは偽装や偽製品の作成が比較的容易であり、必ずしもこの会社が実際に製造した製品かは不明です。また、公開情報からは、あくまで回収されたGeran-4で使用されていたということだけが判明しており、このメーカーが流通に積極的に関与していると示唆するもの **ではない** ことに留意してください。

