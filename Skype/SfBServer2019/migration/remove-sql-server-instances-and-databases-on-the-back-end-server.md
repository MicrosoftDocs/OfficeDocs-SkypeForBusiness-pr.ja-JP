---
title: バック エンド サーバー上の SQL Server インスタンスとデータベースの削除
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
description: サーバーに依存Microsoft SQL Serverサーバーを削除した後、または別のデータベースを使用するサーバーを再構成した後に、データベースとインスタンスを削除します。 このトピックの手順は、現在の SQL Server を廃止する場合や、現在のサーバーを再構成してデータベースを使用できなくなったり使用できなくなったりする場合に実行する必要があります。
ms.openlocfilehash: f9e942f1f5516c0bf3437dd3fc9e2dc25b4cc4236e3cffabbf07ff08dde1e404
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2021
ms.locfileid: "54306210"
---
# <a name="remove-sql-server-instances-and-databases-on-the-back-end-server"></a>バック エンド サーバー上の SQL Server インスタンスとデータベースの削除

サーバーに依存Microsoft SQL Serverサーバーを削除した後、または別のデータベースを使用するサーバーを再構成した後に、データベースとインスタンスを削除します。 このトピックの手順は、現在の SQL Server を廃止する場合や、現在のサーバーを再構成してデータベースを使用できなくなったり使用できなくなったりする場合に実行する必要があります。
  
アーカイブ サーバーまたは監視サーバーのデータベースまたはインスタンスを削除するには、まずサーバーの役割を削除する必要があります。 同様に、フロントエンド プールのインスタンスまたはデータベースを削除するには、最初に依存するサーバーの役割を削除または再構成する必要があります。 これらの手順では、サーバーの併置されたデータベースと個別のインスタンスは区別されません。 データベースの併置によって手順が影響を受けることはありません。
  
## <a name="in-this-section"></a>このセクションの内容

- [フロントエンド プール用の SQL Server データベースの削除](remove-the-sql-server-database-for-a-front-end-pool.md)
    
- [監視サーバー用の SQL Server データベースの削除](remove-the-sql-server-database-for-a-monitoring-server.md)
    
- [アーカイブ サーバー用の SQL Server データベースの削除](remove-the-sql-server-database-for-an-archiving-server.md)
    

