# pilot (100pt / 447 solves)

## 問題文

**cx** の問題で示されたフライト中、添付画像の席に座っていた人物の名前を英語で解答してください。  
（なお、添付画像は座席を示すためのものであり、当該フライトの実際の写真ではありません）  
例えば、人物の名前が John Doe のとき、Flag は `SWIMMER{John Doe}` となります。

In the flight indicated in the **cx** challenge, answer the name of the person who was sitting in the seat shown in the attached image in English.  
(Note that the attached image is for indicating the seat and is not an actual photo of the flight.)  
For example, if the person's name is John Doe, the flag should be `SWIMMER{John Doe}`.


## 配布ファイル

- [pilot.jpg](./public/pilot.jpg)

## 解法

先程の問題で、便名が **CX8100** であると判明しました。そこで、 `CX8100 pilot` のように検索してみると、以下の記事がヒットします。

- [Geoffrey Lui ’95 – Aviation, Cathay Pacific, and Kai Tak Tribute Flight CX8100](https://cisalumniconnect.org/geoffrey-lui-95-aviation-cathay-pacific-and-kai-tak-tribute-flight-cx8100/)


この記事はChinese International Schoolという学校のOBを紹介するもので、CX8100便を操縦したGeoffrey Lui氏が取り上げられています。また、このページには「[Behind the scenes of CX8100: A Cathay Flypast to Remember 揭開幕後：國泰特別航班CX8100](https://www.youtube.com/watch?v=Fjs9AfnyuLg)」という動画が埋め込まれています。

この動画を再生してみると、1:08ごろにGeoffrey氏が登場します。また、1:33ごろにはAdrian Scott氏という人物も登場する。さらに、3:24ごろからはコクピットの様子が映し出されており、左側の座席にGeoffrey氏、右側の座席にAdrian氏が座っていることがわかります。

念の為 `CX8100 Adrian Scott` と検索すると、コクピットのシーンに "Cathay captains Geoffrey Lui and Adrian Scott" というキャプションが記載されている記事もヒットします。

- [Cathay flies over Hong Kong's former airport for nostalgic stunt](https://www.campaignasia.com/video/cathay-flies-over-hong-kongs-former-airport-for-nostalgic-stunt/501935)

これより、Flagは以下の通りとなります。

Flag: **`SWIMMER{Adrian Scott}`**