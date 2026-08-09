# arctic (277pt / 169 solves)

## 問題文

2025年、インドにて「Westarctica」の大使を名乗り、詐欺を働いていた人物が逮捕された。  
以下のニュースに添付されている同国の偽造外交官ナンバープレートは、彼が経営に携わる特定の法人名義で登録されていた。  
この法人の21桁からなる企業識別番号（CIN）を答えよ。  
https://www.abc.net.au/news/2025-07-25/man-arrested-for-running-fake-embassy-in-india/105571606  

たとえば、CINが 123456789ABCDEFG であれば、Flagは `Diver26{123456789ABCDEFG}` となる。

In 2025, a person posing as an ambassador for "Westarctica" was arrested in India for committing fraud.  
The fake diplomatic license plate of the micronation, shown in the photo attached to the news article below, was registered under a specific corporation that this individual was involved in managing.  
Answer the 21-digit Corporate Identification Number (CIN) for this company.  
https://www.abc.net.au/news/2025-07-25/man-arrested-for-running-fake-embassy-in-india/105571606  

For example, the CIN is 123456789ABCDEFG, the flag should be `Diver26{123456789ABCDEFG}`.


## 解法
問題に現れる情報をもとに検索すると、[Times of India](https://timesofindia.indiatimes.com/city/noida/fake-ghaziabad-diplomat-partnered-with-uk-bizman-to-set-up-brokerage-firms-stf/articleshow/122866564.cms)の報道を見つけることができます。ここには、以下のようにあります。  

> The two other cars seized from the house, both with diplomatic registration plates, are owned by Bhavesh Dugar of Delhi and another by Indra Business Private Limited. Delhi. Cops are trying to find out how Jain got access to these cars.

デリーの"Indra Business Private Limited"名義でナンバープレートが取得されていると書かれていますが、[MCA](https://www.mca.gov.in/content/mca/global/en/mca/fo-llp-services/company-llp-name-search.html)にはそのような名称の企業は見つけることができません。  

そこで、さらなる情報を得るため、`DL4CR8559`というナンバーを検索することを考えます。インドにおいては[Carinfo](https://www.carinfo.app/rto-vehicle-registration-detail)、[Vehicleinfo](https://vehicleinfo.app/rc-details/DL4CR8559?rc_no=DL4CR8559)といったウェブサイトにおいて、インド国民以外も車の名義人について限定的な情報を得ることができます。これらの検索結果から、このナンバープレートを持つ車の名義人が`I****A B******S (*****) P**.`であることがわかります。  

この情報が正しい場合、Times of Indiaの報じた法人名とは文字数が合わないため、誤植の可能性に思い至ることができます。`I****A`という文字数から、実際の企業名が`INDIRA`である可能性を想起し、MCAで検索してみると、実際に`INDIRA BUSINESS (INDIA) PRIVATE LIMITED`という企業が存在することがわかります。これにより、車の名義人が`INDIRA BUSINESS (INDIA) pvt.`であることが想定可能となります。実際に登記をとってみると、同社の取締役のひとりにはTimes of Indiaで報じられるHarshvardhan Jainがいることもわかります。

Flag: **U51909DL2002PTC114202**