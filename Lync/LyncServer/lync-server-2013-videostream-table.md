---
title: 'Lync Server 2013: VideoStream テーブル'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: VideoStream table
ms:assetid: 4275ede7-5467-4a97-b8c8-a4b00917bf32
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425928(v=OCS.15)
ms:contentKeyID: 48184014
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 98e0ad3f7c18032dd903d2f8d1d41428ccc12cf9
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34848225"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="videostream-table-in-lync-server-2013"></a><span data-ttu-id="ea38c-102">Lync Server 2013 の VideoStream テーブル</span><span class="sxs-lookup"><span data-stu-id="ea38c-102">VideoStream table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ea38c-103">_**最終更新日:** 2013-12-13_</span><span class="sxs-lookup"><span data-stu-id="ea38c-103">_**Topic Last Modified:** 2013-12-13_</span></span>

<span data-ttu-id="ea38c-104">各レコードは1つのビデオストリームを表します。</span><span class="sxs-lookup"><span data-stu-id="ea38c-104">Each record represents one video stream.</span></span> <span data-ttu-id="ea38c-105">1つのビデオメディアラインには通常、2つのビデオストリームが含まれています。</span><span class="sxs-lookup"><span data-stu-id="ea38c-105">One video media line usually contains two video streams.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="ea38c-106"><strong>列</strong></span><span class="sxs-lookup"><span data-stu-id="ea38c-106"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="ea38c-107"><strong>データ型</strong></span><span class="sxs-lookup"><span data-stu-id="ea38c-107"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="ea38c-108"><strong>キー/インデックス</strong></span><span class="sxs-lookup"><span data-stu-id="ea38c-108"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="ea38c-109"><strong>詳細</strong></span><span class="sxs-lookup"><span data-stu-id="ea38c-109"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ea38c-110"><strong>ConferenceDateTime</strong></span><span class="sxs-lookup"><span data-stu-id="ea38c-110"><strong>ConferenceDateTime</strong></span></span></p></td>
<td><p><span data-ttu-id="ea38c-111">datetime</span><span class="sxs-lookup"><span data-stu-id="ea38c-111">datetime</span></span></p></td>
<td><p><span data-ttu-id="ea38c-112">Primary</span><span class="sxs-lookup"><span data-stu-id="ea38c-112">Primary</span></span></p></td>
<td><p><span data-ttu-id="ea38c-113"><a href="lync-server-2013-medialine-table.md">Lync Server 2013 の MediaLine テーブル</a>から参照されている。</span><span class="sxs-lookup"><span data-stu-id="ea38c-113">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ea38c-114"><strong>SessionSeq</strong></span><span class="sxs-lookup"><span data-stu-id="ea38c-114"><strong>SessionSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="ea38c-115">int</span><span class="sxs-lookup"><span data-stu-id="ea38c-115">int</span></span></p></td>
<td><p><span data-ttu-id="ea38c-116">Primary</span><span class="sxs-lookup"><span data-stu-id="ea38c-116">Primary</span></span></p></td>
<td><p><span data-ttu-id="ea38c-117">MediaLine は、 <a href="lync-server-2013-medialine-table.md">Lync Server 2013 のテーブル</a>から参照されます。</span><span class="sxs-lookup"><span data-stu-id="ea38c-117">R Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ea38c-118"><strong>MediaLineLabel</strong></span><span class="sxs-lookup"><span data-stu-id="ea38c-118"><strong>MediaLineLabel</strong></span></span></p></td>
<td><p><span data-ttu-id="ea38c-119">tinyint</span><span class="sxs-lookup"><span data-stu-id="ea38c-119">tinyint</span></span></p></td>
<td><p><span data-ttu-id="ea38c-120">Primary</span><span class="sxs-lookup"><span data-stu-id="ea38c-120">Primary</span></span></p></td>
<td><p><span data-ttu-id="ea38c-121"><a href="lync-server-2013-medialine-table.md">Lync Server 2013 の MediaLine テーブル</a>から参照されている。</span><span class="sxs-lookup"><span data-stu-id="ea38c-121">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ea38c-122"><strong>StreamID</strong></span><span class="sxs-lookup"><span data-stu-id="ea38c-122"><strong>StreamID</strong></span></span></p></td>
<td><p><span data-ttu-id="ea38c-123">int</span><span class="sxs-lookup"><span data-stu-id="ea38c-123">int</span></span></p></td>
<td><p><span data-ttu-id="ea38c-124">Primary</span><span class="sxs-lookup"><span data-stu-id="ea38c-124">Primary</span></span></p></td>
<td><p><span data-ttu-id="ea38c-125">メディアライン内の一意の ID。</span><span class="sxs-lookup"><span data-stu-id="ea38c-125">Unique ID within a media line.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ea38c-126"><strong>VideoPayloadDescription</strong></span><span class="sxs-lookup"><span data-stu-id="ea38c-126"><strong>VideoPayloadDescription</strong></span></span></p></td>
<td><p><span data-ttu-id="ea38c-127">smallint</span><span class="sxs-lookup"><span data-stu-id="ea38c-127">smallint</span></span></p></td>
<td><p><span data-ttu-id="ea38c-128">外来、プライマリ</span><span class="sxs-lookup"><span data-stu-id="ea38c-128">Foreign, Primary</span></span></p></td>
<td><p><span data-ttu-id="ea38c-129">ペイロードの説明。</span><span class="sxs-lookup"><span data-stu-id="ea38c-129">Payload description.</span></span> <span data-ttu-id="ea38c-130">詳細については、「 <a href="lync-server-2013-payloaddescription-table.md">Lync Server 2013 の PayloadDescription テーブル</a>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ea38c-130">See the <a href="lync-server-2013-payloaddescription-table.md">PayloadDescription table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ea38c-131"><strong>JitterInterArrival</strong></span><span class="sxs-lookup"><span data-stu-id="ea38c-131"><strong>JitterInterArrival</strong></span></span></p></td>
<td><p><span data-ttu-id="ea38c-132">int</span><span class="sxs-lookup"><span data-stu-id="ea38c-132">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="ea38c-133">リアルタイム制御プロトコル (RTCP) の統計情報からの平均ネットワークジッター。</span><span class="sxs-lookup"><span data-stu-id="ea38c-133">Average network jitter from Real Time Control Protocol (RTCP) statistics.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ea38c-134"><strong>JitterInterArrivalMax</strong></span><span class="sxs-lookup"><span data-stu-id="ea38c-134"><strong>JitterInterArrivalMax</strong></span></span></p></td>
<td><p><span data-ttu-id="ea38c-135">int</span><span class="sxs-lookup"><span data-stu-id="ea38c-135">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="ea38c-136">ビデオセッション中の最大ネットワークジッター。</span><span class="sxs-lookup"><span data-stu-id="ea38c-136">Maximum network jitter during the video session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ea38c-137"><strong>RoundTrip</strong></span><span class="sxs-lookup"><span data-stu-id="ea38c-137"><strong>RoundTrip</strong></span></span></p></td>
<td><p><span data-ttu-id="ea38c-138">int</span><span class="sxs-lookup"><span data-stu-id="ea38c-138">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="ea38c-139">RTCP の統計情報からのラウンドトリップ時間。</span><span class="sxs-lookup"><span data-stu-id="ea38c-139">Round trip time from RTCP statistics.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ea38c-140"><strong>RoundTripMax</strong></span><span class="sxs-lookup"><span data-stu-id="ea38c-140"><strong>RoundTripMax</strong></span></span></p></td>
<td><p><span data-ttu-id="ea38c-141">int</span><span class="sxs-lookup"><span data-stu-id="ea38c-141">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="ea38c-142">ビデオストリームの最大ラウンドトリップ時間。</span><span class="sxs-lookup"><span data-stu-id="ea38c-142">Maximum round trip time for the video stream.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ea38c-143"><strong>PacketLossRate</strong></span><span class="sxs-lookup"><span data-stu-id="ea38c-143"><strong>PacketLossRate</strong></span></span></p></td>
<td><p><span data-ttu-id="ea38c-144">10進数 (5, 4)</span><span class="sxs-lookup"><span data-stu-id="ea38c-144">decimal(5,4)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="ea38c-145">通話中の平均パケット損失率。</span><span class="sxs-lookup"><span data-stu-id="ea38c-145">Average packet loss rate during the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ea38c-146"><strong>PacketLossRateMax</strong></span><span class="sxs-lookup"><span data-stu-id="ea38c-146"><strong>PacketLossRateMax</strong></span></span></p></td>
<td><p><span data-ttu-id="ea38c-147">10進数 (5, 4)</span><span class="sxs-lookup"><span data-stu-id="ea38c-147">decimal(5,4)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="ea38c-148">通話中に発生したパケット損失の上限。</span><span class="sxs-lookup"><span data-stu-id="ea38c-148">Maximum packet loss observed during the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ea38c-149"><strong>PacketUtilization</strong></span><span class="sxs-lookup"><span data-stu-id="ea38c-149"><strong>PacketUtilization</strong></span></span></p></td>
<td><p><span data-ttu-id="ea38c-150">int</span><span class="sxs-lookup"><span data-stu-id="ea38c-150">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="ea38c-151">ビデオストリームのパケット数 (リアルタイムトランスポートプロトコル、RTP)。</span><span class="sxs-lookup"><span data-stu-id="ea38c-151">Packet count for the video stream (Real Time Transport Protocol, RTP).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ea38c-152"><strong>BandwidthEst</strong></span><span class="sxs-lookup"><span data-stu-id="ea38c-152"><strong>BandwidthEst</strong></span></span></p></td>
<td><p><span data-ttu-id="ea38c-153">int</span><span class="sxs-lookup"><span data-stu-id="ea38c-153">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="ea38c-154">ビデオストリームの帯域幅推定。</span><span class="sxs-lookup"><span data-stu-id="ea38c-154">Bandwidth estimates for the video stream.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ea38c-155"><strong>VideoResolution</strong></span><span class="sxs-lookup"><span data-stu-id="ea38c-155"><strong>VideoResolution</strong></span></span></p></td>
<td><p><span data-ttu-id="ea38c-156">char (9)</span><span class="sxs-lookup"><span data-stu-id="ea38c-156">char(9)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="ea38c-157">ピクセル幅にピクセルの高さを掛けたビデオの解像度。</span><span class="sxs-lookup"><span data-stu-id="ea38c-157">Resolution of the video in pixels width multiplied by pixels height.</span></span> <span data-ttu-id="ea38c-158">文字列として報告されます。</span><span class="sxs-lookup"><span data-stu-id="ea38c-158">Reported as a string.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ea38c-159"><strong>VideoBitRateAvg</strong></span><span class="sxs-lookup"><span data-stu-id="ea38c-159"><strong>VideoBitRateAvg</strong></span></span></p></td>
<td><p><span data-ttu-id="ea38c-160">int</span><span class="sxs-lookup"><span data-stu-id="ea38c-160">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="ea38c-161">ビデオストリームの平均ビットレート。</span><span class="sxs-lookup"><span data-stu-id="ea38c-161">Average bit rate of the video stream.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ea38c-162"><strong>InboundVideoFrameRateAvg</strong></span><span class="sxs-lookup"><span data-stu-id="ea38c-162"><strong>InboundVideoFrameRateAvg</strong></span></span></p></td>
<td><p><span data-ttu-id="ea38c-163">10進数 (9, 4)</span><span class="sxs-lookup"><span data-stu-id="ea38c-163">decimal(9,4)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="ea38c-164">ビデオフレームレートが適用されました。</span><span class="sxs-lookup"><span data-stu-id="ea38c-164">The video frame rate received.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ea38c-165"><strong>OutboundVideoFrameRateAvg</strong></span><span class="sxs-lookup"><span data-stu-id="ea38c-165"><strong>OutboundVideoFrameRateAvg</strong></span></span></p></td>
<td><p><span data-ttu-id="ea38c-166">10進数 (9, 4)</span><span class="sxs-lookup"><span data-stu-id="ea38c-166">decimal(9,4)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="ea38c-167">送信されたビデオフレームレート。</span><span class="sxs-lookup"><span data-stu-id="ea38c-167">The video frame rate sent.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ea38c-168"><strong>VideoBitRateMax</strong></span><span class="sxs-lookup"><span data-stu-id="ea38c-168"><strong>VideoBitRateMax</strong></span></span></p></td>
<td><p><span data-ttu-id="ea38c-169">int</span><span class="sxs-lookup"><span data-stu-id="ea38c-169">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="ea38c-170">ビデオセッション中の最大ビデオビットレート。</span><span class="sxs-lookup"><span data-stu-id="ea38c-170">The maximum video bit rate during the video session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ea38c-171"><strong>VideoFrameLossRate</strong></span><span class="sxs-lookup"><span data-stu-id="ea38c-171"><strong>VideoFrameLossRate</strong></span></span></p></td>
<td><p><span data-ttu-id="ea38c-172">10進数 (9, 4)</span><span class="sxs-lookup"><span data-stu-id="ea38c-172">decimal(9,4)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="ea38c-173">失われたビデオフレームの合計のパーセンテージ。</span><span class="sxs-lookup"><span data-stu-id="ea38c-173">The percentage of total video frames that are lost.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ea38c-174"><strong>VideoFEC</strong></span><span class="sxs-lookup"><span data-stu-id="ea38c-174"><strong>VideoFEC</strong></span></span></p></td>
<td><p><span data-ttu-id="ea38c-175">bit</span><span class="sxs-lookup"><span data-stu-id="ea38c-175">bit</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="ea38c-176">使用できません。</span><span class="sxs-lookup"><span data-stu-id="ea38c-176">Not available.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ea38c-177"><strong>ビデオ</strong></span><span class="sxs-lookup"><span data-stu-id="ea38c-177"><strong>VideoLocalFrameLossPercentageAvg</strong></span></span></p></td>
<td><p><span data-ttu-id="ea38c-178">10進数 (9, 4)</span><span class="sxs-lookup"><span data-stu-id="ea38c-178">decimal(9,4)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="ea38c-179">失われたビデオフレームの合計のパーセンテージ。</span><span class="sxs-lookup"><span data-stu-id="ea38c-179">The percentage of total video frames that are lost.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ea38c-180"><strong>CIFQualityRatio</strong></span><span class="sxs-lookup"><span data-stu-id="ea38c-180"><strong>CIFQualityRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="ea38c-181">tinyint</span><span class="sxs-lookup"><span data-stu-id="ea38c-181">tinyint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="ea38c-182">共通インターチェンジ形式 (CIF) の解像度での通話の割合。</span><span class="sxs-lookup"><span data-stu-id="ea38c-182">The percentage of the call that was at the Common Interchange Format (CIF) resolution.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ea38c-183"><strong>VGAQualityRatio</strong></span><span class="sxs-lookup"><span data-stu-id="ea38c-183"><strong>VGAQualityRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="ea38c-184">tinyint</span><span class="sxs-lookup"><span data-stu-id="ea38c-184">tinyint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="ea38c-185">VGA 解像度での通話の割合。</span><span class="sxs-lookup"><span data-stu-id="ea38c-185">The percentage of the call that was at VGA resolution.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ea38c-186"><strong>HD720QualityRatio</strong></span><span class="sxs-lookup"><span data-stu-id="ea38c-186"><strong>HD720QualityRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="ea38c-187">tinyint</span><span class="sxs-lookup"><span data-stu-id="ea38c-187">tinyint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="ea38c-188">HD720 の解像度での通話の割合。</span><span class="sxs-lookup"><span data-stu-id="ea38c-188">The percentage of the call that was at HD720 resolution.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ea38c-189"><strong>NoneDropRatio</strong></span><span class="sxs-lookup"><span data-stu-id="ea38c-189"><strong>NoneDropRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="ea38c-190">tinyint</span><span class="sxs-lookup"><span data-stu-id="ea38c-190">tinyint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="ea38c-191">フレームドロップなしの通話時間の割合。</span><span class="sxs-lookup"><span data-stu-id="ea38c-191">Percentage of call duration with no frame drop.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ea38c-192"><strong>Bスペック</strong></span><span class="sxs-lookup"><span data-stu-id="ea38c-192"><strong>BDropRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="ea38c-193">tinyint</span><span class="sxs-lookup"><span data-stu-id="ea38c-193">tinyint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="ea38c-194">B フレームドロップでの通話時間の割合。</span><span class="sxs-lookup"><span data-stu-id="ea38c-194">Percentage of call duration with B frame drop.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ea38c-195"><strong>Bp・スペック</strong></span><span class="sxs-lookup"><span data-stu-id="ea38c-195"><strong>BPDropRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="ea38c-196">tinyint</span><span class="sxs-lookup"><span data-stu-id="ea38c-196">tinyint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="ea38c-197">BP フレームドロップでの通話時間の割合。</span><span class="sxs-lookup"><span data-stu-id="ea38c-197">Percentage of call duration with BP frame drop.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ea38c-198"><strong>Bpsp・ bp</strong></span><span class="sxs-lookup"><span data-stu-id="ea38c-198"><strong>BPSPDropRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="ea38c-199">tinyint</span><span class="sxs-lookup"><span data-stu-id="ea38c-199">tinyint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="ea38c-200">BPSP フレームドロップでの通話時間の割合。</span><span class="sxs-lookup"><span data-stu-id="ea38c-200">Percentage of call duration with BPSP frame drop.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ea38c-201"><strong>BPSPIDropRatio</strong></span><span class="sxs-lookup"><span data-stu-id="ea38c-201"><strong>BPSPIDropRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="ea38c-202">tinyint</span><span class="sxs-lookup"><span data-stu-id="ea38c-202">tinyint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="ea38c-203">BPSPI フレームドロップでの通話時間の割合。</span><span class="sxs-lookup"><span data-stu-id="ea38c-203">Percentage of call duration with BPSPI frame drop.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ea38c-204"><strong>トラフィック</strong></span><span class="sxs-lookup"><span data-stu-id="ea38c-204"><strong>Inbound</strong></span></span></p></td>
<td><p><span data-ttu-id="ea38c-205">bit</span><span class="sxs-lookup"><span data-stu-id="ea38c-205">bit</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="ea38c-206">受信側のストリームデータが受信されます。</span><span class="sxs-lookup"><span data-stu-id="ea38c-206">Stream data on receiver side is received.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ea38c-207"><strong>発信</strong></span><span class="sxs-lookup"><span data-stu-id="ea38c-207"><strong>Outbound</strong></span></span></p></td>
<td><p><span data-ttu-id="ea38c-208">bit</span><span class="sxs-lookup"><span data-stu-id="ea38c-208">bit</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="ea38c-209">送信側のストリームデータが受信されます。</span><span class="sxs-lookup"><span data-stu-id="ea38c-209">Stream data on sender side is received.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ea38c-210"><strong>SenderIsCallerPAI</strong></span><span class="sxs-lookup"><span data-stu-id="ea38c-210"><strong>SenderIsCallerPAI</strong></span></span></p></td>
<td><p><span data-ttu-id="ea38c-211">bit</span><span class="sxs-lookup"><span data-stu-id="ea38c-211">bit</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="ea38c-212">1ストリームの方向は、呼び出し元から呼び出し先へとなります。</span><span class="sxs-lookup"><span data-stu-id="ea38c-212">1 means the stream direction is from the caller to callee.</span></span></p>
<p><span data-ttu-id="ea38c-213">0は、ストリームの方向を呼び出し元から呼び出し元に転送します。</span><span class="sxs-lookup"><span data-stu-id="ea38c-213">0 means the stream direction is from the callee to the caller.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ea38c-214"><strong>LossCongestionPercent</strong></span><span class="sxs-lookup"><span data-stu-id="ea38c-214"><strong>LossCongestionPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="ea38c-215">float</span><span class="sxs-lookup"><span data-stu-id="ea38c-215">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="ea38c-216">通話が切断された輻輳状態であった時間の割合を示します。</span><span class="sxs-lookup"><span data-stu-id="ea38c-216">Indicates the percentage of the time when the call was in a loss congestion state.</span></span></p>
<p><span data-ttu-id="ea38c-217">この列は Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="ea38c-217">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ea38c-218"><strong>DelayCongestionPercent</strong></span><span class="sxs-lookup"><span data-stu-id="ea38c-218"><strong>DelayCongestionPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="ea38c-219">float</span><span class="sxs-lookup"><span data-stu-id="ea38c-219">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="ea38c-220">ネットワークパケットが遅延したために発生した、通話の割合を示します。</span><span class="sxs-lookup"><span data-stu-id="ea38c-220">Indicates the percentage of the call during which congestion was caused by the delayed arrival of network packets.</span></span></p>
<p><span data-ttu-id="ea38c-221">この列は Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="ea38c-221">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ea38c-222"><strong>ContentionDetectedPercent</strong></span><span class="sxs-lookup"><span data-stu-id="ea38c-222"><strong>ContentionDetectedPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="ea38c-223">float</span><span class="sxs-lookup"><span data-stu-id="ea38c-223">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="ea38c-224">通話がネットワークリソースに対して競合した時間の割合を示します。</span><span class="sxs-lookup"><span data-stu-id="ea38c-224">Indicates the percentage of the time when the call was competing for network resources.</span></span></p>
<p><span data-ttu-id="ea38c-225">この列は Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="ea38c-225">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ea38c-226"><strong>BandwidthEstMin</strong></span><span class="sxs-lookup"><span data-stu-id="ea38c-226"><strong>BandwidthEstMin</strong></span></span></p></td>
<td><p><span data-ttu-id="ea38c-227">int</span><span class="sxs-lookup"><span data-stu-id="ea38c-227">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="ea38c-228">通話中の最小帯域幅推定値。</span><span class="sxs-lookup"><span data-stu-id="ea38c-228">Minimum amount of bandwidth estimation measured during the call.</span></span></p>
<p><span data-ttu-id="ea38c-229">この列は Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="ea38c-229">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ea38c-230"><strong>BandwidthEstMax</strong></span><span class="sxs-lookup"><span data-stu-id="ea38c-230"><strong>BandwidthEstMax</strong></span></span></p></td>
<td><p><span data-ttu-id="ea38c-231">int</span><span class="sxs-lookup"><span data-stu-id="ea38c-231">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="ea38c-232">通話中に測定された帯域幅推定の最大量。</span><span class="sxs-lookup"><span data-stu-id="ea38c-232">Maximum amount of bandwidth estimation measured during the call.</span></span></p>
<p><span data-ttu-id="ea38c-233">この列は Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="ea38c-233">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ea38c-234"><strong>BandwidthEstStdDev</strong></span><span class="sxs-lookup"><span data-stu-id="ea38c-234"><strong>BandwidthEstStdDev</strong></span></span></p></td>
<td><p><span data-ttu-id="ea38c-235">int</span><span class="sxs-lookup"><span data-stu-id="ea38c-235">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="ea38c-236">通話中に測定された帯域幅推定の標準偏差。</span><span class="sxs-lookup"><span data-stu-id="ea38c-236">Standard deviation of the bandwidth estimation measured during the call.</span></span></p>
<p><span data-ttu-id="ea38c-237">この列は Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="ea38c-237">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ea38c-238"><strong>BandwidthEstAvge</strong></span><span class="sxs-lookup"><span data-stu-id="ea38c-238"><strong>BandwidthEstAvge</strong></span></span></p></td>
<td><p><span data-ttu-id="ea38c-239">int</span><span class="sxs-lookup"><span data-stu-id="ea38c-239">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="ea38c-240">通話中に計測された平均帯域幅推定量。</span><span class="sxs-lookup"><span data-stu-id="ea38c-240">Average amount of bandwidth estimation measured during the call.</span></span></p>
<p><span data-ttu-id="ea38c-241">この列は Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="ea38c-241">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ea38c-242"><strong>LowBandwidthForMultiview</strong></span><span class="sxs-lookup"><span data-stu-id="ea38c-242"><strong>LowBandwidthForMultiview</strong></span></span></p></td>
<td><p><span data-ttu-id="ea38c-243">float</span><span class="sxs-lookup"><span data-stu-id="ea38c-243">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="ea38c-244">エンドポイントが、ネットワーク接続が multiview ビデオをサポートしていないと判断した通話の割合。</span><span class="sxs-lookup"><span data-stu-id="ea38c-244">Percentage of the call where the endpoint determined that the network connection could not support multiview video.</span></span></p>
<p><span data-ttu-id="ea38c-245">この列は Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="ea38c-245">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ea38c-246"><strong>RelativeOneWayTotal</strong></span><span class="sxs-lookup"><span data-stu-id="ea38c-246"><strong>RelativeOneWayTotal</strong></span></span></p></td>
<td><p><span data-ttu-id="ea38c-247">float</span><span class="sxs-lookup"><span data-stu-id="ea38c-247">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="ea38c-248">一方向の待機時間の合計。</span><span class="sxs-lookup"><span data-stu-id="ea38c-248">Total amount of one-way latency.</span></span> <span data-ttu-id="ea38c-249">相対的な一方向の待ち時間は、クライアントとサーバーの間の遅延を測定します。</span><span class="sxs-lookup"><span data-stu-id="ea38c-249">Relative one-way latency measures the delay between the client and the server.</span></span></p>
<p><span data-ttu-id="ea38c-250">この列は Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="ea38c-250">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ea38c-251"><strong>RelativeOneWayAverage</strong></span><span class="sxs-lookup"><span data-stu-id="ea38c-251"><strong>RelativeOneWayAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="ea38c-252">float</span><span class="sxs-lookup"><span data-stu-id="ea38c-252">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="ea38c-253">一方向の待ち時間の平均値。</span><span class="sxs-lookup"><span data-stu-id="ea38c-253">Average amount of one-way latency.</span></span> <span data-ttu-id="ea38c-254">相対的な一方向の待ち時間は、クライアントとサーバーの間の遅延を測定します。</span><span class="sxs-lookup"><span data-stu-id="ea38c-254">Relative one-way latency measures the delay between the client and the server.</span></span></p>
<p><span data-ttu-id="ea38c-255">この列は Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="ea38c-255">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ea38c-256"><strong>RelativeOneWayMax</strong></span><span class="sxs-lookup"><span data-stu-id="ea38c-256"><strong>RelativeOneWayMax</strong></span></span></p></td>
<td><p><span data-ttu-id="ea38c-257">float</span><span class="sxs-lookup"><span data-stu-id="ea38c-257">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="ea38c-258">一方向の待機時間の上限。</span><span class="sxs-lookup"><span data-stu-id="ea38c-258">Maximum amount of one-way latency.</span></span> <span data-ttu-id="ea38c-259">相対的な一方向の待ち時間は、クライアントとサーバーの間の遅延を測定します。</span><span class="sxs-lookup"><span data-stu-id="ea38c-259">Relative one-way latency measures the delay between the client and the server.</span></span></p>
<p><span data-ttu-id="ea38c-260">この列は Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="ea38c-260">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ea38c-261"><strong>RelativeOneWayBurstOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="ea38c-261"><strong>RelativeOneWayBurstOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="ea38c-262">int</span><span class="sxs-lookup"><span data-stu-id="ea38c-262">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="ea38c-263">1方向のバースト発生の合計。</span><span class="sxs-lookup"><span data-stu-id="ea38c-263">Total one-way burst occurrences.</span></span> <span data-ttu-id="ea38c-264">"Bursty" 伝送とは、安定したストリームと比べて予期しないバーストでデータが流れる伝送です。</span><span class="sxs-lookup"><span data-stu-id="ea38c-264">A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream.</span></span> <span data-ttu-id="ea38c-265">このメトリックは、クライアントとサーバー間のデータフローを計測します。</span><span class="sxs-lookup"><span data-stu-id="ea38c-265">This metric measures data flow between the client and the server.</span></span></p>
<p><span data-ttu-id="ea38c-266">この列は Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="ea38c-266">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ea38c-267"><strong>RelativeOneWayBurstDensity</strong></span><span class="sxs-lookup"><span data-stu-id="ea38c-267"><strong>RelativeOneWayBurstDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="ea38c-268">int</span><span class="sxs-lookup"><span data-stu-id="ea38c-268">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="ea38c-269">全体的な1方向バースト密度。</span><span class="sxs-lookup"><span data-stu-id="ea38c-269">Total one-way burst density.</span></span> <span data-ttu-id="ea38c-270">"Bursty" 伝送とは、安定したストリームと比べて予期しないバーストでデータが流れる伝送です。</span><span class="sxs-lookup"><span data-stu-id="ea38c-270">A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream.</span></span> <span data-ttu-id="ea38c-271">このメトリックは、クライアントとサーバー間のデータフローを計測します。</span><span class="sxs-lookup"><span data-stu-id="ea38c-271">This metric measures data flow between the client and the server.</span></span></p>
<p><span data-ttu-id="ea38c-272">この列は Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="ea38c-272">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ea38c-273"><strong>RelativeOneWayBurstDuration</strong></span><span class="sxs-lookup"><span data-stu-id="ea38c-273"><strong>RelativeOneWayBurstDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="ea38c-274">float</span><span class="sxs-lookup"><span data-stu-id="ea38c-274">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="ea38c-275">一方向のバースト期間の合計。</span><span class="sxs-lookup"><span data-stu-id="ea38c-275">Total one-way burst duration.</span></span> <span data-ttu-id="ea38c-276">"Bursty" 伝送とは、安定したストリームと比べて予期しないバーストでデータが流れる伝送です。</span><span class="sxs-lookup"><span data-stu-id="ea38c-276">A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream.</span></span> <span data-ttu-id="ea38c-277">このメトリックは、クライアントとサーバー間のデータフローを計測します。</span><span class="sxs-lookup"><span data-stu-id="ea38c-277">This metric measures data flow between the client and the server.</span></span></p>
<p><span data-ttu-id="ea38c-278">この列は Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="ea38c-278">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ea38c-279"><strong>RelativeOneWayGapOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="ea38c-279"><strong>RelativeOneWayGapOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="ea38c-280">int</span><span class="sxs-lookup"><span data-stu-id="ea38c-280">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="ea38c-281">一方向のギャップ出現の合計。</span><span class="sxs-lookup"><span data-stu-id="ea38c-281">Total one-way gap occurrences.</span></span> <span data-ttu-id="ea38c-282">"Bursty" 伝送とは、安定したストリームではなく、予期しないバーストでデータが流れる伝送です。ギャップは、このようなバーストの間の遅延を示します。</span><span class="sxs-lookup"><span data-stu-id="ea38c-282">A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream; gaps indicate delays between these bursts.</span></span> <span data-ttu-id="ea38c-283">このメトリックは、クライアントとサーバー間のデータフローを計測します。</span><span class="sxs-lookup"><span data-stu-id="ea38c-283">This metric measures data flow between the client and the server.</span></span></p>
<p><span data-ttu-id="ea38c-284">この列は Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="ea38c-284">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ea38c-285"><strong>RelativeOneWayGapDensity</strong></span><span class="sxs-lookup"><span data-stu-id="ea38c-285"><strong>RelativeOneWayGapDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="ea38c-286">float</span><span class="sxs-lookup"><span data-stu-id="ea38c-286">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="ea38c-287">一方向のギャップの密度の合計。</span><span class="sxs-lookup"><span data-stu-id="ea38c-287">Total one-way gap density.</span></span> <span data-ttu-id="ea38c-288">"Bursty" 伝送とは、安定したストリームではなく、予期しないバーストでデータが流れる伝送です。ギャップは、このようなバーストの間の遅延を示します。</span><span class="sxs-lookup"><span data-stu-id="ea38c-288">A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream; gaps indicate delays between these bursts.</span></span> <span data-ttu-id="ea38c-289">このメトリックは、クライアントとサーバー間のデータフローを計測します。</span><span class="sxs-lookup"><span data-stu-id="ea38c-289">This metric measures data flow between the client and the server.</span></span></p>
<p><span data-ttu-id="ea38c-290">この列は Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="ea38c-290">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ea38c-291"><strong>RelativeOneWayGapDuration</strong></span><span class="sxs-lookup"><span data-stu-id="ea38c-291"><strong>RelativeOneWayGapDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="ea38c-292">float</span><span class="sxs-lookup"><span data-stu-id="ea38c-292">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="ea38c-293">一方向のギャップ期間の合計。</span><span class="sxs-lookup"><span data-stu-id="ea38c-293">Total one-way gap duration.</span></span> <span data-ttu-id="ea38c-294">"Bursty" 伝送とは、安定したストリームではなく、予期しないバーストでデータが流れる伝送です。ギャップは、このようなバーストの間の遅延を示します。</span><span class="sxs-lookup"><span data-stu-id="ea38c-294">A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream; gaps indicate delays between these bursts.</span></span> <span data-ttu-id="ea38c-295">このメトリックは、クライアントとサーバー間のデータフローを計測します。</span><span class="sxs-lookup"><span data-stu-id="ea38c-295">This metric measures data flow between the client and the server.</span></span></p>
<p><span data-ttu-id="ea38c-296">この列は Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="ea38c-296">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ea38c-297"><strong>パケット損失率</strong></span><span class="sxs-lookup"><span data-stu-id="ea38c-297"><strong>VideoPacketLossRate</strong></span></span></p></td>
<td><p><span data-ttu-id="ea38c-298">10進数 (9, 4)</span><span class="sxs-lookup"><span data-stu-id="ea38c-298">decimal(9,4)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="ea38c-299">ビデオパケットが失われた速度。</span><span class="sxs-lookup"><span data-stu-id="ea38c-299">Rate at which video packets were lost.</span></span></p>
<p><span data-ttu-id="ea38c-300">この列は Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="ea38c-300">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ea38c-301"><strong>VideoAllocateBWAvg</strong></span><span class="sxs-lookup"><span data-stu-id="ea38c-301"><strong>VideoAllocateBWAvg</strong></span></span></p></td>
<td><p><span data-ttu-id="ea38c-302">int</span><span class="sxs-lookup"><span data-stu-id="ea38c-302">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="ea38c-303">ビデオに割り当てられている平均帯域幅。</span><span class="sxs-lookup"><span data-stu-id="ea38c-303">Average amount of bandwidth allocated for video.</span></span></p>
<p><span data-ttu-id="ea38c-304">この列は Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="ea38c-304">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ea38c-305"><strong>SendCodecTypes</strong></span><span class="sxs-lookup"><span data-stu-id="ea38c-305"><strong>SendCodecTypes</strong></span></span></p></td>
<td><p><span data-ttu-id="ea38c-306">smallint</span><span class="sxs-lookup"><span data-stu-id="ea38c-306">smallint</span></span></p></td>
<td><p><span data-ttu-id="ea38c-307">外部</span><span class="sxs-lookup"><span data-stu-id="ea38c-307">Foreign</span></span></p></td>
<td><p><span data-ttu-id="ea38c-308">送信者が使用するビデオコーデックの種類。</span><span class="sxs-lookup"><span data-stu-id="ea38c-308">Type of video codecs used by the sender.</span></span> <span data-ttu-id="ea38c-309">詳細については、「 <a href="lync-server-2013-codecdescription-table.md">Lync Server 2013 の CodecDescription テーブル</a>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ea38c-309">See the <a href="lync-server-2013-codecdescription-table.md">CodecDescription table in Lync Server 2013</a> for more information.</span></span></p>
<p><span data-ttu-id="ea38c-310">この列は Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="ea38c-310">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ea38c-311"><strong>Send解像度の幅</strong></span><span class="sxs-lookup"><span data-stu-id="ea38c-311"><strong>SendResolutionWidth</strong></span></span></p></td>
<td><p><span data-ttu-id="ea38c-312">int</span><span class="sxs-lookup"><span data-stu-id="ea38c-312">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="ea38c-313">送信者が使用した解像度の幅。</span><span class="sxs-lookup"><span data-stu-id="ea38c-313">Resolution width used by the sender.</span></span></p>
<p><span data-ttu-id="ea38c-314">この列は Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="ea38c-314">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ea38c-315"><strong>Sendの解像度の高さ</strong></span><span class="sxs-lookup"><span data-stu-id="ea38c-315"><strong>SendResolutionHeight</strong></span></span></p></td>
<td><p><span data-ttu-id="ea38c-316">int</span><span class="sxs-lookup"><span data-stu-id="ea38c-316">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="ea38c-317">送信者が使用する解像度の高さ。</span><span class="sxs-lookup"><span data-stu-id="ea38c-317">Resolution height used by the sender.</span></span></p>
<p><span data-ttu-id="ea38c-318">この列は Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="ea38c-318">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ea38c-319"><strong>SendFrameRateAverage</strong></span><span class="sxs-lookup"><span data-stu-id="ea38c-319"><strong>SendFrameRateAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="ea38c-320">float</span><span class="sxs-lookup"><span data-stu-id="ea38c-320">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="ea38c-321">送信者が使用した平均ビデオフレームレート送信。</span><span class="sxs-lookup"><span data-stu-id="ea38c-321">Average video frame rate transmission used by the sender.</span></span></p>
<p><span data-ttu-id="ea38c-322">この列は Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="ea38c-322">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ea38c-323"><strong>SendBitRateMaximum</strong></span><span class="sxs-lookup"><span data-stu-id="ea38c-323"><strong>SendBitRateMaximum</strong></span></span></p></td>
<td><p><span data-ttu-id="ea38c-324">int</span><span class="sxs-lookup"><span data-stu-id="ea38c-324">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="ea38c-325">送信者の最大ビットレート。</span><span class="sxs-lookup"><span data-stu-id="ea38c-325">Maximum bit rate for the sender.</span></span></p>
<p><span data-ttu-id="ea38c-326">この列は Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="ea38c-326">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ea38c-327"><strong>SendBitRateAverage</strong></span><span class="sxs-lookup"><span data-stu-id="ea38c-327"><strong>SendBitRateAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="ea38c-328">int</span><span class="sxs-lookup"><span data-stu-id="ea38c-328">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="ea38c-329">送信者の平均ビットレート。</span><span class="sxs-lookup"><span data-stu-id="ea38c-329">Average bit rate for the sender.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ea38c-330"><strong>SendVideoStreamsMax</strong></span><span class="sxs-lookup"><span data-stu-id="ea38c-330"><strong>SendVideoStreamsMax</strong></span></span></p></td>
<td><p><span data-ttu-id="ea38c-331">int</span><span class="sxs-lookup"><span data-stu-id="ea38c-331">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="ea38c-332">送信者が使用したビデオストリームの最大数。</span><span class="sxs-lookup"><span data-stu-id="ea38c-332">Maximum number of video streams used by the sender.</span></span></p>
<p><span data-ttu-id="ea38c-333">この列は Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="ea38c-333">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ea38c-334"><strong>RecvCodecTypes</strong></span><span class="sxs-lookup"><span data-stu-id="ea38c-334"><strong>RecvCodecTypes</strong></span></span></p></td>
<td><p><span data-ttu-id="ea38c-335">smallint</span><span class="sxs-lookup"><span data-stu-id="ea38c-335">smallint</span></span></p></td>
<td><p><span data-ttu-id="ea38c-336">外部</span><span class="sxs-lookup"><span data-stu-id="ea38c-336">Foreign</span></span></p></td>
<td><p><span data-ttu-id="ea38c-337">受信者が使用するビデオコード。</span><span class="sxs-lookup"><span data-stu-id="ea38c-337">Video codes used by the receiver.</span></span> <span data-ttu-id="ea38c-338">詳細については、「 <a href="lync-server-2013-codecdescription-table.md">Lync Server 2013 の CodecDescription テーブル</a>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ea38c-338">See the <a href="lync-server-2013-codecdescription-table.md">CodecDescription table in Lync Server 2013</a> for more information.</span></span></p>
<p><span data-ttu-id="ea38c-339">この列は Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="ea38c-339">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ea38c-340"><strong>RecvResolutionWidth</strong></span><span class="sxs-lookup"><span data-stu-id="ea38c-340"><strong>RecvResolutionWidth</strong></span></span></p></td>
<td><p><span data-ttu-id="ea38c-341">int</span><span class="sxs-lookup"><span data-stu-id="ea38c-341">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="ea38c-342">レシーバーで使用される解像度の幅。</span><span class="sxs-lookup"><span data-stu-id="ea38c-342">Resolution width used by the receiver.</span></span></p>
<p><span data-ttu-id="ea38c-343">この列は Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="ea38c-343">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ea38c-344"><strong>RecvResolutionHeight</strong></span><span class="sxs-lookup"><span data-stu-id="ea38c-344"><strong>RecvResolutionHeight</strong></span></span></p></td>
<td><p><span data-ttu-id="ea38c-345">int</span><span class="sxs-lookup"><span data-stu-id="ea38c-345">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="ea38c-346">受信者が使用する解像度の高さ。</span><span class="sxs-lookup"><span data-stu-id="ea38c-346">Resolution height used by the receiver.</span></span></p>
<p><span data-ttu-id="ea38c-347">この列は Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="ea38c-347">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ea38c-348"><strong>受信フレームレート</strong></span><span class="sxs-lookup"><span data-stu-id="ea38c-348"><strong>RecvFrameRateAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="ea38c-349">float</span><span class="sxs-lookup"><span data-stu-id="ea38c-349">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="ea38c-350">受信者が使用した平均ビデオフレームレート。</span><span class="sxs-lookup"><span data-stu-id="ea38c-350">Average video frame rate used by the receiver.</span></span></p>
<p><span data-ttu-id="ea38c-351">この列は Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="ea38c-351">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ea38c-352"><strong>RecvBitRateMaximum</strong></span><span class="sxs-lookup"><span data-stu-id="ea38c-352"><strong>RecvBitRateMaximum</strong></span></span></p></td>
<td><p><span data-ttu-id="ea38c-353">int</span><span class="sxs-lookup"><span data-stu-id="ea38c-353">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="ea38c-354">受信者の最大ビットレート。</span><span class="sxs-lookup"><span data-stu-id="ea38c-354">Maximum bit rate for the receiver.</span></span></p>
<p><span data-ttu-id="ea38c-355">この列は Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="ea38c-355">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ea38c-356"><strong>RecvBitRateAverage</strong></span><span class="sxs-lookup"><span data-stu-id="ea38c-356"><strong>RecvBitRateAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="ea38c-357">int</span><span class="sxs-lookup"><span data-stu-id="ea38c-357">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="ea38c-358">受信者の平均ビットレート。</span><span class="sxs-lookup"><span data-stu-id="ea38c-358">Average bit rate for the receiver.</span></span></p>
<p><span data-ttu-id="ea38c-359">この列は Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="ea38c-359">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ea38c-360"><strong>RecvVideoStreamsMax</strong></span><span class="sxs-lookup"><span data-stu-id="ea38c-360"><strong>RecvVideoStreamsMax</strong></span></span></p></td>
<td><p><span data-ttu-id="ea38c-361">int</span><span class="sxs-lookup"><span data-stu-id="ea38c-361">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="ea38c-362">受信者の最大ビデオストリーム。</span><span class="sxs-lookup"><span data-stu-id="ea38c-362">Maximum video streams for the receiver.</span></span></p>
<p><span data-ttu-id="ea38c-363">この列は Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="ea38c-363">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ea38c-364"><strong>RecvVideoStreamsMin</strong></span><span class="sxs-lookup"><span data-stu-id="ea38c-364"><strong>RecvVideoStreamsMin</strong></span></span></p></td>
<td><p><span data-ttu-id="ea38c-365">int</span><span class="sxs-lookup"><span data-stu-id="ea38c-365">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="ea38c-366">受信者の最小ビデオストリーム。</span><span class="sxs-lookup"><span data-stu-id="ea38c-366">Minimum video streams for the receiver.</span></span></p>
<p><span data-ttu-id="ea38c-367">この列は Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="ea38c-367">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ea38c-368"><strong>RecvVideoStreamsMode</strong></span><span class="sxs-lookup"><span data-stu-id="ea38c-368"><strong>RecvVideoStreamsMode</strong></span></span></p></td>
<td><p><span data-ttu-id="ea38c-369">int</span><span class="sxs-lookup"><span data-stu-id="ea38c-369">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="ea38c-370">受信者のビデオモード (たとえば、ギャラリーや単一ストリーム)。</span><span class="sxs-lookup"><span data-stu-id="ea38c-370">Video mode (for example, gallery or single stream) for the receiver.</span></span></p>
<p><span data-ttu-id="ea38c-371">この列は Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="ea38c-371">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ea38c-372"><strong>ビデオ plr</strong></span><span class="sxs-lookup"><span data-stu-id="ea38c-372"><strong>VideoPostFECPLR</strong></span></span></p></td>
<td><p><span data-ttu-id="ea38c-373">float</span><span class="sxs-lookup"><span data-stu-id="ea38c-373">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="ea38c-374">転送後のエラー訂正が適用された後のパケット損失率。</span><span class="sxs-lookup"><span data-stu-id="ea38c-374">Packet loss rate after forward error correction has been applied.</span></span></p>
<p><span data-ttu-id="ea38c-375">この列は Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="ea38c-375">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ea38c-376"><strong>動的機能</strong></span><span class="sxs-lookup"><span data-stu-id="ea38c-376"><strong>DynamicCapabilityPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="ea38c-377">float</span><span class="sxs-lookup"><span data-stu-id="ea38c-377">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="ea38c-378">動的機能フラグがアクティブになった時間のパーセンテージ。</span><span class="sxs-lookup"><span data-stu-id="ea38c-378">Percentage of time that the dynamic capability flag was active.</span></span></p>
<p><span data-ttu-id="ea38c-379">この列は Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="ea38c-379">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ea38c-380"><strong>解像度分</strong></span><span class="sxs-lookup"><span data-stu-id="ea38c-380"><strong>ResolutionMin</strong></span></span></p></td>
<td><p><span data-ttu-id="ea38c-381">char (9)</span><span class="sxs-lookup"><span data-stu-id="ea38c-381">char(9)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="ea38c-382">通話中に測定された最小解像度。</span><span class="sxs-lookup"><span data-stu-id="ea38c-382">Minimum resolution measured during the call.</span></span></p>
<p><span data-ttu-id="ea38c-383">この列は Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="ea38c-383">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ea38c-384"><strong>LowBitRateCallPercent</strong></span><span class="sxs-lookup"><span data-stu-id="ea38c-384"><strong>LowBitRateCallPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="ea38c-385">float</span><span class="sxs-lookup"><span data-stu-id="ea38c-385">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="ea38c-386">低ビットレートのしきい値 (70 kb/秒) 未満の通話のパーセンテージ。</span><span class="sxs-lookup"><span data-stu-id="ea38c-386">Percentage of the call below the low bit rate threshold (70 kilobits per second).</span></span></p>
<p><span data-ttu-id="ea38c-387">この列は Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="ea38c-387">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ea38c-388"><strong>LowFrameRateCallPercent</strong></span><span class="sxs-lookup"><span data-stu-id="ea38c-388"><strong>LowFrameRateCallPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="ea38c-389">float</span><span class="sxs-lookup"><span data-stu-id="ea38c-389">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="ea38c-390">低フレームレートのしきい値を下回る通話の割合 (1 秒あたりの7.5 フレーム数)。</span><span class="sxs-lookup"><span data-stu-id="ea38c-390">Percentage of the call below the low frame rate threshold (7.5 frames per second, inbound).</span></span></p>
<p><span data-ttu-id="ea38c-391">この列は Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="ea38c-391">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ea38c-392"><strong>低解像度</strong></span><span class="sxs-lookup"><span data-stu-id="ea38c-392"><strong>LowResolutionCallPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="ea38c-393">float</span><span class="sxs-lookup"><span data-stu-id="ea38c-393">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="ea38c-394">最低の解像度で発生した通話の割合。</span><span class="sxs-lookup"><span data-stu-id="ea38c-394">Percentage of the call that occurred at the lowest resolution.</span></span></p>
<p><span data-ttu-id="ea38c-395">この列は Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="ea38c-395">This column was introduced in Microsoft Lync Server 2013.</span></span></p>
<p><span data-ttu-id="ea38c-396">この列は Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="ea38c-396">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ea38c-397"><strong>DurationSeconds</strong></span><span class="sxs-lookup"><span data-stu-id="ea38c-397"><strong>DurationSeconds</strong></span></span></p></td>
<td><p><span data-ttu-id="ea38c-398">float</span><span class="sxs-lookup"><span data-stu-id="ea38c-398">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="ea38c-399">通話の長さ (秒単位)。</span><span class="sxs-lookup"><span data-stu-id="ea38c-399">Length of the call in seconds.</span></span></p>
<p><span data-ttu-id="ea38c-400">この列は Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="ea38c-400">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ea38c-401"><strong>IsAggregatedData</strong></span><span class="sxs-lookup"><span data-stu-id="ea38c-401"><strong>IsAggregatedData</strong></span></span></p></td>
<td><p><span data-ttu-id="ea38c-402">bit</span><span class="sxs-lookup"><span data-stu-id="ea38c-402">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="ea38c-403">複数の通話からデータが集計されたかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="ea38c-403">Indicates whether the data has been aggregated from multiple calls.</span></span></p>
<p><span data-ttu-id="ea38c-404">この列は Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="ea38c-404">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

