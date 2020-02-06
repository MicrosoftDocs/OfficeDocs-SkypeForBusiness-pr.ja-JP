---
title: Skype for Business Server で監視ストアをフロントエンドプールに関連付ける
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: d3a20d5e-3f24-4cff-bc9b-4f84fea30e6b
description: '概要: Skype for Business Server で使用される監視ストアにフロントエンドプールを関連付ける方法について説明します。'
ms.openlocfilehash: 26d846ad533c5ea49fa371cfa4fedab24bf56307
ms.sourcegitcommit: b1229ed5dc25a04e56aa02aab8ad3d4209559d8f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2020
ms.locfileid: "41790045"
---
# <a name="associate-a-monitoring-store-with-a-front-end-pool-in-skype-for-business-server"></a><span data-ttu-id="fe44b-103">Skype for Business Server で監視ストアをフロントエンドプールに関連付ける</span><span class="sxs-lookup"><span data-stu-id="fe44b-103">Associate a monitoring store with a Front End pool in Skype for Business Server</span></span> 
<span data-ttu-id="fe44b-104">**概要:** フロントエンドプールを、Skype for Business Server で使用される監視ストアに関連付ける方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="fe44b-104">**Summary:** Learn how to associate Front End pools with a monitoring store used by Skype for Business Server.</span></span>
  
<span data-ttu-id="fe44b-105">Skype for Business Server では、監視ストアに関連付けられているフロントエンドプールでのみデータを収集できます。通常、トポロジビルダーでフロントエンドプールを定義すると、タスクが実行されます。</span><span class="sxs-lookup"><span data-stu-id="fe44b-105">In Skype for Business Server, monitoring data can only be collected on Front End pools that have been associated with a monitoring store, a task typically carried out when you define a Front End pool in Topology Builder.</span></span>
  
## <a name="associate-a-monitoring-store-with-a-front-end-pool"></a><span data-ttu-id="fe44b-106">フロントエンド プールへの監視ストアの関連付け</span><span class="sxs-lookup"><span data-stu-id="fe44b-106">Associate a monitoring store with a Front End pool</span></span>

 <span data-ttu-id="fe44b-p101">監視ストアを新しいフロントエンド プールに関連付けるには、新しいフロントエンド プールの定義ウィザードの [**機能の選択**] ページで、[**監視を有効にする (通話詳細記録と QoE 指標ロギング)**] オプションを選択するようにします。このオプションを選択した場合、ウィザードを完了するには SQL ストアも指定する必要があることに注意してください。ただし、このストアはウィザードを実行している時点では存在している必要はありません。つまり、先にプールを監視ストアに関連付けておき、後からそのストアを設定および構成することができます。</span><span class="sxs-lookup"><span data-stu-id="fe44b-p101">To associate a monitoring store with a new Front End pool, make sure that you select the option **Monitoring (call detail recording and logging of quality of experience metrics)** on the **Select Features** page of the Define New Front End Pool wizard. Note that, if you select this option, you must also specify a SQL store in order to complete the wizard; however, this store does not have to exist at the time you run the wizard. That means that you can first associate a pool with a monitoring store, then later setup and configure that store.</span></span>
  
<span data-ttu-id="fe44b-110">また、以下の手順を行うことにより既存のフロントエンド プールを新しいまたは別の監視ストアに関連付けることもできます。</span><span class="sxs-lookup"><span data-stu-id="fe44b-110">Alternatively, you can associate an existing Front End pool with a new or different monitoring store by completing the following procedure:</span></span>
  
