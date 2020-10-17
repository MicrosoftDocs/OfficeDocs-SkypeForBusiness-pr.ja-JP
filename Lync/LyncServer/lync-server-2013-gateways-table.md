---
title: 'Lync Server 2013: ゲートウェイテーブル'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Gateways table
ms:assetid: a909daad-d137-45e0-b149-1de9f8e1e029
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412795(v=OCS.15)
ms:contentKeyID: 48185034
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b43adbf088e696b38ff8159e87e2b5b4e8608d38
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/16/2020
ms.locfileid: "48512664"
---
# <a name="gateways-table-in-lync-server-2013"></a>Lync Server 2013 のゲートウェイテーブル

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2010-11-05_

ゲートウェイテーブルは、サポートテーブルです。 各レコードには、データベースにレコードを含む公衆交換電話網 (PSTN) 呼び出しに関係する1つのゲートウェイに関する情報が格納されます。


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
<td><p><strong>GatewayId</strong></p></td>
<td><p>int</p></td>
<td><p>Primary</p></td>
<td><p>このゲートウェイを識別する一意の番号。</p></td>
</tr>
<tr class="even">
<td><p><strong>ゲートウェイ</strong></p></td>
<td><p>nvarchar (256)</p></td>
<td><p> </p></td>
<td><p>ゲートウェイ名。</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

