---
title: 'Lync Server 2013: ピアツーピアアクティビティの概要レポート'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Peer-to-Peer Activity Summary Report
ms:assetid: e829a21e-9dfa-46ba-9b5b-077c175d6586
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615041(v=OCS.15)
ms:contentKeyID: 48185884
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 62bdd1203db471de770ed56cf6377d7a3c651649
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34825388"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="peer-to-peer-activity-summary-report-in-lync-server-2013"></a>Lync Server 2013 のピアツーピアアクティビティの概要レポート

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2012-10-21_

ピアツーピア アクティビティ概要レポートでは、ピアツーピア通信セッションの概要が示されます。 ピアツーピアセッションでは通常、2人のユーザーのみが関係し、Lync Server 会議サービスを使う必要はありません。 これに対して、会議は通常、3人以上のユーザーを対象としており、Microsoft Lync Server 2013 会議サービスを使用する必要があります。 会議アクティビティは、会議概要レポートで報告されます。

ピアツーピア アクティビティ概要レポートは、次のような質問に答えるときに役立ちます。

  - 通常、ユーザーはピアツーピア インスタント メッセージを 1 日に何通送信しますか?

  - ユーザーは、実際に Lync Server アプリケーション共有機能とファイル転送機能を利用していますか。

  - ユーザーが、ネットワークの速度が 1 日の特定の時刻で遅くなるようだと訴えています。これらの時間帯でピアツーピアの音声ビデオセッションに費やされた時間は何分ですか?

<div>

## <a name="accessing-the-peer-to-peer-activity-summary-report"></a>ピアツーピア アクティビティ概要レポートにアクセスする

監視レポートのホーム ページからピアツーピア アクティビティ概要レポートにアクセスします。 次のメトリックのいずれかをクリックして、 [Lync Server 2013 でピアツーピア IM レポート](lync-server-2013-peer-to-peer-im-report.md)を開きます。

  - ピアツーピア IM セッションの合計数

  - ピアツーピア IM メッセージの合計数

同様に、ピアツーピア音声およびビデオ レポートを開くには、次のいずれかの指標をクリックします。

  - ピアツーピア音声セッションの合計数

  - ピアツーピア音声セッションの合計時間 (分)

  - ピアツーピア音声セッションの合計数

  - ピアツーピア音声セッションの合計時間 (分)

</div>

<div>

## <a name="making-the-best-use-of-the-peer-to-peer-activity-summary-report"></a>ピアツーピア アクティビティ概要レポートを最大限に活用する

ピアツーピア アクティビティ概要レポートの下部には、ピアツーピア IM セッションの合計数やピアツーピア IM メッセージの合計数などの、合計の指標が表示されます。これにより、レポート本文にある詳細情報の概要が示されます。

</div>

<div>

## <a name="filters"></a>フィルター

フィルターは、細かく絞り込んだデータ セットを返したり、返されたデータをさまざまな方法で表示したりする方法として利用できます。たとえば、ピアツーピア アクティビティ概要レポートでは、データをグループ化する方法を選択できます。この場合は、時間、日、週、または月を基準にアクティビティがグループ化されます。

次の表に、ピアツーピア アクティビティ概要レポートで使用できるフィルターを示します。

### <a name="peer-to-peer-activity-summary-report-filters"></a>ピアツーピア アクティビティ概要レポートのフィルター

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
<p>7/17/12012 1:00 PM</p>
<p>開始時刻を入力しないと、レポートは自動的に指定日の午前 12:00 に開始します。データを日単位で表示するには、次のように日付のみを入力します。</p>
<p>7/17/12012</p>
<p>週単位または月単位で表示するには、表示する週または月の任意の日付を入力します (その週または月の最初の日である必要はありません)。</p>
<p>7/13/2012</p>
<p>一週間は、日曜日から始まり、土曜日で終わるものとします。</p></td>
</tr>
<tr class="even">
<td><p><strong>終了</strong></p></td>
<td><p>時間範囲の終了日と終了時刻。データを時間単位で表示するには、次のように終了日と終了時刻の両方を入力します。</p>
<p>7/17/12012 1:00 PM</p>
<p>終了時刻を入力しないと、レポートは自動的に指定日の午前 12:00 に終了します。データを日単位で表示するには、次のように日付のみを入力します。</p>
<p>7/17/12012</p>
<p>週単位または月単位で表示するには、表示する週または月の任意の日付を入力します (その週または月の最初の日である必要はありません)。</p>
<p>7/13/2012</p>
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
<p>入力した開始日と終了日が選択した間隔で使用できる値の最大数を超える場合は、最大数の値 (開始日からカウント) のみが表示されます。 たとえば、開始日が7/17/12012 で、終了日が2/28/2012 の [日] 間隔を選択した場合は、8/7/12012 12:00 AM から 9/7/12012 12:00 AM (つまり、31日分のデータ) のデータが表示されます。</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics"></a>指標

