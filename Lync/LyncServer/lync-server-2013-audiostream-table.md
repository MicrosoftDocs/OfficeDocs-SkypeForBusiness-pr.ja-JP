---
title: 'Lync Server 2013: AudioStream テーブル'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: AudioStream table
ms:assetid: 49ccbbc3-2f73-45fc-80a6-e612535cbc10
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425961(v=OCS.15)
ms:contentKeyID: 48184077
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 97a8015bce118991b21b541faf588dd4d76ac784
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41738347"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="audiostream-table-in-lync-server-2013"></a><span data-ttu-id="fd35e-102">Lync Server 2013 の AudioStream テーブル</span><span class="sxs-lookup"><span data-stu-id="fd35e-102">AudioStream table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="fd35e-103">_**最終更新日:** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="fd35e-103">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="fd35e-104">各レコードは1つのオーディオストリームを表します。</span><span class="sxs-lookup"><span data-stu-id="fd35e-104">Each record represents one audio stream.</span></span> <span data-ttu-id="fd35e-105">通常、1つのオーディオメディアラインには2つのオーディオストリームが含まれています。</span><span class="sxs-lookup"><span data-stu-id="fd35e-105">One audio media line usually contains two audio streams.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="fd35e-106"><strong>列</strong></span><span class="sxs-lookup"><span data-stu-id="fd35e-106"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="fd35e-107"><strong>データ型</strong></span><span class="sxs-lookup"><span data-stu-id="fd35e-107"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="fd35e-108"><strong>キー/インデックス</strong></span><span class="sxs-lookup"><span data-stu-id="fd35e-108"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="fd35e-109"><strong>詳細</strong></span><span class="sxs-lookup"><span data-stu-id="fd35e-109"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="fd35e-110"><strong>ConferenceDateTime</strong></span><span class="sxs-lookup"><span data-stu-id="fd35e-110"><strong>ConferenceDateTime</strong></span></span></p></td>
<td><p><span data-ttu-id="fd35e-111">datetime</span><span class="sxs-lookup"><span data-stu-id="fd35e-111">datetime</span></span></p></td>
<td><p><span data-ttu-id="fd35e-112">Primary</span><span class="sxs-lookup"><span data-stu-id="fd35e-112">Primary</span></span></p></td>
<td><p><span data-ttu-id="fd35e-113"><a href="lync-server-2013-medialine-table.md">Lync Server 2013 の MediaLine テーブル</a>から参照されている。</span><span class="sxs-lookup"><span data-stu-id="fd35e-113">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fd35e-114"><strong>SessionSeq</strong></span><span class="sxs-lookup"><span data-stu-id="fd35e-114"><strong>SessionSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="fd35e-115">int</span><span class="sxs-lookup"><span data-stu-id="fd35e-115">int</span></span></p></td>
<td><p><span data-ttu-id="fd35e-116">Primary</span><span class="sxs-lookup"><span data-stu-id="fd35e-116">Primary</span></span></p></td>
<td><p><span data-ttu-id="fd35e-117"><a href="lync-server-2013-medialine-table.md">Lync Server 2013 の MediaLine テーブル</a>から参照されている。</span><span class="sxs-lookup"><span data-stu-id="fd35e-117">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fd35e-118"><strong>MediaLineLabel</strong></span><span class="sxs-lookup"><span data-stu-id="fd35e-118"><strong>MediaLineLabel</strong></span></span></p></td>
<td><p><span data-ttu-id="fd35e-119">tinyint</span><span class="sxs-lookup"><span data-stu-id="fd35e-119">tinyint</span></span></p></td>
<td><p><span data-ttu-id="fd35e-120">Primary</span><span class="sxs-lookup"><span data-stu-id="fd35e-120">Primary</span></span></p></td>
<td><p><span data-ttu-id="fd35e-121"><a href="lync-server-2013-medialine-table.md">Lync Server 2013 の MediaLine テーブル</a>から参照されている。</span><span class="sxs-lookup"><span data-stu-id="fd35e-121">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fd35e-122"><strong>StreamID</strong></span><span class="sxs-lookup"><span data-stu-id="fd35e-122"><strong>StreamID</strong></span></span></p></td>
<td><p><span data-ttu-id="fd35e-123">int</span><span class="sxs-lookup"><span data-stu-id="fd35e-123">int</span></span></p></td>
<td><p><span data-ttu-id="fd35e-124">Primary</span><span class="sxs-lookup"><span data-stu-id="fd35e-124">Primary</span></span></p></td>
<td><p><span data-ttu-id="fd35e-125">メディアライン内の一意の ID。</span><span class="sxs-lookup"><span data-stu-id="fd35e-125">Unique ID within a media line.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fd35e-126"><strong>JitterInterArrival</strong></span><span class="sxs-lookup"><span data-stu-id="fd35e-126"><strong>JitterInterArrival</strong></span></span></p></td>
<td><p><span data-ttu-id="fd35e-127">int</span><span class="sxs-lookup"><span data-stu-id="fd35e-127">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="fd35e-128">リアルタイム制御プロトコル (RTCP) の統計情報からの平均ネットワークジッター。</span><span class="sxs-lookup"><span data-stu-id="fd35e-128">Average network jitter from Real Time Control Protocol (RTCP) statistics.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fd35e-129"><strong>JitterInterArrivalMax</strong></span><span class="sxs-lookup"><span data-stu-id="fd35e-129"><strong>JitterInterArrivalMax</strong></span></span></p></td>
<td><p><span data-ttu-id="fd35e-130">int</span><span class="sxs-lookup"><span data-stu-id="fd35e-130">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="fd35e-131">通話中の最大ネットワークジッター。</span><span class="sxs-lookup"><span data-stu-id="fd35e-131">Maximum network jitter during the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fd35e-132"><strong>PacketLossRate</strong></span><span class="sxs-lookup"><span data-stu-id="fd35e-132"><strong>PacketLossRate</strong></span></span></p></td>
<td><p><span data-ttu-id="fd35e-133">10進数 (5, 4)</span><span class="sxs-lookup"><span data-stu-id="fd35e-133">decimal(5,4)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="fd35e-134">通話中の平均パケット損失率。</span><span class="sxs-lookup"><span data-stu-id="fd35e-134">Average packet loss rate during the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fd35e-135"><strong>PacketLossRateMax</strong></span><span class="sxs-lookup"><span data-stu-id="fd35e-135"><strong>PacketLossRateMax</strong></span></span></p></td>
<td><p><span data-ttu-id="fd35e-136">10進数 (5, 4)</span><span class="sxs-lookup"><span data-stu-id="fd35e-136">decimal(5,4)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="fd35e-137">通話中に発生したパケット損失の上限。</span><span class="sxs-lookup"><span data-stu-id="fd35e-137">Maximum packet loss observed during the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fd35e-138"><strong>BurstDensity</strong></span><span class="sxs-lookup"><span data-stu-id="fd35e-138"><strong>BurstDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="fd35e-139">10進数 (9, 4)</span><span class="sxs-lookup"><span data-stu-id="fd35e-139">decimal(9,4)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="fd35e-140">通話中に損失が発生した場合のパケット損失の平均密度。</span><span class="sxs-lookup"><span data-stu-id="fd35e-140">Average density of packet Loss during bursts of losses during the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fd35e-141"><strong>BurstDuration</strong></span><span class="sxs-lookup"><span data-stu-id="fd35e-141"><strong>BurstDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="fd35e-142">int</span><span class="sxs-lookup"><span data-stu-id="fd35e-142">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="fd35e-143">通話中に損失が発生したときのパケット損失の平均時間。</span><span class="sxs-lookup"><span data-stu-id="fd35e-143">Average duration of packet loss during bursts of losses during the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fd35e-144"><strong>BurstGapDensity</strong></span><span class="sxs-lookup"><span data-stu-id="fd35e-144"><strong>BurstGapDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="fd35e-145">10進数 (9, 4)</span><span class="sxs-lookup"><span data-stu-id="fd35e-145">decimal(9,4)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="fd35e-146">パケット損失のバースト間のパケット損失の平均密度。</span><span class="sxs-lookup"><span data-stu-id="fd35e-146">Average density of packet loss during gaps between bursts of packet loss.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fd35e-147"><strong>BurstGapDuration</strong></span><span class="sxs-lookup"><span data-stu-id="fd35e-147"><strong>BurstGapDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="fd35e-148">int</span><span class="sxs-lookup"><span data-stu-id="fd35e-148">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="fd35e-149">パケット損失のバーストの間の平均時間差。</span><span class="sxs-lookup"><span data-stu-id="fd35e-149">Average duration of gaps between bursts of packet loss.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fd35e-150"><strong>PacketUtilization</strong></span><span class="sxs-lookup"><span data-stu-id="fd35e-150"><strong>PacketUtilization</strong></span></span></p></td>
<td><p><span data-ttu-id="fd35e-151">Int</span><span class="sxs-lookup"><span data-stu-id="fd35e-151">Int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="fd35e-152">オーディオストリームのパケット数。</span><span class="sxs-lookup"><span data-stu-id="fd35e-152">Packet count for the audio stream.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fd35e-153"><strong>BandwidthEst</strong></span><span class="sxs-lookup"><span data-stu-id="fd35e-153"><strong>BandwidthEst</strong></span></span></p></td>
<td><p><span data-ttu-id="fd35e-154">Int</span><span class="sxs-lookup"><span data-stu-id="fd35e-154">Int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="fd35e-155">オーディオストリームの帯域幅の推定。</span><span class="sxs-lookup"><span data-stu-id="fd35e-155">Bandwidth estimates for the audio stream.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fd35e-156"><strong>DegradationAvg</strong></span><span class="sxs-lookup"><span data-stu-id="fd35e-156"><strong>DegradationAvg</strong></span></span></p></td>
<td><p><span data-ttu-id="fd35e-157">10進数 (3, 2)</span><span class="sxs-lookup"><span data-stu-id="fd35e-157">decimal(3,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="fd35e-158">電話全体のネットワーク MOS が低下します。</span><span class="sxs-lookup"><span data-stu-id="fd35e-158">Network MOS Degradation for the whole call.</span></span> <span data-ttu-id="fd35e-159">範囲は 0.0 ~ 5.0 です。</span><span class="sxs-lookup"><span data-stu-id="fd35e-159">Range is 0.0 to 5.0.</span></span> <span data-ttu-id="fd35e-160">このメトリックは、ジッタとパケット損失によってネットワーク MOS が削減された量を示します。</span><span class="sxs-lookup"><span data-stu-id="fd35e-160">This metric shows the amount the Network MOS was reduced because of jitter and packet loss.</span></span> <span data-ttu-id="fd35e-161">許容可能な品質には、0.5 未満の値を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="fd35e-161">For acceptable quality it should less than 0.5.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fd35e-162"><strong>DegradationMax</strong></span><span class="sxs-lookup"><span data-stu-id="fd35e-162"><strong>DegradationMax</strong></span></span></p></td>
<td><p><span data-ttu-id="fd35e-163">10進数 (3, 2)</span><span class="sxs-lookup"><span data-stu-id="fd35e-163">decimal(3,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="fd35e-164">通話中の最大ネットワーク MOS の品質低下。</span><span class="sxs-lookup"><span data-stu-id="fd35e-164">Maximum Network MOS degradation during the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fd35e-165"><strong>DegradationJitterAvg</strong></span><span class="sxs-lookup"><span data-stu-id="fd35e-165"><strong>DegradationJitterAvg</strong></span></span></p></td>
<td><p><span data-ttu-id="fd35e-166">10進数 (3, 2)</span><span class="sxs-lookup"><span data-stu-id="fd35e-166">decimal(3,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="fd35e-167">ジッターによるネットワーク MOS の低下。</span><span class="sxs-lookup"><span data-stu-id="fd35e-167">Network MOS degradation caused by jitter.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fd35e-168"><strong>DegradationPacketLossAvg</strong></span><span class="sxs-lookup"><span data-stu-id="fd35e-168"><strong>DegradationPacketLossAvg</strong></span></span></p></td>
<td><p><span data-ttu-id="fd35e-169">10進数 (3, 2)</span><span class="sxs-lookup"><span data-stu-id="fd35e-169">decimal(3,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="fd35e-170">パケット損失によるネットワーク MOS の低下。</span><span class="sxs-lookup"><span data-stu-id="fd35e-170">Network MOS degradation caused by packet loss.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fd35e-171"><strong>AudioPayloadDescription</strong></span><span class="sxs-lookup"><span data-stu-id="fd35e-171"><strong>AudioPayloadDescription</strong></span></span></p></td>
<td><p><span data-ttu-id="fd35e-172">int</span><span class="sxs-lookup"><span data-stu-id="fd35e-172">int</span></span></p></td>
<td><p><span data-ttu-id="fd35e-173">外部</span><span class="sxs-lookup"><span data-stu-id="fd35e-173">Foreign</span></span></p></td>
<td><p><span data-ttu-id="fd35e-174">PayloadDescription テーブルから参照される、通話に使われるオーディオコーデック。</span><span class="sxs-lookup"><span data-stu-id="fd35e-174">The audio Codec used for the call, referenced from PayloadDescription Table.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fd35e-175"><strong>AudioSampleRate</strong></span><span class="sxs-lookup"><span data-stu-id="fd35e-175"><strong>AudioSampleRate</strong></span></span></p></td>
<td><p><span data-ttu-id="fd35e-176">int</span><span class="sxs-lookup"><span data-stu-id="fd35e-176">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="fd35e-177">オーディオストリームのサンプリングレート。</span><span class="sxs-lookup"><span data-stu-id="fd35e-177">Sampling rate for the audio stream.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fd35e-178"><strong>RoundTrip</strong></span><span class="sxs-lookup"><span data-stu-id="fd35e-178"><strong>RoundTrip</strong></span></span></p></td>
<td><p><span data-ttu-id="fd35e-179">int</span><span class="sxs-lookup"><span data-stu-id="fd35e-179">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="fd35e-180">RTCP の統計情報からのラウンドトリップ時間。</span><span class="sxs-lookup"><span data-stu-id="fd35e-180">Round trip time from RTCP statistics.</span></span> <span data-ttu-id="fd35e-181">許容可能な品質の場合は、100ms 未満にしてください。</span><span class="sxs-lookup"><span data-stu-id="fd35e-181">For acceptable quality this should be less than 100ms.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fd35e-182"><strong>RoundTripMax</strong></span><span class="sxs-lookup"><span data-stu-id="fd35e-182"><strong>RoundTripMax</strong></span></span></p></td>
<td><p><span data-ttu-id="fd35e-183">int</span><span class="sxs-lookup"><span data-stu-id="fd35e-183">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="fd35e-184">オーディオストリームの最大ラウンドトリップ時間。</span><span class="sxs-lookup"><span data-stu-id="fd35e-184">Maximum round trip time for the audio stream.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fd35e-185"><strong>OverallAvgNetworkMOS</strong></span><span class="sxs-lookup"><span data-stu-id="fd35e-185"><strong>OverallAvgNetworkMOS</strong></span></span></p></td>
<td><p><span data-ttu-id="fd35e-186">10進数 (3, 2)</span><span class="sxs-lookup"><span data-stu-id="fd35e-186">decimal(3,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="fd35e-187">通話の平均広帯域ネットワーク MOS。</span><span class="sxs-lookup"><span data-stu-id="fd35e-187">Average wideband Network MOS for the call.</span></span> <span data-ttu-id="fd35e-188">このメトリックは、使用されているパケット損失、ジッタ、およびコーデックによって異なります。</span><span class="sxs-lookup"><span data-stu-id="fd35e-188">This metric depends on the packet loss, jitter, and codec used.</span></span> <span data-ttu-id="fd35e-189">範囲は [1.0 から 5.0] になります。</span><span class="sxs-lookup"><span data-stu-id="fd35e-189">Range is [1.0 to 5.0].</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fd35e-190"><strong>OverallMinNetworkMOS</strong></span><span class="sxs-lookup"><span data-stu-id="fd35e-190"><strong>OverallMinNetworkMOS</strong></span></span></p></td>
<td><p><span data-ttu-id="fd35e-191">10進数 (3, 2)</span><span class="sxs-lookup"><span data-stu-id="fd35e-191">decimal(3,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="fd35e-192">通話の最小広帯域ネットワーク MOS。</span><span class="sxs-lookup"><span data-stu-id="fd35e-192">The minimum wideband Network MOS for the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fd35e-193"><strong>SendListenMOS</strong></span><span class="sxs-lookup"><span data-stu-id="fd35e-193"><strong>SendListenMOS</strong></span></span></p></td>
<td><p><span data-ttu-id="fd35e-194">10進数 (3, 2)</span><span class="sxs-lookup"><span data-stu-id="fd35e-194">decimal(3,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="fd35e-195">送信された音声の平均予測広帯域 MOS score (音声レベル、ノイズレベル、キャプチャデバイスの特性を含む)。</span><span class="sxs-lookup"><span data-stu-id="fd35e-195">The average predicted wideband Listening MOS score for audio sent, including speech level, noise level and capture device characteristics.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fd35e-196"><strong>SendListenMOSMin</strong></span><span class="sxs-lookup"><span data-stu-id="fd35e-196"><strong>SendListenMOSMin</strong></span></span></p></td>
<td><p><span data-ttu-id="fd35e-197">10進数 (3, 2)</span><span class="sxs-lookup"><span data-stu-id="fd35e-197">decimal(3,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="fd35e-198">通話の最小 SendListenMOS。</span><span class="sxs-lookup"><span data-stu-id="fd35e-198">The minimum SendListenMOS for the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fd35e-199"><strong>RecvListenMOS</strong></span><span class="sxs-lookup"><span data-stu-id="fd35e-199"><strong>RecvListenMOS</strong></span></span></p></td>
<td><p><span data-ttu-id="fd35e-200">10進数 (3, 2)</span><span class="sxs-lookup"><span data-stu-id="fd35e-200">decimal(3,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="fd35e-201">予測される平均広帯域は、ネットワークから受信した音声の MOS スコア (音声レベル、ノイズレベル、コーデック、ネットワーク条件、キャプチャデバイスの特性など) を対象としています。</span><span class="sxs-lookup"><span data-stu-id="fd35e-201">The average predicted wideband Listening MOS score for audio received from the network including speech level, noise level, codec, network conditions and capture device characteristics.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fd35e-202"><strong>RecvListenMOSMin</strong></span><span class="sxs-lookup"><span data-stu-id="fd35e-202"><strong>RecvListenMOSMin</strong></span></span></p></td>
<td><p><span data-ttu-id="fd35e-203">10進数 (3, 2)</span><span class="sxs-lookup"><span data-stu-id="fd35e-203">decimal(3,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="fd35e-204">通話の最小 RecvListenMOS。</span><span class="sxs-lookup"><span data-stu-id="fd35e-204">The minimum RecvListenMOS for the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fd35e-205"><strong>AudioFECUsed</strong></span><span class="sxs-lookup"><span data-stu-id="fd35e-205"><strong>AudioFECUsed</strong></span></span></p></td>
<td><p><span data-ttu-id="fd35e-206">bit</span><span class="sxs-lookup"><span data-stu-id="fd35e-206">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="fd35e-207">通話にオーディオ FEC が使用されたかどうかを示すフラグ。</span><span class="sxs-lookup"><span data-stu-id="fd35e-207">Flag indicating if audio FEC was used for the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fd35e-208"><strong>RatioConcealedSamplesAvg</strong></span><span class="sxs-lookup"><span data-stu-id="fd35e-208"><strong>RatioConcealedSamplesAvg</strong></span></span></p></td>
<td><p><span data-ttu-id="fd35e-209">10進数 (5, 2)</span><span class="sxs-lookup"><span data-stu-id="fd35e-209">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="fd35e-210">オーディオの修復によって発生した、一般的なサンプルの平均比率。</span><span class="sxs-lookup"><span data-stu-id="fd35e-210">Average ratio of concealed samples generated by audio healing to typical samples.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fd35e-211"><strong>RatioStretchedSamplesAvg</strong></span><span class="sxs-lookup"><span data-stu-id="fd35e-211"><strong>RatioStretchedSamplesAvg</strong></span></span></p></td>
<td><p><span data-ttu-id="fd35e-212">10進数 (5, 2)</span><span class="sxs-lookup"><span data-stu-id="fd35e-212">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="fd35e-213">オーディオ修復によって生成された、一般的なサンプルの平均比率。</span><span class="sxs-lookup"><span data-stu-id="fd35e-213">Average ratio of stretched samples generated by audio healing to typical samples.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fd35e-214"><strong>RatioCompressedSamplesAvg</strong></span><span class="sxs-lookup"><span data-stu-id="fd35e-214"><strong>RatioCompressedSamplesAvg</strong></span></span></p></td>
<td><p><span data-ttu-id="fd35e-215">10進数 (5, 2)</span><span class="sxs-lookup"><span data-stu-id="fd35e-215">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="fd35e-216">オーディオの修復によって生成された、一般的なサンプルの圧縮サンプルの平均比率。</span><span class="sxs-lookup"><span data-stu-id="fd35e-216">Average ratio of compressed samples generated by audio healing to typical samples.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fd35e-217"><strong>トラフィック</strong></span><span class="sxs-lookup"><span data-stu-id="fd35e-217"><strong>Inbound</strong></span></span></p></td>
<td><p><span data-ttu-id="fd35e-218">bit</span><span class="sxs-lookup"><span data-stu-id="fd35e-218">bit</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="fd35e-219">受信側のストリームデータが受信されます。</span><span class="sxs-lookup"><span data-stu-id="fd35e-219">Stream data on receiver side is received.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fd35e-220"><strong>発信</strong></span><span class="sxs-lookup"><span data-stu-id="fd35e-220"><strong>Outbound</strong></span></span></p></td>
<td><p><span data-ttu-id="fd35e-221">bit</span><span class="sxs-lookup"><span data-stu-id="fd35e-221">bit</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="fd35e-222">送信側のストリームデータが受信されます。</span><span class="sxs-lookup"><span data-stu-id="fd35e-222">Stream data on sender side is received.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fd35e-223"><strong>SenderIsCallerPAI</strong></span><span class="sxs-lookup"><span data-stu-id="fd35e-223"><strong>SenderIsCallerPAI</strong></span></span></p></td>
<td><p><span data-ttu-id="fd35e-224">bit</span><span class="sxs-lookup"><span data-stu-id="fd35e-224">bit</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="fd35e-225">1は、ストリームの方向を呼び出し元から呼び出し先に転送することを意味します。</span><span class="sxs-lookup"><span data-stu-id="fd35e-225">1 means the stream direction is from the caller to the callee.</span></span></p>
<p><span data-ttu-id="fd35e-226">0は、ストリームの方向を呼び出し元から呼び出し元に転送します。</span><span class="sxs-lookup"><span data-stu-id="fd35e-226">0 means the stream direction is from the callee to the caller.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fd35e-227"><strong>JitterInterArrivalSD</strong></span><span class="sxs-lookup"><span data-stu-id="fd35e-227"><strong>JitterInterArrivalSD</strong></span></span></p></td>
<td><p><span data-ttu-id="fd35e-228">float</span><span class="sxs-lookup"><span data-stu-id="fd35e-228">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="fd35e-229">ジッタの到着時刻の標準偏差。</span><span class="sxs-lookup"><span data-stu-id="fd35e-229">Standard deviation for jitter arrival times.</span></span></p>
<p><span data-ttu-id="fd35e-230">この列は Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="fd35e-230">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fd35e-231"><strong>ConcealRatioMax</strong></span><span class="sxs-lookup"><span data-stu-id="fd35e-231"><strong>ConcealRatioMax</strong></span></span></p></td>
<td><p><span data-ttu-id="fd35e-232">float</span><span class="sxs-lookup"><span data-stu-id="fd35e-232">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="fd35e-233">Healer によって隠されているパケットの最大比率。</span><span class="sxs-lookup"><span data-stu-id="fd35e-233">Maximum ratio of packets concealed by the healer.</span></span></p>
<p><span data-ttu-id="fd35e-234">この列は Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="fd35e-234">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fd35e-235"><strong>ConcealRatioSD</strong></span><span class="sxs-lookup"><span data-stu-id="fd35e-235"><strong>ConcealRatioSD</strong></span></span></p></td>
<td><p><span data-ttu-id="fd35e-236">float</span><span class="sxs-lookup"><span data-stu-id="fd35e-236">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="fd35e-237">Healer によって隠されているパケットの比率の標準偏差。</span><span class="sxs-lookup"><span data-stu-id="fd35e-237">Standard deviation for the ratio of packets concealed by the healer.</span></span></p>
<p><span data-ttu-id="fd35e-238">この列は Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="fd35e-238">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fd35e-239"><strong>HealerPacketDropRatio</strong></span><span class="sxs-lookup"><span data-stu-id="fd35e-239"><strong>HealerPacketDropRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="fd35e-240">float</span><span class="sxs-lookup"><span data-stu-id="fd35e-240">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="fd35e-241">受信したパケットの合計数と比較して、healer によってドロップされたパケットの比率。</span><span class="sxs-lookup"><span data-stu-id="fd35e-241">Ratio of packets dropped by the healer compared to the total number of packets received.</span></span></p>
<p><span data-ttu-id="fd35e-242">この列は Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="fd35e-242">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fd35e-243"><strong>HealerFECPacketUsedRatio</strong></span><span class="sxs-lookup"><span data-stu-id="fd35e-243"><strong>HealerFECPacketUsedRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="fd35e-244">float</span><span class="sxs-lookup"><span data-stu-id="fd35e-244">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="fd35e-245">受信したパケットの合計数と比較した、使用された転送エラー修正パケットの比率。</span><span class="sxs-lookup"><span data-stu-id="fd35e-245">Ratio of used forward error correction packets compared to the total number of packets received.</span></span></p>
<p><span data-ttu-id="fd35e-246">この列は Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="fd35e-246">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fd35e-247"><strong>MaxCompressedSamples</strong></span><span class="sxs-lookup"><span data-stu-id="fd35e-247"><strong>MaxCompressedSamples</strong></span></span></p></td>
<td><p><span data-ttu-id="fd35e-248">float</span><span class="sxs-lookup"><span data-stu-id="fd35e-248">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="fd35e-249">Healer によって圧縮されたオーディオパケットの最大数。</span><span class="sxs-lookup"><span data-stu-id="fd35e-249">Maximum number of audio packets that were compressed by the healer.</span></span></p>
<p><span data-ttu-id="fd35e-250">この列は Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="fd35e-250">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fd35e-251"><strong>LossCongestionPercent</strong></span><span class="sxs-lookup"><span data-stu-id="fd35e-251"><strong>LossCongestionPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="fd35e-252">float</span><span class="sxs-lookup"><span data-stu-id="fd35e-252">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="fd35e-253">通話が切断された輻輳状態であった時間の割合を示します。</span><span class="sxs-lookup"><span data-stu-id="fd35e-253">Indicates the percentage of the time when the call was in a loss congestion state.</span></span></p>
<p><span data-ttu-id="fd35e-254">この列は Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="fd35e-254">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fd35e-255"><strong>DelayCongestionPercent</strong></span><span class="sxs-lookup"><span data-stu-id="fd35e-255"><strong>DelayCongestionPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="fd35e-256">float</span><span class="sxs-lookup"><span data-stu-id="fd35e-256">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="fd35e-257">ネットワークパケットが遅延したために発生した、通話の割合を示します。</span><span class="sxs-lookup"><span data-stu-id="fd35e-257">Indicates the percentage of the call during which congestion was caused by the delayed arrival of network packets.</span></span></p>
<p><span data-ttu-id="fd35e-258">この列は Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="fd35e-258">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fd35e-259"><strong>ContentionDetectedPercent</strong></span><span class="sxs-lookup"><span data-stu-id="fd35e-259"><strong>ContentionDetectedPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="fd35e-260">float</span><span class="sxs-lookup"><span data-stu-id="fd35e-260">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="fd35e-261">通話がネットワークリソースに対して競合した時間の割合を示します。</span><span class="sxs-lookup"><span data-stu-id="fd35e-261">Indicates the percentage of the time when the call was competing for network resources.</span></span></p>
<p><span data-ttu-id="fd35e-262">この列は Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="fd35e-262">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fd35e-263"><strong>BandwidthEstMin</strong></span><span class="sxs-lookup"><span data-stu-id="fd35e-263"><strong>BandwidthEstMin</strong></span></span></p></td>
<td><p><span data-ttu-id="fd35e-264">int</span><span class="sxs-lookup"><span data-stu-id="fd35e-264">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="fd35e-265">通話中の最小帯域幅推定値。</span><span class="sxs-lookup"><span data-stu-id="fd35e-265">Minimum amount of bandwidth estimation measured during the call.</span></span></p>
<p><span data-ttu-id="fd35e-266">この列は Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="fd35e-266">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fd35e-267"><strong>BandwidthEstMax</strong></span><span class="sxs-lookup"><span data-stu-id="fd35e-267"><strong>BandwidthEstMax</strong></span></span></p></td>
<td><p><span data-ttu-id="fd35e-268">int</span><span class="sxs-lookup"><span data-stu-id="fd35e-268">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="fd35e-269">通話中に測定された帯域幅推定の最大量。</span><span class="sxs-lookup"><span data-stu-id="fd35e-269">Maximum amount of bandwidth estimation measured during the call.</span></span></p>
<p><span data-ttu-id="fd35e-270">この列は Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="fd35e-270">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fd35e-271"><strong>BandwidthEstStdDev</strong></span><span class="sxs-lookup"><span data-stu-id="fd35e-271"><strong>BandwidthEstStdDev</strong></span></span></p></td>
<td><p><span data-ttu-id="fd35e-272">int</span><span class="sxs-lookup"><span data-stu-id="fd35e-272">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="fd35e-273">通話中に測定された帯域幅推定の標準偏差。</span><span class="sxs-lookup"><span data-stu-id="fd35e-273">Standard deviation of the bandwidth estimation measured during the call.</span></span></p>
<p><span data-ttu-id="fd35e-274">この列は Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="fd35e-274">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fd35e-275"><strong>BandwidthEstAvge</strong></span><span class="sxs-lookup"><span data-stu-id="fd35e-275"><strong>BandwidthEstAvge</strong></span></span></p></td>
<td><p><span data-ttu-id="fd35e-276">int</span><span class="sxs-lookup"><span data-stu-id="fd35e-276">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="fd35e-277">通話中に計測された平均帯域幅推定量。</span><span class="sxs-lookup"><span data-stu-id="fd35e-277">Average amount of bandwidth estimation measured during the call.</span></span></p>
<p><span data-ttu-id="fd35e-278">この列は Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="fd35e-278">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fd35e-279"><strong>RelativeOneWayTotal</strong></span><span class="sxs-lookup"><span data-stu-id="fd35e-279"><strong>RelativeOneWayTotal</strong></span></span></p></td>
<td><p><span data-ttu-id="fd35e-280">float</span><span class="sxs-lookup"><span data-stu-id="fd35e-280">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="fd35e-281">一方向の待機時間の合計。</span><span class="sxs-lookup"><span data-stu-id="fd35e-281">Total amount of one-way latency.</span></span> <span data-ttu-id="fd35e-282">相対的な一方向の待ち時間は、クライアントとサーバーの間の遅延を測定します。</span><span class="sxs-lookup"><span data-stu-id="fd35e-282">Relative one-way latency measures the delay between the client and the server.</span></span></p>
<p><span data-ttu-id="fd35e-283">この列は Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="fd35e-283">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fd35e-284"><strong>RelativeOneWayAverage</strong></span><span class="sxs-lookup"><span data-stu-id="fd35e-284"><strong>RelativeOneWayAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="fd35e-285">float</span><span class="sxs-lookup"><span data-stu-id="fd35e-285">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="fd35e-286">一方向の待ち時間の平均値。</span><span class="sxs-lookup"><span data-stu-id="fd35e-286">Average amount of one-way latency.</span></span> <span data-ttu-id="fd35e-287">相対的な一方向の待ち時間は、クライアントとサーバーの間の遅延を測定します。</span><span class="sxs-lookup"><span data-stu-id="fd35e-287">Relative one-way latency measures the delay between the client and the server.</span></span></p>
<p><span data-ttu-id="fd35e-288">この列は Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="fd35e-288">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fd35e-289"><strong>RelativeOneWayMax</strong></span><span class="sxs-lookup"><span data-stu-id="fd35e-289"><strong>RelativeOneWayMax</strong></span></span></p></td>
<td><p><span data-ttu-id="fd35e-290">float</span><span class="sxs-lookup"><span data-stu-id="fd35e-290">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="fd35e-291">一方向の待機時間の上限。</span><span class="sxs-lookup"><span data-stu-id="fd35e-291">Maximum amount of one-way latency.</span></span> <span data-ttu-id="fd35e-292">相対的な一方向の待ち時間は、クライアントとサーバーの間の遅延を測定します。</span><span class="sxs-lookup"><span data-stu-id="fd35e-292">Relative one-way latency measures the delay between the client and the server.</span></span></p>
<p><span data-ttu-id="fd35e-293">この列は Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="fd35e-293">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fd35e-294"><strong>RelativeOneWayBurstOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="fd35e-294"><strong>RelativeOneWayBurstOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="fd35e-295">int</span><span class="sxs-lookup"><span data-stu-id="fd35e-295">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="fd35e-296">1方向のバースト発生の合計。</span><span class="sxs-lookup"><span data-stu-id="fd35e-296">Total one-way burst occurrences.</span></span> <span data-ttu-id="fd35e-297">"Bursty" 伝送とは、安定したストリームと比べて予期しないバーストでデータが流れる伝送です。</span><span class="sxs-lookup"><span data-stu-id="fd35e-297">A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream.</span></span> <span data-ttu-id="fd35e-298">このメトリックは、クライアントとサーバー間のデータフローを計測します。</span><span class="sxs-lookup"><span data-stu-id="fd35e-298">This metric measures data flow between the client and the server.</span></span></p>
<p><span data-ttu-id="fd35e-299">この列は Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="fd35e-299">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fd35e-300"><strong>RelativeOneWayBurstDensity</strong></span><span class="sxs-lookup"><span data-stu-id="fd35e-300"><strong>RelativeOneWayBurstDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="fd35e-301">float</span><span class="sxs-lookup"><span data-stu-id="fd35e-301">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="fd35e-302">全体的な1方向バースト密度。</span><span class="sxs-lookup"><span data-stu-id="fd35e-302">Total one-way burst density.</span></span> <span data-ttu-id="fd35e-303">"Bursty" 伝送とは、安定したストリームと比べて予期しないバーストでデータが流れる伝送です。</span><span class="sxs-lookup"><span data-stu-id="fd35e-303">A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream.</span></span> <span data-ttu-id="fd35e-304">このメトリックは、クライアントとサーバー間のデータフローを計測します。</span><span class="sxs-lookup"><span data-stu-id="fd35e-304">This metric measures data flow between the client and the server.</span></span></p>
<p><span data-ttu-id="fd35e-305">この列は Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="fd35e-305">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fd35e-306"><strong>RelativeOneWayBurstDuration</strong></span><span class="sxs-lookup"><span data-stu-id="fd35e-306"><strong>RelativeOneWayBurstDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="fd35e-307">float</span><span class="sxs-lookup"><span data-stu-id="fd35e-307">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="fd35e-308">一方向のバースト期間の合計。</span><span class="sxs-lookup"><span data-stu-id="fd35e-308">Total one-way burst duration.</span></span> <span data-ttu-id="fd35e-309">"Bursty" 伝送とは、安定したストリームと比べて予期しないバーストでデータが流れる伝送です。</span><span class="sxs-lookup"><span data-stu-id="fd35e-309">A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream.</span></span> <span data-ttu-id="fd35e-310">このメトリックは、クライアントとサーバー間のデータフローを計測します。</span><span class="sxs-lookup"><span data-stu-id="fd35e-310">This metric measures data flow between the client and the server.</span></span></p>
<p><span data-ttu-id="fd35e-311">この列は Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="fd35e-311">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fd35e-312"><strong>RelativeOneWayGapOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="fd35e-312"><strong>RelativeOneWayGapOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="fd35e-313">int</span><span class="sxs-lookup"><span data-stu-id="fd35e-313">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="fd35e-314">一方向のギャップ出現の合計。</span><span class="sxs-lookup"><span data-stu-id="fd35e-314">Total one-way gap occurrences.</span></span> <span data-ttu-id="fd35e-315">"Bursty" 伝送とは、安定したストリームではなく、予期しないバーストでデータが流れる伝送です。ギャップは、このようなバーストの間の遅延を示します。</span><span class="sxs-lookup"><span data-stu-id="fd35e-315">A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream; gaps indicate delays between these bursts.</span></span> <span data-ttu-id="fd35e-316">このメトリックは、クライアントとサーバー間のデータフローを計測します。</span><span class="sxs-lookup"><span data-stu-id="fd35e-316">This metric measures data flow between the client and the server.</span></span></p>
<p><span data-ttu-id="fd35e-317">この列は Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="fd35e-317">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fd35e-318"><strong>RelativeOneWayGapDensity</strong></span><span class="sxs-lookup"><span data-stu-id="fd35e-318"><strong>RelativeOneWayGapDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="fd35e-319">float</span><span class="sxs-lookup"><span data-stu-id="fd35e-319">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="fd35e-320">一方向のギャップの密度の合計。</span><span class="sxs-lookup"><span data-stu-id="fd35e-320">Total one-way gap density.</span></span> <span data-ttu-id="fd35e-321">"Bursty" 伝送とは、安定したストリームではなく、予期しないバーストでデータが流れる伝送です。ギャップは、このようなバーストの間の遅延を示します。</span><span class="sxs-lookup"><span data-stu-id="fd35e-321">A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream; gaps indicate delays between these bursts.</span></span> <span data-ttu-id="fd35e-322">このメトリックは、クライアントとサーバー間のデータフローを計測します。</span><span class="sxs-lookup"><span data-stu-id="fd35e-322">This metric measures data flow between the client and the server.</span></span></p>
<p><span data-ttu-id="fd35e-323">この列は Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="fd35e-323">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fd35e-324"><strong>RelativeOneWayGapDuration</strong></span><span class="sxs-lookup"><span data-stu-id="fd35e-324"><strong>RelativeOneWayGapDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="fd35e-325">float</span><span class="sxs-lookup"><span data-stu-id="fd35e-325">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="fd35e-326">一方向のギャップ期間の合計。</span><span class="sxs-lookup"><span data-stu-id="fd35e-326">Total one-way gap duration.</span></span> <span data-ttu-id="fd35e-327">"Bursty" 伝送とは、安定したストリームではなく、予期しないバーストでデータが流れる伝送です。ギャップは、このようなバーストの間の遅延を示します。</span><span class="sxs-lookup"><span data-stu-id="fd35e-327">A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream; gaps indicate delays between these bursts.</span></span> <span data-ttu-id="fd35e-328">このメトリックは、クライアントとサーバー間のデータフローを計測します。</span><span class="sxs-lookup"><span data-stu-id="fd35e-328">This metric measures data flow between the client and the server.</span></span></p>
<p><span data-ttu-id="fd35e-329">この列は Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="fd35e-329">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fd35e-330"><strong>DecodeStereoPercent</strong></span><span class="sxs-lookup"><span data-stu-id="fd35e-330"><strong>DecodeStereoPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="fd35e-331">float</span><span class="sxs-lookup"><span data-stu-id="fd35e-331">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="fd35e-332">ステレオとしてデコードされた通話のパーセンテージ。</span><span class="sxs-lookup"><span data-stu-id="fd35e-332">Percentage of the call decoded as stereo.</span></span></p>
<p><span data-ttu-id="fd35e-333">この列は Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="fd35e-333">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fd35e-334"><strong>AecRenderStereoPercent</strong></span><span class="sxs-lookup"><span data-stu-id="fd35e-334"><strong>AecRenderStereoPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="fd35e-335">float</span><span class="sxs-lookup"><span data-stu-id="fd35e-335">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="fd35e-336">アコースティックエコーキャンセラによってステレオとしてレンダリングされた通話の割合。</span><span class="sxs-lookup"><span data-stu-id="fd35e-336">Percentage of the call rendered as stereo by the acoustic echo canceller.</span></span></p>
<p><span data-ttu-id="fd35e-337">この列は Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="fd35e-337">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fd35e-338"><strong>AudioPostFECPLR</strong></span><span class="sxs-lookup"><span data-stu-id="fd35e-338"><strong>AudioPostFECPLR</strong></span></span></p></td>
<td><p><span data-ttu-id="fd35e-339">float</span><span class="sxs-lookup"><span data-stu-id="fd35e-339">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="fd35e-340">転送後のエラー訂正が適用された後のパケット損失率。</span><span class="sxs-lookup"><span data-stu-id="fd35e-340">Packet loss rate after forward error correction has been applied.</span></span></p>
<p><span data-ttu-id="fd35e-341">この列は Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="fd35e-341">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fd35e-342"><strong>EncodeStereoPercent</strong></span><span class="sxs-lookup"><span data-stu-id="fd35e-342"><strong>EncodeStereoPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="fd35e-343">float</span><span class="sxs-lookup"><span data-stu-id="fd35e-343">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="fd35e-344">ステレオとしてエンコードされた通話の割合。</span><span class="sxs-lookup"><span data-stu-id="fd35e-344">Percentage of the call encoded as stereo.</span></span></p>
<p><span data-ttu-id="fd35e-345">この列は Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="fd35e-345">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fd35e-346"><strong>AecCaptureStereoPercent</strong></span><span class="sxs-lookup"><span data-stu-id="fd35e-346"><strong>AecCaptureStereoPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="fd35e-347">float</span><span class="sxs-lookup"><span data-stu-id="fd35e-347">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="fd35e-348">アコースティックエコーキャンセラでステレオとしてキャプチャされた通話のパーセンテージ。</span><span class="sxs-lookup"><span data-stu-id="fd35e-348">Percentage of the call captured as stereo by the acoustic echo canceller.</span></span></p>
<p><span data-ttu-id="fd35e-349">この列は Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="fd35e-349">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

