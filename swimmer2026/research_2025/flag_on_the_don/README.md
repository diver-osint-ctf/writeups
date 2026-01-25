# flag_on_the_don (100pt / 345 solves)

## 問題文

2025年8月28日、群馬県で「太鼓の達人」を利用したイベントが開催されました。  
その会場となった建物はどこでしょうか。 **OpenStreetMapのウェイ（way）番号で解答してください** 。  
例えば、建物が `123456789` というway番号であれば、Flagは `SWIMMER{123456789}` となります。

On August 28th 2025, an event using "Taiko no Tatsujin" (太鼓の達人) was held in Gunma Prefecture.  
What is the building where the venue was held?  **Please answer with the way number of OpenStreetMap** .  
For example, if the building's way number is `123456789`, the Flag should be `SWIMMER{123456789}`.


## 解法

そのまま `2025年8月28日 太鼓の達人 群馬県 イベント` などとGoogle検索してみましょう。

すると、以下のような記事がヒットし、**渋川市** の **市民会館** で高齢者向けのイベントが開催されたことがわかります。

- [高齢者向けｅスポーツ大会開催　群馬県渋川市〔地域〕](https://www.jiji.com/jc/article?k=2025082800855)
- [令和7年7月第4回市長定例記者会見](https://www.city.shibukawa.lg.jp/manage/contents/upload/68870b94eeb0d.pdf)

この市民会館について調べてみると、 **渋川市民会館** という名称でGoogle Mapsに登録されています。  
Google Mapsで表示してみると、座標は 36.494644, 138.993126 付近です。OpenStreetMapを開き、こちらの座標を検索してみましょう。

すると、Google Mapsと一致する場所に市民会館の建物があることがわかります。  
右クリックして「地物を検索」をクリックし、渋川市民会館と書かれた建物をクリックすると、以下の情報が得られます。

- [ウェイ: 渋川市民会館 (628293186)](https://www.openstreetmap.org/way/628293186)

Flag: **`SWIMMER{628293186}`**