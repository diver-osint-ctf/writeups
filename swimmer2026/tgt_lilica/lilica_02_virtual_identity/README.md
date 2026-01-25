# lilica_02_virtual_identity (100pt / 338 solves)

## 問題文

`lilica` はVRにも関心があるようで、未来でもVR関連の活動がわずかながら確認されています。  
`lilica` が2026年時点で使っていたVRChatのユーザーIDを特定し、解答してください。

VRChatのユーザー情報はブラウザからも確認できます。  
例えば、対象アカウントのURLが `https://vrchat.com/home/user/usr_xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx` の場合、
Flagは `SWIMMER{usr_xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx}` となります。

`lilica` is also interested in VR, and some activity has been observed in the future.  
Please answer the VRChat user ID which `lilica` was using as of 2026.

VRChat user info can be viewed in a browser.  
For example, if the account URL were `https://vrchat.com/home/user/usr_xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx`,
the flag would be `SWIMMER{usr_xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx}`.


## 解法

VRChatのWebサイトにログインし、検索欄に `黄昏ブロッサムリリカ` と入力します。

- https://vrchat.com/home/search/users/%E9%BB%84%E6%98%8F%E3%83%96%E3%83%AD%E3%83%83%E3%82%B5%E3%83%A0%E3%83%AA%E3%83%AA%E3%82%AB

すると、以下のユーザーがヒットします。

- https://vrchat.com/home/user/usr_b103fac6-8341-4b89-a606-920092e75e43

Flag: **`SWIMMER{usr_b103fac6-8341-4b89-a606-920092e75e43}`**
