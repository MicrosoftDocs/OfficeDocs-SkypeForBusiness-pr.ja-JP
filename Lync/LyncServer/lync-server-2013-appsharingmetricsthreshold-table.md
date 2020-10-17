---
title: 'Lync Server 2013: AppSharingMetricsThreshold テーブル'
description: 'Lync Server 2013: AppSharingMetricsThreshold テーブル。'
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
ms.openlocfilehash: 092c7d08026e6b736b81043a71b4ecaabc4d5f1b
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48546813"
---
# <a name="appsharingmetricsthreshold-table-in-lync-server-2013"></a><span data-ttu-id="c7366-103">Lync Server 2013 の AppSharingMetricsThreshold テーブル</span><span class="sxs-lookup"><span data-stu-id="c7366-103">AppSharingMetricsThreshold table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c7366-104">_**トピックの最終更新日:** 2015-12-08_</span><span class="sxs-lookup"><span data-stu-id="c7366-104">_**Topic Last Modified:** 2015-12-08_</span></span>

<span data-ttu-id="c7366-p101">AppSharingMetricsThreshold テーブルには、アプリケーション共有で使用される QoE (Quality of Experience) 指標の最適な値と許容される値が含まれます。これらのしきい値は、アプリケーション共有のエクスペリエンスを不良として分類する必要があるかどうかを判断するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="c7366-p101">The AppSharingMetricsThreshold table contains optimal and acceptable values for the Quality of Experience metrics used with application sharing. These thresholds are used to determine if the application sharing experience should be classified as poor.</span></span>

