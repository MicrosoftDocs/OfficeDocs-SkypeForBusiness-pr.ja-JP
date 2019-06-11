---
title: 'Lync Server 2013: QoE レポート'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: QoE reports
ms:assetid: 49c827af-b8dd-4c6e-b0dc-b4bc6d60e9a3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720913(v=OCS.15)
ms:contentKeyID: 63969601
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 04960c43dc8e29c6e5af44a1d3109e40dd578479
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34823736"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="qoe-reports-in-lync-server-2013"></a><span data-ttu-id="dd111-102">Lync Server 2013 の QoE レポート</span><span class="sxs-lookup"><span data-stu-id="dd111-102">QoE reports in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="dd111-103">_**最終更新日:** 2014-05-01_</span><span class="sxs-lookup"><span data-stu-id="dd111-103">_**Topic Last Modified:** 2014-05-01_</span></span>

<div>

## <a name="qoe-summarytrend-reports"></a><span data-ttu-id="dd111-104">QoE サマリー/トレンドレポート</span><span class="sxs-lookup"><span data-stu-id="dd111-104">QoE summary/trend reports</span></span>

<span data-ttu-id="dd111-105">QoE サマリー/トレンドレポートは、組織のネットワークリソースが十分であることを確認するために、1日のピーク使用時間を見つけてメディアの品質を確認するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="dd111-105">The QoE summary/trends reports are useful for finding the peak usage times of day and examining the media quality during those times to help assure that your organization's network resources are sufficient.</span></span> <span data-ttu-id="dd111-106">組織では、レポートで利用可能な多くのフィルターを使用して、特定の場所、クライアントとデバイスの種類、サーバーのパフォーマンスの数値を特定することもできます。</span><span class="sxs-lookup"><span data-stu-id="dd111-106">Your organization can also use the many filters available in the report to isolate performance numbers for certain locations, client and device types, and servers.</span></span>

<span data-ttu-id="dd111-107">QoE サマリー/トレンドレポートは次の要素で構成されます。</span><span class="sxs-lookup"><span data-stu-id="dd111-107">QoE summary/trend reports consist of:</span></span>

  - <span data-ttu-id="dd111-108">UC 対多集計のサマリー/トレンドレポート</span><span class="sxs-lookup"><span data-stu-id="dd111-108">UC-to-UC Summary/Trend Report</span></span>

  - <span data-ttu-id="dd111-109">PSTN サマリー/トレンドレポート</span><span class="sxs-lookup"><span data-stu-id="dd111-109">PSTN Summary/Trend Report</span></span>

  - <span data-ttu-id="dd111-110">会議の概要/傾向レポート</span><span class="sxs-lookup"><span data-stu-id="dd111-110">Conference Summary/Trend Report</span></span>

</div>

<div>

## <a name="qoe-performance-reports"></a><span data-ttu-id="dd111-111">QoE のパフォーマンスレポート</span><span class="sxs-lookup"><span data-stu-id="dd111-111">QoE performance reports</span></span>

<span data-ttu-id="dd111-112">QoE パフォーマンスレポートには、仲介サーバー、A/V 会議サーバー、エンドポイントの場所の QoE パフォーマンスに焦点を当てた3つのレポートに関する詳細が用意されています。</span><span class="sxs-lookup"><span data-stu-id="dd111-112">QoE performance reports provide details about the three reports that concentrate on the QoE performance of Mediation Servers, A/V Conferencing Servers, and endpoint locations.</span></span>

</div>

<div>

## <a name="mediation-server-performance-report"></a><span data-ttu-id="dd111-113">仲介サーバーパフォーマンスレポート</span><span class="sxs-lookup"><span data-stu-id="dd111-113">Mediation server performance report</span></span>

<span data-ttu-id="dd111-114">仲介サーバーのパフォーマンスレポートには、指定した期間中に、1つ以上の仲介によって得られたメトリックが一覧表示されます。</span><span class="sxs-lookup"><span data-stu-id="dd111-114">The Mediation Server Performance report lists the metrics achieved by one or more Mediation during the specified time period.</span></span> <span data-ttu-id="dd111-115">ユニファイドコミュニケーション (UC) 対仲介サーバーの区間と、各通話の仲介サーバー間の区間のメトリックは、別々に報告されます。</span><span class="sxs-lookup"><span data-stu-id="dd111-115">The metrics for the unified communications (UC)-to-Mediation Server leg and the Mediation Server-to-Gateway leg of each call are reported separately.</span></span> <span data-ttu-id="dd111-116">このレポートを使用して、組織のさまざまな仲介サーバーのボリュームとパフォーマンスを比較します。</span><span class="sxs-lookup"><span data-stu-id="dd111-116">Use this report to compare the volume and performance of your organization's various Mediation Servers.</span></span>

