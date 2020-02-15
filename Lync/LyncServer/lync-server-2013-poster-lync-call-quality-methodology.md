---
title: 'Lync Server 2013: ポスター: Lync 通話品質の方法論'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: 'Poster: Lync Call Quality Methodology'
ms:assetid: a069f4e5-4f80-4f0f-8657-2e07276b6b41
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn593600(v=OCS.15)
ms:contentKeyID: 61084874
ms.date: 06/24/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 849e74fb4857dd7b3ab98b8a8efd9c3ce3781e35
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2020
ms.locfileid: "42043039"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="lync-call-quality-methodology-in-lync-server-2013"></a><span data-ttu-id="33251-102">Lync Server 2013 の lync 通話品質の方法論</span><span class="sxs-lookup"><span data-stu-id="33251-102">Lync Call Quality Methodology in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="33251-103">_**トピックの最終更新日:** 2016-06-24_</span><span class="sxs-lookup"><span data-stu-id="33251-103">_**Topic Last Modified:** 2016-06-24_</span></span>

<span data-ttu-id="33251-104">この記事は、 [Lync 通話品質の方法](http://go.microsoft.com/fwlink/?linkid=391841)のポスターに関連しており、ダウンロードセンターからダウンロードできます。</span><span class="sxs-lookup"><span data-stu-id="33251-104">This article is a companion to the [Lync Call Quality Methodology](http://go.microsoft.com/fwlink/?linkid=391841) poster, which you can download from the Download Center.</span></span>

<span data-ttu-id="33251-105">![CQM プロセスを説明するポスター](images/Dn594589.d239e04a-1c3b-4f0e-93af-88b85198615a(OCS.15).jpg "CQM プロセスを説明するポスター")</span><span class="sxs-lookup"><span data-stu-id="33251-105">![Poster describing the CQM process](images/Dn594589.d239e04a-1c3b-4f0e-93af-88b85198615a(OCS.15).jpg "Poster describing the CQM process")</span></span>

<span data-ttu-id="33251-106">このポスターを使用して、エンタープライズ voip 機能を含む Lync 実装の通話品質やユーザーの利便性に影響する問題を見つけて除去するのに役立つ、CQM、Lync 2013 および2010の通話品質の方法論について学ぶことができます。</span><span class="sxs-lookup"><span data-stu-id="33251-106">You can use this poster to learn about CQM, the Call Quality Methodology for Lync 2013 and 2010 that helps you find and eliminate issues affecting call quality and user experience for Lync implementations that include enterprise voice features.</span></span> <span data-ttu-id="33251-107">通話品質の方法論は新しいトラブルシューティングおよびサービス管理フレームワークであり、Lync でエンタープライズ voip サービスを向上させるための効果的な取り組みを可能にします。</span><span class="sxs-lookup"><span data-stu-id="33251-107">Call Quality Methodology is a new troubleshooting and service management framework that can better focus efforts to improve enterprise voice services in Lync.</span></span> <span data-ttu-id="33251-108">この記事では、CQM の詳細、監視対象のサーバーとソリューションの種類、収集したテレメトリデータの処理方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="33251-108">In this article, you can learn more about CQM, the kinds of servers and solutions that are monitored, and what to do with the collected telemetry data.</span></span>

<span data-ttu-id="33251-109">CQM の使用方法について質問がある場合は、cqmfeedback@microsoft.com に質問を送信できます。</span><span class="sxs-lookup"><span data-stu-id="33251-109">If you have questions about how to use CQM, you can submit your questions to cqmfeedback@microsoft.com.</span></span>

<span data-ttu-id="33251-110">ポスターは、以下の領域について説明します。</span><span class="sxs-lookup"><span data-stu-id="33251-110">The poster explains the following areas:</span></span>

  - <span data-ttu-id="33251-111">Lync CQM とは</span><span class="sxs-lookup"><span data-stu-id="33251-111">What is Lync CQM?</span></span>

  - <span data-ttu-id="33251-112">優先度の設定: トレンド分析クエリを実行する</span><span class="sxs-lookup"><span data-stu-id="33251-112">Prioritize: Run Trending Queries</span></span>

  - <span data-ttu-id="33251-113">PCD</span><span class="sxs-lookup"><span data-stu-id="33251-113">PCD</span></span>

  - <span data-ttu-id="33251-114">管理/非管理</span><span class="sxs-lookup"><span data-stu-id="33251-114">Managed/Unmanaged</span></span>

  - <span data-ttu-id="33251-115">サーバー工場の道路</span><span class="sxs-lookup"><span data-stu-id="33251-115">The Server Plant Road</span></span>

  - <span data-ttu-id="33251-116">最後のマイルの道</span><span class="sxs-lookup"><span data-stu-id="33251-116">The Last Mile Road</span></span>

  - <span data-ttu-id="33251-117">エンドポイントの道路</span><span class="sxs-lookup"><span data-stu-id="33251-117">The End Points Road</span></span>

  - <span data-ttu-id="33251-118">サービス管理</span><span class="sxs-lookup"><span data-stu-id="33251-118">Service Management</span></span>

  - <span data-ttu-id="33251-119">ボードゲームのルール</span><span class="sxs-lookup"><span data-stu-id="33251-119">Board Game Rules</span></span>

<span id="WhatIs"></span>

<div>

## <a name="what-is-lync-cqm"></a><span data-ttu-id="33251-120">Lync CQM とは</span><span class="sxs-lookup"><span data-stu-id="33251-120">What is Lync CQM?</span></span>

<span data-ttu-id="33251-121">通話品質の方法論は新しいトラブルシューティングおよびサービス管理フレームワークであり、Lync でエンタープライズ voip サービスを向上させるための効果的な取り組みを可能にします。</span><span class="sxs-lookup"><span data-stu-id="33251-121">Call Quality Methodology is a new troubleshooting and service management framework that can better focus efforts to improve enterprise voice services in Lync.</span></span> <span data-ttu-id="33251-122">CQM を使用する場合は、エンタープライズ voip サービスの通話品質とユーザー満足度を保証するために必要な労力が少なくなります。</span><span class="sxs-lookup"><span data-stu-id="33251-122">When you use CQM, less effort is needed to assure call quality and user satisfaction for enterprise voice services.</span></span> <span data-ttu-id="33251-123">CQM の詳細については、[通話品質の方法論](http://go.microsoft.com/fwlink/p/?linkid=615208)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="33251-123">CQM is more fully explained in the [Call Quality Methodology](http://go.microsoft.com/fwlink/p/?linkid=615208).</span></span> <span data-ttu-id="33251-124">この記事とポスターには、そのコンテンツの概要が記載されています。</span><span class="sxs-lookup"><span data-stu-id="33251-124">This article and the poster are summaries of that content.</span></span>

<span data-ttu-id="33251-125">CQM は、システムのトラブルシューティングを3つのパスまたは「道路」に分割します。</span><span class="sxs-lookup"><span data-stu-id="33251-125">CQM breaks down System troubleshooting into three paths or “Roads.”</span></span> <span data-ttu-id="33251-126">これらの機能は、サーバーとそれらの間のリンク、および通話に使用されるユーザーデバイスとメディアを示すエンドポイントの道路、および従来のスイッチ電話網呼び出しの統合に対応する最後のマイルの道を見ることができます。</span><span class="sxs-lookup"><span data-stu-id="33251-126">These are: the Server Plant Road, which looks at the servers and the links between them, the End Points Road, which looks at user devices and media used to carry calls, and the Last Mile Road, which addresses integration of traditional switched telephone network calls.</span></span>

<span data-ttu-id="33251-127">各道路は特定のエリアまたはトピックに関連するいくつかのセグメントに分かれており、各セグメント定義では、許容できる品質レベルについての説明、その品質レベルを達成するためのアクション、およびサービス管理計画を実施するための準備が整っています。その品質レベルは、次のトピックに進む前に行います。</span><span class="sxs-lookup"><span data-stu-id="33251-127">Each Road is divided into several segments relating to a specific area or topic, and at each segment definitions are made about what is an acceptable quality level, actions are taken to achieve that quality level, and a service management plan is put in place to maintain that quality level before moving on to the next topic.</span></span>

<span data-ttu-id="33251-128">このポスターでは、3人のプレーヤーのボードゲームとして Lync CQM が提供されており、各ユーザーはいずれかの道路を通過します。</span><span class="sxs-lookup"><span data-stu-id="33251-128">The poster presents Lync CQM as a board game for three players, each of whom will go through one of the roads.</span></span> <span data-ttu-id="33251-129">ダウンロードに含まれているカードは、克服する必要がある通話品質への障害をシミュレートするために使用されます。</span><span class="sxs-lookup"><span data-stu-id="33251-129">Cards included with the download are used to simulate impediments to call quality that must be overcome.</span></span> <span data-ttu-id="33251-130">ターゲットに関するヒントと提案、およびそれらを実現する方法が3つのパスに含まれており、実際のアプリケーションで最初に追求する道路に関する優先度設定ガイドライン (ゲームでは、3つすべての道路が並行して処理されます)。</span><span class="sxs-lookup"><span data-stu-id="33251-130">Hints and suggestions about targets and how to achieve them are included along the three paths, as well as prioritization guidelines for which road to pursue first in actual applications (in the game, all three roads are addressed in parallel).</span></span>

<span data-ttu-id="33251-131">以前のバージョンの Lync で CQM はどのように動作しますか?</span><span class="sxs-lookup"><span data-stu-id="33251-131">How does CQM work in earlier versions of Lync?</span></span> <span data-ttu-id="33251-132">Lync 2013 では CQM は新しく追加されましたが、ほとんどは Lync 2010 で使用することができます。</span><span class="sxs-lookup"><span data-stu-id="33251-132">CQM is new for Lync 2013, but most of it can be adapted to be used with Lync 2010.</span></span> <span data-ttu-id="33251-133">CQM は、Microsoft Office Communicator を使用した程度の機能を持つ場合がありますが、これはテストされておらず、サポートされていません。</span><span class="sxs-lookup"><span data-stu-id="33251-133">CQM may work to a degree with Microsoft Office Communicator, but this is untested and not supported.</span></span>

<span data-ttu-id="33251-134">CQM の使用方法について質問がある場合は、cqmfeedback@microsoft.com に質問を送信できます。</span><span class="sxs-lookup"><span data-stu-id="33251-134">If you have questions about how to use CQM, you can submit your questions to cqmfeedback@microsoft.com.</span></span>

</div>

<span id="Trending"></span>

<div>

## <a name="prioritize-run-trending-queries"></a><span data-ttu-id="33251-135">優先度の設定: トレンド分析クエリを実行する</span><span class="sxs-lookup"><span data-stu-id="33251-135">Prioritize: Run Trending Queries</span></span>

<span data-ttu-id="33251-136">CQM の最初の手順は、2週間の傾向分析クエリをそれぞれ実行し、結果を分析することです。</span><span class="sxs-lookup"><span data-stu-id="33251-136">The first step in CQM is to run each of the trending queries for two weeks and then analyze the results.</span></span> <span data-ttu-id="33251-137">最大のストリームコントリビューター、最も低いストリームの比率、および管理対象領域 (自分が管理する) によって、是正措置を優先順位付けします。</span><span class="sxs-lookup"><span data-stu-id="33251-137">Prioritize corrective action by the largest stream contributor, the highest poor stream ratio, and managed areas (ones you control).</span></span><span data-ttu-id="33251-138">音声ビデオマルチポイントコントロールユニット (AV MCU) または仲介クエリが不適切な結果を示している場合は、赤またはサーバーの工場の道路で開始します。</span><span class="sxs-lookup"><span data-stu-id="33251-138">  If the Audio/Video Multi-point Control Unit (AV MCU) or Mediation queries show poor results, start on the Red or Server Plant road.</span></span><span data-ttu-id="33251-139">ワイヤードまたはワイヤレスクエリの結果の表示が不十分な場合は、青または最終マイルの道路で開始します。</span><span class="sxs-lookup"><span data-stu-id="33251-139">  If the Wired or Wireless queries show poor results, start on the Blue or Last Mile road.</span></span><span data-ttu-id="33251-140">VPN または外部クエリの結果の表示が不十分な場合は、緑または端点の道路を開始します。</span><span class="sxs-lookup"><span data-stu-id="33251-140">  If the VPN or External queries show poor results, start on the Green or End Points road.</span></span>

<span data-ttu-id="33251-141">開始する道路を選択した後、各領域 (アサート) のターゲットを定義し、その対象を満たし (達成)、目標を達成するための手順を実装 (保持) します。</span><span class="sxs-lookup"><span data-stu-id="33251-141">After you choose a road to start with, define a target for each area (Assert), work to meet that target (Achieve) and then implement procedures to stay on target (Maintain).</span></span> <span data-ttu-id="33251-142">このポスターをゲームとして使用して、CQM の背後にある原則を理解することもできます。</span><span class="sxs-lookup"><span data-stu-id="33251-142">You can also use this poster as a game to understand the principles behind CQM.</span></span>

</div>

<span id="PCD"></span>

<div>

## <a name="pcd"></a><span data-ttu-id="33251-143">PCD</span><span class="sxs-lookup"><span data-stu-id="33251-143">PCD</span></span>

<span data-ttu-id="33251-144">PreCall Diagnostics tool (PCD) は、境界ネットワークの問題を特定して診断するのに役立ちます (QoE データベースは、エッジまたは周辺ネットワーク上の情報を収集しません)。また、最後のマイルの接続のトラブルシューティングも行います。</span><span class="sxs-lookup"><span data-stu-id="33251-144">The PreCall Diagnostics tool (PCD) will help you identify and diagnose problems in your perimeter network (the QoE database doesn’t collect information on your edge or perimeter network) and also to troubleshoot connections in the Last Mile.</span></span> <span data-ttu-id="33251-145">このツールは、Windows 8 モダンアプリと Windows デスクトップアプリの両方でhttp://apps.microsoft.com/windows/en-us/app/lync-2013-precall-diagnostics/9607fe33-2b51-403d-9615-c23f248e7c88使用できます。</span><span class="sxs-lookup"><span data-stu-id="33251-145">The tool is available as both a Windows 8 Modern App or a Windows Desktop App at http://apps.microsoft.com/windows/en-us/app/lync-2013-precall-diagnostics/9607fe33-2b51-403d-9615-c23f248e7c88.</span></span>

</div>

<span id="ManagedUn"></span>

<div>

## <a name="managedunmanaged"></a><span data-ttu-id="33251-146">管理/非管理</span><span class="sxs-lookup"><span data-stu-id="33251-146">Managed/Unmanaged</span></span>

<span data-ttu-id="33251-147">Lync Server の展開とネットワークインフラストラクチャは、通常、管理スペースとアンマネージ空間に分けることができます。</span><span class="sxs-lookup"><span data-stu-id="33251-147">The Lync Server deployment and network infrastructure can usually be divided into managed and unmanaged spaces.</span></span> <span data-ttu-id="33251-148">管理スペースには、有線ネットワークとサーバーインフラストラクチャ全体が含まれています。</span><span class="sxs-lookup"><span data-stu-id="33251-148">The managed space includes your entire inside wired network and server infrastructure.</span></span> <span data-ttu-id="33251-149">この管理されていない領域は、ワイヤレスインフラストラクチャと外部ネットワークインフラストラクチャです。</span><span class="sxs-lookup"><span data-stu-id="33251-149">The unmanaged space is the wireless infrastructure and the outside network infrastructure.</span></span>

<span data-ttu-id="33251-150">この区別により、データがより明確になり、ユーザーの音声とビデオの品質に大きな影響を与えるワークロードを組織が重視できるようになります。</span><span class="sxs-lookup"><span data-stu-id="33251-150">Making this distinction increases the clarity of your data and helps your organization focus on workloads that will have a measurable impact on your users’ voice and video quality.</span></span> <span data-ttu-id="33251-151">自分が所有する (管理された) インフラストラクチャと、他のエンティティ (非管理対象) の制御下にあるインフラストラクチャの下にあるインフラストラクチャに通話が配置されている場合は、ユーザーの品質が異なることが予想されます。</span><span class="sxs-lookup"><span data-stu-id="33251-151">Users have a different expectation of quality if the call is placed on infrastructure that you own (managed) versus infrastructure that is partly under the control of some other entity (unmanaged).</span></span> <span data-ttu-id="33251-152">これは、ワイヤレスユーザーが自分のデバイスに優れた Lync Server エクスペリエンスを備えているということではありません。</span><span class="sxs-lookup"><span data-stu-id="33251-152">This is not to say that wireless users are left to their own devices to have excellent Lync Server experiences.</span></span>

<span data-ttu-id="33251-153">管理されていないスペースで音声品質を向上させるには、管理領域に高品質を持たせる必要があります。</span><span class="sxs-lookup"><span data-stu-id="33251-153">Improving voice quality in the unmanaged space requires you to have high quality in the managed space.</span></span> <span data-ttu-id="33251-154">ワイヤレス (Wi-fi) が管理されていると見なされるか、または管理されていないスペースが組織になるか。</span><span class="sxs-lookup"><span data-stu-id="33251-154">Whether wireless (Wi-Fi) is considered managed or unmanaged space is up to your organization.</span></span> <span data-ttu-id="33251-155">正常な環境を実現する手法は、ソリューションと同じように2つのスペースで異なります。</span><span class="sxs-lookup"><span data-stu-id="33251-155">The techniques to achieve a healthy environment are different in the two spaces, as are the solutions.</span></span>

</div>

<span id="ServRd"></span>

<div>

## <a name="the-server-plant-road"></a><span data-ttu-id="33251-156">サーバー工場の道路</span><span class="sxs-lookup"><span data-stu-id="33251-156">The Server Plant Road</span></span>

<span data-ttu-id="33251-157">サーバー工場のロードのセグメント1は、Lync 実装の実際のサーバーに対応しています。</span><span class="sxs-lookup"><span data-stu-id="33251-157">Segment 1 of the Server Plant Road addresses the actual servers in the Lync implementation.</span></span> <span data-ttu-id="33251-158">実装でサーバー自体とその役割の両方に関する KHI データを収集し、結果を分析します。</span><span class="sxs-lookup"><span data-stu-id="33251-158">Gather KHI data regarding both the server itself and its role in the implementation and analyze the result.</span></span> <span data-ttu-id="33251-159">アクションが保証されている場合は、検出された問題を修正します。</span><span class="sxs-lookup"><span data-stu-id="33251-159">If action is warranted, correct any problems found.</span></span> <span data-ttu-id="33251-160">このトピックの詳細については、KHI ポスターに付属の「 [Lync Server 2013 の主要な正常性インジケーター](lync-server-2013-poster-key-health-indicators.md)について」の記事を参照してください。</span><span class="sxs-lookup"><span data-stu-id="33251-160">More detail on this topic is presented in the article about [Key Health Indicators in Lync Server 2013](lync-server-2013-poster-key-health-indicators.md) that accompanies the KHI poster.</span></span>

<span data-ttu-id="33251-161">次のセグメントは、AV MCU サーバーと仲介サーバーの間のメディアストリームを解決します。</span><span class="sxs-lookup"><span data-stu-id="33251-161">The next segment addresses media streams between the AV MCU server and mediation server.</span></span> <span data-ttu-id="33251-162">まず、不適切なストリームしきい値の目標を決定します。</span><span class="sxs-lookup"><span data-stu-id="33251-162">Begin by determining your targets for poor stream thresholds.</span></span> <span data-ttu-id="33251-163">不適切なストリームは、 \>通常 PacketLossRate .01 \>または PacketLossRateMax です。</span><span class="sxs-lookup"><span data-stu-id="33251-163">Poor streams are usually PacketLossRate \> .01 or PacketLossRateMax \> .05.</span></span> <span data-ttu-id="33251-164">もう1つの望ましい\<目標は PoorStreamsRatio 2% です。</span><span class="sxs-lookup"><span data-stu-id="33251-164">Another desirable target is PoorStreamsRatio \< 2%.</span></span> <span data-ttu-id="33251-165">次に、詳細なクエリを使用して、不十分なストリームでの AVMCU と仲介サーバーのペアの検索、不適切なストリームパスのネットワーク機器の参照、不足しているストリームの修復、および最適化されたネットワークまたは "ゴールド" 構成の定義を行います。輸送.</span><span class="sxs-lookup"><span data-stu-id="33251-165">Next, use detailed queries to find AVMCU and Mediation server pairs with poor streams, investigate the cause of poor streams, look at network equipment in the poor stream paths, remediate poor streams, and define optimal or “gold” configuration for network equipment.</span></span> <span data-ttu-id="33251-166">アチーブメントを維持するには、構成のドリフトを管理するためのプロセスとツールを実装し、新しい問題領域を報告します。</span><span class="sxs-lookup"><span data-stu-id="33251-166">To maintain your achievement, implement processes and tools to manage configuration drift and to report new problem areas.</span></span>

<span data-ttu-id="33251-167">次に、仲介サーバーと公衆交換電話網 (PSTN) ゲートウェイ間のメディアストリームを調べます。</span><span class="sxs-lookup"><span data-stu-id="33251-167">Next, examine the media streams between the Mediation server and the Public Switched Telephone Network (PSTN) gateway.</span></span> <span data-ttu-id="33251-168">まず、不適切なストリームしきい値の目標を決定します。</span><span class="sxs-lookup"><span data-stu-id="33251-168">Begin by determining your targets for poor stream thresholds.</span></span> <span data-ttu-id="33251-169">不適切なストリームは、 \>通常 PacketLossRate .01 \>または PacketLossRateMax です。</span><span class="sxs-lookup"><span data-stu-id="33251-169">Poor streams are usually PacketLossRate \> .01 or PacketLossRateMax \> .05.</span></span> <span data-ttu-id="33251-170">もう1つの望ましい\<目標は PoorStreamsRatio 2% です。</span><span class="sxs-lookup"><span data-stu-id="33251-170">Another desirable target is PoorStreamsRatio \< 2%.</span></span> <span data-ttu-id="33251-171">次に、詳細なクエリを使用して、ストリームが不足している仲介サーバーとゲートウェイのペアを検索し、ストリームが不足している原因を調べ、不足しているストリームのパスでネットワーク機器を調べ、不適切なストリームを修復し、最適化されたネットワークまたは "ゴールド" 構成を定義します。輸送.</span><span class="sxs-lookup"><span data-stu-id="33251-171">Next, use detailed queries to find Mediation server and gateway pairs with poor streams, investigate the cause of poor streams, look at network equipment in the poor stream paths, remediate poor streams, and define optimal or “gold” configuration for network equipment.</span></span> <span data-ttu-id="33251-172">アチーブメントを維持するには、構成のドリフトを管理するためのプロセスとツールを実装し、新しい問題領域を報告します。</span><span class="sxs-lookup"><span data-stu-id="33251-172">To maintain your achievement, implement processes and tools to manage configuration drift and to report new problem areas.</span></span>

<span data-ttu-id="33251-173">最後に、PSTN ゲートウェイの正常性測定基準を調べます。</span><span class="sxs-lookup"><span data-stu-id="33251-173">Finally, examine the health metrics for your PSTN gateway.</span></span> <span data-ttu-id="33251-174">状態を表示する統計情報を特定し、それらに対するターゲットを定義します。</span><span class="sxs-lookup"><span data-stu-id="33251-174">Identify the statistics that show health and define targets against them.</span></span> <span data-ttu-id="33251-175">使用可能なゲートウェイの数によっては、特定のガイダンスは提供されていません。</span><span class="sxs-lookup"><span data-stu-id="33251-175">No specific guidance is provided here as many possible gateways can be used.</span></span> <span data-ttu-id="33251-176">ターゲットが確立されたら、目標を達成するために必要に応じて修復します。このプロセスでは、ゲートウェイの "ゴールド" または最適な構成を定義することがよくあります。</span><span class="sxs-lookup"><span data-stu-id="33251-176">Once targets are established, remediate as needed to achieve the target; in the process you will likely define a “gold” or optimal configuration for the gateway.</span></span> <span data-ttu-id="33251-177">アチーブメントを維持するには、構成のドリフトを管理するためのプロセスとツールを実装し、新しい問題領域を報告します。</span><span class="sxs-lookup"><span data-stu-id="33251-177">To maintain your achievement, implement processes and tools to manage configuration drift and to report new problem areas.</span></span> <span data-ttu-id="33251-178">ファームウェアおよびソフトウェア更新プログラムによって構成が変更される可能性があることに注意してください。また、"ゴールド" 構成の定義を変更するため、これらの操作には注意が必要です。</span><span class="sxs-lookup"><span data-stu-id="33251-178">Be aware that firmware and software updates may alter your configuration or lead you to change the definition of the “gold” configuration, so approach these activities with care.</span></span>

</div>

<span id="LastMi"></span>

<div>

## <a name="the-last-mile-road"></a><span data-ttu-id="33251-179">最後のマイルの道</span><span class="sxs-lookup"><span data-stu-id="33251-179">The Last Mile Road</span></span>

<span data-ttu-id="33251-180">クライアントがネットワークに接続する2つの方法のうち、有線は最高の品質を提供することが期待されています。これは、最終マイルの問題に対する最初のフォーカスでなければなりません。</span><span class="sxs-lookup"><span data-stu-id="33251-180">Of the two ways clients connect to the network, wired is expected to deliver the highest quality and correspondingly this must be your initial focus for last mile issues.</span></span> <span data-ttu-id="33251-181">Cqm ワイヤードクエリ (lastmile\_0\_ワイヤード) と、それが提供する不十分なストリーム比率データを使用します。</span><span class="sxs-lookup"><span data-stu-id="33251-181">Use the CQM Wired query (LastMile\_0\_Wired) and the Poor Streams ratio data it provides.</span></span> <span data-ttu-id="33251-182">300ストリームの\>サイトには\< 、ターゲット PoorStreamsRatio 5% を定義することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="33251-182">We suggest defining a target PoorStreamsRatio \< 5% for sites with \> 300 streams).</span></span> <span data-ttu-id="33251-183">目標を達成するには、最低から最高の順にサブネットを修復し、QoS を実装します。</span><span class="sxs-lookup"><span data-stu-id="33251-183">To achieve your targets, remediate subnets ordered from worst to best, and implement QoS.</span></span>

<span data-ttu-id="33251-184">ワイヤード接続の品質を最適化すると、ワイヤレスインフラストラクチャは各場所でワイヤードコアの上に置かれるため、ワイヤレスの品質が向上します。</span><span class="sxs-lookup"><span data-stu-id="33251-184">After you optimize the quality of your wired connections, improving wireless quality becomes easier because the wireless infrastructure sits atop the wired core at each location.</span></span> <span data-ttu-id="33251-185">適切なワイヤード品質を備えたサイト内の不適切なワイヤレスストリームは、特定のワイヤレスコンポーネントの属性にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="33251-185">Poor wireless streams in a site with good wired quality must be attributed to the specific wireless components.</span></span> <span data-ttu-id="33251-186">CQM ワイヤレスクエリ (LastMile\_1\_ワイヤレス) は、日付範囲に対して実行され、お客様の環境内のすべての内部ワイヤレスストリームを、Lync クライアントから、または会議サーバーまたは仲介サーバーのいずれかとして返します。</span><span class="sxs-lookup"><span data-stu-id="33251-186">The CQM Wireless query (LastMile\_1\_Wireless) operates on a date range and will return all internal wireless streams in your environment from Lync clients to or from either conferencing servers or mediation servers.</span></span> <span data-ttu-id="33251-187">300ストリームの\>サイトには\< 、ターゲット PoorStreamsRatio 5% を定義することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="33251-187">We suggest defining a target PoorStreamsRatio \< 5% for sites with \> 300 streams).</span></span> <span data-ttu-id="33251-188">目標を達成するには、最低から最高の順にサブネットを修復し、QoS を実装します。</span><span class="sxs-lookup"><span data-stu-id="33251-188">To achieve your targets, remediate subnets ordered from worst to best, and implement QoS.</span></span>

