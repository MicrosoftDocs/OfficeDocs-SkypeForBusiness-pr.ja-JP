---
title: 'Lync Server 2013: 常設チャットサーバーに必要なリソース'
description: 'Lync Server 2013: 常設チャットサーバーに必要なリソース。'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Required resources
ms:assetid: bce50b95-f3c8-407e-963a-d8896ee77fbc
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205211(v=OCS.15)
ms:contentKeyID: 48185255
ms.date: 02/05/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 18c81f0017428e4305e46fbcf5580a83af38accf
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48542553"
---
# <a name="required-resources-for-persistent-chat-server-in-lync-server-2013"></a><span data-ttu-id="74381-103">Lync Server 2013 の常設チャットサーバーに必要なリソース</span><span class="sxs-lookup"><span data-stu-id="74381-103">Required resources for Persistent Chat Server in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="74381-104">_**トピックの最終更新日:** 2016-02-05_</span><span class="sxs-lookup"><span data-stu-id="74381-104">_**Topic Last Modified:** 2016-02-05_</span></span>

<span data-ttu-id="74381-105">常設チャットサーバーの高可用性および障害復旧には、通常、完全な操作に必要なものを超える追加リソースが必要です。</span><span class="sxs-lookup"><span data-stu-id="74381-105">High availability and disaster recovery for Persistent Chat Server requires additional resources beyond what is typically needed for full operation.</span></span> <span data-ttu-id="74381-106">常設チャットサーバーを高可用性および障害復旧用に構成する前に、標準の常設チャットサーバー操作に必要なものに加えて、次のリソースがあることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="74381-106">Before configuring Persistent Chat Server for high availability and disaster recovery, ensure that you have the following resources in addition to what is required for standard Persistent Chat Server operation.</span></span> <span data-ttu-id="74381-107">その他の構成情報については、「 [Lync server 2013 での常設チャットサーバーの構成](lync-server-2013-configuring-persistent-chat-server.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="74381-107">For additional configuration information, see [Configuring Persistent Chat Server in Lync Server 2013](lync-server-2013-configuring-persistent-chat-server.md).</span></span>

  - <span data-ttu-id="74381-108">常設チャットサーバーサービスのホームフロントエンドが配置されている同じ物理データセンター内にある1つの専用データベースインスタンス。</span><span class="sxs-lookup"><span data-stu-id="74381-108">One dedicated database instance located in the same physical data center in which the home front end of the Persistent Chat Server service is located.</span></span> <span data-ttu-id="74381-109">このデータベースは、プライマリ常設チャットデータベースの SQL Server ミラーとして機能します。</span><span class="sxs-lookup"><span data-stu-id="74381-109">This database will serve as the SQL Server mirror for the primary Persistent Chat database.</span></span> <span data-ttu-id="74381-110">必要に応じて、ミラーデータベースへの自動フェールオーバーが必要な場合は、ミラーリング監視として機能する追加の SQL Server を指定します。</span><span class="sxs-lookup"><span data-stu-id="74381-110">Optionally, designate an additional SQL Server to serve as the mirroring witness if you want an automated failover to the mirror database.</span></span>

  - <span data-ttu-id="74381-111">他の物理データ センターに存在する、1 つの専用データベース インスタンス。</span><span class="sxs-lookup"><span data-stu-id="74381-111">One dedicated database instance located in the other physical data center.</span></span> <span data-ttu-id="74381-112">このデータベースは、プライマリデータセンターのデータベースの SQL Server ログ配布セカンダリデータベースとして機能します。</span><span class="sxs-lookup"><span data-stu-id="74381-112">This database will serve as the SQL Server Log Shipping secondary database for the database in the primary data center.</span></span>

  - <span data-ttu-id="74381-113">セカンダリデータベースの SQL Server ミラーとして機能する1つの専用データベースインスタンス。</span><span class="sxs-lookup"><span data-stu-id="74381-113">One dedicated database instance to serve as the SQL Server mirror for the secondary database.</span></span> <span data-ttu-id="74381-114">必要に応じて、ミラーリング監視として追加の SQL Server をサーバーに指定します。</span><span class="sxs-lookup"><span data-stu-id="74381-114">Optionally, designate an additional SQL Server to server as the mirroring witness.</span></span> <span data-ttu-id="74381-115">どちらもセカンダリ データベースと同じ物理データ センターに存在する必要があります。</span><span class="sxs-lookup"><span data-stu-id="74381-115">Both of these must be located in the same physical data center as the secondary database.</span></span>

  - <span data-ttu-id="74381-116">常設チャットサーバーのコンプライアンスが有効になっている場合は、さらに3つの専用データベースインスタンスが必要です。</span><span class="sxs-lookup"><span data-stu-id="74381-116">If Persistent Chat Server compliance is enabled, an additional three dedicated database instances are required.</span></span> <span data-ttu-id="74381-117">その配布は、常設チャットデータベースに対して既に概説されているものと同じです。</span><span class="sxs-lookup"><span data-stu-id="74381-117">Their distribution is the same as those previously outlined for the Persistent Chat database.</span></span> <span data-ttu-id="74381-118">コンプライアンスデータベースで永続的なチャットデータベースと同じ SQL Server インスタンスを共有することはできますが、高可用性と障害復旧のためにスタンドアロンのインスタンスを使用することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="74381-118">While it is possible for the compliance database to share the same SQL Server instance as the Persistent Chat database, we recommend standalone instances for high availability and disaster recovery.</span></span>

  - <span data-ttu-id="74381-119">ファイル共有を作成し、SQL Server ログ配布のトランザクションログに指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="74381-119">A file share must be created and designated for the SQL Server Log Shipping transaction logs.</span></span> <span data-ttu-id="74381-120">常設チャットデータベースを実行する両方のデータセンター内のすべての SQL サーバーは、このファイル共有に対する読み取り/書き込みアクセス権を持っている必要があります。</span><span class="sxs-lookup"><span data-stu-id="74381-120">All SQL Servers in both data centers that run Persistent Chat databases must have read/write access to this file share.</span></span> <span data-ttu-id="74381-121">この共有は、FileStore 役割の一部として定義されません。</span><span class="sxs-lookup"><span data-stu-id="74381-121">This share is not defined as part of a FileStore role.</span></span>

  - <span data-ttu-id="74381-122">プライマリサーバーのファイル共有からコピーされる SQL Server トランザクションログのコピー先フォルダーとして機能するセカンダリデータベースサーバー上のファイル共有。</span><span class="sxs-lookup"><span data-stu-id="74381-122">A file share on the secondary database server to serve as the destination folder for the SQL Server transaction logs that are copied from the primary server file share.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="74381-123">常設チャットサーバープール内のアクティブな常設チャットサーバーは、トポロジで定義されている次ホップの Lync プールと同じタイムゾーンに存在する必要があります。</span><span class="sxs-lookup"><span data-stu-id="74381-123">Active Persistent Chat servers in a Persistent Chat Server pool MUST reside in the same time zone as the next hop Lync Pool defined in the topology.</span></span>



</div>

<span data-ttu-id="74381-124">次の図は、2つの異なる拡張プールトポロジで常設チャットサーバープール全体を構成する方法についての例を示しています。</span><span class="sxs-lookup"><span data-stu-id="74381-124">The following figures provide examples about how the entire Persistent Chat Server pool can be configured in the two different stretched pool topologies:</span></span>

  - <span data-ttu-id="74381-125">データ センターが高帯域幅/低遅延の場所に設置されている場合の拡張常設チャット サーバー プール</span><span class="sxs-lookup"><span data-stu-id="74381-125">Stretched Persistent Chat Server pool when data centers are geo-located with high bandwidth/low latency.</span></span>

  - <span data-ttu-id="74381-126">データ センターが低帯域幅/高遅延の場所に設置されている場合の拡張常設チャット サーバー プール</span><span class="sxs-lookup"><span data-stu-id="74381-126">Stretched Persistent Chat Server pool when data centers are geo-located with low bandwidth/high latency.</span></span>

<span data-ttu-id="74381-127">次の図は、データセンターが高帯域幅/低遅延の場所に設置されている、拡張された常設チャットサーバープールのトポロジを示しています。</span><span class="sxs-lookup"><span data-stu-id="74381-127">The following figure shows a stretched Persistent Chat Server pool topology where data centers are geo-located with high bandwidth/low latency.</span></span>

<span data-ttu-id="74381-128">**データ センターが高帯域幅/低遅延の場所に設置されている場合の拡張常設チャット サーバー プール**</span><span class="sxs-lookup"><span data-stu-id="74381-128">**Stretched Persistent Chat Server pool when data centers are geo-located with high bandwidth/low latency.**</span></span>

<span data-ttu-id="74381-129">![常設チャットサーバープール HBW 構成試験](images/JJ205211.55d10910-c824-41e6-bed2-08d13a2abd65(OCS.15).jpg "常設チャットサーバープール HBW 構成試験")</span><span class="sxs-lookup"><span data-stu-id="74381-129">![Persistent Chat Server pool HBW configuration exam](images/JJ205211.55d10910-c824-41e6-bed2-08d13a2abd65(OCS.15).jpg "Persistent Chat Server pool HBW configuration exam")</span></span>

<span data-ttu-id="74381-130">次の図は、データセンターが低帯域幅/高遅延の場所に設置された、拡張された常設チャットサーバープールトポロジを示しています。</span><span class="sxs-lookup"><span data-stu-id="74381-130">The following figure shows a stretched Persistent Chat Server pool topology where data centers are geo-located with low bandwidth/high latency.</span></span>

<span data-ttu-id="74381-131">**データ センターが低帯域幅/高遅延の場所に設置されている場合の拡張常設チャット サーバー プール**</span><span class="sxs-lookup"><span data-stu-id="74381-131">**Stretched Persistent Chat Server pool when data centers are geo-located with low bandwidth/high latency.**</span></span>

<span data-ttu-id="74381-132">![常設チャットサーバープールの LBW 構成試験](images/JJ205211.586b0a3a-3767-4991-944f-ee54389512aa(OCS.15).jpg "常設チャットサーバープールの LBW 構成試験")</span><span class="sxs-lookup"><span data-stu-id="74381-132">![Persistent Chat Server pool LBW configuration exam](images/JJ205211.586b0a3a-3767-4991-944f-ee54389512aa(OCS.15).jpg "Persistent Chat Server pool LBW configuration exam")</span></span>

</div>

<span> </span>

</div>

</div>

</div>

