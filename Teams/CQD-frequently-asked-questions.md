---
title: 通話品質ダッシュボード (CQD) についてよく寄せられる質問 (FAQ)
ms.author: lolaj
author: LolaJacobsen
manager: serdars
ms.reviewer: mikedav, siunies, gageames
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.collection:
- M365-voice
search.appverid: MET150
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- NOCSH
ms.custom:
- Reporting
- seo-marvel-apr2020
description: よく寄せられる質問 (FAQ) と、Microsoft Teams の通話品質ダッシュボード (CQD) に関する回答を参照してください。
ms.openlocfilehash: f33d66d9c8abb465c6680bacbbd2ff200cf930c6
ms.sourcegitcommit: 90939ad992e65f840e4c2e7a6d18d821621319b4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/09/2020
ms.locfileid: "45086173"
---
# <a name="call-quality-dashboard-cqd-frequently-asked-questions-faq"></a><span data-ttu-id="080f7-103">通話品質ダッシュボード (CQD) についてよく寄せられる質問 (FAQ)</span><span class="sxs-lookup"><span data-stu-id="080f7-103">Call Quality Dashboard (CQD) Frequently asked questions (FAQ)</span></span>

## <a name="frequently-asked-questions"></a><span data-ttu-id="080f7-104">よく寄せられる質問</span><span class="sxs-lookup"><span data-stu-id="080f7-104">Frequently asked questions</span></span>

