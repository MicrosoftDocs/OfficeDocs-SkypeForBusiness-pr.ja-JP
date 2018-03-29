---
title: 常設チャットの構成
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 3/27/2015
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.PersistentChatConfig
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 3f2891e6-bad3-4a23-a345-b7de4cae3bd9
description: 永続的なチャット サーバー展開では、永続的なチャット ルームの多くの同時実行をホストできます。 チャット ルームは、サーバーで一連のカテゴリに編成できます。 各チャット ルームは 1 つのカテゴリに属し、そのカテゴリからいくつかの設定を継承します。 この編成によって、業務目的に基づいて会話を識別するのに便利な構造が作成され、管理の委任および管理の簡素化が容易になります。
ms.openlocfilehash: c4408ebd4417d2cf825620837da018ef30f725c9
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/28/2018
---
# <a name="persistent-chat-configuration"></a><span data-ttu-id="d73f4-106">常設チャットの構成</span><span class="sxs-lookup"><span data-stu-id="d73f4-106">Persistent Chat Configuration</span></span>
 
<span data-ttu-id="d73f4-107">永続的なチャット サーバー展開では、永続的なチャット ルームの多くの同時実行をホストできます。</span><span class="sxs-lookup"><span data-stu-id="d73f4-107">Your Persistent Chat Server deployment can host many concurrent Persistent Chat rooms.</span></span> <span data-ttu-id="d73f4-108">チャット ルームは、サーバーで一連のカテゴリに編成できます。</span><span class="sxs-lookup"><span data-stu-id="d73f4-108">Chat rooms can be organized into a set of categories on the server.</span></span> <span data-ttu-id="d73f4-109">各チャット ルームは 1 つのカテゴリに属し、そのカテゴリからいくつかの設定を継承します。</span><span class="sxs-lookup"><span data-stu-id="d73f4-109">Each chat room belongs to one category, and inherits some settings from that category.</span></span> <span data-ttu-id="d73f4-110">この編成によって、業務目的に基づいて会話を識別するのに便利な構造が作成され、管理の委任および管理の簡素化が容易になります。</span><span class="sxs-lookup"><span data-stu-id="d73f4-110">This organization creates a useful structure for identifying conversations, based on their business purpose, and facilitates delegated administration and simplified management.</span></span>
  
> [!NOTE]
> <span data-ttu-id="d73f4-111">永続的なチャットの管理者 ( **cspersistentchatadministrator**ロール) する必要がありますか、コントロール パネルまたは管理シェルを使用して、ユーザーの永続的なチャットを実行しているコンピューターで利用できるチャット ルームの管理機能の多くが、作成またはカテゴリを管理するコマンドレットです。</span><span class="sxs-lookup"><span data-stu-id="d73f4-111">Although many of the management features of chat rooms are available in computers running Persistent Chat for the user, Persistent Chat Administrators (in the **cspersistentchatadministrator** role) must use either the control panel or management shell cmdlets to create or manage categories.</span></span>
  
<span data-ttu-id="d73f4-112">永続的なチャット管理者を使用して、Skype ビジネス サーバーのコントロール パネルまたは Windows PowerShell コマンドレットを作成し、カテゴリの管理およびチャット ルームのデザインへのアクセスを組織内のユーザーのです。</span><span class="sxs-lookup"><span data-stu-id="d73f4-112">Persistent Chat Administrators use Skype for Business Server Control Panel or Windows PowerShell cmdlets to create and manage categories, and to design access for chat rooms for the users in their organization.</span></span>
  
<span data-ttu-id="d73f4-113">永続的なチャット ルーム マネージャーは、1 つまたは複数のチャット ルームを管理することがあるは室の管理を作成し、会議室を管理する Web アプリケーションを起動するクライアントを使用することができます (または、お客様には、カスタム ソリューションと呼び出されるワークフローを作成できます)。</span><span class="sxs-lookup"><span data-stu-id="d73f4-113">Persistent Chat room managers, who have the ability to manage one or more chat rooms, can use the client to launch a room management Web application to create and manage rooms (or customers can create custom solutions and workflows to be invoked).</span></span> <span data-ttu-id="d73f4-114">常設チャット</span><span class="sxs-lookup"><span data-stu-id="d73f4-114">Persistent Chat</span></span>
  
