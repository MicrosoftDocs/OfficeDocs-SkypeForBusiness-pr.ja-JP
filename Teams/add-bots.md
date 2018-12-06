---
title: Microsoft Teams でプライベートのチャットやチャネルのボットを追加する
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 12/05/2018
ms.topic: article
ms.service: msteams
ms.collection: Teams_ITAdmin_Help
search.appverid: MET150
ms.reviewer: lucarras
description: プライベート チャットとチャネル用に Microsoft Teams にボットを追加する方法、カスタム ボットを作成する方法、プライベート チャット用に独自のボットをサイド ロードする方法について紹介します。
appliesto:
- Microsoft Teams
ms.openlocfilehash: 548da99413714f3947cec909ea51301eb68d2c0d
ms.sourcegitcommit: 969a71ef0ac0030c27bd2455c3bf9d536dbcd752
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/06/2018
ms.locfileid: "27182386"
---
<a name="add-bots-for-private-chats-and-channels-in-microsoft-teams"></a><span data-ttu-id="c1a09-103">Microsoft Teams でプライベートのチャットやチャネルのボットを追加する</span><span class="sxs-lookup"><span data-stu-id="c1a09-103">Add bots for private chats and channels in Microsoft Teams</span></span>
==========================================================
> [!IMPORTANT]
> [!INCLUDE [new-teams-sfb-admin-center-notice](includes/new-teams-sfb-admin-center-notice.md)]

