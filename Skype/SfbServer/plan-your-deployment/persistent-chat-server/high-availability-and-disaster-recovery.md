---
title: Skype for Business Server 2015 での常設チャット サーバーの高可用性と障害復旧を計画する
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 5/17/2016
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: d9aa622a-95a3-4d8e-8d49-cbfe183f25bf
description: '概要: このトピックでは、Skype for Business Server 2015 で常設チャット サーバーの高可用性と障害復旧を計画する方法について説明します。'
ms.openlocfilehash: d29271b314981f3de0eb7bd0b963637c554fb26f
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49832357"
---
# <a name="plan-for-high-availability-and-disaster-recovery-for-persistent-chat-server-in-skype-for-business-server-2015"></a><span data-ttu-id="aece8-103">Skype for Business Server 2015 での常設チャット サーバーの高可用性と障害復旧を計画する</span><span class="sxs-lookup"><span data-stu-id="aece8-103">Plan for high availability and disaster recovery for Persistent Chat Server in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="aece8-104">**概要:** このトピックでは、Skype for Business Server 2015 で常設チャット サーバーの高可用性と障害復旧を計画する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="aece8-104">**Summary:** Read this topic to learn how to plan for high availability and disaster recovery for Persistent Chat Server in Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="aece8-105">常設チャット サーバーの高可用性と障害復旧には、通常、完全運用に必要なリソースを超える追加のリソースが必要です。</span><span class="sxs-lookup"><span data-stu-id="aece8-105">High availability and disaster recovery for Persistent Chat Server require additional resources beyond what is typically needed for full operation.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="aece8-106">AlwaysOn SQLの使用は、常設チャット サーバー データベースではサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="aece8-106">Using SQL AlwaysOn Availability Groups is not supported with Persistent Chat Server databases.</span></span> 

> [!NOTE] 
> <span data-ttu-id="aece8-107">常設チャットは Skype for Business Server 2015 で使用できますが、Skype for Business Server 2019 ではサポートされなくなりました。</span><span class="sxs-lookup"><span data-stu-id="aece8-107">Persistent chat is available in Skype for Business Server 2015 but is no longer supported in Skype for Business Server 2019.</span></span> <span data-ttu-id="aece8-108">Teams でも同じ機能を使用できます。</span><span class="sxs-lookup"><span data-stu-id="aece8-108">The same functionality is available in Teams.</span></span> <span data-ttu-id="aece8-109">詳細については、「Microsoft Teams のアップグレード [の開始」を参照してください](/microsoftteams/upgrade-start-here)。</span><span class="sxs-lookup"><span data-stu-id="aece8-109">For more information, see [Getting started with your Microsoft Teams upgrade](/microsoftteams/upgrade-start-here).</span></span> <span data-ttu-id="aece8-110">常設チャットを使用する必要がある場合は、この機能を必要とするユーザーを Teams に移行するか、Skype for Business Server 2015 を引き続き使用するかのどちらかを選択できます。</span><span class="sxs-lookup"><span data-stu-id="aece8-110">If you need to use Persistent chat, your choices are to either migrate users requiring this functionality to Teams, or to continue using Skype for Business Server 2015.</span></span> 
  
## <a name="resource-requirements"></a><span data-ttu-id="aece8-111">リソースの要件</span><span class="sxs-lookup"><span data-stu-id="aece8-111">Resource requirements</span></span>

<span data-ttu-id="aece8-112">高可用性と障害復旧用に常設チャット サーバーを構成する前に、次の追加リソースが必要です。</span><span class="sxs-lookup"><span data-stu-id="aece8-112">Before configuring Persistent Chat Server for high availability and disaster recovery, ensure that you have the following additional resources.</span></span> 
  
