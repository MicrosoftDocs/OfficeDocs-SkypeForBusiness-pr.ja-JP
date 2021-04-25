---
title: Microsoft Teams で通話キューを作成する
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
description: Microsoft Teams を使用して通話キュー用の電話システムを設定する方法について説明します。これは、案内メッセージ、保留音楽、通話リダイレクト、その他の機能を提供します。
ms.openlocfilehash: f60714bc1c4868496209f414583c925da527460a
ms.sourcegitcommit: 900f28c4ac12d65ccbd996028205ba183b4afb03
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/24/2021
ms.locfileid: "51995285"
---
# <a name="create-a-call-queue"></a><span data-ttu-id="a66cb-103">呼び出しキューを作成する</span><span class="sxs-lookup"><span data-stu-id="a66cb-103">Create a call queue</span></span>

<span data-ttu-id="a66cb-104">通話キューは、特定の問題や質問に役立つ組織内のユーザーに発信者をルーティングする方法を提供します。</span><span class="sxs-lookup"><span data-stu-id="a66cb-104">Call queues provide a method of routing callers to people in your organization who can help with a particular issue or question.</span></span> <span data-ttu-id="a66cb-105">呼び出しは、キュー内のユーザー (エージェントと呼ばれる) に一度に 1 回配布 *されます*。</span><span class="sxs-lookup"><span data-stu-id="a66cb-105">Calls are distributed one at a time to the people in the queue (who are known as *agents*).</span></span> 

<span data-ttu-id="a66cb-106">呼び出しキューには、次の機能が提供されます。</span><span class="sxs-lookup"><span data-stu-id="a66cb-106">Call queues provide:</span></span>

- <span data-ttu-id="a66cb-107">あいさつメッセージ。</span><span class="sxs-lookup"><span data-stu-id="a66cb-107">A greeting message.</span></span>

- <span data-ttu-id="a66cb-108">ユーザーがキューで保留を待機している間の音楽。</span><span class="sxs-lookup"><span data-stu-id="a66cb-108">Music while people are waiting on hold in a queue.</span></span>

- <span data-ttu-id="a66cb-109">通話ルーティング - *First In、First Out* (FIFO) の順序でエージェントに送信します。</span><span class="sxs-lookup"><span data-stu-id="a66cb-109">Call routing - in *First In, First Out* (FIFO) order - to agents.</span></span>

- <span data-ttu-id="a66cb-110">キュー オーバーフローとタイムアウトの処理オプション。</span><span class="sxs-lookup"><span data-stu-id="a66cb-110">Handling options for queue overflow and timeout.</span></span>

