---
title: 'Lync Server 2013: tblPrincipalAffiliations'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: tblPrincipalAffiliations
ms:assetid: 45fd8484-5837-44d2-85bb-45c83546607c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558642(v=OCS.15)
ms:contentKeyID: 48183993
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2900a2ca780cfc239cb7045ea564bbba581f2f55
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/19/2020
ms.locfileid: "42142033"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="tblprincipalaffiliations-in-lync-server-2013"></a>Lync Server 2013 の tblPrincipalAffiliations

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2012-09-12_

tblPrincipalAffiliations には、active directory ドメインサービスセキュリティグループ、Active Directory コンテナー、ドメインなどの場所でのメンバーシップを記述するプリンシパルの所属が含まれています。

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
<td><p>principalID</p></td>
<td><p>NULL でない int</p></td>
<td><p>所属プリンシパルの ID。</p></td>
</tr>
<tr class="even">
<td><p>affiliationID</p></td>
<td><p>NULL でない int</p></td>
<td><p>所属を表すプリンシパルの ID。各プリンシパル (system-user-types 除く) には自己所属も含まれます。</p></td>
</tr>
<tr class="odd">
<td><p>index</p></td>
<td><p>NULL でない int</p></td>
<td><p>順. 自己所属の値は-1 で、その他の所属については、各&lt;PrincipalID、affiliationId&gt;バケット内で1から順に増加します。</p></td>
</tr>
<tr class="even">
<td><p>updatedBy</p></td>
<td><p>NULL でない int</p></td>
<td><p>最新の更新を実行したプリンシパル。通常は、Active Directory の同期を意味する 1 です。</p></td>
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
<th>Columns</th>
<th>説明</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>&lt;principalID、index、affiliationID&gt;</p></td>
<td><p>主キー。</p></td>
</tr>
<tr class="even">
<td><p>principalID</p></td>
<td><p>tblPrincipal.prinID テーブル内の参照による外部キー。</p></td>
</tr>
<tr class="odd">
<td><p>affiliationID</p></td>
<td><p>tblPrincipal.prinID テーブル内の参照による外部キー。</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

