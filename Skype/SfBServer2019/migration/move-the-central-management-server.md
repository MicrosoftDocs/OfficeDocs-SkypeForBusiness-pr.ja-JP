---
title: 中央管理サーバーを移動します。
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: ビジネス サーバー 2019 の Skype に移行した後は、中央管理サーバーを移動する、Skype ビジネス 2019 フロント エンド サーバーまたはプールのレガシ サーバーを削除する前にする必要があります。
ms.openlocfilehash: dc85548a3c81e55267bc0ed3a32e53860e4bce09
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "32231575"
---
# <a name="move-the-legacy-central-management-server-to-skype-for-business-server-2019"></a>ビジネス サーバー 2019 の Skype に従来のサーバーの全体管理サーバーを移動します。

ビジネス サーバー 2019、および従来のサーバーを削除する前に Skype に移行した後、Skype をビジネス 2019 フロント エンド サーバーまたはプールのサーバーの全体管理サーバーを移動する必要があります。 
  
サーバーの全体管理サーバーは、マスターまたは複数の単一のレプリカのシステムでは、中央管理サーバーが含まれるフロント エンド サーバーでデータベースの読み取り/書き込みコピーを保持する場所。 中央の管理サーバーを含むフロント エンド サーバーを含め、トポロジ内の各コンピューターには、中央管理ストア内のデータのセットアップ中にコンピューターにインストールされている SQL Server データベース (既定では RTCLOCAL という名前) の読み取り専用コピーし、展開します。 ローカル データベースは、すべてのコンピューターでサービスとして実行されるビジネス サーバー レプリカ複製エージェントの Skype を使用してレプリカの更新を受信します。 中央管理サーバーとローカルのレプリカには、実際のデータベースの名前は、XDS で、xds.mdf および xds.ldf ファイルの構成です。 Master データベースの場所は、Active Directory ドメイン サービスでサービス コントロール ポイント (SCP) によって参照されます。 管理し、Skype をビジネスのサーバーの構成をサーバーの全体管理サーバーを使用するすべてのツールでは、SCP を使用して、中央管理ストアを探します。
  
中央管理サーバーを正常に移動した後は、元のフロント エンド サーバーからサーバーの全体管理サーバーのデータベースを削除してください。 中央管理サーバーのデータベースを削除する方法の詳細については、[フロント エンド プールの SQL Server データベースを削除する](remove-the-sql-server-database-for-a-front-end-pool.md)を参照してください。
  
ビジネス サーバー 2019 の SQL Server データベースでは、Skype にレガシー インストールの SQL Server データベースからデータベースを移動し、更新するサーバー管理シェルをビジネス用の Skype に**移動 CsManagementServer**の Windows PowerShell コマンドレットを使用する、ビジネス 2019 中央管理サーバーの場所の Skype を指すように SCP です。 
  
ビジネス サーバー 2019 フロント エンド サーバーのサーバーの全体管理サーバーを移動する前に、Skype を準備するのに、このセクションの手順を使用します。
  
## <a name="to-prepare-an-enterprise-edition-front-end-pool"></a>エンタープライズ エディションのフロント エンド プールを準備するのには

1. ビジネス サーバー 2019 エンタープライズ エディションのフロント エンド プールのサーバーの全体管理サーバーに再配置する Skype、上には**RTCUniversalServerAdmins のメンバーとしてビジネス サーバー管理シェルの Skype がインストールされているコンピューターにログオンします。** グループです。 中央管理ストアをインストールするデータベースの SQL Server データベースのシステム管理者のユーザー権利とアクセス許可を必要することもあります。 
    
2. Skype をビジネス サーバー管理シェルを開きます。
    
3. ビジネス サーバー 2019 の SQL Server データベースでは、ビジネス サーバー管理シェルには、Skype での Skype の新しい中央管理ストアを作成するのには次のように入力します。
    
   ```
   Install-CsDatabase -CentralManagementDatabase -SQLServerFQDN <FQDN of your SQL Server> -SQLInstanceName <name of instance>
   ```

4. **Skype**ビジネス サーバーのフロント エンドのサービスの状態が**開始**ことを確認します。
    
## <a name="to-prepare-a-standard-edition-front-end-server"></a>標準 Edition フロント エンド サーバーを準備するのには

1. ビジネス サーバー 2019 標準エディション フロント エンド サーバーのサーバーの全体管理サーバーに再配置する Skype、上には**RTCUniversalServerAdmins のメンバーとしてビジネス サーバー管理シェルの Skype がインストールされているコンピューターにログオンします。** グループです。 
    
2. Skype をビジネス サーバーの展開ウィザードを開きます。
    
3. ビジネス サーバーの展開ウィザードの Skype、 **Standard Edition サーバーの最初の準備**をクリックします。
    
4. **コマンドの実行**] ページで、SQL Server Express は、サーバーの全体管理サーバーとしてインストールされます。 必要なファイアウォール規則が作成されます。 データベースと必要なソフトウェアのインストールが完了したら、[**完了**] をクリックします。
    
    > [!NOTE]
    > 最初のインストール コマンドの出力の概要] 画面に表示内容は更新に時間がかかります。 これは、SQL Server Express をインストールするためです。 データベースのインストールを監視する場合は、セットアップを監視するのにはタスク マネージャーを使用します。 
  
