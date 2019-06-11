---
title: 'Lync Server 2013: tblEnumValue'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: tblEnumValue
ms:assetid: a33df20c-d19d-4f5c-b012-29dab8fb9200
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615025(v=OCS.15)
ms:contentKeyID: 48185040
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1758daf16575491960415647e4c9bc4b43920d26
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34848603"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="tblenumvalue-in-lync-server-2013"></a>Lync Server 2013 の tblEnumValue

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2012-06-28_

tblEnumValue は、ノードテーブルで使用されている属性の可視性と動作の値を含む、ハードコーディングされた表です。

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
<td><p>valueID</p></td>
<td><p>smallint (null ではない)</p></td>
<td><p>値の ID です。</p></td>
</tr>
<tr class="even">
<td><p>attributeID</p></td>
<td><p>smallint (null ではない)</p></td>
<td><p>属性の ID です。</p></td>
</tr>
<tr class="odd">
<td><p>attributeValue</p></td>
<td><p>nvarchar (256)、null ではない</p></td>
<td><p>値の名前。</p></td>
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
<td><p>valueID</p></td>
<td><p>主キー。</p></td>
</tr>
<tr class="even">
<td><p>attributeID</p></td>
<td><p>TblEnumAttribute テーブルで参照する外部キー</p></td>
</tr>
</tbody>
</table>


### <a name="table-values"></a>テーブルの値

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
<td><p>2</p></td>
<td><p>1</p></td>
<td><p>private</p></td>
</tr>
<tr class="even">
<td><p>3</p></td>
<td><p>1</p></td>
<td><p>種類</p></td>
</tr>
<tr class="odd">
<td><p>4</p></td>
<td><p>2</p></td>
<td><p>標準</p></td>
</tr>
<tr class="even">
<td><p>5</p></td>
<td><p>2</p></td>
<td><p>大</p></td>
</tr>
<tr class="odd">
<td><p>6</p></td>
<td><p>1</p></td>
<td><p>開こう</p></td>
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