<span data-ttu-id="d73f4-115">永続的なチャット管理者も使用できますコントロール パネルまたは Windows PowerShell コマンドレットを作成し、会議室を管理します。</span><span class="sxs-lookup"><span data-stu-id="d73f4-115">Persistent Chat administrators can also use control panel or Windows PowerShell cmdlets to create and manage rooms.</span></span>
  
<span data-ttu-id="d73f4-p104">チャット ルームのマネージャーは、チャット ルームのカテゴリ変更を除いて、チャット ルームのすべてのプロパティに変更を加えることができます。チャット ルームのマネージャーが行う以下の操作は制限できません。</span><span class="sxs-lookup"><span data-stu-id="d73f4-p104">Chat room managers can make changes to all chat room properties, except for changing the category of the room. They cannot be restricted from performing the following actions:</span></span>
  
- <span data-ttu-id="d73f4-118">チャット ルームを無効にする</span><span class="sxs-lookup"><span data-stu-id="d73f4-118">Disabling a chat room</span></span>
    
- <span data-ttu-id="d73f4-119">チャット ルームの名前を変更する</span><span class="sxs-lookup"><span data-stu-id="d73f4-119">Changing a chat room name</span></span>
    
- <span data-ttu-id="d73f4-120">チャット ルームの説明を変更する</span><span class="sxs-lookup"><span data-stu-id="d73f4-120">Changing a chat room description</span></span>
    
- <span data-ttu-id="d73f4-121">チャット ルームの種類 (大会議室と標準) を変更する</span><span class="sxs-lookup"><span data-stu-id="d73f4-121">Changing a chat room type (Auditorium versus Normal)</span></span>
    
- <span data-ttu-id="d73f4-122">チャット ルームのプライバシーを変更する (開く、閉じる、非公開にする)</span><span class="sxs-lookup"><span data-stu-id="d73f4-122">Changing the privacy of a room (open versus closed versus secret)</span></span>
    
- <span data-ttu-id="d73f4-123">メンバーを追加または削除する</span><span class="sxs-lookup"><span data-stu-id="d73f4-123">Adding or removing members</span></span>
    
- <span data-ttu-id="d73f4-124">チャット ルーム マネージャーを追加または削除する</span><span class="sxs-lookup"><span data-stu-id="d73f4-124">Adding or removing chat room managers</span></span>
    
- <span data-ttu-id="d73f4-125">アドインを追加または削除する</span><span class="sxs-lookup"><span data-stu-id="d73f4-125">Adding or removing an add-in</span></span>
    
- <span data-ttu-id="d73f4-126">基づくものは、カテゴリで許可されている) への招待などの設定を変更します。</span><span class="sxs-lookup"><span data-stu-id="d73f4-126">Changing settings such as invitations (according to what's permitted by the category)</span></span>
    
## <a name="tasks-that-you-can-perform"></a><span data-ttu-id="d73f4-127">実行できるタスク</span><span class="sxs-lookup"><span data-stu-id="d73f4-127">Tasks that you can perform</span></span>

<span data-ttu-id="d73f4-128">**永続的なチャットの構成**] ページで次の作業を行うことができます: グローバルに、または特定のプールには、永続的なチャット サーバー オプションを構成します。</span><span class="sxs-lookup"><span data-stu-id="d73f4-128">You can perform the following tasks on the **Persistent Chat Configuration** page: configure Persistent Chat Server options globally or for a specific pool.</span></span>
  
## <a name="to-configure-persistent-chat-options-globally"></a><span data-ttu-id="d73f4-129">永続的なチャット ルームのオプションをグローバルに構成するのには</span><span class="sxs-lookup"><span data-stu-id="d73f4-129">To configure Persistent Chat options globally</span></span>

