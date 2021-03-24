---
title: Microsoft Teams の通話品質を監視および改善する
author: SerdarSoysal
ms.author: serdars
manager: Serdars
ms.topic: conceptual
ms.service: msteams
audience: admin
ms.reviewer: vkorlep, siunies
description: サービスの品質 (QoS) 設定を使用し、Microsoft Teams で通話分析と通話品質ダッシュボードを使用します。
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-voice
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 62e687de154fadffd6ac95bd628fec6f9454cc51
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51162659"
---
# <a name="monitor-and-improve-call-quality-for-microsoft-teams"></a><span data-ttu-id="44d8e-103">Microsoft Teams の通話品質を監視および改善する</span><span class="sxs-lookup"><span data-stu-id="44d8e-103">Monitor and improve call quality for Microsoft Teams</span></span>

<span data-ttu-id="44d8e-104">この記事では、Microsoft Teams の通話品質を監視、トラブルシューティング、管理、改善するために使用できる 3 つの重要なツールについて説明します。</span><span class="sxs-lookup"><span data-stu-id="44d8e-104">This article introduces three key tools you can use to monitor, troubleshoot, manage, and improve call quality in Microsoft Teams.</span></span> 

- <span data-ttu-id="44d8e-105">**通話品質ダッシュボード (CQD):** 組織全体の傾向や問題を分析するには、パフォーマンスの向上を後で行います。</span><span class="sxs-lookup"><span data-stu-id="44d8e-105">**Call Quality Dashboard (CQD)**: To analyze org-wide trends or problems, drive improvements to performance</span></span>

- <span data-ttu-id="44d8e-106">**通話分析**: 個々のユーザーの通話と会議の品質を分析するには</span><span class="sxs-lookup"><span data-stu-id="44d8e-106">**Call analytics**: To analyze call and meeting quality for individual users</span></span>

- <span data-ttu-id="44d8e-107">**サービスの品質 (QoS):** 重要なネットワーク トラフィックを優先順位付けするには</span><span class="sxs-lookup"><span data-stu-id="44d8e-107">**Quality of Service (QoS)**: To prioritize important network traffic</span></span>



