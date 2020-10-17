---
title: 'Lync Server 2013: バックアップと復元のプロセスの概要'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Backup and restoration process overview
ms:assetid: e0f23b21-070f-4df5-b795-cea2f5338d85
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh202192(v=OCS.15)
ms:contentKeyID: 51541524
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 94cebbc9a11e1857bed419c97f52f065326b1772
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/16/2020
ms.locfileid: "48504874"
---
# <a name="backup-and-restoration-process-overview-for-lync-server-2013"></a><span data-ttu-id="57a32-102">Lync Server 2013 のバックアップと復元のプロセスの概要</span><span class="sxs-lookup"><span data-stu-id="57a32-102">Backup and restoration process overview for Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="57a32-103">_**トピックの最終更新日:** 2013-03-26_</span><span class="sxs-lookup"><span data-stu-id="57a32-103">_**Topic Last Modified:** 2013-03-26_</span></span>

<span data-ttu-id="57a32-104">このセクションでは、Lync Server 2013 のバックアップと復元のプロセスがどのように機能するかの概要について説明します。</span><span class="sxs-lookup"><span data-stu-id="57a32-104">This section provides an overview of how the backup and restoration process works for Lync Server 2013.</span></span> <span data-ttu-id="57a32-105">すべての Standard Edition サーバーおよび Enterprise Edition サーバーでは、その場所に関係なく同じプロセスを使用します。</span><span class="sxs-lookup"><span data-stu-id="57a32-105">You use the same process for all Standard Edition servers and Enterprise Edition servers, regardless of their location.</span></span>

<span data-ttu-id="57a32-106">一般に、バックアッププロセスは次のように動作します。</span><span class="sxs-lookup"><span data-stu-id="57a32-106">In general, the backup process works as follows:</span></span>

  - <span data-ttu-id="57a32-107">バックアップ先は、どのプールにも属さないスタンドアロンコンピューター上の共有フォルダーとして作成します。</span><span class="sxs-lookup"><span data-stu-id="57a32-107">You create a backup location as a shared folder on a stand-alone computer that is not part of any pool.</span></span> <span data-ttu-id="57a32-108">バックアップの場所は **$Backup**で参照されます。</span><span class="sxs-lookup"><span data-stu-id="57a32-108">The location of the backup is referenced in **$Backup**.</span></span>

  - <span data-ttu-id="57a32-109">通常、スケジュールに従って、lync server データベースおよび [バックアップと復元の2013要件](lync-server-2013-backup-and-restoration-requirements-data.md) で説明されているすべてのファイルストアをバックアップします。この手順については、「lync server [2013](lync-server-2013-backing-up-lync-server.md) をバックアップする」で説明している手順に従います。中央管理ストアには、すべてのサーバー設定と構成が含まれています。</span><span class="sxs-lookup"><span data-stu-id="57a32-109">On a regular, scheduled basis, you back up all the Lync Server databases and all the file stores that are described in [Backup and restoration requirements in Lync Server 2013: data](lync-server-2013-backup-and-restoration-requirements-data.md) by following the procedures described in [Backing up Lync Server 2013](lync-server-2013-backing-up-lync-server.md) The Central Management store includes all the server settings and configurations.</span></span>

  - <span data-ttu-id="57a32-110">その後のバックアップを実行するたびに、新しい共有フォルダーを作成し、 **$Backup** 参照するパスを変更します。</span><span class="sxs-lookup"><span data-stu-id="57a32-110">Each time you run a subsequent backup, you create a new shared folder and change the path that **$Backup** references.</span></span>

