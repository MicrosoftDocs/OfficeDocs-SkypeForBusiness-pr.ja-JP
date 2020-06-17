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
localization_priority: Normal
description: アーカイブサーバーを削除した後、プールデータをホストしていた SQL Server データベースを削除できます。 次の手順を使用して、トポロジビルダーから定義を削除し、データベースサーバーからデータベースとログファイルを削除します。
ms.openlocfilehash: f8a08b7ea73fa954726bdef986e5a28919c90ceb
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/16/2020
ms.locfileid: "44753309"
---
# <a name="remove-the-sql-server-database-for-an-archiving-server"></a>アーカイブ サーバー用の SQL Server データベースの削除

アーカイブサーバーを削除した後、プールデータをホストしていた SQL Server データベースを削除できます。 次の手順を使用して、トポロジビルダーから定義を削除し、データベースサーバーからデータベースとログファイルを削除します。
  
## <a name="to-remove-the-sql-server-database-using-topology-builder"></a>トポロジビルダーを使用して SQL Server データベースを削除するには

1. Skype for Business Server 2019 フロントエンドサーバーで、トポロジビルダーを開きます。
    
2. トポロジビルダーで、[**共有コンポーネント**] に移動し、[ **sql server ストア**] をクリックし、削除または再構成したアーカイブサーバーに関連付けられている sql server インスタンスを右クリックして、[**削除**] をクリックします。
    
3. トポロジを公開し、レプリケーションの状態を確認します。 
    
## <a name="to-remove-the-database-files-from-the-sql-server"></a>SQL Server からデータベース ファイルを削除するには

1. SQL Server のデータベースを削除するには、データベース ファイルを削除している SQL Server の SQL Server sysadmins グループのメンバーである必要があります。 
    
2. Skype for Business Server 管理シェルを開きます。
    
3. コマンドラインで、次のように入力します。
    
   ```PowerShell
   Uninstall-CsDataBase -DatabaseType Archiving -SqlServerFqdn <FQDN> [-SqlInstanceName <instance>]
   ```

    ここで、 _\<FQDN\>_ はデータベースサーバーの完全修飾ドメイン名 (FQDN)、 _\<instance\>_ は名前付きデータベースインスタンス (定義されている場合) です。 
    
4. **Uninstall**コマンドレットを実行してアクションを確認するように求めるメッセージが表示されたら、情報を読み、Y (または enter) キーを押して続行するか、N キーを押してコマンドレットを停止します (エラーがある場合)。 
    

