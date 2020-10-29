---
title: 呼び出しキューを作成する
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
description: Microsoft Teams で通話キューの電話システムをセットアップする方法について説明します。これにより、グリーティングメッセージの送信、音楽の保留、リダイレクト、その他の機能を行うことができます。
ms.openlocfilehash: 31826d1090835a073551e3639cb6105feb16d650
ms.sourcegitcommit: e07b2d7470b93e52b9e85207db0d6fa3a136efd9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/28/2020
ms.locfileid: "48793525"
---
# <a name="create-a-call-queue"></a><span data-ttu-id="a2644-103">呼び出しキューを作成する</span><span class="sxs-lookup"><span data-stu-id="a2644-103">Create a call queue</span></span>

<span data-ttu-id="a2644-104">通話キューには、特定の問題や質問について支援できる組織内のユーザーに、発信者をルーティングする方法が用意されています。</span><span class="sxs-lookup"><span data-stu-id="a2644-104">Call queues provide a method of routing callers to people in your organization who can help with with a particular issue or question.</span></span> <span data-ttu-id="a2644-105">通話は、キュー内のユーザー ( *エージェント* と呼ばれます) に一度に1つずつ配布されます。</span><span class="sxs-lookup"><span data-stu-id="a2644-105">Calls are distributed one at a time to the people in the queue (who are known as *agents* ).</span></span> 

<span data-ttu-id="a2644-106">通話キューでは次の情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="a2644-106">Call queues provide:</span></span>

- <span data-ttu-id="a2644-107">あいさつメッセージ。</span><span class="sxs-lookup"><span data-stu-id="a2644-107">A greeting message.</span></span>

- <span data-ttu-id="a2644-108">他のユーザーがキューで待機中の音楽</span><span class="sxs-lookup"><span data-stu-id="a2644-108">Music while people are waiting on hold in a queue.</span></span>

- <span data-ttu-id="a2644-109">*まず、* ルーティング先 (FIFO) の順に呼び出します。</span><span class="sxs-lookup"><span data-stu-id="a2644-109">Call routing - in *First In, First Out* (FIFO) order - to agents.</span></span>

- <span data-ttu-id="a2644-110">キューのオーバーフローとタイムアウトのオプション。</span><span class="sxs-lookup"><span data-stu-id="a2644-110">Handling options for queue overflow and timeout.</span></span>

