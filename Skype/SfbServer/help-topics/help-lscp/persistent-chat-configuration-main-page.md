---
title: 常設チャット構成メイン ページ
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 3/27/2015
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.PersistentChatConfigMain
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 1e75d352-12cf-4548-9301-5d4c0e1c8f46
description: 永続的なチャット サーバー展開では、永続的なチャット ルームの多くの同時実行をホストできます。 チャット ルームは、サーバーで一連のカテゴリに編成できます。 各チャット ルームは 1 つのカテゴリに属し、そのカテゴリからいくつかの設定を継承します。 この編成によって、業務目的に基づいて会話を識別するのに便利な構造が作成され、管理の委任および管理の簡素化が容易になります。
ms.openlocfilehash: a1995f5d6049bc861e1aa79a3932d734d4002026
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/27/2019
ms.locfileid: "30879105"
---
# <a name="persistent-chat-configuration-main-page"></a><span data-ttu-id="98753-106">常設チャット構成メイン ページ</span><span class="sxs-lookup"><span data-stu-id="98753-106">Persistent Chat Configuration Main Page</span></span>
 
<span data-ttu-id="98753-107">永続的なチャット サーバー展開では、永続的なチャット ルームの多くの同時実行をホストできます。</span><span class="sxs-lookup"><span data-stu-id="98753-107">Your Persistent Chat Server deployment can host many concurrent Persistent Chat rooms.</span></span> <span data-ttu-id="98753-108">チャット ルームは、サーバーで一連のカテゴリに編成できます。</span><span class="sxs-lookup"><span data-stu-id="98753-108">Chat rooms can be organized into a set of categories on the server.</span></span> <span data-ttu-id="98753-109">各チャット ルームは 1 つのカテゴリに属し、そのカテゴリからいくつかの設定を継承します。</span><span class="sxs-lookup"><span data-stu-id="98753-109">Each chat room belongs to one category, and inherits some settings from that category.</span></span> <span data-ttu-id="98753-110">この編成によって、業務目的に基づいて会話を識別するのに便利な構造が作成され、管理の委任および管理の簡素化が容易になります。</span><span class="sxs-lookup"><span data-stu-id="98753-110">This organization creates a useful structure for identifying conversations, based on their business purpose, and facilitates delegated administration and simplified management.</span></span>
  
> [!NOTE]
> <span data-ttu-id="98753-111">( **Cspersistentchatadministrator**ロール) で、永続的なチャット管理者がコントロール パネルまたは管理シェル コマンドレットを使用する必要がありますユーザーの永続的なチャットを実行しているコンピューターで利用できるチャット ルームの管理機能の多くが、カテゴリの管理を作成または取得します。</span><span class="sxs-lookup"><span data-stu-id="98753-111">Although many of the management features of chat rooms are available in computers running Persistent Chat for the user, Persistent Chat Administrators (in the **cspersistentchatadministrator** role) must use the control panel or management shell cmdlets to create or manage categories.</span></span>
  
<span data-ttu-id="98753-112">永続的なチャット管理者を使用して、Skype ビジネス サーバーのコントロール パネルまたは Windows PowerShell コマンドレットを作成し、カテゴリの管理およびチャット ルームのデザインへのアクセスを組織内のユーザーのです。</span><span class="sxs-lookup"><span data-stu-id="98753-112">Persistent Chat Administrators use Skype for Business Server Control Panel or Windows PowerShell cmdlets to create and manage categories, and to design access for chat rooms for the users in their organization.</span></span>
  
<span data-ttu-id="98753-113">永続的なチャット ルーム マネージャーは、1 つまたは複数のチャット ルームを管理することがあるは室の管理を作成し、会議室を管理する Web アプリケーションを起動するクライアントを使用することができます (または、お客様には、カスタム ソリューションと呼び出されるワークフローを作成できます)。</span><span class="sxs-lookup"><span data-stu-id="98753-113">Persistent Chat room managers, who have the ability to manage one or more chat rooms, can use the client to launch a room management Web application to create and manage rooms (or customers can create custom solutions and workflows to be invoked).</span></span> 
  
