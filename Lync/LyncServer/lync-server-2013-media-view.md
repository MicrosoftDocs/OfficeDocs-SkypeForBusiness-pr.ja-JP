---
title: 'Lync Server 2013: メディアビュー'
description: 'Lync Server 2013: メディアビュー。'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Media view
ms:assetid: 1a7b2e59-082e-4188-98ae-48ae9bd3494a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ687981(v=OCS.15)
ms:contentKeyID: 49733570
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 74643986b12a30b1055a46a37febf90eeb70c514
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48558013"
---
# <a name="media-view-in-lync-server-2013"></a><span data-ttu-id="53696-103">Lync Server 2013 のメディア表示</span><span class="sxs-lookup"><span data-stu-id="53696-103">Media view in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="53696-104">_**トピックの最終更新日:** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="53696-104">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="53696-105">Media ビューには、ピアツーピア セッションで使用される 1 つのメディア種類に関する情報が格納されます。</span><span class="sxs-lookup"><span data-stu-id="53696-105">The Media view stores information about one media type used in a peer-to-peer session.</span></span> <span data-ttu-id="53696-106">複数のメディア種類が使用されている場合、1 つのセッションがテーブルでは複数のレコードによって表されます。</span><span class="sxs-lookup"><span data-stu-id="53696-106">One session would be represented by multiple records in the table, if more than one media type is used.</span></span> <span data-ttu-id="53696-107">このビューは Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="53696-107">This view was introduced in Microsoft Lync Server 2013.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="53696-p102">Media ビューを使用してセッションでのメディアの継続時間を計算することはできません。このビューには、セッションでのメディア交換の信号の詳細が格納されます。メディア交換は INVITE 要求によって行われ、StartTime は INVITE が送信された時刻を示します。メディアはセッションが受け付けられた後にのみ開始するので、招待時間は必ずしもメディアの開始時刻を意味しません。</span><span class="sxs-lookup"><span data-stu-id="53696-p102">The Media view should not be used to calculate the media duration for a session. This view contains the signaling details of media exchange in a session. Media exchange is done by the INVITE request, and StartTime indicates the time that the INVITE was sent out. The invite time does not necessarily mean the media start time, because media starts only after the session is accepted.</span></span>



</div>

<span data-ttu-id="53696-111">Media ビューには、 [Lync Server 2013 の Sessiondetails ビュー](lync-server-2013-sessiondetails-view.md) のすべての列に加えて、次に示すものが含まれています。</span><span class="sxs-lookup"><span data-stu-id="53696-111">The Media view contains all of the columns in the [SessionDetails view in Lync Server 2013](lync-server-2013-sessiondetails-view.md) in addition the ones listed below.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="53696-112">Column</span><span class="sxs-lookup"><span data-stu-id="53696-112">Column</span></span></th>
<th><span data-ttu-id="53696-113">データ型</span><span class="sxs-lookup"><span data-stu-id="53696-113">Data Type</span></span></th>
<th><span data-ttu-id="53696-114">詳細</span><span class="sxs-lookup"><span data-stu-id="53696-114">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="53696-115"><strong>Media</strong></span><span class="sxs-lookup"><span data-stu-id="53696-115"><strong>Media</strong></span></span></p></td>
<td><p><span data-ttu-id="53696-116">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="53696-116">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="53696-117">メディア種類。</span><span class="sxs-lookup"><span data-stu-id="53696-117">Media type.</span></span> <span data-ttu-id="53696-118">詳細については、「 <a href="lync-server-2013-medialist-table.md">Lync Server 2013 の Medialist table</a> 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="53696-118">See the <a href="lync-server-2013-medialist-table.md">MediaList table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="53696-119"><strong>MediaStartTime</strong></span><span class="sxs-lookup"><span data-stu-id="53696-119"><strong>MediaStartTime</strong></span></span></p></td>
<td><p><span data-ttu-id="53696-120">日付型</span><span class="sxs-lookup"><span data-stu-id="53696-120">datetime</span></span></p></td>
<td><p><span data-ttu-id="53696-121">メディア要求が送信された時刻。</span><span class="sxs-lookup"><span data-stu-id="53696-121">Time that a media request was sent out.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="53696-122"><strong>MediaEndTime</strong></span><span class="sxs-lookup"><span data-stu-id="53696-122"><strong>MediaEndTime</strong></span></span></p></td>
<td><p><span data-ttu-id="53696-123">日付型</span><span class="sxs-lookup"><span data-stu-id="53696-123">datetime</span></span></p></td>
<td><p><span data-ttu-id="53696-124">セッションの終了時刻。</span><span class="sxs-lookup"><span data-stu-id="53696-124">End time of the session.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

