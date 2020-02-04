---
title: 'Lync Server 2013: 監視ストアとフロントエンドプールの関連付け'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Associating a monitoring store with a Front End pool
ms:assetid: d3a20d5e-3f24-4cff-bc9b-4f84fea30e6b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205271(v=OCS.15)
ms:contentKeyID: 48185439
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 06cc3c85911b7581117a475d1e390aafdf760ca1
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41722767"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="associating-a-monitoring-store-with-a-front-end-pool-in-lync-server-2013"></a><span data-ttu-id="62501-102">Lync Server 2013 での監視ストアとフロントエンドプールの関連付け</span><span class="sxs-lookup"><span data-stu-id="62501-102">Associating a monitoring store with a Front End pool in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="62501-103">_**最終更新日:** 2013-04-22_</span><span class="sxs-lookup"><span data-stu-id="62501-103">_**Topic Last Modified:** 2013-04-22_</span></span>

<span data-ttu-id="62501-104">Microsoft Lync Server 2013 の監視データは、監視ストアに関連付けられているフロントエンドプールでのみ収集できます。通常は、「トポロジビルダーでのフロントエンドプールの定義」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="62501-104">In Microsoft Lync Server 2013 monitoring data can only be collected on Front End pools that have been associated with a monitoring store, a task typically carried out you define a Front End pool in Topology Builder.</span></span> <span data-ttu-id="62501-105">新しいフロントエンドプールを使って監視ストアを関連付けるには、[新しいフロントエンドプールの定義] ウィザードの **[機能の選択**] ページで、[**監視 (通話の詳細記録と音質の記録)** ] を選択していることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="62501-105">To associate a monitoring store with a new Front End pool, make sure that you select the option **Monitoring (call detail recording and logging of quality of experience metrics)** on the **Select Features** page of the Define New Front End Pool wizard.</span></span> <span data-ttu-id="62501-106">このオプションを選択した場合は、ウィザードを完了するために SQL ストアも指定する必要があることに注意してください。ただし、ウィザードを実行するときに、このストアが存在する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="62501-106">Note that, if you select this option, you must also specify a SQL store in order to complete the wizard; however, this store does not have to exist at the time you run the wizard.</span></span> <span data-ttu-id="62501-107">つまり、最初にプールを監視ストアに関連付けて、後でセットアップして、そのストアを構成することができます。</span><span class="sxs-lookup"><span data-stu-id="62501-107">That means that you can first associate a pool with a monitoring store, then later setup and configure that store.</span></span>

<span data-ttu-id="62501-108">また、以下の手順を行うことにより既存のフロントエンド プールを新しいまたは別の監視ストアに関連付けることもできます。</span><span class="sxs-lookup"><span data-stu-id="62501-108">Alternatively, you can associate an existing Front End pool with a new or different monitoring store by completing the following procedure:</span></span>