## <a name="monitor-and-troubleshoot-call-quality"></a><span data-ttu-id="44d8e-108">通話品質を監視およびトラブルシューティングする</span><span class="sxs-lookup"><span data-stu-id="44d8e-108">Monitor and troubleshoot call quality</span></span>
<span data-ttu-id="44d8e-109">ユーザーごとの通話分析と通話品質ダッシュボードを使用して、進行中の操作中に発生する通話品質の問題を見つけてトラブルシューティングします。</span><span class="sxs-lookup"><span data-stu-id="44d8e-109">You'll use per-user **Call analytics** and **Call Quality Dashboard** to find and troubleshoot call-quality problems that come up during ongoing operation.</span></span> <span data-ttu-id="44d8e-110">これにより、ネットワーク全体でパフォーマンスの向上を実現できます。</span><span class="sxs-lookup"><span data-stu-id="44d8e-110">This lets you drive performance improvements across your network.</span></span> <span data-ttu-id="44d8e-111">これらのツールは両方とも Teams 管理センターにあります。</span><span class="sxs-lookup"><span data-stu-id="44d8e-111">Both of these tools are in the Teams admin center.</span></span>

 - <span data-ttu-id="44d8e-112">**通話分析では、Teams** 内の各ユーザーの特定の通話と会議に関連 \*\*\*\* するデバイス、ネットワーク、接続に関する詳細情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="44d8e-112">**Call analytics** shows detailed information about the devices, networks, and connectivity related to  **_specific calls and meetings_** for each user in Teams.</span></span> <span data-ttu-id="44d8e-113">Teams 管理者とヘルプデスク エージェントは、この情報を使用して、特定の通話での通話品質と接続の問題のトラブルシューティングを行います。</span><span class="sxs-lookup"><span data-stu-id="44d8e-113">Teams admin and helpdesk agents will use this information to troubleshoot call quality and connection problems in a specific call.</span></span> <span data-ttu-id="44d8e-114">詳細については、「通話分析を [設定する](set-up-call-analytics.md) 」と「通話分析を使用して低品質の通話のトラブルシューティングを行う [」を参照してください](use-call-analytics-to-troubleshoot-poor-call-quality.md)。</span><span class="sxs-lookup"><span data-stu-id="44d8e-114">To learn more, read [Set up call analytics](set-up-call-analytics.md) and [Use Call Analytics to troubleshoot poor call quality](use-call-analytics-to-troubleshoot-poor-call-quality.md).</span></span>
 
 - <span data-ttu-id="44d8e-115">**通話品質ダッシュボード (CQD)** では \*\*\*\*、組織全体の通話品質をネットワーク全体で表示できます。</span><span class="sxs-lookup"><span data-stu-id="44d8e-115">**Call Quality Dashboard (CQD)** gives you a **_network-wide view_** of call quality across your organization.</span></span> <span data-ttu-id="44d8e-116">CQD 情報を使用して、問題を特定して解決します。</span><span class="sxs-lookup"><span data-stu-id="44d8e-116">Use CQD information to help you identify and fix problems.</span></span> <span data-ttu-id="44d8e-117">まず [、CQD をセットアップします](turning-on-and-using-call-quality-dashboard.md)。</span><span class="sxs-lookup"><span data-stu-id="44d8e-117">First, [Set up CQD](turning-on-and-using-call-quality-dashboard.md).</span></span> <span data-ttu-id="44d8e-118">次に [、「Teams で通話と会議の品質を管理する」を読む](quality-of-experience-review-guide.md)。</span><span class="sxs-lookup"><span data-stu-id="44d8e-118">Then read [Manage call and meeting quality in Teams](quality-of-experience-review-guide.md).</span></span>

 <span data-ttu-id="44d8e-119">通話分析と CQD は並列で実行され、個別に、または一緒に使用できます。</span><span class="sxs-lookup"><span data-stu-id="44d8e-119">Call analytics and CQD run in parallel and can be used independently or together.</span></span> <span data-ttu-id="44d8e-120">たとえば、通信サポートの専門家が、ユーザーの通話の問題のトラブルシューティングにさらに支援が必要と判断した場合、通話に関する追加情報にアクセスできるコミュニケーション サポート エンジニアに通話をエスカレーションします。</span><span class="sxs-lookup"><span data-stu-id="44d8e-120">For example, if a communications support specialist determines that they need more help troubleshooting a user's call problem, they escalate the call to a communications support engineer, who has access to additional information about the call.</span></span> <span data-ttu-id="44d8e-121">さらに、通信サポート エンジニアは、ネットワーク エンジニアに対して、通話分析で気付いたサイト関連の問題の可能性を警告します。</span><span class="sxs-lookup"><span data-stu-id="44d8e-121">In turn, the communications support engineer alerts a network engineer to a possible site-related issue they noticed in the call analytics.</span></span> <span data-ttu-id="44d8e-122">ネットワーク エンジニアは CQD をチェックして、サイト関連の全体的な問題がユーザーの通話の問題の原因になる可能性を確認します。</span><span class="sxs-lookup"><span data-stu-id="44d8e-122">The network engineer checks CQD to see if an overall site-related issue could be a contributing cause of the user's call problem.</span></span>


## <a name="prioritize-important-network-traffic-using-qos"></a><span data-ttu-id="44d8e-123">QoS を使用して重要なネットワーク トラフィックを優先順位付けする</span><span class="sxs-lookup"><span data-stu-id="44d8e-123">Prioritize important network traffic using QoS</span></span>
<span data-ttu-id="44d8e-124">ユーザーが通話や会議に Teams を使い始めるに当たって、発信者の音声が通話や会議で切り取りまたは切り取りされる場合があります。</span><span class="sxs-lookup"><span data-stu-id="44d8e-124">As your users start using Teams for calls and meetings, they may experience a caller's voice breaking up or cutting in and out of a call or meeting.</span></span> <span data-ttu-id="44d8e-125">共有ビデオがフリーズしたりピクセル化したり、完全に失敗したりすることがあります。</span><span class="sxs-lookup"><span data-stu-id="44d8e-125">Shared video may freeze or pixelate, or fail altogether.</span></span> <span data-ttu-id="44d8e-126">これは、ネットワークの混雑が発生し、シーケンスから抜け出す、または一切受信しない音声およびビデオ トラフィックを表す IP パケットが原因です。</span><span class="sxs-lookup"><span data-stu-id="44d8e-126">This is due to the IP packets that represent voice and video traffic encountering network congestion and arriving out of sequence or not at all.</span></span> <span data-ttu-id="44d8e-127">この問題が発生した場合 (または最初に発生する場合は、サービスの品質 **(QoS) を使用します**。</span><span class="sxs-lookup"><span data-stu-id="44d8e-127">If this happens (or to prevent it from happening in the first place), use **Quality of Service (QoS)**.</span></span> 

