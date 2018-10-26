---
title: 'Lync Server 2013: プールのフェールオーバー'
TOCTitle: プールのフェールオーバー
ms:assetid: 10b13732-bc80-4cb2-a71c-56b1d6cb5bbb
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/JJ204678(v=OCS.15)
ms:contentKeyID: 48271294
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 でのプールのフェールオーバー

 

_**トピックの最終更新日:** 2014-10-10_

1 つのフロントエンド プールで障害が発生し、フェールオーバーが必要な場合は、次の手順を使用します。この手順では、Datacenter1 に Pool1 があり、Pool1 で障害が発生した状況を想定しています。フェールオーバー先は Datacenter2 の Pool2 です。

プールのフェールオーバーで行う操作の多くは、必要に応じて 中央管理ストアをフェールオーバーする作業です。プールのユーザーをフェールオーバーするときに 中央管理ストアが動作している必要があるため、この作業は重要です。

また、フロントエンド プールで障害が発生しているが、そのサイトのエッジ プールはまだ実行されている場合は、障害が発生しているプールをエッジ プールで次ホップ プールとして使用するかどうかを把握する必要があります。次ホップ プールとして使用する場合は、障害が発生しているフロントエンド プールをフェールオーバーする前に、エッジ プールを変更して別のフロントエンド プールを使用する必要があります。次ホップの設定を変更する方法は、エッジでエッジ プールと同じサイトのプールを使用するか、別のサイトのプールを使用するかによって異なります。

**同じサイトの次ホップ プールを使用するようにエッジ プールを設定するには**

1.  トポロジ ビルダーを開き、変更する必要があるエッジ プールを右クリックし、\[ **プロパティの編集** \] をクリックします。

2.  \[ **次ホップ** \] をクリックします。\[ **次ホップ プール** \] の一覧で、次ホップ プールとして使用するプールを選択します。

3.  \[ **OK** \] をクリックし、変更を公開します。

**別のサイトの次ホップ プールを使用するようにエッジ プールを設定するには**

1.  Lync Server 管理シェル ウィンドウを開き、次のコマンドレットを入力します。
    
        Set-CsEdgeServer -Identity EdgeServer:<Edge Server pool FQDN> -Registrar Registrar:<NextHopPoolFQDN>

**障害が発生したプールをフェールオーバーするには**

1.  どのプールが 中央管理サーバーのホストであるかを確認するために、Pool2 のフロントエンド サーバーで次のコマンドレットを入力します。
    
        Invoke-CsManagementServerFailover -Whatif
    
    このコマンドレットの結果、 中央管理サーバーを現在ホストしているプールが表示されます。以降の手順では、このプールを CMS\_Pool と呼びます。

2.  トポロジ ビルダーを使用して、CMS\_Pool で動作している Lync Server のバージョンを確認します。 Lync Server 2013 が動作している場合は、次のコマンドレットを使用して、Pool 1 のバックアップ プールを確認します。
    
        Get-CsPoolBackupRelationship -PoolFQDN <CMS_Pool FQDN>
    
    バックアップ プールは Backup\_Pool だったものとします。

3.  次のコマンドレットで 中央管理ストアの状態を確認します。
    
        Get-CsManagementStoreReplicationStatus -CentralManagementStoreStatus 
    
    このコマンドレットの結果、ActiveMasterFQDN と ActiveFileTransferAgents の両方が CMS\_Pool の FQDN を指していれば問題ありません。これらが空の場合は、 中央管理サーバーは使用不能な状態にあり、フェールオーバーが必要です。

4.  中央管理ストアが使用不能であるか、または 中央管理ストアが Pool1 (つまり障害が発生したプール) で動作していた場合は、プールをフェールオーバーする前に 中央管理サーバーをフェールオーバーする必要があります。 Lync Server 2013 が動作するプールでホストされていた 中央管理サーバーをフェールオーバーすることが必要な場合は、手順 5. のコマンドレットを使用します。 Lync Server 2010 が動作するプールでホストされていた 中央管理サーバーをフェールオーバーすることが必要な場合は、手順 6. のコマンドレットを使用します。 中央管理サーバーのフェールオーバーが必要ない場合は、手順 7. に進みます。

