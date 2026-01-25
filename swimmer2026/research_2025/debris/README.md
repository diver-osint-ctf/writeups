# debris (100pt / 228 solves)

## 問題文

2025年12月8日、日本のあるテレビ番組で、高速道路のパトロール隊への密着取材の様子が放映されました。  
パトロール隊の108号車は、路上に落下していたトン袋の回収を命じられました。トン袋が最初に落下していた地点はどこでしょうか？  
マップ上で示して解答してください。

**content warning** : 交通事故の映像が含まれる映像を視聴する必要があります（人が巻き込まれるシーンはありません）。

On December 8, 2025, a Japanese TV program aired close coverage of a highway patrol unit.  
Patrol car 108 was ordered to recover a bag (トン袋, ton bukuro) that had fallen onto the roadway. Where was the bag initially dropped?  
Please answer by indicating the location on the map.

**content warning**: You will need to watch footage that includes a traffic accident (no scenes of people being hit).


## 解法


`2025年12月8日 高速道路 パトロール` でGoogle検索すると、以下の番組がヒットする。

https://www.youtube.com/watch?v=xo_2KZ3n668

番組を視聴すると、[9:43頃](https://youtu.be/xo_2KZ3n668?si=C2fd1Pz40Bb4_Haa&t=583)から当該のシーンが始まる。この番組から得られる情報を整理すると、以下の通りである。

- `上りの護国寺合流先` `音羽(町)` (10:04)
- `道路のセンターにデカいトン袋が落ちている` (10:06)
- `首都高 池袋線` `文京区` (10:28)
- `5`(5号線) と書かれた緑色の看板付近 (10:26 - 10:30)
- `FUKU...` と読める看板があるビル (10:46)
- `大宮七里眼科` と書かれた沿道の看板 (11:54)

Google Maps（3D表示）で `護国寺` `音羽町`をもとに場所を探すと、眼科の看板が見つかる。  
この付近の高速道路上をストリートビューで確認すると、「フクイン」という会社が見つかり、ビルの外観も一致する。

番組の10:59ごろでは、まさに「フクイン」（FUKUIN）のビル横に落下物（トン袋）が落下していることが確認できる。

解答フォームはOpenSteetMapを使っているため、ビル名は表示されないが `関口三丁目公園` を目印に解答できる。

Flag: **35.713272, 139.729549**　（許容誤差 50m）

（なお、上記の座標は正誤判定に用いるための設定値であり、このオーダーでの解答を要求しているものではありません。許容誤差円内に収まっていれば問題ありません。）