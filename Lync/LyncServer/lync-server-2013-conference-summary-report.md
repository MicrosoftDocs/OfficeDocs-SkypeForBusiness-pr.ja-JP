---
title: 'Lync Server 2013: 会議の概要レポート'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Conference Summary Report
ms:assetid: 62f54812-5700-45a3-8526-8f58b0f77fbc
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558656(v=OCS.15)
ms:contentKeyID: 48184299
ms.date: 09/03/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: dde91a25d33bac5af8b1759b1fbfc90cfb9bc0ff
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34840499"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="conference-summary-report-in-lync-server-2013"></a>Lync Server 2013 の会議の概要レポート

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2014-09-03_

電話会議の概要レポートは、オンライン電話会議セッションの全体像を示します。 通常、会議には2人以上のユーザーが関与し、Microsoft Lync Server 2013 会議サービスの使用が必要です。 これに対して、ピアツーピアセッションでは通常、2人のユーザーのみが必要となり、Lync Server の会議サービスを使う必要はありません。 ピアツーピアのアクティビティは、 [Lync Server 2013 のピアツーピアアクティビティの概要レポート](lync-server-2013-peer-to-peer-activity-summary-report.md)で報告されます。

会議の概要レポートには、特定の期間 (1 時間、毎日、毎週、毎月) に開催された会議の数が表示されるだけでなく、それらの会議に参加したユーザーの合計数と、電話会議の合計数が示されます。手帳.

"一意の" 開催者とは、少なくとも 1 件の会議を予定したユーザーです。 たとえば、Pilar Ackerman が 1 件の会議を予定した場合、彼女は 1 名の一意の開催者としてカウントされます。 Ken Myer が 148 件の会議を予定した場合、彼も 1 名の一意の開催者としてカウントされます。 たとえば、次の表では、8回の会議がスケジュールされていますが、固有の開催者 (Ken Myer、Pilar Ackerman、David Ahs) が3つあります。


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>会議の開催者</th>
<th>会議の開催日時</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Ken Myer</p></td>
<td><p>7/7/2012 10:00 AM</p></td>
</tr>
<tr class="even">
<td><p>David Ahs</p></td>
<td><p>7/7/2012 10:00 AM</p></td>
</tr>
<tr class="odd">
<td><p>Ken Myer</p></td>
<td><p>7/7/2012 11:00 AM</p></td>
</tr>
<tr class="even">
<td><p>Pilar Ackerman</p></td>
<td><p>7/7/2012 11:00 AM</p></td>
</tr>
<tr class="odd">
<td><p>Ken Myer</p></td>
<td><p>7/7/2012 1:00 PM</p></td>
</tr>
<tr class="even">
<td><p>Pilar Ackerman</p></td>
<td><p>7/7/2012 2:00 PM</p></td>
</tr>
<tr class="odd">
<td><p>Ken Myer</p></td>
<td><p>7/2/2012 10:00 AM</p></td>
</tr>
<tr class="even">
<td><p>Pilar Ackerman</p></td>
<td><p>7/2/2012 10:00 AM</p></td>
</tr>
</tbody>
</table>


電話会議の概要レポートは、音声/ビデオを利用した会議の数も示します。

<div>

## <a name="accessing-the-conference-summary-report"></a>電話会議の概要レポートへのアクセス方法

電話会議の概要レポートには、[監視レポート] ホーム ページからアクセスします。次の指標のどちらかをクリックすることで、電話会議動作状況レポートにドリルダウンできます。

  - 電話会議の合計数

  - 参加者の合計数

</div>

<div>

## <a name="making-the-best-use-of-the-conference-summary-report"></a>電話会議の概要レポートを最大限に活用する

