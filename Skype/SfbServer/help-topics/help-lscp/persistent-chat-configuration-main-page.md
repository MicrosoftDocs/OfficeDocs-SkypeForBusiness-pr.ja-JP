---
title: 常設チャット構成メイン ページ
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
- ms.lync.lscp.PersistentChatConfigMain
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 1e75d352-12cf-4548-9301-5d4c0e1c8f46
description: 常設チャットサーバーの展開では、多数の同時常設チャットルームをホストできます。 チャット ルームは、サーバーで一連のカテゴリに編成できます。 各チャット ルームは 1 つのカテゴリに属し、そのカテゴリからいくつかの設定を継承します。 この編成によって、業務目的に基づいて会話を識別するのに便利な構造が作成され、管理の委任および管理の簡素化が容易になります。
ms.openlocfilehash: 077ee0fe1058abc54568b47ea55af3c7d9238c7d
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2020
ms.locfileid: "41822540"
---
# <a name="persistent-chat-configuration-main-page"></a><span data-ttu-id="5ce7d-106">常設チャット構成メイン ページ</span><span class="sxs-lookup"><span data-stu-id="5ce7d-106">Persistent Chat Configuration Main Page</span></span>
 
<span data-ttu-id="5ce7d-107">常設チャットサーバーの展開では、多数の同時常設チャットルームをホストできます。</span><span class="sxs-lookup"><span data-stu-id="5ce7d-107">Your Persistent Chat Server deployment can host many concurrent Persistent Chat rooms.</span></span> <span data-ttu-id="5ce7d-108">チャット ルームは、サーバーで一連のカテゴリに編成できます。</span><span class="sxs-lookup"><span data-stu-id="5ce7d-108">Chat rooms can be organized into a set of categories on the server.</span></span> <span data-ttu-id="5ce7d-109">各チャット ルームは 1 つのカテゴリに属し、そのカテゴリからいくつかの設定を継承します。</span><span class="sxs-lookup"><span data-stu-id="5ce7d-109">Each chat room belongs to one category, and inherits some settings from that category.</span></span> <span data-ttu-id="5ce7d-110">この編成によって、業務目的に基づいて会話を識別するのに便利な構造が作成され、管理の委任および管理の簡素化が容易になります。</span><span class="sxs-lookup"><span data-stu-id="5ce7d-110">This organization creates a useful structure for identifying conversations, based on their business purpose, and facilitates delegated administration and simplified management.</span></span>
  
> [!NOTE]
> <span data-ttu-id="5ce7d-111">チャットルームの管理機能の多くは、常設チャットを実行しているコンピューターでも使用できますが、 **cspersistentchatadministrator**ロールの常設チャット管理者は、カテゴリを作成または管理するためにコントロールパネルまたは管理シェルコマンドレットを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="5ce7d-111">Although many of the management features of chat rooms are available in computers running Persistent Chat for the user, Persistent Chat Administrators (in the **cspersistentchatadministrator** role) must use the control panel or management shell cmdlets to create or manage categories.</span></span>
  
<span data-ttu-id="5ce7d-112">常設チャット管理者は、Skype for Business Server コントロールパネルまたは Windows PowerShell コマンドレットを使ってカテゴリの作成と管理を行い、組織内のユーザーのチャットルームへのアクセスを設計します。</span><span class="sxs-lookup"><span data-stu-id="5ce7d-112">Persistent Chat Administrators use Skype for Business Server Control Panel or Windows PowerShell cmdlets to create and manage categories, and to design access for chat rooms for the users in their organization.</span></span>
  
<span data-ttu-id="5ce7d-113">チャットルーム管理者は、1人または複数のチャットルームを管理する機能を備えています。このクライアントを使用して、会議室の作成と管理を行うことができます (または、ユーザーがカスタムソリューションとワークフローを作成して呼び出すことができます)。</span><span class="sxs-lookup"><span data-stu-id="5ce7d-113">Persistent Chat room managers, who have the ability to manage one or more chat rooms, can use the client to launch a room management Web application to create and manage rooms (or customers can create custom solutions and workflows to be invoked).</span></span> 
  
