---
title: 'Lync Server 2013: tblComplianceParticipant'
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
ms.openlocfilehash: 484948a01c82dc8ca256e3e50e484c94a9b81de4
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41731557"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="tblcomplianceparticipant-in-lync-server-2013"></a>Lync Server 2013 内の tblComplianceParticipant

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2012-09-12_

tblComplianceParticipant には、チャネルあたり、サーバーごとに現在の参加者が含まれています。

### <a name="columns"></a>行

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>列</th>
<th>型</th>
<th>説明</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>channelUri</p></td>
<td><p>nvarchar (255)、null ではない</p></td>
<td><p>チャネルの Uniform Resource Identifier (URI)。</p></td>
</tr>
<tr class="even">
<td><p>userId</p></td>
<td><p>int (null ではない)</p></td>
<td><p>参加者のプリンシパル ID (tblPrincipal ID テーブルに対応)</p></td>
</tr>
<tr class="odd">
<td><p>joinedAt</p></td>
<td><p>bigint (null ではない)</p></td>
<td><p>参加イベントのタイムスタンプ。</p></td>
</tr>
<tr class="even">
<td><p>partedAt</p></td>
<td><p>bigint</p></td>
<td><p>参加者がまだ参加している場合は Null です。 チャネルが null でない場合は、チャネルのタイムスタンプがイベントから出ます。</p>
<p>これらのエントリは、すべての翻訳者がイベントを処理すると、最終的に削除されます。</p></td>
</tr>
<tr class="odd">
<td><p>userUri</p></td>
<td><p>nvarchar (255)、null ではない</p></td>
<td><p>ユーザー URI。</p></td>
</tr>
<tr class="even">
<td><p>serverID</p></td>
<td><p>int</p></td>
<td><p>サーバー id (serverID テーブルの場合)。</p></td>
</tr>
<tr class="odd">
<td><p>sessionId</p></td>
<td><p>bigint</p></td>
<td><p>サーバーセッション。 これは、チャットサービスが開始されるたびに生成されるランダムな番号です。 これは、孤立した参加者を識別する目的でセッションを区別するために使われます。</p></td>
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

