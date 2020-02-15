---
title: 'Lync Server 2013: tblActivePeers'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: tblActivePeers
ms:assetid: b50c3f4a-bab6-4cb9-b40e-016cf1a9c607
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615030(v=OCS.15)
ms:contentKeyID: 48185176
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ebde759bceaf682384284cffb6a2ec710050126c
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2020
ms.locfileid: "42031201"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="tblactivepeers-in-lync-server-2013"></a>Lync Server 2013 の tblActivePeers

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2012-06-29_

tblActivePeers には、チャット サービス間の現在のピアツーピア接続が含まれています。

### <a name="columns"></a>Columns

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>列</th>
<th>種類</th>
<th>説明</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>aplServerID</p></td>
<td><p>NULL でない int</p></td>
<td><p>エントリを投稿したサーバーの ID。</p></td>
</tr>
<tr class="even">
<td><p>aplPeerID</p></td>
<td><p>NULL でない int</p></td>
<td><p>投稿元サーバーが接続しているピアの ID。</p></td>
</tr>
</tbody>
</table>


### <a name="keys"></a>Keys

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
<td><p>&lt;aplServerID, aplPeerID&gt;</p></td>
<td><p>主キー。</p></td>
</tr>
<tr class="even">
<td><p>aplServerID</p></td>
<td><p>tblServerIdentity.serverID テーブルを参照する外部キー。</p></td>
</tr>
<tr class="odd">
<td><p>aplPeerID</p></td>
<td><p>tblServerIdentity.serverID テーブルを参照する外部キー。</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

