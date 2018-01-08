---
title: "Microsoft Teams でプライベートのチャットやチャネルのボットを追加する"
author: LolaJacobsen
ms.author: lolaj
manager: lolaj
ms.date: 09/25/2017
ms.topic: article
ms.service: msteams
description: "プライベート チャットとチャネル用に Microsoft Teams にボットを追加する方法、カスタム ボットを作成する方法、プライベート チャット用に独自のボットをサイド ロードする方法について紹介します。"
ms.openlocfilehash: c7f2aec398728f310fab780e96d4df09e4b7f582
ms.sourcegitcommit: 3faedb6057da8650b06b05f9c9bdd941d5ade175
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/20/2017
---
<a name="add-bots-for-private-chats-and-channels-in-microsoft-teams"></a><span data-ttu-id="8354a-103">Microsoft Teams でプライベートのチャットやチャネルのボットを追加する</span><span class="sxs-lookup"><span data-stu-id="8354a-103">Add bots for private chats and channels in Microsoft Teams</span></span>
==========================================================

<span data-ttu-id="8354a-p101">ボットは、問い合わせに応答したり、興味のある情報や最新情報に関する更新および通知を提供する自動化されたプログラムです。ボットによって、ユーザーは、Microsoft Teams のチャット会話を介して、タスク管理、スケジューリング、ポーリングなどのクラウド サービスと相互にやり取りできます。Microsoft Teams のボットは [Microsoft Bot Framework](https://go.microsoft.com/fwlink/?linkid=854370) に基づいており、このフレームワークにより作成されたボットは Microsoft Teams で容易に有効にできます。詳細については「[Office 365 を使用する組織で Microsoft Teams の機能を有効にする](enable-features-office-365.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="8354a-p101">Bots are automated programs that are set up to respond to queries or give updates and notifications about details users find interesting or want to stay informed about. Bots allow users to interact with cloud services like task management, scheduling, and polling, through chat conversations in Microsoft Teams. Bots for Microsoft Teams are built on the [Microsoft Bot Framework](https://go.microsoft.com/fwlink/?linkid=854370) and the bots that are developed using this framework can be enabled easily for Microsoft Teams.</span></span>

<span data-ttu-id="8354a-p102">現在、Microsoft Teams は、チーム内のプライベート チャットとチャネルにおけるボットをサポートしています。管理者は、Office 365 テナント内でのボットの使用可否を管理できます。<span id="_T-Bot" class="anchor"></span></span><span class="sxs-lookup"><span data-stu-id="8354a-p102">Currently, Microsoft Teams support bots in private chats and channels within a team. Administrators can control whether the use of bots is allowed or prohibited within the Office 365 tenant.<span id="_T-Bot" class="anchor"></span></span></span>

<span data-ttu-id="8354a-111">コミュニティにより開発されたボットは、Microsoft Teams 内で利用できます。</span><span class="sxs-lookup"><span data-stu-id="8354a-111">Bots developed by the community can be leveraged within Microsoft Teams.</span></span> <span data-ttu-id="8354a-112">ボットを機能させるには、ボットの機能とサイド ローディングをテナント レベルで有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="8354a-112">The bot’s functionality and bot’s side loading must be enabled on the tenant level for custom bots to be functional.</span></span> <span data-ttu-id="8354a-113">ボットはプライベート チャットまたはチャネルにおいて使用できます。</span><span class="sxs-lookup"><span data-stu-id="8354a-113">Bots can be used in private chats or in channels.</span></span> <span data-ttu-id="8354a-114">チャネルの場合、チーム所有者またはメンバーがボットを追加できます。</span><span class="sxs-lookup"><span data-stu-id="8354a-114">For channels, team owners or members can add bots.</span></span>

<span data-ttu-id="8354a-115">詳細については、[アプリとサービス](https://support.office.com/en-us/article/Apps-and-services-cc1fba57-9900-4634-8306-2360a40c665b)の「ボットの使用」セクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="8354a-115">For more information, see the section "Using bots" in [Apps and services](https://support.office.com/en-us/article/Apps-and-services-cc1fba57-9900-4634-8306-2360a40c665b).</span></span> 








 

<a name="create-custom-bots-for-microsoft-teams"></a><span data-ttu-id="8354a-116">Microsoft Teams のカスタム ボットの作成</span><span class="sxs-lookup"><span data-stu-id="8354a-116">Create custom bots for Microsoft Teams</span></span>
--------------------------------------

<span data-ttu-id="8354a-p104">Microsoft ボット フレームワークを使用して、LOB アプリケーションに統合されるボットを簡単に作成できます。独自のボットを作成および公開する方法については、[Creating and Testing a bot for Microsoft Teams](https://go.microsoft.com/fwlink/?linkid=854371) のガイダンスを参照してください。</span><span class="sxs-lookup"><span data-stu-id="8354a-p104">You can easily create a bot that integrates in to your LOB applications, using the Microsoft Bot Framework. Please refer to [Creating and Testing a bot for Microsoft Teams](https://go.microsoft.com/fwlink/?linkid=854371) guidance to learn how you can develop and publish your own bots.</span></span>

<span data-ttu-id="8354a-119">ボットを作成してボットのフレームワークに登録すると、それを公開することを選択できます。</span><span class="sxs-lookup"><span data-stu-id="8354a-119">When you create a bot and register it with the Bot Framework, you can choose to publish it.</span></span> <span data-ttu-id="8354a-120">公開しない場合、ボットはプライベートのままになります。</span><span class="sxs-lookup"><span data-stu-id="8354a-120">If you don't publish it, the bot remains private.</span></span> <span data-ttu-id="8354a-121">ボットを使う前にログインするようユーザーに要求することもできます。</span><span class="sxs-lookup"><span data-stu-id="8354a-121">You can also require your users to log in before using the bot.</span></span> <span data-ttu-id="8354a-122">ログインを要求することで、ボットのアプリケーション ID が既知のものになった場合でも組織の従業員のみがそのボットにアクセスできるようにできます。</span><span class="sxs-lookup"><span data-stu-id="8354a-122">Requiring login makes sure only employees of your organization can access the bot, even if the bot's application ID becomes known.</span></span> <span data-ttu-id="8354a-123">ボットを使った Active Directory でユーザー認証を実行する方法のコード例については、GitHub の[*AuthBot*](https://go.microsoft.com/fwlink/?linkid=854372) をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="8354a-123">See [*AuthBot*](https://go.microsoft.com/fwlink/?linkid=854372) on GitHub for a code example of how to authenticate users against your Active Directory using bots.</span></span>

<span data-ttu-id="8354a-124">ボットはチームへの展開前に [Bot Framework Emulator](https://go.microsoft.com/fwlink/?linkid=854373) を使用してテストできます。</span><span class="sxs-lookup"><span data-stu-id="8354a-124">Bots can be tested using the [Bot Framework Emulator](https://go.microsoft.com/fwlink/?linkid=854373) before they are deployed into your Teams.</span></span>

<a name="side-load-your-own-bot-for-private-chat"></a><span data-ttu-id="8354a-125">プライベート チャット用の独自のボットのサイド ロード</span><span class="sxs-lookup"><span data-stu-id="8354a-125">Side load your own bot for private chat</span></span>
---------------------------------------

1.  <span data-ttu-id="8354a-126">ボットを作成した後、開発したボットの [**Bot Dashboard (ボットのダッシュボード)**] [ページ](https://go.microsoft.com/fwlink/?linkid=854374)に移動して、[**詳細**] で [**Microsoft App ID (Microsoft アプリ ID)**] をコピーします。![[Microsoft App ID (Microsoft アプリ ID)] が強調表示された状態のボットの詳細ページのスクリーンショット。](media/Add_bots_for_private_chats_and_channels_in_Microsoft_Teams_image5.png)</span><span class="sxs-lookup"><span data-stu-id="8354a-126">After you have created your bot, go to the **Bot Dashboard** [page](https://go.microsoft.com/fwlink/?linkid=854374) for the bot you developed, and then under **Details**, copy the **Microsoft App ID**.![Screenshot of details page for a bot with the Microsoft App ID highlighted.](media/Add_bots_for_private_chats_and_channels_in_Microsoft_Teams_image5.png)</span></span> 



2.  <span data-ttu-id="8354a-127">Microsoft Teams の [**チャット**] ウィンドウで [**Add chat icon (チャット アイコンの追加)**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="8354a-127">From within Microsoft Teams, on the **Chat** pane, select the **Add chat icon**. For To:, paste your bot's Microsoft app ID.</span></span> <span data-ttu-id="8354a-128">[**To: (相手)**] にはボットの [**Microsoft App ID (Microsoft アプリ ID)**] を貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="8354a-128">For **To**, paste your bot's **Microsoft app ID**.</span></span> <span data-ttu-id="8354a-129">![チャットを追加するアイコンと、[Microsoft App ID (Microsoft アプリ ID)] が強調表示された [To (相手)] 行が含まれているチャット ウィンドウのスクリーンショット。](media/Add_bots_for_private_chats_and_channels_in_Microsoft_Teams_image6.png)</span><span class="sxs-lookup"><span data-stu-id="8354a-129">![Screenshot of a chat pane with the icon for Add chat and the To line with the Microsoft app ID highlighted.](media/Add_bots_for_private_chats_and_channels_in_Microsoft_Teams_image6.png)</span></span>



3.  <span data-ttu-id="8354a-130">アプリ ID は [**ボット名**] になります。この手順の実行後にボットとのチャット会話を開始できます。</span><span class="sxs-lookup"><span data-stu-id="8354a-130">The app ID will resolve to your **bot name,** and then you can initiate a chat conversation with that bot.</span></span>
