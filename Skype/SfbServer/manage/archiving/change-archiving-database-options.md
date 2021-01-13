---
title: Skype for Business Server のアーカイブ データベース オプションを変更する
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: dbebaa0a-f3a2-4dbd-b64e-07a62370f899
description: '概要: Skype for Business Server のアーカイブ データベース オプションを変更する方法について説明します。'
ms.openlocfilehash: 9a2b1056b6dd5d31c8b1dda658e219c345b28278
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49817697"
---
# <a name="change-archiving-database-options-in-skype-for-business-server"></a><span data-ttu-id="3eb37-103">Skype for Business Server のアーカイブ データベース オプションを変更する</span><span class="sxs-lookup"><span data-stu-id="3eb37-103">Change Archiving database options in Skype for Business Server</span></span>

<span data-ttu-id="3eb37-104">**概要:** Skype for Business Server のアーカイブ データベース オプションを変更する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="3eb37-104">**Summary:** Learn how to change archiving database options for Skype for Business Server.</span></span>
  
<span data-ttu-id="3eb37-105">ユーザーのアーカイブ ストレージ用に SQL Server ストレージを使用してアーカイブを展開する場合は、次のデータベース ストレージを変更できます。</span><span class="sxs-lookup"><span data-stu-id="3eb37-105">If you deploy archiving using SQL Server storage for archiving storage for any of your users, you can make the following database storage changes:</span></span>
  
- <span data-ttu-id="3eb37-106">アーカイブ ストレージに別SQL Serverデータベースを使用します。</span><span class="sxs-lookup"><span data-stu-id="3eb37-106">Use a different SQL Server database for archiving storage.</span></span> <span data-ttu-id="3eb37-107">これには、プライマリ アーカイブ データベースと、ミラーリングのミラーリングに使用SQL Serverがあります。</span><span class="sxs-lookup"><span data-stu-id="3eb37-107">This includes the primary Archiving database and any database you use for SQL Server mirroring.</span></span>
    
- <span data-ttu-id="3eb37-108">Microsoft Exchange 統合に切り替えて、アーカイブ データとファイルを Exchange サーバーに保存します。</span><span class="sxs-lookup"><span data-stu-id="3eb37-108">Switch to Microsoft Exchange integration to store archiving data and files on Exchange servers.</span></span> <span data-ttu-id="3eb37-109">すべてのユーザーが Exchange サーバーに配置され、展開内のすべてのユーザーに Microsoft Exchange ストレージを使用する場合は、トポロジから SQL Server ストア データベースを削除する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3eb37-109">If all your users are homed on your Exchange servers and you want to use Microsoft Exchange storage for all users in your deployment, you should remove the SQL Server store databases from your topology.</span></span> 
    
<span data-ttu-id="3eb37-110">これらの変更のいずれかを行う場合は、トポロジ ビルダーを実行し、変更を加え、トポロジを再度公開する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3eb37-110">To make either of these changes, you must run Topology Builder, make the changes, and then publish the topology again.</span></span> <span data-ttu-id="3eb37-111">Exchange サーバー **にSQL Server** Skype for Businessユーザーがいない場合は、アーカイブ ストアを指定したり、SQL Server ストアのミラーリング情報を有効にしたりしません。</span><span class="sxs-lookup"><span data-stu-id="3eb37-111">Do not specify **Archiving SQL Server store** or **Enable SQL Server store mirroring** information, unless you have Skype for Business users who are not homed on Exchange servers.</span></span>
  
## <a name="change-archiving-database-options"></a><span data-ttu-id="3eb37-112">アーカイブ データベース オプションの変更</span><span class="sxs-lookup"><span data-stu-id="3eb37-112">Change Archiving database options</span></span>

1. <span data-ttu-id="3eb37-113">Skype for Business Server を実行しているコンピューター、または Skype for Business Server 管理ツールがインストールされているコンピューターで、ローカルの Users グループのメンバーであるアカウント (または同等のユーザー権限を持つアカウント) を使用してログオンします。</span><span class="sxs-lookup"><span data-stu-id="3eb37-113">On a computer that is running Skype for Business Server, or on which the Skype for Business Server administrative tools are installed, log on by using an account that is a member of the local Users group (or an account with equivalent user rights).</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="3eb37-114">ローカル Users グループのメンバーであるアカウントを使用してトポロジを定義できますが、トポロジを公開するには、 トポロジにコンポーネントを追加するために必要なアカウントは **、Domain Admins** グループと **RTCUniversalServerAdmins** グループのメンバーであり、Skype for Business Server ファイル ストアで使用しているファイル共有に対するフル コントロールのアクセス許可 (読み取り、書き込み、変更) を持つアカウント (つまり、必要な随意アクセス制御リスト (DACL) または同等の権限を持つアカウントを構成できる) を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3eb37-114">You can define a topology by using an account that is a member of the local Users group, but to publish a topology, which is required to add a component to the topology, you must use an account that is a member of the **Domain Admins** group and the **RTCUniversalServerAdmins** group, and that has full control permissions (that is, read, write, and modify) on the file share that you are using for the Skype for Business Server file store (that is, so that Topology Builder can configure the required discretionary access control lists (DACLs), or an account with equivalent rights.</span></span>
  
