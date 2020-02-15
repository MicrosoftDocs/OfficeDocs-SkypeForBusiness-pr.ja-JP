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
ms.openlocfilehash: 407b7efd00a521e0eec7a6d573368d2f971ce3bc
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2020
ms.locfileid: "42042104"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="errorcategory-table-in-lync-server-2013"></a>Lync Server 2013 の ErrorCategory テーブル

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2012-08-20_

ErrorCategory テーブルには、Microsoft Lync Server 2013 の診断分類のフレンドリ名が含まれています。 既定では、Lync Server 2013 は次の分類を使用します。

  - 0 -- 成功

  - 1--予期されたエラー

  - 2 – 予期しないエラー

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
<td><p>nvarchar (256)</p></td>
<td></td>
<td><p>分類に割り当てられる値とフレンドリ名。有効な値は次のとおりです。</p>
<ul>
<li><p>0 -- 成功</p></li>
<li><p>1--予期されたエラー</p></li>
<li><p>2 – 予期しないエラー</p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

