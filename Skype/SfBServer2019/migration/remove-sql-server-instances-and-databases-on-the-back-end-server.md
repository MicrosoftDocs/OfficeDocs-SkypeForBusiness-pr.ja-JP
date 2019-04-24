---
title: バックエンド サーバー上の SQL Server インスタンスとデータベースの削除
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Microsoft SQL Server データベースを削除して、インスタンスを実行しているサーバーを削除した後は、上、または別のデータベースを使用するサーバーを再構成した後に依存します。 現在の SQL Server を削除するか、古い、または使用できないデータベース表示されるように現在のサーバーを再構成すると、このトピックの手順を実行する必要があります。
ms.openlocfilehash: 531d4c06daa7dacd2a616244c13207b3e79dca4c
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "32231505"
---
# <a name="remove-sql-server-instances-and-databases-on-the-back-end-server"></a>バックエンド サーバー上の SQL Server インスタンスとデータベースの削除

Microsoft SQL Server データベースを削除して、インスタンスを実行しているサーバーを削除した後は、上、または別のデータベースを使用するサーバーを再構成した後に依存します。 現在の SQL Server を削除するか、古い、または使用できないデータベース表示されるように現在のサーバーを再構成すると、このトピックの手順を実行する必要があります。
  
アーカイブ サーバーまたは監視サーバーのデータベースまたはインスタンスを削除するには、まず、サーバーの役割を削除する必要があります。 同様に、インスタンスまたはデータベースをフロント エンド プールを削除するにするには削除するか依存するサーバーの役割を再設定します。 これらの手順は、サーバーに配置されているデータベースまたは別のインスタンス間での違いを作成しません。 手順は、データベースのコロケーションの影響を受けません。
  
## <a name="in-this-section"></a>このセクションの内容

- [フロントエンド プール用の SQL Server データベースの削除](remove-the-sql-server-database-for-a-front-end-pool.md)
    
- [監視サーバー用の SQL Server データベースの削除](remove-the-sql-server-database-for-a-monitoring-server.md)
    
- [アーカイブ サーバー用の SQL Server データベースの削除](remove-the-sql-server-database-for-an-archiving-server.md)
    

