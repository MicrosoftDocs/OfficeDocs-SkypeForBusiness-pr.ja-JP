---
title: CQD PSTN ダイレクトルーティングレポートを使用する
ms.author: lolaj
author: LolaJacobsen
manager: serdars
ms.reviewer: siunies
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.collection:
- M365-voice
search.appverid: MET150
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
description: CQD PSTN ダイレクトルーティングレポートを使用して、Microsoft Teams の PSTN 通話を監視およびトラブルシューティングします。
ms.openlocfilehash: 32d91d56e51c5706c3e460029312f3b6bb6948c3
ms.sourcegitcommit: 98fcfc03c55917d0aca48b7bd97988f81e8930c1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/07/2020
ms.locfileid: "42559486"
---
# <a name="using-the-cqd-pstn-direct-routing-report"></a><span data-ttu-id="2150c-103">CQD PSTN ダイレクトルーティングレポートを使用する</span><span class="sxs-lookup"><span data-stu-id="2150c-103">Using the CQD PSTN Direct Routing Report</span></span>

<span data-ttu-id="2150c-104">2020年3月に初めて、CQD PSTN ダイレクトルーティングレポートを、 [CQD 用のダウンロード可能な POWER BI クエリテンプレート](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/CQD-Power-BI-query-templates.zip?raw=true)に追加しました。</span><span class="sxs-lookup"><span data-stu-id="2150c-104">New in March 2020, we've added a CQD PSTN Direct Routing Report to our downloadable [Power BI query templates for CQD](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/CQD-Power-BI-query-templates.zip?raw=true).</span></span> 


<span data-ttu-id="2150c-105">CQD PSTN ダイレクトルーティングレポートを使用すると、お客様は、お客様の SBC、テレフォニーサービス、ネットワークパラメーター、およびネットワークの有効性比の詳細と使用状況について、PSTN サービスの使用パターンと音質を把握することができます。サービス.</span><span class="sxs-lookup"><span data-stu-id="2150c-105">The CQD PSTN Direct Routing Report helps customers to understand the usage patterns and quality of their PSTN services monitor information about your SBC, the telephony service, the network parameters, and Network Effectiveness Ratio details and usage of the service.</span></span> <span data-ttu-id="2150c-106">この情報は、通話の中断の理由など、問題を特定するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="2150c-106">This information can help you identify issues, including the reason for dropped calls.</span></span> <span data-ttu-id="2150c-107">たとえば、ボリュームが減少したときに、どのような理由で影響を受ける通話数がわかります。</span><span class="sxs-lookup"><span data-stu-id="2150c-107">For example, you will be able to know when volume drops, how many calls get affected by what reason.</span></span>

