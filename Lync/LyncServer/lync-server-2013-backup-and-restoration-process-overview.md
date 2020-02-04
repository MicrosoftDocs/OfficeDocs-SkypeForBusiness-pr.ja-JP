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
ms.openlocfilehash: 559ebb5a5d5ba91b5a4952037c18ad509ed5cec7
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41728957"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="backup-and-restoration-process-overview-for-lync-server-2013"></a><span data-ttu-id="1e2ce-102">Lync Server 2013 のバックアップと復元プロセスの概要</span><span class="sxs-lookup"><span data-stu-id="1e2ce-102">Backup and restoration process overview for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1e2ce-103">_**最終更新日:** 2013-03-26_</span><span class="sxs-lookup"><span data-stu-id="1e2ce-103">_**Topic Last Modified:** 2013-03-26_</span></span>

<span data-ttu-id="1e2ce-104">このセクションでは、Lync Server 2013 のバックアップと復元プロセスのしくみの概要について説明します。</span><span class="sxs-lookup"><span data-stu-id="1e2ce-104">This section provides an overview of how the backup and restoration process works for Lync Server 2013.</span></span> <span data-ttu-id="1e2ce-105">すべての Standard Edition server および Enterprise Edition server では、場所に関係なく同じプロセスを使用します。</span><span class="sxs-lookup"><span data-stu-id="1e2ce-105">You use the same process for all Standard Edition servers and Enterprise Edition servers, regardless of their location.</span></span>

<span data-ttu-id="1e2ce-106">一般的に、バックアッププロセスは次のように動作します。</span><span class="sxs-lookup"><span data-stu-id="1e2ce-106">In general, the backup process works as follows:</span></span>

  - <span data-ttu-id="1e2ce-107">任意のプールに含まれていないスタンドアロンコンピューター上の共有フォルダーとして、バックアップの場所を作成します。</span><span class="sxs-lookup"><span data-stu-id="1e2ce-107">You create a backup location as a shared folder on a stand-alone computer that is not part of any pool.</span></span> <span data-ttu-id="1e2ce-108">バックアップの場所は **$Backup**で参照されます。</span><span class="sxs-lookup"><span data-stu-id="1e2ce-108">The location of the backup is referenced in **$Backup**.</span></span>

  - <span data-ttu-id="1e2ce-109">定期的にスケジュールが設定されている場合は、「lync server 2013 のバックアップと復元の要件」 [2013](lync-server-2013-backing-up-lync-server.md)で説明した手順に従って、lync server データベースと[バックアップと復元の要件](lync-server-2013-backup-and-restoration-requirements-data.md)について説明している、すべてのサーバーの設定と構成が含まれます。</span><span class="sxs-lookup"><span data-stu-id="1e2ce-109">On a regular, scheduled basis, you back up all the Lync Server databases and all the file stores that are described in [Backup and restoration requirements in Lync Server 2013: data](lync-server-2013-backup-and-restoration-requirements-data.md) by following the procedures described in [Backing up Lync Server 2013](lync-server-2013-backing-up-lync-server.md) The Central Management store includes all the server settings and configurations.</span></span>

  - <span data-ttu-id="1e2ce-110">それ以降のバックアップを実行するたびに、新しい共有フォルダーを作成し、参照を **$Backup**パスを変更します。</span><span class="sxs-lookup"><span data-stu-id="1e2ce-110">Each time you run a subsequent backup, you create a new shared folder and change the path that **$Backup** references.</span></span>

