---
title: 常設チャット アドイン
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 3/27/2015
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.PersistentChatAddin
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 66124a70-67e8-4bda-9da5-8ab13afccf49
description: 永続的なチャット ルームの Url に関連付けるには、永続的なチャット ページの追加のセクションを使用できます。 これらの URL は、チャット ルームにいるクライアントの会話拡張機能ウィンドウに表示されます。 管理者が登録済みアドインの一覧にアドインを追加し、チャット ルームのマネージャー/作成者が登録済みアドインの 1 つにルームを関連付けると、ユーザーはクライアントでこのアップグレードを表示できるようになります。
ms.openlocfilehash: 4e2ec24b9cd6e47391a0e56a6696c622afec25ad
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/24/2018
ms.locfileid: "21006879"
---
# <a name="persistent-chat-add-in"></a><span data-ttu-id="851f6-105">常設チャット アドイン</span><span class="sxs-lookup"><span data-stu-id="851f6-105">Persistent Chat Add-in</span></span>
 
<span data-ttu-id="851f6-106">永続的なチャット ルームの Url に関連付けるには、**永続的なチャット**ページの**追加の**セクションを使用できます。</span><span class="sxs-lookup"><span data-stu-id="851f6-106">You can use the **Add-in** section of the **Persistent Chat** page to associate URLs with Persistent Chat rooms.</span></span> <span data-ttu-id="851f6-107">これらの URL は、チャット ルームにいるクライアントの会話拡張機能ウィンドウに表示されます。</span><span class="sxs-lookup"><span data-stu-id="851f6-107">These URLs appear in the client in the chat room in the conversation extensibility pane.</span></span> <span data-ttu-id="851f6-108">管理者が登録済みアドインの一覧にアドインを追加し、チャット ルームのマネージャー/作成者が登録済みアドインの 1 つにルームを関連付けると、ユーザーはクライアントでこのアップグレードを表示できるようになります。</span><span class="sxs-lookup"><span data-stu-id="851f6-108">An administrator must add Add-ins to the list of registered add-ins, and chat room managers/Creators must associate rooms with one of the registered add-ins before users can see this upgrade in their client.</span></span>
  
<span data-ttu-id="851f6-109">アドインは、ルーム内でのエクスペリエンスを拡張するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="851f6-109">Add-ins are used to extend the in-room experience.</span></span> <span data-ttu-id="851f6-110">一般的なアドインでは、株価情報は、チャット ルームがポストされ、拡張機能のウィンドウで株価履歴を表示しますを傍受した Silverlight アプリケーションを指す URL をなどがあります。</span><span class="sxs-lookup"><span data-stu-id="851f6-110">A typical add-in might include a URL pointing to a Silverlight application that intercepts when a stock ticker is posted to a chat room, and shows the stock history in the extensibility pane.</span></span> <span data-ttu-id="851f6-111">チャット ルームに OneNote 2013 の URL をアドインとして埋め込んで、"優先事項" や "今日のトピック" などの共有コンテキストを組み込むこともできます。</span><span class="sxs-lookup"><span data-stu-id="851f6-111">Other examples include embedding a OneNote 2013 URL in the chat room as an add-in to include some shared context, such as "Top of mind" or "Topic of the day."</span></span>
  
