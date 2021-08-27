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
ms.localizationpriority: medium
description: サーバーに依存Microsoft SQL Serverサーバーを削除した後、または別のデータベースを使用するサーバーを再構成した後に、データベースとインスタンスを削除します。 このトピックの手順は、現在の SQL Server を廃止する場合や、現在のサーバーを再構成してデータベースを使用できなくなったり使用できなくなったりする場合に実行する必要があります。
ms.openlocfilehash: dafd1589bc4d1624a71998813fe785841cbfb713
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/26/2021
ms.locfileid: "58582031"
---
# <a name="remove-sql-server-instances-and-databases-on-the-back-end-server"></a>バック エンド サーバー上の SQL Server インスタンスとデータベースの削除

サーバーに依存Microsoft SQL Serverサーバーを削除した後、または別のデータベースを使用するサーバーを再構成した後に、データベースとインスタンスを削除します。 このトピックの手順は、現在の SQL Server を廃止する場合や、現在のサーバーを再構成してデータベースを使用できなくなったり使用できなくなったりする場合に実行する必要があります。
  
アーカイブ サーバーまたは監視サーバーのデータベースまたはインスタンスを削除するには、まずサーバーの役割を削除する必要があります。 同様に、フロントエンド プールのインスタンスまたはデータベースを削除するには、最初に依存するサーバーの役割を削除または再構成する必要があります。 これらの手順では、サーバーの併置されたデータベースと個別のインスタンスは区別されません。 データベースの併置によって手順が影響を受けることはありません。
  
## <a name="in-this-section"></a>このセクションの内容

- [フロントエンド プール用の SQL Server データベースの削除](remove-the-sql-server-database-for-a-front-end-pool.md)
    
- [監視サーバー用の SQL Server データベースの削除](remove-the-sql-server-database-for-a-monitoring-server.md)
    
- [アーカイブ サーバー用の SQL Server データベースの削除](remove-the-sql-server-database-for-an-archiving-server.md)
    

