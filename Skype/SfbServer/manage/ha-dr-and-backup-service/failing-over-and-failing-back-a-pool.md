---
title: プールのフェール オーバーおよびフェール バック
ms.reviewer: ''
author: SerdarSoysal
ms.author: serdars
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
description: .
ms.openlocfilehash: 0b1f79ff40584c82d6da603ede49004f3c0c8968
ms.sourcegitcommit: 296862e02b548f0212c9c70504e65b467d459cc3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/25/2022
ms.locfileid: "65675039"
---
# <a name="failing-over-and-failing-back-a-pool-in-skype-for-business-server"></a>Skype for Business Serverでプールをフェールオーバーしてフェールバックする

1 つのFront-End プールが失敗してフェールオーバーする必要がある場合、または障害が発生したプールがオンラインに戻り、デプロイを通常の動作状態に復元する必要がある場合は、次の手順を使用します。 Skype for Business フェデレーションまたは XMPP フェデレーションに使用されるエッジ プールをフェールオーバーしてフェールバックする方法、またはFront-End プールに関連付けられているエッジ プールを変更する方法について説明します。

- [フロントエンド プールをフェールオーバーする](#fail-over-a-front-end-pool)
- [プールをフェールバックする](#fail-back-a-pool)
- [Skype for Business Server フェデレーションに使用されるエッジ プールをフェールオーバーする](#fail-over-the-edge-pool-used-for-skype-for-business-server-federation)
- [Skype for Business Serverの XMPP フェデレーションに使用されるエッジ プールをフェールオーバーする](#fail-over-the-edge-pool-used-for-xmpp-federation-in-skype-for-business-server)
- [Skype for Business Server フェデレーションまたは XMPP フェデレーションに使用されるエッジ プールをフェールバックする](#fail-back-the-edge-pool-used-for-skype-for-business-server-federation-or-xmpp-federation)
- [フロントエンド プールに関連付けられているエッジ プールを変更する](#change-the-edge-pool-associated-with-a-front-end-pool)

## <a name="fail-over-a-front-end-pool"></a>Front-End プールをフェールオーバーする

Datacenter1 に Pool1 が含まれており、Pool1 が失敗しました。 Datacenter2 にある Pool2 にフェールオーバーします。

プール フェールオーバーのほとんどの作業では、必要に応じて中央管理ストアをフェールオーバーする必要があります。 中央管理ストアは、プールのユーザーがフェールオーバーされたときに機能している必要があります。

Front-End プールが失敗しても、そのサイトのエッジ プールがまだ実行されている場合は、エッジ プールが失敗したプールを次ホップ プールとして使用するかどうかを確認する必要があります。 その場合は、障害が発生したFront-End プールをフェールオーバーする前に、別のFront-End プールを使用するようにエッジ プールを変更する必要があります。 次ホップの設定を変更する方法は、エッジでエッジ プールと同じサイトのプールを使用するか、別のサイトのプールを使用するかによって異なります。

**同じサイトで次ホップ プールを使用するようにエッジ プールを設定するには**

1. トポロジ ビルダーを開き、変更する必要があるエッジ プールを右クリックし、[プロパティの **編集]** を選択します。

2. **[次ホップ**] を選択します。 **[次ホップ プール:** ] ボックスの一覧から、次ホップ プールとして機能するプールを選択します。

3. **[OK] を** 選択し、変更を発行します。

**別のサイトで次ホップ プールを使用するようにエッジ プールを設定するには**

1. Skype for Business Server管理シェル ウィンドウを開き、次のコマンドレットを入力します。

    ```powershell
    Set-CsEdgeServer -Identity EdgeServer:<Edge Server pool FQDN> -Registrar Registrar:<NextHopPoolFQDN>
    ```

**障害発生時にプールをフェールオーバーするには**

1. 中央管理サーバーのホスト プールを見つけるには、Pool2 のFront-End サーバーで次のコマンドレットを入力します。

    ```powershell
    Invoke-CsManagementServerFailover -Whatif
    ```

    このコマンドレットの結果は、現在中央管理サーバーをホストしているプールを示します。 この手順の残りの部分では、このプールは CMS\_プールと呼ばれます。

2. トポロジ ビルダーを使用して、CMS\_プールで実行されているSkype for Business Serverのバージョンを検索します。 Skype for Business Serverを実行している場合は、次のコマンドレットを使用してプール 1 のバックアップ プールを見つけます。

    ```powershell
    Get-CsPoolBackupRelationship -PoolFQDN <CMS_Pool FQDN>
    ```

    Backup\_ Pool をバックアップ プールにしましょう。

3. 次のコマンドレットを使用して、Central Management ストアの状態を確認します。

    ```powershell
    Get-CsManagementStoreReplicationStatus -CentralManagementStoreStatus
    ```

    このコマンドレットは、ActiveMasterFQDN と ActiveFileTransferAgents の両方が CMS\_プールの FQDN を指していることを示す必要があります。 空の場合は、中央管理サーバーを使用できないため、フェールオーバーする必要があります。

4.  中央管理ストアが使用できない場合、または中央管理ストアが Pool1 で実行されていた場合 (つまり、障害が発生したプール)、プールをフェールオーバーする前に中央管理サーバーをフェールオーバーする必要があります。 Skype for Business Serverを実行しているプールでホストされていた中央管理サーバーをフェールオーバーする必要がある場合は、この手順の手順 5. のコマンドレットを使用します。 中央管理サーバーをフェールオーバーする必要がない場合は、この手順の手順 7 に進んでください。

5.  Skype for Business Serverを実行しているプール上の Central Management ストアをフェールオーバーするには、次の操作を行います。

    1. まず、次のように入力して、central Management ストアのプリンシパル インスタンスを実行する Backup\_ Pool の Back-End サーバーを確認します。

        ```powershell
        Get-CsDatabaseMirrorState -DatabaseType Centralmgmt -PoolFqdn <Backup_Pool Fqdn>
        ```
    
    1. Backup Pool のプライマリ Back-End\_ サーバーがプリンシパルの場合は、次のように入力します。

        ```powershell        
        Invoke-CSManagementServerFailover -BackupSQLServerFqdn <Backup_Pool Primary BackEnd Server FQDN> -BackupSQLInstanceName <Backup_Pool Primary SQL Instance Name>
        ```
        
    1. Backup Pool のミラー Back-End\_ サーバーがプリンシパルの場合は、次のように入力します。
    
        ```powershell
        Invoke-CSManagementServerFailover -MirrorSQLServerFqdn <Backup_Pool Mirror BackEnd Server FQDN> -MirrorSQLInstanceName <Backup_Pool Mirror SQL Instance Name>
        ```
    
    1. 中央管理サーバーのフェールオーバーが完了したことを検証します。 次のコマンドを入力します。
    
        ```powershell    
        Get-CsManagementStoreReplicationStatus -CentralManagementStoreStatus
        ```
        
        ActiveMasterFQDN と ActiveFileTransferAgents の両方が、Backup\_ Pool の FQDN を指していることを確認します。
    
    1. 最後に、次のように入力して、すべてのFront-End サーバーのレプリカの状態を確認します。
        
        ```powershell
        Get-CsManagementStoreReplicationStatus 
        ```
        
        すべてのレプリカの値が True であることを確認します。
        
        手順 7. に進みます。

6.  Backup Pool のバックエンド サーバーに中央管理ストアを\_インストールします。
    
    1. 最初に、次のコマンドを実行します。

        ```powershell
        Install-CsDatabase -CentralManagementDatabase -Clean -SqlServerFqdn <Backup_Pool Back End Server FQDN> -SqlInstanceName rtc  
        ```
    
    1. Backup Pool のフロント エンド サーバーのいずれかで次のコマンドを\_実行して、Central Management ストアを強制的に移動します。

        ```powershell
        Move-CsManagementServer -ConfigurationFileName c:\CsConfigurationFile.zip -LisConfigurationFileName c:\CsLisConfigurationFile.zip -Force
        ```
    
    1. 移動が完了したことを検証します。

        ```powershell
        Get-CsManagementStoreReplicationStatus -CentralManagementStoreStatus
        ```
        
        ActiveMasterFQDN と ActiveFileTransferAgents の両方が、Backup\_ Pool の FQDN を指していることを確認します。
    
    1. すべてのフロントエンド サーバーのレプリカの状態を確認するために、次のように入力します。

        ```powershell
        Get-CsManagementStoreReplicationStatus
        ```
        
        すべてのレプリカの値が True であることを確認します。
    
    1. Backup Pool のフロントエンド サーバーの残りの部分に中央管理サーバー サービスを\_インストールします。 これを行うには、すべてのフロントエンド サーバーで次のコマンドを実行します。ただし、この手順の前に中央管理ストアを強制的に移動するときに使用したコマンドを除きます。

        ```console
        Bootstrapper /Setup
        ```

7.  Skype for Business Server管理シェル ウィンドウで次のコマンドレットを実行して、Pool1 から Pool2 にユーザーをフェールオーバーします。

    ```powershell
    Invoke-CsPoolFailover -PoolFQDN <Pool1 FQDN> -DisasterMode -Verbose
    ```
    
    中央管理ストアの状態を確認するためのこの手順の前の部分で実行した手順はユニバーサルではないため、Central Management ストアがまだ完全にフェールオーバーされていないため、このコマンドレットが失敗する可能性があります。 この場合は、表示されるエラー メッセージに基づいて Central Management ストアを修正し、このコマンドレットをもう一度実行する必要があります。
    
    次のエラー メッセージが表示される場合は、プールをフェールオーバーする前に、このサイトのエッジ プールを変更して別のプールを次ホップとして使用する必要があります。詳細については、このトピックの冒頭に掲載される手順を参照してください。
    
    ```console
    Invoke-CsPoolFailOver : This Front-end pool "pool1.contoso.com" is specified in
    topology as the next hop for the Edge server. Failing over this pool may cause External
    access/Federation/Split-domain/XMPP features to stop working. Please use Topology Builder to
    change the Edge internal next hop setting to point to a different Front-end pool,  before you
    proceed.
    ```


## <a name="fail-back-a-pool"></a>プールをフェールバックする

障害が起きたプール (この例では Pool1) がオンラインに戻ったら、次の手順を実行して、展開を通常の状態に稼働状態に戻します。

フェールバック プロセスが完了するまでに数分かかります。 参考までに、20,000 人のユーザーのプールには最大 60 分かかると予想されます。

次のコマンドレットを入力して、もともと Pool1 に属していて Pool2 にフェールオーバーされたユーザーをフェールバックします。

```powershell
Invoke-CsPoolFailback -PoolFQDN <Pool1 FQDN> -Verbose
```

それ以外の操作は必要ありません。 中央管理サーバーをフェールオーバーした場合は、プール 2 に残すことができます。

## <a name="fail-over-the-edge-pool-used-for-skype-for-business-server-federation"></a>Skype for Business Server フェデレーションに使用されるエッジ プールをフェールオーバーする 

フェデレーションを構成Skype for Business Serverエッジ プールがダウンした場合は、フェデレーションを機能させるために別のエッジ プールを使用するようにフェデレーションを変更する必要があります。

1.  フロントエンド サーバーでトポロジ ビルダーを開きます。 **エッジ プール** を展開し、フェデレーション用に現在構成されているエッジ サーバーまたはエッジ サーバー プールを右クリックします。 [**プロパティの編集**] をクリックします。

2.  [**全般**] の [**プロパティの編集**] で、[**このエッジ プールのフェデレーションの有効化 (ポート 5061)**] をオフにします。 **[OK]** をクリックします。

3.  **[エッジ プール]** を展開し、フェデレーションに使用するエッジ サーバーまたはエッジ サーバー プールを右クリックします。 [**プロパティの編集**] をクリックします。

4.  [**全般**] の [**プロパティの編集**] で、[**このエッジ プールのフェデレーションの有効化 (ポート 5061)**] をオンにします。 **[OK]** をクリックします。

5.  **[アクション**] を選択 **し、[トポロジ**] を選択し、[発行] を選択 **します**。 **[トポロジの発行**] でメッセージが表示されたら、[**次へ**] を選択します。 発行が完了したら、[完了] を選択 **します**。

6.  エッジ サーバーで、Skype for Business Server展開ウィザードを開きます。 [**システムのインストールまたは更新] Skype for Business Server** 選択し、[**Skype for Business Server コンポーネントのセットアップまたは削除**] を選択します。 [ **再実行] を選択します**。

7.  **[次へ]** を選択します。 概要画面に、実行された処理が表示されます。 デプロイが完了したら、[ログの **表示** ] を選択して使用可能なログ ファイルを表示します。 [ **完了] を** 選択してデプロイを完了します。
    
    障害が発生したエッジ プールを含むサイトにまだ実行中のフロント エンド サーバーが含まれている場合は、実行中のリモート サイトでエッジ プールを使用するように、これらのFront-End プールで Web 会議サービスと A/V 会議サービスを更新する必要があります。 

 ## <a name="fail-over-the-edge-pool-used-for-xmpp-federation-in-skype-for-business-server"></a>Skype for Business Serverの XMPP フェデレーションに使用されるエッジ プールをフェールオーバーする 

組織内に XMPP フェデレーションに使用するプールとして指定されたエッジ プールが 1 つあるとします。このプールがダウンした場合、XMPP フェデレーションを再び機能させるには、XMPP フェデレーションをフェールオーバーして別のエッジ プールを使用する必要があります。

エッジ プールを初めてインストールし、XMPP フェデレーションを有効にするときに、1 つのエッジ プールではなく、すべてのエッジ プールで XMPP フェデレーションの外部 DNS SRV レコードを設定することで障害復旧プロセスを簡素化できます。 これらの SRV レコードには、それぞれ異なる優先順位が設定されている必要があります。 すべての XMPP フェデレーション トラフィックは、優先順位が最も高い SRV レコードを使用してプールを通過します。 

次の手順では、EdgePool1 はもともと XMPP フェデレーションをホストしていたプールであり、EdgePool2 は XMPP フェデレーションをホストするプールです。
### <a name="to-fail-over-the-edge-pool-used-for-xmpp-federation"></a>XMPP フェデレーションに使用されるエッジ プールをフェールオーバーするには

1.  (現在ダウンしているエッジ プール以外に) 別のエッジ プールがまだデプロイされていない場合は、そのプールをデプロイします。 

2.  XMPP フェデレーションをホストする新しいエッジ プール (EdgePool2) の各エッジ サーバーで、次のコマンドレットを実行します。

    ```powershell
    Stop-CsWindowsService
    ```

3.  XMPP フェデレーション ルートを変更して EdgePool2 を指すようにするには、次のコマンドレットを実行します。

    ```powershell
    Set-CsSite Site2 -XmppExternalFederationRoute EdgeServer2.contoso.com
    ```
    
    この例で、Site2 は XMPP フェデレーション ルートをこれからホストするエッジ プールを含むサイトを表します。また、EdgeServer2.contoso.com はそのプール内のエッジ サーバーの FQDN です。

4.  外部 DNS サーバーで、XMPP フェデレーションの DNS A レコードを変更して、EdgeServer2.contoso.com を指すようにします。

5.  XMPP フェデレーションをホストする新しいエッジ プールに解決される、XMPP フェデレーションの DNS SRV レコードがまだない場合は、次の例に示すように、このレコードを追加する必要があります。この SRV レコードには、ポート値 5269 が含まれている必要があります。

    ```console
    _xmpp-server._tcp.contoso.com
    ```

6.  XMPP フェデレーションをホストする新しいエッジ プールで、ポート 5269 が外部に開いていることを確認します。

7.  XMPP フェデレーションをホストする新しいエッジ プール内のすべてのエッジ サーバーでサービスを開始します。

    ```powershell
    Start-CsWindowsService
    ```

## <a name="fail-back-the-edge-pool-used-for-skype-for-business-server-federation-or-xmpp-federation"></a>Skype for Business Server フェデレーションまたは XMPP フェデレーションに使用されるエッジ プールをフェールバックする 

フェデレーションのホストに使用されていた障害が発生したエッジ プールがオンラインに戻ったら、この手順を使用して、Skype for Business Serverフェデレーション ルートまたは XMPP フェデレーション ルートをフェールバックして、この復元されたエッジ プールを再度使用します。

1.  再び使用できるようになったエッジ プールで、エッジ サービスを開始します。

2.  復元されたエッジ サーバーを使用するためにSkype for Business Serverフェデレーション ルートをフェールバックする場合は、次の操作を行います。
    
    1. フロントエンド サーバーでトポロジ ビルダーを開きます。 **[エッジ プール**] を展開し、フェデレーション用に現在構成されているエッジ サーバーまたはエッジ サーバー プールを右クリックします。 [**プロパティの編集**] をクリックします。
    
    1. [**全般**] の [**プロパティの編集**] で、[**このエッジ プールのフェデレーションの有効化 (ポート 5061)**] をオフにします。 **[OK]** をクリックします。
    
    1. **[エッジ プール**] を展開し、フェデレーションにもう一度使用する元のエッジ サーバーまたはエッジ サーバー プールを右クリックします。 [**プロパティの編集**] をクリックします。
    
    1. [**全般**] の [**プロパティの編集**] で、[**このエッジ プールのフェデレーションの有効化 (ポート 5061)**] をオンにします。 **[OK]** をクリックします。
    
    1. **[アクション**] を選択 **し、[トポロジ**] を選択し、[発行] を選択 **します**。 **[トポロジの発行**] でメッセージが表示されたら、[**次へ**] を選択します。 発行が完了したら、[完了] を選択 **します**。
    
    1. エッジ サーバーで、Skype for Business Server展開ウィザードを開きます。 [**システムのインストールまたは更新] Skype for Business Server** 選択し、**Skype for Business Serverコンポーネントのセットアップまたは削除** を選択します。 [ **再実行] を選択します**。
    
    1. **[次へ]** を選択します。 概要画面に、実行された処理が表示されます。 デプロイが完了したら、[ログの **表示** ] を選択して使用可能なログ ファイルを表示します。 [ **完了] を** 選択してデプロイを完了します。

3.  復旧されたエッジ サーバーが使用されるように XMPP フェデレーション ルートをフェールバックするには以下を行います。
    
    1. 以下のコマンドレットを実行して、XMPP フェデレーション ルートが、XMPP フェデレーションをホストするようになるエッジ プール (この例では、EdgeServer1) を再び指すようにします。
  
        ```powershell
        Set-CsSite Site1 -XmppExternalFederationRoute EdgeServer1.contoso.com
        ```
        
        この例では、Site1 は XMPP フェデレーション ルートをホストするようになるエッジ プールを含むサイトです。EdgeServer1.contoso.com はそのプール内のエッジ サーバーの FQDN です。
    
    1. XMPP フェデレーションをホストするようになるエッジ プールに解決される、XMPP フェデレーション用の DNS SRV レコードがまだない場合は、以下の例のようにそれを追加する必要があります。この SRV レコードはポート値が 5269 である必要があります。

        ```console
        _xmpp-server._tcp.contoso.com
        ```
    
    1. 外部 DNS サーバーで、XMPP フェデレーション用の DNS A レコードが EdgeServer2.contoso.com を指すように変更します。
    
    1. XMPP フェデレーションをホストするようになるエッジ プールがポート 5269 を外部にオープンしていることを確認します。

4.  障害発生後に復旧されたエッジ プールを含むサイトで、フロントエンド プールが実行を続けていた場合は、それらのフロントエンド プール上の Web 会議サービスおよび音声ビデオ会議サービスを更新して、ローカル サイトのエッジ プールが再び使用されるようにしてください。

5.  停止したエッジ プールと同じサイトでフロントエンド プールも停止していた場合は、Invoke–CsPoolFailback を使ってフロントエンド プールをフェールバックできます。


## <a name="change-the-edge-pool-associated-with-a-front-end-pool"></a>フロントエンド プールに関連付けられているエッジ プールを変更する

エッジ プールがダウンして同じサイトのフロントエンド プールがまだ実行中の場合、問題の発生したエッジ プールが復元されるまで、別のサイトのエッジ プールを使用するようにフロントエンド プールを設定する必要があります。

1.  トポロジ ビルダーで、変更するフロントエンド プールの名前を表示します。

2.  プールを右クリックし、[ **プロパティの編集]** を選択します。

3.  [**関連付け**] セクションの、[**エッジ プールの関連付け (メディア コンポーネント用) の**] 下のドロップダウン ボックスを使用して、このフロントエンド プールを関連付けるエッジ プールを選択します。

4.  **[OK]** をクリックします。
