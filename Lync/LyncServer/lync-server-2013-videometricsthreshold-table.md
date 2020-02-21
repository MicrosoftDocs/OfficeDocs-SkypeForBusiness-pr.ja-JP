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
ms.openlocfilehash: 58a054ba58ff7e1e839b0aeca88d0e61164e30b2
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/21/2020
ms.locfileid: "42211650"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="videometricsthreshold-table-in-lync-server-2013"></a><span data-ttu-id="7a727-102">Lync Server 2013 の VideoMetricsThreshold テーブル</span><span class="sxs-lookup"><span data-stu-id="7a727-102">VideoMetricsThreshold table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7a727-103">_**トピックの最終更新日:** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="7a727-103">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="7a727-104">VideoMetricsThreshold テーブルには、ビデオ通話で使用される QoE 指標の最適な値および許容可能な値が含まれています。</span><span class="sxs-lookup"><span data-stu-id="7a727-104">The VideoMetricsThreshold table contains optimal and acceptable values for the Quality of Experience metrics used with video calls.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="7a727-105"><strong>列</strong></span><span class="sxs-lookup"><span data-stu-id="7a727-105"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="7a727-106"><strong>データ型</strong></span><span class="sxs-lookup"><span data-stu-id="7a727-106"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="7a727-107"><strong>キー/インデックス</strong></span><span class="sxs-lookup"><span data-stu-id="7a727-107"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="7a727-108"><strong>詳細</strong></span><span class="sxs-lookup"><span data-stu-id="7a727-108"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="7a727-109"><strong>CallType</strong></span><span class="sxs-lookup"><span data-stu-id="7a727-109"><strong>CallType</strong></span></span></p></td>
<td><p><span data-ttu-id="7a727-110">int</span><span class="sxs-lookup"><span data-stu-id="7a727-110">int</span></span></p></td>
<td><p><span data-ttu-id="7a727-111">Primary</span><span class="sxs-lookup"><span data-stu-id="7a727-111">Primary</span></span></p></td>
<td><p><span data-ttu-id="7a727-112">発信された通話の種類</span><span class="sxs-lookup"><span data-stu-id="7a727-112">Type of call that was placed.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7a727-113"><strong>VideoPostFECPLROptimal</strong></span><span class="sxs-lookup"><span data-stu-id="7a727-113"><strong>VideoPostFECPLROptimal</strong></span></span></p></td>
<td><p><span data-ttu-id="7a727-114">10進数 (5、2)</span><span class="sxs-lookup"><span data-stu-id="7a727-114">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="7a727-115">既定値は 0.05 です。</span><span class="sxs-lookup"><span data-stu-id="7a727-115">The default value is 0.05.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7a727-116"><strong>VideoPostFECPLRAcceptable</strong></span><span class="sxs-lookup"><span data-stu-id="7a727-116"><strong>VideoPostFECPLRAcceptable</strong></span></span></p></td>
<td><p><span data-ttu-id="7a727-117">10進数 (5、2)</span><span class="sxs-lookup"><span data-stu-id="7a727-117">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="7a727-118">既定値は 0.10 です。</span><span class="sxs-lookup"><span data-stu-id="7a727-118">The default value is 0.10.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7a727-119"><strong>VideoLocalFrameLostPercentageAverageOptimal</strong></span><span class="sxs-lookup"><span data-stu-id="7a727-119"><strong>VideoLocalFrameLostPercentageAverageOptimal</strong></span></span></p></td>
<td><p><span data-ttu-id="7a727-120">10進数 (5、2)</span><span class="sxs-lookup"><span data-stu-id="7a727-120">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="7a727-121">既定値は 5.0 です。</span><span class="sxs-lookup"><span data-stu-id="7a727-121">The default value is 5.0.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7a727-122"><strong>VideoLocalFrameLostPercentageAverageAcceptable</strong></span><span class="sxs-lookup"><span data-stu-id="7a727-122"><strong>VideoLocalFrameLostPercentageAverageAcceptable</strong></span></span></p></td>
<td><p><span data-ttu-id="7a727-123">10進数 (5、2)</span><span class="sxs-lookup"><span data-stu-id="7a727-123">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="7a727-124">既定値は 10.0 です。</span><span class="sxs-lookup"><span data-stu-id="7a727-124">The default value is 10.0.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7a727-125"><strong>RecvFrameRateAverageOptimal</strong></span><span class="sxs-lookup"><span data-stu-id="7a727-125"><strong>RecvFrameRateAverageOptimal</strong></span></span></p></td>
<td><p><span data-ttu-id="7a727-126">10進数 (9、4)</span><span class="sxs-lookup"><span data-stu-id="7a727-126">decimal(9,4)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="7a727-127">既定値は 12.0000 です。</span><span class="sxs-lookup"><span data-stu-id="7a727-127">The default value is 12.0000.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7a727-128"><strong>RecvFramerateAverageAcceptable</strong></span><span class="sxs-lookup"><span data-stu-id="7a727-128"><strong>RecvFramerateAverageAcceptable</strong></span></span></p></td>
<td><p><span data-ttu-id="7a727-129">10進数 (9、4)</span><span class="sxs-lookup"><span data-stu-id="7a727-129">decimal(9,4)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="7a727-130">既定値は 7.0000 です。</span><span class="sxs-lookup"><span data-stu-id="7a727-130">The default value is 7.0000.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7a727-131"><strong>LowFrameRateCallPercentOptimal</strong></span><span class="sxs-lookup"><span data-stu-id="7a727-131"><strong>LowFrameRateCallPercentOptimal</strong></span></span></p></td>
<td><p><span data-ttu-id="7a727-132">10進数 (5、2)</span><span class="sxs-lookup"><span data-stu-id="7a727-132">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="7a727-133">既定値は 5.0 です。</span><span class="sxs-lookup"><span data-stu-id="7a727-133">The default value is 5.0.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7a727-134"><strong>LowFrameRateCallPercentAcceptable</strong></span><span class="sxs-lookup"><span data-stu-id="7a727-134"><strong>LowFrameRateCallPercentAcceptable</strong></span></span></p></td>
<td><p><span data-ttu-id="7a727-135">10進数 (5、2)</span><span class="sxs-lookup"><span data-stu-id="7a727-135">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="7a727-136">既定値は 10.0 です。</span><span class="sxs-lookup"><span data-stu-id="7a727-136">The default value is 10.0/</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7a727-137"><strong>LowResolutionCallPercentOptimal</strong></span><span class="sxs-lookup"><span data-stu-id="7a727-137"><strong>LowResolutionCallPercentOptimal</strong></span></span></p></td>
<td><p><span data-ttu-id="7a727-138">10進数 (5、2)</span><span class="sxs-lookup"><span data-stu-id="7a727-138">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="7a727-139">既定値は 5.0 です。</span><span class="sxs-lookup"><span data-stu-id="7a727-139">The default value is 5.0.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7a727-140"><strong>LowResolutionCallPercentAcceptable</strong></span><span class="sxs-lookup"><span data-stu-id="7a727-140"><strong>LowResolutionCallPercentAcceptable</strong></span></span></p></td>
<td><p><span data-ttu-id="7a727-141">10進数 (5、2)</span><span class="sxs-lookup"><span data-stu-id="7a727-141">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="7a727-142">既定値は 10.0 です。</span><span class="sxs-lookup"><span data-stu-id="7a727-142">The default value is 10.0.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7a727-143"><strong>VideoPacketLossRateOptimal</strong></span><span class="sxs-lookup"><span data-stu-id="7a727-143"><strong>VideoPacketLossRateOptimal</strong></span></span></p></td>
<td><p><span data-ttu-id="7a727-144">=</span><span class="sxs-lookup"><span data-stu-id="7a727-144">foat</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="7a727-145">既定値は 0.05 です。</span><span class="sxs-lookup"><span data-stu-id="7a727-145">The default value is 0.05.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7a727-146"><strong>VideoPacketLossRateAcceptable</strong></span><span class="sxs-lookup"><span data-stu-id="7a727-146"><strong>VideoPacketLossRateAcceptable</strong></span></span></p></td>
<td><p><span data-ttu-id="7a727-147">浮動小数点数</span><span class="sxs-lookup"><span data-stu-id="7a727-147">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="7a727-148">既定値は 0.10 です。</span><span class="sxs-lookup"><span data-stu-id="7a727-148">The default value is 0.10.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7a727-149"><strong>VideoFrameRateAvgOptimal</strong></span><span class="sxs-lookup"><span data-stu-id="7a727-149"><strong>VideoFrameRateAvgOptimal</strong></span></span></p></td>
<td><p><span data-ttu-id="7a727-150">浮動小数点数</span><span class="sxs-lookup"><span data-stu-id="7a727-150">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="7a727-151">既定値は 12 です。</span><span class="sxs-lookup"><span data-stu-id="7a727-151">The default value is 12.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7a727-152"><strong>VideoFrameRateAvgAcceptable</strong></span><span class="sxs-lookup"><span data-stu-id="7a727-152"><strong>VideoFrameRateAvgAcceptable</strong></span></span></p></td>
<td><p><span data-ttu-id="7a727-153">浮動小数点数</span><span class="sxs-lookup"><span data-stu-id="7a727-153">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="7a727-154">既定値は 7 です。</span><span class="sxs-lookup"><span data-stu-id="7a727-154">The default value is 7.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7a727-155"><strong>DynamicCapabilityPercentOptimal</strong></span><span class="sxs-lookup"><span data-stu-id="7a727-155"><strong>DynamicCapabilityPercentOptimal</strong></span></span></p></td>
<td><p><span data-ttu-id="7a727-156">10進数 (5、2)</span><span class="sxs-lookup"><span data-stu-id="7a727-156">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="7a727-157">既定値は 5.00 です。</span><span class="sxs-lookup"><span data-stu-id="7a727-157">The default value is 5.00.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7a727-158"><strong>DynamicCapabilityPercentAcceptable</strong></span><span class="sxs-lookup"><span data-stu-id="7a727-158"><strong>DynamicCapabilityPercentAcceptable</strong></span></span></p></td>
<td><p><span data-ttu-id="7a727-159">10進数 (5、2)</span><span class="sxs-lookup"><span data-stu-id="7a727-159">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="7a727-160">既定値は 10.00 です。</span><span class="sxs-lookup"><span data-stu-id="7a727-160">The default value is 10.00.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

