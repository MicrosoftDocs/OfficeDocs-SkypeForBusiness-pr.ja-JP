---
title: 応答グループの移行
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: ユーザーが Skype for Business Server 2019 プールに移動された後、応答グループを移行できます。 応答グループの移行には、エージェントグループ、キュー、ワークフロー、オーディオファイル、および、従来の展開から Skype for Business Server 2019 プールへの応答グループの連絡先オブジェクトの移動が含まれます。 従来の応答グループを移行すると、応答グループへの通話は、Skype for Business Server 2019 プールの応答グループアプリケーションによって処理されます。 応答グループへの通話は、従来のプールでは処理されなくなりました。
ms.openlocfilehash: 9e7605daf92646e5bb53626eeed2371888bf9cb1
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2020
ms.locfileid: "41813465"
---
# <a name="migrate-response-groups"></a><span data-ttu-id="b8435-106">応答グループの移行</span><span class="sxs-lookup"><span data-stu-id="b8435-106">Migrate response groups</span></span>

<span data-ttu-id="b8435-107">ユーザーが Skype for Business Server 2019 プールに移動された後、応答グループを移行できます。</span><span class="sxs-lookup"><span data-stu-id="b8435-107">After your users are moved to Skype for Business Server 2019 pools, you can migrate your response groups.</span></span> <span data-ttu-id="b8435-108">応答グループの移行には、エージェントグループ、キュー、ワークフロー、オーディオファイル、および、従来の展開から Skype for Business Server 2019 プールへの応答グループの連絡先オブジェクトの移動が含まれます。</span><span class="sxs-lookup"><span data-stu-id="b8435-108">Migrating response groups includes copying agent groups, queues, workflows, audio files, and moving Response Group contact objects from the legacy deployment to the Skype for Business Server 2019 pool.</span></span> <span data-ttu-id="b8435-109">従来の応答グループを移行すると、応答グループへの通話は、Skype for Business Server 2019 プールの応答グループアプリケーションによって処理されます。</span><span class="sxs-lookup"><span data-stu-id="b8435-109">After you migrate your legacy response groups, calls to the response groups are handled by the Response Group application in the Skype for Business Server 2019 pool.</span></span> <span data-ttu-id="b8435-110">応答グループへの通話は、従来のプールでは処理されなくなりました。</span><span class="sxs-lookup"><span data-stu-id="b8435-110">Calls to response groups are no longer handled by the legacy pool.</span></span>
  
> [!NOTE]
> <span data-ttu-id="b8435-111">すべてのユーザーを Skype for Business Server 2019 プールに移動する前に、応答グループを移行することはできますが、すべてのユーザーを最初に移動することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="b8435-111">Although you can migrate response groups before you move all users to the Skype for Business Server 2019 pool, we recommend that you move all users first.</span></span> <span data-ttu-id="b8435-112">特に、応答グループのエージェントであるユーザーは、Skype for Business Server 2019 プールに移動するまで、新機能のすべての機能を利用できません。</span><span class="sxs-lookup"><span data-stu-id="b8435-112">In particular, users who are response group agents will not have full functionality of new features until they are moved to the Skype for Business Server 2019 pool.</span></span> 
  
<span data-ttu-id="b8435-113">応答グループを移行する前に、応答グループアプリケーションが含まれている Skype for Business Server 2019 プールを展開しておく必要があります。</span><span class="sxs-lookup"><span data-stu-id="b8435-113">Before you migrate response groups, you must have deployed a Skype for Business Server 2019 pool that includes the Response Group application.</span></span> <span data-ttu-id="b8435-114">応答グループアプリケーションは、エンタープライズボイスの展開時に既定でインストールされ、有効になります。</span><span class="sxs-lookup"><span data-stu-id="b8435-114">The Response Group application is installed and activated by default when you deploy Enterprise Voice.</span></span> <span data-ttu-id="b8435-115">**ApplicationServer**コマンドレットを実行して、応答グループアプリケーションがインストールされていることを確認できます。</span><span class="sxs-lookup"><span data-stu-id="b8435-115">You can ensure that the Response Group application is installed by running the **Get-CsService -ApplicationServer** cmdlet.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="b8435-116">従来の応答グループを移行する前に、Skype for business Server 2019 プールで新しい Skype for Business Server 2019 応答グループを作成することができます。</span><span class="sxs-lookup"><span data-stu-id="b8435-116">You can create new Skype for Business Server 2019 response groups in the Skype for Business Server 2019 pool before you migrate your legacy response groups.</span></span> 
  
