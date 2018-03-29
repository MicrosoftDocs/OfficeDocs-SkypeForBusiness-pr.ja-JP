---
title: Skype for Business Server 2015 での常設チャット サーバー オプションの構成
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 19ced8de-8867-4152-b38a-891f3bc2a5ea
description: '概要: は、Skype のビジネス サーバー 2015 のグローバル オプションを永続的なチャット サーバー、サイト、またはプールのレベルを構成する方法について説明します。'
ms.openlocfilehash: 6fe06b6a5383178f0a9465624f7a0e739c2a32e6
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/28/2018
---
# <a name="configure-persistent-chat-server-options-in-skype-for-business-server-2015"></a><span data-ttu-id="2cf34-103">Skype for Business Server 2015 での常設チャット サーバー オプションの構成</span><span class="sxs-lookup"><span data-stu-id="2cf34-103">Configure Persistent Chat Server options in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="2cf34-104">**の概要:**ビジネス サーバー 2015 の Skype のグローバル オプションを永続的なチャット サーバー、サイト、またはプールのレベルを構成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="2cf34-104">**Summary:** Learn how to configure Persistent Chat Server options at the global, site, or pool level in Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="2cf34-105">サイト内のすべてのプールまたはサイト内の特定のプールにグローバルに適用できる永続的なチャット サーバーのいくつかのオプションを指定できます。</span><span class="sxs-lookup"><span data-stu-id="2cf34-105">You can specify several options for Persistent Chat Server that can be applied globally, to all pools within a site, or to a specific pool within a site.</span></span> <span data-ttu-id="2cf34-106">常設チャット サーバーには以下のオプションがあります。</span><span class="sxs-lookup"><span data-stu-id="2cf34-106">Persistent Chat server options include the following:</span></span> 
  
- <span data-ttu-id="2cf34-107">[既定のチャット履歴]。</span><span class="sxs-lookup"><span data-stu-id="2cf34-107">Default Chat History.</span></span> <span data-ttu-id="2cf34-108">最初の要求時に各チャット ルームで使用できるチャット メッセージ数です。</span><span class="sxs-lookup"><span data-stu-id="2cf34-108">The number of chat messages that are available for each chat room upon first request.</span></span> <span data-ttu-id="2cf34-109">グローバルなチャット メッセージ数の既定値は 30 です。</span><span class="sxs-lookup"><span data-stu-id="2cf34-109">The global default is 30 chat messages.</span></span> 
    
- <span data-ttu-id="2cf34-p103">[最大ファイル サイズ]。ルームへのアップロードまたはルームからのダウンロードが可能なファイルの最大サイズです。グローバルな既定値は 20 MB です。</span><span class="sxs-lookup"><span data-stu-id="2cf34-p103">Maximum File Size. The maximum size of a file that can be uploaded to or downloaded from a room. The global default is 20MB.</span></span>
    
- <span data-ttu-id="2cf34-113">[参加者の更新制限]。</span><span class="sxs-lookup"><span data-stu-id="2cf34-113">Participant Update Limit.</span></span> <span data-ttu-id="2cf34-114">常設チャットから参加者の名簿の更新情報が送信されるチャット ルームの最大参加者数です。</span><span class="sxs-lookup"><span data-stu-id="2cf34-114">The maximum number of participants in a given chat room for which Persistent Chat will send roster updates.</span></span> <span data-ttu-id="2cf34-115">グローバルな既定値は 75 です。</span><span class="sxs-lookup"><span data-stu-id="2cf34-115">The global default is 75.</span></span>
    
- <span data-ttu-id="2cf34-116">ルーム管理の URL です。</span><span class="sxs-lookup"><span data-stu-id="2cf34-116">Room Management URL.</span></span> <span data-ttu-id="2cf34-117">カスタム チャット ルーム管理に使用される URL です。</span><span class="sxs-lookup"><span data-stu-id="2cf34-117">The URL used for custom chat room management.</span></span> <span data-ttu-id="2cf34-118">この設定により、カスタム ルーム管理ソリューションを使用できるようになります。</span><span class="sxs-lookup"><span data-stu-id="2cf34-118">The setting allows the use of a custom room management solution.</span></span> 
    
