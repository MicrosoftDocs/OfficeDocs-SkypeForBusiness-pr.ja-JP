---
title: Skype for Business Server 2015 の通話の詳細レポート
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 38862e35-3fec-41b9-a035-0b301942d446
description: '概要: は、ビジネス サーバー 2015 の Skype で使用される呼び出しの詳細レポートについて説明します。'
ms.openlocfilehash: 942562ed33462506c9da137b3e4377e102d0ec98
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/28/2018
---
# <a name="call-detail-report-in-skype-for-business-server-2015"></a><span data-ttu-id="f2e67-103">Skype for Business Server 2015 の通話の詳細レポート</span><span class="sxs-lookup"><span data-stu-id="f2e67-103">Call Detail Report in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="f2e67-104">**の概要:**ビジネス サーバー 2015 の Skype で使用される呼び出しの詳細レポートについて説明します。</span><span class="sxs-lookup"><span data-stu-id="f2e67-104">**Summary:** Learn about the Call Detail Report used in Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="f2e67-105">呼び出しの詳細レポートの提供についての詳細を個別に呼び出す。レポートには、2015 年のビジネス サーバーは次のようにレポート セクションに分かれての経験の評価尺度と Skype で収集された統計のほぼすべての品質が含まれています。</span><span class="sxs-lookup"><span data-stu-id="f2e67-105">The Call Detail Report provides a detailed look at an individual call; the report includes nearly all the Quality of Experience metrics and statistics collected by Skype for Business Server 2015, divided into report sections such as:</span></span>
  
- <span data-ttu-id="f2e67-106">通話情報</span><span class="sxs-lookup"><span data-stu-id="f2e67-106">Call Information</span></span> 
    
- <span data-ttu-id="f2e67-107">発信者のデバイスおよび信号指標</span><span class="sxs-lookup"><span data-stu-id="f2e67-107">Caller Device and Signal Metrics</span></span>
    
- <span data-ttu-id="f2e67-108">呼び出し先のデバイスおよび信号指標</span><span class="sxs-lookup"><span data-stu-id="f2e67-108">Callee Device and Signal metrics</span></span>
    
- <span data-ttu-id="f2e67-109">発信者クライアント イベント</span><span class="sxs-lookup"><span data-stu-id="f2e67-109">Caller Client Event</span></span>
    
- <span data-ttu-id="f2e67-110">呼び出し先クライアント イベント</span><span class="sxs-lookup"><span data-stu-id="f2e67-110">Callee Client Event</span></span>
    
- <span data-ttu-id="f2e67-111">音声ストリーム (発信者から呼び出し先)</span><span class="sxs-lookup"><span data-stu-id="f2e67-111">Audio Stream (Caller to Callee)</span></span>
    
- <span data-ttu-id="f2e67-112">ビデオ ストリーム (発信者から呼び出し先)</span><span class="sxs-lookup"><span data-stu-id="f2e67-112">Video Stream (Caller to Callee)</span></span>
    
- <span data-ttu-id="f2e67-113">音声ストリーム (呼び出し先から発信者)</span><span class="sxs-lookup"><span data-stu-id="f2e67-113">Audio Stream (Callee to Caller)</span></span>
    
- <span data-ttu-id="f2e67-114">ビデオ ストリーム (呼び出し先から発信者)</span><span class="sxs-lookup"><span data-stu-id="f2e67-114">Video Stream (Callee to Caller)</span></span>
    
<span data-ttu-id="f2e67-p101">特定のレポートに表示されるカテゴリと指標は、セッションの種類と、セッションで使用されたエンドポイントの種類に依存します。たとえば、音声のみの通話では、通話にビデオ ストリームがないことにより、ビデオ ストリームの指標は報告されません。同様に、呼び出し先統計はないが、発信者統計を示すレポートがあることがあります。この原因は通常、呼び出し先が SIP 準拠のデバイスを使用していないことです。エンドポイントは通話の終了後に、統計を報告します。しかし、(SIP または SIP 統計を関知しない) 携帯電話は、その種類の情報を報告することはできません。電話の相手先が携帯電話で応答した場合は、通話の終了時に、その携帯電話からのレポートは得られません。</span><span class="sxs-lookup"><span data-stu-id="f2e67-p101">Keep in mind that the categories and the metrics you see on a given report depend on two things: the type of session and the type of endpoints used in the session. For example, an audio-only call will not report metrics for video streams; that's because the call didn't have a video stream. Likewise, you might have a report that lists caller statistics but not callee statistics. That's typically because the callee was not using a SIP-compliant device. Endpoints are responsible for reporting statistics at the end of a call; however, a cell phone (which knows nothing about SIP or SIP statistics) is unable to report that kind of information. If you call someone and they answer you on their cell phone, you will not get a report from that cell phone when the call ends.</span></span>
  
