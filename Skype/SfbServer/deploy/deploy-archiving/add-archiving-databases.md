---
title: Skype for Business Server 2015 での既存の展開へのアーカイブ データベースの追加
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 2/7/2018
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 3b67df85-181d-45ca-ba48-bb74a439f242
description: '概要: このサーバー 2015 のビジネスを展開するため、Skype にアーカイブ データベースを追加する方法についてを参照できます。'
ms.openlocfilehash: 09185eed2a8bd0cc9b2a03fc6361abeadbd01829
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/28/2018
---
# <a name="add-archiving-databases-to-an-existing-deployment-in-skype-for-business-server-2015"></a><span data-ttu-id="96bae-103">Skype for Business Server 2015 での既存の展開へのアーカイブ データベースの追加</span><span class="sxs-lookup"><span data-stu-id="96bae-103">Add archiving databases to an existing deployment in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="96bae-104">**の概要:**サーバー 2015 のビジネスを展開するため、Skype にアーカイブ データベースを追加する方法の詳細については、このトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="96bae-104">**Summary:** Read this topic to learn how to add archiving databases to your Skype for Business Server 2015 deployment.</span></span>
  
<span data-ttu-id="96bae-105">アーカイブをサポートするように展開を構成する前に、トポロジにアーカイブを組み込む必要があります。</span><span class="sxs-lookup"><span data-stu-id="96bae-105">You must incorporate archiving into your topology before you can configure your deployment to support archiving.</span></span> <span data-ttu-id="96bae-106">このトピックの情報には、トポロジ ビルダーを使用する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="96bae-106">The information in this topic explains how to use Topology Builder to:</span></span>
  
- <span data-ttu-id="96bae-107">アーカイブ データベースをトポロジに追加する。</span><span class="sxs-lookup"><span data-stu-id="96bae-107">Add an archiving database to your topology.</span></span>
    
- <span data-ttu-id="96bae-108">サーバー 2015 のビジネスを展開するため、Skype にアーカイブ データベースを追加するのには更新したトポロジを公開します。</span><span class="sxs-lookup"><span data-stu-id="96bae-108">Publish the updated topology to add the archiving database to your Skype for Business Server 2015 deployment.</span></span>
    
> [!NOTE]
> <span data-ttu-id="96bae-109">展開で、アーカイブ ・ データとすべてのユーザーの Exchange サーバー上のファイルを格納する Microsoft Exchange の統合を使用する場合は、 **SQL Server のアーカイブを保存**または**使用して SQL Server ストアにミラー化**の情報を指定することはしません。</span><span class="sxs-lookup"><span data-stu-id="96bae-109">If you want to use Microsoft Exchange integration to store archiving data and files on Exchange servers for all your users in your deployment, do not specify **Archiving SQL Server store** or **Use SQL Server Store mirroring** information.</span></span>
  
### <a name="add-an-archiving-database-to-your-topology"></a><span data-ttu-id="96bae-110">アーカイブ データベースをトポロジに追加する</span><span class="sxs-lookup"><span data-stu-id="96bae-110">Add an archiving database to your topology</span></span>

1. <span data-ttu-id="96bae-111">ビジネス サーバーでは、Skype を実行しているコンピューター上に、Skype ビジネス サーバー管理ツールをインストールするにログオンまたはローカルの Users グループ (または同等のユーザー権限を持つアカウント) のメンバーであるアカウントを使用しています。</span><span class="sxs-lookup"><span data-stu-id="96bae-111">On a computer that is running Skype for Business Server, or on which the Skype for Business Server administrative tools are installed, log on by using an account that is a member of the local Users group (or an account with equivalent user rights).</span></span>
    
2. <span data-ttu-id="96bae-112">トポロジ ビルダーを起動します。</span><span class="sxs-lookup"><span data-stu-id="96bae-112">Start Topology Builder.</span></span>
    
3. <span data-ttu-id="96bae-113">コンソール ツリーで、アーカイブを展開するフロントエンド プールに移動し、アーカイブを展開するフロントエンド プールの名前をクリックします。</span><span class="sxs-lookup"><span data-stu-id="96bae-113">In the console tree, navigate to the Front End pool in which you want to deploy Archiving, and then click the name of the Front End pool where you want to deploy archiving.</span></span>
    
