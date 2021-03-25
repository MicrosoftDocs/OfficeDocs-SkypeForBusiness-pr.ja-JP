---
title: Skype for Business Server でのバック エンド サーバーの高可用性
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: c559aacb-4e1d-4e78-9582-41f966ad418d
description: AlwaysOn 可用性グループ、AlwaysOn フェールオーバー クラスター インスタンス、データベース ミラーリング、および SQL フェールオーバー クラスタリングなど、Skype for Business Server でサポートされるバック エンド サーバーの高可用性オプションについて説明します。
ms.openlocfilehash: 31ec37d898bd1f04c07142de1849928656f3238e
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51119376"
---
# <a name="back-end-server-high-availability-in-skype-for-business-server"></a><span data-ttu-id="b3e50-103">Skype for Business Server でのバック エンド サーバーの高可用性</span><span class="sxs-lookup"><span data-stu-id="b3e50-103">Back End Server high availability in Skype for Business Server</span></span>
 
<span data-ttu-id="b3e50-104">AlwaysOn 可用性グループ、AlwaysOn フェールオーバー クラスター インスタンス、データベース ミラーリング、および SQL フェールオーバー クラスタリングなど、Skype for Business Server でサポートされるバック エンド サーバーの高可用性オプションについて説明します。</span><span class="sxs-lookup"><span data-stu-id="b3e50-104">Learn about the Back End Server high availability options supported in Skype for Business Server, including AlwaysOn Availability Groups, AlwaysOn Failover Cluster Instances, database mirroring, and SQL failover clustering.</span></span>
  
<span data-ttu-id="b3e50-105">バック エンド サーバーの高可用性を強化するには、次の 4 つのオプションがあります。</span><span class="sxs-lookup"><span data-stu-id="b3e50-105">To enhance high availability for your Back End Servers, you have four options:</span></span>
  
- <span data-ttu-id="b3e50-106">データベース ミラーリング</span><span class="sxs-lookup"><span data-stu-id="b3e50-106">Database mirroring</span></span>
    
- <span data-ttu-id="b3e50-107">AlwaysOn 可用性グループ</span><span class="sxs-lookup"><span data-stu-id="b3e50-107">AlwaysOn Availability Groups</span></span>
    
- <span data-ttu-id="b3e50-108">AlwaysOn フェールオーバー クラスター インスタンス (FCI)</span><span class="sxs-lookup"><span data-stu-id="b3e50-108">AlwaysOn Failover Cluster Instances (FCI)</span></span>
    
- <span data-ttu-id="b3e50-109">SQLフェールオーバー クラスタリング</span><span class="sxs-lookup"><span data-stu-id="b3e50-109">SQL failover clustering</span></span>
    
<span data-ttu-id="b3e50-110">これらのソリューションのいずれかを使用する方法はオプションですが、組織のビジネス継続性を維持するためにお勧めします。</span><span class="sxs-lookup"><span data-stu-id="b3e50-110">Using one of these solutions is optional, but is recommended to maintain your organization's business continuity.</span></span> <span data-ttu-id="b3e50-111">それ以外の場合、単一のデータベース サーバーがダウンすると、Skype for Business Server の重要なデータが失われる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="b3e50-111">Otherwise, having a single database server go down could cause the loss of significant Skype for Business Server data.</span></span> 
  
<span data-ttu-id="b3e50-112">トポロジ ビルダーのみを使用してデータベース ミラーリングを設定できます。</span><span class="sxs-lookup"><span data-stu-id="b3e50-112">You can set up database mirroring using only Topology Builder.</span></span> <span data-ttu-id="b3e50-113">AlwaysOn 可用性グループ、AlwaysOn フェールオーバー クラスター インスタンス、または SQL フェールオーバー クラスタリングの場合は、SQL Server を使用して高可用性ソリューションを作成し、トポロジ ビルダーを使用してフロントエンド プールに関連付けられます。</span><span class="sxs-lookup"><span data-stu-id="b3e50-113">For AlwaysOn Availability Groups, AlwaysOn Failover Cluster Instances,or SQL failover clustering, you use SQL Server to create the high availability solution, then you can use Topology Builder to associate it with a Front End pool.</span></span>
  
