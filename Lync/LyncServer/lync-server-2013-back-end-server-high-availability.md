---
title: 'Lync Server 2013: バックエンドサーバーの高可用性'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Back End Server high availability
ms:assetid: c559aacb-4e1d-4e78-9582-41f966ad418d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205248(v=OCS.15)
ms:contentKeyID: 48185358
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 335f7680a98eb53414a8b438975d79327b515946
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/21/2020
ms.locfileid: "42196970"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="back-end-server-high-availability-in-lync-server-2013"></a><span data-ttu-id="2a13a-102">Lync Server 2013 のバックエンドサーバーの高可用性</span><span class="sxs-lookup"><span data-stu-id="2a13a-102">Back End Server high availability in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2a13a-103">_**トピックの最終更新日:** 2013-08-12_</span><span class="sxs-lookup"><span data-stu-id="2a13a-103">_**Topic Last Modified:** 2013-08-12_</span></span>

<span data-ttu-id="2a13a-104">バックエンドサーバーの高可用性を確保するために、同期 SQL ミラーリングまたは SQL クラスタリングのどちらかを使用できます。</span><span class="sxs-lookup"><span data-stu-id="2a13a-104">To ensure high availability for your Back End Servers, you can use either synchronous SQL mirroring or SQL clustering.</span></span> <span data-ttu-id="2a13a-105">これらのソリューションのいずれかをオプションで使用しますが、組織のビジネス継続性を維持することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="2a13a-105">Using one of these solutions optional, but is recommended to maintain your organization's business continuity.</span></span> <span data-ttu-id="2a13a-106">Lync Server 2013 のバックエンドサーバーの高可用性については、非同期 SQL ミラーリングはサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="2a13a-106">Asynchronous SQL mirroring is not supported for Back End Server high availability in Lync Server 2013.</span></span> <span data-ttu-id="2a13a-107">これ以降、特に指定がない限り、SQL ミラーリングは同期 SQL ミラーリングを意味するものとします。</span><span class="sxs-lookup"><span data-stu-id="2a13a-107">In the rest of this document, SQL mirroring means synchronous SQL mirroring, unless otherwise explicitly stated.</span></span>

<span data-ttu-id="2a13a-108">トポロジビルダーを使用して、SQL ミラーリングを簡単にセットアップできます。</span><span class="sxs-lookup"><span data-stu-id="2a13a-108">You can easily set up SQL mirroring with Topology Builder.</span></span> <span data-ttu-id="2a13a-109">SQL フェールオーバークラスタリングでは、セットアップに SQL Server を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="2a13a-109">For SQL failover clustering, you must use SQL Server for setup.</span></span>

<span data-ttu-id="2a13a-110">障害復旧用の別のフロントエンドプールとペアになっているプールで SQL ミラーリングまたは SQL クラスタリングのいずれかを使用する場合は、両方のプールで同じバックエンド高可用性ソリューションを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="2a13a-110">If you use either SQL mirroring or SQL clustering in a pool which is paired with another Front End pool for disaster recovery, you should use the same Back End high availability solution in both pools.</span></span> <span data-ttu-id="2a13a-111">SQL クラスタリングを使用して、プールと SQL ミラーリングを使用してプールをペアにすることはできません。</span><span class="sxs-lookup"><span data-stu-id="2a13a-111">You should not pair a pool using SQL mirroring with a pool using SQL clustering.</span></span>

<span data-ttu-id="2a13a-112">SQL ミラーリングを展開すると、プール内のすべての Lync Server データベースがミラーリングされます。これには、中央管理ストア (このプールに配置されている場合)、応答グループアプリケーションデータベースおよびコールパークアプリケーションデータベース (それらのアプリケーションの場合) などがあります。がプールで実行されている。</span><span class="sxs-lookup"><span data-stu-id="2a13a-112">When you deploy SQL mirroring, all Lync Server databases in the pool are mirrored, including the Central Management store, if it is located in this pool, as well as the Response Group application database and the Call Park application database, if those applications are running in the pool.</span></span>

