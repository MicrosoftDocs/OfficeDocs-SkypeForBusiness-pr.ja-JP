---
title: Skype for Business Server 2015 での常設チャット サーバーオプションの構成
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/28/2016
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 19ced8de-8867-4152-b38a-891f3bc2a5ea
description: '概要: Skype for Business Server 2015 のグローバル レベル、サイト レベル、またはプール レベルで常設チャット サーバー オプションを構成する方法について説明します。'
ms.openlocfilehash: 9c0b6d5e03b9bc4f7d955ea0dae3e1c45b14ada3
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49802127"
---
# <a name="configure-persistent-chat-server-options-in-skype-for-business-server-2015"></a><span data-ttu-id="62134-103">Skype for Business Server 2015 での常設チャット サーバーオプションの構成</span><span class="sxs-lookup"><span data-stu-id="62134-103">Configure Persistent Chat Server options in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="62134-104">**概要:** Skype for Business Server 2015 のグローバル レベル、サイト レベル、またはプール レベルで常設チャット サーバー のオプションを構成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="62134-104">**Summary:** Learn how to configure Persistent Chat Server options at the global, site, or pool level in Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="62134-105">常設チャット サーバーには、グローバル、サイト内のすべてのプール、またはサイト内の特定のプールに適用できる複数のオプションを指定できます。</span><span class="sxs-lookup"><span data-stu-id="62134-105">You can specify several options for Persistent Chat Server that can be applied globally, to all pools within a site, or to a specific pool within a site.</span></span> <span data-ttu-id="62134-106">常設チャット サーバーのオプションは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="62134-106">Persistent Chat server options include the following:</span></span> 
  
- <span data-ttu-id="62134-107">既定のチャット履歴。</span><span class="sxs-lookup"><span data-stu-id="62134-107">Default Chat History.</span></span> <span data-ttu-id="62134-108">最初の要求時に各チャット ルームで使用可能なチャット メッセージの数。</span><span class="sxs-lookup"><span data-stu-id="62134-108">The number of chat messages that are available for each chat room upon first request.</span></span> <span data-ttu-id="62134-109">グローバルな既定値は 30 のチャット メッセージです。</span><span class="sxs-lookup"><span data-stu-id="62134-109">The global default is 30 chat messages.</span></span> 
    
- <span data-ttu-id="62134-110">最大ファイル サイズ。</span><span class="sxs-lookup"><span data-stu-id="62134-110">Maximum File Size.</span></span> <span data-ttu-id="62134-111">ルームにアップロードまたはルームからダウンロードできるファイルの最大サイズ。</span><span class="sxs-lookup"><span data-stu-id="62134-111">The maximum size of a file that can be uploaded to or downloaded from a room.</span></span> <span data-ttu-id="62134-112">グローバルの既定値は 20 MB です。</span><span class="sxs-lookup"><span data-stu-id="62134-112">The global default is 20MB.</span></span>
    
- <span data-ttu-id="62134-113">参加者の更新制限。</span><span class="sxs-lookup"><span data-stu-id="62134-113">Participant Update Limit.</span></span> <span data-ttu-id="62134-114">常設チャットが名簿の更新を送信する特定のチャット ルームの参加者の最大数。</span><span class="sxs-lookup"><span data-stu-id="62134-114">The maximum number of participants in a given chat room for which Persistent Chat will send roster updates.</span></span> <span data-ttu-id="62134-115">グローバルの既定値は 75 です。</span><span class="sxs-lookup"><span data-stu-id="62134-115">The global default is 75.</span></span>
    
- <span data-ttu-id="62134-116">ルーム管理 URL。</span><span class="sxs-lookup"><span data-stu-id="62134-116">Room Management URL.</span></span> <span data-ttu-id="62134-117">カスタム チャット ルーム管理に使用する URL。</span><span class="sxs-lookup"><span data-stu-id="62134-117">The URL used for custom chat room management.</span></span> <span data-ttu-id="62134-118">この設定では、カスタム のルーム管理ソリューションを使用できます。</span><span class="sxs-lookup"><span data-stu-id="62134-118">The setting allows the use of a custom room management solution.</span></span> 
   
