---
title: 'Lync Server 2013: データベース ソフトウェアのサポート'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Database software support
ms:assetid: e05d0032-bbea-4e61-987d-d07b1c045fd5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398990(v=OCS.15)
ms:contentKeyID: 48185517
ms.date: 12/02/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8bc8daef764ce5b15fd8c8b7e29f7031ebcfbafc
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34833737"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="database-software-support-in-lync-server-2013"></a><span data-ttu-id="e2fc9-102">Lync Server 2013 でのデータベース ソフトウェアのサポート</span><span class="sxs-lookup"><span data-stu-id="e2fc9-102">Database software support in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e2fc9-103">_**最終更新日:** 2014-12-01_</span><span class="sxs-lookup"><span data-stu-id="e2fc9-103">_**Topic Last Modified:** 2014-12-01_</span></span>

<span data-ttu-id="e2fc9-104">Lync Server 2013 では、次のデータベース管理システムがサポートされています。</span><span class="sxs-lookup"><span data-stu-id="e2fc9-104">Lync Server 2013 supports the following database management systems:</span></span>

  - <span data-ttu-id="e2fc9-105">**フロントエンド プールのバックエンド データベース、アーカイブ データベース、監視データベース、グループ チャット データベース、およびグループ チャット コンプライアンス データベース**</span><span class="sxs-lookup"><span data-stu-id="e2fc9-105">**Back-end database of a Front End pool, Archiving database, Monitoring database, persistent chat database, and persistent chat compliance database**</span></span>
    
      - <span data-ttu-id="e2fc9-p101">Microsoft SQL Server 2008 R2 Enterprise データベース ソフトウェア (64 ビット版)。追加で最新のサービス パックを実行することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="e2fc9-p101">Microsoft SQL Server 2008 R2 Enterprise database software (64-bit edition). Additionally running the latest service pack is recommended.</span></span>
    
      - <span data-ttu-id="e2fc9-108">Microsoft SQL Server 2008 R2 Standard (64 ビット版)。</span><span class="sxs-lookup"><span data-stu-id="e2fc9-108">Microsoft SQL Server 2008 R2 Standard (64-bit edition).</span></span> <span data-ttu-id="e2fc9-109">追加で最新のサービス パックを実行することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="e2fc9-109">Additionally running the latest service pack is recommended.</span></span>
    
      - <span data-ttu-id="e2fc9-p103">Microsoft SQL Server 2012 Enterprise (64 ビット版)。追加で最新のサービス パックを実行することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="e2fc9-p103">Microsoft SQL Server 2012 Enterprise (64-bit edition). Additionally running the latest service pack is recommended.</span></span>
    
      - <span data-ttu-id="e2fc9-p104">Microsoft SQL Server 2012 Standard (64 ビット版)。追加で最新のサービス パックを実行することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="e2fc9-p104">Microsoft SQL Server 2012 Standard (64-bit edition). Additionally running the latest service pack is recommended.</span></span>

  - <span data-ttu-id="e2fc9-114">**Standard Edition server データベースとフロントエンドサーバーデータベース**</span><span class="sxs-lookup"><span data-stu-id="e2fc9-114">**Standard Edition server database and Front End Server databases**</span></span>
    
      - <span data-ttu-id="e2fc9-115">Microsoft SQL Server 2012 Express (64 ビット版)。</span><span class="sxs-lookup"><span data-stu-id="e2fc9-115">Microsoft SQL Server 2012 Express (64-bit edition).</span></span> <span data-ttu-id="e2fc9-116">追加で最新のサービス パックを実行することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="e2fc9-116">Additionally running the latest service pack is recommended.</span></span>
        
        <span data-ttu-id="e2fc9-117">Microsoft は、フロントエンドサーバーと Standard Edition サーバーにおける Microsoft SQL Server の修正プログラムとアップグレードをサポートしています。</span><span class="sxs-lookup"><span data-stu-id="e2fc9-117">We support the patching and upgrade of Microsoft SQL Server on Front End Servers and Standard Edition servers.</span></span> <span data-ttu-id="e2fc9-118">ただし、フロントエンドサーバーに対して何らかのアップグレードまたは更新プログラムを作成する場合は、クォーラム要件を考慮する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e2fc9-118">However, when you make any kind of upgrade or patch on Front End Servers, you must account for quorum requirements.</span></span> <span data-ttu-id="e2fc9-119">詳細については、「[Upgrade or update Front End Servers in Lync Server 2013](lync-server-2013-upgrade-or-update-front-end-servers.md)」および「[Topologies and components for Front End Servers, instant messaging, and presence in Lync Server 2013](lync-server-2013-topologies-and-components-for-front-end-servers-instant-messaging-and-presence.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e2fc9-119">For more information, see [Upgrade or update Front End Servers in Lync Server 2013](lync-server-2013-upgrade-or-update-front-end-servers.md) and [Topologies and components for Front End Servers, instant messaging, and presence in Lync Server 2013](lync-server-2013-topologies-and-components-for-front-end-servers-instant-messaging-and-presence.md).</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="e2fc9-120">Microsoft SQL Server 2012 Express (64 ビット版) は、Lync Server 2013 (各標準エディションサーバーおよび各フロントエンドサーバーサーバー上) によって自動的にインストールされます。</span><span class="sxs-lookup"><span data-stu-id="e2fc9-120">Microsoft SQL Server 2012 Express (64-bit edition) is automatically installed by Lync Server 2013 on each Standard Edition server and each Front End Server server.</span></span>

    
    </div>