<span data-ttu-id="b8435-117">従来のプールから Skype for Business Server 2019 に応答グループを移行するには、 **Move-CsRgsConfiguration**コマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="b8435-117">To migrate response groups from a legacy pool to the Skype for Business Server 2019, you run the **Move-CsRgsConfiguration** cmdlet.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="b8435-118">応答グループの移行コマンドレットは、プール全体の応答グループの構成を移動します。</span><span class="sxs-lookup"><span data-stu-id="b8435-118">The Response Group migration cmdlet moves the Response Group configuration for the entire pool.</span></span> <span data-ttu-id="b8435-119">移行する特定のグループ、キュー、またはワークフローを選ぶことはできません。</span><span class="sxs-lookup"><span data-stu-id="b8435-119">You cannot select specific groups, queues, or workflows to migrate.</span></span> 
  
<span data-ttu-id="b8435-120">応答グループを移行した後、Skype for Business Server コントロールパネルまたは Skype for Business Server Management Shell コマンドレットを使用して、すべてのエージェントグループ、キュー、ワークフローが正常に移動されたことを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b8435-120">After you migrate the response groups, you need to use Skype for Business Server Control Panel or Skype for Business Server Management Shell cmdlets to verify that all agent groups, queues, and workflows moved successfully.</span></span> 
  
<span data-ttu-id="b8435-121">応答グループを移行しても、従来の応答グループは削除されません。</span><span class="sxs-lookup"><span data-stu-id="b8435-121">When you migrate response groups, the legacy response groups are not removed.</span></span> <span data-ttu-id="b8435-122">Skype for Business Server コントロールパネルまたは Skype for Business Server Management Shell を使用して、移行後に応答グループを管理すると、従来の応答グループと Skype for Business Server 2019 応答グループの両方を表示できます。</span><span class="sxs-lookup"><span data-stu-id="b8435-122">When you manage response groups after migration by using either Skype for Business Server Control Panel or Skype for Business Server Management Shell, you can see both the legacy response groups and the Skype for Business Server 2019 response groups.</span></span> <span data-ttu-id="b8435-123">更新プログラムは、Skype for Business Server 2019 応答グループにのみ適用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b8435-123">You should apply updates only to the Skype for Business Server 2019 response groups.</span></span> <span data-ttu-id="b8435-124">従来の応答グループは、ロールバック目的でのみ保持されます。</span><span class="sxs-lookup"><span data-stu-id="b8435-124">The legacy response groups are retained only for rollback purposes.</span></span> 
  
> [!CAUTION]
> <span data-ttu-id="b8435-125">移行が完了し、新しい応答グループが作成された後、Skype for Business Server コントロールパネルと Skype for business server の管理シェルでは、各回答のレガシおよび Skype for business Server 2019 バージョンが表示されます。化.</span><span class="sxs-lookup"><span data-stu-id="b8435-125">After the migration has been completed and the new response groups have been created, the Skype for Business Server Control Panel and the Skype for Business Server Management Shell will display the legacy and Skype for Business Server 2019 versions of each response group.</span></span> <span data-ttu-id="b8435-126">Skype for Business Server コントロールパネルまたは Skype for Business Server 管理シェルを使って、従来の応答グループを削除しないでください。</span><span class="sxs-lookup"><span data-stu-id="b8435-126">Do not use Skype for Business Server Control Panel or Skype for Business Server Management Shell to remove the legacy response groups.</span></span> <span data-ttu-id="b8435-127">いずれかを削除すると、移行中に作成された対応する応答グループは動作を停止します。</span><span class="sxs-lookup"><span data-stu-id="b8435-127">If you do remove one, the corresponding response group that was created during migration will stop working.</span></span> <span data-ttu-id="b8435-128">従来の応答グループは、レガシープールの使用を停止すると削除されます。</span><span class="sxs-lookup"><span data-stu-id="b8435-128">The legacy response groups will be removed when you decommission the legacy pool.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="b8435-129">プールを廃止するまでは、前の展開からデータを削除しないことをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="b8435-129">We recommend that you do not remove any data from your previous deployment until you decommission the pool.</span></span> <span data-ttu-id="b8435-130">また、移行した後すぐに応答グループをエクスポートすることを強くお勧めします。</span><span class="sxs-lookup"><span data-stu-id="b8435-130">In addition, we strongly recommend that you export response groups immediately after you migrate.</span></span> <span data-ttu-id="b8435-131">従来の応答グループを削除する必要がある場合は、バックアップから応答グループを復元して、Skype for Business Server 2019 応答グループをもう一度実行することができます。</span><span class="sxs-lookup"><span data-stu-id="b8435-131">If a legacy response group should get removed, you can then restore your response groups from the backup to get Skype for Business Server 2019 response groups running again.</span></span> 
  
