# suspicious_acft (500pt / 0 solves)

## 問題文

添付されたRFI（情報提供依頼）を参照し、解答せよ。  
この問題はオープンエンドクエスチョンであり、唯一の正解を用意しているものではない。十分に説得力のある論証が行われていれば、採点基準に基づいて加点が行われる。  
ただし、解答の内容に疑念がある場合はチームに対して照会が行われる可能性がある。その場合、採点時間中にチケット上で応答する必要がある。

なお、この問題の解答は競技終了後、公開する可能性がある。もし公開を望まない場合、解答の冒頭に "DO NOT DISCLOSE OUR REPORT" と記載せよ。  
公開を望まない場合でも、点数への影響は一切ない。

Please refer to the attached RFI (Request for Information) and provide your answer.  
There is no single, definitive answer to this challenge. Points will be awarded based on the grading criteria provided that the argument presented is sufficiently persuasive.  
However, if there are any concerns regarding the content of your answer, the team may contact you for clarification. In such cases, you will be required to respond via the ticket during the grading period.

Note that your answer to this challenge may be published after the competition ends. If you do not wish your answer to be disclosed, write "DO NOT DISCLOSE OUR REPORT" at the beginning of your answer.  
Opting out of disclosure will have no effect on your score.


## 配布ファイル

- [rfi_suspicious_acft.pdf](./public/rfi_suspicious_acft.pdf)

## 解法

**結論**: CTF開催時点で、ジョージアのMyWay Airlinesに移転したものだと強く推定されます。直近でイランへ移転する可能性は低く、すでに移転した可能性は限りなく低いといえるでしょう。

なお、競技終了3日後の7月29日、上海→トビリシでMJ5400としてデリバリーが確認されています。

### 分析

まずは当該機JA709Jの動向を追います。Planespottersによると、2022年に日本航空を退役したのち、N837KWとして米国レジが付与されています。その後、2026年5月に日本航空の塗装のまま上海に移動したことが確認されています。  
ナイジェリアの Air Peace へ移転する予定だったが、ntu (not taken up) と書かれています。この真偽はオンライン上では確認しづらいと考えています。

さて、直前の登録国である米国から第三国へ移転したことより、米国に何らかの記録が残っているはずです。  
[Releasable Aircraft Database Download](https://www.faa.gov/licenses_certificates/aircraft_certification/aircraft_registry/releasable_aircraft_download/)のDeregistered Aircraft fileを確認すると、(N)837KWの登録抹消時に移転先としてGEORGIAが記載されています。これより、ジョージアに移転することが推定されます。

```
837KW,32896,1385279,V ,ALTA 777 LLC\,2755 E COTTONWOOD PKWY # 450,,SALT LAKE CITY,UT,84121,,,,,035,US,,20260520,52671521,7,GEORGIA,20230427,20230322,(略),AB7351
```

そして、Planespottersで記載されている移転先の香港の会社は何者でしょうか。
「情報が出ないがペーパーカンパニーだ」と主張することも可能かもしれませんが、航空業界では航空機リースでは特別目的会社が存在することも多いため、その可能性を考慮してみます。

当該の香港企業について、香港の[Company Registry](https://www.cr.gov.hk/en/home/index.htm)を照会すると、MyWay Airlinesの関係者が記載されています（個人情報を含むため詳細は省きます）。

続いて、PlanespottersやFlyteamからMJが保有する機材をリストアップしてみましょう。

- 4M-MWA - 737-8AL
  - Badr AirlinesへACMIリース中
- 4M-MWB - 777-246ER
  - Planespotters曰く、lsd from hidden→香港の会社がリースしている可能性はあるかも
- 4M-MWC - 737-75C(BDSF)
  - 貨物機
- 4M-MWD - 出題時点で情報なし（競技終了後に明らかになった）

また、MJの経営陣がLinkedInで2機目の777-200ERを取得する話を書いており、上海のMRO施設（Boeing Shanghai Aviation Services）での写真が含まれています。  
その写真にはノーズギアに「MD」と記されている、MJ塗装の777−200ERが写っており、航空会社の多くはレジ番を連番で取ることが多いため、これが4M-MWDになるのではと考えられます。

また、MJはACMIリースを行っているものの、現時点ではセネガル（Air Senegal）やスーダン（Badr Airlines）への提供に留まっており、「イランへの移転」を推定できる状況にはないと考えられます。

競技時点では確定できなかったため、次のステップとして「ジョージア側に登録情報を照会する」「上海から出発する4M-MWDをウォッチし続ける」といった手法が考えられます。実際、7月29日に4M-MWDは上海からトビリシへデリバリーされており、この手法は有効でした。

## 採点基準

- A: 結論の提示（200点）
  - 100%: 現時点で推定される事実（ジョージアのMyWay Airlinesへの転籍が行われる可能性が高い）が示されている。
  - 50%: 現時点で推定される事実をカバーしうる結論が十分に検証されたデータと共に示されている
    - 例：「イランに渡ったとは断言できない」→他国への移転も考慮されているのでOK
  - 25%: 現時点で推定される事実をカバーしうる結論が提示されているが、検証データに課題がある
    - 当てずっぽうでこれに至る可能性があるので、データの有無を基準に盛り込んだ
  - 0%: 誤った結論が断言、あるいはほぼ断言されている
    - 例：「イランに渡ったと強く推定される」
- B: 証拠情報の提示（200点）
  - 100%: 結論を導出するために、概ね精緻に検証された証拠が提示されている
  - 50%: 結論を導出できているが、確度が高いとは言えない証拠も無視できない程度に混在している
    - 例：「中国に渡り、整備をした。最終的な譲渡先は不明だが、日本航空に復帰した可能性が高い」など、出題時点で無視できない誤り
  - 25%: 結論を導出できているが、確度が高いとは言えない証拠が主になっている
  - 0%: 証拠が不十分、不正確、関係がないといった理由により、結論を導出できていない
- C: 不足情報およびさらなる情報収集手段の提示（100点）
  - 100%: 現状で不足している情報を概ね正確に認識し、それを補うために手段として妥当なものが提示されている。
  - 50%: 現状で不足している情報を概ね正確に認識しているが、提示されている手段が妥当なものではない（例：実現性の低い手段が提示されている等）
    - 「実現性」は、OSINTの次のステップとして取れるかどうかで判断する。たとえば、「有償の情報を取得する」「役所で公文書を取得する」といった手法は現実的であると考えられるが、「諜報員を施設内に現地に送り込んで目視する」といった手法は（存在しうるかもしれないが）次のステップとして現実的ではないと評価する。
  - 25%: 現状で不足している情報の認識はできているが、十分ではない。
  - 0%: 現状で不足している情報の認識ができていない。
- D: その他顕著な加点要素（100点を上限に加点）
  - 他のどのチームから示されていない新しい情報を正確な根拠と共に示し、それに唯一性と価値がある場合など（今回は該当なし）