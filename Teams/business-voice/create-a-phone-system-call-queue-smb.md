---
title: 小規模ビジネス向けチュートリアルでMicrosoft Teamsキューを作成する
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
description: 小規模企業向け通話キューを設定する方法については、Microsoft 365 Business Voice。
ms.openlocfilehash: e7141d32015207469346e018bc12bc362254ba2f
ms.sourcegitcommit: d77104d5606ff93a792e8712d6c7780ae247b536
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/25/2021
ms.locfileid: "53126923"
---
# <a name="create-a-call-queue---small-business-tutorial"></a><span data-ttu-id="812f0-103">通話キューを作成する - 小規模ビジネス向けチュートリアル</span><span class="sxs-lookup"><span data-stu-id="812f0-103">Create a call queue - small business tutorial</span></span>

<span data-ttu-id="812f0-104">通話キューは、特定の問題や質問に役立つ組織内のユーザーに発信者をルーティングする方法を提供します。</span><span class="sxs-lookup"><span data-stu-id="812f0-104">Call queues provide a method of routing callers to people in your organization who can help with a particular issue or question.</span></span> <span data-ttu-id="812f0-105">呼び出しは、キュー内のユーザー (エージェントと呼ばれる) に一度に 1 回 *配布されます*。</span><span class="sxs-lookup"><span data-stu-id="812f0-105">Calls are distributed one at a time to the people in the queue (who are known as *agents*).</span></span> 

<span data-ttu-id="812f0-106">呼び出しキューには、次の機能があります。</span><span class="sxs-lookup"><span data-stu-id="812f0-106">Call queues provide:</span></span>

- <span data-ttu-id="812f0-107">あいさつメッセージ。</span><span class="sxs-lookup"><span data-stu-id="812f0-107">A greeting message.</span></span>

- <span data-ttu-id="812f0-108">ユーザーがキューで保留を待機している間の音楽。</span><span class="sxs-lookup"><span data-stu-id="812f0-108">Music while people are waiting on hold in a queue.</span></span>

- <span data-ttu-id="812f0-109">コール ルーティング - *First In,First Out* (FIFO) order - to agents.</span><span class="sxs-lookup"><span data-stu-id="812f0-109">Call routing - in *First In, First Out* (FIFO) order - to agents.</span></span>

- <span data-ttu-id="812f0-110">キューのオーバーフローとタイムアウトの処理オプション。</span><span class="sxs-lookup"><span data-stu-id="812f0-110">Handling options for queue overflow and timeout.</span></span>

#### <a name="video-demonstration"></a><span data-ttu-id="812f0-111">ビデオデモ</span><span class="sxs-lookup"><span data-stu-id="812f0-111">Video demonstration</span></span>

<span data-ttu-id="812f0-112">このビデオでは、仮想ネットワークで通話キューを作成する方法Teams。</span><span class="sxs-lookup"><span data-stu-id="812f0-112">This video demonstrates how to create a call queue in Teams.</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RWCF23?autoplay=false]

#### <a name="before-you-begin"></a><span data-ttu-id="812f0-113">はじめに</span><span class="sxs-lookup"><span data-stu-id="812f0-113">Before you begin</span></span>

<span data-ttu-id="812f0-114">一部電話システム[取得 - 仮想ユーザー](../teams-add-on-licensing/virtual-user.md)ライセンスをまだ持ってない場合は、そのライセンスを取得します。</span><span class="sxs-lookup"><span data-stu-id="812f0-114">Get some [Phone System - Virtual User licenses](../teams-add-on-licensing/virtual-user.md) if you don't already have them.</span></span> <span data-ttu-id="812f0-115">設定する予定の通話キューと自動応答ごとに 1 つを取得します。</span><span class="sxs-lookup"><span data-stu-id="812f0-115">Get one for each call queue and auto attendant that you plan to set up.</span></span> <span data-ttu-id="812f0-116">これらのライセンスは無料なので、後でセットアップを変更する場合に備え、追加のライセンスを取得できます。</span><span class="sxs-lookup"><span data-stu-id="812f0-116">These licenses are free, so we suggest getting a few extra in case you decide to make changes to your setup in the future.</span></span>

