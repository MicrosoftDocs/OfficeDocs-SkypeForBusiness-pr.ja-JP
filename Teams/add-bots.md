---
title: "Microsoft のチームで非公開チャットとチャネルのコンポーネントを追加します。"
author: LolaJacobsen
ms.author: lolaj
manager: lolaj
ms.date: 09/25/2017
ms.topic: article
ms.service: msteams
description: "Microsoft チームで非公開チャットとチャネルのコンポーネントを追加する方法について、ユーザー設定のコンポーネントを作成する、側では、独自の結果を読み込む秘密チャットします。"
ms.openlocfilehash: c7f2aec398728f310fab780e96d4df09e4b7f582
ms.sourcegitcommit: 2d84f687ccc44220d5ec9d8b429dfae65cced5a7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/01/2018
---
<a name="add-bots-for-private-chats-and-channels-in-microsoft-teams"></a><span data-ttu-id="c7e68-103">Microsoft のチームで非公開チャットとチャネルのコンポーネントを追加します。</span><span class="sxs-lookup"><span data-stu-id="c7e68-103">Add bots for private chats and channels in Microsoft Teams</span></span>
==========================================================

<span data-ttu-id="c7e68-p101">コンポーネントをクエリに応答するか、他の更新プログラムが自動に通知を受け取るか興味を持ったユーザーの詳細についての通知。コンポーネントには、操作するタスクの管理、スケジュール、および Microsoft チームでチャットを行うを通じて、ポーリングなどのクラウド サービスにユーザーができるようにします。Microsoft チーム ロボットでは、 [Microsoft 結果 Framework](https://go.microsoft.com/fwlink/?linkid=854370)構築されます。チームが Microsoft には、このフレームワークを使用して開発されたコンポーネントが簡単に有効にすることができます。詳細については、 [Office 365 の組織で Microsoft チームを有効にする機能](enable-features-office-365.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c7e68-p101">Bots are automated programs that respond to queries or give updates and notifications about details users find interesting or want to stay informed about. Bots allow users to interact with cloud services like task management, scheduling, and polling, through chat conversations in Microsoft Teams. Bots for Microsoft Teams are built on the [Microsoft Bot Framework](https://go.microsoft.com/fwlink/?linkid=854370). The bots that are developed using this framework can be enabled easily for Microsoft Teams. For more information, see [Enable Microsoft Teams features in your Office 365 organization](enable-features-office-365.md).</span></span>

<span data-ttu-id="c7e68-p102">現時点では、Microsoft チームは、プライベート チャット チーム内でのチャンネルでコンポーネントをサポートします。管理者は、コンポーネントの使用を許可または Office 365 のテナント内の禁止かどうかを制御できます。<span id="_T-Bot" class="anchor"></span></span><span class="sxs-lookup"><span data-stu-id="c7e68-p102">Currently, Microsoft Teams support bots in private chats and channels within a team. Administrators can control whether the use of bots is allowed or prohibited within the Office 365 tenant.<span id="_T-Bot" class="anchor"></span></span></span>

<span data-ttu-id="c7e68-p103">コミュニティが開発したコンポーネントは、Microsoft チーム内で利用できます。ユーザー設定のコンポーネントが機能するは、テナント レベルでは、結果の機能と結果のサイドの読み込みを有効にする必要があります。プライベート チャットまたはチャンネルのコンポーネントを使用できます。チャンネルのチームの所有者またはメンバーは、コンポーネントを追加できます。</span><span class="sxs-lookup"><span data-stu-id="c7e68-p103">Bots developed by the community can be leveraged within Microsoft Teams. The bot’s functionality and bot’s side loading must be enabled on the tenant level for custom bots to be functional. Bots can be used in private chats or in channels. For channels, team owners or members can add bots.</span></span>

<span data-ttu-id="c7e68-115">詳細については、[アプリとサービス](https://support.office.com/en-us/article/Apps-and-services-cc1fba57-9900-4634-8306-2360a40c665b)の「を使用するロボット」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c7e68-115">For more information, see the section "Using bots" in [Apps and services](https://support.office.com/en-us/article/Apps-and-services-cc1fba57-9900-4634-8306-2360a40c665b).</span></span> 








 

<a name="create-custom-bots-for-microsoft-teams"></a><span data-ttu-id="c7e68-116">Microsoft チームのユーザー設定のコンポーネントを作成します。</span><span class="sxs-lookup"><span data-stu-id="c7e68-116">Create custom bots for Microsoft Teams</span></span>
--------------------------------------

<span data-ttu-id="c7e68-p104">簡単に作成できますに統合する結果 LOB アプリケーションに Microsoft 結果フレームワークを使用します。開発し、独自のコンポーネントを発行する方法については[、結果をチームが Microsoft のテストの作成と](https://go.microsoft.com/fwlink/?linkid=854371)ガイダンスを参照してください。</span><span class="sxs-lookup"><span data-stu-id="c7e68-p104">You can easily create a bot that integrates in to your LOB applications, using the Microsoft Bot Framework. Please refer to [Creating and Testing a bot for Microsoft Teams](https://go.microsoft.com/fwlink/?linkid=854371) guidance to learn how you can develop and publish your own bots.</span></span>

<span data-ttu-id="c7e68-p105">結果を作成して結果フレームワークに登録すると、それを公開することもできます。公開しない場合、結果はプライベートは残ります。ユーザーが、結果を使用する前にログインを要求することもできます。必要なログインでは、結果のアプリケーションの ID がわかっている場合でも、組織の従業員のみが、結果にアクセスできることを確認します。コンポーネントを使用して、Active Directory に対してユーザーを認証する方法については、GitHub [*AuthBot*](https://go.microsoft.com/fwlink/?linkid=854372)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c7e68-p105">When you create a bot and register it with the Bot Framework, you can choose to publish it. If you don't publish it, the bot remains private. You can also require your users to log in before using the bot. Requiring login makes sure only employees of your organization can access the bot, even if the bot's application ID becomes known. See [*AuthBot*](https://go.microsoft.com/fwlink/?linkid=854372) on GitHub for a code example of how to authenticate users against your Active Directory using bots.</span></span>

<span data-ttu-id="c7e68-124">コンポーネントをテストするには、チームに展開する前に、[結果 Framework エミュレーター](https://go.microsoft.com/fwlink/?linkid=854373)を使用します。</span><span class="sxs-lookup"><span data-stu-id="c7e68-124">Bots can be tested using the [Bot Framework Emulator](https://go.microsoft.com/fwlink/?linkid=854373) before they are deployed into your Teams.</span></span>

<a name="side-load-your-own-bot-for-private-chat"></a><span data-ttu-id="c7e68-125">サイド プライベート通話用の独自の結果を読み込む</span><span class="sxs-lookup"><span data-stu-id="c7e68-125">Side load your own bot for private chat</span></span>
---------------------------------------

1.  <span data-ttu-id="c7e68-126">結果を作成した後は、開発すると、結果の**結果のダッシュ ボード**[ページ](https://go.microsoft.com/fwlink/?linkid=854374)に移動し、[の**詳細について**は、[ **Microsoft アプリケーションの ID**をコピーします。![が強調表示された Microsoft アプリケーション id を結果の詳細] ページのスクリーン ショット。](media/Add_bots_for_private_chats_and_channels_in_Microsoft_Teams_image5.png)</span><span class="sxs-lookup"><span data-stu-id="c7e68-126">After you have created your bot, go to the **Bot Dashboard** [page](https://go.microsoft.com/fwlink/?linkid=854374) for the bot you developed, and then under **Details**, copy the **Microsoft App ID**.![Screenshot of details page for a bot with the Microsoft App ID highlighted.](media/Add_bots_for_private_chats_and_channels_in_Microsoft_Teams_image5.png)</span></span> 



2.  <span data-ttu-id="c7e68-p106">Microsoft チーム内で**[チャット**] ウィンドウで、[**チャットの追加] アイコン**を選択します。用**に**結果の**Microsoft アプリ ID**を貼り付けます。![追加チャットのアイコンで、[チャット] ウィンドウと Microsoft アプリ id が強調表示されている行のスクリーン ショット。](media/Add_bots_for_private_chats_and_channels_in_Microsoft_Teams_image6.png)</span><span class="sxs-lookup"><span data-stu-id="c7e68-p106">From within Microsoft Teams, on the **Chat** pane, select the **Add chat icon**. For **To**, paste your bot's **Microsoft app ID**. ![Screenshot of a chat pane with the icon for Add chat and the To line with the Microsoft app ID highlighted.](media/Add_bots_for_private_chats_and_channels_in_Microsoft_Teams_image6.png)</span></span>



3.  <span data-ttu-id="c7e68-130">アプリ ID**結果名**に解決され、その結果に、会話を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="c7e68-130">The app ID will resolve to your **bot name,** and then you can initiate a chat conversation with that bot.</span></span>
