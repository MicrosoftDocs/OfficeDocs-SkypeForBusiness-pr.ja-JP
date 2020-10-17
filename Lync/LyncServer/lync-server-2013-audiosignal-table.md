---
title: 'Lync Server 2013: AudioSignal テーブル'
description: 'Lync Server 2013: AudioSignal テーブル。'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: AudioSignal table
ms:assetid: 0013c8c6-cdf9-4d70-bc2a-cddd1560f66b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398064(v=OCS.15)
ms:contentKeyID: 48183217
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 82f3b3119eaccfe56c4706cff07469bc3434461f
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48568763"
---
# <a name="audiosignal-table-in-lync-server-2013"></a><span data-ttu-id="ed553-103">Lync Server 2013 の AudioSignal テーブル</span><span class="sxs-lookup"><span data-stu-id="ed553-103">AudioSignal table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ed553-104">_**トピックの最終更新日:** 2013-11-12_</span><span class="sxs-lookup"><span data-stu-id="ed553-104">_**Topic Last Modified:** 2013-11-12_</span></span>

<span data-ttu-id="ed553-105">各レコードは、1つのエンドポイントの音声信号指標を表します。</span><span class="sxs-lookup"><span data-stu-id="ed553-105">Each record represents audio signal metrics for one endpoint.</span></span> <span data-ttu-id="ed553-106">通常、それぞれの呼び出しには2つのレコードがあります。1つは発信者用、もう1つは呼び出し先用です。</span><span class="sxs-lookup"><span data-stu-id="ed553-106">Usually, each call has two records, one is for caller, and one is for callee.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="ed553-107"><strong>列</strong></span><span class="sxs-lookup"><span data-stu-id="ed553-107"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="ed553-108"><strong>データ型</strong></span><span class="sxs-lookup"><span data-stu-id="ed553-108"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="ed553-109"><strong>キー/インデックス</strong></span><span class="sxs-lookup"><span data-stu-id="ed553-109"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="ed553-110"><strong>詳細</strong></span><span class="sxs-lookup"><span data-stu-id="ed553-110"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ed553-111"><strong>ConferenceDateTime</strong></span><span class="sxs-lookup"><span data-stu-id="ed553-111"><strong>ConferenceDateTime</strong></span></span></p></td>
<td><p><span data-ttu-id="ed553-112">日付型</span><span class="sxs-lookup"><span data-stu-id="ed553-112">datetime</span></span></p></td>
<td><p><span data-ttu-id="ed553-113">Primary</span><span class="sxs-lookup"><span data-stu-id="ed553-113">Primary</span></span></p></td>
<td><p><span data-ttu-id="ed553-114"><a href="lync-server-2013-medialine-table.md">Lync Server 2013 の MediaLine テーブル</a>から参照されます。</span><span class="sxs-lookup"><span data-stu-id="ed553-114">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ed553-115"><strong>SessionSeq</strong></span><span class="sxs-lookup"><span data-stu-id="ed553-115"><strong>SessionSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="ed553-116">int</span><span class="sxs-lookup"><span data-stu-id="ed553-116">int</span></span></p></td>
<td><p><span data-ttu-id="ed553-117">Primary</span><span class="sxs-lookup"><span data-stu-id="ed553-117">Primary</span></span></p></td>
<td><p><span data-ttu-id="ed553-118"><a href="lync-server-2013-medialine-table.md">Lync Server 2013 の MediaLine テーブル</a>から参照されます。</span><span class="sxs-lookup"><span data-stu-id="ed553-118">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ed553-119"><strong>MediaLineLabel</strong></span><span class="sxs-lookup"><span data-stu-id="ed553-119"><strong>MediaLineLabel</strong></span></span></p></td>
<td><p><span data-ttu-id="ed553-120">tinyint</span><span class="sxs-lookup"><span data-stu-id="ed553-120">tinyint</span></span></p></td>
<td><p><span data-ttu-id="ed553-121">Primary</span><span class="sxs-lookup"><span data-stu-id="ed553-121">Primary</span></span></p></td>
<td><p><span data-ttu-id="ed553-122"><a href="lync-server-2013-medialine-table.md">Lync Server 2013 の MediaLine テーブル</a>から参照されます。</span><span class="sxs-lookup"><span data-stu-id="ed553-122">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ed553-123"><strong>FromCaller</strong></span><span class="sxs-lookup"><span data-stu-id="ed553-123"><strong>FromCaller</strong></span></span></p></td>
<td><p><span data-ttu-id="ed553-124">若干</span><span class="sxs-lookup"><span data-stu-id="ed553-124">bit</span></span></p></td>
<td><p><span data-ttu-id="ed553-125">Primary</span><span class="sxs-lookup"><span data-stu-id="ed553-125">Primary</span></span></p></td>
<td><p><span data-ttu-id="ed553-126">0: 呼び出し先のデータ</span><span class="sxs-lookup"><span data-stu-id="ed553-126">0: Callee’s data</span></span></p>
<p><span data-ttu-id="ed553-127">1: 発信者のデータ</span><span class="sxs-lookup"><span data-stu-id="ed553-127">1: Caller’s data</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ed553-128"><strong>SendSignalLevel</strong></span><span class="sxs-lookup"><span data-stu-id="ed553-128"><strong>SendSignalLevel</strong></span></span></p></td>
<td><p><span data-ttu-id="ed553-129">int</span><span class="sxs-lookup"><span data-stu-id="ed553-129">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="ed553-130">アナログのゲイン制御音声信号レベルを表します。</span><span class="sxs-lookup"><span data-stu-id="ed553-130">Represents the Post-Analog Gain Control audio signal level.</span></span> <span data-ttu-id="ed553-131">この測定指標の単位は dBmo です。</span><span class="sxs-lookup"><span data-stu-id="ed553-131">The unit for this metric is dBmo.</span></span> <span data-ttu-id="ed553-132">許容される品質は 30 dBmo 以上です。</span><span class="sxs-lookup"><span data-stu-id="ed553-132">For acceptable quality, it should be at least 30 dBmo.</span></span> <span data-ttu-id="ed553-133">この測定指標は、音声ビデオ会議サーバーまたは IP 電話では報告されません。</span><span class="sxs-lookup"><span data-stu-id="ed553-133">This metric is not reported by the A/V Conferencing Server or IP phones.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ed553-134"><strong>RecvSignalLevel</strong></span><span class="sxs-lookup"><span data-stu-id="ed553-134"><strong>RecvSignalLevel</strong></span></span></p></td>
<td><p><span data-ttu-id="ed553-135">int</span><span class="sxs-lookup"><span data-stu-id="ed553-135">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="ed553-136">SendSignalLevel を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ed553-136">See SendSignalLevel.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ed553-137"><strong>SendNoiseLevel</strong></span><span class="sxs-lookup"><span data-stu-id="ed553-137"><strong>SendNoiseLevel</strong></span></span></p></td>
<td><p><span data-ttu-id="ed553-138">int</span><span class="sxs-lookup"><span data-stu-id="ed553-138">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="ed553-139">アナログのゲインコントロールのオーディオノイズレベルを表します。</span><span class="sxs-lookup"><span data-stu-id="ed553-139">Represents the Post-Analog Gain Control audio noise level.</span></span> <span data-ttu-id="ed553-140">この測定指標の単位は dBmo です。</span><span class="sxs-lookup"><span data-stu-id="ed553-140">The unit for this metric is dBmo.</span></span> <span data-ttu-id="ed553-141">許容される品質は 35 dBmo 未満です。</span><span class="sxs-lookup"><span data-stu-id="ed553-141">For acceptable quality, it should be less than 35 dBmo.</span></span> <span data-ttu-id="ed553-142">この測定指標は、音声ビデオ会議サーバーまたは IP 電話では報告されません。</span><span class="sxs-lookup"><span data-stu-id="ed553-142">This metric is not reported by the A/V Conferencing Server or IP phones.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ed553-143"><strong>RecvNoiseLevel</strong></span><span class="sxs-lookup"><span data-stu-id="ed553-143"><strong>RecvNoiseLevel</strong></span></span></p></td>
<td><p><span data-ttu-id="ed553-144">int</span><span class="sxs-lookup"><span data-stu-id="ed553-144">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="ed553-145">SendNoiseLevel を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ed553-145">See SendNoiseLevel.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ed553-146"><strong>EchoReturn</strong></span><span class="sxs-lookup"><span data-stu-id="ed553-146"><strong>EchoReturn</strong></span></span></p></td>
<td><p><span data-ttu-id="ed553-147">int</span><span class="sxs-lookup"><span data-stu-id="ed553-147">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="ed553-148">エコーリターン損失の拡張指標。</span><span class="sxs-lookup"><span data-stu-id="ed553-148">Echo Return Loss Enhancement metric.</span></span> <span data-ttu-id="ed553-149">この測定指標の単位は dB です。</span><span class="sxs-lookup"><span data-stu-id="ed553-149">The unit for this metric is dB.</span></span> <span data-ttu-id="ed553-150">値が小さいほど、エコーが少ないことを示します。</span><span class="sxs-lookup"><span data-stu-id="ed553-150">Lower values represent less echo.</span></span> <span data-ttu-id="ed553-151">この測定指標は、音声ビデオ会議サーバーまたは IP 電話では報告されません。</span><span class="sxs-lookup"><span data-stu-id="ed553-151">This metric is not reported by the A/V Conferencing Server or IP phones.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ed553-152"><strong>AudioSpeakerGlitchRate</strong></span><span class="sxs-lookup"><span data-stu-id="ed553-152"><strong>AudioSpeakerGlitchRate</strong></span></span></p></td>
<td><p><span data-ttu-id="ed553-153">int</span><span class="sxs-lookup"><span data-stu-id="ed553-153">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="ed553-154">Loudspeaker レンダリングの5分あたりの平均の異常。</span><span class="sxs-lookup"><span data-stu-id="ed553-154">Average glitches per five minutes for the loudspeaker rendering.</span></span> <span data-ttu-id="ed553-155">良好な品質といえるのは、5 分間に 1 回未満です。</span><span class="sxs-lookup"><span data-stu-id="ed553-155">For good quality, this should be less than one per five minutes.</span></span> <span data-ttu-id="ed553-156">音声ビデオ会議サーバー、仲介サーバー、または IP 電話では報告されません。</span><span class="sxs-lookup"><span data-stu-id="ed553-156">Not reported by A/V Conferencing Servers, Mediation Servers, or IP phones.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ed553-157"><strong>AudioMicGlitchRate</strong></span><span class="sxs-lookup"><span data-stu-id="ed553-157"><strong>AudioMicGlitchRate</strong></span></span></p></td>
<td><p><span data-ttu-id="ed553-158">int</span><span class="sxs-lookup"><span data-stu-id="ed553-158">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="ed553-159">マイクキャプチャに対する5分あたりの平均の異常。</span><span class="sxs-lookup"><span data-stu-id="ed553-159">Average glitches per five minutes for the microphone capture.</span></span> <span data-ttu-id="ed553-160">良好な品質といえるのは、5 分間に 1 回未満です。</span><span class="sxs-lookup"><span data-stu-id="ed553-160">For good quality this should be less than one per five minutes.</span></span> <span data-ttu-id="ed553-161">音声ビデオ会議サーバー、仲介サーバー、または IP 電話では報告されません。</span><span class="sxs-lookup"><span data-stu-id="ed553-161">Not reported by A/V Conferencing Servers, Mediation Servers, or IP phones.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ed553-162"><strong>AudioTimestampDriftRateMic</strong></span><span class="sxs-lookup"><span data-stu-id="ed553-162"><strong>AudioTimestampDriftRateMic</strong></span></span></p></td>
<td><p><span data-ttu-id="ed553-163">10進数 (9、2)</span><span class="sxs-lookup"><span data-stu-id="ed553-163">decimal(9,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="ed553-164">CPU クロックに対するマイクデバイスのクロック誤差の割合です。</span><span class="sxs-lookup"><span data-stu-id="ed553-164">Microphone device clock drift rate, relative to CPU clock.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ed553-165"><strong>AudioTimestampDriftRateSpk</strong></span><span class="sxs-lookup"><span data-stu-id="ed553-165"><strong>AudioTimestampDriftRateSpk</strong></span></span></p></td>
<td><p><span data-ttu-id="ed553-166">10進数 (9、2)</span><span class="sxs-lookup"><span data-stu-id="ed553-166">decimal(9,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="ed553-167">CPU クロックに対するスピーカーデバイスのクロック誤差の割合。</span><span class="sxs-lookup"><span data-stu-id="ed553-167">Speaker device clock drift rate, relative to CPU clock.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ed553-168"><strong>AudioTimestampErrorMicMs</strong></span><span class="sxs-lookup"><span data-stu-id="ed553-168"><strong>AudioTimestampErrorMicMs</strong></span></span></p></td>
<td><p><span data-ttu-id="ed553-169">10進数 (9、2)</span><span class="sxs-lookup"><span data-stu-id="ed553-169">decimal(9,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="ed553-170">CPU クロックに対するスピーカーデバイスのクロック誤差の割合。</span><span class="sxs-lookup"><span data-stu-id="ed553-170">Speaker device clock drift rate, relative to CPU clock.</span></span></p>
<p><span data-ttu-id="ed553-171">過去 20 秒間の通話での平均マイク キャプチャ ストリーム タイム スタンプ エラーです (ミリ秒単位)。</span><span class="sxs-lookup"><span data-stu-id="ed553-171">Average microphone capture stream time stamp error, in milliseconds, in the last 20 seconds of the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ed553-172"><strong>AudioTimestampErrorSpkMs</strong></span><span class="sxs-lookup"><span data-stu-id="ed553-172"><strong>AudioTimestampErrorSpkMs</strong></span></span></p></td>
<td><p><span data-ttu-id="ed553-173">10進数 (9、2)</span><span class="sxs-lookup"><span data-stu-id="ed553-173">decimal(9,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="ed553-174">過去20秒間の通話の平均スピーカーレンダーストリームタイムスタンプエラー (ミリ秒単位)。</span><span class="sxs-lookup"><span data-stu-id="ed553-174">Average speaker render stream time stamp error, in milliseconds, in the last 20 seconds of the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ed553-175"><strong>VsEntryCauses</strong></span><span class="sxs-lookup"><span data-stu-id="ed553-175"><strong>VsEntryCauses</strong></span></span></p></td>
<td><p><span data-ttu-id="ed553-176">smallint</span><span class="sxs-lookup"><span data-stu-id="ed553-176">smallint</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="ed553-177">音声スイッチは、遮断能力が低下した半二重モードです。</span><span class="sxs-lookup"><span data-stu-id="ed553-177">Voice switch is a half-duplex mode with reduced interruption ability.</span></span> <span data-ttu-id="ed553-178">音声スイッチエントリの原因:</span><span class="sxs-lookup"><span data-stu-id="ed553-178">Causes of voice switch entry:</span></span></p>
<p><span data-ttu-id="ed553-179">ENTER_VS_BADTS 0x01</span><span class="sxs-lookup"><span data-stu-id="ed553-179">ENTER_VS_BADTS 0x01</span></span></p>
<p><span data-ttu-id="ed553-180">ENTER_VS_ECHO 0x02</span><span class="sxs-lookup"><span data-stu-id="ed553-180">ENTER_VS_ECHO 0x02</span></span></p>
<p><span data-ttu-id="ed553-181">ENTER_VS_FORCEORCONVERGENCE 0x04</span><span class="sxs-lookup"><span data-stu-id="ed553-181">ENTER_VS_FORCEORCONVERGENCE 0x04</span></span></p>
<p><span data-ttu-id="ed553-182">ENTER_VS_DNLP 0x08</span><span class="sxs-lookup"><span data-stu-id="ed553-182">ENTER_VS_DNLP 0x08</span></span></p>
<p><span data-ttu-id="ed553-183">原因として、個々の原因の組み合わせが考えられます。</span><span class="sxs-lookup"><span data-stu-id="ed553-183">The cause can be a combination of those individual causes.</span></span> <span data-ttu-id="ed553-184">ENTER_VS_FORCEORCONVERGENCE は、テストの目的でのみ、レジストリキーを使用して有効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="ed553-184">ENTER_VS_FORCEORCONVERGENCE can only be enabled by regkey for test purpose.</span></span></p>
<p><span data-ttu-id="ed553-185">この列のデータ型は、Microsoft Lync Server 2013 で変更されました。</span><span class="sxs-lookup"><span data-stu-id="ed553-185">The data type for this column was changed in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ed553-186"><strong>EchoEventCauses</strong></span><span class="sxs-lookup"><span data-stu-id="ed553-186"><strong>EchoEventCauses</strong></span></span></p></td>
<td><p><span data-ttu-id="ed553-187">tinyint</span><span class="sxs-lookup"><span data-stu-id="ed553-187">tinyint</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="ed553-188">Echo イベントの原因:</span><span class="sxs-lookup"><span data-stu-id="ed553-188">Causes of an echo event:</span></span></p>
<p><span data-ttu-id="ed553-189">ECHO_EVENT_BAD_TIMESTAMP 0x01</span><span class="sxs-lookup"><span data-stu-id="ed553-189">ECHO_EVENT_BAD_TIMESTAMP 0x01</span></span></p>
<p><span data-ttu-id="ed553-190">ECHO_EVENT_POSTAEC_ECHO 0x02</span><span class="sxs-lookup"><span data-stu-id="ed553-190">ECHO_EVENT_POSTAEC_ECHO 0x02</span></span></p>
<p><span data-ttu-id="ed553-191">ECHO_EVENT_ANLP 0x04</span><span class="sxs-lookup"><span data-stu-id="ed553-191">ECHO_EVENT_ANLP 0x04</span></span></p>
<p><span data-ttu-id="ed553-192">ECHO_EVENT_DNLP 0x08</span><span class="sxs-lookup"><span data-stu-id="ed553-192">ECHO_EVENT_DNLP 0x08</span></span></p>
<p><span data-ttu-id="ed553-193">ECHO_EVENT_MIC_CLIPPING 0x10</span><span class="sxs-lookup"><span data-stu-id="ed553-193">ECHO_EVENT_MIC_CLIPPING 0x10</span></span></p>
<p><span data-ttu-id="ed553-194">ECHO_EVENT_BAD_STATE 0x20</span><span class="sxs-lookup"><span data-stu-id="ed553-194">ECHO_EVENT_BAD_STATE 0x20</span></span></p>
<p><span data-ttu-id="ed553-195">原因として、個々の原因の組み合わせが考えられます。</span><span class="sxs-lookup"><span data-stu-id="ed553-195">The cause can be a combination of those individual causes.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ed553-196"><strong>EchoPercentMicIn</strong></span><span class="sxs-lookup"><span data-stu-id="ed553-196"><strong>EchoPercentMicIn</strong></span></span></p></td>
<td><p><span data-ttu-id="ed553-197">10進数 (5、2)</span><span class="sxs-lookup"><span data-stu-id="ed553-197">decimal(5,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="ed553-198">マイクキャプチャストリームでエコーが検出された時間の割合。</span><span class="sxs-lookup"><span data-stu-id="ed553-198">Percentage of time when echo was detected in the microphone capture stream.</span></span> <span data-ttu-id="ed553-199">通常、ヘッドホンまたはハンドセットの値は低く、スピーカーフォンまたはスタンドアロンスピーカーでは高です。</span><span class="sxs-lookup"><span data-stu-id="ed553-199">Typically, values are low for headsets or handsets, and higher for speaker phones or stand-alone speakers.</span></span> <span data-ttu-id="ed553-200">オンボード音響エコーキャンセレーションをサポートするデバイスでは、値が大きいと、エコーリークが発生します。</span><span class="sxs-lookup"><span data-stu-id="ed553-200">For devices that support on-board acoustic echo cancellation, high values indicate echo leak.</span></span> <span data-ttu-id="ed553-201">その他のデバイスでは、この指標を使用してデバイスの品質を評価することはできません。</span><span class="sxs-lookup"><span data-stu-id="ed553-201">For other devices, this metric should not be used to evaluate device quality.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ed553-202"><strong>EchoPercentSend</strong></span><span class="sxs-lookup"><span data-stu-id="ed553-202"><strong>EchoPercentSend</strong></span></span></p></td>
<td><p><span data-ttu-id="ed553-203">10進数 (5、2)</span><span class="sxs-lookup"><span data-stu-id="ed553-203">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="ed553-204">送信されたストリームでエコーが検出された時間の割合。</span><span class="sxs-lookup"><span data-stu-id="ed553-204">Percentage of time when echo is detected in sent stream.</span></span> <span data-ttu-id="ed553-205">送信ストリームでの高いエコー率は、エコー リークを示しています。</span><span class="sxs-lookup"><span data-stu-id="ed553-205">High echo percentage in send streams an indication of echo leak.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ed553-206"><strong>RxAGCSignalLevel</strong></span><span class="sxs-lookup"><span data-stu-id="ed553-206"><strong>RxAGCSignalLevel</strong></span></span></p></td>
<td><p><span data-ttu-id="ed553-207">int</span><span class="sxs-lookup"><span data-stu-id="ed553-207">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="ed553-208">ゲートウェイからの仲介サーバーの受信した信号レベル。これは、仲介サーバーにのみ適用されます。</span><span class="sxs-lookup"><span data-stu-id="ed553-208">Received signal level on the Mediation Server from the Gateway; this applies only to the Mediation Server.</span></span> <span data-ttu-id="ed553-209">この測定指標の単位は dBoV です。</span><span class="sxs-lookup"><span data-stu-id="ed553-209">The unit of this metric is dBoV.</span></span> <span data-ttu-id="ed553-210">品質を良くするには、許容範囲は [-30 ~-18] dBoV にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="ed553-210">For good quality, the acceptable range should be [-30 to -18] dBoV.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ed553-211"><strong>RxAGCNoiseLevel</strong></span><span class="sxs-lookup"><span data-stu-id="ed553-211"><strong>RxAGCNoiseLevel</strong></span></span></p></td>
<td><p><span data-ttu-id="ed553-212">int</span><span class="sxs-lookup"><span data-stu-id="ed553-212">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="ed553-213">ゲートウェイからの仲介サーバー上の受信した信号レベル。</span><span class="sxs-lookup"><span data-stu-id="ed553-213">Received signal level on the Mediation Server from the Gateway.</span></span> <span data-ttu-id="ed553-214">この値は、仲介サーバーに対してのみ適用されます。</span><span class="sxs-lookup"><span data-stu-id="ed553-214">This applies only to the Mediation Server.</span></span> <span data-ttu-id="ed553-215">この測定指標の単位は dBoV です。</span><span class="sxs-lookup"><span data-stu-id="ed553-215">The unit of this metric is dBoV.</span></span> <span data-ttu-id="ed553-216">良好な品質として許容される範囲は、-50 dBoV 未満です。</span><span class="sxs-lookup"><span data-stu-id="ed553-216">For good quality, the acceptable range should be less than -50 dBoV.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ed553-217"><strong>RxAvgAGCGain</strong></span><span class="sxs-lookup"><span data-stu-id="ed553-217"><strong>RxAvgAGCGain</strong></span></span></p></td>
<td><p><span data-ttu-id="ed553-218">int</span><span class="sxs-lookup"><span data-stu-id="ed553-218">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="ed553-219">仲介サーバー側での自動ゲイン制御 (AGC)。</span><span class="sxs-lookup"><span data-stu-id="ed553-219">Automatic gain control (AGC) on the Mediation Server side.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ed553-220"><strong>InitialSignalLevelRMS</strong></span><span class="sxs-lookup"><span data-stu-id="ed553-220"><strong>InitialSignalLevelRMS</strong></span></span></p></td>
<td><p><span data-ttu-id="ed553-221">浮動小数点数</span><span class="sxs-lookup"><span data-stu-id="ed553-221">float</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="ed553-222">通話の最初の最大30秒間の着信信号のルート平均二乗 (RMS)。</span><span class="sxs-lookup"><span data-stu-id="ed553-222">The root mean square (RMS) of the incoming signal of up to the first 30 seconds of the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ed553-223"><strong>RecvSignalLevelCh1</strong></span><span class="sxs-lookup"><span data-stu-id="ed553-223"><strong>RecvSignalLevelCh1</strong></span></span></p></td>
<td><p><span data-ttu-id="ed553-224">int</span><span class="sxs-lookup"><span data-stu-id="ed553-224">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="ed553-225">チャネル1で受信したシグナルレベル。</span><span class="sxs-lookup"><span data-stu-id="ed553-225">Signal level as received on channel 1.</span></span></p>
<p><span data-ttu-id="ed553-226">このコラムは、Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="ed553-226">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ed553-227"><strong>RecvSignalLevelCh2</strong></span><span class="sxs-lookup"><span data-stu-id="ed553-227"><strong>RecvSignalLevelCh2</strong></span></span></p></td>
<td><p><span data-ttu-id="ed553-228">int</span><span class="sxs-lookup"><span data-stu-id="ed553-228">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="ed553-229">チャネル2で受信したシグナルレベル。</span><span class="sxs-lookup"><span data-stu-id="ed553-229">Signal level as received on channel 2.</span></span></p>
<p><span data-ttu-id="ed553-230">このコラムは、Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="ed553-230">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ed553-231"><strong>RecvNoiseLevelCh1</strong></span><span class="sxs-lookup"><span data-stu-id="ed553-231"><strong>RecvNoiseLevelCh1</strong></span></span></p></td>
<td><p><span data-ttu-id="ed553-232">int</span><span class="sxs-lookup"><span data-stu-id="ed553-232">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="ed553-233">チャネル1で受信したノイズレベル。</span><span class="sxs-lookup"><span data-stu-id="ed553-233">Noise level as received on channel 1.</span></span></p>
<p><span data-ttu-id="ed553-234">このコラムは、Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="ed553-234">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ed553-235"><strong>RecvNoiseLevelCh2</strong></span><span class="sxs-lookup"><span data-stu-id="ed553-235"><strong>RecvNoiseLevelCh2</strong></span></span></p></td>
<td><p><span data-ttu-id="ed553-236">int</span><span class="sxs-lookup"><span data-stu-id="ed553-236">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="ed553-237">チャネル2で受信したノイズレベル。</span><span class="sxs-lookup"><span data-stu-id="ed553-237">Noise level as received on channel 2.</span></span></p>
<p><span data-ttu-id="ed553-238">このコラムは、Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="ed553-238">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ed553-239"><strong>SendSignalLevelCh1</strong></span><span class="sxs-lookup"><span data-stu-id="ed553-239"><strong>SendSignalLevelCh1</strong></span></span></p></td>
<td><p><span data-ttu-id="ed553-240">int</span><span class="sxs-lookup"><span data-stu-id="ed553-240">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="ed553-241">チャネル1で送信されたシグナルレベル。</span><span class="sxs-lookup"><span data-stu-id="ed553-241">Signal level as sent on channel 1.</span></span></p>
<p><span data-ttu-id="ed553-242">このコラムは、Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="ed553-242">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ed553-243"><strong>SendSignalLevelCh2</strong></span><span class="sxs-lookup"><span data-stu-id="ed553-243"><strong>SendSignalLevelCh2</strong></span></span></p></td>
<td><p><span data-ttu-id="ed553-244">int</span><span class="sxs-lookup"><span data-stu-id="ed553-244">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="ed553-245">チャネル2で送信されたシグナルレベル。</span><span class="sxs-lookup"><span data-stu-id="ed553-245">Signal level as sent on channel 2.</span></span></p>
<p><span data-ttu-id="ed553-246">このコラムは、Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="ed553-246">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ed553-247"><strong>SendNoiseLevelCh1</strong></span><span class="sxs-lookup"><span data-stu-id="ed553-247"><strong>SendNoiseLevelCh1</strong></span></span></p></td>
<td><p><span data-ttu-id="ed553-248">int</span><span class="sxs-lookup"><span data-stu-id="ed553-248">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="ed553-249">チャネル1で送信されたノイズレベル。</span><span class="sxs-lookup"><span data-stu-id="ed553-249">Noise level as sent on channel 1.</span></span></p>
<p><span data-ttu-id="ed553-250">このコラムは、Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="ed553-250">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ed553-251"><strong>SendNoiseLevelCh2</strong></span><span class="sxs-lookup"><span data-stu-id="ed553-251"><strong>SendNoiseLevelCh2</strong></span></span></p></td>
<td><p><span data-ttu-id="ed553-252">int</span><span class="sxs-lookup"><span data-stu-id="ed553-252">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="ed553-253">チャネル2で送信されたノイズレベル。</span><span class="sxs-lookup"><span data-stu-id="ed553-253">Noise level as sent on channel 2.</span></span></p>
<p><span data-ttu-id="ed553-254">このコラムは、Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="ed553-254">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

