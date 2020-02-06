---
title: バックエンド サーバー上の SQL Server インスタンスとデータベースの削除
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
description: 依存しているサーバーを削除した後、または別のデータベースを使用するようにサーバーを再構成した後、Microsoft SQL Server データベースとインスタンスを削除します。 このトピックでは、現在の SQL Server を廃止する場合、または現在のサーバーを再構成して、データベースが使用されていない、または利用できないようにする場合に、このトピックで説明する手順を実行する必要があります。
ms.openlocfilehash: 01552fcd494514802fffb35de7db7643f8cc26fd
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2020
ms.locfileid: "41812985"
---
# <a name="remove-sql-server-instances-and-databases-on-the-back-end-server"></a>バックエンド サーバー上の SQL Server インスタンスとデータベースの削除

依存しているサーバーを削除した後、または別のデータベースを使用するようにサーバーを再構成した後、Microsoft SQL Server データベースとインスタンスを削除します。 このトピックでは、現在の SQL Server を廃止する場合、または現在のサーバーを再構成して、データベースが使用されていない、または利用できないようにする場合に、このトピックで説明する手順を実行する必要があります。
  
アーカイブサーバーまたは監視サーバーのデータベースまたはインスタンスを削除するには、まずサーバーの役割を削除する必要があります。 同様に、フロントエンドプールのインスタンスまたはデータベースを削除するには、まず依存サーバーの役割を削除または再構成する必要があります。 これらの手順では、サーバーの併置されたデータベースと個別のインスタンスが区別されません。 プロシージャはデータベースの collocation の影響を受けません。
  
## <a name="in-this-section"></a>このセクションの内容

- [フロントエンド プール用の SQL Server データベースの削除](remove-the-sql-server-database-for-a-front-end-pool.md)
    
- [監視サーバー用の SQL Server データベースの削除](remove-the-sql-server-database-for-a-monitoring-server.md)
    
- [アーカイブ サーバー用の SQL Server データベースの削除](remove-the-sql-server-database-for-an-archiving-server.md)
    