4. <span data-ttu-id="96bae-114">[**操作**] メニューの [**プロパティの編集**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="96bae-114">In the **Action** menu, click **Edit Properties**.</span></span> 
    
5. <span data-ttu-id="96bae-115">[**プロパティの編集**] ダイアログ ボックスで、[**全般**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="96bae-115">In the **Edit Properties** dialog box, click **General**.</span></span>
    
6. <span data-ttu-id="96bae-116">[**アーカイブ**] まで下方向にスクロールします。</span><span class="sxs-lookup"><span data-stu-id="96bae-116">Scroll down to **Archiving**.</span></span>
    
7. <span data-ttu-id="96bae-117">[**アーカイブ**] チェック ボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="96bae-117">Select the **Archiving** check box.</span></span>
    
8. <span data-ttu-id="96bae-118">[ **SQL Server のアーカイブを格納する**には、次のいずれかの操作を行います。</span><span class="sxs-lookup"><span data-stu-id="96bae-118">Under **Archiving SQL Server store,** do one of the following:</span></span>
    
   - <span data-ttu-id="96bae-119">既存の SQL Server ストアを使用するには、ドロップダウン リスト ボックスで、使用する SQL Server ストアの名前をクリックします。</span><span class="sxs-lookup"><span data-stu-id="96bae-119">To use an existing SQL Server store, in the drop-down list box, click the name of the SQL Server store that you want to use.</span></span> <span data-ttu-id="96bae-120">上または Microsoft Exchange Server 2013 のすべてのユーザーのホーム サーバーは、場合アーカイブできます Skype ビジネス コミュニケーションのすべてのユーザーの Exchange です。</span><span class="sxs-lookup"><span data-stu-id="96bae-120">If all of your users are homed on Microsoft Exchange Server 2013 or above, you can archive Skype for Business communications for all your users in Exchange.</span></span> <span data-ttu-id="96bae-121">この例では、SQL Server のアーカイブ ストアを構成する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="96bae-121">In this case, you don't need to configure SQL Server Archiving store.</span></span>
    
   - <span data-ttu-id="96bae-122">新しい SQL Server ストアを指定するには、[**新規**作成] をクリックし**新しい SQL Server ストアの定義**] ダイアログ ボックスで、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="96bae-122">To specify a new SQL Server store, click **New**, and then in the **Define New SQL Server Store** dialog box, do the following:</span></span>
    
   - <span data-ttu-id="96bae-123">**SQL Server の FQDN**を新しい SQL Server ストアを作成するサーバーの FQDN を指定します。</span><span class="sxs-lookup"><span data-stu-id="96bae-123">In **SQL Server FQDN**, specify the FQDN of the server on which you want to create the new SQL Server store.</span></span>
    
   - <span data-ttu-id="96bae-124">既定のインスタンスを使用するには [**既定のインスタンス**] をクリックし、別のインスタンスを指定するには [**名前付きインスタンス**] をクリックして、使用するインスタンスを指定します。</span><span class="sxs-lookup"><span data-stu-id="96bae-124">Either click **Default Instance** to use the default instance, or, to specify a different instance, click **Named instance**, and then specify the instance you want to use.</span></span>
    
   - <span data-ttu-id="96bae-125">ミラーリングの関係で指定された SQL Server のインスタンスがある場合、**ミラーリングの関係ではこの SQL インスタンス**] チェック ボックスをオンを選択し、**ミラー ・ ポートの番号**] ボックスで、ポート番号を指定します。</span><span class="sxs-lookup"><span data-stu-id="96bae-125">If the specified SQL Server instance is in a mirroring relationship, select the **This SQL instance is in mirroring relation** check box, and then, in **Mirror port number**, specify the port number.</span></span>
    