<span data-ttu-id="a2644-111">この記事に記載されている手順を実行する前に、「 [Teams の自動応答と通話キューのプラン](plan-auto-attendant-call-queue.md) 」を参照し、 [作業の開始の手順](plan-auto-attendant-call-queue.md#getting-started) に従っていることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="a2644-111">Be sure you have read [Plan for Teams auto attendants and call queues](plan-auto-attendant-call-queue.md) and followed the [getting started steps](plan-auto-attendant-call-queue.md#getting-started) before you follow the procedures in this articles.</span></span>

<span data-ttu-id="a2644-112">通話キューを設定するには、Teams 管理センターで、[ **音声** ]、[ **通話キュー** ] の順に展開し、[ **追加** ] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a2644-112">To set up a call queue, in the Teams admin center, expand **Voice** , click **Call queues** , and then click **Add** .</span></span>

## <a name="resource-account-and-language"></a><span data-ttu-id="a2644-113">リソースアカウントと言語</span><span class="sxs-lookup"><span data-stu-id="a2644-113">Resource account and language</span></span>

![](media/call-queue-name-language.png)

1. <span data-ttu-id="a2644-114">通話キューの名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="a2644-114">Type a name for the call queue.</span></span> <span data-ttu-id="a2644-115">キューからの着信通話を受信すると、エージェントはこの名前を表示します。</span><span class="sxs-lookup"><span data-stu-id="a2644-115">Agents will see this name when they receive an incoming call from the queue.</span></span>

2. <span data-ttu-id="a2644-116">[ **アカウントの追加** ] をクリックし、この通話キューで使用するリソースアカウントを検索して、[ **追加** ]、[ **追加** ] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="a2644-116">Click **Add accounts** , search for the resource account that you want to use with this call queue, click **Add** , and then click **Add** .</span></span>

3. <span data-ttu-id="a2644-117">言語を選択します。</span><span class="sxs-lookup"><span data-stu-id="a2644-117">Choose a language.</span></span> <span data-ttu-id="a2644-118">この言語は、システムによって生成される音声プロンプトとボイスメール (有効にしている場合) に使用されます。</span><span class="sxs-lookup"><span data-stu-id="a2644-118">This language will be used for system-generated voice prompts and voicemail transcription (if you enable them).</span></span>

## <a name="greetings-and-hold-music"></a><span data-ttu-id="a2644-119">グリーティングと音楽の保留</span><span class="sxs-lookup"><span data-stu-id="a2644-119">Greetings and hold music</span></span>

<span data-ttu-id="a2644-120">キューに到着したときに応答メッセージを再生するかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="a2644-120">Specify if you want to play a greeting to callers when they arrive in the queue.</span></span> <span data-ttu-id="a2644-121">再生する応答メッセージが含まれている MP3、WAV、または WMA ファイルをアップロードする必要があります。</span><span class="sxs-lookup"><span data-stu-id="a2644-121">You must upload an MP3, WAV, or WMA file containing the greeting that you want to play.</span></span>

<span data-ttu-id="a2644-122">チームはキュー内で保留中の場合、既定の音楽を発信者に提供します。</span><span class="sxs-lookup"><span data-stu-id="a2644-122">Teams provides default music to callers while they are on hold in a queue.</span></span> <span data-ttu-id="a2644-123">特定のオーディオファイルを再生する場合は、[ **オーディオファイルの再生** ] を選択し、MP3、WAV、または WMA ファイルをアップロードします。</span><span class="sxs-lookup"><span data-stu-id="a2644-123">If you want to play a specific audio file, choose **Play an audio file** and upload an MP3, WAV, or WMA file.</span></span>

> [!NOTE]
> <span data-ttu-id="a2644-124">アップロードされたレコーディングのサイズは、5 MB 以下でなければなりません。</span><span class="sxs-lookup"><span data-stu-id="a2644-124">The uploaded recording can be no larger than 5 MB.</span></span>
> <span data-ttu-id="a2644-125">Teams の通話キューに用意されている既定の音楽は、組織によって支払われる印税のうち、無料です。</span><span class="sxs-lookup"><span data-stu-id="a2644-125">The default music supplied in Teams call queues is free of any royalties payable by your organization.</span></span> 

## <a name="call-agents"></a><span data-ttu-id="a2644-126">通話エージェント</span><span class="sxs-lookup"><span data-stu-id="a2644-126">Call agents</span></span>

<span data-ttu-id="a2644-127">選択されているコールエージェントは、次のいずれかである必要があります。</span><span class="sxs-lookup"><span data-stu-id="a2644-127">Call agents selected must be one of the following:</span></span> 

- <span data-ttu-id="a2644-128">電話システムのライセンスを持つオンラインユーザーとエンタープライズ Voip が有効になっている</span><span class="sxs-lookup"><span data-stu-id="a2644-128">Online users with a Phone System license and Enterprise Voice enabled</span></span>
- <span data-ttu-id="a2644-129">通話プランを使用するオンラインユーザー</span><span class="sxs-lookup"><span data-stu-id="a2644-129">Online users with a Calling Plan</span></span>
- <span data-ttu-id="a2644-130">オンプレミスの Skype for Business Server ユーザー</span><span class="sxs-lookup"><span data-stu-id="a2644-130">On-premises Skype for Business Server users</span></span>
- <span data-ttu-id="a2644-131">使用しているエージェントで、Microsoft Teams アプリを呼び出しキューとして使用している場合は、そのモードである必要があります。</span><span class="sxs-lookup"><span data-stu-id="a2644-131">If your agents are using the Microsoft Teams app for call queue calls, they need to be in TeamsOnly mode.</span></span>

![](media/call-queue-users-groups.png)

<span data-ttu-id="a2644-132">最大20個のエージェントを個別に追加したり、グループを使用して最大で200のエージェントを追加したりできます。</span><span class="sxs-lookup"><span data-stu-id="a2644-132">You can add up to 20 agents individually and up to 200 agents via groups.</span></span>

<span data-ttu-id="a2644-133">キューにユーザーを追加するには、[ **ユーザーの追加** ] をクリックし、ユーザーを検索して [ **追加** ] をクリックし、[ **追加** ] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a2644-133">To add a user to the queue, click **Add users** , search for the user, click **Add** , and then click **Add** .</span></span>

<span data-ttu-id="a2644-134">キューにグループを追加するには、[ **グループの追加** ] をクリックし、グループを検索して [ **追加** ] をクリックし、[ **追加** ] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a2644-134">To add a group to the queue, click **Add groups** , search for the group, click **Add** , and then click **Add** .</span></span> <span data-ttu-id="a2644-135">配布リスト、セキュリティグループ、Microsoft 365 グループ、または Microsoft Teams teams を使用できます。</span><span class="sxs-lookup"><span data-stu-id="a2644-135">You can use distribution lists, security groups, and Microsoft 365 groups or Microsoft Teams teams.</span></span>

> [!NOTE]
> <span data-ttu-id="a2644-136">グループに追加された新規ユーザーは、最初の通話が到着するまでに最大8時間かかることがあります。</span><span class="sxs-lookup"><span data-stu-id="a2644-136">New users added to a group can take up to eight hours for their first call to arrive.</span></span>

## <a name="call-routing"></a><span data-ttu-id="a2644-137">通話ルーティング</span><span class="sxs-lookup"><span data-stu-id="a2644-137">Call routing</span></span>

![](media/call-queue-conference-mode-routing-method.png)

<span data-ttu-id="a2644-138">**会議モード** では、エージェントが通話を受け入れた後に、発信者がエージェントに接続するのにかかる時間が大幅に短縮されます。</span><span class="sxs-lookup"><span data-stu-id="a2644-138">**Conference mode** significantly reduces the amount of time it takes for a caller to be connected to an agent, after the agent accepts the call.</span></span> <span data-ttu-id="a2644-139">会議モードで機能するには、通話キュー内のエージェントで次のいずれかのクライアントを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a2644-139">For conference mode to work, agents in the call queue must use one of the following clients:</span></span>

  - <span data-ttu-id="a2644-140">最新バージョンの Microsoft Teams デスクトップクライアント、Android アプリ、または iOS アプリ</span><span class="sxs-lookup"><span data-stu-id="a2644-140">The latest version of the Microsoft Teams desktop client, Android app, or iOS app</span></span>
  - <span data-ttu-id="a2644-141">Microsoft Teams phone バージョン 1449/1.0.94.2020051601 以降</span><span class="sxs-lookup"><span data-stu-id="a2644-141">Microsoft Teams phone version 1449/1.0.94.2020051601 or later</span></span>
  
<span data-ttu-id="a2644-142">エージェントの Teams アカウントは、チーム専用モードに設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a2644-142">Agents' Teams accounts need to be set to Teams-only mode.</span></span> <span data-ttu-id="a2644-143">要件を満たしていないエージェントは、通話ルーティングリストに含まれません。</span><span class="sxs-lookup"><span data-stu-id="a2644-143">Agents who don't meet the requirements aren't included in the call routing list.</span></span> <span data-ttu-id="a2644-144">すべてのエージェントが互換性のあるクライアントを使用している場合は、通話キューの会議モードを有効にすることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="a2644-144">We recommend enabling conference mode for your call queues if your agents are all using compatible clients.</span></span>

> [!NOTE]
> <span data-ttu-id="a2644-145">Busy がビジー状態であるため、会議モードでサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="a2644-145">Busy on Busy is not supported by conference mode.</span></span> <span data-ttu-id="a2644-146">プレゼンスベースのルーティングが有効になっていない場合は、着信キュー以外の通話に含まれているエージェントでも、通話キューの呼び出しと共に表示されることがあります。</span><span class="sxs-lookup"><span data-stu-id="a2644-146">Agents on non-call queue calls may still be presented with a call queue call if presence-based routing is not enabled.</span></span>

<span data-ttu-id="a2644-147">**ルーティングメソッド** は、エージェントがキューから呼び出しを受け取る順序を決定します。</span><span class="sxs-lookup"><span data-stu-id="a2644-147">**Routing method** determines the order in which agents receive calls from the queue.</span></span> <span data-ttu-id="a2644-148">以下のオプションから選択します。</span><span class="sxs-lookup"><span data-stu-id="a2644-148">Choose from these options:</span></span>

- <span data-ttu-id="a2644-149">**応答ルーティング** は、キュー内のすべてのエージェントを同時に呼び出します。</span><span class="sxs-lookup"><span data-stu-id="a2644-149">**Attendant routing** rings all agents in the queue at the same time.</span></span> <span data-ttu-id="a2644-150">通話を受ける最初のコールエージェントは、通話を受け取ります。</span><span class="sxs-lookup"><span data-stu-id="a2644-150">The first call agent to pick up the call gets the call.</span></span>

- <span data-ttu-id="a2644-151">**シリアルルーティング** は **、通話エージェントリストで** 指定された順序で、すべての通話エージェントを1つずつ呼び出します。</span><span class="sxs-lookup"><span data-stu-id="a2644-151">**Serial routing** rings all call agents one by one in the order specified in the **Call agents** list.</span></span> <span data-ttu-id="a2644-152">エージェントが終了した場合、または通話を受信しなかった場合、通話は次のエージェントを呼び出し、それが処理されるかタイムアウトするまで、すべてのエージェントを試します。</span><span class="sxs-lookup"><span data-stu-id="a2644-152">If an agent dismisses or does not pick up a call, the call will ring the next agent and will try all agents until it is picked up or times out.</span></span>

- <span data-ttu-id="a2644-153">**ラウンドロビン** は、着信呼び出しのルーティングを保留して、各通話エージェントがキューから同じ回数の通話を取得できるようにします。</span><span class="sxs-lookup"><span data-stu-id="a2644-153">**Round robin** balances the routing of incoming calls so that each call agent gets the same number of calls from the queue.</span></span> <span data-ttu-id="a2644-154">これは、すべての通話エージェントで同一の営業案件を確保するために、着信の販売環境で望ましい場合があります。</span><span class="sxs-lookup"><span data-stu-id="a2644-154">This may be desirable in an inbound sales environment to assure equal opportunity among all the call agents.</span></span>

- <span data-ttu-id="a2644-155">[ **最長アイドル** 時間 (idle) を選びます。通話は、アイドル状態になっているエージェントへの通話ごとに最も長い時間がかかる。</span><span class="sxs-lookup"><span data-stu-id="a2644-155">**Longest idle** routes each call to the agent who has been idle the longest time.</span></span> <span data-ttu-id="a2644-156">エージェントは、プレゼンス状態が利用可能な場合、またはプレゼンス状態が10分未満に退席中の場合に、アイドルと見なされます。</span><span class="sxs-lookup"><span data-stu-id="a2644-156">An agent is considered idle if their presence state is Available or if their presence state has been Away for less than 10 minutes.</span></span> <span data-ttu-id="a2644-157">10分以上放置されているプレゼンス状態を持つエージェントは、アイドルと見なされず、通話を受信可能に変更するまで、着信を受けることはできません。</span><span class="sxs-lookup"><span data-stu-id="a2644-157">Agents whose presence state has been Away for more than 10 minutes are not considered idle and will not be eligible to receive calls until they change their presence to Available.</span></span> 

![](media/call-queue-presence-agents-time.png)


<span data-ttu-id="a2644-158">**プレゼンスベースのルーティング** では、選択したルーティングメソッドの呼び出しルーティングリストにエージェントを含める必要があるかどうかを判断するために、通話エージェントの状態が使用可能になります。</span><span class="sxs-lookup"><span data-stu-id="a2644-158">**Presence-based routing** uses the availability status of call agents to determine whether an agent should be included in the call routing list for the selected routing method.</span></span> <span data-ttu-id="a2644-159">連絡可能状態が [ **利用可能** ] に設定されている通話エージェントは、通話ルーティングリストに含まれており、着信を受け取ることができます。</span><span class="sxs-lookup"><span data-stu-id="a2644-159">Call agents whose availability status is set to **Available** are included in the call routing list and can receive calls.</span></span> <span data-ttu-id="a2644-160">可用性の状態が「その他」の状態に設定されているエージェントは、通話ルーティングリストから除外され、その状態が [連絡 **可能** ] に戻るまでは通話を受信しません。</span><span class="sxs-lookup"><span data-stu-id="a2644-160">Agents whose availability status is set to any other status are excluded from the call routing list and won't receive calls until their availability status changes back to **Available** .</span></span> 

<span data-ttu-id="a2644-161">任意のルーティング方法を使って、プレゼンスベースの通話ルーティングを有効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="a2644-161">You can enable presence-based call routing with any of the routing methods.</span></span>

<span data-ttu-id="a2644-162">エージェントによって通話が発信されない場合、その状態がどのように設定されているかにかかわらず、通話ルーティングリストに含まれません。</span><span class="sxs-lookup"><span data-stu-id="a2644-162">If an agent opts out of getting calls, they won't be included in the call routing list regardless of what their availability status is set to.</span></span> 

> [!NOTE]
> <span data-ttu-id="a2644-163">プレゼンスベースのルーティングが有効になっている場合、Skype for Business クライアントを使用するエージェントは、通話ルーティングリストに含まれません。</span><span class="sxs-lookup"><span data-stu-id="a2644-163">Agents who use the Skype for Business client aren't included in the call routing list when presence-based routing is enabled.</span></span> <span data-ttu-id="a2644-164">Skype for Business を使用するエージェントがある場合は、プレゼンスベースの通話ルーティングを有効にしないでください。</span><span class="sxs-lookup"><span data-stu-id="a2644-164">If you have agents who use Skype for Business, don't enable presence-based call routing.</span></span>

<span data-ttu-id="a2644-165">[ **エージェントの通知時間** ] は、エージェントの電話が次のエージェントへの呼び出しをリダイレクトするまでの、エージェントの電話が着信するまでの時間を指定します。</span><span class="sxs-lookup"><span data-stu-id="a2644-165">**Agent alert time** specifies how long an agent's phone will ring before the queue redirects the call to the next agent.</span></span>

<span data-ttu-id="a2644-166">高ボリュームキューの場合は、次の設定をお勧めします。</span><span class="sxs-lookup"><span data-stu-id="a2644-166">For high volume queues, we recommend the following settings:</span></span>

- <span data-ttu-id="a2644-167">**自動\*\*\*\*会議モード**</span><span class="sxs-lookup"><span data-stu-id="a2644-167">**Conference mode** to **Auto**</span></span>
- <span data-ttu-id="a2644-168">**ルーティングメソッド** と **アテンダントルーティング**</span><span class="sxs-lookup"><span data-stu-id="a2644-168">**Routing method** to **Attendant routing**</span></span>
- <span data-ttu-id="a2644-169">**オン** になった **プレゼンスベースのルーティング**</span><span class="sxs-lookup"><span data-stu-id="a2644-169">**Presence-based routing** to **On**</span></span>
- <span data-ttu-id="a2644-170">**エージェントの通知時間:** **20 秒**</span><span class="sxs-lookup"><span data-stu-id="a2644-170">**Agent alert time:** to **20 seconds**</span></span>

## <a name="call-overflow-handling"></a><span data-ttu-id="a2644-171">通話オーバーフロー処理</span><span class="sxs-lookup"><span data-stu-id="a2644-171">Call overflow handling</span></span>

![](media/call-queue-overflow-handling.png)

<span data-ttu-id="a2644-172">**キュー内の最大の通話** キューで待機できる通話の最大数を指定します。</span><span class="sxs-lookup"><span data-stu-id="a2644-172">**Maximum calls in the queue** specifies the maximum number of calls that can wait in the queue at any given time.</span></span> <span data-ttu-id="a2644-173">既定値は50ですが、0 ~ 200 の範囲で指定できます。</span><span class="sxs-lookup"><span data-stu-id="a2644-173">The default is 50, but it can range from 0 to 200.</span></span> <span data-ttu-id="a2644-174">この制限に達すると、通話 **の最大数に達したとき** にによって指定された呼び出しが処理されます。</span><span class="sxs-lookup"><span data-stu-id="a2644-174">When this limit is reached, the call is handled as specified by the **When the maximum number of calls is reached** setting.</span></span>

<span data-ttu-id="a2644-175">通話を切断するか、いずれかの通話ルーティング先にリダイレクトするかを選択できます。</span><span class="sxs-lookup"><span data-stu-id="a2644-175">You can choose to disconnect the call or redirect it to one of the call routing destinations.</span></span> <span data-ttu-id="a2644-176">たとえば、キュー内のエージェントのボイスメールを発信者が退出させている場合があります。</span><span class="sxs-lookup"><span data-stu-id="a2644-176">For example, you might have the caller leave a voicemail for the agents in the queue.</span></span>

> [!NOTE]
> <span data-ttu-id="a2644-177">通話の最大数が0に設定されている場合、グリーティングメッセージは再生されません。</span><span class="sxs-lookup"><span data-stu-id="a2644-177">If the maximum number of calls is set to 0 then the greeting message will not play.</span></span>

## <a name="call-timeout-handling"></a><span data-ttu-id="a2644-178">通話タイムアウト処理</span><span class="sxs-lookup"><span data-stu-id="a2644-178">Call timeout handling</span></span>

![](media/call-queue-timeout-handling.png)

<span data-ttu-id="a2644-179">**通話タイムアウト: 待ち時間** の最大値を指定すると、通話がリダイレクトされるか切断されるまでの間、キュー内で通話を保留できます。</span><span class="sxs-lookup"><span data-stu-id="a2644-179">**Call Timeout: maximum wait time** specifies the maximum time a call can be on hold in the queue before it is redirected or disconnected.</span></span> <span data-ttu-id="a2644-180">15秒から45分までの値を指定できます。</span><span class="sxs-lookup"><span data-stu-id="a2644-180">You can specify a value from 15 seconds to 45 minutes.</span></span>

<span data-ttu-id="a2644-181">通話を切断するか、いずれかの通話ルーティング先にリダイレクトするかを選択できます。</span><span class="sxs-lookup"><span data-stu-id="a2644-181">You can choose to disconnect the call or redirect it to one of the call routing destinations.</span></span> <span data-ttu-id="a2644-182">たとえば、キュー内のエージェントのボイスメールを発信者が退出させている場合があります。</span><span class="sxs-lookup"><span data-stu-id="a2644-182">For example, you might have the caller leave a voicemail for the agents in the queue.</span></span>

<span data-ttu-id="a2644-183">通話タイムアウトオプションを選んだら、[ **保存** ] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a2644-183">When you have selected your call timeout options, click **Save** .</span></span>

## <a name="caller-id-for-outbound-calls"></a><span data-ttu-id="a2644-184">発信通話の発信者番号</span><span class="sxs-lookup"><span data-stu-id="a2644-184">Caller ID for outbound calls</span></span>

<span data-ttu-id="a2644-185">通話キュー内のエージェントは、顧客からの通話を返すためにダイヤルアウトする可能性があるため、通話キューのメンバーの発信者番号を適切な自動応答のサービス番号に設定することを検討してください。</span><span class="sxs-lookup"><span data-stu-id="a2644-185">Since agents in a call queue may dial out to return a customer call, consider setting the caller ID for members of a call queue to the service number of an appropriate auto attendant.</span></span> <span data-ttu-id="a2644-186">詳細については、「 [Microsoft Teams で発信者番号通知ポリシーを管理](caller-id-policies.md) する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a2644-186">See [Manage caller ID policies in Microsoft Teams](caller-id-policies.md) for more information.</span></span>

## <a name="supported-clients"></a><span data-ttu-id="a2644-187">サポートされるクライアント</span><span class="sxs-lookup"><span data-stu-id="a2644-187">Supported clients</span></span>

- <span data-ttu-id="a2644-188">通話キューのコールエージェントでは、次のクライアントがサポートされています。</span><span class="sxs-lookup"><span data-stu-id="a2644-188">The following clients are supported for call agents in a call queue:</span></span>

  - <span data-ttu-id="a2644-189">Skype for Business デスクトップクライアント 2016 (32 ビットバージョンと64ビットバージョン)</span><span class="sxs-lookup"><span data-stu-id="a2644-189">Skype for Business desktop client 2016 (32-bit and 64-bit versions)</span></span>
  - <span data-ttu-id="a2644-190">Lync デスクトップクライアント 2013 (32 ビットバージョンと64ビットバージョン)</span><span class="sxs-lookup"><span data-stu-id="a2644-190">Lync desktop client 2013 (32-bit and 64-bit versions)</span></span>
  - <span data-ttu-id="a2644-191">Microsoft Teams でサポートされているすべての IP 電話モデル。</span><span class="sxs-lookup"><span data-stu-id="a2644-191">All IP phone models supported for Microsoft Teams.</span></span> <span data-ttu-id="a2644-192">「 [Skype For Business Online の電話を取得する」を](/skypeforbusiness/what-is-phone-system-in-office-365/getting-phones-for-skype-for-business-online/getting-phones-for-skype-for-business-online)参照してください。</span><span class="sxs-lookup"><span data-stu-id="a2644-192">See [Getting phones for Skype for Business Online](/skypeforbusiness/what-is-phone-system-in-office-365/getting-phones-for-skype-for-business-online/getting-phones-for-skype-for-business-online).</span></span>
  - <span data-ttu-id="a2644-193">Mac版  Skype for Business クライアント (バージョン 16.8.196 以降)</span><span class="sxs-lookup"><span data-stu-id="a2644-193">Mac Skype for Business Client (version 16.8.196 and later)</span></span>
  - <span data-ttu-id="a2644-194">Aandroid Skype for Business クライアント (バージョン 6.16.0.9 以降)</span><span class="sxs-lookup"><span data-stu-id="a2644-194">Android Skype for Business Client (version 6.16.0.9 and later)</span></span>
  - <span data-ttu-id="a2644-195">iPhone Skype for Business Client クライアント(バージョン 6.16.0 以降)</span><span class="sxs-lookup"><span data-stu-id="a2644-195">iPhone Skype for Business Client (version 6.16.0 and later)</span></span>
  - <span data-ttu-id="a2644-196">Mac版  Skype for Business クライアント (バージョン 6.16.0 以降)</span><span class="sxs-lookup"><span data-stu-id="a2644-196">iPad Skype for Business Client (version 6.16.0 and later)</span></span>
  - <span data-ttu-id="a2644-197">Microsoft Teams Windows クライアント (32 ビット版と64ビット版)</span><span class="sxs-lookup"><span data-stu-id="a2644-197">Microsoft Teams Windows client (32-bit and 64-bit versions)</span></span>
  - <span data-ttu-id="a2644-198">Microsoft Teams Mac クライアント</span><span class="sxs-lookup"><span data-stu-id="a2644-198">Microsoft Teams Mac client</span></span>
  - <span data-ttu-id="a2644-199">Microsoft Teams iPhone アプリ</span><span class="sxs-lookup"><span data-stu-id="a2644-199">Microsoft Teams iPhone app</span></span>
  - <span data-ttu-id="a2644-200">Microsoft Teams Android アプリ</span><span class="sxs-lookup"><span data-stu-id="a2644-200">Microsoft Teams Android app</span></span>

    > [!NOTE]
    > <span data-ttu-id="a2644-201">直接ルーティング番号が割り当てられている通話キューは、Skype for Business クライアント、Lync クライアント、または Skype for Business の IP 電話をエージェントとしてサポートしません。</span><span class="sxs-lookup"><span data-stu-id="a2644-201">Call queues that are assigned a direct routing number don't support Skype for Business clients, Lync clients, or Skype for Business IP Phones as agents.</span></span>

## <a name="call-queue-cmdlets"></a><span data-ttu-id="a2644-202">通話キューのコマンドレット</span><span class="sxs-lookup"><span data-stu-id="a2644-202">Call queue cmdlets</span></span>

<span data-ttu-id="a2644-203">Windows PowerShell を使用して通話キューを作成し、設定することもできます。</span><span class="sxs-lookup"><span data-stu-id="a2644-203">You can also use Windows PowerShell to create and set up call queues.</span></span> <span data-ttu-id="a2644-204">通話キューを管理するために使用するコマンドレットを以下に示します。</span><span class="sxs-lookup"><span data-stu-id="a2644-204">Here are the cmdlets that you use to manage a call queue.</span></span>

- [<span data-ttu-id="a2644-205">新規-CsCallQueue</span><span class="sxs-lookup"><span data-stu-id="a2644-205">New-CsCallQueue</span></span>](https://docs.microsoft.com/powershell/module/skype/new-CsCallQueue?view=skype-ps)

- [<span data-ttu-id="a2644-206">Set-CsCallQueue</span><span class="sxs-lookup"><span data-stu-id="a2644-206">Set-CsCallQueue</span></span>](https://docs.microsoft.com/powershell/module/skype/set-CsCallQueue?view=skype-ps)

- [<span data-ttu-id="a2644-207">Get-CsCallQueue</span><span class="sxs-lookup"><span data-stu-id="a2644-207">Get-CsCallQueue</span></span>](https://docs.microsoft.com/powershell/module/skype/get-CsCallQueue?view=skype-ps)

- [<span data-ttu-id="a2644-208">Remove-CsCallQueue</span><span class="sxs-lookup"><span data-stu-id="a2644-208">Remove-CsCallQueue</span></span>](https://docs.microsoft.com/powershell/module/skype/remove-CsCallQueue?view=skype-ps)

## <a name="related-topics"></a><span data-ttu-id="a2644-209">関連項目</span><span class="sxs-lookup"><span data-stu-id="a2644-209">Related topics</span></span>

[<span data-ttu-id="a2644-210">電話システムで利用できる機能</span><span class="sxs-lookup"><span data-stu-id="a2644-210">Here's what you get with Phone System</span></span>](here-s-what-you-get-with-phone-system.md)

[<span data-ttu-id="a2644-211">サービス電話番号を取得する</span><span class="sxs-lookup"><span data-stu-id="a2644-211">Getting service phone numbers</span></span>](getting-service-phone-numbers.md)

[<span data-ttu-id="a2644-212">国および地域ごとの電話会議および通話プランの利用可能性</span><span class="sxs-lookup"><span data-stu-id="a2644-212">Country and region availability for Audio Conferencing and Calling Plans</span></span>](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)

[<span data-ttu-id="a2644-213">新しい Csonline Applicationinstance</span><span class="sxs-lookup"><span data-stu-id="a2644-213">New-CsOnlineApplicationInstance</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csonlineapplicationinstance?view=skype-ps)

[<span data-ttu-id="a2644-214">Windows PowerShell と Skype for Business Online の概要</span><span class="sxs-lookup"><span data-stu-id="a2644-214">An introduction to Windows PowerShell and Skype for Business Online</span></span>](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)
