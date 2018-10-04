---
title: 応答グループを移行します。
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: ビジネス サーバー 2019 プールのユーザーを移動した後 Skype は、応答グループを移行できます。 移行する応答グループには、エージェント グループ、キュー、ワークフロー、オーディオのファイルをコピーし、ビジネス サーバー 2019 プールの Skype にレガシー環境からの応答のグループの連絡先オブジェクトを移動が含まれています。 従来の応答グループを移行した後、応答グループへの呼び出しは、プールのビジネス サーバー 2019 Skype で応答グループ アプリケーションによって処理されます。 応答グループへの呼び出しは、不要になったレガシ プールによって処理されます。
ms.openlocfilehash: 89149210e8041fbc84834cec83e1c1fe13d0765c
ms.sourcegitcommit: dd37c12a0312270955755ab2826adcfbae813790
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/04/2018
ms.locfileid: "25372938"
---
# <a name="migrate-response-groups"></a><span data-ttu-id="36ba8-106">応答グループを移行します。</span><span class="sxs-lookup"><span data-stu-id="36ba8-106">Migrate response groups</span></span>

<span data-ttu-id="36ba8-107">ビジネス サーバー 2019 プールのユーザーを移動した後 Skype は、応答グループを移行できます。</span><span class="sxs-lookup"><span data-stu-id="36ba8-107">After your users are moved to Skype for Business Server 2019 pools, you can migrate your response groups.</span></span> <span data-ttu-id="36ba8-108">移行する応答グループには、エージェント グループ、キュー、ワークフロー、オーディオのファイルをコピーし、ビジネス サーバー 2019 プールの Skype にレガシー環境からの応答のグループの連絡先オブジェクトを移動が含まれています。</span><span class="sxs-lookup"><span data-stu-id="36ba8-108">Migrating response groups includes copying agent groups, queues, workflows, audio files, and moving Response Group contact objects from the legacy deployment to the Skype for Business Server 2019 pool.</span></span> <span data-ttu-id="36ba8-109">従来の応答グループを移行した後、応答グループへの呼び出しは、プールのビジネス サーバー 2019 Skype で応答グループ アプリケーションによって処理されます。</span><span class="sxs-lookup"><span data-stu-id="36ba8-109">After you migrate your legacy response groups, calls to the response groups are handled by the Response Group application in the Skype for Business Server 2019 pool.</span></span> <span data-ttu-id="36ba8-110">応答グループへの呼び出しは、不要になったレガシ プールによって処理されます。</span><span class="sxs-lookup"><span data-stu-id="36ba8-110">Calls to response groups are no longer handled by the legacy pool.</span></span>
  
> [!NOTE]
> <span data-ttu-id="36ba8-111">応答グループを移行するには、すべてのユーザーを Skype のビジネス サーバー 2019 プールに移動する前に、まずすべてのユーザーを移動することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="36ba8-111">Although you can migrate response groups before you move all users to the Skype for Business Server 2019 pool, we recommend that you move all users first.</span></span> <span data-ttu-id="36ba8-112">具体的には、ビジネス サーバー 2019 プールのため、Skype に移動されるまで、応答グループのエージェントであるユーザーには新機能の完全な機能はありません。</span><span class="sxs-lookup"><span data-stu-id="36ba8-112">In particular, users who are response group agents will not have full functionality of new features until they are moved to the Skype for Business Server 2019 pool.</span></span> 
  
