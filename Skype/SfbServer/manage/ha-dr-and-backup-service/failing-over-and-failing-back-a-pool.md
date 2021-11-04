---
title: プールのフェール オーバーおよびフェール バック
ms.reviewer: ''
author: cichur
ms.author: v-mahoffman
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
description: .
ms.openlocfilehash: a9f4296ce122cdb539cae4d1f3cb7ef14262efc7
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/04/2021
ms.locfileid: "60750326"
---
# <a name="failing-over-and-failing-back-a-pool-in-skype-for-business-server"></a>サーバー内のプールのフェールオーバーとフェールバックSkype for Business Server

単一の Front-End プールが失敗し、失敗する必要がある場合、または障害が発生したプールがオンラインに戻り、展開を通常の作業状態に復元する必要がある場合は、次の手順を使用します。 Skype for Business フェデレーションまたは XMPP フェデレーションに使用するエッジ プールをフェールオーバーしてフェールバックする方法、または Front-End プールに関連付けられているエッジ プールを変更する方法について説明します。

- [フロントエンド プールのフェールオーバー](#fail-over-a-front-end-pool)
- [プールのフェールバック](#fail-back-a-pool)
- [フェデレーションに使用されるエッジ プールをSkype for Business Serverする](#fail-over-the-edge-pool-used-for-skype-for-business-server-federation)
- [サーバー内の XMPP フェデレーションに使用されるエッジ プールをSkype for Business Server](#fail-over-the-edge-pool-used-for-xmpp-federation-in-skype-for-business-server)
- [フェデレーションまたは XMPP フェデレーションで使用Skype for Business Serverエッジ プールをフェールバックする](#fail-back-the-edge-pool-used-for-skype-for-business-server-federation-or-xmpp-federation)
- [フロントエンド プールに関連付けられているエッジ プールを変更する](#change-the-edge-pool-associated-with-a-front-end-pool)

## <a name="fail-over-a-front-end-pool"></a>プールをFront-Endする

データセンター 1 には Pool1 が含まれているので、Pool1 は失敗しました。 データセンター 2 にある Pool2 にフェールオーバーしています。

プールフェールオーバーの作業の大部分は、必要に応じて中央管理ストアをフェールオーバーする必要があります。 サーバーの全体管理ストアは、プールのユーザーが失敗した場合に機能している必要があります。

サーバー プールFront-Endが失敗しても、そのサイトのエッジ プールがまだ実行されている場合は、エッジ プールが障害が発生したプールを次ホップ プールとして使用するかどうかを知る必要があります。 失敗した場合は、障害が発生したサーバー プールをFront-End前に、エッジ プールを変更して別の Front-Endする必要があります。 次ホップの設定を変更する方法は、エッジでエッジ プールと同じサイトのプールを使用するか、別のサイトのプールを使用するかによって異なります。

**同じサイトで次ホップ プールを使用するエッジ プールを設定するには**

1. トポロジ ビルダーを開き、変更する必要があるエッジ プールを右クリックし、[プロパティの編集] **を選択します**。

2. [次 **ホップ] を選択します**。 [次ホップ **プール:] リスト** から、次ホップ プールとして機能するプールを選択します。

3. **[OK] を** 選択し、変更を発行します。

**別のサイトで次ホップ プールを使用するエッジ プールを設定するには**

1. [管理シェルSkype for Business Server開き、次のコマンドレットを入力します。

    ```powershell
    Set-CsEdgeServer -Identity EdgeServer:<Edge Server pool FQDN> -Registrar Registrar:<NextHopPoolFQDN>
    ```

**障害でプールをフェールオーバーする**

1. Pool2 のサーバーで次のコマンドレットを入力して、サーバーの全体管理サーバーFront-End見つける。

    ```powershell
    Invoke-CsManagementServerFailover -Whatif
    ```

    このコマンドレットの結果は、現在サーバーの全体管理サーバーをホストしているプールを示しています。 この手順の残りの部分では、このプールは CMS プールと呼 \_ ばれる。

2. トポロジ ビルダーを使用して、CMS プールでSkype for Business Serverバージョンを検索 \_ します。 このコマンドレットを実行しているSkype for Business Server、次のコマンドレットを使用してプール 1 のバックアップ プールを検索します。

    ```powershell
    Get-CsPoolBackupRelationship -PoolFQDN <CMS_Pool FQDN>
    ```

    バックアップ プール \_ をバックアップ プールに設定します。

3. 次のコマンドレットを使用して、サーバーの全体管理ストアの状態を確認します。

    ```powershell
    Get-CsManagementStoreReplicationStatus -CentralManagementStoreStatus
    ```

    このコマンドレットは、ActiveMasterFQDN と ActiveFileTransferAgents の両方が CMS プールの FQDN を指している必要 \_ があります。 サーバーが空の場合は、サーバーの全体管理サーバーを使用できないので、サーバーをフェールオーバーする必要があります。

4.  サーバーの全体管理ストアが使用できない場合、またはサーバーの全体管理ストアが Pool1 で実行されている場合 (つまり、失敗したプール) 場合は、プールをフェールオーバーする前に、サーバーの全体管理サーバーをフェールオーバーする必要があります。 サーバーを実行しているプールでホストされたサーバーの全体管理サーバーをSkype for Business Serverする必要がある場合は、この手順の手順 5 のコマンドレットを使用します。 サーバーの全体管理サーバーをフェールオーバーする必要がない場合は、この手順の手順 7 に進みます。

5.  サーバーを実行しているプールの中央管理ストアをSkype for Business Server、次の手順を実行します。

    1. 最初に、バックアップ プールBack-Endサーバーが中央管理ストアのプリンシパル インスタンスを実行する場合は、次 \_ のように入力します。

        ```powershell
        Get-CsDatabaseMirrorState -DatabaseType Centralmgmt -PoolFqdn <Backup_Pool Fqdn>
        ```
    
    1. バックアップ プールのプライマリ Back-Endサーバーが \_ プリンシパルの場合は、次の種類を入力します。

        ```powershell        
        Invoke-CSManagementServerFailover -BackupSQLServerFqdn <Backup_Pool Primary BackEnd Server FQDN> -BackupSQLInstanceName <Backup_Pool Primary SQL Instance Name>
        ```
        
    1. バックアップ プールのサーバーBack-Endがプリンシパルの場合 \_ は、次の種類を入力します。
    
        ```powershell
        Invoke-CSManagementServerFailover -MirrorSQLServerFqdn <Backup_Pool Mirror BackEnd Server FQDN> -MirrorSQLInstanceName <Backup_Pool Mirror SQL Instance Name>
        ```
    
    1. サーバーの全体管理サーバーのフェールオーバーが完了したと確認します。 次のコマンドを入力します。
    
        ```powershell    
        Get-CsManagementStoreReplicationStatus -CentralManagementStoreStatus
        ```
        
        ActiveMasterFQDN と ActiveFileTransferAgents の両方がバックアップ プールの FQDN を指しているのを確認 \_ します。
    
    1. 最後に、次のように入力して、Front-Endサーバーのレプリカの状態を確認します。
        
        ```powershell
        Get-CsManagementStoreReplicationStatus 
        ```
        
        すべてのレプリカの値が True であることを確認します。
        
        手順 7. に進みます。

6.  バックアップ プールのバック エンド サーバーに中央管理ストアをインストール \_ します。
    
    1. 最初に、次のコマンドを実行します。

        ```powershell
        Install-CsDatabase -CentralManagementDatabase -Clean -SqlServerFqdn <Backup_Pool Back End Server FQDN> -SqlInstanceName rtc  
        ```
    
    1. バックアップ プールのフロント エンド サーバーの 1 つで次のコマンドを実行して、中央管理ストア \_ を強制的に移動します。

        ```powershell
        Move-CsManagementServer -ConfigurationFileName c:\CsConfigurationFile.zip -LisConfigurationFileName c:\CsLisConfigurationFile.zip -Force
        ```
    
    1. 移動が完了したことを検証します。

        ```powershell
        Get-CsManagementStoreReplicationStatus -CentralManagementStoreStatus
        ```
        
        ActiveMasterFQDN と ActiveFileTransferAgents の両方がバックアップ プールの FQDN を指しているのを確認 \_ します。
    
    1. すべてのフロントエンド サーバーのレプリカの状態を確認するために、次のように入力します。

        ```powershell
        Get-CsManagementStoreReplicationStatus
        ```
        
        すべてのレプリカの値が True であることを確認します。
    
    1. バックアップ プールのフロント エンド サーバーの残りの部分に、サーバーの全体管理サーバー サービスをインストール \_ します。 これを行うには、この手順の前にサーバーの全体管理ストアを移動する場合に使用したコマンドを除き、すべてのフロントエンド サーバーで次のコマンドを実行します。

        ```console
        Bootstrapper /Setup
        ```

7.  [管理シェル] ウィンドウで次のコマンドレットを実行して、Pool1 から Pool2 にSkype for Business Serverします。

    ```powershell
    Invoke-CsPoolFailover -PoolFQDN <Pool1 FQDN> -DisasterMode -Verbose
    ```
    
    この手順の前の部分で行った中央管理ストアの状態を確認する手順は汎用的ではないので、サーバーの全体管理ストアがまだ完全に失敗していないので、このコマンドレットが失敗する可能性があります。 この場合は、表示されるエラー メッセージに基づいてサーバーの全体管理ストアを修正し、このコマンドレットを再度実行する必要があります。
    
    次のエラー メッセージが表示される場合は、プールをフェールオーバーする前に、このサイトのエッジ プールを変更して別のプールを次ホップとして使用する必要があります。詳細については、このトピックの冒頭に掲載される手順を参照してください。
    
    ```console
    Invoke-CsPoolFailOver : This Front-end pool "pool1.contoso.com" is specified in
    topology as the next hop for the Edge server. Failing over this pool may cause External
    access/Federation/Split-domain/XMPP features to stop working. Please use Topology Builder to
    change the Edge internal next hop setting to point to a different Front-end pool,  before you
    proceed.
    ```


## <a name="fail-back-a-pool"></a>プールのフェールバック

障害が起きたプール (この例では Pool1) がオンラインに戻ったら、次の手順を実行して、展開を通常の状態に稼働状態に戻します。

フェールバック プロセスの完了には数分かかります。 参考までに、20,000 人のユーザーのプールには最大 60 分かかると予想されます。

次のコマンドレットを入力して、もともと Pool1 に属していて Pool2 にフェールオーバーされたユーザーをフェールバックします。

```powershell
Invoke-CsPoolFailback -PoolFQDN <Pool1 FQDN> -Verbose
```

それ以外の操作は必要ありません。 サーバーの全体管理サーバーに障害が発生した場合は、Pool2 に置き去りにできます。

## <a name="fail-over-the-edge-pool-used-for-skype-for-business-server-federation"></a>フェデレーションに使用されるエッジ プールをSkype for Business Serverする 

フェデレーションが構成されているエッジ Skype for Business Serverダウンした場合は、フェデレーションが動作するように別のエッジ プールを使用するようにフェデレーションを変更する必要があります。

1.  フロントエンド サーバーでトポロジ ビルダーを開きます。 [ **エッジ プール]** を展開し、現在フェデレーション用に構成されているエッジ サーバーまたはエッジ サーバー プールを右クリックします。 [**プロパティの編集**] をクリックします。

2.  [**全般**] の [**プロパティの編集**] で、[**このエッジ プールのフェデレーションの有効化 (ポート 5061)**] をオフにします。 **[OK]** を選択します。

3.  [ **エッジ プール]** を展開し、フェデレーションに使用するエッジ サーバーまたはエッジ サーバー プールを右クリックします。 [**プロパティの編集**] をクリックします。

4.  [**全般**] の [**プロパティの編集**] で、[**このエッジ プールのフェデレーションの有効化 (ポート 5061)**] をオンにします。 **[OK]** を選択します。

5.  [アクション **] を選択** し、[ **トポロジ] を選択し**、[発行] **を選択します**。 [トポロジの公開] **でメッセージが表示されたら、[** 次へ] を **選択します**。 発行が完了したら、[完了] を **選択します**。

6.  エッジ サーバーで、[展開] ウィザードSkype for Business Server開きます。 [**システムのインストールまたは更新Skype for Business Server]** を選択し、[セットアップ] または [コンポーネント **の削除Skype for Business Serverします**。 [もう **一度実行] を選択します**。

7.  **[次へ]** を選択します。 概要画面に、実行された処理が表示されます。 展開が完了したら、[ログの表示] **を選択して** 、使用可能なログ ファイルを表示します。 [ **完了] を** 選択して展開を完了します。
    
    障害が発生したエッジ プールを含むサイトに、実行中のフロント エンド サーバーが含まれている場合は、これらの Front-End プールの Web 会議サービスと音声ビデオ会議サービスを更新して、実行中のリモート サイトのエッジ プールを使用する必要があります。 

 ## <a name="fail-over-the-edge-pool-used-for-xmpp-federation-in-skype-for-business-server"></a>サーバー内の XMPP フェデレーションに使用されるエッジ プールをSkype for Business Server 

組織内に XMPP フェデレーションに使用するプールとして指定されたエッジ プールが 1 つあるとします。このプールがダウンした場合、XMPP フェデレーションを再び機能させるには、XMPP フェデレーションをフェールオーバーして別のエッジ プールを使用する必要があります。

エッジ プールを初めてインストールし、XMPP フェデレーションを有効にするときに、1 つのエッジ プールではなく、すべてのエッジ プールで XMPP フェデレーションの外部 DNS SRV レコードを設定することで障害復旧プロセスを簡素化できます。 これらの SRV レコードには、それぞれ異なる優先順位が設定されている必要があります。 すべての XMPP フェデレーション トラフィックは、優先順位が最も高い SRV レコードを使用してプールを通過します。 

次の手順では、EdgePool1 はプールであり、最初は XMPP フェデレーションをホストし、EdgePool2 は XMPP フェデレーションをホストするプールです。
### <a name="to-fail-over-the-edge-pool-used-for-xmpp-federation"></a>XMPP フェデレーションに使用するエッジ プールをフェールオーバーするには

1.  (現在ダウンしているエッジ プール以外に) 別のエッジ プールが展開されていない場合は、そのプールを展開します。 

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

## <a name="fail-back-the-edge-pool-used-for-skype-for-business-server-federation-or-xmpp-federation"></a>フェデレーションまたは XMPP フェデレーションで使用Skype for Business Serverエッジ プールをフェールバックする 

フェデレーションをホストするために使用した障害が発生したエッジ プールをオンラインに戻した後、この手順を使用して、Skype for Business Server フェデレーション ルートまたは XMPP フェデレーション ルートをフェールバックして、この復元されたエッジ プールを再度使用します。

1.  再び使用できるようになったエッジ プールで、エッジ サービスを開始します。

2.  復元されたエッジ サーバーを使用Skype for Business Serverフェデレーション ルートをフェールバックする場合は、次の手順を実行します。
    
    1. フロントエンド サーバーでトポロジ ビルダーを開きます。 [ **エッジ プール]** を展開し、現在フェデレーション用に構成されているエッジ サーバーまたはエッジ サーバー プールを右クリックします。 [**プロパティの編集**] をクリックします。
    
    1. [**全般**] の [**プロパティの編集**] で、[**このエッジ プールのフェデレーションの有効化 (ポート 5061)**] をオフにします。 **[OK]** を選択します。
    
    1. [ **エッジ プール] を** 展開し、フェデレーションに再度使用する元のエッジ サーバーまたはエッジ サーバー プールを右クリックします。 [**プロパティの編集**] をクリックします。
    
    1. [**全般**] の [**プロパティの編集**] で、[**このエッジ プールのフェデレーションの有効化 (ポート 5061)**] をオンにします。 **[OK]** を選択します。
    
    1. [アクション **] を選択** し、[ **トポロジ] を選択し**、[発行] **を選択します**。 [トポロジの公開] **でメッセージが表示されたら、[** 次へ] を **選択します**。 発行が完了したら、[完了] を **選択します**。
    
    1. エッジ サーバーで、[展開] ウィザードSkype for Business Server開きます。 [**システムのインストールまたは更新Skype for Business Server]** を選択し、[セットアップ] または [コンポーネント **の削除Skype for Business Server選択します**。 [もう **一度実行] を選択します**。
    
    1. **[次へ]** を選択します。 概要画面に、実行された処理が表示されます。 展開が完了したら、[ログの表示] **を選択して** 、使用可能なログ ファイルを表示します。 [ **完了] を** 選択して展開を完了します。

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

2.  プールを右クリックし、[プロパティの編集] **を選択します**。

3.  [**関連付け**] セクションの、[**エッジ プールの関連付け (メディア コンポーネント用) の**] 下のドロップダウン ボックスを使用して、このフロントエンド プールを関連付けるエッジ プールを選択します。

4.  **[OK]** を選択します。
