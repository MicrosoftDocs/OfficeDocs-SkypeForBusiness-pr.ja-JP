---
title: 'Lync Server 2013: UserAgent view'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: UserAgent view
ms:assetid: b986f76f-f16e-4e5e-96cb-6e8f7f9b42ee
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721862(v=OCS.15)
ms:contentKeyID: 49733795
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8f7d4cf6d79bdd69b28fb88f9a7d6c6a2095ba99
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34848333"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="useragent-view-in-lync-server-2013"></a>Lync Server 2013 での UserAgent の表示

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2012-10-03_

UserAgent ビューには、データベース内のレコードを持つセッションに関連しているユーザーエージェントに関する情報が格納されます。 このビューは、Microsoft Lync Server 2013 で導入されました。


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>列</th>
<th>データ型</th>
<th>詳細</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>UserAgentKey</p></td>
<td><p>int</p></td>
<td><p>このユーザーエージェントを識別する一意の番号です。</p></td>
</tr>
<tr class="even">
<td><p>UserAgent</p></td>
<td><p>nvarchar(256)</p></td>
<td><p>ユーザーエージェント文字列。</p></td>
</tr>
<tr class="odd">
<td><p>UAType</p></td>
<td><p>smallint</p></td>
<td><p>ユーザーエージェントの種類。 詳細については、「 <a href="lync-server-2013-useragent-table.md">Lync Server 2013 の UserAgent テーブル</a>」を参照してください。</p></td>
</tr>
<tr class="even">
<td><p>UACategory</p></td>
<td><p>nvarchar (64)</p></td>
<td><p>ユーザーエージェントが属しているカテゴリ。 たとえば、ユーザーエージェント Conferencing_Attendant_ 1.0 は UACategory CAA をに属しています。</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

