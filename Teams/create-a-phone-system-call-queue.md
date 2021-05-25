---
title: 呼び出しキューを作成Microsoft Teams
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.reviewer: colongma
ms.topic: article
ms.assetid: 67ccda94-1210-43fb-a25b-7b9785f8a061
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
- m365initiative-voice
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.callqueues.overview"
- Phone System
- seo-marvel-apr2020
description: Microsoft Teams で大規模な組織の通話キューを設定する方法について説明します。この機能は、あいさつメッセージ、保留音楽、通話リダイレクト、その他の機能を提供します。
ms.openlocfilehash: 926e3903f0ee59271d0b4806cf61ad02a6f52088
ms.sourcegitcommit: 330e60ff3549cd5cff5b52ad95dc4259e4e8de13
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/24/2021
ms.locfileid: "52628936"
---
# <a name="create-a-call-queue"></a><span data-ttu-id="396bb-103">呼び出しキューを作成する</span><span class="sxs-lookup"><span data-stu-id="396bb-103">Create a call queue</span></span>

<span data-ttu-id="396bb-104">通話キューは、特定の問題や質問に役立つ組織内のユーザーに発信者をルーティングする方法を提供します。</span><span class="sxs-lookup"><span data-stu-id="396bb-104">Call queues provide a method of routing callers to people in your organization who can help with a particular issue or question.</span></span> <span data-ttu-id="396bb-105">呼び出しは、キュー内のユーザー (エージェントと呼ばれる) に一度に 1 回 *配布されます*。</span><span class="sxs-lookup"><span data-stu-id="396bb-105">Calls are distributed one at a time to the people in the queue (who are known as *agents*).</span></span> 

> [!TIP]
> <span data-ttu-id="396bb-106">この記事は大規模な組織です。</span><span class="sxs-lookup"><span data-stu-id="396bb-106">This article is large organizations.</span></span> <span data-ttu-id="396bb-107">組織が小規模企業の場合は、「通話キューの作成 - 代わりに小規模ビジネス向け [チュートリアル」を](/microsoftteams/business-voice/create-a-phone-system-call-queue-smb) 参照してください。</span><span class="sxs-lookup"><span data-stu-id="396bb-107">If your organization is a small business, read [Create a call queue - small business tutorial](/microsoftteams/business-voice/create-a-phone-system-call-queue-smb) instead.</span></span>

<span data-ttu-id="396bb-108">呼び出しキューには、次の機能があります。</span><span class="sxs-lookup"><span data-stu-id="396bb-108">Call queues provide:</span></span>

- <span data-ttu-id="396bb-109">あいさつメッセージ。</span><span class="sxs-lookup"><span data-stu-id="396bb-109">A greeting message.</span></span>

- <span data-ttu-id="396bb-110">ユーザーがキューで保留を待機している間の音楽。</span><span class="sxs-lookup"><span data-stu-id="396bb-110">Music while people are waiting on hold in a queue.</span></span>

- <span data-ttu-id="396bb-111">コール ルーティング - *First In,First Out* (FIFO) order - to agents.</span><span class="sxs-lookup"><span data-stu-id="396bb-111">Call routing - in *First In, First Out* (FIFO) order - to agents.</span></span>

- <span data-ttu-id="396bb-112">キューのオーバーフローとタイムアウトの処理オプション。</span><span class="sxs-lookup"><span data-stu-id="396bb-112">Handling options for queue overflow and timeout.</span></span>

<span data-ttu-id="396bb-113">この記事の手順に従う前に[、「Teams](plan-auto-attendant-call-queue.md)自動応答と通話キューの計画」を[](plan-auto-attendant-call-queue.md#getting-started)読み、概要の手順に従ってください。</span><span class="sxs-lookup"><span data-stu-id="396bb-113">Be sure you have read [Plan for Teams auto attendants and call queues](plan-auto-attendant-call-queue.md) and followed the [getting started steps](plan-auto-attendant-call-queue.md#getting-started) before you follow the procedures in this article.</span></span>

## <a name="video-demonstration"></a><span data-ttu-id="396bb-114">ビデオデモ</span><span class="sxs-lookup"><span data-stu-id="396bb-114">Video demonstration</span></span>

<span data-ttu-id="396bb-115">このビデオでは、通話キューを作成する方法の基本的な例をTeams。</span><span class="sxs-lookup"><span data-stu-id="396bb-115">This video shows a basic example of how to create a call queue in Teams.</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RWCF23?autoplay=false]

## <a name="create-the-call-queue"></a><span data-ttu-id="396bb-116">呼び出しキューを作成する</span><span class="sxs-lookup"><span data-stu-id="396bb-116">Create the call queue</span></span>