1.  <span data-ttu-id="62501-109">[**スタート**] をクリックし、[**すべてのプログラム**]、[ **Microsoft Lync Server 2013**]、[ **lync server Topology Builder**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="62501-109">Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Topology Builder**.</span></span>

2.  <span data-ttu-id="62501-110">[**トポロジ ビルダー**] ダイアログ ボックスで、[**既存の展開からトポロジをダウンロードする**] を選択して [**OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="62501-110">In the **Topology Builder** dialog box, select **Download Topology from existing deployment** and then click **OK**.</span></span>

3.  <span data-ttu-id="62501-p102">[**名前を付けて保存**] ダイアログ ボックスで、現在のトポロジ用のファイル名を入力し、[**保存**] をクリックします。トポロジを保存しておけば、新しいトポロジに問題が発生した場合に保存したトポロジを取得して再公開できます。</span><span class="sxs-lookup"><span data-stu-id="62501-p102">In the **Save As** dialog box, enter a file name for your current topology and then click **Save**. The saved topology can later be retrieved and re-published in case there are problems with the new topology.</span></span>

4.  <span data-ttu-id="62501-113">[トポロジビルダー] で、[ **Lync Server 2013**] を展開し、フロントエンドプールが含まれているサイトの名前を展開して、[ **Enterprise Edition のフロントエンドプール**の展開] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="62501-113">In Topology Builder, expand **Lync Server 2013**, expand the name of the site containing the Front End pool, then click expand **Enterprise Edition Front End pools**.</span></span>

5.  <span data-ttu-id="62501-114">監視ストアに関連付けるプールの名前を右クリックし、[**プロパティの編集**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="62501-114">Right-click the name of the pool to be associated with the monitoring store and then click **Edit Properties**.</span></span>

6.  <span data-ttu-id="62501-p103">[**プロパティの編集**] ダイアログ ボックスの [**全般**] タブで、[**監視を有効にする (CDR と QoE 指標)**] オプションを選択し、既存の SQL Server データベースを [**監視 SQL Server ストア**] ドロップダウン リストから選択します (または、[**新規**] をクリックしてプールを新しいデータベース ストアに関連付けます)。新しいデータベース ストアを使用するように選択した場合は、[**新しい SQL ストアの定義**] ダイアログ ボックスで、SQL Server コンピューターの完全修飾ドメイン名を [**SQL Server の FQDN**] ボックスに入力します。ストアに既定の SQL Server インスタンスを使用する場合は、[**既定のインスタンス**] を選択します。それ以外の場合は [**名前付きインスタンス**] をクリックし、インスタンス名を [**名前付きインスタンス**] ボックスに入力します。</span><span class="sxs-lookup"><span data-stu-id="62501-p103">In the **Edit Properties** dialog box, on the **General** tab, select the option **Monitoring (CDR and QoE metrics)** and then select an existing SQL Server database from the **Monitoring SQL Server store** dropdown list. (Or, click **New** to associate the pool with a new database store.) If you choose to use a new database store then, in the **Define New SQL Store** dialog box, enter the fully qualified domain name of the SQL Server computer in the **Sql Server FQDN** box. If you want to use the default SQL Server instance for that store select **Default Instance**; otherwise select **Named Instance** and enter the instance name in the **Named Instance** box.</span></span>
    
    <span data-ttu-id="62501-p104">[**プロパティの編集**] ダイアログ ボックスでは、監視データベースの SQL ミラーを作成するオプションを指定することもできます (SQL ミラーでは、監視データベースの 2 つのコピーを保持できます。1 つのコピーは監視ストア コンピューターに保管され、もう 1 つは SQL ミラー コンピューターに保管されます)。ミラーリングを有効にするには、[**この SQL インスタンスはミラーリングの関係にある**] を選択し、ミラー サーバーのポート番号を [**ミラー ポート番号**] ボックスに入力します。</span><span class="sxs-lookup"><span data-stu-id="62501-p104">The **Edit Properties** dialog box also gives you the option of creating a SQL mirror for your monitoring database (a SQL mirror enables you to maintain two copies of your monitoring database, one copy stored on the monitoring store computer and the other on the SQL mirror computer). To enable mirroring, select T**his SQL instance is in mirroring relation** and enter the port number for the mirror server in the **Mirroring port number** box.</span></span>

7.  <span data-ttu-id="62501-120">[**プロパティの編集**] ダイアログ ボックスで、[**OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="62501-120">In the **Edit Properties** dialog box, click **OK**.</span></span>

<span data-ttu-id="62501-121">監視ストアをフロントエンドプールに関連付けると、変更が反映される前に新しいトポロジを公開する必要があります。</span><span class="sxs-lookup"><span data-stu-id="62501-121">After associating the monitoring store with a Front End pool you must publish the new topology before the changes take effect.</span></span> <span data-ttu-id="62501-122">新しいトポロジを公開するには、「トポロジビルダー」で次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="62501-122">To publish your new topology, complete the following steps in Topology Builder:</span></span>

1.  <span data-ttu-id="62501-123">[**アクション**] をクリックし、[**トポロジ**] をポイントし、[**公開**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="62501-123">Click **Action**, point to **Topology**, and then click **Publish**.</span></span>

2.  <span data-ttu-id="62501-124">トポロジの公開ウィザードの [**トポロジの公開**] ページで、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="62501-124">In the Publish Topology wizard, on the **Publish the topology** page, click **Next**.</span></span>

3.  <span data-ttu-id="62501-125">[**公開ウィザードの完了**] ページで、[**完了**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="62501-125">On the **Publishing wizard complete** page, click **Finish**.</span></span>

<span data-ttu-id="62501-126">トポロジが公開されたら、監視ストアをホストするコンピューターに監視データベースをインストールします。</span><span class="sxs-lookup"><span data-stu-id="62501-126">After the topology has been published you can then install the monitoring database on the computer that will host the monitoring store.</span></span> <span data-ttu-id="62501-127">監視データベースは、Lync Server 管理シェルと Windows PowerShell を使用してインストールできます。</span><span class="sxs-lookup"><span data-stu-id="62501-127">The monitoring database can be installed by using the Lync Server Management Shell and Windows PowerShell.</span></span> <span data-ttu-id="62501-128">データベースをローカルにインストールするには (つまり、Lync Server 管理シェルを実行しているコンピューターと同じコンピューターにデータベースをインストールするには)、適切なコンピューター上で管理シェルを起動し、次のコマンドを入力して、ENTER キーを押します。</span><span class="sxs-lookup"><span data-stu-id="62501-128">To install the database locally (that is, to install the database on the same computer where you are running the Lync Server Management Shell), start the Management Shell on the appropriate computer, then type in the following command and press ENTER:</span></span>

    Install-CsDatabase -LocalDatabases

<span data-ttu-id="62501-129">上のコマンドを実行すると、現在の Lync Server のトポロジが読み込まれ、ローカルコンピューターにインストールする必要があるデータベースが特定され、各データベースが自動的にインストールされて構成されます。</span><span class="sxs-lookup"><span data-stu-id="62501-129">When you run the preceding command, Install-CsDatabase will read the current Lync Server topology, determine which databases need to be installed on the local computer, and then automatically install and configure each of those databases.</span></span>

<span data-ttu-id="62501-130">データベースをリモート コンピューター (管理シェルを実行するコンピューターとは別のコンピューター) にインストールする場合は、少なくとも 2 つのパラメーター (ConfiguredDatabases パラメーターと SqlServerFqdn パラメーター) を含める必要があります。</span><span class="sxs-lookup"><span data-stu-id="62501-130">To install the database on a remote computer (that is, a computer other than the computer where the Management Shell is running) you must include at least two parameters: the ConfiguredDatabases parameter and the SqlServerFqdn parameter.</span></span> <span data-ttu-id="62501-131">これらのパラメーターは、SqlServerFqdn パラメーターによって指定されたコンピューターに、Lync Server トポロジを取得し、必要なデータベースをインストールして構成するために、CsDatabase コマンドレットを指定します。</span><span class="sxs-lookup"><span data-stu-id="62501-131">These parameters tell the Install-CsDatabase cmdlet to retrieve the Lync Server topology and then install and configure the required databases on the computer specified by the SqlServerFqdn parameter.</span></span> <span data-ttu-id="62501-132">SqlServerFqdn パラメーターには、データベースのインストール先となるコンピューターの完全修飾ドメイン名を表すパラメーター値を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="62501-132">The SqlServerFqdn parameter must use a parameter value representing the fully qualified domain name of the computer where the databases are to be installed.</span></span>

<span data-ttu-id="62501-133">たとえば、次のコマンドは監視データベースを atl-sql-001.litwareinc.com というコンピューターにインストールします。</span><span class="sxs-lookup"><span data-stu-id="62501-133">For example, this command installs the monitoring database on the computer atl-sql-001.litwareinc.com:</span></span>

    Install-CsDatabase -ConfiguredDatabases -SqlServerFqdn atl-sql-001.litwareinc.com

<span data-ttu-id="62501-134">または、監視ストアをホストするコンピューターで Lync Server 展開ウィザードを実行して、監視データベースをインストールすることもできます。</span><span class="sxs-lookup"><span data-stu-id="62501-134">Alternatively, you can install the monitoring database by running the Lync Server Deployment Wizard on the computer that will host the monitoring store.</span></span> <span data-ttu-id="62501-135">このためには、該当のコンピューターにログオンし、以下の手順を行います。</span><span class="sxs-lookup"><span data-stu-id="62501-135">To do this, log on to the appropriate computer and complete the following procedure:</span></span>

1.  <span data-ttu-id="62501-136">[**スタート**] をクリックし、[**すべてのプログラム**] をクリックし、[ **Microsoft Lync server 2013**] をクリックして、[ **Lync server Deployment Wizard**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="62501-136">Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Deployment Wizard**.</span></span>

2.  <span data-ttu-id="62501-137">展開ウィザードで、[ **Lync Server System のインストールまたは更新**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="62501-137">In the Deployment Wizard, click **Install or Update Lync Server System**.</span></span>

3.  <span data-ttu-id="62501-138">[**展開**] ページの [**手順 2: Lync サーバーコンポーネントをセットアップまたは削除**します] で、[実行] を**もう一度**クリックします。</span><span class="sxs-lookup"><span data-stu-id="62501-138">On the **Deploy** page, under **Step 2: Setup or Remove Lync Server Components**, click **Run Again**.</span></span>

4.  <span data-ttu-id="62501-139">Lync Server コンポーネントのセットアップウィザードの [ **Lync server コンポーネント**のセットアップ] ページで、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="62501-139">In the Setup Lync Server components wizard, on the **Setup Lync Server components** page, click **Next**.</span></span>

5.  <span data-ttu-id="62501-140">[ **MSIs へのパスの指定**] ページで、ファイル ocscore .Msi (Lync Server インストールメディアに含まれているファイル) へのパスを入力し、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="62501-140">On the **Specify path to MSIs** page, type the path to the file Ocscore.msi (a file included with your Lync Server installation media) and then click **Next**.</span></span>

6.  <span data-ttu-id="62501-141">[**コマンドを実行しています**] ページで、[**完了**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="62501-141">On the **Executing Commands** page, click **Finish**.</span></span>

<span data-ttu-id="62501-142">必要な Lync Server サービスがすべて開始されていることを確認するには、[**展開**] ページの [サービスの開始] で [**実行**] をクリックし**ます。**</span><span class="sxs-lookup"><span data-stu-id="62501-142">To ensure that all the required Lync Server services have started, click **Run** under the heading **Step 4: Start Services** on the **Deploy** page</span></span>

</div>

<span> </span>

</div>

</div>

</div>