- <span data-ttu-id="aece8-113">常設チャット サーバー サービスのホーム フロント エンドがあるのと同じ物理データ センターにある 1 つの専用データベース インスタンス。</span><span class="sxs-lookup"><span data-stu-id="aece8-113">One dedicated database instance located in the same physical data center in which the home front end of the Persistent Chat Server service is located.</span></span> <span data-ttu-id="aece8-114">このデータベースは、プライマリ 常設チャット SQL Serverミラーの役割を果たします。</span><span class="sxs-lookup"><span data-stu-id="aece8-114">This database will serve as the SQL Server mirror for the primary Persistent Chat database.</span></span> <span data-ttu-id="aece8-115">必要に応じて、ミラー データベースSQL Serverフェールオーバーする場合にミラーリング監視の役割を果たす追加の監視サーバーを指定します。</span><span class="sxs-lookup"><span data-stu-id="aece8-115">Optionally, designate an additional SQL Server to serve as the mirroring witness if you want an automated failover to the mirror database.</span></span>
    
- <span data-ttu-id="aece8-116">他の物理データ センターに存在する、1 つの専用データベース インスタンス。</span><span class="sxs-lookup"><span data-stu-id="aece8-116">One dedicated database instance located in the other physical data center.</span></span> <span data-ttu-id="aece8-117">このデータベースは、プライマリ データ センター SQL Serverログ配布セカンダリ データベースの役割を果たします。</span><span class="sxs-lookup"><span data-stu-id="aece8-117">This database will serve as the SQL Server Log Shipping secondary database for the database in the primary data center.</span></span>
    
- <span data-ttu-id="aece8-118">セカンダリ データベースのミラーとして機能する 1 SQL Serverデータベース インスタンス。</span><span class="sxs-lookup"><span data-stu-id="aece8-118">One dedicated database instance to serve as the SQL Server mirror for the secondary database.</span></span> <span data-ttu-id="aece8-119">必要に応じて、サーバーに追加SQL Serverミラーリング監視として指定します。</span><span class="sxs-lookup"><span data-stu-id="aece8-119">Optionally, designate an additional SQL Server to server as the mirroring witness.</span></span> <span data-ttu-id="aece8-120">どちらもセカンダリ データベースと同じ物理データ センターに存在する必要があります。</span><span class="sxs-lookup"><span data-stu-id="aece8-120">Both of these must be located in the same physical data center as the secondary database.</span></span>
    
- <span data-ttu-id="aece8-121">常設チャット サーバーのコンプライアンスが有効になっている場合は、追加の 3 つの専用データベース インスタンスが必要です。</span><span class="sxs-lookup"><span data-stu-id="aece8-121">If Persistent Chat Server compliance is enabled, an additional three dedicated database instances are required.</span></span> <span data-ttu-id="aece8-122">これらの配布は、常設チャット データベースで以前に概説した配布と同じです。</span><span class="sxs-lookup"><span data-stu-id="aece8-122">Their distribution is the same as those previously outlined for the Persistent Chat database.</span></span> <span data-ttu-id="aece8-123">コンプライアンス データベースは常設チャット データベースと同じ SQL Server インスタンスを共有することができますが、高可用性および障害復旧用のスタンドアロン インスタンスをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="aece8-123">While it is possible for the compliance database to share the same SQL Server instance as the Persistent Chat database, standalone instances for high availability and disaster recovery are recommended.</span></span>
    
- <span data-ttu-id="aece8-124">ログ配布のトランザクション ログ用にファイル共有SQL Server指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="aece8-124">A file share must be created and designated for the SQL Server Log Shipping transaction logs.</span></span> <span data-ttu-id="aece8-125">常設SQLデータベースを実行する両方のデータ センターのすべてのサーバーに、このファイル共有への読み取り/書き込みアクセス権が必要です。</span><span class="sxs-lookup"><span data-stu-id="aece8-125">All SQL Servers in both data centers that run Persistent Chat databases must have read/write access to this file share.</span></span> <span data-ttu-id="aece8-126">この共有は、FileStore 役割の一部として定義されません。</span><span class="sxs-lookup"><span data-stu-id="aece8-126">This share is not defined as part of a FileStore role.</span></span>
    
- <span data-ttu-id="aece8-127">プライマリ サーバーのファイル共有からコピーされた SQL Server トランザクション ログの保存先フォルダーとして機能するセカンダリ データベース サーバー上のファイル共有。</span><span class="sxs-lookup"><span data-stu-id="aece8-127">A file share on the secondary database server to serve as the destination folder for the SQL Server transaction logs that are copied from the primary server file share.</span></span>
    
