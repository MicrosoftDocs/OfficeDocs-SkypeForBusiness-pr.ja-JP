---
title: CQD PSTN ダイレクト ルーティング レポートの使用
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.reviewer: siunies, fan.fan
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
description: Microsoft Teams 通話品質ダッシュボード (CQD)) PSTN ダイレクト ルーティング レポートを使用して、Microsoft Teams での PSTN 通話を監視およびトラブルシューティングします。
ms.openlocfilehash: f2b63f991f42aa4de9e0e4474137f7f992f95c53
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51094981"
---
# <a name="using-the-cqd-pstn-direct-routing-report"></a><span data-ttu-id="bccad-103">CQD PSTN ダイレクト ルーティング レポートの使用</span><span class="sxs-lookup"><span data-stu-id="bccad-103">Using the CQD PSTN Direct Routing report</span></span>

<span data-ttu-id="bccad-104">2020 年 3 月の新機能として、Microsoft Teams 通話品質ダッシュボード (CQD) PSTN ダイレクト ルーティング レポートを [CQD](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/CQD-Power-BI-query-templates.zip?raw=true)用にダウンロード可能な Power BI クエリ テンプレートに追加しました。</span><span class="sxs-lookup"><span data-stu-id="bccad-104">New in March 2020, we've added a Microsoft Teams Call Quality Dashboard (CQD) PSTN Direct Routing report to our downloadable [Power BI query templates for CQD](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/CQD-Power-BI-query-templates.zip?raw=true).</span></span> 


<span data-ttu-id="bccad-105">CQD PSTN ダイレクト ルーティング レポート (CQD PSTN ダイレクト ルーティング レポート.pbit) は、PSTN サービスの使用パターンと品質を理解するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="bccad-105">The CQD PSTN Direct Routing report (CQD PSTN Direct Routing Report.pbit) helps you understand the usage patterns and quality of your PSTN services.</span></span> <span data-ttu-id="bccad-106">このレポートを使用して、サービスの使用状況、セッション ボーダー コントローラー (SBC)、テレフォニー サービス、ネットワーク パラメーター、ネットワーク有効性比の詳細に関する情報を監視します。</span><span class="sxs-lookup"><span data-stu-id="bccad-106">Use this report to monitor service usage, information about your Session Border Controller (SBC), the telephony service, network parameters, and Network Effectiveness Ratio details.</span></span> <span data-ttu-id="bccad-107">この情報は、通話をドロップした理由など、問題を特定するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="bccad-107">This information can help you identify issues, including the reason for dropped calls.</span></span> <span data-ttu-id="bccad-108">たとえば、ボリュームが低下した場合や、影響を受ける通話の数と理由を確認できます。</span><span class="sxs-lookup"><span data-stu-id="bccad-108">For example, you'll be able to see when volume drops, or how many calls get affected and for what reason.</span></span>


