---
title: フロントエンド プール用の SQL Server データベースの削除
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
description: フロントエンドプールを削除した後、または別のデータベースを使用するようにプールを再構成した後は、プールデータをホストしていた SQL Server データベースを削除できます。 次の手順を使用して、トポロジビルダーから定義を削除し、データベースサーバーからデータベースとログファイルを削除します。
ms.openlocfilehash: 9047486708b92c07e6ec099fce43ec4c708fa900
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/16/2020
ms.locfileid: "44753409"
---
# <a name="remove-the-sql-server-database-for-a-front-end-pool"></a>フロントエンド プール用の SQL Server データベースの削除

フロントエンドプールを削除した後、または別のデータベースを使用するようにプールを再構成した後は、プールデータをホストしていた SQL Server データベースを削除できます。 次の手順を使用して、トポロジビルダーから定義を削除し、データベースサーバーからデータベースとログファイルを削除します。
  
## <a name="to-remove-the-sql-server-database-using-topology-builder"></a>トポロジビルダーを使用して SQL Server データベースを削除するには

1. Skype for Business Server 2019 フロントエンドサーバーから、トポロジビルダーを開き、既存のトポロジをダウンロードします。 
    
2. [トポロジビルダー] で、[**共有コンポーネント**] に移動し、[ **sql server ストア**] を選択して、削除または再構成したフロントエンドプールに関連付けられている SQL server インスタンスを右クリックし、[**削除**] をクリックします。
    
3. トポロジを公開し、レプリケーションの状態を確認します。 
    
## <a name="to-remove-user-and-application-databases-from-the-sql-server"></a>SQL server からユーザーおよびアプリケーションデータベースを削除するには

1. SQL server 上のデータベースを削除するには、データベースファイルを削除する対象の SQL server の SQL Server の [ユーザー] グループのメンバーである必要があります。 
    
2. Skype for Business Server 管理シェルを開きます。
    
3. プール ユーザー ストアのデータベースを削除するには、次のように入力します。
    
   ```PowerShell
   Uninstall-CsDataBase -DatabaseType User -SqlServerFqdn <FQDN> [-SqlInstanceName <instance>]
   ```

    ここで、 _\<FQDN\>_ はデータベースサーバーの完全修飾ドメイン名 (FQDN)、 _\<instance\>_ は名前付きデータベースインスタンス (定義されている場合) です。 
    
4. プール アプリケーション ストアのデータベースを削除するには、次のように入力します。
    
   ```PowerShell
   Uninstall-CsDataBase -DatabaseType Application -SqlServerFqdn <FQDN> [-SqlInstanceName <instance>]
   ```

    ここで、 _\<FQDN\>_ はデータベースサーバーの FQDN、は _\<instance\>_ 名前付きデータベースインスタンス (定義されている場合) です。 
    
5. **Uninstall**コマンドレットを実行してアクションを確認するように求めるメッセージが表示されたら、情報を読み、Y (または enter) キーを押して続行するか、N キーを押してコマンドレットを停止します (エラーがある場合)。 
    

