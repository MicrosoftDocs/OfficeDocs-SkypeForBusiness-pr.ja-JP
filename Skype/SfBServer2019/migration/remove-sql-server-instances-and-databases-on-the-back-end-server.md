---
title: バックエンド サーバー上の SQL Server インスタンスとデータベースの削除
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
description: Microsoft SQL Server データベースとインスタンスは、それに依存しているサーバーを削除した後、または別のデータベースを使用するようにサーバーを再構成した後に削除します。 このトピックの手順を実行する必要があるのは、現在の SQL Server を廃止するか、または現在のサーバーを再構成して、データベースが使用できなくなった、または使用できないようにする場合です。
ms.openlocfilehash: 6e108e4dfef86b482b839bd440f54702ab42107d
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/16/2020
ms.locfileid: "44752159"
---
# <a name="remove-sql-server-instances-and-databases-on-the-back-end-server"></a>バックエンド サーバー上の SQL Server インスタンスとデータベースの削除

Microsoft SQL Server データベースとインスタンスは、それに依存しているサーバーを削除した後、または別のデータベースを使用するようにサーバーを再構成した後に削除します。 このトピックの手順を実行する必要があるのは、現在の SQL Server を廃止するか、または現在のサーバーを再構成して、データベースが使用できなくなった、または使用できないようにする場合です。
  
アーカイブサーバーまたは監視サーバーのデータベースまたはインスタンスを削除するには、最初にサーバーの役割を削除する必要があります。 同様に、フロントエンドプールのインスタンスまたはデータベースを削除するには、最初に依存サーバーの役割を削除または再構成する必要があります。 これらの手順では、サーバーの併置されたデータベースと個別のインスタンスは区別されません。 データベースの併置によって手順が影響を受けることはありません。
  
## <a name="in-this-section"></a>このセクションの内容

- [フロントエンド プール用の SQL Server データベースの削除](remove-the-sql-server-database-for-a-front-end-pool.md)
    
- [監視サーバー用の SQL Server データベースの削除](remove-the-sql-server-database-for-a-monitoring-server.md)
    
- [アーカイブ サーバー用の SQL Server データベースの削除](remove-the-sql-server-database-for-an-archiving-server.md)
    

