---
title: 'Lync Server 2013: tblPrincipalType'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: tblPrincipalType
ms:assetid: 32e1c1d6-80f4-4624-bf4e-b4c77d3982fa
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558633(v=OCS.15)
ms:contentKeyID: 48183787
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6731d0bcda6e4e66b1b498a5f1bf91023627b1f0
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41764087"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="tblprincipaltype-in-lync-server-2013"></a>Lync Server 2013 の tblPrincipalType

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2012-09-12_

tblPrincipalType には、tblPrincipal テーブルの内容を分類するためのプリンシパルの種類が含まれています。

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
<td><p>ptypeID</p></td>
<td><p>smallint (null ではない)</p></td>
<td><p>プリンシパルの種類 ID。</p></td>
</tr>
<tr class="even">
<td><p>ptypeDesc</p></td>
<td><p>nvarchar (256)、null ではない</p></td>
<td><p>型の説明。</p></td>
</tr>
<tr class="odd">
<td><p>ptypeIsSystemUser 場合</p></td>
<td><p>ビット、null ではない</p></td>
<td><p>内部目的で使用されるプリンシパルに対応する型の場合は True です。</p></td>
</tr>
<tr class="even">
<td><p>ptypeIsUser</p></td>
<td><p>ビット、null ではない</p></td>
<td><p>型がユーザーの型である場合は True です。</p></td>
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
<td><p>ptypeID</p></td>
<td><p>主キー。</p></td>
</tr>
</tbody>
</table>


### <a name="principal-values"></a>プリンシパルの値

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>ID</th>
<th>役割</th>
<th>説明</th>
<th>[ユーザー]</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>1</p></td>
<td><p>任意</p></td>
<td><p>既知の型のない汎用プリンシパル。 TblPrincipal テーブルでは使用されません。</p></td>
<td></td>
</tr>
<tr class="even">
<td><p>両面</p></td>
<td><p>任意のユーザー</p></td>
<td><p>ユーザーの種類の汎用プリンシパル。 TblPrincipal テーブルでは使用されません。</p></td>
<td><p>はい</p></td>
</tr>
<tr class="odd">
<td><p>3</p></td>
<td><p>AnyGroup</p></td>
<td><p>グループの意味を持つ汎用プリンシパル。 TblPrincipal テーブルでは使用されません。</p></td>
<td></td>
</tr>
<tr class="even">
<td><p>4</p></td>
<td><p>他のお互い</p></td>
<td><p>常設チャットサーバーで内部的に使用されているプリンシパル。</p></td>
<td></td>
</tr>
<tr class="odd">
<td><p>5</p></td>
<td><p>ユーザー</p></td>
<td><p>標準ユーザー。</p></td>
<td><p>はい</p></td>
</tr>
<tr class="even">
<td><p>個</p></td>
<td><p>修飾</p></td>
<td><p>Active Directory ドメインサービスのドメインコントローラー。</p></td>
<td></td>
</tr>
<tr class="odd">
<td><p>ファイブ</p></td>
<td><p>化</p></td>
<td><p>Active Directory セキュリティグループ。</p></td>
<td></td>
</tr>
<tr class="even">
<td><p>常用</p></td>
<td><p>]</p></td>
<td><p>Active Directory コンテナーまたは組織単位。</p></td>
<td></td>
</tr>
</tbody>
</table>


<div>

## <a name="see-also"></a>関連項目


[Lync Server 2013 の tblPrincipal](lync-server-2013-tblprincipal.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

