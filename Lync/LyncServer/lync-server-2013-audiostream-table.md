---
title: 'Lync Server 2013: AudioStream テーブル'
description: 'Lync Server 2013: AudioStream テーブル。'
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
ms.openlocfilehash: 8af2e622e14c54fa4f9a6313e1b0dae8f2483132
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48552343"
---
# <a name="audiostream-table-in-lync-server-2013"></a><span data-ttu-id="47ec5-103">Lync Server 2013 の AudioStream テーブル</span><span class="sxs-lookup"><span data-stu-id="47ec5-103">AudioStream table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="47ec5-104">_**トピックの最終更新日:** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="47ec5-104">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="47ec5-105">各レコードは、1つのオーディオストリームを表します。</span><span class="sxs-lookup"><span data-stu-id="47ec5-105">Each record represents one audio stream.</span></span> <span data-ttu-id="47ec5-106">通常、1つのオーディオメディアラインには2つのオーディオストリームが含まれています。</span><span class="sxs-lookup"><span data-stu-id="47ec5-106">One audio media line usually contains two audio streams.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="47ec5-107"><strong>列</strong></span><span class="sxs-lookup"><span data-stu-id="47ec5-107"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="47ec5-108"><strong>データ型</strong></span><span class="sxs-lookup"><span data-stu-id="47ec5-108"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="47ec5-109"><strong>キー/インデックス</strong></span><span class="sxs-lookup"><span data-stu-id="47ec5-109"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="47ec5-110"><strong>詳細</strong></span><span class="sxs-lookup"><span data-stu-id="47ec5-110"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="47ec5-111"><strong>ConferenceDateTime</strong></span><span class="sxs-lookup"><span data-stu-id="47ec5-111"><strong>ConferenceDateTime</strong></span></span></p></td>
<td><p><span data-ttu-id="47ec5-112">日付型</span><span class="sxs-lookup"><span data-stu-id="47ec5-112">datetime</span></span></p></td>
<td><p><span data-ttu-id="47ec5-113">Primary</span><span class="sxs-lookup"><span data-stu-id="47ec5-113">Primary</span></span></p></td>
<td><p><span data-ttu-id="47ec5-114"><a href="lync-server-2013-medialine-table.md">Lync Server 2013 の MediaLine テーブル</a>から参照されます。</span><span class="sxs-lookup"><span data-stu-id="47ec5-114">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="47ec5-115"><strong>SessionSeq</strong></span><span class="sxs-lookup"><span data-stu-id="47ec5-115"><strong>SessionSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="47ec5-116">int</span><span class="sxs-lookup"><span data-stu-id="47ec5-116">int</span></span></p></td>
<td><p><span data-ttu-id="47ec5-117">Primary</span><span class="sxs-lookup"><span data-stu-id="47ec5-117">Primary</span></span></p></td>
<td><p><span data-ttu-id="47ec5-118"><a href="lync-server-2013-medialine-table.md">Lync Server 2013 の MediaLine テーブル</a>から参照されます。</span><span class="sxs-lookup"><span data-stu-id="47ec5-118">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="47ec5-119"><strong>MediaLineLabel</strong></span><span class="sxs-lookup"><span data-stu-id="47ec5-119"><strong>MediaLineLabel</strong></span></span></p></td>
<td><p><span data-ttu-id="47ec5-120">tinyint</span><span class="sxs-lookup"><span data-stu-id="47ec5-120">tinyint</span></span></p></td>
<td><p><span data-ttu-id="47ec5-121">Primary</span><span class="sxs-lookup"><span data-stu-id="47ec5-121">Primary</span></span></p></td>
<td><p><span data-ttu-id="47ec5-122"><a href="lync-server-2013-medialine-table.md">Lync Server 2013 の MediaLine テーブル</a>から参照されます。</span><span class="sxs-lookup"><span data-stu-id="47ec5-122">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="47ec5-123"><strong>StreamID</strong></span><span class="sxs-lookup"><span data-stu-id="47ec5-123"><strong>StreamID</strong></span></span></p></td>
<td><p><span data-ttu-id="47ec5-124">int</span><span class="sxs-lookup"><span data-stu-id="47ec5-124">int</span></span></p></td>
<td><p><span data-ttu-id="47ec5-125">Primary</span><span class="sxs-lookup"><span data-stu-id="47ec5-125">Primary</span></span></p></td>
<td><p><span data-ttu-id="47ec5-126">メディア ライン内の一意の ID。</span><span class="sxs-lookup"><span data-stu-id="47ec5-126">Unique ID within a media line.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="47ec5-127"><strong>JitterInterArrival</strong></span><span class="sxs-lookup"><span data-stu-id="47ec5-127"><strong>JitterInterArrival</strong></span></span></p></td>
<td><p><span data-ttu-id="47ec5-128">int</span><span class="sxs-lookup"><span data-stu-id="47ec5-128">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="47ec5-129">リアルタイム制御プロトコル (RTCP) 統計情報に基づく平均ネットワーク ジッター。</span><span class="sxs-lookup"><span data-stu-id="47ec5-129">Average network jitter from Real Time Control Protocol (RTCP) statistics.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="47ec5-130"><strong>JitterInterArrivalMax</strong></span><span class="sxs-lookup"><span data-stu-id="47ec5-130"><strong>JitterInterArrivalMax</strong></span></span></p></td>
<td><p><span data-ttu-id="47ec5-131">int</span><span class="sxs-lookup"><span data-stu-id="47ec5-131">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="47ec5-132">通話時の最大ネットワーク ジッター。</span><span class="sxs-lookup"><span data-stu-id="47ec5-132">Maximum network jitter during the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="47ec5-133"><strong>PacketLossRate</strong></span><span class="sxs-lookup"><span data-stu-id="47ec5-133"><strong>PacketLossRate</strong></span></span></p></td>
<td><p><span data-ttu-id="47ec5-134">10進数 (5, 4)</span><span class="sxs-lookup"><span data-stu-id="47ec5-134">decimal(5,4)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="47ec5-135">通話時の平均パケット損失率。</span><span class="sxs-lookup"><span data-stu-id="47ec5-135">Average packet loss rate during the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="47ec5-136"><strong>PacketLossRateMax</strong></span><span class="sxs-lookup"><span data-stu-id="47ec5-136"><strong>PacketLossRateMax</strong></span></span></p></td>
<td><p><span data-ttu-id="47ec5-137">10進数 (5, 4)</span><span class="sxs-lookup"><span data-stu-id="47ec5-137">decimal(5,4)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="47ec5-138">通話時に観測された最大パケット損失。</span><span class="sxs-lookup"><span data-stu-id="47ec5-138">Maximum packet loss observed during the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="47ec5-139"><strong>BurstDensity</strong></span><span class="sxs-lookup"><span data-stu-id="47ec5-139"><strong>BurstDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="47ec5-140">10進数 (9、4)</span><span class="sxs-lookup"><span data-stu-id="47ec5-140">decimal(9,4)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="47ec5-141">通話中のバースト損失中のパケット損失の平均密度。</span><span class="sxs-lookup"><span data-stu-id="47ec5-141">Average density of packet Loss during bursts of losses during the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="47ec5-142"><strong>BurstDuration</strong></span><span class="sxs-lookup"><span data-stu-id="47ec5-142"><strong>BurstDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="47ec5-143">int</span><span class="sxs-lookup"><span data-stu-id="47ec5-143">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="47ec5-144">通話時の損失のバーストで発生したパケット損失の平均期間。</span><span class="sxs-lookup"><span data-stu-id="47ec5-144">Average duration of packet loss during bursts of losses during the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="47ec5-145"><strong>BurstGapDensity</strong></span><span class="sxs-lookup"><span data-stu-id="47ec5-145"><strong>BurstGapDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="47ec5-146">10進数 (9、4)</span><span class="sxs-lookup"><span data-stu-id="47ec5-146">decimal(9,4)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="47ec5-147">パケット損失のバーストが発生して次のバーストが発生するまでの間に発生したパケット損失の平均密度。</span><span class="sxs-lookup"><span data-stu-id="47ec5-147">Average density of packet loss during gaps between bursts of packet loss.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="47ec5-148"><strong>BurstGapDuration</strong></span><span class="sxs-lookup"><span data-stu-id="47ec5-148"><strong>BurstGapDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="47ec5-149">int</span><span class="sxs-lookup"><span data-stu-id="47ec5-149">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="47ec5-150">パケット損失のバーストが発生して次のバーストが発生するまでの平均期間。</span><span class="sxs-lookup"><span data-stu-id="47ec5-150">Average duration of gaps between bursts of packet loss.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="47ec5-151"><strong>PacketUtilization</strong></span><span class="sxs-lookup"><span data-stu-id="47ec5-151"><strong>PacketUtilization</strong></span></span></p></td>
<td><p><span data-ttu-id="47ec5-152">Int</span><span class="sxs-lookup"><span data-stu-id="47ec5-152">Int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="47ec5-153">音声ストリームのパケット数。</span><span class="sxs-lookup"><span data-stu-id="47ec5-153">Packet count for the audio stream.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="47ec5-154"><strong>BandwidthEst</strong></span><span class="sxs-lookup"><span data-stu-id="47ec5-154"><strong>BandwidthEst</strong></span></span></p></td>
<td><p><span data-ttu-id="47ec5-155">Int</span><span class="sxs-lookup"><span data-stu-id="47ec5-155">Int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="47ec5-156">音声ストリームの帯域幅の推定。</span><span class="sxs-lookup"><span data-stu-id="47ec5-156">Bandwidth estimates for the audio stream.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="47ec5-157"><strong>DegradationAvg</strong></span><span class="sxs-lookup"><span data-stu-id="47ec5-157"><strong>DegradationAvg</strong></span></span></p></td>
<td><p><span data-ttu-id="47ec5-158">10進数 (3、2)</span><span class="sxs-lookup"><span data-stu-id="47ec5-158">decimal(3,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="47ec5-p102">通話全体でのネットワーク MOS の低下。範囲は 0.0 ～ 5.0 です。この指標は、ジッターとパケット損失に起因する、ネットワーク MOS の低下量を示します。許容範囲に収まる程度の品質を維持するには、この値は 0.5 未満である必要があります。</span><span class="sxs-lookup"><span data-stu-id="47ec5-p102">Network MOS Degradation for the whole call. Range is 0.0 to 5.0. This metric shows the amount the Network MOS was reduced because of jitter and packet loss. For acceptable quality it should less than 0.5.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="47ec5-163"><strong>DegradationMax</strong></span><span class="sxs-lookup"><span data-stu-id="47ec5-163"><strong>DegradationMax</strong></span></span></p></td>
<td><p><span data-ttu-id="47ec5-164">10進数 (3、2)</span><span class="sxs-lookup"><span data-stu-id="47ec5-164">decimal(3,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="47ec5-165">通話時のネットワーク MOS の最大低下。</span><span class="sxs-lookup"><span data-stu-id="47ec5-165">Maximum Network MOS degradation during the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="47ec5-166"><strong>DegradationJitterAvg</strong></span><span class="sxs-lookup"><span data-stu-id="47ec5-166"><strong>DegradationJitterAvg</strong></span></span></p></td>
<td><p><span data-ttu-id="47ec5-167">10進数 (3、2)</span><span class="sxs-lookup"><span data-stu-id="47ec5-167">decimal(3,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="47ec5-168">ジッターに起因するネットワーク MOS の低下。</span><span class="sxs-lookup"><span data-stu-id="47ec5-168">Network MOS degradation caused by jitter.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="47ec5-169"><strong>DegradationPacketLossAvg</strong></span><span class="sxs-lookup"><span data-stu-id="47ec5-169"><strong>DegradationPacketLossAvg</strong></span></span></p></td>
<td><p><span data-ttu-id="47ec5-170">10進数 (3、2)</span><span class="sxs-lookup"><span data-stu-id="47ec5-170">decimal(3,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="47ec5-171">パケット損失に起因するネットワーク MOS の低下。</span><span class="sxs-lookup"><span data-stu-id="47ec5-171">Network MOS degradation caused by packet loss.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="47ec5-172"><strong>AudioPayloadDescription</strong></span><span class="sxs-lookup"><span data-stu-id="47ec5-172"><strong>AudioPayloadDescription</strong></span></span></p></td>
<td><p><span data-ttu-id="47ec5-173">int</span><span class="sxs-lookup"><span data-stu-id="47ec5-173">int</span></span></p></td>
<td><p><span data-ttu-id="47ec5-174">外部</span><span class="sxs-lookup"><span data-stu-id="47ec5-174">Foreign</span></span></p></td>
<td><p><span data-ttu-id="47ec5-175">呼び出しに使用されるオーディオコーデック (PayloadDescription テーブルから参照)。</span><span class="sxs-lookup"><span data-stu-id="47ec5-175">The audio Codec used for the call, referenced from PayloadDescription Table.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="47ec5-176"><strong>AudioSampleRate</strong></span><span class="sxs-lookup"><span data-stu-id="47ec5-176"><strong>AudioSampleRate</strong></span></span></p></td>
<td><p><span data-ttu-id="47ec5-177">int</span><span class="sxs-lookup"><span data-stu-id="47ec5-177">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="47ec5-178">音声ストリームのサンプリング レート。</span><span class="sxs-lookup"><span data-stu-id="47ec5-178">Sampling rate for the audio stream.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="47ec5-179"><strong>要し</strong></span><span class="sxs-lookup"><span data-stu-id="47ec5-179"><strong>RoundTrip</strong></span></span></p></td>
<td><p><span data-ttu-id="47ec5-180">int</span><span class="sxs-lookup"><span data-stu-id="47ec5-180">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="47ec5-181">RTCP 統計情報に基づく往復時間。</span><span class="sxs-lookup"><span data-stu-id="47ec5-181">Round trip time from RTCP statistics.</span></span> <span data-ttu-id="47ec5-182">許容できる品質を得るには、これは100ミリ秒より小さくなければなりません。</span><span class="sxs-lookup"><span data-stu-id="47ec5-182">For acceptable quality this should be less than 100ms.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="47ec5-183"><strong>RoundTripMax</strong></span><span class="sxs-lookup"><span data-stu-id="47ec5-183"><strong>RoundTripMax</strong></span></span></p></td>
<td><p><span data-ttu-id="47ec5-184">int</span><span class="sxs-lookup"><span data-stu-id="47ec5-184">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="47ec5-185">音声ストリームの最大往復時間。</span><span class="sxs-lookup"><span data-stu-id="47ec5-185">Maximum round trip time for the audio stream.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="47ec5-186"><strong>OverallAvgNetworkMOS</strong></span><span class="sxs-lookup"><span data-stu-id="47ec5-186"><strong>OverallAvgNetworkMOS</strong></span></span></p></td>
<td><p><span data-ttu-id="47ec5-187">10進数 (3、2)</span><span class="sxs-lookup"><span data-stu-id="47ec5-187">decimal(3,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="47ec5-188">通話の広帯域ネットワーク MOS の平均値。</span><span class="sxs-lookup"><span data-stu-id="47ec5-188">Average wideband Network MOS for the call.</span></span> <span data-ttu-id="47ec5-189">この指標は、パケット損失、ジッター、および使用されるコーデックによって異なります。</span><span class="sxs-lookup"><span data-stu-id="47ec5-189">This metric depends on the packet loss, jitter, and codec used.</span></span> <span data-ttu-id="47ec5-190">範囲は、[1.0 ~ 5.0] です。</span><span class="sxs-lookup"><span data-stu-id="47ec5-190">Range is [1.0 to 5.0].</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="47ec5-191"><strong>OverallMinNetworkMOS</strong></span><span class="sxs-lookup"><span data-stu-id="47ec5-191"><strong>OverallMinNetworkMOS</strong></span></span></p></td>
<td><p><span data-ttu-id="47ec5-192">10進数 (3、2)</span><span class="sxs-lookup"><span data-stu-id="47ec5-192">decimal(3,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="47ec5-193">通話の広帯域ネットワーク MOS の最小値。</span><span class="sxs-lookup"><span data-stu-id="47ec5-193">The minimum wideband Network MOS for the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="47ec5-194"><strong>SendListenMOS</strong></span><span class="sxs-lookup"><span data-stu-id="47ec5-194"><strong>SendListenMOS</strong></span></span></p></td>
<td><p><span data-ttu-id="47ec5-195">10進数 (3、2)</span><span class="sxs-lookup"><span data-stu-id="47ec5-195">decimal(3,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="47ec5-196">音声レベル、ノイズレベル、キャプチャデバイス特性など、送信される音声の広帯域リスニング MOS スコアの平均予測値。</span><span class="sxs-lookup"><span data-stu-id="47ec5-196">The average predicted wideband Listening MOS score for audio sent, including speech level, noise level and capture device characteristics.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="47ec5-197"><strong>SendListenMOSMin</strong></span><span class="sxs-lookup"><span data-stu-id="47ec5-197"><strong>SendListenMOSMin</strong></span></span></p></td>
<td><p><span data-ttu-id="47ec5-198">10進数 (3、2)</span><span class="sxs-lookup"><span data-stu-id="47ec5-198">decimal(3,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="47ec5-199">通話の最小 SendListenMOS。</span><span class="sxs-lookup"><span data-stu-id="47ec5-199">The minimum SendListenMOS for the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="47ec5-200"><strong>RecvListenMOS</strong></span><span class="sxs-lookup"><span data-stu-id="47ec5-200"><strong>RecvListenMOS</strong></span></span></p></td>
<td><p><span data-ttu-id="47ec5-201">10進数 (3、2)</span><span class="sxs-lookup"><span data-stu-id="47ec5-201">decimal(3,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="47ec5-202">音声レベル、ノイズレベル、コーデック、ネットワーク条件、キャプチャデバイス特性など、ネットワークから受信した音声の広帯域リスニング MOS スコアの平均予測値。</span><span class="sxs-lookup"><span data-stu-id="47ec5-202">The average predicted wideband Listening MOS score for audio received from the network including speech level, noise level, codec, network conditions and capture device characteristics.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="47ec5-203"><strong>RecvListenMOSMin</strong></span><span class="sxs-lookup"><span data-stu-id="47ec5-203"><strong>RecvListenMOSMin</strong></span></span></p></td>
<td><p><span data-ttu-id="47ec5-204">10進数 (3、2)</span><span class="sxs-lookup"><span data-stu-id="47ec5-204">decimal(3,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="47ec5-205">通話の最小 RecvListenMOS。</span><span class="sxs-lookup"><span data-stu-id="47ec5-205">The minimum RecvListenMOS for the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="47ec5-206"><strong>AudioFECUsed</strong></span><span class="sxs-lookup"><span data-stu-id="47ec5-206"><strong>AudioFECUsed</strong></span></span></p></td>
<td><p><span data-ttu-id="47ec5-207">若干</span><span class="sxs-lookup"><span data-stu-id="47ec5-207">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="47ec5-208">通話にオーディオ FEC が使用されたかどうかを示すフラグ。</span><span class="sxs-lookup"><span data-stu-id="47ec5-208">Flag indicating if audio FEC was used for the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="47ec5-209"><strong>RatioConcealedSamplesAvg</strong></span><span class="sxs-lookup"><span data-stu-id="47ec5-209"><strong>RatioConcealedSamplesAvg</strong></span></span></p></td>
<td><p><span data-ttu-id="47ec5-210">10進数 (5、2)</span><span class="sxs-lookup"><span data-stu-id="47ec5-210">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="47ec5-211">標準サンプルへの音声復旧によって生成される隠しサンプルの平均比率。</span><span class="sxs-lookup"><span data-stu-id="47ec5-211">Average ratio of concealed samples generated by audio healing to typical samples.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="47ec5-212"><strong>RatioStretchedSamplesAvg</strong></span><span class="sxs-lookup"><span data-stu-id="47ec5-212"><strong>RatioStretchedSamplesAvg</strong></span></span></p></td>
<td><p><span data-ttu-id="47ec5-213">10進数 (5、2)</span><span class="sxs-lookup"><span data-stu-id="47ec5-213">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="47ec5-214">標準サンプルへの音声復旧によって生成される引き伸ばしサンプルの平均比率。</span><span class="sxs-lookup"><span data-stu-id="47ec5-214">Average ratio of stretched samples generated by audio healing to typical samples.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="47ec5-215"><strong>RatioCompressedSamplesAvg</strong></span><span class="sxs-lookup"><span data-stu-id="47ec5-215"><strong>RatioCompressedSamplesAvg</strong></span></span></p></td>
<td><p><span data-ttu-id="47ec5-216">10進数 (5、2)</span><span class="sxs-lookup"><span data-stu-id="47ec5-216">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="47ec5-217">標準サンプルへの音声復旧によって生成される圧縮サンプルの平均比率。</span><span class="sxs-lookup"><span data-stu-id="47ec5-217">Average ratio of compressed samples generated by audio healing to typical samples.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="47ec5-218"><strong>受信</strong></span><span class="sxs-lookup"><span data-stu-id="47ec5-218"><strong>Inbound</strong></span></span></p></td>
<td><p><span data-ttu-id="47ec5-219">若干</span><span class="sxs-lookup"><span data-stu-id="47ec5-219">bit</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="47ec5-220">受信側のストリームデータが受信されます。</span><span class="sxs-lookup"><span data-stu-id="47ec5-220">Stream data on receiver side is received.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="47ec5-221"><strong>向き</strong></span><span class="sxs-lookup"><span data-stu-id="47ec5-221"><strong>Outbound</strong></span></span></p></td>
<td><p><span data-ttu-id="47ec5-222">若干</span><span class="sxs-lookup"><span data-stu-id="47ec5-222">bit</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="47ec5-223">送信側のストリームデータが受信されます。</span><span class="sxs-lookup"><span data-stu-id="47ec5-223">Stream data on sender side is received.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="47ec5-224"><strong>SenderIsCallerPAI</strong></span><span class="sxs-lookup"><span data-stu-id="47ec5-224"><strong>SenderIsCallerPAI</strong></span></span></p></td>
<td><p><span data-ttu-id="47ec5-225">若干</span><span class="sxs-lookup"><span data-stu-id="47ec5-225">bit</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="47ec5-226">1は、ストリームの方向が発信者から呼び出し先へ向かうことを意味します。</span><span class="sxs-lookup"><span data-stu-id="47ec5-226">1 means the stream direction is from the caller to the callee.</span></span></p>
<p><span data-ttu-id="47ec5-227">0 は、ストリームの方向が呼び出し先から発信者へ向かうことを意味します。</span><span class="sxs-lookup"><span data-stu-id="47ec5-227">0 means the stream direction is from the callee to the caller.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="47ec5-228"><strong>JitterInterArrivalSD</strong></span><span class="sxs-lookup"><span data-stu-id="47ec5-228"><strong>JitterInterArrivalSD</strong></span></span></p></td>
<td><p><span data-ttu-id="47ec5-229">浮動小数点数</span><span class="sxs-lookup"><span data-stu-id="47ec5-229">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="47ec5-230">ジッタ到着時間の標準偏差。</span><span class="sxs-lookup"><span data-stu-id="47ec5-230">Standard deviation for jitter arrival times.</span></span></p>
<p><span data-ttu-id="47ec5-231">このコラムは、Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="47ec5-231">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="47ec5-232"><strong>ConcealRatioMax</strong></span><span class="sxs-lookup"><span data-stu-id="47ec5-232"><strong>ConcealRatioMax</strong></span></span></p></td>
<td><p><span data-ttu-id="47ec5-233">浮動小数点数</span><span class="sxs-lookup"><span data-stu-id="47ec5-233">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="47ec5-234">ヒーラーによる隠しパケットの最大比率。</span><span class="sxs-lookup"><span data-stu-id="47ec5-234">Maximum ratio of packets concealed by the healer.</span></span></p>
<p><span data-ttu-id="47ec5-235">このコラムは、Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="47ec5-235">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="47ec5-236"><strong>ConcealRatioSD</strong></span><span class="sxs-lookup"><span data-stu-id="47ec5-236"><strong>ConcealRatioSD</strong></span></span></p></td>
<td><p><span data-ttu-id="47ec5-237">浮動小数点数</span><span class="sxs-lookup"><span data-stu-id="47ec5-237">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="47ec5-238">ヒーラーによって隠されたパケットの比率の標準偏差。</span><span class="sxs-lookup"><span data-stu-id="47ec5-238">Standard deviation for the ratio of packets concealed by the healer.</span></span></p>
<p><span data-ttu-id="47ec5-239">このコラムは、Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="47ec5-239">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="47ec5-240"><strong>HealerPacketDropRatio</strong></span><span class="sxs-lookup"><span data-stu-id="47ec5-240"><strong>HealerPacketDropRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="47ec5-241">浮動小数点数</span><span class="sxs-lookup"><span data-stu-id="47ec5-241">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="47ec5-242">受信したパケットの合計数と比較して、ヒーラーによって削除されたパケットの比率。</span><span class="sxs-lookup"><span data-stu-id="47ec5-242">Ratio of packets dropped by the healer compared to the total number of packets received.</span></span></p>
<p><span data-ttu-id="47ec5-243">このコラムは、Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="47ec5-243">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="47ec5-244"><strong>HealerFECPacketUsedRatio</strong></span><span class="sxs-lookup"><span data-stu-id="47ec5-244"><strong>HealerFECPacketUsedRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="47ec5-245">浮動小数点数</span><span class="sxs-lookup"><span data-stu-id="47ec5-245">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="47ec5-246">受信したパケットの合計数に対する、使用された転送エラー訂正パケットの比率。</span><span class="sxs-lookup"><span data-stu-id="47ec5-246">Ratio of used forward error correction packets compared to the total number of packets received.</span></span></p>
<p><span data-ttu-id="47ec5-247">このコラムは、Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="47ec5-247">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="47ec5-248"><strong>MaxCompressedSamples</strong></span><span class="sxs-lookup"><span data-stu-id="47ec5-248"><strong>MaxCompressedSamples</strong></span></span></p></td>
<td><p><span data-ttu-id="47ec5-249">浮動小数点数</span><span class="sxs-lookup"><span data-stu-id="47ec5-249">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="47ec5-250">ヒーラーによって圧縮されたオーディオパケットの最大数。</span><span class="sxs-lookup"><span data-stu-id="47ec5-250">Maximum number of audio packets that were compressed by the healer.</span></span></p>
<p><span data-ttu-id="47ec5-251">このコラムは、Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="47ec5-251">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="47ec5-252"><strong>LossCongestionPercent</strong></span><span class="sxs-lookup"><span data-stu-id="47ec5-252"><strong>LossCongestionPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="47ec5-253">浮動小数点数</span><span class="sxs-lookup"><span data-stu-id="47ec5-253">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="47ec5-254">通話が切断された輻輳状態であった時間の割合を示します。</span><span class="sxs-lookup"><span data-stu-id="47ec5-254">Indicates the percentage of the time when the call was in a loss congestion state.</span></span></p>
<p><span data-ttu-id="47ec5-255">このコラムは、Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="47ec5-255">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="47ec5-256"><strong>DelayCongestionPercent</strong></span><span class="sxs-lookup"><span data-stu-id="47ec5-256"><strong>DelayCongestionPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="47ec5-257">浮動小数点数</span><span class="sxs-lookup"><span data-stu-id="47ec5-257">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="47ec5-258">ネットワークパケットの遅延到着により輻輳が発生した通話の割合を示します。</span><span class="sxs-lookup"><span data-stu-id="47ec5-258">Indicates the percentage of the call during which congestion was caused by the delayed arrival of network packets.</span></span></p>
<p><span data-ttu-id="47ec5-259">このコラムは、Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="47ec5-259">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="47ec5-260"><strong>ContentionDetectedPercent</strong></span><span class="sxs-lookup"><span data-stu-id="47ec5-260"><strong>ContentionDetectedPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="47ec5-261">浮動小数点数</span><span class="sxs-lookup"><span data-stu-id="47ec5-261">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="47ec5-262">通話がネットワークリソースに対して競合していた時間の割合を示します。</span><span class="sxs-lookup"><span data-stu-id="47ec5-262">Indicates the percentage of the time when the call was competing for network resources.</span></span></p>
<p><span data-ttu-id="47ec5-263">このコラムは、Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="47ec5-263">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="47ec5-264"><strong>BandwidthEstMin</strong></span><span class="sxs-lookup"><span data-stu-id="47ec5-264"><strong>BandwidthEstMin</strong></span></span></p></td>
<td><p><span data-ttu-id="47ec5-265">int</span><span class="sxs-lookup"><span data-stu-id="47ec5-265">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="47ec5-266">呼び出し中に測定された最小帯域幅推定値。</span><span class="sxs-lookup"><span data-stu-id="47ec5-266">Minimum amount of bandwidth estimation measured during the call.</span></span></p>
<p><span data-ttu-id="47ec5-267">このコラムは、Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="47ec5-267">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="47ec5-268"><strong>BandwidthEstMax</strong></span><span class="sxs-lookup"><span data-stu-id="47ec5-268"><strong>BandwidthEstMax</strong></span></span></p></td>
<td><p><span data-ttu-id="47ec5-269">int</span><span class="sxs-lookup"><span data-stu-id="47ec5-269">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="47ec5-270">呼び出し中に測定された最大帯域幅推定値。</span><span class="sxs-lookup"><span data-stu-id="47ec5-270">Maximum amount of bandwidth estimation measured during the call.</span></span></p>
<p><span data-ttu-id="47ec5-271">このコラムは、Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="47ec5-271">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="47ec5-272"><strong>BandwidthEstStdDev</strong></span><span class="sxs-lookup"><span data-stu-id="47ec5-272"><strong>BandwidthEstStdDev</strong></span></span></p></td>
<td><p><span data-ttu-id="47ec5-273">int</span><span class="sxs-lookup"><span data-stu-id="47ec5-273">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="47ec5-274">呼び出し中に測定された帯域幅推定の標準偏差。</span><span class="sxs-lookup"><span data-stu-id="47ec5-274">Standard deviation of the bandwidth estimation measured during the call.</span></span></p>
<p><span data-ttu-id="47ec5-275">このコラムは、Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="47ec5-275">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="47ec5-276"><strong>BandwidthEstAvge</strong></span><span class="sxs-lookup"><span data-stu-id="47ec5-276"><strong>BandwidthEstAvge</strong></span></span></p></td>
<td><p><span data-ttu-id="47ec5-277">int</span><span class="sxs-lookup"><span data-stu-id="47ec5-277">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="47ec5-278">呼び出し中に測定された平均帯域幅推定値。</span><span class="sxs-lookup"><span data-stu-id="47ec5-278">Average amount of bandwidth estimation measured during the call.</span></span></p>
<p><span data-ttu-id="47ec5-279">このコラムは、Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="47ec5-279">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="47ec5-280"><strong>RelativeOneWayTotal</strong></span><span class="sxs-lookup"><span data-stu-id="47ec5-280"><strong>RelativeOneWayTotal</strong></span></span></p></td>
<td><p><span data-ttu-id="47ec5-281">浮動小数点数</span><span class="sxs-lookup"><span data-stu-id="47ec5-281">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="47ec5-p105">一方向の遅延の合計時間。相対的な一方向の遅延によって、クライアントとサーバーの間の遅延が測定されます。</span><span class="sxs-lookup"><span data-stu-id="47ec5-p105">Total amount of one-way latency. Relative one-way latency measures the delay between the client and the server.</span></span></p>
<p><span data-ttu-id="47ec5-284">このコラムは、Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="47ec5-284">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="47ec5-285"><strong>RelativeOneWayAverage</strong></span><span class="sxs-lookup"><span data-stu-id="47ec5-285"><strong>RelativeOneWayAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="47ec5-286">浮動小数点数</span><span class="sxs-lookup"><span data-stu-id="47ec5-286">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="47ec5-p106">一方向の遅延の平均時間。相対的な一方向の遅延によって、クライアントとサーバーの間の遅延が測定されます。</span><span class="sxs-lookup"><span data-stu-id="47ec5-p106">Average amount of one-way latency. Relative one-way latency measures the delay between the client and the server.</span></span></p>
<p><span data-ttu-id="47ec5-289">このコラムは、Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="47ec5-289">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="47ec5-290"><strong>RelativeOneWayMax</strong></span><span class="sxs-lookup"><span data-stu-id="47ec5-290"><strong>RelativeOneWayMax</strong></span></span></p></td>
<td><p><span data-ttu-id="47ec5-291">浮動小数点数</span><span class="sxs-lookup"><span data-stu-id="47ec5-291">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="47ec5-p107">一方向の遅延の最大時間。相対的な一方向の遅延によって、クライアントとサーバーの間の遅延が測定されます。</span><span class="sxs-lookup"><span data-stu-id="47ec5-p107">Maximum amount of one-way latency. Relative one-way latency measures the delay between the client and the server.</span></span></p>
<p><span data-ttu-id="47ec5-294">このコラムは、Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="47ec5-294">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="47ec5-295"><strong>RelativeOneWayBurstOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="47ec5-295"><strong>RelativeOneWayBurstOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="47ec5-296">int</span><span class="sxs-lookup"><span data-stu-id="47ec5-296">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="47ec5-p108">一方向のバーストの合計発生数。"バースト的な" 伝送とは、安定的なストリームではなく、予測できないバーストでデータが流れている伝送のことです。この指標では、クライアントとサーバーの間のデータ フローが測定されます。</span><span class="sxs-lookup"><span data-stu-id="47ec5-p108">Total one-way burst occurrences. A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream. This metric measures data flow between the client and the server.</span></span></p>
<p><span data-ttu-id="47ec5-300">このコラムは、Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="47ec5-300">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="47ec5-301"><strong>RelativeOneWayBurstDensity</strong></span><span class="sxs-lookup"><span data-stu-id="47ec5-301"><strong>RelativeOneWayBurstDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="47ec5-302">浮動小数点数</span><span class="sxs-lookup"><span data-stu-id="47ec5-302">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="47ec5-p109">一方向のバーストの合計密度。"バースト的な" 伝送とは、安定的なストリームではなく、予測できないバーストでデータが流れている伝送のことです。この指標では、クライアントとサーバーの間のデータ フローが測定されます。</span><span class="sxs-lookup"><span data-stu-id="47ec5-p109">Total one-way burst density. A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream. This metric measures data flow between the client and the server.</span></span></p>
<p><span data-ttu-id="47ec5-306">このコラムは、Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="47ec5-306">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="47ec5-307"><strong>RelativeOneWayBurstDuration</strong></span><span class="sxs-lookup"><span data-stu-id="47ec5-307"><strong>RelativeOneWayBurstDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="47ec5-308">浮動小数点数</span><span class="sxs-lookup"><span data-stu-id="47ec5-308">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="47ec5-p110">一方向のバーストの合計期間。"バースト的な" 伝送とは、安定的なストリームではなく、予測できないバーストでデータが流れている伝送のことです。この指標では、クライアントとサーバーの間のデータ フローが測定されます。</span><span class="sxs-lookup"><span data-stu-id="47ec5-p110">Total one-way burst duration. A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream. This metric measures data flow between the client and the server.</span></span></p>
<p><span data-ttu-id="47ec5-312">このコラムは、Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="47ec5-312">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="47ec5-313"><strong>RelativeOneWayGapOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="47ec5-313"><strong>RelativeOneWayGapOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="47ec5-314">int</span><span class="sxs-lookup"><span data-stu-id="47ec5-314">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="47ec5-p111">一方向のギャップの合計発生数。"バースト的な" 伝送とは、安定的なストリームではなく、予測できないバーストでデータが流れている伝送のことです。ギャップは、これらのバースト間の遅延を示します。この指標では、クライアントとサーバーの間のデータ フローが測定されます。</span><span class="sxs-lookup"><span data-stu-id="47ec5-p111">Total one-way gap occurrences. A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream; gaps indicate delays between these bursts. This metric measures data flow between the client and the server.</span></span></p>
<p><span data-ttu-id="47ec5-318">このコラムは、Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="47ec5-318">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="47ec5-319"><strong>RelativeOneWayGapDensity</strong></span><span class="sxs-lookup"><span data-stu-id="47ec5-319"><strong>RelativeOneWayGapDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="47ec5-320">浮動小数点数</span><span class="sxs-lookup"><span data-stu-id="47ec5-320">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="47ec5-p112">一方向のギャップの合計密度。"バースト的な" 伝送とは、安定的なストリームではなく、予測できないバーストでデータが流れている伝送のことです。ギャップは、これらのバースト間の遅延を示します。この指標では、クライアントとサーバーの間のデータ フローが測定されます。</span><span class="sxs-lookup"><span data-stu-id="47ec5-p112">Total one-way gap density. A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream; gaps indicate delays between these bursts. This metric measures data flow between the client and the server.</span></span></p>
<p><span data-ttu-id="47ec5-324">このコラムは、Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="47ec5-324">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="47ec5-325"><strong>RelativeOneWayGapDuration</strong></span><span class="sxs-lookup"><span data-stu-id="47ec5-325"><strong>RelativeOneWayGapDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="47ec5-326">浮動小数点数</span><span class="sxs-lookup"><span data-stu-id="47ec5-326">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="47ec5-p113">一方向のギャップの合計期間。"バースト的な" 伝送とは、安定的なストリームではなく、予測できないバーストでデータが流れている伝送のことです。ギャップは、これらのバースト間の遅延を示します。この指標では、クライアントとサーバーの間のデータ フローが測定されます。</span><span class="sxs-lookup"><span data-stu-id="47ec5-p113">Total one-way gap duration. A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream; gaps indicate delays between these bursts. This metric measures data flow between the client and the server.</span></span></p>
<p><span data-ttu-id="47ec5-330">このコラムは、Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="47ec5-330">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="47ec5-331"><strong>DecodeStereoPercent</strong></span><span class="sxs-lookup"><span data-stu-id="47ec5-331"><strong>DecodeStereoPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="47ec5-332">浮動小数点数</span><span class="sxs-lookup"><span data-stu-id="47ec5-332">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="47ec5-333">ステレオとしてデコードされた通話のパーセンテージ。</span><span class="sxs-lookup"><span data-stu-id="47ec5-333">Percentage of the call decoded as stereo.</span></span></p>
<p><span data-ttu-id="47ec5-334">このコラムは、Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="47ec5-334">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="47ec5-335"><strong>AecRenderStereoPercent</strong></span><span class="sxs-lookup"><span data-stu-id="47ec5-335"><strong>AecRenderStereoPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="47ec5-336">浮動小数点数</span><span class="sxs-lookup"><span data-stu-id="47ec5-336">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="47ec5-337">音響エコーキャンセラでステレオとしてレンダリングされた通話のパーセンテージ。</span><span class="sxs-lookup"><span data-stu-id="47ec5-337">Percentage of the call rendered as stereo by the acoustic echo canceller.</span></span></p>
<p><span data-ttu-id="47ec5-338">このコラムは、Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="47ec5-338">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="47ec5-339"><strong>AudioPostFECPLR</strong></span><span class="sxs-lookup"><span data-stu-id="47ec5-339"><strong>AudioPostFECPLR</strong></span></span></p></td>
<td><p><span data-ttu-id="47ec5-340">浮動小数点数</span><span class="sxs-lookup"><span data-stu-id="47ec5-340">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="47ec5-341">転送エラー訂正が適用された後のパケット損失率。</span><span class="sxs-lookup"><span data-stu-id="47ec5-341">Packet loss rate after forward error correction has been applied.</span></span></p>
<p><span data-ttu-id="47ec5-342">このコラムは、Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="47ec5-342">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="47ec5-343"><strong>EncodeStereoPercent</strong></span><span class="sxs-lookup"><span data-stu-id="47ec5-343"><strong>EncodeStereoPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="47ec5-344">浮動小数点数</span><span class="sxs-lookup"><span data-stu-id="47ec5-344">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="47ec5-345">ステレオとしてエンコードされた通話のパーセンテージ。</span><span class="sxs-lookup"><span data-stu-id="47ec5-345">Percentage of the call encoded as stereo.</span></span></p>
<p><span data-ttu-id="47ec5-346">このコラムは、Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="47ec5-346">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="47ec5-347"><strong>AecCaptureStereoPercent</strong></span><span class="sxs-lookup"><span data-stu-id="47ec5-347"><strong>AecCaptureStereoPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="47ec5-348">浮動小数点数</span><span class="sxs-lookup"><span data-stu-id="47ec5-348">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="47ec5-349">音響エコーキャンセラでステレオとしてキャプチャされた通話のパーセンテージ。</span><span class="sxs-lookup"><span data-stu-id="47ec5-349">Percentage of the call captured as stereo by the acoustic echo canceller.</span></span></p>
<p><span data-ttu-id="47ec5-350">このコラムは、Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="47ec5-350">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

