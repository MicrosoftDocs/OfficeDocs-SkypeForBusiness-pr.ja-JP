---
title: 常設チャットの構成
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/27/2015
audience: ITPro
ms.topic: article
f1.keywords:
- ms.lync.lscp.PersistentChatConfig
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 3f2891e6-bad3-4a23-a345-b7de4cae3bd9
description: 常設チャットサーバーの展開では、多数の同時常設チャットルームをホストできます。 チャット ルームは、サーバーで一連のカテゴリに編成できます。 各チャット ルームは 1 つのカテゴリに属し、そのカテゴリからいくつかの設定を継承します。 この編成によって、業務目的に基づいて会話を識別するのに便利な構造が作成され、管理の委任および管理の簡素化が容易になります。
ms.openlocfilehash: 07c1043a67d5f1a64dbb53540fbd902341067b32
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/03/2020
ms.locfileid: "41686230"
---
# <a name="persistent-chat-configuration"></a><span data-ttu-id="bbb11-106">常設チャットの構成</span><span class="sxs-lookup"><span data-stu-id="bbb11-106">Persistent Chat Configuration</span></span>
 
<span data-ttu-id="bbb11-107">常設チャットサーバーの展開では、多数の同時常設チャットルームをホストできます。</span><span class="sxs-lookup"><span data-stu-id="bbb11-107">Your Persistent Chat Server deployment can host many concurrent Persistent Chat rooms.</span></span> <span data-ttu-id="bbb11-108">チャット ルームは、サーバーで一連のカテゴリに編成できます。</span><span class="sxs-lookup"><span data-stu-id="bbb11-108">Chat rooms can be organized into a set of categories on the server.</span></span> <span data-ttu-id="bbb11-109">各チャット ルームは 1 つのカテゴリに属し、そのカテゴリからいくつかの設定を継承します。</span><span class="sxs-lookup"><span data-stu-id="bbb11-109">Each chat room belongs to one category, and inherits some settings from that category.</span></span> <span data-ttu-id="bbb11-110">この編成によって、業務目的に基づいて会話を識別するのに便利な構造が作成され、管理の委任および管理の簡素化が容易になります。</span><span class="sxs-lookup"><span data-stu-id="bbb11-110">This organization creates a useful structure for identifying conversations, based on their business purpose, and facilitates delegated administration and simplified management.</span></span>
  
> [!NOTE]
> <span data-ttu-id="bbb11-111">チャットルームの管理機能の多くは、ユーザーに対して常設チャットを実行しているコンピューターでは利用できますが、 **cspersistentchatadministrator**ロールの常設チャット管理者は、カテゴリを作成または管理するためにコントロールパネルまたは管理シェルコマンドレットを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="bbb11-111">Although many of the management features of chat rooms are available in computers running Persistent Chat for the user, Persistent Chat Administrators (in the **cspersistentchatadministrator** role) must use either the control panel or management shell cmdlets to create or manage categories.</span></span>
  
<span data-ttu-id="bbb11-112">常設チャット管理者は、Skype for Business Server コントロールパネルまたは Windows PowerShell コマンドレットを使ってカテゴリの作成と管理を行い、組織内のユーザーのチャットルームへのアクセスを設計します。</span><span class="sxs-lookup"><span data-stu-id="bbb11-112">Persistent Chat Administrators use Skype for Business Server Control Panel or Windows PowerShell cmdlets to create and manage categories, and to design access for chat rooms for the users in their organization.</span></span>
  
<span data-ttu-id="bbb11-113">チャットルーム管理者は、1人または複数のチャットルームを管理する機能を備えています。このクライアントを使用して、会議室の作成と管理を行うことができます (または、ユーザーがカスタムソリューションとワークフローを作成して呼び出すことができます)。</span><span class="sxs-lookup"><span data-stu-id="bbb11-113">Persistent Chat room managers, who have the ability to manage one or more chat rooms, can use the client to launch a room management Web application to create and manage rooms (or customers can create custom solutions and workflows to be invoked).</span></span> <span data-ttu-id="bbb11-114">常設チャット</span><span class="sxs-lookup"><span data-stu-id="bbb11-114">Persistent Chat</span></span>
  