<span data-ttu-id="851f6-112">永続的なチャット ルームのアドインを作成するには、[ビジネス サーバー 2015 の Skype での永続的なチャット ルームの設定 - アドイン](../../manage/persistent-chat/configure-add-ins.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="851f6-112">To create Add-ins for Persistent Chat rooms, see [Configure add-ins for Persistent Chat rooms in Skype for Business Server 2015](../../manage/persistent-chat/configure-add-ins.md).</span></span> <span data-ttu-id="851f6-113">永続的なチャットの管理者は、コントロール パネルまたは Windows PowerShell コマンドレットを使用してアドインを作成します。</span><span class="sxs-lookup"><span data-stu-id="851f6-113">If you are a Persistent Chat Administrator, you can create add-ins by using the control panel or Windows PowerShell cmdlets.</span></span>
  
## <a name="tasks-that-you-can-perform"></a><span data-ttu-id="851f6-114">実行できるタスク</span><span class="sxs-lookup"><span data-stu-id="851f6-114">Tasks that you can perform</span></span>

<span data-ttu-id="851f6-115">[**アドイン**] ページでは、次のタスクを実行できます。</span><span class="sxs-lookup"><span data-stu-id="851f6-115">You can perform the following tasks on the **Add-in** page:</span></span>
  
- [<span data-ttu-id="851f6-116">Skype for Business Server 2015 での常設チャット ルームのアドインの構成</span><span class="sxs-lookup"><span data-stu-id="851f6-116">Configure add-ins for Persistent Chat rooms in Skype for Business Server 2015</span></span>](../../manage/persistent-chat/configure-add-ins.md)
    
## <a name="to-configure-add-ins-for-chat-rooms"></a><span data-ttu-id="851f6-117">チャット ルームのアドインを構成するには</span><span class="sxs-lookup"><span data-stu-id="851f6-117">To configure Add-ins for chat rooms</span></span>

<span data-ttu-id="851f6-118">以下は、ページ上のメニュー、コマンド、フィールド、およびプロパティについての説明です。</span><span class="sxs-lookup"><span data-stu-id="851f6-118">The following lists describe the menus, command, fields, and properties on the page.</span></span>
  
1. <span data-ttu-id="851f6-119">CsPersistentChatAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="851f6-119">From a user account that is assigned to the CsPersistentChatAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="851f6-120">**[スタート**] メニューから、Skype ビジネス サーバーのコントロール パネルのまたはブラウザー ウィンドウを開きし、管理 URL を入力します。</span><span class="sxs-lookup"><span data-stu-id="851f6-120">From the **Start** menu, select the Skype for Business Server Control Panel or open a browser window, and then enter the Admin URL.</span></span> <span data-ttu-id="851f6-121">コントロール パネルを起動するために使用できるさまざまな方法についての詳細は、[オープンの Lync Server 管理ツール](http://technet.microsoft.com/library/8c58de94-9e0a-4368-9e14-9afcaa1142d0.aspx)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="851f6-121">For details about the different methods that you can use to start the control panel, see [Open Lync Server Administrative Tools](http://technet.microsoft.com/library/8c58de94-9e0a-4368-9e14-9afcaa1142d0.aspx).</span></span>
    
3. <span data-ttu-id="851f6-122">左側のナビゲーション バーで [**常設チャット**] をクリックして、[**アドイン**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="851f6-122">In the left navigation bar, click **Persistent Chat**, and then click **Add-in**.</span></span>
    
    <span data-ttu-id="851f6-123">複数の永続的なチャット サーバー プールの展開には、ドロップ ダウン リストから適切なプールを選択します。</span><span class="sxs-lookup"><span data-stu-id="851f6-123">For multiple Persistent Chat Server pool deployments, select the appropriate pool from the drop-down list.</span></span>
    
4. <span data-ttu-id="851f6-124">[**アドイン**] ページで、[**新規**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="851f6-124">On the **Add-in** page, click **New**.</span></span>
    
5. <span data-ttu-id="851f6-125">[**サービスの選択**] では、アドインを作成する必要がある永続的なチャット サーバー プールに対応するサービスを選択します。</span><span class="sxs-lookup"><span data-stu-id="851f6-125">In **Select a Service**, select the service corresponding to the Persistent Chat Server pool where you need to create the Add-in.</span></span> <span data-ttu-id="851f6-126">アドインは、プール間で移動したり、異なるプール間で共有したりできません。</span><span class="sxs-lookup"><span data-stu-id="851f6-126">Add-ins cannot be moved from one pool to another or shared between different pools.</span></span>
    
6. <span data-ttu-id="851f6-127">[**新しいアドイン**] で、次の操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="851f6-127">In **New Add-in**, do the following:</span></span>
    
  - <span data-ttu-id="851f6-128">[**名前**] に、新しいアドインの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="851f6-128">In **Name**, specify a name for the new add-in.</span></span>
    
  - <span data-ttu-id="851f6-p107">[**URL**] に、アドインに関連付ける URL を指定します。URL には、http および https プロトコルのみを使用できます。</span><span class="sxs-lookup"><span data-stu-id="851f6-p107">In **URL**, specify the URL to be associated with the add-in. URLs are limited to http and https protocols.</span></span>
    
7. <span data-ttu-id="851f6-131">[**コミット**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="851f6-131">Click **Commit**.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="851f6-132">関連項目</span><span class="sxs-lookup"><span data-stu-id="851f6-132">See also</span></span>

<span data-ttu-id="851f6-133">持続チャット サーバーで永続的なチャット サーバーの機能と機能に関する詳細は、[ビジネス サーバー 2015 の Skype での永続的なチャット サーバーの計画](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md)、[ビジネス サーバー 2015 の Skype で永続的なチャット サーバーを展開](../../deploy/deploy-persistent-chat-server/deploy-persistent-chat-server.md)、および管理を[参照してください。ビジネス サーバー 2015 の Skype で](../../manage/persistent-chat/persistent-chat.md)。</span><span class="sxs-lookup"><span data-stu-id="851f6-133">For details about Persistent Chat Server features and capabilities, see [Plan for Persistent Chat Server in Skype for Business Server 2015](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md), [Deploy Persistent Chat Server in Skype for Business Server 2015](../../deploy/deploy-persistent-chat-server/deploy-persistent-chat-server.md), and [Manage Persistent Chat Server in Skype for Business Server 2015](../../manage/persistent-chat/persistent-chat.md).</span></span>
  

