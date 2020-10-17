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
ms.openlocfilehash: 5452ed1af7d59b690dfbbf4dd239474fd239ff40
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/16/2020
ms.locfileid: "48515354"
---
# <a name="infrastructure-and-deployment-cmdlets-in-lync-server-2013"></a>Lync Server 2013 のインフラストラクチャと展開のコマンドレット

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2012-10-09_

Microsoft Lync Server 2013 に含まれるインフラストラクチャと展開のコマンドレットは、製品の初期セットアップと展開に役立ちます。Lync Server を展開した後は、これらのコマンドレットを使用して、コンポーネントが期待どおりに動作しているかどうかを確認することができます。レプリケーションの設定を管理する。そして、Lync Server のトポロジ、ポリシー、および構成設定をバックアップおよび復元します。

<div>

## <a name="infrastructure-and-deployment-cmdlets"></a>インフラストラクチャおよび展開のコマンドレット

管理者は、ほとんどの場合、インフラストラクチャと展開の多くを直接呼び出す必要があります。 そのため、これらのコマンドレットは、セットアップまたはトポロジビルダーを実行するときに自動的に呼び出されます。 (1 つの大きな例外が、Lync Server のトポロジ、ポリシー、および構成設定のバックアップコピーを作成できる、 **エクスポート-CsConfiguration** コマンドレットである可能性があります)。ただし、必要に応じて、Lync Server 管理シェルまたはスクリプト内から、インフラストラクチャと展開のコマンドレットを実行することもできます。スクリプトを使用すると、特定のタスクを自動化できます。 以下に、インフラストラクチャと展開に直接関連するコマンドレットの一覧を示します。