1. <span data-ttu-id="d73f4-130">CsPersistentChatAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="d73f4-130">From a user account that is assigned to the CsPersistentChatAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="d73f4-131">**[スタート**] メニューから、Skype ビジネス サーバーのコントロール パネルのまたはブラウザー ウィンドウを開きし、管理 URL を入力します。</span><span class="sxs-lookup"><span data-stu-id="d73f4-131">From the **Start** menu, select the Skype for Business Server Control Panel or open a browser window, and then enter the Admin URL.</span></span>
    
3. <span data-ttu-id="d73f4-132">左側のナビゲーション バーで [**常設チャット**] をクリックし、[**常設チャットの構成**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d73f4-132">In the left navigation bar, click **Persistent Chat**, and then click **Persistent Chat Configuration**.</span></span>
    
4. <span data-ttu-id="d73f4-133">[**永続的なチャットの構成**] ページで、[**新規作成**] をクリックし、**サイトの構成**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d73f4-133">On the **Persistent Chat Configuration** page, click **New,** and then click **Site configuration**.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="d73f4-134">サイトに展開されるすべての永続的なチャット サーバー プールに適用する構成を使用する場合は、このオプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="d73f4-134">Choose this option if you want the configuration to be applied to all Persistent Chat Server pools deployed in the site.</span></span> <span data-ttu-id="d73f4-135">特定の永続的なチャット サーバー プールに適用する構成を使用する場合は、**プールの構成**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d73f4-135">Click **Pool Configuration** if you want the configuration to be applied to a specific Persistent Chat Server pool.</span></span>
  
5. <span data-ttu-id="d73f4-136">**サイトを選択**すると、永続的なチャット サーバーのサイト設定を構成するサイトを選択します。</span><span class="sxs-lookup"><span data-stu-id="d73f4-136">In **Select a Site**, select the site to be configured for the Persistent Chat Server site configuration.</span></span>
    
6. <span data-ttu-id="d73f4-137">[**新規 常設チャットの構成**] で、次の操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="d73f4-137">In **New Persistent Chat Configuration**, do the following:</span></span>
    
  - <span data-ttu-id="d73f4-p106">[**名前**] で、新しい構成設定の名前を指定します。既定では、サイト名が既に存在します。</span><span class="sxs-lookup"><span data-stu-id="d73f4-p106">In **Name**, specify a name for the new configuration settings. By default, the site name already exists.</span></span>
    
  - <span data-ttu-id="d73f4-p107">[**既定のチャット履歴**] で、最初の要求時にチャット ルームごとに処理されるチャット メッセージ数を定義します。既定値は 30 で、これはグローバルな既定値です。管理者はカテゴリごとにチャット履歴を無効にできます。</span><span class="sxs-lookup"><span data-stu-id="d73f4-p107">In **Default chat history**, define the number of chat messages that will be processed for each room upon first request. By default, the number is 30. This is the global default, and administrators can disable chat history per category.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="d73f4-143">永続的なチャット サーバーは、メモリ内のこれらのメッセージをキャッシュがより多くのメッセージをキャッシュする場合はこの値を大きくようにします。</span><span class="sxs-lookup"><span data-stu-id="d73f4-143">Persistent Chat Server will cache these messages in memory, so if you increase this number, more messages will be cached.</span></span> <span data-ttu-id="d73f4-144">履歴コンテンツには、検索を使用していつでもアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="d73f4-144">You can always access historical content by search.</span></span> <span data-ttu-id="d73f4-145">既定値は、チャット ルームに接続したときに最初に表示されるメッセージの最大数を規定しているにすぎません。</span><span class="sxs-lookup"><span data-stu-id="d73f4-145">The default number simply determines the maximum number of messages that you initially see when connecting to a chat room.</span></span> 
  
  - <span data-ttu-id="d73f4-p109">[**最大ファイル サイズ (KB)**] で、各チャット履歴の最大ファイル サイズを選択します。既定値は 20 MB (20,000 KB) です。これは、システム内のチャット ルーム (対応する [**分類**] 設定でファイルのアップロードが有効化されているチャット ルーム) にアップロードできるファイルの最大サイズです。</span><span class="sxs-lookup"><span data-stu-id="d73f4-p109">In **Maximum file size (KB)**, select the maximum file size of each chat history. By default, the number is 20 MB (20,000 KB). This is the maximum size for a file that can be uploaded to any chat room in the system (for which file uploads are enabled by its corresponding **Category** setting).</span></span>
    
  - <span data-ttu-id="d73f4-149">[**参加者の更新制限**] で、参加者の更新の制限値を選択します。</span><span class="sxs-lookup"><span data-stu-id="d73f4-149">In **Participant update limit**, select the limit for participant updates.</span></span> <span data-ttu-id="d73f4-150">永続的なチャット サーバーは、接続しているユーザーの数がこの数に到達するまで、すべての参加者に名簿の情報 (ユーザーはチャット ルームに接続されている) を送信します。</span><span class="sxs-lookup"><span data-stu-id="d73f4-150">Persistent Chat Server sends roster information (who is connected to a chat room) to all participants until the number of connected users reaches this number.</span></span> <span data-ttu-id="d73f4-151">既定値は 75 です。</span><span class="sxs-lookup"><span data-stu-id="d73f4-151">By default, the number is 75.</span></span> <span data-ttu-id="d73f4-152">この制限を超えて、永続的なチャット サーバーが停止するルームには、接続されているクライアントに対して、名簿の更新を送信する特定の部屋に参加者の最大数を示します。</span><span class="sxs-lookup"><span data-stu-id="d73f4-152">This limit indicates the maximum number of participants in a given room beyond which Persistent Chat Server stops sending roster updates to connected clients about who is present in the room.</span></span>
    
  - <span data-ttu-id="d73f4-153">(オプション)。**ルーム管理 URL**] には、ルームの管理 URL を選択します。</span><span class="sxs-lookup"><span data-stu-id="d73f4-153">(Optional.) In **Room management URL**, select the room management URL.</span></span> <span data-ttu-id="d73f4-154">これは、web ベースのカスタム ルーム管理の URL です。</span><span class="sxs-lookup"><span data-stu-id="d73f4-154">This is the URL for a web-based custom room management.</span></span> <span data-ttu-id="d73f4-155">室の管理をカスタマイズする必要はありませんし、単に既定の設定を使用する場合は、このオプションを空白のままにします。</span><span class="sxs-lookup"><span data-stu-id="d73f4-155">If you don't need to customize room management, and you simply use the default setting, leave this option blank.</span></span> <span data-ttu-id="d73f4-156">URL を設定すると、部屋の内部および外部の両方の管理 URL として適用されます。</span><span class="sxs-lookup"><span data-stu-id="d73f4-156">After the URL is set, it is applied as both the internal and external room management URL.</span></span>
    
    <span data-ttu-id="d73f4-157">ルーム作成の操作性をカスタマイズし、特定のビジネス ・ ワークフローを含める場合は、永続的なチャット サーバー ソフトウェア開発キット (SDK) を使用してカスタム ルーム管理ソリューションを構築、それをどこかにホストして URL をここに配置します。。</span><span class="sxs-lookup"><span data-stu-id="d73f4-157">If you want to customize your room creation experience and include your specific business workflow, you can build a custom room management solution by using the Persistent Chat Server Software Development Kit (SDK), host it somewhere, and put the URL here.</span></span> <span data-ttu-id="d73f4-158">ユーザーがチャット ルームを表示または作成するときにカスタム チャット ルーム管理ソリューションを使用するように、この URL がクライアントに伝えられます。</span><span class="sxs-lookup"><span data-stu-id="d73f4-158">This URL is sent down to the client, so that when a user tries to view or create a room, he or she is directed to your custom room management solution.</span></span>
    
