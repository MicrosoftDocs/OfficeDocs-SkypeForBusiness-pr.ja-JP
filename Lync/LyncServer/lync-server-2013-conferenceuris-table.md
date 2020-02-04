---
title: 'Lync Server 2013: ConferenceUris テーブル'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: ConferenceUris table
ms:assetid: b1721d52-3c65-45ea-8997-06af8fef93fc
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412854(v=OCS.15)
ms:contentKeyID: 48185160
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3cacbaf4e8c7c826ae2e00e9c86b44cc8387f315
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41741577"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="conferenceuris-table-in-lync-server-2013"></a>Lync Server 2013 の ConferenceUris テーブル

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2012-05-25_

ConfereneUris テーブルは、データベースに記録された会議セッションに参加しているさまざまな会議の Uri のリストを格納するサポートテーブルです。 テーブル内の各レコードは、1つの会議 URI を表します。


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
<td><p><strong>Nextupdatupdat</strong></p></td>
<td><p>datetime</p></td>
<td><p>Primary</p></td>
<td><p>タイムスタンプ、内部使用。</p></td>
</tr>
<tr class="even">
<td><p><strong>ConferenceUriId</strong></p></td>
<td><p>int</p></td>
<td><p>Primary</p></td>
<td><p>この会議 URI を識別する一意の番号です。</p></td>
</tr>
<tr class="odd">
<td><p><strong>ConferenceUri</strong></p></td>
<td><p>nvarchar (450)</p></td>
<td></td>
<td><p>会議の URI。</p></td>
</tr>
<tr class="even">
<td><p><strong>サム</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>ConferenceUri のチェックサム。 データベースの検索速度を上げるために使われます。</p></td>
</tr>
<tr class="odd">
<td><p><strong>UriTypeId</strong></p></td>
<td><p>int</p></td>
<td><p>外部</p></td>
<td><p>URI の種類 ("conf: IM 会議用チャット" または "conf: 音声/ビデオ会議用のオーディオビデオ" など)。 詳細については、「 <a href="lync-server-2013-uritypes-table.md">Lync Server 2013 テーブルの UriTypes テーブル</a>」を参照してください。</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

