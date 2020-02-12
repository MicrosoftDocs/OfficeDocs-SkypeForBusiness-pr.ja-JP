---
title: Skype for Business Server のバックエンドサーバーの高可用性
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: c559aacb-4e1d-4e78-9582-41f966ad418d
description: AlwaysOn 可用性グループ、AlwaysOn フェールオーバークラスターインスタンス、データベースのミラーリング、SQL フェールオーバークラスタリングなど、Skype for Business Server でサポートされているバックエンドサーバーの高可用性オプションについて説明します。
ms.openlocfilehash: 4c814e525b3a1d0900e7162255ec4d7e86d79605
ms.sourcegitcommit: 1a08ec9069332e19135312d35fc6a6c3247ce2d2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/11/2020
ms.locfileid: "41888616"
---
# <a name="back-end-server-high-availability-in-skype-for-business-server"></a><span data-ttu-id="e97de-103">Skype for Business Server のバックエンドサーバーの高可用性</span><span class="sxs-lookup"><span data-stu-id="e97de-103">Back End Server high availability in Skype for Business Server</span></span>
 
<span data-ttu-id="e97de-104">AlwaysOn 可用性グループ、AlwaysOn フェールオーバークラスターインスタンス、データベースのミラーリング、SQL フェールオーバークラスタリングなど、Skype for Business Server でサポートされているバックエンドサーバーの高可用性オプションについて説明します。</span><span class="sxs-lookup"><span data-stu-id="e97de-104">Learn about the Back End Server high availability options supported in Skype for Business Server, including AlwaysOn Availability Groups, AlwaysOn Failover Cluster Instances, database mirroring, and SQL failover clustering.</span></span>
  
<span data-ttu-id="e97de-105">バックエンド サーバーの高可用性を強化するには、以下の 4 つの選択肢があります。</span><span class="sxs-lookup"><span data-stu-id="e97de-105">To enhance high availability for your Back End Servers, you have four options:</span></span>
  
- <span data-ttu-id="e97de-106">データベース ミラーリング</span><span class="sxs-lookup"><span data-stu-id="e97de-106">Database mirroring</span></span>
    
- <span data-ttu-id="e97de-107">AlwaysOn 可用性グループ</span><span class="sxs-lookup"><span data-stu-id="e97de-107">AlwaysOn Availability Groups</span></span>
    
- <span data-ttu-id="e97de-108">AlwaysOn フェールオーバークラスターインスタンス (FCI)</span><span class="sxs-lookup"><span data-stu-id="e97de-108">AlwaysOn Failover Cluster Instances (FCI)</span></span>
    
- <span data-ttu-id="e97de-109">SQL フェールオーバー クラスタリング</span><span class="sxs-lookup"><span data-stu-id="e97de-109">SQL failover clustering</span></span>
    
<span data-ttu-id="e97de-110">これらのソリューションのいずれかの使用はオプションですが、組織のビジネス継続性を維持するには推奨されます。</span><span class="sxs-lookup"><span data-stu-id="e97de-110">Using one of these solutions is optional, but is recommended to maintain your organization's business continuity.</span></span> <span data-ttu-id="e97de-111">そうしないと、1つのデータベースサーバーがダウンすると、大量の Skype for Business Server データが失われる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="e97de-111">Otherwise, having a single database server go down could cause the loss of significant Skype for Business Server data.</span></span> 
  
<span data-ttu-id="e97de-112">データベースミラーリングは、トポロジビルダーのみを使用して設定できます。</span><span class="sxs-lookup"><span data-stu-id="e97de-112">You can set up database mirroring using only Topology Builder.</span></span> <span data-ttu-id="e97de-113">AlwaysOn 可用性グループ、AlwaysOn フェールオーバークラスターインスタンス、または SQL フェールオーバークラスタリングの場合、SQL Server を使用して高可用性ソリューションを作成した後、トポロジビルダーを使用して、フロントエンドプールに関連付けることができます。</span><span class="sxs-lookup"><span data-stu-id="e97de-113">For AlwaysOn Availability Groups, AlwaysOn Failover Cluster Instances,or SQL failover clustering, you use SQL Server to create the high availability solution, then you can use Topology Builder to associate it with a Front End pool.</span></span>
  
