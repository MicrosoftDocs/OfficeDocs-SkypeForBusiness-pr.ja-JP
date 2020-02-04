---
title: バックエンド サーバー上の SQL Server インスタンスとデータベースの削除
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Remove SQL Server instances and databases on the Back End Server
ms:assetid: 32457df9-7dd9-4fca-9362-ea4de26b0296
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688016(v=OCS.15)
ms:contentKeyID: 49733606
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 11439dd9fd339c3620b3e6288526459f45a2a542
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41727107"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="remove-sql-server-instances-and-databases-on-the-back-end-server"></a><span data-ttu-id="fa9af-102">バックエンド サーバー上の SQL Server インスタンスとデータベースの削除</span><span class="sxs-lookup"><span data-stu-id="fa9af-102">Remove SQL Server instances and databases on the Back End Server</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="fa9af-103">_**最終更新日:** 2012-10-19_</span><span class="sxs-lookup"><span data-stu-id="fa9af-103">_**Topic Last Modified:** 2012-10-19_</span></span>

<span data-ttu-id="fa9af-104">自分に依存している Lync Server 2010 を実行しているサーバーを削除した後、または Lync Server 2010 を実行しているサーバーを別のデータベースを使用するように再構成した後に、Microsoft SQL Server データベースとインスタンスを削除します。</span><span class="sxs-lookup"><span data-stu-id="fa9af-104">You remove the Microsoft SQL Server databases and instances after you remove the servers running Lync Server 2010 that are dependent on them, or after you reconfigure the servers running Lync Server 2010 to use another database.</span></span> <span data-ttu-id="fa9af-105">このトピックでは、現在の SQL Server を廃止する場合、またはデータベースが使用されていないように表示されるように、Lync Server 2010 を実行している現在のサーバーを再構成する場合に、この手順を実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="fa9af-105">You need to perform the procedure in this topic when you retire the current SQL Server or reconfigure the current server running Lync Server 2010 in such a way that it renders the databases obsolete or unavailable.</span></span>

<span data-ttu-id="fa9af-106">アーカイブサーバーまたは監視サーバーのデータベースまたはインスタンスを削除するには、まずサーバーの役割を削除する必要があります。</span><span class="sxs-lookup"><span data-stu-id="fa9af-106">To remove the databases or instances for the Archiving Server or Monitoring Server, you must first remove the server role.</span></span> <span data-ttu-id="fa9af-107">同様に、フロントエンドプールのインスタンスまたはデータベースを削除するには、まず依存サーバーの役割を削除または再構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="fa9af-107">Similarly, to remove the instances or databases for Front End pool, you must first remove or reconfigure the dependent server role.</span></span> <span data-ttu-id="fa9af-108">これらの手順では、サーバーの併置されたデータベースと個別のインスタンスが区別されません。</span><span class="sxs-lookup"><span data-stu-id="fa9af-108">These procedures make no distinction between collocated databases or separate instances for servers.</span></span> <span data-ttu-id="fa9af-109">プロシージャはデータベースの collocation の影響を受けません。</span><span class="sxs-lookup"><span data-stu-id="fa9af-109">The procedures are unaffected by the collocation of databases.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="fa9af-110">このセクション中</span><span class="sxs-lookup"><span data-stu-id="fa9af-110">In This Section</span></span>

  - [<span data-ttu-id="fa9af-111">フロントエンド プール用の SQL Server データベースの削除</span><span class="sxs-lookup"><span data-stu-id="fa9af-111">Remove the SQL Server database for a Front End pool</span></span>](remove-the-sql-server-database-for-a-front-end-pool.md)

  - [<span data-ttu-id="fa9af-112">監視サーバー用の SQL Server データベースの削除</span><span class="sxs-lookup"><span data-stu-id="fa9af-112">Remove the SQL Server database for a Monitoring server</span></span>](remove-the-sql-server-database-for-a-monitoring-server.md)

  - [<span data-ttu-id="fa9af-113">アーカイブ サーバー用の SQL Server データベースの削除</span><span class="sxs-lookup"><span data-stu-id="fa9af-113">Remove the SQL Server database for an Archiving server</span></span>](remove-the-sql-server-database-for-an-archiving-server.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

