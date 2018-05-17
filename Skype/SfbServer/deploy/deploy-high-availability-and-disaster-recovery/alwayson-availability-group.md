---
title: ビジネス サーバー 2015 の Skype のバック エンド サーバーに常時接続の可用性グループを展開します。
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
description: (インストール)、常に可用性グループに、Skype のビジネス サーバーの展開を展開します。
ms.openlocfilehash: ed6155ca1d3c7b24450bd8ca5099c2f6fc75e8a4
ms.sourcegitcommit: 5a0b3fe49b64f08979c89443f66b15827034e755
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/17/2018
---
# <a name="deploy-an-always-on-availability-group-on-a-back-end-server-in-skype-for-business-server-2015"></a><span data-ttu-id="f7f08-103">ビジネス サーバー 2015 の Skype のバック エンド サーバーに常時接続の可用性グループを展開します。</span><span class="sxs-lookup"><span data-stu-id="f7f08-103">Deploy an Always On Availability Group on a Back End Server in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="f7f08-104">(インストール)、常に上の可用性グループ (AG)、Skype のビジネス サーバーの展開を展開します。</span><span class="sxs-lookup"><span data-stu-id="f7f08-104">Deploy (install) an Always On Availability Group (AG) in your Skype for Business Server deployment.</span></span>
  
<span data-ttu-id="f7f08-105">AG をどのように展開することを新しいプール、ミラーリングを使用する既存のプールまたはバックエンド データベースの高可用性がされていない既存のプールに展開するかどうかによって異なります。</span><span class="sxs-lookup"><span data-stu-id="f7f08-105">How you deploy an AG depends on whether you are deploying it in a new pool, an existing pool that uses mirroring, or an existing pool that currently has no high availability for the Back End database.</span></span>
  
> [!NOTE]
> <span data-ttu-id="f7f08-106">AG を使用して永続的なチャット サーバーの役割ではサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="f7f08-106">Using an AG with a Persistent Chat Server role is not supported.</span></span> 
  