> [!NOTE] 
> <span data-ttu-id="62134-119">常設チャットは Skype for Business Server 2015 で使用できますが、Skype for Business Server 2019 ではサポートされなくなりました。</span><span class="sxs-lookup"><span data-stu-id="62134-119">Persistent chat is available in Skype for Business Server 2015 but is no longer supported in Skype for Business Server 2019.</span></span> <span data-ttu-id="62134-120">Teams でも同じ機能を使用できます。</span><span class="sxs-lookup"><span data-stu-id="62134-120">The same functionality is available in Teams.</span></span> <span data-ttu-id="62134-121">詳細については、「Microsoft Teams のアップグレード [の開始」を参照してください](/microsoftteams/upgrade-start-here)。</span><span class="sxs-lookup"><span data-stu-id="62134-121">For more information, see [Getting started with your Microsoft Teams upgrade](/microsoftteams/upgrade-start-here).</span></span> <span data-ttu-id="62134-122">常設チャットを使用する必要がある場合は、この機能を必要とするユーザーを Teams に移行するか、Skype for Business Server 2015 を引き続き使用するかのどちらかを選択できます。</span><span class="sxs-lookup"><span data-stu-id="62134-122">If you need to use Persistent chat, your choices are to either migrate users requiring this functionality to Teams, or to continue using Skype for Business Server 2015.</span></span>
 
## <a name="configure-persistent-chat-server-global-options"></a><span data-ttu-id="62134-123">常設チャット サーバーのグローバル オプションを構成する</span><span class="sxs-lookup"><span data-stu-id="62134-123">Configure Persistent Chat Server global options</span></span>

<span data-ttu-id="62134-124">常設チャット サーバーのグローバル オプションを構成するには:</span><span class="sxs-lookup"><span data-stu-id="62134-124">To configure Persistent Chat Server global options:</span></span>
  
1. <span data-ttu-id="62134-125">CsPersistentChatAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="62134-125">From a user account that is assigned to the CsPersistentChatAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="62134-126">[スタート **] メニューから** Skype for Business Server コントロール パネルを選択するか、ブラウザー ウィンドウを開いて管理 URL を入力します。</span><span class="sxs-lookup"><span data-stu-id="62134-126">From the **Start** menu, select the Skype for Business Server Control Panel or open a browser window, and then enter the Admin URL.</span></span>
    
