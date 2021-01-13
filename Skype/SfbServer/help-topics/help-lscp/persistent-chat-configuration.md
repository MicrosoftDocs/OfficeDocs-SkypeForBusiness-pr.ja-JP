---
title: 常設チャットの構成
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
- ms.lync.lscp.PersistentChatConfig
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 3f2891e6-bad3-4a23-a345-b7de4cae3bd9
description: 常設チャット サーバーの展開では、多数の常設チャット ルームを同時にホストできます。 チャット ルームはサーバー上で一連のカテゴリに分類できます。 チャット ルームはそれぞれ 1 つのカテゴリに属し、そのカテゴリからいくつかの設定を継承します。 このように体系化することで、会話を業務目的に基づいて識別するのに役立つ構造が作成され、管理の委任と簡素化が促進されます。
ms.openlocfilehash: ca059cd739093840028a6e9b952e12566ccfa5c0
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49829397"
---
# <a name="persistent-chat-configuration"></a><span data-ttu-id="98a6b-106">常設チャットの構成</span><span class="sxs-lookup"><span data-stu-id="98a6b-106">Persistent Chat Configuration</span></span>
 
<span data-ttu-id="98a6b-107">常設チャット サーバーの展開では、多数の常設チャット ルームを同時にホストできます。</span><span class="sxs-lookup"><span data-stu-id="98a6b-107">Your Persistent Chat Server deployment can host many concurrent Persistent Chat rooms.</span></span> <span data-ttu-id="98a6b-108">チャット ルームはサーバー上で一連のカテゴリに分類できます。</span><span class="sxs-lookup"><span data-stu-id="98a6b-108">Chat rooms can be organized into a set of categories on the server.</span></span> <span data-ttu-id="98a6b-109">チャット ルームはそれぞれ 1 つのカテゴリに属し、そのカテゴリからいくつかの設定を継承します。</span><span class="sxs-lookup"><span data-stu-id="98a6b-109">Each chat room belongs to one category, and inherits some settings from that category.</span></span> <span data-ttu-id="98a6b-110">このように体系化することで、会話を業務目的に基づいて識別するのに役立つ構造が作成され、管理の委任と簡素化が促進されます。</span><span class="sxs-lookup"><span data-stu-id="98a6b-110">This organization creates a useful structure for identifying conversations, based on their business purpose, and facilitates delegated administration and simplified management.</span></span>
  
> [!NOTE]
> <span data-ttu-id="98a6b-111">ユーザーの常設チャットを実行しているコンピューターでは、チャット ルームの管理機能の多くを使用できます。ただし、常設チャット管理者 **(cspersistentchatadministrator** の役割) は、コントロール パネルまたは管理シェル コマンドレットのいずれかを使用してカテゴリを作成または管理する必要があります。</span><span class="sxs-lookup"><span data-stu-id="98a6b-111">Although many of the management features of chat rooms are available in computers running Persistent Chat for the user, Persistent Chat Administrators (in the **cspersistentchatadministrator** role) must use either the control panel or management shell cmdlets to create or manage categories.</span></span>
  
<span data-ttu-id="98a6b-112">常設チャット管理者は、Skype for Business Server コントロール パネルまたは Windows PowerShell コマンドレットを使用して、カテゴリを作成および管理し、組織内のユーザーのチャット ルームへのアクセスを設計します。</span><span class="sxs-lookup"><span data-stu-id="98a6b-112">Persistent Chat Administrators use Skype for Business Server Control Panel or Windows PowerShell cmdlets to create and manage categories, and to design access for chat rooms for the users in their organization.</span></span>
  
<span data-ttu-id="98a6b-113">1 つ以上のチャット ルームを管理できる常設チャット ルームマネージャーは、クライアントを使用してルーム管理 Web アプリケーションを起動し、ルームを作成および管理できます (または、顧客はカスタム ソリューションとワークフローを作成して呼び出すことができます)。</span><span class="sxs-lookup"><span data-stu-id="98a6b-113">Persistent Chat room managers, who have the ability to manage one or more chat rooms, can use the client to launch a room management Web application to create and manage rooms (or customers can create custom solutions and workflows to be invoked).</span></span> <span data-ttu-id="98a6b-114">常設チャット</span><span class="sxs-lookup"><span data-stu-id="98a6b-114">Persistent Chat</span></span>
  