## <a name="disaster-recovery-and-high-availability-solutions"></a><span data-ttu-id="aece8-128">障害復旧および高可用性ソリューション</span><span class="sxs-lookup"><span data-stu-id="aece8-128">Disaster recovery and high availability solutions</span></span>

<span data-ttu-id="aece8-129">Skype for Business Server は、データベース ミラーリングを含む、バック エンド サーバーの高可用性の複数のモードをサポートしています。</span><span class="sxs-lookup"><span data-stu-id="aece8-129">Skype for Business Server supports multiple modes of high availability for your Back End Servers, including database mirroring.</span></span> <span data-ttu-id="aece8-130">詳細については [、「Plan for high availability and disaster recovery in Skype for Business Server 2015」を参照](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md)してください。</span><span class="sxs-lookup"><span data-stu-id="aece8-130">For more information, see [Plan for high availability and disaster recovery in Skype for Business Server 2015](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md).</span></span> 
  
<span data-ttu-id="aece8-131">このトピックで説明する常設チャット サーバーの障害復旧ソリューションは、ストレッチされた常設チャット サーバー プール上に構築されています。</span><span class="sxs-lookup"><span data-stu-id="aece8-131">The disaster recovery solution for Persistent Chat Server described in this topic is built on a stretched Persistent Chat Server pool.</span></span> <span data-ttu-id="aece8-132">仮想ローカル エリア ネットワーク (VLAN) を拡大する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="aece8-132">There is no requirement for a stretched virtual local area network (VLAN).</span></span> <span data-ttu-id="aece8-133">常設チャット サーバー プールを拡大することで、トポロジ内に論理的に 1 つのプールを構成しますが、2 つの異なるデータ センターのプールにサーバーを物理的に配置します。</span><span class="sxs-lookup"><span data-stu-id="aece8-133">By stretching a Persistent Chat Server pool, you configure one pool in the topology logically, but you physically place the servers in the pool in two different data centers.</span></span> <span data-ttu-id="aece8-134">データベースのSQL Serverミラーリングを同じ方法で構成し、データベースとミラーを同じデータ センターに展開します。</span><span class="sxs-lookup"><span data-stu-id="aece8-134">You configure SQL Server mirroring for the database in the same way, and deploy the database and the mirror in the same data center.</span></span> <span data-ttu-id="aece8-135">セカンダリ データ センターでバックアップ データベースを構成する必要があります (障害復旧時に高可用性を提供するオプションのミラーを使用)。</span><span class="sxs-lookup"><span data-stu-id="aece8-135">You need to configure a backup database in the secondary data center (with an optional mirror to provide high availability during disaster recovery).</span></span> <span data-ttu-id="aece8-136">これは、障害復旧時のフェールオーバーに使用されるバックアップ データベースです。</span><span class="sxs-lookup"><span data-stu-id="aece8-136">This is the backup database used for failover during disaster recovery.</span></span> 
  
