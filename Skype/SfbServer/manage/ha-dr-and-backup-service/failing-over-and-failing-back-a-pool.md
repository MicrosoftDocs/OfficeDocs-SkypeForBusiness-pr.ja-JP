---
title: プールのフェールオーバーおよびフェールバック
ms.reviewer: ''
author: lanachin
ms.author: v-lanac
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: .
ms.openlocfilehash: d5409441336ef2af8bbe9c6a39530584a167ec05
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2020
ms.locfileid: "41818208"
---
# <a name="failing-over-and-failing-back-a-pool-in-skype-for-business-server"></a>Skype for Business Server でのプールのフェイルオーバーとフェイルバック 

1つのフロントエンドプールで障害が発生してフェールオーバーが発生した場合、または障害が発生したプールがオンライン状態に戻っている場合は、次の手順を実行します。展開を通常の作業状態に戻す必要があります。 また、Skype for Business フェデレーションまたは XMPP フェデレーションに使用されるエッジプールをフェイルオーバーしてフェールバックする方法や、フロントエンドプールに関連付けられているエッジプールを変更する方法についても説明します。

- [フロントエンドプールのフェイルオーバー](#fail-over-a-front-end-pool)
- [プールのフェイルバック](#fail-back-a-pool)
- [Skype for Business Server federation で使用されるエッジプールをフェイルオーバーする](#fail-over-the-edge-pool-used-for-skype-for-business-server-federation)
- [Skype for Business Server の XMPP フェデレーションに使用されるエッジプールをフェールオーバーする](#fail-over-the-edge-pool-used-for-xmpp-federation-in-skype-for-business-server)
- [Skype for Business Server federation または XMPP フェデレーションに使用されるエッジプールのフェイルバック](#fail-back-the-edge-pool-used-for-skype-for-business-server-federation-or-xmpp-federation)
- [フロントエンドプールに関連付けられているエッジプールを変更する](#change-the-edge-pool-associated-with-a-front-end-pool)

## <a name="fail-over-a-front-end-pool"></a>フロントエンドプールのフェイルオーバー

この手順では、Datacenter1 に Pool1 が含まれており、Pool1 は失敗しています。 Datacenter2 にある Pool2 にフェイルオーバーしています。

プールフェールオーバーのほとんどの作業には、必要に応じて、中央管理ストアのフェールオーバーが含まれています。 プールのユーザーがフェールオーバーされた場合は、中央管理ストアが機能している必要があるため、これは重要です。

さらに、フロントエンドプールに障害が発生しても、そのサイトの Edge プールがまだ実行されている場合は、Edge プールが、失敗したプールを次のホッププールとして使用するかどうかを確認する必要があります。 問題が発生した場合は、失敗したフロントエンドプールを使用するようにエッジプールを変更する必要があります。 次ホップの設定を変更する方法は、エッジプールと同じサイトのプールを使用するか、または別のサイトを使うかによって異なります。

**エッジプールで、同じサイトの次ホッププールを使用するように設定するには**

1.  トポロジビルダーを開き、変更する必要があるエッジプールを右クリックして、[**プロパティの編集**] をクリックします。

2.  [**次ホップ**] をクリックします。 [ **Next ホッププール:** ] ボックスの一覧で、次ホッププールとして機能するプールを選択します。

3.  [ **OK**] をクリックして、変更を公開します。

**別のサイトで次ホッププールを使用するようにエッジプールを設定するには**

1.  Skype for Business Server 管理シェルウィンドウを開いて、次のコマンドレットを入力します。
    
        Set-CsEdgeServer -Identity EdgeServer:<Edge Server pool FQDN> -Registrar Registrar:<NextHopPoolFQDN>

**障害が発生したプールをフェイルオーバーするには**

1.  Pool2 のフロントエンドサーバーに次のコマンドレットを入力して、中央管理サーバーのホストとなるプールを見つけます。
    
        Invoke-CsManagementServerFailover -Whatif
    
    このコマンドレットの結果は、現在中央管理サーバーをホストしているプールを示します。 この手順の残りの部分では、このプールを CMS\_プールと呼びます。

2.  トポロジビルダーを使用して、CMS\_プールで実行されている Skype For business Server のバージョンを確認します。 Skype for Business Server を実行している場合は、次のコマンドレットを使用して、Pool 1 のバックアッププールを検索します。
    
        Get-CsPoolBackupRelationship -PoolFQDN <CMS_Pool FQDN>
    
    バックアップ\_プールをバックアッププールにします。

3.  次のコマンドレットを使用して、サーバーの全体管理ストアの状態を確認します。
    
        Get-CsManagementStoreReplicationStatus -CentralManagementStoreStatus 
    
    このコマンドレットでは、ActiveMasterFQDN と ActiveFileTransferAgents の両方が CMS\_プールの FQDN を指していることを示しています。 空の場合は、サーバーの全体管理サーバーを利用できないため、フェールオーバーを行う必要があります。

4.  中央管理ストアを使用できない場合、または Pool1 で中央管理ストアが実行されている場合 (つまり、失敗したプール)、プールをフェールオーバーする前に、中央管理サーバーをフェールオーバーする必要があります。 Skype for Business Server を実行しているプールでホストされていた中央管理サーバーをフェールオーバーする必要がある場合は、この手順の手順5のコマンドレットを使用します。 サーバーの全体管理サーバーにフェールオーバーする必要がない場合は、手順7に進んでください。

5.  Skype for Business Server を実行しているプールの中央管理ストアをフェールオーバーするには、次の操作を行います。
    
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
        ```PowerShell
         
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

7.  Skype for Business Server 管理シェルウィンドウで次のコマンドレットを実行して、Pool1 から Pool2 にユーザーをフェールオーバーします。
    
        Invoke-CsPoolFailover -PoolFQDN <Pool1 FQDN> -DisasterMode -Verbose
    
    この手順の前の部分で実行した手順では、全体管理ストアの状態を確認する必要があるため、中央管理ストアはまだ完全にフェールオーバーしていないため、このコマンドレットは失敗する可能性があります。 この場合は、表示されるエラーメッセージに基づいて、中央管理ストアを修正し、このコマンドレットをもう一度実行する必要があります。
    
    次のエラーメッセージが表示された場合は、プールをフェールオーバーする前に、このサイトの Edge プールを別のホップとして使用するように変更する必要があります。 詳細については、このトピックの最初の手順を参照してください。
    
        Invoke-CsPoolFailOver : This Front-end pool "pool1.contoso.com" is specified in
        topology as the next hop for the Edge server. Failing over this pool may cause External
        access/Federation/Split-domain/XMPP features to stop working. Please use Topology Builder to
        change the Edge internal next hop setting to point to a different Front-end pool,  before you
        proceed.


## <a name="fail-back-a-pool"></a>プールのフェイルバック

障害が発生したプールがオンラインに戻る (この例では Pool1 である) 場合は、次の手順を実行して、展開を通常の作業状態に戻します。

フェイルバックプロセスが完了するまでに数分かかることに注意してください。参照の場合、2万ユーザーのプールには最大60分かかることが予想されます。

最初に Pool1 をホームにし、次のコマンドレットを入力して、Pool2 にフェイルオーバーしているユーザーをフェールバックします。
    
    Invoke-CsPoolFailback -PoolFQDN <Pool1 FQDN> -Verbose

その他の手順は必要ありません。 中央管理サーバーで障害が発生した場合は、Pool2 にそのままにしておくことができます。

## <a name="fail-over-the-edge-pool-used-for-skype-for-business-server-federation"></a>Skype for Business Server federation で使用されるエッジプールをフェイルオーバーする 

Skype for Business Server フェデレーションが構成されている Edge プールが停止している場合は、フェデレーションが機能するために別のエッジプールを使用するようにフェデレーションを変更する必要があります。

1.  フロントエンドサーバーで、[トポロジビルダー] を開きます。 [**エッジプール**] を展開し、現在フェデレーション用に構成されているエッジサーバープールまたはエッジサーバープールを右クリックします。 [**プロパティの編集**] を選びます。

2.  [**プロパティの編集**] の [**全般**] で、[**このエッジプールに対してフェデレーションを有効にする (ポート 5061)**] をオフにします。 **[OK]** をクリックします。

3.  [**エッジプール**] を展開して、フェデレーションに使用するエッジサーバーまたはエッジサーバープールを右クリックします。 [**プロパティの編集**] を選びます。

4.  [**プロパティの編集**] の [**全般**] で、[**このエッジプールに対してフェデレーションを有効にする (ポート 5061)**] を選択します。 **[OK]** をクリックします。

5.  [**アクション**] をクリックし、[**トポロジ**] を選択し、[**発行**] を選択します。 **トポロジの発行**を求められたら、[**次へ**] をクリックします。 発行が完了したら、[**完了**] をクリックします。

6.  エッジサーバーで、Skype for Business Server 展開ウィザードを開きます。 [ **Skype For Business Server システムのインストールまたは更新**] をクリックし、[**セットアップ] または [Skype For business Server コンポーネントの削除**] をクリックします。 [**実行] をもう一度**クリックします。

7.  [ **次へ**] をクリックします。 概要画面には、実行中の操作が表示されます。 展開が完了したら、[**ログの表示**] をクリックして、利用可能なログファイルを表示します。 [**完了**] をクリックして展開を完了します。
    
    問題のあるエッジプールを含むサイトにまだ実行されているフロントエンドサーバーが含まれている場合は、これらのフロントエンドプールの Web 会議サービスと A/V 会議サービスを更新して、まだ実行中のリモートサイトでエッジプールを使用する必要があります。 

 ## <a name="fail-over-the-edge-pool-used-for-xmpp-federation-in-skype-for-business-server"></a>Skype for Business Server の XMPP フェデレーションに使用されるエッジプールをフェールオーバーする 

組織では、1つのエッジプールがプールとして指定されています。 このプールがダウンした場合は、xmpp フェデレーションを再度使用する前に、別のエッジプールを使用するために XMPP フェデレーションをフェイルオーバーする必要があります。

最初に Edge プールをインストールして XMPP フェデレーションを有効にすると、1つの代わりに XMPP のすべてのエッジプールの外部 DNS SRV レコードを設定することで、障害回復プロセスを簡略化できます。 各 SRV レコードには、異なる優先順位を設定する必要があります。 すべての XMPP フェデレーショントラフィックは、最も優先度の高い SRV レコードを持つプールを通過します。 

次の手順では、EdgePool1 は最初に XMPP フェデレーションをホストしたプールであり、EdgePool2 は XMPP フェデレーションをホストするプールです。


### <a name="to-fail-over-the-edge-pool-used-for-xmpp-federation"></a>XMPP フェデレーションに使用されるエッジプールをフェイルオーバーするには

1.  (現在ダウンしている) 別の Edge プールをまだ展開していない場合は、そのプールを展開します。 

2.  新しいエッジプールの各エッジサーバーで XMPP federation (EdgePool2) をホストするために、次のコマンドレットを実行します。
    
        Stop-CsWindowsService

3.  XMPP フェデレーションルートを EdgePool2 に再ポイントするには、次のコマンドレットを実行します。
    
        Set-CsSite Site2 -XmppExternalFederationRoute EdgeServer2.contoso.com
    
    この例では、Site2 は、XMPP フェデレーションルートをホストするエッジプールが含まれているサイトで、EdgeServer2.contoso.com はそのプールのエッジサーバーの FQDN です。

4.  外部 DNS サーバーで、XMPP フェデレーション用の DNS A レコードを EdgeServer2.contoso.com に変更します。

5.  Xmpp フェデレーション用の DNS SRV レコードをまだ持っていない場合は、次の例のように、それを追加する必要があります。これは、現在 XMPP フェデレーションをホストしています。 この SRV レコードには、5269のポート値を指定する必要があります。
    
        _xmpp-server._tcp.contoso.com

6.  XMPP フェデレーションをホストしている Edge プールのポート5269が外部で開かれていることを確認します。

7.  Edge プール内のすべてのエッジサーバーでサービスを開始します。これで、XMPP フェデレーションがホストされます。
    
        Start-CsWindowsService


## <a name="fail-back-the-edge-pool-used-for-skype-for-business-server-federation-or-xmpp-federation"></a>Skype for Business Server federation または XMPP フェデレーションに使用されるエッジプールのフェイルバック 

フェデレーションをホストするために使用された、失敗したエッジプールをオンラインに戻した後、次の手順を実行して、Skype for Business Server フェデレーションルートまたは XMPP フェデレーションルートをフェイルバックし、この復元されたエッジプールを再び使用します。

1.  もう一度使用できるようになったエッジプールで、エッジサービスを開始します。

2.  復元されたエッジサーバーを使用するために Skype for Business Server フェデレーションルートをフェイルバックする場合は、次の操作を行います。
    
      - フロントエンドサーバーで、[トポロジビルダー] を開きます。 [ **Edge プール**] を展開して、フェデレーション用に現在構成されているエッジサーバープールまたはエッジサーバープールを右クリックします。 [**プロパティの編集**] を選びます。
    
      - [**プロパティの編集**] の [**全般**] で、[**このエッジプールに対してフェデレーションを有効にする (ポート 5061)**] をオフにします。 **[OK]** をクリックします。
    
      - [ **Edge プール**] を展開し、もう一度フェデレーションに使用する元のエッジサーバープールまたはエッジサーバープールを右クリックします。 [**プロパティの編集**] を選びます。
    
      - [**プロパティの編集**] の [**全般**] で、[**このエッジプールに対してフェデレーションを有効にする (ポート 5061)**] を選択します。 **[OK]** をクリックします。
    
      - [**アクション**] をクリックし、[**トポロジ**] を選択し、[**発行**] を選択します。 **トポロジの発行**を求められたら、[**次へ**] をクリックします。 発行が完了したら、[**完了**] をクリックします。
    
      - エッジサーバーで、Skype for Business Server 展開ウィザードを開きます。 [ **Skype For Business Server System をインストールまたは更新**する] をクリックし、[**セットアップ] または [Skype For business Server コンポーネントの削除**] をクリックします。 [**実行] をもう一度**クリックします。
    
      - [ **次へ**] をクリックします。 概要画面には、実行中の操作が表示されます。 展開が完了したら、[**ログの表示**] をクリックして、利用可能なログファイルを表示します。 [**完了**] をクリックして展開を完了します。

3.  復元されたエッジサーバーを使用するために XMPP フェデレーションルートをフェイルバックする場合は、次の操作を行います。
    
      - 次のコマンドレットを実行して、xmpp フェデレーションルートを Edge プールに再ポイントします。これにより、XMPP フェデレーションがホストされます (この例では EdgeServer1)。
        
            Set-CsSite Site1 -XmppExternalFederationRoute EdgeServer1.contoso.com
        
        この例では、Site1 は、XMPP フェデレーションルートをホストするエッジプールが含まれているサイトで、EdgeServer1.contoso.com はそのプールのエッジサーバーの FQDN です。
    
      - Xmpp フェデレーション用の DNS SRV レコードをまだ持っていない場合は、次の例のように、それを追加する必要があります。これは、現在 XMPP フェデレーションをホストしています。 この SRV レコードには、5269のポート値を指定する必要があります。
        
            _xmpp-server._tcp.contoso.com
    
      - 外部 DNS サーバーで、XMPP フェデレーション用の DNS A レコードを EdgeServer2.contoso.com に変更します。
    
      - XMPP フェデレーションをホストしている Edge プールのポート5269が外部で開かれていることを確認します。

4.  フロントエンドプールが、失敗して復元されたエッジプールが含まれているサイトでまだ実行されている場合は、これらのフロントエンドプールの Web 会議サービスと A/V 会議サービスを更新して、もう一度ローカルサイトでエッジプールを使用する必要があります。

5.  障害が発生したエッジプールと同じサイトのフロントエンドプールでもエラーが発生する場合は、CsPoolFailback を使ってフロントエンドプールをフェールバックすることができます。


## <a name="change-the-edge-pool-associated-with-a-front-end-pool"></a>フロントエンドプールに関連付けられているエッジプールを変更する

エッジプールがダウンしていても、同じサイトのフロントエンドプールがまだ実行されている場合は、失敗したエッジプールが復元されるまで、別のサイトでエッジプールを使用するようにフロントエンドプールを設定する必要があります。

1.  [Topology Builder] で、変更する必要があるフロントエンドプールの名前に移動します。

2.  プールを右クリックし、[プロパティの**編集**] をクリックします。

3.  [**関連付け**] セクションの [ **Edge プールの関連付け (メディアコンポーネントの場合)**] で、ドロップダウンボックスを使用して、このフロントエンドプールを関連付けるエッジプールを選択します。

4.  [**OK**] をクリックします。
