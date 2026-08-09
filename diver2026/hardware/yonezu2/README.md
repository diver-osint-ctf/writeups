# yonezu2 (100pt / 245 solves)

## 問題文

米津玄師が搭乗していたサメ形の乗り物を動作させている製品の制御仕様は公開されていると考えられる。  
この製品を回転させる際に使用されるコマンドとそのIDを確認してほしい。  
例えば、 `IrisOut` という **コマンド** が `0xE2` という **コマンド ID** で定義されている場合、Flagは `Diver26{IrisOut_0xE2}` となる。  
コマンド名およびIDは仕様書に書かれている通りに解答せよ。

The control specifications for the product that operates the shark shaped vehicle ridden by Kenshi Yonezu are considered to be public.
Identify and answer the **command** and its **command ID** used to rotate this product.
For example, if the command is `IrisOut` and it is registered as command ID `0xE2`, the flag should be `Diver26{IrisOut_0xE2}`.
Answer the command name and ID exactly as specified in the documentation.


## 解法

WHILL社のプラットフォームについて検索すると、以下のような情報がヒットします。

- [WHILL社、「JAPAN MOBILITY SHOW Bizweek 2024」で歩行領域ロボットの足回りを支えるモビリティプラットフォームを披露](https://prtimes.jp/main/html/rd/p/000000201.000011151.html)

WHILL社は電動車椅子を事業の中心にしていますが、汎用の「モビリティプラットフォーム」も手掛けていることがわかります。  
この中で信地旋回（その場に留まった状態で回転すること）が可能なオムニホイールを用いたプラットフォームが提示されており、これが当該製品である可能性が高いと考えられます。

- [WHILL 電動モビリティプラットフォーム](https://whill-mrp.notion.site/WHILL-f975baf4015e4eebbb243a7d331efb0a#1cef8f981f0980199617cf604cdcbfd0)

上記のページでは「オムニプラットフォーム」というプロダクトが確認でき、以下のように説明されています。

> カスタム可（フレーム形状の変更、ブレーキの追加、ソフトウェアの機能追加、非常停止ボタンの追加など）  
> https://whill-mrp.notion.site/WHILL-f975baf4015e4eebbb243a7d331efb0a#1cef8f981f0980199617cf604cdcbfd0

上記のページで示されているものは正方形に近い比率ですが、サメ形乗り物は比率が異なります（車両の前後方向が長いです）。  
この画像で示されているプラットフォームのフレーム部分は汎用のアルミフレームであると考えられます。説明にもあるようにフレーム形状の変更も可能であるため、比率やサイズの不一致は問題ないと考えられます。  
また、フレームの長さから、電動車椅子ではなく、オムニプラットフォームを利用していることが強く推定されます。

また、上記のページには仕様書へのリンクが掲載されています。

https://github.com/WHILL/whill_control_system_protocol_specification/blob/omnipf/WHILL_Control_System_Protocol_Specification_for_Omni_Platform.pdf

これを確認すると、15ページ目からはじまる「To move Omni platform」というセクションにおいて、17ページ目に明確に `SetVelocity` (`0x08`) コマンドによってプラットフォームを回転（信地旋回）できることが示されています。

Flag: `Diver26{SetVelocity_0x08}`

なお、CR2といった電動車椅子でも使用可能な `SetJoystick` では Front, Back, Left, Rightといった通常の挙動について言及されている一方、Omni Platform固有の挙動（信地旋回）が可能であることを競技時間中に確認できなかったこと、加えてOmni Platformの制御には `SetVelocity` を使用することが前述の仕様書15ページで明言されていることから、Flagの追加を行っていません。