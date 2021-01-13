---
title: Skype for Business Server 2015 へのアップグレード
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 7/14/2016
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 74ce73bc-356b-4705-83b1-341ee010fd19
description: '概要: Lync Server 2013 から Skype for Business Server 2015 にアップグレードする方法について学習します。 Microsoft Evaluation Center から Skype for Business Server 2015 の無料試用版を次の場所からダウンロードします https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server 。'
ms.openlocfilehash: cda83d03db697a0adf404af4f6fe6e350abf6b58
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49820427"
---
# <a name="upgrade-to-skype-for-business-server-2015"></a><span data-ttu-id="be924-104">Skype for Business Server 2015 へのアップグレード</span><span class="sxs-lookup"><span data-stu-id="be924-104">Upgrade to Skype for Business Server 2015</span></span>
 
<span data-ttu-id="be924-105">**概要:** Lync Server 2013 から Skype for Business Server 2015 にアップグレードする方法について学習します。</span><span class="sxs-lookup"><span data-stu-id="be924-105">**Summary:** Learn how to upgrade from Lync Server 2013 to Skype for Business Server 2015.</span></span> <span data-ttu-id="be924-106">Microsoft Evaluation Center から Skype for Business Server 2015 の無料試用版  [をダウンロードします](https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server)。</span><span class="sxs-lookup"><span data-stu-id="be924-106">Download a free trial of Skype for Business Server 2015 from the  [Microsoft Evaluation center](https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server).</span></span>
  
<span data-ttu-id="be924-107">このドキュメントの手順を使用して、Skype for Business Server トポロジ ビルダーと新しい In-Place アップグレード機能を使用して Lync Server 2013 から Skype for Business Server 2015 にアップグレードします。</span><span class="sxs-lookup"><span data-stu-id="be924-107">Use the procedures in this document to upgrade from Lync Server 2013 to Skype for Business Server 2015 by using the Skype for Business Server Topology Builder and the new In-Place Upgrade feature.</span></span> <span data-ttu-id="be924-108">Lync Server 2010 または Office Communications Server 2007 R2 からアップグレードする場合は [、「Skype for Business Server 2015](../plan-your-deployment/upgrade.md)へのアップグレードを計画する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="be924-108">If you want to upgrade from Lync Server 2010 or Office Communications Server 2007 R2, see [Plan to upgrade to Skype for Business Server 2015](../plan-your-deployment/upgrade.md).</span></span>

> [!NOTE]
> <span data-ttu-id="be924-109">一時アップグレードは Skype for Business Server 2015 で利用できますが、Skype for Business Server 2019 ではサポートされなくなりました。</span><span class="sxs-lookup"><span data-stu-id="be924-109">In-place upgrades were available in Skype for Business Server 2015 but are no longer supported in Skype for Business Server 2019.</span></span> <span data-ttu-id="be924-110">共存がサポートされている場合は [、「Skype for Business Server 2019](../../SfBServer2019/migration/migration-to-skype-for-business-server-2019.md) への移行」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="be924-110">Side by side coexistance is supported, see [Migration to Skype for Business Server 2019](../../SfBServer2019/migration/migration-to-skype-for-business-server-2019.md) for more information.</span></span>
  
## <a name="upgrade-from-lync-server-2013"></a><span data-ttu-id="be924-111">Lync Server 2013 からのアップグレード</span><span class="sxs-lookup"><span data-stu-id="be924-111">Upgrade from Lync Server 2013</span></span>

<span data-ttu-id="be924-112">Lync Server 2013 を Skype for Business Server 2015 にアップグレードするには、前提条件となるソフトウェアをインストールし、Skype for Business Server トポロジ ビルダーを使用してプール内のデータベースをアップグレードし、プールに関連付けられている各サーバーで Skype for Business Server In-Place アップグレードを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="be924-112">Upgrading Lync Server 2013 to Skype for Business Server 2015 involves installing prerequisite software, using the Skype for Business Server Topology Builder to upgrade databases in the pool, and using the Skype for Business Server In-Place Upgrade on each of the servers associated with the pool.</span></span> <span data-ttu-id="be924-113">アップグレードを完了するには、このトピックの 8 つの手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="be924-113">To complete the upgrade, go through the eight steps in this topic.</span></span>
  
### <a name="before-you-begin"></a><span data-ttu-id="be924-114">はじめに</span><span class="sxs-lookup"><span data-stu-id="be924-114">Before you begin</span></span>

- <span data-ttu-id="be924-115">[Review Plan to upgrade to Skype for Business Server 2015](../plan-your-deployment/upgrade.md).</span><span class="sxs-lookup"><span data-stu-id="be924-115">Review [Plan to upgrade to Skype for Business Server 2015](../plan-your-deployment/upgrade.md).</span></span>
    