会議の概要レポートで使用されるいくつかの指標の合計値は、レポートの下部にあります。下にスクロールして、指定した期間内に開催された会議の合計数、およびそれらの会議に参加したユーザーの合計数などの値を表示します。 レポートの下部に集計されていない1つのメトリックは、一意の会議開催者の合計数です。 なぜでしょうか。 1つの理由を次に示します。 1ヶ月分のデータを見ているとします。 1日目に、34固有の会議開催者がいます。2日目には、27の固有の会議開催者がいます。 2日間、61固有の会議開催者であるということですか? 必ずしもそうではありません。 結局、2日目に会議を開催した27人全員が、1日目に会議を開催した34人のユーザーである場合があります。 たとえば、この単純なレポートでは、Ken Myer と Pilar Ackermanのスケジュールされた会議は、7/7/2012 と7/2/2012 の両方で使用されていることに注意してください。


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>会議の開催者</th>
<th>会議の開催日時</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Ken Myer</p></td>
<td><p>7/7/2012 10:00 AM</p></td>
</tr>
<tr class="even">
<td><p>David Ahs</p></td>
<td><p>7/7/2012 10:00 AM</p></td>
</tr>
<tr class="odd">
<td><p>Ken Myer</p></td>
<td><p>7/7/2012 11:00 AM</p></td>
</tr>
<tr class="even">
<td><p>Pilar Ackerman</p></td>
<td><p>7/7/2012 11:00 AM</p></td>
</tr>
<tr class="odd">
<td><p>Ken Myer</p></td>
<td><p>7/7/2012 1:00 PM</p></td>
</tr>
<tr class="even">
<td><p>Pilar Ackerman</p></td>
<td><p>7/7/2012 2:00 PM</p></td>
</tr>
<tr class="odd">
<td><p>Ken Myer</p></td>
<td><p>7/2/2012 10:00 AM</p></td>
</tr>
<tr class="even">
<td><p>Pilar Ackerman</p></td>
<td><p>7/2/2012 10:00 AM</p></td>
</tr>
</tbody>
</table>


会議を開催した一意のユーザーの総数を把握するには、期間を変更します。たとえば、日単位ではなく月単位でデータを調べます。

</div>

<div>

## <a name="filters"></a>フィルター

フィルターは、細かく絞り込んだデータ セットを返したり、返されたデータをさまざまな方法で表示したりする方法として利用できます。たとえば、電話会議の概要レポートでは、データをグループ化する方法を選択できます。その場合は、電話会議が時間、日、週、または月の単位でグループ化されます。

次の表に、電話会議の概要レポートで使用できるフィルターを示します。

### <a name="conference-summary-report-filters"></a>電話会議の概要レポートのフィルター

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>名前</th>
<th>説明</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>開始</strong></p></td>
<td><p>時間範囲の開始日と開始時刻。データを時間単位で表示するには、次のように開始日と開始時刻の両方を入力します。</p>
<p>7/7/2012 1:00 PM</p>
<p>開始時刻を入力しないと、レポートは自動的に指定日の午前 12:00 に開始します。データを日単位で表示するには、次のように日付のみを入力します。</p>
<p>7/7/2012</p>
<p>週単位または月単位で表示するには、表示する週または月の任意の日付を入力します (その週または月の最初の日である必要はありません)。</p>
<p>7/3/2012</p>
<p>一週間は、日曜日から始まり、土曜日で終わるものとします。</p></td>
</tr>
<tr class="even">
<td><p><strong>終了</strong></p></td>
<td><p>時間範囲の終了日と終了時刻。データを時間単位で表示するには、次のように終了日と終了時刻の両方を入力します。</p>
<p>7/7/2012 1:00 PM</p>
<p>終了時刻を入力しないと、レポートは自動的に指定日の午前 12:00 に終了します。データを日単位で表示するには、次のように日付のみを入力します。</p>
<p>7/7/2012</p>
<p>週単位または月単位で表示するには、表示する週または月の任意の日付を入力します (その週または月の最初の日である必要はありません)。</p>
<p>7/3/2012</p>
<p>一週間は、日曜日から始まり、土曜日で終わるものとします。</p></td>
</tr>
<tr class="odd">
<td><p><strong>[間隔]</strong></p></td>
<td><p>時間間隔です。次のいずれかを選択します。</p>
<ul>
<li><p>毎時 (最大 25 時間の表示が可能)</p></li>
<li><p>毎日 (最大 31 日の表示が可能)</p></li>
<li><p>毎週 (最大 12 週の表示が可能)</p></li>
<li><p>毎月 (最大 12 か月の表示が可能)</p></li>
</ul>
<p>開始日と終了日が、選択されている期間内で許容される値の最大数を超えると、(開始日から起算した) 値の最大数のみが表示されます。 たとえば、開始日が7/7/2012 で、終了日が2/28/2012 の [日] 間隔を選択した場合は、8/7/2012 12:00 AM から 9/7/2012 12:00 AM (つまり、31日分のデータ) のデータが表示されます。</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics"></a>指標