<span data-ttu-id="36ba8-113">応答グループを移行する前に、応答グループ アプリケーションが含まれていますビジネス サーバー 2019 プールのため、Skype を導入している必要があります。</span><span class="sxs-lookup"><span data-stu-id="36ba8-113">Before you migrate response groups, you must have deployed a Skype for Business Server 2019 pool that includes the Response Group application.</span></span> <span data-ttu-id="36ba8-114">応答グループ アプリケーションがインストールされ、エンタープライズ VoIP を展開するときに既定でアクティブにします。</span><span class="sxs-lookup"><span data-stu-id="36ba8-114">The Response Group application is installed and activated by default when you deploy Enterprise Voice.</span></span> <span data-ttu-id="36ba8-115">**アプリケーション サーバーの取得 CsService**コマンドレットを実行して応答グループ アプリケーションがインストールされていることを確認できます。</span><span class="sxs-lookup"><span data-stu-id="36ba8-115">You can ensure that the Response Group application is installed by running the **Get-CsService -ApplicationServer** cmdlet.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="36ba8-116">従来の応答グループを移行する前に、ビジネス サーバー 2019 プールの Skype のビジネス サーバー 2019 応答グループに対する新しい Skype を作成できます。</span><span class="sxs-lookup"><span data-stu-id="36ba8-116">You can create new Skype for Business Server 2019 response groups in the Skype for Business Server 2019 pool before you migrate your legacy response groups.</span></span> 
  
<span data-ttu-id="36ba8-117">従来のプールから応答グループを移行ビジネス サーバー 2019、Skype をするには、**移動 CsRgsConfiguration**コマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="36ba8-117">To migrate response groups from a legacy pool to the Skype for Business Server 2019, you run the **Move-CsRgsConfiguration** cmdlet.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="36ba8-118">応答グループの移行コマンドレットは、プール全体の応答グループの構成を移動します。</span><span class="sxs-lookup"><span data-stu-id="36ba8-118">The Response Group migration cmdlet moves the Response Group configuration for the entire pool.</span></span> <span data-ttu-id="36ba8-119">移行するには、特定のグループ、キュー、またはワークフローを選択することはできません。</span><span class="sxs-lookup"><span data-stu-id="36ba8-119">You cannot select specific groups, queues, or workflows to migrate.</span></span> 
  
<span data-ttu-id="36ba8-120">応答グループを移行した後は、すべてのエージェント グループ、キュー、およびワークフローが正常に移動することを確認するのには、ビジネス サーバー管理シェル コマンドレットのビジネス サーバーのコントロール パネルまたは Skype の Skype を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="36ba8-120">After you migrate the response groups, you need to use Skype for Business Server Control Panel or Skype for Business Server Management Shell cmdlets to verify that all agent groups, queues, and workflows moved successfully.</span></span> 
  
<span data-ttu-id="36ba8-121">応答グループを移行する場合は、従来の応答グループは削除されません。</span><span class="sxs-lookup"><span data-stu-id="36ba8-121">When you migrate response groups, the legacy response groups are not removed.</span></span> <span data-ttu-id="36ba8-122">ビジネス サーバーのコントロール パネルまたは Skype のビジネス サーバー管理シェルのいずれかの Skype を使用して、移行後の応答のグループを管理するときは、従来の応答グループとビジネス サーバー 2019 応答グループの Skype の両方を表示できます。</span><span class="sxs-lookup"><span data-stu-id="36ba8-122">When you manage response groups after migration by using either Skype for Business Server Control Panel or Skype for Business Server Management Shell, you can see both the legacy response groups and the Skype for Business Server 2019 response groups.</span></span> <span data-ttu-id="36ba8-123">ビジネス サーバー 2019 応答グループの Skype にのみ更新プログラムを適用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="36ba8-123">You should apply updates only to the Skype for Business Server 2019 response groups.</span></span> <span data-ttu-id="36ba8-124">従来の応答グループは、ロールバックの目的でのみ保持されます。</span><span class="sxs-lookup"><span data-stu-id="36ba8-124">The legacy response groups are retained only for rollback purposes.</span></span> 
  
