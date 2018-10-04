---
title: 監視サーバーの SQL Server データベースを削除します。
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 監視サーバーを削除した後は、サーバーのデータをホストしていた SQL Server データベースを削除できます。 トポロジ ビルダーでは、定義を削除するのには次の手順を使用し、データベース ・ サーバからデータベースとログ ファイルを削除します。
ms.openlocfilehash: 85999f1bbb3fc443edcab9d1f1354f26187c6a75
ms.sourcegitcommit: dd37c12a0312270955755ab2826adcfbae813790
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/04/2018
ms.locfileid: "25373358"
---
# <a name="remove-the-sql-server-database-for-a-monitoring-server"></a>監視サーバーの SQL Server データベースを削除します。

監視サーバーを削除した後は、サーバーのデータをホストしていた SQL Server データベースを削除できます。 トポロジ ビルダーでは、定義を削除するのには次の手順を使用し、データベース ・ サーバからデータベースとログ ファイルを削除します。
  
## <a name="to-remove-the-sql-server-database-using-topology-builder"></a>トポロジ ビルダーを使用して SQL Server データベースを削除するには

1. ビジネス 2019 フロント エンド サーバーの Skype、トポロジ ビルダーを開きます。
    
2. トポロジ ビルダーでは、**コンポーネントを共有**し、 **SQL Server ストア**に移動を選択し、SQL Server のインスタンスが削除されたに関連付けられている、またはサーバーの監視を再設定] を右クリックし、[**削除**] をクリックします。
    
3. 、トポロジを公開し、し、レプリケーションの状態を確認します。
    
## <a name="to-remove-the-database-files-from-the-sql-server"></a>SQL Server からデータベース ファイルを削除するのには

1. SQL Server ベースのサーバー上のデータベースを削除するには、データベース ファイルを削除する SQL Server サーバーの SQL Server システム管理者グループのメンバーをする必要があります。
    
2. Skype をビジネス サーバー管理シェルを開きます。
    
3. コマンドラインで、次のように入力します。
    
   ```
   Uninstall-CsDataBase -DatabaseType Monitoring -SqlServerFqdn <FQDN> [-SqlInstanceName <instance>]
   ```

    _ \<FQDN\>_ は、データベース ・ サーバの完全修飾ドメイン名 (FQDN) と_\<インスタンス\>_ 省略可能な名前付きデータベース インスタンスは、します。 
    
4. **アンインストール CsDataBase**コマンドレットを使用して、動作を確認されたらの情報を読み、続行、または N、し、Enter キーを押します (エラーがある場合) は、コマンドレットを停止したい場合に Y (または Enter) キーを押します。 
    

