---
title: Skype for Business Server 2015 での監視ストアとフロントエンド プールの関連付け
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 9/1/2016
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: d3a20d5e-3f24-4cff-bc9b-4f84fea30e6b
description: '概要: ビジネス サーバー 2015 の Skype で使用される監視ストアがフロント エンド プールに関連付ける方法を説明します。'
ms.openlocfilehash: 6706185264df4220b723f72c0863f11d84e2dc05
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/28/2018
---
# <a name="associate-a-monitoring-store-with-a-front-end-pool-in-skype-for-business-server-2015"></a><span data-ttu-id="a6301-103">Skype for Business Server 2015 での監視ストアとフロントエンド プールの関連付け</span><span class="sxs-lookup"><span data-stu-id="a6301-103">Associate a monitoring store with a Front End pool in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="a6301-104">**の概要:**ビジネス サーバー 2015 の Skype で使用される監視ストアがフロント エンド プールに関連付ける方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="a6301-104">**Summary:** Learn how to associate Front End pools with a monitoring store used by Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="a6301-105">ビジネス サーバー 2015 の Skype での監視データのみを収集できます監視ストア、トポロジ ビルダーでは、フロント エンド プールを定義するときに通常実行されるタスクに関連付けられているフロント エンド プールに。</span><span class="sxs-lookup"><span data-stu-id="a6301-105">In Skype for Business Server 2015, monitoring data can only be collected on Front End pools that have been associated with a monitoring store, a task typically carried out when you define a Front End pool in Topology Builder.</span></span>
  
## <a name="associate-a-monitoring-store-with-a-front-end-pool"></a><span data-ttu-id="a6301-106">フロントエンド プールへの監視ストアの関連付け</span><span class="sxs-lookup"><span data-stu-id="a6301-106">Associate a monitoring store with a Front End pool</span></span>

 <span data-ttu-id="a6301-p101">監視ストアを新しいフロントエンド プールに関連付けるには、新しいフロントエンド プールの定義ウィザードの [**機能の選択**] ページで、[**監視を有効にする (通話詳細記録と QoE 指標ロギング)**] オプションを選択するようにします。このオプションを選択した場合、ウィザードを完了するには SQL ストアも指定する必要があることに注意してください。ただし、このストアはウィザードを実行している時点では存在している必要はありません。つまり、先にプールを監視ストアに関連付けておき、後からそのストアを設定および構成することができます。</span><span class="sxs-lookup"><span data-stu-id="a6301-p101">To associate a monitoring store with a new Front End pool, make sure that you select the option **Monitoring (call detail recording and logging of quality of experience metrics)** on the **Select Features** page of the Define New Front End Pool wizard. Note that, if you select this option, you must also specify a SQL store in order to complete the wizard; however, this store does not have to exist at the time you run the wizard. That means that you can first associate a pool with a monitoring store, then later setup and configure that store.</span></span>
  
<span data-ttu-id="a6301-110">また、以下の手順を行うことにより既存のフロントエンド プールを新しいまたは別の監視ストアに関連付けることもできます。</span><span class="sxs-lookup"><span data-stu-id="a6301-110">Alternatively, you can associate an existing Front End pool with a new or different monitoring store by completing the following procedure:</span></span>
  
1. <span data-ttu-id="a6301-111">[**スタート**] ボタン [**すべてのプログラム**] をクリックして、**ビジネス サーバー 2015 の Skype**を**Skype**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a6301-111">Click **Start**, click **All Programs**, click **Skype for Business Server 2015**, and then click **Skype for Business Server Topology Builder**.</span></span>
    