</div>

<span id="EndPt"></span>

<div>

## <a name="the-end-points-road"></a><span data-ttu-id="33251-189">エンドポイントの道路</span><span class="sxs-lookup"><span data-stu-id="33251-189">The End Points Road</span></span>

<span data-ttu-id="33251-190">Lync で使用する場合に、ヘッドセットとその他のデバイスを使用して、適切な品質が得られることがわかっている状態で、エンドポイントへの照会を開始します。</span><span class="sxs-lookup"><span data-stu-id="33251-190">Begin inquiries into the End Points Road with the headsets and other devices known to produce acceptable quality when used with Lync.</span></span> <span data-ttu-id="33251-191">3.6 を100超えるストリームを\>実装する場合は、ターゲットの AvgSendListen MOS にお勧めします。)問題のあるデバイスを特定し、修正または置換することによって、目標を達成します。</span><span class="sxs-lookup"><span data-stu-id="33251-191">We suggest a target AvgSendListen MOS \> 3.6 for implementations with over 100 streams.) Achieve the target by identifying problematic devices and fix or replace them.</span></span>

<span data-ttu-id="33251-192">次に、エンドユーザーの呼び出しで音声を処理するデバイスまたは PC を調べます。</span><span class="sxs-lookup"><span data-stu-id="33251-192">Next, examine the device or PC processing the audio for end user calls.</span></span> <span data-ttu-id="33251-193">提案されるターゲット品質指標は、 \<AudioMicGlitchRate = 1 です。</span><span class="sxs-lookup"><span data-stu-id="33251-193">A suggested target quality metric is an AudioMicGlitchRate \<= 1.</span></span> <span data-ttu-id="33251-194">ユーザーシステムに最適なシステム構成を特定するときには、ドライバーバージョンを含む「ゴールデン」 PC 構成を定義します。</span><span class="sxs-lookup"><span data-stu-id="33251-194">As you identify optimal system configurations for the user systems, define a “golden” PC configuration including driver versions.</span></span>