<span data-ttu-id="98753-p103">チャット ルームのマネージャーは、チャット ルームのカテゴリ変更を除いて、チャット ルームのすべてのプロパティに変更を加えることができます。チャット ルームのマネージャーが行う以下の操作は制限できません。</span><span class="sxs-lookup"><span data-stu-id="98753-p103">Chat room managers can make changes to all chat room properties, except for changing the category of the room. They cannot be restricted from performing the following actions:</span></span>
  
- <span data-ttu-id="98753-116">チャット ルームを無効にする</span><span class="sxs-lookup"><span data-stu-id="98753-116">Disabling a chat room</span></span>
    
- <span data-ttu-id="98753-117">チャット ルームの名前を変更する</span><span class="sxs-lookup"><span data-stu-id="98753-117">Changing a chat room name</span></span>
    
- <span data-ttu-id="98753-118">チャット ルームの説明を変更する</span><span class="sxs-lookup"><span data-stu-id="98753-118">Changing a chat room description</span></span>
    
- <span data-ttu-id="98753-119">チャット ルームの種類 (大会議室と標準) を変更する</span><span class="sxs-lookup"><span data-stu-id="98753-119">Changing a chat room type (Auditorium versus Normal)</span></span>
    
- <span data-ttu-id="98753-120">チャット ルームのプライバシーを変更する (開く、閉じる、非公開にする)</span><span class="sxs-lookup"><span data-stu-id="98753-120">Changing the privacy of a room (open versus closed versus secret)</span></span>
    
- <span data-ttu-id="98753-121">メンバーを追加または削除する</span><span class="sxs-lookup"><span data-stu-id="98753-121">Adding or removing members</span></span>
    
- <span data-ttu-id="98753-122">チャット ルーム マネージャーを追加または削除する</span><span class="sxs-lookup"><span data-stu-id="98753-122">Adding or removing chat room managers</span></span>
    
- <span data-ttu-id="98753-123">アドインを追加または削除する</span><span class="sxs-lookup"><span data-stu-id="98753-123">Adding or removing an add-in</span></span>
    
- <span data-ttu-id="98753-124">基づくものは、カテゴリで許可されている) への招待などの設定を変更します。</span><span class="sxs-lookup"><span data-stu-id="98753-124">Changing settings such as invitations (according to what's permitted by the category)</span></span>
    
## <a name="tasks-that-you-can-perform"></a><span data-ttu-id="98753-125">実行できるタスク</span><span class="sxs-lookup"><span data-stu-id="98753-125">Tasks that you can perform</span></span>

<span data-ttu-id="98753-126">**永続的なチャットの構成**] ページで次の作業を行うことができます: グローバルに、または特定のプールには、永続的なチャット サーバー オプションを構成します。</span><span class="sxs-lookup"><span data-stu-id="98753-126">You can perform the following tasks on the **Persistent Chat Configuration** page: configure Persistent Chat Server options globally or for a specific pool</span></span>
  
## <a name="to-configure-persistent-chat-options-globally"></a><span data-ttu-id="98753-127">永続的なチャット ルームのオプションをグローバルに構成するのには</span><span class="sxs-lookup"><span data-stu-id="98753-127">To configure Persistent Chat options globally</span></span>

1. <span data-ttu-id="98753-128">CsPersistentChatAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="98753-128">From a user account that is assigned to the CsPersistentChatAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="98753-129">**[スタート**] メニューから、Skype ビジネス サーバーのコントロール パネルのまたはブラウザー ウィンドウを開きし、管理 URL を入力します。</span><span class="sxs-lookup"><span data-stu-id="98753-129">From the **Start** menu, select the Skype for Business Server Control Panel or open a browser window, and then enter the Admin URL.</span></span>
    
