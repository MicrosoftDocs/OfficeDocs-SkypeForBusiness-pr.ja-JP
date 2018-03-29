---
title: Skype for Business Server 2015 のバックエンド サーバーへの AlwaysOn 可用性グループの展開
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.date: 2/14/2018
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: c93c01e6-626c-40ad-92dd-373b0fe9189f
description: (インストール)、Skype での AlwaysOn 可用性グループ ビジネス サーバーの展開を展開します。
ms.openlocfilehash: 858f8cd317ecccde315475bc6489c74d79bf72c6
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/28/2018
---
# <a name="deploy-an-alwayson-availability-group-on-a-back-end-server-in-skype-for-business-server-2015"></a><span data-ttu-id="27c08-103">Skype for Business Server 2015 のバックエンド サーバーへの AlwaysOn 可用性グループの展開</span><span class="sxs-lookup"><span data-stu-id="27c08-103">Deploy an AlwaysOn Availability Group on a Back End Server in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="27c08-104">(インストール)、Skype での AlwaysOn 可用性グループ ビジネス サーバーの展開を展開します。</span><span class="sxs-lookup"><span data-stu-id="27c08-104">Deploy (install) an AlwaysOn Availability Group in your Skype for Business Server deployment.</span></span>
  
<span data-ttu-id="27c08-105">AlwaysOn 可用性グループを展開する方法は、ことを新しいプール、ミラーリングを使用する既存のプールまたはバックエンド データベースの高可用性がされていない既存のプールに展開するかどうかによって異なります。</span><span class="sxs-lookup"><span data-stu-id="27c08-105">How you deploy an AlwaysOn Availability Group depends on whether you are deploying it in a new pool, an existing pool that uses mirroring, or an existing pool that currently has no high availability for the Back End database.</span></span>
  
> [!NOTE]
> <span data-ttu-id="27c08-106">AlwaysOn 可用性グループを使用して永続的なチャット サーバーの役割ではサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="27c08-106">Using an AlwaysOn Availability Group with a Persistent Chat Server role is not supported.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="27c08-107">AlwaysOn 可用性グループの複数のインスタンスのインスタンス名は同じである必要があります。</span><span class="sxs-lookup"><span data-stu-id="27c08-107">Instance names for multiple AlwaysOn Availability Group instances must be the same.</span></span> 
  
