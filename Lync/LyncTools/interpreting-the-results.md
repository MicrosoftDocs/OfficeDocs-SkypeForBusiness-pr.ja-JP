---
title: 結果の解釈
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Interpreting the Results
ms:assetid: dd7f199f-7075-4d88-bb84-49a7e05eb593
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945608(v=OCS.15)
ms:contentKeyID: 51541433
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0dcb1d84392cf9f56f2996281eb53e798690ba1e
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41763299"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="interpreting-the-results"></a>結果の解釈

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2013-02-24_

Lync Server 2013 応力/パフォーマンスツール (LyncPerfTool) には、クライアントが何を実行しているのか、問題が発生しているかを理解するために使用できる多くのカウンターがあります。

<div>

## <a name="client-counters"></a>クライアントのカウンター

実行されている LyncPerfTool の各インスタンスには、カウンターの個別のインスタンスがあります。 それぞれのインスタンスには、そのプロセス ID による名前が付けられます。

クライアントが過負荷になっていると、問題が発生する可能性があります。 これらの問題を回避するには、次の操作を行います。

1.  クライアントコンピューターの CPU とメモリ使用量を監視します。 CPU が継続的に 90% 以上になっている場合は、ユーザーの数を減らします。

2.  メモリフットプリントが高すぎる場合は、ページファイルが十分でない場合に問題が発生する可能性があります。 コミット チャージがコンピューターの制限に達していないことを確認してください。 メモリの制限を使用している場合は、ページファイルのサイズを大きくするか、ユーザーの数を減らすことを検討してください。

次の表では、LyncPerfTool のパフォーマンスカウンターの主要な一覧を示します。

**一般情報**


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><strong>パフォーマンス カウンター</strong></th>
<th><strong>説明</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Time Spent in Minutes</p></td>
<td><p>プロセスの開始からの経過時間。</p></td>
</tr>
<tr class="even">
<td><p>Active Endpoints</p></td>
<td><p>現在サーバーに接続しているエンドポイントの数。</p></td>
</tr>
<tr class="odd">
<td><p>Failed Logons</p></td>
<td><p>エンドポイント サインインの合計失敗数。</p></td>
</tr>
<tr class="even">
<td><p>Logon Attempts</p></td>
<td><p>エンドポイント サインインの合計試行数。</p></td>
</tr>
<tr class="odd">
<td><p>Endpoints Disconnected</p></td>
<td><p>切断されたエンドポイントの合計数。</p></td>
</tr>
<tr class="even">
<td></td>
<td></td>
</tr>
</tbody>
</table>


**プレゼンス情報**


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><strong>パフォーマンス カウンター</strong></th>
<th><strong>説明</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>SetPresence Calls</p></td>
<td><p>プレゼンス変更の合計試行数。 プレゼンス変更のさまざまな種類については、SetPresence (プレゼンスの種類) Calls パフォーマンス カウンターを参照してください。</p></td>
</tr>
<tr class="even">
<td><p>NNN Responses for SetPresence</p></td>
<td><p>サーバーから受信した nnn 応答コードの合計数。</p></td>
</tr>
<tr class="odd">
<td><p>GetPresence Calls</p></td>
<td><p>プレゼンス取得要求の合計試行数。</p></td>
</tr>
<tr class="even">
<td><p>NNN Responses for GetPresence</p></td>
<td><p>サーバーから受信した nnn 応答コードの合計数。</p></td>
</tr>
</tbody>
</table>


**アドレス帳サービス情報**

