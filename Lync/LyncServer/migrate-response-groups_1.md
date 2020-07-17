---
title: 応答グループを移行する
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Migrate response groups
ms:assetid: 5c07bf4b-ad8a-4b83-b970-7d933bb7c4ef
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204931(v=OCS.15)
ms:contentKeyID: 48184250
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: de012d0886c51cd70d5003beb24053ff86af05b7
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/16/2020
ms.locfileid: "44756938"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="migrate-response-groups"></a><span data-ttu-id="0f9f2-102">応答グループを移行する</span><span class="sxs-lookup"><span data-stu-id="0f9f2-102">Migrate response groups</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0f9f2-103">_**トピックの最終更新日:** 2012-10-19_</span><span class="sxs-lookup"><span data-stu-id="0f9f2-103">_**Topic Last Modified:** 2012-10-19_</span></span>

<span data-ttu-id="0f9f2-104">ユーザーが Lync Server 2013 プールに移動された後、応答グループを移行することができます。</span><span class="sxs-lookup"><span data-stu-id="0f9f2-104">After your users are moved to Lync Server 2013 pools, you can migrate your response groups.</span></span> <span data-ttu-id="0f9f2-105">応答グループの移行には、エージェントグループ、キュー、ワークフロー、およびオーディオファイルをコピーし、応答グループの連絡先オブジェクトを従来の展開から Lync Server 2013 プールに移動することが含まれます。</span><span class="sxs-lookup"><span data-stu-id="0f9f2-105">Migrating response groups includes copying agent groups, queues, workflows, and audio files, and moving Response Group contact objects from the legacy deployment to the Lync Server 2013 pool.</span></span> <span data-ttu-id="0f9f2-106">従来の応答グループを移行した後、応答グループへの通話は Lync Server 2013 プールの応答グループアプリケーションによって処理されます。</span><span class="sxs-lookup"><span data-stu-id="0f9f2-106">After you migrate your legacy response groups, calls to the response groups are handled by the Response Group application in the Lync Server 2013 pool.</span></span> <span data-ttu-id="0f9f2-107">応答グループへの通話は、従来のプールによって処理されなくなりました。</span><span class="sxs-lookup"><span data-stu-id="0f9f2-107">Calls to response groups are no longer handled by the legacy pool.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="0f9f2-108">すべてのユーザーを Lync Server 2013 プールに移動する前に、応答グループを移行することもできますが、すべてのユーザーを最初に移動することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="0f9f2-108">Although you can migrate response groups before you move all users to the Lync Server 2013 pool, we recommend that you move all users first.</span></span> <span data-ttu-id="0f9f2-109">特に、応答グループのエージェントであるユーザーは、Lync Server 2013 プールに移動するまで、新機能のすべての機能を利用できません。</span><span class="sxs-lookup"><span data-stu-id="0f9f2-109">In particular, users who are response group agents will not have full functionality of new features until they are moved to the Lync Server 2013 pool.</span></span>



</div>

<span data-ttu-id="0f9f2-110">応答グループを移行する前に、応答グループアプリケーションを含む Lync Server 2013 プールを展開しておく必要があります。</span><span class="sxs-lookup"><span data-stu-id="0f9f2-110">Before you migrate response groups, you must have deployed a Lync Server 2013 pool that includes the Response Group application.</span></span> <span data-ttu-id="0f9f2-111">応答グループアプリケーションは、エンタープライズ Voip を展開するときに既定でインストールされ、アクティブ化されます。</span><span class="sxs-lookup"><span data-stu-id="0f9f2-111">The Response Group application is installed and activated by default when you deploy Enterprise Voice.</span></span> <span data-ttu-id="0f9f2-112">**ApplicationServer**コマンドレットを実行して、応答グループアプリケーションがインストールされていることを確認できます。</span><span class="sxs-lookup"><span data-stu-id="0f9f2-112">You can ensure that the Response Group application is installed by running the **Get-CsService–ApplicationServer** cmdlet.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="0f9f2-113">従来の応答グループを移行する前に、Lync Server 2013 プールに新しい Lync Server 2013 応答グループを作成することができます。</span><span class="sxs-lookup"><span data-stu-id="0f9f2-113">You can create new Lync Server 2013 response groups in the Lync Server 2013 pool before you migrate your legacy response groups.</span></span>



</div>