<span data-ttu-id="812f0-117">通話キュー内のエージェントはダイヤルアウトして顧客の通話を返す可能性があります。通話エージェントの発信者番号をメインの電話番号または適切な自動応答の番号に設定します。</span><span class="sxs-lookup"><span data-stu-id="812f0-117">Since agents in a call queue may dial out to return a customer call, consider setting the caller ID for your call agents to your main phone number or the number of an appropriate auto attendant.</span></span> <span data-ttu-id="812f0-118">詳細[については、「Microsoft Teams で](../caller-id-policies.md)発信者番号ポリシーを管理する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="812f0-118">See [Manage caller ID policies in Microsoft Teams](../caller-id-policies.md) for more information.</span></span>

<a name="steps"></a>

#### <a name="follow-these-steps-to-set-up-your-call-queue"></a><span data-ttu-id="812f0-119">次の手順に従って通話キューを設定します。</span><span class="sxs-lookup"><span data-stu-id="812f0-119">Follow these steps to set up your call queue</span></span>

# <a name="step-1brcreate-a-team"></a>[<span data-ttu-id="812f0-120">手順 <br> 1: チームを作成する</span><span class="sxs-lookup"><span data-stu-id="812f0-120">Step 1<br>Create a team</span></span>](#tab/create-team)