1. <span data-ttu-id="fe44b-111">[**スタート**] をクリックし、[**すべてのプログラム**] をクリックし、[ **skype for business server 2015**] をクリックして、[ **skype for business server Topology Builder**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="fe44b-111">Click **Start**, click **All Programs**, click **Skype for Business Server 2015**, and then click **Skype for Business Server Topology Builder**.</span></span>
    
2. <span data-ttu-id="fe44b-112">[**トポロジ ビルダー**] ダイアログ ボックスで、[**既存の展開からトポロジをダウンロードする**] を選択して [**OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="fe44b-112">In the **Topology Builder** dialog box, select **Download Topology from existing deployment** and then click **OK**.</span></span>
    
3. <span data-ttu-id="fe44b-p102">[**名前を付けて保存**] ダイアログ ボックスで、現在のトポロジ用のファイル名を入力し、[**保存**] をクリックします。トポロジを保存しておけば、新しいトポロジに問題が発生した場合に保存したトポロジを取得して再公開できます。</span><span class="sxs-lookup"><span data-stu-id="fe44b-p102">In the **Save As** dialog box, enter a file name for your current topology and then click **Save**. The saved topology can later be retrieved and re-published in case there are problems with the new topology.</span></span>
    
4. <span data-ttu-id="fe44b-115">トポロジビルダーで、[ **Skype For Business Server**] を展開し、フロントエンドプールが含まれているサイトの名前を展開して、[ **Enterprise Edition のフロントエンドプール**の展開] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="fe44b-115">In Topology Builder, expand **Skype for Business Server**, expand the name of the site containing the Front End pool, then click expand **Enterprise Edition Front End pools**.</span></span>
    
5. <span data-ttu-id="fe44b-116">監視ストアに関連付けるプールの名前を右クリックし、[**プロパティの編集**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="fe44b-116">Right-click the name of the pool to be associated with the monitoring store and then click **Edit Properties**.</span></span>
    
6. <span data-ttu-id="fe44b-p103">[**プロパティの編集**] ダイアログ ボックスの [**全般**] タブで、[**監視を有効にする (CDR と QoE 指標)**] オプションを選択し、既存の SQL Server データベースを [**監視 SQL Server ストア**] ドロップダウン リストから選択します (または、[**新規**] をクリックしてプールを新しいデータベース ストアに関連付けます)。新しいデータベース ストアを使用するように選択した場合は、[**新しい SQL ストアの定義**] ダイアログ ボックスで、SQL Server コンピューターの完全修飾ドメイン名を [**SQL Server の FQDN**] ボックスに入力します。ストアに既定の SQL Server インスタンスを使用する場合は、[**既定のインスタンス**] を選択します。それ以外の場合は [**名前付きインスタンス**] をクリックし、インスタンス名を [**名前付きインスタンス**] ボックスに入力します。</span><span class="sxs-lookup"><span data-stu-id="fe44b-p103">In the **Edit Properties** dialog box, on the **General** tab, select the option **Monitoring (CDR and QoE metrics)** and then select an existing SQL Server database from the **Monitoring SQL Server store** dropdown list. (Or, click **New** to associate the pool with a new database store.) If you choose to use a new database store then, in the **Define New SQL Store** dialog box, enter the fully qualified domain name of the SQL Server computer in the **Sql Server FQDN** box. If you want to use the default SQL Server instance for that store select **Default Instance**; otherwise select **Named Instance** and enter the instance name in the **Named Instance** box.</span></span>
    
    <span data-ttu-id="fe44b-120">[**プロパティの編集**] ダイアログボックスには、監視データベースの SQL ミラーを作成するオプションも表示されます (sql mirror では、監視データベースの2つのコピーを保持することができます。1つのコピーを監視用ストアコンピューターと SQL mirror コンピューターに保存します)。</span><span class="sxs-lookup"><span data-stu-id="fe44b-120">The **Edit Properties** dialog box also gives you the option of creating a SQL mirror for your monitoring database (a SQL mirror enables you to maintain two copies of your monitoring database, one copy stored on the monitoring store computer and the other on the SQL mirror computer).</span></span> <span data-ttu-id="fe44b-121">ミラーリングを有効にするに**は、[SQL インスタンスのミラーリング基準**] を選択し、[**ミラーリングポート番号**] ボックスにミラーサーバーのポート番号を入力します。</span><span class="sxs-lookup"><span data-stu-id="fe44b-121">To enable mirroring, select T **his SQL instance is in mirroring relation** and enter the port number for the mirror server in the **Mirroring port number** box.</span></span>
    
7. <span data-ttu-id="fe44b-122">[**プロパティの編集**] ダイアログ ボックスで、[**OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="fe44b-122">In the **Edit Properties** dialog box, click **OK**.</span></span>
    
<span data-ttu-id="fe44b-123">監視ストアをフロントエンドプールに関連付けると、変更が反映される前に新しいトポロジを公開する必要があります。</span><span class="sxs-lookup"><span data-stu-id="fe44b-123">After associating the monitoring store with a Front End pool you must publish the new topology before the changes take effect.</span></span> <span data-ttu-id="fe44b-124">新しいトポロジを公開するには、「トポロジビルダー」で次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="fe44b-124">To publish your new topology, complete the following steps in Topology Builder:</span></span>
  
1. <span data-ttu-id="fe44b-125">[**アクション**] をクリックし、[**トポロジ**] をポイントし、[**公開**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="fe44b-125">Click **Action**, point to **Topology**, and then click **Publish**.</span></span>
    
2. <span data-ttu-id="fe44b-126">トポロジの公開ウィザードの [**トポロジの公開**] ページで、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="fe44b-126">In the Publish Topology wizard, on the **Publish the topology** page, click **Next**.</span></span>
    
3. <span data-ttu-id="fe44b-127">[**公開ウィザードの完了**] ページで、[**完了**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="fe44b-127">On the **Publishing wizard complete** page, click **Finish**.</span></span>
    
<span data-ttu-id="fe44b-128">トポロジが公開されたら、監視ストアをホストするコンピューターに監視データベースをインストールします。</span><span class="sxs-lookup"><span data-stu-id="fe44b-128">After the topology has been published you can then install the monitoring database on the computer that will host the monitoring store.</span></span> <span data-ttu-id="fe44b-129">監視データベースは、Skype for Business Server 管理シェルと Windows PowerShell を使用してインストールできます。</span><span class="sxs-lookup"><span data-stu-id="fe44b-129">The monitoring database can be installed by using the Skype for Business Server Management Shell and Windows PowerShell.</span></span> <span data-ttu-id="fe44b-130">データベースをローカルにインストールする (つまり、Skype for Business Server 管理シェルを実行しているコンピューターと同じコンピューターにデータベースをインストールする) には、適切なコンピューター上で管理シェルを起動し、次のコマンドを入力して、ENTER キーを押します。</span><span class="sxs-lookup"><span data-stu-id="fe44b-130">To install the database locally (that is, to install the database on the same computer where you are running the Skype for Business Server Management Shell), start the Management Shell on the appropriate computer, then type in the following command and press ENTER:</span></span>
  
```powershell
Install-CsDatabase -LocalDatabases
```

<span data-ttu-id="fe44b-131">上のコマンドを実行する場合は、現在の Skype for Business Server のトポロジを参照して、ローカルコンピューターにインストールする必要があるデータベースを特定し、自動的にそれらのデータベースをインストールして構成します。</span><span class="sxs-lookup"><span data-stu-id="fe44b-131">When you run the preceding command, Install-CsDatabase will read the current Skype for Business Server topology, determine which databases need to be installed on the local computer, and then automatically install and configure each of those databases.</span></span>
  
<span data-ttu-id="fe44b-132">データベースをリモート コンピューター (管理シェルを実行するコンピューターとは別のコンピューター) にインストールする場合は、少なくとも 2 つのパラメーター (ConfiguredDatabases パラメーターと SqlServerFqdn パラメーター) を含める必要があります。</span><span class="sxs-lookup"><span data-stu-id="fe44b-132">To install the database on a remote computer (that is, a computer other than the computer where the Management Shell is running) you must include at least two parameters: the ConfiguredDatabases parameter and the SqlServerFqdn parameter.</span></span> <span data-ttu-id="fe44b-133">これらのパラメーターは、SqlServerFqdn パラメーターによって指定されたコンピューターに、Skype for Business Server トポロジを取得して必要なデータベースをインストールして構成するための Install Database コマンドレットを指定します。</span><span class="sxs-lookup"><span data-stu-id="fe44b-133">These parameters tell the Install-CsDatabase cmdlet to retrieve the Skype for Business Server topology and then install and configure the required databases on the computer specified by the SqlServerFqdn parameter.</span></span> <span data-ttu-id="fe44b-134">SqlServerFqdn パラメーターには、データベースのインストール先となるコンピューターの完全修飾ドメイン名を表すパラメーター値を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="fe44b-134">The SqlServerFqdn parameter must use a parameter value representing the fully qualified domain name of the computer where the databases are to be installed.</span></span>
  
<span data-ttu-id="fe44b-135">たとえば、次のコマンドは監視データベースを atl-sql-001.litwareinc.com というコンピューターにインストールします。</span><span class="sxs-lookup"><span data-stu-id="fe44b-135">For example, this command installs the monitoring database on the computer atl-sql-001.litwareinc.com:</span></span>
  
```powershell
Install-CsDatabase -ConfiguredDatabases -SqlServerFqdn atl-sql-001.litwareinc.com
```

<span data-ttu-id="fe44b-136">または、監視ストアをホストするコンピューターで Skype for Business Server 展開ウィザードを実行して、監視データベースをインストールすることもできます。</span><span class="sxs-lookup"><span data-stu-id="fe44b-136">Alternatively, you can install the monitoring database by running the Skype for Business Server Deployment Wizard on the computer that will host the monitoring store.</span></span> <span data-ttu-id="fe44b-137">このためには、該当のコンピューターにログオンし、以下の手順を行います。</span><span class="sxs-lookup"><span data-stu-id="fe44b-137">To do this, log on to the appropriate computer and complete the following procedure:</span></span>
  
1. <span data-ttu-id="fe44b-138">[**スタート**] をクリックし、[**すべてのプログラム**] をクリックし、[ **skype for business server 2015**] をクリックして、[ **skype for business server Deployment ウィザード**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="fe44b-138">Click **Start**, click **All Programs**, click **Skype for Business Server 2015**, and then click **Skype for Business Server Deployment Wizard**.</span></span>
    
2. <span data-ttu-id="fe44b-139">展開ウィザードで、[ **Skype For Business Server システムのインストールまたは更新**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="fe44b-139">In the Deployment Wizard, click **Install or Update Skype for Business Server System**.</span></span>
    
3. <span data-ttu-id="fe44b-140">[**展開**] ページの [**ステップ 2: Skype For business Server コンポーネントのセットアップまたは削除**] で、[実行] を**もう一度**クリックします。</span><span class="sxs-lookup"><span data-stu-id="fe44b-140">On the **Deploy** page, under **Step 2: Setup or Remove Skype for Business Server Components**, click **Run Again**.</span></span>
    
4. <span data-ttu-id="fe44b-141">Skype for Business Server コンポーネントのセットアップウィザードの [ **skype For Business server コンポーネントのセットアップ**] ページで、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="fe44b-141">In the Setup Skype for Business Server components wizard, on the **Setup Skype for Business Server components** page, click **Next**.</span></span>
    
5. <span data-ttu-id="fe44b-142">[ **MSIs へのパスの指定**] ページで、ファイル ocscore .Msi (Skype For business Server インストールメディアに含まれているファイル) へのパスを入力し、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="fe44b-142">On the **Specify path to MSIs** page, type the path to the file Ocscore.msi (a file included with your Skype for Business Server installation media) and then click **Next**.</span></span>
    
6. <span data-ttu-id="fe44b-143">[**コマンドを実行しています**] ページで、[**完了**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="fe44b-143">On the **Executing Commands** page, click **Finish**.</span></span>
    
<span data-ttu-id="fe44b-144">必要なすべての Skype for Business Server サービスが開始されるようにするには、[**展開**] ページで [サービスを開始する] の順にクリックして、[**実行**] をクリックし**ます。**</span><span class="sxs-lookup"><span data-stu-id="fe44b-144">To ensure that all the required Skype for Business Server services have started, click **Run** under the heading **Step 4: Start Services** on the **Deploy** page</span></span>
  

