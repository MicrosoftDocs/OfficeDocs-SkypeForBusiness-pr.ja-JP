---
title: Lync Server 2013 データベースソフトウェアのサポート
description: Lync Server 2013 データベースソフトウェアサポート。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Database software support
ms:assetid: e05d0032-bbea-4e61-987d-d07b1c045fd5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398990(v=OCS.15)
ms:contentKeyID: 48185517
ms.date: 12/02/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1c5d7b44e5febc4123dbcdf7072b98fcfd004609
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48558153"
---
# <a name="database-software-support-in-lync-server-2013"></a><span data-ttu-id="4fe75-103">Lync Server 2013 でのデータベースソフトウェアのサポート</span><span class="sxs-lookup"><span data-stu-id="4fe75-103">Database software support in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4fe75-104">_**トピックの最終更新日:** 2014-12-01_</span><span class="sxs-lookup"><span data-stu-id="4fe75-104">_**Topic Last Modified:** 2014-12-01_</span></span>

<span data-ttu-id="4fe75-105">Lync Server 2013 では、次のデータベース管理システムがサポートされています。</span><span class="sxs-lookup"><span data-stu-id="4fe75-105">Lync Server 2013 supports the following database management systems:</span></span>

  - <span data-ttu-id="4fe75-106">**フロントエンドプールのバックエンドデータベース、アーカイブデータベース、監視データベース、常設チャットデータベース、および常設チャットコンプライアンスデータベース**</span><span class="sxs-lookup"><span data-stu-id="4fe75-106">**Back-end database of a Front End pool, Archiving database, Monitoring database, persistent chat database, and persistent chat compliance database**</span></span>
    
      - <span data-ttu-id="4fe75-107">Microsoft SQL Server 2008 R2 Enterprise データベースソフトウェア (64 ビット版)。</span><span class="sxs-lookup"><span data-stu-id="4fe75-107">Microsoft SQL Server 2008 R2 Enterprise database software (64-bit edition).</span></span> <span data-ttu-id="4fe75-108">また、最新のサービスパックを実行することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="4fe75-108">Additionally running the latest service pack is recommended.</span></span>
    
      - <span data-ttu-id="4fe75-109">Microsoft SQL Server 2008 R2 Standard (64-ビット版)。</span><span class="sxs-lookup"><span data-stu-id="4fe75-109">Microsoft SQL Server 2008 R2 Standard (64-bit edition).</span></span> <span data-ttu-id="4fe75-110">また、最新のサービスパックを実行することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="4fe75-110">Additionally running the latest service pack is recommended.</span></span>
    
      - <span data-ttu-id="4fe75-111">Microsoft SQL Server 2012 Enterprise (64 ビット版)。</span><span class="sxs-lookup"><span data-stu-id="4fe75-111">Microsoft SQL Server 2012 Enterprise (64-bit edition).</span></span> <span data-ttu-id="4fe75-112">また、最新のサービスパックを実行することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="4fe75-112">Additionally running the latest service pack is recommended.</span></span>
    
      - <span data-ttu-id="4fe75-113">Microsoft SQL Server 2012 Standard (64 ビット版)。</span><span class="sxs-lookup"><span data-stu-id="4fe75-113">Microsoft SQL Server 2012 Standard (64-bit edition).</span></span> <span data-ttu-id="4fe75-114">また、最新のサービスパックを実行することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="4fe75-114">Additionally running the latest service pack is recommended.</span></span>

  - <span data-ttu-id="4fe75-115">**Standard Edition サーバーデータベースとフロントエンドサーバーデータベース**</span><span class="sxs-lookup"><span data-stu-id="4fe75-115">**Standard Edition server database and Front End Server databases**</span></span>
    
      - <span data-ttu-id="4fe75-116">Microsoft SQL Server 2012 Express (64 ビット版)。</span><span class="sxs-lookup"><span data-stu-id="4fe75-116">Microsoft SQL Server 2012 Express (64-bit edition).</span></span> <span data-ttu-id="4fe75-117">また、最新のサービスパックを実行することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="4fe75-117">Additionally running the latest service pack is recommended.</span></span>
        
        <span data-ttu-id="4fe75-118">フロントエンドサーバーおよび Standard Edition サーバー上での Microsoft SQL Server のパッチとアップグレードをサポートしています。</span><span class="sxs-lookup"><span data-stu-id="4fe75-118">We support the patching and upgrade of Microsoft SQL Server on Front End Servers and Standard Edition servers.</span></span> <span data-ttu-id="4fe75-119">ただし、フロントエンドサーバーで任意の種類のアップグレードまたはパッチを作成する場合は、クォーラム要件を考慮する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4fe75-119">However, when you make any kind of upgrade or patch on Front End Servers, you must account for quorum requirements.</span></span> <span data-ttu-id="4fe75-120">詳細については、「lync [server 2013 でのフロントエンドサーバーのアップグレードまたは更新](lync-server-2013-upgrade-or-update-front-end-servers.md) 」および「 [lync server 2013 でのフロントエンドサーバー、インスタントメッセージング、プレゼンスのトポロジとコンポーネント](lync-server-2013-topologies-and-components-for-front-end-servers-instant-messaging-and-presence.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4fe75-120">For more information, see [Upgrade or update Front End Servers in Lync Server 2013](lync-server-2013-upgrade-or-update-front-end-servers.md) and [Topologies and components for Front End Servers, instant messaging, and presence in Lync Server 2013](lync-server-2013-topologies-and-components-for-front-end-servers-instant-messaging-and-presence.md).</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="4fe75-121">Microsoft SQL Server 2012 Express (64 ビット版) は、各 Standard Edition サーバーと各フロントエンドサーバーサーバーに Lync Server 2013 によって自動的にインストールされます。</span><span class="sxs-lookup"><span data-stu-id="4fe75-121">Microsoft SQL Server 2012 Express (64-bit edition) is automatically installed by Lync Server 2013 on each Standard Edition server and each Front End Server server.</span></span>

    
    </div>

