---
title: プールでフェイル バックをし、障害が発生しました。
author: heidip
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: .
ms.openlocfilehash: 23b70817ba75f3a0a6e73cc42a9df9026e17b2d7
ms.sourcegitcommit: 5576463b0295e48e0506f7e4b44006ffc0b38a95
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/10/2018
ms.locfileid: "27223508"
---
# <a name="failing-over-and-failing-back-a-pool-in-skype-for-business-server"></a>Skype でプールをビジネス サーバーのフェイル バックをし、障害が発生しました。 

ニーズへのフェイル オーバー、または障害が発生したプールがオンラインに戻ると展開を通常の稼動状態に復元する必要があります 1 つのフロント エンド プールが失敗した場合は、次の手順を使用します。 フェイル オーバーおよびフェイル バックのビジネス連合の XMPP フェデレーションでは、Skype の使用しているエッジ プールする方法について説明し、フロント エンド プールに関連付けられているエッジ プールを変更したりできます。

- [フロント エンド プールをフェールオーバーします。](#fail-over-a-front-end-pool)
- [プールのフェイル バック](#fail-back-a-pool)
- [Skype のビジネス サーバー連合を使用しているエッジ プールのフェールオーバーします。](#fail-over-the-edge-pool-used-for-skype-for-business-server-federation)
- [ビジネス サーバーの Skype の XMPP のフェデレーションに使用するエッジ プールのフェールオーバーします。](#fail-over-the-edge-pool-used-for-xmpp-federation-in-skype-for-business-server)
- [ビジネス サーバーのフェデレーションまたは XMPP フェデレーションの Skype の使用されるエッジ プールのフェイル バック](#fail-back-the-edge-pool-used-for-skype-for-business-server-federation-or-xmpp-federation)
- [フロント エンド プールに関連付けられたエッジ プールを変更します。](#change-the-edge-pool-associated-with-a-front-end-pool)

## <a name="fail-over-a-front-end-pool"></a>フロント エンド プールをフェールオーバーします。

ここで Datacenter1 に Pool1 が含まれているし、Pool1 に失敗しました。 Datacenter2 にある Pool2 にフェールオーバーするとします。

プールのフェールオーバーの処理のほとんどは、中央管理ストアでは、フェールオーバーが必要な場合。 プールのユーザーがフェールオーバーすると、中央管理ストアが機能する必要がありますので、これは重要です。

さらに、フロント エンド プールで障害が発生した場合はそのサイトのエッジ プールがまだ実行中、エッジ プールで障害が発生したプールを使用して、次ホップ プールとしてかどうかを知る必要があります。 場合は、エッジ プールに障害が発生したフロント エンド プールで障害が発生した前に別のフロント エンド プールを使用してを変更する必要があります。 次ホップの設定を変更する方法は、エッジ、エッジのプールと同じサイトまたは別のサイトでプールを使用できるかどうかによって異なります。

**同じサイトにある次ホップ プールを使用するのには、エッジ プールを設定するのには**

1.  トポロジ ビルダーを開き、変更する必要があるエッジ プールを右クリックし**プロパティの編集**] をクリックします。

2.  [**次ホップ**] をクリックします。 **プールを次ホップ:** リストで、次ホップ プールとしてここで使用するプールを選択します。

3.  **[Ok]** をクリックし、変更内容を発行します。

**別のサイトにある次ホップ プールを使用するのには、エッジ プールを設定するのには**

1.  Skype ビジネス サーバー管理シェル ウィンドウを開くし、次のコマンドレットを入力します。
    
        Set-CsEdgeServer -Identity EdgeServer:<Edge Server pool FQDN> -Registrar Registrar:<NextHopPoolFQDN>

**フェイル オーバー、災害時にプールに**

1.  プールは、Pool2 内のフロント エンド サーバーで次のコマンドレットを入力してサーバーの全体管理サーバーのホストを参照してください。
    
        Invoke-CsManagementServerFailover -Whatif
    
    このプールは、サーバーの全体管理サーバーを現在ホスト コマンドレットの表示] の結果。 この手順の残りの部分で、このプールが CMS と呼ばれる\_プールです。

2.  Cms を実行しているビジネス サーバーの Skype のバージョンを検索するのにはトポロジ ビルダーを使用して\_プールです。 Skype ビジネス サーバーは、実行している場合は、プール 1 のバックアップ ・ プールを検索するのには次のコマンドレットを使用します。
    
        Get-CsPoolBackupRelationship -PoolFQDN <CMS_Pool FQDN>
    
    バックアップを\_プールは、バックアップ ・ プールをします。

3.  次のコマンドレットを使用して中央管理ストアの状態を確認します。
    
        Get-CsManagementStoreReplicationStatus -CentralManagementStoreStatus 
    
    このコマンドレットが ActiveMasterFQDN と ActiveFileTransferAgents の両方に、CMS の FQDN を指していることを表示する必要があります\_プールです。 空場合は、中央の管理サーバーが利用できないと、それをフェイル オーバーする必要があります。

4.  Pool1 に中央管理ストアが実行されていた場合、または中央管理ストアが利用できない場合 (つまり、障害が発生した)、プール、プールで障害が発生した前にサーバーの全体管理サーバーをフェールオーバーする必要があります。 Skype を実行して、ビジネスのサーバーのプールでホストされるサーバーの全体管理サーバーのフェールオーバーが必要な場合は、この手順のステップ 5 で、コマンドレットを使用します。 中央管理サーバーにフェールオーバーする必要がない場合は、この手順の手順 7 に進んでください。

5.  Skype を実行して、ビジネスのサーバーのプールを中央管理ストアをフェールオーバーするには、次の操作を行います。
    
      - バック エンド サーバーのバックアップを確認して最初に、\_プールは、次を入力して主体の中央管理ストアのインスタンスを実行します。
        
            Get-CsDatabaseMirrorState -DatabaseType Centralmgmt -PoolFqdn <Backup_Pool Fqdn>
    
      - 場合、プライマリ バック エンド サーバーのバックアップに\_プールでは、プリンシパルの種類。
        
            Invoke-CSManagementServerFailover -BackupSQLServerFqdn <Backup_Pool Primary BackEnd Server FQDN> -BackupSQLInstanceName <Backup_Pool Primary SQL Instance Name>
        
        場合ミラー バックアップでは、バック エンド サーバー\_プールでは、プリンシパルの種類。
        
            Invoke-CSManagementServerFailover -MirrorSQLServerFqdn <Backup_Pool Mirror BackEnd Server FQDN> -MirrorSQLInstanceName <Backup_Pool Mirror SQL Instance Name>
    
      - 中央管理サーバーのフェールオーバーが完了したことを検証します。 次に入力します。
        
            Get-CsManagementStoreReplicationStatus -CentralManagementStoreStatus 
        
        ActiveMasterFQDN と ActiveFileTransferAgents の両方に、FQDN のバックアップを指していることを確認\_プールです。
    
      - 最後に、次を入力してすべてのフロント エンド サーバーのレプリカの状態を確認します。
        
            Get-CsManagementStoreReplicationStatus 
        
        True の値をすべてのレプリカがあることを確認してください。
        
        この手順の手順 7 に進んでください。

6.  バック エンド サーバーのバックアップを中央管理ストアにインストール\_プールです。
    
      - 最初に、次のコマンドを実行します。
        
        ``` 
        Install-CsDatabase -CentralManagementDatabase -Clean -SqlServerFqdn <Backup_Pool Back End Server FQDN> -SqlInstanceName rtc  
        ```
    
      - フロント エンド サーバーのバックアップのいずれかで次のコマンドを実行\_プールを強制的に中央管理ストアの移動します。
        
            Move-CsManagementServer -ConfigurationFileName c:\CsConfigurationFile.zip -LisConfigurationFileName c:\CsLisConfigurationFile.zip -Force 
    
      - 検証移動が完了します。
        
            Get-CsManagementStoreReplicationStatus -CentralManagementStoreStatus 
        
        ActiveMasterFQDN と ActiveFileTransferAgents の両方に、FQDN のバックアップを指していることを確認\_プールです。
    
      - 次を入力して、すべてのフロント エンド サーバーのレプリカの状態を確認します。
        
            Get-CsManagementStoreReplicationStatus 
        
        True の値をすべてのレプリカがあることを確認してください。
    
      - バックアップでは、フロント エンド サーバーの他のサーバーの全体管理サーバーのサービスをインストールする\_プールです。 これを行うには、すべてのフロント エンド サーバーで次のコマンドを実行して、ストアがこの手順で前に移動以外のサーバーの全体管理を強制するときに使用しました。
        
            Bootstrapper /Setup 

7.  Pool1 から Pool2 へのユーザーは失敗し、Skype ビジネス サーバー管理シェル ウィンドウで次のコマンドレットを実行しています。
    
        Invoke-CsPoolFailover -PoolFQDN <Pool1 FQDN> -DisasterMode -Verbose
    
    中央管理ストアの状態を確認する手順を次の手順の前の部分ではユニバーサルではないために、まだ確率中央管理ストアがまだ完全にフェイル オーバーされなかったために、このコマンドレットは失敗します。 この例では、表示されるエラー メッセージに基づく中央管理ストアを修正してこのコマンドレットを再度実行してください。
    
    次のエラー メッセージが表示された場合は、エッジでプール プールで障害が発生した前に次のホップとして別のプールを使用するには、このサイトを変更する必要があります。 詳細については、このトピックの先頭に手順を参照してください。
    
        Invoke-CsPoolFailOver : This Front-end pool "pool1.contoso.com" is specified in
        topology as the next hop for the Edge server. Failing over this pool may cause External
        access/Federation/Split-domain/XMPP features to stop working. Please use Topology Builder to
        change the Edge internal next hop setting to point to a different Front-end pool,  before you
        proceed.


## <a name="fail-back-a-pool"></a>プールのフェイル バック

障害が発生したプールがオンラインに戻った後 (つまり、Pool1 この例では)、通常の動作状態を配置を復元するのには、次の手順を実行します。

フェイル バック ・ プロセスは、いくつかの分を完了することに注意してください。リファレンスについては、最大 60 分まで 20,000 名のユーザーのプールを実行する予定です。

Pool1 にホームが最初とされて失敗した上で Pool2 を次のコマンドレットを入力してユーザーのフェイル バックします。
    
    Invoke-CsPoolFailback -PoolFQDN <Pool1 FQDN> -Verbose

その他の手順を実行する必要はありません。 中央管理サーバーをフェールオーバーする場合は、Pool2 のままにします。

## <a name="fail-over-the-edge-pool-used-for-skype-for-business-server-federation"></a>Skype のビジネス サーバー連合を使用しているエッジ プールのフェールオーバーします。 

構成されているビジネス サーバーのフェデレーション用に Skype があるエッジ プールで障害が発生した場合は、作業を別のエッジ プールのフェデレーションを使用するフェデレーションを変更しなければなりません。

1.  フロント エンド サーバーでは、トポロジ ビルダーを開きます。 **エッジ プール**を展開し、エッジ サーバーまたはフェデレーション用に構成されているエッジ サーバー プールを右クリックします。 **プロパティの編集**] を選択します。

2.  [**全般**の**プロパティの編集** **(ポート 5061) エッジ プールのフェデレーションを有効にする**をオフにします。 [**OK**] をクリックします。

3.  **エッジ プール**を展開し、フェデレーションに使用するようになりました、エッジ サーバーまたはエッジ サーバー プールを右クリックします。 **プロパティの編集**] を選択します。

4.  [**全般****プロパティの編集**] で、**このエッジ プール (ポート 5061) のフェデレーションを有効にする**を選択します。 [**OK**] をクリックします。

5.  [**アクション**] をクリックして、**トポロジ**を選択し、**発行**] を選択します。 **公開トポロジ**でメッセージが表示されたら、[**次へ**] をクリックします。 発行が完了したら、[**完了**] をクリックします。

6.  エッジ サーバーでは、ビジネスのサーバーの展開ウィザードの Skype を開きます。 **インストールまたはサーバーのビジネス システムの更新プログラムの Skype**をクリックし、[**セットアップ] または [サーバー コンポーネントのビジネスの Skype を削除**します。 **もう一度実行**] をクリックします。

7.  [ **次へ**] をクリックします。 サマリー画面で実行されたアクションが表示されます。 展開が完了すると、利用可能なログ ファイルを表示する**ログの表示**をクリックします。 展開を完了する**完了**をクリックします。
    
    障害が発生したエッジのプールが含まれるサイトにまだ実行されているフロント エンド サーバーが含まれている場合は、Web 会議サービス、および A を更新する必要があります ◆ リモート エッジ プールを使用するのには、これらのフロント エンド プールの V 会議サービスがまだ実行中です。 

 ## <a name="fail-over-the-edge-pool-used-for-xmpp-federation-in-skype-for-business-server"></a>ビジネス サーバーの Skype の XMPP のフェデレーションに使用するエッジ プールのフェールオーバーします。 

組織では、XMPP のフェデレーションに使用するプールとして指定されている 1 つのエッジ プールがあります。 このプールで障害が発生した場合は、フェイル オーバーは、XMPP のフェデレーション XMPP フェデレーションが再び動作することができます前に、別のエッジ プールを使用する必要があります。

まず、エッジ プールをインストールし、XMPP フェデレーションを有効にする、エッジ プールの 1 つだけではなく、XMPP フェデレーションのすべての外部の DNS SRV レコードを設定することにより災害復旧プロセスを簡略化できます。 これらの SRV レコードの各には、別の優先順位が設定が必要です。 XMPP フェデレーションのすべてのトラフィックは、優先順位が高い SRV レコードを持つプールを通過します。 

次の手順では最初、XMPP フェデレーションをホストするプール、EdgePool1、EdgePool2 XMPP フェデレーションをホストするようになりましたが、プール。


### <a name="to-fail-over-the-edge-pool-used-for-xmpp-federation"></a>XMPP のフェデレーションに使用するエッジ プールでエラーが発生するには

1.  展開 (現在下にある 1 つ) だけでなく、別のエッジ プールを持っていない場合は、そのプールを展開します。 

2.  XMPP フェデレーション (EdgePool2) をホストするようになりましたが、新しいエッジ プール内の各エッジ サーバーを導入すると、次のコマンドレットを実行します。
    
        Stop-CsWindowsService

3.  EdgePool2 に XMPP フェデレーション ルートへの再接続には、次のコマンドレットを実行します。
    
        Set-CsSite Site2 -XmppExternalFederationRoute EdgeServer2.contoso.com
    
    この例では、サイト 2 は XMPP フェデレーション ルートをホストするようになりましたが、エッジのプールが含まれているサイトで、EdgeServer2.contoso.com は、そのプール内のエッジ サーバーの FQDN です。

4.  外部の DNS サーバーでは、EdgeServer2.contoso.com を指すように XMPP フェデレーション用の DNS A レコードを変更します。

5.  XMPP フェデレーション XMPP フェデレーションをホストするようになりましたが、エッジ プールに解決するための DNS SRV レコードがあるない場合、次の例のようにを追加する必要があります。 この SRV レコードには、5269 のポートの値が必要です。
    
        _xmpp-server._tcp.contoso.com

6.  XMPP フェデレーションをホストするようになりましたが、エッジ プールにポート 5269 を開いて外部を確認します。

7.  XMPP フェデレーションをホストするようになりましたが、エッジ プール内のすべてのエッジ サーバーでサービスを開始します。
    
        Start-CsWindowsService


## <a name="fail-back-the-edge-pool-used-for-skype-for-business-server-federation-or-xmpp-federation"></a>ビジネス サーバーのフェデレーションまたは XMPP フェデレーションの Skype の使用されるエッジ プールのフェイル バック 

障害が発生したエッジの後フェデレーションをホストするために使用するプールをオンラインに復帰されましたが、ビジネス サーバーのフェデレーション ルートと XMPP フェデレーション ルートにもう一度この復元されたエッジ プールを使用する Skype でフェイル バックするにはこの手順を使用します。

1.  現在は再び利用可能なエッジ プールのエッジ サービスを開始します。

2.  復元されたエッジ サーバーを使用するビジネス サーバーのフェデレーション ルートの Skype でフェイル バックする場合は、次の操作を行います。
    
      - フロント エンド サーバーでは、トポロジ ビルダーを開きます。 **エッジ プール**を展開し、エッジ サーバーまたはフェデレーション用に構成されているエッジ サーバー プールを右クリックします。 **プロパティの編集**] を選択します。
    
      - [**全般**の**プロパティの編集** **(ポート 5061) エッジ プールのフェデレーションを有効にする**をオフにします。 [**OK**] をクリックします。
    
      - **エッジ プール**を展開し、フェデレーションに使用する場合、元のエッジ サーバーまたはエッジ サーバー プールを右クリックします。 **プロパティの編集**] を選択します。
    
      - [**全般****プロパティの編集**] で、**このエッジ プール (ポート 5061) のフェデレーションを有効にする**を選択します。 [**OK**] をクリックします。
    
      - [**アクション**] をクリックして、**トポロジ**を選択し、**発行**] を選択します。 **公開トポロジ**でメッセージが表示されたら、[**次へ**] をクリックします。 発行が完了したら、[**完了**] をクリックします。
    
      - エッジ サーバーでは、ビジネスのサーバーの展開ウィザードの Skype を開きます。 **インストールまたはサーバーのビジネス システムの更新プログラムの Skype**をクリックし、[**セットアップ] または [サーバー コンポーネントのビジネスの Skype を削除**します。 **もう一度実行**] をクリックします。
    
      - [ **次へ**] をクリックします。 サマリー画面で実行されたアクションが表示されます。 展開が完了すると、利用可能なログ ファイルを表示する**ログの表示**をクリックします。 展開を完了する**完了**をクリックします。

