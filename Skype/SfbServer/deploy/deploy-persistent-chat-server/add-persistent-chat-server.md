---
title: ビジネス サーバー 2015 トポロジの場合、Skype に永続的なチャット サーバーを追加します。
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 6b4f4d69-3c9d-4bc7-bc9b-46427a095de2
description: '概要: ビジネス サーバー 2015 トポロジの場合、Skype に永続的なチャット サーバーを追加する方法の詳細については、このトピックを読みます。'
ms.openlocfilehash: 16c886e13ff56d0aa059ec676d152d332d0023db
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "32225789"
---
# <a name="add-persistent-chat-server-to-your-skype-for-business-server-2015-topology"></a><span data-ttu-id="f04a6-103">ビジネス サーバー 2015 トポロジの場合、Skype に永続的なチャット サーバーを追加します。</span><span class="sxs-lookup"><span data-stu-id="f04a6-103">Add Persistent Chat Server to your Skype for Business Server 2015 topology</span></span>
 
<span data-ttu-id="f04a6-104">**の概要:** ビジネス サーバー 2015 トポロジの場合、Skype に永続的なチャット サーバーを追加する方法の詳細については、このトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="f04a6-104">**Summary:** Read this topic to learn how to add Persistent Chat Server to your Skype for Business Server 2015 topology.</span></span>
  
<span data-ttu-id="f04a6-105">永続的なチャット サーバーを展開する予定の各サーバーの前提条件のソフトウェアをインストールした後、トポロジ ビルダーを使用します。</span><span class="sxs-lookup"><span data-stu-id="f04a6-105">After you install the prerequisite software on each server on which you plan to deploy Persistent Chat Server, you use Topology Builder to:</span></span> 
  
- <span data-ttu-id="f04a6-106">トポロジを更新して常設チャット サーバーを含める</span><span class="sxs-lookup"><span data-stu-id="f04a6-106">Update your topology to include Persistent Chat Server</span></span>
    
- <span data-ttu-id="f04a6-107">更新されたトポロジを公開する</span><span class="sxs-lookup"><span data-stu-id="f04a6-107">Publish the updated topology</span></span>
    
> [!NOTE] 
> <span data-ttu-id="f04a6-108">永続的なチャットですがビジネス サーバー 2015 の Skype で利用可能なビジネス サーバー 2019 の Skype でサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="f04a6-108">Persistent chat is available in Skype for Business Server 2015 but is no longer supported in Skype for Business Server 2019.</span></span> <span data-ttu-id="f04a6-109">同じ機能は、チームで使用できます。</span><span class="sxs-lookup"><span data-stu-id="f04a6-109">The same functionality is available in Teams.</span></span> <span data-ttu-id="f04a6-110">詳細については、[マイクロソフトのチームにビジネス用の Skype からの旅](/microsoftteams/journey-skypeforbusiness-teams)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f04a6-110">For more information, see [Journey from Skype for Business to Microsoft Teams](/microsoftteams/journey-skypeforbusiness-teams).</span></span> <span data-ttu-id="f04a6-111">永続的なチャットを使用する場合は、選択肢は、いずれかをチームでは、この機能を必要とするユーザーを移行するまたはビジネス サーバー 2015 の Skype を使用し続ける。</span><span class="sxs-lookup"><span data-stu-id="f04a6-111">If you need to use Persistent chat, your choices are to either migrate users requiring this functionality to Teams, or to continue using Skype for Business Server 2015.</span></span> 

## <a name="update-your-topology-to-include-persistent-chat-server"></a><span data-ttu-id="f04a6-112">トポロジを更新して常設チャット サーバーを含める</span><span class="sxs-lookup"><span data-stu-id="f04a6-112">Update your topology to include Persistent Chat Server</span></span>

