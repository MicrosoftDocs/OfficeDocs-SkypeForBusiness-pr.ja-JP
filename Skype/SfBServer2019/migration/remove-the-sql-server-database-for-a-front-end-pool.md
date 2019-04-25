---
title: フロントエンド プール用の SQL Server データベースの削除
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: フロント エンド プールを削除した場合、または別のデータベースを使用するプールを再構成した後は、プールのデータをホストしていた SQL Server データベースを削除できます。 トポロジ ビルダーでは、定義を削除するのには次の手順を使用し、データベース ・ サーバからデータベースとログ ファイルを削除します。
ms.openlocfilehash: 4ba60a905d5f4cda56cf5277e1be2db80d906ca0
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "32231445"
---
# <a name="remove-the-sql-server-database-for-a-front-end-pool"></a>フロントエンド プール用の SQL Server データベースの削除

フロント エンド プールを削除した場合、または別のデータベースを使用するプールを再構成した後は、プールのデータをホストしていた SQL Server データベースを削除できます。 トポロジ ビルダーでは、定義を削除するのには次の手順を使用し、データベース ・ サーバからデータベースとログ ファイルを削除します。
  
## <a name="to-remove-the-sql-server-database-using-topology-builder"></a>トポロジ ビルダーを使用して SQL Server データベースを削除するには

1. ビジネス 2019 フロント エンド サーバーの Skype、トポロジ ビルダーを起動し、既存のトポロジをダウンロードします。 
    
2. トポロジ ビルダーでは、**コンポーネントを共有**し、 **SQL Server ストア**に移動、削除または再構成されたフロント エンド プールに関連付けられている SQL Server のインスタンスを右クリックし、[**削除**] をクリックします。
    
3. 、トポロジを公開し、レプリケーション ステータスを確認します。 
    
## <a name="to-remove-user-and-application-databases-from-the-sql-server"></a>ユーザーおよびアプリケーションのデータベースを SQL server から削除するのには

1. SQL サーバー上のデータベースを削除するには、データベース ファイルを削除する SQL server の SQL Server システム管理者グループのメンバーをする必要があります。 
    
2. Skype をビジネス サーバー管理シェルを開きます。
    
3. プールのユーザー ストアのデータベースを削除するのには次のように入力します。
    
   ```
   Uninstall-CsDataBase -DatabaseType User -SqlServerFqdn <FQDN> [-SqlInstanceName <instance>]
   ```

    _ \<FQDN\>_ は、データベース ・ サーバの完全修飾ドメイン名 (FQDN) と_\<インスタンス\>_(1 つが定義されている) 場合は、名前付きデータベース インスタンスは、します。 
    
4. プール アプリケーション ストアのデータベースを削除するのには次のように入力します。
    
   ```
   Uninstall-CsDataBase -DatabaseType Application -SqlServerFqdn <FQDN> [-SqlInstanceName <instance>]
   ```

    _ \<FQDN\>_ は、データベース ・ サーバの FQDN と_\<インスタンス\>_(1 つが定義されている) 場合は、名前付きデータベース インスタンスは、です。 
    
5. **アンインストール CsDataBase**コマンドレットを使用して、動作を確認されたらの情報を読み、続行、または N、し、Enter キーを押します (エラーがある場合) は、コマンドレットを停止したい場合に Y (または Enter) キーを押します。 
    