<span data-ttu-id="57a32-111">一般的に、復元プロセスは次のように動作します。</span><span class="sxs-lookup"><span data-stu-id="57a32-111">In general, the restoration process works as follows:</span></span>

  - <span data-ttu-id="57a32-112">障害または停止が発生した場合は、 **$Backup** によって参照されている場所のデータを新しいコンピューターまたはクリーンなコンピューターに復元します。</span><span class="sxs-lookup"><span data-stu-id="57a32-112">When a failure or outage occurs, you restore the data in the location referenced by **$Backup** to new or clean computers.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="57a32-113">この復元プロセスでは、データは既存のサーバーの状態に復元されません。</span><span class="sxs-lookup"><span data-stu-id="57a32-113">This restoration process does not restore data onto an existing server state.</span></span> <span data-ttu-id="57a32-114">つまり、このプロセスでは、サーバーがクリーンまたは新規である必要があります。</span><span class="sxs-lookup"><span data-stu-id="57a32-114">That is, this process requires that the server is clean or new.</span></span>

    
    </div>

  - <span data-ttu-id="57a32-115">障害点までユーザーおよび会議情報を回復できるようにするには、「 [Lync Server 2013 での高可用性と障害復旧の計画](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md)」で説明されているように、フロントエンドプールをペアとする障害復旧トポロジを実装できます。</span><span class="sxs-lookup"><span data-stu-id="57a32-115">To enable your user and conference information to be recoverable to the point of failure, you can implement a disaster recovery topology with paired Front End pools, as described in [Planning for high availability and disaster recovery in Lync Server 2013](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md).</span></span>

  - <span data-ttu-id="57a32-116">すべてのドメインネームシステム (DNS) 構成、動的ホスト構成プロトコル (DHCP) の構成、ドメイン名、コンピューターの完全修飾ドメイン名 (Fqdn)、ファイルストアのパスなどは、バックアップ時の復元時と同じである必要があります。</span><span class="sxs-lookup"><span data-stu-id="57a32-116">All Domain Name System (DNS) configuration, Dynamic Host Configuration Protocol (DHCP) configuration, domain names, computer fully qualified domain names (FQDNs), file store paths, and so on must be the same at the time of restoration that they were at the time of back up.</span></span>

<span data-ttu-id="57a32-117">Lync Server を実行しているサーバーに障害が発生した場合、復旧には次の手順が含まれます。</span><span class="sxs-lookup"><span data-stu-id="57a32-117">If a server running Lync Server fails, recovery includes the following steps:</span></span>

  - <span data-ttu-id="57a32-118">エラーが発生したコンピューターと同じ FQDN を使用して、新しいまたはクリーンなコンピューターにオペレーティングシステムをインストールします。</span><span class="sxs-lookup"><span data-stu-id="57a32-118">Install the operating system on a new or clean computer with the same FQDN as the failed computer.</span></span>

  - <span data-ttu-id="57a32-119">証明書を再インストールします。</span><span class="sxs-lookup"><span data-stu-id="57a32-119">Reinstall certificates.</span></span>

  - <span data-ttu-id="57a32-120">サーバーがデータベースをホストしている場合は、Microsoft SQL Server 2012 または Microsoft SQL Server 2008 R2 をインストールします。</span><span class="sxs-lookup"><span data-stu-id="57a32-120">If the server hosted a database, install Microsoft SQL Server 2012 or Microsoft SQL Server 2008 R2.</span></span>

  - <span data-ttu-id="57a32-121">一般的に、サーバーがデータベースをホストしていた場合は、トポロジビルダーを実行して、データベースを作成およびインストールし、アクセス制御リスト (Acl) を設定します。</span><span class="sxs-lookup"><span data-stu-id="57a32-121">In general, if the server hosted a database, run Topology Builder to create and install the database and set up access control lists (ACLs).</span></span>

  - <span data-ttu-id="57a32-122">通常、サーバーがサーバーの役割をホストしている場合は、Lync Server 展開ウィザードの手順 1 ~ 4 を実行して、ローカル構成ファイルをインストールし、サーバーの役割コンポーネントをインストールし、証明書を割り当て、サービスを開始します。</span><span class="sxs-lookup"><span data-stu-id="57a32-122">In general, if the server hosted a server role, run step 1 through step 4 of the Lync Server Deployment Wizard to install the local configuration files, install the server role components, assign certificates, and start the services.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="57a32-123">サーバーがサーバーの役割と併置されているデータベースをホストしていた場合は、Lync Server Deployment ウィザードの手順2を実行すると、データベースが再作成されます。</span><span class="sxs-lookup"><span data-stu-id="57a32-123">If the server hosted a database collocated with the server role, running step 2 of the Lync Server Deployment Wizard recreates the database.</span></span>

    
    </div>

  - <span data-ttu-id="57a32-124">サーバーがデータベースをホストしていた場合は、バックアップしたデータを復元します。</span><span class="sxs-lookup"><span data-stu-id="57a32-124">If the server hosted a database, restore the backed up data.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

