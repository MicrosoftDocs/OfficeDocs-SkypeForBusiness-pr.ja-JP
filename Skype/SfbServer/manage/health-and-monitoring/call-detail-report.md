---
title: Skype のビジネス サーバーの詳細レポートを呼び出す
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 38862e35-3fec-41b9-a035-0b301942d446
description: '概要: は、Skype のビジネスのサーバーが使用する呼び出しの詳細レポートについて説明します。'
ms.openlocfilehash: 3f560a2d4217b5afd61036b39100b39888fe577a
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/24/2018
ms.locfileid: "20978883"
---
# <a name="call-detail-report-in-skype-for-business-server"></a><span data-ttu-id="4dc6f-103">Skype のビジネス サーバーの詳細レポートを呼び出す</span><span class="sxs-lookup"><span data-stu-id="4dc6f-103">Call Detail Report in Skype for Business Server</span></span>
 
<span data-ttu-id="4dc6f-104">**の概要:** ビジネス サーバーの Skype で使用される呼び出しの詳細レポートについて説明します。</span><span class="sxs-lookup"><span data-stu-id="4dc6f-104">**Summary:** Learn about the Call Detail Report used in Skype for Business Server.</span></span>
  
<span data-ttu-id="4dc6f-105">呼び出しの詳細レポートの提供についての詳細を個別に呼び出す。レポートには、ほぼすべての品質の経験が含まれています測定基準および業務サーバーの場合は、Skype で収集される統計情報レポートのセクションに分かれて次のようにします。</span><span class="sxs-lookup"><span data-stu-id="4dc6f-105">The Call Detail Report provides a detailed look at an individual call; the report includes nearly all the Quality of Experience metrics and statistics collected by Skype for Business Server, divided into report sections such as:</span></span>
  
- <span data-ttu-id="4dc6f-106">通話情報</span><span class="sxs-lookup"><span data-stu-id="4dc6f-106">Call Information</span></span> 
    
- <span data-ttu-id="4dc6f-107">発信者のデバイスおよび信号指標</span><span class="sxs-lookup"><span data-stu-id="4dc6f-107">Caller Device and Signal Metrics</span></span>
    
- <span data-ttu-id="4dc6f-108">呼び出し先のデバイスおよび信号指標</span><span class="sxs-lookup"><span data-stu-id="4dc6f-108">Callee Device and Signal metrics</span></span>
    
- <span data-ttu-id="4dc6f-109">発信者クライアント イベント</span><span class="sxs-lookup"><span data-stu-id="4dc6f-109">Caller Client Event</span></span>
    
- <span data-ttu-id="4dc6f-110">呼び出し先クライアント イベント</span><span class="sxs-lookup"><span data-stu-id="4dc6f-110">Callee Client Event</span></span>
    
- <span data-ttu-id="4dc6f-111">音声ストリーム (発信者から呼び出し先)</span><span class="sxs-lookup"><span data-stu-id="4dc6f-111">Audio Stream (Caller to Callee)</span></span>
    
- <span data-ttu-id="4dc6f-112">ビデオ ストリーム (発信者から呼び出し先)</span><span class="sxs-lookup"><span data-stu-id="4dc6f-112">Video Stream (Caller to Callee)</span></span>
    
- <span data-ttu-id="4dc6f-113">音声ストリーム (呼び出し先から発信者)</span><span class="sxs-lookup"><span data-stu-id="4dc6f-113">Audio Stream (Callee to Caller)</span></span>
    
- <span data-ttu-id="4dc6f-114">ビデオ ストリーム (呼び出し先から発信者)</span><span class="sxs-lookup"><span data-stu-id="4dc6f-114">Video Stream (Callee to Caller)</span></span>
    
<span data-ttu-id="4dc6f-p101">特定のレポートに表示されるカテゴリと指標は、セッションの種類と、セッションで使用されたエンドポイントの種類に依存します。たとえば、音声のみの通話では、通話にビデオ ストリームがないことにより、ビデオ ストリームの指標は報告されません。同様に、呼び出し先統計はないが、発信者統計を示すレポートがあることがあります。この原因は通常、呼び出し先が SIP 準拠のデバイスを使用していないことです。エンドポイントは通話の終了後に、統計を報告します。しかし、(SIP または SIP 統計を関知しない) 携帯電話は、その種類の情報を報告することはできません。電話の相手先が携帯電話で応答した場合は、通話の終了時に、その携帯電話からのレポートは得られません。</span><span class="sxs-lookup"><span data-stu-id="4dc6f-p101">Keep in mind that the categories and the metrics you see on a given report depend on two things: the type of session and the type of endpoints used in the session. For example, an audio-only call will not report metrics for video streams; that's because the call didn't have a video stream. Likewise, you might have a report that lists caller statistics but not callee statistics. That's typically because the callee was not using a SIP-compliant device. Endpoints are responsible for reporting statistics at the end of a call; however, a cell phone (which knows nothing about SIP or SIP statistics) is unable to report that kind of information. If you call someone and they answer you on their cell phone, you will not get a report from that cell phone when the call ends.</span></span>
  
