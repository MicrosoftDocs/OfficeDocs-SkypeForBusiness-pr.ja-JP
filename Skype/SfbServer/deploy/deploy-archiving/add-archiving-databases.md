---
title: Skype for Business Server の既存の展開にアーカイブ データベースを追加する
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
f1.keywords:
- NOCSH
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 3b67df85-181d-45ca-ba48-bb74a439f242
description: '概要: このトピックでは、Skype for Business Server 展開にアーカイブ データベースを追加する方法について説明します。'
ms.openlocfilehash: f7642cb79f73ab519938ddcb680f8450347b943d
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49820677"
---
# <a name="add-archiving-databases-to-an-existing-deployment-in-skype-for-business-server"></a><span data-ttu-id="e5da2-103">Skype for Business Server の既存の展開にアーカイブ データベースを追加する</span><span class="sxs-lookup"><span data-stu-id="e5da2-103">Add archiving databases to an existing deployment in Skype for Business Server</span></span>
 
<span data-ttu-id="e5da2-104">**概要:** このトピックでは、Skype for Business Server 展開にアーカイブ データベースを追加する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="e5da2-104">**Summary:** Read this topic to learn how to add archiving databases to your Skype for Business Server deployment.</span></span>
  
<span data-ttu-id="e5da2-105">アーカイブをサポートする展開を構成する前に、アーカイブをトポロジに組み込む必要があります。</span><span class="sxs-lookup"><span data-stu-id="e5da2-105">You must incorporate archiving into your topology before you can configure your deployment to support archiving.</span></span> <span data-ttu-id="e5da2-106">このトピックでは、トポロジ ビルダーを使用して次の方法を実行する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="e5da2-106">The information in this topic explains how to use Topology Builder to:</span></span>
  
- <span data-ttu-id="e5da2-107">アーカイブ データベースをトポロジに追加します。</span><span class="sxs-lookup"><span data-stu-id="e5da2-107">Add an archiving database to your topology.</span></span>
    
- <span data-ttu-id="e5da2-108">更新されたトポロジを公開して、アーカイブ データベースを Skype for Business Server 展開に追加します。</span><span class="sxs-lookup"><span data-stu-id="e5da2-108">Publish the updated topology to add the archiving database to your Skype for Business Server deployment.</span></span>
    
> [!NOTE]
> <span data-ttu-id="e5da2-109">Microsoft Exchange 統合を使用して、展開内のすべてのユーザーのアーカイブ データとファイルを Exchange サーバーに保存する場合は、アーカイブ **SQL Server** ストアまたは **SQL Server ストア** のミラーリング情報を使用するを指定しません。</span><span class="sxs-lookup"><span data-stu-id="e5da2-109">If you want to use Microsoft Exchange integration to store archiving data and files on Exchange servers for all your users in your deployment, do not specify **Archiving SQL Server store** or **Use SQL Server Store mirroring** information.</span></span>
  
### <a name="add-an-archiving-database-to-your-topology"></a><span data-ttu-id="e5da2-110">アーカイブ データベースをトポロジに追加する</span><span class="sxs-lookup"><span data-stu-id="e5da2-110">Add an archiving database to your topology</span></span>

1. <span data-ttu-id="e5da2-111">Skype for Business Server を実行しているコンピューター、または Skype for Business Server 管理ツールがインストールされているコンピューターで、ローカルの Users グループのメンバーであるアカウント (または同等のユーザー権限を持つアカウント) を使用してログオンします。</span><span class="sxs-lookup"><span data-stu-id="e5da2-111">On a computer that is running Skype for Business Server, or on which the Skype for Business Server administrative tools are installed, log on by using an account that is a member of the local Users group (or an account with equivalent user rights).</span></span>
    
2. <span data-ttu-id="e5da2-112">トポロジ ビルダーを開始します。</span><span class="sxs-lookup"><span data-stu-id="e5da2-112">Start Topology Builder.</span></span>
    
3. <span data-ttu-id="e5da2-113">コンソール ツリーで、アーカイブを展開するフロントエンド プールに移動し、アーカイブを展開するフロントエンド プールの名前をクリックします。</span><span class="sxs-lookup"><span data-stu-id="e5da2-113">In the console tree, navigate to the Front End pool in which you want to deploy Archiving, and then click the name of the Front End pool where you want to deploy archiving.</span></span>
    
