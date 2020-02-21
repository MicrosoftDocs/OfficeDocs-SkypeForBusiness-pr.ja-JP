---
title: 'Lync Server 2013: 進捗レポートビュー'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: ProgressReport view
ms:assetid: b49f3fc7-0e2f-498f-8505-aaaf54e435f9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721857(v=OCS.15)
ms:contentKeyID: 49733790
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ac09e1b22e4807b039daf4b5da4778a54cb91d4b
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/21/2020
ms.locfileid: "42201793"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="progressreport-view-in-lync-server-2013"></a>Lync Server 2013 の進捗レポートの表示

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2012-10-01_

ProgressReport ビューは、完了したセッションに関する情報を格納します。 進行状況レポートは、Lync Server 2013 による診断時に役立ちそうな通話とセッションのみを対象として書き込まれます。 このビューは Microsoft Lync Server 2013 で導入されました。

<div>


> [!NOTE]  
> ErrorTime、ErrorReportSeq、および ProgressReportSeq フィールドは、必ずしもエラーを参照するのではなく、通話またはメッセージの状態を示すメッセージを参照します。



</div>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>列</th>
<th>データ型</th>
<th>詳細</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>ErrorTime</strong></p></td>
<td><p>日付型</p></td>
<td><p>エラーが発生した時刻。エラー を一意に識別するために ErrorReportSeq と併用されます。</p></td>
</tr>
<tr class="even">
<td><p><strong>Errorreportseq、</strong></p></td>
<td><p>int</p></td>
<td><p>エラーを識別する ID 番号。エラーを一意に識別するために ErrorTime と併用されます。</p></td>
</tr>
<tr class="odd">
<td><p><strong>ProgressReportSeq</strong></p></td>
<td><p>int</p></td>
<td><p>進行状況レポートを識別するための ID。 同じエラー レポートの進行状況レポートを区別するために使用されます。</p></td>
</tr>
<tr class="even">
<td><p><strong>MsDiagId</strong></p></td>
<td><p>int</p></td>
<td><p>エラー レポートの診断 ID。</p></td>
</tr>
<tr class="odd">
<td><p><strong>Source</strong></p></td>
<td><p>nvarchar (256)</p></td>
<td><p>エラーを発生させたサーバーの名前 (サーバー コンポーネントからレポートが送信された場合)。</p></td>
</tr>
<tr class="even">
<td><p><strong>アプリケーション</strong></p></td>
<td><p>nvarchar (256)</p></td>
<td><p>エラーを発生させたアプリケーションの名前 (サーバー コンポーネントからレポートが送信された場合)。</p></td>
</tr>
<tr class="odd">
<td><p><strong>TelemetryId</strong></p></td>
<td><p>識別子</p></td>
<td><p>会議に関するさまざまなコンポーネントの参加時間情報に関係する一意の識別子。</p></td>
</tr>
<tr class="even">
<td><p><strong>SessionSetupTime 時間</strong></p></td>
<td><p>int</p></td>
<td><p>特定のコンポーネントが会議に参加するのに必要な時間 (ミリ秒)。</p></td>
</tr>
<tr class="odd">
<td><p><strong>MsDiagHeader</strong></p></td>
<td><p>varchar (max)</p></td>
<td><p>追加のエラー情報。</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