[<span data-ttu-id="080f7-105">1人以上の会議の出席者が不適切なエクスペリエンスをした場合、CQD は "Good" として通話をマークするのはなぜですか?</span><span class="sxs-lookup"><span data-stu-id="080f7-105">Why does CQD mark a call as "Good" if one or more meeting participants had a poor experience?</span></span>](#why-does-cqd-mark-a-call-as-good-if-one-or-more-meeting-participants-had-a-poor-experience)

[<span data-ttu-id="080f7-106">メジャーの通話回数とユーザー数の値に0.2% の差が表示されるのはなぜですか。また、正確なボリュームを取得するにはどうすればよいですか?</span><span class="sxs-lookup"><span data-stu-id="080f7-106">Why do I see up to 0.2% difference in call and user count values on measures and how to get most accurate volumes? </span></span>](#why-do-i-see-up-to-02-difference-in-call-and-user-count-values-on-measures-and-how-to-get-most-accurate-volumes)

[<span data-ttu-id="080f7-107">CQD v2 のレポートデータが CQD v3 のレポートデータと異なるのはなぜですか?</span><span class="sxs-lookup"><span data-stu-id="080f7-107">Why does my CQD v2 report data look different than the CQD v3 report data? </span></span>](#why-does-my-cqd-v2-report-data-look-different-than-the-cqd-v3-report-data)

[<span data-ttu-id="080f7-108">Skype for Business からの CQD データが Teams の CQD データと異なっているのはなぜですか?</span><span class="sxs-lookup"><span data-stu-id="080f7-108">Why is CQD data from Skype for Business different than CQD data from Teams? </span></span>](#why-is-cqd-data-from-skype-for-business-different-than-cqd-data-from-teams)

[<span data-ttu-id="080f7-109">CQD で EUII が表示されるのはなぜですか?</span><span class="sxs-lookup"><span data-stu-id="080f7-109">Why can't I see EUII in CQD?</span></span>](#why-cant-i-see-euii-in-cqd)

[<span data-ttu-id="080f7-110">チームのみを対象としてフィルター処理したときに、CQD に Skype for Business の情報が表示されるのはなぜですか?</span><span class="sxs-lookup"><span data-stu-id="080f7-110">Why am I seeing Skype for Business information in CQD when I've filtered for Teams only?</span></span>](#why-am-i-seeing-skype-for-business-information-in-cqd-when-ive-filtered-for-teams-only)

### <a name="why-does-cqd-mark-a-call-as-good-if-one-or-more-meeting-participants-had-a-poor-experience"></a><span data-ttu-id="080f7-111">1人以上の会議の出席者が不適切なエクスペリエンスをした場合、CQD は "Good" として通話をマークするのはなぜですか?</span><span class="sxs-lookup"><span data-stu-id="080f7-111">Why does CQD mark a call as "Good" if one or more meeting participants had a poor experience?</span></span>

<span data-ttu-id="080f7-112">CQD で[ストリームの分類](stream-classification-in-call-quality-dashboard.md)に使用するルールを確認します。</span><span class="sxs-lookup"><span data-stu-id="080f7-112">Check out the rules CQD uses for [stream classification](stream-classification-in-call-quality-dashboard.md).</span></span>
 
<span data-ttu-id="080f7-113">オーディオストリームについては、呼び出しの長さに基づいて平均値に基づいて計算される5つの分類子のいずれかが "good" パラメーター内に存在する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="080f7-113">For audio streams, any of the 5 classifiers, which are calculated for the average based on the length of the call, could all be within "good" parameters.</span></span> <span data-ttu-id="080f7-114">これは、ユーザーがオーディオのドロップアウト、静的、または故障に寄与するものを経験していなかったことを意味します。</span><span class="sxs-lookup"><span data-stu-id="080f7-114">It doesn't mean the users didn't experience something that contributed to an audio drop out, static, or glitch.</span></span> 

<span data-ttu-id="080f7-115">ネットワークの問題であったかどうかを判断するには、セッションの平均値と最大値の間のデルタを確認します。</span><span class="sxs-lookup"><span data-stu-id="080f7-115">To determine if it was a network problem, look at the delta between the average values for the session and the max values.</span></span> <span data-ttu-id="080f7-116">[最大値] は、セッション中に最大検出および報告された値です。</span><span class="sxs-lookup"><span data-stu-id="080f7-116">Max values are the maximum detected and reported during the session.</span></span>
 
<span data-ttu-id="080f7-117">このような状況のトラブルシューティングを行う方法の例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="080f7-117">Here's an example of how to troubleshoot this situation.</span></span> <span data-ttu-id="080f7-118">通話中にネットワークトレースを取得したときに、最初の20分間のパケットが失われても、1.5 秒のパケットが残っていて、通話の残りの部分に適しているとします。</span><span class="sxs-lookup"><span data-stu-id="080f7-118">Let's say you take a network trace during a call and the first 20 minutes there are no lost packets but then you have a gap of 1.5 seconds of packets and then good for the remainder of the call.</span></span> <span data-ttu-id="080f7-119">この平均値は、Wireshark trace RTP の分析であっても、10% (0.1) のパケット損失と <なります。</span><span class="sxs-lookup"><span data-stu-id="080f7-119">The average is going to be <10% (0.1) Packet loss even in a Wireshark trace RTP analysis.</span></span> <span data-ttu-id="080f7-120">パケット損失の最大値は何ですか?</span><span class="sxs-lookup"><span data-stu-id="080f7-120">What was the Max Packet Loss?</span></span> <span data-ttu-id="080f7-121">1.5 秒の間の秒数は、30% (0.3) です。</span><span class="sxs-lookup"><span data-stu-id="080f7-121">1.5 Seconds in a 5-second period would be 30% (0.3).</span></span> <span data-ttu-id="080f7-122">5番目のサンプリング期間内に発生しましたか (おそらく、サンプリング期間に分割されている可能性があります)?</span><span class="sxs-lookup"><span data-stu-id="080f7-122">Did that occur within the five second sampling period (maybe or it could be split over the sampling period)?</span></span>
 
<span data-ttu-id="080f7-123">ネットワークメトリックが [平均] と [最大値] に適切に表示される場合は、他のテレメトリデータを参照します。</span><span class="sxs-lookup"><span data-stu-id="080f7-123">If network metrics look good in the averages and max values, then look to other telemetry data:</span></span> 
- <span data-ttu-id="080f7-124">CPU 不足イベント比率を確認して、検出された CPU リソースが不足していて、品質が低品質であるかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="080f7-124">Check CPU Insufficient Event Ratio to see if the detected CPU resources available were insufficient and caused poor quality.</span></span> 
- <span data-ttu-id="080f7-125">スピーカーに近いマイクによるフィードバックを防ぐため、半二重モードのオーディオデバイスになりましたか?</span><span class="sxs-lookup"><span data-stu-id="080f7-125">Was the audio device in Half Duplex mode to prevent feedback due to microphones that are to close to speakers?</span></span> 
- <span data-ttu-id="080f7-126">デバイスの半二重 AEC イベント比率を確認します。</span><span class="sxs-lookup"><span data-stu-id="080f7-126">Check the Device Half Duplex AEC Event Ratio.</span></span> <span data-ttu-id="080f7-127">ハブまたはドッキングステーションに接続したときに、USB オーディオのドロップアウトによって、デバイスグリッチノイズまたはマイクグリッチノイズ音が聞こえます。</span><span class="sxs-lookup"><span data-stu-id="080f7-127">Was the device glitching or the microphone glitching introducing noise or static due to USB Audio Drop outs when plugged into a Hub or Docking Station:</span></span>  
- <span data-ttu-id="080f7-128">デバイスのエラーとマイクのイベント比率を確認します。</span><span class="sxs-lookup"><span data-stu-id="080f7-128">Check the Device Glitches and Microphone glitches event ratios.</span></span> <span data-ttu-id="080f7-129">デバイス自体が正常に機能していますか?</span><span class="sxs-lookup"><span data-stu-id="080f7-129">Was the device itself functioning properly?</span></span>  
- <span data-ttu-id="080f7-130">キャプチャとレンダリングデバイスが機能していないことを確認します。</span><span class="sxs-lookup"><span data-stu-id="080f7-130">Check the Capture and Render Device Not Functioning Event Ratios.</span></span>


<span data-ttu-id="080f7-131">CQD テレメトリで利用できるディメンションとメジャーの詳細については、「[通話品質ダッシュボードで利用可能なディメンションと測定値](dimensions-and-measures-available-in-call-quality-dashboard.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="080f7-131">For more on dimensions and measures available in CQD telemetry, read [Dimensions and measurements available in Call Quality Dashboard](dimensions-and-measures-available-in-call-quality-dashboard.md).</span></span>

<span data-ttu-id="080f7-132">バックグラウンドノイズの場合は、[ミュートイベント比率] チェックボックスをオンにして、参加者がミュートにした時間の長さを確認します。</span><span class="sxs-lookup"><span data-stu-id="080f7-132">For background noise, check mute event ratio to see the length of time participants were muted.</span></span>
 
<span data-ttu-id="080f7-133">CQD で詳細なレポートを作成し、会議 ID にフィルターを適用して、会議のすべてのユーザーとストリームを確認し、目的のフィールドを追加します。</span><span class="sxs-lookup"><span data-stu-id="080f7-133">Create detailed reports in CQD and filter on Meeting ID to look at all users and streams in a meeting and add the fields you are interested in.</span></span> <span data-ttu-id="080f7-134">問題を報告しているユーザーが、問題が発生しているユーザーでない可能性があります。</span><span class="sxs-lookup"><span data-stu-id="080f7-134">A user reporting the issue may not be the one that was having the issue.</span></span> <span data-ttu-id="080f7-135">経験を報告しているだけです。</span><span class="sxs-lookup"><span data-stu-id="080f7-135">They are just reporting the experience.</span></span>
 
<span data-ttu-id="080f7-136">テレメトリによって問題が発生するとは限りませんが、お客様の意思決定を確認して通知する方法を理解するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="080f7-136">The telemetry will not necessarily call out the issue, but it can help you better understand where to look and inform your decisions.</span></span> <span data-ttu-id="080f7-137">ネットワーク、デバイス、ドライバーまたはファームウェアの更新、使用、またはユーザーのどちらを使用していますか?</span><span class="sxs-lookup"><span data-stu-id="080f7-137">Is it network, device, driver or firmware updates, usage, or user?</span></span>

### <a name="why-do-i-see-up-to-02-difference-in-call-and-user-count-values-on-measures-and-how-to-get-most-accurate-volumes"></a><span data-ttu-id="080f7-138">メジャーの通話回数とユーザー数の値に0.2% の差が表示されるのはなぜですか。また、正確なボリュームを取得するにはどうすればよいですか?</span><span class="sxs-lookup"><span data-stu-id="080f7-138">Why do I see up to 0.2% difference in call and user count values on measures and how to get most accurate volumes?</span></span> 
<span data-ttu-id="080f7-139">通話カウントとユーザーカウントのメジャーを計算するために、個別の countif 操作が、データセット内の呼び出しまたはユーザー id に対して実行されます。</span><span class="sxs-lookup"><span data-stu-id="080f7-139">To compute call count and user count measures, a distinct countif operation is performed against the call or user identifiers in the data set.</span></span> <span data-ttu-id="080f7-140">大きなデータセットでは、個別の countif 操作に固有の最大0.2% のエラーがあります。</span><span class="sxs-lookup"><span data-stu-id="080f7-140">On large data sets, there is an up to 0.2% error inherent with the distinct countif operation.</span></span> <span data-ttu-id="080f7-141">最も正確なボリュームの場合は、この個別の countif 操作に依存しないため、ストリームカウントのメジャーに依存している必要があります。</span><span class="sxs-lookup"><span data-stu-id="080f7-141">For the most accurate volume, you should rely on stream count measures since they do not rely on this distinct countif operation.</span></span> <span data-ttu-id="080f7-142">データの量を減らすためにフィルター処理を行うと、エラーが発生する可能性がありますが、個別の通話とユーザーカウントでこのエラーの原因が解消されない場合があります。</span><span class="sxs-lookup"><span data-stu-id="080f7-142">Filtering to reduce the data volume may reduce the error but may not eliminate this source of error in distinct call and user counts.</span></span> <span data-ttu-id="080f7-143">メジャーに影響を与える[通話品質ダッシュボードで利用可能な寸法と測定値](dimensions-and-measures-available-in-call-quality-dashboard.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="080f7-143">Refer to [Dimensions and measurements available in Call Quality Dashboard](dimensions-and-measures-available-in-call-quality-dashboard.md) for which measures are impacted.</span></span>

### <a name="why-does-my-cqd-v2-report-data-look-different-than-the-cqd-v3-report-data"></a><span data-ttu-id="080f7-144">CQD v2 のレポートデータが CQD v3 のレポートデータと異なるのはなぜですか?</span><span class="sxs-lookup"><span data-stu-id="080f7-144">Why does my CQD v2 report data look different than the CQD v3 report data?</span></span> 

<span data-ttu-id="080f7-145">CQD v2 と v3 のデータの違いが表示される場合は、データの比較または検証が、集計レベルではなく、"りんごからりんご" と "幅" レベルで行われていることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="080f7-145">If you see data differences between CQD v2 and v3, make sure that data comparison or validation is done on an 'apples-to-apples'  and narrow level, not an aggregated level.</span></span> <span data-ttu-id="080f7-146">たとえば、"建物 30" の WiFi Teams のデスクトップクライアントデータの両方のレポートをフィルター処理する場合、低品質の割合は、v2 と v3 で同じである必要があります。</span><span class="sxs-lookup"><span data-stu-id="080f7-146">For example, if you filter both reports for MSIT 'Building 30' WiFi Teams Desktop client data, the Percentage of Poor Quality should be the same between v2 and v3.</span></span>

<span data-ttu-id="080f7-147">CQDv2 の呼び出しセットアップエラーは、"オーディオ" のモダリティでのみ考慮され、CQDv3 では、すべてのモダリティ (オーディオ、ビデオ、Appsharing) に対してこの分類が発生し、各モダリティストリームで表されます。</span><span class="sxs-lookup"><span data-stu-id="080f7-147">CQDv2 classification for CallSetup failure is only considered for "Audio" modality, in CQDv3 this classification happens for every modality (Audio, Video and Appsharing) and is represented in the respective modality stream.</span></span> 

<span data-ttu-id="080f7-148">Teams の場合、CQDv2 はすべてのモダリティ CQDv3 に同じユーザーフィードバックを適用し、Teams のモダリティにフィードバックベースを適用します。</span><span class="sxs-lookup"><span data-stu-id="080f7-148">For Teams, CQDv2 applies the same user feedback to all modalities CQDv3 applies feedback base on modality for Teams.</span></span>

<span data-ttu-id="080f7-149">CQD V3 の内容</span><span class="sxs-lookup"><span data-stu-id="080f7-149">CQD V3 includes</span></span> 
1. <span data-ttu-id="080f7-150">Skype for Business Server の2019通話</span><span class="sxs-lookup"><span data-stu-id="080f7-150">Skype for Business Server 2019 calls,</span></span> 
2. <span data-ttu-id="080f7-151">Skype ボット通話 (自動応答、通話キュー、会議アナウンスメントサービスなど)</span><span class="sxs-lookup"><span data-stu-id="080f7-151">Skype Bot calls, such as:auto attendant, call queue, conference announcement service,</span></span> 
3. <span data-ttu-id="080f7-152">仮想デスクトップインターフェイス、</span><span class="sxs-lookup"><span data-stu-id="080f7-152">Virtual Desktop Interface,</span></span>
4. <span data-ttu-id="080f7-153">会議ビデオの相互運用機能、</span><span class="sxs-lookup"><span data-stu-id="080f7-153">Conference Video Interop,</span></span>
3. <span data-ttu-id="080f7-154">ライブイベントの発行元と発表者の通話</span><span class="sxs-lookup"><span data-stu-id="080f7-154">Live Events Publisher and Presenter calls, and</span></span> 
4. <span data-ttu-id="080f7-155">PSTN 通話。</span><span class="sxs-lookup"><span data-stu-id="080f7-155">PSTN calls.</span></span> 

<span data-ttu-id="080f7-156">これらの Power BI テンプレートを使用して CQD データを分析して報告する方法については、「 [POWER bi FOR CQD レポートを使用](cqd-power-bi-query-templates.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="080f7-156">To learn how to use these Power BI templates to analyze and report your CQD data, read [Use Power BI for CQD reports](cqd-power-bi-query-templates.md).</span></span>


### <a name="why-is-cqd-data-from-skype-for-business-different-than-cqd-data-from-teams"></a><span data-ttu-id="080f7-157">Skype for Business からの CQD データが Teams の CQD データと異なっているのはなぜですか?</span><span class="sxs-lookup"><span data-stu-id="080f7-157">Why is CQD data from Skype for Business different than CQD data from Teams?</span></span> 


> [!IMPORTANT]
> <span data-ttu-id="080f7-158">2020年7月1日以降、古い CQD は最新の CQD のデータにアクセスします。</span><span class="sxs-lookup"><span data-stu-id="080f7-158">As of July 1, 2020, the older CQD accesses data from the latest CQD.</span></span> <span data-ttu-id="080f7-159">古い CQD データは利用できなくなり、文書の作成やレポートのデータをエクスポートすることはできません。</span><span class="sxs-lookup"><span data-stu-id="080f7-159">The older CQD data is no longer available, and you can't export your building or report data.</span></span>


<span data-ttu-id="080f7-160">以前の CQD と Skype for Business の従来のポータル (cqd.lync.com) と最新の CQD の間でデータを比較しようとしている場合は、データが一致していないことがすぐにわかります。</span><span class="sxs-lookup"><span data-stu-id="080f7-160">If you're trying to compare data between the older CQD from the Skype for Business legacy portal (cqd.lync.com) and the latest CQD from the Teams admin center (cqd.teams.microsoft.com), you'll quickly notice that the data doesn't match.</span></span> <span data-ttu-id="080f7-161">これは、最新の CQD で多くの追加の通話シナリオが報告されるためです。</span><span class="sxs-lookup"><span data-stu-id="080f7-161">That's because the latest CQD reports on many additional calling scenarios.</span></span> <span data-ttu-id="080f7-162">以前の CQD のレポートを引き続き使用している場合は、この記事を参照してください。これらのレポートは、 [Skype For Business Server の通話品質ダッシュボード](https://docs.microsoft.com/skypeforbusiness/management-tools/call-quality-dashboard/call-quality-dashboard)を使って解釈することができます。</span><span class="sxs-lookup"><span data-stu-id="080f7-162">If you're still using reports from the older CQD, use this article to help you interpret those reports: [Call Quality Dashboard for Skype for Business Server](https://docs.microsoft.com/skypeforbusiness/management-tools/call-quality-dashboard/call-quality-dashboard).</span></span>



<span data-ttu-id="080f7-163">次に、CQD v2 と CQD v3 のデータを比較するために特定のフィルターを適用する例を示します。</span><span class="sxs-lookup"><span data-stu-id="080f7-163">Here's an example of applying specific filters to compare CQD v2 and CQD v3 data:</span></span>

1. <span data-ttu-id="080f7-164">使用可能な QoE レコード = True</span><span class="sxs-lookup"><span data-stu-id="080f7-164">QoE Record Available = True</span></span>

2. <span data-ttu-id="080f7-165">[追加] は、サーバーペアフィルターの値: Client: client and Client: Server。</span><span class="sxs-lookup"><span data-stu-id="080f7-165">Add Is Server Pair filter with value: Client:Client and Client:Server.</span></span> <span data-ttu-id="080f7-166">ほとんどのテナントでは、サーバー呼び出しを除外します。</span><span class="sxs-lookup"><span data-stu-id="080f7-166">Most tenants prefer to exclude Server:Server calls.</span></span>

3. <span data-ttu-id="080f7-167">ユーザーエージェントカテゴリのフィルターを追加し、自動アテンダント、通話キュー、ボット、Room system、MediationServer、会議アナウンスメントサービス、VDI などのフィルターを追加します。</span><span class="sxs-lookup"><span data-stu-id="080f7-167">Add a filter for User Agent Category and filter out Auto Attendant, Call Queue, Bot, Room system, MediationServer, Conference Announcement service, VDI, etc.</span></span>

:::image type="content" source="media/turning-on-and-using-call-quality-dashboard1.png" alt-text="CQD v3 での特定のフィルターの適用のスクリーンショット":::

:::image type="content" source="media/turning-on-and-using-call-quality-dashboard2.png" alt-text="CQD v2 での特定のフィルターの適用のスクリーンショット":::

#### <a name="other-expected-differences-between-cqd-v2-and-cqd-v3"></a><span data-ttu-id="080f7-170">CQD v2 と CQD v3 とのその他の予想される違い</span><span class="sxs-lookup"><span data-stu-id="080f7-170">Other expected differences between CQD v2 and CQD v3</span></span>

<span data-ttu-id="080f7-171">以前の CQD と最新のバージョンの違いの詳細については、 [「Advanced Call Quality ダッシュボードの](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/Introducing-the-Advanced-Call-Quality-Dashboard/ba-p/972586)ブログを2019年11月5日から紹介する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="080f7-171">To learn more about the differences between the older and latest CQD, read the [Introducing the Advanced Call Quality Dashboard](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/Introducing-the-Advanced-Call-Quality-Dashboard/ba-p/972586) blog, from November 5, 2019.</span></span>


> [!IMPORTANT]
> <span data-ttu-id="080f7-172">2020年7月1日以降、古い CQD は最新の CQD のデータにアクセスします。</span><span class="sxs-lookup"><span data-stu-id="080f7-172">As of July 1, 2020, the older CQD accesses data from the latest CQD.</span></span> <span data-ttu-id="080f7-173">古い CQD データは利用できなくなり、文書の作成やレポートのデータをエクスポートすることはできません。</span><span class="sxs-lookup"><span data-stu-id="080f7-173">The older CQD data is no longer available, and you can't export your building or report data.</span></span>

<span data-ttu-id="080f7-174">以前のバージョンと新しい CQD のレポートでは、集計または概要レベルでより多くのデータの相違が表示される可能性があります。</span><span class="sxs-lookup"><span data-stu-id="080f7-174">You’ll likely see more data differences between your older and newer CQD reports at the aggregated or summary level.</span></span> <span data-ttu-id="080f7-175">データをより細かいレベルで比較すると、"リンゴからりんご" の比較が表示されます。</span><span class="sxs-lookup"><span data-stu-id="080f7-175">If you compare data at a more granular level, you’ll get an “apples-to-apples” comparison.</span></span> <span data-ttu-id="080f7-176">たとえば、個々の建物のデータを見ている場合、低品質のパーセンテージは、以前の CQD レポートと新しいレポートの両方で同じである必要があります。</span><span class="sxs-lookup"><span data-stu-id="080f7-176">For example, if you’re looking at data for an individual building, the Percentage of Poor Quality should be the same between both the older and new CQD reports.</span></span>

- <span data-ttu-id="080f7-177">会社の有線接続、Windows デスクトップ、または1つの地域や建物など、集中するシナリオを選択します。</span><span class="sxs-lookup"><span data-stu-id="080f7-177">Pick a scenario with a tight focus, such as corporate wired connections, Windows Desktops, or a single region or building.</span></span>
- <span data-ttu-id="080f7-178">Teams の [MR]、[TR]、または [MP] の IP 範囲を確認します。</span><span class="sxs-lookup"><span data-stu-id="080f7-178">Check the Teams MR, TR, or MP IP ranges.</span></span> <span data-ttu-id="080f7-179">Teams の範囲は、Skype for Business Online よりも新しいものであり、ファイアウォールに関する接続の問題が発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="080f7-179">The Teams ranges are newer than Skype for Business Online, and that can cause connectivity issues involving firewalls.</span></span>
- <span data-ttu-id="080f7-180">サマリーまたはトップレベルの数値を比較しないでください。</span><span class="sxs-lookup"><span data-stu-id="080f7-180">Don't compare summary or top-level numbers.</span></span> <span data-ttu-id="080f7-181">これらの比較を行うことで、企業の有線接続での Skype for Business Online 通話の大きな通話音量と、LTE またはプライベートネットワーク上での少人数のチーム通話との比較を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="080f7-181">These comparisons will lead you to compare a large call volume of Skype for Business Online calls on a corporate wired connection to a small volume of Teams calls on an LTE or private network.</span></span>
- <span data-ttu-id="080f7-182">位置のバイアスと母集団の相違点に注意してください。多すぎては、次のような違いがあります。</span><span class="sxs-lookup"><span data-stu-id="080f7-182">Beware of location bias and population differences: There are many comparisons that are too dissimilar to be useful:</span></span>
  - <span data-ttu-id="080f7-183">NOAM: APAC</span><span class="sxs-lookup"><span data-stu-id="080f7-183">NOAM : APAC</span></span>
  - <span data-ttu-id="080f7-184">NY: Goa</span><span class="sxs-lookup"><span data-stu-id="080f7-184">NY : Goa</span></span>
  - <span data-ttu-id="080f7-185">有線 : WiFi</span><span class="sxs-lookup"><span data-stu-id="080f7-185">Wired : wifi</span></span>
  - <span data-ttu-id="080f7-186">企業ネットワーク: ホームネットワーク</span><span class="sxs-lookup"><span data-stu-id="080f7-186">Corporate network : home network</span></span>
  
### <a name="why-cant-i-see-euii-in-cqd"></a><span data-ttu-id="080f7-187">CQD で EUII が表示されるのはなぜですか?</span><span class="sxs-lookup"><span data-stu-id="080f7-187">Why can't I see EUII in CQD?</span></span>

<span data-ttu-id="080f7-188">次の管理者ロールは、CQD にアクセスできますが、EUII (エンドユーザーを特定できる情報) を表示することはできません。</span><span class="sxs-lookup"><span data-stu-id="080f7-188">These admin roles can access CQD, but they can't view EUII (end-user identifiable information):</span></span>
- <span data-ttu-id="080f7-189">Microsoft 365 レポートリーダー</span><span class="sxs-lookup"><span data-stu-id="080f7-189">Microsoft 365 Reports Reader</span></span>
- <span data-ttu-id="080f7-190">Teams 通信サポート スペシャリスト</span><span class="sxs-lookup"><span data-stu-id="080f7-190">Teams Communications Support Specialist</span></span>

<span data-ttu-id="080f7-191">CQD にアクセスできる役割の詳細については、「 [CQD にアクセスするための役割の割り当て](turning-on-and-using-call-quality-dashboard.md#assign-admin-roles-for-access-to-cqd)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="080f7-191">To learn more about roles that can access CQD - including EUII - read [Assign roles for accessing CQD](turning-on-and-using-call-quality-dashboard.md#assign-admin-roles-for-access-to-cqd).</span></span>

### <a name="why-am-i-seeing-skype-for-business-information-in-cqd-when-ive-filtered-for-teams-only"></a><span data-ttu-id="080f7-192">チームのみを対象としてフィルター処理したときに、CQD に Skype for Business の情報が表示されるのはなぜですか?</span><span class="sxs-lookup"><span data-stu-id="080f7-192">Why am I seeing Skype for Business information in CQD when I've filtered for Teams only?</span></span>

<span data-ttu-id="080f7-193">CQD レポート (isTeams = 1) でのみチームをフィルター処理している場合、*第1のエンドポイント*が Teams であるすべての通話をフィルター処理します。</span><span class="sxs-lookup"><span data-stu-id="080f7-193">When you filter for Teams only in CQD reports (isTeams = 1), you're filtering for all calls where the *first endpoint* is Teams.</span></span> <span data-ttu-id="080f7-194">*第2のエンドポイント*が Skype for business の場合、その情報が CQD レポートに表示されます。</span><span class="sxs-lookup"><span data-stu-id="080f7-194">If the *second endpoint* is Skype for Business, that information will show up in your CQD report.</span></span>

<span data-ttu-id="080f7-195">CQDv2 と CQDv3 は、CQDv2 にはない新しいシナリオが用意されているため、常に合計数が異なる場合があります。</span><span class="sxs-lookup"><span data-stu-id="080f7-195">CQDv2 and CQDv3 will always have different total counts since CQDv3 will have new scenarios that CQDv2 will not have.</span></span> <span data-ttu-id="080f7-196">このため、サマリーの合計を比較したり、フィルターを使わずにすべての数値を集計したりすると、このような違いがあります。</span><span class="sxs-lookup"><span data-stu-id="080f7-196">That’s why comparing Summary Total or Aggregated all-up numbers with no filters will have these expected differences.</span></span>  

<span data-ttu-id="080f7-197">お客様のシナリオに応じて、CQDv3 には SFB 2019 オンプレミスの通話 (データコネクタと共に SFB 2019 を使用している場合)、Skype ボット通話 (AA、CVI、VDI)、ライブイベント、PSTN 通話が含まれます。</span><span class="sxs-lookup"><span data-stu-id="080f7-197">Depending on Customers’ scenario, CQDv3 will include SFB 2019 on-premises calls (if SFB 2019 is used with a data connector), Skype Bot calls (AA, CVI, VDI), Live Events and PSTN calls.</span></span> <span data-ttu-id="080f7-198">顧客に提供されているが、そのデータは CQD V2 に含まれていないシナリオ/機能。</span><span class="sxs-lookup"><span data-stu-id="080f7-198">Scenarios/Features which are available for the customers, but their data are not in CQD V2.</span></span>

<span data-ttu-id="080f7-199">たとえば、お客様には、20万オーディオストリームが表示され、CQD V2 サマリーレポートで5000エラーが発生することが予想されます。CQD V3 の5500のエラー (2019 オンプレミス通話、CVI 通話、PSTN 通話など) と30万オーディオストリーム。</span><span class="sxs-lookup"><span data-stu-id="080f7-199">For instance, it is expected that your customers and you will see 200,000 audio streams, with 5000 failures in CQD V2 Summary Report; versus 300,000 audio streams with 5500 failures (coming from 2019 on-prem calls, CVI calls, PSTN calls etc) in CQD V3.</span></span>

<span data-ttu-id="080f7-200">予期しない違いがある場合は、データ全体のさまざまな内訳を確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="080f7-200">In order to determine, if there are any unexpected differences, you must look at various breakdowns of the overall data.</span></span>  <span data-ttu-id="080f7-201">目的に合わせて比較します。</span><span class="sxs-lookup"><span data-stu-id="080f7-201">Compare with intent.</span></span>  <span data-ttu-id="080f7-202">ユーザーエージェントカテゴリペア別のデータのスライスは、最初に推奨されるものの1つです。</span><span class="sxs-lookup"><span data-stu-id="080f7-202">Slicing the data by User Agent Category Pair is one of the first things we recommend.</span></span>  <span data-ttu-id="080f7-203">*第1の製品*と*第2の製品*は、スライサーとしても優れています。</span><span class="sxs-lookup"><span data-stu-id="080f7-203">*First Product* and *Second Product* are also good slicers.</span></span>  


## <a name="related-topics"></a><span data-ttu-id="080f7-204">関連項目</span><span class="sxs-lookup"><span data-stu-id="080f7-204">Related topics</span></span>

[<span data-ttu-id="080f7-205">Teams の通話品質を向上させて監視する</span><span class="sxs-lookup"><span data-stu-id="080f7-205">Improve and monitor call quality for Teams</span></span>](monitor-call-quality-qos.md)

[<span data-ttu-id="080f7-206">CQD とは何ですか?</span><span class="sxs-lookup"><span data-stu-id="080f7-206">What is CQD?</span></span>](CQD-what-is-call-quality-dashboard.md)

[<span data-ttu-id="080f7-207">通話品質ダッシュボード (CQD) を設定する</span><span class="sxs-lookup"><span data-stu-id="080f7-207">Set up Call Quality Dashboard (CQD)</span></span>](turning-on-and-using-call-quality-dashboard.md)

[<span data-ttu-id="080f7-208">テナントのアップロードとデータの構築</span><span class="sxs-lookup"><span data-stu-id="080f7-208">Upload tenant and building data</span></span>](CQD-upload-tenant-building-data.md)

[<span data-ttu-id="080f7-209">CQD データとレポート</span><span class="sxs-lookup"><span data-stu-id="080f7-209">CQD data and reports</span></span>](CQD-data-and-reports.md)

[<span data-ttu-id="080f7-210">CQD を使用して通話と会議の品質を管理する</span><span class="sxs-lookup"><span data-stu-id="080f7-210">Use CQD to manage call and meeting quality</span></span>](quality-of-experience-review-guide.md)

[<span data-ttu-id="080f7-211">CQD で使用できるディメンションとメジャー</span><span class="sxs-lookup"><span data-stu-id="080f7-211">Dimensions and measures available in CQD</span></span>](dimensions-and-measures-available-in-call-quality-dashboard.md)

[<span data-ttu-id="080f7-212">CQD でのストリームの分類</span><span class="sxs-lookup"><span data-stu-id="080f7-212">Stream Classification in CQD</span></span>](stream-classification-in-call-quality-dashboard.md)

[<span data-ttu-id="080f7-213">Power BI を使用して CQD データを分析する</span><span class="sxs-lookup"><span data-stu-id="080f7-213">Use Power BI to analyze CQD data</span></span>](CQD-Power-BI-query-templates.md)

[<span data-ttu-id="080f7-214">チームのトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="080f7-214">Teams Troubleshooting</span></span>](https://docs.microsoft.com/MicrosoftTeams/troubleshoot/teams)