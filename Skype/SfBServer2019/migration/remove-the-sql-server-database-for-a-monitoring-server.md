---
title: 監視サーバー用の SQL Server データベースの削除
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: 監視サーバーを削除した後で、サーバーデータをホストしている SQL Server データベースを削除できます。 次の手順を使用して、Topology Builder から定義を削除し、データベースサーバーからデータベースとログファイルを削除します。
ms.openlocfilehash: 275c69f2c35428bcff2d12799cad3fbc129abc23
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2020
ms.locfileid: "41812825"
---
# <a name="remove-the-sql-server-database-for-a-monitoring-server"></a>監視サーバー用の SQL Server データベースの削除

監視サーバーを削除した後で、サーバーデータをホストしている SQL Server データベースを削除できます。 次の手順を使用して、Topology Builder から定義を削除し、データベースサーバーからデータベースとログファイルを削除します。
  
## <a name="to-remove-the-sql-server-database-using-topology-builder"></a>トポロジビルダーを使用して SQL Server データベースを削除するには

1. Skype for Business Server 2019 フロントエンドサーバーで、[トポロジビルダー] を開きます。
    
2. [トポロジビルダー] で、[**共有コンポーネント**] に移動し、[ **sql server ストア**] で、削除または再構成された監視サーバーに関連付けられている sql server インスタンスを右クリックし、[**削除**] をクリックします。
    
3. トポロジを公開し、レプリケーションの状態を確認します。
    
## <a name="to-remove-the-database-files-from-the-sql-server"></a>SQL Server からデータベースファイルを削除するには

1. SQL Server ベースのサーバー上のデータベースを削除するには、データベースファイルを削除する SQL Server サーバーの SQL Server の [データファイル] グループのメンバーである必要があります。
    
2. Skype for Business Server 管理シェルを開きます。
    
3. コマンドラインで、次のように入力します。
    
   ```PowerShell
   Uninstall-CsDataBase -DatabaseType Monitoring -SqlServerFqdn <FQDN> [-SqlInstanceName <instance>]
   ```

    ここ_ \<で\> 、fqdn_はデータベースサーバーの完全修飾ドメイン名 (FQDN) で、 _ \<[\>インスタンス_] はオプションの名前付きデータベースインスタンスです。 
    
4. **CsDataBase**コマンドレットで操作の確認を求めるメッセージが表示されたら、情報を読み、Y (または enter) キーを押して続行するか、または N キーを押してコマンドレットを停止するか (エラーがある場合)、enter キーを押します。 
    

