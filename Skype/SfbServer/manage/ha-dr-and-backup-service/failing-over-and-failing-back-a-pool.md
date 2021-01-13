---
title: プールのフェール オーバーおよびフェール バック
ms.reviewer: ''
author: cichur
ms.author: v-cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: .
ms.openlocfilehash: 1ebd4e8110b8783c869530d95eda0646a895b88e
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49826567"
---
# <a name="failing-over-and-failing-back-a-pool-in-skype-for-business-server"></a>Skype for Business Server のプールのフェールオーバーとフェールバック 

単一のフロントエンド プールが障害を起こしてフェールオーバーする必要がある場合、または障害が発生したプールがオンラインに戻り、展開を通常の作業状態に復元する必要がある場合は、次の手順を使用します。 また、Skype for Business フェデレーションまたは XMPP フェデレーションに使用されるエッジ プールをフェールオーバーおよびフェールバックする方法、またはフロントエンド プールに関連付けられているエッジ プールを変更する方法も説明します。

- [フロントエンド プールのフェールオーバー](#fail-over-a-front-end-pool)
- [プールをフェールバックする](#fail-back-a-pool)
- [Skype for Business Server フェデレーションに使用されるエッジ プールをフェールオーバーする](#fail-over-the-edge-pool-used-for-skype-for-business-server-federation)
- [Skype for Business Server で XMPP フェデレーションに使用されるエッジ プールをフェールオーバーする](#fail-over-the-edge-pool-used-for-xmpp-federation-in-skype-for-business-server)
- [Skype for Business Server フェデレーションまたは XMPP フェデレーションに使用されるエッジ プールのフェールバック](#fail-back-the-edge-pool-used-for-skype-for-business-server-federation-or-xmpp-federation)
- [フロントエンド プールに関連付けられているエッジ プールを変更する](#change-the-edge-pool-associated-with-a-front-end-pool)

## <a name="fail-over-a-front-end-pool"></a>フロントエンド プールのフェールオーバー

この手順では、Datacenter1 に Pool1 があり、Pool1 で障害が発生した状況を想定しています。 フェールオーバー先は Datacenter2 の Pool2 です。

プールフェールオーバーの作業の大部分は、中央管理ストア (必要な場合) をフェールオーバーする必要があります。 これは、プールのユーザーがフェールオーバーするときに中央管理ストアが機能している必要があるから重要です。

また、フロントエンド プールで障害が発生しているが、そのサイトのエッジ プールはまだ実行されている場合は、障害が発生しているプールをエッジ プールで次ホップ プールとして使用するかどうかを把握する必要があります。次ホップ プールとして使用する場合は、障害が発生しているフロントエンド プールをフェールオーバーする前に、エッジ プールを変更して別のフロントエンド プールを使用する必要があります。次ホップの設定を変更する方法は、エッジでエッジ プールと同じサイトのプールを使用するか、別のサイトのプールを使用するかによって異なります。

**同じサイトで次ホップ プールを使用するエッジ プールを設定するには**

1.  トポロジ ビルダーを開き、変更する必要があるエッジ プールを右クリックし、[プロパティの編集] **をクリックします**。

2.  [**次ホップ**] をクリックします。[**次ホップ プール**] の一覧で、次ホップ プールとして使用するプールを選択します。

3.  [**OK**] をクリックし、変更を公開します。

**別のサイトで次ホップ プールを使用するエッジ プールを設定するには**

1.  Skype for Business Server 管理シェル ウィンドウを開き、次のコマンドレットを入力します。
    
        Set-CsEdgeServer -Identity EdgeServer:<Edge Server pool FQDN> -Registrar Registrar:<NextHopPoolFQDN>

**障害時にプールをフェールオーバーする**

1.  Pool2 のフロントエンド サーバーで次のコマンドレットを入力して、中央管理サーバーのホストであるプールを見つける。
    
        Invoke-CsManagementServerFailover -Whatif
    
    このコマンドレットの結果は、中央管理サーバーを現在ホストしているプールを示します。 この手順の残りの部分では、このプールを CMS プールと呼 \_ します。

2.  トポロジ ビルダーを使用して、CMS プールで実行されている Skype for Business Server のバージョンを検索 \_ します。 Skype for Business Server を実行している場合は、次のコマンドレットを使用してプール 1 のバックアップ プールを検索します。
    
        Get-CsPoolBackupRelationship -PoolFQDN <CMS_Pool FQDN>
    
    バックアップ プール \_ をバックアップ プールとします。

3.  次のコマンドレットを使用して、中央管理ストアの状態を確認します。
    
        Get-CsManagementStoreReplicationStatus -CentralManagementStoreStatus 
    
    このコマンドレットは、ActiveMasterFQDN と ActiveFileTransferAgents の両方が CMS プールの FQDN をポイントしている必要 \_ があります。 サーバーが空の場合、中央管理サーバーは使用できません。サーバーをフェールオーバーする必要があります。

4.  中央管理ストアが使用できない場合、または中央管理ストアが Pool1 で実行されている場合 (つまり、障害が発生したプール)、プールをフェールオーバーする前に中央管理サーバーをフェールオーバーする必要があります。 Skype for Business Server を実行しているプールでホストされている中央管理サーバーをフェールオーバーする必要がある場合は、この手順の手順 5 のコマンドレットを使用します。 中央管理サーバーをフェールオーバーする必要がない場合は、この手順の手順 7 に進みます。

5.  Skype for Business Server を実行しているプールで中央管理ストアをフェールオーバーするには、次の手順を実行します。
    
      - 最初に、次のように入力して、バックアップ プール内のどのバック エンド サーバーが中央管理ストアのプリンシパル インスタンスを実行 \_ しているのか確認します。
        
            Get-CsDatabaseMirrorState -DatabaseType Centralmgmt -PoolFqdn <Backup_Pool Fqdn>
    
      - バックアップ プールのプライマリ バック エンド サーバーがプリンシパルの場合 \_ は、次のコマンドを入力します。
        
            Invoke-CSManagementServerFailover -BackupSQLServerFqdn <Backup_Pool Primary BackEnd Server FQDN> -BackupSQLInstanceName <Backup_Pool Primary SQL Instance Name>
        
        バックアップ プール内のミラー のバック エンド サーバーがプリンシパル \_ である場合は、次のコマンドを入力します。
        
            Invoke-CSManagementServerFailover -MirrorSQLServerFqdn <Backup_Pool Mirror BackEnd Server FQDN> -MirrorSQLInstanceName <Backup_Pool Mirror SQL Instance Name>
    
      - 中央管理サーバーのフェールオーバーが完了したと確認します。 次のように入力します。
        
            Get-CsManagementStoreReplicationStatus -CentralManagementStoreStatus 
        
        ActiveMasterFQDN と ActiveFileTransferAgents の両方がバックアップ プールの FQDN をポイントしているのを確認 \_ します。
    
      - 最後に、次のように入力して、すべてのフロントエンド サーバーのレプリカの状態を確認します。
        
            Get-CsManagementStoreReplicationStatus 
        
        すべてのレプリカの値が True であることを確認します。
        
        手順 7. に進みます。

6.  バックアップ プールのバック エンド サーバーに中央管理ストアをインストール \_ します。
    
      - 最初に、次のコマンドを実行します。
        ```PowerShell
         
        Install-CsDatabase -CentralManagementDatabase -Clean -SqlServerFqdn <Backup_Pool Back End Server FQDN> -SqlInstanceName rtc  
        ```
    
      - バックアップ プールのフロントエンド サーバーの 1 つで次のコマンドを実行して、中央管理ストアの移動 \_ を強制します。
        
            Move-CsManagementServer -ConfigurationFileName c:\CsConfigurationFile.zip -LisConfigurationFileName c:\CsLisConfigurationFile.zip -Force 
    
      - 移動が完了したことを検証します。
        
            Get-CsManagementStoreReplicationStatus -CentralManagementStoreStatus 
        
        ActiveMasterFQDN と ActiveFileTransferAgents の両方がバックアップ プールの FQDN をポイントしているのを確認 \_ します。
    
      - すべてのフロントエンド サーバーのレプリカの状態を確認するために、次のように入力します。
        
            Get-CsManagementStoreReplicationStatus 
        
        すべてのレプリカの値が True であることを確認します。
    
      - バックアップ プール内の残りのフロントエンド サーバーに中央管理サーバー サービスをインストール \_ します。 これを行うには、すべてのフロントエンド サーバーで次のコマンドを実行します。ただし、この手順の前に中央管理ストアを移動する際に使用したコマンドを除く。
        
            Bootstrapper /Setup 

7.  Skype for Business Server 管理シェル ウィンドウで次のコマンドレットを実行して、Pool1 から Pool2 にユーザーをフェールオーバーします。
    
        Invoke-CsPoolFailover -PoolFQDN <Pool1 FQDN> -DisasterMode -Verbose
    
    中央管理ストアの状態を確認するためにこの手順の前の部分で実行した手順は汎用的ではないので、中央管理ストアがまだ完全にフェールオーバーしていないので、このコマンドレットが失敗する可能性があります。 この場合は、表示されるエラー メッセージに基づいて中央管理ストアを修正し、このコマンドレットを再度実行する必要があります。
    
    次のエラー メッセージが表示される場合は、プールをフェールオーバーする前に、このサイトのエッジ プールを変更して別のプールを次ホップとして使用する必要があります。詳細については、このトピックの冒頭に掲載される手順を参照してください。
    
        Invoke-CsPoolFailOver : This Front-end pool "pool1.contoso.com" is specified in
        topology as the next hop for the Edge server. Failing over this pool may cause External
        access/Federation/Split-domain/XMPP features to stop working. Please use Topology Builder to
        change the Edge internal next hop setting to point to a different Front-end pool,  before you
        proceed.


## <a name="fail-back-a-pool"></a>プールをフェールバックする

障害が起きたプール (この例では Pool1) がオンラインに戻ったら、次の手順を実行して、展開を通常の状態に稼働状態に戻します。

フェールバック プロセスは完了するまで数分かかることに注意してください。  参考として、20,000 名のユーザーのプールでは、最大 60 分かかることが予想されます。

次のコマンドレットを入力して、もともと Pool1 に属していて Pool2 にフェールオーバーされたユーザーをフェールバックします。
    
    Invoke-CsPoolFailback -PoolFQDN <Pool1 FQDN> -Verbose

それ以外の操作は必要ありません。 中央管理サーバーをフェールオーバーした場合は、Pool2 のままにしておく必要があります。

## <a name="fail-over-the-edge-pool-used-for-skype-for-business-server-federation"></a>Skype for Business Server フェデレーションに使用されるエッジ プールをフェールオーバーする 

Skype for Business Server フェデレーションが構成されているエッジ プールがダウンした場合は、フェデレーションが機能するために別のエッジ プールを使用するようにフェデレーションを変更する必要があります。

1.  フロントエンド サーバーでトポロジ ビルダーを開きます。 [ **エッジ プール]** を展開し、フェデレーション用に現在構成されているエッジ サーバーまたはエッジ サーバー プールを右クリックします。 [**プロパティの編集**] をクリックします。

2.  [**全般**] の [**プロパティの編集**] で、[**このエッジ プールのフェデレーションの有効化 (ポート 5061)**] をオフにします。 [**OK**] をクリックします。

3.  [ **エッジ プール]** を展開し、フェデレーションに使用するエッジ サーバーまたはエッジ サーバー プールを右クリックします。 [**プロパティの編集**] をクリックします。

4.  [**全般**] の [**プロパティの編集**] で、[**このエッジ プールのフェデレーションの有効化 (ポート 5061)**] をオンにします。[**OK**] を選択します。

5.  [**アクション**] をクリックし、[**トポロジ**]、[**公開**] の順に選択します。[**トポロジの公開**] で入力を求められたら、[**次へ**] をクリックします。公開の終了後、[**完了**] をクリックします。

6.  エッジ サーバーで、Skype for Business Server 展開ウィザードを開きます。 [Skype **for Business Server システムのインストールまたは更新] を** クリックし、[Skype for Business Server コンポーネントのセットアップまたは削除] **をクリックします**。 [**再実行**] をクリックします。

7.  [**次へ**] をクリックします。 概要画面に、実行されたアクションが表示されます。 展開が完了したら、[**ログの表示**] をクリックして、参照できるログ ファイルを表示します。 [**完了**] をクリックして、展開を完了します。
    
    失敗したエッジ プールを含むサイトにまだ稼動中のフロントエンド サーバーがある場合は、まだ稼動中のリモート サイトのエッジ プールを使用するように、これらのフロントエンド プールの Web 会議サービスおよび音声ビデオ会議サービスを更新する必要があります。 

 ## <a name="fail-over-the-edge-pool-used-for-xmpp-federation-in-skype-for-business-server"></a>Skype for Business Server で XMPP フェデレーションに使用されるエッジ プールをフェールオーバーする 

組織内に XMPP フェデレーションに使用するプールとして指定されたエッジ プールが 1 つあるとします。このプールがダウンした場合、XMPP フェデレーションを再び機能させるには、XMPP フェデレーションをフェールオーバーして別のエッジ プールを使用する必要があります。

エッジ プールを初めてインストールし、XMPP フェデレーションを有効にするときに、1 つのエッジ プールではなく、すべてのエッジ プールで XMPP フェデレーションの外部 DNS SRV レコードを設定することで障害復旧プロセスを簡素化できます。 これらの SRV レコードには、それぞれ異なる優先順位が設定されている必要があります。 すべての XMPP フェデレーション トラフィックは、優先順位が最も高い SRV レコードを使用してプールを通過します。 

次の手順では、EdgePool1 は XMPP フェデレーションをホストしていた元のプールを表し、EdgePool2 は XMPP フェデレーションをこれからホストするプールを表します。


### <a name="to-fail-over-the-edge-pool-used-for-xmpp-federation"></a>XMPP フェデレーションに使用するエッジ プールをフェールオーバーするには

1.  (現在ダウンしているエッジ プール以外の) 別のエッジ プールをまだ展開していない場合は、そのプールを展開します。 

2.  XMPP フェデレーションをホストする新しいエッジ プール (EdgePool2) の各エッジ サーバーで、次のコマンドレットを実行します。
    
        Stop-CsWindowsService

3.  XMPP フェデレーション ルートを変更して EdgePool2 を指すようにするには、次のコマンドレットを実行します。
    
        Set-CsSite Site2 -XmppExternalFederationRoute EdgeServer2.contoso.com
    
    この例で、Site2 は XMPP フェデレーション ルートをこれからホストするエッジ プールを含むサイトを表します。また、EdgeServer2.contoso.com はそのプール内のエッジ サーバーの FQDN です。

4.  外部 DNS サーバーで、XMPP フェデレーションの DNS A レコードを変更して、EdgeServer2.contoso.com を指すようにします。

5.  XMPP フェデレーションをホストする新しいエッジ プールに解決される、XMPP フェデレーションの DNS SRV レコードがまだない場合は、次の例に示すように、このレコードを追加する必要があります。この SRV レコードには、ポート値 5269 が含まれている必要があります。
    
        _xmpp-server._tcp.contoso.com

6.  XMPP フェデレーションをホストする新しいエッジ プールで、ポート 5269 が外部に開いていることを確認します。

7.  XMPP フェデレーションをホストする新しいエッジ プール内のすべてのエッジ サーバーでサービスを開始します。
    
        Start-CsWindowsService


## <a name="fail-back-the-edge-pool-used-for-skype-for-business-server-federation-or-xmpp-federation"></a>Skype for Business Server フェデレーションまたは XMPP フェデレーションに使用されるエッジ プールのフェールバック 

フェデレーションをホストするために使用した障害が発生したエッジ プールをオンラインに戻した後、この手順を使用して Skype for Business Server フェデレーション ルートまたは XMPP フェデレーション ルートをフェールバックし、この復元されたエッジ プールを再度使用します。

1.  再び使用できるようになったエッジ プールで、エッジ サービスを開始します。

2.  復元されたエッジ サーバーを使用するために Skype for Business Server フェデレーション ルートをフェールバックする場合は、次の手順を実行します。
    
      - フロントエンド サーバーでトポロジ ビルダーを開きます。[**エッジ プール**] を展開し、現在フェデレーションに構成されているエッジ サーバーまたはエッジ サーバー プールを右クリックして、[**プロパティの編集**] を選択します。
    
      - [**プロパティの編集**] の [**全般**] で、[**このエッジ プールのフェデレーションの有効化 (ポート 5061)**] をクリアします。[**OK**] をクリックします。
    
      - [**エッジ プール**] を展開し、フェデレーションに再び使用する元のエッジ サーバーまたはエッジ サーバー プールを右クリックします。[**プロパティの編集**] をクリックします。
    
      - [**プロパティの編集**] の [**全般**] で、[**このエッジ プールのフェデレーションの有効化 (ポート 5061)**] を選択します。[**OK**] をクリックします。
    
      - [**アクション**] をクリックし、[**トポロジ**]、[**公開**] の順に選択します。[**トポロジの公開**] で入力を求められたら、[**次へ**] をクリックします。公開の終了後、[**完了**] をクリックします。
    
      - エッジ サーバーで、Skype for Business Server 展開ウィザードを開きます。 [Skype **for Business Server システムのインストールまたは更新] を** クリックし、[Skype for Business Server コンポーネントのセットアップまたは削除] **をクリックします**。 [**再実行**] をクリックします。
    
      - [**次へ**] をクリックします。 概要画面に、実行されたアクションが表示されます。 展開が完了したら、[**ログの表示**] をクリックして、参照できるログ ファイルを表示します。 [**完了**] をクリックして、展開を完了します。

3.  復旧されたエッジ サーバーが使用されるように XMPP フェデレーション ルートをフェールバックするには以下を行います。
    
      - 以下のコマンドレットを実行して、XMPP フェデレーション ルートが、XMPP フェデレーションをホストするようになるエッジ プール (この例では、EdgeServer1) を再び指すようにします。
        
            Set-CsSite Site1 -XmppExternalFederationRoute EdgeServer1.contoso.com
        
        この例では、Site1 は XMPP フェデレーション ルートをホストするようになるエッジ プールを含むサイトです。EdgeServer1.contoso.com はそのプール内のエッジ サーバーの FQDN です。
    
      - XMPP フェデレーションをホストするようになるエッジ プールに解決される、XMPP フェデレーション用の DNS SRV レコードがまだない場合は、以下の例のようにそれを追加する必要があります。この SRV レコードはポート値が 5269 である必要があります。
        
            _xmpp-server._tcp.contoso.com
    
      - 外部 DNS サーバーで、XMPP フェデレーション用の DNS A レコードが EdgeServer2.contoso.com を指すように変更します。
    
      - XMPP フェデレーションをホストするようになるエッジ プールがポート 5269 を外部にオープンしていることを確認します。

4.  障害発生後に復旧されたエッジ プールを含むサイトで、フロントエンド プールが実行を続けていた場合は、それらのフロントエンド プール上の Web 会議サービスおよび音声ビデオ会議サービスを更新して、ローカル サイトのエッジ プールが再び使用されるようにしてください。

5.  停止したエッジ プールと同じサイトでフロントエンド プールも停止していた場合は、Invoke–CsPoolFailback を使ってフロントエンド プールをフェールバックできます。


## <a name="change-the-edge-pool-associated-with-a-front-end-pool"></a>フロントエンド プールに関連付けられているエッジ プールを変更する

エッジ プールがダウンして同じサイトのフロントエンド プールがまだ実行中の場合、問題の発生したエッジ プールが復元されるまで、別のサイトのエッジ プールを使用するようにフロントエンド プールを設定する必要があります。

1.  トポロジ ビルダーで、変更するフロントエンド プールの名前を表示します。

2.  プールを右クリックし、[**プロパティの編集**] をクリックします。

3.  [**関連付け**] セクションの、[**エッジ プールの関連付け (メディア コンポーネント用) の**] 下のドロップダウン ボックスを使用して、このフロントエンド プールを関連付けるエッジ プールを選択します。

4.  [**OK**] をクリックします。
