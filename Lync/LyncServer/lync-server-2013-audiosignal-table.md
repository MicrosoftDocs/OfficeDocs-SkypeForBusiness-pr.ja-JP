---
title: 'Lync Server 2013: AudioSignal テーブル'
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
ms.openlocfilehash: 2d09842cb8b905798855cef7e015e4d9b32e72dd
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/19/2020
ms.locfileid: "42149136"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="audiosignal-table-in-lync-server-2013"></a><span data-ttu-id="e4f53-102">Lync Server 2013 の AudioSignal テーブル</span><span class="sxs-lookup"><span data-stu-id="e4f53-102">AudioSignal table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e4f53-103">_**トピックの最終更新日:** 2013-11-12_</span><span class="sxs-lookup"><span data-stu-id="e4f53-103">_**Topic Last Modified:** 2013-11-12_</span></span>

<span data-ttu-id="e4f53-104">各レコードは、1つのエンドポイントの音声信号指標を表します。</span><span class="sxs-lookup"><span data-stu-id="e4f53-104">Each record represents audio signal metrics for one endpoint.</span></span> <span data-ttu-id="e4f53-105">通常、それぞれの呼び出しには2つのレコードがあります。1つは発信者用、もう1つは呼び出し先用です。</span><span class="sxs-lookup"><span data-stu-id="e4f53-105">Usually, each call has two records, one is for caller, and one is for callee.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="e4f53-106"><strong>列</strong></span><span class="sxs-lookup"><span data-stu-id="e4f53-106"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="e4f53-107"><strong>データ型</strong></span><span class="sxs-lookup"><span data-stu-id="e4f53-107"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="e4f53-108"><strong>キー/インデックス</strong></span><span class="sxs-lookup"><span data-stu-id="e4f53-108"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="e4f53-109"><strong>詳細</strong></span><span class="sxs-lookup"><span data-stu-id="e4f53-109"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e4f53-110"><strong>ConferenceDateTime</strong></span><span class="sxs-lookup"><span data-stu-id="e4f53-110"><strong>ConferenceDateTime</strong></span></span></p></td>
<td><p><span data-ttu-id="e4f53-111">日付型</span><span class="sxs-lookup"><span data-stu-id="e4f53-111">datetime</span></span></p></td>
<td><p><span data-ttu-id="e4f53-112">Primary</span><span class="sxs-lookup"><span data-stu-id="e4f53-112">Primary</span></span></p></td>
<td><p><span data-ttu-id="e4f53-113"><a href="lync-server-2013-medialine-table.md">Lync Server 2013 の MediaLine テーブル</a>から参照されます。</span><span class="sxs-lookup"><span data-stu-id="e4f53-113">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e4f53-114"><strong>SessionSeq</strong></span><span class="sxs-lookup"><span data-stu-id="e4f53-114"><strong>SessionSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="e4f53-115">int</span><span class="sxs-lookup"><span data-stu-id="e4f53-115">int</span></span></p></td>
<td><p><span data-ttu-id="e4f53-116">Primary</span><span class="sxs-lookup"><span data-stu-id="e4f53-116">Primary</span></span></p></td>
<td><p><span data-ttu-id="e4f53-117"><a href="lync-server-2013-medialine-table.md">Lync Server 2013 の MediaLine テーブル</a>から参照されます。</span><span class="sxs-lookup"><span data-stu-id="e4f53-117">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e4f53-118"><strong>MediaLineLabel</strong></span><span class="sxs-lookup"><span data-stu-id="e4f53-118"><strong>MediaLineLabel</strong></span></span></p></td>
<td><p><span data-ttu-id="e4f53-119">tinyint</span><span class="sxs-lookup"><span data-stu-id="e4f53-119">tinyint</span></span></p></td>
<td><p><span data-ttu-id="e4f53-120">Primary</span><span class="sxs-lookup"><span data-stu-id="e4f53-120">Primary</span></span></p></td>
<td><p><span data-ttu-id="e4f53-121"><a href="lync-server-2013-medialine-table.md">Lync Server 2013 の MediaLine テーブル</a>から参照されます。</span><span class="sxs-lookup"><span data-stu-id="e4f53-121">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e4f53-122"><strong>FromCaller</strong></span><span class="sxs-lookup"><span data-stu-id="e4f53-122"><strong>FromCaller</strong></span></span></p></td>
<td><p><span data-ttu-id="e4f53-123">若干</span><span class="sxs-lookup"><span data-stu-id="e4f53-123">bit</span></span></p></td>
<td><p><span data-ttu-id="e4f53-124">Primary</span><span class="sxs-lookup"><span data-stu-id="e4f53-124">Primary</span></span></p></td>
<td><p><span data-ttu-id="e4f53-125">0: 呼び出し先のデータ</span><span class="sxs-lookup"><span data-stu-id="e4f53-125">0: Callee’s data</span></span></p>
<p><span data-ttu-id="e4f53-126">1: 発信者のデータ</span><span class="sxs-lookup"><span data-stu-id="e4f53-126">1: Caller’s data</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e4f53-127"><strong>SendSignalLevel</strong></span><span class="sxs-lookup"><span data-stu-id="e4f53-127"><strong>SendSignalLevel</strong></span></span></p></td>
<td><p><span data-ttu-id="e4f53-128">int</span><span class="sxs-lookup"><span data-stu-id="e4f53-128">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="e4f53-129">アナログのゲイン制御音声信号レベルを表します。</span><span class="sxs-lookup"><span data-stu-id="e4f53-129">Represents the Post-Analog Gain Control audio signal level.</span></span> <span data-ttu-id="e4f53-130">この測定指標の単位は dBmo です。</span><span class="sxs-lookup"><span data-stu-id="e4f53-130">The unit for this metric is dBmo.</span></span> <span data-ttu-id="e4f53-131">許容される品質は 30 dBmo 以上です。</span><span class="sxs-lookup"><span data-stu-id="e4f53-131">For acceptable quality, it should be at least 30 dBmo.</span></span> <span data-ttu-id="e4f53-132">この測定指標は、音声ビデオ会議サーバーまたは IP 電話では報告されません。</span><span class="sxs-lookup"><span data-stu-id="e4f53-132">This metric is not reported by the A/V Conferencing Server or IP phones.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e4f53-133"><strong>RecvSignalLevel</strong></span><span class="sxs-lookup"><span data-stu-id="e4f53-133"><strong>RecvSignalLevel</strong></span></span></p></td>
<td><p><span data-ttu-id="e4f53-134">int</span><span class="sxs-lookup"><span data-stu-id="e4f53-134">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="e4f53-135">SendSignalLevel を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e4f53-135">See SendSignalLevel.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e4f53-136"><strong>SendNoiseLevel</strong></span><span class="sxs-lookup"><span data-stu-id="e4f53-136"><strong>SendNoiseLevel</strong></span></span></p></td>
<td><p><span data-ttu-id="e4f53-137">int</span><span class="sxs-lookup"><span data-stu-id="e4f53-137">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="e4f53-138">アナログのゲインコントロールのオーディオノイズレベルを表します。</span><span class="sxs-lookup"><span data-stu-id="e4f53-138">Represents the Post-Analog Gain Control audio noise level.</span></span> <span data-ttu-id="e4f53-139">この測定指標の単位は dBmo です。</span><span class="sxs-lookup"><span data-stu-id="e4f53-139">The unit for this metric is dBmo.</span></span> <span data-ttu-id="e4f53-140">許容される品質は 35 dBmo 未満です。</span><span class="sxs-lookup"><span data-stu-id="e4f53-140">For acceptable quality, it should be less than 35 dBmo.</span></span> <span data-ttu-id="e4f53-141">この測定指標は、音声ビデオ会議サーバーまたは IP 電話では報告されません。</span><span class="sxs-lookup"><span data-stu-id="e4f53-141">This metric is not reported by the A/V Conferencing Server or IP phones.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e4f53-142"><strong>RecvNoiseLevel</strong></span><span class="sxs-lookup"><span data-stu-id="e4f53-142"><strong>RecvNoiseLevel</strong></span></span></p></td>
<td><p><span data-ttu-id="e4f53-143">int</span><span class="sxs-lookup"><span data-stu-id="e4f53-143">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="e4f53-144">SendNoiseLevel を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e4f53-144">See SendNoiseLevel.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e4f53-145"><strong>EchoReturn</strong></span><span class="sxs-lookup"><span data-stu-id="e4f53-145"><strong>EchoReturn</strong></span></span></p></td>
<td><p><span data-ttu-id="e4f53-146">int</span><span class="sxs-lookup"><span data-stu-id="e4f53-146">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="e4f53-147">エコーリターン損失の拡張指標。</span><span class="sxs-lookup"><span data-stu-id="e4f53-147">Echo Return Loss Enhancement metric.</span></span> <span data-ttu-id="e4f53-148">この測定指標の単位は dB です。</span><span class="sxs-lookup"><span data-stu-id="e4f53-148">The unit for this metric is dB.</span></span> <span data-ttu-id="e4f53-149">値が小さいほど、エコーが少ないことを示します。</span><span class="sxs-lookup"><span data-stu-id="e4f53-149">Lower values represent less echo.</span></span> <span data-ttu-id="e4f53-150">この測定指標は、音声ビデオ会議サーバーまたは IP 電話では報告されません。</span><span class="sxs-lookup"><span data-stu-id="e4f53-150">This metric is not reported by the A/V Conferencing Server or IP phones.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e4f53-151"><strong>AudioSpeakerGlitchRate</strong></span><span class="sxs-lookup"><span data-stu-id="e4f53-151"><strong>AudioSpeakerGlitchRate</strong></span></span></p></td>
<td><p><span data-ttu-id="e4f53-152">int</span><span class="sxs-lookup"><span data-stu-id="e4f53-152">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="e4f53-153">Loudspeaker レンダリングの5分あたりの平均の異常。</span><span class="sxs-lookup"><span data-stu-id="e4f53-153">Average glitches per five minutes for the loudspeaker rendering.</span></span> <span data-ttu-id="e4f53-154">良好な品質といえるのは、5 分間に 1 回未満です。</span><span class="sxs-lookup"><span data-stu-id="e4f53-154">For good quality, this should be less than one per five minutes.</span></span> <span data-ttu-id="e4f53-155">音声ビデオ会議サーバー、仲介サーバー、または IP 電話では報告されません。</span><span class="sxs-lookup"><span data-stu-id="e4f53-155">Not reported by A/V Conferencing Servers, Mediation Servers, or IP phones.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e4f53-156"><strong>AudioMicGlitchRate</strong></span><span class="sxs-lookup"><span data-stu-id="e4f53-156"><strong>AudioMicGlitchRate</strong></span></span></p></td>
<td><p><span data-ttu-id="e4f53-157">int</span><span class="sxs-lookup"><span data-stu-id="e4f53-157">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="e4f53-158">マイクキャプチャに対する5分あたりの平均の異常。</span><span class="sxs-lookup"><span data-stu-id="e4f53-158">Average glitches per five minutes for the microphone capture.</span></span> <span data-ttu-id="e4f53-159">良好な品質といえるのは、5 分間に 1 回未満です。</span><span class="sxs-lookup"><span data-stu-id="e4f53-159">For good quality this should be less than one per five minutes.</span></span> <span data-ttu-id="e4f53-160">音声ビデオ会議サーバー、仲介サーバー、または IP 電話では報告されません。</span><span class="sxs-lookup"><span data-stu-id="e4f53-160">Not reported by A/V Conferencing Servers, Mediation Servers, or IP phones.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e4f53-161"><strong>AudioTimestampDriftRateMic</strong></span><span class="sxs-lookup"><span data-stu-id="e4f53-161"><strong>AudioTimestampDriftRateMic</strong></span></span></p></td>
<td><p><span data-ttu-id="e4f53-162">10進数 (9、2)</span><span class="sxs-lookup"><span data-stu-id="e4f53-162">decimal(9,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="e4f53-163">CPU クロックに対するマイクデバイスのクロック誤差の割合です。</span><span class="sxs-lookup"><span data-stu-id="e4f53-163">Microphone device clock drift rate, relative to CPU clock.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e4f53-164"><strong>AudioTimestampDriftRateSpk</strong></span><span class="sxs-lookup"><span data-stu-id="e4f53-164"><strong>AudioTimestampDriftRateSpk</strong></span></span></p></td>
<td><p><span data-ttu-id="e4f53-165">10進数 (9、2)</span><span class="sxs-lookup"><span data-stu-id="e4f53-165">decimal(9,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="e4f53-166">CPU クロックに対するスピーカーデバイスのクロック誤差の割合。</span><span class="sxs-lookup"><span data-stu-id="e4f53-166">Speaker device clock drift rate, relative to CPU clock.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e4f53-167"><strong>AudioTimestampErrorMicMs</strong></span><span class="sxs-lookup"><span data-stu-id="e4f53-167"><strong>AudioTimestampErrorMicMs</strong></span></span></p></td>
<td><p><span data-ttu-id="e4f53-168">10進数 (9、2)</span><span class="sxs-lookup"><span data-stu-id="e4f53-168">decimal(9,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="e4f53-169">CPU クロックに対するスピーカーデバイスのクロック誤差の割合。</span><span class="sxs-lookup"><span data-stu-id="e4f53-169">Speaker device clock drift rate, relative to CPU clock.</span></span></p>
<p><span data-ttu-id="e4f53-170">過去 20 秒間の通話での平均マイク キャプチャ ストリーム タイム スタンプ エラーです (ミリ秒単位)。</span><span class="sxs-lookup"><span data-stu-id="e4f53-170">Average microphone capture stream time stamp error, in milliseconds, in the last 20 seconds of the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e4f53-171"><strong>AudioTimestampErrorSpkMs</strong></span><span class="sxs-lookup"><span data-stu-id="e4f53-171"><strong>AudioTimestampErrorSpkMs</strong></span></span></p></td>
<td><p><span data-ttu-id="e4f53-172">10進数 (9、2)</span><span class="sxs-lookup"><span data-stu-id="e4f53-172">decimal(9,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="e4f53-173">過去20秒間の通話の平均スピーカーレンダーストリームタイムスタンプエラー (ミリ秒単位)。</span><span class="sxs-lookup"><span data-stu-id="e4f53-173">Average speaker render stream time stamp error, in milliseconds, in the last 20 seconds of the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e4f53-174"><strong>VsEntryCauses</strong></span><span class="sxs-lookup"><span data-stu-id="e4f53-174"><strong>VsEntryCauses</strong></span></span></p></td>
<td><p><span data-ttu-id="e4f53-175">smallint</span><span class="sxs-lookup"><span data-stu-id="e4f53-175">smallint</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="e4f53-176">音声スイッチは、遮断能力が低下した半二重モードです。</span><span class="sxs-lookup"><span data-stu-id="e4f53-176">Voice switch is a half-duplex mode with reduced interruption ability.</span></span> <span data-ttu-id="e4f53-177">音声スイッチエントリの原因:</span><span class="sxs-lookup"><span data-stu-id="e4f53-177">Causes of voice switch entry:</span></span></p>
<p><span data-ttu-id="e4f53-178">ENTER_VS_BADTS 0x01</span><span class="sxs-lookup"><span data-stu-id="e4f53-178">ENTER_VS_BADTS 0x01</span></span></p>
<p><span data-ttu-id="e4f53-179">ENTER_VS_ECHO 0x02</span><span class="sxs-lookup"><span data-stu-id="e4f53-179">ENTER_VS_ECHO 0x02</span></span></p>
<p><span data-ttu-id="e4f53-180">ENTER_VS_FORCEORCONVERGENCE 0x04</span><span class="sxs-lookup"><span data-stu-id="e4f53-180">ENTER_VS_FORCEORCONVERGENCE 0x04</span></span></p>
<p><span data-ttu-id="e4f53-181">ENTER_VS_DNLP 0x08</span><span class="sxs-lookup"><span data-stu-id="e4f53-181">ENTER_VS_DNLP 0x08</span></span></p>
<p><span data-ttu-id="e4f53-182">原因として、個々の原因の組み合わせが考えられます。</span><span class="sxs-lookup"><span data-stu-id="e4f53-182">The cause can be a combination of those individual causes.</span></span> <span data-ttu-id="e4f53-183">ENTER_VS_FORCEORCONVERGENCE は、テストの目的でのみ、レジストリキーを使用して有効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="e4f53-183">ENTER_VS_FORCEORCONVERGENCE can only be enabled by regkey for test purpose.</span></span></p>
<p><span data-ttu-id="e4f53-184">この列のデータ型は、Microsoft Lync Server 2013 で変更されました。</span><span class="sxs-lookup"><span data-stu-id="e4f53-184">The data type for this column was changed in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e4f53-185"><strong>EchoEventCauses</strong></span><span class="sxs-lookup"><span data-stu-id="e4f53-185"><strong>EchoEventCauses</strong></span></span></p></td>
<td><p><span data-ttu-id="e4f53-186">tinyint</span><span class="sxs-lookup"><span data-stu-id="e4f53-186">tinyint</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="e4f53-187">Echo イベントの原因:</span><span class="sxs-lookup"><span data-stu-id="e4f53-187">Causes of an echo event:</span></span></p>
<p><span data-ttu-id="e4f53-188">ECHO_EVENT_BAD_TIMESTAMP 0x01</span><span class="sxs-lookup"><span data-stu-id="e4f53-188">ECHO_EVENT_BAD_TIMESTAMP 0x01</span></span></p>
<p><span data-ttu-id="e4f53-189">ECHO_EVENT_POSTAEC_ECHO 0x02</span><span class="sxs-lookup"><span data-stu-id="e4f53-189">ECHO_EVENT_POSTAEC_ECHO 0x02</span></span></p>
<p><span data-ttu-id="e4f53-190">ECHO_EVENT_ANLP 0x04</span><span class="sxs-lookup"><span data-stu-id="e4f53-190">ECHO_EVENT_ANLP 0x04</span></span></p>
<p><span data-ttu-id="e4f53-191">ECHO_EVENT_DNLP 0x08</span><span class="sxs-lookup"><span data-stu-id="e4f53-191">ECHO_EVENT_DNLP 0x08</span></span></p>
<p><span data-ttu-id="e4f53-192">ECHO_EVENT_MIC_CLIPPING 0x10</span><span class="sxs-lookup"><span data-stu-id="e4f53-192">ECHO_EVENT_MIC_CLIPPING 0x10</span></span></p>
<p><span data-ttu-id="e4f53-193">ECHO_EVENT_BAD_STATE 0x20</span><span class="sxs-lookup"><span data-stu-id="e4f53-193">ECHO_EVENT_BAD_STATE 0x20</span></span></p>
<p><span data-ttu-id="e4f53-194">原因として、個々の原因の組み合わせが考えられます。</span><span class="sxs-lookup"><span data-stu-id="e4f53-194">The cause can be a combination of those individual causes.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e4f53-195"><strong>EchoPercentMicIn</strong></span><span class="sxs-lookup"><span data-stu-id="e4f53-195"><strong>EchoPercentMicIn</strong></span></span></p></td>
<td><p><span data-ttu-id="e4f53-196">10進数 (5、2)</span><span class="sxs-lookup"><span data-stu-id="e4f53-196">decimal(5,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="e4f53-197">マイクキャプチャストリームでエコーが検出された時間の割合。</span><span class="sxs-lookup"><span data-stu-id="e4f53-197">Percentage of time when echo was detected in the microphone capture stream.</span></span> <span data-ttu-id="e4f53-198">通常、ヘッドホンまたはハンドセットの値は低く、スピーカーフォンまたはスタンドアロンスピーカーでは高です。</span><span class="sxs-lookup"><span data-stu-id="e4f53-198">Typically, values are low for headsets or handsets, and higher for speaker phones or stand-alone speakers.</span></span> <span data-ttu-id="e4f53-199">オンボード音響エコーキャンセレーションをサポートするデバイスでは、値が大きいと、エコーリークが発生します。</span><span class="sxs-lookup"><span data-stu-id="e4f53-199">For devices that support on-board acoustic echo cancellation, high values indicate echo leak.</span></span> <span data-ttu-id="e4f53-200">その他のデバイスでは、この指標を使用してデバイスの品質を評価することはできません。</span><span class="sxs-lookup"><span data-stu-id="e4f53-200">For other devices, this metric should not be used to evaluate device quality.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e4f53-201"><strong>EchoPercentSend</strong></span><span class="sxs-lookup"><span data-stu-id="e4f53-201"><strong>EchoPercentSend</strong></span></span></p></td>
<td><p><span data-ttu-id="e4f53-202">10進数 (5、2)</span><span class="sxs-lookup"><span data-stu-id="e4f53-202">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e4f53-203">送信されたストリームでエコーが検出された時間の割合。</span><span class="sxs-lookup"><span data-stu-id="e4f53-203">Percentage of time when echo is detected in sent stream.</span></span> <span data-ttu-id="e4f53-204">送信ストリームでの高いエコー率は、エコー リークを示しています。</span><span class="sxs-lookup"><span data-stu-id="e4f53-204">High echo percentage in send streams an indication of echo leak.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e4f53-205"><strong>RxAGCSignalLevel</strong></span><span class="sxs-lookup"><span data-stu-id="e4f53-205"><strong>RxAGCSignalLevel</strong></span></span></p></td>
<td><p><span data-ttu-id="e4f53-206">int</span><span class="sxs-lookup"><span data-stu-id="e4f53-206">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="e4f53-207">ゲートウェイからの仲介サーバーの受信した信号レベル。これは、仲介サーバーにのみ適用されます。</span><span class="sxs-lookup"><span data-stu-id="e4f53-207">Received signal level on the Mediation Server from the Gateway; this applies only to the Mediation Server.</span></span> <span data-ttu-id="e4f53-208">この測定指標の単位は dBoV です。</span><span class="sxs-lookup"><span data-stu-id="e4f53-208">The unit of this metric is dBoV.</span></span> <span data-ttu-id="e4f53-209">品質を良くするには、許容範囲は [-30 ~-18] dBoV にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="e4f53-209">For good quality, the acceptable range should be [-30 to -18] dBoV.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e4f53-210"><strong>RxAGCNoiseLevel</strong></span><span class="sxs-lookup"><span data-stu-id="e4f53-210"><strong>RxAGCNoiseLevel</strong></span></span></p></td>
<td><p><span data-ttu-id="e4f53-211">int</span><span class="sxs-lookup"><span data-stu-id="e4f53-211">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="e4f53-212">ゲートウェイからの仲介サーバー上の受信した信号レベル。</span><span class="sxs-lookup"><span data-stu-id="e4f53-212">Received signal level on the Mediation Server from the Gateway.</span></span> <span data-ttu-id="e4f53-213">この値は、仲介サーバーに対してのみ適用されます。</span><span class="sxs-lookup"><span data-stu-id="e4f53-213">This applies only to the Mediation Server.</span></span> <span data-ttu-id="e4f53-214">この測定指標の単位は dBoV です。</span><span class="sxs-lookup"><span data-stu-id="e4f53-214">The unit of this metric is dBoV.</span></span> <span data-ttu-id="e4f53-215">良好な品質として許容される範囲は、-50 dBoV 未満です。</span><span class="sxs-lookup"><span data-stu-id="e4f53-215">For good quality, the acceptable range should be less than -50 dBoV.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e4f53-216"><strong>RxAvgAGCGain</strong></span><span class="sxs-lookup"><span data-stu-id="e4f53-216"><strong>RxAvgAGCGain</strong></span></span></p></td>
<td><p><span data-ttu-id="e4f53-217">int</span><span class="sxs-lookup"><span data-stu-id="e4f53-217">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="e4f53-218">仲介サーバー側での自動ゲイン制御 (AGC)。</span><span class="sxs-lookup"><span data-stu-id="e4f53-218">Automatic gain control (AGC) on the Mediation Server side.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e4f53-219"><strong>InitialSignalLevelRMS</strong></span><span class="sxs-lookup"><span data-stu-id="e4f53-219"><strong>InitialSignalLevelRMS</strong></span></span></p></td>
<td><p><span data-ttu-id="e4f53-220">浮動小数点数</span><span class="sxs-lookup"><span data-stu-id="e4f53-220">float</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="e4f53-221">通話の最初の最大30秒間の着信信号のルート平均二乗 (RMS)。</span><span class="sxs-lookup"><span data-stu-id="e4f53-221">The root mean square (RMS) of the incoming signal of up to the first 30 seconds of the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e4f53-222"><strong>RecvSignalLevelCh1</strong></span><span class="sxs-lookup"><span data-stu-id="e4f53-222"><strong>RecvSignalLevelCh1</strong></span></span></p></td>
<td><p><span data-ttu-id="e4f53-223">int</span><span class="sxs-lookup"><span data-stu-id="e4f53-223">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e4f53-224">チャネル1で受信したシグナルレベル。</span><span class="sxs-lookup"><span data-stu-id="e4f53-224">Signal level as received on channel 1.</span></span></p>
<p><span data-ttu-id="e4f53-225">このコラムは、Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="e4f53-225">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e4f53-226"><strong>RecvSignalLevelCh2</strong></span><span class="sxs-lookup"><span data-stu-id="e4f53-226"><strong>RecvSignalLevelCh2</strong></span></span></p></td>
<td><p><span data-ttu-id="e4f53-227">int</span><span class="sxs-lookup"><span data-stu-id="e4f53-227">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e4f53-228">チャネル2で受信したシグナルレベル。</span><span class="sxs-lookup"><span data-stu-id="e4f53-228">Signal level as received on channel 2.</span></span></p>
<p><span data-ttu-id="e4f53-229">このコラムは、Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="e4f53-229">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e4f53-230"><strong>RecvNoiseLevelCh1</strong></span><span class="sxs-lookup"><span data-stu-id="e4f53-230"><strong>RecvNoiseLevelCh1</strong></span></span></p></td>
<td><p><span data-ttu-id="e4f53-231">int</span><span class="sxs-lookup"><span data-stu-id="e4f53-231">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e4f53-232">チャネル1で受信したノイズレベル。</span><span class="sxs-lookup"><span data-stu-id="e4f53-232">Noise level as received on channel 1.</span></span></p>
<p><span data-ttu-id="e4f53-233">このコラムは、Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="e4f53-233">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e4f53-234"><strong>RecvNoiseLevelCh2</strong></span><span class="sxs-lookup"><span data-stu-id="e4f53-234"><strong>RecvNoiseLevelCh2</strong></span></span></p></td>
<td><p><span data-ttu-id="e4f53-235">int</span><span class="sxs-lookup"><span data-stu-id="e4f53-235">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e4f53-236">チャネル2で受信したノイズレベル。</span><span class="sxs-lookup"><span data-stu-id="e4f53-236">Noise level as received on channel 2.</span></span></p>
<p><span data-ttu-id="e4f53-237">このコラムは、Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="e4f53-237">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e4f53-238"><strong>SendSignalLevelCh1</strong></span><span class="sxs-lookup"><span data-stu-id="e4f53-238"><strong>SendSignalLevelCh1</strong></span></span></p></td>
<td><p><span data-ttu-id="e4f53-239">int</span><span class="sxs-lookup"><span data-stu-id="e4f53-239">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e4f53-240">チャネル1で送信されたシグナルレベル。</span><span class="sxs-lookup"><span data-stu-id="e4f53-240">Signal level as sent on channel 1.</span></span></p>
<p><span data-ttu-id="e4f53-241">このコラムは、Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="e4f53-241">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e4f53-242"><strong>SendSignalLevelCh2</strong></span><span class="sxs-lookup"><span data-stu-id="e4f53-242"><strong>SendSignalLevelCh2</strong></span></span></p></td>
<td><p><span data-ttu-id="e4f53-243">int</span><span class="sxs-lookup"><span data-stu-id="e4f53-243">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e4f53-244">チャネル2で送信されたシグナルレベル。</span><span class="sxs-lookup"><span data-stu-id="e4f53-244">Signal level as sent on channel 2.</span></span></p>
<p><span data-ttu-id="e4f53-245">このコラムは、Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="e4f53-245">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e4f53-246"><strong>SendNoiseLevelCh1</strong></span><span class="sxs-lookup"><span data-stu-id="e4f53-246"><strong>SendNoiseLevelCh1</strong></span></span></p></td>
<td><p><span data-ttu-id="e4f53-247">int</span><span class="sxs-lookup"><span data-stu-id="e4f53-247">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e4f53-248">チャネル1で送信されたノイズレベル。</span><span class="sxs-lookup"><span data-stu-id="e4f53-248">Noise level as sent on channel 1.</span></span></p>
<p><span data-ttu-id="e4f53-249">このコラムは、Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="e4f53-249">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e4f53-250"><strong>SendNoiseLevelCh2</strong></span><span class="sxs-lookup"><span data-stu-id="e4f53-250"><strong>SendNoiseLevelCh2</strong></span></span></p></td>
<td><p><span data-ttu-id="e4f53-251">int</span><span class="sxs-lookup"><span data-stu-id="e4f53-251">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e4f53-252">チャネル2で送信されたノイズレベル。</span><span class="sxs-lookup"><span data-stu-id="e4f53-252">Noise level as sent on channel 2.</span></span></p>
<p><span data-ttu-id="e4f53-253">このコラムは、Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="e4f53-253">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