## <a name="configure-persistent-chat-server-global-options"></a><span data-ttu-id="2cf34-119">永続的なチャット サーバーのグローバル オプションを構成します。</span><span class="sxs-lookup"><span data-stu-id="2cf34-119">Configure Persistent Chat Server global options</span></span>

<span data-ttu-id="2cf34-120">永続的なチャット サーバーのグローバル オプションを構成するには。</span><span class="sxs-lookup"><span data-stu-id="2cf34-120">To configure Persistent Chat Server global options:</span></span>
  
1. <span data-ttu-id="2cf34-121">CsPersistentChatAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="2cf34-121">From a user account that is assigned to the CsPersistentChatAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="2cf34-122">**[スタート**] メニューから、Skype ビジネス サーバーのコントロール パネルのまたはブラウザー ウィンドウを開きし、管理 URL を入力します。</span><span class="sxs-lookup"><span data-stu-id="2cf34-122">From the **Start** menu, select the Skype for Business Server Control Panel or open a browser window, and then enter the Admin URL.</span></span>
    
3. <span data-ttu-id="2cf34-123">左側のナビゲーション バーで [**常設チャット**] をクリックし、[**常設チャットの構成**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="2cf34-123">In the left navigation bar, click **Persistent Chat**, and then click **Persistent Chat Configuration**.</span></span>
    
4. <span data-ttu-id="2cf34-124">[**永続的なチャットの構成**] ページで、[**新規作成**] をクリックし、**サイトの構成**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="2cf34-124">On the **Persistent Chat Configuration** page, click **New,** and then click **Site configuration**.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="2cf34-125">サイトに展開されるすべての永続的なチャット サーバー プールに適用する構成を使用する場合は、このオプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="2cf34-125">Choose this option if you want the configuration to be applied to all Persistent Chat Server pools deployed in the site.</span></span> <span data-ttu-id="2cf34-126">特定の永続的なチャット サーバー プールに適用する構成を使用する場合は、**プールの構成**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="2cf34-126">Click **Pool Configuration** if you want the configuration to be applied to a specific Persistent Chat Server pool.</span></span>
  
5. <span data-ttu-id="2cf34-127">**サイトを選択**すると、永続的なチャット サーバーのサイト設定を構成するサイトを選択します。</span><span class="sxs-lookup"><span data-stu-id="2cf34-127">In **Select a Site**, select the site to be configured for the Persistent Chat Server site configuration.</span></span>
    
6. <span data-ttu-id="2cf34-128">[**新規 常設チャットの構成**] で、次の操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="2cf34-128">In **New Persistent Chat Configuration**, do the following:</span></span>
    
   - <span data-ttu-id="2cf34-p107">[**名前**] で、新しい構成設定の名前を指定します。既定では、サイト名が既に存在します。</span><span class="sxs-lookup"><span data-stu-id="2cf34-p107">In **Name**, specify a name for the new configuration settings. By default, the site name already exists.</span></span>
    
   - <span data-ttu-id="2cf34-p108">[**既定のチャット履歴**] で、最初の要求時にチャット ルームごとに処理されるチャット メッセージ数を定義します。既定値は 30 で、これはグローバルな既定値です。管理者はカテゴリごとにチャット履歴を無効にできます。</span><span class="sxs-lookup"><span data-stu-id="2cf34-p108">In **Default chat history**, define the number of chat messages that will be processed for each room upon first request. By default, the number is 30. This is the global default, and administrators can disable chat history per category.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="2cf34-134">永続的なチャット サーバーは、メモリ内のこれらのメッセージをキャッシュがより多くのメッセージをキャッシュする場合はこの値を大きくようにします。</span><span class="sxs-lookup"><span data-stu-id="2cf34-134">Persistent Chat Server will cache these messages in memory, so if you increase this number, more messages will be cached.</span></span> <span data-ttu-id="2cf34-135">履歴コンテンツには、検索を使用していつでもアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="2cf34-135">You can always access historical content by search.</span></span> <span data-ttu-id="2cf34-136">既定値は、チャット ルームに接続したときに最初に表示されるメッセージの最大数を規定しているにすぎません。</span><span class="sxs-lookup"><span data-stu-id="2cf34-136">The default number simply determines the maximum number of messages that you initially see when connecting to a chat room.</span></span> 
  
   - <span data-ttu-id="2cf34-p110">[**最大ファイル サイズ (KB)**] で、各チャット履歴の最大ファイル サイズを選択します。既定値は 20 MB (20,000 KB) です。これは、システム内のチャット ルーム (対応する [**分類**] 設定でファイルのアップロードが有効化されているチャット ルーム) にアップロードできるファイルの最大サイズです。</span><span class="sxs-lookup"><span data-stu-id="2cf34-p110">In **Maximum file size (KB)**, select the maximum file size of each chat history. By default, the number is 20 MB (20,000 KB). This is the maximum size for a file that can be uploaded to any chat room in the system (for which file uploads are enabled by its corresponding **Category** setting).</span></span>
    
   - <span data-ttu-id="2cf34-140">[**参加者の更新制限**] で、参加者の更新の制限値を選択します。</span><span class="sxs-lookup"><span data-stu-id="2cf34-140">In **Participant update limit**, select the limit for participant updates.</span></span> <span data-ttu-id="2cf34-141">永続的なチャット サーバーは、接続しているユーザーの数がこの数に到達するまで、すべての参加者に名簿の情報 (ユーザーはチャット ルームに接続されている) を送信します。</span><span class="sxs-lookup"><span data-stu-id="2cf34-141">Persistent Chat Server sends roster information (who is connected to a chat room) to all participants until the number of connected users reaches this number.</span></span> <span data-ttu-id="2cf34-142">既定値は 75 です。</span><span class="sxs-lookup"><span data-stu-id="2cf34-142">By default, the number is 75.</span></span> <span data-ttu-id="2cf34-143">この制限を超えて、永続的なチャット サーバーが停止するルームには、接続されているクライアントに対して、名簿の更新を送信する特定の部屋に参加者の最大数を示します。</span><span class="sxs-lookup"><span data-stu-id="2cf34-143">This limit indicates the maximum number of participants in a given room beyond which Persistent Chat Server stops sending roster updates to connected clients about who is present in the room.</span></span>
    
   - <span data-ttu-id="2cf34-144">(オプション)。**ルーム管理 URL**] には、ルームの管理 URL を選択します。</span><span class="sxs-lookup"><span data-stu-id="2cf34-144">(Optional.) In **Room management URL**, select the room management URL.</span></span> <span data-ttu-id="2cf34-145">これは、web ベースのカスタム ルーム管理の URL です。</span><span class="sxs-lookup"><span data-stu-id="2cf34-145">This is the URL for a web-based custom room management.</span></span> <span data-ttu-id="2cf34-146">室の管理をカスタマイズする必要はありませんし、単に既定の設定を使用する場合は、このオプションを空白のままにします。</span><span class="sxs-lookup"><span data-stu-id="2cf34-146">If you don't need to customize room management, and you simply use the default setting, leave this option blank.</span></span> <span data-ttu-id="2cf34-147">URL を設定すると、部屋の内部および外部の両方の管理 URL として適用されます。</span><span class="sxs-lookup"><span data-stu-id="2cf34-147">After the URL is set, it is applied as both the internal and external room management URL.</span></span>
    
    <span data-ttu-id="2cf34-148">ルーム作成の操作性をカスタマイズし、特定のビジネス ・ ワークフローを含める場合は、永続的なチャット サーバー ソフトウェア開発キット (SDK) を使用してカスタム ルーム管理ソリューションを構築、それをどこかにホストして URL をここに配置します。。</span><span class="sxs-lookup"><span data-stu-id="2cf34-148">If you want to customize your room creation experience and include your specific business workflow, you can build a custom room management solution by using the Persistent Chat Server Software Development Kit (SDK), host it somewhere, and put the URL here.</span></span> <span data-ttu-id="2cf34-149">ユーザーがチャット ルームを表示または作成するときにカスタム チャット ルーム管理ソリューションを使用するように、この URL がクライアントに伝えられます。</span><span class="sxs-lookup"><span data-stu-id="2cf34-149">This URL is sent down to the client, so that when a user tries to view or create a room, he or she is directed to your custom room management solution.</span></span>
    
