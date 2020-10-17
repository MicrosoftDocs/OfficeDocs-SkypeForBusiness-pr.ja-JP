---
title: バックエンド サーバー上の SQL Server インスタンスとデータベースの削除
description: バックエンドサーバー上の SQL Server インスタンスとデータベースを削除します。
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Remove SQL Server instances and databases on the Back End Server
ms:assetid: 32457df9-7dd9-4fca-9362-ea4de26b0296
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688016(v=OCS.15)
ms:contentKeyID: 49733606
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c87426a3496e6def2ad65775f5dadb1a0141ae3f
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48551283"
---
# <a name="remove-sql-server-instances-and-databases-on-the-back-end-server"></a><span data-ttu-id="39089-103">バックエンド サーバー上の SQL Server インスタンスとデータベースの削除</span><span class="sxs-lookup"><span data-stu-id="39089-103">Remove SQL Server instances and databases on the Back End Server</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="39089-104">_**トピックの最終更新日:** 2012-10-19_</span><span class="sxs-lookup"><span data-stu-id="39089-104">_**Topic Last Modified:** 2012-10-19_</span></span>

<span data-ttu-id="39089-105">Microsoft SQL Server データベースとインスタンスは、そのサーバーに依存している Lync Server 2010 を実行しているサーバーを削除した後、または別のデータベースを使用するために Lync Server 2010 を実行しているサーバーを再構成した後に削除します。</span><span class="sxs-lookup"><span data-stu-id="39089-105">You remove the Microsoft SQL Server databases and instances after you remove the servers running Lync Server 2010 that are dependent on them, or after you reconfigure the servers running Lync Server 2010 to use another database.</span></span> <span data-ttu-id="39089-106">このトピックの手順を実行する必要があるのは、現在の SQL Server を廃止する場合、または、データベースが使用できなくなった、または利用できないようにするために、Lync Server 2010 を実行している現在のサーバーを再構成する場合です。</span><span class="sxs-lookup"><span data-stu-id="39089-106">You need to perform the procedure in this topic when you retire the current SQL Server or reconfigure the current server running Lync Server 2010 in such a way that it renders the databases obsolete or unavailable.</span></span>

<span data-ttu-id="39089-107">アーカイブサーバーまたは監視サーバーのデータベースまたはインスタンスを削除するには、最初にサーバーの役割を削除する必要があります。</span><span class="sxs-lookup"><span data-stu-id="39089-107">To remove the databases or instances for the Archiving Server or Monitoring Server, you must first remove the server role.</span></span> <span data-ttu-id="39089-108">同様に、フロントエンドプールのインスタンスまたはデータベースを削除するには、最初に依存サーバーの役割を削除または再構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="39089-108">Similarly, to remove the instances or databases for Front End pool, you must first remove or reconfigure the dependent server role.</span></span> <span data-ttu-id="39089-109">これらの手順では、サーバーの併置されたデータベースと個別のインスタンスは区別されません。</span><span class="sxs-lookup"><span data-stu-id="39089-109">These procedures make no distinction between collocated databases or separate instances for servers.</span></span> <span data-ttu-id="39089-110">データベースの併置によって手順が影響を受けることはありません。</span><span class="sxs-lookup"><span data-stu-id="39089-110">The procedures are unaffected by the collocation of databases.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="39089-111">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="39089-111">In This Section</span></span>

  - [<span data-ttu-id="39089-112">フロントエンド プール用の SQL Server データベースの削除</span><span class="sxs-lookup"><span data-stu-id="39089-112">Remove the SQL Server database for a Front End pool</span></span>](remove-the-sql-server-database-for-a-front-end-pool.md)

  - [<span data-ttu-id="39089-113">監視サーバー用の SQL Server データベースの削除</span><span class="sxs-lookup"><span data-stu-id="39089-113">Remove the SQL Server database for a Monitoring server</span></span>](remove-the-sql-server-database-for-a-monitoring-server.md)

  - [<span data-ttu-id="39089-114">アーカイブ サーバー用の SQL Server データベースの削除</span><span class="sxs-lookup"><span data-stu-id="39089-114">Remove the SQL Server database for an Archiving server</span></span>](remove-the-sql-server-database-for-an-archiving-server.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

