---
title: 監視サーバー用の SQL Server データベースの削除
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
description: 監視サーバーを削除した後、サーバー データをホストSQL Serverデータベースを削除できます。 トポロジ ビルダーから定義を削除し、データベース サーバーからデータベース ファイルとログ ファイルを削除するには、次の手順を実行します。
ms.openlocfilehash: 23f58166c6a24680772d50c6bc484ba1bd02d754
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/26/2021
ms.locfileid: "58605756"
---
# <a name="remove-the-sql-server-database-for-a-monitoring-server"></a>監視サーバー用の SQL Server データベースの削除

監視サーバーを削除した後、サーバー データをホストSQL Serverデータベースを削除できます。 トポロジ ビルダーから定義を削除し、データベース サーバーからデータベース ファイルとログ ファイルを削除するには、次の手順を実行します。
  
## <a name="to-remove-the-sql-server-database-using-topology-builder"></a>トポロジ ビルダーを使用SQL Serverデータベースを削除するには

1. 2019 Skype for Business Server エンド サーバーで、トポロジ ビルダーを開きます。
    
2. トポロジ ビルダーで、[共有コンポーネント] に移動し **、[SQL Server** ストア] に移動し、削除または再構成された監視サーバーに関連付けられている SQL Server インスタンスを右クリックし、[削除] をクリック **します**。
    
3. トポロジを公開し、レプリケーションの状態を確認します。
    
## <a name="to-remove-the-database-files-from-the-sql-server"></a>SQL Server からデータベース ファイルを削除するには

1. SQL Server ベースのサーバーにあるデータベースを削除するためには、削除しようとしているデータベース ファイルがある SQL Server ベースのサーバーの SQL Server sysadmins グループのメンバーでなければなりません。
    
2. 管理シェルSkype for Business Server開きます。
    
3. コマンドラインで、次のように入力します。
    
   ```PowerShell
   Uninstall-CsDataBase -DatabaseType Monitoring -SqlServerFqdn <FQDN> [-SqlInstanceName <instance>]
   ```

    ここで  _\<FQDN\>_ 、データベース サーバーの完全修飾ドメイン名 (FQDN) は、オプションの  _\<instance\>_ 名前付きデータベース インスタンスです。 
    
4. **Uninstall-CsDataBase** コマンドレットで、アクションの確認、情報の読み取り、Y (または Enter) キーを押して続行するように求めるメッセージが表示されたら、N キーを押してから Enter キーを押します (エラーがある場合)。 
    

