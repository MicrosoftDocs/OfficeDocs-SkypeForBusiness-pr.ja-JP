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
description: Microsoft Teams で通話キュー用の電話システムをセットアップする方法について説明します。応答メッセージの提供、音楽の保留、通話リダイレクト、その他の機能が提供されます。
ms.openlocfilehash: 0253fb15a8672d83e672e3e3e18f8455d292214c
ms.sourcegitcommit: 27bfa015413bc7742bca4ea227e0324da0c740d7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/08/2021
ms.locfileid: "50145894"
---
# <a name="create-a-call-queue"></a><span data-ttu-id="c7932-103">呼び出しキューを作成する</span><span class="sxs-lookup"><span data-stu-id="c7932-103">Create a call queue</span></span>

<span data-ttu-id="c7932-104">通話キューは、組織内の特定の問題や質問に役立つユーザーに発信者をルーティングする方法を提供します。</span><span class="sxs-lookup"><span data-stu-id="c7932-104">Call queues provide a method of routing callers to people in your organization who can help with a particular issue or question.</span></span> <span data-ttu-id="c7932-105">通話はキュー内のユーザー (エージェントと呼ばれる) に一度に 1 つ配布 *されます*。</span><span class="sxs-lookup"><span data-stu-id="c7932-105">Calls are distributed one at a time to the people in the queue (who are known as *agents*).</span></span> 

<span data-ttu-id="c7932-106">通話キューには次の機能があります。</span><span class="sxs-lookup"><span data-stu-id="c7932-106">Call queues provide:</span></span>

- <span data-ttu-id="c7932-107">あいさつメッセージ。</span><span class="sxs-lookup"><span data-stu-id="c7932-107">A greeting message.</span></span>

- <span data-ttu-id="c7932-108">ユーザーがキューで保留を待っている間の音楽。</span><span class="sxs-lookup"><span data-stu-id="c7932-108">Music while people are waiting on hold in a queue.</span></span>