<span data-ttu-id="2a13a-p104">SQL ミラーリングでは、サーバーに対して共有ストレージを使用する必要はありません。各サーバーは、データベースのコピーをローカル ストレージに保持しします。</span><span class="sxs-lookup"><span data-stu-id="2a13a-p104">With SQL mirroring, you do not need to use shared storage for the servers. Each server keeps its copy of the databases in local storage.</span></span>

<span data-ttu-id="2a13a-p105">SQL ミラーリングの展開では、監視を使用することも使用しないこともできます。バックエンド サーバーのフェールオーバーが自動的になるので、監視を使用することをお勧めします。使用しない場合は、管理者が手動でフェールオーバーを実行する必要があります。監視を展開した場合でも、管理者は必要に応じてバックエンド サーバーのフェールオーバーを手動で開始できます。</span><span class="sxs-lookup"><span data-stu-id="2a13a-p105">You may choose to deploy SQL mirroring with or without a witness. We recommend using a witness because it enables failover of the Back End Server to be automatic. Otherwise, an administrator must manually invoke failover. Note that even if a witness is deployed, an administrator can manually invoke Back End Server failover, if necessary.</span></span>

<span data-ttu-id="2a13a-p106">監視を使用する場合は、バックエンド サーバーの複数のペアに対して 1 つの監視を使用できます。監視とバックエンド サーバーのペアを 1 対 1 で対応させる必要はありません。ただし、バックエンド サーバーの複数のペアに対して 1 つの監視を使用する展開は、ペアごとに異なる監視を使用するトポロジほど復元性が高くありません。</span><span class="sxs-lookup"><span data-stu-id="2a13a-p106">If you use a witness, you can use a single witness for multiple pairs of Back End Servers. There is no strict 1:1 correspondence between witnesses and pairs of Back End Servers. Deployments that use a single witness for multiple pairs of Back End Servers are not quite as resilient as topologies with a separate witness for each Back End Server pair.</span></span>