<span data-ttu-id="b8435-132">Skype for Business Server 2019 では、**ワークフローの種類**と呼ばれる新しい返信グループ機能が導入されています。</span><span class="sxs-lookup"><span data-stu-id="b8435-132">Skype for Business Server 2019 introduces a new Response Group feature called **Workflow Type**.</span></span> <span data-ttu-id="b8435-133">**ワークフローの種類**は、**管理**または**非**管理を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="b8435-133">**Workflow Type** can be **Managed** or **Unmanaged**.</span></span> <span data-ttu-id="b8435-134">すべての応答グループは、**ワークフローの種類**が [**非管理**] に設定され、[管理者] リストが空の状態で移行されます。</span><span class="sxs-lookup"><span data-stu-id="b8435-134">All response groups are migrated with **Workflow Type** set to **Unmanaged** and with an empty Manager list.</span></span> 
  
<span data-ttu-id="b8435-135">**移動-CsRgsConfiguration**コマンドレットを実行しても、ロールバックのために、エージェントグループ、キュー、ワークフロー、オーディオファイルは従来のプールに残ります。</span><span class="sxs-lookup"><span data-stu-id="b8435-135">When you run the **Move-CsRgsConfiguration** cmdlet, the agent groups, queues, workflows, and audio files remain in the legacy pool for rollback purposes.</span></span> <span data-ttu-id="b8435-136">ただし、従来のプールにロールバックする必要がある場合は、 **Move-CsApplicationEndpoint**コマンドレットを実行して、連絡先オブジェクトを従来のプールに戻す必要があります。</span><span class="sxs-lookup"><span data-stu-id="b8435-136">If you do need to roll back to the legacy pool, however, you need to run the **Move-CsApplicationEndpoint** cmdlet to move contact objects back to the legacy pool.</span></span> 
  
<span data-ttu-id="b8435-137">回答グループの構成を移行するための次の手順では、従来のプールと Skype for Business Server 2019 プールの間に1対1のリレーションシップがあることを前提としています。</span><span class="sxs-lookup"><span data-stu-id="b8435-137">The following procedure for migrating Response Group configurations assumes that you have a one-to-one relationship between your legacy pools and the Skype for Business Server 2019 pools.</span></span> <span data-ttu-id="b8435-138">移行および展開中にプールを統合または分割する場合は、どのレガシプールが Skype for Business Server 2019 プールにマップされるかを計画する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b8435-138">If you plan to consolidate or split up pools during your migration and deployment, you need to plan which legacy pool maps to which Skype for Business Server 2019 pool.</span></span>
  
## <a name="to-migrate-response-group-configurations"></a><span data-ttu-id="b8435-139">応答グループの構成を移行するには</span><span class="sxs-lookup"><span data-stu-id="b8435-139">To migrate Response Group configurations</span></span>

1. <span data-ttu-id="b8435-140">RTCUniversalServerAdmins グループのメンバーであるアカウントか、同等の管理者権限と権限を持つアカウントでコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="b8435-140">Log on to the computer with an account that is a member of the RTCUniversalServerAdmins group or has equivalent administrator rights and permissions.</span></span>
    
