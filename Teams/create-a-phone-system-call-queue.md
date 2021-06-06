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
ms.openlocfilehash: fe0c2863c627f728f5418cfeb9b7b17c91d246fa
ms.sourcegitcommit: 17d0108fb4d36a3f56144460683f53d77a8a0a7f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/05/2021
ms.locfileid: "52777928"
---
# <a name="create-a-call-queue"></a><span data-ttu-id="aaddd-103">呼び出しキューを作成する</span><span class="sxs-lookup"><span data-stu-id="aaddd-103">Create a call queue</span></span>

<span data-ttu-id="aaddd-104">通話キューは、特定の問題や質問に役立つ組織内のユーザーに発信者をルーティングする方法を提供します。</span><span class="sxs-lookup"><span data-stu-id="aaddd-104">Call queues provide a method of routing callers to people in your organization who can help with a particular issue or question.</span></span> <span data-ttu-id="aaddd-105">呼び出しは、キュー内のユーザー (エージェントと呼ばれる) に一度に 1 回 *配布されます*。</span><span class="sxs-lookup"><span data-stu-id="aaddd-105">Calls are distributed one at a time to the people in the queue (who are known as *agents*).</span></span> 

> [!TIP]
> <span data-ttu-id="aaddd-106">この記事は大規模な組織向けです。</span><span class="sxs-lookup"><span data-stu-id="aaddd-106">This article is for large organizations.</span></span> <span data-ttu-id="aaddd-107">組織が小規模企業の場合は、「通話キューの作成 - 代わりに小規模ビジネス向け [チュートリアル」を](/microsoftteams/business-voice/create-a-phone-system-call-queue-smb) 参照してください。</span><span class="sxs-lookup"><span data-stu-id="aaddd-107">If your organization is a small business, read [Create a call queue - small business tutorial](/microsoftteams/business-voice/create-a-phone-system-call-queue-smb) instead.</span></span>

<span data-ttu-id="aaddd-108">呼び出しキューには、次の機能があります。</span><span class="sxs-lookup"><span data-stu-id="aaddd-108">Call queues provide:</span></span>

- <span data-ttu-id="aaddd-109">あいさつメッセージ。</span><span class="sxs-lookup"><span data-stu-id="aaddd-109">A greeting message.</span></span>

- <span data-ttu-id="aaddd-110">ユーザーがキューで保留を待機している間の音楽。</span><span class="sxs-lookup"><span data-stu-id="aaddd-110">Music while people are waiting on hold in a queue.</span></span>

- <span data-ttu-id="aaddd-111">コール ルーティング - *First In,First Out* (FIFO) order - to agents.</span><span class="sxs-lookup"><span data-stu-id="aaddd-111">Call routing - in *First In, First Out* (FIFO) order - to agents.</span></span>

- <span data-ttu-id="aaddd-112">キューのオーバーフローとタイムアウトの処理オプション。</span><span class="sxs-lookup"><span data-stu-id="aaddd-112">Handling options for queue overflow and timeout.</span></span>

<span data-ttu-id="aaddd-113">この記事の手順に従う前に[、「Teams](plan-auto-attendant-call-queue.md)自動応答と通話キューの計画」を[](plan-auto-attendant-call-queue.md#getting-started)読み、概要の手順に従ってください。</span><span class="sxs-lookup"><span data-stu-id="aaddd-113">Be sure you have read [Plan for Teams auto attendants and call queues](plan-auto-attendant-call-queue.md) and followed the [getting started steps](plan-auto-attendant-call-queue.md#getting-started) before you follow the procedures in this article.</span></span>

## <a name="video-demonstration"></a><span data-ttu-id="aaddd-114">ビデオデモ</span><span class="sxs-lookup"><span data-stu-id="aaddd-114">Video demonstration</span></span>

<span data-ttu-id="aaddd-115">このビデオでは、通話キューを作成する方法の基本的な例をTeams。</span><span class="sxs-lookup"><span data-stu-id="aaddd-115">This video shows a basic example of how to create a call queue in Teams.</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RWCF23?autoplay=false]

## <a name="create-the-call-queue"></a><span data-ttu-id="aaddd-116">呼び出しキューを作成する</span><span class="sxs-lookup"><span data-stu-id="aaddd-116">Create the call queue</span></span>

<span data-ttu-id="aaddd-117">通話キューを設定するには、Teams 管理センターで、[音声] を展開し、[通話キュー] をクリックし、[追加] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="aaddd-117">To set up a call queue, in the Teams admin center, expand **Voice**, click **Call queues**, and then click **Add**.</span></span>

<span data-ttu-id="aaddd-118">通話キューの名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="aaddd-118">Type a name for the call queue.</span></span>

### <a name="resource-accounts"></a><span data-ttu-id="aaddd-119">リソース アカウント</span><span class="sxs-lookup"><span data-stu-id="aaddd-119">Resource accounts</span></span>

![リソース アカウント設定のスクリーンショット](media/call-queue-name-language.png)

