---
title: Skype for Business Server 2015 での常設チャット サーバー オプションの構成
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/28/2016
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 19ced8de-8867-4152-b38a-891f3bc2a5ea
description: '概要: Skype for Business Server 2015 のグローバル、サイト、またはプールレベルで常設チャットサーバーオプションを構成する方法について説明します。'
ms.openlocfilehash: 6305ba9a961248b24fe1a2fc28d5944efb6adeac
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2019
ms.locfileid: "34273869"
---
# <a name="configure-persistent-chat-server-options-in-skype-for-business-server-2015"></a><span data-ttu-id="64eea-103">Skype for Business Server 2015 での常設チャット サーバー オプションの構成</span><span class="sxs-lookup"><span data-stu-id="64eea-103">Configure Persistent Chat Server options in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="64eea-104">**概要:** Skype for Business Server 2015 のグローバル、サイト、またはプールレベルで常設チャットサーバーオプションを構成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="64eea-104">**Summary:** Learn how to configure Persistent Chat Server options at the global, site, or pool level in Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="64eea-105">グローバルに適用できる常設チャットサーバー、サイト内のすべてのプール、またはサイト内の特定のプールに、いくつかのオプションを指定できます。</span><span class="sxs-lookup"><span data-stu-id="64eea-105">You can specify several options for Persistent Chat Server that can be applied globally, to all pools within a site, or to a specific pool within a site.</span></span> <span data-ttu-id="64eea-106">常設チャット サーバーには以下のオプションがあります。</span><span class="sxs-lookup"><span data-stu-id="64eea-106">Persistent Chat server options include the following:</span></span> 
  
- <span data-ttu-id="64eea-107">[既定のチャット履歴]。</span><span class="sxs-lookup"><span data-stu-id="64eea-107">Default Chat History.</span></span> <span data-ttu-id="64eea-108">最初の要求時に各チャット ルームで使用できるチャット メッセージ数です。</span><span class="sxs-lookup"><span data-stu-id="64eea-108">The number of chat messages that are available for each chat room upon first request.</span></span> <span data-ttu-id="64eea-109">グローバルなチャット メッセージ数の既定値は 30 です。</span><span class="sxs-lookup"><span data-stu-id="64eea-109">The global default is 30 chat messages.</span></span> 
    
- <span data-ttu-id="64eea-p103">[最大ファイル サイズ]。ルームへのアップロードまたはルームからのダウンロードが可能なファイルの最大サイズです。グローバルな既定値は 20 MB です。</span><span class="sxs-lookup"><span data-stu-id="64eea-p103">Maximum File Size. The maximum size of a file that can be uploaded to or downloaded from a room. The global default is 20MB.</span></span>
    
- <span data-ttu-id="64eea-113">[参加者の更新制限]。</span><span class="sxs-lookup"><span data-stu-id="64eea-113">Participant Update Limit.</span></span> <span data-ttu-id="64eea-114">常設チャットから参加者の名簿の更新情報が送信されるチャット ルームの最大参加者数です。</span><span class="sxs-lookup"><span data-stu-id="64eea-114">The maximum number of participants in a given chat room for which Persistent Chat will send roster updates.</span></span> <span data-ttu-id="64eea-115">グローバルな既定値は 75 です。</span><span class="sxs-lookup"><span data-stu-id="64eea-115">The global default is 75.</span></span>
    
- <span data-ttu-id="64eea-116">会議室管理 URL。</span><span class="sxs-lookup"><span data-stu-id="64eea-116">Room Management URL.</span></span> <span data-ttu-id="64eea-117">カスタム チャット ルーム管理に使用される URL です。</span><span class="sxs-lookup"><span data-stu-id="64eea-117">The URL used for custom chat room management.</span></span> <span data-ttu-id="64eea-118">この設定により、カスタム ルーム管理ソリューションを使用できるようになります。</span><span class="sxs-lookup"><span data-stu-id="64eea-118">The setting allows the use of a custom room management solution.</span></span> 
   
