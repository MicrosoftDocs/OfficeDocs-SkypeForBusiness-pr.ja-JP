---
title: 'Lync Server 2013: Conference テーブル'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Conference table
ms:assetid: 2a2c327c-4719-42dc-a3bb-6dbc0864d9af
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425762(v=OCS.15)
ms:contentKeyID: 48183700
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f57f7baf017507da44677cc475c99d192fe868f0
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34840490"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="conference-table-in-lync-server-2013"></a>Lync Server 2013 の Conference テーブル

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2012-10-02_

会議の表は、サポートされているテーブルです。 各レコードは、1つの会議またはピアツーピアセッションを表します。


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
<td><p><strong>ConferenceKey</strong></p></td>
<td><p>int</p></td>
<td><p>Primary</p></td>
<td><p>この会議レコードを識別する一意の番号です。</p></td>
</tr>
<tr class="even">
<td><p><strong>ConfURI</strong></p></td>
<td><p>nvarchar (450)</p></td>
<td><p>一意</p></td>
<td><p>会議の URI (会議の場合) または [この Id がピアツーピアセッションの場合] です。</p></td>
</tr>
<tr class="odd">
<td><p><strong>サム</strong></p></td>
<td><p>int</p></td>
<td><p>位置</p></td>
<td><p>会議 URI のチェックサム。 これは内部的に使用されます。</p></td>
</tr>
<tr class="even">
<td><p><strong>Nextupdatupdat</strong></p></td>
<td><p>datetime</p></td>
<td></td>
<td><p>内部使用のみ。</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

