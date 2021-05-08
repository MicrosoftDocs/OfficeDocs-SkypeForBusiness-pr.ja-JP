---
title: 通話の品質を監視し、改善Microsoft Teams
author: SerdarSoysal
ms.author: serdars
manager: Serdars
ms.topic: conceptual
ms.service: msteams
audience: admin
ms.reviewer: vkorlep, siunies
description: サービス品質 (QoS) 設定を使用し、次に、Microsoft Teams の [通話分析] と [通話品質ダッシュボード] を使用します。
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
# <a name="monitor-and-improve-call-quality-for-microsoft-teams"></a><span data-ttu-id="571f8-103">通話の品質を監視し、改善Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="571f8-103">Monitor and improve call quality for Microsoft Teams</span></span>

<span data-ttu-id="571f8-104">この記事では、通話の品質を監視、トラブルシューティング、管理、および改善するために使用できる 3 つの主要なツールについてMicrosoft Teams。</span><span class="sxs-lookup"><span data-stu-id="571f8-104">This article introduces three key tools you can use to monitor, troubleshoot, manage, and improve call quality in Microsoft Teams.</span></span> 

- <span data-ttu-id="571f8-105">**通話品質ダッシュボード (CQD)**: 組織全体の傾向や問題を分析するには、パフォーマンスの向上に役立つ</span><span class="sxs-lookup"><span data-stu-id="571f8-105">**Call Quality Dashboard (CQD)**: To analyze org-wide trends or problems, drive improvements to performance</span></span>

- <span data-ttu-id="571f8-106">**通話分析**: 個々のユーザーの通話と会議の品質を分析するには</span><span class="sxs-lookup"><span data-stu-id="571f8-106">**Call analytics**: To analyze call and meeting quality for individual users</span></span>

- <span data-ttu-id="571f8-107">**サービス品質 (QoS)**: 重要なネットワーク トラフィックに優先順位を付ける</span><span class="sxs-lookup"><span data-stu-id="571f8-107">**Quality of Service (QoS)**: To prioritize important network traffic</span></span>