2. <span data-ttu-id="b8435-141">Skype for Business Server 管理シェルを開始します。 [**スタート**] をクリックし、[**すべてのプログラム**]、[ **Microsoft skype for business Server 2019**]、[ **skype for business server 管理シェル**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="b8435-141">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Skype for Business Server 2019**, and then click **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="b8435-142">次のコマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="b8435-142">Run:</span></span>
    
   ```PowerShell
   Move-CsRgsConfiguration -Source <source pool FQDN> -Destination <destination pool FQDN>
   ```

    <span data-ttu-id="b8435-143">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="b8435-143">For example:</span></span>
    
   ```PowerShell
   Move-CsRgsConfiguration -Source skype-old.contoso.net -Destination skype-new.contoso.net
   ```

4. <span data-ttu-id="b8435-144">応答グループとエージェントを Skype for Business Server 2019 プールに移行した後、サインインとサインアウトのためにエージェントで使用される URL は、Skype for Business Server 2019 URL であり、[**ツール**] メニューから使用できます。</span><span class="sxs-lookup"><span data-stu-id="b8435-144">After you migrate response groups and agents to the Skype for Business Server 2019 pool, the URL that agents use to sign in and sign out is a Skype for Business Server 2019 URL and is available from the **Tools** menu.</span></span> <span data-ttu-id="b8435-145">ブックマークなどの参照を新しい URL に更新するようにエージェントに通知します。</span><span class="sxs-lookup"><span data-stu-id="b8435-145">Remind agents to update any references, such as bookmarks, to the new URL.</span></span> 
    
## <a name="to-verify-response-group-migration-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="b8435-146">Skype for Business Server コントロールパネルを使用して応答グループの移行を確認するには</span><span class="sxs-lookup"><span data-stu-id="b8435-146">To verify Response Group migration by using Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="b8435-147">RTCUniversalReadOnlyAdmins group のメンバーであるアカウント、または CsViewOnlyAdministrator の役割のメンバーであるアカウントでコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="b8435-147">Log on to the computer with an account that is a member of RTCUniversalReadOnlyAdmins group or is minimally a member of the CsViewOnlyAdministrator role.</span></span>
    
2. <span data-ttu-id="b8435-148">ブラウザーウィンドウを開き、管理 URL を入力して、Skype for Business Server コントロールパネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="b8435-148">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> <span data-ttu-id="b8435-149">Skype for business Server コントロールパネルを起動するために使用できるさまざまな方法について詳しくは、「 [skype For Business server 2019 管理ツールを開く](https://technet.microsoft.com/en-us/library/gg195741(v=ocs.15).aspx)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="b8435-149">For details about the different methods you can use to start Skype for Business Server Control Panel, see [Open Skype for Business Server 2019 administrative tools](https://technet.microsoft.com/en-us/library/gg195741(v=ocs.15).aspx).</span></span> 
    <!-- The above link points to un-rebranded 2013 content we will need to discuss rebrand or bring forward -->
3. <span data-ttu-id="b8435-150">左側のナビゲーションウィンドウで、[**応答グループ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b8435-150">In the left navigation pane, click **Response Groups**.</span></span>
    
4. <span data-ttu-id="b8435-151">[**ワークフロー** ] タブで、従来の環境のすべてのワークフローが一覧に含まれていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="b8435-151">On the **Workflow** tab, verify that all the workflows in your legacy environment are included in the list.</span></span> 
    
5. <span data-ttu-id="b8435-152">[**キュー** ] タブをクリックして、従来の環境のすべてのキューがリストに含まれていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="b8435-152">Click the **Queue** tab, and verify that all the queues in your legacy environment are included in the list.</span></span> 
    
6. <span data-ttu-id="b8435-153">[**グループ**] タブをクリックして、従来の環境のすべてのエージェントグループがリストに含まれていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="b8435-153">Click the **Group** tab, and verify that all the agent groups in your legacy environment are included in the list.</span></span> 
    
## <a name="to-verify-response-group-migration-by-using-skype-for-business-server-management-shell"></a><span data-ttu-id="b8435-154">Skype for Business Server 管理シェルを使用して応答グループの移行を確認するには</span><span class="sxs-lookup"><span data-stu-id="b8435-154">To verify Response Group migration by using Skype for Business Server Management Shell</span></span>

1. <span data-ttu-id="b8435-155">RTCUniversalReadOnlyAdmins group のメンバーであるアカウント、または CsViewOnlyAdministrator の役割のメンバーであるアカウントでコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="b8435-155">Log on to the computer with an account that is a member of RTCUniversalReadOnlyAdmins group or is minimally a member of the CsViewOnlyAdministrator role.</span></span>
    
2. <span data-ttu-id="b8435-156">Skype for Business Server 管理シェルを開始します。 [**スタート**] をクリックし、[**すべてのプログラム**]、[ **Microsoft skype for business Server 2019**]、[ **skype for business server 管理シェル**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="b8435-156">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Skype for Business Server 2019**, and then click **Skype for Business Server Management Shell**.</span></span>
    
    <span data-ttu-id="b8435-157">次のコマンドレットの詳細については、次を実行します。</span><span class="sxs-lookup"><span data-stu-id="b8435-157">For details about the following cmdlets, run:</span></span>
    
   ```PowerShell
   Get-Help <cmdlet name> -Detailed
   ```

3. <span data-ttu-id="b8435-158">次のコマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="b8435-158">Run:</span></span>
    
   ```PowerShell
   Get-CsRgsAgentGroup
   ```

4. <span data-ttu-id="b8435-159">従来の環境のすべてのエージェントグループがリストに含まれていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="b8435-159">Verify that all the agent groups in your legacy environment are included in the list.</span></span>
    
5. <span data-ttu-id="b8435-160">次のコマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="b8435-160">Run:</span></span>
    
   ```PowerShell
   Get-CsRgsQueue
   ```

6. <span data-ttu-id="b8435-161">従来の環境のすべてのキューがリストに含まれていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="b8435-161">Verify that all the queues in your legacy environment are included in the list.</span></span>
    
7. <span data-ttu-id="b8435-162">次のコマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="b8435-162">Run:</span></span>
    
   ```PowerShell
   Get-CsRgsWorkflow
   ```

8. <span data-ttu-id="b8435-163">従来の環境のすべてのワークフローがリストに含まれていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="b8435-163">Verify that all the workflows in your legacy environment are included in the list.</span></span>
    

