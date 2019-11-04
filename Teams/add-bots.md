---
title: Microsoft Teams でプライベートのチャットやチャネルのボットを追加する
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
ms.collection:
- M365-collaboration
search.appverid: MET150
ms.reviewer: lucarras, jakon
description: 個人チャット、グループチャット、チャネル用に Microsoft Teams でボットを追加する方法と、個人チャット、グループチャット、チャネル用のボットをアップロードする方法について説明します。
appliesto:
- Microsoft Teams
ms.openlocfilehash: 7837fd3a832a1764cfde3968b73337069762dab3
ms.sourcegitcommit: 100ba1409bf0af58e4430877c1d29622d793d23f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/01/2019
ms.locfileid: "37516162"
---
<a name="add-bots-for-personal-chats-group-chats-and-channels-in-microsoft-teams"></a><span data-ttu-id="dc4fe-103">Microsoft Teams でパーソナルチャット、グループチャット、チャネルのボットを追加する</span><span class="sxs-lookup"><span data-stu-id="dc4fe-103">Add bots for personal chats, group chats, and channels in Microsoft Teams</span></span>
==========================================================
> [!IMPORTANT]
> [!INCLUDE [new-teams-sfb-admin-center-notice](includes/new-teams-sfb-admin-center-notice.md)]

