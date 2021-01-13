---
title: Skype for Business Server のバック エンド サーバーに Always On 可用性グループを展開する
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
ms.collection: IT_Skype16
ms.assetid: c93c01e6-626c-40ad-92dd-373b0fe9189f
description: Skype for Business Server 展開に Always On 可用性グループを展開 (インストール) します。
ms.openlocfilehash: 83565efe850570ac5ab9a0695757e708f3eae566
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49830657"
---
# <a name="deploy-an-always-on-availability-group-on-a-back-end-server-in-skype-for-business-server"></a><span data-ttu-id="6e658-103">Skype for Business Server のバック エンド サーバーに Always On 可用性グループを展開する</span><span class="sxs-lookup"><span data-stu-id="6e658-103">Deploy an Always On Availability Group on a Back End Server in Skype for Business Server</span></span>
 
<span data-ttu-id="6e658-104">Skype for Business Server 展開に Always On 可用性グループ (AG) を展開 (インストール) します。</span><span class="sxs-lookup"><span data-stu-id="6e658-104">Deploy (install) an Always On Availability Group (AG) in your Skype for Business Server deployment.</span></span>
  
<span data-ttu-id="6e658-105">AG の展開方法は、新しいプール、ミラーリングを使用する既存のプール、または現在、バック エンド データベースの高可用性がない既存のプールに展開するかどうかによって異なります。</span><span class="sxs-lookup"><span data-stu-id="6e658-105">How you deploy an AG depends on whether you are deploying it in a new pool, an existing pool that uses mirroring, or an existing pool that currently has no high availability for the Back End database.</span></span>
  
> [!NOTE]
> <span data-ttu-id="6e658-106">常設チャット サーバーの役割で AG を使用する方法はサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="6e658-106">Using an AG with a Persistent Chat Server role is not supported.</span></span> 
  
