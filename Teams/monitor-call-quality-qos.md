---
title: Microsoft Teams の通話品質を監視および向上させる
author: lolajacobsen
ms.author: lolaj
manager: Serdars
ms.topic: conceptual
ms.service: msteams
audience: admin
ms.reviewer: vkorlep, siunies
description: '[QoS (Quality of Service)] の設定を使用して、Microsoft Teams で分析と通話品質ダッシュボードを呼び出します。'
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-voice
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 2d5db11bbd9608aebb1eb2b73ebacc9793629e44
ms.sourcegitcommit: 90939ad992e65f840e4c2e7a6d18d821621319b4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/09/2020
ms.locfileid: "45085944"
---
# <a name="monitor-and-improve-call-quality-for-microsoft-teams"></a><span data-ttu-id="04efa-103">Microsoft Teams の通話品質を監視および向上させる</span><span class="sxs-lookup"><span data-stu-id="04efa-103">Monitor and improve call quality for Microsoft Teams</span></span>

<span data-ttu-id="04efa-104">この記事では、Microsoft Teams の通話品質を監視、トラブルシューティング、管理、向上させるために使用できる3つの主要ツールについて説明します。</span><span class="sxs-lookup"><span data-stu-id="04efa-104">This article introduces three key tools you can use to monitor, troubleshoot, manage, and improve call quality in Microsoft Teams.</span></span> 

- <span data-ttu-id="04efa-105">**通話品質ダッシュボード (CQD)**: 組織全体の傾向や問題を分析して、パフォーマンスを向上させる</span><span class="sxs-lookup"><span data-stu-id="04efa-105">**Call Quality Dashboard (CQD)**: To analyze org-wide trends or problems, drive improvements to performance</span></span>

- <span data-ttu-id="04efa-106">**通話分析**: 個々のユーザーの通話と会議の品質を分析する</span><span class="sxs-lookup"><span data-stu-id="04efa-106">**Call analytics**: To analyze call and meeting quality for individual users</span></span>

- <span data-ttu-id="04efa-107">**QoS (Quality Of Service)**: 重要なネットワークトラフィックの優先順位付け</span><span class="sxs-lookup"><span data-stu-id="04efa-107">**Quality of Service (QoS)**: To prioritize important network traffic</span></span>



