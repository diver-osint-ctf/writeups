# next_train

## 問題文

この音声が録音された駅はどこか。駅名を答えよ（日本語でも英語でも可）。  
（駅名は鉄道会社の公式サイトやWikipediaに記載されている表記とする）  
Flag形式: `Diver25{京都駅}`

Which station was this sound recorded at? Answer the name of the station.  
(The station name should be as it appears on the official website of the railway company or on Wikipedia.)  
Either Japanese or English are okay.  
Flag Format: `Diver25{Kyoto Station}`



[配布ファイル](./public)

## 難易度

easy / 100 point (245 solves)

## 解法

音声を聞いてみると、後半で以下のように聞き取れます。

> 本日も JR 東日本をご利用くださいまして、ありがとうございます。こんどの 15 番線の電車は 14 時 16 分発 普通 久里浜行きです。
> Thank you for riding with JE East. The next departure from track number 15 will be 2:16pm a local train bound for Kurihama.

検索すると、JR 東日本の「[久里浜駅](https://en.wikipedia.org/wiki/Kurihama_Station)」は横須賀線にあると分かります。ただし、"bound for Kurihama" と言っているように、「久里浜行き」の列車が案内されているということは、ここは久里浜ではありません。[横須賀線の駅](https://en.wikipedia.org/wiki/Yokosuka_Line)のうち、15 番線から列車が発車するのは品川駅だけであるとわかります。

また、録音された曜日は不明ですが、少なくとも CTF 開催時には 14 時 16 分の久里浜行きが存在していることが時刻表からも確認できます。

https://ekitan.com/timetable/railway/line-station/164-2/d1

**Diver25{品川駅}**

## 出題意図

画像データから場所が分かることはジオロケーションの定番ですが、音声データからも場所を特定することにトライしてもらうために出題しました。看板が写り込むと場所が特定しやすいのと同様に、音声情報からも地名や社名があれば特定できることがあります。