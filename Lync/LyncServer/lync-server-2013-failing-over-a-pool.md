---
title: 'Lync Server 2013: プールのフェールオーバー'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Failing over a pool
ms:assetid: 10b13732-bc80-4cb2-a71c-56b1d6cb5bbb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204678(v=OCS.15)
ms:contentKeyID: 48183432
ms.date: 10/10/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 93f6aadd6cde7f09d7c6bdde118055cde8a56de5
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/21/2020
ms.locfileid: "42204269"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="failing-over-a-pool-in-lync-server-2013"></a>Lync Server 2013 でのプールのフェールオーバー

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2014-10-10_

1 つのフロントエンド プールで障害が発生し、フェールオーバーが必要な場合は、次の手順を使用します。この手順では、Datacenter1 に Pool1 があり、Pool1 で障害が発生した状況を想定しています。フェールオーバー先は Datacenter2 の Pool2 です。

プールフェールオーバーの作業のほとんどは、必要な場合に中央管理ストアをフェールオーバーすることになります。 これは、プールのユーザーがフェールオーバーしたときに中央管理ストアが機能する必要があるため、重要です。

また、フロントエンド プールで障害が発生しているが、そのサイトのエッジ プールはまだ実行されている場合は、障害が発生しているプールをエッジ プールで次ホップ プールとして使用するかどうかを把握する必要があります。次ホップ プールとして使用する場合は、障害が発生しているフロントエンド プールをフェールオーバーする前に、エッジ プールを変更して別のフロントエンド プールを使用する必要があります。次ホップの設定を変更する方法は、エッジでエッジ プールと同じサイトのプールを使用するか、別のサイトのプールを使用するかによって異なります。

**同じサイトの次ホップ プールを使用するようにエッジ プールを設定するには**

1.  トポロジビルダーを開き、変更する必要があるエッジプールを右クリックして、[**プロパティの編集**] をクリックします。

2.  [**次ホップ**] をクリックします。[**次ホップ プール**] の一覧で、次ホップ プールとして使用するプールを選択します。

3.  [**OK**] をクリックし、変更を公開します。

**別のサイトの次ホップ プールを使用するようにエッジ プールを設定するには**

1.  [Lync Server 管理シェル] ウィンドウを開き、次のコマンドレットを入力します。
    
        Set-CsEdgeServer -Identity EdgeServer:<Edge Server pool FQDN> -Registrar Registrar:<NextHopPoolFQDN>

**障害が発生したプールをフェールオーバーするには**

1.  Pool2 のフロントエンドサーバーに次のコマンドレットを入力することによって、中央管理サーバーのホストであるプールを検索します。
    
        Invoke-CsManagementServerFailover -Whatif
    
    このコマンドレットの結果は、現在中央管理サーバーをホストしているプールを示しています。 この手順の残りの部分では、このプールを CMS\_プールと呼びます。

2.  トポロジビルダーを使用して、CMS\_プールで実行されている Lync Server のバージョンを検索します。 Lync Server 2013 を実行している場合は、次のコマンドレットを使用して、プール1のバックアッププールを検索します。
    
        Get-CsPoolBackupRelationship -PoolFQDN <CMS_Pool FQDN>
    
    バックアップ\_プールをバックアッププールとして使用します。

3.  次のコマンドレットを使用して、中央管理ストアの状態を確認します。
    
        Get-CsManagementStoreReplicationStatus -CentralManagementStoreStatus 
    
    このコマンドレットでは、ActiveMasterFQDN と ActiveFileTransferAgents の両方が CMS\_プールの FQDN を指していることを示しています。 これらが空の場合は、中央管理サーバーを使用できないので、フェールオーバーする必要があります。

4.  中央管理ストアが使用できない場合、または中央管理ストアが Pool1 (つまり、障害が発生したプール) 上で実行されている場合は、プールをフェールオーバーする前に中央管理サーバーをフェールオーバーする必要があります。 Lync Server 2013 を実行しているプールでホストされていた中央管理サーバーをフェールオーバーする必要がある場合は、この手順の手順5でコマンドレットを使用します。 Lync Server 2010 を実行しているプールでホストされていた中央管理サーバーをフェールオーバーする必要がある場合は、この手順の手順6でコマンドレットを使用します。 中央管理サーバーをフェールオーバーする必要がない場合は、この手順の手順7に進みます。

