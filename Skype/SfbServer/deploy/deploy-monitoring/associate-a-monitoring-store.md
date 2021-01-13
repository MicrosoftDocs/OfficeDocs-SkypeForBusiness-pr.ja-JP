---
title: Skype for Business Server のフロントエンド プールに監視ストアを関連付ける
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: d3a20d5e-3f24-4cff-bc9b-4f84fea30e6b
description: '概要: フロントエンド プールを Skype for Business Server で使用される監視ストアに関連付ける方法について学習します。'
ms.openlocfilehash: 4ec48e99da9a827cdc40d87c42ec764bda66a416
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49830547"
---
# <a name="associate-a-monitoring-store-with-a-front-end-pool-in-skype-for-business-server"></a><span data-ttu-id="6095a-103">Skype for Business Server のフロントエンド プールに監視ストアを関連付ける</span><span class="sxs-lookup"><span data-stu-id="6095a-103">Associate a monitoring store with a Front End pool in Skype for Business Server</span></span> 
<span data-ttu-id="6095a-104">**概要:** フロントエンド プールを Skype for Business Server で使用される監視ストアに関連付ける方法について学習します。</span><span class="sxs-lookup"><span data-stu-id="6095a-104">**Summary:** Learn how to associate Front End pools with a monitoring store used by Skype for Business Server.</span></span>
  
<span data-ttu-id="6095a-105">Skype for Business Server では、監視データは、監視ストアに関連付けられているフロントエンド プールでのみ収集できます。タスクは、通常、トポロジ ビルダーでフロントエンド プールを定義するときに実行されます。</span><span class="sxs-lookup"><span data-stu-id="6095a-105">In Skype for Business Server, monitoring data can only be collected on Front End pools that have been associated with a monitoring store, a task typically carried out when you define a Front End pool in Topology Builder.</span></span>
  
## <a name="associate-a-monitoring-store-with-a-front-end-pool"></a><span data-ttu-id="6095a-106">監視ストアをフロントエンド プールに関連付ける</span><span class="sxs-lookup"><span data-stu-id="6095a-106">Associate a monitoring store with a Front End pool</span></span>

 <span data-ttu-id="6095a-107">監視ストアを新しいフロントエンド プールに関連付ける場合は、[新しいフロントエンド プールの定義] ウィザードの [機能の選択] ページで、[監視] (通話詳細記録および Quality **of Experience** 指標のログ) を選択してください。</span><span class="sxs-lookup"><span data-stu-id="6095a-107">To associate a monitoring store with a new Front End pool, make sure that you select the option **Monitoring (call detail recording and logging of quality of experience metrics)** on the **Select Features** page of the Define New Front End Pool wizard.</span></span> <span data-ttu-id="6095a-108">このオプションを選択した場合は、ウィザードを完了するためにSQLストアも指定する必要があります。ただし、このストアはウィザードを実行する時点で存在する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="6095a-108">Note that, if you select this option, you must also specify a SQL store in order to complete the wizard; however, this store does not have to exist at the time you run the wizard.</span></span> <span data-ttu-id="6095a-109">つまり、最初にプールを監視ストアに関連付け、その後、そのストアをセットアップして構成できます。</span><span class="sxs-lookup"><span data-stu-id="6095a-109">That means that you can first associate a pool with a monitoring store, then later setup and configure that store.</span></span>
  
<span data-ttu-id="6095a-110">この他に、以下の手順を行うことにより既存のフロントエンド プールを新しいまたは別の監視ストアに関連付けることもできます。</span><span class="sxs-lookup"><span data-stu-id="6095a-110">Alternatively, you can associate an existing Front End pool with a new or different monitoring store by completing the following procedure:</span></span>
  
1. <span data-ttu-id="6095a-111">[ **スタート] ボタン**、[ **すべての** プログラム] の順にクリックし **、[Skype for Business Server 2015]** をクリックして **、[Skype for Business Server トポロジ ビルダー] をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="6095a-111">Click **Start**, click **All Programs**, click **Skype for Business Server 2015**, and then click **Skype for Business Server Topology Builder**.</span></span>
    
