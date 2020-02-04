---
title: 'Lync Server 2013: 常設チャット サーバーをトポロジに追加する'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Add Persistent Chat Server to the topology
ms:assetid: 8389b307-8c17-4e45-b3b5-5dc9fcfc2ffb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205049(v=OCS.15)
ms:contentKeyID: 48184682
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 53f8c65f561a0f2c7b1937d60344c0177d221ba8
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41738237"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="add-persistent-chat-server-to-the-topology-in-lync-server-2013"></a><span data-ttu-id="cd5a4-102">Lync Server 2013 で常設チャット サーバーをトポロジに追加する</span><span class="sxs-lookup"><span data-stu-id="cd5a4-102">Add Persistent Chat Server to the topology in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="cd5a4-103">_**最終更新日:** 2012-10-06_</span><span class="sxs-lookup"><span data-stu-id="cd5a4-103">_**Topic Last Modified:** 2012-10-06_</span></span>

<span data-ttu-id="cd5a4-104">常設チャットサーバーをサポートするように展開を構成するには、お客様のトポロジで Lync Server 2013 の常設チャットサーバーのサポートを組み込む必要があります。</span><span class="sxs-lookup"><span data-stu-id="cd5a4-104">You must incorporate Lync Server 2013, Persistent Chat Server support in your topology before you can configure your deployment to support Persistent Chat Server.</span></span> <span data-ttu-id="cd5a4-105">このトピックでは、トポロジビルダーを使用して、既存のトポロジに常設チャットサーバーサポートを追加する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="cd5a4-105">The information in this topic describes how to use Topology Builder to add Persistent Chat Server support to your existing topology.</span></span>

<div>

## <a name="to-add-persistent-chat-server-to-a-topology"></a><span data-ttu-id="cd5a4-106">トポロジに常設チャットサーバーを追加するには</span><span class="sxs-lookup"><span data-stu-id="cd5a4-106">To add Persistent Chat Server to a topology</span></span>

