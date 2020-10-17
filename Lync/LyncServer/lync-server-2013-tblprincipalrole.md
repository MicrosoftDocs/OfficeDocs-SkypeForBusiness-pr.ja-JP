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
ms.openlocfilehash: 76dda06baa4e5fab51ca44586f7f8fce00860695
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/16/2020
ms.locfileid: "48523614"
---
# <a name="tblprincipalrole-in-lync-server-2013"></a>Lync Server 2013 のに tblprincipalrole

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2012-09-12_

に tblprincipalrole には、ノードに割り当てられた明示的な役割が含まれます。

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