<span data-ttu-id="0f9f2-114">応答グループを従来のプールから Lync Server 2013 に移行するには、**移動-CsRgsConfiguration**コマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="0f9f2-114">To migrate response groups from a legacy pool to the Lync Server 2013, you run the **Move-CsRgsConfiguration** cmdlet.</span></span> <span data-ttu-id="0f9f2-115">**Move-CsRgsConfiguration** コマンドレットを実行する前に、まず Windows Management Instrumentation (WMI) 下位互換性インターフェイス パッケージをインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="0f9f2-115">Before you can run **Move-CsRgsConfiguration**, you must first install the Windows Management Instrumentation (WMI) Backward Compatibility interfaces package.</span></span> <span data-ttu-id="0f9f2-116">このアプリケーションは、OCSWMIBC.msi を実行してインストールします。</span><span class="sxs-lookup"><span data-stu-id="0f9f2-116">Install this application by running OCSWMIBC.msi.</span></span> <span data-ttu-id="0f9f2-117">OCSWMIBC.msi は、インストール メディアの Setup フォルダーにあります。</span><span class="sxs-lookup"><span data-stu-id="0f9f2-117">You can find OCSWMIBC.msi on the installation media in the Setup folder.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="0f9f2-118">応答グループ移行コマンドレットは、プール全体の応答グループの構成を移動します。</span><span class="sxs-lookup"><span data-stu-id="0f9f2-118">The Response Group migration cmdlet moves the Response Group configuration for the entire pool.</span></span> <span data-ttu-id="0f9f2-119">特定のグループ、キュー、またはワークフローを選択して移行することはできません。</span><span class="sxs-lookup"><span data-stu-id="0f9f2-119">You cannot select specific groups, queues, or workflows to migrate.</span></span>



</div>

<span data-ttu-id="0f9f2-120">応答グループを移行した後、正式エージェントが応答グループにサインインおよびサインアウトするために使用する URL を更新し、Lync Server コントロールパネルまたは Lync Server 管理シェルコマンドレットを使用して、すべてのエージェントグループ、キュー、およびワークフローが正常に移動されたことを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="0f9f2-120">After you migrate the response groups, you need to update the URL that formal agents use to sign into and out of their response groups, and use Lync Server Control Panel or Lync Server Management Shell cmdlets to verify that all agent groups, queues, and workflows moved successfully.</span></span>

<div>


> [!WARNING]  
> <span data-ttu-id="0f9f2-121">応答グループを移行する場合、Office Communications Server 2007 R2 応答グループは削除されません。</span><span class="sxs-lookup"><span data-stu-id="0f9f2-121">When you migrate response groups, the Office Communications Server 2007 R2 response groups are not removed.</span></span> <span data-ttu-id="0f9f2-122">Office Communications Server 2007 R2 応答グループは削除しないでください。</span><span class="sxs-lookup"><span data-stu-id="0f9f2-122">Do not remove Office Communications Server 2007 R2 response groups.</span></span> <span data-ttu-id="0f9f2-123">Office Communications Server 2007 R2 応答グループを削除すると、Lync Server 2013 の応答グループは動作を停止します。</span><span class="sxs-lookup"><span data-stu-id="0f9f2-123">If you remove an Office Communications Server 2007 R2 response group, the response groups in Lync Server 2013 stop working.</span></span>



</div>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="0f9f2-124">プールの使用を停止するまで、以前の展開からデータを削除しないようにすることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="0f9f2-124">We recommend that you do not remove any data from your previous deployment until you decommission the pool.</span></span> <span data-ttu-id="0f9f2-125">また、移行直後に応答グループをエクスポートすることを強くお勧めします。</span><span class="sxs-lookup"><span data-stu-id="0f9f2-125">In addition, we strongly recommend that you export response groups immediately after you migrate.</span></span> <span data-ttu-id="0f9f2-126">Office Communications Server 2007 R2 応答グループが削除された場合は、バックアップから応答グループを復元して、Lync Server 2013 応答グループを再度実行することができます。</span><span class="sxs-lookup"><span data-stu-id="0f9f2-126">If an Office Communications Server 2007 R2 response group gets removed, you can then restore your response groups from the backup to get Lync Server 2013 response groups running again.</span></span>



</div>

<span data-ttu-id="0f9f2-127">**Move-CsRgsConfiguration** コマンドレットを実行した場合、エージェント グループ、キュー、ワークフロー、およびオーディオ ファイルは、ロールバックできるようにレガシ プールに残されたままとなります。</span><span class="sxs-lookup"><span data-stu-id="0f9f2-127">When you run the **Move-CsRgsConfiguration** cmdlet, the agent groups, queues, workflows, and audio files remain in the legacy pool for rollback purposes.</span></span> <span data-ttu-id="0f9f2-128">ただし、レガシ プールへのロールバックが必要な場合に連絡先オブジェクトを移動してレガシ プールに戻すには、**Move-CsApplicationEndpoint** コマンドレットを実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="0f9f2-128">If you do need to roll back to the legacy pool, however, you need to run the **Move-CsApplicationEndpoint** cmdlet to move contact objects back to the legacy pool.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="0f9f2-129">プールの使用を停止するまで、従来のプールから応答グループのデータを削除しないようにすることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="0f9f2-129">We recommend that you don't delete any response group data from the legacy pool until you decommission the pool.</span></span>



