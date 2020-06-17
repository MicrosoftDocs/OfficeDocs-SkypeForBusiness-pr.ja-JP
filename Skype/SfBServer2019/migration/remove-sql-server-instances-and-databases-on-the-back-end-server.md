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
# <a name="remove-sql-server-instances-and-databases-on-the-back-end-server"></a><span data-ttu-id="b2ceb-104">バックエンド サーバー上の SQL Server インスタンスとデータベースの削除</span><span class="sxs-lookup"><span data-stu-id="b2ceb-104">Remove SQL Server instances and databases on the Back End Server</span></span>

<span data-ttu-id="b2ceb-105">Microsoft SQL Server データベースとインスタンスは、それに依存しているサーバーを削除した後、または別のデータベースを使用するようにサーバーを再構成した後に削除します。</span><span class="sxs-lookup"><span data-stu-id="b2ceb-105">You remove the Microsoft SQL Server databases and instances after you remove the servers running that are dependent on them, or after you reconfigure the servers to use another database.</span></span> <span data-ttu-id="b2ceb-106">このトピックの手順を実行する必要があるのは、現在の SQL Server を廃止するか、または現在のサーバーを再構成して、データベースが使用できなくなった、または使用できないようにする場合です。</span><span class="sxs-lookup"><span data-stu-id="b2ceb-106">You need to perform the procedure in this topic when you retire the current SQL Server or reconfigure the current server in such a way that it renders the databases obsolete or unavailable.</span></span>
  
<span data-ttu-id="b2ceb-107">アーカイブサーバーまたは監視サーバーのデータベースまたはインスタンスを削除するには、最初にサーバーの役割を削除する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b2ceb-107">To remove the databases or instances for the Archiving Server or Monitoring Server, you must first remove the server role.</span></span> <span data-ttu-id="b2ceb-108">同様に、フロントエンドプールのインスタンスまたはデータベースを削除するには、最初に依存サーバーの役割を削除または再構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b2ceb-108">Similarly, to remove the instances or databases for Front End pool, you must first remove or reconfigure the dependent server role.</span></span> <span data-ttu-id="b2ceb-109">これらの手順では、サーバーの併置されたデータベースと個別のインスタンスは区別されません。</span><span class="sxs-lookup"><span data-stu-id="b2ceb-109">These procedures make no distinction between collocated databases or separate instances for servers.</span></span> <span data-ttu-id="b2ceb-110">データベースの併置によって手順が影響を受けることはありません。</span><span class="sxs-lookup"><span data-stu-id="b2ceb-110">The procedures are unaffected by the collocation of databases.</span></span>
  
## <a name="in-this-section"></a><span data-ttu-id="b2ceb-111">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="b2ceb-111">In this section</span></span>

- [<span data-ttu-id="b2ceb-112">フロントエンド プール用の SQL Server データベースの削除</span><span class="sxs-lookup"><span data-stu-id="b2ceb-112">Remove the SQL Server database for a Front End pool</span></span>](remove-the-sql-server-database-for-a-front-end-pool.md)
    
- [<span data-ttu-id="b2ceb-113">監視サーバー用の SQL Server データベースの削除</span><span class="sxs-lookup"><span data-stu-id="b2ceb-113">Remove the SQL Server database for a Monitoring server</span></span>](remove-the-sql-server-database-for-a-monitoring-server.md)
    
- [<span data-ttu-id="b2ceb-114">アーカイブ サーバー用の SQL Server データベースの削除</span><span class="sxs-lookup"><span data-stu-id="b2ceb-114">Remove the SQL Server database for an Archiving server</span></span>](remove-the-sql-server-database-for-an-archiving-server.md)
    

