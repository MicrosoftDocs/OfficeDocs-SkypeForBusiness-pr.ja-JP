---
title: 応答グループを移行する
description: 応答グループを移行します。
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Migrate response groups
ms:assetid: 43741ae7-c871-4573-b660-f2f5febc0856
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204854(v=OCS.15)
ms:contentKeyID: 48184020
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 19da4d39b6f11931bffb5a6e422c2826e7351d69
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48570323"
---
# <a name="migrate-response-groups"></a><span data-ttu-id="63e41-103">応答グループを移行する</span><span class="sxs-lookup"><span data-stu-id="63e41-103">Migrate response groups</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="63e41-104">_**トピックの最終更新日:** 2013-09-23_</span><span class="sxs-lookup"><span data-stu-id="63e41-104">_**Topic Last Modified:** 2013-09-23_</span></span>

<span data-ttu-id="63e41-105">ユーザーが Lync Server 2013 プールに移動された後、応答グループを移行することができます。</span><span class="sxs-lookup"><span data-stu-id="63e41-105">After your users are moved to Lync Server 2013 pools, you can migrate your response groups.</span></span> <span data-ttu-id="63e41-106">応答グループの移行では、エージェントグループ、キュー、ワークフロー、オーディオファイルをコピーし、応答グループの連絡先オブジェクトを従来の展開から Lync Server 2013 プールに移動することが含まれます。</span><span class="sxs-lookup"><span data-stu-id="63e41-106">Migrating response groups includes copying agent groups, queues, workflows, audio files, and moving Response Group contact objects from the legacy deployment to the Lync Server 2013 pool.</span></span> <span data-ttu-id="63e41-107">従来の応答グループを移行した後、応答グループへの通話は Lync Server 2013 プールの応答グループアプリケーションによって処理されます。</span><span class="sxs-lookup"><span data-stu-id="63e41-107">After you migrate your legacy response groups, calls to the response groups are handled by the Response Group application in the Lync Server 2013 pool.</span></span> <span data-ttu-id="63e41-108">応答グループへの通話は、従来のプールによって処理されなくなりました。</span><span class="sxs-lookup"><span data-stu-id="63e41-108">Calls to response groups are no longer handled by the legacy pool.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="63e41-109">すべてのユーザーを Lync Server 2013 プールに移動する前に、応答グループを移行することもできますが、すべてのユーザーを最初に移動することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="63e41-109">Although you can migrate response groups before you move all users to the Lync Server 2013 pool, we recommend that you move all users first.</span></span> <span data-ttu-id="63e41-110">特に、応答グループのエージェントであるユーザーは、Lync Server 2013 プールに移動するまで、新機能のすべての機能を利用できません。</span><span class="sxs-lookup"><span data-stu-id="63e41-110">In particular, users who are response group agents will not have full functionality of new features until they are moved to the Lync Server 2013 pool.</span></span>



</div>

<span data-ttu-id="63e41-111">応答グループを移行する前に、応答グループアプリケーションを含む Lync Server 2013 プールを展開しておく必要があります。</span><span class="sxs-lookup"><span data-stu-id="63e41-111">Before you migrate response groups, you must have deployed a Lync Server 2013 pool that includes the Response Group application.</span></span> <span data-ttu-id="63e41-112">応答グループアプリケーションは、エンタープライズ Voip を展開するときに既定でインストールされ、アクティブ化されます。</span><span class="sxs-lookup"><span data-stu-id="63e41-112">The Response Group application is installed and activated by default when you deploy Enterprise Voice.</span></span> <span data-ttu-id="63e41-113">**ApplicationServer**コマンドレットを実行して、応答グループアプリケーションがインストールされていることを確認できます。</span><span class="sxs-lookup"><span data-stu-id="63e41-113">You can ensure that the Response Group application is installed by running the **Get-CsService –ApplicationServer** cmdlet.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="63e41-114">従来の応答グループを移行する前に、Lync Server 2013 プールに新しい Lync Server 2013 応答グループを作成することができます。</span><span class="sxs-lookup"><span data-stu-id="63e41-114">You can create new Lync Server 2013 response groups in the Lync Server 2013 pool before you migrate your legacy response groups.</span></span>



</div>

<span data-ttu-id="63e41-115">応答グループを従来のプールから Lync Server 2013 に移行するには、 **移動-CsRgsConfiguration** コマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="63e41-115">To migrate response groups from a legacy pool to the Lync Server 2013, you run the **Move-CsRgsConfiguration** cmdlet.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="63e41-116">応答グループ移行コマンドレットは、プール全体の応答グループの構成を移動します。</span><span class="sxs-lookup"><span data-stu-id="63e41-116">The Response Group migration cmdlet moves the Response Group configuration for the entire pool.</span></span> <span data-ttu-id="63e41-117">特定のグループ、キュー、またはワークフローを選択して移行することはできません。</span><span class="sxs-lookup"><span data-stu-id="63e41-117">You cannot select specific groups, queues, or workflows to migrate.</span></span>



