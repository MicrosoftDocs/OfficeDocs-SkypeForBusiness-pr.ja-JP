---
title: Skype for Business Server 2015 へのアップグレード
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 7/14/2016
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 74ce73bc-356b-4705-83b1-341ee010fd19
description: '概要: Lync Server 2013 から Skype for Business Server 2015 にアップグレードする方法について説明します。 Skype for Business Server 2015 の無料トライアルは、次https://www.microsoft.com/evalcenter/evaluate-skype-for-business-serverの Microsoft 評価センターからダウンロードしてください。'
ms.openlocfilehash: f68e944b75af9f921dacd182bab023177a3ab2b1
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2019
ms.locfileid: "34275515"
---
# <a name="upgrade-to-skype-for-business-server-2015"></a><span data-ttu-id="f7907-104">Upgrade to Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="f7907-104">Upgrade to Skype for Business Server 2015</span></span>
 
<span data-ttu-id="f7907-105">**概要:** Lync Server 2013 から Skype for Business Server 2015 にアップグレードする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="f7907-105">**Summary:** Learn how to upgrade from Lync Server 2013 to Skype for Business Server 2015.</span></span> <span data-ttu-id="f7907-106">[Microsoft 評価センター](https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server)から Skype For business Server 2015 の無料トライアルをダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="f7907-106">Download a free trial of Skype for Business Server 2015 from the  [Microsoft Evaluation center](https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server).</span></span>
  