3. <span data-ttu-id="98753-130">左側のナビゲーション バーで [**常設チャット**] をクリックし、[**常設チャットの構成**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="98753-130">In the left navigation bar, click **Persistent Chat**, and then click **Persistent Chat Configuration**.</span></span>
    
4. <span data-ttu-id="98753-131">[**永続的なチャットの構成**] ページで、[**新規作成**] をクリックし、**サイトの構成**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="98753-131">On the **Persistent Chat Configuration** page, click **New,** and then click **Site configuration**.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="98753-132">サイトに展開されるすべての永続的なチャット サーバー プールに適用する構成を使用する場合は、このオプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="98753-132">Choose this option if you want the configuration to be applied to all Persistent Chat Server pools deployed in the site.</span></span> <span data-ttu-id="98753-133">特定の永続的なチャット サーバー プールに適用する構成を使用する場合は、**プールの構成**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="98753-133">Click **Pool Configuration** if you want the configuration to be applied to a specific Persistent Chat Server pool.</span></span>
  
5. <span data-ttu-id="98753-134">**サイトを選択**すると、永続的なチャット サーバーのサイト設定を構成するサイトを選択します。</span><span class="sxs-lookup"><span data-stu-id="98753-134">In **Select a Site**, select the site to be configured for the Persistent Chat Server site configuration.</span></span>
    
6. <span data-ttu-id="98753-135">[**新規 常設チャットの構成**] で、次の操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="98753-135">In **New Persistent Chat Configuration**, do the following:</span></span>
    
   - <span data-ttu-id="98753-p105">[**名前**] で、新しい構成設定の名前を指定します。既定では、サイト名が既に存在します。</span><span class="sxs-lookup"><span data-stu-id="98753-p105">In **Name**, specify a name for the new configuration settings. By default, the site name already exists.</span></span>
    
   - <span data-ttu-id="98753-p106">[**既定のチャット履歴**] で、最初の要求時にチャット ルームごとに処理されるチャット メッセージ数を定義します。既定値は 30 で、これはグローバルな既定値です。管理者はカテゴリごとにチャット履歴を無効にできます。</span><span class="sxs-lookup"><span data-stu-id="98753-p106">In **Default chat history**, define the number of chat messages that will be processed for each room upon first request. By default, the number is 30. This is the global default, and administrators can disable chat history per category.</span></span>
    
     > [!IMPORTANT]
     > <span data-ttu-id="98753-141">永続的なチャット サーバーは、メモリ内のこれらのメッセージをキャッシュがより多くのメッセージをキャッシュする場合はこの値を大きくようにします。</span><span class="sxs-lookup"><span data-stu-id="98753-141">Persistent Chat Server will cache these messages in memory, so if you increase this number, more messages will be cached.</span></span> <span data-ttu-id="98753-142">履歴コンテンツには、検索を使用していつでもアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="98753-142">You can always access historical content by search.</span></span> <span data-ttu-id="98753-143">既定値は、チャット ルームに接続したときに最初に表示されるメッセージの最大数を規定しているにすぎません。</span><span class="sxs-lookup"><span data-stu-id="98753-143">The default number simply determines the maximum number of messages that you initially see when connecting to a chat room.</span></span> 
  
   - <span data-ttu-id="98753-p108">[**最大ファイル サイズ (KB)**] で、各チャット履歴の最大ファイル サイズを選択します。既定値は 20 MB (20,000 KB) です。これは、システム内のチャット ルーム (対応する [**分類**] 設定でファイルのアップロードが有効化されているチャット ルーム) にアップロードできるファイルの最大サイズです。</span><span class="sxs-lookup"><span data-stu-id="98753-p108">In **Maximum file size (KB)**, select the maximum file size of each chat history. By default, the number is 20 MB (20,000 KB). This is the maximum size for a file that can be uploaded to any chat room in the system (for which file uploads are enabled by its corresponding **Category** setting).</span></span>
    
   - <span data-ttu-id="98753-147">[**参加者の更新制限**] で、参加者の更新の制限値を選択します。</span><span class="sxs-lookup"><span data-stu-id="98753-147">In **Participant update limit**, select the limit for participant updates.</span></span> <span data-ttu-id="98753-148">永続的なチャット サーバーは、接続しているユーザーの数がこの数に到達するまで、すべての参加者に名簿の情報 (ユーザーはチャット ルームに接続されている) を送信します。</span><span class="sxs-lookup"><span data-stu-id="98753-148">Persistent Chat Server sends roster information (who is connected to a chat room) to all participants until the number of connected users reaches this number.</span></span> <span data-ttu-id="98753-149">既定値は 75 です。</span><span class="sxs-lookup"><span data-stu-id="98753-149">By default, the number is 75.</span></span> <span data-ttu-id="98753-150">この制限を超えて、永続的なチャット サーバーが停止するルームには、接続されているクライアントに対して、名簿の更新を送信する特定の部屋に参加者の最大数を示します。</span><span class="sxs-lookup"><span data-stu-id="98753-150">This limit indicates the maximum number of participants in a given room beyond which Persistent Chat Server stops sending roster updates to connected clients about who is present in the room.</span></span>
    
   - <span data-ttu-id="98753-151">(オプション)。**ルーム管理 URL**] には、ルームの管理 URL を選択します。</span><span class="sxs-lookup"><span data-stu-id="98753-151">(Optional.) In **Room management URL**, select the room management URL.</span></span> <span data-ttu-id="98753-152">これは、web ベースのカスタム ルーム管理の URL です。</span><span class="sxs-lookup"><span data-stu-id="98753-152">This is the URL for a web-based custom room management.</span></span> <span data-ttu-id="98753-153">室の管理をカスタマイズする必要はありませんし、単に既定の設定を使用する場合は、このオプションを空白のままにします。</span><span class="sxs-lookup"><span data-stu-id="98753-153">If you don't need to customize room management, and you simply use the default setting, leave this option blank.</span></span> <span data-ttu-id="98753-154">URL を設定すると、部屋の内部および外部の両方の管理 URL として適用されます。</span><span class="sxs-lookup"><span data-stu-id="98753-154">After the URL is set, it is applied as both the internal and external room management URL.</span></span>
    
     <span data-ttu-id="98753-155">ルーム作成の操作性をカスタマイズし、特定のビジネス ・ ワークフローを含める場合は、永続的なチャット サーバー ソフトウェア開発キット (SDK) を使用してカスタム ルーム管理ソリューションを構築、それをどこかにホストして URL をここに配置します。。</span><span class="sxs-lookup"><span data-stu-id="98753-155">If you want to customize your room creation experience and include your specific business workflow, you can build a custom room management solution by using the Persistent Chat Server Software Development Kit (SDK), host it somewhere, and put the URL here.</span></span> <span data-ttu-id="98753-156">ユーザーがチャット ルームを表示または作成するときにカスタム チャット ルーム管理ソリューションを使用するよう、この URL がクライアントに伝えられます。</span><span class="sxs-lookup"><span data-stu-id="98753-156">This URL is sent down to the client, so that when a user tries to view or create a room, he or she is directed to your custom room management solution.</span></span>
    
