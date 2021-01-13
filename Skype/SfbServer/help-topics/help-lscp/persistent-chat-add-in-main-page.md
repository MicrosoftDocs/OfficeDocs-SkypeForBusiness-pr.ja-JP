---
title: 常設チャット アドイン メイン ページ
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
- ms.lync.lscp.PersistentChatAddinMain
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 0c0ecf64-258d-4b43-8fac-fa5ffa4e7646
description: '[常設チャット] ページの [アドイン] セクションを使用して、URL を常設チャット ルームに関連付けできます。 これらの URL は、チャット ルームの会話機能拡張ウィンドウのクライアントに表示されます。 管理者は登録済みアドインの一覧にアドインを追加する必要があります。チャット ルームのマネージャー/作成者は、ユーザーがクライアントでこのアップグレードを確認する前に、登録済みのアドインの 1 つにルームを関連付ける必要があります。'
ms.openlocfilehash: ee747e12b4a6209d831588e68533531b0a7d95ff
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49803797"
---
# <a name="persistent-chat-add-in-main-page"></a><span data-ttu-id="6d2d1-105">常設チャット アドイン メイン ページ</span><span class="sxs-lookup"><span data-stu-id="6d2d1-105">Persistent Chat Add-in Main Page</span></span>

<span data-ttu-id="6d2d1-106">[常設チャット] **ページの** [アドイン] セクション **を** 使用して、URL を常設チャット ルームに関連付けできます。</span><span class="sxs-lookup"><span data-stu-id="6d2d1-106">You can use the **Add-in** section of the **Persistent Chat** page to associate URLs with Persistent Chat rooms.</span></span> <span data-ttu-id="6d2d1-107">これらの URL は、チャット ルームの会話機能拡張ウィンドウのクライアントに表示されます。</span><span class="sxs-lookup"><span data-stu-id="6d2d1-107">These URLs appear in the client in the chat room in the conversation extensibility pane.</span></span> <span data-ttu-id="6d2d1-108">管理者は登録済みアドインの一覧にアドインを追加する必要があります。チャット ルームのマネージャー/作成者は、ユーザーがクライアントでこのアップグレードを確認する前に、登録済みのアドインの 1 つにルームを関連付ける必要があります。</span><span class="sxs-lookup"><span data-stu-id="6d2d1-108">An administrator must add Add-ins to the list of registered add-ins, and chat room managers/Creators must associate rooms with one of the registered add-ins before users can see this upgrade in their client.</span></span>

<span data-ttu-id="6d2d1-109">アドインは、ルーム内でのエクスペリエンスを拡張するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="6d2d1-109">Add-ins are used to extend the in-room experience.</span></span> <span data-ttu-id="6d2d1-110">一般的なアドインには、株価情報がチャット ルームに投稿され、拡張ウィンドウに株価履歴が表示される Silverlight アプリケーションを指す URL が含まれる場合があります。</span><span class="sxs-lookup"><span data-stu-id="6d2d1-110">A typical add-in might include a URL pointing to a Silverlight application that intercepts when a stock ticker is posted to a chat room, and shows the stock history in the extensibility pane.</span></span> <span data-ttu-id="6d2d1-111">また、OneNote 2013 の URL をアドインとしてチャット ルームに組み込み、"優先事項" や "今日のトピック" などの共有コンテキストを表示することもできます。</span><span class="sxs-lookup"><span data-stu-id="6d2d1-111">Other examples include embedding a OneNote 2013 URL in the chat room as an add-in to include some shared context, such as "Top of mind" or "Topic of the day."</span></span>

<span data-ttu-id="6d2d1-112">常設チャット ルーム用のアドインを作成するには [、「Skype for Business Server 2015](../../manage/persistent-chat/configure-add-ins.md)で常設チャット ルーム用のアドインを構成する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6d2d1-112">To create Add-ins for Persistent Chat rooms, see [Configure add-ins for Persistent Chat rooms in Skype for Business Server 2015](../../manage/persistent-chat/configure-add-ins.md).</span></span> <span data-ttu-id="6d2d1-113">常設チャット管理者の場合は、コントロール パネルまたはカスタム コマンドレットを使用してアドインWindows PowerShellできます。</span><span class="sxs-lookup"><span data-stu-id="6d2d1-113">If you are a Persistent Chat Administrator, you can create add-ins by using the control panel or Windows PowerShell cmdlets.</span></span>

## <a name="tasks-you-can-perform"></a><span data-ttu-id="6d2d1-114">実行できるタスク</span><span class="sxs-lookup"><span data-stu-id="6d2d1-114">Tasks you can perform</span></span>

<span data-ttu-id="6d2d1-115">[**アドイン**] ページでは、次のタスクを実行できます。</span><span class="sxs-lookup"><span data-stu-id="6d2d1-115">You can perform the following tasks on the **Add-in** page:</span></span>

- [<span data-ttu-id="6d2d1-116">Skype for Business Server 2015 での常設チャット ルームのアドインの構成</span><span class="sxs-lookup"><span data-stu-id="6d2d1-116">Configure add-ins for Persistent Chat rooms in Skype for Business Server 2015</span></span>](../../manage/persistent-chat/configure-add-ins.md)