> [!CAUTION]
> <span data-ttu-id="36ba8-125">ビジネス サーバーのコントロール パネルの Skype とビジネスのサーバー管理シェルの Skype が表示されます、レガシ移行が完了し、新しい応答グループが作成されて、および各応答のビジネス サーバー 2019 バージョンの Skypeグループです。</span><span class="sxs-lookup"><span data-stu-id="36ba8-125">After the migration has been completed and the new response groups have been created, the Skype for Business Server Control Panel and the Skype for Business Server Management Shell will display the legacy and Skype for Business Server 2019 versions of each response group.</span></span> <span data-ttu-id="36ba8-126">従来の応答グループを削除するのにはビジネス サーバーのコントロール パネルまたはビジネス サーバー管理シェルの Skype の Skype を使用しません。</span><span class="sxs-lookup"><span data-stu-id="36ba8-126">Do not use Skype for Business Server Control Panel or Skype for Business Server Management Shell to remove the legacy response groups.</span></span> <span data-ttu-id="36ba8-127">いずれかを削除して、移行中に作成された対応する応答グループは、作業を停止します。</span><span class="sxs-lookup"><span data-stu-id="36ba8-127">If you do remove one, the corresponding response group that was created during migration will stop working.</span></span> <span data-ttu-id="36ba8-128">従来の応答グループは、従来のプールを停止すると、削除されます。</span><span class="sxs-lookup"><span data-stu-id="36ba8-128">The legacy response groups will be removed when you decommission the legacy pool.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="36ba8-129">するまで削除しないデータ、以前の展開からプールの使用を停止することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="36ba8-129">We recommend that you do not remove any data from your previous deployment until you decommission the pool.</span></span> <span data-ttu-id="36ba8-130">さらに、移行した後にすぐに応答グループをエクスポートすることを強くお勧めします。</span><span class="sxs-lookup"><span data-stu-id="36ba8-130">In addition, we strongly recommend that you export response groups immediately after you migrate.</span></span> <span data-ttu-id="36ba8-131">従来の応答グループを削除取得する場合、ビジネス サーバー 2019 応答のグループを再度実行するための Skype へのバックアップから、応答グループを復元できます。</span><span class="sxs-lookup"><span data-stu-id="36ba8-131">If a legacy response group should get removed, you can then restore your response groups from the backup to get Skype for Business Server 2019 response groups running again.</span></span> 
  
<span data-ttu-id="36ba8-132">ビジネス サーバー 2019 の Skype では、**ワークフローの型**と呼ばれる新しい応答グループの機能について説明します。</span><span class="sxs-lookup"><span data-stu-id="36ba8-132">Skype for Business Server 2019 introduces a new Response Group feature called **Workflow Type**.</span></span> <span data-ttu-id="36ba8-133">**ワークフローの種類**には、**管理**または**非管理**ができます。</span><span class="sxs-lookup"><span data-stu-id="36ba8-133">**Workflow Type** can be **Managed** or **Unmanaged**.</span></span> <span data-ttu-id="36ba8-134">応答のすべてのグループは、**ワークフローの種類**が設定**されていない**と、空のマネージャーのリストに移行されます。</span><span class="sxs-lookup"><span data-stu-id="36ba8-134">All response groups are migrated with **Workflow Type** set to **Unmanaged** and with an empty Manager list.</span></span> 
  
<span data-ttu-id="36ba8-135">**移動 CsRgsConfiguration**コマンドレットを実行すると、エージェント グループ、キュー、ワークフロー、およびオーディオ ファイルがロールバックのために従来のプールに残っています。</span><span class="sxs-lookup"><span data-stu-id="36ba8-135">When you run the **Move-CsRgsConfiguration** cmdlet, the agent groups, queues, workflows, and audio files remain in the legacy pool for rollback purposes.</span></span> <span data-ttu-id="36ba8-136">従来のプールをロールバックする必要がある場合は、連絡先オブジェクトを既存のプールに移動する**移動 CsApplicationEndpoint**コマンドレットを実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="36ba8-136">If you do need to roll back to the legacy pool, however, you need to run the **Move-CsApplicationEndpoint** cmdlet to move contact objects back to the legacy pool.</span></span> 
  