- <span data-ttu-id="be924-116">[Skype for Business Server 2015 のサーバー要件を確認します](../plan-your-deployment/requirements-for-your-environment/server-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="be924-116">Review [Server requirements for Skype for Business Server 2015](../plan-your-deployment/requirements-for-your-environment/server-requirements.md).</span></span>
    
- <span data-ttu-id="be924-117">[Skype for Business Server 2015 の前提条件をインストールします](install/install-prerequisites.md) 。</span><span class="sxs-lookup"><span data-stu-id="be924-117">[Install prerequisites for Skype for Business Server 2015](install/install-prerequisites.md) .</span></span>
    
- <span data-ttu-id="be924-118">[Skype for Business Server 2015 をインストールします](install/install.md) 。</span><span class="sxs-lookup"><span data-stu-id="be924-118">[Install Skype for Business Server 2015](install/install.md) .</span></span>
    
### <a name="step-1-install-administrator-tools-and-download-topology"></a><span data-ttu-id="be924-119">手順 1: 管理者ツールをインストールしてトポロジをダウンロードする</span><span class="sxs-lookup"><span data-stu-id="be924-119">Step 1: Install Administrator tools and download topology</span></span>

1. <span data-ttu-id="be924-120">Lync OCSCore または他の Lync コンポーネントがインストールされていないトポロジ内のコンピューターに接続します。</span><span class="sxs-lookup"><span data-stu-id="be924-120">Connect to computer in the topology that does not have Lync OCSCore or any other Lync components installed.</span></span>
    
2. <span data-ttu-id="be924-121">Skype for Business Server 2015インストール メディアから **、Setup.exe\Setup\AMD64 OCS_Volumeを実行します**。</span><span class="sxs-lookup"><span data-stu-id="be924-121">From Skype for Business Server 2015 installation media, run **Setup.exe** from **OCS_Volume\Setup\AMD64**.</span></span> 
    
3. <span data-ttu-id="be924-122">**[インストール]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="be924-122">Click **Install**.</span></span> 
    
4. <span data-ttu-id="be924-123">使用許諾契約書に同意します。</span><span class="sxs-lookup"><span data-stu-id="be924-123">Accept the license agreement.</span></span>
    
5. <span data-ttu-id="be924-124">展開ウィザードで、[管理者ツールのインストール] **をクリック** し、手順に従ってインストールします。</span><span class="sxs-lookup"><span data-stu-id="be924-124">On the Deployment Wizard, click **Install Administrator tools**, and follow the steps to install.</span></span>
    
     ![[Install Administrator Tools] (インストール管理者ツール) へのリンクが示された展開ウィザードのスクリーン ショット。](../media/5bbac2d6-a5b3-42b4-a243-7bcf2b04477a.png)
  
6. <span data-ttu-id="be924-126">Windows のスタート画面で、Skype for Business Server トポロジ ビルダーを開きます。</span><span class="sxs-lookup"><span data-stu-id="be924-126">From the Windows Start screen, open Skype for Business Server Topology Builder.</span></span>
    
7. <span data-ttu-id="be924-127">[ **既存の展開からトポロジをダウンロード] をクリックし、[** 次へ] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="be924-127">Click **Download topology from existing deployment**, and click **Next**.</span></span>
    
8. <span data-ttu-id="be924-128">トポロジの名前を入力し、[保存] をクリック **します**。</span><span class="sxs-lookup"><span data-stu-id="be924-128">Enter a name for the topology, and click **Save**.</span></span>
    
9. <span data-ttu-id="be924-129">トポロジを保存した場所に移動し、トポロジのコピーを作成します。</span><span class="sxs-lookup"><span data-stu-id="be924-129">Go to location where you saved the topology, and make a copy of the topology.</span></span>
    
### <a name="step-2-upgrade-and-publish-topology-using-topology-builder"></a><span data-ttu-id="be924-130">手順 2: トポロジ ビルダーを使用してトポロジをアップグレードおよび公開する</span><span class="sxs-lookup"><span data-stu-id="be924-130">Step 2: Upgrade and publish topology using Topology Builder</span></span>

<span data-ttu-id="be924-131">アップグレード プロセスを開始する前に、アップグレードを計画しているプールに対してすべてのサービスが実行されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="be924-131">Before you start the upgrade process, all services must be running for the pools you plan to upgrade.</span></span> <span data-ttu-id="be924-132">そのため、トポロジの変更はプール内のサーバーのローカル データベースにレプリケートされます。</span><span class="sxs-lookup"><span data-stu-id="be924-132">This is so the topology changes will be replicated to the local database of the servers in the pool.</span></span>
  
> [!IMPORTANT]
>  <span data-ttu-id="be924-133">アップグレードする前に、トポロジ ファイルのコピーを保存します。</span><span class="sxs-lookup"><span data-stu-id="be924-133">Save a copy of your topology file before you upgrade.</span></span> <span data-ttu-id="be924-134">アップグレード後は、トポロジをダウングレードできません。> 常設チャット サービスが常設チャット データベースと同じサーバー上にあるなど、サービスがデータベースと同じサーバーにある場合は、この手順をスキップして、手順 4. に進みます。</span><span class="sxs-lookup"><span data-stu-id="be924-134">After you upgrade, you will not be able to downgrade the topology.>  If your services are on the same servers as your databases, like the Persistent Chat service is on the same server as the Persistent Chat database, skip this step, and go to step 4.</span></span> <span data-ttu-id="be924-135">サービスを停止した後、各サーバーで In-Place アップグレード のセットアップを実行して、ローカル データベースをアップグレードします。</span><span class="sxs-lookup"><span data-stu-id="be924-135">After you stop the services, run the In-Place Upgrade setup on each server to upgrade the local databases.</span></span>
  
> [!NOTE]
> <span data-ttu-id="be924-136">トポロジにミラー化されたバック エンド データベースがある場合、トポロジ ビルダーを使用してトポロジを公開すると、プリンシパル データベースとミラー 化データベースの両方が表示されます。</span><span class="sxs-lookup"><span data-stu-id="be924-136">If the topology has a back-end database that is mirrored then you will see both the Principal and the Mirrored databases show up **when you publish the topology** using Topology Builder.</span></span> <span data-ttu-id="be924-137">すべてのデータベースがプリンシパルで実行され、ミラーではなくプリンシパルのみを選択してください。そうしないと、トポロジの公開後に警告が表示されます。</span><span class="sxs-lookup"><span data-stu-id="be924-137">Make sure all of the databases are running on the Principal and only select the Principal, not the mirror, when publishing the topology otherwise you will see a warning after publishing the topology.</span></span>
  
<span data-ttu-id="be924-138">Skype for Business Server 2015 トポロジ ビルダーを使用して新しいトポロジをアップグレードおよび公開するには、以下のいずれかのオプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="be924-138">Pick one of the options below to upgrade and publish a new topology by using the Skype for Business Server 2015 Topology Builder.</span></span> <span data-ttu-id="be924-139">手順を完了し、更新されたトポロジを公開したら、このトピックの手順 3 に進みます。</span><span class="sxs-lookup"><span data-stu-id="be924-139">After you complete the steps and publish the updated topology, move to Step 3 in this topic.</span></span>
  
#### <a name="option-1-upgrade-an-isolated-front-end-pool-and-associated-archiving-and-monitoring-stores"></a><span data-ttu-id="be924-140">オプション 1: 分離されたフロントエンド プールと関連するアーカイブストアと監視ストアをアップグレードする</span><span class="sxs-lookup"><span data-stu-id="be924-140">Option 1: Upgrade an isolated Front End pool and associated Archiving and Monitoring stores</span></span>

<span data-ttu-id="be924-141">アップグレードするプールにアーカイブ ストアと監視ストアの依存関係がある場合は、次の手順を使用すると、アーカイブ ストアと監視ストアもアップグレードされます。</span><span class="sxs-lookup"><span data-stu-id="be924-141">If the pool you're upgrading has an Archiving and Monitoring store dependency, when you use the following steps, the Archiving and Monitoring store will be upgraded as well.</span></span>
  
1. <span data-ttu-id="be924-142">トポロジ ビルダーで、Lync Server 2013 プールを右クリックし **、[Skype for Business Server 2015** へのアップグレード] を選択して、手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="be924-142">In Topology Builder, right-click a Lync Server 2013 pool, select **Upgrade to Skype for Business Server 2015**, and follow the steps.</span></span> 
    
     ![Lync Server 2013 のアップグレード オプションを含む右クリック メニューのスクリーン ショット。](../media/7d5b25b1-e5c0-474c-a024-a5ba33f1b3a1.png)
  
2. <span data-ttu-id="be924-144">トポロジ ビルダーで、[アクションの公開 **]**  >  **トポロジまたは [アクション\*\*\*\*トポロジの公開]**  >  **を**  >  **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="be924-144">In Topology Builder, click **Action** > **Publish topology** or **Action** > **Topology** > **Publish**.</span></span> 
    
     ![トポロジ ビルダーの [トポロジの公開] オプションが表示された [操作] メニューのスクリーン ショット。](../media/d6712634-9205-401f-a0b0-3ea096ca51bf.png)
  
3. <span data-ttu-id="be924-146">発行時に、アーカイブストアと監視ストアにデータベースをインストールします。</span><span class="sxs-lookup"><span data-stu-id="be924-146">During publishing, choose to install a database on the Archiving and Monitoring store.</span></span>
    
#### <a name="option-2-upgrade-front-end-pool-without-upgrading-archiving-and-monitoring-stores"></a><span data-ttu-id="be924-147">オプション 2: アーカイブ ストアと監視ストアをアップグレードせずにフロントエンド プールをアップグレードする</span><span class="sxs-lookup"><span data-stu-id="be924-147">Option 2: Upgrade Front End pool without upgrading Archiving and Monitoring stores</span></span>

<span data-ttu-id="be924-148">次の手順を使用すると、選択したプールのアーカイブと監視が無効になります。</span><span class="sxs-lookup"><span data-stu-id="be924-148">If you use the following steps, archiving and monitoring for the selected pool are disabled.</span></span> <span data-ttu-id="be924-149">アップグレード後、プールにはアーカイブ ストアと監視ストアは含めらなされます。</span><span class="sxs-lookup"><span data-stu-id="be924-149">The pool will not have Archiving and Monitoring stores after the upgrade.</span></span>
  
1. <span data-ttu-id="be924-150">トポロジ ビルダーで、アップグレードする Lync Server 2013 プールを選択します。</span><span class="sxs-lookup"><span data-stu-id="be924-150">In Topology Builder, select the Lync Server 2013 pool that you want to upgrade.</span></span>
    
2. <span data-ttu-id="be924-151">Lync Server 2013 のアーカイブ ストアと監視ストアへの依存関係を削除します。</span><span class="sxs-lookup"><span data-stu-id="be924-151">Remove the dependency to the Lync Server 2013 Archiving and Monitoring stores.</span></span> 
    
   - <span data-ttu-id="be924-152">[アクションの編集 **]**  >  **プロパティに移動します**。</span><span class="sxs-lookup"><span data-stu-id="be924-152">Go to **Action** > **Edit properties**.</span></span>
    
   - <span data-ttu-id="be924-153">[アーカイブ **] チェック ボックスを** オフにします。</span><span class="sxs-lookup"><span data-stu-id="be924-153">Clear the **Archiving** check box.</span></span>
    
     ![[プロパティの編集] ダイアログ ボックスの [アーカイブ] チェック ボックスのスクリーン ショット。](../media/9a88427e-80ee-49d0-a767-809fa9a5faf1.png)
  
   - <span data-ttu-id="be924-155">[監視] **チェック ボックス** をオフにします。</span><span class="sxs-lookup"><span data-stu-id="be924-155">Clear the **Monitoring** check box.</span></span>
    
     ![[監視] チェック ボックスを表示する [プロパティの編集] ダイアログのスクリーン ショット。](../media/880acf33-57bb-4521-8717-cf5b67261ed4.png)
  
3. <span data-ttu-id="be924-157">Lync Server 2013 プールを右クリックし **、[Skype for Business Server 2015** へのアップグレード] を選択して、手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="be924-157">Right-click the Lync Server 2013 pool, select **Upgrade to Skype for Business Server 2015**, and follow the steps.</span></span> 
    
     ![Lync Server 2013 のアップグレード オプションを含む右クリック メニューのスクリーン ショット。](../media/7d5b25b1-e5c0-474c-a024-a5ba33f1b3a1.png)
  
4. <span data-ttu-id="be924-159">トポロジ ビルダーで、[アクションの公開 **]**  >  **トポロジまたは [アクション\*\*\*\*トポロジの公開]**  >  **を**  >  **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="be924-159">In Topology Builder, click **Action** > **Publish topology** or **Action** > **Topology** > **Publish**.</span></span> 
    
#### <a name="option-3-upgrade-front-end-pool-and-associated-it-to-new-skype-for-business-server-2015-archiving-and-monitoring-stores"></a><span data-ttu-id="be924-160">オプション 3: フロント エンド プールをアップグレードし、それを新しい Skype for Business Server 2015 のアーカイブおよび監視ストアに関連付にする</span><span class="sxs-lookup"><span data-stu-id="be924-160">Option 3: Upgrade Front End pool and associated it to new Skype for Business Server 2015 Archiving and Monitoring stores</span></span>

<span data-ttu-id="be924-161">次の手順を実行すると、アーカイブと監視は前のストアで停止し、作成した新しいストアで開始されます。</span><span class="sxs-lookup"><span data-stu-id="be924-161">If you use the following steps, archiving and monitoring will stop in the previous store and start in the new store you've created.</span></span> 
  
1. <span data-ttu-id="be924-162">トポロジ ビルダーで、アップグレードする Lync Server 2013 プールを選択します。</span><span class="sxs-lookup"><span data-stu-id="be924-162">In Topology Builder, select the Lync Server 2013 pool that you want to upgrade.</span></span> 
    
2. <span data-ttu-id="be924-163">Lync Server 2013 のアーカイブ ストアと監視ストアへの依存関係を削除します。</span><span class="sxs-lookup"><span data-stu-id="be924-163">Remove the dependency to the Lync Server 2013 Archiving and Monitoring stores.</span></span> 
    
   - <span data-ttu-id="be924-164">[アクションの編集 **]**  >  **プロパティに移動します**。</span><span class="sxs-lookup"><span data-stu-id="be924-164">Go to **Action** > **Edit properties**.</span></span>
    
   - <span data-ttu-id="be924-165">[アーカイブ **] チェック ボックスを** オフにします。</span><span class="sxs-lookup"><span data-stu-id="be924-165">Clear the **Archiving** check box.</span></span>
    
     ![[プロパティの編集] ダイアログ ボックスの [アーカイブ] チェック ボックスのスクリーン ショット。](../media/9a88427e-80ee-49d0-a767-809fa9a5faf1.png)
  
   - <span data-ttu-id="be924-167">[監視] **チェック ボックス** をオフにします。</span><span class="sxs-lookup"><span data-stu-id="be924-167">Clear the **Monitoring** check box.</span></span>
    
     ![[監視] チェック ボックスを表示する [プロパティの編集] ダイアログのスクリーン ショット。](../media/880acf33-57bb-4521-8717-cf5b67261ed4.png)
  
3. <span data-ttu-id="be924-169">Lync Server 2013 プールを右クリックし **、[Skype for Business Server 2015** へのアップグレード] を選択して、手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="be924-169">Right-click the Lync Server 2013 pool, select **Upgrade to Skype for Business Server 2015**, and follow the steps.</span></span> 
    
     ![Lync Server 2013 のアップグレード オプションを含む右クリック メニューのスクリーン ショット。](../media/7d5b25b1-e5c0-474c-a024-a5ba33f1b3a1.png)
  
4. <span data-ttu-id="be924-171">アーカイブ用の新SQLストアを作成します。</span><span class="sxs-lookup"><span data-stu-id="be924-171">Create a new SQL store for Archiving.</span></span> 
    
   - <span data-ttu-id="be924-172">プールとアクション編集の **プロパティ**  >  **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="be924-172">Select the pool and **Action** > **Edit properties**.</span></span> 
    
   -  <span data-ttu-id="be924-173">[アーカイブ **] チェック ボックスを** オンにします。</span><span class="sxs-lookup"><span data-stu-id="be924-173">Select the **Archiving** check box.</span></span>
    
   - <span data-ttu-id="be924-174">**[新規作成]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="be924-174">Click **New**.</span></span>
    
     ![[アーカイブ] セクションの [新規] ボタンを表示する [プロパティの編集] ダイアログのスクリーン ショット。](../media/3a4a18e7-8251-4736-837c-2b486f64f896.png)
  
5. <span data-ttu-id="be924-176">監視用の新SQLストアを作成します。</span><span class="sxs-lookup"><span data-stu-id="be924-176">Create a new SQL store for Monitoring.</span></span> 
    
   - <span data-ttu-id="be924-177">プールとアクション編集の **プロパティ**  >  **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="be924-177">Select the pool and **Action** > **Edit properties**.</span></span> 
    
   -  <span data-ttu-id="be924-178">[監視] **チェック ボックス** をオンにします。</span><span class="sxs-lookup"><span data-stu-id="be924-178">Select the **Monitoring** check box.</span></span>
    
   - <span data-ttu-id="be924-179">**[新規作成]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="be924-179">Click **New**.</span></span>
    
     ![[監視] セクションの下に [新規] ボタンが表示される [プロパティの編集] ダイアログのスクリーン ショット。](../media/729c72a7-0068-4e0d-99dc-e480a6bfbf1d.png)
  
6. <span data-ttu-id="be924-181">トポロジ ビルダーで、[アクションの公開 **]**  >  **トポロジまたは [アクション\*\*\*\*トポロジの公開]**  >  **を**  >  **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="be924-181">In Topology Builder, click **Action** > **Publish topology** or **Action** > **Topology** > **Publish**.</span></span> 
    
7. <span data-ttu-id="be924-182">発行時に、新しいアーカイブおよび監視ストアにデータベースをインストールします。</span><span class="sxs-lookup"><span data-stu-id="be924-182">During publishing, choose to install the database on the new Archiving and Monitoring store.</span></span>
    
### <a name="step-3-wait-for-replication"></a><span data-ttu-id="be924-183">手順 3: レプリケーションを待つ</span><span class="sxs-lookup"><span data-stu-id="be924-183">Step 3: Wait for replication</span></span>

<span data-ttu-id="be924-184">更新されたトポロジを環境内のすべてのサーバーに公開するために、レプリケーションに時間を与えます。</span><span class="sxs-lookup"><span data-stu-id="be924-184">Give replication some time to publish the updated topology to all the servers in the environment.</span></span>
  
### <a name="step-4-stop-all-services-in-pool-to-be-upgraded"></a><span data-ttu-id="be924-185">手順 4: アップグレードするプール内のすべてのサービスを停止する</span><span class="sxs-lookup"><span data-stu-id="be924-185">Step 4: Stop all services in pool to be upgraded</span></span>

<span data-ttu-id="be924-186">アップグレードするプールを提供している各サーバーで、PowerShell で次のコマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="be924-186">On each server that is servicing the pool that you're going to upgrade, run the following cmdlet in PowerShell:</span></span>
  
```powershell
Disable-CsComputer -Scorch
```

<span data-ttu-id="be924-187">アップグレード プロセスのDisable-CsComputerサーバーの再起動が必要になる場合がある場合は、このIn-Place使用することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="be924-187">We recommend using Disable-CsComputer because you may need to reboot the server during the In-Place Upgrade process.</span></span> <span data-ttu-id="be924-188">Stop-CsWindowsService を使用すると、再起動後に一部のサービスが自動的に再起動される場合があります。</span><span class="sxs-lookup"><span data-stu-id="be924-188">If you use Stop-CsWindowsService, some services may restart automatically after a reboot.</span></span> <span data-ttu-id="be924-189">この場合、アップグレードIn-Place失敗する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="be924-189">This may cause the In-Place Upgrade to fail.</span></span>
  
### <a name="step-5-upgrade-front-end-pools-and-non-front-end-pool-servers"></a><span data-ttu-id="be924-190">手順 5: フロントエンド プールとフロントエンド 以外のプール サーバーをアップグレードする</span><span class="sxs-lookup"><span data-stu-id="be924-190">Step 5: Upgrade Front End pools and non-Front End pool servers</span></span>

> [!NOTE]
>  <span data-ttu-id="be924-191">アップグレードの前に、Skype for Business Server 201 > 5 に必要なすべての新しい前提条件をインストールしてください。この前提条件には、アップグレードを試行する前に、32 GB 以上の空き領域が含まれます。</span><span class="sxs-lookup"><span data-stu-id="be924-191">Before upgrading please install all new prerequisites required for Skype for Business Server 2015 which include:>  At least 32GB of free space before attempting an upgrade.</span></span> <span data-ttu-id="be924-192">また、ドライブが固定ローカル ドライブで、USB または Firewire で接続されていないか確認してください。 は NTFS ファイル システムでフォーマットされ、圧縮されません。ページ ファイルは含> PowerShell バージョン 6. 2.9200.0 以降.> 最新の Lync Server 2013 累積更新プログラムがインストールされている。> SQL Server 2012 SP1 がインストールされている。> 次の KB がインストールされている (Microsoft Update を使用している場合は自動的にインストール):> Windows Server 2008 R2 -[KB2533623](https://support.microsoft.com/kb/2533623)> Windows Server 2012 -[KB2858668](https://support.microsoft.com/kb/2858668)> Windows Server 2012 R2 -[KB29820066](https://support.microsoft.com/kb/2982006)</span><span class="sxs-lookup"><span data-stu-id="be924-192">In addition, make sure that the drive is a fixed local drive, is not connected by USB or Firewire, is formatted with NTFS file system, is not compressed, and does not contain a page file.>  PowerShell version 6.2.9200.0 or later.>  The latest Lync Server 2013 Cumulative Update installed.>  SQL Server 2012 SP1 installed.>  The following KB's installed (installed automatically if using Microsoft Update):>  Windows Server 2008 R2 -[KB2533623](https://support.microsoft.com/kb/2533623)>  Windows Server 2012 -[KB2858668](https://support.microsoft.com/kb/2858668)>  Windows Server 2012 R2 -[KB2982006](https://support.microsoft.com/kb/2982006)</span></span>
  
<span data-ttu-id="be924-193">各サーバーIn-Placeアップグレードを使用して、フロントエンド プール、エッジ プール、仲介サーバー、および常設チャット プールを更新します。</span><span class="sxs-lookup"><span data-stu-id="be924-193">Use the In-Place Upgrade on each server to update the Front End pool, Edge pool, Mediation server, and the Persistent Chat pool.</span></span>
  
1. <span data-ttu-id="be924-194">各サーバーで、skype for Business Server 2015 **Setup.exe** メディアで **OCS_Volume\Setup\amd64** からこのコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="be924-194">On each server, run **Setup.exe** from **OCS_Volume\Setup\amd64** on the Skype for Business Server 2015 installation media.</span></span>
    
2. <span data-ttu-id="be924-195">使用許諾契約書に同意し、アップグレードの指示にIn-Placeします。</span><span class="sxs-lookup"><span data-stu-id="be924-195">Accept the license agreement and follow the prompts for the In-Place Upgrade.</span></span>
    
3. <span data-ttu-id="be924-196">フロント エンド プール内の各サーバーと、フロントエンド 以外のプール サーバーごとに、これらの手順を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="be924-196">Repeat these steps for each server in the Front End pool and on each non-Front End pool server.</span></span>
    
> [!NOTE]
> <span data-ttu-id="be924-197">アップグレード中にサーバーを再起動するように求In-Placeがあります。</span><span class="sxs-lookup"><span data-stu-id="be924-197">You might be prompted to reboot the server during the In-Place Upgrade.</span></span> <span data-ttu-id="be924-198">いいですよ。</span><span class="sxs-lookup"><span data-stu-id="be924-198">That's ok.</span></span> <span data-ttu-id="be924-199">再起動後、アップグレードIn-Place、アップグレードがオフにされた場所から続行されます。</span><span class="sxs-lookup"><span data-stu-id="be924-199">After you reboot, the In-Place Upgrade will continue from where it left off.</span></span> 
  
<span data-ttu-id="be924-200">アップグレードIn-Place正常に完了すると、次のメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="be924-200">When the In-Place Upgrade completes successfully, you see the following message.</span></span>
  
![一時アップグレードが正常に完了した場合のスクリーン ショット。](../media/2f52cb50-9bb4-4714-a982-9c7a0865f78a.png)
  
### <a name="step-6-restart-services-on-all-upgraded-servers"></a><span data-ttu-id="be924-202">手順 6: アップグレードされたサーバーすべてでサービスを再起動する</span><span class="sxs-lookup"><span data-stu-id="be924-202">Step 6: Restart services on all upgraded servers</span></span>

> [!NOTE]
> <span data-ttu-id="be924-203">サービスを再起動する前に、%ProgramData%\WindowsFabric がすべてのフロントエンド サーバーに存在しないか確認してください。</span><span class="sxs-lookup"><span data-stu-id="be924-203">Before restarting the services, please make sure %ProgramData%\WindowsFabric doesn't exist on all Front End Servers.</span></span> <span data-ttu-id="be924-204">存在する場合は、サービスを開始する前に削除します。</span><span class="sxs-lookup"><span data-stu-id="be924-204">If it exists, delete it before starting the services.</span></span> 
  
- <span data-ttu-id="be924-205">フロントエンド プール内のすべてのサーバーをアップグレードした後、次の PowerShell コマンドを使用してサービスを再起動します。</span><span class="sxs-lookup"><span data-stu-id="be924-205">After you've upgraded all servers in the Front End pool, restart the services by using the following PowerShell command:</span></span> 
    
  ```powershell
  Start-CsPool
  ```

    > [!NOTE]
    > <span data-ttu-id="be924-206">In-Place Upgrade の実行を開始する前に保留中のシステム再起動が既に必要な場合、In-Place Upgrade はインストールの最後に再起動を求めしません。</span><span class="sxs-lookup"><span data-stu-id="be924-206">If there is already a pending system reboot needed before you start running In-Place Upgrade, then In-Place Upgrade won't ask you to reboot at the end of the installation.</span></span> <span data-ttu-id="be924-207">これにより、Start-CSPool コマンドレットを使用してサービスを開始しようとするときに、最初のフロントエンド サーバーに対してアセンブリ例外がStart-CSPoolされます。</span><span class="sxs-lookup"><span data-stu-id="be924-207">This will cause some assembly exceptions to be thrown against the first Front End server when you try to start services using the Start-CSPool cmdlet.</span></span> <span data-ttu-id="be924-208">これらのエラーを解決するには、プール内のすべてのサーバーを再起動し、コマンドレットを再度実行します。</span><span class="sxs-lookup"><span data-stu-id="be924-208">To resolve these errors, reboot all of the servers in the pool and run the cmdlet again.</span></span> 
  
- <span data-ttu-id="be924-209">フロントエンド プール 以外のサーバーで、次のコマンドを使用してサービスを再起動します。</span><span class="sxs-lookup"><span data-stu-id="be924-209">On the non-Front End pool servers, restart the services by using the following command:</span></span>
    
  ```powershell
  Start-CsWindowsService
  ```

<span data-ttu-id="be924-210">[アップグレード] ページで **[OK]** In-Placeクリックすると、この手順を完了するために次のリマインダーが表示されます。</span><span class="sxs-lookup"><span data-stu-id="be924-210">After you click **OK** on the In-Place Upgrade page, you'll see the following reminder to complete this step.</span></span>
  
![一時アップグレードが正常に完了した後の次の手順を示すスクリーン ショット。](../media/6a7236b6-9ef9-4df3-8682-b0e4021810f9.png)
  
### <a name="step-7-verify-skype-for-business-functionality-works"></a><span data-ttu-id="be924-212">手順 7: Skype for Business の機能が機能することを確認する</span><span class="sxs-lookup"><span data-stu-id="be924-212">Step 7: Verify Skype for Business functionality works</span></span>

<span data-ttu-id="be924-213">アップグレードが成功した場合は、アップグレードされたプールで Skype for Business をテストし、機能が期待通り動作しているのを確認します。</span><span class="sxs-lookup"><span data-stu-id="be924-213">To make sure the upgrade was successful, for the pool that was upgraded, test Skype for Business to make sure the functionality is working as expected.</span></span> 
  
### <a name="step-8-upgrade-secondary-pools"></a><span data-ttu-id="be924-214">手順 8: セカンダリ プールをアップグレードする</span><span class="sxs-lookup"><span data-stu-id="be924-214">Step 8: Upgrade secondary pools</span></span>

<span data-ttu-id="be924-215">環境内に追加のプールがある場合は、このトピックの手順を繰り返してアップグレードします。</span><span class="sxs-lookup"><span data-stu-id="be924-215">Repeat the steps in this topic to upgrade any additional pools that you have in your environment.</span></span>
  
## <a name="troubleshoot-issues-with-the-in-place-upgrade"></a><span data-ttu-id="be924-216">アップグレードに関する問題In-Placeトラブルシューティングを行う</span><span class="sxs-lookup"><span data-stu-id="be924-216">Troubleshoot issues with the In-Place Upgrade</span></span>

<span data-ttu-id="be924-217">アップグレードがIn-Place、次の図のようなメッセージが表示されることがあります。</span><span class="sxs-lookup"><span data-stu-id="be924-217">If the In-Place Upgrade fails, you might see a message similar to what's in the following image.</span></span> 
  
![必要な累積的な更新プログラムがインストールされていない場合の一時アップグレードの失敗を示すスクリーン ショット。](../media/f84db06b-0841-45a9-870d-7ba4b5a463d5.png)
  
<span data-ttu-id="be924-219">ページの下部にある完全なメッセージを確認して、問題のトラブルシューティングに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="be924-219">Review the full message at the bottom of the page to help you troubleshoot the issue.</span></span> <span data-ttu-id="be924-220">[ログ **の表示] をクリック** して詳細を表示します。</span><span class="sxs-lookup"><span data-stu-id="be924-220">Click **View logs** to get more detail.</span></span>
  
<span data-ttu-id="be924-221">アップグレードの準備の確認または不足している前提条件のインストールで In-Placeアップグレードが失敗した場合は、サーバーに最新の Windows Server、Lync Server、および SQL Server の更新プログラムが適用され、必要なすべてのソフトウェアと役割がインストールされていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="be924-221">If the In-Place Upgrade fails on **Verifying upgrade readiness** or **Installing missing prerequisites**, make sure the server has all the latest Windows Server, Lync Server, and SQL Server updates applied, and all the required software and roles are installed.</span></span> <span data-ttu-id="be924-222">必要な機能の一覧については[、「Skype for Business Server 2015 のサーバー要件」および「Skype for Business Server 2015](../plan-your-deployment/requirements-for-your-environment/server-requirements.md)の前提条件のインストール」を参照してください。 [](install/install-prerequisites.md)</span><span class="sxs-lookup"><span data-stu-id="be924-222">For a list of what's required, see [Server requirements for Skype for Business Server 2015](../plan-your-deployment/requirements-for-your-environment/server-requirements.md) and [Install prerequisites for Skype for Business Server 2015](install/install-prerequisites.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="be924-223">関連項目</span><span class="sxs-lookup"><span data-stu-id="be924-223">See also</span></span>

[<span data-ttu-id="be924-224">Skype for Business Server 2015 へのアップグレードを計画する</span><span class="sxs-lookup"><span data-stu-id="be924-224">Plan to upgrade to Skype for Business Server 2015</span></span>](../plan-your-deployment/upgrade.md)
  
[<span data-ttu-id="be924-225">Skype for Business Server 2015 のサーバー要件</span><span class="sxs-lookup"><span data-stu-id="be924-225">Server requirements for Skype for Business Server 2015</span></span>](../plan-your-deployment/requirements-for-your-environment/server-requirements.md)
  
[<span data-ttu-id="be924-226">Skype for Business Server 2015 の前提条件のインストール</span><span class="sxs-lookup"><span data-stu-id="be924-226">Install prerequisites for Skype for Business Server 2015</span></span>](install/install-prerequisites.md)
  
[<span data-ttu-id="be924-227">Skype for Business Server 2015 のインストール</span><span class="sxs-lookup"><span data-stu-id="be924-227">Install Skype for Business Server 2015</span></span>](install/install.md)
