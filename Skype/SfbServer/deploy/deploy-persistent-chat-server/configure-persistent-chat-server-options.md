---
title: Skype for Business Server 2015 での常設チャット サーバー オプションの構成
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 19ced8de-8867-4152-b38a-891f3bc2a5ea
description: '概要: は、Skype のビジネス サーバー 2015 のグローバル オプションを永続的なチャット サーバー、サイト、またはプールのレベルを構成する方法について説明します。'
ms.openlocfilehash: fa2f5aec3a4061191927563437b36504cbb3a119
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "33894487"
---
# <a name="configure-persistent-chat-server-options-in-skype-for-business-server-2015"></a><span data-ttu-id="4b89b-103">Skype for Business Server 2015 での常設チャット サーバー オプションの構成</span><span class="sxs-lookup"><span data-stu-id="4b89b-103">Configure Persistent Chat Server options in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="4b89b-104">**の概要:** ビジネス サーバー 2015 の Skype のグローバル オプションを永続的なチャット サーバー、サイト、またはプールのレベルを構成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="4b89b-104">**Summary:** Learn how to configure Persistent Chat Server options at the global, site, or pool level in Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="4b89b-105">サイト内のすべてのプールまたはサイト内の特定のプールにグローバルに適用できる永続的なチャット サーバーのいくつかのオプションを指定できます。</span><span class="sxs-lookup"><span data-stu-id="4b89b-105">You can specify several options for Persistent Chat Server that can be applied globally, to all pools within a site, or to a specific pool within a site.</span></span> <span data-ttu-id="4b89b-106">常設チャット サーバーには以下のオプションがあります。</span><span class="sxs-lookup"><span data-stu-id="4b89b-106">Persistent Chat server options include the following:</span></span> 
  
- <span data-ttu-id="4b89b-107">[既定のチャット履歴]。</span><span class="sxs-lookup"><span data-stu-id="4b89b-107">Default Chat History.</span></span> <span data-ttu-id="4b89b-108">最初の要求時に各チャット ルームで使用できるチャット メッセージ数です。</span><span class="sxs-lookup"><span data-stu-id="4b89b-108">The number of chat messages that are available for each chat room upon first request.</span></span> <span data-ttu-id="4b89b-109">グローバルなチャット メッセージ数の既定値は 30 です。</span><span class="sxs-lookup"><span data-stu-id="4b89b-109">The global default is 30 chat messages.</span></span> 
    
- <span data-ttu-id="4b89b-p103">[最大ファイル サイズ]。ルームへのアップロードまたはルームからのダウンロードが可能なファイルの最大サイズです。グローバルな既定値は 20 MB です。</span><span class="sxs-lookup"><span data-stu-id="4b89b-p103">Maximum File Size. The maximum size of a file that can be uploaded to or downloaded from a room. The global default is 20MB.</span></span>
    
- <span data-ttu-id="4b89b-113">[参加者の更新制限]。</span><span class="sxs-lookup"><span data-stu-id="4b89b-113">Participant Update Limit.</span></span> <span data-ttu-id="4b89b-114">常設チャットから参加者の名簿の更新情報が送信されるチャット ルームの最大参加者数です。</span><span class="sxs-lookup"><span data-stu-id="4b89b-114">The maximum number of participants in a given chat room for which Persistent Chat will send roster updates.</span></span> <span data-ttu-id="4b89b-115">グローバルな既定値は 75 です。</span><span class="sxs-lookup"><span data-stu-id="4b89b-115">The global default is 75.</span></span>
    
- <span data-ttu-id="4b89b-116">ルーム管理の URL です。</span><span class="sxs-lookup"><span data-stu-id="4b89b-116">Room Management URL.</span></span> <span data-ttu-id="4b89b-117">カスタム チャット ルーム管理に使用される URL です。</span><span class="sxs-lookup"><span data-stu-id="4b89b-117">The URL used for custom chat room management.</span></span> <span data-ttu-id="4b89b-118">この設定により、カスタム ルーム管理ソリューションを使用できるようになります。</span><span class="sxs-lookup"><span data-stu-id="4b89b-118">The setting allows the use of a custom room management solution.</span></span> 
   