<span data-ttu-id="aaddd-121">[**アカウントの追加]** をクリックし、この呼び出しキューで使用するリソースアカウントを検索し、[追加] をクリックして、[追加] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="aaddd-121">Click **Add accounts**, search for the resource account that you want to use with this call queue, click **Add**, and then click **Add**.</span></span> <span data-ttu-id="aaddd-122">(エージェントは、着信呼び出しを受信すると、リソース アカウント名を表示します)。</span><span class="sxs-lookup"><span data-stu-id="aaddd-122">(Agents will see the resource account name when they receive an incoming call.)</span></span>

### <a name="assign-calling-id"></a><span data-ttu-id="aaddd-123">呼び出し元 ID を割り当てる</span><span class="sxs-lookup"><span data-stu-id="aaddd-123">Assign calling ID</span></span>

![呼び出し元 ID 設定のスクリーンショット](media/call-queue-assign-calling-id.png)

<span data-ttu-id="aaddd-125">通話エージェントに Teams チャネルを使用する場合は、電話番号で 1 つ以上のリソース アカウントを指定することで、エージェントの発信発信者番号を割り当てできます。</span><span class="sxs-lookup"><span data-stu-id="aaddd-125">If you plan to use a Teams channel for your call agents, you can assign an outbound caller ID number for the agents by specifying one or more resource accounts with a phone number.</span></span>

<span data-ttu-id="aaddd-126">[**追加]** をクリックし、エージェントが発信呼び出しを行う際に ID を呼び出す目的で許可するリソース アカウントを検索し、[追加] をクリックし、[追加] をクリック **します**。</span><span class="sxs-lookup"><span data-stu-id="aaddd-126">Click **Add**, search for the resource accounts that you want to allow agents to for calling ID purposes when making outbound calls, click **Add**, and then click **Add**.</span></span>

<span data-ttu-id="aaddd-127">エージェント メンバーシップを制御するために Teams チャネルを使用していない場合は、通話キューのメンバーの発信者番号を、通話キューのサービス番号または適切な自動応答に直接設定してください。</span><span class="sxs-lookup"><span data-stu-id="aaddd-127">If you are not using a Teams channel to control agent membership, consider directly setting the caller ID for members of the call queue to the service number of the call queue or appropriate auto attendant.</span></span> <span data-ttu-id="aaddd-128">詳細[については、「Microsoft Teams で](caller-id-policies.md)発信者番号ポリシーを管理する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="aaddd-128">See [Manage caller ID policies in Microsoft Teams](caller-id-policies.md) for more information.</span></span>

### <a name="language"></a><span data-ttu-id="aaddd-129">言語</span><span class="sxs-lookup"><span data-stu-id="aaddd-129">Language</span></span>

![言語設定のスクリーンショット](media/call-queue-language.png)

<span data-ttu-id="aaddd-131">サポートされている [言語を選択します](create-a-phone-system-call-queue-languages.md)。</span><span class="sxs-lookup"><span data-stu-id="aaddd-131">Choose a [supported language](create-a-phone-system-call-queue-languages.md).</span></span> <span data-ttu-id="aaddd-132">この言語は、システムで生成された音声プロンプトとボイスメールのトランスクリプション (有効にした場合) に使用されます。</span><span class="sxs-lookup"><span data-stu-id="aaddd-132">This language will be used for system-generated voice prompts and voicemail transcription (if you enable them).</span></span>

### <a name="greetings-and-music-on-hold-in-queue"></a><span data-ttu-id="aaddd-133">キュー内の応答メッセージと保留音</span><span class="sxs-lookup"><span data-stu-id="aaddd-133">Greetings and music on hold in queue</span></span>

![キュー設定でのあいさつメッセージと保留音のスクリーンショット](media/call-queue-greetings-music.png)

<span data-ttu-id="aaddd-135">発信者がキューに到着するときに、発信者にあいさつメッセージを再生する場合に指定します。</span><span class="sxs-lookup"><span data-stu-id="aaddd-135">Specify if you want to play a greeting to callers when they arrive in the queue.</span></span> <span data-ttu-id="aaddd-136">再生するあいさつメッセージを含む MP3、WAV、または WMA ファイルをアップロードする必要があります。</span><span class="sxs-lookup"><span data-stu-id="aaddd-136">You must upload an MP3, WAV, or WMA file containing the greeting that you want to play.</span></span>

<span data-ttu-id="aaddd-137">Teamsキュー内で保留されている間、呼び出し元に既定の音楽を提供します。</span><span class="sxs-lookup"><span data-stu-id="aaddd-137">Teams provides default music to callers while they are on hold in a queue.</span></span> <span data-ttu-id="aaddd-138">特定のオーディオ ファイルを再生する場合は、[オーディオ ファイルの再生] を選択し、MP3、WAV、または WMA ファイルをアップロードします。</span><span class="sxs-lookup"><span data-stu-id="aaddd-138">If you want to play a specific audio file, choose **Play an audio file** and upload an MP3, WAV, or WMA file.</span></span>

