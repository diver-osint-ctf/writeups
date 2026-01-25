# debeyohiru_02_profile (100pt / 373 solves)

## 問題文

`debeyohiru` は2026年1月時点で求職中で、プロフィールページをウェブ上に公開していたようです。  
このページを探り出し、そのURLを解答してください。

例えば、 `https://example.com/foobar` が対象のページの場合、 Flagは `SWIMMER{https://example.com/foobar}` となります。

As of January 2026, `debeyohiru` appears to have been job hunting and had a profile page published online.  
Find this page and answer its URL.

For example, if the relevant page were `https://example.com/foobar`, the flag would be `SWIMMER{https://example.com/foobar}`.


## 解法

先ほどと同じように、[WhatsMyName](https://whatsmyname.app/) や [Sherlock](https://github.com/sherlock-project/sherlock) を使ってみると、GitHubに `furaigo5` というアカウントがヒットします。また、noteでエンジニアであると書いていることから、最初からGitHubを探してもよいでしょう。

- [https://github.com/furaigo5](https://github.com/furaigo5)

プロフィールにWebサイトのURLが記載されています。

Flag: **`SWIMMER{https://furaigo5.github.io/profile/}`**