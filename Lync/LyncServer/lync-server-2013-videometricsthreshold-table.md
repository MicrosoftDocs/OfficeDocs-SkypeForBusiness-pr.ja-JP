---
title: 'Lync Server 2013: VideoMetricsThreshold テーブル'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: VideoMetricsThreshold table
ms:assetid: 2e2f4711-35ba-48c6-b15b-5aba61c4eb75
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204778(v=OCS.15)
ms:contentKeyID: 48183736
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7c15910f6478f3df12bf906f04aee82c89a822de
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34848224"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="videometricsthreshold-table-in-lync-server-2013"></a><span data-ttu-id="a83d3-102">Lync Server 2013 の VideoMetricsThreshold テーブル</span><span class="sxs-lookup"><span data-stu-id="a83d3-102">VideoMetricsThreshold table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a83d3-103">_**最終更新日:** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="a83d3-103">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="a83d3-104">VideoMetricsThreshold テーブルには、ビデオ通話で使用されるエクスペリエンスメトリックの品質と受け入れ可能な値が含まれています。</span><span class="sxs-lookup"><span data-stu-id="a83d3-104">The VideoMetricsThreshold table contains optimal and acceptable values for the Quality of Experience metrics used with video calls.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="a83d3-105"><strong>列</strong></span><span class="sxs-lookup"><span data-stu-id="a83d3-105"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="a83d3-106"><strong>データ型</strong></span><span class="sxs-lookup"><span data-stu-id="a83d3-106"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="a83d3-107"><strong>キー/インデックス</strong></span><span class="sxs-lookup"><span data-stu-id="a83d3-107"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="a83d3-108"><strong>詳細</strong></span><span class="sxs-lookup"><span data-stu-id="a83d3-108"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a83d3-109"><strong>CallType</strong></span><span class="sxs-lookup"><span data-stu-id="a83d3-109"><strong>CallType</strong></span></span></p></td>
<td><p><span data-ttu-id="a83d3-110">int</span><span class="sxs-lookup"><span data-stu-id="a83d3-110">int</span></span></p></td>
<td><p><span data-ttu-id="a83d3-111">Primary</span><span class="sxs-lookup"><span data-stu-id="a83d3-111">Primary</span></span></p></td>
<td><p><span data-ttu-id="a83d3-112">発信した通話の種類。</span><span class="sxs-lookup"><span data-stu-id="a83d3-112">Type of call that was placed.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a83d3-113"><strong>VideoPostFECPLROptimal</strong></span><span class="sxs-lookup"><span data-stu-id="a83d3-113"><strong>VideoPostFECPLROptimal</strong></span></span></p></td>
<td><p><span data-ttu-id="a83d3-114">10進数 (5, 2)</span><span class="sxs-lookup"><span data-stu-id="a83d3-114">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="a83d3-115">既定値は0.05 です。</span><span class="sxs-lookup"><span data-stu-id="a83d3-115">The default value is 0.05.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a83d3-116"><strong>VideoPostFECPLRAcceptable</strong></span><span class="sxs-lookup"><span data-stu-id="a83d3-116"><strong>VideoPostFECPLRAcceptable</strong></span></span></p></td>
<td><p><span data-ttu-id="a83d3-117">10進数 (5, 2)</span><span class="sxs-lookup"><span data-stu-id="a83d3-117">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="a83d3-118">既定値は0.10 です。</span><span class="sxs-lookup"><span data-stu-id="a83d3-118">The default value is 0.10.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a83d3-119"><strong>VideoLocalFrameLostPercentageAverageOptimal</strong></span><span class="sxs-lookup"><span data-stu-id="a83d3-119"><strong>VideoLocalFrameLostPercentageAverageOptimal</strong></span></span></p></td>
<td><p><span data-ttu-id="a83d3-120">10進数 (5, 2)</span><span class="sxs-lookup"><span data-stu-id="a83d3-120">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="a83d3-121">既定値は5.0 です。</span><span class="sxs-lookup"><span data-stu-id="a83d3-121">The default value is 5.0.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a83d3-122"><strong>VideoLocalFrameLostPercentageAverageAcceptable</strong></span><span class="sxs-lookup"><span data-stu-id="a83d3-122"><strong>VideoLocalFrameLostPercentageAverageAcceptable</strong></span></span></p></td>
<td><p><span data-ttu-id="a83d3-123">10進数 (5, 2)</span><span class="sxs-lookup"><span data-stu-id="a83d3-123">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="a83d3-124">既定値は10.0 です。</span><span class="sxs-lookup"><span data-stu-id="a83d3-124">The default value is 10.0.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a83d3-125"><strong>RecvFrameRateAverageOptimal</strong></span><span class="sxs-lookup"><span data-stu-id="a83d3-125"><strong>RecvFrameRateAverageOptimal</strong></span></span></p></td>
<td><p><span data-ttu-id="a83d3-126">10進数 (9, 4)</span><span class="sxs-lookup"><span data-stu-id="a83d3-126">decimal(9,4)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="a83d3-127">既定値は12.0000 です。</span><span class="sxs-lookup"><span data-stu-id="a83d3-127">The default value is 12.0000.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a83d3-128"><strong>RecvFramerateAverageAcceptable</strong></span><span class="sxs-lookup"><span data-stu-id="a83d3-128"><strong>RecvFramerateAverageAcceptable</strong></span></span></p></td>
<td><p><span data-ttu-id="a83d3-129">10進数 (9, 4)</span><span class="sxs-lookup"><span data-stu-id="a83d3-129">decimal(9,4)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="a83d3-130">既定値は7.0000 です。</span><span class="sxs-lookup"><span data-stu-id="a83d3-130">The default value is 7.0000.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a83d3-131"><strong>LowFrameRateCallPercentOptimal</strong></span><span class="sxs-lookup"><span data-stu-id="a83d3-131"><strong>LowFrameRateCallPercentOptimal</strong></span></span></p></td>
<td><p><span data-ttu-id="a83d3-132">10進数 (5, 2)</span><span class="sxs-lookup"><span data-stu-id="a83d3-132">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="a83d3-133">既定値は5.0 です。</span><span class="sxs-lookup"><span data-stu-id="a83d3-133">The default value is 5.0.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a83d3-134"><strong>LowFrameRateCallPercentAcceptable</strong></span><span class="sxs-lookup"><span data-stu-id="a83d3-134"><strong>LowFrameRateCallPercentAcceptable</strong></span></span></p></td>
<td><p><span data-ttu-id="a83d3-135">10進数 (5, 2)</span><span class="sxs-lookup"><span data-stu-id="a83d3-135">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="a83d3-136">既定値は 10.0/</span><span class="sxs-lookup"><span data-stu-id="a83d3-136">The default value is 10.0/</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a83d3-137"><strong>LowResolutionCallPercentOptimal</strong></span><span class="sxs-lookup"><span data-stu-id="a83d3-137"><strong>LowResolutionCallPercentOptimal</strong></span></span></p></td>
<td><p><span data-ttu-id="a83d3-138">10進数 (5, 2)</span><span class="sxs-lookup"><span data-stu-id="a83d3-138">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="a83d3-139">既定値は5.0 です。</span><span class="sxs-lookup"><span data-stu-id="a83d3-139">The default value is 5.0.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a83d3-140"><strong>LowResolutionCallPercentAcceptable</strong></span><span class="sxs-lookup"><span data-stu-id="a83d3-140"><strong>LowResolutionCallPercentAcceptable</strong></span></span></p></td>
<td><p><span data-ttu-id="a83d3-141">10進数 (5, 2)</span><span class="sxs-lookup"><span data-stu-id="a83d3-141">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="a83d3-142">既定値は10.0 です。</span><span class="sxs-lookup"><span data-stu-id="a83d3-142">The default value is 10.0.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a83d3-143"><strong>VideoPacketLossRateOptimal</strong></span><span class="sxs-lookup"><span data-stu-id="a83d3-143"><strong>VideoPacketLossRateOptimal</strong></span></span></p></td>
<td><p><span data-ttu-id="a83d3-144">@</span><span class="sxs-lookup"><span data-stu-id="a83d3-144">foat</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="a83d3-145">既定値は0.05 です。</span><span class="sxs-lookup"><span data-stu-id="a83d3-145">The default value is 0.05.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a83d3-146"><strong>VideoPacketLossRateAcceptable</strong></span><span class="sxs-lookup"><span data-stu-id="a83d3-146"><strong>VideoPacketLossRateAcceptable</strong></span></span></p></td>
<td><p><span data-ttu-id="a83d3-147">float</span><span class="sxs-lookup"><span data-stu-id="a83d3-147">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="a83d3-148">既定値は0.10 です。</span><span class="sxs-lookup"><span data-stu-id="a83d3-148">The default value is 0.10.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a83d3-149"><strong>VideoFrameRateAvgOptimal</strong></span><span class="sxs-lookup"><span data-stu-id="a83d3-149"><strong>VideoFrameRateAvgOptimal</strong></span></span></p></td>
<td><p><span data-ttu-id="a83d3-150">float</span><span class="sxs-lookup"><span data-stu-id="a83d3-150">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="a83d3-151">既定値は12です。</span><span class="sxs-lookup"><span data-stu-id="a83d3-151">The default value is 12.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a83d3-152"><strong>VideoFrameRateAvgAcceptable</strong></span><span class="sxs-lookup"><span data-stu-id="a83d3-152"><strong>VideoFrameRateAvgAcceptable</strong></span></span></p></td>
<td><p><span data-ttu-id="a83d3-153">float</span><span class="sxs-lookup"><span data-stu-id="a83d3-153">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="a83d3-154">既定値は7です。</span><span class="sxs-lookup"><span data-stu-id="a83d3-154">The default value is 7.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a83d3-155"><strong>DynamicCapabilityPercentOptimal</strong></span><span class="sxs-lookup"><span data-stu-id="a83d3-155"><strong>DynamicCapabilityPercentOptimal</strong></span></span></p></td>
<td><p><span data-ttu-id="a83d3-156">10進数 (5, 2)</span><span class="sxs-lookup"><span data-stu-id="a83d3-156">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="a83d3-157">既定値は5.00 です。</span><span class="sxs-lookup"><span data-stu-id="a83d3-157">The default value is 5.00.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a83d3-158"><strong>DynamicCapabilityPercentAcceptable</strong></span><span class="sxs-lookup"><span data-stu-id="a83d3-158"><strong>DynamicCapabilityPercentAcceptable</strong></span></span></p></td>
<td><p><span data-ttu-id="a83d3-159">10進数 (5, 2)</span><span class="sxs-lookup"><span data-stu-id="a83d3-159">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="a83d3-160">既定値は10.00 です。</span><span class="sxs-lookup"><span data-stu-id="a83d3-160">The default value is 10.00.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

