---
title: Skype for Business Server の通話詳細レポート
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 38862e35-3fec-41b9-a035-0b301942d446
description: '概要: Skype for Business Server で使用される通話詳細レポートについて説明します。'
ms.openlocfilehash: 9b02722c8dd872b5703d6b459c2cd48568e39f94
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49826517"
---
# <a name="call-detail-report-in-skype-for-business-server"></a><span data-ttu-id="11351-103">Skype for Business Server の通話詳細レポート</span><span class="sxs-lookup"><span data-stu-id="11351-103">Call Detail Report in Skype for Business Server</span></span>
 
<span data-ttu-id="11351-104">**概要:** Skype for Business Server で使用される通話詳細レポートについて説明します。</span><span class="sxs-lookup"><span data-stu-id="11351-104">**Summary:** Learn about the Call Detail Report used in Skype for Business Server.</span></span>
  
<span data-ttu-id="11351-105">通話詳細レポートでは、個々の通話の詳細を確認できます。このレポートには、Skype for Business Server によって収集された、ほぼすべての Quality of Experience 指標と統計情報が含まれます。次のようなレポート セクションに分かれています。</span><span class="sxs-lookup"><span data-stu-id="11351-105">The Call Detail Report provides a detailed look at an individual call; the report includes nearly all the Quality of Experience metrics and statistics collected by Skype for Business Server, divided into report sections such as:</span></span>
  
- <span data-ttu-id="11351-106">通話情報</span><span class="sxs-lookup"><span data-stu-id="11351-106">Call Information</span></span> 
    
- <span data-ttu-id="11351-107">発信者デバイスと信号測定値</span><span class="sxs-lookup"><span data-stu-id="11351-107">Caller Device and Signal Metrics</span></span>
    
- <span data-ttu-id="11351-108">呼び出し先デバイスと信号測定値</span><span class="sxs-lookup"><span data-stu-id="11351-108">Callee Device and Signal metrics</span></span>
    
- <span data-ttu-id="11351-109">発信者クライアント イベント</span><span class="sxs-lookup"><span data-stu-id="11351-109">Caller Client Event</span></span>
    
- <span data-ttu-id="11351-110">呼び出し先クライアント イベント</span><span class="sxs-lookup"><span data-stu-id="11351-110">Callee Client Event</span></span>
    
- <span data-ttu-id="11351-111">音声ストリーム (発信者から呼び出し先)</span><span class="sxs-lookup"><span data-stu-id="11351-111">Audio Stream (Caller to Callee)</span></span>
    
- <span data-ttu-id="11351-112">ビデオ ストリーム (発信者から呼び出し先)</span><span class="sxs-lookup"><span data-stu-id="11351-112">Video Stream (Caller to Callee)</span></span>
    
- <span data-ttu-id="11351-113">音声ストリーム (呼び出し先から発信者)</span><span class="sxs-lookup"><span data-stu-id="11351-113">Audio Stream (Callee to Caller)</span></span>
    
- <span data-ttu-id="11351-114">ビデオ ストリーム (呼び出し先から発信者)</span><span class="sxs-lookup"><span data-stu-id="11351-114">Video Stream (Callee to Caller)</span></span>
    
<span data-ttu-id="11351-p101">特定のレポートに表示されるカテゴリと測定値は、セッションの種類と、セッションで使用されたエンドポイントの種類に依存します。たとえば、音声のみの通話では、通話にビデオ ストリームがないことにより、ビデオ ストリームの測定値を報告されません。同様に、呼び出し先統計はないが、発信者統計を示すレポートがあることがあります。これは、一般的には、呼び出し先が SIP 準拠のデバイスを使用していなかったことによります。エンドポイントは通話の終了後に、統計を報告します。しかし、(SIP または SIP 統計を関知しない) 携帯電話は、その種類の情報を報告することはできません。だれかに電話して、その人が携帯電話で応答した場合は、通話が終了したときに、その携帯電話からのレポートは得られません。</span><span class="sxs-lookup"><span data-stu-id="11351-p101">Keep in mind that the categories and the metrics you see on a given report depend on two things: the type of session and the type of endpoints used in the session. For example, an audio-only call will not report metrics for video streams; that's because the call didn't have a video stream. Likewise, you might have a report that lists caller statistics but not callee statistics. That's typically because the callee was not using a SIP-compliant device. Endpoints are responsible for reporting statistics at the end of a call; however, a cell phone (which knows nothing about SIP or SIP statistics) is unable to report that kind of information. If you call someone and they answer you on their cell phone, you will not get a report from that cell phone when the call ends.</span></span>
  
