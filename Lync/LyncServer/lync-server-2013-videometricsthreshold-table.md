---
title: 'Lync Server 2013: VideoMetricsThreshold テーブル'
description: 'Lync Server 2013: VideoMetricsThreshold テーブル。'
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
ms.openlocfilehash: 93cdd6fb4c3c54ac1470499490f36fee87ba283d
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48568003"
---
# <a name="videometricsthreshold-table-in-lync-server-2013"></a><span data-ttu-id="d84cd-103">Lync Server 2013 の VideoMetricsThreshold テーブル</span><span class="sxs-lookup"><span data-stu-id="d84cd-103">VideoMetricsThreshold table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d84cd-104">_**トピックの最終更新日:** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="d84cd-104">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="d84cd-105">VideoMetricsThreshold テーブルには、ビデオ通話で使用される QoE 指標の最適な値および許容可能な値が含まれています。</span><span class="sxs-lookup"><span data-stu-id="d84cd-105">The VideoMetricsThreshold table contains optimal and acceptable values for the Quality of Experience metrics used with video calls.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="d84cd-106"><strong>列</strong></span><span class="sxs-lookup"><span data-stu-id="d84cd-106"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="d84cd-107"><strong>データ型</strong></span><span class="sxs-lookup"><span data-stu-id="d84cd-107"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="d84cd-108"><strong>キー/インデックス</strong></span><span class="sxs-lookup"><span data-stu-id="d84cd-108"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="d84cd-109"><strong>詳細</strong></span><span class="sxs-lookup"><span data-stu-id="d84cd-109"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="d84cd-110"><strong>CallType</strong></span><span class="sxs-lookup"><span data-stu-id="d84cd-110"><strong>CallType</strong></span></span></p></td>
<td><p><span data-ttu-id="d84cd-111">int</span><span class="sxs-lookup"><span data-stu-id="d84cd-111">int</span></span></p></td>
<td><p><span data-ttu-id="d84cd-112">Primary</span><span class="sxs-lookup"><span data-stu-id="d84cd-112">Primary</span></span></p></td>
<td><p><span data-ttu-id="d84cd-113">発信された通話の種類</span><span class="sxs-lookup"><span data-stu-id="d84cd-113">Type of call that was placed.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d84cd-114"><strong>VideoPostFECPLROptimal</strong></span><span class="sxs-lookup"><span data-stu-id="d84cd-114"><strong>VideoPostFECPLROptimal</strong></span></span></p></td>
<td><p><span data-ttu-id="d84cd-115">10進数 (5、2)</span><span class="sxs-lookup"><span data-stu-id="d84cd-115">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="d84cd-116">既定値は 0.05 です。</span><span class="sxs-lookup"><span data-stu-id="d84cd-116">The default value is 0.05.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d84cd-117"><strong>VideoPostFECPLRAcceptable</strong></span><span class="sxs-lookup"><span data-stu-id="d84cd-117"><strong>VideoPostFECPLRAcceptable</strong></span></span></p></td>
<td><p><span data-ttu-id="d84cd-118">10進数 (5、2)</span><span class="sxs-lookup"><span data-stu-id="d84cd-118">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="d84cd-119">既定値は 0.10 です。</span><span class="sxs-lookup"><span data-stu-id="d84cd-119">The default value is 0.10.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d84cd-120"><strong>VideoLocalFrameLostPercentageAverageOptimal</strong></span><span class="sxs-lookup"><span data-stu-id="d84cd-120"><strong>VideoLocalFrameLostPercentageAverageOptimal</strong></span></span></p></td>
<td><p><span data-ttu-id="d84cd-121">10進数 (5、2)</span><span class="sxs-lookup"><span data-stu-id="d84cd-121">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="d84cd-122">既定値は 5.0 です。</span><span class="sxs-lookup"><span data-stu-id="d84cd-122">The default value is 5.0.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d84cd-123"><strong>VideoLocalFrameLostPercentageAverageAcceptable</strong></span><span class="sxs-lookup"><span data-stu-id="d84cd-123"><strong>VideoLocalFrameLostPercentageAverageAcceptable</strong></span></span></p></td>
<td><p><span data-ttu-id="d84cd-124">10進数 (5、2)</span><span class="sxs-lookup"><span data-stu-id="d84cd-124">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="d84cd-125">既定値は 10.0 です。</span><span class="sxs-lookup"><span data-stu-id="d84cd-125">The default value is 10.0.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d84cd-126"><strong>RecvFrameRateAverageOptimal</strong></span><span class="sxs-lookup"><span data-stu-id="d84cd-126"><strong>RecvFrameRateAverageOptimal</strong></span></span></p></td>
<td><p><span data-ttu-id="d84cd-127">10進数 (9、4)</span><span class="sxs-lookup"><span data-stu-id="d84cd-127">decimal(9,4)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="d84cd-128">既定値は 12.0000 です。</span><span class="sxs-lookup"><span data-stu-id="d84cd-128">The default value is 12.0000.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d84cd-129"><strong>RecvFramerateAverageAcceptable</strong></span><span class="sxs-lookup"><span data-stu-id="d84cd-129"><strong>RecvFramerateAverageAcceptable</strong></span></span></p></td>
<td><p><span data-ttu-id="d84cd-130">10進数 (9、4)</span><span class="sxs-lookup"><span data-stu-id="d84cd-130">decimal(9,4)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="d84cd-131">既定値は 7.0000 です。</span><span class="sxs-lookup"><span data-stu-id="d84cd-131">The default value is 7.0000.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d84cd-132"><strong>LowFrameRateCallPercentOptimal</strong></span><span class="sxs-lookup"><span data-stu-id="d84cd-132"><strong>LowFrameRateCallPercentOptimal</strong></span></span></p></td>
<td><p><span data-ttu-id="d84cd-133">10進数 (5、2)</span><span class="sxs-lookup"><span data-stu-id="d84cd-133">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="d84cd-134">既定値は 5.0 です。</span><span class="sxs-lookup"><span data-stu-id="d84cd-134">The default value is 5.0.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d84cd-135"><strong>LowFrameRateCallPercentAcceptable</strong></span><span class="sxs-lookup"><span data-stu-id="d84cd-135"><strong>LowFrameRateCallPercentAcceptable</strong></span></span></p></td>
<td><p><span data-ttu-id="d84cd-136">10進数 (5、2)</span><span class="sxs-lookup"><span data-stu-id="d84cd-136">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="d84cd-137">既定値は 10.0 です。</span><span class="sxs-lookup"><span data-stu-id="d84cd-137">The default value is 10.0/</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d84cd-138"><strong>LowResolutionCallPercentOptimal</strong></span><span class="sxs-lookup"><span data-stu-id="d84cd-138"><strong>LowResolutionCallPercentOptimal</strong></span></span></p></td>
<td><p><span data-ttu-id="d84cd-139">10進数 (5、2)</span><span class="sxs-lookup"><span data-stu-id="d84cd-139">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="d84cd-140">既定値は 5.0 です。</span><span class="sxs-lookup"><span data-stu-id="d84cd-140">The default value is 5.0.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d84cd-141"><strong>LowResolutionCallPercentAcceptable</strong></span><span class="sxs-lookup"><span data-stu-id="d84cd-141"><strong>LowResolutionCallPercentAcceptable</strong></span></span></p></td>
<td><p><span data-ttu-id="d84cd-142">10進数 (5、2)</span><span class="sxs-lookup"><span data-stu-id="d84cd-142">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="d84cd-143">既定値は 10.0 です。</span><span class="sxs-lookup"><span data-stu-id="d84cd-143">The default value is 10.0.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d84cd-144"><strong>VideoPacketLossRateOptimal</strong></span><span class="sxs-lookup"><span data-stu-id="d84cd-144"><strong>VideoPacketLossRateOptimal</strong></span></span></p></td>
<td><p><span data-ttu-id="d84cd-145">=</span><span class="sxs-lookup"><span data-stu-id="d84cd-145">foat</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="d84cd-146">既定値は 0.05 です。</span><span class="sxs-lookup"><span data-stu-id="d84cd-146">The default value is 0.05.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d84cd-147"><strong>VideoPacketLossRateAcceptable</strong></span><span class="sxs-lookup"><span data-stu-id="d84cd-147"><strong>VideoPacketLossRateAcceptable</strong></span></span></p></td>
<td><p><span data-ttu-id="d84cd-148">浮動小数点数</span><span class="sxs-lookup"><span data-stu-id="d84cd-148">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="d84cd-149">既定値は 0.10 です。</span><span class="sxs-lookup"><span data-stu-id="d84cd-149">The default value is 0.10.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d84cd-150"><strong>VideoFrameRateAvgOptimal</strong></span><span class="sxs-lookup"><span data-stu-id="d84cd-150"><strong>VideoFrameRateAvgOptimal</strong></span></span></p></td>
<td><p><span data-ttu-id="d84cd-151">浮動小数点数</span><span class="sxs-lookup"><span data-stu-id="d84cd-151">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="d84cd-152">既定値は 12 です。</span><span class="sxs-lookup"><span data-stu-id="d84cd-152">The default value is 12.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d84cd-153"><strong>VideoFrameRateAvgAcceptable</strong></span><span class="sxs-lookup"><span data-stu-id="d84cd-153"><strong>VideoFrameRateAvgAcceptable</strong></span></span></p></td>
<td><p><span data-ttu-id="d84cd-154">浮動小数点数</span><span class="sxs-lookup"><span data-stu-id="d84cd-154">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="d84cd-155">既定値は 7 です。</span><span class="sxs-lookup"><span data-stu-id="d84cd-155">The default value is 7.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d84cd-156"><strong>DynamicCapabilityPercentOptimal</strong></span><span class="sxs-lookup"><span data-stu-id="d84cd-156"><strong>DynamicCapabilityPercentOptimal</strong></span></span></p></td>
<td><p><span data-ttu-id="d84cd-157">10進数 (5、2)</span><span class="sxs-lookup"><span data-stu-id="d84cd-157">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="d84cd-158">既定値は 5.00 です。</span><span class="sxs-lookup"><span data-stu-id="d84cd-158">The default value is 5.00.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d84cd-159"><strong>DynamicCapabilityPercentAcceptable</strong></span><span class="sxs-lookup"><span data-stu-id="d84cd-159"><strong>DynamicCapabilityPercentAcceptable</strong></span></span></p></td>
<td><p><span data-ttu-id="d84cd-160">10進数 (5、2)</span><span class="sxs-lookup"><span data-stu-id="d84cd-160">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="d84cd-161">既定値は 10.00 です。</span><span class="sxs-lookup"><span data-stu-id="d84cd-161">The default value is 10.00.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

