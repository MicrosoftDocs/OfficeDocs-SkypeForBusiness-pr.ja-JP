---
title: 応答グループの移行
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Migrate response groups
ms:assetid: 43741ae7-c871-4573-b660-f2f5febc0856
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204854(v=OCS.15)
ms:contentKeyID: 48184020
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 60a5bb2b2124b84adeb6a494f6f33ce867f7d416
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34848070"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="migrate-response-groups"></a><span data-ttu-id="15ccd-102">応答グループの移行</span><span class="sxs-lookup"><span data-stu-id="15ccd-102">Migrate response groups</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="15ccd-103">_**最終更新日:** 2013-09-23_</span><span class="sxs-lookup"><span data-stu-id="15ccd-103">_**Topic Last Modified:** 2013-09-23_</span></span>

<span data-ttu-id="15ccd-104">ユーザーが Lync Server 2013 プールに移動された後、応答グループを移行できます。</span><span class="sxs-lookup"><span data-stu-id="15ccd-104">After your users are moved to Lync Server 2013 pools, you can migrate your response groups.</span></span> <span data-ttu-id="15ccd-105">応答グループの移行には、エージェントグループ、キュー、ワークフロー、オーディオファイル、および、従来の展開から Lync Server 2013 プールへの応答グループの連絡先オブジェクトの移動が含まれます。</span><span class="sxs-lookup"><span data-stu-id="15ccd-105">Migrating response groups includes copying agent groups, queues, workflows, audio files, and moving Response Group contact objects from the legacy deployment to the Lync Server 2013 pool.</span></span> <span data-ttu-id="15ccd-106">従来の応答グループを移行すると、応答グループへの通話は、Lync Server 2013 プールの応答グループアプリケーションによって処理されます。</span><span class="sxs-lookup"><span data-stu-id="15ccd-106">After you migrate your legacy response groups, calls to the response groups are handled by the Response Group application in the Lync Server 2013 pool.</span></span> <span data-ttu-id="15ccd-107">応答グループへの通話は、従来のプールでは処理されなくなりました。</span><span class="sxs-lookup"><span data-stu-id="15ccd-107">Calls to response groups are no longer handled by the legacy pool.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="15ccd-108">すべてのユーザーを Lync Server 2013 プールに移動する前に、応答グループを移行することもできますが、最初にすべてのユーザーを移動することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="15ccd-108">Although you can migrate response groups before you move all users to the Lync Server 2013 pool, we recommend that you move all users first.</span></span> <span data-ttu-id="15ccd-109">特に、応答グループのエージェントであるユーザーは、Lync Server 2013 プールに移動するまで、新機能のすべての機能を利用できません。</span><span class="sxs-lookup"><span data-stu-id="15ccd-109">In particular, users who are response group agents will not have full functionality of new features until they are moved to the Lync Server 2013 pool.</span></span>



</div>

<span data-ttu-id="15ccd-110">応答グループを移行する前に、応答グループアプリケーションを含む Lync Server 2013 プールを展開しておく必要があります。</span><span class="sxs-lookup"><span data-stu-id="15ccd-110">Before you migrate response groups, you must have deployed a Lync Server 2013 pool that includes the Response Group application.</span></span> <span data-ttu-id="15ccd-111">応答グループアプリケーションは、エンタープライズボイスの展開時に既定でインストールされ、有効になります。</span><span class="sxs-lookup"><span data-stu-id="15ccd-111">The Response Group application is installed and activated by default when you deploy Enterprise Voice.</span></span> <span data-ttu-id="15ccd-112">**ApplicationServer**コマンドレットを実行して、応答グループアプリケーションがインストールされていることを確認できます。</span><span class="sxs-lookup"><span data-stu-id="15ccd-112">You can ensure that the Response Group application is installed by running the **Get-CsService –ApplicationServer** cmdlet.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="15ccd-113">従来の応答グループを移行する前に、Lync Server 2013 プールに新しい Lync Server 2013 応答グループを作成することができます。</span><span class="sxs-lookup"><span data-stu-id="15ccd-113">You can create new Lync Server 2013 response groups in the Lync Server 2013 pool before you migrate your legacy response groups.</span></span>



</div>

