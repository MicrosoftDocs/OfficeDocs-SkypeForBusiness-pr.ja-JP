---
title: 応答グループを移行する
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: ユーザーが Skype for Business Server 2019 プールに移動された後、応答グループを移行できます。 応答グループの移行には、エージェントグループ、キュー、ワークフロー、オーディオファイルをコピーし、応答グループの連絡先オブジェクトを従来の展開から Skype for Business Server 2019 プールに移動することが含まれます。 従来の応答グループを移行した後、応答グループへの通話は、Skype for Business Server 2019 プールの応答グループアプリケーションによって処理されます。 応答グループへの通話は、従来のプールによって処理されなくなりました。
ms.openlocfilehash: 03b0ffd900b5d7c23dd6ff680d56c0c4db53d8dc
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/16/2020
ms.locfileid: "44752679"
---
# <a name="migrate-response-groups"></a><span data-ttu-id="b9871-106">応答グループを移行する</span><span class="sxs-lookup"><span data-stu-id="b9871-106">Migrate response groups</span></span>

<span data-ttu-id="b9871-107">ユーザーが Skype for Business Server 2019 プールに移動された後、応答グループを移行できます。</span><span class="sxs-lookup"><span data-stu-id="b9871-107">After your users are moved to Skype for Business Server 2019 pools, you can migrate your response groups.</span></span> <span data-ttu-id="b9871-108">応答グループの移行には、エージェントグループ、キュー、ワークフロー、オーディオファイルをコピーし、応答グループの連絡先オブジェクトを従来の展開から Skype for Business Server 2019 プールに移動することが含まれます。</span><span class="sxs-lookup"><span data-stu-id="b9871-108">Migrating response groups includes copying agent groups, queues, workflows, audio files, and moving Response Group contact objects from the legacy deployment to the Skype for Business Server 2019 pool.</span></span> <span data-ttu-id="b9871-109">従来の応答グループを移行した後、応答グループへの通話は、Skype for Business Server 2019 プールの応答グループアプリケーションによって処理されます。</span><span class="sxs-lookup"><span data-stu-id="b9871-109">After you migrate your legacy response groups, calls to the response groups are handled by the Response Group application in the Skype for Business Server 2019 pool.</span></span> <span data-ttu-id="b9871-110">応答グループへの通話は、従来のプールによって処理されなくなりました。</span><span class="sxs-lookup"><span data-stu-id="b9871-110">Calls to response groups are no longer handled by the legacy pool.</span></span>
  
> [!NOTE]
> <span data-ttu-id="b9871-111">すべてのユーザーを Skype for Business Server 2019 プールに移動する前に、応答グループを移行することもできますが、すべてのユーザーを最初に移動することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="b9871-111">Although you can migrate response groups before you move all users to the Skype for Business Server 2019 pool, we recommend that you move all users first.</span></span> <span data-ttu-id="b9871-112">特に、応答グループのエージェントであるユーザーは、Skype for Business Server 2019 プールに移動するまで、新機能のすべての機能を利用できません。</span><span class="sxs-lookup"><span data-stu-id="b9871-112">In particular, users who are response group agents will not have full functionality of new features until they are moved to the Skype for Business Server 2019 pool.</span></span> 
  
<span data-ttu-id="b9871-113">応答グループを移行する前に、応答グループアプリケーションを含む Skype for Business Server 2019 プールを展開しておく必要があります。</span><span class="sxs-lookup"><span data-stu-id="b9871-113">Before you migrate response groups, you must have deployed a Skype for Business Server 2019 pool that includes the Response Group application.</span></span> <span data-ttu-id="b9871-114">応答グループアプリケーションは、エンタープライズ Voip を展開するときに既定でインストールされ、アクティブ化されます。</span><span class="sxs-lookup"><span data-stu-id="b9871-114">The Response Group application is installed and activated by default when you deploy Enterprise Voice.</span></span> <span data-ttu-id="b9871-115">**ApplicationServer**コマンドレットを実行して、応答グループアプリケーションがインストールされていることを確認できます。</span><span class="sxs-lookup"><span data-stu-id="b9871-115">You can ensure that the Response Group application is installed by running the **Get-CsService -ApplicationServer** cmdlet.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="b9871-116">従来の応答グループを移行する前に、Skype for Business Server 2019 プールで新しい Skype for Business Server 2019 応答グループを作成することができます。</span><span class="sxs-lookup"><span data-stu-id="b9871-116">You can create new Skype for Business Server 2019 response groups in the Skype for Business Server 2019 pool before you migrate your legacy response groups.</span></span> 
  