<span data-ttu-id="bbb11-115">常設チャット管理者は、コントロールパネルまたは Windows PowerShell コマンドレットを使用して、会議室の作成と管理を行うこともできます。</span><span class="sxs-lookup"><span data-stu-id="bbb11-115">Persistent Chat administrators can also use control panel or Windows PowerShell cmdlets to create and manage rooms.</span></span>
  
<span data-ttu-id="bbb11-p104">チャット ルームのマネージャーは、チャット ルームのカテゴリ変更を除いて、チャット ルームのすべてのプロパティに変更を加えることができます。チャット ルームのマネージャーが行う以下の操作は制限できません。</span><span class="sxs-lookup"><span data-stu-id="bbb11-p104">Chat room managers can make changes to all chat room properties, except for changing the category of the room. They cannot be restricted from performing the following actions:</span></span>
  
- <span data-ttu-id="bbb11-118">チャット ルームを無効にする</span><span class="sxs-lookup"><span data-stu-id="bbb11-118">Disabling a chat room</span></span>
    
- <span data-ttu-id="bbb11-119">チャット ルームの名前を変更する</span><span class="sxs-lookup"><span data-stu-id="bbb11-119">Changing a chat room name</span></span>
    
- <span data-ttu-id="bbb11-120">チャット ルームの説明を変更する</span><span class="sxs-lookup"><span data-stu-id="bbb11-120">Changing a chat room description</span></span>
    
- <span data-ttu-id="bbb11-121">チャット ルームの種類 (大会議室と標準) を変更する</span><span class="sxs-lookup"><span data-stu-id="bbb11-121">Changing a chat room type (Auditorium versus Normal)</span></span>
    
- <span data-ttu-id="bbb11-122">チャット ルームのプライバシーを変更する (開く、閉じる、非公開にする)</span><span class="sxs-lookup"><span data-stu-id="bbb11-122">Changing the privacy of a room (open versus closed versus secret)</span></span>
    
- <span data-ttu-id="bbb11-123">メンバーを追加または削除する</span><span class="sxs-lookup"><span data-stu-id="bbb11-123">Adding or removing members</span></span>
    
- <span data-ttu-id="bbb11-124">チャット ルーム マネージャーを追加または削除する</span><span class="sxs-lookup"><span data-stu-id="bbb11-124">Adding or removing chat room managers</span></span>
    
- <span data-ttu-id="bbb11-125">アドインを追加または削除する</span><span class="sxs-lookup"><span data-stu-id="bbb11-125">Adding or removing an add-in</span></span>
    
