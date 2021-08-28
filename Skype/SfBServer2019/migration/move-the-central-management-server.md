---
title: サーバーの全体管理サーバーの移動
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
description: Skype for Business Server 2019 に移行した後、従来のサーバーを削除する前に、サーバーの全体管理サーバーを Skype for Business Server 2019 フロント エンド サーバーまたはプールに移動する必要があります。
ms.openlocfilehash: 5c3d090f762904aa5f076033a68e46139b1e84e4
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/26/2021
ms.locfileid: "58618283"
---
# <a name="move-the-legacy-central-management-server-to-skype-for-business-server-2019"></a>従来のサーバーの全体管理サーバーを 2019 年Skype for Business Serverする

Skype for Business Server 2019 に移行した後、従来のサーバーを削除する前に、中央管理サーバーを Skype for Business Server フロントエンド サーバーまたはプールに移動する必要があります。 
  
中央管理サーバーは単一のマスター/複数レプリカ システムで、データベースの読み取り/書き込みコピーは、中央管理サーバーを含むフロントエンド サーバーによって保持されます。 サーバーの全体管理サーバーを含むフロントエンド サーバーを含むトポロジ内の各コンピューターには、セットアップと展開中に、SQL Server データベース (既定では RTCLOCAL という名前) にインストールされている中央管理ストア データの読み取り専用コピーがあります。 ローカル データベースは、すべてのコンピューターでサービスとしてSkype for Business Serverレプリカ レプリケーター エージェントを使用してレプリカ更新プログラムを受信します。 サーバーの全体管理サーバーとローカル レプリカ上の実際のデータベースの名前は、xds.mdf ファイルと xds.ldf ファイルで構成される XDS です。 マスター データベースの場所は、Active Directory ドメイン サービスのサービス コントロール ポイント (SCP) によって参照されます。 サーバーの全体管理サーバーを使用してサーバーを管理および構成Skype for Business Server、SCP を使用して中央管理ストアを検索します。
  
サーバーの全体管理サーバーを正常に移動したら、サーバーの全体管理サーバー データベースを元のフロント エンド サーバーから削除する必要があります。 サーバーの全体管理サーバー データベースの削除の詳細については、「フロント エンド プールSQL Serverデータベースを削除する[」を参照してください](remove-the-sql-server-database-for-a-front-end-pool.md)。
  
Skype for Business Server 管理シェルの Windows PowerShell コマンドレット **Move-CsManagementServer** を使用して、従来のインストール SQL Server データベースから Skype for Business Server 2019 SQL Server データベースにデータベースを移動し、SCP を更新して Skype for Business Server 2019 サーバーの全体管理サーバーの場所をポイントします。 
  
サーバーの全体管理サーバーを移動する前に、Skype for Business Server 2019 フロントエンド サーバーを準備するには、このセクションの手順を使用します。
  
## <a name="to-prepare-an-enterprise-edition-front-end-pool"></a>フロントエンド プールEnterprise Editionを準備する

1. 中央管理サーバーを再配置する Skype for Business Server 2019 Enterprise Edition フロントエンド プールで、Skype for Business Server 管理シェルが **RTCUniversalServerAdmins** グループのメンバーとしてインストールされているコンピューターにログオンします。 また、サーバーの全体管理SQL Serverインストールするデータベースに対するデータベース sysadmin ユーザー権限とアクセス許可を持っている必要があります。 
    
2. 管理シェルSkype for Business Server開きます。
    
3. 新しいサーバーの全体管理ストアを 2019 Skype for Business Server データベースにSQL Serverするには、次Skype for Business Server入力します。
    
   ```PowerShell
   Install-CsDatabase -CentralManagementDatabase -SQLServerFQDN <FQDN of your SQL Server> -SQLInstanceName <name of instance>
   ```