<span data-ttu-id="f04a6-113">災害復旧構成のない 1 つの永続的なチャット サーバー プールをインストールするためには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="f04a6-113">Perform the following steps for installing a single Persistent Chat Server pool without a disaster recovery configuration.</span></span> <span data-ttu-id="f04a6-114">高可用性と災害復旧の拡大された永続的なチャット サーバー プールを構成するには、[構成の高可用性とビジネス サーバー 2015 の Skype での永続的なチャット サーバーの障害回復](../../deploy/deploy-high-availability-and-disaster-recovery/configure-hadr-for-persistent-chat.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f04a6-114">For configuring a stretched Persistent Chat Server pool for high availability and disaster recovery, see [Configure high availability and disaster recovery for Persistent Chat Server in Skype for Business Server 2015](../../deploy/deploy-high-availability-and-disaster-recovery/configure-hadr-for-persistent-chat.md).</span></span>
  
<span data-ttu-id="f04a6-115">複数の永続的なチャット サーバー プールを展開するには、プールごとに同じ処理を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="f04a6-115">To deploy multiple Persistent Chat Server pools, repeat the same process for each pool.</span></span>
  
1. <span data-ttu-id="f04a6-116">ビジネス サーバーの Skype を実行しているコンピューター上に、Skype ビジネス サーバー管理ツールをインストールするにログオンまたはローカルの Users グループ (または同等のユーザー権限を持つアカウント) のメンバーであるアカウントを使用しています。</span><span class="sxs-lookup"><span data-stu-id="f04a6-116">On a computer that is running Skype for Business Server or on which the Skype for Business Server administrative tools are installed, log on using an account that is a member of the local Users group (or an account with equivalent user rights).</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="f04a6-117">ローカルの Users グループのメンバーであるアカウントを使用してトポロジを定義することができますが、トポロジでは、Skype をビジネスのサーバーのインストールに必要なを公開するには、 **Domain Admins**グループと、**のメンバーであるアカウントを使用する必要があります。RTCUniversalServerAdmins**グループがフル コントロールのアクセス許可 (読み取り、書き込み、および変更)、ファイル ストアの永続的なチャット サーバー ファイル ストア (つまり、そのトポロジ ビルダーでは、必要な Dacl を設定できます) を使用しているのかを持つアカウント同等の権利です。</span><span class="sxs-lookup"><span data-stu-id="f04a6-117">You can define a topology by using an account that is a member of the local Users group, but to publish a topology, which is required to install Skype for Business Server, you must use an account that is a member of the **Domain Admins** group and the **RTCUniversalServerAdmins** group, and that has full control permissions (read, write, and modify) on the file store that you are going to use for the Persistent Chat Server file store (so that Topology Builder can configure the required DACLs), or an account with equivalent rights.</span></span>
  
2. <span data-ttu-id="f04a6-118">トポロジ ビルダーを起動します。</span><span class="sxs-lookup"><span data-stu-id="f04a6-118">Start Topology Builder.</span></span>
    
3. <span data-ttu-id="f04a6-119">コンソール ツリーで、**永続的なチャット プール**] ノードに移動し、Skype ビジネス サーバー プールを選択またはノードを右クリックし、**新しい永続的なチャットのプール**を選択して展開します。</span><span class="sxs-lookup"><span data-stu-id="f04a6-119">In the console tree, navigate to the **Persistent Chat Pools** node and expand it to select a Skype for Business Server pool, or right-click the node and select **New Persistent Chat Pool**.</span></span> <span data-ttu-id="f04a6-120">プールの完全修飾ドメイン名 (FQDN) を定義し、プールが 1 台のサーバー プールまたは複数のサーバー プールの展開になるかどうかを示す必要があります。</span><span class="sxs-lookup"><span data-stu-id="f04a6-120">You must define the pool's fully qualified domain name (FQDN), and indicate whether the pool will be a single-server pool or multiple-server pool deployment.</span></span>
    
    <span data-ttu-id="f04a6-121">**複数コンピューターのプール**または**単一コンピューターのプール**を選択します。</span><span class="sxs-lookup"><span data-stu-id="f04a6-121">You can choose a **Multiple Computer Pool** or a **Single Computer Pool**.</span></span> <span data-ttu-id="f04a6-122">永続的なチャット サーバー プールに複数のフロント エンド サーバーを計画している場合は、前者を選択します。</span><span class="sxs-lookup"><span data-stu-id="f04a6-122">Choose the former if you are planning to have more than one Front End Server in your Persistent Chat Server pool.</span></span> <span data-ttu-id="f04a6-123">1 台のコンピューターのプールを作成したら、追加できないため、追加のサーバーに後で今すぐ、または後で、この選択を確認します。</span><span class="sxs-lookup"><span data-stu-id="f04a6-123">Make this choice now, or at a later point, because after you create a single computer pool, you cannot add additional servers to it later.</span></span> <span data-ttu-id="f04a6-124">複数コンピューターのプールを選択する場合は、プールを構成する個々 のフロント エンド サーバーの名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="f04a6-124">If you choose a multiple computer pool, enter the names of the individual Front End Servers that comprise the pool.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="f04a6-125">永続的なチャット サーバーの役割がインストールする場合、Standard Edition サーバーで、FQDN は、Standard Edition サーバーの FQDN と一致する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f04a6-125">If the Persistent Chat Server role is being installed on a Standard Edition server, the FQDN needs to match the FQDN of the Standard Edition server.</span></span> 
  
