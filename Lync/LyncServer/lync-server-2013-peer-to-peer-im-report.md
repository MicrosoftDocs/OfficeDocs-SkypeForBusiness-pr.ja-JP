---
title: 'Lync Server 2013: ピアツーピア IM レポート'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Peer-to-Peer IM Report
ms:assetid: 19ec0145-2398-437b-8989-f780c179b798
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558620(v=OCS.15)
ms:contentKeyID: 48183533
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f44d25ec36788e6964ea81bde71e82f3746c5aee
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34825353"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="peer-to-peer-im-report-in-lync-server-2013"></a>Lync Server 2013 のピアツーピア IM レポート

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2012-11-01_

ピアツーピア IM レポートでは、ピアツーピア インスタント メッセージング (IM) セッションの傾向に関する情報が、プールおよび認証種類ごとに示されます。レポートでは、指定の時間内 (たとえば、日単位または時間単位) に行われたセッションの総数を表示したり、その時間内に送信されたインスタント メッセージの総数を表示したりできます。

<div>

## <a name="accessing-the-peer-to-peer-im-report"></a>ピアツーピア IM レポートへのアクセス

[ピアツーピアの IM] レポートにアクセスするには、 [Lync Server 2013 でピアツーピアアクティビティの概要レポート](lync-server-2013-peer-to-peer-activity-summary-report.md)を開いてから、次のいずれかの指標をクリックします。

  - ピアツーピア IM セッションの合計数

  - ピアツーピア IM メッセージの合計数

</div>

<div>

## <a name="making-the-best-use-of-the-peer-to-peer-im-report"></a>ピアツーピア IM レポートの利用

既定では、ピアツーピア IM レポートには、1 時間 (または、設定によっては 1 日) あたりのメッセージ数が示されます。ただし、1 日を時間単位のセッションで表示することもできます。この操作を行うには、[レポート] ウィンドウの右上隅にある [**パラメーターの表示/非表示**] をクリックし、[**報告元**] の一覧で [**セッション数**] をクリックします。

</div>

<div>

## <a name="filters"></a>フィルター

フィルターは、細かく絞り込んだデータ セットを返したり、返されたデータをさまざまな方法で表示したりする方法として利用できます。次の表に、ピアツーピア IM レポートで使用できるフィルターを示します。

### <a name="peer-to-peer-im-report-filters"></a>ピアツーピア IM レポートのフィルター

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
<p>週単位または月単位で表示するには、週または月の任意の日付を入力します (その週または月の最初の日である必要はありません)。</p>
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
<tr class="even">
<td><p><strong>報告元</strong></p></td>
<td><p>レポートで使用する値を指定します。次のいずれかを選択します。</p>
<ul>
<li><p>セッション数</p></li>
<li><p>メッセージ数</p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-peer-to-peer-im-session-by-pool"></a>ピアツーピア IM セッション (プール別) の指標

次の表に、ピアツーピア IM レポートで提供される情報を示します。

### <a name="metrics-for-peer-to-peer-im-session-by-pool"></a>ピアツーピア IM セッション (プール別) の指標

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
<td><p><strong>プール</strong></p></td>
<td><p>いいえ</p></td>
<td><p>レジストラープールまたはエッジサーバーの名前。</p></td>
</tr>
<tr class="even">
<td><p><strong>日付/時刻</strong></p></td>
<td><p>いいえ</p></td>
<td><p>セッションの発生日時。</p></td>
</tr>
<tr class="odd">
<td><p><strong>[合計]</strong></p></td>
<td><p>いいえ</p></td>
<td><p>セッション数またはメッセージ数の合計。</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-peer-to-peer-im-session-by-authentication-type"></a>ピアツーピア IM セッション (認証の種類別) の指標

次の表に、ピアツーピア セッションにおいて参加者によって使用される各認証の種類に対してピアツーピア IM レポートで提供される情報を示します。

### <a name="metrics-for-peer-to-peer-im-session-by-authentication-type"></a>ピアツーピア IM セッション (認証の種類別) の指標

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
<td><p><strong>[認証の種類]</strong></p></td>
<td><p>不可</p></td>
<td><p>セッション参加者によって使用される認証の種類。通常、値は次のいずれかです。</p>
<ul>
<li><p>Enterprise</p></li>
<li><p>Federated</p></li>
<li><p>PIC</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><strong>[日付/時刻]</strong></p></td>
<td><p>いいえ</p></td>
<td><p>セッションの発生日時。</p></td>
</tr>
<tr class="odd">
<td><p><strong>[合計]</strong></p></td>
<td><p>いいえ</p></td>
<td><p>セッション数またはメッセージ数の合計。</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