<span data-ttu-id="e97de-114">バックエンドサーバーの高可用性プールで、障害回復用の別のフロントエンドプールとペアリングされている場合は、両方のプールで同じバックエンドの高可用性ソリューションを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e97de-114">If you use Back End Server high availability on a Front End pool that is paired with another Front End pool for disaster recovery, you should use the same Back End high availability solution in both pools.</span></span> 
  
## <a name="database-mirroring"></a><span data-ttu-id="e97de-115">データベース ミラーリング</span><span class="sxs-lookup"><span data-stu-id="e97de-115">Database mirroring</span></span>

<span data-ttu-id="e97de-116">Skype for Business Server は、次のデータベースソフトウェアとのミラーリングをサポートしています。</span><span class="sxs-lookup"><span data-stu-id="e97de-116">Skype for Business Server supports mirroring with the following database software:</span></span>
  
- <span data-ttu-id="e97de-117">SQL Server 2019 (Enterprise Edition と Standard Edition の両方)</span><span class="sxs-lookup"><span data-stu-id="e97de-117">SQL Server 2019, both Enterprise Edition and Standard Edition</span></span>

- <span data-ttu-id="e97de-118">SQL Server 2017 (Enterprise Edition と Standard Edition の両方)</span><span class="sxs-lookup"><span data-stu-id="e97de-118">SQL Server 2017, both Enterprise Edition and Standard Edition</span></span>

- <span data-ttu-id="e97de-119">SQL Server 2016 (Enterprise Edition と Standard Edition の両方)</span><span class="sxs-lookup"><span data-stu-id="e97de-119">SQL Server 2016, both Enterprise Edition and Standard Edition</span></span>

- <span data-ttu-id="e97de-120">SQL Server 2014 (Enterprise Edition と Standard Edition の両方)</span><span class="sxs-lookup"><span data-stu-id="e97de-120">SQL Server 2014, both Enterprise Edition and Standard Edition</span></span>
    
- <span data-ttu-id="e97de-121">SQL Server 2012 SP2 と CU2 (Enterprise Edition と Standard Edition の両方)</span><span class="sxs-lookup"><span data-stu-id="e97de-121">SQL Server 2012 SP2 and CU2, both Enterprise Edition and Standard Edition</span></span>
    

> [!NOTE]
> <span data-ttu-id="e97de-122">SQL ミラーリングは、Skype for Business Server 2015 では使用できますが、Skype for Business Server 2019 ではサポートされなくなりました。</span><span class="sxs-lookup"><span data-stu-id="e97de-122">SQL Mirroring is available in Skype for Business Server 2015 but is no longer supported in Skype for Business Server 2019.</span></span> <span data-ttu-id="e97de-123">AlwaysOn 可用性グループ、AlwaysOn フェールオーバークラスターインスタンス (FCI)、SQL フェールオーバークラスタリングの各方法は、Skype for Business Server 2019 でサポートされている唯一のオプションです。</span><span class="sxs-lookup"><span data-stu-id="e97de-123">The AlwaysOn Availability Groups, AlwaysOn Failover Cluster Instances (FCI), and SQL failover clustering methods are the only supported options with Skype for Business Server 2019.</span></span>
    
<span data-ttu-id="e97de-124">Skype for Business Server では、バックエンドサーバーの高可用性を実現するための非同期データベースミラーリングはサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="e97de-124">Asynchronous database mirroring is not supported for Back End Server high availability in Skype for Business Server.</span></span> <span data-ttu-id="e97de-125">これ以降、特に指定がない限り、データベース ミラーリングは同期データベース ミラーリングを意味するものとします。</span><span class="sxs-lookup"><span data-stu-id="e97de-125">In the rest of this document, database mirroring means synchronous database mirroring, unless otherwise explicitly stated.</span></span> 
  
