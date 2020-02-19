---
title: 'Lync Server 2013: 進捗レポートテーブル'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: ProgressReport table
ms:assetid: 38e5f060-5e9b-4185-87b2-7ef61c4bb75f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425864(v=OCS.15)
ms:contentKeyID: 48183847
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 50697242b7086dbd81b74d098d200b1162ac12a5
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/19/2020
ms.locfileid: "42139068"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="progressreport-table-in-lync-server-2013"></a>Lync Server 2013 の進捗レポートの表

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2012-09-28_

進行状況レポートは、通話またはセッションの完了後にクライアントによってデータベースにアップロードされたデータに基づきます。 進行状況レポートは、Lync Server 2013 による診断時に役立ちそうな通話とセッションのみを対象として書き込まれます。

ErrorTime、ErrorReportSeq、および ProgressReportSeq フィールドは、必ずしもエラーを参照するのではなく、通話またはメッセージの状態を示すメッセージを参照します。


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>列</th>
<th>データ型</th>
<th>キー/インデックス</th>
<th>詳細</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>ErrorTime</strong></p></td>
<td><p>日付型</p></td>
<td><p>主/プライマリ、外部</p></td>
<td><p>この進行状況レポートを含む進行状況エラー レポートの日時。 詳細については、「 <a href="lync-server-2013-errorreport-table.md">Lync Server 2013 の ErrorReport テーブル</a>」を参照してください。</p></td>
</tr>
<tr class="even">
<td><p><strong>ErrorId</strong></p></td>
<td><p>int</p></td>
<td><p>主/プライマリ、外部</p></td>
<td><p>進捗レポートを一意に識別するために ErrorTime、progress Reportseq と共に使用される ID 番号。 詳細については、「 <a href="lync-server-2013-errorreport-table.md">Lync Server 2013 の ErrorReport テーブル</a>」を参照してください。</p></td>
</tr>
<tr class="odd">
<td><p><strong>Errorreportseq、</strong></p></td>
<td><p>int</p></td>
<td><p>主/プライマリ、外部</p></td>
<td><p>エラー レポートを識別する ID 番号。 ErrorReporSeq は、一意的にエラー レポートを識別する目的で ErrorTime と共に使用されます。 詳細については、「 <a href="lync-server-2013-errorreport-table.md">Lync Server 2013 の ErrorReport テーブル</a>を参照してください。</p>
<p>このフィールドは、Microsoft Lync Server 2013 で導入されました。</p></td>
</tr>
<tr class="even">
<td><p><strong>ProgressReportSeq</strong></p></td>
<td><p>int</p></td>
<td><p>Primary</p></td>
<td><p>進行状況レポートを識別するための ID 番号。進行状況レポートを一意に識別するために ErrorTime と ErrorReportSeq と併用されます。</p></td>
</tr>
<tr class="odd">
<td><p><strong>MsDiagId</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>進行状況レポートの診断 ID。</p>
<p>このフィールドは、Microsoft Lync Server 2013 で導入されました。</p></td>
</tr>
<tr class="even">
<td><p><strong>SourceId</strong></p></td>
<td><p>int</p></td>
<td><p>外部</p></td>
<td><p>エラーレポートを送信したサーバー (サーバーコンポーネントからレポートが送信された場合)。 詳細については、「 <a href="lync-server-2013-servers-table.md">Lync Server 2013 のサーバーの表</a>」を参照してください。このフィールドは、Microsoft Lync Server 2013 で導入されました。</p></td>
</tr>
<tr class="odd">
<td><p><strong>ApplicationId</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>レポートの対象となる Lync Server プロセス。詳細については、「アプリケーション テーブル」を参照してください。</p></td>
</tr>
<tr class="even">
<td><p><strong>詳細</strong></p></td>
<td><p>image</p></td>
<td></td>
<td><p>進行状況レポートの詳細。記憶域を節約するできるようにバイナリ形式で格納されます。このデータは、次のコードを使用してテキスト形式に変換できます。</p>
<p>cast(cast(Detail as varbinary(max)) as varchar(max))</p></td>
</tr>
<tr class="odd">
<td><p><strong>TelemetryId</strong></p></td>
<td><p>識別子</p></td>
<td></td>
<td><p>電話会議に関係するさまざまなコンポーネントの参加時間情報を関連付ける一意識別子。</p>
<p>このフィールドは、Microsoft Lync Server 2013 で導入されました。</p></td>
</tr>
<tr class="even">
<td><p><strong>SessionSetupTime 時間</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>特定のコンポーネントが電話会議に参加する時間 (単位はミリ秒)。</p>
<p>このフィールドは、Microsoft Lync Server 2013 で導入されました。</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

