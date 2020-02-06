---
title: Skype for Business Server 2015 の常設チャットサーバーの高可用性と障害復旧の計画
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 5/17/2016
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: d9aa622a-95a3-4d8e-8d49-cbfe183f25bf
description: '概要: このトピックでは、Skype for Business Server 2015 で常設チャットサーバーの高可用性と障害回復を計画する方法について説明します。'
ms.openlocfilehash: 08b025b09acc4b4db5f26ae67761412a96c0339c
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2020
ms.locfileid: "41815745"
---
# <a name="plan-for-high-availability-and-disaster-recovery-for-persistent-chat-server-in-skype-for-business-server-2015"></a><span data-ttu-id="94020-103">Skype for Business Server 2015 の常設チャットサーバーの高可用性と障害復旧の計画</span><span class="sxs-lookup"><span data-stu-id="94020-103">Plan for high availability and disaster recovery for Persistent Chat Server in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="94020-104">**概要:** このトピックでは、Skype for Business Server 2015 の常設チャットサーバーで高可用性と障害回復を計画する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="94020-104">**Summary:** Read this topic to learn how to plan for high availability and disaster recovery for Persistent Chat Server in Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="94020-105">常設チャットサーバーの高可用性と障害回復には、通常、完全な操作に必要なもの以外に追加のリソースが必要です。</span><span class="sxs-lookup"><span data-stu-id="94020-105">High availability and disaster recovery for Persistent Chat Server require additional resources beyond what is typically needed for full operation.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="94020-106">常設チャット サーバー データベースで SQL AlwaysOn 可用性グループを使用することは、サポートされていません。</span><span class="sxs-lookup"><span data-stu-id="94020-106">Using SQL AlwaysOn Availability Groups is not supported with Persistent Chat Server databases.</span></span> 

> [!NOTE] 
> <span data-ttu-id="94020-107">常設チャットは Skype for Business Server 2015 で使用できますが、Skype for Business Server 2019 ではサポートされなくなりました。</span><span class="sxs-lookup"><span data-stu-id="94020-107">Persistent chat is available in Skype for Business Server 2015 but is no longer supported in Skype for Business Server 2019.</span></span> <span data-ttu-id="94020-108">Teams でも同じ機能を使用できます。</span><span class="sxs-lookup"><span data-stu-id="94020-108">The same functionality is available in Teams.</span></span> <span data-ttu-id="94020-109">詳細については、「 [Microsoft Teams のアップグレードの](/microsoftteams/upgrade-start-here)概要」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="94020-109">For more information, see [Getting started with your Microsoft Teams upgrade](/microsoftteams/upgrade-start-here).</span></span> <span data-ttu-id="94020-110">常設チャットを使用する必要がある場合は、この機能が必要なユーザーをチームに移行するか、Skype for Business Server 2015 を使い続けるかのいずれかを選択できます。</span><span class="sxs-lookup"><span data-stu-id="94020-110">If you need to use Persistent chat, your choices are to either migrate users requiring this functionality to Teams, or to continue using Skype for Business Server 2015.</span></span> 
  
## <a name="resource-requirements"></a><span data-ttu-id="94020-111">リソースの要件</span><span class="sxs-lookup"><span data-stu-id="94020-111">Resource requirements</span></span>

<span data-ttu-id="94020-112">高可用性と障害回復のために常設チャットサーバーを構成する前に、次の追加のリソースがあることを確認します。</span><span class="sxs-lookup"><span data-stu-id="94020-112">Before configuring Persistent Chat Server for high availability and disaster recovery, ensure that you have the following additional resources.</span></span> 
  
