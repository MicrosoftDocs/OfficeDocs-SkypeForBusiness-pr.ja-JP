---
title: 中央管理サーバーを移動する
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Skype for Business Server 2019 に移行した後は、従来のサーバーを削除する前に、中央管理サーバーを Skype for Business Server 2019 フロントエンドサーバーまたはプールに移動する必要があります。
ms.openlocfilehash: 5e16145b6695a9ee7006ab7d5321af9e478d7c37
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2019
ms.locfileid: "34291299"
---
# <a name="move-the-legacy-central-management-server-to-skype-for-business-server-2019"></a>従来のサーバーの全体管理サーバーを Skype for Business Server 2019 に移動する

Skype for Business Server 2019 に移行した後、レガシサーバーを削除する前に、中央管理サーバーを Skype for Business Server 2019 フロントエンドサーバーまたはプールに移動する必要があります。 
  
サーバーの全体管理サーバーは、1つのマスター/マルチレプリカシステムです。このシステムでは、データベースの読み取り/書き込みのコピーが、中央管理サーバーを含むフロントエンドサーバーによって保持されています。 トポロジ内の各コンピューターには、サーバーを含むフロントエンドサーバーを含む、セットアップ時にコンピューターにインストールされた、SQL Server データベースの中央管理ストアデータの読み取り専用コピーがあります (既定では、RTCLOCAL という名前が付いています)。デプロイメント. ローカルデータベースは、すべてのコンピューターでサービスとして実行される Skype for Business Server Replica Replicator エージェントを介して、レプリカの更新を受信します。 サーバーの全体管理サーバー上の実際のデータベースの名前とローカルレプリカは XDS で、これらは xds と xds のファイルで構成されます。 Master データベースの場所は、Active Directory ドメインサービスのサービスコントロールポイント (SCP) によって参照されます。 中央管理サーバーを使用して Skype for Business Server を管理および構成するすべてのツール SCP を使用して、中央管理ストアを検索します。
  
サーバーの全体管理サーバーが正常に移動されたら、元のフロントエンドサーバーから中央管理サーバーのデータベースを削除する必要があります。 サーバーの全体管理サーバーデータベースの削除については、「[フロントエンドプールの SQL Server データベースを削除](remove-the-sql-server-database-for-a-front-end-pool.md)する」を参照してください。
  
Skype for Business Server 管理シェルで Windows PowerShell コマンドレット**CsManagementServer**を使用して、従来の sql server データベースから Skype For business SERVER 2019 SQL server データベースにデータベースを移動し、次のようにします。[Skype for Business Server 2019 Central Management Server] の場所を示す SCP。 
  
このセクションの手順を使用して、中央管理サーバーを移動する前に、Skype for Business Server 2019 フロントエンドサーバーを準備します。
  
## <a name="to-prepare-an-enterprise-edition-front-end-pool"></a>Enterprise Edition フロントエンドプールを準備するには

1. 中央管理サーバーを再配置する Skype for Business Server 2019 Enterprise Edition のフロントエンドプールで、Skype for Business Server 管理シェルが RTCUniversalServerAdmins のメンバーとしてインストールされているコンピューターにログオンします。 **** グループ。 また、中央管理ストアをインストールするデータベースの SQL Server データベース sysadmin ユーザー権限と権限が必要です。 
    
2. Skype for Business Server 管理シェルを開きます。
    
3. Skype for Business Server 2019 SQL Server データベースに新しい中央管理ストアを作成するには、Skype for business Server 管理シェルで次のように入力します。
    
   ```
   Install-CsDatabase -CentralManagementDatabase -SQLServerFQDN <FQDN of your SQL Server> -SQLInstanceName <name of instance>
   ```

4. **Skype For Business Server フロントエンド**サービスの状態が**開始**されていることを確認します。
    
## <a name="to-prepare-a-standard-edition-front-end-server"></a>Standard Edition フロントエンドサーバーを準備するには

1. 中央管理サーバーを再配置する Skype for Business Server 2019 Standard Edition フロントエンドサーバーで、Skype for Business Server 管理シェルが RTCUniversalServerAdmins のメンバーとしてインストールされているコンピューターにログオンします。 **** グループ。 
    
2. Skype for Business Server 展開ウィザードを開きます。
    
3. Skype for Business Server の展開ウィザードで、[**最初の Standard Edition サーバーの準備**] をクリックします。
    
4. [**コマンドの実行**] ページでは、SQL Server Express が中央管理サーバーとしてインストールされています。 必要なファイアウォールルールが作成されます。 データベースと必須ソフトウェアのインストールが完了したら、[**完了**] をクリックします。
    
    > [!NOTE]
    > 最初のインストールでは、コマンド出力の概要画面に表示される更新プログラムがないと、時間がかかる場合があります。 これは、SQL Server Express をインストールしているためです。 データベースのインストールを監視する必要がある場合は、タスクマネージャーを使用してセットアップを監視します。 
  
