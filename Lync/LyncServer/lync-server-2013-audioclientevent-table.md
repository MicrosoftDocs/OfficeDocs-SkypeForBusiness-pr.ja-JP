---
title: 'Lync Server 2013: AudioClientEvent テーブル'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: AudioClientEvent table
ms:assetid: fef73d8f-7261-4e5b-9769-82435b007979
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg413086(v=OCS.15)
ms:contentKeyID: 48185967
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 44d5146b334af83618ca2dd6261a18e72708f4f5
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41722627"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="audioclientevent-table-in-lync-server-2013"></a><span data-ttu-id="ae62e-102">Lync Server 2013 の AudioClientEvent テーブル</span><span class="sxs-lookup"><span data-stu-id="ae62e-102">AudioClientEvent table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ae62e-103">_**最終更新日:** 2012-10-17_</span><span class="sxs-lookup"><span data-stu-id="ae62e-103">_**Topic Last Modified:** 2012-10-17_</span></span>

<span data-ttu-id="ae62e-104">各レコードには、音声通話中の1つのエンドポイントのクライアントイベントが含まれています。</span><span class="sxs-lookup"><span data-stu-id="ae62e-104">Each record contains a client event for one endpoint in an audio call.</span></span> <span data-ttu-id="ae62e-105">通常、1つの通話には2つのレコードがあります。1つは呼び出し元用、もう1つは呼び出し先用です。</span><span class="sxs-lookup"><span data-stu-id="ae62e-105">Usually, one call has two records, one for caller and one for callee.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="ae62e-106"><strong>列</strong></span><span class="sxs-lookup"><span data-stu-id="ae62e-106"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="ae62e-107"><strong>データ型</strong></span><span class="sxs-lookup"><span data-stu-id="ae62e-107"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="ae62e-108"><strong>キー/インデックス</strong></span><span class="sxs-lookup"><span data-stu-id="ae62e-108"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="ae62e-109"><strong>詳細</strong></span><span class="sxs-lookup"><span data-stu-id="ae62e-109"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ae62e-110"><strong>ConferenceDateTime</strong></span><span class="sxs-lookup"><span data-stu-id="ae62e-110"><strong>ConferenceDateTime</strong></span></span></p></td>
<td><p><span data-ttu-id="ae62e-111">datetime</span><span class="sxs-lookup"><span data-stu-id="ae62e-111">datetime</span></span></p></td>
<td><p><span data-ttu-id="ae62e-112">Primary</span><span class="sxs-lookup"><span data-stu-id="ae62e-112">Primary</span></span></p></td>
<td><p><span data-ttu-id="ae62e-113"><a href="lync-server-2013-medialine-table.md">Lync Server 2013 の MediaLine テーブル</a>から参照されている。</span><span class="sxs-lookup"><span data-stu-id="ae62e-113">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ae62e-114"><strong>SessionSeq</strong></span><span class="sxs-lookup"><span data-stu-id="ae62e-114"><strong>SessionSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="ae62e-115">int</span><span class="sxs-lookup"><span data-stu-id="ae62e-115">int</span></span></p></td>
<td><p><span data-ttu-id="ae62e-116">Primary</span><span class="sxs-lookup"><span data-stu-id="ae62e-116">Primary</span></span></p></td>
<td><p><span data-ttu-id="ae62e-117"><a href="lync-server-2013-medialine-table.md">Lync Server 2013 の MediaLine テーブル</a>から参照されている。</span><span class="sxs-lookup"><span data-stu-id="ae62e-117">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ae62e-118"><strong>MediaLineLabel</strong></span><span class="sxs-lookup"><span data-stu-id="ae62e-118"><strong>MediaLineLabel</strong></span></span></p></td>
<td><p><span data-ttu-id="ae62e-119">tinyint</span><span class="sxs-lookup"><span data-stu-id="ae62e-119">tinyint</span></span></p></td>
<td><p><span data-ttu-id="ae62e-120">Primary</span><span class="sxs-lookup"><span data-stu-id="ae62e-120">Primary</span></span></p></td>
<td><p><span data-ttu-id="ae62e-121"><a href="lync-server-2013-medialine-table.md">Lync Server 2013 の MediaLine テーブル</a>から参照されている。</span><span class="sxs-lookup"><span data-stu-id="ae62e-121">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ae62e-122"><strong>FromCaller</strong></span><span class="sxs-lookup"><span data-stu-id="ae62e-122"><strong>FromCaller</strong></span></span></p></td>
<td><p><span data-ttu-id="ae62e-123">bit</span><span class="sxs-lookup"><span data-stu-id="ae62e-123">bit</span></span></p></td>
<td><p><span data-ttu-id="ae62e-124">Primary</span><span class="sxs-lookup"><span data-stu-id="ae62e-124">Primary</span></span></p></td>
<td><p><span data-ttu-id="ae62e-125">0: 呼び出し先のデータ</span><span class="sxs-lookup"><span data-stu-id="ae62e-125">0: Callee’s data</span></span></p>
<p><span data-ttu-id="ae62e-126">1: 発信者のデータ</span><span class="sxs-lookup"><span data-stu-id="ae62e-126">1: Caller’s data</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ae62e-127"><strong>NetworkSendQualityEventRatio</strong></span><span class="sxs-lookup"><span data-stu-id="ae62e-127"><strong>NetworkSendQualityEventRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="ae62e-128">10進数 (5, 2)</span><span class="sxs-lookup"><span data-stu-id="ae62e-128">decimal(5,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="ae62e-129">セッションのパーセンテージ NetworkSendQuality イベントが ' Bad ' 状態に対して発生しました。</span><span class="sxs-lookup"><span data-stu-id="ae62e-129">Percentage of session the NetworkSendQuality event was fired for ‘Bad’ state.</span></span></p>
<p><span data-ttu-id="ae62e-130">ネットワーク品質は、ジッタまたはパケット損失の観点から、送信された音声の品質に重大な影響を与えることがあります。</span><span class="sxs-lookup"><span data-stu-id="ae62e-130">Network quality in terms of jitter or packet loss is severe and impacting the quality of audio being sent.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ae62e-131"><strong>NetworkReceiveQualityEventRatio</strong></span><span class="sxs-lookup"><span data-stu-id="ae62e-131"><strong>NetworkReceiveQualityEventRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="ae62e-132">10進数 (5, 2)</span><span class="sxs-lookup"><span data-stu-id="ae62e-132">decimal(5,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="ae62e-133">セッションのパーセンテージ ReceiveSendQuality イベントが ' Bad ' 状態で発生しました。</span><span class="sxs-lookup"><span data-stu-id="ae62e-133">Percentage of session the ReceiveSendQuality event was fired for ‘Bad’ state.</span></span></p>
<p><span data-ttu-id="ae62e-134">ネットワーク品質は、ジッタまたはパケット損失の観点から、受信中のオーディオの品質に深刻な影響を与えることができます。</span><span class="sxs-lookup"><span data-stu-id="ae62e-134">Network quality in terms of jitter or packet loss is severe and impacting the quality of audio being received.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ae62e-135"><strong>NetworkDelayEventRatio スペック</strong></span><span class="sxs-lookup"><span data-stu-id="ae62e-135"><strong>NetworkDelayEventRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="ae62e-136">10進数 (5, 2)</span><span class="sxs-lookup"><span data-stu-id="ae62e-136">decimal(5,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="ae62e-137">セッションのパーセンテージ "Bad" 状態に対して Delay イベントが発生しました。</span><span class="sxs-lookup"><span data-stu-id="ae62e-137">Percentage of session the Delay event was fired for ‘Bad’ state.</span></span> <span data-ttu-id="ae62e-138">ネットワーク待ち時間が重大であり、対話的なコミュニケーションを防ぐことで、エクスペリエンスに影響を与える</span><span class="sxs-lookup"><span data-stu-id="ae62e-138">Network latency is severe and impacting the experience by preventing interactive communication</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ae62e-139"><strong>NetworkBandwidthLowEventRatio</strong></span><span class="sxs-lookup"><span data-stu-id="ae62e-139"><strong>NetworkBandwidthLowEventRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="ae62e-140">10進数 (5, 2)</span><span class="sxs-lookup"><span data-stu-id="ae62e-140">decimal(5,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="ae62e-141">セッションのパーセンテージ低帯域幅イベントが ' Bad ' 状態に対して発生しました。</span><span class="sxs-lookup"><span data-stu-id="ae62e-141">Percentage of session the LowBandwidth event was fired for ‘Bad’ state.</span></span> <span data-ttu-id="ae62e-142">利用可能な音声エクスペリエンスを実現するには、利用可能な帯域幅が不足しています。</span><span class="sxs-lookup"><span data-stu-id="ae62e-142">The available bandwidth is insufficient for an acceptable voice experience.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ae62e-143"><strong>CPUInsufficientEventRatio</strong></span><span class="sxs-lookup"><span data-stu-id="ae62e-143"><strong>CPUInsufficientEventRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="ae62e-144">10進数 (5, 2)</span><span class="sxs-lookup"><span data-stu-id="ae62e-144">decimal(5,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="ae62e-145">セッションの割合。不適切な CPU イベントが ' Bad ' 状態に対して発生しました。</span><span class="sxs-lookup"><span data-stu-id="ae62e-145">Percentage of session the insufficient CPU event was fired for ‘Bad’ state.</span></span> <span data-ttu-id="ae62e-146">現在使用中のモダリティとアプリケーションで処理するための CPU サイクルが十分にありません。</span><span class="sxs-lookup"><span data-stu-id="ae62e-146">There are insufficient CPU cycles for processing with the current modalities and applications in use.</span></span> <span data-ttu-id="ae62e-147">これにより、オーディオチャンネルでひずみが発生します。</span><span class="sxs-lookup"><span data-stu-id="ae62e-147">This causes distortions with the audio channel.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ae62e-148"><strong>DeviceHalfDuplexAECEventRatio</strong></span><span class="sxs-lookup"><span data-stu-id="ae62e-148"><strong>DeviceHalfDuplexAECEventRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="ae62e-149">10進数 (5, 2)</span><span class="sxs-lookup"><span data-stu-id="ae62e-149">decimal(5,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="ae62e-150">セッションのパーセンテージ DeviceHalfDuplexAEC イベントが ' Bad ' 状態で発生しました。</span><span class="sxs-lookup"><span data-stu-id="ae62e-150">Percentage of session the DeviceHalfDuplexAEC event was fired for ‘Bad’ state.</span></span> <span data-ttu-id="ae62e-151">エコーを防ぐために、システムは半二重モードに設定されています。</span><span class="sxs-lookup"><span data-stu-id="ae62e-151">In order to prevent echo, the system has enter half duplex.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ae62e-152"><strong>DeviceRenderNotFunctioningEventRatio</strong></span><span class="sxs-lookup"><span data-stu-id="ae62e-152"><strong>DeviceRenderNotFunctioningEventRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="ae62e-153">10進数 (5, 2)</span><span class="sxs-lookup"><span data-stu-id="ae62e-153">decimal(5,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="ae62e-154">セッションの割合 DeviceRenderNotFunctioning イベントが ' Bad ' 状態に対して発生しました。</span><span class="sxs-lookup"><span data-stu-id="ae62e-154">Percentage of session the DeviceRenderNotFunctioning event was fired for ‘Bad’ state.</span></span> <span data-ttu-id="ae62e-155">現在セッションで使用されているレンダーデバイスが正常に機能していません。</span><span class="sxs-lookup"><span data-stu-id="ae62e-155">The render device currently being used for the session is not functioning correctly.</span></span> <span data-ttu-id="ae62e-156">これにより、1方向の音声の問題が発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="ae62e-156">This can cause one-way audio issues.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ae62e-157"><strong>DeviceCaptureNotFunctioningEventRatio 使い方</strong></span><span class="sxs-lookup"><span data-stu-id="ae62e-157"><strong>DeviceCaptureNotFunctioningEventRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="ae62e-158">10進数 (5, 2)</span><span class="sxs-lookup"><span data-stu-id="ae62e-158">decimal(5,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="ae62e-159">セッションのパーセンテージ DeviceCaptureNotFunctioning イベントが ' Bad ' 状態に対して発生しました。</span><span class="sxs-lookup"><span data-stu-id="ae62e-159">Percentage of session the DeviceCaptureNotFunctioning event was fired for ‘Bad’ state.</span></span> <span data-ttu-id="ae62e-160">現在セッションで使用されているキャプチャデバイスが正常に機能していません。</span><span class="sxs-lookup"><span data-stu-id="ae62e-160">The capture device currently being used for the session is not functioning correctly.</span></span> <span data-ttu-id="ae62e-161">これにより、1方向の音声の問題が発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="ae62e-161">This can cause one-way audio issues.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ae62e-162"><strong>DeviceGlitchesEventRatio</strong></span><span class="sxs-lookup"><span data-stu-id="ae62e-162"><strong>DeviceGlitchesEventRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="ae62e-163">10進数 (5, 2)</span><span class="sxs-lookup"><span data-stu-id="ae62e-163">decimal(5,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="ae62e-164">セッションの割合 DeviceGlitches イベントが ' Bad ' 状態で発生しました。</span><span class="sxs-lookup"><span data-stu-id="ae62e-164">Percentage of session the DeviceGlitches event was fired for ‘Bad’ state.</span></span> <span data-ttu-id="ae62e-165">オーディオのレンダリングで、ひずみの原因となる重大な問題が発生します。</span><span class="sxs-lookup"><span data-stu-id="ae62e-165">There are severe glitches in the rendering of audio which is causing distortions.</span></span> <span data-ttu-id="ae62e-166">これらのエラーは、ドライバーの問題、遅延プロシージャ呼び出し (DPC) ストーム (ドライバー)、および CPU 使用率が高くなることが原因で発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="ae62e-166">These glitches can be caused by driver issues, deferred procedure calls (DPC) storm (drivers), and high CPU usage.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ae62e-167"><strong>DeviceLowSNREventRatio</strong></span><span class="sxs-lookup"><span data-stu-id="ae62e-167"><strong>DeviceLowSNREventRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="ae62e-168">10進数 (5, 2)</span><span class="sxs-lookup"><span data-stu-id="ae62e-168">decimal(5,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="ae62e-169">セッションのパーセンテージ DeviceLowSNR イベントが ' Bad ' 状態に対して発生しました。</span><span class="sxs-lookup"><span data-stu-id="ae62e-169">Percentage of session the DeviceLowSNR event was fired for ‘Bad’ state.</span></span> <span data-ttu-id="ae62e-170">キャプチャ品質は非常に低い。雑音が多いか、ユーザがマイクから離れすぎている。</span><span class="sxs-lookup"><span data-stu-id="ae62e-170">The capture quality is very poor, either very noisy or user is talking too far away from the microphone.</span></span> <span data-ttu-id="ae62e-171">これにより、ひずみが発生します。</span><span class="sxs-lookup"><span data-stu-id="ae62e-171">This will cause distortions.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ae62e-172"><strong>DeviceLowSpeechLevelEventRatio</strong></span><span class="sxs-lookup"><span data-stu-id="ae62e-172"><strong>DeviceLowSpeechLevelEventRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="ae62e-173">10進数 (5, 2)</span><span class="sxs-lookup"><span data-stu-id="ae62e-173">decimal(5,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="ae62e-174">セッションのパーセンテージ DeviceLowSpeechLevel イベントが ' Bad ' 状態で発生しました。</span><span class="sxs-lookup"><span data-stu-id="ae62e-174">Percentage of session the DeviceLowSpeechLevel event was fired for ‘Bad’ state.</span></span> <span data-ttu-id="ae62e-175">ユーザーの音声レベルが低すぎて、システムがそれ以上の機能を向上させることができない。</span><span class="sxs-lookup"><span data-stu-id="ae62e-175">User‘s speech level is too low and the system cannot increase it any further.</span></span> <span data-ttu-id="ae62e-176">これにより、ひずみが発生したり、一方向のオーディオとして認識されるようになります。</span><span class="sxs-lookup"><span data-stu-id="ae62e-176">This can either cause distortions or perceived as one-way audio.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ae62e-177"><strong>DeviceClippingEventRatio</strong></span><span class="sxs-lookup"><span data-stu-id="ae62e-177"><strong>DeviceClippingEventRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="ae62e-178">10進数 (5, 2)</span><span class="sxs-lookup"><span data-stu-id="ae62e-178">Decimal(5,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="ae62e-179">セッションのパーセンテージ DeviceClipping イベントが ' Bad ' 状態で発生しました。</span><span class="sxs-lookup"><span data-stu-id="ae62e-179">Percentage of session the DeviceClipping event was fired for ‘Bad’ state.</span></span></p>
<p><span data-ttu-id="ae62e-180">ニアエンドの音声によってマイクがクリップされる場合は、クリッピングによるひずみが発生します。</span><span class="sxs-lookup"><span data-stu-id="ae62e-180">When near-end speech clips the microphone, far-end hears distortion due to clipping.</span></span> <span data-ttu-id="ae62e-181">ニアエンドマイクのクリッピングを回避することが重要です。</span><span class="sxs-lookup"><span data-stu-id="ae62e-181">It is important to avoid near-end microphone clipping.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ae62e-182"><strong>DeviceEchoEventRatio</strong></span><span class="sxs-lookup"><span data-stu-id="ae62e-182"><strong>DeviceEchoEventRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="ae62e-183">10進数 (5, 2)</span><span class="sxs-lookup"><span data-stu-id="ae62e-183">decimal(5,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="ae62e-184">セッションのパーセンテージ DeviceEchoEvent イベントが ' Bad ' 状態で発生しました。</span><span class="sxs-lookup"><span data-stu-id="ae62e-184">Percentage of session the DeviceEchoEvent event was fired for ‘Bad’ state.</span></span> <span data-ttu-id="ae62e-185">デバイスまたはセットアップが原因で、システムの補正機能を超えたエコーが発生しています。</span><span class="sxs-lookup"><span data-stu-id="ae62e-185">Device or setup is causing echo beyond the ability of the system to compensate.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ae62e-186"><strong>デバイスの Devicorています。</strong></span><span class="sxs-lookup"><span data-stu-id="ae62e-186"><strong>DeviceNearEndToEchoRatioEventRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="ae62e-187">10進数 (5, 2)</span><span class="sxs-lookup"><span data-stu-id="ae62e-187">decimal(5,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="ae62e-188">セッションのパーセンテージ Devicenなイベントが ' Bad ' 状態で発生しました。</span><span class="sxs-lookup"><span data-stu-id="ae62e-188">Percentage of session the DeviceNearEndToEchoRatio event was fired for ‘Bad’ state.</span></span> <span data-ttu-id="ae62e-189">ユーザーの音声が、ユーザーの中断を簡単にすることができるようになるため、キャプチャされたエコーと比較して、ユーザーエクスペリエンスに影響を与えることができます。</span><span class="sxs-lookup"><span data-stu-id="ae62e-189">The user’s speech is too low compared to the echo being captured which impacts the users experience because it limits how easy it is to interrupt a user.</span></span> <span data-ttu-id="ae62e-190">スピーカーの音量を下げて、マイクをトーカーに近づける。</span><span class="sxs-lookup"><span data-stu-id="ae62e-190">Reduce speaker volume, move the microphone closer to the talker.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ae62e-191"><strong>DeviceMultipleEndpointsEventCount</strong></span><span class="sxs-lookup"><span data-stu-id="ae62e-191"><strong>DeviceMultipleEndpointsEventCount</strong></span></span></p></td>
<td><p><span data-ttu-id="ae62e-192">int</span><span class="sxs-lookup"><span data-stu-id="ae62e-192">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="ae62e-193">セッション中に ' Bad ' 状態に対して DeviceMultipleEndpoints イベントが発生した回数。</span><span class="sxs-lookup"><span data-stu-id="ae62e-193">Number of times during session the DeviceMultipleEndpoints event was fired for ‘Bad’ state.</span></span> <span data-ttu-id="ae62e-194">同じセッション内の複数のオーディオエンドポイントが検出され、レンダーボリュームが減ることで、システムが補正しています。</span><span class="sxs-lookup"><span data-stu-id="ae62e-194">Multiple audio endpoints in the same session detected and the system has compensated by reducing render volume.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ae62e-195"><strong>Deviceskのイベントカウント</strong></span><span class="sxs-lookup"><span data-stu-id="ae62e-195"><strong>DeviceHowlingEventCount</strong></span></span></p></td>
<td><p><span data-ttu-id="ae62e-196">int</span><span class="sxs-lookup"><span data-stu-id="ae62e-196">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="ae62e-197">セッション中に、' Bad ' 状態に対して Deviceなイベントイベントが発生した回数。</span><span class="sxs-lookup"><span data-stu-id="ae62e-197">Number of times during session the DeviceHowlingEvent event was fired for ‘Bad’ state.</span></span> <span data-ttu-id="ae62e-198">音声フィードバックループが検出されました (複数のエンドポイントでのオーディオパスの共有によって発生)。</span><span class="sxs-lookup"><span data-stu-id="ae62e-198">Audio feedback loop detected (caused by multiple endpoints sharing audio path).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ae62e-199"><strong>Devicerendervolumevolumeeventr</strong></span><span class="sxs-lookup"><span data-stu-id="ae62e-199"><strong>DeviceRenderZeroVolumeEventRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="ae62e-200">10進数 (5, 2)</span><span class="sxs-lookup"><span data-stu-id="ae62e-200">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="ae62e-201">セッションのパーセンテージ Devicerenderゼロボリュームイベントが "Bad" 状態になったときに発生しました。</span><span class="sxs-lookup"><span data-stu-id="ae62e-201">Percentage of session the DeviceRenderZeroVolume event was fired for being in the “Bad’ state.</span></span> <span data-ttu-id="ae62e-202">レンダーデバイスがボリューム0に設定されています。</span><span class="sxs-lookup"><span data-stu-id="ae62e-202">The render device was set to zero volume.</span></span></p>
<p><span data-ttu-id="ae62e-203">この列は Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="ae62e-203">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ae62e-204"><strong>Devicerendermuteeventr</strong></span><span class="sxs-lookup"><span data-stu-id="ae62e-204"><strong>DeviceRenderMuteEventRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="ae62e-205">10進数 (5, 2)</span><span class="sxs-lookup"><span data-stu-id="ae62e-205">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="ae62e-206">セッションのパーセンテージ DeviceRenderMute イベントが "Bad" 状態になったときに発生しました。</span><span class="sxs-lookup"><span data-stu-id="ae62e-206">Percentage of session the DeviceRenderMute event was fired for being in the “Bad’ state.</span></span> <span data-ttu-id="ae62e-207">レンダーデバイスがミュートにされました。</span><span class="sxs-lookup"><span data-stu-id="ae62e-207">The render device was muted.</span></span></p>
<p><span data-ttu-id="ae62e-208">この列は Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="ae62e-208">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