<span data-ttu-id="2150c-108">CQD PSTN のダイレクトルーティングレポートには、次の4つのセクションがあります。</span><span class="sxs-lookup"><span data-stu-id="2150c-108">The CQD PSTN Direct Routing Report has four sections:</span></span>

  - [<span data-ttu-id="2150c-109">PSTN の概要</span><span class="sxs-lookup"><span data-stu-id="2150c-109">PSTN Overview</span></span>](#pstn-overview)

  - [<span data-ttu-id="2150c-110">サービスの詳細</span><span class="sxs-lookup"><span data-stu-id="2150c-110">Service Details</span></span>](#service-details)

  - [<span data-ttu-id="2150c-111">ネットワークの有効性比</span><span class="sxs-lookup"><span data-stu-id="2150c-111">Network Effectiveness Ratio</span></span>](#network-effectiveness-ratio)

  - [<span data-ttu-id="2150c-112">ネットワークパラメーター</span><span class="sxs-lookup"><span data-stu-id="2150c-112">Network Parameters</span></span>](#network-parameters)

## <a name="pstn-overview"></a><span data-ttu-id="2150c-113">PSTN の概要</span><span class="sxs-lookup"><span data-stu-id="2150c-113">PSTN Overview</span></span>

<span data-ttu-id="2150c-114">CQD PSTN ダイレクトルーティングレポートでは、過去180日間のサービスの全体的な正常性に関する次の情報が提供されます。</span><span class="sxs-lookup"><span data-stu-id="2150c-114">The CQD PSTN Direct Routing Report provides the following information related to overall health of the service for the past 180 days.</span></span>
<span data-ttu-id="2150c-115">![スクリーンショット: PSTN CQD レポート](media/CQD-PSTN-report1.png)</span><span class="sxs-lookup"><span data-stu-id="2150c-115">![Screenshot: PSTN CQD report](media/CQD-PSTN-report1.png)</span></span>

<span data-ttu-id="2150c-116">たとえば、米国の国内では、すべての着信通話に関する全体的な使用状況と正常性については、次のようになります。</span><span class="sxs-lookup"><span data-stu-id="2150c-116">For example, if you are interested in the overall usage and health about all inbound calls going through SBC abc.bca.adatum.biz with US as the internal country:</span></span>

| <span data-ttu-id="2150c-117">**発信**</span><span class="sxs-lookup"><span data-stu-id="2150c-117">**Call Out**</span></span> | <span data-ttu-id="2150c-118">**説明**</span><span class="sxs-lookup"><span data-stu-id="2150c-118">**Description**</span></span>                                                                                                                                                 |
| ------------ | --------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| <span data-ttu-id="2150c-119">1</span><span class="sxs-lookup"><span data-stu-id="2150c-119">1</span></span>            | <span data-ttu-id="2150c-120">一番上にあるフィルターを使用してドリルダウンし、[通話の種類] として [abc.bca.contoso.com]、[Session Boarder Controller として送信]、[国内] の順に選択することができます。</span><span class="sxs-lookup"><span data-stu-id="2150c-120">You can use the filters at the top to drill down and select ByotIn as call type, abc.bca.contoso.com as Session Boarder Controller, and US as internal country.</span></span> |
| <span data-ttu-id="2150c-121">両面</span><span class="sxs-lookup"><span data-stu-id="2150c-121">2</span></span>            | <span data-ttu-id="2150c-122">過去180日間の使用状況の傾向。</span><span class="sxs-lookup"><span data-stu-id="2150c-122">Usage trend for the past 180 days.</span></span> <span data-ttu-id="2150c-123">利用状況の詳細レポートは、サービスの詳細ページで確認できます。</span><span class="sxs-lookup"><span data-stu-id="2150c-123">You can find usage detail report on Service Detail page.</span></span>                                                                     |
| <span data-ttu-id="2150c-124">3</span><span class="sxs-lookup"><span data-stu-id="2150c-124">3</span></span>            | <span data-ttu-id="2150c-125">過去180日間のダイヤル後の遅延、待ち時間、ジッタ、パケット損失の傾向。</span><span class="sxs-lookup"><span data-stu-id="2150c-125">Post Dial Delay, Latency, Jitter, and Packet Loss trend for the past 180 days.</span></span> <span data-ttu-id="2150c-126">[ネットワークパラメーター] ページで詳細レポートを見つけることができます。</span><span class="sxs-lookup"><span data-stu-id="2150c-126">You can find detail report on Network Parameters page.</span></span>                           |
| <span data-ttu-id="2150c-127">4</span><span class="sxs-lookup"><span data-stu-id="2150c-127">4</span></span>            | <span data-ttu-id="2150c-128">過去180日間の同時呼び出しと1日のアクティブなユーザーの傾向。</span><span class="sxs-lookup"><span data-stu-id="2150c-128">Concurrent Call and Daily Active User trend for the past 180 days.</span></span> <span data-ttu-id="2150c-129">このグラフは、サービスの最大音量を理解するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="2150c-129">This chart can help you understand the max volume of the service.</span></span>                            |
| <span data-ttu-id="2150c-130">5</span><span class="sxs-lookup"><span data-stu-id="2150c-130">5</span></span>            | <span data-ttu-id="2150c-131">上位の通話終了理由過去180日間のサービス品質に影響します。</span><span class="sxs-lookup"><span data-stu-id="2150c-131">Top Call End Reason affected service quality for the past 180 days.</span></span> <span data-ttu-id="2150c-132">サービスの正常性の詳細については、「ネットワークの有効比率 (説明)」ページをご覧ください。</span><span class="sxs-lookup"><span data-stu-id="2150c-132">You can find service health detail on Network Effective Ratio(NER) page.</span></span>                    |

## <a name="service-details"></a><span data-ttu-id="2150c-133">サービスの詳細</span><span class="sxs-lookup"><span data-stu-id="2150c-133">Service Details</span></span>

<span data-ttu-id="2150c-134">このページには、1日あたりのサービス利用傾向と、地理的なユーザーフィードバックの内訳が表示されます。</span><span class="sxs-lookup"><span data-stu-id="2150c-134">This page provides service usage trends per day and user feedback breakdown by geographic.</span></span>

  - <span data-ttu-id="2150c-135">**試行回数の合計:** 成功した通話と失敗した通話の両方を含む、その時間範囲内での通話の合計試行回数</span><span class="sxs-lookup"><span data-stu-id="2150c-135">**Total Attempt Calls –** Total attempt calls in that time range, including both success and failed calls</span></span>

  - <span data-ttu-id="2150c-136">**接続された合計通話-** その時間範囲内の接続されている合計通話数</span><span class="sxs-lookup"><span data-stu-id="2150c-136">**Total Connected Calls -** Total connected calls in that time range</span></span>

  - <span data-ttu-id="2150c-137">**合計分数–** その時間範囲の合計使用時間 (分)</span><span class="sxs-lookup"><span data-stu-id="2150c-137">**Total Minutes –** Total minute usage in that time range</span></span>

  - <span data-ttu-id="2150c-138">**日常的なアクティブユーザー (DAU) –** その日に少なくとも1つ接続されたアクティブなユーザーの数</span><span class="sxs-lookup"><span data-stu-id="2150c-138">**Daily Active Users(DAU) –** Count of daily active user who made at least one connected call in that day</span></span>

  - <span data-ttu-id="2150c-139">**同時通話–** 1分あたりの同時アクティブ通話の最大数</span><span class="sxs-lookup"><span data-stu-id="2150c-139">**Concurrent Calls –** Max of simultaneous active calls in a minute</span></span>

  - <span data-ttu-id="2150c-140">**ユーザのフィードバック–**「通話料金の評価」スコアは、ユーザーによって取得されます。</span><span class="sxs-lookup"><span data-stu-id="2150c-140">**User Feedback –** "Rate My Call" score comes from the user.</span></span> <span data-ttu-id="2150c-141">3-5 は、適切な通話と見なされます。</span><span class="sxs-lookup"><span data-stu-id="2150c-141">3-5 is considered as a good call.</span></span> <span data-ttu-id="2150c-142">1-2 は、不正な通話と見なされます。</span><span class="sxs-lookup"><span data-stu-id="2150c-142">1-2 is considered as a bad call.</span></span>

![スクリーンショット: PSTN CQD レポート](media/CQD-PSTN-report2.png)

<span data-ttu-id="2150c-144">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="2150c-144">For example:</span></span>

1.  <span data-ttu-id="2150c-145">02/14/2020 で平均通話時間が0になる場合は、まず通話音量が正常であるかどうかを確認し、接続の合計数と試行回数の差が大きいかどうかを確認できます。</span><span class="sxs-lookup"><span data-stu-id="2150c-145">If you see average call duration drops to 0 at 02/14/2020, you can first check if the call volume looks normal and see if there is a big discrepancy between total connect calls and total attempt calls.</span></span> <span data-ttu-id="2150c-146">次に、[ネットワークの有効性の比率] ページに移動して、通話の失敗の理由についてご購入ください。</span><span class="sxs-lookup"><span data-stu-id="2150c-146">Then go to Network Effectiveness Ratio page to invest on call failure reasons.</span></span>

2.  <span data-ttu-id="2150c-147">ユーザーフィードバックマップで赤いスポットが増加している場合は、[ネットワークの実効性比] ページと [ネットワークパラメーター] に移動して、異常があるかどうかを確認し、MS サービスデスクを使ってチケットを生成できます。</span><span class="sxs-lookup"><span data-stu-id="2150c-147">If you see increasing red spots on the user feedback map, you could go to Network Effectiveness Ratio page and Network Parameter to see if there are any anomalies and you could raise a ticket using MS Service Desk.</span></span>

## <a name="network-effectiveness-ratio"></a><span data-ttu-id="2150c-148">ネットワークの有効性比</span><span class="sxs-lookup"><span data-stu-id="2150c-148">Network Effectiveness Ratio</span></span>

<span data-ttu-id="2150c-149">これは、全体的な正常性ダッシュボードに表示されるメトリックと同じです。</span><span class="sxs-lookup"><span data-stu-id="2150c-149">This is the same metric that appears on the Overall Health dashboard.</span></span> <span data-ttu-id="2150c-150">時間あたりのネットワークの効率性比と、次に示す通話の終了理由グラフの両方について、通話の方向 (受信/送信) の両方について、影響を受ける通話の詳細を確認できます。</span><span class="sxs-lookup"><span data-stu-id="2150c-150">You can check hourly NER number with affected calls detail for both call directions (inbound/outbound) on the Hourly network effectiveness ratio and call ending reason chart below.</span></span>

  - <span data-ttu-id="2150c-151">\*\*\*\* この機能 (%)通話の発信回数と受信者に送信された通話の数を測定して、通話を発信するネットワークのこと。</span><span class="sxs-lookup"><span data-stu-id="2150c-151">**NER** - The ability (%) of a network to deliver calls by measuring the number of calls sent versus the number of calls delivered to a recipient.</span></span>

  - <span data-ttu-id="2150c-152">**SIP 応答コード**-3 桁の整数応答コードによって通話状態が示されます。</span><span class="sxs-lookup"><span data-stu-id="2150c-152">**SIP response code**- A three-digit integer response code shows the call status.</span></span>

  - <span data-ttu-id="2150c-153">**Microsoft 応答コード**-microsoft コンポーネントから送信される応答コード。</span><span class="sxs-lookup"><span data-stu-id="2150c-153">**Microsoft response code**-A response code sent out from Microsoft component.</span></span>

  - <span data-ttu-id="2150c-154">**説明**– SIP 応答コードと Microsoft の応答コードに対応する理由フェーズ。</span><span class="sxs-lookup"><span data-stu-id="2150c-154">**Description** – The reason phase that corresponding to the SIP response code and Microsoft response code.</span></span>

  - <span data-ttu-id="2150c-155">**影響を受ける通話の数**–選択した期間中に影響を受けた通話の合計数。</span><span class="sxs-lookup"><span data-stu-id="2150c-155">**Number of calls affected** – The total number of calls got affected during the selected time range.</span></span>

> ![スクリーンショット: PSTN CQD レポート](media/CQD-PSTN-report3.png)
> 
<span data-ttu-id="2150c-157">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="2150c-157">For example:</span></span>

![スクリーンショット: PSTN CQD レポート](media/CQD-PSTN-report4.png)

<span data-ttu-id="2150c-159">Daily の場合、02/05/2020 で dip を利用している場合は、日付をクリックすると、その日付に合わせて拡大/縮小することができます。</span><span class="sxs-lookup"><span data-stu-id="2150c-159">If Daily NER has a dip on 02/05/2020, you can click on the date and other charts will zoom to that specific date.</span></span>

![スクリーンショット: PSTN CQD レポート](media/CQD-PSTN-report5.png)

<span data-ttu-id="2150c-161">達成率の1時間の傾向から、21:00 の周りで dip が発生していることがわかります。</span><span class="sxs-lookup"><span data-stu-id="2150c-161">From the NER Good Percentage Hourly Trend, you can find the dip happens around 21:00.</span></span> <span data-ttu-id="2150c-162">もう一度クリックすると、時間21にズームし、影響を受ける通話の詳細を確認して、その時間内に失敗した通話の数と通話の終了理由を確認します。</span><span class="sxs-lookup"><span data-stu-id="2150c-162">Then click again to zoom to hour 21 and check Effected Call Details to see how many calls failed in that hour and what are the call end reasons.</span></span> <span data-ttu-id="2150c-163">問題が SBC に関連していない場合は、SBC の問題が発生した場合、またはサービスデスクに報告する場合は、自己トラブルシューティングを始めることができます。</span><span class="sxs-lookup"><span data-stu-id="2150c-163">You can start with self-trouble shooting on any SBC problems or report to Service Desk if the problem is not related to SBC.</span></span>

## <a name="network-parameters"></a><span data-ttu-id="2150c-164">ネットワークパラメーター</span><span class="sxs-lookup"><span data-stu-id="2150c-164">Network Parameters</span></span>

<span data-ttu-id="2150c-165">すべてのネットワークパラメーターは、ダイレクトルーティングインターフェイスからセッションの境界コントローラーまで計測されます。</span><span class="sxs-lookup"><span data-stu-id="2150c-165">All network parameters are measured from the Direct Routing interface to the Session Border Controller.</span></span> <span data-ttu-id="2150c-166">推奨値の詳細については、「 [Microsoft Teams 用に組織のネットワークを準備](prepare-network.md)する」を参照してください。顧客の Edge を microsoft Edge で推奨される値について確認します。</span><span class="sxs-lookup"><span data-stu-id="2150c-166">For information about the recommended values, see [Prepare your organization's network for Microsoft Teams](prepare-network.md), and look at the Customer Edge to Microsoft Edge recommended values.</span></span>

  - <span data-ttu-id="2150c-167">**ジッター** – RTCP (RTP 制御プロトコル) を使って2つのエンドポイントの間で計算されたネットワーク伝達遅延時間の単位 (ミリ秒) です。</span><span class="sxs-lookup"><span data-stu-id="2150c-167">**Jitter** – Is the millisecond measure of variation in network propagation delay time computed between two endpoints using RTCP (The RTP Control Protocol).</span></span>

  - <span data-ttu-id="2150c-168">**パケット損失**–到着に失敗したパケットの測定。これは、2つのエンドポイントの間で計算されます。</span><span class="sxs-lookup"><span data-stu-id="2150c-168">**Packet Loss** – Is a measure of packet that failed to arrive; it is computed between two endpoints.</span></span>

  - <span data-ttu-id="2150c-169">**待ち時間**-(ラウンドトリップ時間とも呼ばれます) は、シグナルが送信されるまでにかかる時間と、そのシグナルの受信確認にかかる時間の長さです。</span><span class="sxs-lookup"><span data-stu-id="2150c-169">**Latency** - (Also known as round trip time) is the length of time it takes for a signal to be sent plus the length of time it takes for the acknowledgment of that signal to be received.</span></span> <span data-ttu-id="2150c-170">この時間遅延は、シグナルの2つのポイント間の伝播時間で構成されます。</span><span class="sxs-lookup"><span data-stu-id="2150c-170">This time delay consists of the propagation times between the two points of a signal.</span></span>

> ![スクリーンショット: PSTN CQD レポート](media/CQD-PSTN-report6.png)

<span data-ttu-id="2150c-172">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="2150c-172">For example:</span></span>

<span data-ttu-id="2150c-173">4つのグラフ (待機時間、ジッター、パッケージ損失率、事後ダイヤル遅延) のいずれかに、特定の日付 (たとえば、02/14/2020 の待機時間) が表示されている場合は、その日付ポイントをクリックします。</span><span class="sxs-lookup"><span data-stu-id="2150c-173">If you see a spike on any of the four charts (Latency, Jitter, Package Loss Rate, Post Dial Delay) for a specific date, for example, Latency on 02/14/2020, click on the date point.</span></span> <span data-ttu-id="2150c-174">また、下の時間単位の傾向グラフが更新されて、時間単位の数値が表示されます。</span><span class="sxs-lookup"><span data-stu-id="2150c-174">And the hourly trend chart at the bottom will refresh to show the hourly number.</span></span> <span data-ttu-id="2150c-175">MS Service Desk で、SBCs を確認したり、チケットを生成したりできます。</span><span class="sxs-lookup"><span data-stu-id="2150c-175">You can check the SBCs or raise a ticket with MS Service Desk.</span></span>

![スクリーンショット: PSTN CQD レポート](media/CQD-PSTN-report7.png)



## <a name="related-topics"></a><span data-ttu-id="2150c-177">関連項目</span><span class="sxs-lookup"><span data-stu-id="2150c-177">Related topics</span></span>

[<span data-ttu-id="2150c-178">Power BI を使用して Microsoft Teams の CQD データを分析する</span><span class="sxs-lookup"><span data-stu-id="2150c-178">Use Power BI to analyze CQD data for Microsoft Teams</span></span>](CQD-PSTN-report.md)