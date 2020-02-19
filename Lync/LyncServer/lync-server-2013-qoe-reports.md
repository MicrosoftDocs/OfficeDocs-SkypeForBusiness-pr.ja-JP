---
title: 'Lync Server 2013: QoE レポート'
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
ms.openlocfilehash: 9b08544365cf536b791fdfffa5d1d1521a1cc966
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/19/2020
ms.locfileid: "42138928"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="qoe-reports-in-lync-server-2013"></a><span data-ttu-id="50e89-102">Lync Server 2013 の QoE レポート</span><span class="sxs-lookup"><span data-stu-id="50e89-102">QoE reports in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="50e89-103">_**トピックの最終更新日:** 2014-05-01_</span><span class="sxs-lookup"><span data-stu-id="50e89-103">_**Topic Last Modified:** 2014-05-01_</span></span>

<div>

## <a name="qoe-summarytrend-reports"></a><span data-ttu-id="50e89-104">QoE の概要/傾向レポート</span><span class="sxs-lookup"><span data-stu-id="50e89-104">QoE summary/trend reports</span></span>

<span data-ttu-id="50e89-105">QoE のサマリー/傾向レポートは、時間のピーク時の使用時間を見つけて、メディアの品質を調べて、組織のネットワークリソースを十分に確保するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="50e89-105">The QoE summary/trends reports are useful for finding the peak usage times of day and examining the media quality during those times to help assure that your organization's network resources are sufficient.</span></span> <span data-ttu-id="50e89-106">組織はレポートで利用可能な多くのフィルターを使用して、特定の場所、クライアントとデバイスの種類、およびサーバーのパフォーマンスの数値を特定することもできます。</span><span class="sxs-lookup"><span data-stu-id="50e89-106">Your organization can also use the many filters available in the report to isolate performance numbers for certain locations, client and device types, and servers.</span></span>

<span data-ttu-id="50e89-107">QoE の概要/傾向レポートは、次の要素で構成されます。</span><span class="sxs-lookup"><span data-stu-id="50e89-107">QoE summary/trend reports consist of:</span></span>

  - <span data-ttu-id="50e89-108">UC から UC へのサマリー/傾向レポート</span><span class="sxs-lookup"><span data-stu-id="50e89-108">UC-to-UC Summary/Trend Report</span></span>

  - <span data-ttu-id="50e89-109">PSTN の概要/傾向レポート</span><span class="sxs-lookup"><span data-stu-id="50e89-109">PSTN Summary/Trend Report</span></span>

  - <span data-ttu-id="50e89-110">電話会議の概要/傾向レポート</span><span class="sxs-lookup"><span data-stu-id="50e89-110">Conference Summary/Trend Report</span></span>

</div>

<div>

## <a name="qoe-performance-reports"></a><span data-ttu-id="50e89-111">QoE パフォーマンスレポート</span><span class="sxs-lookup"><span data-stu-id="50e89-111">QoE performance reports</span></span>

<span data-ttu-id="50e89-112">QoE パフォーマンスレポートには、仲介サーバー、音声ビデオ会議サーバー、およびエンドポイントの場所の QoE パフォーマンスに集中する3つのレポートに関する詳細が記載されています。</span><span class="sxs-lookup"><span data-stu-id="50e89-112">QoE performance reports provide details about the three reports that concentrate on the QoE performance of Mediation Servers, A/V Conferencing Servers, and endpoint locations.</span></span>

</div>

<div>

## <a name="mediation-server-performance-report"></a><span data-ttu-id="50e89-113">仲介サーバーのパフォーマンスレポート</span><span class="sxs-lookup"><span data-stu-id="50e89-113">Mediation server performance report</span></span>

<span data-ttu-id="50e89-114">仲介サーバーのパフォーマンスレポートには、指定された期間中に1つ以上の仲介で得られた指標が一覧表示されます。</span><span class="sxs-lookup"><span data-stu-id="50e89-114">The Mediation Server Performance report lists the metrics achieved by one or more Mediation during the specified time period.</span></span> <span data-ttu-id="50e89-115">統合コミュニケーション (UC) ツー仲介サーバーレグの指標と、各呼び出しの仲介サーバー間の区間は別々に報告されます。</span><span class="sxs-lookup"><span data-stu-id="50e89-115">The metrics for the unified communications (UC)-to-Mediation Server leg and the Mediation Server-to-Gateway leg of each call are reported separately.</span></span> <span data-ttu-id="50e89-116">このレポートを使用して、組織のさまざまな仲介サーバーのボリュームとパフォーマンスを比較します。</span><span class="sxs-lookup"><span data-stu-id="50e89-116">Use this report to compare the volume and performance of your organization's various Mediation Servers.</span></span>