<span data-ttu-id="c7366-107">この表は、Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="c7366-107">This table was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="c7366-108"><strong>列</strong></span><span class="sxs-lookup"><span data-stu-id="c7366-108"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="c7366-109"><strong>データ型</strong></span><span class="sxs-lookup"><span data-stu-id="c7366-109"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="c7366-110"><strong>キー/インデックス</strong></span><span class="sxs-lookup"><span data-stu-id="c7366-110"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="c7366-111"><strong>詳細</strong></span><span class="sxs-lookup"><span data-stu-id="c7366-111"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c7366-112"><strong>CallType</strong></span><span class="sxs-lookup"><span data-stu-id="c7366-112"><strong>CallType</strong></span></span></p></td>
<td><p><span data-ttu-id="c7366-113">int</span><span class="sxs-lookup"><span data-stu-id="c7366-113">int</span></span></p></td>
<td><p><span data-ttu-id="c7366-114">Primary</span><span class="sxs-lookup"><span data-stu-id="c7366-114">Primary</span></span></p></td>
<td><p><span data-ttu-id="c7366-115">行われた通話の種類です。</span><span class="sxs-lookup"><span data-stu-id="c7366-115">Type of call that was placed.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c7366-116"><strong>AppliedBandwidthLimitOptimal</strong></span><span class="sxs-lookup"><span data-stu-id="c7366-116"><strong>AppliedBandwidthLimitOptimal</strong></span></span></p></td>
<td><p><span data-ttu-id="c7366-117">int</span><span class="sxs-lookup"><span data-stu-id="c7366-117">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="c7366-p102">アプリケーション共有の最善の帯域幅制限です。既定値は 1000000 です。</span><span class="sxs-lookup"><span data-stu-id="c7366-p102">Optimal bandwidth limitation for application sharing. The default value is 1000000.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c7366-120"><strong>AppliedBandwidthLimitAcceptable</strong></span><span class="sxs-lookup"><span data-stu-id="c7366-120"><strong>AppliedBandwidthLimitAcceptable</strong></span></span></p></td>
<td><p><span data-ttu-id="c7366-121">int</span><span class="sxs-lookup"><span data-stu-id="c7366-121">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="c7366-p103">アプリケーション共有の許容される帯域幅制限です。既定値は 500000 です。</span><span class="sxs-lookup"><span data-stu-id="c7366-p103">Acceptable bandwidth limitation for application sharing. The default value is 500000.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c7366-124"><strong>SpoiledTilePercentTotalOptimal</strong></span><span class="sxs-lookup"><span data-stu-id="c7366-124"><strong>SpoiledTilePercentTotalOptimal</strong></span></span></p></td>
<td><p><span data-ttu-id="c7366-125">10進数 (5、2)</span><span class="sxs-lookup"><span data-stu-id="c7366-125">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="c7366-p104">アプリケーション共有の品質の分類のために "スポイルされた" タイルの最善の割合です。この値は、ビューアーに到達しなかった共有者からのコンテンツのパーセンテージです。コンテンツは、共有者がグラフィックス ソースからタイルを破棄すると、または ASMCU タイルが共有者からタイルを破棄すると、破棄される (スポイルされる) 可能性があります。既定値は 11 パーセントです。</span><span class="sxs-lookup"><span data-stu-id="c7366-p104">Optimal percentage rate for “spoiled” tiles for classifying an Application Sharing quality. This value is the percentage of the content from the sharer that did not reach the viewer. Content may be discarded (or spoiled) when the sharer discards tiles from the graphics source or the ASMCU tiles discards tiles from Sharer respectively. The default value is 11 percent.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c7366-130"><strong>SpoiledTilePercentTotalAcceptable</strong></span><span class="sxs-lookup"><span data-stu-id="c7366-130"><strong>SpoiledTilePercentTotalAcceptable</strong></span></span></p></td>
<td><p><span data-ttu-id="c7366-131">10進数 (5、2)</span><span class="sxs-lookup"><span data-stu-id="c7366-131">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="c7366-p105">アプリケーション共有の品質の分類のために "スポイルされた" タイルの許容される割合です。この値は、ビューアーに到達しなかった共有者からのコンテンツのパーセンテージです。コンテンツは、共有者がグラフィックス ソースからタイルを破棄すると、または ASMCU タイルが共有者からタイルを破棄すると、破棄される (スポイルされる) 可能性があります。既定値は 36 パーセントです。</span><span class="sxs-lookup"><span data-stu-id="c7366-p105">cceptable percentage rate for “spoiled” tiles for classifying an Application Sharing quality. This value is the percentage of the content from the sharer that did not reach the viewer. Content may be discarded (or spoiled) when the sharer discards tiles from the graphics source or the ASMCU tiles discards tiles from Sharer respectively. The default value is 36 percent.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c7366-136"><strong>JitterInterArrivalOptimal</strong></span><span class="sxs-lookup"><span data-stu-id="c7366-136"><strong>JitterInterArrivalOptimal</strong></span></span></p></td>
<td><p><span data-ttu-id="c7366-137">int</span><span class="sxs-lookup"><span data-stu-id="c7366-137">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="c7366-138">この列は、Microsoft Lync Server 2013 では使用されません。</span><span class="sxs-lookup"><span data-stu-id="c7366-138">This column is not used in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c7366-139"><strong>JitterInterArrivalAcceptable</strong></span><span class="sxs-lookup"><span data-stu-id="c7366-139"><strong>JitterInterArrivalAcceptable</strong></span></span></p></td>
<td><p><span data-ttu-id="c7366-140">int</span><span class="sxs-lookup"><span data-stu-id="c7366-140">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="c7366-141">この列は、Microsoft Lync Server 2013 では使用されません。</span><span class="sxs-lookup"><span data-stu-id="c7366-141">This column is not used in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c7366-142"><strong>RelativeOneWayBurstDensityOptimal</strong></span><span class="sxs-lookup"><span data-stu-id="c7366-142"><strong>RelativeOneWayBurstDensityOptimal</strong></span></span></p></td>
<td><p><span data-ttu-id="c7366-143">浮動小数点数</span><span class="sxs-lookup"><span data-stu-id="c7366-143">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="c7366-144">この列は、Microsoft Lync Server 2013 では使用されません。</span><span class="sxs-lookup"><span data-stu-id="c7366-144">This column is not used in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c7366-145"><strong>RelativeOneWayBurstDensityAcceptable</strong></span><span class="sxs-lookup"><span data-stu-id="c7366-145"><strong>RelativeOneWayBurstDensityAcceptable</strong></span></span></p></td>
<td><p><span data-ttu-id="c7366-146">浮動小数点数</span><span class="sxs-lookup"><span data-stu-id="c7366-146">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="c7366-147">この列は、Microsoft Lync Server 2013 では使用されません。</span><span class="sxs-lookup"><span data-stu-id="c7366-147">This column is not used in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c7366-148"><strong>RDPTileProcessingLatencyBurstDensityOptimal</strong></span><span class="sxs-lookup"><span data-stu-id="c7366-148"><strong>RDPTileProcessingLatencyBurstDensityOptimal</strong></span></span></p></td>
<td><p><span data-ttu-id="c7366-149">浮動小数点数</span><span class="sxs-lookup"><span data-stu-id="c7366-149">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="c7366-150">この列は、Microsoft Lync Server 2013 では使用されません。</span><span class="sxs-lookup"><span data-stu-id="c7366-150">This column is not used in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c7366-151"><strong>RDPTileProcessingLatencyBurstDensityAcceptable</strong></span><span class="sxs-lookup"><span data-stu-id="c7366-151"><strong>RDPTileProcessingLatencyBurstDensityAcceptable</strong></span></span></p></td>
<td><p><span data-ttu-id="c7366-152">浮動小数点数</span><span class="sxs-lookup"><span data-stu-id="c7366-152">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="c7366-153">この列は、Microsoft Lync Server 2013 では使用されません。</span><span class="sxs-lookup"><span data-stu-id="c7366-153">This column is not used in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c7366-154"><strong>RelativeOneWayAverageOptimal</strong></span><span class="sxs-lookup"><span data-stu-id="c7366-154"><strong>RelativeOneWayAverageOptimal</strong></span></span></p></td>
<td><p><span data-ttu-id="c7366-155">浮動小数点数</span><span class="sxs-lookup"><span data-stu-id="c7366-155">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="c7366-p106">アプリケーション共有に関係する 2 つのメディア エンドポイント間の相対的な一方向遅延の最善の値です。これは単一ホップ遅延の測定値です。既定値は 1.0 秒です。</span><span class="sxs-lookup"><span data-stu-id="c7366-p106">Optimal value for the relative one-way delay between the two media endpoints involved in the application sharing. This is a single-hop latency measure. The default value is 1.0 seconds.</span></span></p>
<p><span data-ttu-id="c7366-159">このコラムは Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="c7366-159">The column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c7366-160"><strong>RelativeOneWayAverageAcceptable</strong></span><span class="sxs-lookup"><span data-stu-id="c7366-160"><strong>RelativeOneWayAverageAcceptable</strong></span></span></p></td>
<td><p><span data-ttu-id="c7366-161">浮動小数点数</span><span class="sxs-lookup"><span data-stu-id="c7366-161">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="c7366-p107">アプリケーション共有に関係する 2 つのメディア エンドポイント間の相対的な一方向遅延の許容される値です。これは単一ホップ遅延の測定値です。既定値は 1.75 秒です。</span><span class="sxs-lookup"><span data-stu-id="c7366-p107">Optimal value for the relative one-way delay between the two media endpoints involved in the application sharing. This is a single-hop latency measure. The default value is 1.75 seconds.</span></span></p>
<p><span data-ttu-id="c7366-165">このコラムは Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="c7366-165">The column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c7366-166"><strong>RDPTileProcessingLatencyAverageOptimal</strong></span><span class="sxs-lookup"><span data-stu-id="c7366-166"><strong>RDPTileProcessingLatencyAverageOptimal</strong></span></span></p></td>
<td><p><span data-ttu-id="c7366-167">浮動小数点数</span><span class="sxs-lookup"><span data-stu-id="c7366-167">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="c7366-168">表示セッション中の AS 会議サーバーでの RDP タイル処理の最善の平均遅延です。</span><span class="sxs-lookup"><span data-stu-id="c7366-168">Optimal value of the average RDP tile processing latency in the AS Conferencing Server over the duration of the viewing session.</span></span> <span data-ttu-id="c7366-169">Latency は、サーバー (シナリオによっては、共有先または MCU) で開始フレームがエンコードされてから、同じ開始フレームが閲覧者にデコードされるまでの時間差です。</span><span class="sxs-lookup"><span data-stu-id="c7366-169">Latency is the time difference between when the Start Frame is encoded on the server (sharer or MCU depending on the scenario) and the same Start Frame is decoded on the viewer.</span></span></p>
<p><span data-ttu-id="c7366-p109">高い平均値は、表示エクスペリエンスでの長い遅延を反映します。高い負荷がかかっている会議サーバーでは、平均遅延が高くなる場合があります。既定値は 200 ミリ秒です。</span><span class="sxs-lookup"><span data-stu-id="c7366-p109">A high average reflects a longer delay in the viewing experience. An overloaded conferencing server may experience higher average delays. The default value is 200ms.</span></span></p>
<p><span data-ttu-id="c7366-173">このコラムは Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="c7366-173">The column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c7366-174"><strong>RDPTileProcessingLatencyAverageAcceptable</strong></span><span class="sxs-lookup"><span data-stu-id="c7366-174"><strong>RDPTileProcessingLatencyAverageAcceptable</strong></span></span></p></td>
<td><p><span data-ttu-id="c7366-175">浮動小数点数</span><span class="sxs-lookup"><span data-stu-id="c7366-175">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="c7366-176">表示セッション中の AS 会議サーバーでの RDP タイル処理の平均遅延の許容される値です。</span><span class="sxs-lookup"><span data-stu-id="c7366-176">Acceptable value of the average RDP tile processing latency in the AS Conferencing Server over the duration of the viewing session.</span></span> <span data-ttu-id="c7366-177">Latency は、サーバー (シナリオによっては、共有先または MCU) で開始フレームがエンコードされてから、同じ開始フレームが閲覧者にデコードされるまでの時間差です。</span><span class="sxs-lookup"><span data-stu-id="c7366-177">Latency is the time difference between when the Start Frame is encoded on the server (sharer or MCU depending on the scenario) and the same Start Frame is decoded on the viewer.</span></span></p>
<p><span data-ttu-id="c7366-p111">高い平均値は、表示エクスペリエンスでの長い遅延を反映します。高い負荷がかかっている会議サーバーでは、平均遅延が高くなる場合があります。既定値は 200 ミリ秒です。</span><span class="sxs-lookup"><span data-stu-id="c7366-p111">A high average reflects a longer delay in the viewing experience. An overloaded conferencing server may experience higher average delays. The default value is 200ms.</span></span></p>
<p><span data-ttu-id="c7366-181">このコラムは Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="c7366-181">The column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