<span data-ttu-id="dd111-117">各仲介サーバー (および各通話区間用) には、次のようなレポートが表示されます。</span><span class="sxs-lookup"><span data-stu-id="dd111-117">For each Mediation Server (and for each call leg), the report displays the following:</span></span>

  - <span data-ttu-id="dd111-118">通話の数</span><span class="sxs-lookup"><span data-stu-id="dd111-118">Number of calls</span></span>

  - <span data-ttu-id="dd111-119">パケット損失</span><span class="sxs-lookup"><span data-stu-id="dd111-119">Packet Loss</span></span>

  - <span data-ttu-id="dd111-120">ラウンドトリップ時間</span><span class="sxs-lookup"><span data-stu-id="dd111-120">Round Trip Time</span></span>

  - <span data-ttu-id="dd111-121">ジッター</span><span class="sxs-lookup"><span data-stu-id="dd111-121">Jitter</span></span>

  - <span data-ttu-id="dd111-122">話し言葉平均の意見 (MOS)</span><span class="sxs-lookup"><span data-stu-id="dd111-122">Conversational mean opinion score (MOS)</span></span>

  - <span data-ttu-id="dd111-123">MOS を送信中</span><span class="sxs-lookup"><span data-stu-id="dd111-123">Sending MOS</span></span>

  - <span data-ttu-id="dd111-124">聞き取り MOS</span><span class="sxs-lookup"><span data-stu-id="dd111-124">Listening MOS</span></span>

  - <span data-ttu-id="dd111-125">Network MOS</span><span class="sxs-lookup"><span data-stu-id="dd111-125">Network MOS</span></span>

  - <span data-ttu-id="dd111-126">ネットワーク MOS の低下</span><span class="sxs-lookup"><span data-stu-id="dd111-126">Network MOS Degradation</span></span>

  - <span data-ttu-id="dd111-127">エコーリターン</span><span class="sxs-lookup"><span data-stu-id="dd111-127">Echo Return</span></span>

  - <span data-ttu-id="dd111-128">シグナルレベル</span><span class="sxs-lookup"><span data-stu-id="dd111-128">Signal Level</span></span>

</div>

<div>

## <a name="av-conferencing-server-performance-report"></a><span data-ttu-id="dd111-129">A/V 会議サーバーパフォーマンスレポート</span><span class="sxs-lookup"><span data-stu-id="dd111-129">A/V conferencing server performance report</span></span>

<span data-ttu-id="dd111-130">A/V 会議サーバーパフォーマンスレポートでは、指定された期間中に1つ以上の A/V 会議サーバーによって達成された指標の一覧が表示されます。</span><span class="sxs-lookup"><span data-stu-id="dd111-130">The A/V Conferencing Server Performance report provides lists of metrics achieved by one or more A/V Conferencing Servers during the specified time period.</span></span> <span data-ttu-id="dd111-131">このレポートは、組織のさまざまな A/V 会議サーバーのボリュームとパフォーマンスを比較するために使用できます。</span><span class="sxs-lookup"><span data-stu-id="dd111-131">This report can be used to compare the volume and performance of your organization’s various A/V Conferencing Servers.</span></span> <span data-ttu-id="dd111-132">組織でレポートを分離して、Lync クライアントや PSTN クライアントなど、特定のクライアントの種類のエクスペリエンスのみを表示することもできます。</span><span class="sxs-lookup"><span data-stu-id="dd111-132">Your organization can also isolate the report to show only the experience for specific client types, such as Lync clients or PSTN clients.</span></span>