<span data-ttu-id="50e89-117">各仲介サーバー (および各通話区間) に対して、レポートには次のように表示されます。</span><span class="sxs-lookup"><span data-stu-id="50e89-117">For each Mediation Server (and for each call leg), the report displays the following:</span></span>

  - <span data-ttu-id="50e89-118">通話の数</span><span class="sxs-lookup"><span data-stu-id="50e89-118">Number of calls</span></span>

  - <span data-ttu-id="50e89-119">パケット損失</span><span class="sxs-lookup"><span data-stu-id="50e89-119">Packet Loss</span></span>

  - <span data-ttu-id="50e89-120">往復時間</span><span class="sxs-lookup"><span data-stu-id="50e89-120">Round Trip Time</span></span>

  - <span data-ttu-id="50e89-121">ずれ</span><span class="sxs-lookup"><span data-stu-id="50e89-121">Jitter</span></span>

  - <span data-ttu-id="50e89-122">話し言葉平均意見スコア (MOS)</span><span class="sxs-lookup"><span data-stu-id="50e89-122">Conversational mean opinion score (MOS)</span></span>

  - <span data-ttu-id="50e89-123">MOS の送信</span><span class="sxs-lookup"><span data-stu-id="50e89-123">Sending MOS</span></span>

  - <span data-ttu-id="50e89-124">リスニング MOS</span><span class="sxs-lookup"><span data-stu-id="50e89-124">Listening MOS</span></span>

  - <span data-ttu-id="50e89-125">ネットワーク MOS</span><span class="sxs-lookup"><span data-stu-id="50e89-125">Network MOS</span></span>

  - <span data-ttu-id="50e89-126">ネットワーク MOS の低下</span><span class="sxs-lookup"><span data-stu-id="50e89-126">Network MOS Degradation</span></span>

  - <span data-ttu-id="50e89-127">エコーリターン</span><span class="sxs-lookup"><span data-stu-id="50e89-127">Echo Return</span></span>

  - <span data-ttu-id="50e89-128">シグナルレベル</span><span class="sxs-lookup"><span data-stu-id="50e89-128">Signal Level</span></span>

</div>

<div>

## <a name="av-conferencing-server-performance-report"></a><span data-ttu-id="50e89-129">音声ビデオ会議サーバーのパフォーマンスレポート</span><span class="sxs-lookup"><span data-stu-id="50e89-129">A/V conferencing server performance report</span></span>

<span data-ttu-id="50e89-130">音声ビデオ会議サーバーのパフォーマンスレポートでは、指定された期間中に1つ以上の音声ビデオ会議サーバーによって得られる指標の一覧が示されます。</span><span class="sxs-lookup"><span data-stu-id="50e89-130">The A/V Conferencing Server Performance report provides lists of metrics achieved by one or more A/V Conferencing Servers during the specified time period.</span></span> <span data-ttu-id="50e89-131">このレポートは、組織のさまざまな音声ビデオ会議サーバーのボリュームとパフォーマンスを比較するために使用できます。</span><span class="sxs-lookup"><span data-stu-id="50e89-131">This report can be used to compare the volume and performance of your organization’s various A/V Conferencing Servers.</span></span> <span data-ttu-id="50e89-132">また、組織でレポートを分離して、Lync クライアントや PSTN クライアントなど、特定のクライアントの種類に関する実績のみを表示することもできます。</span><span class="sxs-lookup"><span data-stu-id="50e89-132">Your organization can also isolate the report to show only the experience for specific client types, such as Lync clients or PSTN clients.</span></span>