3.  復元されたエッジ サーバーを使用する XMPP フェデレーション ルートをフェールバックするには、次の操作を行います。
    
      - XMPP フェデレーション ルート (この例では、EdgeServer1) では、XMPP フェデレーションをホストするようになりましたが、エッジのプールへの再接続には、次のコマンドレットを実行します。
        
            Set-CsSite Site1 -XmppExternalFederationRoute EdgeServer1.contoso.com
        
        この例では、Site1 XMPP フェデレーション ルートをホストするようになりましたが、エッジのプールが含まれるサイトは、EdgeServer1.contoso.com では、プール内のエッジ サーバーの FQDN です。
    
      - XMPP フェデレーション XMPP フェデレーションをホストするようになりましたが、エッジ プールに解決するための DNS SRV レコードがあるない場合、次の例のようにを追加する必要があります。 この SRV レコードには、5269 のポートの値が必要です。
        
            _xmpp-server._tcp.contoso.com
    
      - 外部の DNS サーバーでは、EdgeServer2.contoso.com を指すように XMPP フェデレーション用の DNS A レコードを変更します。
    
      - XMPP フェデレーションをホストするようになりましたが、エッジ プールにポート 5269 を開いて外部を確認します。

4.  フロント エンド プールに残っている障害が発生し、復元されたエッジ プールを含むサイトで実行中、する場合は、Web 会議サービス、および A を更新する必要がありますこれらのフロント エンドでの V 会議サービス プール再使用する、ローカル サイトにあるエッジ プールとします。

5.  障害が発生したエッジのプールと同じサイトでフロント エンド プールも失敗した場合、使えるようになりました呼び出し – CsPoolFailback フロント エンド プールをフェールバックするためです。


## <a name="change-the-edge-pool-associated-with-a-front-end-pool"></a>フロント エンド プールに関連付けられたエッジ プールを変更します。

エッジ プールは、障害が発生した場合は、同じサイトのフロント エンド プールがまだ実行中は、障害が発生したエッジ プールが復元されるまで、別のサイトで、エッジのプールを使用するフロント エンド プールを設定する必要があります。

1.  トポロジ ビルダーでは、変更する必要がありますフロント エンド プールの名前に移動します。

2.  プールを右クリックし、 **[プロパティの編集**] をクリックします。

3.  **関連付け**] セクションの [**エッジ プールを (メディア コンポーネント) の関連付け**] の下で、リスト ボックスでは、このフロント エンド プールに関連付けるエッジ プールを選択するのにはドロップを使用します。

4.  [**OK**] をクリックします。