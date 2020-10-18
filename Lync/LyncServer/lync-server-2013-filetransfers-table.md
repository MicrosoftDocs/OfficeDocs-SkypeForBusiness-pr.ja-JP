---
title: 'Lync Server 2013: FileTransfers テーブル'
description: 'Lync Server 2013: FileTransfers テーブル。'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: FileTransfers table
ms:assetid: 5368e67c-d8a9-43a1-9472-a839950dedb3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398353(v=OCS.15)
ms:contentKeyID: 48184118
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ccde45fa3743a809499273676d567846ef292ecc
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48573363"
---
# <a name="filetransfers-table-in-lync-server-2013"></a>Lync Server 2013 の FileTransfers テーブル

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2012-09-28_

各レコードは、1 つのファイル転送セッションを表します。


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
<td><p><strong>SessionIdTime</strong></p></td>
<td><p>日付型</p></td>
<td><p>主/プライマリ、外部</p></td>
<td><p>セッション要求の時刻。 セッションを一意に識別するために <strong>SessionIdSeq</strong> と併用されます。 詳細については、「 <a href="lync-server-2013-dialogs-table.md">Lync Server 2013 のダイアログテーブル</a> 」を参照してください。</p></td>
</tr>
<tr class="even">
<td><p><strong>Sessionidseq と</strong></p></td>
<td><p>int</p></td>
<td><p>主/プライマリ、外部</p></td>
<td><p>セッションを識別するための ID 番号。 セッションを一意に識別するために <strong>SessionIdTime</strong> と併用されます。 詳細については、「 <a href="lync-server-2013-dialogs-table.md">Lync Server 2013 のダイアログテーブル</a> 」を参照してください。</p></td>
</tr>
<tr class="odd">
<td><p><strong>File Name</strong></p></td>
<td><p>nvarchar (256)</p></td>
<td></td>
<td><p>ファイルの名前。</p></td>
</tr>
<tr class="even">
<td><p><strong>FileIdentity</strong></p></td>
<td><p>識別子</p></td>
<td></td>
<td><p>同じファイル名を含むファイル転送を区別するための一意の識別子。</p></td>
</tr>
<tr class="odd">
<td><p><strong>クッキー</strong></p></td>
<td><p>nvarchar(128</p></td>
<td><p>Primary</p></td>
<td><p>すべてのフォローアップ メッセージをこれに関連付けられたものとして識別するために使用します。</p></td>
</tr>
<tr class="even">
<td><p><strong>Accept</strong></p></td>
<td><p>若干</p></td>
<td></td>
<td><p>TRUE または NULL。TRUE の場合は、Reject と Cancel が NULL になります。</p></td>
</tr>
<tr class="odd">
<td><p><strong>拒否する</strong></p></td>
<td><p>若干</p></td>
<td></td>
<td><p>TRUE または NULL。TRUE の場合は、Accept と Cancel が NULL になります。</p></td>
</tr>
<tr class="even">
<td><p><strong>Cancel</strong></p></td>
<td><p>若干</p></td>
<td></td>
<td><p>TRUE または NULL。TRUE の場合は、Accept と Reject が NULL になります。</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

