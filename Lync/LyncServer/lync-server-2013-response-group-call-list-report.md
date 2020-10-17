---
title: 'Lync Server 2013: 応答グループの通話リストレポート'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Response Group Call List Report
ms:assetid: a2d3e08b-511b-4507-abba-8ff71aa27c8e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615443(v=OCS.15)
ms:contentKeyID: 48184954
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: abb3a1b13bf7357a0a2ee31180557911fc37ae0e
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/16/2020
ms.locfileid: "48511764"
---
# <a name="response-group-call-list-report-in-lync-server-2013"></a>Lync Server 2013 の応答グループの通話リストレポート

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2013-02-22_

応答グループアプリケーションは、Microsoft Lync Server 2013 が、ダイヤルされた番号と、必要に応じて発信者の一連の質問に対する応答に基づいて、電話での通話に応答してルーティングする方法を提供します。 通常、応答グループの通話は個々のユーザーにルーティングされませんが、代わりにエージェントグループと呼ばれるユーザーのチームにルーティングされます。 たとえば、ユーザーがヘルプデスクの電話番号を呼び出すと、Lync Server 2013 は、その通話を最初に利用可能なヘルプデスクエージェントに自動的にルーティングすることができます。 または、Lync Server は一連の質問をすることができます (ハードウェアに問題がある場合は1を押します)。 ソフトウェアに問題がある場合は、2を押します。 ネットワークの問題が発生している場合は、3を押します。)その後、質問に対する回答に基づいて、最適なヘルプデスクエージェントに通話をルーティングします。

応答グループの通話リスト レポートは、特定の期間に特定の種類の通話に対して行われた通話のコレクションです。応答グループの使用レポート (応答グループの通話リスト レポートを開くには先にこのレポートを開く必要があります) では、次の種類の通話が認識されます。

  - **受信した通話**。応答グループ アプリケーションのすべてのインスタンスで受信した通話の合計数。

  - **正常な通話**。 応答グループアプリケーションによって処理された通話の合計数。

  - **提供された通話**。応答グループ エージェントによって転送された通話の合計数。

  - **応答した通話**。応答グループ エージェントが実際に応答した通話の合計数。

  - 破棄された通話のパーセンテージ。 応答グループ アプリケーションによって受信されたが、エージェントが応答しなかった通話のパーセンテージ。 この値は、受信した通話数から応答した通話数を引いた値を受信した通話数で割って計算されます。 たとえば、受信した通話数が 10 件、応答した通話数が 7 件の場合、10 から 7 を引いて 3 件が応答のない通話数として残ります。 この値を 10 で割ると、破棄された通話のパーセンテージは 30% になります。

  - **転送された通話**。キューのタイムアウトまたはキューのオーバーフローによって転送された、応答グループの通話の合計数。

<div>

## <a name="accessing-the-response-group-call-list-report"></a>応答グループの通話リスト レポートへのアクセス

応答グループの通話リストレポートにアクセスするには、 [Lync Server 2013 の応答グループの使用状況レポート](lync-server-2013-response-group-usage-report.md)にある次のいずれかの指標をクリックする必要があります。

  - [受信した通話]

  - [正常な通話]

  - [提供された通話]

  - [応答した通話]

  - 転送された通話

</div>

<div>

## <a name="making-the-best-use-of-the-response-group-call-list-report"></a>応答グループの通話リスト レポートの活用

応答グループの通話リスト レポートでは、表示されるデータを、特定の応答グループ ワークフローに関連する通話のみに限定することができます。そのためには、[ワークフロー URI] ボックスにワークフロー URI (ワークフローの SIP アドレス) を入力する必要があります。ただし、その前に、まず [ワークフロー URI] ボックスを表示する必要があります。応答グループの通話リスト レポートのフィルター オプションを表示するには、レポート ウィンドウの左上の部分にある [パラメーターの表示/非表示] ボタンをクリックします。