<span data-ttu-id="aece8-137">常設チャット サーバーの高可用性と障害復旧を構成する方法の詳細については [、「Configure high availability and disaster recovery for Persistent Chat Server in Skype for Business Server 2015」](../../deploy/deploy-persistent-chat-server/configure-hadr-for-persistent-chat.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="aece8-137">For details about how to configure high availability and disaster recovery for Persistent Chat Server, see [Configure high availability and disaster recovery for Persistent Chat Server in Skype for Business Server 2015](../../deploy/deploy-persistent-chat-server/configure-hadr-for-persistent-chat.md).</span></span> 
  
<span data-ttu-id="aece8-138">次の図は、常設チャット サーバー プールを 2 つの異なるストレッチ プール トポロジで構成する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="aece8-138">The following figures show how the Persistent Chat Server pool can be configured in two different stretched pool topologies:</span></span>
  
- <span data-ttu-id="aece8-139">データ センターが高帯域幅/低遅延の場所に設置されている場合の拡張常設チャット サーバー プール</span><span class="sxs-lookup"><span data-stu-id="aece8-139">Stretched Persistent Chat Server pool when data centers are geo-located with high bandwidth/low latency.</span></span>
    
- <span data-ttu-id="aece8-140">データ センターが低帯域幅/高遅延の場所に設置されている場合の拡張常設チャット サーバー プール</span><span class="sxs-lookup"><span data-stu-id="aece8-140">Stretched Persistent Chat Server pool when data centers are geo-located with low bandwidth/high latency.</span></span>
    
<span data-ttu-id="aece8-141">図 1 は、データ センターが高帯域幅/低待機時間で地理的に位置するストレッチド 常設チャット サーバー プール トポロジを示しています。</span><span class="sxs-lookup"><span data-stu-id="aece8-141">Figure 1 shows a stretched Persistent Chat Server pool topology where data centers are geo-located with high bandwidth/low latency.</span></span> <span data-ttu-id="aece8-142">論理トポロジと物理トポロジでは、次の条件を想定します。</span><span class="sxs-lookup"><span data-stu-id="aece8-142">Assume the following for the logical and physical topologies:</span></span>
  
- <span data-ttu-id="aece8-143">論理トポロジは、次の要素で構成されます。</span><span class="sxs-lookup"><span data-stu-id="aece8-143">The logical topology consists of the following:</span></span>
    
  - <span data-ttu-id="aece8-144">サーバー 1 ~ 8 を含むサイト 1 とサイト 2 の常設チャット プール。</span><span class="sxs-lookup"><span data-stu-id="aece8-144">A Persistent Chat pool across Sites 1 and 2 containing servers 1 through 8.</span></span>
    
  - <span data-ttu-id="aece8-145">サイト 1 上に物理的に存在するフロントエンド サーバー プール、常設チャット データベース、ミラー 化データベース、および必要に応じて監視データベース (図には表示されません)。</span><span class="sxs-lookup"><span data-stu-id="aece8-145">A Front End Server pool, a Persistent Chat database, a mirrored database, and, optionally, a witness database (not shown in diagram) residing physically on Site 1.</span></span> 
    
  - <span data-ttu-id="aece8-146">2 番目のフロントエンド サーバー プールと、サイト 2 に物理的に存在するバックアップ データベース。</span><span class="sxs-lookup"><span data-stu-id="aece8-146">A second Front End Server pool and a backup database residing physically on Site 2.</span></span>
    
- <span data-ttu-id="aece8-147">物理トポロジは、次のようにサイト 1 とサイト 2 で構成されます。</span><span class="sxs-lookup"><span data-stu-id="aece8-147">The physical topology consists of Sites 1 and 2 as follows:</span></span>
    
  - <span data-ttu-id="aece8-148">サイト 1 のサーバー 1 ~ 4、2 つのアクティブ、2 つのアイドル状態を含む常設チャット プール。</span><span class="sxs-lookup"><span data-stu-id="aece8-148">A Persistent Chat pool, containing servers 1 through 4, two active, two idle on Site 1.</span></span>
    
  - <span data-ttu-id="aece8-149">サイト 2 のサーバー 5 ~ 8、2 つのアクティブ、2 つのアイドル状態を含む常設チャット プール。</span><span class="sxs-lookup"><span data-stu-id="aece8-149">A Persistent Chat pool, containing servers 5 through 8, two active, two idle on Site 2.</span></span>
    
  - <span data-ttu-id="aece8-150">サイト 1 のフロントエンド サーバー プール、常設チャット データベース、ミラー 化されたデータベース、およびオプションで(図には示されていない) 監視データベース。</span><span class="sxs-lookup"><span data-stu-id="aece8-150">A Front End Server pool, a Persistent Chat database, a mirrored database, and, optionally, a witness database (not shown in diagram) on Site 1.</span></span>
    
  - <span data-ttu-id="aece8-151">サイト 2 のフロントエンド サーバー プールと、SQLのバックアップ データベース。</span><span class="sxs-lookup"><span data-stu-id="aece8-151">A Front End Server Pool, and a backup database, which is the SQL log shipping target, on Site 2.</span></span>
    
<span data-ttu-id="aece8-152">**データ センターが高帯域幅/低遅延の場所に位置する場合のストレッチド 常設チャット サーバー プール**</span><span class="sxs-lookup"><span data-stu-id="aece8-152">**Stretched Persistent Chat Server pool when data centers are geo-located with high bandwidth/low latency**</span></span>

![高帯域幅/低待機時間の常設チャット ストレッチド プール](../../media/55cf3d4b-5f51-4d2f-84ca-b4a13dc5eba3.png)
  
<span data-ttu-id="aece8-154">図 2 は、データ センターが低帯域幅/高待機時間で地理的に位置するストレッチド 常設チャット サーバー プール トポロジを示しています。</span><span class="sxs-lookup"><span data-stu-id="aece8-154">Figure 2 shows a stretched Persistent Chat Server pool topology where data centers are geo-located with low bandwidth/high latency.</span></span>
  
- <span data-ttu-id="aece8-155">論理トポロジは、次の要素で構成されます。</span><span class="sxs-lookup"><span data-stu-id="aece8-155">The logical topology consists of the following:</span></span>
    
  - <span data-ttu-id="aece8-156">サーバー 1 ~ 8 を含むサイト 1 とサイト 2 の常設チャット プール。</span><span class="sxs-lookup"><span data-stu-id="aece8-156">A Persistent Chat pool across Sites 1 and 2 containing servers 1 through 8.</span></span>
    
  - <span data-ttu-id="aece8-157">サイト 1 上に物理的に存在するフロントエンド サーバー プール、常設チャット データベース、ミラー 化データベース、および必要に応じて監視データベース (図には表示されません)。</span><span class="sxs-lookup"><span data-stu-id="aece8-157">A Front End Server pool, a Persistent Chat database, a mirrored database, and, optionally, a witness database (not shown in diagram) residing physically on Site 1.</span></span> 
    
  - <span data-ttu-id="aece8-158">2 番目のフロントエンド サーバー プールと、サイト 2 に物理的に存在するバックアップ データベース。</span><span class="sxs-lookup"><span data-stu-id="aece8-158">A second Front End Server pool and a backup database residing physically on Site 2.</span></span>
    
- <span data-ttu-id="aece8-159">物理トポロジは、次のようにサイト 1 とサイト 2 で構成されます。</span><span class="sxs-lookup"><span data-stu-id="aece8-159">The physical topology consists of Sites 1 and 2 as follows:</span></span>
    
  - <span data-ttu-id="aece8-160">サイト 1 上のサーバー 1 ~ 4 (すべてアクティブ) を含む常設チャット プール。</span><span class="sxs-lookup"><span data-stu-id="aece8-160">A Persistent Chat pool, containing servers 1 through 4, all active, on Site 1.</span></span>
    
  - <span data-ttu-id="aece8-161">サイト 2 上のサーバー 5 ~ 8 (すべてアイドル状態) を含む常設チャット プール。</span><span class="sxs-lookup"><span data-stu-id="aece8-161">A Persistent Chat pool, containing servers 5 through 8, all idle, on Site 2.</span></span>
    
  - <span data-ttu-id="aece8-162">サイト 1 のフロントエンド サーバー プール、常設チャット データベース、ミラー 化されたデータベース、およびオプションで(図には示されていない) 監視データベース。</span><span class="sxs-lookup"><span data-stu-id="aece8-162">A Front End Server pool, a Persistent Chat database, a mirrored database, and, optionally, a witness database (not shown in diagram) on Site 1.</span></span>
    
  - <span data-ttu-id="aece8-163">サイト 2 上のフロントエンド サーバー プールと、SQLログ配布の対象となるバックアップ データベース。</span><span class="sxs-lookup"><span data-stu-id="aece8-163">A Front End Server pool, and a backup database, which is the SQL log shipping target, on Site 2.</span></span>
    
<span data-ttu-id="aece8-164">**データ センターが低帯域幅/高待機時間で地理的に位置する場合のストレッチド 常設チャット サーバー プール**</span><span class="sxs-lookup"><span data-stu-id="aece8-164">**Stretched Persistent Chat Server pool when data centers are geo-located with low bandwidth/high latency**</span></span>

![低帯域幅/高待機時間の常設チャット ストレッチド プール](../../media/40cbd902-57b8-4d57-a61c-cde4e0bd47f0.png)
  

