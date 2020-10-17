---
title: 'Lync Server 2013: tblComplianceParticipant'
description: 'Lync Server 2013: tblComplianceParticipant。'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: tblComplianceParticipant
ms:assetid: 5d7e0dea-74f7-46d1-badf-b94abc8f066d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558655(v=OCS.15)
ms:contentKeyID: 48184262
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c1385b0a635f003a72de93f10f72642314ad7ebd
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48569073"
---
# <a name="tblcomplianceparticipant-in-lync-server-2013"></a>Lync Server 2013 の tblComplianceParticipant

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2012-09-12_

tblComplianceParticipant には、現在の参加者がチャネルおよびサーバー別に格納されます。

### <a name="columns"></a>段組み

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Column</th>
<th>種類</th>
<th>説明</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>channelUri</p></td>
<td><p>NULL でない nvarchar (255)</p></td>
<td><p>チャネルの URI (Uniform Resource Identifier)。</p></td>
</tr>
<tr class="even">
<td><p>userId</p></td>
<td><p>NULL でない int</p></td>
<td><p>参加者のプリンシパル ID (tblPrincipal.prinID テーブルに対応)。</p></td>
</tr>
<tr class="odd">
<td><p>joinedAt</p></td>
<td><p>NULL でない bigint</p></td>
<td><p>参加イベントのタイム スタンプ。</p></td>
</tr>
<tr class="even">
<td><p>partedAt</p></td>
<td><p>bigint</p></td>
<td><p>参加者がまだ参加している場合は NULL。NULL でない場合は、チャネル退出イベントのタイム スタンプ。</p>
<p>これらのエントリは、すべてのトランスレーターがイベントを処理すると最終的に削除されます。</p></td>
</tr>
<tr class="odd">
<td><p>userUri</p></td>
<td><p>NULL でない nvarchar(255)</p></td>
<td><p>ユーザーの URI。</p></td>
</tr>
<tr class="even">
<td><p>serverID</p></td>
<td><p>int</p></td>
<td><p>サーバーの ID (tblServerIdentity.serverID テーブルなど)。</p></td>
</tr>
<tr class="odd">
<td><p>sessionId</p></td>
<td><p>bigint</p></td>
<td><p>サーバー セッション。チャット サービスが起動するたびに生成されるランダムな数値。孤立した参加者の識別を目的としたセッションの区別に使用されます。</p></td>
</tr>
</tbody>
</table>


### <a name="key"></a>キー

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>列</th>
<th>説明</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>&lt;channelUri、userId、joinedAt&gt;</p></td>
<td><p>主キー。</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

