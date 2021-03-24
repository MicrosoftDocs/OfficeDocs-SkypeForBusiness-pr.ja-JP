---
title: 常設チャット アドイン
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/27/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.lscp.PersistentChatAddin
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 66124a70-67e8-4bda-9da5-8ab13afccf49
description: '[常設チャット] ページの [アドイン] セクションを使用して、URL を常設チャット ルームに関連付けできます。 これらの URL は、会話機能拡張ウィンドウのチャット ルームのクライアントに表示されます。 管理者は、登録されたアドインのリストにアドインを追加する必要があります。また、チャット ルームの管理者/作成者は、ユーザーがクライアントでこのアップグレードを確認する前に、登録されたアドインの 1 つとルームを関連付ける必要があります。'
ms.openlocfilehash: c90383a26c658e8da73df09368a5d8fe04cfe69b
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51099503"
---
# <a name="persistent-chat-add-in"></a><span data-ttu-id="93eb1-105">常設チャット アドイン</span><span class="sxs-lookup"><span data-stu-id="93eb1-105">Persistent Chat Add-in</span></span>

<span data-ttu-id="93eb1-106">[常設チャット]**ページの**[アドイン] セクションを使用して、URL を常設チャット ルームに関連付けできます。</span><span class="sxs-lookup"><span data-stu-id="93eb1-106">You can use the **Add-in** section of the **Persistent Chat** page to associate URLs with Persistent Chat rooms.</span></span> <span data-ttu-id="93eb1-107">これらの URL は、会話機能拡張ウィンドウのチャット ルームのクライアントに表示されます。</span><span class="sxs-lookup"><span data-stu-id="93eb1-107">These URLs appear in the client in the chat room in the conversation extensibility pane.</span></span> <span data-ttu-id="93eb1-108">管理者は、登録されたアドインのリストにアドインを追加する必要があります。また、チャット ルームの管理者/作成者は、ユーザーがクライアントでこのアップグレードを確認する前に、登録されたアドインの 1 つとルームを関連付ける必要があります。</span><span class="sxs-lookup"><span data-stu-id="93eb1-108">An administrator must add Add-ins to the list of registered add-ins, and chat room managers/Creators must associate rooms with one of the registered add-ins before users can see this upgrade in their client.</span></span>

<span data-ttu-id="93eb1-109">アドインは、ルーム内でのエクスペリエンスを拡張するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="93eb1-109">Add-ins are used to extend the in-room experience.</span></span> <span data-ttu-id="93eb1-110">一般的なアドインには、株式ティッカーがチャット ルームに投稿され、拡張ウィンドウに在庫履歴が表示される Silverlight アプリケーションを指す URL が含まれる場合があります。</span><span class="sxs-lookup"><span data-stu-id="93eb1-110">A typical add-in might include a URL pointing to a Silverlight application that intercepts when a stock ticker is posted to a chat room, and shows the stock history in the extensibility pane.</span></span> <span data-ttu-id="93eb1-111">また、OneNote 2013 の URL をアドインとしてチャット ルームに組み込み、"優先事項" や "今日のトピック" などの共有コンテキストを表示することもできます。</span><span class="sxs-lookup"><span data-stu-id="93eb1-111">Other examples include embedding a OneNote 2013 URL in the chat room as an add-in to include some shared context, such as "Top of mind" or "Topic of the day."</span></span>

<span data-ttu-id="93eb1-112">常設チャット ルーム用のアドインを作成するには [、「Configure add-ins for Persistent Chat rooms in Skype for Business Server 2015」を参照](../../manage/persistent-chat/configure-add-ins.md)してください。</span><span class="sxs-lookup"><span data-stu-id="93eb1-112">To create Add-ins for Persistent Chat rooms, see [Configure add-ins for Persistent Chat rooms in Skype for Business Server 2015](../../manage/persistent-chat/configure-add-ins.md).</span></span> <span data-ttu-id="93eb1-113">常設チャット管理者の場合は、コントロール パネルまたはコマンドレットを使用してアドインWindows PowerShellできます。</span><span class="sxs-lookup"><span data-stu-id="93eb1-113">If you are a Persistent Chat Administrator, you can create add-ins by using the control panel or Windows PowerShell cmdlets.</span></span>

## <a name="tasks-that-you-can-perform"></a><span data-ttu-id="93eb1-114">実行できるタスク</span><span class="sxs-lookup"><span data-stu-id="93eb1-114">Tasks that you can perform</span></span>

<span data-ttu-id="93eb1-115">[**アドイン**] ページでは、次のタスクを実行できます。</span><span class="sxs-lookup"><span data-stu-id="93eb1-115">You can perform the following tasks on the **Add-in** page:</span></span>

- [<span data-ttu-id="93eb1-116">Skype for Business Server 2015 で常設チャット ルームのアドインを構成する</span><span class="sxs-lookup"><span data-stu-id="93eb1-116">Configure add-ins for Persistent Chat rooms in Skype for Business Server 2015</span></span>](../../manage/persistent-chat/configure-add-ins.md)

