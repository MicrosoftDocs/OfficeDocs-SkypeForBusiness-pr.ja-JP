---
title: 'Lync Server 2013: 常設チャットサーバーのオプションをグローバルに、または常設チャットサーバープール用に構成する'
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
ms.openlocfilehash: 6a9cadd23099dbcaee5c577705ca1c2e4bdf6c00
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/16/2020
ms.locfileid: "48520464"
---
# <a name="configure-persistent-chat-server-options-globally-or-for-persistent-chat-server-pool-in-lync-server-2013"></a><span data-ttu-id="612f8-102">Lync Server 2013 で常設チャットサーバーのオプションをグローバルに、または常設チャットサーバープール用に構成する</span><span class="sxs-lookup"><span data-stu-id="612f8-102">Configure Persistent Chat Server options globally or for Persistent Chat Server pool in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="612f8-103">_**トピックの最終更新日:** 2012-10-06_</span><span class="sxs-lookup"><span data-stu-id="612f8-103">_**Topic Last Modified:** 2012-10-06_</span></span>

<span data-ttu-id="612f8-104">Lync Server 2013 コントロールパネルで、 **[常設チャット] ページの**[**常設チャットの構成**] セクションを使用して、常設チャットの設定をすべての常設チャットサーバープールに適用するか、特定の常設チャットサーバープールに対して構成することができます。</span><span class="sxs-lookup"><span data-stu-id="612f8-104">In Lync Server 2013 Control Panel, you can use the **Persistent Chat Configuration** section of the **Persistent Chat** page to configure Persistent Chat settings globally where it applies to all Persistent Chat Server pools, or for a specific Persistent Chat Server pool.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="612f8-105">常設チャットサーバーを構成して使用するには、まず、トポロジビルダーを使用して、常設チャットサーバーのサポートをトポロジに追加してから、トポロジを公開する必要があります。</span><span class="sxs-lookup"><span data-stu-id="612f8-105">To configure and use Persistent Chat Server, you must first use Topology Builder to add Persistent Chat Server support to the topology, and then publish the topology.</span></span> <span data-ttu-id="612f8-106">詳細については、「展開」のドキュメントの「 <A href="lync-server-2013-adding-persistent-chat-server-to-your-deployment.md">Lync server 2013 での展開への常設チャットサーバーの追加</A> 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="612f8-106">For details, see <A href="lync-server-2013-adding-persistent-chat-server-to-your-deployment.md">Adding Persistent Chat Server to your deployment in Lync Server 2013</A> in the Deployment documentation.</span></span>



</div>

<div>

## <a name="to-configure-persistent-chat-options-globally"></a><span data-ttu-id="612f8-107">常設チャットのオプションをグローバルに構成するには</span><span class="sxs-lookup"><span data-stu-id="612f8-107">To configure Persistent Chat options globally</span></span>