5. Skype for Business Server 2019 Standard Edition のフロントエンドサーバーで新しい中央管理ストアを作成するには、Skype for business Server 管理シェルで次のように入力します。 
    
   ```
   Install-CsDatabase -CentralManagementDatabase -SQLServerFQDN <FQDN of your Standard Edition Server> -SQLInstanceName <name of instance - RTC by default>
   ```

6. **Skype For Business Server フロントエンド**サービスの状態が**開始**されていることを確認します。
    
## <a name="to-move-the-legacy-installs-central-management-server-to-skype-for-business-server-2019"></a>従来のインストールを移行するには、サーバーの全体管理サーバーを Skype for Business Server 2019 にインストールします。

1. 中央管理サーバーとなる Skype for Business Server 2019 サーバーで、Skype for Business Server 管理シェルが**RTCUniversalServerAdmins**グループのメンバーとしてインストールされているコンピューターにログオンします。 SQL Server データベース管理者のユーザー権限と権限も必要です。 
    
2. Skype for Business Server 管理シェルを開きます。
    
3. Skype for Business Server 管理シェルで、次のように入力します。 
    
   ```
   Enable-CsTopology
   ```

    > [!CAUTION]
    > 問題`Enable-CsTopology`が解決しない場合は、続行する前にコマンドの完了を妨げる問題を解決してください。 **Enable-CsTopology**方法で問題が発生した場合は、移行が失敗し、中央管理ストアがない状態でトポロジが残る場合があります。 
  
4. Skype for Business Server 2019 フロントエンドサーバーまたはフロントエンドプールの Skype for Business Server 管理シェルで、次のように入力します。 
    
   ```
   Move-CsManagementServer
   ```

5. Skype for Business Server 管理シェルには、サーバー、ファイルストア、データベースストア、現在の状態と提案された状態のサービス接続ポイントが表示されます。 情報を慎重に読み、目的のソースと行先であることを確認します。 続行する場合は「 **Y** 」、移動を停止する場合は**N**を入力します。 
    
6. **CsManagementServer**コマンドによって生成された警告またはエラーを確認し、解決します。 
    
7. Skype for Business server 2019 サーバーで、Skype for Business Server Deployment ウィザードを開きます。 
    
8. Skype for Business Server の展開ウィザードで、[ **skype for Business Server システムのインストールまたは更新**] をクリックし、[**手順 2: Skype For business Server コンポーネントのセットアップまたは削除**] をクリックし、[**次へ**] をクリックして概要を確認し、[完了] をクリックします。 ****. 
    
9. 従来のインストールサーバーで展開ウィザードを開きます。 
    
10. Skype for Business Server の展開ウィザードで、[ **skype for Business Server システムのインストールまたは更新**] をクリックし、[**手順 2: Skype For business Server コンポーネントのセットアップまたは削除**] をクリックし、[**次へ**] をクリックして概要を確認し、[完了] をクリックします。 ****. 
    
11. Skype for Business Server 2019 サーバーを再起動します。 これが必要なのは、サーバーの全体管理サーバーデータベースにアクセスするためのグループメンバーシップが変更されたためです。
    
12. 新しい中央管理ストアでのレプリケーションが行われていることを確認するには、Skype for Business Server 管理シェルで次のように入力します。 
    
    ```
    Get-CsManagementStoreReplicationStatus
    ```

    > [!NOTE]
    > レプリケーションは、現在のすべてのレプリカの更新に時間がかかる場合があります。 
  
## <a name="to-remove-legacy-install-central-management-store-files-after-a-move"></a>移行後に、従来の中央管理ストアのファイルを削除するには

1. 従来のインストールサーバーで、Skype for Business Server 管理シェルが**RTCUniversalServerAdmins**グループのメンバーとしてインストールされているコンピューターにログオンします。 SQL Server データベース管理者のユーザー権限と権限も必要です。 
    
2. Skype for Business Server 管理シェルを開く
    
    > [!CAUTION]
    > 複製が完了し、安定しているまで、以前のデータベースファイルの削除は行わないでください。 複製処理を完了する前にファイルを削除すると、レプリケーションプロセスが中断され、新しく移動した中央管理サーバーは不明な状態のままになります。 **CsManagementStoreReplicationStatus**コマンドレットを使用して、レプリケーションの状態を確認します。 
  
3. 従来のセントラルマネジメントサーバーから全体管理ストアデータベースファイルを削除するには、次のように入力します。
    
   ```
   Uninstall-CsDatabase -CentralManagementDatabase -SqlServerFqdn <FQDN of SQL Server> -SqlInstanceName <Name of source server>
   ```

    次に例を示します。
    
   ```
   Uninstall-CsDatabase -CentralManagementDatabase -SqlServerFqdn sql.contoso.net -SqlInstanceName rtc
   ```

    _ \<SQL Server\>の FQDN_は、Enterprise Edition 展開または Standard edition サーバーの fqdn のレガシインストールバックエンドサーバーです。 
    