<span data-ttu-id="b9871-117">応答グループを従来のプールから Skype for Business Server 2019 に移行するには、 **Move-CsRgsConfiguration**コマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="b9871-117">To migrate response groups from a legacy pool to the Skype for Business Server 2019, you run the **Move-CsRgsConfiguration** cmdlet.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="b9871-118">応答グループ移行コマンドレットは、プール全体の応答グループの構成を移動します。</span><span class="sxs-lookup"><span data-stu-id="b9871-118">The Response Group migration cmdlet moves the Response Group configuration for the entire pool.</span></span> <span data-ttu-id="b9871-119">特定のグループ、キュー、またはワークフローを選択して移行することはできません。</span><span class="sxs-lookup"><span data-stu-id="b9871-119">You cannot select specific groups, queues, or workflows to migrate.</span></span> 
  
<span data-ttu-id="b9871-120">応答グループを移行したら、Skype for Business Server コントロールパネルまたは Skype for Business Server 管理シェルコマンドレットを使用して、すべてのエージェントグループ、キュー、およびワークフローが正常に移動されたことを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b9871-120">After you migrate the response groups, you need to use Skype for Business Server Control Panel or Skype for Business Server Management Shell cmdlets to verify that all agent groups, queues, and workflows moved successfully.</span></span> 
  
<span data-ttu-id="b9871-121">応答グループを移行する場合、従来の応答グループは削除されません。</span><span class="sxs-lookup"><span data-stu-id="b9871-121">When you migrate response groups, the legacy response groups are not removed.</span></span> <span data-ttu-id="b9871-122">Skype for Business Server コントロールパネルまたは Skype for Business Server 管理シェルのいずれかを使用して移行後に応答グループを管理すると、従来の応答グループと Skype for Business Server 2019 応答グループの両方を表示することができます。</span><span class="sxs-lookup"><span data-stu-id="b9871-122">When you manage response groups after migration by using either Skype for Business Server Control Panel or Skype for Business Server Management Shell, you can see both the legacy response groups and the Skype for Business Server 2019 response groups.</span></span> <span data-ttu-id="b9871-123">更新プログラムは、Skype for Business Server 2019 応答グループにのみ適用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b9871-123">You should apply updates only to the Skype for Business Server 2019 response groups.</span></span> <span data-ttu-id="b9871-124">従来の応答グループは、ロールバックの目的でのみ保持されます。</span><span class="sxs-lookup"><span data-stu-id="b9871-124">The legacy response groups are retained only for rollback purposes.</span></span> 
  
> [!CAUTION]
> <span data-ttu-id="b9871-125">移行が完了し、新しい応答グループが作成されたら、Skype for Business Server コントロールパネルと Skype for Business Server 管理シェルによって、各応答グループのレガシおよび Skype for business Server 2019 のバージョンが表示されます。</span><span class="sxs-lookup"><span data-stu-id="b9871-125">After the migration has been completed and the new response groups have been created, the Skype for Business Server Control Panel and the Skype for Business Server Management Shell will display the legacy and Skype for Business Server 2019 versions of each response group.</span></span> <span data-ttu-id="b9871-126">従来の応答グループを削除するには、Skype for Business Server コントロールパネルまたは Skype for business Server 管理シェルを使用しないでください。</span><span class="sxs-lookup"><span data-stu-id="b9871-126">Do not use Skype for Business Server Control Panel or Skype for Business Server Management Shell to remove the legacy response groups.</span></span> <span data-ttu-id="b9871-127">いずれかを削除すると、移行中に作成された対応する応答グループは動作を停止します。</span><span class="sxs-lookup"><span data-stu-id="b9871-127">If you do remove one, the corresponding response group that was created during migration will stop working.</span></span> <span data-ttu-id="b9871-128">従来の応答グループは、従来のプールを使用停止にしたときに削除されます。</span><span class="sxs-lookup"><span data-stu-id="b9871-128">The legacy response groups will be removed when you decommission the legacy pool.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="b9871-129">プールの使用を停止するまで、以前の展開からデータを削除しないようにすることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="b9871-129">We recommend that you do not remove any data from your previous deployment until you decommission the pool.</span></span> <span data-ttu-id="b9871-130">また、移行直後に応答グループをエクスポートすることを強くお勧めします。</span><span class="sxs-lookup"><span data-stu-id="b9871-130">In addition, we strongly recommend that you export response groups immediately after you migrate.</span></span> <span data-ttu-id="b9871-131">従来の応答グループを削除する必要がある場合は、バックアップから応答グループを復元して、Skype for Business Server 2019 応答グループを再度実行することができます。</span><span class="sxs-lookup"><span data-stu-id="b9871-131">If a legacy response group should get removed, you can then restore your response groups from the backup to get Skype for Business Server 2019 response groups running again.</span></span> 
  