</div>

<span data-ttu-id="0f9f2-130">応答グループの構成を移行する手順では、従来のプールと Lync Server 2013 プール間の1対1の関係があることを前提としています。</span><span class="sxs-lookup"><span data-stu-id="0f9f2-130">The procedure that follows for migrating Response Group configurations assumes that you have a one-to-one relationship between your legacy pools and the Lync Server 2013 pools.</span></span> <span data-ttu-id="0f9f2-131">移行と展開時にプールを統合または分割する予定の場合は、どの従来のプールを Lync Server 2013 プールにマッピングするかを計画する必要があります。</span><span class="sxs-lookup"><span data-stu-id="0f9f2-131">If you plan to consolidate or split up pools during your migration and deployment, you need to plan which legacy pool maps to which Lync Server 2013 pool.</span></span>

<div>

## <a name="to-migrate-response-group-configurations"></a><span data-ttu-id="0f9f2-132">応答グループの構成を移行するには</span><span class="sxs-lookup"><span data-stu-id="0f9f2-132">To Migrate Response Group Configurations</span></span>

1.  <span data-ttu-id="0f9f2-133">インストール メディアの Setup フォルダーで OCSWMIBC.msi を検索し、これをインストールします。</span><span class="sxs-lookup"><span data-stu-id="0f9f2-133">Locate OCSWMIBC.msi in the Setup folder of the installation media and install it.</span></span>

2.  <span data-ttu-id="0f9f2-134">RTCUniversalServerAdmins グループのメンバーであるアカウント、またはそれと同等の管理者権限およびアクセス許可を持つアカウントを使用して、コンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="0f9f2-134">Log on to the computer with an account that is a member of the RTCUniversalServerAdmins group or has equivalent administrator rights and permissions.</span></span>

3.  <span data-ttu-id="0f9f2-135">Lync Server 管理シェルを開きます。</span><span class="sxs-lookup"><span data-stu-id="0f9f2-135">Open the Lync Server Management Shell.</span></span>

4.  <span data-ttu-id="0f9f2-136">コマンドラインで、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="0f9f2-136">At the command line, type the following:</span></span>
    
        Move-CsRgsConfiguration -Source <source pool FQDN> -Destination <destination pool FQDN>
    
    <span data-ttu-id="0f9f2-137">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="0f9f2-137">For example:</span></span>
    
        Move-CsRgsConfiguration -Source pool01.contoso.net -Destination pool02.contoso.net

5.  <span data-ttu-id="0f9f2-138">Office Communications Server 2007 R2 環境の Microsoft Office Communicator 2007 R2 用の [応答グループ] タブを展開した場合は、そのタブを Office Communicator 2007 R2 tabs.xml ファイルから削除します。</span><span class="sxs-lookup"><span data-stu-id="0f9f2-138">If you deployed the Response Group tab for Microsoft Office Communicator 2007 R2 in your Office Communications Server 2007 R2 environment, remove the tab from the Office Communicator 2007 R2 tabs.xml file.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="0f9f2-139">正規のエージェントが通話を受信するには、[応答グループ] タブを使用して応答グループにサインインする必要がありました。</span><span class="sxs-lookup"><span data-stu-id="0f9f2-139">Formal agents used the Response Group tab to sign in to their response groups before they could receive calls.</span></span> <span data-ttu-id="0f9f2-140">[応答グループ] タブを展開した場合は、展開時に Office Communicator 2007 R2 tabs.xml ファイルの場所を選択しています。</span><span class="sxs-lookup"><span data-stu-id="0f9f2-140">If you deployed the Response Group tab, you chose the location for the Office Communicator 2007 R2 tabs.xml file when you deployed it.</span></span>

    
    </div>

