---
title: 'Lync Server 2013: フェールオーバー ルートの構成'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring a failover route
ms:assetid: 76e48df4-3b78-4fb7-b1f7-c1e604b81bad
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398581(v=OCS.15)
ms:contentKeyID: 48184542
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 22ebdf359a8cdf5f20ada8740a589b0181c3cc93
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41741287"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-a-failover-route-in-lync-server-2013"></a>Lync Server 2013 でのフェールオーバー ルートの構成

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2012-09-21_

次の例では、Dallas-GW1 がメンテナンスで停止したり、利用できなくなったりしたときに使用するフェールオーバー ルートの定義方法を示します。必要な構成の変更を次の表に示します。

### <a name="table-1-user-policy"></a>表 1. ユーザー ポリシー

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>ユーザー ポリシー</th>
<th>電話使用法</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Default Calling Policy</p></td>
<td><p>Local</p>
<p>GlobalPSTNHopoff</p></td>
</tr>
<tr class="even">
<td><p>Redmond Local Policy</p></td>
<td><p>RedmondLocal</p></td>
</tr>
<tr class="odd">
<td><p>Dallas Calling Policy</p></td>
<td><p>DallasUsers</p>
<p>GlobalPSTNHopoff</p></td>
</tr>
</tbody>
</table>


### <a name="table-2-routes"></a>表 2. ルート

<table>
<colgroup>
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
</colgroup>
<thead>
<tr class="header">
<th>ルート名</th>
<th>番号のパターン</th>
<th>電話使用法</th>
<th>トランク</th>
<th>ゲートウェイ</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Redmond Local Route</p></td>
<td><p>^\+1 (425 | 206 | 253) (\d{7}) $</p></td>
<td><p>Local</p>
<p>RedmondLocal</p></td>
<td><p>Trunk1</p>
<p>Trunk2</p></td>
<td><p>Red-GW1</p>
<p>Red-GW2</p></td>
</tr>
<tr class="even">
<td><p>Dallas Local Route</p></td>
<td><p>^\+1 (972 | 214 | 469) (\d{7}) $</p></td>
<td><p>Local</p></td>
<td><p>Trunk3</p></td>
<td><p>Dallas-GW1</p></td>
</tr>
<tr class="odd">
<td><p>Universal Route</p></td>
<td><p>^\+?(\d *) $</p></td>
<td><p>GlobalPSTNHopoff</p></td>
<td><p>Trunk1</p>
<p>Trunk2</p>
<p>Trunk3</p></td>
<td><p>Red-GW1</p>
<p>Red-GW2</p>
<p>Dallas-GW1</p></td>
</tr>
<tr class="even">
<td><p>Dallas Users Route</p></td>
<td><p>^\+?(\d *) $</p></td>
<td><p>DallasUsers</p></td>
<td><p>Trunk3</p></td>
<td><p>Dallas-GW1</p></td>
</tr>
</tbody>
</table>


表 1 では、Dallas Calling Policy の電話使用法 DallasUsers の後に、電話使用法 GlobalPSTNHopoff が追加されます。この結果、電話使用法 DallasUsers に対応したルートが使用できない場合に、Dallas Calling Policy の通話で電話使用法 GlobalPSTNHopoff 用に構成されたルートが使用できるようになります。

</div>

<span> </span>

</div>

</div>

</div>

