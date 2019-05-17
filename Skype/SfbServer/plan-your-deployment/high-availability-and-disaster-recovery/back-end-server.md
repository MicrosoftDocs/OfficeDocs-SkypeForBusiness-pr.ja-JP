---
title: Skype の最後のサーバーの高可用性をビジネスのサーバーのバックアップします。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: c559aacb-4e1d-4e78-9582-41f966ad418d
description: ビジネス サーバーには、AlwaysOn 可用性グループ、AlwaysOn フェールオーバー クラスター インスタンス、データベース ミラーリング、SQL のフェールオーバー クラスタ リングなど、Skype でサポートされているバック エンド サーバーの高可用性オプションについて説明します。
ms.openlocfilehash: c200596ac43099d92b7fd37e850a524cf92a24ce
ms.sourcegitcommit: ee05fe02fe68b5bd6ee38dd4a3ad69da3d37c492
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/17/2019
ms.locfileid: "34106300"
---
# <a name="back-end-server-high-availability-in-skype-for-business-server"></a><span data-ttu-id="02e32-103">Skype の最後のサーバーの高可用性をビジネスのサーバーのバックアップします。</span><span class="sxs-lookup"><span data-stu-id="02e32-103">Back End Server high availability in Skype for Business Server</span></span>
 
<span data-ttu-id="02e32-104">ビジネス サーバーには、AlwaysOn 可用性グループ、AlwaysOn フェールオーバー クラスター インスタンス、データベース ミラーリング、SQL のフェールオーバー クラスタ リングなど、Skype でサポートされているバック エンド サーバーの高可用性オプションについて説明します。</span><span class="sxs-lookup"><span data-stu-id="02e32-104">Learn about the Back End Server high availability options supported in Skype for Business Server, including AlwaysOn Availability Groups, AlwaysOn Failover Cluster Instances, database mirroring, and SQL failover clustering.</span></span>
  
<span data-ttu-id="02e32-105">バックエンド サーバーの高可用性を強化するには、以下の 4 つの選択肢があります。</span><span class="sxs-lookup"><span data-stu-id="02e32-105">To enhance high availability for your Back End Servers, you have four options:</span></span>
  
- <span data-ttu-id="02e32-106">データベース ミラーリング</span><span class="sxs-lookup"><span data-stu-id="02e32-106">Database mirroring</span></span>
    
- <span data-ttu-id="02e32-107">AlwaysOn 可用性グループ</span><span class="sxs-lookup"><span data-stu-id="02e32-107">AlwaysOn Availability Groups</span></span>
    
- <span data-ttu-id="02e32-108">AlwaysOn フェールオーバー クラスターのインスタンス (FCI)</span><span class="sxs-lookup"><span data-stu-id="02e32-108">AlwaysOn Failover Cluster Instances (FCI)</span></span>
    
- <span data-ttu-id="02e32-109">SQL フェールオーバー クラスタリング</span><span class="sxs-lookup"><span data-stu-id="02e32-109">SQL failover clustering</span></span>
    
<span data-ttu-id="02e32-110">これらのソリューションのいずれかの使用はオプションですが、組織のビジネス継続性を維持するには推奨されます。</span><span class="sxs-lookup"><span data-stu-id="02e32-110">Using one of these solutions is optional, but is recommended to maintain your organization's business continuity.</span></span> <span data-ttu-id="02e32-111">それ以外の場合、1 つのデータベース サーバーがダウンすることでしたがビジネスのサーバーのデータの重要な Skype の失われる。</span><span class="sxs-lookup"><span data-stu-id="02e32-111">Otherwise, having a single database server go down could cause the loss of significant Skype for Business Server data.</span></span> 
  