<span data-ttu-id="33251-195">ここで、オーディオストリームが Lync エンドポイントシステムから受け取るネットワークパスを調べます。これにより、音質が低下する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="33251-195">Now examine the network path an audio stream takes from a Lync endpoint system, which can cause poor audio quality.</span></span> <span data-ttu-id="33251-196">VPN 接続を介してオーディオを転送する場合は、待機時間の問題が発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="33251-196">If audio travels over a VPN connection you might see latency issues.</span></span> <span data-ttu-id="33251-197">内部の Lync クライアントが、2者またはピアツーピア通話のために別の内部 Lync クライアントに直接メディアストリームを確立できない場合は、Lync エッジサーバーを介して中継するパスに戻され、待機時間の問題に加えて、さらに遅延が発生する可能性があります。損失とジッター。</span><span class="sxs-lookup"><span data-stu-id="33251-197">If an internal Lync client cannot establish a direct media stream to another internal Lync client for a two-party or peer-to-peer call, it will fall back to a path that relays through a Lync Edge server, again leading to latency issues as well as increased potential for loss and jitter.</span></span> <span data-ttu-id="33251-198">VPN に対して0% のメディアの品質指標を定義することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="33251-198">We suggest you define a quality metric of 0% Media over VPN.</span></span> <span data-ttu-id="33251-199">設定した目標を達成するために修復する際には、問題のサブネットを特定し、ファイアウォールルール、パケットコントローラー、およびその他の関連するネットワーク機器構成を調査します。</span><span class="sxs-lookup"><span data-stu-id="33251-199">As you remediate to achieve the target you set, identify problem subnets and investigate firewall rules, packet shapers, and other relevant network equipment configuration.</span></span>