- [<span data-ttu-id="6e658-107">新しいフロントエンド プールに Always On 可用性グループを展開する</span><span class="sxs-lookup"><span data-stu-id="6e658-107">Deploy an Always On Availability Group on a new Front End pool</span></span>](alwayson-availability-group.md#BKMK_NewPool_CreateAlwaysOnGroup)
    
- [<span data-ttu-id="6e658-108">データベース ミラーリングを使用する既存のプールに Always On 可用性グループを展開する</span><span class="sxs-lookup"><span data-stu-id="6e658-108">Deploy an Always On Availability Group on an existing pool that uses database mirroring</span></span>](alwayson-availability-group.md#BKMK_MirroredPool_CreateAlwaysOnGroup)
    
- [<span data-ttu-id="6e658-109">データベース ミラーリングを使用しない既存のプールに Always On 可用性グループを展開する</span><span class="sxs-lookup"><span data-stu-id="6e658-109">Deploy an Always On Availability Group on an existing pool that does not use database mirroring</span></span>](alwayson-availability-group.md#BKMK_NoHAPool_CreateAlwaysOnGroup)
    
## <a name="deploy-an-always-on-availability-group-on-a-new-front-end-pool"></a><span data-ttu-id="6e658-110">新しいフロントエンド プールに Always On 可用性グループを展開する</span><span class="sxs-lookup"><span data-stu-id="6e658-110">Deploy an Always On Availability Group on a new Front End pool</span></span>
<span data-ttu-id="6e658-111"><a name="BKMK_NewPool_CreateAlwaysOnGroup"> </a></span><span class="sxs-lookup"><span data-stu-id="6e658-111"><a name="BKMK_NewPool_CreateAlwaysOnGroup"> </a></span></span>

1. <span data-ttu-id="6e658-112">AG の一部になるすべてのデータベース サーバーでフェールオーバー クラスタリング機能を有効にします。</span><span class="sxs-lookup"><span data-stu-id="6e658-112">Enable the Failover Clustering feature on all the database servers which will be part of the AG.</span></span> <span data-ttu-id="6e658-113">各サーバーで、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="6e658-113">On each server, do the following</span></span>
    
   - <span data-ttu-id="6e658-114">サーバー マネージャーを開き、[役割と **機能の追加] をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="6e658-114">Open Server Manager and click **Add roles and features**.</span></span>
    
   - <span data-ttu-id="6e658-115">[機能 **の選択** ] ボックスが表示されるまで 、[ **次へ] をクリック** します。</span><span class="sxs-lookup"><span data-stu-id="6e658-115">Click **Next** until you reach the **Select features** box.</span></span> <span data-ttu-id="6e658-116">ここで、[フェールオーバー クラスタリング **] チェック ボックスを** オンにします。</span><span class="sxs-lookup"><span data-stu-id="6e658-116">Here, select the **Failover Clustering** check box.</span></span>
    
   - <span data-ttu-id="6e658-117">[フェールオーバー **クラスタリングに必要な機能の追加** ] ボックスで、[機能の追加] **をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="6e658-117">In the **Add features that are required for Failover Clustering?** box, click **Add Features**.</span></span>
    
   - <span data-ttu-id="6e658-118">**[インストール]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6e658-118">Click **Install**.</span></span>
    
2. <span data-ttu-id="6e658-119">クラスター構成を検証します。</span><span class="sxs-lookup"><span data-stu-id="6e658-119">Validate the cluster configuration.</span></span>
    
   - <span data-ttu-id="6e658-120">サーバー マネージャーで、[ツール] メニュー **をクリック** し、[フェールオーバー クラスター マネージャー] **をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="6e658-120">In Server Manager, click the **Tools** menu and then click **Failover Cluster Manager**.</span></span>
    
   - <span data-ttu-id="6e658-121">画面 **の右側** にある [操作] で、[構成の検証] **をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="6e658-121">Under **Actions** on the right side of the screen, click **Validate Configuration**.</span></span>
    
   - <span data-ttu-id="6e658-122">**[始める前に]** ページで、 **[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6e658-122">On the **Before You Begin** page, click **Next**.</span></span>
    
   - <span data-ttu-id="6e658-123">クラスターに追加するサーバーを選択し、[すべてのテストを実行] **をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="6e658-123">Select the servers to add to the cluster, and then click **Run all tests**.</span></span>
    
   - <span data-ttu-id="6e658-124">[概要 **] ボックス** で、ウィザードによって報告されるエラーを確認します。</span><span class="sxs-lookup"><span data-stu-id="6e658-124">In the **Summary** box, check any errors that the wizard reports.</span></span> <span data-ttu-id="6e658-125">次に、[ **完了]** をクリックして検証を完了します。</span><span class="sxs-lookup"><span data-stu-id="6e658-125">Then click **Finish** to complete the validation.</span></span>
    
     <span data-ttu-id="6e658-126">特に共有ストレージを使用していない場合は、ウィザードによっていくつかの警告が報告される可能性があります。</span><span class="sxs-lookup"><span data-stu-id="6e658-126">The wizard will probably report several warnings, especially if you are not using shared storage.</span></span> <span data-ttu-id="6e658-127">共有ストレージを使用する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="6e658-127">You are not required to use shared storage.</span></span> <span data-ttu-id="6e658-128">ただし、エラー メッセージが表示 **された場合** は、続行する前にそれらの問題を修正する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6e658-128">However, if you see any **Error** messages, you must fix those issues before continuing.</span></span>
    
3. <span data-ttu-id="6e658-129">Windows Server フェールオーバー クラスター (WSFC) を作成します。</span><span class="sxs-lookup"><span data-stu-id="6e658-129">Create the Windows Server Failover Cluster (WSFC).</span></span>
    
   - <span data-ttu-id="6e658-130">フェールオーバー クラスター **管理ウィザードで、[** フェールオーバー クラスター管理] を **右クリックし**、[クラスターの作成] **をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="6e658-130">In the **Failover Cluster Management** wizard, right-click **Failover Cluster Management**, then click **Create Cluster**.</span></span>
    
   - <span data-ttu-id="6e658-131">**[始める前に]** ページで、 **[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6e658-131">On the **Before You Begin** page, click **Next**.</span></span>
    
   - <span data-ttu-id="6e658-132">クラスター名と IP アドレスを追加します。</span><span class="sxs-lookup"><span data-stu-id="6e658-132">Add the cluster name and IP address.</span></span> <span data-ttu-id="6e658-133">設定が検証された後、[次へ] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="6e658-133">When the settings are validated, click **Next**.</span></span>
    
   - <span data-ttu-id="6e658-134">[確認] ページで、 **[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6e658-134">On the Confirmation page, click **Next**.</span></span>
    
   - <span data-ttu-id="6e658-135">クラスターが作成された後、[完了] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="6e658-135">After the cluster is created, click **Finish**.</span></span>
    
4. <span data-ttu-id="6e658-136">ファイル共有監視を使用するクラスター クォーラム設定を構成することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="6e658-136">We recommend that you configure the cluster quorum settings to use a file share witness.</span></span> <span data-ttu-id="6e658-137">これを行うには、次の手順を使用します。</span><span class="sxs-lookup"><span data-stu-id="6e658-137">To do so, use these steps:</span></span>
    
   - <span data-ttu-id="6e658-138">クラスター名を右クリックし、[その他の操作 **] を** クリックして、[クラスター クォーラム設定の構成 **] をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="6e658-138">Right-click the cluster name, click **More Actions**, and click **Configure Cluster Quorum Settings**.</span></span>
    
   - <span data-ttu-id="6e658-139">[クォー **ラム構成オプションの選択] ページ** で、[クォーラム監視 **の選択] をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="6e658-139">In the **Select Quorum Configuration Option** page, click **Select the quorum witness**.</span></span>
    
   - <span data-ttu-id="6e658-140">[クォー **ラム監視の選択]** ページで、[ファイル共有監視 **の構成] をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="6e658-140">In the **Select Quorum Witness** page, click **Configure a file share witness**.</span></span>
    
   - <span data-ttu-id="6e658-141">[ファイル **共有監視の** 構成] ページで、使用するファイル共有のパスを入力し、[次へ] をクリック **します**。</span><span class="sxs-lookup"><span data-stu-id="6e658-141">In the **Configure File Share Witness** page, type the path of the file share you want to use, and then click **Next**.</span></span>
    
   - <span data-ttu-id="6e658-142">**[確認]** ページで、 **[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6e658-142">On the **Confirmation** page, click **Next**.</span></span>
    
5. <span data-ttu-id="6e658-143">クラスター内の各サーバーで、Configuration Manager で AG SQL Server有効にします。</span><span class="sxs-lookup"><span data-stu-id="6e658-143">On each server in the cluster, enable the AG feature in SQL Server Configuration Manager.</span></span>
    
   - <span data-ttu-id="6e658-144">SQL Server 構成マネージャーを開きます。</span><span class="sxs-lookup"><span data-stu-id="6e658-144">Open SQL Server Configuration Manager.</span></span> <span data-ttu-id="6e658-145">画面の左側のツリーで、[SQL Server **サービス**] をクリックし、SQL Serverします。</span><span class="sxs-lookup"><span data-stu-id="6e658-145">In the tree on the left side of the screen, click **SQL Server Services**, then double-click the SQL Server service.</span></span> 
    
   - <span data-ttu-id="6e658-146">[プロパティ **] ボックス** で **、[AlwaysOn 高可用性] タブを選択** します。 **[AlwaysOn 可用性グループを有効にする]** チェック ボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="6e658-146">In the **Properties** box, select the **AlwaysOn High Availability** tab. Select the **Enable AlwaysOn Availability Groups** check box.</span></span> <span data-ttu-id="6e658-147">メッセージが表示されたらSQL Serverサービスを再起動します。</span><span class="sxs-lookup"><span data-stu-id="6e658-147">Restart the SQL Server service when prompted.</span></span>
   
6. <span data-ttu-id="6e658-148">「Skype for Business Server での新しいトポロジの作成と公開」で説明されている方法で、トポロジ ビルダーを使用してフロントエンド プール [を作成します](../../deploy/install/create-and-publish-new-topology.md)。</span><span class="sxs-lookup"><span data-stu-id="6e658-148">Use Topology Builder to create the Front End pool, as explained in [Create and publish new topology in Skype for Business Server](../../deploy/install/create-and-publish-new-topology.md).</span></span> <span data-ttu-id="6e658-149">その場合は、AG をプールのSQLストアとして指定します。</span><span class="sxs-lookup"><span data-stu-id="6e658-149">When you do, specify the AG as the SQL store for the pool.</span></span>
    
7. <span data-ttu-id="6e658-150">可用性グループを作成します。</span><span class="sxs-lookup"><span data-stu-id="6e658-150">Create the availability group.</span></span>
    
   - <span data-ttu-id="6e658-151">新SQL Server Management Studio開き、新しいインスタンスSQL Serverします。</span><span class="sxs-lookup"><span data-stu-id="6e658-151">Open SQL Server Management Studio, and connect to the SQL Server instance.</span></span>
    
   - <span data-ttu-id="6e658-152">オブジェクト エクスプローラーで **、Always On 高可用性フォルダーを展開** します。</span><span class="sxs-lookup"><span data-stu-id="6e658-152">In Object Explorer, expand the **Always On High Availability** folder.</span></span> <span data-ttu-id="6e658-153">可用性グループ フォルダーを **右クリックし** 、新しい可用性グループ **ウィザードをクリックします**。</span><span class="sxs-lookup"><span data-stu-id="6e658-153">Right-click the **Availability Groups** folder and click **New Availability Group Wizard**.</span></span>
    
   - <span data-ttu-id="6e658-154">[概要] **ページが** 表示されたら、[次へ] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="6e658-154">If the **Introduction** page appears, click **Next**.</span></span>
    
   - <span data-ttu-id="6e658-155">[可用性 **グループ名の指定** ] ページで、可用性グループの名前を入力し、[次へ] をクリック **します**。</span><span class="sxs-lookup"><span data-stu-id="6e658-155">In the **Specify Availability Group Name** page, type the name of the Availability group, and click **Next**.</span></span>
    
   - <span data-ttu-id="6e658-156">[データベースの選択] ページで、AlwaysOn 可用性グループに含めるデータベースを選択します。</span><span class="sxs-lookup"><span data-stu-id="6e658-156">In the Select Databases page, select the databases that you want to include in the AlwaysOn Availability Group.</span></span> <span data-ttu-id="6e658-157">次に、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6e658-157">Then click **Next**.</span></span>
    
     <span data-ttu-id="6e658-158">このシナリオではサポートされていないので **、AlwaysOn** 可用性グループには ReportServer データベース **、ReportServerTempDB** データベース、または常設チャット データベースを含めずにしてください。</span><span class="sxs-lookup"><span data-stu-id="6e658-158">Do not include the **ReportServer**, **ReportServerTempDB**, or Persistent Chat databases in the AlwaysOn Availability Group, as these are not supported in this scenario.</span></span> <span data-ttu-id="6e658-159">AlwaysOn 可用性グループには、他のすべての Skype for Business Server データベースを含めできます。</span><span class="sxs-lookup"><span data-stu-id="6e658-159">You can include all other Skype for Business Server databases in the AlwaysOn Availability Group.</span></span>
    
   - <span data-ttu-id="6e658-160">[レプリカ **の指定] ページ** で、[レプリカ] **タブをクリック** します。次に、[ **レプリカ** の追加] ボタンをクリックし、Windows Server フェールオーバー クラスターのノードとして参加SQL他のインスタンスに接続します。</span><span class="sxs-lookup"><span data-stu-id="6e658-160">In the **Specify Replicas** page, click the **Replicas** tab. Then click the **Add Replicas** button, and connect to the other SQL instances that you joined as nodes of the Windows Server Failover Cluster.</span></span>
    
   - <span data-ttu-id="6e658-161">インスタンスごとに、[自動フェールオーバーと **同期コミット** ] **オプションを選択** します。</span><span class="sxs-lookup"><span data-stu-id="6e658-161">For each instance, select the **Automatic Failover** and **Synchronous Commit** options.</span></span> <span data-ttu-id="6e658-162">[読み取り可能な **セカンダリ] オプションは選択** できません。</span><span class="sxs-lookup"><span data-stu-id="6e658-162">Do not select the **Readable Secondary** option.</span></span>
    
   - <span data-ttu-id="6e658-163">[エンドポイント **] タブを** クリックし、 **ポート** 番号が 5022 に設定されています。</span><span class="sxs-lookup"><span data-stu-id="6e658-163">Click the **Endpoints** tab and verify that **Port Number** is set to 5022.</span></span>
    
   - <span data-ttu-id="6e658-164">[リスナー **] タブを** クリックし、[可用性グループ リスナー **の作成] オプションを選択** します。</span><span class="sxs-lookup"><span data-stu-id="6e658-164">Click the **Listener** tab, and select the **Create an availability group listener** option.</span></span> <span data-ttu-id="6e658-165">このオプションの下にリスナーの名前を入力し、 **ポート** を 1433 に設定します (他のポートは、このオプションではサポートされていません)。</span><span class="sxs-lookup"><span data-stu-id="6e658-165">Under that option, type a name for the listener, and set the **Port** to 1433 (other ports are not supported for this option).</span></span>
    
   - <span data-ttu-id="6e658-166">[ **追加]** をクリックし **、[IPv4 アドレス** ] ボックスに希望する仮想 IP アドレスを入力し **、[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6e658-166">Click **Add**, and then in the **IPv4 Address** box, provide your preferred virtual IP address, and then click **OK**.</span></span>
    
   - <span data-ttu-id="6e658-167">[初期データ同期の選択] ページで [完全] を選択し、レプリカからアクセス可能なフォルダーを指定します。また、両方のレプリカで使用される SQL Server サービス アカウントに書き込みアクセス許可が付与されます。</span><span class="sxs-lookup"><span data-stu-id="6e658-167">In the **Select Initial Data Synchronization** page, select Full, and specify a folder that is accessible to the replicas, and that the SQL Server service account used by both replicas has Write permissions for.</span></span> <span data-ttu-id="6e658-168">次に、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6e658-168">Then click **Next**.</span></span>
    
     <span data-ttu-id="6e658-169">このファイル共有は、データベースを初期化するときに一時的に使用されます。</span><span class="sxs-lookup"><span data-stu-id="6e658-169">This file share will be used temporarily when you initialize the databases.</span></span> <span data-ttu-id="6e658-170">大規模なデータベースを扱う場合は、ネットワーク帯域幅がデータベース バックアップのサイズに対応できない場合に備え、手動で初期化することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="6e658-170">If you are dealing with large databases, we recommend that you manually initialize them in case your network bandwidth cannot accommodate the size of the database backups.</span></span>
    
   - <span data-ttu-id="6e658-171">[検証] ページで、すべての検証チェックが成功したと確認し、[次へ] をクリック **します**。</span><span class="sxs-lookup"><span data-stu-id="6e658-171">In the Validation page, verify that all validation checks are successful, then click **Next**.</span></span>
    
   - <span data-ttu-id="6e658-172">[概要 **] ページで** 、すべての設定を確認し、[完了] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6e658-172">In the **Summary** page, verify all settings and click Finish.</span></span>
      
8. <span data-ttu-id="6e658-173">プールと AG を展開した後、最後の手順を実行して、SQL ログインが AlwaysOn 可用性グループ内の各レプリカ上に配置されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="6e658-173">After the pool and the AG are deployed, perform some final steps to make sure that the SQL logins are on each of the replicas in the AlwaysOn Availability Group.</span></span> 
    
   - <span data-ttu-id="6e658-174">トポロジ ビルダーを開き、[既存の展開から **トポロジ** をダウンロードする] を選択し **、[OK] をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="6e658-174">Open Topology Builder, select **Download topology from existing deployment**, and click **OK**.</span></span>
    
   - <span data-ttu-id="6e658-175">[Skype for Business Server] を展開し、トポロジを展開し、[ストア] **SQL Server展開します**。</span><span class="sxs-lookup"><span data-stu-id="6e658-175">Expand Skype for Business Server, expand your topology, and expand **SQL Server Stores**.</span></span> <span data-ttu-id="6e658-176">新しい AlwaysOn 可用性SQLストアを右クリックし、[プロパティの編集] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="6e658-176">Right-click the SQL store of the new AlwaysOn Availability Group, and click **Edit Properties**.</span></span>
    
     - <span data-ttu-id="6e658-177">ページの下部にある [ SQL Server **FQDN]** ボックスで、値を AG のリスナーの FQDN に変更します。</span><span class="sxs-lookup"><span data-stu-id="6e658-177">At the bottom of the page, in the **SQL Server FQDN** box, change the value to the FQDN of the Listener of the AG.</span></span>
    
   - <span data-ttu-id="6e658-178">トポロジを公開します。</span><span class="sxs-lookup"><span data-stu-id="6e658-178">Publish the topology.</span></span> <span data-ttu-id="6e658-179">[操作 **] メニューの** [ **トポロジ] をクリックし、[公開]** を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="6e658-179">From the **Action** menu click **Topology** and then **Publish**.</span></span> <span data-ttu-id="6e658-180">次に、確認ページで [次へ] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="6e658-180">Then in the confirmation page click **Next**.</span></span> <span data-ttu-id="6e658-181">その後、新しいトポロジがレプリケートされるのを数分待ちます。</span><span class="sxs-lookup"><span data-stu-id="6e658-181">Then wait a few minutes for the new topology to replicate.</span></span>
    
   - <span data-ttu-id="6e658-182">ファイルSQL Server Management Studio開き、AG に移動します。</span><span class="sxs-lookup"><span data-stu-id="6e658-182">Open SQL Server Management Studio, and navigate to the AG.</span></span> <span data-ttu-id="6e658-183">セカンダリ レプリカにフェールオーバーします。</span><span class="sxs-lookup"><span data-stu-id="6e658-183">Fail it over to a secondary replica.</span></span>
    
   - <span data-ttu-id="6e658-184">Skype for Business Server 管理シェルを開き、次のコマンドレットを入力して、このレプリカSQLログインを作成します。</span><span class="sxs-lookup"><span data-stu-id="6e658-184">Open Skype for Business Server Management Shell and type the following cmdlet to create the SQL logins on this replica:</span></span>
    
   ```powershell
   Install-CsDatabase -Update
   ```

   - <span data-ttu-id="6e658-185">グループ内の各レプリカについて、前の 2 つの手順を繰り返します (グループをセカンダリ レプリカにフェールオーバーし、次に  `Install-CsDatabase -Update` 使用します)。</span><span class="sxs-lookup"><span data-stu-id="6e658-185">Repeat the previous two steps (fail over the group to a secondary replica, then use  `Install-CsDatabase -Update`) for each replica in the group.</span></span>
    
## <a name="deploy-an-always-on-availability-group-on-an-existing-pool-that-uses-database-mirroring"></a><span data-ttu-id="6e658-186">データベース ミラーリングを使用する既存のプールに Always On 可用性グループを展開する</span><span class="sxs-lookup"><span data-stu-id="6e658-186">Deploy an Always On Availability Group on an existing pool that uses database mirroring</span></span>
<span data-ttu-id="6e658-187"><a name="BKMK_MirroredPool_CreateAlwaysOnGroup"> </a></span><span class="sxs-lookup"><span data-stu-id="6e658-187"><a name="BKMK_MirroredPool_CreateAlwaysOnGroup"> </a></span></span>

> [!NOTE]
> <span data-ttu-id="6e658-188">AG にアップグレードするプールが組織の中央管理ストアをホストしている場合は、このプールをアップグレードする前に、まず CMS を別のプールに移動する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6e658-188">If the pool you are upgrading to an AG hosts the Central Management store for your organization, you must first move the CMS to another pool before you upgrade this pool.</span></span> <span data-ttu-id="6e658-189">次のコマンドレットMove-CsManagementServer使用して、プールを移動します。</span><span class="sxs-lookup"><span data-stu-id="6e658-189">Use the Move-CsManagementServer cmdlet to move the pool.</span></span> <span data-ttu-id="6e658-190">組織内に別のプールを持たしていない場合は、プールを AG にアップグレードする前に、Standard Edition サーバーを一時的に展開し、CMS をこのサーバーに移動できます。</span><span class="sxs-lookup"><span data-stu-id="6e658-190">If you do not have another pool in your organization, you can deploy a Standard Edition server temporarily and move the CMS to this server before you upgrade your pool to the AG.</span></span> 
  
1. <span data-ttu-id="6e658-191">Skype for Business Server 管理シェルを開き、次のコマンドレットを入力して、ミラーからプリンシパル ノードにすべてのデータをフェールオーバーします。</span><span class="sxs-lookup"><span data-stu-id="6e658-191">Fail over all data from the mirror to the principal node by opening Skype for Business Server Management Shell and typing the following cmdlet.</span></span>
    
   ```powershell
   Invoke-CsDatabaseFailover -PoolFqdn <Pool FQDN> -DatabaseType <DatabaseType> -NewPrincipal "Primary"
   ```

    <span data-ttu-id="6e658-192">プール内のデータベースの種類ごとに、このコマンドレットを繰り返します。</span><span class="sxs-lookup"><span data-stu-id="6e658-192">Repeat this cmdlet for each database type in the pool.</span></span> <span data-ttu-id="6e658-193">次のコマンドレットを使用して、このプールに格納されているデータベースの種類を検索できます。</span><span class="sxs-lookup"><span data-stu-id="6e658-193">You can use the following cmdlet to find all the database types stored in this pool.</span></span>
     
   ```powershell
   Get-CsPool -Identity <Pool FQDN>
   ```

2. <span data-ttu-id="6e658-194">トポロジ ビルダーを使用して、プールからデータベース ミラーリングを削除します。</span><span class="sxs-lookup"><span data-stu-id="6e658-194">Use Topology Builder to remove database mirroring from the pool.</span></span>
    
   - <span data-ttu-id="6e658-195">トポロジ ビルダーを開きます。</span><span class="sxs-lookup"><span data-stu-id="6e658-195">Open Topology Builder.</span></span> <span data-ttu-id="6e658-196">トポロジで **、Enterprise Edition** フロントエンド プールを展開し、プールの名前を右クリックして、[プロパティの編集] **をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="6e658-196">In your topology, expand **Enterprise Edition Front End Pools**, right-click the name of the pool, and click **Edit Properties**.</span></span>
    
   - <span data-ttu-id="6e658-197">プール内のストアのSQL種類ごとに、[ストア ミラーリングの有効化] SQL **オフ** にします。</span><span class="sxs-lookup"><span data-stu-id="6e658-197">For each type of SQL store in the pool, clear the **Enable SQL Store Mirroring** check box.</span></span>
    
3. <span data-ttu-id="6e658-198">変更されたトポロジを公開します。</span><span class="sxs-lookup"><span data-stu-id="6e658-198">Publish the changed topology.</span></span> <span data-ttu-id="6e658-199">[操作 **] メニューの** [ **トポロジ] をクリックし、[公開]** を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="6e658-199">From the **Action** menu click **Topology** and then **Publish**.</span></span> <span data-ttu-id="6e658-200">次に、確認ページで [次へ] を **クリックします。**</span><span class="sxs-lookup"><span data-stu-id="6e658-200">Then in the confirmation page click **Next**</span></span>
    
4. <span data-ttu-id="6e658-201">ミラー SQL Server Management Studioを壊す場合は、このコマンドを使用します。</span><span class="sxs-lookup"><span data-stu-id="6e658-201">Use SQL Server Management Studio to break the mirror.</span></span>
    
   - <span data-ttu-id="6e658-202">データベースSQL Server Management Studio開き、データベースに移動し、[タスク] を右クリックして **、[ミラー** ] をクリック **します**。</span><span class="sxs-lookup"><span data-stu-id="6e658-202">Open SQL Server Management Studio, navigate to your databases, right-click **Tasks** and click **Mirror**.</span></span> <span data-ttu-id="6e658-203">次に、[**ミラーリングの削除] をクリックし\*\*\*\*、[OK] をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="6e658-203">Then click **Remove Mirroring** and click **OK**.</span></span>
    
   - <span data-ttu-id="6e658-204">AG に変換されるプール内のすべてのデータベースについて、この手順を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="6e658-204">Repeat this for all databases in the pool which will be converted to an AG.</span></span>
    
5. <span data-ttu-id="6e658-205">AG の一部になるすべてのデータベース サーバーでフェールオーバー クラスタリング機能をセットアップします。</span><span class="sxs-lookup"><span data-stu-id="6e658-205">Set up the Failover Clustering feature on all the database servers which will be part of the AG.</span></span> <span data-ttu-id="6e658-206">各サーバーで、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="6e658-206">On each server, do the following</span></span>
    
   - <span data-ttu-id="6e658-207">サーバー マネージャーを開き、[役割と **機能の追加] をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="6e658-207">Open Server Manager and click **Add roles and features**.</span></span>
    
   - <span data-ttu-id="6e658-208">[機能 **の選択** ] ボックスが表示されるまで 、[ **次へ] をクリック** します。</span><span class="sxs-lookup"><span data-stu-id="6e658-208">Click **Next** until you reach the **Select features** box.</span></span> <span data-ttu-id="6e658-209">ここで、[フェールオーバー クラスタリング **] チェック ボックスを** オンにします。</span><span class="sxs-lookup"><span data-stu-id="6e658-209">Here, select the **Failover Clustering** check box.</span></span>
    
   - <span data-ttu-id="6e658-210">[フェールオーバー **クラスタリングに必要な機能の追加** ] ボックスで、[機能の追加] **をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="6e658-210">In the **Add features that are required for Failover Clustering?** box, click **Add Features**.</span></span>
    
   - <span data-ttu-id="6e658-211">**[インストール]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6e658-211">Click **Install**.</span></span>
    
6. <span data-ttu-id="6e658-212">クラスター構成を検証します。</span><span class="sxs-lookup"><span data-stu-id="6e658-212">Validate the cluster configuration.</span></span>
    
   - <span data-ttu-id="6e658-213">サーバー マネージャーで、[ツール] メニュー **をクリック** し、[フェールオーバー クラスター マネージャー] **をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="6e658-213">In Server Manager, click the **Tools** menu and then click **Failover Cluster Manager**.</span></span>
    
   - <span data-ttu-id="6e658-214">画面 **の右側** にある [操作] で、[構成の検証] **をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="6e658-214">Under **Actions** on the right side of the screen, click **Validate Configuration**.</span></span>
    
   - <span data-ttu-id="6e658-215">**[始める前に]** ページで、 **[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6e658-215">On the **Before You Begin** page, click **Next**.</span></span>
    
   - <span data-ttu-id="6e658-216">クラスターに追加するサーバーを選択し、[すべてのテストを実行] **をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="6e658-216">Select the servers to add to the cluster, and then click **Run all tests**.</span></span>
    
   - <span data-ttu-id="6e658-217">[概要 **] ボックス** で、ウィザードによって報告されるエラーを確認します。</span><span class="sxs-lookup"><span data-stu-id="6e658-217">In the **Summary** box, check any errors that the wizard reports.</span></span> <span data-ttu-id="6e658-218">次に、[ **完了]** をクリックして検証を完了します。</span><span class="sxs-lookup"><span data-stu-id="6e658-218">Then click **Finish** to complete the validation.</span></span>
    
     <span data-ttu-id="6e658-219">特に共有ストレージを使用していない場合は、ウィザードによっていくつかの警告が報告される可能性があります。</span><span class="sxs-lookup"><span data-stu-id="6e658-219">The wizard will probably report several warnings, especially if you are not using shared storage.</span></span> <span data-ttu-id="6e658-220">共有ストレージを使用する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="6e658-220">You are not required to use shared storage.</span></span> <span data-ttu-id="6e658-221">ただし、エラー メッセージが表示 **された場合** は、続行する前にそれらの問題を修正する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6e658-221">However, if you see any **Error** messages, you must fix those issues before continuing.</span></span>
    
7. <span data-ttu-id="6e658-222">Windows Server フェールオーバー クラスターを作成します。</span><span class="sxs-lookup"><span data-stu-id="6e658-222">Create the Windows Server Failover Cluster.</span></span>
    
   - <span data-ttu-id="6e658-223">フェールオーバー クラスター **管理ウィザードで、[** フェールオーバー クラスター管理] を **右クリックし**、[クラスターの作成] **をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="6e658-223">In the **Failover Cluster Management** wizard, right-click **Failover Cluster Management**, then click **Create Cluster**.</span></span>
    
   - <span data-ttu-id="6e658-224">**[始める前に]** ページで、 **[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6e658-224">On the **Before You Begin** page, click **Next**.</span></span>
    
   - <span data-ttu-id="6e658-225">クラスター名と IP アドレスを追加します。</span><span class="sxs-lookup"><span data-stu-id="6e658-225">Add the cluster name and IP address.</span></span> <span data-ttu-id="6e658-226">設定が検証された後、[次へ] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="6e658-226">When the settings are validated, click **Next**.</span></span>
    
   - <span data-ttu-id="6e658-227">[確認] ページで、 **[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6e658-227">On the Confirmation page, click **Next**.</span></span>
    
   - <span data-ttu-id="6e658-228">クラスターが作成された後、[完了] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="6e658-228">After the cluster is created, click **Finish**.</span></span>
    
8. <span data-ttu-id="6e658-229">ファイル共有監視を使用するクラスター クォーラム設定を構成することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="6e658-229">We recommend that you configure the cluster quorum settings to use a file share witness.</span></span> <span data-ttu-id="6e658-230">これを行うには、次の手順を使用します。</span><span class="sxs-lookup"><span data-stu-id="6e658-230">To do so, use these steps:</span></span>
    
   - <span data-ttu-id="6e658-231">クラスター名を右クリックし、[その他の操作 **] を** クリックして、[クラスター クォーラム設定の構成 **] をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="6e658-231">Right-click the cluster name, click **More Actions**, and click **Configure Cluster Quorum Settings**.</span></span>
    
   - <span data-ttu-id="6e658-232">[クォー **ラム構成オプションの選択] ページ** で、[クォーラム監視 **の選択] をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="6e658-232">In the **Select Quorum Configuration Option** page, click **Select the quorum witness**.</span></span>
    
   - <span data-ttu-id="6e658-233">[クォー **ラム監視の選択]** ページで、[ファイル共有監視 **の構成] をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="6e658-233">In the **Select Quorum Witness** page, click **Configure a file share witness**.</span></span>
    
   - <span data-ttu-id="6e658-234">[ファイル **共有監視の** 構成] ページで、使用するファイル共有のパスを入力し、[次へ] をクリック **します**。</span><span class="sxs-lookup"><span data-stu-id="6e658-234">In the **Configure File Share Witness** page, type the path of the file share you want to use, and then click **Next**.</span></span>
    
   - <span data-ttu-id="6e658-235">**[確認]** ページで、 **[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6e658-235">On the **Confirmation** page, click **Next**.</span></span>
    
9. <span data-ttu-id="6e658-236">クラスター内の各サーバーで、Configuration Manager で AG SQL Server有効にします。</span><span class="sxs-lookup"><span data-stu-id="6e658-236">On each server in the cluster, enable the AG feature in SQL Server Configuration Manager.</span></span>
    
   - <span data-ttu-id="6e658-237">SQL Server 構成マネージャーを開きます。</span><span class="sxs-lookup"><span data-stu-id="6e658-237">Open SQL Server Configuration Manager.</span></span> <span data-ttu-id="6e658-238">画面の左側のツリーで、[SQL Server **サービス**] をクリックし、SQL Serverします。</span><span class="sxs-lookup"><span data-stu-id="6e658-238">In the tree on the left side of the screen, click **SQL Server Services**, then double-click the SQL Server service.</span></span> 
    
   - <span data-ttu-id="6e658-239">[プロパティ **] ボックス** で **、[AlwaysOn 高可用性] タブを選択** します。 **[AlwaysOn 可用性グループを有効にする]** チェック ボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="6e658-239">In the **Properties** box, select the **AlwaysOn High Availability** tab. Select the **Enable AlwaysOn Availability Groups** check box.</span></span> <span data-ttu-id="6e658-240">メッセージが表示されたらSQL Serverサービスを再起動します。</span><span class="sxs-lookup"><span data-stu-id="6e658-240">Restart the SQL Server service when prompted.</span></span>
    
10. <span data-ttu-id="6e658-241">可用性グループを作成します。</span><span class="sxs-lookup"><span data-stu-id="6e658-241">Create the availability group.</span></span>
    
    - <span data-ttu-id="6e658-242">新SQL Server Management Studio開き、新しいインスタンスSQL Serverします。</span><span class="sxs-lookup"><span data-stu-id="6e658-242">Open SQL Server Management Studio, and connect to the SQL Server instance.</span></span>
    
    - <span data-ttu-id="6e658-243">オブジェクト エクスプローラーで **、Always On 高可用性フォルダーを展開** します。</span><span class="sxs-lookup"><span data-stu-id="6e658-243">In Object Explorer, expand the **Always On High Availability** folder.</span></span> <span data-ttu-id="6e658-244">可用性グループ フォルダーを **右クリックし** 、新しい可用性グループ **ウィザードをクリックします**。</span><span class="sxs-lookup"><span data-stu-id="6e658-244">Right-click the **Availability Groups** folder and click **New Availability Group Wizard**.</span></span>
    
    - <span data-ttu-id="6e658-245">[概要] **ページが** 表示されたら、[次へ] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="6e658-245">If the **Introduction** page appears, click **Next**.</span></span>
    
    - <span data-ttu-id="6e658-246">[可用性 **グループ名の指定** ] ページで、可用性グループの名前を入力し、[次へ] をクリック **します**。</span><span class="sxs-lookup"><span data-stu-id="6e658-246">In the **Specify Availability Group Name** page, type the name of the Availability group, and click **Next**.</span></span>
    
    - <span data-ttu-id="6e658-247">[データベースの選択] ページで、AlwaysOn 可用性グループに含めるデータベースを選択します。</span><span class="sxs-lookup"><span data-stu-id="6e658-247">In the Select Databases page, select the databases that you want to include in the AlwaysOn Availability Group.</span></span> <span data-ttu-id="6e658-248">次に、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6e658-248">Then click **Next**.</span></span>
    
    <span data-ttu-id="6e658-249">このシナリオではサポートされていないので **、AlwaysOn** 可用性グループには ReportServer データベース **、ReportServerTempDB** データベース、または常設チャット データベースを含めずにしてください。</span><span class="sxs-lookup"><span data-stu-id="6e658-249">Do not include the **ReportServer**, **ReportServerTempDB**, or Persistent Chat databases in the AlwaysOn Availability Group, as these are not supported in this scenario.</span></span> <span data-ttu-id="6e658-250">AlwaysOn 可用性グループには、他のすべての Skype for Business Server データベースを含めできます。</span><span class="sxs-lookup"><span data-stu-id="6e658-250">You can include all other Skype for Business Server databases in the AlwaysOn Availability Group.</span></span>
    
    - <span data-ttu-id="6e658-251">[レプリカ **の指定] ページ** で、[レプリカ] **タブをクリック** します。次に、[ **レプリカ** の追加] ボタンをクリックし、Windows Server フェールオーバー クラスターのノードとして参加SQL他のインスタンスに接続します。</span><span class="sxs-lookup"><span data-stu-id="6e658-251">In the **Specify Replicas** page, click the **Replicas** tab. Then click the **Add Replicas** button, and connect to the other SQL instances that you joined as nodes of the Windows Server Failover Cluster.</span></span>
    
    - <span data-ttu-id="6e658-252">インスタンスごとに、[自動フェールオーバーと **同期コミット** ] **オプションを選択** します。</span><span class="sxs-lookup"><span data-stu-id="6e658-252">For each instance, select the **Automatic Failover** and **Synchronous Commit** options.</span></span> <span data-ttu-id="6e658-253">[読み取り可能な **セカンダリ] オプションは選択** できません。</span><span class="sxs-lookup"><span data-stu-id="6e658-253">Do not select the **Readable Secondary** option.</span></span>
    
    - <span data-ttu-id="6e658-254">[エンドポイント **] タブを** クリックし、 **ポート** 番号が 5022 に設定されています。</span><span class="sxs-lookup"><span data-stu-id="6e658-254">Click the **Endpoints** tab and verify that **Port Number** is set to 5022.</span></span>
    
      - <span data-ttu-id="6e658-255">[リスナー **] タブを** クリックし、[可用性グループ リスナー **の作成] オプションを選択** します。</span><span class="sxs-lookup"><span data-stu-id="6e658-255">Click the **Listener** tab, and select the **Create an availability group listener** option.</span></span> <span data-ttu-id="6e658-256">このオプションの下にリスナーの名前を入力し、 **ポート** を 1433 に設定します (他のポートは、このオプションではサポートされていません)。</span><span class="sxs-lookup"><span data-stu-id="6e658-256">Under that option, type a name for the listener, and set the **Port** to 1433 (other ports are not supported for this option).</span></span>
    
    - <span data-ttu-id="6e658-257">[ **追加]** をクリックし **、[IPv4 アドレス** ] ボックスに希望する仮想 IP アドレスを入力し **、[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6e658-257">Click **Add**, and then in the **IPv4 Address** box, provide your preferred virtual IP address, and then click **OK**.</span></span>
    
    - <span data-ttu-id="6e658-258">[初期データ同期の選択] ページで [完全] を選択し、レプリカからアクセス可能なフォルダーを指定します。また、両方のレプリカで使用される SQL Server サービス アカウントに書き込みアクセス許可が付与されます。</span><span class="sxs-lookup"><span data-stu-id="6e658-258">In the **Select Initial Data Synchronization** page, select Full, and specify a folder that is accessible to the replicas, and that the SQL Server service account used by both replicas has Write permissions for.</span></span> <span data-ttu-id="6e658-259">次に、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6e658-259">Then click **Next**.</span></span>
    
    <span data-ttu-id="6e658-260">このファイル共有は、データベースを初期化するときに一時的に使用されます。</span><span class="sxs-lookup"><span data-stu-id="6e658-260">This file share will be used temporarily when you initialize the databases.</span></span> <span data-ttu-id="6e658-261">大規模なデータベースを扱う場合は、ネットワーク帯域幅がデータベース バックアップのサイズに対応できない場合に備え、手動で初期化することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="6e658-261">If you are dealing with large databases, we recommend that you manually initialize them in case your network bandwidth cannot accommodate the size of the database backups.</span></span>
    
    - <span data-ttu-id="6e658-262">[検証] ページで、すべての検証チェックが成功したと確認し、[次へ] をクリック **します**。</span><span class="sxs-lookup"><span data-stu-id="6e658-262">In the Validation page, verify that all validation checks are successful, then click **Next**.</span></span>
    
    - <span data-ttu-id="6e658-263">[概要 **] ページで** 、すべての設定を確認し、[完了] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6e658-263">In the **Summary** page, verify all settings and click Finish.</span></span>
    
11. <span data-ttu-id="6e658-264">AG リスナーを指定し、古いミラーのプリンシパルを AG のプライマリ ノードとして指定する新しいストアを作成します。</span><span class="sxs-lookup"><span data-stu-id="6e658-264">Create a new store specifying the AG listener, and specifying the principal of the old mirror as the primary node of the AG.</span></span>
    
    - <span data-ttu-id="6e658-265">トポロジ ビルダーを開きます。</span><span class="sxs-lookup"><span data-stu-id="6e658-265">Open Topology Builder.</span></span> <span data-ttu-id="6e658-266">トポロジで、[共有コンポーネント]を展開し、[ストア] を右SQL Server **して**、[新しいストア] **SQL Serverします**。</span><span class="sxs-lookup"><span data-stu-id="6e658-266">In your topology, expand **Shared Components**, right-click **SQL Server Stores**, and click **New SQL Server Store**.</span></span>
    
    - <span data-ttu-id="6e658-267">[新しい SQL ストアの定義] ページで、最初に [高可用性の設定] チェック ボックスをオンにし、ドロップダウン ボックスに SQL AlwaysOn 可用性グループが表示されます。</span><span class="sxs-lookup"><span data-stu-id="6e658-267">In the **Define New SQL Store** page, first select the **High Availability Settings** check box, and then make sure that SQL AlwaysOn Availability Groups appears in the drop-down box.</span></span>
    
    - <span data-ttu-id="6e658-268">[可用性 **SQL Server FQDN]** ボックスに、可用性グループの作成時に作成したリスナーの FQDN を入力します。</span><span class="sxs-lookup"><span data-stu-id="6e658-268">In the **SQL Server Availability Listener FQDN** box, type the FQDN of the listener you created when you created the availability group.</span></span>
    
    - <span data-ttu-id="6e658-269">[次 **SQL Server FQDN]** ボックスに、AG のプライマリ ノードの FQDN を入力し **、[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6e658-269">In the **SQL Server FQDN** box, type the FQDN of the primary node of the AG, and then click **OK**.</span></span> <span data-ttu-id="6e658-270">これは、このストアの古いミラーのプリンシパルである必要があります。</span><span class="sxs-lookup"><span data-stu-id="6e658-270">This should be the principal of the old mirror for this store.</span></span>
    
12. <span data-ttu-id="6e658-271">新しい AG をフロントエンド プールに関連付ける。</span><span class="sxs-lookup"><span data-stu-id="6e658-271">Associate the new AG with the Front End pool.</span></span>
    
    - <span data-ttu-id="6e658-272">トポロジ ビルダーで、AG に関連付けるプールを右クリックし、[プロパティの編集] **をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="6e658-272">In Topology Builder, right-click the pool to associate with the AG, and click **Edit Properties**.</span></span>
    
    - <span data-ttu-id="6e658-273">[ **関連付け]** の [ストア] **ボックスSQL Server AG** を選択します。</span><span class="sxs-lookup"><span data-stu-id="6e658-273">Under **Associations**, in the **SQL Server Store** box, select the AG.</span></span> <span data-ttu-id="6e658-274">AG に移動するプール内の他のデータベースに同じグループを選択します。</span><span class="sxs-lookup"><span data-stu-id="6e658-274">Select the same group for any other databases in the pool which you want to move to the AG.</span></span>
    
    - <span data-ttu-id="6e658-275">必要なすべてのデータベースが AG に設定されているのが確実な場合は **、[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6e658-275">When you're sure that all needed databases are set to the AG, click **OK**.</span></span>
    
13. <span data-ttu-id="6e658-276">トポロジを公開します。</span><span class="sxs-lookup"><span data-stu-id="6e658-276">Publish the topology.</span></span> <span data-ttu-id="6e658-277">[操作 **] メニューの** [ **トポロジ] をクリックし、[公開]** を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="6e658-277">From the **Action** menu click **Topology** and then **Publish**.</span></span> <span data-ttu-id="6e658-278">次に、確認ページで [次へ] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="6e658-278">Then in the confirmation page click **Next**.</span></span>
    
14. <span data-ttu-id="6e658-279">最後の手順を実行して、SQL AlwaysOn 可用性グループ内の各レプリカにログインを実行します。</span><span class="sxs-lookup"><span data-stu-id="6e658-279">Perform some final steps to make sure that the SQL logins are on each of the replicas in the AlwaysOn Availability Group.</span></span>
    
    - <span data-ttu-id="6e658-280">トポロジ ビルダーを開き、[既存の展開から **トポロジ** をダウンロードする] を選択し **、[OK] をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="6e658-280">Open Topology Builder, select **Download topology from existing deployment**, and click **OK**.</span></span>
    
    - <span data-ttu-id="6e658-281">[Skype for Business Server] を展開し、トポロジを展開し、[ストア] **SQL Server展開します**。</span><span class="sxs-lookup"><span data-stu-id="6e658-281">Expand Skype for Business Server, expand your topology, and expand **SQL Server Stores**.</span></span> <span data-ttu-id="6e658-282">新しい AG のSQLを右クリックし、[プロパティの編集] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="6e658-282">Right-click the SQL store of the new AG, and click **Edit Properties**.</span></span>
    
    - <span data-ttu-id="6e658-283">ページの下部にある [ SQL Server **FQDN]** ボックスで、値を AG のリスナーの FQDN に変更します。</span><span class="sxs-lookup"><span data-stu-id="6e658-283">At the bottom of the page, in the **SQL Server FQDN** box, change the value to the FQDN of the Listener of the AG.</span></span>
    
    - <span data-ttu-id="6e658-284">トポロジを公開します。</span><span class="sxs-lookup"><span data-stu-id="6e658-284">Publish the topology.</span></span> <span data-ttu-id="6e658-285">[操作 **] メニューの** [ **トポロジ] をクリックし、[公開]** を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="6e658-285">From the **Action** menu click **Topology** and then **Publish**.</span></span> <span data-ttu-id="6e658-286">次に、確認ページで [次へ] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="6e658-286">Then in the confirmation page click **Next**.</span></span> <span data-ttu-id="6e658-287">その後、新しいトポロジがレプリケートされるのを数分待ちます。</span><span class="sxs-lookup"><span data-stu-id="6e658-287">Then wait a few minutes for the new topology to replicate.</span></span>
    
    - <span data-ttu-id="6e658-288">ファイルSQL Server Management Studio開き、AG に移動します。</span><span class="sxs-lookup"><span data-stu-id="6e658-288">Open SQL Server Management Studio, and navigate to the AG.</span></span> <span data-ttu-id="6e658-289">セカンダリ レプリカにフェールオーバーします。</span><span class="sxs-lookup"><span data-stu-id="6e658-289">Fail it over to a secondary replica.</span></span>
    
    - <span data-ttu-id="6e658-290">Skype for Business Server 管理シェルを開き、次のコマンドレットを入力して、このレプリカSQLログインを作成します。</span><span class="sxs-lookup"><span data-stu-id="6e658-290">Open Skype for Business Server Management Shell and type the following cmdlet to create the SQL logins on this replica:</span></span>
    
    ```powershell
    Install-CsDatabase -Update
    ```

    - <span data-ttu-id="6e658-291">グループ内の各レプリカについて、前の 2 つの手順を繰り返します (グループをセカンダリ レプリカにフェールオーバーし、次に  `Install-CsDatabase -Update` 使用します)。</span><span class="sxs-lookup"><span data-stu-id="6e658-291">Repeat the previous two steps (fail over the group to a secondary replica, then use  `Install-CsDatabase -Update`) for each replica in the group.</span></span>
    
## <a name="deploy-an-always-on-availability-group-on-an-existing-pool-that-does-not-use-database-mirroring"></a><span data-ttu-id="6e658-292">データベース ミラーリングを使用しない既存のプールに Always On 可用性グループを展開する</span><span class="sxs-lookup"><span data-stu-id="6e658-292">Deploy an Always On Availability Group on an existing pool that does not use database mirroring</span></span>
<span data-ttu-id="6e658-293"><a name="BKMK_NoHAPool_CreateAlwaysOnGroup"> </a></span><span class="sxs-lookup"><span data-stu-id="6e658-293"><a name="BKMK_NoHAPool_CreateAlwaysOnGroup"> </a></span></span>

> [!NOTE]
> <span data-ttu-id="6e658-294">AG にアップグレードするプールが組織の中央管理ストアをホストしている場合は、このプールをアップグレードする前に、まず CMS を別のプールに移動する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6e658-294">If the pool you are upgrading to an AG hosts the Central Management store for your organization, you must first move the CMS to another pool before you upgrade this pool.</span></span> <span data-ttu-id="6e658-295">次のコマンドレットMove-CsManagementServer使用して、プールを移動します。</span><span class="sxs-lookup"><span data-stu-id="6e658-295">Use the Move-CsManagementServer cmdlet to move the pool.</span></span> <span data-ttu-id="6e658-296">組織内に別のプールを持たしていない場合は、プールを AG にアップグレードする前に、Standard Edition サーバーを一時的に展開し、CMS をこのサーバーに移動できます。</span><span class="sxs-lookup"><span data-stu-id="6e658-296">If you do not have another pool in your organization, you can deploy a Standard Edition server temporarily and move the CMS to this server before you upgrade your pool to the AG.</span></span> 
  
1. <span data-ttu-id="6e658-297">AG の一部になるすべてのデータベース サーバーでフェールオーバー クラスタリング機能をセットアップします。</span><span class="sxs-lookup"><span data-stu-id="6e658-297">Set up the Failover Clustering feature on all the database servers which will be part of the AG.</span></span> <span data-ttu-id="6e658-298">各サーバーで、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="6e658-298">On each server, do the following</span></span>
    
   - <span data-ttu-id="6e658-299">サーバー マネージャーを開き、[役割と **機能の追加] をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="6e658-299">Open Server Manager and click **Add roles and features**.</span></span>
    
   - <span data-ttu-id="6e658-300">[機能 **の選択** ] ボックスが表示されるまで 、[ **次へ] をクリック** します。</span><span class="sxs-lookup"><span data-stu-id="6e658-300">Click **Next** until you reach the **Select features** box.</span></span> <span data-ttu-id="6e658-301">ここで、[フェールオーバー クラスタリング **] チェック ボックスを** オンにします。</span><span class="sxs-lookup"><span data-stu-id="6e658-301">Here, select the **Failover Clustering** check box.</span></span>
    
   - <span data-ttu-id="6e658-302">[フェールオーバー **クラスタリングに必要な機能の追加** ] ボックスで、[機能の追加] **をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="6e658-302">In the **Add features that are required for Failover Clustering?** box, click **Add Features**.</span></span>
    
   - <span data-ttu-id="6e658-303">**[インストール]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6e658-303">Click **Install**.</span></span>
    
2. <span data-ttu-id="6e658-304">クラスター構成を検証します。</span><span class="sxs-lookup"><span data-stu-id="6e658-304">Validate the cluster configuration.</span></span>
    
   - <span data-ttu-id="6e658-305">サーバー マネージャーで、[ツール] メニュー **をクリック** し、[フェールオーバー クラスター マネージャー] **をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="6e658-305">In Server Manager, click the **Tools** menu and then click **Failover Cluster Manager**.</span></span>
    
   - <span data-ttu-id="6e658-306">画面 **の右側** にある [操作] で、[構成の検証] **をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="6e658-306">Under **Actions** on the right side of the screen, click **Validate Configuration**.</span></span>
    
   - <span data-ttu-id="6e658-307">**[始める前に]** ページで、 **[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6e658-307">On the **Before You Begin** page, click **Next**.</span></span>
    
   - <span data-ttu-id="6e658-308">クラスターに追加するサーバーを選択し、[すべてのテストを実行] **をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="6e658-308">Select the servers to add to the cluster, and then click **Run all tests**.</span></span>
    
   - <span data-ttu-id="6e658-309">[概要 **] ボックス** で、ウィザードによって報告されるエラーを確認します。</span><span class="sxs-lookup"><span data-stu-id="6e658-309">In the **Summary** box, check any errors that the wizard reports.</span></span> <span data-ttu-id="6e658-310">次に、[ **完了]** をクリックして検証を完了します。</span><span class="sxs-lookup"><span data-stu-id="6e658-310">Then click **Finish** to complete the validation.</span></span>
    
     <span data-ttu-id="6e658-311">特に共有ストレージを使用していない場合は、ウィザードによっていくつかの警告が報告される可能性があります。</span><span class="sxs-lookup"><span data-stu-id="6e658-311">The wizard will probably report several warnings, especially if you are not using shared storage.</span></span> <span data-ttu-id="6e658-312">共有ストレージを使用する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="6e658-312">You are not required to use shared storage.</span></span> <span data-ttu-id="6e658-313">ただし、エラー メッセージが表示 **された場合** は、続行する前にそれらの問題を修正する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6e658-313">However, if you see any **Error** messages, you must fix those issues before continuing.</span></span>
    
3. <span data-ttu-id="6e658-314">Windows Server フェールオーバー クラスター (WSFC) を作成します。</span><span class="sxs-lookup"><span data-stu-id="6e658-314">Create the Windows Server Failover Cluster (WSFC).</span></span>
    
   - <span data-ttu-id="6e658-315">フェールオーバー クラスター **管理ウィザードで、[** フェールオーバー クラスター管理] を **右クリックし**、[クラスターの作成] **をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="6e658-315">In the **Failover Cluster Management** wizard, right-click **Failover Cluster Management**, then click **Create Cluster**.</span></span>
    
   - <span data-ttu-id="6e658-316">**[始める前に]** ページで、 **[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6e658-316">On the **Before You Begin** page, click **Next**.</span></span>
    
   - <span data-ttu-id="6e658-317">クラスター名と IP アドレスを追加します。</span><span class="sxs-lookup"><span data-stu-id="6e658-317">Add the cluster name and IP address.</span></span> <span data-ttu-id="6e658-318">設定が検証された後、[次へ] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="6e658-318">When the settings are validated, click **Next**.</span></span>
    
   - <span data-ttu-id="6e658-319">[確認] ページで、 **[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6e658-319">On the Confirmation page, click **Next**.</span></span>
    
   - <span data-ttu-id="6e658-320">クラスターが作成された後、[完了] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="6e658-320">After the cluster is created, click **Finish**.</span></span>
    
4. <span data-ttu-id="6e658-321">ファイル共有監視を使用するクラスター クォーラム設定を構成することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="6e658-321">We recommend that you configure the cluster quorum settings to use a file share witness.</span></span> <span data-ttu-id="6e658-322">これを行うには、次の手順を使用します。</span><span class="sxs-lookup"><span data-stu-id="6e658-322">To do so, use these steps:</span></span>
    
   - <span data-ttu-id="6e658-323">クラスター名を右クリックし、[その他の操作 **] を** クリックして、[クラスター クォーラム設定の構成 **] をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="6e658-323">Right-click the cluster name, click **More Actions**, and click **Configure Cluster Quorum Settings**.</span></span>
    
   - <span data-ttu-id="6e658-324">[クォー **ラム構成オプションの選択] ページ** で、[クォーラム監視 **の選択] をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="6e658-324">In the **Select Quorum Configuration Option** page, click **Select the quorum witness**.</span></span>
    
   - <span data-ttu-id="6e658-325">[クォー **ラム監視の選択]** ページで、[ファイル共有監視 **の構成] をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="6e658-325">In the **Select Quorum Witness** page, click **Configure a file share witness**.</span></span>
    
   - <span data-ttu-id="6e658-326">[ファイル **共有監視の** 構成] ページで、使用するファイル共有のパスを入力し、[次へ] をクリック **します**。</span><span class="sxs-lookup"><span data-stu-id="6e658-326">In the **Configure File Share Witness** page, type the path of the file share you want to use, and then click **Next**.</span></span>
    
   - <span data-ttu-id="6e658-327">**[確認]** ページで、 **[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6e658-327">On the **Confirmation** page, click **Next**.</span></span>
    
5. <span data-ttu-id="6e658-328">クラスター内の各サーバーで、Configuration Manager で AG SQL Server有効にします。</span><span class="sxs-lookup"><span data-stu-id="6e658-328">On each server in the cluster, enable AG in SQL Server Configuration Manager.</span></span>
    
   - <span data-ttu-id="6e658-329">SQL Server 構成マネージャーを開きます。</span><span class="sxs-lookup"><span data-stu-id="6e658-329">Open SQL Server Configuration Manager.</span></span> <span data-ttu-id="6e658-330">画面の左側のツリーで、[SQL Server **サービス**] をクリックし、SQL Serverします。</span><span class="sxs-lookup"><span data-stu-id="6e658-330">In the tree on the left side of the screen, click **SQL Server Services**, then double-click the SQL Server service.</span></span> 
    
   - <span data-ttu-id="6e658-331">[プロパティ **] ボックス** で **、[AlwaysOn 高可用性] タブを選択** します。 **[AlwaysOn 可用性グループを有効にする]** チェック ボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="6e658-331">In the **Properties** box, select the **AlwaysOn High Availability** tab. Select the **Enable AlwaysOn Availability Groups** check box.</span></span> <span data-ttu-id="6e658-332">メッセージが表示されたらSQL Serverサービスを再起動します。</span><span class="sxs-lookup"><span data-stu-id="6e658-332">Restart the SQL Server service when prompted.</span></span>
    
6. <span data-ttu-id="6e658-333">可用性グループを作成します。</span><span class="sxs-lookup"><span data-stu-id="6e658-333">Create the availability group.</span></span>
    
   - <span data-ttu-id="6e658-334">新SQL Server Management Studio開き、新しいインスタンスSQL Serverします。</span><span class="sxs-lookup"><span data-stu-id="6e658-334">Open SQL Server Management Studio, and connect to the SQL Server instance.</span></span>
    
   - <span data-ttu-id="6e658-335">オブジェクト エクスプローラーで **、Always On 高可用性フォルダーを展開** します。</span><span class="sxs-lookup"><span data-stu-id="6e658-335">In Object Explorer, expand the **Always On High Availability** folder.</span></span> <span data-ttu-id="6e658-336">可用性グループ フォルダーを **右クリックし** 、新しい可用性グループ **ウィザードをクリックします**。</span><span class="sxs-lookup"><span data-stu-id="6e658-336">Right-click the **Availability Groups** folder and click **New Availability Group Wizard**.</span></span>
    
   - <span data-ttu-id="6e658-337">[概要] **ページが** 表示されたら、[次へ] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="6e658-337">If the **Introduction** page appears, click **Next**.</span></span>
    
   - <span data-ttu-id="6e658-338">[可用性 **グループ名の指定** ] ページで、可用性グループの名前を入力し、[次へ] をクリック **します**。</span><span class="sxs-lookup"><span data-stu-id="6e658-338">In the **Specify Availability Group Name** page, type the name of the Availability group, and click **Next**.</span></span>
    
   - <span data-ttu-id="6e658-339">[データベースの選択] ページで、AG に含めるデータベースを選択します。</span><span class="sxs-lookup"><span data-stu-id="6e658-339">In the Select Databases page, select the databases that you want to include in the AG.</span></span> <span data-ttu-id="6e658-340">次に、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6e658-340">Then click **Next**.</span></span>
    
     <span data-ttu-id="6e658-341">ReportServer データベース **、ReportServerTempDB** データベース、または常設チャット データベースは、このシナリオではサポートされていないので、AG に含めさせはありません。 </span><span class="sxs-lookup"><span data-stu-id="6e658-341">Do not include the **ReportServer**, **ReportServerTempDB**, or Persistent Chat databases in the AG, as these are not supported in this scenario.</span></span> <span data-ttu-id="6e658-342">その他すべての Skype for Business Server データベースを AG に含めできます。</span><span class="sxs-lookup"><span data-stu-id="6e658-342">You can include all other Skype for Business Server databases in the AG.</span></span>
    
   - <span data-ttu-id="6e658-343">[レプリカ **の指定] ページ** で、[レプリカ] **タブをクリック** します。次に、[ **レプリカの** 追加] ボタンをクリックし、WSFC のノードとして参加SQL他のインスタンスに接続します。</span><span class="sxs-lookup"><span data-stu-id="6e658-343">In the **Specify Replicas** page, click the **Replicas** tab. Then click the **Add Replicas** button, and connect to the other SQL instances that you joined as nodes of the WSFC.</span></span>
    
   - <span data-ttu-id="6e658-344">インスタンスごとに、[自動フェールオーバーと **同期コミット** ] **オプションを選択** します。</span><span class="sxs-lookup"><span data-stu-id="6e658-344">For each instance, select the **Automatic Failover** and **Synchronous Commit** options.</span></span> <span data-ttu-id="6e658-345">[読み取り可能な **セカンダリ] オプションは選択** できません。</span><span class="sxs-lookup"><span data-stu-id="6e658-345">Do not select the **Readable Secondary** option.</span></span>
    
   - <span data-ttu-id="6e658-346">[エンドポイント **] タブを** クリックし、 **ポート** 番号が 5022 に設定されています。</span><span class="sxs-lookup"><span data-stu-id="6e658-346">Click the **Endpoints** tab and verify that **Port Number** is set to 5022.</span></span>
    
   - <span data-ttu-id="6e658-347">[リスナー **] タブを** クリックし、[可用性グループ リスナー **の作成] オプションを選択** します。</span><span class="sxs-lookup"><span data-stu-id="6e658-347">Click the **Listener** tab, and select the **Create an availability group listener** option.</span></span> <span data-ttu-id="6e658-348">このオプションの下にリスナーの名前を入力し、 **ポート** を 1433 に設定します (他のポートは、このオプションではサポートされていません)。</span><span class="sxs-lookup"><span data-stu-id="6e658-348">Under that option, type a name for the listener, and set the **Port** to 1433 (other ports are not supported for this option).</span></span>
    
   - <span data-ttu-id="6e658-349">[ **追加]** をクリックし **、[IPv4 アドレス** ] ボックスに希望する仮想 IP アドレスを入力し **、[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6e658-349">Click **Add**, and then in the **IPv4 Address** box, provide your preferred virtual IP address, and then click **OK**.</span></span>
    
   - <span data-ttu-id="6e658-350">[初期データ同期の選択] ページで [完全] を選択し、レプリカからアクセス可能なフォルダーを指定します。また、両方のレプリカで使用される SQL Server サービス アカウントに書き込みアクセス許可が付与されます。</span><span class="sxs-lookup"><span data-stu-id="6e658-350">In the **Select Initial Data Synchronization** page, select Full, and specify a folder that is accessible to the replicas, and that the SQL Server service account used by both replicas has Write permissions for.</span></span> <span data-ttu-id="6e658-351">次に、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6e658-351">Then click **Next**.</span></span>
    
     <span data-ttu-id="6e658-352">このファイル共有は、データベースを初期化するときに一時的に使用されます。</span><span class="sxs-lookup"><span data-stu-id="6e658-352">This file share will be used temporarily when you initialize the databases.</span></span> <span data-ttu-id="6e658-353">大規模なデータベースを扱う場合は、ネットワーク帯域幅がデータベース バックアップのサイズに対応できない場合に備え、手動で初期化することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="6e658-353">If you are dealing with large databases, we recommend that you manually initialize them in case your network bandwidth cannot accommodate the size of the database backups.</span></span>
    
     - <span data-ttu-id="6e658-354">[検証] ページで、すべての検証チェックが成功したと確認し、[次へ] をクリック **します**。</span><span class="sxs-lookup"><span data-stu-id="6e658-354">In the Validation page, verify that all validation checks are successful, then click **Next**.</span></span>
    
   - <span data-ttu-id="6e658-355">[概要 **] ページで** 、すべての設定を確認し、[完了] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6e658-355">In the **Summary** page, verify all settings and click Finish.</span></span>
    
7. <span data-ttu-id="6e658-356">AG リスナーを指定する新しいストアを作成します。</span><span class="sxs-lookup"><span data-stu-id="6e658-356">Create a new store specifying the AG listener.</span></span>
    
   - <span data-ttu-id="6e658-357">トポロジ ビルダーを開きます。</span><span class="sxs-lookup"><span data-stu-id="6e658-357">Open Topology Builder.</span></span> <span data-ttu-id="6e658-358">トポロジで、[共有コンポーネント]を展開し、[ストア] を右SQL Server **して**、[新しいストア] **SQL Serverします**。</span><span class="sxs-lookup"><span data-stu-id="6e658-358">In your topology, expand **Shared Components**, right-click **SQL Server Stores**, and click **New SQL Server Store**.</span></span>
    
   - <span data-ttu-id="6e658-359">[新しい SQL ストアの定義] ページで、最初に [高可用性の設定] チェック ボックスをオンにし、ドロップダウン ボックスに SQL AlwaysOn 可用性グループが表示されます。</span><span class="sxs-lookup"><span data-stu-id="6e658-359">In the **Define New SQL Store** page, first select the **High Availability Settings** check box, and then make sure that SQL AlwaysOn Availability Groups appears in the drop-down box.</span></span>
    
   - <span data-ttu-id="6e658-360">[可用性 **SQL Server FQDN]** ボックスに、可用性グループの作成時に作成したリスナーの FQDN を入力します。</span><span class="sxs-lookup"><span data-stu-id="6e658-360">In the **SQL Server Availability Listener FQDN** box, type the FQDN of the listener you created when you created the availability group.</span></span>
    
   - <span data-ttu-id="6e658-361">[次 **SQL Server FQDN]** ボックスに、AG のプライマリ ノードの FQDN を入力し **、[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6e658-361">In the **SQL Server FQDN** box, type the FQDN of the primary node of the AG, and then click **OK**.</span></span>
    
8. <span data-ttu-id="6e658-362">新しい Always On 可用性グループをフロントエンド プールに関連付ける。</span><span class="sxs-lookup"><span data-stu-id="6e658-362">Associate the new Always On Availability Group with the Front End pool.</span></span>
    
   - <span data-ttu-id="6e658-363">トポロジ ビルダーで、AG に関連付けるプールを右クリックし、[プロパティの編集] **をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="6e658-363">In Topology Builder, right-click the pool to associate with the AG, and click **Edit Properties**.</span></span>
    
   - <span data-ttu-id="6e658-364">[ **関連付け]** の [ストア] **ボックスSQL Server AG** を選択します。</span><span class="sxs-lookup"><span data-stu-id="6e658-364">Under **Associations**, in the **SQL Server Store** box, select the AG.</span></span> <span data-ttu-id="6e658-365">AG に移動するプール内の他のデータベースに同じグループを選択します。</span><span class="sxs-lookup"><span data-stu-id="6e658-365">Select the same group for any other databases in the pool which you want to move to the AG.</span></span>
    
   - <span data-ttu-id="6e658-366">必要なすべてのデータベースが AG に設定されているのが確実な場合は **、[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6e658-366">When you're sure that all needed databases are set to the AG, click **OK**.</span></span>
    
9. <span data-ttu-id="6e658-367">トポロジを公開します。</span><span class="sxs-lookup"><span data-stu-id="6e658-367">Publish the topology.</span></span> <span data-ttu-id="6e658-368">[操作 **] メニューの** [ **トポロジ] をクリックし、[公開]** を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="6e658-368">From the **Action** menu click **Topology** and then **Publish**.</span></span> <span data-ttu-id="6e658-369">次に、確認ページで [次へ] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="6e658-369">Then in the confirmation page click **Next**.</span></span>
    
10. <span data-ttu-id="6e658-370">最後の手順を実行して、SQLが AG 内の各レプリカ上に表示されます。</span><span class="sxs-lookup"><span data-stu-id="6e658-370">Perform some final steps to make sure that the SQL logins are on each of the replicas in the AG.</span></span>
    
    - <span data-ttu-id="6e658-371">トポロジ ビルダーを開き、[既存の展開から **トポロジ** をダウンロードする] を選択し **、[OK] をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="6e658-371">Open Topology Builder, select **Download topology from existing deployment**, and click **OK**.</span></span>
    
    - <span data-ttu-id="6e658-372">[Skype for Business Server] を展開し、トポロジを展開し、[ストア] **SQL Server展開します**。</span><span class="sxs-lookup"><span data-stu-id="6e658-372">Expand Skype for Business Server, expand your topology, and expand **SQL Server Stores**.</span></span> <span data-ttu-id="6e658-373">新しい AG のSQLを右クリックし、[プロパティの編集] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="6e658-373">Right-click the SQL store of the new AG, and click **Edit Properties**.</span></span>
    
    - <span data-ttu-id="6e658-374">ページの下部にある [ SQL Server **FQDN]** ボックスで、値を AG のリスナーの FQDN に変更します。</span><span class="sxs-lookup"><span data-stu-id="6e658-374">At the bottom of the page, in the **SQL Server FQDN** box, change the value to the FQDN of the Listener of the AG.</span></span>
    
    - <span data-ttu-id="6e658-375">トポロジを公開します。</span><span class="sxs-lookup"><span data-stu-id="6e658-375">Publish the topology.</span></span> <span data-ttu-id="6e658-376">[操作 **] メニューの** [ **トポロジ] をクリックし、[公開]** を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="6e658-376">From the **Action** menu click **Topology** and then **Publish**.</span></span> <span data-ttu-id="6e658-377">次に、確認ページで [次へ] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="6e658-377">Then in the confirmation page click **Next**.</span></span> <span data-ttu-id="6e658-378">その後、新しいトポロジがレプリケートされるのを数分待ちます。</span><span class="sxs-lookup"><span data-stu-id="6e658-378">Then wait a few minutes for the new topology to replicate.</span></span>
    
    - <span data-ttu-id="6e658-379">ファイルSQL Server Management Studio開き、AG に移動します。</span><span class="sxs-lookup"><span data-stu-id="6e658-379">Open SQL Server Management Studio, and navigate to the AG.</span></span> <span data-ttu-id="6e658-380">セカンダリ レプリカにフェールオーバーします。</span><span class="sxs-lookup"><span data-stu-id="6e658-380">Fail it over to a secondary replica.</span></span>
    
    - <span data-ttu-id="6e658-381">Skype for Business Server 管理シェルを開き、次のコマンドレットを入力して、このレプリカSQLログインを作成します。</span><span class="sxs-lookup"><span data-stu-id="6e658-381">Open Skype for Business Server Management Shell and type the following cmdlet to create the SQL logins on this replica:</span></span>
    
      ```powershell
      Install-CsDatabase -Update
      ```

      - <span data-ttu-id="6e658-382">グループ内の各レプリカについて、前の 2 つの手順を繰り返します (グループをセカンダリ レプリカにフェールオーバーし、次に  `Install-CsDatabase -Update` 使用します)。</span><span class="sxs-lookup"><span data-stu-id="6e658-382">Repeat the previous two steps (fail over the group to a secondary replica, then use  `Install-CsDatabase -Update`) for each replica in the group.</span></span>
