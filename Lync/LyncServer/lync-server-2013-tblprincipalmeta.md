---
title: 'Lync Server 2013: tblPrincipalMeta'
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
ms.openlocfilehash: 848f4dc19ddf64c53c2dd30ae6ca4c8036b67c79
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41764097"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="tblprincipalmeta-in-lync-server-2013"></a>Lync Server 2013 の tblPrincipalMeta

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2012-09-12_

tblPrincipalMeta には、Active Directory ドメインサービスから更新する必要があるプリンシパルが含まれています。

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
<td><p>prinID</p></td>
<td><p>int (null ではない)</p></td>
<td><p>プリンシパル ID。</p></td>
</tr>
<tr class="even">
<td><p>prinAffiliationsDirty</p></td>
<td><p>ビット、null ではない</p></td>
<td><p>プリンシパルの所属を更新する必要がある場合は True。</p></td>
</tr>
<tr class="odd">
<td><p>Prin属性のダーティ</p></td>
<td><p>ビット、null ではない</p></td>
<td><p>プリンシパル属性を更新する必要がある場合は True。</p></td>
</tr>
<tr class="even">
<td><p>プリントが削除されました</p></td>
<td><p>ビット、null ではない</p></td>
<td><p>プリンシパルが削除された場合は True。</p></td>
</tr>
<tr class="odd">
<td><p>tryCount</p></td>
<td><p>int</p></td>
<td><p>これまでに発生した、AD DS からプリンシパルを更新しようとした回数。</p></td>
</tr>
<tr class="even">
<td><p>最終試用</p></td>
<td><p>datetime</p></td>
<td><p>プリンシパルを最新の状態に更新しようとしたときのタイムスタンプ。 更新をまだ実行していない場合は、null を指定できます。</p></td>
</tr>
<tr class="odd">
<td><p>nextTry</p></td>
<td><p>datetime</p></td>
<td><p>スケジュールされている次回の更新のタイムスタンプ。 それ以降の更新がスケジュールされていない場合は、null を指定できます。</p></td>
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
<td><p>prinID</p></td>
<td><p>主キー。</p></td>
</tr>
<tr class="even">
<td><p>prinID</p></td>
<td><p>TblPrincipal Id テーブルで参照される外部キー。</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

