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
ms.openlocfilehash: ded780f0793a503e4f4089c7a201e659008e9eb7
ms.sourcegitcommit: 5a39061c2156531f4b7f5f69eecf81a8c8b238d0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/27/2021
ms.locfileid: "52030127"
---
# <a name="create-a-call-queue---small-business-tutorial"></a><span data-ttu-id="84207-103">通話キューの作成 - 小規模ビジネス向けチュートリアル</span><span class="sxs-lookup"><span data-stu-id="84207-103">Create a call queue - small business tutorial</span></span>

<span data-ttu-id="84207-104">通話キューは、特定の問題や質問に役立つ組織内のユーザーに発信者をルーティングする方法を提供します。</span><span class="sxs-lookup"><span data-stu-id="84207-104">Call queues provide a method of routing callers to people in your organization who can help with a particular issue or question.</span></span> <span data-ttu-id="84207-105">呼び出しは、キュー内のユーザー (エージェントと呼ばれる) に一度に 1 回配布 *されます*。</span><span class="sxs-lookup"><span data-stu-id="84207-105">Calls are distributed one at a time to the people in the queue (who are known as *agents*).</span></span> 

<span data-ttu-id="84207-106">呼び出しキューには、次の機能が提供されます。</span><span class="sxs-lookup"><span data-stu-id="84207-106">Call queues provide:</span></span>

- <span data-ttu-id="84207-107">あいさつメッセージ。</span><span class="sxs-lookup"><span data-stu-id="84207-107">A greeting message.</span></span>

- <span data-ttu-id="84207-108">ユーザーがキューで保留を待機している間の音楽。</span><span class="sxs-lookup"><span data-stu-id="84207-108">Music while people are waiting on hold in a queue.</span></span>

- <span data-ttu-id="84207-109">通話ルーティング - *First In、First Out* (FIFO) の順序でエージェントに送信します。</span><span class="sxs-lookup"><span data-stu-id="84207-109">Call routing - in *First In, First Out* (FIFO) order - to agents.</span></span>

- <span data-ttu-id="84207-110">キュー オーバーフローとタイムアウトの処理オプション。</span><span class="sxs-lookup"><span data-stu-id="84207-110">Handling options for queue overflow and timeout.</span></span>

#### <a name="before-you-begin"></a><span data-ttu-id="84207-111">はじめに</span><span class="sxs-lookup"><span data-stu-id="84207-111">Before you begin</span></span>

<span data-ttu-id="84207-112">電話システム [- 仮想ユーザー ライセンスを](../teams-add-on-licensing/virtual-user.md) まだ持ってない場合は、一部の電話システムを取得します。</span><span class="sxs-lookup"><span data-stu-id="84207-112">Get some [Phone System - Virtual User licenses](../teams-add-on-licensing/virtual-user.md) if you don't already have them.</span></span> <span data-ttu-id="84207-113">設定する各通話キューと自動応答ごとに 1 つを取得します。</span><span class="sxs-lookup"><span data-stu-id="84207-113">Get one for each call queue and auto attendant that you plan to set up.</span></span> <span data-ttu-id="84207-114">これらのライセンスは無料なので、今後セットアップに変更を加える場合に備え、追加のライセンスを取得してください。</span><span class="sxs-lookup"><span data-stu-id="84207-114">These licenses are free, so we suggest getting a few extra in case you decide to make changes to your setup in the future.</span></span>

<span data-ttu-id="84207-115">通話キュー内のエージェントがダイヤルアウトして顧客の通話を返す場合があります。通話エージェントの発信者 ID をメインの電話番号または適切な自動応答の番号に設定してください。</span><span class="sxs-lookup"><span data-stu-id="84207-115">Since agents in a call queue may dial out to return a customer call, consider setting the caller ID for your call agents to your main phone number or the number of an appropriate auto attendant.</span></span> <span data-ttu-id="84207-116">詳細については [、「Microsoft Teams で発信者 ID ポリシーを管理する」](../caller-id-policies.md) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="84207-116">See [Manage caller ID policies in Microsoft Teams](../caller-id-policies.md) for more information.</span></span>

