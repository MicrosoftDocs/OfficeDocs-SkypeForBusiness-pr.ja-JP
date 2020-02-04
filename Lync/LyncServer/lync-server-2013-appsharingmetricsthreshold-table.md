---
title: 'Lync Server 2013: AppSharingMetricsThreshold テーブル'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: AppSharingMetricsThreshold table
ms:assetid: 782cfab9-01a6-4843-aea1-28f47b0b51f7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205018(v=OCS.15)
ms:contentKeyID: 48184556
ms.date: 12/09/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7e247f83b00d226024f9fc671f2d744f1ee7fdf0
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41738427"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="appsharingmetricsthreshold-table-in-lync-server-2013"></a><span data-ttu-id="824b6-102">Lync Server 2013 の AppSharingMetricsThreshold テーブル</span><span class="sxs-lookup"><span data-stu-id="824b6-102">AppSharingMetricsThreshold table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="824b6-103">_**最終更新日:** 2015-12-08_</span><span class="sxs-lookup"><span data-stu-id="824b6-103">_**Topic Last Modified:** 2015-12-08_</span></span>

<span data-ttu-id="824b6-104">AppSharingMetricsThreshold の表には、アプリケーションの共有で使用されるエクスペリエンスメトリックの品質と受け入れ可能な値が含まれています。</span><span class="sxs-lookup"><span data-stu-id="824b6-104">The AppSharingMetricsThreshold table contains optimal and acceptable values for the Quality of Experience metrics used with application sharing.</span></span> <span data-ttu-id="824b6-105">これらのしきい値は、アプリケーション共有エクスペリエンスが低品質として分類される必要があるかどうかを判断するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="824b6-105">These thresholds are used to determine if the application sharing experience should be classified as poor.</span></span>

