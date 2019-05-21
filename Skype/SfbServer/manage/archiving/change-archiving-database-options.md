---
title: Skype for Business Server でアーカイブデータベースのオプションを変更する
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: dbebaa0a-f3a2-4dbd-b64e-07a62370f899
description: '概要: Skype for Business Server のアーカイブデータベースオプションを変更する方法について説明します。'
ms.openlocfilehash: 56aa29ef185176ce3b080572723c566455731dc4
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2019
ms.locfileid: "34299987"
---
# <a name="change-archiving-database-options-in-skype-for-business-server"></a><span data-ttu-id="f7795-103">Skype for Business Server でアーカイブデータベースのオプションを変更する</span><span class="sxs-lookup"><span data-stu-id="f7795-103">Change Archiving database options in Skype for Business Server</span></span>

<span data-ttu-id="f7795-104">**概要:** Skype for Business Server のアーカイブデータベースのオプションを変更する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="f7795-104">**Summary:** Learn how to change archiving database options for Skype for Business Server.</span></span>
  
<span data-ttu-id="f7795-105">いずれかのユーザーのために SQL Server ストレージを使用してアーカイブを展開している場合は、次のデータベース記憶域を変更することができます。</span><span class="sxs-lookup"><span data-stu-id="f7795-105">If you deploy archiving using SQL Server storage for archiving storage for any of your users, you can make the following database storage changes:</span></span>
  
- <span data-ttu-id="f7795-106">アーカイブストレージとして別の SQL Server データベースを使用します。</span><span class="sxs-lookup"><span data-stu-id="f7795-106">Use a different SQL Server database for archiving storage.</span></span> <span data-ttu-id="f7795-107">これには、プライマリアーカイブデータベースと、SQL Server ミラーリングで使用するデータベースが含まれます。</span><span class="sxs-lookup"><span data-stu-id="f7795-107">This includes the primary Archiving database and any database you use for SQL Server mirroring.</span></span>
    
- <span data-ttu-id="f7795-108">Exchange server にアーカイブデータとファイルを保存するには、Microsoft Exchange 統合に切り替えます。</span><span class="sxs-lookup"><span data-stu-id="f7795-108">Switch to Microsoft Exchange integration to store archiving data and files on Exchange servers.</span></span> <span data-ttu-id="f7795-109">すべてのユーザーが Exchange サーバーを使用していて、展開内のすべてのユーザーに対して Microsoft Exchange ストレージを使用する場合は、SQL Server ストアデータベースをトポロジから削除する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f7795-109">If all your users are homed on your Exchange servers and you want to use Microsoft Exchange storage for all users in your deployment, you should remove the SQL Server store databases from your topology.</span></span> 
    
<span data-ttu-id="f7795-110">これらの変更を行うには、トポロジビルダーを実行し、変更を行ってから、トポロジをもう一度公開する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f7795-110">To make either of these changes, you must run Topology Builder, make the changes, and then publish the topology again.</span></span> <span data-ttu-id="f7795-111">Skype for Business ユーザーが Exchange サーバーを使っていない場合は、**アーカイブ Sql server ストア**または**sql server ストアのミラーリング**情報を有効にしないようにします。</span><span class="sxs-lookup"><span data-stu-id="f7795-111">Do not specify **Archiving SQL Server store** or **Enable SQL Server store mirroring** information, unless you have Skype for Business users who are not homed on Exchange servers.</span></span>
  
## <a name="change-archiving-database-options"></a><span data-ttu-id="f7795-112">アーカイブ データベース オプションの変更</span><span class="sxs-lookup"><span data-stu-id="f7795-112">Change Archiving database options</span></span>