## <a name="to-configure-add-ins-for-chat-rooms"></a><span data-ttu-id="6d2d1-117">チャット ルームのアドインを構成するには</span><span class="sxs-lookup"><span data-stu-id="6d2d1-117">To configure Add-ins for chat rooms</span></span>

<span data-ttu-id="6d2d1-118">以下は、ページ上のメニュー、コマンド、フィールド、およびプロパティについての説明です。</span><span class="sxs-lookup"><span data-stu-id="6d2d1-118">The following lists describe the menus, command, fields, and properties on the page.</span></span>

1. <span data-ttu-id="6d2d1-119">CsPersistentChatAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="6d2d1-119">From a user account that is assigned to the CsPersistentChatAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2. <span data-ttu-id="6d2d1-120">[スタート **] メニューから** Skype for Business Server コントロール パネルを選択するか、ブラウザー ウィンドウを開いて管理 URL を入力します。</span><span class="sxs-lookup"><span data-stu-id="6d2d1-120">From the **Start** menu, select the Skype for Business Server Control Panel or open a browser window, and then enter the Admin URL.</span></span> <span data-ttu-id="6d2d1-121">コントロール パネルの起動に使用できるさまざまな方法の詳細については、「Lync Server 管理ツールを開く」 [を参照してください](https://technet.microsoft.com/library/8c58de94-9e0a-4368-9e14-9afcaa1142d0.aspx)。</span><span class="sxs-lookup"><span data-stu-id="6d2d1-121">For details about the different methods that you can use to start control panel, see [Open Lync Server Administrative Tools](https://technet.microsoft.com/library/8c58de94-9e0a-4368-9e14-9afcaa1142d0.aspx).</span></span>

3. <span data-ttu-id="6d2d1-122">左側のナビゲーション バーで [**常設チャット**] をクリックして、[**アドイン**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6d2d1-122">In the left navigation bar, click **Persistent Chat**, and then click **Add-in**.</span></span>

    <span data-ttu-id="6d2d1-123">複数の常設チャット サーバー プール展開の場合は、ドロップダウン リストから適切なプールを選択します。</span><span class="sxs-lookup"><span data-stu-id="6d2d1-123">For multiple Persistent Chat Server pool deployments, select the appropriate pool from the drop-down list.</span></span>

4. <span data-ttu-id="6d2d1-124">[**アドイン**] ページで、[**新規**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6d2d1-124">On the **Add-in** page, click **New**.</span></span>

5. <span data-ttu-id="6d2d1-125">[ **サービスの選択]** で、アドインを作成する必要がある常設チャット サーバー プールに対応するサービスを選択します。</span><span class="sxs-lookup"><span data-stu-id="6d2d1-125">In **Select a Service**, select the service corresponding to the Persistent Chat Server pool where you need to create the Add-in.</span></span> <span data-ttu-id="6d2d1-126">アドインをプール間で移動したり、複数のプールで共有したりすることはできません。</span><span class="sxs-lookup"><span data-stu-id="6d2d1-126">Add-ins cannot be moved from one pool to another or shared between different pools.</span></span>

6. <span data-ttu-id="6d2d1-127">[**新規 アドイン**] で、次の操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="6d2d1-127">In **New Add-in**, do the following:</span></span>

   - <span data-ttu-id="6d2d1-128">[**名前**] に、新しいアドインの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="6d2d1-128">In **Name**, specify a name for the new add-in.</span></span>

   - <span data-ttu-id="6d2d1-p107">[**URL**] で、アドインに関連付ける URL を指定します。URL には http および https プロトコルのみを使用できます。</span><span class="sxs-lookup"><span data-stu-id="6d2d1-p107">In **URL**, specify the URL to be associated with the add-in. URLs are limited to http and https protocols.</span></span>

7. <span data-ttu-id="6d2d1-131">[**確定**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6d2d1-131">Click **Commit**.</span></span>

## <a name="see-also"></a><span data-ttu-id="6d2d1-132">関連項目</span><span class="sxs-lookup"><span data-stu-id="6d2d1-132">See also</span></span>

<span data-ttu-id="6d2d1-133">常設チャット サーバーの機能の詳細については [、「Plan for Persistent Chat Server in Skype for Business Server 2015,](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md) [Deploy Persistent Chat Server in Skype for Business Server 2015,](../../deploy/deploy-persistent-chat-server/deploy-persistent-chat-server.md)and [Manage Persistent Chat Server in Skype for Business Server 2015」](../../manage/persistent-chat/persistent-chat.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6d2d1-133">For details about Persistent Chat Server features and capabilities, see [Plan for Persistent Chat Server in Skype for Business Server 2015](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md), [Deploy Persistent Chat Server in Skype for Business Server 2015](../../deploy/deploy-persistent-chat-server/deploy-persistent-chat-server.md), and [Manage Persistent Chat Server in Skype for Business Server 2015](../../manage/persistent-chat/persistent-chat.md).</span></span>


