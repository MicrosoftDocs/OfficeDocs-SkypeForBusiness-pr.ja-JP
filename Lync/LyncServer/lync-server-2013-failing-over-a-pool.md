---
title: 'Lync Server 2013: プールのフェールオーバー'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Failing over a pool
ms:assetid: 10b13732-bc80-4cb2-a71c-56b1d6cb5bbb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204678(v=OCS.15)
ms:contentKeyID: 48183432
ms.date: 10/10/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 512d7bc09d40d7b99cc66970cdd2a5584030fea9
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34833183"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="failing-over-a-pool-in-lync-server-2013"></a>Lync Server 2013 でのプールのフェールオーバー

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2014-10-10_

1つのフロントエンドプールで障害が発生し、フェールオーバーを行う必要がある場合は、次の手順を使用します。 この手順では、Datacenter1 に Pool1 が含まれており、Pool1 は失敗しています。 Datacenter2 にある Pool2 にフェイルオーバーしています。

プールフェールオーバーのほとんどの作業には、必要に応じて、中央管理ストアのフェールオーバーが含まれています。 プールのユーザーがフェールオーバーされた場合は、中央管理ストアが機能している必要があるため、これは重要です。

さらに、フロントエンドプールに障害が発生しても、そのサイトの Edge プールがまだ実行されている場合は、Edge プールが、失敗したプールを次のホッププールとして使用するかどうかを確認する必要があります。 問題が発生した場合は、失敗したフロントエンドプールを使用するようにエッジプールを変更する必要があります。 次ホップの設定を変更する方法は、エッジプールと同じサイトのプールを使用するか、または別のサイトを使うかによって異なります。

**エッジプールで、同じサイトの次ホッププールを使用するように設定するには**

1.  トポロジビルダーを開き、変更する必要があるエッジプールを右クリックして、[**プロパティの編集**] をクリックします。

2.  [**次ホップ**] をクリックします。 [ **Next ホッププール:** ] ボックスの一覧で、次ホッププールとして機能するプールを選択します。

3.  [ **OK**] をクリックして、変更を公開します。

**別のサイトで次ホッププールを使用するようにエッジプールを設定するには**

1.  Lync Server 管理シェルウィンドウを開いて、次のコマンドレットを入力します。
    
        Set-CsEdgeServer -Identity EdgeServer:<Edge Server pool FQDN> -Registrar Registrar:<NextHopPoolFQDN>

**障害が発生したプールをフェイルオーバーするには**

1.  Pool2 のフロントエンドサーバーに次のコマンドレットを入力して、中央管理サーバーのホストとなるプールを見つけます。
    
        Invoke-CsManagementServerFailover -Whatif
    
    このコマンドレットの結果は、現在中央管理サーバーをホストしているプールを示します。 この手順の残りの部分では、このプールを CMS\_プールと呼びます。

2.  トポロジビルダーを使用して、CMS\_プールで実行されている Lync Server のバージョンを確認します。 Lync Server 2013 を実行している場合は、次のコマンドレットを使用して、Pool 1 のバックアッププールを検索します。
    
        Get-CsPoolBackupRelationship -PoolFQDN <CMS_Pool FQDN>
    
    バックアップ\_プールをバックアッププールにします。

3.  次のコマンドレットを使用して、サーバーの全体管理ストアの状態を確認します。
    
        Get-CsManagementStoreReplicationStatus -CentralManagementStoreStatus 
    
    このコマンドレットでは、ActiveMasterFQDN と ActiveFileTransferAgents の両方が CMS\_プールの FQDN を指していることを示しています。 空の場合は、サーバーの全体管理サーバーを利用できないため、フェールオーバーを行う必要があります。

4.  中央管理ストアを使用できない場合、または Pool1 で中央管理ストアが実行されている場合 (つまり、失敗したプール)、プールをフェールオーバーする前に、中央管理サーバーをフェールオーバーする必要があります。 Lync Server 2013 を実行しているプールでホストされていた中央管理サーバーをフェールオーバーする必要がある場合は、この手順の手順5のコマンドレットを使用します。 Lync Server 2010 を実行しているプールでホストされていた中央管理サーバーをフェールオーバーする必要がある場合は、この手順の手順6でコマンドレットを使用します。 サーバーの全体管理サーバーにフェールオーバーする必要がない場合は、手順7に進んでください。

