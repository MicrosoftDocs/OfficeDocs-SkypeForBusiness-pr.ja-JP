---
title: Microsoft Teams でプライベートのチャットやチャネルのボットを追加する
author: LolaJacobsen, DamienDoumer
ms.author: lolaj, Damien
manager: serdars
ms.date: 12/05/2018
ms.topic: article
ms.service: msteams
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
search.appverid: MET150
ms.reviewer: lucarras
description: プライベート チャットとチャネル用に Microsoft Teams にボットを追加する方法、カスタム ボットを作成する方法、プライベート チャット用に独自のボットをサイド ロードする方法について紹介します。
appliesto:
- Microsoft Teams
ms.openlocfilehash: 6987c14973443e62f0be69f9872c4e248ddb026b
ms.sourcegitcommit: b5949233f8080a6cf0edb4b5e27272214feb1c22
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/29/2019
ms.locfileid: "34548846"
---
<a name="add-bots-for-private-chats-and-channels-in-microsoft-teams"></a><span data-ttu-id="3e0a0-103">Microsoft Teams でプライベートのチャットやチャネルのボットを追加する</span><span class="sxs-lookup"><span data-stu-id="3e0a0-103">Add bots for private chats and channels in Microsoft Teams</span></span>
==========================================================
> [!IMPORTANT]
> [!INCLUDE [new-teams-sfb-admin-center-notice](includes/new-teams-sfb-admin-center-notice.md)]