<span data-ttu-id="02e32-112">トポロジ ビルダーだけを使用してデータベースのミラーリングを設定できます。</span><span class="sxs-lookup"><span data-stu-id="02e32-112">You can set up database mirroring using only Topology Builder.</span></span> <span data-ttu-id="02e32-113">AlwaysOn 可用性グループ、AlwaysOn フェールオーバー クラスター インスタンス、または SQL のフェールオーバー クラスタ リングでは、SQL Server を使用して、高可用性ソリューションを作成するし、トポロジ ビルダーを使用するには、フロント エンド プールに関連付けることにします。</span><span class="sxs-lookup"><span data-stu-id="02e32-113">For AlwaysOn Availability Groups, AlwaysOn Failover Cluster Instances,or SQL failover clustering, you use SQL Server to create the high availability solution, then you can use Topology Builder to associate it with a Front End pool.</span></span>
  
<span data-ttu-id="02e32-114">災害復旧のための別のフロント エンド プールとフロント エンド プールのバック エンド サーバーの高可用性を使用する場合は、両方のプールに同じバックエンドの高可用性ソリューションを使用してください。</span><span class="sxs-lookup"><span data-stu-id="02e32-114">If you use Back End Server high availability on a Front End pool that is paired with another Front End pool for disaster recovery, you should use the same Back End high availability solution in both pools.</span></span> 
  
## <a name="database-mirroring"></a><span data-ttu-id="02e32-115">データベース ミラーリング</span><span class="sxs-lookup"><span data-stu-id="02e32-115">Database mirroring</span></span>

<span data-ttu-id="02e32-116">ビジネス サーバーの Skype では、次のデータベース ソフトウェアでミラーリングがサポートされています。</span><span class="sxs-lookup"><span data-stu-id="02e32-116">Skype for Business Server supports mirroring with the following database software:</span></span>
  
- <span data-ttu-id="02e32-117">SQL Server Enterprise Edition と Standard Edition の両方の 2017</span><span class="sxs-lookup"><span data-stu-id="02e32-117">SQL Server 2017, both Enterprise Edition and Standard Edition</span></span>

- <span data-ttu-id="02e32-118">SQL Server Enterprise Edition と Standard Edition の両方の 2016</span><span class="sxs-lookup"><span data-stu-id="02e32-118">SQL Server 2016, both Enterprise Edition and Standard Edition</span></span>

- <span data-ttu-id="02e32-119">SQL Server Enterprise Edition と Standard Edition の両方の 2014</span><span class="sxs-lookup"><span data-stu-id="02e32-119">SQL Server 2014, both Enterprise Edition and Standard Edition</span></span>
    
- <span data-ttu-id="02e32-120">SQL Server 2012 の SP2 には、CU2、Enterprise Edition と Standard Edition の両方</span><span class="sxs-lookup"><span data-stu-id="02e32-120">SQL Server 2012 SP2 and CU2, both Enterprise Edition and Standard Edition</span></span>
    

> [!NOTE]
> <span data-ttu-id="02e32-121">SQL ミラーリング ビジネス サーバー 2015 の Skype で利用できるが、ビジネス サーバー 2019 の Skype でサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="02e32-121">SQL Mirroring is available in Skype for Business Server 2015 but is no longer supported in Skype for Business Server 2019.</span></span> <span data-ttu-id="02e32-122">AlwaysOn 可用性グループ、AlwaysOn フェールオーバー クラスター インスタンス (FCI)、および SQL フェールオーバー クラスタ リング手法は、ビジネス サーバー 2019 の Skype で優先します。</span><span class="sxs-lookup"><span data-stu-id="02e32-122">The  AlwaysOn Availability Groups, AlwaysOn Failover Cluster Instances (FCI), and SQL failover clustering methods are preferred with Skype for Business Server 2019.</span></span>
    
<span data-ttu-id="02e32-123">非同期データベース ミラーリングは Skype のバック エンド サーバーの高可用性のビジネス サーバーです。</span><span class="sxs-lookup"><span data-stu-id="02e32-123">Asynchronous database mirroring is not supported for Back End Server high availability in Skype for Business Server.</span></span> <span data-ttu-id="02e32-124">これ以降、特に指定がない限り、データベース ミラーリングは同期データベース ミラーリングを意味するものとします。</span><span class="sxs-lookup"><span data-stu-id="02e32-124">In the rest of this document, database mirroring means synchronous database mirroring, unless otherwise explicitly stated.</span></span> 
  
