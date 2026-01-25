# UART

## 問題文

https://www.office-partner.de/tp-link-archer-ax20-12778639

この商品のイーサネットスイッチコントローラに直接UARTでアクセスを試みたい。どの部品の、どのピンにアクセスすればいいだろうか。  
**PCB上の部品番号** と、その部品の **UART RX / UART TX ピン番号** を答えよ。ピン番号は部品の仕様に準拠せよ。  
なお、ピンヘッダやコネクタが利用可能な場合でも、イーサネットスイッチコントローラのピン番号を答えてほしい。  
Flag形式: `Diver25{PCB上の部品番号_UART RXピン番号_UART TXピン番号}`  
（例えば、イーサネットスイッチコントローラが `T21` という部品番号で、RXのピン番号が120、TXのピン番号が150であれば、`Diver25{T21_120_150}`となる）

I want to try to access the Ethernet switch controller of this product directly via UART. Which component and which pin should I access?  
Answer the **part number on the PCB** and the **UART RX / UART TX pin number** of the component. The pin number should follow the specification of the component.  
Note that even if pin headers and connectors are available, answer the pin numbers of the Ethernet switch controller.
Flag Format: `Diver25{Part Number on PCB_UART RX pin number_UART TX pin number}`  
(If the Ethernet switch controller has part number `T21` on PCB, RX pin number is `120` and TX pin number is `150`, the flag should be `Diver25{T21_120_150}`.)


## ヒント

1. ハードウェアにも複数のバージョンが存在する点には注意しよう。いくつかのサイトでは商品名にバージョンが記載されているはずだ。 / Note that there are multiple versions of the hardware. The version name is written in the product name on some websites.

## 難易度

hard / 495 point (24 solves)

## 解法

**TP-Link Archer AX20 AX1800 V2 Dualband Wi-Fi 6 Router** という商品名が記載されています。

この商品について調べてみると、一部のオンラインショッピングサイトやオークションサイトなどでは、裏面のラベルが読み取れます。それらをよく確認してみると、"Ver 2.0"と書いてあるものと、"Ver 1.0" と書いてあるものが存在するようです。  
https://www.amazon.com.mx/TP-Link-WiFi-Router-AX1800-Smart/dp/B08JLH574X

先ほどの商品名では "V2" と書かれていましたから、V2 (Ver 2.0)に該当する商品の FCC ID を調べてみます。上記 URL で示したメキシコの Amazon に表示されている画像にはちょうど Ver 2.0 と書かれており、**TE7AX20V2** という ID の記載があります。

この ID を Google 検索すると、以下の Web サイトがヒットします。  
https://fcc.report/FCC-ID/TE7AX20V2

この中の"[Internal Photos](https://fcc.report/FCC-ID/TE7AX20V2)" という文書には、主要な電子部品がクローズアップされた写真が掲載されています。これらの品番を検索してみると、 **[RTL8367S](https://www.realtek.com/Product/Index?id=3699)** がイーサネットスイッチコントローラであると分かります。また、PCB（Printed Circuit Board）上の部品番号は読み取りづらいですが **U7** であるとわかります。V と紛らわしいかもしれませんが、IC は通常 "U" に割り当てられます（[参考](https://www.ultralibrarian.com/2021/05/25/common-pcb-component-codes-to-know-ulc)）。

電子部品の仕様を記した書類は「[データシート](https://en.wikipedia.org/wiki/Datasheet)」と呼ばれます。ここで、`RTL8367S datasheet` と Google 検索すると、このチップのピン配置が記されたドキュメントが複数ヒットします。

45 番ピンが `GPIO01/RG2_TXD3/M2M_TXD3/M2P_RXD3/UART_RX` 、46 番ピンが `GPIO02/RG2_TXD2/M2M_TXD2/M2P_RXD2/UART_TX` と記載されていることから、Flag は以下の通りです。

**Diver25{U7_45_46}**

## 出題意図

ハードウェアのハッキングやリバースエンジニアリングにおいても、OSINTのノウハウは活用されます。もしデバイスが手元にあれば分解を行うのが手っ取り早い方法に思えますが、意図しない破損やタンパ検知によってデバイスが使用できなくなるリスクがあるため、一般的には仕様書などから分析を始めるのがベストプラクティスとされています。特に、入手が難しいハードウェアについては実際に開けて破損させてしまう前に、可能な限り必要な情報を集めるのが望ましいでしょう。

"phone" の問題にも登場したFCC IDは、米国で販売される無線機器には必ず付与されているもので、オンライン上で様々な情報を得るきっかけになります。また、電子機器のdatasheetもオンラインで参照できることが多く、こちらも調査において有用です。

今回、UARTのピンをFlagとしたのは、UARTはIoTデバイスやルータのハッキングにおいて実際に使用されることがあるためです。より現実的には、QFPに直接プローブを当てるのではなく、UARTに接続されていると思われるピンヘッダやコネクタ、JTAGにアクセスを試みることになるでしょう（実際、当該製品にもそれらしきピンヘッダがあります）。

- 参考記事
  - https://github.com/f3nter/HardBreak/blob/main/hardware-hacking/reconnaissance/closed-device/osint-search-the-web.md
  - [When IoT Attacks: Hacking A Linux-Powered Rifle](https://youtu.be/ZcukSF7ruZY?si=JV1VJIZW4ehSi1Vj&t=784) - Black Hat
  - [AvertX製IPカメラで3つの脆弱性が見つかる](https://unit42.paloaltonetworks.com/ja/avertx-ip-cameras-vulnerabilities/)

## CTF開催中のFlag追加訂正について

当初、運営チームの確認不足により、 **Diver25{U1_45_46}** をFlagとして設定していましたが **Diver25{U7_45_46}** が正しいことが確認されました。そのため、競技時間中に正しいFlagを **追加設定** し、送信されたものに対して遡及して正解を適用しました。

大変申し訳ございません。ご迷惑をおかけいたしました。