<span data-ttu-id="98a6b-115">常設チャット管理者は、コントロール パネルまたはWindows PowerShellを使用してルームを作成および管理することもできます。</span><span class="sxs-lookup"><span data-stu-id="98a6b-115">Persistent Chat administrators can also use control panel or Windows PowerShell cmdlets to create and manage rooms.</span></span>
  
<span data-ttu-id="98a6b-p104">チャット ルームのマネージャーは、ルームのカテゴリを変更することを除いて、チャット ルームのすべてのプロパティを変更できます。チャット ルームのマネージャーによる次の操作を制限することはできません。</span><span class="sxs-lookup"><span data-stu-id="98a6b-p104">Chat room managers can make changes to all chat room properties, except for changing the category of the room. They cannot be restricted from performing the following actions:</span></span>
  
- <span data-ttu-id="98a6b-118">チャット ルームを無効にする</span><span class="sxs-lookup"><span data-stu-id="98a6b-118">Disabling a chat room</span></span>
    
- <span data-ttu-id="98a6b-119">チャット ルームの名前を変更する</span><span class="sxs-lookup"><span data-stu-id="98a6b-119">Changing a chat room name</span></span>
    
- <span data-ttu-id="98a6b-120">チャット ルームの説明を変更する</span><span class="sxs-lookup"><span data-stu-id="98a6b-120">Changing a chat room description</span></span>
    
- <span data-ttu-id="98a6b-121">チャット ルームの種類 (大会議室と標準) を変更する</span><span class="sxs-lookup"><span data-stu-id="98a6b-121">Changing a chat room type (Auditorium versus Normal)</span></span>
    
- <span data-ttu-id="98a6b-122">ルームのプライバシーを変更する (オープンかクローズか秘密か)</span><span class="sxs-lookup"><span data-stu-id="98a6b-122">Changing the privacy of a room (open versus closed versus secret)</span></span>
    
- <span data-ttu-id="98a6b-123">メンバーを追加または削除する</span><span class="sxs-lookup"><span data-stu-id="98a6b-123">Adding or removing members</span></span>
    
- <span data-ttu-id="98a6b-124">チャット ルーム マネージャーを追加または削除する</span><span class="sxs-lookup"><span data-stu-id="98a6b-124">Adding or removing chat room managers</span></span>
    
- <span data-ttu-id="98a6b-125">アドインを追加または削除する</span><span class="sxs-lookup"><span data-stu-id="98a6b-125">Adding or removing an add-in</span></span>
    