<span data-ttu-id="bccad-109">CQD PSTN ダイレクト ルーティング レポートには、次の 4 つのセクションがあります。</span><span class="sxs-lookup"><span data-stu-id="bccad-109">The CQD PSTN Direct Routing Report has four sections:</span></span>

  - [<span data-ttu-id="bccad-110">PSTN の概要</span><span class="sxs-lookup"><span data-stu-id="bccad-110">PSTN Overview</span></span>](#pstn-overview)

  - [<span data-ttu-id="bccad-111">サービスの詳細</span><span class="sxs-lookup"><span data-stu-id="bccad-111">Service Details</span></span>](#service-details)

  - [<span data-ttu-id="bccad-112">ネットワークの有効性の比率</span><span class="sxs-lookup"><span data-stu-id="bccad-112">Network Effectiveness Ratio</span></span>](#network-effectiveness-ratio)

  - [<span data-ttu-id="bccad-113">ネットワーク パラメーター</span><span class="sxs-lookup"><span data-stu-id="bccad-113">Network Parameters</span></span>](#network-parameters)

## <a name="highlights"></a><span data-ttu-id="bccad-114">ハイライト</span><span class="sxs-lookup"><span data-stu-id="bccad-114">Highlights</span></span>

1. <span data-ttu-id="bccad-115">通話の種類、SBC、発信者、通話先の国で分析する</span><span class="sxs-lookup"><span data-stu-id="bccad-115">Analyze by call type, SBC, caller and callee country</span></span>

   <span data-ttu-id="bccad-116">CQD PSTN ダイレクト ルーティング レポートは、過去 7、30 日、または 180 日間 (6 か月間) のテナント上のすべての SPC の信頼性と使用状況に関する指標を集計します。</span><span class="sxs-lookup"><span data-stu-id="bccad-116">The CQD PSTN Direct Routing report aggregates reliability and usage metrics for all SBCs on your tenant for the last 7, 30, or 180 days (6 months).</span></span> <span data-ttu-id="bccad-117">通話の種類、SBC、発信者、通話先の国別にデータを分析できます。</span><span class="sxs-lookup"><span data-stu-id="bccad-117">You can analyze data by call type, SBC, caller and callee country.</span></span> <span data-ttu-id="bccad-118">特定の SBC または国に関心がある場合は、選択した時間範囲の傾向の変化を特定できます。</span><span class="sxs-lookup"><span data-stu-id="bccad-118">If you're interested in a particular SBC or country, you'll be able to identify changes in trends over the selected time range.</span></span>
   :::image type="content" source="media/CQD-PSTN-report8.png" alt-text="CQD PSTN ダイレクト ルーティング レポートで利用できるフィルターのスクリーンショット":::
   
2. <span data-ttu-id="bccad-120">傾向を追跡する</span><span class="sxs-lookup"><span data-stu-id="bccad-120">Track trends</span></span>

    <span data-ttu-id="bccad-121">傾向分析は、サービスの使用状況と信頼性を理解する場合に不可欠です。</span><span class="sxs-lookup"><span data-stu-id="bccad-121">Trends analysis is essential when trying to understand service usage and reliability.</span></span> <span data-ttu-id="bccad-122">時間別の傾向は、毎日のパフォーマンスを詳細に把握し、リアルタイム のインシデントを特定するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="bccad-122">Hourly trends provide a close look at daily performance, which helps identify real-time incidents.</span></span> <span data-ttu-id="bccad-123">毎日の傾向を見ると、長期的な観点からサービスの正常性を確認できます。</span><span class="sxs-lookup"><span data-stu-id="bccad-123">Daily trends let you see your service health from a long-term perspective.</span></span> <span data-ttu-id="bccad-124">適切なデータ細分性を持つ 2 つのモード間でシフトすることが重要です。</span><span class="sxs-lookup"><span data-stu-id="bccad-124">It's important to be able to shift between those two modes with appropriate data granularity.</span></span> <span data-ttu-id="bccad-125">CQD PSTN ダイレクト ルーティング レポートには、6 か月間の傾向の概要、1 日 7 日と 30 日の傾向、時間別の傾向が表示され、各レベルでパフォーマンスを分析できます。</span><span class="sxs-lookup"><span data-stu-id="bccad-125">The CQD PSTN Direct Routing report provides 6-month trends overview, 7- and 30-day daily trends, and hourly trends so you can analyze performance at each level.</span></span>
    :::image type="content" source="media/CQD-PSTN-report9.png" alt-text="CQD PSTN ダイレクト ルーティング レポートの傾向グラフのスクリーンショット":::

3. <span data-ttu-id="bccad-127">SBC またはユーザー レベルにドリル スルーする</span><span class="sxs-lookup"><span data-stu-id="bccad-127">Drill through to SBC or user level</span></span>

   <span data-ttu-id="bccad-128">CQD では、CQD の多くのデータ カテゴリにドリルスルー機能を組み込み、SBC またはユーザー レベルでの使用状況や信頼性の分布をすばやく把握できます。</span><span class="sxs-lookup"><span data-stu-id="bccad-128">We've been building in drill-through capability on many data categories in CQD, which lets you quickly understand usage or reliability distribution at the SBC or user level.</span></span> <span data-ttu-id="bccad-129">ドリル スルーを使用すると、問題をすばやく特定し、実際のユーザーへの影響を把握できます。</span><span class="sxs-lookup"><span data-stu-id="bccad-129">By using drill through, you can quickly poinpoint issues and understand real user impact.</span></span> <span data-ttu-id="bccad-130">CQD PSTN ダイレクト ルーティング レポートでは、サービスの詳細とネットワークの有効性の比率に関するメトリックの詳細が表示されます。</span><span class="sxs-lookup"><span data-stu-id="bccad-130">The CQD PSTN Direct Routing report features drill through on the Service Detail and Network Effectiveness Ratio metrics.</span></span> <span data-ttu-id="bccad-131">詳細を表示するデータ ポイントをクリックして、SBC またはユーザー レベルの詳細を表示します。</span><span class="sxs-lookup"><span data-stu-id="bccad-131">Click the data point you're interested in to drill through to SBC- or user-level details.</span></span>
   :::image type="content" source="media/CQD-PSTN-report10.png" alt-text="データ ポイントのドリルスルー機能を示すスクリーンショット":::


## <a name="pstn-overview"></a><span data-ttu-id="bccad-133">PSTN の概要</span><span class="sxs-lookup"><span data-stu-id="bccad-133">PSTN Overview</span></span>

<span data-ttu-id="bccad-134">CQD PSTN ダイレクト ルーティング レポートでは、過去 180 日間のサービスの全体的な正常性に関する次の情報が提供されます。</span><span class="sxs-lookup"><span data-stu-id="bccad-134">The CQD PSTN Direct Routing Report provides the following information related to overall health of the service for the past 180 days.</span></span>
<span data-ttu-id="bccad-135">![スクリーンショット: PSTN CQD レポート](media/CQD-PSTN-report1.png)</span><span class="sxs-lookup"><span data-stu-id="bccad-135">![Screenshot: PSTN CQD report](media/CQD-PSTN-report1.png)</span></span>

<span data-ttu-id="bccad-136">たとえば、SBC 経由のすべての着信通話に関する全体的な使用状況と正常性に関心がある場合は、abc.bca.adatum.biz 米国を内部の国として使用できます。</span><span class="sxs-lookup"><span data-stu-id="bccad-136">For example, if you are interested in the overall usage and health about all inbound calls going through SBC abc.bca.adatum.biz with US as the internal country:</span></span>

| <span data-ttu-id="bccad-137">**コールアウト**</span><span class="sxs-lookup"><span data-stu-id="bccad-137">**Call Out**</span></span> | <span data-ttu-id="bccad-138">**説明**</span><span class="sxs-lookup"><span data-stu-id="bccad-138">**Description**</span></span>                                                                                                                                                 |
| ------------ | --------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| <span data-ttu-id="bccad-139">1</span><span class="sxs-lookup"><span data-stu-id="bccad-139">1</span></span>            | <span data-ttu-id="bccad-140">上部にあるフィルターを使用して、通話の種類として ByotIn をドリルダウンして選択し、セッション abc.bca.contoso.com コントローラーとして、米国を内部の国として選択できます。</span><span class="sxs-lookup"><span data-stu-id="bccad-140">You can use the filters at the top to drill down and select ByotIn as call type, abc.bca.contoso.com as Session Boarder Controller, and US as internal country.</span></span> |
| <span data-ttu-id="bccad-141">2</span><span class="sxs-lookup"><span data-stu-id="bccad-141">2</span></span>            | <span data-ttu-id="bccad-142">過去 180 日間の使用状況の傾向。</span><span class="sxs-lookup"><span data-stu-id="bccad-142">Usage trend for the past 180 days.</span></span> <span data-ttu-id="bccad-143">利用状況の詳細レポートは、[サービスの詳細] ページで確認できます。</span><span class="sxs-lookup"><span data-stu-id="bccad-143">You can find usage detail report on Service Detail page.</span></span>                                                                     |
| <span data-ttu-id="bccad-144">3</span><span class="sxs-lookup"><span data-stu-id="bccad-144">3</span></span>            | <span data-ttu-id="bccad-145">過去 180 日間のダイヤル後の遅延、遅延、ジッター、パケット損失の傾向。</span><span class="sxs-lookup"><span data-stu-id="bccad-145">Post Dial Delay, Latency, Jitter, and Packet Loss trend for the past 180 days.</span></span> <span data-ttu-id="bccad-146">詳細レポートは、[ネットワーク パラメーター] ページで確認できます。</span><span class="sxs-lookup"><span data-stu-id="bccad-146">You can find detail report on Network Parameters page.</span></span>                           |
| <span data-ttu-id="bccad-147">4</span><span class="sxs-lookup"><span data-stu-id="bccad-147">4</span></span>            | <span data-ttu-id="bccad-148">過去 180 日間の同時通話と毎日のアクティブ ユーザーの傾向。</span><span class="sxs-lookup"><span data-stu-id="bccad-148">Concurrent Call and Daily Active User trend for the past 180 days.</span></span> <span data-ttu-id="bccad-149">このグラフは、サービスの最大ボリュームを理解するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="bccad-149">This chart can help you understand the max volume of the service.</span></span>                            |
| <span data-ttu-id="bccad-150">5</span><span class="sxs-lookup"><span data-stu-id="bccad-150">5</span></span>            | <span data-ttu-id="bccad-151">トップ通話終了の理由は、過去 180 日間のサービス品質に影響しました。</span><span class="sxs-lookup"><span data-stu-id="bccad-151">Top Call End Reason affected service quality for the past 180 days.</span></span> <span data-ttu-id="bccad-152">サービス正常性の詳細については、Network Effective Ratio(NER) ページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="bccad-152">You can find service health detail on Network Effective Ratio(NER) page.</span></span>                    |

## <a name="service-details"></a><span data-ttu-id="bccad-153">サービスの詳細</span><span class="sxs-lookup"><span data-stu-id="bccad-153">Service Details</span></span>

<span data-ttu-id="bccad-154">このページでは、1 日あたりのサービス使用状況の傾向と、地理的なユーザー フィードバックの内訳を示します。</span><span class="sxs-lookup"><span data-stu-id="bccad-154">This page provides service usage trends per day and user feedback breakdown by geographic.</span></span>

  - <span data-ttu-id="bccad-155">**合計試行回数 :** その時間範囲内の合計試行回数 (成功した通話と失敗した通話の両方を含む)</span><span class="sxs-lookup"><span data-stu-id="bccad-155">**Total Attempt Calls –** Total attempt calls in that time range, including both success and failed calls</span></span>

  - <span data-ttu-id="bccad-156">**接続された通話の合計 -** その時間範囲内の接続された通話の合計</span><span class="sxs-lookup"><span data-stu-id="bccad-156">**Total Connected Calls -** Total connected calls in that time range</span></span>

  - <span data-ttu-id="bccad-157">**合計分数 –** その時間範囲での分の合計使用量</span><span class="sxs-lookup"><span data-stu-id="bccad-157">**Total Minutes –** Total minute usage in that time range</span></span>

  - <span data-ttu-id="bccad-158">**日次アクティブ ユーザー (DAU) –** その日に少なくとも 1 つの接続された通話を行った毎日のアクティブ ユーザーの数</span><span class="sxs-lookup"><span data-stu-id="bccad-158">**Daily Active Users(DAU) –** Count of daily active user who made at least one connected call in that day</span></span>

  - <span data-ttu-id="bccad-159">**同時呼び出し –** アクティブな同時呼び出しの最大時間 (1 分)</span><span class="sxs-lookup"><span data-stu-id="bccad-159">**Concurrent Calls –** Max of simultaneous active calls in a minute</span></span>

  - <span data-ttu-id="bccad-160">**ユーザー フィードバック –** "通話の評価" スコアはユーザーから提供されます。</span><span class="sxs-lookup"><span data-stu-id="bccad-160">**User Feedback –** "Rate My Call" score comes from the user.</span></span> <span data-ttu-id="bccad-161">3-5 は良い呼び出しと見なされます。</span><span class="sxs-lookup"><span data-stu-id="bccad-161">3-5 is considered as a good call.</span></span> <span data-ttu-id="bccad-162">1 から 2 は、悪い呼び出しと見なされます。</span><span class="sxs-lookup"><span data-stu-id="bccad-162">1-2 is considered as a bad call.</span></span>

![スクリーンショット: PSTN CQD レポート](media/CQD-PSTN-report2.png)

<span data-ttu-id="bccad-164">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="bccad-164">For example:</span></span>

1.  <span data-ttu-id="bccad-165">2020/02/14 に平均通話時間が 0 に低下した場合は、最初に通話音量が正常に表示されるのを確認し、接続通話の合計と試行回数の合計に大きな不一致が発生した場合に確認できます。</span><span class="sxs-lookup"><span data-stu-id="bccad-165">If you see average call duration drops to 0 at 02/14/2020, you can first check if the call volume looks normal and see if there is a big discrepancy between total connect calls and total attempt calls.</span></span> <span data-ttu-id="bccad-166">次に、[ネットワーク有効性比] ページに移動して、通話障害の理由に投資します。</span><span class="sxs-lookup"><span data-stu-id="bccad-166">Then go to Network Effectiveness Ratio page to invest on call failure reasons.</span></span>

2.  <span data-ttu-id="bccad-167">ユーザー フィードバック マップに赤色のスポットが増えている場合は、[ネットワーク有効性比] ページと [ネットワーク パラメーター] に移動して、異常が発生した場合、MS Service Desk を使用してチケットを上げる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="bccad-167">If you see increasing red spots on the user feedback map, you could go to Network Effectiveness Ratio page and Network Parameter to see if there are any anomalies and you could raise a ticket using MS Service Desk.</span></span>

## <a name="network-effectiveness-ratio"></a><span data-ttu-id="bccad-168">ネットワークの有効性の比率</span><span class="sxs-lookup"><span data-stu-id="bccad-168">Network Effectiveness Ratio</span></span>

<span data-ttu-id="bccad-169">これは、正常性全体ダッシュボードに表示されるのと同じメトリックです。</span><span class="sxs-lookup"><span data-stu-id="bccad-169">This is the same metric that appears on the Overall Health dashboard.</span></span> <span data-ttu-id="bccad-170">時間的ネットワークの有効性の比率と通話終了理由のグラフでは、影響を受ける通話の詳細 (着信/発信) について、時間次 NER 番号を確認できます。</span><span class="sxs-lookup"><span data-stu-id="bccad-170">You can check hourly NER number with affected calls detail for both call directions (inbound/outbound) on the Hourly network effectiveness ratio and call ending reason chart below.</span></span>

  - <span data-ttu-id="bccad-171">**NER** - 能力 (%)送信された通話数と受信者に配信された通話の数を測定して、通話を配信するネットワークの数。</span><span class="sxs-lookup"><span data-stu-id="bccad-171">**NER** - The ability (%) of a network to deliver calls by measuring the number of calls sent versus the number of calls delivered to a recipient.</span></span>

  - <span data-ttu-id="bccad-172">**SIP 応答コード**- 3 桁の整数応答コードは、通話の状態を示します。</span><span class="sxs-lookup"><span data-stu-id="bccad-172">**SIP response code**- A three-digit integer response code shows the call status.</span></span>

  - <span data-ttu-id="bccad-173">**Microsoft 応答コード**- Microsoft コンポーネントから送信された応答コード。</span><span class="sxs-lookup"><span data-stu-id="bccad-173">**Microsoft response code**-A response code sent out from Microsoft component.</span></span>

  - <span data-ttu-id="bccad-174">**説明** – SIP 応答コードと Microsoft 応答コードに対応する理由フェーズ。</span><span class="sxs-lookup"><span data-stu-id="bccad-174">**Description** – The reason phase that corresponding to the SIP response code and Microsoft response code.</span></span>

  - <span data-ttu-id="bccad-175">**影響を受ける通話の数** – 選択した期間中に影響を受けた通話の総数。</span><span class="sxs-lookup"><span data-stu-id="bccad-175">**Number of calls affected** – The total number of calls got affected during the selected time range.</span></span>

> ![スクリーンショット: PSTN CQD レポート](media/CQD-PSTN-report3.png)
> 
<span data-ttu-id="bccad-177">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="bccad-177">For example:</span></span>

![スクリーンショット: PSTN CQD レポート](media/CQD-PSTN-report4.png)

<span data-ttu-id="bccad-179">Daily NER が 2020/02/05 に一気に入った場合は、日付をクリックすると、他のグラフで特定の日付が拡大表示されます。</span><span class="sxs-lookup"><span data-stu-id="bccad-179">If Daily NER has a dip on 02/05/2020, you can click on the date and other charts will zoom to that specific date.</span></span>

![スクリーンショット: PSTN CQD レポート](media/CQD-PSTN-report5.png)

<span data-ttu-id="bccad-181">NER の良いパーセンテージの時間次傾向から、21:00 頃にひと泳ぎが起こるのを確認できます。</span><span class="sxs-lookup"><span data-stu-id="bccad-181">From the NER Good Percentage Hourly Trend, you can find the dip happens around 21:00.</span></span> <span data-ttu-id="bccad-182">次に、もう一度クリックして時間 21 に拡大し、[効果付き通話の詳細] をオンにし、その時間に失敗した通話の数と通話終了の理由を確認します。</span><span class="sxs-lookup"><span data-stu-id="bccad-182">Then click again to zoom to hour 21 and check Effected Call Details to see how many calls failed in that hour and what are the call end reasons.</span></span> <span data-ttu-id="bccad-183">SBC の問題に関する自己トラブルから開始するか、問題が SBC に関連していない場合はサービス デスクに報告します。</span><span class="sxs-lookup"><span data-stu-id="bccad-183">You can start with self-trouble shooting on any SBC problems or report to Service Desk if the problem is not related to SBC.</span></span>

## <a name="network-parameters"></a><span data-ttu-id="bccad-184">ネットワーク パラメーター</span><span class="sxs-lookup"><span data-stu-id="bccad-184">Network Parameters</span></span>

<span data-ttu-id="bccad-185">すべてのネットワーク パラメーターは、直接ルーティング インターフェイスからセッション ボーダー コントローラーに測定されます。</span><span class="sxs-lookup"><span data-stu-id="bccad-185">All network parameters are measured from the Direct Routing interface to the Session Border Controller.</span></span> <span data-ttu-id="bccad-186">推奨される値の詳細については、「組織のネットワークを [Microsoft Teams](prepare-network.md)用に準備する」を参照し、カスタマー エッジから Microsoft Edge への推奨値を参照してください。</span><span class="sxs-lookup"><span data-stu-id="bccad-186">For information about the recommended values, see [Prepare your organization's network for Microsoft Teams](prepare-network.md), and look at the Customer Edge to Microsoft Edge recommended values.</span></span>

  - <span data-ttu-id="bccad-187">**Jitter** – RTCP (RTP コントロール プロトコル) を使用して 2 つのエンドポイント間で計算されるネットワーク伝達遅延時間の変化のミリ秒単位の測定です。</span><span class="sxs-lookup"><span data-stu-id="bccad-187">**Jitter** – Is the millisecond measure of variation in network propagation delay time computed between two endpoints using RTCP (The RTP Control Protocol).</span></span>

  - <span data-ttu-id="bccad-188">**[パケット損失** ] - パケットの受信に失敗したメジャーです。2 つのエンドポイント間で計算されます。</span><span class="sxs-lookup"><span data-stu-id="bccad-188">**Packet Loss** – Is a measure of packet that failed to arrive; it is computed between two endpoints.</span></span>

  - <span data-ttu-id="bccad-189">**遅延** - (ラウンドトリップ時間とも呼ばれる) は、信号が送信される時間の長さと、その信号の確認応答が受信されるのにかかる時間の長さです。</span><span class="sxs-lookup"><span data-stu-id="bccad-189">**Latency** - (Also known as round trip time) is the length of time it takes for a signal to be sent plus the length of time it takes for the acknowledgment of that signal to be received.</span></span> <span data-ttu-id="bccad-190">この時間遅延は、信号の 2 点間の伝達時間で構成されます。</span><span class="sxs-lookup"><span data-stu-id="bccad-190">This time delay consists of the propagation times between the two points of a signal.</span></span>

> ![スクリーンショット: PSTN CQD レポート](media/CQD-PSTN-report6.png)

<span data-ttu-id="bccad-192">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="bccad-192">For example:</span></span>

<span data-ttu-id="bccad-193">特定の日付 (2020/02/14 の遅延など) の 4 つのグラフ (遅延、ジッター、パッケージ損失率、ダイヤル後の遅延) に急上昇が表示される場合は、日付ポイントをクリックします。</span><span class="sxs-lookup"><span data-stu-id="bccad-193">If you see a spike on any of the four charts (Latency, Jitter, Package Loss Rate, Post Dial Delay) for a specific date, for example, Latency on 02/14/2020, click on the date point.</span></span> <span data-ttu-id="bccad-194">下部の時間次傾向グラフが更新され、1 時間の数値が表示されます。</span><span class="sxs-lookup"><span data-stu-id="bccad-194">And the hourly trend chart at the bottom will refresh to show the hourly number.</span></span> <span data-ttu-id="bccad-195">MS Service Desk で SPC を確認したり、チケットを上げすることができます。</span><span class="sxs-lookup"><span data-stu-id="bccad-195">You can check the SBCs or raise a ticket with MS Service Desk.</span></span>

![スクリーンショット: PSTN CQD レポート](media/CQD-PSTN-report7.png)



## <a name="related-topics"></a><span data-ttu-id="bccad-197">関連項目</span><span class="sxs-lookup"><span data-stu-id="bccad-197">Related topics</span></span>

[<span data-ttu-id="bccad-198">Power BI を使用して Microsoft Teams の CQD データを分析する</span><span class="sxs-lookup"><span data-stu-id="bccad-198">Use Power BI to analyze CQD data for Microsoft Teams</span></span>](CQD-PSTN-report.md)

[<span data-ttu-id="bccad-199">Teams のトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="bccad-199">Teams Troubleshooting</span></span>](/MicrosoftTeams/troubleshoot/teams)