<span data-ttu-id="824b6-106">この表は、Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="824b6-106">This table was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="824b6-107"><strong>列</strong></span><span class="sxs-lookup"><span data-stu-id="824b6-107"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="824b6-108"><strong>データ型</strong></span><span class="sxs-lookup"><span data-stu-id="824b6-108"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="824b6-109"><strong>キー/インデックス</strong></span><span class="sxs-lookup"><span data-stu-id="824b6-109"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="824b6-110"><strong>詳細</strong></span><span class="sxs-lookup"><span data-stu-id="824b6-110"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="824b6-111"><strong>CallType</strong></span><span class="sxs-lookup"><span data-stu-id="824b6-111"><strong>CallType</strong></span></span></p></td>
<td><p><span data-ttu-id="824b6-112">int</span><span class="sxs-lookup"><span data-stu-id="824b6-112">int</span></span></p></td>
<td><p><span data-ttu-id="824b6-113">Primary</span><span class="sxs-lookup"><span data-stu-id="824b6-113">Primary</span></span></p></td>
<td><p><span data-ttu-id="824b6-114">発信した通話の種類。</span><span class="sxs-lookup"><span data-stu-id="824b6-114">Type of call that was placed.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="824b6-115"><strong>AppliedBandwidthLimitOptimal</strong></span><span class="sxs-lookup"><span data-stu-id="824b6-115"><strong>AppliedBandwidthLimitOptimal</strong></span></span></p></td>
<td><p><span data-ttu-id="824b6-116">int</span><span class="sxs-lookup"><span data-stu-id="824b6-116">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="824b6-117">アプリケーション共有に最適な帯域幅の制限。</span><span class="sxs-lookup"><span data-stu-id="824b6-117">Optimal bandwidth limitation for application sharing.</span></span> <span data-ttu-id="824b6-118">既定値は100万です。</span><span class="sxs-lookup"><span data-stu-id="824b6-118">The default value is 1000000.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="824b6-119"><strong>AppliedBandwidthLimitAcceptable</strong></span><span class="sxs-lookup"><span data-stu-id="824b6-119"><strong>AppliedBandwidthLimitAcceptable</strong></span></span></p></td>
<td><p><span data-ttu-id="824b6-120">int</span><span class="sxs-lookup"><span data-stu-id="824b6-120">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="824b6-121">アプリケーション共有に対して許容可能な帯域幅制限。</span><span class="sxs-lookup"><span data-stu-id="824b6-121">Acceptable bandwidth limitation for application sharing.</span></span> <span data-ttu-id="824b6-122">既定値は50万です。</span><span class="sxs-lookup"><span data-stu-id="824b6-122">The default value is 500000.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="824b6-123"><strong>SpoiledTilePercentTotalOptimal</strong></span><span class="sxs-lookup"><span data-stu-id="824b6-123"><strong>SpoiledTilePercentTotalOptimal</strong></span></span></p></td>
<td><p><span data-ttu-id="824b6-124">10進数 (5, 2)</span><span class="sxs-lookup"><span data-stu-id="824b6-124">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="824b6-125">アプリケーション共有の品質を分類するための "損失" タイルの最適な比率。</span><span class="sxs-lookup"><span data-stu-id="824b6-125">Optimal percentage rate for “spoiled” tiles for classifying an Application Sharing quality.</span></span> <span data-ttu-id="824b6-126">この値は、閲覧者に届かなかった、共有先のコンテンツのパーセンテージです。</span><span class="sxs-lookup"><span data-stu-id="824b6-126">This value is the percentage of the content from the sharer that did not reach the viewer.</span></span> <span data-ttu-id="824b6-127">グラフィックスソースまたは ASMCU タイルから共有されているタイルがそれぞれ、共有元のタイルを破棄した場合、コンテンツは破棄 (または損失) されることがあります。</span><span class="sxs-lookup"><span data-stu-id="824b6-127">Content may be discarded (or spoiled) when the sharer discards tiles from the graphics source or the ASMCU tiles discards tiles from Sharer respectively.</span></span> <span data-ttu-id="824b6-128">既定値は11パーセントです。</span><span class="sxs-lookup"><span data-stu-id="824b6-128">The default value is 11 percent.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="824b6-129"><strong>SpoiledTilePercentTotalAcceptable</strong></span><span class="sxs-lookup"><span data-stu-id="824b6-129"><strong>SpoiledTilePercentTotalAcceptable</strong></span></span></p></td>
<td><p><span data-ttu-id="824b6-130">10進数 (5, 2)</span><span class="sxs-lookup"><span data-stu-id="824b6-130">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="824b6-131">アプリの共有品質を分類するための "損失" タイルの cceptable のパーセンテージ率。</span><span class="sxs-lookup"><span data-stu-id="824b6-131">cceptable percentage rate for “spoiled” tiles for classifying an Application Sharing quality.</span></span> <span data-ttu-id="824b6-132">この値は、閲覧者に届かなかった、共有先のコンテンツのパーセンテージです。</span><span class="sxs-lookup"><span data-stu-id="824b6-132">This value is the percentage of the content from the sharer that did not reach the viewer.</span></span> <span data-ttu-id="824b6-133">グラフィックスソースまたは ASMCU タイルから共有されているタイルがそれぞれ、共有元のタイルを破棄した場合、コンテンツは破棄 (または損失) されることがあります。</span><span class="sxs-lookup"><span data-stu-id="824b6-133">Content may be discarded (or spoiled) when the sharer discards tiles from the graphics source or the ASMCU tiles discards tiles from Sharer respectively.</span></span> <span data-ttu-id="824b6-134">既定値は36パーセントです。</span><span class="sxs-lookup"><span data-stu-id="824b6-134">The default value is 36 percent.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="824b6-135"><strong>JitterInterArrivalOptimal</strong></span><span class="sxs-lookup"><span data-stu-id="824b6-135"><strong>JitterInterArrivalOptimal</strong></span></span></p></td>
<td><p><span data-ttu-id="824b6-136">int</span><span class="sxs-lookup"><span data-stu-id="824b6-136">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="824b6-137">この列は、Microsoft Lync Server 2013 では使用されません。</span><span class="sxs-lookup"><span data-stu-id="824b6-137">This column is not used in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="824b6-138"><strong>JitterInterArrivalAcceptable</strong></span><span class="sxs-lookup"><span data-stu-id="824b6-138"><strong>JitterInterArrivalAcceptable</strong></span></span></p></td>
<td><p><span data-ttu-id="824b6-139">int</span><span class="sxs-lookup"><span data-stu-id="824b6-139">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="824b6-140">この列は、Microsoft Lync Server 2013 では使用されません。</span><span class="sxs-lookup"><span data-stu-id="824b6-140">This column is not used in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="824b6-141"><strong>RelativeOneWayBurstDensityOptimal</strong></span><span class="sxs-lookup"><span data-stu-id="824b6-141"><strong>RelativeOneWayBurstDensityOptimal</strong></span></span></p></td>
<td><p><span data-ttu-id="824b6-142">float</span><span class="sxs-lookup"><span data-stu-id="824b6-142">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="824b6-143">この列は、Microsoft Lync Server 2013 では使用されません。</span><span class="sxs-lookup"><span data-stu-id="824b6-143">This column is not used in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="824b6-144"><strong>RelativeOneWayBurstDensityAcceptable</strong></span><span class="sxs-lookup"><span data-stu-id="824b6-144"><strong>RelativeOneWayBurstDensityAcceptable</strong></span></span></p></td>
<td><p><span data-ttu-id="824b6-145">float</span><span class="sxs-lookup"><span data-stu-id="824b6-145">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="824b6-146">この列は、Microsoft Lync Server 2013 では使用されません。</span><span class="sxs-lookup"><span data-stu-id="824b6-146">This column is not used in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="824b6-147"><strong>RDPTileProcessingLatencyBurstDensityOptimal</strong></span><span class="sxs-lookup"><span data-stu-id="824b6-147"><strong>RDPTileProcessingLatencyBurstDensityOptimal</strong></span></span></p></td>
<td><p><span data-ttu-id="824b6-148">float</span><span class="sxs-lookup"><span data-stu-id="824b6-148">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="824b6-149">この列は、Microsoft Lync Server 2013 では使用されません。</span><span class="sxs-lookup"><span data-stu-id="824b6-149">This column is not used in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="824b6-150"><strong>RDPTileProcessingLatencyBurstDensityAcceptable</strong></span><span class="sxs-lookup"><span data-stu-id="824b6-150"><strong>RDPTileProcessingLatencyBurstDensityAcceptable</strong></span></span></p></td>
<td><p><span data-ttu-id="824b6-151">float</span><span class="sxs-lookup"><span data-stu-id="824b6-151">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="824b6-152">この列は、Microsoft Lync Server 2013 では使用されません。</span><span class="sxs-lookup"><span data-stu-id="824b6-152">This column is not used in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="824b6-153"><strong>RelativeOneWayAverageOptimal</strong></span><span class="sxs-lookup"><span data-stu-id="824b6-153"><strong>RelativeOneWayAverageOptimal</strong></span></span></p></td>
<td><p><span data-ttu-id="824b6-154">float</span><span class="sxs-lookup"><span data-stu-id="824b6-154">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="824b6-155">アプリケーション共有に関連する2つのメディアエンドポイント間の相対的な一方向の遅延の最適値。</span><span class="sxs-lookup"><span data-stu-id="824b6-155">Optimal value for the relative one-way delay between the two media endpoints involved in the application sharing.</span></span> <span data-ttu-id="824b6-156">これは 1 ホップの遅延の測定です。</span><span class="sxs-lookup"><span data-stu-id="824b6-156">This is a single-hop latency measure.</span></span> <span data-ttu-id="824b6-157">既定値は1.0 秒です。</span><span class="sxs-lookup"><span data-stu-id="824b6-157">The default value is 1.0 seconds.</span></span></p>
<p><span data-ttu-id="824b6-158">この列は、Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="824b6-158">The column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="824b6-159"><strong>RelativeOneWayAverageAcceptable</strong></span><span class="sxs-lookup"><span data-stu-id="824b6-159"><strong>RelativeOneWayAverageAcceptable</strong></span></span></p></td>
<td><p><span data-ttu-id="824b6-160">float</span><span class="sxs-lookup"><span data-stu-id="824b6-160">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="824b6-161">アプリケーション共有に関連する2つのメディアエンドポイント間の相対的な一方向の遅延の最適値。</span><span class="sxs-lookup"><span data-stu-id="824b6-161">Optimal value for the relative one-way delay between the two media endpoints involved in the application sharing.</span></span> <span data-ttu-id="824b6-162">これは 1 ホップの遅延の測定です。</span><span class="sxs-lookup"><span data-stu-id="824b6-162">This is a single-hop latency measure.</span></span> <span data-ttu-id="824b6-163">既定値は1.75 秒です。</span><span class="sxs-lookup"><span data-stu-id="824b6-163">The default value is 1.75 seconds.</span></span></p>
<p><span data-ttu-id="824b6-164">この列は、Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="824b6-164">The column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="824b6-165"><strong>RDPTileProcessingLatencyAverageOptimal</strong></span><span class="sxs-lookup"><span data-stu-id="824b6-165"><strong>RDPTileProcessingLatencyAverageOptimal</strong></span></span></p></td>
<td><p><span data-ttu-id="824b6-166">float</span><span class="sxs-lookup"><span data-stu-id="824b6-166">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="824b6-167">表示セッションの間の会議サーバーとしての平均 RDP タイル処理の待機時間の最適値。</span><span class="sxs-lookup"><span data-stu-id="824b6-167">Optimal value of the average RDP tile processing latency in the AS Conferencing Server over the duration of the viewing session.</span></span> <span data-ttu-id="824b6-168">[待ち時間] は、サーバー (シナリオによっては共有先または MCU) で開始フレームがエンコードされてから、同じ開始フレームが viewer でデコードされるタイミングの差です。</span><span class="sxs-lookup"><span data-stu-id="824b6-168">Latency is the time difference between when the Start Frame is encoded on the server (sharer or MCU depending on the scenario) and the same Start Frame is decoded on the viewer.</span></span></p>
<p><span data-ttu-id="824b6-169">平均値が高いと、表示の際の遅延が大きくなります。</span><span class="sxs-lookup"><span data-stu-id="824b6-169">A high average reflects a longer delay in the viewing experience.</span></span> <span data-ttu-id="824b6-170">過負荷の会議サーバーでは平均遅延が大きくなる場合があります。</span><span class="sxs-lookup"><span data-stu-id="824b6-170">An overloaded conferencing server may experience higher average delays.</span></span> <span data-ttu-id="824b6-171">既定値は200ms です。</span><span class="sxs-lookup"><span data-stu-id="824b6-171">The default value is 200ms.</span></span></p>
<p><span data-ttu-id="824b6-172">この列は、Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="824b6-172">The column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="824b6-173"><strong>RDPTileProcessingLatencyAverageAcceptable</strong></span><span class="sxs-lookup"><span data-stu-id="824b6-173"><strong>RDPTileProcessingLatencyAverageAcceptable</strong></span></span></p></td>
<td><p><span data-ttu-id="824b6-174">float</span><span class="sxs-lookup"><span data-stu-id="824b6-174">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="824b6-175">表示セッション中の会議サーバーとしての平均 RDP タイル処理待ち時間の値。</span><span class="sxs-lookup"><span data-stu-id="824b6-175">Acceptable value of the average RDP tile processing latency in the AS Conferencing Server over the duration of the viewing session.</span></span> <span data-ttu-id="824b6-176">[待ち時間] は、サーバー (シナリオによっては共有先または MCU) で開始フレームがエンコードされてから、同じ開始フレームが viewer でデコードされるタイミングの差です。</span><span class="sxs-lookup"><span data-stu-id="824b6-176">Latency is the time difference between when the Start Frame is encoded on the server (sharer or MCU depending on the scenario) and the same Start Frame is decoded on the viewer.</span></span></p>
<p><span data-ttu-id="824b6-177">平均値が高いと、表示の際の遅延が大きくなります。</span><span class="sxs-lookup"><span data-stu-id="824b6-177">A high average reflects a longer delay in the viewing experience.</span></span> <span data-ttu-id="824b6-178">過負荷の会議サーバーでは平均遅延が大きくなる場合があります。</span><span class="sxs-lookup"><span data-stu-id="824b6-178">An overloaded conferencing server may experience higher average delays.</span></span> <span data-ttu-id="824b6-179">既定値は200ms です。</span><span class="sxs-lookup"><span data-stu-id="824b6-179">The default value is 200ms.</span></span></p>
<p><span data-ttu-id="824b6-180">この列は、Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="824b6-180">The column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

