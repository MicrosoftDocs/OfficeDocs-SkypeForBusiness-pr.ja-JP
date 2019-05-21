---
title: Skype for Business Server 2015 トポロジに常設チャットサーバーを追加する
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/28/2016
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 6b4f4d69-3c9d-4bc7-bc9b-46427a095de2
description: '概要: このトピックでは、Skype for Business Server 2015 トポロジに常設チャットサーバーを追加する方法について説明します。'
ms.openlocfilehash: c953b93d8ea20b8878269c8be0540ba8e032ce87
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2019
ms.locfileid: "34282302"
---
# <a name="add-persistent-chat-server-to-your-skype-for-business-server-2015-topology"></a><span data-ttu-id="24726-103">Skype for Business Server 2015 トポロジに常設チャットサーバーを追加する</span><span class="sxs-lookup"><span data-stu-id="24726-103">Add Persistent Chat Server to your Skype for Business Server 2015 topology</span></span>
 
<span data-ttu-id="24726-104">**概要:** このトピックでは、Skype for Business Server 2015 トポロジに常設チャットサーバーを追加する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="24726-104">**Summary:** Read this topic to learn how to add Persistent Chat Server to your Skype for Business Server 2015 topology.</span></span>
  
<span data-ttu-id="24726-105">常設チャットサーバーの展開を計画している各サーバーに、必須のソフトウェアをインストールしたら、次のようにトポロジビルダーを使用します。</span><span class="sxs-lookup"><span data-stu-id="24726-105">After you install the prerequisite software on each server on which you plan to deploy Persistent Chat Server, you use Topology Builder to:</span></span> 
  
- <span data-ttu-id="24726-106">トポロジを更新して常設チャット サーバーを含める</span><span class="sxs-lookup"><span data-stu-id="24726-106">Update your topology to include Persistent Chat Server</span></span>
    
- <span data-ttu-id="24726-107">更新されたトポロジを公開する</span><span class="sxs-lookup"><span data-stu-id="24726-107">Publish the updated topology</span></span>
    
> [!NOTE] 
> <span data-ttu-id="24726-108">常設チャットは Skype for Business Server 2015 で使用できますが、Skype for Business Server 2019 ではサポートされなくなりました。</span><span class="sxs-lookup"><span data-stu-id="24726-108">Persistent chat is available in Skype for Business Server 2015 but is no longer supported in Skype for Business Server 2019.</span></span> <span data-ttu-id="24726-109">Teams でも同じ機能を使用できます。</span><span class="sxs-lookup"><span data-stu-id="24726-109">The same functionality is available in Teams.</span></span> <span data-ttu-id="24726-110">詳細については、「 [Skype For business から Microsoft Teams への旅](/microsoftteams/journey-skypeforbusiness-teams)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="24726-110">For more information, see [Journey from Skype for Business to Microsoft Teams](/microsoftteams/journey-skypeforbusiness-teams).</span></span> <span data-ttu-id="24726-111">常設チャットを使用する必要がある場合は、この機能が必要なユーザーをチームに移行するか、Skype for Business Server 2015 を使い続けるかのいずれかを選択できます。</span><span class="sxs-lookup"><span data-stu-id="24726-111">If you need to use Persistent chat, your choices are to either migrate users requiring this functionality to Teams, or to continue using Skype for Business Server 2015.</span></span> 

## <a name="update-your-topology-to-include-persistent-chat-server"></a><span data-ttu-id="24726-112">トポロジを更新して常設チャット サーバーを含める</span><span class="sxs-lookup"><span data-stu-id="24726-112">Update your topology to include Persistent Chat Server</span></span>