## <a name="to-configure-add-ins-for-chat-rooms"></a><span data-ttu-id="93eb1-117">チャット ルームのアドインを構成するには</span><span class="sxs-lookup"><span data-stu-id="93eb1-117">To configure Add-ins for chat rooms</span></span>

<span data-ttu-id="93eb1-118">以下は、ページ上のメニュー、コマンド、フィールド、およびプロパティについての説明です。</span><span class="sxs-lookup"><span data-stu-id="93eb1-118">The following lists describe the menus, command, fields, and properties on the page.</span></span>

1. <span data-ttu-id="93eb1-119">CsPersistentChatAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="93eb1-119">From a user account that is assigned to the CsPersistentChatAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2. <span data-ttu-id="93eb1-120">[スタート **] メニュー** から、Skype for Business Server コントロール パネルを選択するか、ブラウザー ウィンドウを開き、管理 URL を入力します。</span><span class="sxs-lookup"><span data-stu-id="93eb1-120">From the **Start** menu, select the Skype for Business Server Control Panel or open a browser window, and then enter the Admin URL.</span></span> <span data-ttu-id="93eb1-121">コントロール パネルの起動に使用できるさまざまな方法の詳細については [、「Open Lync Server 管理ツール」を参照してください](/previous-versions/office/lync-server-2013/lync-server-2013-open-lync-server-administrative-tools)。</span><span class="sxs-lookup"><span data-stu-id="93eb1-121">For details about the different methods that you can use to start the control panel, see [Open Lync Server Administrative Tools](/previous-versions/office/lync-server-2013/lync-server-2013-open-lync-server-administrative-tools).</span></span>

3. <span data-ttu-id="93eb1-122">左側のナビゲーション バーで [**常設チャット**] をクリックして、[**アドイン**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="93eb1-122">In the left navigation bar, click **Persistent Chat**, and then click **Add-in**.</span></span>

    <span data-ttu-id="93eb1-123">複数の常設チャット サーバー プール展開の場合は、ドロップダウン リストから適切なプールを選択します。</span><span class="sxs-lookup"><span data-stu-id="93eb1-123">For multiple Persistent Chat Server pool deployments, select the appropriate pool from the drop-down list.</span></span>

4. <span data-ttu-id="93eb1-124">[**アドイン**] ページで、[**新規**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="93eb1-124">On the **Add-in** page, click **New**.</span></span>

5. <span data-ttu-id="93eb1-125">[ **サービスの選択]** で、アドインを作成する必要がある常設チャット サーバー プールに対応するサービスを選択します。</span><span class="sxs-lookup"><span data-stu-id="93eb1-125">In **Select a Service**, select the service corresponding to the Persistent Chat Server pool where you need to create the Add-in.</span></span> <span data-ttu-id="93eb1-126">アドインをプール間で移動したり、複数のプールで共有したりすることはできません。</span><span class="sxs-lookup"><span data-stu-id="93eb1-126">Add-ins cannot be moved from one pool to another or shared between different pools.</span></span>

6. <span data-ttu-id="93eb1-127">[**新規 アドイン**] で、次の操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="93eb1-127">In **New Add-in**, do the following:</span></span>

   - <span data-ttu-id="93eb1-128">[**名前**] に、新しいアドインの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="93eb1-128">In **Name**, specify a name for the new add-in.</span></span>

   - <span data-ttu-id="93eb1-p107">[**URL**] で、アドインに関連付ける URL を指定します。URL には http および https プロトコルのみを使用できます。</span><span class="sxs-lookup"><span data-stu-id="93eb1-p107">In **URL**, specify the URL to be associated with the add-in. URLs are limited to http and https protocols.</span></span>

7. <span data-ttu-id="93eb1-131">[**確定**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="93eb1-131">Click **Commit**.</span></span>

## <a name="see-also"></a><span data-ttu-id="93eb1-132">関連項目</span><span class="sxs-lookup"><span data-stu-id="93eb1-132">See also</span></span>

<span data-ttu-id="93eb1-133">常設チャット サーバーの機能の詳細については、「Plan for Persistent Chat Server in [Skype for Business Server 2015](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md)」、Skype for Business Server 2015 での常設チャット サーバーの展開、および Skype for Business Server [2015](../../deploy/deploy-persistent-chat-server/deploy-persistent-chat-server.md)での常設チャット サーバーの管理を参照してください。 [](../../manage/persistent-chat/persistent-chat.md)</span><span class="sxs-lookup"><span data-stu-id="93eb1-133">For details about Persistent Chat Server features and capabilities, see [Plan for Persistent Chat Server in Skype for Business Server 2015](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md), [Deploy Persistent Chat Server in Skype for Business Server 2015](../../deploy/deploy-persistent-chat-server/deploy-persistent-chat-server.md), and [Manage Persistent Chat Server in Skype for Business Server 2015](../../manage/persistent-chat/persistent-chat.md).</span></span>