<span data-ttu-id="5ce7d-p103">チャット ルームのマネージャーは、チャット ルームのカテゴリ変更を除いて、チャット ルームのすべてのプロパティに変更を加えることができます。チャット ルームのマネージャーが行う以下の操作は制限できません。</span><span class="sxs-lookup"><span data-stu-id="5ce7d-p103">Chat room managers can make changes to all chat room properties, except for changing the category of the room. They cannot be restricted from performing the following actions:</span></span>
  
- <span data-ttu-id="5ce7d-116">チャット ルームを無効にする</span><span class="sxs-lookup"><span data-stu-id="5ce7d-116">Disabling a chat room</span></span>
    
- <span data-ttu-id="5ce7d-117">チャット ルームの名前を変更する</span><span class="sxs-lookup"><span data-stu-id="5ce7d-117">Changing a chat room name</span></span>
    
- <span data-ttu-id="5ce7d-118">チャット ルームの説明を変更する</span><span class="sxs-lookup"><span data-stu-id="5ce7d-118">Changing a chat room description</span></span>
    
- <span data-ttu-id="5ce7d-119">チャット ルームの種類 (大会議室と標準) を変更する</span><span class="sxs-lookup"><span data-stu-id="5ce7d-119">Changing a chat room type (Auditorium versus Normal)</span></span>
    
- <span data-ttu-id="5ce7d-120">チャット ルームのプライバシーを変更する (開く、閉じる、非公開にする)</span><span class="sxs-lookup"><span data-stu-id="5ce7d-120">Changing the privacy of a room (open versus closed versus secret)</span></span>
    
- <span data-ttu-id="5ce7d-121">メンバーを追加または削除する</span><span class="sxs-lookup"><span data-stu-id="5ce7d-121">Adding or removing members</span></span>
    
- <span data-ttu-id="5ce7d-122">チャット ルーム マネージャーを追加または削除する</span><span class="sxs-lookup"><span data-stu-id="5ce7d-122">Adding or removing chat room managers</span></span>
    
- <span data-ttu-id="5ce7d-123">アドインを追加または削除する</span><span class="sxs-lookup"><span data-stu-id="5ce7d-123">Adding or removing an add-in</span></span>
    