<span data-ttu-id="cd5a4-107">災害回復構成を行わずに、1つの常設チャットサーバープールをインストールするには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="cd5a4-107">Perform the following steps for installing a single Persistent Chat Server pool without a disaster recovery configuration.</span></span> <span data-ttu-id="cd5a4-108">拡張された常設チャットサーバープールを構成して高可用性と障害回復を実現する方法については、展開ドキュメントの「 [Lync server 2013 で高可用性と障害回復のための常設チャットサーバーを構成](lync-server-2013-configuring-persistent-chat-server-for-high-availability-and-disaster-recovery.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="cd5a4-108">For configuring a stretched Persistent Chat Server pool for high availability and disaster recovery, see [Configuring Persistent Chat Server for high availability and disaster recovery in Lync Server 2013](lync-server-2013-configuring-persistent-chat-server-for-high-availability-and-disaster-recovery.md) in the Deployment documentation.</span></span>

<span data-ttu-id="cd5a4-109">複数の常設チャットサーバープールを展開するには、各プールで同じ手順を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="cd5a4-109">To deploy multiple Persistent Chat Server pools, repeat the same process for each pool.</span></span>

1.  <span data-ttu-id="cd5a4-110">Lync Server 2013 を実行しているか、Lync Server 管理ツールがインストールされているコンピューターで、ローカルユーザーグループのメンバーであるか、同等のユーザー権限を持つアカウントを使用してログオンします。</span><span class="sxs-lookup"><span data-stu-id="cd5a4-110">On a computer that is running Lync Server 2013 or on which the Lync Server administrative tools are installed, log on using an account that is a member of the local Users group (or an account with equivalent user rights).</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="cd5a4-111">トポロジを定義するには、ローカルユーザーグループのメンバーであるアカウントを使用します。ただし、Lync Server 2013 サーバーをインストールするために必要なトポロジを公開するには、<STRONG>ドメイン管理者</STRONG>グループと<STRONG>RTCUniversalServerAdmins</STRONG>グループのメンバーであるアカウントと、常設チャットサーバーファイルストアで使用するファイルストアのフルコントロールのアクセス許可 (つまり、読み取り、書き込み、変更) を使用する必要があります (つまり、トポロジビルダーが必要な dacl を構成できるようにします)。または、同等の権限を持つアカウント。</span><span class="sxs-lookup"><span data-stu-id="cd5a4-111">You can define a topology by using an account that is a member of the local Users group, but to publish a topology, which is required to install a Lync Server 2013 server, you must use an account that is a member of the <STRONG>Domain Admins</STRONG> group and the <STRONG>RTCUniversalServerAdmins</STRONG> group, and that has full control permissions (that is, read, write, and modify) on the file store that you are going to use for the Persistent Chat Server file store (that is, so that Topology Builder can configure the required DACLs), or an account with equivalent rights.</span></span>

    
    </div>

2.  <span data-ttu-id="cd5a4-112">トポロジビルダーを起動します。</span><span class="sxs-lookup"><span data-stu-id="cd5a4-112">Start Topology Builder.</span></span>

3.  <span data-ttu-id="cd5a4-113">コンソールツリーで、**常設チャットプール**ノードに移動して展開し、常設チャットサーバープールを選択するか、ノードを右クリックして [**新しい常設チャットプール**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="cd5a4-113">In the console tree, navigate to the **Persistent Chat Pools** node and expand it to select a Persistent Chat Server pool, or right-click the node and select **New Persistent Chat Pool**.</span></span> <span data-ttu-id="cd5a4-114">You must define the pool’s fully qualified domain name (FQDN), and indicate whether the pool will be a single-server pool or multiple-server pool deployment.</span><span class="sxs-lookup"><span data-stu-id="cd5a4-114">You must define the pool’s fully qualified domain name (FQDN), and indicate whether the pool will be a single-server pool or multiple-server pool deployment.</span></span>
    
    <span data-ttu-id="cd5a4-115">**複数のコンピュータープール**または**1 台のコンピュータープール**を選ぶことができます。</span><span class="sxs-lookup"><span data-stu-id="cd5a4-115">You can choose a **Multiple Computer Pool** or a **Single Computer Pool**.</span></span> <span data-ttu-id="cd5a4-116">常設チャットサーバープールに複数の常設チャットサーバーフロントエンドサーバーを使用することを計画している場合は、前者を選びます。</span><span class="sxs-lookup"><span data-stu-id="cd5a4-116">Choose the former if you are planning to have more than one Persistent Chat Server Front End Server in your Persistent Chat Server pool.</span></span> <span data-ttu-id="cd5a4-117">このオプションは、1台のコンピュータープールを作成した後で、後で追加することはできないため、ここで設定します。</span><span class="sxs-lookup"><span data-stu-id="cd5a4-117">Make this choice now, or at a later point, because after you create a single computer pool, you cannot add additional servers to it later.</span></span> <span data-ttu-id="cd5a4-118">複数のコンピュータープールを選択する場合は、プールを構成する個別の常設チャットサーバーのフロントエンドサーバーの名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="cd5a4-118">If you choose a multiple computer pool, enter the names of the individual Persistent Chat Server Front End Servers that comprise the pool.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="cd5a4-119">常設チャットサーバーの役割が Lync Server 2013&nbsp;Standard edition サーバーにインストールされている場合、Fqdn は standard edition サーバーの fqdn と一致する必要があります。</span><span class="sxs-lookup"><span data-stu-id="cd5a4-119">If the Persistent Chat Server role is being installed on a Lync Server 2013&nbsp;Standard Edition server, the FQDN needs to match the FQDN of the Standard Edition server.</span></span>

    
    </div>

4.  <span data-ttu-id="cd5a4-120">常設チャットサーバープールの簡易**表示名**を定義します。</span><span class="sxs-lookup"><span data-stu-id="cd5a4-120">Define a simple **Display Name** for the Persistent Chat Server pool.</span></span> <span data-ttu-id="cd5a4-121">この表示名は、カスタムクライアントで使うことができます。特に、複数の常設チャットサーバープールがある場合は、ルームを区別することができます。</span><span class="sxs-lookup"><span data-stu-id="cd5a4-121">The display name can be used by custom clients, particularly when there are multiple Persistent Chat Server pools, to differentiate rooms.</span></span>

5.  <span data-ttu-id="cd5a4-122">常設チャットサーバーが Lync Server フロントエンドサーバーと通信するために使用するポートを定義します。</span><span class="sxs-lookup"><span data-stu-id="cd5a4-122">Define the port used by the Persistent Chat Server to communicate with Lync Server Front End Servers.</span></span> <span data-ttu-id="cd5a4-123">既定のポートは 5041 です。</span><span class="sxs-lookup"><span data-stu-id="cd5a4-123">The default port is 5041.</span></span>

6.  <span data-ttu-id="cd5a4-124">組織にコンプライアンス サポートが必要な場合は、[**コンプライアンスを有効にする**] チェック ボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="cd5a4-124">If your organization requires compliance support, select the **Enable compliance** check box.</span></span> <span data-ttu-id="cd5a4-125">選択されている場合、常設チャット Server コンプライアンスサービスは、常設チャットサーバーフロントエンドサーバーと同じコンピューターにインストールされます。</span><span class="sxs-lookup"><span data-stu-id="cd5a4-125">If chosen, the Persistent Chat Server Compliance service is installed on the same computer as the Persistent Chat Server Front End Server.</span></span> <span data-ttu-id="cd5a4-126">後で常設チャットサーバーのコンプライアンス用の SQL Server バックエンドサーバーを選択するように求められます。</span><span class="sxs-lookup"><span data-stu-id="cd5a4-126">You are prompted to select a SQL Server Back End Server for Persistent Chat Server Compliance later.</span></span>

7.  <span data-ttu-id="cd5a4-127">常設チャットサーバープールにサイトのアフィニティを割り当てます。</span><span class="sxs-lookup"><span data-stu-id="cd5a4-127">Assign site affinity for the Persistent Chat Server pool.</span></span> <span data-ttu-id="cd5a4-128">この [**このプールをサイトの\<サイト\> **の既定のプールとして使用する] チェックボックスをオンにするか、またはすべてのサイトの既定のプールとしてこのプールを**使用**します。</span><span class="sxs-lookup"><span data-stu-id="cd5a4-128">Select the **Use this pool as default for site \<SiteName\>** check box or **Use this pool as default for all sites** to designate this Persistent Chat Server pool as the default pool for the current site or all sites.</span></span> <span data-ttu-id="cd5a4-129">Lync 2013 クライアントを使用して会議室の作成と管理を行う場合、ユーザーのサイトに関連付けられた既定のプールは、ルームの作成と管理のエクスペリエンスによって使用され、ルームの作成と管理の操作をそのプールにルーティングすることができます。</span><span class="sxs-lookup"><span data-stu-id="cd5a4-129">When the Lync 2013 client is used to create and manage rooms, the default pool associated with the user’s site is used by the room creation and management experience so that it can route room creation and management operations to that pool.</span></span> <span data-ttu-id="cd5a4-130">これは、複数の常設チャットサーバープールが展開されており、常設チャットサーバーのルーム作成と管理機能を使用する場合にのみ適用されます。</span><span class="sxs-lookup"><span data-stu-id="cd5a4-130">This only applies when you have multiple Persistent Chat Server pools deployed, and want to use the room creation and management features of Persistent Chat Server.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="cd5a4-131">常設チャットサーバーソフトウェア開発キット (SDK) を使って、ルームの作成と管理の機能をカスタマイズできます。</span><span class="sxs-lookup"><span data-stu-id="cd5a4-131">You can customize the room creation and management features using the Persistent Chat Server Software Development Kit (SDK).</span></span><BR><span data-ttu-id="cd5a4-132">ディザスターリカバリーのために SQL Server バックアップデータベースを構成する方法の詳細については、「展開ドキュメントの<A href="lync-server-2013-configuring-persistent-chat-server-for-high-availability-and-disaster-recovery.md">Lync server 2013 で高可用性と障害回復のための常設チャットサーバーを構成</A>する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="cd5a4-132">For details about how to configure SQL Server backup databases for disaster recovery, see <A href="lync-server-2013-configuring-persistent-chat-server-for-high-availability-and-disaster-recovery.md">Configuring Persistent Chat Server for high availability and disaster recovery in Lync Server 2013</A> in the Deployment documentation.</span></span>

    
    </div>

8.  <span data-ttu-id="cd5a4-133">次のいずれかの操作を行って、**常設チャットサーバーのバックエンド用の SQL ストア (チャットルームのコンテンツが保存されている場所) を**定義します。</span><span class="sxs-lookup"><span data-stu-id="cd5a4-133">Define the **SQL store for the Persistent Chat Server Back End (where chat room content is stored)** by doing one of the following:</span></span>
    
      - <span data-ttu-id="cd5a4-134">既存の SQL Server データベースを使用するには、ドロップダウンリストで、使用する SQL Server データベースの名前をクリックします。</span><span class="sxs-lookup"><span data-stu-id="cd5a4-134">To use an existing SQL Server database, in the drop-down list, click the name of the SQL Server database that you want to use.</span></span>
    
      - <span data-ttu-id="cd5a4-135">新しい SQL Server データベースを指定するには、[**新規**作成] をクリックし、[**新しい Sql ストアの定義**] で次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="cd5a4-135">To specify a new SQL Server database, click **New**, and in **Define New SQL Store**, perform the following:</span></span>
    
    <!-- end list -->
    
      - <span data-ttu-id="cd5a4-136">[ **Sql SERVER fqdn**] で、新しい sql server データベースを作成する sql SERVER の fqdn を指定します。</span><span class="sxs-lookup"><span data-stu-id="cd5a4-136">In **SQL Server FQDN**, specify the FQDN of the SQL Server on which you want to create the new SQL Server database.</span></span>
    
      - <span data-ttu-id="cd5a4-137">[**既定のインスタンス**] を選択して既定のインスタンスを使用するか、別のインスタンスを指定する場合は、[**名前付きインスタンス**] を選択して、使用するインスタンスを指定します。</span><span class="sxs-lookup"><span data-stu-id="cd5a4-137">Either select **Default Instance** to use the default instance or, to specify a different instance, select **Named Instance**, and specify the instance that you want to use.</span></span>

9.  <span data-ttu-id="cd5a4-138">コンプライアンスを有効にしている場合は、SQL Server コンプライアンスデータベースを定義します。</span><span class="sxs-lookup"><span data-stu-id="cd5a4-138">Define the SQL Server compliance database if you enabled Compliance.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="cd5a4-139">常設チャットサーバーデータベースおよび常設チャットサーバーのコンプライアンスデータベースに対して高可用性のための SQL Server ミラーを構成する方法の詳細については、展開ドキュメントの「 <A href="lync-server-2013-configuring-persistent-chat-server-for-high-availability-and-disaster-recovery.md">Lync server 2013 で高可用性と障害復旧のための常設チャットサーバーを構成</A>する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="cd5a4-139">For details about how to configure SQL Server mirrors for high availability for the Persistent Chat Server database and the Persistent Chat Server compliance database, see <A href="lync-server-2013-configuring-persistent-chat-server-for-high-availability-and-disaster-recovery.md">Configuring Persistent Chat Server for high availability and disaster recovery in Lync Server 2013</A> in the Deployment documentation.</span></span>

    
    </div>

10. <span data-ttu-id="cd5a4-140">ファイルストアを定義します。</span><span class="sxs-lookup"><span data-stu-id="cd5a4-140">Define the file store.</span></span> <span data-ttu-id="cd5a4-141">ファイルストアは、ファイルリポジトリにアップロードされたファイルのコピーが格納されているフォルダーです (たとえば、チャットルームに投稿された添付ファイルを保存します)。</span><span class="sxs-lookup"><span data-stu-id="cd5a4-141">A file store is a folder where a copy of any file uploaded to the file repository is stored (for example, storing file attachments posted to a chat room).</span></span> <span data-ttu-id="cd5a4-142">複数サーバーの常設チャットサーバートポロジの場合、これは汎用名前付け規則 (UNC) パスである必要があります。また、単一サーバーの常設チャットサーバートポロジでは、ローカルファイルパスにすることができます。</span><span class="sxs-lookup"><span data-stu-id="cd5a4-142">In the case of a multiple-server Persistent Chat Server topology, this must be a Universal Naming Convention (UNC) path; and for a single-server Persistent Chat Server topology, it can be a local file path.</span></span>
    
    <span data-ttu-id="cd5a4-143">既存のファイル ストアを使用するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="cd5a4-143">To use an existing file store, perform the following steps:</span></span>
    
      - <span data-ttu-id="cd5a4-144">[**ファイルサーバー fqdn**] で、新しいファイルストアを作成するファイルストアの FQDN を指定します。</span><span class="sxs-lookup"><span data-stu-id="cd5a4-144">In **File Server FQDN**, specify the FQDN of the file store on which you want to create the new file store.</span></span>
    
      - <span data-ttu-id="cd5a4-145">[**ファイル共有**] で、使用するファイル ストアを指定します。</span><span class="sxs-lookup"><span data-stu-id="cd5a4-145">In **File Share**, specify the file store that you want to use.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="cd5a4-146">ファイルストアを作成する前に、トポロジビルダーでファイルストアを定義できますが、トポロジを公開する前に定義した定義された場所にファイルストアを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="cd5a4-146">You can define the file store in Topology Builder before you create the file store, but you must create the file store in the defined location you define before you publish the topology.</span></span>

    
    </div>

11. <span data-ttu-id="cd5a4-147">この常設チャットサーバープールの次ホップとして使用するフロントエンドサーバープールを選択します。</span><span class="sxs-lookup"><span data-stu-id="cd5a4-147">Select the Front End Server pool to be used as a next hop for this Persistent Chat Server pool.</span></span> <span data-ttu-id="cd5a4-148">これは、このプールへの常設チャットサーバー要求をルーティングできるフロントエンドサーバープールです。</span><span class="sxs-lookup"><span data-stu-id="cd5a4-148">This is the Front End Server pool that will be able to route Persistent Chat Server requests to this pool.</span></span>

12. <span data-ttu-id="cd5a4-149">構成を保存するには、[**完了**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="cd5a4-149">To save the configuration, click **Finish**.</span></span> <span data-ttu-id="cd5a4-150">常設チャットサーバープールは、特定のプール設定と共に、トポロジビルダーに表示されます。</span><span class="sxs-lookup"><span data-stu-id="cd5a4-150">The Persistent Chat Server pool appears in Topology Builder accompanied by your specific pool settings.</span></span>
    
    <span data-ttu-id="cd5a4-151">常設チャットサーバーを使用して更新されたトポロジを公開するには、展開ドキュメントの「 [Lync Server 2013 で更新されたトポロジを公開](lync-server-2013-publish-the-updated-topology.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="cd5a4-151">To now publish your updated topology to which you’ve Persistent Chat Server, see [Publish the updated topology in Lync Server 2013](lync-server-2013-publish-the-updated-topology.md) in the Deployment documentation.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="cd5a4-152">トポロジビルダーを既に開いている場合は、「更新されたトポロジを<A href="lync-server-2013-publish-the-updated-topology.md">Lync Server 2013 で公開</A>する」の手順3に進んで、更新されたトポロジの公開を開始できます。</span><span class="sxs-lookup"><span data-stu-id="cd5a4-152">With Topology Builder already open, you can proceed to step 3 in <A href="lync-server-2013-publish-the-updated-topology.md">Publish the updated topology in Lync Server 2013</A> to begin publishing your updated topology.</span></span>

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