- <span data-ttu-id="94020-113">常設チャットサーバーサービスのホームフロントエンドが存在する同じ物理データセンターに、1つの専用データベースインスタンスがあります。</span><span class="sxs-lookup"><span data-stu-id="94020-113">One dedicated database instance located in the same physical data center in which the home front end of the Persistent Chat Server service is located.</span></span> <span data-ttu-id="94020-114">このデータベースは、プライマリ常設チャットデータベースの SQL Server mirror として機能します。</span><span class="sxs-lookup"><span data-stu-id="94020-114">This database will serve as the SQL Server mirror for the primary Persistent Chat database.</span></span> <span data-ttu-id="94020-115">必要に応じて、ミラーデータベースへの自動フェールオーバーが必要な場合は、ミラーリング監視として機能する追加の SQL Server を指定します。</span><span class="sxs-lookup"><span data-stu-id="94020-115">Optionally, designate an additional SQL Server to serve as the mirroring witness if you want an automated failover to the mirror database.</span></span>
    
- <span data-ttu-id="94020-116">他の物理データ センターに存在する、1 つの専用データベース インスタンス。</span><span class="sxs-lookup"><span data-stu-id="94020-116">One dedicated database instance located in the other physical data center.</span></span> <span data-ttu-id="94020-117">このデータベースは、プライマリデータセンターのデータベースの SQL Server Log 配布セカンダリデータベースとして機能します。</span><span class="sxs-lookup"><span data-stu-id="94020-117">This database will serve as the SQL Server Log Shipping secondary database for the database in the primary data center.</span></span>
    
- <span data-ttu-id="94020-118">セカンダリデータベースの SQL Server ミラーとして機能する1つの専用データベースインスタンス。</span><span class="sxs-lookup"><span data-stu-id="94020-118">One dedicated database instance to serve as the SQL Server mirror for the secondary database.</span></span> <span data-ttu-id="94020-119">必要に応じて、ミラーリング監視として追加の SQL Server をサーバーに指定します。</span><span class="sxs-lookup"><span data-stu-id="94020-119">Optionally, designate an additional SQL Server to server as the mirroring witness.</span></span> <span data-ttu-id="94020-120">どちらもセカンダリ データベースと同じ物理データ センターに存在する必要があります。</span><span class="sxs-lookup"><span data-stu-id="94020-120">Both of these must be located in the same physical data center as the secondary database.</span></span>
    
- <span data-ttu-id="94020-121">常設チャットサーバーのコンプライアンスが有効になっている場合は、3つの専用データベースインスタンスが必要になります。</span><span class="sxs-lookup"><span data-stu-id="94020-121">If Persistent Chat Server compliance is enabled, an additional three dedicated database instances are required.</span></span> <span data-ttu-id="94020-122">これらの配布は、常設チャットデータベースで前に説明したものと同じです。</span><span class="sxs-lookup"><span data-stu-id="94020-122">Their distribution is the same as those previously outlined for the Persistent Chat database.</span></span> <span data-ttu-id="94020-123">コンプライアンスデータベースは、永続的なチャットデータベースと同じ SQL Server インスタンスを共有できますが、高可用性と障害回復のためのスタンドアロンインスタンスを使用することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="94020-123">While it is possible for the compliance database to share the same SQL Server instance as the Persistent Chat database, standalone instances for high availability and disaster recovery are recommended.</span></span>
    
- <span data-ttu-id="94020-124">ファイル共有を作成し、SQL Server のログ配布トランザクションログに指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="94020-124">A file share must be created and designated for the SQL Server Log Shipping transaction logs.</span></span> <span data-ttu-id="94020-125">常設チャットデータベースを実行する両方のデータセンターにあるすべての SQL Server は、このファイル共有に対する読み取り/書き込みアクセス権を持っている必要があります。</span><span class="sxs-lookup"><span data-stu-id="94020-125">All SQL Servers in both data centers that run Persistent Chat databases must have read/write access to this file share.</span></span> <span data-ttu-id="94020-126">この共有は、FileStore 役割の一部としては定義されません。</span><span class="sxs-lookup"><span data-stu-id="94020-126">This share is not defined as part of a FileStore role.</span></span>
    
- <span data-ttu-id="94020-127">セカンダリデータベースサーバー上のファイル共有は、プライマリサーバーファイル共有からコピーした SQL Server トランザクションログの移動先フォルダーとして機能します。</span><span class="sxs-lookup"><span data-stu-id="94020-127">A file share on the secondary database server to serve as the destination folder for the SQL Server transaction logs that are copied from the primary server file share.</span></span>
    