<span data-ttu-id="33251-200">IP パケットは、伝送制御プロトコル (TCP) またはユーザーデータグラムプロトコル (UDP) のどちらかを使用できます。</span><span class="sxs-lookup"><span data-stu-id="33251-200">IP Packets can use either Transmission Control Protocol (TCP) or User Datagram Protocol (UDP).</span></span> <span data-ttu-id="33251-201">TCP はデータストリームに最適です。</span><span class="sxs-lookup"><span data-stu-id="33251-201">TCP is optimal for data streams.</span></span> <span data-ttu-id="33251-202">UDP はコネクションレス型であり、TCP 復旧メカニズムがリアルタイムメディアで損失を解決できないため、メディアの方が効率的です。</span><span class="sxs-lookup"><span data-stu-id="33251-202">UDP is connectionless and is more efficient for media since TCP recovery mechanisms cannot address loss in real time media.</span></span> <span data-ttu-id="33251-203">Lync では常に UDP が推奨されますが、UDP セッションを確立できない場合は TCP に戻ります。</span><span class="sxs-lookup"><span data-stu-id="33251-203">Lync always prefers UDP, but will revert to TCP if a UDP session cannot be established.</span></span> <span data-ttu-id="33251-204">TCP 経由のメディアセッションでは、UDP よりも音質が低下します。</span><span class="sxs-lookup"><span data-stu-id="33251-204">Media sessions over TCP will exhibit poorer quality than over UDP.</span></span> <span data-ttu-id="33251-205">TCP 経由の接続数が0% の品質定義をお勧めします。</span><span class="sxs-lookup"><span data-stu-id="33251-205">We recommend a quality definition of 0% connections over TCP.</span></span> <span data-ttu-id="33251-206">設定した目標を達成するために修復する際には、問題のサブネットを特定し、ファイアウォールルール、パケットコントローラー、およびその他の関連するネットワーク機器構成を調査します。</span><span class="sxs-lookup"><span data-stu-id="33251-206">As you remediate to achieve the target you set, identify problem subnets and investigate firewall rules, packet shapers, and other relevant network equipment configuration.</span></span>

