# island

## 問題文

「四方ぎり島」という名前の島における、最高地点の標高を整数（メートル）で答えよ。  
Answer the highest elevation of the island named "四方ぎり島" in integer and metric.  
Flag例 / Flag example: `Diver24{3776}`

## 難易度

medium / 479 point (24 solves)

## 解法

<details>

<summary>クリックで表示</summary>

作問時・CTF開催時には単にGoogle検索をしても有益な結果は得られませんでした。

そこで、引用符を付けて検索すると、[南極地名委員会](https://nipr.repo.nii.ac.jp/record/8622/files/KJ00000139872.pdf)や[国土地理院](https://www.gsi.go.jp/common/000054629.pdf)のWebサイトがヒットし、「四方ぎり島（よもぎりじま, Yomogiri Zima/Jima）」は南極に存在することがわかります。

この英語表記 "Yomogiri Zima (Jima)" を使って検索すると、[Marine Regions · Yomogiri Zima (Island)](https://www.marineregions.org/gazetteer.php?p=details&id=10095)というサイトがヒットします。ここからも、名称が日本語由来であることも確認できる。

南極の各地点の標高が記された精緻な地図を見つけるのは難しそうですが、先ほどヒットした国土地理院のPDFに「**国土地理院の南極観測概要**」と記載されていることから、日本の国土地理院が観測を行った可能性が推測できます。

`国土地理院　南極`で検索すると、国土地理院の[南極観測に関するページ](https://www.gsi.go.jp/KOKUSAI/nankyoku.htm)がヒットします。実は、ここからも見つけられるのですが、検索しづらいのでなるべくショートカットしたいところです。

そこで、英語表記 `Yomogiri Zima (Jima)` の検索結果に戻ってみると、 [ドイツ語版Wikipediaの記事](https://de.wikipedia.org/wiki/Yomogiri_Zima)がヒットします（この島のページはドイツ語版にしかありません）。ページ右上の座標をクリックすると、[GeoHackのページ](https://geohack.toolforge.org/geohack.php?pagename=Yomogiri_Zima&language=de&params=69.71667_S_38.96667_E_region:AQ_type:isle(0))に飛びます。

ここに**Geographical Survey Institute**、つまり国土地理院のページもリンクされているのでクリックしてみましょう。  
すると、地理院地図のページが表示されるのですが、初期状態では何も表示されません。左上にある「地図」から「その他」をクリックすると、「南極」が登場します。この中の「1:25000 南極地形図（標高版）」をクリックすると、「よもぎり島」が表示され、標高として18メートルの地点が確認できます。

**Diver24{18}**

本問はGeoHackやオンラインGISツールを活用してほしいという意図で作られています。

なお、開催中にプレイヤーから別の測量データセットに基づいて 19m も妥当ではないかという問い合わせがありました。運営チームでデータセットの妥当性を検証の上、確証が取れたことから Flag 追加と遡及して正解扱いとする対応を行いました。

</details>