<a name="steps"></a>

#### <a name="follow-these-steps-to-set-up-your-call-queue"></a><span data-ttu-id="84207-117">次の手順に従って、通話キューを設定します。</span><span class="sxs-lookup"><span data-stu-id="84207-117">Follow these steps to set up your call queue</span></span>

# <a name="step-1brcreate-a-team"></a>[<span data-ttu-id="84207-118">手順 1 <br> チームを作成する</span><span class="sxs-lookup"><span data-stu-id="84207-118">Step 1<br>Create a team</span></span>](#tab/create-team)

<span data-ttu-id="84207-119">呼び出しキューを作成するときに、個々のユーザーをキューに追加したり、既存のセキュリティ グループ、Microsoft 365 グループ、または Microsoft Teams チームを使用することができます。</span><span class="sxs-lookup"><span data-stu-id="84207-119">When creating a call queue, you can add individual users to the queue, or you can use an existing security group, Microsoft 365 group, or Microsoft Teams team.</span></span> <span data-ttu-id="84207-120">チーム チャネル [を使用することをお勧めします](https://support.microsoft.com/office/9f07dabe-91c6-4a9b-a545-8ffdddd2504e)。</span><span class="sxs-lookup"><span data-stu-id="84207-120">We recommend [using a team channel](https://support.microsoft.com/office/9f07dabe-91c6-4a9b-a545-8ffdddd2504e).</span></span> <span data-ttu-id="84207-121">これにより、キューのメンバーが互いにチャットしたり、アイデアを共有したり、ドキュメントや他のリソースを作成して、顧客を支援することができます。</span><span class="sxs-lookup"><span data-stu-id="84207-121">This allows members of the queue to chat with each other, share ideas, and create documents or other resources to help them help your customers.</span></span> <span data-ttu-id="84207-122">また、チームは、発信者が数時間後にメッセージを残したり、キューが最大容量に達した場合にメッセージを残したりするボイス メールボックスも提供します。</span><span class="sxs-lookup"><span data-stu-id="84207-122">A team also provides a voice mailbox for callers to leave a message after hours or if the queue reaches its maximum capacity.</span></span>

<span data-ttu-id="84207-123">チームを作成するには</span><span class="sxs-lookup"><span data-stu-id="84207-123">To create a team</span></span>

1. <span data-ttu-id="84207-124">まず、アプリ **の左側にある [Teams]** をクリックし、[参加] をクリックするか、チームリストの下部にあるチームを作成します。</span><span class="sxs-lookup"><span data-stu-id="84207-124">First, click **Teams** on the left side of the app, then click **Join or create a team** at the bottom of your teams list.</span></span>

2. <span data-ttu-id="84207-125">次に、[ **チームの作成]** (最初のカード、左上隅) をクリックします。</span><span class="sxs-lookup"><span data-stu-id="84207-125">Then click **Create team** (first card, top left corner).</span></span>

3. <span data-ttu-id="84207-126">[チーム **を最初から作成する] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="84207-126">Choose **Build a team from scratch**.</span></span>

4. <span data-ttu-id="84207-127">次に、パブリック チームとプライベート チームの 2 つを選択します。</span><span class="sxs-lookup"><span data-stu-id="84207-127">Next, choose whether you want a public or private team.</span></span> <span data-ttu-id="84207-128">チームに **参加** することで、ユーザーが意図せずにキューに参加しないように、通話キューのプライベートを使用することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="84207-128">We recommend **Private** for your call queue to avoid people unintentionally becoming part of the queue by joining the team.</span></span>

5. <span data-ttu-id="84207-129">チームに名前を付け、オプションの説明を追加します。</span><span class="sxs-lookup"><span data-stu-id="84207-129">Name your team and add an optional description.</span></span>

6. <span data-ttu-id="84207-130">完了したら、[作成] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="84207-130">When you're done, click **Create**.</span></span>

8. <span data-ttu-id="84207-131">通話キューに必要なユーザーの名前を入力し、[追加] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="84207-131">Type the names of the people that you want to have in your call queue, and then click **Add**.</span></span>

9. <span data-ttu-id="84207-132">[**閉じる**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="84207-132">Click **Close**.</span></span> <span data-ttu-id="84207-133">チームに追加したユーザーは、チームのメンバーとして知らせるメールを受け取り、チームがチームの一覧に表示されます。</span><span class="sxs-lookup"><span data-stu-id="84207-133">People you add to a team will receive an email letting them know they are now a member of your team and the team will show up in their teams list.</span></span>

<span data-ttu-id="84207-134">次に、呼び出しキューで使用するチャネルを追加します。</span><span class="sxs-lookup"><span data-stu-id="84207-134">Next, we'll add a channel to use with the call queue.</span></span>

<span data-ttu-id="84207-135">チャネルを追加するには</span><span class="sxs-lookup"><span data-stu-id="84207-135">To add a channel</span></span>

1. <span data-ttu-id="84207-136">Teams で、作成したチームを見つけ、[その他のオプション (....)] をクリックし、[チャンネルの追加]**をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="84207-136">In Teams, find the team you just created, click **More options** (...), and then click **Add channel**.</span></span>

2. <span data-ttu-id="84207-137">チャネルの名前と説明を入力し、[追加] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="84207-137">Type a name and description for the channel, and then click **Add**.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="84207-138">手順 2 - リソース アカウントの></span><span class="sxs-lookup"><span data-stu-id="84207-138">Step 2 - Resource accounts ></span></span>](/microsoftteams/business-voice/create-a-phone-system-call-queue-smb?tabs=resource-account#steps)

# <a name="step-2brresource-accounts"></a>[<span data-ttu-id="84207-139">手順 2 <br> リソース アカウント</span><span class="sxs-lookup"><span data-stu-id="84207-139">Step 2<br>Resource accounts</span></span>](#tab/resource-account)

<span data-ttu-id="84207-140">作成する各呼び出しキューには、リソース アカウントが必要です。</span><span class="sxs-lookup"><span data-stu-id="84207-140">Each call queue that you create requires a resource account.</span></span> <span data-ttu-id="84207-141">これは、ユーザー アカウントに似ていますが、アカウントがユーザーではなく自動応答キューまたは通話キューに関連付けられている点を除きます。</span><span class="sxs-lookup"><span data-stu-id="84207-141">This is similar to a user account, except the account is associated with an auto attendant or call queue instead of a person.</span></span> <span data-ttu-id="84207-142">この手順では、アカウントを作成し *、Microsoft 365* Phone System - Virtual User ライセンスを割り当て、それを使用して通話キューの作成を開始します。</span><span class="sxs-lookup"><span data-stu-id="84207-142">In this step, we'll create the account, assign it a *Microsoft 365 Phone System - Virtual User* license, and then use it to start creating the call queue.</span></span>

### <a name="create-a-resource-account"></a><span data-ttu-id="84207-143">リソース アカウントを作成する</span><span class="sxs-lookup"><span data-stu-id="84207-143">Create a resource account</span></span>

<span data-ttu-id="84207-144">Teams 管理センターでリソース アカウントを作成できます。</span><span class="sxs-lookup"><span data-stu-id="84207-144">You can create a resource account in the Teams admin center.</span></span>

1. <span data-ttu-id="84207-145">Teams 管理センターで、[組織全体の設定] **を展開** し、[リソース アカウント] **をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="84207-145">In the Teams admin center, expand **Org-wide settings**, and then click **Resource accounts**.</span></span>

2. <span data-ttu-id="84207-146">**[追加]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="84207-146">Click **Add**.</span></span>

3. <span data-ttu-id="84207-147">[リソース **アカウントの追加]** ウィンドウで、[表示名] 、[ユーザー名] を **入力し**、[リソース **アカウントの** 種類] で [通話キュー]**を選択します**。</span><span class="sxs-lookup"><span data-stu-id="84207-147">In the **Add resource account** pane, fill out **Display name**, **Username**, and choose **Call queue** for the **Resource account type**.</span></span> <span data-ttu-id="84207-148">エージェントは、キューから着信呼び出しを受信すると、表示名を表示します。</span><span class="sxs-lookup"><span data-stu-id="84207-148">Agents will see the display name when they receive an incoming call from the queue.</span></span>

    ![リソース アカウントのユーザー インターフェイスの追加のスクリーンショット](../media/resource-account-add-cq.png)

4. <span data-ttu-id="84207-150">**[保存]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="84207-150">Click **Save**.</span></span>

   <span data-ttu-id="84207-151">新しいアカウントがアカウントの一覧に表示されます。</span><span class="sxs-lookup"><span data-stu-id="84207-151">The new account will appear in the list of accounts.</span></span>

   ![リソース アカウントの一覧のスクリーンショット](../media/resource-accounts-page.png)

### <a name="assign-a-license"></a><span data-ttu-id="84207-153">ライセンスを割り当てる</span><span class="sxs-lookup"><span data-stu-id="84207-153">Assign a license</span></span>

<span data-ttu-id="84207-154">リソース アカウントに *Microsoft 365 Phone System - Virtual User ライセンスを割* り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="84207-154">You must assign a *Microsoft 365 Phone System - Virtual User* license to the resource account.</span></span>

1. <span data-ttu-id="84207-155">Microsoft 365 管理センターの [アクティブなユーザー] リストで、ライセンスを割り当てるリソース アカウントをクリックします。</span><span class="sxs-lookup"><span data-stu-id="84207-155">In the Microsoft 365 admin center, in the **Active users** list, click the resource account to which you want to assign a license.</span></span>

2. <span data-ttu-id="84207-156">[ライセンスと **アプリ] タブの**[**ライセンス] で\*\*\*\*、[Microsoft 365 電話** システム - 仮想ユーザー] を選択します。</span><span class="sxs-lookup"><span data-stu-id="84207-156">On the **Licenses and Apps** tab, under **Licenses**, select **Microsoft 365 Phone System - Virtual User**.</span></span>

3. <span data-ttu-id="84207-157">[変更 **を保存] をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="84207-157">Click **Save changes**.</span></span>

    ![Microsoft 365 管理センターでのライセンスの割り当てユーザー インターフェイスのスクリーンショット](../media/resource-account-assign-virtual-user-license.png)

### <a name="create-a-call-queue"></a><span data-ttu-id="84207-159">呼び出しキューを作成する</span><span class="sxs-lookup"><span data-stu-id="84207-159">Create a call queue</span></span>

<span data-ttu-id="84207-160">次に、新しい呼び出しキューの作成を開始し、リソース アカウントを割り当てる予定です。</span><span class="sxs-lookup"><span data-stu-id="84207-160">Next, we'll start creating a new call queue and assign the resource account.</span></span>

1. <span data-ttu-id="84207-161">Teams 管理センターで 、[Voice] を **展開し、[** キューの呼び出し] を **クリック** し、[追加] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="84207-161">In the Teams admin center, expand **Voice**, click **Call queues**, and then click **Add**.</span></span>

1. <span data-ttu-id="84207-162">呼び出しキューの名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="84207-162">Type a name for the call queue.</span></span>

2. <span data-ttu-id="84207-163">[**アカウントの追加]** をクリックし、この呼び出しキューで使用するリソースアカウントを検索し、[追加] をクリックし、[追加] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="84207-163">Click **Add accounts**, search for the resource account that you want to use with this call queue, click **Add**, and then click **Add**.</span></span>

3. <span data-ttu-id="84207-164">言語を選択します。</span><span class="sxs-lookup"><span data-stu-id="84207-164">Choose a language.</span></span> <span data-ttu-id="84207-165">この言語は、システムで生成された音声プロンプトとボイスメールの文字起こし (有効にした場合) に使用されます。</span><span class="sxs-lookup"><span data-stu-id="84207-165">This language will be used for system-generated voice prompts and voicemail transcription (if you enable them).</span></span>

    ![リソース アカウントと言語設定のスクリーンショット](../media/call-queue-name-language.png)

4. <span data-ttu-id="84207-167">発信者がキューに到着するときに、発信者にあいさつを再生する場合に指定します。</span><span class="sxs-lookup"><span data-stu-id="84207-167">Specify if you want to play a greeting to callers when they arrive in the queue.</span></span> <span data-ttu-id="84207-168">再生するあいさつを含む MP3、WAV、または WMA ファイルをアップロードする必要があります。</span><span class="sxs-lookup"><span data-stu-id="84207-168">You must upload an MP3, WAV, or WMA file containing the greeting that you want to play.</span></span>

5. <span data-ttu-id="84207-169">Teams は、キューで保留の間、呼び出し元に既定の音楽を提供します。</span><span class="sxs-lookup"><span data-stu-id="84207-169">Teams provides default music to callers while they are on hold in a queue.</span></span> <span data-ttu-id="84207-170">特定のオーディオ ファイルを再生する場合は、[オーディオ ファイルの再生] を選択し、MP3、WAV、または WMA ファイルをアップロードします。</span><span class="sxs-lookup"><span data-stu-id="84207-170">If you want to play a specific audio file, choose **Play an audio file** and upload an MP3, WAV, or WMA file.</span></span>

   > [!NOTE]
   > <span data-ttu-id="84207-171">アップロードされた記録は、5 MB 以下に設定できます。</span><span class="sxs-lookup"><span data-stu-id="84207-171">The uploaded recording can be no larger than 5 MB.</span></span>
   > <span data-ttu-id="84207-172">Teams 呼び出しキューで提供される既定の音楽には、組織が支払うロイヤリティは無料です。</span><span class="sxs-lookup"><span data-stu-id="84207-172">The default music supplied in Teams call queues is free of any royalties payable by your organization.</span></span> 

> [!div class="nextstepaction"]
> [<span data-ttu-id="84207-173">手順 3 - エージェントを呼び出></span><span class="sxs-lookup"><span data-stu-id="84207-173">Step 3 - Call agents ></span></span>](/microsoftteams/business-voice/create-a-phone-system-call-queue-smb?tabs=call-agents#steps)

# <a name="step-3brcall-agents"></a>[<span data-ttu-id="84207-174">手順 3 <br> エージェントを呼び出す</span><span class="sxs-lookup"><span data-stu-id="84207-174">Step 3<br>Call agents</span></span>](#tab/call-agents)

<span data-ttu-id="84207-175">エージェントを呼び出しキューに追加するには、先に作成したチームとチャネルにエージェントを追加します。</span><span class="sxs-lookup"><span data-stu-id="84207-175">To add agents to the call queue, we'll add them to the team and channel that we created earlier.</span></span>

1. <span data-ttu-id="84207-176">[チームの **選択] オプションを選択し** 、[チャンネルの追加 **] をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="84207-176">Select the **Choose a team** option and click **Add a channel**.</span></span>
2. <span data-ttu-id="84207-177">作成したチームの名前を入力して選択し、[追加] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="84207-177">Type the name of the team that you created, select it, and click **Add**.</span></span>
3. <span data-ttu-id="84207-178">キュー用に作成したチャネルを選択します。</span><span class="sxs-lookup"><span data-stu-id="84207-178">Select the channel that you created for the queue.</span></span>
3. <span data-ttu-id="84207-179">[**適用**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="84207-179">Click **Apply**.</span></span>

    ![通話キューのユーザーとグループの設定のスクリーンショット](../media/call-queue-users-groups.png)

> [!NOTE]
> <span data-ttu-id="84207-181">新しいユーザーがチームに追加された場合、最初の呼び出しが到着するには最大 8 時間かかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="84207-181">When new users are added to the team, it can take up to eight hours for their first call to arrive.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="84207-182">手順 4 - リソース アカウントの></span><span class="sxs-lookup"><span data-stu-id="84207-182">Step 4 - Resource accounts ></span></span>](/microsoftteams/business-voice/create-a-phone-system-call-queue-smb?tabs=call-routing#steps)

# <a name="step-4brcall-routing"></a>[<span data-ttu-id="84207-183">手順 4 通話 <br> ルーティング</span><span class="sxs-lookup"><span data-stu-id="84207-183">Step 4<br>Call routing</span></span>](#tab/call-routing)

<span data-ttu-id="84207-184">使用する呼び出しルーティング方法を選択します。</span><span class="sxs-lookup"><span data-stu-id="84207-184">Choose the call routing method that you want to use.</span></span>

1. <span data-ttu-id="84207-185">[会議 **モード] を [自動** ] に **設定します**。</span><span class="sxs-lookup"><span data-stu-id="84207-185">Set **Conference mode** to **Auto**.</span></span>

2. <span data-ttu-id="84207-186">使用する **ルーティング方法** を選択します。</span><span class="sxs-lookup"><span data-stu-id="84207-186">Choose the **Routing method** you want to use.</span></span> <span data-ttu-id="84207-187">これにより、エージェントがキューから呼び出しを受信する順序が決定されます。</span><span class="sxs-lookup"><span data-stu-id="84207-187">This determines the order in which agents receive calls from the queue.</span></span> <span data-ttu-id="84207-188">シリアル ルーティング **またはラウンド ロビン** をお  **勧めします**。</span><span class="sxs-lookup"><span data-stu-id="84207-188">We recommend **Serial routing** or  **Round robin**.</span></span> <span data-ttu-id="84207-189">次のオプションから選択します。</span><span class="sxs-lookup"><span data-stu-id="84207-189">Choose from these options:</span></span>

    - <span data-ttu-id="84207-190">**アテンダント ルーティング** では、キュー内のすべてのエージェントが同時に呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="84207-190">**Attendant routing** rings all agents in the queue at the same time.</span></span> <span data-ttu-id="84207-191">呼び出しを受け取る最初の呼び出しエージェントは、呼び出しを取得します。</span><span class="sxs-lookup"><span data-stu-id="84207-191">The first call agent to pick up the call gets the call.</span></span>

    - <span data-ttu-id="84207-192">**シリアル ルーティングでは** 、すべての呼び出しエージェントが 1 つ 1 つリングされます。</span><span class="sxs-lookup"><span data-stu-id="84207-192">**Serial routing** rings all call agents one by one.</span></span> <span data-ttu-id="84207-193">エージェントが通話を却下または取り上げない場合、呼び出しは次のエージェントを呼び出し、そのエージェントが取り上げられるか、または時間が切れるまですべてのエージェントを試します。</span><span class="sxs-lookup"><span data-stu-id="84207-193">If an agent dismisses or does not pick up a call, the call will ring the next agent and will try all agents until it is picked up or times out.</span></span>

    - <span data-ttu-id="84207-194">**ラウンド ロビンは** 、着信呼び出しのルーティングのバランスを取り、各呼び出しエージェントがキューから同じ数の呼び出しを取得します。</span><span class="sxs-lookup"><span data-stu-id="84207-194">**Round robin** balances the routing of incoming calls so that each call agent gets the same number of calls from the queue.</span></span> <span data-ttu-id="84207-195">これは、すべての通話エージェント間で均等な機会を確保するために、受信販売環境で望ましい場合があります。</span><span class="sxs-lookup"><span data-stu-id="84207-195">This may be desirable in an inbound sales environment to assure equal opportunity among all the call agents.</span></span>

    - <span data-ttu-id="84207-196">**アイドル時間が** 最も長いエージェントに各呼び出しがルーティングされます。</span><span class="sxs-lookup"><span data-stu-id="84207-196">**Longest idle** routes each call to the agent who has been idle the longest time.</span></span> <span data-ttu-id="84207-197">(プレゼンス状態が 10 分以上離れたエージェントは含まれません)。</span><span class="sxs-lookup"><span data-stu-id="84207-197">(Agents whose presence state has been Away for more than 10 minutes are not included.)</span></span>

    ![会議モードとルーティング方法の設定のスクリーンショット](../media/call-queue-conference-mode-routing-method.png)

3. <span data-ttu-id="84207-199">プレゼンス **ベースのルーティングを有効** にする。</span><span class="sxs-lookup"><span data-stu-id="84207-199">Turn **Presence-based routing** on.</span></span> <span data-ttu-id="84207-200">これにより、プレゼンス状態が [使用可能] のエージェントに呼び出しが **ルーティングされます**。</span><span class="sxs-lookup"><span data-stu-id="84207-200">This routes calls to agents whose presence status is **Available**.</span></span>

4. <span data-ttu-id="84207-201">エージェントが通話をオプトアウトすることを許可する場合に選択します。</span><span class="sxs-lookup"><span data-stu-id="84207-201">Choose if you want to allow agents to opt out of calls.</span></span>

5. <span data-ttu-id="84207-202">エージェントアラート **時間を設定** して、キューが呼び出しを次のエージェントにリダイレクトする前にエージェントの電話が鳴る時間を指定します。</span><span class="sxs-lookup"><span data-stu-id="84207-202">Set an **Agent alert time** to specify how long an agent's phone will ring before the queue redirects the call to the next agent.</span></span>

    ![ルーティング、オプトアウト、アラート時間の設定のスクリーンショット](../media/call-queue-presence-agents-time.png)

> [!div class="nextstepaction"]
> [<span data-ttu-id="84207-204">手順 5 - 呼び出しオーバーフロー ></span><span class="sxs-lookup"><span data-stu-id="84207-204">Step 5 - Call overflow ></span></span>](/microsoftteams/business-voice/create-a-phone-system-call-queue-smb?tabs=call-overflow#steps)

# <a name="step-5brcall-overflow"></a>[<span data-ttu-id="84207-205">手順 5 呼び <br> 出しオーバーフロー</span><span class="sxs-lookup"><span data-stu-id="84207-205">Step 5<br>Call overflow</span></span>](#tab/call-overflow)

<span data-ttu-id="84207-206">キューの最大数を超える呼び出しを処理する方法を選択します。</span><span class="sxs-lookup"><span data-stu-id="84207-206">Choose how you want to handle calls that exceed the maximum in the queue.</span></span>

1. <span data-ttu-id="84207-207">キューの **最大呼び出しを設定します**。</span><span class="sxs-lookup"><span data-stu-id="84207-207">Set the **Maximum calls in the queue**.</span></span>

2. <span data-ttu-id="84207-208">呼び出しの最大数に達した場合に実行する操作を選択します。</span><span class="sxs-lookup"><span data-stu-id="84207-208">Choose what you want to do when the maximum number of calls is reached.</span></span> <span data-ttu-id="84207-209">呼び出しを切断するか、リダイレクトできます。</span><span class="sxs-lookup"><span data-stu-id="84207-209">You can disconnect the call or redirect it.</span></span> <span data-ttu-id="84207-210">次のいずれかの宛先に呼び出しをリダイレクトすることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="84207-210">We recommend that you redirect the call to one of the following destinations:</span></span>
    - <span data-ttu-id="84207-211">**組織内のユーザー** - 音声通話を受信できる組織内のユーザー</span><span class="sxs-lookup"><span data-stu-id="84207-211">**Person in the organization** - a person in your organization who is able to receive voice calls</span></span>
    - <span data-ttu-id="84207-212">**音声アプリ** - 自動応答または別の通話キュー。</span><span class="sxs-lookup"><span data-stu-id="84207-212">**Voice app** - an auto attendant or another call queue.</span></span> <span data-ttu-id="84207-213">(この宛先を選択する場合は、自動応答に関連付けられているリソース アカウントを選択するか、キューを呼び出します)。</span><span class="sxs-lookup"><span data-stu-id="84207-213">(Choose the resource account associated with the auto attendant or call queue when choosing this destination.)</span></span>
    - <span data-ttu-id="84207-214">**外部電話番号** - 任意の電話番号。</span><span class="sxs-lookup"><span data-stu-id="84207-214">**External phone number** - any phone number.</span></span> <span data-ttu-id="84207-215">次の形式を使用します。+[国コード][地域コード][電話番号]</span><span class="sxs-lookup"><span data-stu-id="84207-215">Use this format: +[country code][area code][phone number]</span></span>
    - <span data-ttu-id="84207-216">**ボイス** メール - 作成したチームのボイス メールボックスを使用できます。</span><span class="sxs-lookup"><span data-stu-id="84207-216">**Voicemail** - you can use the voice mailbox of the team that you created.</span></span>

    ![呼び出しオーバーフロー設定のスクリーンショット](../media/call-queue-overflow-handling.png)

> [!div class="nextstepaction"]
> [<span data-ttu-id="84207-218">手順 6 - タイムアウトの呼び出し></span><span class="sxs-lookup"><span data-stu-id="84207-218">Step 6 - Call timeout ></span></span>](/microsoftteams/business-voice/create-a-phone-system-call-queue-smb?tabs=call-timeout#steps)

# <a name="step-6brcall-timeout"></a>[<span data-ttu-id="84207-219">手順 6 <br> タイムアウトを呼び出す</span><span class="sxs-lookup"><span data-stu-id="84207-219">Step 6<br>Call timeout</span></span>](#tab/call-timeout)

<span data-ttu-id="84207-220">呼び出しがキューで待ち時間が長すぎるときに発生する処理を選択します。</span><span class="sxs-lookup"><span data-stu-id="84207-220">Choose what you want to happen when calls have been waiting in the queue for too long.</span></span>

1. <span data-ttu-id="84207-221">[最大 **待機時間] を設定します**。</span><span class="sxs-lookup"><span data-stu-id="84207-221">Set the **Maximum wait time**.</span></span>

2. <span data-ttu-id="84207-222">通話がアウトした場合に実行する操作を選択します。呼び出しを切断するか、リダイレクトできます。</span><span class="sxs-lookup"><span data-stu-id="84207-222">Choose what you want to do when a call times out. You can disconnect the call or redirect it.</span></span> <span data-ttu-id="84207-223">次のいずれかの宛先に呼び出しをリダイレクトすることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="84207-223">We recommend that you redirect the call to one of the following destinations:</span></span>
    - <span data-ttu-id="84207-224">**組織内のユーザー** - 音声通話を受信できる組織内のユーザー</span><span class="sxs-lookup"><span data-stu-id="84207-224">**Person in the organization** - a person in your organization who is able to receive voice calls</span></span>
    - <span data-ttu-id="84207-225">**音声アプリ** - 自動応答または別の通話キュー。</span><span class="sxs-lookup"><span data-stu-id="84207-225">**Voice app** - an auto attendant or another call queue.</span></span> <span data-ttu-id="84207-226">(この宛先を選択する場合は、自動応答に関連付けられているリソース アカウントを選択するか、キューを呼び出します)。</span><span class="sxs-lookup"><span data-stu-id="84207-226">(Choose the resource account associated with the auto attendant or call queue when choosing this destination.)</span></span>
    - <span data-ttu-id="84207-227">**外部電話番号** - 任意の電話番号。</span><span class="sxs-lookup"><span data-stu-id="84207-227">**External phone number** - any phone number.</span></span> <span data-ttu-id="84207-228">次の形式を使用します。+[国コード][地域コード][電話番号]</span><span class="sxs-lookup"><span data-stu-id="84207-228">Use this format: +[country code][area code][phone number]</span></span>
    - <span data-ttu-id="84207-229">**ボイス** メール - 作成したチームのボイス メールボックスを使用できます。</span><span class="sxs-lookup"><span data-stu-id="84207-229">**Voicemail** - you can use the voice mailbox of the team that you created.</span></span>

    ![通話タイムアウト設定のスクリーンショット](../media/call-queue-timeout-handling.png)

3. <span data-ttu-id="84207-231">**[保存]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="84207-231">Click **Save**.</span></span>

<span data-ttu-id="84207-232">これで、通話キューのセットアップが完了します。</span><span class="sxs-lookup"><span data-stu-id="84207-232">This completes the setup of your call queue.</span></span> <span data-ttu-id="84207-233">次に、自動応答 [を設定できます](create-a-phone-system-auto-attendant-smb.md)。</span><span class="sxs-lookup"><span data-stu-id="84207-233">Next, you may want to [set up an auto attendant](create-a-phone-system-auto-attendant-smb.md).</span></span>

---

