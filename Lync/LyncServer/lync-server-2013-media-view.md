---
title: 'Lync Server 2013: メディアビュー'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Media view
ms:assetid: 1a7b2e59-082e-4188-98ae-48ae9bd3494a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ687981(v=OCS.15)
ms:contentKeyID: 49733570
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b1ec4b80cc790068029a286a54d26a59a35fc125
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34827299"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="media-view-in-lync-server-2013"></a><span data-ttu-id="c7ac3-102">Lync Server 2013 でのメディアの表示</span><span class="sxs-lookup"><span data-stu-id="c7ac3-102">Media view in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c7ac3-103">_**最終更新日:** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="c7ac3-103">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="c7ac3-104">メディアビューには、ピアツーピアセッションで使用される1つのメディアの種類に関する情報が格納されます。</span><span class="sxs-lookup"><span data-stu-id="c7ac3-104">The Media view stores information about one media type used in a peer-to-peer session.</span></span> <span data-ttu-id="c7ac3-105">複数のメディアの種類を使用している場合は、1つのセッションがテーブル内の複数のレコードで表されます。</span><span class="sxs-lookup"><span data-stu-id="c7ac3-105">One session would be represented by multiple records in the table, if more than one media type is used.</span></span> <span data-ttu-id="c7ac3-106">このビューは、Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="c7ac3-106">This view was introduced in Microsoft Lync Server 2013.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="c7ac3-107">メディア表示は、セッションのメディア再生時間の計算に使用しないようにします。</span><span class="sxs-lookup"><span data-stu-id="c7ac3-107">The Media view should not be used to calculate the media duration for a session.</span></span> <span data-ttu-id="c7ac3-108">このビューには、セッションでのメディア交換の通知の詳細が含まれています。</span><span class="sxs-lookup"><span data-stu-id="c7ac3-108">This view contains the signaling details of media exchange in a session.</span></span> <span data-ttu-id="c7ac3-109">メディア交換は INVITE 要求によって実行され、StartTime は招待が送信された時間を示します。この招待時刻は、メディアの開始時刻を意味するわけではありません。これは、セッションが受け入れられた後にのみメディアが開始されるためです。</span><span class="sxs-lookup"><span data-stu-id="c7ac3-109">Media exchange is done by the INVITE request, and StartTime indicates the time that the INVITE was sent out. The invite time does not necessarily mean the media start time, because media starts only after the session is accepted.</span></span>



</div>

<span data-ttu-id="c7ac3-110">メディアビューには、 [Lync Server 2013 の Sessiondetails ビュー](lync-server-2013-sessiondetails-view.md)のすべての列に加えて、以下に示すものが含まれています。</span><span class="sxs-lookup"><span data-stu-id="c7ac3-110">The Media view contains all of the columns in the [SessionDetails view in Lync Server 2013](lync-server-2013-sessiondetails-view.md) in addition the ones listed below.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="c7ac3-111">列</span><span class="sxs-lookup"><span data-stu-id="c7ac3-111">Column</span></span></th>
<th><span data-ttu-id="c7ac3-112">データ型</span><span class="sxs-lookup"><span data-stu-id="c7ac3-112">Data Type</span></span></th>
<th><span data-ttu-id="c7ac3-113">詳細</span><span class="sxs-lookup"><span data-stu-id="c7ac3-113">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c7ac3-114"><strong>メディア</strong></span><span class="sxs-lookup"><span data-stu-id="c7ac3-114"><strong>Media</strong></span></span></p></td>
<td><p><span data-ttu-id="c7ac3-115">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="c7ac3-115">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="c7ac3-116">メディアの種類。</span><span class="sxs-lookup"><span data-stu-id="c7ac3-116">Media type.</span></span> <span data-ttu-id="c7ac3-117">詳細については、「 <a href="lync-server-2013-medialist-table.md">Lync Server 2013 の Medialist の表</a>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c7ac3-117">See the <a href="lync-server-2013-medialist-table.md">MediaList table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c7ac3-118"><strong>MediaStartTime</strong></span><span class="sxs-lookup"><span data-stu-id="c7ac3-118"><strong>MediaStartTime</strong></span></span></p></td>
<td><p><span data-ttu-id="c7ac3-119">datetime</span><span class="sxs-lookup"><span data-stu-id="c7ac3-119">datetime</span></span></p></td>
<td><p><span data-ttu-id="c7ac3-120">メディア要求が送信された時刻。</span><span class="sxs-lookup"><span data-stu-id="c7ac3-120">Time that a media request was sent out.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c7ac3-121"><strong>MediaEndTime</strong></span><span class="sxs-lookup"><span data-stu-id="c7ac3-121"><strong>MediaEndTime</strong></span></span></p></td>
<td><p><span data-ttu-id="c7ac3-122">datetime</span><span class="sxs-lookup"><span data-stu-id="c7ac3-122">datetime</span></span></p></td>
<td><p><span data-ttu-id="c7ac3-123">セッションの終了時刻。</span><span class="sxs-lookup"><span data-stu-id="c7ac3-123">End time of the session.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