<span data-ttu-id="1e2ce-111">通常、復元プロセスは次のように動作します。</span><span class="sxs-lookup"><span data-stu-id="1e2ce-111">In general, the restoration process works as follows:</span></span>

  - <span data-ttu-id="1e2ce-112">障害または障害が発生した場合は、 **$Backup**によって参照されている場所のデータを新しいコンピューターまたはクリーンコンピューターに復元します。</span><span class="sxs-lookup"><span data-stu-id="1e2ce-112">When a failure or outage occurs, you restore the data in the location referenced by **$Backup** to new or clean computers.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="1e2ce-113">この復元プロセスでは、既存のサーバーの状態にデータが復元されることはありません。</span><span class="sxs-lookup"><span data-stu-id="1e2ce-113">This restoration process does not restore data onto an existing server state.</span></span> <span data-ttu-id="1e2ce-114">つまり、このプロセスではサーバーがクリーンまたは新規である必要があります。</span><span class="sxs-lookup"><span data-stu-id="1e2ce-114">That is, this process requires that the server is clean or new.</span></span>

    
    </div>

  - <span data-ttu-id="1e2ce-115">ユーザーと会議の情報をエラーの発生時に回復できるようにするために、「 [Lync Server 2013 での高可用性と障害回復の計画](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md)」で説明されているように、フロントエンドプールがペアになった障害回復トポロジを実装できます。</span><span class="sxs-lookup"><span data-stu-id="1e2ce-115">To enable your user and conference information to be recoverable to the point of failure, you can implement a disaster recovery topology with paired Front End pools, as described in [Planning for high availability and disaster recovery in Lync Server 2013](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md).</span></span>

  - <span data-ttu-id="1e2ce-116">すべてのドメインネームシステム (DNS) 構成、動的ホスト構成プロトコル (DHCP) 構成、ドメイン名、コンピューターの完全修飾ドメイン名 (Fqdn)、ファイルストアパスなどは、復元時に同じである必要があります。バックアップ。</span><span class="sxs-lookup"><span data-stu-id="1e2ce-116">All Domain Name System (DNS) configuration, Dynamic Host Configuration Protocol (DHCP) configuration, domain names, computer fully qualified domain names (FQDNs), file store paths, and so on must be the same at the time of restoration that they were at the time of back up.</span></span>

<span data-ttu-id="1e2ce-117">Lync Server が実行されているサーバーで障害が発生した場合、次の手順に従います。</span><span class="sxs-lookup"><span data-stu-id="1e2ce-117">If a server running Lync Server fails, recovery includes the following steps:</span></span>

  - <span data-ttu-id="1e2ce-118">故障したコンピューターと同じ FQDN を使用して、新しいまたはクリーンなコンピューターにオペレーティングシステムをインストールします。</span><span class="sxs-lookup"><span data-stu-id="1e2ce-118">Install the operating system on a new or clean computer with the same FQDN as the failed computer.</span></span>

  - <span data-ttu-id="1e2ce-119">証明書を再インストールします。</span><span class="sxs-lookup"><span data-stu-id="1e2ce-119">Reinstall certificates.</span></span>

  - <span data-ttu-id="1e2ce-120">サーバーがデータベースをホストしている場合は、Microsoft SQL Server 2012 または Microsoft SQL Server 2008 R2 をインストールします。</span><span class="sxs-lookup"><span data-stu-id="1e2ce-120">If the server hosted a database, install Microsoft SQL Server 2012 or Microsoft SQL Server 2008 R2.</span></span>

  - <span data-ttu-id="1e2ce-121">一般的に、サーバーがデータベースをホストしている場合は、トポロジビルダーを実行してデータベースを作成してインストールし、アクセス制御リスト (Acl) を設定します。</span><span class="sxs-lookup"><span data-stu-id="1e2ce-121">In general, if the server hosted a database, run Topology Builder to create and install the database and set up access control lists (ACLs).</span></span>

  - <span data-ttu-id="1e2ce-122">通常、サーバーの役割をホストしているサーバーの場合は、Lync Server 展開ウィザードの手順1から4を実行して、ローカル構成ファイルをインストールし、サーバーの役割コンポーネントをインストールして、証明書を割り当て、サービスを開始します。</span><span class="sxs-lookup"><span data-stu-id="1e2ce-122">In general, if the server hosted a server role, run step 1 through step 4 of the Lync Server Deployment Wizard to install the local configuration files, install the server role components, assign certificates, and start the services.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="1e2ce-123">サーバーがサーバーの役割と連携しているデータベースをホストしている場合は、Lync Server 展開ウィザードの手順2を実行するとデータベースが再作成されます。</span><span class="sxs-lookup"><span data-stu-id="1e2ce-123">If the server hosted a database collocated with the server role, running step 2 of the Lync Server Deployment Wizard recreates the database.</span></span>

    
    </div>

  - <span data-ttu-id="1e2ce-124">サーバーがデータベースをホストしている場合は、バックアップしたデータを復元します。</span><span class="sxs-lookup"><span data-stu-id="1e2ce-124">If the server hosted a database, restore the backed up data.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