<span data-ttu-id="f2e67-121">通話の詳細レポートは、特定の通話でメディアの品質の問題が発生した理由を正確に確認するときに最も役立ちます。</span><span class="sxs-lookup"><span data-stu-id="f2e67-121">The Call Detail Report is most useful when you are trying to determine exactly why a given call experienced media quality problems.</span></span>
  
## <a name="accessing-the-call-detail-report"></a><span data-ttu-id="f2e67-122">通話の詳細レポートを表示する</span><span class="sxs-lookup"><span data-stu-id="f2e67-122">Accessing the Call Detail Report</span></span>

<span data-ttu-id="f2e67-123">通話の詳細レポートは、以下の任意のレポートから表示できます。</span><span class="sxs-lookup"><span data-stu-id="f2e67-123">The Call Detail Report can be accessed from any of the following reports:</span></span>
  
- <span data-ttu-id="f2e67-124">[ビジネス サーバー 2015 の Skype での場所のレポート](location-report.md)] をクリックして電話の数または不適切な呼び出しの割合のメトリックのいずれか)</span><span class="sxs-lookup"><span data-stu-id="f2e67-124">The [Location Report in Skype for Business Server 2015](location-report.md) (by clicking either the Call volume or the Poor call percentage metric)</span></span>
    
- <span data-ttu-id="f2e67-125">[ビジネス サーバー 2015 の Skype でのメディア品質概要レポート](summary.md)] をクリックして通話量または不適切な呼び出しの割合のメトリックのいずれか)</span><span class="sxs-lookup"><span data-stu-id="f2e67-125">The [Media Quality Summary Report in Skype for Business Server 2015](summary.md) (by clicking either the Call volume or Poor call percentage metric)</span></span>
    
- <span data-ttu-id="f2e67-126">[ビジネス サーバー 2015 の Skype でメディアの品質の比較レポート](comparison.md)([ビジネス サーバー 2015 の Skype での一覧のレポートを呼び出す](call-list-report-0.md)] をクリックし、[詳細] のメトリックをクリック) します。</span><span class="sxs-lookup"><span data-stu-id="f2e67-126">The [Media Quality Comparison Report in Skype for Business Server 2015](comparison.md) (by clicking the [Call List Report in Skype for Business Server 2015](call-list-report-0.md) and then clicking the Detail metric).</span></span>
    
- <span data-ttu-id="f2e67-127">[ビジネス サーバー 2015 の Skype のサーバー パフォーマンス レポート](server-performance.md)] をクリックして通話量または不適切な呼び出しの割合のメトリックのいずれか)</span><span class="sxs-lookup"><span data-stu-id="f2e67-127">The [Server Performance Report in Skype for Business Server 2015](server-performance.md) (by clicking either the Call volume or Poor call percentage metric)</span></span>
    
- <span data-ttu-id="f2e67-128">[ビジネス サーバー 2015 の Skype での一覧のレポートを呼び出す](call-list-report-0.md)] をクリックして、[詳細] のメトリック)</span><span class="sxs-lookup"><span data-stu-id="f2e67-128">The [Call List Report in Skype for Business Server 2015](call-list-report-0.md) (by clicking the Detail metric)</span></span>
    
<span data-ttu-id="f2e67-129">呼び出しの詳細レポート内からに次の測定値のいずれかをクリックすると、[ビジネス サーバー 2015 の Skype でのデバイスのレポート](device-report.md)をアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="f2e67-129">From within the Call Detail Report you can access the [Device Report in Skype for Business Server 2015](device-report.md) by clicking either of the following metrics:</span></span>
  
- <span data-ttu-id="f2e67-130">[キャプチャ デバイス]</span><span class="sxs-lookup"><span data-stu-id="f2e67-130">Capture device</span></span>
    
- <span data-ttu-id="f2e67-131">[レンダー デバイス]</span><span class="sxs-lookup"><span data-stu-id="f2e67-131">Render device</span></span>
    
