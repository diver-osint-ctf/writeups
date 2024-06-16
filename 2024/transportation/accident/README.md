# accident

## 問題文

画像に映るバスと似たような車の観光バスが2023年に起こした事故の時刻と場所を探してください。  
Flag形式は `Diver24{時刻_場所}` です。

- 時刻: `2000-01-23 01:23:45`のような形式で、3秒の誤差が許容されます（現地時間）。
- 場所: `40.689N74.044E`のような形式で、小数第四位を切り捨てて表してください。

なお、時刻はバスが事故を起こしてから完全に停止した時刻を指します。  
Flag例:  
`Diver24{2000-01-23 01:23:45_40.689N74.044E}`  
**注意**: この問題には交通事故に関連する情報が含まれています。

Find the time and location of the accident in 2023 caused by a tourist bus similar to the bus model shown in the image.  
Flag format is `Diver24{Time_Location}` .

- Time: it is in the form `2000-01-23 01:23:45` with a margin of error of 3 seconds allowed (local time). 
- Location: it is in the form `40.689N74.044E`, rounded down to the fourth decimal place.

Note that the time refers to the time when the bus comes to a complete stop after the accident.  
Flag example:  
`Diver24{2000-01-23 01:23:45_40.689N74.044E}`  
**Warning**: This challenge contains information relating to road accidents.

## 難易度

medium / 471 point (28 solves)

## 解法

<details>

<summary>クリックで表示</summary>

まず、この問題ではGoogle検索の際に利用する言語設定を繁体字-台湾にする必要があります。必須ではありませんが、関係のない情報が大量に出てきてしまうのであまりお勧めしません。  

次にGoogle Lensでバスに焦点を当てて検索すると、[Youtubeの動画](https://youtu.be/viGlAeZcX6k?t=10)が見つかります。その動画に時刻が載っています。動画の概要欄の[リンク](https://www.wowtchout.com/video/6982de00-933c-404e-934e-3ce17727e10c)に座標が載っていますが、これは正確な場所ではありません。そのため、Google Mapsを用いて映像を確認しながら正確な座標を調整します。

**Diver24{2023-10-21 09:43:03_23.703N120.603E}**

</details>