</div>

<span id="ServMgt"></span>

<div>

## <a name="service-management"></a><span data-ttu-id="33251-207">サービス管理</span><span class="sxs-lookup"><span data-stu-id="33251-207">Service Management</span></span>

<span data-ttu-id="33251-208">サービス管理は、CQM の終了状態と3つのすべての道路の宛先です。</span><span class="sxs-lookup"><span data-stu-id="33251-208">Service management is the end state of CQM, and the destination for all three roads.</span></span> <span data-ttu-id="33251-209">高レベルの通話品質を維持するには、次の領域を監視します。</span><span class="sxs-lookup"><span data-stu-id="33251-209">To maintain high levels of call quality, monitor these areas:</span></span>

1.  <span data-ttu-id="33251-210">**ユーザー** -修復アクティビティは、ユーザーの満足度を大幅に向上させる必要があります。</span><span class="sxs-lookup"><span data-stu-id="33251-210">**Users** - Remediation activities should show a measurable increase in user satisfaction.</span></span> <span data-ttu-id="33251-211">これは、問題のチケットまたは他のフィードバックメカニズムによって測定できます。</span><span class="sxs-lookup"><span data-stu-id="33251-211">You can measure this by problem tickets or other feedback mechanisms.</span></span> <span data-ttu-id="33251-212">品質指標を公開することもできます。</span><span class="sxs-lookup"><span data-stu-id="33251-212">You can also publish quality metrics.</span></span>