4. フロントエンド サービスの状態が [開始 **Skype for Business Serverを確認****します**。
    
## <a name="to-prepare-a-standard-edition-front-end-server"></a>フロントエンド サーバー Standard Edition準備するには

1. 中央管理サーバーを再配置する Skype for Business Server Standard Edition フロントエンド サーバーで **、rtCUniversalServerAdmins** グループのメンバーとして Skype for Business Server 管理シェルがインストールされているコンピューターにログオンします。 
    
2. 展開ウィザードSkype for Business Server開きます。
    
3. [展開ウィザードSkype for Business Serverで、[最初のサーバーを準備 **する] Standard Editionクリックします**。
    
4. [コマンド **の実行] ページ** でSQL Server Expressサーバーの全体管理サーバーとしてインストールされます。 必要なファイアウォール規則が作成されます。 データベースと必要なソフトウェアのインストールが完了したら、[**完了**] をクリックします。
    
    > [!NOTE]
    > 最初のインストールには、コマンド出力の概要画面に表示される更新プログラムがない状態で、時間がかかる場合があります。 これは、アプリケーションのインストールが原因SQL Server Express。 データベースのインストールを監視する必要がある場合は、タスク マネージャーを使用してセットアップを監視します。 
  
5. 2019 年 3 月 2019 Skype for Business Serverフロント エンド Standard Editionに新しい中央管理ストアを作成するには、「Skype for Business Server」と入力します。 
    
   ```PowerShell
   Install-CsDatabase -CentralManagementDatabase -SQLServerFQDN <FQDN of your Standard Edition Server> -SQLInstanceName <name of instance - RTC by default>
   ```

6. フロントエンド サービスの状態が [開始 **Skype for Business Serverを確認****します**。
    
## <a name="to-move-the-legacy-installs-central-management-server-to-skype-for-business-server-2019"></a>従来のインストールのサーバーの全体管理を 2019 Skype for Business Serverするには

1. サーバーのSkype for Business Server 2019 サーバーで **、rtCUniversalServerAdmins** グループのメンバーとして Skype for Business Server 管理シェルがインストールされているコンピューターにログオンします。 また、データベース管理者のSQL Server権限とアクセス許可を持っている必要があります。 
    
2. 管理Skype for Business Serverを開きます (管理者として実行)。
    
3. [管理シェルSkype for Business Serverで、次の入力を行います。 
    
   ```PowerShell
   Enable-CsTopology
   ```

    > [!CAUTION]
    > 成功 `Enable-CsTopology` しない場合は、続行する前にコマンドが完了しない問題を解決します。 **Enable-CsTopology** が成功しない場合、移動は失敗し、サーバーの全体管理ストアがない状態でトポロジが残る可能性があります。 
  
4. 2019 Skype for Business Server サーバーまたはフロント エンド プールの [管理シェル] で、次Skype for Business Server入力します。 
    
   ```PowerShell
   Move-CsManagementServer
   ```

5. Skype for Business Server管理シェルには、現在の状態と提案された状態のサーバー、ファイル ストア、データベース ストア、およびサービス接続ポイントが表示されます。 この情報を注意深く読み、移動元と移動先が意図したものであることを確認します。 続行するには「**Y**」を入力し、移動を中止するには「**N**」を入力します。 
    
6. **Move-CsManagementServer** コマンドで表示される警告またはエラーを確認して解決します。 
    
7. 2019 Skype for Business Serverで、[展開ウィザード] Skype for Business Server開きます。 
    
8. [Skype for Business Server 展開ウィザードで **、[Skype for Business Server システム** のインストールまたは更新] をクリックし、[手順 **2:** Skype for Business Server コンポーネントのセットアップまたは削除]をクリックし、[次へ] をクリックし、概要を確認し、[完了] をクリック **します**。 
    
9. 従来のインストール サーバーで、展開ウィザードを開きます。 
    
10. [Skype for Business Server 展開ウィザードで **、[Skype for Business Server システム** のインストールまたは更新] をクリックし、[手順 **2:** Skype for Business Server コンポーネントのセットアップまたは削除]をクリックし、[次へ] をクリックし、概要を確認し、[完了] をクリック **します**。 
    
11. 2019 Skype for Business Server再起動します。 これは、サーバーの全体管理サーバー データベースにアクセスするグループ メンバーシップの変更のために必要です。
    
12. 新しいサーバーの全体管理ストアでのレプリケーションが行なSkype for Business Server入力します。 
    
    ```PowerShell
    Get-CsManagementStoreReplicationStatus
    ```

    > [!NOTE]
    > レプリケーションが現在のすべてのレプリカを更新するには、少し時間がかかる場合があります。 
  
## <a name="to-remove-legacy-install-central-management-store-files-after-a-move"></a>移動後に従来のインストールの中央管理ストア ファイルを削除するには

1. 従来のインストール サーバーで **、RTCUniversalServerAdmins** グループのメンバーとして Skype for Business Server 管理シェルがインストールされているコンピューターにログオンします。 また、データベース管理者のSQL Server権限とアクセス許可を持っている必要があります。 
    
2. 管理Skype for Business Serverを開く
    
    > [!CAUTION]
    > レプリケーションが完了して安定するまで、以前のデータベース ファイルを削除しないでください。 レプリケーションを完了する前にファイルを削除すると、レプリケーション プロセスが中断され、新しく移動されたサーバーの全体管理サーバーは不明な状態になります。 レプリケーションの状態を確認するには、**Get-CsManagementStoreReplicationStatus** コマンドレットを使用します。 
  
3. 従来のインストールのサーバーの全体管理サーバーからサーバーの全体管理ストア データベース ファイルを削除するには、次の入力を行います。
    
   ```PowerShell
   Uninstall-CsDatabase -CentralManagementDatabase -SqlServerFqdn <FQDN of SQL Server> -SqlInstanceName <Name of source server>
   ```

    次に例を示します。
    
   ```PowerShell
   Uninstall-CsDatabase -CentralManagementDatabase -SqlServerFqdn sql.contoso.net -SqlInstanceName rtc
   ```

    ここで、従来のインストールバック エンド サーバーは、Enterprise Editionサーバーの _\<FQDN of SQL Server\>_ FQDN Standard Editionします。 
    

