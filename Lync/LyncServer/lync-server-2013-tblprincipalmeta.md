---
title: 'Lync Server 2013: tblPrincipalMeta'
description: 'Lync Server 2013: tblPrincipalMeta。'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: tblPrincipalMeta
ms:assetid: 808490d4-7d6d-47a2-b8af-b5940d47073b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615009(v=OCS.15)
ms:contentKeyID: 48184648
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 899fd1e450dac52afa56c1ee1de86da82b2db309
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48573643"
---
# <a name="tblprincipalmeta-in-lync-server-2013"></a>Lync Server 2013 の tblPrincipalMeta

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2012-09-12_

tblPrincipalMeta には、Active Directory ドメインサービスから更新する必要があるプリンシパルが含まれています。

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
<td><p>Tblprincipal.prinid</p></td>
<td><p>NULL でない int</p></td>
<td><p>プリンシパル ID。</p></td>
</tr>
<tr class="even">
<td><p>prinAffiliationsDirty</p></td>
<td><p>NULL でない bit</p></td>
<td><p>プリンシパルの所属を最新の情報に更新する必要がある場合は True。</p></td>
</tr>
<tr class="odd">
<td><p>Prinattributes ダーティ</p></td>
<td><p>NULL でない bit</p></td>
<td><p>プリンシパル属性を最新の情報に更新する必要がある場合は True。</p></td>
</tr>
<tr class="even">
<td><p>prinDeleted</p></td>
<td><p>NULL でない bit</p></td>
<td><p>プリンシパルが削除されている場合は True。</p></td>
</tr>
<tr class="odd">
<td><p>tryCount</p></td>
<td><p>int</p></td>
<td><p>それまでに行われた AD DS からプリンシパルを更新する試行の数。</p></td>
</tr>
<tr class="even">
<td><p>lastTry</p></td>
<td><p>日付型</p></td>
<td><p>プリンシパルを最新の情報に更新する最新の試行からのタイム スタンプ。最新の情報への更新をまだ試みていない場合は NULL になります。</p></td>
</tr>
<tr class="odd">
<td><p>nextTry</p></td>
<td><p>日付型</p></td>
<td><p>次にスケジュールされている最新の情報への更新のタイム スタンプ。最新の情報への更新がスケジュールされていない場合は NULL になります。</p></td>
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
<td><p>Tblprincipal.prinid</p></td>
<td><p>主キー。</p></td>
</tr>
<tr class="even">
<td><p>Tblprincipal.prinid</p></td>
<td><p>tblPrincipal.prinID テーブル内の参照による外部キー。</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

