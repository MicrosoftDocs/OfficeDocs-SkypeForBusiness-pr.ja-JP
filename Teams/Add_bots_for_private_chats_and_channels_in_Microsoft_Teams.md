---
title: "Microsoft Teams でプライベートのチャットやチャネルのボットを追加する | Microsoft サポート"
author: LolaJacobsen
ms.author: lolaj
manager: serdar
ms.date: 08/10/2017
ms.topic: tutorial
ms.prod: teams
description: "プライベート チャットとチャネル用に Microsoft Teams にボットを追加する方法、カスタム ボットを作成する方法、プライベート チャット用に独自のボットをサイド ロードする方法について紹介します。"
ms.openlocfilehash: a93e2b27c350de043fe1d1af553a3d2d727db0fd
ms.sourcegitcommit: 3b9b3f07f4f67cd5f43da68f48d62222d7e49167
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/31/2017
---
<a name="add-bots-for-private-chats-and-channels-in-microsoft-teams"></a><span data-ttu-id="1aaff-103">Microsoft Teams でプライベートのチャットやチャネルのボットを追加する</span><span class="sxs-lookup"><span data-stu-id="1aaff-103">Add bots for private chats and channels in Microsoft Teams</span></span>
==========================================================

<span data-ttu-id="1aaff-p101">ボットは、問い合わせに応答したり、興味のある情報や最新情報に関する更新および通知を提供する自動化されたプログラムです。ボットによって、ユーザーは、Microsoft Teams のチャット会話を介して、タスク管理、スケジューリング、ポーリングなどのクラウド サービスと相互にやり取りできます。Microsoft Teams のボットは [Microsoft Bot Framework](https://go.microsoft.com/fwlink/?linkid=854370) に基づいており、このフレームワークにより作成されたボットは Microsoft Teams で容易に有効にできます。</span><span class="sxs-lookup"><span data-stu-id="1aaff-p101">Bots are automated programs that are set up to respond to queries or give updates and notifications about details users find interesting or want to stay informed about. Bots allow users to interact with cloud services like task management, scheduling, and polling, through chat conversations in Microsoft Teams. Bots for Microsoft Teams are built on the [Microsoft Bot Framework](https://go.microsoft.com/fwlink/?linkid=854370) and the bots that are developed using this framework can be enabled easily for Microsoft Teams.</span></span>

<span data-ttu-id="1aaff-p102">現在、Microsoft Teams は、チーム内のプライベート チャットとチャネルにおけるボットをサポートしています。管理者は、Office 365 テナント内でのボットの使用可否を管理できます。<span id="_T-Bot" class="anchor"></span></span><span class="sxs-lookup"><span data-stu-id="1aaff-p102">Currently, Microsoft Teams support bots in private chats and channels within a team. Administrators can control whether the use of bots is allowed or prohibited within the Office 365 tenant.<span id="_T-Bot" class="anchor"></span></span></span>

<span data-ttu-id="1aaff-p103">コミュニティにより作成されて利用可能となったボットは、Microsoft Teams 内で利用できます。カスタム ボットを機能させるには、ボットの機能とサイド ローディングをテナント レベルで有効にする必要があります。ボットはプライベート チャットまたはチャネルにおいて使用できます。チャネルの場合、チーム所有者またはメンバーがボットを追加できます。</span><span class="sxs-lookup"><span data-stu-id="1aaff-p103">Bots developed by the community and are made available, can be leveraged within Microsoft Teams. The bot’s functionality and bot’s side loading must be enabled on the tenant level for custom bots to be functional. Bots can be used in private chats or in channels. For channels, team owners or members can add bots.</span></span>

<a name="add-bots-for-private-chat-and-channels"></a><span data-ttu-id="1aaff-113">プライベート チャットとチャネル用ボットの追加</span><span class="sxs-lookup"><span data-stu-id="1aaff-113">Add bots for Private Chat and channels</span></span>
--------------------------------------

<span data-ttu-id="1aaff-114">プライベート チャットとチャネル用のボットを統合する場合、次に示す 2 つの方法があります。</span><span class="sxs-lookup"><span data-stu-id="1aaff-114">There are two ways to integrate a bot for private chats and channels:</span></span>

1.  <span data-ttu-id="1aaff-p104">公開されている**プライベート チャット**または**チャネル**用のボットをインストールする。(これが第 1 のオプションとなります。)</span><span class="sxs-lookup"><span data-stu-id="1aaff-p104">Install publicly available bots for **private chat** or **channels**. (This is the first option.)</span></span>

2.  <span data-ttu-id="1aaff-117">または、ボットを検索するには、[**チャット**] に移動して、[**連絡先**] を検索して、[**アプリを検出**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="1aaff-117">Alternatively, to find bots, navigate to **Chat**, search for a **contact,** and click **Discover apps.**</span></span>

![](media/Add_bots_for_private_chats_and_channels_in_Microsoft_Teams_image1.png)

3.  <span data-ttu-id="1aaff-118">以下に示すとおり、会話をしたい**ボット**を選択します。</span><span class="sxs-lookup"><span data-stu-id="1aaff-118">Select which **Bot** you want to have a conversation with, as shown below.</span></span>

![](media/Add_bots_for_private_chats_and_channels_in_Microsoft_Teams_image2.png)

4.  <span data-ttu-id="1aaff-119">選択したら、ボットに**権限**を与え、**ボットをプライベート チャットで**使用したいかどうかを選択するか、ボットを使用する**チーム**を選択します。</span><span class="sxs-lookup"><span data-stu-id="1aaff-119">Once selected, provide the bot **permissions,** and select whether you want to use **bots in a private chat** or select a **Team** to use it in.</span></span>

![](media/Add_bots_for_private_chats_and_channels_in_Microsoft_Teams_image3.png)

5.  <span data-ttu-id="1aaff-p105">ボットをチームのチャネル内で使用する場合は、[**View Team and Bots (チームとボットを表示)**] をクリックするだけです。このようにすることで、その他のボットを見つけることができます。</span><span class="sxs-lookup"><span data-stu-id="1aaff-p105">Alternatively, to use a bot within a channel of a team, simply click **View Team and Bots**. Here you can Discover additional bots.</span></span>

6.  <span data-ttu-id="1aaff-p106">ボットはいつでもチームから削除できます。この場合は、[**View Team and Bots (チームとボットを表示)**] をクリックして、すべてのボットを表示してから、目的のボットを [**削除**] します。</span><span class="sxs-lookup"><span data-stu-id="1aaff-p106">At any time, a bot can be removed from the team. Simply click **View Team and Bots,** to see all bots and then **remove** the one you’d like.</span></span>

![](media/Add_bots_for_private_chats_and_channels_in_Microsoft_Teams_image4.png)

<a name="create-custom-bots-for-microsoft-teams"></a><span data-ttu-id="1aaff-124">Microsoft Teams のカスタム ボットの作成</span><span class="sxs-lookup"><span data-stu-id="1aaff-124">Create custom bots for Microsoft Teams</span></span>
--------------------------------------

<span data-ttu-id="1aaff-p107">Microsoft ボット フレームワークを使用して、LOB アプリケーションに統合されるボットを簡単に作成できます。独自のボットを作成および公開する方法については、[Creating and Testing a bot for Microsoft Teams](https://go.microsoft.com/fwlink/?linkid=854371) のガイダンスを参照してください。</span><span class="sxs-lookup"><span data-stu-id="1aaff-p107">You can easily create a bot that integrates in to your LOB applications, using the Microsoft Bot Framework. Please refer to [Creating and Testing a bot for Microsoft Teams](https://go.microsoft.com/fwlink/?linkid=854371) guidance to learn how you can develop and publish your own bots.</span></span>

<span data-ttu-id="1aaff-p108">ボットを作成してボットのフレームワークに登録すると、それを公開するかどうかを選択することができます。公開しない場合、ボットはプライベートのままになります。ボットを使う前にログインするようユーザーに要求することもできます。ログインを要求することで、ボットのアプリケーション ID が既知のものになった場合でも組織の従業員のみがそのボットにアクセスできるようにできます。ボットを使った Active Directory でユーザー認証を実行する方法のコード例については、GitHub の「[*AuthBot*](https://go.microsoft.com/fwlink/?linkid=854372)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="1aaff-p108">When you create a bot and register it with the Bot Framework, you can choose to publish it or not. If you don't publish it, the bot remains private. You can also require your users to log in before using the bot. Requiring login makes sure only employees of your organization can access the bot, even if the bot's application ID becomes known. See [*AuthBot*](https://go.microsoft.com/fwlink/?linkid=854372) on GitHub for a code example of how to authenticate users against your Active Directory using bots.</span></span>

<span data-ttu-id="1aaff-132">ボットはチームへの展開前に [Bot Framework Emulator](https://go.microsoft.com/fwlink/?linkid=854373) を使用してテストできます。</span><span class="sxs-lookup"><span data-stu-id="1aaff-132">Bots can be tested using the [Bot Framework Emulator](https://go.microsoft.com/fwlink/?linkid=854373) before they are deployed into your Teams.</span></span>

<a name="side-load-your-own-bot-for-private-chat"></a><span data-ttu-id="1aaff-133">プライベート チャット用の独自のボットのサイド ロード</span><span class="sxs-lookup"><span data-stu-id="1aaff-133">Side load your own bot for private chat</span></span>
---------------------------------------

1.  <span data-ttu-id="1aaff-134">ボットを作成したら、作成したボットの [**Bot Dashboard (ボットのダッシュボード)**] [ページ](https://go.microsoft.com/fwlink/?linkid=854374)に移動して、[**詳細**] で [**Microsoft App ID (Microsoft アプリ ID)**] をコピーします。</span><span class="sxs-lookup"><span data-stu-id="1aaff-134">Once you have created your Bot, navigate to the **Bot Dashboard** [page](https://go.microsoft.com/fwlink/?linkid=854374) for the bot you developed, and under **Details**, copy the **Microsoft App ID**.</span></span>

![](media/Add_bots_for_private_chats_and_channels_in_Microsoft_Teams_image5.png)

2.  <span data-ttu-id="1aaff-p109">Microsoft Teams の [**チャット**] ウィンドウで [**Add chat icon (チャット アイコンの追加)**] を選択します。[**To: (相手)**] にはボットの [**Microsoft App ID (Microsoft アプリ ID)**] を貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="1aaff-p109">From within Microsoft Teams, on the **Chat** pane, select the **Add chat icon**. For **To:,** paste your bot's **Microsoft app ID**.</span></span>

![](media/Add_bots_for_private_chats_and_channels_in_Microsoft_Teams_image6.png)

3.  <span data-ttu-id="1aaff-137">アプリ ID は [**ボット名**] になります。この手順の実行後にボットとのチャット会話を開始できます。</span><span class="sxs-lookup"><span data-stu-id="1aaff-137">The app ID will resolve to your **bot name,** and then you can initiate a chat conversation with that bot.</span></span>
