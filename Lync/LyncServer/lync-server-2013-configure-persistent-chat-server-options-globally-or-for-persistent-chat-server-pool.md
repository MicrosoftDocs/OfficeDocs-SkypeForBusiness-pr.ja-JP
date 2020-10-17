---
title: 'Lync Server 2013: 常設チャットサーバーのオプションをグローバルに、または常設チャットサーバープール用に構成する'
description: 'Lync Server 2013: 常設チャットサーバーのオプションをグローバルに、または常設チャットサーバープール用に構成します。'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure Persistent Chat Server options globally or for Persistent Chat Server pool
ms:assetid: 1e8d5245-cd58-4aad-9a1c-35b24189bc40
ms:mtpsurl: https://technet.microsoft.com/library/JJ204731(v=OCS.15)
ms:contentKeyID: 48183581
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0e0e26fc8719f9aa5f153a7962df70ee7237b980
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48564993"
---
# <a name="configure-persistent-chat-server-options-globally-or-for-persistent-chat-server-pool-in-lync-server-2013"></a><span data-ttu-id="192e9-103">Lync Server 2013 で常設チャットサーバーのオプションをグローバルに、または常設チャットサーバープール用に構成する</span><span class="sxs-lookup"><span data-stu-id="192e9-103">Configure Persistent Chat Server options globally or for Persistent Chat Server pool in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="192e9-104">_**トピックの最終更新日:** 2012-10-06_</span><span class="sxs-lookup"><span data-stu-id="192e9-104">_**Topic Last Modified:** 2012-10-06_</span></span>

<span data-ttu-id="192e9-105">Lync Server 2013 コントロールパネルで、 **[常設チャット] ページの**[**常設チャットの構成**] セクションを使用して、常設チャットの設定をすべての常設チャットサーバープールに適用するか、特定の常設チャットサーバープールに対して構成することができます。</span><span class="sxs-lookup"><span data-stu-id="192e9-105">In Lync Server 2013 Control Panel, you can use the **Persistent Chat Configuration** section of the **Persistent Chat** page to configure Persistent Chat settings globally where it applies to all Persistent Chat Server pools, or for a specific Persistent Chat Server pool.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="192e9-106">常設チャットサーバーを構成して使用するには、まず、トポロジビルダーを使用して、常設チャットサーバーのサポートをトポロジに追加してから、トポロジを公開する必要があります。</span><span class="sxs-lookup"><span data-stu-id="192e9-106">To configure and use Persistent Chat Server, you must first use Topology Builder to add Persistent Chat Server support to the topology, and then publish the topology.</span></span> <span data-ttu-id="192e9-107">詳細については、「展開」のドキュメントの「 <A href="lync-server-2013-adding-persistent-chat-server-to-your-deployment.md">Lync server 2013 での展開への常設チャットサーバーの追加</A> 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="192e9-107">For details, see <A href="lync-server-2013-adding-persistent-chat-server-to-your-deployment.md">Adding Persistent Chat Server to your deployment in Lync Server 2013</A> in the Deployment documentation.</span></span>



</div>

<div>

## <a name="to-configure-persistent-chat-options-globally"></a><span data-ttu-id="192e9-108">常設チャットのオプションをグローバルに構成するには</span><span class="sxs-lookup"><span data-stu-id="192e9-108">To configure Persistent Chat options globally</span></span>

