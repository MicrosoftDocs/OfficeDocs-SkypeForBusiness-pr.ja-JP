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
ms.openlocfilehash: b92c8a0a6957eed00cf4e25f60ce2e0ff24d1fd2
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41762995"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="medialist-table-in-lync-server-2013"></a>Lync Server 2013 の MediaList テーブル

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2016-07-12_

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
<td><p>値: 1 -7</p></td>
</tr>
<tr class="even">
<td><p><strong>メディア</strong></p></td>
<td><p>nvarchar(256)</p></td>
<td></td>
<td><p>MediaID 値と Media 値の固定マッピング:</p>
<ul>
<li><p>1– IM</p></li>
<li><p>2 – ファイル転送</p></li>
<li><p>3 – リモート アシスタンス</p></li>
<li><p>4 – アプリケーション共有</p></li>
<li><p>5-オーディオ</p></li>
<li><p>6-ビデオ</p></li>
<li><p>7 – アプリケーション招待</p></li>
</ul></td>
</tr>
</tbody>
</table>


LcsCDR.SessionDetailsView.MediaTypes の値でモダリティの種類を特定しようとしている場合は、次の Join スニペットを使用する必要があります。

    LEFT JOIN on Media.MediaId = MediaList.MediaId

</div>

<span> </span>

</div>

</div>

</div>