4. <span data-ttu-id="f04a6-126">永続的なチャット サーバー プールの簡易**表示名**を定義します。</span><span class="sxs-lookup"><span data-stu-id="f04a6-126">Define a simple **Display Name** for the Persistent Chat Server pool.</span></span> <span data-ttu-id="f04a6-127">部屋を区別するために複数の永続的なチャット サーバー プールが存在する場合に特に、カスタムのクライアントで表示名を使用できます。</span><span class="sxs-lookup"><span data-stu-id="f04a6-127">The display name can be used by custom clients, particularly when there are multiple Persistent Chat Server pools to differentiate rooms.</span></span>
    
5. <span data-ttu-id="f04a6-128">ビジネス サーバーのフロント エンド サーバーの Skype で通信するために永続的なチャット サーバーが使用するポートを定義します。</span><span class="sxs-lookup"><span data-stu-id="f04a6-128">Define the port used by the Persistent Chat Server to communicate with Skype for Business Server Front End Servers.</span></span> <span data-ttu-id="f04a6-129">既定のポートは 5041 です。</span><span class="sxs-lookup"><span data-stu-id="f04a6-129">The default port is 5041.</span></span>
    
6. <span data-ttu-id="f04a6-130">組織にコンプライアンス サポートが必要な場合は、[**コンプライアンスを有効にする**] チェック ボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="f04a6-130">If your organization requires compliance support, select the **Enable compliance** check box.</span></span> <span data-ttu-id="f04a6-131">このオプションを選択すると、永続的なチャット サーバーのコンプライアンス サービスは、永続的なチャット サーバー フロント エンド サーバーと同じコンピューターにインストールされます。</span><span class="sxs-lookup"><span data-stu-id="f04a6-131">If chosen, the Persistent Chat Server Compliance service is installed on the same computer as the Persistent Chat Server Front End Server.</span></span> <span data-ttu-id="f04a6-132">後で永続的なチャット サーバーのコンプライアンスのため、SQL Server バック エンド サーバーを選択するように求められます。</span><span class="sxs-lookup"><span data-stu-id="f04a6-132">You are prompted to select a SQL Server Back End Server for Persistent Chat Server Compliance later.</span></span>
    
7. <span data-ttu-id="f04a6-133">サイトの関係を永続的なチャット サーバー プールを割り当てます。</span><span class="sxs-lookup"><span data-stu-id="f04a6-133">Assign site affinity for the Persistent Chat Server pool.</span></span> <span data-ttu-id="f04a6-134">選択して、**サイトの既定値としてこのプールを使用して\<サイト名\>**] チェック ボックスまたは**すべてのサイトの既定値としては、このプールを使用して**現在のサイトまたはすべてのサイトの既定のプールとして、この永続的なチャット サーバー プールを指定するします。</span><span class="sxs-lookup"><span data-stu-id="f04a6-134">Select the **Use this pool as default for site \<SiteName\>** check box or **Use this pool as default for all sites** to designate this Persistent Chat Server pool as the default pool for the current site or all sites.</span></span> <span data-ttu-id="f04a6-135">ビジネス クライアント用の Skype を使用するを作成し、会議室を管理すると、ルームの作成と管理の経験によって、ルームの作成および管理の操作をそのプールにルーティングできるように、ユーザーのサイトに関連付けられている既定のプールが使用されます。</span><span class="sxs-lookup"><span data-stu-id="f04a6-135">When the Skype for Business client is used to create and manage rooms, the default pool associated with the user's site is used by the room creation and management experience so that it can route room creation and management operations to that pool.</span></span> <span data-ttu-id="f04a6-136">のみ、この問題は、展開されると、複数の永続的なチャット サーバー プールが存在し、永続的なチャット サーバーの部屋の作成と管理機能を使用するときに適用されます。</span><span class="sxs-lookup"><span data-stu-id="f04a6-136">This only applies when you have multiple Persistent Chat Server pools deployed, and want to use the room creation and management features of Persistent Chat Server.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="f04a6-137">永続的なチャット サーバー ソフトウェア開発キット (SDK) を使用して、ルームの作成と管理機能をカスタマイズすることができます。</span><span class="sxs-lookup"><span data-stu-id="f04a6-137">You can customize the room creation and management features using the Persistent Chat Server Software Development Kit (SDK).</span></span> 
  