<span data-ttu-id="b3e50-114">障害復旧のために別のフロントエンド プールとペアにされているフロントエンド プールでバック エンド サーバーの高可用性を使用する場合は、両方のプールで同じバック エンド 高可用性ソリューションを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b3e50-114">If you use Back End Server high availability on a Front End pool that is paired with another Front End pool for disaster recovery, you should use the same Back End high availability solution in both pools.</span></span> 
  
## <a name="database-mirroring"></a><span data-ttu-id="b3e50-115">データベース ミラーリング</span><span class="sxs-lookup"><span data-stu-id="b3e50-115">Database mirroring</span></span>

<span data-ttu-id="b3e50-116">Skype for Business Server では、次のデータベース ソフトウェアを使用したミラーリングがサポートされています。</span><span class="sxs-lookup"><span data-stu-id="b3e50-116">Skype for Business Server supports mirroring with the following database software:</span></span>
  
- <span data-ttu-id="b3e50-117">SQL Server 2019、Enterprise Edition と Standard Edition の両方</span><span class="sxs-lookup"><span data-stu-id="b3e50-117">SQL Server 2019, both Enterprise Edition and Standard Edition</span></span>

- <span data-ttu-id="b3e50-118">SQL Server 2017、Enterprise Edition と Standard Edition の両方</span><span class="sxs-lookup"><span data-stu-id="b3e50-118">SQL Server 2017, both Enterprise Edition and Standard Edition</span></span>

- <span data-ttu-id="b3e50-119">SQL Server 2016、Enterprise Edition と Standard Edition の両方</span><span class="sxs-lookup"><span data-stu-id="b3e50-119">SQL Server 2016, both Enterprise Edition and Standard Edition</span></span>

- <span data-ttu-id="b3e50-120">SQL Server 2014、Enterprise Edition と Standard Edition の両方</span><span class="sxs-lookup"><span data-stu-id="b3e50-120">SQL Server 2014, both Enterprise Edition and Standard Edition</span></span>
    
- <span data-ttu-id="b3e50-121">SQL Server 2012 SP2 と CU2(Enterprise Edition と Standard Edition の両方)</span><span class="sxs-lookup"><span data-stu-id="b3e50-121">SQL Server 2012 SP2 and CU2, both Enterprise Edition and Standard Edition</span></span>
    

> [!NOTE]
> <span data-ttu-id="b3e50-122">SQLミラーリングは Skype for Business Server 2015 で使用できますが、Skype for Business Server 2019 ではサポートされなくなりました。</span><span class="sxs-lookup"><span data-stu-id="b3e50-122">SQL Mirroring is available in Skype for Business Server 2015 but is no longer supported in Skype for Business Server 2019.</span></span> <span data-ttu-id="b3e50-123">AlwaysOn 可用性グループ、AlwaysOn フェールオーバー クラスター インスタンス (FCI)、および SQL フェールオーバー クラスタリング方法は、Skype for Business Server 2019 でサポートされる唯一のオプションです。</span><span class="sxs-lookup"><span data-stu-id="b3e50-123">The AlwaysOn Availability Groups, AlwaysOn Failover Cluster Instances (FCI), and SQL failover clustering methods are the only supported options with Skype for Business Server 2019.</span></span>
    
<span data-ttu-id="b3e50-124">Skype for Business Server のバック エンド サーバーの高可用性では、非同期データベース ミラーリングはサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="b3e50-124">Asynchronous database mirroring is not supported for Back End Server high availability in Skype for Business Server.</span></span> <span data-ttu-id="b3e50-125">このドキュメントの残りの部分では、データベース ミラーリングとは、特に明示的に指定されていない限り、同期データベース ミラーリングを意味します。</span><span class="sxs-lookup"><span data-stu-id="b3e50-125">In the rest of this document, database mirroring means synchronous database mirroring, unless otherwise explicitly stated.</span></span> 
  
