---
title: 'Lync Server 2013: インフラストラクチャと展開のコマンドレット'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Infrastructure and deployment cmdlets
ms:assetid: 0a6e872a-9f70-4f23-a4a5-8820dbf55370
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398153(v=OCS.15)
ms:contentKeyID: 48183364
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 93d2c35fcc9ebf037eb33e6553cef28b9e1041ec
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2020
ms.locfileid: "42044649"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="infrastructure-and-deployment-cmdlets-in-lync-server-2013"></a><span data-ttu-id="f7620-102">Lync Server 2013 のインフラストラクチャと展開のコマンドレット</span><span class="sxs-lookup"><span data-stu-id="f7620-102">Infrastructure and deployment cmdlets in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f7620-103">_**トピックの最終更新日:** 2012-10-09_</span><span class="sxs-lookup"><span data-stu-id="f7620-103">_**Topic Last Modified:** 2012-10-09_</span></span>

<span data-ttu-id="f7620-104">Microsoft Lync Server 2013 に含まれるインフラストラクチャと展開のコマンドレットは、製品の初期セットアップと展開に役立ちます。Lync Server を展開した後は、これらのコマンドレットを使用して、コンポーネントが期待どおりに動作しているかどうかを確認することができます。レプリケーションの設定を管理する。そして、Lync Server のトポロジ、ポリシー、および構成設定をバックアップおよび復元します。</span><span class="sxs-lookup"><span data-stu-id="f7620-104">The infrastructure and deployment cmdlets included in Microsoft Lync Server 2013 can be useful in the initial setup and deployment of the product; after Lync Server has been deployed these cmdlets can then be used to do such things as verify that components are working as expected; manage replication settings; and backup and restore the Lync Server topology, policies, and configuration settings.</span></span>

<div>

## <a name="infrastructure-and-deployment-cmdlets"></a><span data-ttu-id="f7620-105">インフラストラクチャおよび展開のコマンドレット</span><span class="sxs-lookup"><span data-stu-id="f7620-105">Infrastructure and Deployment Cmdlets</span></span>

<span data-ttu-id="f7620-106">管理者は、ほとんどの場合、インフラストラクチャと展開の多くを直接呼び出す必要があります。</span><span class="sxs-lookup"><span data-stu-id="f7620-106">Administrators will rarely need to directly call many of the infrastructure and deployment.</span></span> <span data-ttu-id="f7620-107">そのため、これらのコマンドレットは、セットアップまたはトポロジビルダーを実行するときに自動的に呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="f7620-107">That is because these cmdlets are automatically invoked when you run Setup or the Topology Builder.</span></span> <span data-ttu-id="f7620-108">(1 つの大きな例外が、Lync Server のトポロジ、ポリシー、および構成設定のバックアップコピーを作成できる、**エクスポート-CsConfiguration**コマンドレットである可能性があります)。ただし、必要に応じて、Lync Server 管理シェルまたはスクリプト内から、インフラストラクチャと展開のコマンドレットを実行することもできます。スクリプトを使用すると、特定のタスクを自動化できます。</span><span class="sxs-lookup"><span data-stu-id="f7620-108">(One major exception might be the **Export-CsConfiguration** cmdlet, which enables you to make a backup copy of your Lync Server topology, policies, and configuration settings.) However, and when needed, the infrastructure and deployment cmdlets can also be run from the Lync Server Management Shell or from within a script; using a script enables you to automate certain tasks.</span></span> <span data-ttu-id="f7620-109">以下に、インフラストラクチャと展開に直接関連するコマンドレットの一覧を示します。</span><span class="sxs-lookup"><span data-stu-id="f7620-109">The following is a list of cmdlets that relate directly to infrastructure and deployment:</span></span>