2. <span data-ttu-id="6095a-112">[**トポロジ ビルダー**] ダイアログ ボックスで、[**既存の展開からトポロジをダウンロードする**] を選択して [**OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6095a-112">In the **Topology Builder** dialog box, select **Download Topology from existing deployment** and then click **OK**.</span></span>
    
3. <span data-ttu-id="6095a-p102">[**名前を付けて保存**] ダイアログ ボックスで、現在のトポロジ用のファイル名を入力し、[**保存**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6095a-p102">In the **Save As** dialog box, enter a file name for your current topology and then click **Save**. The saved topology can later be retrieved and re-published in case there are problems with the new topology.</span></span>
    
4. <span data-ttu-id="6095a-115">トポロジ ビルダーで **、[Skype for Business Server]** を展開し、フロントエンド プールを含むサイトの名前を展開し **、[Enterprise Edition** フロントエンド プール] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6095a-115">In Topology Builder, expand **Skype for Business Server**, expand the name of the site containing the Front End pool, then click expand **Enterprise Edition Front End pools**.</span></span>
    
5. <span data-ttu-id="6095a-116">監視ストアに関連付けるプールの名前を右クリックし、[**プロパティの編集**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6095a-116">Right-click the name of the pool to be associated with the monitoring store and then click **Edit Properties**.</span></span>
    
6. <span data-ttu-id="6095a-p103">[**プロパティの編集**] ダイアログ ボックスの [**全般**] タブで、[**監視 (CDR と QoE 指標)**] オプションを選択し、既存の SQL Server データベースを [**監視 SQL Server ストア**] ドロップダウン リストから選択します (または、[**新規**] をクリックしてプールを新しいデータベース ストアに関連付けます。) 新しいデータベース ストアを使用するように選択した場合は、[**新しい SQL ストアの定義**] ダイアログ ボックスで、SQL Server コンピューターの完全修飾ドメイン名を [**SQL Server の FQDN**] ボックスに入力します。ストアに既定の SQL Server インスタンスを使用する場合は、[**既定のインスタンス**] を選択します。それ以外の場合は [**名前付きインスタンス**] をクリックし、インスタンス名を [**名前付きインスタンス**] ボックスに入力します。</span><span class="sxs-lookup"><span data-stu-id="6095a-p103">In the **Edit Properties** dialog box, on the **General** tab, select the option **Monitoring (CDR and QoE metrics)** and then select an existing SQL Server database from the **Monitoring SQL Server store** dropdown list. (Or, click **New** to associate the pool with a new database store.) If you choose to use a new database store then, in the **Define New SQL Store** dialog box, enter the fully qualified domain name of the SQL Server computer in the **Sql Server FQDN** box. If you want to use the default SQL Server instance for that store select **Default Instance**; otherwise select **Named Instance** and enter the instance name in the **Named Instance** box.</span></span>
    
    <span data-ttu-id="6095a-120">[プロパティの編集] ダイアログ ボックスには、監視データベース用の SQL ミラーを作成するオプション (SQL ミラー) を使用すると、監視データベースの 2 つのコピー (1 つは監視ストア コンピューターに格納され、もう 1 つは SQL ミラー コンピューター上) を維持できます。</span><span class="sxs-lookup"><span data-stu-id="6095a-120">The **Edit Properties** dialog box also gives you the option of creating a SQL mirror for your monitoring database (a SQL mirror enables you to maintain two copies of your monitoring database, one copy stored on the monitoring store computer and the other on the SQL mirror computer).</span></span> <span data-ttu-id="6095a-121">ミラーリングを有効にするには、インスタンスがミラーリング関係にある t **SQL** を選択し、[ミラーリングのポート番号] ボックスにミラー サーバーのポート番号 **を入力** します。</span><span class="sxs-lookup"><span data-stu-id="6095a-121">To enable mirroring, select T **his SQL instance is in mirroring relation** and enter the port number for the mirror server in the **Mirroring port number** box.</span></span>
    
7. <span data-ttu-id="6095a-122">[**プロパティの編集**] ダイアログ ボックスで、[**OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6095a-122">In the **Edit Properties** dialog box, click **OK**.</span></span>
    
<span data-ttu-id="6095a-p105">監視ストアをフロントエンド プールに関連付けたら、新しいトポロジを公開する必要があります。これを行うまで変更は有効になりません。新しいトポロジを公開するには、トポロジ ビルダーで以下の手順を行います。</span><span class="sxs-lookup"><span data-stu-id="6095a-p105">After associating the monitoring store with a Front End pool you must publish the new topology before the changes take effect. To publish your new topology, complete the following steps in Topology Builder:</span></span>
  
1. <span data-ttu-id="6095a-125">[**操作**] をクリックし、[**トポロジ**] をポイントし、[**公開**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6095a-125">Click **Action**, point to **Topology**, and then click **Publish**.</span></span>
    
2. <span data-ttu-id="6095a-126">トポロジの公開ウィザードの [**トポロジの公開**] ページで、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6095a-126">In the Publish Topology wizard, on the **Publish the topology** page, click **Next**.</span></span>
    
3. <span data-ttu-id="6095a-127">[**公開ウィザード完了**] ページで、[**完了**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6095a-127">On the **Publishing wizard complete** page, click **Finish**.</span></span>
    
<span data-ttu-id="6095a-128">トポロジが公開されたら、監視ストアをホストするコンピューターに監視データベースをインストールします。</span><span class="sxs-lookup"><span data-stu-id="6095a-128">After the topology has been published you can then install the monitoring database on the computer that will host the monitoring store.</span></span> <span data-ttu-id="6095a-129">監視データベースは、Skype for Business Server 管理シェルと管理シェルを使用してWindows PowerShell。</span><span class="sxs-lookup"><span data-stu-id="6095a-129">The monitoring database can be installed by using the Skype for Business Server Management Shell and Windows PowerShell.</span></span> <span data-ttu-id="6095a-130">データベースをローカルにインストールするには (つまり、Skype for Business Server 管理シェルを実行しているのと同じコンピューターにデータベースをインストールするには)、適切なコンピューターで管理シェルを起動し、次のコマンドを入力して Enter キーを押します。</span><span class="sxs-lookup"><span data-stu-id="6095a-130">To install the database locally (that is, to install the database on the same computer where you are running the Skype for Business Server Management Shell), start the Management Shell on the appropriate computer, then type in the following command and press ENTER:</span></span>
  
```powershell
Install-CsDatabase -LocalDatabases
```

<span data-ttu-id="6095a-131">前のコマンドを実行すると、Install-CsDatabase は現在の Skype for Business Server トポロジを読み取り、ローカル コンピューターにインストールする必要があるデータベースを特定し、それらの各データベースを自動的にインストールして構成します。</span><span class="sxs-lookup"><span data-stu-id="6095a-131">When you run the preceding command, Install-CsDatabase will read the current Skype for Business Server topology, determine which databases need to be installed on the local computer, and then automatically install and configure each of those databases.</span></span>
  
<span data-ttu-id="6095a-132">データベースをリモート コンピューター (管理シェルを実行するコンピューターとは別のコンピューター) にインストールする場合は、少なくとも 2 つのパラメーター (ConfiguredDatabases パラメーターと、SqlServerFqdn パラメーター) を含める必要があります。</span><span class="sxs-lookup"><span data-stu-id="6095a-132">To install the database on a remote computer (that is, a computer other than the computer where the Management Shell is running) you must include at least two parameters: the ConfiguredDatabases parameter and the SqlServerFqdn parameter.</span></span> <span data-ttu-id="6095a-133">これらのパラメーターは、Install-CsDatabase コマンドレットに Skype for Business Server トポロジを取得し、SqlServerFqdn パラメーターで指定されたコンピューターに必要なデータベースをインストールして構成します。</span><span class="sxs-lookup"><span data-stu-id="6095a-133">These parameters tell the Install-CsDatabase cmdlet to retrieve the Skype for Business Server topology and then install and configure the required databases on the computer specified by the SqlServerFqdn parameter.</span></span> <span data-ttu-id="6095a-134">SqlServerFqdn パラメーターには、データベースのインストール先となるコンピューターの完全修飾ドメイン名を表すパラメーター値を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6095a-134">The SqlServerFqdn parameter must use a parameter value representing the fully qualified domain name of the computer where the databases are to be installed.</span></span>
  
<span data-ttu-id="6095a-135">たとえば、次のコマンドは監視データベースを atl-sql-001.litwareinc.com というコンピューターにインストールします。</span><span class="sxs-lookup"><span data-stu-id="6095a-135">For example, this command installs the monitoring database on the computer atl-sql-001.litwareinc.com:</span></span>
  
```powershell
Install-CsDatabase -ConfiguredDatabases -SqlServerFqdn atl-sql-001.litwareinc.com
```

<span data-ttu-id="6095a-136">または、監視ストアをホストするコンピューターで Skype for Business Server 展開ウィザードを実行して、監視データベースをインストールすることもできます。</span><span class="sxs-lookup"><span data-stu-id="6095a-136">Alternatively, you can install the monitoring database by running the Skype for Business Server Deployment Wizard on the computer that will host the monitoring store.</span></span> <span data-ttu-id="6095a-137">このためには、該当のコンピューターにログオンし、以下の手順を行います。</span><span class="sxs-lookup"><span data-stu-id="6095a-137">To do this, log on to the appropriate computer and complete the following procedure:</span></span>
  
1. <span data-ttu-id="6095a-138">[ **スタート] ボタン**、[ **すべての** プログラム] の順にクリックし **、[Skype for Business Server 2015]** をクリックして、[Skype for Business Server 展開ウィザード] **をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="6095a-138">Click **Start**, click **All Programs**, click **Skype for Business Server 2015**, and then click **Skype for Business Server Deployment Wizard**.</span></span>
    
2. <span data-ttu-id="6095a-139">展開ウィザードで **、[Skype for Business Server システムのインストールまたは更新] をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="6095a-139">In the Deployment Wizard, click **Install or Update Skype for Business Server System**.</span></span>
    
3. <span data-ttu-id="6095a-140">[展開 **] ページの** [ **ステップ 2: Skype for Business Server** コンポーネントのセットアップまたは削除] で、[再び実行] **をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="6095a-140">On the **Deploy** page, under **Step 2: Setup or Remove Skype for Business Server Components**, click **Run Again**.</span></span>
    
4. <span data-ttu-id="6095a-141">Skype for Business Server コンポーネントのセットアップ ウィザードの **[Skype for Business Server** コンポーネントのセットアップ] ページで、[次へ] をクリック **します**。</span><span class="sxs-lookup"><span data-stu-id="6095a-141">In the Setup Skype for Business Server components wizard, on the **Setup Skype for Business Server components** page, click **Next**.</span></span>
    
5. <span data-ttu-id="6095a-142">**[MSIs** へのパスの指定] ページで、ファイル Ocscore.msi (Skype for Business Server インストール メディアに含まれるファイル) へのパスを入力し、[次へ] をクリック **します**。</span><span class="sxs-lookup"><span data-stu-id="6095a-142">On the **Specify path to MSIs** page, type the path to the file Ocscore.msi (a file included with your Skype for Business Server installation media) and then click **Next**.</span></span>
    
6. <span data-ttu-id="6095a-143">**[コマンドを実行しています]** ページで、**[完了]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6095a-143">On the **Executing Commands** page, click **Finish**.</span></span>
    
<span data-ttu-id="6095a-144">必要なすべての Skype for Business Server サービスが開始されたのを確認するには、[展開] ページの [ステップ **4:** サービスの開始] という見出しの下にある [実行] を **クリック** します。</span><span class="sxs-lookup"><span data-stu-id="6095a-144">To ensure that all the required Skype for Business Server services have started, click **Run** under the heading **Step 4: Start Services** on the **Deploy** page</span></span>
  

