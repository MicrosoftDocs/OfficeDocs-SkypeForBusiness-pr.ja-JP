---
title: 'Lync Server 2013: MediationServers テーブル'
description: 'Lync Server 2013: MediationServers テーブル。'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: MediationServers table
ms:assetid: 9f757377-ab79-4795-aaa9-1163cb9c8a59
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412743(v=OCS.15)
ms:contentKeyID: 48184929
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a227f76272790d3a23ff06f0c97ba4a263f418a5
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48568603"
---
# <a name="mediationservers-table-in-lync-server-2013"></a>Lync Server 2013 の MediationServers テーブル

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2010-11-06_

MediationServers テーブルは、サポートテーブルです。 各レコードには、データベース内のレコードを持つ呼び出しに関係する1つの仲介サーバーに関する情報が格納されます。


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>Column</th>
<th>データ型</th>
<th>キー/インデックス</th>
<th>詳細</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>MediationServerId</strong></p></td>
<td><p>int</p></td>
<td><p>Primary</p></td>
<td><p>この仲介サーバーを識別する一意の番号。</p></td>
</tr>
<tr class="even">
<td><p><strong>MediationServer</strong></p></td>
<td><p>nvarchar (256)</p></td>
<td><p> </p></td>
<td><p>仲介サーバーの名前。</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

