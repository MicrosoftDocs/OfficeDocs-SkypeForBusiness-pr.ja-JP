---
title: 'Lync Server 2013: Servers テーブル'
description: 'Lync Server 2013: Servers テーブル'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Servers table
ms:assetid: 1535e676-a647-4606-bc56-e8bfde5ca823
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398223(v=OCS.15)
ms:contentKeyID: 48183487
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c7ff7bd94aa6a999169d35cc3a8cd057c92188c7
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48576513"
---
# <a name="servers-table-in-lync-server-2013"></a>Lync Server 2013 のサーバーテーブル

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2010-11-05_

Servers テーブルは、さまざまなサーバーに関する情報を格納するサポートテーブルです。 テーブル内の各レコードは、1つのサーバーを表します。


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
<td><p><strong>ServerId</strong></p></td>
<td><p>int</p></td>
<td><p>Primary</p></td>
<td><p>このサーバーを示す一意の番号です。</p></td>
</tr>
<tr class="even">
<td><p><strong>ServerFQDN</strong></p></td>
<td><p>nvarchar (256)</p></td>
<td><p> </p></td>
<td><p>サーバーの FQDN。</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