<span data-ttu-id="24726-113">災害回復構成を行わずに、1つの常設チャットサーバープールをインストールするには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="24726-113">Perform the following steps for installing a single Persistent Chat Server pool without a disaster recovery configuration.</span></span> <span data-ttu-id="24726-114">拡張された常設チャットサーバープールを構成して高可用性と障害回復を実現する方法については、「 [Skype For Business server 2015 での常設チャットサーバーの高可用性と障害回復を構成](../../deploy/deploy-high-availability-and-disaster-recovery/configure-hadr-for-persistent-chat.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="24726-114">For configuring a stretched Persistent Chat Server pool for high availability and disaster recovery, see [Configure high availability and disaster recovery for Persistent Chat Server in Skype for Business Server 2015](../../deploy/deploy-high-availability-and-disaster-recovery/configure-hadr-for-persistent-chat.md).</span></span>
  
<span data-ttu-id="24726-115">複数の常設チャットサーバープールを展開するには、各プールで同じ手順を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="24726-115">To deploy multiple Persistent Chat Server pools, repeat the same process for each pool.</span></span>
  
1. <span data-ttu-id="24726-116">Skype for Business Server を実行しているコンピューター、または Skype for Business Server 管理ツールがインストールされているコンピューターで、ローカルユーザーグループのメンバーであるアカウント (または同等のユーザー権限を持つアカウント) を使ってログオンします。</span><span class="sxs-lookup"><span data-stu-id="24726-116">On a computer that is running Skype for Business Server or on which the Skype for Business Server administrative tools are installed, log on using an account that is a member of the local Users group (or an account with equivalent user rights).</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="24726-117">トポロジを定義するには、local Users グループのメンバーであるアカウントを使用しますが、Skype for Business Server をインストールするために必要なトポロジを公開するには、 **Domain Admins**グループ**のメンバーであるアカウントを使用する必要があります。RTCUniversalServerAdmins**グループ。これには、常設チャットサーバーファイルストア (Topology Builder で必要な dacl を構成できるようにします) のフルコントロールのアクセス許可 (読み取り、書き込み、変更)、またはそのアカウントの同等の権利。</span><span class="sxs-lookup"><span data-stu-id="24726-117">You can define a topology by using an account that is a member of the local Users group, but to publish a topology, which is required to install Skype for Business Server, you must use an account that is a member of the **Domain Admins** group and the **RTCUniversalServerAdmins** group, and that has full control permissions (read, write, and modify) on the file store that you are going to use for the Persistent Chat Server file store (so that Topology Builder can configure the required DACLs), or an account with equivalent rights.</span></span>
  
2. <span data-ttu-id="24726-118">トポロジビルダーを起動します。</span><span class="sxs-lookup"><span data-stu-id="24726-118">Start Topology Builder.</span></span>
    
3. <span data-ttu-id="24726-119">コンソールツリーで、[**常設チャットプール**] ノードに移動し、それを展開して Skype For business Server プールを選択するか、ノードを右クリックして [**新しい常設チャットプール**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="24726-119">In the console tree, navigate to the **Persistent Chat Pools** node and expand it to select a Skype for Business Server pool, or right-click the node and select **New Persistent Chat Pool**.</span></span> <span data-ttu-id="24726-120">プールの完全修飾ドメイン名 (FQDN) を定義し、プールを単一サーバープールにするか、複数サーバープール展開にするかを指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="24726-120">You must define the pool's fully qualified domain name (FQDN), and indicate whether the pool will be a single-server pool or multiple-server pool deployment.</span></span>
    
    <span data-ttu-id="24726-121">**複数のコンピュータープール**または**1 台のコンピュータープール**を選ぶことができます。</span><span class="sxs-lookup"><span data-stu-id="24726-121">You can choose a **Multiple Computer Pool** or a **Single Computer Pool**.</span></span> <span data-ttu-id="24726-122">常設チャットサーバープールに複数のフロントエンドサーバーを使用する場合は、前者を選びます。</span><span class="sxs-lookup"><span data-stu-id="24726-122">Choose the former if you are planning to have more than one Front End Server in your Persistent Chat Server pool.</span></span> <span data-ttu-id="24726-123">このオプションは、1台のコンピュータープールを作成した後で、後で追加することはできないため、ここで設定します。</span><span class="sxs-lookup"><span data-stu-id="24726-123">Make this choice now, or at a later point, because after you create a single computer pool, you cannot add additional servers to it later.</span></span> <span data-ttu-id="24726-124">複数のコンピュータープールを選択する場合は、プールを構成する個々のフロントエンドサーバーの名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="24726-124">If you choose a multiple computer pool, enter the names of the individual Front End Servers that comprise the pool.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="24726-125">標準エディションのサーバーに常設チャットサーバーの役割がインストールされている場合、FQDN は Standard Edition サーバーの FQDN と一致する必要があります。</span><span class="sxs-lookup"><span data-stu-id="24726-125">If the Persistent Chat Server role is being installed on a Standard Edition server, the FQDN needs to match the FQDN of the Standard Edition server.</span></span> 
  
4. <span data-ttu-id="24726-126">常設チャットサーバープールの簡易**表示名**を定義します。</span><span class="sxs-lookup"><span data-stu-id="24726-126">Define a simple **Display Name** for the Persistent Chat Server pool.</span></span> <span data-ttu-id="24726-127">表示名は、カスタムクライアントによって使用される場合があります。特に、会議室を区別するための常設チャットサーバープールが複数存在する場合に便利です。</span><span class="sxs-lookup"><span data-stu-id="24726-127">The display name can be used by custom clients, particularly when there are multiple Persistent Chat Server pools to differentiate rooms.</span></span>
    
5. <span data-ttu-id="24726-128">常設チャットサーバーが Skype for Business Server フロントエンドサーバーと通信するために使用するポートを定義します。</span><span class="sxs-lookup"><span data-stu-id="24726-128">Define the port used by the Persistent Chat Server to communicate with Skype for Business Server Front End Servers.</span></span> <span data-ttu-id="24726-129">既定のポートは 5041 です。</span><span class="sxs-lookup"><span data-stu-id="24726-129">The default port is 5041.</span></span>
    
6. <span data-ttu-id="24726-130">組織にコンプライアンス サポートが必要な場合は、[**コンプライアンスを有効にする**] チェック ボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="24726-130">If your organization requires compliance support, select the **Enable compliance** check box.</span></span> <span data-ttu-id="24726-131">選択されている場合、常設チャット Server コンプライアンスサービスは、常設チャットサーバーフロントエンドサーバーと同じコンピューターにインストールされます。</span><span class="sxs-lookup"><span data-stu-id="24726-131">If chosen, the Persistent Chat Server Compliance service is installed on the same computer as the Persistent Chat Server Front End Server.</span></span> <span data-ttu-id="24726-132">後で常設チャットサーバーのコンプライアンス用の SQL Server バックエンドサーバーを選択するように求められます。</span><span class="sxs-lookup"><span data-stu-id="24726-132">You are prompted to select a SQL Server Back End Server for Persistent Chat Server Compliance later.</span></span>
    
7. <span data-ttu-id="24726-133">常設チャットサーバープールにサイトのアフィニティを割り当てます。</span><span class="sxs-lookup"><span data-stu-id="24726-133">Assign site affinity for the Persistent Chat Server pool.</span></span> <span data-ttu-id="24726-134">この [**このプールをサイトの\<サイト\> **の既定のプールとして使用する] チェックボックスをオンにするか、またはすべてのサイトの既定のプールとしてこのプールを**使用**します。</span><span class="sxs-lookup"><span data-stu-id="24726-134">Select the **Use this pool as default for site \<SiteName\>** check box or **Use this pool as default for all sites** to designate this Persistent Chat Server pool as the default pool for the current site or all sites.</span></span> <span data-ttu-id="24726-135">Skype for Business クライアントを使用して会議室の作成と管理を行う場合、ユーザーのサイトに関連付けられた既定のプールは、ルームの作成と管理のエクスペリエンスによって使用され、ルームの作成と管理の操作をそのプールにルーティングすることができます。</span><span class="sxs-lookup"><span data-stu-id="24726-135">When the Skype for Business client is used to create and manage rooms, the default pool associated with the user's site is used by the room creation and management experience so that it can route room creation and management operations to that pool.</span></span> <span data-ttu-id="24726-136">これは、複数の常設チャットサーバープールが展開されており、常設チャットサーバーのルーム作成と管理機能を使用する場合にのみ適用されます。</span><span class="sxs-lookup"><span data-stu-id="24726-136">This only applies when you have multiple Persistent Chat Server pools deployed, and want to use the room creation and management features of Persistent Chat Server.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="24726-137">常設チャットサーバーソフトウェア開発キット (SDK) を使って、ルームの作成と管理の機能をカスタマイズできます。</span><span class="sxs-lookup"><span data-stu-id="24726-137">You can customize the room creation and management features using the Persistent Chat Server Software Development Kit (SDK).</span></span> 
  
8. <span data-ttu-id="24726-138">次のいずれかの操作を行って、**常設チャットサーバーのバックエンド用の SQL ストア (チャットルームのコンテンツが保存されている場所) を**定義します。</span><span class="sxs-lookup"><span data-stu-id="24726-138">Define the **SQL store for the Persistent Chat Server Back End (where chat room content is stored)** by doing one of the following:</span></span>
    
   - <span data-ttu-id="24726-139">既存の SQL Server ストアを使用するには、ドロップダウンリストで、使用する SQL Server ストアの名前をクリックします。</span><span class="sxs-lookup"><span data-stu-id="24726-139">To use an existing SQL Server store, in the drop-down list, click the name of the SQL Server store that you want to use.</span></span>
    
   - <span data-ttu-id="24726-140">新しい SQL Server データベースを指定するには、[**新規**作成] をクリックし、[**新しい Sql ストアの定義**] で次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="24726-140">To specify a new SQL Server database, click **New**, and in **Define New SQL Store**, perform the following:</span></span>
    
   - <span data-ttu-id="24726-141">[ **Sql SERVER fqdn**] で、新しい sql server データベースを作成する sql SERVER の fqdn を指定します。</span><span class="sxs-lookup"><span data-stu-id="24726-141">In **SQL Server FQDN**, specify the FQDN of the SQL Server on which you want to create the new SQL Server database.</span></span>
    
   - <span data-ttu-id="24726-142">[**既定のインスタンス**] を選択して既定のインスタンスを使用するか、別のインスタンスを指定する場合は、[**名前付きインスタンス**] を選択して、使用するインスタンスを指定します。</span><span class="sxs-lookup"><span data-stu-id="24726-142">Either select **Default Instance** to use the default instance or, to specify a different instance, select **Named Instance**, and specify the instance that you want to use.</span></span>
    
     > [!NOTE]
     > <span data-ttu-id="24726-143">災害復旧のために SQL Server バックアップデータベースを構成する方法の詳細については、「 [Skype For Business server 2015 の常設チャットサーバーの高可用性と障害回復を構成](../../deploy/deploy-high-availability-and-disaster-recovery/configure-hadr-for-persistent-chat.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="24726-143">For details about how to configure SQL Server backup databases for disaster recovery, see [Configure high availability and disaster recovery for Persistent Chat Server in Skype for Business Server 2015](../../deploy/deploy-high-availability-and-disaster-recovery/configure-hadr-for-persistent-chat.md).</span></span> 
  
9. <span data-ttu-id="24726-144">コンプライアンスを有効にしている場合は、SQL Server コンプライアンスストアを定義します。</span><span class="sxs-lookup"><span data-stu-id="24726-144">Define the SQL Server compliance store if you enabled Compliance.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="24726-145">常設チャットサーバーデータベースと常設チャットサーバーのコンプライアンスデータベースに対して高可用性のための SQL Server ミラーを構成する方法の詳細については、「 [Skype の常設チャットサーバーの高可用性と障害回復を構成する」を参照してください。Business Server 2015 の場合](../../deploy/deploy-high-availability-and-disaster-recovery/configure-hadr-for-persistent-chat.md)。</span><span class="sxs-lookup"><span data-stu-id="24726-145">For details about how to configure SQL Server mirrors for high availability for the Persistent Chat Server database and the Persistent Chat Server compliance database, see [Configure high availability and disaster recovery for Persistent Chat Server in Skype for Business Server 2015](../../deploy/deploy-high-availability-and-disaster-recovery/configure-hadr-for-persistent-chat.md).</span></span> 
  
10. <span data-ttu-id="24726-146">ファイルストアを定義します。</span><span class="sxs-lookup"><span data-stu-id="24726-146">Define the file store.</span></span> <span data-ttu-id="24726-147">ファイルストアは、ファイルリポジトリにアップロードされたファイルのコピーが格納されているフォルダーです (たとえば、チャットルームに投稿された添付ファイルを保存します)。</span><span class="sxs-lookup"><span data-stu-id="24726-147">A file store is a folder where a copy of any file uploaded to the file repository is stored (for example, storing file attachments posted to a chat room).</span></span> <span data-ttu-id="24726-148">複数サーバーの常設チャットサーバートポロジの場合、これは汎用名前付け規則 (UNC) パスである必要があります。また、単一サーバーの常設チャットサーバートポロジでは、ローカルファイルパスにすることができます。</span><span class="sxs-lookup"><span data-stu-id="24726-148">In the case of a multiple-server Persistent Chat Server topology, this must be a Universal Naming Convention (UNC) path; and for a single-server Persistent Chat Server topology, it can be a local file path.</span></span>
    
    <span data-ttu-id="24726-149">既存のファイル ストアを使用するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="24726-149">To use an existing file store, perform the following steps:</span></span>
    
    - <span data-ttu-id="24726-150">[**ファイル サーバーの FQDN**] で、新しいファイル ストアを作成するコンピューターの FQDN を指定します。</span><span class="sxs-lookup"><span data-stu-id="24726-150">In **File Server FQDN**, specify the FQDN of the machine on which you want to create the new file store.</span></span>
    
    - <span data-ttu-id="24726-151">[**ファイル共有**] で、使用するファイル ストアを指定します。</span><span class="sxs-lookup"><span data-stu-id="24726-151">In **File Share**, specify the file store that you want to use.</span></span>
    
      > [!IMPORTANT]
      > <span data-ttu-id="24726-152">ファイルストアを作成する前に、トポロジビルダーでファイルストアを定義できますが、トポロジを公開する前に定義した定義された場所にファイルストアを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="24726-152">You can define the file store in Topology Builder before you create the file store, but you must create the file store in the defined location you define before you publish the topology.</span></span> <span data-ttu-id="24726-153">ファイル ストアがまだ存在していない場合、トポロジを公開しようとすると失敗します。</span><span class="sxs-lookup"><span data-stu-id="24726-153">If the file store doesn't already exist, attempts to publish the topology will fail.</span></span> 
  
11. <span data-ttu-id="24726-154">この常設チャットサーバープールの次ホップとして使用するフロントエンドサーバープールを選択します。</span><span class="sxs-lookup"><span data-stu-id="24726-154">Select the Front End Server pool to be used as a next hop for this Persistent Chat Server pool.</span></span> <span data-ttu-id="24726-155">これは、このプールへの常設チャットサーバー要求をルーティングできるフロントエンドサーバープールです。</span><span class="sxs-lookup"><span data-stu-id="24726-155">This is the Front End Server pool that will be able to route Persistent Chat Server requests to this pool.</span></span>
    
12. <span data-ttu-id="24726-156">構成を保存するには、[**完了**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="24726-156">To save the configuration, click **Finish**.</span></span> <span data-ttu-id="24726-157">常設チャットサーバープールは、特定のプール設定と共に、トポロジビルダーに表示されます。</span><span class="sxs-lookup"><span data-stu-id="24726-157">The Persistent Chat Server pool appears in Topology Builder accompanied by your specific pool settings.</span></span>
    
    <span data-ttu-id="24726-158">常設チャットサーバーを追加した、更新されたトポロジを公開するには、「更新されたトポロジを公開する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="24726-158">To publish your updated topology to which you've added Persistent Chat Server, see Publish the updated topology.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="24726-159">トポロジビルダーを既に開いている場合は、「更新されたトポロジを公開する」の手順3に進んで、更新されたトポロジの公開を開始します。</span><span class="sxs-lookup"><span data-stu-id="24726-159">With Topology Builder already open, you can proceed to step 3 in Publish the updated topology to begin publishing your updated topology.</span></span> 
  
## <a name="publish-the-updated-topology"></a><span data-ttu-id="24726-160">更新されたトポロジを公開する</span><span class="sxs-lookup"><span data-stu-id="24726-160">Publish the updated topology</span></span>
<span data-ttu-id="24726-161"><a name="BKMK_PublishTopology"> </a></span><span class="sxs-lookup"><span data-stu-id="24726-161"></span></span>

<span data-ttu-id="24726-162">トポロジビルダーでトポロジを更新した後、Skype for Business Server を構成して使用するには、トポロジを中央管理ストアに発行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="24726-162">After updating your topology in Topology Builder, you must publish the topology to the Central Management store before you can configure and use Skype for Business Server.</span></span> <span data-ttu-id="24726-163">このデータの読み取り専用コピーはトポロジ内のすべてのサーバーにレプリケートされ、すべてのサーバーは、トポロジおよび他の構成の変更と同期された状態で維持されます。</span><span class="sxs-lookup"><span data-stu-id="24726-163">Read-only copies of the data are replicated to all servers in the topology to keep all servers in sync with topology and other configuration changes.</span></span>
  
<span data-ttu-id="24726-164">トポロジを公開する前に、常設チャットサーバー用のデータベースをインストールします。</span><span class="sxs-lookup"><span data-stu-id="24726-164">Before you publish your topology, install the databases for Persistent Chat Server.</span></span> <span data-ttu-id="24726-165">[**アクション**]、[**データベースのインストール**] の順に選択して、トポロジビルダーを使用してデータベースをインストールします。</span><span class="sxs-lookup"><span data-stu-id="24726-165">Use Topology Builder to install databases by selecting **Action** and **Install Database**.</span></span>
  
1. <span data-ttu-id="24726-166">Skype for Business Server を実行しているコンピューター、または Skype for Business Server 管理ツールがインストールされているコンピューターの場合は、 **Domain Admins**グループと**RTCUniversalServerAdmins**グループの両方のメンバーであるアカウントを使用してログオンします。また、これには、常設チャットサーバーファイルストア (Topology Builder が必要な随意アクセス制御リスト (Dacl)) または同等のユーザーのアカウントを構成できるように、ファイルストアに対するフルコントロールのアクセス許可 (読み取り、書き込み、変更) が含まれています。rights.</span><span class="sxs-lookup"><span data-stu-id="24726-166">On a computer that is running Skype for Business Server or on which the Skype for Business Server administrative tools are installed, log on using an account that is a member of both the **Domain Admins** group and the **RTCUniversalServerAdmins** group, and that has full control permissions (read, write, and modify) on the file store to be used for the Persistent Chat Server file store (so that Topology Builder can configure the required discretionary access control lists (DACLs)), or an account with equivalent user rights.</span></span>
    
2. <span data-ttu-id="24726-167">トポロジビルダーを起動します。</span><span class="sxs-lookup"><span data-stu-id="24726-167">Start Topology Builder.</span></span> <span data-ttu-id="24726-168">トポロジがローカルに保存されている場合は、[**ローカル ファイルからトポロジを開く**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="24726-168">Select **Open Topology from a local file** if you saved it locally.</span></span>
    
3. <span data-ttu-id="24726-169">コンソールツリーで、[ **Skype For Business Server 2015**] を右クリックし、[**トポロジの公開**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="24726-169">In the console tree, right-click **Skype for Business Server 2015**, and then click **Publish Topology**.</span></span>
    
4. <span data-ttu-id="24726-170">[**トポロジの公開**] ページで、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="24726-170">On the **Publish the topology** page, click **Next**.</span></span>
    
5. <span data-ttu-id="24726-171">[**公開ウィザードの完了**] ページで、トポロジが正常に公開されたことを確認し、[**完了**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="24726-171">On the **Publishing wizard complete** page, verify that the topology was successfully published, and then click **Finish**.</span></span>
    

