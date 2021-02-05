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
description: Microsoft Teams 通話品質ダッシュボード (CQD) についてよく寄せられる質問 (FAQ) と回答をお読みください。
ms.openlocfilehash: f622d197900faf632d94d659dae0a5b6eeaee2db
ms.sourcegitcommit: ac73536f790f83a61eeb2eb8c6b71662f7bd26fc
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/05/2021
ms.locfileid: "50110260"
---
# <a name="call-quality-dashboard-cqd-frequently-asked-questions-faq"></a><span data-ttu-id="b19e4-103">通話品質ダッシュボード (CQD) についてよく寄せられる質問 (FAQ)</span><span class="sxs-lookup"><span data-stu-id="b19e4-103">Call Quality Dashboard (CQD) Frequently asked questions (FAQ)</span></span>

## <a name="frequently-asked-questions"></a><span data-ttu-id="b19e4-104">よく寄せられる質問</span><span class="sxs-lookup"><span data-stu-id="b19e4-104">Frequently asked questions</span></span>

[<span data-ttu-id="b19e4-105">1 人または複数の会議参加者のエクスペリエンスが低下した場合、CQD は通話を "良い" とマークする理由を示します。</span><span class="sxs-lookup"><span data-stu-id="b19e4-105">Why does CQD mark a call as "Good" if one or more meeting participants had a poor experience?</span></span>](#why-does-cqd-mark-a-call-as-good-if-one-or-more-meeting-participants-had-a-poor-experience)

[<span data-ttu-id="b19e4-106">メジャーの呼び出しとユーザー 数の値に最大 0.2% の差が表示される理由と、最も正確なボリュームを取得する方法 </span><span class="sxs-lookup"><span data-stu-id="b19e4-106">Why do I see up to 0.2% difference in call and user count values on measures and how to get most accurate volumes? </span></span>](#why-do-i-see-up-to-02-difference-in-call-and-user-count-values-on-measures-and-how-to-get-most-accurate-volumes)

[<span data-ttu-id="b19e4-107">Skype for Business の CQD データが Teams の CQD データと異なる理由 </span><span class="sxs-lookup"><span data-stu-id="b19e4-107">Why is CQD data from Skype for Business different than CQD data from Teams? </span></span>](#why-is-cqd-data-from-skype-for-business-different-than-cqd-data-from-teams)

[<span data-ttu-id="b19e4-108">CQD に EUII が表示できない理由</span><span class="sxs-lookup"><span data-stu-id="b19e4-108">Why can't I see EUII in CQD?</span></span>](#why-cant-i-see-euii-in-cqd)

[<span data-ttu-id="b19e4-109">Teams のみをフィルター処理した場合に、CQD に Skype for Business の情報が表示される理由</span><span class="sxs-lookup"><span data-stu-id="b19e4-109">Why am I seeing Skype for Business information in CQD when I've filtered for Teams only?</span></span>](#why-am-i-seeing-skype-for-business-information-in-cqd-when-ive-filtered-for-teams-only)

[<span data-ttu-id="b19e4-110">追加のエントリが必要とわかっているのに、カスタム レポートで返される行数が最大 10,000 行である理由</span><span class="sxs-lookup"><span data-stu-id="b19e4-110">Why do my custom reports only return a maximum of 10,000 rows when I know there should be more entries?</span></span>](#why-do-my-custom-reports-only-return-a-maximum-of-10000-rows-when-i-know-there-should-be-more-entries)

### <a name="why-does-cqd-mark-a-call-as-good-if-one-or-more-meeting-participants-had-a-poor-experience"></a><span data-ttu-id="b19e4-111">1 人または複数の会議参加者のエクスペリエンスが低下した場合、CQD は通話を "良い" とマークする理由を示します。</span><span class="sxs-lookup"><span data-stu-id="b19e4-111">Why does CQD mark a call as "Good" if one or more meeting participants had a poor experience?</span></span>

<span data-ttu-id="b19e4-112">ストリームの分類に CQD が使用するルール [を確認します](stream-classification-in-call-quality-dashboard.md)。</span><span class="sxs-lookup"><span data-stu-id="b19e4-112">Check out the rules CQD uses for [stream classification](stream-classification-in-call-quality-dashboard.md).</span></span>
 
<span data-ttu-id="b19e4-113">オーディオ ストリームの場合、呼び出しの長さに基づいて平均に対して計算される 5 つの分類子はすべて "良好" パラメーター内に含まれます。</span><span class="sxs-lookup"><span data-stu-id="b19e4-113">For audio streams, any of the 5 classifiers, which are calculated for the average based on the length of the call, could all be within "good" parameters.</span></span> <span data-ttu-id="b19e4-114">これは、ユーザーがオーディオのドロップ アウト、静的、またはエラーの発生を経験しなかったという意味では意味されません。</span><span class="sxs-lookup"><span data-stu-id="b19e4-114">It doesn't mean the users didn't experience something that contributed to an audio drop out, static, or glitch.</span></span> 

<span data-ttu-id="b19e4-115">ネットワークの問題かどうかを判断するには、セッションの平均値と最大値の差分を確認します。</span><span class="sxs-lookup"><span data-stu-id="b19e4-115">To determine if it was a network problem, look at the delta between the average values for the session and the max values.</span></span> <span data-ttu-id="b19e4-116">最大値は、セッション中に検出および報告される最大値です。</span><span class="sxs-lookup"><span data-stu-id="b19e4-116">Max values are the maximum detected and reported during the session.</span></span>
 
<span data-ttu-id="b19e4-117">この状況のトラブルシューティングを行う方法の例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="b19e4-117">Here's an example of how to troubleshoot this situation.</span></span> <span data-ttu-id="b19e4-118">たとえば、通話中にネットワーク トレースを実行し、最初の 20 分間はパケットが失われなくなっても、1.5 秒のパケットの間隔が生じ、通話の残りの部分に有効だとします。</span><span class="sxs-lookup"><span data-stu-id="b19e4-118">Let's say you take a network trace during a call and the first 20 minutes there are no lost packets but then you have a gap of 1.5 seconds of packets and then good for the remainder of the call.</span></span> <span data-ttu-id="b19e4-119">平均は、Wireshark トレース RTP 分析<10% (0.1) パケット損失に対応する予定です。</span><span class="sxs-lookup"><span data-stu-id="b19e4-119">The average is going to be <10% (0.1) Packet loss even in a Wireshark trace RTP analysis.</span></span> <span data-ttu-id="b19e4-120">最大パケット損失は何でしたか?</span><span class="sxs-lookup"><span data-stu-id="b19e4-120">What was the Max Packet Loss?</span></span> <span data-ttu-id="b19e4-121">5 秒の 1.5 秒は 30% (0.3) になります。</span><span class="sxs-lookup"><span data-stu-id="b19e4-121">1.5 Seconds in a 5-second period would be 30% (0.3).</span></span> <span data-ttu-id="b19e4-122">これは 5 秒のサンプリング期間内に発生しましたか (または、サンプリング期間を超える場合に分割される可能性があります)。</span><span class="sxs-lookup"><span data-stu-id="b19e4-122">Did that occur within the five second sampling period (maybe or it could be split over the sampling period)?</span></span>
 
<span data-ttu-id="b19e4-123">ネットワークメトリックが平均と最大値で良好に表示される場合は、他のテレメトリ データを確認します。</span><span class="sxs-lookup"><span data-stu-id="b19e4-123">If network metrics look good in the averages and max values, then look to other telemetry data:</span></span> 
- <span data-ttu-id="b19e4-124">[CPU Insufficient Event Ratio] をチェックして、使用可能な検出された CPU リソースが不足し、低品質の原因になっているか確認します。</span><span class="sxs-lookup"><span data-stu-id="b19e4-124">Check CPU Insufficient Event Ratio to see if the detected CPU resources available were insufficient and caused poor quality.</span></span> 
- <span data-ttu-id="b19e4-125">スピーカーに近いマイクによるフィードバックを防ぐために、オーディオ デバイスは半両面モードでしたか?</span><span class="sxs-lookup"><span data-stu-id="b19e4-125">Was the audio device in Half Duplex mode to prevent feedback due to microphones that are to close to speakers?</span></span> 
- <span data-ttu-id="b19e4-126">Device Half Duplex AEC Event Ratio を確認します。</span><span class="sxs-lookup"><span data-stu-id="b19e4-126">Check the Device Half Duplex AEC Event Ratio.</span></span> <span data-ttu-id="b19e4-127">ハブまたはドッキング ステーションに接続すると、USB オーディオ のドロップアウトが原因でノイズまたは静的なノイズが発生したデバイスまたはマイク gling でした。</span><span class="sxs-lookup"><span data-stu-id="b19e4-127">Was the device glitching or the microphone glitching introducing noise or static due to USB Audio Drop outs when plugged into a Hub or Docking Station:</span></span>  
- <span data-ttu-id="b19e4-128">デバイスの不具合とマイクの不具合のイベント比率を確認します。</span><span class="sxs-lookup"><span data-stu-id="b19e4-128">Check the Device Glitches and Microphone glitches event ratios.</span></span> <span data-ttu-id="b19e4-129">デバイス自体は正しく機能しましたか?</span><span class="sxs-lookup"><span data-stu-id="b19e4-129">Was the device itself functioning properly?</span></span>  
- <span data-ttu-id="b19e4-130">キャプチャ デバイスとレンダー デバイスが機能しないイベント 比を確認します。</span><span class="sxs-lookup"><span data-stu-id="b19e4-130">Check the Capture and Render Device Not Functioning Event Ratios.</span></span>


<span data-ttu-id="b19e4-131">CQD テレメトリで利用できるディメンションとメジャーの詳細については、通話品質ダッシュボードで利用できるディメンションと測定値 [を参照してください](dimensions-and-measures-available-in-call-quality-dashboard.md)。</span><span class="sxs-lookup"><span data-stu-id="b19e4-131">For more on dimensions and measures available in CQD telemetry, read [Dimensions and measurements available in Call Quality Dashboard](dimensions-and-measures-available-in-call-quality-dashboard.md).</span></span>

<span data-ttu-id="b19e4-132">背景の雑音の場合は、ミュート イベントの比率を確認して、参加者がミュートにされた時間の長さを確認します。</span><span class="sxs-lookup"><span data-stu-id="b19e4-132">For background noise, check mute event ratio to see the length of time participants were muted.</span></span>
 
<span data-ttu-id="b19e4-133">CQD で詳細レポートを作成し、会議 ID をフィルター処理して、会議のすべてのユーザーとストリームを確認し、関心のあるフィールドを追加します。</span><span class="sxs-lookup"><span data-stu-id="b19e4-133">Create detailed reports in CQD and filter on Meeting ID to look at all users and streams in a meeting and add the fields you are interested in.</span></span> <span data-ttu-id="b19e4-134">問題を報告しているユーザーが、問題を発生しているユーザーではない可能性があります。</span><span class="sxs-lookup"><span data-stu-id="b19e4-134">A user reporting the issue may not be the one that was having the issue.</span></span> <span data-ttu-id="b19e4-135">これらのユーザーは、そのエクスペリエンスを報告しています。</span><span class="sxs-lookup"><span data-stu-id="b19e4-135">They are just reporting the experience.</span></span>
 
<span data-ttu-id="b19e4-136">テレメトリは必ずしも問題を呼び出すとは限りませんが、どこで決定を見て通知する必要があるのかをよりよく理解するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="b19e4-136">The telemetry will not necessarily call out the issue, but it can help you better understand where to look and inform your decisions.</span></span> <span data-ttu-id="b19e4-137">ネットワーク、デバイス、ドライバー、またはファームウェアの更新プログラム、使用状況、またはユーザーですか?</span><span class="sxs-lookup"><span data-stu-id="b19e4-137">Is it network, device, driver or firmware updates, usage, or user?</span></span>

### <a name="why-do-i-see-up-to-02-difference-in-call-and-user-count-values-on-measures-and-how-to-get-most-accurate-volumes"></a><span data-ttu-id="b19e4-138">メジャーの呼び出しとユーザー 数の値に最大 0.2% の差が表示される理由と、最も正確なボリュームを取得する方法</span><span class="sxs-lookup"><span data-stu-id="b19e4-138">Why do I see up to 0.2% difference in call and user count values on measures and how to get most accurate volumes?</span></span> 
<span data-ttu-id="b19e4-139">呼び出し数とユーザー数のメジャーを計算するには、データ セット内の呼び出しまたはユーザー識別子に対して個別の countif 操作が実行されます。</span><span class="sxs-lookup"><span data-stu-id="b19e4-139">To compute call count and user count measures, a distinct countif operation is performed against the call or user identifiers in the data set.</span></span> <span data-ttu-id="b19e4-140">大きなデータ セットの場合、個別の countif 操作に固有のエラーは最大 0.2% です。</span><span class="sxs-lookup"><span data-stu-id="b19e4-140">On large data sets, there is an up to 0.2% error inherent with the distinct countif operation.</span></span> <span data-ttu-id="b19e4-141">最も正確なボリュームの場合は、この個別の countif 操作に依存しないので、ストリーム カウント メジャーに依存する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b19e4-141">For the most accurate volume, you should rely on stream count measures since they do not rely on this distinct countif operation.</span></span> <span data-ttu-id="b19e4-142">データ ボリュームを減らすためにフィルター処理を行った場合、エラーが減る可能性がありますが、個別の呼び出しとユーザー数でこのエラーの原因が排除されない場合があります。</span><span class="sxs-lookup"><span data-stu-id="b19e4-142">Filtering to reduce the data volume may reduce the error but may not eliminate this source of error in distinct call and user counts.</span></span> <span data-ttu-id="b19e4-143">メジャーが [影響を受け取る通話品質ダッシュボードで使用](dimensions-and-measures-available-in-call-quality-dashboard.md) できるディメンションと寸法を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b19e4-143">Refer to [Dimensions and measurements available in Call Quality Dashboard](dimensions-and-measures-available-in-call-quality-dashboard.md) for which measures are impacted.</span></span>


### <a name="why-is-cqd-data-from-skype-for-business-different-than-cqd-data-from-teams"></a><span data-ttu-id="b19e4-144">Skype for Business の CQD データが Teams の CQD データと異なる理由</span><span class="sxs-lookup"><span data-stu-id="b19e4-144">Why is CQD data from Skype for Business different than CQD data from Teams?</span></span> 


> [!IMPORTANT]
> <span data-ttu-id="b19e4-145">2020 年 7 月 1 日現在、古い CQD (CQD.lync.com) では最新の CQD (CQD) のデータが使用されます。Teams.microsoft.com)。</span><span class="sxs-lookup"><span data-stu-id="b19e4-145">As of July 1, 2020, the older CQD (CQD.lync.com) uses data from the latest CQD (CQD.Teams.microsoft.com).</span></span> <span data-ttu-id="b19e4-146">古い CQD データは使用できなくなったので、建物やレポートのデータをエクスポートできません。</span><span class="sxs-lookup"><span data-stu-id="b19e4-146">The older CQD data is no longer available, and you can't export your building or report data.</span></span> <span data-ttu-id="b19e4-147">CQD.lync.com (Skype for Business 管理センターから利用可能) を引き続き使用できますが、まもなく CQD.lync.com へのアクセスがオフになりますので、CQD に移動する必要があります。Teams.microsoft.comまだ行っていない場合は、この設定を行います。</span><span class="sxs-lookup"><span data-stu-id="b19e4-147">You can still use CQD.lync.com (available from the Skype for Business admin center), but we'll turn off access to CQD.lync.com soon, so you should move to CQD.Teams.microsoft.com if you haven't already done so.</span></span>


<span data-ttu-id="b19e4-148">Skype for Business レガシ ポータル (cqd.lync.com) の古い CQD と Teams 管理センター (cqd.teams.microsoft.com) の最新の CQD の間でデータを比較しようとしている場合、データが一致しない場合があります。</span><span class="sxs-lookup"><span data-stu-id="b19e4-148">If you're trying to compare data between the older CQD from the Skype for Business legacy portal (cqd.lync.com) and the latest CQD from the Teams admin center (cqd.teams.microsoft.com), you'll quickly notice that the data doesn't match.</span></span> <span data-ttu-id="b19e4-149">これは、最新の CQD レポートで多くの追加の呼び出しシナリオが報告されるからです。</span><span class="sxs-lookup"><span data-stu-id="b19e4-149">That's because the latest CQD reports on many additional calling scenarios.</span></span> <span data-ttu-id="b19e4-150">古い CQD のレポートを引き続き使用している場合は、この記事を使用して、これらのレポートを解釈するのに役立ちます [。Skype for Business Server](https://docs.microsoft.com/skypeforbusiness/management-tools/call-quality-dashboard/call-quality-dashboard)の通話品質ダッシュボード。</span><span class="sxs-lookup"><span data-stu-id="b19e4-150">If you're still using reports from the older CQD, use this article to help you interpret those reports: [Call Quality Dashboard for Skype for Business Server](https://docs.microsoft.com/skypeforbusiness/management-tools/call-quality-dashboard/call-quality-dashboard).</span></span>


  
### <a name="why-cant-i-see-euii-in-cqd"></a><span data-ttu-id="b19e4-151">CQD に EUII が表示できない理由</span><span class="sxs-lookup"><span data-stu-id="b19e4-151">Why can't I see EUII in CQD?</span></span>

<span data-ttu-id="b19e4-152">これらの管理者ロールは CQD にアクセスできますが、EUII (エンド ユーザーを特定できる情報) を表示できません。</span><span class="sxs-lookup"><span data-stu-id="b19e4-152">These admin roles can access CQD, but they can't view EUII (end-user identifiable information):</span></span>
- <span data-ttu-id="b19e4-153">Microsoft 365 レポート リーダー</span><span class="sxs-lookup"><span data-stu-id="b19e4-153">Microsoft 365 Reports Reader</span></span>
- <span data-ttu-id="b19e4-154">Teams 通信サポート スペシャリスト</span><span class="sxs-lookup"><span data-stu-id="b19e4-154">Teams Communications Support Specialist</span></span>

<span data-ttu-id="b19e4-155">CQD にアクセスできるロール (EUII を含む) の詳細については [、「CQD](turning-on-and-using-call-quality-dashboard.md#assign-admin-roles-for-access-to-cqd)にアクセスするためにロールを割り当てる」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b19e4-155">To learn more about roles that can access CQD - including EUII - read [Assign roles for accessing CQD](turning-on-and-using-call-quality-dashboard.md#assign-admin-roles-for-access-to-cqd).</span></span>

### <a name="why-am-i-seeing-skype-for-business-information-in-cqd-when-ive-filtered-for-teams-only"></a><span data-ttu-id="b19e4-156">Teams のみをフィルター処理した場合に、CQD に Skype for Business の情報が表示される理由</span><span class="sxs-lookup"><span data-stu-id="b19e4-156">Why am I seeing Skype for Business information in CQD when I've filtered for Teams only?</span></span>

<span data-ttu-id="b19e4-157">CQD レポート (isTeams = 1) でのみ Teams をフィルター処理する場合、第 1 のエンドポイントが Teams であるすべての呼び出しを *フィルター処理します* 。</span><span class="sxs-lookup"><span data-stu-id="b19e4-157">When you filter for Teams only in CQD reports (isTeams = 1), you're filtering for all calls where the *first endpoint* is Teams.</span></span> <span data-ttu-id="b19e4-158">第 *2 のエンドポイント* が Skype for Business の場合、その情報が CQD レポートに表示されます。</span><span class="sxs-lookup"><span data-stu-id="b19e4-158">If the *second endpoint* is Skype for Business, that information will show up in your CQD report.</span></span>

<span data-ttu-id="b19e4-159">CQDv2 と CQDv3 では CQDv2 にはない新しいシナリオが作成されるので、CQDv3 と CQDv3 の合計カウントは常に異なります。</span><span class="sxs-lookup"><span data-stu-id="b19e4-159">CQDv2 and CQDv3 will always have different total counts since CQDv3 will have new scenarios that CQDv2 will not have.</span></span> <span data-ttu-id="b19e4-160">これは、集計合計または集計された集計された集計値をフィルターを使用して比較すると、期待される違いがあります。</span><span class="sxs-lookup"><span data-stu-id="b19e4-160">That’s why comparing Summary Total or Aggregated all-up numbers with no filters will have these expected differences.</span></span>  

<span data-ttu-id="b19e4-161">顧客のシナリオに応じて、CQDv3 には SFB 2019 オンプレミス通話 (SFB 2019 がデータ コネクタで使用されている場合)、Skype Bot 通話 (AA、CVI、VDI)、ライブ イベント、PSTN 通話が含まれます。</span><span class="sxs-lookup"><span data-stu-id="b19e4-161">Depending on Customers’ scenario, CQDv3 will include SFB 2019 on-premises calls (if SFB 2019 is used with a data connector), Skype Bot calls (AA, CVI, VDI), Live Events and PSTN calls.</span></span> <span data-ttu-id="b19e4-162">お客様が利用できるシナリオ/機能ですが、そのデータは CQD V2 に含められません。</span><span class="sxs-lookup"><span data-stu-id="b19e4-162">Scenarios/Features which are available for the customers, but their data are not in CQD V2.</span></span>

<span data-ttu-id="b19e4-163">たとえば、顧客と 200,000 のオーディオ ストリームが表示され、CQD V2 サマリー レポートで 5000 の失敗が発生すると想定されます。CQD V3 での 300,000 のオーディオ ストリームと 5500 失敗 (2019 のオンプレム通話、CVI 通話、PSTN 通話など) に対する。</span><span class="sxs-lookup"><span data-stu-id="b19e4-163">For instance, it is expected that your customers and you will see 200,000 audio streams, with 5000 failures in CQD V2 Summary Report; versus 300,000 audio streams with 5500 failures (coming from 2019 on-prem calls, CVI calls, PSTN calls etc) in CQD V3.</span></span>

<span data-ttu-id="b19e4-164">予期しない違いがあるかどうかを判断するには、データ全体のさまざまな内訳を確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b19e4-164">In order to determine, if there are any unexpected differences, you must look at various breakdowns of the overall data.</span></span>  <span data-ttu-id="b19e4-165">目的に合った比較を行います。</span><span class="sxs-lookup"><span data-stu-id="b19e4-165">Compare with intent.</span></span>  <span data-ttu-id="b19e4-166">ユーザー エージェント カテゴリ ペアによるデータのスライスは、最初に推奨される項目の 1 つです。</span><span class="sxs-lookup"><span data-stu-id="b19e4-166">Slicing the data by User Agent Category Pair is one of the first things we recommend.</span></span>  <span data-ttu-id="b19e4-167">*First Product と* *Second Product も* 優れたスライサーです。</span><span class="sxs-lookup"><span data-stu-id="b19e4-167">*First Product* and *Second Product* are also good slicers.</span></span>  

### <a name="why-do-my-custom-reports-only-return-a-maximum-of-10000-rows-when-i-know-there-should-be-more-entries"></a><span data-ttu-id="b19e4-168">追加のエントリが必要とわかっているのに、カスタム レポートで返される行数が最大 10,000 行である理由</span><span class="sxs-lookup"><span data-stu-id="b19e4-168">Why do my custom reports only return a maximum of 10,000 rows when I know there should be more entries?</span></span>

<span data-ttu-id="b19e4-169">CQD は集計されたデータ クエリ用に設計され、データ エクスポート用には設計されません。</span><span class="sxs-lookup"><span data-stu-id="b19e4-169">CQD is designed for summarized data queries, and is not designed for data export.</span></span> <span data-ttu-id="b19e4-170">可能な場合は、10,000 行の制限を超えないように、レポートを再構築することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="b19e4-170">We recommend restructuring your reports, where possible, to prevent the 10,000 row limit from being exceeded.</span></span> <span data-ttu-id="b19e4-171">まず、月、年、日付、地域、国など、より大きく基数が小さいディメンションを使用して KPI を確認します。そこから、より高い基数のディメンションにドリルダウンできます。</span><span class="sxs-lookup"><span data-stu-id="b19e4-171">Start by looking at your KPIs using broader, lower-cardinality dimensions, such as Month, Year, Date, Region, Country, etc. From there, you can drill down into increasingly higher-cardinality dimensions.</span></span> <span data-ttu-id="b19e4-172">ヘルプデスクとレポートLocation-Enhanced両方とも、このドリルダウン ワークフローの良い例を示します。</span><span class="sxs-lookup"><span data-stu-id="b19e4-172">The Helpdesk and Location-Enhanced Reports both provide good examples of this drill down workflow.</span></span>

## <a name="related-topics"></a><span data-ttu-id="b19e4-173">関連項目</span><span class="sxs-lookup"><span data-stu-id="b19e4-173">Related topics</span></span>

[<span data-ttu-id="b19e4-174">Teams の通話品質の向上と監視</span><span class="sxs-lookup"><span data-stu-id="b19e4-174">Improve and monitor call quality for Teams</span></span>](monitor-call-quality-qos.md)

[<span data-ttu-id="b19e4-175">CQD とは</span><span class="sxs-lookup"><span data-stu-id="b19e4-175">What is CQD?</span></span>](CQD-what-is-call-quality-dashboard.md)

[<span data-ttu-id="b19e4-176">通話品質ダッシュボード (CQD) を設定する</span><span class="sxs-lookup"><span data-stu-id="b19e4-176">Set up Call Quality Dashboard (CQD)</span></span>](turning-on-and-using-call-quality-dashboard.md)

[<span data-ttu-id="b19e4-177">テナントと建物のデータをアップロードする</span><span class="sxs-lookup"><span data-stu-id="b19e4-177">Upload tenant and building data</span></span>](CQD-upload-tenant-building-data.md)

[<span data-ttu-id="b19e4-178">CQD データとレポート</span><span class="sxs-lookup"><span data-stu-id="b19e4-178">CQD data and reports</span></span>](CQD-data-and-reports.md)

[<span data-ttu-id="b19e4-179">CQD を使用して通話と会議の品質を管理する</span><span class="sxs-lookup"><span data-stu-id="b19e4-179">Use CQD to manage call and meeting quality</span></span>](quality-of-experience-review-guide.md)

[<span data-ttu-id="b19e4-180">CQD で使用できるディメンションとメジャー</span><span class="sxs-lookup"><span data-stu-id="b19e4-180">Dimensions and measures available in CQD</span></span>](dimensions-and-measures-available-in-call-quality-dashboard.md)

[<span data-ttu-id="b19e4-181">CQD でのストリームの分類</span><span class="sxs-lookup"><span data-stu-id="b19e4-181">Stream Classification in CQD</span></span>](stream-classification-in-call-quality-dashboard.md)

[<span data-ttu-id="b19e4-182">Power BI を使用して CQD データを分析する</span><span class="sxs-lookup"><span data-stu-id="b19e4-182">Use Power BI to analyze CQD data</span></span>](CQD-Power-BI-query-templates.md)

[<span data-ttu-id="b19e4-183">Teams のトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="b19e4-183">Teams Troubleshooting</span></span>](https://docs.microsoft.com/MicrosoftTeams/troubleshoot/teams)