<span data-ttu-id="02e32-125">フロント エンド プールのデータベース ミラーリング機能を配置する場合、プール内のビジネス サーバー データベースのすべての Skype は、ミラーリング、このプールと同様に、応答グループ アプリケーション データベースと、コール パーク内にある場合、中央管理ストアを含むアプリケーション ・ データベースでは、それらのアプリケーションは、プールで実行している場合。</span><span class="sxs-lookup"><span data-stu-id="02e32-125">When you deploy database mirroring in a Front End pool, all Skype for Business Server databases in the pool are mirrored, including the Central Management store, if it is located in this pool, as well as the Response Group application database and the Call Park application database, if those applications are running in the pool.</span></span> 
  
<span data-ttu-id="02e32-p105">データベース ミラーリングでは、サーバーに対して共有ストレージを使用する必要はありません。各サーバーは、データベースのコピーをローカル ストレージに保持します。</span><span class="sxs-lookup"><span data-stu-id="02e32-p105">With database mirroring, you do not need to use shared storage for the servers. Each server keeps its copy of the databases in local storage.</span></span> 
  
<span data-ttu-id="02e32-p106">データベース ミラーリングの展開では、監視を使用することも使用しないこともできます。バックエンド サーバーのフェールオーバーが自動的になるので、監視を使用することをお勧めします。使用しない場合は、管理者が手動でフェールオーバーを実行する必要があります。監視を展開した場合でも、管理者は必要に応じてバックエンド サーバーのフェールオーバーを手動で開始できます。</span><span class="sxs-lookup"><span data-stu-id="02e32-p106">You may choose to deploy database mirroring with or without a witness. We recommend using a witness because it enables failover of the Back End Server to be automatic. Otherwise, an administrator must manually invoke failover. Note that even if a witness is deployed, an administrator can manually invoke Back End Server failover, if necessary.</span></span>
  
<span data-ttu-id="02e32-p107">監視を使用する場合は、バックエンド サーバーの複数のペアに対して 1 つの監視を使用できます。監視とバックエンド サーバーのペアを 1 対 1 で対応させる必要はありません。ただし、バックエンド サーバーの複数のペアに対して 1 つの監視を使用する展開は、ペアごとに異なる監視を使用するトポロジほど復元性が高くありません。</span><span class="sxs-lookup"><span data-stu-id="02e32-p107">If you use a witness, you can use a single witness for multiple pairs of Back End Servers. There is no strict 1:1 correspondence between witnesses and pairs of Back End Servers. Deployments that use a single witness for multiple pairs of Back End Servers are not quite as resilient as topologies with a separate witness for each Back End Server pair.</span></span> 
  
### <a name="guidelines-for-planning-back-end-server-mirroring"></a><span data-ttu-id="02e32-135">バックエンド サーバーのミラーリングのガイドライン</span><span class="sxs-lookup"><span data-stu-id="02e32-135">Guidelines for planning Back End Server mirroring</span></span>

<span data-ttu-id="02e32-136">一般に、2 つのバックエンド サーバー間での SQL ミラーリングを設定するには、以下の要件を満たしている必要があります。</span><span class="sxs-lookup"><span data-stu-id="02e32-136">In general, setting up SQL mirroring between the two Back End Servers with a witness requires the following:</span></span>
  
- <span data-ttu-id="02e32-137">SQL Server のプライマリ サーバーのバージョンでは、SQL のミラーリングをサポートする必要があります。</span><span class="sxs-lookup"><span data-stu-id="02e32-137">The primary server's version of SQL Server must support SQL mirroring.</span></span>
    