- <span data-ttu-id="5ce7d-124">招待状などの設定を変更する (カテゴリによって許可された内容による)</span><span class="sxs-lookup"><span data-stu-id="5ce7d-124">Changing settings such as invitations (according to what's permitted by the category)</span></span>
    
## <a name="tasks-that-you-can-perform"></a><span data-ttu-id="5ce7d-125">実行できるタスク</span><span class="sxs-lookup"><span data-stu-id="5ce7d-125">Tasks that you can perform</span></span>

<span data-ttu-id="5ce7d-126">**常設チャットの構成**ページで、次のタスクを実行できます。常設チャットサーバーオプションをグローバルまたは特定のプールに対して構成する</span><span class="sxs-lookup"><span data-stu-id="5ce7d-126">You can perform the following tasks on the **Persistent Chat Configuration** page: configure Persistent Chat Server options globally or for a specific pool</span></span>
  
## <a name="to-configure-persistent-chat-options-globally"></a><span data-ttu-id="5ce7d-127">常設チャットのオプションをグローバルに構成するには</span><span class="sxs-lookup"><span data-stu-id="5ce7d-127">To configure Persistent Chat options globally</span></span>

1. <span data-ttu-id="5ce7d-128">CsPersistentChatAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="5ce7d-128">From a user account that is assigned to the CsPersistentChatAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="5ce7d-129">[**スタート**] メニューで、[Skype For business Server] コントロールパネルを選択するか、ブラウザーウィンドウを開き、管理 URL を入力します。</span><span class="sxs-lookup"><span data-stu-id="5ce7d-129">From the **Start** menu, select the Skype for Business Server Control Panel or open a browser window, and then enter the Admin URL.</span></span>
    
3. <span data-ttu-id="5ce7d-130">左側のナビゲーション バーで [**常設チャット**] をクリックし、[**常設チャットの構成**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="5ce7d-130">In the left navigation bar, click **Persistent Chat**, and then click **Persistent Chat Configuration**.</span></span>
    
4. <span data-ttu-id="5ce7d-131">[**常設チャットの構成**] ページで、[**新規] を**クリックし、[サイトの**構成**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="5ce7d-131">On the **Persistent Chat Configuration** page, click **New,** and then click **Site configuration**.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="5ce7d-132">サイトに展開されているすべての常設チャットサーバープールに構成を適用する場合は、このオプションを選びます。</span><span class="sxs-lookup"><span data-stu-id="5ce7d-132">Choose this option if you want the configuration to be applied to all Persistent Chat Server pools deployed in the site.</span></span> <span data-ttu-id="5ce7d-133">特定の常設チャットサーバープールに構成を適用する場合は、[**プール構成**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="5ce7d-133">Click **Pool Configuration** if you want the configuration to be applied to a specific Persistent Chat Server pool.</span></span>
  
5. <span data-ttu-id="5ce7d-134">[**サイトの選択**] で、常設チャットサーバーのサイト構成用に構成するサイトを選びます。</span><span class="sxs-lookup"><span data-stu-id="5ce7d-134">In **Select a Site**, select the site to be configured for the Persistent Chat Server site configuration.</span></span>
    
6. <span data-ttu-id="5ce7d-135">[**新規 常設チャットの構成**] で、次の操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="5ce7d-135">In **New Persistent Chat Configuration**, do the following:</span></span>
    
   - <span data-ttu-id="5ce7d-p105">[**名前**] で、新しい構成設定の名前を指定します。既定では、サイト名が既に存在します。</span><span class="sxs-lookup"><span data-stu-id="5ce7d-p105">In **Name**, specify a name for the new configuration settings. By default, the site name already exists.</span></span>
    
   - <span data-ttu-id="5ce7d-p106">[**既定のチャット履歴**] で、最初の要求時にチャット ルームごとに処理されるチャット メッセージ数を定義します。既定値は 30 で、これはグローバルな既定値です。管理者はカテゴリごとにチャット履歴を無効にできます。</span><span class="sxs-lookup"><span data-stu-id="5ce7d-p106">In **Default chat history**, define the number of chat messages that will be processed for each room upon first request. By default, the number is 30. This is the global default, and administrators can disable chat history per category.</span></span>
    
     > [!IMPORTANT]
     > <span data-ttu-id="5ce7d-141">常設チャットサーバーでは、これらのメッセージがメモリにキャッシュされるため、この数値を増やすと、より多くのメッセージがキャッシュされます。</span><span class="sxs-lookup"><span data-stu-id="5ce7d-141">Persistent Chat Server will cache these messages in memory, so if you increase this number, more messages will be cached.</span></span> <span data-ttu-id="5ce7d-142">履歴コンテンツには、検索を使用していつでもアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="5ce7d-142">You can always access historical content by search.</span></span> <span data-ttu-id="5ce7d-143">既定値は、チャット ルームに接続したときに最初に表示されるメッセージの最大数を規定しているにすぎません。</span><span class="sxs-lookup"><span data-stu-id="5ce7d-143">The default number simply determines the maximum number of messages that you initially see when connecting to a chat room.</span></span> 
  
   - <span data-ttu-id="5ce7d-p108">[**最大ファイル サイズ (KB)**] で、各チャット履歴の最大ファイル サイズを選択します。既定値は 20 MB (20,000 KB) です。これは、システム内のチャット ルーム (対応する [**分類**] 設定でファイルのアップロードが有効化されているチャット ルーム) にアップロードできるファイルの最大サイズです。</span><span class="sxs-lookup"><span data-stu-id="5ce7d-p108">In **Maximum file size (KB)**, select the maximum file size of each chat history. By default, the number is 20 MB (20,000 KB). This is the maximum size for a file that can be uploaded to any chat room in the system (for which file uploads are enabled by its corresponding **Category** setting).</span></span>
    
   - <span data-ttu-id="5ce7d-147">[**参加者の更新制限**] で、参加者の更新の制限値を選択します。</span><span class="sxs-lookup"><span data-stu-id="5ce7d-147">In **Participant update limit**, select the limit for participant updates.</span></span> <span data-ttu-id="5ce7d-148">常設チャットサーバーは、接続されているユーザーの数がこの番号に到達するまで、すべての参加者にリスト情報 (チャットルームに接続されているユーザー) を送信します。</span><span class="sxs-lookup"><span data-stu-id="5ce7d-148">Persistent Chat Server sends roster information (who is connected to a chat room) to all participants until the number of connected users reaches this number.</span></span> <span data-ttu-id="5ce7d-149">既定値は 75 です。</span><span class="sxs-lookup"><span data-stu-id="5ce7d-149">By default, the number is 75.</span></span> <span data-ttu-id="5ce7d-150">この制限は、常設チャットサーバーが、会議室に存在するユーザーに対して、接続されているクライアントに対して、リストの更新情報を送信するのを超えた、特定のルーム内の参加者の最大数を示します。</span><span class="sxs-lookup"><span data-stu-id="5ce7d-150">This limit indicates the maximum number of participants in a given room beyond which Persistent Chat Server stops sending roster updates to connected clients about who is present in the room.</span></span>
    
   - <span data-ttu-id="5ce7d-151">(省略可能)[ **Room MANAGEMENT url**] で、[会議室管理 url] を選びます。</span><span class="sxs-lookup"><span data-stu-id="5ce7d-151">(Optional.) In **Room management URL**, select the room management URL.</span></span> <span data-ttu-id="5ce7d-152">これは、web ベースのカスタムルーム管理の URL です。</span><span class="sxs-lookup"><span data-stu-id="5ce7d-152">This is the URL for a web-based custom room management.</span></span> <span data-ttu-id="5ce7d-153">Room management をカスタマイズする必要がなく、既定の設定を使用している場合は、このオプションを空白のままにします。</span><span class="sxs-lookup"><span data-stu-id="5ce7d-153">If you don't need to customize room management, and you simply use the default setting, leave this option blank.</span></span> <span data-ttu-id="5ce7d-154">URL を設定すると、その URL は、内部および外部の room 管理 URL の両方として適用されます。</span><span class="sxs-lookup"><span data-stu-id="5ce7d-154">After the URL is set, it is applied as both the internal and external room management URL.</span></span>
    
     <span data-ttu-id="5ce7d-155">会議室の作成環境をカスタマイズして、特定のビジネスワークフローを含める場合は、常設チャットサーバーソフトウェア開発キット (SDK) を使用して、カスタムルーム管理ソリューションを構築し、どこかにホストして、URL をここに入力します。</span><span class="sxs-lookup"><span data-stu-id="5ce7d-155">If you want to customize your room creation experience and include your specific business workflow, you can build a custom room management solution by using the Persistent Chat Server Software Development Kit (SDK), host it somewhere, and put the URL here.</span></span> <span data-ttu-id="5ce7d-156">ユーザーがチャット ルームを表示または作成するときにカスタム チャット ルーム管理ソリューションを使用するよう、この URL がクライアントに伝えられます。</span><span class="sxs-lookup"><span data-stu-id="5ce7d-156">This URL is sent down to the client, so that when a user tries to view or create a room, he or she is directed to your custom room management solution.</span></span>
    
7. <span data-ttu-id="5ce7d-157">[**コミット**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="5ce7d-157">Click **Commit**.</span></span>
    
## <a name="to-configure-persistent-chat-options-for-a-specific-persistent-chat-server-pool"></a><span data-ttu-id="5ce7d-158">特定の常設チャットサーバープールの常設チャットオプションを構成するには</span><span class="sxs-lookup"><span data-stu-id="5ce7d-158">To configure Persistent Chat options for a specific Persistent Chat Server pool</span></span>

1. <span data-ttu-id="5ce7d-159">CsPersistentChatAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="5ce7d-159">From a user account that is assigned to the CsPersistentChatAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="5ce7d-160">[**スタート**] メニューで、[Skype For business Server] コントロールパネルを選択するか、ブラウザーウィンドウを開いて、管理者 URL を入力します。</span><span class="sxs-lookup"><span data-stu-id="5ce7d-160">From the **Start** menu, select the Skype for Business Server Control Panel, or open a browser window, and then enter the Admin URL.</span></span>
    
3. <span data-ttu-id="5ce7d-161">左側のナビゲーション バーで [**常設チャット**] をクリックし、[**常設チャットの構成**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="5ce7d-161">In the left navigation bar, click **Persistent Chat**, and then click **Persistent Chat Configuration**.</span></span>
    
4. <span data-ttu-id="5ce7d-162">[**常設チャットの構成**] ページで、[**新規**] をクリックし、[**プール構成**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="5ce7d-162">On the **Persistent Chat Configuration** page, click **New**, and then click **Pool configuration**.</span></span>
    
5. <span data-ttu-id="5ce7d-163">[**サービスの選択**] で、構成する常設チャットサーバープールに関連するサービスを選びます。</span><span class="sxs-lookup"><span data-stu-id="5ce7d-163">In **Select a Service**, select the service associated with the Persistent Chat Server pool to be configured.</span></span>
    
6. <span data-ttu-id="5ce7d-164">[**新規 常設チャットの構成**] で、次の操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="5ce7d-164">In **New Persistent Chat Configuration**, do the following:</span></span>
    
   - <span data-ttu-id="5ce7d-p112">[**名前**] で、新しい構成設定の名前を指定します。既定では、サイト プール名が既に存在します。</span><span class="sxs-lookup"><span data-stu-id="5ce7d-p112">In **Name**, specify a name for the new configuration settings. By default, the site pool name already exists.</span></span>
    
   - <span data-ttu-id="5ce7d-p113">[**既定のチャット履歴**] で、最初の要求時にチャット ルームごとに処理されるチャット メッセージ数を定義します。既定値は 30 で、これはグローバルな既定値です。管理者はカテゴリごとにチャット履歴を無効にできます。</span><span class="sxs-lookup"><span data-stu-id="5ce7d-p113">In **Default chat history**, define the number of chat messages that will be processed for each room upon first request. By default, the number is 30. This is the global default, and administrators can disable chat history per category.</span></span>
    
     > [!IMPORTANT]
     > <span data-ttu-id="5ce7d-170">常設チャットサーバーでは、これらのメッセージがメモリにキャッシュされるため、この数値を増やすと、より多くのメッセージがキャッシュされます。</span><span class="sxs-lookup"><span data-stu-id="5ce7d-170">Persistent Chat Server will cache these messages in memory, so if you increase this number, more messages will be cached.</span></span> <span data-ttu-id="5ce7d-171">履歴コンテンツには、検索を使用していつでもアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="5ce7d-171">You can always access historical content by search.</span></span> <span data-ttu-id="5ce7d-172">既定値は、チャット ルームに接続したときに最初に表示されるメッセージの最大数を規定しているにすぎません。</span><span class="sxs-lookup"><span data-stu-id="5ce7d-172">The default number simply determines the maximum number of messages that you initially see when connecting to a chat room.</span></span> 
  
   - <span data-ttu-id="5ce7d-p115">[**最大ファイル サイズ (KB)**] で、各チャット履歴の最大ファイル サイズを選択します。既定値は 20 MB (20,000 KB) です。これは、システム内のチャット ルーム (対応する [**分類**] 設定でファイルのアップロードが有効化されているチャット ルーム) にアップロードできるファイルの最大サイズです。</span><span class="sxs-lookup"><span data-stu-id="5ce7d-p115">In **Maximum file size (KB)**, select the maximum file size of each chat history. By default, the number is 20 MB (20,000 KB). This is the maximum size for a file that can be uploaded to any chat room in the system (for which file uploads are enabled by its corresponding **Category** setting).</span></span>
    
   - <span data-ttu-id="5ce7d-176">[**参加者の更新制限**] で、参加者の更新の制限値を選択します。</span><span class="sxs-lookup"><span data-stu-id="5ce7d-176">In **Participant update limit**, select the limit for participant updates.</span></span> <span data-ttu-id="5ce7d-177">常設チャットサーバーは、接続されているユーザーの数がこの番号に到達するまで、すべての参加者にリスト情報 (チャットルームに接続されているユーザー) を送信します。</span><span class="sxs-lookup"><span data-stu-id="5ce7d-177">Persistent Chat Server sends roster information (who is connected to a chat room) to all participants until the number of connected users reaches this number.</span></span> <span data-ttu-id="5ce7d-178">既定値は 75 です。</span><span class="sxs-lookup"><span data-stu-id="5ce7d-178">By default, the number is 75.</span></span> <span data-ttu-id="5ce7d-179">この制限は、常設チャットサーバーが、会議室に存在するユーザーに対して、接続されているクライアントに対して、リストの更新情報を送信するのを超えた、特定のルーム内の参加者の最大数を示します。</span><span class="sxs-lookup"><span data-stu-id="5ce7d-179">This limit indicates the maximum number of participants in a given room beyond which Persistent Chat Server stops sending roster updates to connected clients about who is present in the room.</span></span>
    
   - <span data-ttu-id="5ce7d-180">[**ルームの管理 URL**] で、ルーム管理 URL を選択します。</span><span class="sxs-lookup"><span data-stu-id="5ce7d-180">In **Room management URL**, select the room management URL.</span></span> <span data-ttu-id="5ce7d-181">これは Web ベースのチャット ルーム管理用の URL です。</span><span class="sxs-lookup"><span data-stu-id="5ce7d-181">This is the URL for a web-based room management deployment.</span></span> <span data-ttu-id="5ce7d-182">Room management をカスタマイズする必要がなく、既定の設定を使用している場合は、このオプションを空白のままにします。</span><span class="sxs-lookup"><span data-stu-id="5ce7d-182">If you don't need to customize room management, and you simply use the default setting, leave this option blank.</span></span>
    
     <span data-ttu-id="5ce7d-183">会議室の作成環境をカスタマイズして、特定のビジネスワークフローを含める場合は、常設チャットサーバーソフトウェア開発キット (SDK) を使用して、カスタムルーム管理ソリューションを構築し、どこかにホストして、URL をここに入力します。</span><span class="sxs-lookup"><span data-stu-id="5ce7d-183">If you want to customize your room creation experience and include your specific business workflow, you can build a custom room management solution by using the Persistent Chat Server Software Development Kit (SDK), host it somewhere, and put the URL here.</span></span> <span data-ttu-id="5ce7d-184">ユーザーがチャット ルームを表示または作成するときにカスタム チャット ルーム管理ソリューションを使用するよう、この URL がクライアントに伝えられます。</span><span class="sxs-lookup"><span data-stu-id="5ce7d-184">This URL is sent down to the client so that when a user tries to view/create a room, he or she is directed to your custom room management solution.</span></span>
    
7. <span data-ttu-id="5ce7d-185">[**コミット**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="5ce7d-185">Click **Commit**.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="5ce7d-186">関連項目</span><span class="sxs-lookup"><span data-stu-id="5ce7d-186">See also</span></span>

<span data-ttu-id="5ce7d-187">常設チャットサーバーの機能と機能について詳しくは、「skype [For Business server 2015 での常設チャットサーバーの計画](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md)」、「skype for business server [2015 で](../../deploy/deploy-persistent-chat-server/deploy-persistent-chat-server.md)の常設チャットサーバーの展開」、「 [skype for Business server 2015 での常設チャットサーバーの管理](../../manage/persistent-chat/persistent-chat.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="5ce7d-187">For details about Persistent Chat Server features and capabilities, see [Plan for Persistent Chat Server in Skype for Business Server 2015](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md), [Deploy Persistent Chat Server in Skype for Business Server 2015](../../deploy/deploy-persistent-chat-server/deploy-persistent-chat-server.md), and [Manage Persistent Chat Server in Skype for Business Server 2015](../../manage/persistent-chat/persistent-chat.md).</span></span>
  