1. <span data-ttu-id="f7795-113">Skype for Business Server を実行しているコンピューター、または Skype for Business Server 管理ツールがインストールされているコンピューターで、ローカルユーザーグループのメンバーであるアカウント (または同等のユーザー権限を持つアカウント) を使用してログオンします。</span><span class="sxs-lookup"><span data-stu-id="f7795-113">On a computer that is running Skype for Business Server, or on which the Skype for Business Server administrative tools are installed, log on by using an account that is a member of the local Users group (or an account with equivalent user rights).</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="f7795-114">トポロジは、[ローカルユーザー] グループのメンバーであるアカウントを使用して定義できますが、トポロジを公開するためには、" **Domain Admins** " グループと "RTCUniversalSer" のメンバーであるアカウントを使用する必要があります。 **verAdmins**グループ、および Skype For Business Server ファイルストアで使用しているファイル共有に対するフルコントロールのアクセス許可 (つまり、読み取り、書き込み、変更) を持っている (つまり、トポロジビルダーが必要な随意アクセス制御を構成できるようにする)リスト (Dacl)、または同等の権限を持つアカウント。</span><span class="sxs-lookup"><span data-stu-id="f7795-114">You can define a topology by using an account that is a member of the local Users group, but to publish a topology, which is required to add a component to the topology, you must use an account that is a member of the **Domain Admins** group and the **RTCUniversalServerAdmins** group, and that has full control permissions (that is, read, write, and modify) on the file share that you are using for the Skype for Business Server file store (that is, so that Topology Builder can configure the required discretionary access control lists (DACLs), or an account with equivalent rights.</span></span>
  
2. <span data-ttu-id="f7795-115">トポロジビルダーを起動します。</span><span class="sxs-lookup"><span data-stu-id="f7795-115">Start Topology Builder.</span></span>
    
3. <span data-ttu-id="f7795-116">コンソール プールで、アーカイブを展開したフロントエンド プールに移動し、データベース オプションを変更するフロントエンド プールの名前をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f7795-116">In the console tree, navigate to the Front End pool in which you deployed Archiving, and then click the name of the Front End pool where you want to change the database options.</span></span>
    
4. <span data-ttu-id="f7795-117">[**アクション**] メニューの [**プロパティの編集**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f7795-117">In the **Action** menu, click **Edit Properties**.</span></span> 
    
5. <span data-ttu-id="f7795-118">[**プロパティの編集**] ダイアログ ボックスで、[**全般**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f7795-118">In the **Edit Properties** dialog box, click **General**.</span></span>
    
6. <span data-ttu-id="f7795-119">[**アーカイブ**] まで下方向にスクロールします。</span><span class="sxs-lookup"><span data-stu-id="f7795-119">Scroll down to **Archiving**.</span></span>
    
7. <span data-ttu-id="f7795-120">[**アーカイブ**] で、次の操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="f7795-120">In **Archiving**, do the following:</span></span>
    
   - <span data-ttu-id="f7795-121">別の既存の SQL Server ストアに変更するには、[**SQL Server ストアのアーカイブ**] ドロップダウン リスト ボックスで、次の操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="f7795-121">To change to a different existing SQL Server store, under **Archiving SQL Server store**, in the drop-down list box, do the following:</span></span>
    
   - <span data-ttu-id="f7795-122">既存の SQL Server ストアを使用するには、ドロップダウン リスト ボックスで、使用する SQL Server ストアの名前をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f7795-122">To use an existing SQL Server store, in the drop-down list box, click the name of the SQL Server store that you want to use.</span></span>
    
   - <span data-ttu-id="f7795-123">新しい SQL Server ストアを定義するには、[**新規**] をクリックし、[**新しい SQL Server ストアの定義**] ダイアログ ボックスで次の操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="f7795-123">To specify a new SQL Server store, click **New**, and then in the **Define New SQL Server store** dialog box, do the following:</span></span>
    
     - <span data-ttu-id="f7795-124">既存の SQL Server ストアを使用するには、ドロップダウン リスト ボックスで、使用する SQL Server ストアの名前をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f7795-124">To use an existing SQL Server store, in the drop-down list box, click the name of the SQL Server store that you want to use.</span></span>
    
     - <span data-ttu-id="f7795-125">新しい SQL Server ストアを指定するには、[**新規**作成] をクリックし、[**新しい sql Server ストアの定義**] ダイアログボックスで、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="f7795-125">To specify a new SQL Server store, click **New**, and then in the **Define New SQL Server Store** dialog box, do the following:</span></span>
    
       - <span data-ttu-id="f7795-126">[ **Sql SERVER fqdn**] で、新しい SQL Server ストアを作成するサーバーの fqdn を指定します。</span><span class="sxs-lookup"><span data-stu-id="f7795-126">In **SQL Server FQDN**, specify the FQDN of the server on which you want to create the new SQL Server store.</span></span>
    
       - <span data-ttu-id="f7795-127">既定のインスタンスを使用するには [**既定のインスタンス**] をクリックし、別のインスタンスを指定するには [**名前付きインスタンス**] をクリックして、使用するインスタンスを指定します。</span><span class="sxs-lookup"><span data-stu-id="f7795-127">Either click **Default Instance** to use the default instance, or, to specify a different instance, click **Named instance**, and then specify the instance you want to use.</span></span>
    
       - <span data-ttu-id="f7795-128">指定した SQL Server インスタンスがミラーリング関係にある場合は、[**この sql インスタンスがミラーリング**関係] チェックボックスをオンにし、[**ミラーポート番号**] でポート番号を指定します。</span><span class="sxs-lookup"><span data-stu-id="f7795-128">If the specified SQL Server instance is in a mirroring relationship, select the **This SQL instance is in mirroring relation** check box, and then, in **Mirror port number**, specify the port number.</span></span>
    
   - <span data-ttu-id="f7795-129">ミラーリング用に SQL Server ストアを追加するか、SQL Server ストア ミラーリングとして別の既存の SQL Server ストアに変更するには、[**SQL Server ストア ミラーリングの有効化**] を選択して、以下の操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="f7795-129">To add SQL Server store for mirroring or change to a different existing SQL Server store for SQL Server store mirroring, select **Enable SQL Server store mirroring**, and then do the following:</span></span>
    
     - <span data-ttu-id="f7795-130">ミラーリング用の既存の SQL Server ストアを使用するには、[**アーカイブ SQL server ストアミラー** ] ドロップダウンリストボックスで、ミラーリングに使用する sql server ストアの名前をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f7795-130">To use an existing SQL Server store for mirroring, in the **Archiving SQL Server store mirror** drop-down list box, click the name of the SQL Server store that you want to use for mirroring.</span></span>
    
     - <span data-ttu-id="f7795-131">ミラーリング用の新しい SQL Server ストアを指定するには、[**新規**作成] をクリックし、[**新しい sql Server ストアの定義**] ダイアログボックスで、次のいずれかの操作を行います。</span><span class="sxs-lookup"><span data-stu-id="f7795-131">To specify a new SQL Server store for mirroring, click **New**, and then in the **Define New SQL Server Store** dialog box, do one of the following:</span></span>
    
       <span data-ttu-id="f7795-132">a.</span><span class="sxs-lookup"><span data-stu-id="f7795-132">a.</span></span> <span data-ttu-id="f7795-133">[ **Sql SERVER fqdn**] で、新しい sql server ストアを作成する sql SERVER の fqdn を指定します。</span><span class="sxs-lookup"><span data-stu-id="f7795-133">In **SQL Server FQDN**, specify the FQDN of the SQL Server on which you want to create the new SQL Server store.</span></span>
    
       <span data-ttu-id="f7795-134">b.</span><span class="sxs-lookup"><span data-stu-id="f7795-134">b.</span></span> <span data-ttu-id="f7795-135">既定のインスタンスを使用するには [**既定のインスタンス**] をクリックし、別のインスタンスを指定するには [**名前付きインスタンス**] をクリックして、使用するインスタンスを指定します。</span><span class="sxs-lookup"><span data-stu-id="f7795-135">Either click **Default Instance** to use the default instance, or, to specify a different instance, click **Named Instance**, and then specify the instance you want to use.</span></span>
    
       <span data-ttu-id="f7795-136">c.</span><span class="sxs-lookup"><span data-stu-id="f7795-136">c.</span></span> <span data-ttu-id="f7795-137">指定した SQL Server インスタンスがミラーリング関係にある場合は、[**この sql インスタンスがミラーリング**関係] チェックボックスをオンにし、[**ミラーポート番号**] でポート番号を指定します。</span><span class="sxs-lookup"><span data-stu-id="f7795-137">If the specified SQL Server instance is in a mirroring relationship, select the **This SQL instance is in mirroring relation** check box, and then, in **Mirror port number**, specify the port number.</span></span>
    
   - <span data-ttu-id="f7795-138">Sql Server のミラーリングを有効にしており、SQL Server ミラーリング監視 (プライマリ SQL Server サーバーの正常性を検出できる別の SQL Server インスタンス) を追加または変更する場合は、[ **Sql server ミラーリング監視を使用する] を選択します。[自動フェールオーバーを有効にする**] チェックボックスをオンにして、次のいずれかの操作を行います。</span><span class="sxs-lookup"><span data-stu-id="f7795-138">If you enable SQL Server mirroring and want to add or change a SQL Server mirroring witness (a third, separate SQL Server instance that can detect the health of the primary SQL Server server and mirror instances), select the **Use SQL Server mirroring witness to enable automatic failover** check box, and then do one of the following:</span></span>
    
      <span data-ttu-id="f7795-139">a.</span><span class="sxs-lookup"><span data-stu-id="f7795-139">a.</span></span> <span data-ttu-id="f7795-140">[ **Sql SERVER fqdn**] で、新しい SQL server ミラーリング監視を作成するサーバーの fqdn を指定します。</span><span class="sxs-lookup"><span data-stu-id="f7795-140">In **SQL Server FQDN**, specify the FQDN of the server on which you want to create the new SQL Server mirroring witness.</span></span>
    
      <span data-ttu-id="f7795-141">b.</span><span class="sxs-lookup"><span data-stu-id="f7795-141">b.</span></span> <span data-ttu-id="f7795-142">既定のインスタンスを使用するには [**既定のインスタンス**] をクリックし、別のインスタンスを指定するには [**名前付きインスタンス**] をクリックして、ミラーリング監視で使用するインスタンスを指定します。</span><span class="sxs-lookup"><span data-stu-id="f7795-142">Either click **Default Instance** to use the default instance, or, to specify a different instance, click **Named Instance**, and then specify the instance you want to use for the mirroring witness.</span></span>
    
      <span data-ttu-id="f7795-143">c.</span><span class="sxs-lookup"><span data-stu-id="f7795-143">c.</span></span> <span data-ttu-id="f7795-144">指定した SQL Server インスタンスがミラーリング関係にある場合は、[**この sql インスタンスがミラーリング**関係] チェックボックスをオンにし、[**ミラーポート番号**] でポート番号を指定します。</span><span class="sxs-lookup"><span data-stu-id="f7795-144">If the specified SQL Server instance is in a mirroring relationship, select the **This SQL instance is in mirroring relation** check box, and then, in **Mirror port number**, specify the port number.</span></span>
    
   - <span data-ttu-id="f7795-145">Exchange server にアーカイブデータとファイルを保存するために Microsoft Exchange との統合を切り替えるには (展開内のすべてのユーザーが Exchange サーバーに所属している場合)、アーカイブデータベースのすべての情報を削除します。</span><span class="sxs-lookup"><span data-stu-id="f7795-145">To switch to Microsoft Exchange integration to store archiving data and files on Exchange servers (if all users in your deployment are homed on your Exchange servers), delete all information for Archiving databases.</span></span>
    
     > [!IMPORTANT]
     > <span data-ttu-id="f7795-146">Exchange サーバーを使用していない Skype for Business ユーザーがいる場合は、SQL Server ストアの情報を削除しないでください。</span><span class="sxs-lookup"><span data-stu-id="f7795-146">If you have any Skype for Business users who are not homed on Exchange servers, do not delete the SQL Server store information.</span></span> 
  
8. <span data-ttu-id="f7795-147">構成を保存するには、[**OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f7795-147">To save the configuration, click **OK**.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="f7795-148">トポロジビルダーで行った変更は、新しいトポロジを公開するまで有効になりません。</span><span class="sxs-lookup"><span data-stu-id="f7795-148">The changes you make in Topology Builder do not take effect until you publish the new topology.</span></span> <span data-ttu-id="f7795-149">詳細については、「 [Skype For Business Server の既存の展開にアーカイブデータベースを追加する](../../deploy/deploy-archiving/add-archiving-databases.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f7795-149">For details, see [Add archiving databases to an existing deployment in Skype for Business Server](../../deploy/deploy-archiving/add-archiving-databases.md).</span></span> 
  
## <a name="change-the-location-of-the-archiving-database-by-using-windows-powershell"></a><span data-ttu-id="f7795-150">Windows PowerShell を使用したアーカイブ データベースの場所の変更</span><span class="sxs-lookup"><span data-stu-id="f7795-150">Change the location of the Archiving database by using Windows PowerShell</span></span>

<span data-ttu-id="f7795-151">ほとんどの場合は、アーカイブ サーバーをインストールするときに指定されたアーカイブ データベースの場所を変更する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="f7795-151">In most cases, you will not need to change the location of the Archiving database, which is specified when you install Archiving Server.</span></span> <span data-ttu-id="f7795-152">ただし、ハードウェア障害や他の問題が発生した場合は、**Set-CsArchivingServer** コマンドレットを使用して、アーカイブ サーバーが新しいデータベースを参照するように設定できます。</span><span class="sxs-lookup"><span data-stu-id="f7795-152">However, if a hardware failure or other problem should occur, you can point Archiving Server to a new database by using the **Set-CsArchivingServer** cmdlet.</span></span>
  
<span data-ttu-id="f7795-153">次の例では、ArchivingServer: atl-001.contoso.com アーカイブサーバーのアーカイブデータベースの場所を変更します。</span><span class="sxs-lookup"><span data-stu-id="f7795-153">The following example changes the location of the Archiving database for the ArchivingServer:atl-cs-001.contoso.com Archiving Server.</span></span> <span data-ttu-id="f7795-154">この例では、新しいデータベースが ArchivingDatabase:atl-sql-001.contoso.com に置かれます。</span><span class="sxs-lookup"><span data-stu-id="f7795-154">In this example, the new database is located at ArchivingDatabase:atl-sql-001.contoso.com:</span></span>
  
```
Set-CsArchivingServer -Identity "ArchivingServer:atl-cs-001.contoso.com" -ArchivingDatabase "ArchivingDatabase:atl-sql-001.contoso.com"
```


