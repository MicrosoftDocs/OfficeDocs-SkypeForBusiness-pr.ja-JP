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
ms.openlocfilehash: 55df55ba8c9953a1efce25269c24b43328472d7f
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/16/2020
ms.locfileid: "48529994"
---
# <a name="userstatistics-table-in-lync-server-2013"></a>Lync Server 2013 の UserStatistics テーブル

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



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
<th>Column</th>
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

