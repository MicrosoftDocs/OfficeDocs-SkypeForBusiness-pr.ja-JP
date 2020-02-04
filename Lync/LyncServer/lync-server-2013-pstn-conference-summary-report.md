---
title: 'Lync Server 2013: PSTN 会議の概要レポート'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: PSTN Conference Summary Report
ms:assetid: 8e2f0862-4dfa-4c2b-bf8d-ad71419f15d2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615014(v=OCS.15)
ms:contentKeyID: 48184764
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f8cd36f651a84b25f7e8163a8cfc40aff5162f90
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41724797"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="pstn-conference-summary-report-in-lync-server-2013"></a>Lync Server 2013 の PSTN 会議の概要レポート

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2012-10-22_

Microsoft Lync Server 2013 の PSTN 会議は、PSTN (公衆交換電話網) 電話を使って、少なくとも1人の参加者がオーディオ部分にダイヤルインする会議です。 (PSTN 電話とは、"固定電話"、携帯電話、またはボイスオーバー IP を使用しないその他の任意の電話のことです)。監視レポートでは PSTN 会議と呼ばれていますが、このような会議は、一般的にダイヤルイン会議と呼ばれることがあります。

PSTN 電話会議の概要レポートは、組織で開催されるすべての PSTN 電話会議 (つまり、少なくとも 1 人のダイヤルイン ユーザーがいたすべての電話会議) に関する情報を提供します。レポートには、PSTN 電話会議の総数、これらの電話会議に参加した人数の合計、およびおそらく最も重要なダイヤルイン ユーザーの総数 (PSTN 参加者の合計数指標) に関する情報が含まれます。

<div>

## <a name="accessing-the-pstn-conference-summary-report"></a>PSTN 電話会議の概要レポートへのアクセス

PSTN 電話会議の概要レポートには、監視レポートのホーム ページからのみアクセスできます。このレポートは、他のどのレポートともリンクされていません。個々のエンドポイントがこの情報の送信を担当することを理由の一部として、PSTN 電話会議の詳細な通話情報は取得できません。PSTN 電話は、通話詳細情報を追跡または送信できません。

</div>

<div>

## <a name="making-the-best-use-of-the-pstn-conference-summary-report"></a>PSTN 電話会議の概要レポートの最適な利用

ダイヤルインユーザーを含むすべての会議の割合を判断するには、PSTN 会議の合計数と、 [Lync Server 2013 の [会議の概要] レポート](lync-server-2013-conference-summary-report.md)で検出された会議の評価指標の合計の値とを比較します。

必要な数の PSTN 会議が表示されない場合は、ダイヤルインユーザーを許可する会議を開催できるかどうかは、ユーザーに割り当てられている会議ポリシーによって異なることに注意してください。ほとんどのユーザーが PS を保持することを許可されている場合は、次の点に注意してください。TN 会議には、ほとんどの PSTN 会議があります。 会議ポリシー (該当する場合) が、Lync Server 管理シェル内から次のコマンドを実行して、PSTN 会議をスケジュールできるかどうかを簡単に確認できます。

    Get-CsConferencingPolicy | Select-Object Identity, EnableDialInConferencing

この結果、次のようなデータが返されます。

    Identity                                EnableDialInConferencing
    --------                                ------------------------
    Global                                                      True
    site:Redmond                                               False
    site:Dublin                                                False
    Tag:RedmondDialInUsers                                      True
    Tag:DublinDialInUsers                                       True

この結果、次のようなデータが返されます。

</div>

<div>

## <a name="filters"></a>フィルター

フィルターは、細かく絞り込んだデータ セットを返したり、返されたデータをさまざまな方法で表示したりする方法として利用できます。 たとえば、PSTN 電話会議の概要レポートでは、データをグループ化する方法を選択できます。 その場合は、電話会議が時間、日、週、または月の単位でグループ化されます。

次の表に、PSTN 電話会議の概要レポートで使用できるフィルターを示します。

### <a name="pstn-conference-summary-report-filters"></a>PSTN 電話会議の概要レポートのフィルター

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
<p>入力した開始日と終了日が選択した間隔で使用できる値の最大数を超える場合は、最大数の値 (開始日からカウント) のみが表示されます。 たとえば、開始日が7/7/2012 で、終了日が2/28/2012 の [日] 間隔を選択した場合は、8/7/2012 12:00 AM から 9/7/2012 12:00 AM (つまり、31日分のデータ) のデータが表示されます。</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics"></a>指標

次の表に、PSTN 電話会議の概要レポートの情報を示します。

### <a name="pstn-conference-summary-report-metrics"></a>PSTN 電話会議の概要レポートの指標

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
<td><p>選択されている時間間隔を示します。 必要に応じて、特定の時間間隔をクリックして、その間隔の詳細な情報を表示できます。 たとえば、毎日の間隔を使用していて、[7/7/2012] をクリックすると、その日付のユーザー登録アクティビティの時間の内訳が表示されます。</p></td>
</tr>
<tr class="even">
<td><p><strong>[PSTN 電話会議の合計数]</strong></p></td>
<td><p>いいえ</p></td>
<td><p>ダイヤルイン アクセスが許可された電話会議の総数です。</p></td>
</tr>
<tr class="odd">
<td><p><strong>[参加者の合計数]</strong></p></td>
<td><p>いいえ</p></td>
<td><p>ダイヤルイン アクセスが許可された電話会議に参加したユーザーの総数です。</p></td>
</tr>
<tr class="even">
<td><p><strong>[音声ビデオ会議の合計時間 (分)]</strong></p></td>
<td><p>いいえ</p></td>
<td><p>音声ビデオ会議の合計時間です。</p></td>
</tr>
<tr class="odd">
<td><p><strong>[音声ビデオ会議参加者の合計時間 (分)]</strong></p></td>
<td><p>いいえ</p></td>
<td><p>参加者が音声ビデオ会議に費やした合計時間です。たとえば、ある参加者が音声ビデオ会議に 5 分費やし、別の参加者が同じ会議に 3 分費やした場合、音声ビデオ会議参加者の合計時間は 8 分になります。</p></td>
</tr>
<tr class="even">
<td><p><strong>[PSTN 参加者の合計数]</strong></p></td>
<td><p>いいえ</p></td>
<td><p>ダイヤルイン アクセスが許可された電話会議にダイヤルインしたユーザーの総数です。</p></td>
</tr>
<tr class="odd">
<td><p><strong>[PSTN 参加者の合計時間 (分)]</strong></p></td>
<td><p>いいえ</p></td>
<td><p>ダイヤルイン ユーザーが電話会議に費やした合計時間です。たとえば、あるダイヤルイン参加者が電話会議に 5 分費やし、別の参加者が同じ電話会議に 3 分費やした場合、PSTN 参加者の合計時間は 8 分になります。</p></td>
</tr>
<tr class="even">
<td><p><strong>[一意の電話会議開催者]</strong></p></td>
<td><p>不可</p></td>
<td><p>ダイヤルイン アクセスが許可された電話会議を少なくとも 1 件開催したユーザーの総数です。複数の電話会議を開催したユーザーも、電話会議を 1 件しか開催していないユーザーと同じように、一意の開催者 1 人分としてカウントされます。</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