<span data-ttu-id="396bb-117">通話キューを設定するには、Teams 管理センターで、[音声] を展開し、[通話キュー] をクリックし、[追加] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="396bb-117">To set up a call queue, in the Teams admin center, expand **Voice**, click **Call queues**, and then click **Add**.</span></span>

### <a name="resource-account-and-language"></a><span data-ttu-id="396bb-118">リソース アカウントと言語</span><span class="sxs-lookup"><span data-stu-id="396bb-118">Resource account and language</span></span>

![リソース アカウントと言語設定のスクリーンショット](media/call-queue-name-language.png)

1. <span data-ttu-id="396bb-120">通話キューの名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="396bb-120">Type a name for the call queue.</span></span>

2. <span data-ttu-id="396bb-121">[**アカウントの追加]** をクリックし、この呼び出しキューで使用するリソースアカウントを検索し、[追加] をクリックして、[追加] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="396bb-121">Click **Add accounts**, search for the resource account that you want to use with this call queue, click **Add**, and then click **Add**.</span></span> <span data-ttu-id="396bb-122">(エージェントは、着信呼び出しを受信すると、リソース アカウント名を表示します)。</span><span class="sxs-lookup"><span data-stu-id="396bb-122">(Agents will see the resource account name when they receive an incoming call.)</span></span>

3. <span data-ttu-id="396bb-123">サポートされている [言語を選択します](create-a-phone-system-call-queue-languages.md)。</span><span class="sxs-lookup"><span data-stu-id="396bb-123">Choose a [supported language](create-a-phone-system-call-queue-languages.md).</span></span> <span data-ttu-id="396bb-124">この言語は、システムで生成された音声プロンプトとボイスメールのトランスクリプション (有効にした場合) に使用されます。</span><span class="sxs-lookup"><span data-stu-id="396bb-124">This language will be used for system-generated voice prompts and voicemail transcription (if you enable them).</span></span>

### <a name="greetings-and-music-on-hold-in-queue"></a><span data-ttu-id="396bb-125">キュー内の応答メッセージと保留音</span><span class="sxs-lookup"><span data-stu-id="396bb-125">Greetings and music on hold in queue</span></span>

<span data-ttu-id="396bb-126">発信者がキューに到着するときに、発信者にあいさつメッセージを再生する場合に指定します。</span><span class="sxs-lookup"><span data-stu-id="396bb-126">Specify if you want to play a greeting to callers when they arrive in the queue.</span></span> <span data-ttu-id="396bb-127">再生するあいさつメッセージを含む MP3、WAV、または WMA ファイルをアップロードする必要があります。</span><span class="sxs-lookup"><span data-stu-id="396bb-127">You must upload an MP3, WAV, or WMA file containing the greeting that you want to play.</span></span>

<span data-ttu-id="396bb-128">Teamsキュー内で保留されている間、呼び出し元に既定の音楽を提供します。</span><span class="sxs-lookup"><span data-stu-id="396bb-128">Teams provides default music to callers while they are on hold in a queue.</span></span> <span data-ttu-id="396bb-129">特定のオーディオ ファイルを再生する場合は、[オーディオ ファイルの再生] を選択し、MP3、WAV、または WMA ファイルをアップロードします。</span><span class="sxs-lookup"><span data-stu-id="396bb-129">If you want to play a specific audio file, choose **Play an audio file** and upload an MP3, WAV, or WMA file.</span></span>

> [!NOTE]
> <span data-ttu-id="396bb-130">アップロードされた記録は 5 MB 以下にできます。</span><span class="sxs-lookup"><span data-stu-id="396bb-130">The uploaded recording can be no larger than 5 MB.</span></span>
> <span data-ttu-id="396bb-131">通話キューで提供される既定Teamsは、組織が支払う使用料金は無料です。</span><span class="sxs-lookup"><span data-stu-id="396bb-131">The default music supplied in Teams call queues is free of any royalties payable by your organization.</span></span> 

### <a name="call-agents"></a><span data-ttu-id="396bb-132">エージェントの呼び出し</span><span class="sxs-lookup"><span data-stu-id="396bb-132">Call agents</span></span>