7. <span data-ttu-id="2cf34-150">[**確定**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="2cf34-150">Click **Commit**.</span></span>
    
## <a name="configure-options-for-a-specific-persistent-chat-server-pool"></a><span data-ttu-id="2cf34-151">特定の永続的なチャット サーバー プールのオプションを構成します。</span><span class="sxs-lookup"><span data-stu-id="2cf34-151">Configure options for a specific Persistent Chat Server pool</span></span>

<span data-ttu-id="2cf34-152">特定の永続的なチャット サーバー プールのオプションを構成します。</span><span class="sxs-lookup"><span data-stu-id="2cf34-152">To configure options for a specific Persistent Chat Server pool.</span></span>
  
1. <span data-ttu-id="2cf34-153">CsPersistentChatAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="2cf34-153">From a user account that is assigned to the CsPersistentChatAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="2cf34-154">**[スタート**] メニューから、Skype をビジネス サーバーのコントロール パネル] を選択や、ブラウザー ウィンドウを開く管理 URL を入力します。</span><span class="sxs-lookup"><span data-stu-id="2cf34-154">From the **Start** menu, select the Skype for Business Server Control Panel, or open a browser window, and then enter the Admin URL.</span></span>
    
3. <span data-ttu-id="2cf34-155">左側のナビゲーション バーで [**常設チャット**] をクリックし、[**常設チャットの構成**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="2cf34-155">In the left navigation bar, click **Persistent Chat**, and then click **Persistent Chat Configuration**.</span></span>
    
4. <span data-ttu-id="2cf34-156">[**常設チャットの構成**] ページで、[**新規**] をクリックし、[**プール構成**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="2cf34-156">On the **Persistent Chat Configuration** page, click **New**, and then click **Pool configuration**.</span></span>
    
5. <span data-ttu-id="2cf34-157">[**サービスの選択**] で構成される永続的なチャット サーバー プールに関連付けられているサービスを選択します。</span><span class="sxs-lookup"><span data-stu-id="2cf34-157">In **Select a Service**, select the service associated with the Persistent Chat Server pool to be configured.</span></span>
    
6. <span data-ttu-id="2cf34-158">[**新規 常設チャットの構成**] で、次の操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="2cf34-158">In **New Persistent Chat Configuration**, do the following:</span></span>
    
   - <span data-ttu-id="2cf34-p114">[**名前**] で、新しい構成設定の名前を指定します。既定では、サイト プール名が既に存在します。</span><span class="sxs-lookup"><span data-stu-id="2cf34-p114">In **Name**, specify a name for the new configuration settings. By default, the site pool name already exists.</span></span>
    
   - <span data-ttu-id="2cf34-p115">[**既定のチャット履歴**] で、最初の要求時にチャット ルームごとに処理されるチャット メッセージ数を定義します。既定値は 30 で、これはグローバルな既定値です。管理者はカテゴリごとにチャット履歴を無効にできます。</span><span class="sxs-lookup"><span data-stu-id="2cf34-p115">In **Default chat history**, define the number of chat messages that will be processed for each room upon first request. By default, the number is 30. This is the global default, and administrators can disable chat history per category.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="2cf34-164">永続的なチャット サーバーは、メモリ内のこれらのメッセージをキャッシュがより多くのメッセージをキャッシュする場合はこの値を大きくようにします。</span><span class="sxs-lookup"><span data-stu-id="2cf34-164">Persistent Chat Server will cache these messages in memory, so if you increase this number, more messages will be cached.</span></span> <span data-ttu-id="2cf34-165">履歴コンテンツには、検索を使用していつでもアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="2cf34-165">You can always access historical content by search.</span></span> <span data-ttu-id="2cf34-166">既定値は、チャット ルームに接続したときに最初に表示されるメッセージの最大数を規定しているにすぎません。</span><span class="sxs-lookup"><span data-stu-id="2cf34-166">The default number simply determines the maximum number of messages that you initially see when connecting to a chat room.</span></span> 
  
   - <span data-ttu-id="2cf34-p117">[**最大ファイル サイズ (KB)**] で、各チャット履歴の最大ファイル サイズを選択します。既定値は 20 MB (20,000 KB) です。これは、システム内のチャット ルーム (対応する [**分類**] 設定でファイルのアップロードが有効化されているチャット ルーム) にアップロードできるファイルの最大サイズです。</span><span class="sxs-lookup"><span data-stu-id="2cf34-p117">In **Maximum file size (KB)**, select the maximum file size of each chat history. By default, the number is 20 MB (20,000 KB). This is the maximum size for a file that can be uploaded to any chat room in the system (for which file uploads are enabled by its corresponding **Category** setting).</span></span>
    
   - <span data-ttu-id="2cf34-170">[**参加者の更新制限**] で、参加者の更新の制限値を選択します。</span><span class="sxs-lookup"><span data-stu-id="2cf34-170">In **Participant update limit**, select the limit for participant updates.</span></span> <span data-ttu-id="2cf34-171">永続的なチャット サーバーは、接続しているユーザーの数がこの数に到達するまで、すべての参加者に名簿の情報 (ユーザーはチャット ルームに接続されている) を送信します。</span><span class="sxs-lookup"><span data-stu-id="2cf34-171">Persistent Chat Server sends roster information (who is connected to a chat room) to all participants until the number of connected users reaches this number.</span></span> <span data-ttu-id="2cf34-172">既定値は 75 です。</span><span class="sxs-lookup"><span data-stu-id="2cf34-172">By default, the number is 75.</span></span> <span data-ttu-id="2cf34-173">この制限を超えて、永続的なチャット サーバーが停止するルームには、接続されているクライアントに対して、名簿の更新を送信する特定の部屋に参加者の最大数を示します。</span><span class="sxs-lookup"><span data-stu-id="2cf34-173">This limit indicates the maximum number of participants in a given room beyond which Persistent Chat Server stops sending roster updates to connected clients about who is present in the room.</span></span>
    
   - <span data-ttu-id="2cf34-174">[**ルームの管理 URL**] で、ルーム管理 URL を選択します。</span><span class="sxs-lookup"><span data-stu-id="2cf34-174">In **Room management URL**, select the room management URL.</span></span> <span data-ttu-id="2cf34-175">これは Web ベースのチャット ルーム管理用の URL です。</span><span class="sxs-lookup"><span data-stu-id="2cf34-175">This is the URL for a web-based room management deployment.</span></span> <span data-ttu-id="2cf34-176">室の管理をカスタマイズする必要はありませんし、単に既定の設定を使用する場合は、このオプションを空白のままにします。</span><span class="sxs-lookup"><span data-stu-id="2cf34-176">If you don't need to customize room management, and you simply use the default setting, leave this option blank.</span></span>
    
    <span data-ttu-id="2cf34-177">ルーム作成の操作性をカスタマイズし、特定のビジネス ・ ワークフローを含める場合は、永続的なチャット サーバー ソフトウェア開発キット (SDK) を使用してカスタム ルーム管理ソリューションを構築、それをどこかにホストして URL をここに配置します。。</span><span class="sxs-lookup"><span data-stu-id="2cf34-177">If you want to customize your room creation experience and include your specific business workflow, you can build a custom room management solution by using the Persistent Chat Server Software Development Kit (SDK), host it somewhere, and put the URL here.</span></span> <span data-ttu-id="2cf34-178">ユーザーがチャット ルームを表示または作成するときにカスタム チャット ルーム管理ソリューションを使用するように、この URL がクライアントに伝えられます。</span><span class="sxs-lookup"><span data-stu-id="2cf34-178">This URL is sent down to the client so that when a user tries to view/create a room, he or she is directed to your custom room management solution.</span></span>
    
7. <span data-ttu-id="2cf34-179">[**確定**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="2cf34-179">Click **Commit**.</span></span>
    

