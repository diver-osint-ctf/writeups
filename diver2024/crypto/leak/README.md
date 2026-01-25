# leak

## 問題文
先月、日本の会社で大規模なBTCの不正流出が起きた。  
流出先となっているウォレットアドレスを答えよ。  
Flag形式: `Diver24{ウォレットアドレス}`  
    
Last month, there was a large-scale unauthorized outflow of BTC from a Japanese company.  
Identify the wallet address where the outflow went.  
Flag format: `Diver24{wallet address}`  

## 難易度

easy / 100 point (211 Solves)

## 解法


<details>

<summary>クリックで表示</summary>
 
`btc leak may 2024` などとGoogleで調べると、5月31日にDMM Bitcoinが約3億ドル分のBTCの不正流出の被害に遭っていることが分かります。  
X（Twitter）で`dmm btc address`と調べると、まとめている[ポスト](https://x.com/lookonchain/status/1796789067499327649)があり、流出先となっているウォレットアドレスが記載されています。

また、このアドレスは[Binance News](https://www.binance.com/ja/square/post/2024-05-31-stolen-bitcoins-from-japanese-exchange-dmm-bitcoin-distributed-to-ten-addresses-8846900839153)など他のソースにも記載されているほか、[Whale Alert](https://whale-alert.io/transaction/bitcoin/975ec405ac9dc9fa5ab8009d94d6a1fe31dff8a8127ea90d023104e52754e4d7)からも確認できます。

**Diver24{1B6rJRfjTXwEy36SCs5zofGMmdv2kdZw7P}**

</details>
