# conflicted (311pt / 156 solves)

## 問題文

日本国内において、ソ連で設計された小型航空機が地上構造物との接触による事故を起こしたことが記録されている。  
この **構造物の位置** を地図上で示せ。

**墜落場所ではなく、構造物の場所を答えよ。**

There are recorded incidents in Japan involving small aircraft of Soviet design colliding with ground structures.  
Indicate **the location of this structure** on a map.

**Not a crash site. Indicate the location of the structure.**


## 解法

`航空事故 記録` で検索すると、日本国内で発生した航空事故は、[運輸安全委員会](https://en.wikipedia.org/wiki/Japan_Transport_Safety_Board)による報告書が存在しており、オンライン上で公開されていることがわかります。

[報告書検索](https://jtsb.mlit.go.jp/jtsb/aircraft/index.php)ページで、「キーワード検索」を使います。  
[ソ連で航空機を製造していたメーカー](https://ja.wikipedia.org/wiki/Category:%E3%82%BD%E3%83%93%E3%82%A8%E3%83%88%E9%80%A3%E9%82%A6%E3%81%AE%E8%88%AA%E7%A9%BA%E6%A9%9F%E3%83%A1%E3%83%BC%E3%82%AB%E3%83%BC)を1件ずつ入力してみると、「スホーイ」で平成15年（2003年）の事故が1件ヒットします。

> ＡＳＢ飛行連盟所属スホーイ式ＳＵ－２６型ＲＡ２８２１Ｋは、平成１５年１０月３１日（金）、栃木県芳賀郡茂木町のツインリンクもてぎ自動車レース場を会場として開催されていた航空ショーにおいて、会場内の場外離着陸場から機長のみが搭乗して離陸後、背面飛行で競技コースを飛行中、１０時３１分ごろコースを逸脱し、背面飛行の状態でコースの左側に隣接する照明塔等に衝突し、墜落した。

https://jtsb.mlit.go.jp/aircraft/rep-acci/AA2004-2-3-RA2821K.pdf

上記PDFの「付図２ 事故現場見取図」を見ると、「衝突した照明塔、信号塔及び監視小屋」という衝突箇所が示されています。  
Google Earthでツインリンクもてぎを確認すると、地図と一致する場所に構造物はまだ存在しており (36.5316888, 140.2299088) 、これが答えとなります。