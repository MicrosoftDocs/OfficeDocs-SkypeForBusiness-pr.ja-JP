---
title: 'Lync Server 2013: QoE レポート'
description: 'Lync Server 2013: QoE レポート。'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: QoE reports
ms:assetid: 49c827af-b8dd-4c6e-b0dc-b4bc6d60e9a3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720913(v=OCS.15)
ms:contentKeyID: 63969601
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 55965d246b7f0ddd71eaeeec99d218eaf8819c2e
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48571403"
---
# <a name="qoe-reports-in-lync-server-2013"></a><span data-ttu-id="c77a2-103">Lync Server 2013 の QoE レポート</span><span class="sxs-lookup"><span data-stu-id="c77a2-103">QoE reports in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c77a2-104">_**トピックの最終更新日:** 2014-05-01_</span><span class="sxs-lookup"><span data-stu-id="c77a2-104">_**Topic Last Modified:** 2014-05-01_</span></span>

<div>

## <a name="qoe-summarytrend-reports"></a><span data-ttu-id="c77a2-105">QoE の概要/傾向レポート</span><span class="sxs-lookup"><span data-stu-id="c77a2-105">QoE summary/trend reports</span></span>

<span data-ttu-id="c77a2-106">QoE のサマリー/傾向レポートは、時間のピーク時の使用時間を見つけて、メディアの品質を調べて、組織のネットワークリソースを十分に確保するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="c77a2-106">The QoE summary/trends reports are useful for finding the peak usage times of day and examining the media quality during those times to help assure that your organization's network resources are sufficient.</span></span> <span data-ttu-id="c77a2-107">組織はレポートで利用可能な多くのフィルターを使用して、特定の場所、クライアントとデバイスの種類、およびサーバーのパフォーマンスの数値を特定することもできます。</span><span class="sxs-lookup"><span data-stu-id="c77a2-107">Your organization can also use the many filters available in the report to isolate performance numbers for certain locations, client and device types, and servers.</span></span>

<span data-ttu-id="c77a2-108">QoE の概要/傾向レポートは、次の要素で構成されます。</span><span class="sxs-lookup"><span data-stu-id="c77a2-108">QoE summary/trend reports consist of:</span></span>

  - <span data-ttu-id="c77a2-109">UC から UC へのサマリー/傾向レポート</span><span class="sxs-lookup"><span data-stu-id="c77a2-109">UC-to-UC Summary/Trend Report</span></span>

  - <span data-ttu-id="c77a2-110">PSTN の概要/傾向レポート</span><span class="sxs-lookup"><span data-stu-id="c77a2-110">PSTN Summary/Trend Report</span></span>

  - <span data-ttu-id="c77a2-111">電話会議の概要/傾向レポート</span><span class="sxs-lookup"><span data-stu-id="c77a2-111">Conference Summary/Trend Report</span></span>

</div>

<div>

## <a name="qoe-performance-reports"></a><span data-ttu-id="c77a2-112">QoE パフォーマンスレポート</span><span class="sxs-lookup"><span data-stu-id="c77a2-112">QoE performance reports</span></span>

<span data-ttu-id="c77a2-113">QoE パフォーマンスレポートには、仲介サーバー、音声ビデオ会議サーバー、およびエンドポイントの場所の QoE パフォーマンスに集中する3つのレポートに関する詳細が記載されています。</span><span class="sxs-lookup"><span data-stu-id="c77a2-113">QoE performance reports provide details about the three reports that concentrate on the QoE performance of Mediation Servers, A/V Conferencing Servers, and endpoint locations.</span></span>

</div>

<div>

## <a name="mediation-server-performance-report"></a><span data-ttu-id="c77a2-114">仲介サーバーのパフォーマンスレポート</span><span class="sxs-lookup"><span data-stu-id="c77a2-114">Mediation server performance report</span></span>

<span data-ttu-id="c77a2-115">仲介サーバーのパフォーマンスレポートには、指定された期間中に1つ以上の仲介で得られた指標が一覧表示されます。</span><span class="sxs-lookup"><span data-stu-id="c77a2-115">The Mediation Server Performance report lists the metrics achieved by one or more Mediation during the specified time period.</span></span> <span data-ttu-id="c77a2-116">統合コミュニケーション (UC) ツー仲介サーバーレグの指標と、各呼び出しの仲介サーバー間の区間は別々に報告されます。</span><span class="sxs-lookup"><span data-stu-id="c77a2-116">The metrics for the unified communications (UC)-to-Mediation Server leg and the Mediation Server-to-Gateway leg of each call are reported separately.</span></span> <span data-ttu-id="c77a2-117">このレポートを使用して、組織のさまざまな仲介サーバーのボリュームとパフォーマンスを比較します。</span><span class="sxs-lookup"><span data-stu-id="c77a2-117">Use this report to compare the volume and performance of your organization's various Mediation Servers.</span></span>