次の表に、ピアツーピア アクティビティ概要レポートで提供される情報を示します。

### <a name="peer-to-peer-activity-summary-report-metrics"></a>ピアツーピア アクティビティ概要レポートの指標

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
<td><p>いいえ</p></td>
<td><p>フィルター ツール バーで選択した期間を示します。 場合によっては、特定の期間をクリックして、その期間の詳細情報を表示することもできます。 たとえば、毎日の間隔を使用していて、[7/17/12012] をクリックすると、その日付のユーザー登録アクティビティの時間の内訳が表示されます。</p></td>
</tr>
<tr class="even">
<td><p><strong>ピアツーピア セッションの合計数</strong></p></td>
<td><p>いいえ</p></td>
<td><p>実行されたピアツーピア セッションの合計数。セッションの種類は問いません。</p></td>
</tr>
<tr class="odd">
<td><p><strong>ピアツーピア IM セッションの合計数</strong></p></td>
<td><p>いいえ</p></td>
<td><p>ピアツーピア インスタント メッセージング (IM) セッションの合計数。この項目をクリックすると、選択した時間のピアツーピア IM レポートが表示されます。</p></td>
</tr>
<tr class="even">
<td><p><strong>ピアツーピア IM メッセージの合計数</strong></p></td>
<td><p>いいえ</p></td>
<td><p>ピアツーピア セッションで送信されたインスタント メッセージの合計数。この項目をクリックすると、選択した時間のピアツーピア IM レポートが表示されます。</p></td>
</tr>
<tr class="odd">
<td><p><strong>ピアツーピア音声セッションの合計数</strong></p></td>
<td><p>いいえ</p></td>
<td><p>ピアツーピア音声通話の合計数。このフィールドをクリックすると、選択した時間のピアツーピア音声およびビデオ レポートが表示されます。</p></td>
</tr>
<tr class="even">
<td><p><strong>ピアツーピア音声セッションの合計時間 (分)</strong></p></td>
<td><p>不可</p></td>
<td><p>ピアツーピア音声セッションの合計時間。 この項目をクリックすると、選択した時間のピアツーピア音声およびビデオ レポートが表示されます。</p></td>
</tr>
<tr class="odd">
<td><p><strong>ピアツーピア音声セッションの平均時間 (分)</strong></p></td>
<td><p>いいえ</p></td>
<td><p>ピアツーピア音声セッションの平均時間。音声セッションの合計時間を音声セッションの合計数で割ることにより計算されます。</p></td>
</tr>
<tr class="even">
<td><p><strong>ピアツーピア ビデオ セッションの合計数</strong></p></td>
<td><p>いいえ</p></td>
<td><p>ピアツーピア ビデオ通話の合計数。ビデオ セッションは音声セッションとしてもカウントされることに注意してください。各ビデオ セッションは、1 つのビデオ セッションおよび 1 つの音声セッションとしてカウントされます。この項目をクリックすると、選択した時間のピアツーピア音声およびビデオ レポートが表示されます。</p></td>
</tr>
<tr class="odd">
<td><p><strong>ピアツーピア ビデオ セッションの合計時間 (分)</strong></p></td>
<td><p>いいえ</p></td>
<td><p>ピアツーピア ビデオ セッションの合計時間。この項目をクリックすると、選択した時間のピアツーピア音声およびビデオ レポートが表示されます。</p></td>
</tr>
<tr class="even">
<td><p><strong>ピアツーピア ビデオ セッションの平均時間 (分)</strong></p></td>
<td><p>いいえ</p></td>
<td><p>ピアツーピア ビデオ セッションの平均時間。ビデオ セッションの合計時間をビデオ セッションの合計数で割ることにより計算されます。</p></td>
</tr>
<tr class="odd">
<td><p><strong>ピアツーピア ファイル送信セッションの合計数</strong></p></td>
<td><p>いいえ</p></td>
<td><p>ファイル送信を行ったピアツーピア セッションの合計数。</p></td>
</tr>
<tr class="even">
<td><p><strong>ピアツーピア アプリケーション共有セッションの合計数</strong></p></td>
<td><p>不可</p></td>
<td><p>アプリケーション共有を行ったピアツーピア セッションの合計数。</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

