---
title: 'Lync Server 2013: ErrorCategory テーブル'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: ErrorCategory table
ms:assetid: 0fde3b73-9a2f-44dd-b8dc-6df512303ff1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204675(v=OCS.15)
ms:contentKeyID: 48183425
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c5da1da6f54fa9099cc455040a71fb11c4fe070e
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41735427"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="errorcategory-table-in-lync-server-2013"></a>Lync Server 2013 の ErrorCategory テーブル

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2012-08-20_

ErrorCategory テーブルには、Microsoft Lync Server 2013 診断分類ごとのフレンドリ名が含まれています。 既定では、Lync Server 2013 には次のような分類が使用されます。

  - 0--成功

  - 1--予期しないエラー

  - 2-予期しないエラー

この表は、Microsoft Lync Server 2013 で導入されました。


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>列</th>
<th>データ型</th>
<th>キー/インデックス</th>
<th>詳細</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>区分</strong></p></td>
<td><p>tinyint</p></td>
<td><p>Primary</p></td>
<td><p>分類の一意の識別子。</p></td>
</tr>
<tr class="even">
<td><p><strong>名前</strong></p></td>
<td><p>nvarchar(256)</p></td>
<td></td>
<td><p>分類に割り当てられている値とフレンドリ名。 有効な値は次のとおりです。</p>
<ul>
<li><p>0--成功</p></li>
<li><p>1--予期しないエラー</p></li>
<li><p>2-予期しないエラー</p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

