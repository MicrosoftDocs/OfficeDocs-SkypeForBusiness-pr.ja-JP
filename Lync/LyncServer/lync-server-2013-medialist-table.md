---
title: 'Lync Server 2013: MediaList テーブル'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: MediaList table
ms:assetid: 1f440590-c1bc-483e-b7bc-6cc763847768
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398279(v=OCS.15)
ms:contentKeyID: 48183579
ms.date: 07/12/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6fe16e903a1dfbc958336dca68903ca80770995d
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2020
ms.locfileid: "42039491"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="medialist-table-in-lync-server-2013"></a>Lync Server 2013 の MediaList テーブル

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2016-07-12_

MediaList テーブルは、さまざまなメディアの種類の一覧を格納する静的なテーブルです。


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
<td><p><strong>MediaId</strong></p></td>
<td><p>tinyint</p></td>
<td><p>Primary</p></td>
<td><p>値: 1-7</p></td>
</tr>
<tr class="even">
<td><p><strong>メディア</strong></p></td>
<td><p>nvarchar (256)</p></td>
<td></td>
<td><p>MediaID とメディアの値の静的マッピング:</p>
<ul>
<li><p>1– IM</p></li>
<li><p>2 -- ファイル転送</p></li>
<li><p>3 -- リモート アシスタンス</p></li>
<li><p>4 -- アプリケーション共有</p></li>
<li><p>5–音声</p></li>
<li><p>6–ビデオ</p></li>
<li><p>7 -- アプリケーション招待</p></li>
</ul></td>
</tr>
</tbody>
</table>


LcsCDR MediaTypes の値のモダリティの種類を決定しようとしている場合は、次の Join スニペットを使用する必要があります。

    LEFT JOIN on Media.MediaId = MediaList.MediaId

</div>

<span> </span>

</div>

</div>

</div>

