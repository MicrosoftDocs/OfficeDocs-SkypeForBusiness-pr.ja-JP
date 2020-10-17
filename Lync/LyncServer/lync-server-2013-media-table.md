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
ms.openlocfilehash: 369e1ace7e0f3f9326896373a640597360ded81d
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/16/2020
ms.locfileid: "48516174"
---
# <a name="media-table-in-lync-server-2013"></a><span data-ttu-id="1fdc7-102">Lync Server 2013 のメディアテーブル</span><span class="sxs-lookup"><span data-stu-id="1fdc7-102">Media table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1fdc7-103">_**トピックの最終更新日:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="1fdc7-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="1fdc7-p101">各レコードは、ピアツーピア セッションで使用される 1 つのメディア種類を表します。複数のメディア種類が使用されている場合、1 つのセッションがテーブルでは複数のレコードによって表されます。</span><span class="sxs-lookup"><span data-stu-id="1fdc7-p101">Each record represents one media type used in a peer-to-peer session. One session would be represented by multiple records in the table, if more than one media type is used.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="1fdc7-p102">Media テーブルを使用してセッションでのメディアの継続時間を計算することはできません。このテーブルには、セッションでのメディア交換の信号の詳細が格納されます。メディア交換は INVITE 要求によって行われ、StartTime は INVITE が送信された時刻を示します。メディアはセッション参加者がセッションを受け付けた後でのみ開始するので、招待時間は必ずしもメディアの開始時刻を意味しません。EndTime は、通常、このセッションの終了時刻を意味します。</span><span class="sxs-lookup"><span data-stu-id="1fdc7-p102">The Media table should not be used to calculate the media duration for a session. This table contains the signaling details of media exchange in a session. Media exchange is done by the INVITE request, and StartTime indicates the time that the INVITE was sent out. The invite time does not necessarily mean the media start time, because media starts only after the sessionee accepts the session. The EndTime usually means the end time of this session.</span></span>



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
<th><span data-ttu-id="1fdc7-110">Column</span><span class="sxs-lookup"><span data-stu-id="1fdc7-110">Column</span></span></th>
<th><span data-ttu-id="1fdc7-111">データ型</span><span class="sxs-lookup"><span data-stu-id="1fdc7-111">Data Type</span></span></th>
<th><span data-ttu-id="1fdc7-112">キー/インデックス</span><span class="sxs-lookup"><span data-stu-id="1fdc7-112">Key/Index</span></span></th>
<th><span data-ttu-id="1fdc7-113">詳細</span><span class="sxs-lookup"><span data-stu-id="1fdc7-113">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="1fdc7-114"><strong>SessionIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="1fdc7-114"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="1fdc7-115">日付型</span><span class="sxs-lookup"><span data-stu-id="1fdc7-115">datetime</span></span></p></td>
<td><p><span data-ttu-id="1fdc7-116">主/プライマリ、外部</span><span class="sxs-lookup"><span data-stu-id="1fdc7-116">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="1fdc7-117">セッション要求の時刻。</span><span class="sxs-lookup"><span data-stu-id="1fdc7-117">Time of session request.</span></span> <span data-ttu-id="1fdc7-118">セッションを一意に識別するために <strong>SessionIdSeq</strong> と併用されます。</span><span class="sxs-lookup"><span data-stu-id="1fdc7-118">Used in conjunction with <strong>SessionIdSeq</strong> to uniquely identify a session.</span></span> <span data-ttu-id="1fdc7-119">詳細については、「 <a href="lync-server-2013-dialogs-table.md">Lync Server 2013 のダイアログテーブル</a> 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1fdc7-119">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1fdc7-120"><strong>Sessionidseq と</strong></span><span class="sxs-lookup"><span data-stu-id="1fdc7-120"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="1fdc7-121">int</span><span class="sxs-lookup"><span data-stu-id="1fdc7-121">int</span></span></p></td>
<td><p><span data-ttu-id="1fdc7-122">主/プライマリ、外部</span><span class="sxs-lookup"><span data-stu-id="1fdc7-122">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="1fdc7-123">セッションを識別するための ID 番号。</span><span class="sxs-lookup"><span data-stu-id="1fdc7-123">ID number to identify the session.</span></span> <span data-ttu-id="1fdc7-124">セッションを一意に識別するために <strong>SessionIdTime</strong> と併用されます。</span><span class="sxs-lookup"><span data-stu-id="1fdc7-124">Used in conjunction with <strong>SessionIdTime</strong> to uniquely identify a session.</span></span> <span data-ttu-id="1fdc7-125">詳細については、「 <a href="lync-server-2013-dialogs-table.md">Lync Server 2013 のダイアログテーブル</a> 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1fdc7-125">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1fdc7-126"><strong>MediaId</strong></span><span class="sxs-lookup"><span data-stu-id="1fdc7-126"><strong>MediaId</strong></span></span></p></td>
<td><p><span data-ttu-id="1fdc7-127">tinyint</span><span class="sxs-lookup"><span data-stu-id="1fdc7-127">tinyint</span></span></p></td>
<td><p><span data-ttu-id="1fdc7-128">主/プライマリ、外部</span><span class="sxs-lookup"><span data-stu-id="1fdc7-128">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="1fdc7-129">このメディアの種類を示す一意の番号。</span><span class="sxs-lookup"><span data-stu-id="1fdc7-129">Unique number identifying this media type.</span></span> <span data-ttu-id="1fdc7-130">詳細については、「 <a href="lync-server-2013-medialist-table.md">Lync Server 2013 の Medialist table</a> 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1fdc7-130">See the <a href="lync-server-2013-medialist-table.md">MediaList table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1fdc7-131"><strong>StartTime</strong></span><span class="sxs-lookup"><span data-stu-id="1fdc7-131"><strong>StartTime</strong></span></span></p></td>
<td><p><span data-ttu-id="1fdc7-132">日付型</span><span class="sxs-lookup"><span data-stu-id="1fdc7-132">datetime</span></span></p></td>
<td><p><span data-ttu-id="1fdc7-133">Primary</span><span class="sxs-lookup"><span data-stu-id="1fdc7-133">Primary</span></span></p></td>
<td><p><span data-ttu-id="1fdc7-p106">メディア要求が送信された時刻です。実際にメディアが開始した時刻ではありません。<strong>StartTime</strong> にはセッションのセットアップ時間が含まれます。</span><span class="sxs-lookup"><span data-stu-id="1fdc7-p106">This is the time that a media request was sent out, not the real media start time. <strong>StartTime</strong> includes the session setup time.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1fdc7-136"><strong>EndTime</strong></span><span class="sxs-lookup"><span data-stu-id="1fdc7-136"><strong>EndTime</strong></span></span></p></td>
<td><p><span data-ttu-id="1fdc7-137">日付型</span><span class="sxs-lookup"><span data-stu-id="1fdc7-137">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="1fdc7-138">セッションの終了時刻です。</span><span class="sxs-lookup"><span data-stu-id="1fdc7-138">This is the end time of the session.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

