---
title: 'Lync Server 2013: に tblprincipalrole'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: tblPrincipalRole
ms:assetid: dcd16dc1-a66c-4720-a48f-ec8b28337383
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615039(v=OCS.15)
ms:contentKeyID: 48185597
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ddab28b269cf2b720d6935fa6d50f4bf9ea3084a
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2020
ms.locfileid: "42038589"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="tblprincipalrole-in-lync-server-2013"></a>Lync Server 2013 のに tblprincipalrole

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2012-09-12_

に tblprincipalrole には、ノードに割り当てられた明示的な役割が含まれます。

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
<td><p>Principalrole.prinrolenodeid</p></td>
<td><p>NULL でない int</p></td>
<td><p>役割の適用先のノード ID。</p></td>
</tr>
<tr class="even">
<td><p>Principalrole.prinroleprinid</p></td>
<td><p>NULL でない int</p></td>
<td><p>プリンシパル ID。</p></td>
</tr>
<tr class="odd">
<td><p>Principalrole.prinroletypeid</p></td>
<td><p>NULL でない int</p></td>
<td><p>役割の種類の ID (tblRoleType)。</p></td>
</tr>
<tr class="even">
<td><p>prinRoleUpdatedBy</p></td>
<td><p>NULL でない int</p></td>
<td><p>このエントリを最後に更新したプリンシパルの ID。</p></td>
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
<td><p>&lt;prinRoleNodeID、prinRolePrinID、prinRoleTypeID&gt;</p></td>
<td><p>主キー。</p></td>
</tr>
<tr class="even">
<td><p>Principalrole.prinrolenodeid</p></td>
<td><p>tblNode.nodeID テーブル内の参照による外部キー。</p></td>
</tr>
<tr class="odd">
<td><p>Principalrole.prinroleprinid</p></td>
<td><p>tblPrincipal.prinID テーブル内の参照による外部キー。</p></td>
</tr>
<tr class="even">
<td><p>Principalrole.prinroletypeid</p></td>
<td><p>TblRoleType テーブルに参照がある外部キー。</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

