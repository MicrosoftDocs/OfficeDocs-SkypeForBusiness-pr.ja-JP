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
ms.openlocfilehash: 9d7dcf9337dceded96679411e575abc888164618
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2020
ms.locfileid: "42044589"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="audiosignal-table-in-lync-server-2013"></a><span data-ttu-id="5a8d8-102">Lync Server 2013 の AudioSignal テーブル</span><span class="sxs-lookup"><span data-stu-id="5a8d8-102">AudioSignal table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5a8d8-103">_**トピックの最終更新日:** 2013-11-12_</span><span class="sxs-lookup"><span data-stu-id="5a8d8-103">_**Topic Last Modified:** 2013-11-12_</span></span>

<span data-ttu-id="5a8d8-104">各レコードは、1つのエンドポイントの音声信号指標を表します。</span><span class="sxs-lookup"><span data-stu-id="5a8d8-104">Each record represents audio signal metrics for one endpoint.</span></span> <span data-ttu-id="5a8d8-105">通常、それぞれの呼び出しには2つのレコードがあります。1つは発信者用、もう1つは呼び出し先用です。</span><span class="sxs-lookup"><span data-stu-id="5a8d8-105">Usually, each call has two records, one is for caller, and one is for callee.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="5a8d8-106"><strong>列</strong></span><span class="sxs-lookup"><span data-stu-id="5a8d8-106"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="5a8d8-107"><strong>データ型</strong></span><span class="sxs-lookup"><span data-stu-id="5a8d8-107"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="5a8d8-108"><strong>キー/インデックス</strong></span><span class="sxs-lookup"><span data-stu-id="5a8d8-108"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="5a8d8-109"><strong>詳細</strong></span><span class="sxs-lookup"><span data-stu-id="5a8d8-109"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="5a8d8-110"><strong>ConferenceDateTime</strong></span><span class="sxs-lookup"><span data-stu-id="5a8d8-110"><strong>ConferenceDateTime</strong></span></span></p></td>
<td><p><span data-ttu-id="5a8d8-111">日付型</span><span class="sxs-lookup"><span data-stu-id="5a8d8-111">datetime</span></span></p></td>
<td><p><span data-ttu-id="5a8d8-112">Primary</span><span class="sxs-lookup"><span data-stu-id="5a8d8-112">Primary</span></span></p></td>
<td><p><span data-ttu-id="5a8d8-113"><a href="lync-server-2013-medialine-table.md">Lync Server 2013 の MediaLine テーブル</a>から参照されます。</span><span class="sxs-lookup"><span data-stu-id="5a8d8-113">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5a8d8-114"><strong>SessionSeq</strong></span><span class="sxs-lookup"><span data-stu-id="5a8d8-114"><strong>SessionSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="5a8d8-115">int</span><span class="sxs-lookup"><span data-stu-id="5a8d8-115">int</span></span></p></td>
<td><p><span data-ttu-id="5a8d8-116">Primary</span><span class="sxs-lookup"><span data-stu-id="5a8d8-116">Primary</span></span></p></td>
<td><p><span data-ttu-id="5a8d8-117"><a href="lync-server-2013-medialine-table.md">Lync Server 2013 の MediaLine テーブル</a>から参照されます。</span><span class="sxs-lookup"><span data-stu-id="5a8d8-117">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5a8d8-118"><strong>MediaLineLabel</strong></span><span class="sxs-lookup"><span data-stu-id="5a8d8-118"><strong>MediaLineLabel</strong></span></span></p></td>
<td><p><span data-ttu-id="5a8d8-119">tinyint</span><span class="sxs-lookup"><span data-stu-id="5a8d8-119">tinyint</span></span></p></td>
<td><p><span data-ttu-id="5a8d8-120">Primary</span><span class="sxs-lookup"><span data-stu-id="5a8d8-120">Primary</span></span></p></td>
<td><p><span data-ttu-id="5a8d8-121"><a href="lync-server-2013-medialine-table.md">Lync Server 2013 の MediaLine テーブル</a>から参照されます。</span><span class="sxs-lookup"><span data-stu-id="5a8d8-121">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5a8d8-122"><strong>FromCaller</strong></span><span class="sxs-lookup"><span data-stu-id="5a8d8-122"><strong>FromCaller</strong></span></span></p></td>
<td><p><span data-ttu-id="5a8d8-123">若干</span><span class="sxs-lookup"><span data-stu-id="5a8d8-123">bit</span></span></p></td>
<td><p><span data-ttu-id="5a8d8-124">Primary</span><span class="sxs-lookup"><span data-stu-id="5a8d8-124">Primary</span></span></p></td>
<td><p><span data-ttu-id="5a8d8-125">0: 呼び出し先のデータ</span><span class="sxs-lookup"><span data-stu-id="5a8d8-125">0: Callee’s data</span></span></p>
<p><span data-ttu-id="5a8d8-126">1: 発信者のデータ</span><span class="sxs-lookup"><span data-stu-id="5a8d8-126">1: Caller’s data</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5a8d8-127"><strong>SendSignalLevel</strong></span><span class="sxs-lookup"><span data-stu-id="5a8d8-127"><strong>SendSignalLevel</strong></span></span></p></td>
<td><p><span data-ttu-id="5a8d8-128">int</span><span class="sxs-lookup"><span data-stu-id="5a8d8-128">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="5a8d8-129">アナログのゲイン制御音声信号レベルを表します。</span><span class="sxs-lookup"><span data-stu-id="5a8d8-129">Represents the Post-Analog Gain Control audio signal level.</span></span> <span data-ttu-id="5a8d8-130">この測定指標の単位は dBmo です。</span><span class="sxs-lookup"><span data-stu-id="5a8d8-130">The unit for this metric is dBmo.</span></span> <span data-ttu-id="5a8d8-131">許容される品質は 30 dBmo 以上です。</span><span class="sxs-lookup"><span data-stu-id="5a8d8-131">For acceptable quality, it should be at least 30 dBmo.</span></span> <span data-ttu-id="5a8d8-132">この測定指標は、音声ビデオ会議サーバーまたは IP 電話では報告されません。</span><span class="sxs-lookup"><span data-stu-id="5a8d8-132">This metric is not reported by the A/V Conferencing Server or IP phones.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5a8d8-133"><strong>RecvSignalLevel</strong></span><span class="sxs-lookup"><span data-stu-id="5a8d8-133"><strong>RecvSignalLevel</strong></span></span></p></td>
<td><p><span data-ttu-id="5a8d8-134">int</span><span class="sxs-lookup"><span data-stu-id="5a8d8-134">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="5a8d8-135">SendSignalLevel を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5a8d8-135">See SendSignalLevel.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5a8d8-136"><strong>SendNoiseLevel</strong></span><span class="sxs-lookup"><span data-stu-id="5a8d8-136"><strong>SendNoiseLevel</strong></span></span></p></td>
<td><p><span data-ttu-id="5a8d8-137">int</span><span class="sxs-lookup"><span data-stu-id="5a8d8-137">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="5a8d8-138">アナログのゲインコントロールのオーディオノイズレベルを表します。</span><span class="sxs-lookup"><span data-stu-id="5a8d8-138">Represents the Post-Analog Gain Control audio noise level.</span></span> <span data-ttu-id="5a8d8-139">この測定指標の単位は dBmo です。</span><span class="sxs-lookup"><span data-stu-id="5a8d8-139">The unit for this metric is dBmo.</span></span> <span data-ttu-id="5a8d8-140">許容される品質は 35 dBmo 未満です。</span><span class="sxs-lookup"><span data-stu-id="5a8d8-140">For acceptable quality, it should be less than 35 dBmo.</span></span> <span data-ttu-id="5a8d8-141">この測定指標は、音声ビデオ会議サーバーまたは IP 電話では報告されません。</span><span class="sxs-lookup"><span data-stu-id="5a8d8-141">This metric is not reported by the A/V Conferencing Server or IP phones.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5a8d8-142"><strong>RecvNoiseLevel</strong></span><span class="sxs-lookup"><span data-stu-id="5a8d8-142"><strong>RecvNoiseLevel</strong></span></span></p></td>
<td><p><span data-ttu-id="5a8d8-143">int</span><span class="sxs-lookup"><span data-stu-id="5a8d8-143">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="5a8d8-144">SendNoiseLevel を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5a8d8-144">See SendNoiseLevel.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5a8d8-145"><strong>EchoReturn</strong></span><span class="sxs-lookup"><span data-stu-id="5a8d8-145"><strong>EchoReturn</strong></span></span></p></td>
<td><p><span data-ttu-id="5a8d8-146">int</span><span class="sxs-lookup"><span data-stu-id="5a8d8-146">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="5a8d8-147">エコーリターン損失の拡張指標。</span><span class="sxs-lookup"><span data-stu-id="5a8d8-147">Echo Return Loss Enhancement metric.</span></span> <span data-ttu-id="5a8d8-148">この測定指標の単位は dB です。</span><span class="sxs-lookup"><span data-stu-id="5a8d8-148">The unit for this metric is dB.</span></span> <span data-ttu-id="5a8d8-149">値が小さいほど、エコーが少ないことを示します。</span><span class="sxs-lookup"><span data-stu-id="5a8d8-149">Lower values represent less echo.</span></span> <span data-ttu-id="5a8d8-150">この測定指標は、音声ビデオ会議サーバーまたは IP 電話では報告されません。</span><span class="sxs-lookup"><span data-stu-id="5a8d8-150">This metric is not reported by the A/V Conferencing Server or IP phones.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5a8d8-151"><strong>AudioSpeakerGlitchRate</strong></span><span class="sxs-lookup"><span data-stu-id="5a8d8-151"><strong>AudioSpeakerGlitchRate</strong></span></span></p></td>
<td><p><span data-ttu-id="5a8d8-152">int</span><span class="sxs-lookup"><span data-stu-id="5a8d8-152">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="5a8d8-153">Loudspeaker レンダリングの5分あたりの平均の異常。</span><span class="sxs-lookup"><span data-stu-id="5a8d8-153">Average glitches per five minutes for the loudspeaker rendering.</span></span> <span data-ttu-id="5a8d8-154">良好な品質といえるのは、5 分間に 1 回未満です。</span><span class="sxs-lookup"><span data-stu-id="5a8d8-154">For good quality, this should be less than one per five minutes.</span></span> <span data-ttu-id="5a8d8-155">音声ビデオ会議サーバー、仲介サーバー、または IP 電話では報告されません。</span><span class="sxs-lookup"><span data-stu-id="5a8d8-155">Not reported by A/V Conferencing Servers, Mediation Servers, or IP phones.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5a8d8-156"><strong>AudioMicGlitchRate</strong></span><span class="sxs-lookup"><span data-stu-id="5a8d8-156"><strong>AudioMicGlitchRate</strong></span></span></p></td>
<td><p><span data-ttu-id="5a8d8-157">int</span><span class="sxs-lookup"><span data-stu-id="5a8d8-157">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="5a8d8-158">マイクキャプチャに対する5分あたりの平均の異常。</span><span class="sxs-lookup"><span data-stu-id="5a8d8-158">Average glitches per five minutes for the microphone capture.</span></span> <span data-ttu-id="5a8d8-159">良好な品質といえるのは、5 分間に 1 回未満です。</span><span class="sxs-lookup"><span data-stu-id="5a8d8-159">For good quality this should be less than one per five minutes.</span></span> <span data-ttu-id="5a8d8-160">音声ビデオ会議サーバー、仲介サーバー、または IP 電話では報告されません。</span><span class="sxs-lookup"><span data-stu-id="5a8d8-160">Not reported by A/V Conferencing Servers, Mediation Servers, or IP phones.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5a8d8-161"><strong>AudioTimestampDriftRateMic</strong></span><span class="sxs-lookup"><span data-stu-id="5a8d8-161"><strong>AudioTimestampDriftRateMic</strong></span></span></p></td>
<td><p><span data-ttu-id="5a8d8-162">10進数 (9、2)</span><span class="sxs-lookup"><span data-stu-id="5a8d8-162">decimal(9,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="5a8d8-163">CPU クロックに対するマイクデバイスのクロック誤差の割合です。</span><span class="sxs-lookup"><span data-stu-id="5a8d8-163">Microphone device clock drift rate, relative to CPU clock.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5a8d8-164"><strong>AudioTimestampDriftRateSpk</strong></span><span class="sxs-lookup"><span data-stu-id="5a8d8-164"><strong>AudioTimestampDriftRateSpk</strong></span></span></p></td>
<td><p><span data-ttu-id="5a8d8-165">10進数 (9、2)</span><span class="sxs-lookup"><span data-stu-id="5a8d8-165">decimal(9,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="5a8d8-166">CPU クロックに対するスピーカーデバイスのクロック誤差の割合。</span><span class="sxs-lookup"><span data-stu-id="5a8d8-166">Speaker device clock drift rate, relative to CPU clock.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5a8d8-167"><strong>AudioTimestampErrorMicMs</strong></span><span class="sxs-lookup"><span data-stu-id="5a8d8-167"><strong>AudioTimestampErrorMicMs</strong></span></span></p></td>
<td><p><span data-ttu-id="5a8d8-168">10進数 (9、2)</span><span class="sxs-lookup"><span data-stu-id="5a8d8-168">decimal(9,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="5a8d8-169">CPU クロックに対するスピーカーデバイスのクロック誤差の割合。</span><span class="sxs-lookup"><span data-stu-id="5a8d8-169">Speaker device clock drift rate, relative to CPU clock.</span></span></p>
<p><span data-ttu-id="5a8d8-170">過去 20 秒間の通話での平均マイク キャプチャ ストリーム タイム スタンプ エラーです (ミリ秒単位)。</span><span class="sxs-lookup"><span data-stu-id="5a8d8-170">Average microphone capture stream time stamp error, in milliseconds, in the last 20 seconds of the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5a8d8-171"><strong>AudioTimestampErrorSpkMs</strong></span><span class="sxs-lookup"><span data-stu-id="5a8d8-171"><strong>AudioTimestampErrorSpkMs</strong></span></span></p></td>
<td><p><span data-ttu-id="5a8d8-172">10進数 (9、2)</span><span class="sxs-lookup"><span data-stu-id="5a8d8-172">decimal(9,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="5a8d8-173">過去20秒間の通話の平均スピーカーレンダーストリームタイムスタンプエラー (ミリ秒単位)。</span><span class="sxs-lookup"><span data-stu-id="5a8d8-173">Average speaker render stream time stamp error, in milliseconds, in the last 20 seconds of the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5a8d8-174"><strong>VsEntryCauses</strong></span><span class="sxs-lookup"><span data-stu-id="5a8d8-174"><strong>VsEntryCauses</strong></span></span></p></td>
<td><p><span data-ttu-id="5a8d8-175">smallint</span><span class="sxs-lookup"><span data-stu-id="5a8d8-175">smallint</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="5a8d8-176">音声スイッチは、遮断能力が低下した半二重モードです。</span><span class="sxs-lookup"><span data-stu-id="5a8d8-176">Voice switch is a half-duplex mode with reduced interruption ability.</span></span> <span data-ttu-id="5a8d8-177">音声スイッチエントリの原因:</span><span class="sxs-lookup"><span data-stu-id="5a8d8-177">Causes of voice switch entry:</span></span></p>
<p><span data-ttu-id="5a8d8-178">ENTER_VS_BADTS 0x01</span><span class="sxs-lookup"><span data-stu-id="5a8d8-178">ENTER_VS_BADTS 0x01</span></span></p>
<p><span data-ttu-id="5a8d8-179">ENTER_VS_ECHO 0x02</span><span class="sxs-lookup"><span data-stu-id="5a8d8-179">ENTER_VS_ECHO 0x02</span></span></p>
<p><span data-ttu-id="5a8d8-180">ENTER_VS_FORCEORCONVERGENCE 0x04</span><span class="sxs-lookup"><span data-stu-id="5a8d8-180">ENTER_VS_FORCEORCONVERGENCE 0x04</span></span></p>
<p><span data-ttu-id="5a8d8-181">ENTER_VS_DNLP 0x08</span><span class="sxs-lookup"><span data-stu-id="5a8d8-181">ENTER_VS_DNLP 0x08</span></span></p>
<p><span data-ttu-id="5a8d8-182">原因として、個々の原因の組み合わせが考えられます。</span><span class="sxs-lookup"><span data-stu-id="5a8d8-182">The cause can be a combination of those individual causes.</span></span> <span data-ttu-id="5a8d8-183">ENTER_VS_FORCEORCONVERGENCE は、テストの目的でのみ、レジストリキーを使用して有効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="5a8d8-183">ENTER_VS_FORCEORCONVERGENCE can only be enabled by regkey for test purpose.</span></span></p>
<p><span data-ttu-id="5a8d8-184">この列のデータ型は、Microsoft Lync Server 2013 で変更されました。</span><span class="sxs-lookup"><span data-stu-id="5a8d8-184">The data type for this column was changed in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5a8d8-185"><strong>EchoEventCauses</strong></span><span class="sxs-lookup"><span data-stu-id="5a8d8-185"><strong>EchoEventCauses</strong></span></span></p></td>
<td><p><span data-ttu-id="5a8d8-186">tinyint</span><span class="sxs-lookup"><span data-stu-id="5a8d8-186">tinyint</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="5a8d8-187">Echo イベントの原因:</span><span class="sxs-lookup"><span data-stu-id="5a8d8-187">Causes of an echo event:</span></span></p>
<p><span data-ttu-id="5a8d8-188">ECHO_EVENT_BAD_TIMESTAMP 0x01</span><span class="sxs-lookup"><span data-stu-id="5a8d8-188">ECHO_EVENT_BAD_TIMESTAMP 0x01</span></span></p>
<p><span data-ttu-id="5a8d8-189">ECHO_EVENT_POSTAEC_ECHO 0x02</span><span class="sxs-lookup"><span data-stu-id="5a8d8-189">ECHO_EVENT_POSTAEC_ECHO 0x02</span></span></p>
<p><span data-ttu-id="5a8d8-190">ECHO_EVENT_ANLP 0x04</span><span class="sxs-lookup"><span data-stu-id="5a8d8-190">ECHO_EVENT_ANLP 0x04</span></span></p>
<p><span data-ttu-id="5a8d8-191">ECHO_EVENT_DNLP 0x08</span><span class="sxs-lookup"><span data-stu-id="5a8d8-191">ECHO_EVENT_DNLP 0x08</span></span></p>
<p><span data-ttu-id="5a8d8-192">ECHO_EVENT_MIC_CLIPPING 0x10</span><span class="sxs-lookup"><span data-stu-id="5a8d8-192">ECHO_EVENT_MIC_CLIPPING 0x10</span></span></p>
<p><span data-ttu-id="5a8d8-193">ECHO_EVENT_BAD_STATE 0x20</span><span class="sxs-lookup"><span data-stu-id="5a8d8-193">ECHO_EVENT_BAD_STATE 0x20</span></span></p>
<p><span data-ttu-id="5a8d8-194">原因として、個々の原因の組み合わせが考えられます。</span><span class="sxs-lookup"><span data-stu-id="5a8d8-194">The cause can be a combination of those individual causes.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5a8d8-195"><strong>EchoPercentMicIn</strong></span><span class="sxs-lookup"><span data-stu-id="5a8d8-195"><strong>EchoPercentMicIn</strong></span></span></p></td>
<td><p><span data-ttu-id="5a8d8-196">10進数 (5、2)</span><span class="sxs-lookup"><span data-stu-id="5a8d8-196">decimal(5,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="5a8d8-197">マイクキャプチャストリームでエコーが検出された時間の割合。</span><span class="sxs-lookup"><span data-stu-id="5a8d8-197">Percentage of time when echo was detected in the microphone capture stream.</span></span> <span data-ttu-id="5a8d8-198">通常、ヘッドホンまたはハンドセットの値は低く、スピーカーフォンまたはスタンドアロンスピーカーでは高です。</span><span class="sxs-lookup"><span data-stu-id="5a8d8-198">Typically, values are low for headsets or handsets, and higher for speaker phones or stand-alone speakers.</span></span> <span data-ttu-id="5a8d8-199">オンボード音響エコーキャンセレーションをサポートするデバイスでは、値が大きいと、エコーリークが発生します。</span><span class="sxs-lookup"><span data-stu-id="5a8d8-199">For devices that support on-board acoustic echo cancellation, high values indicate echo leak.</span></span> <span data-ttu-id="5a8d8-200">その他のデバイスでは、この指標を使用してデバイスの品質を評価することはできません。</span><span class="sxs-lookup"><span data-stu-id="5a8d8-200">For other devices, this metric should not be used to evaluate device quality.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5a8d8-201"><strong>EchoPercentSend</strong></span><span class="sxs-lookup"><span data-stu-id="5a8d8-201"><strong>EchoPercentSend</strong></span></span></p></td>
<td><p><span data-ttu-id="5a8d8-202">10進数 (5、2)</span><span class="sxs-lookup"><span data-stu-id="5a8d8-202">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="5a8d8-203">送信されたストリームでエコーが検出された時間の割合。</span><span class="sxs-lookup"><span data-stu-id="5a8d8-203">Percentage of time when echo is detected in sent stream.</span></span> <span data-ttu-id="5a8d8-204">送信ストリームでの高いエコー率は、エコー リークを示しています。</span><span class="sxs-lookup"><span data-stu-id="5a8d8-204">High echo percentage in send streams an indication of echo leak.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5a8d8-205"><strong>RxAGCSignalLevel</strong></span><span class="sxs-lookup"><span data-stu-id="5a8d8-205"><strong>RxAGCSignalLevel</strong></span></span></p></td>
<td><p><span data-ttu-id="5a8d8-206">int</span><span class="sxs-lookup"><span data-stu-id="5a8d8-206">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="5a8d8-207">ゲートウェイからの仲介サーバーの受信した信号レベル。これは、仲介サーバーにのみ適用されます。</span><span class="sxs-lookup"><span data-stu-id="5a8d8-207">Received signal level on the Mediation Server from the Gateway; this applies only to the Mediation Server.</span></span> <span data-ttu-id="5a8d8-208">この測定指標の単位は dBoV です。</span><span class="sxs-lookup"><span data-stu-id="5a8d8-208">The unit of this metric is dBoV.</span></span> <span data-ttu-id="5a8d8-209">品質を良くするには、許容範囲は [-30 ~-18] dBoV にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="5a8d8-209">For good quality, the acceptable range should be [-30 to -18] dBoV.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5a8d8-210"><strong>RxAGCNoiseLevel</strong></span><span class="sxs-lookup"><span data-stu-id="5a8d8-210"><strong>RxAGCNoiseLevel</strong></span></span></p></td>
<td><p><span data-ttu-id="5a8d8-211">int</span><span class="sxs-lookup"><span data-stu-id="5a8d8-211">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="5a8d8-212">ゲートウェイからの仲介サーバー上の受信した信号レベル。</span><span class="sxs-lookup"><span data-stu-id="5a8d8-212">Received signal level on the Mediation Server from the Gateway.</span></span> <span data-ttu-id="5a8d8-213">この値は、仲介サーバーに対してのみ適用されます。</span><span class="sxs-lookup"><span data-stu-id="5a8d8-213">This applies only to the Mediation Server.</span></span> <span data-ttu-id="5a8d8-214">この測定指標の単位は dBoV です。</span><span class="sxs-lookup"><span data-stu-id="5a8d8-214">The unit of this metric is dBoV.</span></span> <span data-ttu-id="5a8d8-215">良好な品質として許容される範囲は、-50 dBoV 未満です。</span><span class="sxs-lookup"><span data-stu-id="5a8d8-215">For good quality, the acceptable range should be less than -50 dBoV.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5a8d8-216"><strong>RxAvgAGCGain</strong></span><span class="sxs-lookup"><span data-stu-id="5a8d8-216"><strong>RxAvgAGCGain</strong></span></span></p></td>
<td><p><span data-ttu-id="5a8d8-217">int</span><span class="sxs-lookup"><span data-stu-id="5a8d8-217">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="5a8d8-218">仲介サーバー側での自動ゲイン制御 (AGC)。</span><span class="sxs-lookup"><span data-stu-id="5a8d8-218">Automatic gain control (AGC) on the Mediation Server side.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5a8d8-219"><strong>InitialSignalLevelRMS</strong></span><span class="sxs-lookup"><span data-stu-id="5a8d8-219"><strong>InitialSignalLevelRMS</strong></span></span></p></td>
<td><p><span data-ttu-id="5a8d8-220">浮動小数点数</span><span class="sxs-lookup"><span data-stu-id="5a8d8-220">float</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="5a8d8-221">通話の最初の最大30秒間の着信信号のルート平均二乗 (RMS)。</span><span class="sxs-lookup"><span data-stu-id="5a8d8-221">The root mean square (RMS) of the incoming signal of up to the first 30 seconds of the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5a8d8-222"><strong>RecvSignalLevelCh1</strong></span><span class="sxs-lookup"><span data-stu-id="5a8d8-222"><strong>RecvSignalLevelCh1</strong></span></span></p></td>
<td><p><span data-ttu-id="5a8d8-223">int</span><span class="sxs-lookup"><span data-stu-id="5a8d8-223">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="5a8d8-224">チャネル1で受信したシグナルレベル。</span><span class="sxs-lookup"><span data-stu-id="5a8d8-224">Signal level as received on channel 1.</span></span></p>
<p><span data-ttu-id="5a8d8-225">このコラムは、Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="5a8d8-225">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5a8d8-226"><strong>RecvSignalLevelCh2</strong></span><span class="sxs-lookup"><span data-stu-id="5a8d8-226"><strong>RecvSignalLevelCh2</strong></span></span></p></td>
<td><p><span data-ttu-id="5a8d8-227">int</span><span class="sxs-lookup"><span data-stu-id="5a8d8-227">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="5a8d8-228">チャネル2で受信したシグナルレベル。</span><span class="sxs-lookup"><span data-stu-id="5a8d8-228">Signal level as received on channel 2.</span></span></p>
<p><span data-ttu-id="5a8d8-229">このコラムは、Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="5a8d8-229">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5a8d8-230"><strong>RecvNoiseLevelCh1</strong></span><span class="sxs-lookup"><span data-stu-id="5a8d8-230"><strong>RecvNoiseLevelCh1</strong></span></span></p></td>
<td><p><span data-ttu-id="5a8d8-231">int</span><span class="sxs-lookup"><span data-stu-id="5a8d8-231">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="5a8d8-232">チャネル1で受信したノイズレベル。</span><span class="sxs-lookup"><span data-stu-id="5a8d8-232">Noise level as received on channel 1.</span></span></p>
<p><span data-ttu-id="5a8d8-233">このコラムは、Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="5a8d8-233">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5a8d8-234"><strong>RecvNoiseLevelCh2</strong></span><span class="sxs-lookup"><span data-stu-id="5a8d8-234"><strong>RecvNoiseLevelCh2</strong></span></span></p></td>
<td><p><span data-ttu-id="5a8d8-235">int</span><span class="sxs-lookup"><span data-stu-id="5a8d8-235">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="5a8d8-236">チャネル2で受信したノイズレベル。</span><span class="sxs-lookup"><span data-stu-id="5a8d8-236">Noise level as received on channel 2.</span></span></p>
<p><span data-ttu-id="5a8d8-237">このコラムは、Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="5a8d8-237">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5a8d8-238"><strong>SendSignalLevelCh1</strong></span><span class="sxs-lookup"><span data-stu-id="5a8d8-238"><strong>SendSignalLevelCh1</strong></span></span></p></td>
<td><p><span data-ttu-id="5a8d8-239">int</span><span class="sxs-lookup"><span data-stu-id="5a8d8-239">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="5a8d8-240">チャネル1で送信されたシグナルレベル。</span><span class="sxs-lookup"><span data-stu-id="5a8d8-240">Signal level as sent on channel 1.</span></span></p>
<p><span data-ttu-id="5a8d8-241">このコラムは、Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="5a8d8-241">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5a8d8-242"><strong>SendSignalLevelCh2</strong></span><span class="sxs-lookup"><span data-stu-id="5a8d8-242"><strong>SendSignalLevelCh2</strong></span></span></p></td>
<td><p><span data-ttu-id="5a8d8-243">int</span><span class="sxs-lookup"><span data-stu-id="5a8d8-243">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="5a8d8-244">チャネル2で送信されたシグナルレベル。</span><span class="sxs-lookup"><span data-stu-id="5a8d8-244">Signal level as sent on channel 2.</span></span></p>
<p><span data-ttu-id="5a8d8-245">このコラムは、Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="5a8d8-245">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5a8d8-246"><strong>SendNoiseLevelCh1</strong></span><span class="sxs-lookup"><span data-stu-id="5a8d8-246"><strong>SendNoiseLevelCh1</strong></span></span></p></td>
<td><p><span data-ttu-id="5a8d8-247">int</span><span class="sxs-lookup"><span data-stu-id="5a8d8-247">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="5a8d8-248">チャネル1で送信されたノイズレベル。</span><span class="sxs-lookup"><span data-stu-id="5a8d8-248">Noise level as sent on channel 1.</span></span></p>
<p><span data-ttu-id="5a8d8-249">このコラムは、Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="5a8d8-249">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5a8d8-250"><strong>SendNoiseLevelCh2</strong></span><span class="sxs-lookup"><span data-stu-id="5a8d8-250"><strong>SendNoiseLevelCh2</strong></span></span></p></td>
<td><p><span data-ttu-id="5a8d8-251">int</span><span class="sxs-lookup"><span data-stu-id="5a8d8-251">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="5a8d8-252">チャネル2で送信されたノイズレベル。</span><span class="sxs-lookup"><span data-stu-id="5a8d8-252">Noise level as sent on channel 2.</span></span></p>
<p><span data-ttu-id="5a8d8-253">このコラムは、Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="5a8d8-253">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