<div>


> [!IMPORTANT]  
> <UL>
> <LI>
> <P><span data-ttu-id="4fe75-122">Lync Server 2013 は、32ビット版の SQL Server をサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="4fe75-122">Lync Server 2013 does not support the 32-bit edition of SQL Server.</span></span> <span data-ttu-id="4fe75-123">64ビット版を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4fe75-123">You must use the 64-bit edition.</span></span></P>
> <LI>
> <P><span data-ttu-id="4fe75-124">SQL Server Web edition および SQL Server Workgroup edition はサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="4fe75-124">SQL Server Web edition and SQL Server Workgroup edition are not supported.</span></span> <span data-ttu-id="4fe75-125">これらを Lync Server 2013 で使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="4fe75-125">You cannot use them with Lync Server 2013.</span></span></P>
> <LI>
> <P><span data-ttu-id="4fe75-126">Lync Server 2013 は、ネイティブデータベースミラーリングをサポートしています。</span><span class="sxs-lookup"><span data-stu-id="4fe75-126">Lync Server 2013 does support native database mirroring.</span></span></P>
> <LI>
> <P><span data-ttu-id="4fe75-127">監視サーバーの役割を使用するには、SQL Server Reporting Services をインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="4fe75-127">To use the Monitoring Server role, you should install SQL Server Reporting Services.</span></span></P></LI></UL>



</div>

<span data-ttu-id="4fe75-128">フロントエンドプールでは、バックエンドデータベースを単一の SQL Server コンピューターにすることができます。</span><span class="sxs-lookup"><span data-stu-id="4fe75-128">In a Front End pool, the back-end database can be a single SQL Server computer.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="4fe75-129">Lync Server データベースを他のデータベースと併置する場合は、可用性とパフォーマンスに影響する可能性のあるすべての要因を評価し、一方のノードに障害が発生した場合は、残りのノードが負荷を処理できることを確認することを強くお勧めします。</span><span class="sxs-lookup"><span data-stu-id="4fe75-129">If you collocate Lync Server databases with other databases, we highly recommend assessing all factors that might affect availability and performance, as well as ensuring that, if one node fails, the remaining node can handle the load.</span></span> <span data-ttu-id="4fe75-130">フェールオーバー機能を検証する場合は、すべてのフェールオーバー シナリオをテストすることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="4fe75-130">To verify failover capabilities, we recommend testing all failover scenarios.</span></span>



</div>

<div>

## <a name="using-sql-mirroring-and-sql-clustering"></a><span data-ttu-id="4fe75-131">SQL ミラーリングと SQL クラスタリングの使用</span><span class="sxs-lookup"><span data-stu-id="4fe75-131">Using SQL Mirroring and SQL Clustering</span></span>

<span data-ttu-id="4fe75-132">Lync Server 2013 では、各 Lync Server データベースに対して SQL ミラーリングまたは SQL クラスタリングの使用をサポートしています。</span><span class="sxs-lookup"><span data-stu-id="4fe75-132">Lync Server 2013 supports the use of either SQL mirroring or SQL clustering for each Lync Server database.</span></span> <span data-ttu-id="4fe75-133">Lync Server 2013 のトポロジビルダーツールを使用して、SQL ミラーリングを簡単にセットアップできます。</span><span class="sxs-lookup"><span data-stu-id="4fe75-133">You can easily set up SQL mirroring with the Topology Builder tool in Lync Server 2013.</span></span> <span data-ttu-id="4fe75-134">SQL フェールオーバークラスタリングでは、セットアップに SQL Server を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4fe75-134">For SQL failover clustering, you must use SQL Server for setup.</span></span>