<span data-ttu-id="44d8e-128">QoS を使用すると、遅延に依存するネットワーク トラフィック (音声ストリームやビデオ ストリームなど) に優先順位を付け、機密性の低いトラフィックの前で (新しいアプリをダウンロードする場合など)、(ダウンロードする余分な秒が大した問題ではない) トラフィックの前で "ラインでカット" することを許可します。</span><span class="sxs-lookup"><span data-stu-id="44d8e-128">With QoS, you prioritize delay-sensitive network traffic (for example, voice or video streams), allowing it to "cut in line" in front of traffic that is less sensitive (like downloading a new app, where an extra second to download isn't a big deal).</span></span> <span data-ttu-id="44d8e-129">QoS は、Windows グループ ポリシー オブジェクトとポートベースのアクセス制御リストと呼ばれるルーティング機能を使用して、すべてのパケットをリアルタイム ストリームで識別してマークします。この機能は、音声、ビデオ、および画面共有に独自の専用ネットワーク帯域幅を提供するようにネットワークに指示します。</span><span class="sxs-lookup"><span data-stu-id="44d8e-129">QoS identifies and marks all packets in real-time streams using Windows Group Policy Objects and a routing feature called Port-based Access Control Lists, which instructs your network to give voice, video, and screen sharing their own dedicated network bandwidth.</span></span>

<span data-ttu-id="44d8e-130">理想的には、Teams を展開する準備をしながら内部ネットワークに QoS を実装しますが、いつでも実行できます。</span><span class="sxs-lookup"><span data-stu-id="44d8e-130">Ideally, you'll implement QoS on your internal network while getting ready to roll out Teams, but you can do it anytime.</span></span> <span data-ttu-id="44d8e-131">十分に小さい場合は、QoS は必要ない可能性があります。</span><span class="sxs-lookup"><span data-stu-id="44d8e-131">If you're small enough, you might not need QoS.</span></span>

<span data-ttu-id="44d8e-132">準備ができたら、「Microsoft Teams でサービス [の品質 (QoS) を実装する」を参照してください](QoS-in-Teams.md)。</span><span class="sxs-lookup"><span data-stu-id="44d8e-132">When you're ready, read [Implement Quality of Service (QoS) in Microsoft Teams](QoS-in-Teams.md).</span></span>

<span data-ttu-id="44d8e-133">QoS を使用して会議トラフィックを管理するには、「Teams 会議のリアルタイム メディア トラフィックを処理する方法を設定する [」を参照してください](meeting-settings-in-teams.md#set-how-you-want-to-handle-real-time-media-traffic-for-teams-meetings)。</span><span class="sxs-lookup"><span data-stu-id="44d8e-133">To use QoS to manage meeting traffic, read [Set how you want to handle real-time media traffic for Teams meetings](meeting-settings-in-teams.md#set-how-you-want-to-handle-real-time-media-traffic-for-teams-meetings).</span></span>


## <a name="related-topics"></a><span data-ttu-id="44d8e-134">関連トピック</span><span class="sxs-lookup"><span data-stu-id="44d8e-134">Related Topics</span></span>

[<span data-ttu-id="44d8e-135">通話分析を設定する</span><span class="sxs-lookup"><span data-stu-id="44d8e-135">Set up call analytics</span></span>](set-up-call-analytics.md)

[<span data-ttu-id="44d8e-136">通話分析を使用して低品質の通話をトラブルシューティングする</span><span class="sxs-lookup"><span data-stu-id="44d8e-136">Use Call Analytics to troubleshoot poor call quality</span></span>](use-call-analytics-to-troubleshoot-poor-call-quality.md)

[<span data-ttu-id="44d8e-137">CQD をセットアップする</span><span class="sxs-lookup"><span data-stu-id="44d8e-137">Set up CQD</span></span>](turning-on-and-using-call-quality-dashboard.md)

[<span data-ttu-id="44d8e-138">Teams で通話と会議の品質を管理する</span><span class="sxs-lookup"><span data-stu-id="44d8e-138">Manage call and meeting quality in Teams</span></span>](quality-of-experience-review-guide.md)

[<span data-ttu-id="44d8e-139">Teams のトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="44d8e-139">Teams Troubleshooting</span></span>](/MicrosoftTeams/troubleshoot/teams)