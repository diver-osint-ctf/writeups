# sunny_saturday (436pt / 91 solves)

## 問題文

映像 / Video: https://www.youtube.com/watch?v=XNHPGva-RCQ  

この映像はある晴れた土曜日に撮影された。撮影した日時として考えられるものをYYYY-MM-DD_HH:mm形式（現地時間）で解答せよ。  
例えば、現地時間の2022年7月25日18時47分に撮影された場合、flagは `Diver26{2022-07-25_18:47}` となる。  

なお、時刻については3分までの誤差を許容している。正答が18時47分である場合、18時45分や18時50分も正解Flagとして設定されている。  
**24時間表記で解答せよ**。

This video was filmed on a clear Saturday. Answer with a possible date and time of filming in `YYYY-MM-DD_HH:mm` format (in local time).  
For example, if it was filmed at 18:47 local time on July 25, 2022, the flag should be `Diver26{2022-07-25_18:47}`.

Note that a margin of error of up to 3 minutes is allowed for the time. If the correct answer is 18:47, then 18:45 or 18:50 are also accepted as correct flags.  

**Use a [24-hour clock](https://en.wikipedia.org/wiki/24-hour_clock) (like 18:00) instead of a 12-hour clock (like 6:00pm)**


## 解法

Google LensでReverse Image Searchを行うと、撮影地が東京都中央区の銀座エリアにある[数寄屋橋交差点](https://www.city.chuo.lg.jp/miryoku/imamukashi/sukiyabashi.html)であることがわかります。

冒頭で映っている[Ginza Sony Park](https://ja.wikipedia.org/wiki/Ginza_Sony_Park)に "100 80 60" と掲示されています。検索すると、「[100.80.60.展](https://www.ginzasonypark.com/activity/022/)」のものであるとわかり、映像が2026年に撮影されたものだと確定できます。

0:06 ごろ、高速道路（KK線）上に人が複数人立っていることに着目します。`ginza highway pedestrian 2026` といったワードで検索すると、以下のような記事がヒットし、"Roof Park Fest & Walk 2026" というイベントが2026年4月25日（土）・4月26日（日）に開催されたことがわかります。

- [Former Expressway Turning into Sky Park in Tokyo’s Glitzy Ginza](https://www.english.metro.tokyo.lg.jp/w/000-101-009894)

このうち、土曜日の条件に合致するのは2026年4月25日です。

0:08ごろに時計が映っており、16:15であると判断できます（明るさから早朝4時でないことは判断でき、イベント開催時間からも判断できます）。

Flag: **Diver26{2026-04-25_16:15}**