<span data-ttu-id="4fe75-135">Lync server 2013 では、greenfield の展開や、以前のバージョンの Lync Server からアップグレードした組織を含む、すべての展開において SQL ミラーリングと SQL クラスタリングの両方のトポロジがサポートされています。</span><span class="sxs-lookup"><span data-stu-id="4fe75-135">Lync Server 2013 supports both SQL mirroring and SQL clustering topologies for all deployments, including greenfield deployments and organizations that have upgraded from previous versions of Lync Server.</span></span>

<span data-ttu-id="4fe75-136">SQL クラスタリングは、アクティブ/パッシブ構成でサポートされています。</span><span class="sxs-lookup"><span data-stu-id="4fe75-136">SQL Clustering support is for an active/passive configuration.</span></span> <span data-ttu-id="4fe75-137">パフォーマンス上の理由から、パッシブノードは他の SQL インスタンスと共有しないでください。</span><span class="sxs-lookup"><span data-stu-id="4fe75-137">For performance reasons, the passive node should not be shared by any other SQL instance.</span></span>

<span data-ttu-id="4fe75-138">次のサポートが含まれています。</span><span class="sxs-lookup"><span data-stu-id="4fe75-138">The following support is included:</span></span>

  - <span data-ttu-id="4fe75-139">次の2ノードフェールオーバークラスタリング:</span><span class="sxs-lookup"><span data-stu-id="4fe75-139">Two-node failover clustering for the following:</span></span>
    
      - <span data-ttu-id="4fe75-140">Microsoft SQL Server 2012 Standard (64 ビット版)。</span><span class="sxs-lookup"><span data-stu-id="4fe75-140">Microsoft SQL Server 2012 Standard (64-bit edition).</span></span> <span data-ttu-id="4fe75-141">また、最新のサービスパックを実行することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="4fe75-141">Additionally running the latest service pack is recommended.</span></span>
    
      - <span data-ttu-id="4fe75-142">Microsoft SQL Server 2008 R2 Standard (64-ビット版)。</span><span class="sxs-lookup"><span data-stu-id="4fe75-142">Microsoft SQL Server 2008 R2 Standard (64-bit edition).</span></span> <span data-ttu-id="4fe75-143">また、最新のサービスパックを実行することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="4fe75-143">Additionally running the latest service pack is recommended.</span></span>

  - <span data-ttu-id="4fe75-144">最大16ノードのフェールオーバークラスタリングは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="4fe75-144">Up to sixteen-node failover clustering for the following:</span></span>
    
      - <span data-ttu-id="4fe75-145">Microsoft SQL Server 2012 Enterprise (64 ビット版)。</span><span class="sxs-lookup"><span data-stu-id="4fe75-145">Microsoft SQL Server 2012 Enterprise (64-bit edition).</span></span> <span data-ttu-id="4fe75-146">また、最新のサービスパックを実行することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="4fe75-146">Additionally running the latest service pack is recommended.</span></span>
    
      - <span data-ttu-id="4fe75-147">Microsoft SQL Server 2008 R2 Enterprise データベースソフトウェア (64 ビット版)。</span><span class="sxs-lookup"><span data-stu-id="4fe75-147">Microsoft SQL Server 2008 R2 Enterprise database software (64-bit edition).</span></span> <span data-ttu-id="4fe75-148">また、最新のサービスパックを実行することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="4fe75-148">Additionally running the latest service pack is recommended.</span></span>

<span data-ttu-id="4fe75-149">SQL ミラーリングの詳細については、「 [Lync server 2013 のバックエンドサーバーの高可用性](lync-server-2013-back-end-server-high-availability.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4fe75-149">For more information about SQL mirroring, see [Back End Server high availability in Lync Server 2013](lync-server-2013-back-end-server-high-availability.md).</span></span> <span data-ttu-id="4fe75-150">SQL クラスタリングを展開する方法の詳細については、「 [CONFIGURE Sql Server クラスタリング For Lync Server 2013](lync-server-2013-configure-sql-server-clustering.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4fe75-150">For details on how to deploy SQL clustering, see [Configure SQL Server clustering for Lync Server 2013](lync-server-2013-configure-sql-server-clustering.md).</span></span>

<span data-ttu-id="4fe75-151">SQL Server 2012 のフェールオーバークラスタリングの詳細とベストプラクティスについては、「」を参照してください <https://technet.microsoft.com/library/hh231721.aspx> 。</span><span class="sxs-lookup"><span data-stu-id="4fe75-151">For more information and best practices for failover clustering in SQL Server 2012, see <https://technet.microsoft.com/library/hh231721.aspx>.</span></span> <span data-ttu-id="4fe75-152">SQL Server 2008 のフェールオーバークラスタリングについては、「」を参照してください <https://technet.microsoft.com/library/ms189134(v=sql.105).aspx> 。</span><span class="sxs-lookup"><span data-stu-id="4fe75-152">For failover clustering in SQL Server 2008, see <https://technet.microsoft.com/library/ms189134(v=sql.105).aspx>.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

