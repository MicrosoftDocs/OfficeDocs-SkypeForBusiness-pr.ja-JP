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
ms.openlocfilehash: 59799e9b6feb076575d8187936a42a408d0dba2b
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/19/2020
ms.locfileid: "42136895"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="videostream-table-in-lync-server-2013"></a><span data-ttu-id="c9edc-102">Lync Server 2013 の VideoStream テーブル</span><span class="sxs-lookup"><span data-stu-id="c9edc-102">VideoStream table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c9edc-103">_**トピックの最終更新日:** 2013-12-13_</span><span class="sxs-lookup"><span data-stu-id="c9edc-103">_**Topic Last Modified:** 2013-12-13_</span></span>

<span data-ttu-id="c9edc-104">各レコードは1つのビデオストリームを表します。</span><span class="sxs-lookup"><span data-stu-id="c9edc-104">Each record represents one video stream.</span></span> <span data-ttu-id="c9edc-105">通常、1つのビデオメディアラインには2つのビデオストリームが含まれています。</span><span class="sxs-lookup"><span data-stu-id="c9edc-105">One video media line usually contains two video streams.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="c9edc-106"><strong>列</strong></span><span class="sxs-lookup"><span data-stu-id="c9edc-106"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="c9edc-107"><strong>データ型</strong></span><span class="sxs-lookup"><span data-stu-id="c9edc-107"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="c9edc-108"><strong>キー/インデックス</strong></span><span class="sxs-lookup"><span data-stu-id="c9edc-108"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="c9edc-109"><strong>詳細</strong></span><span class="sxs-lookup"><span data-stu-id="c9edc-109"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c9edc-110"><strong>ConferenceDateTime</strong></span><span class="sxs-lookup"><span data-stu-id="c9edc-110"><strong>ConferenceDateTime</strong></span></span></p></td>
<td><p><span data-ttu-id="c9edc-111">日付型</span><span class="sxs-lookup"><span data-stu-id="c9edc-111">datetime</span></span></p></td>
<td><p><span data-ttu-id="c9edc-112">Primary</span><span class="sxs-lookup"><span data-stu-id="c9edc-112">Primary</span></span></p></td>
<td><p><span data-ttu-id="c9edc-113"><a href="lync-server-2013-medialine-table.md">Lync Server 2013 の MediaLine テーブル</a>から参照されます。</span><span class="sxs-lookup"><span data-stu-id="c9edc-113">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c9edc-114"><strong>SessionSeq</strong></span><span class="sxs-lookup"><span data-stu-id="c9edc-114"><strong>SessionSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="c9edc-115">int</span><span class="sxs-lookup"><span data-stu-id="c9edc-115">int</span></span></p></td>
<td><p><span data-ttu-id="c9edc-116">Primary</span><span class="sxs-lookup"><span data-stu-id="c9edc-116">Primary</span></span></p></td>
<td><p><span data-ttu-id="c9edc-117"><a href="lync-server-2013-medialine-table.md">MediaLine テーブル (Lync Server 2013</a>) から参照される R。</span><span class="sxs-lookup"><span data-stu-id="c9edc-117">R Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c9edc-118"><strong>MediaLineLabel</strong></span><span class="sxs-lookup"><span data-stu-id="c9edc-118"><strong>MediaLineLabel</strong></span></span></p></td>
<td><p><span data-ttu-id="c9edc-119">tinyint</span><span class="sxs-lookup"><span data-stu-id="c9edc-119">tinyint</span></span></p></td>
<td><p><span data-ttu-id="c9edc-120">Primary</span><span class="sxs-lookup"><span data-stu-id="c9edc-120">Primary</span></span></p></td>
<td><p><span data-ttu-id="c9edc-121"><a href="lync-server-2013-medialine-table.md">Lync Server 2013 の MediaLine テーブル</a>から参照されます。</span><span class="sxs-lookup"><span data-stu-id="c9edc-121">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c9edc-122"><strong>StreamID</strong></span><span class="sxs-lookup"><span data-stu-id="c9edc-122"><strong>StreamID</strong></span></span></p></td>
<td><p><span data-ttu-id="c9edc-123">int</span><span class="sxs-lookup"><span data-stu-id="c9edc-123">int</span></span></p></td>
<td><p><span data-ttu-id="c9edc-124">Primary</span><span class="sxs-lookup"><span data-stu-id="c9edc-124">Primary</span></span></p></td>
<td><p><span data-ttu-id="c9edc-125">メディア ライン内の一意の ID。</span><span class="sxs-lookup"><span data-stu-id="c9edc-125">Unique ID within a media line.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c9edc-126"><strong>VideoPayloadDescription</strong></span><span class="sxs-lookup"><span data-stu-id="c9edc-126"><strong>VideoPayloadDescription</strong></span></span></p></td>
<td><p><span data-ttu-id="c9edc-127">smallint</span><span class="sxs-lookup"><span data-stu-id="c9edc-127">smallint</span></span></p></td>
<td><p><span data-ttu-id="c9edc-128">外部、プライマリ</span><span class="sxs-lookup"><span data-stu-id="c9edc-128">Foreign, Primary</span></span></p></td>
<td><p><span data-ttu-id="c9edc-129">ペイロードの説明。</span><span class="sxs-lookup"><span data-stu-id="c9edc-129">Payload description.</span></span> <span data-ttu-id="c9edc-130">詳細については、「 <a href="lync-server-2013-payloaddescription-table.md">Lync Server 2013 の PayloadDescription テーブル</a>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c9edc-130">See the <a href="lync-server-2013-payloaddescription-table.md">PayloadDescription table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c9edc-131"><strong>JitterInterArrival</strong></span><span class="sxs-lookup"><span data-stu-id="c9edc-131"><strong>JitterInterArrival</strong></span></span></p></td>
<td><p><span data-ttu-id="c9edc-132">int</span><span class="sxs-lookup"><span data-stu-id="c9edc-132">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="c9edc-133">リアルタイム制御プロトコル (RTCP) 統計情報に基づく平均ネットワーク ジッター。</span><span class="sxs-lookup"><span data-stu-id="c9edc-133">Average network jitter from Real Time Control Protocol (RTCP) statistics.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c9edc-134"><strong>JitterInterArrivalMax</strong></span><span class="sxs-lookup"><span data-stu-id="c9edc-134"><strong>JitterInterArrivalMax</strong></span></span></p></td>
<td><p><span data-ttu-id="c9edc-135">int</span><span class="sxs-lookup"><span data-stu-id="c9edc-135">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="c9edc-136">ビデオセッション時の最大ネットワークジッター。</span><span class="sxs-lookup"><span data-stu-id="c9edc-136">Maximum network jitter during the video session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c9edc-137"><strong>要し</strong></span><span class="sxs-lookup"><span data-stu-id="c9edc-137"><strong>RoundTrip</strong></span></span></p></td>
<td><p><span data-ttu-id="c9edc-138">int</span><span class="sxs-lookup"><span data-stu-id="c9edc-138">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="c9edc-139">RTCP 統計情報に基づく往復時間。</span><span class="sxs-lookup"><span data-stu-id="c9edc-139">Round trip time from RTCP statistics.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c9edc-140"><strong>RoundTripMax</strong></span><span class="sxs-lookup"><span data-stu-id="c9edc-140"><strong>RoundTripMax</strong></span></span></p></td>
<td><p><span data-ttu-id="c9edc-141">int</span><span class="sxs-lookup"><span data-stu-id="c9edc-141">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="c9edc-142">ビデオストリームの最大往復時間。</span><span class="sxs-lookup"><span data-stu-id="c9edc-142">Maximum round trip time for the video stream.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c9edc-143"><strong>PacketLossRate</strong></span><span class="sxs-lookup"><span data-stu-id="c9edc-143"><strong>PacketLossRate</strong></span></span></p></td>
<td><p><span data-ttu-id="c9edc-144">10進数 (5, 4)</span><span class="sxs-lookup"><span data-stu-id="c9edc-144">decimal(5,4)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="c9edc-145">通話時の平均パケット損失率。</span><span class="sxs-lookup"><span data-stu-id="c9edc-145">Average packet loss rate during the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c9edc-146"><strong>PacketLossRateMax</strong></span><span class="sxs-lookup"><span data-stu-id="c9edc-146"><strong>PacketLossRateMax</strong></span></span></p></td>
<td><p><span data-ttu-id="c9edc-147">10進数 (5, 4)</span><span class="sxs-lookup"><span data-stu-id="c9edc-147">decimal(5,4)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="c9edc-148">通話時に観測された最大パケット損失。</span><span class="sxs-lookup"><span data-stu-id="c9edc-148">Maximum packet loss observed during the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c9edc-149"><strong>PacketUtilization</strong></span><span class="sxs-lookup"><span data-stu-id="c9edc-149"><strong>PacketUtilization</strong></span></span></p></td>
<td><p><span data-ttu-id="c9edc-150">int</span><span class="sxs-lookup"><span data-stu-id="c9edc-150">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="c9edc-151">ビデオ ストリームのパケット数 (リアルタイム転送プロトコル、RTP)。</span><span class="sxs-lookup"><span data-stu-id="c9edc-151">Packet count for the video stream (Real Time Transport Protocol, RTP).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c9edc-152"><strong>BandwidthEst</strong></span><span class="sxs-lookup"><span data-stu-id="c9edc-152"><strong>BandwidthEst</strong></span></span></p></td>
<td><p><span data-ttu-id="c9edc-153">int</span><span class="sxs-lookup"><span data-stu-id="c9edc-153">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="c9edc-154">ビデオストリームの帯域幅の推定値。</span><span class="sxs-lookup"><span data-stu-id="c9edc-154">Bandwidth estimates for the video stream.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c9edc-155"><strong>VideoResolution</strong></span><span class="sxs-lookup"><span data-stu-id="c9edc-155"><strong>VideoResolution</strong></span></span></p></td>
<td><p><span data-ttu-id="c9edc-156">文字 (9)</span><span class="sxs-lookup"><span data-stu-id="c9edc-156">char(9)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="c9edc-p103">幅×高さで示すビデオの解像度 (単位ピクセル)。文字列で報告されます。</span><span class="sxs-lookup"><span data-stu-id="c9edc-p103">Resolution of the video in pixels width multiplied by pixels height. Reported as a string.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c9edc-159"><strong>VideoBitRateAvg</strong></span><span class="sxs-lookup"><span data-stu-id="c9edc-159"><strong>VideoBitRateAvg</strong></span></span></p></td>
<td><p><span data-ttu-id="c9edc-160">int</span><span class="sxs-lookup"><span data-stu-id="c9edc-160">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="c9edc-161">ビデオ ストリームの平均ビット レート。</span><span class="sxs-lookup"><span data-stu-id="c9edc-161">Average bit rate of the video stream.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c9edc-162"><strong>InboundVideoFrameRateAvg</strong></span><span class="sxs-lookup"><span data-stu-id="c9edc-162"><strong>InboundVideoFrameRateAvg</strong></span></span></p></td>
<td><p><span data-ttu-id="c9edc-163">10進数 (9、4)</span><span class="sxs-lookup"><span data-stu-id="c9edc-163">decimal(9,4)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="c9edc-164">ビデオのフレームレートを受信しました。</span><span class="sxs-lookup"><span data-stu-id="c9edc-164">The video frame rate received.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c9edc-165"><strong>OutboundVideoFrameRateAvg</strong></span><span class="sxs-lookup"><span data-stu-id="c9edc-165"><strong>OutboundVideoFrameRateAvg</strong></span></span></p></td>
<td><p><span data-ttu-id="c9edc-166">10進数 (9、4)</span><span class="sxs-lookup"><span data-stu-id="c9edc-166">decimal(9,4)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="c9edc-167">ビデオのフレームレートが送信されます。</span><span class="sxs-lookup"><span data-stu-id="c9edc-167">The video frame rate sent.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c9edc-168"><strong>VideoBitRateMax</strong></span><span class="sxs-lookup"><span data-stu-id="c9edc-168"><strong>VideoBitRateMax</strong></span></span></p></td>
<td><p><span data-ttu-id="c9edc-169">int</span><span class="sxs-lookup"><span data-stu-id="c9edc-169">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="c9edc-170">ビデオセッション時の最大ビデオビットレート。</span><span class="sxs-lookup"><span data-stu-id="c9edc-170">The maximum video bit rate during the video session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c9edc-171"><strong>VideoFrameLossRate</strong></span><span class="sxs-lookup"><span data-stu-id="c9edc-171"><strong>VideoFrameLossRate</strong></span></span></p></td>
<td><p><span data-ttu-id="c9edc-172">10進数 (9、4)</span><span class="sxs-lookup"><span data-stu-id="c9edc-172">decimal(9,4)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="c9edc-173">失われた合計ビデオフレーム数の割合。</span><span class="sxs-lookup"><span data-stu-id="c9edc-173">The percentage of total video frames that are lost.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c9edc-174"><strong>VideoFEC</strong></span><span class="sxs-lookup"><span data-stu-id="c9edc-174"><strong>VideoFEC</strong></span></span></p></td>
<td><p><span data-ttu-id="c9edc-175">若干</span><span class="sxs-lookup"><span data-stu-id="c9edc-175">bit</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="c9edc-176">注意事項なし。</span><span class="sxs-lookup"><span data-stu-id="c9edc-176">Not available.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c9edc-177"><strong>VideoLocalFrameLossPercentageAvg</strong></span><span class="sxs-lookup"><span data-stu-id="c9edc-177"><strong>VideoLocalFrameLossPercentageAvg</strong></span></span></p></td>
<td><p><span data-ttu-id="c9edc-178">10進数 (9、4)</span><span class="sxs-lookup"><span data-stu-id="c9edc-178">decimal(9,4)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="c9edc-179">失われた合計ビデオフレーム数の割合。</span><span class="sxs-lookup"><span data-stu-id="c9edc-179">The percentage of total video frames that are lost.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c9edc-180"><strong>CIFQualityRatio</strong></span><span class="sxs-lookup"><span data-stu-id="c9edc-180"><strong>CIFQualityRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="c9edc-181">tinyint</span><span class="sxs-lookup"><span data-stu-id="c9edc-181">tinyint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="c9edc-182">共通交換形式 (CIF) の解決にかけられた通話のパーセンテージ。</span><span class="sxs-lookup"><span data-stu-id="c9edc-182">The percentage of the call that was at the Common Interchange Format (CIF) resolution.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c9edc-183"><strong>VGAQualityRatio</strong></span><span class="sxs-lookup"><span data-stu-id="c9edc-183"><strong>VGAQualityRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="c9edc-184">tinyint</span><span class="sxs-lookup"><span data-stu-id="c9edc-184">tinyint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="c9edc-185">VGA 解像度で行われた通話のパーセンテージ。</span><span class="sxs-lookup"><span data-stu-id="c9edc-185">The percentage of the call that was at VGA resolution.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c9edc-186"><strong>HD720QualityRatio</strong></span><span class="sxs-lookup"><span data-stu-id="c9edc-186"><strong>HD720QualityRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="c9edc-187">tinyint</span><span class="sxs-lookup"><span data-stu-id="c9edc-187">tinyint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="c9edc-188">HD720 の解像度で行われた通話のパーセンテージ。</span><span class="sxs-lookup"><span data-stu-id="c9edc-188">The percentage of the call that was at HD720 resolution.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c9edc-189"><strong>NoneDropRatio</strong></span><span class="sxs-lookup"><span data-stu-id="c9edc-189"><strong>NoneDropRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="c9edc-190">tinyint</span><span class="sxs-lookup"><span data-stu-id="c9edc-190">tinyint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="c9edc-191">フレームが欠落していない通話時間のパーセンテージ。</span><span class="sxs-lookup"><span data-stu-id="c9edc-191">Percentage of call duration with no frame drop.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c9edc-192"><strong>B' _ '</strong></span><span class="sxs-lookup"><span data-stu-id="c9edc-192"><strong>BDropRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="c9edc-193">tinyint</span><span class="sxs-lookup"><span data-stu-id="c9edc-193">tinyint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="c9edc-194">B フレームが欠落している通話時間のパーセンテージ。</span><span class="sxs-lookup"><span data-stu-id="c9edc-194">Percentage of call duration with B frame drop.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c9edc-195"><strong>Bp' bp'</strong></span><span class="sxs-lookup"><span data-stu-id="c9edc-195"><strong>BPDropRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="c9edc-196">tinyint</span><span class="sxs-lookup"><span data-stu-id="c9edc-196">tinyint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="c9edc-197">BP フレームが欠落している通話時間のパーセンテージ。</span><span class="sxs-lookup"><span data-stu-id="c9edc-197">Percentage of call duration with BP frame drop.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c9edc-198"><strong>Bpsp/Bpprた</strong></span><span class="sxs-lookup"><span data-stu-id="c9edc-198"><strong>BPSPDropRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="c9edc-199">tinyint</span><span class="sxs-lookup"><span data-stu-id="c9edc-199">tinyint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="c9edc-200">BPSP フレームが欠落している通話時間のパーセンテージ。</span><span class="sxs-lookup"><span data-stu-id="c9edc-200">Percentage of call duration with BPSP frame drop.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c9edc-201"><strong>BPSPIDropRatio</strong></span><span class="sxs-lookup"><span data-stu-id="c9edc-201"><strong>BPSPIDropRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="c9edc-202">tinyint</span><span class="sxs-lookup"><span data-stu-id="c9edc-202">tinyint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="c9edc-203">BPSPI フレームが欠落している通話時間のパーセンテージ。</span><span class="sxs-lookup"><span data-stu-id="c9edc-203">Percentage of call duration with BPSPI frame drop.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c9edc-204"><strong>受信</strong></span><span class="sxs-lookup"><span data-stu-id="c9edc-204"><strong>Inbound</strong></span></span></p></td>
<td><p><span data-ttu-id="c9edc-205">若干</span><span class="sxs-lookup"><span data-stu-id="c9edc-205">bit</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="c9edc-206">受信側のストリームデータが受信されます。</span><span class="sxs-lookup"><span data-stu-id="c9edc-206">Stream data on receiver side is received.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c9edc-207"><strong>送信</strong></span><span class="sxs-lookup"><span data-stu-id="c9edc-207"><strong>Outbound</strong></span></span></p></td>
<td><p><span data-ttu-id="c9edc-208">若干</span><span class="sxs-lookup"><span data-stu-id="c9edc-208">bit</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="c9edc-209">送信側のストリームデータが受信されます。</span><span class="sxs-lookup"><span data-stu-id="c9edc-209">Stream data on sender side is received.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c9edc-210"><strong>SenderIsCallerPAI</strong></span><span class="sxs-lookup"><span data-stu-id="c9edc-210"><strong>SenderIsCallerPAI</strong></span></span></p></td>
<td><p><span data-ttu-id="c9edc-211">若干</span><span class="sxs-lookup"><span data-stu-id="c9edc-211">bit</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="c9edc-212">1 は、ストリームの方向が発信者から呼び出し先へ向かうことを意味します。</span><span class="sxs-lookup"><span data-stu-id="c9edc-212">1 means the stream direction is from the caller to callee.</span></span></p>
<p><span data-ttu-id="c9edc-213">0 は、ストリームの方向が呼び出し先から発信者へ向かうことを意味します。</span><span class="sxs-lookup"><span data-stu-id="c9edc-213">0 means the stream direction is from the callee to the caller.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c9edc-214"><strong>LossCongestionPercent</strong></span><span class="sxs-lookup"><span data-stu-id="c9edc-214"><strong>LossCongestionPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="c9edc-215">浮動小数点数</span><span class="sxs-lookup"><span data-stu-id="c9edc-215">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="c9edc-216">通話が切断された輻輳状態であった時間の割合を示します。</span><span class="sxs-lookup"><span data-stu-id="c9edc-216">Indicates the percentage of the time when the call was in a loss congestion state.</span></span></p>
<p><span data-ttu-id="c9edc-217">このコラムは、Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="c9edc-217">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c9edc-218"><strong>DelayCongestionPercent</strong></span><span class="sxs-lookup"><span data-stu-id="c9edc-218"><strong>DelayCongestionPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="c9edc-219">浮動小数点数</span><span class="sxs-lookup"><span data-stu-id="c9edc-219">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="c9edc-220">ネットワークパケットの遅延到着により輻輳が発生した通話の割合を示します。</span><span class="sxs-lookup"><span data-stu-id="c9edc-220">Indicates the percentage of the call during which congestion was caused by the delayed arrival of network packets.</span></span></p>
<p><span data-ttu-id="c9edc-221">このコラムは、Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="c9edc-221">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c9edc-222"><strong>ContentionDetectedPercent</strong></span><span class="sxs-lookup"><span data-stu-id="c9edc-222"><strong>ContentionDetectedPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="c9edc-223">浮動小数点数</span><span class="sxs-lookup"><span data-stu-id="c9edc-223">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="c9edc-224">通話がネットワークリソースに対して競合していた時間の割合を示します。</span><span class="sxs-lookup"><span data-stu-id="c9edc-224">Indicates the percentage of the time when the call was competing for network resources.</span></span></p>
<p><span data-ttu-id="c9edc-225">このコラムは、Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="c9edc-225">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c9edc-226"><strong>BandwidthEstMin</strong></span><span class="sxs-lookup"><span data-stu-id="c9edc-226"><strong>BandwidthEstMin</strong></span></span></p></td>
<td><p><span data-ttu-id="c9edc-227">int</span><span class="sxs-lookup"><span data-stu-id="c9edc-227">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="c9edc-228">呼び出し中に測定された最小帯域幅推定値。</span><span class="sxs-lookup"><span data-stu-id="c9edc-228">Minimum amount of bandwidth estimation measured during the call.</span></span></p>
<p><span data-ttu-id="c9edc-229">このコラムは、Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="c9edc-229">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c9edc-230"><strong>BandwidthEstMax</strong></span><span class="sxs-lookup"><span data-stu-id="c9edc-230"><strong>BandwidthEstMax</strong></span></span></p></td>
<td><p><span data-ttu-id="c9edc-231">int</span><span class="sxs-lookup"><span data-stu-id="c9edc-231">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="c9edc-232">呼び出し中に測定された最大帯域幅推定値。</span><span class="sxs-lookup"><span data-stu-id="c9edc-232">Maximum amount of bandwidth estimation measured during the call.</span></span></p>
<p><span data-ttu-id="c9edc-233">このコラムは、Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="c9edc-233">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c9edc-234"><strong>BandwidthEstStdDev</strong></span><span class="sxs-lookup"><span data-stu-id="c9edc-234"><strong>BandwidthEstStdDev</strong></span></span></p></td>
<td><p><span data-ttu-id="c9edc-235">int</span><span class="sxs-lookup"><span data-stu-id="c9edc-235">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="c9edc-236">呼び出し中に測定された帯域幅推定の標準偏差。</span><span class="sxs-lookup"><span data-stu-id="c9edc-236">Standard deviation of the bandwidth estimation measured during the call.</span></span></p>
<p><span data-ttu-id="c9edc-237">このコラムは、Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="c9edc-237">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c9edc-238"><strong>BandwidthEstAvge</strong></span><span class="sxs-lookup"><span data-stu-id="c9edc-238"><strong>BandwidthEstAvge</strong></span></span></p></td>
<td><p><span data-ttu-id="c9edc-239">int</span><span class="sxs-lookup"><span data-stu-id="c9edc-239">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="c9edc-240">呼び出し中に測定された平均帯域幅推定値。</span><span class="sxs-lookup"><span data-stu-id="c9edc-240">Average amount of bandwidth estimation measured during the call.</span></span></p>
<p><span data-ttu-id="c9edc-241">このコラムは、Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="c9edc-241">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c9edc-242"><strong>LowBandwidthForMultiview</strong></span><span class="sxs-lookup"><span data-stu-id="c9edc-242"><strong>LowBandwidthForMultiview</strong></span></span></p></td>
<td><p><span data-ttu-id="c9edc-243">浮動小数点数</span><span class="sxs-lookup"><span data-stu-id="c9edc-243">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="c9edc-244">エンドポイントが、ネットワーク接続がマルチビュービデオをサポートできなかったと判断した通話のパーセンテージ。</span><span class="sxs-lookup"><span data-stu-id="c9edc-244">Percentage of the call where the endpoint determined that the network connection could not support multiview video.</span></span></p>
<p><span data-ttu-id="c9edc-245">このコラムは、Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="c9edc-245">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c9edc-246"><strong>RelativeOneWayTotal</strong></span><span class="sxs-lookup"><span data-stu-id="c9edc-246"><strong>RelativeOneWayTotal</strong></span></span></p></td>
<td><p><span data-ttu-id="c9edc-247">浮動小数点数</span><span class="sxs-lookup"><span data-stu-id="c9edc-247">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="c9edc-p104">一方向の遅延の合計時間。相対的な一方向の遅延によって、クライアントとサーバーの間の遅延が測定されます。</span><span class="sxs-lookup"><span data-stu-id="c9edc-p104">Total amount of one-way latency. Relative one-way latency measures the delay between the client and the server.</span></span></p>
<p><span data-ttu-id="c9edc-250">このコラムは、Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="c9edc-250">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c9edc-251"><strong>RelativeOneWayAverage</strong></span><span class="sxs-lookup"><span data-stu-id="c9edc-251"><strong>RelativeOneWayAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="c9edc-252">浮動小数点数</span><span class="sxs-lookup"><span data-stu-id="c9edc-252">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="c9edc-p105">一方向の遅延の平均時間。相対的な一方向の遅延によって、クライアントとサーバーの間の遅延が測定されます。</span><span class="sxs-lookup"><span data-stu-id="c9edc-p105">Average amount of one-way latency. Relative one-way latency measures the delay between the client and the server.</span></span></p>
<p><span data-ttu-id="c9edc-255">このコラムは、Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="c9edc-255">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c9edc-256"><strong>RelativeOneWayMax</strong></span><span class="sxs-lookup"><span data-stu-id="c9edc-256"><strong>RelativeOneWayMax</strong></span></span></p></td>
<td><p><span data-ttu-id="c9edc-257">浮動小数点数</span><span class="sxs-lookup"><span data-stu-id="c9edc-257">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="c9edc-p106">一方向の遅延の最大時間。相対的な一方向の遅延によって、クライアントとサーバーの間の遅延が測定されます。</span><span class="sxs-lookup"><span data-stu-id="c9edc-p106">Maximum amount of one-way latency. Relative one-way latency measures the delay between the client and the server.</span></span></p>
<p><span data-ttu-id="c9edc-260">このコラムは、Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="c9edc-260">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c9edc-261"><strong>RelativeOneWayBurstOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="c9edc-261"><strong>RelativeOneWayBurstOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="c9edc-262">int</span><span class="sxs-lookup"><span data-stu-id="c9edc-262">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="c9edc-p107">一方向のバーストの合計発生数。"バースト的な" 伝送とは、安定的なストリームではなく、予測できないバーストでデータが流れている伝送のことです。この指標では、クライアントとサーバーの間のデータ フローが測定されます。</span><span class="sxs-lookup"><span data-stu-id="c9edc-p107">Total one-way burst occurrences. A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream. This metric measures data flow between the client and the server.</span></span></p>
<p><span data-ttu-id="c9edc-266">このコラムは、Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="c9edc-266">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c9edc-267"><strong>RelativeOneWayBurstDensity</strong></span><span class="sxs-lookup"><span data-stu-id="c9edc-267"><strong>RelativeOneWayBurstDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="c9edc-268">int</span><span class="sxs-lookup"><span data-stu-id="c9edc-268">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="c9edc-p108">一方向のバーストの合計密度。"バースト的な" 伝送とは、安定的なストリームではなく、予測できないバーストでデータが流れている伝送のことです。この指標では、クライアントとサーバーの間のデータ フローが測定されます。</span><span class="sxs-lookup"><span data-stu-id="c9edc-p108">Total one-way burst density. A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream. This metric measures data flow between the client and the server.</span></span></p>
<p><span data-ttu-id="c9edc-272">このコラムは、Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="c9edc-272">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c9edc-273"><strong>RelativeOneWayBurstDuration</strong></span><span class="sxs-lookup"><span data-stu-id="c9edc-273"><strong>RelativeOneWayBurstDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="c9edc-274">浮動小数点数</span><span class="sxs-lookup"><span data-stu-id="c9edc-274">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="c9edc-p109">一方向のバーストの合計期間。"バースト的な" 伝送とは、安定的なストリームではなく、予測できないバーストでデータが流れている伝送のことです。この指標では、クライアントとサーバーの間のデータ フローが測定されます。</span><span class="sxs-lookup"><span data-stu-id="c9edc-p109">Total one-way burst duration. A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream. This metric measures data flow between the client and the server.</span></span></p>
<p><span data-ttu-id="c9edc-278">このコラムは、Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="c9edc-278">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c9edc-279"><strong>RelativeOneWayGapOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="c9edc-279"><strong>RelativeOneWayGapOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="c9edc-280">int</span><span class="sxs-lookup"><span data-stu-id="c9edc-280">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="c9edc-p110">一方向のギャップの合計発生数。"バースト的な" 伝送とは、安定的なストリームではなく、予測できないバーストでデータが流れている伝送のことです。ギャップは、これらのバースト間の遅延を示します。この指標では、クライアントとサーバーの間のデータ フローが測定されます。</span><span class="sxs-lookup"><span data-stu-id="c9edc-p110">Total one-way gap occurrences. A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream; gaps indicate delays between these bursts. This metric measures data flow between the client and the server.</span></span></p>
<p><span data-ttu-id="c9edc-284">このコラムは、Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="c9edc-284">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c9edc-285"><strong>RelativeOneWayGapDensity</strong></span><span class="sxs-lookup"><span data-stu-id="c9edc-285"><strong>RelativeOneWayGapDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="c9edc-286">浮動小数点数</span><span class="sxs-lookup"><span data-stu-id="c9edc-286">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="c9edc-p111">一方向のギャップの合計密度。"バースト的な" 伝送とは、安定的なストリームではなく、予測できないバーストでデータが流れている伝送のことです。ギャップは、これらのバースト間の遅延を示します。この指標では、クライアントとサーバーの間のデータ フローが測定されます。</span><span class="sxs-lookup"><span data-stu-id="c9edc-p111">Total one-way gap density. A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream; gaps indicate delays between these bursts. This metric measures data flow between the client and the server.</span></span></p>
<p><span data-ttu-id="c9edc-290">このコラムは、Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="c9edc-290">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c9edc-291"><strong>RelativeOneWayGapDuration</strong></span><span class="sxs-lookup"><span data-stu-id="c9edc-291"><strong>RelativeOneWayGapDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="c9edc-292">浮動小数点数</span><span class="sxs-lookup"><span data-stu-id="c9edc-292">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="c9edc-p112">一方向のギャップの合計期間。"バースト的な" 伝送とは、安定的なストリームではなく、予測できないバーストでデータが流れている伝送のことです。ギャップは、これらのバースト間の遅延を示します。この指標では、クライアントとサーバーの間のデータ フローが測定されます。</span><span class="sxs-lookup"><span data-stu-id="c9edc-p112">Total one-way gap duration. A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream; gaps indicate delays between these bursts. This metric measures data flow between the client and the server.</span></span></p>
<p><span data-ttu-id="c9edc-296">このコラムは、Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="c9edc-296">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c9edc-297"><strong>VideoPacketLossRate</strong></span><span class="sxs-lookup"><span data-stu-id="c9edc-297"><strong>VideoPacketLossRate</strong></span></span></p></td>
<td><p><span data-ttu-id="c9edc-298">10進数 (9、4)</span><span class="sxs-lookup"><span data-stu-id="c9edc-298">decimal(9,4)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="c9edc-299">失われたビデオ パケット数の割合。</span><span class="sxs-lookup"><span data-stu-id="c9edc-299">Rate at which video packets were lost.</span></span></p>
<p><span data-ttu-id="c9edc-300">このコラムは、Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="c9edc-300">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c9edc-301"><strong>VideoAllocateBWAvg</strong></span><span class="sxs-lookup"><span data-stu-id="c9edc-301"><strong>VideoAllocateBWAvg</strong></span></span></p></td>
<td><p><span data-ttu-id="c9edc-302">int</span><span class="sxs-lookup"><span data-stu-id="c9edc-302">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="c9edc-303">ビデオに割り当てられた帯域幅の平均。</span><span class="sxs-lookup"><span data-stu-id="c9edc-303">Average amount of bandwidth allocated for video.</span></span></p>
<p><span data-ttu-id="c9edc-304">このコラムは、Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="c9edc-304">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c9edc-305"><strong>SendCodecTypes</strong></span><span class="sxs-lookup"><span data-stu-id="c9edc-305"><strong>SendCodecTypes</strong></span></span></p></td>
<td><p><span data-ttu-id="c9edc-306">smallint</span><span class="sxs-lookup"><span data-stu-id="c9edc-306">smallint</span></span></p></td>
<td><p><span data-ttu-id="c9edc-307">外部</span><span class="sxs-lookup"><span data-stu-id="c9edc-307">Foreign</span></span></p></td>
<td><p><span data-ttu-id="c9edc-308">送信者が使用するビデオコーデックの種類。</span><span class="sxs-lookup"><span data-stu-id="c9edc-308">Type of video codecs used by the sender.</span></span> <span data-ttu-id="c9edc-309">詳細については、「 <a href="lync-server-2013-codecdescription-table.md">Lync Server 2013 の CodecDescription テーブル</a>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c9edc-309">See the <a href="lync-server-2013-codecdescription-table.md">CodecDescription table in Lync Server 2013</a> for more information.</span></span></p>
<p><span data-ttu-id="c9edc-310">このコラムは、Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="c9edc-310">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c9edc-311"><strong>Send解像度の幅</strong></span><span class="sxs-lookup"><span data-stu-id="c9edc-311"><strong>SendResolutionWidth</strong></span></span></p></td>
<td><p><span data-ttu-id="c9edc-312">int</span><span class="sxs-lookup"><span data-stu-id="c9edc-312">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="c9edc-313">送信者が使用する解像度の幅。</span><span class="sxs-lookup"><span data-stu-id="c9edc-313">Resolution width used by the sender.</span></span></p>
<p><span data-ttu-id="c9edc-314">このコラムは、Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="c9edc-314">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c9edc-315"><strong>Send解像度の高さ</strong></span><span class="sxs-lookup"><span data-stu-id="c9edc-315"><strong>SendResolutionHeight</strong></span></span></p></td>
<td><p><span data-ttu-id="c9edc-316">int</span><span class="sxs-lookup"><span data-stu-id="c9edc-316">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="c9edc-317">送信者が使用する解像度の高さ。</span><span class="sxs-lookup"><span data-stu-id="c9edc-317">Resolution height used by the sender.</span></span></p>
<p><span data-ttu-id="c9edc-318">このコラムは、Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="c9edc-318">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c9edc-319"><strong>SendFrameRateAverage</strong></span><span class="sxs-lookup"><span data-stu-id="c9edc-319"><strong>SendFrameRateAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="c9edc-320">浮動小数点数</span><span class="sxs-lookup"><span data-stu-id="c9edc-320">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="c9edc-321">送信者が使用する平均ビデオフレームレート伝送。</span><span class="sxs-lookup"><span data-stu-id="c9edc-321">Average video frame rate transmission used by the sender.</span></span></p>
<p><span data-ttu-id="c9edc-322">このコラムは、Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="c9edc-322">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c9edc-323"><strong>SendBitRateMaximum</strong></span><span class="sxs-lookup"><span data-stu-id="c9edc-323"><strong>SendBitRateMaximum</strong></span></span></p></td>
<td><p><span data-ttu-id="c9edc-324">int</span><span class="sxs-lookup"><span data-stu-id="c9edc-324">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="c9edc-325">送信者の最大ビットレート。</span><span class="sxs-lookup"><span data-stu-id="c9edc-325">Maximum bit rate for the sender.</span></span></p>
<p><span data-ttu-id="c9edc-326">このコラムは、Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="c9edc-326">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c9edc-327"><strong>SendBitRateAverage</strong></span><span class="sxs-lookup"><span data-stu-id="c9edc-327"><strong>SendBitRateAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="c9edc-328">int</span><span class="sxs-lookup"><span data-stu-id="c9edc-328">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="c9edc-329">送信者の平均ビットレート。</span><span class="sxs-lookup"><span data-stu-id="c9edc-329">Average bit rate for the sender.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c9edc-330"><strong>SendVideoStreamsMax</strong></span><span class="sxs-lookup"><span data-stu-id="c9edc-330"><strong>SendVideoStreamsMax</strong></span></span></p></td>
<td><p><span data-ttu-id="c9edc-331">int</span><span class="sxs-lookup"><span data-stu-id="c9edc-331">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="c9edc-332">送信者が使用するビデオストリームの最大数。</span><span class="sxs-lookup"><span data-stu-id="c9edc-332">Maximum number of video streams used by the sender.</span></span></p>
<p><span data-ttu-id="c9edc-333">このコラムは、Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="c9edc-333">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c9edc-334"><strong>RecvCodecTypes</strong></span><span class="sxs-lookup"><span data-stu-id="c9edc-334"><strong>RecvCodecTypes</strong></span></span></p></td>
<td><p><span data-ttu-id="c9edc-335">smallint</span><span class="sxs-lookup"><span data-stu-id="c9edc-335">smallint</span></span></p></td>
<td><p><span data-ttu-id="c9edc-336">外部</span><span class="sxs-lookup"><span data-stu-id="c9edc-336">Foreign</span></span></p></td>
<td><p><span data-ttu-id="c9edc-337">受信者が使用するビデオコード。</span><span class="sxs-lookup"><span data-stu-id="c9edc-337">Video codes used by the receiver.</span></span> <span data-ttu-id="c9edc-338">詳細については、「 <a href="lync-server-2013-codecdescription-table.md">Lync Server 2013 の CodecDescription テーブル</a>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c9edc-338">See the <a href="lync-server-2013-codecdescription-table.md">CodecDescription table in Lync Server 2013</a> for more information.</span></span></p>
<p><span data-ttu-id="c9edc-339">このコラムは、Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="c9edc-339">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c9edc-340"><strong>RecvResolutionWidth</strong></span><span class="sxs-lookup"><span data-stu-id="c9edc-340"><strong>RecvResolutionWidth</strong></span></span></p></td>
<td><p><span data-ttu-id="c9edc-341">int</span><span class="sxs-lookup"><span data-stu-id="c9edc-341">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="c9edc-342">受信者が使用する解像度の幅。</span><span class="sxs-lookup"><span data-stu-id="c9edc-342">Resolution width used by the receiver.</span></span></p>
<p><span data-ttu-id="c9edc-343">このコラムは、Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="c9edc-343">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c9edc-344"><strong>RecvResolutionHeight</strong></span><span class="sxs-lookup"><span data-stu-id="c9edc-344"><strong>RecvResolutionHeight</strong></span></span></p></td>
<td><p><span data-ttu-id="c9edc-345">int</span><span class="sxs-lookup"><span data-stu-id="c9edc-345">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="c9edc-346">受信者が使用する解像度の高さ。</span><span class="sxs-lookup"><span data-stu-id="c9edc-346">Resolution height used by the receiver.</span></span></p>
<p><span data-ttu-id="c9edc-347">このコラムは、Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="c9edc-347">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c9edc-348"><strong>RecvFrameRateAverage</strong></span><span class="sxs-lookup"><span data-stu-id="c9edc-348"><strong>RecvFrameRateAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="c9edc-349">浮動小数点数</span><span class="sxs-lookup"><span data-stu-id="c9edc-349">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="c9edc-350">受信者が使用する平均ビデオフレームレート。</span><span class="sxs-lookup"><span data-stu-id="c9edc-350">Average video frame rate used by the receiver.</span></span></p>
<p><span data-ttu-id="c9edc-351">このコラムは、Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="c9edc-351">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c9edc-352"><strong>RecvBitRateMaximum</strong></span><span class="sxs-lookup"><span data-stu-id="c9edc-352"><strong>RecvBitRateMaximum</strong></span></span></p></td>
<td><p><span data-ttu-id="c9edc-353">int</span><span class="sxs-lookup"><span data-stu-id="c9edc-353">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="c9edc-354">受信者の最大ビットレート。</span><span class="sxs-lookup"><span data-stu-id="c9edc-354">Maximum bit rate for the receiver.</span></span></p>
<p><span data-ttu-id="c9edc-355">このコラムは、Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="c9edc-355">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c9edc-356"><strong>RecvBitRateAverage</strong></span><span class="sxs-lookup"><span data-stu-id="c9edc-356"><strong>RecvBitRateAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="c9edc-357">int</span><span class="sxs-lookup"><span data-stu-id="c9edc-357">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="c9edc-358">受信者の平均ビットレート。</span><span class="sxs-lookup"><span data-stu-id="c9edc-358">Average bit rate for the receiver.</span></span></p>
<p><span data-ttu-id="c9edc-359">このコラムは、Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="c9edc-359">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c9edc-360"><strong>RecvVideoStreamsMax</strong></span><span class="sxs-lookup"><span data-stu-id="c9edc-360"><strong>RecvVideoStreamsMax</strong></span></span></p></td>
<td><p><span data-ttu-id="c9edc-361">int</span><span class="sxs-lookup"><span data-stu-id="c9edc-361">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="c9edc-362">受信者の最大ビデオストリーム。</span><span class="sxs-lookup"><span data-stu-id="c9edc-362">Maximum video streams for the receiver.</span></span></p>
<p><span data-ttu-id="c9edc-363">このコラムは、Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="c9edc-363">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c9edc-364"><strong>RecvVideoStreamsMin</strong></span><span class="sxs-lookup"><span data-stu-id="c9edc-364"><strong>RecvVideoStreamsMin</strong></span></span></p></td>
<td><p><span data-ttu-id="c9edc-365">int</span><span class="sxs-lookup"><span data-stu-id="c9edc-365">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="c9edc-366">受信者の最小ビデオストリーム。</span><span class="sxs-lookup"><span data-stu-id="c9edc-366">Minimum video streams for the receiver.</span></span></p>
<p><span data-ttu-id="c9edc-367">このコラムは、Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="c9edc-367">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c9edc-368"><strong>RecvVideoStreamsMode</strong></span><span class="sxs-lookup"><span data-stu-id="c9edc-368"><strong>RecvVideoStreamsMode</strong></span></span></p></td>
<td><p><span data-ttu-id="c9edc-369">int</span><span class="sxs-lookup"><span data-stu-id="c9edc-369">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="c9edc-370">受信者のビデオモード (ギャラリー、単一ストリームなど)。</span><span class="sxs-lookup"><span data-stu-id="c9edc-370">Video mode (for example, gallery or single stream) for the receiver.</span></span></p>
<p><span data-ttu-id="c9edc-371">このコラムは、Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="c9edc-371">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c9edc-372"><strong>VideoPostFECPLR</strong></span><span class="sxs-lookup"><span data-stu-id="c9edc-372"><strong>VideoPostFECPLR</strong></span></span></p></td>
<td><p><span data-ttu-id="c9edc-373">浮動小数点数</span><span class="sxs-lookup"><span data-stu-id="c9edc-373">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="c9edc-374">転送エラー訂正が適用された後のパケット損失率。</span><span class="sxs-lookup"><span data-stu-id="c9edc-374">Packet loss rate after forward error correction has been applied.</span></span></p>
<p><span data-ttu-id="c9edc-375">このコラムは、Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="c9edc-375">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c9edc-376"><strong>DynamicCapabilityPercent</strong></span><span class="sxs-lookup"><span data-stu-id="c9edc-376"><strong>DynamicCapabilityPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="c9edc-377">浮動小数点数</span><span class="sxs-lookup"><span data-stu-id="c9edc-377">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="c9edc-378">動的機能フラグがアクティブだった時間の割合。</span><span class="sxs-lookup"><span data-stu-id="c9edc-378">Percentage of time that the dynamic capability flag was active.</span></span></p>
<p><span data-ttu-id="c9edc-379">このコラムは、Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="c9edc-379">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c9edc-380"><strong>解像度 (分)</strong></span><span class="sxs-lookup"><span data-stu-id="c9edc-380"><strong>ResolutionMin</strong></span></span></p></td>
<td><p><span data-ttu-id="c9edc-381">文字 (9)</span><span class="sxs-lookup"><span data-stu-id="c9edc-381">char(9)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="c9edc-382">呼び出し中に測定された最小解像度。</span><span class="sxs-lookup"><span data-stu-id="c9edc-382">Minimum resolution measured during the call.</span></span></p>
<p><span data-ttu-id="c9edc-383">このコラムは、Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="c9edc-383">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c9edc-384"><strong>LowBitRateCallPercent</strong></span><span class="sxs-lookup"><span data-stu-id="c9edc-384"><strong>LowBitRateCallPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="c9edc-385">浮動小数点数</span><span class="sxs-lookup"><span data-stu-id="c9edc-385">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="c9edc-386">低ビットレートのしきい値を下回る通話のパーセンテージ (70 キロビット/秒)。</span><span class="sxs-lookup"><span data-stu-id="c9edc-386">Percentage of the call below the low bit rate threshold (70 kilobits per second).</span></span></p>
<p><span data-ttu-id="c9edc-387">このコラムは、Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="c9edc-387">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c9edc-388"><strong>LowFrameRateCallPercent</strong></span><span class="sxs-lookup"><span data-stu-id="c9edc-388"><strong>LowFrameRateCallPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="c9edc-389">浮動小数点数</span><span class="sxs-lookup"><span data-stu-id="c9edc-389">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="c9edc-390">低フレームレートのしきい値を下回る通話のパーセンテージ (7.5 フレーム/秒、受信)。</span><span class="sxs-lookup"><span data-stu-id="c9edc-390">Percentage of the call below the low frame rate threshold (7.5 frames per second, inbound).</span></span></p>
<p><span data-ttu-id="c9edc-391">このコラムは、Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="c9edc-391">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c9edc-392"><strong>Low解決呼び出しの割合</strong></span><span class="sxs-lookup"><span data-stu-id="c9edc-392"><strong>LowResolutionCallPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="c9edc-393">浮動小数点数</span><span class="sxs-lookup"><span data-stu-id="c9edc-393">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="c9edc-394">最小解像度で発生した通話のパーセンテージ。</span><span class="sxs-lookup"><span data-stu-id="c9edc-394">Percentage of the call that occurred at the lowest resolution.</span></span></p>
<p><span data-ttu-id="c9edc-395">このコラムは、Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="c9edc-395">This column was introduced in Microsoft Lync Server 2013.</span></span></p>
<p><span data-ttu-id="c9edc-396">このコラムは、Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="c9edc-396">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c9edc-397"><strong>DurationSeconds</strong></span><span class="sxs-lookup"><span data-stu-id="c9edc-397"><strong>DurationSeconds</strong></span></span></p></td>
<td><p><span data-ttu-id="c9edc-398">浮動小数点数</span><span class="sxs-lookup"><span data-stu-id="c9edc-398">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="c9edc-399">通話の長さ (秒単位)。</span><span class="sxs-lookup"><span data-stu-id="c9edc-399">Length of the call in seconds.</span></span></p>
<p><span data-ttu-id="c9edc-400">このコラムは、Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="c9edc-400">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c9edc-401"><strong>IsAggregatedData</strong></span><span class="sxs-lookup"><span data-stu-id="c9edc-401"><strong>IsAggregatedData</strong></span></span></p></td>
<td><p><span data-ttu-id="c9edc-402">若干</span><span class="sxs-lookup"><span data-stu-id="c9edc-402">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="c9edc-403">データが複数の呼び出しから集約されているかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="c9edc-403">Indicates whether the data has been aggregated from multiple calls.</span></span></p>
<p><span data-ttu-id="c9edc-404">このコラムは、Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="c9edc-404">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