- <span data-ttu-id="bbb11-126">招待状などの設定を変更する (カテゴリによって許可された内容による)</span><span class="sxs-lookup"><span data-stu-id="bbb11-126">Changing settings such as invitations (according to what's permitted by the category)</span></span>
    
## <a name="tasks-that-you-can-perform"></a><span data-ttu-id="bbb11-127">実行できるタスク</span><span class="sxs-lookup"><span data-stu-id="bbb11-127">Tasks that you can perform</span></span>

<span data-ttu-id="bbb11-128">**常設チャットの構成**ページで、「常設チャット」オプションをグローバルに構成するか、特定のプールに対して、次のタスクを実行できます。</span><span class="sxs-lookup"><span data-stu-id="bbb11-128">You can perform the following tasks on the **Persistent Chat Configuration** page: configure Persistent Chat Server options globally or for a specific pool.</span></span>
  
## <a name="to-configure-persistent-chat-options-globally"></a><span data-ttu-id="bbb11-129">常設チャットのオプションをグローバルに構成するには</span><span class="sxs-lookup"><span data-stu-id="bbb11-129">To configure Persistent Chat options globally</span></span>

1. <span data-ttu-id="bbb11-130">CsPersistentChatAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="bbb11-130">From a user account that is assigned to the CsPersistentChatAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="bbb11-131">[**スタート**] メニューで、[Skype For business Server] コントロールパネルを選択するか、ブラウザーウィンドウを開き、管理 URL を入力します。</span><span class="sxs-lookup"><span data-stu-id="bbb11-131">From the **Start** menu, select the Skype for Business Server Control Panel or open a browser window, and then enter the Admin URL.</span></span>
    
3. <span data-ttu-id="bbb11-132">左側のナビゲーション バーで [**常設チャット**] をクリックし、[**常設チャットの構成**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="bbb11-132">In the left navigation bar, click **Persistent Chat**, and then click **Persistent Chat Configuration**.</span></span>
    
4. <span data-ttu-id="bbb11-133">[**常設チャットの構成**] ページで、[**新規] を**クリックし、[サイトの**構成**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="bbb11-133">On the **Persistent Chat Configuration** page, click **New,** and then click **Site configuration**.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="bbb11-134">サイトに展開されているすべての常設チャットサーバープールに構成を適用する場合は、このオプションを選びます。</span><span class="sxs-lookup"><span data-stu-id="bbb11-134">Choose this option if you want the configuration to be applied to all Persistent Chat Server pools deployed in the site.</span></span> <span data-ttu-id="bbb11-135">特定の常設チャットサーバープールに構成を適用する場合は、[**プール構成**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="bbb11-135">Click **Pool Configuration** if you want the configuration to be applied to a specific Persistent Chat Server pool.</span></span>
  
5. <span data-ttu-id="bbb11-136">[**サイトの選択**] で、常設チャットサーバーのサイト構成用に構成するサイトを選びます。</span><span class="sxs-lookup"><span data-stu-id="bbb11-136">In **Select a Site**, select the site to be configured for the Persistent Chat Server site configuration.</span></span>
    
6. <span data-ttu-id="bbb11-137">[**新規 常設チャットの構成**] で、次の操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="bbb11-137">In **New Persistent Chat Configuration**, do the following:</span></span>
    
   - <span data-ttu-id="bbb11-p106">[**名前**] で、新しい構成設定の名前を指定します。既定では、サイト名が既に存在します。</span><span class="sxs-lookup"><span data-stu-id="bbb11-p106">In **Name**, specify a name for the new configuration settings. By default, the site name already exists.</span></span>
    
   - <span data-ttu-id="bbb11-p107">[**既定のチャット履歴**] で、最初の要求時にチャット ルームごとに処理されるチャット メッセージ数を定義します。既定値は 30 で、これはグローバルな既定値です。管理者はカテゴリごとにチャット履歴を無効にできます。</span><span class="sxs-lookup"><span data-stu-id="bbb11-p107">In **Default chat history**, define the number of chat messages that will be processed for each room upon first request. By default, the number is 30. This is the global default, and administrators can disable chat history per category.</span></span>
    
     > [!IMPORTANT]
     > <span data-ttu-id="bbb11-143">常設チャットサーバーでは、これらのメッセージがメモリにキャッシュされるため、この数値を増やすと、より多くのメッセージがキャッシュされます。</span><span class="sxs-lookup"><span data-stu-id="bbb11-143">Persistent Chat Server will cache these messages in memory, so if you increase this number, more messages will be cached.</span></span> <span data-ttu-id="bbb11-144">履歴コンテンツには、検索を使用していつでもアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="bbb11-144">You can always access historical content by search.</span></span> <span data-ttu-id="bbb11-145">既定値は、チャット ルームに接続したときに最初に表示されるメッセージの最大数を規定しているにすぎません。</span><span class="sxs-lookup"><span data-stu-id="bbb11-145">The default number simply determines the maximum number of messages that you initially see when connecting to a chat room.</span></span> 
  
   - <span data-ttu-id="bbb11-p109">[**最大ファイル サイズ (KB)**] で、各チャット履歴の最大ファイル サイズを選択します。既定値は 20 MB (20,000 KB) です。これは、システム内のチャット ルーム (対応する [**分類**] 設定でファイルのアップロードが有効化されているチャット ルーム) にアップロードできるファイルの最大サイズです。</span><span class="sxs-lookup"><span data-stu-id="bbb11-p109">In **Maximum file size (KB)**, select the maximum file size of each chat history. By default, the number is 20 MB (20,000 KB). This is the maximum size for a file that can be uploaded to any chat room in the system (for which file uploads are enabled by its corresponding **Category** setting).</span></span>
    
   - <span data-ttu-id="bbb11-149">[**参加者の更新制限**] で、参加者の更新の制限値を選択します。</span><span class="sxs-lookup"><span data-stu-id="bbb11-149">In **Participant update limit**, select the limit for participant updates.</span></span> <span data-ttu-id="bbb11-150">常設チャットサーバーは、接続されているユーザーの数がこの番号に到達するまで、すべての参加者にリスト情報 (チャットルームに接続されているユーザー) を送信します。</span><span class="sxs-lookup"><span data-stu-id="bbb11-150">Persistent Chat Server sends roster information (who is connected to a chat room) to all participants until the number of connected users reaches this number.</span></span> <span data-ttu-id="bbb11-151">既定値は 75 です。</span><span class="sxs-lookup"><span data-stu-id="bbb11-151">By default, the number is 75.</span></span> <span data-ttu-id="bbb11-152">この制限は、常設チャットサーバーが、会議室に存在するユーザーに対して、接続されているクライアントに対して、リストの更新情報を送信するのを超えた、特定のルーム内の参加者の最大数を示します。</span><span class="sxs-lookup"><span data-stu-id="bbb11-152">This limit indicates the maximum number of participants in a given room beyond which Persistent Chat Server stops sending roster updates to connected clients about who is present in the room.</span></span>
    
   - <span data-ttu-id="bbb11-153">(省略可能)[ **Room MANAGEMENT url**] で、[会議室管理 url] を選びます。</span><span class="sxs-lookup"><span data-stu-id="bbb11-153">(Optional.) In **Room management URL**, select the room management URL.</span></span> <span data-ttu-id="bbb11-154">これは、web ベースのカスタムルーム管理の URL です。</span><span class="sxs-lookup"><span data-stu-id="bbb11-154">This is the URL for a web-based custom room management.</span></span> <span data-ttu-id="bbb11-155">Room management をカスタマイズする必要がなく、既定の設定を使用している場合は、このオプションを空白のままにします。</span><span class="sxs-lookup"><span data-stu-id="bbb11-155">If you don't need to customize room management, and you simply use the default setting, leave this option blank.</span></span> <span data-ttu-id="bbb11-156">URL を設定すると、その URL は、内部および外部の room 管理 URL の両方として適用されます。</span><span class="sxs-lookup"><span data-stu-id="bbb11-156">After the URL is set, it is applied as both the internal and external room management URL.</span></span>
    
     <span data-ttu-id="bbb11-157">会議室の作成環境をカスタマイズして、特定のビジネスワークフローを含める場合は、常設チャットサーバーソフトウェア開発キット (SDK) を使用して、カスタムルーム管理ソリューションを構築し、どこかにホストして、URL をここに入力します。</span><span class="sxs-lookup"><span data-stu-id="bbb11-157">If you want to customize your room creation experience and include your specific business workflow, you can build a custom room management solution by using the Persistent Chat Server Software Development Kit (SDK), host it somewhere, and put the URL here.</span></span> <span data-ttu-id="bbb11-158">ユーザーがチャット ルームを表示または作成するときにカスタム チャット ルーム管理ソリューションを使用するよう、この URL がクライアントに伝えられます。</span><span class="sxs-lookup"><span data-stu-id="bbb11-158">This URL is sent down to the client, so that when a user tries to view or create a room, he or she is directed to your custom room management solution.</span></span>
    
7. <span data-ttu-id="bbb11-159">[**確定**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="bbb11-159">Click **Commit**.</span></span>
    
## <a name="to-configure-persistent-chat-options-for-a-specific-persistent-chat-server-pool"></a><span data-ttu-id="bbb11-160">特定の常設チャットサーバープールの常設チャットオプションを構成するには</span><span class="sxs-lookup"><span data-stu-id="bbb11-160">To configure Persistent Chat options for a specific Persistent Chat Server pool</span></span>

1. <span data-ttu-id="bbb11-161">CsPersistentChatAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="bbb11-161">From a user account that is assigned to the CsPersistentChatAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="bbb11-162">[**スタート**] メニューで、[Skype For business Server] コントロールパネルを選択するか、ブラウザーウィンドウを開いて、管理者 URL を入力します。</span><span class="sxs-lookup"><span data-stu-id="bbb11-162">From the **Start** menu, select the Skype for Business Server Control Panel, or open a browser window, and then enter the Admin URL.</span></span>
    
3. <span data-ttu-id="bbb11-163">左側のナビゲーション バーで [**常設チャット**] をクリックし、[**常設チャットの構成**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="bbb11-163">In the left navigation bar, click **Persistent Chat**, and then click **Persistent Chat Configuration**.</span></span>
    
4. <span data-ttu-id="bbb11-164">[**常設チャットの構成**] ページで、[**新規**] をクリックし、[**プール構成**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="bbb11-164">On the **Persistent Chat Configuration** page, click **New**, and then click **Pool configuration**.</span></span>
    
5. <span data-ttu-id="bbb11-165">[**サービスの選択**] で、構成する常設チャットサーバープールに関連するサービスを選びます。</span><span class="sxs-lookup"><span data-stu-id="bbb11-165">In **Select a Service**, select the service associated with the Persistent Chat Server pool to be configured.</span></span>
    
6. <span data-ttu-id="bbb11-166">[**新規 常設チャットの構成**] で、次の操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="bbb11-166">In **New Persistent Chat Configuration**, do the following:</span></span>
    
   - <span data-ttu-id="bbb11-p113">[**名前**] で、新しい構成設定の名前を指定します。既定では、サイト プール名が既に存在します。</span><span class="sxs-lookup"><span data-stu-id="bbb11-p113">In **Name**, specify a name for the new configuration settings. By default, the site pool name already exists.</span></span>
    
   - <span data-ttu-id="bbb11-p114">[**既定のチャット履歴**] で、最初の要求時にチャット ルームごとに処理されるチャット メッセージ数を定義します。既定値は 30 で、これはグローバルな既定値です。管理者はカテゴリごとにチャット履歴を無効にできます。</span><span class="sxs-lookup"><span data-stu-id="bbb11-p114">In **Default chat history**, define the number of chat messages that will be processed for each room upon first request. By default, the number is 30. This is the global default, and administrators can disable chat history per category.</span></span>
    
     > [!IMPORTANT]
     > <span data-ttu-id="bbb11-172">常設チャットサーバーでは、これらのメッセージがメモリにキャッシュされるため、この数値を増やすと、より多くのメッセージがキャッシュされます。</span><span class="sxs-lookup"><span data-stu-id="bbb11-172">Persistent Chat Server will cache these messages in memory, so if you increase this number, more messages will be cached.</span></span> <span data-ttu-id="bbb11-173">履歴コンテンツには、検索を使用していつでもアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="bbb11-173">You can always access historical content by search.</span></span> <span data-ttu-id="bbb11-174">既定値は、チャット ルームに接続したときに最初に表示されるメッセージの最大数を規定しているにすぎません。</span><span class="sxs-lookup"><span data-stu-id="bbb11-174">The default number simply determines the maximum number of messages that you initially see when connecting to a chat room.</span></span> 
  
   - <span data-ttu-id="bbb11-p116">[**最大ファイル サイズ (KB)**] で、各チャット履歴の最大ファイル サイズを選択します。既定値は 20 MB (20,000 KB) です。これは、システム内のチャット ルーム (対応する [**分類**] 設定でファイルのアップロードが有効化されているチャット ルーム) にアップロードできるファイルの最大サイズです。</span><span class="sxs-lookup"><span data-stu-id="bbb11-p116">In **Maximum file size (KB)**, select the maximum file size of each chat history. By default, the number is 20 MB (20,000 KB). This is the maximum size for a file that can be uploaded to any chat room in the system (for which file uploads are enabled by its corresponding **Category** setting).</span></span>
    
   - <span data-ttu-id="bbb11-178">[**参加者の更新制限**] で、参加者の更新の制限値を選択します。</span><span class="sxs-lookup"><span data-stu-id="bbb11-178">In **Participant update limit**, select the limit for participant updates.</span></span> <span data-ttu-id="bbb11-179">常設チャットサーバーは、接続されているユーザーの数がこの番号に到達するまで、すべての参加者にリスト情報 (チャットルームに接続されているユーザー) を送信します。</span><span class="sxs-lookup"><span data-stu-id="bbb11-179">Persistent Chat Server sends roster information (who is connected to a chat room) to all participants until the number of connected users reaches this number.</span></span> <span data-ttu-id="bbb11-180">既定値は 75 です。</span><span class="sxs-lookup"><span data-stu-id="bbb11-180">By default, the number is 75.</span></span> <span data-ttu-id="bbb11-181">この制限は、常設チャットサーバーが、会議室に存在するユーザーに対して、接続されているクライアントに対して、リストの更新情報を送信するのを超えた、特定のルーム内の参加者の最大数を示します。</span><span class="sxs-lookup"><span data-stu-id="bbb11-181">This limit indicates the maximum number of participants in a given room beyond which Persistent Chat Server stops sending roster updates to connected clients about who is present in the room.</span></span>
    
   - <span data-ttu-id="bbb11-182">(オプション) [**ルームの管理 URL**] で、ルームの管理 URL を選択します。</span><span class="sxs-lookup"><span data-stu-id="bbb11-182">(Optional) In **Room management URL**, select the room management URL.</span></span> <span data-ttu-id="bbb11-183">これは Web ベースのチャット ルーム管理展開用の URL です。</span><span class="sxs-lookup"><span data-stu-id="bbb11-183">This is the URL for a web-based room management deployment.</span></span> <span data-ttu-id="bbb11-184">Room management をカスタマイズする必要がなく、既定の設定を使用している場合は、このオプションを空白のままにします。</span><span class="sxs-lookup"><span data-stu-id="bbb11-184">If you don't need to customize room management, and you simply use the default setting, leave this option blank.</span></span>
    
     <span data-ttu-id="bbb11-185">会議室の作成環境をカスタマイズして、特定のビジネスワークフローを含める場合は、常設チャットサーバーソフトウェア開発キット (SDK) を使用して、カスタムルーム管理ソリューションを構築し、どこかにホストして、URL をここに入力します。</span><span class="sxs-lookup"><span data-stu-id="bbb11-185">If you want to customize your room creation experience and include your specific business workflow, you can build a custom room management solution by using the Persistent Chat Server Software Development Kit (SDK), host it somewhere, and put the URL here.</span></span> <span data-ttu-id="bbb11-186">ユーザーがチャット ルームを表示または作成するときにカスタム チャット ルーム管理ソリューションを使用するよう、この URL がクライアントに伝えられます。</span><span class="sxs-lookup"><span data-stu-id="bbb11-186">This URL is sent down to the client, so that when a user tries to view/create a room, he or she is directed to your custom room management solution.</span></span>
    
7. <span data-ttu-id="bbb11-187">[**コミット**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="bbb11-187">Click **Commit**.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="bbb11-188">関連項目</span><span class="sxs-lookup"><span data-stu-id="bbb11-188">See also</span></span>

<span data-ttu-id="bbb11-189">常設チャットサーバーの機能と機能について詳しくは、「skype [For Business server 2015 での常設チャットサーバーの計画](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md)」、「skype for business server [2015 で](../../deploy/deploy-persistent-chat-server/deploy-persistent-chat-server.md)の常設チャットサーバーの展開」、「 [skype for Business server 2015 での常設チャットサーバーの管理](../../manage/persistent-chat/persistent-chat.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="bbb11-189">For details about Persistent Chat Server features and capabilities, see [Plan for Persistent Chat Server in Skype for Business Server 2015](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md), [Deploy Persistent Chat Server in Skype for Business Server 2015](../../deploy/deploy-persistent-chat-server/deploy-persistent-chat-server.md), and [Manage Persistent Chat Server in Skype for Business Server 2015](../../manage/persistent-chat/persistent-chat.md).</span></span>
  