<span data-ttu-id="3e0a0-104">ボットとは、クエリに応答したり、ユーザーが興味を持っている詳細や常に情報を得ていたい詳細について更新や通知を行う自動プログラムのことです。</span><span class="sxs-lookup"><span data-stu-id="3e0a0-104">Bots are automated programs that respond to queries or give updates and notifications about details users find interesting or want to stay informed about.</span></span> <span data-ttu-id="3e0a0-105">ボットは、ユーザーが Microsoft Teams でのチャットの会話を通じて、タスク管理、スケジュール、ポーリングなどのクラウドサービスを操作できるようにします。</span><span class="sxs-lookup"><span data-stu-id="3e0a0-105">Bots allow users to interact with cloud services like task management, scheduling, and polling, through chat conversations in Microsoft Teams.</span></span> <span data-ttu-id="3e0a0-106">Microsoft Teams のボットは、 [Microsoft ボットフレームワーク](https://go.microsoft.com/fwlink/?linkid=854370)上に構築されています。</span><span class="sxs-lookup"><span data-stu-id="3e0a0-106">Bots for Microsoft Teams are built on the [Microsoft Bot Framework](https://go.microsoft.com/fwlink/?linkid=854370).</span></span> <span data-ttu-id="3e0a0-107">このフレームワークを使用して開発されたボットは、Microsoft Teams で簡単に有効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="3e0a0-107">The bots that are developed using this framework can be enabled easily for Microsoft Teams.</span></span> <span data-ttu-id="3e0a0-108">詳細については、[組織のMicrosoft Teams 設定の管理](enable-features-office-365.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3e0a0-108">For more information, see [Manage Microsoft Teams settings for your organization](enable-features-office-365.md).</span></span>

<span data-ttu-id="3e0a0-p102">現在、Microsoft Teams は、チーム内のプライベート チャットとチャネルにおけるボットをサポートしています。管理者は、Office 365 テナント内でのボットの使用可否を管理できます。<span id="_T-Bot" class="anchor"></span></span><span class="sxs-lookup"><span data-stu-id="3e0a0-p102">Currently, Microsoft Teams support bots in private chats and channels within a team. Administrators can control whether the use of bots is allowed or prohibited within the Office 365 tenant.<span id="_T-Bot" class="anchor"></span></span></span>

<span data-ttu-id="3e0a0-111">コミュニティにより開発されたボットは、Microsoft Teams 内で利用できます。</span><span class="sxs-lookup"><span data-stu-id="3e0a0-111">Bots developed by the community can be leveraged within Microsoft Teams.</span></span> <span data-ttu-id="3e0a0-112">ボットを機能させるには、ボットの機能とサイド ローディングをテナント レベルで有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="3e0a0-112">The bot’s functionality and bot’s side loading must be enabled on the tenant level for custom bots to be functional.</span></span> <span data-ttu-id="3e0a0-113">ボットはプライベート チャットまたはチャネルにおいて使用できます。</span><span class="sxs-lookup"><span data-stu-id="3e0a0-113">Bots can be used in private chats or in channels.</span></span> <span data-ttu-id="3e0a0-114">チャネルの場合、チーム所有者またはメンバーがボットを追加できます。</span><span class="sxs-lookup"><span data-stu-id="3e0a0-114">For channels, team owners or members can add bots.</span></span>

<span data-ttu-id="3e0a0-115">詳細については、[アプリとサービス](https://support.office.com/article/Apps-and-services-cc1fba57-9900-4634-8306-2360a40c665b)の「ボットの使用」セクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="3e0a0-115">For more information, see the section "Using bots" in [Apps and services](https://support.office.com/article/Apps-and-services-cc1fba57-9900-4634-8306-2360a40c665b).</span></span> 

> [!IMPORTANT]
> <span data-ttu-id="3e0a0-116">テスト以外の理由で、[GUID] にボットを追加することはお勧めしません。</span><span class="sxs-lookup"><span data-stu-id="3e0a0-116">Adding a bot by GUID, for anything other than testing purposes, is not recommended.</span></span> <span data-ttu-id="3e0a0-117">これにより、ボットの機能が大幅に制限されます。</span><span class="sxs-lookup"><span data-stu-id="3e0a0-117">Doing so severely limits the functionality of a bot.</span></span> <span data-ttu-id="3e0a0-118">製品使用中のボットは、アプリの一部として Teams に追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3e0a0-118">Bots in production use should be added to Teams as part of an app.</span></span> <span data-ttu-id="3e0a0-119">「[ボットを作成](https://docs.microsoft.com/microsoftteams/platform/concepts/bots/bots-create)して、 [Microsoft Teams のボットをテストしてデバッグする](https://docs.microsoft.com/microsoftteams/platform/concepts/bots/bots-test)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3e0a0-119">See [Create a bot](https://docs.microsoft.com/microsoftteams/platform/concepts/bots/bots-create) and [Test and debug your Microsoft Teams bot](https://docs.microsoft.com/microsoftteams/platform/concepts/bots/bots-test)</span></span>

<a name="create-custom-bots-for-microsoft-teams"></a><span data-ttu-id="3e0a0-120">Microsoft Teams のカスタム ボットの作成</span><span class="sxs-lookup"><span data-stu-id="3e0a0-120">Create custom bots for Microsoft Teams</span></span>
--------------------------------------

<span data-ttu-id="3e0a0-p105">Microsoft ボット フレームワークを使用して、LOB アプリケーションに統合されるボットを簡単に作成できます。独自のボットを作成および公開する方法については、[Creating and Testing a bot for Microsoft Teams](https://go.microsoft.com/fwlink/?linkid=854371) のガイダンスを参照してください。</span><span class="sxs-lookup"><span data-stu-id="3e0a0-p105">You can easily create a bot that integrates in to your LOB applications, using the Microsoft Bot Framework. Please refer to [Creating and Testing a bot for Microsoft Teams](https://go.microsoft.com/fwlink/?linkid=854371) guidance to learn how you can develop and publish your own bots.</span></span>

<span data-ttu-id="3e0a0-123">ボットを作成してボットのフレームワークに登録すると、それを公開することを選択できます。</span><span class="sxs-lookup"><span data-stu-id="3e0a0-123">When you create a bot and register it with the Bot Framework, you can choose to publish it.</span></span> <span data-ttu-id="3e0a0-124">公開しない場合、ボットはプライベートのままになります。</span><span class="sxs-lookup"><span data-stu-id="3e0a0-124">If you don't publish it, the bot remains private.</span></span> <span data-ttu-id="3e0a0-125">ボットを使う前にログインするようユーザーに要求することもできます。</span><span class="sxs-lookup"><span data-stu-id="3e0a0-125">You can also require your users to log in before using the bot.</span></span> <span data-ttu-id="3e0a0-126">ログインを要求することで、ボットのアプリケーション ID が既知のものになった場合でも組織の従業員のみがそのボットにアクセスできるようにできます。</span><span class="sxs-lookup"><span data-stu-id="3e0a0-126">Requiring login makes sure only employees of your organization can access the bot, even if the bot's application ID becomes known.</span></span> <span data-ttu-id="3e0a0-127">ボットを使った Active Directory でユーザー認証を実行する方法のコード例については、GitHub の[*AuthBot*](https://go.microsoft.com/fwlink/?linkid=854372) をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="3e0a0-127">See [*AuthBot*](https://go.microsoft.com/fwlink/?linkid=854372) on GitHub for a code example of how to authenticate users against your Active Directory using bots.</span></span>

<span data-ttu-id="3e0a0-128">ボットはチームへの展開前に [Bot Framework Emulator](https://go.microsoft.com/fwlink/?linkid=854373) を使用してテストできます。</span><span class="sxs-lookup"><span data-stu-id="3e0a0-128">Bots can be tested using the [Bot Framework Emulator](https://go.microsoft.com/fwlink/?linkid=854373) before they are deployed into your Teams.</span></span>

<a name="side-load-your-own-bot-for-private-chat"></a><span data-ttu-id="3e0a0-129">プライベート チャット用の独自のボットのサイド ロード</span><span class="sxs-lookup"><span data-stu-id="3e0a0-129">Side load your own bot for private chat</span></span>
---------------------------------------

1. <span data-ttu-id="3e0a0-130">ボットを作成したら、開発したボットの**アプリケーション設定**に移動して、[**アプリの設定**] の [ **microsoft appid** ] 設定の値をコピーします。![ボット用のアプリケーション設定ページのスクリーンショット](media/Add_bots_for_private_chats_and_channels_in_Microsoft_Teams_image5.png)</span><span class="sxs-lookup"><span data-stu-id="3e0a0-130">After you have created your bot, go to the **Application Settings** for the bot you developed, then under **App settings**, copy the value of the **MicrosoftAppId** setting.![Screenshot of Application Settings page for a bot](media/Add_bots_for_private_chats_and_channels_in_Microsoft_Teams_image5.png)</span></span>



2.  <span data-ttu-id="3e0a0-131">Microsoft Teams の [**チャット**] ウィンドウで [**Add chat icon (チャット アイコンの追加)**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="3e0a0-131">From within Microsoft Teams, on the **Chat** pane, select the **Add chat icon**.</span></span> <span data-ttu-id="3e0a0-132">[**To: (相手)**] にはボットの [**Microsoft App ID (Microsoft アプリ ID)**] を貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="3e0a0-132">For **To**, paste your bot's **Microsoft app ID**.</span></span> <span data-ttu-id="3e0a0-133">![Microsoft アプリ ID が強調表示されたチャットウィンドウのスクリーンショット](media/Add_bots_for_private_chats_and_channels_in_Microsoft_Teams_image6.png)</span><span class="sxs-lookup"><span data-stu-id="3e0a0-133">![Screenshot of a chat pane with Microsoft app ID highlighted](media/Add_bots_for_private_chats_and_channels_in_Microsoft_Teams_image6.png)</span></span>



3.  <span data-ttu-id="3e0a0-134">アプリ ID は [**ボット名**] になります。この手順の実行後にボットとのチャット会話を開始できます。</span><span class="sxs-lookup"><span data-stu-id="3e0a0-134">The app ID will resolve to your **bot name,** and then you can initiate a chat conversation with that bot.</span></span>

<a name="side-load-your-bot-for-channels"></a><span data-ttu-id="3e0a0-135">チャンネルのボットをサイド ローディングする</span><span class="sxs-lookup"><span data-stu-id="3e0a0-135">Side load your bot for channels</span></span>
-----------------------------------

<span data-ttu-id="3e0a0-136">ここでは、ボットを同僚と共有する場合の、さまざまなチームのチャネルにボットを追加する方法を紹介します。</span><span class="sxs-lookup"><span data-stu-id="3e0a0-136">If you want to share your bot with your colleagues, here's how to add it to channels of different teams:</span></span>

1. <span data-ttu-id="3e0a0-137">[ボットのアプリ パッケージを作成](https://docs.microsoft.com/microsoftteams/platform/concepts/apps/apps-upload)したら、Teams を開き、サイド ローディングするボットのチームを参照します。</span><span class="sxs-lookup"><span data-stu-id="3e0a0-137">After you have [created an app package for your bot](https://docs.microsoft.com/microsoftteams/platform/concepts/apps/apps-upload), open Teams and browse to the team in which you'll be side-loading the bot.</span></span>
2. <span data-ttu-id="3e0a0-138">**[アプリ Studio](https://docs.microsoft.com/microsoftteams/platform/get-started/get-started-app-studio)**、アプリを Microsoft Teams に追加します。</span><span class="sxs-lookup"><span data-stu-id="3e0a0-138">Add **[App Studio](https://docs.microsoft.com/microsoftteams/platform/get-started/get-started-app-studio)**, app to Microsoft Teams.</span></span>
3. <span data-ttu-id="3e0a0-139">App Studio で、[マニフェスト\*\*\*\* エディター] タブの![スクリーンショットを選択します。](media/Adding_Bot_To_Teams.png)</span><span class="sxs-lookup"><span data-stu-id="3e0a0-139">In App Studio, select the **Manifest Editor** Tab. ![Screenshot of the Manifest Editor Tab.](media/Adding_Bot_To_Teams.png)</span></span>
4. <span data-ttu-id="3e0a0-140">ボットを追加するには、[機能] で [ボット] を選択し、既存のボットを追加するように選択します。ドロップダウンから既存のボットを選択するか、既存のボットの Id を入力するオプションが表示されます。</span><span class="sxs-lookup"><span data-stu-id="3e0a0-140">To add your bot, In capabilities, select bot and chose to add an existing bot, then you will have the option to chose an existing bot from a drop or enter the Id of one of your existing bots.</span></span>
<span data-ttu-id="3e0a0-141">![既に作成したボットの選択を表示します。](media/Select_Existing_Bot.png)</span><span class="sxs-lookup"><span data-stu-id="3e0a0-141">![Shows selecting the bot you already created.](media/Select_Existing_Bot.png)</span></span>
5. <span data-ttu-id="3e0a0-142">アプリ パッケージの場所を参照、選択し、**開く**を選択します。</span><span class="sxs-lookup"><span data-stu-id="3e0a0-142">Browse to the location of your app package, select it, and then click **Open**.</span></span>
6. <span data-ttu-id="3e0a0-143">ボットの名前を選択します ([範囲] セクションの [チーム] チェックボックスを忘れずに確認してください)。</span><span class="sxs-lookup"><span data-stu-id="3e0a0-143">Select your bot's name (Don't forget to check the "Team" checkbox under the scope section)</span></span>
7. <span data-ttu-id="3e0a0-144">[テストと配布] オプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="3e0a0-144">Select the Test and distribute option.</span></span>
8. <span data-ttu-id="3e0a0-145">ポップアップが表示されるダイアログボックスで、ボットを接続するチームを選択します。</span><span class="sxs-lookup"><span data-stu-id="3e0a0-145">Select the team where you wish to connect your bot to in the dialog which pops up.</span></span>

<span data-ttu-id="3e0a0-146">これにより、お客様のボットが Microsoft チームのチームで利用できるようになります。</span><span class="sxs-lookup"><span data-stu-id="3e0a0-146">With this, your bot will be available in your Microsoft Team's team.</span></span>
