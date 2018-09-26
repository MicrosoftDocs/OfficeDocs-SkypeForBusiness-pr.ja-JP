---
title: SQL Server のインスタンスおよびバック エンド サーバー上のデータベースを削除します。
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Microsoft SQL Server データベースを削除して、インスタンスを実行しているサーバーを削除した後は、上、または別のデータベースを使用するサーバーを再構成した後に依存します。 現在の SQL Server を削除するか、古い、または使用できないデータベース表示されるように現在のサーバーを再構成すると、このトピックの手順を実行する必要があります。
ms.openlocfilehash: 648c808ee293c4fa33352d0f68ba337e4a489d27
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/24/2018
ms.locfileid: "25027880"
---
# <a name="remove-sql-server-instances-and-databases-on-the-back-end-server"></a><span data-ttu-id="b7f68-104">SQL Server のインスタンスおよびバック エンド サーバー上のデータベースを削除します。</span><span class="sxs-lookup"><span data-stu-id="b7f68-104">Remove SQL Server instances and databases on the Back End Server</span></span>

<span data-ttu-id="b7f68-105">Microsoft SQL Server データベースを削除して、インスタンスを実行しているサーバーを削除した後は、上、または別のデータベースを使用するサーバーを再構成した後に依存します。</span><span class="sxs-lookup"><span data-stu-id="b7f68-105">You remove the Microsoft SQL Server databases and instances after you remove the servers running that are dependent on them, or after you reconfigure the servers to use another database.</span></span> <span data-ttu-id="b7f68-106">現在の SQL Server を削除するか、古い、または使用できないデータベース表示されるように現在のサーバーを再構成すると、このトピックの手順を実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b7f68-106">You need to perform the procedure in this topic when you retire the current SQL Server or reconfigure the current server in such a way that it renders the databases obsolete or unavailable.</span></span>
  
<span data-ttu-id="b7f68-107">アーカイブ サーバーまたは監視サーバーのデータベースまたはインスタンスを削除するには、まず、サーバーの役割を削除する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b7f68-107">To remove the databases or instances for the Archiving Server or Monitoring Server, you must first remove the server role.</span></span> <span data-ttu-id="b7f68-108">同様に、インスタンスまたはデータベースをフロント エンド プールを削除するにするには削除するか依存するサーバーの役割を再設定します。</span><span class="sxs-lookup"><span data-stu-id="b7f68-108">Similarly, to remove the instances or databases for Front End pool, you must first remove or reconfigure the dependent server role.</span></span> <span data-ttu-id="b7f68-109">これらの手順は、サーバーに配置されているデータベースまたは別のインスタンス間での違いを作成しません。</span><span class="sxs-lookup"><span data-stu-id="b7f68-109">These procedures make no distinction between collocated databases or separate instances for servers.</span></span> <span data-ttu-id="b7f68-110">手順は、データベースのコロケーションの影響を受けません。</span><span class="sxs-lookup"><span data-stu-id="b7f68-110">The procedures are unaffected by the collocation of databases.</span></span>
  
## <a name="in-this-section"></a><span data-ttu-id="b7f68-111">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="b7f68-111">In this section</span></span>

- [<span data-ttu-id="b7f68-112">フロント エンド プールの SQL Server データベースを削除します。</span><span class="sxs-lookup"><span data-stu-id="b7f68-112">Remove the SQL Server database for a Front End pool</span></span>](remove-the-sql-server-database-for-a-front-end-pool.md)
    
- [<span data-ttu-id="b7f68-113">監視サーバーの SQL Server データベースを削除します。</span><span class="sxs-lookup"><span data-stu-id="b7f68-113">Remove the SQL Server database for a Monitoring server</span></span>](remove-the-sql-server-database-for-a-monitoring-server.md)
    
- [<span data-ttu-id="b7f68-114">アーカイブ サーバーの SQL Server データベースを削除します。</span><span class="sxs-lookup"><span data-stu-id="b7f68-114">Remove the SQL Server database for an Archiving server</span></span>](remove-the-sql-server-database-for-an-archiving-server.md)
    