<span data-ttu-id="b9871-132">Skype for Business Server 2019 には、**ワークフローの種類**と呼ばれる新しい応答グループ機能が導入されています。</span><span class="sxs-lookup"><span data-stu-id="b9871-132">Skype for Business Server 2019 introduces a new Response Group feature called **Workflow Type**.</span></span> <span data-ttu-id="b9871-133">[**ワークフローの種類**] は、[**管理**] または [**管理されていない**] に設定できます。</span><span class="sxs-lookup"><span data-stu-id="b9871-133">**Workflow Type** can be **Managed** or **Unmanaged**.</span></span> <span data-ttu-id="b9871-134">すべての応答グループは、[**ワークフローの種類**] が [**管理されていない**] に設定され、マネージャーの一覧が空の状態で移行されます。</span><span class="sxs-lookup"><span data-stu-id="b9871-134">All response groups are migrated with **Workflow Type** set to **Unmanaged** and with an empty Manager list.</span></span> 
  
<span data-ttu-id="b9871-135">**Move-CsRgsConfiguration** コマンドレットを実行した場合、エージェント グループ、キュー、ワークフロー、およびオーディオ ファイルは、ロールバックできるようにレガシ プールに残されたままとなります。</span><span class="sxs-lookup"><span data-stu-id="b9871-135">When you run the **Move-CsRgsConfiguration** cmdlet, the agent groups, queues, workflows, and audio files remain in the legacy pool for rollback purposes.</span></span> <span data-ttu-id="b9871-136">ただし、レガシ プールへのロールバックが必要な場合に連絡先オブジェクトを移動してレガシ プールに戻すには、**Move-CsApplicationEndpoint** コマンドレットを実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b9871-136">If you do need to roll back to the legacy pool, however, you need to run the **Move-CsApplicationEndpoint** cmdlet to move contact objects back to the legacy pool.</span></span> 
  
<span data-ttu-id="b9871-137">応答グループ構成を移行するための次の手順では、従来のプールと Skype for Business Server 2019 プールとの間に1対1の関係があることを前提としています。</span><span class="sxs-lookup"><span data-stu-id="b9871-137">The following procedure for migrating Response Group configurations assumes that you have a one-to-one relationship between your legacy pools and the Skype for Business Server 2019 pools.</span></span> <span data-ttu-id="b9871-138">移行と展開時にプールを統合または分割する予定の場合は、どの従来のプールをどの Skype for Business Server 2019 プールにマッピングするかを計画する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b9871-138">If you plan to consolidate or split up pools during your migration and deployment, you need to plan which legacy pool maps to which Skype for Business Server 2019 pool.</span></span>
  
## <a name="to-migrate-response-group-configurations"></a><span data-ttu-id="b9871-139">応答グループの構成を移行するには</span><span class="sxs-lookup"><span data-stu-id="b9871-139">To migrate Response Group configurations</span></span>

1. <span data-ttu-id="b9871-140">RTCUniversalServerAdmins グループのメンバーであるアカウント、またはそれと同等の管理者権限およびアクセス許可を持つアカウントを使用して、コンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="b9871-140">Log on to the computer with an account that is a member of the RTCUniversalServerAdmins group or has equivalent administrator rights and permissions.</span></span>
    
