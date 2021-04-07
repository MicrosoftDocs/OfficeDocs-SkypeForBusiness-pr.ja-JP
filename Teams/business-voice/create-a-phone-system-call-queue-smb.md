---
title: Microsoft Teams で通話キューを作成する - 小規模ビジネス向けチュートリアル
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.reviewer: dobro
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
ms.openlocfilehash: 40018ce331dfe8516e00c6781373d528a71e85c5
ms.sourcegitcommit: 3861d661d32f507bd8479509ed09b1cfcf0b214f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/07/2021
ms.locfileid: "51607559"
---
# <a name="create-a-call-queue---small-business-tutorial"></a><span data-ttu-id="85c6a-103">通話キューを作成する - 小規模ビジネス向けチュートリアル</span><span class="sxs-lookup"><span data-stu-id="85c6a-103">Create a call queue - small business tutorial</span></span>

<span data-ttu-id="85c6a-104">通話キューは、組織内の特定の問題や質問に役立つユーザーに発信者をルーティングする方法を提供します。</span><span class="sxs-lookup"><span data-stu-id="85c6a-104">Call queues provide a method of routing callers to people in your organization who can help with with a particular issue or question.</span></span> <span data-ttu-id="85c6a-105">通話はキュー内のユーザー (エージェントと呼ばれる) に一度に 1 つ配布 *されます*。</span><span class="sxs-lookup"><span data-stu-id="85c6a-105">Calls are distributed one at a time to the people in the queue (who are known as *agents*).</span></span> 

<span data-ttu-id="85c6a-106">通話キューには次の機能があります。</span><span class="sxs-lookup"><span data-stu-id="85c6a-106">Call queues provide:</span></span>

- <span data-ttu-id="85c6a-107">あいさつメッセージ。</span><span class="sxs-lookup"><span data-stu-id="85c6a-107">A greeting message.</span></span>

- <span data-ttu-id="85c6a-108">ユーザーがキューで保留を待っている間の音楽。</span><span class="sxs-lookup"><span data-stu-id="85c6a-108">Music while people are waiting on hold in a queue.</span></span>

- <span data-ttu-id="85c6a-109">コール ルーティング - *First In、First Out* (FIRST Out )順序で- エージェントに。</span><span class="sxs-lookup"><span data-stu-id="85c6a-109">Call routing - in *First In, First Out* (FIFO) order - to agents.</span></span>

- <span data-ttu-id="85c6a-110">キュー オーバーフローとタイムアウトの処理オプション。</span><span class="sxs-lookup"><span data-stu-id="85c6a-110">Handling options for queue overflow and timeout.</span></span>

#### <a name="before-you-begin"></a><span data-ttu-id="85c6a-111">はじめに</span><span class="sxs-lookup"><span data-stu-id="85c6a-111">Before you begin</span></span>

<span data-ttu-id="85c6a-112">電話システム [を取得する - 仮想ユーザー ライセンス](../teams-add-on-licensing/virtual-user.md) をまだ持ってない場合は、仮想ユーザー ライセンスを取得します。</span><span class="sxs-lookup"><span data-stu-id="85c6a-112">Get some [Phone System - Virtual User licenses](../teams-add-on-licensing/virtual-user.md) if you don't already have them.</span></span> <span data-ttu-id="85c6a-113">セットアップする通話キューと自動応答ごとに 1 つ取得します。</span><span class="sxs-lookup"><span data-stu-id="85c6a-113">Get one for each call queue and auto attendant that you plan to set up.</span></span> <span data-ttu-id="85c6a-114">これらのライセンスは無料なので、後でセットアップを変更する場合に備え、追加のライセンスを取得する方法をお勧めしています。</span><span class="sxs-lookup"><span data-stu-id="85c6a-114">These licenses are free, so we suggest getting a few extra in case you decide to make changes to your setup in the future.</span></span>

<span data-ttu-id="85c6a-115">通話キュー内のエージェントがダイヤルアウトして顧客の通話を返す可能性がある場合は、通話エージェントの発信者番号をメインの電話番号または適切な自動応答の番号に設定します。</span><span class="sxs-lookup"><span data-stu-id="85c6a-115">Since agents in a call queue may dial out to return a customer call, consider setting the caller ID for your call agents to your main phone number or the number of an appropriate auto attendant.</span></span> <span data-ttu-id="85c6a-116">詳細 [については、「Microsoft Teams で発信者番号ポリシーを](../caller-id-policies.md) 管理する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="85c6a-116">See [Manage caller ID policies in Microsoft Teams](../caller-id-policies.md) for more information.</span></span>

