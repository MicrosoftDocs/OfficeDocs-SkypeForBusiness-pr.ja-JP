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
ms.openlocfilehash: 43dd0f85c21914320ff48c2e0aab82614670ff90
ms.sourcegitcommit: 3e5cac88911611c94c0330bf50af9c34db308cdf
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/22/2020
ms.locfileid: "45372126"
---
# <a name="call-quality-dashboard-cqd-frequently-asked-questions-faq"></a><span data-ttu-id="b2857-103">通話品質ダッシュボード (CQD) についてよく寄せられる質問 (FAQ)</span><span class="sxs-lookup"><span data-stu-id="b2857-103">Call Quality Dashboard (CQD) Frequently asked questions (FAQ)</span></span>

## <a name="frequently-asked-questions"></a><span data-ttu-id="b2857-104">よく寄せられる質問</span><span class="sxs-lookup"><span data-stu-id="b2857-104">Frequently asked questions</span></span>

[<span data-ttu-id="b2857-105">1人以上の会議の出席者が不適切なエクスペリエンスをした場合、CQD は "Good" として通話をマークするのはなぜですか?</span><span class="sxs-lookup"><span data-stu-id="b2857-105">Why does CQD mark a call as "Good" if one or more meeting participants had a poor experience?</span></span>](#why-does-cqd-mark-a-call-as-good-if-one-or-more-meeting-participants-had-a-poor-experience)

[<span data-ttu-id="b2857-106">メジャーの通話回数とユーザー数の値に0.2% の差が表示されるのはなぜですか。また、正確なボリュームを取得するにはどうすればよいですか?</span><span class="sxs-lookup"><span data-stu-id="b2857-106">Why do I see up to 0.2% difference in call and user count values on measures and how to get most accurate volumes? </span></span>](#why-do-i-see-up-to-02-difference-in-call-and-user-count-values-on-measures-and-how-to-get-most-accurate-volumes)

[<span data-ttu-id="b2857-107">Skype for Business からの CQD データが Teams の CQD データと異なっているのはなぜですか?</span><span class="sxs-lookup"><span data-stu-id="b2857-107">Why is CQD data from Skype for Business different than CQD data from Teams? </span></span>](#why-is-cqd-data-from-skype-for-business-different-than-cqd-data-from-teams)

[<span data-ttu-id="b2857-108">CQD で EUII が表示されるのはなぜですか?</span><span class="sxs-lookup"><span data-stu-id="b2857-108">Why can't I see EUII in CQD?</span></span>](#why-cant-i-see-euii-in-cqd)

[<span data-ttu-id="b2857-109">チームのみを対象としてフィルター処理したときに、CQD に Skype for Business の情報が表示されるのはなぜですか?</span><span class="sxs-lookup"><span data-stu-id="b2857-109">Why am I seeing Skype for Business information in CQD when I've filtered for Teams only?</span></span>](#why-am-i-seeing-skype-for-business-information-in-cqd-when-ive-filtered-for-teams-only)

### <a name="why-does-cqd-mark-a-call-as-good-if-one-or-more-meeting-participants-had-a-poor-experience"></a><span data-ttu-id="b2857-110">1人以上の会議の出席者が不適切なエクスペリエンスをした場合、CQD は "Good" として通話をマークするのはなぜですか?</span><span class="sxs-lookup"><span data-stu-id="b2857-110">Why does CQD mark a call as "Good" if one or more meeting participants had a poor experience?</span></span>

<span data-ttu-id="b2857-111">CQD で[ストリームの分類](stream-classification-in-call-quality-dashboard.md)に使用するルールを確認します。</span><span class="sxs-lookup"><span data-stu-id="b2857-111">Check out the rules CQD uses for [stream classification](stream-classification-in-call-quality-dashboard.md).</span></span>
 
<span data-ttu-id="b2857-112">オーディオストリームについては、呼び出しの長さに基づいて平均値に基づいて計算される5つの分類子のいずれかが "good" パラメーター内に存在する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="b2857-112">For audio streams, any of the 5 classifiers, which are calculated for the average based on the length of the call, could all be within "good" parameters.</span></span> <span data-ttu-id="b2857-113">これは、ユーザーがオーディオのドロップアウト、静的、または故障に寄与するものを経験していなかったことを意味します。</span><span class="sxs-lookup"><span data-stu-id="b2857-113">It doesn't mean the users didn't experience something that contributed to an audio drop out, static, or glitch.</span></span> 

<span data-ttu-id="b2857-114">ネットワークの問題であったかどうかを判断するには、セッションの平均値と最大値の間のデルタを確認します。</span><span class="sxs-lookup"><span data-stu-id="b2857-114">To determine if it was a network problem, look at the delta between the average values for the session and the max values.</span></span> <span data-ttu-id="b2857-115">[最大値] は、セッション中に最大検出および報告された値です。</span><span class="sxs-lookup"><span data-stu-id="b2857-115">Max values are the maximum detected and reported during the session.</span></span>
 
<span data-ttu-id="b2857-116">このような状況のトラブルシューティングを行う方法の例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="b2857-116">Here's an example of how to troubleshoot this situation.</span></span> <span data-ttu-id="b2857-117">通話中にネットワークトレースを取得したときに、最初の20分間のパケットが失われても、1.5 秒のパケットが残っていて、通話の残りの部分に適しているとします。</span><span class="sxs-lookup"><span data-stu-id="b2857-117">Let's say you take a network trace during a call and the first 20 minutes there are no lost packets but then you have a gap of 1.5 seconds of packets and then good for the remainder of the call.</span></span> <span data-ttu-id="b2857-118">この平均値は、Wireshark trace RTP の分析であっても、10% (0.1) のパケット損失と <なります。</span><span class="sxs-lookup"><span data-stu-id="b2857-118">The average is going to be <10% (0.1) Packet loss even in a Wireshark trace RTP analysis.</span></span> <span data-ttu-id="b2857-119">パケット損失の最大値は何ですか?</span><span class="sxs-lookup"><span data-stu-id="b2857-119">What was the Max Packet Loss?</span></span> <span data-ttu-id="b2857-120">1.5 秒の間の秒数は、30% (0.3) です。</span><span class="sxs-lookup"><span data-stu-id="b2857-120">1.5 Seconds in a 5-second period would be 30% (0.3).</span></span> <span data-ttu-id="b2857-121">5番目のサンプリング期間内に発生しましたか (おそらく、サンプリング期間に分割されている可能性があります)?</span><span class="sxs-lookup"><span data-stu-id="b2857-121">Did that occur within the five second sampling period (maybe or it could be split over the sampling period)?</span></span>
 
<span data-ttu-id="b2857-122">ネットワークメトリックが [平均] と [最大値] に適切に表示される場合は、他のテレメトリデータを参照します。</span><span class="sxs-lookup"><span data-stu-id="b2857-122">If network metrics look good in the averages and max values, then look to other telemetry data:</span></span> 
- <span data-ttu-id="b2857-123">CPU 不足イベント比率を確認して、検出された CPU リソースが不足していて、品質が低品質であるかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="b2857-123">Check CPU Insufficient Event Ratio to see if the detected CPU resources available were insufficient and caused poor quality.</span></span> 
- <span data-ttu-id="b2857-124">スピーカーに近いマイクによるフィードバックを防ぐため、半二重モードのオーディオデバイスになりましたか?</span><span class="sxs-lookup"><span data-stu-id="b2857-124">Was the audio device in Half Duplex mode to prevent feedback due to microphones that are to close to speakers?</span></span> 
- <span data-ttu-id="b2857-125">デバイスの半二重 AEC イベント比率を確認します。</span><span class="sxs-lookup"><span data-stu-id="b2857-125">Check the Device Half Duplex AEC Event Ratio.</span></span> <span data-ttu-id="b2857-126">ハブまたはドッキングステーションに接続したときに、USB オーディオのドロップアウトによって、デバイスグリッチノイズまたはマイクグリッチノイズ音が聞こえます。</span><span class="sxs-lookup"><span data-stu-id="b2857-126">Was the device glitching or the microphone glitching introducing noise or static due to USB Audio Drop outs when plugged into a Hub or Docking Station:</span></span>  
- <span data-ttu-id="b2857-127">デバイスのエラーとマイクのイベント比率を確認します。</span><span class="sxs-lookup"><span data-stu-id="b2857-127">Check the Device Glitches and Microphone glitches event ratios.</span></span> <span data-ttu-id="b2857-128">デバイス自体が正常に機能していますか?</span><span class="sxs-lookup"><span data-stu-id="b2857-128">Was the device itself functioning properly?</span></span>  
- <span data-ttu-id="b2857-129">キャプチャとレンダリングデバイスが機能していないことを確認します。</span><span class="sxs-lookup"><span data-stu-id="b2857-129">Check the Capture and Render Device Not Functioning Event Ratios.</span></span>


<span data-ttu-id="b2857-130">CQD テレメトリで利用できるディメンションとメジャーの詳細については、「[通話品質ダッシュボードで利用可能なディメンションと測定値](dimensions-and-measures-available-in-call-quality-dashboard.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b2857-130">For more on dimensions and measures available in CQD telemetry, read [Dimensions and measurements available in Call Quality Dashboard](dimensions-and-measures-available-in-call-quality-dashboard.md).</span></span>

<span data-ttu-id="b2857-131">バックグラウンドノイズの場合は、[ミュートイベント比率] チェックボックスをオンにして、参加者がミュートにした時間の長さを確認します。</span><span class="sxs-lookup"><span data-stu-id="b2857-131">For background noise, check mute event ratio to see the length of time participants were muted.</span></span>
 
<span data-ttu-id="b2857-132">CQD で詳細なレポートを作成し、会議 ID にフィルターを適用して、会議のすべてのユーザーとストリームを確認し、目的のフィールドを追加します。</span><span class="sxs-lookup"><span data-stu-id="b2857-132">Create detailed reports in CQD and filter on Meeting ID to look at all users and streams in a meeting and add the fields you are interested in.</span></span> <span data-ttu-id="b2857-133">問題を報告しているユーザーが、問題が発生しているユーザーでない可能性があります。</span><span class="sxs-lookup"><span data-stu-id="b2857-133">A user reporting the issue may not be the one that was having the issue.</span></span> <span data-ttu-id="b2857-134">経験を報告しているだけです。</span><span class="sxs-lookup"><span data-stu-id="b2857-134">They are just reporting the experience.</span></span>
 
<span data-ttu-id="b2857-135">テレメトリによって問題が発生するとは限りませんが、お客様の意思決定を確認して通知する方法を理解するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="b2857-135">The telemetry will not necessarily call out the issue, but it can help you better understand where to look and inform your decisions.</span></span> <span data-ttu-id="b2857-136">ネットワーク、デバイス、ドライバーまたはファームウェアの更新、使用、またはユーザーのどちらを使用していますか?</span><span class="sxs-lookup"><span data-stu-id="b2857-136">Is it network, device, driver or firmware updates, usage, or user?</span></span>

### <a name="why-do-i-see-up-to-02-difference-in-call-and-user-count-values-on-measures-and-how-to-get-most-accurate-volumes"></a><span data-ttu-id="b2857-137">メジャーの通話回数とユーザー数の値に0.2% の差が表示されるのはなぜですか。また、正確なボリュームを取得するにはどうすればよいですか?</span><span class="sxs-lookup"><span data-stu-id="b2857-137">Why do I see up to 0.2% difference in call and user count values on measures and how to get most accurate volumes?</span></span> 
<span data-ttu-id="b2857-138">通話カウントとユーザーカウントのメジャーを計算するために、個別の countif 操作が、データセット内の呼び出しまたはユーザー id に対して実行されます。</span><span class="sxs-lookup"><span data-stu-id="b2857-138">To compute call count and user count measures, a distinct countif operation is performed against the call or user identifiers in the data set.</span></span> <span data-ttu-id="b2857-139">大きなデータセットでは、個別の countif 操作に固有の最大0.2% のエラーがあります。</span><span class="sxs-lookup"><span data-stu-id="b2857-139">On large data sets, there is an up to 0.2% error inherent with the distinct countif operation.</span></span> <span data-ttu-id="b2857-140">最も正確なボリュームの場合は、この個別の countif 操作に依存しないため、ストリームカウントのメジャーに依存している必要があります。</span><span class="sxs-lookup"><span data-stu-id="b2857-140">For the most accurate volume, you should rely on stream count measures since they do not rely on this distinct countif operation.</span></span> <span data-ttu-id="b2857-141">データの量を減らすためにフィルター処理を行うと、エラーが発生する可能性がありますが、個別の通話とユーザーカウントでこのエラーの原因が解消されない場合があります。</span><span class="sxs-lookup"><span data-stu-id="b2857-141">Filtering to reduce the data volume may reduce the error but may not eliminate this source of error in distinct call and user counts.</span></span> <span data-ttu-id="b2857-142">メジャーに影響を与える[通話品質ダッシュボードで利用可能な寸法と測定値](dimensions-and-measures-available-in-call-quality-dashboard.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b2857-142">Refer to [Dimensions and measurements available in Call Quality Dashboard](dimensions-and-measures-available-in-call-quality-dashboard.md) for which measures are impacted.</span></span>


### <a name="why-is-cqd-data-from-skype-for-business-different-than-cqd-data-from-teams"></a><span data-ttu-id="b2857-143">Skype for Business からの CQD データが Teams の CQD データと異なっているのはなぜですか?</span><span class="sxs-lookup"><span data-stu-id="b2857-143">Why is CQD data from Skype for Business different than CQD data from Teams?</span></span> 


> [!IMPORTANT]
> <span data-ttu-id="b2857-144">2020年7月1日の時点では、古い CQD (CQD.lync.com) は最新の CQD (CQD のデータを使用しています。Teams.microsoft.com)。</span><span class="sxs-lookup"><span data-stu-id="b2857-144">As of July 1, 2020, the older CQD (CQD.lync.com) uses data from the latest CQD (CQD.Teams.microsoft.com).</span></span> <span data-ttu-id="b2857-145">古い CQD データは利用できなくなり、文書の作成やレポートのデータをエクスポートすることはできません。</span><span class="sxs-lookup"><span data-stu-id="b2857-145">The older CQD data is no longer available, and you can't export your building or report data.</span></span> <span data-ttu-id="b2857-146">引き続き CQD.lync.com (Skype for Business 管理センターから利用可能) は使用できますが、CQD.lync.com へのアクセスはすぐにオフにするため、CQD に移動する必要があります。まだインストールしていない場合は、Teams.microsoft.com します。</span><span class="sxs-lookup"><span data-stu-id="b2857-146">You can still use CQD.lync.com (available from the Skype for Business admin center), but we'll turn off access to CQD.lync.com soon, so you should move to CQD.Teams.microsoft.com if you haven't already done so.</span></span>


<span data-ttu-id="b2857-147">以前の CQD と Skype for Business の従来のポータル (cqd.lync.com) と最新の CQD の間でデータを比較しようとしている場合は、データが一致していないことがすぐにわかります。</span><span class="sxs-lookup"><span data-stu-id="b2857-147">If you're trying to compare data between the older CQD from the Skype for Business legacy portal (cqd.lync.com) and the latest CQD from the Teams admin center (cqd.teams.microsoft.com), you'll quickly notice that the data doesn't match.</span></span> <span data-ttu-id="b2857-148">これは、最新の CQD で多くの追加の通話シナリオが報告されるためです。</span><span class="sxs-lookup"><span data-stu-id="b2857-148">That's because the latest CQD reports on many additional calling scenarios.</span></span> <span data-ttu-id="b2857-149">以前の CQD のレポートを引き続き使用している場合は、この記事を参照してください。これらのレポートは、 [Skype For Business Server の通話品質ダッシュボード](https://docs.microsoft.com/skypeforbusiness/management-tools/call-quality-dashboard/call-quality-dashboard)を使って解釈することができます。</span><span class="sxs-lookup"><span data-stu-id="b2857-149">If you're still using reports from the older CQD, use this article to help you interpret those reports: [Call Quality Dashboard for Skype for Business Server](https://docs.microsoft.com/skypeforbusiness/management-tools/call-quality-dashboard/call-quality-dashboard).</span></span>


  
### <a name="why-cant-i-see-euii-in-cqd"></a><span data-ttu-id="b2857-150">CQD で EUII が表示されるのはなぜですか?</span><span class="sxs-lookup"><span data-stu-id="b2857-150">Why can't I see EUII in CQD?</span></span>

<span data-ttu-id="b2857-151">次の管理者ロールは、CQD にアクセスできますが、EUII (エンドユーザーを特定できる情報) を表示することはできません。</span><span class="sxs-lookup"><span data-stu-id="b2857-151">These admin roles can access CQD, but they can't view EUII (end-user identifiable information):</span></span>
- <span data-ttu-id="b2857-152">Microsoft 365 レポートリーダー</span><span class="sxs-lookup"><span data-stu-id="b2857-152">Microsoft 365 Reports Reader</span></span>
- <span data-ttu-id="b2857-153">Teams 通信サポート スペシャリスト</span><span class="sxs-lookup"><span data-stu-id="b2857-153">Teams Communications Support Specialist</span></span>

<span data-ttu-id="b2857-154">CQD にアクセスできる役割の詳細については、「 [CQD にアクセスするための役割の割り当て](turning-on-and-using-call-quality-dashboard.md#assign-admin-roles-for-access-to-cqd)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b2857-154">To learn more about roles that can access CQD - including EUII - read [Assign roles for accessing CQD](turning-on-and-using-call-quality-dashboard.md#assign-admin-roles-for-access-to-cqd).</span></span>

### <a name="why-am-i-seeing-skype-for-business-information-in-cqd-when-ive-filtered-for-teams-only"></a><span data-ttu-id="b2857-155">チームのみを対象としてフィルター処理したときに、CQD に Skype for Business の情報が表示されるのはなぜですか?</span><span class="sxs-lookup"><span data-stu-id="b2857-155">Why am I seeing Skype for Business information in CQD when I've filtered for Teams only?</span></span>

<span data-ttu-id="b2857-156">CQD レポート (isTeams = 1) でのみチームをフィルター処理している場合、*第1のエンドポイント*が Teams であるすべての通話をフィルター処理します。</span><span class="sxs-lookup"><span data-stu-id="b2857-156">When you filter for Teams only in CQD reports (isTeams = 1), you're filtering for all calls where the *first endpoint* is Teams.</span></span> <span data-ttu-id="b2857-157">*第2のエンドポイント*が Skype for business の場合、その情報が CQD レポートに表示されます。</span><span class="sxs-lookup"><span data-stu-id="b2857-157">If the *second endpoint* is Skype for Business, that information will show up in your CQD report.</span></span>

<span data-ttu-id="b2857-158">CQDv2 と CQDv3 は、CQDv2 にはない新しいシナリオが用意されているため、常に合計数が異なる場合があります。</span><span class="sxs-lookup"><span data-stu-id="b2857-158">CQDv2 and CQDv3 will always have different total counts since CQDv3 will have new scenarios that CQDv2 will not have.</span></span> <span data-ttu-id="b2857-159">このため、サマリーの合計を比較したり、フィルターを使わずにすべての数値を集計したりすると、このような違いがあります。</span><span class="sxs-lookup"><span data-stu-id="b2857-159">That’s why comparing Summary Total or Aggregated all-up numbers with no filters will have these expected differences.</span></span>  

<span data-ttu-id="b2857-160">お客様のシナリオに応じて、CQDv3 には SFB 2019 オンプレミスの通話 (データコネクタと共に SFB 2019 を使用している場合)、Skype ボット通話 (AA、CVI、VDI)、ライブイベント、PSTN 通話が含まれます。</span><span class="sxs-lookup"><span data-stu-id="b2857-160">Depending on Customers’ scenario, CQDv3 will include SFB 2019 on-premises calls (if SFB 2019 is used with a data connector), Skype Bot calls (AA, CVI, VDI), Live Events and PSTN calls.</span></span> <span data-ttu-id="b2857-161">顧客に提供されているが、そのデータは CQD V2 に含まれていないシナリオ/機能。</span><span class="sxs-lookup"><span data-stu-id="b2857-161">Scenarios/Features which are available for the customers, but their data are not in CQD V2.</span></span>

<span data-ttu-id="b2857-162">たとえば、お客様には、20万オーディオストリームが表示され、CQD V2 サマリーレポートで5000エラーが発生することが予想されます。CQD V3 の5500のエラー (2019 オンプレミス通話、CVI 通話、PSTN 通話など) と30万オーディオストリーム。</span><span class="sxs-lookup"><span data-stu-id="b2857-162">For instance, it is expected that your customers and you will see 200,000 audio streams, with 5000 failures in CQD V2 Summary Report; versus 300,000 audio streams with 5500 failures (coming from 2019 on-prem calls, CVI calls, PSTN calls etc) in CQD V3.</span></span>

<span data-ttu-id="b2857-163">予期しない違いがある場合は、データ全体のさまざまな内訳を確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b2857-163">In order to determine, if there are any unexpected differences, you must look at various breakdowns of the overall data.</span></span>  <span data-ttu-id="b2857-164">目的に合わせて比較します。</span><span class="sxs-lookup"><span data-stu-id="b2857-164">Compare with intent.</span></span>  <span data-ttu-id="b2857-165">ユーザーエージェントカテゴリペア別のデータのスライスは、最初に推奨されるものの1つです。</span><span class="sxs-lookup"><span data-stu-id="b2857-165">Slicing the data by User Agent Category Pair is one of the first things we recommend.</span></span>  <span data-ttu-id="b2857-166">*第1の製品*と*第2の製品*は、スライサーとしても優れています。</span><span class="sxs-lookup"><span data-stu-id="b2857-166">*First Product* and *Second Product* are also good slicers.</span></span>  


## <a name="related-topics"></a><span data-ttu-id="b2857-167">関連項目</span><span class="sxs-lookup"><span data-stu-id="b2857-167">Related topics</span></span>

[<span data-ttu-id="b2857-168">Teams の通話品質を向上させて監視する</span><span class="sxs-lookup"><span data-stu-id="b2857-168">Improve and monitor call quality for Teams</span></span>](monitor-call-quality-qos.md)

[<span data-ttu-id="b2857-169">CQD とは何ですか?</span><span class="sxs-lookup"><span data-stu-id="b2857-169">What is CQD?</span></span>](CQD-what-is-call-quality-dashboard.md)

[<span data-ttu-id="b2857-170">通話品質ダッシュボード (CQD) を設定する</span><span class="sxs-lookup"><span data-stu-id="b2857-170">Set up Call Quality Dashboard (CQD)</span></span>](turning-on-and-using-call-quality-dashboard.md)

[<span data-ttu-id="b2857-171">テナントのアップロードとデータの構築</span><span class="sxs-lookup"><span data-stu-id="b2857-171">Upload tenant and building data</span></span>](CQD-upload-tenant-building-data.md)

[<span data-ttu-id="b2857-172">CQD データとレポート</span><span class="sxs-lookup"><span data-stu-id="b2857-172">CQD data and reports</span></span>](CQD-data-and-reports.md)

[<span data-ttu-id="b2857-173">CQD を使用して通話と会議の品質を管理する</span><span class="sxs-lookup"><span data-stu-id="b2857-173">Use CQD to manage call and meeting quality</span></span>](quality-of-experience-review-guide.md)

[<span data-ttu-id="b2857-174">CQD で使用できるディメンションとメジャー</span><span class="sxs-lookup"><span data-stu-id="b2857-174">Dimensions and measures available in CQD</span></span>](dimensions-and-measures-available-in-call-quality-dashboard.md)

[<span data-ttu-id="b2857-175">CQD でのストリームの分類</span><span class="sxs-lookup"><span data-stu-id="b2857-175">Stream Classification in CQD</span></span>](stream-classification-in-call-quality-dashboard.md)

[<span data-ttu-id="b2857-176">Power BI を使用して CQD データを分析する</span><span class="sxs-lookup"><span data-stu-id="b2857-176">Use Power BI to analyze CQD data</span></span>](CQD-Power-BI-query-templates.md)

[<span data-ttu-id="b2857-177">Teams のトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="b2857-177">Teams Troubleshooting</span></span>](https://docs.microsoft.com/MicrosoftTeams/troubleshoot/teams)