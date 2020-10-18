---
title: 'Lync Server 2013: tblPrincipalMemberDifference'
description: 'Lync Server 2013: tblPrincipalMemberDifference。'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: tblPrincipalMemberDifference
ms:assetid: 0b94f555-6888-4fe0-a048-4660a2513276
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558612(v=OCS.15)
ms:contentKeyID: 48183379
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ce7c770a6fed02dc27d2493816fae58943d391a6
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48573223"
---
# <a name="tblprincipalmemberdifference-in-lync-server-2013"></a>Lync Server 2013 の tblPrincipalMemberDifference

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2012-09-12_

tblPrincipalMemberDifference には、以降の Active Directory ドメインサービス同期手順でまだ処理されていないグループメンバーシップの変更 (メンバーの追加および削除) が含まれています。

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
<td><p>Principal.pringuid</p></td>
<td><p>NULL でない GUID</p></td>
<td><p>変更されたグループのプリンシパル GUID。</p></td>
</tr>
<tr class="even">
<td><p>memberADPath</p></td>
<td><p>nvarchar (256)</p></td>
<td><p>メンバーの識別名。</p></td>
</tr>
<tr class="odd">
<td><p>メンバーの削除</p></td>
<td><p>NULL でない bit</p></td>
<td><p>メンバーが追加された場合は False。メンバーが削除された場合は True。</p></td>
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
<td><p>&lt;prinGuid、memberADPath&gt;</p></td>
<td><p>主キー。</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