4. <span data-ttu-id="e5da2-114">[**操作**] メニューの [**プロパティの編集**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="e5da2-114">In the **Action** menu, click **Edit Properties**.</span></span> 
    
5. <span data-ttu-id="e5da2-115">[**プロパティの編集**] ダイアログ ボックスで、[**全般**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="e5da2-115">In the **Edit Properties** dialog box, click **General**.</span></span>
    
6. <span data-ttu-id="e5da2-116">[**アーカイブ**] まで下方向にスクロールします。</span><span class="sxs-lookup"><span data-stu-id="e5da2-116">Scroll down to **Archiving**.</span></span>
    
7. <span data-ttu-id="e5da2-117">[アーカイブ **] チェック ボックスを** オンにします。</span><span class="sxs-lookup"><span data-stu-id="e5da2-117">Select the **Archiving** check box.</span></span>
    
8. <span data-ttu-id="e5da2-118">[ **アーカイブ SQL Server] で、次** のいずれかの操作を行います。</span><span class="sxs-lookup"><span data-stu-id="e5da2-118">Under **Archiving SQL Server store,** do one of the following:</span></span>
    
   - <span data-ttu-id="e5da2-119">既存の SQL Server ストアを使用するには、ドロップダウン リスト ボックスで、使用する SQL Server ストアの名前をクリックします。</span><span class="sxs-lookup"><span data-stu-id="e5da2-119">To use an existing SQL Server store, in the drop-down list box, click the name of the SQL Server store that you want to use.</span></span> <span data-ttu-id="e5da2-120">すべてのユーザーが Microsoft Exchange Server 2013 以上にホームを設定している場合は、Exchange のすべてのユーザーの Skype for Business 通信をアーカイブできます。</span><span class="sxs-lookup"><span data-stu-id="e5da2-120">If all of your users are homed on Microsoft Exchange Server 2013 or above, you can archive Skype for Business communications for all your users in Exchange.</span></span> <span data-ttu-id="e5da2-121">この場合、アーカイブ ストアを構成するSQL Server必要があります。</span><span class="sxs-lookup"><span data-stu-id="e5da2-121">In this case, you don't need to configure SQL Server Archiving store.</span></span>
    
   - <span data-ttu-id="e5da2-122">新しいストアをSQL Serverするには、[新規] をクリックし、[ストアの新しいSQL Server **定義**] ダイアログ ボックスで、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="e5da2-122">To specify a new SQL Server store, click **New**, and then in the **Define New SQL Server Store** dialog box, do the following:</span></span>
    
   - <span data-ttu-id="e5da2-123">[SQL SERVER **FQDN]** で、新しいドメイン ストアを作成するサーバーの FQDN SQL Serverします。</span><span class="sxs-lookup"><span data-stu-id="e5da2-123">In **SQL Server FQDN**, specify the FQDN of the server on which you want to create the new SQL Server store.</span></span>
    
   - <span data-ttu-id="e5da2-124">既定のインスタンスを使用するには [**既定のインスタンス**] をクリックし、別のインスタンスを指定するには [**名前付きインスタンス**] をクリックして、使用するインスタンスを指定します。</span><span class="sxs-lookup"><span data-stu-id="e5da2-124">Either click **Default Instance** to use the default instance, or, to specify a different instance, click **Named instance**, and then specify the instance you want to use.</span></span>
    
   - <span data-ttu-id="e5da2-125">指定した SQL Server インスタンスがミラーリング関係にある場合は、[This SQL **instance is in mirroring relation]** チェック ボックスをオンにし **、[Mirror port number]** でポート番号を指定します。</span><span class="sxs-lookup"><span data-stu-id="e5da2-125">If the specified SQL Server instance is in a mirroring relationship, select the **This SQL instance is in mirroring relation** check box, and then, in **Mirror port number**, specify the port number.</span></span>
    
9. <span data-ttu-id="e5da2-126">ストア ミラーリングを使用する場合SQL Serverストア ミラーリングを有効SQL Server **し**、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="e5da2-126">If you want to use SQL Server store mirroring, select **Enable SQL Server Store mirroring**, and then do the following:</span></span>
    
   - <span data-ttu-id="e5da2-127">既存の SQL Server ストアをミラーリングに使用するには、[アーカイブ **SQL Server** ストアのミラー] ドロップダウン リスト ボックスで、ミラーリングに使用する SQL Server ストアの名前をクリックします。</span><span class="sxs-lookup"><span data-stu-id="e5da2-127">To use an existing SQL Server store for mirroring, in the **Archiving SQL Server store mirror** drop-down list box, click the name of the SQL Server store that you want to use for mirroring.</span></span>
    
   - <span data-ttu-id="e5da2-128">ミラーリング用の新しい SQL Server ストアを指定するには、[新規] をクリックし、[新しい SQL Server **ストア** の定義] ダイアログ ボックスで、次のいずれかの操作を行います。</span><span class="sxs-lookup"><span data-stu-id="e5da2-128">To specify a new SQL Server store for mirroring, click **New**, and then in the **Define New SQL Server Store** dialog box, do one of the following:</span></span>
    
     <span data-ttu-id="e5da2-129">a. </span><span class="sxs-lookup"><span data-stu-id="e5da2-129">a.</span></span> <span data-ttu-id="e5da2-130">[SQL SERVER **FQDN]** で、新しいSQL Serverストアを作成する場所の FQDN をSQL Serverします。</span><span class="sxs-lookup"><span data-stu-id="e5da2-130">In **SQL Server FQDN**, specify the FQDN of the SQL Server on which you want to create the new SQL Server store.</span></span>
    
     <span data-ttu-id="e5da2-131">b.</span><span class="sxs-lookup"><span data-stu-id="e5da2-131">b.</span></span> <span data-ttu-id="e5da2-132">既定のインスタンスを使用するには [**既定のインスタンス**] をクリックし、別のインスタンスを指定するには [**名前付きインスタンス**] をクリックして、使用するインスタンスを指定します。</span><span class="sxs-lookup"><span data-stu-id="e5da2-132">Either click **Default Instance** to use the default instance, or, to specify a different instance, click **Named Instance**, and then specify the instance you want to use.</span></span>
    
     <span data-ttu-id="e5da2-133">c.</span><span class="sxs-lookup"><span data-stu-id="e5da2-133">c.</span></span> <span data-ttu-id="e5da2-134">指定した SQL Server インスタンスがミラーリング関係にある場合は、[This SQL **instance is in mirroring relation]** チェック ボックスをオンにし **、[Mirror port number]** でポート番号を指定します。</span><span class="sxs-lookup"><span data-stu-id="e5da2-134">If the specified SQL Server instance is in a mirroring relationship, select the **This SQL instance is in mirroring relation** check box, and then, in **Mirror port number**, specify the port number.</span></span>
    
   - <span data-ttu-id="e5da2-135">SQL Server ミラーリングを有効にし、SQL Server ミラーリング監視 (プライマリ SQL Server とミラー インスタンスの正常性を検出できる 3 番目の独立した SQL Server インスタンス) を含める場合は **、[SQL Server** ミラーリング監視を使用して自動フェールオーバーを有効にする] チェック ボックスをオンにし、次のいずれかの操作を行います。</span><span class="sxs-lookup"><span data-stu-id="e5da2-135">If you enable SQL Server mirroring and want to include a SQL Server mirroring witness (a third, separate SQL Server instance that can detect the health of the primary SQL Server and mirror instances), select the **Use SQL Server mirroring witness to enable automatic failover** check box, and then do one of the following:</span></span>
    
     <span data-ttu-id="e5da2-136">a. </span><span class="sxs-lookup"><span data-stu-id="e5da2-136">a.</span></span> <span data-ttu-id="e5da2-137">FQDN **SQL Server新** しいミラーリング監視を作成するサーバーの FQDN SQL Server指定します。</span><span class="sxs-lookup"><span data-stu-id="e5da2-137">In **SQL Server FQDN**, specify the FQDN of the server on which you want to create the new SQL Server mirroring witness.</span></span>
    
     <span data-ttu-id="e5da2-138">b.</span><span class="sxs-lookup"><span data-stu-id="e5da2-138">b.</span></span> <span data-ttu-id="e5da2-139">既定のインスタンスを使用するには [**既定のインスタンス**] をクリックし、別のインスタンスを指定するには [**名前付きインスタンス**] をクリックして、ミラーリング監視で使用するインスタンスを指定します。</span><span class="sxs-lookup"><span data-stu-id="e5da2-139">Either click **Default Instance** to use the default instance, or, to specify a different instance, click **Named Instance**, and then specify the instance you want to use for the mirroring witness.</span></span>
    
     <span data-ttu-id="e5da2-140">c.</span><span class="sxs-lookup"><span data-stu-id="e5da2-140">c.</span></span> <span data-ttu-id="e5da2-141">指定した SQL Server インスタンスがミラーリング関係にある場合は、[This SQL **instance is in mirroring relation]** チェック ボックスをオンにし **、[Mirror port number]** でポート番号を指定します。</span><span class="sxs-lookup"><span data-stu-id="e5da2-141">If the specified SQL Server instance is in a mirroring relationship, select the **This SQL instance is in mirroring relation** check box, and then, in **Mirror port number**, specify the port number.</span></span>
    
10. <span data-ttu-id="e5da2-142">構成を保存するには、[**OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="e5da2-142">To save the configuration, click **OK**.</span></span>
    
### <a name="publish-the-updated-topology-to-add-an-archiving-database-to-your-deployment"></a><span data-ttu-id="e5da2-143">更新されたトポロジを公開してアーカイブ データベースを展開に追加する</span><span class="sxs-lookup"><span data-stu-id="e5da2-143">Publish the updated topology to add an archiving database to your deployment</span></span>

1. <span data-ttu-id="e5da2-144">Skype for Business Server を実行しているコンピューター、または Skype for Business Server 管理ツールがインストールされているコンピューターで、ローカルの Users グループのメンバーであるアカウント (または同等のユーザー権限を持つアカウント) を使用してログオンします。</span><span class="sxs-lookup"><span data-stu-id="e5da2-144">On a computer that is running Skype for Business Server, or on which the Skype for Business Server administrative tools are installed, log on using an account that is a member of the local Users group (or an account with equivalent user rights).</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="e5da2-145">ローカル Users グループのメンバーであるアカウントを使用してトポロジを定義できます。 ただし、トポロジにサーバーを追加するために必要なトポロジを公開するには **、Domain Admins** グループと **RTCUniversalServerAdmins** グループのメンバーであり、Skype for Business Server ファイル ストアで使用しているファイル共有に対するフル コントロールのアクセス許可 (読み取り、書き込み、および変更) を持つアカウント (必要な随意アクセス制御リスト (DACL) または同等の権限を持つアカウント) を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e5da2-145">You can define a topology by using an account that is a member of the local Users group, but to publish a topology, which is required to add a server to the topology, you must use an account that is a member of the **Domain Admins** group and the **RTCUniversalServerAdmins** group, and that has full control permissions (read, write, and modify) on the file share that you are using for the Skype for Business Server file store (so that Topology Builder can configure the required discretionary access control list (DACLs), or an account with equivalent rights.</span></span>
  
2. <span data-ttu-id="e5da2-146">トポロジ ビルダーを使用して、前のセクションで作成したトポロジを開きます。</span><span class="sxs-lookup"><span data-stu-id="e5da2-146">Open the topology you created in the previous section using Topology Builder.</span></span>
    
3. <span data-ttu-id="e5da2-147">コンソール ツリーで **、Skype for Business Server** を右クリックし、[トポロジの公開] **をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="e5da2-147">In the console tree, right-click **Skype for Business Server**, and then click **Publish Topology**.</span></span>
    
4. <span data-ttu-id="e5da2-148">[**トポロジの公開**] ページで、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="e5da2-148">On the **Publish the topology** page, click **Next**.</span></span>
    
5. <span data-ttu-id="e5da2-149">[**データベースの作成**] ページで、データベースが選択されていることを確認して、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="e5da2-149">On the **Create databases** page, verify that the database is selected, and then click **Next**.</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="e5da2-150">データベースを作成するための適切なアクセス許可を持っていない場合、ここでのデータベースの選択を取り消して、適切なアクセス許可を持つ別のユーザーがデータベースを作成できます。</span><span class="sxs-lookup"><span data-stu-id="e5da2-150">If you do not have the appropriate permissions to create databases, you can cancel the selection of the database and someone with appropriate permissions can create the database.</span></span> <span data-ttu-id="e5da2-151">> 専用サーバー上のデータベースSQLトポロジ ビルダーを使用してインストールできます。</span><span class="sxs-lookup"><span data-stu-id="e5da2-151">> Only databases on dedicated SQL Servers can be installed by using Topology Builder.</span></span> <span data-ttu-id="e5da2-152">他のサーバー コンポーネントと併置されている SQL サーバー上のデータベースは、そのコンピューターでローカル セットアップを実行してインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="e5da2-152">Databases on SQL Servers that are collocated with other server components must be installed by running local setup on that computer.</span></span> 
  
6. <span data-ttu-id="e5da2-153">**[公開完了のウィザード]** ページで、トポロジが正常に公開されたことを確認し、**[完了]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="e5da2-153">On the **Publishing wizard complete** page, verify that the topology was successfully published, and then click **Finish**.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="e5da2-154">トポロジを公開した後、コンテンツをアーカイブする前に、アーカイブのオプションおよびポリシーを構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e5da2-154">After publishing the topology, you must configure options and policies for Archiving before any content can be archived.</span></span> <span data-ttu-id="e5da2-155">詳細については [、「Skype for Business Server のアーカイブ](configure-archiving-options.md) オプションを構成する」および「Skype for Business Server のアーカイブ ポリシー [を構成する」を参照してください](configure-archiving-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="e5da2-155">For details, see [Configure archiving options for Skype for Business Server](configure-archiving-options.md) and [Configure archiving policies for Skype for Business Server](configure-archiving-policies.md).</span></span> 
  

