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
ms.openlocfilehash: 5708212aa2eb30cfcc3c3d40894ca2340475bd8b
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41740137"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="back-end-server-high-availability-in-lync-server-2013"></a><span data-ttu-id="1c538-102">Lync Server 2013 でのバックエンドサーバーの高可用性</span><span class="sxs-lookup"><span data-stu-id="1c538-102">Back End Server high availability in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1c538-103">_**最終更新日:** 2013-08-12_</span><span class="sxs-lookup"><span data-stu-id="1c538-103">_**Topic Last Modified:** 2013-08-12_</span></span>

<span data-ttu-id="1c538-104">バックエンドサーバーの高可用性を確保するために、同期 SQL ミラーリングまたは SQL クラスタリングのいずれかを使用できます。</span><span class="sxs-lookup"><span data-stu-id="1c538-104">To ensure high availability for your Back End Servers, you can use either synchronous SQL mirroring or SQL clustering.</span></span> <span data-ttu-id="1c538-105">これらのソリューションのいずれかをオプションで使用しますが、組織のビジネス継続性を維持することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="1c538-105">Using one of these solutions optional, but is recommended to maintain your organization's business continuity.</span></span> <span data-ttu-id="1c538-106">Lync Server 2013 では、バックエンドサーバーの高可用性を実現するために、非同期 SQL ミラーリングはサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="1c538-106">Asynchronous SQL mirroring is not supported for Back End Server high availability in Lync Server 2013.</span></span> <span data-ttu-id="1c538-107">このドキュメントの残りの部分では、特に明示的に指定されていない限り、SQL ミラーリングが同期 SQL ミラーリングを意味します。</span><span class="sxs-lookup"><span data-stu-id="1c538-107">In the rest of this document, SQL mirroring means synchronous SQL mirroring, unless otherwise explicitly stated.</span></span>

<span data-ttu-id="1c538-108">トポロジビルダーを使用して、簡単に SQL ミラーリングを設定することができます。</span><span class="sxs-lookup"><span data-stu-id="1c538-108">You can easily set up SQL mirroring with Topology Builder.</span></span> <span data-ttu-id="1c538-109">SQL フェールオーバー クラスタリングの場合、設定に SQL Server を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="1c538-109">For SQL failover clustering, you must use SQL Server for setup.</span></span>

<span data-ttu-id="1c538-110">障害回復用の別のフロントエンドプールとペアリングされているプールで SQL ミラーリングまたは SQL クラスタリングを使用している場合は、両方のプールで同じバックエンドの高可用性ソリューションを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="1c538-110">If you use either SQL mirroring or SQL clustering in a pool which is paired with another Front End pool for disaster recovery, you should use the same Back End high availability solution in both pools.</span></span> <span data-ttu-id="1c538-111">SQL クラスタリングを使用しているプールと SQL ミラーリングを使用してプールをペアリングしないでください。</span><span class="sxs-lookup"><span data-stu-id="1c538-111">You should not pair a pool using SQL mirroring with a pool using SQL clustering.</span></span>

<span data-ttu-id="1c538-112">SQL ミラーリングを展開すると、プール内のすべての Lync Server データベースが、このプールに配置されている場合は、中央管理ストア、応答グループのアプリケーションデータベース、およびコールパークアプリケーションデータベース (これらのアプリケーションの場合) を含めてミラーリングされます。はプール内で実行されています。</span><span class="sxs-lookup"><span data-stu-id="1c538-112">When you deploy SQL mirroring, all Lync Server databases in the pool are mirrored, including the Central Management store, if it is located in this pool, as well as the Response Group application database and the Call Park application database, if those applications are running in the pool.</span></span>

<span data-ttu-id="1c538-113">SQL ミラーリングでは、サーバーで共有記憶域を使用する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="1c538-113">With SQL mirroring, you do not need to use shared storage for the servers.</span></span> <span data-ttu-id="1c538-114">各サーバーは、データベースのコピーをローカル ストレージに保持します。</span><span class="sxs-lookup"><span data-stu-id="1c538-114">Each server keeps its copy of the databases in local storage.</span></span>

<span data-ttu-id="1c538-115">SQL のミラーリングは、監視を使用するかどうかにかかわらず展開することができます。</span><span class="sxs-lookup"><span data-stu-id="1c538-115">You may choose to deploy SQL mirroring with or without a witness.</span></span> <span data-ttu-id="1c538-116">バックエンド サーバーのフェールオーバーが自動的になるので、監視を使用することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="1c538-116">We recommend using a witness because it enables failover of the Back End Server to be automatic.</span></span> <span data-ttu-id="1c538-117">使用しない場合は、管理者が手動でフェールオーバーを実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="1c538-117">Otherwise, an administrator must manually invoke failover.</span></span> <span data-ttu-id="1c538-118">監視を展開した場合でも、管理者は必要に応じてバックエンド サーバーのフェールオーバーを手動で開始できます。</span><span class="sxs-lookup"><span data-stu-id="1c538-118">Note that even if a witness is deployed, an administrator can manually invoke Back End Server failover, if necessary.</span></span>

<span data-ttu-id="1c538-p106">監視を使用する場合は、バックエンド サーバーの複数のペアに対して 1 つの監視を使用できます。監視とバックエンド サーバーのペアを 1 対 1 で対応させる必要はありません。ただし、バックエンド サーバーの複数のペアに対して 1 つの監視を使用する展開は、ペアごとに異なる監視を使用するトポロジほど復元性が高くありません。</span><span class="sxs-lookup"><span data-stu-id="1c538-p106">If you use a witness, you can use a single witness for multiple pairs of Back End Servers. There is no strict 1:1 correspondence between witnesses and pairs of Back End Servers. Deployments that use a single witness for multiple pairs of Back End Servers are not quite as resilient as topologies with a separate witness for each Back End Server pair.</span></span>