8. <span data-ttu-id="f04a6-138">次のいずれかの方法で**SQL に永続的なチャット サーバー バックエンド (チャット ルームの内容が保存されている) の格納**を定義します。</span><span class="sxs-lookup"><span data-stu-id="f04a6-138">Define the **SQL store for the Persistent Chat Server Back End (where chat room content is stored)** by doing one of the following:</span></span>
    
   - <span data-ttu-id="f04a6-139">ボックスの一覧で、既存の SQL Server ストアを使用するには、使用する SQL Server のストアの名前をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f04a6-139">To use an existing SQL Server store, in the drop-down list, click the name of the SQL Server store that you want to use.</span></span>
    
   - <span data-ttu-id="f04a6-140">新しい SQL Server データベースを指定するには、[**新規**作成] をクリックし、 **[新しい SQL ストアの定義**では、次の。</span><span class="sxs-lookup"><span data-stu-id="f04a6-140">To specify a new SQL Server database, click **New**, and in **Define New SQL Store**, perform the following:</span></span>
    
   - <span data-ttu-id="f04a6-141">**SQL Server の FQDN**を新しい SQL Server データベースを作成する SQL Server の FQDN を指定します。</span><span class="sxs-lookup"><span data-stu-id="f04a6-141">In **SQL Server FQDN**, specify the FQDN of the SQL Server on which you want to create the new SQL Server database.</span></span>
    
   - <span data-ttu-id="f04a6-142">[**既定のインスタンス**] を選択して既定のインスタンスを使用するか、別のインスタンスを指定する場合は、[**名前付きインスタンス**] を選択して、使用するインスタンスを指定します。</span><span class="sxs-lookup"><span data-stu-id="f04a6-142">Either select **Default Instance** to use the default instance or, to specify a different instance, select **Named Instance**, and specify the instance that you want to use.</span></span>
    
     > [!NOTE]
     > <span data-ttu-id="f04a6-143">災害復旧用バックアップ ・ データベースを SQL Server を構成する方法の詳細については、[構成の高可用性とビジネス サーバー 2015 の Skype での永続的なチャット サーバーの障害回復](../../deploy/deploy-high-availability-and-disaster-recovery/configure-hadr-for-persistent-chat.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f04a6-143">For details about how to configure SQL Server backup databases for disaster recovery, see [Configure high availability and disaster recovery for Persistent Chat Server in Skype for Business Server 2015](../../deploy/deploy-high-availability-and-disaster-recovery/configure-hadr-for-persistent-chat.md).</span></span> 
  
9. <span data-ttu-id="f04a6-144">コンプライアンスを有効にした場合は、SQL Server の準拠のストアを定義します。</span><span class="sxs-lookup"><span data-stu-id="f04a6-144">Define the SQL Server compliance store if you enabled Compliance.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="f04a6-145">永続的なチャット サーバーのデータベースおよび永続的なチャット サーバー コンプライアンス データベースの高可用性の SQL Server のミラーを構成する方法の詳細については、Skype での永続的なチャット サーバーの[構成の高可用性および災害復旧を参照します。ビジネス サーバー 2015 の](../../deploy/deploy-high-availability-and-disaster-recovery/configure-hadr-for-persistent-chat.md)です。</span><span class="sxs-lookup"><span data-stu-id="f04a6-145">For details about how to configure SQL Server mirrors for high availability for the Persistent Chat Server database and the Persistent Chat Server compliance database, see [Configure high availability and disaster recovery for Persistent Chat Server in Skype for Business Server 2015](../../deploy/deploy-high-availability-and-disaster-recovery/configure-hadr-for-persistent-chat.md).</span></span> 
  
10. <span data-ttu-id="f04a6-146">ファイル ストアを定義します。</span><span class="sxs-lookup"><span data-stu-id="f04a6-146">Define the file store.</span></span> <span data-ttu-id="f04a6-147">ファイル ストアは、フォルダー (たとえば、チャット ルームに投稿されたファイルの添付ファイルを保存する) ファイルのリポジトリにアップロードされたファイルのコピーを保存する場所です。</span><span class="sxs-lookup"><span data-stu-id="f04a6-147">A file store is a folder where a copy of any file uploaded to the file repository is stored (for example, storing file attachments posted to a chat room).</span></span> <span data-ttu-id="f04a6-148">場合は永続的なチャット サーバーの複数サーバー トポロジでは、これを汎用名前付け規則 (UNC) パスにする必要があります。永続的なチャット サーバーの 1 台のサーバー トポロジでは、ローカル ファイル パスであることができます。</span><span class="sxs-lookup"><span data-stu-id="f04a6-148">In the case of a multiple-server Persistent Chat Server topology, this must be a Universal Naming Convention (UNC) path; and for a single-server Persistent Chat Server topology, it can be a local file path.</span></span>
    
    <span data-ttu-id="f04a6-149">既存のファイル ストアを使用するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="f04a6-149">To use an existing file store, perform the following steps:</span></span>
    
    - <span data-ttu-id="f04a6-150">[**ファイル サーバーの FQDN**] で、新しいファイル ストアを作成するコンピューターの FQDN を指定します。</span><span class="sxs-lookup"><span data-stu-id="f04a6-150">In **File Server FQDN**, specify the FQDN of the machine on which you want to create the new file store.</span></span>
    
    - <span data-ttu-id="f04a6-151">[**ファイル共有**] で、使用するファイル ストアを指定します。</span><span class="sxs-lookup"><span data-stu-id="f04a6-151">In **File Share**, specify the file store that you want to use.</span></span>
    
      > [!IMPORTANT]
      > <span data-ttu-id="f04a6-152">トポロジ ビルダーのファイル ストアを定義するには、ファイル ストアを作成する前にトポロジを公開する前に定義する定義済みの場所にファイル ストアを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f04a6-152">You can define the file store in Topology Builder before you create the file store, but you must create the file store in the defined location you define before you publish the topology.</span></span> <span data-ttu-id="f04a6-153">ファイル ストアがまだ存在していない場合、トポロジを公開しようとすると失敗します。</span><span class="sxs-lookup"><span data-stu-id="f04a6-153">If the file store doesn't already exist, attempts to publish the topology will fail.</span></span> 
  
11. <span data-ttu-id="f04a6-154">この永続的なチャット サーバー プールの次ホップとして使用するフロント エンド サーバー プールを選択します。</span><span class="sxs-lookup"><span data-stu-id="f04a6-154">Select the Front End Server pool to be used as a next hop for this Persistent Chat Server pool.</span></span> <span data-ttu-id="f04a6-155">これは、このプールに永続的なチャット サーバー要求をルーティングするようになりますがフロント エンド サーバー プールです。</span><span class="sxs-lookup"><span data-stu-id="f04a6-155">This is the Front End Server pool that will be able to route Persistent Chat Server requests to this pool.</span></span>
    
12. <span data-ttu-id="f04a6-156">構成を保存するには、[**完了**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f04a6-156">To save the configuration, click **Finish**.</span></span> <span data-ttu-id="f04a6-157">永続的なチャット サーバー プールは、特定のプールの設定、トポロジ ビルダーで表示されます。</span><span class="sxs-lookup"><span data-stu-id="f04a6-157">The Persistent Chat Server pool appears in Topology Builder accompanied by your specific pool settings.</span></span>
    
    <span data-ttu-id="f04a6-158">永続的なチャット サーバーを追加して更新したトポロジを公開するには、発行、更新したトポロジを参照してください。</span><span class="sxs-lookup"><span data-stu-id="f04a6-158">To publish your updated topology to which you've added Persistent Chat Server, see Publish the updated topology.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="f04a6-159">トポロジ ビルダーが既に開いていると進むことができます発行のステップ 3 に更新したトポロジを更新したトポロジを公開を開始します。</span><span class="sxs-lookup"><span data-stu-id="f04a6-159">With Topology Builder already open, you can proceed to step 3 in Publish the updated topology to begin publishing your updated topology.</span></span> 
  
## <a name="publish-the-updated-topology"></a><span data-ttu-id="f04a6-160">更新されたトポロジを公開する</span><span class="sxs-lookup"><span data-stu-id="f04a6-160">Publish the updated topology</span></span>
<span data-ttu-id="f04a6-161"><a name="BKMK_PublishTopology"> </a></span><span class="sxs-lookup"><span data-stu-id="f04a6-161"></span></span>

<span data-ttu-id="f04a6-162">トポロジ ビルダーでトポロジを更新した後、中央管理ストアにトポロジを公開してを構成し、ビジネスのサーバーに Skype を使用する前にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="f04a6-162">After updating your topology in Topology Builder, you must publish the topology to the Central Management store before you can configure and use Skype for Business Server.</span></span> <span data-ttu-id="f04a6-163">このデータの読み取り専用コピーはトポロジ内のすべてのサーバーにレプリケートされ、すべてのサーバーは、トポロジおよび他の構成の変更と同期された状態で維持されます。</span><span class="sxs-lookup"><span data-stu-id="f04a6-163">Read-only copies of the data are replicated to all servers in the topology to keep all servers in sync with topology and other configuration changes.</span></span>
  
<span data-ttu-id="f04a6-164">トポロジを公開する前に、永続的なチャット サーバーのデータベースをインストールします。</span><span class="sxs-lookup"><span data-stu-id="f04a6-164">Before you publish your topology, install the databases for Persistent Chat Server.</span></span> <span data-ttu-id="f04a6-165">**操作**と**データベースのインストール**を選択してデータベースをインストールするのにはトポロジ ビルダーを使用します。</span><span class="sxs-lookup"><span data-stu-id="f04a6-165">Use Topology Builder to install databases by selecting **Action** and **Install Database**.</span></span>
  
1. <span data-ttu-id="f04a6-166">ビジネス サーバーの Skype を実行しているコンピューター上に、Skype ビジネス サーバー管理ツールをインストールするにログオンまたは**Domain Admins**グループと、 **RTCUniversalServerAdmins**グループの両方のメンバーであるアカウントを使用して永続的なチャット サーバー ファイル ストア (つまり、そのトポロジ ビルダーでは、必要な随意アクセス制御リスト (Dacl) を構成することができます) に使用されるファイル ストアにフル コントロールのアクセス許可 (読み取り、書き込み、および変更) を持つ、または同等のユーザー アカウント権限がありません。</span><span class="sxs-lookup"><span data-stu-id="f04a6-166">On a computer that is running Skype for Business Server or on which the Skype for Business Server administrative tools are installed, log on using an account that is a member of both the **Domain Admins** group and the **RTCUniversalServerAdmins** group, and that has full control permissions (read, write, and modify) on the file store to be used for the Persistent Chat Server file store (so that Topology Builder can configure the required discretionary access control lists (DACLs)), or an account with equivalent user rights.</span></span>
    
2. <span data-ttu-id="f04a6-167">トポロジ ビルダーを起動します。</span><span class="sxs-lookup"><span data-stu-id="f04a6-167">Start Topology Builder.</span></span> <span data-ttu-id="f04a6-168">トポロジがローカルに保存されている場合は、[**ローカル ファイルからトポロジを開く**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="f04a6-168">Select **Open Topology from a local file** if you saved it locally.</span></span>
    
3. <span data-ttu-id="f04a6-169">コンソール ツリーは、**ビジネス サーバー 2015 の Skype**を右クリックし、 **[トポロジの公開**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f04a6-169">In the console tree, right-click **Skype for Business Server 2015**, and then click **Publish Topology**.</span></span>
    
4. <span data-ttu-id="f04a6-170">[**トポロジの公開**] ページで、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f04a6-170">On the **Publish the topology** page, click **Next**.</span></span>
    
5. <span data-ttu-id="f04a6-171">[**公開ウィザードの完了**] ページで、トポロジが正常に公開されたことを確認し、[**完了**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f04a6-171">On the **Publishing wizard complete** page, verify that the topology was successfully published, and then click **Finish**.</span></span>
    