5.  Lync Server 2013 を実行しているプールの中央管理ストアをフェールオーバーするには、次の手順を実行します。
    
      - 最初に、次のように入力し\_て、バックアッププールのどのバックエンドサーバーが中央管理ストアのプリンシパルインスタンスを実行するかを確認します。
        
            Get-CsDatabaseMirrorState -DatabaseType Centralmgmt -PoolFqdn <Backup_Pool Fqdn>
    
      - バックアップ\_プールのプライマリバックエンドサーバーがプリンシパルの場合は、次のように入力します。
        
            Invoke-CSManagementServerFailover -BackupSQLServerFqdn <Backup_Pool Primary BackEnd Server FQDN> -BackupSQLInstanceName <Backup_Pool Primary SQL Instance Name>
        
        バックアップ\_プールのミラーバックエンドサーバーがプリンシパルの場合は、次のように入力します。
        
            Invoke-CSManagementServerFailover -MirrorSQLServerFqdn <Backup_Pool Mirror BackEnd Server FQDN> -MirrorSQLInstanceName <Backup_Pool Mirror SQL Instance Name>
    
      - 中央管理サーバーのフェールオーバーが完了していることを確認します。 次のように入力します。
        
            Get-CsManagementStoreReplicationStatus -CentralManagementStoreStatus 
        
        ActiveMasterFQDN と ActiveFileTransferAgents の両方がバックアップ\_プールの FQDN を指していることを確認してください。
    
      - 最後に、次のように入力して、すべてのフロントエンドサーバーのレプリカの状態を確認します。
        
            Get-CsManagementStoreReplicationStatus 
        
        すべてのレプリカの値が True であることを確認します。
        
        手順 7. に進みます。

6.  中央管理ストアをバックアップ\_プールのバックエンドサーバーにインストールします。
    
      - 最初に、次のコマンドを実行します。
        
        ```PowerShell 
        Install-CsDatabase -CentralManagementDatabase -Clean -SqlServerFqdn <Backup_Pool Back End Server FQDN> -SqlInstanceName rtc  
        ```
    
      - バックアップ\_プールのフロントエンドサーバーの1つで次のコマンドを実行して、中央管理ストアの移動を強制します。
        
            Move-CsManagementServer -ConfigurationFileName c:\CsConfigurationFile.zip -LisConfigurationFileName c:\CsLisConfigurationFile.zip -Force 
    
      - 移動が完了したことを検証します。
        
            Get-CsManagementStoreReplicationStatus -CentralManagementStoreStatus 
        
        ActiveMasterFQDN と ActiveFileTransferAgents の両方がバックアップ\_プールの FQDN を指していることを確認してください。
    
      - すべてのフロントエンド サーバーのレプリカの状態を確認するために、次のように入力します。
        
            Get-CsManagementStoreReplicationStatus 
        
        すべてのレプリカの値が True であることを確認します。
    
      - 中央管理サーバーサービスをバックアップ\_プール内の残りのフロントエンドサーバーにインストールします。 これを行うには、すべてのフロントエンドサーバー上で次のコマンドを実行します。ただし、この手順の最初に中央管理ストアを強制的に移動するときに使用したものを除きます。
        
            Bootstrapper /Setup 

7.  Lync Server 管理シェルウィンドウで次のコマンドレットを実行して、Pool1 から Pool2 にユーザーをフェールオーバーします。
    
        Invoke-CsPoolFailover -PoolFQDN <Pool1 FQDN> -DisasterMode -Verbose
    
    中央管理ストアの状態を確認するために、この手順の前の部分で説明した手順がユニバーサルではないため、中央管理ストアがまだ完全にフェールオーバーされていないため、このコマンドレットが失敗する可能性があります。 この場合は、表示されるエラーメッセージに基づいて中央管理ストアを修正してから、このコマンドレットを再度実行する必要があります。
    
    次のエラー メッセージが表示される場合は、プールをフェールオーバーする前に、このサイトのエッジ プールを変更して別のプールを次ホップとして使用する必要があります。詳細については、このトピックの冒頭に掲載される手順を参照してください。
    
        Invoke-CsPoolFailOver : This Front-end pool "pool1.contoso.com" is specified in
        topology as the next hop for the Edge server. Failing over this pool may cause External
        access/Federation/Split-domain/XMPP features to stop working. Please use Topology Builder to
        change the Edge internal next hop setting to point to a different Front-end pool,  before you
        proceed.

</div>

<span> </span>

</div>

</div>

</div>

