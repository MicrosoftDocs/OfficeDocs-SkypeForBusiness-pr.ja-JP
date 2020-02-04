---
title: 'Lync Server 2013: FileTransfers テーブル'
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
ms.openlocfilehash: de8a3e69c670c273bcdd91ac5895c0b1f0b15d80
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41743366"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="filetransfers-table-in-lync-server-2013"></a>Lync Server 2013 の FileTransfers テーブル

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2012-09-28_

各レコードは、1つのファイル転送セッションを表します。


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
<td><p><strong>セッション Id</strong></p></td>
<td><p>datetime</p></td>
<td><p>プライマリ、外部</p></td>
<td><p>セッション要求の時刻。 セッションを一意に識別するために<strong>Sessionidseq</strong>と組み合わせて使用されます。 詳細については、「 <a href="lync-server-2013-dialogs-table.md">Lync Server 2013 のダイアログテーブル</a>」を参照してください。</p></td>
</tr>
<tr class="even">
<td><p><strong>SessionIdSeq</strong></p></td>
<td><p>int</p></td>
<td><p>プライマリ、外部</p></td>
<td><p>セッションを識別する ID 番号。 セッションを一意に識別するために<strong>Sessionidtime</strong>と組み合わせて使用されます。 詳細については、「 <a href="lync-server-2013-dialogs-table.md">Lync Server 2013 のダイアログテーブル</a>」を参照してください。</p></td>
</tr>
<tr class="odd">
<td><p><strong>ファイル名</strong></p></td>
<td><p>nvarchar(256)</p></td>
<td></td>
<td><p>ファイルの名前。</p></td>
</tr>
<tr class="even">
<td><p><strong>FileIdentity</strong></p></td>
<td><p>長さ</p></td>
<td></td>
<td><p>同じファイル名を含むファイル転送を区別する一意の識別子。</p></td>
</tr>
<tr class="odd">
<td><p><strong>クッキー</strong></p></td>
<td><p>nvarchar(128</p></td>
<td><p>Primary</p></td>
<td><p>すべてのフォローアップメッセージをこのメールに関連付けられているものとして識別するために使用されます。</p></td>
</tr>
<tr class="even">
<td><p><strong>受諾</strong></p></td>
<td><p>bit</p></td>
<td></td>
<td><p>TRUE または NULL を指定できます。 TRUE の場合は、拒否とキャンセルは NULL になります。</p></td>
</tr>
<tr class="odd">
<td><p><strong>拒否</strong></p></td>
<td><p>bit</p></td>
<td></td>
<td><p>TRUE または NULL を指定できます。 TRUE の場合は、Accept と Cancel は NULL になります。</p></td>
</tr>
<tr class="even">
<td><p><strong>キャンセル</strong></p></td>
<td><p>bit</p></td>
<td></td>
<td><p>TRUE または NULL を指定できます。 TRUE の場合は、Accept と Reject は NULL になります。</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

