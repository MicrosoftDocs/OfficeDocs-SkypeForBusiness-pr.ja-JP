---
title: Skype for Business Server 2015 トポロジへの常設チャット サーバーの追加
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/28/2016
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 6b4f4d69-3c9d-4bc7-bc9b-46427a095de2
description: '概要: このトピックでは、Skype for Business Server 2015 トポロジに常設チャット サーバーを追加する方法について説明します。'
ms.openlocfilehash: 3b0f3ca57af4b9bf53125e38e1aa3005099b5b70
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49825107"
---
# <a name="add-persistent-chat-server-to-your-skype-for-business-server-2015-topology"></a><span data-ttu-id="927d5-103">Skype for Business Server 2015 トポロジへの常設チャット サーバーの追加</span><span class="sxs-lookup"><span data-stu-id="927d5-103">Add Persistent Chat Server to your Skype for Business Server 2015 topology</span></span>
 
<span data-ttu-id="927d5-104">**概要:** このトピックでは、Skype for Business Server 2015 トポロジに常設チャット サーバーを追加する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="927d5-104">**Summary:** Read this topic to learn how to add Persistent Chat Server to your Skype for Business Server 2015 topology.</span></span>
  
<span data-ttu-id="927d5-105">常設チャット サーバーを展開する予定の各サーバーに必要なソフトウェアをインストールした後、トポロジ ビルダーを使用して次の処理を行います。</span><span class="sxs-lookup"><span data-stu-id="927d5-105">After you install the prerequisite software on each server on which you plan to deploy Persistent Chat Server, you use Topology Builder to:</span></span> 
  
- <span data-ttu-id="927d5-106">常設チャット サーバーを含むトポロジを更新する</span><span class="sxs-lookup"><span data-stu-id="927d5-106">Update your topology to include Persistent Chat Server</span></span>
    
- <span data-ttu-id="927d5-107">更新されたトポロジを公開する</span><span class="sxs-lookup"><span data-stu-id="927d5-107">Publish the updated topology</span></span>
    
> [!NOTE] 
> <span data-ttu-id="927d5-108">常設チャットは Skype for Business Server 2015 で使用できますが、Skype for Business Server 2019 ではサポートされなくなりました。</span><span class="sxs-lookup"><span data-stu-id="927d5-108">Persistent chat is available in Skype for Business Server 2015 but is no longer supported in Skype for Business Server 2019.</span></span> <span data-ttu-id="927d5-109">Teams でも同じ機能を使用できます。</span><span class="sxs-lookup"><span data-stu-id="927d5-109">The same functionality is available in Teams.</span></span> <span data-ttu-id="927d5-110">詳細については、「Microsoft Teams のアップグレード [の開始」を参照してください](/microsoftteams/upgrade-start-here)。</span><span class="sxs-lookup"><span data-stu-id="927d5-110">For more information, see [Getting started with your Microsoft Teams upgrade](/microsoftteams/upgrade-start-here).</span></span> <span data-ttu-id="927d5-111">常設チャットを使用する必要がある場合は、この機能を必要とするユーザーを Teams に移行するか、Skype for Business Server 2015 を引き続き使用するかのどちらかを選択できます。</span><span class="sxs-lookup"><span data-stu-id="927d5-111">If you need to use Persistent chat, your choices are to either migrate users requiring this functionality to Teams, or to continue using Skype for Business Server 2015.</span></span> 

## <a name="update-your-topology-to-include-persistent-chat-server"></a><span data-ttu-id="927d5-112">常設チャット サーバーを含むトポロジを更新する</span><span class="sxs-lookup"><span data-stu-id="927d5-112">Update your topology to include Persistent Chat Server</span></span>

