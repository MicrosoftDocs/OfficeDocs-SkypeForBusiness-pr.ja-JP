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

# <a name="media-table-in-lync-server-2013"></a><span data-ttu-id="c9ff5-102">Lync Server 2013 の Media テーブル</span><span class="sxs-lookup"><span data-stu-id="c9ff5-102">Media table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c9ff5-103">_**最終更新日:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="c9ff5-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="c9ff5-104">各レコードは、ピアツーピアセッションで使用される1つのメディアの種類を表します。</span><span class="sxs-lookup"><span data-stu-id="c9ff5-104">Each record represents one media type used in a peer-to-peer session.</span></span> <span data-ttu-id="c9ff5-105">複数のメディアの種類を使用している場合は、1つのセッションがテーブル内の複数のレコードで表されます。</span><span class="sxs-lookup"><span data-stu-id="c9ff5-105">One session would be represented by multiple records in the table, if more than one media type is used.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="c9ff5-106">メディアテーブルを使って、セッションのメディアの再生時間を計算することはできません。</span><span class="sxs-lookup"><span data-stu-id="c9ff5-106">The Media table should not be used to calculate the media duration for a session.</span></span> <span data-ttu-id="c9ff5-107">この表には、セッションでのメディア交換の信号の詳細が含まれています。</span><span class="sxs-lookup"><span data-stu-id="c9ff5-107">This table contains the signaling details of media exchange in a session.</span></span> <span data-ttu-id="c9ff5-108">メディア交換は INVITE 要求によって実行され、StartTime は招待が送信された時間を示します。この招待は、セッションの開始時刻を意味するわけではありません。これは、セッションを開始した後にのみメディアが開始されるためです。</span><span class="sxs-lookup"><span data-stu-id="c9ff5-108">Media exchange is done by the INVITE request, and StartTime indicates the time that the INVITE was sent out. The invite time does not necessarily mean the media start time, because media starts only after the sessionee accepts the session.</span></span> <span data-ttu-id="c9ff5-109">通常、EndTime はこのセッションの終了時刻を示します。</span><span class="sxs-lookup"><span data-stu-id="c9ff5-109">The EndTime usually means the end time of this session.</span></span>



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
<th><span data-ttu-id="c9ff5-110">列</span><span class="sxs-lookup"><span data-stu-id="c9ff5-110">Column</span></span></th>
<th><span data-ttu-id="c9ff5-111">データ型</span><span class="sxs-lookup"><span data-stu-id="c9ff5-111">Data Type</span></span></th>
<th><span data-ttu-id="c9ff5-112">キー/インデックス</span><span class="sxs-lookup"><span data-stu-id="c9ff5-112">Key/Index</span></span></th>
<th><span data-ttu-id="c9ff5-113">詳細</span><span class="sxs-lookup"><span data-stu-id="c9ff5-113">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c9ff5-114"><strong>セッション Id</strong></span><span class="sxs-lookup"><span data-stu-id="c9ff5-114"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="c9ff5-115">datetime</span><span class="sxs-lookup"><span data-stu-id="c9ff5-115">datetime</span></span></p></td>
<td><p><span data-ttu-id="c9ff5-116">プライマリ、外部</span><span class="sxs-lookup"><span data-stu-id="c9ff5-116">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="c9ff5-117">セッション要求の時刻。</span><span class="sxs-lookup"><span data-stu-id="c9ff5-117">Time of session request.</span></span> <span data-ttu-id="c9ff5-118">セッションを一意に識別するために<strong>Sessionidseq</strong>と組み合わせて使用されます。</span><span class="sxs-lookup"><span data-stu-id="c9ff5-118">Used in conjunction with <strong>SessionIdSeq</strong> to uniquely identify a session.</span></span> <span data-ttu-id="c9ff5-119">詳細については、「 <a href="lync-server-2013-dialogs-table.md">Lync Server 2013 のダイアログテーブル</a>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c9ff5-119">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c9ff5-120"><strong>SessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="c9ff5-120"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="c9ff5-121">int</span><span class="sxs-lookup"><span data-stu-id="c9ff5-121">int</span></span></p></td>
<td><p><span data-ttu-id="c9ff5-122">プライマリ、外部</span><span class="sxs-lookup"><span data-stu-id="c9ff5-122">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="c9ff5-123">セッションを識別する ID 番号。</span><span class="sxs-lookup"><span data-stu-id="c9ff5-123">ID number to identify the session.</span></span> <span data-ttu-id="c9ff5-124">セッションを一意に識別するために<strong>Sessionidtime</strong>と組み合わせて使用されます。</span><span class="sxs-lookup"><span data-stu-id="c9ff5-124">Used in conjunction with <strong>SessionIdTime</strong> to uniquely identify a session.</span></span> <span data-ttu-id="c9ff5-125">詳細については、「 <a href="lync-server-2013-dialogs-table.md">Lync Server 2013 のダイアログテーブル</a>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c9ff5-125">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c9ff5-126"><strong>MediaId</strong></span><span class="sxs-lookup"><span data-stu-id="c9ff5-126"><strong>MediaId</strong></span></span></p></td>
<td><p><span data-ttu-id="c9ff5-127">tinyint</span><span class="sxs-lookup"><span data-stu-id="c9ff5-127">tinyint</span></span></p></td>
<td><p><span data-ttu-id="c9ff5-128">プライマリ、外部</span><span class="sxs-lookup"><span data-stu-id="c9ff5-128">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="c9ff5-129">このメディアの種類を識別する一意の番号です。</span><span class="sxs-lookup"><span data-stu-id="c9ff5-129">Unique number identifying this media type.</span></span> <span data-ttu-id="c9ff5-130">詳細については、「 <a href="lync-server-2013-medialist-table.md">Lync Server 2013 の Medialist の表</a>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c9ff5-130">See the <a href="lync-server-2013-medialist-table.md">MediaList table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c9ff5-131"><strong>StartTime</strong></span><span class="sxs-lookup"><span data-stu-id="c9ff5-131"><strong>StartTime</strong></span></span></p></td>
<td><p><span data-ttu-id="c9ff5-132">datetime</span><span class="sxs-lookup"><span data-stu-id="c9ff5-132">datetime</span></span></p></td>
<td><p><span data-ttu-id="c9ff5-133">Primary</span><span class="sxs-lookup"><span data-stu-id="c9ff5-133">Primary</span></span></p></td>
<td><p><span data-ttu-id="c9ff5-134">これは、実際のメディアの開始時刻ではなく、メディア要求が送信された時刻です。</span><span class="sxs-lookup"><span data-stu-id="c9ff5-134">This is the time that a media request was sent out, not the real media start time.</span></span> <span data-ttu-id="c9ff5-135"><strong>StartTime</strong>には、セッションのセットアップ時間が含まれます。</span><span class="sxs-lookup"><span data-stu-id="c9ff5-135"><strong>StartTime</strong> includes the session setup time.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c9ff5-136"><strong>EndTime</strong></span><span class="sxs-lookup"><span data-stu-id="c9ff5-136"><strong>EndTime</strong></span></span></p></td>
<td><p><span data-ttu-id="c9ff5-137">datetime</span><span class="sxs-lookup"><span data-stu-id="c9ff5-137">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="c9ff5-138">これはセッションの終了時刻です。</span><span class="sxs-lookup"><span data-stu-id="c9ff5-138">This is the end time of the session.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

