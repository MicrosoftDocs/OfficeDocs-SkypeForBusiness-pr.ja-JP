---
title: 'Lync Server 2013: 常設チャット サーバーのオプションをグローバルに、または常設チャット サーバー プール用に構成する'
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
ms.openlocfilehash: 86ee77dd34e3a43ea62ac6cffaf4af952b1c447e
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41762835"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configure-persistent-chat-server-options-globally-or-for-persistent-chat-server-pool-in-lync-server-2013"></a><span data-ttu-id="eed08-102">Lync Server 2013 で常設チャット サーバーのオプションをグローバルに、または常設チャット サーバー プール用に構成する</span><span class="sxs-lookup"><span data-stu-id="eed08-102">Configure Persistent Chat Server options globally or for Persistent Chat Server pool in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="eed08-103">_**最終更新日:** 2012-10-06_</span><span class="sxs-lookup"><span data-stu-id="eed08-103">_**Topic Last Modified:** 2012-10-06_</span></span>

<span data-ttu-id="eed08-104">Lync Server 2013 コントロールパネルでは **、常設チャットページの\*\*\*\*常設チャット構成**セクションを使用して、すべての常設チャットサーバープールまたは特定の常設チャットサーバープールに適用される常設チャット設定をグローバルに構成することができます。</span><span class="sxs-lookup"><span data-stu-id="eed08-104">In Lync Server 2013 Control Panel, you can use the **Persistent Chat Configuration** section of the **Persistent Chat** page to configure Persistent Chat settings globally where it applies to all Persistent Chat Server pools, or for a specific Persistent Chat Server pool.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="eed08-105">常設チャットサーバーを構成して使用するには、最初にトポロジビルダーを使用して、トポロジに常設チャットサーバーサポートを追加してから、トポロジを発行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="eed08-105">To configure and use Persistent Chat Server, you must first use Topology Builder to add Persistent Chat Server support to the topology, and then publish the topology.</span></span> <span data-ttu-id="eed08-106">詳細については、展開ドキュメントの「 <A href="lync-server-2013-adding-persistent-chat-server-to-your-deployment.md">Lync server 2013 での展開への常設チャットサーバーの追加</A>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="eed08-106">For details, see <A href="lync-server-2013-adding-persistent-chat-server-to-your-deployment.md">Adding Persistent Chat Server to your deployment in Lync Server 2013</A> in the Deployment documentation.</span></span>



</div>

<div>

## <a name="to-configure-persistent-chat-options-globally"></a><span data-ttu-id="eed08-107">常設チャットのオプションをグローバルに構成するには</span><span class="sxs-lookup"><span data-stu-id="eed08-107">To configure Persistent Chat options globally</span></span>