<span data-ttu-id="b3e50-126">フロントエンド プールにデータベース ミラーリングを展開すると、プール内のすべての Skype for Business Server データベース (このプールに配置されている場合は、サーバーの全体管理ストアを含む) と、応答グループ アプリケーション データベースとコール パーク アプリケーション データベース (それらのアプリケーションがプールで実行されている場合) がミラーリングされます。</span><span class="sxs-lookup"><span data-stu-id="b3e50-126">When you deploy database mirroring in a Front End pool, all Skype for Business Server databases in the pool are mirrored, including the Central Management store, if it is located in this pool, as well as the Response Group application database and the Call Park application database, if those applications are running in the pool.</span></span> 
  
<span data-ttu-id="b3e50-127">データベース ミラーリングでは、サーバーに共有ストレージを使用する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="b3e50-127">With database mirroring, you do not need to use shared storage for the servers.</span></span> <span data-ttu-id="b3e50-128">各サーバーは、データベースのコピーをローカル ストレージに保持しします。</span><span class="sxs-lookup"><span data-stu-id="b3e50-128">Each server keeps its copy of the databases in local storage.</span></span> 
  
<span data-ttu-id="b3e50-129">ミラーリング監視を使用する場合と使用しない場合は、データベース ミラーリングを展開できます。</span><span class="sxs-lookup"><span data-stu-id="b3e50-129">You may choose to deploy database mirroring with or without a witness.</span></span> <span data-ttu-id="b3e50-130">バックエンド サーバーのフェールオーバーが自動的になるので、監視を使用することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="b3e50-130">We recommend using a witness because it enables failover of the Back End Server to be automatic.</span></span> <span data-ttu-id="b3e50-131">使用しない場合は、管理者が手動でフェールオーバーを実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b3e50-131">Otherwise, an administrator must manually invoke failover.</span></span> <span data-ttu-id="b3e50-132">監視を展開した場合でも、管理者は必要に応じてバックエンド サーバーのフェールオーバーを手動で開始できます。</span><span class="sxs-lookup"><span data-stu-id="b3e50-132">Note that even if a witness is deployed, an administrator can manually invoke Back End Server failover, if necessary.</span></span>
  
<span data-ttu-id="b3e50-p107">監視を使用する場合は、バックエンド サーバーの複数のペアに対して 1 つの監視を使用できます。監視とバックエンド サーバーのペアを 1 対 1 で対応させる必要はありません。ただし、バックエンド サーバーの複数のペアに対して 1 つの監視を使用する展開は、ペアごとに異なる監視を使用するトポロジほど復元性が高くありません。</span><span class="sxs-lookup"><span data-stu-id="b3e50-p107">If you use a witness, you can use a single witness for multiple pairs of Back End Servers. There is no strict 1:1 correspondence between witnesses and pairs of Back End Servers. Deployments that use a single witness for multiple pairs of Back End Servers are not quite as resilient as topologies with a separate witness for each Back End Server pair.</span></span> 
  
### <a name="guidelines-for-planning-back-end-server-mirroring"></a><span data-ttu-id="b3e50-136">バック エンド サーバーミラーリングの計画に関するガイドライン</span><span class="sxs-lookup"><span data-stu-id="b3e50-136">Guidelines for planning Back End Server mirroring</span></span>

<span data-ttu-id="b3e50-137">一般に、2 つのバックエンド サーバー間での SQL ミラーリングを設定するには、以下の要件を満たしている必要があります。</span><span class="sxs-lookup"><span data-stu-id="b3e50-137">In general, setting up SQL mirroring between the two Back End Servers with a witness requires the following:</span></span>
  
- <span data-ttu-id="b3e50-138">プライマリ サーバーのバージョンのサーバーは、SQL ServerミラーリングをSQL必要があります。</span><span class="sxs-lookup"><span data-stu-id="b3e50-138">The primary server's version of SQL Server must support SQL mirroring.</span></span>
    
- <span data-ttu-id="b3e50-139">プライマリ、ミラー、およびミラーリング監視 (展開されている場合) の各 SQL Server が同一バージョンである。</span><span class="sxs-lookup"><span data-stu-id="b3e50-139">The primary, mirror, and the witness (if deployed) must have the same version of SQL Server.</span></span> 
    