## <a name="monitor-and-troubleshoot-call-quality"></a><span data-ttu-id="571f8-108">通話品質の監視とトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="571f8-108">Monitor and troubleshoot call quality</span></span>
<span data-ttu-id="571f8-109">ユーザーごとの通話分析と通話品質ダッシュボードを使用して、進行中の操作中に発生する通話品質の問題を見つけてトラブルシューティングします。</span><span class="sxs-lookup"><span data-stu-id="571f8-109">You'll use per-user **Call analytics** and **Call Quality Dashboard** to find and troubleshoot call-quality problems that come up during ongoing operation.</span></span> <span data-ttu-id="571f8-110">これにより、ネットワーク全体のパフォーマンス向上を実現できます。</span><span class="sxs-lookup"><span data-stu-id="571f8-110">This lets you drive performance improvements across your network.</span></span> <span data-ttu-id="571f8-111">これらのツールはどちらも、管理センター Teamsにあります。</span><span class="sxs-lookup"><span data-stu-id="571f8-111">Both of these tools are in the Teams admin center.</span></span>

 - <span data-ttu-id="571f8-112">**通話分析では**、デバイス、ネットワーク、および各ユーザーの特定の通話や会議に \*\*\*\* 関連する接続に関する詳細情報がTeams。</span><span class="sxs-lookup"><span data-stu-id="571f8-112">**Call analytics** shows detailed information about the devices, networks, and connectivity related to  **_specific calls and meetings_** for each user in Teams.</span></span> <span data-ttu-id="571f8-113">Teamsヘルプデスク エージェントは、この情報を使用して、特定の呼び出しでの通話品質と接続の問題のトラブルシューティングを行います。</span><span class="sxs-lookup"><span data-stu-id="571f8-113">Teams admin and helpdesk agents will use this information to troubleshoot call quality and connection problems in a specific call.</span></span> <span data-ttu-id="571f8-114">詳細については、「通話分析を設定 [する」](set-up-call-analytics.md) と「通話分析を使用して低品質の通話のトラブルシューティング [を行う」を参照してください](use-call-analytics-to-troubleshoot-poor-call-quality.md)。</span><span class="sxs-lookup"><span data-stu-id="571f8-114">To learn more, read [Set up call analytics](set-up-call-analytics.md) and [Use Call Analytics to troubleshoot poor call quality](use-call-analytics-to-troubleshoot-poor-call-quality.md).</span></span>
 
 - <span data-ttu-id="571f8-115">**通話品質ダッシュボード (CQD) を使用** すると、 **_組織全体の_** 通話品質をネットワーク全体で確認できます。</span><span class="sxs-lookup"><span data-stu-id="571f8-115">**Call Quality Dashboard (CQD)** gives you a **_network-wide view_** of call quality across your organization.</span></span> <span data-ttu-id="571f8-116">CQD 情報を使用して、問題の特定と解決に役立ちます。</span><span class="sxs-lookup"><span data-stu-id="571f8-116">Use CQD information to help you identify and fix problems.</span></span> <span data-ttu-id="571f8-117">最初に [、CQD を設定します](turning-on-and-using-call-quality-dashboard.md)。</span><span class="sxs-lookup"><span data-stu-id="571f8-117">First, [Set up CQD](turning-on-and-using-call-quality-dashboard.md).</span></span> <span data-ttu-id="571f8-118">次に、「[通話と会議の品質を管理する」をTeams。](quality-of-experience-review-guide.md)</span><span class="sxs-lookup"><span data-stu-id="571f8-118">Then read [Manage call and meeting quality in Teams](quality-of-experience-review-guide.md).</span></span>

 <span data-ttu-id="571f8-119">呼び出し分析と CQD は並列で実行され、個別に、または一緒に使用できます。</span><span class="sxs-lookup"><span data-stu-id="571f8-119">Call analytics and CQD run in parallel and can be used independently or together.</span></span> <span data-ttu-id="571f8-120">たとえば、通信サポートスペシャリストが、ユーザーの通話問題のトラブルシューティングにさらに支援が必要と判断した場合、通話に関する追加情報にアクセスできるコミュニケーション サポート エンジニアに通話をエスカレートします。</span><span class="sxs-lookup"><span data-stu-id="571f8-120">For example, if a communications support specialist determines that they need more help troubleshooting a user's call problem, they escalate the call to a communications support engineer, who has access to additional information about the call.</span></span> <span data-ttu-id="571f8-121">さらに、通信サポート エンジニアは、通話分析で気付いたサイト関連の問題の可能性についてネットワーク エンジニアに警告します。</span><span class="sxs-lookup"><span data-stu-id="571f8-121">In turn, the communications support engineer alerts a network engineer to a possible site-related issue they noticed in the call analytics.</span></span> <span data-ttu-id="571f8-122">ネットワーク エンジニアは、CQD をチェックして、サイト関連の全体的な問題がユーザーの通話問題の原因になる可能性がある場合を確認します。</span><span class="sxs-lookup"><span data-stu-id="571f8-122">The network engineer checks CQD to see if an overall site-related issue could be a contributing cause of the user's call problem.</span></span>


## <a name="prioritize-important-network-traffic-using-qos"></a><span data-ttu-id="571f8-123">QoS を使用して重要なネットワーク トラフィックに優先順位を付ける</span><span class="sxs-lookup"><span data-stu-id="571f8-123">Prioritize important network traffic using QoS</span></span>
<span data-ttu-id="571f8-124">ユーザーが通話や会議に Teams を使い始めると、発信者の音声が別れ、通話や会議の切り抜きが発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="571f8-124">As your users start using Teams for calls and meetings, they may experience a caller's voice breaking up or cutting in and out of a call or meeting.</span></span> <span data-ttu-id="571f8-125">共有ビデオがフリーズしたり、ピクセル化したり、完全に失敗したりすることがあります。</span><span class="sxs-lookup"><span data-stu-id="571f8-125">Shared video may freeze or pixelate, or fail altogether.</span></span> <span data-ttu-id="571f8-126">これは、ネットワークの輻輳が発生し、順不同で到着する、または一切到着しない音声およびビデオ トラフィックを表す IP パケットが原因です。</span><span class="sxs-lookup"><span data-stu-id="571f8-126">This is due to the IP packets that represent voice and video traffic encountering network congestion and arriving out of sequence or not at all.</span></span> <span data-ttu-id="571f8-127">これが発生した場合 (または、最初に発生するのを防ぐために) は、サービス品質 **(QoS) を使用します**。</span><span class="sxs-lookup"><span data-stu-id="571f8-127">If this happens (or to prevent it from happening in the first place), use **Quality of Service (QoS)**.</span></span> 

