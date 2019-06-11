---
title: 'Lync Server 2013: tblPrincipalAffiliations'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: tblPrincipalAffiliations
ms:assetid: 45fd8484-5837-44d2-85bb-45c83546607c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558642(v=OCS.15)
ms:contentKeyID: 48183993
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: eb5f6400de1c71b4d11101871b2dadedd232a9ce
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34848583"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="tblprincipalaffiliations-in-lync-server-2013"></a>Lync Server 2013 の tblPrincipalAffiliations

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2012-09-12_

tblPrincipalAffiliations には、active Directory ドメインサービスセキュリティグループなどの場所のメンバーシップを、ドメインの Active Directory コンテナーで説明するプリンシパルの所属が含まれています。

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
<td><p>principalID</p></td>
<td><p>int (null ではない)</p></td>
<td><p>関連主体の ID です。</p></td>
</tr>
<tr class="even">
<td><p>affiliationID</p></td>
<td><p>int (null ではない)</p></td>
<td><p>所属を表すプリンシパルの ID です。 各プリンシパル (システムユーザーの種類を除く) には、自己所属も含まれています。</p></td>
</tr>
<tr class="odd">
<td><p>位置</p></td>
<td><p>int (null ではない)</p></td>
<td><p>位置. 自己所属の値は-1 であり、その他の所属については、principalID の各&lt;&gt;バケット内の1から順に1が増加します。</p></td>
</tr>
<tr class="even">
<td><p>updatedBy</p></td>
<td><p>int (null ではない)</p></td>
<td><p>最新の更新プログラムを実行したプリンシパル。 これは通常1で、Active Directory の同期を意味します。</p></td>
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
<th>行</th>
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
<td><p>TblPrincipal Id テーブルで参照される外部キー。</p></td>
</tr>
<tr class="odd">
<td><p>affiliationID</p></td>
<td><p>TblPrincipal Id テーブルで参照される外部キー。</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