- <span data-ttu-id="b3e50-p108">プライマリおよびミラーの各 SQL Server が同一エディションである (ミラーリング監視のエディションは異なっていても構いません)。</span><span class="sxs-lookup"><span data-stu-id="b3e50-p108">The primary and the mirror must have the same edition of SQL Server. The witness may have a different edition.</span></span>
    
<span data-ttu-id="b3e50-142">監視SQLでサポートされているSQLのベスト プラクティスについては、MSDN ライブラリの  [「データベース](/sql/database-engine/database-mirroring/database-mirroring-witness) ミラーリング監視」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b3e50-142">For SQL best practices in terms of what SQL versions are supported for a Witness role, see  ["Database Mirroring Witness"](/sql/database-engine/database-mirroring/database-mirroring-witness) in the MSDN Library.</span></span>
  
<span data-ttu-id="b3e50-143">サーバー ミラーリングを構成する前に、まずデータベースのアクセス許可をSQL設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b3e50-143">Before configuring server mirroring, you must first set up SQL database permissions correctly.</span></span> <span data-ttu-id="b3e50-144">詳細については、「データベース ミラーリングまたは AlwaysOn 可用性グループのログイン アカウントを設定  [する (SQL Server)」を参照してください](/sql/database-engine/database-mirroring/set-up-login-accounts-database-mirroring-always-on-availability)。</span><span class="sxs-lookup"><span data-stu-id="b3e50-144">For details, see  ["Set Up Login Accounts for Database Mirroring or AlwaysOn Availability Groups (SQL Server)"](/sql/database-engine/database-mirroring/set-up-login-accounts-database-mirroring-always-on-availability).</span></span>
  
<span data-ttu-id="b3e50-p110">SQL ミラーリングでは、データベース復旧モードは常に [**完全**] に設定されます。これは、トランザクション ログ サイズを綿密に監視し、トランザクション ログを定期的にバックアップしてバックエンド サーバー上のディスク容量の不足を回避する必要があることを意味します。トランザクション ログのバックアップ頻度は、ログの増加率によって決まります。ログの増加率は、フロントエンド プールのユーザー アクティビティによるデータベース トランザクションによって決まります。Lync 展開ワークロードに対して予想されるトランザクション ログの増加を判断し、それに応じて計画することをお勧めします。次の記事では、SQL バックアップおよびログ管理に関する追加情報を提供しています。</span><span class="sxs-lookup"><span data-stu-id="b3e50-p110">With SQL mirroring, database recovery mode is always set to **Full**, which means you must closely monitor transaction log size and back up transaction logs on a regular basis to avoid running out of disk space on the Back End Servers. The frequency of transaction log backups depends on the log growth rate, which in turn depends on database transactions incurred by user activities on the Front End pool. We recommend that you determine how much transaction log growth is expected for your Lync deployment workload so that you can do the planning accordingly. The following articles provide additional information on SQL backup and log management:</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="b3e50-149">トポロジ ビルダーまたはコマンドレットを使用して SQL ミラーリングをセットアップおよび削除すると、プライマリ サーバー、ミラー サーバー、監視サーバー (必要な場合) サーバーすべてが同じドメインに属している場合にのみサポートされます。</span><span class="sxs-lookup"><span data-stu-id="b3e50-149">Using Topology Builder or cmdlets to set up and remove SQL mirroring is supported only when the primary, mirror, and witness (if desired) servers all belong to the same domain.</span></span> <span data-ttu-id="b3e50-150">異なるドメインのサーバーに SQL ミラーリングを設定する場合は、SQL Server のドキュメントを参照してください。</span><span class="sxs-lookup"><span data-stu-id="b3e50-150">If you want to set up SQL mirroring among servers in different domains, see your SQL Server documentation.</span></span> 