<span data-ttu-id="15ccd-114">従来のプールから Lync Server 2013 に応答グループを移行するには、 **Move-CsRgsConfiguration**コマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="15ccd-114">To migrate response groups from a legacy pool to the Lync Server 2013, you run the **Move-CsRgsConfiguration** cmdlet.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="15ccd-115">応答グループの移行コマンドレットは、プール全体の応答グループの構成を移動します。</span><span class="sxs-lookup"><span data-stu-id="15ccd-115">The Response Group migration cmdlet moves the Response Group configuration for the entire pool.</span></span> <span data-ttu-id="15ccd-116">移行する特定のグループ、キュー、またはワークフローを選ぶことはできません。</span><span class="sxs-lookup"><span data-stu-id="15ccd-116">You cannot select specific groups, queues, or workflows to migrate.</span></span>



</div>

<span data-ttu-id="15ccd-117">応答グループを移行した後、Lync Server コントロールパネルまたは Lync Server Management Shell コマンドレットを使用して、すべてのエージェントグループ、キュー、ワークフローが正常に移動されたことを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="15ccd-117">After you migrate the response groups, you need to use Lync Server Control Panel or Lync Server Management Shell cmdlets to verify that all agent groups, queues, and workflows moved successfully.</span></span>

<span data-ttu-id="15ccd-118">応答グループを移行しても、Lync Server 2010 応答グループは削除されません。</span><span class="sxs-lookup"><span data-stu-id="15ccd-118">When you migrate response groups, the Lync Server 2010 response groups are not removed.</span></span> <span data-ttu-id="15ccd-119">Lync Server コントロールパネルまたは Lync Server 管理シェルを使用して、移行後に応答グループを管理すると、Lync Server 2010 応答グループと Lync Server 2013 応答グループの両方を表示できます。</span><span class="sxs-lookup"><span data-stu-id="15ccd-119">When you manage response groups after migration by using either Lync Server Control Panel or Lync Server Management Shell, you can see both the Lync Server 2010 response groups and the Lync Server 2013 response groups.</span></span> <span data-ttu-id="15ccd-120">Lync Server 2013 応答グループにのみ更新プログラムを適用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="15ccd-120">You should apply updates only to the Lync Server 2013 response groups.</span></span> <span data-ttu-id="15ccd-121">Lync Server 2010 応答グループは、ロールバック目的でのみ保持されます。</span><span class="sxs-lookup"><span data-stu-id="15ccd-121">The Lync Server 2010 response groups are retained only for rollback purposes.</span></span>

<div>


> [!WARNING]  
> <span data-ttu-id="15ccd-122">移行が完了し、新しい応答グループが作成されると、Lync Server コントロールパネルと Lync server 管理シェルに、各返信グループの Lync Server 2010 および Lync Server 2013 のバージョンが表示されます。</span><span class="sxs-lookup"><span data-stu-id="15ccd-122">After the migration has been completed and the new response groups have been created, the Lync Server Control Panel and the Lync Server Management Shell will display the Lync Server 2010 and Lync Server 2013 versions of each response group.</span></span> <span data-ttu-id="15ccd-123">Lync server コントロールパネルまたは Lync Server 管理シェルを使用して、Lync Server 2010 応答グループを削除しないでください。</span><span class="sxs-lookup"><span data-stu-id="15ccd-123">Do not use Lync Server Control Panel or Lync Server Management Shell to remove the Lync Server 2010 response groups.</span></span> <span data-ttu-id="15ccd-124">いずれかを削除すると、移行中に作成された対応する応答グループは動作を停止します。</span><span class="sxs-lookup"><span data-stu-id="15ccd-124">If you do remove one, the corresponding response group that was created during migration will stop working.</span></span> <span data-ttu-id="15ccd-125">Lync server 2010 プールの使用を停止すると、Lync Server 2010 応答グループは削除されます。</span><span class="sxs-lookup"><span data-stu-id="15ccd-125">The Lync Server 2010 response groups will be removed when you decommission the Lync Server 2010 pool.</span></span>



</div>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="15ccd-126">プールを廃止するまでは、前の展開からデータを削除しないことをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="15ccd-126">We recommend that you do not remove any data from your previous deployment until you decommission the pool.</span></span> <span data-ttu-id="15ccd-127">また、移行した後すぐに応答グループをエクスポートすることを強くお勧めします。</span><span class="sxs-lookup"><span data-stu-id="15ccd-127">In addition, we strongly recommend that you export response groups immediately after you migrate.</span></span> <span data-ttu-id="15ccd-128">Lync Server 2010 応答グループを削除する必要がある場合は、バックアップから応答グループを復元して、Lync Server 2013 応答グループを再起動することができます。</span><span class="sxs-lookup"><span data-stu-id="15ccd-128">If a Lync Server 2010 response group should get removed, you can then restore your response groups from the backup to get Lync Server 2013 response groups running again.</span></span>



</div>