2. <span data-ttu-id="b9871-141">Skype for Business Server 管理シェルを起動します。 [**スタート**]、[**すべてのプログラム**]、[ **Microsoft Skype for business Server 2019**]、[ **skype for business server 管理シェル**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="b9871-141">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Skype for Business Server 2019**, and then click **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="b9871-142">実行</span><span class="sxs-lookup"><span data-stu-id="b9871-142">Run:</span></span>
    
   ```PowerShell
   Move-CsRgsConfiguration -Source <source pool FQDN> -Destination <destination pool FQDN>
   ```

    <span data-ttu-id="b9871-143">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="b9871-143">For example:</span></span>
    
   ```PowerShell
   Move-CsRgsConfiguration -Source skype-old.contoso.net -Destination skype-new.contoso.net
   ```

4. <span data-ttu-id="b9871-144">応答グループとエージェントを Skype for Business Server 2019 プールに移行すると、エージェントがサインインおよびサインアウトする際に使用する URL が Skype for Business Server 2019 の URL になり、[**ツール**] メニューから利用できるようになります。</span><span class="sxs-lookup"><span data-stu-id="b9871-144">After you migrate response groups and agents to the Skype for Business Server 2019 pool, the URL that agents use to sign in and sign out is a Skype for Business Server 2019 URL and is available from the **Tools** menu.</span></span> <span data-ttu-id="b9871-145">ブックマークなどの参照を、新しい URL に更新するようにエージェントに知らせてください。</span><span class="sxs-lookup"><span data-stu-id="b9871-145">Remind agents to update any references, such as bookmarks, to the new URL.</span></span> 
    
## <a name="to-verify-response-group-migration-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="b9871-146">Skype for Business Server コントロールパネルを使用して応答グループの移行を確認するには</span><span class="sxs-lookup"><span data-stu-id="b9871-146">To verify Response Group migration by using Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="b9871-147">RTCUniversalReadOnlyAdmins グループのメンバーまたは少なくとも CsViewOnlyAdministrator 役割のメンバーであるアカウントを使用して、コンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="b9871-147">Log on to the computer with an account that is a member of RTCUniversalReadOnlyAdmins group or is minimally a member of the CsViewOnlyAdministrator role.</span></span>
    
2. <span data-ttu-id="b9871-148">ブラウザーウィンドウを開き、管理 URL を入力して Skype for Business Server コントロールパネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="b9871-148">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> <span data-ttu-id="b9871-149">Skype for business Server コントロールパネルの起動に使用できるさまざまな方法の詳細については、「 [skype For Business server 2019 管理ツールを開く](https://technet.microsoft.com/library/gg195741(v=ocs.15).aspx)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b9871-149">For details about the different methods you can use to start Skype for Business Server Control Panel, see [Open Skype for Business Server 2019 administrative tools](https://technet.microsoft.com/library/gg195741(v=ocs.15).aspx).</span></span> 
    <!-- The above link points to un-rebranded 2013 content we will need to discuss rebrand or bring forward -->
3. <span data-ttu-id="b9871-150">左側のナビゲーション ウィンドウで [**応答グループ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b9871-150">In the left navigation pane, click **Response Groups**.</span></span>
    
4. <span data-ttu-id="b9871-151">[**ワークフロー** ] タブで、従来の環境のすべてのワークフローがリストに含まれていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="b9871-151">On the **Workflow** tab, verify that all the workflows in your legacy environment are included in the list.</span></span> 
    
5. <span data-ttu-id="b9871-152">[**キュー** ] タブをクリックし、従来の環境のすべてのキューがリストに含まれていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="b9871-152">Click the **Queue** tab, and verify that all the queues in your legacy environment are included in the list.</span></span> 
    
6. <span data-ttu-id="b9871-153">[**グループ**] タブをクリックし、従来の環境のすべてのエージェントグループがリストに含まれていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="b9871-153">Click the **Group** tab, and verify that all the agent groups in your legacy environment are included in the list.</span></span> 
    
## <a name="to-verify-response-group-migration-by-using-skype-for-business-server-management-shell"></a><span data-ttu-id="b9871-154">Skype for Business Server 管理シェルを使用して応答グループの移行を確認するには</span><span class="sxs-lookup"><span data-stu-id="b9871-154">To verify Response Group migration by using Skype for Business Server Management Shell</span></span>

1. <span data-ttu-id="b9871-155">RTCUniversalReadOnlyAdmins グループのメンバーまたは少なくとも CsViewOnlyAdministrator 役割のメンバーであるアカウントを使用して、コンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="b9871-155">Log on to the computer with an account that is a member of RTCUniversalReadOnlyAdmins group or is minimally a member of the CsViewOnlyAdministrator role.</span></span>
    
2. <span data-ttu-id="b9871-156">Skype for Business Server 管理シェルを起動します。 [**スタート**]、[**すべてのプログラム**]、[ **Microsoft Skype for business Server 2019**]、[ **skype for business server 管理シェル**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="b9871-156">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Skype for Business Server 2019**, and then click **Skype for Business Server Management Shell**.</span></span>
    
    <span data-ttu-id="b9871-157">各コマンドレットの詳細については、次のように実行してください。</span><span class="sxs-lookup"><span data-stu-id="b9871-157">For details about the following cmdlets, run:</span></span>
    
   ```PowerShell
   Get-Help <cmdlet name> -Detailed
   ```

3. <span data-ttu-id="b9871-158">実行</span><span class="sxs-lookup"><span data-stu-id="b9871-158">Run:</span></span>
    
   ```PowerShell
   Get-CsRgsAgentGroup
   ```

4. <span data-ttu-id="b9871-159">従来の環境のすべてのエージェントグループがリストに含まれていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="b9871-159">Verify that all the agent groups in your legacy environment are included in the list.</span></span>
    
5. <span data-ttu-id="b9871-160">実行</span><span class="sxs-lookup"><span data-stu-id="b9871-160">Run:</span></span>
    
   ```PowerShell
   Get-CsRgsQueue
   ```

6. <span data-ttu-id="b9871-161">従来の環境のすべてのキューがリストに含まれていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="b9871-161">Verify that all the queues in your legacy environment are included in the list.</span></span>
    
7. <span data-ttu-id="b9871-162">実行</span><span class="sxs-lookup"><span data-stu-id="b9871-162">Run:</span></span>
    
   ```PowerShell
   Get-CsRgsWorkflow
   ```

8. <span data-ttu-id="b9871-163">従来の環境のすべてのワークフローがリストに含まれていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="b9871-163">Verify that all the workflows in your legacy environment are included in the list.</span></span>
    