> [!NOTE]
> <span data-ttu-id="b3e50-151">SQLミラーリングは Skype for Business Server 2015 で使用できますが、Skype for Business Server 2019 ではサポートされなくなりました。</span><span class="sxs-lookup"><span data-stu-id="b3e50-151">SQL Mirroring is available in Skype for Business Server 2015 but is no longer supported in Skype for Business Server 2019.</span></span> <span data-ttu-id="b3e50-152">AlwaysOn 可用性グループ、AlwaysOn フェールオーバー クラスター インスタンス (FCI)、および SQL フェールオーバー クラスタリング方法は、Skype for Business Server 2019 で優先されます。</span><span class="sxs-lookup"><span data-stu-id="b3e50-152">The  AlwaysOn Availability Groups, AlwaysOn Failover Cluster Instances (FCI), and SQL failover clustering methods are preferred with Skype for Business Server 2019.</span></span>
  
### <a name="recovery-time-for-automatic-back-end-server-failover-with-database-mirroring"></a><span data-ttu-id="b3e50-153">データベース ミラーリングによるバック エンド サーバーの自動フェールオーバーの復旧時間</span><span class="sxs-lookup"><span data-stu-id="b3e50-153">Recovery time for automatic Back End Server failover with database mirroring</span></span>

<span data-ttu-id="b3e50-154">データベース ミラーリングによるバック エンドの自動フェールオーバーの場合、目標復旧時間 (RTO) のエンジニアリング 目標は 5 分です。</span><span class="sxs-lookup"><span data-stu-id="b3e50-154">For automatic Back End failover with database mirroring, the engineering target for recovery time objective (RTO) is 5 minutes.</span></span> <span data-ttu-id="b3e50-155">同期データベース ミラーリングのため、バック エンド サーバーの障害時のデータ損失は予測されませんが、フロントエンド サーバーとバック エンド サーバーの両方が同時にダウンし、データがサーバー間で移動される場合を除きます。</span><span class="sxs-lookup"><span data-stu-id="b3e50-155">Because of the synchronous database mirroring, we do not anticipate data loss during Back End Server failures except in rare occasions when both the Front End Servers and the Back End Server go down simultaneously while data is being moved between the servers.</span></span> <span data-ttu-id="b3e50-156">目標復旧ポイント (RPO) のエンジニアリング目標は 5 分です。</span><span class="sxs-lookup"><span data-stu-id="b3e50-156">The engineering target for recovery point objective (RPO) is 5 minutes.</span></span>
  
### <a name="user-experience-during-back-end-server-failure-with-database-mirroring"></a><span data-ttu-id="b3e50-157">データベース ミラーリングを使用したバック エンド サーバーの障害時のユーザー エクスペリエンス</span><span class="sxs-lookup"><span data-stu-id="b3e50-157">User experience during Back End Server failure with database mirroring</span></span>

<span data-ttu-id="b3e50-158">障害の間のユーザー エクスペリエンスは、障害の特徴とトポロジによって異なります。</span><span class="sxs-lookup"><span data-stu-id="b3e50-158">User experience during a failure depends on the nature of the failure, and on your topology.</span></span>
  
<span data-ttu-id="b3e50-159">データベース ミラーリングを使用してミラーリング監視を構成し、プリンシパルが失敗した場合、バック エンド サーバーのフェールオーバーは自動的かつ迅速に行われます。</span><span class="sxs-lookup"><span data-stu-id="b3e50-159">If you use database mirroring and have a witness configured, and the principal fails, Back End Server failover happens automatically and quickly.</span></span> <span data-ttu-id="b3e50-160">使用中のユーザーがセッションで大きな中断を感じることはありません。</span><span class="sxs-lookup"><span data-stu-id="b3e50-160">Active users should not notice much interruption to their ongoing sessions.</span></span>
  
<span data-ttu-id="b3e50-161">監視が構成されていない場合、管理者が手動でフェールオーバーを呼び出すのに時間がかかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="b3e50-161">If there is no witness configured, it will take some time for the administrator to manually invoke the failover.</span></span> <span data-ttu-id="b3e50-162">その間、アクティブなユーザーが影響を受ける可能性があります。</span><span class="sxs-lookup"><span data-stu-id="b3e50-162">During that time, active users may be affected.</span></span> <span data-ttu-id="b3e50-163">セッションは通常通り約 30 分間継続します。</span><span class="sxs-lookup"><span data-stu-id="b3e50-163">They will continue their sessions as normal for about 30 minutes.</span></span> <span data-ttu-id="b3e50-164">プライマリがまだ復元されていない場合、または管理者がバックアップに失敗していない場合、ユーザーは復元モードに切り替わります。つまり、Lync Server で永続的な変更が必要なタスク (連絡先の追加など) を実行できません。</span><span class="sxs-lookup"><span data-stu-id="b3e50-164">If the primary is still not restored, or an administrator has not failed over to the backup, then users are switched to Resiliency mode, meaning that they are unable to perform tasks that require a persistent change on Lync Server (such as adding a contact).</span></span>
  
