---
title: 'Lync Server 2013: メディアビュー'
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
ms.openlocfilehash: d0e6cd8658278a8d7798153698355f5a73f2952b
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/16/2020
ms.locfileid: "48516154"
---
# <a name="media-view-in-lync-server-2013"></a><span data-ttu-id="0452c-102">Lync Server 2013 のメディア表示</span><span class="sxs-lookup"><span data-stu-id="0452c-102">Media view in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0452c-103">_**トピックの最終更新日:** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="0452c-103">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="0452c-104">Media ビューには、ピアツーピア セッションで使用される 1 つのメディア種類に関する情報が格納されます。</span><span class="sxs-lookup"><span data-stu-id="0452c-104">The Media view stores information about one media type used in a peer-to-peer session.</span></span> <span data-ttu-id="0452c-105">複数のメディア種類が使用されている場合、1 つのセッションがテーブルでは複数のレコードによって表されます。</span><span class="sxs-lookup"><span data-stu-id="0452c-105">One session would be represented by multiple records in the table, if more than one media type is used.</span></span> <span data-ttu-id="0452c-106">このビューは Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="0452c-106">This view was introduced in Microsoft Lync Server 2013.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="0452c-p102">Media ビューを使用してセッションでのメディアの継続時間を計算することはできません。このビューには、セッションでのメディア交換の信号の詳細が格納されます。メディア交換は INVITE 要求によって行われ、StartTime は INVITE が送信された時刻を示します。メディアはセッションが受け付けられた後にのみ開始するので、招待時間は必ずしもメディアの開始時刻を意味しません。</span><span class="sxs-lookup"><span data-stu-id="0452c-p102">The Media view should not be used to calculate the media duration for a session. This view contains the signaling details of media exchange in a session. Media exchange is done by the INVITE request, and StartTime indicates the time that the INVITE was sent out. The invite time does not necessarily mean the media start time, because media starts only after the session is accepted.</span></span>



</div>

<span data-ttu-id="0452c-110">Media ビューには、 [Lync Server 2013 の Sessiondetails ビュー](lync-server-2013-sessiondetails-view.md) のすべての列に加えて、次に示すものが含まれています。</span><span class="sxs-lookup"><span data-stu-id="0452c-110">The Media view contains all of the columns in the [SessionDetails view in Lync Server 2013](lync-server-2013-sessiondetails-view.md) in addition the ones listed below.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="0452c-111">Column</span><span class="sxs-lookup"><span data-stu-id="0452c-111">Column</span></span></th>
<th><span data-ttu-id="0452c-112">データ型</span><span class="sxs-lookup"><span data-stu-id="0452c-112">Data Type</span></span></th>
<th><span data-ttu-id="0452c-113">詳細</span><span class="sxs-lookup"><span data-stu-id="0452c-113">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="0452c-114"><strong>Media</strong></span><span class="sxs-lookup"><span data-stu-id="0452c-114"><strong>Media</strong></span></span></p></td>
<td><p><span data-ttu-id="0452c-115">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="0452c-115">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="0452c-116">メディア種類。</span><span class="sxs-lookup"><span data-stu-id="0452c-116">Media type.</span></span> <span data-ttu-id="0452c-117">詳細については、「 <a href="lync-server-2013-medialist-table.md">Lync Server 2013 の Medialist table</a> 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0452c-117">See the <a href="lync-server-2013-medialist-table.md">MediaList table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0452c-118"><strong>MediaStartTime</strong></span><span class="sxs-lookup"><span data-stu-id="0452c-118"><strong>MediaStartTime</strong></span></span></p></td>
<td><p><span data-ttu-id="0452c-119">日付型</span><span class="sxs-lookup"><span data-stu-id="0452c-119">datetime</span></span></p></td>
<td><p><span data-ttu-id="0452c-120">メディア要求が送信された時刻。</span><span class="sxs-lookup"><span data-stu-id="0452c-120">Time that a media request was sent out.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0452c-121"><strong>MediaEndTime</strong></span><span class="sxs-lookup"><span data-stu-id="0452c-121"><strong>MediaEndTime</strong></span></span></p></td>
<td><p><span data-ttu-id="0452c-122">日付型</span><span class="sxs-lookup"><span data-stu-id="0452c-122">datetime</span></span></p></td>
<td><p><span data-ttu-id="0452c-123">セッションの終了時刻。</span><span class="sxs-lookup"><span data-stu-id="0452c-123">End time of the session.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