2.  <span data-ttu-id="33251-213">**プロセス**-毎日、毎週、および毎月のプロセスを operationalize cqm に定義します。</span><span class="sxs-lookup"><span data-stu-id="33251-213">**Process** - define daily, weekly and monthly processes to operationalize CQM.</span></span> <span data-ttu-id="33251-214">修復 (毎日) の周波数が高くなり、安定した頻度 (月単位) に移動すると、監視のリズムは高くなります。</span><span class="sxs-lookup"><span data-stu-id="33251-214">Monitoring rhythm starts at a higher frequency while you are remediating (daily) and moves to a lower frequency (monthly) as you stabilize.</span></span>

3.  <span data-ttu-id="33251-215">**ツール**-測定および修復の両方のツールを識別します。</span><span class="sxs-lookup"><span data-stu-id="33251-215">**Tools** - identify tools to both measure and remediate.</span></span> <span data-ttu-id="33251-216">プロセスをサポートするために、CQM クエリの実行を自動化すると便利な場合があります。</span><span class="sxs-lookup"><span data-stu-id="33251-216">You may find it useful to automate running the CQM queries to support your processes.</span></span> <span data-ttu-id="33251-217">修復には、ネットワーク要素に標準化された構成を適用したり、不適切なストリームで障害をトラブルシューティングしたりするための追加ツールが必要になることがあります。</span><span class="sxs-lookup"><span data-stu-id="33251-217">Remediation may require additional tools for example to enforce standardized configurations on network elements or troubleshooting loss in poor streams.</span></span>

