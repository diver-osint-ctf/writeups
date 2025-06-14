# listen

## 問題文

音声 / Audio:  
https://drive.google.com/file/d/1s_HC_S_9szbkupw9jQo4Zsvkoj73Qd_6/view?usp=sharing

この航空管制のやり取りが録音された空港のICAOコード（4レターコード）を答えよ。  
Flag形式: `Diver25{RJTT}`

Answer the ICAO 4 letter code of the airport where this air traffic control communication was recorded.  
Flag Format: `Diver25{RJTT}`


## ヒント

1. 音声の冒頭は無音です / The beginning of the audio is silent.

## 難易度

medium / 473 point (53 solves)

## 解法

英語で行われた航空管制のデータが与えられるため、[transcribe.mov](https://app.transcribe.mov/)のような音声書き起こしツールに読み込ませます。無線の録音ゆえに音質が悪く、専門用語も含まれるため、不慣れな場合は全てを正確に聞き取るのは難しいかもしれませんが、少なくとも以下のような情報は AI ツールによって書き起こせるはずです。

```
[1:43] contact departure 133.65
[1:48] cleared for takeoff from runway 30
[2:36] contact with ground 21.7
[3:03] Air Canada 248
[3:50] Porter 289
[4:45] cleared to land runway 02
```

**Air Canada 248** および **Porter 289** は便名であると推測できます。前者は文字通り[エアカナダの AC248 便](https://ja.flightaware.com/live/flight/ACA248)です。後者は `Porter callsign` で Google 検索すると、[Porter Airlines](https://en.wikipedia.org/wiki/Porter_Airlines)の情報がヒットし、同社の[PD289 便](https://www.flightaware.com/live/flight/POE289)であると分かります。

AC248 便はバンクーバー（YVR）発エドモントン（YEG）行き、PD289 便はオタワ（YOW）発エドモントン行きです。そのため、この航空管制はこれら 2 つの便が到着した **エドモントン**（エドモントン国際空港）である可能性が高いといえます。

`Edmonton airport frequency` などと Google 検索し、エドモントン国際空港の周波数を確認してみましょう。[LiveATC](https://www.liveatc.net/search/?icao=cyeg) などがヒットし、Departure が **133.65**、Ground が **121.7** (省略して 21.7) であることが分かります。これは管制記録で言及されている周波数と一致します。

また、[Google Maps などでエドモントン国際空港の衛星画像](https://maps.app.goo.gl/DRKEMyUNnmewgbtc8)を確認すると、滑走路は **02/20**, **12/30** の 2 本が存在しており、管制記録にある `runway 30` `runway 02`といったやり取りとも一致します。

これより、Flag は以下の通り、エドモントン国際空港の ICAO コードとなります。

**Diver25{CYEG}**

audio data source: LiveATC CYEG-Del-Gnd-Misc-Jan-18-2025-0500Z

## 出題意図

近年は航空事故やトラブルが発生した際、LiveATCを公開情報源として管制のやり取りを分析する調査報道の事例が多く見られます。  
日本国内の航空無線に関しては、自ら音声をLiveATCへ投稿することは電波法に違反する可能性があるものの、少なくとも諸外国の空港に関して投稿されている音声データをWeb上から聴取することには問題ないため、ソースとして覚えておいて損はありません。

- 参考記事
  - [JAL機炎上、そのとき何が 検証・羽田空港衝突事故 - 日本経済新聞](https://vdata.nikkei.com/newsgraphics/haneda-runway-collision/)
  - [American Airlines plane narrowly avoids crashing into Hawaii mountain range - NEW YORK POST](https://nypost.com/2024/11/15/us-news/american-airlines-plane-avoids-crashing-into-hawaii-mountain-range/)
  - ['Thought we were going to die': United Airlines jet makes emergency landing after flames break out in engine - ABC News](https://abcnews.go.com/US/thought-die-united-airlines-jet-makes-emergency-landing/story?id=107880210)

また、オンライン上で拡散する偽情報には、「もっともらしい音声」を付けて信憑性を高めようとするものの、内容は全く異なるものというケースも見られます。確かに音質が悪く、専門用語を含む音声は聞き取りづらく、キャプションが付けられてしまえば「そうなのか」と思ってしまいがちです。しかし、今回のようにツールの力を借りつつ丁寧に分析すれば、ある程度その音声データの素性を見抜くことも不可能ではありません。