5.  Lync Server 2013 を実行しているプールの中央管理ストアをフェールオーバーするには、次の操作を行います。
    
      - まず、次のように入力して\_、バックアッププールのどのバックエンドサーバーで中央管理ストアのプリンシパルインスタンスを実行するかを確認します。
        
            Get-CsDatabaseMirrorState -DatabaseType Centralmgmt -PoolFqdn <Backup_Pool Fqdn>
    
      - バックアップ\_プールのプライマリバックエンドサーバーがプリンシパルである場合は、次のように入力します。
        
            Invoke-CSManagementServerFailover -BackupSQLServerFqdn <Backup_Pool Primary BackEnd Server FQDN> -BackupSQLInstanceName <Backup_Pool Primary SQL Instance Name>
        
        バックアップ\_プールのミラーバックエンドサーバーがプリンシパルである場合は、次のように入力します。
        
            Invoke-CSManagementServerFailover -MirrorSQLServerFqdn <Backup_Pool Mirror BackEnd Server FQDN> -MirrorSQLInstanceName <Backup_Pool Mirror SQL Instance Name>
    
      - サーバーの全体のフェールオーバーが完了していることを確認します。 次のように入力します。
        
            Get-CsManagementStoreReplicationStatus -CentralManagementStoreStatus 
        
        ActiveMasterFQDN と ActiveFileTransferAgents の両方がバックアップ\_プールの FQDN を指していることを確認します。
    
      - 最後に、次のように入力して、すべてのフロントエンドサーバーのレプリカの状態を確認します。
        
            Get-CsManagementStoreReplicationStatus 
        
        すべてのレプリカの値が True であることを確認します。
        
        この手順の手順7に進みます。

6.  バックアップ\_プールのバックエンドサーバーに中央管理ストアをインストールします。
    
      - 最初に、次のコマンドを実行します。
        
        ``` 
        Install-CsDatabase -CentralManagementDatabase -Clean -SqlServerFqdn <Backup_Pool Back End Server FQDN> -SqlInstanceName rtc  
        ```
    
      - バックアップ\_プールのいずれかのフロントエンドサーバーで次のコマンドを実行して、中央管理ストアの移動を強制します。
        
            Move-CsManagementServer -ConfigurationFileName c:\CsConfigurationFile.zip -LisConfigurationFileName c:\CsLisConfigurationFile.zip -Force 
    
      - 移動が完了したことを確認します。
        
            Get-CsManagementStoreReplicationStatus -CentralManagementStoreStatus 
        
        ActiveMasterFQDN と ActiveFileTransferAgents の両方がバックアップ\_プールの FQDN を指していることを確認します。
    
      - 次のように入力して、すべてのフロントエンドサーバーのレプリカの状態を確認します。
        
            Get-CsManagementStoreReplicationStatus 
        
        すべてのレプリカの値が True であることを確認します。
    
      - 中央管理サーバーサービスを、バックアップ\_プールのフロントエンドサーバーの残りの部分にインストールします。 この操作を行うには、この手順の最初に中央管理ストアを強制するときに使用したものを除き、すべてのフロントエンドサーバーで次のコマンドを実行します。
        
            Bootstrapper /Setup 

7.  Lync Server 管理シェルウィンドウで次のコマンドレットを実行して、Pool1 から Pool2 にユーザーをフェールオーバーします。
    
        Invoke-CsPoolFailover -PoolFQDN <Pool1 FQDN> -DisasterMode -Verbose
    
    この手順の前の部分で実行した手順では、全体管理ストアの状態を確認する必要があるため、中央管理ストアはまだ完全にフェールオーバーしていないため、このコマンドレットは失敗する可能性があります。 この場合は、表示されるエラーメッセージに基づいて、中央管理ストアを修正し、このコマンドレットをもう一度実行する必要があります。
    
    次のエラーメッセージが表示された場合は、プールをフェールオーバーする前に、このサイトの Edge プールを別のホップとして使用するように変更する必要があります。 詳細については、このトピックの最初の手順を参照してください。
    
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

