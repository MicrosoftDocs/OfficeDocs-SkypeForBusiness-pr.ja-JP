---
title: 'Lync Server 2013: ピアツーピア音声およびビデオレポート'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Peer-to-Peer Voice and Video Report
ms:assetid: e17c36b5-5a2f-4673-9696-3b2d31c2bb2f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615040(v=OCS.15)
ms:contentKeyID: 48185535
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 974f403f65b494964affc4fbdc4880820ecb2db2
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2020
ms.locfileid: "42038659"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="peer-to-peer-voice-and-video-report-in-lync-server-2013"></a>Lync Server 2013 のピアツーピア音声およびビデオレポート

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2012-10-21_

ピアツーピア音声およびビデオ レポートは、指定した期間における音声通話やビデオ通話の配信に関する詳細を提供します (たとえば、1 時間あたりの通話回数または 1 日あたりの通話回数)。また、行われたすべての音声通話とビデオ通話を表示したり、正常な通話または失敗した通話のみを表示したりできます。レポートでは、次のグループに分割した通話情報が表示されます。

  - プール別の通話

  - 通話の種類ごとの通話 (たとえば、Lync から Lync への通話、および PSTN ネットワーク上の個人への Lync 通話)

  - アクセスの種類別の通話 (内部ネットワークにログオンしているユーザー、外部ネットワークにログオンしているユーザー)

  - 仲介サーバーあたりの通話

<div>

## <a name="to-access-the-peer-to-peer-voice-and-video-report"></a>ピアツーピア音声およびビデオ レポートにアクセスするには

ピアツーピア アクティビティ概要レポートを開き、次のいずれかの指標をクリックすることによってのみ、ピアツーピア音声およびビデオ レポートにアクセスできます。

  - ピアツーピア音声セッションの合計数

  - ピアツーピア音声セッションの合計時間

  - ピアツーピア ビデオ セッションの合計数

  - ピアツーピア ビデオ セッションの合計時間

</div>

<div>

## <a name="to-make-the-best-use-of-the-peer-to-peer-voice-and-video-report"></a>ピアツーピア音声およびビデオ レポートを最大限に活用するには

ピアツーピア音声およびビデオ レポートをフィルターするさまざまな方法があります。ただし、既定では、これらのフィルター オプションは非表示になっています。使用できるフィルター オプションを表示するには、[レポート] ウィンドウの右上隅にある [**パラメータの表示/非表示**] ボタンをクリックします。

</div>

<div>

## <a name="filters"></a>フィルター

フィルターは、細かく絞り込んだデータ セットを返したり、データをさまざま方法で表示したりする方法として利用できます。次の表に、ピアツーピア音声およびビデオ レポートで使用できるフィルターを示します。

### <a name="peer-to-peer-voice-and-video-report-filters"></a>ピアツーピア音声およびビデオ レポートのフィルター

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
<td><p><strong>From</strong></p></td>
<td><p>時間範囲の開始日と開始時刻。データを時間単位で表示するには、次のように開始日と開始時刻の両方を入力します。</p>
<p>2012/7/7 13:00</p>
<p>開始時刻を入力しないと、レポートは自動的に指定日の午前 12:00 に開始します。データを日単位で表示するには、次のように日付のみを入力します。</p>
<p>7/7/2012</p>
<p>週単位または月単位で表示するには、表示する週または月の任意の日付を入力します (その週または月の最初の日である必要はありません)。</p>
<p>7/3/2012</p>
<p>週は、常に日曜日から土曜日までです。</p></td>
</tr>
<tr class="even">
<td><p><strong>To</strong></p></td>
<td><p>時間範囲の終了日と終了時刻。データを時間単位で表示するには、次のように終了日と終了時刻の両方を入力します。</p>
<p>7/7/2012 1:00 PM</p>
<p>終了時刻を入力しないと、レポートは自動的に指定日の午前 12:00 に終了します。データを日単位で表示するには、次のように日付のみを入力します。</p>
<p>7/7/2012</p>
<p>週単位または月単位で表示するには、表示する週または月の任意の日付を入力します (その週または月の最初の日である必要はありません)。</p>
<p>7/3/2012</p>
<p>週は、常に日曜日から土曜日までです。</p></td>
</tr>
<tr class="odd">
<td><p><strong>間隔</strong></p></td>
<td><p>時間間隔です。次のいずれかを選択します。</p>
<ul>
<li><p>時間単位 (最大 25 時間の表示が可能)</p></li>
<li><p>日単位 (最大 31 日の表示が可能)</p></li>
<li><p>週単位 (最大 12 週の表示が可能)</p></li>
<li><p>月単位 (最大 12 か月の表示が可能)</p></li>
</ul>
<p>入力した開始日と終了日が選択した間隔で使用できる値の最大数を超える場合は、最大数の値 (開始日からカウント) のみが表示されます。たとえば、開始日と終了日をそれぞれ 7/7/2012 (2012 年 7 月 7 日)、2/28/2012 (2012 年 2 月 28 日) として毎日の間隔を選択しても、2012 年 8 月 7 日の午前 12:00 から 2012 年 9 月 7 日の午前 12:00 までの日付のデータ (つまり、合計 31 日分のデータのみ) が表示されることになります。</p></td>
</tr>
<tr class="even">
<td><p>[<strong>メディアの種類</strong>]</p></td>
<td><p>セッションで使用されたメディアの種類を示します。次のいずれかを選択します。</p>
<ul>
<li><p>Both/フォーム/データシート</p></li>
<li><p>オーディオ</p></li>
<li><p>ビデオ</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p>[<strong>通話のディスポジション</strong>]</p></td>
<td><p>セッションの成功または失敗を示します。次のいずれかを選択します。</p>
<ul>
<li><p>いずれ</p></li>
<li><p>成功した通話</p></li>
<li><p>失敗した通話</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>[<strong>報告元</strong>]</p></td>
<td><p>レポートで使用する値を指定します。次の中から選択します。</p>
<ul>
<li><p>セッション数</p></li>
<li><p>通話の分数</p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-peer-to-peer-voice-and-video-activity-by-pool"></a>プール別のピアツーピア音声およびビデオ アクティビティの指標