<span data-ttu-id="b3e50-p116">プリンシパルとミラーの両方のバックエンド サーバーで障害が発生した場合、またはどちらかのサーバーと監視で障害が発生した場合は、バックエンド サーバーは使用できなくなります (プリンシパルがまだ動作していたとしても)。この場合、使用中のユーザーはしばらくしてから復元モードに切り替えられます。</span><span class="sxs-lookup"><span data-stu-id="b3e50-p116">If both the principal and the mirror Back End Servers fail, or if one of those servers and the witness fails, the Back End Server will become unavailable (even if it is the principal that is still working). In this case, active users are switched to Resiliency mode after some time.</span></span>
  
## <a name="alwayson-availability-groups-and-alwayson-failover-cluster-instances"></a><span data-ttu-id="b3e50-167">AlwaysOn 可用性グループと AlwaysOn フェールオーバー クラスター インスタンス</span><span class="sxs-lookup"><span data-stu-id="b3e50-167">AlwaysOn Availability Groups and AlwaysOn Failover Cluster Instances</span></span>

<span data-ttu-id="b3e50-168">Skype for Business Server は AlwaysOn 可用性グループのみをアクティブ/パッシブとしてサポートし、アクティブ/アクティブはサポートしません。</span><span class="sxs-lookup"><span data-stu-id="b3e50-168">Skype for Business Server supports AlwaysOn Availability Groups only as active/passive, not active/active.</span></span> 
  
<span data-ttu-id="b3e50-169">AlwaysOn 可用性グループまたは AlwaysOn フェールオーバー クラスター インスタンスを使用するには、SQL Serverを使用して高可用性ソリューションをセットアップおよび構成します。</span><span class="sxs-lookup"><span data-stu-id="b3e50-169">To use AlwaysOn Availability Groups or AlwaysOn Failover Cluster Instances, you first use SQL Server to set up and configure the high availability solution.</span></span> <span data-ttu-id="b3e50-170">その後、トポロジ ビルダーを使用して、フロントエンド プールに関連付けできます。</span><span class="sxs-lookup"><span data-stu-id="b3e50-170">You can then use Topology Builder to associate it with a Front End pool.</span></span>

<span data-ttu-id="b3e50-171">Skype for Business Server は、次のデータベース ソフトウェアを使用して AlwaysOn をサポートします。</span><span class="sxs-lookup"><span data-stu-id="b3e50-171">Skype for Business Server supports AlwaysOn with the following database software:</span></span>

- <span data-ttu-id="b3e50-172">SQL Server 2019 Enterprise Edition</span><span class="sxs-lookup"><span data-stu-id="b3e50-172">SQL Server 2019 Enterprise Edition</span></span>

- <span data-ttu-id="b3e50-173">SQL Server 2019 Standard Edition の制限事項については、以下の注を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b3e50-173">SQL Server 2019 Standard Edition with limitations, see note below</span></span>

- <span data-ttu-id="b3e50-174">SQL Server 2017 Enterprise Edition</span><span class="sxs-lookup"><span data-stu-id="b3e50-174">SQL Server 2017 Enterprise Edition</span></span>

- <span data-ttu-id="b3e50-175">SQL Server 2017 Standard Edition の制限事項については、以下の注を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b3e50-175">SQL Server 2017 Standard Edition with limitations, see note below</span></span>

- <span data-ttu-id="b3e50-176">SQL Server 2016 Enterprise Edition</span><span class="sxs-lookup"><span data-stu-id="b3e50-176">SQL Server 2016 Enterprise Edition</span></span>