<a name="steps"></a>

#### <a name="follow-these-steps-to-set-up-your-call-queue"></a><span data-ttu-id="85c6a-117">通話キューをセットアップするには、次の手順に従います。</span><span class="sxs-lookup"><span data-stu-id="85c6a-117">Follow these steps to set up your call queue</span></span>

# <a name="step-1brcreate-a-team"></a>[<span data-ttu-id="85c6a-118">手順 1 <br> チームを作成する</span><span class="sxs-lookup"><span data-stu-id="85c6a-118">Step 1<br>Create a team</span></span>](#tab/create-team)

<span data-ttu-id="85c6a-119">通話キューを作成するときに、個々のユーザーをキューに追加するか、既存のセキュリティ グループ、Microsoft 365 グループ、または Microsoft Teams チームを使用できます。</span><span class="sxs-lookup"><span data-stu-id="85c6a-119">When creating a call queue, you can add individual users to the queue, or you can use an existing security group, Microsoft 365 group, or Microsoft Teams team.</span></span> <span data-ttu-id="85c6a-120">チーム チャネル [を使用することをお勧めします](https://support.microsoft.com/office/9f07dabe-91c6-4a9b-a545-8ffdddd2504e)。</span><span class="sxs-lookup"><span data-stu-id="85c6a-120">We recommend [using a team channel](https://support.microsoft.com/office/9f07dabe-91c6-4a9b-a545-8ffdddd2504e).</span></span> <span data-ttu-id="85c6a-121">これにより、キューのメンバーは互いにチャットしたり、アイデアを共有したり、顧客を支援するドキュメントや他のリソースを作成することができます。</span><span class="sxs-lookup"><span data-stu-id="85c6a-121">This allows members of the queue to chat with each other, share ideas, and create documents or other resources to help them help your customers.</span></span> <span data-ttu-id="85c6a-122">また、チームは、発信者が数時間後にメッセージを残したり、キューが最大容量に達したりするためにボイス メールボックスを提供します。</span><span class="sxs-lookup"><span data-stu-id="85c6a-122">A team also provides a voice mailbox for callers to leave a message after hours or if the queue reaches its maximum capacity.</span></span>

<span data-ttu-id="85c6a-123">チームを作成するには</span><span class="sxs-lookup"><span data-stu-id="85c6a-123">To create a team</span></span>

1. <span data-ttu-id="85c6a-124">まず、アプリ **の左側にある [Teams]** をクリックし、[参加] をクリックするか、チーム リストの下部にあるチームを作成します。</span><span class="sxs-lookup"><span data-stu-id="85c6a-124">First, click **Teams** on the left side of the app, then click **Join or create a team** at the bottom of your teams list.</span></span>

2. <span data-ttu-id="85c6a-125">次に、[ **チームの作成]** (最初のカード、左上隅) をクリックします。</span><span class="sxs-lookup"><span data-stu-id="85c6a-125">Then click **Create team** (first card, top left corner).</span></span>

3. <span data-ttu-id="85c6a-126">[チーム **を一から作成] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="85c6a-126">Choose **Build a team from scratch**.</span></span>

4. <span data-ttu-id="85c6a-127">次に、パブリック チームとプライベート チームの選択を行います。</span><span class="sxs-lookup"><span data-stu-id="85c6a-127">Next, choose whether you want a public or private team.</span></span> <span data-ttu-id="85c6a-128">チームに **参加** することで、ユーザーが意図せずにキューに参加することを避けるために、通話キューにプライベートを使用することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="85c6a-128">We recommend **Private** for your call queue to avoid people unintentionally becoming part of the queue by joining the team.</span></span>

5. <span data-ttu-id="85c6a-129">チームに名前を付け、オプションの説明を追加します。</span><span class="sxs-lookup"><span data-stu-id="85c6a-129">Name your team and add an optional description.</span></span>

6. <span data-ttu-id="85c6a-130">完了したら、[作成] をクリック **します**。</span><span class="sxs-lookup"><span data-stu-id="85c6a-130">When you're done, click **Create**.</span></span>

8. <span data-ttu-id="85c6a-131">通話キューに追加するユーザーの名前を入力し、[追加] をクリック **します**。</span><span class="sxs-lookup"><span data-stu-id="85c6a-131">Type the names of the people that you want to have in your call queue, and then click **Add**.</span></span>

9. <span data-ttu-id="85c6a-132">[**閉じる**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="85c6a-132">Click **Close**.</span></span> <span data-ttu-id="85c6a-133">チームに追加したユーザーには、チームのメンバーになれたというメールが送信され、チームがチーム リストに表示されます。</span><span class="sxs-lookup"><span data-stu-id="85c6a-133">People you add to a team will receive an email letting them know they are now a member of your team and the team will show up in their teams list.</span></span>

<span data-ttu-id="85c6a-134">次に、通話キューで使用するチャネルを追加します。</span><span class="sxs-lookup"><span data-stu-id="85c6a-134">Next, we'll add a channel to use with the call queue.</span></span>

<span data-ttu-id="85c6a-135">チャネルを追加するには</span><span class="sxs-lookup"><span data-stu-id="85c6a-135">To add a channel</span></span>

1. <span data-ttu-id="85c6a-136">Teams で、作成したチームを見つけ、[その他のオプション **]** (...) をクリックし、[チャネルの追加] **をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="85c6a-136">In Teams, find the team you just created, click **More options** (...), and then click **Add channel**.</span></span>

2. <span data-ttu-id="85c6a-137">チャネルの名前と説明を入力し、[追加] をクリック **します**。</span><span class="sxs-lookup"><span data-stu-id="85c6a-137">Type a name and description for the channel, and then click **Add**.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="85c6a-138">手順 2 - リソース アカウントの></span><span class="sxs-lookup"><span data-stu-id="85c6a-138">Step 2 - Resource accounts ></span></span>](/microsoftteams/business-voice/create-a-phone-system-call-queue-smb?tabs=resource-account#steps)

# <a name="step-2brresource-accounts"></a>[<span data-ttu-id="85c6a-139">手順 2 <br> リソース アカウント</span><span class="sxs-lookup"><span data-stu-id="85c6a-139">Step 2<br>Resource accounts</span></span>](#tab/resource-account)

<span data-ttu-id="85c6a-140">作成する各通話キューには、リソース アカウントが必要です。</span><span class="sxs-lookup"><span data-stu-id="85c6a-140">Each call queue that you create requires a resource account.</span></span> <span data-ttu-id="85c6a-141">これはユーザー アカウントに似ていますが、アカウントがユーザーではなく自動応答または通話キューに関連付けられている場合を除きます。</span><span class="sxs-lookup"><span data-stu-id="85c6a-141">This is similar to a user account, except the account is associated with an auto attendant or call queue instead of a person.</span></span> <span data-ttu-id="85c6a-142">この手順では、アカウントを作成し *、Microsoft 365* 電話システム - 仮想ユーザー ライセンスを割り当て、それを使用して通話キューの作成を開始します。</span><span class="sxs-lookup"><span data-stu-id="85c6a-142">In this step, we'll create the account, assign it a *Microsoft 365 Phone System - Virtual User* license, and then use it to start creating the call queue.</span></span>

### <a name="create-a-resource-account"></a><span data-ttu-id="85c6a-143">リソース アカウントを作成する</span><span class="sxs-lookup"><span data-stu-id="85c6a-143">Create a resource account</span></span>

<span data-ttu-id="85c6a-144">Teams 管理センターでリソース アカウントを作成できます。</span><span class="sxs-lookup"><span data-stu-id="85c6a-144">You can create a resource account in the Teams admin center.</span></span>

1. <span data-ttu-id="85c6a-145">Teams 管理センターで、組織全体の設定 **を** 展開し、[リソース アカウント] **をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="85c6a-145">In the Teams admin center, expand **Org-wide settings**, and then click **Resource accounts**.</span></span>

2. <span data-ttu-id="85c6a-146">**[追加]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="85c6a-146">Click **Add**.</span></span>

3. <span data-ttu-id="85c6a-147">[リソース アカウント **の追加]** ウィンドウで、[表示名] に[**ユーザー** 名] を入力し、[リソース アカウントの種類] の [通話キュー **] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="85c6a-147">In the **Add resource account** pane, fill out **Display name**, **Username**, and choose **Call queue** for the **Resource account type**.</span></span> <span data-ttu-id="85c6a-148">エージェントは、キューからの着信通話を受信すると、表示名を表示します。</span><span class="sxs-lookup"><span data-stu-id="85c6a-148">Agents will see the display name when they receive an incoming call from the queue.</span></span>

    ![リソース アカウントのユーザー インターフェイスの追加のスクリーンショット](../media/resource-account-add-cq.png)

4. <span data-ttu-id="85c6a-150">**[保存]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="85c6a-150">Click **Save**.</span></span>

<span data-ttu-id="85c6a-151">新しいアカウントがアカウントの一覧に表示されます。</span><span class="sxs-lookup"><span data-stu-id="85c6a-151">The new account will appear in the list of accounts.</span></span>

![リソース アカウントの一覧のスクリーンショット](../media/resource-accounts-page.png)

### <a name="assign-a-license"></a><span data-ttu-id="85c6a-153">ライセンスを割り当てる</span><span class="sxs-lookup"><span data-stu-id="85c6a-153">Assign a license</span></span>

<span data-ttu-id="85c6a-154">Microsoft *365* 電話システム - 仮想ユーザー ライセンスをリソース アカウントに割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="85c6a-154">You must assign a *Microsoft 365 Phone System - Virtual User* license to the resource account.</span></span>

1. <span data-ttu-id="85c6a-155">Microsoft 365 管理センターの [アクティブなユーザー] リストで、ライセンスを割り当てるリソース アカウントをクリックします。</span><span class="sxs-lookup"><span data-stu-id="85c6a-155">In the Microsoft 365 admin center, in the **Active users** list, click the resource account to which you want to assign a license.</span></span>

2. <span data-ttu-id="85c6a-156">[ライセンスと **アプリ] タブの** [ **ライセンス]** で **、[Microsoft 365 電話システム - 仮想ユーザー] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="85c6a-156">On the **Licenses and Apps** tab, under **Licenses**, select **Microsoft 365 Phone System - Virtual User**.</span></span>

3. <span data-ttu-id="85c6a-157">[変更を **保存] をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="85c6a-157">Click **Save changes**.</span></span>

    ![Microsoft 365 管理センターのライセンスの割り当てユーザー インターフェイスのスクリーンショット](../media/resource-account-assign-virtual-user-license.png)

### <a name="create-a-call-queue"></a><span data-ttu-id="85c6a-159">呼び出しキューを作成する</span><span class="sxs-lookup"><span data-stu-id="85c6a-159">Create a call queue</span></span>

<span data-ttu-id="85c6a-160">次に、新しい通話キューの作成を開始し、リソース アカウントを割り当てします。</span><span class="sxs-lookup"><span data-stu-id="85c6a-160">Next, we'll start creating a new call queue and assign the resource account.</span></span>

1. <span data-ttu-id="85c6a-161">Teams 管理センターで、[音声] を **展開** し、[ **通話キュー**] をクリックして、[追加] をクリック **します**。</span><span class="sxs-lookup"><span data-stu-id="85c6a-161">In the Teams admin center, expand **Voice**, click **Call queues**, and then click **Add**.</span></span>

1. <span data-ttu-id="85c6a-162">通話キューの名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="85c6a-162">Type a name for the call queue.</span></span>

2. <span data-ttu-id="85c6a-163">[**アカウントの追加]** をクリックし、この通話キューで使用するリソース アカウントを検索し、[追加] をクリックして、[追加] をクリック **します**。</span><span class="sxs-lookup"><span data-stu-id="85c6a-163">Click **Add accounts**, search for the resource account that you want to use with this call queue, click **Add**, and then click **Add**.</span></span>

3. <span data-ttu-id="85c6a-164">言語を選択します。</span><span class="sxs-lookup"><span data-stu-id="85c6a-164">Choose a language.</span></span> <span data-ttu-id="85c6a-165">この言語は、システム生成の音声プロンプトとボイスメール トランスクリプション (有効にした場合) に使用されます。</span><span class="sxs-lookup"><span data-stu-id="85c6a-165">This language will be used for system-generated voice prompts and voicemail transcription (if you enable them).</span></span>

    ![リソース アカウントと言語設定のスクリーンショット](../media/call-queue-name-language.png)

4. <span data-ttu-id="85c6a-167">発信者がキューに入った場合に発信者に応答メッセージを再生する場合に指定します。</span><span class="sxs-lookup"><span data-stu-id="85c6a-167">Specify if you want to play a greeting to callers when they arrive in the queue.</span></span> <span data-ttu-id="85c6a-168">再生する応答メッセージを含む MP3、WAV、または WMA ファイルをアップロードする必要があります。</span><span class="sxs-lookup"><span data-stu-id="85c6a-168">You must upload an MP3, WAV, or WMA file containing the greeting that you want to play.</span></span>

5. <span data-ttu-id="85c6a-169">Teams は、キューで保留にしている間、発信者に既定の音楽を提供します。</span><span class="sxs-lookup"><span data-stu-id="85c6a-169">Teams provides default music to callers while they are on hold in a queue.</span></span> <span data-ttu-id="85c6a-170">特定のオーディオ ファイルを再生する場合は、[オーディオ ファイルの再生] を選択し、MP3、WAV、または WMA ファイルをアップロードします。</span><span class="sxs-lookup"><span data-stu-id="85c6a-170">If you want to play a specific audio file, choose **Play an audio file** and upload an MP3, WAV, or WMA file.</span></span>

> [!NOTE]
> <span data-ttu-id="85c6a-171">アップロードされた記録は 5 MB 以下にできます。</span><span class="sxs-lookup"><span data-stu-id="85c6a-171">The uploaded recording can be no larger than 5 MB.</span></span>
> <span data-ttu-id="85c6a-172">Teams の通話キューで提供される既定の音楽には、組織が支払う料金は無料です。</span><span class="sxs-lookup"><span data-stu-id="85c6a-172">The default music supplied in Teams call queues is free of any royalties payable by your organization.</span></span> 

> [!div class="nextstepaction"]
> [<span data-ttu-id="85c6a-173">手順 3 - コール エージェントが></span><span class="sxs-lookup"><span data-stu-id="85c6a-173">Step 3 - Call agents ></span></span>](/microsoftteams/business-voice/create-a-phone-system-call-queue-smb?tabs=call-agents#steps)

# <a name="step-3brcall-agents"></a>[<span data-ttu-id="85c6a-174">手順 3 コール <br> エージェント</span><span class="sxs-lookup"><span data-stu-id="85c6a-174">Step 3<br>Call agents</span></span>](#tab/call-agents)

<span data-ttu-id="85c6a-175">エージェントを通話キューに追加するには、先に作成したチームとチャネルにエージェントを追加します。</span><span class="sxs-lookup"><span data-stu-id="85c6a-175">To add agents to the call queue, we'll add them to the team and channel that we created earlier.</span></span>

1. <span data-ttu-id="85c6a-176">[チームの **選択] オプションを選択し** 、[チャネルの追加 **] をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="85c6a-176">Select the **Choose a team** option and click **Add a channel**.</span></span>
2. <span data-ttu-id="85c6a-177">作成したチームの名前を入力して選択し、[追加] をクリック **します**。</span><span class="sxs-lookup"><span data-stu-id="85c6a-177">Type the name of the team that you created, select it, and click **Add**.</span></span>
3. <span data-ttu-id="85c6a-178">キュー用に作成したチャネルを選択します。</span><span class="sxs-lookup"><span data-stu-id="85c6a-178">Select the channel that you created for the queue.</span></span>
3. <span data-ttu-id="85c6a-179">[**適用**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="85c6a-179">Click **Apply**.</span></span>

    ![通話キューのユーザーとグループの設定のスクリーンショット](../media/call-queue-users-groups.png)

> [!NOTE]
> <span data-ttu-id="85c6a-181">新しいユーザーがチームに追加された場合、最初の通話が到着するには最大 8 時間かかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="85c6a-181">When new users are added to the team, it can take up to eight hours for their first call to arrive.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="85c6a-182">手順 4 - リソース アカウントの></span><span class="sxs-lookup"><span data-stu-id="85c6a-182">Step 4 - Resource accounts ></span></span>](/microsoftteams/business-voice/create-a-phone-system-call-queue-smb?tabs=call-routing#steps)

# <a name="step-4brcall-routing"></a>[<span data-ttu-id="85c6a-183">手順 4 通話 <br> ルーティング</span><span class="sxs-lookup"><span data-stu-id="85c6a-183">Step 4<br>Call routing</span></span>](#tab/call-routing)

<span data-ttu-id="85c6a-184">使用する通話ルーティング方法を選択します。</span><span class="sxs-lookup"><span data-stu-id="85c6a-184">Choose the call routing method that you want to use.</span></span>

1. <span data-ttu-id="85c6a-185">会議モード **を自動に\*\*\*\*設定します**。</span><span class="sxs-lookup"><span data-stu-id="85c6a-185">Set **Conference mode** to **Auto**.</span></span>

2. <span data-ttu-id="85c6a-186">使用する **ルーティング方法** を選択します。</span><span class="sxs-lookup"><span data-stu-id="85c6a-186">Choose the **Routing method** you want to use.</span></span> <span data-ttu-id="85c6a-187">これにより、エージェントがキューから通話を受信する順序が決定されます。</span><span class="sxs-lookup"><span data-stu-id="85c6a-187">This determines the order in which agents receive calls from the queue.</span></span> <span data-ttu-id="85c6a-188">シリアル ルーティング **またはラウンド ロビン\*\*\*\*をお勧めします**。</span><span class="sxs-lookup"><span data-stu-id="85c6a-188">We recommend **Serial routing** or  **Round robin**.</span></span> <span data-ttu-id="85c6a-189">次のオプションから選択します。</span><span class="sxs-lookup"><span data-stu-id="85c6a-189">Choose from these options:</span></span>

    - <span data-ttu-id="85c6a-190">**アテンダント** ルーティングでは、キュー内のすべてのエージェントが同時に呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="85c6a-190">**Attendant routing** rings all agents in the queue at the same time.</span></span> <span data-ttu-id="85c6a-191">通話を受け取る最初の通話エージェントが通話を受け取る。</span><span class="sxs-lookup"><span data-stu-id="85c6a-191">The first call agent to pick up the call gets the call.</span></span>

    - <span data-ttu-id="85c6a-192">**シリアル ルーティングは** 、すべてのコール エージェントを 1 つ 1 つリングします。</span><span class="sxs-lookup"><span data-stu-id="85c6a-192">**Serial routing** rings all call agents one by one.</span></span> <span data-ttu-id="85c6a-193">エージェントが通話を却下するか、通話を受け取らない場合、通話は次のエージェントを呼び出し、エージェントが受け取されるか、または時間が切れるまですべてのエージェントを試します。</span><span class="sxs-lookup"><span data-stu-id="85c6a-193">If an agent dismisses or does not pick up a call, the call will ring the next agent and will try all agents until it is picked up or times out.</span></span>

    - <span data-ttu-id="85c6a-194">**ラウンド ロビンは** 、着信通話のルーティングのバランスを取り、各通話エージェントがキューから同じ数の通話を受け取ります。</span><span class="sxs-lookup"><span data-stu-id="85c6a-194">**Round robin** balances the routing of incoming calls so that each call agent gets the same number of calls from the queue.</span></span> <span data-ttu-id="85c6a-195">受信販売環境では、すべてのコール エージェント間で機会が均等に確保されるのが望ましい場合があります。</span><span class="sxs-lookup"><span data-stu-id="85c6a-195">This may be desirable in an inbound sales environment to assure equal opportunity among all the call agents.</span></span>

    - <span data-ttu-id="85c6a-196">**アイドル時間が** 最も長いエージェントに各呼び出しがルーティングされます。</span><span class="sxs-lookup"><span data-stu-id="85c6a-196">**Longest idle** routes each call to the agent who has been idle the longest time.</span></span> <span data-ttu-id="85c6a-197">(プレゼンス状態が 10 分以上離れたエージェントは含まれません)。</span><span class="sxs-lookup"><span data-stu-id="85c6a-197">(Agents whose presence state has been Away for more than 10 minutes are not included.)</span></span>

    ![電話会議モードとルーティング方法の設定のスクリーンショット](../media/call-queue-conference-mode-routing-method.png)

3. <span data-ttu-id="85c6a-199">プレゼンス **ベースのルーティングを有効** にする。</span><span class="sxs-lookup"><span data-stu-id="85c6a-199">Turn **Presence-based routing** on.</span></span> <span data-ttu-id="85c6a-200">これにより、プレゼンス状態が [使用可能] のエージェントに通話がルーティング **されます**。</span><span class="sxs-lookup"><span data-stu-id="85c6a-200">This routes calls to agents whose presence status is **Available**.</span></span>

4. <span data-ttu-id="85c6a-201">エージェントが通話をオプトアウトすることを許可する場合に選択します。</span><span class="sxs-lookup"><span data-stu-id="85c6a-201">Choose if you want to allow agents to opt out of calls.</span></span>

5. <span data-ttu-id="85c6a-202">エージェントの **通知時間を設定** して、キューが呼び出しを次のエージェントにリダイレクトする前にエージェントの電話が鳴る時間を指定します。</span><span class="sxs-lookup"><span data-stu-id="85c6a-202">Set an **Agent alert time** to specify how long an agent's phone will ring before the queue redirects the call to the next agent.</span></span>

    ![ルーティング、オプトアウト、通知時間の設定のスクリーンショット](../media/call-queue-presence-agents-time.png)

> [!div class="nextstepaction"]
> [<span data-ttu-id="85c6a-204">手順 5 - 呼び出しオーバーフロー ></span><span class="sxs-lookup"><span data-stu-id="85c6a-204">Step 5 - Call overflow ></span></span>](/microsoftteams/business-voice/create-a-phone-system-call-queue-smb?tabs=call-overflow#steps)

# <a name="step-5brcall-overflow"></a>[<span data-ttu-id="85c6a-205">手順 5 通話 <br> オーバーフロー</span><span class="sxs-lookup"><span data-stu-id="85c6a-205">Step 5<br>Call overflow</span></span>](#tab/call-overflow)

<span data-ttu-id="85c6a-206">キューの最大数を超える呼び出しを処理する方法を選択します。</span><span class="sxs-lookup"><span data-stu-id="85c6a-206">Choose how you want to handle calls that exceed the maximum in the queue.</span></span>

1. <span data-ttu-id="85c6a-207">キュー内 **の最大呼び出しを設定します**。</span><span class="sxs-lookup"><span data-stu-id="85c6a-207">Set the **Maximum calls in the queue**.</span></span>

2. <span data-ttu-id="85c6a-208">通話の最大数に達した場合に実行する操作を選択します。</span><span class="sxs-lookup"><span data-stu-id="85c6a-208">Choose what you want to do when the maximum number of calls is reached.</span></span> <span data-ttu-id="85c6a-209">通話を切断するか、リダイレクトできます。</span><span class="sxs-lookup"><span data-stu-id="85c6a-209">You can disconnect the call or redirect it.</span></span> <span data-ttu-id="85c6a-210">次のいずれかの接続先に通話をリダイレクトすることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="85c6a-210">We recommend that you redirect the call to one of the following destinations:</span></span>
    - <span data-ttu-id="85c6a-211">**組織内のユーザー** - 音声通話を受信できる組織内のユーザー</span><span class="sxs-lookup"><span data-stu-id="85c6a-211">**Person in the organization** - a person in your organization who is able to receive voice calls</span></span>
    - <span data-ttu-id="85c6a-212">**音声アプリ** - 自動応答または別の通話キュー。</span><span class="sxs-lookup"><span data-stu-id="85c6a-212">**Voice app** - an auto attendant or another call queue.</span></span> <span data-ttu-id="85c6a-213">(この宛先を選ぶときに、自動応答または通話キューに関連付けられているリソース アカウントを選ぶ。</span><span class="sxs-lookup"><span data-stu-id="85c6a-213">(Choose the resource account associated with the auto attendant or call queue when choosing this destination.)</span></span>
    - <span data-ttu-id="85c6a-214">**外部電話番号** - 任意の電話番号。</span><span class="sxs-lookup"><span data-stu-id="85c6a-214">**External phone number** - any phone number.</span></span> <span data-ttu-id="85c6a-215">次の形式を使用します: +[国コード][郵便番号][電話番号]</span><span class="sxs-lookup"><span data-stu-id="85c6a-215">Use this format: +[country code][area code][phone number]</span></span>
    - <span data-ttu-id="85c6a-216">**ボイス** メール - 作成したチームのボイス メールボックスを使用できます。</span><span class="sxs-lookup"><span data-stu-id="85c6a-216">**Voicemail** - you can use the voice mailbox of the team that you created.</span></span>

    ![呼び出しオーバーフロー設定のスクリーンショット](../media/call-queue-overflow-handling.png)

> [!div class="nextstepaction"]
> [<span data-ttu-id="85c6a-218">手順 6 - 通話のタイムアウト></span><span class="sxs-lookup"><span data-stu-id="85c6a-218">Step 6 - Call timeout ></span></span>](/microsoftteams/business-voice/create-a-phone-system-call-queue-smb?tabs=call-timeout#steps)

# <a name="step-6brcall-timeout"></a>[<span data-ttu-id="85c6a-219">手順 6 通話 <br> タイムアウト</span><span class="sxs-lookup"><span data-stu-id="85c6a-219">Step 6<br>Call timeout</span></span>](#tab/call-timeout)

<span data-ttu-id="85c6a-220">通話がキュー内で長い間待機している場合に実行する処理を選択します。</span><span class="sxs-lookup"><span data-stu-id="85c6a-220">Choose what you want to happen when calls have been waiting in the queue for too long.</span></span>

1. <span data-ttu-id="85c6a-221">[最大 **待ち時間] を設定します**。</span><span class="sxs-lookup"><span data-stu-id="85c6a-221">Set the **Maximum wait time**.</span></span>

2. <span data-ttu-id="85c6a-222">通話がタイムアウトした場合に実行する操作を選択します。通話を切断するか、リダイレクトできます。</span><span class="sxs-lookup"><span data-stu-id="85c6a-222">Choose what you want to do when a call times out. You can disconnect the call or redirect it.</span></span> <span data-ttu-id="85c6a-223">次のいずれかの接続先に通話をリダイレクトすることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="85c6a-223">We recommend that you redirect the call to one of the following destinations:</span></span>
    - <span data-ttu-id="85c6a-224">**組織内のユーザー** - 音声通話を受信できる組織内のユーザー</span><span class="sxs-lookup"><span data-stu-id="85c6a-224">**Person in the organization** - a person in your organization who is able to receive voice calls</span></span>
    - <span data-ttu-id="85c6a-225">**音声アプリ** - 自動応答または別の通話キュー。</span><span class="sxs-lookup"><span data-stu-id="85c6a-225">**Voice app** - an auto attendant or another call queue.</span></span> <span data-ttu-id="85c6a-226">(この宛先を選ぶときに、自動応答または通話キューに関連付けられているリソース アカウントを選ぶ。</span><span class="sxs-lookup"><span data-stu-id="85c6a-226">(Choose the resource account associated with the auto attendant or call queue when choosing this destination.)</span></span>
    - <span data-ttu-id="85c6a-227">**外部電話番号** - 任意の電話番号。</span><span class="sxs-lookup"><span data-stu-id="85c6a-227">**External phone number** - any phone number.</span></span> <span data-ttu-id="85c6a-228">次の形式を使用します: +[国コード][郵便番号][電話番号]</span><span class="sxs-lookup"><span data-stu-id="85c6a-228">Use this format: +[country code][area code][phone number]</span></span>
    - <span data-ttu-id="85c6a-229">**ボイス** メール - 作成したチームのボイス メールボックスを使用できます。</span><span class="sxs-lookup"><span data-stu-id="85c6a-229">**Voicemail** - you can use the voice mailbox of the team that you created.</span></span>

    ![通話タイムアウト設定のスクリーンショット](../media/call-queue-timeout-handling.png)

3. <span data-ttu-id="85c6a-231">**[保存]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="85c6a-231">Click **Save**.</span></span>

<span data-ttu-id="85c6a-232">これで通話キューのセットアップが完了します。</span><span class="sxs-lookup"><span data-stu-id="85c6a-232">This completes the setup of your call queue.</span></span> <span data-ttu-id="85c6a-233">次に、自動応答 [を設定できます](create-a-phone-system-auto-attendant-smb.md)。</span><span class="sxs-lookup"><span data-stu-id="85c6a-233">Next, you may want to [set up an auto attendant](create-a-phone-system-auto-attendant-smb.md).</span></span>

---