</div>

<span id="BoardGm"></span>

<div>

## <a name="board-game-rules"></a><span data-ttu-id="33251-218">ボードゲームのルール</span><span class="sxs-lookup"><span data-stu-id="33251-218">Board Game Rules</span></span>

<span data-ttu-id="33251-219">このポスターは、CQM 実装への参照として、またはゲームとして使用して、概念を練習することができます。</span><span class="sxs-lookup"><span data-stu-id="33251-219">You can use this poster either as a reference to a CQM implementation or as a game to practice the concepts.</span></span> <span data-ttu-id="33251-220">プレイするには、1 6 サイドと、カードが提供されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="33251-220">To play, you will need one six-sided die and the cards provided.</span></span> <span data-ttu-id="33251-221">ダウンロード可能なカードのバージョンは、標準のエイブリィ5871の名刺に印刷できます。</span><span class="sxs-lookup"><span data-stu-id="33251-221">A downloadable version of the cards is available to print on standard Avery 5871 business cards.</span></span>

<span data-ttu-id="33251-222">ゲームは3人のプレイヤーを対象としています。</span><span class="sxs-lookup"><span data-stu-id="33251-222">The game is for 3 players.</span></span> <span data-ttu-id="33251-223">目的の品質を達成し、センターサービス管理の状態 (サーバー工場、エンドポイント、および最終マイル) に到達するには、次の3つのパスを使用できます。</span><span class="sxs-lookup"><span data-stu-id="33251-223">There are three paths the players can use to achieve the desired quality and reach the center Service Management state: Server Plant, End Point, and Last Mile.</span></span> <span data-ttu-id="33251-224">各パスは、品質目標をアサートし、目標を達成し、システムの側面を維持する方法に沿って停止します。</span><span class="sxs-lookup"><span data-stu-id="33251-224">Each path has stops along the way where you Assert quality targets, Achieve goals, and Maintain an aspect of your system.</span></span> <span data-ttu-id="33251-225">上の指定された領域にカードを置き、5枚のカードを描画します。</span><span class="sxs-lookup"><span data-stu-id="33251-225">Place the cards in the indicated area above, and then draw 5 cards.</span></span> <span data-ttu-id="33251-226">描画したカードを確認し、それを関連ボードセグメントに配置します。</span><span class="sxs-lookup"><span data-stu-id="33251-226">Review the cards you’ve drawn and place them on the relevant board segment.</span></span> <span data-ttu-id="33251-227">各プレーヤーは、パス上のカードを順に移動し、品質ターゲットをアサートし、それらのターゲットを達成し、サービスレベルを維持します。</span><span class="sxs-lookup"><span data-stu-id="33251-227">Each player moves through the cards on their path step by step, asserting quality targets, achieving those targets, and maintaining the service levels.</span></span> <span data-ttu-id="33251-228">すべてのプレイヤーがセンターサービス管理の状態に達すると、ゲームは完了です。</span><span class="sxs-lookup"><span data-stu-id="33251-228">The game is completed when all players reach the center Service Management state.</span></span> <span data-ttu-id="33251-229">詳細なルールについては、「ゲームカードのダウンロード」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="33251-229">More detailed rules are provided with the game card download.</span></span>

