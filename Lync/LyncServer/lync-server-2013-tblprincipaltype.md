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
ms.openlocfilehash: 6f1c43c0e000e0c8adc3516304b931a68111072d
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/19/2020
ms.locfileid: "42141973"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="tblprincipaltype-in-lync-server-2013"></a>Lync Server 2013 の tblPrincipalType

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2012-09-12_

tblPrincipal テーブルには、tblPrincipal テーブルの内容を分類するプリンシパル型が含まれます。

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
<td><p>Tblprincipaltype.ptypeid</p></td>
<td><p>NULL でない smallint</p></td>
<td><p>プリンシパル型 ID。</p></td>
</tr>
<tr class="even">
<td><p>ptypeDesc</p></td>
<td><p>NULL でない nvarchar (256)</p></td>
<td><p>型の説明。</p></td>
</tr>
<tr class="odd">
<td><p>ptypeIsSystemUser</p></td>
<td><p>NULL でない bit</p></td>
<td><p>型が内部の用途で使用されるプリンシパルに対応する場合、True。</p></td>
</tr>
<tr class="even">
<td><p>ptypeIsUser</p></td>
<td><p>NULL でない bit</p></td>
<td><p>型がユーザー型の場合、True。</p></td>
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
<td><p>Tblprincipaltype.ptypeid</p></td>
<td><p>主キー。</p></td>
</tr>
</tbody>
</table>


### <a name="principal-values"></a>プリンシパル値

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
<th>Role</th>
<th>説明</th>
<th>ユーザー</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>1-d</p></td>
<td><p>任意</p></td>
<td><p>既知の型を持たない汎用的なプリンシパル。tblPrincipal テーブルでは使用されません。</p></td>
<td></td>
</tr>
<tr class="even">
<td><p>pbm-2</p></td>
<td><p>AnyUser</p></td>
<td><p>ユーザー型の汎用的なプリンシパル。tblPrincipal テーブルでは使用されません。</p></td>
<td><p>はい</p></td>
</tr>
<tr class="odd">
<td><p>1/3</p></td>
<td><p>AnyGroup</p></td>
<td><p>グループ セマンティックを持つ汎用的なプリンシパル。tblPrincipal テーブルでは使用されません。</p></td>
<td></td>
</tr>
<tr class="even">
<td><p>2/4</p></td>
<td><p>自分のもの</p></td>
<td><p>常設チャットサーバーによって内部的に使用されるプリンシパル。</p></td>
<td></td>
</tr>
<tr class="odd">
<td><p>5</p></td>
<td><p>ユーザー</p></td>
<td><p>標準のユーザー</p></td>
<td><p>はい</p></td>
</tr>
<tr class="even">
<td><p>8 </p></td>
<td><p>DC</p></td>
<td><p>Active Directory ドメインサービスのドメインコントローラー。</p></td>
<td></td>
</tr>
<tr class="odd">
<td><p>9 </p></td>
<td><p>Group</p></td>
<td><p>Active Directory セキュリティ グループ。</p></td>
<td></td>
</tr>
<tr class="even">
<td><p>10 </p></td>
<td><p>フォルダー</p></td>
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

