---
title: 'Lync Server 2013: VideoStream テーブル'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: VideoStream table
ms:assetid: 4275ede7-5467-4a97-b8c8-a4b00917bf32
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425928(v=OCS.15)
ms:contentKeyID: 48184014
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ef5c417ff391bb3ec5954cf12d00f6de3d2e6d9b
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/16/2020
ms.locfileid: "48518564"
---
# <a name="videostream-table-in-lync-server-2013"></a><span data-ttu-id="fea66-102">Lync Server 2013 の VideoStream テーブル</span><span class="sxs-lookup"><span data-stu-id="fea66-102">VideoStream table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="fea66-103">_**トピックの最終更新日:** 2013-12-13_</span><span class="sxs-lookup"><span data-stu-id="fea66-103">_**Topic Last Modified:** 2013-12-13_</span></span>

<span data-ttu-id="fea66-104">各レコードは1つのビデオストリームを表します。</span><span class="sxs-lookup"><span data-stu-id="fea66-104">Each record represents one video stream.</span></span> <span data-ttu-id="fea66-105">通常、1つのビデオメディアラインには2つのビデオストリームが含まれています。</span><span class="sxs-lookup"><span data-stu-id="fea66-105">One video media line usually contains two video streams.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="fea66-106"><strong>列</strong></span><span class="sxs-lookup"><span data-stu-id="fea66-106"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="fea66-107"><strong>データ型</strong></span><span class="sxs-lookup"><span data-stu-id="fea66-107"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="fea66-108"><strong>キー/インデックス</strong></span><span class="sxs-lookup"><span data-stu-id="fea66-108"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="fea66-109"><strong>詳細</strong></span><span class="sxs-lookup"><span data-stu-id="fea66-109"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="fea66-110"><strong>ConferenceDateTime</strong></span><span class="sxs-lookup"><span data-stu-id="fea66-110"><strong>ConferenceDateTime</strong></span></span></p></td>
<td><p><span data-ttu-id="fea66-111">日付型</span><span class="sxs-lookup"><span data-stu-id="fea66-111">datetime</span></span></p></td>
<td><p><span data-ttu-id="fea66-112">Primary</span><span class="sxs-lookup"><span data-stu-id="fea66-112">Primary</span></span></p></td>
<td><p><span data-ttu-id="fea66-113"><a href="lync-server-2013-medialine-table.md">Lync Server 2013 の MediaLine テーブル</a>から参照されます。</span><span class="sxs-lookup"><span data-stu-id="fea66-113">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fea66-114"><strong>SessionSeq</strong></span><span class="sxs-lookup"><span data-stu-id="fea66-114"><strong>SessionSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="fea66-115">int</span><span class="sxs-lookup"><span data-stu-id="fea66-115">int</span></span></p></td>
<td><p><span data-ttu-id="fea66-116">Primary</span><span class="sxs-lookup"><span data-stu-id="fea66-116">Primary</span></span></p></td>
<td><p><span data-ttu-id="fea66-117"><a href="lync-server-2013-medialine-table.md">MediaLine テーブル (Lync Server 2013</a>) から参照される R。</span><span class="sxs-lookup"><span data-stu-id="fea66-117">R Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fea66-118"><strong>MediaLineLabel</strong></span><span class="sxs-lookup"><span data-stu-id="fea66-118"><strong>MediaLineLabel</strong></span></span></p></td>
<td><p><span data-ttu-id="fea66-119">tinyint</span><span class="sxs-lookup"><span data-stu-id="fea66-119">tinyint</span></span></p></td>
<td><p><span data-ttu-id="fea66-120">Primary</span><span class="sxs-lookup"><span data-stu-id="fea66-120">Primary</span></span></p></td>
<td><p><span data-ttu-id="fea66-121"><a href="lync-server-2013-medialine-table.md">Lync Server 2013 の MediaLine テーブル</a>から参照されます。</span><span class="sxs-lookup"><span data-stu-id="fea66-121">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fea66-122"><strong>StreamID</strong></span><span class="sxs-lookup"><span data-stu-id="fea66-122"><strong>StreamID</strong></span></span></p></td>
<td><p><span data-ttu-id="fea66-123">int</span><span class="sxs-lookup"><span data-stu-id="fea66-123">int</span></span></p></td>
<td><p><span data-ttu-id="fea66-124">Primary</span><span class="sxs-lookup"><span data-stu-id="fea66-124">Primary</span></span></p></td>
<td><p><span data-ttu-id="fea66-125">メディア ライン内の一意の ID。</span><span class="sxs-lookup"><span data-stu-id="fea66-125">Unique ID within a media line.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fea66-126"><strong>VideoPayloadDescription</strong></span><span class="sxs-lookup"><span data-stu-id="fea66-126"><strong>VideoPayloadDescription</strong></span></span></p></td>
<td><p><span data-ttu-id="fea66-127">smallint</span><span class="sxs-lookup"><span data-stu-id="fea66-127">smallint</span></span></p></td>
<td><p><span data-ttu-id="fea66-128">外部、プライマリ</span><span class="sxs-lookup"><span data-stu-id="fea66-128">Foreign, Primary</span></span></p></td>
<td><p><span data-ttu-id="fea66-129">ペイロードの説明。</span><span class="sxs-lookup"><span data-stu-id="fea66-129">Payload description.</span></span> <span data-ttu-id="fea66-130">詳細については、「 <a href="lync-server-2013-payloaddescription-table.md">Lync Server 2013 の PayloadDescription テーブル</a> 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="fea66-130">See the <a href="lync-server-2013-payloaddescription-table.md">PayloadDescription table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fea66-131"><strong>JitterInterArrival</strong></span><span class="sxs-lookup"><span data-stu-id="fea66-131"><strong>JitterInterArrival</strong></span></span></p></td>
<td><p><span data-ttu-id="fea66-132">int</span><span class="sxs-lookup"><span data-stu-id="fea66-132">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="fea66-133">リアルタイム制御プロトコル (RTCP) 統計情報に基づく平均ネットワーク ジッター。</span><span class="sxs-lookup"><span data-stu-id="fea66-133">Average network jitter from Real Time Control Protocol (RTCP) statistics.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fea66-134"><strong>JitterInterArrivalMax</strong></span><span class="sxs-lookup"><span data-stu-id="fea66-134"><strong>JitterInterArrivalMax</strong></span></span></p></td>
<td><p><span data-ttu-id="fea66-135">int</span><span class="sxs-lookup"><span data-stu-id="fea66-135">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="fea66-136">ビデオセッション時の最大ネットワークジッター。</span><span class="sxs-lookup"><span data-stu-id="fea66-136">Maximum network jitter during the video session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fea66-137"><strong>要し</strong></span><span class="sxs-lookup"><span data-stu-id="fea66-137"><strong>RoundTrip</strong></span></span></p></td>
<td><p><span data-ttu-id="fea66-138">int</span><span class="sxs-lookup"><span data-stu-id="fea66-138">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="fea66-139">RTCP 統計情報に基づく往復時間。</span><span class="sxs-lookup"><span data-stu-id="fea66-139">Round trip time from RTCP statistics.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fea66-140"><strong>RoundTripMax</strong></span><span class="sxs-lookup"><span data-stu-id="fea66-140"><strong>RoundTripMax</strong></span></span></p></td>
<td><p><span data-ttu-id="fea66-141">int</span><span class="sxs-lookup"><span data-stu-id="fea66-141">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="fea66-142">ビデオストリームの最大往復時間。</span><span class="sxs-lookup"><span data-stu-id="fea66-142">Maximum round trip time for the video stream.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fea66-143"><strong>PacketLossRate</strong></span><span class="sxs-lookup"><span data-stu-id="fea66-143"><strong>PacketLossRate</strong></span></span></p></td>
<td><p><span data-ttu-id="fea66-144">10進数 (5, 4)</span><span class="sxs-lookup"><span data-stu-id="fea66-144">decimal(5,4)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="fea66-145">通話時の平均パケット損失率。</span><span class="sxs-lookup"><span data-stu-id="fea66-145">Average packet loss rate during the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fea66-146"><strong>PacketLossRateMax</strong></span><span class="sxs-lookup"><span data-stu-id="fea66-146"><strong>PacketLossRateMax</strong></span></span></p></td>
<td><p><span data-ttu-id="fea66-147">10進数 (5, 4)</span><span class="sxs-lookup"><span data-stu-id="fea66-147">decimal(5,4)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="fea66-148">通話時に観測された最大パケット損失。</span><span class="sxs-lookup"><span data-stu-id="fea66-148">Maximum packet loss observed during the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fea66-149"><strong>PacketUtilization</strong></span><span class="sxs-lookup"><span data-stu-id="fea66-149"><strong>PacketUtilization</strong></span></span></p></td>
<td><p><span data-ttu-id="fea66-150">int</span><span class="sxs-lookup"><span data-stu-id="fea66-150">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="fea66-151">ビデオ ストリームのパケット数 (リアルタイム転送プロトコル、RTP)。</span><span class="sxs-lookup"><span data-stu-id="fea66-151">Packet count for the video stream (Real Time Transport Protocol, RTP).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fea66-152"><strong>BandwidthEst</strong></span><span class="sxs-lookup"><span data-stu-id="fea66-152"><strong>BandwidthEst</strong></span></span></p></td>
<td><p><span data-ttu-id="fea66-153">int</span><span class="sxs-lookup"><span data-stu-id="fea66-153">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="fea66-154">ビデオストリームの帯域幅の推定値。</span><span class="sxs-lookup"><span data-stu-id="fea66-154">Bandwidth estimates for the video stream.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fea66-155"><strong>VideoResolution</strong></span><span class="sxs-lookup"><span data-stu-id="fea66-155"><strong>VideoResolution</strong></span></span></p></td>
<td><p><span data-ttu-id="fea66-156">文字 (9)</span><span class="sxs-lookup"><span data-stu-id="fea66-156">char(9)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="fea66-p103">幅×高さで示すビデオの解像度 (単位ピクセル)。文字列で報告されます。</span><span class="sxs-lookup"><span data-stu-id="fea66-p103">Resolution of the video in pixels width multiplied by pixels height. Reported as a string.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fea66-159"><strong>VideoBitRateAvg</strong></span><span class="sxs-lookup"><span data-stu-id="fea66-159"><strong>VideoBitRateAvg</strong></span></span></p></td>
<td><p><span data-ttu-id="fea66-160">int</span><span class="sxs-lookup"><span data-stu-id="fea66-160">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="fea66-161">ビデオ ストリームの平均ビット レート。</span><span class="sxs-lookup"><span data-stu-id="fea66-161">Average bit rate of the video stream.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fea66-162"><strong>InboundVideoFrameRateAvg</strong></span><span class="sxs-lookup"><span data-stu-id="fea66-162"><strong>InboundVideoFrameRateAvg</strong></span></span></p></td>
<td><p><span data-ttu-id="fea66-163">10進数 (9、4)</span><span class="sxs-lookup"><span data-stu-id="fea66-163">decimal(9,4)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="fea66-164">ビデオのフレームレートを受信しました。</span><span class="sxs-lookup"><span data-stu-id="fea66-164">The video frame rate received.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fea66-165"><strong>OutboundVideoFrameRateAvg</strong></span><span class="sxs-lookup"><span data-stu-id="fea66-165"><strong>OutboundVideoFrameRateAvg</strong></span></span></p></td>
<td><p><span data-ttu-id="fea66-166">10進数 (9、4)</span><span class="sxs-lookup"><span data-stu-id="fea66-166">decimal(9,4)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="fea66-167">ビデオのフレームレートが送信されます。</span><span class="sxs-lookup"><span data-stu-id="fea66-167">The video frame rate sent.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fea66-168"><strong>VideoBitRateMax</strong></span><span class="sxs-lookup"><span data-stu-id="fea66-168"><strong>VideoBitRateMax</strong></span></span></p></td>
<td><p><span data-ttu-id="fea66-169">int</span><span class="sxs-lookup"><span data-stu-id="fea66-169">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="fea66-170">ビデオセッション時の最大ビデオビットレート。</span><span class="sxs-lookup"><span data-stu-id="fea66-170">The maximum video bit rate during the video session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fea66-171"><strong>VideoFrameLossRate</strong></span><span class="sxs-lookup"><span data-stu-id="fea66-171"><strong>VideoFrameLossRate</strong></span></span></p></td>
<td><p><span data-ttu-id="fea66-172">10進数 (9、4)</span><span class="sxs-lookup"><span data-stu-id="fea66-172">decimal(9,4)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="fea66-173">失われた合計ビデオフレーム数の割合。</span><span class="sxs-lookup"><span data-stu-id="fea66-173">The percentage of total video frames that are lost.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fea66-174"><strong>VideoFEC</strong></span><span class="sxs-lookup"><span data-stu-id="fea66-174"><strong>VideoFEC</strong></span></span></p></td>
<td><p><span data-ttu-id="fea66-175">若干</span><span class="sxs-lookup"><span data-stu-id="fea66-175">bit</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="fea66-176">注意事項なし。</span><span class="sxs-lookup"><span data-stu-id="fea66-176">Not available.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fea66-177"><strong>VideoLocalFrameLossPercentageAvg</strong></span><span class="sxs-lookup"><span data-stu-id="fea66-177"><strong>VideoLocalFrameLossPercentageAvg</strong></span></span></p></td>
<td><p><span data-ttu-id="fea66-178">10進数 (9、4)</span><span class="sxs-lookup"><span data-stu-id="fea66-178">decimal(9,4)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="fea66-179">失われた合計ビデオフレーム数の割合。</span><span class="sxs-lookup"><span data-stu-id="fea66-179">The percentage of total video frames that are lost.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fea66-180"><strong>CIFQualityRatio</strong></span><span class="sxs-lookup"><span data-stu-id="fea66-180"><strong>CIFQualityRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="fea66-181">tinyint</span><span class="sxs-lookup"><span data-stu-id="fea66-181">tinyint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="fea66-182">共通交換形式 (CIF) の解決にかけられた通話のパーセンテージ。</span><span class="sxs-lookup"><span data-stu-id="fea66-182">The percentage of the call that was at the Common Interchange Format (CIF) resolution.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fea66-183"><strong>VGAQualityRatio</strong></span><span class="sxs-lookup"><span data-stu-id="fea66-183"><strong>VGAQualityRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="fea66-184">tinyint</span><span class="sxs-lookup"><span data-stu-id="fea66-184">tinyint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="fea66-185">VGA 解像度で行われた通話のパーセンテージ。</span><span class="sxs-lookup"><span data-stu-id="fea66-185">The percentage of the call that was at VGA resolution.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fea66-186"><strong>HD720QualityRatio</strong></span><span class="sxs-lookup"><span data-stu-id="fea66-186"><strong>HD720QualityRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="fea66-187">tinyint</span><span class="sxs-lookup"><span data-stu-id="fea66-187">tinyint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="fea66-188">HD720 の解像度で行われた通話のパーセンテージ。</span><span class="sxs-lookup"><span data-stu-id="fea66-188">The percentage of the call that was at HD720 resolution.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fea66-189"><strong>NoneDropRatio</strong></span><span class="sxs-lookup"><span data-stu-id="fea66-189"><strong>NoneDropRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="fea66-190">tinyint</span><span class="sxs-lookup"><span data-stu-id="fea66-190">tinyint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="fea66-191">フレームが欠落していない通話時間のパーセンテージ。</span><span class="sxs-lookup"><span data-stu-id="fea66-191">Percentage of call duration with no frame drop.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fea66-192"><strong>B' _ '</strong></span><span class="sxs-lookup"><span data-stu-id="fea66-192"><strong>BDropRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="fea66-193">tinyint</span><span class="sxs-lookup"><span data-stu-id="fea66-193">tinyint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="fea66-194">B フレームが欠落している通話時間のパーセンテージ。</span><span class="sxs-lookup"><span data-stu-id="fea66-194">Percentage of call duration with B frame drop.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fea66-195"><strong>Bp' bp'</strong></span><span class="sxs-lookup"><span data-stu-id="fea66-195"><strong>BPDropRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="fea66-196">tinyint</span><span class="sxs-lookup"><span data-stu-id="fea66-196">tinyint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="fea66-197">BP フレームが欠落している通話時間のパーセンテージ。</span><span class="sxs-lookup"><span data-stu-id="fea66-197">Percentage of call duration with BP frame drop.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fea66-198"><strong>Bpsp/Bpprた</strong></span><span class="sxs-lookup"><span data-stu-id="fea66-198"><strong>BPSPDropRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="fea66-199">tinyint</span><span class="sxs-lookup"><span data-stu-id="fea66-199">tinyint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="fea66-200">BPSP フレームが欠落している通話時間のパーセンテージ。</span><span class="sxs-lookup"><span data-stu-id="fea66-200">Percentage of call duration with BPSP frame drop.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fea66-201"><strong>BPSPIDropRatio</strong></span><span class="sxs-lookup"><span data-stu-id="fea66-201"><strong>BPSPIDropRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="fea66-202">tinyint</span><span class="sxs-lookup"><span data-stu-id="fea66-202">tinyint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="fea66-203">BPSPI フレームが欠落している通話時間のパーセンテージ。</span><span class="sxs-lookup"><span data-stu-id="fea66-203">Percentage of call duration with BPSPI frame drop.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fea66-204"><strong>受信</strong></span><span class="sxs-lookup"><span data-stu-id="fea66-204"><strong>Inbound</strong></span></span></p></td>
<td><p><span data-ttu-id="fea66-205">若干</span><span class="sxs-lookup"><span data-stu-id="fea66-205">bit</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="fea66-206">受信側のストリームデータが受信されます。</span><span class="sxs-lookup"><span data-stu-id="fea66-206">Stream data on receiver side is received.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fea66-207"><strong>向き</strong></span><span class="sxs-lookup"><span data-stu-id="fea66-207"><strong>Outbound</strong></span></span></p></td>
<td><p><span data-ttu-id="fea66-208">若干</span><span class="sxs-lookup"><span data-stu-id="fea66-208">bit</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="fea66-209">送信側のストリームデータが受信されます。</span><span class="sxs-lookup"><span data-stu-id="fea66-209">Stream data on sender side is received.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fea66-210"><strong>SenderIsCallerPAI</strong></span><span class="sxs-lookup"><span data-stu-id="fea66-210"><strong>SenderIsCallerPAI</strong></span></span></p></td>
<td><p><span data-ttu-id="fea66-211">若干</span><span class="sxs-lookup"><span data-stu-id="fea66-211">bit</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="fea66-212">1 は、ストリームの方向が発信者から呼び出し先へ向かうことを意味します。</span><span class="sxs-lookup"><span data-stu-id="fea66-212">1 means the stream direction is from the caller to callee.</span></span></p>
<p><span data-ttu-id="fea66-213">0 は、ストリームの方向が呼び出し先から発信者へ向かうことを意味します。</span><span class="sxs-lookup"><span data-stu-id="fea66-213">0 means the stream direction is from the callee to the caller.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fea66-214"><strong>LossCongestionPercent</strong></span><span class="sxs-lookup"><span data-stu-id="fea66-214"><strong>LossCongestionPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="fea66-215">浮動小数点数</span><span class="sxs-lookup"><span data-stu-id="fea66-215">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="fea66-216">通話が切断された輻輳状態であった時間の割合を示します。</span><span class="sxs-lookup"><span data-stu-id="fea66-216">Indicates the percentage of the time when the call was in a loss congestion state.</span></span></p>
<p><span data-ttu-id="fea66-217">このコラムは、Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="fea66-217">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fea66-218"><strong>DelayCongestionPercent</strong></span><span class="sxs-lookup"><span data-stu-id="fea66-218"><strong>DelayCongestionPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="fea66-219">浮動小数点数</span><span class="sxs-lookup"><span data-stu-id="fea66-219">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="fea66-220">ネットワークパケットの遅延到着により輻輳が発生した通話の割合を示します。</span><span class="sxs-lookup"><span data-stu-id="fea66-220">Indicates the percentage of the call during which congestion was caused by the delayed arrival of network packets.</span></span></p>
<p><span data-ttu-id="fea66-221">このコラムは、Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="fea66-221">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fea66-222"><strong>ContentionDetectedPercent</strong></span><span class="sxs-lookup"><span data-stu-id="fea66-222"><strong>ContentionDetectedPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="fea66-223">浮動小数点数</span><span class="sxs-lookup"><span data-stu-id="fea66-223">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="fea66-224">通話がネットワークリソースに対して競合していた時間の割合を示します。</span><span class="sxs-lookup"><span data-stu-id="fea66-224">Indicates the percentage of the time when the call was competing for network resources.</span></span></p>
<p><span data-ttu-id="fea66-225">このコラムは、Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="fea66-225">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fea66-226"><strong>BandwidthEstMin</strong></span><span class="sxs-lookup"><span data-stu-id="fea66-226"><strong>BandwidthEstMin</strong></span></span></p></td>
<td><p><span data-ttu-id="fea66-227">int</span><span class="sxs-lookup"><span data-stu-id="fea66-227">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="fea66-228">呼び出し中に測定された最小帯域幅推定値。</span><span class="sxs-lookup"><span data-stu-id="fea66-228">Minimum amount of bandwidth estimation measured during the call.</span></span></p>
<p><span data-ttu-id="fea66-229">このコラムは、Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="fea66-229">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fea66-230"><strong>BandwidthEstMax</strong></span><span class="sxs-lookup"><span data-stu-id="fea66-230"><strong>BandwidthEstMax</strong></span></span></p></td>
<td><p><span data-ttu-id="fea66-231">int</span><span class="sxs-lookup"><span data-stu-id="fea66-231">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="fea66-232">呼び出し中に測定された最大帯域幅推定値。</span><span class="sxs-lookup"><span data-stu-id="fea66-232">Maximum amount of bandwidth estimation measured during the call.</span></span></p>
<p><span data-ttu-id="fea66-233">このコラムは、Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="fea66-233">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fea66-234"><strong>BandwidthEstStdDev</strong></span><span class="sxs-lookup"><span data-stu-id="fea66-234"><strong>BandwidthEstStdDev</strong></span></span></p></td>
<td><p><span data-ttu-id="fea66-235">int</span><span class="sxs-lookup"><span data-stu-id="fea66-235">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="fea66-236">呼び出し中に測定された帯域幅推定の標準偏差。</span><span class="sxs-lookup"><span data-stu-id="fea66-236">Standard deviation of the bandwidth estimation measured during the call.</span></span></p>
<p><span data-ttu-id="fea66-237">このコラムは、Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="fea66-237">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fea66-238"><strong>BandwidthEstAvge</strong></span><span class="sxs-lookup"><span data-stu-id="fea66-238"><strong>BandwidthEstAvge</strong></span></span></p></td>
<td><p><span data-ttu-id="fea66-239">int</span><span class="sxs-lookup"><span data-stu-id="fea66-239">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="fea66-240">呼び出し中に測定された平均帯域幅推定値。</span><span class="sxs-lookup"><span data-stu-id="fea66-240">Average amount of bandwidth estimation measured during the call.</span></span></p>
<p><span data-ttu-id="fea66-241">このコラムは、Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="fea66-241">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fea66-242"><strong>LowBandwidthForMultiview</strong></span><span class="sxs-lookup"><span data-stu-id="fea66-242"><strong>LowBandwidthForMultiview</strong></span></span></p></td>
<td><p><span data-ttu-id="fea66-243">浮動小数点数</span><span class="sxs-lookup"><span data-stu-id="fea66-243">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="fea66-244">エンドポイントが、ネットワーク接続がマルチビュービデオをサポートできなかったと判断した通話のパーセンテージ。</span><span class="sxs-lookup"><span data-stu-id="fea66-244">Percentage of the call where the endpoint determined that the network connection could not support multiview video.</span></span></p>
<p><span data-ttu-id="fea66-245">このコラムは、Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="fea66-245">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fea66-246"><strong>RelativeOneWayTotal</strong></span><span class="sxs-lookup"><span data-stu-id="fea66-246"><strong>RelativeOneWayTotal</strong></span></span></p></td>
<td><p><span data-ttu-id="fea66-247">浮動小数点数</span><span class="sxs-lookup"><span data-stu-id="fea66-247">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="fea66-p104">一方向の遅延の合計時間。相対的な一方向の遅延によって、クライアントとサーバーの間の遅延が測定されます。</span><span class="sxs-lookup"><span data-stu-id="fea66-p104">Total amount of one-way latency. Relative one-way latency measures the delay between the client and the server.</span></span></p>
<p><span data-ttu-id="fea66-250">このコラムは、Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="fea66-250">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fea66-251"><strong>RelativeOneWayAverage</strong></span><span class="sxs-lookup"><span data-stu-id="fea66-251"><strong>RelativeOneWayAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="fea66-252">浮動小数点数</span><span class="sxs-lookup"><span data-stu-id="fea66-252">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="fea66-p105">一方向の遅延の平均時間。相対的な一方向の遅延によって、クライアントとサーバーの間の遅延が測定されます。</span><span class="sxs-lookup"><span data-stu-id="fea66-p105">Average amount of one-way latency. Relative one-way latency measures the delay between the client and the server.</span></span></p>
<p><span data-ttu-id="fea66-255">このコラムは、Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="fea66-255">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fea66-256"><strong>RelativeOneWayMax</strong></span><span class="sxs-lookup"><span data-stu-id="fea66-256"><strong>RelativeOneWayMax</strong></span></span></p></td>
<td><p><span data-ttu-id="fea66-257">浮動小数点数</span><span class="sxs-lookup"><span data-stu-id="fea66-257">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="fea66-p106">一方向の遅延の最大時間。相対的な一方向の遅延によって、クライアントとサーバーの間の遅延が測定されます。</span><span class="sxs-lookup"><span data-stu-id="fea66-p106">Maximum amount of one-way latency. Relative one-way latency measures the delay between the client and the server.</span></span></p>
<p><span data-ttu-id="fea66-260">このコラムは、Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="fea66-260">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fea66-261"><strong>RelativeOneWayBurstOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="fea66-261"><strong>RelativeOneWayBurstOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="fea66-262">int</span><span class="sxs-lookup"><span data-stu-id="fea66-262">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="fea66-p107">一方向のバーストの合計発生数。"バースト的な" 伝送とは、安定的なストリームではなく、予測できないバーストでデータが流れている伝送のことです。この指標では、クライアントとサーバーの間のデータ フローが測定されます。</span><span class="sxs-lookup"><span data-stu-id="fea66-p107">Total one-way burst occurrences. A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream. This metric measures data flow between the client and the server.</span></span></p>
<p><span data-ttu-id="fea66-266">このコラムは、Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="fea66-266">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fea66-267"><strong>RelativeOneWayBurstDensity</strong></span><span class="sxs-lookup"><span data-stu-id="fea66-267"><strong>RelativeOneWayBurstDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="fea66-268">int</span><span class="sxs-lookup"><span data-stu-id="fea66-268">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="fea66-p108">一方向のバーストの合計密度。"バースト的な" 伝送とは、安定的なストリームではなく、予測できないバーストでデータが流れている伝送のことです。この指標では、クライアントとサーバーの間のデータ フローが測定されます。</span><span class="sxs-lookup"><span data-stu-id="fea66-p108">Total one-way burst density. A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream. This metric measures data flow between the client and the server.</span></span></p>
<p><span data-ttu-id="fea66-272">このコラムは、Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="fea66-272">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fea66-273"><strong>RelativeOneWayBurstDuration</strong></span><span class="sxs-lookup"><span data-stu-id="fea66-273"><strong>RelativeOneWayBurstDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="fea66-274">浮動小数点数</span><span class="sxs-lookup"><span data-stu-id="fea66-274">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="fea66-p109">一方向のバーストの合計期間。"バースト的な" 伝送とは、安定的なストリームではなく、予測できないバーストでデータが流れている伝送のことです。この指標では、クライアントとサーバーの間のデータ フローが測定されます。</span><span class="sxs-lookup"><span data-stu-id="fea66-p109">Total one-way burst duration. A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream. This metric measures data flow between the client and the server.</span></span></p>
<p><span data-ttu-id="fea66-278">このコラムは、Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="fea66-278">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fea66-279"><strong>RelativeOneWayGapOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="fea66-279"><strong>RelativeOneWayGapOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="fea66-280">int</span><span class="sxs-lookup"><span data-stu-id="fea66-280">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="fea66-p110">一方向のギャップの合計発生数。"バースト的な" 伝送とは、安定的なストリームではなく、予測できないバーストでデータが流れている伝送のことです。ギャップは、これらのバースト間の遅延を示します。この指標では、クライアントとサーバーの間のデータ フローが測定されます。</span><span class="sxs-lookup"><span data-stu-id="fea66-p110">Total one-way gap occurrences. A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream; gaps indicate delays between these bursts. This metric measures data flow between the client and the server.</span></span></p>
<p><span data-ttu-id="fea66-284">このコラムは、Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="fea66-284">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fea66-285"><strong>RelativeOneWayGapDensity</strong></span><span class="sxs-lookup"><span data-stu-id="fea66-285"><strong>RelativeOneWayGapDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="fea66-286">浮動小数点数</span><span class="sxs-lookup"><span data-stu-id="fea66-286">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="fea66-p111">一方向のギャップの合計密度。"バースト的な" 伝送とは、安定的なストリームではなく、予測できないバーストでデータが流れている伝送のことです。ギャップは、これらのバースト間の遅延を示します。この指標では、クライアントとサーバーの間のデータ フローが測定されます。</span><span class="sxs-lookup"><span data-stu-id="fea66-p111">Total one-way gap density. A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream; gaps indicate delays between these bursts. This metric measures data flow between the client and the server.</span></span></p>
<p><span data-ttu-id="fea66-290">このコラムは、Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="fea66-290">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fea66-291"><strong>RelativeOneWayGapDuration</strong></span><span class="sxs-lookup"><span data-stu-id="fea66-291"><strong>RelativeOneWayGapDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="fea66-292">浮動小数点数</span><span class="sxs-lookup"><span data-stu-id="fea66-292">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="fea66-p112">一方向のギャップの合計期間。"バースト的な" 伝送とは、安定的なストリームではなく、予測できないバーストでデータが流れている伝送のことです。ギャップは、これらのバースト間の遅延を示します。この指標では、クライアントとサーバーの間のデータ フローが測定されます。</span><span class="sxs-lookup"><span data-stu-id="fea66-p112">Total one-way gap duration. A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream; gaps indicate delays between these bursts. This metric measures data flow between the client and the server.</span></span></p>
<p><span data-ttu-id="fea66-296">このコラムは、Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="fea66-296">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fea66-297"><strong>VideoPacketLossRate</strong></span><span class="sxs-lookup"><span data-stu-id="fea66-297"><strong>VideoPacketLossRate</strong></span></span></p></td>
<td><p><span data-ttu-id="fea66-298">10進数 (9、4)</span><span class="sxs-lookup"><span data-stu-id="fea66-298">decimal(9,4)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="fea66-299">失われたビデオ パケット数の割合。</span><span class="sxs-lookup"><span data-stu-id="fea66-299">Rate at which video packets were lost.</span></span></p>
<p><span data-ttu-id="fea66-300">このコラムは、Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="fea66-300">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fea66-301"><strong>VideoAllocateBWAvg</strong></span><span class="sxs-lookup"><span data-stu-id="fea66-301"><strong>VideoAllocateBWAvg</strong></span></span></p></td>
<td><p><span data-ttu-id="fea66-302">int</span><span class="sxs-lookup"><span data-stu-id="fea66-302">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="fea66-303">ビデオに割り当てられた帯域幅の平均。</span><span class="sxs-lookup"><span data-stu-id="fea66-303">Average amount of bandwidth allocated for video.</span></span></p>
<p><span data-ttu-id="fea66-304">このコラムは、Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="fea66-304">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fea66-305"><strong>SendCodecTypes</strong></span><span class="sxs-lookup"><span data-stu-id="fea66-305"><strong>SendCodecTypes</strong></span></span></p></td>
<td><p><span data-ttu-id="fea66-306">smallint</span><span class="sxs-lookup"><span data-stu-id="fea66-306">smallint</span></span></p></td>
<td><p><span data-ttu-id="fea66-307">外部</span><span class="sxs-lookup"><span data-stu-id="fea66-307">Foreign</span></span></p></td>
<td><p><span data-ttu-id="fea66-308">送信者が使用するビデオコーデックの種類。</span><span class="sxs-lookup"><span data-stu-id="fea66-308">Type of video codecs used by the sender.</span></span> <span data-ttu-id="fea66-309">詳細については、「 <a href="lync-server-2013-codecdescription-table.md">Lync Server 2013 の CodecDescription テーブル</a> 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="fea66-309">See the <a href="lync-server-2013-codecdescription-table.md">CodecDescription table in Lync Server 2013</a> for more information.</span></span></p>
<p><span data-ttu-id="fea66-310">このコラムは、Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="fea66-310">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fea66-311"><strong>Send解像度の幅</strong></span><span class="sxs-lookup"><span data-stu-id="fea66-311"><strong>SendResolutionWidth</strong></span></span></p></td>
<td><p><span data-ttu-id="fea66-312">int</span><span class="sxs-lookup"><span data-stu-id="fea66-312">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="fea66-313">送信者が使用する解像度の幅。</span><span class="sxs-lookup"><span data-stu-id="fea66-313">Resolution width used by the sender.</span></span></p>
<p><span data-ttu-id="fea66-314">このコラムは、Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="fea66-314">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fea66-315"><strong>Send解像度の高さ</strong></span><span class="sxs-lookup"><span data-stu-id="fea66-315"><strong>SendResolutionHeight</strong></span></span></p></td>
<td><p><span data-ttu-id="fea66-316">int</span><span class="sxs-lookup"><span data-stu-id="fea66-316">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="fea66-317">送信者が使用する解像度の高さ。</span><span class="sxs-lookup"><span data-stu-id="fea66-317">Resolution height used by the sender.</span></span></p>
<p><span data-ttu-id="fea66-318">このコラムは、Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="fea66-318">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fea66-319"><strong>SendFrameRateAverage</strong></span><span class="sxs-lookup"><span data-stu-id="fea66-319"><strong>SendFrameRateAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="fea66-320">浮動小数点数</span><span class="sxs-lookup"><span data-stu-id="fea66-320">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="fea66-321">送信者が使用する平均ビデオフレームレート伝送。</span><span class="sxs-lookup"><span data-stu-id="fea66-321">Average video frame rate transmission used by the sender.</span></span></p>
<p><span data-ttu-id="fea66-322">このコラムは、Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="fea66-322">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fea66-323"><strong>SendBitRateMaximum</strong></span><span class="sxs-lookup"><span data-stu-id="fea66-323"><strong>SendBitRateMaximum</strong></span></span></p></td>
<td><p><span data-ttu-id="fea66-324">int</span><span class="sxs-lookup"><span data-stu-id="fea66-324">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="fea66-325">送信者の最大ビットレート。</span><span class="sxs-lookup"><span data-stu-id="fea66-325">Maximum bit rate for the sender.</span></span></p>
<p><span data-ttu-id="fea66-326">このコラムは、Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="fea66-326">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fea66-327"><strong>SendBitRateAverage</strong></span><span class="sxs-lookup"><span data-stu-id="fea66-327"><strong>SendBitRateAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="fea66-328">int</span><span class="sxs-lookup"><span data-stu-id="fea66-328">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="fea66-329">送信者の平均ビットレート。</span><span class="sxs-lookup"><span data-stu-id="fea66-329">Average bit rate for the sender.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fea66-330"><strong>SendVideoStreamsMax</strong></span><span class="sxs-lookup"><span data-stu-id="fea66-330"><strong>SendVideoStreamsMax</strong></span></span></p></td>
<td><p><span data-ttu-id="fea66-331">int</span><span class="sxs-lookup"><span data-stu-id="fea66-331">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="fea66-332">送信者が使用するビデオストリームの最大数。</span><span class="sxs-lookup"><span data-stu-id="fea66-332">Maximum number of video streams used by the sender.</span></span></p>
<p><span data-ttu-id="fea66-333">このコラムは、Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="fea66-333">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fea66-334"><strong>RecvCodecTypes</strong></span><span class="sxs-lookup"><span data-stu-id="fea66-334"><strong>RecvCodecTypes</strong></span></span></p></td>
<td><p><span data-ttu-id="fea66-335">smallint</span><span class="sxs-lookup"><span data-stu-id="fea66-335">smallint</span></span></p></td>
<td><p><span data-ttu-id="fea66-336">外部</span><span class="sxs-lookup"><span data-stu-id="fea66-336">Foreign</span></span></p></td>
<td><p><span data-ttu-id="fea66-337">受信者が使用するビデオコード。</span><span class="sxs-lookup"><span data-stu-id="fea66-337">Video codes used by the receiver.</span></span> <span data-ttu-id="fea66-338">詳細については、「 <a href="lync-server-2013-codecdescription-table.md">Lync Server 2013 の CodecDescription テーブル</a> 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="fea66-338">See the <a href="lync-server-2013-codecdescription-table.md">CodecDescription table in Lync Server 2013</a> for more information.</span></span></p>
<p><span data-ttu-id="fea66-339">このコラムは、Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="fea66-339">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fea66-340"><strong>RecvResolutionWidth</strong></span><span class="sxs-lookup"><span data-stu-id="fea66-340"><strong>RecvResolutionWidth</strong></span></span></p></td>
<td><p><span data-ttu-id="fea66-341">int</span><span class="sxs-lookup"><span data-stu-id="fea66-341">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="fea66-342">受信者が使用する解像度の幅。</span><span class="sxs-lookup"><span data-stu-id="fea66-342">Resolution width used by the receiver.</span></span></p>
<p><span data-ttu-id="fea66-343">このコラムは、Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="fea66-343">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fea66-344"><strong>RecvResolutionHeight</strong></span><span class="sxs-lookup"><span data-stu-id="fea66-344"><strong>RecvResolutionHeight</strong></span></span></p></td>
<td><p><span data-ttu-id="fea66-345">int</span><span class="sxs-lookup"><span data-stu-id="fea66-345">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="fea66-346">受信者が使用する解像度の高さ。</span><span class="sxs-lookup"><span data-stu-id="fea66-346">Resolution height used by the receiver.</span></span></p>
<p><span data-ttu-id="fea66-347">このコラムは、Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="fea66-347">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fea66-348"><strong>RecvFrameRateAverage</strong></span><span class="sxs-lookup"><span data-stu-id="fea66-348"><strong>RecvFrameRateAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="fea66-349">浮動小数点数</span><span class="sxs-lookup"><span data-stu-id="fea66-349">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="fea66-350">受信者が使用する平均ビデオフレームレート。</span><span class="sxs-lookup"><span data-stu-id="fea66-350">Average video frame rate used by the receiver.</span></span></p>
<p><span data-ttu-id="fea66-351">このコラムは、Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="fea66-351">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fea66-352"><strong>RecvBitRateMaximum</strong></span><span class="sxs-lookup"><span data-stu-id="fea66-352"><strong>RecvBitRateMaximum</strong></span></span></p></td>
<td><p><span data-ttu-id="fea66-353">int</span><span class="sxs-lookup"><span data-stu-id="fea66-353">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="fea66-354">受信者の最大ビットレート。</span><span class="sxs-lookup"><span data-stu-id="fea66-354">Maximum bit rate for the receiver.</span></span></p>
<p><span data-ttu-id="fea66-355">このコラムは、Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="fea66-355">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fea66-356"><strong>RecvBitRateAverage</strong></span><span class="sxs-lookup"><span data-stu-id="fea66-356"><strong>RecvBitRateAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="fea66-357">int</span><span class="sxs-lookup"><span data-stu-id="fea66-357">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="fea66-358">受信者の平均ビットレート。</span><span class="sxs-lookup"><span data-stu-id="fea66-358">Average bit rate for the receiver.</span></span></p>
<p><span data-ttu-id="fea66-359">このコラムは、Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="fea66-359">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fea66-360"><strong>RecvVideoStreamsMax</strong></span><span class="sxs-lookup"><span data-stu-id="fea66-360"><strong>RecvVideoStreamsMax</strong></span></span></p></td>
<td><p><span data-ttu-id="fea66-361">int</span><span class="sxs-lookup"><span data-stu-id="fea66-361">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="fea66-362">受信者の最大ビデオストリーム。</span><span class="sxs-lookup"><span data-stu-id="fea66-362">Maximum video streams for the receiver.</span></span></p>
<p><span data-ttu-id="fea66-363">このコラムは、Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="fea66-363">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fea66-364"><strong>RecvVideoStreamsMin</strong></span><span class="sxs-lookup"><span data-stu-id="fea66-364"><strong>RecvVideoStreamsMin</strong></span></span></p></td>
<td><p><span data-ttu-id="fea66-365">int</span><span class="sxs-lookup"><span data-stu-id="fea66-365">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="fea66-366">受信者の最小ビデオストリーム。</span><span class="sxs-lookup"><span data-stu-id="fea66-366">Minimum video streams for the receiver.</span></span></p>
<p><span data-ttu-id="fea66-367">このコラムは、Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="fea66-367">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fea66-368"><strong>RecvVideoStreamsMode</strong></span><span class="sxs-lookup"><span data-stu-id="fea66-368"><strong>RecvVideoStreamsMode</strong></span></span></p></td>
<td><p><span data-ttu-id="fea66-369">int</span><span class="sxs-lookup"><span data-stu-id="fea66-369">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="fea66-370">受信者のビデオモード (ギャラリー、単一ストリームなど)。</span><span class="sxs-lookup"><span data-stu-id="fea66-370">Video mode (for example, gallery or single stream) for the receiver.</span></span></p>
<p><span data-ttu-id="fea66-371">このコラムは、Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="fea66-371">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fea66-372"><strong>VideoPostFECPLR</strong></span><span class="sxs-lookup"><span data-stu-id="fea66-372"><strong>VideoPostFECPLR</strong></span></span></p></td>
<td><p><span data-ttu-id="fea66-373">浮動小数点数</span><span class="sxs-lookup"><span data-stu-id="fea66-373">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="fea66-374">転送エラー訂正が適用された後のパケット損失率。</span><span class="sxs-lookup"><span data-stu-id="fea66-374">Packet loss rate after forward error correction has been applied.</span></span></p>
<p><span data-ttu-id="fea66-375">このコラムは、Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="fea66-375">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fea66-376"><strong>DynamicCapabilityPercent</strong></span><span class="sxs-lookup"><span data-stu-id="fea66-376"><strong>DynamicCapabilityPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="fea66-377">浮動小数点数</span><span class="sxs-lookup"><span data-stu-id="fea66-377">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="fea66-378">動的機能フラグがアクティブだった時間の割合。</span><span class="sxs-lookup"><span data-stu-id="fea66-378">Percentage of time that the dynamic capability flag was active.</span></span></p>
<p><span data-ttu-id="fea66-379">このコラムは、Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="fea66-379">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fea66-380"><strong>解像度 (分)</strong></span><span class="sxs-lookup"><span data-stu-id="fea66-380"><strong>ResolutionMin</strong></span></span></p></td>
<td><p><span data-ttu-id="fea66-381">文字 (9)</span><span class="sxs-lookup"><span data-stu-id="fea66-381">char(9)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="fea66-382">呼び出し中に測定された最小解像度。</span><span class="sxs-lookup"><span data-stu-id="fea66-382">Minimum resolution measured during the call.</span></span></p>
<p><span data-ttu-id="fea66-383">このコラムは、Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="fea66-383">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fea66-384"><strong>LowBitRateCallPercent</strong></span><span class="sxs-lookup"><span data-stu-id="fea66-384"><strong>LowBitRateCallPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="fea66-385">浮動小数点数</span><span class="sxs-lookup"><span data-stu-id="fea66-385">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="fea66-386">低ビットレートのしきい値を下回る通話のパーセンテージ (70 キロビット/秒)。</span><span class="sxs-lookup"><span data-stu-id="fea66-386">Percentage of the call below the low bit rate threshold (70 kilobits per second).</span></span></p>
<p><span data-ttu-id="fea66-387">このコラムは、Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="fea66-387">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fea66-388"><strong>LowFrameRateCallPercent</strong></span><span class="sxs-lookup"><span data-stu-id="fea66-388"><strong>LowFrameRateCallPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="fea66-389">浮動小数点数</span><span class="sxs-lookup"><span data-stu-id="fea66-389">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="fea66-390">低フレームレートのしきい値を下回る通話のパーセンテージ (7.5 フレーム/秒、受信)。</span><span class="sxs-lookup"><span data-stu-id="fea66-390">Percentage of the call below the low frame rate threshold (7.5 frames per second, inbound).</span></span></p>
<p><span data-ttu-id="fea66-391">このコラムは、Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="fea66-391">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fea66-392"><strong>Low解決呼び出しの割合</strong></span><span class="sxs-lookup"><span data-stu-id="fea66-392"><strong>LowResolutionCallPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="fea66-393">浮動小数点数</span><span class="sxs-lookup"><span data-stu-id="fea66-393">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="fea66-394">最小解像度で発生した通話のパーセンテージ。</span><span class="sxs-lookup"><span data-stu-id="fea66-394">Percentage of the call that occurred at the lowest resolution.</span></span></p>
<p><span data-ttu-id="fea66-395">このコラムは、Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="fea66-395">This column was introduced in Microsoft Lync Server 2013.</span></span></p>
<p><span data-ttu-id="fea66-396">このコラムは、Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="fea66-396">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fea66-397"><strong>DurationSeconds</strong></span><span class="sxs-lookup"><span data-stu-id="fea66-397"><strong>DurationSeconds</strong></span></span></p></td>
<td><p><span data-ttu-id="fea66-398">浮動小数点数</span><span class="sxs-lookup"><span data-stu-id="fea66-398">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="fea66-399">通話の長さ (秒単位)。</span><span class="sxs-lookup"><span data-stu-id="fea66-399">Length of the call in seconds.</span></span></p>
<p><span data-ttu-id="fea66-400">このコラムは、Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="fea66-400">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fea66-401"><strong>IsAggregatedData</strong></span><span class="sxs-lookup"><span data-stu-id="fea66-401"><strong>IsAggregatedData</strong></span></span></p></td>
<td><p><span data-ttu-id="fea66-402">若干</span><span class="sxs-lookup"><span data-stu-id="fea66-402">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="fea66-403">データが複数の呼び出しから集約されているかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="fea66-403">Indicates whether the data has been aggregated from multiple calls.</span></span></p>
<p><span data-ttu-id="fea66-404">このコラムは、Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="fea66-404">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