- [<span data-ttu-id="f7f08-107">常に可用性グループに新しいフロント エンド プールでの展開します。</span><span class="sxs-lookup"><span data-stu-id="f7f08-107">Deploy an Always On Availability Group on a new Front End pool</span></span>](alwayson-availability-group.md#BKMK_NewPool_CreateAlwaysOnGroup)
    
- [<span data-ttu-id="f7f08-108">常に可用性グループにデータベース ミラーリングを使用する既存のプールでの展開します。</span><span class="sxs-lookup"><span data-stu-id="f7f08-108">Deploy an Always On Availability Group on an existing pool that uses database mirroring</span></span>](alwayson-availability-group.md#BKMK_MirroredPool_CreateAlwaysOnGroup)
    
- [<span data-ttu-id="f7f08-109">常に可用性グループにデータベース ミラーリングを使用しない既存のプールでの展開します。</span><span class="sxs-lookup"><span data-stu-id="f7f08-109">Deploy an Always On Availability Group on an existing pool that does not use database mirroring</span></span>](alwayson-availability-group.md#BKMK_NoHAPool_CreateAlwaysOnGroup)
    
## <a name="deploy-an-always-on-availability-group-on-a-new-front-end-pool"></a><span data-ttu-id="f7f08-110">常に可用性グループに新しいフロント エンド プールでの展開します。</span><span class="sxs-lookup"><span data-stu-id="f7f08-110">Deploy an Always On Availability Group on a new Front End pool</span></span>
<span data-ttu-id="f7f08-111"><a name="BKMK_NewPool_CreateAlwaysOnGroup"> </a></span><span class="sxs-lookup"><span data-stu-id="f7f08-111"></span></span>

1. <span data-ttu-id="f7f08-112">AG の一部となるすべてのデータベース サーバーのフェールオーバー クラスタ リング機能を有効にします。</span><span class="sxs-lookup"><span data-stu-id="f7f08-112">Enable the Failover Clustering feature on all the database servers which will be part of the AG.</span></span> <span data-ttu-id="f7f08-113">各サーバーで、以下の作業を行います。</span><span class="sxs-lookup"><span data-stu-id="f7f08-113">On each server, do the following</span></span>
    
   - <span data-ttu-id="f7f08-114">サーバー マネージャーを開き、[**役割と機能の追加**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f7f08-114">Open Server Manager and click **Add roles and features**.</span></span>
    
   - <span data-ttu-id="f7f08-p102">[**機能の選択**] ボックスが表示されるまで [**次へ**] をクリックします。このボックスで、[**フェールオーバー クラスタリング**] チェック ボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="f7f08-p102">Click **Next** until you reach the **Select features** box. Here, select the **Failover Clustering** check box.</span></span>
    
   - <span data-ttu-id="f7f08-117">[**フェールオーバー クラスタリングに必要な機能を追加しますか?**] ボックスで、[**機能の追加**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f7f08-117">In the **Add features that are required for Failover Clustering?** box, click **Add Features**.</span></span>
    
   - <span data-ttu-id="f7f08-118">[**インストール**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f7f08-118">Click **Install**.</span></span>
    
2. <span data-ttu-id="f7f08-119">クラスター構成を検証します。</span><span class="sxs-lookup"><span data-stu-id="f7f08-119">Validate the cluster configuration.</span></span>
    
   - <span data-ttu-id="f7f08-120">サーバー マネージャーで、[**ツール**] メニューをクリックし、[**フェールオーバー クラスター マネージャー**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f7f08-120">In Server Manager, click the **Tools** menu and then click **Failover Cluster Manager**.</span></span>
    
   - <span data-ttu-id="f7f08-121">画面右側の [**操作**] で、[**構成の検証**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f7f08-121">Under **Actions** on the right side of the screen, click **Validate Configuration**.</span></span>
    
   - <span data-ttu-id="f7f08-122">[**開始する前に**] ページで、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f7f08-122">On the **Before You Begin** page, click **Next**.</span></span>
    
   - <span data-ttu-id="f7f08-123">クラスターに追加するサーバーを選択し、[**すべてのテストを実行**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f7f08-123">Select the servers to add to the cluster, and then click **Run all tests**.</span></span>
    
   - <span data-ttu-id="f7f08-124">[**概要**] ボックスで、ウィザードに表示されるエラーを確認してください。</span><span class="sxs-lookup"><span data-stu-id="f7f08-124">In the**Summary** box, check any errors that the wizard reports.</span></span> <span data-ttu-id="f7f08-125">確認したら、[**完了**] をクリックして検証を完了します。</span><span class="sxs-lookup"><span data-stu-id="f7f08-125">Then click **Finish** to complete the validation.</span></span>
    
    <span data-ttu-id="f7f08-p104">特に、共有ストレージを使用していない場合、通常はウィザードにより複数の警告が報告されます。共有ストレージを使用する必要はありませんが、[**エラー**] でメッセージが表示されている場合は、作業を続行する前にこれらの問題を修正する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f7f08-p104">The wizard will probably report several warnings, especially if you are not using shared storage. You are not required to use shared storage. However, if you see any **Error** messages, you must fix those issues before continuing.</span></span>
    
3. <span data-ttu-id="f7f08-129">(WSFC) Windows Server フェールオーバー クラスターを作成します。</span><span class="sxs-lookup"><span data-stu-id="f7f08-129">Create the Windows Server Failover Cluster (WSFC).</span></span>
    
   - <span data-ttu-id="f7f08-130">[**フェールオーバー クラスター管理**] ウィザードで、[**フェールオーバー クラスター管理**]、[**クラスターの作成**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="f7f08-130">In the **Failover Cluster Management** wizard, right-click **Failover Cluster Management**, then click **Create Cluster**.</span></span>
    
   - <span data-ttu-id="f7f08-131">[**開始する前に**] ページで、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f7f08-131">On the **Before You Begin** page, click **Next**.</span></span>
    
   - <span data-ttu-id="f7f08-p105">クラスター名と IP アドレスを追加します。設定が検証されたら、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f7f08-p105">Add the cluster name and IP address. When the settings are validated, click **Next**.</span></span>
    
   - <span data-ttu-id="f7f08-134">[確認] ページで、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f7f08-134">On the Confirmation page, click **Next**.</span></span>
    
   - <span data-ttu-id="f7f08-135">クラスターが作成されたら、[**完了**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f7f08-135">After the cluster is created, click **Finish**.</span></span>
    
4. <span data-ttu-id="f7f08-p106">ファイル共有監視を使用するようにクラスター クォーラム設定を構成することをお勧めします。このためには、以下の手順を行います。</span><span class="sxs-lookup"><span data-stu-id="f7f08-p106">We recommend that you configure the cluster quorum settings to use a file share witness. To do so, use these steps:</span></span>
    
   - <span data-ttu-id="f7f08-138">クラスター名を右クリックし、[**他の操作**]、[**クラスター クォーラム設定の構成**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="f7f08-138">Right-click the cluster name, click **More Actions**, and click **Configure Cluster Quorum Settings**.</span></span>
    
   - <span data-ttu-id="f7f08-139">[**クォーラム構成オプションの選択**] ページで、[**クォーラム監視を選択する**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f7f08-139">In the **Select Quorum Configuration Option** page, click **Select the quorum witness**.</span></span>
    
   - <span data-ttu-id="f7f08-140">[**クォーラム監視の選択**] ページで、[**ファイル共有監視を構成する**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f7f08-140">In the **Select Quorum Witness** page, click **Configure a file share witness**.</span></span>
    
   - <span data-ttu-id="f7f08-141">[**ファイル共有監視の構成**] ページで、使用するファイル共有のパスを入力し、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f7f08-141">In the **Configure File Share Witness** page, type the path of the file share you want to use, and then click **Next**.</span></span>
    
   - <span data-ttu-id="f7f08-142">[**確認**] ページで、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f7f08-142">On the **Confirmation** page, click **Next**.</span></span>
    
5. <span data-ttu-id="f7f08-143">クラスター内の各サーバーでは、AG 機能で SQL Server 構成マネージャーを有効にします。</span><span class="sxs-lookup"><span data-stu-id="f7f08-143">On each server in the cluster, enable the AG feature in SQL Server Configuration Manager.</span></span>
    
   - <span data-ttu-id="f7f08-p107">SQL Server 構成マネージャーを開きます。画面左側のツリーで、[**SQL Server のサービス**] をクリックし、SQL Server サービスをダブルクリックします。</span><span class="sxs-lookup"><span data-stu-id="f7f08-p107">Open SQL Server Configuration Manager. In the tree on the left side of the screen, click **SQL Server Services**, then double-click the SQL Server service.</span></span> 
    
   - <span data-ttu-id="f7f08-p108">[**プロパティ**] ボックスで、[**AlwaysOn 高可用性**] タブを選択します。[**AlwaysOn 可用性グループを有効にする**] チェック ボックスをオンにします。SQL Server サービスを再開するよう求めるメッセージが表示されたら、サービスを再開します。</span><span class="sxs-lookup"><span data-stu-id="f7f08-p108">In the **Properties** box, select the **AlwaysOn High Availability** tab. Select the **Enable AlwaysOn Availability Groups** check box. Restart the SQL Server service when prompted.</span></span>
    
6. <span data-ttu-id="f7f08-148">可用性グループを作成します。</span><span class="sxs-lookup"><span data-stu-id="f7f08-148">Create the availability group.</span></span>
    
   - <span data-ttu-id="f7f08-149">SQL Server Management Studio を開き、SQL Server インスタンスに接続します。</span><span class="sxs-lookup"><span data-stu-id="f7f08-149">Open SQL Server Management Studio, and connect to the SQL Server instance.</span></span>
    
   - <span data-ttu-id="f7f08-150">オブジェクト エクスプ ローラーで、**常に高可用性**のフォルダーを展開します。</span><span class="sxs-lookup"><span data-stu-id="f7f08-150">In Object Explorer, expand the **Always On High Availability** folder.</span></span> <span data-ttu-id="f7f08-151">[**可用性グループ**] フォルダーを右クリックし、[**新しい可用性グループ ウィザード**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f7f08-151">Right-click the **Availability Groups** folder and click **New Availability Group Wizard**.</span></span>
    
   - <span data-ttu-id="f7f08-152">[**説明**] ページが表示されたら、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f7f08-152">If the **Introduction** page appears, click **Next**.</span></span>
    
   - <span data-ttu-id="f7f08-153">[**可用性グループ名の指定**] ページで、可用性グループの名前を入力し、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f7f08-153">In the **Specify Availability Group Name** page, type the name of the Availability group, and click **Next**.</span></span>
    
   - <span data-ttu-id="f7f08-154">データベースの選択] ページでは、AlwaysOn 可用性グループに追加するデータベースを選択します。</span><span class="sxs-lookup"><span data-stu-id="f7f08-154">In the Select Databases page, select the databases that you want to include in the AlwaysOn Availability Group.</span></span> <span data-ttu-id="f7f08-155">続いて [ **次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f7f08-155">Then click **Next**.</span></span>
    
    <span data-ttu-id="f7f08-156">**ReportServer**、 **ReportServerTempDB**、またはデータベースの永続的なチャットに含めないで、AlwaysOn 可用性グループと、このシナリオではサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="f7f08-156">Do not include the **ReportServer**, **ReportServerTempDB**, or Persistent Chat databases in the AlwaysOn Availability Group, as these are not supported in this scenario.</span></span> <span data-ttu-id="f7f08-157">AlwaysOn 可用性グループで、ビジネスのサーバー データベースの他のすべての Skype を含めることができます。</span><span class="sxs-lookup"><span data-stu-id="f7f08-157">You can include all other Skype for Business Server databases in the AlwaysOn Availability Group.</span></span>
    
   - <span data-ttu-id="f7f08-158">[**レプリカの指定**] ページで、[**レプリカ**] タブをクリックします。続いて [**レプリカの追加**] ボタンをクリックし、Windows Server フェールオーバー クラスターのノードとして参加させた他の SQL インスタンスに接続します。</span><span class="sxs-lookup"><span data-stu-id="f7f08-158">In the **Specify Replicas** page, click the **Replicas** tab. Then click the **Add Replicas** button, and connect to the other SQL instances that you joined as nodes of the Windows Server Failover Cluster.</span></span>
    
   - <span data-ttu-id="f7f08-p112">各インスタンスの [**自動フェールオーバー**] オプションと [**同期コミット**] オプションをオンにします。[**読み取り可能なセカンダリ**] オプションはオンにしないでください。</span><span class="sxs-lookup"><span data-stu-id="f7f08-p112">For each instance, select the **Automatic Failover** and **Synchronous Commit** options. Do not select the **Readable Secondary** option.</span></span>
    
   - <span data-ttu-id="f7f08-161">[**エンドポイント**] タブをクリックし、[**ポート番号**] が "5022" に設定されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="f7f08-161">Click the **Endpoints** tab and verify that **Port Number** is set to 5022.</span></span>
    
   - <span data-ttu-id="f7f08-p113">[**リスナー**] タブをクリックし、[**可用性グループ リスナーの作成**] オプションをオンにします。そのオプションの下で、リスナーの名前を入力し、[**ポート**] を "1433" (他のポートはこのオプションではサポートされません) に設定します。</span><span class="sxs-lookup"><span data-stu-id="f7f08-p113">Click the **Listener** tab, and select the **Create an availability group listener** option. Under that option, type a name for the listener, and set the **Port** to 1433 (other ports are not supported for this option).</span></span>
    
   - <span data-ttu-id="f7f08-164">[**追加**] をクリックし、[**IPv4 アドレス**] ボックスに優先させる仮想 IP アドレスを入力して、[**OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f7f08-164">Click **Add**, and then in the **IPv4 Address** box, provide your preferred virtual IP address, and then click **OK**.</span></span>
    
   - <span data-ttu-id="f7f08-p114">[**最初のデータの同期を選択**] ページで [完全] を選択します。レプリカがアクセスでき、両方のレプリカにより使用される SQL Server サービス アカウントが書き込みアクセス許可を持っているフォルダーを指定します。続いて、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f7f08-p114">In the **Select Initial Data Synchronization** page, select Full, and specify a folder that is accessible to the replicas, and that the SQL Server service account used by both replicas has Write permissions for. Then click **Next**.</span></span>
    
    <span data-ttu-id="f7f08-p115">このファイル共有は、データベースを初期化した時点で一時的に使用されます。大きなデータベースを扱う場合、使用するネットワーク帯域幅でデータベース バックアップのサイズに対応できない場合に備えて、データベースを手動で初期化することを推奨します。</span><span class="sxs-lookup"><span data-stu-id="f7f08-p115">This file share will be used temporarily when you initialize the databases. If you are dealing with large databases, we recommend that you manually initialize them in case your network bandwidth cannot accommodate the size of the database backups.</span></span>
    
   - <span data-ttu-id="f7f08-169">[検証] ページで、すべての検証チェックが成功したことを確認し、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f7f08-169">In the Validation page, verify that all validation checks are successful, then click **Next**.</span></span>
    
   - <span data-ttu-id="f7f08-170">**概要**] ページで、すべての設定を確認して、[完了] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f7f08-170">In the**Summary** page, verify all settings and click Finish.</span></span>
    
7. <span data-ttu-id="f7f08-171">説明したように、フロント エンド プールを作成するトポロジ ビルダーを使用して、[を作成するビジネス サーバー 2015 の Skype の新しいトポロジを公開し、](../../deploy/install/create-and-publish-new-topology.md)。</span><span class="sxs-lookup"><span data-stu-id="f7f08-171">Use Topology Builder to create the Front End pool, as explained in [Create and publish new topology in Skype for Business Server 2015](../../deploy/install/create-and-publish-new-topology.md).</span></span> <span data-ttu-id="f7f08-172">実行すると、プールの SQL ストアとして、AG を指定します。</span><span class="sxs-lookup"><span data-stu-id="f7f08-172">When you do, specify the AG as the SQL store for the pool.</span></span>
    
8. <span data-ttu-id="f7f08-173">プールと AG が配置されると、SQL ログインが各 AlwaysOn 可用性グループのレプリカであることを確認するのにはいくつかの最終的な手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="f7f08-173">After the pool and the AG are deployed, perform some final steps to make sure that the SQL logins are on each of the replicas in the AlwaysOn Availability Group.</span></span> 
    
   - <span data-ttu-id="f7f08-174">トポロジ ビルダーを開き**既存の展開からトポロジをダウンロード**するを選択して **[ok]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f7f08-174">Open Topology Builder, select **Download topology from existing deployment**, and click **OK**.</span></span>
    
   - <span data-ttu-id="f7f08-175">[Skype for Business Server]、使用するトポロジ、[**SQL Server ストア**] の順に展開します。</span><span class="sxs-lookup"><span data-stu-id="f7f08-175">Expand Skype for Business Server, expand your topology, and expand **SQL Server Stores**.</span></span> <span data-ttu-id="f7f08-176">新しい AlwaysOn 可用性グループの SQL ストアを右クリックし、をクリックして * * 編集プロパティ * *。</span><span class="sxs-lookup"><span data-stu-id="f7f08-176">Right-click the SQL store of the new AlwaysOn Availability Group, and click ** Edit Properties**.</span></span>
    
    - <span data-ttu-id="f7f08-177">[ **SQL Server の FQDN** ] ボックスで、ページの下部にある AG のリスナーの FQDN の値を変更します。</span><span class="sxs-lookup"><span data-stu-id="f7f08-177">At the bottom of the page, in the **SQL Server FQDN** box, change the value to the FQDN of the Listener of the AG.</span></span>
    
   - <span data-ttu-id="f7f08-p118">トポロジを公開します。[**操作**] メニューから、[**トポロジ**]、[**公開**] の順にクリックします。続いて、確認ページで [**次へ**] をクリックします。新しいトポロジがレプリケートされるまで数分待ちます。</span><span class="sxs-lookup"><span data-stu-id="f7f08-p118">Publish the topology. From the **Action** menu click **Topology** and then **Publish**. Then in the confirmation page click **Next**. Then wait a few minutes for the new topology to replicate.</span></span>
    
   - <span data-ttu-id="f7f08-182">SQL Server Management Studio を開き AG に移動します。</span><span class="sxs-lookup"><span data-stu-id="f7f08-182">Open SQL Server Management Studio, and navigate to the AG.</span></span> <span data-ttu-id="f7f08-183">AlwaysOn 可用性グループのセカンダリ レプリカへのフェールオーバーを行います。</span><span class="sxs-lookup"><span data-stu-id="f7f08-183">Fail it over to a secondary replica.</span></span>
    
   - <span data-ttu-id="f7f08-184">ビジネス サーバー管理シェルの Skype を開きこのレプリカの SQL ログインを作成するのには、次のコマンドレットを入力します。</span><span class="sxs-lookup"><span data-stu-id="f7f08-184">Open Skype for Business Server Management Shell and type the following cmdlet to create the SQL logins on this replica:</span></span>
    
   ```
   Install-CsDatabase -Update
   ```

   - <span data-ttu-id="f7f08-185">前の 2 つの手順を繰り返します (セカンダリ レプリカでは、グループをフェールオーバーしを使用して、 `Install-CsDatabase -Update`)、グループ内の各レプリカのです。</span><span class="sxs-lookup"><span data-stu-id="f7f08-185">Repeat the previous two steps (fail over the group to a secondary replica, then use  `Install-CsDatabase -Update`) for each replica in the group.</span></span>
    
## <a name="deploy-an-always-on-availability-group-on-an-existing-pool-that-uses-database-mirroring"></a><span data-ttu-id="f7f08-186">常に可用性グループにデータベース ミラーリングを使用する既存のプールでの展開します。</span><span class="sxs-lookup"><span data-stu-id="f7f08-186">Deploy an Always On Availability Group on an existing pool that uses database mirroring</span></span>
<span data-ttu-id="f7f08-187"><a name="BKMK_MirroredPool_CreateAlwaysOnGroup"> </a></span><span class="sxs-lookup"><span data-stu-id="f7f08-187"></span></span>

> [!NOTE]
> <span data-ttu-id="f7f08-188">AG にアップグレードするプールでは、組織の中央管理ストアをホストしている場合必要があります最初に移動する CMS 別のプールにこのプールをアップグレードする前にします。</span><span class="sxs-lookup"><span data-stu-id="f7f08-188">If the pool you are upgrading to an AG hosts the Central Management store for your organization, you must first move the CMS to another pool before you upgrade this pool.</span></span> <span data-ttu-id="f7f08-189">プールを移動するには、Move-CsManagementServer コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="f7f08-189">Use the Move-CsManagementServer cmdlet to move the pool.</span></span> <span data-ttu-id="f7f08-190">組織内の別のプールがない、Standard Edition サーバーを一時的に展開し、AG にプールをアップグレードする前に、このサーバーに CMS を移動できます。</span><span class="sxs-lookup"><span data-stu-id="f7f08-190">If you do not have another pool in your organization, you can deploy a Standard Edition server temporarily and move the CMS to this server before you upgrade your pool to the AG.</span></span> 
  
1. <span data-ttu-id="f7f08-191">ビジネス サーバー管理シェルの Skype を開き、次のコマンドレットを入力すると、ミラーからのすべてのデータの主要なノードをフェールオーバーします。</span><span class="sxs-lookup"><span data-stu-id="f7f08-191">Fail over all data from the mirror to the principal node by opening Skype for Business Server Management Shell and typing the following cmdlet.</span></span>
    
   ```
   Invoke-CsDatabaseFailover -PoolFqdn <Pool FQDN> -DatabaseType <DatabaseType> -NewPrincipal "Primary"
   ```

    <span data-ttu-id="f7f08-p121">プール内の各データベースの種類に対してこのコマンドレットを繰り返します。次のコマンドレットを使用すると、このプールに格納されているすべてのデータベースの種類を見つけることができます。</span><span class="sxs-lookup"><span data-stu-id="f7f08-p121">Repeat this cmdlet for each database type in the pool. You can use the following cmdlet to find all the database types stored in this pool.</span></span>
     
   ```
   Get-CsPool -Identity <Pool FQDN>
   ```

2. <span data-ttu-id="f7f08-194">トポロジ ビルダーを使用して、プールからデータベース ミラーリングを削除する</span><span class="sxs-lookup"><span data-stu-id="f7f08-194">Use Topology Builder to remove database mirroring from the pool</span></span>
    
   - <span data-ttu-id="f7f08-195">トポロジ ビルダーを開きます。</span><span class="sxs-lookup"><span data-stu-id="f7f08-195">Open Topology Builder.</span></span> <span data-ttu-id="f7f08-196">トポロジで [**Enterprise Edition フロントエンド プール**] を展開し、プール名を右クリックし、[**プロパティの編集**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f7f08-196">In your topology, expand **Enterprise Edition Front End Pools**, right-click the name of the pool, and click **Edit Properties**.</span></span>
    
   - <span data-ttu-id="f7f08-197">プール内の各種類の SQL ストアに対して、[**SQL ストアのミラーリングを有効にする**] チェック ボックスをオフにします。</span><span class="sxs-lookup"><span data-stu-id="f7f08-197">For each type of SQL store in the pool, clear the **Enable SQL Store Mirroring** check box.</span></span>
    
3. <span data-ttu-id="f7f08-p123">変更したトポロジを公開します。[**操作**] メニューから、[**トポロジ**]、[**公開**] の順にクリックします。続いて確認ページで [**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f7f08-p123">Publish the changed topology. From the **Action** menu click **Topology** and then **Publish**. Then in the confirmation page click **Next**</span></span>
    
4. <span data-ttu-id="f7f08-201">SQL Server Management Studio を使用して、ミラーを解除します。</span><span class="sxs-lookup"><span data-stu-id="f7f08-201">Use SQL Server Management Studio to break the mirror.</span></span>
    
   - <span data-ttu-id="f7f08-p124">SQL Server Management Studio を開き、使用しているデータベースに移動し、[**タスク**] を右クリックし、[**ミラー**] をクリックします。続いて [**ミラーリングの削除**] をクリックし、[**OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f7f08-p124">Open SQL Server Management Studio, navigate to your databases, right-click **Tasks** and click **Mirror**. Then click **Remove Mirroring** and click **OK**.</span></span>
    
   - <span data-ttu-id="f7f08-204">AG に変換されるプール内のすべてのデータベースに対してこの手順を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="f7f08-204">Repeat this for all databases in the pool which will be converted to an AG.</span></span>
    
5. <span data-ttu-id="f7f08-205">AG の一部となるすべてのデータベース サーバーのフェールオーバー クラスタ リング機能を設定します。</span><span class="sxs-lookup"><span data-stu-id="f7f08-205">Set up the Failover Clustering feature on all the database servers which will be part of the AG.</span></span> <span data-ttu-id="f7f08-206">各サーバーで、以下の作業を行います。</span><span class="sxs-lookup"><span data-stu-id="f7f08-206">On each server, do the following</span></span>
    
   - <span data-ttu-id="f7f08-207">サーバー マネージャーを開き、[**役割と機能の追加**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f7f08-207">Open Server Manager and click **Add roles and features**.</span></span>
    
   - <span data-ttu-id="f7f08-p126">[**機能の選択**] ボックスが表示されるまで [**次へ**] をクリックします。このボックスで、[**フェールオーバー クラスタリング**] チェック ボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="f7f08-p126">Click **Next** until you reach the **Select features** box. Here, select the **Failover Clustering** check box.</span></span>
    
   - <span data-ttu-id="f7f08-210">[**フェールオーバー クラスタリングに必要な機能を追加しますか?**] ボックスで、[**機能の追加**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f7f08-210">In the **Add features that are required for Failover Clustering?** box, click **Add Features**.</span></span>
    
   - <span data-ttu-id="f7f08-211">[**インストール**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f7f08-211">Click **Install**.</span></span>
    
6. <span data-ttu-id="f7f08-212">クラスター構成を検証します。</span><span class="sxs-lookup"><span data-stu-id="f7f08-212">Validate the cluster configuration.</span></span>
    
   - <span data-ttu-id="f7f08-213">サーバー マネージャーで、[**ツール**] メニューをクリックし、[**フェールオーバー クラスター マネージャー**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f7f08-213">In Server Manager, click the **Tools** menu and then click **Failover Cluster Manager**.</span></span>
    
   - <span data-ttu-id="f7f08-214">画面右側の [**操作**] で、[**構成の検証**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f7f08-214">Under **Actions** on the right side of the screen, click **Validate Configuration**.</span></span>
    
   - <span data-ttu-id="f7f08-215">[**開始する前に**] ページで、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f7f08-215">On the **Before You Begin** page, click **Next**.</span></span>
    
   - <span data-ttu-id="f7f08-216">クラスターに追加するサーバーを選択し、[**すべてのテストを実行**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f7f08-216">Select the servers to add to the cluster, and then click **Run all tests**.</span></span>
    
   - <span data-ttu-id="f7f08-217">[**概要**] ボックスで、ウィザードに表示されるエラーを確認してください。</span><span class="sxs-lookup"><span data-stu-id="f7f08-217">In the**Summary** box, check any errors that the wizard reports.</span></span> <span data-ttu-id="f7f08-218">確認したら、[**完了**] をクリックして検証を完了します。</span><span class="sxs-lookup"><span data-stu-id="f7f08-218">Then click **Finish** to complete the validation.</span></span>
    
    <span data-ttu-id="f7f08-p128">特に、共有ストレージを使用していない場合、通常はウィザードにより複数の警告が報告されます。共有ストレージを使用する必要はありませんが、[**エラー**] でメッセージが表示されている場合は、作業を続行する前にこれらの問題を修正する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f7f08-p128">The wizard will probably report several warnings, especially if you are not using shared storage. You are not required to use shared storage. However, if you see any **Error** messages, you must fix those issues before continuing.</span></span>
    
7. <span data-ttu-id="f7f08-222">Windows Server フェールオーバー クラスターを作成します。</span><span class="sxs-lookup"><span data-stu-id="f7f08-222">Create the Windows Server Failover Cluster.</span></span>
    
   - <span data-ttu-id="f7f08-223">[**フェールオーバー クラスター管理**] ウィザードで、[**フェールオーバー クラスター管理**]、[**クラスターの作成**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="f7f08-223">In the **Failover Cluster Management** wizard, right-click **Failover Cluster Management**, then click **Create Cluster**.</span></span>
    
   - <span data-ttu-id="f7f08-224">[**開始する前に**] ページで、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f7f08-224">On the **Before You Begin** page, click **Next**.</span></span>
    
   - <span data-ttu-id="f7f08-p129">クラスター名と IP アドレスを追加します。設定が検証されたら、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f7f08-p129">Add the cluster name and IP address. When the settings are validated, click **Next**.</span></span>
    
   - <span data-ttu-id="f7f08-227">[確認] ページで、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f7f08-227">On the Confirmation page, click **Next**.</span></span>
    
   - <span data-ttu-id="f7f08-228">クラスターが作成されたら、[**完了**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f7f08-228">After the cluster is created, click **Finish**.</span></span>
    
8. <span data-ttu-id="f7f08-p130">ファイル共有監視を使用するようにクラスター クォーラム設定を構成することをお勧めします。このためには、以下の手順を行います。</span><span class="sxs-lookup"><span data-stu-id="f7f08-p130">We recommend that you configure the cluster quorum settings to use a file share witness. To do so, use these steps:</span></span>
    
   - <span data-ttu-id="f7f08-231">クラスター名を右クリックし、[**他の操作**]、[**クラスター クォーラム設定の構成**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="f7f08-231">Right-click the cluster name, click **More Actions**, and click **Configure Cluster Quorum Settings**.</span></span>
    
   - <span data-ttu-id="f7f08-232">[**クォーラム構成オプションの選択**] ページで、[**クォーラム監視を選択する**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f7f08-232">In the **Select Quorum Configuration Option** page, click **Select the quorum witness**.</span></span>
    
   - <span data-ttu-id="f7f08-233">[**クォーラム監視の選択**] ページで、[**ファイル共有監視を構成する**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f7f08-233">In the **Select Quorum Witness** page, click **Configure a file share witness**.</span></span>
    
   - <span data-ttu-id="f7f08-234">[**ファイル共有監視の構成**] ページで、使用するファイル共有のパスを入力し、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f7f08-234">In the **Configure File Share Witness** page, type the path of the file share you want to use, and then click **Next**.</span></span>
    
   - <span data-ttu-id="f7f08-235">[**確認**] ページで、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f7f08-235">On the **Confirmation** page, click **Next**.</span></span>
    
9. <span data-ttu-id="f7f08-236">クラスター内の各サーバーでは、AG 機能で SQL Server 構成マネージャーを有効にします。</span><span class="sxs-lookup"><span data-stu-id="f7f08-236">On each server in the cluster, enable the AG feature in SQL Server Configuration Manager.</span></span>
    
   - <span data-ttu-id="f7f08-p131">SQL Server 構成マネージャーを開きます。画面左側のツリーで、[**SQL Server のサービス**] をクリックし、SQL Server サービスをダブルクリックします。</span><span class="sxs-lookup"><span data-stu-id="f7f08-p131">Open SQL Server Configuration Manager. In the tree on the left side of the screen, click **SQL Server Services**, then double-click the SQL Server service.</span></span> 
    
   - <span data-ttu-id="f7f08-p132">[**プロパティ**] ボックスで、[**AlwaysOn 高可用性**] タブを選択します。[**AlwaysOn 可用性グループを有効にする**] チェック ボックスをオンにします。SQL Server サービスを再開するよう求めるメッセージが表示されたら、サービスを再開します。</span><span class="sxs-lookup"><span data-stu-id="f7f08-p132">In the **Properties** box, select the **AlwaysOn High Availability** tab. Select the **Enable AlwaysOn Availability Groups** check box. Restart the SQL Server service when prompted.</span></span>
    
10. <span data-ttu-id="f7f08-241">可用性グループを作成します。</span><span class="sxs-lookup"><span data-stu-id="f7f08-241">Create the availability group.</span></span>
    
    - <span data-ttu-id="f7f08-242">SQL Server Management Studio を開き、SQL Server インスタンスに接続します。</span><span class="sxs-lookup"><span data-stu-id="f7f08-242">Open SQL Server Management Studio, and connect to the SQL Server instance.</span></span>
    
    - <span data-ttu-id="f7f08-243">オブジェクト エクスプ ローラーで、**常に高可用性**のフォルダーを展開します。</span><span class="sxs-lookup"><span data-stu-id="f7f08-243">In Object Explorer, expand the **Always On High Availability** folder.</span></span> <span data-ttu-id="f7f08-244">[**可用性グループ**] フォルダーを右クリックし、[**新しい可用性グループ ウィザード**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f7f08-244">Right-click the **Availability Groups** folder and click **New Availability Group Wizard**.</span></span>
    
    - <span data-ttu-id="f7f08-245">[**説明**] ページが表示されたら、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f7f08-245">If the **Introduction** page appears, click **Next**.</span></span>
    
    - <span data-ttu-id="f7f08-246">[**可用性グループ名の指定**] ページで、可用性グループの名前を入力し、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f7f08-246">In the **Specify Availability Group Name** page, type the name of the Availability group, and click **Next**.</span></span>
    
    - <span data-ttu-id="f7f08-247">データベースの選択] ページでは、AlwaysOn 可用性グループに追加するデータベースを選択します。</span><span class="sxs-lookup"><span data-stu-id="f7f08-247">In the Select Databases page, select the databases that you want to include in the AlwaysOn Availability Group.</span></span> <span data-ttu-id="f7f08-248">続いて [ **次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f7f08-248">Then click **Next**.</span></span>
    
    <span data-ttu-id="f7f08-249">**ReportServer**、 **ReportServerTempDB**、またはデータベースの永続的なチャットに含めないで、AlwaysOn 可用性グループと、このシナリオではサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="f7f08-249">Do not include the **ReportServer**, **ReportServerTempDB**, or Persistent Chat databases in the AlwaysOn Availability Group, as these are not supported in this scenario.</span></span> <span data-ttu-id="f7f08-250">AlwaysOn 可用性グループで、ビジネスのサーバー データベースの他のすべての Skype を含めることができます。</span><span class="sxs-lookup"><span data-stu-id="f7f08-250">You can include all other Skype for Business Server databases in the AlwaysOn Availability Group.</span></span>
    
    - <span data-ttu-id="f7f08-251">[**レプリカの指定**] ページで、[**レプリカ**] タブをクリックします。続いて [**レプリカの追加**] ボタンをクリックし、Windows Server フェールオーバー クラスターのノードとして参加させた他の SQL インスタンスに接続します。</span><span class="sxs-lookup"><span data-stu-id="f7f08-251">In the **Specify Replicas** page, click the **Replicas** tab. Then click the **Add Replicas** button, and connect to the other SQL instances that you joined as nodes of the Windows Server Failover Cluster.</span></span>
    
    - <span data-ttu-id="f7f08-p136">各インスタンスの [**自動フェールオーバー**] オプションと [**同期コミット**] オプションをオンにします。[**読み取り可能なセカンダリ**] オプションはオンにしないでください。</span><span class="sxs-lookup"><span data-stu-id="f7f08-p136">For each instance, select the **Automatic Failover** and **Synchronous Commit** options. Do not select the **Readable Secondary** option.</span></span>
    
    - <span data-ttu-id="f7f08-254">[**エンドポイント**] タブをクリックし、[**ポート番号**] が "5022" に設定されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="f7f08-254">Click the **Endpoints** tab and verify that **Port Number** is set to 5022.</span></span>
    
     - <span data-ttu-id="f7f08-p137">[**リスナー**] タブをクリックし、[**可用性グループ リスナーの作成**] オプションをオンにします。そのオプションの下で、リスナーの名前を入力し、[**ポート**] を "1433" (他のポートはこのオプションではサポートされません) に設定します。</span><span class="sxs-lookup"><span data-stu-id="f7f08-p137">Click the **Listener** tab, and select the **Create an availability group listener** option. Under that option, type a name for the listener, and set the **Port** to 1433 (other ports are not supported for this option).</span></span>
    
    - <span data-ttu-id="f7f08-257">[**追加**] をクリックし、[**IPv4 アドレス**] ボックスに優先させる仮想 IP アドレスを入力して、[**OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f7f08-257">Click **Add**, and then in the **IPv4 Address** box, provide your preferred virtual IP address, and then click **OK**.</span></span>
    
    - <span data-ttu-id="f7f08-p138">[**最初のデータの同期を選択**] ページで [完全] を選択します。レプリカがアクセスでき、両方のレプリカにより使用される SQL Server サービス アカウントが書き込みアクセス許可を持っているフォルダーを指定します。続いて、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f7f08-p138">In the **Select Initial Data Synchronization** page, select Full, and specify a folder that is accessible to the replicas, and that the SQL Server service account used by both replicas has Write permissions for. Then click **Next**.</span></span>
    
    <span data-ttu-id="f7f08-p139">このファイル共有は、データベースを初期化した時点で一時的に使用されます。大きなデータベースを扱う場合、使用するネットワーク帯域幅でデータベース バックアップのサイズに対応できない場合に備えて、データベースを手動で初期化することを推奨します。</span><span class="sxs-lookup"><span data-stu-id="f7f08-p139">This file share will be used temporarily when you initialize the databases. If you are dealing with large databases, we recommend that you manually initialize them in case your network bandwidth cannot accommodate the size of the database backups.</span></span>
    
    - <span data-ttu-id="f7f08-262">[検証] ページで、すべての検証チェックが成功したことを確認し、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f7f08-262">In the Validation page, verify that all validation checks are successful, then click **Next**.</span></span>
    
    - <span data-ttu-id="f7f08-263">[**概要**] ページで、すべての設定を確認し、[完了] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f7f08-263">In the **Summary** page, verify all settings and click Finish.</span></span>
    
11. <span data-ttu-id="f7f08-264">AG リスナーを指定して、AG のプライマリ ノードとしての古いミラーのプリンシパルを指定することに、新しいストアを作成します。</span><span class="sxs-lookup"><span data-stu-id="f7f08-264">Create a new store specifying the AG listener, and specifying the principal of the old mirror as the primary node of the AG.</span></span>
    
    - <span data-ttu-id="f7f08-265">トポロジ ビルダーを開きます。</span><span class="sxs-lookup"><span data-stu-id="f7f08-265">Open Topology Builder.</span></span> <span data-ttu-id="f7f08-266">トポロジで、[**共有コンポーネント**] を展開し、[**SQL Server ストア**] を右クリックして、[**新しい SQL Server ストア**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f7f08-266">In your topology, expand **Shared Components**, right-click **SQL Server Stores**, and click **New SQL Server Store**.</span></span>
    
    - <span data-ttu-id="f7f08-267">[**新しい SQL ストアの定義**] ページで、まず [**高可用性の設定**] チェック ボックスをオンにしてから、SQL AlwaysOn 可用性グループがドロップダウン ボックスに表示されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="f7f08-267">In the **Define New SQL Store** page, first select the **High Availability Settings** check box, and then make sure that SQL AlwaysOn Availability Groups appears in the drop-down box.</span></span>
    
    - <span data-ttu-id="f7f08-268">[**SQL Server の可用性グループのリスナーの FQDN**] ボックスに、可用性グループを作成したときに作成したリスナーの FQDN を入力します。</span><span class="sxs-lookup"><span data-stu-id="f7f08-268">In the **SQL Server Availability Listener FQDN** box, type the FQDN of the listener you created when you created the availability group.</span></span>
    
    - <span data-ttu-id="f7f08-269">ボックスで、 **SQL Server の FQDN** AG のプライマリ ノードの FQDN を入力し、し、[ **OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f7f08-269">In the **SQL Server FQDN** box, type the FQDN of the primary node of the AG, and then click **OK**.</span></span> <span data-ttu-id="f7f08-270">これは、このストアの古いミラーのプリンシパルである必要があります。</span><span class="sxs-lookup"><span data-stu-id="f7f08-270">This should be the principal of the old mirror for this store.</span></span>
    
12. <span data-ttu-id="f7f08-271">新しい AG をフロント エンド プールに関連付けます。</span><span class="sxs-lookup"><span data-stu-id="f7f08-271">Associate the new AG with the Front End pool.</span></span>
    
    - <span data-ttu-id="f7f08-272">トポロジ ビルダーでは、AG と関連付けるプールを右クリックし、**プロパティの編集**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f7f08-272">In Topology Builder, right-click the pool to associate with the AG, and click **Edit Properties**.</span></span>
    
    - <span data-ttu-id="f7f08-273">**SQL Server ストア**] ボックスで、[**関連付け**の AG を選択します。</span><span class="sxs-lookup"><span data-stu-id="f7f08-273">Under **Associations**, in the **SQL Server Store** box, select the AG.</span></span> <span data-ttu-id="f7f08-274">AG への移動先となるプール内の他のデータベースの同じグループを選択します。</span><span class="sxs-lookup"><span data-stu-id="f7f08-274">Select the same group for any other databases in the pool which you want to move to the AG.</span></span>
    
    - <span data-ttu-id="f7f08-275">AG に必要なすべてのデータベースが設定されていることを確認したら、[ **OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f7f08-275">When you're sure that all needed databases are set to the AG, click **OK**.</span></span>
    
13. <span data-ttu-id="f7f08-p143">トポロジを公開します。[**操作**] メニューから、[**トポロジ**]、[**公開**] の順にクリックします。続いて確認ページで [**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f7f08-p143">Publish the topology. From the **Action** menu click **Topology** and then **Publish**. Then in the confirmation page click **Next**.</span></span>
    
14. <span data-ttu-id="f7f08-279">AlwaysOn 可用性グループのレプリカの各 SQL ログインしているかどうかを確認するのにはいくつかの最終的な手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="f7f08-279">Perform some final steps to make sure that the SQL logins are on each of the replicas in the AlwaysOn Availability Group.</span></span>
    
    - <span data-ttu-id="f7f08-280">トポロジ ビルダーを開き**既存の展開からトポロジをダウンロード**するを選択して **[ok]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f7f08-280">Open Topology Builder, select **Download topology from existing deployment**, and click **OK**.</span></span>
    
    - <span data-ttu-id="f7f08-281">[Skype for Business Server]、使用するトポロジ、[**SQL Server ストア**] の順に展開します。</span><span class="sxs-lookup"><span data-stu-id="f7f08-281">Expand Skype for Business Server, expand your topology, and expand **SQL Server Stores**.</span></span> <span data-ttu-id="f7f08-282">、新しい AG の SQL ストアを右クリックし、[**プロパティの編集**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f7f08-282">Right-click the SQL store of the new AG, and click **Edit Properties**.</span></span>
    
    - <span data-ttu-id="f7f08-283">[ **SQL Server の FQDN** ] ボックスで、ページの下部にある AG のリスナーの FQDN の値を変更します。</span><span class="sxs-lookup"><span data-stu-id="f7f08-283">At the bottom of the page, in the **SQL Server FQDN** box, change the value to the FQDN of the Listener of the AG.</span></span>
    
    - <span data-ttu-id="f7f08-p145">トポロジを公開します。[**操作**] メニューから、[**トポロジ**]、[**公開**] の順にクリックします。続いて、確認ページで [**次へ**] をクリックします。新しいトポロジがレプリケートされるまで数分待ちます。</span><span class="sxs-lookup"><span data-stu-id="f7f08-p145">Publish the topology. From the **Action** menu click **Topology** and then **Publish**. Then in the confirmation page click **Next**. Then wait a few minutes for the new topology to replicate.</span></span>
    
    - <span data-ttu-id="f7f08-288">SQL Server Management Studio を開き AG に移動します。</span><span class="sxs-lookup"><span data-stu-id="f7f08-288">Open SQL Server Management Studio, and navigate to the AG.</span></span> <span data-ttu-id="f7f08-289">AlwaysOn 可用性グループのセカンダリ レプリカへのフェールオーバーを行います。</span><span class="sxs-lookup"><span data-stu-id="f7f08-289">Fail it over to a secondary replica.</span></span>
    
    - <span data-ttu-id="f7f08-290">ビジネス サーバー管理シェルの Skype を開きこのレプリカの SQL ログインを作成するのには、次のコマンドレットを入力します。</span><span class="sxs-lookup"><span data-stu-id="f7f08-290">Open Skype for Business Server Management Shell and type the following cmdlet to create the SQL logins on this replica:</span></span>
    
    ```
    Install-CsDatabase -Update
    ```

    - <span data-ttu-id="f7f08-291">前の 2 つの手順を繰り返します (セカンダリ レプリカでは、グループをフェールオーバーしを使用して、 `Install-CsDatabase -Update`)、グループ内の各レプリカのです。</span><span class="sxs-lookup"><span data-stu-id="f7f08-291">Repeat the previous two steps (fail over the group to a secondary replica, then use  `Install-CsDatabase -Update`) for each replica in the group.</span></span>
    
## <a name="deploy-an-always-on-availability-group-on-an-existing-pool-that-does-not-use-database-mirroring"></a><span data-ttu-id="f7f08-292">常に可用性グループにデータベース ミラーリングを使用しない既存のプールでの展開します。</span><span class="sxs-lookup"><span data-stu-id="f7f08-292">Deploy an Always On Availability Group on an existing pool that does not use database mirroring</span></span>
<span data-ttu-id="f7f08-293"><a name="BKMK_NoHAPool_CreateAlwaysOnGroup"> </a></span><span class="sxs-lookup"><span data-stu-id="f7f08-293"></span></span>

> [!NOTE]
> <span data-ttu-id="f7f08-294">AG にアップグレードするプールでは、組織の中央管理ストアをホストしている場合必要があります最初に移動する CMS 別のプールにこのプールをアップグレードする前にします。</span><span class="sxs-lookup"><span data-stu-id="f7f08-294">If the pool you are upgrading to an AG hosts the Central Management store for your organization, you must first move the CMS to another pool before you upgrade this pool.</span></span> <span data-ttu-id="f7f08-295">プールを移動するには、Move-CsManagementServer コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="f7f08-295">Use the Move-CsManagementServer cmdlet to move the pool.</span></span> <span data-ttu-id="f7f08-296">組織内の別のプールがない、Standard Edition サーバーを一時的に展開し、AG にプールをアップグレードする前に、このサーバーに CMS を移動できます。</span><span class="sxs-lookup"><span data-stu-id="f7f08-296">If you do not have another pool in your organization, you can deploy a Standard Edition server temporarily and move the CMS to this server before you upgrade your pool to the AG.</span></span> 
  
1. <span data-ttu-id="f7f08-297">AG の一部となるすべてのデータベース サーバーのフェールオーバー クラスタ リング機能を設定します。</span><span class="sxs-lookup"><span data-stu-id="f7f08-297">Set up the Failover Clustering feature on all the database servers which will be part of the AG.</span></span> <span data-ttu-id="f7f08-298">各サーバーで、以下の作業を行います。</span><span class="sxs-lookup"><span data-stu-id="f7f08-298">On each server, do the following</span></span>
    
   - <span data-ttu-id="f7f08-299">サーバー マネージャーを開き、[**役割と機能の追加**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f7f08-299">Open Server Manager and click **Add roles and features**.</span></span>
    
   - <span data-ttu-id="f7f08-p149">[**機能の選択**] ボックスが表示されるまで [**次へ**] をクリックします。このボックスで、[**フェールオーバー クラスタリング**] チェック ボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="f7f08-p149">Click **Next** until you reach the **Select features** box. Here, select the **Failover Clustering** check box.</span></span>
    
   - <span data-ttu-id="f7f08-302">[**フェールオーバー クラスタリングに必要な機能を追加しますか?**] ボックスで、[**機能の追加**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f7f08-302">In the **Add features that are required for Failover Clustering?** box, click **Add Features**.</span></span>
    
   - <span data-ttu-id="f7f08-303">[**インストール**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f7f08-303">Click **Install**.</span></span>
    
2. <span data-ttu-id="f7f08-304">クラスター構成を検証します。</span><span class="sxs-lookup"><span data-stu-id="f7f08-304">Validate the cluster configuration.</span></span>
    
   - <span data-ttu-id="f7f08-305">サーバー マネージャーで、[**ツール**] メニューをクリックし、[**フェールオーバー クラスター マネージャー**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f7f08-305">In Server Manager, click the **Tools** menu and then click **Failover Cluster Manager**.</span></span>
    
   - <span data-ttu-id="f7f08-306">画面右側の [**操作**] で、[**構成の検証**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f7f08-306">Under **Actions** on the right side of the screen, click **Validate Configuration**.</span></span>
    
   - <span data-ttu-id="f7f08-307">[**開始する前に**] ページで、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f7f08-307">On the **Before You Begin** page, click **Next**.</span></span>
    
   - <span data-ttu-id="f7f08-308">クラスターに追加するサーバーを選択し、[**すべてのテストを実行**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f7f08-308">Select the servers to add to the cluster, and then click **Run all tests**.</span></span>
    
   - <span data-ttu-id="f7f08-309">[**概要**] ボックスで、ウィザードに表示されるエラーを確認してください。</span><span class="sxs-lookup"><span data-stu-id="f7f08-309">In the**Summary** box, check any errors that the wizard reports.</span></span> <span data-ttu-id="f7f08-310">確認したら、[**完了**] をクリックして検証を完了します。</span><span class="sxs-lookup"><span data-stu-id="f7f08-310">Then click **Finish** to complete the validation.</span></span>
    
    <span data-ttu-id="f7f08-p151">特に、共有ストレージを使用していない場合、通常はウィザードにより複数の警告が報告されます。共有ストレージを使用する必要はありませんが、[**エラー**] でメッセージが表示されている場合は、作業を続行する前にこれらの問題を修正する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f7f08-p151">The wizard will probably report several warnings, especially if you are not using shared storage. You are not required to use shared storage. However, if you see any **Error** messages, you must fix those issues before continuing.</span></span>
    
3. <span data-ttu-id="f7f08-314">(WSFC) Windows Server フェールオーバー クラスターを作成します。</span><span class="sxs-lookup"><span data-stu-id="f7f08-314">Create the Windows Server Failover Cluster (WSFC).</span></span>
    
   - <span data-ttu-id="f7f08-315">[**フェールオーバー クラスター管理**] ウィザードで、[**フェールオーバー クラスター管理**]、[**クラスターの作成**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="f7f08-315">In the **Failover Cluster Management** wizard, right-click **Failover Cluster Management**, then click **Create Cluster**.</span></span>
    
   - <span data-ttu-id="f7f08-316">[**開始する前に**] ページで、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f7f08-316">On the **Before You Begin** page, click **Next**.</span></span>
    
   - <span data-ttu-id="f7f08-p152">クラスター名と IP アドレスを追加します。設定が検証されたら、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f7f08-p152">Add the cluster name and IP address. When the settings are validated, click **Next**.</span></span>
    
   - <span data-ttu-id="f7f08-319">[確認] ページで、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f7f08-319">On the Confirmation page, click **Next**.</span></span>
    
   - <span data-ttu-id="f7f08-320">クラスターが作成されたら、[**完了**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f7f08-320">After the cluster is created, click **Finish**.</span></span>
    
4. <span data-ttu-id="f7f08-p153">ファイル共有監視を使用するようにクラスター クォーラム設定を構成することをお勧めします。このためには、以下の手順を行います。</span><span class="sxs-lookup"><span data-stu-id="f7f08-p153">We recommend that you configure the cluster quorum settings to use a file share witness. To do so, use these steps:</span></span>
    
   - <span data-ttu-id="f7f08-323">クラスター名を右クリックし、[**他の操作**]、[**クラスター クォーラム設定の構成**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="f7f08-323">Right-click the cluster name, click **More Actions**, and click **Configure Cluster Quorum Settings**.</span></span>
    
   - <span data-ttu-id="f7f08-324">[**クォーラム構成オプションの選択**] ページで、[**クォーラム監視を選択する**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f7f08-324">In the **Select Quorum Configuration Option** page, click **Select the quorum witness**.</span></span>
    
   - <span data-ttu-id="f7f08-325">[**クォーラム監視の選択**] ページで、[**ファイル共有監視を構成する**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f7f08-325">In the **Select Quorum Witness** page, click **Configure a file share witness**.</span></span>
    
   - <span data-ttu-id="f7f08-326">[**ファイル共有監視の構成**] ページで、使用するファイル共有のパスを入力し、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f7f08-326">In the **Configure File Share Witness** page, type the path of the file share you want to use, and then click **Next**.</span></span>
    
   - <span data-ttu-id="f7f08-327">[**確認**] ページで、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f7f08-327">On the **Confirmation** page, click **Next**.</span></span>
    
5. <span data-ttu-id="f7f08-328">クラスター内の各サーバーでは、AG で、SQL Server 構成マネージャーを有効にします。</span><span class="sxs-lookup"><span data-stu-id="f7f08-328">On each server in the cluster, enable AG in SQL Server Configuration Manager.</span></span>
    
   - <span data-ttu-id="f7f08-p154">SQL Server 構成マネージャーを開きます。画面左側のツリーで、[**SQL Server のサービス**] をクリックし、SQL Server サービスをダブルクリックします。</span><span class="sxs-lookup"><span data-stu-id="f7f08-p154">Open SQL Server Configuration Manager. In the tree on the left side of the screen, click **SQL Server Services**, then double-click the SQL Server service.</span></span> 
    
   - <span data-ttu-id="f7f08-p155">[**プロパティ**] ボックスで、[**AlwaysOn 高可用性**] タブを選択します。[**AlwaysOn 可用性グループを有効にする**] チェック ボックスをオンにします。SQL Server サービスを再開するよう求めるメッセージが表示されたら、サービスを再開します。</span><span class="sxs-lookup"><span data-stu-id="f7f08-p155">In the **Properties** box, select the **AlwaysOn High Availability** tab. Select the **Enable AlwaysOn Availability Groups** check box. Restart the SQL Server service when prompted.</span></span>
    
6. <span data-ttu-id="f7f08-333">可用性グループを作成します。</span><span class="sxs-lookup"><span data-stu-id="f7f08-333">Create the availability group.</span></span>
    
   - <span data-ttu-id="f7f08-334">SQL Server Management Studio を開き、SQL Server インスタンスに接続します。</span><span class="sxs-lookup"><span data-stu-id="f7f08-334">Open SQL Server Management Studio, and connect to the SQL Server instance.</span></span>
    
   - <span data-ttu-id="f7f08-335">オブジェクト エクスプ ローラーで、**常に高可用性**のフォルダーを展開します。</span><span class="sxs-lookup"><span data-stu-id="f7f08-335">In Object Explorer, expand the **Always On High Availability** folder.</span></span> <span data-ttu-id="f7f08-336">[**可用性グループ**] フォルダーを右クリックし、[**新しい可用性グループ ウィザード**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f7f08-336">Right-click the **Availability Groups** folder and click **New Availability Group Wizard**.</span></span>
    
   - <span data-ttu-id="f7f08-337">[**説明**] ページが表示されたら、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f7f08-337">If the **Introduction** page appears, click **Next**.</span></span>
    
   - <span data-ttu-id="f7f08-338">[**可用性グループ名の指定**] ページで、可用性グループの名前を入力し、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f7f08-338">In the **Specify Availability Group Name** page, type the name of the Availability group, and click **Next**.</span></span>
    
   - <span data-ttu-id="f7f08-339">データベースの選択] ページでは、AG に追加するデータベースを選択します。</span><span class="sxs-lookup"><span data-stu-id="f7f08-339">In the Select Databases page, select the databases that you want to include in the AG.</span></span> <span data-ttu-id="f7f08-340">続いて [ **次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f7f08-340">Then click **Next**.</span></span>
    
    <span data-ttu-id="f7f08-341">含めないでください、**レポート サーバー**、 **ReportServerTempDB**、またはデータベースの永続的なチャット、AG のようにこのシナリオではサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="f7f08-341">Do not include the **ReportServer**, **ReportServerTempDB**, or Persistent Chat databases in the AG, as these are not supported in this scenario.</span></span> <span data-ttu-id="f7f08-342">AG のビジネス サーバー データベースの他のすべての Skype を含めることができます。</span><span class="sxs-lookup"><span data-stu-id="f7f08-342">You can include all other Skype for Business Server databases in the AG.</span></span>
    
   - <span data-ttu-id="f7f08-343">**レプリカの指定**] ページで、[**複製**] タブをクリックします。**レプリカの追加**] ボタンをクリックし、次に、WSFC のノードとして参加した他の SQL インスタンスに接続します。</span><span class="sxs-lookup"><span data-stu-id="f7f08-343">In the **Specify Replicas** page, click the **Replicas** tab. Then click the **Add Replicas** button, and connect to the other SQL instances that you joined as nodes of the WSFC.</span></span>
    
   - <span data-ttu-id="f7f08-p159">各インスタンスの [**自動フェールオーバー**] オプションと [**同期コミット**] オプションをオンにします。[**読み取り可能なセカンダリ**] オプションはオンにしないでください。</span><span class="sxs-lookup"><span data-stu-id="f7f08-p159">For each instance, select the **Automatic Failover** and **Synchronous Commit** options. Do not select the **Readable Secondary** option.</span></span>
    
   - <span data-ttu-id="f7f08-346">[**エンドポイント**] タブをクリックし、[**ポート番号**] が "5022" に設定されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="f7f08-346">Click the **Endpoints** tab and verify that **Port Number** is set to 5022.</span></span>
    
   - <span data-ttu-id="f7f08-p160">[**リスナー**] タブをクリックし、[**可用性グループ リスナーの作成**] オプションをオンにします。そのオプションの下で、リスナーの名前を入力し、[**ポート**] を "1433" (他のポートはこのオプションではサポートされません) に設定します。</span><span class="sxs-lookup"><span data-stu-id="f7f08-p160">Click the **Listener** tab, and select the **Create an availability group listener** option. Under that option, type a name for the listener, and set the **Port** to 1433 (other ports are not supported for this option).</span></span>
    
   - <span data-ttu-id="f7f08-349">[**追加**] をクリックし、[**IPv4 アドレス**] ボックスに優先させる仮想 IP アドレスを入力して、[**OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f7f08-349">Click **Add**, and then in the **IPv4 Address** box, provide your preferred virtual IP address, and then click **OK**.</span></span>
    
   - <span data-ttu-id="f7f08-p161">[**最初のデータの同期を選択**] ページで [完全] を選択します。レプリカがアクセスでき、両方のレプリカにより使用される SQL Server サービス アカウントが書き込みアクセス許可を持っているフォルダーを指定します。続いて、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f7f08-p161">In the **Select Initial Data Synchronization** page, select Full, and specify a folder that is accessible to the replicas, and that the SQL Server service account used by both replicas has Write permissions for. Then click **Next**.</span></span>
    
    <span data-ttu-id="f7f08-p162">このファイル共有は、データベースを初期化した時点で一時的に使用されます。大きなデータベースを扱う場合、使用するネットワーク帯域幅でデータベース バックアップのサイズに対応できない場合に備えて、データベースを手動で初期化することを推奨します。</span><span class="sxs-lookup"><span data-stu-id="f7f08-p162">This file share will be used temporarily when you initialize the databases. If you are dealing with large databases, we recommend that you manually initialize them in case your network bandwidth cannot accommodate the size of the database backups.</span></span>
    
    - <span data-ttu-id="f7f08-354">[検証] ページで、すべての検証チェックが成功したことを確認し、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f7f08-354">In the Validation page, verify that all validation checks are successful, then click **Next**.</span></span>
    
   - <span data-ttu-id="f7f08-355">[**概要**] ページで、すべての設定を確認し、[完了] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f7f08-355">In the **Summary** page, verify all settings and click Finish.</span></span>
    
7. <span data-ttu-id="f7f08-356">AG リスナーを指定する新しいストアを作成します。</span><span class="sxs-lookup"><span data-stu-id="f7f08-356">Create a new store specifying the AG listener.</span></span>
    
   - <span data-ttu-id="f7f08-357">トポロジ ビルダーを開きます。</span><span class="sxs-lookup"><span data-stu-id="f7f08-357">Open Topology Builder.</span></span> <span data-ttu-id="f7f08-358">トポロジで、[**共有コンポーネント**] を展開し、[**SQL Server ストア**] を右クリックして、[**新しい SQL Server ストア**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f7f08-358">In your topology, expand **Shared Components**, right-click **SQL Server Stores**, and click **New SQL Server Store**.</span></span>
    
   - <span data-ttu-id="f7f08-359">[**新しい SQL ストアの定義**] ページで、まず [**高可用性の設定**] チェック ボックスをオンにしてから、SQL AlwaysOn 可用性グループがドロップダウン ボックスに表示されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="f7f08-359">In the **Define New SQL Store** page, first select the **High Availability Settings** check box, and then make sure that SQL AlwaysOn Availability Groups appears in the drop-down box.</span></span>
    
   - <span data-ttu-id="f7f08-360">[**SQL Server の可用性グループのリスナーの FQDN**] ボックスに、可用性グループを作成したときに作成したリスナーの FQDN を入力します。</span><span class="sxs-lookup"><span data-stu-id="f7f08-360">In the **SQL Server Availability Listener FQDN** box, type the FQDN of the listener you created when you created the availability group.</span></span>
    
   - <span data-ttu-id="f7f08-361">ボックスで、 **SQL Server の FQDN** AG のプライマリ ノードの FQDN を入力し、し、[ **OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f7f08-361">In the **SQL Server FQDN** box, type the FQDN of the primary node of the AG, and then click **OK**.</span></span>
    
8. <span data-ttu-id="f7f08-362">新しい常に可用性グループをフロント エンド プールに関連付けます。</span><span class="sxs-lookup"><span data-stu-id="f7f08-362">Associate the new Always On Availability Group with the Front End pool.</span></span>
    
   - <span data-ttu-id="f7f08-363">トポロジ ビルダーでは、AG と関連付けるプールを右クリックし、**プロパティの編集**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f7f08-363">In Topology Builder, right-click the pool to associate with the AG, and click **Edit Properties**.</span></span>
    
   - <span data-ttu-id="f7f08-364">**SQL Server ストア**] ボックスで、[**関連付け**の AG を選択します。</span><span class="sxs-lookup"><span data-stu-id="f7f08-364">Under **Associations**, in the **SQL Server Store** box, select the AG.</span></span> <span data-ttu-id="f7f08-365">AG への移動先となるプール内の他のデータベースの同じグループを選択します。</span><span class="sxs-lookup"><span data-stu-id="f7f08-365">Select the same group for any other databases in the pool which you want to move to the AG.</span></span>
    
   - <span data-ttu-id="f7f08-366">AG に必要なすべてのデータベースが設定されていることを確認したら、[ **OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f7f08-366">When you're sure that all needed databases are set to the AG, click **OK**.</span></span>
    
9. <span data-ttu-id="f7f08-p165">トポロジを公開します。[**操作**] メニューから、[**トポロジ**]、[**公開**] の順にクリックします。続いて確認ページで [**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f7f08-p165">Publish the topology. From the **Action** menu click **Topology** and then **Publish**. Then in the confirmation page click **Next**.</span></span>
    
10. <span data-ttu-id="f7f08-370">AG のレプリカごとに、SQL ログインしているかどうかを確認するのにはいくつかの最終的な手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="f7f08-370">Perform some final steps to make sure that the SQL logins are on each of the replicas in the AG.</span></span>
    
    - <span data-ttu-id="f7f08-371">トポロジ ビルダーを開き**既存の展開からトポロジをダウンロード**するを選択して **[ok]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f7f08-371">Open Topology Builder, select **Download topology from existing deployment**, and click **OK**.</span></span>
    
    - <span data-ttu-id="f7f08-372">[Skype for Business Server]、使用するトポロジ、[**SQL Server ストア**] の順に展開します。</span><span class="sxs-lookup"><span data-stu-id="f7f08-372">Expand Skype for Business Server, expand your topology, and expand **SQL Server Stores**.</span></span> <span data-ttu-id="f7f08-373">、新しい AG の SQL ストアを右クリックし、をクリックして * * 編集プロパティ * *。</span><span class="sxs-lookup"><span data-stu-id="f7f08-373">Right-click the SQL store of the new AG, and click ** Edit Properties**.</span></span>
    
    - <span data-ttu-id="f7f08-374">[ **SQL Server の FQDN** ] ボックスで、ページの下部にある AG のリスナーの FQDN の値を変更します。</span><span class="sxs-lookup"><span data-stu-id="f7f08-374">At the bottom of the page, in the **SQL Server FQDN** box, change the value to the FQDN of the Listener of the AG.</span></span>
    
    - <span data-ttu-id="f7f08-p167">トポロジを公開します。[**操作**] メニューから、[**トポロジ**]、[**公開**] の順にクリックします。続いて、確認ページで [**次へ**] をクリックします。新しいトポロジがレプリケートされるまで数分待ちます。</span><span class="sxs-lookup"><span data-stu-id="f7f08-p167">Publish the topology. From the **Action** menu click **Topology** and then **Publish**. Then in the confirmation page click **Next**. Then wait a few minutes for the new topology to replicate.</span></span>
    
    - <span data-ttu-id="f7f08-379">SQL Server Management Studio を開き AG に移動します。</span><span class="sxs-lookup"><span data-stu-id="f7f08-379">Open SQL Server Management Studio, and navigate to the AG.</span></span> <span data-ttu-id="f7f08-380">AlwaysOn 可用性グループのセカンダリ レプリカへのフェールオーバーを行います。</span><span class="sxs-lookup"><span data-stu-id="f7f08-380">Fail it over to a secondary replica.</span></span>
    
    - <span data-ttu-id="f7f08-381">ビジネス サーバー管理シェルの Skype を開きこのレプリカの SQL ログインを作成するのには、次のコマンドレットを入力します。</span><span class="sxs-lookup"><span data-stu-id="f7f08-381">Open Skype for Business Server Management Shell and type the following cmdlet to create the SQL logins on this replica:</span></span>
    
     ```
     Install-CsDatabase -Update
     ```

     - <span data-ttu-id="f7f08-382">前の 2 つの手順を繰り返します (セカンダリ レプリカでは、グループをフェールオーバーしを使用して、 `Install-CsDatabase -Update`)、グループ内の各レプリカのです。</span><span class="sxs-lookup"><span data-stu-id="f7f08-382">Repeat the previous two steps (fail over the group to a secondary replica, then use  `Install-CsDatabase -Update`) for each replica in the group.</span></span>
    

