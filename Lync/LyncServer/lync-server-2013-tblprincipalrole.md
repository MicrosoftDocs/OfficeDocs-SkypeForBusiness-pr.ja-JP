---
title: 'Lync Server 2013: tblPrincipalRole'
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
ms.openlocfilehash: de125c0f314bd0ba72b9bbd463201b12d3e19eea
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41731177"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="tblprincipalrole-in-lync-server-2013"></a>Lync Server 2013 の tblPrincipalRole

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2012-09-12_

tblPrincipalRole には、ノードに割り当てられている明示的な役割が含まれます。

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
<td><p>Prinrolid</p></td>
<td><p>int (null ではない)</p></td>
<td><p>役割が適用されるノード ID。</p></td>
</tr>
<tr class="even">
<td><p>prinRolePrinID</p></td>
<td><p>int (null ではない)</p></td>
<td><p>プリンシパル ID。</p></td>
</tr>
<tr class="odd">
<td><p>prinRoleTypeID</p></td>
<td><p>int (null ではない)</p></td>
<td><p>役割の種類の ID (tblRoleType から)。</p></td>
</tr>
<tr class="even">
<td><p>prinroleupdat</p></td>
<td><p>int (null ではない)</p></td>
<td><p>このエントリを最後に更新したプリンシパルの ID です。</p></td>
</tr>
</tbody>
</table>


### <a name="keys"></a>機能

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
<td><p>&lt;Prinroldeid、prinRolePrinID、prinRoleTypeID&gt;</p></td>
<td><p>主キー。</p></td>
</tr>
<tr class="even">
<td><p>Prinrolid</p></td>
<td><p>TblNode テーブルで参照される外部キー。</p></td>
</tr>
<tr class="odd">
<td><p>prinRolePrinID</p></td>
<td><p>TblPrincipal Id テーブルで参照される外部キー。</p></td>
</tr>
<tr class="even">
<td><p>prinRoleTypeID</p></td>
<td><p>TblRoleType の Typeid テーブルで参照される外部キー。</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

