---
title: フロント エンド プール用の SQL Server データベースの削除
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
description: フロント エンド プールを削除するか、別のデータベースを使用するプールを再構成した後、プール データをホストSQL Serverデータベースを削除できます。 トポロジ ビルダーから定義を削除し、データベース サーバーからデータベース ファイルとログ ファイルを削除するには、次の手順を実行します。
ms.openlocfilehash: 01a28beabb85aa7cda25043680537f519872d58654dee5418f03ae9f5f702a19
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2021
ms.locfileid: "54340323"
---
# <a name="remove-the-sql-server-database-for-a-front-end-pool"></a>フロント エンド プール用の SQL Server データベースの削除

フロント エンド プールを削除するか、別のデータベースを使用するプールを再構成した後、プール データをホストSQL Serverデータベースを削除できます。 トポロジ ビルダーから定義を削除し、データベース サーバーからデータベース ファイルとログ ファイルを削除するには、次の手順を実行します。
  
## <a name="to-remove-the-sql-server-database-using-topology-builder"></a>トポロジ ビルダーを使用SQL Serverデータベースを削除するには

1. 2019 Skype for Business Server 2019 フロントエンド サーバーからトポロジ ビルダーを開き、既存のトポロジをダウンロードします。 
    
2. トポロジ ビルダーで、[共有コンポーネント] に移動し **、[SQL Server ストア**] に移動し、削除または再構成されたフロント エンド プールに関連付けられている SQL Server インスタンスを右クリックし、[削除] をクリック **します**。
    
3. トポロジを公開し、レプリケーションの状態を確認します。 
    
## <a name="to-remove-user-and-application-databases-from-the-sql-server"></a>ユーザー データベースとアプリケーション データベースをサーバーからSQLするには

1. SQL サーバー上のデータベースを削除するには、データベース ファイルを削除する SQL サーバーの SQL Server sysadmins グループのメンバーである必要があります。 
    
2. [管理Skype for Business Server] を開きます。
    
3. プール ユーザー ストアのデータベースを削除するには、次のように入力します。
    
   ```PowerShell
   Uninstall-CsDataBase -DatabaseType User -SqlServerFqdn <FQDN> [-SqlInstanceName <instance>]
   ```

    ここで  _\<FQDN\>_ 、データベース サーバーの完全修飾ドメイン名 (FQDN) は、名前付きデータベース インスタンス (つまり、定義されている場合)  _\<instance\>_ です。 
    
4. プール アプリケーション ストアのデータベースを削除するには、次のように入力します。
    
   ```PowerShell
   Uninstall-CsDataBase -DatabaseType Application -SqlServerFqdn <FQDN> [-SqlInstanceName <instance>]
   ```

    データベース サーバーの FQDN はここで、名前付きデータベース インスタンス (つまり、定義されている場合  _\<FQDN\>_  _\<instance\>_ ) です。 
    
5. **Uninstall-CsDataBase** コマンドレットで、アクションの確認、情報の読み取り、Y (または Enter) キーを押して続行するように求めるメッセージが表示されたら、N キーを押してから Enter キーを押します (エラーがある場合)。 
    

