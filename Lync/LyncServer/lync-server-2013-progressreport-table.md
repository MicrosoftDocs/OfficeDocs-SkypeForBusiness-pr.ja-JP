---
title: 'Lync Server 2013: ProgressReport テーブル'
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
ms.openlocfilehash: 2e1cb7c8e764097af96981220ee74d481b379341
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41724817"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="progressreport-table-in-lync-server-2013"></a>Lync Server 2013 の ProgressReport テーブル

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2012-09-28_

進行状況レポートは、呼び出しまたはセッションが完了した後に、クライアントからデータベースにアップロードされたデータに基づいています。 進行状況レポートは、Lync Server 2013 で判別目的で役立つ可能性がある通話とセッションに対してのみ記録されます。

ErrorTime、ErrorReportSeq、進捗レポート Seq フィールドは、必ずしもエラーも参照しません。通話またはメッセージの状態を示すメッセージが表示されるわけではありません。


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
<td><p>datetime</p></td>
<td><p>プライマリ、外部</p></td>
<td><p>この進捗状況レポートが含まれる進捗状況エラーレポートの日付と時刻。 詳細については、「 <a href="lync-server-2013-errorreport-table.md">Lync Server 2013 の ErrorReport テーブル</a>」を参照してください。</p></td>
</tr>
<tr class="even">
<td><p><strong>ErrorId</strong></p></td>
<td><p>int</p></td>
<td><p>プライマリ、外部</p></td>
<td><p>ID 番号は、ErrorTime と共に使用されます。進捗レポートは、進行状況レポートを一意に識別するために使われます。 詳細については、「 <a href="lync-server-2013-errorreport-table.md">Lync Server 2013 の ErrorReport テーブル</a>」を参照してください。</p></td>
</tr>
<tr class="odd">
<td><p><strong>ErrorReportSeq</strong></p></td>
<td><p>int</p></td>
<td><p>プライマリ、外部</p></td>
<td><p>エラーレポートを識別する ID 番号。 エラーレポートを一意に識別するには、ErrorReporSeq と ErrorTime との組み合わせで使用されます。 詳細については、「 <a href="lync-server-2013-errorreport-table.md">Lync Server 2013 の ErrorReport テーブル</a>」を参照してください。</p>
<p>このフィールドは、Microsoft Lync Server 2013 で導入されました。</p></td>
</tr>
<tr class="even">
<td><p><strong>進捗状況レポート Seq</strong></p></td>
<td><p>int</p></td>
<td><p>Primary</p></td>
<td><p>進捗状況レポートを識別する ID 番号。 ErrorTime と ErrorReportSeq と組み合わせて、進行状況レポートを一意に識別するために使用されます。</p></td>
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
<td><p>エラーレポートを送信したサーバー (レポートがサーバーコンポーネントから送信された場合)。 詳細については、「 <a href="lync-server-2013-servers-table.md">Lync Server 2013 のサーバーの表</a>」を参照してください。このフィールドは、Microsoft Lync Server 2013 で導入されました。</p></td>
</tr>
<tr class="odd">
<td><p><strong>ApplicationId</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>レポートの作成に関する Lync Server プロセス。 詳しくは、アプリケーションの表をご覧ください。</p></td>
</tr>
<tr class="even">
<td><p><strong>[詳細]</strong></p></td>
<td><p>画像</p></td>
<td></td>
<td><p>サイズを節約するためのバイナリ形式で保存された進行状況レポートの詳細。このデータは、次の構文を使用してテキスト形式に変換できます。</p>
<p>cast (cast (varbinary (max) としての Detail (max))</p></td>
</tr>
<tr class="odd">
<td><p><strong>TelemetryId</strong></p></td>
<td><p>長さ</p></td>
<td></td>
<td><p>会議に参加しているさまざまなコンポーネントの参加時間情報を関連付ける一意の識別子です。</p>
<p>このフィールドは、Microsoft Lync Server 2013 で導入されました。</p></td>
</tr>
<tr class="even">
<td><p><strong>SessionSetupTime 時間</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>特定のコンポーネントが会議に参加するまでの時間 (ミリ秒単位) です。</p>
<p>このフィールドは、Microsoft Lync Server 2013 で導入されました。</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