5. ビジネス サーバー 2019 標準 Edition フロント エンド サーバー、ビジネス サーバー管理シェルには、Skype では、Skype の新しい中央管理ストアを作成するのには次のように入力します。 
    
   ```
   Install-CsDatabase -CentralManagementDatabase -SQLServerFQDN <FQDN of your Standard Edition Server> -SQLInstanceName <name of instance - RTC by default>
   ```

6. **Skype**ビジネス サーバーのフロント エンドのサービスの状態が**開始**ことを確認します。
    
## <a name="to-move-the-legacy-installs-central-management-server-to-skype-for-business-server-2019"></a>従来の移動には、ビジネス サーバー 2019 用 Skype を中央の管理サーバーをインストールします。

1. ビジネス サーバー 2019 のサーバーにサーバーの全体管理サーバーの Skype、 **RTCUniversalServerAdmins**グループのメンバーとしてビジネス サーバー管理シェルの Skype がインストールされているコンピューターにログオンします。 SQL Server データベース管理者のユーザー権利とアクセス許可も必要です。 
    
2. Skype をビジネス サーバー管理シェルを開きます。
    
3. ビジネス サーバー管理シェルの Skype で次のように入力します。 
    
   ```
   Enable-CsTopology
   ```

    > [!CAUTION]
    > 場合`Enable-CsTopology`が失敗した場合は、コマンドが続行する前に完了するを防止する問題を解決します。 移動は失敗します、それが状態のままに、トポロジ**を有効にする CsTopology**が成功しない場合は、中央管理ストアが存在しません。 
  
4. ビジネス 2019 フロント エンド サーバーまたはフロント エンド プール、ビジネス サーバー管理シェルには、Skype の Skype で次のように入力します。 
    
   ```
   Move-CsManagementServer
   ```

5. Skype ビジネス サーバー管理シェルには、サーバー、ファイル ストア、データベース ストア、および現在の状態を提案済み状態のサービス接続ポイントが表示されます。 情報をよく読んで、目的のソースと宛先を確認します。 続けるには、 **Y**または移動を停止するのには**N**を入力します。 
    
6. **移動-CsManagementServer**コマンドによって生成されるエラーまたは警告を確認し、それらを解決します。 
    
7. ビジネス サーバー 2019 サーバーの Skype、Skype ビジネス サーバーの展開ウィザードを開きます。 
    
8. ビジネス サーバーの展開ウィザードの Skype は、の**インストールまたはサーバーのビジネス システムの更新プログラムの Skype**をクリックして**手順 2: セットアップまたは削除の Skype ビジネス サーバー コンポーネントの**は、[**次へ**] をクリックしの概要を確認 **[完了] をクリックし、**. 
    
9. 従来のサーバーをインストール、展開ウィザードを開きます。 
    
10. ビジネス サーバーの展開ウィザードの Skype は、の**インストールまたはサーバーのビジネス システムの更新プログラムの Skype**をクリックして**手順 2: セットアップまたは削除の Skype ビジネス サーバー コンポーネントの**は、[**次へ**] をクリックしの概要を確認 **[完了] をクリックし、**. 
    
11. ビジネス サーバー 2019 サーバーの Skype を再起動します。 グループ メンバーシップの変更をサーバーの全体管理サーバーのデータベースにアクセスするために必要です。
    
12. 新しい中央管理ストアで発生している、ビジネス サーバー管理シェルには、Skype では、そのレプリケーションを確認するのには次のように入力します。 
    
    ```
    Get-CsManagementStoreReplicationStatus
    ```

    > [!NOTE]
    > レプリケーション現在のすべてのレプリカを更新するのには時間がかかる場合があります。 
  
## <a name="to-remove-legacy-install-central-management-store-files-after-a-move"></a>移動後のレガシー インストールの中央管理ストアのファイルを削除するのには

1. 従来のサーバーのインストール、 **RTCUniversalServerAdmins**グループのメンバーとしてビジネス サーバー管理シェルの Skype がインストールされているコンピューターにログオンします。 SQL Server データベース管理者のユーザー権利とアクセス許可も必要です。 
    
2. ビジネス サーバー管理シェルの Skype を開く
    
    > [!CAUTION]
    > レプリケーションが完了し、安定するまでは、以前のデータベース ファイルの削除を続行しないでください。 レプリケーションを完了する前にファイルを削除する場合レプリケーション ・ プロセスを中断し、状態が不明で新しく移動されたサーバーの全体管理サーバーのままにします。 レプリケーションの状態を確認するのには、 **Get CsManagementStoreReplicationStatus**コマンドレットを使用します。 
  
3. レガシー インストールのサーバーの全体管理サーバーから中央管理ストアのデータベース ファイルを削除するのには次のように入力します。
    
   ```
   Uninstall-CsDatabase -CentralManagementDatabase -SqlServerFqdn <FQDN of SQL Server> -SqlInstanceName <Name of source server>
   ```

    次に例を示します。
    
   ```
   Uninstall-CsDatabase -CentralManagementDatabase -SqlServerFqdn sql.contoso.net -SqlInstanceName rtc
   ```

    場所、 _ \<SQL Server の FQDN\>_ は、従来のいずれか、Enterprise Edition または Standard Edition サーバーの FQDN のバック エンド サーバーをインストールします。 
    

