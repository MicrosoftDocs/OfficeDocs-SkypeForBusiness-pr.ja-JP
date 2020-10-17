---
title: 'Lync Server 2013: AudioClientEvent テーブル'
description: 'Lync Server 2013: AudioClientEvent テーブル。'
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
ms.openlocfilehash: 2200cd9567bdd10ac4ad8f5c269062c2f5614dcb
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48568783"
---
# <a name="audioclientevent-table-in-lync-server-2013"></a><span data-ttu-id="5ea46-103">Lync Server 2013 の AudioClientEvent テーブル</span><span class="sxs-lookup"><span data-stu-id="5ea46-103">AudioClientEvent table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5ea46-104">_**トピックの最終更新日:** 2012-10-17_</span><span class="sxs-lookup"><span data-stu-id="5ea46-104">_**Topic Last Modified:** 2012-10-17_</span></span>

<span data-ttu-id="5ea46-105">各レコードには、音声通話の1つのエンドポイントのクライアントイベントが含まれています。</span><span class="sxs-lookup"><span data-stu-id="5ea46-105">Each record contains a client event for one endpoint in an audio call.</span></span> <span data-ttu-id="5ea46-106">通常、1つの呼び出しには2つのレコードがあり、1つは呼び出し元用、もう1つは呼び出し先用です。</span><span class="sxs-lookup"><span data-stu-id="5ea46-106">Usually, one call has two records, one for caller and one for callee.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="5ea46-107"><strong>列</strong></span><span class="sxs-lookup"><span data-stu-id="5ea46-107"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="5ea46-108"><strong>データ型</strong></span><span class="sxs-lookup"><span data-stu-id="5ea46-108"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="5ea46-109"><strong>キー/インデックス</strong></span><span class="sxs-lookup"><span data-stu-id="5ea46-109"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="5ea46-110"><strong>詳細</strong></span><span class="sxs-lookup"><span data-stu-id="5ea46-110"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="5ea46-111"><strong>ConferenceDateTime</strong></span><span class="sxs-lookup"><span data-stu-id="5ea46-111"><strong>ConferenceDateTime</strong></span></span></p></td>
<td><p><span data-ttu-id="5ea46-112">日付型</span><span class="sxs-lookup"><span data-stu-id="5ea46-112">datetime</span></span></p></td>
<td><p><span data-ttu-id="5ea46-113">Primary</span><span class="sxs-lookup"><span data-stu-id="5ea46-113">Primary</span></span></p></td>
<td><p><span data-ttu-id="5ea46-114"><a href="lync-server-2013-medialine-table.md">Lync Server 2013 の MediaLine テーブル</a>から参照されます。</span><span class="sxs-lookup"><span data-stu-id="5ea46-114">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5ea46-115"><strong>SessionSeq</strong></span><span class="sxs-lookup"><span data-stu-id="5ea46-115"><strong>SessionSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="5ea46-116">int</span><span class="sxs-lookup"><span data-stu-id="5ea46-116">int</span></span></p></td>
<td><p><span data-ttu-id="5ea46-117">Primary</span><span class="sxs-lookup"><span data-stu-id="5ea46-117">Primary</span></span></p></td>
<td><p><span data-ttu-id="5ea46-118"><a href="lync-server-2013-medialine-table.md">Lync Server 2013 の MediaLine テーブル</a>から参照されます。</span><span class="sxs-lookup"><span data-stu-id="5ea46-118">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5ea46-119"><strong>MediaLineLabel</strong></span><span class="sxs-lookup"><span data-stu-id="5ea46-119"><strong>MediaLineLabel</strong></span></span></p></td>
<td><p><span data-ttu-id="5ea46-120">tinyint</span><span class="sxs-lookup"><span data-stu-id="5ea46-120">tinyint</span></span></p></td>
<td><p><span data-ttu-id="5ea46-121">Primary</span><span class="sxs-lookup"><span data-stu-id="5ea46-121">Primary</span></span></p></td>
<td><p><span data-ttu-id="5ea46-122"><a href="lync-server-2013-medialine-table.md">Lync Server 2013 の MediaLine テーブル</a>から参照されます。</span><span class="sxs-lookup"><span data-stu-id="5ea46-122">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5ea46-123"><strong>FromCaller</strong></span><span class="sxs-lookup"><span data-stu-id="5ea46-123"><strong>FromCaller</strong></span></span></p></td>
<td><p><span data-ttu-id="5ea46-124">若干</span><span class="sxs-lookup"><span data-stu-id="5ea46-124">bit</span></span></p></td>
<td><p><span data-ttu-id="5ea46-125">Primary</span><span class="sxs-lookup"><span data-stu-id="5ea46-125">Primary</span></span></p></td>
<td><p><span data-ttu-id="5ea46-126">0: 呼び出し先のデータ</span><span class="sxs-lookup"><span data-stu-id="5ea46-126">0: Callee’s data</span></span></p>
<p><span data-ttu-id="5ea46-127">1: 発信者のデータ</span><span class="sxs-lookup"><span data-stu-id="5ea46-127">1: Caller’s data</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5ea46-128"><strong>NetworkSendQualityEventRatio</strong></span><span class="sxs-lookup"><span data-stu-id="5ea46-128"><strong>NetworkSendQualityEventRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="5ea46-129">10進数 (5、2)</span><span class="sxs-lookup"><span data-stu-id="5ea46-129">decimal(5,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="5ea46-130">' Bad ' 状態に対して NetworkSendQuality イベントが発生したセッションの割合。</span><span class="sxs-lookup"><span data-stu-id="5ea46-130">Percentage of session the NetworkSendQuality event was fired for ‘Bad’ state.</span></span></p>
<p><span data-ttu-id="5ea46-131">ジッターまたはパケット損失の面でネットワーク品質が深刻で、送信される音声の品質に影響します。</span><span class="sxs-lookup"><span data-stu-id="5ea46-131">Network quality in terms of jitter or packet loss is severe and impacting the quality of audio being sent.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5ea46-132"><strong>NetworkReceiveQualityEventRatio</strong></span><span class="sxs-lookup"><span data-stu-id="5ea46-132"><strong>NetworkReceiveQualityEventRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="5ea46-133">10進数 (5、2)</span><span class="sxs-lookup"><span data-stu-id="5ea46-133">decimal(5,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="5ea46-134">対して receivesendquality イベントが ' Bad ' 状態に対して起動されたセッションの割合。</span><span class="sxs-lookup"><span data-stu-id="5ea46-134">Percentage of session the ReceiveSendQuality event was fired for ‘Bad’ state.</span></span></p>
<p><span data-ttu-id="5ea46-135">ジッターまたはパケット損失の面でネットワーク品質が厳しく、受信する音声の品質に影響します。</span><span class="sxs-lookup"><span data-stu-id="5ea46-135">Network quality in terms of jitter or packet loss is severe and impacting the quality of audio being received.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5ea46-136"><strong>Networkdelayeventrev</strong></span><span class="sxs-lookup"><span data-stu-id="5ea46-136"><strong>NetworkDelayEventRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="5ea46-137">10進数 (5、2)</span><span class="sxs-lookup"><span data-stu-id="5ea46-137">decimal(5,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="5ea46-138">' Bad ' 状態で遅延イベントが発生したセッションの割合。</span><span class="sxs-lookup"><span data-stu-id="5ea46-138">Percentage of session the Delay event was fired for ‘Bad’ state.</span></span> <span data-ttu-id="5ea46-139">ネットワークの遅延が深刻で、対話的なコミュニケーションを妨げることによって、操作が影響を受ける</span><span class="sxs-lookup"><span data-stu-id="5ea46-139">Network latency is severe and impacting the experience by preventing interactive communication</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5ea46-140"><strong>NetworkBandwidthLowEventRatio</strong></span><span class="sxs-lookup"><span data-stu-id="5ea46-140"><strong>NetworkBandwidthLowEventRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="5ea46-141">10進数 (5、2)</span><span class="sxs-lookup"><span data-stu-id="5ea46-141">decimal(5,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="5ea46-142">[セッションの割合] LowBandwidth 幅イベントは、' Bad ' 状態に対して起動されました。</span><span class="sxs-lookup"><span data-stu-id="5ea46-142">Percentage of session the LowBandwidth event was fired for ‘Bad’ state.</span></span> <span data-ttu-id="5ea46-143">使用可能な音声環境に十分な帯域幅がありません。</span><span class="sxs-lookup"><span data-stu-id="5ea46-143">The available bandwidth is insufficient for an acceptable voice experience.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5ea46-144"><strong>CPUInsufficientEventRatio</strong></span><span class="sxs-lookup"><span data-stu-id="5ea46-144"><strong>CPUInsufficientEventRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="5ea46-145">10進数 (5、2)</span><span class="sxs-lookup"><span data-stu-id="5ea46-145">decimal(5,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="5ea46-146">' Bad ' 状態に対して、CPU の不足イベントが発生したセッションの割合。</span><span class="sxs-lookup"><span data-stu-id="5ea46-146">Percentage of session the insufficient CPU event was fired for ‘Bad’ state.</span></span> <span data-ttu-id="5ea46-147">現在使用されているモダリティおよびアプリケーションとの処理に CPU サイクルが不足しています。</span><span class="sxs-lookup"><span data-stu-id="5ea46-147">There are insufficient CPU cycles for processing with the current modalities and applications in use.</span></span> <span data-ttu-id="5ea46-148">これにより、オーディオチャネルとのゆがみが発生します。</span><span class="sxs-lookup"><span data-stu-id="5ea46-148">This causes distortions with the audio channel.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5ea46-149"><strong>DeviceHalfDuplexAECEventRatio</strong></span><span class="sxs-lookup"><span data-stu-id="5ea46-149"><strong>DeviceHalfDuplexAECEventRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="5ea46-150">10進数 (5、2)</span><span class="sxs-lookup"><span data-stu-id="5ea46-150">decimal(5,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="5ea46-151">DeviceHalfDuplexAEC イベントが ' Bad ' 状態に対して起動されたセッションの割合。</span><span class="sxs-lookup"><span data-stu-id="5ea46-151">Percentage of session the DeviceHalfDuplexAEC event was fired for ‘Bad’ state.</span></span> <span data-ttu-id="5ea46-152">エコーを防ぐために、システムは半二重入力します。</span><span class="sxs-lookup"><span data-stu-id="5ea46-152">In order to prevent echo, the system has enter half duplex.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5ea46-153"><strong>Devicerendernotfunctioningeventrev</strong></span><span class="sxs-lookup"><span data-stu-id="5ea46-153"><strong>DeviceRenderNotFunctioningEventRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="5ea46-154">10進数 (5、2)</span><span class="sxs-lookup"><span data-stu-id="5ea46-154">decimal(5,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="5ea46-155">' Bad ' 状態に対して DeviceRenderNotFunctioning イベントが発生したセッションの割合。</span><span class="sxs-lookup"><span data-stu-id="5ea46-155">Percentage of session the DeviceRenderNotFunctioning event was fired for ‘Bad’ state.</span></span> <span data-ttu-id="5ea46-156">セッションで現在使用されているレンダーデバイスが正しく機能していません。</span><span class="sxs-lookup"><span data-stu-id="5ea46-156">The render device currently being used for the session is not functioning correctly.</span></span> <span data-ttu-id="5ea46-157">これにより、1ウェイの音声の問題が発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="5ea46-157">This can cause one-way audio issues.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5ea46-158"><strong>Devicecapturenotfunctioningeventrev</strong></span><span class="sxs-lookup"><span data-stu-id="5ea46-158"><strong>DeviceCaptureNotFunctioningEventRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="5ea46-159">10進数 (5、2)</span><span class="sxs-lookup"><span data-stu-id="5ea46-159">decimal(5,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="5ea46-160">' Bad ' 状態に対して DeviceCaptureNotFunctioning イベントが発生したセッションの割合。</span><span class="sxs-lookup"><span data-stu-id="5ea46-160">Percentage of session the DeviceCaptureNotFunctioning event was fired for ‘Bad’ state.</span></span> <span data-ttu-id="5ea46-161">セッションで現在使用されているキャプチャデバイスが正しく機能していません。</span><span class="sxs-lookup"><span data-stu-id="5ea46-161">The capture device currently being used for the session is not functioning correctly.</span></span> <span data-ttu-id="5ea46-162">これにより、1ウェイの音声の問題が発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="5ea46-162">This can cause one-way audio issues.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5ea46-163"><strong>DeviceGlitchesEventRatio</strong></span><span class="sxs-lookup"><span data-stu-id="5ea46-163"><strong>DeviceGlitchesEventRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="5ea46-164">10進数 (5、2)</span><span class="sxs-lookup"><span data-stu-id="5ea46-164">decimal(5,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="5ea46-165">' Bad ' 状態で DeviceGlitches イベントが発生したセッションの割合。</span><span class="sxs-lookup"><span data-stu-id="5ea46-165">Percentage of session the DeviceGlitches event was fired for ‘Bad’ state.</span></span> <span data-ttu-id="5ea46-166">ひずみが発生している音声のレンダリングに重大な問題があります。</span><span class="sxs-lookup"><span data-stu-id="5ea46-166">There are severe glitches in the rendering of audio which is causing distortions.</span></span> <span data-ttu-id="5ea46-167">これらの問題は、ドライバーの問題、遅延プロシージャ呼び出し (DPC) ストーム (ドライバー)、CPU 使用率が高いことが原因で発生することがあります。</span><span class="sxs-lookup"><span data-stu-id="5ea46-167">These glitches can be caused by driver issues, deferred procedure calls (DPC) storm (drivers), and high CPU usage.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5ea46-168"><strong>DeviceLowSNREventRatio</strong></span><span class="sxs-lookup"><span data-stu-id="5ea46-168"><strong>DeviceLowSNREventRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="5ea46-169">10進数 (5、2)</span><span class="sxs-lookup"><span data-stu-id="5ea46-169">decimal(5,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="5ea46-170">' Bad ' 状態に対して DeviceLowSNR イベントが発生したセッションの割合。</span><span class="sxs-lookup"><span data-stu-id="5ea46-170">Percentage of session the DeviceLowSNR event was fired for ‘Bad’ state.</span></span> <span data-ttu-id="5ea46-171">キャプチャ品質が非常に低い。雑音が多いか、ユーザーがマイクから離れすぎている。</span><span class="sxs-lookup"><span data-stu-id="5ea46-171">The capture quality is very poor, either very noisy or user is talking too far away from the microphone.</span></span> <span data-ttu-id="5ea46-172">これにより、ゆがみが発生します。</span><span class="sxs-lookup"><span data-stu-id="5ea46-172">This will cause distortions.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5ea46-173"><strong>DeviceLowSpeechLevelEventRatio</strong></span><span class="sxs-lookup"><span data-stu-id="5ea46-173"><strong>DeviceLowSpeechLevelEventRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="5ea46-174">10進数 (5、2)</span><span class="sxs-lookup"><span data-stu-id="5ea46-174">decimal(5,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="5ea46-175">DeviceLowSpeechLevel イベントが ' Bad ' 状態に対して起動されたセッションの割合。</span><span class="sxs-lookup"><span data-stu-id="5ea46-175">Percentage of session the DeviceLowSpeechLevel event was fired for ‘Bad’ state.</span></span> <span data-ttu-id="5ea46-176">ユーザーの音声レベルが低すぎるため、システムがこれ以上の機能を向上させることはできません。</span><span class="sxs-lookup"><span data-stu-id="5ea46-176">User‘s speech level is too low and the system cannot increase it any further.</span></span> <span data-ttu-id="5ea46-177">これにより、ゆがみが一通行の音声として認識されることがあります。</span><span class="sxs-lookup"><span data-stu-id="5ea46-177">This can either cause distortions or perceived as one-way audio.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5ea46-178"><strong>DeviceClippingEventRatio</strong></span><span class="sxs-lookup"><span data-stu-id="5ea46-178"><strong>DeviceClippingEventRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="5ea46-179">10進数 (5、2)</span><span class="sxs-lookup"><span data-stu-id="5ea46-179">Decimal(5,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="5ea46-180">対して deviceclipping イベントが ' Bad ' 状態に対して起動されたセッションの割合。</span><span class="sxs-lookup"><span data-stu-id="5ea46-180">Percentage of session the DeviceClipping event was fired for ‘Bad’ state.</span></span></p>
<p><span data-ttu-id="5ea46-181">ニアエンド音声によってマイクがクリップされると、遠方でクリッピングが発生することがあります。</span><span class="sxs-lookup"><span data-stu-id="5ea46-181">When near-end speech clips the microphone, far-end hears distortion due to clipping.</span></span> <span data-ttu-id="5ea46-182">ニアエンドマイクのクリッピングを回避することが重要です。</span><span class="sxs-lookup"><span data-stu-id="5ea46-182">It is important to avoid near-end microphone clipping.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5ea46-183"><strong>DeviceEchoEventRatio</strong></span><span class="sxs-lookup"><span data-stu-id="5ea46-183"><strong>DeviceEchoEventRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="5ea46-184">10進数 (5、2)</span><span class="sxs-lookup"><span data-stu-id="5ea46-184">decimal(5,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="5ea46-185">Deviceechoevent が生じイベントが ' Bad ' 状態に対して起動されたセッションの割合。</span><span class="sxs-lookup"><span data-stu-id="5ea46-185">Percentage of session the DeviceEchoEvent event was fired for ‘Bad’ state.</span></span> <span data-ttu-id="5ea46-186">デバイスまたはセットアップによって、システムの機能を超えるエコーが発生しています。</span><span class="sxs-lookup"><span data-stu-id="5ea46-186">Device or setup is causing echo beyond the ability of the system to compensate.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5ea46-187"><strong>Devicenん endtoo/exceloeventrev</strong></span><span class="sxs-lookup"><span data-stu-id="5ea46-187"><strong>DeviceNearEndToEchoRatioEventRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="5ea46-188">10進数 (5、2)</span><span class="sxs-lookup"><span data-stu-id="5ea46-188">decimal(5,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="5ea46-189">' Bad ' 状態に対して、Devicen/Endto///のイベントが発生したセッションの割合。</span><span class="sxs-lookup"><span data-stu-id="5ea46-189">Percentage of session the DeviceNearEndToEchoRatio event was fired for ‘Bad’ state.</span></span> <span data-ttu-id="5ea46-190">ユーザーの音声が小さすぎる場合は、キャプチャしたエコーと比較して、ユーザーが簡単に中断できることを制限するため、ユーザーの操作に影響を及ぼします。</span><span class="sxs-lookup"><span data-stu-id="5ea46-190">The user’s speech is too low compared to the echo being captured which impacts the users experience because it limits how easy it is to interrupt a user.</span></span> <span data-ttu-id="5ea46-191">スピーカー音量を下げるには、マイクをトーカーの近くに動かします。</span><span class="sxs-lookup"><span data-stu-id="5ea46-191">Reduce speaker volume, move the microphone closer to the talker.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5ea46-192"><strong>DeviceMultipleEndpointsEventCount</strong></span><span class="sxs-lookup"><span data-stu-id="5ea46-192"><strong>DeviceMultipleEndpointsEventCount</strong></span></span></p></td>
<td><p><span data-ttu-id="5ea46-193">int</span><span class="sxs-lookup"><span data-stu-id="5ea46-193">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="5ea46-194">セッション中の DeviceMultipleEndpoints イベントが ' Bad ' 状態に対して起動された回数。</span><span class="sxs-lookup"><span data-stu-id="5ea46-194">Number of times during session the DeviceMultipleEndpoints event was fired for ‘Bad’ state.</span></span> <span data-ttu-id="5ea46-195">同じセッションで複数のオーディオエンドポイントが検出され、描画ボリュームが減少することにより、システムが補償しています。</span><span class="sxs-lookup"><span data-stu-id="5ea46-195">Multiple audio endpoints in the same session detected and the system has compensated by reducing render volume.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5ea46-196"><strong>Devicecount/Eventcount</strong></span><span class="sxs-lookup"><span data-stu-id="5ea46-196"><strong>DeviceHowlingEventCount</strong></span></span></p></td>
<td><p><span data-ttu-id="5ea46-197">int</span><span class="sxs-lookup"><span data-stu-id="5ea46-197">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="5ea46-198">セッション中に発生した回数。 ' Bad ' 状態で Deviceの状態イベントイベントが発生しました。</span><span class="sxs-lookup"><span data-stu-id="5ea46-198">Number of times during session the DeviceHowlingEvent event was fired for ‘Bad’ state.</span></span> <span data-ttu-id="5ea46-199">検出された音声フィードバックループ (複数のエンドポイントがオーディオパスを共有したことが原因)。</span><span class="sxs-lookup"><span data-stu-id="5ea46-199">Audio feedback loop detected (caused by multiple endpoints sharing audio path).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5ea46-200"><strong>Devicerenderゼロの volumeeventr</strong></span><span class="sxs-lookup"><span data-stu-id="5ea46-200"><strong>DeviceRenderZeroVolumeEventRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="5ea46-201">10進数 (5、2)</span><span class="sxs-lookup"><span data-stu-id="5ea46-201">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="5ea46-202">"Bad" 状態になっているために、Devicerenderゼロボリュームイベントが発生したセッションの割合。</span><span class="sxs-lookup"><span data-stu-id="5ea46-202">Percentage of session the DeviceRenderZeroVolume event was fired for being in the “Bad’ state.</span></span> <span data-ttu-id="5ea46-203">レンダーデバイスがボリューム0に設定されています。</span><span class="sxs-lookup"><span data-stu-id="5ea46-203">The render device was set to zero volume.</span></span></p>
<p><span data-ttu-id="5ea46-204">このコラムは、Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="5ea46-204">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5ea46-205"><strong>DeviceRenderMuteEventRatio スペック)</strong></span><span class="sxs-lookup"><span data-stu-id="5ea46-205"><strong>DeviceRenderMuteEventRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="5ea46-206">10進数 (5、2)</span><span class="sxs-lookup"><span data-stu-id="5ea46-206">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="5ea46-207">"Bad" 状態であるために、DeviceRenderMute イベントが発生したセッションの割合。</span><span class="sxs-lookup"><span data-stu-id="5ea46-207">Percentage of session the DeviceRenderMute event was fired for being in the “Bad’ state.</span></span> <span data-ttu-id="5ea46-208">レンダーデバイスがミュートされました。</span><span class="sxs-lookup"><span data-stu-id="5ea46-208">The render device was muted.</span></span></p>
<p><span data-ttu-id="5ea46-209">このコラムは、Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="5ea46-209">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