<span data-ttu-id="f2e67-132">また、音声ビデオ エッジ サーバー指標をクリックすると、サーバー メディア品質傾向レポートを表示できます。</span><span class="sxs-lookup"><span data-stu-id="f2e67-132">You can also access the Server Media Quality Trend Report by clicking the A/V edge server metric.</span></span>
  
## <a name="making-the-best-use-of-the-call-detail-report"></a><span data-ttu-id="f2e67-133">通話の詳細レポートの活用</span><span class="sxs-lookup"><span data-stu-id="f2e67-133">Making the Best Use of the Call Detail Report</span></span>

<span data-ttu-id="f2e67-p102">通話の詳細レポートには、一般的には、マイクのタイムスタンプの誤差、低 SNR 時間、および近端エコー時間の項目のような、250 個以上のさまざまな指標が含まれます。これらの指標の詳細が思い出せない場合は、指標のラベル上にマウス ポインターを置きます。多くの場合は、その指標を説明するツール ヒントが表示されます。</span><span class="sxs-lookup"><span data-stu-id="f2e67-p102">The Call Detail Report typically includes over 250 different metrics, including such items as Microphone timestamp drift, Low SNR time, and Near end to echo time. If you can't remember what all of these metrics actually measure, try holding your mouse over the metric label; often-times, a tooltip will appear describing that metric.</span></span>
  
