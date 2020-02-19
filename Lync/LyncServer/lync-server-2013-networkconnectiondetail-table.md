---
title: 'Lync Server 2013: NetworkConnectionDetail テーブル'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: NetworkConnectionDetail table
ms:assetid: b48cc9a6-5232-48b5-bd20-53b68229336b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205185(v=OCS.15)
ms:contentKeyID: 48185170
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: bb192385cfd5d04712b0e66169326aedd6c0f1b1
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/19/2020
ms.locfileid: "42128330"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="networkconnectiondetail-table-in-lync-server-2013"></a>Lync Server 2013 の NetworkConnectionDetail テーブル

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2012-10-02_

NetworkConnectionDetail テーブルは、Quality of Experience データベースの他の場所で使用されるネットワーク接続の識別子にネットワーク接続の種類を対応させます。 この表は、Microsoft Lync Server 2013 で導入されました。


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
<td><p><strong>Networkconnectionのすべてのキー</strong></p></td>
<td><p>tinyint</p></td>
<td><p>Primary</p></td>
<td><p>ネットワーク接続の種類の一意の識別子。</p></td>
</tr>
<tr class="even">
<td><p><strong>NetworkConnectionDetail</strong></p></td>
<td><p>varchar (256)</p></td>
<td><p>一意</p></td>
<td><p>NetworkConnectionDetailKey に対応するネットワーク接続の種類。有効な値は次のとおりです。</p>
<ol>
<li><p>0: 有線</p></li>
<li><p>1: WiFi</p></li>
<li><p>2: イーサネット</p></li>
</ol></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