<span data-ttu-id="396bb-133">エージェントを [呼び出しキューに追加するための前提条件を確認します](plan-auto-attendant-call-queue.md#prerequisites)。</span><span class="sxs-lookup"><span data-stu-id="396bb-133">Review the [prerequisites for adding agents to a call queue](plan-auto-attendant-call-queue.md#prerequisites).</span></span>

![通話キューのユーザーとグループの設定のスクリーンショット](media/call-queue-users-groups.png)

##### <a name="teams-channel"></a><span data-ttu-id="396bb-135">Teams チャネル</span><span class="sxs-lookup"><span data-stu-id="396bb-135">Teams channel</span></span>

<span data-ttu-id="396bb-136">1 つのチャネルを介して最大 200 のエージェントTeamsできます。</span><span class="sxs-lookup"><span data-stu-id="396bb-136">You can add up to 200 agents via a Teams channel.</span></span>

<span data-ttu-id="396bb-137">キューを管理するために [Teamsを使用する](https://support.microsoft.com/office/9f07dabe-91c6-4a9b-a545-8ffdddd2504e)場合は、[チームの選択] オプションを選択し、[チャネルの追加 **] をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="396bb-137">If you want to [use a Teams channel to manage the queue](https://support.microsoft.com/office/9f07dabe-91c6-4a9b-a545-8ffdddd2504e), select the **Choose a team** option and click **Add a channel**.</span></span> <span data-ttu-id="396bb-138">使用するチームを検索して選択し、[追加] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="396bb-138">Search for the team that you want to use, select it, and click **Add**.</span></span> <span data-ttu-id="396bb-139">使用するチャネルを選択し、[適用] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="396bb-139">Select the channel that you want to use and click **Apply**.</span></span>

<span data-ttu-id="396bb-140">次のクライアントは、呼び出しキューにTeamsチャネルを使用する場合にサポートされます。</span><span class="sxs-lookup"><span data-stu-id="396bb-140">The following clients are supported when using a Teams channel for call queues:</span></span> 

  - <span data-ttu-id="396bb-141">Microsoft Teams Windows クライアント</span><span class="sxs-lookup"><span data-stu-id="396bb-141">Microsoft Teams Windows client</span></span>
  - <span data-ttu-id="396bb-142">Microsoft Teams Mac クライアント</span><span class="sxs-lookup"><span data-stu-id="396bb-142">Microsoft Teams Mac client</span></span>

##### <a name="users-and-groups"></a><span data-ttu-id="396bb-143">ユーザーとグループ</span><span class="sxs-lookup"><span data-stu-id="396bb-143">Users and groups</span></span>

<span data-ttu-id="396bb-144">最大 20 個のエージェントを個別に追加し、最大 200 個のエージェントをグループ経由で追加できます。</span><span class="sxs-lookup"><span data-stu-id="396bb-144">You can add up to 20 agents individually and up to 200 agents via groups.</span></span>

<span data-ttu-id="396bb-145">キューに個々のユーザーまたはグループを追加する場合は、[ユーザーとグループの選択 **] オプションを選択** します。</span><span class="sxs-lookup"><span data-stu-id="396bb-145">If you want to add individual users or groups to the queue, select the **Choose users and groups** option.</span></span> 

<span data-ttu-id="396bb-146">キューにユーザーを追加するには、[ユーザーの追加]**をクリック** し、ユーザーを検索し、[追加] をクリックして、[追加] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="396bb-146">To add a user to the queue, click **Add users**, search for the user, click **Add**, and then click **Add**.</span></span>

<span data-ttu-id="396bb-147">キューにグループを追加するには、[グループの追加]**をクリック** し、グループを検索し、[追加] をクリックして、[追加] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="396bb-147">To add a group to the queue, click **Add groups**, search for the group, click **Add**, and then click **Add**.</span></span> <span data-ttu-id="396bb-148">配布リスト、セキュリティ グループ、およびグループまたはチームMicrosoft 365使用Microsoft Teamsできます。</span><span class="sxs-lookup"><span data-stu-id="396bb-148">You can use distribution lists, security groups, and Microsoft 365 groups or Microsoft Teams teams.</span></span>

> [!NOTE]
> <span data-ttu-id="396bb-149">グループに追加された新しいユーザーは、最初の呼び出しが到着するために最大 8 時間かかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="396bb-149">New users added to a group can take up to eight hours for their first call to arrive.</span></span>

### <a name="call-routing"></a><span data-ttu-id="396bb-150">通話ルーティング</span><span class="sxs-lookup"><span data-stu-id="396bb-150">Call routing</span></span>

![電話会議モードとルーティング方法の設定のスクリーンショット](media/call-queue-conference-mode-routing-method.png)

<span data-ttu-id="396bb-152">**電話会議モード** では、エージェントが呼び出しを受け入れてから、呼び出し元がエージェントに接続するのにかかる時間が大幅に短縮されます。</span><span class="sxs-lookup"><span data-stu-id="396bb-152">**Conference mode** significantly reduces the amount of time it takes for a caller to be connected to an agent, after the agent accepts the call.</span></span> <span data-ttu-id="396bb-153">電話会議モードを機能するには、通話キュー内のエージェントが次のいずれかのクライアントを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="396bb-153">For conference mode to work, agents in the call queue must use one of the following clients:</span></span>

  - <span data-ttu-id="396bb-154">デスクトップ クライアント、Android Microsoft Teams iOS アプリの最新バージョン</span><span class="sxs-lookup"><span data-stu-id="396bb-154">The latest version of the Microsoft Teams desktop client, Android app, or iOS app</span></span>
  - <span data-ttu-id="396bb-155">Microsoft Teamsバージョン 1449/1.0.94.2020051601 以降</span><span class="sxs-lookup"><span data-stu-id="396bb-155">Microsoft Teams phone version 1449/1.0.94.2020051601 or later</span></span>
  
<span data-ttu-id="396bb-156">エージェントのTeamsアカウントは、Teamsモードに設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="396bb-156">Agents' Teams accounts need to be set to Teams-only mode.</span></span> <span data-ttu-id="396bb-157">要件を満たしていないエージェントは、通話ルーティングの一覧には含まれません。</span><span class="sxs-lookup"><span data-stu-id="396bb-157">Agents who don't meet the requirements aren't included in the call routing list.</span></span> <span data-ttu-id="396bb-158">エージェントが互換性のあるクライアントを使用している場合は、通話キューの会議モードを有効にすることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="396bb-158">We recommend enabling conference mode for your call queues if your agents are all using compatible clients.</span></span>

> [!NOTE]
> <span data-ttu-id="396bb-159">電話呼び出しが、場所ベースのルーティングが有効になっているダイレクト ルーティング ゲートウェイからキューにルーティングされる場合、電話会議モードはサポートされません。</span><span class="sxs-lookup"><span data-stu-id="396bb-159">Conference mode is not supported if phone calls are routed to the queue from a Direct Routing gateway that is enabled for Location Based Routing.</span></span>

<span data-ttu-id="396bb-160">**ルーティング方法は** 、エージェントがキューから呼び出しを受信する順序を決定します。</span><span class="sxs-lookup"><span data-stu-id="396bb-160">**Routing method** determines the order in which agents receive calls from the queue.</span></span> <span data-ttu-id="396bb-161">次のオプションから選択します。</span><span class="sxs-lookup"><span data-stu-id="396bb-161">Choose from these options:</span></span>

- <span data-ttu-id="396bb-162">**アテンダント** ルーティングでは、キュー内のすべてのエージェントが同時に呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="396bb-162">**Attendant routing** rings all agents in the queue at the same time.</span></span> <span data-ttu-id="396bb-163">呼び出しを受け取る最初の呼び出しエージェントが呼び出しを取得します。</span><span class="sxs-lookup"><span data-stu-id="396bb-163">The first call agent to pick up the call gets the call.</span></span>

- <span data-ttu-id="396bb-164">**シリアル ルーティングでは** 、すべての呼び出しエージェントが[通話エージェント] の一覧で指定された順序 **で 1 つ 1 つリング** されます。</span><span class="sxs-lookup"><span data-stu-id="396bb-164">**Serial routing** rings all call agents one by one in the order specified in the **Call agents** list.</span></span> <span data-ttu-id="396bb-165">エージェントが通話を閉じ、または呼び出しを受け取らない場合、呼び出しは次のエージェントを呼び出し、エージェントが取り出されるか、または時間が切れるまですべてのエージェントを試します。</span><span class="sxs-lookup"><span data-stu-id="396bb-165">If an agent dismisses or does not pick up a call, the call will ring the next agent and will try all agents until it is picked up or times out.</span></span>

- <span data-ttu-id="396bb-166">**ラウンド ロビンは** 、着信呼び出しのルーティングのバランスを取り、各呼び出しエージェントがキューから同じ数の呼び出しを取得します。</span><span class="sxs-lookup"><span data-stu-id="396bb-166">**Round robin** balances the routing of incoming calls so that each call agent gets the same number of calls from the queue.</span></span> <span data-ttu-id="396bb-167">これは、すべての通話エージェント間で均等な機会を確保するために、受信販売環境で望ましい場合があります。</span><span class="sxs-lookup"><span data-stu-id="396bb-167">This may be desirable in an inbound sales environment to assure equal opportunity among all the call agents.</span></span>

- <span data-ttu-id="396bb-168">**アイドル時間が** 最も長いエージェントに各呼び出しをルーティングします。</span><span class="sxs-lookup"><span data-stu-id="396bb-168">**Longest idle** routes each call to the agent who has been idle the longest time.</span></span> <span data-ttu-id="396bb-169">エージェントのプレゼンス状態が [使用可能] の場合、またはプレゼンス状態が 10 分未満の場合、エージェントはアイドル状態と見なされます。</span><span class="sxs-lookup"><span data-stu-id="396bb-169">An agent is considered idle if their presence state is Available or if their presence state has been Away for less than 10 minutes.</span></span> <span data-ttu-id="396bb-170">プレゼンス状態が 10 分を超える状態のエージェントはアイドル状態とは見なされません。プレゼンスを [利用可能] に変更するまで、通話を受信する資格は得られません。</span><span class="sxs-lookup"><span data-stu-id="396bb-170">Agents whose presence state has been Away for more than 10 minutes are not considered idle and will not be eligible to receive calls until they change their presence to Available.</span></span> 

![ルーティング、オプトアウト、アラート時間の設定のスクリーンショット](media/call-queue-presence-agents-time.png)


<span data-ttu-id="396bb-172">**プレゼンス ベースのルーティングでは** 、呼び出しエージェントの可用性状態を使用して、選択したルーティング方法の呼び出しルーティング リストにエージェントを含める必要があるかどうかを判断します。</span><span class="sxs-lookup"><span data-stu-id="396bb-172">**Presence-based routing** uses the availability status of call agents to determine whether an agent should be included in the call routing list for the selected routing method.</span></span> <span data-ttu-id="396bb-173">可用性の状態が [使用可能] に設定されている通話エージェント **は、通話** ルーティング リストに含まれており、通話を受信できます。</span><span class="sxs-lookup"><span data-stu-id="396bb-173">Call agents whose availability status is set to **Available** are included in the call routing list and can receive calls.</span></span> <span data-ttu-id="396bb-174">可用性の状態が他の状態に設定されているエージェントは、通話ルーティング リストから除外され、可用性の状態が [利用可能] に戻るまで、呼び出しを受信 **しません**。</span><span class="sxs-lookup"><span data-stu-id="396bb-174">Agents whose availability status is set to any other status are excluded from the call routing list and won't receive calls until their availability status changes back to **Available**.</span></span> 

<span data-ttu-id="396bb-175">プレゼンス ベースの呼び出しルーティングは、任意のルーティング方法で有効にできます。</span><span class="sxs-lookup"><span data-stu-id="396bb-175">You can enable presence-based call routing with any of the routing methods.</span></span>

<span data-ttu-id="396bb-176">エージェントが呼び出しを受け取らない場合、エージェントは、可用性の状態が設定されているに関係なく、通話ルーティング リストに含まれません。</span><span class="sxs-lookup"><span data-stu-id="396bb-176">If an agent opts out of getting calls, they won't be included in the call routing list regardless of what their availability status is set to.</span></span> 

> [!NOTE]
> <span data-ttu-id="396bb-177">プレゼンス ベースのルーティングSkype for Business、クライアントを使用するエージェントは、呼び出しルーティング の一覧に含まれません。</span><span class="sxs-lookup"><span data-stu-id="396bb-177">Agents who use the Skype for Business client aren't included in the call routing list when presence-based routing is enabled.</span></span> <span data-ttu-id="396bb-178">このサービスを使用するエージェントSkype for Business、プレゼンス ベースの呼び出しルーティングを有効にすることはできません。</span><span class="sxs-lookup"><span data-stu-id="396bb-178">If you have agents who use Skype for Business, don't enable presence-based call routing.</span></span>

<span data-ttu-id="396bb-179">**エージェント アラート時間は** 、キューが呼び出しを次のエージェントにリダイレクトする前に、エージェントの電話が鳴る時間を指定します。</span><span class="sxs-lookup"><span data-stu-id="396bb-179">**Agent alert time** specifies how long an agent's phone will ring before the queue redirects the call to the next agent.</span></span>

<span data-ttu-id="396bb-180">次の設定をお勧めします。</span><span class="sxs-lookup"><span data-stu-id="396bb-180">The following settings are recommended:</span></span>

- <span data-ttu-id="396bb-181">**会議モードから\*\*\*\*自動**</span><span class="sxs-lookup"><span data-stu-id="396bb-181">**Conference mode** to **Auto**</span></span>
- <span data-ttu-id="396bb-182">**ラウンド ロビンまたは\*\*\*\*最長アイドルへの\*\*\*\*ルーティング方法**</span><span class="sxs-lookup"><span data-stu-id="396bb-182">**Routing method** to **Round robin** or **Longest idle**</span></span>
- <span data-ttu-id="396bb-183">**プレゼンス ベースのルーティングを** **[オン] に設定する**</span><span class="sxs-lookup"><span data-stu-id="396bb-183">**Presence-based routing** to **On**</span></span>
- <span data-ttu-id="396bb-184">**エージェントのアラート時間:** **~ 20 秒**</span><span class="sxs-lookup"><span data-stu-id="396bb-184">**Agent alert time:** to **20 seconds**</span></span>

> [!NOTE]
> <span data-ttu-id="396bb-185">プレゼンス ベースのルーティングが有効ではなく、キュー内に複数の呼び出しがある場合、システムは、プレゼンス状態に関係なく、これらの呼び出しをエージェントに同時に表示します。</span><span class="sxs-lookup"><span data-stu-id="396bb-185">If presence-based routing is not enabled and there are multiple calls in the queue, the system will present these calls simultaneously to the agents regardless of their presence status.</span></span> <span data-ttu-id="396bb-186">これにより、エージェントに対する複数の呼び出し通知が発生します。特に、一部のエージェントがエージェントに提示された最初の呼び出しに応答しない場合。</span><span class="sxs-lookup"><span data-stu-id="396bb-186">This will result in multiple call notifications to agents, particularly if some agents don’t answer the initial call presented to them.</span></span>

### <a name="call-overflow-handling"></a><span data-ttu-id="396bb-187">呼び出しオーバーフロー処理</span><span class="sxs-lookup"><span data-stu-id="396bb-187">Call overflow handling</span></span>

![呼び出しオーバーフロー設定のスクリーンショット](media/call-queue-overflow-handling.png)

<span data-ttu-id="396bb-189">**キュー内の最大呼び** 出し数は、特定の時点でキュー内で待機できる呼び出しの最大数を指定します。</span><span class="sxs-lookup"><span data-stu-id="396bb-189">**Maximum calls in the queue** specifies the maximum number of calls that can wait in the queue at any given time.</span></span> <span data-ttu-id="396bb-190">既定値は 50 ですが、0 ~ 200 の範囲で指定できます。</span><span class="sxs-lookup"><span data-stu-id="396bb-190">The default is 50, but it can range from 0 to 200.</span></span> <span data-ttu-id="396bb-191">この制限に達すると、呼び出しは [呼び出しの最大数に達した場合] 設定で指定された **方法で処理** されます。</span><span class="sxs-lookup"><span data-stu-id="396bb-191">When this limit is reached, the call is handled as specified by the **When the maximum number of calls is reached** setting.</span></span>

<span data-ttu-id="396bb-192">通話を切断するか、任意の通話ルーティング先にリダイレクトすることができます。</span><span class="sxs-lookup"><span data-stu-id="396bb-192">You can choose to disconnect the call or redirect it to any of the call routing destinations.</span></span> <span data-ttu-id="396bb-193">たとえば、発信者にキュー内のエージェントのボイスメールを残す場合があります。</span><span class="sxs-lookup"><span data-stu-id="396bb-193">For example, you might have the caller leave a voicemail for the agents in the queue.</span></span> <span data-ttu-id="396bb-194">外部転送については、「前提条件」と[](plan-auto-attendant-call-queue.md#prerequisites)「外部電話番号の転送 - 番号の書式設定に関[する技術的な詳細](create-a-phone-system-auto-attendant.md#external-phone-number-transfers---technical-details)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="396bb-194">For external transfers, please refer to [Prerequisites](plan-auto-attendant-call-queue.md#prerequisites) and the [external phone number transfers - technical details](create-a-phone-system-auto-attendant.md#external-phone-number-transfers---technical-details) for number formatting.</span></span>

> [!NOTE]
> <span data-ttu-id="396bb-195">呼び出しの最大数が 0 に設定されている場合、あいさつメッセージは再生されません。</span><span class="sxs-lookup"><span data-stu-id="396bb-195">If the maximum number of calls is set to 0 then the greeting message will not play.</span></span>

### <a name="call-timeout-handling"></a><span data-ttu-id="396bb-196">呼び出しタイムアウト処理</span><span class="sxs-lookup"><span data-stu-id="396bb-196">Call timeout handling</span></span>

![通話タイムアウト設定のスクリーンショット](media/call-queue-timeout-handling.png)

<span data-ttu-id="396bb-198">**呼び出** しタイムアウト: 最大待機時間は、呼び出しがリダイレクトまたは切断される前にキューで保留にできる最大時間を指定します。</span><span class="sxs-lookup"><span data-stu-id="396bb-198">**Call Timeout: maximum wait time** specifies the maximum time a call can be on hold in the queue before it is redirected or disconnected.</span></span> <span data-ttu-id="396bb-199">0 秒から 45 分の値を指定できます。</span><span class="sxs-lookup"><span data-stu-id="396bb-199">You can specify a value from 0 seconds to 45 minutes.</span></span>

<span data-ttu-id="396bb-200">通話を切断するか、または通話ルーティング先の 1 つにリダイレクトすることができます。</span><span class="sxs-lookup"><span data-stu-id="396bb-200">You can choose to disconnect the call or redirect it to one of the call routing destinations.</span></span> <span data-ttu-id="396bb-201">たとえば、発信者にキュー内のエージェントのボイスメールを残す場合があります。</span><span class="sxs-lookup"><span data-stu-id="396bb-201">For example, you might have the caller leave a voicemail for the agents in the queue.</span></span> <span data-ttu-id="396bb-202">外部転送については、「前提条件」と[](plan-auto-attendant-call-queue.md#prerequisites)「外部電話番号の転送 - 番号の書式設定に関[する技術的な詳細](create-a-phone-system-auto-attendant.md#external-phone-number-transfers---technical-details)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="396bb-202">For external transfers, please refer to [Prerequisites](plan-auto-attendant-call-queue.md#prerequisites) and the [external phone number transfers - technical details](create-a-phone-system-auto-attendant.md#external-phone-number-transfers---technical-details) for number formatting.</span></span>

<span data-ttu-id="396bb-203">通話タイムアウト オプションを選択した後、[保存] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="396bb-203">When you have selected your call timeout options, click **Save**.</span></span>

## <a name="caller-id-for-outbound-calls"></a><span data-ttu-id="396bb-204">発信呼び出しの呼び出し元 ID</span><span class="sxs-lookup"><span data-stu-id="396bb-204">Caller ID for outbound calls</span></span>

<span data-ttu-id="396bb-205">通話キュー内のエージェントはダイヤルアウトして顧客の通話を返す可能性があります。通話キューのメンバーの発信者番号を適切な自動応答のサービス番号に設定します。</span><span class="sxs-lookup"><span data-stu-id="396bb-205">Since agents in a call queue may dial out to return a customer call, consider setting the caller ID for members of a call queue to the service number of an appropriate auto attendant.</span></span> <span data-ttu-id="396bb-206">詳細[については、「Microsoft Teams で](caller-id-policies.md)発信者番号ポリシーを管理する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="396bb-206">See [Manage caller ID policies in Microsoft Teams](caller-id-policies.md) for more information.</span></span>

## <a name="supported-clients"></a><span data-ttu-id="396bb-207">サポートされるクライアント</span><span class="sxs-lookup"><span data-stu-id="396bb-207">Supported clients</span></span>

<span data-ttu-id="396bb-208">呼び出しキュー内の呼び出しエージェントでは、次のクライアントがサポートされます。</span><span class="sxs-lookup"><span data-stu-id="396bb-208">The following clients are supported for call agents in a call queue:</span></span>

  - <span data-ttu-id="396bb-209">Skype for Business クライアント 2016 (32 ビット版と 64 ビット版)</span><span class="sxs-lookup"><span data-stu-id="396bb-209">Skype for Business desktop client 2016 (32-bit and 64-bit versions)</span></span>
  - <span data-ttu-id="396bb-210">Lync デスクトップ クライアント 2013 (32 ビット版と 64 ビット版)</span><span class="sxs-lookup"><span data-stu-id="396bb-210">Lync desktop client 2013 (32-bit and 64-bit versions)</span></span>
  - <span data-ttu-id="396bb-211">すべての IP 電話モデルは、Microsoft Teams。</span><span class="sxs-lookup"><span data-stu-id="396bb-211">All IP phone models supported for Microsoft Teams.</span></span> <span data-ttu-id="396bb-212">[「Getting phones for Skype for Business Online 」を参照してください](/skypeforbusiness/what-is-phone-system-in-office-365/getting-phones-for-skype-for-business-online/getting-phones-for-skype-for-business-online)。</span><span class="sxs-lookup"><span data-stu-id="396bb-212">See [Getting phones for Skype for Business Online](/skypeforbusiness/what-is-phone-system-in-office-365/getting-phones-for-skype-for-business-online/getting-phones-for-skype-for-business-online).</span></span>
  - <span data-ttu-id="396bb-213">Mac版  Skype for Business クライアント (バージョン 16.8.196 以降)</span><span class="sxs-lookup"><span data-stu-id="396bb-213">Mac Skype for Business Client (version 16.8.196 and later)</span></span>
  - <span data-ttu-id="396bb-214">Aandroid Skype for Business クライアント (バージョン 6.16.0.9 以降)</span><span class="sxs-lookup"><span data-stu-id="396bb-214">Android Skype for Business Client (version 6.16.0.9 and later)</span></span>
  - <span data-ttu-id="396bb-215">iPhone Skype for Business Client クライアント(バージョン 6.16.0 以降)</span><span class="sxs-lookup"><span data-stu-id="396bb-215">iPhone Skype for Business Client (version 6.16.0 and later)</span></span>
  - <span data-ttu-id="396bb-216">Mac版  Skype for Business クライアント (バージョン 6.16.0 以降)</span><span class="sxs-lookup"><span data-stu-id="396bb-216">iPad Skype for Business Client (version 6.16.0 and later)</span></span>
  - <span data-ttu-id="396bb-217">Microsoft Teams Windows クライアント (32 ビットおよび 64 ビット バージョン)</span><span class="sxs-lookup"><span data-stu-id="396bb-217">Microsoft Teams Windows client (32-bit and 64-bit versions)</span></span>
  - <span data-ttu-id="396bb-218">Microsoft Teams Mac クライアント</span><span class="sxs-lookup"><span data-stu-id="396bb-218">Microsoft Teams Mac client</span></span>
  - <span data-ttu-id="396bb-219">Microsoft Teams[デスクトップ インフラストラクチャ](/microsoftteams/teams-for-vdi)(Windows Virtual Desktop、Citrix、VMware) に関するページ</span><span class="sxs-lookup"><span data-stu-id="396bb-219">Microsoft Teams on [Virtualized Desktop Infrastructure](/microsoftteams/teams-for-vdi) (Windows Virtual Desktop, Citrix, and VMware)</span></span>
  - <span data-ttu-id="396bb-220">Microsoft Teams iPhone アプリ</span><span class="sxs-lookup"><span data-stu-id="396bb-220">Microsoft Teams iPhone app</span></span>
  - <span data-ttu-id="396bb-221">Microsoft Teams Android アプリ</span><span class="sxs-lookup"><span data-stu-id="396bb-221">Microsoft Teams Android app</span></span>

    > [!NOTE]
    > <span data-ttu-id="396bb-222">直接ルーティング番号が割り当てられた通話キューは、クライアント、Lync クライアント、Skype for Business IP Phone をエージェントSkype for Businessサポートしません。</span><span class="sxs-lookup"><span data-stu-id="396bb-222">Call queues that are assigned a direct routing number don't support Skype for Business clients, Lync clients, or Skype for Business IP Phones as agents.</span></span>

## <a name="call-queue-cmdlets"></a><span data-ttu-id="396bb-223">通話キューのコマンドレット</span><span class="sxs-lookup"><span data-stu-id="396bb-223">Call queue cmdlets</span></span>

<span data-ttu-id="396bb-224">Windows PowerShell を使用して通話キューを作成し、設定することもできます。</span><span class="sxs-lookup"><span data-stu-id="396bb-224">You can also use Windows PowerShell to create and set up call queues.</span></span> <span data-ttu-id="396bb-225">呼び出しキューの管理に使用するコマンドレットを次に示します。</span><span class="sxs-lookup"><span data-stu-id="396bb-225">Here are the cmdlets that you use to manage a call queue.</span></span>

- [<span data-ttu-id="396bb-226">New-CsCallQueue</span><span class="sxs-lookup"><span data-stu-id="396bb-226">New-CsCallQueue</span></span>](/powershell/module/skype/new-CsCallQueue)

- [<span data-ttu-id="396bb-227">Set-CsCallQueue</span><span class="sxs-lookup"><span data-stu-id="396bb-227">Set-CsCallQueue</span></span>](/powershell/module/skype/set-CsCallQueue)

- [<span data-ttu-id="396bb-228">Get-CsCallQueue</span><span class="sxs-lookup"><span data-stu-id="396bb-228">Get-CsCallQueue</span></span>](/powershell/module/skype/get-CsCallQueue)

- [<span data-ttu-id="396bb-229">Remove-CsCallQueue</span><span class="sxs-lookup"><span data-stu-id="396bb-229">Remove-CsCallQueue</span></span>](/powershell/module/skype/remove-CsCallQueue)

## <a name="related-topics"></a><span data-ttu-id="396bb-230">関連項目</span><span class="sxs-lookup"><span data-stu-id="396bb-230">Related topics</span></span>

[<span data-ttu-id="396bb-231">電話システムで利用できる機能</span><span class="sxs-lookup"><span data-stu-id="396bb-231">Here's what you get with Phone System</span></span>](here-s-what-you-get-with-phone-system.md)

[<span data-ttu-id="396bb-232">サービス電話番号を取得する</span><span class="sxs-lookup"><span data-stu-id="396bb-232">Getting service phone numbers</span></span>](getting-service-phone-numbers.md)

[<span data-ttu-id="396bb-233">国および地域ごとの電話会議および通話プランの利用可能性</span><span class="sxs-lookup"><span data-stu-id="396bb-233">Country and region availability for Audio Conferencing and Calling Plans</span></span>](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)

[<span data-ttu-id="396bb-234">New-CsOnlineApplicationInstance</span><span class="sxs-lookup"><span data-stu-id="396bb-234">New-CsOnlineApplicationInstance</span></span>](/powershell/module/skype/new-csonlineapplicationinstance)

[<span data-ttu-id="396bb-235">Windows PowerShell と Skype for Business Online の概要</span><span class="sxs-lookup"><span data-stu-id="396bb-235">An introduction to Windows PowerShell and Skype for Business Online</span></span>](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)
