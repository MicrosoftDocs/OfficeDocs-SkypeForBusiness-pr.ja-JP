---
title: 'Lync Server 2013: tblScopePrincipal'
description: 'Lync Server 2013: tblScopePrincipal。'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: tblScopePrincipal
ms:assetid: 422d6c7f-7ba7-4dd4-bacc-95ace47959ff
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558639(v=OCS.15)
ms:contentKeyID: 48184009
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 63315f8525e5c2f05fe54a0f9ed9e8a97b9e8bce
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48555613"
---
# <a name="tblscopeprincipal-in-lync-server-2013"></a>Lync Server 2013 の tblScopePrincipal

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2012-09-12_

tblScopePrincipal には、ノードに割り当てられるスコープが含まれます。

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
<td><p>Scopeprincipal.scopenodeid</p></td>
<td><p>NULL でない int</p></td>
<td><p>範囲の適用先ノード ID。</p></td>
</tr>
<tr class="even">
<td><p>Scopeprincipal.scopeprinid</p></td>
<td><p>NULL でない int</p></td>
<td><p>プリンシパル ID。</p></td>
</tr>
<tr class="odd">
<td><p>scopeIsDenied</p></td>
<td><p>NULL でない bit</p></td>
<td><p>スコープの種類が [拒否] の場合は True、[許可] の場合は False。</p></td>
</tr>
<tr class="even">
<td><p>scopeupdat</p></td>
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
<td><p>&lt;Scopeprincipal.scopenodeid、scopePrinID&gt;</p></td>
<td><p>主キー。</p></td>
</tr>
<tr class="even">
<td><p>Scopeprincipal.scopenodeid</p></td>
<td><p>tblNode.nodeID テーブル内の参照による外部キー。</p></td>
</tr>
<tr class="odd">
<td><p>Scopeprincipal.scopeprinid</p></td>
<td><p>tblPrincipal.prinID テーブル内の参照による外部キー。</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