- <span data-ttu-id="98a6b-126">招待などの設定を変更する (カテゴリで許可されている設定に従う)</span><span class="sxs-lookup"><span data-stu-id="98a6b-126">Changing settings such as invitations (according to what's permitted by the category)</span></span>
    
## <a name="tasks-that-you-can-perform"></a><span data-ttu-id="98a6b-127">実行できるタスク</span><span class="sxs-lookup"><span data-stu-id="98a6b-127">Tasks that you can perform</span></span>

<span data-ttu-id="98a6b-128">[常設チャットの構成] ページでは、常設チャット サーバーのオプションをグローバルまたは特定のプールに対して構成するタスクを実行できます。</span><span class="sxs-lookup"><span data-stu-id="98a6b-128">You can perform the following tasks on the **Persistent Chat Configuration** page: configure Persistent Chat Server options globally or for a specific pool.</span></span>
  
## <a name="to-configure-persistent-chat-options-globally"></a><span data-ttu-id="98a6b-129">常設チャット オプションをグローバルに構成するには</span><span class="sxs-lookup"><span data-stu-id="98a6b-129">To configure Persistent Chat options globally</span></span>

1. <span data-ttu-id="98a6b-130">CsPersistentChatAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="98a6b-130">From a user account that is assigned to the CsPersistentChatAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="98a6b-131">[スタート **] メニュー** から Skype for Business Server コントロール パネルを選択するか、ブラウザー ウィンドウを開いて管理 URL を入力します。</span><span class="sxs-lookup"><span data-stu-id="98a6b-131">From the **Start** menu, select the Skype for Business Server Control Panel or open a browser window, and then enter the Admin URL.</span></span>
    
3. <span data-ttu-id="98a6b-132">左側のナビゲーション バーで [**常設チャット**] をクリックし、[**常設チャットの構成**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="98a6b-132">In the left navigation bar, click **Persistent Chat**, and then click **Persistent Chat Configuration**.</span></span>
    
4. <span data-ttu-id="98a6b-133">[常設 **チャットの構成] ページで** 、[新規] **をクリック** し、[サイトの構成] **をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="98a6b-133">On the **Persistent Chat Configuration** page, click **New,** and then click **Site configuration**.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="98a6b-134">サイトに展開されている常設チャット サーバー のすべてのプールに構成を適用する場合は、このオプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="98a6b-134">Choose this option if you want the configuration to be applied to all Persistent Chat Server pools deployed in the site.</span></span> <span data-ttu-id="98a6b-135">構成 **を特定** の常設チャット サーバー プールに適用する場合は、[プールの構成] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="98a6b-135">Click **Pool Configuration** if you want the configuration to be applied to a specific Persistent Chat Server pool.</span></span>
  
5. <span data-ttu-id="98a6b-136">[ **サイトの選択]** で、常設チャット サーバー サイト構成用に構成するサイトを選択します。</span><span class="sxs-lookup"><span data-stu-id="98a6b-136">In **Select a Site**, select the site to be configured for the Persistent Chat Server site configuration.</span></span>
    
6. <span data-ttu-id="98a6b-137">[**新規 常設チャットの構成**] で、次の操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="98a6b-137">In **New Persistent Chat Configuration**, do the following:</span></span>
    
   - <span data-ttu-id="98a6b-p106">[**名前**] で、新しい構成設定の名前を指定します。既定では、サイト名は既に存在します。</span><span class="sxs-lookup"><span data-stu-id="98a6b-p106">In **Name**, specify a name for the new configuration settings. By default, the site name already exists.</span></span>
    
   - <span data-ttu-id="98a6b-p107">[**Default chat history**] で、最初の要求時にチャット ルームごとに処理されるチャット メッセージ数を定義します。既定値は 30 で、これはグローバルな既定値です。管理者はカテゴリごとにチャット履歴を無効にできます。</span><span class="sxs-lookup"><span data-stu-id="98a6b-p107">In **Default chat history**, define the number of chat messages that will be processed for each room upon first request. By default, the number is 30. This is the global default, and administrators can disable chat history per category.</span></span>
    
     > [!IMPORTANT]
     > <span data-ttu-id="98a6b-143">常設チャット サーバーは、これらのメッセージをメモリにキャッシュします。したがって、この数を増やすと、キャッシュされるメッセージの数が増える可能性があります。</span><span class="sxs-lookup"><span data-stu-id="98a6b-143">Persistent Chat Server will cache these messages in memory, so if you increase this number, more messages will be cached.</span></span> <span data-ttu-id="98a6b-144">履歴コンテンツには、検索を使用していつでもアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="98a6b-144">You can always access historical content by search.</span></span> <span data-ttu-id="98a6b-145">既定値は、チャット ルームに接続したときに最初に表示されるメッセージの最大数を規定しているにすぎません。</span><span class="sxs-lookup"><span data-stu-id="98a6b-145">The default number simply determines the maximum number of messages that you initially see when connecting to a chat room.</span></span> 
  
   - <span data-ttu-id="98a6b-p109">[**最大ファイル サイズ (KB)**] で、各チャット履歴の最大ファイル サイズを選択します。既定値は 20 MB (20,000 KB) です。これは、システム内のチャット ルーム (対応する [**分類**] 設定でファイルのアップロードが有効化されているチャット ルーム) にアップロードできるファイルの最大サイズです。</span><span class="sxs-lookup"><span data-stu-id="98a6b-p109">In **Maximum file size (KB)**, select the maximum file size of each chat history. By default, the number is 20 MB (20,000 KB). This is the maximum size for a file that can be uploaded to any chat room in the system (for which file uploads are enabled by its corresponding **Category** setting).</span></span>
    
   - <span data-ttu-id="98a6b-149">[**参加者の更新制限**] で、参加者の更新の制限値を選択します。</span><span class="sxs-lookup"><span data-stu-id="98a6b-149">In **Participant update limit**, select the limit for participant updates.</span></span> <span data-ttu-id="98a6b-150">常設チャット サーバーは、接続されているユーザーの数がこの数に達するまで、参加者全員に名簿情報 (チャット ルームに接続されているユーザー) を送信します。</span><span class="sxs-lookup"><span data-stu-id="98a6b-150">Persistent Chat Server sends roster information (who is connected to a chat room) to all participants until the number of connected users reaches this number.</span></span> <span data-ttu-id="98a6b-151">既定値は 75 です。</span><span class="sxs-lookup"><span data-stu-id="98a6b-151">By default, the number is 75.</span></span> <span data-ttu-id="98a6b-152">この制限は、常設チャット サーバーがルームに存在するユーザーに関する名簿の更新の送信を停止する特定のルームの参加者の最大数を示します。</span><span class="sxs-lookup"><span data-stu-id="98a6b-152">This limit indicates the maximum number of participants in a given room beyond which Persistent Chat Server stops sending roster updates to connected clients about who is present in the room.</span></span>
    
   - <span data-ttu-id="98a6b-153">(省略可能)[ **ルームの管理 URL] で**、ルーム管理 URL を選択します。</span><span class="sxs-lookup"><span data-stu-id="98a6b-153">(Optional.) In **Room management URL**, select the room management URL.</span></span> <span data-ttu-id="98a6b-154">これは Web をベースにした、ルームのカスタム管理用 URL です。</span><span class="sxs-lookup"><span data-stu-id="98a6b-154">This is the URL for a web-based custom room management.</span></span> <span data-ttu-id="98a6b-155">ルームの管理をカスタマイズする必要はありません。既定の設定を使用する場合は、このオプションを空白のままにします。</span><span class="sxs-lookup"><span data-stu-id="98a6b-155">If you don't need to customize room management, and you simply use the default setting, leave this option blank.</span></span> <span data-ttu-id="98a6b-156">URL を設定すると、内部と外部の両方のルームの管理 URL として適用されます。</span><span class="sxs-lookup"><span data-stu-id="98a6b-156">After the URL is set, it is applied as both the internal and external room management URL.</span></span>
    
     <span data-ttu-id="98a6b-157">ルームの作成エクスペリエンスをカスタマイズし、特定のビジネス ワークフローを含める場合は、常設チャット サーバー ソフトウェア開発キット (SDK) を使用してカスタム のチャット ルーム管理ソリューションを構築し、どこかでホストし、URL をここに置きます。</span><span class="sxs-lookup"><span data-stu-id="98a6b-157">If you want to customize your room creation experience and include your specific business workflow, you can build a custom room management solution by using the Persistent Chat Server Software Development Kit (SDK), host it somewhere, and put the URL here.</span></span> <span data-ttu-id="98a6b-158">ユーザーがチャット ルームを表示または作成するときにカスタム チャット ルーム管理ソリューションを使用するよう、この URL がクライアントに伝えられます。</span><span class="sxs-lookup"><span data-stu-id="98a6b-158">This URL is sent down to the client, so that when a user tries to view or create a room, he or she is directed to your custom room management solution.</span></span>
    
7. <span data-ttu-id="98a6b-159">[**確定**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="98a6b-159">Click **Commit**.</span></span>
    
## <a name="to-configure-persistent-chat-options-for-a-specific-persistent-chat-server-pool"></a><span data-ttu-id="98a6b-160">特定の常設チャット サーバー プールの常設チャット オプションを構成するには</span><span class="sxs-lookup"><span data-stu-id="98a6b-160">To configure Persistent Chat options for a specific Persistent Chat Server pool</span></span>

1. <span data-ttu-id="98a6b-161">CsPersistentChatAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="98a6b-161">From a user account that is assigned to the CsPersistentChatAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="98a6b-162">[スタート **] メニュー** から Skype for Business Server コントロール パネルを選択するか、ブラウザー ウィンドウを開いて管理 URL を入力します。</span><span class="sxs-lookup"><span data-stu-id="98a6b-162">From the **Start** menu, select the Skype for Business Server Control Panel, or open a browser window, and then enter the Admin URL.</span></span>
    
3. <span data-ttu-id="98a6b-163">左側のナビゲーション バーで [**常設チャット**] をクリックし、[**常設チャットの構成**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="98a6b-163">In the left navigation bar, click **Persistent Chat**, and then click **Persistent Chat Configuration**.</span></span>
    
4. <span data-ttu-id="98a6b-164">[**常設チャットの構成**] ページで、[**新規**] をクリックし、[**プール構成**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="98a6b-164">On the **Persistent Chat Configuration** page, click **New**, and then click **Pool configuration**.</span></span>
    
5. <span data-ttu-id="98a6b-165">[ **サービスの選択]** で、構成する常設チャット サーバー プールに関連付けられているサービスを選択します。</span><span class="sxs-lookup"><span data-stu-id="98a6b-165">In **Select a Service**, select the service associated with the Persistent Chat Server pool to be configured.</span></span>
    
6. <span data-ttu-id="98a6b-166">[**新規 常設チャットの構成**] で、次の操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="98a6b-166">In **New Persistent Chat Configuration**, do the following:</span></span>
    
   - <span data-ttu-id="98a6b-p113">[**名前**] で、新しい構成設定の名前を指定します。既定では、サイト プール名は既に存在します。</span><span class="sxs-lookup"><span data-stu-id="98a6b-p113">In **Name**, specify a name for the new configuration settings. By default, the site pool name already exists.</span></span>
    
   - <span data-ttu-id="98a6b-p114">[**Default chat history**] で、最初の要求時にチャット ルームごとに処理されるチャット メッセージ数を定義します。既定値は 30 で、これはグローバルな既定値です。管理者はカテゴリごとにチャット履歴を無効にできます。</span><span class="sxs-lookup"><span data-stu-id="98a6b-p114">In **Default chat history**, define the number of chat messages that will be processed for each room upon first request. By default, the number is 30. This is the global default, and administrators can disable chat history per category.</span></span>
    
     > [!IMPORTANT]
     > <span data-ttu-id="98a6b-172">常設チャット サーバーは、これらのメッセージをメモリにキャッシュします。そのため、この数を増やすと、キャッシュされるメッセージの数が増える可能性があります。</span><span class="sxs-lookup"><span data-stu-id="98a6b-172">Persistent Chat Server will cache these messages in memory, so if you increase this number, more messages will be cached.</span></span> <span data-ttu-id="98a6b-173">履歴コンテンツには、検索を使用していつでもアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="98a6b-173">You can always access historical content by search.</span></span> <span data-ttu-id="98a6b-174">既定値は、チャット ルームに接続したときに最初に表示されるメッセージの最大数を規定しているにすぎません。</span><span class="sxs-lookup"><span data-stu-id="98a6b-174">The default number simply determines the maximum number of messages that you initially see when connecting to a chat room.</span></span> 
  
   - <span data-ttu-id="98a6b-p116">[**最大ファイル サイズ (KB)**] で、各チャット履歴の最大ファイル サイズを選択します。既定値は 20 MB (20,000 KB) です。これは、システム内のチャット ルーム (対応する [**分類**] 設定でファイルのアップロードが有効化されているチャット ルーム) にアップロードできるファイルの最大サイズです。</span><span class="sxs-lookup"><span data-stu-id="98a6b-p116">In **Maximum file size (KB)**, select the maximum file size of each chat history. By default, the number is 20 MB (20,000 KB). This is the maximum size for a file that can be uploaded to any chat room in the system (for which file uploads are enabled by its corresponding **Category** setting).</span></span>
    
   - <span data-ttu-id="98a6b-178">[**参加者の更新制限**] で、参加者の更新の制限値を選択します。</span><span class="sxs-lookup"><span data-stu-id="98a6b-178">In **Participant update limit**, select the limit for participant updates.</span></span> <span data-ttu-id="98a6b-179">常設チャット サーバーは、接続されているユーザーの数がこの数に達するまで、参加者全員に名簿情報 (チャット ルームに接続されているユーザー) を送信します。</span><span class="sxs-lookup"><span data-stu-id="98a6b-179">Persistent Chat Server sends roster information (who is connected to a chat room) to all participants until the number of connected users reaches this number.</span></span> <span data-ttu-id="98a6b-180">既定値は 75 です。</span><span class="sxs-lookup"><span data-stu-id="98a6b-180">By default, the number is 75.</span></span> <span data-ttu-id="98a6b-181">この制限は、常設チャット サーバーがルームに存在するユーザーに関する名簿の更新の送信を停止する特定のルームの参加者の最大数を示します。</span><span class="sxs-lookup"><span data-stu-id="98a6b-181">This limit indicates the maximum number of participants in a given room beyond which Persistent Chat Server stops sending roster updates to connected clients about who is present in the room.</span></span>
    
   - <span data-ttu-id="98a6b-182">(省略可能)[ **ルームの管理 URL] で**、ルーム管理 URL を選択します。</span><span class="sxs-lookup"><span data-stu-id="98a6b-182">(Optional) In **Room management URL**, select the room management URL.</span></span> <span data-ttu-id="98a6b-183">これは Web ベースのチャット ルーム管理用の URL です。</span><span class="sxs-lookup"><span data-stu-id="98a6b-183">This is the URL for a web-based room management deployment.</span></span> <span data-ttu-id="98a6b-184">ルームの管理をカスタマイズする必要はありません。既定の設定を使用する場合は、このオプションを空白のままにします。</span><span class="sxs-lookup"><span data-stu-id="98a6b-184">If you don't need to customize room management, and you simply use the default setting, leave this option blank.</span></span>
    
     <span data-ttu-id="98a6b-185">ルームの作成エクスペリエンスをカスタマイズし、特定のビジネス ワークフローを含める場合は、常設チャット サーバー ソフトウェア開発キット (SDK) を使用してカスタム のチャット ルーム管理ソリューションを構築し、どこかでホストし、URL をここに置きます。</span><span class="sxs-lookup"><span data-stu-id="98a6b-185">If you want to customize your room creation experience and include your specific business workflow, you can build a custom room management solution by using the Persistent Chat Server Software Development Kit (SDK), host it somewhere, and put the URL here.</span></span> <span data-ttu-id="98a6b-186">この URL はクライアントに送信され、ユーザーがルームを表示または作成しようとすると、カスタム のルーム管理ソリューションにリダイレクトされます。</span><span class="sxs-lookup"><span data-stu-id="98a6b-186">This URL is sent down to the client, so that when a user tries to view/create a room, he or she is directed to your custom room management solution.</span></span>
    
7. <span data-ttu-id="98a6b-187">[**確定**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="98a6b-187">Click **Commit**.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="98a6b-188">関連項目</span><span class="sxs-lookup"><span data-stu-id="98a6b-188">See also</span></span>

<span data-ttu-id="98a6b-189">常設チャット サーバーの機能の詳細については [、「Plan for Persistent Chat Server in Skype for Business Server 2015,](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md) [Deploy Persistent Chat Server in Skype for Business Server 2015,](../../deploy/deploy-persistent-chat-server/deploy-persistent-chat-server.md)and [Manage Persistent Chat Server in Skype for Business Server 2015」](../../manage/persistent-chat/persistent-chat.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="98a6b-189">For details about Persistent Chat Server features and capabilities, see [Plan for Persistent Chat Server in Skype for Business Server 2015](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md), [Deploy Persistent Chat Server in Skype for Business Server 2015](../../deploy/deploy-persistent-chat-server/deploy-persistent-chat-server.md), and [Manage Persistent Chat Server in Skype for Business Server 2015](../../manage/persistent-chat/persistent-chat.md).</span></span>
  

