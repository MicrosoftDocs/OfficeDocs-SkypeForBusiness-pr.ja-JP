---
title: 'Lync Server 2013: AudioSignal テーブル'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: AudioSignal table
ms:assetid: 0013c8c6-cdf9-4d70-bc2a-cddd1560f66b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398064(v=OCS.15)
ms:contentKeyID: 48183217
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e6605a25191906660bbad11908f754a81360c893
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34840903"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="audiosignal-table-in-lync-server-2013"></a><span data-ttu-id="3a7a8-102">Lync Server 2013 の AudioSignal テーブル</span><span class="sxs-lookup"><span data-stu-id="3a7a8-102">AudioSignal table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3a7a8-103">_**最終更新日:** 2013-11-12_</span><span class="sxs-lookup"><span data-stu-id="3a7a8-103">_**Topic Last Modified:** 2013-11-12_</span></span>

<span data-ttu-id="3a7a8-104">各レコードは、1つのエンドポイントの音声シグナルメトリックを表します。</span><span class="sxs-lookup"><span data-stu-id="3a7a8-104">Each record represents audio signal metrics for one endpoint.</span></span> <span data-ttu-id="3a7a8-105">通常、各通話には2つのレコードがあります。1つは呼び出し元用、もう1つは呼び出し先用です。</span><span class="sxs-lookup"><span data-stu-id="3a7a8-105">Usually, each call has two records, one is for caller, and one is for callee.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="3a7a8-106"><strong>列</strong></span><span class="sxs-lookup"><span data-stu-id="3a7a8-106"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="3a7a8-107"><strong>データ型</strong></span><span class="sxs-lookup"><span data-stu-id="3a7a8-107"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="3a7a8-108"><strong>キー/インデックス</strong></span><span class="sxs-lookup"><span data-stu-id="3a7a8-108"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="3a7a8-109"><strong>詳細</strong></span><span class="sxs-lookup"><span data-stu-id="3a7a8-109"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="3a7a8-110"><strong>ConferenceDateTime</strong></span><span class="sxs-lookup"><span data-stu-id="3a7a8-110"><strong>ConferenceDateTime</strong></span></span></p></td>
<td><p><span data-ttu-id="3a7a8-111">datetime</span><span class="sxs-lookup"><span data-stu-id="3a7a8-111">datetime</span></span></p></td>
<td><p><span data-ttu-id="3a7a8-112">Primary</span><span class="sxs-lookup"><span data-stu-id="3a7a8-112">Primary</span></span></p></td>
<td><p><span data-ttu-id="3a7a8-113"><a href="lync-server-2013-medialine-table.md">Lync Server 2013 の MediaLine テーブル</a>から参照されている。</span><span class="sxs-lookup"><span data-stu-id="3a7a8-113">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3a7a8-114"><strong>SessionSeq</strong></span><span class="sxs-lookup"><span data-stu-id="3a7a8-114"><strong>SessionSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="3a7a8-115">int</span><span class="sxs-lookup"><span data-stu-id="3a7a8-115">int</span></span></p></td>
<td><p><span data-ttu-id="3a7a8-116">Primary</span><span class="sxs-lookup"><span data-stu-id="3a7a8-116">Primary</span></span></p></td>
<td><p><span data-ttu-id="3a7a8-117"><a href="lync-server-2013-medialine-table.md">Lync Server 2013 の MediaLine テーブル</a>から参照されている。</span><span class="sxs-lookup"><span data-stu-id="3a7a8-117">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3a7a8-118"><strong>MediaLineLabel</strong></span><span class="sxs-lookup"><span data-stu-id="3a7a8-118"><strong>MediaLineLabel</strong></span></span></p></td>
<td><p><span data-ttu-id="3a7a8-119">tinyint</span><span class="sxs-lookup"><span data-stu-id="3a7a8-119">tinyint</span></span></p></td>
<td><p><span data-ttu-id="3a7a8-120">Primary</span><span class="sxs-lookup"><span data-stu-id="3a7a8-120">Primary</span></span></p></td>
<td><p><span data-ttu-id="3a7a8-121"><a href="lync-server-2013-medialine-table.md">Lync Server 2013 の MediaLine テーブル</a>から参照されている。</span><span class="sxs-lookup"><span data-stu-id="3a7a8-121">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3a7a8-122"><strong>FromCaller</strong></span><span class="sxs-lookup"><span data-stu-id="3a7a8-122"><strong>FromCaller</strong></span></span></p></td>
<td><p><span data-ttu-id="3a7a8-123">bit</span><span class="sxs-lookup"><span data-stu-id="3a7a8-123">bit</span></span></p></td>
<td><p><span data-ttu-id="3a7a8-124">Primary</span><span class="sxs-lookup"><span data-stu-id="3a7a8-124">Primary</span></span></p></td>
<td><p><span data-ttu-id="3a7a8-125">0: 呼び出し先のデータ</span><span class="sxs-lookup"><span data-stu-id="3a7a8-125">0: Callee’s data</span></span></p>
<p><span data-ttu-id="3a7a8-126">1: 発信者のデータ</span><span class="sxs-lookup"><span data-stu-id="3a7a8-126">1: Caller’s data</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3a7a8-127"><strong>SendSignalLevel</strong></span><span class="sxs-lookup"><span data-stu-id="3a7a8-127"><strong>SendSignalLevel</strong></span></span></p></td>
<td><p><span data-ttu-id="3a7a8-128">int</span><span class="sxs-lookup"><span data-stu-id="3a7a8-128">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="3a7a8-129">アナログ高のゲイン制御オーディオ信号レベルを表します。</span><span class="sxs-lookup"><span data-stu-id="3a7a8-129">Represents the Post-Analog Gain Control audio signal level.</span></span> <span data-ttu-id="3a7a8-130">このメトリックの単位は dBmo です。</span><span class="sxs-lookup"><span data-stu-id="3a7a8-130">The unit for this metric is dBmo.</span></span> <span data-ttu-id="3a7a8-131">許容可能な品質を求めるには、少なくとも30個の dBmo を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3a7a8-131">For acceptable quality, it should be at least 30 dBmo.</span></span> <span data-ttu-id="3a7a8-132">このメトリックは、A/V 会議サーバーまたは IP 携帯電話によって報告されることはありません。</span><span class="sxs-lookup"><span data-stu-id="3a7a8-132">This metric is not reported by the A/V Conferencing Server or IP phones.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3a7a8-133"><strong>RecvSignalLevel</strong></span><span class="sxs-lookup"><span data-stu-id="3a7a8-133"><strong>RecvSignalLevel</strong></span></span></p></td>
<td><p><span data-ttu-id="3a7a8-134">int</span><span class="sxs-lookup"><span data-stu-id="3a7a8-134">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="3a7a8-135">「SendSignalLevel」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="3a7a8-135">See SendSignalLevel.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3a7a8-136"><strong>SendNoiseLevel</strong></span><span class="sxs-lookup"><span data-stu-id="3a7a8-136"><strong>SendNoiseLevel</strong></span></span></p></td>
<td><p><span data-ttu-id="3a7a8-137">int</span><span class="sxs-lookup"><span data-stu-id="3a7a8-137">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="3a7a8-138">アナログのゲイン制御オーディオノイズレベルを表します。</span><span class="sxs-lookup"><span data-stu-id="3a7a8-138">Represents the Post-Analog Gain Control audio noise level.</span></span> <span data-ttu-id="3a7a8-139">このメトリックの単位は dBmo です。</span><span class="sxs-lookup"><span data-stu-id="3a7a8-139">The unit for this metric is dBmo.</span></span> <span data-ttu-id="3a7a8-140">許容される品質には、35 dBmo よりも小さい値を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3a7a8-140">For acceptable quality, it should be less than 35 dBmo.</span></span> <span data-ttu-id="3a7a8-141">このメトリックは、A/V 会議サーバーまたは IP 携帯電話によって報告されることはありません。</span><span class="sxs-lookup"><span data-stu-id="3a7a8-141">This metric is not reported by the A/V Conferencing Server or IP phones.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3a7a8-142"><strong>RecvNoiseLevel</strong></span><span class="sxs-lookup"><span data-stu-id="3a7a8-142"><strong>RecvNoiseLevel</strong></span></span></p></td>
<td><p><span data-ttu-id="3a7a8-143">int</span><span class="sxs-lookup"><span data-stu-id="3a7a8-143">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="3a7a8-144">「SendNoiseLevel」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="3a7a8-144">See SendNoiseLevel.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3a7a8-145"><strong>EchoReturn</strong></span><span class="sxs-lookup"><span data-stu-id="3a7a8-145"><strong>EchoReturn</strong></span></span></p></td>
<td><p><span data-ttu-id="3a7a8-146">int</span><span class="sxs-lookup"><span data-stu-id="3a7a8-146">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="3a7a8-147">エコーリターンロスの拡張メトリック。</span><span class="sxs-lookup"><span data-stu-id="3a7a8-147">Echo Return Loss Enhancement metric.</span></span> <span data-ttu-id="3a7a8-148">このメトリックの単位は dB です。</span><span class="sxs-lookup"><span data-stu-id="3a7a8-148">The unit for this metric is dB.</span></span> <span data-ttu-id="3a7a8-149">小さい値は、エコーが少なくなります。</span><span class="sxs-lookup"><span data-stu-id="3a7a8-149">Lower values represent less echo.</span></span> <span data-ttu-id="3a7a8-150">このメトリックは、A/V 会議サーバーまたは IP 携帯電話によって報告されることはありません。</span><span class="sxs-lookup"><span data-stu-id="3a7a8-150">This metric is not reported by the A/V Conferencing Server or IP phones.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3a7a8-151"><strong>AudioSpeakerGlitchRate</strong></span><span class="sxs-lookup"><span data-stu-id="3a7a8-151"><strong>AudioSpeakerGlitchRate</strong></span></span></p></td>
<td><p><span data-ttu-id="3a7a8-152">int</span><span class="sxs-lookup"><span data-stu-id="3a7a8-152">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="3a7a8-153">スピーカーレンダリングに対する5分あたりの平均エラー。</span><span class="sxs-lookup"><span data-stu-id="3a7a8-153">Average glitches per five minutes for the loudspeaker rendering.</span></span> <span data-ttu-id="3a7a8-154">品質を向上させるには、5分未満でなければなりません。</span><span class="sxs-lookup"><span data-stu-id="3a7a8-154">For good quality, this should be less than one per five minutes.</span></span> <span data-ttu-id="3a7a8-155">A/V 会議サーバー、仲介サーバー、または IP 電話によって報告されていません。</span><span class="sxs-lookup"><span data-stu-id="3a7a8-155">Not reported by A/V Conferencing Servers, Mediation Servers, or IP phones.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3a7a8-156"><strong>AudioMicGlitchRate</strong></span><span class="sxs-lookup"><span data-stu-id="3a7a8-156"><strong>AudioMicGlitchRate</strong></span></span></p></td>
<td><p><span data-ttu-id="3a7a8-157">int</span><span class="sxs-lookup"><span data-stu-id="3a7a8-157">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="3a7a8-158">マイクをキャプチャするための5分あたりの平均エラー。</span><span class="sxs-lookup"><span data-stu-id="3a7a8-158">Average glitches per five minutes for the microphone capture.</span></span> <span data-ttu-id="3a7a8-159">品質を向上させるには、5分未満の値を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3a7a8-159">For good quality this should be less than one per five minutes.</span></span> <span data-ttu-id="3a7a8-160">A/V 会議サーバー、仲介サーバー、または IP 電話によって報告されていません。</span><span class="sxs-lookup"><span data-stu-id="3a7a8-160">Not reported by A/V Conferencing Servers, Mediation Servers, or IP phones.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3a7a8-161"><strong>AudioTimestampDriftRateMic</strong></span><span class="sxs-lookup"><span data-stu-id="3a7a8-161"><strong>AudioTimestampDriftRateMic</strong></span></span></p></td>
<td><p><span data-ttu-id="3a7a8-162">10進数 (9, 2)</span><span class="sxs-lookup"><span data-stu-id="3a7a8-162">decimal(9,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="3a7a8-163">CPU クロックを基準としたマイクデバイスクロックドリフトレート。</span><span class="sxs-lookup"><span data-stu-id="3a7a8-163">Microphone device clock drift rate, relative to CPU clock.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3a7a8-164"><strong>AudioTimestampDriftRateSpk</strong></span><span class="sxs-lookup"><span data-stu-id="3a7a8-164"><strong>AudioTimestampDriftRateSpk</strong></span></span></p></td>
<td><p><span data-ttu-id="3a7a8-165">10進数 (9, 2)</span><span class="sxs-lookup"><span data-stu-id="3a7a8-165">decimal(9,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="3a7a8-166">CPU クロックを基準としたスピーカーデバイスクロックドリフトレート。</span><span class="sxs-lookup"><span data-stu-id="3a7a8-166">Speaker device clock drift rate, relative to CPU clock.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3a7a8-167"><strong>AudioTimestampErrorMicMs</strong></span><span class="sxs-lookup"><span data-stu-id="3a7a8-167"><strong>AudioTimestampErrorMicMs</strong></span></span></p></td>
<td><p><span data-ttu-id="3a7a8-168">10進数 (9, 2)</span><span class="sxs-lookup"><span data-stu-id="3a7a8-168">decimal(9,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="3a7a8-169">CPU クロックを基準としたスピーカーデバイスクロックドリフトレート。</span><span class="sxs-lookup"><span data-stu-id="3a7a8-169">Speaker device clock drift rate, relative to CPU clock.</span></span></p>
<p><span data-ttu-id="3a7a8-170">平均マイクキャプチャストリームタイムスタンプエラー (ミリ秒単位)、通話の最後の20秒。</span><span class="sxs-lookup"><span data-stu-id="3a7a8-170">Average microphone capture stream time stamp error, in milliseconds, in the last 20 seconds of the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3a7a8-171"><strong>AudioTimestampErrorSpkMs</strong></span><span class="sxs-lookup"><span data-stu-id="3a7a8-171"><strong>AudioTimestampErrorSpkMs</strong></span></span></p></td>
<td><p><span data-ttu-id="3a7a8-172">10進数 (9, 2)</span><span class="sxs-lookup"><span data-stu-id="3a7a8-172">decimal(9,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="3a7a8-173">通話の最後の20秒間の平均スピーカーレンダーストリームタイムスタンプエラー (ミリ秒単位)。</span><span class="sxs-lookup"><span data-stu-id="3a7a8-173">Average speaker render stream time stamp error, in milliseconds, in the last 20 seconds of the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3a7a8-174"><strong>VsEntryCauses 原因</strong></span><span class="sxs-lookup"><span data-stu-id="3a7a8-174"><strong>VsEntryCauses</strong></span></span></p></td>
<td><p><span data-ttu-id="3a7a8-175">smallint</span><span class="sxs-lookup"><span data-stu-id="3a7a8-175">smallint</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="3a7a8-176">音声スイッチは半二重モードで、中断機能が低減されます。</span><span class="sxs-lookup"><span data-stu-id="3a7a8-176">Voice switch is a half-duplex mode with reduced interruption ability.</span></span> <span data-ttu-id="3a7a8-177">音声スイッチの入力の原因:</span><span class="sxs-lookup"><span data-stu-id="3a7a8-177">Causes of voice switch entry:</span></span></p>
<p><span data-ttu-id="3a7a8-178">ENTER_VS_BADTS 0x01</span><span class="sxs-lookup"><span data-stu-id="3a7a8-178">ENTER_VS_BADTS 0x01</span></span></p>
<p><span data-ttu-id="3a7a8-179">ENTER_VS_ECHO 0x02</span><span class="sxs-lookup"><span data-stu-id="3a7a8-179">ENTER_VS_ECHO 0x02</span></span></p>
<p><span data-ttu-id="3a7a8-180">ENTER_VS_FORCEORCONVERGENCE 0x04</span><span class="sxs-lookup"><span data-stu-id="3a7a8-180">ENTER_VS_FORCEORCONVERGENCE 0x04</span></span></p>
<p><span data-ttu-id="3a7a8-181">ENTER_VS_DNLP 0x08</span><span class="sxs-lookup"><span data-stu-id="3a7a8-181">ENTER_VS_DNLP 0x08</span></span></p>
<p><span data-ttu-id="3a7a8-182">原因として、このような個々の原因が考えられます。</span><span class="sxs-lookup"><span data-stu-id="3a7a8-182">The cause can be a combination of those individual causes.</span></span> <span data-ttu-id="3a7a8-183">ENTER_VS_FORCEORCONVERGENCE は、テスト目的でのみ、regkey で有効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="3a7a8-183">ENTER_VS_FORCEORCONVERGENCE can only be enabled by regkey for test purpose.</span></span></p>
<p><span data-ttu-id="3a7a8-184">この列のデータ型は、Microsoft Lync Server 2013 で変更されました。</span><span class="sxs-lookup"><span data-stu-id="3a7a8-184">The data type for this column was changed in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3a7a8-185"><strong>EchoEventCauses</strong></span><span class="sxs-lookup"><span data-stu-id="3a7a8-185"><strong>EchoEventCauses</strong></span></span></p></td>
<td><p><span data-ttu-id="3a7a8-186">tinyint</span><span class="sxs-lookup"><span data-stu-id="3a7a8-186">tinyint</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="3a7a8-187">エコーイベントの原因:</span><span class="sxs-lookup"><span data-stu-id="3a7a8-187">Causes of an echo event:</span></span></p>
<p><span data-ttu-id="3a7a8-188">ECHO_EVENT_BAD_TIMESTAMP 0x01</span><span class="sxs-lookup"><span data-stu-id="3a7a8-188">ECHO_EVENT_BAD_TIMESTAMP 0x01</span></span></p>
<p><span data-ttu-id="3a7a8-189">ECHO_EVENT_POSTAEC_ECHO 0x02</span><span class="sxs-lookup"><span data-stu-id="3a7a8-189">ECHO_EVENT_POSTAEC_ECHO 0x02</span></span></p>
<p><span data-ttu-id="3a7a8-190">ECHO_EVENT_ANLP 0x04</span><span class="sxs-lookup"><span data-stu-id="3a7a8-190">ECHO_EVENT_ANLP 0x04</span></span></p>
<p><span data-ttu-id="3a7a8-191">ECHO_EVENT_DNLP 0x08</span><span class="sxs-lookup"><span data-stu-id="3a7a8-191">ECHO_EVENT_DNLP 0x08</span></span></p>
<p><span data-ttu-id="3a7a8-192">ECHO_EVENT_MIC_CLIPPING 0x10</span><span class="sxs-lookup"><span data-stu-id="3a7a8-192">ECHO_EVENT_MIC_CLIPPING 0x10</span></span></p>
<p><span data-ttu-id="3a7a8-193">ECHO_EVENT_BAD_STATE 0x20</span><span class="sxs-lookup"><span data-stu-id="3a7a8-193">ECHO_EVENT_BAD_STATE 0x20</span></span></p>
<p><span data-ttu-id="3a7a8-194">原因として、このような個々の原因が考えられます。</span><span class="sxs-lookup"><span data-stu-id="3a7a8-194">The cause can be a combination of those individual causes.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3a7a8-195"><strong>EchoPercentMicIn</strong></span><span class="sxs-lookup"><span data-stu-id="3a7a8-195"><strong>EchoPercentMicIn</strong></span></span></p></td>
<td><p><span data-ttu-id="3a7a8-196">10進数 (5, 2)</span><span class="sxs-lookup"><span data-stu-id="3a7a8-196">decimal(5,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="3a7a8-197">マイクのキャプチャストリームでエコーが検出された時間の割合。</span><span class="sxs-lookup"><span data-stu-id="3a7a8-197">Percentage of time when echo was detected in the microphone capture stream.</span></span> <span data-ttu-id="3a7a8-198">一般的に、ヘッドセットまたはハンドセットの値は低く、スピーカーフォンやスタンドアロンスピーカーでは高くなります。</span><span class="sxs-lookup"><span data-stu-id="3a7a8-198">Typically, values are low for headsets or handsets, and higher for speaker phones or stand-alone speakers.</span></span> <span data-ttu-id="3a7a8-199">オンボード音響エコーキャンセルをサポートしているデバイスでは、高値を指定するとエコーリークが発生します。</span><span class="sxs-lookup"><span data-stu-id="3a7a8-199">For devices that support on-board acoustic echo cancellation, high values indicate echo leak.</span></span> <span data-ttu-id="3a7a8-200">その他のデバイスでは、デバイスの品質を評価するためにこのメトリックを使用しないようにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="3a7a8-200">For other devices, this metric should not be used to evaluate device quality.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3a7a8-201"><strong>EchoPercentSend</strong></span><span class="sxs-lookup"><span data-stu-id="3a7a8-201"><strong>EchoPercentSend</strong></span></span></p></td>
<td><p><span data-ttu-id="3a7a8-202">10進数 (5, 2)</span><span class="sxs-lookup"><span data-stu-id="3a7a8-202">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="3a7a8-203">送信ストリームでエコーが検出された時間のパーセンテージ。</span><span class="sxs-lookup"><span data-stu-id="3a7a8-203">Percentage of time when echo is detected in sent stream.</span></span> <span data-ttu-id="3a7a8-204">送信ストリームでのエコー率が高いと、エコーが発生したことを示します。</span><span class="sxs-lookup"><span data-stu-id="3a7a8-204">High echo percentage in send streams an indication of echo leak.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3a7a8-205"><strong>RxAGCSignalLevel</strong></span><span class="sxs-lookup"><span data-stu-id="3a7a8-205"><strong>RxAGCSignalLevel</strong></span></span></p></td>
<td><p><span data-ttu-id="3a7a8-206">int</span><span class="sxs-lookup"><span data-stu-id="3a7a8-206">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="3a7a8-207">ゲートウェイからの仲介サーバー上の受信したシグナルレベル。これは、仲介サーバーにのみ適用されます。</span><span class="sxs-lookup"><span data-stu-id="3a7a8-207">Received signal level on the Mediation Server from the Gateway; this applies only to the Mediation Server.</span></span> <span data-ttu-id="3a7a8-208">このメトリックの単位は dBoV です。</span><span class="sxs-lookup"><span data-stu-id="3a7a8-208">The unit of this metric is dBoV.</span></span> <span data-ttu-id="3a7a8-209">品質を向上させるには、許容範囲は [-30 ~-18] の dBoV にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="3a7a8-209">For good quality, the acceptable range should be [-30 to -18] dBoV.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3a7a8-210"><strong>RxAGCNoiseLevel</strong></span><span class="sxs-lookup"><span data-stu-id="3a7a8-210"><strong>RxAGCNoiseLevel</strong></span></span></p></td>
<td><p><span data-ttu-id="3a7a8-211">int</span><span class="sxs-lookup"><span data-stu-id="3a7a8-211">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="3a7a8-212">ゲートウェイからの仲介サーバーで受信したシグナルレベル。</span><span class="sxs-lookup"><span data-stu-id="3a7a8-212">Received signal level on the Mediation Server from the Gateway.</span></span> <span data-ttu-id="3a7a8-213">これは、仲介サーバーにのみ適用されます。</span><span class="sxs-lookup"><span data-stu-id="3a7a8-213">This applies only to the Mediation Server.</span></span> <span data-ttu-id="3a7a8-214">このメトリックの単位は dBoV です。</span><span class="sxs-lookup"><span data-stu-id="3a7a8-214">The unit of this metric is dBoV.</span></span> <span data-ttu-id="3a7a8-215">品質を向上させるには、許容範囲として 50 dBoV 未満の値を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3a7a8-215">For good quality, the acceptable range should be less than -50 dBoV.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3a7a8-216"><strong>RxAvgAGCGain</strong></span><span class="sxs-lookup"><span data-stu-id="3a7a8-216"><strong>RxAvgAGCGain</strong></span></span></p></td>
<td><p><span data-ttu-id="3a7a8-217">int</span><span class="sxs-lookup"><span data-stu-id="3a7a8-217">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="3a7a8-218">仲介サーバー側の自動ゲイン制御 (AGC)。</span><span class="sxs-lookup"><span data-stu-id="3a7a8-218">Automatic gain control (AGC) on the Mediation Server side.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3a7a8-219"><strong>InitialSignalLevelRMS</strong></span><span class="sxs-lookup"><span data-stu-id="3a7a8-219"><strong>InitialSignalLevelRMS</strong></span></span></p></td>
<td><p><span data-ttu-id="3a7a8-220">float</span><span class="sxs-lookup"><span data-stu-id="3a7a8-220">float</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="3a7a8-221">通話の最初の30秒以内の着信シグナルのルート平均平方根 (RMS)。</span><span class="sxs-lookup"><span data-stu-id="3a7a8-221">The root mean square (RMS) of the incoming signal of up to the first 30 seconds of the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3a7a8-222"><strong>RecvSignalLevelCh1</strong></span><span class="sxs-lookup"><span data-stu-id="3a7a8-222"><strong>RecvSignalLevelCh1</strong></span></span></p></td>
<td><p><span data-ttu-id="3a7a8-223">int</span><span class="sxs-lookup"><span data-stu-id="3a7a8-223">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="3a7a8-224">チャネル1で受信したシグナルレベル。</span><span class="sxs-lookup"><span data-stu-id="3a7a8-224">Signal level as received on channel 1.</span></span></p>
<p><span data-ttu-id="3a7a8-225">この列は Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="3a7a8-225">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3a7a8-226"><strong>RecvSignalLevelCh2</strong></span><span class="sxs-lookup"><span data-stu-id="3a7a8-226"><strong>RecvSignalLevelCh2</strong></span></span></p></td>
<td><p><span data-ttu-id="3a7a8-227">int</span><span class="sxs-lookup"><span data-stu-id="3a7a8-227">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="3a7a8-228">チャネル2で受信したシグナルレベル。</span><span class="sxs-lookup"><span data-stu-id="3a7a8-228">Signal level as received on channel 2.</span></span></p>
<p><span data-ttu-id="3a7a8-229">この列は Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="3a7a8-229">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3a7a8-230"><strong>RecvNoiseLevelCh1</strong></span><span class="sxs-lookup"><span data-stu-id="3a7a8-230"><strong>RecvNoiseLevelCh1</strong></span></span></p></td>
<td><p><span data-ttu-id="3a7a8-231">int</span><span class="sxs-lookup"><span data-stu-id="3a7a8-231">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="3a7a8-232">チャネル1で受信したノイズレベル。</span><span class="sxs-lookup"><span data-stu-id="3a7a8-232">Noise level as received on channel 1.</span></span></p>
<p><span data-ttu-id="3a7a8-233">この列は Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="3a7a8-233">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3a7a8-234"><strong>RecvNoiseLevelCh2</strong></span><span class="sxs-lookup"><span data-stu-id="3a7a8-234"><strong>RecvNoiseLevelCh2</strong></span></span></p></td>
<td><p><span data-ttu-id="3a7a8-235">int</span><span class="sxs-lookup"><span data-stu-id="3a7a8-235">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="3a7a8-236">チャネル2で受信したノイズレベル。</span><span class="sxs-lookup"><span data-stu-id="3a7a8-236">Noise level as received on channel 2.</span></span></p>
<p><span data-ttu-id="3a7a8-237">この列は Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="3a7a8-237">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3a7a8-238"><strong>SendSignalLevelCh1</strong></span><span class="sxs-lookup"><span data-stu-id="3a7a8-238"><strong>SendSignalLevelCh1</strong></span></span></p></td>
<td><p><span data-ttu-id="3a7a8-239">int</span><span class="sxs-lookup"><span data-stu-id="3a7a8-239">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="3a7a8-240">チャネル1で送信されたシグナルレベル。</span><span class="sxs-lookup"><span data-stu-id="3a7a8-240">Signal level as sent on channel 1.</span></span></p>
<p><span data-ttu-id="3a7a8-241">この列は Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="3a7a8-241">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3a7a8-242"><strong>SendSignalLevelCh2</strong></span><span class="sxs-lookup"><span data-stu-id="3a7a8-242"><strong>SendSignalLevelCh2</strong></span></span></p></td>
<td><p><span data-ttu-id="3a7a8-243">int</span><span class="sxs-lookup"><span data-stu-id="3a7a8-243">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="3a7a8-244">チャネル2で送信されたシグナルレベル。</span><span class="sxs-lookup"><span data-stu-id="3a7a8-244">Signal level as sent on channel 2.</span></span></p>
<p><span data-ttu-id="3a7a8-245">この列は Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="3a7a8-245">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3a7a8-246"><strong>SendNoiseLevelCh1</strong></span><span class="sxs-lookup"><span data-stu-id="3a7a8-246"><strong>SendNoiseLevelCh1</strong></span></span></p></td>
<td><p><span data-ttu-id="3a7a8-247">int</span><span class="sxs-lookup"><span data-stu-id="3a7a8-247">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="3a7a8-248">チャネル1で送信されたノイズレベル。</span><span class="sxs-lookup"><span data-stu-id="3a7a8-248">Noise level as sent on channel 1.</span></span></p>
<p><span data-ttu-id="3a7a8-249">この列は Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="3a7a8-249">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3a7a8-250"><strong>SendNoiseLevelCh2</strong></span><span class="sxs-lookup"><span data-stu-id="3a7a8-250"><strong>SendNoiseLevelCh2</strong></span></span></p></td>
<td><p><span data-ttu-id="3a7a8-251">int</span><span class="sxs-lookup"><span data-stu-id="3a7a8-251">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="3a7a8-252">チャンネル2に送信されたノイズレベル。</span><span class="sxs-lookup"><span data-stu-id="3a7a8-252">Noise level as sent on channel 2.</span></span></p>
<p><span data-ttu-id="3a7a8-253">この列は Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="3a7a8-253">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