<span data-ttu-id="c77a2-118">各仲介サーバー (および各通話区間) に対して、レポートには次のように表示されます。</span><span class="sxs-lookup"><span data-stu-id="c77a2-118">For each Mediation Server (and for each call leg), the report displays the following:</span></span>

  - <span data-ttu-id="c77a2-119">通話の数</span><span class="sxs-lookup"><span data-stu-id="c77a2-119">Number of calls</span></span>

  - <span data-ttu-id="c77a2-120">パケット損失</span><span class="sxs-lookup"><span data-stu-id="c77a2-120">Packet Loss</span></span>

  - <span data-ttu-id="c77a2-121">往復時間</span><span class="sxs-lookup"><span data-stu-id="c77a2-121">Round Trip Time</span></span>

  - <span data-ttu-id="c77a2-122">ずれ</span><span class="sxs-lookup"><span data-stu-id="c77a2-122">Jitter</span></span>

  - <span data-ttu-id="c77a2-123">話し言葉平均意見スコア (MOS)</span><span class="sxs-lookup"><span data-stu-id="c77a2-123">Conversational mean opinion score (MOS)</span></span>

  - <span data-ttu-id="c77a2-124">MOS の送信</span><span class="sxs-lookup"><span data-stu-id="c77a2-124">Sending MOS</span></span>

  - <span data-ttu-id="c77a2-125">リスニング MOS</span><span class="sxs-lookup"><span data-stu-id="c77a2-125">Listening MOS</span></span>

  - <span data-ttu-id="c77a2-126">ネットワーク MOS</span><span class="sxs-lookup"><span data-stu-id="c77a2-126">Network MOS</span></span>

  - <span data-ttu-id="c77a2-127">ネットワーク MOS の低下</span><span class="sxs-lookup"><span data-stu-id="c77a2-127">Network MOS Degradation</span></span>

  - <span data-ttu-id="c77a2-128">エコーリターン</span><span class="sxs-lookup"><span data-stu-id="c77a2-128">Echo Return</span></span>

  - <span data-ttu-id="c77a2-129">シグナルレベル</span><span class="sxs-lookup"><span data-stu-id="c77a2-129">Signal Level</span></span>

</div>

<div>

## <a name="av-conferencing-server-performance-report"></a><span data-ttu-id="c77a2-130">音声ビデオ会議サーバーのパフォーマンスレポート</span><span class="sxs-lookup"><span data-stu-id="c77a2-130">A/V conferencing server performance report</span></span>

<span data-ttu-id="c77a2-131">音声ビデオ会議サーバーのパフォーマンスレポートでは、指定された期間中に1つ以上の音声ビデオ会議サーバーによって得られる指標の一覧が示されます。</span><span class="sxs-lookup"><span data-stu-id="c77a2-131">The A/V Conferencing Server Performance report provides lists of metrics achieved by one or more A/V Conferencing Servers during the specified time period.</span></span> <span data-ttu-id="c77a2-132">このレポートは、組織のさまざまな音声ビデオ会議サーバーのボリュームとパフォーマンスを比較するために使用できます。</span><span class="sxs-lookup"><span data-stu-id="c77a2-132">This report can be used to compare the volume and performance of your organization’s various A/V Conferencing Servers.</span></span> <span data-ttu-id="c77a2-133">また、組織でレポートを分離して、Lync クライアントや PSTN クライアントなど、特定のクライアントの種類に関する実績のみを表示することもできます。</span><span class="sxs-lookup"><span data-stu-id="c77a2-133">Your organization can also isolate the report to show only the experience for specific client types, such as Lync clients or PSTN clients.</span></span>