<span data-ttu-id="36ba8-137">応答グループ構成を移行するには、次の手順では、レガシ プールとビジネス サーバー 2019 プールの Skype との間の一対一リレーションシップがあることを前提としています。</span><span class="sxs-lookup"><span data-stu-id="36ba8-137">The following procedure for migrating Response Group configurations assumes that you have a one-to-one relationship between your legacy pools and the Skype for Business Server 2019 pools.</span></span> <span data-ttu-id="36ba8-138">統合または移行、展開中にプールを分割する場合は、レガシ プールにマップする Skype をビジネス サーバー 2019 プールの計画をする必要があります。</span><span class="sxs-lookup"><span data-stu-id="36ba8-138">If you plan to consolidate or split up pools during your migration and deployment, you need to plan which legacy pool maps to which Skype for Business Server 2019 pool.</span></span>
  
## <a name="to-migrate-response-group-configurations"></a><span data-ttu-id="36ba8-139">応答グループの構成を移行するには</span><span class="sxs-lookup"><span data-stu-id="36ba8-139">To migrate Response Group configurations</span></span>

1. <span data-ttu-id="36ba8-140">RTCUniversalServerAdmins グループのメンバーであるか、同等の管理者権限とアクセス許可を持つアカウントでコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="36ba8-140">Log on to the computer with an account that is a member of the RTCUniversalServerAdmins group or has equivalent administrator rights and permissions.</span></span>
    
2. <span data-ttu-id="36ba8-141">ビジネス サーバー管理シェルには、Skype を起動する: [**スタート**] ボタン、[**すべてのプログラム**] をクリックして、**ビジネス サーバー 2019 の Skype をマイクロソフト**をクリック**ビジネス サーバー管理シェルの Skype**です。</span><span class="sxs-lookup"><span data-stu-id="36ba8-141">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Skype for Business Server 2019**, and then click **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="36ba8-142">次のコマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="36ba8-142">Run:</span></span>
    
   ```
   Move-CsRgsConfiguration -Source <source pool FQDN> -Destination <destination pool FQDN>
   ```

    <span data-ttu-id="36ba8-143">例:</span><span class="sxs-lookup"><span data-stu-id="36ba8-143">For example:</span></span>
    
   ```
   Move-CsRgsConfiguration -Source skype-old.contoso.net -Destination skype-new.contoso.net
   ```

4. <span data-ttu-id="36ba8-144">ビジネス サーバー 2019 プールの Skype に応答グループとエージェントを移行した後、エージェントに使用する URL には、サインインし、サインアウトを Skype ビジネス サーバー 2019 の URL の **[ツール**] メニューから利用できます。</span><span class="sxs-lookup"><span data-stu-id="36ba8-144">After you migrate response groups and agents to the Skype for Business Server 2019 pool, the URL that agents use to sign in and sign out is a Skype for Business Server 2019 URL and is available from the **Tools** menu.</span></span> <span data-ttu-id="36ba8-145">エージェントが新しい URL にブックマークなどのすべての参照を更新することを指摘します。</span><span class="sxs-lookup"><span data-stu-id="36ba8-145">Remind agents to update any references, such as bookmarks, to the new URL.</span></span> 
    
## <a name="to-verify-response-group-migration-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="36ba8-146">ビジネス サーバーのコントロール パネルの Skype を使用して応答グループの移行を確認するには</span><span class="sxs-lookup"><span data-stu-id="36ba8-146">To verify Response Group migration by using Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="36ba8-147">RTCUniversalReadOnlyAdmins グループのメンバーであるか、CsViewOnlyAdministrator ロールのメンバーは、最低限を持つアカウントでコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="36ba8-147">Log on to the computer with an account that is a member of RTCUniversalReadOnlyAdmins group or is minimally a member of the CsViewOnlyAdministrator role.</span></span>
    