<span data-ttu-id="f7620-110">**[Lync Server 2013 での Active Directory のコマンドレット](lync-server-2013-active-directory-cmdlets.md)**</span><span class="sxs-lookup"><span data-stu-id="f7620-110">**[Active Directory cmdlets in Lync Server 2013](lync-server-2013-active-directory-cmdlets.md)**</span></span>

  - <span></span>  
    <span data-ttu-id="f7620-111">[無効-CsAdDomain](https://technet.microsoft.com/library/Gg398785(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="f7620-111">[Disable-CsAdDomain](https://technet.microsoft.com/library/Gg398785(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="f7620-112">[Enable-CsAdDomain](https://technet.microsoft.com/library/Gg412764(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="f7620-112">[Enable-CsAdDomain](https://technet.microsoft.com/library/Gg412764(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="f7620-113">[取得-CsAdDomain](https://technet.microsoft.com/library/Gg398453(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="f7620-113">[Get-CsAdDomain](https://technet.microsoft.com/library/Gg398453(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="f7620-114">[無効-CsAdForest](https://technet.microsoft.com/library/Gg398122(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="f7620-114">[Disable-CsAdForest](https://technet.microsoft.com/library/Gg398122(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="f7620-115">[Enable-CsAdForest](https://technet.microsoft.com/library/Gg425713(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="f7620-115">[Enable-CsAdForest](https://technet.microsoft.com/library/Gg425713(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="f7620-116">[取得-CsAdForest](https://technet.microsoft.com/library/Gg412995(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="f7620-116">[Get-CsAdForest](https://technet.microsoft.com/library/Gg412995(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="f7620-117">[取得-CsAdServerSchema](https://technet.microsoft.com/library/Gg413070(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="f7620-117">[Get-CsAdServerSchema](https://technet.microsoft.com/library/Gg413070(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="f7620-118">[Install-CsAdServerSchema](https://technet.microsoft.com/library/Gg398681(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="f7620-118">[Install-CsAdServerSchema](https://technet.microsoft.com/library/Gg398681(v=OCS.15))</span></span>

<span data-ttu-id="f7620-119">**[Lync Server 2013 のレプリケーションのコマンドレット](lync-server-2013-replication-cmdlets.md)**</span><span class="sxs-lookup"><span data-stu-id="f7620-119">**[Replication cmdlets in Lync Server 2013](lync-server-2013-replication-cmdlets.md)**</span></span>

  - <span></span>  
    <span data-ttu-id="f7620-120">[デバッグ-CsInterPoolReplication](https://technet.microsoft.com/library/JJ619185(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="f7620-120">[Debug-CsInterPoolReplication](https://technet.microsoft.com/library/JJ619185(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="f7620-121">[Invoke-csmanagementstorereplication](https://technet.microsoft.com/library/Gg413060(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="f7620-121">[Invoke-CsManagementStoreReplication](https://technet.microsoft.com/library/Gg413060(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="f7620-122">[Get-csmanagementstorereplicationstatus](https://technet.microsoft.com/library/Gg399052(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="f7620-122">[Get-CsManagementStoreReplicationStatus](https://technet.microsoft.com/library/Gg399052(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="f7620-123">[を有効にする-CsReplica](https://technet.microsoft.com/library/Gg425965(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="f7620-123">[Enable-CsReplica](https://technet.microsoft.com/library/Gg425965(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="f7620-124">[テスト-CsReplica](https://technet.microsoft.com/library/JJ205289(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="f7620-124">[Test-CsReplica](https://technet.microsoft.com/library/JJ205289(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="f7620-125">[-CsUserReplicatorConfiguration の取得](https://technet.microsoft.com/library/Gg398548(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="f7620-125">[Get-CsUserReplicatorConfiguration](https://technet.microsoft.com/library/Gg398548(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="f7620-126">[新しい-CsUserReplicatorConfiguration](https://technet.microsoft.com/library/Gg399059(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="f7620-126">[New-CsUserReplicatorConfiguration](https://technet.microsoft.com/library/Gg399059(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="f7620-127">[-CsUserReplicatorConfiguration の削除](https://technet.microsoft.com/library/Gg425738(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="f7620-127">[Remove-CsUserReplicatorConfiguration](https://technet.microsoft.com/library/Gg425738(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="f7620-128">[設定-CsUserReplicatorConfiguration](https://technet.microsoft.com/library/Gg398540(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="f7620-128">[Set-CsUserReplicatorConfiguration](https://technet.microsoft.com/library/Gg398540(v=OCS.15))</span></span>

<span data-ttu-id="f7620-129">**[トポロジのコマンドレット (Lync Server 2013)](lync-server-2013-topology-cmdlets.md)**</span><span class="sxs-lookup"><span data-stu-id="f7620-129">**[Topology cmdlets jn Lync Server 2013](lync-server-2013-topology-cmdlets.md)**</span></span>

  - <span></span>  
    <span data-ttu-id="f7620-130">[取得-CsPool](https://technet.microsoft.com/library/Gg398992(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="f7620-130">[Get-CsPool](https://technet.microsoft.com/library/Gg398992(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="f7620-131">[取得-CsSite](https://technet.microsoft.com/library/Gg398185(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="f7620-131">[Get-CsSite](https://technet.microsoft.com/library/Gg398185(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="f7620-132">[設定-CsSite](https://technet.microsoft.com/library/Gg413023(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="f7620-132">[Set-CsSite](https://technet.microsoft.com/library/Gg413023(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="f7620-133">[Enable-CsTopology](https://technet.microsoft.com/library/Gg398398(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="f7620-133">[Enable-CsTopology](https://technet.microsoft.com/library/Gg398398(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="f7620-134">[取得-CsTopology テクノロジー](https://technet.microsoft.com/library/Gg412824(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="f7620-134">[Get-CsTopology](https://technet.microsoft.com/library/Gg412824(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="f7620-135">[発行-CsTopology テクノロジー](https://technet.microsoft.com/library/Gg398953(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="f7620-135">[Publish-CsTopology](https://technet.microsoft.com/library/Gg398953(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="f7620-136">[テスト-CsTopology テクノロジー](https://technet.microsoft.com/library/Gg398127(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="f7620-136">[Test-CsTopology](https://technet.microsoft.com/library/Gg398127(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="f7620-137">[エクスポート-CsConfiguration](https://technet.microsoft.com/library/Gg398627(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="f7620-137">[Export-CsConfiguration](https://technet.microsoft.com/library/Gg398627(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="f7620-138">[インポート-CsConfiguration](https://technet.microsoft.com/library/Gg398800(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="f7620-138">[Import-CsConfiguration](https://technet.microsoft.com/library/Gg398800(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="f7620-139">[Get-csserverversion](https://technet.microsoft.com/library/Gg398470(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="f7620-139">[Get-CsServerVersion](https://technet.microsoft.com/library/Gg398470(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="f7620-140">[-CsComputer を無効にする](https://technet.microsoft.com/library/Gg399023(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="f7620-140">[Disable-CsComputer](https://technet.microsoft.com/library/Gg399023(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="f7620-141">[を有効にする-CsComputer](https://technet.microsoft.com/library/Gg412815(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="f7620-141">[Enable-CsComputer](https://technet.microsoft.com/library/Gg412815(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="f7620-142">[-CsComputer の取得](https://technet.microsoft.com/library/Gg425959(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="f7620-142">[Get-CsComputer](https://technet.microsoft.com/library/Gg425959(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="f7620-143">[テスト-CsComputer](https://technet.microsoft.com/library/Gg398162(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="f7620-143">[Test-CsComputer](https://technet.microsoft.com/library/Gg398162(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="f7620-144">[Get-csnetworkinterface](https://technet.microsoft.com/library/Gg398121(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="f7620-144">[Get-CsNetworkInterface](https://technet.microsoft.com/library/Gg398121(v=OCS.15))</span></span>

<span data-ttu-id="f7620-145">**[Lync Server 2013 のバックアップと高可用性のコマンドレット](lync-server-2013-backup-and-high-availability-cmdlets.md)**</span><span class="sxs-lookup"><span data-stu-id="f7620-145">**[Backup and high availability cmdlets in Lync Server 2013](lync-server-2013-backup-and-high-availability-cmdlets.md)**</span></span>

  - <span data-ttu-id="f7620-146">[Get-csbackupserviceconfiguration](https://technet.microsoft.com/library/JJ205087(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="f7620-146">[Get-CsBackupServiceConfiguration](https://technet.microsoft.com/library/JJ205087(v=OCS.15))</span></span>

  - <span data-ttu-id="f7620-147">[Get-csbackupserviceconfiguration](https://technet.microsoft.com/library/JJ204903(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="f7620-147">[Remove-CsBackupServiceConfiguration](https://technet.microsoft.com/library/JJ204903(v=OCS.15))</span></span>

  - <span data-ttu-id="f7620-148">[Get-csbackupserviceconfiguration](https://technet.microsoft.com/library/JJ205006(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="f7620-148">[Set-CsBackupServiceConfiguration](https://technet.microsoft.com/library/JJ205006(v=OCS.15))</span></span>

<!-- end list -->

  - <span data-ttu-id="f7620-149">[Get-csbackupservicestatus](https://technet.microsoft.com/library/JJ205032(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="f7620-149">[Get-CsBackupServiceStatus](https://technet.microsoft.com/library/JJ205032(v=OCS.15))</span></span>

<!-- end list -->

  - <span data-ttu-id="f7620-150">[Invoke-csbackupservicesync](https://technet.microsoft.com/library/JJ205374(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="f7620-150">[Invoke-CsBackupServiceSync](https://technet.microsoft.com/library/JJ205374(v=OCS.15))</span></span>

<!-- end list -->

  - <span data-ttu-id="f7620-151">[デバッグ-Csintrアポストロフィ Olreplication](https://technet.microsoft.com/library/JJ205103(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="f7620-151">[Debug-CsIntraPoolReplication](https://technet.microsoft.com/library/JJ205103(v=OCS.15))</span></span>

<!-- end list -->

  - <span data-ttu-id="f7620-152">[バックアップ-CsPool](https://technet.microsoft.com/library/JJ204955(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="f7620-152">[Backup-CsPool](https://technet.microsoft.com/library/JJ204955(v=OCS.15))</span></span>

<!-- end list -->

  - <span data-ttu-id="f7620-153">[Get-cspoolbackuprelationship](https://technet.microsoft.com/library/JJ204745(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="f7620-153">[Get-CsPoolBackupRelationship](https://technet.microsoft.com/library/JJ204745(v=OCS.15))</span></span>

<!-- end list -->

  - <span data-ttu-id="f7620-154">[Get-cspoolfabricstate](https://technet.microsoft.com/library/JJ619188(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="f7620-154">[Get-CsPoolFabricState](https://technet.microsoft.com/library/JJ619188(v=OCS.15))</span></span>

<!-- end list -->

  - <span data-ttu-id="f7620-155">[Invoke-cspoolfailback](https://technet.microsoft.com/library/JJ204873(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="f7620-155">[Invoke-CsPoolFailBack](https://technet.microsoft.com/library/JJ204873(v=OCS.15))</span></span>

<!-- end list -->

  - <span data-ttu-id="f7620-156">[Initialize-cspoolfailover](https://technet.microsoft.com/library/JJ205189(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="f7620-156">[Invoke-CsPoolFailOver](https://technet.microsoft.com/library/JJ205189(v=OCS.15))</span></span>

<!-- end list -->

  - <span data-ttu-id="f7620-157">[Get-cspoolupgradereadinessstate 戻し](https://technet.microsoft.com/library/JJ204689(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="f7620-157">[Get-CsPoolUpgradeReadinessState](https://technet.microsoft.com/library/JJ204689(v=OCS.15))</span></span>

<!-- end list -->

  - <span data-ttu-id="f7620-158">[Invoke-csstorageserviceflush](https://technet.microsoft.com/library/JJ619175(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="f7620-158">[Invoke-CsStorageServiceFlush](https://technet.microsoft.com/library/JJ619175(v=OCS.15))</span></span>

<!-- end list -->

  - <span data-ttu-id="f7620-159">[同期-CsUserData](https://technet.microsoft.com/library/JJ205242(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="f7620-159">[Sync-CsUserData](https://technet.microsoft.com/library/JJ205242(v=OCS.15))</span></span>

<!-- end list -->

  - <span data-ttu-id="f7620-160">[-CsUserStoreBackupData を削除する](https://technet.microsoft.com/library/JJ205003(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="f7620-160">[Remove-CsUserStoreBackupData](https://technet.microsoft.com/library/JJ205003(v=OCS.15))</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="f7620-161">関連項目</span><span class="sxs-lookup"><span data-stu-id="f7620-161">See Also</span></span>


[<span data-ttu-id="f7620-162">Lync Server PowerShell ブログ</span><span class="sxs-lookup"><span data-stu-id="f7620-162">Lync Server PowerShell Blog</span></span>](http://go.microsoft.com/fwlink/p/?linkid=203150)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

