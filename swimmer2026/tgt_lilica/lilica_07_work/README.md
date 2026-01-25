# lilica_07_work (168pt / 206 solves)

## 問題文

`lilica` は、Xとは別のSNSにもアカウントを所持しているようです。  
このアカウントの情報から職場の最寄り駅として推定されるものを、**東京メトロの駅名** で解答してください。  
例えば、推定される職場の最寄り駅が `新宿三丁目駅` の場合、Flagは `SWIMMER{新宿三丁目}` となります。

`lilica` seems to have an account on another social network.  
From that account, infer their workplace's nearest station and answer using the **Tokyo Metro station name**.  
For example, if the nearest station is `新宿三丁目駅` (Shinjuku-sanchome), the flag would be `SWIMMER{新宿三丁目}`.


## 解法

Instagram を `Nanaogi Shiharu` で検索してみると、 `nanaogi_shiharu` というアカウントが存在していることがわかります。

`nanaogi_shiharu` の投稿を確認すると、 `#中目黒` というハッシュタグとともに、職場付近の様子を投稿していることがわかります。  
また、Google Lensでこれらの画像を確認すると、実際に中目黒駅近辺のものであることも確認できます。

Flag: **`SWIMMER{中目黒}`**