応答グループの通話リストで応答コードまたは診断 ID の上にマウス ポインターを置いてもこれらの指標の情報は表示されません。 詳細が必要な場合は、応答コードや診断 ID を書き留めておいて、 [Lync Server 2013 のトップエラーレポート](lync-server-2013-top-failures-report.md)でこれらの値を検索することがあります。

たとえば、最も多くの通話を受信したワークフローはどれかを調べるには、次の操作を行います。

1.  応答グループの使用レポートで、目的の期間を設定し、[受信した通話] 指標をクリックします。応答グループの通話リスト レポートが開きます。

2.  応答グループの通話リスト レポートに表示されたデータをエクスポートします。たとえば、データを Microsoft Excel 形式でエクスポートして、Excel で CSV (コンマ区切り値) ファイルに変換することができます。

3.  Windows PowerShell を使用して分析を実行します。

たとえば、データを C: データ応答グループの通話リストReport.csv に保存した場合、 \\ \\ \_ \_ \_ \_ 次のコマンドを使用して、レポートに一覧表示されている各ワークフローの受信呼び出しの合計数を取得できます。

    $calls = Import-Csv -Path "C:\ Data\Response_Group_Call_List_Report.csv"
    $calls | Group-Object Workflow | Select-Object Count, Name | Sort-Object Count -Descending

次のような情報が表示されます。

    Count    Name
    -----    ----
      160    Redmond Help Desk
       47    Dublin Help Desk
       31    North America Customer Support
       16    EMEA Customer Support
       14    Employment Opportunities

</div>

<div>

## <a name="filters"></a>フィルター

フィルターは、細かく絞り込んだデータ セットを返したり、返されたデータをさまざま方法で表示したりする方法として利用できます。次の表に、応答グループの通話リスト レポートで使用できるフィルターを示します。

### <a name="response-group-call-list-report-filters"></a>応答グループの通話リスト レポートのフィルター

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
<p>7/7/2012 1:00 PM</p>
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
<td><p>[<strong>ワークフロー URI</strong>]</p></td>
<td><p>返されるデータを、指定されている応答グループ ワークフローに制限できます。このフィルターを使用するには、ワークフローの SIP アドレスを入力します。次に例を示します。</p>
<p>sip:helpdesk@litwareinc.com</p></td>
</tr>
<tr class="even">
<td><p><strong>通話</strong></p></td>
<td><p>次のいずれかの通話の種類を選択できます。</p>
<ul>
<li><p>受信した通話</p></li>
<li><p>正常な通話</p></li>
<li><p>提供された通話</p></li>
<li><p>応答した通話</p></li>
<li><p>転送された通話</p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics"></a>指標

次の表に、応答グループの通話リスト レポートで、応答グループ アプリケーションが受信した通話ごとに提供される情報を示します。

### <a name="response-group-call-list-report-metrics"></a>応答グループの通話リスト レポートの指標

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
<td><p><strong>Caller</strong></p></td>
<td><p>いいえ</p></td>
<td><p>発信者の SIP アドレス。</p></td>
</tr>
<tr class="even">
<td><p><strong>ワークフロー</strong></p></td>
<td><p>いいえ</p></td>
<td><p>応答グループ ワークフローの SIP アドレス。</p></td>
</tr>
<tr class="odd">
<td><p>[<strong>開始時刻</strong>]</p></td>
<td><p>いいえ</p></td>
<td><p>通話が開始された日時。</p></td>
</tr>
<tr class="even">
<td><p>[<strong>終了時刻</strong>]</p></td>
<td><p>いいえ</p></td>
<td><p>通話が終了した日時。</p></td>
</tr>
<tr class="odd">
<td><p>[<strong>応答コード</strong>]</p></td>
<td><p>いいえ</p></td>
<td><p>セッションが失敗したときに送信された SIP 応答コード。</p></td>
</tr>
<tr class="even">
<td><p>[<strong>診断 ID</strong>]</p></td>
<td><p>いいえ</p></td>
<td><p>SIP メッセージに (ms-diagnostics ヘッダーの形で) 添付された一意の識別子。多くの場合、この情報はトラブルシューティングに役立ちます。</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