<span data-ttu-id="4dc6f-121">通話の詳細レポートは、特定の通話でメディアの品質の問題が発生した理由を正確に確認するときに最も役立ちます。</span><span class="sxs-lookup"><span data-stu-id="4dc6f-121">The Call Detail Report is most useful when you are trying to determine exactly why a given call experienced media quality problems.</span></span>
  
## <a name="accessing-the-call-detail-report"></a><span data-ttu-id="4dc6f-122">通話の詳細レポートを表示する</span><span class="sxs-lookup"><span data-stu-id="4dc6f-122">Accessing the Call Detail Report</span></span>

<span data-ttu-id="4dc6f-123">通話の詳細レポートは、以下の任意のレポートから表示できます。</span><span class="sxs-lookup"><span data-stu-id="4dc6f-123">The Call Detail Report can be accessed from any of the following reports:</span></span>
  
- <span data-ttu-id="4dc6f-124">[場所レポート] をクリックして電話の数または不適切な呼び出しの割合のメトリックのいずれか) ビジネス サーバー (場所 report.md) の Skype で</span><span class="sxs-lookup"><span data-stu-id="4dc6f-124">The [Location Report in Skype for Business Server (location-report.md) (by clicking either the Call volume or the Poor call percentage metric)</span></span>
    
- <span data-ttu-id="4dc6f-125">[メディア品質概要レポート] をクリックして通話量または不適切な呼び出しの割合のメトリックのいずれか) ビジネス サーバー (summary.md) の Skype で</span><span class="sxs-lookup"><span data-stu-id="4dc6f-125">The [Media Quality Summary Report in Skype for Business Server (summary.md) (by clicking either the Call volume or Poor call percentage metric)</span></span>
    
- <span data-ttu-id="4dc6f-126">[Skype ビジネス サーバー用のメディアの品質の比較レポート](comparison.md)( [Skype ビジネス サーバーでリスト レポートを呼び出す](call-list-report-0.md)] をクリックし、[詳細] のメトリックをクリックすると)。</span><span class="sxs-lookup"><span data-stu-id="4dc6f-126">The [Media Quality Comparison Report in Skype for Business Server](comparison.md) (by clicking the [Call List Report in Skype for Business Server](call-list-report-0.md) and then clicking the Detail metric).</span></span>
    
- <span data-ttu-id="4dc6f-127">[Skype ビジネス サーバー用のサーバー パフォーマンス レポート](server-performance.md)] をクリックして通話量または不適切な呼び出しの割合のメトリックのいずれか)</span><span class="sxs-lookup"><span data-stu-id="4dc6f-127">The [Server Performance Report in Skype for Business Server](server-performance.md) (by clicking either the Call volume or Poor call percentage metric)</span></span>
    
- <span data-ttu-id="4dc6f-128">[Skype ビジネス サーバーでリスト レポートを呼び出す](call-list-report-0.md)] をクリックして、[詳細] のメトリック)</span><span class="sxs-lookup"><span data-stu-id="4dc6f-128">The [Call List Report in Skype for Business Server](call-list-report-0.md) (by clicking the Detail metric)</span></span>
    
<span data-ttu-id="4dc6f-129">呼び出しの詳細レポート内からに次の測定値のいずれかをクリックすると、 [Skype のビジネス サーバーでデバイスのレポート](device-report.md)をアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="4dc6f-129">From within the Call Detail Report you can access the [Device Report in Skype for Business Server](device-report.md) by clicking either of the following metrics:</span></span>
  
- <span data-ttu-id="4dc6f-130">[キャプチャ デバイス]</span><span class="sxs-lookup"><span data-stu-id="4dc6f-130">Capture device</span></span>
    
- <span data-ttu-id="4dc6f-131">[レンダー デバイス]</span><span class="sxs-lookup"><span data-stu-id="4dc6f-131">Render device</span></span>
    