<span data-ttu-id="2a13a-122">SQL クラスタリングのサポートの詳細については、「 [Lync Server 2013 のデータベースソフトウェアサポート](lync-server-2013-database-software-support.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2a13a-122">For more information about SQL clustering support, see [Database software support in Lync Server 2013](lync-server-2013-database-software-support.md).</span></span> <span data-ttu-id="2a13a-123">SQL クラスタリングの展開の詳細については、「 [CONFIGURE Sql Server クラスタリング For Lync Server 2013](lync-server-2013-configure-sql-server-clustering.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2a13a-123">For details on deploying SQL clustering, see [Configure SQL Server clustering for Lync Server 2013](lync-server-2013-configure-sql-server-clustering.md).</span></span>

<div>

## <a name="recovery-time-for-automatic-back-end-server-failover-with-sql-mirroring"></a><span data-ttu-id="2a13a-124">SQL ミラーリングによるバックエンドサーバーの自動フェールオーバーの復旧時間</span><span class="sxs-lookup"><span data-stu-id="2a13a-124">Recovery Time for Automatic Back End Server Failover with SQL Mirroring</span></span>

<span data-ttu-id="2a13a-125">SQL ミラーリングを使用した自動バックエンドフェールオーバーの場合、目標復旧時間 (RTO) のエンジニアリング目標は5分です。</span><span class="sxs-lookup"><span data-stu-id="2a13a-125">For automatic Back End failover with SQL mirroring, the engineering target for recovery time objective (RTO) is 5 minutes.</span></span> <span data-ttu-id="2a13a-126">同期 SQL ミラーリングなので、バックエンド サーバー障害の間にデータ損失が発生する可能性は、サーバー間のデータ移動中にフロントエンド サーバーとバックエンド サーバーの両方が同時にダウンするという希な状況を除き、ありません。</span><span class="sxs-lookup"><span data-stu-id="2a13a-126">Because of the synchronous SQL mirroring, we do not anticipate data loss during Back End Server failures except in rare occasions when both the Front End Servers and the Back End Server go down simultaneously while data is being moved between the servers.</span></span> <span data-ttu-id="2a13a-127">目標復旧ポイント (RPO) のエンジニアリング目標は 5 分です。</span><span class="sxs-lookup"><span data-stu-id="2a13a-127">The engineering target for recovery point objective (RPO) is 5 minutes.</span></span>

</div>

<div>

## <a name="user-experience-during-back-end-server-failure-with-sql-mirroring"></a><span data-ttu-id="2a13a-128">SQL ミラーリングでバックエンドサーバー障害が発生したときのユーザー環境</span><span class="sxs-lookup"><span data-stu-id="2a13a-128">User Experience During Back End Server Failure with SQL Mirroring</span></span>

<span data-ttu-id="2a13a-129">障害の間のユーザー エクスペリエンスは、障害の特徴とトポロジによって異なります。</span><span class="sxs-lookup"><span data-stu-id="2a13a-129">User experience during a failure depends on the nature of the failure, and on your topology.</span></span>

<span data-ttu-id="2a13a-130">SQL ミラーリングを使用し、監視を構成していて、プリンシパルに障害が発生した場合、バックエンドサーバーのフェールオーバーは自動的に、かつ迅速に行われます。</span><span class="sxs-lookup"><span data-stu-id="2a13a-130">If you use SQL mirroring and have a witness configured, and the principal fails, Back End Server failover happens automatically and quickly.</span></span> <span data-ttu-id="2a13a-131">使用中のユーザーがセッションで大きな中断を感じることはありません。</span><span class="sxs-lookup"><span data-stu-id="2a13a-131">Active users should not notice much interruption to their ongoing sessions.</span></span>

<span data-ttu-id="2a13a-132">監視が構成されていない場合は、管理者が手動でフェールオーバーを起動するまでにしばらく時間がかかります。</span><span class="sxs-lookup"><span data-stu-id="2a13a-132">If there is no witness configured, it will take some time for the administrator to manually invoke the failover.</span></span> <span data-ttu-id="2a13a-133">その間、アクティブユーザーが影響を受ける可能性があります。</span><span class="sxs-lookup"><span data-stu-id="2a13a-133">During that time, active users may be affected.</span></span> <span data-ttu-id="2a13a-134">約30分間は通常どおりセッションを続行します。</span><span class="sxs-lookup"><span data-stu-id="2a13a-134">They will continue their sessions as normal for about 30 minutes.</span></span> <span data-ttu-id="2a13a-135">プライマリが依然として復元されていない場合、または管理者がバックアップにフェールオーバーしていない場合、ユーザーは復元モードに切り替わります。つまり、Lync Server で永続的な変更を必要とするタスク (連絡先の追加など) を実行できなくなります。</span><span class="sxs-lookup"><span data-stu-id="2a13a-135">If the primary is still not restored, or an administrator has not failed over to the backup, then users are switched to Resiliency mode, meaning that they are unable to perform tasks that require a persistent change on Lync Server (such as adding a contact).</span></span>

<span data-ttu-id="2a13a-p111">プリンシパルとミラーの両方のバックエンド サーバーで障害が発生した場合、またはどちらかのサーバーと監視で障害が発生した場合は、バックエンド サーバーは使用できなくなります (プリンシパルがまだ動作していたとしても)。この場合、使用中のユーザーはしばらくしてから復元モードに切り替えられます。</span><span class="sxs-lookup"><span data-stu-id="2a13a-p111">If both the principal and the mirror Back End Servers fail, or if one of those servers and the witness fails, the Back End Server will become unavailable (even if it is the principal that is still working). In this case, active users are switched to Resiliency mode after some time.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

