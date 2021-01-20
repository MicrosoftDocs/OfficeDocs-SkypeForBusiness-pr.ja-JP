---
title: Microsoft Teams で通話キューを作成する - 小規模ビジネス向けチュートリアル
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.reviewer: colongma
ms.topic: article
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
description: Microsoft 365 Business Voice で通話キューを設定する方法について説明します。
ms.openlocfilehash: 10bc19f122daab89c91a01db0ffa31f48739d96d
ms.sourcegitcommit: fdef9b52247097e5cae64f01b6b2b710c5b203cf
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/20/2021
ms.locfileid: "49909636"
---
# <a name="create-a-call-queue---small-business-tutorial"></a><span data-ttu-id="4f711-103">通話キューを作成する - 小規模ビジネス向けチュートリアル</span><span class="sxs-lookup"><span data-stu-id="4f711-103">Create a call queue - small business tutorial</span></span>

<span data-ttu-id="4f711-104">通話キューは、組織内の特定の問題や質問に役立つユーザーに発信者をルーティングする方法を提供します。</span><span class="sxs-lookup"><span data-stu-id="4f711-104">Call queues provide a method of routing callers to people in your organization who can help with with a particular issue or question.</span></span> <span data-ttu-id="4f711-105">通話はキュー内のユーザー (エージェントと呼ばれる) に一度に 1 つ配布 *されます*。</span><span class="sxs-lookup"><span data-stu-id="4f711-105">Calls are distributed one at a time to the people in the queue (who are known as *agents*).</span></span> 

<span data-ttu-id="4f711-106">通話キューには次の機能があります。</span><span class="sxs-lookup"><span data-stu-id="4f711-106">Call queues provide:</span></span>

- <span data-ttu-id="4f711-107">あいさつメッセージ。</span><span class="sxs-lookup"><span data-stu-id="4f711-107">A greeting message.</span></span>

- <span data-ttu-id="4f711-108">ユーザーがキューで保留を待っている間の音楽。</span><span class="sxs-lookup"><span data-stu-id="4f711-108">Music while people are waiting on hold in a queue.</span></span>