<span data-ttu-id="4dc6f-132">また、音声ビデオ エッジ サーバー指標をクリックすると、サーバー メディア品質傾向レポートを表示できます。</span><span class="sxs-lookup"><span data-stu-id="4dc6f-132">You can also access the Server Media Quality Trend Report by clicking the A/V edge server metric.</span></span>
  
## <a name="making-the-best-use-of-the-call-detail-report"></a><span data-ttu-id="4dc6f-133">通話の詳細レポートの活用</span><span class="sxs-lookup"><span data-stu-id="4dc6f-133">Making the Best Use of the Call Detail Report</span></span>

<span data-ttu-id="4dc6f-p102">通話の詳細レポートには、一般的には、マイクのタイムスタンプの誤差、低 SNR 時間、および近端エコー時間の項目のような、250 個以上のさまざまな指標が含まれます。これらの指標の詳細が思い出せない場合は、指標のラベル上にマウス ポインターを置きます。多くの場合は、その指標を説明するツール ヒントが表示されます。</span><span class="sxs-lookup"><span data-stu-id="4dc6f-p102">The Call Detail Report typically includes over 250 different metrics, including such items as Microphone timestamp drift, Low SNR time, and Near end to echo time. If you can't remember what all of these metrics actually measure, try holding your mouse over the metric label; often-times, a tooltip will appear describing that metric.</span></span>
  
