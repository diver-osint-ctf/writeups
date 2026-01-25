# rage (100pt / 301 solves)

## 問題文

2025年7月、メキシコシティでは住宅価格の高騰を理由とするデモが起きました。  
以下の記事URLから確認できる報道写真で破壊されている店舗がオープンした日時を、 `YYYY/MM/DD` （現地時間）の形式で解答してください。  
例えば、答えが2025年7月5日の場合、Flagは `SWIMMER{2025/07/05}` となります。  

In July 2025, a protest broke out in Mexico City over soaring housing prices.  
Using the news photo in the article below, answer the opening date (local time) of the vandalized store in `YYYY/MM/DD` format.  
For example, if the answer were July 5, 2025, the flag would be `SWIMMER{2025/07/05}`.  

**記事 / Article**: [https://www.jiji.com/jc/article?k=2025070500264&g=int&p=20250705at46S&rel=pv](https://www.jiji.com/jc/article?k=2025070500264&g=int&p=20250705at46S&rel=pv)


## 解法
写真の奥に店舗のロゴマークが映っているため、傾きを修正したうえで Google Lens に通します。このときヒットする画像を再び Google Lens にかけると、これがスケートブランドのRIPNDIPのロゴであることがわかります。  
メキシコにあるRIPNDIPの店舗はメキシコシティのRIPNDIP MEXICOのみであるとわかります。

また、機械翻訳などを利用し、「CDMX gentrificación disturbios tienda de ropa」といった言葉で検索しても、RIPNDIPの被害について報道した現地メディアの記事を見つけることができます。

次に、RIPNDIP MEXICOの開店日を特定する必要があります。「RIPNDIP MEXICO Día de apertura」といった言葉で検索すると、Instagram・Facebookなどに掲載された店舗オープン時のポスト・プレスリリースを確認することができます。


Flag: **`SWIMMER{2022/04/29}`**

## 競技中の対応について

メキシコシティのRIPNDIPは開店後、[ローマ地区に移転](https://www.instagram.com/p/C_vhevVPEA-/)しています。当初、Flagは移転前の開店日のみ対応していたのですが、移転後の日付も題意を満たすため、`SWIMMER{2024/09/14}` もFlagとして追加し、すでに送信された解答についても遡及して正解扱いにする対応を行っています。ご迷惑をおかけして申し訳ありませんでした。また、競技中のご指摘に感謝いたします。