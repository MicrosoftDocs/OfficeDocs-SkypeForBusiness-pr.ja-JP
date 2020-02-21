---
title: 'Lync Server 2013: 場所テーブル'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Locations table
ms:assetid: 78dc1b14-5394-4f8e-89d3-4ba593272a04
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398596(v=OCS.15)
ms:contentKeyID: 48184579
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d93300acda297a026af03070680825899a608d86
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/21/2020
ms.locfileid: "42186410"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="locations-table-in-lync-server-2013"></a>Lync Server 2013 の場所テーブル

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2012-05-25_

それぞれのレコードは、E9-1-1 通話など、緊急通話における 1 つの場所の参照を表します。


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
<td><p><strong>SessionIdTime</strong></p></td>
<td><p>日付型</p></td>
<td><p>主/プライマリ、外部</p></td>
<td><p>セッション要求の時刻。 セッションを一意に識別するために <strong>SessionIdSeq</strong> と併用されます。 詳細については、「 <a href="lync-server-2013-dialogs-table.md">Lync Server 2013 のダイアログテーブル</a>」を参照してください。</p></td>
</tr>
<tr class="even">
<td><p><strong>Sessionidseq と</strong></p></td>
<td><p>int</p></td>
<td><p>主/プライマリ、外部</p></td>
<td><p>セッションを識別するための ID 番号。 セッションを一意に識別するために <strong>SessionIdTime</strong> と併用されます。 詳細については、「 <a href="lync-server-2013-dialogs-table.md">Lync Server 2013 のダイアログテーブル</a>」を参照してください。</p></td>
</tr>
<tr class="odd">
<td><p><strong>場所</strong></p></td>
<td><p>nvarchar (max)</p></td>
<td></td>
<td><p>緊急通話の場所。</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