<span data-ttu-id="927d5-113">障害復旧構成を使用せずに単一の常設チャット サーバー プールをインストールするには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="927d5-113">Perform the following steps for installing a single Persistent Chat Server pool without a disaster recovery configuration.</span></span> <span data-ttu-id="927d5-114">高可用性と障害復旧用にストレッチされた常設チャット サーバー プールを構成する方法については [、「Configure high availability and disaster recovery for Persistent Chat Server in Skype for Business Server 2015」](../../deploy/deploy-high-availability-and-disaster-recovery/configure-hadr-for-persistent-chat.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="927d5-114">For configuring a stretched Persistent Chat Server pool for high availability and disaster recovery, see [Configure high availability and disaster recovery for Persistent Chat Server in Skype for Business Server 2015](../../deploy/deploy-high-availability-and-disaster-recovery/configure-hadr-for-persistent-chat.md).</span></span>
  
<span data-ttu-id="927d5-115">複数の常設チャット サーバー プールを展開するには、プールごとに同じプロセスを繰り返します。</span><span class="sxs-lookup"><span data-stu-id="927d5-115">To deploy multiple Persistent Chat Server pools, repeat the same process for each pool.</span></span>
  
1. <span data-ttu-id="927d5-116">Skype for Business Server を実行しているコンピューター、または Skype for Business Server 管理ツールがインストールされているコンピューターで、ローカルの Users グループのメンバーであるアカウント (または同等のユーザー権限を持つアカウント) を使用してログオンします。</span><span class="sxs-lookup"><span data-stu-id="927d5-116">On a computer that is running Skype for Business Server or on which the Skype for Business Server administrative tools are installed, log on using an account that is a member of the local Users group (or an account with equivalent user rights).</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="927d5-117">ローカル Users グループのメンバーであるアカウントを使用してトポロジを定義できます。 ただし、Skype for Business Server のインストールに必要なトポロジを公開するには **、Domain Admins** グループと **RTCUniversalServerAdmins** グループのメンバーであり、常設チャット サーバー ファイル ストアで使用するファイル ストアに対するフル コントロールのアクセス許可 (読み取り、書き込み、および変更) を持つアカウント (トポロジ ビルダーが必要な DACL を構成できるよう)、または同等の権限を持つアカウントを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="927d5-117">You can define a topology by using an account that is a member of the local Users group, but to publish a topology, which is required to install Skype for Business Server, you must use an account that is a member of the **Domain Admins** group and the **RTCUniversalServerAdmins** group, and that has full control permissions (read, write, and modify) on the file store that you are going to use for the Persistent Chat Server file store (so that Topology Builder can configure the required DACLs), or an account with equivalent rights.</span></span>
  
2. <span data-ttu-id="927d5-118">トポロジ ビルダーを開始します。</span><span class="sxs-lookup"><span data-stu-id="927d5-118">Start Topology Builder.</span></span>
    
3. <span data-ttu-id="927d5-119">コンソール ツリーで、常設チャットプール ノードに移動し、それを展開して Skype for Business Server プールを選択するか、ノードを右クリックして [新しい常設チャット プール] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="927d5-119">In the console tree, navigate to the **Persistent Chat Pools** node and expand it to select a Skype for Business Server pool, or right-click the node and select **New Persistent Chat Pool**.</span></span> <span data-ttu-id="927d5-120">プールの完全修飾ドメイン名 (FQDN) を定義し、プールが単一サーバー プールか複数サーバー プールの展開かを指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="927d5-120">You must define the pool's fully qualified domain name (FQDN), and indicate whether the pool will be a single-server pool or multiple-server pool deployment.</span></span>
    
    <span data-ttu-id="927d5-121">複数のコンピューター プール **または 1 つの** コンピューター **プールを選択できます**。</span><span class="sxs-lookup"><span data-stu-id="927d5-121">You can choose a **Multiple Computer Pool** or a **Single Computer Pool**.</span></span> <span data-ttu-id="927d5-122">常設チャット サーバー プールに複数のフロントエンド サーバーを使用する場合は、前者を選択します。</span><span class="sxs-lookup"><span data-stu-id="927d5-122">Choose the former if you are planning to have more than one Front End Server in your Persistent Chat Server pool.</span></span> <span data-ttu-id="927d5-123">1 台のコンピューター プールを作成した後、後でサーバーを追加できないので、この選択を今すぐ、または後で行います。</span><span class="sxs-lookup"><span data-stu-id="927d5-123">Make this choice now, or at a later point, because after you create a single computer pool, you cannot add additional servers to it later.</span></span> <span data-ttu-id="927d5-124">複数のコンピューター プールを選択する場合は、プールを構成する個々のフロントエンド サーバーの名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="927d5-124">If you choose a multiple computer pool, enter the names of the individual Front End Servers that comprise the pool.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="927d5-125">常設チャット サーバーの役割が Standard Edition サーバーにインストールされている場合、FQDN は Standard Edition サーバーの FQDN と一致する必要があります。</span><span class="sxs-lookup"><span data-stu-id="927d5-125">If the Persistent Chat Server role is being installed on a Standard Edition server, the FQDN needs to match the FQDN of the Standard Edition server.</span></span> 
  
4. <span data-ttu-id="927d5-126">常設チャット サーバー **プールの簡単** な表示名を定義します。</span><span class="sxs-lookup"><span data-stu-id="927d5-126">Define a simple **Display Name** for the Persistent Chat Server pool.</span></span> <span data-ttu-id="927d5-127">表示名は、特にルームを区別する複数の常設チャット サーバー プールがある場合に、カスタム クライアントで使用できます。</span><span class="sxs-lookup"><span data-stu-id="927d5-127">The display name can be used by custom clients, particularly when there are multiple Persistent Chat Server pools to differentiate rooms.</span></span>
    
5. <span data-ttu-id="927d5-128">常設チャット サーバーが Skype for Business Server フロントエンド サーバーと通信するために使用するポートを定義します。</span><span class="sxs-lookup"><span data-stu-id="927d5-128">Define the port used by the Persistent Chat Server to communicate with Skype for Business Server Front End Servers.</span></span> <span data-ttu-id="927d5-129">既定のポートは 5041 です。</span><span class="sxs-lookup"><span data-stu-id="927d5-129">The default port is 5041.</span></span>
    
6. <span data-ttu-id="927d5-130">組織にコンプライアンス サポートが必要な場合は、[**コンプライアンスを有効にする**] チェック ボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="927d5-130">If your organization requires compliance support, select the **Enable compliance** check box.</span></span> <span data-ttu-id="927d5-131">選択した場合、常設チャット サーバー コンプライアンス サービスは常設チャット サーバー フロントエンド サーバーと同じコンピューターにインストールされます。</span><span class="sxs-lookup"><span data-stu-id="927d5-131">If chosen, the Persistent Chat Server Compliance service is installed on the same computer as the Persistent Chat Server Front End Server.</span></span> <span data-ttu-id="927d5-132">後で常設チャット サーバーコンプライアンス用のSQL Serverを選択するように求めるメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="927d5-132">You are prompted to select a SQL Server Back End Server for Persistent Chat Server Compliance later.</span></span>
    
7. <span data-ttu-id="927d5-133">常設チャット サーバー プールのサイト アフィニティを割り当てる。</span><span class="sxs-lookup"><span data-stu-id="927d5-133">Assign site affinity for the Persistent Chat Server pool.</span></span> <span data-ttu-id="927d5-134">[この **プール \<SiteName\> を** サイトの既定として使用する]チェック ボックスをオンにするか、このプールをすべてのサイトの既定として使用して、この常設チャット サーバー プールを現在のサイトまたはすべてのサイトの既定のプールとして指定します。</span><span class="sxs-lookup"><span data-stu-id="927d5-134">Select the **Use this pool as default for site \<SiteName\>** check box or **Use this pool as default for all sites** to designate this Persistent Chat Server pool as the default pool for the current site or all sites.</span></span> <span data-ttu-id="927d5-135">Skype for Business クライアントを使用してルームを作成および管理する場合、ユーザーのサイトに関連付けられている既定のプールは、ルームの作成と管理のエクスペリエンスによって使用され、ルームの作成および管理操作をそのプールにルーティングできます。</span><span class="sxs-lookup"><span data-stu-id="927d5-135">When the Skype for Business client is used to create and manage rooms, the default pool associated with the user's site is used by the room creation and management experience so that it can route room creation and management operations to that pool.</span></span> <span data-ttu-id="927d5-136">これは、複数の常設チャット サーバー プールが展開され、常設チャット サーバーのルームの作成および管理機能を使用する場合にのみ適用されます。</span><span class="sxs-lookup"><span data-stu-id="927d5-136">This only applies when you have multiple Persistent Chat Server pools deployed, and want to use the room creation and management features of Persistent Chat Server.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="927d5-137">常設チャット サーバー ソフトウェア開発キット (SDK) を使用して、ルームの作成および管理機能をカスタマイズできます。</span><span class="sxs-lookup"><span data-stu-id="927d5-137">You can customize the room creation and management features using the Persistent Chat Server Software Development Kit (SDK).</span></span> 
  
8. <span data-ttu-id="927d5-138">次のいずれかをSQLして、常設チャット サーバー のバック エンド (チャット ルームのコンテンツが格納 **される場所)** の管理ストアを定義します。</span><span class="sxs-lookup"><span data-stu-id="927d5-138">Define the **SQL store for the Persistent Chat Server Back End (where chat room content is stored)** by doing one of the following:</span></span>
    
   - <span data-ttu-id="927d5-139">既存の SQL Server ストアを使用するには、ドロップダウン リストで、使用する SQL Server ストアの名前をクリックします。</span><span class="sxs-lookup"><span data-stu-id="927d5-139">To use an existing SQL Server store, in the drop-down list, click the name of the SQL Server store that you want to use.</span></span>
    
   - <span data-ttu-id="927d5-140">新しいデータベースを指定SQL Server、[新規] をクリックし、[新しいストアの定義] SQL **実行** します。</span><span class="sxs-lookup"><span data-stu-id="927d5-140">To specify a new SQL Server database, click **New**, and in **Define New SQL Store**, perform the following:</span></span>
    
   - <span data-ttu-id="927d5-141">[SQL SERVER **FQDN]** で、新しいデータベースSQL Server作成するサーバーの FQDN をSQL Serverします。</span><span class="sxs-lookup"><span data-stu-id="927d5-141">In **SQL Server FQDN**, specify the FQDN of the SQL Server on which you want to create the new SQL Server database.</span></span>
    
   - <span data-ttu-id="927d5-142">[**既定のインスタンス**] を選択して既定のインスタンスを使用するか、別のインスタンスを指定する場合は、[**名前付きインスタンス**] を選択して、使用するインスタンスを指定します。</span><span class="sxs-lookup"><span data-stu-id="927d5-142">Either select **Default Instance** to use the default instance or, to specify a different instance, select **Named Instance**, and specify the instance that you want to use.</span></span>
    
     > [!NOTE]
     > <span data-ttu-id="927d5-143">障害復旧用に SQL Server バックアップ データベースを構成する方法の詳細については [、「Configure high availability and disaster recovery for Persistent Chat Server in Skype for Business Server 2015」](../../deploy/deploy-high-availability-and-disaster-recovery/configure-hadr-for-persistent-chat.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="927d5-143">For details about how to configure SQL Server backup databases for disaster recovery, see [Configure high availability and disaster recovery for Persistent Chat Server in Skype for Business Server 2015](../../deploy/deploy-high-availability-and-disaster-recovery/configure-hadr-for-persistent-chat.md).</span></span> 
  
9. <span data-ttu-id="927d5-144">コンプライアンスを有効SQL Server、コンプライアンス ストアを定義します。</span><span class="sxs-lookup"><span data-stu-id="927d5-144">Define the SQL Server compliance store if you enabled Compliance.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="927d5-145">常設チャット サーバー データベースと常設チャット サーバー コンプライアンス データベースの高可用性を実現するために SQL Server ミラーを構成する方法の詳細については [、「Configure high availability and disaster recovery for Persistent Chat Server in Skype for Business Server 2015」](../../deploy/deploy-high-availability-and-disaster-recovery/configure-hadr-for-persistent-chat.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="927d5-145">For details about how to configure SQL Server mirrors for high availability for the Persistent Chat Server database and the Persistent Chat Server compliance database, see [Configure high availability and disaster recovery for Persistent Chat Server in Skype for Business Server 2015](../../deploy/deploy-high-availability-and-disaster-recovery/configure-hadr-for-persistent-chat.md).</span></span> 
  
10. <span data-ttu-id="927d5-146">ファイル ストアを定義します。</span><span class="sxs-lookup"><span data-stu-id="927d5-146">Define the file store.</span></span> <span data-ttu-id="927d5-147">ファイル ストアは、ファイル リポジトリにアップロードされたファイルのコピーが保存されるフォルダーです (たとえば、チャット ルームに投稿された添付ファイルを格納します)。</span><span class="sxs-lookup"><span data-stu-id="927d5-147">A file store is a folder where a copy of any file uploaded to the file repository is stored (for example, storing file attachments posted to a chat room).</span></span> <span data-ttu-id="927d5-148">複数サーバーの常設チャット サーバー トポロジの場合、これは汎用名前付け規則 (UNC) パスである必要があります。また、単一サーバーの常設チャット サーバー トポロジの場合は、ローカル ファイル パスを使用できます。</span><span class="sxs-lookup"><span data-stu-id="927d5-148">In the case of a multiple-server Persistent Chat Server topology, this must be a Universal Naming Convention (UNC) path; and for a single-server Persistent Chat Server topology, it can be a local file path.</span></span>
    
    <span data-ttu-id="927d5-149">既存のファイル ストアを使用するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="927d5-149">To use an existing file store, perform the following steps:</span></span>
    
    - <span data-ttu-id="927d5-150">[ **ファイル サーバーの FQDN]** で、新しいファイル ストアを作成するコンピューターの FQDN を指定します。</span><span class="sxs-lookup"><span data-stu-id="927d5-150">In **File Server FQDN**, specify the FQDN of the machine on which you want to create the new file store.</span></span>
    
    - <span data-ttu-id="927d5-151">[**ファイル共有**] で、使用するファイル ストアを指定します。</span><span class="sxs-lookup"><span data-stu-id="927d5-151">In **File Share**, specify the file store that you want to use.</span></span>
    
      > [!IMPORTANT]
      > <span data-ttu-id="927d5-152">ファイル ストアを作成する前にトポロジ ビルダーでファイル ストアを定義できますが、トポロジを公開する前に、定義した場所にファイル ストアを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="927d5-152">You can define the file store in Topology Builder before you create the file store, but you must create the file store in the defined location you define before you publish the topology.</span></span> <span data-ttu-id="927d5-153">ファイル ストアが存在しない場合、トポロジの公開は失敗します。</span><span class="sxs-lookup"><span data-stu-id="927d5-153">If the file store doesn't already exist, attempts to publish the topology will fail.</span></span> 
  
11. <span data-ttu-id="927d5-154">この常設チャット サーバー プールの次ホップとして使用するフロントエンド サーバー プールを選択します。</span><span class="sxs-lookup"><span data-stu-id="927d5-154">Select the Front End Server pool to be used as a next hop for this Persistent Chat Server pool.</span></span> <span data-ttu-id="927d5-155">これは、常設チャット サーバー要求をこのプールにルーティングできるフロントエンド サーバー プールです。</span><span class="sxs-lookup"><span data-stu-id="927d5-155">This is the Front End Server pool that will be able to route Persistent Chat Server requests to this pool.</span></span>
    
12. <span data-ttu-id="927d5-156">構成を保存するには、[**完了**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="927d5-156">To save the configuration, click **Finish**.</span></span> <span data-ttu-id="927d5-157">常設チャット サーバー プールは、特定のプール設定と共にトポロジ ビルダーに表示されます。</span><span class="sxs-lookup"><span data-stu-id="927d5-157">The Persistent Chat Server pool appears in Topology Builder accompanied by your specific pool settings.</span></span>
    
    <span data-ttu-id="927d5-158">常設チャット サーバーを追加した更新されたトポロジを公開するには、「更新されたトポロジを公開する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="927d5-158">To publish your updated topology to which you've added Persistent Chat Server, see Publish the updated topology.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="927d5-159">トポロジ ビルダーが既に開いている場合は、「更新されたトポロジを公開する」の手順 3 に進み、更新されたトポロジの公開を開始できます。</span><span class="sxs-lookup"><span data-stu-id="927d5-159">With Topology Builder already open, you can proceed to step 3 in Publish the updated topology to begin publishing your updated topology.</span></span> 
  
## <a name="publish-the-updated-topology"></a><span data-ttu-id="927d5-160">更新されたトポロジを公開する</span><span class="sxs-lookup"><span data-stu-id="927d5-160">Publish the updated topology</span></span>
<span data-ttu-id="927d5-161"><a name="BKMK_PublishTopology"> </a></span><span class="sxs-lookup"><span data-stu-id="927d5-161"><a name="BKMK_PublishTopology"> </a></span></span>

<span data-ttu-id="927d5-162">トポロジ ビルダーでトポロジを更新した後、Skype for Business Server を構成して使用する前に、トポロジを中央管理ストアに公開する必要があります。</span><span class="sxs-lookup"><span data-stu-id="927d5-162">After updating your topology in Topology Builder, you must publish the topology to the Central Management store before you can configure and use Skype for Business Server.</span></span> <span data-ttu-id="927d5-163">このデータの読み取り専用コピーはトポロジ内のすべてのサーバーにレプリケートされ、すべてのサーバーは、トポロジおよび他の構成の変更と同期された状態で維持されます。</span><span class="sxs-lookup"><span data-stu-id="927d5-163">Read-only copies of the data are replicated to all servers in the topology to keep all servers in sync with topology and other configuration changes.</span></span>
  
<span data-ttu-id="927d5-164">トポロジを公開する前に、常設チャット サーバーのデータベースをインストールします。</span><span class="sxs-lookup"><span data-stu-id="927d5-164">Before you publish your topology, install the databases for Persistent Chat Server.</span></span> <span data-ttu-id="927d5-165">[操作] および [データベースのインストール] を選択して、トポロジ ビルダーを使用 **して** データベース **をインストールします**。</span><span class="sxs-lookup"><span data-stu-id="927d5-165">Use Topology Builder to install databases by selecting **Action** and **Install Database**.</span></span>
  
1. <span data-ttu-id="927d5-166">Skype for Business Server を実行しているコンピューター、または Skype for Business Server 管理ツールがインストールされているコンピューターで、 **Domain Admins** グループと **RTCUniversalServerAdmins** グループの両方のメンバーであり、常設チャット サーバーファイル ストアで使用するファイル ストアに対するフル コントロールのアクセス許可 (読み取り、書き込み、および変更) を持つアカウント (トポロジ ビルダーが必要な随意アクセス制御リスト (DACL) を構成できる) または同等のユーザー権限を持つアカウントを使用してログオンします。</span><span class="sxs-lookup"><span data-stu-id="927d5-166">On a computer that is running Skype for Business Server or on which the Skype for Business Server administrative tools are installed, log on using an account that is a member of both the **Domain Admins** group and the **RTCUniversalServerAdmins** group, and that has full control permissions (read, write, and modify) on the file store to be used for the Persistent Chat Server file store (so that Topology Builder can configure the required discretionary access control lists (DACLs)), or an account with equivalent user rights.</span></span>
    
2. <span data-ttu-id="927d5-167">トポロジ ビルダーを開始します。</span><span class="sxs-lookup"><span data-stu-id="927d5-167">Start Topology Builder.</span></span> <span data-ttu-id="927d5-168">ローカル **ファイルをローカルに保存した場合は、ローカル** ファイルから [トポロジを開く] を選択します。</span><span class="sxs-lookup"><span data-stu-id="927d5-168">Select **Open Topology from a local file** if you saved it locally.</span></span>
    
3. <span data-ttu-id="927d5-169">コンソール ツリーで **、Skype for Business Server 2015** を右クリックし、[トポロジの公開] **をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="927d5-169">In the console tree, right-click **Skype for Business Server 2015**, and then click **Publish Topology**.</span></span>
    
4. <span data-ttu-id="927d5-170">[**トポロジの公開**] ページで、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="927d5-170">On the **Publish the topology** page, click **Next**.</span></span>
    
5. <span data-ttu-id="927d5-171">[**公開ウィザードの完了**] ページで、トポロジが正常に公開されたことを確認し、[**完了**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="927d5-171">On the **Publishing wizard complete** page, verify that the topology was successfully published, and then click **Finish**.</span></span>
    