1.  <span data-ttu-id="eed08-108">CsPersistentChatAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="eed08-108">From a user account that is assigned to the CsPersistentChatAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="eed08-109">[**スタート**] メニューから [Lync Server コントロールパネル] を選択するか、ブラウザーウィンドウを開き、管理 URL を入力します。</span><span class="sxs-lookup"><span data-stu-id="eed08-109">From the **Start** menu, select the Lync Server Control Panel or open a browser window, and then enter the Admin URL.</span></span> <span data-ttu-id="eed08-110">Lync Server コントロールパネルを起動するために使用できるさまざまな方法について詳しくは、「 [Lync server 2013 管理ツールを開く](lync-server-2013-open-lync-server-administrative-tools.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="eed08-110">For details about the different methods that you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="eed08-111">Windows PowerShell コマンドレットを使うこともできます。</span><span class="sxs-lookup"><span data-stu-id="eed08-111">You can also use Windows PowerShell cmdlets.</span></span> <span data-ttu-id="eed08-112">詳細については、展開ドキュメントの「 <A href="configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md">Windows PowerShell コマンドレットを使用して常設チャットサーバーを構成</A>する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="eed08-112">For details, see <A href="configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md">Configuring Persistent Chat Server by using Windows PowerShell cmdlets</A> in the Deployment documentation.</span></span>

    
    </div>

3.  <span data-ttu-id="eed08-113">左側のナビゲーション バーで [**常設チャット**] をクリックし、[**常設チャットの構成**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="eed08-113">In the left navigation bar, click **Persistent Chat**, and then click **Persistent Chat Configuration**.</span></span>

4.  <span data-ttu-id="eed08-114">[**常設チャットの構成**] ページで、[**新規] を**クリックし、[サイトの**構成**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="eed08-114">On the **Persistent Chat Configuration** page, click **New,** and then click **Site configuration**.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="eed08-115">サイトに展開されているすべての常設チャットサーバープールに構成を適用する場合は、このオプションを選びます。</span><span class="sxs-lookup"><span data-stu-id="eed08-115">Choose this option if you want the configuration to be applied to all Persistent Chat Server pools deployed in the site.</span></span> <span data-ttu-id="eed08-116">特定の常設チャットサーバープールに構成を適用する場合は、[<STRONG>プール構成</STRONG>] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="eed08-116">Click <STRONG>Pool Configuration</STRONG> if you want the configuration to be applied to a specific Persistent Chat Server pool.</span></span>

    
    </div>

5.  <span data-ttu-id="eed08-117">[**サイトの選択**] で、常設チャットサーバーのサイト構成用に構成するサイトを選びます。</span><span class="sxs-lookup"><span data-stu-id="eed08-117">In **Select a Site**, select the site to be configured for the Persistent Chat Server site configuration.</span></span>

6.  <span data-ttu-id="eed08-118">[**新規 常設チャットの構成**] で、次の操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="eed08-118">In **New Persistent Chat Configuration**, do the following:</span></span>
    
      - <span data-ttu-id="eed08-p105">[**名前**] で、新しい構成設定の名前を指定します。既定では、サイト名が既に存在します。</span><span class="sxs-lookup"><span data-stu-id="eed08-p105">In **Name**, specify a name for the new configuration settings. By default, the site name already exists.</span></span>
    
      - <span data-ttu-id="eed08-p106">[**既定のチャット履歴**] で、最初の要求時にチャット ルームごとに処理されるチャット メッセージ数を定義します。既定値は 30 で、これはグローバルな既定値です。管理者はカテゴリごとにチャット履歴を無効にできます。</span><span class="sxs-lookup"><span data-stu-id="eed08-p106">In **Default chat history**, define the number of chat messages that will be processed for each room upon first request. By default, the number is 30. This is the global default, and administrators can disable chat history per category.</span></span>
        
        <div>
        

        > [!IMPORTANT]  
        > <span data-ttu-id="eed08-124">常設チャットサーバーでは、これらのメッセージがメモリにキャッシュされるため、この数値を増やすと、より多くのメッセージがキャッシュされます。</span><span class="sxs-lookup"><span data-stu-id="eed08-124">Persistent Chat Server will cache these messages in memory, so if you increase this number, more messages will be cached.</span></span> <span data-ttu-id="eed08-125">履歴コンテンツには、検索を使用していつでもアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="eed08-125">You can always access historical content by search.</span></span> <span data-ttu-id="eed08-126">既定値は、チャット ルームに接続したときに最初に表示されるメッセージの最大数を規定しているにすぎません。</span><span class="sxs-lookup"><span data-stu-id="eed08-126">The default number simply determines the maximum number of messages that you initially see when connecting to a chat room.</span></span>

        
        </div>
    
      - <span data-ttu-id="eed08-p108">[**最大ファイル サイズ (KB)**] で、各チャット履歴の最大ファイル サイズを選択します。既定値は 20 MB (20,000 KB) です。これは、システム内のチャット ルーム (対応する [**分類**] 設定でファイルのアップロードが有効化されているチャット ルーム) にアップロードできるファイルの最大サイズです。</span><span class="sxs-lookup"><span data-stu-id="eed08-p108">In **Maximum file size (KB)**, select the maximum file size of each chat history. By default, the number is 20 MB (20,000 KB). This is the maximum size for a file that can be uploaded to any chat room in the system (for which file uploads are enabled by its corresponding **Category** setting).</span></span>
        
        <div>
        

        > [!IMPORTANT]  
        > <span data-ttu-id="eed08-130">この設定は、Office Communications Server 2007 R2&nbsp;グループチャットサーバーまたは Lync server 2010 を使用するカスタムアプリケーションまたは以前のグループチャットクライアントで、サーバーに適用されます。グループチャットでは、ファイルをルームに投稿できます。</span><span class="sxs-lookup"><span data-stu-id="eed08-130">This setting is enforced on the server because custom applications or previous Group Chat clients using Office Communications Server 2007 R2&nbsp;Group Chat Server or Lync Server 2010, Group Chat can post files to a room.</span></span> <span data-ttu-id="eed08-131">Lync 2013 クライアントには、ファイルのアップロード/ダウンロード機能がありません。そのため、Lync 2013 の展開または Lync 2013 クライアントが純粋にインストールされている場合は、常設チャットサーバーのチャットルームにファイルを投稿することはできません。</span><span class="sxs-lookup"><span data-stu-id="eed08-131">The Lync 2013 client does not have file upload/download capability, so if you have a pure Lync 2013 deployment or Lync 2013 client, it is not possible to post files in a Persistent Chat Server chat room.</span></span>

        
        </div>
    
      - <span data-ttu-id="eed08-132">[**参加者の更新制限**] で、参加者の更新の制限値を選択します。</span><span class="sxs-lookup"><span data-stu-id="eed08-132">In **Participant update limit**, select the limit for participant updates.</span></span> <span data-ttu-id="eed08-133">常設チャットサーバーは、接続されているユーザーの数がこの番号に到達するまで、すべての参加者にリスト情報 (チャットルームに接続されているユーザー) を送信します。</span><span class="sxs-lookup"><span data-stu-id="eed08-133">Persistent Chat Server sends roster information (who is connected to a chat room) to all participants until the number of connected users reaches this number.</span></span> <span data-ttu-id="eed08-134">既定値は 75 です。</span><span class="sxs-lookup"><span data-stu-id="eed08-134">By default, the number is 75.</span></span> <span data-ttu-id="eed08-135">この制限は、常設チャットサーバーが、会議室に存在するユーザーに対して、接続されているクライアントに対して、リストの更新情報を送信するのを超えた、特定のルーム内の参加者の最大数を示します。</span><span class="sxs-lookup"><span data-stu-id="eed08-135">This limit indicates the maximum number of participants in a given room beyond which Persistent Chat Server stops sending roster updates to connected clients about who is present in the room.</span></span>
    
      - <span data-ttu-id="eed08-p111">(オプション) [**ルームの管理 URL**] で、ルーム管理 URL を選択します。これは Web ベースのカスタム チャット ルーム管理用の URL です。チャット ルームの管理をカスタマイズする必要がなく、既定の設定をそのまま使用する場合は、このオプションを空白のままにします。URL を設定すると、その URL は内部と外部の両方のチャット ルーム管理 URL として適用されます。</span><span class="sxs-lookup"><span data-stu-id="eed08-p111">(Optional.) In **Room management URL**, select the room management URL. This is the URL for a web-based custom room management. If you don’t need to customize room management, and you simply use the default setting, leave this option blank. After the URL is set, it is applied as both the internal and external room management URL.</span></span>
        
        <span data-ttu-id="eed08-140">会議室の作成環境をカスタマイズして、特定のビジネスワークフローを含める場合は、常設チャットサーバーソフトウェア開発キット (SDK) を使用して、カスタムルーム管理ソリューションを構築し、どこかにホストして、URL をここに入力します。</span><span class="sxs-lookup"><span data-stu-id="eed08-140">If you want to customize your room creation experience and include your specific business workflow, you can build a custom room management solution by using the Persistent Chat Server Software Development Kit (SDK), host it somewhere, and put the URL here.</span></span> <span data-ttu-id="eed08-141">ユーザーがチャット ルームを表示または作成するときにカスタム チャット ルーム管理ソリューションを使用するよう、この URL がクライアントに伝えられます。</span><span class="sxs-lookup"><span data-stu-id="eed08-141">This URL is sent down to the client, so that when a user tries to view or create a room, he or she is directed to your custom room management solution.</span></span>

7.  <span data-ttu-id="eed08-142">[**コミット**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="eed08-142">Click **Commit**.</span></span>

</div>

<div>

## <a name="to-configure-persistent-chat-options-for-a-specific-persistent-chat-server-pool"></a><span data-ttu-id="eed08-143">特定の常設チャットサーバープールの常設チャットオプションを構成するには</span><span class="sxs-lookup"><span data-stu-id="eed08-143">To configure Persistent Chat options for a specific Persistent Chat Server pool</span></span>

1.  <span data-ttu-id="eed08-144">CsPersistentChatAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="eed08-144">From a user account that is assigned to the CsPersistentChatAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="eed08-145">[**スタート**] メニューから [Lync Server コントロールパネル] を選択するか、ブラウザーウィンドウを開き、管理 URL を入力します。</span><span class="sxs-lookup"><span data-stu-id="eed08-145">From the **Start** menu, select the Lync Server Control Panel, or open a browser window, and then enter the Admin URL.</span></span> <span data-ttu-id="eed08-146">Lync Server コントロールパネルを起動するために使用できるさまざまな方法について詳しくは、「 [Lync server 2013 管理ツールを開く](lync-server-2013-open-lync-server-administrative-tools.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="eed08-146">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="eed08-147">Windows PowerShell コマンドレットを使うこともできます。</span><span class="sxs-lookup"><span data-stu-id="eed08-147">You can also use Windows PowerShell cmdlets.</span></span> <span data-ttu-id="eed08-148">詳細については、展開ドキュメントの「 <A href="configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md">Windows PowerShell コマンドレットを使用して常設チャットサーバーを構成</A>する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="eed08-148">For details, see <A href="configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md">Configuring Persistent Chat Server by using Windows PowerShell cmdlets</A> in the Deployment documentation.</span></span>

    
    </div>

3.  <span data-ttu-id="eed08-149">左側のナビゲーション バーで [**常設チャット**] をクリックし、[**常設チャットの構成**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="eed08-149">In the left navigation bar, click **Persistent Chat**, and then click **Persistent Chat Configuration**.</span></span>

4.  <span data-ttu-id="eed08-150">[**常設チャットの構成**] ページで、[**新規**] をクリックし、[**プール構成**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="eed08-150">On the **Persistent Chat Configuration** page, click **New**, and then click **Pool configuration**.</span></span>

5.  <span data-ttu-id="eed08-151">[**サービスの選択**] で、構成する常設チャットサーバープールに関連するサービスを選びます。</span><span class="sxs-lookup"><span data-stu-id="eed08-151">In **Select a Service**, select the service associated with the Persistent Chat Server pool to be configured.</span></span>

6.  <span data-ttu-id="eed08-152">[**新規 常設チャットの構成**] で、次の操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="eed08-152">In **New Persistent Chat Configuration**, do the following:</span></span>
    
      - <span data-ttu-id="eed08-p115">[**名前**] で、新しい構成設定の名前を指定します。既定では、サイト プール名が既に存在します。</span><span class="sxs-lookup"><span data-stu-id="eed08-p115">In **Name**, specify a name for the new configuration settings. By default, the site pool name already exists.</span></span>
    
      - <span data-ttu-id="eed08-p116">[**既定のチャット履歴**] で、最初の要求時にチャット ルームごとに処理されるチャット メッセージ数を定義します。既定値は 30 で、これはグローバルな既定値です。管理者はカテゴリごとにチャット履歴を無効にできます。</span><span class="sxs-lookup"><span data-stu-id="eed08-p116">In **Default chat history**, define the number of chat messages that will be processed for each room upon first request. By default, the number is 30. This is the global default, and administrators can disable chat history per category.</span></span>
        
        <div>
        

        > [!IMPORTANT]  
        > <span data-ttu-id="eed08-158">常設チャットサーバーでは、これらのメッセージがメモリにキャッシュされるため、この数値を増やすと、より多くのメッセージがキャッシュされます。</span><span class="sxs-lookup"><span data-stu-id="eed08-158">Persistent Chat Server will cache these messages in memory, so if you increase this number, more messages will be cached.</span></span> <span data-ttu-id="eed08-159">履歴コンテンツには、検索を使用していつでもアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="eed08-159">You can always access historical content by search.</span></span> <span data-ttu-id="eed08-160">既定値は、チャット ルームに接続したときに最初に表示されるメッセージの最大数を規定しているにすぎません。</span><span class="sxs-lookup"><span data-stu-id="eed08-160">The default number simply determines the maximum number of messages that you initially see when connecting to a chat room.</span></span>

        
        </div>
    
      - <span data-ttu-id="eed08-p118">[**最大ファイル サイズ (KB)**] で、各チャット履歴の最大ファイル サイズを選択します。既定値は 20 MB (20,000 KB) です。これは、システム内のチャット ルーム (対応する [**分類**] 設定でファイルのアップロードが有効化されているチャット ルーム) にアップロードできるファイルの最大サイズです。</span><span class="sxs-lookup"><span data-stu-id="eed08-p118">In **Maximum file size (KB)**, select the maximum file size of each chat history. By default, the number is 20 MB (20,000 KB). This is the maximum size for a file that can be uploaded to any chat room in the system (for which file uploads are enabled by its corresponding **Category** setting).</span></span>
        
        <div>
        

        > [!IMPORTANT]  
        > <span data-ttu-id="eed08-164">この設定は、カスタムアプリケーションまたは以前のグループチャットクライアント (Office Communications Server 2007 R2&nbsp;グループチャットサーバーまたは Lync server 2010、グループチャット) を使用して、会議室にファイルを投稿することができるため、サーバーに適用されます。</span><span class="sxs-lookup"><span data-stu-id="eed08-164">This setting is enforced on the server because custom applications or previous Group Chat clients (Office Communications Server 2007 R2&nbsp;Group Chat Server or Lync Server 2010, Group Chat) can post files to a room.</span></span> <span data-ttu-id="eed08-165">Lync 2013 クライアントには、ファイルのアップロード/ダウンロード機能がありません。そのため、Lync 2013 の展開または Lync 2013 クライアントが純粋にインストールされている場合は、常設チャットサーバーのチャットルームにファイルを投稿することはできません。</span><span class="sxs-lookup"><span data-stu-id="eed08-165">The Lync 2013 client does not have file upload/download capability, so if you have a pure Lync 2013 deployment or Lync 2013 client, it is not possible to post files in a Persistent Chat Server chat room.</span></span>

        
        </div>
    
      - <span data-ttu-id="eed08-166">[**参加者の更新制限**] で、参加者の更新の制限値を選択します。</span><span class="sxs-lookup"><span data-stu-id="eed08-166">In **Participant update limit**, select the limit for participant updates.</span></span> <span data-ttu-id="eed08-167">常設チャットサーバーは、接続されているユーザーの数がこの番号に到達するまで、すべての参加者にリスト情報 (チャットルームに接続されているユーザー) を送信します。</span><span class="sxs-lookup"><span data-stu-id="eed08-167">Persistent Chat Server sends roster information (who is connected to a chat room) to all participants until the number of connected users reaches this number.</span></span> <span data-ttu-id="eed08-168">既定値は 75 です。</span><span class="sxs-lookup"><span data-stu-id="eed08-168">By default, the number is 75.</span></span> <span data-ttu-id="eed08-169">この制限は、常設チャットサーバーが、会議室に存在するユーザーに対して、接続されているクライアントに対して、リストの更新情報を送信するのを超えた、特定のルーム内の参加者の最大数を示します。</span><span class="sxs-lookup"><span data-stu-id="eed08-169">This limit indicates the maximum number of participants in a given room beyond which Persistent Chat Server stops sending roster updates to connected clients about who is present in the room.</span></span>
    
      - <span data-ttu-id="eed08-p121">[**ルームの管理 URL**] で、ルーム管理 URL を選択します。これは Web ベースのチャット ルーム管理用の URL です。チャット ルームの管理をカスタマイズする必要がなく、既定の設定をそのまま使用する場合は、このオプションを空白のままにします。</span><span class="sxs-lookup"><span data-stu-id="eed08-p121">In **Room management URL**, select the room management URL. This is the URL for a web-based room management deployment. If you don’t need to customize room management, and you simply use the default setting, leave this option blank.</span></span>
        
        <span data-ttu-id="eed08-173">会議室の作成環境をカスタマイズして、特定のビジネスワークフローを含める場合は、常設チャットサーバーソフトウェア開発キット (SDK) を使用して、カスタムルーム管理ソリューションを構築し、どこかにホストして、URL をここに入力します。</span><span class="sxs-lookup"><span data-stu-id="eed08-173">If you want to customize your room creation experience and include your specific business workflow, you can build a custom room management solution by using the Persistent Chat Server Software Development Kit (SDK), host it somewhere, and put the URL here.</span></span> <span data-ttu-id="eed08-174">ユーザーがチャット ルームを表示または作成するときにカスタム チャット ルーム管理ソリューションを使用するよう、この URL がクライアントに伝えられます。</span><span class="sxs-lookup"><span data-stu-id="eed08-174">This URL is sent down to the client so that when a user tries to view/create a room, he or she is directed to your custom room management solution.</span></span>

7.  <span data-ttu-id="eed08-175">[**コミット**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="eed08-175">Click **Commit**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