- <span data-ttu-id="02e32-138">プライマリ、ミラー、およびミラーリング監視 (展開されている場合) の各 SQL Server が同一バージョンである。</span><span class="sxs-lookup"><span data-stu-id="02e32-138">The primary, mirror, and the witness (if deployed) must have the same version of SQL Server.</span></span> 
    
- <span data-ttu-id="02e32-p108">プライマリおよびミラーの各 SQL Server が同一エディションである (ミラーリング監視のエディションは異なっていても構いません)。</span><span class="sxs-lookup"><span data-stu-id="02e32-p108">The primary and the mirror must have the same edition of SQL Server. The witness may have a different edition.</span></span>
    
<span data-ttu-id="02e32-141">ミラーリング監視ロールのどのような SQL のバージョンはサポートされているという点で SQL のベスト プラクティスは、MSDN ライブラリの[「データベース ミラーリングの監視」](https://go.microsoft.com/fwlink/p/?LinkId=247345)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="02e32-141">For SQL best practices in terms of what SQL versions are supported for a Witness role, see  ["Database Mirroring Witness"](https://go.microsoft.com/fwlink/p/?LinkId=247345) in the MSDN Library.</span></span>
  
<span data-ttu-id="02e32-142">サーバー ミラーリングを構成する前に、まず SQL データベース アクセス許可を正しく設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="02e32-142">Before configuring server mirroring, you must first set up SQL database permissions correctly.</span></span> <span data-ttu-id="02e32-143">詳細については、 [「データベース ミラーリングまたは AlwaysOn 可用性グループ (SQL Server) のログイン アカウントの設定」](https://go.microsoft.com/fwlink/p/?LinkId=268454)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="02e32-143">For details, see  ["Set Up Login Accounts for Database Mirroring or AlwaysOn Availability Groups (SQL Server)"](https://go.microsoft.com/fwlink/p/?LinkId=268454).</span></span>
  
<span data-ttu-id="02e32-p110">SQL ミラーリングでは、データベース復旧モードは常に [**完全**] に設定されます。これは、トランザクション ログ サイズを綿密に監視し、トランザクション ログを定期的にバックアップしてバックエンド サーバー上のディスク容量の不足を回避する必要があることを意味します。トランザクション ログのバックアップ頻度は、ログの増加率によって決まります。ログの増加率は、フロントエンド プールのユーザー アクティビティによるデータベース トランザクションによって決まります。Lync 展開ワークロードに対して予想されるトランザクション ログの増加を判断し、それに応じて計画することをお勧めします。次の記事では、SQL バックアップおよびログ管理に関する追加情報を提供しています。</span><span class="sxs-lookup"><span data-stu-id="02e32-p110">With SQL mirroring, database recovery mode is always set to **Full**, which means you must closely monitor transaction log size and back up transaction logs on a regular basis to avoid running out of disk space on the Back End Servers. The frequency of transaction log backups depends on the log growth rate, which in turn depends on database transactions incurred by user activities on the Front End pool. We recommend that you determine how much transaction log growth is expected for your Lync deployment workload so that you can do the planning accordingly. The following articles provide additional information on SQL backup and log management:</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="02e32-148">設定し、SQL を削除するのにはトポロジ ビルダーまたはコマンドレットを使用してミラーリングがサポートされているプライマリ、ミラー、および (必要な場合)、ミラーリング監視サーバーが同じドメインに属している場合にのみです。</span><span class="sxs-lookup"><span data-stu-id="02e32-148">Using Topology Builder or cmdlets to set up and remove SQL mirroring is supported only when the primary, mirror, and witness (if desired) servers all belong to the same domain.</span></span> <span data-ttu-id="02e32-149">異なるドメインのサーバーに SQL ミラーリングを設定する場合は、SQL Server のドキュメントを参照してください。</span><span class="sxs-lookup"><span data-stu-id="02e32-149">If you want to set up SQL mirroring among servers in different domains, see your SQL Server documentation.</span></span> 

> [!NOTE]
> <span data-ttu-id="02e32-150">SQL ミラーリング ビジネス サーバー 2015 の Skype で利用できるが、ビジネス サーバー 2019 の Skype でサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="02e32-150">SQL Mirroring is available in Skype for Business Server 2015 but is no longer supported in Skype for Business Server 2019.</span></span> <span data-ttu-id="02e32-151">AlwaysOn 可用性グループ、AlwaysOn フェールオーバー クラスター インスタンス (FCI)、および SQL フェールオーバー クラスタ リング手法は、ビジネス サーバー 2019 の Skype で優先します。</span><span class="sxs-lookup"><span data-stu-id="02e32-151">The  AlwaysOn Availability Groups, AlwaysOn Failover Cluster Instances (FCI), and SQL failover clustering methods are preferred with Skype for Business Server 2019.</span></span>
  
### <a name="recovery-time-for-automatic-back-end-server-failover-with-database-mirroring"></a><span data-ttu-id="02e32-152">データベース ミラーリングを使用したバックエンド サーバーの自動フェールオーバーの復旧時間</span><span class="sxs-lookup"><span data-stu-id="02e32-152">Recovery time for automatic Back End Server failover with database mirroring</span></span>

<span data-ttu-id="02e32-p113">データベース ミラーリングを使用した自動バックエンド フェールオーバーの場合、目標復旧時間 (RTO) のエンジニアリング目標は 5 分です。同期データベース ミラーリングなので、バックエンド サーバー障害の間にデータ損失が発生する可能性は、サーバー間のデータ移動中にフロント エンド サーバーとバックエンド サーバーの両方が同時にダウンするというまれな状況を除き、ありません。目標復旧ポイント (RPO) のエンジニアリング目標は 5 分です。</span><span class="sxs-lookup"><span data-stu-id="02e32-p113">For automatic Back End failover with database mirroring, the engineering target for recovery time objective (RTO) is 5 minutes. Because of the synchronous database mirroring, we do not anticipate data loss during Back End Server failures except in rare occasions when both the Front End Servers and the Back End Server go down simultaneously while data is being moved between the servers. The engineering target for recovery point objective (RPO) is 5 minutes.</span></span>
  
### <a name="user-experience-during-back-end-server-failure-with-database-mirroring"></a><span data-ttu-id="02e32-156">データベース ミラーリングを使用したバックエンド サーバー障害の間のユーザー エクスペリエンス</span><span class="sxs-lookup"><span data-stu-id="02e32-156">User experience during Back End Server failure with database mirroring</span></span>

<span data-ttu-id="02e32-157">障害の間のユーザー エクスペリエンスは、障害の性質とトポロジによって異なります。</span><span class="sxs-lookup"><span data-stu-id="02e32-157">User experience during a failure depends on the nature of the failure, and on your topology.</span></span>
  
<span data-ttu-id="02e32-p114">監視を構成してあり、プリンシパルで障害が発生した場合は、データベース ミラーリングを使用したバックエンド サーバーのフェールオーバーは自動的かつ迅速に行われます。アクティブ ユーザーがセッションで大きな中断を感じることはありません。</span><span class="sxs-lookup"><span data-stu-id="02e32-p114">If you use database mirroring and have a witness configured, and the principal fails, Back End Server failover happens automatically and quickly. Active users should not notice much interruption to their ongoing sessions.</span></span>
  
<span data-ttu-id="02e32-160">補助の設定がない場合、管理者はフェイル オーバーを手動で起動に時間がかかります。</span><span class="sxs-lookup"><span data-stu-id="02e32-160">If there is no witness configured, it will take some time for the administrator to manually invoke the failover.</span></span> <span data-ttu-id="02e32-161">その間、アクティブなユーザーが影響を受ける可能性があります。</span><span class="sxs-lookup"><span data-stu-id="02e32-161">During that time, active users may be affected.</span></span> <span data-ttu-id="02e32-162">約 30 分間のセッションを通常どおり引き続き。</span><span class="sxs-lookup"><span data-stu-id="02e32-162">They will continue their sessions as normal for about 30 minutes.</span></span> <span data-ttu-id="02e32-163">プライマリも復元されず、または、管理者、バックアップにフェールオーバーしない、し、ユーザーに切り替えられます復元モードでは、いるもの (取引先担当者を追加するには) などの Lync Server 上の永続的な変更を必要とするタスクを実行することを意味します。</span><span class="sxs-lookup"><span data-stu-id="02e32-163">If the primary is still not restored, or an administrator has not failed over to the backup, then users are switched to Resiliency mode, meaning that they are unable to perform tasks that require a persistent change on Lync Server (such as adding a contact).</span></span>
  
<span data-ttu-id="02e32-p116">プリンシパルとミラーの両方のバックエンド サーバーで障害が発生した場合、またはどちらかのサーバーと監視で障害が発生した場合は、(プリンシパルがまだ動作していても) バックエンド サーバーは使用できなくなります。この場合、アクティブ ユーザーはしばらくしてから復元モードに切り替えられます。</span><span class="sxs-lookup"><span data-stu-id="02e32-p116">If both the principal and the mirror Back End Servers fail, or if one of those servers and the witness fails, the Back End Server will become unavailable (even if it is the principal that is still working). In this case, active users are switched to Resiliency mode after some time.</span></span>
  
## <a name="alwayson-availability-groups-and-alwayson-failover-cluster-instances"></a><span data-ttu-id="02e32-166">AlwaysOn 可用性グループと AlwaysOn フェールオーバー クラスター インスタンス</span><span class="sxs-lookup"><span data-stu-id="02e32-166">AlwaysOn Availability Groups and AlwaysOn Failover Cluster Instances</span></span>

<span data-ttu-id="02e32-167">ビジネス サーバーの Skype では、アクティブ/パッシブ、アクティブ/アクティブのないとしてのみ AlwaysOn 可用性グループをサポートしています。</span><span class="sxs-lookup"><span data-stu-id="02e32-167">Skype for Business Server supports AlwaysOn Availability Groups only as active/passive, not active/active.</span></span> 
  
<span data-ttu-id="02e32-168">AlwaysOn 可用性グループまたは AlwaysOn フェールオーバー クラスター インスタンスを使用するには、最初に設定して高可用性ソリューションを構成する SQL Server を使用します。</span><span class="sxs-lookup"><span data-stu-id="02e32-168">To use AlwaysOn Availability Groups or AlwaysOn Failover Cluster Instances, you first use SQL Server to set up and configure the high availability solution.</span></span> <span data-ttu-id="02e32-169">フロント エンド プールに関連付けることをトポロジ ビルダーを使用できます。</span><span class="sxs-lookup"><span data-stu-id="02e32-169">You can then use Topology Builder to associate it with a Front End pool.</span></span>

<span data-ttu-id="02e32-170">ビジネス サーバーの Skype では、次のデータベース ソフトウェアを AlwaysOn をサポートしています。</span><span class="sxs-lookup"><span data-stu-id="02e32-170">Skype for Business Server supports AlwaysOn with the following database software:</span></span>

- <span data-ttu-id="02e32-171">2017 エンタープライズ エディションの SQL Server</span><span class="sxs-lookup"><span data-stu-id="02e32-171">SQL Server 2017 Enterprise Edition</span></span>

- <span data-ttu-id="02e32-172">制限があります、SQL Server 2017 の Standard Edition は、以下の注を参照してください。</span><span class="sxs-lookup"><span data-stu-id="02e32-172">SQL Server 2017 Standard Edition with limitations, see note below</span></span>

- <span data-ttu-id="02e32-173">2016 エンタープライズ エディションの SQL Server</span><span class="sxs-lookup"><span data-stu-id="02e32-173">SQL Server 2016 Enterprise Edition</span></span>

- <span data-ttu-id="02e32-174">制限があります、SQL Server 2016 の Standard Edition は、以下の注を参照してください。</span><span class="sxs-lookup"><span data-stu-id="02e32-174">SQL Server 2016 Standard Edition with limitations, see note below</span></span>

- <span data-ttu-id="02e32-175">2014 エンタープライズ エディションの SQL Server</span><span class="sxs-lookup"><span data-stu-id="02e32-175">SQL Server 2014 Enterprise Edition</span></span>
    
- <span data-ttu-id="02e32-176">SQL Server 2012 の SP2 には、Enterprise Edition の CU2</span><span class="sxs-lookup"><span data-stu-id="02e32-176">SQL Server 2012 SP2 and CU2 Enterprise Edition</span></span>

> [!NOTE]
> <span data-ttu-id="02e32-177">2017 の SQL Server と SQL Server の 2016 は、ビジネス サーバー 2019 の Skype によってサポートされている唯一のバージョンです。</span><span class="sxs-lookup"><span data-stu-id="02e32-177">SQL Server 2017 and SQL Server 2016 are the only versions supported by Skype for Business Server 2019.</span></span>

> [!NOTE]
> <span data-ttu-id="02e32-178">可用性グループに常には、SQL 2016、2017 標準エディションではサポートされて**いません**が、フェールオーバー クラスター インスタンスに常に使用することができます。</span><span class="sxs-lookup"><span data-stu-id="02e32-178">Always On Availability Groups is **not** supported in SQL 2016 and 2017 Standard Editions but you can use Always On Failover Cluster Instances.</span></span> <span data-ttu-id="02e32-179">[エディションと 2016 年の SQL Server のサポートされている機能](https://docs.microsoft.com/sql/sql-server/editions-and-components-of-sql-server-2016?view=sql-server-2017)の詳細を参照してください。</span><span class="sxs-lookup"><span data-stu-id="02e32-179">See [Editions and supported features of SQL Server 2016](https://docs.microsoft.com/sql/sql-server/editions-and-components-of-sql-server-2016?view=sql-server-2017) to learn more.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="02e32-180">AlwaysOn 可用性グループの複数のインスタンスのインスタンス名は同じである必要があります。</span><span class="sxs-lookup"><span data-stu-id="02e32-180">Instance names for multiple AlwaysOn Availability Group instances must be the same.</span></span> 
  
<span data-ttu-id="02e32-181">AlwaysOn 可用性グループを展開する手順を実行するには、 [Skype のビジネス サーバーのバック エンド サーバー上の AlwaysOn 可用性グループの配置](../../deploy/deploy-high-availability-and-disaster-recovery/alwayson-availability-group.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="02e32-181">For steps for deploying AlwaysOn Availability Groups, see [Deploy an AlwaysOn Availability Group on a Back End Server in Skype for Business Server](../../deploy/deploy-high-availability-and-disaster-recovery/alwayson-availability-group.md).</span></span>
  
## <a name="sql-server-failover-clustering"></a><span data-ttu-id="02e32-182">SQL Server フェールオーバー クラスタリング</span><span class="sxs-lookup"><span data-stu-id="02e32-182">SQL Server Failover Clustering</span></span>

<span data-ttu-id="02e32-183">Skype ビジネス サーバー用には、次のデータベース ソフトウェアをクラスター化 SQL Server のフェールオーバーがサポートされています。</span><span class="sxs-lookup"><span data-stu-id="02e32-183">Skype for Business Server supports SQL Server failover clustering with the following database software:</span></span>
  
- <span data-ttu-id="02e32-184">SQL Server Enterprise Edition と Standard Edition の両方の 2017</span><span class="sxs-lookup"><span data-stu-id="02e32-184">SQL Server 2017, both Enterprise Edition and Standard Edition</span></span>

- <span data-ttu-id="02e32-185">SQL Server Enterprise Edition と Standard Edition の両方の 2016</span><span class="sxs-lookup"><span data-stu-id="02e32-185">SQL Server 2016, both Enterprise Edition and Standard Edition</span></span>

- <span data-ttu-id="02e32-186">SQL Server Enterprise Edition と Standard Edition の両方の 2014</span><span class="sxs-lookup"><span data-stu-id="02e32-186">SQL Server 2014, both Enterprise Edition and Standard Edition</span></span>
    
- <span data-ttu-id="02e32-187">SQL Server 2012 の SP2 には、CU2、Enterprise Edition と Standard Edition の両方</span><span class="sxs-lookup"><span data-stu-id="02e32-187">SQL Server 2012 SP2 and CU2, both Enterprise Edition and Standard Edition</span></span>

<span data-ttu-id="02e32-188">SQL のフェールオーバー クラスタ リングを使用するには、最初を設定し、フロント エンド プールを展開する前に SQL Server のクラスターを構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="02e32-188">To use SQL failover clustering, you should first set up and configure the SQL Server cluster before deploying your Front End pool.</span></span> <span data-ttu-id="02e32-189">ベスト ・ プラクティスは、SQL Server 2012 のフェールオーバー クラスタ リングのセットアップ手順を参照してください[https://technet.microsoft.com/en-us/library/hh231721.aspx](https://technet.microsoft.com/en-us/library/hh231721.aspx)。</span><span class="sxs-lookup"><span data-stu-id="02e32-189">For best practices and setup instructions for failover clustering in SQL Server 2012, see [https://technet.microsoft.com/en-us/library/hh231721.aspx](https://technet.microsoft.com/en-us/library/hh231721.aspx).</span></span>

> [!NOTE]
> <span data-ttu-id="02e32-190">2017 の SQL Server と SQL Server の 2016 は、ビジネス サーバー 2019 の Skype によってサポートされている唯一のバージョンです。</span><span class="sxs-lookup"><span data-stu-id="02e32-190">SQL Server 2017 and SQL Server 2016 are the only versions supported by Skype for Business Server 2019.</span></span>
    
<span data-ttu-id="02e32-191">SQL のフェールオーバー クラスタ リングを使用するには、最初を設定し、フロント エンド プールを展開する前に SQL Server のクラスターを構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="02e32-191">To use SQL failover clustering, you should first set up and configure the SQL Server cluster before deploying your Front End pool.</span></span> <span data-ttu-id="02e32-192">ベスト ・ プラクティスは、SQL Server 2014、2016 のフェールオーバー クラスタ リングのセットアップ手順を参照してください[https://technet.microsoft.com/en-us/library/hh231721.aspx](https://technet.microsoft.com/en-us/library/hh231721.aspx)。</span><span class="sxs-lookup"><span data-stu-id="02e32-192">For best practices and setup instructions for failover clustering in SQL Server 2014 and 2016, see [https://technet.microsoft.com/en-us/library/hh231721.aspx](https://technet.microsoft.com/en-us/library/hh231721.aspx).</span></span> <span data-ttu-id="02e32-193">SQL Server 2008 のクラスタ リング フェイル オーバーを参照してください[https://technet.microsoft.com/en-us/library/ms189134(v=sql.105).aspx](https://technet.microsoft.com/en-us/library/ms189134%28v=sql.105%29.aspx)。</span><span class="sxs-lookup"><span data-stu-id="02e32-193">For failover clustering in SQL Server 2008, see [https://technet.microsoft.com/en-us/library/ms189134(v=sql.105).aspx](https://technet.microsoft.com/en-us/library/ms189134%28v=sql.105%29.aspx).</span></span>
  
<span data-ttu-id="02e32-p121">SQL Server をインストールする際は、SQL Server Management Studio をインストールしてデータベースとログ ファイルの場所を管理する必要があります。SQL Server Management Studio は、SQL Server のインストール時にオプション コンポーネントとしてインストールされます。</span><span class="sxs-lookup"><span data-stu-id="02e32-p121">When you install SQL Server, you should install SQL Server Management Studio to manage the locations for database and log file locations. SQL Server Management Studio is installed as an optional component when you install SQL Server.</span></span>
  