- [<span data-ttu-id="27c08-108">新しいフロント エンド プールでの AlwaysOn 可用性グループの展開</span><span class="sxs-lookup"><span data-stu-id="27c08-108">Deploy an AlwaysOn Availability Group on a new Front End pool</span></span>](alwayson-availability-group.md#BKMK_NewPool_CreateAlwaysOnGroup)
    
- [<span data-ttu-id="27c08-109">データベース ミラーリングを使用する既存のプールで、AlwaysOn 可用性グループを展開します。</span><span class="sxs-lookup"><span data-stu-id="27c08-109">Deploy an AlwaysOn Availability Group on an existing pool that uses database mirroring</span></span>](alwayson-availability-group.md#BKMK_MirroredPool_CreateAlwaysOnGroup)
    
- [<span data-ttu-id="27c08-110">データベース ミラーリングを使用しない既存のプールに AlwaysOn 可用性グループを展開します</span><span class="sxs-lookup"><span data-stu-id="27c08-110">Deploy an AlwaysOn Availability Group on an existing pool that does not use database mirroring</span></span>](alwayson-availability-group.md#BKMK_NoHAPool_CreateAlwaysOnGroup)
    
## <a name="deploy-an-alwayson-availability-group-on-a-new-front-end-pool"></a><span data-ttu-id="27c08-111">新しいフロント エンド プールでの AlwaysOn 可用性グループの展開</span><span class="sxs-lookup"><span data-stu-id="27c08-111">Deploy an AlwaysOn Availability Group on a new Front End pool</span></span>
<span data-ttu-id="27c08-112"><a name="BKMK_NewPool_CreateAlwaysOnGroup"> </a></span><span class="sxs-lookup"><span data-stu-id="27c08-112"></span></span>

1. <span data-ttu-id="27c08-113">AlwaysOn 可用性グループの一部となるすべてのデータベース サーバーでは、Windows Server フェールオーバー クラスタ リングを設定します。</span><span class="sxs-lookup"><span data-stu-id="27c08-113">Set up Windows Server Failover Clustering on all the database servers which will be part of the AlwaysOn Availability Group.</span></span> <span data-ttu-id="27c08-114">各サーバーで、以下の作業を行います。</span><span class="sxs-lookup"><span data-stu-id="27c08-114">On each server, do the following</span></span>
    
   - <span data-ttu-id="27c08-115">サーバー マネージャーを開き、[**役割と機能の追加**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="27c08-115">Open Server Manager and click **Add roles and features**.</span></span>
    
   - <span data-ttu-id="27c08-p102">[**機能の選択**] ボックスが表示されるまで [**次へ**] をクリックします。このボックスで、[**フェールオーバー クラスタリング**] チェック ボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="27c08-p102">Click **Next** until you reach the **Select features** box. Here, select the **Failover Clustering** check box.</span></span>
    
   - <span data-ttu-id="27c08-118">[**フェールオーバー クラスタリングに必要な機能を追加しますか?**] ボックスで、[**機能の追加**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="27c08-118">In the **Add features that are required for Failover Clustering?** box, click **Add Features**.</span></span>
    
   - <span data-ttu-id="27c08-119">[**インストール**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="27c08-119">Click **Install**.</span></span>
    
2. <span data-ttu-id="27c08-120">クラスター構成を検証します。</span><span class="sxs-lookup"><span data-stu-id="27c08-120">Validate the cluster configuration.</span></span>
    
   - <span data-ttu-id="27c08-121">サーバー マネージャーで、[**ツール**] メニューをクリックし、[**フェールオーバー クラスター マネージャー**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="27c08-121">In Server Manager, click the **Tools** menu and then click **Failover Cluster Manager**.</span></span>
    
   - <span data-ttu-id="27c08-122">画面右側の [**操作**] で、[**構成の検証**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="27c08-122">Under **Actions** on the right side of the screen, click **Validate Configuration**.</span></span>
    
   - <span data-ttu-id="27c08-123">[**開始する前に**] ページで、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="27c08-123">On the **Before You Begin** page, click **Next**.</span></span>
    
   - <span data-ttu-id="27c08-124">クラスターに追加するサーバーを選択し、[**すべてのテストを実行**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="27c08-124">Select the servers to add to the cluster, and then click **Run all tests**.</span></span>
    
   - <span data-ttu-id="27c08-125">[**概要**] ボックスで、ウィザードに表示されるエラーを確認してください。</span><span class="sxs-lookup"><span data-stu-id="27c08-125">In the**Summary** box, check any errors that the wizard reports.</span></span> <span data-ttu-id="27c08-126">確認したら、[**完了**] をクリックして検証を完了します。</span><span class="sxs-lookup"><span data-stu-id="27c08-126">Then click **Finish** to complete the validation.</span></span>
    
    <span data-ttu-id="27c08-p104">特に、共有ストレージを使用していない場合、通常はウィザードにより複数の警告が報告されます。共有ストレージを使用する必要はありませんが、[**エラー**] でメッセージが表示されている場合は、作業を続行する前にこれらの問題を修正する必要があります。</span><span class="sxs-lookup"><span data-stu-id="27c08-p104">The wizard will probably report several warnings, especially if you are not using shared storage. You are not required to use shared storage. However, if you see any **Error** messages, you must fix those issues before continuing.</span></span>
    
3. <span data-ttu-id="27c08-130">クラスターを作成します。</span><span class="sxs-lookup"><span data-stu-id="27c08-130">Create the cluster.</span></span>
    
   - <span data-ttu-id="27c08-131">[**フェールオーバー クラスター管理**] ウィザードで、[**フェールオーバー クラスター管理**]、[**クラスターの作成**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="27c08-131">In the **Failover Cluster Management** wizard, right-click **Failover Cluster Management**, then click **Create Cluster**.</span></span>
    
   - <span data-ttu-id="27c08-132">[**開始する前に**] ページで、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="27c08-132">On the **Before You Begin** page, click **Next**.</span></span>
    
   - <span data-ttu-id="27c08-p105">クラスター名と IP アドレスを追加します。設定が検証されたら、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="27c08-p105">Add the cluster name and IP address. When the settings are validated, click **Next**.</span></span>
    
   - <span data-ttu-id="27c08-135">[確認] ページで、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="27c08-135">On the Confirmation page, click **Next**.</span></span>
    
   - <span data-ttu-id="27c08-136">クラスターが作成されたら、[**完了**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="27c08-136">After the cluster is created, click **Finish**.</span></span>
    
4. <span data-ttu-id="27c08-p106">ファイル共有監視を使用するようにクラスター クォーラム設定を構成することをお勧めします。このためには、以下の手順を行います。</span><span class="sxs-lookup"><span data-stu-id="27c08-p106">We recommend that you configure the cluster quorum settings to use a file share witness. To do so, use these steps:</span></span>
    
   - <span data-ttu-id="27c08-139">クラスター名を右クリックし、[**他の操作**]、[**クラスター クォーラム設定の構成**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="27c08-139">Right-click the cluster name, click **More Actions**, and click **Configure Cluster Quorum Settings**.</span></span>
    
   - <span data-ttu-id="27c08-140">[**クォーラム構成オプションの選択**] ページで、[**クォーラム監視を選択する**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="27c08-140">In the **Select Quorum Configuration Option** page, click **Select the quorum witness**.</span></span>
    
   - <span data-ttu-id="27c08-141">[**クォーラム監視の選択**] ページで、[**ファイル共有監視を構成する**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="27c08-141">In the **Select Quorum Witness** page, click **Configure a file share witness**.</span></span>
    
   - <span data-ttu-id="27c08-142">[**ファイル共有監視の構成**] ページで、使用するファイル共有のパスを入力し、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="27c08-142">In the **Configure File Share Witness** page, type the path of the file share you want to use, and then click **Next**.</span></span>
    
   - <span data-ttu-id="27c08-143">[**確認**] ページで、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="27c08-143">On the **Confirmation** page, click **Next**.</span></span>
    
5. <span data-ttu-id="27c08-144">クラスター内の各サーバーの SQL Server 構成マネージャーで、"Always On" を有効にします。</span><span class="sxs-lookup"><span data-stu-id="27c08-144">On each server in the cluster, enable Always On in SQL Server Configuration Manager.</span></span>
    
   - <span data-ttu-id="27c08-p107">SQL Server 構成マネージャーを開きます。画面左側のツリーで、[**SQL Server のサービス**] をクリックし、SQL Server サービスをダブルクリックします。</span><span class="sxs-lookup"><span data-stu-id="27c08-p107">Open SQL Server Configuration Manager. In the tree on the left side of the screen, click **SQL Server Services**, then double-click the SQL Server service.</span></span> 
    
   - <span data-ttu-id="27c08-p108">[**プロパティ**] ボックスで、[**AlwaysOn 高可用性**] タブを選択します。[**AlwaysOn 可用性グループを有効にする**] チェック ボックスをオンにします。SQL Server サービスを再開するよう求めるメッセージが表示されたら、サービスを再開します。</span><span class="sxs-lookup"><span data-stu-id="27c08-p108">In the **Properties** box, select the **AlwaysOn High Availability** tab. Select the **Enable AlwaysOn Availability Groups** check box. Restart the SQL Server service when prompted.</span></span>
    
6. <span data-ttu-id="27c08-149">可用性グループを作成します。</span><span class="sxs-lookup"><span data-stu-id="27c08-149">Create the availability group.</span></span>
    
   - <span data-ttu-id="27c08-150">SQL Server Management Studio を開き、SQL Server インスタンスに接続します。</span><span class="sxs-lookup"><span data-stu-id="27c08-150">Open SQL Server Management Studio, and connect to the SQL Server instance.</span></span>
    
   - <span data-ttu-id="27c08-p109">オブジェクト エクスプローラーで、[**AlwaysOn 高可用性**] フォルダーを展開します。[**可用性グループ**] フォルダーを右クリックし、[**新しい可用性グループ ウィザード**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="27c08-p109">In Object Explorer, expand the **AlwaysOn High Availability** folder. Right-click the **Availability Groups** folder and click **New Availability Group Wizard**.</span></span>
    
   - <span data-ttu-id="27c08-153">[**説明**] ページが表示されたら、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="27c08-153">If the **Introduction** page appears, click **Next**.</span></span>
    
   - <span data-ttu-id="27c08-154">[**可用性グループ名の指定**] ページで、可用性グループの名前を入力し、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="27c08-154">In the **Specify Availability Group Name** page, type the name of the Availability group, and click **Next**.</span></span>
    
   - <span data-ttu-id="27c08-155">データベースの選択] ページでは、AlwaysOn 可用性グループに追加するデータベースを選択します。</span><span class="sxs-lookup"><span data-stu-id="27c08-155">In the Select Databases page, select the databases that you want to include in the AlwaysOn Availability Group.</span></span> <span data-ttu-id="27c08-156">続いて [ **次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="27c08-156">Then click **Next**.</span></span>
    
    <span data-ttu-id="27c08-157">**ReportServer**、 **ReportServerTempDB**、またはデータベースの永続的なチャットに含めないで、AlwaysOn 可用性グループと、このシナリオではサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="27c08-157">Do not include the **ReportServer**, **ReportServerTempDB**, or Persistent Chat databases in the AlwaysOn Availability Group, as these are not supported in this scenario.</span></span> <span data-ttu-id="27c08-158">AlwaysOn 可用性グループで、ビジネスのサーバー データベースの他のすべての Skype を含めることができます。</span><span class="sxs-lookup"><span data-stu-id="27c08-158">You can include all other Skype for Business Server databases in the AlwaysOn Availability Group.</span></span>
    
   - <span data-ttu-id="27c08-159">[**レプリカの指定**] ページで、[**レプリカ**] タブをクリックします。続いて [**レプリカの追加**] ボタンをクリックし、Windows Server フェールオーバー クラスターのノードとして参加させた他の SQL インスタンスに接続します。</span><span class="sxs-lookup"><span data-stu-id="27c08-159">In the **Specify Replicas** page, click the **Replicas** tab. Then click the **Add Replicas** button, and connect to the other SQL instances that you joined as nodes of the Windows Server Failover Cluster.</span></span>
    
   - <span data-ttu-id="27c08-p112">各インスタンスの [**自動フェールオーバー**] オプションと [**同期コミット**] オプションをオンにします。[**読み取り可能なセカンダリ**] オプションはオンにしないでください。</span><span class="sxs-lookup"><span data-stu-id="27c08-p112">For each instance, select the **Automatic Failover** and **Synchronous Commit** options. Do not select the **Readable Secondary** option.</span></span>
    
   - <span data-ttu-id="27c08-162">[**エンドポイント**] タブをクリックし、[**ポート番号**] が "5022" に設定されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="27c08-162">Click the **Endpoints** tab and verify that **Port Number** is set to 5022.</span></span>
    
   - <span data-ttu-id="27c08-p113">[**リスナー**] タブをクリックし、[**可用性グループ リスナーの作成**] オプションをオンにします。そのオプションの下で、リスナーの名前を入力し、[**ポート**] を "1433" (他のポートはこのオプションではサポートされません) に設定します。</span><span class="sxs-lookup"><span data-stu-id="27c08-p113">Click the **Listener** tab, and select the **Create an availability group listener** option. Under that option, type a name for the listener, and set the **Port** to 1433 (other ports are not supported for this option).</span></span>
    
   - <span data-ttu-id="27c08-165">[**追加**] をクリックし、[**IPv4 アドレス**] ボックスに優先させる仮想 IP アドレスを入力して、[**OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="27c08-165">Click **Add**, and then in the **IPv4 Address** box, provide your preferred virtual IP address, and then click **OK**.</span></span>
    
   - <span data-ttu-id="27c08-p114">[**最初のデータの同期を選択**] ページで [完全] を選択します。レプリカがアクセスでき、両方のレプリカにより使用される SQL Server サービス アカウントが書き込みアクセス許可を持っているフォルダーを指定します。続いて、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="27c08-p114">In the **Select Initial Data Synchronization** page, select Full, and specify a folder that is accessible to the replicas, and that the SQL Server service account used by both replicas has Write permissions for. Then click **Next**.</span></span>
    
    <span data-ttu-id="27c08-p115">このファイル共有は、データベースを初期化した時点で一時的に使用されます。大きなデータベースを扱う場合、使用するネットワーク帯域幅でデータベース バックアップのサイズに対応できない場合に備えて、データベースを手動で初期化することを推奨します。</span><span class="sxs-lookup"><span data-stu-id="27c08-p115">This file share will be used temporarily when you initialize the databases. If you are dealing with large databases, we recommend that you manually initialize them in case your network bandwidth cannot accommodate the size of the database backups.</span></span>
    
   - <span data-ttu-id="27c08-170">[検証] ページで、すべての検証チェックが成功したことを確認し、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="27c08-170">In the Validation page, verify that all validation checks are successful, then click **Next**.</span></span>
    
   - <span data-ttu-id="27c08-171">**概要**] ページで、すべての設定を確認して、[完了] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="27c08-171">In the**Summary** page, verify all settings and click Finish.</span></span>
    
7. <span data-ttu-id="27c08-172">説明したように、フロント エンド プールを作成するトポロジ ビルダーを使用して、[を作成するビジネス サーバー 2015 の Skype の新しいトポロジを公開し、](../../deploy/install/create-and-publish-new-topology.md)。</span><span class="sxs-lookup"><span data-stu-id="27c08-172">Use Topology Builder to create the Front End pool, as explained in [Create and publish new topology in Skype for Business Server 2015](../../deploy/install/create-and-publish-new-topology.md).</span></span> <span data-ttu-id="27c08-173">実行すると、プールの SQL ストアとして、AlwaysOn 可用性グループを指定します。</span><span class="sxs-lookup"><span data-stu-id="27c08-173">When you do, specify the AlwaysOn Availability Group as the SQL store for the pool.</span></span>
    
8. <span data-ttu-id="27c08-174">プールおよび AlwaysOn 可用性グループを展開した後は、SQL ログインが各 AlwaysOn 可用性グループのレプリカであることを確認するのにはいくつかの最終的な手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="27c08-174">After the pool and the AlwaysOn Availability Group are deployed, perform some final steps to make sure that the SQL logins are on each of the replicas in the AlwaysOn Availability Group.</span></span> 
    
   - <span data-ttu-id="27c08-175">トポロジ ビルダーを開き**既存の展開からトポロジをダウンロード**するを選択して**[ok]**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="27c08-175">Open Topology Builder, select **Download topology from existing deployment**, and click **OK**.</span></span>
    
   - <span data-ttu-id="27c08-176">[Skype for Business Server]、使用するトポロジ、[**SQL Server ストア**] の順に展開します。</span><span class="sxs-lookup"><span data-stu-id="27c08-176">Expand Skype for Business Server, expand your topology, and expand **SQL Server Stores**.</span></span> <span data-ttu-id="27c08-177">新しい AlwaysOn 可用性グループの SQL ストアを右クリックし、をクリックして * * 編集プロパティ * *。</span><span class="sxs-lookup"><span data-stu-id="27c08-177">Right-click the SQL store of the new AlwaysOn Availability Group, and click ** Edit Properties**.</span></span>
    
    - <span data-ttu-id="27c08-178">**SQL Server の FQDN** ] ボックスで、ページの下部にある AlwaysOn 可用性グループのリスナーの FQDN の値を変更します。</span><span class="sxs-lookup"><span data-stu-id="27c08-178">At the bottom of the page, in the **SQL Server FQDN** box, change the value to the FQDN of the Listener of the AlwaysOn Availability Group.</span></span>
    
   - <span data-ttu-id="27c08-p118">トポロジを公開します。[**操作**] メニューから、[**トポロジ**]、[**公開**] の順にクリックします。続いて、確認ページで [**次へ**] をクリックします。新しいトポロジがレプリケートされるまで数分待ちます。</span><span class="sxs-lookup"><span data-stu-id="27c08-p118">Publish the topology. From the **Action** menu click **Topology** and then **Publish**. Then in the confirmation page click **Next**. Then wait a few minutes for the new topology to replicate.</span></span>
    
   - <span data-ttu-id="27c08-183">SQL Server Management Studio を開き AlwaysOn 可用性グループに移動します。</span><span class="sxs-lookup"><span data-stu-id="27c08-183">Open SQL Server Management Studio, and navigate to the AlwaysOn Availability Group.</span></span> <span data-ttu-id="27c08-184">AlwaysOn 可用性グループのセカンダリ レプリカへのフェールオーバーを行います。</span><span class="sxs-lookup"><span data-stu-id="27c08-184">Fail it over to a secondary replica.</span></span>
    
   - <span data-ttu-id="27c08-185">ビジネス サーバー管理シェルの Skype を開きこのレプリカの SQL ログインを作成するのには、次のコマンドレットを入力します。</span><span class="sxs-lookup"><span data-stu-id="27c08-185">Open Skype for Business Server Management Shell and type the following cmdlet to create the SQL logins on this replica:</span></span>
    
   ```
   Install-CsDatabase -Update
   ```

   - <span data-ttu-id="27c08-186">前の 2 つの手順を繰り返します (セカンダリ レプリカでは、グループをフェールオーバーしを使用して、 `Install-CsDatabase -Update`)、グループ内の各レプリカのです。</span><span class="sxs-lookup"><span data-stu-id="27c08-186">Repeat the previous two steps (fail over the group to a secondary replica, then use  `Install-CsDatabase -Update`) for each replica in the group.</span></span>
    
## <a name="deploy-an-alwayson-availability-group-on-an-existing-pool-that-uses-database-mirroring"></a><span data-ttu-id="27c08-187">データベース ミラーリングを使用する既存のプールで、AlwaysOn 可用性グループを展開します。</span><span class="sxs-lookup"><span data-stu-id="27c08-187">Deploy an AlwaysOn Availability Group on an existing pool that uses database mirroring</span></span>
<span data-ttu-id="27c08-188"><a name="BKMK_MirroredPool_CreateAlwaysOnGroup"> </a></span><span class="sxs-lookup"><span data-stu-id="27c08-188"></span></span>

> [!NOTE]
> <span data-ttu-id="27c08-189">場合は、プールをアップグレードしている AlwaysOn 可用性グループをホストするサーバーの全体管理は、組織の保存、移動、CMS 別のプールにこのプールをアップグレードする前にします。</span><span class="sxs-lookup"><span data-stu-id="27c08-189">If the pool you are upgrading to an AlwaysOn Availability Group hosts the Central Management store for your organization, you must first move the CMS to another pool before you upgrade this pool.</span></span> <span data-ttu-id="27c08-190">プールを移動するには、Move-CsManagementServer コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="27c08-190">Use the Move-CsManagementServer cmdlet to move the pool.</span></span> <span data-ttu-id="27c08-191">組織内の別のプールがない、Standard Edition サーバーを一時的に展開し、AlwaysOn 可用性グループに、プールをアップグレードする前に、このサーバーに CMS を移動できます。</span><span class="sxs-lookup"><span data-stu-id="27c08-191">If you do not have another pool in your organization, you can deploy a Standard Edition server temporarily and move the CMS to this server before you upgrade your pool to the AlwaysOn Availability Group.</span></span> 
  
1. <span data-ttu-id="27c08-192">ビジネス サーバー管理シェルの Skype を開き、次のコマンドレットを入力すると、ミラーからのすべてのデータの主要なノードをフェールオーバーします。</span><span class="sxs-lookup"><span data-stu-id="27c08-192">Fail over all data from the mirror to the principal node by opening Skype for Business Server Management Shell and typing the following cmdlet.</span></span>
    
   ```
   Invoke-CsDatabaseFailover -PoolFqdn <Pool FQDN> -DatabaseType <DatabaseType> -NewPrincipal "Primary"
   ```

    <span data-ttu-id="27c08-p121">プール内の各データベースの種類に対してこのコマンドレットを繰り返します。次のコマンドレットを使用すると、このプールに格納されているすべてのデータベースの種類を見つけることができます。</span><span class="sxs-lookup"><span data-stu-id="27c08-p121">Repeat this cmdlet for each database type in the pool. You can use the following cmdlet to find all the database types stored in this pool.</span></span>
     
   ```
   Get-CsPool -Identity <Pool FQDN>
   ```

2. <span data-ttu-id="27c08-195">トポロジ ビルダーを使用して、プールからデータベース ミラーリングを削除する</span><span class="sxs-lookup"><span data-stu-id="27c08-195">Use Topology Builder to remove database mirroring from the pool</span></span>
    
   - <span data-ttu-id="27c08-196">トポロジ ビルダーを開きます。</span><span class="sxs-lookup"><span data-stu-id="27c08-196">Open Topology Builder.</span></span> <span data-ttu-id="27c08-197">トポロジで [**Enterprise Edition フロントエンド プール**] を展開し、プール名を右クリックし、[**プロパティの編集**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="27c08-197">In your topology, expand **Enterprise Edition Front End Pools**, right-click the name of the pool, and click **Edit Properties**.</span></span>
    
   - <span data-ttu-id="27c08-198">プール内の各種類の SQL ストアに対して、[**SQL ストアのミラーリングを有効にする**] チェック ボックスをオフにします。</span><span class="sxs-lookup"><span data-stu-id="27c08-198">For each type of SQL store in the pool, clear the **Enable SQL Store Mirroring** check box.</span></span>
    
3. <span data-ttu-id="27c08-p123">変更したトポロジを公開します。[**操作**] メニューから、[**トポロジ**]、[**公開**] の順にクリックします。続いて確認ページで [**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="27c08-p123">Publish the changed topology. From the **Action** menu click **Topology** and then **Publish**. Then in the confirmation page click **Next**</span></span>
    
4. <span data-ttu-id="27c08-202">SQL Server Management Studio を使用して、ミラーを解除します。</span><span class="sxs-lookup"><span data-stu-id="27c08-202">Use SQL Server Management Studio to break the mirror.</span></span>
    
   - <span data-ttu-id="27c08-p124">SQL Server Management Studio を開き、使用しているデータベースに移動し、[**タスク**] を右クリックし、[**ミラー**] をクリックします。続いて [**ミラーリングの削除**] をクリックし、[**OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="27c08-p124">Open SQL Server Management Studio, navigate to your databases, right-click **Tasks** and click **Mirror**. Then click **Remove Mirroring** and click **OK**.</span></span>
    
   - <span data-ttu-id="27c08-205">AlwaysOn 可用性グループに変換されるプール内のすべてのデータベースに対してこの手順を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="27c08-205">Repeat this for all databases in the pool which will be converted to an AlwaysOn Availability Group.</span></span>
    
5. <span data-ttu-id="27c08-206">AlwaysOn 可用性グループの一部となるすべてのデータベース サーバーでは、Windows Server フェールオーバー クラスタ リングを設定します。</span><span class="sxs-lookup"><span data-stu-id="27c08-206">Set up Windows Server Failover Clustering on all the database servers which will be part of the AlwaysOn Availability Group.</span></span> <span data-ttu-id="27c08-207">各サーバーで、以下の作業を行います。</span><span class="sxs-lookup"><span data-stu-id="27c08-207">On each server, do the following</span></span>
    
   - <span data-ttu-id="27c08-208">サーバー マネージャーを開き、[**役割と機能の追加**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="27c08-208">Open Server Manager and click **Add roles and features**.</span></span>
    
   - <span data-ttu-id="27c08-p126">[**機能の選択**] ボックスが表示されるまで [**次へ**] をクリックします。このボックスで、[**フェールオーバー クラスタリング**] チェック ボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="27c08-p126">Click **Next** until you reach the **Select features** box. Here, select the **Failover Clustering** check box.</span></span>
    
   - <span data-ttu-id="27c08-211">[**フェールオーバー クラスタリングに必要な機能を追加しますか?**] ボックスで、[**機能の追加**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="27c08-211">In the **Add features that are required for Failover Clustering?** box, click **Add Features**.</span></span>
    
   - <span data-ttu-id="27c08-212">[**インストール**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="27c08-212">Click **Install**.</span></span>
    
6. <span data-ttu-id="27c08-213">クラスター構成を検証します。</span><span class="sxs-lookup"><span data-stu-id="27c08-213">Validate the cluster configuration.</span></span>
    
   - <span data-ttu-id="27c08-214">サーバー マネージャーで、[**ツール**] メニューをクリックし、[**フェールオーバー クラスター マネージャー**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="27c08-214">In Server Manager, click the **Tools** menu and then click **Failover Cluster Manager**.</span></span>
    
   - <span data-ttu-id="27c08-215">画面右側の [**操作**] で、[**構成の検証**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="27c08-215">Under **Actions** on the right side of the screen, click **Validate Configuration**.</span></span>
    
   - <span data-ttu-id="27c08-216">[**開始する前に**] ページで、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="27c08-216">On the **Before You Begin** page, click **Next**.</span></span>
    
   - <span data-ttu-id="27c08-217">クラスターに追加するサーバーを選択し、[**すべてのテストを実行**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="27c08-217">Select the servers to add to the cluster, and then click **Run all tests**.</span></span>
    
   - <span data-ttu-id="27c08-218">[**概要**] ボックスで、ウィザードに表示されるエラーを確認してください。</span><span class="sxs-lookup"><span data-stu-id="27c08-218">In the**Summary** box, check any errors that the wizard reports.</span></span> <span data-ttu-id="27c08-219">確認したら、[**完了**] をクリックして検証を完了します。</span><span class="sxs-lookup"><span data-stu-id="27c08-219">Then click **Finish** to complete the validation.</span></span>
    
    <span data-ttu-id="27c08-p128">特に、共有ストレージを使用していない場合、通常はウィザードにより複数の警告が報告されます。共有ストレージを使用する必要はありませんが、[**エラー**] でメッセージが表示されている場合は、作業を続行する前にこれらの問題を修正する必要があります。</span><span class="sxs-lookup"><span data-stu-id="27c08-p128">The wizard will probably report several warnings, especially if you are not using shared storage. You are not required to use shared storage. However, if you see any **Error** messages, you must fix those issues before continuing.</span></span>
    
7. <span data-ttu-id="27c08-223">クラスターを作成します。</span><span class="sxs-lookup"><span data-stu-id="27c08-223">Create the cluster.</span></span>
    
   - <span data-ttu-id="27c08-224">[**フェールオーバー クラスター管理**] ウィザードで、[**フェールオーバー クラスター管理**]、[**クラスターの作成**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="27c08-224">In the **Failover Cluster Management** wizard, right-click **Failover Cluster Management**, then click **Create Cluster**.</span></span>
    
   - <span data-ttu-id="27c08-225">[**開始する前に**] ページで、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="27c08-225">On the **Before You Begin** page, click **Next**.</span></span>
    
   - <span data-ttu-id="27c08-p129">クラスター名と IP アドレスを追加します。設定が検証されたら、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="27c08-p129">Add the cluster name and IP address. When the settings are validated, click **Next**.</span></span>
    
   - <span data-ttu-id="27c08-228">[確認] ページで、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="27c08-228">On the Confirmation page, click **Next**.</span></span>
    
   - <span data-ttu-id="27c08-229">クラスターが作成されたら、[**完了**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="27c08-229">After the cluster is created, click **Finish**.</span></span>
    
8. <span data-ttu-id="27c08-p130">ファイル共有監視を使用するようにクラスター クォーラム設定を構成することをお勧めします。このためには、以下の手順を行います。</span><span class="sxs-lookup"><span data-stu-id="27c08-p130">We recommend that you configure the cluster quorum settings to use a file share witness. To do so, use these steps:</span></span>
    
   - <span data-ttu-id="27c08-232">クラスター名を右クリックし、[**他の操作**]、[**クラスター クォーラム設定の構成**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="27c08-232">Right-click the cluster name, click **More Actions**, and click **Configure Cluster Quorum Settings**.</span></span>
    
   - <span data-ttu-id="27c08-233">[**クォーラム構成オプションの選択**] ページで、[**クォーラム監視を選択する**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="27c08-233">In the **Select Quorum Configuration Option** page, click **Select the quorum witness**.</span></span>
    
   - <span data-ttu-id="27c08-234">[**クォーラム監視の選択**] ページで、[**ファイル共有監視を構成する**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="27c08-234">In the **Select Quorum Witness** page, click **Configure a file share witness**.</span></span>
    
   - <span data-ttu-id="27c08-235">[**ファイル共有監視の構成**] ページで、使用するファイル共有のパスを入力し、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="27c08-235">In the **Configure File Share Witness** page, type the path of the file share you want to use, and then click **Next**.</span></span>
    
   - <span data-ttu-id="27c08-236">[**確認**] ページで、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="27c08-236">On the **Confirmation** page, click **Next**.</span></span>
    
9. <span data-ttu-id="27c08-237">クラスター内の各サーバーの SQL Server 構成マネージャーで、"Always On" を有効にします。</span><span class="sxs-lookup"><span data-stu-id="27c08-237">On each server in the cluster, enable Always On in SQL Server Configuration Manager.</span></span>
    
   - <span data-ttu-id="27c08-p131">SQL Server 構成マネージャーを開きます。画面左側のツリーで、[**SQL Server のサービス**] をクリックし、SQL Server サービスをダブルクリックします。</span><span class="sxs-lookup"><span data-stu-id="27c08-p131">Open SQL Server Configuration Manager. In the tree on the left side of the screen, click **SQL Server Services**, then double-click the SQL Server service.</span></span> 
    
   - <span data-ttu-id="27c08-p132">[**プロパティ**] ボックスで、[**AlwaysOn 高可用性**] タブを選択します。[**AlwaysOn 可用性グループを有効にする**] チェック ボックスをオンにします。SQL Server サービスを再開するよう求めるメッセージが表示されたら、サービスを再開します。</span><span class="sxs-lookup"><span data-stu-id="27c08-p132">In the **Properties** box, select the **AlwaysOn High Availability** tab. Select the **Enable AlwaysOn Availability Groups** check box. Restart the SQL Server service when prompted.</span></span>
    
10. <span data-ttu-id="27c08-242">可用性グループを作成します。</span><span class="sxs-lookup"><span data-stu-id="27c08-242">Create the availability group.</span></span>
    
    - <span data-ttu-id="27c08-243">SQL Server Management Studio を開き、SQL Server インスタンスに接続します。</span><span class="sxs-lookup"><span data-stu-id="27c08-243">Open SQL Server Management Studio, and connect to the SQL Server instance.</span></span>
    
    - <span data-ttu-id="27c08-p133">オブジェクト エクスプローラーで、[**AlwaysOn 高可用性**] フォルダーを展開します。[**可用性グループ**] フォルダーを右クリックし、[**新しい可用性グループ ウィザード**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="27c08-p133">In Object Explorer, expand the **AlwaysOn High Availability** folder. Right-click the **Availability Groups** folder and click **New Availability Group Wizard**.</span></span>
    
    - <span data-ttu-id="27c08-246">[**説明**] ページが表示されたら、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="27c08-246">If the **Introduction** page appears, click **Next**.</span></span>
    
    - <span data-ttu-id="27c08-247">[**可用性グループ名の指定**] ページで、可用性グループの名前を入力し、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="27c08-247">In the **Specify Availability Group Name** page, type the name of the Availability group, and click **Next**.</span></span>
    
    - <span data-ttu-id="27c08-248">データベースの選択] ページでは、AlwaysOn 可用性グループに追加するデータベースを選択します。</span><span class="sxs-lookup"><span data-stu-id="27c08-248">In the Select Databases page, select the databases that you want to include in the AlwaysOn Availability Group.</span></span> <span data-ttu-id="27c08-249">続いて [ **次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="27c08-249">Then click **Next**.</span></span>
    
    <span data-ttu-id="27c08-250">**ReportServer**、 **ReportServerTempDB**、またはデータベースの永続的なチャットに含めないで、AlwaysOn 可用性グループと、このシナリオではサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="27c08-250">Do not include the **ReportServer**, **ReportServerTempDB**, or Persistent Chat databases in the AlwaysOn Availability Group, as these are not supported in this scenario.</span></span> <span data-ttu-id="27c08-251">AlwaysOn 可用性グループで、ビジネスのサーバー データベースの他のすべての Skype を含めることができます。</span><span class="sxs-lookup"><span data-stu-id="27c08-251">You can include all other Skype for Business Server databases in the AlwaysOn Availability Group.</span></span>
    
    - <span data-ttu-id="27c08-252">[**レプリカの指定**] ページで、[**レプリカ**] タブをクリックします。続いて [**レプリカの追加**] ボタンをクリックし、Windows Server フェールオーバー クラスターのノードとして参加させた他の SQL インスタンスに接続します。</span><span class="sxs-lookup"><span data-stu-id="27c08-252">In the **Specify Replicas** page, click the **Replicas** tab. Then click the **Add Replicas** button, and connect to the other SQL instances that you joined as nodes of the Windows Server Failover Cluster.</span></span>
    
    - <span data-ttu-id="27c08-p136">各インスタンスの [**自動フェールオーバー**] オプションと [**同期コミット**] オプションをオンにします。[**読み取り可能なセカンダリ**] オプションはオンにしないでください。</span><span class="sxs-lookup"><span data-stu-id="27c08-p136">For each instance, select the **Automatic Failover** and **Synchronous Commit** options. Do not select the **Readable Secondary** option.</span></span>
    
    - <span data-ttu-id="27c08-255">[**エンドポイント**] タブをクリックし、[**ポート番号**] が "5022" に設定されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="27c08-255">Click the **Endpoints** tab and verify that **Port Number** is set to 5022.</span></span>
    
     - <span data-ttu-id="27c08-p137">[**リスナー**] タブをクリックし、[**可用性グループ リスナーの作成**] オプションをオンにします。そのオプションの下で、リスナーの名前を入力し、[**ポート**] を "1433" (他のポートはこのオプションではサポートされません) に設定します。</span><span class="sxs-lookup"><span data-stu-id="27c08-p137">Click the **Listener** tab, and select the **Create an availability group listener** option. Under that option, type a name for the listener, and set the **Port** to 1433 (other ports are not supported for this option).</span></span>
    
    - <span data-ttu-id="27c08-258">[**追加**] をクリックし、[**IPv4 アドレス**] ボックスに優先させる仮想 IP アドレスを入力して、[**OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="27c08-258">Click **Add**, and then in the **IPv4 Address** box, provide your preferred virtual IP address, and then click **OK**.</span></span>
    
    - <span data-ttu-id="27c08-p138">[**最初のデータの同期を選択**] ページで [完全] を選択します。レプリカがアクセスでき、両方のレプリカにより使用される SQL Server サービス アカウントが書き込みアクセス許可を持っているフォルダーを指定します。続いて、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="27c08-p138">In the **Select Initial Data Synchronization** page, select Full, and specify a folder that is accessible to the replicas, and that the SQL Server service account used by both replicas has Write permissions for. Then click **Next**.</span></span>
    
    <span data-ttu-id="27c08-p139">このファイル共有は、データベースを初期化した時点で一時的に使用されます。大きなデータベースを扱う場合、使用するネットワーク帯域幅でデータベース バックアップのサイズに対応できない場合に備えて、データベースを手動で初期化することを推奨します。</span><span class="sxs-lookup"><span data-stu-id="27c08-p139">This file share will be used temporarily when you initialize the databases. If you are dealing with large databases, we recommend that you manually initialize them in case your network bandwidth cannot accommodate the size of the database backups.</span></span>
    
    - <span data-ttu-id="27c08-263">[検証] ページで、すべての検証チェックが成功したことを確認し、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="27c08-263">In the Validation page, verify that all validation checks are successful, then click **Next**.</span></span>
    
    - <span data-ttu-id="27c08-264">[**概要**] ページで、すべての設定を確認し、[完了] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="27c08-264">In the **Summary** page, verify all settings and click Finish.</span></span>
    
11. <span data-ttu-id="27c08-265">AlwaysOn 可用性グループ リスナーを指定して、AlwaysOn 可用性グループのプライマリ ノードとしての古いミラーのプリンシパルを指定することに、新しいストアを作成します。</span><span class="sxs-lookup"><span data-stu-id="27c08-265">Create a new store specifying the AlwaysOn Availability Group listener, and specifying the principal of the old mirror as the primary node of the AlwaysOn Availability Group.</span></span>
    
    - <span data-ttu-id="27c08-266">トポロジ ビルダーを開きます。</span><span class="sxs-lookup"><span data-stu-id="27c08-266">Open Topology Builder.</span></span> <span data-ttu-id="27c08-267">トポロジで、[**共有コンポーネント**] を展開し、[**SQL Server ストア**] を右クリックして、[**新しい SQL Server ストア**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="27c08-267">In your topology, expand **Shared Components**, right-click **SQL Server Stores**, and click **New SQL Server Store**.</span></span>
    
    - <span data-ttu-id="27c08-268">[**新しい SQL ストアの定義**] ページで、まず [**高可用性の設定**] チェック ボックスをオンにしてから、SQL AlwaysOn 可用性グループがドロップダウン ボックスに表示されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="27c08-268">In the **Define New SQL Store** page, first select the **High Availability Settings** check box, and then make sure that SQL AlwaysOn Availability Groups appears in the drop-down box.</span></span>
    
    - <span data-ttu-id="27c08-269">[**SQL Server の可用性グループのリスナーの FQDN**] ボックスに、可用性グループを作成したときに作成したリスナーの FQDN を入力します。</span><span class="sxs-lookup"><span data-stu-id="27c08-269">In the **SQL Server Availability Listener FQDN** box, type the FQDN of the listener you created when you created the availability group.</span></span>
    
    - <span data-ttu-id="27c08-270">**SQL Server の FQDN** ] ボックスに、AlwaysOn 可用性グループのプライマリ ノードの FQDN を入力し、し、[ **OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="27c08-270">In the **SQL Server FQDN** box, type the FQDN of the primary node of the AlwaysOn Availability Group, and then click **OK**.</span></span> <span data-ttu-id="27c08-271">これは、このストアの古いミラーのプリンシパルである必要があります。</span><span class="sxs-lookup"><span data-stu-id="27c08-271">This should be the principal of the old mirror for this store.</span></span>
    
12. <span data-ttu-id="27c08-272">新しい AlwaysOn 可用性グループをフロント エンド プールに関連付けます。</span><span class="sxs-lookup"><span data-stu-id="27c08-272">Associate the new AlwaysOn Availability Group with the Front End pool.</span></span>
    
    - <span data-ttu-id="27c08-273">トポロジ ビルダーでは、AlwaysOn 可用性グループに関連付けるには、プールを右クリックし、**プロパティの編集**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="27c08-273">In Topology Builder, right-click the pool to associate with the AlwaysOn Availability Group, and click **Edit Properties**.</span></span>
    
    - <span data-ttu-id="27c08-274">[**関連付け**の**SQL Server ストア**] ボックスに、AlwaysOn 可用性グループを選択します。</span><span class="sxs-lookup"><span data-stu-id="27c08-274">Under **Associations**, in the **SQL Server Store** box, select the AlwaysOn Availability Group.</span></span> <span data-ttu-id="27c08-275">AlwaysOn 可用性グループに移動先となるプール内の他のデータベースの同じグループを選択します。</span><span class="sxs-lookup"><span data-stu-id="27c08-275">Select the same group for any other databases in the pool which you want to move to the AlwaysOn Availability Group.</span></span>
    
    - <span data-ttu-id="27c08-276">AlwaysOn 可用性グループに必要なすべてのデータベースが設定されていることを確認したら、[ **OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="27c08-276">When you're sure that all needed databases are set to the AlwaysOn Availability Group, click **OK**.</span></span>
    
13. <span data-ttu-id="27c08-p143">トポロジを公開します。[**操作**] メニューから、[**トポロジ**]、[**公開**] の順にクリックします。続いて確認ページで [**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="27c08-p143">Publish the topology. From the **Action** menu click **Topology** and then **Publish**. Then in the confirmation page click **Next**.</span></span>
    
14. <span data-ttu-id="27c08-280">AlwaysOn 可用性グループのレプリカの各 SQL ログインしているかどうかを確認するのにはいくつかの最終的な手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="27c08-280">Perform some final steps to make sure that the SQL logins are on each of the replicas in the AlwaysOn Availability Group.</span></span>
    
    - <span data-ttu-id="27c08-281">トポロジ ビルダーを開き**既存の展開からトポロジをダウンロード**するを選択して**[ok]**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="27c08-281">Open Topology Builder, select **Download topology from existing deployment**, and click **OK**.</span></span>
    
    - <span data-ttu-id="27c08-282">[Skype for Business Server]、使用するトポロジ、[**SQL Server ストア**] の順に展開します。</span><span class="sxs-lookup"><span data-stu-id="27c08-282">Expand Skype for Business Server, expand your topology, and expand **SQL Server Stores**.</span></span> <span data-ttu-id="27c08-283">新しい AlwaysOn 可用性グループの SQL ストアを右クリックし、[**プロパティの編集**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="27c08-283">Right-click the SQL store of the new AlwaysOn Availability Group, and click **Edit Properties**.</span></span>
    
    - <span data-ttu-id="27c08-284">**SQL Server の FQDN** ] ボックスで、ページの下部にある AlwaysOn 可用性グループのリスナーの FQDN の値を変更します。</span><span class="sxs-lookup"><span data-stu-id="27c08-284">At the bottom of the page, in the **SQL Server FQDN** box, change the value to the FQDN of the Listener of the AlwaysOn Availability Group.</span></span>
    
    - <span data-ttu-id="27c08-p145">トポロジを公開します。[**操作**] メニューから、[**トポロジ**]、[**公開**] の順にクリックします。続いて、確認ページで [**次へ**] をクリックします。新しいトポロジがレプリケートされるまで数分待ちます。</span><span class="sxs-lookup"><span data-stu-id="27c08-p145">Publish the topology. From the **Action** menu click **Topology** and then **Publish**. Then in the confirmation page click **Next**. Then wait a few minutes for the new topology to replicate.</span></span>
    
    - <span data-ttu-id="27c08-289">SQL Server Management Studio を開き AlwaysOn 可用性グループに移動します。</span><span class="sxs-lookup"><span data-stu-id="27c08-289">Open SQL Server Management Studio, and navigate to the AlwaysOn Availability Group.</span></span> <span data-ttu-id="27c08-290">AlwaysOn 可用性グループのセカンダリ レプリカへのフェールオーバーを行います。</span><span class="sxs-lookup"><span data-stu-id="27c08-290">Fail it over to a secondary replica.</span></span>
    
    - <span data-ttu-id="27c08-291">ビジネス サーバー管理シェルの Skype を開きこのレプリカの SQL ログインを作成するのには、次のコマンドレットを入力します。</span><span class="sxs-lookup"><span data-stu-id="27c08-291">Open Skype for Business Server Management Shell and type the following cmdlet to create the SQL logins on this replica:</span></span>
    
    ```
    Install-CsDatabase -Update
    ```

    - <span data-ttu-id="27c08-292">前の 2 つの手順を繰り返します (セカンダリ レプリカでは、グループをフェールオーバーしを使用して、 `Install-CsDatabase -Update`)、グループ内の各レプリカのです。</span><span class="sxs-lookup"><span data-stu-id="27c08-292">Repeat the previous two steps (fail over the group to a secondary replica, then use  `Install-CsDatabase -Update`) for each replica in the group.</span></span>
    
## <a name="deploy-an-alwayson-availability-group-on-an-existing-pool-that-does-not-use-database-mirroring"></a><span data-ttu-id="27c08-293">データベース ミラーリングを使用しない既存のプールに AlwaysOn 可用性グループを展開します</span><span class="sxs-lookup"><span data-stu-id="27c08-293">Deploy an AlwaysOn Availability Group on an existing pool that does not use database mirroring</span></span>
<span data-ttu-id="27c08-294"><a name="BKMK_NoHAPool_CreateAlwaysOnGroup"> </a></span><span class="sxs-lookup"><span data-stu-id="27c08-294"></span></span>

> [!NOTE]
> <span data-ttu-id="27c08-295">場合は、プールをアップグレードしている AlwaysOn 可用性グループをホストするサーバーの全体管理は、組織の保存、移動、CMS 別のプールにこのプールをアップグレードする前にします。</span><span class="sxs-lookup"><span data-stu-id="27c08-295">If the pool you are upgrading to an AlwaysOn Availability Group hosts the Central Management store for your organization, you must first move the CMS to another pool before you upgrade this pool.</span></span> <span data-ttu-id="27c08-296">プールを移動するには、Move-CsManagementServer コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="27c08-296">Use the Move-CsManagementServer cmdlet to move the pool.</span></span> <span data-ttu-id="27c08-297">組織内の別のプールがない、Standard Edition サーバーを一時的に展開し、AlwaysOn 可用性グループに、プールをアップグレードする前に、このサーバーに CMS を移動できます。</span><span class="sxs-lookup"><span data-stu-id="27c08-297">If you do not have another pool in your organization, you can deploy a Standard Edition server temporarily and move the CMS to this server before you upgrade your pool to the AlwaysOn Availability Group.</span></span> 
  
1. <span data-ttu-id="27c08-298">AlwaysOn 可用性グループの一部となるすべてのデータベース サーバーでは、Windows Server フェールオーバー クラスタ リングを設定します。</span><span class="sxs-lookup"><span data-stu-id="27c08-298">Set up Windows Server Failover Clustering on all the database servers which will be part of the AlwaysOn Availability Group.</span></span> <span data-ttu-id="27c08-299">各サーバーで、以下の作業を行います。</span><span class="sxs-lookup"><span data-stu-id="27c08-299">On each server, do the following</span></span>
    
   - <span data-ttu-id="27c08-300">サーバー マネージャーを開き、[**役割と機能の追加**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="27c08-300">Open Server Manager and click **Add roles and features**.</span></span>
    
   - <span data-ttu-id="27c08-p149">[**機能の選択**] ボックスが表示されるまで [**次へ**] をクリックします。このボックスで、[**フェールオーバー クラスタリング**] チェック ボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="27c08-p149">Click **Next** until you reach the **Select features** box. Here, select the **Failover Clustering** check box.</span></span>
    
   - <span data-ttu-id="27c08-303">[**フェールオーバー クラスタリングに必要な機能を追加しますか?**] ボックスで、[**機能の追加**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="27c08-303">In the **Add features that are required for Failover Clustering?** box, click **Add Features**.</span></span>
    
   - <span data-ttu-id="27c08-304">[**インストール**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="27c08-304">Click **Install**.</span></span>
    
2. <span data-ttu-id="27c08-305">クラスター構成を検証します。</span><span class="sxs-lookup"><span data-stu-id="27c08-305">Validate the cluster configuration.</span></span>
    
   - <span data-ttu-id="27c08-306">サーバー マネージャーで、[**ツール**] メニューをクリックし、[**フェールオーバー クラスター マネージャー**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="27c08-306">In Server Manager, click the **Tools** menu and then click **Failover Cluster Manager**.</span></span>
    
   - <span data-ttu-id="27c08-307">画面右側の [**操作**] で、[**構成の検証**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="27c08-307">Under **Actions** on the right side of the screen, click **Validate Configuration**.</span></span>
    
   - <span data-ttu-id="27c08-308">[**開始する前に**] ページで、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="27c08-308">On the **Before You Begin** page, click **Next**.</span></span>
    
   - <span data-ttu-id="27c08-309">クラスターに追加するサーバーを選択し、[**すべてのテストを実行**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="27c08-309">Select the servers to add to the cluster, and then click **Run all tests**.</span></span>
    
   - <span data-ttu-id="27c08-310">[**概要**] ボックスで、ウィザードに表示されるエラーを確認してください。</span><span class="sxs-lookup"><span data-stu-id="27c08-310">In the**Summary** box, check any errors that the wizard reports.</span></span> <span data-ttu-id="27c08-311">確認したら、[**完了**] をクリックして検証を完了します。</span><span class="sxs-lookup"><span data-stu-id="27c08-311">Then click **Finish** to complete the validation.</span></span>
    
    <span data-ttu-id="27c08-p151">特に、共有ストレージを使用していない場合、通常はウィザードにより複数の警告が報告されます。共有ストレージを使用する必要はありませんが、[**エラー**] でメッセージが表示されている場合は、作業を続行する前にこれらの問題を修正する必要があります。</span><span class="sxs-lookup"><span data-stu-id="27c08-p151">The wizard will probably report several warnings, especially if you are not using shared storage. You are not required to use shared storage. However, if you see any **Error** messages, you must fix those issues before continuing.</span></span>
    
3. <span data-ttu-id="27c08-315">クラスターを作成します。</span><span class="sxs-lookup"><span data-stu-id="27c08-315">Create the cluster.</span></span>
    
   - <span data-ttu-id="27c08-316">[**フェールオーバー クラスター管理**] ウィザードで、[**フェールオーバー クラスター管理**]、[**クラスターの作成**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="27c08-316">In the **Failover Cluster Management** wizard, right-click **Failover Cluster Management**, then click **Create Cluster**.</span></span>
    
   - <span data-ttu-id="27c08-317">[**開始する前に**] ページで、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="27c08-317">On the **Before You Begin** page, click **Next**.</span></span>
    
   - <span data-ttu-id="27c08-p152">クラスター名と IP アドレスを追加します。設定が検証されたら、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="27c08-p152">Add the cluster name and IP address. When the settings are validated, click **Next**.</span></span>
    
   - <span data-ttu-id="27c08-320">[確認] ページで、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="27c08-320">On the Confirmation page, click **Next**.</span></span>
    
   - <span data-ttu-id="27c08-321">クラスターが作成されたら、[**完了**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="27c08-321">After the cluster is created, click **Finish**.</span></span>
    
4. <span data-ttu-id="27c08-p153">ファイル共有監視を使用するようにクラスター クォーラム設定を構成することをお勧めします。このためには、以下の手順を行います。</span><span class="sxs-lookup"><span data-stu-id="27c08-p153">We recommend that you configure the cluster quorum settings to use a file share witness. To do so, use these steps:</span></span>
    
   - <span data-ttu-id="27c08-324">クラスター名を右クリックし、[**他の操作**]、[**クラスター クォーラム設定の構成**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="27c08-324">Right-click the cluster name, click **More Actions**, and click **Configure Cluster Quorum Settings**.</span></span>
    
   - <span data-ttu-id="27c08-325">[**クォーラム構成オプションの選択**] ページで、[**クォーラム監視を選択する**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="27c08-325">In the **Select Quorum Configuration Option** page, click **Select the quorum witness**.</span></span>
    
   - <span data-ttu-id="27c08-326">[**クォーラム監視の選択**] ページで、[**ファイル共有監視を構成する**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="27c08-326">In the **Select Quorum Witness** page, click **Configure a file share witness**.</span></span>
    
   - <span data-ttu-id="27c08-327">[**ファイル共有監視の構成**] ページで、使用するファイル共有のパスを入力し、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="27c08-327">In the **Configure File Share Witness** page, type the path of the file share you want to use, and then click **Next**.</span></span>
    
   - <span data-ttu-id="27c08-328">[**確認**] ページで、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="27c08-328">On the **Confirmation** page, click **Next**.</span></span>
    
5. <span data-ttu-id="27c08-329">クラスター内の各サーバーの SQL Server 構成マネージャーで、"Always On" を有効にします。</span><span class="sxs-lookup"><span data-stu-id="27c08-329">On each server in the cluster, enable Always On in SQL Server Configuration Manager.</span></span>
    
   - <span data-ttu-id="27c08-p154">SQL Server 構成マネージャーを開きます。画面左側のツリーで、[**SQL Server のサービス**] をクリックし、SQL Server サービスをダブルクリックします。</span><span class="sxs-lookup"><span data-stu-id="27c08-p154">Open SQL Server Configuration Manager. In the tree on the left side of the screen, click **SQL Server Services**, then double-click the SQL Server service.</span></span> 
    
   - <span data-ttu-id="27c08-p155">[**プロパティ**] ボックスで、[**AlwaysOn 高可用性**] タブを選択します。[**AlwaysOn 可用性グループを有効にする**] チェック ボックスをオンにします。SQL Server サービスを再開するよう求めるメッセージが表示されたら、サービスを再開します。</span><span class="sxs-lookup"><span data-stu-id="27c08-p155">In the **Properties** box, select the **AlwaysOn High Availability** tab. Select the **Enable AlwaysOn Availability Groups** check box. Restart the SQL Server service when prompted.</span></span>
    
6. <span data-ttu-id="27c08-334">可用性グループを作成します。</span><span class="sxs-lookup"><span data-stu-id="27c08-334">Create the availability group.</span></span>
    
   - <span data-ttu-id="27c08-335">SQL Server Management Studio を開き、SQL Server インスタンスに接続します。</span><span class="sxs-lookup"><span data-stu-id="27c08-335">Open SQL Server Management Studio, and connect to the SQL Server instance.</span></span>
    
   - <span data-ttu-id="27c08-p156">オブジェクト エクスプローラーで、[**AlwaysOn 高可用性**] フォルダーを展開します。[**可用性グループ**] フォルダーを右クリックし、[**新しい可用性グループ ウィザード**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="27c08-p156">In Object Explorer, expand the **AlwaysOn High Availability** folder. Right-click the **Availability Groups** folder and click **New Availability Group Wizard**.</span></span>
    
   - <span data-ttu-id="27c08-338">[**説明**] ページが表示されたら、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="27c08-338">If the **Introduction** page appears, click **Next**.</span></span>
    
   - <span data-ttu-id="27c08-339">[**可用性グループ名の指定**] ページで、可用性グループの名前を入力し、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="27c08-339">In the **Specify Availability Group Name** page, type the name of the Availability group, and click **Next**.</span></span>
    
   - <span data-ttu-id="27c08-340">データベースの選択] ページでは、AlwaysOn 可用性グループに追加するデータベースを選択します。</span><span class="sxs-lookup"><span data-stu-id="27c08-340">In the Select Databases page, select the databases that you want to include in the AlwaysOn Availability Group.</span></span> <span data-ttu-id="27c08-341">続いて [ **次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="27c08-341">Then click **Next**.</span></span>
    
    <span data-ttu-id="27c08-342">**ReportServer**、 **ReportServerTempDB**、またはデータベースの永続的なチャットに含めないで、AlwaysOn 可用性グループと、このシナリオではサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="27c08-342">Do not include the **ReportServer**, **ReportServerTempDB**, or Persistent Chat databases in the AlwaysOn Availability Group, as these are not supported in this scenario.</span></span> <span data-ttu-id="27c08-343">AlwaysOn 可用性グループで、ビジネスのサーバー データベースの他のすべての Skype を含めることができます。</span><span class="sxs-lookup"><span data-stu-id="27c08-343">You can include all other Skype for Business Server databases in the AlwaysOn Availability Group.</span></span>
    
   - <span data-ttu-id="27c08-344">[**レプリカの指定**] ページで、[**レプリカ**] タブをクリックします。続いて [**レプリカの追加**] ボタンをクリックし、Windows Server フェールオーバー クラスターのノードとして参加させた他の SQL インスタンスに接続します。</span><span class="sxs-lookup"><span data-stu-id="27c08-344">In the **Specify Replicas** page, click the **Replicas** tab. Then click the **Add Replicas** button, and connect to the other SQL instances that you joined as nodes of the Windows Server Failover Cluster.</span></span>
    
   - <span data-ttu-id="27c08-p159">各インスタンスの [**自動フェールオーバー**] オプションと [**同期コミット**] オプションをオンにします。[**読み取り可能なセカンダリ**] オプションはオンにしないでください。</span><span class="sxs-lookup"><span data-stu-id="27c08-p159">For each instance, select the **Automatic Failover** and **Synchronous Commit** options. Do not select the **Readable Secondary** option.</span></span>
    
   - <span data-ttu-id="27c08-347">[**エンドポイント**] タブをクリックし、[**ポート番号**] が "5022" に設定されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="27c08-347">Click the **Endpoints** tab and verify that **Port Number** is set to 5022.</span></span>
    
   - <span data-ttu-id="27c08-p160">[**リスナー**] タブをクリックし、[**可用性グループ リスナーの作成**] オプションをオンにします。そのオプションの下で、リスナーの名前を入力し、[**ポート**] を "1433" (他のポートはこのオプションではサポートされません) に設定します。</span><span class="sxs-lookup"><span data-stu-id="27c08-p160">Click the **Listener** tab, and select the **Create an availability group listener** option. Under that option, type a name for the listener, and set the **Port** to 1433 (other ports are not supported for this option).</span></span>
    
   - <span data-ttu-id="27c08-350">[**追加**] をクリックし、[**IPv4 アドレス**] ボックスに優先させる仮想 IP アドレスを入力して、[**OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="27c08-350">Click **Add**, and then in the **IPv4 Address** box, provide your preferred virtual IP address, and then click **OK**.</span></span>
    
   - <span data-ttu-id="27c08-p161">[**最初のデータの同期を選択**] ページで [完全] を選択します。レプリカがアクセスでき、両方のレプリカにより使用される SQL Server サービス アカウントが書き込みアクセス許可を持っているフォルダーを指定します。続いて、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="27c08-p161">In the **Select Initial Data Synchronization** page, select Full, and specify a folder that is accessible to the replicas, and that the SQL Server service account used by both replicas has Write permissions for. Then click **Next**.</span></span>
    
    <span data-ttu-id="27c08-p162">このファイル共有は、データベースを初期化した時点で一時的に使用されます。大きなデータベースを扱う場合、使用するネットワーク帯域幅でデータベース バックアップのサイズに対応できない場合に備えて、データベースを手動で初期化することを推奨します。</span><span class="sxs-lookup"><span data-stu-id="27c08-p162">This file share will be used temporarily when you initialize the databases. If you are dealing with large databases, we recommend that you manually initialize them in case your network bandwidth cannot accommodate the size of the database backups.</span></span>
    
    - <span data-ttu-id="27c08-355">[検証] ページで、すべての検証チェックが成功したことを確認し、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="27c08-355">In the Validation page, verify that all validation checks are successful, then click **Next**.</span></span>
    
   - <span data-ttu-id="27c08-356">[**概要**] ページで、すべての設定を確認し、[完了] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="27c08-356">In the **Summary** page, verify all settings and click Finish.</span></span>
    
7. <span data-ttu-id="27c08-357">AlwaysOn 可用性グループ リスナーを指定する新しいストアを作成します。</span><span class="sxs-lookup"><span data-stu-id="27c08-357">Create a new store specifying the AlwaysOn Availability Group listener.</span></span>
    
   - <span data-ttu-id="27c08-358">トポロジ ビルダーを開きます。</span><span class="sxs-lookup"><span data-stu-id="27c08-358">Open Topology Builder.</span></span> <span data-ttu-id="27c08-359">トポロジで、[**共有コンポーネント**] を展開し、[**SQL Server ストア**] を右クリックして、[**新しい SQL Server ストア**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="27c08-359">In your topology, expand **Shared Components**, right-click **SQL Server Stores**, and click **New SQL Server Store**.</span></span>
    
   - <span data-ttu-id="27c08-360">[**新しい SQL ストアの定義**] ページで、まず [**高可用性の設定**] チェック ボックスをオンにしてから、SQL AlwaysOn 可用性グループがドロップダウン ボックスに表示されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="27c08-360">In the **Define New SQL Store** page, first select the **High Availability Settings** check box, and then make sure that SQL AlwaysOn Availability Groups appears in the drop-down box.</span></span>
    
   - <span data-ttu-id="27c08-361">[**SQL Server の可用性グループのリスナーの FQDN**] ボックスに、可用性グループを作成したときに作成したリスナーの FQDN を入力します。</span><span class="sxs-lookup"><span data-stu-id="27c08-361">In the **SQL Server Availability Listener FQDN** box, type the FQDN of the listener you created when you created the availability group.</span></span>
    
   - <span data-ttu-id="27c08-362">**SQL Server の FQDN** ] ボックスに、AlwaysOn 可用性グループのプライマリ ノードの FQDN を入力し、し、[ **OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="27c08-362">In the **SQL Server FQDN** box, type the FQDN of the primary node of the AlwaysOn Availability Group, and then click **OK**.</span></span>
    
8. <span data-ttu-id="27c08-363">新しい AlwaysOn 可用性グループをフロント エンド プールに関連付けます。</span><span class="sxs-lookup"><span data-stu-id="27c08-363">Associate the new AlwaysOn Availability Group with the Front End pool.</span></span>
    
   - <span data-ttu-id="27c08-364">トポロジ ビルダーでは、AlwaysOn 可用性グループに関連付けるには、プールを右クリックし、**プロパティの編集**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="27c08-364">In Topology Builder, right-click the pool to associate with the AlwaysOn Availability Group, and click **Edit Properties**.</span></span>
    
   - <span data-ttu-id="27c08-365">[**関連付け**の**SQL Server ストア**] ボックスに、AlwaysOn 可用性グループを選択します。</span><span class="sxs-lookup"><span data-stu-id="27c08-365">Under **Associations**, in the **SQL Server Store** box, select the AlwaysOn Availability Group.</span></span> <span data-ttu-id="27c08-366">AlwaysOn 可用性グループに移動先となるプール内の他のデータベースの同じグループを選択します。</span><span class="sxs-lookup"><span data-stu-id="27c08-366">Select the same group for any other databases in the pool which you want to move to the AlwaysOn Availability Group.</span></span>
    
   - <span data-ttu-id="27c08-367">AlwaysOn 可用性グループに必要なすべてのデータベースが設定されていることを確認したら、[ **OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="27c08-367">When you're sure that all needed databases are set to the AlwaysOn Availability Group, click **OK**.</span></span>
    
9. <span data-ttu-id="27c08-p165">トポロジを公開します。[**操作**] メニューから、[**トポロジ**]、[**公開**] の順にクリックします。続いて確認ページで [**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="27c08-p165">Publish the topology. From the **Action** menu click **Topology** and then **Publish**. Then in the confirmation page click **Next**.</span></span>
    
10. <span data-ttu-id="27c08-371">AlwaysOn 可用性グループのレプリカの各 SQL ログインしているかどうかを確認するのにはいくつかの最終的な手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="27c08-371">Perform some final steps to make sure that the SQL logins are on each of the replicas in the AlwaysOn Availability Group.</span></span>
    
    - <span data-ttu-id="27c08-372">トポロジ ビルダーを開き**既存の展開からトポロジをダウンロード**するを選択して**[ok]**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="27c08-372">Open Topology Builder, select **Download topology from existing deployment**, and click **OK**.</span></span>
    
    - <span data-ttu-id="27c08-373">[Skype for Business Server]、使用するトポロジ、[**SQL Server ストア**] の順に展開します。</span><span class="sxs-lookup"><span data-stu-id="27c08-373">Expand Skype for Business Server, expand your topology, and expand **SQL Server Stores**.</span></span> <span data-ttu-id="27c08-374">新しい AlwaysOn 可用性グループの SQL ストアを右クリックし、をクリックして * * 編集プロパティ * *。</span><span class="sxs-lookup"><span data-stu-id="27c08-374">Right-click the SQL store of the new AlwaysOn Availability Group, and click ** Edit Properties**.</span></span>
    
    - <span data-ttu-id="27c08-375">**SQL Server の FQDN** ] ボックスで、ページの下部にある AlwaysOn 可用性グループのリスナーの FQDN の値を変更します。</span><span class="sxs-lookup"><span data-stu-id="27c08-375">At the bottom of the page, in the **SQL Server FQDN** box, change the value to the FQDN of the Listener of the AlwaysOn Availability Group.</span></span>
    
    - <span data-ttu-id="27c08-p167">トポロジを公開します。[**操作**] メニューから、[**トポロジ**]、[**公開**] の順にクリックします。続いて、確認ページで [**次へ**] をクリックします。新しいトポロジがレプリケートされるまで数分待ちます。</span><span class="sxs-lookup"><span data-stu-id="27c08-p167">Publish the topology. From the **Action** menu click **Topology** and then **Publish**. Then in the confirmation page click **Next**. Then wait a few minutes for the new topology to replicate.</span></span>
    
    - <span data-ttu-id="27c08-380">SQL Server Management Studio を開き AlwaysOn 可用性グループに移動します。</span><span class="sxs-lookup"><span data-stu-id="27c08-380">Open SQL Server Management Studio, and navigate to the AlwaysOn Availability Group.</span></span> <span data-ttu-id="27c08-381">AlwaysOn 可用性グループのセカンダリ レプリカへのフェールオーバーを行います。</span><span class="sxs-lookup"><span data-stu-id="27c08-381">Fail it over to a secondary replica.</span></span>
    
    - <span data-ttu-id="27c08-382">ビジネス サーバー管理シェルの Skype を開きこのレプリカの SQL ログインを作成するのには、次のコマンドレットを入力します。</span><span class="sxs-lookup"><span data-stu-id="27c08-382">Open Skype for Business Server Management Shell and type the following cmdlet to create the SQL logins on this replica:</span></span>
    
     ```
     Install-CsDatabase -Update
     ```

     - <span data-ttu-id="27c08-383">前の 2 つの手順を繰り返します (セカンダリ レプリカでは、グループをフェールオーバーしを使用して、 `Install-CsDatabase -Update`)、グループ内の各レプリカのです。</span><span class="sxs-lookup"><span data-stu-id="27c08-383">Repeat the previous two steps (fail over the group to a secondary replica, then use  `Install-CsDatabase -Update`) for each replica in the group.</span></span>
    

