# Afghanistan

## 問題文

動画 / Video:  
https://www.youtube.com/watch?v=NWQwx4-MeRg&t=65s

この動画の65～67秒に表示される写真はいつどこで撮影されたものか。  
Flag形式: `Diver25{撮影場所名_YYYY-MM-DD}`（撮影場所名は英語）  
例えば、2025年6月5日に、Camp Darbyで撮られた場合は、`Diver25{Camp Darby_2025-06-05}`となる。

When and where was the photo shown at 65-67 seconds in this video taken?  
Flag format: `Diver25{location name_YYYY-MM-DD}` (location name should be in English)  
For example, if it was taken at Camp Darby on June 5, 2025, it would be `Diver25{Camp Darby_2025-06-05}`.

## 難易度

medium / 414 point (94 solves)

## 解法

2 人の軍人が山を背景にした拠点的な場所にてバスケットボールをしている様相を映した画像です。

画像内の地形情報や方角、文字、その他ジオロケーションに利用可能な情報はありません。そこで、この画像に関連する情報がないかを考えます。もしかしたら、ストックフォトなどとして別の場所で説明付きで利用されている可能性があります。

このような画像への定石としては、Google Lens で検索ですが、この画像については全体でも部分でもあまりうまくいかないようです。

そこで、画像検索ツールを変えながら試してみます。Bing・Yandex でも同様です。しかし、[TinEye](https://tineye.com/)で検索すると、1 件ヒットします（作問時点）。

Filename は `http://img.rt.com/files/politics/afghan-general-interview/us-soldiers.op.jpg` で、`http://rt.com/politics/study-war-terror-obama/` と `http://rt.com/politics/study-war-terror-obama/comments/` に関係があるようです。  
しかし、画像は見当たらず、記事にもそれらしい影はありません。また、小さく掲載されているサムネイル画像は確かに似ているのですが、検索してもそれらしいサイトには辿り着けません。

ここで、Wayback Machine にないか探しますが、その画像ファイルの URL では何も見つかりません。また、記事のアーカイブにも一応サムネイルのみあり、`http://rt.com/politics/afghan-general-interview/` という記事に辿り着けますが画像が見当たらず、役に立ちません。  
そこで、Wayback Machine で、URL 検索をします。具体的には、`http://img.rt.com/files/politics/afghan-general-interview/us-soldiers.op.jpg` が怪しいと考えられます。

いくつか理由はありますが、1 つは画像ファイル名の op が気になること、もう一つは構造から `http://img.rt.com/files/politics/afghan-general-interview/` に記事に関連する画像が集められていそうと考えられるからです。これで検索すると実際に `https://web.archive.org/web/20150428102237*/http://img.rt.com/files/politics/afghan-general-interview/us-soldiers.n.jpg` のアーカイブが出てきます。

この方法で表示した画像を Lens すると、[Getty Images のページ](https://www.gettyimages.com/photos/naray-afghanistan)とサムネイルが表示されます。また、撮影者は"LIU JIN" という人物であることがわかります（これは、rt.com の http://rt.com/politics/afghan-general-interview/ の記事の冒頭、表示されない動画の下に書いてある情報と一致します。また、左下に `86012381` とあり何か特定するための情報の可能性があります。

しかし、この一覧のぺージを見ても同じ画像は表示されません。さらにこのサムネイルを Google Lens すると、Getty Images の様々なページが出てきますが、なぜか答えにはたどり着けません。そこで、左下の数字と gettyimages の語の組み合わせをググると、 `https://www.gettyimages.ae/detail/news-photo/two-us-soldiers-from-1st-infantry-division-play-a-game-of-news-photo/86012381` という画像に辿り着きます。この画像の Exif を見てみると、タイトル部分からいつ、どこか判明します。

**Diver25{Forward Operating Base Bostick_2009-04-16}**（`Diver25{Camp Bostick_2009-04-16}`などの表記揺れも正解）
