---
title: アーカイブ サーバーの SQL Server データベースを削除します。
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: アーカイブ サーバーを削除した後は、プールのデータをホストしていた SQL Server データベースを削除できます。 トポロジ ビルダーでは、定義を削除するのには次の手順を使用し、データベース ・ サーバからデータベースとログ ファイルを削除します。
ms.openlocfilehash: c82f718cf86de653f6c1340d38e21e96cbaa150d
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/24/2018
ms.locfileid: "25027964"
---
# <a name="remove-the-sql-server-database-for-an-archiving-server"></a>アーカイブ サーバーの SQL Server データベースを削除します。

アーカイブ サーバーを削除した後は、プールのデータをホストしていた SQL Server データベースを削除できます。 トポロジ ビルダーでは、定義を削除するのには次の手順を使用し、データベース ・ サーバからデータベースとログ ファイルを削除します。
  
## <a name="to-remove-the-sql-server-database-using-topology-builder"></a>トポロジ ビルダーを使用して SQL Server データベースを削除するには

1. ビジネス 2019 フロント エンド サーバーの Skype、トポロジ ビルダーを開きます。
    
2. トポロジ ビルダーでは、**コンポーネントを共有**し、 **SQL Server ストア**に移動を選択し、SQL Server のインスタンスが削除されたに関連付けられている、またはアーカイブ サーバーを再構成] を右クリックし、[**削除**] をクリックします。
    
3. 、トポロジを公開し、し、レプリケーションの状態を確認します。 
    
## <a name="to-remove-the-database-files-from-the-sql-server"></a>SQL Server からデータベース ファイルを削除するのには

1. SQL Server 上のデータベースを削除するには、データベース ファイルを削除する SQL Server の SQL Server システム管理者グループのメンバーをする必要があります。 
    
2. Skype をビジネス サーバー管理シェルを開きます。
    
3. コマンドラインで、次のように入力します。
    
  ```
  Uninstall-CsDataBase -DatabaseType Archiving -SqlServerFqdn <FQDN> [-SqlInstanceName <instance>]
  ```

    _ \<FQDN\>_ は、データベース ・ サーバの完全修飾ドメイン名 (FQDN) と_\<インスタンス\>_(1 つが定義されている) 場合は、名前付きデータベース インスタンスは、します。 
    
4. **アンインストール CsDataBase**コマンドレットを使用して、動作を確認されたらの情報を読み、続行、または N、し、Enter キーを押します (エラーがある場合) は、コマンドレットを停止したい場合に Y (または Enter) キーを押します。 
    

