---
title: 'Lync Server 2013: UserStatistics テーブル'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: UserStatistics table
ms:assetid: cfaf803b-1679-4169-92d3-533fad3e56ed
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721893(v=OCS.15)
ms:contentKeyID: 49733827
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f0f684850625f61ca72bbcc9c4bc53b56fcc6b38
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34848318"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="userstatistics-table-in-lync-server-2013"></a>Lync Server 2013 の UserStatistics テーブル

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2012-09-28_

UserStatistics テーブルは、サポートテーブルです。 テーブルの各レコードには、個々のユーザーによるシステムの使用状況に関する情報が格納されます。 この表は、Microsoft Lync Server 2013 で導入されました。


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
<td><p>このユーザーを識別する一意の番号です。</p></td>
</tr>
<tr class="even">
<td><p><strong>最終ログイン時間</strong></p></td>
<td><p>datetime</p></td>
<td></td>
<td><p>前回ユーザーがログインした日時。</p></td>
</tr>
<tr class="odd">
<td><p><strong>Lastconforizedtime</strong></p></td>
<td><p>datetime</p></td>
<td></td>
<td><p>ユーザーが最後に会議を開催した日時。</p></td>
</tr>
<tr class="even">
<td><p><strong>Lastcallオーガナイザー Ercallfailuretime</strong></p></td>
<td><p>datetime</p></td>
<td></td>
<td><p>前回ユーザーが通話の失敗を経験した日時。</p></td>
</tr>
<tr class="odd">
<td><p><strong>Lastconforガント Izercallfailuretime</strong></p></td>
<td><p>datetime</p></td>
<td></td>
<td><p>前回ユーザーが会議開催者として通話の失敗を経験した時刻。</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