<span data-ttu-id="4dc6f-p103">特定の測定値が見つからない場合は、検索ボックスに測定値ラベルの一部を入力して、次に [**検索**] をクリックします。たとえば、低 SNR 時間測定値が見つからない場合は、検索ボックスに "SNR" と入力して、次に [**検索**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="4dc6f-p103">If you have problems locating a metric, type part of the metric label in the search box, and then click **Find**. For example, if you can't find the Low SNR time metric, type SNR in the search box, and then click **Find**.</span></span>
  
<span data-ttu-id="4dc6f-p104">レポートは、通話に関する情報を記録するだけです。通話自体は記録されません。</span><span class="sxs-lookup"><span data-stu-id="4dc6f-p104">Note that the report only tracks information about a call. The call itself is not recorded.</span></span>
  
## <a name="filters"></a><span data-ttu-id="4dc6f-140">フィルター</span><span class="sxs-lookup"><span data-stu-id="4dc6f-140">Filters</span></span>

<span data-ttu-id="4dc6f-p105">なし。通話の詳細レポートにはフィルターを適用できません。</span><span class="sxs-lookup"><span data-stu-id="4dc6f-p105">None. You cannot filter the Call Detail Report.</span></span>
  
## <a name="metrics"></a><span data-ttu-id="4dc6f-143">指標</span><span class="sxs-lookup"><span data-stu-id="4dc6f-143">Metrics</span></span>

<span data-ttu-id="4dc6f-144">次の表に、各通話の通話の詳細レポートで提供される情報を示します。</span><span class="sxs-lookup"><span data-stu-id="4dc6f-144">The following table lists the information provided in the Call Detail Report for each call.</span></span>
  
<span data-ttu-id="4dc6f-145">**通話の詳細レポートの指標**</span><span class="sxs-lookup"><span data-stu-id="4dc6f-145">**Call Detail Report Metrics**</span></span>

|<span data-ttu-id="4dc6f-146">**名前**</span><span class="sxs-lookup"><span data-stu-id="4dc6f-146">**Name**</span></span>|<span data-ttu-id="4dc6f-147">**この項目での並べ替え**</span><span class="sxs-lookup"><span data-stu-id="4dc6f-147">**Can you sort on this item?**</span></span>|<span data-ttu-id="4dc6f-148">**説明**</span><span class="sxs-lookup"><span data-stu-id="4dc6f-148">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="4dc6f-149">**[発信者 PAI]**</span><span class="sxs-lookup"><span data-stu-id="4dc6f-149">**Caller PAI**</span></span> <br/> |<span data-ttu-id="4dc6f-150">不可</span><span class="sxs-lookup"><span data-stu-id="4dc6f-150">No</span></span>  <br/> |<span data-ttu-id="4dc6f-p106">呼び出しを開始したユーザーの P-Asserted-Identity。P-Asserted-Identity は、信頼されたネットワーク内でユーザーの証明済み ID を送信するのに使用されます。</span><span class="sxs-lookup"><span data-stu-id="4dc6f-p106">P-Asserted-Identity of the user who initiated the call. The P-Asserted-Identity is used to convey the proven identity of a user within a trusted network.</span></span>  <br/> |
|<span data-ttu-id="4dc6f-153">**[発信者 URI]**</span><span class="sxs-lookup"><span data-stu-id="4dc6f-153">**Caller URI**</span></span> <br/> |<span data-ttu-id="4dc6f-154">不可</span><span class="sxs-lookup"><span data-stu-id="4dc6f-154">No</span></span>  <br/> |<span data-ttu-id="4dc6f-155">呼び出しを開始したユーザーの SIP アドレス。</span><span class="sxs-lookup"><span data-stu-id="4dc6f-155">SIP address of the user who initiated the call.</span></span>  <br/> |
|<span data-ttu-id="4dc6f-156">**[発信者エンドポイント]**</span><span class="sxs-lookup"><span data-stu-id="4dc6f-156">**Caller endpoint**</span></span> <br/> |<span data-ttu-id="4dc6f-157">不可</span><span class="sxs-lookup"><span data-stu-id="4dc6f-157">No</span></span>  <br/> |<span data-ttu-id="4dc6f-158">呼び出しを実行したデバイス。</span><span class="sxs-lookup"><span data-stu-id="4dc6f-158">Device used to make the call.</span></span>  <br/> |
|<span data-ttu-id="4dc6f-159">**[発信者ユーザー エージェント]**</span><span class="sxs-lookup"><span data-stu-id="4dc6f-159">**Caller user agent**</span></span> <br/> |<span data-ttu-id="4dc6f-160">不可</span><span class="sxs-lookup"><span data-stu-id="4dc6f-160">No</span></span>  <br/> |<span data-ttu-id="4dc6f-161">呼び出しを実行したデバイスで使用されるソフトウェア。</span><span class="sxs-lookup"><span data-stu-id="4dc6f-161">Software used on the device that made the call.</span></span>  <br/> |
|<span data-ttu-id="4dc6f-162">**[通話の開始]**</span><span class="sxs-lookup"><span data-stu-id="4dc6f-162">**Call start**</span></span> <br/> |<span data-ttu-id="4dc6f-163">不可</span><span class="sxs-lookup"><span data-stu-id="4dc6f-163">No</span></span>  <br/> |<span data-ttu-id="4dc6f-164">呼び出しが最初に開始された日時。</span><span class="sxs-lookup"><span data-stu-id="4dc6f-164">Date and time that the call was initially placed.</span></span>  <br/> |
|<span data-ttu-id="4dc6f-165">**[仲介サーバーのバイパス通話]**</span><span class="sxs-lookup"><span data-stu-id="4dc6f-165">**Mediation Server bypass call**</span></span> <br/> |<span data-ttu-id="4dc6f-166">不可</span><span class="sxs-lookup"><span data-stu-id="4dc6f-166">No</span></span>  <br/> |<span data-ttu-id="4dc6f-167">呼び出しが仲介サーバーを経由せずに PSTN 音声ゲートウェイまたは適切な IP-PBX に接続されたかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="4dc6f-167">Indicates whether the call connected to a PSTN voice gateway or qualified IP-PBX without passing through the Mediation Server.</span></span>  <br/> |
|<span data-ttu-id="4dc6f-168">**[発信者 OS]**</span><span class="sxs-lookup"><span data-stu-id="4dc6f-168">**Caller OS**</span></span> <br/> |<span data-ttu-id="4dc6f-169">不可</span><span class="sxs-lookup"><span data-stu-id="4dc6f-169">No</span></span>  <br/> |<span data-ttu-id="4dc6f-170">呼び出し元のコンピューターのオペレーティング システム。</span><span class="sxs-lookup"><span data-stu-id="4dc6f-170">Operating system of the caller's computer.</span></span>  <br/> |
|<span data-ttu-id="4dc6f-171">**[発信者 CPU]**</span><span class="sxs-lookup"><span data-stu-id="4dc6f-171">**Caller CPU**</span></span> <br/> |<span data-ttu-id="4dc6f-172">不可</span><span class="sxs-lookup"><span data-stu-id="4dc6f-172">No</span></span>  <br/> |<span data-ttu-id="4dc6f-173">呼び出しを開始したユーザーのコンピューターに搭載される CPU。</span><span class="sxs-lookup"><span data-stu-id="4dc6f-173">CPU installed in the computer of the user who initiated the call.</span></span>  <br/> |
|<span data-ttu-id="4dc6f-174">**[発信者 CPU コア番号]**</span><span class="sxs-lookup"><span data-stu-id="4dc6f-174">**Caller CPU core number**</span></span> <br/> |<span data-ttu-id="4dc6f-175">不可</span><span class="sxs-lookup"><span data-stu-id="4dc6f-175">No</span></span>  <br/> |<span data-ttu-id="4dc6f-176">呼び出しを開始したユーザーが使用するコンピューターのプロセッサ番号。</span><span class="sxs-lookup"><span data-stu-id="4dc6f-176">Processor number in the computer used by the person who initiated the call.</span></span>  <br/> |
|<span data-ttu-id="4dc6f-177">**[発信者 CPU 速度]**</span><span class="sxs-lookup"><span data-stu-id="4dc6f-177">**Caller CPU speed**</span></span> <br/> |<span data-ttu-id="4dc6f-178">不可</span><span class="sxs-lookup"><span data-stu-id="4dc6f-178">No</span></span>  <br/> |<span data-ttu-id="4dc6f-179">呼び出しを開始したユーザーが使用するコンピューターの CPU のクロック速度。</span><span class="sxs-lookup"><span data-stu-id="4dc6f-179">Clock speed of the CPU of the computer used by the person who initiated the call.</span></span>  <br/> |
|<span data-ttu-id="4dc6f-180">**[発信者 CPU 仮想化]**</span><span class="sxs-lookup"><span data-stu-id="4dc6f-180">**Caller CPU virtualization**</span></span> <br/> |<span data-ttu-id="4dc6f-181">不可</span><span class="sxs-lookup"><span data-stu-id="4dc6f-181">No</span></span>  <br/> |<span data-ttu-id="4dc6f-182">呼び出しを開始したユーザーが使用するコンピューターでの仮想化 (仮想化されている場合)。</span><span class="sxs-lookup"><span data-stu-id="4dc6f-182">Virtualization (if any) used on the computer used by the person who initiated the call.</span></span>  <br/> |
|<span data-ttu-id="4dc6f-183">**[呼び出し先 PAI]**</span><span class="sxs-lookup"><span data-stu-id="4dc6f-183">**Callee PAI**</span></span> <br/> |<span data-ttu-id="4dc6f-184">不可</span><span class="sxs-lookup"><span data-stu-id="4dc6f-184">No</span></span>  <br/> |<span data-ttu-id="4dc6f-p107">通話に招待されたユーザーの P-Asserted-Identity。P-Asserted-Identity は、信頼されたネットワーク内でユーザーの証明済み ID を送信するのに使用されます。</span><span class="sxs-lookup"><span data-stu-id="4dc6f-p107">P-Asserted-Identity of the user who was invited to join the call. The P-Asserted-Identity is used to convey the proven identity of a user within a trusted network.</span></span>  <br/> |
|<span data-ttu-id="4dc6f-187">**[呼び出し先 URI]**</span><span class="sxs-lookup"><span data-stu-id="4dc6f-187">**Callee URI**</span></span> <br/> |<span data-ttu-id="4dc6f-188">不可</span><span class="sxs-lookup"><span data-stu-id="4dc6f-188">No</span></span>  <br/> |<span data-ttu-id="4dc6f-189">呼び出し先ユーザーの SIP アドレス。</span><span class="sxs-lookup"><span data-stu-id="4dc6f-189">SIP address of the user who was called.</span></span>  <br/> |
|<span data-ttu-id="4dc6f-190">**[呼び出し先エンドポイント]**</span><span class="sxs-lookup"><span data-stu-id="4dc6f-190">**Callee endpoint**</span></span> <br/> |<span data-ttu-id="4dc6f-191">不可</span><span class="sxs-lookup"><span data-stu-id="4dc6f-191">No</span></span>  <br/> |<span data-ttu-id="4dc6f-192">呼び出しを受信したデバイス。</span><span class="sxs-lookup"><span data-stu-id="4dc6f-192">Device used to receive the call.</span></span>  <br/> |
|<span data-ttu-id="4dc6f-193">**[呼び出し先ユーザー エージェント]**</span><span class="sxs-lookup"><span data-stu-id="4dc6f-193">**Callee user agent**</span></span> <br/> |<span data-ttu-id="4dc6f-194">不可</span><span class="sxs-lookup"><span data-stu-id="4dc6f-194">No</span></span>  <br/> |<span data-ttu-id="4dc6f-195">呼び出しを受信したデバイスで使用されるソフトウェア。</span><span class="sxs-lookup"><span data-stu-id="4dc6f-195">Software used on the device that received the call.</span></span>  <br/> |
|<span data-ttu-id="4dc6f-196">**[時間]**</span><span class="sxs-lookup"><span data-stu-id="4dc6f-196">**Duration**</span></span> <br/> |<span data-ttu-id="4dc6f-197">不可</span><span class="sxs-lookup"><span data-stu-id="4dc6f-197">No</span></span>  <br/> |<span data-ttu-id="4dc6f-198">通話時間。</span><span class="sxs-lookup"><span data-stu-id="4dc6f-198">Length of time for the call.</span></span>  <br/> |
|<span data-ttu-id="4dc6f-199">**[メディア バイパス警告フラグ]**</span><span class="sxs-lookup"><span data-stu-id="4dc6f-199">**Media bypass warning flag**</span></span> <br/> |<span data-ttu-id="4dc6f-200">不可</span><span class="sxs-lookup"><span data-stu-id="4dc6f-200">No</span></span>  <br/> |<span data-ttu-id="4dc6f-201">仲介サーバーがバイパスされたときに発行された警告。</span><span class="sxs-lookup"><span data-stu-id="4dc6f-201">Warning issued when the Mediation Server was bypassed.</span></span>  <br/> |
|<span data-ttu-id="4dc6f-202">**[呼び出し先 OS]**</span><span class="sxs-lookup"><span data-stu-id="4dc6f-202">**Callee OS**</span></span> <br/> |<span data-ttu-id="4dc6f-203">不可</span><span class="sxs-lookup"><span data-stu-id="4dc6f-203">No</span></span>  <br/> |<span data-ttu-id="4dc6f-204">呼び出し先ユーザーのコンピューターのオペレーティング システム。</span><span class="sxs-lookup"><span data-stu-id="4dc6f-204">Operating system of the computer for the user who was called.</span></span>  <br/> |
|<span data-ttu-id="4dc6f-205">**[呼び出し先 CPU]**</span><span class="sxs-lookup"><span data-stu-id="4dc6f-205">**Callee CPU**</span></span> <br/> |<span data-ttu-id="4dc6f-206">不可</span><span class="sxs-lookup"><span data-stu-id="4dc6f-206">No</span></span>  <br/> |<span data-ttu-id="4dc6f-207">呼び出し先ユーザーのコンピューターに搭載される CPU。</span><span class="sxs-lookup"><span data-stu-id="4dc6f-207">CPU installed in the computer of the user who was called.</span></span>  <br/> |
|<span data-ttu-id="4dc6f-208">**[呼び出し先コア番号]**</span><span class="sxs-lookup"><span data-stu-id="4dc6f-208">**Callee core number**</span></span> <br/> |<span data-ttu-id="4dc6f-209">いいえ</span><span class="sxs-lookup"><span data-stu-id="4dc6f-209">No</span></span>  <br/> |<span data-ttu-id="4dc6f-210">呼び出し先ユーザーが使用するコンピューターのプロセッサ番号。</span><span class="sxs-lookup"><span data-stu-id="4dc6f-210">Processor number in the computer used by the person who was called.</span></span>  <br/> |
|<span data-ttu-id="4dc6f-211">**[呼び出し先 CPU 速度]**</span><span class="sxs-lookup"><span data-stu-id="4dc6f-211">**Callee CPU speed**</span></span> <br/> |<span data-ttu-id="4dc6f-212">不可</span><span class="sxs-lookup"><span data-stu-id="4dc6f-212">No</span></span>  <br/> |<span data-ttu-id="4dc6f-213">呼び出し先ユーザーが使用するコンピューターの CPU のクロック速度。</span><span class="sxs-lookup"><span data-stu-id="4dc6f-213">Clock speed of the CPU of the computer used by the person who was called.</span></span>  <br/> |
|<span data-ttu-id="4dc6f-214">**[呼び出し先 CPU 仮想化]**</span><span class="sxs-lookup"><span data-stu-id="4dc6f-214">**Callee CPU virtualization**</span></span> <br/> |<span data-ttu-id="4dc6f-215">不可</span><span class="sxs-lookup"><span data-stu-id="4dc6f-215">No</span></span>  <br/> |<span data-ttu-id="4dc6f-216">呼び出し先ユーザーが使用するコンピューターでの仮想化 (仮想化されている場合)。</span><span class="sxs-lookup"><span data-stu-id="4dc6f-216">Virtualization (if any) used on the computer used by the person who was called.</span></span>  <br/> |
   