> [!NOTE] 
> <span data-ttu-id="4b89b-119">永続的なチャットですがビジネス サーバー 2015 の Skype で利用可能なビジネス サーバー 2019 の Skype でサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="4b89b-119">Persistent chat is available in Skype for Business Server 2015 but is no longer supported in Skype for Business Server 2019.</span></span> <span data-ttu-id="4b89b-120">同じ機能は、チームで使用できます。</span><span class="sxs-lookup"><span data-stu-id="4b89b-120">The same functionality is available in Teams.</span></span> <span data-ttu-id="4b89b-121">詳細については、[マイクロソフトのチームにビジネス用の Skype からの旅](/microsoftteams/journey-skypeforbusiness-teams)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4b89b-121">For more information, see [Journey from Skype for Business to Microsoft Teams](/microsoftteams/journey-skypeforbusiness-teams).</span></span> <span data-ttu-id="4b89b-122">永続的なチャットを使用する場合は、選択肢は、いずれかをチームでは、この機能を必要とするユーザーを移行するまたはビジネス サーバー 2015 の Skype を使用し続ける。</span><span class="sxs-lookup"><span data-stu-id="4b89b-122">If you need to use Persistent chat, your choices are to either migrate users requiring this functionality to Teams, or to continue using Skype for Business Server 2015.</span></span>
 
## <a name="configure-persistent-chat-server-global-options"></a><span data-ttu-id="4b89b-123">永続的なチャット サーバーのグローバル オプションを構成します。</span><span class="sxs-lookup"><span data-stu-id="4b89b-123">Configure Persistent Chat Server global options</span></span>

<span data-ttu-id="4b89b-124">永続的なチャット サーバーのグローバル オプションを構成するには。</span><span class="sxs-lookup"><span data-stu-id="4b89b-124">To configure Persistent Chat Server global options:</span></span>
  
1. <span data-ttu-id="4b89b-125">CsPersistentChatAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="4b89b-125">From a user account that is assigned to the CsPersistentChatAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="4b89b-126">**[スタート**] メニューから、Skype ビジネス サーバーのコントロール パネルのまたはブラウザー ウィンドウを開きし、管理 URL を入力します。</span><span class="sxs-lookup"><span data-stu-id="4b89b-126">From the **Start** menu, select the Skype for Business Server Control Panel or open a browser window, and then enter the Admin URL.</span></span>
    