<span data-ttu-id="e97de-126">フロントエンドプールにデータベースミラーリングを展開すると、プール内のすべての Skype for Business Server データベースが、このプールに配置されている場合は中央管理ストア、応答グループアプリケーションデータベース、コールパークと共にミラーリングされます。アプリがプールで実行されている場合は、アプリケーションデータベース。</span><span class="sxs-lookup"><span data-stu-id="e97de-126">When you deploy database mirroring in a Front End pool, all Skype for Business Server databases in the pool are mirrored, including the Central Management store, if it is located in this pool, as well as the Response Group application database and the Call Park application database, if those applications are running in the pool.</span></span> 
  
<span data-ttu-id="e97de-p105">データベース ミラーリングでは、サーバーに対して共有ストレージを使用する必要はありません。各サーバーは、データベースのコピーをローカル ストレージに保持します。</span><span class="sxs-lookup"><span data-stu-id="e97de-p105">With database mirroring, you do not need to use shared storage for the servers. Each server keeps its copy of the databases in local storage.</span></span> 
  
<span data-ttu-id="e97de-p106">データベース ミラーリングの展開では、監視を使用することも使用しないこともできます。バックエンド サーバーのフェールオーバーが自動的になるので、監視を使用することをお勧めします。使用しない場合は、管理者が手動でフェールオーバーを実行する必要があります。監視を展開した場合でも、管理者は必要に応じてバックエンド サーバーのフェールオーバーを手動で開始できます。</span><span class="sxs-lookup"><span data-stu-id="e97de-p106">You may choose to deploy database mirroring with or without a witness. We recommend using a witness because it enables failover of the Back End Server to be automatic. Otherwise, an administrator must manually invoke failover. Note that even if a witness is deployed, an administrator can manually invoke Back End Server failover, if necessary.</span></span>
  
<span data-ttu-id="e97de-p107">監視を使用する場合は、バックエンド サーバーの複数のペアに対して 1 つの監視を使用できます。監視とバックエンド サーバーのペアを 1 対 1 で対応させる必要はありません。ただし、バックエンド サーバーの複数のペアに対して 1 つの監視を使用する展開は、ペアごとに異なる監視を使用するトポロジほど復元性が高くありません。</span><span class="sxs-lookup"><span data-stu-id="e97de-p107">If you use a witness, you can use a single witness for multiple pairs of Back End Servers. There is no strict 1:1 correspondence between witnesses and pairs of Back End Servers. Deployments that use a single witness for multiple pairs of Back End Servers are not quite as resilient as topologies with a separate witness for each Back End Server pair.</span></span> 
  
### <a name="guidelines-for-planning-back-end-server-mirroring"></a><span data-ttu-id="e97de-136">バックエンド サーバーのミラーリングのガイドライン</span><span class="sxs-lookup"><span data-stu-id="e97de-136">Guidelines for planning Back End Server mirroring</span></span>

<span data-ttu-id="e97de-137">一般に、2 つのバックエンド サーバー間での SQL ミラーリングを設定するには、以下の要件を満たしている必要があります。</span><span class="sxs-lookup"><span data-stu-id="e97de-137">In general, setting up SQL mirroring between the two Back End Servers with a witness requires the following:</span></span>
  
- <span data-ttu-id="e97de-138">プライマリサーバーの SQL Server のバージョンでは、SQL のミラーリングがサポートされている必要があります。</span><span class="sxs-lookup"><span data-stu-id="e97de-138">The primary server's version of SQL Server must support SQL mirroring.</span></span>
    
- <span data-ttu-id="e97de-139">プライマリ、ミラー、およびミラーリング監視 (展開されている場合) の各 SQL Server が同一バージョンである。</span><span class="sxs-lookup"><span data-stu-id="e97de-139">The primary, mirror, and the witness (if deployed) must have the same version of SQL Server.</span></span> 
    