1.  <span data-ttu-id="612f8-108">CsPersistentChatAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="612f8-108">From a user account that is assigned to the CsPersistentChatAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="612f8-109">[ **スタート** ] メニューから [Lync Server コントロールパネル] を選択するか、ブラウザーウィンドウを開いて管理 URL を入力します。</span><span class="sxs-lookup"><span data-stu-id="612f8-109">From the **Start** menu, select the Lync Server Control Panel or open a browser window, and then enter the Admin URL.</span></span> <span data-ttu-id="612f8-110">Lync Server コントロールパネルの起動に使用できるさまざまな方法の詳細については、「 [Open Lync server 2013 管理ツール](lync-server-2013-open-lync-server-administrative-tools.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="612f8-110">For details about the different methods that you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="612f8-111">Windows PowerShell コマンドレットを使用することもできます。</span><span class="sxs-lookup"><span data-stu-id="612f8-111">You can also use Windows PowerShell cmdlets.</span></span> <span data-ttu-id="612f8-112">詳細については、「展開」のドキュメントの「 <A href="configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md">Windows PowerShell コマンドレットを使用して常設チャットサーバーを構成する</A> 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="612f8-112">For details, see <A href="configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md">Configuring Persistent Chat Server by using Windows PowerShell cmdlets</A> in the Deployment documentation.</span></span>

    
    </div>

3.  <span data-ttu-id="612f8-113">左側のナビゲーション バーで [**常設チャット**] をクリックし、[**常設チャットの構成**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="612f8-113">In the left navigation bar, click **Persistent Chat**, and then click **Persistent Chat Configuration**.</span></span>

4.  <span data-ttu-id="612f8-114">[ **常設チャットの構成** ] ページで、[ **新規** ] をクリックし、[ **サイト構成**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="612f8-114">On the **Persistent Chat Configuration** page, click **New,** and then click **Site configuration**.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="612f8-115">サイトに展開されているすべての常設チャットサーバープールに構成を適用する場合は、このオプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="612f8-115">Choose this option if you want the configuration to be applied to all Persistent Chat Server pools deployed in the site.</span></span> <span data-ttu-id="612f8-116">特定の常設チャットサーバープールに構成を適用する場合は、[ <STRONG>プール構成</STRONG> ] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="612f8-116">Click <STRONG>Pool Configuration</STRONG> if you want the configuration to be applied to a specific Persistent Chat Server pool.</span></span>

    
    </div>

5.  <span data-ttu-id="612f8-117">[ **サイトの選択**] で、常設チャットサーバーサイト構成用に構成するサイトを選択します。</span><span class="sxs-lookup"><span data-stu-id="612f8-117">In **Select a Site**, select the site to be configured for the Persistent Chat Server site configuration.</span></span>

6.  <span data-ttu-id="612f8-118">[**新規 常設チャットの構成**] で、次の操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="612f8-118">In **New Persistent Chat Configuration**, do the following:</span></span>
    
      - <span data-ttu-id="612f8-p105">[**名前**] で、新しい構成設定の名前を指定します。既定では、サイト名は既に存在します。</span><span class="sxs-lookup"><span data-stu-id="612f8-p105">In **Name**, specify a name for the new configuration settings. By default, the site name already exists.</span></span>
    
      - <span data-ttu-id="612f8-p106">[**Default chat history**] で、最初の要求時にチャット ルームごとに処理されるチャット メッセージ数を定義します。既定値は 30 で、これはグローバルな既定値です。管理者はカテゴリごとにチャット履歴を無効にできます。</span><span class="sxs-lookup"><span data-stu-id="612f8-p106">In **Default chat history**, define the number of chat messages that will be processed for each room upon first request. By default, the number is 30. This is the global default, and administrators can disable chat history per category.</span></span>
        
        <div>
        

        > [!IMPORTANT]  
        > <span data-ttu-id="612f8-124">常設チャットサーバーはこれらのメッセージをメモリにキャッシュするので、この数を増やすと、メッセージがキャッシュされます。</span><span class="sxs-lookup"><span data-stu-id="612f8-124">Persistent Chat Server will cache these messages in memory, so if you increase this number, more messages will be cached.</span></span> <span data-ttu-id="612f8-125">履歴コンテンツには、検索を使用していつでもアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="612f8-125">You can always access historical content by search.</span></span> <span data-ttu-id="612f8-126">既定値は、チャット ルームに接続したときに最初に表示されるメッセージの最大数を規定しているにすぎません。</span><span class="sxs-lookup"><span data-stu-id="612f8-126">The default number simply determines the maximum number of messages that you initially see when connecting to a chat room.</span></span>

        
        </div>
    
      - <span data-ttu-id="612f8-p108">[**最大ファイル サイズ (KB)**] で、各チャット履歴の最大ファイル サイズを選択します。既定値は 20 MB (20,000 KB) です。これは、システム内のチャット ルーム (対応する [**分類**] 設定でファイルのアップロードが有効化されているチャット ルーム) にアップロードできるファイルの最大サイズです。</span><span class="sxs-lookup"><span data-stu-id="612f8-p108">In **Maximum file size (KB)**, select the maximum file size of each chat history. By default, the number is 20 MB (20,000 KB). This is the maximum size for a file that can be uploaded to any chat room in the system (for which file uploads are enabled by its corresponding **Category** setting).</span></span>
        
        <div>
        

        > [!IMPORTANT]  
        > <span data-ttu-id="612f8-130">この設定は、カスタムアプリケーションまたは以前のグループチャットクライアント (Office Communications Server 2007 R2 &nbsp; グループチャットサーバーまたは Lync server 2010 を使用している場合)、グループチャットでルームにファイルを投稿できるため、サーバーに適用されます。</span><span class="sxs-lookup"><span data-stu-id="612f8-130">This setting is enforced on the server because custom applications or previous Group Chat clients using Office Communications Server 2007 R2&nbsp;Group Chat Server or Lync Server 2010, Group Chat can post files to a room.</span></span> <span data-ttu-id="612f8-131">Lync 2013 クライアントはファイルのアップロード/ダウンロード機能を備えていないため、純粋な Lync 2013 展開または Lync 2013 クライアントを使用している場合は、常設チャットサーバーのチャットルームにファイルを投稿することはできません。</span><span class="sxs-lookup"><span data-stu-id="612f8-131">The Lync 2013 client does not have file upload/download capability, so if you have a pure Lync 2013 deployment or Lync 2013 client, it is not possible to post files in a Persistent Chat Server chat room.</span></span>

        
        </div>
    
      - <span data-ttu-id="612f8-132">[**参加者の更新制限**] で、参加者の更新の制限値を選択します。</span><span class="sxs-lookup"><span data-stu-id="612f8-132">In **Participant update limit**, select the limit for participant updates.</span></span> <span data-ttu-id="612f8-133">常設チャットサーバーは、接続されているユーザーの数がこの値に達するまで、すべての参加者に名簿情報 (チャットルームに接続されている人) を送信します。</span><span class="sxs-lookup"><span data-stu-id="612f8-133">Persistent Chat Server sends roster information (who is connected to a chat room) to all participants until the number of connected users reaches this number.</span></span> <span data-ttu-id="612f8-134">既定値は 75 です。</span><span class="sxs-lookup"><span data-stu-id="612f8-134">By default, the number is 75.</span></span> <span data-ttu-id="612f8-135">この制限は、常設チャットサーバーが、ルームにあるユーザーについて、接続されたクライアントに対して名簿の更新の送信を停止する、特定の会議室の参加者の最大数を示します。</span><span class="sxs-lookup"><span data-stu-id="612f8-135">This limit indicates the maximum number of participants in a given room beyond which Persistent Chat Server stops sending roster updates to connected clients about who is present in the room.</span></span>
    
      - <span data-ttu-id="612f8-p111">(オプション) [**ルームの管理 URL**] で、ルーム管理 URL を選択します。これは Web ベースのカスタム チャット ルーム管理用の URL です。チャット ルームの管理をカスタマイズする必要がなく、既定の設定をそのまま使用する場合は、このオプションを空白のままにします。URL を設定すると、その URL は内部と外部の両方のチャット ルーム管理 URL として適用されます。</span><span class="sxs-lookup"><span data-stu-id="612f8-p111">(Optional.) In **Room management URL**, select the room management URL. This is the URL for a web-based custom room management. If you don’t need to customize room management, and you simply use the default setting, leave this option blank. After the URL is set, it is applied as both the internal and external room management URL.</span></span>
        
        <span data-ttu-id="612f8-140">ルームの作成環境をカスタマイズして、特定のビジネスワークフローを含める必要がある場合は、常設チャットサーバーソフトウェア開発キット (SDK) を使用してカスタムルーム管理ソリューションを構築し、どこかにホストし、URL をここに配置することができます。</span><span class="sxs-lookup"><span data-stu-id="612f8-140">If you want to customize your room creation experience and include your specific business workflow, you can build a custom room management solution by using the Persistent Chat Server Software Development Kit (SDK), host it somewhere, and put the URL here.</span></span> <span data-ttu-id="612f8-141">ユーザーがチャット ルームを表示または作成するときにカスタム チャット ルーム管理ソリューションを使用するよう、この URL がクライアントに伝えられます。</span><span class="sxs-lookup"><span data-stu-id="612f8-141">This URL is sent down to the client, so that when a user tries to view or create a room, he or she is directed to your custom room management solution.</span></span>

7.  <span data-ttu-id="612f8-142">[**確定**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="612f8-142">Click **Commit**.</span></span>

</div>

<div>

## <a name="to-configure-persistent-chat-options-for-a-specific-persistent-chat-server-pool"></a><span data-ttu-id="612f8-143">特定の常設チャットサーバープールの常設チャットオプションを構成するには</span><span class="sxs-lookup"><span data-stu-id="612f8-143">To configure Persistent Chat options for a specific Persistent Chat Server pool</span></span>

1.  <span data-ttu-id="612f8-144">CsPersistentChatAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="612f8-144">From a user account that is assigned to the CsPersistentChatAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="612f8-145">[ **スタート** ] メニューから [Lync Server コントロールパネル] を選択するか、ブラウザーウィンドウを開いて管理 URL を入力します。</span><span class="sxs-lookup"><span data-stu-id="612f8-145">From the **Start** menu, select the Lync Server Control Panel, or open a browser window, and then enter the Admin URL.</span></span> <span data-ttu-id="612f8-146">Lync Server コントロールパネルの起動に使用できるさまざまな方法の詳細については、「 [Open Lync server 2013 管理ツール](lync-server-2013-open-lync-server-administrative-tools.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="612f8-146">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="612f8-147">Windows PowerShell コマンドレットを使用することもできます。</span><span class="sxs-lookup"><span data-stu-id="612f8-147">You can also use Windows PowerShell cmdlets.</span></span> <span data-ttu-id="612f8-148">詳細については、「展開」のドキュメントの「 <A href="configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md">Windows PowerShell コマンドレットを使用して常設チャットサーバーを構成する</A> 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="612f8-148">For details, see <A href="configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md">Configuring Persistent Chat Server by using Windows PowerShell cmdlets</A> in the Deployment documentation.</span></span>

    
    </div>

3.  <span data-ttu-id="612f8-149">左側のナビゲーション バーで [**常設チャット**] をクリックし、[**常設チャットの構成**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="612f8-149">In the left navigation bar, click **Persistent Chat**, and then click **Persistent Chat Configuration**.</span></span>

4.  <span data-ttu-id="612f8-150">[**常設チャットの構成**] ページで、[**新規**] をクリックし、[**プール構成**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="612f8-150">On the **Persistent Chat Configuration** page, click **New**, and then click **Pool configuration**.</span></span>

5.  <span data-ttu-id="612f8-151">**[サービスの選択**] で、構成する常設チャットサーバープールに関連付けられているサービスを選択します。</span><span class="sxs-lookup"><span data-stu-id="612f8-151">In **Select a Service**, select the service associated with the Persistent Chat Server pool to be configured.</span></span>

6.  <span data-ttu-id="612f8-152">[**新規 常設チャットの構成**] で、次の操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="612f8-152">In **New Persistent Chat Configuration**, do the following:</span></span>
    
      - <span data-ttu-id="612f8-p115">[**名前**] で、新しい構成設定の名前を指定します。既定では、サイト プール名は既に存在します。</span><span class="sxs-lookup"><span data-stu-id="612f8-p115">In **Name**, specify a name for the new configuration settings. By default, the site pool name already exists.</span></span>
    
      - <span data-ttu-id="612f8-p116">[**Default chat history**] で、最初の要求時にチャット ルームごとに処理されるチャット メッセージ数を定義します。既定値は 30 で、これはグローバルな既定値です。管理者はカテゴリごとにチャット履歴を無効にできます。</span><span class="sxs-lookup"><span data-stu-id="612f8-p116">In **Default chat history**, define the number of chat messages that will be processed for each room upon first request. By default, the number is 30. This is the global default, and administrators can disable chat history per category.</span></span>
        
        <div>
        

        > [!IMPORTANT]  
        > <span data-ttu-id="612f8-158">常設チャットサーバーはこれらのメッセージをメモリにキャッシュするので、この数を増やすと、メッセージがキャッシュされます。</span><span class="sxs-lookup"><span data-stu-id="612f8-158">Persistent Chat Server will cache these messages in memory, so if you increase this number, more messages will be cached.</span></span> <span data-ttu-id="612f8-159">履歴コンテンツには、検索を使用していつでもアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="612f8-159">You can always access historical content by search.</span></span> <span data-ttu-id="612f8-160">既定値は、チャット ルームに接続したときに最初に表示されるメッセージの最大数を規定しているにすぎません。</span><span class="sxs-lookup"><span data-stu-id="612f8-160">The default number simply determines the maximum number of messages that you initially see when connecting to a chat room.</span></span>

        
        </div>
    
      - <span data-ttu-id="612f8-p118">[**最大ファイル サイズ (KB)**] で、各チャット履歴の最大ファイル サイズを選択します。既定値は 20 MB (20,000 KB) です。これは、システム内のチャット ルーム (対応する [**分類**] 設定でファイルのアップロードが有効化されているチャット ルーム) にアップロードできるファイルの最大サイズです。</span><span class="sxs-lookup"><span data-stu-id="612f8-p118">In **Maximum file size (KB)**, select the maximum file size of each chat history. By default, the number is 20 MB (20,000 KB). This is the maximum size for a file that can be uploaded to any chat room in the system (for which file uploads are enabled by its corresponding **Category** setting).</span></span>
        
        <div>
        

        > [!IMPORTANT]  
        > <span data-ttu-id="612f8-164">この設定は、カスタムアプリケーションまたは以前のグループチャットクライアント (Office Communications Server 2007 R2 &nbsp; グループチャットサーバーまたは Lync server 2010、グループチャット) が会議室にファイルを投稿できるため、サーバーで適用されます。</span><span class="sxs-lookup"><span data-stu-id="612f8-164">This setting is enforced on the server because custom applications or previous Group Chat clients (Office Communications Server 2007 R2&nbsp;Group Chat Server or Lync Server 2010, Group Chat) can post files to a room.</span></span> <span data-ttu-id="612f8-165">Lync 2013 クライアントはファイルのアップロード/ダウンロード機能を備えていないため、純粋な Lync 2013 展開または Lync 2013 クライアントを使用している場合は、常設チャットサーバーのチャットルームにファイルを投稿することはできません。</span><span class="sxs-lookup"><span data-stu-id="612f8-165">The Lync 2013 client does not have file upload/download capability, so if you have a pure Lync 2013 deployment or Lync 2013 client, it is not possible to post files in a Persistent Chat Server chat room.</span></span>

        
        </div>
    
      - <span data-ttu-id="612f8-166">[**参加者の更新制限**] で、参加者の更新の制限値を選択します。</span><span class="sxs-lookup"><span data-stu-id="612f8-166">In **Participant update limit**, select the limit for participant updates.</span></span> <span data-ttu-id="612f8-167">常設チャットサーバーは、接続されているユーザーの数がこの値に達するまで、すべての参加者に名簿情報 (チャットルームに接続されている人) を送信します。</span><span class="sxs-lookup"><span data-stu-id="612f8-167">Persistent Chat Server sends roster information (who is connected to a chat room) to all participants until the number of connected users reaches this number.</span></span> <span data-ttu-id="612f8-168">既定値は 75 です。</span><span class="sxs-lookup"><span data-stu-id="612f8-168">By default, the number is 75.</span></span> <span data-ttu-id="612f8-169">この制限は、常設チャットサーバーが、ルームにあるユーザーについて、接続されたクライアントに対して名簿の更新の送信を停止する、特定の会議室の参加者の最大数を示します。</span><span class="sxs-lookup"><span data-stu-id="612f8-169">This limit indicates the maximum number of participants in a given room beyond which Persistent Chat Server stops sending roster updates to connected clients about who is present in the room.</span></span>
    
      - <span data-ttu-id="612f8-p121">[**ルームの管理 URL**] で、ルーム管理 URL を選択します。これは Web ベースのチャット ルーム管理用の URL です。チャット ルームの管理をカスタマイズする必要がなく、既定の設定をそのまま使用する場合は、このオプションを空白のままにします。</span><span class="sxs-lookup"><span data-stu-id="612f8-p121">In **Room management URL**, select the room management URL. This is the URL for a web-based room management deployment. If you don’t need to customize room management, and you simply use the default setting, leave this option blank.</span></span>
        
        <span data-ttu-id="612f8-173">ルームの作成環境をカスタマイズして、特定のビジネスワークフローを含める必要がある場合は、常設チャットサーバーソフトウェア開発キット (SDK) を使用してカスタムルーム管理ソリューションを構築し、どこかにホストし、URL をここに配置することができます。</span><span class="sxs-lookup"><span data-stu-id="612f8-173">If you want to customize your room creation experience and include your specific business workflow, you can build a custom room management solution by using the Persistent Chat Server Software Development Kit (SDK), host it somewhere, and put the URL here.</span></span> <span data-ttu-id="612f8-174">ユーザーがチャット ルームを表示または作成するときにカスタム チャット ルーム管理ソリューションを使用するよう、この URL がクライアントに伝えられます。</span><span class="sxs-lookup"><span data-stu-id="612f8-174">This URL is sent down to the client so that when a user tries to view/create a room, he or she is directed to your custom room management solution.</span></span>

7.  <span data-ttu-id="612f8-175">[**確定**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="612f8-175">Click **Commit**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

