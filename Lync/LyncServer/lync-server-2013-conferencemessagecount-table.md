---
title: 'Lync Server 2013: ConferenceMessageCount テーブル'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: ConferenceMessageCount table
ms:assetid: 78569dbf-5217-42fa-ba1a-4380f56e2a3d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398590(v=OCS.15)
ms:contentKeyID: 48184570
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 426ae4abca9f91fcabaedfb5a363703523d6aa94
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41740027"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="conferencemessagecount-table-in-lync-server-2013"></a>Lync Server 2013 の ConferenceMessageCount テーブル

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2012-09-28_

このテーブル内の各レコードは、1人の IM 会議で1人のユーザーを表し、そのユーザーから送信されたメッセージの数が含まれます。 各会議は、この表の複数のレコードで表されます。ユーザーごとに1つのレコード。


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
<td><p>会議インスタンスの時刻。 電話会議インスタンスを一意に識別するために<strong>Sessionidseq</strong>と組み合わせて使用されます。 詳細については、「 <a href="lync-server-2013-conferences-table.md">Lync Server 2013 での会議の表</a>」を参照してください。</p></td>
</tr>
<tr class="even">
<td><p><strong>SessionIdSeq</strong></p></td>
<td><p>int</p></td>
<td><p>プライマリ、外部</p></td>
<td><p>会議インスタンスを識別する ID 番号。 電話会議インスタンスを一意に識別するために<strong>Sessionidtime</strong>と組み合わせて使用されます。 詳細については、「 <a href="lync-server-2013-conferences-table.md">Lync Server 2013 での会議の表</a>」を参照してください。</p></td>
</tr>
<tr class="odd">
<td><p><strong>UserId</strong></p></td>
<td><p>int</p></td>
<td><p>外部</p></td>
<td><p>このユーザーを識別する一意の番号です。 <a href="lync-server-2013-users-table.md">Lync Server 2013 の [ユーザー] テーブル</a>から参照されます。</p></td>
</tr>
<tr class="even">
<td><p><strong>MessageCount</strong></p></td>
<td><p>smallint</p></td>
<td><p> </p></td>
<td><p>この会議中にこのユーザーによって送信されたメッセージの数です。</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