このカテゴリには、アドレス帳サービス (ABS) のファイル ダウンロードとアドレス帳 Web クエリ サービスの要求を監視するために使用するカウンターが含まれています。


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><strong>パフォーマンス カウンター</strong></th>
<th><strong>説明</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>ABS Full/Delta File Downloads Attempted</p></td>
<td><p>試行された完全または差分ファイル ダウンロード要求の合計数。</p></td>
</tr>
<tr class="even">
<td><p>ABS Full/Delta File Downloads Succeeded</p></td>
<td><p>試行された完全または差分ファイル ダウンロード要求の合計数。</p></td>
</tr>
<tr class="odd">
<td><p>アドレス帳 Web クエリ サービスに関連するカウンター</p></td>
<td><p>アドレス帳ファイルのダウンロードに関連するカウンター。</p></td>
</tr>
<tr class="even">
<td><p>ABS WS Calls attempted</p></td>
<td><p>試行したアドレス帳 Web クエリ サービス要求の合計数。</p></td>
</tr>
<tr class="odd">
<td><p>ABS WS Calls Succeeded</p></td>
<td><p>成功応答コードを返したアドレス帳 Web クエリ サービス要求の合計数。</p></td>
</tr>
<tr class="even">
<td><p>ABS WS Calls Failed</p></td>
<td><p>エラー応答コードを返したアドレス帳 Web クエリ サービスの合計数。</p></td>
</tr>
</tbody>
</table>


**配布リスト (DL) の情報**


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><strong>パフォーマンス カウンター</strong></th>
<th><strong>説明</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Calls Attempted</p></td>
<td><p>試行した配布リスト展開 (DLX) Web サービス要求の合計数。</p></td>
</tr>
<tr class="even">
<td><p>Calls Succeeded</p></td>
<td><p>成功応答コードを返した DLX Web サービス要求の合計数。</p></td>
</tr>
<tr class="odd">
<td><p>Calls Failed</p></td>
<td><p>エラー応答コードを返した DLX Web サービス要求の合計数。</p></td>
</tr>
</tbody>
</table>


**VoIP の基本情報**

次に示す各パフォーマンス カウンターは、すべての Voice over IP (VoIP) の通話数を報告します。これには、仲介サーバー、音声ビデオ会議サーバー、エッジ サーバー、応答グループ アプリケーション、および電話会議自動応答に対する通話が含まれます (これらのシナリオが有効な場合)。


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><strong>パフォーマンス カウンター</strong></th>
<th><strong>説明</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Calls Active</p></td>
<td><p>現在進行中の着信/発信音声通話の合計数。</p></td>
</tr>
<tr class="even">
<td><p>Calls Terminated</p></td>
<td><p>既に終了している着信/発信音声通話の合計数。</p></td>
</tr>
<tr class="odd">
<td><p>Calls Declined</p></td>
<td><p>拒否した着信音声通話の合計数。</p></td>
</tr>
<tr class="even">
<td><p>Incoming/Outgoing Calls Attempted</p></td>
<td><p>試行した着信/発信音声通話の合計数。</p></td>
</tr>
<tr class="odd">
<td><p>Incoming/Outgoing Calls Established</p></td>
<td><p>成立した着信/発信音声通話の合計数。</p></td>
</tr>
<tr class="even">
<td><p>Calls Received NNN</p></td>
<td><p>サーバーから受信した nnn 応答コードの合計数。</p></td>
</tr>
<tr class="odd">
<td><p>VoIP Pass Rate (%)</p></td>
<td><p>成立した通話の合計/試行した通話の合計。</p></td>
</tr>
</tbody>
</table>


**応答グループ サービス通話の情報**


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><strong>パフォーマンス カウンター</strong></th>
<th><strong>説明</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Calls Active</p></td>
<td><p>応答グループ アプリケーションへのアクティブな通話の合計数。</p></td>
</tr>
<tr class="even">
<td><p>Calls Attempted</p></td>
<td><p>試行した通話の合計数。</p></td>
</tr>
</tbody>
</table>