## <a name="disaster-recovery-and-high-availability-solutions"></a><span data-ttu-id="94020-128">障害復旧と高可用性のソリューション</span><span class="sxs-lookup"><span data-stu-id="94020-128">Disaster recovery and high availability solutions</span></span>

<span data-ttu-id="94020-129">Skype for Business Server では、データベースミラーリングなど、バックエンドサーバーでの高可用性の複数のモードがサポートされています。</span><span class="sxs-lookup"><span data-stu-id="94020-129">Skype for Business Server supports multiple modes of high availability for your Back End Servers, including database mirroring.</span></span> <span data-ttu-id="94020-130">詳細については、「[Plan for high availability and disaster recovery in Skype for Business Server 2015](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="94020-130">For more information, see [Plan for high availability and disaster recovery in Skype for Business Server 2015](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md).</span></span> 
  
<span data-ttu-id="94020-131">このトピックで説明されている常設チャットサーバーの障害回復ソリューションは、ストレッチ型の常設チャットサーバープールに基づいています。</span><span class="sxs-lookup"><span data-stu-id="94020-131">The disaster recovery solution for Persistent Chat Server described in this topic is built on a stretched Persistent Chat Server pool.</span></span> <span data-ttu-id="94020-132">拡張型の仮想ローカル エリア ネットワーク (VLAN) に関する要件はありません。</span><span class="sxs-lookup"><span data-stu-id="94020-132">There is no requirement for a stretched virtual local area network (VLAN).</span></span> <span data-ttu-id="94020-133">常設チャットサーバープールを拡大することによって、トポロジ内の1つのプールを論理的に構成しますが、プール内にはサーバーを物理的に2つの異なるデータセンターに配置します。</span><span class="sxs-lookup"><span data-stu-id="94020-133">By stretching a Persistent Chat Server pool, you configure one pool in the topology logically, but you physically place the servers in the pool in two different data centers.</span></span> <span data-ttu-id="94020-134">データベースの SQL Server ミラーリングを同じ方法で構成し、データベースとそのミラーを同じデータ センター内に展開します。</span><span class="sxs-lookup"><span data-stu-id="94020-134">You configure SQL Server mirroring for the database in the same way, and deploy the database and the mirror in the same data center.</span></span> <span data-ttu-id="94020-135">セカンダリ データ センターでは、(障害復旧時に高可用性を提供するためにオプションのミラーを使用して) バックアップ データベースを構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="94020-135">You need to configure a backup database in the secondary data center (with an optional mirror to provide high availability during disaster recovery).</span></span> <span data-ttu-id="94020-136">これは、障害復旧時にフェールオーバー用に使用されるバックアップ データベースです。</span><span class="sxs-lookup"><span data-stu-id="94020-136">This is the backup database used for failover during disaster recovery.</span></span> 
  
<span data-ttu-id="94020-137">常設チャットサーバーの高可用性と障害回復を構成する方法の詳細については、「 [Skype For Business server 2015 の常設チャットサーバーの高可用性と障害回復を構成](../../deploy/deploy-persistent-chat-server/configure-hadr-for-persistent-chat.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="94020-137">For details about how to configure high availability and disaster recovery for Persistent Chat Server, see [Configure high availability and disaster recovery for Persistent Chat Server in Skype for Business Server 2015](../../deploy/deploy-persistent-chat-server/configure-hadr-for-persistent-chat.md).</span></span> 
  
<span data-ttu-id="94020-138">次の図は、2つの異なるストレッチプールトポロジで常設チャットサーバープールを構成する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="94020-138">The following figures show how the Persistent Chat Server pool can be configured in two different stretched pool topologies:</span></span>
  
- <span data-ttu-id="94020-139">帯域幅が高く、待機時間が短い場合、データセンターが地理的な位置にある場合は、常設チャットサーバープールが拡張されます。</span><span class="sxs-lookup"><span data-stu-id="94020-139">Stretched Persistent Chat Server pool when data centers are geo-located with high bandwidth/low latency.</span></span>
    
- <span data-ttu-id="94020-140">データセンターが低帯域幅または長い待ち時間で配置されている場合は、常設チャットサーバープールが拡張されます。</span><span class="sxs-lookup"><span data-stu-id="94020-140">Stretched Persistent Chat Server pool when data centers are geo-located with low bandwidth/high latency.</span></span>
    
<span data-ttu-id="94020-141">図1は、高帯域幅/低レイテンシでデータセンターが地理的に配置されている、拡大型の常設チャットサーバープールトポロジを示しています。</span><span class="sxs-lookup"><span data-stu-id="94020-141">Figure 1 shows a stretched Persistent Chat Server pool topology where data centers are geo-located with high bandwidth/low latency.</span></span> <span data-ttu-id="94020-142">論理トポロジと物理トポロジについては、次のことを前提とします。</span><span class="sxs-lookup"><span data-stu-id="94020-142">Assume the following for the logical and physical topologies:</span></span>
  
- <span data-ttu-id="94020-143">論理トポロジは次の構成です。</span><span class="sxs-lookup"><span data-stu-id="94020-143">The logical topology consists of the following:</span></span>
    
  - <span data-ttu-id="94020-144">サーバー 1 ～ 8 を含む、サイト 1 および 2 にまたがる常設チャット プール。</span><span class="sxs-lookup"><span data-stu-id="94020-144">A Persistent Chat pool across Sites 1 and 2 containing servers 1 through 8.</span></span>
    
  - <span data-ttu-id="94020-145">フロントエンドサーバープール、常設チャットデータベース、ミラーデータベース、必要に応じて、サイト1の物理的な監視データベース (図には表示されません)。</span><span class="sxs-lookup"><span data-stu-id="94020-145">A Front End Server pool, a Persistent Chat database, a mirrored database, and, optionally, a witness database (not shown in diagram) residing physically on Site 1.</span></span> 
    
  - <span data-ttu-id="94020-146">サイト 2 上に物理的に存在する、2 つ目のフロントエンド サーバー プールと、バックアップ データベース。</span><span class="sxs-lookup"><span data-stu-id="94020-146">A second Front End Server pool and a backup database residing physically on Site 2.</span></span>
    
- <span data-ttu-id="94020-147">物理トポロジは、次のようにサイト1と2で構成されます。</span><span class="sxs-lookup"><span data-stu-id="94020-147">The physical topology consists of Sites 1 and 2 as follows:</span></span>
    
  - <span data-ttu-id="94020-148">サイト 1 上に、サーバー 1 ～ 4 (2 台がアクティブで 2 台がアイドル) が含まれる常設チャット プール。</span><span class="sxs-lookup"><span data-stu-id="94020-148">A Persistent Chat pool, containing servers 1 through 4, two active, two idle on Site 1.</span></span>
    
  - <span data-ttu-id="94020-149">サイト 5 上に、サーバー 2 ～ 8 (2 台がアクティブで 2 台がアイドル) が含まれる常設チャット プール。</span><span class="sxs-lookup"><span data-stu-id="94020-149">A Persistent Chat pool, containing servers 5 through 8, two active, two idle on Site 2.</span></span>
    
  - <span data-ttu-id="94020-150">フロントエンドサーバープール、常設チャットデータベース、ミラーデータベース、オプションとして、サイト1の監視データベース (図には表示されません)。</span><span class="sxs-lookup"><span data-stu-id="94020-150">A Front End Server pool, a Persistent Chat database, a mirrored database, and, optionally, a witness database (not shown in diagram) on Site 1.</span></span>
    
  - <span data-ttu-id="94020-151">サイト 2 上に、フロントエンド サーバー プールと、SQL ログ配布のターゲットであるバックアップ データベース。</span><span class="sxs-lookup"><span data-stu-id="94020-151">A Front End Server Pool, and a backup database, which is the SQL log shipping target, on Site 2.</span></span>
    
<span data-ttu-id="94020-152">**データ センターが高帯域幅/低遅延の場所に設置されている場合の拡張常設チャット サーバー プール**</span><span class="sxs-lookup"><span data-stu-id="94020-152">**Stretched Persistent Chat Server pool when data centers are geo-located with high bandwidth/low latency**</span></span>

![高帯域幅/低遅延の常設チャット用に拡張されたプール](../../media/55cf3d4b-5f51-4d2f-84ca-b4a13dc5eba3.png)
  
<span data-ttu-id="94020-154">図2は、帯域幅が少なく、待機時間が長い、データセンターが地理的に配置されている、ストレッチ型の常設チャットサーバープールトポロジを示しています。</span><span class="sxs-lookup"><span data-stu-id="94020-154">Figure 2 shows a stretched Persistent Chat Server pool topology where data centers are geo-located with low bandwidth/high latency.</span></span>
  
- <span data-ttu-id="94020-155">論理トポロジは次の構成です。</span><span class="sxs-lookup"><span data-stu-id="94020-155">The logical topology consists of the following:</span></span>
    
  - <span data-ttu-id="94020-156">サーバー 1 ～ 8 を含む、サイト 1 および 2 にまたがる常設チャット プール。</span><span class="sxs-lookup"><span data-stu-id="94020-156">A Persistent Chat pool across Sites 1 and 2 containing servers 1 through 8.</span></span>
    
  - <span data-ttu-id="94020-157">フロントエンドサーバープール、常設チャットデータベース、ミラーデータベース、必要に応じて、サイト1の物理的な監視データベース (図には表示されません)。</span><span class="sxs-lookup"><span data-stu-id="94020-157">A Front End Server pool, a Persistent Chat database, a mirrored database, and, optionally, a witness database (not shown in diagram) residing physically on Site 1.</span></span> 
    
  - <span data-ttu-id="94020-158">サイト 2 上に物理的に存在する、2 つ目のフロントエンド サーバー プールと、バックアップ データベース。</span><span class="sxs-lookup"><span data-stu-id="94020-158">A second Front End Server pool and a backup database residing physically on Site 2.</span></span>
    
- <span data-ttu-id="94020-159">物理トポロジは、次のようにサイト1と2で構成されます。</span><span class="sxs-lookup"><span data-stu-id="94020-159">The physical topology consists of Sites 1 and 2 as follows:</span></span>
    
  - <span data-ttu-id="94020-160">サイト 1 上に、サーバー 1 ～ 4 (すべてアクティブ) が含まれる常設チャット プール。</span><span class="sxs-lookup"><span data-stu-id="94020-160">A Persistent Chat pool, containing servers 1 through 4, all active, on Site 1.</span></span>
    
  - <span data-ttu-id="94020-161">サイト 2 上に、サーバー 5 ～ 8 (すべてアイドル) が含まれる常設チャット プール。</span><span class="sxs-lookup"><span data-stu-id="94020-161">A Persistent Chat pool, containing servers 5 through 8, all idle, on Site 2.</span></span>
    
  - <span data-ttu-id="94020-162">フロントエンドサーバープール、常設チャットデータベース、ミラーデータベース、オプションとして、サイト1の監視データベース (図には表示されません)。</span><span class="sxs-lookup"><span data-stu-id="94020-162">A Front End Server pool, a Persistent Chat database, a mirrored database, and, optionally, a witness database (not shown in diagram) on Site 1.</span></span>
    
  - <span data-ttu-id="94020-163">サイト 2 上に、フロントエンド サーバー プールと、SQL ログ配布のターゲットであるバックアップ データベース。</span><span class="sxs-lookup"><span data-stu-id="94020-163">A Front End Server pool, and a backup database, which is the SQL log shipping target, on Site 2.</span></span>
    
<span data-ttu-id="94020-164">**データ センターが低帯域幅/高遅延の場所に設置されている場合の拡張常設チャット サーバー プール**</span><span class="sxs-lookup"><span data-stu-id="94020-164">**Stretched Persistent Chat Server pool when data centers are geo-located with low bandwidth/high latency**</span></span>

![低帯域幅/高遅延の常設チャット用に拡張されたプール](../../media/40cbd902-57b8-4d57-a61c-cde4e0bd47f0.png)
  

