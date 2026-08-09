# accident (398pt / 115 solves)

## 問題文

1955年、アメリカの軍人であるMiguel A. Pedrazaは運転中の事故によって死去した。
このとき彼が乗っていた車のナンバーを教えよ（ハイフン・スペースなし）。
たとえば、ナンバーが`ABC-123`である場合、flagは `Diver26{ABC123}`となる。

In 1955, Miguel A. Pedraza, an American serviceman, died in a traffic accident.
Answer the license plate number of the car he was driving at this time (without hyphens or spaces).
If the plate number is `ABC-123`, the flag should be `Diver26{ABC123}`.


## 解法
`Miguel A. Pedraza US army "1955"`といったワードで検索すると、プエルトリコ国立墓地（Puerto Rico National Cemetery）の被葬者一覧に、[次の記録](https://www.interment.net/united-states/puerto-rico/bayamon/puerto-rico-national-cemetery/transcription/575.php?page=464)が見つかります。  

> Pedraza, Miguel Angel: b. 9/18/1918, d. 5/4/1955, Sec. C, Site 154, US ARMY, CAPT, KOREA

埋葬先がプエルトリコ国立墓地であることから、死去した場所もプエルトリコであった可能性が高いです。当時の新聞記事を探すと、プエルトリコの日刊紙『El Mundo』の[デジタルアーカイブ](https://www.eastview.com/resources/gpa/el-mundo/)を見つけることができます。  

1955年5月に期間を絞り、「Pedraza」で検索すると、同月6日付の紙面に[該当記事](https://gpa.eastview.com/crl/elmundo/newspapers/mndo19550506-01.1.1)が掲載されています。  

> El cuerpo del capitán Miguel Ángel Pedraza, de 35 años, fue localizado ayer a las 2 de la tarde a 19 pies de profundidad en el lago de la represa del Salto de Comerío, en el kilómetro 20, hectómetro 6 de la carretera 167. Un buzo del Décimo Distrito Naval localizó el cadáver dentro del automóvil Chrysler 39-735, hundido entre agua y lodo.

> 35歳のミゲル・アンヘル・ペドラサ大尉の遺体は、昨日午後2時、167号線のキロメートル20、ヘクトメートル6にあるコメリオのサルト・ダム湖の水深19フィートで発見された。第10海軍管区の潜水士が、水と泥の中に沈んでいたクライスラー・39-735の内部で遺体を発見した。

Flag: **Diver26{39735}**