</div>

<span data-ttu-id="63e41-118">応答グループを移行した後、Lync Server コントロールパネルまたは Lync Server 管理シェルコマンドレットを使用して、すべてのエージェントグループ、キュー、およびワークフローが正常に移動されたことを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="63e41-118">After you migrate the response groups, you need to use Lync Server Control Panel or Lync Server Management Shell cmdlets to verify that all agent groups, queues, and workflows moved successfully.</span></span>

<span data-ttu-id="63e41-119">応答グループを移行する場合、Lync Server 2010 応答グループは削除されません。</span><span class="sxs-lookup"><span data-stu-id="63e41-119">When you migrate response groups, the Lync Server 2010 response groups are not removed.</span></span> <span data-ttu-id="63e41-120">Lync Server コントロールパネルまたは Lync Server 管理シェルのいずれかを使用して移行後に応答グループを管理すると、Lync Server 2010 応答グループと Lync Server 2013 応答グループの両方を表示することができます。</span><span class="sxs-lookup"><span data-stu-id="63e41-120">When you manage response groups after migration by using either Lync Server Control Panel or Lync Server Management Shell, you can see both the Lync Server 2010 response groups and the Lync Server 2013 response groups.</span></span> <span data-ttu-id="63e41-121">更新プログラムは、Lync Server 2013 応答グループにのみ適用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="63e41-121">You should apply updates only to the Lync Server 2013 response groups.</span></span> <span data-ttu-id="63e41-122">Lync Server 2010 応答グループは、ロールバックの目的でのみ保持されます。</span><span class="sxs-lookup"><span data-stu-id="63e41-122">The Lync Server 2010 response groups are retained only for rollback purposes.</span></span>

<div>


> [!WARNING]  
> <span data-ttu-id="63e41-123">移行が完了し、新しい応答グループが作成された後、lync server コントロールパネルおよび Lync server 管理シェルには、各応答グループの Lync Server 2010 および Lync Server 2013 のバージョンが表示されます。</span><span class="sxs-lookup"><span data-stu-id="63e41-123">After the migration has been completed and the new response groups have been created, the Lync Server Control Panel and the Lync Server Management Shell will display the Lync Server 2010 and Lync Server 2013 versions of each response group.</span></span> <span data-ttu-id="63e41-124">Lync server コントロールパネルまたは Lync Server 管理シェルを使用して Lync Server 2010 応答グループを削除しないでください。</span><span class="sxs-lookup"><span data-stu-id="63e41-124">Do not use Lync Server Control Panel or Lync Server Management Shell to remove the Lync Server 2010 response groups.</span></span> <span data-ttu-id="63e41-125">いずれかを削除すると、移行中に作成された対応する応答グループは動作を停止します。</span><span class="sxs-lookup"><span data-stu-id="63e41-125">If you do remove one, the corresponding response group that was created during migration will stop working.</span></span> <span data-ttu-id="63e41-126">Lync server 2010 プールを使用停止にすると、Lync Server 2010 応答グループが削除されます。</span><span class="sxs-lookup"><span data-stu-id="63e41-126">The Lync Server 2010 response groups will be removed when you decommission the Lync Server 2010 pool.</span></span>



</div>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="63e41-127">プールの使用を停止するまで、以前の展開からデータを削除しないようにすることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="63e41-127">We recommend that you do not remove any data from your previous deployment until you decommission the pool.</span></span> <span data-ttu-id="63e41-128">また、移行直後に応答グループをエクスポートすることを強くお勧めします。</span><span class="sxs-lookup"><span data-stu-id="63e41-128">In addition, we strongly recommend that you export response groups immediately after you migrate.</span></span> <span data-ttu-id="63e41-129">Lync Server 2010 応答グループを削除する必要がある場合は、バックアップから応答グループを復元して Lync Server 2013 応答グループを再度実行することができます。</span><span class="sxs-lookup"><span data-stu-id="63e41-129">If a Lync Server 2010 response group should get removed, you can then restore your response groups from the backup to get Lync Server 2013 response groups running again.</span></span>



</div>