2. <span data-ttu-id="a6301-112">[**トポロジ ビルダー**] ダイアログ ボックスで、[**既存の展開からトポロジをダウンロードする**] を選択して [**OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a6301-112">In the **Topology Builder** dialog box, select **Download Topology from existing deployment** and then click **OK**.</span></span>
    
3. <span data-ttu-id="a6301-p102">[**名前を付けて保存**] ダイアログ ボックスで、現在のトポロジ用のファイル名を入力し、[**保存**] をクリックします。トポロジを保存しておけば、新しいトポロジに問題が発生した場合に保存したトポロジを取得して再公開できます。</span><span class="sxs-lookup"><span data-stu-id="a6301-p102">In the **Save As** dialog box, enter a file name for your current topology and then click **Save**. The saved topology can later be retrieved and re-published in case there are problems with the new topology.</span></span>
    
4. <span data-ttu-id="a6301-115">トポロジ ビルダーでは、 **Skype**を展開し、フロント エンド プールが含まれているサイトの名前を展開し、**エンタープライズ エディションのフロント エンド プール**を展開する] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a6301-115">In Topology Builder, expand **Skype for Business Server**, expand the name of the site containing the Front End pool, then click expand **Enterprise Edition Front End pools**.</span></span>
    
5. <span data-ttu-id="a6301-116">監視ストアに関連付けるプールの名前を右クリックし、[**プロパティの編集**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a6301-116">Right-click the name of the pool to be associated with the monitoring store and then click **Edit Properties**.</span></span>
    
6. <span data-ttu-id="a6301-p103">[**プロパティの編集**] ダイアログ ボックスの [**全般**] タブで、[**監視を有効にする (CDR と QoE 指標)**] オプションを選択し、既存の SQL Server データベースを [**監視 SQL Server ストア**] ドロップダウン リストから選択します (または、[**新規**] をクリックしてプールを新しいデータベース ストアに関連付けます)。新しいデータベース ストアを使用するように選択した場合は、[**新しい SQL ストアの定義**] ダイアログ ボックスで、SQL Server コンピューターの完全修飾ドメイン名を [**SQL Server の FQDN**] ボックスに入力します。ストアに既定の SQL Server インスタンスを使用する場合は、[**既定のインスタンス**] を選択します。それ以外の場合は [**名前付きインスタンス**] をクリックし、インスタンス名を [**名前付きインスタンス**] ボックスに入力します。</span><span class="sxs-lookup"><span data-stu-id="a6301-p103">In the **Edit Properties** dialog box, on the **General** tab, select the option **Monitoring (CDR and QoE metrics)** and then select an existing SQL Server database from the **Monitoring SQL Server store** dropdown list. (Or, click **New** to associate the pool with a new database store.) If you choose to use a new database store then, in the **Define New SQL Store** dialog box, enter the fully qualified domain name of the SQL Server computer in the **Sql Server FQDN** box. If you want to use the default SQL Server instance for that store select **Default Instance**; otherwise select **Named Instance** and enter the instance name in the **Named Instance** box.</span></span>
    
    <span data-ttu-id="a6301-120">**プロパティの編集**] ダイアログ ボックスするオプションも、監視データベースの SQL ミラーを作成する (SQL ミラーを使用すると、監視データベース、監視に格納されている 1 つのコピーのコピーが 2 つのコンピューターと他を格納するを維持するために、SQL ミラー コンピューター)。</span><span class="sxs-lookup"><span data-stu-id="a6301-120">The **Edit Properties** dialog box also gives you the option of creating a SQL mirror for your monitoring database (a SQL mirror enables you to maintain two copies of your monitoring database, one copy stored on the monitoring store computer and the other on the SQL mirror computer).</span></span> <span data-ttu-id="a6301-121">ミラーリングを有効にするには、T の**関係をミラーリングでは彼の SQL インスタンス**を選択し、**ミラーリング ポート番号**] ボックスで、ミラー ・ サーバのポート番号を入力します。</span><span class="sxs-lookup"><span data-stu-id="a6301-121">To enable mirroring, select T **his SQL instance is in mirroring relation** and enter the port number for the mirror server in the **Mirroring port number** box.</span></span>
    