3. <span data-ttu-id="4b89b-127">左側のナビゲーション バーで [**常設チャット**] をクリックし、[**常設チャットの構成**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="4b89b-127">In the left navigation bar, click **Persistent Chat**, and then click **Persistent Chat Configuration**.</span></span>
    
4. <span data-ttu-id="4b89b-128">[**永続的なチャットの構成**] ページで、[**新規作成**] をクリックし、**サイトの構成**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="4b89b-128">On the **Persistent Chat Configuration** page, click **New,** and then click **Site configuration**.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="4b89b-129">サイトに展開されるすべての永続的なチャット サーバー プールに適用する構成を使用する場合は、このオプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="4b89b-129">Choose this option if you want the configuration to be applied to all Persistent Chat Server pools deployed in the site.</span></span> <span data-ttu-id="4b89b-130">特定の永続的なチャット サーバー プールに適用する構成を使用する場合は、**プールの構成**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="4b89b-130">Click **Pool Configuration** if you want the configuration to be applied to a specific Persistent Chat Server pool.</span></span>
  
5. <span data-ttu-id="4b89b-131">**サイトを選択**すると、永続的なチャット サーバーのサイト設定を構成するサイトを選択します。</span><span class="sxs-lookup"><span data-stu-id="4b89b-131">In **Select a Site**, select the site to be configured for the Persistent Chat Server site configuration.</span></span>
    
6. <span data-ttu-id="4b89b-132">[**新規 常設チャットの構成**] で、次の操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="4b89b-132">In **New Persistent Chat Configuration**, do the following:</span></span>
    
   - <span data-ttu-id="4b89b-p108">[**名前**] で、新しい構成設定の名前を指定します。既定では、サイト名が既に存在します。</span><span class="sxs-lookup"><span data-stu-id="4b89b-p108">In **Name**, specify a name for the new configuration settings. By default, the site name already exists.</span></span>
    
   - <span data-ttu-id="4b89b-p109">[**既定のチャット履歴**] で、最初の要求時にチャット ルームごとに処理されるチャット メッセージ数を定義します。既定値は 30 で、これはグローバルな既定値です。管理者はカテゴリごとにチャット履歴を無効にできます。</span><span class="sxs-lookup"><span data-stu-id="4b89b-p109">In **Default chat history**, define the number of chat messages that will be processed for each room upon first request. By default, the number is 30. This is the global default, and administrators can disable chat history per category.</span></span>
    
     > [!IMPORTANT]
     > <span data-ttu-id="4b89b-138">永続的なチャット サーバーは、メモリ内のこれらのメッセージをキャッシュがより多くのメッセージをキャッシュする場合はこの値を大きくようにします。</span><span class="sxs-lookup"><span data-stu-id="4b89b-138">Persistent Chat Server will cache these messages in memory, so if you increase this number, more messages will be cached.</span></span> <span data-ttu-id="4b89b-139">履歴コンテンツには、検索を使用していつでもアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="4b89b-139">You can always access historical content by search.</span></span> <span data-ttu-id="4b89b-140">既定値は、チャット ルームに接続したときに最初に表示されるメッセージの最大数を規定しているにすぎません。</span><span class="sxs-lookup"><span data-stu-id="4b89b-140">The default number simply determines the maximum number of messages that you initially see when connecting to a chat room.</span></span> 
  
   - <span data-ttu-id="4b89b-p111">[**最大ファイル サイズ (KB)**] で、各チャット履歴の最大ファイル サイズを選択します。既定値は 20 MB (20,000 KB) です。これは、システム内のチャット ルーム (対応する [**分類**] 設定でファイルのアップロードが有効化されているチャット ルーム) にアップロードできるファイルの最大サイズです。</span><span class="sxs-lookup"><span data-stu-id="4b89b-p111">In **Maximum file size (KB)**, select the maximum file size of each chat history. By default, the number is 20 MB (20,000 KB). This is the maximum size for a file that can be uploaded to any chat room in the system (for which file uploads are enabled by its corresponding **Category** setting).</span></span>
    
   - <span data-ttu-id="4b89b-144">[**参加者の更新制限**] で、参加者の更新の制限値を選択します。</span><span class="sxs-lookup"><span data-stu-id="4b89b-144">In **Participant update limit**, select the limit for participant updates.</span></span> <span data-ttu-id="4b89b-145">永続的なチャット サーバーは、接続しているユーザーの数がこの数に到達するまで、すべての参加者に名簿の情報 (ユーザーはチャット ルームに接続されている) を送信します。</span><span class="sxs-lookup"><span data-stu-id="4b89b-145">Persistent Chat Server sends roster information (who is connected to a chat room) to all participants until the number of connected users reaches this number.</span></span> <span data-ttu-id="4b89b-146">既定値は 75 です。</span><span class="sxs-lookup"><span data-stu-id="4b89b-146">By default, the number is 75.</span></span> <span data-ttu-id="4b89b-147">この制限を超えて、永続的なチャット サーバーが停止するルームには、接続されているクライアントに対して、名簿の更新を送信する特定の部屋に参加者の最大数を示します。</span><span class="sxs-lookup"><span data-stu-id="4b89b-147">This limit indicates the maximum number of participants in a given room beyond which Persistent Chat Server stops sending roster updates to connected clients about who is present in the room.</span></span>
    
   - <span data-ttu-id="4b89b-148">(オプション)。**ルーム管理 URL**] には、ルームの管理 URL を選択します。</span><span class="sxs-lookup"><span data-stu-id="4b89b-148">(Optional.) In **Room management URL**, select the room management URL.</span></span> <span data-ttu-id="4b89b-149">これは、web ベースのカスタム ルーム管理の URL です。</span><span class="sxs-lookup"><span data-stu-id="4b89b-149">This is the URL for a web-based custom room management.</span></span> <span data-ttu-id="4b89b-150">室の管理をカスタマイズする必要はありませんし、単に既定の設定を使用する場合は、このオプションを空白のままにします。</span><span class="sxs-lookup"><span data-stu-id="4b89b-150">If you don't need to customize room management, and you simply use the default setting, leave this option blank.</span></span> <span data-ttu-id="4b89b-151">URL を設定すると、部屋の内部および外部の両方の管理 URL として適用されます。</span><span class="sxs-lookup"><span data-stu-id="4b89b-151">After the URL is set, it is applied as both the internal and external room management URL.</span></span>
    
     <span data-ttu-id="4b89b-152">ルーム作成の操作性をカスタマイズし、特定のビジネス ・ ワークフローを含める場合は、永続的なチャット サーバー ソフトウェア開発キット (SDK) を使用してカスタム ルーム管理ソリューションを構築、それをどこかにホストして URL をここに配置します。。</span><span class="sxs-lookup"><span data-stu-id="4b89b-152">If you want to customize your room creation experience and include your specific business workflow, you can build a custom room management solution by using the Persistent Chat Server Software Development Kit (SDK), host it somewhere, and put the URL here.</span></span> <span data-ttu-id="4b89b-153">ユーザーがチャット ルームを表示または作成するときにカスタム チャット ルーム管理ソリューションを使用するよう、この URL がクライアントに伝えられます。</span><span class="sxs-lookup"><span data-stu-id="4b89b-153">This URL is sent down to the client, so that when a user tries to view or create a room, he or she is directed to your custom room management solution.</span></span>
    