<span data-ttu-id="812f0-121">通話キューを作成するときに、個々のユーザーをキューに追加したり、既存のセキュリティ グループ、Microsoft 365 グループ、または他のチームMicrosoft Teamsできます。</span><span class="sxs-lookup"><span data-stu-id="812f0-121">When creating a call queue, you can add individual users to the queue, or you can use an existing security group, Microsoft 365 group, or Microsoft Teams team.</span></span> <span data-ttu-id="812f0-122">チーム チャネル [を使用することをお勧めします](https://support.microsoft.com/office/9f07dabe-91c6-4a9b-a545-8ffdddd2504e)。</span><span class="sxs-lookup"><span data-stu-id="812f0-122">We recommend [using a team channel](https://support.microsoft.com/office/9f07dabe-91c6-4a9b-a545-8ffdddd2504e).</span></span> <span data-ttu-id="812f0-123">これにより、キューのメンバーは互いにチャットしたり、アイデアを共有したり、顧客を支援するドキュメントや他のリソースを作成することができます。</span><span class="sxs-lookup"><span data-stu-id="812f0-123">This allows members of the queue to chat with each other, share ideas, and create documents or other resources to help them help your customers.</span></span> <span data-ttu-id="812f0-124">また、チームは、発信者が数時間後にメッセージを残したり、キューが最大容量に達したりするためにボイス メールボックスを提供します。</span><span class="sxs-lookup"><span data-stu-id="812f0-124">A team also provides a voice mailbox for callers to leave a message after hours or if the queue reaches its maximum capacity.</span></span>

<span data-ttu-id="812f0-125">チームを作成するには</span><span class="sxs-lookup"><span data-stu-id="812f0-125">To create a team</span></span>

1. <span data-ttu-id="812f0-126">最初に **、Teams** の左側にある [チーム] をクリックし、チーム リストの下部にある [参加] または [チームの作成] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="812f0-126">First, click **Teams** on the left side of the app, then click **Join or create a team** at the bottom of your teams list.</span></span>

2. <span data-ttu-id="812f0-127">次に、[ **チームの作成]** (最初のカード、左上隅) をクリックします。</span><span class="sxs-lookup"><span data-stu-id="812f0-127">Then click **Create team** (first card, top left corner).</span></span>

3. <span data-ttu-id="812f0-128">[ **チームをゼロから作成する] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="812f0-128">Choose **Build a team from scratch**.</span></span>

4. <span data-ttu-id="812f0-129">次に、パブリック チームとプライベート チームの 2 つのチームを選択します。</span><span class="sxs-lookup"><span data-stu-id="812f0-129">Next, choose whether you want a public or private team.</span></span> <span data-ttu-id="812f0-130">チームに **参加** することで、ユーザーが意図せずにキューに参加しないように、通話キューに Private を使用することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="812f0-130">We recommend **Private** for your call queue to avoid people unintentionally becoming part of the queue by joining the team.</span></span>

5. <span data-ttu-id="812f0-131">チームに名前を付け、オプションの説明を追加します。</span><span class="sxs-lookup"><span data-stu-id="812f0-131">Name your team and add an optional description.</span></span>

6. <span data-ttu-id="812f0-132">完了したら、[作成] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="812f0-132">When you're done, click **Create**.</span></span>

8. <span data-ttu-id="812f0-133">通話キューに追加するユーザーの名前を入力し、[追加] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="812f0-133">Type the names of the people that you want to have in your call queue, and then click **Add**.</span></span>

9. <span data-ttu-id="812f0-134">[**閉じる**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="812f0-134">Click **Close**.</span></span> <span data-ttu-id="812f0-135">チームに追加したユーザーは、チームのメンバーになれたと知らせるメールを受け取り、チームの一覧にチームが表示されます。</span><span class="sxs-lookup"><span data-stu-id="812f0-135">People you add to a team will receive an email letting them know they are now a member of your team and the team will show up in their teams list.</span></span>

<span data-ttu-id="812f0-136">次に、通話キューで使用するチャネルを追加します。</span><span class="sxs-lookup"><span data-stu-id="812f0-136">Next, we'll add a channel to use with the call queue.</span></span>

<span data-ttu-id="812f0-137">チャネルを追加するには</span><span class="sxs-lookup"><span data-stu-id="812f0-137">To add a channel</span></span>

1. <span data-ttu-id="812f0-138">このTeams作成したチームを見つけ、[その他のオプション (...)] をクリックし、[チャネルの追加]**をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="812f0-138">In Teams, find the team you just created, click **More options** (...), and then click **Add channel**.</span></span>

2. <span data-ttu-id="812f0-139">チャネルの名前と説明を入力し、[追加] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="812f0-139">Type a name and description for the channel, and then click **Add**.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="812f0-140">手順 2 - リソース アカウントの></span><span class="sxs-lookup"><span data-stu-id="812f0-140">Step 2 - Resource accounts ></span></span>](/microsoftteams/business-voice/create-a-phone-system-call-queue-smb?tabs=resource-account#steps)

# <a name="step-2brresource-accounts"></a>[<span data-ttu-id="812f0-141">手順 2 <br> リソース アカウント</span><span class="sxs-lookup"><span data-stu-id="812f0-141">Step 2<br>Resource accounts</span></span>](#tab/resource-account)

<span data-ttu-id="812f0-142">作成する各呼び出しキューには、リソース アカウントが必要です。</span><span class="sxs-lookup"><span data-stu-id="812f0-142">Each call queue that you create requires a resource account.</span></span> <span data-ttu-id="812f0-143">これはユーザー アカウントに似ていますが、アカウントがユーザーではなく自動応答または通話キューに関連付けられている点が除きます。</span><span class="sxs-lookup"><span data-stu-id="812f0-143">This is similar to a user account, except the account is associated with an auto attendant or call queue instead of a person.</span></span> <span data-ttu-id="812f0-144">この手順では、アカウントを作成し、Microsoft 365 電話システム *- Virtual User* ライセンスを割り当て、それを使用して通話キューの作成を開始します。</span><span class="sxs-lookup"><span data-stu-id="812f0-144">In this step, we'll create the account, assign it a *Microsoft 365 Phone System - Virtual User* license, and then use it to start creating the call queue.</span></span>

### <a name="create-a-resource-account"></a><span data-ttu-id="812f0-145">リソース アカウントを作成する</span><span class="sxs-lookup"><span data-stu-id="812f0-145">Create a resource account</span></span>

<span data-ttu-id="812f0-146">リソース アカウントは、管理センター Teams作成できます。</span><span class="sxs-lookup"><span data-stu-id="812f0-146">You can create a resource account in the Teams admin center.</span></span>

1. <span data-ttu-id="812f0-147">管理センター Teams、[組織全体の設定]**を展開し**、[リソース アカウント]**をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="812f0-147">In the Teams admin center, expand **Org-wide settings**, and then click **Resource accounts**.</span></span>

2. <span data-ttu-id="812f0-148">**[追加]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="812f0-148">Click **Add**.</span></span>

3. <span data-ttu-id="812f0-149">[リソース **アカウントの追加]** ウィンドウで、[表示名] 、[**ユーザー** 名] に入力し、[リソース アカウントの種類] で [キューの呼び **出し] を選択します**。 </span><span class="sxs-lookup"><span data-stu-id="812f0-149">In the **Add resource account** pane, fill out **Display name**, **Username**, and choose **Call queue** for the **Resource account type**.</span></span> <span data-ttu-id="812f0-150">エージェントは、キューから着信呼び出しを受信すると、表示名を表示します。</span><span class="sxs-lookup"><span data-stu-id="812f0-150">Agents will see the display name when they receive an incoming call from the queue.</span></span>

    ![リソース アカウントのユーザー インターフェイスの追加のスクリーンショット](../media/resource-account-add-cq.png)

4. <span data-ttu-id="812f0-152">**[保存]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="812f0-152">Click **Save**.</span></span>

   <span data-ttu-id="812f0-153">新しいアカウントがアカウントの一覧に表示されます。</span><span class="sxs-lookup"><span data-stu-id="812f0-153">The new account will appear in the list of accounts.</span></span>

   ![リソース アカウントの一覧のスクリーンショット](../media/resource-accounts-page.png)

### <a name="assign-a-license"></a><span data-ttu-id="812f0-155">ライセンスを割り当てる</span><span class="sxs-lookup"><span data-stu-id="812f0-155">Assign a license</span></span>

<span data-ttu-id="812f0-156">リソース アカウントに Microsoft 365 電話システム *- 仮想ユーザー ライセンスを* 割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="812f0-156">You must assign a *Microsoft 365 Phone System - Virtual User* license to the resource account.</span></span>

1. <span data-ttu-id="812f0-157">[アクティブMicrosoft 365 管理センターの一覧で、ライセンスを割り当てるリソース アカウントをクリックします。</span><span class="sxs-lookup"><span data-stu-id="812f0-157">In the Microsoft 365 admin center, in the **Active users** list, click the resource account to which you want to assign a license.</span></span>

2. <span data-ttu-id="812f0-158">[ライセンスと **アプリ] タブの**[ライセンス]**で**、[仮想Microsoft 365 電話システム **- 仮想ユーザー] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="812f0-158">On the **Licenses and Apps** tab, under **Licenses**, select **Microsoft 365 Phone System - Virtual User**.</span></span>

3. <span data-ttu-id="812f0-159">[変更の **保存] をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="812f0-159">Click **Save changes**.</span></span>

    ![[ライセンスの割り当て] ユーザー インターフェイスのスクリーンショットMicrosoft 365 管理センター](../media/resource-account-assign-virtual-user-license.png)

### <a name="create-a-call-queue"></a><span data-ttu-id="812f0-161">呼び出しキューを作成する</span><span class="sxs-lookup"><span data-stu-id="812f0-161">Create a call queue</span></span>

<span data-ttu-id="812f0-162">次に、新しい呼び出しキューの作成を開始し、リソース アカウントを割り当てします。</span><span class="sxs-lookup"><span data-stu-id="812f0-162">Next, we'll start creating a new call queue and assign the resource account.</span></span>

1. <span data-ttu-id="812f0-163">管理センター Teams、[音声] を **展開** し **、[キューの** 呼び出し] をクリックし、[追加] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="812f0-163">In the Teams admin center, expand **Voice**, click **Call queues**, and then click **Add**.</span></span>

1. <span data-ttu-id="812f0-164">通話キューの名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="812f0-164">Type a name for the call queue.</span></span>

2. <span data-ttu-id="812f0-165">[**アカウントの追加]** をクリックし、この呼び出しキューで使用するリソースアカウントを検索し、[追加] をクリックして、[追加] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="812f0-165">Click **Add accounts**, search for the resource account that you want to use with this call queue, click **Add**, and then click **Add**.</span></span>

3. <span data-ttu-id="812f0-166">(省略可能)[**通話 ID の割** り当て] で、[追加] をクリックし、自動応答用に作成したリソース アカウントを検索し、[追加] をクリックし、[追加] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="812f0-166">(Optional) Under **Assign calling ID**, click **Add**, search for the resource accounts that you created for your auto attendant, click **Add**, and then click **Add**.</span></span> <span data-ttu-id="812f0-167">これにより、通話エージェントがコールアウトするときに、メイン ラインの発信者番号が提供されます。</span><span class="sxs-lookup"><span data-stu-id="812f0-167">This will give your call agents the caller ID of your main line when they call out.</span></span>

    ![呼び出し元 ID 設定のスクリーンショット](../media/call-queue-assign-calling-id.png)

3. <span data-ttu-id="812f0-169">言語を選択します。</span><span class="sxs-lookup"><span data-stu-id="812f0-169">Choose a language.</span></span> <span data-ttu-id="812f0-170">この言語は、システムで生成された音声プロンプトとボイスメールのトランスクリプション (有効にした場合) に使用されます。</span><span class="sxs-lookup"><span data-stu-id="812f0-170">This language will be used for system-generated voice prompts and voicemail transcription (if you enable them).</span></span>

    ![リソース アカウント設定のスクリーンショット](../media/call-queue-name-language.png)

4. <span data-ttu-id="812f0-172">発信者がキューに到着するときに、発信者にあいさつメッセージを再生する場合に指定します。</span><span class="sxs-lookup"><span data-stu-id="812f0-172">Specify if you want to play a greeting to callers when they arrive in the queue.</span></span> <span data-ttu-id="812f0-173">再生するあいさつメッセージを含む MP3、WAV、または WMA ファイルをアップロードする必要があります。</span><span class="sxs-lookup"><span data-stu-id="812f0-173">You must upload an MP3, WAV, or WMA file containing the greeting that you want to play.</span></span>

5. <span data-ttu-id="812f0-174">Teamsキュー内で保留されている間、呼び出し元に既定の音楽を提供します。</span><span class="sxs-lookup"><span data-stu-id="812f0-174">Teams provides default music to callers while they are on hold in a queue.</span></span> <span data-ttu-id="812f0-175">特定のオーディオ ファイルを再生する場合は、[オーディオ ファイルの再生] を選択し、MP3、WAV、または WMA ファイルをアップロードします。</span><span class="sxs-lookup"><span data-stu-id="812f0-175">If you want to play a specific audio file, choose **Play an audio file** and upload an MP3, WAV, or WMA file.</span></span>

   > [!NOTE]
   > <span data-ttu-id="812f0-176">アップロードされた記録は 5 MB 以下にできます。</span><span class="sxs-lookup"><span data-stu-id="812f0-176">The uploaded recording can be no larger than 5 MB.</span></span>
   > <span data-ttu-id="812f0-177">通話キューで提供される既定Teamsは、組織が支払う使用料金は無料です。</span><span class="sxs-lookup"><span data-stu-id="812f0-177">The default music supplied in Teams call queues is free of any royalties payable by your organization.</span></span> 

> [!div class="nextstepaction"]
> [<span data-ttu-id="812f0-178">手順 3 - エージェントを呼び出></span><span class="sxs-lookup"><span data-stu-id="812f0-178">Step 3 - Call agents ></span></span>](/microsoftteams/business-voice/create-a-phone-system-call-queue-smb?tabs=call-agents#steps)

# <a name="step-3brcall-agents"></a>[<span data-ttu-id="812f0-179">手順 3 エージェント <br> を呼び出す</span><span class="sxs-lookup"><span data-stu-id="812f0-179">Step 3<br>Call agents</span></span>](#tab/call-agents)

<span data-ttu-id="812f0-180">エージェントを呼び出しキューに追加するには、前に作成したチームとチャネルにエージェントを追加します。</span><span class="sxs-lookup"><span data-stu-id="812f0-180">To add agents to the call queue, we'll add them to the team and channel that we created earlier.</span></span> <span data-ttu-id="812f0-181">これを行うには、チームのメンバーである必要があります。</span><span class="sxs-lookup"><span data-stu-id="812f0-181">You need to be a member of the team to do this.</span></span>

1. <span data-ttu-id="812f0-182">[チームの **選択] オプションを選択し** 、[チャネルの **追加] をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="812f0-182">Select the **Choose a team** option and click **Add a channel**.</span></span>
2. <span data-ttu-id="812f0-183">作成したチームの名前を入力して選択し、[追加] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="812f0-183">Type the name of the team that you created, select it, and click **Add**.</span></span>
3. <span data-ttu-id="812f0-184">キュー用に作成したチャネルを選択します。</span><span class="sxs-lookup"><span data-stu-id="812f0-184">Select the channel that you created for the queue.</span></span>
3. <span data-ttu-id="812f0-185">[**適用**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="812f0-185">Click **Apply**.</span></span>

    ![通話キューのユーザーとグループの設定のスクリーンショット](../media/call-queue-users-groups.png)

> [!NOTE]
> <span data-ttu-id="812f0-187">新しいユーザーがチームに追加された場合、最初の呼び出しが到着するには最大 8 時間かかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="812f0-187">When new users are added to the team, it can take up to eight hours for their first call to arrive.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="812f0-188">手順 4 - リソース アカウントの></span><span class="sxs-lookup"><span data-stu-id="812f0-188">Step 4 - Resource accounts ></span></span>](/microsoftteams/business-voice/create-a-phone-system-call-queue-smb?tabs=call-routing#steps)

# <a name="step-4brcall-routing"></a>[<span data-ttu-id="812f0-189">手順 4 通話 <br> ルーティング</span><span class="sxs-lookup"><span data-stu-id="812f0-189">Step 4<br>Call routing</span></span>](#tab/call-routing)

<span data-ttu-id="812f0-190">使用する呼び出しルーティング方法を選択します。</span><span class="sxs-lookup"><span data-stu-id="812f0-190">Choose the call routing method that you want to use.</span></span>

1. <span data-ttu-id="812f0-191">[会議 **モード] を [** 自動] に **設定します**。</span><span class="sxs-lookup"><span data-stu-id="812f0-191">Set **Conference mode** to **Auto**.</span></span>

2. <span data-ttu-id="812f0-192">使用する **ルーティング方法** を選択します。</span><span class="sxs-lookup"><span data-stu-id="812f0-192">Choose the **Routing method** you want to use.</span></span> <span data-ttu-id="812f0-193">これにより、エージェントがキューから呼び出しを受信する順序が決定されます。</span><span class="sxs-lookup"><span data-stu-id="812f0-193">This determines the order in which agents receive calls from the queue.</span></span> <span data-ttu-id="812f0-194">シリアル ルーティングまたは **ラウンド ロビン をお\*\*\*\*勧めします**。</span><span class="sxs-lookup"><span data-stu-id="812f0-194">We recommend **Serial routing** or  **Round robin**.</span></span> <span data-ttu-id="812f0-195">次のオプションから選択します。</span><span class="sxs-lookup"><span data-stu-id="812f0-195">Choose from these options:</span></span>

    - <span data-ttu-id="812f0-196">**アテンダント** ルーティングでは、キュー内のすべてのエージェントが同時に呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="812f0-196">**Attendant routing** rings all agents in the queue at the same time.</span></span> <span data-ttu-id="812f0-197">呼び出しを受け取る最初の呼び出しエージェントが呼び出しを取得します。</span><span class="sxs-lookup"><span data-stu-id="812f0-197">The first call agent to pick up the call gets the call.</span></span>

    - <span data-ttu-id="812f0-198">**シリアル ルーティングでは、** すべての呼び出しエージェントが 1 つ 1 つリングされます。</span><span class="sxs-lookup"><span data-stu-id="812f0-198">**Serial routing** rings all call agents one by one.</span></span> <span data-ttu-id="812f0-199">エージェントが通話を閉じ、または呼び出しを受け取らない場合、呼び出しは次のエージェントを呼び出し、エージェントが取り出されるか、または時間が切れるまですべてのエージェントを試します。</span><span class="sxs-lookup"><span data-stu-id="812f0-199">If an agent dismisses or does not pick up a call, the call will ring the next agent and will try all agents until it is picked up or times out.</span></span>

    - <span data-ttu-id="812f0-200">**ラウンド ロビンは** 、着信呼び出しのルーティングのバランスを取り、各呼び出しエージェントがキューから同じ数の呼び出しを取得します。</span><span class="sxs-lookup"><span data-stu-id="812f0-200">**Round robin** balances the routing of incoming calls so that each call agent gets the same number of calls from the queue.</span></span> <span data-ttu-id="812f0-201">これは、すべての通話エージェント間で均等な機会を確保するために、受信販売環境で望ましい場合があります。</span><span class="sxs-lookup"><span data-stu-id="812f0-201">This may be desirable in an inbound sales environment to assure equal opportunity among all the call agents.</span></span>

    - <span data-ttu-id="812f0-202">**アイドル時間が** 最も長いエージェントに各呼び出しをルーティングします。</span><span class="sxs-lookup"><span data-stu-id="812f0-202">**Longest idle** routes each call to the agent who has been idle the longest time.</span></span> <span data-ttu-id="812f0-203">(プレゼンス状態が 10 分以上離れたエージェントは含まれません)。</span><span class="sxs-lookup"><span data-stu-id="812f0-203">(Agents whose presence state has been Away for more than 10 minutes are not included.)</span></span>

    ![電話会議モードとルーティング方法の設定のスクリーンショット](../media/call-queue-conference-mode-routing-method.png)

3. <span data-ttu-id="812f0-205">プレゼンス **ベースのルーティングを有効** にする。</span><span class="sxs-lookup"><span data-stu-id="812f0-205">Turn **Presence-based routing** on.</span></span> <span data-ttu-id="812f0-206">これにより、プレゼンス状態が [使用可能] のエージェントに呼び出しが **ルーティングされます**。</span><span class="sxs-lookup"><span data-stu-id="812f0-206">This routes calls to agents whose presence status is **Available**.</span></span>

4. <span data-ttu-id="812f0-207">エージェントが呼び出しからオプトアウトすることを許可する場合に選択します。</span><span class="sxs-lookup"><span data-stu-id="812f0-207">Choose if you want to allow agents to opt out of calls.</span></span>

5. <span data-ttu-id="812f0-208">エージェントの **アラート時間を設定** して、キューが呼び出しを次のエージェントにリダイレクトする前にエージェントの電話が鳴る時間を指定します。</span><span class="sxs-lookup"><span data-stu-id="812f0-208">Set an **Agent alert time** to specify how long an agent's phone will ring before the queue redirects the call to the next agent.</span></span>

    ![ルーティング、オプトアウト、アラート時間の設定のスクリーンショット](../media/call-queue-presence-agents-time.png)

> [!div class="nextstepaction"]
> [<span data-ttu-id="812f0-210">手順 5 - 呼び出しオーバーフロー></span><span class="sxs-lookup"><span data-stu-id="812f0-210">Step 5 - Call overflow ></span></span>](/microsoftteams/business-voice/create-a-phone-system-call-queue-smb?tabs=call-overflow#steps)

# <a name="step-5brcall-overflow"></a>[<span data-ttu-id="812f0-211">手順 5. <br> 呼び出しオーバーフロー</span><span class="sxs-lookup"><span data-stu-id="812f0-211">Step 5<br>Call overflow</span></span>](#tab/call-overflow)

<span data-ttu-id="812f0-212">キューの最大数を超える呼び出しを処理する方法を選択します。</span><span class="sxs-lookup"><span data-stu-id="812f0-212">Choose how you want to handle calls that exceed the maximum in the queue.</span></span>

1. <span data-ttu-id="812f0-213">キュー内 **の最大呼び出し数を設定します**。</span><span class="sxs-lookup"><span data-stu-id="812f0-213">Set the **Maximum calls in the queue**.</span></span>

2. <span data-ttu-id="812f0-214">呼び出しの最大数に達した場合に実行する操作を選択します。</span><span class="sxs-lookup"><span data-stu-id="812f0-214">Choose what you want to do when the maximum number of calls is reached.</span></span> <span data-ttu-id="812f0-215">通話を切断するか、リダイレクトできます。</span><span class="sxs-lookup"><span data-stu-id="812f0-215">You can disconnect the call or redirect it.</span></span> <span data-ttu-id="812f0-216">次のいずれかの宛先に呼び出しをリダイレクトすることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="812f0-216">We recommend that you redirect the call to one of the following destinations:</span></span>
    - <span data-ttu-id="812f0-217">**組織内のユーザー** - 音声通話を受信できる組織内のユーザー</span><span class="sxs-lookup"><span data-stu-id="812f0-217">**Person in the organization** - a person in your organization who is able to receive voice calls</span></span>
    - <span data-ttu-id="812f0-218">**音声アプリ** - 自動応答または別の通話キュー。</span><span class="sxs-lookup"><span data-stu-id="812f0-218">**Voice app** - an auto attendant or another call queue.</span></span> <span data-ttu-id="812f0-219">(この宛先を選択するときに、自動応答または通話キューに関連付けられているリソース アカウントを選択します)。</span><span class="sxs-lookup"><span data-stu-id="812f0-219">(Choose the resource account associated with the auto attendant or call queue when choosing this destination.)</span></span>
    - <span data-ttu-id="812f0-220">**外部電話番号** - 任意の電話番号。</span><span class="sxs-lookup"><span data-stu-id="812f0-220">**External phone number** - any phone number.</span></span> <span data-ttu-id="812f0-221">+[国コード][地域コード][電話番号] の形式を使用します。</span><span class="sxs-lookup"><span data-stu-id="812f0-221">Use this format: +[country code][area code][phone number]</span></span>
    - <span data-ttu-id="812f0-222">**ボイス** メール - 作成したチームのボイス メールボックスを使用できます。</span><span class="sxs-lookup"><span data-stu-id="812f0-222">**Voicemail** - you can use the voice mailbox of the team that you created.</span></span>

    ![呼び出しオーバーフロー設定のスクリーンショット](../media/call-queue-overflow-handling.png)

> [!div class="nextstepaction"]
> [<span data-ttu-id="812f0-224">手順 6 - 呼び出しタイムアウト></span><span class="sxs-lookup"><span data-stu-id="812f0-224">Step 6 - Call timeout ></span></span>](/microsoftteams/business-voice/create-a-phone-system-call-queue-smb?tabs=call-timeout#steps)

# <a name="step-6brcall-timeout"></a>[<span data-ttu-id="812f0-225">手順 6 通話 <br> タイムアウト</span><span class="sxs-lookup"><span data-stu-id="812f0-225">Step 6<br>Call timeout</span></span>](#tab/call-timeout)

<span data-ttu-id="812f0-226">呼び出しがキュー内で待ち時間が長すぎるときに実行する処理を選択します。</span><span class="sxs-lookup"><span data-stu-id="812f0-226">Choose what you want to happen when calls have been waiting in the queue for too long.</span></span>

1. <span data-ttu-id="812f0-227">[最大 **待機時間] を設定します**。</span><span class="sxs-lookup"><span data-stu-id="812f0-227">Set the **Maximum wait time**.</span></span>

2. <span data-ttu-id="812f0-228">通話がアウトした場合に実行する操作を選択します。通話を切断するか、リダイレクトできます。</span><span class="sxs-lookup"><span data-stu-id="812f0-228">Choose what you want to do when a call times out. You can disconnect the call or redirect it.</span></span> <span data-ttu-id="812f0-229">次のいずれかの宛先に呼び出しをリダイレクトすることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="812f0-229">We recommend that you redirect the call to one of the following destinations:</span></span>
    - <span data-ttu-id="812f0-230">**組織内のユーザー** - 音声通話を受信できる組織内のユーザー</span><span class="sxs-lookup"><span data-stu-id="812f0-230">**Person in the organization** - a person in your organization who is able to receive voice calls</span></span>
    - <span data-ttu-id="812f0-231">**音声アプリ** - 自動応答または別の通話キュー。</span><span class="sxs-lookup"><span data-stu-id="812f0-231">**Voice app** - an auto attendant or another call queue.</span></span> <span data-ttu-id="812f0-232">(この宛先を選択するときに、自動応答または通話キューに関連付けられているリソース アカウントを選択します)。</span><span class="sxs-lookup"><span data-stu-id="812f0-232">(Choose the resource account associated with the auto attendant or call queue when choosing this destination.)</span></span>
    - <span data-ttu-id="812f0-233">**外部電話番号** - 任意の電話番号。</span><span class="sxs-lookup"><span data-stu-id="812f0-233">**External phone number** - any phone number.</span></span> <span data-ttu-id="812f0-234">+[国コード][地域コード][電話番号] の形式を使用します。</span><span class="sxs-lookup"><span data-stu-id="812f0-234">Use this format: +[country code][area code][phone number]</span></span>
    - <span data-ttu-id="812f0-235">**ボイス** メール - 作成したチームのボイス メールボックスを使用できます。</span><span class="sxs-lookup"><span data-stu-id="812f0-235">**Voicemail** - you can use the voice mailbox of the team that you created.</span></span>

    ![通話タイムアウト設定のスクリーンショット](../media/call-queue-timeout-handling.png)

3. <span data-ttu-id="812f0-237">**[保存]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="812f0-237">Click **Save**.</span></span>

<span data-ttu-id="812f0-238">これで、通話キューのセットアップが完了します。</span><span class="sxs-lookup"><span data-stu-id="812f0-238">This completes the setup of your call queue.</span></span> <span data-ttu-id="812f0-239">次に、自動応答 [を設定できます](create-a-phone-system-auto-attendant-smb.md)。</span><span class="sxs-lookup"><span data-stu-id="812f0-239">Next, you may want to [set up an auto attendant](create-a-phone-system-auto-attendant-smb.md).</span></span>

---