<span data-ttu-id="1c538-122">SQL クラスタリングのサポートについて詳しくは、「 [Lync Server 2013 でのデータベースソフトウェアのサポート](lync-server-2013-database-software-support.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="1c538-122">For more information about SQL clustering support, see [Database software support in Lync Server 2013](lync-server-2013-database-software-support.md).</span></span> <span data-ttu-id="1c538-123">SQL クラスタリングの展開の詳細については、「 [Lync server 2013 用に Sql Server クラスタリングを構成する](lync-server-2013-configure-sql-server-clustering.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1c538-123">For details on deploying SQL clustering, see [Configure SQL Server clustering for Lync Server 2013](lync-server-2013-configure-sql-server-clustering.md).</span></span>

<div>

## <a name="recovery-time-for-automatic-back-end-server-failover-with-sql-mirroring"></a><span data-ttu-id="1c538-124">SQL ミラーリングでの自動バックエンドサーバーフェールオーバーの回復時間</span><span class="sxs-lookup"><span data-stu-id="1c538-124">Recovery Time for Automatic Back End Server Failover with SQL Mirroring</span></span>

<span data-ttu-id="1c538-125">SQL ミラーリングを使用した自動バックエンドフェールオーバーの場合は、rpo (目標復旧時間) のエンジニアリングターゲット (RTO) は5分です。</span><span class="sxs-lookup"><span data-stu-id="1c538-125">For automatic Back End failover with SQL mirroring, the engineering target for recovery time objective (RTO) is 5 minutes.</span></span> <span data-ttu-id="1c538-126">同期 SQL ミラーリングのため、フロントエンドサーバーとバックエンドサーバーの両方が同時に停止し、サーバー間でデータが移動されている場合を除き、バックエンドサーバーでデータ損失が発生することはありません。</span><span class="sxs-lookup"><span data-stu-id="1c538-126">Because of the synchronous SQL mirroring, we do not anticipate data loss during Back End Server failures except in rare occasions when both the Front End Servers and the Back End Server go down simultaneously while data is being moved between the servers.</span></span> <span data-ttu-id="1c538-127">目標復旧ポイント (RPO) のエンジニアリング目標は 5 分です。</span><span class="sxs-lookup"><span data-stu-id="1c538-127">The engineering target for recovery point objective (RPO) is 5 minutes.</span></span>

</div>

<div>

## <a name="user-experience-during-back-end-server-failure-with-sql-mirroring"></a><span data-ttu-id="1c538-128">SQL ミラーリングでバックエンドサーバー障害が発生したときのユーザーエクスペリエンス</span><span class="sxs-lookup"><span data-stu-id="1c538-128">User Experience During Back End Server Failure with SQL Mirroring</span></span>

<span data-ttu-id="1c538-129">障害の間のユーザー エクスペリエンスは、障害の性質とトポロジによって異なります。</span><span class="sxs-lookup"><span data-stu-id="1c538-129">User experience during a failure depends on the nature of the failure, and on your topology.</span></span>

<span data-ttu-id="1c538-130">SQL ミラーリングを使用し、監視を構成している場合、プリンシパルが失敗すると、バックエンドサーバーのフェールオーバーは自動的に行われます。</span><span class="sxs-lookup"><span data-stu-id="1c538-130">If you use SQL mirroring and have a witness configured, and the principal fails, Back End Server failover happens automatically and quickly.</span></span> <span data-ttu-id="1c538-131">アクティブ ユーザーがセッションで大きな中断を感じることはありません。</span><span class="sxs-lookup"><span data-stu-id="1c538-131">Active users should not notice much interruption to their ongoing sessions.</span></span>

<span data-ttu-id="1c538-132">ミラーリング監視が構成されていない場合は、管理者が手動でフェールオーバーを呼び出すまでに少し時間がかかります。</span><span class="sxs-lookup"><span data-stu-id="1c538-132">If there is no witness configured, it will take some time for the administrator to manually invoke the failover.</span></span> <span data-ttu-id="1c538-133">その間、アクティブなユーザーが影響を受ける可能性があります。</span><span class="sxs-lookup"><span data-stu-id="1c538-133">During that time, active users may be affected.</span></span> <span data-ttu-id="1c538-134">残りのセッションは約30分間は通常どおりに続行されます。</span><span class="sxs-lookup"><span data-stu-id="1c538-134">They will continue their sessions as normal for about 30 minutes.</span></span> <span data-ttu-id="1c538-135">それでもプライマリが復元されない場合、または管理者がバックアップにフェールオーバーしていない場合、ユーザーは回復可能モードに切り替わります。つまり、Lync Server に対する永続的な変更を必要とするタスク (連絡先の追加など) を実行することはできません。</span><span class="sxs-lookup"><span data-stu-id="1c538-135">If the primary is still not restored, or an administrator has not failed over to the backup, then users are switched to Resiliency mode, meaning that they are unable to perform tasks that require a persistent change on Lync Server (such as adding a contact).</span></span>

<span data-ttu-id="1c538-p111">プリンシパルとミラーの両方のバックエンド サーバーで障害が発生した場合、またはどちらかのサーバーと監視で障害が発生した場合は、(プリンシパルがまだ動作していても) バックエンド サーバーは使用できなくなります。この場合、アクティブ ユーザーはしばらくしてから復元モードに切り替えられます。</span><span class="sxs-lookup"><span data-stu-id="1c538-p111">If both the principal and the mirror Back End Servers fail, or if one of those servers and the witness fails, the Back End Server will become unavailable (even if it is the principal that is still working). In this case, active users are switched to Resiliency mode after some time.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