> [!NOTE] 
> <span data-ttu-id="64eea-119">常設チャットは Skype for Business Server 2015 で使用できますが、Skype for Business Server 2019 ではサポートされなくなりました。</span><span class="sxs-lookup"><span data-stu-id="64eea-119">Persistent chat is available in Skype for Business Server 2015 but is no longer supported in Skype for Business Server 2019.</span></span> <span data-ttu-id="64eea-120">Teams でも同じ機能を使用できます。</span><span class="sxs-lookup"><span data-stu-id="64eea-120">The same functionality is available in Teams.</span></span> <span data-ttu-id="64eea-121">詳細については、「 [Skype For business から Microsoft Teams への旅](/microsoftteams/journey-skypeforbusiness-teams)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="64eea-121">For more information, see [Journey from Skype for Business to Microsoft Teams](/microsoftteams/journey-skypeforbusiness-teams).</span></span> <span data-ttu-id="64eea-122">常設チャットを使用する必要がある場合は、この機能が必要なユーザーをチームに移行するか、Skype for Business Server 2015 を使い続けるかのいずれかを選択できます。</span><span class="sxs-lookup"><span data-stu-id="64eea-122">If you need to use Persistent chat, your choices are to either migrate users requiring this functionality to Teams, or to continue using Skype for Business Server 2015.</span></span>
 
## <a name="configure-persistent-chat-server-global-options"></a><span data-ttu-id="64eea-123">常設チャットサーバーのグローバルオプションを構成する</span><span class="sxs-lookup"><span data-stu-id="64eea-123">Configure Persistent Chat Server global options</span></span>

<span data-ttu-id="64eea-124">常設チャットサーバーのグローバルオプションを構成するには:</span><span class="sxs-lookup"><span data-stu-id="64eea-124">To configure Persistent Chat Server global options:</span></span>
  
1. <span data-ttu-id="64eea-125">CsPersistentChatAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="64eea-125">From a user account that is assigned to the CsPersistentChatAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="64eea-126">[**スタート**] メニューで、[Skype For business Server] コントロールパネルを選択するか、ブラウザーウィンドウを開き、管理 URL を入力します。</span><span class="sxs-lookup"><span data-stu-id="64eea-126">From the **Start** menu, select the Skype for Business Server Control Panel or open a browser window, and then enter the Admin URL.</span></span>
    
