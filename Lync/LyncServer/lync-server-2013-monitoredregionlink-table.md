---
title: 'Lync Server 2013: MonitoredRegionLink テーブル'
description: 'Lync Server 2013: MonitoredRegionLink テーブル。'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: MonitoredRegionLink table
ms:assetid: cebda194-7be3-42d6-b6f0-c86f8b0f200a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398874(v=OCS.15)
ms:contentKeyID: 48185487
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0a162b59f2d8aea7c0b30b0ee4af1aee7dd8c2e1
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48562103"
---
# <a name="monitoredregionlink-table-in-lync-server-2013"></a>Lync Server 2013 の MonitoredRegionLink テーブル

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2012-10-02_

MonitoredRegionLink テーブルは、サポート テーブルです。各レコードは、2 つの国/地域の間の 1 つのリンクを表します。


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><strong>列</strong></th>
<th><strong>データ型</strong></th>
<th><strong>キー/インデックス</strong></th>
<th><strong>詳細</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>Region1Key</strong></p></td>
<td><p>int</p></td>
<td><p>主/プライマリ、外部</p></td>
<td><p><a href="lync-server-2013-region-table.md">Lync Server 2013 の Region テーブル</a>から参照されます。</p></td>
</tr>
<tr class="even">
<td><p><strong>Region2Key</strong></p></td>
<td><p>int</p></td>
<td><p>主/プライマリ、外部</p></td>
<td><p><a href="lync-server-2013-region-table.md">Lync Server 2013 の Region テーブル</a>から参照されます。</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

