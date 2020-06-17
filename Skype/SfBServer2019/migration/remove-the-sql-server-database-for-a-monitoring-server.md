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
localization_priority: Normal
description: 監視サーバーを削除した後、サーバーデータをホストしていた SQL Server データベースを削除できます。 次の手順を使用して、トポロジビルダーから定義を削除し、データベースサーバーからデータベースとログファイルを削除します。
ms.openlocfilehash: 829e55175c9b9c85582aafe996bbbee0afdffa62
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/16/2020
ms.locfileid: "44753329"
---
# <a name="remove-the-sql-server-database-for-a-monitoring-server"></a>監視サーバー用の SQL Server データベースの削除

監視サーバーを削除した後、サーバーデータをホストしていた SQL Server データベースを削除できます。 次の手順を使用して、トポロジビルダーから定義を削除し、データベースサーバーからデータベースとログファイルを削除します。
  
## <a name="to-remove-the-sql-server-database-using-topology-builder"></a>トポロジビルダーを使用して SQL Server データベースを削除するには

1. Skype for Business Server 2019 フロントエンドサーバーで、トポロジビルダーを開きます。
    
2. トポロジビルダーで、[**共有コンポーネント**] に移動し、[ **sql server ストア**] をクリックし、削除または再構成された監視サーバーに関連付けられている sql server インスタンスを右クリックして、[**削除**] をクリックします。
    
3. トポロジを公開し、レプリケーションの状態を確認します。
    
## <a name="to-remove-the-database-files-from-the-sql-server"></a>SQL Server からデータベース ファイルを削除するには

1. SQL Server ベースのサーバーにあるデータベースを削除するためには、削除しようとしているデータベース ファイルがある SQL Server ベースのサーバーの SQL Server sysadmins グループのメンバーでなければなりません。
    
2. Skype for Business Server 管理シェルを開きます。
    
3. コマンドラインで、次のように入力します。
    
   ```PowerShell
   Uninstall-CsDataBase -DatabaseType Monitoring -SqlServerFqdn <FQDN> [-SqlInstanceName <instance>]
   ```

    ここ _\<FQDN\>_ で、はデータベースサーバーの完全修飾ドメイン名 (FQDN)、 _\<instance\>_ はオプションの名前付きデータベースインスタンスです。 
    
4. **Uninstall**コマンドレットを実行してアクションを確認するように求めるメッセージが表示されたら、情報を読み、Y (または enter) キーを押して続行するか、N キーを押してコマンドレットを停止します (エラーがある場合)。 
    

