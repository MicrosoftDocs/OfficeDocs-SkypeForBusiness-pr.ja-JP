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
ms.openlocfilehash: 53f43bdae2fd134e851c93be958aa671657489e1
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2020
ms.locfileid: "42044599"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="audioclientevent-table-in-lync-server-2013"></a><span data-ttu-id="21896-102">Lync Server 2013 の AudioClientEvent テーブル</span><span class="sxs-lookup"><span data-stu-id="21896-102">AudioClientEvent table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="21896-103">_**トピックの最終更新日:** 2012-10-17_</span><span class="sxs-lookup"><span data-stu-id="21896-103">_**Topic Last Modified:** 2012-10-17_</span></span>

<span data-ttu-id="21896-104">各レコードには、音声通話の1つのエンドポイントのクライアントイベントが含まれています。</span><span class="sxs-lookup"><span data-stu-id="21896-104">Each record contains a client event for one endpoint in an audio call.</span></span> <span data-ttu-id="21896-105">通常、1つの呼び出しには2つのレコードがあり、1つは呼び出し元用、もう1つは呼び出し先用です。</span><span class="sxs-lookup"><span data-stu-id="21896-105">Usually, one call has two records, one for caller and one for callee.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="21896-106"><strong>列</strong></span><span class="sxs-lookup"><span data-stu-id="21896-106"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="21896-107"><strong>データ型</strong></span><span class="sxs-lookup"><span data-stu-id="21896-107"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="21896-108"><strong>キー/インデックス</strong></span><span class="sxs-lookup"><span data-stu-id="21896-108"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="21896-109"><strong>詳細</strong></span><span class="sxs-lookup"><span data-stu-id="21896-109"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="21896-110"><strong>ConferenceDateTime</strong></span><span class="sxs-lookup"><span data-stu-id="21896-110"><strong>ConferenceDateTime</strong></span></span></p></td>
<td><p><span data-ttu-id="21896-111">日付型</span><span class="sxs-lookup"><span data-stu-id="21896-111">datetime</span></span></p></td>
<td><p><span data-ttu-id="21896-112">Primary</span><span class="sxs-lookup"><span data-stu-id="21896-112">Primary</span></span></p></td>
<td><p><span data-ttu-id="21896-113"><a href="lync-server-2013-medialine-table.md">Lync Server 2013 の MediaLine テーブル</a>から参照されます。</span><span class="sxs-lookup"><span data-stu-id="21896-113">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="21896-114"><strong>SessionSeq</strong></span><span class="sxs-lookup"><span data-stu-id="21896-114"><strong>SessionSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="21896-115">int</span><span class="sxs-lookup"><span data-stu-id="21896-115">int</span></span></p></td>
<td><p><span data-ttu-id="21896-116">Primary</span><span class="sxs-lookup"><span data-stu-id="21896-116">Primary</span></span></p></td>
<td><p><span data-ttu-id="21896-117"><a href="lync-server-2013-medialine-table.md">Lync Server 2013 の MediaLine テーブル</a>から参照されます。</span><span class="sxs-lookup"><span data-stu-id="21896-117">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="21896-118"><strong>MediaLineLabel</strong></span><span class="sxs-lookup"><span data-stu-id="21896-118"><strong>MediaLineLabel</strong></span></span></p></td>
<td><p><span data-ttu-id="21896-119">tinyint</span><span class="sxs-lookup"><span data-stu-id="21896-119">tinyint</span></span></p></td>
<td><p><span data-ttu-id="21896-120">Primary</span><span class="sxs-lookup"><span data-stu-id="21896-120">Primary</span></span></p></td>
<td><p><span data-ttu-id="21896-121"><a href="lync-server-2013-medialine-table.md">Lync Server 2013 の MediaLine テーブル</a>から参照されます。</span><span class="sxs-lookup"><span data-stu-id="21896-121">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="21896-122"><strong>FromCaller</strong></span><span class="sxs-lookup"><span data-stu-id="21896-122"><strong>FromCaller</strong></span></span></p></td>
<td><p><span data-ttu-id="21896-123">若干</span><span class="sxs-lookup"><span data-stu-id="21896-123">bit</span></span></p></td>
<td><p><span data-ttu-id="21896-124">Primary</span><span class="sxs-lookup"><span data-stu-id="21896-124">Primary</span></span></p></td>
<td><p><span data-ttu-id="21896-125">0: 呼び出し先のデータ</span><span class="sxs-lookup"><span data-stu-id="21896-125">0: Callee’s data</span></span></p>
<p><span data-ttu-id="21896-126">1: 発信者のデータ</span><span class="sxs-lookup"><span data-stu-id="21896-126">1: Caller’s data</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="21896-127"><strong>NetworkSendQualityEventRatio</strong></span><span class="sxs-lookup"><span data-stu-id="21896-127"><strong>NetworkSendQualityEventRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="21896-128">10進数 (5、2)</span><span class="sxs-lookup"><span data-stu-id="21896-128">decimal(5,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="21896-129">' Bad ' 状態に対して NetworkSendQuality イベントが発生したセッションの割合。</span><span class="sxs-lookup"><span data-stu-id="21896-129">Percentage of session the NetworkSendQuality event was fired for ‘Bad’ state.</span></span></p>
<p><span data-ttu-id="21896-130">ジッターまたはパケット損失の面でネットワーク品質が深刻で、送信される音声の品質に影響します。</span><span class="sxs-lookup"><span data-stu-id="21896-130">Network quality in terms of jitter or packet loss is severe and impacting the quality of audio being sent.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="21896-131"><strong>NetworkReceiveQualityEventRatio</strong></span><span class="sxs-lookup"><span data-stu-id="21896-131"><strong>NetworkReceiveQualityEventRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="21896-132">10進数 (5、2)</span><span class="sxs-lookup"><span data-stu-id="21896-132">decimal(5,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="21896-133">対して receivesendquality イベントが ' Bad ' 状態に対して起動されたセッションの割合。</span><span class="sxs-lookup"><span data-stu-id="21896-133">Percentage of session the ReceiveSendQuality event was fired for ‘Bad’ state.</span></span></p>
<p><span data-ttu-id="21896-134">ジッターまたはパケット損失の面でネットワーク品質が厳しく、受信する音声の品質に影響します。</span><span class="sxs-lookup"><span data-stu-id="21896-134">Network quality in terms of jitter or packet loss is severe and impacting the quality of audio being received.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="21896-135"><strong>Networkdelayeventrev</strong></span><span class="sxs-lookup"><span data-stu-id="21896-135"><strong>NetworkDelayEventRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="21896-136">10進数 (5、2)</span><span class="sxs-lookup"><span data-stu-id="21896-136">decimal(5,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="21896-137">' Bad ' 状態で遅延イベントが発生したセッションの割合。</span><span class="sxs-lookup"><span data-stu-id="21896-137">Percentage of session the Delay event was fired for ‘Bad’ state.</span></span> <span data-ttu-id="21896-138">ネットワークの遅延が深刻で、対話的なコミュニケーションを妨げることによって、操作が影響を受ける</span><span class="sxs-lookup"><span data-stu-id="21896-138">Network latency is severe and impacting the experience by preventing interactive communication</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="21896-139"><strong>NetworkBandwidthLowEventRatio</strong></span><span class="sxs-lookup"><span data-stu-id="21896-139"><strong>NetworkBandwidthLowEventRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="21896-140">10進数 (5、2)</span><span class="sxs-lookup"><span data-stu-id="21896-140">decimal(5,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="21896-141">[セッションの割合] LowBandwidth 幅イベントは、' Bad ' 状態に対して起動されました。</span><span class="sxs-lookup"><span data-stu-id="21896-141">Percentage of session the LowBandwidth event was fired for ‘Bad’ state.</span></span> <span data-ttu-id="21896-142">使用可能な音声環境に十分な帯域幅がありません。</span><span class="sxs-lookup"><span data-stu-id="21896-142">The available bandwidth is insufficient for an acceptable voice experience.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="21896-143"><strong>CPUInsufficientEventRatio</strong></span><span class="sxs-lookup"><span data-stu-id="21896-143"><strong>CPUInsufficientEventRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="21896-144">10進数 (5、2)</span><span class="sxs-lookup"><span data-stu-id="21896-144">decimal(5,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="21896-145">' Bad ' 状態に対して、CPU の不足イベントが発生したセッションの割合。</span><span class="sxs-lookup"><span data-stu-id="21896-145">Percentage of session the insufficient CPU event was fired for ‘Bad’ state.</span></span> <span data-ttu-id="21896-146">現在使用されているモダリティおよびアプリケーションとの処理に CPU サイクルが不足しています。</span><span class="sxs-lookup"><span data-stu-id="21896-146">There are insufficient CPU cycles for processing with the current modalities and applications in use.</span></span> <span data-ttu-id="21896-147">これにより、オーディオチャネルとのゆがみが発生します。</span><span class="sxs-lookup"><span data-stu-id="21896-147">This causes distortions with the audio channel.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="21896-148"><strong>DeviceHalfDuplexAECEventRatio</strong></span><span class="sxs-lookup"><span data-stu-id="21896-148"><strong>DeviceHalfDuplexAECEventRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="21896-149">10進数 (5、2)</span><span class="sxs-lookup"><span data-stu-id="21896-149">decimal(5,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="21896-150">DeviceHalfDuplexAEC イベントが ' Bad ' 状態に対して起動されたセッションの割合。</span><span class="sxs-lookup"><span data-stu-id="21896-150">Percentage of session the DeviceHalfDuplexAEC event was fired for ‘Bad’ state.</span></span> <span data-ttu-id="21896-151">エコーを防ぐために、システムは半二重入力します。</span><span class="sxs-lookup"><span data-stu-id="21896-151">In order to prevent echo, the system has enter half duplex.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="21896-152"><strong>Devicerendernotfunctioningeventrev</strong></span><span class="sxs-lookup"><span data-stu-id="21896-152"><strong>DeviceRenderNotFunctioningEventRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="21896-153">10進数 (5、2)</span><span class="sxs-lookup"><span data-stu-id="21896-153">decimal(5,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="21896-154">' Bad ' 状態に対して DeviceRenderNotFunctioning イベントが発生したセッションの割合。</span><span class="sxs-lookup"><span data-stu-id="21896-154">Percentage of session the DeviceRenderNotFunctioning event was fired for ‘Bad’ state.</span></span> <span data-ttu-id="21896-155">セッションで現在使用されているレンダーデバイスが正しく機能していません。</span><span class="sxs-lookup"><span data-stu-id="21896-155">The render device currently being used for the session is not functioning correctly.</span></span> <span data-ttu-id="21896-156">これにより、1ウェイの音声の問題が発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="21896-156">This can cause one-way audio issues.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="21896-157"><strong>Devicecapturenotfunctioningeventrev</strong></span><span class="sxs-lookup"><span data-stu-id="21896-157"><strong>DeviceCaptureNotFunctioningEventRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="21896-158">10進数 (5、2)</span><span class="sxs-lookup"><span data-stu-id="21896-158">decimal(5,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="21896-159">' Bad ' 状態に対して DeviceCaptureNotFunctioning イベントが発生したセッションの割合。</span><span class="sxs-lookup"><span data-stu-id="21896-159">Percentage of session the DeviceCaptureNotFunctioning event was fired for ‘Bad’ state.</span></span> <span data-ttu-id="21896-160">セッションで現在使用されているキャプチャデバイスが正しく機能していません。</span><span class="sxs-lookup"><span data-stu-id="21896-160">The capture device currently being used for the session is not functioning correctly.</span></span> <span data-ttu-id="21896-161">これにより、1ウェイの音声の問題が発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="21896-161">This can cause one-way audio issues.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="21896-162"><strong>DeviceGlitchesEventRatio</strong></span><span class="sxs-lookup"><span data-stu-id="21896-162"><strong>DeviceGlitchesEventRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="21896-163">10進数 (5、2)</span><span class="sxs-lookup"><span data-stu-id="21896-163">decimal(5,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="21896-164">' Bad ' 状態で DeviceGlitches イベントが発生したセッションの割合。</span><span class="sxs-lookup"><span data-stu-id="21896-164">Percentage of session the DeviceGlitches event was fired for ‘Bad’ state.</span></span> <span data-ttu-id="21896-165">ひずみが発生している音声のレンダリングに重大な問題があります。</span><span class="sxs-lookup"><span data-stu-id="21896-165">There are severe glitches in the rendering of audio which is causing distortions.</span></span> <span data-ttu-id="21896-166">これらの問題は、ドライバーの問題、遅延プロシージャ呼び出し (DPC) ストーム (ドライバー)、CPU 使用率が高いことが原因で発生することがあります。</span><span class="sxs-lookup"><span data-stu-id="21896-166">These glitches can be caused by driver issues, deferred procedure calls (DPC) storm (drivers), and high CPU usage.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="21896-167"><strong>DeviceLowSNREventRatio</strong></span><span class="sxs-lookup"><span data-stu-id="21896-167"><strong>DeviceLowSNREventRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="21896-168">10進数 (5、2)</span><span class="sxs-lookup"><span data-stu-id="21896-168">decimal(5,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="21896-169">' Bad ' 状態に対して DeviceLowSNR イベントが発生したセッションの割合。</span><span class="sxs-lookup"><span data-stu-id="21896-169">Percentage of session the DeviceLowSNR event was fired for ‘Bad’ state.</span></span> <span data-ttu-id="21896-170">キャプチャ品質が非常に低い。雑音が多いか、ユーザーがマイクから離れすぎている。</span><span class="sxs-lookup"><span data-stu-id="21896-170">The capture quality is very poor, either very noisy or user is talking too far away from the microphone.</span></span> <span data-ttu-id="21896-171">これにより、ゆがみが発生します。</span><span class="sxs-lookup"><span data-stu-id="21896-171">This will cause distortions.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="21896-172"><strong>DeviceLowSpeechLevelEventRatio</strong></span><span class="sxs-lookup"><span data-stu-id="21896-172"><strong>DeviceLowSpeechLevelEventRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="21896-173">10進数 (5、2)</span><span class="sxs-lookup"><span data-stu-id="21896-173">decimal(5,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="21896-174">DeviceLowSpeechLevel イベントが ' Bad ' 状態に対して起動されたセッションの割合。</span><span class="sxs-lookup"><span data-stu-id="21896-174">Percentage of session the DeviceLowSpeechLevel event was fired for ‘Bad’ state.</span></span> <span data-ttu-id="21896-175">ユーザーの音声レベルが低すぎるため、システムがこれ以上の機能を向上させることはできません。</span><span class="sxs-lookup"><span data-stu-id="21896-175">User‘s speech level is too low and the system cannot increase it any further.</span></span> <span data-ttu-id="21896-176">これにより、ゆがみが一通行の音声として認識されることがあります。</span><span class="sxs-lookup"><span data-stu-id="21896-176">This can either cause distortions or perceived as one-way audio.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="21896-177"><strong>DeviceClippingEventRatio</strong></span><span class="sxs-lookup"><span data-stu-id="21896-177"><strong>DeviceClippingEventRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="21896-178">10進数 (5、2)</span><span class="sxs-lookup"><span data-stu-id="21896-178">Decimal(5,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="21896-179">対して deviceclipping イベントが ' Bad ' 状態に対して起動されたセッションの割合。</span><span class="sxs-lookup"><span data-stu-id="21896-179">Percentage of session the DeviceClipping event was fired for ‘Bad’ state.</span></span></p>
<p><span data-ttu-id="21896-180">ニアエンド音声によってマイクがクリップされると、遠方でクリッピングが発生することがあります。</span><span class="sxs-lookup"><span data-stu-id="21896-180">When near-end speech clips the microphone, far-end hears distortion due to clipping.</span></span> <span data-ttu-id="21896-181">ニアエンドマイクのクリッピングを回避することが重要です。</span><span class="sxs-lookup"><span data-stu-id="21896-181">It is important to avoid near-end microphone clipping.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="21896-182"><strong>DeviceEchoEventRatio</strong></span><span class="sxs-lookup"><span data-stu-id="21896-182"><strong>DeviceEchoEventRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="21896-183">10進数 (5、2)</span><span class="sxs-lookup"><span data-stu-id="21896-183">decimal(5,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="21896-184">Deviceechoevent が生じイベントが ' Bad ' 状態に対して起動されたセッションの割合。</span><span class="sxs-lookup"><span data-stu-id="21896-184">Percentage of session the DeviceEchoEvent event was fired for ‘Bad’ state.</span></span> <span data-ttu-id="21896-185">デバイスまたはセットアップによって、システムの機能を超えるエコーが発生しています。</span><span class="sxs-lookup"><span data-stu-id="21896-185">Device or setup is causing echo beyond the ability of the system to compensate.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="21896-186"><strong>Devicenん endtoo/exceloeventrev</strong></span><span class="sxs-lookup"><span data-stu-id="21896-186"><strong>DeviceNearEndToEchoRatioEventRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="21896-187">10進数 (5、2)</span><span class="sxs-lookup"><span data-stu-id="21896-187">decimal(5,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="21896-188">' Bad ' 状態に対して、Devicen/Endto///のイベントが発生したセッションの割合。</span><span class="sxs-lookup"><span data-stu-id="21896-188">Percentage of session the DeviceNearEndToEchoRatio event was fired for ‘Bad’ state.</span></span> <span data-ttu-id="21896-189">ユーザーの音声が小さすぎる場合は、キャプチャしたエコーと比較して、ユーザーが簡単に中断できることを制限するため、ユーザーの操作に影響を及ぼします。</span><span class="sxs-lookup"><span data-stu-id="21896-189">The user’s speech is too low compared to the echo being captured which impacts the users experience because it limits how easy it is to interrupt a user.</span></span> <span data-ttu-id="21896-190">スピーカー音量を下げるには、マイクをトーカーの近くに動かします。</span><span class="sxs-lookup"><span data-stu-id="21896-190">Reduce speaker volume, move the microphone closer to the talker.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="21896-191"><strong>DeviceMultipleEndpointsEventCount</strong></span><span class="sxs-lookup"><span data-stu-id="21896-191"><strong>DeviceMultipleEndpointsEventCount</strong></span></span></p></td>
<td><p><span data-ttu-id="21896-192">int</span><span class="sxs-lookup"><span data-stu-id="21896-192">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="21896-193">セッション中の DeviceMultipleEndpoints イベントが ' Bad ' 状態に対して起動された回数。</span><span class="sxs-lookup"><span data-stu-id="21896-193">Number of times during session the DeviceMultipleEndpoints event was fired for ‘Bad’ state.</span></span> <span data-ttu-id="21896-194">同じセッションで複数のオーディオエンドポイントが検出され、描画ボリュームが減少することにより、システムが補償しています。</span><span class="sxs-lookup"><span data-stu-id="21896-194">Multiple audio endpoints in the same session detected and the system has compensated by reducing render volume.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="21896-195"><strong>Devicecount/Eventcount</strong></span><span class="sxs-lookup"><span data-stu-id="21896-195"><strong>DeviceHowlingEventCount</strong></span></span></p></td>
<td><p><span data-ttu-id="21896-196">int</span><span class="sxs-lookup"><span data-stu-id="21896-196">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="21896-197">セッション中に発生した回数。 ' Bad ' 状態で Deviceの状態イベントイベントが発生しました。</span><span class="sxs-lookup"><span data-stu-id="21896-197">Number of times during session the DeviceHowlingEvent event was fired for ‘Bad’ state.</span></span> <span data-ttu-id="21896-198">検出された音声フィードバックループ (複数のエンドポイントがオーディオパスを共有したことが原因)。</span><span class="sxs-lookup"><span data-stu-id="21896-198">Audio feedback loop detected (caused by multiple endpoints sharing audio path).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="21896-199"><strong>Devicerenderゼロの volumeeventr</strong></span><span class="sxs-lookup"><span data-stu-id="21896-199"><strong>DeviceRenderZeroVolumeEventRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="21896-200">10進数 (5、2)</span><span class="sxs-lookup"><span data-stu-id="21896-200">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="21896-201">"Bad" 状態になっているために、Devicerenderゼロボリュームイベントが発生したセッションの割合。</span><span class="sxs-lookup"><span data-stu-id="21896-201">Percentage of session the DeviceRenderZeroVolume event was fired for being in the “Bad’ state.</span></span> <span data-ttu-id="21896-202">レンダーデバイスがボリューム0に設定されています。</span><span class="sxs-lookup"><span data-stu-id="21896-202">The render device was set to zero volume.</span></span></p>
<p><span data-ttu-id="21896-203">このコラムは、Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="21896-203">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="21896-204"><strong>DeviceRenderMuteEventRatio スペック)</strong></span><span class="sxs-lookup"><span data-stu-id="21896-204"><strong>DeviceRenderMuteEventRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="21896-205">10進数 (5、2)</span><span class="sxs-lookup"><span data-stu-id="21896-205">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="21896-206">"Bad" 状態であるために、DeviceRenderMute イベントが発生したセッションの割合。</span><span class="sxs-lookup"><span data-stu-id="21896-206">Percentage of session the DeviceRenderMute event was fired for being in the “Bad’ state.</span></span> <span data-ttu-id="21896-207">レンダーデバイスがミュートされました。</span><span class="sxs-lookup"><span data-stu-id="21896-207">The render device was muted.</span></span></p>
<p><span data-ttu-id="21896-208">このコラムは、Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="21896-208">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