- <span data-ttu-id="b3e50-177">SQL Server 2016 Standard Edition の制限事項については、以下の注を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b3e50-177">SQL Server 2016 Standard Edition with limitations, see note below</span></span>

- <span data-ttu-id="b3e50-178">SQL Server 2014 Enterprise Edition</span><span class="sxs-lookup"><span data-stu-id="b3e50-178">SQL Server 2014 Enterprise Edition</span></span>
    
- <span data-ttu-id="b3e50-179">SQL Server 2012 SP2 および CU2 Enterprise Edition</span><span class="sxs-lookup"><span data-stu-id="b3e50-179">SQL Server 2012 SP2 and CU2 Enterprise Edition</span></span>

> [!NOTE]
> <span data-ttu-id="b3e50-180">SQL Server 2019、2017、および 2016 は、Skype for Business Server 2019 でサポートされている唯一のバージョンです。</span><span class="sxs-lookup"><span data-stu-id="b3e50-180">SQL Server 2019, 2017, and 2016 are the only versions supported by Skype for Business Server 2019.</span></span>

> [!NOTE]
> <span data-ttu-id="b3e50-181">Always On 可用性 **グループは** 、SQL 2016、2017、および 2019 Standard Edition ではサポートされていませんが、Always On フェールオーバー クラスター インスタンスを使用できます。</span><span class="sxs-lookup"><span data-stu-id="b3e50-181">Always On Availability Groups is **not** supported in SQL 2016, 2017, and 2019 Standard Editions but you can use Always On Failover Cluster Instances.</span></span> <span data-ttu-id="b3e50-182">詳細 [については、「Editions and supported features of SQL Server 2016」](/sql/sql-server/editions-and-components-of-sql-server-2016?view=sql-server-2017) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b3e50-182">See [Editions and supported features of SQL Server 2016](/sql/sql-server/editions-and-components-of-sql-server-2016?view=sql-server-2017) to learn more.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="b3e50-183">複数の AlwaysOn 可用性グループ インスタンスのインスタンス名は同じである必要があります。</span><span class="sxs-lookup"><span data-stu-id="b3e50-183">Instance names for multiple AlwaysOn Availability Group instances must be the same.</span></span> 
  
<span data-ttu-id="b3e50-184">AlwaysOn 可用性グループを展開する手順については、「Skype for Business Server のバック エンド サーバーに AlwaysOn 可用性グループを展開 [する」を参照してください](../../deploy/deploy-high-availability-and-disaster-recovery/alwayson-availability-group.md)。</span><span class="sxs-lookup"><span data-stu-id="b3e50-184">For steps for deploying AlwaysOn Availability Groups, see [Deploy an AlwaysOn Availability Group on a Back End Server in Skype for Business Server](../../deploy/deploy-high-availability-and-disaster-recovery/alwayson-availability-group.md).</span></span>
  
## <a name="sql-server-failover-clustering"></a><span data-ttu-id="b3e50-185">SQL Server フェールオーバー クラスタリング</span><span class="sxs-lookup"><span data-stu-id="b3e50-185">SQL Server Failover Clustering</span></span>

<span data-ttu-id="b3e50-186">Skype for Business Server では、次SQL Serverのデータベース ソフトウェアを使用してフェールオーバー クラスタリングを実行できます。</span><span class="sxs-lookup"><span data-stu-id="b3e50-186">Skype for Business Server supports SQL Server failover clustering with the following database software:</span></span>
  
- <span data-ttu-id="b3e50-187">SQL Server 2019、Enterprise Edition と Standard Edition の両方</span><span class="sxs-lookup"><span data-stu-id="b3e50-187">SQL Server 2019, both Enterprise Edition and Standard Edition</span></span>

- <span data-ttu-id="b3e50-188">SQL Server 2017、Enterprise Edition と Standard Edition の両方</span><span class="sxs-lookup"><span data-stu-id="b3e50-188">SQL Server 2017, both Enterprise Edition and Standard Edition</span></span>

- <span data-ttu-id="b3e50-189">SQL Server 2016、Enterprise Edition と Standard Edition の両方</span><span class="sxs-lookup"><span data-stu-id="b3e50-189">SQL Server 2016, both Enterprise Edition and Standard Edition</span></span>