次の表に、ピアツーピア音声およびビデオ レポートで各プールについて表示される情報を示します。

### <a name="metrics-for-peer-to-peer-voice-and-video-activity-by-pool"></a>プール別のピアツーピア音声およびビデオ アクティビティの指標

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
<td><p><strong>Pool</strong></p></td>
<td><p>いいえ</p></td>
<td><p>呼び出しに使用されたレジストラープールまたはエッジサーバーの名前。</p></td>
</tr>
<tr class="even">
<td><p><strong>日付/時刻</strong></p></td>
<td><p>いいえ</p></td>
<td><p>通話が行われた日付と時間。</p></td>
</tr>
<tr class="odd">
<td><p><strong>合計</strong></p></td>
<td><p>いいえ</p></td>
<td><p>セッション数またはメッセージ数の合計。</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-peer-to-peer-voice-and-video-activity-by-call-type"></a>通話の種類別のピアツーピア音声およびビデオ アクティビティの指標

次の表に、ピアツーピア音声およびビデオ レポートで各種類の通話について表示される情報を示します。

### <a name="metrics-for-peer-to-peer-voice-and-video-activity-by-call-type"></a>通話の種類別のピアツーピア音声およびビデオ アクティビティの指標

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
<td><p>[<strong>通話の種類</strong>]</p></td>
<td><p>いいえ</p></td>
<td><p>行われた通話の種類を示します。値は次のいずれかです。</p>
<ul>
<li><p>Uc ツー UC</p></li>
<li><p>UC ツー PSTN</p></li>
<li><p>PSTN から UC</p></li>
<li><p>PSTN ツー PSTN</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><strong>日付/時刻</strong></p></td>
<td><p>いいえ</p></td>
<td><p>通話が行われた日付と時間。</p></td>
</tr>
<tr class="odd">
<td><p><strong>合計</strong></p></td>
<td><p>いいえ</p></td>
<td><p>セッション数またはメッセージ数の合計。</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-peer-to-peer-voice-and-video-activity-by-access-type"></a>アクセスの種類別のピアツーピア音声およびビデオ アクティビティの指標

次の表に、ピアツーピア音声およびビデオ レポートで各種類のアクセスについて表示される情報を示します。

### <a name="metrics-for-peer-to-peer-voice-and-video-activity-by-access-type"></a>アクセスの種類別のピアツーピア音声およびビデオ アクティビティの指標

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
<td><p>[<strong>動作状況の種類</strong>]</p></td>
<td><p>いいえ</p></td>
<td><p>クライアントが通話時に内部ネットワークにログオンしたか、外部ネットワークにログオンしたかを示します。通常は次のいずれかの値です。</p>
<ul>
<li><p>内部</p></li>
<li><p>External</p></li>
<li><p>混合</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><strong>日付/時刻</strong></p></td>
<td><p>いいえ</p></td>
<td><p>通話が行われた日付と時間。</p></td>
</tr>
<tr class="odd">
<td><p><strong>合計</strong></p></td>
<td><p>いいえ</p></td>
<td><p>セッション数またはメッセージ数の合計。</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-peer-to-peer-voice-and-video-activity-by-mediation-server"></a>仲介サーバー別のピアツーピア音声およびビデオ アクティビティの指標

次の表に、ピアツーピア音声およびビデオレポートで仲介サーバーごとに提供される情報を示します。

### <a name="metrics-for-peer-to-peer-voice-and-video-activity-by-mediation-server"></a>仲介サーバー別のピアツーピア音声およびビデオ アクティビティの指標

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
<td><p>[<strong>仲介サーバー</strong>]</p></td>
<td><p>いいえ</p></td>
<td><p>仲介サーバーの名前。</p></td>
</tr>
<tr class="even">
<td><p><strong>日付/時刻</strong></p></td>
<td><p>いいえ</p></td>
<td><p>通話が行われた日付と時間。</p></td>
</tr>
<tr class="odd">
<td><p><strong>合計</strong></p></td>
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