<span data-ttu-id="dc4fe-104">ボットとは、クエリに応答したり、ユーザーが興味を持っている詳細や常に情報を得ていたい詳細について更新や通知を行う自動プログラムのことです。</span><span class="sxs-lookup"><span data-stu-id="dc4fe-104">Bots are automated programs that respond to queries or give updates and notifications about details users find interesting or want to stay informed about.</span></span> <span data-ttu-id="dc4fe-105">ボットは、ユーザーが Microsoft Teams でのチャットの会話を通じて、タスク管理、スケジュール、ポーリングなどのクラウドサービスを操作できるようにします。</span><span class="sxs-lookup"><span data-stu-id="dc4fe-105">Bots allow users to interact with cloud services like task management, scheduling, and polling, through chat conversations in Microsoft Teams.</span></span> <span data-ttu-id="dc4fe-106">Teams のボットは、 [Microsoft ボットのフレームワーク](https://go.microsoft.com/fwlink/?linkid=854370)上に構築されています。</span><span class="sxs-lookup"><span data-stu-id="dc4fe-106">Bots for Teams are built on the [Microsoft Bot Framework](https://go.microsoft.com/fwlink/?linkid=854370).</span></span> <span data-ttu-id="dc4fe-107">このフレームワークを使って開発されたボットは、Teams で簡単に有効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="dc4fe-107">The bots that are developed using this framework can be enabled easily for Teams.</span></span> <span data-ttu-id="dc4fe-108">詳細については、[組織のMicrosoft Teams 設定の管理](enable-features-office-365.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="dc4fe-108">For more information, see [Manage Microsoft Teams settings for your organization](enable-features-office-365.md).</span></span>

<span data-ttu-id="dc4fe-109">現時点では、チームは、個人チャット、グループチャット、チーム内のチャネルでボットをサポートしています。</span><span class="sxs-lookup"><span data-stu-id="dc4fe-109">Currently, Teams supports bots in personal chats, group chats, and channels within a team.</span></span> <span data-ttu-id="dc4fe-110">管理者は、Office 365 テナント内でボットの使用を許可または禁止するかどうかを制御できます。<span id="_T-Bot" class="anchor"></span></span><span class="sxs-lookup"><span data-stu-id="dc4fe-110">Administrators can control whether the use of bots is allowed or prohibited within the Office 365 tenant.<span id="_T-Bot" class="anchor"></span></span></span>

<span data-ttu-id="dc4fe-111">コミュニティによって開発されたボットは Teams 内で活用できます。</span><span class="sxs-lookup"><span data-stu-id="dc4fe-111">Bots developed by the community can be leveraged within Teams.</span></span> <span data-ttu-id="dc4fe-112">ボットの機能とカスタムアプリ (サイドローディングとも呼ばれます) をアップロードする機能は、カスタムボットが機能するためにテナントレベルで有効になっている必要があります。</span><span class="sxs-lookup"><span data-stu-id="dc4fe-112">The bot's functionality and the ability to upload custom apps (also known as sideloading) must be enabled on the tenant level for custom bots to be functional.</span></span> <span data-ttu-id="dc4fe-113">ボットは、個人チャット、グループチャット、チャネルで使用できます。</span><span class="sxs-lookup"><span data-stu-id="dc4fe-113">Bots can be used in personal chats, group chats, and channels.</span></span> <span data-ttu-id="dc4fe-114">チャネルの場合、チーム所有者またはメンバーがボットを追加できます。</span><span class="sxs-lookup"><span data-stu-id="dc4fe-114">For channels, team owners or members can add bots.</span></span>

<span data-ttu-id="dc4fe-115">詳細については、「[アプリとサービス](https://support.office.com/article/Apps-and-services-cc1fba57-9900-4634-8306-2360a40c665b)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="dc4fe-115">For more information, see [Apps and services](https://support.office.com/article/Apps-and-services-cc1fba57-9900-4634-8306-2360a40c665b).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="dc4fe-116">テスト以外の理由で、[GUID] にボットを追加することはお勧めしません。</span><span class="sxs-lookup"><span data-stu-id="dc4fe-116">Adding a bot by GUID, for anything other than testing purposes, is not recommended.</span></span> <span data-ttu-id="dc4fe-117">これにより、ボットの機能が大幅に制限されます。</span><span class="sxs-lookup"><span data-stu-id="dc4fe-117">Doing so severely limits the functionality of a bot.</span></span> <span data-ttu-id="dc4fe-118">製品使用中のボットは、アプリの一部として Teams に追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="dc4fe-118">Bots in production use should be added to Teams as part of an app.</span></span> <span data-ttu-id="dc4fe-119">「[ボットを作成](https://docs.microsoft.com/microsoftteams/platform/concepts/bots/bots-create)して、 [Microsoft Teams のボットをテストしてデバッグする](https://docs.microsoft.com/microsoftteams/platform/concepts/bots/bots-test)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="dc4fe-119">See [Create a bot](https://docs.microsoft.com/microsoftteams/platform/concepts/bots/bots-create) and [Test and debug your Microsoft Teams bot](https://docs.microsoft.com/microsoftteams/platform/concepts/bots/bots-test)</span></span>

<a name="create-custom-bots-for-microsoft-teams"></a><span data-ttu-id="dc4fe-120">Microsoft Teams のカスタム ボットの作成</span><span class="sxs-lookup"><span data-stu-id="dc4fe-120">Create custom bots for Microsoft Teams</span></span>
--------------------------------------

<span data-ttu-id="dc4fe-121">Microsoft ボットフレームワークを使用して、LOB アプリケーションに統合されるボットを簡単に作成することができます。</span><span class="sxs-lookup"><span data-stu-id="dc4fe-121">You can easily create a bot that integrates in to your LOB applications, using the Microsoft Bot Framework.</span></span> <span data-ttu-id="dc4fe-122">独自のボットを開発して公開する方法については、「 [Microsoft Teams のボットの作成とテスト](https://go.microsoft.com/fwlink/?linkid=854371)」のガイダンスを参照してください。</span><span class="sxs-lookup"><span data-stu-id="dc4fe-122">See the [Creating and Testing a bot for Microsoft Teams](https://go.microsoft.com/fwlink/?linkid=854371) guidance to learn how you can develop and publish your own bots.</span></span>

<span data-ttu-id="dc4fe-123">ボットを作成してボットのフレームワークに登録すると、それを公開することを選択できます。</span><span class="sxs-lookup"><span data-stu-id="dc4fe-123">When you create a bot and register it with the Bot Framework, you can choose to publish it.</span></span> <span data-ttu-id="dc4fe-124">公開しない場合、ボットはプライベートのままになります。</span><span class="sxs-lookup"><span data-stu-id="dc4fe-124">If you don't publish it, the bot remains private.</span></span> <span data-ttu-id="dc4fe-125">ボットを使う前にログインするようユーザーに要求することもできます。</span><span class="sxs-lookup"><span data-stu-id="dc4fe-125">You can also require your users to log in before using the bot.</span></span> <span data-ttu-id="dc4fe-126">ログインを要求することで、ボットのアプリケーション ID が既知のものになった場合でも組織の従業員のみがそのボットにアクセスできるようにできます。</span><span class="sxs-lookup"><span data-stu-id="dc4fe-126">Requiring login makes sure only employees of your organization can access the bot, even if the bot's application ID becomes known.</span></span> <span data-ttu-id="dc4fe-127">ボットを使った Active Directory でユーザー認証を実行する方法のコード例については、GitHub の[*AuthBot*](https://go.microsoft.com/fwlink/?linkid=854372) をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="dc4fe-127">See [*AuthBot*](https://go.microsoft.com/fwlink/?linkid=854372) on GitHub for a code example of how to authenticate users against your Active Directory using bots.</span></span>

<span data-ttu-id="dc4fe-128">ボットはチームへの展開前に [Bot Framework Emulator](https://go.microsoft.com/fwlink/?linkid=854373) を使用してテストできます。</span><span class="sxs-lookup"><span data-stu-id="dc4fe-128">Bots can be tested using the [Bot Framework Emulator](https://go.microsoft.com/fwlink/?linkid=854373) before they are deployed into your Teams.</span></span>

<a name="upload-your-bot-for-personal-chat"></a><span data-ttu-id="dc4fe-129">お客様のボットをアップロードする</span><span class="sxs-lookup"><span data-stu-id="dc4fe-129">Upload your bot for personal chat</span></span>
---------------------------------------

1. <span data-ttu-id="dc4fe-130">ボットを作成したら、開発したボットの**アプリケーション設定**に移動し、[アプリの**設定**] の [ **microsoft appid** ] 設定の値をコピーします。![ボット用のアプリケーション設定ページのスクリーンショット](media/Add_bots_for_private_chats_and_channels_in_Microsoft_Teams_image5.png)</span><span class="sxs-lookup"><span data-stu-id="dc4fe-130">After you create your bot, go to the **Application Settings** for the bot you developed, and then under **App settings**, copy the value of the **MicrosoftAppId** setting.![Screenshot of Application Settings page for a bot](media/Add_bots_for_private_chats_and_channels_in_Microsoft_Teams_image5.png)</span></span>

2.  <span data-ttu-id="dc4fe-131">Teams の**チャット**ウィンドウで、[**チャットの追加] アイコン**を選択します。</span><span class="sxs-lookup"><span data-stu-id="dc4fe-131">In Teams, on the **Chat** pane, select the **Add chat icon**.</span></span> <span data-ttu-id="dc4fe-132">[**宛先**] に、ボットの**Microsoft アプリ ID**を貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="dc4fe-132">In **To**, paste your bot's **Microsoft app ID**.</span></span> <span data-ttu-id="dc4fe-133">![Microsoft アプリ ID が強調表示されたチャットウィンドウのスクリーンショット](media/Add_bots_for_private_chats_and_channels_in_Microsoft_Teams_image6.png)</span><span class="sxs-lookup"><span data-stu-id="dc4fe-133">![Screenshot of a chat pane with Microsoft app ID highlighted](media/Add_bots_for_private_chats_and_channels_in_Microsoft_Teams_image6.png)</span></span>

3. <span data-ttu-id="dc4fe-134">アプリ ID は**ボット名**に解決され、そのボットとのチャット会話を開始できます。</span><span class="sxs-lookup"><span data-stu-id="dc4fe-134">The app ID will resolve to your **bot name,** and then you can start a chat conversation with that bot.</span></span>

<a name="upload-your-bot-for-group-chats-or-channels"></a><span data-ttu-id="dc4fe-135">グループチャットまたはチャネル用のボットをアップロードする</span><span class="sxs-lookup"><span data-stu-id="dc4fe-135">Upload your bot for group chats or channels</span></span>
-----------------------------------

<span data-ttu-id="dc4fe-136">ボットを同僚と共有する場合は、次のようにして、グループチャットやさまざまなチームのチャンネルに追加します。</span><span class="sxs-lookup"><span data-stu-id="dc4fe-136">If you want to share your bot with your colleagues, here's how to add it to group chats or channels of different teams:</span></span>

1. <span data-ttu-id="dc4fe-137">[ボットのアプリパッケージを作成](https://docs.microsoft.com/microsoftteams/platform/concepts/apps/apps-upload)したら、Teams を開き、ボットをアップロードするチームを参照します。</span><span class="sxs-lookup"><span data-stu-id="dc4fe-137">After you [create an app package for your bot](https://docs.microsoft.com/microsoftteams/platform/concepts/apps/apps-upload), open Teams and browse to the team in which you'll be uploading the bot.</span></span>
2. <span data-ttu-id="dc4fe-138">**[App Studio](https://docs.microsoft.com/microsoftteams/platform/get-started/get-started-app-studio)** のアプリを Teams に追加します。</span><span class="sxs-lookup"><span data-stu-id="dc4fe-138">Add **[App Studio](https://docs.microsoft.com/microsoftteams/platform/get-started/get-started-app-studio)**, app to Teams.</span></span>
3. <span data-ttu-id="dc4fe-139">App Studio で、 **[マニフェストエディター** ] タブの![スクリーンショットを選択します。](media/Adding_Bot_To_Teams.png)</span><span class="sxs-lookup"><span data-stu-id="dc4fe-139">In App Studio, select the **Manifest Editor** Tab. ![Screenshot of the Manifest Editor Tab.](media/Adding_Bot_To_Teams.png)</span></span>
4. <span data-ttu-id="dc4fe-140">ボットを追加するには、[機能] でボットを選択して、既存のボットを追加します。</span><span class="sxs-lookup"><span data-stu-id="dc4fe-140">To add your bot, in capabilities, select the bot and choose to add an existing bot.</span></span> <span data-ttu-id="dc4fe-141">次に、既存のボットを選択するか、既存のボットの Id を入力します。</span><span class="sxs-lookup"><span data-stu-id="dc4fe-141">Then, choose an existing bot or enter the Id of an existing bot.</span></span>
<span data-ttu-id="dc4fe-142">![既に作成したボットの選択を表示します。](media/Select_Existing_Bot.png)</span><span class="sxs-lookup"><span data-stu-id="dc4fe-142">![Shows selecting the bot you already created.](media/Select_Existing_Bot.png)</span></span>
5. <span data-ttu-id="dc4fe-143">アプリ パッケージの場所を参照、選択し、**開く**を選択します。</span><span class="sxs-lookup"><span data-stu-id="dc4fe-143">Browse to the location of your app package, select it, and then click **Open**.</span></span>
6. <span data-ttu-id="dc4fe-144">ボットの名前を選択します。</span><span class="sxs-lookup"><span data-stu-id="dc4fe-144">Select your bot's name.</span></span> <span data-ttu-id="dc4fe-145">([範囲] セクションの下にある [**グループチャット**] または [**チーム**] チェックボックスを必ずオンにしてください)。</span><span class="sxs-lookup"><span data-stu-id="dc4fe-145">(Don't forget to select the **Group chat** or **Team** check box under the scope section).</span></span>
7. <span data-ttu-id="dc4fe-146">[**テストと配布**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="dc4fe-146">Select **Test and distribute**.</span></span>
8. <span data-ttu-id="dc4fe-147">ボットを接続するグループチャットまたはチームを選択します。</span><span class="sxs-lookup"><span data-stu-id="dc4fe-147">Select the group chat or team where you want to connect your bot to.</span></span>

    <span data-ttu-id="dc4fe-148">お客様のボットは、Teams のグループチャットまたはチームで利用できます。</span><span class="sxs-lookup"><span data-stu-id="dc4fe-148">Your bot will be available in your group chat or team in Teams.</span></span>