<span data-ttu-id="15ccd-129">Lync Server 2013 では、**ワークフローの種類**と呼ばれる新しい返信グループ機能が導入されています。</span><span class="sxs-lookup"><span data-stu-id="15ccd-129">Lync Server 2013 introduces a new Response Group feature called **Workflow Type**.</span></span> <span data-ttu-id="15ccd-130">**ワークフローの種類**は、**管理**または**非**管理を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="15ccd-130">**Workflow Type** can be **Managed** or **Unmanaged**.</span></span> <span data-ttu-id="15ccd-131">すべての応答グループは、**ワークフローの種類**が [**非管理**] に設定され、[管理者] リストが空の状態で移行されます。</span><span class="sxs-lookup"><span data-stu-id="15ccd-131">All response groups are migrated with **Workflow Type** set to **Unmanaged** and with an empty Manager list.</span></span>

<span data-ttu-id="15ccd-132">**移動-CsRgsConfiguration**コマンドレットを実行しても、ロールバックのために、エージェントグループ、キュー、ワークフロー、オーディオファイルは従来のプールに残ります。</span><span class="sxs-lookup"><span data-stu-id="15ccd-132">When you run the **Move-CsRgsConfiguration** cmdlet, the agent groups, queues, workflows, and audio files remain in the legacy pool for rollback purposes.</span></span> <span data-ttu-id="15ccd-133">ただし、従来のプールにロールバックする必要がある場合は、 **Move-CsApplicationEndpoint**コマンドレットを実行して、連絡先オブジェクトを従来のプールに戻す必要があります。</span><span class="sxs-lookup"><span data-stu-id="15ccd-133">If you do need to roll back to the legacy pool, however, you need to run the **Move-CsApplicationEndpoint** cmdlet to move contact objects back to the legacy pool.</span></span>

<span data-ttu-id="15ccd-134">回答グループの構成を移行するための次の手順では、従来のプールと Lync Server 2013 プールの間に1対1のリレーションシップがあることを前提としています。</span><span class="sxs-lookup"><span data-stu-id="15ccd-134">The following procedure for migrating Response Group configurations assumes that you have a one-to-one relationship between your legacy pools and the Lync Server 2013 pools.</span></span> <span data-ttu-id="15ccd-135">移行および展開中にプールを統合または分割する場合は、どのレガシプールが Lync Server 2013 プールにマッピングされるかを計画する必要があります。</span><span class="sxs-lookup"><span data-stu-id="15ccd-135">If you plan to consolidate or split up pools during your migration and deployment, you need to plan which legacy pool maps to which Lync Server 2013 pool.</span></span>

<div>

## <a name="to-migrate-response-group-configurations"></a><span data-ttu-id="15ccd-136">応答グループの構成を移行するには</span><span class="sxs-lookup"><span data-stu-id="15ccd-136">To migrate Response Group configurations</span></span>

1.  <span data-ttu-id="15ccd-137">RTCUniversalServerAdmins グループのメンバーであるアカウントか、同等の管理者権限と権限を持つアカウントでコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="15ccd-137">Log on to the computer with an account that is a member of the RTCUniversalServerAdmins group or has equivalent administrator rights and permissions.</span></span>