- <span data-ttu-id="c7932-109">エージェントへのコール ルーティング ( *First In、First Out* (FIRST Out ) 順序 (</span><span class="sxs-lookup"><span data-stu-id="c7932-109">Call routing - in *First In, First Out* (FIFO) order - to agents.</span></span>

- <span data-ttu-id="c7932-110">キュー のオーバーフローとタイムアウトの処理オプション。</span><span class="sxs-lookup"><span data-stu-id="c7932-110">Handling options for queue overflow and timeout.</span></span>

<span data-ttu-id="c7932-111">この記事の手順に従う前に[、「Teams](plan-auto-attendant-call-queue.md)の自動応答と通話キューの[](plan-auto-attendant-call-queue.md#getting-started)計画」を読み、開始手順に従ってください。</span><span class="sxs-lookup"><span data-stu-id="c7932-111">Be sure you have read [Plan for Teams auto attendants and call queues](plan-auto-attendant-call-queue.md) and followed the [getting started steps](plan-auto-attendant-call-queue.md#getting-started) before you follow the procedures in this articles.</span></span>

<span data-ttu-id="c7932-112">通話キューを設定するには、Teams 管理センターで [音声] を展開し、[通話キュー] をクリックして、[追加] をクリック **します**。</span><span class="sxs-lookup"><span data-stu-id="c7932-112">To set up a call queue, in the Teams admin center, expand **Voice**, click **Call queues**, and then click **Add**.</span></span>

## <a name="resource-account-and-language"></a><span data-ttu-id="c7932-113">リソース アカウントと言語</span><span class="sxs-lookup"><span data-stu-id="c7932-113">Resource account and language</span></span>

![リソース アカウントと言語設定のスクリーンショット](media/call-queue-name-language.png)

1. <span data-ttu-id="c7932-115">通話キューの名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="c7932-115">Type a name for the call queue.</span></span> <span data-ttu-id="c7932-116">エージェントは、キューからの着信通話を受信すると、この名前を表示します。</span><span class="sxs-lookup"><span data-stu-id="c7932-116">Agents will see this name when they receive an incoming call from the queue.</span></span>

2. <span data-ttu-id="c7932-117">[**アカウントの追加]** をクリックし、この通話キューで使用するリソース アカウントを検索し、[追加] をクリックして、[追加] をクリック **します**。</span><span class="sxs-lookup"><span data-stu-id="c7932-117">Click **Add accounts**, search for the resource account that you want to use with this call queue, click **Add**, and then click **Add**.</span></span>

3. <span data-ttu-id="c7932-118">言語を選択します。</span><span class="sxs-lookup"><span data-stu-id="c7932-118">Choose a language.</span></span> <span data-ttu-id="c7932-119">この言語は、システム生成の音声プロンプトとボイスメール トランスクリプション (有効にした場合) に使用されます。</span><span class="sxs-lookup"><span data-stu-id="c7932-119">This language will be used for system-generated voice prompts and voicemail transcription (if you enable them).</span></span>

## <a name="greetings-and-music-on-hold-in-queue"></a><span data-ttu-id="c7932-120">キュー内の応答メッセージと保留音</span><span class="sxs-lookup"><span data-stu-id="c7932-120">Greetings and music on hold in queue</span></span>

<span data-ttu-id="c7932-121">発信者がキューに入った場合に発信者に応答メッセージを再生する場合に指定します。</span><span class="sxs-lookup"><span data-stu-id="c7932-121">Specify if you want to play a greeting to callers when they arrive in the queue.</span></span> <span data-ttu-id="c7932-122">再生する応答メッセージを含む MP3、WAV、または WMA ファイルをアップロードする必要があります。</span><span class="sxs-lookup"><span data-stu-id="c7932-122">You must upload an MP3, WAV, or WMA file containing the greeting that you want to play.</span></span>

<span data-ttu-id="c7932-123">Teams は、キューで保留されている間、発信者に既定の音楽を提供します。</span><span class="sxs-lookup"><span data-stu-id="c7932-123">Teams provides default music to callers while they are on hold in a queue.</span></span> <span data-ttu-id="c7932-124">特定のオーディオ ファイルを再生する場合は、[オーディオ ファイルの再生] を選択し、MP3、WAV、または WMA ファイルをアップロードします。</span><span class="sxs-lookup"><span data-stu-id="c7932-124">If you want to play a specific audio file, choose **Play an audio file** and upload an MP3, WAV, or WMA file.</span></span>

> [!NOTE]
> <span data-ttu-id="c7932-125">アップロードされた記録は 5 MB 以下にできます。</span><span class="sxs-lookup"><span data-stu-id="c7932-125">The uploaded recording can be no larger than 5 MB.</span></span>
> <span data-ttu-id="c7932-126">Teams の通話キューで提供される既定の音楽には、組織が支払う料金は無料です。</span><span class="sxs-lookup"><span data-stu-id="c7932-126">The default music supplied in Teams call queues is free of any royalties payable by your organization.</span></span> 

## <a name="call-agents"></a><span data-ttu-id="c7932-127">コール エージェント</span><span class="sxs-lookup"><span data-stu-id="c7932-127">Call agents</span></span>

<span data-ttu-id="c7932-128">エージェントを通話キュー [に](plan-auto-attendant-call-queue.md#prerequisites) 追加するには、「前提条件」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c7932-128">Please refer to the [Prerequisites](plan-auto-attendant-call-queue.md#prerequisites) in order to be able to add agents to a call queue.</span></span>

![通話キューのユーザーとグループの設定のスクリーンショット](media/call-queue-users-groups.png)

<span data-ttu-id="c7932-130">最大 20 人のエージェントを個別に追加し、最大 200 人のエージェントをグループ経由で追加できます。</span><span class="sxs-lookup"><span data-stu-id="c7932-130">You can add up to 20 agents individually and up to 200 agents via groups.</span></span>

<span data-ttu-id="c7932-131">キューにユーザーを追加するには、[ユーザーの追加] をクリックし、ユーザーを検索し、[追加] をクリックして、[追加] をクリック **します**。</span><span class="sxs-lookup"><span data-stu-id="c7932-131">To add a user to the queue, click **Add users**, search for the user, click **Add**, and then click **Add**.</span></span>

<span data-ttu-id="c7932-132">キューにグループを追加するには、[グループの追加] をクリックし、グループを検索し、[追加] をクリックして、[追加] をクリック **します**。</span><span class="sxs-lookup"><span data-stu-id="c7932-132">To add a group to the queue, click **Add groups**, search for the group, click **Add**, and then click **Add**.</span></span> <span data-ttu-id="c7932-133">配布リスト、セキュリティ グループ、Microsoft 365 グループまたは Microsoft Teams チームを使用できます。</span><span class="sxs-lookup"><span data-stu-id="c7932-133">You can use distribution lists, security groups, and Microsoft 365 groups or Microsoft Teams teams.</span></span>

> [!NOTE]
> <span data-ttu-id="c7932-134">グループに追加された新しいユーザーは、最初の通話が到着するために最大 8 時間かかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="c7932-134">New users added to a group can take up to eight hours for their first call to arrive.</span></span>

## <a name="call-routing"></a><span data-ttu-id="c7932-135">通話ルーティング</span><span class="sxs-lookup"><span data-stu-id="c7932-135">Call routing</span></span>

![電話会議モードとルーティング方法の設定のスクリーンショット](media/call-queue-conference-mode-routing-method.png)

<span data-ttu-id="c7932-137">**電話会議モード** では、エージェントが通話を受け入れてから、発信者がエージェントに接続するのにかかる時間が大幅に短縮されます。</span><span class="sxs-lookup"><span data-stu-id="c7932-137">**Conference mode** significantly reduces the amount of time it takes for a caller to be connected to an agent, after the agent accepts the call.</span></span> <span data-ttu-id="c7932-138">会議モードが機能するには、通話キュー内のエージェントが次のいずれかのクライアントを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c7932-138">For conference mode to work, agents in the call queue must use one of the following clients:</span></span>

  - <span data-ttu-id="c7932-139">最新バージョンの Microsoft Teams デスクトップ クライアント、Android アプリ、または iOS アプリ</span><span class="sxs-lookup"><span data-stu-id="c7932-139">The latest version of the Microsoft Teams desktop client, Android app, or iOS app</span></span>
  - <span data-ttu-id="c7932-140">Microsoft Teams の電話バージョン 1449/1.0.94.2020051601 以降</span><span class="sxs-lookup"><span data-stu-id="c7932-140">Microsoft Teams phone version 1449/1.0.94.2020051601 or later</span></span>
  
<span data-ttu-id="c7932-141">エージェントの Teams アカウントは、Teams 専用モードに設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c7932-141">Agents' Teams accounts need to be set to Teams-only mode.</span></span> <span data-ttu-id="c7932-142">要件を満たしていないエージェントは、通話ルーティング リストに含まれません。</span><span class="sxs-lookup"><span data-stu-id="c7932-142">Agents who don't meet the requirements aren't included in the call routing list.</span></span> <span data-ttu-id="c7932-143">エージェント全員が互換性のあるクライアントを使用している場合は、通話キューの会議モードを有効にすることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="c7932-143">We recommend enabling conference mode for your call queues if your agents are all using compatible clients.</span></span>

<span data-ttu-id="c7932-144">**ルーティング方法は** 、エージェントがキューから通話を受信する順序を決定します。</span><span class="sxs-lookup"><span data-stu-id="c7932-144">**Routing method** determines the order in which agents receive calls from the queue.</span></span> <span data-ttu-id="c7932-145">次のオプションから選択します。</span><span class="sxs-lookup"><span data-stu-id="c7932-145">Choose from these options:</span></span>

- <span data-ttu-id="c7932-146">**アテンダント** ルーティングでは、キュー内のすべてのエージェントが同時に呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="c7932-146">**Attendant routing** rings all agents in the queue at the same time.</span></span> <span data-ttu-id="c7932-147">通話を受け取る最初の通話エージェントが通話を受け取る。</span><span class="sxs-lookup"><span data-stu-id="c7932-147">The first call agent to pick up the call gets the call.</span></span>

- <span data-ttu-id="c7932-148">**シリアル ルーティングは** 、すべてのコール エージェントを、コール エージェント リストで指定された順序で 1 **つ 1 つリング** します。</span><span class="sxs-lookup"><span data-stu-id="c7932-148">**Serial routing** rings all call agents one by one in the order specified in the **Call agents** list.</span></span> <span data-ttu-id="c7932-149">エージェントが通話を却下するか、通話を受け取らない場合、通話は次のエージェントを呼び出し、エージェントが受け取されるか、または時間が切れるまですべてのエージェントを試します。</span><span class="sxs-lookup"><span data-stu-id="c7932-149">If an agent dismisses or does not pick up a call, the call will ring the next agent and will try all agents until it is picked up or times out.</span></span>

- <span data-ttu-id="c7932-150">**ラウンド ロビンは** 、着信通話のルーティングのバランスを取り、各通話エージェントがキューから同じ数の通話を受け取ります。</span><span class="sxs-lookup"><span data-stu-id="c7932-150">**Round robin** balances the routing of incoming calls so that each call agent gets the same number of calls from the queue.</span></span> <span data-ttu-id="c7932-151">これは、すべての通話エージェント間で同じ機会を確保するために、受信販売環境で望ましい場合があります。</span><span class="sxs-lookup"><span data-stu-id="c7932-151">This may be desirable in an inbound sales environment to assure equal opportunity among all the call agents.</span></span>

- <span data-ttu-id="c7932-152">**アイドル時間が** 最も長いエージェントに各呼び出しがルーティングされます。</span><span class="sxs-lookup"><span data-stu-id="c7932-152">**Longest idle** routes each call to the agent who has been idle the longest time.</span></span> <span data-ttu-id="c7932-153">エージェントのプレゼンス状態が [使用可能] の場合、またはプレゼンス状態が 10 分未満離れた場合、エージェントはアイドルと見なされます。</span><span class="sxs-lookup"><span data-stu-id="c7932-153">An agent is considered idle if their presence state is Available or if their presence state has been Away for less than 10 minutes.</span></span> <span data-ttu-id="c7932-154">プレゼンス状態が 10 分以上離れたエージェントはアイドルと見なされ、プレゼンスを [利用可能] に変更するまで通話を受信できません。</span><span class="sxs-lookup"><span data-stu-id="c7932-154">Agents whose presence state has been Away for more than 10 minutes are not considered idle and will not be eligible to receive calls until they change their presence to Available.</span></span> 

![ルーティング、オプトアウト、通知時間の設定のスクリーンショット](media/call-queue-presence-agents-time.png)


<span data-ttu-id="c7932-156">**プレゼンス ベースのルーティングでは** 、エージェントの可用性の状態を使用して、選択したルーティング方法の通話ルーティング リストにエージェントを含める必要があるかどうかを決定します。</span><span class="sxs-lookup"><span data-stu-id="c7932-156">**Presence-based routing** uses the availability status of call agents to determine whether an agent should be included in the call routing list for the selected routing method.</span></span> <span data-ttu-id="c7932-157">利用可能状態が [連絡可能]に設定されているコール エージェントは、通話ルーティング リストに含まれており、通話を受信できます。</span><span class="sxs-lookup"><span data-stu-id="c7932-157">Call agents whose availability status is set to **Available** are included in the call routing list and can receive calls.</span></span> <span data-ttu-id="c7932-158">利用可能状態が他の状態に設定されているエージェントは、通話ルーティング リストから除外され、利用可能状態が [連絡可能] に戻るまで通話を受信 **しません**。</span><span class="sxs-lookup"><span data-stu-id="c7932-158">Agents whose availability status is set to any other status are excluded from the call routing list and won't receive calls until their availability status changes back to **Available**.</span></span> 

<span data-ttu-id="c7932-159">プレゼンス ベースの通話ルーティングは、任意のルーティング方法で有効にできます。</span><span class="sxs-lookup"><span data-stu-id="c7932-159">You can enable presence-based call routing with any of the routing methods.</span></span>

<span data-ttu-id="c7932-160">エージェントが通話の受け取りをオプトアウトした場合、エージェントの状態に設定されている状態に関係なく、エージェントは通話ルーティング リストに含まれません。</span><span class="sxs-lookup"><span data-stu-id="c7932-160">If an agent opts out of getting calls, they won't be included in the call routing list regardless of what their availability status is set to.</span></span> 

> [!NOTE]
> <span data-ttu-id="c7932-161">プレゼンス ベースのルーティングが有効な場合、Skype for Business クライアントを使用するエージェントは通話ルーティング リストに含まれません。</span><span class="sxs-lookup"><span data-stu-id="c7932-161">Agents who use the Skype for Business client aren't included in the call routing list when presence-based routing is enabled.</span></span> <span data-ttu-id="c7932-162">Skype for Business を使用するエージェントが存在する場合は、プレゼンス ベースの通話ルーティングを有効にしない。</span><span class="sxs-lookup"><span data-stu-id="c7932-162">If you have agents who use Skype for Business, don't enable presence-based call routing.</span></span>

<span data-ttu-id="c7932-163">**エージェント通知時間は** 、キューが呼び出しを次のエージェントにリダイレクトする前にエージェントの電話が鳴る時間を指定します。</span><span class="sxs-lookup"><span data-stu-id="c7932-163">**Agent alert time** specifies how long an agent's phone will ring before the queue redirects the call to the next agent.</span></span>

<span data-ttu-id="c7932-164">次の設定をお勧めします。</span><span class="sxs-lookup"><span data-stu-id="c7932-164">The following settings are recommended:</span></span>

- <span data-ttu-id="c7932-165">**会議モードから\*\*\*\*自動へ**</span><span class="sxs-lookup"><span data-stu-id="c7932-165">**Conference mode** to **Auto**</span></span>
- <span data-ttu-id="c7932-166">**ラウンド ロビンまたは\*\*\*\*最長アイドルへの\*\*\*\*ルーティング方法**</span><span class="sxs-lookup"><span data-stu-id="c7932-166">**Routing method** to **Round robin** or **Longest idle**</span></span>
- <span data-ttu-id="c7932-167">**プレゼンス ベースのルーティングを\*\*\*\*オンに**</span><span class="sxs-lookup"><span data-stu-id="c7932-167">**Presence-based routing** to **On**</span></span>
- <span data-ttu-id="c7932-168">**エージェントの通知時間:** **20 秒**</span><span class="sxs-lookup"><span data-stu-id="c7932-168">**Agent alert time:** to **20 seconds**</span></span>

> [!NOTE]
> <span data-ttu-id="c7932-169">プレゼンス ベースのルーティングが有効でなく、キュー内に複数の通話がある場合、システムはプレゼンス状態に関係なく、これらの通話をエージェントに同時に表示します。</span><span class="sxs-lookup"><span data-stu-id="c7932-169">If presence-based routing is not enabled and there are multiple calls in the queue, the system will present these calls simultaneously to the agents regardless of their presence status.</span></span> <span data-ttu-id="c7932-170">これにより、特に一部のエージェントがエージェントに表示された最初の通話に応答しない場合は、エージェントに対して複数の通話通知が送信されます。</span><span class="sxs-lookup"><span data-stu-id="c7932-170">This will result in multiple call notifications to agents, particularly if some agents don’t answer the initial call presented to them.</span></span>

## <a name="call-overflow-handling"></a><span data-ttu-id="c7932-171">呼び出しオーバーフロー処理</span><span class="sxs-lookup"><span data-stu-id="c7932-171">Call overflow handling</span></span>

![呼び出しオーバーフロー設定のスクリーンショット](media/call-queue-overflow-handling.png)

<span data-ttu-id="c7932-173">**キュー内の最大呼** び出し数は、任意の時点でキュー内で待機できる呼び出しの最大数を指定します。</span><span class="sxs-lookup"><span data-stu-id="c7932-173">**Maximum calls in the queue** specifies the maximum number of calls that can wait in the queue at any given time.</span></span> <span data-ttu-id="c7932-174">既定値は 50 ですが、0 から 200 の範囲で指定できます。</span><span class="sxs-lookup"><span data-stu-id="c7932-174">The default is 50, but it can range from 0 to 200.</span></span> <span data-ttu-id="c7932-175">この制限に達すると、呼び出しは [通話の最大数に達した場合] 設定で指定された方法 **で処理** されます。</span><span class="sxs-lookup"><span data-stu-id="c7932-175">When this limit is reached, the call is handled as specified by the **When the maximum number of calls is reached** setting.</span></span>

<span data-ttu-id="c7932-176">通話を切断するか、任意の通話ルーティング先にリダイレクトすることができます。</span><span class="sxs-lookup"><span data-stu-id="c7932-176">You can choose to disconnect the call or redirect it to any of the call routing destinations.</span></span> <span data-ttu-id="c7932-177">たとえば、発信者にキュー内のエージェントのボイスメールを残す場合があります。</span><span class="sxs-lookup"><span data-stu-id="c7932-177">For example, you might have the caller leave a voicemail for the agents in the queue.</span></span> <span data-ttu-id="c7932-178">外部転送については、「前提条件」と[](plan-auto-attendant-call-queue.md#prerequisites)「外部電話番号の転送[-](create-a-phone-system-auto-attendant.md#external-phone-number-transfers---technical-details)番号の書式設定の技術的な詳細」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c7932-178">For external transfers, please refer to [Prerequisites](plan-auto-attendant-call-queue.md#prerequisites) and the [external phone number transfers - technical details](create-a-phone-system-auto-attendant.md#external-phone-number-transfers---technical-details) for number formatting.</span></span>

> [!NOTE]
> <span data-ttu-id="c7932-179">通話の最大数が 0 に設定されている場合、あいさつメッセージは再生されません。</span><span class="sxs-lookup"><span data-stu-id="c7932-179">If the maximum number of calls is set to 0 then the greeting message will not play.</span></span>

## <a name="call-timeout-handling"></a><span data-ttu-id="c7932-180">通話タイムアウト処理</span><span class="sxs-lookup"><span data-stu-id="c7932-180">Call timeout handling</span></span>

![通話タイムアウト設定のスクリーンショット](media/call-queue-timeout-handling.png)

<span data-ttu-id="c7932-182">**通話タイムアウト: 最大待ち** 時間は、呼び出しがリダイレクトまたは切断される前にキュー内で保留にできる最大時間を指定します。</span><span class="sxs-lookup"><span data-stu-id="c7932-182">**Call Timeout: maximum wait time** specifies the maximum time a call can be on hold in the queue before it is redirected or disconnected.</span></span> <span data-ttu-id="c7932-183">0 秒から 45 分の値を指定できます。</span><span class="sxs-lookup"><span data-stu-id="c7932-183">You can specify a value from 0 seconds to 45 minutes.</span></span>

<span data-ttu-id="c7932-184">通話を切断するか、通話ルーティング先の 1 つにリダイレクトすることができます。</span><span class="sxs-lookup"><span data-stu-id="c7932-184">You can choose to disconnect the call or redirect it to one of the call routing destinations.</span></span> <span data-ttu-id="c7932-185">たとえば、発信者にキュー内のエージェントのボイスメールを残す場合があります。</span><span class="sxs-lookup"><span data-stu-id="c7932-185">For example, you might have the caller leave a voicemail for the agents in the queue.</span></span> <span data-ttu-id="c7932-186">外部転送については、「前提条件」と[](plan-auto-attendant-call-queue.md#prerequisites)「外部電話番号の転送[-](create-a-phone-system-auto-attendant.md#external-phone-number-transfers---technical-details)番号の書式設定の技術的な詳細」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c7932-186">For external transfers, please refer to [Prerequisites](plan-auto-attendant-call-queue.md#prerequisites) and the [external phone number transfers - technical details](create-a-phone-system-auto-attendant.md#external-phone-number-transfers---technical-details) for number formatting.</span></span>

<span data-ttu-id="c7932-187">通話のタイムアウト オプションを選択した場合は、[保存] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="c7932-187">When you have selected your call timeout options, click **Save**.</span></span>

## <a name="caller-id-for-outbound-calls"></a><span data-ttu-id="c7932-188">発信通話の発信者番号</span><span class="sxs-lookup"><span data-stu-id="c7932-188">Caller ID for outbound calls</span></span>

<span data-ttu-id="c7932-189">通話キュー内のエージェントがダイヤルアウトして顧客の通話を返す可能性があるから、通話キューのメンバーの発信者番号を適切な自動応答のサービス番号に設定する方法を検討してください。</span><span class="sxs-lookup"><span data-stu-id="c7932-189">Since agents in a call queue may dial out to return a customer call, consider setting the caller ID for members of a call queue to the service number of an appropriate auto attendant.</span></span> <span data-ttu-id="c7932-190">詳細 [については、「Microsoft Teams で発信者番号ポリシーを](caller-id-policies.md) 管理する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c7932-190">See [Manage caller ID policies in Microsoft Teams](caller-id-policies.md) for more information.</span></span>

## <a name="supported-clients"></a><span data-ttu-id="c7932-191">サポートされるクライアント</span><span class="sxs-lookup"><span data-stu-id="c7932-191">Supported clients</span></span>

<span data-ttu-id="c7932-192">通話キュー内のコール エージェントでは、次のクライアントがサポートされます。</span><span class="sxs-lookup"><span data-stu-id="c7932-192">The following clients are supported for call agents in a call queue:</span></span>

  - <span data-ttu-id="c7932-193">Skype for Business デスクトップ クライアント 2016 (32 ビット版と 64 ビット版)</span><span class="sxs-lookup"><span data-stu-id="c7932-193">Skype for Business desktop client 2016 (32-bit and 64-bit versions)</span></span>
  - <span data-ttu-id="c7932-194">Lync デスクトップ クライアント 2013 (32 ビット版と 64 ビット版)</span><span class="sxs-lookup"><span data-stu-id="c7932-194">Lync desktop client 2013 (32-bit and 64-bit versions)</span></span>
  - <span data-ttu-id="c7932-195">Microsoft Teams でサポートされるすべての IP 電話モデル。</span><span class="sxs-lookup"><span data-stu-id="c7932-195">All IP phone models supported for Microsoft Teams.</span></span> <span data-ttu-id="c7932-196">[「Skype for Business Online の電話を取得する」を参照してください](/skypeforbusiness/what-is-phone-system-in-office-365/getting-phones-for-skype-for-business-online/getting-phones-for-skype-for-business-online)。</span><span class="sxs-lookup"><span data-stu-id="c7932-196">See [Getting phones for Skype for Business Online](/skypeforbusiness/what-is-phone-system-in-office-365/getting-phones-for-skype-for-business-online/getting-phones-for-skype-for-business-online).</span></span>
  - <span data-ttu-id="c7932-197">Mac版  Skype for Business クライアント (バージョン 16.8.196 以降)</span><span class="sxs-lookup"><span data-stu-id="c7932-197">Mac Skype for Business Client (version 16.8.196 and later)</span></span>
  - <span data-ttu-id="c7932-198">Aandroid Skype for Business クライアント (バージョン 6.16.0.9 以降)</span><span class="sxs-lookup"><span data-stu-id="c7932-198">Android Skype for Business Client (version 6.16.0.9 and later)</span></span>
  - <span data-ttu-id="c7932-199">iPhone Skype for Business Client クライアント(バージョン 6.16.0 以降)</span><span class="sxs-lookup"><span data-stu-id="c7932-199">iPhone Skype for Business Client (version 6.16.0 and later)</span></span>
  - <span data-ttu-id="c7932-200">Mac版  Skype for Business クライアント (バージョン 6.16.0 以降)</span><span class="sxs-lookup"><span data-stu-id="c7932-200">iPad Skype for Business Client (version 6.16.0 and later)</span></span>
  - <span data-ttu-id="c7932-201">Microsoft Teams Windows クライアント (32 ビット版と 64 ビット版)</span><span class="sxs-lookup"><span data-stu-id="c7932-201">Microsoft Teams Windows client (32-bit and 64-bit versions)</span></span>
  - <span data-ttu-id="c7932-202">Microsoft Teams Mac クライアント</span><span class="sxs-lookup"><span data-stu-id="c7932-202">Microsoft Teams Mac client</span></span>
  - <span data-ttu-id="c7932-203">Microsoft Teams iPhone アプリ</span><span class="sxs-lookup"><span data-stu-id="c7932-203">Microsoft Teams iPhone app</span></span>
  - <span data-ttu-id="c7932-204">Microsoft Teams Android アプリ</span><span class="sxs-lookup"><span data-stu-id="c7932-204">Microsoft Teams Android app</span></span>

    > [!NOTE]
    > <span data-ttu-id="c7932-205">直接ルーティング番号が割り当てられている通話キューは、エージェントとして Skype for Business クライアント、Lync クライアント、または Skype for Business IP Phone をサポートしません。</span><span class="sxs-lookup"><span data-stu-id="c7932-205">Call queues that are assigned a direct routing number don't support Skype for Business clients, Lync clients, or Skype for Business IP Phones as agents.</span></span>

## <a name="call-queue-cmdlets"></a><span data-ttu-id="c7932-206">通話キューのコマンドレット</span><span class="sxs-lookup"><span data-stu-id="c7932-206">Call queue cmdlets</span></span>

<span data-ttu-id="c7932-207">Windows PowerShell を使用して通話キューを作成し、設定することもできます。</span><span class="sxs-lookup"><span data-stu-id="c7932-207">You can also use Windows PowerShell to create and set up call queues.</span></span> <span data-ttu-id="c7932-208">通話キューの管理に使用するコマンドレットは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="c7932-208">Here are the cmdlets that you use to manage a call queue.</span></span>

- [<span data-ttu-id="c7932-209">New-CsCallQueue</span><span class="sxs-lookup"><span data-stu-id="c7932-209">New-CsCallQueue</span></span>](https://docs.microsoft.com/powershell/module/skype/new-CsCallQueue)

- [<span data-ttu-id="c7932-210">Set-CsCallQueue</span><span class="sxs-lookup"><span data-stu-id="c7932-210">Set-CsCallQueue</span></span>](https://docs.microsoft.com/powershell/module/skype/set-CsCallQueue)

- [<span data-ttu-id="c7932-211">Get-CsCallQueue</span><span class="sxs-lookup"><span data-stu-id="c7932-211">Get-CsCallQueue</span></span>](https://docs.microsoft.com/powershell/module/skype/get-CsCallQueue)

- [<span data-ttu-id="c7932-212">Remove-CsCallQueue</span><span class="sxs-lookup"><span data-stu-id="c7932-212">Remove-CsCallQueue</span></span>](https://docs.microsoft.com/powershell/module/skype/remove-CsCallQueue)

## <a name="related-topics"></a><span data-ttu-id="c7932-213">関連トピック</span><span class="sxs-lookup"><span data-stu-id="c7932-213">Related topics</span></span>

[<span data-ttu-id="c7932-214">電話システムで利用できる機能</span><span class="sxs-lookup"><span data-stu-id="c7932-214">Here's what you get with Phone System</span></span>](here-s-what-you-get-with-phone-system.md)

[<span data-ttu-id="c7932-215">サービス電話番号を取得する</span><span class="sxs-lookup"><span data-stu-id="c7932-215">Getting service phone numbers</span></span>](getting-service-phone-numbers.md)

[<span data-ttu-id="c7932-216">国および地域ごとの電話会議および通話プランの利用可能性</span><span class="sxs-lookup"><span data-stu-id="c7932-216">Country and region availability for Audio Conferencing and Calling Plans</span></span>](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)

[<span data-ttu-id="c7932-217">New-CsOnlineApplicationInstance</span><span class="sxs-lookup"><span data-stu-id="c7932-217">New-CsOnlineApplicationInstance</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csonlineapplicationinstance)

[<span data-ttu-id="c7932-218">Windows PowerShell と Skype for Business Online の概要</span><span class="sxs-lookup"><span data-stu-id="c7932-218">An introduction to Windows PowerShell and Skype for Business Online</span></span>](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)
