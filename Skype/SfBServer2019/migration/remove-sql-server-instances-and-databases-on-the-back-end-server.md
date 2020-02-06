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
# <a name="remove-sql-server-instances-and-databases-on-the-back-end-server"></a><span data-ttu-id="7ee29-104">バックエンド サーバー上の SQL Server インスタンスとデータベースの削除</span><span class="sxs-lookup"><span data-stu-id="7ee29-104">Remove SQL Server instances and databases on the Back End Server</span></span>

<span data-ttu-id="7ee29-105">依存しているサーバーを削除した後、または別のデータベースを使用するようにサーバーを再構成した後、Microsoft SQL Server データベースとインスタンスを削除します。</span><span class="sxs-lookup"><span data-stu-id="7ee29-105">You remove the Microsoft SQL Server databases and instances after you remove the servers running that are dependent on them, or after you reconfigure the servers to use another database.</span></span> <span data-ttu-id="7ee29-106">このトピックでは、現在の SQL Server を廃止する場合、または現在のサーバーを再構成して、データベースが使用されていない、または利用できないようにする場合に、このトピックで説明する手順を実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="7ee29-106">You need to perform the procedure in this topic when you retire the current SQL Server or reconfigure the current server in such a way that it renders the databases obsolete or unavailable.</span></span>
  
<span data-ttu-id="7ee29-107">アーカイブサーバーまたは監視サーバーのデータベースまたはインスタンスを削除するには、まずサーバーの役割を削除する必要があります。</span><span class="sxs-lookup"><span data-stu-id="7ee29-107">To remove the databases or instances for the Archiving Server or Monitoring Server, you must first remove the server role.</span></span> <span data-ttu-id="7ee29-108">同様に、フロントエンドプールのインスタンスまたはデータベースを削除するには、まず依存サーバーの役割を削除または再構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="7ee29-108">Similarly, to remove the instances or databases for Front End pool, you must first remove or reconfigure the dependent server role.</span></span> <span data-ttu-id="7ee29-109">これらの手順では、サーバーの併置されたデータベースと個別のインスタンスが区別されません。</span><span class="sxs-lookup"><span data-stu-id="7ee29-109">These procedures make no distinction between collocated databases or separate instances for servers.</span></span> <span data-ttu-id="7ee29-110">プロシージャはデータベースの collocation の影響を受けません。</span><span class="sxs-lookup"><span data-stu-id="7ee29-110">The procedures are unaffected by the collocation of databases.</span></span>
  
## <a name="in-this-section"></a><span data-ttu-id="7ee29-111">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="7ee29-111">In this section</span></span>

- [<span data-ttu-id="7ee29-112">フロントエンド プール用の SQL Server データベースの削除</span><span class="sxs-lookup"><span data-stu-id="7ee29-112">Remove the SQL Server database for a Front End pool</span></span>](remove-the-sql-server-database-for-a-front-end-pool.md)
    
- [<span data-ttu-id="7ee29-113">監視サーバー用の SQL Server データベースの削除</span><span class="sxs-lookup"><span data-stu-id="7ee29-113">Remove the SQL Server database for a Monitoring server</span></span>](remove-the-sql-server-database-for-a-monitoring-server.md)
    
- [<span data-ttu-id="7ee29-114">アーカイブ サーバー用の SQL Server データベースの削除</span><span class="sxs-lookup"><span data-stu-id="7ee29-114">Remove the SQL Server database for an Archiving server</span></span>](remove-the-sql-server-database-for-an-archiving-server.md)
    

