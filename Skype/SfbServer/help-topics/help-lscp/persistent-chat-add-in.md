---
title: 常設チャット アドイン
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
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
description: '[常設チャット] ページの [アドイン] セクションを使って、Url を常設チャットルームに関連付けることができます。 これらの URL は、チャット ルームにいるクライアントの会話拡張機能ウィンドウに表示されます。 管理者が登録済みアドインの一覧にアドインを追加し、チャット ルームのマネージャー/作成者が登録済みアドインの 1 つにルームを関連付けると、ユーザーはクライアントでこのアップグレードを表示できるようになります。'
ms.openlocfilehash: 2122f07bb51167dbaea6eb7d0881443e1ff44575
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2020
ms.locfileid: "41822570"
---
# <a name="persistent-chat-add-in"></a><span data-ttu-id="857bc-105">常設チャット アドイン</span><span class="sxs-lookup"><span data-stu-id="857bc-105">Persistent Chat Add-in</span></span>

<span data-ttu-id="857bc-106">[**常設チャット**] ページの [**アドイン**] セクションを使って、url を常設チャットルームに関連付けることができます。</span><span class="sxs-lookup"><span data-stu-id="857bc-106">You can use the **Add-in** section of the **Persistent Chat** page to associate URLs with Persistent Chat rooms.</span></span> <span data-ttu-id="857bc-107">これらの URL は、チャット ルームにいるクライアントの会話拡張機能ウィンドウに表示されます。</span><span class="sxs-lookup"><span data-stu-id="857bc-107">These URLs appear in the client in the chat room in the conversation extensibility pane.</span></span> <span data-ttu-id="857bc-108">管理者が登録済みアドインの一覧にアドインを追加し、チャット ルームのマネージャー/作成者が登録済みアドインの 1 つにルームを関連付けると、ユーザーはクライアントでこのアップグレードを表示できるようになります。</span><span class="sxs-lookup"><span data-stu-id="857bc-108">An administrator must add Add-ins to the list of registered add-ins, and chat room managers/Creators must associate rooms with one of the registered add-ins before users can see this upgrade in their client.</span></span>

<span data-ttu-id="857bc-109">アドインは、ルーム内でのエクスペリエンスを拡張するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="857bc-109">Add-ins are used to extend the in-room experience.</span></span> <span data-ttu-id="857bc-110">一般的なアドインには、株式のティッカーがチャットルームに投稿されたときに受信する Silverlight アプリケーションを指す URL が含まれている場合があります。また、拡張機能ウィンドウには、株式履歴が表示されます。</span><span class="sxs-lookup"><span data-stu-id="857bc-110">A typical add-in might include a URL pointing to a Silverlight application that intercepts when a stock ticker is posted to a chat room, and shows the stock history in the extensibility pane.</span></span> <span data-ttu-id="857bc-111">チャット ルームに OneNote 2013 の URL をアドインとして埋め込んで、"優先事項" や "今日のトピック" などの共有コンテキストを組み込むこともできます。</span><span class="sxs-lookup"><span data-stu-id="857bc-111">Other examples include embedding a OneNote 2013 URL in the chat room as an add-in to include some shared context, such as "Top of mind" or "Topic of the day."</span></span>