## <a name="monitor-and-troubleshoot-call-quality"></a><span data-ttu-id="04efa-108">通話品質の監視とトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="04efa-108">Monitor and troubleshoot call quality</span></span>
<span data-ttu-id="04efa-109">ユーザーごとの**通話分析**と**通話品質ダッシュボード**を使用して、進行中の操作中に発生する可能性のある通話品質の問題を検出し、トラブルシューティングします。</span><span class="sxs-lookup"><span data-stu-id="04efa-109">You'll use per-user **Call analytics** and **Call Quality Dashboard** to find and troubleshoot call-quality problems that come up during ongoing operation.</span></span> <span data-ttu-id="04efa-110">これにより、ネットワーク全体のパフォーマンスを向上させることができます。</span><span class="sxs-lookup"><span data-stu-id="04efa-110">This lets you drive performance improvements across your network.</span></span> <span data-ttu-id="04efa-111">これらのツールはどちらも Teams 管理センターにあります。</span><span class="sxs-lookup"><span data-stu-id="04efa-111">Both of these tools are in the Teams admin center.</span></span>

 - <span data-ttu-id="04efa-112">[**通話分析**] には、チーム内の各ユーザーの特定の***通話と会議***に関連するデバイス、ネットワーク、接続に関する詳細情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="04efa-112">**Call analytics** shows detailed information about the devices, networks, and connectivity related to  ***specific calls and meetings*** for each user in Teams.</span></span> <span data-ttu-id="04efa-113">チーム管理者およびヘルプデスク担当者はこの情報を使って、特定の通話での通話品質と接続の問題のトラブルシューティングを行います。</span><span class="sxs-lookup"><span data-stu-id="04efa-113">Teams admin and helpdesk agents will use this information to troubleshoot call quality and connection problems in a specific call.</span></span> <span data-ttu-id="04efa-114">詳細については、「通話[分析を設定](set-up-call-analytics.md)する」および「[通話分析を使用して通話品質の低下を解決する」を](use-call-analytics-to-troubleshoot-poor-call-quality.md)参照してください。</span><span class="sxs-lookup"><span data-stu-id="04efa-114">To learn more, read [Set up call analytics](set-up-call-analytics.md) and [Use Call Analytics to troubleshoot poor call quality](use-call-analytics-to-troubleshoot-poor-call-quality.md).</span></span>
 
 - <span data-ttu-id="04efa-115">**通話品質ダッシュボード (CQD)** を使用すると、組織全体の通話品質を***ネットワーク全体で確認***できます。</span><span class="sxs-lookup"><span data-stu-id="04efa-115">**Call Quality Dashboard (CQD)** gives you a ***network-wide view*** of call quality across your organization.</span></span> <span data-ttu-id="04efa-116">CQD 情報を使用して、問題の特定と解決に役立ちます。</span><span class="sxs-lookup"><span data-stu-id="04efa-116">Use CQD information to help you identify and fix problems.</span></span> <span data-ttu-id="04efa-117">まず、 [CQD を設定](turning-on-and-using-call-quality-dashboard.md)します。</span><span class="sxs-lookup"><span data-stu-id="04efa-117">First, [Set up CQD](turning-on-and-using-call-quality-dashboard.md).</span></span> <span data-ttu-id="04efa-118">次に、「 [Teams で通話と会議の品質を管理する」](quality-of-experience-review-guide.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="04efa-118">Then read [Manage call and meeting quality in Teams](quality-of-experience-review-guide.md).</span></span>

 <span data-ttu-id="04efa-119">通話分析と CQD は並列で実行され、個別に、または一緒に使うことができます。</span><span class="sxs-lookup"><span data-stu-id="04efa-119">Call analytics and CQD run in parallel and can be used independently or together.</span></span> <span data-ttu-id="04efa-120">たとえば、通信サポート担当者が、ユーザーの通話の問題のトラブルシューティングにさらに詳しいヘルプが必要であると判断した場合は、通話に関する追加情報にアクセスできる通信サポートエンジニアに通話がエスカレートされます。</span><span class="sxs-lookup"><span data-stu-id="04efa-120">For example, if a communications support specialist determines that they need more help troubleshooting a user's call problem, they escalate the call to a communications support engineer, who has access to additional information about the call.</span></span> <span data-ttu-id="04efa-121">さらに、通信サポートエンジニアが、通話分析で検出されたサイト関連の問題についてネットワークエンジニアに警告します。</span><span class="sxs-lookup"><span data-stu-id="04efa-121">In turn, the communications support engineer alerts a network engineer to a possible site-related issue they noticed in the call analytics.</span></span> <span data-ttu-id="04efa-122">ネットワークエンジニアは、CQD をチェックして、サイトに関連する全体的な問題がユーザーの通話の問題の原因になっている可能性があるかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="04efa-122">The network engineer checks CQD to see if an overall site-related issue could be a contributing cause of the user's call problem.</span></span>


## <a name="prioritize-important-network-traffic-using-qos"></a><span data-ttu-id="04efa-123">QoS を使用して重要なネットワークトラフィックの優先順位を付ける</span><span class="sxs-lookup"><span data-stu-id="04efa-123">Prioritize important network traffic using QoS</span></span>
<span data-ttu-id="04efa-124">ユーザーが通話と会議に Teams の使用を開始すると、発信者の声が出たり、通話や会議の途中で切断されたりする場合があります。</span><span class="sxs-lookup"><span data-stu-id="04efa-124">As your users start using Teams for calls and meetings, they may experience a caller's voice breaking up or cutting in and out of a call or meeting.</span></span> <span data-ttu-id="04efa-125">共有ビデオは、フリーズまたは pixelate、または完全に失敗することがあります。</span><span class="sxs-lookup"><span data-stu-id="04efa-125">Shared video may freeze or pixelate, or fail altogether.</span></span> <span data-ttu-id="04efa-126">これは、ネットワークの輻輳を示す音声とビデオのトラフィックを示す IP パケットによって、順番が正しく表示されない、またはまったく表示されないためです。</span><span class="sxs-lookup"><span data-stu-id="04efa-126">This is due to the IP packets that represent voice and video traffic encountering network congestion and arriving out of sequence or not at all.</span></span> <span data-ttu-id="04efa-127">この問題が発生した場合は (または最初の場所で行われないようにするために)、 **Quality Of Service (QoS)** を使用します。</span><span class="sxs-lookup"><span data-stu-id="04efa-127">If this happens (or to prevent it from happening in the first place), use **Quality of Service (QoS)**.</span></span> 

<span data-ttu-id="04efa-128">QoS では、遅延が発生する可能性のあるネットワークトラフィック (音声やビデオのストリームなど) の優先順位を付けて、機密性の低いトラフィック (たとえば、新しいアプリをダウンロードして、もう1つ目のダウンロードがあまり重要でない場合) に優先順位を付けることができます。</span><span class="sxs-lookup"><span data-stu-id="04efa-128">With QoS, you prioritize delay-sensitive network traffic (for example, voice or video streams), allowing it to "cut in line" in front of traffic that is less sensitive (like downloading a new app, where an extra second to download isn't a big deal).</span></span> <span data-ttu-id="04efa-129">QoS では、Windows のグループポリシーオブジェクトと、ポートベースのアクセス制御リストと呼ばれるルーティング機能を使用して、リアルタイムストリーム内のすべてのパケットを識別してマークします。これは、ネットワークに対して、独自の専用ネットワーク帯域幅で音声、ビデオ、画面を共有するように指示します。</span><span class="sxs-lookup"><span data-stu-id="04efa-129">QoS identifies and marks all packets in real-time streams using Windows Group Policy Objects and a routing feature called Port-based Access Control Lists, which instructs your network to give voice, video, and screen sharing their own dedicated network bandwidth.</span></span>

<span data-ttu-id="04efa-130">理想的には、社内ネットワークに QoS を実装して、Teams をロールアウトする準備をしていますが、いつでも行うことができます。</span><span class="sxs-lookup"><span data-stu-id="04efa-130">Ideally, you'll implement QoS on your internal network while getting ready to roll out Teams, but you can do it anytime.</span></span> <span data-ttu-id="04efa-131">容量が十分でない場合は、QoS を必要としない可能性があります。</span><span class="sxs-lookup"><span data-stu-id="04efa-131">If you're small enough, you might not need QoS.</span></span>

<span data-ttu-id="04efa-132">準備ができたら、「 [Microsoft Teams でサービスの品質 (QoS) を実装する (QoS)」](QoS-in-Teams.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="04efa-132">When you're ready, read [Implement Quality of Service (QoS) in Microsoft Teams](QoS-in-Teams.md).</span></span>

<span data-ttu-id="04efa-133">QoS を使って会議トラフィックを管理するには、「 [Teams 会議のリアルタイムメディアトラフィックを処理する方法を設定](meeting-settings-in-teams.md#set-how-you-want-to-handle-real-time-media-traffic-for-teams-meetings)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="04efa-133">To use QoS to manage meeting traffic, read [Set how you want to handle real-time media traffic for Teams meetings](meeting-settings-in-teams.md#set-how-you-want-to-handle-real-time-media-traffic-for-teams-meetings).</span></span>


## <a name="related-topics"></a><span data-ttu-id="04efa-134">関連項目</span><span class="sxs-lookup"><span data-stu-id="04efa-134">Related Topics</span></span>

[<span data-ttu-id="04efa-135">通話分析を設定する</span><span class="sxs-lookup"><span data-stu-id="04efa-135">Set up call analytics</span></span>](set-up-call-analytics.md)

[<span data-ttu-id="04efa-136">通話分析を使用して低品質の通話をトラブルシューティングする</span><span class="sxs-lookup"><span data-stu-id="04efa-136">Use Call Analytics to troubleshoot poor call quality</span></span>](use-call-analytics-to-troubleshoot-poor-call-quality.md)

[<span data-ttu-id="04efa-137">CQD を設定する</span><span class="sxs-lookup"><span data-stu-id="04efa-137">Set up CQD</span></span>](turning-on-and-using-call-quality-dashboard.md)

[<span data-ttu-id="04efa-138">Teams で通話と会議の品質を管理する</span><span class="sxs-lookup"><span data-stu-id="04efa-138">Manage call and meeting quality in Teams</span></span>](quality-of-experience-review-guide.md)

[<span data-ttu-id="04efa-139">チームのトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="04efa-139">Teams Troubleshooting</span></span>](https://docs.microsoft.com/MicrosoftTeams/troubleshoot/teams)

