---
title: 'Lync Server 2013: 会議アクティビティレポート'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Conference Activity Report
ms:assetid: 22ddb509-af16-4fc8-9b98-6f58caa6f37e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558627(v=OCS.15)
ms:contentKeyID: 48183618
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f96ddc5dfda18fa1d96903eb5755481f76853c06
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34840504"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="conference-activity-report-in-lync-server-2013"></a>Lync Server 2013 での会議アクティビティレポート

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2012-10-22_

電話会議動作状況レポートを使用すると、たとえば 1 日に開催されている電話会議の数や、その時間帯に関する質問に簡単に答えることができます。 このような情報はそれ自体が有用であるだけでなく、トラブルシューティング ツールとしても役立ちます。 たとえば、昼頃になるとネットワークが著しく遅くなるという苦情がユーザーから寄せられているとします。 会議アクティビティレポートの概要については、考えられる理由の1つとして、10:00 AM と 2:00 PM の間でスケジュールされている会議の数を確認します。

ネットワーク速度が遅いために問題が起きている場合は、一部の電話会議の予定をトラフィックが少ない時間帯にずらしてもらうようにユーザーに働きかけることができます。

<div>

## <a name="accessing-the-conference-activity-report"></a>電話会議動作状況レポートにアクセスする

会議アクティビティレポートには、 [Lync Server 2013 の [会議の概要] レポート](lync-server-2013-conference-summary-report.md)からアクセスできます。次のいずれかの指標をクリックします。

  - 電話会議の合計数

  - 参加者の合計数

</div>

<div>

## <a name="making-the-best-use-of-the-conference-activity-report"></a>電話会議動作状況レポートを最大限に活用する

既定では、電話会議動作状況レポートには指定した期間における電話会議の合計数 (たとえば、1 日あたりの電話会議の合計数や、1 日の 1 時間あたりの電話会議の合計数) が表示されます。ただし、その期間における参加者の合計数や、参加者の合計分数を表示することもできます。この操作を行うには、[パラメーターの表示/非表示] ボタンをクリックしてフィルター オプションを表示し、[報告元] ドロップダウン リストから次のいずれかを選択します。

  - 参加者数

  - 参加者の分数

  - 電話会議数

</div>

<div>

## <a name="filters"></a>フィルター

フィルターは、細かく絞り込んだデータ セットを返したり、返されたデータをさまざまな方法で表示したりする方法として利用できます。次の表に、電話会議動作状況レポートで使用できるフィルターを示します。

### <a name="conference-activity-report-filters"></a>電話会議動作状況レポートのフィルター

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
<tr class="even">
<td><p><strong>[報告元]</strong></p></td>
<td><p>レポートで使用する値を指定します。次の中から選択します。</p>
<ul>
<li><p>参加者数</p></li>
<li><p>参加者の分数</p></li>
<li><p>電話会議数</p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-conferences-by-pool"></a>電話会議 (プール別) の指標

次の表に、プールごとの電話会議動作状況レポートでの情報を示します。

### <a name="metrics-for-conferences-by-pool"></a>電話会議 (プール別) の指標

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
<td><p>電話会議で使用されたレジストラー プールまたはエッジ サーバーの名前。</p></td>
</tr>
<tr class="even">
<td><p><strong>日付/時刻</strong></p></td>
<td><p>いいえ</p></td>
<td><p>電話会議の開始日時。</p></td>
</tr>
<tr class="odd">
<td><p><strong>[合計]</strong></p></td>
<td><p>いいえ</p></td>
<td><p>参加者総数、参加者総時間 (分)、電話会議総数。</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-conferences-by-server-type"></a>電話会議 (サーバーの種類別) の指標

次の表に、サーバーの種類ごとの電話会議動作状況レポートでの情報を示します。

### <a name="metrics-for-conferences-by-server-type"></a>電話会議 (サーバーの種類別) の指標

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
<td><p><strong>[会議サーバーの種類]</strong></p></td>
<td><p>不可</p></td>
<td><p>電話会議で使用されたサーバーの種類。通常は、次のいずれかです。</p>
<ul>
<li><p>Web 会議サーバー</p></li>
<li><p>IM 会議サービス</p></li>
<li><p>テレフォニー会議サービス</p></li>
<li><p>音声ビデオ会議サーバー</p></li>
<li><p>アプリケーション共有</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><strong>[日付/時刻]</strong></p></td>
<td><p>いいえ</p></td>
<td><p>電話会議の開始日時。</p></td>
</tr>
<tr class="odd">
<td><p><strong>[合計]</strong></p></td>
<td><p>いいえ</p></td>
<td><p>参加者総数、参加者総時間 (分)、電話会議総数。</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