次の表に、電話会議の概要レポートで提供される情報を示します。

### <a name="conference-summary-report-metrics"></a>電話会議の概要レポートの指標

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>名前</th>
<th>この項目での並べ替え</th>
<th>説明</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>[毎時]</strong></p>
<p><strong>[毎日]</strong></p>
<p><strong>[毎週]</strong></p>
<p><strong>[毎月]</strong></p></td>
<td><p>不可</p></td>
<td><p>フィルター ツール バーで選択した期間を示します。 場合によっては、特定の期間をクリックして、その期間の詳細情報を表示することもできます。 たとえば、毎日の間隔を使用していて、[7/7/2012] をクリックすると、その日付のユーザー登録アクティビティの時間の内訳が表示されます。</p></td>
</tr>
<tr class="even">
<td><p><strong>[電話会議の合計数]</strong></p></td>
<td><p>いいえ</p></td>
<td><p>実施された電話会議の総数です (会議の種類は区別されません)。この項目をクリックすると、選択した期間に対する電話会議動作状況レポートが表示されます。</p></td>
</tr>
<tr class="odd">
<td><p><strong>[参加者の合計数]</strong></p></td>
<td><p>いいえ</p></td>
<td><p>電話会議に参加したユーザーの総数です。この項目をクリックすると、選択した期間に対する電話会議動作状況レポートが表示されます。</p></td>
</tr>
<tr class="even">
<td><p><strong>[電話会議 1 件あたりの平均参加者数]</strong></p></td>
<td><p>いいえ</p></td>
<td><p>1 件の電話会議に参加した平均ユーザー数です。電話会議の合計数を参加者の合計数で割ることで求められます。</p></td>
</tr>
<tr class="odd">
<td><p><strong>[音声ビデオ会議の合計数]</strong></p></td>
<td><p>いいえ</p></td>
<td><p>音声またはビデオを利用した会議の総数です。</p></td>
</tr>
<tr class="even">
<td><p><strong>[音声ビデオ会議の合計時間 (分)]</strong></p></td>
<td><p>いいえ</p></td>
<td><p>音声ビデオ会議に費やされた合計時間を分単位で表したものです。</p>
<p>トータル A/V 会議の分単位の料金は、オーディオ/ビジュアル会議の種類 (A/V 会議など) をまとめたものです。IM 会議アプリ共有会議データ会議[PSTN 会議] を選びます。</p></td>
</tr>
<tr class="odd">
<td><p><strong>[音声ビデオ会議参加者の合計時間 (分)]</strong></p></td>
<td><p>いいえ</p></td>
<td><p>参加者が音声ビデオ会議に費やした合計時間を分単位で表したものです。たとえば、あるユーザーが音声ビデオ会議に 5 分費やし、別のユーザーが同じ会議に 3 分費やしたとします。この場合、会議参加者の合計時間は 8 分 (= 5 分 + 3 分) となります。</p></td>
</tr>
<tr class="even">
<td><p><strong>[音声ビデオ会議の平均時間 (分)]</strong></p></td>
<td><p>いいえ</p></td>
<td><p>音声ビデオ会議 1 件あたりの平均時間を分単位で表したものです。</p></td>
</tr>
<tr class="odd">
<td><p><strong>[電話会議の一意な開催者の合計数]</strong></p></td>
<td><p>いいえ</p></td>
<td><p>少なくとも 1 件の電話会議を開催したユーザーの総数です。複数の電話会議を開催したユーザーも、電話会議を 1 件しか開催していないユーザーと同じように、一意の開催者 1 人分としてカウントされます。</p></td>
</tr>
<tr class="even">
<td><p><strong>[電話会議メッセージの合計数]</strong></p></td>
<td><p>不可</p></td>
<td><p>電話会議中に送信されたインスタント メッセージの総数です。</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

