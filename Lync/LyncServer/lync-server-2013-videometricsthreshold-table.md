---
title: 'Lync Server 2013: VideoMetricsThreshold テーブル'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: VideoMetricsThreshold table
ms:assetid: 2e2f4711-35ba-48c6-b15b-5aba61c4eb75
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204778(v=OCS.15)
ms:contentKeyID: 48183736
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 93dc2fd539ccc24717939ccfa2ca93032fd9f25b
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41741987"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="videometricsthreshold-table-in-lync-server-2013"></a><span data-ttu-id="44c96-102">Lync Server 2013 の VideoMetricsThreshold テーブル</span><span class="sxs-lookup"><span data-stu-id="44c96-102">VideoMetricsThreshold table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="44c96-103">_**最終更新日:** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="44c96-103">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="44c96-104">VideoMetricsThreshold テーブルには、ビデオ通話で使用されるエクスペリエンスメトリックの品質と受け入れ可能な値が含まれています。</span><span class="sxs-lookup"><span data-stu-id="44c96-104">The VideoMetricsThreshold table contains optimal and acceptable values for the Quality of Experience metrics used with video calls.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="44c96-105"><strong>列</strong></span><span class="sxs-lookup"><span data-stu-id="44c96-105"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="44c96-106"><strong>データ型</strong></span><span class="sxs-lookup"><span data-stu-id="44c96-106"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="44c96-107"><strong>キー/インデックス</strong></span><span class="sxs-lookup"><span data-stu-id="44c96-107"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="44c96-108"><strong>詳細</strong></span><span class="sxs-lookup"><span data-stu-id="44c96-108"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="44c96-109"><strong>CallType</strong></span><span class="sxs-lookup"><span data-stu-id="44c96-109"><strong>CallType</strong></span></span></p></td>
<td><p><span data-ttu-id="44c96-110">int</span><span class="sxs-lookup"><span data-stu-id="44c96-110">int</span></span></p></td>
<td><p><span data-ttu-id="44c96-111">Primary</span><span class="sxs-lookup"><span data-stu-id="44c96-111">Primary</span></span></p></td>
<td><p><span data-ttu-id="44c96-112">発信した通話の種類。</span><span class="sxs-lookup"><span data-stu-id="44c96-112">Type of call that was placed.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="44c96-113"><strong>VideoPostFECPLROptimal</strong></span><span class="sxs-lookup"><span data-stu-id="44c96-113"><strong>VideoPostFECPLROptimal</strong></span></span></p></td>
<td><p><span data-ttu-id="44c96-114">10進数 (5, 2)</span><span class="sxs-lookup"><span data-stu-id="44c96-114">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="44c96-115">既定値は0.05 です。</span><span class="sxs-lookup"><span data-stu-id="44c96-115">The default value is 0.05.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="44c96-116"><strong>VideoPostFECPLRAcceptable</strong></span><span class="sxs-lookup"><span data-stu-id="44c96-116"><strong>VideoPostFECPLRAcceptable</strong></span></span></p></td>
<td><p><span data-ttu-id="44c96-117">10進数 (5, 2)</span><span class="sxs-lookup"><span data-stu-id="44c96-117">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="44c96-118">既定値は0.10 です。</span><span class="sxs-lookup"><span data-stu-id="44c96-118">The default value is 0.10.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="44c96-119"><strong>VideoLocalFrameLostPercentageAverageOptimal</strong></span><span class="sxs-lookup"><span data-stu-id="44c96-119"><strong>VideoLocalFrameLostPercentageAverageOptimal</strong></span></span></p></td>
<td><p><span data-ttu-id="44c96-120">10進数 (5, 2)</span><span class="sxs-lookup"><span data-stu-id="44c96-120">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="44c96-121">既定値は5.0 です。</span><span class="sxs-lookup"><span data-stu-id="44c96-121">The default value is 5.0.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="44c96-122"><strong>VideoLocalFrameLostPercentageAverageAcceptable</strong></span><span class="sxs-lookup"><span data-stu-id="44c96-122"><strong>VideoLocalFrameLostPercentageAverageAcceptable</strong></span></span></p></td>
<td><p><span data-ttu-id="44c96-123">10進数 (5, 2)</span><span class="sxs-lookup"><span data-stu-id="44c96-123">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="44c96-124">既定値は10.0 です。</span><span class="sxs-lookup"><span data-stu-id="44c96-124">The default value is 10.0.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="44c96-125"><strong>RecvFrameRateAverageOptimal</strong></span><span class="sxs-lookup"><span data-stu-id="44c96-125"><strong>RecvFrameRateAverageOptimal</strong></span></span></p></td>
<td><p><span data-ttu-id="44c96-126">10進数 (9, 4)</span><span class="sxs-lookup"><span data-stu-id="44c96-126">decimal(9,4)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="44c96-127">既定値は12.0000 です。</span><span class="sxs-lookup"><span data-stu-id="44c96-127">The default value is 12.0000.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="44c96-128"><strong>RecvFramerateAverageAcceptable</strong></span><span class="sxs-lookup"><span data-stu-id="44c96-128"><strong>RecvFramerateAverageAcceptable</strong></span></span></p></td>
<td><p><span data-ttu-id="44c96-129">10進数 (9, 4)</span><span class="sxs-lookup"><span data-stu-id="44c96-129">decimal(9,4)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="44c96-130">既定値は7.0000 です。</span><span class="sxs-lookup"><span data-stu-id="44c96-130">The default value is 7.0000.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="44c96-131"><strong>LowFrameRateCallPercentOptimal</strong></span><span class="sxs-lookup"><span data-stu-id="44c96-131"><strong>LowFrameRateCallPercentOptimal</strong></span></span></p></td>
<td><p><span data-ttu-id="44c96-132">10進数 (5, 2)</span><span class="sxs-lookup"><span data-stu-id="44c96-132">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="44c96-133">既定値は5.0 です。</span><span class="sxs-lookup"><span data-stu-id="44c96-133">The default value is 5.0.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="44c96-134"><strong>LowFrameRateCallPercentAcceptable</strong></span><span class="sxs-lookup"><span data-stu-id="44c96-134"><strong>LowFrameRateCallPercentAcceptable</strong></span></span></p></td>
<td><p><span data-ttu-id="44c96-135">10進数 (5, 2)</span><span class="sxs-lookup"><span data-stu-id="44c96-135">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="44c96-136">既定値は 10.0/</span><span class="sxs-lookup"><span data-stu-id="44c96-136">The default value is 10.0/</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="44c96-137"><strong>LowResolutionCallPercentOptimal</strong></span><span class="sxs-lookup"><span data-stu-id="44c96-137"><strong>LowResolutionCallPercentOptimal</strong></span></span></p></td>
<td><p><span data-ttu-id="44c96-138">10進数 (5, 2)</span><span class="sxs-lookup"><span data-stu-id="44c96-138">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="44c96-139">既定値は5.0 です。</span><span class="sxs-lookup"><span data-stu-id="44c96-139">The default value is 5.0.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="44c96-140"><strong>LowResolutionCallPercentAcceptable</strong></span><span class="sxs-lookup"><span data-stu-id="44c96-140"><strong>LowResolutionCallPercentAcceptable</strong></span></span></p></td>
<td><p><span data-ttu-id="44c96-141">10進数 (5, 2)</span><span class="sxs-lookup"><span data-stu-id="44c96-141">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="44c96-142">既定値は10.0 です。</span><span class="sxs-lookup"><span data-stu-id="44c96-142">The default value is 10.0.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="44c96-143"><strong>VideoPacketLossRateOptimal</strong></span><span class="sxs-lookup"><span data-stu-id="44c96-143"><strong>VideoPacketLossRateOptimal</strong></span></span></p></td>
<td><p><span data-ttu-id="44c96-144">@</span><span class="sxs-lookup"><span data-stu-id="44c96-144">foat</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="44c96-145">既定値は0.05 です。</span><span class="sxs-lookup"><span data-stu-id="44c96-145">The default value is 0.05.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="44c96-146"><strong>VideoPacketLossRateAcceptable</strong></span><span class="sxs-lookup"><span data-stu-id="44c96-146"><strong>VideoPacketLossRateAcceptable</strong></span></span></p></td>
<td><p><span data-ttu-id="44c96-147">float</span><span class="sxs-lookup"><span data-stu-id="44c96-147">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="44c96-148">既定値は0.10 です。</span><span class="sxs-lookup"><span data-stu-id="44c96-148">The default value is 0.10.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="44c96-149"><strong>VideoFrameRateAvgOptimal</strong></span><span class="sxs-lookup"><span data-stu-id="44c96-149"><strong>VideoFrameRateAvgOptimal</strong></span></span></p></td>
<td><p><span data-ttu-id="44c96-150">float</span><span class="sxs-lookup"><span data-stu-id="44c96-150">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="44c96-151">既定値は12です。</span><span class="sxs-lookup"><span data-stu-id="44c96-151">The default value is 12.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="44c96-152"><strong>VideoFrameRateAvgAcceptable</strong></span><span class="sxs-lookup"><span data-stu-id="44c96-152"><strong>VideoFrameRateAvgAcceptable</strong></span></span></p></td>
<td><p><span data-ttu-id="44c96-153">float</span><span class="sxs-lookup"><span data-stu-id="44c96-153">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="44c96-154">既定値は7です。</span><span class="sxs-lookup"><span data-stu-id="44c96-154">The default value is 7.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="44c96-155"><strong>DynamicCapabilityPercentOptimal</strong></span><span class="sxs-lookup"><span data-stu-id="44c96-155"><strong>DynamicCapabilityPercentOptimal</strong></span></span></p></td>
<td><p><span data-ttu-id="44c96-156">10進数 (5, 2)</span><span class="sxs-lookup"><span data-stu-id="44c96-156">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="44c96-157">既定値は5.00 です。</span><span class="sxs-lookup"><span data-stu-id="44c96-157">The default value is 5.00.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="44c96-158"><strong>DynamicCapabilityPercentAcceptable</strong></span><span class="sxs-lookup"><span data-stu-id="44c96-158"><strong>DynamicCapabilityPercentAcceptable</strong></span></span></p></td>
<td><p><span data-ttu-id="44c96-159">10進数 (5, 2)</span><span class="sxs-lookup"><span data-stu-id="44c96-159">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="44c96-160">既定値は10.00 です。</span><span class="sxs-lookup"><span data-stu-id="44c96-160">The default value is 10.00.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