6.  <span data-ttu-id="0f9f2-141">各エージェントが各応答グループにサインインおよびサインアウトするために必要な更新後の URL をユーザーに付与します。</span><span class="sxs-lookup"><span data-stu-id="0f9f2-141">Provide users with the updated URL that agents need to sign into and out of their response groups.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="0f9f2-142">通常、URL は https://webpoolFQDN/RgsClients/Tab.aspx 、Lync Server 2013 に移行したばかりのプールに関連付けられている web プールの完全修飾ドメイン名 (fqdn) である webpoolFQDN です。</span><span class="sxs-lookup"><span data-stu-id="0f9f2-142">The URL is typically https://webpoolFQDN/RgsClients/Tab.aspx, where webpoolFQDN is the fully qualified domain name (FQDN) of the web pool that is associated with the pool that you just migrated to Lync Server 2013.</span></span>

    
    </div>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="0f9f2-143">Lync の [<STRONG>ツール</STRONG>] メニューから URL を利用できるため、ユーザーが lync 2013 にアップグレードした後は、この手順は必要ありません。</span><span class="sxs-lookup"><span data-stu-id="0f9f2-143">This step is not required after users upgrade to Lync 2013 because the URL is available from the <STRONG>Tools</STRONG> menu in Lync.</span></span>

    
    </div>

</div>

<div>

## <a name="to-verify-response-group-migration-by-using-lync-server-control-panel"></a><span data-ttu-id="0f9f2-144">Lync Server コントロールパネルを使用して応答グループの移行を確認するには</span><span class="sxs-lookup"><span data-stu-id="0f9f2-144">To Verify Response Group Migration by Using Lync Server Control Panel</span></span>

1.  <span data-ttu-id="0f9f2-145">Lync Server コントロール パネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="0f9f2-145">Open the Lync Server Control Panel.</span></span>

2.  <span data-ttu-id="0f9f2-146">左側のナビゲーション ウィンドウで [**応答グループ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="0f9f2-146">In the left navigation pane, click **Response Groups**.</span></span>

3.  <span data-ttu-id="0f9f2-147">[**ワークフロー** ] タブで、Office Communications Server 2007 R2 環境のすべてのワークフローがリストに含まれていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="0f9f2-147">On the **Workflow** tab, verify that all the workflows in your Office Communications Server 2007 R2 environment are included in the list.</span></span>

4.  <span data-ttu-id="0f9f2-148">[**キュー** ] タブをクリックして、Office Communications Server 2007 R2 環境のすべてのキューがリストに含まれていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="0f9f2-148">Click the **Queue** tab, and verify that all the queues in your Office Communications Server 2007 R2 environment are included in the list.</span></span>

5.  <span data-ttu-id="0f9f2-149">[**グループ**] タブをクリックし、Office Communications Server 2007 R2 環境のすべてのエージェントグループがリストに含まれていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="0f9f2-149">Click the **Group** tab, and verify that all the agent groups in your Office Communications Server 2007 R2 environment are included in the list.</span></span>

</div>

<div>

## <a name="to-verify-response-group-migration-by-using-cmdlets"></a><span data-ttu-id="0f9f2-150">コマンドレットを使用して応答グループの移行を確認するには</span><span class="sxs-lookup"><span data-stu-id="0f9f2-150">To Verify Response Group Migration by Using Cmdlets</span></span>

1.  <span data-ttu-id="0f9f2-151">Lync Server 管理シェルを開きます。</span><span class="sxs-lookup"><span data-stu-id="0f9f2-151">Open the Lync Server Management Shell.</span></span>
    
    <span data-ttu-id="0f9f2-152">各コマンドレットの詳細については、次のように実行してください。</span><span class="sxs-lookup"><span data-stu-id="0f9f2-152">For details about the following cmdlets, run:</span></span>
    
        Get-Help <cmdlet name> -Detailed

2.  <span data-ttu-id="0f9f2-153">コマンド ラインで、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="0f9f2-153">At the command line, type the following:</span></span>
    
        Get-CsRgsAgentGroup

3.  <span data-ttu-id="0f9f2-154">Office Communications Server 2007 R2 環境のすべてのエージェントグループがリストに含まれていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="0f9f2-154">Verify that all the agent groups in your Office Communications Server 2007 R2 environment are included in the list.</span></span>

4.  <span data-ttu-id="0f9f2-155">コマンドラインで、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="0f9f2-155">At the command line, type the following:</span></span>
    
        Get-CsRgsQueue

5.  <span data-ttu-id="0f9f2-156">Office Communications Server 2007 R2 環境のすべてのキューがリストに含まれていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="0f9f2-156">Verify that all the queues in your Office Communications Server 2007 R2 environment are included in the list.</span></span>

6.  <span data-ttu-id="0f9f2-157">コマンドラインで、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="0f9f2-157">At the command line, type the following:</span></span>
    
        Get-CsRgsWorkflow

7.  <span data-ttu-id="0f9f2-158">Office Communications Server 2007 R2 環境のすべてのワークフローがリストに含まれていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="0f9f2-158">Verify that all the workflows in your Office Communications Server 2007 R2 environment are included in the list.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