**インスタント メッセージング (IM) 通話の情報**


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><strong>パフォーマンス カウンター</strong></th>
<th><strong>説明</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Calls Active</p></td>
<td><p>進行中の着信/発信インスタント メッセージング通話の合計数。</p></td>
</tr>
<tr class="even">
<td><p>Calls Terminated</p></td>
<td><p>既に終了している着信/発信インスタント メッセージング通話の合計数。</p></td>
</tr>
<tr class="odd">
<td><p>Calls Received NNN</p></td>
<td><p>サーバーから受信した nnn 応答コードの合計数。</p></td>
</tr>
<tr class="even">
<td><p>IM Messages Received/Sent</p></td>
<td><p>すべてのセッションで受信または送信したメッセージの合計数。</p></td>
</tr>
<tr class="odd">
<td><p>Incoming/Outgoing Calls Attempted</p></td>
<td><p>試行した着信/発信インスタント メッセージング通話の合計数。</p></td>
</tr>
<tr class="even">
<td><p>Incoming/Outgoing Calls Established</p></td>
<td><p>成立した着信/発信インスタント メッセージ通話の合計数。</p></td>
</tr>
</tbody>
</table>


**アプリケーション共有通話の情報**


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><strong>パフォーマンス カウンター</strong></th>
<th><strong>説明</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Calls Active</p></td>
<td><p>進行中の着信/発信アプリケーション共有通話の合計数。</p></td>
</tr>
<tr class="even">
<td><p>Calls Terminated</p></td>
<td><p>既に終了している着信/発信アプリケーション共有通話の合計数。</p></td>
</tr>
<tr class="odd">
<td><p>Calls Received NNN</p></td>
<td><p>サーバーから受信した nnn 応答コードの合計数。</p></td>
</tr>
<tr class="even">
<td><p>Incoming/Outgoing Calls Attempted</p></td>
<td><p>試行した着信/発信アプリケーション共有通話の合計数。</p></td>
</tr>
<tr class="odd">
<td><p>Incoming/Outgoing Calls Established</p></td>
<td><p>成立した着信/発信アプリケーション共有通話の合計数。</p></td>
</tr>
<tr class="even">
<td></td>
<td></td>
</tr>
</tbody>
</table>


**CAA 通話の情報**


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><strong>パフォーマンス カウンター</strong></th>
<th><strong>説明</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Calls Active</p></td>
<td><p>現在進行中の着信/発信公衆交換電話網 (PSTN) 通話の合計数。</p></td>
</tr>
<tr class="even">
<td><p>Calls Terminated</p></td>
<td><p>既に終了している着信/発信 PSTN 通話の合計数。</p></td>
</tr>
<tr class="odd">
<td><p>Incoming/Outgoing Calls Attempted</p></td>
<td><p>試行した着信/発信 PSTN 通話の合計数。</p></td>
</tr>
<tr class="even">
<td><p>Incoming/Outgoing Calls Established</p></td>
<td><p>成立した着信/発信 PSTN 通話の合計数。</p></td>
</tr>
</tbody>
</table>


**会議通話の情報**


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><strong>パフォーマンス カウンター</strong></th>
<th><strong>説明</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Active Instant Messaging Conferences</p></td>
<td><p>進行中のインスタント メッセージング会議通話の合計数。</p></td>
</tr>
<tr class="even">
<td><p>Active Audio/Video Conferences</p></td>
<td><p>進行中の音声ビデオ (A/V) 会議通話の合計数。</p></td>
</tr>
<tr class="odd">
<td><p>Active Application Sharing Conferences</p></td>
<td><p>進行中のアプリケーション共有会議通話の合計数。</p></td>
</tr>
<tr class="even">
<td><p>Number of Participants</p></td>
<td><p>会議通話に現在接続している参加者の合計数。</p></td>
</tr>
<tr class="odd">
<td><p>Conference Schedule Failure</p></td>
<td><p>会議通話のスケジュールに失敗した合計回数。</p></td>
</tr>
<tr class="even">
<td><p>Join Conference Failure</p></td>
<td><p>会議通話への接続に失敗した合計回数。</p></td>
</tr>
</tbody>
</table>


**UCWA クライアントのカウンター**


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><strong>パフォーマンス カウンター</strong></th>
<th><strong>説明</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Total Number of IMMCU Joins Succeeded</p></td>
<td><p>参加したインスタント メッセージング会議通話の合計数。</p></td>
</tr>
<tr class="even">
<td><p>Total Number of DMCU Joins Succeeded</p></td>
<td><p>参加した音声ビデオ会議通話の合計数。</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