2.  <span data-ttu-id="15ccd-138">Lync Server 管理シェルを起動します。 [**スタート**] をクリックし、[**すべてのプログラム**]、[ **Microsoft Lync Server 2013**]、[ **lync server 管理シェル**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="15ccd-138">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="15ccd-139">次のコマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="15ccd-139">Run:</span></span>
    
        Move-CsRgsConfiguration -Source <source pool FQDN> -Destination <destination pool FQDN>
    
    <span data-ttu-id="15ccd-140">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="15ccd-140">For example:</span></span>
    
        Move-CsRgsConfiguration -Source lync-old.contoso.net -Destination lync-new.contoso.net

4.  <span data-ttu-id="15ccd-141">応答グループとエージェントを Lync Server 2013 プールに移行した後、サインインとサインアウトに使用するエージェントの URL は Lync Server 2013 URL であり、[**ツール**] メニューから使用できます。</span><span class="sxs-lookup"><span data-stu-id="15ccd-141">After you migrate response groups and agents to the Lync Server 2013 pool, the URL that agents use to sign in and sign out is a Lync Server 2013 URL and is available from the **Tools** menu.</span></span> <span data-ttu-id="15ccd-142">ブックマークなどの参照を新しい URL に更新するようにエージェントに通知します。</span><span class="sxs-lookup"><span data-stu-id="15ccd-142">Remind agents to update any references, such as bookmarks, to the new URL.</span></span>

</div>

<div>

## <a name="to-verify-response-group-migration-by-using-lync-server-control-panel"></a><span data-ttu-id="15ccd-143">Lync Server コントロールパネルを使用して応答グループの移行を確認するには</span><span class="sxs-lookup"><span data-stu-id="15ccd-143">To verify Response Group migration by using Lync Server Control Panel</span></span>

1.  <span data-ttu-id="15ccd-144">RTCUniversalReadOnlyAdmins group のメンバーであるアカウント、または CsViewOnlyAdministrator の役割のメンバーであるアカウントでコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="15ccd-144">Log on to the computer with an account that is a member of RTCUniversalReadOnlyAdmins group or is minimally a member of the CsViewOnlyAdministrator role.</span></span>

2.  <span data-ttu-id="15ccd-145">ブラウザーウィンドウを開き、管理 URL を入力して Lync Server コントロールパネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="15ccd-145">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="15ccd-146">Lync Server コントロールパネルを起動するために使用できるさまざまな方法について詳しくは、「 [Lync server 2013 管理ツールを開く](lync-server-2013-open-lync-server-administrative-tools.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="15ccd-146">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="15ccd-147">左側のナビゲーションウィンドウで、[**応答グループ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="15ccd-147">In the left navigation pane, click **Response Groups**.</span></span>

4.  <span data-ttu-id="15ccd-148">[**ワークフロー** ] タブで、Lync Server 2010 環境内のすべてのワークフローが一覧に含まれていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="15ccd-148">On the **Workflow** tab, verify that all the workflows in your Lync Server 2010 environment are included in the list.</span></span>

5.  <span data-ttu-id="15ccd-149">[**キュー** ] タブをクリックして、Lync Server 2010 環境内のすべてのキューがリストに含まれていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="15ccd-149">Click the **Queue** tab, and verify that all the queues in your Lync Server 2010 environment are included in the list.</span></span>

6.  <span data-ttu-id="15ccd-150">[**グループ**] タブをクリックし、Lync Server 2010 環境内のすべてのエージェントグループがリストに含まれていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="15ccd-150">Click the **Group** tab, and verify that all the agent groups in your Lync Server 2010 environment are included in the list.</span></span>

</div>

<div>

## <a name="to-verify-response-group-migration-by-using-lync-server-management-shell"></a><span data-ttu-id="15ccd-151">Lync Server 管理シェルを使用して応答グループの移行を確認するには</span><span class="sxs-lookup"><span data-stu-id="15ccd-151">To verify Response Group migration by using Lync Server Management Shell</span></span>

1.  <span data-ttu-id="15ccd-152">RTCUniversalReadOnlyAdmins group のメンバーであるアカウント、または CsViewOnlyAdministrator の役割のメンバーであるアカウントでコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="15ccd-152">Log on to the computer with an account that is a member of RTCUniversalReadOnlyAdmins group or is minimally a member of the CsViewOnlyAdministrator role.</span></span>

2.  <span data-ttu-id="15ccd-153">Lync Server 管理シェルを起動します。 [**スタート**] をクリックし、[**すべてのプログラム**]、[ **Microsoft Lync Server 2013**]、[ **lync server 管理シェル**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="15ccd-153">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>
    
    <span data-ttu-id="15ccd-154">次のコマンドレットの詳細については、次を実行します。</span><span class="sxs-lookup"><span data-stu-id="15ccd-154">For details about the following cmdlets, run:</span></span>
    
        Get-Help <cmdlet name> -Detailed

3.  <span data-ttu-id="15ccd-155">次のコマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="15ccd-155">Run:</span></span>
    
        Get-CsRgsAgentGroup

4.  <span data-ttu-id="15ccd-156">Lync Server 2010 環境内のすべてのエージェントグループがリストに含まれていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="15ccd-156">Verify that all the agent groups in your Lync Server 2010 environment are included in the list.</span></span>

5.  <span data-ttu-id="15ccd-157">次のコマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="15ccd-157">Run:</span></span>
    
        Get-CsRgsQueue

6.  <span data-ttu-id="15ccd-158">Lync Server 2010 環境内のすべてのキューがリストに含まれていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="15ccd-158">Verify that all the queues in your Lync Server 2010 environment are included in the list.</span></span>

7.  <span data-ttu-id="15ccd-159">次のコマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="15ccd-159">Run:</span></span>
    
        Get-CsRgsWorkflow

8.  <span data-ttu-id="15ccd-160">Lync Server 2010 環境内のすべてのワークフローが一覧に含まれていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="15ccd-160">Verify that all the workflows in your Lync Server 2010 environment are included in the list.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

