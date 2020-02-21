---
title: 'Lync Server 2013: UserStatistics テーブル'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: UserStatistics table
ms:assetid: cfaf803b-1679-4169-92d3-533fad3e56ed
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721893(v=OCS.15)
ms:contentKeyID: 49733827
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 876d861e62014738816c02e2a6c2628f5dd46fc0
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/21/2020
ms.locfileid: "42212883"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="userstatistics-table-in-lync-server-2013"></a>Lync Server 2013 の UserStatistics テーブル

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2012-09-28_

UserStatistics テーブルはサポート テーブルです。 このテーブル内の各レコードは、システムの個々のユーザーの使用状況についての情報を格納しています。 この表は、Microsoft Lync Server 2013 で導入されました。


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
<td><p><strong>UserId</strong></p></td>
<td><p>int</p></td>
<td><p>Primary</p></td>
<td><p>このユーザーを識別する一意の番号。</p></td>
</tr>
<tr class="even">
<td><p><strong>LastLogInTime</strong></p></td>
<td><p>日付型</p></td>
<td></td>
<td><p>ユーザーが最後にログインした時刻。</p></td>
</tr>
<tr class="odd">
<td><p><strong>Lastconforガント Izedtime</strong></p></td>
<td><p>日付型</p></td>
<td></td>
<td><p>ユーザーが最後に会議を開催した時刻。</p></td>
</tr>
<tr class="even">
<td><p><strong>Lastcallオーガナイザー Ercallfailuretime</strong></p></td>
<td><p>日付型</p></td>
<td></td>
<td><p>ユーザーが最後に通話に失敗した時刻。</p></td>
</tr>
<tr class="odd">
<td><p><strong>Lastconforガント Izercallfailuretime</strong></p></td>
<td><p>日付型</p></td>
<td></td>
<td><p>ユーザーが会議開催者として最後に通話に失敗した時刻。</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

