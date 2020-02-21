---
title: 'Lync Server 2013: トポロジへの常設チャットサーバーの追加'
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
ms.openlocfilehash: 5ae7ca7e475fd106608dea09fedf250ef541a5c9
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/21/2020
ms.locfileid: "42191410"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="add-persistent-chat-server-to-the-topology-in-lync-server-2013"></a><span data-ttu-id="7e5b1-102">Lync Server 2013 で常設チャットサーバーをトポロジに追加する</span><span class="sxs-lookup"><span data-stu-id="7e5b1-102">Add Persistent Chat Server to the topology in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7e5b1-103">_**トピックの最終更新日:** 2012-10-06_</span><span class="sxs-lookup"><span data-stu-id="7e5b1-103">_**Topic Last Modified:** 2012-10-06_</span></span>

<span data-ttu-id="7e5b1-104">常設チャットサーバーをサポートするように展開を構成する前に、Lync Server 2013、常設チャットサーバーのサポートをトポロジに組み込む必要があります。</span><span class="sxs-lookup"><span data-stu-id="7e5b1-104">You must incorporate Lync Server 2013, Persistent Chat Server support in your topology before you can configure your deployment to support Persistent Chat Server.</span></span> <span data-ttu-id="7e5b1-105">このトピックの情報では、トポロジビルダーを使用して、既存のトポロジに常設チャットサーバーのサポートを追加する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="7e5b1-105">The information in this topic describes how to use Topology Builder to add Persistent Chat Server support to your existing topology.</span></span>

<div>

## <a name="to-add-persistent-chat-server-to-a-topology"></a><span data-ttu-id="7e5b1-106">常設チャットサーバーをトポロジに追加するには</span><span class="sxs-lookup"><span data-stu-id="7e5b1-106">To add Persistent Chat Server to a topology</span></span>

