---
title: 'Lync Server 2013: TraceRoute テーブル'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: TraceRoute table
ms:assetid: b9493cef-6ece-4f13-bf68-dbf132aab4f4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205205(v=OCS.15)
ms:contentKeyID: 48185242
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f1dd0f9bc3bd900d71a316bf2ff1ab7612a51194
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34848392"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="traceroute-table-in-lync-server-2013"></a><span data-ttu-id="8ecc1-102">Lync Server 2013 の TraceRoute テーブル</span><span class="sxs-lookup"><span data-stu-id="8ecc1-102">TraceRoute table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8ecc1-103">_**最終更新日:** 2014-02-21_</span><span class="sxs-lookup"><span data-stu-id="8ecc1-103">_**Topic Last Modified:** 2014-02-21_</span></span>

<span data-ttu-id="8ecc1-104">TraceRoute テーブルには、通話のルーティング情報が含まれています。</span><span class="sxs-lookup"><span data-stu-id="8ecc1-104">The TraceRoute table contains routing information from calls.</span></span> <span data-ttu-id="8ecc1-105">この表は、Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="8ecc1-105">This table was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="8ecc1-106"><strong>列</strong></span><span class="sxs-lookup"><span data-stu-id="8ecc1-106"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="8ecc1-107"><strong>データ型</strong></span><span class="sxs-lookup"><span data-stu-id="8ecc1-107"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="8ecc1-108"><strong>キー/インデックス</strong></span><span class="sxs-lookup"><span data-stu-id="8ecc1-108"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="8ecc1-109"><strong>詳細</strong></span><span class="sxs-lookup"><span data-stu-id="8ecc1-109"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="8ecc1-110"><strong>ConferenceDateTime</strong></span><span class="sxs-lookup"><span data-stu-id="8ecc1-110"><strong>ConferenceDateTime</strong></span></span></p></td>
<td><p><span data-ttu-id="8ecc1-111">datetime</span><span class="sxs-lookup"><span data-stu-id="8ecc1-111">datetime</span></span></p></td>
<td><p><span data-ttu-id="8ecc1-112">プライマリ、外部</span><span class="sxs-lookup"><span data-stu-id="8ecc1-112">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="8ecc1-113">通話が開始された日付と時刻。</span><span class="sxs-lookup"><span data-stu-id="8ecc1-113">Date and time that the call began.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8ecc1-114"><strong>SessionSeq</strong></span><span class="sxs-lookup"><span data-stu-id="8ecc1-114"><strong>SessionSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="8ecc1-115">int</span><span class="sxs-lookup"><span data-stu-id="8ecc1-115">int</span></span></p></td>
<td><p><span data-ttu-id="8ecc1-116">プライマリ、外部</span><span class="sxs-lookup"><span data-stu-id="8ecc1-116">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="8ecc1-117">同じ日付と同時に開始された可能性がある複数の通話を区別するために使用される一意の識別子。</span><span class="sxs-lookup"><span data-stu-id="8ecc1-117">Unique identifier used to distinguish between multiple calls that might have begun on the same date and at the same time.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8ecc1-118"><strong>MediaLineLabel</strong></span><span class="sxs-lookup"><span data-stu-id="8ecc1-118"><strong>MediaLineLabel</strong></span></span></p></td>
<td><p><span data-ttu-id="8ecc1-119">tinyint</span><span class="sxs-lookup"><span data-stu-id="8ecc1-119">tinyint</span></span></p></td>
<td><p><span data-ttu-id="8ecc1-120">プライマリ、外部</span><span class="sxs-lookup"><span data-stu-id="8ecc1-120">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="8ecc1-121">通話で使用されるビデオラインの種類を表します。</span><span class="sxs-lookup"><span data-stu-id="8ecc1-121">Represents the type of video line used in the call.</span></span> <span data-ttu-id="8ecc1-122">有効な値は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="8ecc1-122">Allowed values are:</span></span></p>
<ul>
<li><p><span data-ttu-id="8ecc1-123">0–音声</span><span class="sxs-lookup"><span data-stu-id="8ecc1-123">0 – Audio</span></span></p></li>
<li><p><span data-ttu-id="8ecc1-124">1-ビデオ</span><span class="sxs-lookup"><span data-stu-id="8ecc1-124">1 – Video</span></span></p></li>
<li><p><span data-ttu-id="8ecc1-125">2-パノラマビデオ</span><span class="sxs-lookup"><span data-stu-id="8ecc1-125">2 – Panoramic video</span></span></p></li>
<li><p><span data-ttu-id="8ecc1-126">3-アプリケーション/デスクトップ共有</span><span class="sxs-lookup"><span data-stu-id="8ecc1-126">3 – Application/Desktop sharing</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8ecc1-127"><strong>FromCaller</strong></span><span class="sxs-lookup"><span data-stu-id="8ecc1-127"><strong>FromCaller</strong></span></span></p></td>
<td><p><span data-ttu-id="8ecc1-128">bit</span><span class="sxs-lookup"><span data-stu-id="8ecc1-128">bit</span></span></p></td>
<td><p><span data-ttu-id="8ecc1-129">Primary</span><span class="sxs-lookup"><span data-stu-id="8ecc1-129">Primary</span></span></p></td>
<td><p><span data-ttu-id="8ecc1-130">通話を発信したエンドポイント。</span><span class="sxs-lookup"><span data-stu-id="8ecc1-130">Endpoint that placed the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8ecc1-131"><strong>ホップ</strong></span><span class="sxs-lookup"><span data-stu-id="8ecc1-131"><strong>Hop</strong></span></span></p></td>
<td><p><span data-ttu-id="8ecc1-132">int</span><span class="sxs-lookup"><span data-stu-id="8ecc1-132">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="8ecc1-133">ネットワークホップ/</span><span class="sxs-lookup"><span data-stu-id="8ecc1-133">Network hop/</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8ecc1-134"><strong>IPAddressKey</strong></span><span class="sxs-lookup"><span data-stu-id="8ecc1-134"><strong>IPAddressKey</strong></span></span></p></td>
<td><p><span data-ttu-id="8ecc1-135">int</span><span class="sxs-lookup"><span data-stu-id="8ecc1-135">int</span></span></p></td>
<td><p><span data-ttu-id="8ecc1-136">外部</span><span class="sxs-lookup"><span data-stu-id="8ecc1-136">Foreign</span></span></p></td>
<td><p><span data-ttu-id="8ecc1-137">IP アドレスの一意の識別子。</span><span class="sxs-lookup"><span data-stu-id="8ecc1-137">Unique identifier for the IP address.</span></span> <span data-ttu-id="8ecc1-138">IP アドレス情報は、 <a href="lync-server-2013-ipaddress-table.md">Lync Server 2013 の IPAddress テーブル</a>に格納されます。</span><span class="sxs-lookup"><span data-stu-id="8ecc1-138">IP address information is stored in the <a href="lync-server-2013-ipaddress-table.md">IPAddress table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8ecc1-139"><strong>RTT</strong></span><span class="sxs-lookup"><span data-stu-id="8ecc1-139"><strong>RTT</strong></span></span></p></td>
<td><p><span data-ttu-id="8ecc1-140">int</span><span class="sxs-lookup"><span data-stu-id="8ecc1-140">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="8ecc1-141">往復時間。</span><span class="sxs-lookup"><span data-stu-id="8ecc1-141">Roundtrip time.</span></span> <span data-ttu-id="8ecc1-142">往復時間は、ボイスパケットがその宛先に到達し、受信した通知を返信するのにかかる時間を測定します。</span><span class="sxs-lookup"><span data-stu-id="8ecc1-142">The roundtrip time measures the amount of time it takes for a voice packet to reach its destination and then send back notification that it was received.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