<span data-ttu-id="11351-121">通話の詳細レポートは、特定の通話でメディアの品質の問題が発生した理由を正確に確認するときに最も役立ちます。</span><span class="sxs-lookup"><span data-stu-id="11351-121">The Call Detail Report is most useful when you are trying to determine exactly why a given call experienced media quality problems.</span></span>
  
## <a name="accessing-the-call-detail-report"></a><span data-ttu-id="11351-122">通話の詳細レポートを表示する</span><span class="sxs-lookup"><span data-stu-id="11351-122">Accessing the Call Detail Report</span></span>

<span data-ttu-id="11351-123">通話の詳細レポートは、以下の任意のレポートから表示できます。</span><span class="sxs-lookup"><span data-stu-id="11351-123">The Call Detail Report can be accessed from any of the following reports:</span></span>
  
- <span data-ttu-id="11351-124">The [Location Report in Skype for Business Server (location-report.md) (by clicking either the Call volume or the Poor call percentage metric)</span><span class="sxs-lookup"><span data-stu-id="11351-124">The [Location Report in Skype for Business Server (location-report.md) (by clicking either the Call volume or the Poor call percentage metric)</span></span>
    
- <span data-ttu-id="11351-125">The [Media Quality Summary Report in Skype for Business Server (summary.md) (by clicking either the Call volume or Poor call percentage metric)</span><span class="sxs-lookup"><span data-stu-id="11351-125">The [Media Quality Summary Report in Skype for Business Server (summary.md) (by clicking either the Call volume or Poor call percentage metric)</span></span>
    
- <span data-ttu-id="11351-126">[Skype for Business Server](comparison.md)のメディア品質比較レポート[(Skype for Business Server](call-list-report-0.md)の通話リスト レポートをクリックし、[詳細] 指標をクリック)。</span><span class="sxs-lookup"><span data-stu-id="11351-126">The [Media Quality Comparison Report in Skype for Business Server](comparison.md) (by clicking the [Call List Report in Skype for Business Server](call-list-report-0.md) and then clicking the Detail metric).</span></span>
    
- <span data-ttu-id="11351-127">[Skype for Business Server](server-performance.md)のサーバー パフォーマンス レポート ([通話ボリューム] または [低品質通話のパーセンテージ] 指標をクリック)</span><span class="sxs-lookup"><span data-stu-id="11351-127">The [Server Performance Report in Skype for Business Server](server-performance.md) (by clicking either the Call volume or Poor call percentage metric)</span></span>
    
- <span data-ttu-id="11351-128">[Skype for Business Server の通話リスト](call-list-report-0.md)レポート ([詳細] 指標をクリック)</span><span class="sxs-lookup"><span data-stu-id="11351-128">The [Call List Report in Skype for Business Server](call-list-report-0.md) (by clicking the Detail metric)</span></span>
    
<span data-ttu-id="11351-129">通話詳細レポートから、次のいずれかの指標をクリックすると [、Skype for Business Server](device-report.md) のデバイス レポートにアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="11351-129">From within the Call Detail Report you can access the [Device Report in Skype for Business Server](device-report.md) by clicking either of the following metrics:</span></span>
  
- <span data-ttu-id="11351-130">キャプチャ デバイス</span><span class="sxs-lookup"><span data-stu-id="11351-130">Capture device</span></span>
    
- <span data-ttu-id="11351-131">レンダー デバイス</span><span class="sxs-lookup"><span data-stu-id="11351-131">Render device</span></span>
    
<span data-ttu-id="11351-132">また、音声ビデオ エッジ サーバー測定値をクリックすることによってサーバーメディア品質傾向レポートを表示できます。</span><span class="sxs-lookup"><span data-stu-id="11351-132">You can also access the Server Media Quality Trend Report by clicking the A/V edge server metric.</span></span>
  
## <a name="making-the-best-use-of-the-call-detail-report"></a><span data-ttu-id="11351-133">通話の詳細レポートの活用</span><span class="sxs-lookup"><span data-stu-id="11351-133">Making the Best Use of the Call Detail Report</span></span>

<span data-ttu-id="11351-p102">通話の詳細レポートには、一般的には、マイクのタイムスタンプの誤差、低 SNR 時間、および近端エコー時間の項目のような、250 以上のさまざまな測定値が含まれます。これらの測定値の詳細が思い出せない場合は、測定値のラベル上にマウス ポインターを置きます。多くの場合は、その測定値を説明するツール ヒントが表示されます。</span><span class="sxs-lookup"><span data-stu-id="11351-p102">The Call Detail Report typically includes over 250 different metrics, including such items as Microphone timestamp drift, Low SNR time, and Near end to echo time. If you can't remember what all of these metrics actually measure, try holding your mouse over the metric label; often-times, a tooltip will appear describing that metric.</span></span>
  
<span data-ttu-id="11351-136">測定基準の特定に問題がある場合は、検索ボックスに測定基準ラベルの一部を入力し、[検索] をクリック **します**。</span><span class="sxs-lookup"><span data-stu-id="11351-136">If you have problems locating a metric, type part of the metric label in the search box, and then click **Find**.</span></span> <span data-ttu-id="11351-137">たとえば、低 SNR 時間メトリックが見当たらない場合は、検索ボックスに SNR と入力し、[検索] をクリック **します**。</span><span class="sxs-lookup"><span data-stu-id="11351-137">For example, if you can't find the Low SNR time metric, type SNR in the search box, and then click **Find**.</span></span>
  
<span data-ttu-id="11351-138">レポートは通話に関する情報のみを追跡します。</span><span class="sxs-lookup"><span data-stu-id="11351-138">Note that the report only tracks information about a call.</span></span> <span data-ttu-id="11351-139">呼び出し自体は記録されません。</span><span class="sxs-lookup"><span data-stu-id="11351-139">The call itself is not recorded.</span></span>
  
## <a name="filters"></a><span data-ttu-id="11351-140">フィルター</span><span class="sxs-lookup"><span data-stu-id="11351-140">Filters</span></span>

<span data-ttu-id="11351-p105">なし。通話の詳細レポートにはフィルターを適用できません。</span><span class="sxs-lookup"><span data-stu-id="11351-p105">None. You cannot filter the Call Detail Report.</span></span>
  
## <a name="metrics"></a><span data-ttu-id="11351-143">指標</span><span class="sxs-lookup"><span data-stu-id="11351-143">Metrics</span></span>

<span data-ttu-id="11351-144">次の表に、各通話の通話の詳細レポートで提供される情報を示します。</span><span class="sxs-lookup"><span data-stu-id="11351-144">The following table lists the information provided in the Call Detail Report for each call.</span></span>
  
<span data-ttu-id="11351-145">**通話の詳細レポートの指標**</span><span class="sxs-lookup"><span data-stu-id="11351-145">**Call Detail Report Metrics**</span></span>

|<span data-ttu-id="11351-146">**名前**</span><span class="sxs-lookup"><span data-stu-id="11351-146">**Name**</span></span>|<span data-ttu-id="11351-147">**このアイテムを並べ替えることはできますか?**</span><span class="sxs-lookup"><span data-stu-id="11351-147">**Can you sort on this item?**</span></span>|<span data-ttu-id="11351-148">**説明**</span><span class="sxs-lookup"><span data-stu-id="11351-148">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="11351-149">[**発信者 PAI**]</span><span class="sxs-lookup"><span data-stu-id="11351-149">**Caller PAI**</span></span> <br/> |<span data-ttu-id="11351-150">いいえ</span><span class="sxs-lookup"><span data-stu-id="11351-150">No</span></span>  <br/> |<span data-ttu-id="11351-p106">呼び出しを開始したユーザーの P-Asserted-Identity。P-Asserted-Identity は、信頼されたネットワーク内でユーザーの証明済み ID を送信するのに使用されます。</span><span class="sxs-lookup"><span data-stu-id="11351-p106">P-Asserted-Identity of the user who initiated the call. The P-Asserted-Identity is used to convey the proven identity of a user within a trusted network.</span></span>  <br/> |
|<span data-ttu-id="11351-153">[**発信者 URI**]</span><span class="sxs-lookup"><span data-stu-id="11351-153">**Caller URI**</span></span> <br/> |<span data-ttu-id="11351-154">いいえ</span><span class="sxs-lookup"><span data-stu-id="11351-154">No</span></span>  <br/> |<span data-ttu-id="11351-155">呼び出しを開始したユーザーの SIP アドレス。</span><span class="sxs-lookup"><span data-stu-id="11351-155">SIP address of the user who initiated the call.</span></span>  <br/> |
|<span data-ttu-id="11351-156">[**発信者エンドポイント**]</span><span class="sxs-lookup"><span data-stu-id="11351-156">**Caller endpoint**</span></span> <br/> |<span data-ttu-id="11351-157">いいえ</span><span class="sxs-lookup"><span data-stu-id="11351-157">No</span></span>  <br/> |<span data-ttu-id="11351-158">呼び出しを実行したデバイス。</span><span class="sxs-lookup"><span data-stu-id="11351-158">Device used to make the call.</span></span>  <br/> |
|<span data-ttu-id="11351-159">[**発信者ユーザー エージェント**]</span><span class="sxs-lookup"><span data-stu-id="11351-159">**Caller user agent**</span></span> <br/> |<span data-ttu-id="11351-160">いいえ</span><span class="sxs-lookup"><span data-stu-id="11351-160">No</span></span>  <br/> |<span data-ttu-id="11351-161">呼び出しを実行したデバイスで使用されるソフトウェア。</span><span class="sxs-lookup"><span data-stu-id="11351-161">Software used on the device that made the call.</span></span>  <br/> |
|<span data-ttu-id="11351-162">[**通話の開始**]</span><span class="sxs-lookup"><span data-stu-id="11351-162">**Call start**</span></span> <br/> |<span data-ttu-id="11351-163">いいえ</span><span class="sxs-lookup"><span data-stu-id="11351-163">No</span></span>  <br/> |<span data-ttu-id="11351-164">呼び出しが最初に開始された日時。</span><span class="sxs-lookup"><span data-stu-id="11351-164">Date and time that the call was initially placed.</span></span>  <br/> |
|<span data-ttu-id="11351-165">[**仲介サーバーのバイパス通話**]</span><span class="sxs-lookup"><span data-stu-id="11351-165">**Mediation Server bypass call**</span></span> <br/> |<span data-ttu-id="11351-166">いいえ</span><span class="sxs-lookup"><span data-stu-id="11351-166">No</span></span>  <br/> |<span data-ttu-id="11351-167">呼び出しが仲介サーバーを経由せずに PSTN 音声ゲートウェイまたは適切な IP-PBX に接続されたかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="11351-167">Indicates whether the call connected to a PSTN voice gateway or qualified IP-PBX without passing through the Mediation Server.</span></span>  <br/> |
|<span data-ttu-id="11351-168">[**発信者 OS**]</span><span class="sxs-lookup"><span data-stu-id="11351-168">**Caller OS**</span></span> <br/> |<span data-ttu-id="11351-169">いいえ</span><span class="sxs-lookup"><span data-stu-id="11351-169">No</span></span>  <br/> |<span data-ttu-id="11351-170">呼び出し元のコンピューターのオペレーティング システム。</span><span class="sxs-lookup"><span data-stu-id="11351-170">Operating system of the caller's computer.</span></span>  <br/> |
|<span data-ttu-id="11351-171">[**発信者 CPU**]</span><span class="sxs-lookup"><span data-stu-id="11351-171">**Caller CPU**</span></span> <br/> |<span data-ttu-id="11351-172">いいえ</span><span class="sxs-lookup"><span data-stu-id="11351-172">No</span></span>  <br/> |<span data-ttu-id="11351-173">呼び出しを開始したユーザーのコンピューターに搭載される CPU。</span><span class="sxs-lookup"><span data-stu-id="11351-173">CPU installed in the computer of the user who initiated the call.</span></span>  <br/> |
|<span data-ttu-id="11351-174">[**発信者 CPU コア番号**]</span><span class="sxs-lookup"><span data-stu-id="11351-174">**Caller CPU core number**</span></span> <br/> |<span data-ttu-id="11351-175">いいえ</span><span class="sxs-lookup"><span data-stu-id="11351-175">No</span></span>  <br/> |<span data-ttu-id="11351-176">呼び出しを開始したユーザーが使用するコンピューターのプロセッサ番号。</span><span class="sxs-lookup"><span data-stu-id="11351-176">Processor number in the computer used by the person who initiated the call.</span></span>  <br/> |
|<span data-ttu-id="11351-177">[**発信者 CPU 速度**]</span><span class="sxs-lookup"><span data-stu-id="11351-177">**Caller CPU speed**</span></span> <br/> |<span data-ttu-id="11351-178">いいえ</span><span class="sxs-lookup"><span data-stu-id="11351-178">No</span></span>  <br/> |<span data-ttu-id="11351-179">呼び出しを開始したユーザーが使用するコンピューターの CPU のクロック速度。</span><span class="sxs-lookup"><span data-stu-id="11351-179">Clock speed of the CPU of the computer used by the person who initiated the call.</span></span>  <br/> |
|<span data-ttu-id="11351-180">[**発信者 CPU 仮想化**]</span><span class="sxs-lookup"><span data-stu-id="11351-180">**Caller CPU virtualization**</span></span> <br/> |<span data-ttu-id="11351-181">いいえ</span><span class="sxs-lookup"><span data-stu-id="11351-181">No</span></span>  <br/> |<span data-ttu-id="11351-182">呼び出しを開始したユーザーが使用するコンピューターでの仮想化 (仮想化されている場合)。</span><span class="sxs-lookup"><span data-stu-id="11351-182">Virtualization (if any) used on the computer used by the person who initiated the call.</span></span>  <br/> |
|<span data-ttu-id="11351-183">[**呼び出し先 PAI**]</span><span class="sxs-lookup"><span data-stu-id="11351-183">**Callee PAI**</span></span> <br/> |<span data-ttu-id="11351-184">いいえ</span><span class="sxs-lookup"><span data-stu-id="11351-184">No</span></span>  <br/> |<span data-ttu-id="11351-p107">通話に招待されたユーザーの P-Asserted-Identity。P-Asserted-Identity は、信頼されたネットワーク内でユーザーの証明済み ID を送信するのに使用されます。</span><span class="sxs-lookup"><span data-stu-id="11351-p107">P-Asserted-Identity of the user who was invited to join the call. The P-Asserted-Identity is used to convey the proven identity of a user within a trusted network.</span></span>  <br/> |
|<span data-ttu-id="11351-187">[**呼び出し先 URI**]</span><span class="sxs-lookup"><span data-stu-id="11351-187">**Callee URI**</span></span> <br/> |<span data-ttu-id="11351-188">いいえ</span><span class="sxs-lookup"><span data-stu-id="11351-188">No</span></span>  <br/> |<span data-ttu-id="11351-189">呼び出し先ユーザーの SIP アドレス。</span><span class="sxs-lookup"><span data-stu-id="11351-189">SIP address of the user who was called.</span></span>  <br/> |
|<span data-ttu-id="11351-190">[**呼び出し先エンドポイント**]</span><span class="sxs-lookup"><span data-stu-id="11351-190">**Callee endpoint**</span></span> <br/> |<span data-ttu-id="11351-191">いいえ</span><span class="sxs-lookup"><span data-stu-id="11351-191">No</span></span>  <br/> |<span data-ttu-id="11351-192">呼び出しを受信したデバイス。</span><span class="sxs-lookup"><span data-stu-id="11351-192">Device used to receive the call.</span></span>  <br/> |
|<span data-ttu-id="11351-193">[**呼び出し先ユーザー エージェント**]</span><span class="sxs-lookup"><span data-stu-id="11351-193">**Callee user agent**</span></span> <br/> |<span data-ttu-id="11351-194">いいえ</span><span class="sxs-lookup"><span data-stu-id="11351-194">No</span></span>  <br/> |<span data-ttu-id="11351-195">呼び出しを受信したデバイスで使用されるソフトウェア。</span><span class="sxs-lookup"><span data-stu-id="11351-195">Software used on the device that received the call.</span></span>  <br/> |
|<span data-ttu-id="11351-196">**Duration**</span><span class="sxs-lookup"><span data-stu-id="11351-196">**Duration**</span></span> <br/> |<span data-ttu-id="11351-197">いいえ</span><span class="sxs-lookup"><span data-stu-id="11351-197">No</span></span>  <br/> |<span data-ttu-id="11351-198">通話時間。</span><span class="sxs-lookup"><span data-stu-id="11351-198">Length of time for the call.</span></span>  <br/> |
|<span data-ttu-id="11351-199">[**メディア バイパス警告フラグ**]</span><span class="sxs-lookup"><span data-stu-id="11351-199">**Media bypass warning flag**</span></span> <br/> |<span data-ttu-id="11351-200">いいえ</span><span class="sxs-lookup"><span data-stu-id="11351-200">No</span></span>  <br/> |<span data-ttu-id="11351-201">仲介サーバーがバイパスされたときに発行された警告。</span><span class="sxs-lookup"><span data-stu-id="11351-201">Warning issued when the Mediation Server was bypassed.</span></span>  <br/> |
|<span data-ttu-id="11351-202">[**呼び出し先 OS**]</span><span class="sxs-lookup"><span data-stu-id="11351-202">**Callee OS**</span></span> <br/> |<span data-ttu-id="11351-203">いいえ</span><span class="sxs-lookup"><span data-stu-id="11351-203">No</span></span>  <br/> |<span data-ttu-id="11351-204">呼び出し先ユーザーのコンピューターのオペレーティング システム。</span><span class="sxs-lookup"><span data-stu-id="11351-204">Operating system of the computer for the user who was called.</span></span>  <br/> |
|<span data-ttu-id="11351-205">[**呼び出し先 CPU**]</span><span class="sxs-lookup"><span data-stu-id="11351-205">**Callee CPU**</span></span> <br/> |<span data-ttu-id="11351-206">いいえ</span><span class="sxs-lookup"><span data-stu-id="11351-206">No</span></span>  <br/> |<span data-ttu-id="11351-207">呼び出し先ユーザーのコンピューターに搭載される CPU。</span><span class="sxs-lookup"><span data-stu-id="11351-207">CPU installed in the computer of the user who was called.</span></span>  <br/> |
|<span data-ttu-id="11351-208">[**呼び出し先コア番号**]</span><span class="sxs-lookup"><span data-stu-id="11351-208">**Callee core number**</span></span> <br/> |<span data-ttu-id="11351-209">いいえ</span><span class="sxs-lookup"><span data-stu-id="11351-209">No</span></span>  <br/> |<span data-ttu-id="11351-210">呼び出し先ユーザーが使用するコンピューターのプロセッサ番号。</span><span class="sxs-lookup"><span data-stu-id="11351-210">Processor number in the computer used by the person who was called.</span></span>  <br/> |
|<span data-ttu-id="11351-211">[**呼び出し先 CPU 速度**]</span><span class="sxs-lookup"><span data-stu-id="11351-211">**Callee CPU speed**</span></span> <br/> |<span data-ttu-id="11351-212">いいえ</span><span class="sxs-lookup"><span data-stu-id="11351-212">No</span></span>  <br/> |<span data-ttu-id="11351-213">呼び出し先ユーザーが使用するコンピューターの CPU のクロック速度。</span><span class="sxs-lookup"><span data-stu-id="11351-213">Clock speed of the CPU of the computer used by the person who was called.</span></span>  <br/> |
|<span data-ttu-id="11351-214">[**呼び出し先 CPU 仮想化**]</span><span class="sxs-lookup"><span data-stu-id="11351-214">**Callee CPU virtualization**</span></span> <br/> |<span data-ttu-id="11351-215">いいえ</span><span class="sxs-lookup"><span data-stu-id="11351-215">No</span></span>  <br/> |<span data-ttu-id="11351-216">呼び出し先ユーザーが使用するコンピューターでの仮想化 (仮想化されている場合)。</span><span class="sxs-lookup"><span data-stu-id="11351-216">Virtualization (if any) used on the computer used by the person who was called.</span></span>  <br/> |
   