2. <span data-ttu-id="3eb37-115">トポロジ ビルダーを開始します。</span><span class="sxs-lookup"><span data-stu-id="3eb37-115">Start Topology Builder.</span></span>
    
3. <span data-ttu-id="3eb37-116">コンソール プールで、アーカイブを展開したフロントエンド プールに移動し、データベース オプションを変更するフロントエンド プールの名前をクリックします。</span><span class="sxs-lookup"><span data-stu-id="3eb37-116">In the console tree, navigate to the Front End pool in which you deployed Archiving, and then click the name of the Front End pool where you want to change the database options.</span></span>
    
4. <span data-ttu-id="3eb37-117">[**操作**] メニューの [**プロパティの編集**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="3eb37-117">In the **Action** menu, click **Edit Properties**.</span></span> 
    
5. <span data-ttu-id="3eb37-118">[**プロパティの編集**] ダイアログ ボックスで、[**全般**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="3eb37-118">In the **Edit Properties** dialog box, click **General**.</span></span>
    
6. <span data-ttu-id="3eb37-119">[**アーカイブ**] まで下方向にスクロールします。</span><span class="sxs-lookup"><span data-stu-id="3eb37-119">Scroll down to **Archiving**.</span></span>
    
7. <span data-ttu-id="3eb37-120">[**アーカイブ**] で、次の操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="3eb37-120">In **Archiving**, do the following:</span></span>
    
   - <span data-ttu-id="3eb37-121">別の既存の SQL Server ストアに変更するには、[**アーカイブ SQL Server ストア**] ドロップダウン リスト ボックスで、次の操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="3eb37-121">To change to a different existing SQL Server store, under **Archiving SQL Server store**, in the drop-down list box, do the following:</span></span>
    
   - <span data-ttu-id="3eb37-122">既存の SQL Server ストアを使用するには、ドロップダウン リスト ボックスで、使用する SQL Server ストアの名前をクリックします。</span><span class="sxs-lookup"><span data-stu-id="3eb37-122">To use an existing SQL Server store, in the drop-down list box, click the name of the SQL Server store that you want to use.</span></span>
    
   - <span data-ttu-id="3eb37-123">新しい SQL Server ストアを定義するには、[**新規作成**] をクリックし、[**新しい SQL Server ストアの定義**] ダイアログ ボックスで次の操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="3eb37-123">To specify a new SQL Server store, click **New**, and then in the **Define New SQL Server store** dialog box, do the following:</span></span>
    
     - <span data-ttu-id="3eb37-124">既存の SQL Server ストアを使用するには、ドロップダウン リスト ボックスで、使用する SQL Server ストアの名前をクリックします。</span><span class="sxs-lookup"><span data-stu-id="3eb37-124">To use an existing SQL Server store, in the drop-down list box, click the name of the SQL Server store that you want to use.</span></span>
    
     - <span data-ttu-id="3eb37-125">新しいストアをSQL Serverするには、[新規] をクリックし、[ストアの新しいSQL Server **定義**] ダイアログ ボックスで、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="3eb37-125">To specify a new SQL Server store, click **New**, and then in the **Define New SQL Server Store** dialog box, do the following:</span></span>
    
       - <span data-ttu-id="3eb37-126">[SQL SERVER **FQDN]** で、新しいドメイン ストアを作成するサーバーの FQDN SQL Serverします。</span><span class="sxs-lookup"><span data-stu-id="3eb37-126">In **SQL Server FQDN**, specify the FQDN of the server on which you want to create the new SQL Server store.</span></span>
    
       - <span data-ttu-id="3eb37-127">既定のインスタンスを使用するには [**既定のインスタンス**] をクリックし、別のインスタンスを指定するには [**名前付きインスタンス**] をクリックして、使用するインスタンスを指定します。</span><span class="sxs-lookup"><span data-stu-id="3eb37-127">Either click **Default Instance** to use the default instance, or, to specify a different instance, click **Named instance**, and then specify the instance you want to use.</span></span>
    
       - <span data-ttu-id="3eb37-128">指定した SQL Server インスタンスがミラーリング関係にある場合は、[This SQL **instance is in mirroring relation]** チェック ボックスをオンにし **、[Mirror port number]** でポート番号を指定します。</span><span class="sxs-lookup"><span data-stu-id="3eb37-128">If the specified SQL Server instance is in a mirroring relationship, select the **This SQL instance is in mirroring relation** check box, and then, in **Mirror port number**, specify the port number.</span></span>
    
   - <span data-ttu-id="3eb37-129">ミラーリング用に SQL Server ストアを追加するか、SQL Server ストア ミラーリングとして別の既存の SQL Server ストアに変更するには、[**SQL Server ストア ミラーリングを有効にする**] を選択して、以下の作業をします。</span><span class="sxs-lookup"><span data-stu-id="3eb37-129">To add SQL Server store for mirroring or change to a different existing SQL Server store for SQL Server store mirroring, select **Enable SQL Server store mirroring**, and then do the following:</span></span>
    
     - <span data-ttu-id="3eb37-130">既存の SQL Server ストアをミラーリングに使用するには、[アーカイブ **SQL Server** ストアのミラー] ドロップダウン リスト ボックスで、ミラーリングに使用する SQL Server ストアの名前をクリックします。</span><span class="sxs-lookup"><span data-stu-id="3eb37-130">To use an existing SQL Server store for mirroring, in the **Archiving SQL Server store mirror** drop-down list box, click the name of the SQL Server store that you want to use for mirroring.</span></span>
    
     - <span data-ttu-id="3eb37-131">ミラーリング用の新SQL Serverストアを指定するには、[新規] をクリックし、[新しい SQL Server **ストア** の定義] ダイアログ ボックスで、次のいずれかの操作を行います。</span><span class="sxs-lookup"><span data-stu-id="3eb37-131">To specify a new SQL Server store for mirroring, click **New**, and then in the **Define New SQL Server Store** dialog box, do one of the following:</span></span>
    
       <span data-ttu-id="3eb37-132">a. </span><span class="sxs-lookup"><span data-stu-id="3eb37-132">a.</span></span> <span data-ttu-id="3eb37-133">[SQL SERVER **FQDN]** で、新しいSQL Serverストアを作成する場所の FQDN をSQL Serverします。</span><span class="sxs-lookup"><span data-stu-id="3eb37-133">In **SQL Server FQDN**, specify the FQDN of the SQL Server on which you want to create the new SQL Server store.</span></span>
    
       <span data-ttu-id="3eb37-134">b.</span><span class="sxs-lookup"><span data-stu-id="3eb37-134">b.</span></span> <span data-ttu-id="3eb37-135">既定のインスタンスを使用するには [**既定のインスタンス**] をクリックし、別のインスタンスを指定するには [**名前付きインスタンス**] をクリックして、使用するインスタンスを指定します。</span><span class="sxs-lookup"><span data-stu-id="3eb37-135">Either click **Default Instance** to use the default instance, or, to specify a different instance, click **Named Instance**, and then specify the instance you want to use.</span></span>
    
       <span data-ttu-id="3eb37-136">c.</span><span class="sxs-lookup"><span data-stu-id="3eb37-136">c.</span></span> <span data-ttu-id="3eb37-137">指定した SQL Server インスタンスがミラーリング関係にある場合は、[This SQL **instance is in mirroring relation]** チェック ボックスをオンにし **、[Mirror port number]** でポート番号を指定します。</span><span class="sxs-lookup"><span data-stu-id="3eb37-137">If the specified SQL Server instance is in a mirroring relationship, select the **This SQL instance is in mirroring relation** check box, and then, in **Mirror port number**, specify the port number.</span></span>
    
   - <span data-ttu-id="3eb37-138">SQL Server ミラーリングを有効にし、SQL Server ミラーリング監視 (プライマリ SQL Server サーバーとミラー インスタンスの正常性を検出できる 3 つ目の独立した SQL Server インスタンス) を追加または変更する場合は **、[SQL Server** ミラーリング監視を使用して自動フェールオーバーを有効にする] チェック ボックスをオンにし、次のいずれかの操作を行います。</span><span class="sxs-lookup"><span data-stu-id="3eb37-138">If you enable SQL Server mirroring and want to add or change a SQL Server mirroring witness (a third, separate SQL Server instance that can detect the health of the primary SQL Server server and mirror instances), select the **Use SQL Server mirroring witness to enable automatic failover** check box, and then do one of the following:</span></span>
    
      <span data-ttu-id="3eb37-139">a. </span><span class="sxs-lookup"><span data-stu-id="3eb37-139">a.</span></span> <span data-ttu-id="3eb37-140">FQDN **SQL Server新** しいミラーリング監視を作成するサーバーの FQDN SQL Server指定します。</span><span class="sxs-lookup"><span data-stu-id="3eb37-140">In **SQL Server FQDN**, specify the FQDN of the server on which you want to create the new SQL Server mirroring witness.</span></span>
    
      <span data-ttu-id="3eb37-141">b.</span><span class="sxs-lookup"><span data-stu-id="3eb37-141">b.</span></span> <span data-ttu-id="3eb37-142">既定のインスタンスを使用するには [**既定のインスタンス**] をクリックし、別のインスタンスを指定するには [**名前付きインスタンス**] をクリックして、ミラーリング監視で使用するインスタンスを指定します。</span><span class="sxs-lookup"><span data-stu-id="3eb37-142">Either click **Default Instance** to use the default instance, or, to specify a different instance, click **Named Instance**, and then specify the instance you want to use for the mirroring witness.</span></span>
    
      <span data-ttu-id="3eb37-143">c.</span><span class="sxs-lookup"><span data-stu-id="3eb37-143">c.</span></span> <span data-ttu-id="3eb37-144">指定した SQL Server インスタンスがミラーリング関係にある場合は、[This SQL **instance is in mirroring relation]** チェック ボックスをオンにし **、[Mirror port number]** でポート番号を指定します。</span><span class="sxs-lookup"><span data-stu-id="3eb37-144">If the specified SQL Server instance is in a mirroring relationship, select the **This SQL instance is in mirroring relation** check box, and then, in **Mirror port number**, specify the port number.</span></span>
    
   - <span data-ttu-id="3eb37-145">Microsoft Exchange 統合に切り替えて、アーカイブ データとファイルを Exchange サーバーに保存するには (展開内のすべてのユーザーが Exchange サーバーに配置されている場合)、アーカイブ データベースのすべての情報を削除します。</span><span class="sxs-lookup"><span data-stu-id="3eb37-145">To switch to Microsoft Exchange integration to store archiving data and files on Exchange servers (if all users in your deployment are homed on your Exchange servers), delete all information for Archiving databases.</span></span>
    
     > [!IMPORTANT]
     > <span data-ttu-id="3eb37-146">Exchange サーバーにホームではない Skype for Business ユーザーがいる場合は、ストア情報SQL Server削除しません。</span><span class="sxs-lookup"><span data-stu-id="3eb37-146">If you have any Skype for Business users who are not homed on Exchange servers, do not delete the SQL Server store information.</span></span> 
  
8. <span data-ttu-id="3eb37-147">構成を保存するには、[**OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="3eb37-147">To save the configuration, click **OK**.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="3eb37-148">トポロジ ビルダーで行った変更は、新しいトポロジを公開するまで有効ではありません。</span><span class="sxs-lookup"><span data-stu-id="3eb37-148">The changes you make in Topology Builder do not take effect until you publish the new topology.</span></span> <span data-ttu-id="3eb37-149">詳細については [、「Skype for Business Server の既存の展開にアーカイブ データベースを追加する」を参照してください](../../deploy/deploy-archiving/add-archiving-databases.md)。</span><span class="sxs-lookup"><span data-stu-id="3eb37-149">For details, see [Add archiving databases to an existing deployment in Skype for Business Server](../../deploy/deploy-archiving/add-archiving-databases.md).</span></span> 
  
## <a name="change-the-location-of-the-archiving-database-by-using-windows-powershell"></a><span data-ttu-id="3eb37-150">アーカイブ データベースを使用してアーカイブ データベースの場所を変更Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="3eb37-150">Change the location of the Archiving database by using Windows PowerShell</span></span>

<span data-ttu-id="3eb37-151">ほとんどの場合、アーカイブ サーバーのインストール時に指定されているアーカイブ データベースの場所を変更する必要は生じしません。</span><span class="sxs-lookup"><span data-stu-id="3eb37-151">In most cases, you will not need to change the location of the Archiving database, which is specified when you install Archiving Server.</span></span> <span data-ttu-id="3eb37-152">ただし、ハードウェア障害などの問題が発生した場合は **、Set-CsArchivingServer** コマンドレットを使用して、アーカイブ サーバーの接続を新しいデータベースに設定できます。</span><span class="sxs-lookup"><span data-stu-id="3eb37-152">However, if a hardware failure or other problem should occur, you can point Archiving Server to a new database by using the **Set-CsArchivingServer** cmdlet.</span></span>
  
<span data-ttu-id="3eb37-153">次の例では、ArchivingServer:atl-cs-001.contoso.com Archiving Server のアーカイブ データベースの場所を変更します。</span><span class="sxs-lookup"><span data-stu-id="3eb37-153">The following example changes the location of the Archiving database for the ArchivingServer:atl-cs-001.contoso.com Archiving Server.</span></span> <span data-ttu-id="3eb37-154">この例では、新しいデータベースは ArchivingDatabase:atl-sql-001.contoso.com。</span><span class="sxs-lookup"><span data-stu-id="3eb37-154">In this example, the new database is located at ArchivingDatabase:atl-sql-001.contoso.com:</span></span>
  
```PowerShell
Set-CsArchivingServer -Identity "ArchivingServer:atl-cs-001.contoso.com" -ArchivingDatabase "ArchivingDatabase:atl-sql-001.contoso.com"
```