<div>


> [!IMPORTANT]  
> <UL>
> <LI>
> <P><span data-ttu-id="e2fc9-121">Lync Server 2013 では、32ビット版の SQL Server はサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="e2fc9-121">Lync Server 2013 does not support the 32-bit edition of SQL Server.</span></span> <span data-ttu-id="e2fc9-122">64 ビット版を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e2fc9-122">You must use the 64-bit edition.</span></span></P>
> <LI>
> <P><span data-ttu-id="e2fc9-123">SQL Server Web edition と SQL Server Workgroup edition はサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="e2fc9-123">SQL Server Web edition and SQL Server Workgroup edition are not supported.</span></span> <span data-ttu-id="e2fc9-124">Lync Server 2013 では使用できません。</span><span class="sxs-lookup"><span data-stu-id="e2fc9-124">You cannot use them with Lync Server 2013.</span></span></P>
> <LI>
> <P><span data-ttu-id="e2fc9-125">Lync Server 2013 では、ネイティブデータベースのミラーリングがサポートされています。</span><span class="sxs-lookup"><span data-stu-id="e2fc9-125">Lync Server 2013 does support native database mirroring.</span></span></P>
> <LI>
> <P><span data-ttu-id="e2fc9-126">監視サーバーの役割を使用するには、SQL Server Reporting Services をインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="e2fc9-126">To use the Monitoring Server role, you should install SQL Server Reporting Services.</span></span></P></LI></UL>



</div>

<span data-ttu-id="e2fc9-127">フロントエンドプールでは、バックエンドデータベースを単一の SQL Server コンピューターにすることができます。</span><span class="sxs-lookup"><span data-stu-id="e2fc9-127">In a Front End pool, the back-end database can be a single SQL Server computer.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="e2fc9-128">他のデータベースを使用して Lync Server データベースを作成する場合は、可用性とパフォーマンスに影響する可能性のあるすべての要素を評価することと、1つのノードに障害が発生した場合に、残りのノードがその読み込みを処理できることを確認することを強くお勧めします。</span><span class="sxs-lookup"><span data-stu-id="e2fc9-128">If you collocate Lync Server databases with other databases, we highly recommend assessing all factors that might affect availability and performance, as well as ensuring that, if one node fails, the remaining node can handle the load.</span></span> <span data-ttu-id="e2fc9-129">フェールオーバー機能を検証する場合は、すべてのフェールオーバー シナリオをテストすることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="e2fc9-129">To verify failover capabilities, we recommend testing all failover scenarios.</span></span>



</div>

<div>

## <a name="using-sql-mirroring-and-sql-clustering"></a><span data-ttu-id="e2fc9-130">SQL ミラーリングと SQL クラスタリングの使用</span><span class="sxs-lookup"><span data-stu-id="e2fc9-130">Using SQL Mirroring and SQL Clustering</span></span>

<span data-ttu-id="e2fc9-131">Lync Server 2013 では、各 Lync Server データベースに対して SQL ミラーリングと SQL クラスタリングのいずれかがサポートされています。</span><span class="sxs-lookup"><span data-stu-id="e2fc9-131">Lync Server 2013 supports the use of either SQL mirroring or SQL clustering for each Lync Server database.</span></span> <span data-ttu-id="e2fc9-132">Lync Server 2013 のトポロジビルダーツールを使用して、簡単に SQL ミラーリングを設定することができます。</span><span class="sxs-lookup"><span data-stu-id="e2fc9-132">You can easily set up SQL mirroring with the Topology Builder tool in Lync Server 2013.</span></span> <span data-ttu-id="e2fc9-133">SQL フェールオーバー クラスタリングの場合、設定に SQL Server を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e2fc9-133">For SQL failover clustering, you must use SQL Server for setup.</span></span>

