---
title: 'Lync Server 2013: Phones テーブル'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Phones table
ms:assetid: 41cb356d-9cc8-42b6-ac23-98a61b25aadc
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425923(v=OCS.15)
ms:contentKeyID: 48183996
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: cddf5eac7cc85852f4a7f61f4b746091158257e2
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41755187"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="phones-table-in-lync-server-2013"></a>Lync Server 2013 の Phones テーブル

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2012-08-20_

電話の表はサポートテーブルです。 テーブル内の各レコードには、データベース内にレコードがある VoIP 通話に関連する1つの電話番号に関する情報が格納されます。


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
<td><p><strong>PhoneId</strong></p></td>
<td><p>int</p></td>
<td><p>Primary</p></td>
<td><p>この電話を識別する一意の番号。</p></td>
</tr>
<tr class="even">
<td><p><strong>電話の Uri</strong></p></td>
<td><p>nvarchar (450)</p></td>
<td><p> </p></td>
<td><p>電話番号。</p></td>
</tr>
<tr class="odd">
<td><p><strong>Nextupdatupdat</strong></p></td>
<td><p>dateTime</p></td>
<td></td>
<td><p>タイムスタンプ (内部使用のみ)。</p>
<p>このフィールドは、Microsoft Lync Server 2013 で導入されました。</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