- <span data-ttu-id="4f711-109">エージェントへのコール ルーティング ( *First In、First Out* (FIRST Out ) 順序 (</span><span class="sxs-lookup"><span data-stu-id="4f711-109">Call routing - in *First In, First Out* (FIFO) order - to agents.</span></span>

- <span data-ttu-id="4f711-110">キュー のオーバーフローとタイムアウトの処理オプション。</span><span class="sxs-lookup"><span data-stu-id="4f711-110">Handling options for queue overflow and timeout.</span></span>

#### <a name="before-you-begin"></a><span data-ttu-id="4f711-111">開始する前に</span><span class="sxs-lookup"><span data-stu-id="4f711-111">Before you begin</span></span>

<span data-ttu-id="4f711-112">電話システム [の取得 - 仮想ユーザー ライセンス](../teams-add-on-licensing/virtual-user.md) をまだ持ってない場合は、仮想ユーザー ライセンスを取得します。</span><span class="sxs-lookup"><span data-stu-id="4f711-112">Get some [Phone System - Virtual User licenses](../teams-add-on-licensing/virtual-user.md) if you don't already have them.</span></span> <span data-ttu-id="4f711-113">セットアップする通話キューと自動応答ごとに 1 つ取得します。</span><span class="sxs-lookup"><span data-stu-id="4f711-113">Get one for each call queue and auto attendant that you plan to set up.</span></span> <span data-ttu-id="4f711-114">これらのライセンスは無料なので、後でセットアップを変更する場合に備え、追加のライセンスを取得する方法をお勧めしています。</span><span class="sxs-lookup"><span data-stu-id="4f711-114">These licenses are free, so we suggest getting a few extra in case you decide to make changes to your setup in the future.</span></span>

<span data-ttu-id="4f711-115">通話キュー内のエージェントがダイヤルアウトして顧客の通話を返す可能性がある場合は、通話エージェントの発信者番号をメインの電話番号または適切な自動応答の番号に設定します。</span><span class="sxs-lookup"><span data-stu-id="4f711-115">Since agents in a call queue may dial out to return a customer call, consider setting the caller ID for your call agents to your main phone number or the number of an appropriate auto attendant.</span></span> <span data-ttu-id="4f711-116">詳細 [については、「Microsoft Teams で発信者番号ポリシーを](../caller-id-policies.md) 管理する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4f711-116">See [Manage caller ID policies in Microsoft Teams](../caller-id-policies.md) for more information.</span></span>

<a name="steps"></a>

#### <a name="follow-these-steps-to-set-up-your-call-queue"></a><span data-ttu-id="4f711-117">通話キューをセットアップするには、次の手順に従います。</span><span class="sxs-lookup"><span data-stu-id="4f711-117">Follow these steps to set up your call queue</span></span>

# <a name="step-1brcreate-a-team"></a>[<span data-ttu-id="4f711-118">手順 1 <br> チームを作成する</span><span class="sxs-lookup"><span data-stu-id="4f711-118">Step 1<br>Create a team</span></span>](#tab/create-team)

<span data-ttu-id="4f711-119">通話キューを作成するときに、個々のユーザーをキューに追加するか、既存のセキュリティ グループ、Microsoft 365 グループ、または Microsoft Teams チームを使用できます。</span><span class="sxs-lookup"><span data-stu-id="4f711-119">When creating a call queue, you can add individual users to the queue, or you can use an existing security group, Microsoft 365 group, or Microsoft Teams team.</span></span> <span data-ttu-id="4f711-120">チームを使用することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="4f711-120">We recommend using a team.</span></span> <span data-ttu-id="4f711-121">これにより、キューのメンバーは互いにチャットしたり、アイデアを共有したり、顧客を支援するドキュメントや他のリソースを作成できます。</span><span class="sxs-lookup"><span data-stu-id="4f711-121">This allows members of the queue to chat with each other, share ideas, and create documents or other resources to help them help your customers.</span></span> <span data-ttu-id="4f711-122">また、チームは、発信者が数時間後にメッセージを残したり、キューが最大容量に達したりするためにボイス メールボックスを提供します。</span><span class="sxs-lookup"><span data-stu-id="4f711-122">A team also provides a voice mailbox for callers to leave a message after hours or if the queue reaches its maximum capacity.</span></span>

<span data-ttu-id="4f711-123">チームを作成するには</span><span class="sxs-lookup"><span data-stu-id="4f711-123">To create a team</span></span>

1. <span data-ttu-id="4f711-124">まず、アプリ **の左側にある [Teams]** をクリックし、[参加] をクリックするか、チーム リストの下部にあるチームを作成します。</span><span class="sxs-lookup"><span data-stu-id="4f711-124">First, click **Teams** on the left side of the app, then click **Join or create a team** at the bottom of your teams list.</span></span>

2. <span data-ttu-id="4f711-125">次に、[ **チームの作成]** (最初のカード、左上隅) をクリックします。</span><span class="sxs-lookup"><span data-stu-id="4f711-125">Then click **Create team** (first card, top left corner).</span></span>

3. <span data-ttu-id="4f711-126">[チーム **を一から作成] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="4f711-126">Choose **Build a team from scratch**.</span></span>

4. <span data-ttu-id="4f711-127">次に、パブリック チームとプライベート チームの選択を行います。</span><span class="sxs-lookup"><span data-stu-id="4f711-127">Next, choose whether you want a public or private team.</span></span> <span data-ttu-id="4f711-128">チームに **参加** することで、ユーザーが意図せずにキューに参加することを避けるために、通話キューにプライベートを使用することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="4f711-128">We recommend **Private** for your call queue to avoid people unintentionally becoming part of the queue by joining the team.</span></span>

5. <span data-ttu-id="4f711-129">チームに名前を付け、オプションの説明を追加します。</span><span class="sxs-lookup"><span data-stu-id="4f711-129">Name your team and add an optional description.</span></span>

6. <span data-ttu-id="4f711-130">完了したら、[作成] をクリック **します**。</span><span class="sxs-lookup"><span data-stu-id="4f711-130">When you're done, click **Create**.</span></span>

8. <span data-ttu-id="4f711-131">通話キューに追加するユーザーの名前を入力し、[追加] をクリック **します**。</span><span class="sxs-lookup"><span data-stu-id="4f711-131">Type the names of the people that you want to have in your call queue, and then click **Add**.</span></span>

9. <span data-ttu-id="4f711-132">[**閉じる**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="4f711-132">Click **Close**.</span></span> <span data-ttu-id="4f711-133">チームに追加したユーザーには、チームのメンバーになれたというメールが送信され、チームがチーム リストに表示されます。</span><span class="sxs-lookup"><span data-stu-id="4f711-133">People you add to a team will receive an email letting them know they are now a member of your team and the team will show up in their teams list.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="4f711-134">手順 2 - リソース アカウントの></span><span class="sxs-lookup"><span data-stu-id="4f711-134">Step 2 - Resource accounts ></span></span>](https://review.docs.microsoft.com/microsoftteams/business-voice/create-a-phone-system-call-queue-smb?branch=mikeplum-smb-voice&tabs=resource-account#steps)

# <a name="step-2brresource-accounts"></a>[<span data-ttu-id="4f711-135">手順 2 <br> リソース アカウント</span><span class="sxs-lookup"><span data-stu-id="4f711-135">Step 2<br>Resource accounts</span></span>](#tab/resource-account)

<span data-ttu-id="4f711-136">作成する各通話キューには、リソース アカウントが必要です。</span><span class="sxs-lookup"><span data-stu-id="4f711-136">Each call queue that you create requires a resource account.</span></span> <span data-ttu-id="4f711-137">これはユーザー アカウントに似ていますが、アカウントがユーザーではなく自動応答または通話キューに関連付けられている場合を除きます。</span><span class="sxs-lookup"><span data-stu-id="4f711-137">This is similar to a user account, except the account is associated with an auto attendant or call queue instead of a person.</span></span> <span data-ttu-id="4f711-138">この手順では、アカウントを作成し *、Microsoft 365* 電話システム - 仮想ユーザー ライセンスを割り当て、それを使用して通話キューの作成を開始します。</span><span class="sxs-lookup"><span data-stu-id="4f711-138">In this step, we'll create the account, assign it a *Microsoft 365 Phone System - Virtual User* license, and then use it to start creating the call queue.</span></span>

### <a name="create-a-resource-account"></a><span data-ttu-id="4f711-139">リソース アカウントを作成する</span><span class="sxs-lookup"><span data-stu-id="4f711-139">Create a resource account</span></span>

<span data-ttu-id="4f711-140">Teams 管理センターでリソース アカウントを作成できます。</span><span class="sxs-lookup"><span data-stu-id="4f711-140">You can create a resource account in the Teams admin center.</span></span>

1. <span data-ttu-id="4f711-141">Teams 管理センターで、組織全体の設定 **を** 展開し、[リソース アカウント] **をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="4f711-141">In the Teams admin center, expand **Org-wide settings**, and then click **Resource accounts**.</span></span>

2. <span data-ttu-id="4f711-142">**[追加]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="4f711-142">Click **Add**.</span></span>

3. <span data-ttu-id="4f711-143">[リソース アカウント **の追加]** ウィンドウで、表示 **名**、ユーザー名を入力し、[リソース アカウントの種類] の **[** 通話キュー **] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="4f711-143">In the **Add resource account** pane, fill out **Display name**, **Username**, and choose **Call queue** for the **Resource account type**.</span></span>

    ![リソース アカウントのユーザー インターフェイスの追加のスクリーンショット](../media/resource-account-add-cq.png)

4. <span data-ttu-id="4f711-145">**[保存]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="4f711-145">Click **Save**.</span></span>

<span data-ttu-id="4f711-146">新しいアカウントがアカウントの一覧に表示されます。</span><span class="sxs-lookup"><span data-stu-id="4f711-146">The new account will appear in the list of accounts.</span></span>

![リソース アカウントの一覧のスクリーンショット](../media/resource-accounts-page.png)

### <a name="assign-a-license"></a><span data-ttu-id="4f711-148">ライセンスを割り当てる</span><span class="sxs-lookup"><span data-stu-id="4f711-148">Assign a license</span></span>

<span data-ttu-id="4f711-149">Microsoft *365* 電話システム - 仮想ユーザー ライセンスをリソース アカウントに割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="4f711-149">You must assign a *Microsoft 365 Phone System - Virtual User* license to the resource account.</span></span>

1. <span data-ttu-id="4f711-150">Microsoft 365 管理センターで、ライセンスを割り当てるリソース アカウントをクリックします。</span><span class="sxs-lookup"><span data-stu-id="4f711-150">In the Microsoft 365 admin center, click the resource account to which you want to assign a license.</span></span>

2. <span data-ttu-id="4f711-151">[ライセンスと **アプリ] タブの** [ **ライセンス]** で **、[Microsoft 365 電話システム - 仮想ユーザー] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="4f711-151">On the **Licenses and Apps** tab, under **Licenses**, select **Microsoft 365 Phone System - Virtual User**.</span></span>

3. <span data-ttu-id="4f711-152">[変更を **保存] をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="4f711-152">Click **Save changes**.</span></span>

    ![Microsoft 365 管理センターのライセンスの割り当てユーザー インターフェイスのスクリーンショット](../media/resource-account-assign-virtual-user-license.png)

### <a name="create-a-call-queue"></a><span data-ttu-id="4f711-154">呼び出しキューを作成する</span><span class="sxs-lookup"><span data-stu-id="4f711-154">Create a call queue</span></span>

<span data-ttu-id="4f711-155">次に、新しい通話キューの作成を開始し、リソース アカウントを割り当てします。</span><span class="sxs-lookup"><span data-stu-id="4f711-155">Next, we'll start creating a new call queue and assign the resource account.</span></span>

1. <span data-ttu-id="4f711-156">Teams 管理センターで、[音声] を **展開** し、[ **通話** キュー] をクリックして、[追加] をクリック **します**。</span><span class="sxs-lookup"><span data-stu-id="4f711-156">In the Teams admin center, expand **Voice**, click **Call queues**, and then click **Add**.</span></span>

1. <span data-ttu-id="4f711-157">通話キューの名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="4f711-157">Type a name for the call queue.</span></span> <span data-ttu-id="4f711-158">エージェントは、キューからの着信通話を受信すると、この名前を表示します。</span><span class="sxs-lookup"><span data-stu-id="4f711-158">Agents will see this name when they receive an incoming call from the queue.</span></span>

2. <span data-ttu-id="4f711-159">[**アカウントの追加]** をクリックし、この通話キューで使用するリソース アカウントを検索し、[追加] をクリックして、[追加] をクリック **します**。</span><span class="sxs-lookup"><span data-stu-id="4f711-159">Click **Add accounts**, search for the resource account that you want to use with this call queue, click **Add**, and then click **Add**.</span></span>

3. <span data-ttu-id="4f711-160">言語を選択します。</span><span class="sxs-lookup"><span data-stu-id="4f711-160">Choose a language.</span></span> <span data-ttu-id="4f711-161">この言語は、システム生成の音声プロンプトとボイスメール トランスクリプション (有効にした場合) に使用されます。</span><span class="sxs-lookup"><span data-stu-id="4f711-161">This language will be used for system-generated voice prompts and voicemail transcription (if you enable them).</span></span>

    ![リソース アカウントと言語設定のスクリーンショット](../media/call-queue-name-language.png)

4. <span data-ttu-id="4f711-163">発信者がキューに入った場合に発信者に応答メッセージを再生する場合に指定します。</span><span class="sxs-lookup"><span data-stu-id="4f711-163">Specify if you want to play a greeting to callers when they arrive in the queue.</span></span> <span data-ttu-id="4f711-164">再生する応答メッセージを含む MP3、WAV、または WMA ファイルをアップロードする必要があります。</span><span class="sxs-lookup"><span data-stu-id="4f711-164">You must upload an MP3, WAV, or WMA file containing the greeting that you want to play.</span></span>

5. <span data-ttu-id="4f711-165">Teams は、キューで保留されている間、発信者に既定の音楽を提供します。</span><span class="sxs-lookup"><span data-stu-id="4f711-165">Teams provides default music to callers while they are on hold in a queue.</span></span> <span data-ttu-id="4f711-166">特定のオーディオ ファイルを再生する場合は、[オーディオ ファイルの再生] を選択し、MP3、WAV、または WMA ファイルをアップロードします。</span><span class="sxs-lookup"><span data-stu-id="4f711-166">If you want to play a specific audio file, choose **Play an audio file** and upload an MP3, WAV, or WMA file.</span></span>

> [!NOTE]
> <span data-ttu-id="4f711-167">アップロードされた記録は 5 MB 以下にできます。</span><span class="sxs-lookup"><span data-stu-id="4f711-167">The uploaded recording can be no larger than 5 MB.</span></span>
> <span data-ttu-id="4f711-168">Teams の通話キューで提供される既定の音楽には、組織が支払う料金は無料です。</span><span class="sxs-lookup"><span data-stu-id="4f711-168">The default music supplied in Teams call queues is free of any royalties payable by your organization.</span></span> 

> [!div class="nextstepaction"]
> [<span data-ttu-id="4f711-169">手順 3 - コール エージェントが></span><span class="sxs-lookup"><span data-stu-id="4f711-169">Step 3 - Call agents ></span></span>](https://review.docs.microsoft.com/microsoftteams/business-voice/create-a-phone-system-call-queue-smb?branch=mikeplum-smb-voice&tabs=call-agents#steps)

# <a name="step-3brcall-agents"></a>[<span data-ttu-id="4f711-170">手順 3 コール <br> エージェント</span><span class="sxs-lookup"><span data-stu-id="4f711-170">Step 3<br>Call agents</span></span>](#tab/call-agents)

<span data-ttu-id="4f711-171">エージェントを通話キューに追加するには、以前に作成したチームを追加します。</span><span class="sxs-lookup"><span data-stu-id="4f711-171">To add agents to the call queue, we'll add the team that we created earlier.</span></span>

1. <span data-ttu-id="4f711-172">[グループの **追加] をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="4f711-172">Click **Add groups**.</span></span>
2. <span data-ttu-id="4f711-173">作成したチームの名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="4f711-173">Type the name of the team that you created.</span></span>
3. <span data-ttu-id="4f711-174">[追加 **] をクリック** し、[追加] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="4f711-174">Click **Add**, and then click **Add**.</span></span>

    ![通話キューのユーザーとグループの設定のスクリーンショット](../media/call-queue-users-groups-smb.png)

<span data-ttu-id="4f711-176">最大 20 人のエージェントを個別に追加し、最大 200 人のエージェントをグループまたはチーム経由で追加できます。</span><span class="sxs-lookup"><span data-stu-id="4f711-176">You can add up to 20 agents individually and up to 200 agents via groups or teams.</span></span>

> [!NOTE]
> <span data-ttu-id="4f711-177">新しいユーザーがチームに追加された場合、最初の通話が到着するには最大 8 時間かかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="4f711-177">When new users are added to the team, it can take up to eight hours for their first call to arrive.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="4f711-178">手順 4 - リソース アカウント></span><span class="sxs-lookup"><span data-stu-id="4f711-178">Step 4 - Resource accounts ></span></span>](https://review.docs.microsoft.com/microsoftteams/business-voice/create-a-phone-system-call-queue-smb?branch=mikeplum-smb-voice&tabs=call-routing#steps)

# <a name="step-4brcall-routing"></a>[<span data-ttu-id="4f711-179">手順 4 通話 <br> ルーティング</span><span class="sxs-lookup"><span data-stu-id="4f711-179">Step 4<br>Call routing</span></span>](#tab/call-routing)

<span data-ttu-id="4f711-180">使用する通話ルーティング方法を選択します。</span><span class="sxs-lookup"><span data-stu-id="4f711-180">Choose the call routing method that you want to use.</span></span>

1. <span data-ttu-id="4f711-181">会議モード **を自動に\*\*\*\*設定します**。</span><span class="sxs-lookup"><span data-stu-id="4f711-181">Set **Conference mode** to **Auto**.</span></span>

2. <span data-ttu-id="4f711-182">使用する **ルーティング方法** を選択します。</span><span class="sxs-lookup"><span data-stu-id="4f711-182">Choose the **Routing method** you want to use.</span></span> <span data-ttu-id="4f711-183">これにより、エージェントがキューから通話を受信する順序が決定されます。</span><span class="sxs-lookup"><span data-stu-id="4f711-183">This determines the order in which agents receive calls from the queue.</span></span> <span data-ttu-id="4f711-184">シリアル ルーティング **またはラウンド ロビン\*\*\*\*をお勧めします**。</span><span class="sxs-lookup"><span data-stu-id="4f711-184">We recommend **Serial routing** or  **Round robin**.</span></span> <span data-ttu-id="4f711-185">次のオプションから選択します。</span><span class="sxs-lookup"><span data-stu-id="4f711-185">Choose from these options:</span></span>

    - <span data-ttu-id="4f711-186">**アテンダント** ルーティングでは、キュー内のすべてのエージェントが同時に呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="4f711-186">**Attendant routing** rings all agents in the queue at the same time.</span></span> <span data-ttu-id="4f711-187">通話を受け取る最初の通話エージェントが通話を受け取る。</span><span class="sxs-lookup"><span data-stu-id="4f711-187">The first call agent to pick up the call gets the call.</span></span>

    - <span data-ttu-id="4f711-188">**シリアル ルーティングは** 、すべてのコール エージェントを 1 つ 1 つリングします。</span><span class="sxs-lookup"><span data-stu-id="4f711-188">**Serial routing** rings all call agents one by one.</span></span> <span data-ttu-id="4f711-189">エージェントが通話を却下するか、通話を受け取らない場合、通話は次のエージェントを呼び出し、エージェントが受け取されるか、または時間が切れるまですべてのエージェントを試します。</span><span class="sxs-lookup"><span data-stu-id="4f711-189">If an agent dismisses or does not pick up a call, the call will ring the next agent and will try all agents until it is picked up or times out.</span></span>

    - <span data-ttu-id="4f711-190">**ラウンド ロビンは** 、着信通話のルーティングのバランスを取り、各通話エージェントがキューから同じ数の通話を受け取ります。</span><span class="sxs-lookup"><span data-stu-id="4f711-190">**Round robin** balances the routing of incoming calls so that each call agent gets the same number of calls from the queue.</span></span> <span data-ttu-id="4f711-191">これは、すべての通話エージェント間で同じ機会を確保するために、受信販売環境で望ましい場合があります。</span><span class="sxs-lookup"><span data-stu-id="4f711-191">This may be desirable in an inbound sales environment to assure equal opportunity among all the call agents.</span></span>

    - <span data-ttu-id="4f711-192">**アイドル時間が** 最も長いエージェントに各呼び出しがルーティングされます。</span><span class="sxs-lookup"><span data-stu-id="4f711-192">**Longest idle** routes each call to the agent who has been idle the longest time.</span></span> <span data-ttu-id="4f711-193">(プレゼンス状態が 10 分以上離れたエージェントは含まれません)。</span><span class="sxs-lookup"><span data-stu-id="4f711-193">(Agents whose presence state has been Away for more than 10 minutes are not included.)</span></span>

    ![電話会議モードとルーティング方法の設定のスクリーンショット](../media/call-queue-conference-mode-routing-method.png)

3. <span data-ttu-id="4f711-195">プレゼンス **ベースのルーティングを有効** にする。</span><span class="sxs-lookup"><span data-stu-id="4f711-195">Turn **Presence-based routing** on.</span></span> <span data-ttu-id="4f711-196">これにより、プレゼンス状態が [使用可能] のエージェントに通話がルーティング **されます**。</span><span class="sxs-lookup"><span data-stu-id="4f711-196">This routes calls to agents whose presence status is **Available**.</span></span>

4. <span data-ttu-id="4f711-197">エージェントが通話をオプトアウトすることを許可する場合に選択します。</span><span class="sxs-lookup"><span data-stu-id="4f711-197">Choose if you want to allow agents to opt out of calls.</span></span>

5. <span data-ttu-id="4f711-198">エージェントの **通知時間を設定** して、キューが呼び出しを次のエージェントにリダイレクトする前にエージェントの電話が鳴る時間を指定します。</span><span class="sxs-lookup"><span data-stu-id="4f711-198">Set an **Agent alert time** to specify how long an agent's phone will ring before the queue redirects the call to the next agent.</span></span>

    ![ルーティング、オプトアウト、通知時間の設定のスクリーンショット](../media/call-queue-presence-agents-time.png)

> [!div class="nextstepaction"]
> [<span data-ttu-id="4f711-200">手順 5 - 呼び出しオーバーフロー ></span><span class="sxs-lookup"><span data-stu-id="4f711-200">Step 5 - Call overflow ></span></span>](https://review.docs.microsoft.com/microsoftteams/business-voice/create-a-phone-system-call-queue-smb?branch=mikeplum-smb-voice&tabs=call-overflow#steps)

# <a name="step-5brcall-overflow"></a>[<span data-ttu-id="4f711-201">手順 5 通話 <br> オーバーフロー</span><span class="sxs-lookup"><span data-stu-id="4f711-201">Step 5<br>Call overflow</span></span>](#tab/call-overflow)

<span data-ttu-id="4f711-202">キューの最大数を超える呼び出しを処理する方法を選択します。</span><span class="sxs-lookup"><span data-stu-id="4f711-202">Choose how you want to handle calls that exceed the maximum in the queue.</span></span>

1. <span data-ttu-id="4f711-203">キュー内 **の最大呼び出しを設定します**。</span><span class="sxs-lookup"><span data-stu-id="4f711-203">Set the **Maximum calls in the queue**.</span></span>

2. <span data-ttu-id="4f711-204">通話の最大数に達した場合に実行する操作を選択します。</span><span class="sxs-lookup"><span data-stu-id="4f711-204">Choose what you want to do when the maximum number of calls is reached.</span></span> <span data-ttu-id="4f711-205">通話を切断するか、リダイレクトできます。</span><span class="sxs-lookup"><span data-stu-id="4f711-205">You can disconnect the call or redirect it.</span></span> <span data-ttu-id="4f711-206">次のいずれかの接続先に通話をリダイレクトすることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="4f711-206">We recommend that you redirect the call to one of the following destinations:</span></span>
    - <span data-ttu-id="4f711-207">**組織内のユーザー** - 音声通話を受信できる組織内のユーザー</span><span class="sxs-lookup"><span data-stu-id="4f711-207">**Person in the organization** - a person in your organization who is able to receive voice calls</span></span>
    - <span data-ttu-id="4f711-208">**音声アプリ** - 自動応答または別の通話キュー。</span><span class="sxs-lookup"><span data-stu-id="4f711-208">**Voice app** - an auto attendant or another call queue.</span></span> <span data-ttu-id="4f711-209">(この宛先を選ぶときに、自動応答または通話キューに関連付けられているリソース アカウントを選ぶ。</span><span class="sxs-lookup"><span data-stu-id="4f711-209">(Choose the resource account associated with the auto attendant or call queue when choosing this destination.)</span></span>
    - <span data-ttu-id="4f711-210">**外部電話番号** - 任意の電話番号。</span><span class="sxs-lookup"><span data-stu-id="4f711-210">**External phone number** - any phone number.</span></span> <span data-ttu-id="4f711-211">次の形式を使用します: +[国コード][郵便番号][電話番号]</span><span class="sxs-lookup"><span data-stu-id="4f711-211">Use this format: +[country code][area code][phone number]</span></span>
    - <span data-ttu-id="4f711-212">**ボイス** メール - 作成したチームのボイス メールボックスを使用できます。</span><span class="sxs-lookup"><span data-stu-id="4f711-212">**Voicemail** - you can use the voice mailbox of the team that you created.</span></span>

    ![呼び出しオーバーフロー設定のスクリーンショット](../media/call-queue-overflow-handling.png)

> [!div class="nextstepaction"]
> [<span data-ttu-id="4f711-214">手順 6 - 通話のタイムアウト></span><span class="sxs-lookup"><span data-stu-id="4f711-214">Step 6 - Call timeout ></span></span>](https://review.docs.microsoft.com/microsoftteams/business-voice/create-a-phone-system-call-queue-smb?branch=mikeplum-smb-voice&tabs=call-timeout#steps)

# <a name="step-6brcall-timeout"></a>[<span data-ttu-id="4f711-215">手順 6 通話 <br> タイムアウト</span><span class="sxs-lookup"><span data-stu-id="4f711-215">Step 6<br>Call timeout</span></span>](#tab/call-timeout)

<span data-ttu-id="4f711-216">通話がキュー内で長い間待機している場合に実行する処理を選択します。</span><span class="sxs-lookup"><span data-stu-id="4f711-216">Choose what you want to happen when calls have been waiting in the queue for too long.</span></span>

1. <span data-ttu-id="4f711-217">通話タイムアウト **を設定する: 最大待ち時間**。</span><span class="sxs-lookup"><span data-stu-id="4f711-217">Set the **Call Timeout: maximum wait time**.</span></span>

2. <span data-ttu-id="4f711-218">通話がタイムアウトした場合に実行する操作を選択します。通話を切断するか、リダイレクトできます。</span><span class="sxs-lookup"><span data-stu-id="4f711-218">Choose what you want to do when a call times out. You can disconnect the call or redirect it.</span></span> <span data-ttu-id="4f711-219">次のいずれかの接続先に通話をリダイレクトすることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="4f711-219">We recommend that you redirect the call to one of the following destinations:</span></span>
    - <span data-ttu-id="4f711-220">**組織内のユーザー** - 音声通話を受信できる組織内のユーザー</span><span class="sxs-lookup"><span data-stu-id="4f711-220">**Person in the organization** - a person in your organization who is able to receive voice calls</span></span>
    - <span data-ttu-id="4f711-221">**音声アプリ** - 自動応答または別の通話キュー。</span><span class="sxs-lookup"><span data-stu-id="4f711-221">**Voice app** - an auto attendant or another call queue.</span></span> <span data-ttu-id="4f711-222">(この宛先を選ぶときに、自動応答または通話キューに関連付けられているリソース アカウントを選ぶ。</span><span class="sxs-lookup"><span data-stu-id="4f711-222">(Choose the resource account associated with the auto attendant or call queue when choosing this destination.)</span></span>
    - <span data-ttu-id="4f711-223">**外部電話番号** - 任意の電話番号。</span><span class="sxs-lookup"><span data-stu-id="4f711-223">**External phone number** - any phone number.</span></span> <span data-ttu-id="4f711-224">次の形式を使用します: +[国コード][郵便番号][電話番号]</span><span class="sxs-lookup"><span data-stu-id="4f711-224">Use this format: +[country code][area code][phone number]</span></span>
    - <span data-ttu-id="4f711-225">**ボイス** メール - 作成したチームのボイス メールボックスを使用できます。</span><span class="sxs-lookup"><span data-stu-id="4f711-225">**Voicemail** - you can use the voice mailbox of the team that you created.</span></span>

    ![通話タイムアウト設定のスクリーンショット](../media/call-queue-timeout-handling.png)

3. <span data-ttu-id="4f711-227">**[保存]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="4f711-227">Click **Save**.</span></span>

<span data-ttu-id="4f711-228">これで通話キューのセットアップが完了します。</span><span class="sxs-lookup"><span data-stu-id="4f711-228">This completes the setup of your call queue.</span></span> <span data-ttu-id="4f711-229">次に、自動応答 [を設定できます](create-a-phone-system-auto-attendant-smb.md)。</span><span class="sxs-lookup"><span data-stu-id="4f711-229">Next, you may want to [set up an auto attendant](create-a-phone-system-auto-attendant-smb.md).</span></span>

---

