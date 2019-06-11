---
title: 'Lync Server 2013: UriTypes テーブル'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: UriTypes table
ms:assetid: 77c4dfae-1b29-4e81-ba05-609e61643998
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398587(v=OCS.15)
ms:contentKeyID: 48184553
ms.date: 06/16/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 916f4e6b06bc8fab484d29f7fe88170025de01d2
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34848357"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="uritypes-table-in-lync-server-2013"></a>Lync Server 2013 の UriTypes テーブル

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2015-06-16_

UriTypes テーブルには、Microsoft Lync Server 2013 で監視されるさまざまな URI (Uniform resource identifier) の種類が含まれています。


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
<td><p><strong>UriTypeId</strong></p></td>
<td><p>tinyint</p></td>
<td><p>Primary</p></td>
<td><p>URI 型に割り当てられている一意の識別子。</p></td>
</tr>
<tr class="even">
<td><p><strong>UriType</strong></p></td>
<td><p>nvarchar(256)</p></td>
<td></td>
<td><p>各種の URI の種類について説明します。 有効な値は次のとおりです。</p>
<ul>
<li><p>1–電話の Uri</p></li>
<li><p>0–ユーザー Uri</p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

