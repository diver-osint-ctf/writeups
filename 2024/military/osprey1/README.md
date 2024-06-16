# osprey1

## 問題文

2023年11月29日、アメリカ軍のオスプレイ（V-22）が日本の屋久島沖で墜落した。この機体の番号と、墜落時のコールサインは何か。  
Flag形式: `Diver24{XX-XXXX_CALLSIGN}`  
たとえば機体登録番号が01-2345、コールサインがCALL01の場合、Flagは `Diver24{01-2345_CALL01}` となる。

この事故に関する問題は本CTFにおいて3問あります。正解することで1問ずつアンロックされます。

On 29 November 2023, a US military Osprey (V-22) crashed off Yakushima Island, Japan. What is the number of this aircraft and what was its call sign at the time of the crash?  
Flag format: `Diver24{XX-XXXX_CALLSIGN}`  
For example, if the aircraft registration number is 01-2345 and the callsign is CALL01, the flag should be `Diver24{01-2345_CALL01}`.

There are three challenges on this accident in this CTF. Each challenges is unlocked by answering it correctly.


## 難易度
easy / 100 point (203 solves)

## 解法

<details>

<summary>クリックで表示</summary>

航空機の事故など、大きな影響のある事象は何らかのデータベースになっている可能性が高いといえます（最低限でも、個人レベルでまとめている人がいると想像できます）。

`V-22 accident list` で検索すると、[Aviation Safety Network](https://asn.flightsafety.org/wikibase/type/V22)のリストがヒットします。

ここに屋久島沖の事故についてのデータも記録されています。[事故の個別ページ](https://aviation-safety.net/wikibase/348462)を開くと、機体番号を意味する"Registration"という欄に `12-0065` と記載されています。また、本文にはコールサインの `Gundam 22` が記載されており、これらがフラグとなります。

**Diver24{12-0065_GUNDAM22}** （表記揺れも考慮）

なお、参加者の方のwriteupを拝見する限りだと、 SNS の単一の投稿を情報源として利用した方も多いように思われました。しかし、個人的にはあまりおすすめできる手法ではありません。SNS 上でOSINTを標榜する軍事情報のアカウントには、非常に参考になる情報を発信されている方もいらっしゃる一方で、ソースのない情報を「OSINT」と称して流しているものも多数存在し、ある程度の経験がないとそれらの真偽を確認することは難しいからです（もちろん、CTFの解答方法としては問題ありません）。

今回のような、軍事動向や航空事故に関してはなるべく複数のソースを辿ることをおすすめします。特に事故発生直後など、未確定の段階では軍事アナリストの間でも情報が錯綜しがちです。

</details>