7. <span data-ttu-id="a6301-122">[**プロパティの編集**] ダイアログ ボックスで、[**OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a6301-122">In the **Edit Properties** dialog box, click **OK**.</span></span>
    
<span data-ttu-id="a6301-123">フロント エンド プールと監視ストアを関連付けると、変更を有効にするために新しいトポロジを公開しなければなりません。</span><span class="sxs-lookup"><span data-stu-id="a6301-123">After associating the monitoring store with a Front End pool you must publish the new topology before the changes take effect.</span></span> <span data-ttu-id="a6301-124">新しいトポロジを公開するには、トポロジ ビルダーで次の手順を行います。</span><span class="sxs-lookup"><span data-stu-id="a6301-124">To publish your new topology, complete the following steps in Topology Builder:</span></span>
  
1. <span data-ttu-id="a6301-125">[**アクション**] をクリックし、[**トポロジ**] をポイントし、[**公開**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a6301-125">Click **Action**, point to **Topology**, and then click **Publish**.</span></span>
    
2. <span data-ttu-id="a6301-126">トポロジの公開ウィザードの [**トポロジの公開**] ページで、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a6301-126">In the Publish Topology wizard, on the **Publish the topology** page, click **Next**.</span></span>
    
3. <span data-ttu-id="a6301-127">[**公開ウィザードの完了**] ページで、[**完了**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a6301-127">On the **Publishing wizard complete** page, click **Finish**.</span></span>
    
<span data-ttu-id="a6301-128">トポロジが公開されたら、監視ストアをホストするコンピューターに監視データベースをインストールします。</span><span class="sxs-lookup"><span data-stu-id="a6301-128">After the topology has been published you can then install the monitoring database on the computer that will host the monitoring store.</span></span> <span data-ttu-id="a6301-129">ビジネス サーバー管理シェルは、Windows PowerShell は、Skype を使用して監視データベースをインストールすることができます。</span><span class="sxs-lookup"><span data-stu-id="a6301-129">The monitoring database can be installed by using the Skype for Business Server Management Shell and Windows PowerShell.</span></span> <span data-ttu-id="a6301-130">ローカル データベースをインストールする (つまり、ビジネス サーバー管理シェルには、Skype を実行している同じコンピューターにデータベースをインストールするのには) 適切なコンピューターで、管理シェルを起動し、次のコマンドを入力して ENTER キーを押します。</span><span class="sxs-lookup"><span data-stu-id="a6301-130">To install the database locally (that is, to install the database on the same computer where you are running the Skype for Business Server Management Shell), start the Management Shell on the appropriate computer, then type in the following command and press ENTER:</span></span>
  
```
Install-CsDatabase -LocalDatabases
```

<span data-ttu-id="a6301-131">上記のコマンドを実行するとインストール CsDatabase はビジネス サーバー トポロジの現在の Skype、特定のデータベースをローカル コンピューターにインストールされている自動的にインストールし、それらのデータベースのそれぞれを構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a6301-131">When you run the preceding command, Install-CsDatabase will read the current Skype for Business Server topology, determine which databases need to be installed on the local computer, and then automatically install and configure each of those databases.</span></span>
  
<span data-ttu-id="a6301-132">データベースをリモート コンピューター (管理シェルを実行するコンピューターとは別のコンピューター) にインストールする場合は、少なくとも 2 つのパラメーター (ConfiguredDatabases パラメーターと SqlServerFqdn パラメーター) を含める必要があります。</span><span class="sxs-lookup"><span data-stu-id="a6301-132">To install the database on a remote computer (that is, a computer other than the computer where the Management Shell is running) you must include at least two parameters: the ConfiguredDatabases parameter and the SqlServerFqdn parameter.</span></span> <span data-ttu-id="a6301-133">これらのパラメーターは、ビジネス サーバー トポロジの Skype を取得しインストールし、SqlServerFqdn パラメーターで指定されたコンピューターに必要なデータベースを構成するインストール CsDatabase コマンドレットに指示します。</span><span class="sxs-lookup"><span data-stu-id="a6301-133">These parameters tell the Install-CsDatabase cmdlet to retrieve the Skype for Business Server topology and then install and configure the required databases on the computer specified by the SqlServerFqdn parameter.</span></span> <span data-ttu-id="a6301-134">SqlServerFqdn パラメーターには、データベースのインストール先となるコンピューターの完全修飾ドメイン名を表すパラメーター値を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a6301-134">The SqlServerFqdn parameter must use a parameter value representing the fully qualified domain name of the computer where the databases are to be installed.</span></span>
  
<span data-ttu-id="a6301-135">たとえば、次のコマンドは監視データベースを atl-sql-001.litwareinc.com というコンピューターにインストールします。</span><span class="sxs-lookup"><span data-stu-id="a6301-135">For example, this command installs the monitoring database on the computer atl-sql-001.litwareinc.com:</span></span>
  
```
Install-CsDatabase -ConfiguredDatabases -SqlServerFqdn atl-sql-001.litwareinc.com
```

<span data-ttu-id="a6301-136">代わりに、監視ストアをホストするコンピューター上のビジネス サーバーの展開ウィザードの Skype を実行して、監視データベースをインストールできます。</span><span class="sxs-lookup"><span data-stu-id="a6301-136">Alternatively, you can install the monitoring database by running the Skype for Business Server Deployment Wizard on the computer that will host the monitoring store.</span></span> <span data-ttu-id="a6301-137">このためには、該当のコンピューターにログオンし、以下の手順を行います。</span><span class="sxs-lookup"><span data-stu-id="a6301-137">To do this, log on to the appropriate computer and complete the following procedure:</span></span>
  
1. <span data-ttu-id="a6301-138">[**スタート**] ボタン [**すべてのプログラム**] をクリックして、**ビジネス サーバー 2015 の Skype**を**Skype ビジネス サーバーの展開ウィザード**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a6301-138">Click **Start**, click **All Programs**, click **Skype for Business Server 2015**, and then click **Skype for Business Server Deployment Wizard**.</span></span>
    
2. <span data-ttu-id="a6301-139">展開ウィザードで、**サーバーのビジネス システムの更新プログラムの Skype をインストールまたは**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a6301-139">In the Deployment Wizard, click **Install or Update Skype for Business Server System**.</span></span>
    
3. <span data-ttu-id="a6301-140">[**展開**] ページで、[**手順 2: セットアップまたは削除の Skype ビジネス サーバー コンポーネントの**、[**再実行**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a6301-140">On the **Deploy** page, under **Step 2: Setup or Remove Skype for Business Server Components**, click **Run Again**.</span></span>
    
4. <span data-ttu-id="a6301-141">**ビジネス サーバー コンポーネントのセットアップ Skype** ] ページで、ビジネスのサーバー コンポーネント ウィザードのセットアップの Skype では、**次**のようにクリックします。</span><span class="sxs-lookup"><span data-stu-id="a6301-141">In the Setup Skype for Business Server components wizard, on the **Setup Skype for Business Server components** page, click **Next**.</span></span>
    
5. <span data-ttu-id="a6301-142">**Msi へのパスの指定**] ページで、Ocscore.msi (ファイルの場合、Skype をビジネスのサーバーのインストール メディアに含まれている) ファイルへのパスを入力し、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a6301-142">On the **Specify path to MSIs** page, type the path to the file Ocscore.msi (a file included with your Skype for Business Server installation media) and then click **Next**.</span></span>
    
6. <span data-ttu-id="a6301-143">[**コマンドを実行しています**] ページで、[**完了**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a6301-143">On the **Executing Commands** page, click **Finish**.</span></span>
    
<span data-ttu-id="a6301-144">ビジネス サーバー サービスに必要なすべての Skype が起動していることを確認するをクリックして**実行**] の下**ステップ 4: サービスを開始**、[**配置**] ページ</span><span class="sxs-lookup"><span data-stu-id="a6301-144">To ensure that all the required Skype for Business Server services have started, click **Run** under the heading **Step 4: Start Services** on the **Deploy** page</span></span>
  

