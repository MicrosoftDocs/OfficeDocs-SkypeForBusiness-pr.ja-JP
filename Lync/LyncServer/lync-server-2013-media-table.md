---
title: 'Lync Server 2013: Media テーブル'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Media table
ms:assetid: 1e1b427f-59b5-4564-bde5-1002a80439ee
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398268(v=OCS.15)
ms:contentKeyID: 48183568
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 69f9ad10c5c06ab8a9d2bc95eddceb67b20e745c
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41765105"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="media-table-in-lync-server-2013"></a>Lync Server 2013 の Media テーブル

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2012-09-28_

各レコードは、ピアツーピアセッションで使用される1つのメディアの種類を表します。 複数のメディアの種類を使用している場合は、1つのセッションがテーブル内の複数のレコードで表されます。

<div>


> [!NOTE]  
> メディアテーブルを使って、セッションのメディアの再生時間を計算することはできません。 この表には、セッションでのメディア交換の信号の詳細が含まれています。 メディア交換は INVITE 要求によって実行され、StartTime は招待が送信された時間を示します。この招待は、セッションの開始時刻を意味するわけではありません。これは、セッションを開始した後にのみメディアが開始されるためです。 通常、EndTime はこのセッションの終了時刻を示します。



</div>


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
<td><p><strong>MediaId</strong></p></td>
<td><p>tinyint</p></td>
<td><p>プライマリ、外部</p></td>
<td><p>このメディアの種類を識別する一意の番号です。 詳細については、「 <a href="lync-server-2013-medialist-table.md">Lync Server 2013 の Medialist の表</a>」を参照してください。</p></td>
</tr>
<tr class="even">
<td><p><strong>StartTime</strong></p></td>
<td><p>datetime</p></td>
<td><p>Primary</p></td>
<td><p>これは、実際のメディアの開始時刻ではなく、メディア要求が送信された時刻です。 <strong>StartTime</strong>には、セッションのセットアップ時間が含まれます。</p></td>
</tr>
<tr class="odd">
<td><p><strong>EndTime</strong></p></td>
<td><p>datetime</p></td>
<td></td>
<td><p>これはセッションの終了時刻です。</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