5.  Lync Server 2013 が動作するプールの 中央管理ストアをフェールオーバーするには、次の操作を行います。
    
      - まず、Backup\_Pool のどのバックエンド サーバーが 中央管理ストアのプリンシパル インスタンスを実行しているかを確認するために、次のように入力します。
        
            Get-CsDatabaseMirrorState -DatabaseType Centralmgmt -PoolFqdn <Backup_Pool Fqdn>
    
      - Backup\_Pool のプライマリ バックエンド サーバーがプリンシパルの場合は、次のように入力します。
        
            Invoke-CSManagementServerFailover -BackupSQLServerFqdn <Backup_Pool Primary BackEnd Server FQDN> -BackupSQLInstanceName <Backup_Pool Primary SQL Instance Name>
        
        Backup\_Pool のミラー バックエンド サーバーがプリンシパルの場合は、次のように入力します。
        
            Invoke-CSManagementServerFailover -MirrorSQLServerFqdn <Backup_Pool Mirror BackEnd Server FQDN> -MirrorSQLInstanceName <Backup_Pool Mirror SQL Instance Name>
    
      - 中央管理サーバーのフェールオーバーが完了したことを検証します。次のように入力します。
        
            Get-CsManagementStoreReplicationStatus -CentralManagementStoreStatus 
        
        ActiveMasterFQDN と ActiveFileTransferAgents の両方が Backup\_Pool の FQDN を指していることを確認します。
    
      - 最後に、すべての フロント エンド サーバーのレプリカの状態を確認するために、次のように入力します。
        
            Get-CsManagementStoreReplicationStatus 
        
        すべてのレプリカの値が True であることを確認します。
        
        手順 7. に進みます。

6.  Backup\_Pool のバックエンド サーバーに 中央管理ストアをインストールします。
    
      - 最初に、次のコマンドを実行します。
        
        ``` 
        Install-CsDatabase -CentralManagementDatabase -Clean -SqlServerFqdn <Backup_Pool Back End Server FQDN> -SqlInstanceName rtc  
        ```
    
      - Backup\_Pool のいずれかのフロントエンド サーバーで次のコマンドを実行して、 中央管理ストアを強制的に移動します。
        
            Move-CsManagementServer -ConfigurationFileName c:\CsConfigurationFile.zip -LisConfigurationFileName c:\CsLisConfigurationFile.zip -Force 
    
      - 移動が完了したことを検証します。
        
            Get-CsManagementStoreReplicationStatus -CentralManagementStoreStatus 
        
        ActiveMasterFQDN と ActiveFileTransferAgents の両方が Backup\_Pool の FQDN を指していることを確認します。
    
      - すべてのフロントエンド サーバーのレプリカの状態を確認するために、次のように入力します。
        
            Get-CsManagementStoreReplicationStatus 
        
        すべてのレプリカの値が True であることを確認します。
    
      - Backup\_Pool の残りのフロントエンド サーバーに 中央管理サーバー サービスをインストールします。それには、すべてのフロントエンド サーバーで次のコマンドを実行します。ただし、前の手順で 中央管理ストアの移動を強制するときに使用したフロントエンド サーバーは除きます。
        
            Bootstrapper /Setup 

7.  Pool1 から Pool2 にユーザーをフェールオーバーするために、 Lync Server 管理シェル ウィンドウで次のコマンドレットを実行します。
    
        Invoke-CsPoolFailover -PoolFQDN <Pool1 FQDN> -DisasterMode -Verbose
    
    手順の前半部分で 中央管理ストアの状態を確認するために行った操作は、あらゆる状況に適用できるものではなく、 中央管理ストアが完全にフェールオーバーしていないと、このコマンドレットはエラーになる可能性があります。その場合は、表示されるエラー メッセージに基づいて 中央管理ストアを修正したうえで、このコマンドレットを再度実行する必要があります。
    
    次のエラー メッセージが表示される場合は、プールをフェールオーバーする前に、このサイトのエッジ プールを変更して別のプールを次ホップとして使用する必要があります。詳細については、このトピックの冒頭に掲載される手順を参照してください。
    
        Invoke-CsPoolFailOver : This Front-end pool "pool1.contoso.com" is specified in
        topology as the next hop for the Edge server. Failing over this pool may cause External
        access/Federation/Split-domain/XMPP features to stop working. Please use Topology Builder to
        change the Edge internal next hop setting to point to a different Front-end pool,  before you
        proceed.