7. <span data-ttu-id="d73f4-159">[**確定**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d73f4-159">Click **Commit**.</span></span>
    
## <a name="to-configure-persistent-chat-options-for-a-specific-persistent-chat-server-pool"></a><span data-ttu-id="d73f4-160">特定の永続的なチャット サーバー プールに永続的なチャットのオプションを構成するには</span><span class="sxs-lookup"><span data-stu-id="d73f4-160">To configure Persistent Chat options for a specific Persistent Chat Server pool</span></span>

1. <span data-ttu-id="d73f4-161">CsPersistentChatAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="d73f4-161">From a user account that is assigned to the CsPersistentChatAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="d73f4-162">**[スタート**] メニューから、Skype をビジネス サーバーのコントロール パネル] を選択や、ブラウザー ウィンドウを開く管理 URL を入力します。</span><span class="sxs-lookup"><span data-stu-id="d73f4-162">From the **Start** menu, select the Skype for Business Server Control Panel, or open a browser window, and then enter the Admin URL.</span></span>
    
3. <span data-ttu-id="d73f4-163">左側のナビゲーション バーで [**常設チャット**] をクリックし、[**常設チャットの構成**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d73f4-163">In the left navigation bar, click **Persistent Chat**, and then click **Persistent Chat Configuration**.</span></span>
    
4. <span data-ttu-id="d73f4-164">[**常設チャットの構成**] ページで、[**新規**] をクリックし、[**プール構成**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d73f4-164">On the **Persistent Chat Configuration** page, click **New**, and then click **Pool configuration**.</span></span>
    
5. <span data-ttu-id="d73f4-165">[**サービスの選択**] で構成される永続的なチャット サーバー プールに関連付けられているサービスを選択します。</span><span class="sxs-lookup"><span data-stu-id="d73f4-165">In **Select a Service**, select the service associated with the Persistent Chat Server pool to be configured.</span></span>
    
6. <span data-ttu-id="d73f4-166">[**新規 常設チャットの構成**] で、次の操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="d73f4-166">In **New Persistent Chat Configuration**, do the following:</span></span>
    
  - <span data-ttu-id="d73f4-p113">[**名前**] で、新しい構成設定の名前を指定します。既定では、サイト プール名が既に存在します。</span><span class="sxs-lookup"><span data-stu-id="d73f4-p113">In **Name**, specify a name for the new configuration settings. By default, the site pool name already exists.</span></span>
    
  - <span data-ttu-id="d73f4-p114">[**既定のチャット履歴**] で、最初の要求時にチャット ルームごとに処理されるチャット メッセージ数を定義します。既定値は 30 で、これはグローバルな既定値です。管理者はカテゴリごとにチャット履歴を無効にできます。</span><span class="sxs-lookup"><span data-stu-id="d73f4-p114">In **Default chat history**, define the number of chat messages that will be processed for each room upon first request. By default, the number is 30. This is the global default, and administrators can disable chat history per category.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="d73f4-172">永続的なチャット サーバーは、メモリ内のこれらのメッセージをキャッシュがより多くのメッセージをキャッシュする場合はこの値を大きくようにします。</span><span class="sxs-lookup"><span data-stu-id="d73f4-172">Persistent Chat Server will cache these messages in memory, so if you increase this number, more messages will be cached.</span></span> <span data-ttu-id="d73f4-173">履歴コンテンツには、検索を使用していつでもアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="d73f4-173">You can always access historical content by search.</span></span> <span data-ttu-id="d73f4-174">既定値は、チャット ルームに接続したときに最初に表示されるメッセージの最大数を規定しているにすぎません。</span><span class="sxs-lookup"><span data-stu-id="d73f4-174">The default number simply determines the maximum number of messages that you initially see when connecting to a chat room.</span></span> 
  
  - <span data-ttu-id="d73f4-p116">[**最大ファイル サイズ (KB)**] で、各チャット履歴の最大ファイル サイズを選択します。既定値は 20 MB (20,000 KB) です。これは、システム内のチャット ルーム (対応する [**分類**] 設定でファイルのアップロードが有効化されているチャット ルーム) にアップロードできるファイルの最大サイズです。</span><span class="sxs-lookup"><span data-stu-id="d73f4-p116">In **Maximum file size (KB)**, select the maximum file size of each chat history. By default, the number is 20 MB (20,000 KB). This is the maximum size for a file that can be uploaded to any chat room in the system (for which file uploads are enabled by its corresponding **Category** setting).</span></span>
    
  - <span data-ttu-id="d73f4-178">[**参加者の更新制限**] で、参加者の更新の制限値を選択します。</span><span class="sxs-lookup"><span data-stu-id="d73f4-178">In **Participant update limit**, select the limit for participant updates.</span></span> <span data-ttu-id="d73f4-179">永続的なチャット サーバーは、接続しているユーザーの数がこの数に到達するまで、すべての参加者に名簿の情報 (ユーザーはチャット ルームに接続されている) を送信します。</span><span class="sxs-lookup"><span data-stu-id="d73f4-179">Persistent Chat Server sends roster information (who is connected to a chat room) to all participants until the number of connected users reaches this number.</span></span> <span data-ttu-id="d73f4-180">既定値は 75 です。</span><span class="sxs-lookup"><span data-stu-id="d73f4-180">By default, the number is 75.</span></span> <span data-ttu-id="d73f4-181">この制限を超えて、永続的なチャット サーバーが停止するルームには、接続されているクライアントに対して、名簿の更新を送信する特定の部屋に参加者の最大数を示します。</span><span class="sxs-lookup"><span data-stu-id="d73f4-181">This limit indicates the maximum number of participants in a given room beyond which Persistent Chat Server stops sending roster updates to connected clients about who is present in the room.</span></span>
    
  - <span data-ttu-id="d73f4-182">(オプション) [**ルームの管理 URL**] で、ルームの管理 URL を選択します。</span><span class="sxs-lookup"><span data-stu-id="d73f4-182">(Optional) In **Room management URL**, select the room management URL.</span></span> <span data-ttu-id="d73f4-183">これは Web ベースのチャット ルーム管理展開用の URL です。</span><span class="sxs-lookup"><span data-stu-id="d73f4-183">This is the URL for a web-based room management deployment.</span></span> <span data-ttu-id="d73f4-184">室の管理をカスタマイズする必要はありませんし、単に既定の設定を使用する場合は、このオプションを空白のままにします。</span><span class="sxs-lookup"><span data-stu-id="d73f4-184">If you don't need to customize room management, and you simply use the default setting, leave this option blank.</span></span>
    
    <span data-ttu-id="d73f4-185">ルーム作成の操作性をカスタマイズし、特定のビジネス ・ ワークフローを含める場合は、永続的なチャット サーバー ソフトウェア開発キット (SDK) を使用してカスタム ルーム管理ソリューションを構築、それをどこかにホストして URL をここに配置します。。</span><span class="sxs-lookup"><span data-stu-id="d73f4-185">If you want to customize your room creation experience and include your specific business workflow, you can build a custom room management solution by using the Persistent Chat Server Software Development Kit (SDK), host it somewhere, and put the URL here.</span></span> <span data-ttu-id="d73f4-186">ユーザーがチャット ルームを表示または作成するときにカスタム チャット ルーム管理ソリューションを使用するよう、この URL がクライアントに伝えられます。</span><span class="sxs-lookup"><span data-stu-id="d73f4-186">This URL is sent down to the client, so that when a user tries to view/create a room, he or she is directed to your custom room management solution.</span></span>
    
7. <span data-ttu-id="d73f4-187">[**コミット**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d73f4-187">Click **Commit**.</span></span>
    
### 

<span data-ttu-id="d73f4-188">持続チャット サーバーで永続的なチャット サーバーの機能と機能に関する詳細は、[ビジネス サーバー 2015 の Skype での永続的なチャット サーバーの計画](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md)、[ビジネス サーバー 2015 の Skype で永続的なチャット サーバーを展開](../../deploy/deploy-persistent-chat-server/deploy-persistent-chat-server.md)、および管理を[参照してください。ビジネス サーバー 2015 の Skype で](../../manage/persistent-chat/persistent-chat.md)。</span><span class="sxs-lookup"><span data-stu-id="d73f4-188">For details about Persistent Chat Server features and capabilities, see [Plan for Persistent Chat Server in Skype for Business Server 2015](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md), [Deploy Persistent Chat Server in Skype for Business Server 2015](../../deploy/deploy-persistent-chat-server/deploy-persistent-chat-server.md), and [Manage Persistent Chat Server in Skype for Business Server 2015](../../manage/persistent-chat/persistent-chat.md).</span></span>
  