**[Lync Server 2013 での Active Directory のコマンドレット](lync-server-2013-active-directory-cmdlets.md)**

  - <span></span>  
    [無効-CsAdDomain](https://technet.microsoft.com/library/Gg398785(v=OCS.15))

  - <span></span>  
    [Enable-CsAdDomain](https://technet.microsoft.com/library/Gg412764(v=OCS.15))

  - <span></span>  
    [取得-CsAdDomain](https://technet.microsoft.com/library/Gg398453(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [無効-CsAdForest](https://technet.microsoft.com/library/Gg398122(v=OCS.15))

  - <span></span>  
    [Enable-CsAdForest](https://technet.microsoft.com/library/Gg425713(v=OCS.15))

  - <span></span>  
    [取得-CsAdForest](https://technet.microsoft.com/library/Gg412995(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [取得-CsAdServerSchema](https://technet.microsoft.com/library/Gg413070(v=OCS.15))

  - <span></span>  
    [Install-CsAdServerSchema](https://technet.microsoft.com/library/Gg398681(v=OCS.15))

**[Lync Server 2013 のレプリケーションのコマンドレット](lync-server-2013-replication-cmdlets.md)**

  - <span></span>  
    [デバッグ-CsInterPoolReplication](https://technet.microsoft.com/library/JJ619185(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Invoke-csmanagementstorereplication](https://technet.microsoft.com/library/Gg413060(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Get-csmanagementstorereplicationstatus](https://technet.microsoft.com/library/Gg399052(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [を有効にする-CsReplica](https://technet.microsoft.com/library/Gg425965(v=OCS.15))

  - <span></span>  
    [テスト-CsReplica](https://technet.microsoft.com/library/JJ205289(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [-CsUserReplicatorConfiguration の取得](https://technet.microsoft.com/library/Gg398548(v=OCS.15))

  - <span></span>  
    [新しい-CsUserReplicatorConfiguration](https://technet.microsoft.com/library/Gg399059(v=OCS.15))

  - <span></span>  
    [-CsUserReplicatorConfiguration の削除](https://technet.microsoft.com/library/Gg425738(v=OCS.15))

  - <span></span>  
    [設定-CsUserReplicatorConfiguration](https://technet.microsoft.com/library/Gg398540(v=OCS.15))

**[トポロジのコマンドレット (Lync Server 2013)](lync-server-2013-topology-cmdlets.md)**

  - <span></span>  
    [取得-CsPool](https://technet.microsoft.com/library/Gg398992(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [取得-CsSite](https://technet.microsoft.com/library/Gg398185(v=OCS.15))

  - <span></span>  
    [設定-CsSite](https://technet.microsoft.com/library/Gg413023(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Enable-CsTopology](https://technet.microsoft.com/library/Gg398398(v=OCS.15))

  - <span></span>  
    [取得-CsTopology テクノロジー](https://technet.microsoft.com/library/Gg412824(v=OCS.15))

  - <span></span>  
    [発行-CsTopology テクノロジー](https://technet.microsoft.com/library/Gg398953(v=OCS.15))

  - <span></span>  
    [テスト-CsTopology テクノロジー](https://technet.microsoft.com/library/Gg398127(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [エクスポート-CsConfiguration](https://technet.microsoft.com/library/Gg398627(v=OCS.15))

  - <span></span>  
    [インポート-CsConfiguration](https://technet.microsoft.com/library/Gg398800(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Get-csserverversion](https://technet.microsoft.com/library/Gg398470(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [-CsComputer を無効にする](https://technet.microsoft.com/library/Gg399023(v=OCS.15))

  - <span></span>  
    [を有効にする-CsComputer](https://technet.microsoft.com/library/Gg412815(v=OCS.15))

  - <span></span>  
    [-CsComputer の取得](https://technet.microsoft.com/library/Gg425959(v=OCS.15))

  - <span></span>  
    [テスト-CsComputer](https://technet.microsoft.com/library/Gg398162(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Get-csnetworkinterface](https://technet.microsoft.com/library/Gg398121(v=OCS.15))

**[Lync Server 2013 のバックアップと高可用性のコマンドレット](lync-server-2013-backup-and-high-availability-cmdlets.md)**

  - [Get-csbackupserviceconfiguration](https://technet.microsoft.com/library/JJ205087(v=OCS.15))

  - [Get-csbackupserviceconfiguration](https://technet.microsoft.com/library/JJ204903(v=OCS.15))

  - [Get-csbackupserviceconfiguration](https://technet.microsoft.com/library/JJ205006(v=OCS.15))

<!-- end list -->

  - [Get-csbackupservicestatus](https://technet.microsoft.com/library/JJ205032(v=OCS.15))

<!-- end list -->

  - [Invoke-csbackupservicesync](https://technet.microsoft.com/library/JJ205374(v=OCS.15))

<!-- end list -->

  - [デバッグ-Csintrアポストロフィ Olreplication](https://technet.microsoft.com/library/JJ205103(v=OCS.15))

<!-- end list -->

  - [バックアップ-CsPool](https://technet.microsoft.com/library/JJ204955(v=OCS.15))

<!-- end list -->

  - [Get-cspoolbackuprelationship](https://technet.microsoft.com/library/JJ204745(v=OCS.15))

<!-- end list -->

  - [Get-cspoolfabricstate](https://technet.microsoft.com/library/JJ619188(v=OCS.15))

<!-- end list -->

  - [Invoke-cspoolfailback](https://technet.microsoft.com/library/JJ204873(v=OCS.15))

<!-- end list -->

  - [Initialize-cspoolfailover](https://technet.microsoft.com/library/JJ205189(v=OCS.15))

<!-- end list -->

  - [Get-cspoolupgradereadinessstate 戻し](https://technet.microsoft.com/library/JJ204689(v=OCS.15))

<!-- end list -->

  - [Invoke-csstorageserviceflush](https://technet.microsoft.com/library/JJ619175(v=OCS.15))

<!-- end list -->

  - [同期-CsUserData](https://technet.microsoft.com/library/JJ205242(v=OCS.15))

<!-- end list -->

  - [-CsUserStoreBackupData を削除する](https://technet.microsoft.com/library/JJ205003(v=OCS.15))

</div>

<div>

## <a name="see-also"></a>関連項目


[Lync Server PowerShell ブログ](https://go.microsoft.com/fwlink/p/?linkid=203150)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

