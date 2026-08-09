# trot (491pt / 35 solves)

## 問題文

Website: https://www.reddit.com/r/Awww/comments/1kej10n/is_that_a_mini_schnauzer/

かわいい小犬が彫刻の前を駆け抜けていった。この彫刻の作者をラテン文字表記で答えよ。  
例えば、Leonardo da Vinciが作者の場合、Flagは `Diver26{Leonardo da Vinci}` となる。

A cute puppy trotted past the sculpture. Answer the name of the sculpture's creator in Latin characters.
For example, if the creator is Leonardo da Vinci, the flag should be `Diver26{Leonardo da Vinci}`.


## 解法
動画には車と、薬局らしき建物が映っています。建物の看板が Ph で始まっていることから、英語圏またはフランス語圏にある可能性が考えられます。周囲の建物に掲げられた看板は英語らしく見えず、街並みや歩行者の様子も踏まえると、ヨーロッパのフランス語圏である可能性が高いと推測できます。  

映っている車のナンバープレートには、EU加盟国のナンバープレートで一般的に見られる左端の青い帯がありません。ヨーロッパのフランス語圏にあり、EUに加盟していない国や地域としては、スイス、アンドラ、モナコなどが候補となります。

動画内のナンバープレートは文字数が比較的少なく見えるため、スイスの可能性は低いと考えられます。アンドラおよびモナコのナンバープレートと比較すると、プレート左側にモナコの国章らしき意匠が微かに確認できます。

一方、動画に映る場所は開けた平坦な広場であり、急峻な地形の多いモナコ中心部とは周辺環境が一致しにくいです。このため、モナコの車両が往来しやすい南フランスの近隣都市、特にニースやカンヌ周辺が候補として考えられます。  

Google map上でニースやカンヌの薬局を `Pharmacie` という語で検索し、店舗外観を順に比較したところ、動画に映る薬局はニースの [Pharmacie du Palais](https://maps.app.goo.gl/N4XNE9KBfAWHCNCF9) と一致しました。Ph で始まる店舗名は候補を絞り込みやすく、ストリートビューとの照合によって場所を特定できます。  

Google mapの航空写真を確認すると、撮影場所付近に "L'Oulivié" というモニュメントがあることが確認できます。これを参考に動画を見直すと、0:06付近で犬を散歩させる人が白い直方体のような構造物の前を横切っていることを確認でき、これが"L'Oulivié"の台座であることもわかります。

さらに検索すると、[地元のニュースサイト](https://www.lebonbon.fr/nice/news/oulivie-nouvelle-sculpture-remplace-fontaine-place-palais-de-justice-nice/)の記事から彫刻の作者がLaurent Bosioであることがわかります。

Flag: **Diver26{Laurent Bosio}**
