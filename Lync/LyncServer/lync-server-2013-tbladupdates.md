---
title: 'Lync Server 2013: tblADUpdates'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: tblADUpdates
ms:assetid: ba19fa16-4d2d-4635-ac32-f93e09469546
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615033(v=OCS.15)
ms:contentKeyID: 48185227
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ee3f0d881e26c3d26773b1b59feca3d1d02665dd
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/19/2020
ms.locfileid: "42142183"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="tbladupdates-in-lync-server-2013"></a>Lync Server 2013 の tblADUpdates

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2012-09-12_

tblADUpdates には、以降の Active Directory 同期手順でまだ処理されていない Active Directory ドメインサービスの変更が含まれています。

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
<td><p>Principal.pringuid</p></td>
<td><p>NULL でない GUID</p></td>
<td><p>変更したオブジェクトのプリンシパル GUID。</p></td>
</tr>
<tr class="even">
<td><p>prinADPath</p></td>
<td><p>NULL でない nvarchar (384)</p></td>
<td><p>オブジェクトの識別名。</p></td>
</tr>
<tr class="odd">
<td><p>Prinattributes 変更</p></td>
<td><p>NULL でない bit</p></td>
<td><p>オブジェクトの属性が 1 つ以上変更された場合は True。</p></td>
</tr>
<tr class="even">
<td><p>prinMembersChanged</p></td>
<td><p>NULL でない bit</p></td>
<td><p>メンバーシップが変更された場合は True。</p></td>
</tr>
<tr class="odd">
<td><p>prinAffiliationsChanged</p></td>
<td><p>NULL でない bit</p></td>
<td><p>不使用。</p></td>
</tr>
<tr class="even">
<td><p>prinDeleted</p></td>
<td><p>NULL でない bit</p></td>
<td><p>オブジェクトが削除された場合は True。</p></td>
</tr>
<tr class="odd">
<td><p>lastUpdated</p></td>
<td><p>NULL でない datetime</p></td>
<td><p>行が挿入された時点のタイムスタンプ。</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