<span data-ttu-id="63e41-130">Lync Server 2013 には、 **ワークフローの種類**と呼ばれる新しい応答グループ機能が導入されています。</span><span class="sxs-lookup"><span data-stu-id="63e41-130">Lync Server 2013 introduces a new Response Group feature called **Workflow Type**.</span></span> <span data-ttu-id="63e41-131">[**ワークフローの種類**] は、[**管理**] または [**管理されていない**] に設定できます。</span><span class="sxs-lookup"><span data-stu-id="63e41-131">**Workflow Type** can be **Managed** or **Unmanaged**.</span></span> <span data-ttu-id="63e41-132">すべての応答グループは、[**ワークフローの種類**] が [**管理されていない**] に設定され、マネージャーの一覧が空の状態で移行されます。</span><span class="sxs-lookup"><span data-stu-id="63e41-132">All response groups are migrated with **Workflow Type** set to **Unmanaged** and with an empty Manager list.</span></span>

<span data-ttu-id="63e41-133">**Move-CsRgsConfiguration** コマンドレットを実行した場合、エージェント グループ、キュー、ワークフロー、およびオーディオ ファイルは、ロールバックできるようにレガシ プールに残されたままとなります。</span><span class="sxs-lookup"><span data-stu-id="63e41-133">When you run the **Move-CsRgsConfiguration** cmdlet, the agent groups, queues, workflows, and audio files remain in the legacy pool for rollback purposes.</span></span> <span data-ttu-id="63e41-134">ただし、レガシ プールへのロールバックが必要な場合に連絡先オブジェクトを移動してレガシ プールに戻すには、**Move-CsApplicationEndpoint** コマンドレットを実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="63e41-134">If you do need to roll back to the legacy pool, however, you need to run the **Move-CsApplicationEndpoint** cmdlet to move contact objects back to the legacy pool.</span></span>

<span data-ttu-id="63e41-135">応答グループ構成を移行するための次の手順では、従来のプールと Lync Server 2013 プール間の1対1の関係があることを前提としています。</span><span class="sxs-lookup"><span data-stu-id="63e41-135">The following procedure for migrating Response Group configurations assumes that you have a one-to-one relationship between your legacy pools and the Lync Server 2013 pools.</span></span> <span data-ttu-id="63e41-136">移行と展開時にプールを統合または分割する予定の場合は、どの従来のプールを Lync Server 2013 プールにマッピングするかを計画する必要があります。</span><span class="sxs-lookup"><span data-stu-id="63e41-136">If you plan to consolidate or split up pools during your migration and deployment, you need to plan which legacy pool maps to which Lync Server 2013 pool.</span></span>

<div>

## <a name="to-migrate-response-group-configurations"></a><span data-ttu-id="63e41-137">応答グループの構成を移行するには</span><span class="sxs-lookup"><span data-stu-id="63e41-137">To migrate Response Group configurations</span></span>

1.  <span data-ttu-id="63e41-138">RTCUniversalServerAdmins グループのメンバーであるアカウント、またはそれと同等の管理者権限およびアクセス許可を持つアカウントを使用して、コンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="63e41-138">Log on to the computer with an account that is a member of the RTCUniversalServerAdmins group or has equivalent administrator rights and permissions.</span></span>