<span data-ttu-id="571f8-128">QoS では、遅延の影響を受けるネットワーク トラフィック (音声やビデオ ストリームなど) に優先順位を付け、機密性の低いトラフィックの前で (新しいアプリをダウンロードする場合など)、追加の 1 秒をダウンロードすることはあまり重要ではありません。</span><span class="sxs-lookup"><span data-stu-id="571f8-128">With QoS, you prioritize delay-sensitive network traffic (for example, voice or video streams), allowing it to "cut in line" in front of traffic that is less sensitive (like downloading a new app, where an extra second to download isn't a big deal).</span></span> <span data-ttu-id="571f8-129">QoS は、Windows グループ ポリシー オブジェクトとポート ベースのアクセス制御リストと呼ばれるルーティング機能を使用して、すべてのパケットをリアルタイム ストリームで識別してマークします。この機能は、音声、ビデオ、画面共有に独自の専用ネットワーク帯域幅を提供するようネットワークに指示します。</span><span class="sxs-lookup"><span data-stu-id="571f8-129">QoS identifies and marks all packets in real-time streams using Windows Group Policy Objects and a routing feature called Port-based Access Control Lists, which instructs your network to give voice, video, and screen sharing their own dedicated network bandwidth.</span></span>

<span data-ttu-id="571f8-130">理想的には、内部ネットワークに QoS を実装しながら、Teams を展開する準備をしますが、いつでも実行できます。</span><span class="sxs-lookup"><span data-stu-id="571f8-130">Ideally, you'll implement QoS on your internal network while getting ready to roll out Teams, but you can do it anytime.</span></span> <span data-ttu-id="571f8-131">十分に小さい場合は、QoS は必要ない可能性があります。</span><span class="sxs-lookup"><span data-stu-id="571f8-131">If you're small enough, you might not need QoS.</span></span>

<span data-ttu-id="571f8-132">準備ができたら、「サービス品質[(QoS)](QoS-in-Teams.md)を実装する」を参照Microsoft Teams。</span><span class="sxs-lookup"><span data-stu-id="571f8-132">When you're ready, read [Implement Quality of Service (QoS) in Microsoft Teams](QoS-in-Teams.md).</span></span>

<span data-ttu-id="571f8-133">QoS を使用して会議のトラフィックを管理するには、「会議のリアルタイム メディア トラフィックを処理する方法を設定する[」をTeamsしてください](meeting-settings-in-teams.md#set-how-you-want-to-handle-real-time-media-traffic-for-teams-meetings)。</span><span class="sxs-lookup"><span data-stu-id="571f8-133">To use QoS to manage meeting traffic, read [Set how you want to handle real-time media traffic for Teams meetings](meeting-settings-in-teams.md#set-how-you-want-to-handle-real-time-media-traffic-for-teams-meetings).</span></span>


## <a name="related-topics"></a><span data-ttu-id="571f8-134">関連トピック</span><span class="sxs-lookup"><span data-stu-id="571f8-134">Related Topics</span></span>

[<span data-ttu-id="571f8-135">通話分析を設定する</span><span class="sxs-lookup"><span data-stu-id="571f8-135">Set up call analytics</span></span>](set-up-call-analytics.md)

[<span data-ttu-id="571f8-136">通話分析を使用して低品質の通話をトラブルシューティングする</span><span class="sxs-lookup"><span data-stu-id="571f8-136">Use Call Analytics to troubleshoot poor call quality</span></span>](use-call-analytics-to-troubleshoot-poor-call-quality.md)

[<span data-ttu-id="571f8-137">CQD を設定する</span><span class="sxs-lookup"><span data-stu-id="571f8-137">Set up CQD</span></span>](turning-on-and-using-call-quality-dashboard.md)

[<span data-ttu-id="571f8-138">通話と会議の品質を管理Teams</span><span class="sxs-lookup"><span data-stu-id="571f8-138">Manage call and meeting quality in Teams</span></span>](quality-of-experience-review-guide.md)

[<span data-ttu-id="571f8-139">Teams のトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="571f8-139">Teams Troubleshooting</span></span>](/MicrosoftTeams/troubleshoot/teams)