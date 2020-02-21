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
ms.openlocfilehash: 8c833ab255741b6a2f28ce9d72f46226c42baea3
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/21/2020
ms.locfileid: "42217613"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="media-table-in-lync-server-2013"></a>Lync Server 2013 のメディアテーブル

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2012-09-28_

各レコードは、ピアツーピア セッションで使用される 1 つのメディア種類を表します。複数のメディア種類が使用されている場合、1 つのセッションがテーブルでは複数のレコードによって表されます。

<div>


> [!NOTE]  
> Media テーブルを使用してセッションでのメディアの継続時間を計算することはできません。このテーブルには、セッションでのメディア交換の信号の詳細が格納されます。メディア交換は INVITE 要求によって行われ、StartTime は INVITE が送信された時刻を示します。メディアはセッション参加者がセッションを受け付けた後でのみ開始するので、招待時間は必ずしもメディアの開始時刻を意味しません。EndTime は、通常、このセッションの終了時刻を意味します。



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
<td><p><strong>MediaId</strong></p></td>
<td><p>tinyint</p></td>
<td><p>主/プライマリ、外部</p></td>
<td><p>このメディアの種類を示す一意の番号。 詳細については、「 <a href="lync-server-2013-medialist-table.md">Lync Server 2013 の Medialist table</a> 」を参照してください。</p></td>
</tr>
<tr class="even">
<td><p><strong>StartTime</strong></p></td>
<td><p>日付型</p></td>
<td><p>Primary</p></td>
<td><p>メディア要求が送信された時刻です。実際にメディアが開始した時刻ではありません。<strong>StartTime</strong> にはセッションのセットアップ時間が含まれます。</p></td>
</tr>
<tr class="odd">
<td><p><strong>EndTime</strong></p></td>
<td><p>日付型</p></td>
<td></td>
<td><p>セッションの終了時刻です。</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