3. <span data-ttu-id="64eea-127">左側のナビゲーション バーで [**常設チャット**] をクリックし、[**常設チャットの構成**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="64eea-127">In the left navigation bar, click **Persistent Chat**, and then click **Persistent Chat Configuration**.</span></span>
    
4. <span data-ttu-id="64eea-128">[**常設チャットの構成**] ページで、[**新規] を**クリックし、[サイトの**構成**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="64eea-128">On the **Persistent Chat Configuration** page, click **New,** and then click **Site configuration**.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="64eea-129">サイトに展開されているすべての常設チャットサーバープールに構成を適用する場合は、このオプションを選びます。</span><span class="sxs-lookup"><span data-stu-id="64eea-129">Choose this option if you want the configuration to be applied to all Persistent Chat Server pools deployed in the site.</span></span> <span data-ttu-id="64eea-130">特定の常設チャットサーバープールに構成を適用する場合は、[**プール構成**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="64eea-130">Click **Pool Configuration** if you want the configuration to be applied to a specific Persistent Chat Server pool.</span></span>
  
5. <span data-ttu-id="64eea-131">[**サイトの選択**] で、常設チャットサーバーのサイト構成用に構成するサイトを選びます。</span><span class="sxs-lookup"><span data-stu-id="64eea-131">In **Select a Site**, select the site to be configured for the Persistent Chat Server site configuration.</span></span>
    
6. <span data-ttu-id="64eea-132">[**新規 常設チャットの構成**] で、次の操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="64eea-132">In **New Persistent Chat Configuration**, do the following:</span></span>
    
   - <span data-ttu-id="64eea-p108">[**名前**] で、新しい構成設定の名前を指定します。既定では、サイト名が既に存在します。</span><span class="sxs-lookup"><span data-stu-id="64eea-p108">In **Name**, specify a name for the new configuration settings. By default, the site name already exists.</span></span>
    
   - <span data-ttu-id="64eea-p109">[**既定のチャット履歴**] で、最初の要求時にチャット ルームごとに処理されるチャット メッセージ数を定義します。既定値は 30 で、これはグローバルな既定値です。管理者はカテゴリごとにチャット履歴を無効にできます。</span><span class="sxs-lookup"><span data-stu-id="64eea-p109">In **Default chat history**, define the number of chat messages that will be processed for each room upon first request. By default, the number is 30. This is the global default, and administrators can disable chat history per category.</span></span>
    
     > [!IMPORTANT]
     > <span data-ttu-id="64eea-138">常設チャットサーバーでは、これらのメッセージがメモリにキャッシュされるため、この数値を増やすと、より多くのメッセージがキャッシュされます。</span><span class="sxs-lookup"><span data-stu-id="64eea-138">Persistent Chat Server will cache these messages in memory, so if you increase this number, more messages will be cached.</span></span> <span data-ttu-id="64eea-139">履歴コンテンツには、検索を使用していつでもアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="64eea-139">You can always access historical content by search.</span></span> <span data-ttu-id="64eea-140">既定値は、チャット ルームに接続したときに最初に表示されるメッセージの最大数を規定しているにすぎません。</span><span class="sxs-lookup"><span data-stu-id="64eea-140">The default number simply determines the maximum number of messages that you initially see when connecting to a chat room.</span></span> 
  
   - <span data-ttu-id="64eea-p111">[**最大ファイル サイズ (KB)**] で、各チャット履歴の最大ファイル サイズを選択します。既定値は 20 MB (20,000 KB) です。これは、システム内のチャット ルーム (対応する [**分類**] 設定でファイルのアップロードが有効化されているチャット ルーム) にアップロードできるファイルの最大サイズです。</span><span class="sxs-lookup"><span data-stu-id="64eea-p111">In **Maximum file size (KB)**, select the maximum file size of each chat history. By default, the number is 20 MB (20,000 KB). This is the maximum size for a file that can be uploaded to any chat room in the system (for which file uploads are enabled by its corresponding **Category** setting).</span></span>
    
   - <span data-ttu-id="64eea-144">[**参加者の更新制限**] で、参加者の更新の制限値を選択します。</span><span class="sxs-lookup"><span data-stu-id="64eea-144">In **Participant update limit**, select the limit for participant updates.</span></span> <span data-ttu-id="64eea-145">常設チャットサーバーは、接続されているユーザーの数がこの番号に到達するまで、すべての参加者にリスト情報 (チャットルームに接続されているユーザー) を送信します。</span><span class="sxs-lookup"><span data-stu-id="64eea-145">Persistent Chat Server sends roster information (who is connected to a chat room) to all participants until the number of connected users reaches this number.</span></span> <span data-ttu-id="64eea-146">既定値は 75 です。</span><span class="sxs-lookup"><span data-stu-id="64eea-146">By default, the number is 75.</span></span> <span data-ttu-id="64eea-147">この制限は、常設チャットサーバーが、会議室に存在するユーザーに対して、接続されているクライアントに対して、リストの更新情報を送信するのを超えた、特定のルーム内の参加者の最大数を示します。</span><span class="sxs-lookup"><span data-stu-id="64eea-147">This limit indicates the maximum number of participants in a given room beyond which Persistent Chat Server stops sending roster updates to connected clients about who is present in the room.</span></span>
    
   - <span data-ttu-id="64eea-148">(省略可能)[ **Room MANAGEMENT url**] で、[会議室管理 url] を選びます。</span><span class="sxs-lookup"><span data-stu-id="64eea-148">(Optional.) In **Room management URL**, select the room management URL.</span></span> <span data-ttu-id="64eea-149">これは、web ベースのカスタムルーム管理の URL です。</span><span class="sxs-lookup"><span data-stu-id="64eea-149">This is the URL for a web-based custom room management.</span></span> <span data-ttu-id="64eea-150">Room management をカスタマイズする必要がなく、既定の設定を使用している場合は、このオプションを空白のままにします。</span><span class="sxs-lookup"><span data-stu-id="64eea-150">If you don't need to customize room management, and you simply use the default setting, leave this option blank.</span></span> <span data-ttu-id="64eea-151">URL を設定すると、その URL は、内部および外部の room 管理 URL の両方として適用されます。</span><span class="sxs-lookup"><span data-stu-id="64eea-151">After the URL is set, it is applied as both the internal and external room management URL.</span></span>
    
     <span data-ttu-id="64eea-152">会議室の作成環境をカスタマイズして、特定のビジネスワークフローを含める場合は、常設チャットサーバーソフトウェア開発キット (SDK) を使用して、カスタムルーム管理ソリューションを構築し、どこかにホストして、URL をここに入力します。</span><span class="sxs-lookup"><span data-stu-id="64eea-152">If you want to customize your room creation experience and include your specific business workflow, you can build a custom room management solution by using the Persistent Chat Server Software Development Kit (SDK), host it somewhere, and put the URL here.</span></span> <span data-ttu-id="64eea-153">ユーザーがチャット ルームを表示または作成するときにカスタム チャット ルーム管理ソリューションを使用するよう、この URL がクライアントに伝えられます。</span><span class="sxs-lookup"><span data-stu-id="64eea-153">This URL is sent down to the client, so that when a user tries to view or create a room, he or she is directed to your custom room management solution.</span></span>
    
7. <span data-ttu-id="64eea-154">[**コミット**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="64eea-154">Click **Commit**.</span></span>
    
## <a name="configure-options-for-a-specific-persistent-chat-server-pool"></a><span data-ttu-id="64eea-155">特定の常設チャットサーバープールのオプションを構成する</span><span class="sxs-lookup"><span data-stu-id="64eea-155">Configure options for a specific Persistent Chat Server pool</span></span>

<span data-ttu-id="64eea-156">特定の常設チャットサーバープールのオプションを構成します。</span><span class="sxs-lookup"><span data-stu-id="64eea-156">To configure options for a specific Persistent Chat Server pool.</span></span>
  
1. <span data-ttu-id="64eea-157">CsPersistentChatAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="64eea-157">From a user account that is assigned to the CsPersistentChatAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="64eea-158">[**スタート**] メニューで、[Skype For business Server] コントロールパネルを選択するか、ブラウザーウィンドウを開いて、管理者 URL を入力します。</span><span class="sxs-lookup"><span data-stu-id="64eea-158">From the **Start** menu, select the Skype for Business Server Control Panel, or open a browser window, and then enter the Admin URL.</span></span>
    
3. <span data-ttu-id="64eea-159">左側のナビゲーション バーで [**常設チャット**] をクリックし、[**常設チャットの構成**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="64eea-159">In the left navigation bar, click **Persistent Chat**, and then click **Persistent Chat Configuration**.</span></span>
    
4. <span data-ttu-id="64eea-160">[**常設チャットの構成**] ページで、[**新規**] をクリックし、[**プール構成**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="64eea-160">On the **Persistent Chat Configuration** page, click **New**, and then click **Pool configuration**.</span></span>
    
5. <span data-ttu-id="64eea-161">[**サービスの選択**] で、構成する常設チャットサーバープールに関連するサービスを選びます。</span><span class="sxs-lookup"><span data-stu-id="64eea-161">In **Select a Service**, select the service associated with the Persistent Chat Server pool to be configured.</span></span>
    
6. <span data-ttu-id="64eea-162">[**新規 常設チャットの構成**] で、次の操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="64eea-162">In **New Persistent Chat Configuration**, do the following:</span></span>
    
   - <span data-ttu-id="64eea-p115">[**名前**] で、新しい構成設定の名前を指定します。既定では、サイト プール名が既に存在します。</span><span class="sxs-lookup"><span data-stu-id="64eea-p115">In **Name**, specify a name for the new configuration settings. By default, the site pool name already exists.</span></span>
    
   - <span data-ttu-id="64eea-p116">[**既定のチャット履歴**] で、最初の要求時にチャット ルームごとに処理されるチャット メッセージ数を定義します。既定値は 30 で、これはグローバルな既定値です。管理者はカテゴリごとにチャット履歴を無効にできます。</span><span class="sxs-lookup"><span data-stu-id="64eea-p116">In **Default chat history**, define the number of chat messages that will be processed for each room upon first request. By default, the number is 30. This is the global default, and administrators can disable chat history per category.</span></span>
    
     > [!IMPORTANT]
     > <span data-ttu-id="64eea-168">常設チャットサーバーでは、これらのメッセージがメモリにキャッシュされるため、この数値を増やすと、より多くのメッセージがキャッシュされます。</span><span class="sxs-lookup"><span data-stu-id="64eea-168">Persistent Chat Server will cache these messages in memory, so if you increase this number, more messages will be cached.</span></span> <span data-ttu-id="64eea-169">履歴コンテンツには、検索を使用していつでもアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="64eea-169">You can always access historical content by search.</span></span> <span data-ttu-id="64eea-170">既定値は、チャット ルームに接続したときに最初に表示されるメッセージの最大数を規定しているにすぎません。</span><span class="sxs-lookup"><span data-stu-id="64eea-170">The default number simply determines the maximum number of messages that you initially see when connecting to a chat room.</span></span> 
  
   - <span data-ttu-id="64eea-p118">[**最大ファイル サイズ (KB)**] で、各チャット履歴の最大ファイル サイズを選択します。既定値は 20 MB (20,000 KB) です。これは、システム内のチャット ルーム (対応する [**分類**] 設定でファイルのアップロードが有効化されているチャット ルーム) にアップロードできるファイルの最大サイズです。</span><span class="sxs-lookup"><span data-stu-id="64eea-p118">In **Maximum file size (KB)**, select the maximum file size of each chat history. By default, the number is 20 MB (20,000 KB). This is the maximum size for a file that can be uploaded to any chat room in the system (for which file uploads are enabled by its corresponding **Category** setting).</span></span>
    
   - <span data-ttu-id="64eea-174">[**参加者の更新制限**] で、参加者の更新の制限値を選択します。</span><span class="sxs-lookup"><span data-stu-id="64eea-174">In **Participant update limit**, select the limit for participant updates.</span></span> <span data-ttu-id="64eea-175">常設チャットサーバーは、接続されているユーザーの数がこの番号に到達するまで、すべての参加者にリスト情報 (チャットルームに接続されているユーザー) を送信します。</span><span class="sxs-lookup"><span data-stu-id="64eea-175">Persistent Chat Server sends roster information (who is connected to a chat room) to all participants until the number of connected users reaches this number.</span></span> <span data-ttu-id="64eea-176">既定値は 75 です。</span><span class="sxs-lookup"><span data-stu-id="64eea-176">By default, the number is 75.</span></span> <span data-ttu-id="64eea-177">この制限は、常設チャットサーバーが、会議室に存在するユーザーに対して、接続されているクライアントに対して、リストの更新情報を送信するのを超えた、特定のルーム内の参加者の最大数を示します。</span><span class="sxs-lookup"><span data-stu-id="64eea-177">This limit indicates the maximum number of participants in a given room beyond which Persistent Chat Server stops sending roster updates to connected clients about who is present in the room.</span></span>
    
   - <span data-ttu-id="64eea-178">[**ルームの管理 URL**] で、ルーム管理 URL を選択します。</span><span class="sxs-lookup"><span data-stu-id="64eea-178">In **Room management URL**, select the room management URL.</span></span> <span data-ttu-id="64eea-179">これは Web ベースのチャット ルーム管理用の URL です。</span><span class="sxs-lookup"><span data-stu-id="64eea-179">This is the URL for a web-based room management deployment.</span></span> <span data-ttu-id="64eea-180">Room management をカスタマイズする必要がなく、既定の設定を使用している場合は、このオプションを空白のままにします。</span><span class="sxs-lookup"><span data-stu-id="64eea-180">If you don't need to customize room management, and you simply use the default setting, leave this option blank.</span></span>
    
     <span data-ttu-id="64eea-181">会議室の作成環境をカスタマイズして、特定のビジネスワークフローを含める場合は、常設チャットサーバーソフトウェア開発キット (SDK) を使用して、カスタムルーム管理ソリューションを構築し、どこかにホストして、URL をここに入力します。</span><span class="sxs-lookup"><span data-stu-id="64eea-181">If you want to customize your room creation experience and include your specific business workflow, you can build a custom room management solution by using the Persistent Chat Server Software Development Kit (SDK), host it somewhere, and put the URL here.</span></span> <span data-ttu-id="64eea-182">ユーザーがチャット ルームを表示または作成するときにカスタム チャット ルーム管理ソリューションを使用するよう、この URL がクライアントに伝えられます。</span><span class="sxs-lookup"><span data-stu-id="64eea-182">This URL is sent down to the client so that when a user tries to view/create a room, he or she is directed to your custom room management solution.</span></span>
    
7. <span data-ttu-id="64eea-183">[**コミット**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="64eea-183">Click **Commit**.</span></span>
    

