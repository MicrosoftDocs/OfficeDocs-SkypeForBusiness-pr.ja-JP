---
title: 'Lync Server 2013: tblEnumValue'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: tblEnumValue
ms:assetid: a33df20c-d19d-4f5c-b012-29dab8fb9200
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615025(v=OCS.15)
ms:contentKeyID: 48185040
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 79d1b68cd10858812a1310ebbd1f2caae913da75
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/16/2020
ms.locfileid: "48509324"
---
# <a name="tblenumvalue-in-lync-server-2013"></a>Lync Server 2013 の tblEnumValue

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2012-06-28_

tblEnumValue は、ノード テーブルで使われる属性の Visibility (表示設定) 値と Behavior (動作) 値を含む、ハードコードされたテーブルです。

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
<td><p>valueID</p></td>
<td><p>NULL でない smallint</p></td>
<td><p>値の ID。</p></td>
</tr>
<tr class="even">
<td><p>attributeID</p></td>
<td><p>NULL でない smallint</p></td>
<td><p>属性の ID。</p></td>
</tr>
<tr class="odd">
<td><p>attributeValue</p></td>
<td><p>NULL でない nvarchar (256)</p></td>
<td><p>値の名前。</p></td>
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
<td><p>valueID</p></td>
<td><p>主キー。</p></td>
</tr>
<tr class="even">
<td><p>attributeID</p></td>
<td><p>tblEnumAttribute.attributeID テーブルを参照する外部キー。</p></td>
</tr>
</tbody>
</table>


### <a name="table-values"></a>テーブル値

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>valueID</th>
<th>attributeID</th>
<th>attributeValue</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>pbm-2</p></td>
<td><p>1-d</p></td>
<td><p>機密性</p></td>
</tr>
<tr class="even">
<td><p>1/3</p></td>
<td><p>1-d</p></td>
<td><p>scope</p></td>
</tr>
<tr class="odd">
<td><p>4 </p></td>
<td><p>pbm-2</p></td>
<td><p>ノーマル</p></td>
</tr>
<tr class="even">
<td><p>5 </p></td>
<td><p>pbm-2</p></td>
<td><p>大会議室</p></td>
</tr>
<tr class="odd">
<td><p>6 </p></td>
<td><p>1-d</p></td>
<td><p>開か</p></td>
</tr>
</tbody>
</table>


<div>

## <a name="see-also"></a>関連項目


[Lync Server 2013 の tblNode](lync-server-2013-tblnode.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