- <span data-ttu-id="b3e50-190">SQL Server 2014、Enterprise Edition と Standard Edition の両方</span><span class="sxs-lookup"><span data-stu-id="b3e50-190">SQL Server 2014, both Enterprise Edition and Standard Edition</span></span>
    
- <span data-ttu-id="b3e50-191">SQL Server 2012 SP2 と CU2(Enterprise Edition と Standard Edition の両方)</span><span class="sxs-lookup"><span data-stu-id="b3e50-191">SQL Server 2012 SP2 and CU2, both Enterprise Edition and Standard Edition</span></span>

<span data-ttu-id="b3e50-192">フェールオーバー クラスタリングSQLするには、まずフロントエンド プールを展開する前に、SQL Serverクラスターをセットアップして構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b3e50-192">To use SQL failover clustering, you should first set up and configure the SQL Server cluster before deploying your Front End pool.</span></span> <span data-ttu-id="b3e50-193">2012 年のフェールオーバー クラスタリングのベスト プラクティスとセットアップ手順については、「SQL Server」を参照してください [https://technet.microsoft.com/library/hh231721.aspx](/sql/sql-server/failover-clusters/install/sql-server-failover-cluster-installation) 。</span><span class="sxs-lookup"><span data-stu-id="b3e50-193">For best practices and setup instructions for failover clustering in SQL Server 2012, see [https://technet.microsoft.com/library/hh231721.aspx](/sql/sql-server/failover-clusters/install/sql-server-failover-cluster-installation).</span></span>

> [!NOTE]
> <span data-ttu-id="b3e50-194">SQL Server 2019、2017、および SQL Server 2016 は、Skype for Business Server 2019 でサポートされている唯一のバージョンです。</span><span class="sxs-lookup"><span data-stu-id="b3e50-194">SQL Server 2019, 2017, and SQL Server 2016 are the only versions supported by Skype for Business Server 2019.</span></span>
    
<span data-ttu-id="b3e50-195">フェールオーバー クラスタリングSQLするには、まずフロントエンド プールを展開する前に、SQL Serverクラスターをセットアップして構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b3e50-195">To use SQL failover clustering, you should first set up and configure the SQL Server cluster before deploying your Front End pool.</span></span> <span data-ttu-id="b3e50-196">2014 年と 2016 年のフェールオーバー クラスタリングのベスト プラクティスとセットアップ手順については、「SQL Server 2016」を参照してください [https://technet.microsoft.com/library/hh231721.aspx](/sql/sql-server/failover-clusters/install/sql-server-failover-cluster-installation) 。</span><span class="sxs-lookup"><span data-stu-id="b3e50-196">For best practices and setup instructions for failover clustering in SQL Server 2014 and 2016, see [https://technet.microsoft.com/library/hh231721.aspx](/sql/sql-server/failover-clusters/install/sql-server-failover-cluster-installation).</span></span> <span data-ttu-id="b3e50-197">2008 年のフェールオーバー クラスタリングSQL Serverを参照してください [https://technet.microsoft.com/library/ms189134(v=sql.105).aspx](/previous-versions/sql/sql-server-2008-r2/ms189134(v=sql.105)) 。</span><span class="sxs-lookup"><span data-stu-id="b3e50-197">For failover clustering in SQL Server 2008, see [https://technet.microsoft.com/library/ms189134(v=sql.105).aspx](/previous-versions/sql/sql-server-2008-r2/ms189134(v=sql.105)).</span></span>
  
<span data-ttu-id="b3e50-198">SQL Server をインストールする際には、データベースの場所とログ ファイルの場所を管理するための SQL Server Management Studio をインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="b3e50-198">When you install SQL Server, you should install SQL Server Management Studio to manage the locations for database and log file locations.</span></span> <span data-ttu-id="b3e50-199">SQL Server Management Studio は、SQL Server のインストール時にオプションのコンポーネントとしてインストールされます。</span><span class="sxs-lookup"><span data-stu-id="b3e50-199">SQL Server Management Studio is installed as an optional component when you install SQL Server.</span></span>