9. <span data-ttu-id="96bae-126">SQL Server ストアのミラーリングを使用する場合は、**有効にする SQL Server のストアのミラーリング**を選択し、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="96bae-126">If you want to use SQL Server store mirroring, select **Enable SQL Server Store mirroring**, and then do the following:</span></span>
    
   - <span data-ttu-id="96bae-127">ミラーリングは、 **SQL Server のアーカイブ ストア ミラー** 」ドロップ ダウン リスト ボックスで、既存の SQL Server ストアを使用するには、ミラーリングに使用する SQL Server のストアの名前をクリックします。</span><span class="sxs-lookup"><span data-stu-id="96bae-127">To use an existing SQL Server store for mirroring, in the **Archiving SQL Server store mirror** drop-down list box, click the name of the SQL Server store that you want to use for mirroring.</span></span>
    
   - <span data-ttu-id="96bae-128">ミラーリング用の新しい SQL Server ストアを指定するに [**新規**作成] をクリックし、**新しい SQL Server ストアの定義**] ダイアログ ボックスでの操作を行います次のいずれか。</span><span class="sxs-lookup"><span data-stu-id="96bae-128">To specify a new SQL Server store for mirroring, click **New**, and then in the **Define New SQL Server Store** dialog box, do one of the following:</span></span>
    
    <span data-ttu-id="96bae-129">a.</span><span class="sxs-lookup"><span data-stu-id="96bae-129">a.</span></span> <span data-ttu-id="96bae-130">**SQL Server の FQDN**を新しい SQL Server ストアを作成する SQL Server の FQDN を指定します。</span><span class="sxs-lookup"><span data-stu-id="96bae-130">In **SQL Server FQDN**, specify the FQDN of the SQL Server on which you want to create the new SQL Server store.</span></span>
    
    <span data-ttu-id="96bae-131">b.</span><span class="sxs-lookup"><span data-stu-id="96bae-131">b.</span></span> <span data-ttu-id="96bae-132">既定のインスタンスを使用するには [**既定のインスタンス**] をクリックし、別のインスタンスを指定するには [**名前付きインスタンス**] をクリックして、使用するインスタンスを指定します。</span><span class="sxs-lookup"><span data-stu-id="96bae-132">Either click **Default Instance** to use the default instance, or, to specify a different instance, click **Named Instance**, and then specify the instance you want to use.</span></span>
    
    <span data-ttu-id="96bae-133">c.</span><span class="sxs-lookup"><span data-stu-id="96bae-133">c.</span></span> <span data-ttu-id="96bae-134">ミラーリングの関係で指定された SQL Server のインスタンスがある場合、**ミラーリングの関係ではこの SQL インスタンス**] チェック ボックスをオンを選択し、**ミラー ・ ポートの番号**] ボックスで、ポート番号を指定します。</span><span class="sxs-lookup"><span data-stu-id="96bae-134">If the specified SQL Server instance is in a mirroring relationship, select the **This SQL instance is in mirroring relation** check box, and then, in **Mirror port number**, specify the port number.</span></span>
    
   - <span data-ttu-id="96bae-135">SQL Server のミラーリングを有効にするし、ミラーリング監視 (、第 3 に、独立した SQL Server のインスタンスを主要な SQL Server インスタンスとミラー インスタンスの稼働状態を検出することができます)、SQL Server を追加する、**のミラーリング監視を使用して SQL Server の自動を有効にするを選択します。フェイル オーバー ・**チェック ボックスをオンし、次のいずれかの操作を行います。</span><span class="sxs-lookup"><span data-stu-id="96bae-135">If you enable SQL Server mirroring and want to include a SQL Server mirroring witness (a third, separate SQL Server instance that can detect the health of the primary SQL Server and mirror instances), select the **Use SQL Server mirroring witness to enable automatic failover** check box, and then do one of the following:</span></span>
    
    <span data-ttu-id="96bae-136">a.</span><span class="sxs-lookup"><span data-stu-id="96bae-136">a.</span></span> <span data-ttu-id="96bae-137">**SQL Server の FQDN**では、ミラーリング監視をミラーリングする新しい SQL Server を作成するサーバーの FQDN を指定します。</span><span class="sxs-lookup"><span data-stu-id="96bae-137">In **SQL Server FQDN**, specify the FQDN of the server on which you want to create the new SQL Server mirroring witness.</span></span>
    
    <span data-ttu-id="96bae-138">b.</span><span class="sxs-lookup"><span data-stu-id="96bae-138">b.</span></span> <span data-ttu-id="96bae-139">既定のインスタンスを使用するには [**既定のインスタンス**] をクリックし、別のインスタンスを指定するには [**名前付きインスタンス**] をクリックして、ミラーリング監視で使用するインスタンスを指定します。</span><span class="sxs-lookup"><span data-stu-id="96bae-139">Either click **Default Instance** to use the default instance, or, to specify a different instance, click **Named Instance**, and then specify the instance you want to use for the mirroring witness.</span></span>
    
    <span data-ttu-id="96bae-140">c.</span><span class="sxs-lookup"><span data-stu-id="96bae-140">c.</span></span> <span data-ttu-id="96bae-141">ミラーリングの関係で指定された SQL Server のインスタンスがある場合、**ミラーリングの関係ではこの SQL インスタンス**] チェック ボックスをオンを選択し、**ミラー ・ ポートの番号**] ボックスで、ポート番号を指定します。</span><span class="sxs-lookup"><span data-stu-id="96bae-141">If the specified SQL Server instance is in a mirroring relationship, select the **This SQL instance is in mirroring relation** check box, and then, in **Mirror port number**, specify the port number.</span></span>
    
