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
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/27/2019
ms.locfileid: "30898741"
---
# <a name="remove-sql-server-instances-and-databases-on-the-back-end-server"></a><span data-ttu-id="49bcd-104">バックエンド サーバー上の SQL Server インスタンスとデータベースの削除</span><span class="sxs-lookup"><span data-stu-id="49bcd-104">Remove SQL Server instances and databases on the Back End Server</span></span>

<span data-ttu-id="49bcd-105">Microsoft SQL Server データベースを削除して、インスタンスを実行しているサーバーを削除した後は、上、または別のデータベースを使用するサーバーを再構成した後に依存します。</span><span class="sxs-lookup"><span data-stu-id="49bcd-105">You remove the Microsoft SQL Server databases and instances after you remove the servers running that are dependent on them, or after you reconfigure the servers to use another database.</span></span> <span data-ttu-id="49bcd-106">現在の SQL Server を削除するか、古い、または使用できないデータベース表示されるように現在のサーバーを再構成すると、このトピックの手順を実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="49bcd-106">You need to perform the procedure in this topic when you retire the current SQL Server or reconfigure the current server in such a way that it renders the databases obsolete or unavailable.</span></span>
  
<span data-ttu-id="49bcd-107">アーカイブ サーバーまたは監視サーバーのデータベースまたはインスタンスを削除するには、まず、サーバーの役割を削除する必要があります。</span><span class="sxs-lookup"><span data-stu-id="49bcd-107">To remove the databases or instances for the Archiving Server or Monitoring Server, you must first remove the server role.</span></span> <span data-ttu-id="49bcd-108">同様に、インスタンスまたはデータベースをフロント エンド プールを削除するにするには削除するか依存するサーバーの役割を再設定します。</span><span class="sxs-lookup"><span data-stu-id="49bcd-108">Similarly, to remove the instances or databases for Front End pool, you must first remove or reconfigure the dependent server role.</span></span> <span data-ttu-id="49bcd-109">これらの手順は、サーバーに配置されているデータベースまたは別のインスタンス間での違いを作成しません。</span><span class="sxs-lookup"><span data-stu-id="49bcd-109">These procedures make no distinction between collocated databases or separate instances for servers.</span></span> <span data-ttu-id="49bcd-110">手順は、データベースのコロケーションの影響を受けません。</span><span class="sxs-lookup"><span data-stu-id="49bcd-110">The procedures are unaffected by the collocation of databases.</span></span>
  
## <a name="in-this-section"></a><span data-ttu-id="49bcd-111">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="49bcd-111">In this section</span></span>

- [<span data-ttu-id="49bcd-112">フロントエンド プール用の SQL Server データベースの削除</span><span class="sxs-lookup"><span data-stu-id="49bcd-112">Remove the SQL Server database for a Front End pool</span></span>](remove-the-sql-server-database-for-a-front-end-pool.md)
    
- [<span data-ttu-id="49bcd-113">監視サーバー用の SQL Server データベースの削除</span><span class="sxs-lookup"><span data-stu-id="49bcd-113">Remove the SQL Server database for a Monitoring server</span></span>](remove-the-sql-server-database-for-a-monitoring-server.md)
    
- [<span data-ttu-id="49bcd-114">アーカイブ サーバー用の SQL Server データベースの削除</span><span class="sxs-lookup"><span data-stu-id="49bcd-114">Remove the SQL Server database for an Archiving server</span></span>](remove-the-sql-server-database-for-an-archiving-server.md)
    