<span data-ttu-id="7e5b1-107">障害復旧構成を行わずに単一の常設チャットサーバープールをインストールするには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="7e5b1-107">Perform the following steps for installing a single Persistent Chat Server pool without a disaster recovery configuration.</span></span> <span data-ttu-id="7e5b1-108">高可用性および障害復旧用に拡張された常設チャットサーバープールを構成する方法については、「展開」のドキュメントの「[高可用性と障害2013復旧のための常設チャットサーバーの構成](lync-server-2013-configuring-persistent-chat-server-for-high-availability-and-disaster-recovery.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7e5b1-108">For configuring a stretched Persistent Chat Server pool for high availability and disaster recovery, see [Configuring Persistent Chat Server for high availability and disaster recovery in Lync Server 2013](lync-server-2013-configuring-persistent-chat-server-for-high-availability-and-disaster-recovery.md) in the Deployment documentation.</span></span>

<span data-ttu-id="7e5b1-109">複数の常設チャットサーバープールを展開するには、各プールに対して同じ手順を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="7e5b1-109">To deploy multiple Persistent Chat Server pools, repeat the same process for each pool.</span></span>

1.  <span data-ttu-id="7e5b1-110">Lync Server 2013 を実行しているコンピューター、または Lync Server 管理ツールがインストールされているコンピューターで、ローカルユーザーグループのメンバーであるアカウント (または同等のユーザー権限を持つアカウント) を使用してログオンします。</span><span class="sxs-lookup"><span data-stu-id="7e5b1-110">On a computer that is running Lync Server 2013 or on which the Lync Server administrative tools are installed, log on using an account that is a member of the local Users group (or an account with equivalent user rights).</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="7e5b1-111">トポロジを定義するには、ローカルユーザーグループのメンバーであるアカウントを使用します。ただし、Lync Server 2013 サーバーをインストールするために必要なトポロジを公開するには、 <STRONG>Domain Admins</STRONG>グループおよび<STRONG>RTCUniversalServerAdmins</STRONG>グループのメンバーであり、常設チャットサーバーのファイルストアに対して使用するファイルストアに対するフルコントロールのアクセス許可 (つまり、読み取り、書き込み、および変更) を持つアカウントを使用する必要があります (つまり、トポロジビルダーが必要な dacl を構成できるようにするため)。、またはそれと同等の権限を持つアカウント。</span><span class="sxs-lookup"><span data-stu-id="7e5b1-111">You can define a topology by using an account that is a member of the local Users group, but to publish a topology, which is required to install a Lync Server 2013 server, you must use an account that is a member of the <STRONG>Domain Admins</STRONG> group and the <STRONG>RTCUniversalServerAdmins</STRONG> group, and that has full control permissions (that is, read, write, and modify) on the file store that you are going to use for the Persistent Chat Server file store (that is, so that Topology Builder can configure the required DACLs), or an account with equivalent rights.</span></span>

    
    </div>

2.  <span data-ttu-id="7e5b1-112">トポロジ ビルダーを開始します。</span><span class="sxs-lookup"><span data-stu-id="7e5b1-112">Start Topology Builder.</span></span>

3.  <span data-ttu-id="7e5b1-113">コンソールツリーで、[**常設チャットプール**] ノードに移動して展開し、常設チャットサーバープールを選択するか、ノードを右クリックして [**新しい常設チャットプール**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="7e5b1-113">In the console tree, navigate to the **Persistent Chat Pools** node and expand it to select a Persistent Chat Server pool, or right-click the node and select **New Persistent Chat Pool**.</span></span> <span data-ttu-id="7e5b1-114">プールの完全修飾ドメイン名 (FQDN) を定義し、そのプールが単一サーバー プールまたは複数サーバー プールのどちらの構成であるかを指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="7e5b1-114">You must define the pool’s fully qualified domain name (FQDN), and indicate whether the pool will be a single-server pool or multiple-server pool deployment.</span></span>
    
    <span data-ttu-id="7e5b1-115">**複数のコンピュータープール**または**単一コンピュータープール**を選択できます。</span><span class="sxs-lookup"><span data-stu-id="7e5b1-115">You can choose a **Multiple Computer Pool** or a **Single Computer Pool**.</span></span> <span data-ttu-id="7e5b1-116">常設チャットサーバープールに複数の常設チャットサーバーフロントエンドサーバーを使用することを計画している場合は、前者を選択します。</span><span class="sxs-lookup"><span data-stu-id="7e5b1-116">Choose the former if you are planning to have more than one Persistent Chat Server Front End Server in your Persistent Chat Server pool.</span></span> <span data-ttu-id="7e5b1-117">このオプションは、1台のコンピュータープールを作成した後、後で追加することはできないため、ここで行うか、または後の時点で実行してください。</span><span class="sxs-lookup"><span data-stu-id="7e5b1-117">Make this choice now, or at a later point, because after you create a single computer pool, you cannot add additional servers to it later.</span></span> <span data-ttu-id="7e5b1-118">複数のコンピュータープールを選択する場合は、プールを構成する個別の常設チャットサーバーのフロントエンドサーバーの名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="7e5b1-118">If you choose a multiple computer pool, enter the names of the individual Persistent Chat Server Front End Servers that comprise the pool.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="7e5b1-119">常設チャットサーバーの役割が Lync Server 2013&nbsp;standard edition サーバーにインストールされている場合、Fqdn は standard edition サーバーの fqdn と一致する必要があります。</span><span class="sxs-lookup"><span data-stu-id="7e5b1-119">If the Persistent Chat Server role is being installed on a Lync Server 2013&nbsp;Standard Edition server, the FQDN needs to match the FQDN of the Standard Edition server.</span></span>

    
    </div>

4.  <span data-ttu-id="7e5b1-120">常設チャットサーバープールの簡易**表示名**を定義します。</span><span class="sxs-lookup"><span data-stu-id="7e5b1-120">Define a simple **Display Name** for the Persistent Chat Server pool.</span></span> <span data-ttu-id="7e5b1-121">この表示名は、カスタムクライアントによって使用されます。特に、複数の常設チャットサーバープールがある場合は、ルームを区別するために使用できます。</span><span class="sxs-lookup"><span data-stu-id="7e5b1-121">The display name can be used by custom clients, particularly when there are multiple Persistent Chat Server pools, to differentiate rooms.</span></span>

5.  <span data-ttu-id="7e5b1-122">Lync Server フロントエンドサーバーと通信するために常設チャットサーバーによって使用されるポートを定義します。</span><span class="sxs-lookup"><span data-stu-id="7e5b1-122">Define the port used by the Persistent Chat Server to communicate with Lync Server Front End Servers.</span></span> <span data-ttu-id="7e5b1-123">既定のポートは 5041 です。</span><span class="sxs-lookup"><span data-stu-id="7e5b1-123">The default port is 5041.</span></span>

6.  <span data-ttu-id="7e5b1-124">組織にコンプライアンス サポートが必要な場合は、[**コンプライアンスを有効にする**] チェック ボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="7e5b1-124">If your organization requires compliance support, select the **Enable compliance** check box.</span></span> <span data-ttu-id="7e5b1-125">常設チャットサーバーのコンプライアンスサービスを選択すると、常設チャットサーバーのフロントエンドサーバーと同じコンピューターにインストールされます。</span><span class="sxs-lookup"><span data-stu-id="7e5b1-125">If chosen, the Persistent Chat Server Compliance service is installed on the same computer as the Persistent Chat Server Front End Server.</span></span> <span data-ttu-id="7e5b1-126">常設チャットサーバーのコンプライアンス用の SQL Server バックエンドサーバーを後で選択するように求めるメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="7e5b1-126">You are prompted to select a SQL Server Back End Server for Persistent Chat Server Compliance later.</span></span>

7.  <span data-ttu-id="7e5b1-127">常設チャットサーバープールのサイトの類似性を割り当てます。</span><span class="sxs-lookup"><span data-stu-id="7e5b1-127">Assign site affinity for the Persistent Chat Server pool.</span></span> <span data-ttu-id="7e5b1-128">[この**プールを\<サイト\>の既定値として使用**する] チェックボックスをオンにするか、**すべてのサイトの**既定のプールとしてこのプールを使用して、この常設チャットサーバープールを現在のサイトまたはすべてのサイトの既定のプールとして指定します。</span><span class="sxs-lookup"><span data-stu-id="7e5b1-128">Select the **Use this pool as default for site \<SiteName\>** check box or **Use this pool as default for all sites** to designate this Persistent Chat Server pool as the default pool for the current site or all sites.</span></span> <span data-ttu-id="7e5b1-129">Lync 2013 クライアントを使用してルームを作成して管理する場合、ユーザーのサイトに関連付けられている既定のプールが、ルームの作成と管理の操作によって、そのプールに対するルームの作成および管理の操作をルーティングできるようになります。</span><span class="sxs-lookup"><span data-stu-id="7e5b1-129">When the Lync 2013 client is used to create and manage rooms, the default pool associated with the user’s site is used by the room creation and management experience so that it can route room creation and management operations to that pool.</span></span> <span data-ttu-id="7e5b1-130">これは、複数の常設チャットサーバープールが展開されており、常設チャットサーバーのルーム作成および管理機能を使用する場合にのみ適用されます。</span><span class="sxs-lookup"><span data-stu-id="7e5b1-130">This only applies when you have multiple Persistent Chat Server pools deployed, and want to use the room creation and management features of Persistent Chat Server.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="7e5b1-131">常設チャットサーバーソフトウェア開発キット (SDK) を使用して、ルームの作成と管理の機能をカスタマイズできます。</span><span class="sxs-lookup"><span data-stu-id="7e5b1-131">You can customize the room creation and management features using the Persistent Chat Server Software Development Kit (SDK).</span></span><BR><span data-ttu-id="7e5b1-132">障害復旧用の SQL Server バックアップデータベースを構成する方法の詳細については、「展開」のドキュメントの「configure<A href="lync-server-2013-configuring-persistent-chat-server-for-high-availability-and-disaster-recovery.md">常設 Chat server for high availability and disaster recovery In Lync server 2013</A> 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7e5b1-132">For details about how to configure SQL Server backup databases for disaster recovery, see <A href="lync-server-2013-configuring-persistent-chat-server-for-high-availability-and-disaster-recovery.md">Configuring Persistent Chat Server for high availability and disaster recovery in Lync Server 2013</A> in the Deployment documentation.</span></span>

    
    </div>

8.  <span data-ttu-id="7e5b1-133">次のいずれかの操作を実行して、**常設チャットサーバーのバックエンド (チャットルームのコンテンツが保存されている) の SQL ストア**を定義します。</span><span class="sxs-lookup"><span data-stu-id="7e5b1-133">Define the **SQL store for the Persistent Chat Server Back End (where chat room content is stored)** by doing one of the following:</span></span>
    
      - <span data-ttu-id="7e5b1-134">既存の SQL Server データベースを使用するには、ドロップダウンリストで、使用する SQL Server データベースの名前をクリックします。</span><span class="sxs-lookup"><span data-stu-id="7e5b1-134">To use an existing SQL Server database, in the drop-down list, click the name of the SQL Server database that you want to use.</span></span>
    
      - <span data-ttu-id="7e5b1-135">新しい SQL Server データベースを指定するには、[**新規**] をクリックし、[**新しい Sql ストアの定義**] で以下の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="7e5b1-135">To specify a new SQL Server database, click **New**, and in **Define New SQL Store**, perform the following:</span></span>
    
    <!-- end list -->
    
      - <span data-ttu-id="7e5b1-136">[ **Sql server の fqdn**] で、新しい sql server データベースを作成する sql SERVER の fqdn を指定します。</span><span class="sxs-lookup"><span data-stu-id="7e5b1-136">In **SQL Server FQDN**, specify the FQDN of the SQL Server on which you want to create the new SQL Server database.</span></span>
    
      - <span data-ttu-id="7e5b1-137">[**既定のインスタンス**] を選択して既定のインスタンスを使用するか、別のインスタンスを指定する場合は、[**名前付きインスタンス**] を選択して、使用するインスタンスを指定します。</span><span class="sxs-lookup"><span data-stu-id="7e5b1-137">Either select **Default Instance** to use the default instance or, to specify a different instance, select **Named Instance**, and specify the instance that you want to use.</span></span>

9.  <span data-ttu-id="7e5b1-138">コンプライアンスを有効にした場合は、SQL Server コンプライアンスデータベースを定義します。</span><span class="sxs-lookup"><span data-stu-id="7e5b1-138">Define the SQL Server compliance database if you enabled Compliance.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="7e5b1-139">常設チャットサーバーデータベースおよび常設チャットサーバーのコンプライアンスデータベースの高可用性を確保するための SQL Server ミラーの構成方法の詳細については、「展開」のドキュメントの「configure<A href="lync-server-2013-configuring-persistent-chat-server-for-high-availability-and-disaster-recovery.md">常設 Chat server for high availability and disaster recovery In Lync server 2013</A> 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7e5b1-139">For details about how to configure SQL Server mirrors for high availability for the Persistent Chat Server database and the Persistent Chat Server compliance database, see <A href="lync-server-2013-configuring-persistent-chat-server-for-high-availability-and-disaster-recovery.md">Configuring Persistent Chat Server for high availability and disaster recovery in Lync Server 2013</A> in the Deployment documentation.</span></span>

    
    </div>

10. <span data-ttu-id="7e5b1-140">ファイルストアを定義します。</span><span class="sxs-lookup"><span data-stu-id="7e5b1-140">Define the file store.</span></span> <span data-ttu-id="7e5b1-141">ファイルストアとは、ファイルリポジトリにアップロードされたファイルのコピーが格納されるフォルダーです (たとえば、チャットルームに投稿されたファイル添付ファイルの保存など)。</span><span class="sxs-lookup"><span data-stu-id="7e5b1-141">A file store is a folder where a copy of any file uploaded to the file repository is stored (for example, storing file attachments posted to a chat room).</span></span> <span data-ttu-id="7e5b1-142">複数サーバーの常設チャットサーバートポロジの場合、これは汎用名前付け規則 (UNC) パスである必要があります。また、単一サーバーの常設チャットサーバートポロジでは、ローカルファイルパスにすることができます。</span><span class="sxs-lookup"><span data-stu-id="7e5b1-142">In the case of a multiple-server Persistent Chat Server topology, this must be a Universal Naming Convention (UNC) path; and for a single-server Persistent Chat Server topology, it can be a local file path.</span></span>
    
    <span data-ttu-id="7e5b1-143">既存のファイル ストアを使用するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="7e5b1-143">To use an existing file store, perform the following steps:</span></span>
    
      - <span data-ttu-id="7e5b1-144">[**ファイル サーバーの FQDN**] で、新しいファイル ストアを作成するファイル ストアの FQDN を指定します。</span><span class="sxs-lookup"><span data-stu-id="7e5b1-144">In **File Server FQDN**, specify the FQDN of the file store on which you want to create the new file store.</span></span>
    
      - <span data-ttu-id="7e5b1-145">[**ファイル共有**] で、使用するファイル ストアを指定します。</span><span class="sxs-lookup"><span data-stu-id="7e5b1-145">In **File Share**, specify the file store that you want to use.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="7e5b1-146">ファイルストアを作成する前に、トポロジビルダーでファイルストアを定義することはできますが、トポロジを公開する前に定義する定義済みの場所にファイルストアを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="7e5b1-146">You can define the file store in Topology Builder before you create the file store, but you must create the file store in the defined location you define before you publish the topology.</span></span>

    
    </div>

11. <span data-ttu-id="7e5b1-147">この常設チャットサーバープールの次ホップとして使用するフロントエンドサーバープールを選択します。</span><span class="sxs-lookup"><span data-stu-id="7e5b1-147">Select the Front End Server pool to be used as a next hop for this Persistent Chat Server pool.</span></span> <span data-ttu-id="7e5b1-148">これは、このプールに常設チャットサーバーの要求をルーティングすることができるフロントエンドサーバープールです。</span><span class="sxs-lookup"><span data-stu-id="7e5b1-148">This is the Front End Server pool that will be able to route Persistent Chat Server requests to this pool.</span></span>

12. <span data-ttu-id="7e5b1-149">構成を保存するには、[**完了**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="7e5b1-149">To save the configuration, click **Finish**.</span></span> <span data-ttu-id="7e5b1-150">常設チャットサーバープールは、トポロジビルダーに、特定のプール設定と共に表示されます。</span><span class="sxs-lookup"><span data-stu-id="7e5b1-150">The Persistent Chat Server pool appears in Topology Builder accompanied by your specific pool settings.</span></span>
    
    <span data-ttu-id="7e5b1-151">常設チャットサーバーを使用している更新されたトポロジを公開するには、「展開」のドキュメントの「 [Lync Server 2013 で更新さ](lync-server-2013-publish-the-updated-topology.md)れたトポロジを公開する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7e5b1-151">To now publish your updated topology to which you’ve Persistent Chat Server, see [Publish the updated topology in Lync Server 2013](lync-server-2013-publish-the-updated-topology.md) in the Deployment documentation.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="7e5b1-152">トポロジビルダーが既に開いている場合は、「 <A href="lync-server-2013-publish-the-updated-topology.md">Lync Server 2013 で更新さ</A>れたトポロジを公開する」の手順3に進んで、更新したトポロジの公開を開始できます。</span><span class="sxs-lookup"><span data-stu-id="7e5b1-152">With Topology Builder already open, you can proceed to step 3 in <A href="lync-server-2013-publish-the-updated-topology.md">Publish the updated topology in Lync Server 2013</A> to begin publishing your updated topology.</span></span>

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

