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
ms.openlocfilehash: 0f169a00a9eff262d0229daf6e52110d64cf7a34
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/19/2020
ms.locfileid: "42145476"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="audiostream-table-in-lync-server-2013"></a><span data-ttu-id="0fdfd-102">Lync Server 2013 の AudioStream テーブル</span><span class="sxs-lookup"><span data-stu-id="0fdfd-102">AudioStream table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0fdfd-103">_**トピックの最終更新日:** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="0fdfd-103">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="0fdfd-104">各レコードは、1つのオーディオストリームを表します。</span><span class="sxs-lookup"><span data-stu-id="0fdfd-104">Each record represents one audio stream.</span></span> <span data-ttu-id="0fdfd-105">通常、1つのオーディオメディアラインには2つのオーディオストリームが含まれています。</span><span class="sxs-lookup"><span data-stu-id="0fdfd-105">One audio media line usually contains two audio streams.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="0fdfd-106"><strong>列</strong></span><span class="sxs-lookup"><span data-stu-id="0fdfd-106"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="0fdfd-107"><strong>データ型</strong></span><span class="sxs-lookup"><span data-stu-id="0fdfd-107"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="0fdfd-108"><strong>キー/インデックス</strong></span><span class="sxs-lookup"><span data-stu-id="0fdfd-108"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="0fdfd-109"><strong>詳細</strong></span><span class="sxs-lookup"><span data-stu-id="0fdfd-109"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="0fdfd-110"><strong>ConferenceDateTime</strong></span><span class="sxs-lookup"><span data-stu-id="0fdfd-110"><strong>ConferenceDateTime</strong></span></span></p></td>
<td><p><span data-ttu-id="0fdfd-111">日付型</span><span class="sxs-lookup"><span data-stu-id="0fdfd-111">datetime</span></span></p></td>
<td><p><span data-ttu-id="0fdfd-112">Primary</span><span class="sxs-lookup"><span data-stu-id="0fdfd-112">Primary</span></span></p></td>
<td><p><span data-ttu-id="0fdfd-113"><a href="lync-server-2013-medialine-table.md">Lync Server 2013 の MediaLine テーブル</a>から参照されます。</span><span class="sxs-lookup"><span data-stu-id="0fdfd-113">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0fdfd-114"><strong>SessionSeq</strong></span><span class="sxs-lookup"><span data-stu-id="0fdfd-114"><strong>SessionSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="0fdfd-115">int</span><span class="sxs-lookup"><span data-stu-id="0fdfd-115">int</span></span></p></td>
<td><p><span data-ttu-id="0fdfd-116">Primary</span><span class="sxs-lookup"><span data-stu-id="0fdfd-116">Primary</span></span></p></td>
<td><p><span data-ttu-id="0fdfd-117"><a href="lync-server-2013-medialine-table.md">Lync Server 2013 の MediaLine テーブル</a>から参照されます。</span><span class="sxs-lookup"><span data-stu-id="0fdfd-117">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0fdfd-118"><strong>MediaLineLabel</strong></span><span class="sxs-lookup"><span data-stu-id="0fdfd-118"><strong>MediaLineLabel</strong></span></span></p></td>
<td><p><span data-ttu-id="0fdfd-119">tinyint</span><span class="sxs-lookup"><span data-stu-id="0fdfd-119">tinyint</span></span></p></td>
<td><p><span data-ttu-id="0fdfd-120">Primary</span><span class="sxs-lookup"><span data-stu-id="0fdfd-120">Primary</span></span></p></td>
<td><p><span data-ttu-id="0fdfd-121"><a href="lync-server-2013-medialine-table.md">Lync Server 2013 の MediaLine テーブル</a>から参照されます。</span><span class="sxs-lookup"><span data-stu-id="0fdfd-121">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0fdfd-122"><strong>StreamID</strong></span><span class="sxs-lookup"><span data-stu-id="0fdfd-122"><strong>StreamID</strong></span></span></p></td>
<td><p><span data-ttu-id="0fdfd-123">int</span><span class="sxs-lookup"><span data-stu-id="0fdfd-123">int</span></span></p></td>
<td><p><span data-ttu-id="0fdfd-124">Primary</span><span class="sxs-lookup"><span data-stu-id="0fdfd-124">Primary</span></span></p></td>
<td><p><span data-ttu-id="0fdfd-125">メディア ライン内の一意の ID。</span><span class="sxs-lookup"><span data-stu-id="0fdfd-125">Unique ID within a media line.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0fdfd-126"><strong>JitterInterArrival</strong></span><span class="sxs-lookup"><span data-stu-id="0fdfd-126"><strong>JitterInterArrival</strong></span></span></p></td>
<td><p><span data-ttu-id="0fdfd-127">int</span><span class="sxs-lookup"><span data-stu-id="0fdfd-127">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="0fdfd-128">リアルタイム制御プロトコル (RTCP) 統計情報に基づく平均ネットワーク ジッター。</span><span class="sxs-lookup"><span data-stu-id="0fdfd-128">Average network jitter from Real Time Control Protocol (RTCP) statistics.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0fdfd-129"><strong>JitterInterArrivalMax</strong></span><span class="sxs-lookup"><span data-stu-id="0fdfd-129"><strong>JitterInterArrivalMax</strong></span></span></p></td>
<td><p><span data-ttu-id="0fdfd-130">int</span><span class="sxs-lookup"><span data-stu-id="0fdfd-130">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="0fdfd-131">通話時の最大ネットワーク ジッター。</span><span class="sxs-lookup"><span data-stu-id="0fdfd-131">Maximum network jitter during the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0fdfd-132"><strong>PacketLossRate</strong></span><span class="sxs-lookup"><span data-stu-id="0fdfd-132"><strong>PacketLossRate</strong></span></span></p></td>
<td><p><span data-ttu-id="0fdfd-133">10進数 (5, 4)</span><span class="sxs-lookup"><span data-stu-id="0fdfd-133">decimal(5,4)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="0fdfd-134">通話時の平均パケット損失率。</span><span class="sxs-lookup"><span data-stu-id="0fdfd-134">Average packet loss rate during the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0fdfd-135"><strong>PacketLossRateMax</strong></span><span class="sxs-lookup"><span data-stu-id="0fdfd-135"><strong>PacketLossRateMax</strong></span></span></p></td>
<td><p><span data-ttu-id="0fdfd-136">10進数 (5, 4)</span><span class="sxs-lookup"><span data-stu-id="0fdfd-136">decimal(5,4)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="0fdfd-137">通話時に観測された最大パケット損失。</span><span class="sxs-lookup"><span data-stu-id="0fdfd-137">Maximum packet loss observed during the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0fdfd-138"><strong>BurstDensity</strong></span><span class="sxs-lookup"><span data-stu-id="0fdfd-138"><strong>BurstDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="0fdfd-139">10進数 (9、4)</span><span class="sxs-lookup"><span data-stu-id="0fdfd-139">decimal(9,4)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="0fdfd-140">通話中のバースト損失中のパケット損失の平均密度。</span><span class="sxs-lookup"><span data-stu-id="0fdfd-140">Average density of packet Loss during bursts of losses during the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0fdfd-141"><strong>BurstDuration</strong></span><span class="sxs-lookup"><span data-stu-id="0fdfd-141"><strong>BurstDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="0fdfd-142">int</span><span class="sxs-lookup"><span data-stu-id="0fdfd-142">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="0fdfd-143">通話時の損失のバーストで発生したパケット損失の平均期間。</span><span class="sxs-lookup"><span data-stu-id="0fdfd-143">Average duration of packet loss during bursts of losses during the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0fdfd-144"><strong>BurstGapDensity</strong></span><span class="sxs-lookup"><span data-stu-id="0fdfd-144"><strong>BurstGapDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="0fdfd-145">10進数 (9、4)</span><span class="sxs-lookup"><span data-stu-id="0fdfd-145">decimal(9,4)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="0fdfd-146">パケット損失のバーストが発生して次のバーストが発生するまでの間に発生したパケット損失の平均密度。</span><span class="sxs-lookup"><span data-stu-id="0fdfd-146">Average density of packet loss during gaps between bursts of packet loss.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0fdfd-147"><strong>BurstGapDuration</strong></span><span class="sxs-lookup"><span data-stu-id="0fdfd-147"><strong>BurstGapDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="0fdfd-148">int</span><span class="sxs-lookup"><span data-stu-id="0fdfd-148">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="0fdfd-149">パケット損失のバーストが発生して次のバーストが発生するまでの平均期間。</span><span class="sxs-lookup"><span data-stu-id="0fdfd-149">Average duration of gaps between bursts of packet loss.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0fdfd-150"><strong>PacketUtilization</strong></span><span class="sxs-lookup"><span data-stu-id="0fdfd-150"><strong>PacketUtilization</strong></span></span></p></td>
<td><p><span data-ttu-id="0fdfd-151">Int</span><span class="sxs-lookup"><span data-stu-id="0fdfd-151">Int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="0fdfd-152">音声ストリームのパケット数。</span><span class="sxs-lookup"><span data-stu-id="0fdfd-152">Packet count for the audio stream.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0fdfd-153"><strong>BandwidthEst</strong></span><span class="sxs-lookup"><span data-stu-id="0fdfd-153"><strong>BandwidthEst</strong></span></span></p></td>
<td><p><span data-ttu-id="0fdfd-154">Int</span><span class="sxs-lookup"><span data-stu-id="0fdfd-154">Int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="0fdfd-155">音声ストリームの帯域幅の推定。</span><span class="sxs-lookup"><span data-stu-id="0fdfd-155">Bandwidth estimates for the audio stream.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0fdfd-156"><strong>DegradationAvg</strong></span><span class="sxs-lookup"><span data-stu-id="0fdfd-156"><strong>DegradationAvg</strong></span></span></p></td>
<td><p><span data-ttu-id="0fdfd-157">10進数 (3、2)</span><span class="sxs-lookup"><span data-stu-id="0fdfd-157">decimal(3,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="0fdfd-p102">通話全体でのネットワーク MOS の低下。範囲は 0.0 ～ 5.0 です。この指標は、ジッターとパケット損失に起因する、ネットワーク MOS の低下量を示します。許容範囲に収まる程度の品質を維持するには、この値は 0.5 未満である必要があります。</span><span class="sxs-lookup"><span data-stu-id="0fdfd-p102">Network MOS Degradation for the whole call. Range is 0.0 to 5.0. This metric shows the amount the Network MOS was reduced because of jitter and packet loss. For acceptable quality it should less than 0.5.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0fdfd-162"><strong>DegradationMax</strong></span><span class="sxs-lookup"><span data-stu-id="0fdfd-162"><strong>DegradationMax</strong></span></span></p></td>
<td><p><span data-ttu-id="0fdfd-163">10進数 (3、2)</span><span class="sxs-lookup"><span data-stu-id="0fdfd-163">decimal(3,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="0fdfd-164">通話時のネットワーク MOS の最大低下。</span><span class="sxs-lookup"><span data-stu-id="0fdfd-164">Maximum Network MOS degradation during the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0fdfd-165"><strong>DegradationJitterAvg</strong></span><span class="sxs-lookup"><span data-stu-id="0fdfd-165"><strong>DegradationJitterAvg</strong></span></span></p></td>
<td><p><span data-ttu-id="0fdfd-166">10進数 (3、2)</span><span class="sxs-lookup"><span data-stu-id="0fdfd-166">decimal(3,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="0fdfd-167">ジッターに起因するネットワーク MOS の低下。</span><span class="sxs-lookup"><span data-stu-id="0fdfd-167">Network MOS degradation caused by jitter.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0fdfd-168"><strong>DegradationPacketLossAvg</strong></span><span class="sxs-lookup"><span data-stu-id="0fdfd-168"><strong>DegradationPacketLossAvg</strong></span></span></p></td>
<td><p><span data-ttu-id="0fdfd-169">10進数 (3、2)</span><span class="sxs-lookup"><span data-stu-id="0fdfd-169">decimal(3,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="0fdfd-170">パケット損失に起因するネットワーク MOS の低下。</span><span class="sxs-lookup"><span data-stu-id="0fdfd-170">Network MOS degradation caused by packet loss.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0fdfd-171"><strong>AudioPayloadDescription</strong></span><span class="sxs-lookup"><span data-stu-id="0fdfd-171"><strong>AudioPayloadDescription</strong></span></span></p></td>
<td><p><span data-ttu-id="0fdfd-172">int</span><span class="sxs-lookup"><span data-stu-id="0fdfd-172">int</span></span></p></td>
<td><p><span data-ttu-id="0fdfd-173">外部</span><span class="sxs-lookup"><span data-stu-id="0fdfd-173">Foreign</span></span></p></td>
<td><p><span data-ttu-id="0fdfd-174">呼び出しに使用されるオーディオコーデック (PayloadDescription テーブルから参照)。</span><span class="sxs-lookup"><span data-stu-id="0fdfd-174">The audio Codec used for the call, referenced from PayloadDescription Table.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0fdfd-175"><strong>AudioSampleRate</strong></span><span class="sxs-lookup"><span data-stu-id="0fdfd-175"><strong>AudioSampleRate</strong></span></span></p></td>
<td><p><span data-ttu-id="0fdfd-176">int</span><span class="sxs-lookup"><span data-stu-id="0fdfd-176">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="0fdfd-177">音声ストリームのサンプリング レート。</span><span class="sxs-lookup"><span data-stu-id="0fdfd-177">Sampling rate for the audio stream.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0fdfd-178"><strong>要し</strong></span><span class="sxs-lookup"><span data-stu-id="0fdfd-178"><strong>RoundTrip</strong></span></span></p></td>
<td><p><span data-ttu-id="0fdfd-179">int</span><span class="sxs-lookup"><span data-stu-id="0fdfd-179">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="0fdfd-180">RTCP 統計情報に基づく往復時間。</span><span class="sxs-lookup"><span data-stu-id="0fdfd-180">Round trip time from RTCP statistics.</span></span> <span data-ttu-id="0fdfd-181">許容できる品質を得るには、これは100ミリ秒より小さくなければなりません。</span><span class="sxs-lookup"><span data-stu-id="0fdfd-181">For acceptable quality this should be less than 100ms.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0fdfd-182"><strong>RoundTripMax</strong></span><span class="sxs-lookup"><span data-stu-id="0fdfd-182"><strong>RoundTripMax</strong></span></span></p></td>
<td><p><span data-ttu-id="0fdfd-183">int</span><span class="sxs-lookup"><span data-stu-id="0fdfd-183">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="0fdfd-184">音声ストリームの最大往復時間。</span><span class="sxs-lookup"><span data-stu-id="0fdfd-184">Maximum round trip time for the audio stream.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0fdfd-185"><strong>OverallAvgNetworkMOS</strong></span><span class="sxs-lookup"><span data-stu-id="0fdfd-185"><strong>OverallAvgNetworkMOS</strong></span></span></p></td>
<td><p><span data-ttu-id="0fdfd-186">10進数 (3、2)</span><span class="sxs-lookup"><span data-stu-id="0fdfd-186">decimal(3,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="0fdfd-187">通話の広帯域ネットワーク MOS の平均値。</span><span class="sxs-lookup"><span data-stu-id="0fdfd-187">Average wideband Network MOS for the call.</span></span> <span data-ttu-id="0fdfd-188">この指標は、パケット損失、ジッター、および使用されるコーデックによって異なります。</span><span class="sxs-lookup"><span data-stu-id="0fdfd-188">This metric depends on the packet loss, jitter, and codec used.</span></span> <span data-ttu-id="0fdfd-189">範囲は、[1.0 ~ 5.0] です。</span><span class="sxs-lookup"><span data-stu-id="0fdfd-189">Range is [1.0 to 5.0].</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0fdfd-190"><strong>OverallMinNetworkMOS</strong></span><span class="sxs-lookup"><span data-stu-id="0fdfd-190"><strong>OverallMinNetworkMOS</strong></span></span></p></td>
<td><p><span data-ttu-id="0fdfd-191">10進数 (3、2)</span><span class="sxs-lookup"><span data-stu-id="0fdfd-191">decimal(3,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="0fdfd-192">通話の広帯域ネットワーク MOS の最小値。</span><span class="sxs-lookup"><span data-stu-id="0fdfd-192">The minimum wideband Network MOS for the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0fdfd-193"><strong>SendListenMOS</strong></span><span class="sxs-lookup"><span data-stu-id="0fdfd-193"><strong>SendListenMOS</strong></span></span></p></td>
<td><p><span data-ttu-id="0fdfd-194">10進数 (3、2)</span><span class="sxs-lookup"><span data-stu-id="0fdfd-194">decimal(3,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="0fdfd-195">音声レベル、ノイズレベル、キャプチャデバイス特性など、送信される音声の広帯域リスニング MOS スコアの平均予測値。</span><span class="sxs-lookup"><span data-stu-id="0fdfd-195">The average predicted wideband Listening MOS score for audio sent, including speech level, noise level and capture device characteristics.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0fdfd-196"><strong>SendListenMOSMin</strong></span><span class="sxs-lookup"><span data-stu-id="0fdfd-196"><strong>SendListenMOSMin</strong></span></span></p></td>
<td><p><span data-ttu-id="0fdfd-197">10進数 (3、2)</span><span class="sxs-lookup"><span data-stu-id="0fdfd-197">decimal(3,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="0fdfd-198">通話の最小 SendListenMOS。</span><span class="sxs-lookup"><span data-stu-id="0fdfd-198">The minimum SendListenMOS for the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0fdfd-199"><strong>RecvListenMOS</strong></span><span class="sxs-lookup"><span data-stu-id="0fdfd-199"><strong>RecvListenMOS</strong></span></span></p></td>
<td><p><span data-ttu-id="0fdfd-200">10進数 (3、2)</span><span class="sxs-lookup"><span data-stu-id="0fdfd-200">decimal(3,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="0fdfd-201">音声レベル、ノイズレベル、コーデック、ネットワーク条件、キャプチャデバイス特性など、ネットワークから受信した音声の広帯域リスニング MOS スコアの平均予測値。</span><span class="sxs-lookup"><span data-stu-id="0fdfd-201">The average predicted wideband Listening MOS score for audio received from the network including speech level, noise level, codec, network conditions and capture device characteristics.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0fdfd-202"><strong>RecvListenMOSMin</strong></span><span class="sxs-lookup"><span data-stu-id="0fdfd-202"><strong>RecvListenMOSMin</strong></span></span></p></td>
<td><p><span data-ttu-id="0fdfd-203">10進数 (3、2)</span><span class="sxs-lookup"><span data-stu-id="0fdfd-203">decimal(3,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="0fdfd-204">通話の最小 RecvListenMOS。</span><span class="sxs-lookup"><span data-stu-id="0fdfd-204">The minimum RecvListenMOS for the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0fdfd-205"><strong>AudioFECUsed</strong></span><span class="sxs-lookup"><span data-stu-id="0fdfd-205"><strong>AudioFECUsed</strong></span></span></p></td>
<td><p><span data-ttu-id="0fdfd-206">若干</span><span class="sxs-lookup"><span data-stu-id="0fdfd-206">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="0fdfd-207">通話にオーディオ FEC が使用されたかどうかを示すフラグ。</span><span class="sxs-lookup"><span data-stu-id="0fdfd-207">Flag indicating if audio FEC was used for the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0fdfd-208"><strong>RatioConcealedSamplesAvg</strong></span><span class="sxs-lookup"><span data-stu-id="0fdfd-208"><strong>RatioConcealedSamplesAvg</strong></span></span></p></td>
<td><p><span data-ttu-id="0fdfd-209">10進数 (5、2)</span><span class="sxs-lookup"><span data-stu-id="0fdfd-209">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="0fdfd-210">標準サンプルへの音声復旧によって生成される隠しサンプルの平均比率。</span><span class="sxs-lookup"><span data-stu-id="0fdfd-210">Average ratio of concealed samples generated by audio healing to typical samples.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0fdfd-211"><strong>RatioStretchedSamplesAvg</strong></span><span class="sxs-lookup"><span data-stu-id="0fdfd-211"><strong>RatioStretchedSamplesAvg</strong></span></span></p></td>
<td><p><span data-ttu-id="0fdfd-212">10進数 (5、2)</span><span class="sxs-lookup"><span data-stu-id="0fdfd-212">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="0fdfd-213">標準サンプルへの音声復旧によって生成される引き伸ばしサンプルの平均比率。</span><span class="sxs-lookup"><span data-stu-id="0fdfd-213">Average ratio of stretched samples generated by audio healing to typical samples.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0fdfd-214"><strong>RatioCompressedSamplesAvg</strong></span><span class="sxs-lookup"><span data-stu-id="0fdfd-214"><strong>RatioCompressedSamplesAvg</strong></span></span></p></td>
<td><p><span data-ttu-id="0fdfd-215">10進数 (5、2)</span><span class="sxs-lookup"><span data-stu-id="0fdfd-215">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="0fdfd-216">標準サンプルへの音声復旧によって生成される圧縮サンプルの平均比率。</span><span class="sxs-lookup"><span data-stu-id="0fdfd-216">Average ratio of compressed samples generated by audio healing to typical samples.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0fdfd-217"><strong>受信</strong></span><span class="sxs-lookup"><span data-stu-id="0fdfd-217"><strong>Inbound</strong></span></span></p></td>
<td><p><span data-ttu-id="0fdfd-218">若干</span><span class="sxs-lookup"><span data-stu-id="0fdfd-218">bit</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="0fdfd-219">受信側のストリームデータが受信されます。</span><span class="sxs-lookup"><span data-stu-id="0fdfd-219">Stream data on receiver side is received.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0fdfd-220"><strong>送信</strong></span><span class="sxs-lookup"><span data-stu-id="0fdfd-220"><strong>Outbound</strong></span></span></p></td>
<td><p><span data-ttu-id="0fdfd-221">若干</span><span class="sxs-lookup"><span data-stu-id="0fdfd-221">bit</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="0fdfd-222">送信側のストリームデータが受信されます。</span><span class="sxs-lookup"><span data-stu-id="0fdfd-222">Stream data on sender side is received.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0fdfd-223"><strong>SenderIsCallerPAI</strong></span><span class="sxs-lookup"><span data-stu-id="0fdfd-223"><strong>SenderIsCallerPAI</strong></span></span></p></td>
<td><p><span data-ttu-id="0fdfd-224">若干</span><span class="sxs-lookup"><span data-stu-id="0fdfd-224">bit</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="0fdfd-225">1は、ストリームの方向が発信者から呼び出し先へ向かうことを意味します。</span><span class="sxs-lookup"><span data-stu-id="0fdfd-225">1 means the stream direction is from the caller to the callee.</span></span></p>
<p><span data-ttu-id="0fdfd-226">0 は、ストリームの方向が呼び出し先から発信者へ向かうことを意味します。</span><span class="sxs-lookup"><span data-stu-id="0fdfd-226">0 means the stream direction is from the callee to the caller.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0fdfd-227"><strong>JitterInterArrivalSD</strong></span><span class="sxs-lookup"><span data-stu-id="0fdfd-227"><strong>JitterInterArrivalSD</strong></span></span></p></td>
<td><p><span data-ttu-id="0fdfd-228">浮動小数点数</span><span class="sxs-lookup"><span data-stu-id="0fdfd-228">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="0fdfd-229">ジッタ到着時間の標準偏差。</span><span class="sxs-lookup"><span data-stu-id="0fdfd-229">Standard deviation for jitter arrival times.</span></span></p>
<p><span data-ttu-id="0fdfd-230">このコラムは、Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="0fdfd-230">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0fdfd-231"><strong>ConcealRatioMax</strong></span><span class="sxs-lookup"><span data-stu-id="0fdfd-231"><strong>ConcealRatioMax</strong></span></span></p></td>
<td><p><span data-ttu-id="0fdfd-232">浮動小数点数</span><span class="sxs-lookup"><span data-stu-id="0fdfd-232">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="0fdfd-233">ヒーラーによる隠しパケットの最大比率。</span><span class="sxs-lookup"><span data-stu-id="0fdfd-233">Maximum ratio of packets concealed by the healer.</span></span></p>
<p><span data-ttu-id="0fdfd-234">このコラムは、Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="0fdfd-234">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0fdfd-235"><strong>ConcealRatioSD</strong></span><span class="sxs-lookup"><span data-stu-id="0fdfd-235"><strong>ConcealRatioSD</strong></span></span></p></td>
<td><p><span data-ttu-id="0fdfd-236">浮動小数点数</span><span class="sxs-lookup"><span data-stu-id="0fdfd-236">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="0fdfd-237">ヒーラーによって隠されたパケットの比率の標準偏差。</span><span class="sxs-lookup"><span data-stu-id="0fdfd-237">Standard deviation for the ratio of packets concealed by the healer.</span></span></p>
<p><span data-ttu-id="0fdfd-238">このコラムは、Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="0fdfd-238">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0fdfd-239"><strong>HealerPacketDropRatio</strong></span><span class="sxs-lookup"><span data-stu-id="0fdfd-239"><strong>HealerPacketDropRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="0fdfd-240">浮動小数点数</span><span class="sxs-lookup"><span data-stu-id="0fdfd-240">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="0fdfd-241">受信したパケットの合計数と比較して、ヒーラーによって削除されたパケットの比率。</span><span class="sxs-lookup"><span data-stu-id="0fdfd-241">Ratio of packets dropped by the healer compared to the total number of packets received.</span></span></p>
<p><span data-ttu-id="0fdfd-242">このコラムは、Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="0fdfd-242">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0fdfd-243"><strong>HealerFECPacketUsedRatio</strong></span><span class="sxs-lookup"><span data-stu-id="0fdfd-243"><strong>HealerFECPacketUsedRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="0fdfd-244">浮動小数点数</span><span class="sxs-lookup"><span data-stu-id="0fdfd-244">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="0fdfd-245">受信したパケットの合計数に対する、使用された転送エラー訂正パケットの比率。</span><span class="sxs-lookup"><span data-stu-id="0fdfd-245">Ratio of used forward error correction packets compared to the total number of packets received.</span></span></p>
<p><span data-ttu-id="0fdfd-246">このコラムは、Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="0fdfd-246">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0fdfd-247"><strong>MaxCompressedSamples</strong></span><span class="sxs-lookup"><span data-stu-id="0fdfd-247"><strong>MaxCompressedSamples</strong></span></span></p></td>
<td><p><span data-ttu-id="0fdfd-248">浮動小数点数</span><span class="sxs-lookup"><span data-stu-id="0fdfd-248">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="0fdfd-249">ヒーラーによって圧縮されたオーディオパケットの最大数。</span><span class="sxs-lookup"><span data-stu-id="0fdfd-249">Maximum number of audio packets that were compressed by the healer.</span></span></p>
<p><span data-ttu-id="0fdfd-250">このコラムは、Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="0fdfd-250">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0fdfd-251"><strong>LossCongestionPercent</strong></span><span class="sxs-lookup"><span data-stu-id="0fdfd-251"><strong>LossCongestionPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="0fdfd-252">浮動小数点数</span><span class="sxs-lookup"><span data-stu-id="0fdfd-252">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="0fdfd-253">通話が切断された輻輳状態であった時間の割合を示します。</span><span class="sxs-lookup"><span data-stu-id="0fdfd-253">Indicates the percentage of the time when the call was in a loss congestion state.</span></span></p>
<p><span data-ttu-id="0fdfd-254">このコラムは、Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="0fdfd-254">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0fdfd-255"><strong>DelayCongestionPercent</strong></span><span class="sxs-lookup"><span data-stu-id="0fdfd-255"><strong>DelayCongestionPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="0fdfd-256">浮動小数点数</span><span class="sxs-lookup"><span data-stu-id="0fdfd-256">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="0fdfd-257">ネットワークパケットの遅延到着により輻輳が発生した通話の割合を示します。</span><span class="sxs-lookup"><span data-stu-id="0fdfd-257">Indicates the percentage of the call during which congestion was caused by the delayed arrival of network packets.</span></span></p>
<p><span data-ttu-id="0fdfd-258">このコラムは、Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="0fdfd-258">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0fdfd-259"><strong>ContentionDetectedPercent</strong></span><span class="sxs-lookup"><span data-stu-id="0fdfd-259"><strong>ContentionDetectedPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="0fdfd-260">浮動小数点数</span><span class="sxs-lookup"><span data-stu-id="0fdfd-260">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="0fdfd-261">通話がネットワークリソースに対して競合していた時間の割合を示します。</span><span class="sxs-lookup"><span data-stu-id="0fdfd-261">Indicates the percentage of the time when the call was competing for network resources.</span></span></p>
<p><span data-ttu-id="0fdfd-262">このコラムは、Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="0fdfd-262">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0fdfd-263"><strong>BandwidthEstMin</strong></span><span class="sxs-lookup"><span data-stu-id="0fdfd-263"><strong>BandwidthEstMin</strong></span></span></p></td>
<td><p><span data-ttu-id="0fdfd-264">int</span><span class="sxs-lookup"><span data-stu-id="0fdfd-264">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="0fdfd-265">呼び出し中に測定された最小帯域幅推定値。</span><span class="sxs-lookup"><span data-stu-id="0fdfd-265">Minimum amount of bandwidth estimation measured during the call.</span></span></p>
<p><span data-ttu-id="0fdfd-266">このコラムは、Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="0fdfd-266">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0fdfd-267"><strong>BandwidthEstMax</strong></span><span class="sxs-lookup"><span data-stu-id="0fdfd-267"><strong>BandwidthEstMax</strong></span></span></p></td>
<td><p><span data-ttu-id="0fdfd-268">int</span><span class="sxs-lookup"><span data-stu-id="0fdfd-268">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="0fdfd-269">呼び出し中に測定された最大帯域幅推定値。</span><span class="sxs-lookup"><span data-stu-id="0fdfd-269">Maximum amount of bandwidth estimation measured during the call.</span></span></p>
<p><span data-ttu-id="0fdfd-270">このコラムは、Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="0fdfd-270">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0fdfd-271"><strong>BandwidthEstStdDev</strong></span><span class="sxs-lookup"><span data-stu-id="0fdfd-271"><strong>BandwidthEstStdDev</strong></span></span></p></td>
<td><p><span data-ttu-id="0fdfd-272">int</span><span class="sxs-lookup"><span data-stu-id="0fdfd-272">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="0fdfd-273">呼び出し中に測定された帯域幅推定の標準偏差。</span><span class="sxs-lookup"><span data-stu-id="0fdfd-273">Standard deviation of the bandwidth estimation measured during the call.</span></span></p>
<p><span data-ttu-id="0fdfd-274">このコラムは、Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="0fdfd-274">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0fdfd-275"><strong>BandwidthEstAvge</strong></span><span class="sxs-lookup"><span data-stu-id="0fdfd-275"><strong>BandwidthEstAvge</strong></span></span></p></td>
<td><p><span data-ttu-id="0fdfd-276">int</span><span class="sxs-lookup"><span data-stu-id="0fdfd-276">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="0fdfd-277">呼び出し中に測定された平均帯域幅推定値。</span><span class="sxs-lookup"><span data-stu-id="0fdfd-277">Average amount of bandwidth estimation measured during the call.</span></span></p>
<p><span data-ttu-id="0fdfd-278">このコラムは、Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="0fdfd-278">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0fdfd-279"><strong>RelativeOneWayTotal</strong></span><span class="sxs-lookup"><span data-stu-id="0fdfd-279"><strong>RelativeOneWayTotal</strong></span></span></p></td>
<td><p><span data-ttu-id="0fdfd-280">浮動小数点数</span><span class="sxs-lookup"><span data-stu-id="0fdfd-280">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="0fdfd-p105">一方向の遅延の合計時間。相対的な一方向の遅延によって、クライアントとサーバーの間の遅延が測定されます。</span><span class="sxs-lookup"><span data-stu-id="0fdfd-p105">Total amount of one-way latency. Relative one-way latency measures the delay between the client and the server.</span></span></p>
<p><span data-ttu-id="0fdfd-283">このコラムは、Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="0fdfd-283">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0fdfd-284"><strong>RelativeOneWayAverage</strong></span><span class="sxs-lookup"><span data-stu-id="0fdfd-284"><strong>RelativeOneWayAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="0fdfd-285">浮動小数点数</span><span class="sxs-lookup"><span data-stu-id="0fdfd-285">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="0fdfd-p106">一方向の遅延の平均時間。相対的な一方向の遅延によって、クライアントとサーバーの間の遅延が測定されます。</span><span class="sxs-lookup"><span data-stu-id="0fdfd-p106">Average amount of one-way latency. Relative one-way latency measures the delay between the client and the server.</span></span></p>
<p><span data-ttu-id="0fdfd-288">このコラムは、Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="0fdfd-288">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0fdfd-289"><strong>RelativeOneWayMax</strong></span><span class="sxs-lookup"><span data-stu-id="0fdfd-289"><strong>RelativeOneWayMax</strong></span></span></p></td>
<td><p><span data-ttu-id="0fdfd-290">浮動小数点数</span><span class="sxs-lookup"><span data-stu-id="0fdfd-290">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="0fdfd-p107">一方向の遅延の最大時間。相対的な一方向の遅延によって、クライアントとサーバーの間の遅延が測定されます。</span><span class="sxs-lookup"><span data-stu-id="0fdfd-p107">Maximum amount of one-way latency. Relative one-way latency measures the delay between the client and the server.</span></span></p>
<p><span data-ttu-id="0fdfd-293">このコラムは、Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="0fdfd-293">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0fdfd-294"><strong>RelativeOneWayBurstOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="0fdfd-294"><strong>RelativeOneWayBurstOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="0fdfd-295">int</span><span class="sxs-lookup"><span data-stu-id="0fdfd-295">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="0fdfd-p108">一方向のバーストの合計発生数。"バースト的な" 伝送とは、安定的なストリームではなく、予測できないバーストでデータが流れている伝送のことです。この指標では、クライアントとサーバーの間のデータ フローが測定されます。</span><span class="sxs-lookup"><span data-stu-id="0fdfd-p108">Total one-way burst occurrences. A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream. This metric measures data flow between the client and the server.</span></span></p>
<p><span data-ttu-id="0fdfd-299">このコラムは、Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="0fdfd-299">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0fdfd-300"><strong>RelativeOneWayBurstDensity</strong></span><span class="sxs-lookup"><span data-stu-id="0fdfd-300"><strong>RelativeOneWayBurstDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="0fdfd-301">浮動小数点数</span><span class="sxs-lookup"><span data-stu-id="0fdfd-301">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="0fdfd-p109">一方向のバーストの合計密度。"バースト的な" 伝送とは、安定的なストリームではなく、予測できないバーストでデータが流れている伝送のことです。この指標では、クライアントとサーバーの間のデータ フローが測定されます。</span><span class="sxs-lookup"><span data-stu-id="0fdfd-p109">Total one-way burst density. A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream. This metric measures data flow between the client and the server.</span></span></p>
<p><span data-ttu-id="0fdfd-305">このコラムは、Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="0fdfd-305">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0fdfd-306"><strong>RelativeOneWayBurstDuration</strong></span><span class="sxs-lookup"><span data-stu-id="0fdfd-306"><strong>RelativeOneWayBurstDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="0fdfd-307">浮動小数点数</span><span class="sxs-lookup"><span data-stu-id="0fdfd-307">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="0fdfd-p110">一方向のバーストの合計期間。"バースト的な" 伝送とは、安定的なストリームではなく、予測できないバーストでデータが流れている伝送のことです。この指標では、クライアントとサーバーの間のデータ フローが測定されます。</span><span class="sxs-lookup"><span data-stu-id="0fdfd-p110">Total one-way burst duration. A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream. This metric measures data flow between the client and the server.</span></span></p>
<p><span data-ttu-id="0fdfd-311">このコラムは、Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="0fdfd-311">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0fdfd-312"><strong>RelativeOneWayGapOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="0fdfd-312"><strong>RelativeOneWayGapOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="0fdfd-313">int</span><span class="sxs-lookup"><span data-stu-id="0fdfd-313">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="0fdfd-p111">一方向のギャップの合計発生数。"バースト的な" 伝送とは、安定的なストリームではなく、予測できないバーストでデータが流れている伝送のことです。ギャップは、これらのバースト間の遅延を示します。この指標では、クライアントとサーバーの間のデータ フローが測定されます。</span><span class="sxs-lookup"><span data-stu-id="0fdfd-p111">Total one-way gap occurrences. A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream; gaps indicate delays between these bursts. This metric measures data flow between the client and the server.</span></span></p>
<p><span data-ttu-id="0fdfd-317">このコラムは、Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="0fdfd-317">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0fdfd-318"><strong>RelativeOneWayGapDensity</strong></span><span class="sxs-lookup"><span data-stu-id="0fdfd-318"><strong>RelativeOneWayGapDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="0fdfd-319">浮動小数点数</span><span class="sxs-lookup"><span data-stu-id="0fdfd-319">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="0fdfd-p112">一方向のギャップの合計密度。"バースト的な" 伝送とは、安定的なストリームではなく、予測できないバーストでデータが流れている伝送のことです。ギャップは、これらのバースト間の遅延を示します。この指標では、クライアントとサーバーの間のデータ フローが測定されます。</span><span class="sxs-lookup"><span data-stu-id="0fdfd-p112">Total one-way gap density. A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream; gaps indicate delays between these bursts. This metric measures data flow between the client and the server.</span></span></p>
<p><span data-ttu-id="0fdfd-323">このコラムは、Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="0fdfd-323">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0fdfd-324"><strong>RelativeOneWayGapDuration</strong></span><span class="sxs-lookup"><span data-stu-id="0fdfd-324"><strong>RelativeOneWayGapDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="0fdfd-325">浮動小数点数</span><span class="sxs-lookup"><span data-stu-id="0fdfd-325">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="0fdfd-p113">一方向のギャップの合計期間。"バースト的な" 伝送とは、安定的なストリームではなく、予測できないバーストでデータが流れている伝送のことです。ギャップは、これらのバースト間の遅延を示します。この指標では、クライアントとサーバーの間のデータ フローが測定されます。</span><span class="sxs-lookup"><span data-stu-id="0fdfd-p113">Total one-way gap duration. A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream; gaps indicate delays between these bursts. This metric measures data flow between the client and the server.</span></span></p>
<p><span data-ttu-id="0fdfd-329">このコラムは、Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="0fdfd-329">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0fdfd-330"><strong>DecodeStereoPercent</strong></span><span class="sxs-lookup"><span data-stu-id="0fdfd-330"><strong>DecodeStereoPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="0fdfd-331">浮動小数点数</span><span class="sxs-lookup"><span data-stu-id="0fdfd-331">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="0fdfd-332">ステレオとしてデコードされた通話のパーセンテージ。</span><span class="sxs-lookup"><span data-stu-id="0fdfd-332">Percentage of the call decoded as stereo.</span></span></p>
<p><span data-ttu-id="0fdfd-333">このコラムは、Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="0fdfd-333">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0fdfd-334"><strong>AecRenderStereoPercent</strong></span><span class="sxs-lookup"><span data-stu-id="0fdfd-334"><strong>AecRenderStereoPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="0fdfd-335">浮動小数点数</span><span class="sxs-lookup"><span data-stu-id="0fdfd-335">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="0fdfd-336">音響エコーキャンセラでステレオとしてレンダリングされた通話のパーセンテージ。</span><span class="sxs-lookup"><span data-stu-id="0fdfd-336">Percentage of the call rendered as stereo by the acoustic echo canceller.</span></span></p>
<p><span data-ttu-id="0fdfd-337">このコラムは、Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="0fdfd-337">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0fdfd-338"><strong>AudioPostFECPLR</strong></span><span class="sxs-lookup"><span data-stu-id="0fdfd-338"><strong>AudioPostFECPLR</strong></span></span></p></td>
<td><p><span data-ttu-id="0fdfd-339">浮動小数点数</span><span class="sxs-lookup"><span data-stu-id="0fdfd-339">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="0fdfd-340">転送エラー訂正が適用された後のパケット損失率。</span><span class="sxs-lookup"><span data-stu-id="0fdfd-340">Packet loss rate after forward error correction has been applied.</span></span></p>
<p><span data-ttu-id="0fdfd-341">このコラムは、Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="0fdfd-341">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0fdfd-342"><strong>EncodeStereoPercent</strong></span><span class="sxs-lookup"><span data-stu-id="0fdfd-342"><strong>EncodeStereoPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="0fdfd-343">浮動小数点数</span><span class="sxs-lookup"><span data-stu-id="0fdfd-343">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="0fdfd-344">ステレオとしてエンコードされた通話のパーセンテージ。</span><span class="sxs-lookup"><span data-stu-id="0fdfd-344">Percentage of the call encoded as stereo.</span></span></p>
<p><span data-ttu-id="0fdfd-345">このコラムは、Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="0fdfd-345">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0fdfd-346"><strong>AecCaptureStereoPercent</strong></span><span class="sxs-lookup"><span data-stu-id="0fdfd-346"><strong>AecCaptureStereoPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="0fdfd-347">浮動小数点数</span><span class="sxs-lookup"><span data-stu-id="0fdfd-347">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="0fdfd-348">音響エコーキャンセラでステレオとしてキャプチャされた通話のパーセンテージ。</span><span class="sxs-lookup"><span data-stu-id="0fdfd-348">Percentage of the call captured as stereo by the acoustic echo canceller.</span></span></p>
<p><span data-ttu-id="0fdfd-349">このコラムは、Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="0fdfd-349">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