<span data-ttu-id="f2e67-p103">特定の測定値が見つからない場合は、検索ボックスに測定値ラベルの一部を入力して、次に [**検索**] をクリックします。たとえば、低 SNR 時間測定値が見つからない場合は、検索ボックスに "SNR" と入力して、次に [**検索**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f2e67-p103">If you have problems locating a metric, type part of the metric label in the search box, and then click **Find**. For example, if you can't find the Low SNR time metric, type SNR in the search box, and then click **Find**.</span></span>
  
<span data-ttu-id="f2e67-p104">レポートは、通話に関する情報を記録するだけです。通話自体は記録されません。</span><span class="sxs-lookup"><span data-stu-id="f2e67-p104">Note that the report only tracks information about a call. The call itself is not recorded.</span></span>
  
## <a name="filters"></a><span data-ttu-id="f2e67-140">フィルター</span><span class="sxs-lookup"><span data-stu-id="f2e67-140">Filters</span></span>

<span data-ttu-id="f2e67-p105">なし。通話の詳細レポートにはフィルターを適用できません。</span><span class="sxs-lookup"><span data-stu-id="f2e67-p105">None. You cannot filter the Call Detail Report.</span></span>
  
## <a name="metrics"></a><span data-ttu-id="f2e67-143">指標</span><span class="sxs-lookup"><span data-stu-id="f2e67-143">Metrics</span></span>

<span data-ttu-id="f2e67-144">次の表に、各通話の通話の詳細レポートで提供される情報を示します。</span><span class="sxs-lookup"><span data-stu-id="f2e67-144">The following table lists the information provided in the Call Detail Report for each call.</span></span>
  
<span data-ttu-id="f2e67-145">**詳細レポートのメトリックを呼び出す**</span><span class="sxs-lookup"><span data-stu-id="f2e67-145">**Call Detail Report Metrics**</span></span>

|<span data-ttu-id="f2e67-146">**名**</span><span class="sxs-lookup"><span data-stu-id="f2e67-146">**Name**</span></span>|<span data-ttu-id="f2e67-147">**この項目を並べ替えることができますか。**</span><span class="sxs-lookup"><span data-stu-id="f2e67-147">**Can you sort on this item?**</span></span>|<span data-ttu-id="f2e67-148">**説明**</span><span class="sxs-lookup"><span data-stu-id="f2e67-148">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="f2e67-149">**[発信者 PAI]**</span><span class="sxs-lookup"><span data-stu-id="f2e67-149">**Caller PAI**</span></span> <br/> |<span data-ttu-id="f2e67-150">不可</span><span class="sxs-lookup"><span data-stu-id="f2e67-150">No</span></span>  <br/> |<span data-ttu-id="f2e67-p106">呼び出しを開始したユーザーの P-Asserted-Identity。P-Asserted-Identity は、信頼されたネットワーク内でユーザーの証明済み ID を送信するのに使用されます。</span><span class="sxs-lookup"><span data-stu-id="f2e67-p106">P-Asserted-Identity of the user who initiated the call. The P-Asserted-Identity is used to convey the proven identity of a user within a trusted network.</span></span>  <br/> |
|<span data-ttu-id="f2e67-153">**[発信者 URI]**</span><span class="sxs-lookup"><span data-stu-id="f2e67-153">**Caller URI**</span></span> <br/> |<span data-ttu-id="f2e67-154">不可</span><span class="sxs-lookup"><span data-stu-id="f2e67-154">No</span></span>  <br/> |<span data-ttu-id="f2e67-155">呼び出しを開始したユーザーの SIP アドレス。</span><span class="sxs-lookup"><span data-stu-id="f2e67-155">SIP address of the user who initiated the call.</span></span>  <br/> |
|<span data-ttu-id="f2e67-156">**[発信者エンドポイント]**</span><span class="sxs-lookup"><span data-stu-id="f2e67-156">**Caller endpoint**</span></span> <br/> |<span data-ttu-id="f2e67-157">不可</span><span class="sxs-lookup"><span data-stu-id="f2e67-157">No</span></span>  <br/> |<span data-ttu-id="f2e67-158">呼び出しを実行したデバイス。</span><span class="sxs-lookup"><span data-stu-id="f2e67-158">Device used to make the call.</span></span>  <br/> |
|<span data-ttu-id="f2e67-159">**[発信者ユーザー エージェント]**</span><span class="sxs-lookup"><span data-stu-id="f2e67-159">**Caller user agent**</span></span> <br/> |<span data-ttu-id="f2e67-160">不可</span><span class="sxs-lookup"><span data-stu-id="f2e67-160">No</span></span>  <br/> |<span data-ttu-id="f2e67-161">呼び出しを実行したデバイスで使用されるソフトウェア。</span><span class="sxs-lookup"><span data-stu-id="f2e67-161">Software used on the device that made the call.</span></span>  <br/> |
|<span data-ttu-id="f2e67-162">**[通話の開始]**</span><span class="sxs-lookup"><span data-stu-id="f2e67-162">**Call start**</span></span> <br/> |<span data-ttu-id="f2e67-163">不可</span><span class="sxs-lookup"><span data-stu-id="f2e67-163">No</span></span>  <br/> |<span data-ttu-id="f2e67-164">呼び出しが最初に開始された日時。</span><span class="sxs-lookup"><span data-stu-id="f2e67-164">Date and time that the call was initially placed.</span></span>  <br/> |
|<span data-ttu-id="f2e67-165">**[仲介サーバーのバイパス通話]**</span><span class="sxs-lookup"><span data-stu-id="f2e67-165">**Mediation Server bypass call**</span></span> <br/> |<span data-ttu-id="f2e67-166">不可</span><span class="sxs-lookup"><span data-stu-id="f2e67-166">No</span></span>  <br/> |<span data-ttu-id="f2e67-167">呼び出しが仲介サーバーを経由せずに PSTN 音声ゲートウェイまたは適切な IP-PBX に接続されたかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="f2e67-167">Indicates whether the call connected to a PSTN voice gateway or qualified IP-PBX without passing through the Mediation Server.</span></span>  <br/> |
|<span data-ttu-id="f2e67-168">**[発信者 OS]**</span><span class="sxs-lookup"><span data-stu-id="f2e67-168">**Caller OS**</span></span> <br/> |<span data-ttu-id="f2e67-169">不可</span><span class="sxs-lookup"><span data-stu-id="f2e67-169">No</span></span>  <br/> |<span data-ttu-id="f2e67-170">呼び出し元のコンピューターのオペレーティング システム。</span><span class="sxs-lookup"><span data-stu-id="f2e67-170">Operating system of the caller's computer.</span></span>  <br/> |
|<span data-ttu-id="f2e67-171">**[発信者 CPU]**</span><span class="sxs-lookup"><span data-stu-id="f2e67-171">**Caller CPU**</span></span> <br/> |<span data-ttu-id="f2e67-172">不可</span><span class="sxs-lookup"><span data-stu-id="f2e67-172">No</span></span>  <br/> |<span data-ttu-id="f2e67-173">呼び出しを開始したユーザーのコンピューターに搭載される CPU。</span><span class="sxs-lookup"><span data-stu-id="f2e67-173">CPU installed in the computer of the user who initiated the call.</span></span>  <br/> |
|<span data-ttu-id="f2e67-174">**[発信者 CPU コア番号]**</span><span class="sxs-lookup"><span data-stu-id="f2e67-174">**Caller CPU core number**</span></span> <br/> |<span data-ttu-id="f2e67-175">不可</span><span class="sxs-lookup"><span data-stu-id="f2e67-175">No</span></span>  <br/> |<span data-ttu-id="f2e67-176">呼び出しを開始したユーザーが使用するコンピューターのプロセッサ番号。</span><span class="sxs-lookup"><span data-stu-id="f2e67-176">Processor number in the computer used by the person who initiated the call.</span></span>  <br/> |
|<span data-ttu-id="f2e67-177">**[発信者 CPU 速度]**</span><span class="sxs-lookup"><span data-stu-id="f2e67-177">**Caller CPU speed**</span></span> <br/> |<span data-ttu-id="f2e67-178">不可</span><span class="sxs-lookup"><span data-stu-id="f2e67-178">No</span></span>  <br/> |<span data-ttu-id="f2e67-179">呼び出しを開始したユーザーが使用するコンピューターの CPU のクロック速度。</span><span class="sxs-lookup"><span data-stu-id="f2e67-179">Clock speed of the CPU of the computer used by the person who initiated the call.</span></span>  <br/> |
|<span data-ttu-id="f2e67-180">**[発信者 CPU 仮想化]**</span><span class="sxs-lookup"><span data-stu-id="f2e67-180">**Caller CPU virtualization**</span></span> <br/> |<span data-ttu-id="f2e67-181">不可</span><span class="sxs-lookup"><span data-stu-id="f2e67-181">No</span></span>  <br/> |<span data-ttu-id="f2e67-182">呼び出しを開始したユーザーが使用するコンピューターでの仮想化 (仮想化されている場合)。</span><span class="sxs-lookup"><span data-stu-id="f2e67-182">Virtualization (if any) used on the computer used by the person who initiated the call.</span></span>  <br/> |
|<span data-ttu-id="f2e67-183">**[呼び出し先 PAI]**</span><span class="sxs-lookup"><span data-stu-id="f2e67-183">**Callee PAI**</span></span> <br/> |<span data-ttu-id="f2e67-184">不可</span><span class="sxs-lookup"><span data-stu-id="f2e67-184">No</span></span>  <br/> |<span data-ttu-id="f2e67-p107">通話に招待されたユーザーの P-Asserted-Identity。P-Asserted-Identity は、信頼されたネットワーク内でユーザーの証明済み ID を送信するのに使用されます。</span><span class="sxs-lookup"><span data-stu-id="f2e67-p107">P-Asserted-Identity of the user who was invited to join the call. The P-Asserted-Identity is used to convey the proven identity of a user within a trusted network.</span></span>  <br/> |
|<span data-ttu-id="f2e67-187">**[呼び出し先 URI]**</span><span class="sxs-lookup"><span data-stu-id="f2e67-187">**Callee URI**</span></span> <br/> |<span data-ttu-id="f2e67-188">不可</span><span class="sxs-lookup"><span data-stu-id="f2e67-188">No</span></span>  <br/> |<span data-ttu-id="f2e67-189">呼び出し先ユーザーの SIP アドレス。</span><span class="sxs-lookup"><span data-stu-id="f2e67-189">SIP address of the user who was called.</span></span>  <br/> |
|<span data-ttu-id="f2e67-190">**[呼び出し先エンドポイント]**</span><span class="sxs-lookup"><span data-stu-id="f2e67-190">**Callee endpoint**</span></span> <br/> |<span data-ttu-id="f2e67-191">不可</span><span class="sxs-lookup"><span data-stu-id="f2e67-191">No</span></span>  <br/> |<span data-ttu-id="f2e67-192">呼び出しを受信したデバイス。</span><span class="sxs-lookup"><span data-stu-id="f2e67-192">Device used to receive the call.</span></span>  <br/> |
|<span data-ttu-id="f2e67-193">**[呼び出し先ユーザー エージェント]**</span><span class="sxs-lookup"><span data-stu-id="f2e67-193">**Callee user agent**</span></span> <br/> |<span data-ttu-id="f2e67-194">不可</span><span class="sxs-lookup"><span data-stu-id="f2e67-194">No</span></span>  <br/> |<span data-ttu-id="f2e67-195">呼び出しを受信したデバイスで使用されるソフトウェア。</span><span class="sxs-lookup"><span data-stu-id="f2e67-195">Software used on the device that received the call.</span></span>  <br/> |
|<span data-ttu-id="f2e67-196">**[時間]**</span><span class="sxs-lookup"><span data-stu-id="f2e67-196">**Duration**</span></span> <br/> |<span data-ttu-id="f2e67-197">不可</span><span class="sxs-lookup"><span data-stu-id="f2e67-197">No</span></span>  <br/> |<span data-ttu-id="f2e67-198">通話時間。</span><span class="sxs-lookup"><span data-stu-id="f2e67-198">Length of time for the call.</span></span>  <br/> |
|<span data-ttu-id="f2e67-199">**[メディア バイパス警告フラグ]**</span><span class="sxs-lookup"><span data-stu-id="f2e67-199">**Media bypass warning flag**</span></span> <br/> |<span data-ttu-id="f2e67-200">不可</span><span class="sxs-lookup"><span data-stu-id="f2e67-200">No</span></span>  <br/> |<span data-ttu-id="f2e67-201">仲介サーバーがバイパスされたときに発行された警告。</span><span class="sxs-lookup"><span data-stu-id="f2e67-201">Warning issued when the Mediation Server was bypassed.</span></span>  <br/> |
|<span data-ttu-id="f2e67-202">**[呼び出し先 OS]**</span><span class="sxs-lookup"><span data-stu-id="f2e67-202">**Callee OS**</span></span> <br/> |<span data-ttu-id="f2e67-203">不可</span><span class="sxs-lookup"><span data-stu-id="f2e67-203">No</span></span>  <br/> |<span data-ttu-id="f2e67-204">呼び出し先ユーザーのコンピューターのオペレーティング システム。</span><span class="sxs-lookup"><span data-stu-id="f2e67-204">Operating system of the computer for the user who was called.</span></span>  <br/> |
|<span data-ttu-id="f2e67-205">**[呼び出し先 CPU]**</span><span class="sxs-lookup"><span data-stu-id="f2e67-205">**Callee CPU**</span></span> <br/> |<span data-ttu-id="f2e67-206">不可</span><span class="sxs-lookup"><span data-stu-id="f2e67-206">No</span></span>  <br/> |<span data-ttu-id="f2e67-207">呼び出し先ユーザーのコンピューターに搭載される CPU。</span><span class="sxs-lookup"><span data-stu-id="f2e67-207">CPU installed in the computer of the user who was called.</span></span>  <br/> |
|<span data-ttu-id="f2e67-208">**[呼び出し先コア番号]**</span><span class="sxs-lookup"><span data-stu-id="f2e67-208">**Callee core number**</span></span> <br/> |<span data-ttu-id="f2e67-209">いいえ</span><span class="sxs-lookup"><span data-stu-id="f2e67-209">No</span></span>  <br/> |<span data-ttu-id="f2e67-210">呼び出し先ユーザーが使用するコンピューターのプロセッサ番号。</span><span class="sxs-lookup"><span data-stu-id="f2e67-210">Processor number in the computer used by the person who was called.</span></span>  <br/> |
|<span data-ttu-id="f2e67-211">**[呼び出し先 CPU 速度]**</span><span class="sxs-lookup"><span data-stu-id="f2e67-211">**Callee CPU speed**</span></span> <br/> |<span data-ttu-id="f2e67-212">不可</span><span class="sxs-lookup"><span data-stu-id="f2e67-212">No</span></span>  <br/> |<span data-ttu-id="f2e67-213">呼び出し先ユーザーが使用するコンピューターの CPU のクロック速度。</span><span class="sxs-lookup"><span data-stu-id="f2e67-213">Clock speed of the CPU of the computer used by the person who was called.</span></span>  <br/> |
|<span data-ttu-id="f2e67-214">**[呼び出し先 CPU 仮想化]**</span><span class="sxs-lookup"><span data-stu-id="f2e67-214">**Callee CPU virtualization**</span></span> <br/> |<span data-ttu-id="f2e67-215">不可</span><span class="sxs-lookup"><span data-stu-id="f2e67-215">No</span></span>  <br/> |<span data-ttu-id="f2e67-216">呼び出し先ユーザーが使用するコンピューターでの仮想化 (仮想化されている場合)。</span><span class="sxs-lookup"><span data-stu-id="f2e67-216">Virtualization (if any) used on the computer used by the person who was called.</span></span>  <br/> |
   