1.  <span data-ttu-id="192e9-109">CsPersistentChatAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="192e9-109">From a user account that is assigned to the CsPersistentChatAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="192e9-110">[ **スタート** ] メニューから [Lync Server コントロールパネル] を選択するか、ブラウザーウィンドウを開いて管理 URL を入力します。</span><span class="sxs-lookup"><span data-stu-id="192e9-110">From the **Start** menu, select the Lync Server Control Panel or open a browser window, and then enter the Admin URL.</span></span> <span data-ttu-id="192e9-111">Lync Server コントロールパネルの起動に使用できるさまざまな方法の詳細については、「 [Open Lync server 2013 管理ツール](lync-server-2013-open-lync-server-administrative-tools.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="192e9-111">For details about the different methods that you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="192e9-112">Windows PowerShell コマンドレットを使用することもできます。</span><span class="sxs-lookup"><span data-stu-id="192e9-112">You can also use Windows PowerShell cmdlets.</span></span> <span data-ttu-id="192e9-113">詳細については、「展開」のドキュメントの「 <A href="configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md">Windows PowerShell コマンドレットを使用して常設チャットサーバーを構成する</A> 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="192e9-113">For details, see <A href="configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md">Configuring Persistent Chat Server by using Windows PowerShell cmdlets</A> in the Deployment documentation.</span></span>

    
    </div>

3.  <span data-ttu-id="192e9-114">左側のナビゲーション バーで [**常設チャット**] をクリックし、[**常設チャットの構成**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="192e9-114">In the left navigation bar, click **Persistent Chat**, and then click **Persistent Chat Configuration**.</span></span>

4.  <span data-ttu-id="192e9-115">[ **常設チャットの構成** ] ページで、[ **新規** ] をクリックし、[ **サイト構成**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="192e9-115">On the **Persistent Chat Configuration** page, click **New,** and then click **Site configuration**.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="192e9-116">サイトに展開されているすべての常設チャットサーバープールに構成を適用する場合は、このオプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="192e9-116">Choose this option if you want the configuration to be applied to all Persistent Chat Server pools deployed in the site.</span></span> <span data-ttu-id="192e9-117">特定の常設チャットサーバープールに構成を適用する場合は、[ <STRONG>プール構成</STRONG> ] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="192e9-117">Click <STRONG>Pool Configuration</STRONG> if you want the configuration to be applied to a specific Persistent Chat Server pool.</span></span>

    
    </div>

5.  <span data-ttu-id="192e9-118">[ **サイトの選択**] で、常設チャットサーバーサイト構成用に構成するサイトを選択します。</span><span class="sxs-lookup"><span data-stu-id="192e9-118">In **Select a Site**, select the site to be configured for the Persistent Chat Server site configuration.</span></span>

6.  <span data-ttu-id="192e9-119">[**新規 常設チャットの構成**] で、次の操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="192e9-119">In **New Persistent Chat Configuration**, do the following:</span></span>
    
      - <span data-ttu-id="192e9-p105">[**名前**] で、新しい構成設定の名前を指定します。既定では、サイト名は既に存在します。</span><span class="sxs-lookup"><span data-stu-id="192e9-p105">In **Name**, specify a name for the new configuration settings. By default, the site name already exists.</span></span>
    
      - <span data-ttu-id="192e9-p106">[**Default chat history**] で、最初の要求時にチャット ルームごとに処理されるチャット メッセージ数を定義します。既定値は 30 で、これはグローバルな既定値です。管理者はカテゴリごとにチャット履歴を無効にできます。</span><span class="sxs-lookup"><span data-stu-id="192e9-p106">In **Default chat history**, define the number of chat messages that will be processed for each room upon first request. By default, the number is 30. This is the global default, and administrators can disable chat history per category.</span></span>
        
        <div>
        

        > [!IMPORTANT]  
        > <span data-ttu-id="192e9-125">常設チャットサーバーはこれらのメッセージをメモリにキャッシュするので、この数を増やすと、メッセージがキャッシュされます。</span><span class="sxs-lookup"><span data-stu-id="192e9-125">Persistent Chat Server will cache these messages in memory, so if you increase this number, more messages will be cached.</span></span> <span data-ttu-id="192e9-126">履歴コンテンツには、検索を使用していつでもアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="192e9-126">You can always access historical content by search.</span></span> <span data-ttu-id="192e9-127">既定値は、チャット ルームに接続したときに最初に表示されるメッセージの最大数を規定しているにすぎません。</span><span class="sxs-lookup"><span data-stu-id="192e9-127">The default number simply determines the maximum number of messages that you initially see when connecting to a chat room.</span></span>

        
        </div>
    
      - <span data-ttu-id="192e9-p108">[**最大ファイル サイズ (KB)**] で、各チャット履歴の最大ファイル サイズを選択します。既定値は 20 MB (20,000 KB) です。これは、システム内のチャット ルーム (対応する [**分類**] 設定でファイルのアップロードが有効化されているチャット ルーム) にアップロードできるファイルの最大サイズです。</span><span class="sxs-lookup"><span data-stu-id="192e9-p108">In **Maximum file size (KB)**, select the maximum file size of each chat history. By default, the number is 20 MB (20,000 KB). This is the maximum size for a file that can be uploaded to any chat room in the system (for which file uploads are enabled by its corresponding **Category** setting).</span></span>
        
        <div>
        

        > [!IMPORTANT]  
        > <span data-ttu-id="192e9-131">この設定は、カスタムアプリケーションまたは以前のグループチャットクライアント (Office Communications Server 2007 R2 &nbsp; グループチャットサーバーまたは Lync server 2010 を使用している場合)、グループチャットでルームにファイルを投稿できるため、サーバーに適用されます。</span><span class="sxs-lookup"><span data-stu-id="192e9-131">This setting is enforced on the server because custom applications or previous Group Chat clients using Office Communications Server 2007 R2&nbsp;Group Chat Server or Lync Server 2010, Group Chat can post files to a room.</span></span> <span data-ttu-id="192e9-132">Lync 2013 クライアントはファイルのアップロード/ダウンロード機能を備えていないため、純粋な Lync 2013 展開または Lync 2013 クライアントを使用している場合は、常設チャットサーバーのチャットルームにファイルを投稿することはできません。</span><span class="sxs-lookup"><span data-stu-id="192e9-132">The Lync 2013 client does not have file upload/download capability, so if you have a pure Lync 2013 deployment or Lync 2013 client, it is not possible to post files in a Persistent Chat Server chat room.</span></span>

        
        </div>
    
      - <span data-ttu-id="192e9-133">[**参加者の更新制限**] で、参加者の更新の制限値を選択します。</span><span class="sxs-lookup"><span data-stu-id="192e9-133">In **Participant update limit**, select the limit for participant updates.</span></span> <span data-ttu-id="192e9-134">常設チャットサーバーは、接続されているユーザーの数がこの値に達するまで、すべての参加者に名簿情報 (チャットルームに接続されている人) を送信します。</span><span class="sxs-lookup"><span data-stu-id="192e9-134">Persistent Chat Server sends roster information (who is connected to a chat room) to all participants until the number of connected users reaches this number.</span></span> <span data-ttu-id="192e9-135">既定値は 75 です。</span><span class="sxs-lookup"><span data-stu-id="192e9-135">By default, the number is 75.</span></span> <span data-ttu-id="192e9-136">この制限は、常設チャットサーバーが、ルームにあるユーザーについて、接続されたクライアントに対して名簿の更新の送信を停止する、特定の会議室の参加者の最大数を示します。</span><span class="sxs-lookup"><span data-stu-id="192e9-136">This limit indicates the maximum number of participants in a given room beyond which Persistent Chat Server stops sending roster updates to connected clients about who is present in the room.</span></span>
    
      - <span data-ttu-id="192e9-p111">(オプション) [**ルームの管理 URL**] で、ルーム管理 URL を選択します。これは Web ベースのカスタム チャット ルーム管理用の URL です。チャット ルームの管理をカスタマイズする必要がなく、既定の設定をそのまま使用する場合は、このオプションを空白のままにします。URL を設定すると、その URL は内部と外部の両方のチャット ルーム管理 URL として適用されます。</span><span class="sxs-lookup"><span data-stu-id="192e9-p111">(Optional.) In **Room management URL**, select the room management URL. This is the URL for a web-based custom room management. If you don’t need to customize room management, and you simply use the default setting, leave this option blank. After the URL is set, it is applied as both the internal and external room management URL.</span></span>
        
        <span data-ttu-id="192e9-141">ルームの作成環境をカスタマイズして、特定のビジネスワークフローを含める必要がある場合は、常設チャットサーバーソフトウェア開発キット (SDK) を使用してカスタムルーム管理ソリューションを構築し、どこかにホストし、URL をここに配置することができます。</span><span class="sxs-lookup"><span data-stu-id="192e9-141">If you want to customize your room creation experience and include your specific business workflow, you can build a custom room management solution by using the Persistent Chat Server Software Development Kit (SDK), host it somewhere, and put the URL here.</span></span> <span data-ttu-id="192e9-142">ユーザーがチャット ルームを表示または作成するときにカスタム チャット ルーム管理ソリューションを使用するよう、この URL がクライアントに伝えられます。</span><span class="sxs-lookup"><span data-stu-id="192e9-142">This URL is sent down to the client, so that when a user tries to view or create a room, he or she is directed to your custom room management solution.</span></span>

7.  <span data-ttu-id="192e9-143">[**確定**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="192e9-143">Click **Commit**.</span></span>

</div>

<div>

## <a name="to-configure-persistent-chat-options-for-a-specific-persistent-chat-server-pool"></a><span data-ttu-id="192e9-144">特定の常設チャットサーバープールの常設チャットオプションを構成するには</span><span class="sxs-lookup"><span data-stu-id="192e9-144">To configure Persistent Chat options for a specific Persistent Chat Server pool</span></span>

1.  <span data-ttu-id="192e9-145">CsPersistentChatAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="192e9-145">From a user account that is assigned to the CsPersistentChatAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="192e9-146">[ **スタート** ] メニューから [Lync Server コントロールパネル] を選択するか、ブラウザーウィンドウを開いて管理 URL を入力します。</span><span class="sxs-lookup"><span data-stu-id="192e9-146">From the **Start** menu, select the Lync Server Control Panel, or open a browser window, and then enter the Admin URL.</span></span> <span data-ttu-id="192e9-147">Lync Server コントロールパネルの起動に使用できるさまざまな方法の詳細については、「 [Open Lync server 2013 管理ツール](lync-server-2013-open-lync-server-administrative-tools.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="192e9-147">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="192e9-148">Windows PowerShell コマンドレットを使用することもできます。</span><span class="sxs-lookup"><span data-stu-id="192e9-148">You can also use Windows PowerShell cmdlets.</span></span> <span data-ttu-id="192e9-149">詳細については、「展開」のドキュメントの「 <A href="configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md">Windows PowerShell コマンドレットを使用して常設チャットサーバーを構成する</A> 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="192e9-149">For details, see <A href="configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md">Configuring Persistent Chat Server by using Windows PowerShell cmdlets</A> in the Deployment documentation.</span></span>

    
    </div>

3.  <span data-ttu-id="192e9-150">左側のナビゲーション バーで [**常設チャット**] をクリックし、[**常設チャットの構成**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="192e9-150">In the left navigation bar, click **Persistent Chat**, and then click **Persistent Chat Configuration**.</span></span>

4.  <span data-ttu-id="192e9-151">[**常設チャットの構成**] ページで、[**新規**] をクリックし、[**プール構成**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="192e9-151">On the **Persistent Chat Configuration** page, click **New**, and then click **Pool configuration**.</span></span>

5.  <span data-ttu-id="192e9-152">**[サービスの選択**] で、構成する常設チャットサーバープールに関連付けられているサービスを選択します。</span><span class="sxs-lookup"><span data-stu-id="192e9-152">In **Select a Service**, select the service associated with the Persistent Chat Server pool to be configured.</span></span>

6.  <span data-ttu-id="192e9-153">[**新規 常設チャットの構成**] で、次の操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="192e9-153">In **New Persistent Chat Configuration**, do the following:</span></span>
    
      - <span data-ttu-id="192e9-p115">[**名前**] で、新しい構成設定の名前を指定します。既定では、サイト プール名は既に存在します。</span><span class="sxs-lookup"><span data-stu-id="192e9-p115">In **Name**, specify a name for the new configuration settings. By default, the site pool name already exists.</span></span>
    
      - <span data-ttu-id="192e9-p116">[**Default chat history**] で、最初の要求時にチャット ルームごとに処理されるチャット メッセージ数を定義します。既定値は 30 で、これはグローバルな既定値です。管理者はカテゴリごとにチャット履歴を無効にできます。</span><span class="sxs-lookup"><span data-stu-id="192e9-p116">In **Default chat history**, define the number of chat messages that will be processed for each room upon first request. By default, the number is 30. This is the global default, and administrators can disable chat history per category.</span></span>
        
        <div>
        

        > [!IMPORTANT]  
        > <span data-ttu-id="192e9-159">常設チャットサーバーはこれらのメッセージをメモリにキャッシュするので、この数を増やすと、メッセージがキャッシュされます。</span><span class="sxs-lookup"><span data-stu-id="192e9-159">Persistent Chat Server will cache these messages in memory, so if you increase this number, more messages will be cached.</span></span> <span data-ttu-id="192e9-160">履歴コンテンツには、検索を使用していつでもアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="192e9-160">You can always access historical content by search.</span></span> <span data-ttu-id="192e9-161">既定値は、チャット ルームに接続したときに最初に表示されるメッセージの最大数を規定しているにすぎません。</span><span class="sxs-lookup"><span data-stu-id="192e9-161">The default number simply determines the maximum number of messages that you initially see when connecting to a chat room.</span></span>

        
        </div>
    
      - <span data-ttu-id="192e9-p118">[**最大ファイル サイズ (KB)**] で、各チャット履歴の最大ファイル サイズを選択します。既定値は 20 MB (20,000 KB) です。これは、システム内のチャット ルーム (対応する [**分類**] 設定でファイルのアップロードが有効化されているチャット ルーム) にアップロードできるファイルの最大サイズです。</span><span class="sxs-lookup"><span data-stu-id="192e9-p118">In **Maximum file size (KB)**, select the maximum file size of each chat history. By default, the number is 20 MB (20,000 KB). This is the maximum size for a file that can be uploaded to any chat room in the system (for which file uploads are enabled by its corresponding **Category** setting).</span></span>
        
        <div>
        

        > [!IMPORTANT]  
        > <span data-ttu-id="192e9-165">この設定は、カスタムアプリケーションまたは以前のグループチャットクライアント (Office Communications Server 2007 R2 &nbsp; グループチャットサーバーまたは Lync server 2010、グループチャット) が会議室にファイルを投稿できるため、サーバーで適用されます。</span><span class="sxs-lookup"><span data-stu-id="192e9-165">This setting is enforced on the server because custom applications or previous Group Chat clients (Office Communications Server 2007 R2&nbsp;Group Chat Server or Lync Server 2010, Group Chat) can post files to a room.</span></span> <span data-ttu-id="192e9-166">Lync 2013 クライアントはファイルのアップロード/ダウンロード機能を備えていないため、純粋な Lync 2013 展開または Lync 2013 クライアントを使用している場合は、常設チャットサーバーのチャットルームにファイルを投稿することはできません。</span><span class="sxs-lookup"><span data-stu-id="192e9-166">The Lync 2013 client does not have file upload/download capability, so if you have a pure Lync 2013 deployment or Lync 2013 client, it is not possible to post files in a Persistent Chat Server chat room.</span></span>

        
        </div>
    
      - <span data-ttu-id="192e9-167">[**参加者の更新制限**] で、参加者の更新の制限値を選択します。</span><span class="sxs-lookup"><span data-stu-id="192e9-167">In **Participant update limit**, select the limit for participant updates.</span></span> <span data-ttu-id="192e9-168">常設チャットサーバーは、接続されているユーザーの数がこの値に達するまで、すべての参加者に名簿情報 (チャットルームに接続されている人) を送信します。</span><span class="sxs-lookup"><span data-stu-id="192e9-168">Persistent Chat Server sends roster information (who is connected to a chat room) to all participants until the number of connected users reaches this number.</span></span> <span data-ttu-id="192e9-169">既定値は 75 です。</span><span class="sxs-lookup"><span data-stu-id="192e9-169">By default, the number is 75.</span></span> <span data-ttu-id="192e9-170">この制限は、常設チャットサーバーが、ルームにあるユーザーについて、接続されたクライアントに対して名簿の更新の送信を停止する、特定の会議室の参加者の最大数を示します。</span><span class="sxs-lookup"><span data-stu-id="192e9-170">This limit indicates the maximum number of participants in a given room beyond which Persistent Chat Server stops sending roster updates to connected clients about who is present in the room.</span></span>
    
      - <span data-ttu-id="192e9-p121">[**ルームの管理 URL**] で、ルーム管理 URL を選択します。これは Web ベースのチャット ルーム管理用の URL です。チャット ルームの管理をカスタマイズする必要がなく、既定の設定をそのまま使用する場合は、このオプションを空白のままにします。</span><span class="sxs-lookup"><span data-stu-id="192e9-p121">In **Room management URL**, select the room management URL. This is the URL for a web-based room management deployment. If you don’t need to customize room management, and you simply use the default setting, leave this option blank.</span></span>
        
        <span data-ttu-id="192e9-174">ルームの作成環境をカスタマイズして、特定のビジネスワークフローを含める必要がある場合は、常設チャットサーバーソフトウェア開発キット (SDK) を使用してカスタムルーム管理ソリューションを構築し、どこかにホストし、URL をここに配置することができます。</span><span class="sxs-lookup"><span data-stu-id="192e9-174">If you want to customize your room creation experience and include your specific business workflow, you can build a custom room management solution by using the Persistent Chat Server Software Development Kit (SDK), host it somewhere, and put the URL here.</span></span> <span data-ttu-id="192e9-175">ユーザーがチャット ルームを表示または作成するときにカスタム チャット ルーム管理ソリューションを使用するよう、この URL がクライアントに伝えられます。</span><span class="sxs-lookup"><span data-stu-id="192e9-175">This URL is sent down to the client so that when a user tries to view/create a room, he or she is directed to your custom room management solution.</span></span>

7.  <span data-ttu-id="192e9-176">[**確定**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="192e9-176">Click **Commit**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

