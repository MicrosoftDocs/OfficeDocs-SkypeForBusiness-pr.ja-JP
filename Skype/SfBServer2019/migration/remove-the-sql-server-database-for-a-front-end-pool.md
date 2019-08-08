---
title: フロントエンド プール用の SQL Server データベースの削除
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: フロントエンドプールを削除するか、プールを再構成して別のデータベースを使用する場合は、プールデータをホストしている SQL Server データベースを削除することができます。 次の手順を使用して、Topology Builder から定義を削除し、データベースサーバーからデータベースとログファイルを削除します。
ms.openlocfilehash: d22a90401bdfa4a2897a18805e8b9c588892c5fb
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/07/2019
ms.locfileid: "36241564"
---
# <a name="remove-the-sql-server-database-for-a-front-end-pool"></a>フロントエンド プール用の SQL Server データベースの削除

フロントエンドプールを削除するか、プールを再構成して別のデータベースを使用する場合は、プールデータをホストしている SQL Server データベースを削除することができます。 次の手順を使用して、Topology Builder から定義を削除し、データベースサーバーからデータベースとログファイルを削除します。
  
## <a name="to-remove-the-sql-server-database-using-topology-builder"></a>トポロジビルダーを使用して SQL Server データベースを削除するには

1. Skype for Business Server 2019 フロントエンドサーバーから、[トポロジビルダー] を開き、既存のトポロジをダウンロードします。 
    
2. [トポロジビルダー] で、[**共有コンポーネント**] に移動し、[ **sql Server ストア**] で、削除または再構成されたフロントエンドプールに関連付けられている sql server インスタンスを右クリックし、[**削除**] をクリックします。
    
3. トポロジを公開し、レプリケーションの状態を確認します。 
    
## <a name="to-remove-user-and-application-databases-from-the-sql-server"></a>SQL server からユーザーデータベースとアプリケーションデータベースを削除するには

1. SQL server 上のデータベースを削除するには、データベースファイルを削除する SQL server の [SQL Server のオプション] グループのメンバーである必要があります。 
    
2. Skype for Business Server 管理シェルを開きます。
    
3. プールユーザーストアのデータベースを削除するには、次のように入力します。
    
   ```
   Uninstall-CsDataBase -DatabaseType User -SqlServerFqdn <FQDN> [-SqlInstanceName <instance>]
   ```

    ここ_ \<で\> 、fqdn_はデータベースサーバーの完全修飾ドメイン名 (FQDN) であり_ \<、\>インスタンス_は名前付きデータベースインスタンス (定義されている場合) です。 
    
4. プールアプリケーションストアのデータベースを削除するには、次のように入力します。
    
   ```
   Uninstall-CsDataBase -DatabaseType Application -SqlServerFqdn <FQDN> [-SqlInstanceName <instance>]
   ```

    ここ_ \<で\> 、fqdn_はデータベースサーバーの fqdn で、 _ \<インスタンス\> _は名前付きデータベースインスタンス (定義されている場合) です。 
    
5. **CsDataBase**コマンドレットで操作の確認を求めるメッセージが表示されたら、情報を読み、Y (または enter) キーを押して続行するか、または N キーを押してコマンドレットを停止するか (エラーがある場合)、enter キーを押します。 
    

