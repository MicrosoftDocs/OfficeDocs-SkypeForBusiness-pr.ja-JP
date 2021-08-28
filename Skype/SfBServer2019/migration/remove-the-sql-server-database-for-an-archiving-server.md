---
title: アーカイブ サーバー用の SQL Server データベースの削除
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
description: アーカイブ サーバーを削除した後、プール データをホストSQL Serverデータベースを削除できます。 トポロジ ビルダーから定義を削除し、データベース サーバーからデータベース ファイルとログ ファイルを削除するには、次の手順を実行します。
ms.openlocfilehash: 9305109e38c265b919d9ec22fa626d27efb19225
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/26/2021
ms.locfileid: "58621919"
---
# <a name="remove-the-sql-server-database-for-an-archiving-server"></a>アーカイブ サーバー用の SQL Server データベースの削除

アーカイブ サーバーを削除した後、プール データをホストSQL Serverデータベースを削除できます。 トポロジ ビルダーから定義を削除し、データベース サーバーからデータベース ファイルとログ ファイルを削除するには、次の手順を実行します。
  
## <a name="to-remove-the-sql-server-database-using-topology-builder"></a>トポロジ ビルダーを使用SQL Serverデータベースを削除するには

1. 2019 Skype for Business Server エンド サーバーで、トポロジ ビルダーを開きます。
    
2. トポロジ ビルダーで、[共有コンポーネント] に移動し **、[SQL Server** ストア] に移動し、削除または再構成されたアーカイブ サーバーに関連付けられている SQL Server インスタンスを右クリックし、[削除] をクリックします。
    
3. トポロジを公開し、レプリケーションの状態を確認します。 
    
## <a name="to-remove-the-database-files-from-the-sql-server"></a>SQL Server からデータベース ファイルを削除するには

1. SQL Server のデータベースを削除するには、データベース ファイルを削除している SQL Server の SQL Server sysadmins グループのメンバーである必要があります。 
    
2. 管理シェルSkype for Business Server開きます。
    
3. コマンドラインで、次のように入力します。
    
   ```PowerShell
   Uninstall-CsDataBase -DatabaseType Archiving -SqlServerFqdn <FQDN> [-SqlInstanceName <instance>]
   ```

    ここで  _\<FQDN\>_ 、データベース サーバーの完全修飾ドメイン名 (FQDN) は、名前付きデータベース インスタンス (つまり、定義されている場合)  _\<instance\>_ です。 
    
4. **Uninstall-CsDataBase** コマンドレットで、アクションの確認、情報の読み取り、Y (または Enter) キーを押して続行するように求めるメッセージが表示されたら、N キーを押してから Enter キーを押します (エラーがある場合)。 
    

