# cooking (100pt / 384 solves)

## 問題文

2025年12月、ボリス・ジョンソン元イギリス首相夫妻は私的に日本を訪れた。
彼らは国内の料理教室で寿司作り体験を行ったようだ。
この料理教室を運営する法人の、**12桁からなる会社法人等番号**を答えよ。
会社法人等番号が`130001011420`である場合、Flagは`Diver26{130001011420}`となる。

In December 2025, former UK Prime Minister Boris Johnson and his spouse paid a private visit to Japan.
It is reported that they experienced making sushi at a local cooking class.
Answer **the 12-digit Corporate Identification Number** of the entity that runs this cooking school.
If the number is `130001011420`, the flag should be `Diver26{130001011420}`.


## 解法
ボリス・ジョンソン元英国首相と妻のキャリー・ジョンソンが、日本滞在中に寿司作り体験へ参加した事実は、[キャリー・ジョンソン本人のInstagram投稿](https://www.instagram.com/p/DSVzph4k40B/?img_index=16)から確認できます。また、`ボリス・ジョンソン 寿司体験 2025` といったワードで検索すると、[料理教室経営者のポスト](https://www.facebook.com/fujitanzm/posts/pfbid0C3tHvMerLXQrpfbmv2XqZ1CCum7tFY3wPEjyzbzhLmzNewW5hBz7VuPqbuJ8g6jzl)もヒットします。  

Instagramにタグ付けされている講師の個人アカウントないし経営者のポストから、ジョンソン夫妻は「株式会社のぞみ」の経営する[Sushi Lab.](https://www.su4lab.com/ja)にて寿司作りを行ったことがわかります。

「株式会社のぞみ」という屋号を持つ企業は多数存在するものの、[国税庁法人番号検索サイト](https://www.houjin-bangou.nta.go.jp/)から[会社公式サイト](https://nzm.jp/)に掲載される住所を検索すると、法人番号`5130001026308`を有する同名の法人を確認することができます。ここで取得できる番号は国税庁が指定する法人番号であり、法務局が指定する会社法人等番号ではないため、先頭1文字を削ってフォーマットに適合するようにします。  

Flag: **Diver26{130001026308}**