2.  <span data-ttu-id="63e41-139">Lync Server 管理シェルを以下の手順で起動します。[**スタート**]、[**すべてのプログラム**]、[**Microsoft Lync Server 2013**]、[**Lync Server 管理シェル**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="63e41-139">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="63e41-140">実行</span><span class="sxs-lookup"><span data-stu-id="63e41-140">Run:</span></span>
    
        Move-CsRgsConfiguration -Source <source pool FQDN> -Destination <destination pool FQDN>
    
    <span data-ttu-id="63e41-141">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="63e41-141">For example:</span></span>
    
        Move-CsRgsConfiguration -Source lync-old.contoso.net -Destination lync-new.contoso.net

4.  <span data-ttu-id="63e41-142">応答グループとエージェントを Lync Server 2013 プールに移行すると、エージェントがサインインおよびサインアウトする際に使用する URL が Lync Server 2013 の URL になり、[ **ツール** ] メニューから利用できるようになります。</span><span class="sxs-lookup"><span data-stu-id="63e41-142">After you migrate response groups and agents to the Lync Server 2013 pool, the URL that agents use to sign in and sign out is a Lync Server 2013 URL and is available from the **Tools** menu.</span></span> <span data-ttu-id="63e41-143">ブックマークなどの参照を、新しい URL に更新するようにエージェントに知らせてください。</span><span class="sxs-lookup"><span data-stu-id="63e41-143">Remind agents to update any references, such as bookmarks, to the new URL.</span></span>

</div>

<div>

## <a name="to-verify-response-group-migration-by-using-lync-server-control-panel"></a><span data-ttu-id="63e41-144">Lync Server コントロール パネルを使用して応答グループの移行を確認するには</span><span class="sxs-lookup"><span data-stu-id="63e41-144">To verify Response Group migration by using Lync Server Control Panel</span></span>

1.  <span data-ttu-id="63e41-145">RTCUniversalReadOnlyAdmins グループのメンバーまたは少なくとも CsViewOnlyAdministrator 役割のメンバーであるアカウントを使用して、コンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="63e41-145">Log on to the computer with an account that is a member of RTCUniversalReadOnlyAdmins group or is minimally a member of the CsViewOnlyAdministrator role.</span></span>

2.  <span data-ttu-id="63e41-146">ブラウザー ウィンドウを開いて管理 URL を入力し、Lync Server コントロール パネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="63e41-146">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="63e41-147">Lync Server コントロールパネルの起動に使用できるさまざまな方法の詳細については、「 [Open Lync server 2013 管理ツール](lync-server-2013-open-lync-server-administrative-tools.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="63e41-147">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="63e41-148">左側のナビゲーション ウィンドウで [**応答グループ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="63e41-148">In the left navigation pane, click **Response Groups**.</span></span>

4.  <span data-ttu-id="63e41-149">[ **ワークフロー** ] タブで、Lync Server 2010 環境内のすべてのワークフローがリストに含まれていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="63e41-149">On the **Workflow** tab, verify that all the workflows in your Lync Server 2010 environment are included in the list.</span></span>

5.  <span data-ttu-id="63e41-150">[ **キュー** ] タブをクリックして、Lync Server 2010 環境内のすべてのキューがリストに含まれていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="63e41-150">Click the **Queue** tab, and verify that all the queues in your Lync Server 2010 environment are included in the list.</span></span>

6.  <span data-ttu-id="63e41-151">[ **グループ** ] タブをクリックし、Lync Server 2010 環境内のすべてのエージェントグループがリストに含まれていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="63e41-151">Click the **Group** tab, and verify that all the agent groups in your Lync Server 2010 environment are included in the list.</span></span>

</div>

<div>

## <a name="to-verify-response-group-migration-by-using-lync-server-management-shell"></a><span data-ttu-id="63e41-152">Lync Server 管理シェルを使用して応答グループの移行を確認するには</span><span class="sxs-lookup"><span data-stu-id="63e41-152">To verify Response Group migration by using Lync Server Management Shell</span></span>

1.  <span data-ttu-id="63e41-153">RTCUniversalReadOnlyAdmins グループのメンバーまたは少なくとも CsViewOnlyAdministrator 役割のメンバーであるアカウントを使用して、コンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="63e41-153">Log on to the computer with an account that is a member of RTCUniversalReadOnlyAdmins group or is minimally a member of the CsViewOnlyAdministrator role.</span></span>

2.  <span data-ttu-id="63e41-154">Lync Server 管理シェルを以下の手順で起動します。[**スタート**]、[**すべてのプログラム**]、[**Microsoft Lync Server 2013**]、[**Lync Server 管理シェル**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="63e41-154">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>
    
    <span data-ttu-id="63e41-155">各コマンドレットの詳細については、次のように実行してください。</span><span class="sxs-lookup"><span data-stu-id="63e41-155">For details about the following cmdlets, run:</span></span>
    
        Get-Help <cmdlet name> -Detailed

3.  <span data-ttu-id="63e41-156">実行</span><span class="sxs-lookup"><span data-stu-id="63e41-156">Run:</span></span>
    
        Get-CsRgsAgentGroup

4.  <span data-ttu-id="63e41-157">Lync Server 2010 環境内のすべてのエージェントグループがリストに含まれていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="63e41-157">Verify that all the agent groups in your Lync Server 2010 environment are included in the list.</span></span>

5.  <span data-ttu-id="63e41-158">実行</span><span class="sxs-lookup"><span data-stu-id="63e41-158">Run:</span></span>
    
        Get-CsRgsQueue

6.  <span data-ttu-id="63e41-159">Lync Server 2010 環境内のすべてのキューがリストに含まれていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="63e41-159">Verify that all the queues in your Lync Server 2010 environment are included in the list.</span></span>

7.  <span data-ttu-id="63e41-160">実行</span><span class="sxs-lookup"><span data-stu-id="63e41-160">Run:</span></span>
    
        Get-CsRgsWorkflow

8.  <span data-ttu-id="63e41-161">Lync Server 2010 環境内のすべてのワークフローがリストに含まれていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="63e41-161">Verify that all the workflows in your Lync Server 2010 environment are included in the list.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

