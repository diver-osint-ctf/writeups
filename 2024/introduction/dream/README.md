# dream

## 問題文
画像に写っているパイプオルガンがある施設の郵便番号を答えなさい。  
Flag形式: `Diver24{123-4567}`

Give the postal code of the facility with the pipe organ shown in the image.  
Flag format: `Diver24{123-4567}`

![](dream.JPG)

## 難易度
introduction / 100 point (255 solves)

## 解法

<details>

<summary>クリックで表示</summary>

OSINT CTF問題の基本中の基本である、Reverse Image Searchを行う問題です。

Google Lensで検索を行うと、パイプオルガンが設置されている施設が「ポップタウン住道オペラパーク」とわかります。

[Google Maps](https://www.google.com/maps/place/%E3%83%9D%E3%83%83%E3%83%97%E3%82%BF%E3%82%A6%E3%83%B3%E4%BD%8F%E9%81%93+%E3%82%AA%E3%83%9A%E3%83%A9%E3%83%91%E3%83%BC%E3%82%AF/@34.708894,135.6175468,16z/data=!3m1!5s0x60011f8cc0f0ca51:0xa230d50ab74aaba0!4m14!1m7!3m6!1s0x60011ff3344295cf:0x37c142a6743fa2e4!2z44Od44OD44OX44K_44Km44Oz5L2P6YGTIOOCquODmuODqeODkeODvOOCrw!8m2!3d34.708894!4d135.6201217!16s%2Fg%2F121cs0w0!3m5!1s0x60011ff3344295cf:0x37c142a6743fa2e4!8m2!3d34.708894!4d135.6201217!16s%2Fg%2F121cs0w0?entry=ttu)あるいは[公式サイト](https://www.pop-town.net/)に記載されている郵便番号がFlagとなります。

**Diver24{574-0046}**

</details>