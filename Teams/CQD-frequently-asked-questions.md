---
title: 通話品質ダッシュボード (CQD) についてよく寄せられる質問 (FAQ)
ms.author: serdars
author: SerdarSoysal
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
description: 通話品質ダッシュボード (CQD) に関してよく寄せられる質問 (FAQ) Microsoft Teams回答を参照してください。
ms.openlocfilehash: ad718df893b69b333dd63d224663238879fda8c7
ms.sourcegitcommit: 90615674e9703aa5ea32be64ab3638aa30e83127
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/02/2021
ms.locfileid: "52718008"
---
# <a name="call-quality-dashboard-cqd-frequently-asked-questions-faq"></a><span data-ttu-id="54a38-103">通話品質ダッシュボード (CQD) についてよく寄せられる質問 (FAQ)</span><span class="sxs-lookup"><span data-stu-id="54a38-103">Call Quality Dashboard (CQD) Frequently asked questions (FAQ)</span></span>

## <a name="frequently-asked-questions"></a><span data-ttu-id="54a38-104">よく寄せられる質問</span><span class="sxs-lookup"><span data-stu-id="54a38-104">Frequently asked questions</span></span>

[<span data-ttu-id="54a38-105">1 人または複数の会議参加者の経験が低い場合、CQD が通話を "良好" とマークする理由</span><span class="sxs-lookup"><span data-stu-id="54a38-105">Why does CQD mark a call as "Good" if one or more meeting participants had a poor experience?</span></span>](#why-does-cqd-mark-a-call-as-good-if-one-or-more-meeting-participants-had-a-poor-experience)

[<span data-ttu-id="54a38-106">メジャーの呼び出しとユーザーカウントの値に最大 0.2% の差が表示される理由と、最も正確なボリュームを取得する方法 </span><span class="sxs-lookup"><span data-stu-id="54a38-106">Why do I see up to 0.2% difference in call and user count values on measures and how to get most accurate volumes? </span></span>](#why-do-i-see-up-to-02-difference-in-call-and-user-count-values-on-measures-and-how-to-get-most-accurate-volumes)

[<span data-ttu-id="54a38-107">データからの CQD データがSkype for Business CQD データと異なるTeams。</span><span class="sxs-lookup"><span data-stu-id="54a38-107">Why is CQD data from Skype for Business different than CQD data from Teams? </span></span>](#why-is-cqd-data-from-skype-for-business-different-than-cqd-data-from-teams)

[<span data-ttu-id="54a38-108">CQD で EUII が表示できない理由</span><span class="sxs-lookup"><span data-stu-id="54a38-108">Why can't I see EUII in CQD?</span></span>](#why-cant-i-see-euii-in-cqd)

[<span data-ttu-id="54a38-109">フィルター処理のみをSkype for Business、CQD に情報が表示Teams。</span><span class="sxs-lookup"><span data-stu-id="54a38-109">Why am I seeing Skype for Business information in CQD when I've filtered for Teams only?</span></span>](#why-am-i-seeing-skype-for-business-information-in-cqd-when-ive-filtered-for-teams-only)

[<span data-ttu-id="54a38-110">追加のエントリが必要とわかっているのに、カスタム レポートで返される行数が最大 10,000 行になる理由</span><span class="sxs-lookup"><span data-stu-id="54a38-110">Why do my custom reports only return a maximum of 10,000 rows when I know there should be more entries?</span></span>](#why-do-my-custom-reports-only-return-a-maximum-of-10000-rows-when-i-know-there-should-be-more-entries)

[<span data-ttu-id="54a38-111">WiFi VPN 接続が WiFi ではなく有線として表示される理由</span><span class="sxs-lookup"><span data-stu-id="54a38-111">Why do WiFi VPN connections show as Wired instead of WiFi?</span></span>](#why-do-wifi-vpn-connections-show-as-wired-instead-of-wifi)

### <a name="why-does-cqd-mark-a-call-as-good-if-one-or-more-meeting-participants-had-a-poor-experience"></a><span data-ttu-id="54a38-112">1 人または複数の会議参加者の経験が低い場合、CQD が通話を "良好" とマークする理由</span><span class="sxs-lookup"><span data-stu-id="54a38-112">Why does CQD mark a call as "Good" if one or more meeting participants had a poor experience?</span></span>

<span data-ttu-id="54a38-113">CQD がストリーム分類に使用する規則 [を確認してください](stream-classification-in-call-quality-dashboard.md)。</span><span class="sxs-lookup"><span data-stu-id="54a38-113">Check out the rules CQD uses for [stream classification](stream-classification-in-call-quality-dashboard.md).</span></span>
 
<span data-ttu-id="54a38-114">オーディオ ストリームの場合、呼び出しの長さに基づいて平均に対して計算される 5 つの分類子は、すべて "良好" パラメーター内に含まれます。</span><span class="sxs-lookup"><span data-stu-id="54a38-114">For audio streams, any of the five classifiers, which are calculated for the average based on the length of the call, could all be within "good" parameters.</span></span> <span data-ttu-id="54a38-115">これは、ユーザーがオーディオのドロップアウト、静的、またはエラーの発生を経験しなかったことを意味する必要があります。</span><span class="sxs-lookup"><span data-stu-id="54a38-115">It doesn't mean the users didn't experience something that contributed to an audio drop out, static, or glitch.</span></span> 

<span data-ttu-id="54a38-116">ネットワークの問題かどうかを判断するには、セッションの平均値と最大値の差分を確認します。</span><span class="sxs-lookup"><span data-stu-id="54a38-116">To determine if it was a network problem, look at the delta between the average values for the session and the max values.</span></span> <span data-ttu-id="54a38-117">最大値は、セッション中に検出され、報告される最大値です。</span><span class="sxs-lookup"><span data-stu-id="54a38-117">Max values are the maximum detected and reported during the session.</span></span>
 
<span data-ttu-id="54a38-118">この状況をトラブルシューティングする方法の例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="54a38-118">Here's an example of how to troubleshoot this situation.</span></span> <span data-ttu-id="54a38-119">たとえば、通話中にネットワーク トレースを実行し、最初の 20 分間はパケットが失われることはありませんが、その後は 1.5 秒のパケットの間隔が生じ、その後の通話の残りの部分に良好な差が生じてしまいます。</span><span class="sxs-lookup"><span data-stu-id="54a38-119">Let's say you take a network trace during a call and the first 20 minutes there are no lost packets but then you have a gap of 1.5 seconds of packets and then good for the remainder of the call.</span></span> <span data-ttu-id="54a38-120">平均は、Wireshark トレース RTP <でも 10% (0.1) パケット損失が発生します。</span><span class="sxs-lookup"><span data-stu-id="54a38-120">The average is going to be <10% (0.1) Packet loss even in a Wireshark trace RTP analysis.</span></span> <span data-ttu-id="54a38-121">最大パケット損失は何でしたか?</span><span class="sxs-lookup"><span data-stu-id="54a38-121">What was the Max Packet Loss?</span></span> <span data-ttu-id="54a38-122">5 秒間の 1.5 秒は 30% (0.3) になります。</span><span class="sxs-lookup"><span data-stu-id="54a38-122">1.5 Seconds in a 5-second period would be 30% (0.3).</span></span> <span data-ttu-id="54a38-123">これは、5 秒間のサンプリング期間中に発生しましたか (または、サンプリング期間に分割される可能性があります)。</span><span class="sxs-lookup"><span data-stu-id="54a38-123">Did that occur within the 5-second sampling period (maybe or it could be split over the sampling period)?</span></span>
 
<span data-ttu-id="54a38-124">ネットワーク メトリックが平均値と最大値で良好に見える場合は、他のテレメトリ データを確認します。</span><span class="sxs-lookup"><span data-stu-id="54a38-124">If network metrics look good in the averages and max values, then look to other telemetry data:</span></span> 
- <span data-ttu-id="54a38-125">[CPU Insufficient Event Ratio]をオンにし、検出された使用可能な CPU リソースが不十分で、低品質の原因になっているか確認します。</span><span class="sxs-lookup"><span data-stu-id="54a38-125">Check CPU Insufficient Event Ratio to see if the detected CPU resources available were insufficient and caused poor quality.</span></span> 
- <span data-ttu-id="54a38-126">スピーカーに近いマイクによるフィードバックを防ぐために、オーディオ デバイスは半二重モードでしたか?</span><span class="sxs-lookup"><span data-stu-id="54a38-126">Was the audio device in Half Duplex mode to prevent feedback due to microphones that are to close to speakers?</span></span> 
- <span data-ttu-id="54a38-127">デバイスの半分の両面 AEC イベントの比率を確認します。</span><span class="sxs-lookup"><span data-stu-id="54a38-127">Check the Device Half Duplex AEC Event Ratio.</span></span> <span data-ttu-id="54a38-128">ハブまたはドッキング ステーションに接続すると、USB オーディオドロップアウトが原因で、デバイスのグリンクまたはマイクのグリンクによってノイズや静的が発生しましたか?</span><span class="sxs-lookup"><span data-stu-id="54a38-128">Was the device glitching or the microphone glitching introducing noise or static due to USB Audio Drop outs when plugged into a Hub or Docking Station?</span></span>  
- <span data-ttu-id="54a38-129">デバイスの不具合とマイクの不具合イベントの比率を確認します。</span><span class="sxs-lookup"><span data-stu-id="54a38-129">Check the Device Glitches and Microphone glitches event ratios.</span></span> <span data-ttu-id="54a38-130">デバイス自体が正しく機能していますか?</span><span class="sxs-lookup"><span data-stu-id="54a38-130">Was the device itself functioning properly?</span></span>  
- <span data-ttu-id="54a38-131">Capture デバイスと Render Device Not Functioning Event Ratios を確認します。</span><span class="sxs-lookup"><span data-stu-id="54a38-131">Check the Capture and Render Device Not Functioning Event Ratios.</span></span>


<span data-ttu-id="54a38-132">CQD テレメトリで使用できるディメンションとメジャーの詳細については、「通話品質ダッシュボードで使用可能なディメンションと測定値 [」を参照してください](dimensions-and-measures-available-in-call-quality-dashboard.md)。</span><span class="sxs-lookup"><span data-stu-id="54a38-132">For more on dimensions and measures available in CQD telemetry, read [Dimensions and measurements available in Call Quality Dashboard](dimensions-and-measures-available-in-call-quality-dashboard.md).</span></span>

<span data-ttu-id="54a38-133">バックグラウンド ノイズの場合は、[ミュート イベントの比率] をオンにし、参加者がミュートされた時間の長さを確認します。</span><span class="sxs-lookup"><span data-stu-id="54a38-133">For background noise, check mute event ratio to see the length of time participants were muted.</span></span>
 
<span data-ttu-id="54a38-134">CQD で詳細なレポートを作成し、会議 ID でフィルター処理して、会議のすべてのユーザーとストリームを確認し、関心のあるフィールドを追加します。</span><span class="sxs-lookup"><span data-stu-id="54a38-134">Create detailed reports in CQD and filter on Meeting ID to look at all users and streams in a meeting and add the fields you are interested in.</span></span> <span data-ttu-id="54a38-135">問題を報告しているユーザーが、問題を発生しているユーザーではない可能性があります。</span><span class="sxs-lookup"><span data-stu-id="54a38-135">A user reporting the issue may not be the one that was having the issue.</span></span> <span data-ttu-id="54a38-136">ユーザーはエクスペリエンスを報告しているだけです。</span><span class="sxs-lookup"><span data-stu-id="54a38-136">They are just reporting the experience.</span></span>
 
<span data-ttu-id="54a38-137">テレメトリは必ずしも問題を呼び出すとは限りませんが、決定を確認して通知する場所をよりよく理解するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="54a38-137">The telemetry will not necessarily call out the issue, but it can help you better understand where to look and inform your decisions.</span></span> <span data-ttu-id="54a38-138">ネットワーク、デバイス、ドライバーまたはファームウェアの更新プログラム、使用状況、またはユーザーですか。</span><span class="sxs-lookup"><span data-stu-id="54a38-138">Is it network, device, driver or firmware updates, usage, or user?</span></span>

### <a name="why-do-i-see-up-to-02-difference-in-call-and-user-count-values-on-measures-and-how-to-get-most-accurate-volumes"></a><span data-ttu-id="54a38-139">メジャーの呼び出しとユーザーカウントの値に最大 0.2% の差が表示される理由と、最も正確なボリュームを取得する方法</span><span class="sxs-lookup"><span data-stu-id="54a38-139">Why do I see up to 0.2% difference in call and user count values on measures and how to get most accurate volumes?</span></span> 
<span data-ttu-id="54a38-140">呼び出し数とユーザー数の測定を計算するために、データ セット内の呼び出しまたはユーザー識別子に対して個別の countif 操作が実行されます。</span><span class="sxs-lookup"><span data-stu-id="54a38-140">To compute call count and user count measures, a distinct countif operation is performed against the call or user identifiers in the data set.</span></span> <span data-ttu-id="54a38-141">大規模なデータ セットでは、個別の countif 操作に固有の最大 0.2% のエラーがあります。</span><span class="sxs-lookup"><span data-stu-id="54a38-141">On large data sets, there is an up to 0.2% error inherent with the distinct countif operation.</span></span> <span data-ttu-id="54a38-142">最も正確なボリュームの場合は、この個別の countif 操作に依存しならず、ストリーム数のメジャーに依存する必要があります。</span><span class="sxs-lookup"><span data-stu-id="54a38-142">For the most accurate volume, you should rely on stream count measures since they do not rely on this distinct countif operation.</span></span> <span data-ttu-id="54a38-143">データ 量を減らしてフィルター処理すると、エラーが減る可能性がありますが、個別の呼び出しとユーザー数でこのエラーの原因が排除されない場合があります。</span><span class="sxs-lookup"><span data-stu-id="54a38-143">Filtering to reduce the data volume may reduce the error but may not eliminate this source of error in distinct call and user counts.</span></span> <span data-ttu-id="54a38-144">メジャーが [影響を受け取る「通話品質](dimensions-and-measures-available-in-call-quality-dashboard.md) ダッシュボード」で使用できるディメンションと測定値に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="54a38-144">Refer to [Dimensions and measurements available in Call Quality Dashboard](dimensions-and-measures-available-in-call-quality-dashboard.md) for which measures are impacted.</span></span>


### <a name="why-is-cqd-data-from-skype-for-business-different-than-cqd-data-from-teams"></a><span data-ttu-id="54a38-145">データからの CQD データがSkype for Business CQD データと異なるTeams。</span><span class="sxs-lookup"><span data-stu-id="54a38-145">Why is CQD data from Skype for Business different than CQD data from Teams?</span></span> 


> [!IMPORTANT]
> <span data-ttu-id="54a38-146">2020 年 7 月 1 日の現在、古い CQD (CQD.lync.com) では、最新の CQD (CQD.Teams.microsoft.com) のデータが使用されています。</span><span class="sxs-lookup"><span data-stu-id="54a38-146">As of July 1, 2020, the older CQD (CQD.lync.com) uses data from the latest CQD (CQD.Teams.microsoft.com).</span></span> <span data-ttu-id="54a38-147">古い CQD データは使用できなくなりました。また、建物データやレポート データをエクスポートできません。</span><span class="sxs-lookup"><span data-stu-id="54a38-147">The older CQD data is no longer available, and you can't export your building or report data.</span></span> <span data-ttu-id="54a38-148">引き続き CQD.lync.com (Skype for Business 管理センターから利用可能) を使用できますが、間もなく CQD.lync.com へのアクセスがオフになります。そのため、CQD に移行する必要があります。Teams.microsoft.com(まだ行っていない場合)。</span><span class="sxs-lookup"><span data-stu-id="54a38-148">You can still use CQD.lync.com (available from the Skype for Business admin center), but we'll turn off access to CQD.lync.com soon, so you should move to CQD.Teams.microsoft.com if you haven't already done so.</span></span>


<span data-ttu-id="54a38-149">Skype for Business レガシ ポータル (cqd.lync.com) の古い CQD と Teams 管理センター (cqd.teams.microsoft.com) の最新の CQD の間でデータを比較する場合、データが一致しないのがすぐに分かっています。</span><span class="sxs-lookup"><span data-stu-id="54a38-149">If you're trying to compare data between the older CQD from the Skype for Business legacy portal (cqd.lync.com) and the latest CQD from the Teams admin center (cqd.teams.microsoft.com), you'll quickly notice that the data doesn't match.</span></span> <span data-ttu-id="54a38-150">これは、最新の CQD が多くの追加の呼び出しシナリオを報告する理由です。</span><span class="sxs-lookup"><span data-stu-id="54a38-150">That's because the latest CQD reports on many additional calling scenarios.</span></span> <span data-ttu-id="54a38-151">古い CQD のレポートを引き続き使用している場合は、この記事を使用して、これらのレポートを解釈するのに役立ちます。「通話品質ダッシュボード[for Skype for Business Server」](/skypeforbusiness/management-tools/call-quality-dashboard/call-quality-dashboard)</span><span class="sxs-lookup"><span data-stu-id="54a38-151">If you're still using reports from the older CQD, use this article to help you interpret those reports: [Call Quality Dashboard for Skype for Business Server](/skypeforbusiness/management-tools/call-quality-dashboard/call-quality-dashboard).</span></span>


  
### <a name="why-cant-i-see-euii-in-cqd"></a><span data-ttu-id="54a38-152">CQD で EUII が表示できない理由</span><span class="sxs-lookup"><span data-stu-id="54a38-152">Why can't I see EUII in CQD?</span></span>

<span data-ttu-id="54a38-153">これらの管理者ロールは CQD にアクセスできますが、EUII (エンド ユーザーを特定できる情報) を表示できません。</span><span class="sxs-lookup"><span data-stu-id="54a38-153">These admin roles can access CQD, but they can't view EUII (end-user identifiable information):</span></span>
- <span data-ttu-id="54a38-154">Microsoft 365レポート閲覧者</span><span class="sxs-lookup"><span data-stu-id="54a38-154">Microsoft 365 Reports Reader</span></span>
- <span data-ttu-id="54a38-155">Teams 通信サポート スペシャリスト</span><span class="sxs-lookup"><span data-stu-id="54a38-155">Teams Communications Support Specialist</span></span>

<span data-ttu-id="54a38-156">CQD にアクセスできるロール (EUII を含む) の詳細については、「CQD にアクセスするためにロールを割り当てる」 [を参照してください](turning-on-and-using-call-quality-dashboard.md#assign-admin-roles-for-access-to-cqd)。</span><span class="sxs-lookup"><span data-stu-id="54a38-156">To learn more about roles that can access CQD - including EUII - read [Assign roles for accessing CQD](turning-on-and-using-call-quality-dashboard.md#assign-admin-roles-for-access-to-cqd).</span></span>

### <a name="why-am-i-seeing-skype-for-business-information-in-cqd-when-ive-filtered-for-teams-only"></a><span data-ttu-id="54a38-157">フィルター処理のみをSkype for Business、CQD に情報が表示Teams。</span><span class="sxs-lookup"><span data-stu-id="54a38-157">Why am I seeing Skype for Business information in CQD when I've filtered for Teams only?</span></span>

<span data-ttu-id="54a38-158">CQD Teams レポート (isTeams = 1) でのみフィルター処理を行う場合は、最初のエンドポイントが含Teams。</span><span class="sxs-lookup"><span data-stu-id="54a38-158">When you filter for Teams only in CQD reports (isTeams = 1), you're filtering for all calls where the *first endpoint* is Teams.</span></span> <span data-ttu-id="54a38-159">2 *番目の* エンドポイントがSkype for Business、その情報が CQD レポートに表示されます。</span><span class="sxs-lookup"><span data-stu-id="54a38-159">If the *second endpoint* is Skype for Business, that information will show up in your CQD report.</span></span>

<span data-ttu-id="54a38-160">CQDv2 と CQDv3 の合計カウントは常に異なります。CQDv3 には、CQDv2 にはない新しいシナリオが含まれています。</span><span class="sxs-lookup"><span data-stu-id="54a38-160">CQDv2 and CQDv3 will always have different total counts since CQDv3 will have new scenarios that CQDv2 will not have.</span></span> <span data-ttu-id="54a38-161">集計合計または集計された全数値をフィルターを使用して比較すると、これらの期待される違いが生じ得るのは、その理由です。</span><span class="sxs-lookup"><span data-stu-id="54a38-161">That’s why comparing Summary Total or Aggregated all-up numbers with no filters will have these expected differences.</span></span>  

<span data-ttu-id="54a38-162">顧客のシナリオに応じて、CQDv3 には SFB 2019 オンプレミス呼び出し (SFB 2019 がデータ コネクタで使用されている場合)、Skype ボット呼び出し (AA、CVI、VDI)、ライブ イベント、PSTN 通話が含まれます。</span><span class="sxs-lookup"><span data-stu-id="54a38-162">Depending on Customers’ scenario, CQDv3 will include SFB 2019 on-premises calls (if SFB 2019 is used with a data connector), Skype Bot calls (AA, CVI, VDI), Live Events and PSTN calls.</span></span> <span data-ttu-id="54a38-163">顧客が利用できるが、データが CQD V2 内にはないシナリオ/機能。</span><span class="sxs-lookup"><span data-stu-id="54a38-163">Scenarios/Features which are available for the customers, but their data are not in CQD V2.</span></span>

<span data-ttu-id="54a38-164">たとえば、顧客と 200,000 のオーディオ ストリームが表示され、CQD V2 サマリー レポートで 5000 エラーが発生すると想定されます。CQD V3 では、300,000 のオーディオ ストリームと 5500 の障害 (2019 年のオンプレム通話、CVI 呼び出し、PSTN 通話など) が発生します。</span><span class="sxs-lookup"><span data-stu-id="54a38-164">For instance, it is expected that your customers and you will see 200,000 audio streams, with 5000 failures in CQD V2 Summary Report; versus 300,000 audio streams with 5500 failures (coming from 2019 on-prem calls, CVI calls, PSTN calls, etc.) in CQD V3.</span></span>

<span data-ttu-id="54a38-165">予期しない違いがある場合は、データ全体のさまざまな内訳を確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="54a38-165">In order to determine, if there are any unexpected differences, you must look at various breakdowns of the overall data.</span></span>  <span data-ttu-id="54a38-166">意図と比較します。</span><span class="sxs-lookup"><span data-stu-id="54a38-166">Compare with intent.</span></span>  <span data-ttu-id="54a38-167">ユーザー エージェント カテゴリ ペアによるデータのスライスは、最初に推奨される項目の 1 つです。</span><span class="sxs-lookup"><span data-stu-id="54a38-167">Slicing the data by User Agent Category Pair is one of the first things we recommend.</span></span>  <span data-ttu-id="54a38-168">*First Product と* *Second Product* も優れたスライサーです。</span><span class="sxs-lookup"><span data-stu-id="54a38-168">*First Product* and *Second Product* are also good slicers.</span></span>  

### <a name="why-do-my-custom-reports-only-return-a-maximum-of-10000-rows-when-i-know-there-should-be-more-entries"></a><span data-ttu-id="54a38-169">追加のエントリが必要とわかっているのに、カスタム レポートで返される行数が最大 10,000 行になる理由</span><span class="sxs-lookup"><span data-stu-id="54a38-169">Why do my custom reports only return a maximum of 10,000 rows when I know there should be more entries?</span></span>

<span data-ttu-id="54a38-170">CQD は集計されたデータ クエリ用に設計され、データエクスポート用には設計されません。</span><span class="sxs-lookup"><span data-stu-id="54a38-170">CQD is designed for summarized data queries, and is not designed for data export.</span></span> <span data-ttu-id="54a38-171">可能であれば、10,000 行の制限を超えないように、レポートを再構築することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="54a38-171">We recommend restructuring your reports, where possible, to prevent the 10,000 row limit from being exceeded.</span></span> <span data-ttu-id="54a38-172">まず、月、年、日付、地域、国など、より広範なカーディナリティディメンションを使用して KPI を確認します。そこから、より高いカーディナリティ ディメンションにドリルダウンできます。</span><span class="sxs-lookup"><span data-stu-id="54a38-172">Start by looking at your KPIs using broader, lower-cardinality dimensions, such as Month, Year, Date, Region, Country, etc. From there, you can drill down into increasingly higher-cardinality dimensions.</span></span> <span data-ttu-id="54a38-173">ヘルプデスクレポートとLocation-Enhancedレポートはどちらも、このドリルダウン ワークフローの優れた例を提供します。</span><span class="sxs-lookup"><span data-stu-id="54a38-173">The Helpdesk and Location-Enhanced Reports both provide good examples of this drill down workflow.</span></span>

### <a name="why-do-wifi-vpn-connections-show-as-wired-instead-of-wifi"></a><span data-ttu-id="54a38-174">WiFi VPN 接続が WiFi ではなく有線として表示される理由</span><span class="sxs-lookup"><span data-stu-id="54a38-174">Why do WiFi VPN connections show as Wired instead of WiFi?</span></span>

<span data-ttu-id="54a38-175">これは予期されることです。</span><span class="sxs-lookup"><span data-stu-id="54a38-175">This is expected.</span></span> <span data-ttu-id="54a38-176">VPN ベンダーは、有線接続として扱われる仮想イーサネット アダプターを作成しました。</span><span class="sxs-lookup"><span data-stu-id="54a38-176">The VPN vendor created a virtual ethernet adapter which is treated like a wired connection.</span></span> <span data-ttu-id="54a38-177">正しくラベル付けされていないので、オペレーティング システムは WiFi 接続を知らないので、有線として報告します。</span><span class="sxs-lookup"><span data-stu-id="54a38-177">Since it's not properly labeled, the operating system doesn't know it's a WiFi connection and reports it as wired.</span></span>

## <a name="related-topics"></a><span data-ttu-id="54a38-178">関連項目</span><span class="sxs-lookup"><span data-stu-id="54a38-178">Related topics</span></span>

[<span data-ttu-id="54a38-179">Teams の通話品質の向上と監視</span><span class="sxs-lookup"><span data-stu-id="54a38-179">Improve and monitor call quality for Teams</span></span>](monitor-call-quality-qos.md)

[<span data-ttu-id="54a38-180">CQD とは</span><span class="sxs-lookup"><span data-stu-id="54a38-180">What is CQD?</span></span>](CQD-what-is-call-quality-dashboard.md)

[<span data-ttu-id="54a38-181">通話品質ダッシュボード (CQD) を設定する</span><span class="sxs-lookup"><span data-stu-id="54a38-181">Set up Call Quality Dashboard (CQD)</span></span>](turning-on-and-using-call-quality-dashboard.md)

[<span data-ttu-id="54a38-182">アップロードとデータの構築</span><span class="sxs-lookup"><span data-stu-id="54a38-182">Upload tenant and building data</span></span>](CQD-upload-tenant-building-data.md)

[<span data-ttu-id="54a38-183">CQD データとレポート</span><span class="sxs-lookup"><span data-stu-id="54a38-183">CQD data and reports</span></span>](CQD-data-and-reports.md)

[<span data-ttu-id="54a38-184">CQD を使用して通話と会議の品質を管理する</span><span class="sxs-lookup"><span data-stu-id="54a38-184">Use CQD to manage call and meeting quality</span></span>](quality-of-experience-review-guide.md)

[<span data-ttu-id="54a38-185">CQD で使用可能なディメンションとメジャー</span><span class="sxs-lookup"><span data-stu-id="54a38-185">Dimensions and measures available in CQD</span></span>](dimensions-and-measures-available-in-call-quality-dashboard.md)

[<span data-ttu-id="54a38-186">CQD のストリーム分類</span><span class="sxs-lookup"><span data-stu-id="54a38-186">Stream Classification in CQD</span></span>](stream-classification-in-call-quality-dashboard.md)

[<span data-ttu-id="54a38-187">CQD Power BI分析するには、次のコマンドを使用します。</span><span class="sxs-lookup"><span data-stu-id="54a38-187">Use Power BI to analyze CQD data</span></span>](CQD-Power-BI-query-templates.md)

[<span data-ttu-id="54a38-188">Teams のトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="54a38-188">Teams Troubleshooting</span></span>](/MicrosoftTeams/troubleshoot/teams)
