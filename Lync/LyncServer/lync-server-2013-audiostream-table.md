---
title: 'Lync Server 2013: AudioStream テーブル'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: AudioStream table
ms:assetid: 49ccbbc3-2f73-45fc-80a6-e612535cbc10
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425961(v=OCS.15)
ms:contentKeyID: 48184077
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f9412001652f4f323bdd3fb5722d0d7222535fd2
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34840902"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="audiostream-table-in-lync-server-2013"></a><span data-ttu-id="b093f-102">Lync Server 2013 の AudioStream テーブル</span><span class="sxs-lookup"><span data-stu-id="b093f-102">AudioStream table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b093f-103">_**最終更新日:** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="b093f-103">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="b093f-104">各レコードは1つのオーディオストリームを表します。</span><span class="sxs-lookup"><span data-stu-id="b093f-104">Each record represents one audio stream.</span></span> <span data-ttu-id="b093f-105">通常、1つのオーディオメディアラインには2つのオーディオストリームが含まれています。</span><span class="sxs-lookup"><span data-stu-id="b093f-105">One audio media line usually contains two audio streams.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="b093f-106"><strong>列</strong></span><span class="sxs-lookup"><span data-stu-id="b093f-106"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="b093f-107"><strong>データ型</strong></span><span class="sxs-lookup"><span data-stu-id="b093f-107"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="b093f-108"><strong>キー/インデックス</strong></span><span class="sxs-lookup"><span data-stu-id="b093f-108"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="b093f-109"><strong>詳細</strong></span><span class="sxs-lookup"><span data-stu-id="b093f-109"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="b093f-110"><strong>ConferenceDateTime</strong></span><span class="sxs-lookup"><span data-stu-id="b093f-110"><strong>ConferenceDateTime</strong></span></span></p></td>
<td><p><span data-ttu-id="b093f-111">datetime</span><span class="sxs-lookup"><span data-stu-id="b093f-111">datetime</span></span></p></td>
<td><p><span data-ttu-id="b093f-112">Primary</span><span class="sxs-lookup"><span data-stu-id="b093f-112">Primary</span></span></p></td>
<td><p><span data-ttu-id="b093f-113"><a href="lync-server-2013-medialine-table.md">Lync Server 2013 の MediaLine テーブル</a>から参照されている。</span><span class="sxs-lookup"><span data-stu-id="b093f-113">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b093f-114"><strong>SessionSeq</strong></span><span class="sxs-lookup"><span data-stu-id="b093f-114"><strong>SessionSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="b093f-115">int</span><span class="sxs-lookup"><span data-stu-id="b093f-115">int</span></span></p></td>
<td><p><span data-ttu-id="b093f-116">Primary</span><span class="sxs-lookup"><span data-stu-id="b093f-116">Primary</span></span></p></td>
<td><p><span data-ttu-id="b093f-117"><a href="lync-server-2013-medialine-table.md">Lync Server 2013 の MediaLine テーブル</a>から参照されている。</span><span class="sxs-lookup"><span data-stu-id="b093f-117">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b093f-118"><strong>MediaLineLabel</strong></span><span class="sxs-lookup"><span data-stu-id="b093f-118"><strong>MediaLineLabel</strong></span></span></p></td>
<td><p><span data-ttu-id="b093f-119">tinyint</span><span class="sxs-lookup"><span data-stu-id="b093f-119">tinyint</span></span></p></td>
<td><p><span data-ttu-id="b093f-120">Primary</span><span class="sxs-lookup"><span data-stu-id="b093f-120">Primary</span></span></p></td>
<td><p><span data-ttu-id="b093f-121"><a href="lync-server-2013-medialine-table.md">Lync Server 2013 の MediaLine テーブル</a>から参照されている。</span><span class="sxs-lookup"><span data-stu-id="b093f-121">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b093f-122"><strong>StreamID</strong></span><span class="sxs-lookup"><span data-stu-id="b093f-122"><strong>StreamID</strong></span></span></p></td>
<td><p><span data-ttu-id="b093f-123">int</span><span class="sxs-lookup"><span data-stu-id="b093f-123">int</span></span></p></td>
<td><p><span data-ttu-id="b093f-124">Primary</span><span class="sxs-lookup"><span data-stu-id="b093f-124">Primary</span></span></p></td>
<td><p><span data-ttu-id="b093f-125">メディアライン内の一意の ID。</span><span class="sxs-lookup"><span data-stu-id="b093f-125">Unique ID within a media line.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b093f-126"><strong>JitterInterArrival</strong></span><span class="sxs-lookup"><span data-stu-id="b093f-126"><strong>JitterInterArrival</strong></span></span></p></td>
<td><p><span data-ttu-id="b093f-127">int</span><span class="sxs-lookup"><span data-stu-id="b093f-127">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="b093f-128">リアルタイム制御プロトコル (RTCP) の統計情報からの平均ネットワークジッター。</span><span class="sxs-lookup"><span data-stu-id="b093f-128">Average network jitter from Real Time Control Protocol (RTCP) statistics.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b093f-129"><strong>JitterInterArrivalMax</strong></span><span class="sxs-lookup"><span data-stu-id="b093f-129"><strong>JitterInterArrivalMax</strong></span></span></p></td>
<td><p><span data-ttu-id="b093f-130">int</span><span class="sxs-lookup"><span data-stu-id="b093f-130">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="b093f-131">通話中の最大ネットワークジッター。</span><span class="sxs-lookup"><span data-stu-id="b093f-131">Maximum network jitter during the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b093f-132"><strong>PacketLossRate</strong></span><span class="sxs-lookup"><span data-stu-id="b093f-132"><strong>PacketLossRate</strong></span></span></p></td>
<td><p><span data-ttu-id="b093f-133">10進数 (5, 4)</span><span class="sxs-lookup"><span data-stu-id="b093f-133">decimal(5,4)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="b093f-134">通話中の平均パケット損失率。</span><span class="sxs-lookup"><span data-stu-id="b093f-134">Average packet loss rate during the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b093f-135"><strong>PacketLossRateMax</strong></span><span class="sxs-lookup"><span data-stu-id="b093f-135"><strong>PacketLossRateMax</strong></span></span></p></td>
<td><p><span data-ttu-id="b093f-136">10進数 (5, 4)</span><span class="sxs-lookup"><span data-stu-id="b093f-136">decimal(5,4)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="b093f-137">通話中に発生したパケット損失の上限。</span><span class="sxs-lookup"><span data-stu-id="b093f-137">Maximum packet loss observed during the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b093f-138"><strong>BurstDensity</strong></span><span class="sxs-lookup"><span data-stu-id="b093f-138"><strong>BurstDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="b093f-139">10進数 (9, 4)</span><span class="sxs-lookup"><span data-stu-id="b093f-139">decimal(9,4)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="b093f-140">通話中に損失が発生した場合のパケット損失の平均密度。</span><span class="sxs-lookup"><span data-stu-id="b093f-140">Average density of packet Loss during bursts of losses during the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b093f-141"><strong>BurstDuration</strong></span><span class="sxs-lookup"><span data-stu-id="b093f-141"><strong>BurstDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="b093f-142">int</span><span class="sxs-lookup"><span data-stu-id="b093f-142">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="b093f-143">通話中に損失が発生したときのパケット損失の平均時間。</span><span class="sxs-lookup"><span data-stu-id="b093f-143">Average duration of packet loss during bursts of losses during the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b093f-144"><strong>BurstGapDensity</strong></span><span class="sxs-lookup"><span data-stu-id="b093f-144"><strong>BurstGapDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="b093f-145">10進数 (9, 4)</span><span class="sxs-lookup"><span data-stu-id="b093f-145">decimal(9,4)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="b093f-146">パケット損失のバースト間のパケット損失の平均密度。</span><span class="sxs-lookup"><span data-stu-id="b093f-146">Average density of packet loss during gaps between bursts of packet loss.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b093f-147"><strong>BurstGapDuration</strong></span><span class="sxs-lookup"><span data-stu-id="b093f-147"><strong>BurstGapDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="b093f-148">int</span><span class="sxs-lookup"><span data-stu-id="b093f-148">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="b093f-149">パケット損失のバーストの間の平均時間差。</span><span class="sxs-lookup"><span data-stu-id="b093f-149">Average duration of gaps between bursts of packet loss.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b093f-150"><strong>PacketUtilization</strong></span><span class="sxs-lookup"><span data-stu-id="b093f-150"><strong>PacketUtilization</strong></span></span></p></td>
<td><p><span data-ttu-id="b093f-151">Int</span><span class="sxs-lookup"><span data-stu-id="b093f-151">Int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="b093f-152">オーディオストリームのパケット数。</span><span class="sxs-lookup"><span data-stu-id="b093f-152">Packet count for the audio stream.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b093f-153"><strong>BandwidthEst</strong></span><span class="sxs-lookup"><span data-stu-id="b093f-153"><strong>BandwidthEst</strong></span></span></p></td>
<td><p><span data-ttu-id="b093f-154">Int</span><span class="sxs-lookup"><span data-stu-id="b093f-154">Int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="b093f-155">オーディオストリームの帯域幅の推定。</span><span class="sxs-lookup"><span data-stu-id="b093f-155">Bandwidth estimates for the audio stream.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b093f-156"><strong>DegradationAvg</strong></span><span class="sxs-lookup"><span data-stu-id="b093f-156"><strong>DegradationAvg</strong></span></span></p></td>
<td><p><span data-ttu-id="b093f-157">10進数 (3, 2)</span><span class="sxs-lookup"><span data-stu-id="b093f-157">decimal(3,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="b093f-158">電話全体のネットワーク MOS が低下します。</span><span class="sxs-lookup"><span data-stu-id="b093f-158">Network MOS Degradation for the whole call.</span></span> <span data-ttu-id="b093f-159">範囲は 0.0 ~ 5.0 です。</span><span class="sxs-lookup"><span data-stu-id="b093f-159">Range is 0.0 to 5.0.</span></span> <span data-ttu-id="b093f-160">このメトリックは、ジッタとパケット損失によってネットワーク MOS が削減された量を示します。</span><span class="sxs-lookup"><span data-stu-id="b093f-160">This metric shows the amount the Network MOS was reduced because of jitter and packet loss.</span></span> <span data-ttu-id="b093f-161">許容可能な品質には、0.5 未満の値を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b093f-161">For acceptable quality it should less than 0.5.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b093f-162"><strong>DegradationMax</strong></span><span class="sxs-lookup"><span data-stu-id="b093f-162"><strong>DegradationMax</strong></span></span></p></td>
<td><p><span data-ttu-id="b093f-163">10進数 (3, 2)</span><span class="sxs-lookup"><span data-stu-id="b093f-163">decimal(3,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="b093f-164">通話中の最大ネットワーク MOS の品質低下。</span><span class="sxs-lookup"><span data-stu-id="b093f-164">Maximum Network MOS degradation during the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b093f-165"><strong>DegradationJitterAvg</strong></span><span class="sxs-lookup"><span data-stu-id="b093f-165"><strong>DegradationJitterAvg</strong></span></span></p></td>
<td><p><span data-ttu-id="b093f-166">10進数 (3, 2)</span><span class="sxs-lookup"><span data-stu-id="b093f-166">decimal(3,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="b093f-167">ジッターによるネットワーク MOS の低下。</span><span class="sxs-lookup"><span data-stu-id="b093f-167">Network MOS degradation caused by jitter.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b093f-168"><strong>DegradationPacketLossAvg</strong></span><span class="sxs-lookup"><span data-stu-id="b093f-168"><strong>DegradationPacketLossAvg</strong></span></span></p></td>
<td><p><span data-ttu-id="b093f-169">10進数 (3, 2)</span><span class="sxs-lookup"><span data-stu-id="b093f-169">decimal(3,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="b093f-170">パケット損失によるネットワーク MOS の低下。</span><span class="sxs-lookup"><span data-stu-id="b093f-170">Network MOS degradation caused by packet loss.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b093f-171"><strong>AudioPayloadDescription</strong></span><span class="sxs-lookup"><span data-stu-id="b093f-171"><strong>AudioPayloadDescription</strong></span></span></p></td>
<td><p><span data-ttu-id="b093f-172">int</span><span class="sxs-lookup"><span data-stu-id="b093f-172">int</span></span></p></td>
<td><p><span data-ttu-id="b093f-173">外部</span><span class="sxs-lookup"><span data-stu-id="b093f-173">Foreign</span></span></p></td>
<td><p><span data-ttu-id="b093f-174">PayloadDescription テーブルから参照される、通話に使われるオーディオコーデック。</span><span class="sxs-lookup"><span data-stu-id="b093f-174">The audio Codec used for the call, referenced from PayloadDescription Table.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b093f-175"><strong>AudioSampleRate</strong></span><span class="sxs-lookup"><span data-stu-id="b093f-175"><strong>AudioSampleRate</strong></span></span></p></td>
<td><p><span data-ttu-id="b093f-176">int</span><span class="sxs-lookup"><span data-stu-id="b093f-176">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="b093f-177">オーディオストリームのサンプリングレート。</span><span class="sxs-lookup"><span data-stu-id="b093f-177">Sampling rate for the audio stream.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b093f-178"><strong>RoundTrip</strong></span><span class="sxs-lookup"><span data-stu-id="b093f-178"><strong>RoundTrip</strong></span></span></p></td>
<td><p><span data-ttu-id="b093f-179">int</span><span class="sxs-lookup"><span data-stu-id="b093f-179">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="b093f-180">RTCP の統計情報からのラウンドトリップ時間。</span><span class="sxs-lookup"><span data-stu-id="b093f-180">Round trip time from RTCP statistics.</span></span> <span data-ttu-id="b093f-181">許容可能な品質の場合は、100ms 未満にしてください。</span><span class="sxs-lookup"><span data-stu-id="b093f-181">For acceptable quality this should be less than 100ms.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b093f-182"><strong>RoundTripMax</strong></span><span class="sxs-lookup"><span data-stu-id="b093f-182"><strong>RoundTripMax</strong></span></span></p></td>
<td><p><span data-ttu-id="b093f-183">int</span><span class="sxs-lookup"><span data-stu-id="b093f-183">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="b093f-184">オーディオストリームの最大ラウンドトリップ時間。</span><span class="sxs-lookup"><span data-stu-id="b093f-184">Maximum round trip time for the audio stream.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b093f-185"><strong>OverallAvgNetworkMOS</strong></span><span class="sxs-lookup"><span data-stu-id="b093f-185"><strong>OverallAvgNetworkMOS</strong></span></span></p></td>
<td><p><span data-ttu-id="b093f-186">10進数 (3, 2)</span><span class="sxs-lookup"><span data-stu-id="b093f-186">decimal(3,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="b093f-187">通話の平均広帯域ネットワーク MOS。</span><span class="sxs-lookup"><span data-stu-id="b093f-187">Average wideband Network MOS for the call.</span></span> <span data-ttu-id="b093f-188">このメトリックは、使用されているパケット損失、ジッタ、およびコーデックによって異なります。</span><span class="sxs-lookup"><span data-stu-id="b093f-188">This metric depends on the packet loss, jitter, and codec used.</span></span> <span data-ttu-id="b093f-189">範囲は [1.0 から 5.0] になります。</span><span class="sxs-lookup"><span data-stu-id="b093f-189">Range is [1.0 to 5.0].</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b093f-190"><strong>OverallMinNetworkMOS</strong></span><span class="sxs-lookup"><span data-stu-id="b093f-190"><strong>OverallMinNetworkMOS</strong></span></span></p></td>
<td><p><span data-ttu-id="b093f-191">10進数 (3, 2)</span><span class="sxs-lookup"><span data-stu-id="b093f-191">decimal(3,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="b093f-192">通話の最小広帯域ネットワーク MOS。</span><span class="sxs-lookup"><span data-stu-id="b093f-192">The minimum wideband Network MOS for the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b093f-193"><strong>SendListenMOS</strong></span><span class="sxs-lookup"><span data-stu-id="b093f-193"><strong>SendListenMOS</strong></span></span></p></td>
<td><p><span data-ttu-id="b093f-194">10進数 (3, 2)</span><span class="sxs-lookup"><span data-stu-id="b093f-194">decimal(3,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="b093f-195">送信された音声の平均予測広帯域 MOS score (音声レベル、ノイズレベル、キャプチャデバイスの特性を含む)。</span><span class="sxs-lookup"><span data-stu-id="b093f-195">The average predicted wideband Listening MOS score for audio sent, including speech level, noise level and capture device characteristics.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b093f-196"><strong>SendListenMOSMin</strong></span><span class="sxs-lookup"><span data-stu-id="b093f-196"><strong>SendListenMOSMin</strong></span></span></p></td>
<td><p><span data-ttu-id="b093f-197">10進数 (3, 2)</span><span class="sxs-lookup"><span data-stu-id="b093f-197">decimal(3,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="b093f-198">通話の最小 SendListenMOS。</span><span class="sxs-lookup"><span data-stu-id="b093f-198">The minimum SendListenMOS for the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b093f-199"><strong>RecvListenMOS</strong></span><span class="sxs-lookup"><span data-stu-id="b093f-199"><strong>RecvListenMOS</strong></span></span></p></td>
<td><p><span data-ttu-id="b093f-200">10進数 (3, 2)</span><span class="sxs-lookup"><span data-stu-id="b093f-200">decimal(3,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="b093f-201">予測される平均広帯域は、ネットワークから受信した音声の MOS スコア (音声レベル、ノイズレベル、コーデック、ネットワーク条件、キャプチャデバイスの特性など) を対象としています。</span><span class="sxs-lookup"><span data-stu-id="b093f-201">The average predicted wideband Listening MOS score for audio received from the network including speech level, noise level, codec, network conditions and capture device characteristics.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b093f-202"><strong>RecvListenMOSMin</strong></span><span class="sxs-lookup"><span data-stu-id="b093f-202"><strong>RecvListenMOSMin</strong></span></span></p></td>
<td><p><span data-ttu-id="b093f-203">10進数 (3, 2)</span><span class="sxs-lookup"><span data-stu-id="b093f-203">decimal(3,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="b093f-204">通話の最小 RecvListenMOS。</span><span class="sxs-lookup"><span data-stu-id="b093f-204">The minimum RecvListenMOS for the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b093f-205"><strong>AudioFECUsed</strong></span><span class="sxs-lookup"><span data-stu-id="b093f-205"><strong>AudioFECUsed</strong></span></span></p></td>
<td><p><span data-ttu-id="b093f-206">bit</span><span class="sxs-lookup"><span data-stu-id="b093f-206">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="b093f-207">通話にオーディオ FEC が使用されたかどうかを示すフラグ。</span><span class="sxs-lookup"><span data-stu-id="b093f-207">Flag indicating if audio FEC was used for the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b093f-208"><strong>RatioConcealedSamplesAvg</strong></span><span class="sxs-lookup"><span data-stu-id="b093f-208"><strong>RatioConcealedSamplesAvg</strong></span></span></p></td>
<td><p><span data-ttu-id="b093f-209">10進数 (5, 2)</span><span class="sxs-lookup"><span data-stu-id="b093f-209">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="b093f-210">オーディオの修復によって発生した、一般的なサンプルの平均比率。</span><span class="sxs-lookup"><span data-stu-id="b093f-210">Average ratio of concealed samples generated by audio healing to typical samples.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b093f-211"><strong>RatioStretchedSamplesAvg</strong></span><span class="sxs-lookup"><span data-stu-id="b093f-211"><strong>RatioStretchedSamplesAvg</strong></span></span></p></td>
<td><p><span data-ttu-id="b093f-212">10進数 (5, 2)</span><span class="sxs-lookup"><span data-stu-id="b093f-212">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="b093f-213">オーディオ修復によって生成された、一般的なサンプルの平均比率。</span><span class="sxs-lookup"><span data-stu-id="b093f-213">Average ratio of stretched samples generated by audio healing to typical samples.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b093f-214"><strong>RatioCompressedSamplesAvg</strong></span><span class="sxs-lookup"><span data-stu-id="b093f-214"><strong>RatioCompressedSamplesAvg</strong></span></span></p></td>
<td><p><span data-ttu-id="b093f-215">10進数 (5, 2)</span><span class="sxs-lookup"><span data-stu-id="b093f-215">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="b093f-216">オーディオの修復によって生成された、一般的なサンプルの圧縮サンプルの平均比率。</span><span class="sxs-lookup"><span data-stu-id="b093f-216">Average ratio of compressed samples generated by audio healing to typical samples.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b093f-217"><strong>トラフィック</strong></span><span class="sxs-lookup"><span data-stu-id="b093f-217"><strong>Inbound</strong></span></span></p></td>
<td><p><span data-ttu-id="b093f-218">bit</span><span class="sxs-lookup"><span data-stu-id="b093f-218">bit</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="b093f-219">受信側のストリームデータが受信されます。</span><span class="sxs-lookup"><span data-stu-id="b093f-219">Stream data on receiver side is received.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b093f-220"><strong>発信</strong></span><span class="sxs-lookup"><span data-stu-id="b093f-220"><strong>Outbound</strong></span></span></p></td>
<td><p><span data-ttu-id="b093f-221">bit</span><span class="sxs-lookup"><span data-stu-id="b093f-221">bit</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="b093f-222">送信側のストリームデータが受信されます。</span><span class="sxs-lookup"><span data-stu-id="b093f-222">Stream data on sender side is received.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b093f-223"><strong>SenderIsCallerPAI</strong></span><span class="sxs-lookup"><span data-stu-id="b093f-223"><strong>SenderIsCallerPAI</strong></span></span></p></td>
<td><p><span data-ttu-id="b093f-224">bit</span><span class="sxs-lookup"><span data-stu-id="b093f-224">bit</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="b093f-225">1は、ストリームの方向を呼び出し元から呼び出し先に転送することを意味します。</span><span class="sxs-lookup"><span data-stu-id="b093f-225">1 means the stream direction is from the caller to the callee.</span></span></p>
<p><span data-ttu-id="b093f-226">0は、ストリームの方向を呼び出し元から呼び出し元に転送します。</span><span class="sxs-lookup"><span data-stu-id="b093f-226">0 means the stream direction is from the callee to the caller.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b093f-227"><strong>JitterInterArrivalSD</strong></span><span class="sxs-lookup"><span data-stu-id="b093f-227"><strong>JitterInterArrivalSD</strong></span></span></p></td>
<td><p><span data-ttu-id="b093f-228">float</span><span class="sxs-lookup"><span data-stu-id="b093f-228">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="b093f-229">ジッタの到着時刻の標準偏差。</span><span class="sxs-lookup"><span data-stu-id="b093f-229">Standard deviation for jitter arrival times.</span></span></p>
<p><span data-ttu-id="b093f-230">この列は Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="b093f-230">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b093f-231"><strong>ConcealRatioMax</strong></span><span class="sxs-lookup"><span data-stu-id="b093f-231"><strong>ConcealRatioMax</strong></span></span></p></td>
<td><p><span data-ttu-id="b093f-232">float</span><span class="sxs-lookup"><span data-stu-id="b093f-232">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="b093f-233">Healer によって隠されているパケットの最大比率。</span><span class="sxs-lookup"><span data-stu-id="b093f-233">Maximum ratio of packets concealed by the healer.</span></span></p>
<p><span data-ttu-id="b093f-234">この列は Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="b093f-234">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b093f-235"><strong>ConcealRatioSD</strong></span><span class="sxs-lookup"><span data-stu-id="b093f-235"><strong>ConcealRatioSD</strong></span></span></p></td>
<td><p><span data-ttu-id="b093f-236">float</span><span class="sxs-lookup"><span data-stu-id="b093f-236">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="b093f-237">Healer によって隠されているパケットの比率の標準偏差。</span><span class="sxs-lookup"><span data-stu-id="b093f-237">Standard deviation for the ratio of packets concealed by the healer.</span></span></p>
<p><span data-ttu-id="b093f-238">この列は Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="b093f-238">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b093f-239"><strong>HealerPacketDropRatio</strong></span><span class="sxs-lookup"><span data-stu-id="b093f-239"><strong>HealerPacketDropRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="b093f-240">float</span><span class="sxs-lookup"><span data-stu-id="b093f-240">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="b093f-241">受信したパケットの合計数と比較して、healer によってドロップされたパケットの比率。</span><span class="sxs-lookup"><span data-stu-id="b093f-241">Ratio of packets dropped by the healer compared to the total number of packets received.</span></span></p>
<p><span data-ttu-id="b093f-242">この列は Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="b093f-242">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b093f-243"><strong>HealerFECPacketUsedRatio</strong></span><span class="sxs-lookup"><span data-stu-id="b093f-243"><strong>HealerFECPacketUsedRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="b093f-244">float</span><span class="sxs-lookup"><span data-stu-id="b093f-244">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="b093f-245">受信したパケットの合計数と比較した、使用された転送エラー修正パケットの比率。</span><span class="sxs-lookup"><span data-stu-id="b093f-245">Ratio of used forward error correction packets compared to the total number of packets received.</span></span></p>
<p><span data-ttu-id="b093f-246">この列は Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="b093f-246">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b093f-247"><strong>MaxCompressedSamples</strong></span><span class="sxs-lookup"><span data-stu-id="b093f-247"><strong>MaxCompressedSamples</strong></span></span></p></td>
<td><p><span data-ttu-id="b093f-248">float</span><span class="sxs-lookup"><span data-stu-id="b093f-248">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="b093f-249">Healer によって圧縮されたオーディオパケットの最大数。</span><span class="sxs-lookup"><span data-stu-id="b093f-249">Maximum number of audio packets that were compressed by the healer.</span></span></p>
<p><span data-ttu-id="b093f-250">この列は Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="b093f-250">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b093f-251"><strong>LossCongestionPercent</strong></span><span class="sxs-lookup"><span data-stu-id="b093f-251"><strong>LossCongestionPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="b093f-252">float</span><span class="sxs-lookup"><span data-stu-id="b093f-252">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="b093f-253">通話が切断された輻輳状態であった時間の割合を示します。</span><span class="sxs-lookup"><span data-stu-id="b093f-253">Indicates the percentage of the time when the call was in a loss congestion state.</span></span></p>
<p><span data-ttu-id="b093f-254">この列は Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="b093f-254">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b093f-255"><strong>DelayCongestionPercent</strong></span><span class="sxs-lookup"><span data-stu-id="b093f-255"><strong>DelayCongestionPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="b093f-256">float</span><span class="sxs-lookup"><span data-stu-id="b093f-256">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="b093f-257">ネットワークパケットが遅延したために発生した、通話の割合を示します。</span><span class="sxs-lookup"><span data-stu-id="b093f-257">Indicates the percentage of the call during which congestion was caused by the delayed arrival of network packets.</span></span></p>
<p><span data-ttu-id="b093f-258">この列は Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="b093f-258">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b093f-259"><strong>ContentionDetectedPercent</strong></span><span class="sxs-lookup"><span data-stu-id="b093f-259"><strong>ContentionDetectedPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="b093f-260">float</span><span class="sxs-lookup"><span data-stu-id="b093f-260">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="b093f-261">通話がネットワークリソースに対して競合した時間の割合を示します。</span><span class="sxs-lookup"><span data-stu-id="b093f-261">Indicates the percentage of the time when the call was competing for network resources.</span></span></p>
<p><span data-ttu-id="b093f-262">この列は Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="b093f-262">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b093f-263"><strong>BandwidthEstMin</strong></span><span class="sxs-lookup"><span data-stu-id="b093f-263"><strong>BandwidthEstMin</strong></span></span></p></td>
<td><p><span data-ttu-id="b093f-264">int</span><span class="sxs-lookup"><span data-stu-id="b093f-264">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="b093f-265">通話中の最小帯域幅推定値。</span><span class="sxs-lookup"><span data-stu-id="b093f-265">Minimum amount of bandwidth estimation measured during the call.</span></span></p>
<p><span data-ttu-id="b093f-266">この列は Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="b093f-266">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b093f-267"><strong>BandwidthEstMax</strong></span><span class="sxs-lookup"><span data-stu-id="b093f-267"><strong>BandwidthEstMax</strong></span></span></p></td>
<td><p><span data-ttu-id="b093f-268">int</span><span class="sxs-lookup"><span data-stu-id="b093f-268">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="b093f-269">通話中に測定された帯域幅推定の最大量。</span><span class="sxs-lookup"><span data-stu-id="b093f-269">Maximum amount of bandwidth estimation measured during the call.</span></span></p>
<p><span data-ttu-id="b093f-270">この列は Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="b093f-270">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b093f-271"><strong>BandwidthEstStdDev</strong></span><span class="sxs-lookup"><span data-stu-id="b093f-271"><strong>BandwidthEstStdDev</strong></span></span></p></td>
<td><p><span data-ttu-id="b093f-272">int</span><span class="sxs-lookup"><span data-stu-id="b093f-272">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="b093f-273">通話中に測定された帯域幅推定の標準偏差。</span><span class="sxs-lookup"><span data-stu-id="b093f-273">Standard deviation of the bandwidth estimation measured during the call.</span></span></p>
<p><span data-ttu-id="b093f-274">この列は Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="b093f-274">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b093f-275"><strong>BandwidthEstAvge</strong></span><span class="sxs-lookup"><span data-stu-id="b093f-275"><strong>BandwidthEstAvge</strong></span></span></p></td>
<td><p><span data-ttu-id="b093f-276">int</span><span class="sxs-lookup"><span data-stu-id="b093f-276">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="b093f-277">通話中に計測された平均帯域幅推定量。</span><span class="sxs-lookup"><span data-stu-id="b093f-277">Average amount of bandwidth estimation measured during the call.</span></span></p>
<p><span data-ttu-id="b093f-278">この列は Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="b093f-278">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b093f-279"><strong>RelativeOneWayTotal</strong></span><span class="sxs-lookup"><span data-stu-id="b093f-279"><strong>RelativeOneWayTotal</strong></span></span></p></td>
<td><p><span data-ttu-id="b093f-280">float</span><span class="sxs-lookup"><span data-stu-id="b093f-280">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="b093f-281">一方向の待機時間の合計。</span><span class="sxs-lookup"><span data-stu-id="b093f-281">Total amount of one-way latency.</span></span> <span data-ttu-id="b093f-282">相対的な一方向の待ち時間は、クライアントとサーバーの間の遅延を測定します。</span><span class="sxs-lookup"><span data-stu-id="b093f-282">Relative one-way latency measures the delay between the client and the server.</span></span></p>
<p><span data-ttu-id="b093f-283">この列は Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="b093f-283">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b093f-284"><strong>RelativeOneWayAverage</strong></span><span class="sxs-lookup"><span data-stu-id="b093f-284"><strong>RelativeOneWayAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="b093f-285">float</span><span class="sxs-lookup"><span data-stu-id="b093f-285">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="b093f-286">一方向の待ち時間の平均値。</span><span class="sxs-lookup"><span data-stu-id="b093f-286">Average amount of one-way latency.</span></span> <span data-ttu-id="b093f-287">相対的な一方向の待ち時間は、クライアントとサーバーの間の遅延を測定します。</span><span class="sxs-lookup"><span data-stu-id="b093f-287">Relative one-way latency measures the delay between the client and the server.</span></span></p>
<p><span data-ttu-id="b093f-288">この列は Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="b093f-288">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b093f-289"><strong>RelativeOneWayMax</strong></span><span class="sxs-lookup"><span data-stu-id="b093f-289"><strong>RelativeOneWayMax</strong></span></span></p></td>
<td><p><span data-ttu-id="b093f-290">float</span><span class="sxs-lookup"><span data-stu-id="b093f-290">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="b093f-291">一方向の待機時間の上限。</span><span class="sxs-lookup"><span data-stu-id="b093f-291">Maximum amount of one-way latency.</span></span> <span data-ttu-id="b093f-292">相対的な一方向の待ち時間は、クライアントとサーバーの間の遅延を測定します。</span><span class="sxs-lookup"><span data-stu-id="b093f-292">Relative one-way latency measures the delay between the client and the server.</span></span></p>
<p><span data-ttu-id="b093f-293">この列は Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="b093f-293">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b093f-294"><strong>RelativeOneWayBurstOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="b093f-294"><strong>RelativeOneWayBurstOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="b093f-295">int</span><span class="sxs-lookup"><span data-stu-id="b093f-295">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="b093f-296">1方向のバースト発生の合計。</span><span class="sxs-lookup"><span data-stu-id="b093f-296">Total one-way burst occurrences.</span></span> <span data-ttu-id="b093f-297">"Bursty" 伝送とは、安定したストリームと比べて予期しないバーストでデータが流れる伝送です。</span><span class="sxs-lookup"><span data-stu-id="b093f-297">A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream.</span></span> <span data-ttu-id="b093f-298">このメトリックは、クライアントとサーバー間のデータフローを計測します。</span><span class="sxs-lookup"><span data-stu-id="b093f-298">This metric measures data flow between the client and the server.</span></span></p>
<p><span data-ttu-id="b093f-299">この列は Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="b093f-299">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b093f-300"><strong>RelativeOneWayBurstDensity</strong></span><span class="sxs-lookup"><span data-stu-id="b093f-300"><strong>RelativeOneWayBurstDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="b093f-301">float</span><span class="sxs-lookup"><span data-stu-id="b093f-301">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="b093f-302">全体的な1方向バースト密度。</span><span class="sxs-lookup"><span data-stu-id="b093f-302">Total one-way burst density.</span></span> <span data-ttu-id="b093f-303">"Bursty" 伝送とは、安定したストリームと比べて予期しないバーストでデータが流れる伝送です。</span><span class="sxs-lookup"><span data-stu-id="b093f-303">A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream.</span></span> <span data-ttu-id="b093f-304">このメトリックは、クライアントとサーバー間のデータフローを計測します。</span><span class="sxs-lookup"><span data-stu-id="b093f-304">This metric measures data flow between the client and the server.</span></span></p>
<p><span data-ttu-id="b093f-305">この列は Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="b093f-305">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b093f-306"><strong>RelativeOneWayBurstDuration</strong></span><span class="sxs-lookup"><span data-stu-id="b093f-306"><strong>RelativeOneWayBurstDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="b093f-307">float</span><span class="sxs-lookup"><span data-stu-id="b093f-307">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="b093f-308">一方向のバースト期間の合計。</span><span class="sxs-lookup"><span data-stu-id="b093f-308">Total one-way burst duration.</span></span> <span data-ttu-id="b093f-309">"Bursty" 伝送とは、安定したストリームと比べて予期しないバーストでデータが流れる伝送です。</span><span class="sxs-lookup"><span data-stu-id="b093f-309">A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream.</span></span> <span data-ttu-id="b093f-310">このメトリックは、クライアントとサーバー間のデータフローを計測します。</span><span class="sxs-lookup"><span data-stu-id="b093f-310">This metric measures data flow between the client and the server.</span></span></p>
<p><span data-ttu-id="b093f-311">この列は Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="b093f-311">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b093f-312"><strong>RelativeOneWayGapOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="b093f-312"><strong>RelativeOneWayGapOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="b093f-313">int</span><span class="sxs-lookup"><span data-stu-id="b093f-313">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="b093f-314">一方向のギャップ出現の合計。</span><span class="sxs-lookup"><span data-stu-id="b093f-314">Total one-way gap occurrences.</span></span> <span data-ttu-id="b093f-315">"Bursty" 伝送とは、安定したストリームではなく、予期しないバーストでデータが流れる伝送です。ギャップは、このようなバーストの間の遅延を示します。</span><span class="sxs-lookup"><span data-stu-id="b093f-315">A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream; gaps indicate delays between these bursts.</span></span> <span data-ttu-id="b093f-316">このメトリックは、クライアントとサーバー間のデータフローを計測します。</span><span class="sxs-lookup"><span data-stu-id="b093f-316">This metric measures data flow between the client and the server.</span></span></p>
<p><span data-ttu-id="b093f-317">この列は Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="b093f-317">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b093f-318"><strong>RelativeOneWayGapDensity</strong></span><span class="sxs-lookup"><span data-stu-id="b093f-318"><strong>RelativeOneWayGapDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="b093f-319">float</span><span class="sxs-lookup"><span data-stu-id="b093f-319">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="b093f-320">一方向のギャップの密度の合計。</span><span class="sxs-lookup"><span data-stu-id="b093f-320">Total one-way gap density.</span></span> <span data-ttu-id="b093f-321">"Bursty" 伝送とは、安定したストリームではなく、予期しないバーストでデータが流れる伝送です。ギャップは、このようなバーストの間の遅延を示します。</span><span class="sxs-lookup"><span data-stu-id="b093f-321">A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream; gaps indicate delays between these bursts.</span></span> <span data-ttu-id="b093f-322">このメトリックは、クライアントとサーバー間のデータフローを計測します。</span><span class="sxs-lookup"><span data-stu-id="b093f-322">This metric measures data flow between the client and the server.</span></span></p>
<p><span data-ttu-id="b093f-323">この列は Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="b093f-323">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b093f-324"><strong>RelativeOneWayGapDuration</strong></span><span class="sxs-lookup"><span data-stu-id="b093f-324"><strong>RelativeOneWayGapDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="b093f-325">float</span><span class="sxs-lookup"><span data-stu-id="b093f-325">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="b093f-326">一方向のギャップ期間の合計。</span><span class="sxs-lookup"><span data-stu-id="b093f-326">Total one-way gap duration.</span></span> <span data-ttu-id="b093f-327">"Bursty" 伝送とは、安定したストリームではなく、予期しないバーストでデータが流れる伝送です。ギャップは、このようなバーストの間の遅延を示します。</span><span class="sxs-lookup"><span data-stu-id="b093f-327">A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream; gaps indicate delays between these bursts.</span></span> <span data-ttu-id="b093f-328">このメトリックは、クライアントとサーバー間のデータフローを計測します。</span><span class="sxs-lookup"><span data-stu-id="b093f-328">This metric measures data flow between the client and the server.</span></span></p>
<p><span data-ttu-id="b093f-329">この列は Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="b093f-329">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b093f-330"><strong>DecodeStereoPercent</strong></span><span class="sxs-lookup"><span data-stu-id="b093f-330"><strong>DecodeStereoPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="b093f-331">float</span><span class="sxs-lookup"><span data-stu-id="b093f-331">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="b093f-332">ステレオとしてデコードされた通話のパーセンテージ。</span><span class="sxs-lookup"><span data-stu-id="b093f-332">Percentage of the call decoded as stereo.</span></span></p>
<p><span data-ttu-id="b093f-333">この列は Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="b093f-333">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b093f-334"><strong>AecRenderStereoPercent</strong></span><span class="sxs-lookup"><span data-stu-id="b093f-334"><strong>AecRenderStereoPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="b093f-335">float</span><span class="sxs-lookup"><span data-stu-id="b093f-335">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="b093f-336">アコースティックエコーキャンセラによってステレオとしてレンダリングされた通話の割合。</span><span class="sxs-lookup"><span data-stu-id="b093f-336">Percentage of the call rendered as stereo by the acoustic echo canceller.</span></span></p>
<p><span data-ttu-id="b093f-337">この列は Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="b093f-337">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b093f-338"><strong>AudioPostFECPLR</strong></span><span class="sxs-lookup"><span data-stu-id="b093f-338"><strong>AudioPostFECPLR</strong></span></span></p></td>
<td><p><span data-ttu-id="b093f-339">float</span><span class="sxs-lookup"><span data-stu-id="b093f-339">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="b093f-340">転送後のエラー訂正が適用された後のパケット損失率。</span><span class="sxs-lookup"><span data-stu-id="b093f-340">Packet loss rate after forward error correction has been applied.</span></span></p>
<p><span data-ttu-id="b093f-341">この列は Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="b093f-341">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b093f-342"><strong>EncodeStereoPercent</strong></span><span class="sxs-lookup"><span data-stu-id="b093f-342"><strong>EncodeStereoPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="b093f-343">float</span><span class="sxs-lookup"><span data-stu-id="b093f-343">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="b093f-344">ステレオとしてエンコードされた通話の割合。</span><span class="sxs-lookup"><span data-stu-id="b093f-344">Percentage of the call encoded as stereo.</span></span></p>
<p><span data-ttu-id="b093f-345">この列は Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="b093f-345">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b093f-346"><strong>AecCaptureStereoPercent</strong></span><span class="sxs-lookup"><span data-stu-id="b093f-346"><strong>AecCaptureStereoPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="b093f-347">float</span><span class="sxs-lookup"><span data-stu-id="b093f-347">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="b093f-348">アコースティックエコーキャンセラでステレオとしてキャプチャされた通話のパーセンテージ。</span><span class="sxs-lookup"><span data-stu-id="b093f-348">Percentage of the call captured as stereo by the acoustic echo canceller.</span></span></p>
<p><span data-ttu-id="b093f-349">この列は Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="b093f-349">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