<span data-ttu-id="e2fc9-134">Lync Server 2013 は、以前のバージョンの Lync Server からアップグレードしたから始めの展開や組織を含む、すべての展開で SQL ミラーリングと SQL クラスタリングのトポロジの両方をサポートしています。</span><span class="sxs-lookup"><span data-stu-id="e2fc9-134">Lync Server 2013 supports both SQL mirroring and SQL clustering topologies for all deployments, including greenfield deployments and organizations that have upgraded from previous versions of Lync Server.</span></span>

<span data-ttu-id="e2fc9-p111">SQL クラスタリングのサポートは、アクティブ/パッシブ構成用です。パフォーマンス上の理由から、パッシブ ノードを他の SQL インスタンスと共有しないでください。</span><span class="sxs-lookup"><span data-stu-id="e2fc9-p111">SQL Clustering support is for an active/passive configuration. For performance reasons, the passive node should not be shared by any other SQL instance.</span></span>

<span data-ttu-id="e2fc9-137">次のサポートが含まれます。</span><span class="sxs-lookup"><span data-stu-id="e2fc9-137">The following support is included:</span></span>

  - <span data-ttu-id="e2fc9-138">以下の製品用の 2 ノードのフェールオーバー クラスタリング:</span><span class="sxs-lookup"><span data-stu-id="e2fc9-138">Two-node failover clustering for the following:</span></span>
    
      - <span data-ttu-id="e2fc9-p112">Microsoft SQL Server 2012 Standard (64 ビット版)。追加で最新のサービス パックを実行することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="e2fc9-p112">Microsoft SQL Server 2012 Standard (64-bit edition). Additionally running the latest service pack is recommended.</span></span>
    
      - <span data-ttu-id="e2fc9-p113">Microsoft SQL Server 2008 R2 Standard (64 ビット版)。追加で最新のサービス パックを実行することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="e2fc9-p113">Microsoft SQL Server 2008 R2 Standard (64-bit edition). Additionally running the latest service pack is recommended.</span></span>

  - <span data-ttu-id="e2fc9-143">以下の製品用の最大 16 ノードのフェールオーバー クラスタリング:</span><span class="sxs-lookup"><span data-stu-id="e2fc9-143">Up to sixteen-node failover clustering for the following:</span></span>
    
      - <span data-ttu-id="e2fc9-p114">Microsoft SQL Server 2012 Enterprise (64 ビット版)。追加で最新のサービス パックを実行することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="e2fc9-p114">Microsoft SQL Server 2012 Enterprise (64-bit edition). Additionally running the latest service pack is recommended.</span></span>
    
      - <span data-ttu-id="e2fc9-p115">Microsoft SQL Server 2008 R2 Enterprise データベース ソフトウェア (64 ビット版)。追加で最新のサービス パックを実行することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="e2fc9-p115">Microsoft SQL Server 2008 R2 Enterprise database software (64-bit edition). Additionally running the latest service pack is recommended.</span></span>

<span data-ttu-id="e2fc9-148">SQL のミラーリングの詳細については、「 [Lync Server 2013 のバックエンドサーバーの高可用性](lync-server-2013-back-end-server-high-availability.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e2fc9-148">For more information about SQL mirroring, see [Back End Server high availability in Lync Server 2013](lync-server-2013-back-end-server-high-availability.md).</span></span> <span data-ttu-id="e2fc9-149">SQL クラスタリングの展開方法の詳細については、「 [Lync server 2013 用の Sql Server クラスタリングを構成](lync-server-2013-configure-sql-server-clustering.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e2fc9-149">For details on how to deploy SQL clustering, see [Configure SQL Server clustering for Lync Server 2013](lync-server-2013-configure-sql-server-clustering.md).</span></span>

<span data-ttu-id="e2fc9-150">SQL Server 2012 のフェールオーバークラスタリングの詳細とベストプラクティスについて<http://technet.microsoft.com/en-us/library/hh231721.aspx>は、を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e2fc9-150">For more information and best practices for failover clustering in SQL Server 2012, see <http://technet.microsoft.com/en-us/library/hh231721.aspx>.</span></span> <span data-ttu-id="e2fc9-151">SQL Server 2008 のフェールオーバークラスタリングについ<http://technet.microsoft.com/en-us/library/ms189134(v=sql.105).aspx>ては、を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e2fc9-151">For failover clustering in SQL Server 2008, see <http://technet.microsoft.com/en-us/library/ms189134(v=sql.105).aspx>.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