<span data-ttu-id="f7907-107">このドキュメントの手順を使用して、Skype for Business Server のトポロジビルダーと新しいインプレースアップグレード機能を使用して、Lync Server 2013 から Skype for Business Server 2015 にアップグレードします。</span><span class="sxs-lookup"><span data-stu-id="f7907-107">Use the procedures in this document to upgrade from Lync Server 2013 to Skype for Business Server 2015 by using the Skype for Business Server Topology Builder and the new In-Place Upgrade feature.</span></span> <span data-ttu-id="f7907-108">Lync Server 2010 または Office Communications Server 2007 R2 からアップグレードする場合は、「 [Skype For Business Server 2015 へのアップグレードを計画](../plan-your-deployment/upgrade.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f7907-108">If you want to upgrade from Lync Server 2010 or Office Communications Server 2007 R2, see [Plan to upgrade to Skype for Business Server 2015](../plan-your-deployment/upgrade.md).</span></span>

> [!NOTE]
> <span data-ttu-id="f7907-109">インプレースアップグレードは、Skype for Business Server 2015 で使用できましたが、Skype for Business Server 2019 ではサポートされなくなりました。</span><span class="sxs-lookup"><span data-stu-id="f7907-109">In-place upgrades were available in Skype for Business Server 2015 but are no longer supported in Skype for Business Server 2019.</span></span> <span data-ttu-id="f7907-110">サイドバイサイドの coexistance はサポートされています。詳細については、「 [Skype For Business Server 2019 への移行](../../SfBServer2019/migration/migration-to-skype-for-business-server-2019.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f7907-110">Side by side coexistance is supported, see [Migration to Skype for Business Server 2019](../../SfBServer2019/migration/migration-to-skype-for-business-server-2019.md) for more information.</span></span>
  
## <a name="upgrade-from-lync-server-2013"></a><span data-ttu-id="f7907-111">Lync Server 2013 からのアップグレード</span><span class="sxs-lookup"><span data-stu-id="f7907-111">Upgrade from Lync Server 2013</span></span>

<span data-ttu-id="f7907-112">Lync Server 2013 を Skype for Business Server 2015 にアップグレードするには、必須ソフトウェアのインストール、Skype for Business Server Topology Builder を使用した、プール内のデータベースのアップグレード、および Skype for Business Server のインプレースアップグレードの使用プールに関連付けられているサーバー。</span><span class="sxs-lookup"><span data-stu-id="f7907-112">Upgrading Lync Server 2013 to Skype for Business Server 2015 involves installing prerequisite software, using the Skype for Business Server Topology Builder to upgrade databases in the pool, and using the Skype for Business Server In-Place Upgrade on each of the servers associated with the pool.</span></span> <span data-ttu-id="f7907-113">アップグレードを完了するには、このトピックの 8 つの手順に従います。</span><span class="sxs-lookup"><span data-stu-id="f7907-113">To complete the upgrade, go through the eight steps in this topic.</span></span>
  
### <a name="before-you-begin"></a><span data-ttu-id="f7907-114">始める前に</span><span class="sxs-lookup"><span data-stu-id="f7907-114">Before you begin</span></span>

- <span data-ttu-id="f7907-115">「[Plan to upgrade to Skype for Business Server 2015](../plan-your-deployment/upgrade.md)」を確認します。</span><span class="sxs-lookup"><span data-stu-id="f7907-115">Review [Plan to upgrade to Skype for Business Server 2015](../plan-your-deployment/upgrade.md).</span></span>
    
- <span data-ttu-id="f7907-116">[Skype For Business server 2015 のサーバー要件を](../plan-your-deployment/requirements-for-your-environment/server-requirements.md)確認します。</span><span class="sxs-lookup"><span data-stu-id="f7907-116">Review [Server requirements for Skype for Business Server 2015](../plan-your-deployment/requirements-for-your-environment/server-requirements.md).</span></span>
    
- <span data-ttu-id="f7907-117">[Skype For Business Server 2015 の前提条件をインストール](install/install-prerequisites.md)します。</span><span class="sxs-lookup"><span data-stu-id="f7907-117">[Install prerequisites for Skype for Business Server 2015](install/install-prerequisites.md) .</span></span>
    
- <span data-ttu-id="f7907-118">[Skype For Business Server 2015 をインストール](install/install.md)します。</span><span class="sxs-lookup"><span data-stu-id="f7907-118">[Install Skype for Business Server 2015](install/install.md) .</span></span>
    
### <a name="step-1-install-administrator-tools-and-download-topology"></a><span data-ttu-id="f7907-119">手順 1: 管理ツールをインストールしてトポロジをダウンロードする</span><span class="sxs-lookup"><span data-stu-id="f7907-119">Step 1: Install Administrator tools and download topology</span></span>

1. <span data-ttu-id="f7907-120">Lync OCSCore またはその他の Lync コンポーネントがインストールされていないトポロジのコンピューターに接続します。</span><span class="sxs-lookup"><span data-stu-id="f7907-120">Connect to computer in the topology that does not have Lync OCSCore or any other Lync components installed.</span></span>
    
2. <span data-ttu-id="f7907-121">Skype for Business Server 2015 インストールメディアから、 **OCS_Volume\Setup\AMD64**から setup.exe を実行します。 \*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="f7907-121">From Skype for Business Server 2015 installation media, run **Setup.exe** from **OCS_Volume\Setup\AMD64**.</span></span> 
    
3. <span data-ttu-id="f7907-122">[**インストール**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f7907-122">Click **Install**.</span></span> 
    
4. <span data-ttu-id="f7907-123">ライセンス契約に同意します。</span><span class="sxs-lookup"><span data-stu-id="f7907-123">Accept the license agreement.</span></span>
    
5. <span data-ttu-id="f7907-124">展開ウィザードで、[**管理ツールのインストール**] をクリックして、インストールの手順に従います。</span><span class="sxs-lookup"><span data-stu-id="f7907-124">On the Deployment Wizard, click **Install Administrator tools**, and follow the steps to install.</span></span>
    
     ![[管理ツールのインストール] へのリンクが強調された展開ウィザードのスクリーン ショット](../media/5bbac2d6-a5b3-42b4-a243-7bcf2b04477a.png)
  
6. <span data-ttu-id="f7907-126">Windows のスタート画面で、Skype for Business Server トポロジビルダーを開きます。</span><span class="sxs-lookup"><span data-stu-id="f7907-126">From the Windows Start screen, open Skype for Business Server Topology Builder.</span></span>
    
7. <span data-ttu-id="f7907-127">[**既存の展開からトポロジをダウンロードする**] をクリックして、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f7907-127">Click **Download topology from existing deployment**, and click **Next**.</span></span>
    
8. <span data-ttu-id="f7907-128">トポロジの名前を入力して、[**保存**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f7907-128">Enter a name for the topology, and click **Save**.</span></span>
    
9. <span data-ttu-id="f7907-129">トポロジを保存した場所に移動して、トポロジのコピーを作成します。</span><span class="sxs-lookup"><span data-stu-id="f7907-129">Go to location where you saved the topology, and make a copy of the topology.</span></span>
    
### <a name="step-2-upgrade-and-publish-topology-using-topology-builder"></a><span data-ttu-id="f7907-130">手順 2: トポロジ ビルダーを使用して、トポロジをアップグレードして公開する</span><span class="sxs-lookup"><span data-stu-id="f7907-130">Step 2: Upgrade and publish topology using Topology Builder</span></span>

<span data-ttu-id="f7907-131">アップグレードを開始する前に、アップグレードを計画しているプールのすべてのサービスが実行されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="f7907-131">Before you start the upgrade process, all services must be running for the pools you plan to upgrade.</span></span> <span data-ttu-id="f7907-132">これは、トポロジの変更が、プール内のサーバーのローカル データベースにレプリケートされるようにするためです。</span><span class="sxs-lookup"><span data-stu-id="f7907-132">This is so the topology changes will be replicated to the local database of the servers in the pool.</span></span>
  
> [!IMPORTANT]
>  <span data-ttu-id="f7907-133">アップグレードの前に、トポロジ ファイルのコピーを保存します。</span><span class="sxs-lookup"><span data-stu-id="f7907-133">Save a copy of your topology file before you upgrade.</span></span> <span data-ttu-id="f7907-134">アップグレードした後は、> をダウングレードすることはできません。永続的なチャットサービスが、常設チャットデータベースと同じサーバー上にある場合は、この手順をスキップして、手順4に進みます。</span><span class="sxs-lookup"><span data-stu-id="f7907-134">After you upgrade, you will not be able to downgrade the topology.>  If your services are on the same servers as your databases, like the Persistent Chat service is on the same server as the Persistent Chat database, skip this step, and go to step 4.</span></span> <span data-ttu-id="f7907-135">サービスを停止した後、各サーバー上で一括アップグレードのセットアップを実行して、ローカル データベースをアップグレードします。</span><span class="sxs-lookup"><span data-stu-id="f7907-135">After you stop the services, run the In-Place Upgrade setup on each server to upgrade the local databases.</span></span>
  
> [!NOTE]
> <span data-ttu-id="f7907-p108">ミラー化されているバック エンド データベースがトポロジに含まれる場合、トポロジ ビルダーを使用して**トポロジを公開すると**、プリンシパル データベースとミラー化されたデータベースの両方が表示されます。トポロジを公開するときは、すべてのデータベースがプリンシパル上で実行されていて、ミラーではなくプリンシパルのみを選択していることを確認してください。条件が満たされていない場合、トポロジを公開した後に警告が表示されます。</span><span class="sxs-lookup"><span data-stu-id="f7907-p108">If the topology has a back-end database that is mirrored then you will see both the Principal and the Mirrored databases show up **when you publish the topology** using Topology Builder. Make sure all of the databases are running on the Principal and only select the Principal, not the mirror, when publishing the topology otherwise you will see a warning after publishing the topology.</span></span>
  
<span data-ttu-id="f7907-138">以下のいずれかのオプションを選び、Skype for Business Server 2015 Topology Builder を使用して、新しいトポロジをアップグレードして公開します。</span><span class="sxs-lookup"><span data-stu-id="f7907-138">Pick one of the options below to upgrade and publish a new topology by using the Skype for Business Server 2015 Topology Builder.</span></span> <span data-ttu-id="f7907-139">手順を完了し、アップグレードしたトポロジを公開した後、このトピックの手順 3 に進みます。</span><span class="sxs-lookup"><span data-stu-id="f7907-139">After you complete the steps and publish the updated topology, move to Step 3 in this topic.</span></span>
  
#### <a name="option-1-upgrade-an-isolated-front-end-pool-and-associated-archiving-and-monitoring-stores"></a><span data-ttu-id="f7907-140">オプション 1: 孤立したフロントエンド プールと、関連するアーカイブ ストアと監視ストアをアップグレードする</span><span class="sxs-lookup"><span data-stu-id="f7907-140">Option 1: Upgrade an isolated Front End pool and associated Archiving and Monitoring stores</span></span>

<span data-ttu-id="f7907-141">アップグレードするプールにアーカイブ ストアと監視ストアの依存関係が存在する場合、以下の手順に従って、アーカイブ ストアと監視ストアもアップグレードされます。</span><span class="sxs-lookup"><span data-stu-id="f7907-141">If the pool you're upgrading has an Archiving and Monitoring store dependency, when you use the following steps, the Archiving and Monitoring store will be upgraded as well.</span></span>
  
1. <span data-ttu-id="f7907-142">[トポロジビルダー] で、Lync Server 2013 プールを右クリックし、[ **Skype For Business Server 2015 にアップグレード**] を選択して、手順に従います。</span><span class="sxs-lookup"><span data-stu-id="f7907-142">In Topology Builder, right-click a Lync Server 2013 pool, select **Upgrade to Skype for Business Server 2015**, and follow the steps.</span></span> 
    
     ![Lync Server 2013 のアップグレード オプションが含まれる右クリック メニューのスクリーン ショット](../media/7d5b25b1-e5c0-474c-a024-a5ba33f1b3a1.png)
  
2. <span data-ttu-id="f7907-144">トポロジビルダーで、[**アクション** > **発行トポロジ**] または [**アクション** > **トポロジ** > の**公開**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f7907-144">In Topology Builder, click **Action** > **Publish topology** or **Action** > **Topology** > **Publish**.</span></span> 
    
     ![トポロジ ビルダーの [アクション] メニューの [トポロジの公開] オプションのスクリーン ショット](../media/d6712634-9205-401f-a0b0-3ea096ca51bf.png)
  
3. <span data-ttu-id="f7907-146">公開時に、アーカイブ ストアと監視ストアへのデータベースのインストールを選択します。</span><span class="sxs-lookup"><span data-stu-id="f7907-146">During publishing, choose to install a database on the Archiving and Monitoring store.</span></span>
    
#### <a name="option-2-upgrade-front-end-pool-without-upgrading-archiving-and-monitoring-stores"></a><span data-ttu-id="f7907-147">オプション 2: アーカイブおよび監視ストアをアップグレードせずに、フロントエンドプールをアップグレードする</span><span class="sxs-lookup"><span data-stu-id="f7907-147">Option 2: Upgrade Front End pool without upgrading Archiving and Monitoring stores</span></span>

<span data-ttu-id="f7907-p110">以下の手順に従うと、選択したプールのアーカイブと監視が無効になります。アップグレード後、プールにはアーカイブ ストアと監視ストアは存在しなくなります。</span><span class="sxs-lookup"><span data-stu-id="f7907-p110">If you use the following steps, archiving and monitoring for the selected pool are disabled. The pool will not have Archiving and Monitoring stores after the upgrade.</span></span>
  
1. <span data-ttu-id="f7907-150">[トポロジビルダー] で、アップグレードする Lync Server 2013 プールを選択します。</span><span class="sxs-lookup"><span data-stu-id="f7907-150">In Topology Builder, select the Lync Server 2013 pool that you want to upgrade.</span></span>
    
2. <span data-ttu-id="f7907-151">Lync Server 2013 アーカイブおよび監視ストアへの依存関係を削除します。</span><span class="sxs-lookup"><span data-stu-id="f7907-151">Remove the dependency to the Lync Server 2013 Archiving and Monitoring stores.</span></span> 
    
   - <span data-ttu-id="f7907-152">[**アクション** > の**編集プロパティ**] に移動します。</span><span class="sxs-lookup"><span data-stu-id="f7907-152">Go to **Action** > **Edit properties**.</span></span>
    
   - <span data-ttu-id="f7907-153">[**アーカイブ**] チェック ボックスをオフにします。</span><span class="sxs-lookup"><span data-stu-id="f7907-153">Clear the **Archiving** check box.</span></span>
    
     ![[プロパティの編集] ダイアログの [アーカイブ] チェックボックスのスクリーン ショット](../media/9a88427e-80ee-49d0-a767-809fa9a5faf1.png)
  
   - <span data-ttu-id="f7907-155">[**監視**] チェック ボックスをオフにします。</span><span class="sxs-lookup"><span data-stu-id="f7907-155">Clear the **Monitoring** check box.</span></span>
    
     ![[監視] チェックボックスを示している、[プロパティの編集] ダイアログのスクリーン ショット](../media/880acf33-57bb-4521-8717-cf5b67261ed4.png)
  
3. <span data-ttu-id="f7907-157">Lync Server 2013 プールを右クリックし、[ **Skype For Business Server 2015 にアップグレード**] を選択して、手順に従います。</span><span class="sxs-lookup"><span data-stu-id="f7907-157">Right-click the Lync Server 2013 pool, select **Upgrade to Skype for Business Server 2015**, and follow the steps.</span></span> 
    
     ![Lync Server 2013 のアップグレード オプションが含まれる右クリック メニューのスクリーン ショット](../media/7d5b25b1-e5c0-474c-a024-a5ba33f1b3a1.png)
  
4. <span data-ttu-id="f7907-159">トポロジビルダーで、[**アクション** > **発行トポロジ**] または [**アクション** > **トポロジ** > の**公開**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f7907-159">In Topology Builder, click **Action** > **Publish topology** or **Action** > **Topology** > **Publish**.</span></span> 
    
#### <a name="option-3-upgrade-front-end-pool-and-associated-it-to-new-skype-for-business-server-2015-archiving-and-monitoring-stores"></a><span data-ttu-id="f7907-160">オプション 3: フロントエンドプールをアップグレードし、それに関連付けた新しい Skype for Business Server 2015 アーカイブと監視ストア</span><span class="sxs-lookup"><span data-stu-id="f7907-160">Option 3: Upgrade Front End pool and associated it to new Skype for Business Server 2015 Archiving and Monitoring stores</span></span>

<span data-ttu-id="f7907-161">以下の手順に従うと、アーカイブと監視が以前のストアで停止され、作成した新しいストアで開始されます。</span><span class="sxs-lookup"><span data-stu-id="f7907-161">If you use the following steps, archiving and monitoring will stop in the previous store and start in the new store you've created.</span></span> 
  
1. <span data-ttu-id="f7907-162">[トポロジビルダー] で、アップグレードする Lync Server 2013 プールを選択します。</span><span class="sxs-lookup"><span data-stu-id="f7907-162">In Topology Builder, select the Lync Server 2013 pool that you want to upgrade.</span></span> 
    
2. <span data-ttu-id="f7907-163">Lync Server 2013 アーカイブおよび監視ストアへの依存関係を削除します。</span><span class="sxs-lookup"><span data-stu-id="f7907-163">Remove the dependency to the Lync Server 2013 Archiving and Monitoring stores.</span></span> 
    
   - <span data-ttu-id="f7907-164">[**アクション** > の**編集プロパティ**] に移動します。</span><span class="sxs-lookup"><span data-stu-id="f7907-164">Go to **Action** > **Edit properties**.</span></span>
    
   - <span data-ttu-id="f7907-165">[**アーカイブ**] チェック ボックスをオフにします。</span><span class="sxs-lookup"><span data-stu-id="f7907-165">Clear the **Archiving** check box.</span></span>
    
     ![[プロパティの編集] ダイアログの [アーカイブ] チェックボックスのスクリーン ショット](../media/9a88427e-80ee-49d0-a767-809fa9a5faf1.png)
  
   - <span data-ttu-id="f7907-167">[**監視**] チェック ボックスをオフにします。</span><span class="sxs-lookup"><span data-stu-id="f7907-167">Clear the **Monitoring** check box.</span></span>
    
     ![[監視] チェックボックスを示している、[プロパティの編集] ダイアログのスクリーン ショット](../media/880acf33-57bb-4521-8717-cf5b67261ed4.png)
  
3. <span data-ttu-id="f7907-169">Lync Server 2013 プールを右クリックし、[ **Skype For Business Server 2015 にアップグレード**] を選択して、手順に従います。</span><span class="sxs-lookup"><span data-stu-id="f7907-169">Right-click the Lync Server 2013 pool, select **Upgrade to Skype for Business Server 2015**, and follow the steps.</span></span> 
    
     ![Lync Server 2013 のアップグレード オプションが含まれる右クリック メニューのスクリーン ショット](../media/7d5b25b1-e5c0-474c-a024-a5ba33f1b3a1.png)
  
4. <span data-ttu-id="f7907-171">アーカイブ用の新しい SQL ストアを作成します。</span><span class="sxs-lookup"><span data-stu-id="f7907-171">Create a new SQL store for Archiving.</span></span> 
    
   - <span data-ttu-id="f7907-172">プールと**アクション** > の**編集プロパティ**を選びます。</span><span class="sxs-lookup"><span data-stu-id="f7907-172">Select the pool and **Action** > **Edit properties**.</span></span> 
    
   -  <span data-ttu-id="f7907-173">[**アーカイブ**] チェック ボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="f7907-173">Select the **Archiving** check box.</span></span>
    
   - <span data-ttu-id="f7907-174">[**新規**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f7907-174">Click **New**.</span></span>
    
     ![[アーカイブ] セクションの [新規] ボタンを示している、[プロパティの編集] ダイアログのスクリーン ショット](../media/3a4a18e7-8251-4736-837c-2b486f64f896.png)
  
5. <span data-ttu-id="f7907-176">監視用の新しい SQL ストアを作成します。</span><span class="sxs-lookup"><span data-stu-id="f7907-176">Create a new SQL store for Monitoring.</span></span> 
    
   - <span data-ttu-id="f7907-177">プールと**アクション** > の**編集プロパティ**を選びます。</span><span class="sxs-lookup"><span data-stu-id="f7907-177">Select the pool and **Action** > **Edit properties**.</span></span> 
    
   -  <span data-ttu-id="f7907-178">[**監視**] チェック ボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="f7907-178">Select the **Monitoring** check box.</span></span>
    
   - <span data-ttu-id="f7907-179">[**新規**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f7907-179">Click **New**.</span></span>
    
     ![[監視] セクションの [新規] ボタンを示している、[プロパティの編集] ダイアログのスクリーン ショット](../media/729c72a7-0068-4e0d-99dc-e480a6bfbf1d.png)
  
6. <span data-ttu-id="f7907-181">トポロジビルダーで、[**アクション** > **発行トポロジ**] または [**アクション** > **トポロジ** > の**公開**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f7907-181">In Topology Builder, click **Action** > **Publish topology** or **Action** > **Topology** > **Publish**.</span></span> 
    
7. <span data-ttu-id="f7907-182">公開時に、新しいアーカイブ ストアと監視ストアへのデータベースのインストールを選択します。</span><span class="sxs-lookup"><span data-stu-id="f7907-182">During publishing, choose to install the database on the new Archiving and Monitoring store.</span></span>
    
### <a name="step-3-wait-for-replication"></a><span data-ttu-id="f7907-183">手順 3: レプリケーションを待機する</span><span class="sxs-lookup"><span data-stu-id="f7907-183">Step 3: Wait for replication</span></span>

<span data-ttu-id="f7907-184">更新されたトポロジを、環境内のすべてのサーバーに公開するために、レプリケーションが完了するまで少し待ちます。</span><span class="sxs-lookup"><span data-stu-id="f7907-184">Give replication some time to publish the updated topology to all the servers in the environment.</span></span>
  
### <a name="step-4-stop-all-services-in-pool-to-be-upgraded"></a><span data-ttu-id="f7907-185">手順 4: アップグレードするプールですべてのサービスを停止する</span><span class="sxs-lookup"><span data-stu-id="f7907-185">Step 4: Stop all services in pool to be upgraded</span></span>

<span data-ttu-id="f7907-186">アップグレードするプールをサービスしている各サーバーで、PowerShell で次のコマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="f7907-186">On each server that is servicing the pool that you're going to upgrade, run the following cmdlet in PowerShell:</span></span>
  
```
Disable-CsComputer -Scorch
```

<span data-ttu-id="f7907-187">インプレースアップグレード処理中にサーバーの再起動が必要になる場合があるため、[無効-CsComputer] を使うことをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="f7907-187">We recommend using Disable-CsComputer because you may need to reboot the server during the In-Place Upgrade process.</span></span> <span data-ttu-id="f7907-188">Stop-CsWindowsService を使った場合、再起動後に一部のサービスが自動的に再起動されることがあります。</span><span class="sxs-lookup"><span data-stu-id="f7907-188">If you use Stop-CsWindowsService, some services may restart automatically after a reboot.</span></span> <span data-ttu-id="f7907-189">これにより、インプレースアップグレードが失敗することがあります。</span><span class="sxs-lookup"><span data-stu-id="f7907-189">This may cause the In-Place Upgrade to fail.</span></span>
  
### <a name="step-5-upgrade-front-end-pools-and-non-front-end-pool-servers"></a><span data-ttu-id="f7907-190">手順 5: フロントエンド プールと非フロントエンド プール サーバーをアップグレードする</span><span class="sxs-lookup"><span data-stu-id="f7907-190">Step 5: Upgrade Front End pools and non-Front End pool servers</span></span>

> [!NOTE]
>  <span data-ttu-id="f7907-191">アップグレード前に、Skype for Business Server 2015 に必要なすべての新しい前提条件をインストールしてください。アップグレードを試みる前に、少なくとも 32 GB の空き領域を > してください。</span><span class="sxs-lookup"><span data-stu-id="f7907-191">Before upgrading please install all new prerequisites required for Skype for Business Server 2015 which include:>  At least 32GB of free space before attempting an upgrade.</span></span> <span data-ttu-id="f7907-192">さらに、ドライブが固定ローカルドライブであり、USB または Firewire で接続されていないこと、NTFS ファイルシステムで書式設定されていること、> PowerShell バージョン6.2.9200.0 以降を使用していないことを確認します。最新の Lync Server 2013 を > します。累積的な更新プログラムがインストールされています。 > SQL Server 2012 SP1 がインストールされている > (Microsoft Update を使用した場合に自動的にインストールされる): > Windows Server 2008 R2-[KB2533623](https://support.microsoft.com/kb/2533623)_GT_ windows server 2012-[KB2858668](https://support.microsoft.com/kb/2858668)> windowsサーバー 2012 R2-[KB2982006](https://support.microsoft.com/kb/2982006)</span><span class="sxs-lookup"><span data-stu-id="f7907-192">In addition, make sure that the drive is a fixed local drive, is not connected by USB or Firewire, is formatted with NTFS file system, is not compressed, and does not contain a page file.>  PowerShell version 6.2.9200.0 or later.>  The latest Lync Server 2013 Cumulative Update installed.>  SQL Server 2012 SP1 installed.>  The following KB's installed (installed automatically if using Microsoft Update):>  Windows Server 2008 R2 -[KB2533623](https://support.microsoft.com/kb/2533623)>  Windows Server 2012 -[KB2858668](https://support.microsoft.com/kb/2858668)>  Windows Server 2012 R2 -[KB2982006](https://support.microsoft.com/kb/2982006)</span></span>
  
<span data-ttu-id="f7907-193">各サーバーでインプレースアップグレードを使用して、フロントエンドプール、エッジプール、仲介サーバー、常設チャットプールを更新します。</span><span class="sxs-lookup"><span data-stu-id="f7907-193">Use the In-Place Upgrade on each server to update the Front End pool, Edge pool, Mediation server, and the Persistent Chat pool.</span></span>
  
1. <span data-ttu-id="f7907-194">各サーバーで、Skype \*\*\*\* For business server 2015 インストールメディアの**OCS_Volume\Setup\amd64**から setup.exe を実行します。</span><span class="sxs-lookup"><span data-stu-id="f7907-194">On each server, run **Setup.exe** from **OCS_Volume\Setup\amd64** on the Skype for Business Server 2015 installation media.</span></span>
    
2. <span data-ttu-id="f7907-195">使用許諾契約に同意し、インプレースアップグレードのプロンプトに従います。</span><span class="sxs-lookup"><span data-stu-id="f7907-195">Accept the license agreement and follow the prompts for the In-Place Upgrade.</span></span>
    
3. <span data-ttu-id="f7907-196">フロントエンドプールとフロントエンドプールサーバーの各サーバーについて、この手順を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="f7907-196">Repeat these steps for each server in the Front End pool and on each non-Front End pool server.</span></span>
    
> [!NOTE]
> <span data-ttu-id="f7907-197">インプレースアップグレード中にサーバーを再起動するように求められる場合があります。</span><span class="sxs-lookup"><span data-stu-id="f7907-197">You might be prompted to reboot the server during the In-Place Upgrade.</span></span> <span data-ttu-id="f7907-198">いいですよ。</span><span class="sxs-lookup"><span data-stu-id="f7907-198">That's ok.</span></span> <span data-ttu-id="f7907-199">再起動後、インプレースアップグレードは中断した場所から続行されます。</span><span class="sxs-lookup"><span data-stu-id="f7907-199">After you reboot, the In-Place Upgrade will continue from where it left off.</span></span> 
  
<span data-ttu-id="f7907-200">一括アップグレードが正常に完了すると、次のメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="f7907-200">When the In-Place Upgrade completes successfully, you see the following message.</span></span>
  
![正常に完了した一括アップグレードのスクリーン ショット](../media/2f52cb50-9bb4-4714-a982-9c7a0865f78a.png)
  
### <a name="step-6-restart-services-on-all-upgraded-servers"></a><span data-ttu-id="f7907-202">手順 6: アップグレードしたすべてのサーバーでサービスを再開する</span><span class="sxs-lookup"><span data-stu-id="f7907-202">Step 6: Restart services on all upgraded servers</span></span>

> [!NOTE]
> <span data-ttu-id="f7907-203">サービスを再起動する前に、%ProgramData%\WindowsFabric がすべてのフロントエンドサーバーに存在しないことを確認してください。</span><span class="sxs-lookup"><span data-stu-id="f7907-203">Before restarting the services, please make sure %ProgramData%\WindowsFabric doesn't exist on all Front End Servers.</span></span> <span data-ttu-id="f7907-204">存在する場合は、サービスを開始する前に削除します。</span><span class="sxs-lookup"><span data-stu-id="f7907-204">If it exists, delete it before starting the services.</span></span> 
  
- <span data-ttu-id="f7907-205">フロントエンドプール内のすべてのサーバーのアップグレードが完了したら、次の PowerShell コマンドを使用してサービスを再起動します。</span><span class="sxs-lookup"><span data-stu-id="f7907-205">After you've upgraded all servers in the Front End pool, restart the services by using the following PowerShell command:</span></span> 
    
  ```
  Start-CsPool
  ```

    > [!NOTE]
    > <span data-ttu-id="f7907-p115">一括アップグレードの実行開始前に再起動が必要な保留中のシステムが既に存在する場合は、インストールの最後に一括アップグレードから再起動は求められません。これにより、Start-CSPool コマンドレットを使用してサービスを開始しようとすると、最初のフロントエンド サーバーに対してアセンブリ例外がスローされます。このようなエラーを解決するには、プール内の全サーバーを再起動し、このコマンドレットをもう一度実行してください。</span><span class="sxs-lookup"><span data-stu-id="f7907-p115">If there is already a pending system reboot needed before you start running In-Place Upgrade, then In-Place Upgrade won't ask you to reboot at the end of the installation. This will cause some assembly exceptions to be thrown against the first Front End server when you try to start services using the Start-CSPool cmdlet. To resolve these errors, reboot all of the servers in the pool and run the cmdlet again.</span></span> 
  
- <span data-ttu-id="f7907-209">非フロントエンド プール サーバーでは、以下のコマンドを実行してサービスを再開します。</span><span class="sxs-lookup"><span data-stu-id="f7907-209">On the non-Front End pool servers, restart the services by using the following command:</span></span>
    
  ```
  Start-CsWindowsService
  ```

<span data-ttu-id="f7907-210">一括アップグレードのページで [**OK**] をクリックした後、この手順を完了するための以下の通知が表示されます。</span><span class="sxs-lookup"><span data-stu-id="f7907-210">After you click **OK** on the In-Place Upgrade page, you'll see the following reminder to complete this step.</span></span>
  
![一括アップグレードが正常に完了した後の、次のステップを示しているスクリーン ショット](../media/6a7236b6-9ef9-4df3-8682-b0e4021810f9.png)
  
### <a name="step-7-verify-skype-for-business-functionality-works"></a><span data-ttu-id="f7907-212">手順 7: Skype for Business 機能の動作を確認する</span><span class="sxs-lookup"><span data-stu-id="f7907-212">Step 7: Verify Skype for Business functionality works</span></span>

<span data-ttu-id="f7907-213">アップグレードが成功したことを確認するには、アップグレードされたプールについて、Skype for Business をテストして、機能が期待どおりに機能していることを確認します。</span><span class="sxs-lookup"><span data-stu-id="f7907-213">To make sure the upgrade was successful, for the pool that was upgraded, test Skype for Business to make sure the functionality is working as expected.</span></span> 
  
### <a name="step-8-upgrade-secondary-pools"></a><span data-ttu-id="f7907-214">手順 8: 二次的なプールをアップグレードする</span><span class="sxs-lookup"><span data-stu-id="f7907-214">Step 8: Upgrade secondary pools</span></span>

<span data-ttu-id="f7907-215">このトピックの手順を繰り返して、環境に存在する他のプールをすべてアップグレードします。</span><span class="sxs-lookup"><span data-stu-id="f7907-215">Repeat the steps in this topic to upgrade any additional pools that you have in your environment.</span></span>
  
## <a name="troubleshoot-issues-with-the-in-place-upgrade"></a><span data-ttu-id="f7907-216">一括アップグレードの問題をトラブルシューティングする</span><span class="sxs-lookup"><span data-stu-id="f7907-216">Troubleshoot issues with the In-Place Upgrade</span></span>

<span data-ttu-id="f7907-217">一括アップグレードが失敗すると、次の図のようなメッセージが表示される場合があります。</span><span class="sxs-lookup"><span data-stu-id="f7907-217">If the In-Place Upgrade fails, you might see a message similar to what's in the following image.</span></span> 
  
![必須の累積的な更新プログラムがインストールされていないために一括アップグレードが失敗していることを示しているスクリーン ショット](../media/f84db06b-0841-45a9-870d-7ba4b5a463d5.png)
  
<span data-ttu-id="f7907-219">ページの下部にあるすべてのメッセージを確認して、問題のトラブルシューティングに役立てます。</span><span class="sxs-lookup"><span data-stu-id="f7907-219">Review the full message at the bottom of the page to help you troubleshoot the issue.</span></span> <span data-ttu-id="f7907-220">詳細情報を表示するには、[**ログの表示**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f7907-220">Click **View logs** to get more detail.</span></span>
  
<span data-ttu-id="f7907-221">**アップグレードの準備状況の確認**でインプレースアップグレードが失敗した場合、または**前提条件をインストール**していない場合は、サーバーに最新の Windows server、Lync server、SQL server の更新プログラムがすべて適用されていることを確認してください。また、必要なすべてのソフトウェアとロールがインストール.</span><span class="sxs-lookup"><span data-stu-id="f7907-221">If the In-Place Upgrade fails on **Verifying upgrade readiness** or **Installing missing prerequisites**, make sure the server has all the latest Windows Server, Lync Server, and SQL Server updates applied, and all the required software and roles are installed.</span></span> <span data-ttu-id="f7907-222">必要なものの一覧については、「Skype for business [server 2015 のサーバー要件](../plan-your-deployment/requirements-for-your-environment/server-requirements.md)」および「 [Skype for business server 2015 の前提条件をインストール](install/install-prerequisites.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f7907-222">For a list of what's required, see [Server requirements for Skype for Business Server 2015](../plan-your-deployment/requirements-for-your-environment/server-requirements.md) and [Install prerequisites for Skype for Business Server 2015](install/install-prerequisites.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="f7907-223">関連項目</span><span class="sxs-lookup"><span data-stu-id="f7907-223">See also</span></span>

[<span data-ttu-id="f7907-224">Plan to upgrade to Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="f7907-224">Plan to upgrade to Skype for Business Server 2015</span></span>](../plan-your-deployment/upgrade.md)
  
[<span data-ttu-id="f7907-225">Server requirements for Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="f7907-225">Server requirements for Skype for Business Server 2015</span></span>](../plan-your-deployment/requirements-for-your-environment/server-requirements.md)
  
[<span data-ttu-id="f7907-226">Skype for Business Server 2015 の前提条件のインストール</span><span class="sxs-lookup"><span data-stu-id="f7907-226">Install prerequisites for Skype for Business Server 2015</span></span>](install/install-prerequisites.md)
  
[<span data-ttu-id="f7907-227">Skype for Business Server 2015 のインストール</span><span class="sxs-lookup"><span data-stu-id="f7907-227">Install Skype for Business Server 2015</span></span>](install/install.md)