3. <span data-ttu-id="62134-127">左側のナビゲーション バーで [**常設チャット**] をクリックし、[**常設チャットの構成**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="62134-127">In the left navigation bar, click **Persistent Chat**, and then click **Persistent Chat Configuration**.</span></span>
    
4. <span data-ttu-id="62134-128">[常設 **チャットの構成] ページで** 、[新規] **をクリック** し、[サイトの構成] **をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="62134-128">On the **Persistent Chat Configuration** page, click **New,** and then click **Site configuration**.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="62134-129">サイトに展開されている常設チャット サーバー のすべてのプールに構成を適用する場合は、このオプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="62134-129">Choose this option if you want the configuration to be applied to all Persistent Chat Server pools deployed in the site.</span></span> <span data-ttu-id="62134-130">構成 **を特定** の常設チャット サーバー プールに適用する場合は、[プールの構成] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="62134-130">Click **Pool Configuration** if you want the configuration to be applied to a specific Persistent Chat Server pool.</span></span>
  
5. <span data-ttu-id="62134-131">[ **サイトの選択]** で、常設チャット サーバー サイト構成用に構成するサイトを選択します。</span><span class="sxs-lookup"><span data-stu-id="62134-131">In **Select a Site**, select the site to be configured for the Persistent Chat Server site configuration.</span></span>
    
6. <span data-ttu-id="62134-132">[**新規 常設チャットの構成**] で、次の操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="62134-132">In **New Persistent Chat Configuration**, do the following:</span></span>
    
   - <span data-ttu-id="62134-p108">[**名前**] で、新しい構成設定の名前を指定します。既定では、サイト名は既に存在します。</span><span class="sxs-lookup"><span data-stu-id="62134-p108">In **Name**, specify a name for the new configuration settings. By default, the site name already exists.</span></span>
    
   - <span data-ttu-id="62134-p109">[**Default chat history**] で、最初の要求時にチャット ルームごとに処理されるチャット メッセージ数を定義します。既定値は 30 で、これはグローバルな既定値です。管理者はカテゴリごとにチャット履歴を無効にできます。</span><span class="sxs-lookup"><span data-stu-id="62134-p109">In **Default chat history**, define the number of chat messages that will be processed for each room upon first request. By default, the number is 30. This is the global default, and administrators can disable chat history per category.</span></span>
    
     > [!IMPORTANT]
     > <span data-ttu-id="62134-138">常設チャット サーバーは、これらのメッセージをメモリにキャッシュします。したがって、この数を増やすと、キャッシュされるメッセージの数が増える可能性があります。</span><span class="sxs-lookup"><span data-stu-id="62134-138">Persistent Chat Server will cache these messages in memory, so if you increase this number, more messages will be cached.</span></span> <span data-ttu-id="62134-139">履歴コンテンツには、検索を使用していつでもアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="62134-139">You can always access historical content by search.</span></span> <span data-ttu-id="62134-140">既定値は、チャット ルームに接続したときに最初に表示されるメッセージの最大数を規定しているにすぎません。</span><span class="sxs-lookup"><span data-stu-id="62134-140">The default number simply determines the maximum number of messages that you initially see when connecting to a chat room.</span></span> 
  
   - <span data-ttu-id="62134-p111">[**最大ファイル サイズ (KB)**] で、各チャット履歴の最大ファイル サイズを選択します。既定値は 20 MB (20,000 KB) です。これは、システム内のチャット ルーム (対応する [**分類**] 設定でファイルのアップロードが有効化されているチャット ルーム) にアップロードできるファイルの最大サイズです。</span><span class="sxs-lookup"><span data-stu-id="62134-p111">In **Maximum file size (KB)**, select the maximum file size of each chat history. By default, the number is 20 MB (20,000 KB). This is the maximum size for a file that can be uploaded to any chat room in the system (for which file uploads are enabled by its corresponding **Category** setting).</span></span>
    
   - <span data-ttu-id="62134-144">[**参加者の更新制限**] で、参加者の更新の制限値を選択します。</span><span class="sxs-lookup"><span data-stu-id="62134-144">In **Participant update limit**, select the limit for participant updates.</span></span> <span data-ttu-id="62134-145">常設チャット サーバーは、接続されているユーザーの数がこの数に達するまで、参加者全員に名簿情報 (チャット ルームに接続されているユーザー) を送信します。</span><span class="sxs-lookup"><span data-stu-id="62134-145">Persistent Chat Server sends roster information (who is connected to a chat room) to all participants until the number of connected users reaches this number.</span></span> <span data-ttu-id="62134-146">既定値は 75 です。</span><span class="sxs-lookup"><span data-stu-id="62134-146">By default, the number is 75.</span></span> <span data-ttu-id="62134-147">この制限は、常設チャット サーバーがルームに存在するユーザーに関する名簿の更新の送信を停止する特定のルームの参加者の最大数を示します。</span><span class="sxs-lookup"><span data-stu-id="62134-147">This limit indicates the maximum number of participants in a given room beyond which Persistent Chat Server stops sending roster updates to connected clients about who is present in the room.</span></span>
    
   - <span data-ttu-id="62134-148">(省略可能)[ **ルームの管理 URL] で**、ルーム管理 URL を選択します。</span><span class="sxs-lookup"><span data-stu-id="62134-148">(Optional.) In **Room management URL**, select the room management URL.</span></span> <span data-ttu-id="62134-149">これは Web をベースにした、ルームのカスタム管理用 URL です。</span><span class="sxs-lookup"><span data-stu-id="62134-149">This is the URL for a web-based custom room management.</span></span> <span data-ttu-id="62134-150">ルームの管理をカスタマイズする必要はありません。既定の設定を使用する場合は、このオプションを空白のままにします。</span><span class="sxs-lookup"><span data-stu-id="62134-150">If you don't need to customize room management, and you simply use the default setting, leave this option blank.</span></span> <span data-ttu-id="62134-151">URL を設定すると、内部と外部の両方のルームの管理 URL として適用されます。</span><span class="sxs-lookup"><span data-stu-id="62134-151">After the URL is set, it is applied as both the internal and external room management URL.</span></span>
    
     <span data-ttu-id="62134-152">ルームの作成エクスペリエンスをカスタマイズし、特定のビジネス ワークフローを含める場合は、常設チャット サーバー ソフトウェア開発キット (SDK) を使用してカスタム ルーム管理ソリューションを構築し、どこかでホストし、URL をここに置きます。</span><span class="sxs-lookup"><span data-stu-id="62134-152">If you want to customize your room creation experience and include your specific business workflow, you can build a custom room management solution by using the Persistent Chat Server Software Development Kit (SDK), host it somewhere, and put the URL here.</span></span> <span data-ttu-id="62134-153">ユーザーがチャット ルームを表示または作成するときにカスタム チャット ルーム管理ソリューションを使用するよう、この URL がクライアントに伝えられます。</span><span class="sxs-lookup"><span data-stu-id="62134-153">This URL is sent down to the client, so that when a user tries to view or create a room, he or she is directed to your custom room management solution.</span></span>
    
7. <span data-ttu-id="62134-154">[**確定**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="62134-154">Click **Commit**.</span></span>
    
## <a name="configure-options-for-a-specific-persistent-chat-server-pool"></a><span data-ttu-id="62134-155">特定の常設チャット サーバー プールのオプションを構成する</span><span class="sxs-lookup"><span data-stu-id="62134-155">Configure options for a specific Persistent Chat Server pool</span></span>

<span data-ttu-id="62134-156">特定の常設チャット サーバー プールのオプションを構成する。</span><span class="sxs-lookup"><span data-stu-id="62134-156">To configure options for a specific Persistent Chat Server pool.</span></span>
  
1. <span data-ttu-id="62134-157">CsPersistentChatAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="62134-157">From a user account that is assigned to the CsPersistentChatAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="62134-158">[スタート **] メニュー** から Skype for Business Server コントロール パネルを選択するか、ブラウザー ウィンドウを開いて管理 URL を入力します。</span><span class="sxs-lookup"><span data-stu-id="62134-158">From the **Start** menu, select the Skype for Business Server Control Panel, or open a browser window, and then enter the Admin URL.</span></span>
    
3. <span data-ttu-id="62134-159">左側のナビゲーション バーで [**常設チャット**] をクリックし、[**常設チャットの構成**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="62134-159">In the left navigation bar, click **Persistent Chat**, and then click **Persistent Chat Configuration**.</span></span>
    
4. <span data-ttu-id="62134-160">[**常設チャットの構成**] ページで、[**新規**] をクリックし、[**プール構成**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="62134-160">On the **Persistent Chat Configuration** page, click **New**, and then click **Pool configuration**.</span></span>
    
5. <span data-ttu-id="62134-161">[ **サービスの選択]** で、構成する常設チャット サーバー プールに関連付けられているサービスを選択します。</span><span class="sxs-lookup"><span data-stu-id="62134-161">In **Select a Service**, select the service associated with the Persistent Chat Server pool to be configured.</span></span>
    
6. <span data-ttu-id="62134-162">[**新規 常設チャットの構成**] で、次の操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="62134-162">In **New Persistent Chat Configuration**, do the following:</span></span>
    
   - <span data-ttu-id="62134-p115">[**名前**] で、新しい構成設定の名前を指定します。既定では、サイト プール名は既に存在します。</span><span class="sxs-lookup"><span data-stu-id="62134-p115">In **Name**, specify a name for the new configuration settings. By default, the site pool name already exists.</span></span>
    
   - <span data-ttu-id="62134-p116">[**Default chat history**] で、最初の要求時にチャット ルームごとに処理されるチャット メッセージ数を定義します。既定値は 30 で、これはグローバルな既定値です。管理者はカテゴリごとにチャット履歴を無効にできます。</span><span class="sxs-lookup"><span data-stu-id="62134-p116">In **Default chat history**, define the number of chat messages that will be processed for each room upon first request. By default, the number is 30. This is the global default, and administrators can disable chat history per category.</span></span>
    
     > [!IMPORTANT]
     > <span data-ttu-id="62134-168">常設チャット サーバーは、これらのメッセージをメモリにキャッシュします。したがって、この数を増やすと、キャッシュされるメッセージの数が増える可能性があります。</span><span class="sxs-lookup"><span data-stu-id="62134-168">Persistent Chat Server will cache these messages in memory, so if you increase this number, more messages will be cached.</span></span> <span data-ttu-id="62134-169">履歴コンテンツには、検索を使用していつでもアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="62134-169">You can always access historical content by search.</span></span> <span data-ttu-id="62134-170">既定値は、チャット ルームに接続したときに最初に表示されるメッセージの最大数を規定しているにすぎません。</span><span class="sxs-lookup"><span data-stu-id="62134-170">The default number simply determines the maximum number of messages that you initially see when connecting to a chat room.</span></span> 
  
   - <span data-ttu-id="62134-p118">[**最大ファイル サイズ (KB)**] で、各チャット履歴の最大ファイル サイズを選択します。既定値は 20 MB (20,000 KB) です。これは、システム内のチャット ルーム (対応する [**分類**] 設定でファイルのアップロードが有効化されているチャット ルーム) にアップロードできるファイルの最大サイズです。</span><span class="sxs-lookup"><span data-stu-id="62134-p118">In **Maximum file size (KB)**, select the maximum file size of each chat history. By default, the number is 20 MB (20,000 KB). This is the maximum size for a file that can be uploaded to any chat room in the system (for which file uploads are enabled by its corresponding **Category** setting).</span></span>
    
   - <span data-ttu-id="62134-174">[**参加者の更新制限**] で、参加者の更新の制限値を選択します。</span><span class="sxs-lookup"><span data-stu-id="62134-174">In **Participant update limit**, select the limit for participant updates.</span></span> <span data-ttu-id="62134-175">常設チャット サーバーは、接続されているユーザーの数がこの数に達するまで、参加者全員に名簿情報 (チャット ルームに接続されているユーザー) を送信します。</span><span class="sxs-lookup"><span data-stu-id="62134-175">Persistent Chat Server sends roster information (who is connected to a chat room) to all participants until the number of connected users reaches this number.</span></span> <span data-ttu-id="62134-176">既定値は 75 です。</span><span class="sxs-lookup"><span data-stu-id="62134-176">By default, the number is 75.</span></span> <span data-ttu-id="62134-177">この制限は、常設チャット サーバーがルームに存在するユーザーに関する名簿の更新の送信を停止する特定のルームの参加者の最大数を示します。</span><span class="sxs-lookup"><span data-stu-id="62134-177">This limit indicates the maximum number of participants in a given room beyond which Persistent Chat Server stops sending roster updates to connected clients about who is present in the room.</span></span>
    
   - <span data-ttu-id="62134-178">[**ルームの管理 URL**] で、ルーム管理 URL を選択します。</span><span class="sxs-lookup"><span data-stu-id="62134-178">In **Room management URL**, select the room management URL.</span></span> <span data-ttu-id="62134-179">これは Web ベースのチャット ルーム管理用の URL です。</span><span class="sxs-lookup"><span data-stu-id="62134-179">This is the URL for a web-based room management deployment.</span></span> <span data-ttu-id="62134-180">ルームの管理をカスタマイズする必要はありません。既定の設定を使用する場合は、このオプションを空白のままにします。</span><span class="sxs-lookup"><span data-stu-id="62134-180">If you don't need to customize room management, and you simply use the default setting, leave this option blank.</span></span>
    
     <span data-ttu-id="62134-181">ルームの作成エクスペリエンスをカスタマイズし、特定のビジネス ワークフローを含める場合は、常設チャット サーバー ソフトウェア開発キット (SDK) を使用してカスタム ルーム管理ソリューションを構築し、どこかでホストし、URL をここに置きます。</span><span class="sxs-lookup"><span data-stu-id="62134-181">If you want to customize your room creation experience and include your specific business workflow, you can build a custom room management solution by using the Persistent Chat Server Software Development Kit (SDK), host it somewhere, and put the URL here.</span></span> <span data-ttu-id="62134-182">ユーザーがチャット ルームを表示または作成するときにカスタム チャット ルーム管理ソリューションを使用するよう、この URL がクライアントに伝えられます。</span><span class="sxs-lookup"><span data-stu-id="62134-182">This URL is sent down to the client so that when a user tries to view/create a room, he or she is directed to your custom room management solution.</span></span>
    
7. <span data-ttu-id="62134-183">[**確定**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="62134-183">Click **Commit**.</span></span>
    