10. <span data-ttu-id="96bae-142">構成を保存するには、[**OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="96bae-142">To save the configuration, click **OK**.</span></span>
    
### <a name="publish-the-updated-topology-to-add-an-archiving-database-to-your-deployment"></a><span data-ttu-id="96bae-143">アーカイブ データベースを展開に追加するために、更新されたトポロジを公開する</span><span class="sxs-lookup"><span data-stu-id="96bae-143">Publish the updated topology to add an archiving database to your deployment</span></span>

1. <span data-ttu-id="96bae-144">ビジネス サーバーでは、Skype を実行しているコンピューター上に、Skype ビジネス サーバー管理ツールをインストールするにログオンまたはローカルの Users グループ (または同等のユーザー権限を持つアカウント) のメンバーであるアカウントを使用しています。</span><span class="sxs-lookup"><span data-stu-id="96bae-144">On a computer that is running Skype for Business Server, or on which the Skype for Business Server administrative tools are installed, log on using an account that is a member of the local Users group (or an account with equivalent user rights).</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="96bae-145">ローカルの Users グループのメンバーであるアカウントを使用してトポロジを定義することができますが、トポロジでは、サーバーをトポロジに追加するのに必要なを公開するには、 **RTCUniversalServer し、 **Domain Admins**グループのメンバーであるアカウントを使用する必要があります。管理者**グループがフル コントロールのアクセス許可 (読み取り、書き込み、および変更) (トポロジ ビルダーで必要な随意アクセス制御リスト (Dacl) を構成できますようにまたはビジネス サーバーのファイル ストアの Skype を使用しているファイル共有の同等の権利を持つアカウント。</span><span class="sxs-lookup"><span data-stu-id="96bae-145">You can define a topology by using an account that is a member of the local Users group, but to publish a topology, which is required to add a server to the topology, you must use an account that is a member of the **Domain Admins** group and the **RTCUniversalServerAdmins** group, and that has full control permissions (read, write, and modify) on the file share that you are using for the Skype for Business Server file store (so that Topology Builder can configure the required discretionary access control list (DACLs), or an account with equivalent rights.</span></span>
  
2. <span data-ttu-id="96bae-146">トポロジ ビルダーを使用して前のセクションで作成したトポロジを開きます。</span><span class="sxs-lookup"><span data-stu-id="96bae-146">Open the topology you created in the previous section using Topology Builder.</span></span>
    
3. <span data-ttu-id="96bae-147">コンソール ツリーでは、 **Skype**ビジネス サーバーを右クリックし、 **[トポロジの公開**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="96bae-147">In the console tree, right-click **Skype for Business Server**, and then click **Publish Topology**.</span></span>
    
4. <span data-ttu-id="96bae-148">[**トポロジの公開**] ページで、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="96bae-148">On the **Publish the topology** page, click **Next**.</span></span>
    
5. <span data-ttu-id="96bae-149">[**データベースの作成**] ページで、データベースが選択されていることを確認し、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="96bae-149">On the **Create databases** page, verify that the database is selected, and then click **Next**.</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="96bae-150">データベースを作成するための適切なアクセス許可を持っていない場合、ここでのデータベースの選択を取り消して、適切なアクセス許可を持つ別のユーザーがデータベースを作成できます。</span><span class="sxs-lookup"><span data-stu-id="96bae-150">If you do not have the appropriate permissions to create databases, you can cancel the selection of the database and someone with appropriate permissions can create the database.</span></span> <span data-ttu-id="96bae-151">> 専用の SQL サーバー データベースだけは、トポロジ ビルダーを使用してインストールできます。</span><span class="sxs-lookup"><span data-stu-id="96bae-151">> Only databases on dedicated SQL Servers can be installed by using Topology Builder.</span></span> <span data-ttu-id="96bae-152">他のサーバー コンポーネントと併置されている SQL Server 上のデータベースは、そのコンピューター上でローカル セットアップを実行することによってインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="96bae-152">Databases on SQL Servers that are collocated with other server components must be installed by running local setup on that computer.</span></span> 
  
6. <span data-ttu-id="96bae-153">[**公開ウィザードの完了**] ページで、トポロジが正常に公開されたことを確認し、[**完了**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="96bae-153">On the **Publishing wizard complete** page, verify that the topology was successfully published, and then click **Finish**.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="96bae-154">トポロジを公開した後、コンテンツをアーカイブする前に、アーカイブのオプションおよびポリシーを構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="96bae-154">After publishing the topology, you must configure options and policies for Archiving before any content can be archived.</span></span> <span data-ttu-id="96bae-155">詳細については、[アーカイブ ・ ビジネス サーバー 2015 の Skype のオプションを構成](configure-archiving-options.md)し、[アーカイブ ・ ビジネス サーバー 2015 の Skype のポリシーの構成](configure-archiving-policies.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="96bae-155">For details, see [Configure archiving options for Skype for Business Server 2015](configure-archiving-options.md) and [Configure archiving policies for Skype for Business Server 2015](configure-archiving-policies.md).</span></span> 
  

