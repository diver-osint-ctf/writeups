# uploader

## 問題文

我々が追っている人物は、どこかに猫の動画を投稿しているようだ。その動画のアップロード時間を特定できないだろうか。  
Flag形式: `Diver24{投稿時刻のunix time(UTC+0)}`   
例えば、2000年1月1日 12時34分56秒(UTC+0)に投稿されている場合、`Diver24{946730096}`となります。

The person we are pursuing appears to have posted a video of a cat somewhere. Can you determine the upload time of that video?  
Flag format: `Diver24{upload time in unix time(UTC+0)}`   
For example, if the video was uploaded at 12:34:56(UTC+0) on 1st Jan 2000, the flag should be `Diver24{946730096}`.

## 難易度

medium / 500 point (2 solves)

## 解法

<details>

<summary>クリックで表示</summary>

Mapillaryと同じユーザIDを使用しているX（Twitter）から、TikTokのURLを見つけることができます。

TikTokは「あなたのアカウントをおすすめ表示」機能がONになっている状態で動画を共有した場合、その共有者のアカウント名が露出する仕様があります。スマホ(または、PCのブラウザでスマホのサイズにした状態)でURLを開くとページ上部にユーザ名が表示されます。

その結果、動画を特定できます。

[https://www.tiktok.com/@mmrrkkww0615/video/7359809566856449281](https://www.tiktok.com/@mmrrkkww0615/video/7359809566856449281)

また、TikTokは動画のIDから動画の投稿時間を算出することができます。詳しくは[この記事](https://dfir.blog/tinkering-with-tiktok-timestamps/)を参照してください。

**Diver24{1713589198}**

</details>