<span data-ttu-id="33251-230">品質目標を**アサート**するには、そのターゲットに適用されているパラメーターを確認し、[状態] を選択して、受け入れないようにします。</span><span class="sxs-lookup"><span data-stu-id="33251-230">To **Assert** a quality target, review the parameters applicable to that target, and state out loud what you will and won’t choose to accept.</span></span> <span data-ttu-id="33251-231">開始点は推奨されていますが、最終的な呼び出しを行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="33251-231">We have recommended beginning points, but you must make the final call.</span></span> <span data-ttu-id="33251-232">例外は KHI データで、Microsoft によって規定されている標準を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="33251-232">The exception is KHI data, where the standards established by Microsoft should be used.</span></span> <span data-ttu-id="33251-233">付随する KHI ポスターを参照してください。</span><span class="sxs-lookup"><span data-stu-id="33251-233">See the accompanying KHI poster.</span></span>

<span data-ttu-id="33251-234">ゲーム**では**、khi データおよびシステムクエリの代わりに提供されているカードを使用してください。</span><span class="sxs-lookup"><span data-stu-id="33251-234">To **Achieve** in the game, use the cards provided in place of KHI data and system queries.</span></span> <span data-ttu-id="33251-235">ゲームの開始時に、指定された側面に関連するカードを描画しなかった場合は、それ以降の操作を続行できます。</span><span class="sxs-lookup"><span data-stu-id="33251-235">If at the start of the game you did not draw a card relating to a given aspect, you can continue past it.</span></span> <span data-ttu-id="33251-236">関連するカードがある場合は、さいころをロールします。</span><span class="sxs-lookup"><span data-stu-id="33251-236">If there is a relevant card, roll the die.</span></span> <span data-ttu-id="33251-237">カードに示されている番号に基づいて展開した場合は、成功したことになります。</span><span class="sxs-lookup"><span data-stu-id="33251-237">If you rolled under the number indicated on the card, you have succeeded.</span></span> <span data-ttu-id="33251-238">指定した数以上の場合は、デッキから別のカードを描く必要があります。</span><span class="sxs-lookup"><span data-stu-id="33251-238">If you roll at or over the indicated number, you must draw another card from the deck.</span></span> <span data-ttu-id="33251-239">カードが2人以上のプレーヤーをロールする必要があることを示している場合は、すべてが正常にロールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="33251-239">If the card indicates two or more players need to roll, they must all roll successfully.</span></span>

<span data-ttu-id="33251-240">ゲームを**維持**するために、Lync 環境のその側面に関するサービス管理計画についての概要を示します。</span><span class="sxs-lookup"><span data-stu-id="33251-240">To **Maintain** in the game, state out loud the service management plan regarding that aspect of the Lync environment.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="33251-241">関連項目</span><span class="sxs-lookup"><span data-stu-id="33251-241">See Also</span></span>


[<span data-ttu-id="33251-242">Lync Server ネットワークガイド</span><span class="sxs-lookup"><span data-stu-id="33251-242">Lync Server Networking Guide</span></span>](http://go.microsoft.com/fwlink/p/?linkid=390677)  
[<span data-ttu-id="33251-243">主要な正常性インジケーター: 正常な Lync Server を維持するための基礎</span><span class="sxs-lookup"><span data-stu-id="33251-243">Key Health Indicators: The Foundation for Maintaining Healthy Lync Servers</span></span>](http://go.microsoft.com/fwlink/?linkid=391838)  
[<span data-ttu-id="33251-244">Lync 通話品質の方法論</span><span class="sxs-lookup"><span data-stu-id="33251-244">Lync Call Quality Methodology</span></span>](http://go.microsoft.com/fwlink/?linkid=391841)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

