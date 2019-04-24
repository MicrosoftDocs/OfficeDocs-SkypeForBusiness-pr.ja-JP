---
title: ビジネス サーバー 2015 の Skype での永続的なチャット サーバーの高可用性と災害復旧の計画
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 5/17/2016
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: d9aa622a-95a3-4d8e-8d49-cbfe183f25bf
description: '概要: ビジネス サーバー 2015 の Skype での永続的なチャット サーバーの高可用性と災害復旧を計画する方法の詳細については、このトピックを読みます。'
ms.openlocfilehash: 88584c43cb205d10d2baacb6cb31c4e8fdbb228a
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "32213827"
---
# <a name="plan-for-high-availability-and-disaster-recovery-for-persistent-chat-server-in-skype-for-business-server-2015"></a><span data-ttu-id="d11c2-103">ビジネス サーバー 2015 の Skype での永続的なチャット サーバーの高可用性と災害復旧の計画</span><span class="sxs-lookup"><span data-stu-id="d11c2-103">Plan for high availability and disaster recovery for Persistent Chat Server in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="d11c2-104">**の概要:** ビジネス サーバー 2015 の Skype での永続的なチャット サーバーの高可用性と災害復旧を計画する方法の詳細については、このトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="d11c2-104">**Summary:** Read this topic to learn how to plan for high availability and disaster recovery for Persistent Chat Server in Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="d11c2-105">高可用性と災害復旧の永続的なチャット サーバーの完全な処理に必要な通常以外の追加リソースが必要です。</span><span class="sxs-lookup"><span data-stu-id="d11c2-105">High availability and disaster recovery for Persistent Chat Server require additional resources beyond what is typically needed for full operation.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="d11c2-106">常設チャット サーバー データベースで SQL AlwaysOn 可用性グループを使用することは、サポートされていません。</span><span class="sxs-lookup"><span data-stu-id="d11c2-106">Using SQL AlwaysOn Availability Groups is not supported with Persistent Chat Server databases.</span></span> 

> [!NOTE] 
> <span data-ttu-id="d11c2-107">永続的なチャットですがビジネス サーバー 2015 の Skype で利用可能なビジネス サーバー 2019 の Skype でサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="d11c2-107">Persistent chat is available in Skype for Business Server 2015 but is no longer supported in Skype for Business Server 2019.</span></span> <span data-ttu-id="d11c2-108">同じ機能は、チームで使用できます。</span><span class="sxs-lookup"><span data-stu-id="d11c2-108">The same functionality is available in Teams.</span></span> <span data-ttu-id="d11c2-109">詳細については、[マイクロソフトのチームにビジネス用の Skype からの旅](/microsoftteams/journey-skypeforbusiness-teams)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d11c2-109">For more information, see [Journey from Skype for Business to Microsoft Teams](/microsoftteams/journey-skypeforbusiness-teams).</span></span> <span data-ttu-id="d11c2-110">永続的なチャットを使用する場合は、選択肢は、いずれかをチームでは、この機能を必要とするユーザーを移行するまたはビジネス サーバー 2015 の Skype を使用し続ける。</span><span class="sxs-lookup"><span data-stu-id="d11c2-110">If you need to use Persistent chat, your choices are to either migrate users requiring this functionality to Teams, or to continue using Skype for Business Server 2015.</span></span> 
  
## <a name="resource-requirements"></a><span data-ttu-id="d11c2-111">リソースの要件</span><span class="sxs-lookup"><span data-stu-id="d11c2-111">Resource requirements</span></span>

<span data-ttu-id="d11c2-112">永続的なチャット サーバーを構成する、高可用性と災害復旧について、前に、以下の追加リソースがあることを確認します。</span><span class="sxs-lookup"><span data-stu-id="d11c2-112">Before configuring Persistent Chat Server for high availability and disaster recovery, ensure that you have the following additional resources.</span></span> 
  
