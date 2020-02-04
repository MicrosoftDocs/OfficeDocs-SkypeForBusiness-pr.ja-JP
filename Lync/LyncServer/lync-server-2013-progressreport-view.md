---
title: 'Lync Server 2013: 進捗状況レポートビュー'
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
ms.openlocfilehash: 4fa8d73981490503b26b77b79be6f42aab77703e
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41747247"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="progressreport-view-in-lync-server-2013"></a>Lync Server 2013 の進捗状況レポートビュー

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2012-10-01_

進捗レポートビューには、完了したセッションに関する情報が格納されます。 進行状況レポートは、Lync Server 2013 で判別目的で役立つ可能性がある通話とセッションに対してのみ記録されます。 このビューは、Microsoft Lync Server 2013 で導入されました。

<div>


> [!NOTE]  
> ErrorTime、ErrorReportSeq、進捗レポート Seq フィールドは、必ずしもエラーも参照しません。通話またはメッセージの状態を示すメッセージが表示されるわけではありません。



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
<td><p>datetime</p></td>
<td><p>エラーが発生した時刻。 エラーを一意に識別するには、ErrorReportSeq と組み合わせて使います。</p></td>
</tr>
<tr class="even">
<td><p><strong>ErrorReportSeq</strong></p></td>
<td><p>int</p></td>
<td><p>エラーを識別する ID 番号。 エラーを一意に識別するための ErrorTime と共に使用されます。</p></td>
</tr>
<tr class="odd">
<td><p><strong>進捗状況レポート Seq</strong></p></td>
<td><p>int</p></td>
<td><p>進行状況レポートを識別する ID。 同じエラーレポートの進行状況レポートを区別するために使用されます。</p></td>
</tr>
<tr class="even">
<td><p><strong>MsDiagId</strong></p></td>
<td><p>int</p></td>
<td><p>エラーレポートの診断 ID。</p></td>
</tr>
<tr class="odd">
<td><p><strong>ソース</strong></p></td>
<td><p>nvarchar(256)</p></td>
<td><p>エラーが発生したサーバーの名前 (サーバーコンポーネントからレポートが送信された場合)。</p></td>
</tr>
<tr class="even">
<td><p><strong>Application</strong></p></td>
<td><p>nvarchar(256)</p></td>
<td><p>エラーの発生元のアプリケーションの名前 (サーバーコンポーネントからレポートが送信された場合)。</p></td>
</tr>
<tr class="odd">
<td><p><strong>TelemetryId</strong></p></td>
<td><p>長さ</p></td>
<td><p>電話会議に参加しているさまざまなコンポーネントについての、固有の識別子による結合時間情報の関連付け。</p></td>
</tr>
<tr class="even">
<td><p><strong>SessionSetupTime 時間</strong></p></td>
<td><p>int</p></td>
<td><p>特定のコンポーネントが会議に参加するために必要な時間 (ミリ秒単位) です。</p></td>
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