<span data-ttu-id="c1a09-104">ボットは、クエリに応答したり、更新情報を提供する自動化されたプログラムとユーザーの詳細についての通知が興味深いかに関する情報を把握します。</span><span class="sxs-lookup"><span data-stu-id="c1a09-104">Bots are automated programs that respond to queries or give updates and notifications about details users find interesting or want to stay informed about.</span></span> <span data-ttu-id="c1a09-105">ボットは、タスク管理、スケジュール、およびマイクロソフトのチームでのチャットの会話で、ポーリングのようなクラウド サービスと対話するようにします。</span><span class="sxs-lookup"><span data-stu-id="c1a09-105">Bots allow users to interact with cloud services like task management, scheduling, and polling, through chat conversations in Microsoft Teams.</span></span> <span data-ttu-id="c1a09-106">[マイクロソフト Bot のフレームワーク](https://go.microsoft.com/fwlink/?linkid=854370)では、マイクロソフト チームの bot が構築されます。</span><span class="sxs-lookup"><span data-stu-id="c1a09-106">Bots for Microsoft Teams are built on the [Microsoft Bot Framework](https://go.microsoft.com/fwlink/?linkid=854370).</span></span> <span data-ttu-id="c1a09-107">このフレームワークを使用して開発されたボットは、マイクロソフトのチームを簡単に有効にできます。</span><span class="sxs-lookup"><span data-stu-id="c1a09-107">The bots that are developed using this framework can be enabled easily for Microsoft Teams.</span></span> <span data-ttu-id="c1a09-108">詳細については、 [Office 365 の組織での Microsoft チームの管理機能](enable-features-office-365.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c1a09-108">For more information, see [Manage Microsoft Teams features in your Office 365 organization](enable-features-office-365.md).</span></span>

<span data-ttu-id="c1a09-p102">現在、Microsoft Teams は、チーム内のプライベート チャットとチャネルにおけるボットをサポートしています。管理者は、Office 365 テナント内でのボットの使用可否を管理できます。<span id="_T-Bot" class="anchor"></span></span><span class="sxs-lookup"><span data-stu-id="c1a09-p102">Currently, Microsoft Teams support bots in private chats and channels within a team. Administrators can control whether the use of bots is allowed or prohibited within the Office 365 tenant.<span id="_T-Bot" class="anchor"></span></span></span>

<span data-ttu-id="c1a09-111">コミュニティにより開発されたボットは、Microsoft Teams 内で利用できます。</span><span class="sxs-lookup"><span data-stu-id="c1a09-111">Bots developed by the community can be leveraged within Microsoft Teams.</span></span> <span data-ttu-id="c1a09-112">ボットを機能させるには、ボットの機能とサイド ローディングをテナント レベルで有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="c1a09-112">The bot’s functionality and bot’s side loading must be enabled on the tenant level for custom bots to be functional.</span></span> <span data-ttu-id="c1a09-113">ボットはプライベート チャットまたはチャネルにおいて使用できます。</span><span class="sxs-lookup"><span data-stu-id="c1a09-113">Bots can be used in private chats or in channels.</span></span> <span data-ttu-id="c1a09-114">チャネルの場合、チーム所有者またはメンバーがボットを追加できます。</span><span class="sxs-lookup"><span data-stu-id="c1a09-114">For channels, team owners or members can add bots.</span></span>

<span data-ttu-id="c1a09-115">詳細については、[アプリとサービス](https://support.office.com/article/Apps-and-services-cc1fba57-9900-4634-8306-2360a40c665b)の「ボットの使用」セクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="c1a09-115">For more information, see the section "Using bots" in [Apps and services](https://support.office.com/article/Apps-and-services-cc1fba57-9900-4634-8306-2360a40c665b).</span></span> 




<a name="create-custom-bots-for-microsoft-teams"></a><span data-ttu-id="c1a09-116">Microsoft Teams のカスタム ボットの作成</span><span class="sxs-lookup"><span data-stu-id="c1a09-116">Create custom bots for Microsoft Teams</span></span>
--------------------------------------

<span data-ttu-id="c1a09-p104">Microsoft ボット フレームワークを使用して、LOB アプリケーションに統合されるボットを簡単に作成できます。独自のボットを作成および公開する方法については、[Creating and Testing a bot for Microsoft Teams](https://go.microsoft.com/fwlink/?linkid=854371) のガイダンスを参照してください。</span><span class="sxs-lookup"><span data-stu-id="c1a09-p104">You can easily create a bot that integrates in to your LOB applications, using the Microsoft Bot Framework. Please refer to [Creating and Testing a bot for Microsoft Teams](https://go.microsoft.com/fwlink/?linkid=854371) guidance to learn how you can develop and publish your own bots.</span></span>

<span data-ttu-id="c1a09-119">ボットを作成してボットのフレームワークに登録すると、それを公開することを選択できます。</span><span class="sxs-lookup"><span data-stu-id="c1a09-119">When you create a bot and register it with the Bot Framework, you can choose to publish it.</span></span> <span data-ttu-id="c1a09-120">公開しない場合、ボットはプライベートのままになります。</span><span class="sxs-lookup"><span data-stu-id="c1a09-120">If you don't publish it, the bot remains private.</span></span> <span data-ttu-id="c1a09-121">ボットを使う前にログインするようユーザーに要求することもできます。</span><span class="sxs-lookup"><span data-stu-id="c1a09-121">You can also require your users to log in before using the bot.</span></span> <span data-ttu-id="c1a09-122">ログインを要求することで、ボットのアプリケーション ID が既知のものになった場合でも組織の従業員のみがそのボットにアクセスできるようにできます。</span><span class="sxs-lookup"><span data-stu-id="c1a09-122">Requiring login makes sure only employees of your organization can access the bot, even if the bot's application ID becomes known.</span></span> <span data-ttu-id="c1a09-123">ボットを使った Active Directory でユーザー認証を実行する方法のコード例については、GitHub の[*AuthBot*](https://go.microsoft.com/fwlink/?linkid=854372) をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="c1a09-123">See [*AuthBot*](https://go.microsoft.com/fwlink/?linkid=854372) on GitHub for a code example of how to authenticate users against your Active Directory using bots.</span></span>

<span data-ttu-id="c1a09-124">ボットはチームへの展開前に [Bot Framework Emulator](https://go.microsoft.com/fwlink/?linkid=854373) を使用してテストできます。</span><span class="sxs-lookup"><span data-stu-id="c1a09-124">Bots can be tested using the [Bot Framework Emulator](https://go.microsoft.com/fwlink/?linkid=854373) before they are deployed into your Teams.</span></span>

<a name="side-load-your-own-bot-for-private-chat"></a><span data-ttu-id="c1a09-125">プライベート チャット用の独自のボットのサイド ロード</span><span class="sxs-lookup"><span data-stu-id="c1a09-125">Side load your own bot for private chat</span></span>
---------------------------------------

1. <span data-ttu-id="c1a09-126">Bot を作成して、ボットを開発した、し、[**アプリケーションの設定**の**アプリケーションの設定**を**MicrosoftAppId**の設定の値をコピーします。![の bot が強調表示されている Microsoft アプリケーションの ID を持つアプリケーションの設定のスクリーン ショットのページです。](media/Add_bots_for_private_chats_and_channels_in_Microsoft_Teams_image5.png)</span><span class="sxs-lookup"><span data-stu-id="c1a09-126">After you have created your bot, go to the **Application Settings** for the bot you developed, then under **App settings**, copy the value of the **MicrosoftAppId** setting.![Screenshot of Application Settings page for a bot with the Microsoft App ID highlighted.](media/Add_bots_for_private_chats_and_channels_in_Microsoft_Teams_image5.png)</span></span>



2.  <span data-ttu-id="c1a09-127">Microsoft Teams の [**チャット**] ウィンドウで [**Add chat icon (チャット アイコンの追加)**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="c1a09-127">From within Microsoft Teams, on the **Chat** pane, select the **Add chat icon**.</span></span> <span data-ttu-id="c1a09-128">[**To: (相手)**] にはボットの [**Microsoft App ID (Microsoft アプリ ID)**] を貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="c1a09-128">For **To**, paste your bot's **Microsoft app ID**.</span></span> <span data-ttu-id="c1a09-129">![チャットを追加するアイコンと、[Microsoft App ID (Microsoft アプリ ID)] が強調表示された [To (相手)] 行が含まれているチャット ウィンドウのスクリーンショット。](media/Add_bots_for_private_chats_and_channels_in_Microsoft_Teams_image6.png)</span><span class="sxs-lookup"><span data-stu-id="c1a09-129">![Screenshot of a chat pane with the icon for Add chat and the To line with the Microsoft app ID highlighted.](media/Add_bots_for_private_chats_and_channels_in_Microsoft_Teams_image6.png)</span></span>



3.  <span data-ttu-id="c1a09-130">アプリ ID は [**ボット名**] になります。この手順の実行後にボットとのチャット会話を開始できます。</span><span class="sxs-lookup"><span data-stu-id="c1a09-130">The app ID will resolve to your **bot name,** and then you can initiate a chat conversation with that bot.</span></span>

<a name="side-load-your-bot-for-channels"></a><span data-ttu-id="c1a09-131">側のチャネル、bot をロードします。</span><span class="sxs-lookup"><span data-stu-id="c1a09-131">Side load your bot for channels</span></span>
-----------------------------------

<span data-ttu-id="c1a09-132">Bot を仲間と共有するには、さまざまなチームのチャンネルに追加する方法です。</span><span class="sxs-lookup"><span data-stu-id="c1a09-132">If you want to share your bot with your colleagues, here's how to add it to channels of different teams:</span></span>

1. <span data-ttu-id="c1a09-133">[ボットは、アプリケーション パッケージを作成](https://docs.microsoft.com/en-us/microsoftteams/platform/concepts/apps/apps-upload)したらは、チームを開きチームを説明する側の読み込み bot を参照します。</span><span class="sxs-lookup"><span data-stu-id="c1a09-133">After you have [created an app package for your bot](https://docs.microsoft.com/en-us/microsoftteams/platform/concepts/apps/apps-upload), open Teams and browse to the team in which you'll be side-loading the bot.</span></span>
2. <span data-ttu-id="c1a09-134">チーム名の横の**詳細**(...) を選択します。</span><span class="sxs-lookup"><span data-stu-id="c1a09-134">Select **More** (...) next to the team name.</span></span>
3. <span data-ttu-id="c1a09-135">**管理チーム**を選択し、[**アプリケーション**] タブを選択します。</span><span class="sxs-lookup"><span data-stu-id="c1a09-135">Select **Manage team** and then select the **Apps** tab.</span></span>
4. <span data-ttu-id="c1a09-136">、右下の画面では、**カスタム アプリケーションをアップロード**を選択します。</span><span class="sxs-lookup"><span data-stu-id="c1a09-136">At the bottom-right of your screen, select **Upload a custom app**.</span></span>
5. <span data-ttu-id="c1a09-137">アプリケーション パッケージの場所を参照するを選択し、[**開く**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c1a09-137">Browse to the location of your app package, select it, and then click **Open**.</span></span>