- <span data-ttu-id="d11c2-113">永続的なチャット サーバー サービスのホーム フロント エンドが配置されている同じ物理データ センター内にある 1 つの専用データベース インスタンス。</span><span class="sxs-lookup"><span data-stu-id="d11c2-113">One dedicated database instance located in the same physical data center in which the home front end of the Persistent Chat Server service is located.</span></span> <span data-ttu-id="d11c2-114">このデータベースは、プライマリの永続的なチャットのデータベースの SQL Server ミラーの役割を果たします。</span><span class="sxs-lookup"><span data-stu-id="d11c2-114">This database will serve as the SQL Server mirror for the primary Persistent Chat database.</span></span> <span data-ttu-id="d11c2-115">必要に応じて、ミラー データベースへの自動フェイル オーバーする場合は、ミラーリングの補助として使用する追加の SQL Server を指定します。</span><span class="sxs-lookup"><span data-stu-id="d11c2-115">Optionally, designate an additional SQL Server to serve as the mirroring witness if you want an automated failover to the mirror database.</span></span>
    
- <span data-ttu-id="d11c2-116">他の物理データ センターに存在する、1 つの専用データベース インスタンス。</span><span class="sxs-lookup"><span data-stu-id="d11c2-116">One dedicated database instance located in the other physical data center.</span></span> <span data-ttu-id="d11c2-117">このデータベースは、プライマリ ・ データ ・ センター内のデータベースの SQL Server のログ配布セカンダリ データベースの役割を果たします。</span><span class="sxs-lookup"><span data-stu-id="d11c2-117">This database will serve as the SQL Server Log Shipping secondary database for the database in the primary data center.</span></span>
    
- <span data-ttu-id="d11c2-118">セカンダリ データベースの SQL Server ミラーとして機能する専用のデータベースのインスタンスを 1 つ。</span><span class="sxs-lookup"><span data-stu-id="d11c2-118">One dedicated database instance to serve as the SQL Server mirror for the secondary database.</span></span> <span data-ttu-id="d11c2-119">必要に応じて、ミラーリング監視用としてサーバーに追加の SQL Server を指定します。</span><span class="sxs-lookup"><span data-stu-id="d11c2-119">Optionally, designate an additional SQL Server to server as the mirroring witness.</span></span> <span data-ttu-id="d11c2-120">どちらもセカンダリ データベースと同じ物理データ センターに存在する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d11c2-120">Both of these must be located in the same physical data center as the secondary database.</span></span>
    
- <span data-ttu-id="d11c2-121">永続的なチャット サーバーのコンプライアンスを有効にすると、3 つの他の専用データベース インスタンスは必要があります。</span><span class="sxs-lookup"><span data-stu-id="d11c2-121">If Persistent Chat Server compliance is enabled, an additional three dedicated database instances are required.</span></span> <span data-ttu-id="d11c2-122">これらの再配布は、前述の永続的なチャットのデータベースの場合と同じです。</span><span class="sxs-lookup"><span data-stu-id="d11c2-122">Their distribution is the same as those previously outlined for the Persistent Chat database.</span></span> <span data-ttu-id="d11c2-123">永続的なチャット データベースと同じ SQL Server インスタンスを共有するための対応のデータベースのことはできますが、高可用性と災害復旧用のスタンドアロンのインスタンスを推奨します。</span><span class="sxs-lookup"><span data-stu-id="d11c2-123">While it is possible for the compliance database to share the same SQL Server instance as the Persistent Chat database, standalone instances for high availability and disaster recovery are recommended.</span></span>
    
- <span data-ttu-id="d11c2-124">ファイル共有を作成され、SQL Server のログ配布のトランザクション ログ用に指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d11c2-124">A file share must be created and designated for the SQL Server Log Shipping transaction logs.</span></span> <span data-ttu-id="d11c2-125">データベースの永続的なチャットを実行している両方のデータ ・ センター内のすべての SQL サーバーは、このファイル共有への読み取り/書き込みアクセスに必要です。</span><span class="sxs-lookup"><span data-stu-id="d11c2-125">All SQL Servers in both data centers that run Persistent Chat databases must have read/write access to this file share.</span></span> <span data-ttu-id="d11c2-126">この共有は、FileStore 役割の一部としては定義されません。</span><span class="sxs-lookup"><span data-stu-id="d11c2-126">This share is not defined as part of a FileStore role.</span></span>
    
- <span data-ttu-id="d11c2-127">プライマリ サーバーのファイル共有からコピーした SQL Server トランザクション ・ ログの保存先フォルダーとして使用するセカンダリ ・ データベース ・ サーバ上のファイル共有。</span><span class="sxs-lookup"><span data-stu-id="d11c2-127">A file share on the secondary database server to serve as the destination folder for the SQL Server transaction logs that are copied from the primary server file share.</span></span>
    