<span data-ttu-id="dd111-133">各 A/V 会議サーバーでは、レポートに次の内容が表示されます。</span><span class="sxs-lookup"><span data-stu-id="dd111-133">For each A/V Conferencing Server, the report displays the following:</span></span>

  - <span data-ttu-id="dd111-134">会議の数</span><span class="sxs-lookup"><span data-stu-id="dd111-134">Number of conferences</span></span>

  - <span data-ttu-id="dd111-135">パケット損失</span><span class="sxs-lookup"><span data-stu-id="dd111-135">Packet Loss</span></span>

  - <span data-ttu-id="dd111-136">ラウンドトリップ時間</span><span class="sxs-lookup"><span data-stu-id="dd111-136">Round Trip Time</span></span>

  - <span data-ttu-id="dd111-137">ジッター</span><span class="sxs-lookup"><span data-stu-id="dd111-137">Jitter</span></span>

  - <span data-ttu-id="dd111-138">話し言葉平均の意見 (MOS)</span><span class="sxs-lookup"><span data-stu-id="dd111-138">Conversational mean opinion score (MOS)</span></span>

  - <span data-ttu-id="dd111-139">MOS を送信中</span><span class="sxs-lookup"><span data-stu-id="dd111-139">Sending MOS</span></span>

  - <span data-ttu-id="dd111-140">聞き取り MOS</span><span class="sxs-lookup"><span data-stu-id="dd111-140">Listening MOS</span></span>

  - <span data-ttu-id="dd111-141">Network MOS</span><span class="sxs-lookup"><span data-stu-id="dd111-141">Network MOS</span></span>

  - <span data-ttu-id="dd111-142">ネットワーク MOS の低下</span><span class="sxs-lookup"><span data-stu-id="dd111-142">Network MOS Degradation</span></span>

  - <span data-ttu-id="dd111-143">エコーリターン</span><span class="sxs-lookup"><span data-stu-id="dd111-143">Echo Return</span></span>

  - <span data-ttu-id="dd111-144">シグナルレベル</span><span class="sxs-lookup"><span data-stu-id="dd111-144">Signal Level</span></span>

</div>

<div>

## <a name="location-based-performance-report"></a><span data-ttu-id="dd111-145">位置ベースのパフォーマンスレポート</span><span class="sxs-lookup"><span data-stu-id="dd111-145">Location-based performance report</span></span>

<span data-ttu-id="dd111-146">位置ベースのパフォーマンスレポートでは、ネットワーク上の場所の一覧が表示され、各場所には、事前に決定された各品質の範囲の通話数が示されます。</span><span class="sxs-lookup"><span data-stu-id="dd111-146">The Location-Based Performance report provides a list of network locations and for each location shows the number of calls in each pre-determined range of quality.</span></span> <span data-ttu-id="dd111-147">このレポートの目的は、さまざまな場所についての組織の電話による通話の質を把握して、組織内で実行されている場所を特定し、さまざまな種類のメディアの品質を確認できるようにすることです。異なる場所。</span><span class="sxs-lookup"><span data-stu-id="dd111-147">The goal of this report is to provide insight into the media quality of the bulk of your organization’s telephone calls for various locations so that you can identify poorly performing locations, and see the different grades of media quality in your organization’s different locations.</span></span>

<span data-ttu-id="dd111-148">レポートを表示すると、さまざまなメトリックのテーブルが表示されます。組織がレポートを決定する各指標ごとに1つのテーブルが表示されます。</span><span class="sxs-lookup"><span data-stu-id="dd111-148">When displaying the report, different tables of metrics appear—one table for each metric your organization decides to report on.</span></span> <span data-ttu-id="dd111-149">このレポートには、次のメトリックから選ぶことができます。</span><span class="sxs-lookup"><span data-stu-id="dd111-149">You can choose from the following metrics for this report:</span></span>

  - <span data-ttu-id="dd111-150">話し言葉平均の意見 (MOS)</span><span class="sxs-lookup"><span data-stu-id="dd111-150">Conversational mean opinion score (MOS)</span></span>

  - <span data-ttu-id="dd111-151">Network MOS</span><span class="sxs-lookup"><span data-stu-id="dd111-151">Network MOS</span></span>

  - <span data-ttu-id="dd111-152">ネットワーク MOS の低下</span><span class="sxs-lookup"><span data-stu-id="dd111-152">Network MOS Degradation</span></span>

  - <span data-ttu-id="dd111-153">MOS を送信中</span><span class="sxs-lookup"><span data-stu-id="dd111-153">Sending MOS</span></span>

  - <span data-ttu-id="dd111-154">聞き取り MOS</span><span class="sxs-lookup"><span data-stu-id="dd111-154">Listening MOS</span></span>

  - <span data-ttu-id="dd111-155">パケット損失</span><span class="sxs-lookup"><span data-stu-id="dd111-155">Packet Loss</span></span>

  - <span data-ttu-id="dd111-156">ジッター</span><span class="sxs-lookup"><span data-stu-id="dd111-156">Jitter</span></span>

  - <span data-ttu-id="dd111-157">間隔</span><span class="sxs-lookup"><span data-stu-id="dd111-157">Latency</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

