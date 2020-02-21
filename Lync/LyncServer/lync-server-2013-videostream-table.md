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
ms.openlocfilehash: a313419ca4072fe4d1841ba66a9cb603671e6c56
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/21/2020
ms.locfileid: "42211649"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="videostream-table-in-lync-server-2013"></a><span data-ttu-id="f17be-102">Lync Server 2013 の VideoStream テーブル</span><span class="sxs-lookup"><span data-stu-id="f17be-102">VideoStream table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f17be-103">_**トピックの最終更新日:** 2013-12-13_</span><span class="sxs-lookup"><span data-stu-id="f17be-103">_**Topic Last Modified:** 2013-12-13_</span></span>

<span data-ttu-id="f17be-104">各レコードは1つのビデオストリームを表します。</span><span class="sxs-lookup"><span data-stu-id="f17be-104">Each record represents one video stream.</span></span> <span data-ttu-id="f17be-105">通常、1つのビデオメディアラインには2つのビデオストリームが含まれています。</span><span class="sxs-lookup"><span data-stu-id="f17be-105">One video media line usually contains two video streams.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="f17be-106"><strong>列</strong></span><span class="sxs-lookup"><span data-stu-id="f17be-106"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="f17be-107"><strong>データ型</strong></span><span class="sxs-lookup"><span data-stu-id="f17be-107"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="f17be-108"><strong>キー/インデックス</strong></span><span class="sxs-lookup"><span data-stu-id="f17be-108"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="f17be-109"><strong>詳細</strong></span><span class="sxs-lookup"><span data-stu-id="f17be-109"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="f17be-110"><strong>ConferenceDateTime</strong></span><span class="sxs-lookup"><span data-stu-id="f17be-110"><strong>ConferenceDateTime</strong></span></span></p></td>
<td><p><span data-ttu-id="f17be-111">日付型</span><span class="sxs-lookup"><span data-stu-id="f17be-111">datetime</span></span></p></td>
<td><p><span data-ttu-id="f17be-112">Primary</span><span class="sxs-lookup"><span data-stu-id="f17be-112">Primary</span></span></p></td>
<td><p><span data-ttu-id="f17be-113"><a href="lync-server-2013-medialine-table.md">Lync Server 2013 の MediaLine テーブル</a>から参照されます。</span><span class="sxs-lookup"><span data-stu-id="f17be-113">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f17be-114"><strong>SessionSeq</strong></span><span class="sxs-lookup"><span data-stu-id="f17be-114"><strong>SessionSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="f17be-115">int</span><span class="sxs-lookup"><span data-stu-id="f17be-115">int</span></span></p></td>
<td><p><span data-ttu-id="f17be-116">Primary</span><span class="sxs-lookup"><span data-stu-id="f17be-116">Primary</span></span></p></td>
<td><p><span data-ttu-id="f17be-117"><a href="lync-server-2013-medialine-table.md">MediaLine テーブル (Lync Server 2013</a>) から参照される R。</span><span class="sxs-lookup"><span data-stu-id="f17be-117">R Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f17be-118"><strong>MediaLineLabel</strong></span><span class="sxs-lookup"><span data-stu-id="f17be-118"><strong>MediaLineLabel</strong></span></span></p></td>
<td><p><span data-ttu-id="f17be-119">tinyint</span><span class="sxs-lookup"><span data-stu-id="f17be-119">tinyint</span></span></p></td>
<td><p><span data-ttu-id="f17be-120">Primary</span><span class="sxs-lookup"><span data-stu-id="f17be-120">Primary</span></span></p></td>
<td><p><span data-ttu-id="f17be-121"><a href="lync-server-2013-medialine-table.md">Lync Server 2013 の MediaLine テーブル</a>から参照されます。</span><span class="sxs-lookup"><span data-stu-id="f17be-121">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f17be-122"><strong>StreamID</strong></span><span class="sxs-lookup"><span data-stu-id="f17be-122"><strong>StreamID</strong></span></span></p></td>
<td><p><span data-ttu-id="f17be-123">int</span><span class="sxs-lookup"><span data-stu-id="f17be-123">int</span></span></p></td>
<td><p><span data-ttu-id="f17be-124">Primary</span><span class="sxs-lookup"><span data-stu-id="f17be-124">Primary</span></span></p></td>
<td><p><span data-ttu-id="f17be-125">メディア ライン内の一意の ID。</span><span class="sxs-lookup"><span data-stu-id="f17be-125">Unique ID within a media line.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f17be-126"><strong>VideoPayloadDescription</strong></span><span class="sxs-lookup"><span data-stu-id="f17be-126"><strong>VideoPayloadDescription</strong></span></span></p></td>
<td><p><span data-ttu-id="f17be-127">smallint</span><span class="sxs-lookup"><span data-stu-id="f17be-127">smallint</span></span></p></td>
<td><p><span data-ttu-id="f17be-128">外部、プライマリ</span><span class="sxs-lookup"><span data-stu-id="f17be-128">Foreign, Primary</span></span></p></td>
<td><p><span data-ttu-id="f17be-129">ペイロードの説明。</span><span class="sxs-lookup"><span data-stu-id="f17be-129">Payload description.</span></span> <span data-ttu-id="f17be-130">詳細については、「 <a href="lync-server-2013-payloaddescription-table.md">Lync Server 2013 の PayloadDescription テーブル</a>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f17be-130">See the <a href="lync-server-2013-payloaddescription-table.md">PayloadDescription table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f17be-131"><strong>JitterInterArrival</strong></span><span class="sxs-lookup"><span data-stu-id="f17be-131"><strong>JitterInterArrival</strong></span></span></p></td>
<td><p><span data-ttu-id="f17be-132">int</span><span class="sxs-lookup"><span data-stu-id="f17be-132">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="f17be-133">リアルタイム制御プロトコル (RTCP) 統計情報に基づく平均ネットワーク ジッター。</span><span class="sxs-lookup"><span data-stu-id="f17be-133">Average network jitter from Real Time Control Protocol (RTCP) statistics.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f17be-134"><strong>JitterInterArrivalMax</strong></span><span class="sxs-lookup"><span data-stu-id="f17be-134"><strong>JitterInterArrivalMax</strong></span></span></p></td>
<td><p><span data-ttu-id="f17be-135">int</span><span class="sxs-lookup"><span data-stu-id="f17be-135">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="f17be-136">ビデオセッション時の最大ネットワークジッター。</span><span class="sxs-lookup"><span data-stu-id="f17be-136">Maximum network jitter during the video session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f17be-137"><strong>要し</strong></span><span class="sxs-lookup"><span data-stu-id="f17be-137"><strong>RoundTrip</strong></span></span></p></td>
<td><p><span data-ttu-id="f17be-138">int</span><span class="sxs-lookup"><span data-stu-id="f17be-138">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="f17be-139">RTCP 統計情報に基づく往復時間。</span><span class="sxs-lookup"><span data-stu-id="f17be-139">Round trip time from RTCP statistics.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f17be-140"><strong>RoundTripMax</strong></span><span class="sxs-lookup"><span data-stu-id="f17be-140"><strong>RoundTripMax</strong></span></span></p></td>
<td><p><span data-ttu-id="f17be-141">int</span><span class="sxs-lookup"><span data-stu-id="f17be-141">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="f17be-142">ビデオストリームの最大往復時間。</span><span class="sxs-lookup"><span data-stu-id="f17be-142">Maximum round trip time for the video stream.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f17be-143"><strong>PacketLossRate</strong></span><span class="sxs-lookup"><span data-stu-id="f17be-143"><strong>PacketLossRate</strong></span></span></p></td>
<td><p><span data-ttu-id="f17be-144">10進数 (5, 4)</span><span class="sxs-lookup"><span data-stu-id="f17be-144">decimal(5,4)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="f17be-145">通話時の平均パケット損失率。</span><span class="sxs-lookup"><span data-stu-id="f17be-145">Average packet loss rate during the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f17be-146"><strong>PacketLossRateMax</strong></span><span class="sxs-lookup"><span data-stu-id="f17be-146"><strong>PacketLossRateMax</strong></span></span></p></td>
<td><p><span data-ttu-id="f17be-147">10進数 (5, 4)</span><span class="sxs-lookup"><span data-stu-id="f17be-147">decimal(5,4)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="f17be-148">通話時に観測された最大パケット損失。</span><span class="sxs-lookup"><span data-stu-id="f17be-148">Maximum packet loss observed during the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f17be-149"><strong>PacketUtilization</strong></span><span class="sxs-lookup"><span data-stu-id="f17be-149"><strong>PacketUtilization</strong></span></span></p></td>
<td><p><span data-ttu-id="f17be-150">int</span><span class="sxs-lookup"><span data-stu-id="f17be-150">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="f17be-151">ビデオ ストリームのパケット数 (リアルタイム転送プロトコル、RTP)。</span><span class="sxs-lookup"><span data-stu-id="f17be-151">Packet count for the video stream (Real Time Transport Protocol, RTP).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f17be-152"><strong>BandwidthEst</strong></span><span class="sxs-lookup"><span data-stu-id="f17be-152"><strong>BandwidthEst</strong></span></span></p></td>
<td><p><span data-ttu-id="f17be-153">int</span><span class="sxs-lookup"><span data-stu-id="f17be-153">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="f17be-154">ビデオストリームの帯域幅の推定値。</span><span class="sxs-lookup"><span data-stu-id="f17be-154">Bandwidth estimates for the video stream.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f17be-155"><strong>VideoResolution</strong></span><span class="sxs-lookup"><span data-stu-id="f17be-155"><strong>VideoResolution</strong></span></span></p></td>
<td><p><span data-ttu-id="f17be-156">文字 (9)</span><span class="sxs-lookup"><span data-stu-id="f17be-156">char(9)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="f17be-p103">幅×高さで示すビデオの解像度 (単位ピクセル)。文字列で報告されます。</span><span class="sxs-lookup"><span data-stu-id="f17be-p103">Resolution of the video in pixels width multiplied by pixels height. Reported as a string.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f17be-159"><strong>VideoBitRateAvg</strong></span><span class="sxs-lookup"><span data-stu-id="f17be-159"><strong>VideoBitRateAvg</strong></span></span></p></td>
<td><p><span data-ttu-id="f17be-160">int</span><span class="sxs-lookup"><span data-stu-id="f17be-160">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="f17be-161">ビデオ ストリームの平均ビット レート。</span><span class="sxs-lookup"><span data-stu-id="f17be-161">Average bit rate of the video stream.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f17be-162"><strong>InboundVideoFrameRateAvg</strong></span><span class="sxs-lookup"><span data-stu-id="f17be-162"><strong>InboundVideoFrameRateAvg</strong></span></span></p></td>
<td><p><span data-ttu-id="f17be-163">10進数 (9、4)</span><span class="sxs-lookup"><span data-stu-id="f17be-163">decimal(9,4)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="f17be-164">ビデオのフレームレートを受信しました。</span><span class="sxs-lookup"><span data-stu-id="f17be-164">The video frame rate received.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f17be-165"><strong>OutboundVideoFrameRateAvg</strong></span><span class="sxs-lookup"><span data-stu-id="f17be-165"><strong>OutboundVideoFrameRateAvg</strong></span></span></p></td>
<td><p><span data-ttu-id="f17be-166">10進数 (9、4)</span><span class="sxs-lookup"><span data-stu-id="f17be-166">decimal(9,4)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="f17be-167">ビデオのフレームレートが送信されます。</span><span class="sxs-lookup"><span data-stu-id="f17be-167">The video frame rate sent.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f17be-168"><strong>VideoBitRateMax</strong></span><span class="sxs-lookup"><span data-stu-id="f17be-168"><strong>VideoBitRateMax</strong></span></span></p></td>
<td><p><span data-ttu-id="f17be-169">int</span><span class="sxs-lookup"><span data-stu-id="f17be-169">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="f17be-170">ビデオセッション時の最大ビデオビットレート。</span><span class="sxs-lookup"><span data-stu-id="f17be-170">The maximum video bit rate during the video session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f17be-171"><strong>VideoFrameLossRate</strong></span><span class="sxs-lookup"><span data-stu-id="f17be-171"><strong>VideoFrameLossRate</strong></span></span></p></td>
<td><p><span data-ttu-id="f17be-172">10進数 (9、4)</span><span class="sxs-lookup"><span data-stu-id="f17be-172">decimal(9,4)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="f17be-173">失われた合計ビデオフレーム数の割合。</span><span class="sxs-lookup"><span data-stu-id="f17be-173">The percentage of total video frames that are lost.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f17be-174"><strong>VideoFEC</strong></span><span class="sxs-lookup"><span data-stu-id="f17be-174"><strong>VideoFEC</strong></span></span></p></td>
<td><p><span data-ttu-id="f17be-175">若干</span><span class="sxs-lookup"><span data-stu-id="f17be-175">bit</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="f17be-176">注意事項なし。</span><span class="sxs-lookup"><span data-stu-id="f17be-176">Not available.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f17be-177"><strong>VideoLocalFrameLossPercentageAvg</strong></span><span class="sxs-lookup"><span data-stu-id="f17be-177"><strong>VideoLocalFrameLossPercentageAvg</strong></span></span></p></td>
<td><p><span data-ttu-id="f17be-178">10進数 (9、4)</span><span class="sxs-lookup"><span data-stu-id="f17be-178">decimal(9,4)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f17be-179">失われた合計ビデオフレーム数の割合。</span><span class="sxs-lookup"><span data-stu-id="f17be-179">The percentage of total video frames that are lost.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f17be-180"><strong>CIFQualityRatio</strong></span><span class="sxs-lookup"><span data-stu-id="f17be-180"><strong>CIFQualityRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="f17be-181">tinyint</span><span class="sxs-lookup"><span data-stu-id="f17be-181">tinyint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f17be-182">共通交換形式 (CIF) の解決にかけられた通話のパーセンテージ。</span><span class="sxs-lookup"><span data-stu-id="f17be-182">The percentage of the call that was at the Common Interchange Format (CIF) resolution.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f17be-183"><strong>VGAQualityRatio</strong></span><span class="sxs-lookup"><span data-stu-id="f17be-183"><strong>VGAQualityRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="f17be-184">tinyint</span><span class="sxs-lookup"><span data-stu-id="f17be-184">tinyint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f17be-185">VGA 解像度で行われた通話のパーセンテージ。</span><span class="sxs-lookup"><span data-stu-id="f17be-185">The percentage of the call that was at VGA resolution.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f17be-186"><strong>HD720QualityRatio</strong></span><span class="sxs-lookup"><span data-stu-id="f17be-186"><strong>HD720QualityRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="f17be-187">tinyint</span><span class="sxs-lookup"><span data-stu-id="f17be-187">tinyint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f17be-188">HD720 の解像度で行われた通話のパーセンテージ。</span><span class="sxs-lookup"><span data-stu-id="f17be-188">The percentage of the call that was at HD720 resolution.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f17be-189"><strong>NoneDropRatio</strong></span><span class="sxs-lookup"><span data-stu-id="f17be-189"><strong>NoneDropRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="f17be-190">tinyint</span><span class="sxs-lookup"><span data-stu-id="f17be-190">tinyint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f17be-191">フレームが欠落していない通話時間のパーセンテージ。</span><span class="sxs-lookup"><span data-stu-id="f17be-191">Percentage of call duration with no frame drop.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f17be-192"><strong>B' _ '</strong></span><span class="sxs-lookup"><span data-stu-id="f17be-192"><strong>BDropRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="f17be-193">tinyint</span><span class="sxs-lookup"><span data-stu-id="f17be-193">tinyint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f17be-194">B フレームが欠落している通話時間のパーセンテージ。</span><span class="sxs-lookup"><span data-stu-id="f17be-194">Percentage of call duration with B frame drop.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f17be-195"><strong>Bp' bp'</strong></span><span class="sxs-lookup"><span data-stu-id="f17be-195"><strong>BPDropRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="f17be-196">tinyint</span><span class="sxs-lookup"><span data-stu-id="f17be-196">tinyint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f17be-197">BP フレームが欠落している通話時間のパーセンテージ。</span><span class="sxs-lookup"><span data-stu-id="f17be-197">Percentage of call duration with BP frame drop.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f17be-198"><strong>Bpsp/Bpprた</strong></span><span class="sxs-lookup"><span data-stu-id="f17be-198"><strong>BPSPDropRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="f17be-199">tinyint</span><span class="sxs-lookup"><span data-stu-id="f17be-199">tinyint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f17be-200">BPSP フレームが欠落している通話時間のパーセンテージ。</span><span class="sxs-lookup"><span data-stu-id="f17be-200">Percentage of call duration with BPSP frame drop.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f17be-201"><strong>BPSPIDropRatio</strong></span><span class="sxs-lookup"><span data-stu-id="f17be-201"><strong>BPSPIDropRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="f17be-202">tinyint</span><span class="sxs-lookup"><span data-stu-id="f17be-202">tinyint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f17be-203">BPSPI フレームが欠落している通話時間のパーセンテージ。</span><span class="sxs-lookup"><span data-stu-id="f17be-203">Percentage of call duration with BPSPI frame drop.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f17be-204"><strong>受信</strong></span><span class="sxs-lookup"><span data-stu-id="f17be-204"><strong>Inbound</strong></span></span></p></td>
<td><p><span data-ttu-id="f17be-205">若干</span><span class="sxs-lookup"><span data-stu-id="f17be-205">bit</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="f17be-206">受信側のストリームデータが受信されます。</span><span class="sxs-lookup"><span data-stu-id="f17be-206">Stream data on receiver side is received.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f17be-207"><strong>送信</strong></span><span class="sxs-lookup"><span data-stu-id="f17be-207"><strong>Outbound</strong></span></span></p></td>
<td><p><span data-ttu-id="f17be-208">若干</span><span class="sxs-lookup"><span data-stu-id="f17be-208">bit</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="f17be-209">送信側のストリームデータが受信されます。</span><span class="sxs-lookup"><span data-stu-id="f17be-209">Stream data on sender side is received.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f17be-210"><strong>SenderIsCallerPAI</strong></span><span class="sxs-lookup"><span data-stu-id="f17be-210"><strong>SenderIsCallerPAI</strong></span></span></p></td>
<td><p><span data-ttu-id="f17be-211">若干</span><span class="sxs-lookup"><span data-stu-id="f17be-211">bit</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="f17be-212">1 は、ストリームの方向が発信者から呼び出し先へ向かうことを意味します。</span><span class="sxs-lookup"><span data-stu-id="f17be-212">1 means the stream direction is from the caller to callee.</span></span></p>
<p><span data-ttu-id="f17be-213">0 は、ストリームの方向が呼び出し先から発信者へ向かうことを意味します。</span><span class="sxs-lookup"><span data-stu-id="f17be-213">0 means the stream direction is from the callee to the caller.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f17be-214"><strong>LossCongestionPercent</strong></span><span class="sxs-lookup"><span data-stu-id="f17be-214"><strong>LossCongestionPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="f17be-215">浮動小数点数</span><span class="sxs-lookup"><span data-stu-id="f17be-215">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f17be-216">通話が切断された輻輳状態であった時間の割合を示します。</span><span class="sxs-lookup"><span data-stu-id="f17be-216">Indicates the percentage of the time when the call was in a loss congestion state.</span></span></p>
<p><span data-ttu-id="f17be-217">このコラムは、Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="f17be-217">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f17be-218"><strong>DelayCongestionPercent</strong></span><span class="sxs-lookup"><span data-stu-id="f17be-218"><strong>DelayCongestionPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="f17be-219">浮動小数点数</span><span class="sxs-lookup"><span data-stu-id="f17be-219">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f17be-220">ネットワークパケットの遅延到着により輻輳が発生した通話の割合を示します。</span><span class="sxs-lookup"><span data-stu-id="f17be-220">Indicates the percentage of the call during which congestion was caused by the delayed arrival of network packets.</span></span></p>
<p><span data-ttu-id="f17be-221">このコラムは、Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="f17be-221">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f17be-222"><strong>ContentionDetectedPercent</strong></span><span class="sxs-lookup"><span data-stu-id="f17be-222"><strong>ContentionDetectedPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="f17be-223">浮動小数点数</span><span class="sxs-lookup"><span data-stu-id="f17be-223">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f17be-224">通話がネットワークリソースに対して競合していた時間の割合を示します。</span><span class="sxs-lookup"><span data-stu-id="f17be-224">Indicates the percentage of the time when the call was competing for network resources.</span></span></p>
<p><span data-ttu-id="f17be-225">このコラムは、Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="f17be-225">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f17be-226"><strong>BandwidthEstMin</strong></span><span class="sxs-lookup"><span data-stu-id="f17be-226"><strong>BandwidthEstMin</strong></span></span></p></td>
<td><p><span data-ttu-id="f17be-227">int</span><span class="sxs-lookup"><span data-stu-id="f17be-227">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f17be-228">呼び出し中に測定された最小帯域幅推定値。</span><span class="sxs-lookup"><span data-stu-id="f17be-228">Minimum amount of bandwidth estimation measured during the call.</span></span></p>
<p><span data-ttu-id="f17be-229">このコラムは、Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="f17be-229">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f17be-230"><strong>BandwidthEstMax</strong></span><span class="sxs-lookup"><span data-stu-id="f17be-230"><strong>BandwidthEstMax</strong></span></span></p></td>
<td><p><span data-ttu-id="f17be-231">int</span><span class="sxs-lookup"><span data-stu-id="f17be-231">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f17be-232">呼び出し中に測定された最大帯域幅推定値。</span><span class="sxs-lookup"><span data-stu-id="f17be-232">Maximum amount of bandwidth estimation measured during the call.</span></span></p>
<p><span data-ttu-id="f17be-233">このコラムは、Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="f17be-233">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f17be-234"><strong>BandwidthEstStdDev</strong></span><span class="sxs-lookup"><span data-stu-id="f17be-234"><strong>BandwidthEstStdDev</strong></span></span></p></td>
<td><p><span data-ttu-id="f17be-235">int</span><span class="sxs-lookup"><span data-stu-id="f17be-235">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f17be-236">呼び出し中に測定された帯域幅推定の標準偏差。</span><span class="sxs-lookup"><span data-stu-id="f17be-236">Standard deviation of the bandwidth estimation measured during the call.</span></span></p>
<p><span data-ttu-id="f17be-237">このコラムは、Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="f17be-237">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f17be-238"><strong>BandwidthEstAvge</strong></span><span class="sxs-lookup"><span data-stu-id="f17be-238"><strong>BandwidthEstAvge</strong></span></span></p></td>
<td><p><span data-ttu-id="f17be-239">int</span><span class="sxs-lookup"><span data-stu-id="f17be-239">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f17be-240">呼び出し中に測定された平均帯域幅推定値。</span><span class="sxs-lookup"><span data-stu-id="f17be-240">Average amount of bandwidth estimation measured during the call.</span></span></p>
<p><span data-ttu-id="f17be-241">このコラムは、Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="f17be-241">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f17be-242"><strong>LowBandwidthForMultiview</strong></span><span class="sxs-lookup"><span data-stu-id="f17be-242"><strong>LowBandwidthForMultiview</strong></span></span></p></td>
<td><p><span data-ttu-id="f17be-243">浮動小数点数</span><span class="sxs-lookup"><span data-stu-id="f17be-243">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f17be-244">エンドポイントが、ネットワーク接続がマルチビュービデオをサポートできなかったと判断した通話のパーセンテージ。</span><span class="sxs-lookup"><span data-stu-id="f17be-244">Percentage of the call where the endpoint determined that the network connection could not support multiview video.</span></span></p>
<p><span data-ttu-id="f17be-245">このコラムは、Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="f17be-245">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f17be-246"><strong>RelativeOneWayTotal</strong></span><span class="sxs-lookup"><span data-stu-id="f17be-246"><strong>RelativeOneWayTotal</strong></span></span></p></td>
<td><p><span data-ttu-id="f17be-247">浮動小数点数</span><span class="sxs-lookup"><span data-stu-id="f17be-247">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f17be-p104">一方向の遅延の合計時間。相対的な一方向の遅延によって、クライアントとサーバーの間の遅延が測定されます。</span><span class="sxs-lookup"><span data-stu-id="f17be-p104">Total amount of one-way latency. Relative one-way latency measures the delay between the client and the server.</span></span></p>
<p><span data-ttu-id="f17be-250">このコラムは、Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="f17be-250">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f17be-251"><strong>RelativeOneWayAverage</strong></span><span class="sxs-lookup"><span data-stu-id="f17be-251"><strong>RelativeOneWayAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="f17be-252">浮動小数点数</span><span class="sxs-lookup"><span data-stu-id="f17be-252">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f17be-p105">一方向の遅延の平均時間。相対的な一方向の遅延によって、クライアントとサーバーの間の遅延が測定されます。</span><span class="sxs-lookup"><span data-stu-id="f17be-p105">Average amount of one-way latency. Relative one-way latency measures the delay between the client and the server.</span></span></p>
<p><span data-ttu-id="f17be-255">このコラムは、Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="f17be-255">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f17be-256"><strong>RelativeOneWayMax</strong></span><span class="sxs-lookup"><span data-stu-id="f17be-256"><strong>RelativeOneWayMax</strong></span></span></p></td>
<td><p><span data-ttu-id="f17be-257">浮動小数点数</span><span class="sxs-lookup"><span data-stu-id="f17be-257">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f17be-p106">一方向の遅延の最大時間。相対的な一方向の遅延によって、クライアントとサーバーの間の遅延が測定されます。</span><span class="sxs-lookup"><span data-stu-id="f17be-p106">Maximum amount of one-way latency. Relative one-way latency measures the delay between the client and the server.</span></span></p>
<p><span data-ttu-id="f17be-260">このコラムは、Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="f17be-260">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f17be-261"><strong>RelativeOneWayBurstOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="f17be-261"><strong>RelativeOneWayBurstOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="f17be-262">int</span><span class="sxs-lookup"><span data-stu-id="f17be-262">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f17be-p107">一方向のバーストの合計発生数。"バースト的な" 伝送とは、安定的なストリームではなく、予測できないバーストでデータが流れている伝送のことです。この指標では、クライアントとサーバーの間のデータ フローが測定されます。</span><span class="sxs-lookup"><span data-stu-id="f17be-p107">Total one-way burst occurrences. A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream. This metric measures data flow between the client and the server.</span></span></p>
<p><span data-ttu-id="f17be-266">このコラムは、Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="f17be-266">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f17be-267"><strong>RelativeOneWayBurstDensity</strong></span><span class="sxs-lookup"><span data-stu-id="f17be-267"><strong>RelativeOneWayBurstDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="f17be-268">int</span><span class="sxs-lookup"><span data-stu-id="f17be-268">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f17be-p108">一方向のバーストの合計密度。"バースト的な" 伝送とは、安定的なストリームではなく、予測できないバーストでデータが流れている伝送のことです。この指標では、クライアントとサーバーの間のデータ フローが測定されます。</span><span class="sxs-lookup"><span data-stu-id="f17be-p108">Total one-way burst density. A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream. This metric measures data flow between the client and the server.</span></span></p>
<p><span data-ttu-id="f17be-272">このコラムは、Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="f17be-272">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f17be-273"><strong>RelativeOneWayBurstDuration</strong></span><span class="sxs-lookup"><span data-stu-id="f17be-273"><strong>RelativeOneWayBurstDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="f17be-274">浮動小数点数</span><span class="sxs-lookup"><span data-stu-id="f17be-274">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f17be-p109">一方向のバーストの合計期間。"バースト的な" 伝送とは、安定的なストリームではなく、予測できないバーストでデータが流れている伝送のことです。この指標では、クライアントとサーバーの間のデータ フローが測定されます。</span><span class="sxs-lookup"><span data-stu-id="f17be-p109">Total one-way burst duration. A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream. This metric measures data flow between the client and the server.</span></span></p>
<p><span data-ttu-id="f17be-278">このコラムは、Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="f17be-278">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f17be-279"><strong>RelativeOneWayGapOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="f17be-279"><strong>RelativeOneWayGapOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="f17be-280">int</span><span class="sxs-lookup"><span data-stu-id="f17be-280">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f17be-p110">一方向のギャップの合計発生数。"バースト的な" 伝送とは、安定的なストリームではなく、予測できないバーストでデータが流れている伝送のことです。ギャップは、これらのバースト間の遅延を示します。この指標では、クライアントとサーバーの間のデータ フローが測定されます。</span><span class="sxs-lookup"><span data-stu-id="f17be-p110">Total one-way gap occurrences. A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream; gaps indicate delays between these bursts. This metric measures data flow between the client and the server.</span></span></p>
<p><span data-ttu-id="f17be-284">このコラムは、Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="f17be-284">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f17be-285"><strong>RelativeOneWayGapDensity</strong></span><span class="sxs-lookup"><span data-stu-id="f17be-285"><strong>RelativeOneWayGapDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="f17be-286">浮動小数点数</span><span class="sxs-lookup"><span data-stu-id="f17be-286">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f17be-p111">一方向のギャップの合計密度。"バースト的な" 伝送とは、安定的なストリームではなく、予測できないバーストでデータが流れている伝送のことです。ギャップは、これらのバースト間の遅延を示します。この指標では、クライアントとサーバーの間のデータ フローが測定されます。</span><span class="sxs-lookup"><span data-stu-id="f17be-p111">Total one-way gap density. A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream; gaps indicate delays between these bursts. This metric measures data flow between the client and the server.</span></span></p>
<p><span data-ttu-id="f17be-290">このコラムは、Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="f17be-290">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f17be-291"><strong>RelativeOneWayGapDuration</strong></span><span class="sxs-lookup"><span data-stu-id="f17be-291"><strong>RelativeOneWayGapDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="f17be-292">浮動小数点数</span><span class="sxs-lookup"><span data-stu-id="f17be-292">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f17be-p112">一方向のギャップの合計期間。"バースト的な" 伝送とは、安定的なストリームではなく、予測できないバーストでデータが流れている伝送のことです。ギャップは、これらのバースト間の遅延を示します。この指標では、クライアントとサーバーの間のデータ フローが測定されます。</span><span class="sxs-lookup"><span data-stu-id="f17be-p112">Total one-way gap duration. A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream; gaps indicate delays between these bursts. This metric measures data flow between the client and the server.</span></span></p>
<p><span data-ttu-id="f17be-296">このコラムは、Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="f17be-296">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f17be-297"><strong>VideoPacketLossRate</strong></span><span class="sxs-lookup"><span data-stu-id="f17be-297"><strong>VideoPacketLossRate</strong></span></span></p></td>
<td><p><span data-ttu-id="f17be-298">10進数 (9、4)</span><span class="sxs-lookup"><span data-stu-id="f17be-298">decimal(9,4)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f17be-299">失われたビデオ パケット数の割合。</span><span class="sxs-lookup"><span data-stu-id="f17be-299">Rate at which video packets were lost.</span></span></p>
<p><span data-ttu-id="f17be-300">このコラムは、Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="f17be-300">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f17be-301"><strong>VideoAllocateBWAvg</strong></span><span class="sxs-lookup"><span data-stu-id="f17be-301"><strong>VideoAllocateBWAvg</strong></span></span></p></td>
<td><p><span data-ttu-id="f17be-302">int</span><span class="sxs-lookup"><span data-stu-id="f17be-302">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f17be-303">ビデオに割り当てられた帯域幅の平均。</span><span class="sxs-lookup"><span data-stu-id="f17be-303">Average amount of bandwidth allocated for video.</span></span></p>
<p><span data-ttu-id="f17be-304">このコラムは、Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="f17be-304">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f17be-305"><strong>SendCodecTypes</strong></span><span class="sxs-lookup"><span data-stu-id="f17be-305"><strong>SendCodecTypes</strong></span></span></p></td>
<td><p><span data-ttu-id="f17be-306">smallint</span><span class="sxs-lookup"><span data-stu-id="f17be-306">smallint</span></span></p></td>
<td><p><span data-ttu-id="f17be-307">外部</span><span class="sxs-lookup"><span data-stu-id="f17be-307">Foreign</span></span></p></td>
<td><p><span data-ttu-id="f17be-308">送信者が使用するビデオコーデックの種類。</span><span class="sxs-lookup"><span data-stu-id="f17be-308">Type of video codecs used by the sender.</span></span> <span data-ttu-id="f17be-309">詳細については、「 <a href="lync-server-2013-codecdescription-table.md">Lync Server 2013 の CodecDescription テーブル</a>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f17be-309">See the <a href="lync-server-2013-codecdescription-table.md">CodecDescription table in Lync Server 2013</a> for more information.</span></span></p>
<p><span data-ttu-id="f17be-310">このコラムは、Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="f17be-310">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f17be-311"><strong>Send解像度の幅</strong></span><span class="sxs-lookup"><span data-stu-id="f17be-311"><strong>SendResolutionWidth</strong></span></span></p></td>
<td><p><span data-ttu-id="f17be-312">int</span><span class="sxs-lookup"><span data-stu-id="f17be-312">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f17be-313">送信者が使用する解像度の幅。</span><span class="sxs-lookup"><span data-stu-id="f17be-313">Resolution width used by the sender.</span></span></p>
<p><span data-ttu-id="f17be-314">このコラムは、Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="f17be-314">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f17be-315"><strong>Send解像度の高さ</strong></span><span class="sxs-lookup"><span data-stu-id="f17be-315"><strong>SendResolutionHeight</strong></span></span></p></td>
<td><p><span data-ttu-id="f17be-316">int</span><span class="sxs-lookup"><span data-stu-id="f17be-316">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f17be-317">送信者が使用する解像度の高さ。</span><span class="sxs-lookup"><span data-stu-id="f17be-317">Resolution height used by the sender.</span></span></p>
<p><span data-ttu-id="f17be-318">このコラムは、Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="f17be-318">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f17be-319"><strong>SendFrameRateAverage</strong></span><span class="sxs-lookup"><span data-stu-id="f17be-319"><strong>SendFrameRateAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="f17be-320">浮動小数点数</span><span class="sxs-lookup"><span data-stu-id="f17be-320">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f17be-321">送信者が使用する平均ビデオフレームレート伝送。</span><span class="sxs-lookup"><span data-stu-id="f17be-321">Average video frame rate transmission used by the sender.</span></span></p>
<p><span data-ttu-id="f17be-322">このコラムは、Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="f17be-322">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f17be-323"><strong>SendBitRateMaximum</strong></span><span class="sxs-lookup"><span data-stu-id="f17be-323"><strong>SendBitRateMaximum</strong></span></span></p></td>
<td><p><span data-ttu-id="f17be-324">int</span><span class="sxs-lookup"><span data-stu-id="f17be-324">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f17be-325">送信者の最大ビットレート。</span><span class="sxs-lookup"><span data-stu-id="f17be-325">Maximum bit rate for the sender.</span></span></p>
<p><span data-ttu-id="f17be-326">このコラムは、Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="f17be-326">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f17be-327"><strong>SendBitRateAverage</strong></span><span class="sxs-lookup"><span data-stu-id="f17be-327"><strong>SendBitRateAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="f17be-328">int</span><span class="sxs-lookup"><span data-stu-id="f17be-328">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f17be-329">送信者の平均ビットレート。</span><span class="sxs-lookup"><span data-stu-id="f17be-329">Average bit rate for the sender.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f17be-330"><strong>SendVideoStreamsMax</strong></span><span class="sxs-lookup"><span data-stu-id="f17be-330"><strong>SendVideoStreamsMax</strong></span></span></p></td>
<td><p><span data-ttu-id="f17be-331">int</span><span class="sxs-lookup"><span data-stu-id="f17be-331">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f17be-332">送信者が使用するビデオストリームの最大数。</span><span class="sxs-lookup"><span data-stu-id="f17be-332">Maximum number of video streams used by the sender.</span></span></p>
<p><span data-ttu-id="f17be-333">このコラムは、Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="f17be-333">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f17be-334"><strong>RecvCodecTypes</strong></span><span class="sxs-lookup"><span data-stu-id="f17be-334"><strong>RecvCodecTypes</strong></span></span></p></td>
<td><p><span data-ttu-id="f17be-335">smallint</span><span class="sxs-lookup"><span data-stu-id="f17be-335">smallint</span></span></p></td>
<td><p><span data-ttu-id="f17be-336">外部</span><span class="sxs-lookup"><span data-stu-id="f17be-336">Foreign</span></span></p></td>
<td><p><span data-ttu-id="f17be-337">受信者が使用するビデオコード。</span><span class="sxs-lookup"><span data-stu-id="f17be-337">Video codes used by the receiver.</span></span> <span data-ttu-id="f17be-338">詳細については、「 <a href="lync-server-2013-codecdescription-table.md">Lync Server 2013 の CodecDescription テーブル</a>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f17be-338">See the <a href="lync-server-2013-codecdescription-table.md">CodecDescription table in Lync Server 2013</a> for more information.</span></span></p>
<p><span data-ttu-id="f17be-339">このコラムは、Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="f17be-339">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f17be-340"><strong>RecvResolutionWidth</strong></span><span class="sxs-lookup"><span data-stu-id="f17be-340"><strong>RecvResolutionWidth</strong></span></span></p></td>
<td><p><span data-ttu-id="f17be-341">int</span><span class="sxs-lookup"><span data-stu-id="f17be-341">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f17be-342">受信者が使用する解像度の幅。</span><span class="sxs-lookup"><span data-stu-id="f17be-342">Resolution width used by the receiver.</span></span></p>
<p><span data-ttu-id="f17be-343">このコラムは、Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="f17be-343">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f17be-344"><strong>RecvResolutionHeight</strong></span><span class="sxs-lookup"><span data-stu-id="f17be-344"><strong>RecvResolutionHeight</strong></span></span></p></td>
<td><p><span data-ttu-id="f17be-345">int</span><span class="sxs-lookup"><span data-stu-id="f17be-345">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f17be-346">受信者が使用する解像度の高さ。</span><span class="sxs-lookup"><span data-stu-id="f17be-346">Resolution height used by the receiver.</span></span></p>
<p><span data-ttu-id="f17be-347">このコラムは、Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="f17be-347">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f17be-348"><strong>RecvFrameRateAverage</strong></span><span class="sxs-lookup"><span data-stu-id="f17be-348"><strong>RecvFrameRateAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="f17be-349">浮動小数点数</span><span class="sxs-lookup"><span data-stu-id="f17be-349">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f17be-350">受信者が使用する平均ビデオフレームレート。</span><span class="sxs-lookup"><span data-stu-id="f17be-350">Average video frame rate used by the receiver.</span></span></p>
<p><span data-ttu-id="f17be-351">このコラムは、Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="f17be-351">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f17be-352"><strong>RecvBitRateMaximum</strong></span><span class="sxs-lookup"><span data-stu-id="f17be-352"><strong>RecvBitRateMaximum</strong></span></span></p></td>
<td><p><span data-ttu-id="f17be-353">int</span><span class="sxs-lookup"><span data-stu-id="f17be-353">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f17be-354">受信者の最大ビットレート。</span><span class="sxs-lookup"><span data-stu-id="f17be-354">Maximum bit rate for the receiver.</span></span></p>
<p><span data-ttu-id="f17be-355">このコラムは、Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="f17be-355">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f17be-356"><strong>RecvBitRateAverage</strong></span><span class="sxs-lookup"><span data-stu-id="f17be-356"><strong>RecvBitRateAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="f17be-357">int</span><span class="sxs-lookup"><span data-stu-id="f17be-357">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f17be-358">受信者の平均ビットレート。</span><span class="sxs-lookup"><span data-stu-id="f17be-358">Average bit rate for the receiver.</span></span></p>
<p><span data-ttu-id="f17be-359">このコラムは、Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="f17be-359">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f17be-360"><strong>RecvVideoStreamsMax</strong></span><span class="sxs-lookup"><span data-stu-id="f17be-360"><strong>RecvVideoStreamsMax</strong></span></span></p></td>
<td><p><span data-ttu-id="f17be-361">int</span><span class="sxs-lookup"><span data-stu-id="f17be-361">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f17be-362">受信者の最大ビデオストリーム。</span><span class="sxs-lookup"><span data-stu-id="f17be-362">Maximum video streams for the receiver.</span></span></p>
<p><span data-ttu-id="f17be-363">このコラムは、Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="f17be-363">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f17be-364"><strong>RecvVideoStreamsMin</strong></span><span class="sxs-lookup"><span data-stu-id="f17be-364"><strong>RecvVideoStreamsMin</strong></span></span></p></td>
<td><p><span data-ttu-id="f17be-365">int</span><span class="sxs-lookup"><span data-stu-id="f17be-365">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f17be-366">受信者の最小ビデオストリーム。</span><span class="sxs-lookup"><span data-stu-id="f17be-366">Minimum video streams for the receiver.</span></span></p>
<p><span data-ttu-id="f17be-367">このコラムは、Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="f17be-367">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f17be-368"><strong>RecvVideoStreamsMode</strong></span><span class="sxs-lookup"><span data-stu-id="f17be-368"><strong>RecvVideoStreamsMode</strong></span></span></p></td>
<td><p><span data-ttu-id="f17be-369">int</span><span class="sxs-lookup"><span data-stu-id="f17be-369">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f17be-370">受信者のビデオモード (ギャラリー、単一ストリームなど)。</span><span class="sxs-lookup"><span data-stu-id="f17be-370">Video mode (for example, gallery or single stream) for the receiver.</span></span></p>
<p><span data-ttu-id="f17be-371">このコラムは、Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="f17be-371">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f17be-372"><strong>VideoPostFECPLR</strong></span><span class="sxs-lookup"><span data-stu-id="f17be-372"><strong>VideoPostFECPLR</strong></span></span></p></td>
<td><p><span data-ttu-id="f17be-373">浮動小数点数</span><span class="sxs-lookup"><span data-stu-id="f17be-373">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f17be-374">転送エラー訂正が適用された後のパケット損失率。</span><span class="sxs-lookup"><span data-stu-id="f17be-374">Packet loss rate after forward error correction has been applied.</span></span></p>
<p><span data-ttu-id="f17be-375">このコラムは、Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="f17be-375">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f17be-376"><strong>DynamicCapabilityPercent</strong></span><span class="sxs-lookup"><span data-stu-id="f17be-376"><strong>DynamicCapabilityPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="f17be-377">浮動小数点数</span><span class="sxs-lookup"><span data-stu-id="f17be-377">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f17be-378">動的機能フラグがアクティブだった時間の割合。</span><span class="sxs-lookup"><span data-stu-id="f17be-378">Percentage of time that the dynamic capability flag was active.</span></span></p>
<p><span data-ttu-id="f17be-379">このコラムは、Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="f17be-379">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f17be-380"><strong>解像度 (分)</strong></span><span class="sxs-lookup"><span data-stu-id="f17be-380"><strong>ResolutionMin</strong></span></span></p></td>
<td><p><span data-ttu-id="f17be-381">文字 (9)</span><span class="sxs-lookup"><span data-stu-id="f17be-381">char(9)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f17be-382">呼び出し中に測定された最小解像度。</span><span class="sxs-lookup"><span data-stu-id="f17be-382">Minimum resolution measured during the call.</span></span></p>
<p><span data-ttu-id="f17be-383">このコラムは、Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="f17be-383">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f17be-384"><strong>LowBitRateCallPercent</strong></span><span class="sxs-lookup"><span data-stu-id="f17be-384"><strong>LowBitRateCallPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="f17be-385">浮動小数点数</span><span class="sxs-lookup"><span data-stu-id="f17be-385">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f17be-386">低ビットレートのしきい値を下回る通話のパーセンテージ (70 キロビット/秒)。</span><span class="sxs-lookup"><span data-stu-id="f17be-386">Percentage of the call below the low bit rate threshold (70 kilobits per second).</span></span></p>
<p><span data-ttu-id="f17be-387">このコラムは、Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="f17be-387">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f17be-388"><strong>LowFrameRateCallPercent</strong></span><span class="sxs-lookup"><span data-stu-id="f17be-388"><strong>LowFrameRateCallPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="f17be-389">浮動小数点数</span><span class="sxs-lookup"><span data-stu-id="f17be-389">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f17be-390">低フレームレートのしきい値を下回る通話のパーセンテージ (7.5 フレーム/秒、受信)。</span><span class="sxs-lookup"><span data-stu-id="f17be-390">Percentage of the call below the low frame rate threshold (7.5 frames per second, inbound).</span></span></p>
<p><span data-ttu-id="f17be-391">このコラムは、Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="f17be-391">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f17be-392"><strong>Low解決呼び出しの割合</strong></span><span class="sxs-lookup"><span data-stu-id="f17be-392"><strong>LowResolutionCallPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="f17be-393">浮動小数点数</span><span class="sxs-lookup"><span data-stu-id="f17be-393">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f17be-394">最小解像度で発生した通話のパーセンテージ。</span><span class="sxs-lookup"><span data-stu-id="f17be-394">Percentage of the call that occurred at the lowest resolution.</span></span></p>
<p><span data-ttu-id="f17be-395">このコラムは、Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="f17be-395">This column was introduced in Microsoft Lync Server 2013.</span></span></p>
<p><span data-ttu-id="f17be-396">このコラムは、Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="f17be-396">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f17be-397"><strong>DurationSeconds</strong></span><span class="sxs-lookup"><span data-stu-id="f17be-397"><strong>DurationSeconds</strong></span></span></p></td>
<td><p><span data-ttu-id="f17be-398">浮動小数点数</span><span class="sxs-lookup"><span data-stu-id="f17be-398">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f17be-399">通話の長さ (秒単位)。</span><span class="sxs-lookup"><span data-stu-id="f17be-399">Length of the call in seconds.</span></span></p>
<p><span data-ttu-id="f17be-400">このコラムは、Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="f17be-400">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f17be-401"><strong>IsAggregatedData</strong></span><span class="sxs-lookup"><span data-stu-id="f17be-401"><strong>IsAggregatedData</strong></span></span></p></td>
<td><p><span data-ttu-id="f17be-402">若干</span><span class="sxs-lookup"><span data-stu-id="f17be-402">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f17be-403">データが複数の呼び出しから集約されているかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="f17be-403">Indicates whether the data has been aggregated from multiple calls.</span></span></p>
<p><span data-ttu-id="f17be-404">このコラムは、Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="f17be-404">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