> [!NOTE]
> <span data-ttu-id="aaddd-139">アップロードされた記録は 5 MB 以下にできます。</span><span class="sxs-lookup"><span data-stu-id="aaddd-139">The uploaded recording can be no larger than 5 MB.</span></span>
> <span data-ttu-id="aaddd-140">通話キューで提供される既定Teamsは、組織が支払う使用料金は無料です。</span><span class="sxs-lookup"><span data-stu-id="aaddd-140">The default music supplied in Teams call queues is free of any royalties payable by your organization.</span></span> 

### <a name="call-agents"></a><span data-ttu-id="aaddd-141">エージェントの呼び出し</span><span class="sxs-lookup"><span data-stu-id="aaddd-141">Call agents</span></span>

<span data-ttu-id="aaddd-142">エージェントを [呼び出しキューに追加するための前提条件を確認します](plan-auto-attendant-call-queue.md#prerequisites)。</span><span class="sxs-lookup"><span data-stu-id="aaddd-142">Review the [prerequisites for adding agents to a call queue](plan-auto-attendant-call-queue.md#prerequisites).</span></span>

![通話キューのユーザーとグループの設定のスクリーンショット](media/call-queue-users-groups.png)

##### <a name="teams-channel"></a><span data-ttu-id="aaddd-144">Teams チャネル</span><span class="sxs-lookup"><span data-stu-id="aaddd-144">Teams channel</span></span>

<span data-ttu-id="aaddd-145">1 つのチャネルを介して最大 200 のエージェントTeamsできます。</span><span class="sxs-lookup"><span data-stu-id="aaddd-145">You can add up to 200 agents via a Teams channel.</span></span>

<span data-ttu-id="aaddd-146">キューを管理するために [Teamsを使用する](https://support.microsoft.com/office/9f07dabe-91c6-4a9b-a545-8ffdddd2504e)場合は、[チームの選択] オプションを選択し、[チャネルの追加 **] をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="aaddd-146">If you want to [use a Teams channel to manage the queue](https://support.microsoft.com/office/9f07dabe-91c6-4a9b-a545-8ffdddd2504e), select the **Choose a team** option and click **Add a channel**.</span></span> <span data-ttu-id="aaddd-147">使用するチームを検索して選択し、[追加] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="aaddd-147">Search for the team that you want to use, select it, and click **Add**.</span></span> <span data-ttu-id="aaddd-148">使用するチャネルを選択し、[適用] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="aaddd-148">Select the channel that you want to use and click **Apply**.</span></span>

<span data-ttu-id="aaddd-149">次のクライアントは、呼び出しキューにTeamsチャネルを使用する場合にサポートされます。</span><span class="sxs-lookup"><span data-stu-id="aaddd-149">The following clients are supported when using a Teams channel for call queues:</span></span> 

  - <span data-ttu-id="aaddd-150">Microsoft Teams Windows クライアント</span><span class="sxs-lookup"><span data-stu-id="aaddd-150">Microsoft Teams Windows client</span></span>
  - <span data-ttu-id="aaddd-151">Microsoft Teams Mac クライアント</span><span class="sxs-lookup"><span data-stu-id="aaddd-151">Microsoft Teams Mac client</span></span>

##### <a name="users-and-groups"></a><span data-ttu-id="aaddd-152">ユーザーとグループ</span><span class="sxs-lookup"><span data-stu-id="aaddd-152">Users and groups</span></span>

<span data-ttu-id="aaddd-153">最大 20 個のエージェントを個別に追加し、最大 200 個のエージェントをグループ経由で追加できます。</span><span class="sxs-lookup"><span data-stu-id="aaddd-153">You can add up to 20 agents individually and up to 200 agents via groups.</span></span>

<span data-ttu-id="aaddd-154">キューに個々のユーザーまたはグループを追加する場合は、[ユーザーとグループの選択 **] オプションを選択** します。</span><span class="sxs-lookup"><span data-stu-id="aaddd-154">If you want to add individual users or groups to the queue, select the **Choose users and groups** option.</span></span> 

<span data-ttu-id="aaddd-155">キューにユーザーを追加するには、[ユーザーの追加]**をクリック** し、ユーザーを検索し、[追加] をクリックして、[追加] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="aaddd-155">To add a user to the queue, click **Add users**, search for the user, click **Add**, and then click **Add**.</span></span>

<span data-ttu-id="aaddd-156">キューにグループを追加するには、[グループの追加]**をクリック** し、グループを検索し、[追加] をクリックして、[追加] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="aaddd-156">To add a group to the queue, click **Add groups**, search for the group, click **Add**, and then click **Add**.</span></span> <span data-ttu-id="aaddd-157">配布リスト、セキュリティ グループ、およびグループまたはチームMicrosoft 365使用Microsoft Teamsできます。</span><span class="sxs-lookup"><span data-stu-id="aaddd-157">You can use distribution lists, security groups, and Microsoft 365 groups or Microsoft Teams teams.</span></span>

> [!NOTE]
> <span data-ttu-id="aaddd-158">グループに追加された新しいユーザーは、最初の呼び出しが到着するために最大 8 時間かかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="aaddd-158">New users added to a group can take up to eight hours for their first call to arrive.</span></span>

### <a name="call-routing"></a><span data-ttu-id="aaddd-159">通話ルーティング</span><span class="sxs-lookup"><span data-stu-id="aaddd-159">Call routing</span></span>

![電話会議モードとルーティング方法の設定のスクリーンショット](media/call-queue-conference-mode-routing-method.png)

<span data-ttu-id="aaddd-161">**電話会議モード** では、エージェントが呼び出しを受け入れてから、呼び出し元がエージェントに接続するのにかかる時間が大幅に短縮されます。</span><span class="sxs-lookup"><span data-stu-id="aaddd-161">**Conference mode** significantly reduces the amount of time it takes for a caller to be connected to an agent, after the agent accepts the call.</span></span> <span data-ttu-id="aaddd-162">電話会議モードを機能するには、通話キュー内のエージェントが次のいずれかのクライアントを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="aaddd-162">For conference mode to work, agents in the call queue must use one of the following clients:</span></span>

  - <span data-ttu-id="aaddd-163">デスクトップ クライアント、Android Microsoft Teams iOS アプリの最新バージョン</span><span class="sxs-lookup"><span data-stu-id="aaddd-163">The latest version of the Microsoft Teams desktop client, Android app, or iOS app</span></span>
  - <span data-ttu-id="aaddd-164">Microsoft Teamsバージョン 1449/1.0.94.2020051601 以降</span><span class="sxs-lookup"><span data-stu-id="aaddd-164">Microsoft Teams phone version 1449/1.0.94.2020051601 or later</span></span>
  
<span data-ttu-id="aaddd-165">エージェントのTeamsアカウントは、Teamsモードに設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="aaddd-165">Agents' Teams accounts need to be set to Teams-only mode.</span></span> <span data-ttu-id="aaddd-166">要件を満たしていないエージェントは、通話ルーティングの一覧には含まれません。</span><span class="sxs-lookup"><span data-stu-id="aaddd-166">Agents who don't meet the requirements aren't included in the call routing list.</span></span> <span data-ttu-id="aaddd-167">エージェントが互換性のあるクライアントを使用している場合は、通話キューの会議モードを有効にすることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="aaddd-167">We recommend enabling conference mode for your call queues if your agents are all using compatible clients.</span></span>

> [!NOTE]
> <span data-ttu-id="aaddd-168">電話呼び出しが、場所ベースのルーティングが有効になっているダイレクト ルーティング ゲートウェイからキューにルーティングされる場合、電話会議モードはサポートされません。</span><span class="sxs-lookup"><span data-stu-id="aaddd-168">Conference mode is not supported if phone calls are routed to the queue from a Direct Routing gateway that is enabled for Location Based Routing.</span></span>

<span data-ttu-id="aaddd-169">**ルーティング方法は** 、エージェントがキューから呼び出しを受信する順序を決定します。</span><span class="sxs-lookup"><span data-stu-id="aaddd-169">**Routing method** determines the order in which agents receive calls from the queue.</span></span> <span data-ttu-id="aaddd-170">次のオプションから選択します。</span><span class="sxs-lookup"><span data-stu-id="aaddd-170">Choose from these options:</span></span>

- <span data-ttu-id="aaddd-171">**アテンダント** ルーティングでは、キュー内のすべてのエージェントが同時に呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="aaddd-171">**Attendant routing** rings all agents in the queue at the same time.</span></span> <span data-ttu-id="aaddd-172">呼び出しを受け取る最初の呼び出しエージェントが呼び出しを取得します。</span><span class="sxs-lookup"><span data-stu-id="aaddd-172">The first call agent to pick up the call gets the call.</span></span>

- <span data-ttu-id="aaddd-173">**シリアル ルーティングでは** 、すべての呼び出しエージェントが[通話エージェント] の一覧で指定された順序 **で 1 つ 1 つリング** されます。</span><span class="sxs-lookup"><span data-stu-id="aaddd-173">**Serial routing** rings all call agents one by one in the order specified in the **Call agents** list.</span></span> <span data-ttu-id="aaddd-174">エージェントが通話を閉じ、または呼び出しを受け取らない場合、呼び出しは次のエージェントを呼び出し、エージェントが取り出されるか、または時間が切れるまですべてのエージェントを試します。</span><span class="sxs-lookup"><span data-stu-id="aaddd-174">If an agent dismisses or does not pick up a call, the call will ring the next agent and will try all agents until it is picked up or times out.</span></span>

- <span data-ttu-id="aaddd-175">**ラウンド ロビンは** 、着信呼び出しのルーティングのバランスを取り、各呼び出しエージェントがキューから同じ数の呼び出しを取得します。</span><span class="sxs-lookup"><span data-stu-id="aaddd-175">**Round robin** balances the routing of incoming calls so that each call agent gets the same number of calls from the queue.</span></span> <span data-ttu-id="aaddd-176">これは、すべての通話エージェント間で均等な機会を確保するために、受信販売環境で望ましい場合があります。</span><span class="sxs-lookup"><span data-stu-id="aaddd-176">This may be desirable in an inbound sales environment to assure equal opportunity among all the call agents.</span></span>

- <span data-ttu-id="aaddd-177">**アイドル時間が** 最も長いエージェントに各呼び出しをルーティングします。</span><span class="sxs-lookup"><span data-stu-id="aaddd-177">**Longest idle** routes each call to the agent who has been idle the longest time.</span></span> <span data-ttu-id="aaddd-178">エージェントのプレゼンス状態が [使用可能] の場合、またはプレゼンス状態が 10 分未満の場合、エージェントはアイドル状態と見なされます。</span><span class="sxs-lookup"><span data-stu-id="aaddd-178">An agent is considered idle if their presence state is Available or if their presence state has been Away for less than 10 minutes.</span></span> <span data-ttu-id="aaddd-179">プレゼンス状態が 10 分を超える状態のエージェントはアイドル状態とは見なされません。プレゼンスを [利用可能] に変更するまで、通話を受信する資格は得られません。</span><span class="sxs-lookup"><span data-stu-id="aaddd-179">Agents whose presence state has been Away for more than 10 minutes are not considered idle and will not be eligible to receive calls until they change their presence to Available.</span></span> 

![ルーティング、オプトアウト、アラート時間の設定のスクリーンショット](media/call-queue-presence-agents-time.png)

<span data-ttu-id="aaddd-181">**プレゼンス ベースのルーティングでは** 、呼び出しエージェントの可用性状態を使用して、選択したルーティング方法の呼び出しルーティング リストにエージェントを含める必要があるかどうかを判断します。</span><span class="sxs-lookup"><span data-stu-id="aaddd-181">**Presence-based routing** uses the availability status of call agents to determine whether an agent should be included in the call routing list for the selected routing method.</span></span> <span data-ttu-id="aaddd-182">可用性の状態が [使用可能] に設定されている通話エージェント **は、通話** ルーティング リストに含まれており、通話を受信できます。</span><span class="sxs-lookup"><span data-stu-id="aaddd-182">Call agents whose availability status is set to **Available** are included in the call routing list and can receive calls.</span></span> <span data-ttu-id="aaddd-183">可用性の状態が他の状態に設定されているエージェントは、通話ルーティング リストから除外され、可用性の状態が [利用可能] に戻るまで、呼び出しを受信 **しません**。</span><span class="sxs-lookup"><span data-stu-id="aaddd-183">Agents whose availability status is set to any other status are excluded from the call routing list and won't receive calls until their availability status changes back to **Available**.</span></span> 

<span data-ttu-id="aaddd-184">プレゼンス ベースの呼び出しルーティングは、任意のルーティング方法で有効にできます。</span><span class="sxs-lookup"><span data-stu-id="aaddd-184">You can enable presence-based call routing with any of the routing methods.</span></span>

> [!NOTE]
> <span data-ttu-id="aaddd-185">ルーティング **方法として [最長** アイドル時間] が選択されている場合、プレゼンス ベースのルーティングのトグルが [オフ] および[グレー] になっている場合でも、プレゼンス ベースのルーティングが必要であり、自動的に有効になります。</span><span class="sxs-lookup"><span data-stu-id="aaddd-185">When **Longest idle** is selected as the routing method, presence-based routing is required and automatically enabled even though the Presence-based routing toggle will be **Off** and grayed out.</span></span>

<span data-ttu-id="aaddd-186">エージェントが呼び出しを受け取らない場合、エージェントは、可用性の状態が設定されているに関係なく、通話ルーティング リストに含まれません。</span><span class="sxs-lookup"><span data-stu-id="aaddd-186">If an agent opts out of getting calls, they won't be included in the call routing list regardless of what their availability status is set to.</span></span> 

> [!NOTE]
> <span data-ttu-id="aaddd-187">プレゼンス ベースのルーティングSkype for Business、クライアントを使用するエージェントは、呼び出しルーティング の一覧に含まれません。</span><span class="sxs-lookup"><span data-stu-id="aaddd-187">Agents who use the Skype for Business client aren't included in the call routing list when presence-based routing is enabled.</span></span> <span data-ttu-id="aaddd-188">このサービスを使用するエージェントSkype for Business、プレゼンス ベースの呼び出しルーティングを有効にすることはできません。</span><span class="sxs-lookup"><span data-stu-id="aaddd-188">If you have agents who use Skype for Business, don't enable presence-based call routing.</span></span>

<span data-ttu-id="aaddd-189">**エージェント アラート時間は** 、キューが呼び出しを次のエージェントにリダイレクトする前に、エージェントの電話が鳴る時間を指定します。</span><span class="sxs-lookup"><span data-stu-id="aaddd-189">**Agent alert time** specifies how long an agent's phone will ring before the queue redirects the call to the next agent.</span></span>

<span data-ttu-id="aaddd-190">次の設定をお勧めします。</span><span class="sxs-lookup"><span data-stu-id="aaddd-190">The following settings are recommended:</span></span>

- <span data-ttu-id="aaddd-191">**会議モードから\*\*\*\*自動**</span><span class="sxs-lookup"><span data-stu-id="aaddd-191">**Conference mode** to **Auto**</span></span>
- <span data-ttu-id="aaddd-192">**ラウンド ロビンまたは\*\*\*\*最長アイドルへの\*\*\*\*ルーティング方法**</span><span class="sxs-lookup"><span data-stu-id="aaddd-192">**Routing method** to **Round robin** or **Longest idle**</span></span>
- <span data-ttu-id="aaddd-193">**プレゼンス ベースのルーティングを** **[オン] に設定する**</span><span class="sxs-lookup"><span data-stu-id="aaddd-193">**Presence-based routing** to **On**</span></span>
- <span data-ttu-id="aaddd-194">**エージェントのアラート時間:** **~ 20 秒**</span><span class="sxs-lookup"><span data-stu-id="aaddd-194">**Agent alert time:** to **20 seconds**</span></span>

> [!NOTE]
> <span data-ttu-id="aaddd-195">プレゼンス ベースのルーティングが有効ではなく、キュー内に複数の呼び出しがある場合、システムは、プレゼンス状態に関係なく、これらの呼び出しをエージェントに同時に表示します。</span><span class="sxs-lookup"><span data-stu-id="aaddd-195">If presence-based routing is not enabled and there are multiple calls in the queue, the system will present these calls simultaneously to the agents regardless of their presence status.</span></span> <span data-ttu-id="aaddd-196">これにより、エージェントに対する複数の呼び出し通知が発生します。特に、一部のエージェントがエージェントに提示された最初の呼び出しに応答しない場合。</span><span class="sxs-lookup"><span data-stu-id="aaddd-196">This will result in multiple call notifications to agents, particularly if some agents don’t answer the initial call presented to them.</span></span>

### <a name="call-overflow-handling"></a><span data-ttu-id="aaddd-197">呼び出しオーバーフロー処理</span><span class="sxs-lookup"><span data-stu-id="aaddd-197">Call overflow handling</span></span>

![呼び出しオーバーフロー設定のスクリーンショット](media/call-queue-overflow-handling.png)

<span data-ttu-id="aaddd-199">**キュー内の最大呼び** 出し数は、特定の時点でキュー内で待機できる呼び出しの最大数を指定します。</span><span class="sxs-lookup"><span data-stu-id="aaddd-199">**Maximum calls in the queue** specifies the maximum number of calls that can wait in the queue at any given time.</span></span> <span data-ttu-id="aaddd-200">既定値は 50 ですが、0 ~ 200 の範囲で指定できます。</span><span class="sxs-lookup"><span data-stu-id="aaddd-200">The default is 50, but it can range from 0 to 200.</span></span> <span data-ttu-id="aaddd-201">この制限に達すると、呼び出しは [呼び出しの最大数に達した場合] 設定で指定された **方法で処理** されます。</span><span class="sxs-lookup"><span data-stu-id="aaddd-201">When this limit is reached, the call is handled as specified by the **When the maximum number of calls is reached** setting.</span></span>

<span data-ttu-id="aaddd-202">通話を切断するか、任意の通話ルーティング先にリダイレクトすることができます。</span><span class="sxs-lookup"><span data-stu-id="aaddd-202">You can choose to disconnect the call or redirect it to any of the call routing destinations.</span></span> <span data-ttu-id="aaddd-203">たとえば、発信者にキュー内のエージェントのボイスメールを残す場合があります。</span><span class="sxs-lookup"><span data-stu-id="aaddd-203">For example, you might have the caller leave a voicemail for the agents in the queue.</span></span> <span data-ttu-id="aaddd-204">外部転送については、「前提条件」と[](plan-auto-attendant-call-queue.md#prerequisites)「外部電話番号の転送 - 番号の書式設定に関[する技術的な詳細](create-a-phone-system-auto-attendant.md#external-phone-number-transfers---technical-details)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="aaddd-204">For external transfers, please refer to [Prerequisites](plan-auto-attendant-call-queue.md#prerequisites) and the [external phone number transfers - technical details](create-a-phone-system-auto-attendant.md#external-phone-number-transfers---technical-details) for number formatting.</span></span>

> [!NOTE]
> <span data-ttu-id="aaddd-205">呼び出しの最大数が 0 に設定されている場合、あいさつメッセージは再生されません。</span><span class="sxs-lookup"><span data-stu-id="aaddd-205">If the maximum number of calls is set to 0 then the greeting message will not play.</span></span>

### <a name="call-timeout-handling"></a><span data-ttu-id="aaddd-206">呼び出しタイムアウト処理</span><span class="sxs-lookup"><span data-stu-id="aaddd-206">Call timeout handling</span></span>

![通話タイムアウト設定のスクリーンショット](media/call-queue-timeout-handling.png)

<span data-ttu-id="aaddd-208">**呼び出** しタイムアウト: 最大待機時間は、呼び出しがリダイレクトまたは切断される前にキューで保留にできる最大時間を指定します。</span><span class="sxs-lookup"><span data-stu-id="aaddd-208">**Call Timeout: maximum wait time** specifies the maximum time a call can be on hold in the queue before it is redirected or disconnected.</span></span> <span data-ttu-id="aaddd-209">0 秒から 45 分の値を指定できます。</span><span class="sxs-lookup"><span data-stu-id="aaddd-209">You can specify a value from 0 seconds to 45 minutes.</span></span>

<span data-ttu-id="aaddd-210">通話を切断するか、または通話ルーティング先の 1 つにリダイレクトすることができます。</span><span class="sxs-lookup"><span data-stu-id="aaddd-210">You can choose to disconnect the call or redirect it to one of the call routing destinations.</span></span> <span data-ttu-id="aaddd-211">たとえば、発信者にキュー内のエージェントのボイスメールを残す場合があります。</span><span class="sxs-lookup"><span data-stu-id="aaddd-211">For example, you might have the caller leave a voicemail for the agents in the queue.</span></span> <span data-ttu-id="aaddd-212">外部転送については、「前提条件」と[](plan-auto-attendant-call-queue.md#prerequisites)「外部電話番号の転送 - 番号の書式設定に関[する技術的な詳細](create-a-phone-system-auto-attendant.md#external-phone-number-transfers---technical-details)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="aaddd-212">For external transfers, please refer to [Prerequisites](plan-auto-attendant-call-queue.md#prerequisites) and the [external phone number transfers - technical details](create-a-phone-system-auto-attendant.md#external-phone-number-transfers---technical-details) for number formatting.</span></span>

<span data-ttu-id="aaddd-213">通話タイムアウト オプションを選択した後、[保存] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="aaddd-213">When you have selected your call timeout options, click **Save**.</span></span>

## <a name="supported-clients"></a><span data-ttu-id="aaddd-214">サポートされるクライアント</span><span class="sxs-lookup"><span data-stu-id="aaddd-214">Supported clients</span></span>

<span data-ttu-id="aaddd-215">呼び出しキュー内の呼び出しエージェントでは、次のクライアントがサポートされます。</span><span class="sxs-lookup"><span data-stu-id="aaddd-215">The following clients are supported for call agents in a call queue:</span></span>

  - <span data-ttu-id="aaddd-216">Skype for Business クライアント 2016 (32 ビット版と 64 ビット版)</span><span class="sxs-lookup"><span data-stu-id="aaddd-216">Skype for Business desktop client 2016 (32-bit and 64-bit versions)</span></span>
  - <span data-ttu-id="aaddd-217">Lync デスクトップ クライアント 2013 (32 ビット版と 64 ビット版)</span><span class="sxs-lookup"><span data-stu-id="aaddd-217">Lync desktop client 2013 (32-bit and 64-bit versions)</span></span>
  - <span data-ttu-id="aaddd-218">すべての IP 電話モデルは、Microsoft Teams。</span><span class="sxs-lookup"><span data-stu-id="aaddd-218">All IP phone models supported for Microsoft Teams.</span></span> <span data-ttu-id="aaddd-219">[「Getting phones for Skype for Business Online 」を参照してください](/skypeforbusiness/what-is-phone-system-in-office-365/getting-phones-for-skype-for-business-online/getting-phones-for-skype-for-business-online)。</span><span class="sxs-lookup"><span data-stu-id="aaddd-219">See [Getting phones for Skype for Business Online](/skypeforbusiness/what-is-phone-system-in-office-365/getting-phones-for-skype-for-business-online/getting-phones-for-skype-for-business-online).</span></span>
  - <span data-ttu-id="aaddd-220">Mac版  Skype for Business クライアント (バージョン 16.8.196 以降)</span><span class="sxs-lookup"><span data-stu-id="aaddd-220">Mac Skype for Business Client (version 16.8.196 and later)</span></span>
  - <span data-ttu-id="aaddd-221">Aandroid Skype for Business クライアント (バージョン 6.16.0.9 以降)</span><span class="sxs-lookup"><span data-stu-id="aaddd-221">Android Skype for Business Client (version 6.16.0.9 and later)</span></span>
  - <span data-ttu-id="aaddd-222">iPhone Skype for Business Client クライアント(バージョン 6.16.0 以降)</span><span class="sxs-lookup"><span data-stu-id="aaddd-222">iPhone Skype for Business Client (version 6.16.0 and later)</span></span>
  - <span data-ttu-id="aaddd-223">Mac版  Skype for Business クライアント (バージョン 6.16.0 以降)</span><span class="sxs-lookup"><span data-stu-id="aaddd-223">iPad Skype for Business Client (version 6.16.0 and later)</span></span>
  - <span data-ttu-id="aaddd-224">Microsoft Teams Windows クライアント (32 ビットおよび 64 ビット バージョン)</span><span class="sxs-lookup"><span data-stu-id="aaddd-224">Microsoft Teams Windows client (32-bit and 64-bit versions)</span></span>
  - <span data-ttu-id="aaddd-225">Microsoft Teams Mac クライアント</span><span class="sxs-lookup"><span data-stu-id="aaddd-225">Microsoft Teams Mac client</span></span>
  - <span data-ttu-id="aaddd-226">Microsoft Teams[デスクトップ インフラストラクチャ](/microsoftteams/teams-for-vdi)(Windows Virtual Desktop、Citrix、VMware) に関するページ</span><span class="sxs-lookup"><span data-stu-id="aaddd-226">Microsoft Teams on [Virtualized Desktop Infrastructure](/microsoftteams/teams-for-vdi) (Windows Virtual Desktop, Citrix, and VMware)</span></span>
  - <span data-ttu-id="aaddd-227">Microsoft Teams iPhone アプリ</span><span class="sxs-lookup"><span data-stu-id="aaddd-227">Microsoft Teams iPhone app</span></span>
  - <span data-ttu-id="aaddd-228">Microsoft Teams Android アプリ</span><span class="sxs-lookup"><span data-stu-id="aaddd-228">Microsoft Teams Android app</span></span>

    > [!NOTE]
    > <span data-ttu-id="aaddd-229">直接ルーティング番号が割り当てられた通話キューは、クライアント、Lync クライアント、Skype for Business IP Phone をエージェントSkype for Businessサポートしません。</span><span class="sxs-lookup"><span data-stu-id="aaddd-229">Call queues that are assigned a direct routing number don't support Skype for Business clients, Lync clients, or Skype for Business IP Phones as agents.</span></span>

## <a name="call-queue-cmdlets"></a><span data-ttu-id="aaddd-230">通話キューのコマンドレット</span><span class="sxs-lookup"><span data-stu-id="aaddd-230">Call queue cmdlets</span></span>

<span data-ttu-id="aaddd-231">Windows PowerShell を使用して通話キューを作成し、設定することもできます。</span><span class="sxs-lookup"><span data-stu-id="aaddd-231">You can also use Windows PowerShell to create and set up call queues.</span></span> <span data-ttu-id="aaddd-232">呼び出しキューの管理に使用するコマンドレットを次に示します。</span><span class="sxs-lookup"><span data-stu-id="aaddd-232">Here are the cmdlets that you use to manage a call queue.</span></span>

- [<span data-ttu-id="aaddd-233">New-CsCallQueue</span><span class="sxs-lookup"><span data-stu-id="aaddd-233">New-CsCallQueue</span></span>](/powershell/module/skype/new-CsCallQueue)

- [<span data-ttu-id="aaddd-234">Set-CsCallQueue</span><span class="sxs-lookup"><span data-stu-id="aaddd-234">Set-CsCallQueue</span></span>](/powershell/module/skype/set-CsCallQueue)

- [<span data-ttu-id="aaddd-235">Get-CsCallQueue</span><span class="sxs-lookup"><span data-stu-id="aaddd-235">Get-CsCallQueue</span></span>](/powershell/module/skype/get-CsCallQueue)

- [<span data-ttu-id="aaddd-236">Remove-CsCallQueue</span><span class="sxs-lookup"><span data-stu-id="aaddd-236">Remove-CsCallQueue</span></span>](/powershell/module/skype/remove-CsCallQueue)

## <a name="related-topics"></a><span data-ttu-id="aaddd-237">関連項目</span><span class="sxs-lookup"><span data-stu-id="aaddd-237">Related topics</span></span>

[<span data-ttu-id="aaddd-238">電話システムで利用できる機能</span><span class="sxs-lookup"><span data-stu-id="aaddd-238">Here's what you get with Phone System</span></span>](here-s-what-you-get-with-phone-system.md)

[<span data-ttu-id="aaddd-239">サービス電話番号を取得する</span><span class="sxs-lookup"><span data-stu-id="aaddd-239">Getting service phone numbers</span></span>](getting-service-phone-numbers.md)

[<span data-ttu-id="aaddd-240">国および地域ごとの電話会議および通話プランの利用可能性</span><span class="sxs-lookup"><span data-stu-id="aaddd-240">Country and region availability for Audio Conferencing and Calling Plans</span></span>](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)

[<span data-ttu-id="aaddd-241">New-CsOnlineApplicationInstance</span><span class="sxs-lookup"><span data-stu-id="aaddd-241">New-CsOnlineApplicationInstance</span></span>](/powershell/module/skype/new-csonlineapplicationinstance)

[<span data-ttu-id="aaddd-242">Windows PowerShell と Skype for Business Online の概要</span><span class="sxs-lookup"><span data-stu-id="aaddd-242">An introduction to Windows PowerShell and Skype for Business Online</span></span>](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)