- <span data-ttu-id="e97de-p108">プライマリおよびミラーの各 SQL Server が同一エディションである (ミラーリング監視のエディションは異なっていても構いません)。</span><span class="sxs-lookup"><span data-stu-id="e97de-p108">The primary and the mirror must have the same edition of SQL Server. The witness may have a different edition.</span></span>
    
<span data-ttu-id="e97de-142">監視ロールでサポートされる SQL バージョンについては、SQL のベストプラクティスについては、MSDN ライブラリの[「データベースミラーリングの監視」](https://go.microsoft.com/fwlink/p/?LinkId=247345)をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="e97de-142">For SQL best practices in terms of what SQL versions are supported for a Witness role, see  ["Database Mirroring Witness"](https://go.microsoft.com/fwlink/p/?LinkId=247345) in the MSDN Library.</span></span>
  
<span data-ttu-id="e97de-143">サーバー ミラーリングを構成する前に、まず SQL データベース アクセス許可を正しく設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e97de-143">Before configuring server mirroring, you must first set up SQL database permissions correctly.</span></span> <span data-ttu-id="e97de-144">詳細について[は、「データベースミラーリングまたは AlwaysOn 可用性グループ (SQL Server) のログインアカウントの](https://go.microsoft.com/fwlink/p/?LinkId=268454)セットアップ」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e97de-144">For details, see  ["Set Up Login Accounts for Database Mirroring or AlwaysOn Availability Groups (SQL Server)"](https://go.microsoft.com/fwlink/p/?LinkId=268454).</span></span>
  
<span data-ttu-id="e97de-p110">SQL ミラーリングでは、データベース復旧モードは常に [**完全**] に設定されます。これは、トランザクション ログ サイズを綿密に監視し、トランザクション ログを定期的にバックアップしてバックエンド サーバー上のディスク容量の不足を回避する必要があることを意味します。トランザクション ログのバックアップ頻度は、ログの増加率によって決まります。ログの増加率は、フロントエンド プールのユーザー アクティビティによるデータベース トランザクションによって決まります。Lync 展開ワークロードに対して予想されるトランザクション ログの増加を判断し、それに応じて計画することをお勧めします。次の記事では、SQL バックアップおよびログ管理に関する追加情報を提供しています。</span><span class="sxs-lookup"><span data-stu-id="e97de-p110">With SQL mirroring, database recovery mode is always set to **Full**, which means you must closely monitor transaction log size and back up transaction logs on a regular basis to avoid running out of disk space on the Back End Servers. The frequency of transaction log backups depends on the log growth rate, which in turn depends on database transactions incurred by user activities on the Front End pool. We recommend that you determine how much transaction log growth is expected for your Lync deployment workload so that you can do the planning accordingly. The following articles provide additional information on SQL backup and log management:</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="e97de-149">SQL ミラーリングのセットアップと削除を行うためのトポロジビルダーまたはコマンドレットの使用は、プライマリ、ミラー、および監視 (必要な場合) サーバーがすべて同じドメインに属している場合にのみサポートされます。</span><span class="sxs-lookup"><span data-stu-id="e97de-149">Using Topology Builder or cmdlets to set up and remove SQL mirroring is supported only when the primary, mirror, and witness (if desired) servers all belong to the same domain.</span></span> <span data-ttu-id="e97de-150">異なるドメインのサーバーに SQL ミラーリングを設定する場合は、SQL Server のドキュメントを参照してください。</span><span class="sxs-lookup"><span data-stu-id="e97de-150">If you want to set up SQL mirroring among servers in different domains, see your SQL Server documentation.</span></span> 

> [!NOTE]
> <span data-ttu-id="e97de-151">SQL ミラーリングは、Skype for Business Server 2015 では使用できますが、Skype for Business Server 2019 ではサポートされなくなりました。</span><span class="sxs-lookup"><span data-stu-id="e97de-151">SQL Mirroring is available in Skype for Business Server 2015 but is no longer supported in Skype for Business Server 2019.</span></span> <span data-ttu-id="e97de-152">AlwaysOn 可用性グループ、AlwaysOn フェールオーバークラスターインスタンス (FCI)、SQL フェールオーバークラスタリングの各方法は、Skype for Business Server 2019 で推奨されます。</span><span class="sxs-lookup"><span data-stu-id="e97de-152">The  AlwaysOn Availability Groups, AlwaysOn Failover Cluster Instances (FCI), and SQL failover clustering methods are preferred with Skype for Business Server 2019.</span></span>
  
### <a name="recovery-time-for-automatic-back-end-server-failover-with-database-mirroring"></a><span data-ttu-id="e97de-153">データベース ミラーリングを使用したバックエンド サーバーの自動フェールオーバーの復旧時間</span><span class="sxs-lookup"><span data-stu-id="e97de-153">Recovery time for automatic Back End Server failover with database mirroring</span></span>

<span data-ttu-id="e97de-p113">データベース ミラーリングを使用した自動バックエンド フェールオーバーの場合、目標復旧時間 (RTO) のエンジニアリング目標は 5 分です。同期データベース ミラーリングなので、バックエンド サーバー障害の間にデータ損失が発生する可能性は、サーバー間のデータ移動中にフロント エンド サーバーとバックエンド サーバーの両方が同時にダウンするというまれな状況を除き、ありません。目標復旧ポイント (RPO) のエンジニアリング目標は 5 分です。</span><span class="sxs-lookup"><span data-stu-id="e97de-p113">For automatic Back End failover with database mirroring, the engineering target for recovery time objective (RTO) is 5 minutes. Because of the synchronous database mirroring, we do not anticipate data loss during Back End Server failures except in rare occasions when both the Front End Servers and the Back End Server go down simultaneously while data is being moved between the servers. The engineering target for recovery point objective (RPO) is 5 minutes.</span></span>
  
### <a name="user-experience-during-back-end-server-failure-with-database-mirroring"></a><span data-ttu-id="e97de-157">データベース ミラーリングを使用したバックエンド サーバー障害の間のユーザー エクスペリエンス</span><span class="sxs-lookup"><span data-stu-id="e97de-157">User experience during Back End Server failure with database mirroring</span></span>

<span data-ttu-id="e97de-158">障害の間のユーザー エクスペリエンスは、障害の性質とトポロジによって異なります。</span><span class="sxs-lookup"><span data-stu-id="e97de-158">User experience during a failure depends on the nature of the failure, and on your topology.</span></span>
  
<span data-ttu-id="e97de-p114">監視を構成してあり、プリンシパルで障害が発生した場合は、データベース ミラーリングを使用したバックエンド サーバーのフェールオーバーは自動的かつ迅速に行われます。アクティブ ユーザーがセッションで大きな中断を感じることはありません。</span><span class="sxs-lookup"><span data-stu-id="e97de-p114">If you use database mirroring and have a witness configured, and the principal fails, Back End Server failover happens automatically and quickly. Active users should not notice much interruption to their ongoing sessions.</span></span>
  
<span data-ttu-id="e97de-161">ミラーリング監視が構成されていない場合は、管理者が手動でフェールオーバーを呼び出すまでに少し時間がかかります。</span><span class="sxs-lookup"><span data-stu-id="e97de-161">If there is no witness configured, it will take some time for the administrator to manually invoke the failover.</span></span> <span data-ttu-id="e97de-162">その間、アクティブなユーザーが影響を受ける可能性があります。</span><span class="sxs-lookup"><span data-stu-id="e97de-162">During that time, active users may be affected.</span></span> <span data-ttu-id="e97de-163">残りのセッションは約30分間は通常どおりに続行されます。</span><span class="sxs-lookup"><span data-stu-id="e97de-163">They will continue their sessions as normal for about 30 minutes.</span></span> <span data-ttu-id="e97de-164">それでもプライマリが復元されない場合、または管理者がバックアップにフェールオーバーしていない場合、ユーザーは回復可能モードに切り替わります。つまり、Lync Server に対する永続的な変更を必要とするタスク (連絡先の追加など) を実行することはできません。</span><span class="sxs-lookup"><span data-stu-id="e97de-164">If the primary is still not restored, or an administrator has not failed over to the backup, then users are switched to Resiliency mode, meaning that they are unable to perform tasks that require a persistent change on Lync Server (such as adding a contact).</span></span>
  
<span data-ttu-id="e97de-p116">プリンシパルとミラーの両方のバックエンド サーバーで障害が発生した場合、またはどちらかのサーバーと監視で障害が発生した場合は、(プリンシパルがまだ動作していても) バックエンド サーバーは使用できなくなります。この場合、アクティブ ユーザーはしばらくしてから復元モードに切り替えられます。</span><span class="sxs-lookup"><span data-stu-id="e97de-p116">If both the principal and the mirror Back End Servers fail, or if one of those servers and the witness fails, the Back End Server will become unavailable (even if it is the principal that is still working). In this case, active users are switched to Resiliency mode after some time.</span></span>
  
## <a name="alwayson-availability-groups-and-alwayson-failover-cluster-instances"></a><span data-ttu-id="e97de-167">AlwaysOn 可用性グループと AlwaysOn フェールオーバー クラスター インスタンス</span><span class="sxs-lookup"><span data-stu-id="e97de-167">AlwaysOn Availability Groups and AlwaysOn Failover Cluster Instances</span></span>

<span data-ttu-id="e97de-168">Skype for Business Server は、アクティブ/パッシブとしてのみ、AlwaysOn 可用性グループをサポートします。アクティブ/アクティブにはなりません。</span><span class="sxs-lookup"><span data-stu-id="e97de-168">Skype for Business Server supports AlwaysOn Availability Groups only as active/passive, not active/active.</span></span> 
  
<span data-ttu-id="e97de-169">AlwaysOn 可用性グループまたは AlwaysOn フェールオーバークラスターインスタンスを使用するには、最初に SQL Server を使用して高可用性ソリューションをセットアップし、構成します。</span><span class="sxs-lookup"><span data-stu-id="e97de-169">To use AlwaysOn Availability Groups or AlwaysOn Failover Cluster Instances, you first use SQL Server to set up and configure the high availability solution.</span></span> <span data-ttu-id="e97de-170">次に、トポロジビルダーを使用して、フロントエンドプールに関連付けます。</span><span class="sxs-lookup"><span data-stu-id="e97de-170">You can then use Topology Builder to associate it with a Front End pool.</span></span>

<span data-ttu-id="e97de-171">Skype for Business Server は、次のデータベースソフトウェアを使用して AlwaysOn をサポートしています。</span><span class="sxs-lookup"><span data-stu-id="e97de-171">Skype for Business Server supports AlwaysOn with the following database software:</span></span>

- <span data-ttu-id="e97de-172">SQL Server 2019 Enterprise Edition</span><span class="sxs-lookup"><span data-stu-id="e97de-172">SQL Server 2019 Enterprise Edition</span></span>

- <span data-ttu-id="e97de-173">SQL Server 2019 Standard Edition の制限事項については、以下の注を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e97de-173">SQL Server 2019 Standard Edition with limitations, see note below</span></span>

- <span data-ttu-id="e97de-174">SQL Server 2017 Enterprise Edition</span><span class="sxs-lookup"><span data-stu-id="e97de-174">SQL Server 2017 Enterprise Edition</span></span>

- <span data-ttu-id="e97de-175">SQL Server 2017 Standard Edition の制限事項については、以下の注を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e97de-175">SQL Server 2017 Standard Edition with limitations, see note below</span></span>

- <span data-ttu-id="e97de-176">SQL Server 2016 Enterprise Edition</span><span class="sxs-lookup"><span data-stu-id="e97de-176">SQL Server 2016 Enterprise Edition</span></span>

- <span data-ttu-id="e97de-177">SQL Server 2016 Standard Edition の制限事項については、以下の注を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e97de-177">SQL Server 2016 Standard Edition with limitations, see note below</span></span>

- <span data-ttu-id="e97de-178">SQL Server 2014 Enterprise Edition</span><span class="sxs-lookup"><span data-stu-id="e97de-178">SQL Server 2014 Enterprise Edition</span></span>
    
- <span data-ttu-id="e97de-179">SQL Server 2012 SP2 と CU2 Enterprise Edition</span><span class="sxs-lookup"><span data-stu-id="e97de-179">SQL Server 2012 SP2 and CU2 Enterprise Edition</span></span>

> [!NOTE]
> <span data-ttu-id="e97de-180">SQL Server 2019、2017、2016は、Skype for Business Server 2019 でサポートされている唯一のバージョンです。</span><span class="sxs-lookup"><span data-stu-id="e97de-180">SQL Server 2019, 2017, and 2016 are the only versions supported by Skype for Business Server 2019.</span></span>

> [!NOTE]
> <span data-ttu-id="e97de-181">Always On 可用性グループは、SQL 2016、2017、2019標準エディションではサポートされ**ません**が、フェールオーバークラスターインスタンスでは常に使用できます。</span><span class="sxs-lookup"><span data-stu-id="e97de-181">Always On Availability Groups is **not** supported in SQL 2016, 2017, and 2019 Standard Editions but you can use Always On Failover Cluster Instances.</span></span> <span data-ttu-id="e97de-182">詳細については[、「SQL Server 2016 の各エディションとサポートされる機能](https://docs.microsoft.com/sql/sql-server/editions-and-components-of-sql-server-2016?view=sql-server-2017)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e97de-182">See [Editions and supported features of SQL Server 2016](https://docs.microsoft.com/sql/sql-server/editions-and-components-of-sql-server-2016?view=sql-server-2017) to learn more.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="e97de-183">複数の AlwaysOn 可用性グループインスタンスのインスタンス名は同じである必要があります。</span><span class="sxs-lookup"><span data-stu-id="e97de-183">Instance names for multiple AlwaysOn Availability Group instances must be the same.</span></span> 
  
<span data-ttu-id="e97de-184">AlwaysOn 可用性グループを展開する手順については、「 [Skype For Business Server のバックエンドサーバーに Alwayson 可用性グループを展開](../../deploy/deploy-high-availability-and-disaster-recovery/alwayson-availability-group.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e97de-184">For steps for deploying AlwaysOn Availability Groups, see [Deploy an AlwaysOn Availability Group on a Back End Server in Skype for Business Server](../../deploy/deploy-high-availability-and-disaster-recovery/alwayson-availability-group.md).</span></span>
  
## <a name="sql-server-failover-clustering"></a><span data-ttu-id="e97de-185">SQL Server フェールオーバー クラスタリング</span><span class="sxs-lookup"><span data-stu-id="e97de-185">SQL Server Failover Clustering</span></span>

<span data-ttu-id="e97de-186">Skype for Business Server は、次のデータベースソフトウェアで SQL Server フェールオーバークラスタリングをサポートしています。</span><span class="sxs-lookup"><span data-stu-id="e97de-186">Skype for Business Server supports SQL Server failover clustering with the following database software:</span></span>
  
- <span data-ttu-id="e97de-187">SQL Server 2019 (Enterprise Edition と Standard Edition の両方)</span><span class="sxs-lookup"><span data-stu-id="e97de-187">SQL Server 2019, both Enterprise Edition and Standard Edition</span></span>

- <span data-ttu-id="e97de-188">SQL Server 2017 (Enterprise Edition と Standard Edition の両方)</span><span class="sxs-lookup"><span data-stu-id="e97de-188">SQL Server 2017, both Enterprise Edition and Standard Edition</span></span>

- <span data-ttu-id="e97de-189">SQL Server 2016 (Enterprise Edition と Standard Edition の両方)</span><span class="sxs-lookup"><span data-stu-id="e97de-189">SQL Server 2016, both Enterprise Edition and Standard Edition</span></span>

- <span data-ttu-id="e97de-190">SQL Server 2014 (Enterprise Edition と Standard Edition の両方)</span><span class="sxs-lookup"><span data-stu-id="e97de-190">SQL Server 2014, both Enterprise Edition and Standard Edition</span></span>
    
- <span data-ttu-id="e97de-191">SQL Server 2012 SP2 と CU2 (Enterprise Edition と Standard Edition の両方)</span><span class="sxs-lookup"><span data-stu-id="e97de-191">SQL Server 2012 SP2 and CU2, both Enterprise Edition and Standard Edition</span></span>

<span data-ttu-id="e97de-192">SQL フェールオーバークラスタリングを使用するには、まず、フロントエンドプールを展開する前に SQL Server クラスターをセットアップして構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e97de-192">To use SQL failover clustering, you should first set up and configure the SQL Server cluster before deploying your Front End pool.</span></span> <span data-ttu-id="e97de-193">SQL Server 2012 のフェールオーバークラスタリングのベストプラクティスとセットアップ手順につい[https://technet.microsoft.com/library/hh231721.aspx](https://technet.microsoft.com/library/hh231721.aspx)ては、を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e97de-193">For best practices and setup instructions for failover clustering in SQL Server 2012, see [https://technet.microsoft.com/library/hh231721.aspx](https://technet.microsoft.com/library/hh231721.aspx).</span></span>

> [!NOTE]
> <span data-ttu-id="e97de-194">SQL Server 2019、2017、SQL Server 2016 は、Skype for Business Server 2019 でサポートされているバージョンのみです。</span><span class="sxs-lookup"><span data-stu-id="e97de-194">SQL Server 2019, 2017, and SQL Server 2016 are the only versions supported by Skype for Business Server 2019.</span></span>
    
<span data-ttu-id="e97de-195">SQL フェールオーバークラスタリングを使用するには、まず、フロントエンドプールを展開する前に SQL Server クラスターをセットアップして構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e97de-195">To use SQL failover clustering, you should first set up and configure the SQL Server cluster before deploying your Front End pool.</span></span> <span data-ttu-id="e97de-196">SQL Server 2014 および2016のフェールオーバークラスタリングのベストプラクティスとセットアップ手順につい[https://technet.microsoft.com/library/hh231721.aspx](https://technet.microsoft.com/library/hh231721.aspx)ては、を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e97de-196">For best practices and setup instructions for failover clustering in SQL Server 2014 and 2016, see [https://technet.microsoft.com/library/hh231721.aspx](https://technet.microsoft.com/library/hh231721.aspx).</span></span> <span data-ttu-id="e97de-197">SQL Server 2008 のフェールオーバークラスタリングについ[https://technet.microsoft.com/library/ms189134(v=sql.105).aspx](https://technet.microsoft.com/library/ms189134%28v=sql.105%29.aspx)ては、を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e97de-197">For failover clustering in SQL Server 2008, see [https://technet.microsoft.com/library/ms189134(v=sql.105).aspx](https://technet.microsoft.com/library/ms189134%28v=sql.105%29.aspx).</span></span>
  
<span data-ttu-id="e97de-p121">SQL Server をインストールする際は、SQL Server Management Studio をインストールしてデータベースとログ ファイルの場所を管理する必要があります。SQL Server Management Studio は、SQL Server のインストール時にオプション コンポーネントとしてインストールされます。</span><span class="sxs-lookup"><span data-stu-id="e97de-p121">When you install SQL Server, you should install SQL Server Management Studio to manage the locations for database and log file locations. SQL Server Management Studio is installed as an optional component when you install SQL Server.</span></span>
  