2. <span data-ttu-id="36ba8-148">、ブラウザー ウィンドウを開き、を開くには、Skype ビジネス サーバーのコントロール パネルの管理 URL を入力します。</span><span class="sxs-lookup"><span data-stu-id="36ba8-148">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> <span data-ttu-id="36ba8-149">ビジネス サーバーのコントロール パネルの Skype を起動することができますを使用するさまざまな方法についての詳細は、[管理ツールのビジネス サーバー 2019 の Skype を開く](https://technet.microsoft.com/en-us/library/gg195741(v=ocs.15).aspx)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="36ba8-149">For details about the different methods you can use to start Skype for Business Server Control Panel, see [Open Skype for Business Server 2019 administrative tools](https://technet.microsoft.com/en-us/library/gg195741(v=ocs.15).aspx).</span></span> 
    <!-- The above link points to un-rebranded 2013 content we will need to discuss rebrand or bring forward -->
3. <span data-ttu-id="36ba8-150">左側のナビゲーション ウィンドウでは、**応答グループ**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="36ba8-150">In the left navigation pane, click **Response Groups**.</span></span>
    
4. <span data-ttu-id="36ba8-151">[**ワークフロー** ] タブで、レガシ環境でのすべてのワークフローがリストに含まれていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="36ba8-151">On the **Workflow** tab, verify that all the workflows in your legacy environment are included in the list.</span></span> 
    
5. <span data-ttu-id="36ba8-152">[**キュー** ] タブをクリックし、レガシ環境でのすべてのキューが一覧に含まれていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="36ba8-152">Click the **Queue** tab, and verify that all the queues in your legacy environment are included in the list.</span></span> 
    
6. <span data-ttu-id="36ba8-153">[**グループ**] タブをクリックし、レガシ環境でのすべてのエージェント グループが一覧に含まれていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="36ba8-153">Click the **Group** tab, and verify that all the agent groups in your legacy environment are included in the list.</span></span> 
    
## <a name="to-verify-response-group-migration-by-using-skype-for-business-server-management-shell"></a><span data-ttu-id="36ba8-154">Skype ビジネス サーバー管理シェルを使用して応答グループの移行を確認するには</span><span class="sxs-lookup"><span data-stu-id="36ba8-154">To verify Response Group migration by using Skype for Business Server Management Shell</span></span>

1. <span data-ttu-id="36ba8-155">RTCUniversalReadOnlyAdmins グループのメンバーであるか、CsViewOnlyAdministrator ロールのメンバーは、最低限を持つアカウントでコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="36ba8-155">Log on to the computer with an account that is a member of RTCUniversalReadOnlyAdmins group or is minimally a member of the CsViewOnlyAdministrator role.</span></span>
    
2. <span data-ttu-id="36ba8-156">ビジネス サーバー管理シェルには、Skype を起動する: [**スタート**] ボタン、[**すべてのプログラム**] をクリックして、**ビジネス サーバー 2019 の Skype をマイクロソフト**をクリック**ビジネス サーバー管理シェルの Skype**です。</span><span class="sxs-lookup"><span data-stu-id="36ba8-156">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Skype for Business Server 2019**, and then click **Skype for Business Server Management Shell**.</span></span>
    
    <span data-ttu-id="36ba8-157">次のコマンドレットの詳細については、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="36ba8-157">For details about the following cmdlets, run:</span></span>
    
   ```
   Get-Help <cmdlet name> -Detailed
   ```

3. <span data-ttu-id="36ba8-158">次のコマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="36ba8-158">Run:</span></span>
    
   ```
   Get-CsRgsAgentGroup
   ```

4. <span data-ttu-id="36ba8-159">レガシ環境でのすべてのエージェント グループが一覧に含まれていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="36ba8-159">Verify that all the agent groups in your legacy environment are included in the list.</span></span>
    
5. <span data-ttu-id="36ba8-160">次のコマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="36ba8-160">Run:</span></span>
    
   ```
   Get-CsRgsQueue
   ```

6. <span data-ttu-id="36ba8-161">レガシ環境でのすべてのキューが一覧に含まれていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="36ba8-161">Verify that all the queues in your legacy environment are included in the list.</span></span>
    
7. <span data-ttu-id="36ba8-162">次のコマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="36ba8-162">Run:</span></span>
    
   ```
   Get-CsRgsWorkflow
   ```

8. <span data-ttu-id="36ba8-163">レガシ環境でのすべてのワークフローがリストに含まれていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="36ba8-163">Verify that all the workflows in your legacy environment are included in the list.</span></span>
    