<span data-ttu-id="a66cb-111">この記事の手順に従う前に[、「Teams](plan-auto-attendant-call-queue.md)の自動応答と通話キューの[](plan-auto-attendant-call-queue.md#getting-started)計画」を読み、開始手順に従ってください。</span><span class="sxs-lookup"><span data-stu-id="a66cb-111">Be sure you have read [Plan for Teams auto attendants and call queues](plan-auto-attendant-call-queue.md) and followed the [getting started steps](plan-auto-attendant-call-queue.md#getting-started) before you follow the procedures in this article.</span></span>

<span data-ttu-id="a66cb-112">通話キューを設定するには、Teams 管理センターで [Voice] を展開し、[通話キュー] をクリックし、[追加] を **クリックします**。 </span><span class="sxs-lookup"><span data-stu-id="a66cb-112">To set up a call queue, in the Teams admin center, expand **Voice**, click **Call queues**, and then click **Add**.</span></span>

## <a name="resource-account-and-language"></a><span data-ttu-id="a66cb-113">リソース アカウントと言語</span><span class="sxs-lookup"><span data-stu-id="a66cb-113">Resource account and language</span></span>

![リソース アカウントと言語設定のスクリーンショット](media/call-queue-name-language.png)

1. <span data-ttu-id="a66cb-115">呼び出しキューの名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="a66cb-115">Type a name for the call queue.</span></span>

2. <span data-ttu-id="a66cb-116">[**アカウントの追加]** をクリックし、この呼び出しキューで使用するリソースアカウントを検索し、[追加] をクリックし、[追加] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="a66cb-116">Click **Add accounts**, search for the resource account that you want to use with this call queue, click **Add**, and then click **Add**.</span></span> <span data-ttu-id="a66cb-117">(エージェントは、着信呼び出しを受信すると、リソース アカウント名が表示されます)。</span><span class="sxs-lookup"><span data-stu-id="a66cb-117">(Agents will see the resource account name when they receive an incoming call.)</span></span>

3. <span data-ttu-id="a66cb-118">サポートされている言語 [を選択します](create-a-phone-system-call-queue-languages.md)。</span><span class="sxs-lookup"><span data-stu-id="a66cb-118">Choose a [supported language](create-a-phone-system-call-queue-languages.md).</span></span> <span data-ttu-id="a66cb-119">この言語は、システムで生成された音声プロンプトとボイスメールの文字起こし (有効にした場合) に使用されます。</span><span class="sxs-lookup"><span data-stu-id="a66cb-119">This language will be used for system-generated voice prompts and voicemail transcription (if you enable them).</span></span>

## <a name="greetings-and-music-on-hold-in-queue"></a><span data-ttu-id="a66cb-120">キュー内のグリーティングと保留の音楽</span><span class="sxs-lookup"><span data-stu-id="a66cb-120">Greetings and music on hold in queue</span></span>

<span data-ttu-id="a66cb-121">発信者がキューに到着するときに、発信者にあいさつを再生する場合に指定します。</span><span class="sxs-lookup"><span data-stu-id="a66cb-121">Specify if you want to play a greeting to callers when they arrive in the queue.</span></span> <span data-ttu-id="a66cb-122">再生するあいさつを含む MP3、WAV、または WMA ファイルをアップロードする必要があります。</span><span class="sxs-lookup"><span data-stu-id="a66cb-122">You must upload an MP3, WAV, or WMA file containing the greeting that you want to play.</span></span>

<span data-ttu-id="a66cb-123">Teams は、キューで保留の間、呼び出し元に既定の音楽を提供します。</span><span class="sxs-lookup"><span data-stu-id="a66cb-123">Teams provides default music to callers while they are on hold in a queue.</span></span> <span data-ttu-id="a66cb-124">特定のオーディオ ファイルを再生する場合は、[オーディオ ファイルの再生] を選択し、MP3、WAV、または WMA ファイルをアップロードします。</span><span class="sxs-lookup"><span data-stu-id="a66cb-124">If you want to play a specific audio file, choose **Play an audio file** and upload an MP3, WAV, or WMA file.</span></span>

> [!NOTE]
> <span data-ttu-id="a66cb-125">アップロードされた記録は、5 MB 以下に設定できます。</span><span class="sxs-lookup"><span data-stu-id="a66cb-125">The uploaded recording can be no larger than 5 MB.</span></span>
> <span data-ttu-id="a66cb-126">Teams 呼び出しキューで提供される既定の音楽には、組織が支払うロイヤリティは無料です。</span><span class="sxs-lookup"><span data-stu-id="a66cb-126">The default music supplied in Teams call queues is free of any royalties payable by your organization.</span></span> 

## <a name="call-agents"></a><span data-ttu-id="a66cb-127">エージェントを呼び出す</span><span class="sxs-lookup"><span data-stu-id="a66cb-127">Call agents</span></span>

<span data-ttu-id="a66cb-128">エージェントを [呼び出しキューに追加するための前提条件を確認します](plan-auto-attendant-call-queue.md#prerequisites)。</span><span class="sxs-lookup"><span data-stu-id="a66cb-128">Review the [prerequisites for adding agents to a call queue](plan-auto-attendant-call-queue.md#prerequisites).</span></span>

![通話キューのユーザーとグループの設定のスクリーンショット](media/call-queue-users-groups.png)

##### <a name="teams-channel"></a><span data-ttu-id="a66cb-130">Teams チャネル</span><span class="sxs-lookup"><span data-stu-id="a66cb-130">Teams channel</span></span>

<span data-ttu-id="a66cb-131">Teams チャネルを使用して最大 200 人のエージェントを追加できます。</span><span class="sxs-lookup"><span data-stu-id="a66cb-131">You can add up to 200 agents via a Teams channel.</span></span>

<span data-ttu-id="a66cb-132">Teams チャネルを使用 [してキューを](https://support.microsoft.com/office/9f07dabe-91c6-4a9b-a545-8ffdddd2504e)管理する場合は、[チームの選択] オプションを選択し、[チャネルの追加 **] をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="a66cb-132">If you want to [use a Teams channel to manage the queue](https://support.microsoft.com/office/9f07dabe-91c6-4a9b-a545-8ffdddd2504e), select the **Choose a team** option and click **Add a channel**.</span></span> <span data-ttu-id="a66cb-133">使用するチームを検索して選択し、[追加] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="a66cb-133">Search for the team that you want to use, select it, and click **Add**.</span></span> <span data-ttu-id="a66cb-134">使用するチャネルを選択し、[適用] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="a66cb-134">Select the channel that you want to use and click **Apply**.</span></span>

<span data-ttu-id="a66cb-135">次のクライアントは、通話キューに Teams チャネルを使用する場合にサポートされます。</span><span class="sxs-lookup"><span data-stu-id="a66cb-135">The following clients are supported when using a Teams channel for call queues:</span></span> 

  - <span data-ttu-id="a66cb-136">Microsoft Teams Windows クライアント</span><span class="sxs-lookup"><span data-stu-id="a66cb-136">Microsoft Teams Windows client</span></span>
  - <span data-ttu-id="a66cb-137">Microsoft Teams Mac クライアント</span><span class="sxs-lookup"><span data-stu-id="a66cb-137">Microsoft Teams Mac client</span></span>

##### <a name="users-and-groups"></a><span data-ttu-id="a66cb-138">ユーザーとグループ</span><span class="sxs-lookup"><span data-stu-id="a66cb-138">Users and groups</span></span>

<span data-ttu-id="a66cb-139">最大 20 人のエージェントを個別に追加し、最大 200 人のエージェントをグループ経由で追加できます。</span><span class="sxs-lookup"><span data-stu-id="a66cb-139">You can add up to 20 agents individually and up to 200 agents via groups.</span></span>

<span data-ttu-id="a66cb-140">キューに個々のユーザーまたはグループを追加する場合は、[ユーザーとグループの選択] オプション **を選択** します。</span><span class="sxs-lookup"><span data-stu-id="a66cb-140">If you want to add individual users or groups to the queue, select the **Choose users and groups** option.</span></span> 

<span data-ttu-id="a66cb-141">キューにユーザーを追加するには、[ユーザーの追加] をクリックし、ユーザーを検索し、[追加] をクリックし、[追加] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="a66cb-141">To add a user to the queue, click **Add users**, search for the user, click **Add**, and then click **Add**.</span></span>

<span data-ttu-id="a66cb-142">キューにグループを追加するには、[グループの追加] をクリックし、グループを検索し、[追加] をクリックし、[追加] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="a66cb-142">To add a group to the queue, click **Add groups**, search for the group, click **Add**, and then click **Add**.</span></span> <span data-ttu-id="a66cb-143">配布リスト、セキュリティ グループ、および Microsoft 365 グループまたは Microsoft Teams チームを使用できます。</span><span class="sxs-lookup"><span data-stu-id="a66cb-143">You can use distribution lists, security groups, and Microsoft 365 groups or Microsoft Teams teams.</span></span>

> [!NOTE]
> <span data-ttu-id="a66cb-144">グループに追加された新しいユーザーは、最初の呼び出しが到着するために最大 8 時間かかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="a66cb-144">New users added to a group can take up to eight hours for their first call to arrive.</span></span>

## <a name="call-routing"></a><span data-ttu-id="a66cb-145">通話ルーティング</span><span class="sxs-lookup"><span data-stu-id="a66cb-145">Call routing</span></span>

![会議モードとルーティング方法の設定のスクリーンショット](media/call-queue-conference-mode-routing-method.png)

<span data-ttu-id="a66cb-147">**会議モード** では、エージェントが呼び出しを受け入れる後に、呼び出し元がエージェントに接続するのにかかる時間が大幅に短縮されます。</span><span class="sxs-lookup"><span data-stu-id="a66cb-147">**Conference mode** significantly reduces the amount of time it takes for a caller to be connected to an agent, after the agent accepts the call.</span></span> <span data-ttu-id="a66cb-148">会議モードを機能するには、通話キュー内のエージェントが次のいずれかのクライアントを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a66cb-148">For conference mode to work, agents in the call queue must use one of the following clients:</span></span>

  - <span data-ttu-id="a66cb-149">Microsoft Teams デスクトップ クライアント、Android アプリ、または iOS アプリの最新バージョン</span><span class="sxs-lookup"><span data-stu-id="a66cb-149">The latest version of the Microsoft Teams desktop client, Android app, or iOS app</span></span>
  - <span data-ttu-id="a66cb-150">Microsoft Teams の電話バージョン 1449/1.0.94.2020051601 以降</span><span class="sxs-lookup"><span data-stu-id="a66cb-150">Microsoft Teams phone version 1449/1.0.94.2020051601 or later</span></span>
  
<span data-ttu-id="a66cb-151">エージェントの Teams アカウントは、Teams 専用モードに設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a66cb-151">Agents' Teams accounts need to be set to Teams-only mode.</span></span> <span data-ttu-id="a66cb-152">要件を満たしていないエージェントは、通話ルーティング リストに含まれません。</span><span class="sxs-lookup"><span data-stu-id="a66cb-152">Agents who don't meet the requirements aren't included in the call routing list.</span></span> <span data-ttu-id="a66cb-153">エージェントが互換性のあるクライアントを使用している場合は、通話キューの会議モードを有効にすることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="a66cb-153">We recommend enabling conference mode for your call queues if your agents are all using compatible clients.</span></span>

> [!NOTE]
> <span data-ttu-id="a66cb-154">場所に基づくルーティングが有効になっているダイレクト ルーティング ゲートウェイから電話がキューにルーティングされる場合、会議モードはサポートされません。</span><span class="sxs-lookup"><span data-stu-id="a66cb-154">Conference mode is not supported if phone calls are routed to the queue from a Direct Routing gateway that is enabled for Location Based Routing.</span></span>

<span data-ttu-id="a66cb-155">**ルーティング方法は** 、エージェントがキューから呼び出しを受信する順序を決定します。</span><span class="sxs-lookup"><span data-stu-id="a66cb-155">**Routing method** determines the order in which agents receive calls from the queue.</span></span> <span data-ttu-id="a66cb-156">次のオプションから選択します。</span><span class="sxs-lookup"><span data-stu-id="a66cb-156">Choose from these options:</span></span>

- <span data-ttu-id="a66cb-157">**アテンダント ルーティング** では、キュー内のすべてのエージェントが同時に呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="a66cb-157">**Attendant routing** rings all agents in the queue at the same time.</span></span> <span data-ttu-id="a66cb-158">呼び出しを受け取る最初の呼び出しエージェントは、呼び出しを取得します。</span><span class="sxs-lookup"><span data-stu-id="a66cb-158">The first call agent to pick up the call gets the call.</span></span>

- <span data-ttu-id="a66cb-159">**シリアル ルーティングでは** 、すべての呼び出しエージェントが[エージェントの呼び出し] リストで指定された順序 **で 1 つ 1 つリング** されます。</span><span class="sxs-lookup"><span data-stu-id="a66cb-159">**Serial routing** rings all call agents one by one in the order specified in the **Call agents** list.</span></span> <span data-ttu-id="a66cb-160">エージェントが通話を却下または取り上げない場合、呼び出しは次のエージェントを呼び出し、そのエージェントが取り上げられるか、または時間が切れるまですべてのエージェントを試します。</span><span class="sxs-lookup"><span data-stu-id="a66cb-160">If an agent dismisses or does not pick up a call, the call will ring the next agent and will try all agents until it is picked up or times out.</span></span>

- <span data-ttu-id="a66cb-161">**ラウンド ロビンは** 、着信呼び出しのルーティングのバランスを取り、各呼び出しエージェントがキューから同じ数の呼び出しを取得します。</span><span class="sxs-lookup"><span data-stu-id="a66cb-161">**Round robin** balances the routing of incoming calls so that each call agent gets the same number of calls from the queue.</span></span> <span data-ttu-id="a66cb-162">これは、すべての通話エージェント間で均等な機会を確保するために、受信販売環境で望ましい場合があります。</span><span class="sxs-lookup"><span data-stu-id="a66cb-162">This may be desirable in an inbound sales environment to assure equal opportunity among all the call agents.</span></span>

- <span data-ttu-id="a66cb-163">**アイドル時間が** 最も長いエージェントに各呼び出しがルーティングされます。</span><span class="sxs-lookup"><span data-stu-id="a66cb-163">**Longest idle** routes each call to the agent who has been idle the longest time.</span></span> <span data-ttu-id="a66cb-164">エージェントのプレゼンス状態が [使用可能] である場合、またはプレゼンス状態が 10 分未満離れた場合、エージェントはアイドル状態と見なされます。</span><span class="sxs-lookup"><span data-stu-id="a66cb-164">An agent is considered idle if their presence state is Available or if their presence state has been Away for less than 10 minutes.</span></span> <span data-ttu-id="a66cb-165">プレゼンス状態が 10 分以上離れたエージェントはアイドル状態とは見なされません。プレゼンスを [利用可能] に変更するまで、通話を受信する資格は得られません。</span><span class="sxs-lookup"><span data-stu-id="a66cb-165">Agents whose presence state has been Away for more than 10 minutes are not considered idle and will not be eligible to receive calls until they change their presence to Available.</span></span> 

![ルーティング、オプトアウト、アラート時間の設定のスクリーンショット](media/call-queue-presence-agents-time.png)


<span data-ttu-id="a66cb-167">**プレゼンス ベースのルーティングでは** 、呼び出しエージェントの可用性状態を使用して、エージェントを選択したルーティング方法の呼び出しルーティング リストに含める必要があるかどうかを判断します。</span><span class="sxs-lookup"><span data-stu-id="a66cb-167">**Presence-based routing** uses the availability status of call agents to determine whether an agent should be included in the call routing list for the selected routing method.</span></span> <span data-ttu-id="a66cb-168">可用性の状態が [利用可能] に設定されている通話エージェント **は、通話** ルーティング リストに含まれており、呼び出しを受信できます。</span><span class="sxs-lookup"><span data-stu-id="a66cb-168">Call agents whose availability status is set to **Available** are included in the call routing list and can receive calls.</span></span> <span data-ttu-id="a66cb-169">可用性の状態が他の状態に設定されているエージェントは、通話ルーティング リストから除外され、可用性の状態が [利用可能] に戻るまで呼び出しを受信 **しません**。</span><span class="sxs-lookup"><span data-stu-id="a66cb-169">Agents whose availability status is set to any other status are excluded from the call routing list and won't receive calls until their availability status changes back to **Available**.</span></span> 

<span data-ttu-id="a66cb-170">任意のルーティング方法でプレゼンス ベースの呼び出しルーティングを有効にできます。</span><span class="sxs-lookup"><span data-stu-id="a66cb-170">You can enable presence-based call routing with any of the routing methods.</span></span>

<span data-ttu-id="a66cb-171">エージェントが通話の受け取りをオプトアウトした場合、エージェントの可用性の状態が設定されている状況に関係なく、通話ルーティング リストに含まれません。</span><span class="sxs-lookup"><span data-stu-id="a66cb-171">If an agent opts out of getting calls, they won't be included in the call routing list regardless of what their availability status is set to.</span></span> 

> [!NOTE]
> <span data-ttu-id="a66cb-172">プレゼンス ベースのルーティングが有効になっている場合、Skype for Business クライアントを使用するエージェントは、通話ルーティング リストに含まれません。</span><span class="sxs-lookup"><span data-stu-id="a66cb-172">Agents who use the Skype for Business client aren't included in the call routing list when presence-based routing is enabled.</span></span> <span data-ttu-id="a66cb-173">Skype for Business を使用するエージェントがある場合は、プレゼンス ベースの通話ルーティングを有効にしない。</span><span class="sxs-lookup"><span data-stu-id="a66cb-173">If you have agents who use Skype for Business, don't enable presence-based call routing.</span></span>

<span data-ttu-id="a66cb-174">**エージェントアラート時間は** 、キューが呼び出しを次のエージェントにリダイレクトする前にエージェントの電話が鳴る時間を指定します。</span><span class="sxs-lookup"><span data-stu-id="a66cb-174">**Agent alert time** specifies how long an agent's phone will ring before the queue redirects the call to the next agent.</span></span>

<span data-ttu-id="a66cb-175">次の設定をお勧めします。</span><span class="sxs-lookup"><span data-stu-id="a66cb-175">The following settings are recommended:</span></span>

- <span data-ttu-id="a66cb-176">**会議モードを** [自動] **に設定する**</span><span class="sxs-lookup"><span data-stu-id="a66cb-176">**Conference mode** to **Auto**</span></span>
- <span data-ttu-id="a66cb-177">**ラウンド ロビンまたは\*\*\*\*最長アイドルへの\*\*\*\*ルーティング方法**</span><span class="sxs-lookup"><span data-stu-id="a66cb-177">**Routing method** to **Round robin** or **Longest idle**</span></span>
- <span data-ttu-id="a66cb-178">**プレゼンス ベースのルーティングを** **On に設定する**</span><span class="sxs-lookup"><span data-stu-id="a66cb-178">**Presence-based routing** to **On**</span></span>
- <span data-ttu-id="a66cb-179">**エージェントのアラート時間:** **20 秒**</span><span class="sxs-lookup"><span data-stu-id="a66cb-179">**Agent alert time:** to **20 seconds**</span></span>

> [!NOTE]
> <span data-ttu-id="a66cb-180">プレゼンス ベースのルーティングが有効ではなく、キュー内に複数の呼び出しがある場合、システムはプレゼンス状態に関係なく、これらの呼び出しをエージェントに同時に表示します。</span><span class="sxs-lookup"><span data-stu-id="a66cb-180">If presence-based routing is not enabled and there are multiple calls in the queue, the system will present these calls simultaneously to the agents regardless of their presence status.</span></span> <span data-ttu-id="a66cb-181">これにより、エージェントに対して複数の通話通知が送信されます。特に、一部のエージェントがエージェントに提示された最初の呼び出しに応答しない場合。</span><span class="sxs-lookup"><span data-stu-id="a66cb-181">This will result in multiple call notifications to agents, particularly if some agents don’t answer the initial call presented to them.</span></span>

## <a name="call-overflow-handling"></a><span data-ttu-id="a66cb-182">呼び出しオーバーフロー処理</span><span class="sxs-lookup"><span data-stu-id="a66cb-182">Call overflow handling</span></span>

![呼び出しオーバーフロー設定のスクリーンショット](media/call-queue-overflow-handling.png)

<span data-ttu-id="a66cb-184">**キュー内の最大呼び** 出し数は、任意の時点でキューで待機できる呼び出しの最大数を指定します。</span><span class="sxs-lookup"><span data-stu-id="a66cb-184">**Maximum calls in the queue** specifies the maximum number of calls that can wait in the queue at any given time.</span></span> <span data-ttu-id="a66cb-185">既定値は 50 ですが、0 から 200 の範囲で指定できます。</span><span class="sxs-lookup"><span data-stu-id="a66cb-185">The default is 50, but it can range from 0 to 200.</span></span> <span data-ttu-id="a66cb-186">この制限に達すると、呼び出しは [呼び出しの最大数に達した場合] 設定で指定された通 **り処理** されます。</span><span class="sxs-lookup"><span data-stu-id="a66cb-186">When this limit is reached, the call is handled as specified by the **When the maximum number of calls is reached** setting.</span></span>

<span data-ttu-id="a66cb-187">通話を切断するか、任意の呼び出しルーティング先にリダイレクトすることができます。</span><span class="sxs-lookup"><span data-stu-id="a66cb-187">You can choose to disconnect the call or redirect it to any of the call routing destinations.</span></span> <span data-ttu-id="a66cb-188">たとえば、発信者がキュー内のエージェントのボイスメールを残す場合があります。</span><span class="sxs-lookup"><span data-stu-id="a66cb-188">For example, you might have the caller leave a voicemail for the agents in the queue.</span></span> <span data-ttu-id="a66cb-189">外部転送については、「前提条件」と[](plan-auto-attendant-call-queue.md#prerequisites)「外部電話番号の転送[-](create-a-phone-system-auto-attendant.md#external-phone-number-transfers---technical-details)番号の書式設定に関する技術的な詳細」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a66cb-189">For external transfers, please refer to [Prerequisites](plan-auto-attendant-call-queue.md#prerequisites) and the [external phone number transfers - technical details](create-a-phone-system-auto-attendant.md#external-phone-number-transfers---technical-details) for number formatting.</span></span>

> [!NOTE]
> <span data-ttu-id="a66cb-190">呼び出しの最大数が 0 に設定されている場合、あいさつメッセージは再生されません。</span><span class="sxs-lookup"><span data-stu-id="a66cb-190">If the maximum number of calls is set to 0 then the greeting message will not play.</span></span>

## <a name="call-timeout-handling"></a><span data-ttu-id="a66cb-191">呼び出しタイムアウト処理</span><span class="sxs-lookup"><span data-stu-id="a66cb-191">Call timeout handling</span></span>

![通話タイムアウト設定のスクリーンショット](media/call-queue-timeout-handling.png)

<span data-ttu-id="a66cb-193">**呼び出しタイムアウト:** 最大待機時間は、呼び出しがリダイレクトまたは切断される前にキューで保留にできる最大時間を指定します。</span><span class="sxs-lookup"><span data-stu-id="a66cb-193">**Call Timeout: maximum wait time** specifies the maximum time a call can be on hold in the queue before it is redirected or disconnected.</span></span> <span data-ttu-id="a66cb-194">0 秒から 45 分の値を指定できます。</span><span class="sxs-lookup"><span data-stu-id="a66cb-194">You can specify a value from 0 seconds to 45 minutes.</span></span>

<span data-ttu-id="a66cb-195">通話を切断するか、または呼び出しルーティング先の 1 つにリダイレクトすることができます。</span><span class="sxs-lookup"><span data-stu-id="a66cb-195">You can choose to disconnect the call or redirect it to one of the call routing destinations.</span></span> <span data-ttu-id="a66cb-196">たとえば、発信者がキュー内のエージェントのボイスメールを残す場合があります。</span><span class="sxs-lookup"><span data-stu-id="a66cb-196">For example, you might have the caller leave a voicemail for the agents in the queue.</span></span> <span data-ttu-id="a66cb-197">外部転送については、「前提条件」と[](plan-auto-attendant-call-queue.md#prerequisites)「外部電話番号の転送[-](create-a-phone-system-auto-attendant.md#external-phone-number-transfers---technical-details)番号の書式設定に関する技術的な詳細」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a66cb-197">For external transfers, please refer to [Prerequisites](plan-auto-attendant-call-queue.md#prerequisites) and the [external phone number transfers - technical details](create-a-phone-system-auto-attendant.md#external-phone-number-transfers---technical-details) for number formatting.</span></span>

<span data-ttu-id="a66cb-198">通話タイムアウト オプションを選択した場合は、[保存] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="a66cb-198">When you have selected your call timeout options, click **Save**.</span></span>

## <a name="caller-id-for-outbound-calls"></a><span data-ttu-id="a66cb-199">発信呼び出しの呼び出し元 ID</span><span class="sxs-lookup"><span data-stu-id="a66cb-199">Caller ID for outbound calls</span></span>

<span data-ttu-id="a66cb-200">通話キュー内のエージェントがダイヤルアウトして顧客の通話を返す場合があります。通話キューのメンバーの発信者 ID を、適切な自動応答のサービス番号に設定してください。</span><span class="sxs-lookup"><span data-stu-id="a66cb-200">Since agents in a call queue may dial out to return a customer call, consider setting the caller ID for members of a call queue to the service number of an appropriate auto attendant.</span></span> <span data-ttu-id="a66cb-201">詳細については [、「Microsoft Teams で発信者 ID ポリシーを管理する」](caller-id-policies.md) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a66cb-201">See [Manage caller ID policies in Microsoft Teams](caller-id-policies.md) for more information.</span></span>

## <a name="supported-clients"></a><span data-ttu-id="a66cb-202">サポートされるクライアント</span><span class="sxs-lookup"><span data-stu-id="a66cb-202">Supported clients</span></span>

<span data-ttu-id="a66cb-203">呼び出しキューの呼び出しエージェントでは、次のクライアントがサポートされます。</span><span class="sxs-lookup"><span data-stu-id="a66cb-203">The following clients are supported for call agents in a call queue:</span></span>

  - <span data-ttu-id="a66cb-204">Skype for Business デスクトップ クライアント 2016 (32 ビット版と 64 ビット版)</span><span class="sxs-lookup"><span data-stu-id="a66cb-204">Skype for Business desktop client 2016 (32-bit and 64-bit versions)</span></span>
  - <span data-ttu-id="a66cb-205">Lync デスクトップ クライアント 2013 (32 ビット版と 64 ビット版)</span><span class="sxs-lookup"><span data-stu-id="a66cb-205">Lync desktop client 2013 (32-bit and 64-bit versions)</span></span>
  - <span data-ttu-id="a66cb-206">Microsoft Teams でサポートされているすべての IP フォン モデル。</span><span class="sxs-lookup"><span data-stu-id="a66cb-206">All IP phone models supported for Microsoft Teams.</span></span> <span data-ttu-id="a66cb-207">「Skype for Business [Online の電話を取得する」を参照してください](/skypeforbusiness/what-is-phone-system-in-office-365/getting-phones-for-skype-for-business-online/getting-phones-for-skype-for-business-online)。</span><span class="sxs-lookup"><span data-stu-id="a66cb-207">See [Getting phones for Skype for Business Online](/skypeforbusiness/what-is-phone-system-in-office-365/getting-phones-for-skype-for-business-online/getting-phones-for-skype-for-business-online).</span></span>
  - <span data-ttu-id="a66cb-208">Mac版  Skype for Business クライアント (バージョン 16.8.196 以降)</span><span class="sxs-lookup"><span data-stu-id="a66cb-208">Mac Skype for Business Client (version 16.8.196 and later)</span></span>
  - <span data-ttu-id="a66cb-209">Aandroid Skype for Business クライアント (バージョン 6.16.0.9 以降)</span><span class="sxs-lookup"><span data-stu-id="a66cb-209">Android Skype for Business Client (version 6.16.0.9 and later)</span></span>
  - <span data-ttu-id="a66cb-210">iPhone Skype for Business Client クライアント(バージョン 6.16.0 以降)</span><span class="sxs-lookup"><span data-stu-id="a66cb-210">iPhone Skype for Business Client (version 6.16.0 and later)</span></span>
  - <span data-ttu-id="a66cb-211">Mac版  Skype for Business クライアント (バージョン 6.16.0 以降)</span><span class="sxs-lookup"><span data-stu-id="a66cb-211">iPad Skype for Business Client (version 6.16.0 and later)</span></span>
  - <span data-ttu-id="a66cb-212">Microsoft Teams Windows クライアント (32 ビット版と 64 ビット版)</span><span class="sxs-lookup"><span data-stu-id="a66cb-212">Microsoft Teams Windows client (32-bit and 64-bit versions)</span></span>
  - <span data-ttu-id="a66cb-213">Microsoft Teams Mac クライアント</span><span class="sxs-lookup"><span data-stu-id="a66cb-213">Microsoft Teams Mac client</span></span>
  - <span data-ttu-id="a66cb-214">Microsoft Teams on [Virtualed Desktop Infrastructure](/microsoftteams/teams-for-vdi) (Windows Virtual Desktop、Citrix、VMware)</span><span class="sxs-lookup"><span data-stu-id="a66cb-214">Microsoft Teams on [Virtualized Desktop Infrastructure](/microsoftteams/teams-for-vdi) (Windows Virtual Desktop, Citrix, and VMware)</span></span>
  - <span data-ttu-id="a66cb-215">Microsoft Teams iPhone アプリ</span><span class="sxs-lookup"><span data-stu-id="a66cb-215">Microsoft Teams iPhone app</span></span>
  - <span data-ttu-id="a66cb-216">Microsoft Teams Android アプリ</span><span class="sxs-lookup"><span data-stu-id="a66cb-216">Microsoft Teams Android app</span></span>

    > [!NOTE]
    > <span data-ttu-id="a66cb-217">直接ルーティング番号が割り当てられている通話キューは、Skype for Business クライアント、Lync クライアント、または Skype for Business IP Phone をエージェントとしてサポートしません。</span><span class="sxs-lookup"><span data-stu-id="a66cb-217">Call queues that are assigned a direct routing number don't support Skype for Business clients, Lync clients, or Skype for Business IP Phones as agents.</span></span>

## <a name="call-queue-cmdlets"></a><span data-ttu-id="a66cb-218">通話キューのコマンドレット</span><span class="sxs-lookup"><span data-stu-id="a66cb-218">Call queue cmdlets</span></span>

<span data-ttu-id="a66cb-219">Windows PowerShell を使用して通話キューを作成し、設定することもできます。</span><span class="sxs-lookup"><span data-stu-id="a66cb-219">You can also use Windows PowerShell to create and set up call queues.</span></span> <span data-ttu-id="a66cb-220">呼び出しキューの管理に使用するコマンドレットを次に示します。</span><span class="sxs-lookup"><span data-stu-id="a66cb-220">Here are the cmdlets that you use to manage a call queue.</span></span>

- [<span data-ttu-id="a66cb-221">New-CsCallQueue</span><span class="sxs-lookup"><span data-stu-id="a66cb-221">New-CsCallQueue</span></span>](/powershell/module/skype/new-CsCallQueue)

- [<span data-ttu-id="a66cb-222">Set-CsCallQueue</span><span class="sxs-lookup"><span data-stu-id="a66cb-222">Set-CsCallQueue</span></span>](/powershell/module/skype/set-CsCallQueue)

- [<span data-ttu-id="a66cb-223">Get-CsCallQueue</span><span class="sxs-lookup"><span data-stu-id="a66cb-223">Get-CsCallQueue</span></span>](/powershell/module/skype/get-CsCallQueue)

- [<span data-ttu-id="a66cb-224">Remove-CsCallQueue</span><span class="sxs-lookup"><span data-stu-id="a66cb-224">Remove-CsCallQueue</span></span>](/powershell/module/skype/remove-CsCallQueue)

## <a name="related-topics"></a><span data-ttu-id="a66cb-225">関連項目</span><span class="sxs-lookup"><span data-stu-id="a66cb-225">Related topics</span></span>

[<span data-ttu-id="a66cb-226">電話システムで利用できる機能</span><span class="sxs-lookup"><span data-stu-id="a66cb-226">Here's what you get with Phone System</span></span>](here-s-what-you-get-with-phone-system.md)

[<span data-ttu-id="a66cb-227">サービス電話番号を取得する</span><span class="sxs-lookup"><span data-stu-id="a66cb-227">Getting service phone numbers</span></span>](getting-service-phone-numbers.md)

[<span data-ttu-id="a66cb-228">国および地域ごとの電話会議および通話プランの利用可能性</span><span class="sxs-lookup"><span data-stu-id="a66cb-228">Country and region availability for Audio Conferencing and Calling Plans</span></span>](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)

[<span data-ttu-id="a66cb-229">New-CsOnlineApplicationInstance</span><span class="sxs-lookup"><span data-stu-id="a66cb-229">New-CsOnlineApplicationInstance</span></span>](/powershell/module/skype/new-csonlineapplicationinstance)

[<span data-ttu-id="a66cb-230">Windows PowerShell と Skype for Business Online の概要</span><span class="sxs-lookup"><span data-stu-id="a66cb-230">An introduction to Windows PowerShell and Skype for Business Online</span></span>](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)
