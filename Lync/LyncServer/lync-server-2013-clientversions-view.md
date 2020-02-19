---
title: 'Lync Server 2013: ClientVersions ビュー'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: ClientVersions view
ms:assetid: caf7678f-83a0-46c8-83cc-fee4c3991f52
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721891(v=OCS.15)
ms:contentKeyID: 49733825
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: cf10e56acf6e719a5d5bd63d661cb4a5362e172f
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/19/2020
ms.locfileid: "42138535"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="clientversions-view-in-lync-server-2013"></a>Lync Server 2013 の ClientVersions ビュー

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2012-10-01_

ClientVersions ビューは、データベースに記録されるセッションに参加した、さまざまなクライアントの種類およびバージョンの情報を格納します。 ビュー内の各レコードは、1 つのクライアント バージョンを表します。 このビューは Microsoft Lync Server 2013 で導入されました。

<div>


> [!NOTE]  
> 一部の列には複数のレコードが存在する場合があります。



</div>


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
<td><p><strong>VersionId</strong></p></td>
<td><p>int</p></td>
<td><p>このクライアントの種類とバージョンを識別する一意の番号。</p></td>
</tr>
<tr class="even">
<td><p><strong>バージョン</strong></p></td>
<td><p>nvarchar (256)</p></td>
<td><p>ユーザー エージェントを表す。</p></td>
</tr>
<tr class="odd">
<td><p><strong>ClientType</strong></p></td>
<td><p>int</p></td>
<td><p>クライアントの種類。</p></td>
</tr>
<tr class="even">
<td><p><strong>ClientCategory</strong></p></td>
<td><p>nvarchar (64)</p></td>
<td><p>クライアントが属するカテゴリ。たとえば、Conferencing_Attendant_1.0 というクライアントは CAA という ClientCategory に属します。</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