<span data-ttu-id="857bc-112">常設チャットルーム用のアドインを作成するには、「 [Skype For Business Server 2015 の常設チャットルーム用のアドインを設定](../../manage/persistent-chat/configure-add-ins.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="857bc-112">To create Add-ins for Persistent Chat rooms, see [Configure add-ins for Persistent Chat rooms in Skype for Business Server 2015](../../manage/persistent-chat/configure-add-ins.md).</span></span> <span data-ttu-id="857bc-113">常設チャットの管理者である場合は、コントロールパネルまたは Windows PowerShell コマンドレットを使用してアドインを作成できます。</span><span class="sxs-lookup"><span data-stu-id="857bc-113">If you are a Persistent Chat Administrator, you can create add-ins by using the control panel or Windows PowerShell cmdlets.</span></span>

## <a name="tasks-that-you-can-perform"></a><span data-ttu-id="857bc-114">実行できるタスク</span><span class="sxs-lookup"><span data-stu-id="857bc-114">Tasks that you can perform</span></span>

<span data-ttu-id="857bc-115">[**アドイン**] ページでは、次のタスクを実行できます。</span><span class="sxs-lookup"><span data-stu-id="857bc-115">You can perform the following tasks on the **Add-in** page:</span></span>

- [<span data-ttu-id="857bc-116">Skype for Business Server 2015 での常設チャット ルームのアドインの構成</span><span class="sxs-lookup"><span data-stu-id="857bc-116">Configure add-ins for Persistent Chat rooms in Skype for Business Server 2015</span></span>](../../manage/persistent-chat/configure-add-ins.md)

## <a name="to-configure-add-ins-for-chat-rooms"></a><span data-ttu-id="857bc-117">チャット ルームのアドインを構成するには</span><span class="sxs-lookup"><span data-stu-id="857bc-117">To configure Add-ins for chat rooms</span></span>

<span data-ttu-id="857bc-118">以下は、ページ上のメニュー、コマンド、フィールド、およびプロパティについての説明です。</span><span class="sxs-lookup"><span data-stu-id="857bc-118">The following lists describe the menus, command, fields, and properties on the page.</span></span>

1. <span data-ttu-id="857bc-119">CsPersistentChatAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="857bc-119">From a user account that is assigned to the CsPersistentChatAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2. <span data-ttu-id="857bc-120">[**スタート**] メニューで、[Skype For business Server] コントロールパネルを選択するか、ブラウザーウィンドウを開き、管理 URL を入力します。</span><span class="sxs-lookup"><span data-stu-id="857bc-120">From the **Start** menu, select the Skype for Business Server Control Panel or open a browser window, and then enter the Admin URL.</span></span> <span data-ttu-id="857bc-121">コントロール パネルの起動に使用できるさまざまな方法の詳細については、「[Open Lync Server Administrative Tools](https://technet.microsoft.com/library/8c58de94-9e0a-4368-9e14-9afcaa1142d0.aspx)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="857bc-121">For details about the different methods that you can use to start the control panel, see [Open Lync Server Administrative Tools](https://technet.microsoft.com/library/8c58de94-9e0a-4368-9e14-9afcaa1142d0.aspx).</span></span>

3. <span data-ttu-id="857bc-122">左側のナビゲーション バーで [**常設チャット**] をクリックして、[**アドイン**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="857bc-122">In the left navigation bar, click **Persistent Chat**, and then click **Add-in**.</span></span>

    <span data-ttu-id="857bc-123">複数の常設チャットサーバープールの展開の場合、ドロップダウンリストから適切なプールを選択します。</span><span class="sxs-lookup"><span data-stu-id="857bc-123">For multiple Persistent Chat Server pool deployments, select the appropriate pool from the drop-down list.</span></span>

4. <span data-ttu-id="857bc-124">[**アドイン**] ページで、[**新規**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="857bc-124">On the **Add-in** page, click **New**.</span></span>

5. <span data-ttu-id="857bc-125">[**サービスの選択**] で、アドインを作成する必要がある常設チャットサーバープールに対応するサービスを選びます。</span><span class="sxs-lookup"><span data-stu-id="857bc-125">In **Select a Service**, select the service corresponding to the Persistent Chat Server pool where you need to create the Add-in.</span></span> <span data-ttu-id="857bc-126">アドインは、プール間で移動したり、異なるプール間で共有したりできません。</span><span class="sxs-lookup"><span data-stu-id="857bc-126">Add-ins cannot be moved from one pool to another or shared between different pools.</span></span>

6. <span data-ttu-id="857bc-127">[**新しいアドイン**] で、次の操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="857bc-127">In **New Add-in**, do the following:</span></span>

   - <span data-ttu-id="857bc-128">[**名前**] に、新しいアドインの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="857bc-128">In **Name**, specify a name for the new add-in.</span></span>

   - <span data-ttu-id="857bc-p107">[**URL**] に、アドインに関連付ける URL を指定します。URL には、http および https プロトコルのみを使用できます。</span><span class="sxs-lookup"><span data-stu-id="857bc-p107">In **URL**, specify the URL to be associated with the add-in. URLs are limited to http and https protocols.</span></span>

7. <span data-ttu-id="857bc-131">[**コミット**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="857bc-131">Click **Commit**.</span></span>

## <a name="see-also"></a><span data-ttu-id="857bc-132">関連項目</span><span class="sxs-lookup"><span data-stu-id="857bc-132">See also</span></span>

<span data-ttu-id="857bc-133">常設チャットサーバーの機能と機能について詳しくは、「skype [For Business server 2015 での常設チャットサーバーの計画](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md)」、「skype for business server [2015 で](../../deploy/deploy-persistent-chat-server/deploy-persistent-chat-server.md)の常設チャットサーバーの展開」、「 [skype for Business server 2015 での常設チャットサーバーの管理](../../manage/persistent-chat/persistent-chat.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="857bc-133">For details about Persistent Chat Server features and capabilities, see [Plan for Persistent Chat Server in Skype for Business Server 2015](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md), [Deploy Persistent Chat Server in Skype for Business Server 2015](../../deploy/deploy-persistent-chat-server/deploy-persistent-chat-server.md), and [Manage Persistent Chat Server in Skype for Business Server 2015](../../manage/persistent-chat/persistent-chat.md).</span></span>