## <a name="disaster-recovery-and-high-availability-solutions"></a><span data-ttu-id="d11c2-128">障害復旧と高可用性のソリューション</span><span class="sxs-lookup"><span data-stu-id="d11c2-128">Disaster recovery and high availability solutions</span></span>

<span data-ttu-id="d11c2-129">ビジネス サーバー用の Skype は、バック エンド サーバー、データベース ・ ミラーリングなどの複数の高可用性モードをサポートします。</span><span class="sxs-lookup"><span data-stu-id="d11c2-129">Skype for Business Server supports multiple modes of high availability for your Back End Servers, including database mirroring.</span></span> <span data-ttu-id="d11c2-130">詳細については、「[Plan for high availability and disaster recovery in Skype for Business Server 2015](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d11c2-130">For more information, see [Plan for high availability and disaster recovery in Skype for Business Server 2015](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md).</span></span> 
  
<span data-ttu-id="d11c2-131">拡大された永続的なチャット サーバー プールの永続的なチャット サーバーがこのトピックで説明されている災害復旧ソリューションがビルドされます。</span><span class="sxs-lookup"><span data-stu-id="d11c2-131">The disaster recovery solution for Persistent Chat Server described in this topic is built on a stretched Persistent Chat Server pool.</span></span> <span data-ttu-id="d11c2-132">拡張型の仮想ローカル エリア ネットワーク (VLAN) に関する要件はありません。</span><span class="sxs-lookup"><span data-stu-id="d11c2-132">There is no requirement for a stretched virtual local area network (VLAN).</span></span> <span data-ttu-id="d11c2-133">永続的なチャット サーバー プールを拡大するには、論理的には、トポロジでは、1 つのプールを構成するが、物理的に 2 つの異なるデータ センターにプールにサーバーを配置します。</span><span class="sxs-lookup"><span data-stu-id="d11c2-133">By stretching a Persistent Chat Server pool, you configure one pool in the topology logically, but you physically place the servers in the pool in two different data centers.</span></span> <span data-ttu-id="d11c2-134">データベースの SQL Server ミラーリングを同じ方法で構成し、データベースとそのミラーを同じデータ センター内に展開します。</span><span class="sxs-lookup"><span data-stu-id="d11c2-134">You configure SQL Server mirroring for the database in the same way, and deploy the database and the mirror in the same data center.</span></span> <span data-ttu-id="d11c2-135">セカンダリ データ センターでは、(障害復旧時に高可用性を提供するためにオプションのミラーを使用して) バックアップ データベースを構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d11c2-135">You need to configure a backup database in the secondary data center (with an optional mirror to provide high availability during disaster recovery).</span></span> <span data-ttu-id="d11c2-136">これは、障害復旧時にフェールオーバー用に使用されるバックアップ データベースです。</span><span class="sxs-lookup"><span data-stu-id="d11c2-136">This is the backup database used for failover during disaster recovery.</span></span> 
  
<span data-ttu-id="d11c2-137">永続的なチャット サーバーの高可用性と障害回復を構成する方法の詳細については、[構成の高可用性とビジネス サーバー 2015 の Skype での永続的なチャット サーバーの障害回復](../../deploy/deploy-persistent-chat-server/configure-hadr-for-persistent-chat.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d11c2-137">For details about how to configure high availability and disaster recovery for Persistent Chat Server, see [Configure high availability and disaster recovery for Persistent Chat Server in Skype for Business Server 2015](../../deploy/deploy-persistent-chat-server/configure-hadr-for-persistent-chat.md).</span></span> 
  
<span data-ttu-id="d11c2-138">次の図は、2 つの別のプールが拡大されたトポロジでは、永続的なチャット サーバー プールを構成する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="d11c2-138">The following figures show how the Persistent Chat Server pool can be configured in two different stretched pool topologies:</span></span>
  
- <span data-ttu-id="d11c2-139">拡大された永続的なチャット サーバー プールのデータ ・ センターは、高帯域幅と低レーテンシーと地域にある場合です。</span><span class="sxs-lookup"><span data-stu-id="d11c2-139">Stretched Persistent Chat Server pool when data centers are geo-located with high bandwidth/low latency.</span></span>
    
- <span data-ttu-id="d11c2-140">拡大された永続的なチャット サーバー プールのデータ ・ センターでは、低帯域幅/高遅延の地域にある場合です。</span><span class="sxs-lookup"><span data-stu-id="d11c2-140">Stretched Persistent Chat Server pool when data centers are geo-located with low bandwidth/high latency.</span></span>
    
<span data-ttu-id="d11c2-141">場所のデータ センターは、高帯域幅と低レーテンシーと地域にある拡大された永続的なチャット サーバー プール トポロジを図 1 に示します。</span><span class="sxs-lookup"><span data-stu-id="d11c2-141">Figure 1 shows a stretched Persistent Chat Server pool topology where data centers are geo-located with high bandwidth/low latency.</span></span> <span data-ttu-id="d11c2-142">論理的および物理的なトポロジは、次を想定しています。</span><span class="sxs-lookup"><span data-stu-id="d11c2-142">Assume the following for the logical and physical topologies:</span></span>
  
- <span data-ttu-id="d11c2-143">論理トポロジは次の構成です。</span><span class="sxs-lookup"><span data-stu-id="d11c2-143">The logical topology consists of the following:</span></span>
    
  - <span data-ttu-id="d11c2-144">サーバー 1 ～ 8 を含む、サイト 1 および 2 にまたがる常設チャット プール。</span><span class="sxs-lookup"><span data-stu-id="d11c2-144">A Persistent Chat pool across Sites 1 and 2 containing servers 1 through 8.</span></span>
    
  - <span data-ttu-id="d11c2-145">フロント エンド サーバー プール、永続的なチャットのデータベース、ミラー化されたデータベース、および、必要に応じて、(図では表示されません)、補助データベース上に存在する物理的なサイトの 1 です。</span><span class="sxs-lookup"><span data-stu-id="d11c2-145">A Front End Server pool, a Persistent Chat database, a mirrored database, and, optionally, a witness database (not shown in diagram) residing physically on Site 1.</span></span> 
    
  - <span data-ttu-id="d11c2-146">サイト 2 上に物理的に存在する、2 つ目のフロントエンド サーバー プールと、バックアップ データベース。</span><span class="sxs-lookup"><span data-stu-id="d11c2-146">A second Front End Server pool and a backup database residing physically on Site 2.</span></span>
    
- <span data-ttu-id="d11c2-147">物理的なトポロジで構成されていますサイト 1 と 2 のとおり。</span><span class="sxs-lookup"><span data-stu-id="d11c2-147">The physical topology consists of Sites 1 and 2 as follows:</span></span>
    
  - <span data-ttu-id="d11c2-148">サイト 1 上に、サーバー 1 ～ 4 (2 台がアクティブで 2 台がアイドル) が含まれる常設チャット プール。</span><span class="sxs-lookup"><span data-stu-id="d11c2-148">A Persistent Chat pool, containing servers 1 through 4, two active, two idle on Site 1.</span></span>
    
  - <span data-ttu-id="d11c2-149">サイト 5 上に、サーバー 2 ～ 8 (2 台がアクティブで 2 台がアイドル) が含まれる常設チャット プール。</span><span class="sxs-lookup"><span data-stu-id="d11c2-149">A Persistent Chat pool, containing servers 5 through 8, two active, two idle on Site 2.</span></span>
    
  - <span data-ttu-id="d11c2-150">フロント エンド サーバー プール、永続的なチャットのデータベース、ミラー化されたデータベース、および、必要に応じて、補助データベース (図には表示されません) サイト 1 の。</span><span class="sxs-lookup"><span data-stu-id="d11c2-150">A Front End Server pool, a Persistent Chat database, a mirrored database, and, optionally, a witness database (not shown in diagram) on Site 1.</span></span>
    
  - <span data-ttu-id="d11c2-151">サイト 2 上に、フロントエンド サーバー プールと、SQL ログ配布のターゲットであるバックアップ データベース。</span><span class="sxs-lookup"><span data-stu-id="d11c2-151">A Front End Server Pool, and a backup database, which is the SQL log shipping target, on Site 2.</span></span>
    
<span data-ttu-id="d11c2-152">**データ センターが高帯域幅/低遅延の場所に設置されている場合の拡張常設チャット サーバー プール**</span><span class="sxs-lookup"><span data-stu-id="d11c2-152">**Stretched Persistent Chat Server pool when data centers are geo-located with high bandwidth/low latency**</span></span>

![高帯域幅/低遅延の常設チャット用に拡張されたプール](../../media/55cf3d4b-5f51-4d2f-84ca-b4a13dc5eba3.png)
  
<span data-ttu-id="d11c2-154">データ センターが低帯域幅/高遅延の地域にあるを拡大された永続的なチャット サーバー プール トポロジを図 2 に示します。</span><span class="sxs-lookup"><span data-stu-id="d11c2-154">Figure 2 shows a stretched Persistent Chat Server pool topology where data centers are geo-located with low bandwidth/high latency.</span></span>
  
- <span data-ttu-id="d11c2-155">論理トポロジは次の構成です。</span><span class="sxs-lookup"><span data-stu-id="d11c2-155">The logical topology consists of the following:</span></span>
    
  - <span data-ttu-id="d11c2-156">サーバー 1 ～ 8 を含む、サイト 1 および 2 にまたがる常設チャット プール。</span><span class="sxs-lookup"><span data-stu-id="d11c2-156">A Persistent Chat pool across Sites 1 and 2 containing servers 1 through 8.</span></span>
    
  - <span data-ttu-id="d11c2-157">フロント エンド サーバー プール、永続的なチャットのデータベース、ミラー化されたデータベース、および、必要に応じて、(図では表示されません)、補助データベース上に存在する物理的なサイトの 1 です。</span><span class="sxs-lookup"><span data-stu-id="d11c2-157">A Front End Server pool, a Persistent Chat database, a mirrored database, and, optionally, a witness database (not shown in diagram) residing physically on Site 1.</span></span> 
    
  - <span data-ttu-id="d11c2-158">サイト 2 上に物理的に存在する、2 つ目のフロントエンド サーバー プールと、バックアップ データベース。</span><span class="sxs-lookup"><span data-stu-id="d11c2-158">A second Front End Server pool and a backup database residing physically on Site 2.</span></span>
    
- <span data-ttu-id="d11c2-159">物理的なトポロジで構成されていますサイト 1 と 2 のとおり。</span><span class="sxs-lookup"><span data-stu-id="d11c2-159">The physical topology consists of Sites 1 and 2 as follows:</span></span>
    
  - <span data-ttu-id="d11c2-160">サイト 1 上に、サーバー 1 ～ 4 (すべてアクティブ) が含まれる常設チャット プール。</span><span class="sxs-lookup"><span data-stu-id="d11c2-160">A Persistent Chat pool, containing servers 1 through 4, all active, on Site 1.</span></span>
    
  - <span data-ttu-id="d11c2-161">サイト 2 上に、サーバー 5 ～ 8 (すべてアイドル) が含まれる常設チャット プール。</span><span class="sxs-lookup"><span data-stu-id="d11c2-161">A Persistent Chat pool, containing servers 5 through 8, all idle, on Site 2.</span></span>
    
  - <span data-ttu-id="d11c2-162">フロント エンド サーバー プール、永続的なチャットのデータベース、ミラー化されたデータベース、および、必要に応じて、補助データベース (図には表示されません) サイト 1 の。</span><span class="sxs-lookup"><span data-stu-id="d11c2-162">A Front End Server pool, a Persistent Chat database, a mirrored database, and, optionally, a witness database (not shown in diagram) on Site 1.</span></span>
    
  - <span data-ttu-id="d11c2-163">サイト 2 上に、フロントエンド サーバー プールと、SQL ログ配布のターゲットであるバックアップ データベース。</span><span class="sxs-lookup"><span data-stu-id="d11c2-163">A Front End Server pool, and a backup database, which is the SQL log shipping target, on Site 2.</span></span>
    
<span data-ttu-id="d11c2-164">**データ センターが低帯域幅/高遅延の場所に設置されている場合の拡張常設チャット サーバー プール**</span><span class="sxs-lookup"><span data-stu-id="d11c2-164">**Stretched Persistent Chat Server pool when data centers are geo-located with low bandwidth/high latency**</span></span>

![低帯域幅/高遅延の常設チャット用に拡張されたプール](../../media/40cbd902-57b8-4d57-a61c-cde4e0bd47f0.png)
  

