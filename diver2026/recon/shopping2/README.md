# shopping2 (275pt / 170 solves)

## 問題文

shopping1 で特定した攻撃者は別のキャンペーンも並行運用しているらしい。並行キャンペーンサイトのFQDNを特定せよ。<br>
例えば、FQDNがcampaign.example.comの場合、Flagは `Diver26{campaign.example.com}` となる。

The attacker identified in shopping1 appears to be running another campaign in parallel. Identify the FQDN of the parallel campaign site.<br>
For example, if the FQDN is campaign.example.com, the flag should be `Diver26{campaign.example.com}`.


## 配布ファイル

- [.gitkeep](./public/.gitkeep)

## 解法

この問題の解法は3つあります。想定解法を以下に記載します。

**1. 攻撃者の GitHub gist を探す**

shopping1 で判明した GitHub アカウント `smpri194-beep` の公開 gist を確認します。

- `https://gist.github.com/smpri194-beep`

"How to Prevent Email Spoofing on a Cloudflare Domain" という gist (`email_spoofing.md`) が見つかります。

**2. スクショから Cloudflare Worker のアプリ名を読み取る**

gist に貼られた Cloudflare ダッシュボードのスクリーンショットに Workers の一覧が写っており、Worker (アプリ) 名 **`plain-cherry-ca06`** が確認できます。

同じスクショの左上にアカウント名が「`<...>@gmail.com's Account`」と表示されています。これにより Cloudflare アカウントが Gmail アドレスに紐づくことがわかりますが、**メールのローカル部はマスクされている**ため、ここだけでは workers.dev のサブドメインを確定できません。

**3. GitHub からメールアドレスを特定する**

workers.dev のサブドメインはデフォルトではアカウント作成時に決まります。そこで、メールアドレスを探すと、gist は git リポジトリとして clone でき、コミットの author email がそのまま残っていることがわかります。

```bash
git clone https://gist.github.com/d3caac338832b3933e04e7dee256e7b9.git
git -C d3caac338832b3933e04e7dee256e7b9 log -1 --format='%ae'
# => smpri194@gmail.com
```

(gist の revisions 表示や commit の `.patch` 参照でも同じ author email が得られます。)

**4. Worker URL を組み立てて開く**

Cloudflare Workers の URL は `https://<worker名>.<サブドメイン>.workers.dev/` の形式:

- worker 名: `plain-cherry-ca06` (ステップ 2 / スクショ)
- サブドメイン: `smpri194` (ステップ 3 / メール)

```
https://plain-cherry-ca06.smpri194.workers.dev/
```

開くと並行キャンペーンのサイトが表示されます。

**5. 同一人物であることを verify**

Worker ページと js-deliver.com の HTML を確認すると、どちらも同じ Google Tag Manager measurement ID **`G-WXWZVC8P09`** を埋め込んでいます。

```bash
curl -s https://plain-cherry-ca06.smpri194.workers.dev/ | grep -oE 'G-[A-Z0-9]{10}'  # G-WXWZVC8P09
curl -s https://js-deliver.com/ | grep -oE 'G-[A-Z0-9]{10}'                          # G-WXWZVC8P09
```

ここから、単一の GA / GTM アカウントで両サイトを運用している = **js-deliver.com と同一人物 (同一キャンペーン運用者)** であることが確認できます。

**6. FLAG**

```
Diver26{plain-cherry-ca06.smpri194.workers.dev}
```

---

なお、別の解法として、簡単に2つ紹介します。

**別解1: Google Tag Manager measurement IDを検索する**

どこかにページのソースコードをキャッシュされていたり、魚拓されていれば検索可能なことがあります。なお、このCTFの開催直前の時点ではどのサイトにも保存されていなかったように思えますが、開催中は検索可能だった可能性があります。

**別解2: Google検索する**

攻撃者のメールアドレスを検索すると、メールアドレスのローカルパートがキャンペーンサイトのドメインの一部と一致するので、検索に引っかかることがあります(別解1のために、no-indexを設定していませんでした)。