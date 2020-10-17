---
title: 'Lync Server 2013: VideoStream テーブル'
description: 'Lync Server 2013: VideoStream テーブル。'
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
ms.openlocfilehash: 0d741478e1f6290685181bff471f143e41ce9ca1
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48567993"
---
# <a name="videostream-table-in-lync-server-2013"></a><span data-ttu-id="ccd35-103">Lync Server 2013 の VideoStream テーブル</span><span class="sxs-lookup"><span data-stu-id="ccd35-103">VideoStream table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ccd35-104">_**トピックの最終更新日:** 2013-12-13_</span><span class="sxs-lookup"><span data-stu-id="ccd35-104">_**Topic Last Modified:** 2013-12-13_</span></span>

<span data-ttu-id="ccd35-105">各レコードは1つのビデオストリームを表します。</span><span class="sxs-lookup"><span data-stu-id="ccd35-105">Each record represents one video stream.</span></span> <span data-ttu-id="ccd35-106">通常、1つのビデオメディアラインには2つのビデオストリームが含まれています。</span><span class="sxs-lookup"><span data-stu-id="ccd35-106">One video media line usually contains two video streams.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="ccd35-107"><strong>列</strong></span><span class="sxs-lookup"><span data-stu-id="ccd35-107"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="ccd35-108"><strong>データ型</strong></span><span class="sxs-lookup"><span data-stu-id="ccd35-108"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="ccd35-109"><strong>キー/インデックス</strong></span><span class="sxs-lookup"><span data-stu-id="ccd35-109"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="ccd35-110"><strong>詳細</strong></span><span class="sxs-lookup"><span data-stu-id="ccd35-110"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ccd35-111"><strong>ConferenceDateTime</strong></span><span class="sxs-lookup"><span data-stu-id="ccd35-111"><strong>ConferenceDateTime</strong></span></span></p></td>
<td><p><span data-ttu-id="ccd35-112">日付型</span><span class="sxs-lookup"><span data-stu-id="ccd35-112">datetime</span></span></p></td>
<td><p><span data-ttu-id="ccd35-113">Primary</span><span class="sxs-lookup"><span data-stu-id="ccd35-113">Primary</span></span></p></td>
<td><p><span data-ttu-id="ccd35-114"><a href="lync-server-2013-medialine-table.md">Lync Server 2013 の MediaLine テーブル</a>から参照されます。</span><span class="sxs-lookup"><span data-stu-id="ccd35-114">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ccd35-115"><strong>SessionSeq</strong></span><span class="sxs-lookup"><span data-stu-id="ccd35-115"><strong>SessionSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="ccd35-116">int</span><span class="sxs-lookup"><span data-stu-id="ccd35-116">int</span></span></p></td>
<td><p><span data-ttu-id="ccd35-117">Primary</span><span class="sxs-lookup"><span data-stu-id="ccd35-117">Primary</span></span></p></td>
<td><p><span data-ttu-id="ccd35-118"><a href="lync-server-2013-medialine-table.md">MediaLine テーブル (Lync Server 2013</a>) から参照される R。</span><span class="sxs-lookup"><span data-stu-id="ccd35-118">R Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ccd35-119"><strong>MediaLineLabel</strong></span><span class="sxs-lookup"><span data-stu-id="ccd35-119"><strong>MediaLineLabel</strong></span></span></p></td>
<td><p><span data-ttu-id="ccd35-120">tinyint</span><span class="sxs-lookup"><span data-stu-id="ccd35-120">tinyint</span></span></p></td>
<td><p><span data-ttu-id="ccd35-121">Primary</span><span class="sxs-lookup"><span data-stu-id="ccd35-121">Primary</span></span></p></td>
<td><p><span data-ttu-id="ccd35-122"><a href="lync-server-2013-medialine-table.md">Lync Server 2013 の MediaLine テーブル</a>から参照されます。</span><span class="sxs-lookup"><span data-stu-id="ccd35-122">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ccd35-123"><strong>StreamID</strong></span><span class="sxs-lookup"><span data-stu-id="ccd35-123"><strong>StreamID</strong></span></span></p></td>
<td><p><span data-ttu-id="ccd35-124">int</span><span class="sxs-lookup"><span data-stu-id="ccd35-124">int</span></span></p></td>
<td><p><span data-ttu-id="ccd35-125">Primary</span><span class="sxs-lookup"><span data-stu-id="ccd35-125">Primary</span></span></p></td>
<td><p><span data-ttu-id="ccd35-126">メディア ライン内の一意の ID。</span><span class="sxs-lookup"><span data-stu-id="ccd35-126">Unique ID within a media line.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ccd35-127"><strong>VideoPayloadDescription</strong></span><span class="sxs-lookup"><span data-stu-id="ccd35-127"><strong>VideoPayloadDescription</strong></span></span></p></td>
<td><p><span data-ttu-id="ccd35-128">smallint</span><span class="sxs-lookup"><span data-stu-id="ccd35-128">smallint</span></span></p></td>
<td><p><span data-ttu-id="ccd35-129">外部、プライマリ</span><span class="sxs-lookup"><span data-stu-id="ccd35-129">Foreign, Primary</span></span></p></td>
<td><p><span data-ttu-id="ccd35-130">ペイロードの説明。</span><span class="sxs-lookup"><span data-stu-id="ccd35-130">Payload description.</span></span> <span data-ttu-id="ccd35-131">詳細については、「 <a href="lync-server-2013-payloaddescription-table.md">Lync Server 2013 の PayloadDescription テーブル</a> 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ccd35-131">See the <a href="lync-server-2013-payloaddescription-table.md">PayloadDescription table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ccd35-132"><strong>JitterInterArrival</strong></span><span class="sxs-lookup"><span data-stu-id="ccd35-132"><strong>JitterInterArrival</strong></span></span></p></td>
<td><p><span data-ttu-id="ccd35-133">int</span><span class="sxs-lookup"><span data-stu-id="ccd35-133">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="ccd35-134">リアルタイム制御プロトコル (RTCP) 統計情報に基づく平均ネットワーク ジッター。</span><span class="sxs-lookup"><span data-stu-id="ccd35-134">Average network jitter from Real Time Control Protocol (RTCP) statistics.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ccd35-135"><strong>JitterInterArrivalMax</strong></span><span class="sxs-lookup"><span data-stu-id="ccd35-135"><strong>JitterInterArrivalMax</strong></span></span></p></td>
<td><p><span data-ttu-id="ccd35-136">int</span><span class="sxs-lookup"><span data-stu-id="ccd35-136">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="ccd35-137">ビデオセッション時の最大ネットワークジッター。</span><span class="sxs-lookup"><span data-stu-id="ccd35-137">Maximum network jitter during the video session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ccd35-138"><strong>要し</strong></span><span class="sxs-lookup"><span data-stu-id="ccd35-138"><strong>RoundTrip</strong></span></span></p></td>
<td><p><span data-ttu-id="ccd35-139">int</span><span class="sxs-lookup"><span data-stu-id="ccd35-139">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="ccd35-140">RTCP 統計情報に基づく往復時間。</span><span class="sxs-lookup"><span data-stu-id="ccd35-140">Round trip time from RTCP statistics.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ccd35-141"><strong>RoundTripMax</strong></span><span class="sxs-lookup"><span data-stu-id="ccd35-141"><strong>RoundTripMax</strong></span></span></p></td>
<td><p><span data-ttu-id="ccd35-142">int</span><span class="sxs-lookup"><span data-stu-id="ccd35-142">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="ccd35-143">ビデオストリームの最大往復時間。</span><span class="sxs-lookup"><span data-stu-id="ccd35-143">Maximum round trip time for the video stream.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ccd35-144"><strong>PacketLossRate</strong></span><span class="sxs-lookup"><span data-stu-id="ccd35-144"><strong>PacketLossRate</strong></span></span></p></td>
<td><p><span data-ttu-id="ccd35-145">10進数 (5, 4)</span><span class="sxs-lookup"><span data-stu-id="ccd35-145">decimal(5,4)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="ccd35-146">通話時の平均パケット損失率。</span><span class="sxs-lookup"><span data-stu-id="ccd35-146">Average packet loss rate during the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ccd35-147"><strong>PacketLossRateMax</strong></span><span class="sxs-lookup"><span data-stu-id="ccd35-147"><strong>PacketLossRateMax</strong></span></span></p></td>
<td><p><span data-ttu-id="ccd35-148">10進数 (5, 4)</span><span class="sxs-lookup"><span data-stu-id="ccd35-148">decimal(5,4)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="ccd35-149">通話時に観測された最大パケット損失。</span><span class="sxs-lookup"><span data-stu-id="ccd35-149">Maximum packet loss observed during the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ccd35-150"><strong>PacketUtilization</strong></span><span class="sxs-lookup"><span data-stu-id="ccd35-150"><strong>PacketUtilization</strong></span></span></p></td>
<td><p><span data-ttu-id="ccd35-151">int</span><span class="sxs-lookup"><span data-stu-id="ccd35-151">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="ccd35-152">ビデオ ストリームのパケット数 (リアルタイム転送プロトコル、RTP)。</span><span class="sxs-lookup"><span data-stu-id="ccd35-152">Packet count for the video stream (Real Time Transport Protocol, RTP).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ccd35-153"><strong>BandwidthEst</strong></span><span class="sxs-lookup"><span data-stu-id="ccd35-153"><strong>BandwidthEst</strong></span></span></p></td>
<td><p><span data-ttu-id="ccd35-154">int</span><span class="sxs-lookup"><span data-stu-id="ccd35-154">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="ccd35-155">ビデオストリームの帯域幅の推定値。</span><span class="sxs-lookup"><span data-stu-id="ccd35-155">Bandwidth estimates for the video stream.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ccd35-156"><strong>VideoResolution</strong></span><span class="sxs-lookup"><span data-stu-id="ccd35-156"><strong>VideoResolution</strong></span></span></p></td>
<td><p><span data-ttu-id="ccd35-157">文字 (9)</span><span class="sxs-lookup"><span data-stu-id="ccd35-157">char(9)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="ccd35-p103">幅×高さで示すビデオの解像度 (単位ピクセル)。文字列で報告されます。</span><span class="sxs-lookup"><span data-stu-id="ccd35-p103">Resolution of the video in pixels width multiplied by pixels height. Reported as a string.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ccd35-160"><strong>VideoBitRateAvg</strong></span><span class="sxs-lookup"><span data-stu-id="ccd35-160"><strong>VideoBitRateAvg</strong></span></span></p></td>
<td><p><span data-ttu-id="ccd35-161">int</span><span class="sxs-lookup"><span data-stu-id="ccd35-161">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="ccd35-162">ビデオ ストリームの平均ビット レート。</span><span class="sxs-lookup"><span data-stu-id="ccd35-162">Average bit rate of the video stream.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ccd35-163"><strong>InboundVideoFrameRateAvg</strong></span><span class="sxs-lookup"><span data-stu-id="ccd35-163"><strong>InboundVideoFrameRateAvg</strong></span></span></p></td>
<td><p><span data-ttu-id="ccd35-164">10進数 (9、4)</span><span class="sxs-lookup"><span data-stu-id="ccd35-164">decimal(9,4)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="ccd35-165">ビデオのフレームレートを受信しました。</span><span class="sxs-lookup"><span data-stu-id="ccd35-165">The video frame rate received.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ccd35-166"><strong>OutboundVideoFrameRateAvg</strong></span><span class="sxs-lookup"><span data-stu-id="ccd35-166"><strong>OutboundVideoFrameRateAvg</strong></span></span></p></td>
<td><p><span data-ttu-id="ccd35-167">10進数 (9、4)</span><span class="sxs-lookup"><span data-stu-id="ccd35-167">decimal(9,4)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="ccd35-168">ビデオのフレームレートが送信されます。</span><span class="sxs-lookup"><span data-stu-id="ccd35-168">The video frame rate sent.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ccd35-169"><strong>VideoBitRateMax</strong></span><span class="sxs-lookup"><span data-stu-id="ccd35-169"><strong>VideoBitRateMax</strong></span></span></p></td>
<td><p><span data-ttu-id="ccd35-170">int</span><span class="sxs-lookup"><span data-stu-id="ccd35-170">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="ccd35-171">ビデオセッション時の最大ビデオビットレート。</span><span class="sxs-lookup"><span data-stu-id="ccd35-171">The maximum video bit rate during the video session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ccd35-172"><strong>VideoFrameLossRate</strong></span><span class="sxs-lookup"><span data-stu-id="ccd35-172"><strong>VideoFrameLossRate</strong></span></span></p></td>
<td><p><span data-ttu-id="ccd35-173">10進数 (9、4)</span><span class="sxs-lookup"><span data-stu-id="ccd35-173">decimal(9,4)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="ccd35-174">失われた合計ビデオフレーム数の割合。</span><span class="sxs-lookup"><span data-stu-id="ccd35-174">The percentage of total video frames that are lost.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ccd35-175"><strong>VideoFEC</strong></span><span class="sxs-lookup"><span data-stu-id="ccd35-175"><strong>VideoFEC</strong></span></span></p></td>
<td><p><span data-ttu-id="ccd35-176">若干</span><span class="sxs-lookup"><span data-stu-id="ccd35-176">bit</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="ccd35-177">注意事項なし。</span><span class="sxs-lookup"><span data-stu-id="ccd35-177">Not available.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ccd35-178"><strong>VideoLocalFrameLossPercentageAvg</strong></span><span class="sxs-lookup"><span data-stu-id="ccd35-178"><strong>VideoLocalFrameLossPercentageAvg</strong></span></span></p></td>
<td><p><span data-ttu-id="ccd35-179">10進数 (9、4)</span><span class="sxs-lookup"><span data-stu-id="ccd35-179">decimal(9,4)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="ccd35-180">失われた合計ビデオフレーム数の割合。</span><span class="sxs-lookup"><span data-stu-id="ccd35-180">The percentage of total video frames that are lost.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ccd35-181"><strong>CIFQualityRatio</strong></span><span class="sxs-lookup"><span data-stu-id="ccd35-181"><strong>CIFQualityRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="ccd35-182">tinyint</span><span class="sxs-lookup"><span data-stu-id="ccd35-182">tinyint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="ccd35-183">共通交換形式 (CIF) の解決にかけられた通話のパーセンテージ。</span><span class="sxs-lookup"><span data-stu-id="ccd35-183">The percentage of the call that was at the Common Interchange Format (CIF) resolution.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ccd35-184"><strong>VGAQualityRatio</strong></span><span class="sxs-lookup"><span data-stu-id="ccd35-184"><strong>VGAQualityRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="ccd35-185">tinyint</span><span class="sxs-lookup"><span data-stu-id="ccd35-185">tinyint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="ccd35-186">VGA 解像度で行われた通話のパーセンテージ。</span><span class="sxs-lookup"><span data-stu-id="ccd35-186">The percentage of the call that was at VGA resolution.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ccd35-187"><strong>HD720QualityRatio</strong></span><span class="sxs-lookup"><span data-stu-id="ccd35-187"><strong>HD720QualityRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="ccd35-188">tinyint</span><span class="sxs-lookup"><span data-stu-id="ccd35-188">tinyint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="ccd35-189">HD720 の解像度で行われた通話のパーセンテージ。</span><span class="sxs-lookup"><span data-stu-id="ccd35-189">The percentage of the call that was at HD720 resolution.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ccd35-190"><strong>NoneDropRatio</strong></span><span class="sxs-lookup"><span data-stu-id="ccd35-190"><strong>NoneDropRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="ccd35-191">tinyint</span><span class="sxs-lookup"><span data-stu-id="ccd35-191">tinyint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="ccd35-192">フレームが欠落していない通話時間のパーセンテージ。</span><span class="sxs-lookup"><span data-stu-id="ccd35-192">Percentage of call duration with no frame drop.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ccd35-193"><strong>B' _ '</strong></span><span class="sxs-lookup"><span data-stu-id="ccd35-193"><strong>BDropRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="ccd35-194">tinyint</span><span class="sxs-lookup"><span data-stu-id="ccd35-194">tinyint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="ccd35-195">B フレームが欠落している通話時間のパーセンテージ。</span><span class="sxs-lookup"><span data-stu-id="ccd35-195">Percentage of call duration with B frame drop.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ccd35-196"><strong>Bp' bp'</strong></span><span class="sxs-lookup"><span data-stu-id="ccd35-196"><strong>BPDropRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="ccd35-197">tinyint</span><span class="sxs-lookup"><span data-stu-id="ccd35-197">tinyint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="ccd35-198">BP フレームが欠落している通話時間のパーセンテージ。</span><span class="sxs-lookup"><span data-stu-id="ccd35-198">Percentage of call duration with BP frame drop.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ccd35-199"><strong>Bpsp/Bpprた</strong></span><span class="sxs-lookup"><span data-stu-id="ccd35-199"><strong>BPSPDropRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="ccd35-200">tinyint</span><span class="sxs-lookup"><span data-stu-id="ccd35-200">tinyint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="ccd35-201">BPSP フレームが欠落している通話時間のパーセンテージ。</span><span class="sxs-lookup"><span data-stu-id="ccd35-201">Percentage of call duration with BPSP frame drop.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ccd35-202"><strong>BPSPIDropRatio</strong></span><span class="sxs-lookup"><span data-stu-id="ccd35-202"><strong>BPSPIDropRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="ccd35-203">tinyint</span><span class="sxs-lookup"><span data-stu-id="ccd35-203">tinyint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="ccd35-204">BPSPI フレームが欠落している通話時間のパーセンテージ。</span><span class="sxs-lookup"><span data-stu-id="ccd35-204">Percentage of call duration with BPSPI frame drop.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ccd35-205"><strong>受信</strong></span><span class="sxs-lookup"><span data-stu-id="ccd35-205"><strong>Inbound</strong></span></span></p></td>
<td><p><span data-ttu-id="ccd35-206">若干</span><span class="sxs-lookup"><span data-stu-id="ccd35-206">bit</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="ccd35-207">受信側のストリームデータが受信されます。</span><span class="sxs-lookup"><span data-stu-id="ccd35-207">Stream data on receiver side is received.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ccd35-208"><strong>向き</strong></span><span class="sxs-lookup"><span data-stu-id="ccd35-208"><strong>Outbound</strong></span></span></p></td>
<td><p><span data-ttu-id="ccd35-209">若干</span><span class="sxs-lookup"><span data-stu-id="ccd35-209">bit</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="ccd35-210">送信側のストリームデータが受信されます。</span><span class="sxs-lookup"><span data-stu-id="ccd35-210">Stream data on sender side is received.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ccd35-211"><strong>SenderIsCallerPAI</strong></span><span class="sxs-lookup"><span data-stu-id="ccd35-211"><strong>SenderIsCallerPAI</strong></span></span></p></td>
<td><p><span data-ttu-id="ccd35-212">若干</span><span class="sxs-lookup"><span data-stu-id="ccd35-212">bit</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="ccd35-213">1 は、ストリームの方向が発信者から呼び出し先へ向かうことを意味します。</span><span class="sxs-lookup"><span data-stu-id="ccd35-213">1 means the stream direction is from the caller to callee.</span></span></p>
<p><span data-ttu-id="ccd35-214">0 は、ストリームの方向が呼び出し先から発信者へ向かうことを意味します。</span><span class="sxs-lookup"><span data-stu-id="ccd35-214">0 means the stream direction is from the callee to the caller.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ccd35-215"><strong>LossCongestionPercent</strong></span><span class="sxs-lookup"><span data-stu-id="ccd35-215"><strong>LossCongestionPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="ccd35-216">浮動小数点数</span><span class="sxs-lookup"><span data-stu-id="ccd35-216">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="ccd35-217">通話が切断された輻輳状態であった時間の割合を示します。</span><span class="sxs-lookup"><span data-stu-id="ccd35-217">Indicates the percentage of the time when the call was in a loss congestion state.</span></span></p>
<p><span data-ttu-id="ccd35-218">このコラムは、Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="ccd35-218">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ccd35-219"><strong>DelayCongestionPercent</strong></span><span class="sxs-lookup"><span data-stu-id="ccd35-219"><strong>DelayCongestionPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="ccd35-220">浮動小数点数</span><span class="sxs-lookup"><span data-stu-id="ccd35-220">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="ccd35-221">ネットワークパケットの遅延到着により輻輳が発生した通話の割合を示します。</span><span class="sxs-lookup"><span data-stu-id="ccd35-221">Indicates the percentage of the call during which congestion was caused by the delayed arrival of network packets.</span></span></p>
<p><span data-ttu-id="ccd35-222">このコラムは、Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="ccd35-222">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ccd35-223"><strong>ContentionDetectedPercent</strong></span><span class="sxs-lookup"><span data-stu-id="ccd35-223"><strong>ContentionDetectedPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="ccd35-224">浮動小数点数</span><span class="sxs-lookup"><span data-stu-id="ccd35-224">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="ccd35-225">通話がネットワークリソースに対して競合していた時間の割合を示します。</span><span class="sxs-lookup"><span data-stu-id="ccd35-225">Indicates the percentage of the time when the call was competing for network resources.</span></span></p>
<p><span data-ttu-id="ccd35-226">このコラムは、Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="ccd35-226">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ccd35-227"><strong>BandwidthEstMin</strong></span><span class="sxs-lookup"><span data-stu-id="ccd35-227"><strong>BandwidthEstMin</strong></span></span></p></td>
<td><p><span data-ttu-id="ccd35-228">int</span><span class="sxs-lookup"><span data-stu-id="ccd35-228">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="ccd35-229">呼び出し中に測定された最小帯域幅推定値。</span><span class="sxs-lookup"><span data-stu-id="ccd35-229">Minimum amount of bandwidth estimation measured during the call.</span></span></p>
<p><span data-ttu-id="ccd35-230">このコラムは、Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="ccd35-230">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ccd35-231"><strong>BandwidthEstMax</strong></span><span class="sxs-lookup"><span data-stu-id="ccd35-231"><strong>BandwidthEstMax</strong></span></span></p></td>
<td><p><span data-ttu-id="ccd35-232">int</span><span class="sxs-lookup"><span data-stu-id="ccd35-232">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="ccd35-233">呼び出し中に測定された最大帯域幅推定値。</span><span class="sxs-lookup"><span data-stu-id="ccd35-233">Maximum amount of bandwidth estimation measured during the call.</span></span></p>
<p><span data-ttu-id="ccd35-234">このコラムは、Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="ccd35-234">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ccd35-235"><strong>BandwidthEstStdDev</strong></span><span class="sxs-lookup"><span data-stu-id="ccd35-235"><strong>BandwidthEstStdDev</strong></span></span></p></td>
<td><p><span data-ttu-id="ccd35-236">int</span><span class="sxs-lookup"><span data-stu-id="ccd35-236">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="ccd35-237">呼び出し中に測定された帯域幅推定の標準偏差。</span><span class="sxs-lookup"><span data-stu-id="ccd35-237">Standard deviation of the bandwidth estimation measured during the call.</span></span></p>
<p><span data-ttu-id="ccd35-238">このコラムは、Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="ccd35-238">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ccd35-239"><strong>BandwidthEstAvge</strong></span><span class="sxs-lookup"><span data-stu-id="ccd35-239"><strong>BandwidthEstAvge</strong></span></span></p></td>
<td><p><span data-ttu-id="ccd35-240">int</span><span class="sxs-lookup"><span data-stu-id="ccd35-240">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="ccd35-241">呼び出し中に測定された平均帯域幅推定値。</span><span class="sxs-lookup"><span data-stu-id="ccd35-241">Average amount of bandwidth estimation measured during the call.</span></span></p>
<p><span data-ttu-id="ccd35-242">このコラムは、Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="ccd35-242">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ccd35-243"><strong>LowBandwidthForMultiview</strong></span><span class="sxs-lookup"><span data-stu-id="ccd35-243"><strong>LowBandwidthForMultiview</strong></span></span></p></td>
<td><p><span data-ttu-id="ccd35-244">浮動小数点数</span><span class="sxs-lookup"><span data-stu-id="ccd35-244">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="ccd35-245">エンドポイントが、ネットワーク接続がマルチビュービデオをサポートできなかったと判断した通話のパーセンテージ。</span><span class="sxs-lookup"><span data-stu-id="ccd35-245">Percentage of the call where the endpoint determined that the network connection could not support multiview video.</span></span></p>
<p><span data-ttu-id="ccd35-246">このコラムは、Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="ccd35-246">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ccd35-247"><strong>RelativeOneWayTotal</strong></span><span class="sxs-lookup"><span data-stu-id="ccd35-247"><strong>RelativeOneWayTotal</strong></span></span></p></td>
<td><p><span data-ttu-id="ccd35-248">浮動小数点数</span><span class="sxs-lookup"><span data-stu-id="ccd35-248">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="ccd35-p104">一方向の遅延の合計時間。相対的な一方向の遅延によって、クライアントとサーバーの間の遅延が測定されます。</span><span class="sxs-lookup"><span data-stu-id="ccd35-p104">Total amount of one-way latency. Relative one-way latency measures the delay between the client and the server.</span></span></p>
<p><span data-ttu-id="ccd35-251">このコラムは、Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="ccd35-251">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ccd35-252"><strong>RelativeOneWayAverage</strong></span><span class="sxs-lookup"><span data-stu-id="ccd35-252"><strong>RelativeOneWayAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="ccd35-253">浮動小数点数</span><span class="sxs-lookup"><span data-stu-id="ccd35-253">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="ccd35-p105">一方向の遅延の平均時間。相対的な一方向の遅延によって、クライアントとサーバーの間の遅延が測定されます。</span><span class="sxs-lookup"><span data-stu-id="ccd35-p105">Average amount of one-way latency. Relative one-way latency measures the delay between the client and the server.</span></span></p>
<p><span data-ttu-id="ccd35-256">このコラムは、Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="ccd35-256">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ccd35-257"><strong>RelativeOneWayMax</strong></span><span class="sxs-lookup"><span data-stu-id="ccd35-257"><strong>RelativeOneWayMax</strong></span></span></p></td>
<td><p><span data-ttu-id="ccd35-258">浮動小数点数</span><span class="sxs-lookup"><span data-stu-id="ccd35-258">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="ccd35-p106">一方向の遅延の最大時間。相対的な一方向の遅延によって、クライアントとサーバーの間の遅延が測定されます。</span><span class="sxs-lookup"><span data-stu-id="ccd35-p106">Maximum amount of one-way latency. Relative one-way latency measures the delay between the client and the server.</span></span></p>
<p><span data-ttu-id="ccd35-261">このコラムは、Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="ccd35-261">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ccd35-262"><strong>RelativeOneWayBurstOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="ccd35-262"><strong>RelativeOneWayBurstOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="ccd35-263">int</span><span class="sxs-lookup"><span data-stu-id="ccd35-263">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="ccd35-p107">一方向のバーストの合計発生数。"バースト的な" 伝送とは、安定的なストリームではなく、予測できないバーストでデータが流れている伝送のことです。この指標では、クライアントとサーバーの間のデータ フローが測定されます。</span><span class="sxs-lookup"><span data-stu-id="ccd35-p107">Total one-way burst occurrences. A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream. This metric measures data flow between the client and the server.</span></span></p>
<p><span data-ttu-id="ccd35-267">このコラムは、Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="ccd35-267">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ccd35-268"><strong>RelativeOneWayBurstDensity</strong></span><span class="sxs-lookup"><span data-stu-id="ccd35-268"><strong>RelativeOneWayBurstDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="ccd35-269">int</span><span class="sxs-lookup"><span data-stu-id="ccd35-269">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="ccd35-p108">一方向のバーストの合計密度。"バースト的な" 伝送とは、安定的なストリームではなく、予測できないバーストでデータが流れている伝送のことです。この指標では、クライアントとサーバーの間のデータ フローが測定されます。</span><span class="sxs-lookup"><span data-stu-id="ccd35-p108">Total one-way burst density. A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream. This metric measures data flow between the client and the server.</span></span></p>
<p><span data-ttu-id="ccd35-273">このコラムは、Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="ccd35-273">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ccd35-274"><strong>RelativeOneWayBurstDuration</strong></span><span class="sxs-lookup"><span data-stu-id="ccd35-274"><strong>RelativeOneWayBurstDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="ccd35-275">浮動小数点数</span><span class="sxs-lookup"><span data-stu-id="ccd35-275">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="ccd35-p109">一方向のバーストの合計期間。"バースト的な" 伝送とは、安定的なストリームではなく、予測できないバーストでデータが流れている伝送のことです。この指標では、クライアントとサーバーの間のデータ フローが測定されます。</span><span class="sxs-lookup"><span data-stu-id="ccd35-p109">Total one-way burst duration. A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream. This metric measures data flow between the client and the server.</span></span></p>
<p><span data-ttu-id="ccd35-279">このコラムは、Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="ccd35-279">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ccd35-280"><strong>RelativeOneWayGapOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="ccd35-280"><strong>RelativeOneWayGapOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="ccd35-281">int</span><span class="sxs-lookup"><span data-stu-id="ccd35-281">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="ccd35-p110">一方向のギャップの合計発生数。"バースト的な" 伝送とは、安定的なストリームではなく、予測できないバーストでデータが流れている伝送のことです。ギャップは、これらのバースト間の遅延を示します。この指標では、クライアントとサーバーの間のデータ フローが測定されます。</span><span class="sxs-lookup"><span data-stu-id="ccd35-p110">Total one-way gap occurrences. A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream; gaps indicate delays between these bursts. This metric measures data flow between the client and the server.</span></span></p>
<p><span data-ttu-id="ccd35-285">このコラムは、Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="ccd35-285">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ccd35-286"><strong>RelativeOneWayGapDensity</strong></span><span class="sxs-lookup"><span data-stu-id="ccd35-286"><strong>RelativeOneWayGapDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="ccd35-287">浮動小数点数</span><span class="sxs-lookup"><span data-stu-id="ccd35-287">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="ccd35-p111">一方向のギャップの合計密度。"バースト的な" 伝送とは、安定的なストリームではなく、予測できないバーストでデータが流れている伝送のことです。ギャップは、これらのバースト間の遅延を示します。この指標では、クライアントとサーバーの間のデータ フローが測定されます。</span><span class="sxs-lookup"><span data-stu-id="ccd35-p111">Total one-way gap density. A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream; gaps indicate delays between these bursts. This metric measures data flow between the client and the server.</span></span></p>
<p><span data-ttu-id="ccd35-291">このコラムは、Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="ccd35-291">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ccd35-292"><strong>RelativeOneWayGapDuration</strong></span><span class="sxs-lookup"><span data-stu-id="ccd35-292"><strong>RelativeOneWayGapDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="ccd35-293">浮動小数点数</span><span class="sxs-lookup"><span data-stu-id="ccd35-293">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="ccd35-p112">一方向のギャップの合計期間。"バースト的な" 伝送とは、安定的なストリームではなく、予測できないバーストでデータが流れている伝送のことです。ギャップは、これらのバースト間の遅延を示します。この指標では、クライアントとサーバーの間のデータ フローが測定されます。</span><span class="sxs-lookup"><span data-stu-id="ccd35-p112">Total one-way gap duration. A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream; gaps indicate delays between these bursts. This metric measures data flow between the client and the server.</span></span></p>
<p><span data-ttu-id="ccd35-297">このコラムは、Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="ccd35-297">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ccd35-298"><strong>VideoPacketLossRate</strong></span><span class="sxs-lookup"><span data-stu-id="ccd35-298"><strong>VideoPacketLossRate</strong></span></span></p></td>
<td><p><span data-ttu-id="ccd35-299">10進数 (9、4)</span><span class="sxs-lookup"><span data-stu-id="ccd35-299">decimal(9,4)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="ccd35-300">失われたビデオ パケット数の割合。</span><span class="sxs-lookup"><span data-stu-id="ccd35-300">Rate at which video packets were lost.</span></span></p>
<p><span data-ttu-id="ccd35-301">このコラムは、Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="ccd35-301">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ccd35-302"><strong>VideoAllocateBWAvg</strong></span><span class="sxs-lookup"><span data-stu-id="ccd35-302"><strong>VideoAllocateBWAvg</strong></span></span></p></td>
<td><p><span data-ttu-id="ccd35-303">int</span><span class="sxs-lookup"><span data-stu-id="ccd35-303">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="ccd35-304">ビデオに割り当てられた帯域幅の平均。</span><span class="sxs-lookup"><span data-stu-id="ccd35-304">Average amount of bandwidth allocated for video.</span></span></p>
<p><span data-ttu-id="ccd35-305">このコラムは、Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="ccd35-305">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ccd35-306"><strong>SendCodecTypes</strong></span><span class="sxs-lookup"><span data-stu-id="ccd35-306"><strong>SendCodecTypes</strong></span></span></p></td>
<td><p><span data-ttu-id="ccd35-307">smallint</span><span class="sxs-lookup"><span data-stu-id="ccd35-307">smallint</span></span></p></td>
<td><p><span data-ttu-id="ccd35-308">外部</span><span class="sxs-lookup"><span data-stu-id="ccd35-308">Foreign</span></span></p></td>
<td><p><span data-ttu-id="ccd35-309">送信者が使用するビデオコーデックの種類。</span><span class="sxs-lookup"><span data-stu-id="ccd35-309">Type of video codecs used by the sender.</span></span> <span data-ttu-id="ccd35-310">詳細については、「 <a href="lync-server-2013-codecdescription-table.md">Lync Server 2013 の CodecDescription テーブル</a> 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ccd35-310">See the <a href="lync-server-2013-codecdescription-table.md">CodecDescription table in Lync Server 2013</a> for more information.</span></span></p>
<p><span data-ttu-id="ccd35-311">このコラムは、Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="ccd35-311">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ccd35-312"><strong>Send解像度の幅</strong></span><span class="sxs-lookup"><span data-stu-id="ccd35-312"><strong>SendResolutionWidth</strong></span></span></p></td>
<td><p><span data-ttu-id="ccd35-313">int</span><span class="sxs-lookup"><span data-stu-id="ccd35-313">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="ccd35-314">送信者が使用する解像度の幅。</span><span class="sxs-lookup"><span data-stu-id="ccd35-314">Resolution width used by the sender.</span></span></p>
<p><span data-ttu-id="ccd35-315">このコラムは、Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="ccd35-315">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ccd35-316"><strong>Send解像度の高さ</strong></span><span class="sxs-lookup"><span data-stu-id="ccd35-316"><strong>SendResolutionHeight</strong></span></span></p></td>
<td><p><span data-ttu-id="ccd35-317">int</span><span class="sxs-lookup"><span data-stu-id="ccd35-317">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="ccd35-318">送信者が使用する解像度の高さ。</span><span class="sxs-lookup"><span data-stu-id="ccd35-318">Resolution height used by the sender.</span></span></p>
<p><span data-ttu-id="ccd35-319">このコラムは、Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="ccd35-319">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ccd35-320"><strong>SendFrameRateAverage</strong></span><span class="sxs-lookup"><span data-stu-id="ccd35-320"><strong>SendFrameRateAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="ccd35-321">浮動小数点数</span><span class="sxs-lookup"><span data-stu-id="ccd35-321">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="ccd35-322">送信者が使用する平均ビデオフレームレート伝送。</span><span class="sxs-lookup"><span data-stu-id="ccd35-322">Average video frame rate transmission used by the sender.</span></span></p>
<p><span data-ttu-id="ccd35-323">このコラムは、Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="ccd35-323">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ccd35-324"><strong>SendBitRateMaximum</strong></span><span class="sxs-lookup"><span data-stu-id="ccd35-324"><strong>SendBitRateMaximum</strong></span></span></p></td>
<td><p><span data-ttu-id="ccd35-325">int</span><span class="sxs-lookup"><span data-stu-id="ccd35-325">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="ccd35-326">送信者の最大ビットレート。</span><span class="sxs-lookup"><span data-stu-id="ccd35-326">Maximum bit rate for the sender.</span></span></p>
<p><span data-ttu-id="ccd35-327">このコラムは、Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="ccd35-327">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ccd35-328"><strong>SendBitRateAverage</strong></span><span class="sxs-lookup"><span data-stu-id="ccd35-328"><strong>SendBitRateAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="ccd35-329">int</span><span class="sxs-lookup"><span data-stu-id="ccd35-329">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="ccd35-330">送信者の平均ビットレート。</span><span class="sxs-lookup"><span data-stu-id="ccd35-330">Average bit rate for the sender.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ccd35-331"><strong>SendVideoStreamsMax</strong></span><span class="sxs-lookup"><span data-stu-id="ccd35-331"><strong>SendVideoStreamsMax</strong></span></span></p></td>
<td><p><span data-ttu-id="ccd35-332">int</span><span class="sxs-lookup"><span data-stu-id="ccd35-332">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="ccd35-333">送信者が使用するビデオストリームの最大数。</span><span class="sxs-lookup"><span data-stu-id="ccd35-333">Maximum number of video streams used by the sender.</span></span></p>
<p><span data-ttu-id="ccd35-334">このコラムは、Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="ccd35-334">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ccd35-335"><strong>RecvCodecTypes</strong></span><span class="sxs-lookup"><span data-stu-id="ccd35-335"><strong>RecvCodecTypes</strong></span></span></p></td>
<td><p><span data-ttu-id="ccd35-336">smallint</span><span class="sxs-lookup"><span data-stu-id="ccd35-336">smallint</span></span></p></td>
<td><p><span data-ttu-id="ccd35-337">外部</span><span class="sxs-lookup"><span data-stu-id="ccd35-337">Foreign</span></span></p></td>
<td><p><span data-ttu-id="ccd35-338">受信者が使用するビデオコード。</span><span class="sxs-lookup"><span data-stu-id="ccd35-338">Video codes used by the receiver.</span></span> <span data-ttu-id="ccd35-339">詳細については、「 <a href="lync-server-2013-codecdescription-table.md">Lync Server 2013 の CodecDescription テーブル</a> 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ccd35-339">See the <a href="lync-server-2013-codecdescription-table.md">CodecDescription table in Lync Server 2013</a> for more information.</span></span></p>
<p><span data-ttu-id="ccd35-340">このコラムは、Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="ccd35-340">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ccd35-341"><strong>RecvResolutionWidth</strong></span><span class="sxs-lookup"><span data-stu-id="ccd35-341"><strong>RecvResolutionWidth</strong></span></span></p></td>
<td><p><span data-ttu-id="ccd35-342">int</span><span class="sxs-lookup"><span data-stu-id="ccd35-342">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="ccd35-343">受信者が使用する解像度の幅。</span><span class="sxs-lookup"><span data-stu-id="ccd35-343">Resolution width used by the receiver.</span></span></p>
<p><span data-ttu-id="ccd35-344">このコラムは、Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="ccd35-344">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ccd35-345"><strong>RecvResolutionHeight</strong></span><span class="sxs-lookup"><span data-stu-id="ccd35-345"><strong>RecvResolutionHeight</strong></span></span></p></td>
<td><p><span data-ttu-id="ccd35-346">int</span><span class="sxs-lookup"><span data-stu-id="ccd35-346">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="ccd35-347">受信者が使用する解像度の高さ。</span><span class="sxs-lookup"><span data-stu-id="ccd35-347">Resolution height used by the receiver.</span></span></p>
<p><span data-ttu-id="ccd35-348">このコラムは、Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="ccd35-348">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ccd35-349"><strong>RecvFrameRateAverage</strong></span><span class="sxs-lookup"><span data-stu-id="ccd35-349"><strong>RecvFrameRateAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="ccd35-350">浮動小数点数</span><span class="sxs-lookup"><span data-stu-id="ccd35-350">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="ccd35-351">受信者が使用する平均ビデオフレームレート。</span><span class="sxs-lookup"><span data-stu-id="ccd35-351">Average video frame rate used by the receiver.</span></span></p>
<p><span data-ttu-id="ccd35-352">このコラムは、Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="ccd35-352">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ccd35-353"><strong>RecvBitRateMaximum</strong></span><span class="sxs-lookup"><span data-stu-id="ccd35-353"><strong>RecvBitRateMaximum</strong></span></span></p></td>
<td><p><span data-ttu-id="ccd35-354">int</span><span class="sxs-lookup"><span data-stu-id="ccd35-354">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="ccd35-355">受信者の最大ビットレート。</span><span class="sxs-lookup"><span data-stu-id="ccd35-355">Maximum bit rate for the receiver.</span></span></p>
<p><span data-ttu-id="ccd35-356">このコラムは、Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="ccd35-356">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ccd35-357"><strong>RecvBitRateAverage</strong></span><span class="sxs-lookup"><span data-stu-id="ccd35-357"><strong>RecvBitRateAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="ccd35-358">int</span><span class="sxs-lookup"><span data-stu-id="ccd35-358">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="ccd35-359">受信者の平均ビットレート。</span><span class="sxs-lookup"><span data-stu-id="ccd35-359">Average bit rate for the receiver.</span></span></p>
<p><span data-ttu-id="ccd35-360">このコラムは、Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="ccd35-360">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ccd35-361"><strong>RecvVideoStreamsMax</strong></span><span class="sxs-lookup"><span data-stu-id="ccd35-361"><strong>RecvVideoStreamsMax</strong></span></span></p></td>
<td><p><span data-ttu-id="ccd35-362">int</span><span class="sxs-lookup"><span data-stu-id="ccd35-362">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="ccd35-363">受信者の最大ビデオストリーム。</span><span class="sxs-lookup"><span data-stu-id="ccd35-363">Maximum video streams for the receiver.</span></span></p>
<p><span data-ttu-id="ccd35-364">このコラムは、Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="ccd35-364">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ccd35-365"><strong>RecvVideoStreamsMin</strong></span><span class="sxs-lookup"><span data-stu-id="ccd35-365"><strong>RecvVideoStreamsMin</strong></span></span></p></td>
<td><p><span data-ttu-id="ccd35-366">int</span><span class="sxs-lookup"><span data-stu-id="ccd35-366">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="ccd35-367">受信者の最小ビデオストリーム。</span><span class="sxs-lookup"><span data-stu-id="ccd35-367">Minimum video streams for the receiver.</span></span></p>
<p><span data-ttu-id="ccd35-368">このコラムは、Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="ccd35-368">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ccd35-369"><strong>RecvVideoStreamsMode</strong></span><span class="sxs-lookup"><span data-stu-id="ccd35-369"><strong>RecvVideoStreamsMode</strong></span></span></p></td>
<td><p><span data-ttu-id="ccd35-370">int</span><span class="sxs-lookup"><span data-stu-id="ccd35-370">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="ccd35-371">受信者のビデオモード (ギャラリー、単一ストリームなど)。</span><span class="sxs-lookup"><span data-stu-id="ccd35-371">Video mode (for example, gallery or single stream) for the receiver.</span></span></p>
<p><span data-ttu-id="ccd35-372">このコラムは、Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="ccd35-372">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ccd35-373"><strong>VideoPostFECPLR</strong></span><span class="sxs-lookup"><span data-stu-id="ccd35-373"><strong>VideoPostFECPLR</strong></span></span></p></td>
<td><p><span data-ttu-id="ccd35-374">浮動小数点数</span><span class="sxs-lookup"><span data-stu-id="ccd35-374">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="ccd35-375">転送エラー訂正が適用された後のパケット損失率。</span><span class="sxs-lookup"><span data-stu-id="ccd35-375">Packet loss rate after forward error correction has been applied.</span></span></p>
<p><span data-ttu-id="ccd35-376">このコラムは、Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="ccd35-376">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ccd35-377"><strong>DynamicCapabilityPercent</strong></span><span class="sxs-lookup"><span data-stu-id="ccd35-377"><strong>DynamicCapabilityPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="ccd35-378">浮動小数点数</span><span class="sxs-lookup"><span data-stu-id="ccd35-378">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="ccd35-379">動的機能フラグがアクティブだった時間の割合。</span><span class="sxs-lookup"><span data-stu-id="ccd35-379">Percentage of time that the dynamic capability flag was active.</span></span></p>
<p><span data-ttu-id="ccd35-380">このコラムは、Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="ccd35-380">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ccd35-381"><strong>解像度 (分)</strong></span><span class="sxs-lookup"><span data-stu-id="ccd35-381"><strong>ResolutionMin</strong></span></span></p></td>
<td><p><span data-ttu-id="ccd35-382">文字 (9)</span><span class="sxs-lookup"><span data-stu-id="ccd35-382">char(9)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="ccd35-383">呼び出し中に測定された最小解像度。</span><span class="sxs-lookup"><span data-stu-id="ccd35-383">Minimum resolution measured during the call.</span></span></p>
<p><span data-ttu-id="ccd35-384">このコラムは、Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="ccd35-384">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ccd35-385"><strong>LowBitRateCallPercent</strong></span><span class="sxs-lookup"><span data-stu-id="ccd35-385"><strong>LowBitRateCallPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="ccd35-386">浮動小数点数</span><span class="sxs-lookup"><span data-stu-id="ccd35-386">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="ccd35-387">低ビットレートのしきい値を下回る通話のパーセンテージ (70 キロビット/秒)。</span><span class="sxs-lookup"><span data-stu-id="ccd35-387">Percentage of the call below the low bit rate threshold (70 kilobits per second).</span></span></p>
<p><span data-ttu-id="ccd35-388">このコラムは、Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="ccd35-388">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ccd35-389"><strong>LowFrameRateCallPercent</strong></span><span class="sxs-lookup"><span data-stu-id="ccd35-389"><strong>LowFrameRateCallPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="ccd35-390">浮動小数点数</span><span class="sxs-lookup"><span data-stu-id="ccd35-390">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="ccd35-391">低フレームレートのしきい値を下回る通話のパーセンテージ (7.5 フレーム/秒、受信)。</span><span class="sxs-lookup"><span data-stu-id="ccd35-391">Percentage of the call below the low frame rate threshold (7.5 frames per second, inbound).</span></span></p>
<p><span data-ttu-id="ccd35-392">このコラムは、Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="ccd35-392">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ccd35-393"><strong>Low解決呼び出しの割合</strong></span><span class="sxs-lookup"><span data-stu-id="ccd35-393"><strong>LowResolutionCallPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="ccd35-394">浮動小数点数</span><span class="sxs-lookup"><span data-stu-id="ccd35-394">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="ccd35-395">最小解像度で発生した通話のパーセンテージ。</span><span class="sxs-lookup"><span data-stu-id="ccd35-395">Percentage of the call that occurred at the lowest resolution.</span></span></p>
<p><span data-ttu-id="ccd35-396">このコラムは、Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="ccd35-396">This column was introduced in Microsoft Lync Server 2013.</span></span></p>
<p><span data-ttu-id="ccd35-397">このコラムは、Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="ccd35-397">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ccd35-398"><strong>DurationSeconds</strong></span><span class="sxs-lookup"><span data-stu-id="ccd35-398"><strong>DurationSeconds</strong></span></span></p></td>
<td><p><span data-ttu-id="ccd35-399">浮動小数点数</span><span class="sxs-lookup"><span data-stu-id="ccd35-399">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="ccd35-400">通話の長さ (秒単位)。</span><span class="sxs-lookup"><span data-stu-id="ccd35-400">Length of the call in seconds.</span></span></p>
<p><span data-ttu-id="ccd35-401">このコラムは、Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="ccd35-401">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ccd35-402"><strong>IsAggregatedData</strong></span><span class="sxs-lookup"><span data-stu-id="ccd35-402"><strong>IsAggregatedData</strong></span></span></p></td>
<td><p><span data-ttu-id="ccd35-403">若干</span><span class="sxs-lookup"><span data-stu-id="ccd35-403">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="ccd35-404">データが複数の呼び出しから集約されているかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="ccd35-404">Indicates whether the data has been aggregated from multiple calls.</span></span></p>
<p><span data-ttu-id="ccd35-405">このコラムは、Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="ccd35-405">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