7. <span data-ttu-id="4b89b-154">[**コミット**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="4b89b-154">Click **Commit**.</span></span>
    
## <a name="configure-options-for-a-specific-persistent-chat-server-pool"></a><span data-ttu-id="4b89b-155">特定の永続的なチャット サーバー プールのオプションを構成します。</span><span class="sxs-lookup"><span data-stu-id="4b89b-155">Configure options for a specific Persistent Chat Server pool</span></span>

<span data-ttu-id="4b89b-156">特定の永続的なチャット サーバー プールのオプションを構成します。</span><span class="sxs-lookup"><span data-stu-id="4b89b-156">To configure options for a specific Persistent Chat Server pool.</span></span>
  
1. <span data-ttu-id="4b89b-157">CsPersistentChatAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="4b89b-157">From a user account that is assigned to the CsPersistentChatAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="4b89b-158">**[スタート**] メニューから、Skype をビジネス サーバーのコントロール パネル] を選択や、ブラウザー ウィンドウを開く管理 URL を入力します。</span><span class="sxs-lookup"><span data-stu-id="4b89b-158">From the **Start** menu, select the Skype for Business Server Control Panel, or open a browser window, and then enter the Admin URL.</span></span>
    
3. <span data-ttu-id="4b89b-159">左側のナビゲーション バーで [**常設チャット**] をクリックし、[**常設チャットの構成**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="4b89b-159">In the left navigation bar, click **Persistent Chat**, and then click **Persistent Chat Configuration**.</span></span>
    
4. <span data-ttu-id="4b89b-160">[**常設チャットの構成**] ページで、[**新規**] をクリックし、[**プール構成**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="4b89b-160">On the **Persistent Chat Configuration** page, click **New**, and then click **Pool configuration**.</span></span>
    
5. <span data-ttu-id="4b89b-161">[**サービスの選択**] で構成される永続的なチャット サーバー プールに関連付けられているサービスを選択します。</span><span class="sxs-lookup"><span data-stu-id="4b89b-161">In **Select a Service**, select the service associated with the Persistent Chat Server pool to be configured.</span></span>
    
6. <span data-ttu-id="4b89b-162">[**新規 常設チャットの構成**] で、次の操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="4b89b-162">In **New Persistent Chat Configuration**, do the following:</span></span>
    
   - <span data-ttu-id="4b89b-p115">[**名前**] で、新しい構成設定の名前を指定します。既定では、サイト プール名が既に存在します。</span><span class="sxs-lookup"><span data-stu-id="4b89b-p115">In **Name**, specify a name for the new configuration settings. By default, the site pool name already exists.</span></span>
    
   - <span data-ttu-id="4b89b-p116">[**既定のチャット履歴**] で、最初の要求時にチャット ルームごとに処理されるチャット メッセージ数を定義します。既定値は 30 で、これはグローバルな既定値です。管理者はカテゴリごとにチャット履歴を無効にできます。</span><span class="sxs-lookup"><span data-stu-id="4b89b-p116">In **Default chat history**, define the number of chat messages that will be processed for each room upon first request. By default, the number is 30. This is the global default, and administrators can disable chat history per category.</span></span>
    
     > [!IMPORTANT]
     > <span data-ttu-id="4b89b-168">永続的なチャット サーバーは、メモリ内のこれらのメッセージをキャッシュがより多くのメッセージをキャッシュする場合はこの値を大きくようにします。</span><span class="sxs-lookup"><span data-stu-id="4b89b-168">Persistent Chat Server will cache these messages in memory, so if you increase this number, more messages will be cached.</span></span> <span data-ttu-id="4b89b-169">履歴コンテンツには、検索を使用していつでもアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="4b89b-169">You can always access historical content by search.</span></span> <span data-ttu-id="4b89b-170">既定値は、チャット ルームに接続したときに最初に表示されるメッセージの最大数を規定しているにすぎません。</span><span class="sxs-lookup"><span data-stu-id="4b89b-170">The default number simply determines the maximum number of messages that you initially see when connecting to a chat room.</span></span> 
  
   - <span data-ttu-id="4b89b-p118">[**最大ファイル サイズ (KB)**] で、各チャット履歴の最大ファイル サイズを選択します。既定値は 20 MB (20,000 KB) です。これは、システム内のチャット ルーム (対応する [**分類**] 設定でファイルのアップロードが有効化されているチャット ルーム) にアップロードできるファイルの最大サイズです。</span><span class="sxs-lookup"><span data-stu-id="4b89b-p118">In **Maximum file size (KB)**, select the maximum file size of each chat history. By default, the number is 20 MB (20,000 KB). This is the maximum size for a file that can be uploaded to any chat room in the system (for which file uploads are enabled by its corresponding **Category** setting).</span></span>
    
   - <span data-ttu-id="4b89b-174">[**参加者の更新制限**] で、参加者の更新の制限値を選択します。</span><span class="sxs-lookup"><span data-stu-id="4b89b-174">In **Participant update limit**, select the limit for participant updates.</span></span> <span data-ttu-id="4b89b-175">永続的なチャット サーバーは、接続しているユーザーの数がこの数に到達するまで、すべての参加者に名簿の情報 (ユーザーはチャット ルームに接続されている) を送信します。</span><span class="sxs-lookup"><span data-stu-id="4b89b-175">Persistent Chat Server sends roster information (who is connected to a chat room) to all participants until the number of connected users reaches this number.</span></span> <span data-ttu-id="4b89b-176">既定値は 75 です。</span><span class="sxs-lookup"><span data-stu-id="4b89b-176">By default, the number is 75.</span></span> <span data-ttu-id="4b89b-177">この制限を超えて、永続的なチャット サーバーが停止するルームには、接続されているクライアントに対して、名簿の更新を送信する特定の部屋に参加者の最大数を示します。</span><span class="sxs-lookup"><span data-stu-id="4b89b-177">This limit indicates the maximum number of participants in a given room beyond which Persistent Chat Server stops sending roster updates to connected clients about who is present in the room.</span></span>
    
   - <span data-ttu-id="4b89b-178">[**ルームの管理 URL**] で、ルーム管理 URL を選択します。</span><span class="sxs-lookup"><span data-stu-id="4b89b-178">In **Room management URL**, select the room management URL.</span></span> <span data-ttu-id="4b89b-179">これは Web ベースのチャット ルーム管理用の URL です。</span><span class="sxs-lookup"><span data-stu-id="4b89b-179">This is the URL for a web-based room management deployment.</span></span> <span data-ttu-id="4b89b-180">室の管理をカスタマイズする必要はありませんし、単に既定の設定を使用する場合は、このオプションを空白のままにします。</span><span class="sxs-lookup"><span data-stu-id="4b89b-180">If you don't need to customize room management, and you simply use the default setting, leave this option blank.</span></span>
    
     <span data-ttu-id="4b89b-181">ルーム作成の操作性をカスタマイズし、特定のビジネス ・ ワークフローを含める場合は、永続的なチャット サーバー ソフトウェア開発キット (SDK) を使用してカスタム ルーム管理ソリューションを構築、それをどこかにホストして URL をここに配置します。。</span><span class="sxs-lookup"><span data-stu-id="4b89b-181">If you want to customize your room creation experience and include your specific business workflow, you can build a custom room management solution by using the Persistent Chat Server Software Development Kit (SDK), host it somewhere, and put the URL here.</span></span> <span data-ttu-id="4b89b-182">ユーザーがチャット ルームを表示または作成するときにカスタム チャット ルーム管理ソリューションを使用するよう、この URL がクライアントに伝えられます。</span><span class="sxs-lookup"><span data-stu-id="4b89b-182">This URL is sent down to the client so that when a user tries to view/create a room, he or she is directed to your custom room management solution.</span></span>
    
7. <span data-ttu-id="4b89b-183">[**コミット**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="4b89b-183">Click **Commit**.</span></span>
    