7. <span data-ttu-id="98753-157">[**コミット**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="98753-157">Click **Commit**.</span></span>
    
## <a name="to-configure-persistent-chat-options-for-a-specific-persistent-chat-server-pool"></a><span data-ttu-id="98753-158">特定の永続的なチャット サーバー プールに永続的なチャットのオプションを構成するには</span><span class="sxs-lookup"><span data-stu-id="98753-158">To configure Persistent Chat options for a specific Persistent Chat Server pool</span></span>

1. <span data-ttu-id="98753-159">CsPersistentChatAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="98753-159">From a user account that is assigned to the CsPersistentChatAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="98753-160">**[スタート**] メニューから、Skype をビジネス サーバーのコントロール パネル] を選択や、ブラウザー ウィンドウを開く管理 URL を入力します。</span><span class="sxs-lookup"><span data-stu-id="98753-160">From the **Start** menu, select the Skype for Business Server Control Panel, or open a browser window, and then enter the Admin URL.</span></span>
    
3. <span data-ttu-id="98753-161">左側のナビゲーション バーで [**常設チャット**] をクリックし、[**常設チャットの構成**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="98753-161">In the left navigation bar, click **Persistent Chat**, and then click **Persistent Chat Configuration**.</span></span>
    
4. <span data-ttu-id="98753-162">[**常設チャットの構成**] ページで、[**新規**] をクリックし、[**プール構成**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="98753-162">On the **Persistent Chat Configuration** page, click **New**, and then click **Pool configuration**.</span></span>
    
5. <span data-ttu-id="98753-163">[**サービスの選択**] で構成される永続的なチャット サーバー プールに関連付けられているサービスを選択します。</span><span class="sxs-lookup"><span data-stu-id="98753-163">In **Select a Service**, select the service associated with the Persistent Chat Server pool to be configured.</span></span>
    
6. <span data-ttu-id="98753-164">[**新規 常設チャットの構成**] で、次の操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="98753-164">In **New Persistent Chat Configuration**, do the following:</span></span>
    
   - <span data-ttu-id="98753-p112">[**名前**] で、新しい構成設定の名前を指定します。既定では、サイト プール名が既に存在します。</span><span class="sxs-lookup"><span data-stu-id="98753-p112">In **Name**, specify a name for the new configuration settings. By default, the site pool name already exists.</span></span>
    
   - <span data-ttu-id="98753-p113">[**既定のチャット履歴**] で、最初の要求時にチャット ルームごとに処理されるチャット メッセージ数を定義します。既定値は 30 で、これはグローバルな既定値です。管理者はカテゴリごとにチャット履歴を無効にできます。</span><span class="sxs-lookup"><span data-stu-id="98753-p113">In **Default chat history**, define the number of chat messages that will be processed for each room upon first request. By default, the number is 30. This is the global default, and administrators can disable chat history per category.</span></span>
    
     > [!IMPORTANT]
     > <span data-ttu-id="98753-170">永続的なチャット サーバーは、メモリ内のこれらのメッセージをキャッシュがより多くのメッセージをキャッシュする場合はこの値を大きくようにします。</span><span class="sxs-lookup"><span data-stu-id="98753-170">Persistent Chat Server will cache these messages in memory, so if you increase this number, more messages will be cached.</span></span> <span data-ttu-id="98753-171">履歴コンテンツには、検索を使用していつでもアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="98753-171">You can always access historical content by search.</span></span> <span data-ttu-id="98753-172">既定値は、チャット ルームに接続したときに最初に表示されるメッセージの最大数を規定しているにすぎません。</span><span class="sxs-lookup"><span data-stu-id="98753-172">The default number simply determines the maximum number of messages that you initially see when connecting to a chat room.</span></span> 
  
   - <span data-ttu-id="98753-p115">[**最大ファイル サイズ (KB)**] で、各チャット履歴の最大ファイル サイズを選択します。既定値は 20 MB (20,000 KB) です。これは、システム内のチャット ルーム (対応する [**分類**] 設定でファイルのアップロードが有効化されているチャット ルーム) にアップロードできるファイルの最大サイズです。</span><span class="sxs-lookup"><span data-stu-id="98753-p115">In **Maximum file size (KB)**, select the maximum file size of each chat history. By default, the number is 20 MB (20,000 KB). This is the maximum size for a file that can be uploaded to any chat room in the system (for which file uploads are enabled by its corresponding **Category** setting).</span></span>
    
   - <span data-ttu-id="98753-176">[**参加者の更新制限**] で、参加者の更新の制限値を選択します。</span><span class="sxs-lookup"><span data-stu-id="98753-176">In **Participant update limit**, select the limit for participant updates.</span></span> <span data-ttu-id="98753-177">永続的なチャット サーバーは、接続しているユーザーの数がこの数に到達するまで、すべての参加者に名簿の情報 (ユーザーはチャット ルームに接続されている) を送信します。</span><span class="sxs-lookup"><span data-stu-id="98753-177">Persistent Chat Server sends roster information (who is connected to a chat room) to all participants until the number of connected users reaches this number.</span></span> <span data-ttu-id="98753-178">既定値は 75 です。</span><span class="sxs-lookup"><span data-stu-id="98753-178">By default, the number is 75.</span></span> <span data-ttu-id="98753-179">この制限を超えて、永続的なチャット サーバーが停止するルームには、接続されているクライアントに対して、名簿の更新を送信する特定の部屋に参加者の最大数を示します。</span><span class="sxs-lookup"><span data-stu-id="98753-179">This limit indicates the maximum number of participants in a given room beyond which Persistent Chat Server stops sending roster updates to connected clients about who is present in the room.</span></span>
    
   - <span data-ttu-id="98753-180">[**ルームの管理 URL**] で、ルーム管理 URL を選択します。</span><span class="sxs-lookup"><span data-stu-id="98753-180">In **Room management URL**, select the room management URL.</span></span> <span data-ttu-id="98753-181">これは Web ベースのチャット ルーム管理用の URL です。</span><span class="sxs-lookup"><span data-stu-id="98753-181">This is the URL for a web-based room management deployment.</span></span> <span data-ttu-id="98753-182">室の管理をカスタマイズする必要はありませんし、単に既定の設定を使用する場合は、このオプションを空白のままにします。</span><span class="sxs-lookup"><span data-stu-id="98753-182">If you don't need to customize room management, and you simply use the default setting, leave this option blank.</span></span>
    
     <span data-ttu-id="98753-183">ルーム作成の操作性をカスタマイズし、特定のビジネス ・ ワークフローを含める場合は、永続的なチャット サーバー ソフトウェア開発キット (SDK) を使用してカスタム ルーム管理ソリューションを構築、それをどこかにホストして URL をここに配置します。。</span><span class="sxs-lookup"><span data-stu-id="98753-183">If you want to customize your room creation experience and include your specific business workflow, you can build a custom room management solution by using the Persistent Chat Server Software Development Kit (SDK), host it somewhere, and put the URL here.</span></span> <span data-ttu-id="98753-184">ユーザーがチャット ルームを表示または作成するときにカスタム チャット ルーム管理ソリューションを使用するよう、この URL がクライアントに伝えられます。</span><span class="sxs-lookup"><span data-stu-id="98753-184">This URL is sent down to the client so that when a user tries to view/create a room, he or she is directed to your custom room management solution.</span></span>
    
7. <span data-ttu-id="98753-185">[**コミット**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="98753-185">Click **Commit**.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="98753-186">関連項目</span><span class="sxs-lookup"><span data-stu-id="98753-186">See also</span></span>

<span data-ttu-id="98753-187">持続チャット サーバーで永続的なチャット サーバーの機能と機能に関する詳細は、[ビジネス サーバー 2015 の Skype での永続的なチャット サーバーの計画](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md)、[ビジネス サーバー 2015 の Skype で永続的なチャット サーバーを展開](../../deploy/deploy-persistent-chat-server/deploy-persistent-chat-server.md)、および管理を[参照してください。ビジネス サーバー 2015 の Skype で](../../manage/persistent-chat/persistent-chat.md)。</span><span class="sxs-lookup"><span data-stu-id="98753-187">For details about Persistent Chat Server features and capabilities, see [Plan for Persistent Chat Server in Skype for Business Server 2015](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md), [Deploy Persistent Chat Server in Skype for Business Server 2015](../../deploy/deploy-persistent-chat-server/deploy-persistent-chat-server.md), and [Manage Persistent Chat Server in Skype for Business Server 2015](../../manage/persistent-chat/persistent-chat.md).</span></span>
  

