---
title: 中央管理サーバーを移動する
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: Skype for business Server 2019 に移行した後、中央管理サーバーを Skype for Business Server 2019 フロントエンドサーバーまたはプールに移動してから、従来のサーバーを削除する必要があります。
ms.openlocfilehash: b5412e1b538627c50c3f2a98a5b68c64364f00a9
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/16/2020
ms.locfileid: "44752469"
---
# <a name="move-the-legacy-central-management-server-to-skype-for-business-server-2019"></a>従来の中央管理サーバーを Skype for Business Server 2019 に移動する

Skype for Business Server 2019 に移行した後、および従来のサーバーを削除する前に、中央管理サーバーを Skype for Business Server 2019 フロントエンドサーバーまたはプールに移動する必要があります。 
  
中央管理サーバーは、中央管理サーバーを含むフロントエンドサーバーによって、データベースの読み取り/書き込みコピーが保持されている単一のマスター/マルチレプリカシステムです。 トポロジ内の各コンピューター (中央管理サーバーを含むフロントエンドサーバーを含む) には、セットアップと展開時にコンピューターにインストールされた SQL Server データベース内の中央管理ストアデータの読み取り専用コピーがあります (既定では RTCLOCAL という名前が付いています)。 ローカルデータベースは、すべてのコンピューターでサービスとして実行される Skype for Business Server Replica Replicator エージェントを使用して、レプリカの更新を受信します。 中央管理サーバーとローカルレプリカの実際のデータベースの名前は XDS で、このファイルは xds ファイルと xds ファイルで構成されています。 Master データベースの場所は、Active Directory ドメインサービスのサービスコントロールポイント (SCP) によって参照されます。 中央管理サーバーを使用して Skype for Business Server を管理および構成するすべてのツール SCP を使用して、中央管理ストアを特定します。
  
中央管理サーバーを正常に移動したら、元のフロントエンドサーバーから中央管理サーバーデータベースを削除する必要があります。 中央管理サーバーデータベースの削除の詳細については、「[フロントエンドプールの SQL Server データベースを削除](remove-the-sql-server-database-for-a-front-end-pool.md)する」を参照してください。
  
Skype for business Server 管理シェルの Windows PowerShell コマンドレット**move-csmanagementserver**を使用して、データベースを従来の sql server データベースから Skype For business SERVER 2019 sql server データベースに移動し、次に、Skype For business Server 2019 Central Management サーバーの場所を指すように SCP を更新します。 
  
中央管理サーバーを移動する前に、このセクションの手順を使用して、Skype for Business Server 2019 フロントエンドサーバーを準備します。
  
## <a name="to-prepare-an-enterprise-edition-front-end-pool"></a>Enterprise Edition フロントエンドプールを準備するには

1. 中央管理サーバーを再配置する Skype for Business Server 2019 Enterprise Edition フロントエンドプールで、Skype for business Server 管理シェルがインストールされているコンピューターに、 **RTCUniversalServerAdmins**グループのメンバーとしてログオンします。 また、中央管理ストアをインストールするデータベースに対して、SQL Server データベース sysadmin のユーザー権限とアクセス許可も持っている必要があります。 
    
2. Skype for Business Server 管理シェルを開きます。
    
3. Skype for business server 2019 の SQL Server データベースに新しい中央管理ストアを作成するには、Skype for Business Server 管理シェルで、次のように入力します。
    
   ```PowerShell
   Install-CsDatabase -CentralManagementDatabase -SQLServerFQDN <FQDN of your SQL Server> -SQLInstanceName <name of instance>
   ```

4. **Skype For Business Server フロントエンド**サービスの状態が**開始**していることを確認します。
    
## <a name="to-prepare-a-standard-edition-front-end-server"></a>Standard Edition フロントエンドサーバーを準備するには

1. 中央管理サーバーを再配置する Skype for Business Server 2019 Standard Edition フロントエンドサーバーで、Skype for business Server 管理シェルがインストールされているコンピューターに、 **RTCUniversalServerAdmins**グループのメンバーとしてログオンします。 
    
2. Skype for Business Server 展開ウィザードを開きます。
    
3. Skype for Business Server の展開ウィザードで、[**最初の Standard Edition サーバーの準備**] をクリックします。
    
4. [**コマンドの実行**] ページで、中央管理サーバーとして SQL Server Express がインストールされます。 必要なファイアウォール規則が作成されます。 データベースと必要なソフトウェアのインストールが完了したら、[**完了**] をクリックします。
    
    > [!NOTE]
    > 最初のインストールには、コマンド出力の概要画面に表示される更新がないと、しばらく時間がかかる場合があります。 これは SQL Server Express がインストールされているためです。 データベースのインストールを監視する必要がある場合は、タスクマネージャーを使用してセットアップを監視します。 
  
