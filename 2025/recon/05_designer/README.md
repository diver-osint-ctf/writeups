# designer

## 問題文

**"00_engineer"** の問題で見つかった会社のWebサイトを手がけたデザイナーの連絡先（メールアドレス）を答えよ。  
Flag 形式: `Diver25{foo.bar@example.com}`

Answer the contact email address of the designer who worked on the company's website found in the **"00_engineer"** challenge.  
Flag Format: `Diver25{foo.bar@example.com}`


## 難易度

hard / 500 point (7 solves)

## 解法

Magneight 社の旧ドメイン `magn8soft.tokyo` にアクセスしても、新しい Web サイト `magneight.com` に転送されるようになっています。

しかし、Wayback Machine で旧ドメインを参照すると、2025 年 3 月頃に新サービスのティザーサイトが用意されており、そこには `magneight-teaser.mp4` という MP4 ファイルが存在していたことが明らかになっています。

https://web.archive.org/web/20250309135450/https://magn8soft.tokyo/

MP4 ファイルに Exif は存在しませんが、Adobe PremierePro や AfterEffects などから出力されたファイルであれば、[Extensible Metadata Platform (XMP)](https://helpx.adobe.com/jp/audition/using/viewing-editing-xmp-metadata.html)メタデータが存在している可能性があります。  
そこで、この MP4 ファイルを exiftool に通してみましょう。すると、以下のようなデータが得られます（抜粋）。

```
Pantry History Software Agent   : Adobe After Effects 2025 (Macintosh)
Pantry History Changed          : /
Pantry Windows Atom Extension   : .aep
Pantry Windows Atom Invocation Flags: -ep
Pantry Mac Atom Application Code: 1180193859
Pantry Mac Atom Invocation Apple Event: 1131559026
Pantry Ae Project Link Composition ID: 1
Pantry Ae Project Link Render Queue Item ID: 4
Pantry Ae Project Link Render Output Module Index: 0
Pantry Ae Project Link Full Path: /Users/callalily0629izuhara/Documents/footage/magneight.aep
Derived From Instance ID        : xmp.iid:bc3822a1-41be-4dea-871e-863d404f63c7
Derived From Document ID        : xmp.did:bc3822a1-41be-4dea-871e-863d404f63c7
Derived From Original Document ID: xmp.did:bc3822a1-41be-4dea-871e-863d404f63c7
Windows Atom Extension          : .prproj
Windows Atom Invocation Flags   : /L
Mac Atom Application Code       : 1347449455
Mac Atom Invocation Apple Event : 1129468018
Mac Atom Posix Project Path     : /Users/callalily0629izuhara/Documents/Adobe/Premiere Pro/23.0/Magneight_2025.prproj
```

[マーカー](https://helpx.adobe.com/jp/premiere-pro/using/markers.html)（Tracks Markers）の情報などと共に、AEP ファイル（AfterEffects のプロジェクトファイル）や、PRPROJ ファイル（PremierePro のプロジェクトファイル）のパスが記録されていることが確認できます。

ファイルパスには **callalily0629izuhara** というユーザ名が記録されています。  
これを sherlock に通してみると、（いくつか偽陽性も含まれますが）Instagram のアカウントがヒットします。

```bash
$ sherlock callalily0629izuhara
[*] Checking username callalily0629izuhara on:

[+] Instagram: https://instagram.com/callalily0629izuhara

[*] Search completed with 7 results
```

CEO の Instagram での投稿から、Magneight 社の Web コンテンツは映像から Web デザインまで一貫して同じ人物が担当していることが判明します。これより、この人物のメールアドレスがこの問題の Flag となると考えられます。

![](./ceo_instagram.png)

さて、callalily0629izuhara のアカウント上には **BlueSky: callalily-izuhara.bsky.social** とプロフィールに書かれています。  
Bluesky のアカウントでログインしてこのアカウントを確認すると、この URL には以下のリンクが含まれています。

https://lit.link/en/callalily0629izuhara

このサイトに連絡先のメールアドレスが記載されています。

**Diver25{izuhara.calla.lily@outlook.com}**