<span data-ttu-id="c77a2-134">音声ビデオ会議サーバーごとに、レポートに次のメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="c77a2-134">For each A/V Conferencing Server, the report displays the following:</span></span>

  - <span data-ttu-id="c77a2-135">電話会議の数</span><span class="sxs-lookup"><span data-stu-id="c77a2-135">Number of conferences</span></span>

  - <span data-ttu-id="c77a2-136">パケット損失</span><span class="sxs-lookup"><span data-stu-id="c77a2-136">Packet Loss</span></span>

  - <span data-ttu-id="c77a2-137">往復時間</span><span class="sxs-lookup"><span data-stu-id="c77a2-137">Round Trip Time</span></span>

  - <span data-ttu-id="c77a2-138">ずれ</span><span class="sxs-lookup"><span data-stu-id="c77a2-138">Jitter</span></span>

  - <span data-ttu-id="c77a2-139">話し言葉平均意見スコア (MOS)</span><span class="sxs-lookup"><span data-stu-id="c77a2-139">Conversational mean opinion score (MOS)</span></span>

  - <span data-ttu-id="c77a2-140">MOS の送信</span><span class="sxs-lookup"><span data-stu-id="c77a2-140">Sending MOS</span></span>

  - <span data-ttu-id="c77a2-141">リスニング MOS</span><span class="sxs-lookup"><span data-stu-id="c77a2-141">Listening MOS</span></span>

  - <span data-ttu-id="c77a2-142">ネットワーク MOS</span><span class="sxs-lookup"><span data-stu-id="c77a2-142">Network MOS</span></span>

  - <span data-ttu-id="c77a2-143">ネットワーク MOS の低下</span><span class="sxs-lookup"><span data-stu-id="c77a2-143">Network MOS Degradation</span></span>

  - <span data-ttu-id="c77a2-144">エコーリターン</span><span class="sxs-lookup"><span data-stu-id="c77a2-144">Echo Return</span></span>

  - <span data-ttu-id="c77a2-145">シグナルレベル</span><span class="sxs-lookup"><span data-stu-id="c77a2-145">Signal Level</span></span>

</div>

<div>

## <a name="location-based-performance-report"></a><span data-ttu-id="c77a2-146">場所に基づくパフォーマンスレポート</span><span class="sxs-lookup"><span data-stu-id="c77a2-146">Location-based performance report</span></span>

<span data-ttu-id="c77a2-147">Location-Based パフォーマンスレポートには、ネットワークの場所の一覧が表示され、それぞれの場所について、事前に決められた各品質の範囲内の呼び出しの数が表示されます。</span><span class="sxs-lookup"><span data-stu-id="c77a2-147">The Location-Based Performance report provides a list of network locations and for each location shows the number of calls in each pre-determined range of quality.</span></span> <span data-ttu-id="c77a2-148">このレポートの目的は、さまざまな場所に対する組織の電話の大部分のメディア品質についての洞察を提供することによって、組織のさまざまな場所で実行されているさまざまなメディア品質を知ることができるようにすることです。</span><span class="sxs-lookup"><span data-stu-id="c77a2-148">The goal of this report is to provide insight into the media quality of the bulk of your organization’s telephone calls for various locations so that you can identify poorly performing locations, and see the different grades of media quality in your organization’s different locations.</span></span>

<span data-ttu-id="c77a2-149">レポートを表示すると、測定基準の異なるテーブルが表示されます。組織がレポートを決定する指標ごとに1つのテーブルが表示されます。</span><span class="sxs-lookup"><span data-stu-id="c77a2-149">When displaying the report, different tables of metrics appear—one table for each metric your organization decides to report on.</span></span> <span data-ttu-id="c77a2-150">このレポートには、次の指標を選択できます。</span><span class="sxs-lookup"><span data-stu-id="c77a2-150">You can choose from the following metrics for this report:</span></span>

  - <span data-ttu-id="c77a2-151">話し言葉平均意見スコア (MOS)</span><span class="sxs-lookup"><span data-stu-id="c77a2-151">Conversational mean opinion score (MOS)</span></span>

  - <span data-ttu-id="c77a2-152">ネットワーク MOS</span><span class="sxs-lookup"><span data-stu-id="c77a2-152">Network MOS</span></span>

  - <span data-ttu-id="c77a2-153">ネットワーク MOS の低下</span><span class="sxs-lookup"><span data-stu-id="c77a2-153">Network MOS Degradation</span></span>

  - <span data-ttu-id="c77a2-154">MOS の送信</span><span class="sxs-lookup"><span data-stu-id="c77a2-154">Sending MOS</span></span>

  - <span data-ttu-id="c77a2-155">リスニング MOS</span><span class="sxs-lookup"><span data-stu-id="c77a2-155">Listening MOS</span></span>

  - <span data-ttu-id="c77a2-156">パケット損失</span><span class="sxs-lookup"><span data-stu-id="c77a2-156">Packet Loss</span></span>

  - <span data-ttu-id="c77a2-157">ずれ</span><span class="sxs-lookup"><span data-stu-id="c77a2-157">Jitter</span></span>

  - <span data-ttu-id="c77a2-158">遅延</span><span class="sxs-lookup"><span data-stu-id="c77a2-158">Latency</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