<span data-ttu-id="50e89-133">音声ビデオ会議サーバーごとに、レポートに次のメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="50e89-133">For each A/V Conferencing Server, the report displays the following:</span></span>

  - <span data-ttu-id="50e89-134">電話会議の数</span><span class="sxs-lookup"><span data-stu-id="50e89-134">Number of conferences</span></span>

  - <span data-ttu-id="50e89-135">パケット損失</span><span class="sxs-lookup"><span data-stu-id="50e89-135">Packet Loss</span></span>

  - <span data-ttu-id="50e89-136">往復時間</span><span class="sxs-lookup"><span data-stu-id="50e89-136">Round Trip Time</span></span>

  - <span data-ttu-id="50e89-137">ずれ</span><span class="sxs-lookup"><span data-stu-id="50e89-137">Jitter</span></span>

  - <span data-ttu-id="50e89-138">話し言葉平均意見スコア (MOS)</span><span class="sxs-lookup"><span data-stu-id="50e89-138">Conversational mean opinion score (MOS)</span></span>

  - <span data-ttu-id="50e89-139">MOS の送信</span><span class="sxs-lookup"><span data-stu-id="50e89-139">Sending MOS</span></span>

  - <span data-ttu-id="50e89-140">リスニング MOS</span><span class="sxs-lookup"><span data-stu-id="50e89-140">Listening MOS</span></span>

  - <span data-ttu-id="50e89-141">ネットワーク MOS</span><span class="sxs-lookup"><span data-stu-id="50e89-141">Network MOS</span></span>

  - <span data-ttu-id="50e89-142">ネットワーク MOS の低下</span><span class="sxs-lookup"><span data-stu-id="50e89-142">Network MOS Degradation</span></span>

  - <span data-ttu-id="50e89-143">エコーリターン</span><span class="sxs-lookup"><span data-stu-id="50e89-143">Echo Return</span></span>

  - <span data-ttu-id="50e89-144">シグナルレベル</span><span class="sxs-lookup"><span data-stu-id="50e89-144">Signal Level</span></span>

</div>

<div>

## <a name="location-based-performance-report"></a><span data-ttu-id="50e89-145">場所に基づくパフォーマンスレポート</span><span class="sxs-lookup"><span data-stu-id="50e89-145">Location-based performance report</span></span>

<span data-ttu-id="50e89-146">場所に基づくパフォーマンスレポートには、ネットワークの場所の一覧が表示されます。また、各場所には、事前に決められた各品質の範囲内の呼び出しの数が表示されます。</span><span class="sxs-lookup"><span data-stu-id="50e89-146">The Location-Based Performance report provides a list of network locations and for each location shows the number of calls in each pre-determined range of quality.</span></span> <span data-ttu-id="50e89-147">このレポートの目的は、さまざまな場所に対する組織の電話の大部分のメディア品質についての情報を提供することによって、実際には実行されていない場所を特定し、組織内のさまざまな品質のメディア品質を確認できるようにすることです。場所が異なります。</span><span class="sxs-lookup"><span data-stu-id="50e89-147">The goal of this report is to provide insight into the media quality of the bulk of your organization’s telephone calls for various locations so that you can identify poorly performing locations, and see the different grades of media quality in your organization’s different locations.</span></span>

<span data-ttu-id="50e89-148">レポートを表示すると、測定基準の異なるテーブルが表示されます。組織がレポートを決定する指標ごとに1つのテーブルが表示されます。</span><span class="sxs-lookup"><span data-stu-id="50e89-148">When displaying the report, different tables of metrics appear—one table for each metric your organization decides to report on.</span></span> <span data-ttu-id="50e89-149">このレポートには、次の指標を選択できます。</span><span class="sxs-lookup"><span data-stu-id="50e89-149">You can choose from the following metrics for this report:</span></span>

  - <span data-ttu-id="50e89-150">話し言葉平均意見スコア (MOS)</span><span class="sxs-lookup"><span data-stu-id="50e89-150">Conversational mean opinion score (MOS)</span></span>

  - <span data-ttu-id="50e89-151">ネットワーク MOS</span><span class="sxs-lookup"><span data-stu-id="50e89-151">Network MOS</span></span>

  - <span data-ttu-id="50e89-152">ネットワーク MOS の低下</span><span class="sxs-lookup"><span data-stu-id="50e89-152">Network MOS Degradation</span></span>

  - <span data-ttu-id="50e89-153">MOS の送信</span><span class="sxs-lookup"><span data-stu-id="50e89-153">Sending MOS</span></span>

  - <span data-ttu-id="50e89-154">リスニング MOS</span><span class="sxs-lookup"><span data-stu-id="50e89-154">Listening MOS</span></span>

  - <span data-ttu-id="50e89-155">パケット損失</span><span class="sxs-lookup"><span data-stu-id="50e89-155">Packet Loss</span></span>

  - <span data-ttu-id="50e89-156">ずれ</span><span class="sxs-lookup"><span data-stu-id="50e89-156">Jitter</span></span>

  - <span data-ttu-id="50e89-157">待機時間</span><span class="sxs-lookup"><span data-stu-id="50e89-157">Latency</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

