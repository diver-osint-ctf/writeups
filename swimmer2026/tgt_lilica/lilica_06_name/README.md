# lilica_06_name (100pt / 255 solves)

## 問題文

`lilica` の本名が知りたいです。  
この人物の実名と考えられるものを解答してください。  
ローマ字（アルファベット）表記で入力してください。漢字の表記を考慮する必要はありません。  

例えば、`Sanae Takaichi` が実名の場合、Flagは `SWIMMER{Sanae Takaichi}` となります。  

Please answer what you believe to be `lilica`'s real name.  
Answer in the Latin alphabet (romaji); you do not need to consider Kanji / Hiragana.  
For example, if the real name were `Sanae Takaichi` , the flag would be `SWIMMER{Sanae Takaichi}`.  


## 解法


lilicaは以下のような投稿をしています。

- [面白くなっちゃって とりあえず髪留めこねてみたんだけど これどうやったらVRCのアクセサリにできるんだろう？（2025年12月15日）](https://x.com/twilight_lilica/status/2000551415039791278)

この投稿にはギガファイル便のURLが添えられています。

- [https://54.gigafile.nu/0324-c62de7be61d9af6377e01324cec7939b5](https://54.gigafile.nu/0324-c62de7be61d9af6377e01324cec7939b5)


ダウンロードすると、 `simple_hair_pin.fbx` というファイルが得られます。調べてみると、[FBX形式](https://ja.wikipedia.org/wiki/FBX)は3DCGのデータ形式であることが分かります。

Blenderなどで開いてみると、lilicaの投稿にあったスクリーンショットと同じものであることが確認できます。

しかし、このファイルから得られる情報は本当にこれだけでしょうか？

一般的に、ファイルには何らかの付加的な情報（メタデータ）が記録されていることがあります。JPEG画像であればExif、MP4動画であればXMPデータなどです（CTFでの類題: [DIVER OSINT CTF 2025 recon/05_designer](https://github.com/diver-osint-ctf/writeups/tree/main/2025/recon/05_designer)）。

FBXデータにも何かメタデータがないか調べてみましょう。`FBX メタデータ` `FBX 個人情報` などとGoogle検索すると、FBXには書き出した際のファイルパスが記録されることが多くのサイトやブログで言及されています。

- [FBXファイルに含まれるメタ情報と安全なエクスポート方法](https://blender.atom-box.net/fbx-meta-path/)
- [FBXファイルを共有する？ちょっと待って、その前に！](https://note.com/yui2pm/n/nf74a0a4e776b)

また、これらの記事ではWindowsであれば「メモ帳」で簡易的に閲覧できることも記されています。実際にメモ帳で `simple_hair_pin.fbx` を開いてみると、以下のファイルパスが存在しており、Windowsのユーザ名が漏洩していることが確認できます。

```
C:\Users\shiharu_nanaogi\Documents\modeling\vrc_test\hair_pin\simple_hair_pin.fbx
```

Flag: **`SWIMMER{Shiharu Nanaogi}`**