5. Skype for business Server 2019 Standard Edition フロントエンドサーバーに新しい中央管理ストアを作成するには、Skype for Business Server 管理シェルで、次のように入力します。 
    
   ```PowerShell
   Install-CsDatabase -CentralManagementDatabase -SQLServerFQDN <FQDN of your Standard Edition Server> -SQLInstanceName <name of instance - RTC by default>
   ```

6. **Skype For Business Server フロントエンド**サービスの状態が**開始**していることを確認します。
    
## <a name="to-move-the-legacy-installs-central-management-server-to-skype-for-business-server-2019"></a>レガシーを移行するには、中央管理サーバーを Skype for Business Server 2019 にインストールします。

1. 中央管理サーバーとなる Skype for Business Server 2019 サーバーで、Skype for business Server 管理シェルがインストールされているコンピューターに、 **RTCUniversalServerAdmins**グループのメンバーとしてログオンします。 また、SQL Server データベース管理者のユーザー権限とアクセス許可を持っている必要があります。 
    
2. Skype for Business Server 管理シェルを開きます (管理者として実行します)。
    
3. Skype for Business Server 管理シェルで、次のように入力します。 
    
   ```PowerShell
   Enable-CsTopology
   ```

    > [!CAUTION]
    > `Enable-CsTopology`成功しない場合は、続行する前に、コマンドの完了を妨げている問題を解決してください。 **Enable-CsTopology テクノロジ**が成功しなかった場合、移動は失敗し、中央管理ストアがない状態で、トポロジがそのまま残る場合があります。 
  
4. Skype for business Server 2019 のフロントエンドサーバーまたはフロントエンドプールの場合は、Skype for Business Server 管理シェルで、次のように入力します。 
    
   ```PowerShell
   Move-CsManagementServer
   ```

5. Skype for Business Server 管理シェルは、サーバー、ファイルストア、データベースストア、および現在の状態のサービス接続ポイントと提案された状態を表示します。 この情報を注意深く読み、移動元と移動先が意図したものであることを確認します。 続行するには「**Y**」を入力し、移動を中止するには「**N**」を入力します。 
    
6. **Move-CsManagementServer** コマンドで表示される警告またはエラーを確認して解決します。 
    
7. Skype for Business Server 2019 サーバーで、Skype for Business Server 展開ウィザードを開きます。 
    
8. Skype for Business server の展開ウィザードで、[ **skype for Business Server システムのインストールまたは更新**] をクリックし、[**ステップ 2: Skype For business Server コンポーネントのセットアップまたは削除**] をクリックし、[**次へ**] をクリックして概要を確認し、[**完了**] をクリックします。 
    
9. 従来のインストールサーバーで、展開ウィザードを開きます。 
    
10. Skype for Business server の展開ウィザードで、[ **skype for Business Server システムのインストールまたは更新**] をクリックし、[**ステップ 2: Skype For business Server コンポーネントのセットアップまたは削除**] をクリックし、[**次へ**] をクリックして概要を確認し、[**完了**] をクリックします。 
    
11. Skype for Business Server 2019 サーバーを再起動します。 これは、グループメンバーシップの変更によって中央管理サーバーデータベースにアクセスするために必要です。
    
12. 新しい中央管理ストアとのレプリケーションが行われていることを確認するには、Skype for Business Server 管理シェルで、次のように入力します。 
    
    ```PowerShell
    Get-CsManagementStoreReplicationStatus
    ```

    > [!NOTE]
    > レプリケーションが現在のすべてのレプリカを更新するには、少し時間がかかる場合があります。 
  
## <a name="to-remove-legacy-install-central-management-store-files-after-a-move"></a>移行後に従来の中央管理ストアファイルを削除するには

1. 従来のインストールサーバーで、Skype for Business Server 管理シェルがインストールされているコンピューターに、 **RTCUniversalServerAdmins**グループのメンバーとしてログオンします。 また、SQL Server データベース管理者のユーザー権限とアクセス許可を持っている必要があります。 
    
2. Skype for Business Server 管理シェルを開く
    
    > [!CAUTION]
    > レプリケーションが完了して安定するまで、以前のデータベース ファイルを削除しないでください。 レプリケーションを完了する前にファイルを削除すると、レプリケーションプロセスが中断され、新しく移動した中央管理サーバーが不明な状態のままになります。 レプリケーションの状態を確認するには、**Get-CsManagementStoreReplicationStatus** コマンドレットを使用します。 
  
3. 中央管理ストアデータベースファイルをレガシインストールの中央管理サーバーから削除するには、次のように入力します。
    
   ```PowerShell
   Uninstall-CsDatabase -CentralManagementDatabase -SqlServerFqdn <FQDN of SQL Server> -SqlInstanceName <Name of source server>
   ```

    例:
    
   ```PowerShell
   Uninstall-CsDatabase -CentralManagementDatabase -SqlServerFqdn sql.contoso.net -SqlInstanceName rtc
   ```

    は、 _\<FQDN of SQL Server\>_ Enterprise Edition 展開の従来のバックエンドサーバー、または Standard Edition サーバーの FQDN のいずれかです。 
    

