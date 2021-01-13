---
title: Skype for Business Server で高可用性と障害復旧を計画する
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.custom:
- ms.lync.plan.HighAvailabilityType
ms.prod: skype-for-business-itpro
f1.keywords:
- CSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 3543eb40-54f4-49ef-a058-03aceed4773a
description: Skype for Business Server は、サーバー プールでの高可用性、プールペアリングによる障害復旧、および AlwaysOn 可用性グループ、データベース ミラーリング、SQL フェールオーバー クラスタリングなど、いくつかのモードのバック エンド サーバー高可用性を提供します。
ms.openlocfilehash: 61b720bc9dce5bc8dc54a6c493429b0a3c9b27d2
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49802817"
---
# <a name="plan-for-high-availability-and-disaster-recovery-in-skype-for-business-server"></a><span data-ttu-id="d891a-103">Skype for Business Server で高可用性と障害復旧を計画する</span><span class="sxs-lookup"><span data-stu-id="d891a-103">Plan for high availability and disaster recovery in Skype for Business Server</span></span>
 
<span data-ttu-id="d891a-104">Skype for Business Server は、サーバー プールでの高可用性、プールペアリングによる障害復旧、および AlwaysOn 可用性グループ、データベース ミラーリング、SQL フェールオーバー クラスタリングなど、いくつかのモードのバック エンド サーバー高可用性を提供します。</span><span class="sxs-lookup"><span data-stu-id="d891a-104">Skype for Business Server offers high availability with server pooling, disaster recovery with pool pairing, and several modes of Back End Server high availability, including AlwaysOn Availability groups, database mirroring, and SQL failover clustering.</span></span> 
  
<span data-ttu-id="d891a-105">高可用性とは、1 つ以上のサーバーがダウンした場合でも、Skype for Business Server サービスを確実に利用できる状態を指します。</span><span class="sxs-lookup"><span data-stu-id="d891a-105">High availability refers to making sure that Skype for Business Server services are available even if one or more servers goes down.</span></span> <span data-ttu-id="d891a-106">障害復旧とは、自然または人が引き起こした障害が発生した場合にサービスを維持し、災害前からのデータをできる限り多く保持することです。</span><span class="sxs-lookup"><span data-stu-id="d891a-106">Disaster recovery refers to keeping services going in the event of a natural or human-caused disaster, and preserving as much data from before the disaster as possible.</span></span>
  
<span data-ttu-id="d891a-107">以前のバージョンの Lync Server と同様に、Skype for Business Server のほとんどのサーバーの役割の主な高可用性機能は、プールによるサーバーの冗長性です。</span><span class="sxs-lookup"><span data-stu-id="d891a-107">As in previous versions of Lync Server, the main high availability feature for most server roles in Skype for Business Server is server redundancy via pooling.</span></span> <span data-ttu-id="d891a-108">あるサーバーの役割を実行しているサーバーが失敗すると、プール内で同じサーバーの役割を実行している別のサーバーがそのサーバーの負荷を引き継ぎます。</span><span class="sxs-lookup"><span data-stu-id="d891a-108">If a server running a certain server role fails, the other servers in the pool running the same role take the load of that server.</span></span> <span data-ttu-id="d891a-109">これはフロントエンド サーバー、エッジ サーバー、仲介サーバー、およびディレクターに適用されます。</span><span class="sxs-lookup"><span data-stu-id="d891a-109">This applies to Front End Servers, Edge Servers, Mediation Servers, and Directors.</span></span>
  
<span data-ttu-id="d891a-110">Skype for Business Server には、フロントエンド プールの障害復旧オプションも用意されています。</span><span class="sxs-lookup"><span data-stu-id="d891a-110">Skype for Business Server also provides disaster recovery options for Front End pools.</span></span> <span data-ttu-id="d891a-111">地理的に異なる地域に 2 つのプールを設定して、互いにバックアップとして機能することができます。</span><span class="sxs-lookup"><span data-stu-id="d891a-111">You can set up two pools in different geographical areas to serve as backups for each other.</span></span> <span data-ttu-id="d891a-112">その後、プールまたはサイト全体がダウンした場合でも、バックアップ プールは両方のサイトのユーザーにサービスを提供し続ける可能性があります。</span><span class="sxs-lookup"><span data-stu-id="d891a-112">Then if you have an entire pool or site go down, the backup pool can continue to provide service to users at both sites.</span></span>
  
<span data-ttu-id="d891a-113">また、Skype for Business Server は、SQL ミラーリング、AlwaysOn 可用性グループ、AlwaysOn フェールオーバー クラスター インスタンス (FCI)、および SQL フェールオーバー クラスタリングという 4 つのモードの高可用性をサポートしています。</span><span class="sxs-lookup"><span data-stu-id="d891a-113">Skype for Business Server also supports four modes of high availability for your Back End Servers: SQL mirroring, AlwaysOn Availability Groups, AlwaysOn Failover Cluster Instances (FCI), and SQL failover clustering.</span></span>
  
> [!NOTE]
> <span data-ttu-id="d891a-114">SQLミラーリングは Skype for Business Server 2015 で使用できますが、Skype for Business Server 2019 ではサポートされなくなりました。</span><span class="sxs-lookup"><span data-stu-id="d891a-114">SQL Mirroring is available in Skype for Business Server 2015 but is no longer supported in Skype for Business Server 2019.</span></span> <span data-ttu-id="d891a-115">Skype for Business Server 2019 では、AlwaysOn 可用性グループ、AlwaysOn フェールオーバー クラスター インスタンス (FCI)、および SQL フェールオーバー クラスタリングの方法が優先されます。</span><span class="sxs-lookup"><span data-stu-id="d891a-115">The  AlwaysOn Availability Groups, AlwaysOn Failover Cluster Instances (FCI), and SQL failover clustering methods are preferred with Skype for Business Server 2019.</span></span>

> [!NOTE]
> <span data-ttu-id="d891a-116">AlwaysOn 可用性グループは、常設チャット サーバーではサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="d891a-116">AlwaysOn Availability Groups are not supported with Persistent Chat Servers.</span></span> 
  
<span data-ttu-id="d891a-117">このセクションでは、これらの機能について説明します。また、他のサーバーの役割の一部に対して、高可用性と障害復旧のために実行できる手順も説明します。</span><span class="sxs-lookup"><span data-stu-id="d891a-117">This section explains these features, and also covers what steps you can take for high availability and disaster recovery for some of your other server roles.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="d891a-118">関連項目</span><span class="sxs-lookup"><span data-stu-id="d891a-118">See also</span></span>

[<span data-ttu-id="d891a-119">フロントエンド プールの高可用性と管理</span><span class="sxs-lookup"><span data-stu-id="d891a-119">Front End Pool high availability and management</span></span>](high-availability.md)
  
[<span data-ttu-id="d891a-120">Skype for Business Server でのフロントエンド プールの障害復旧</span><span class="sxs-lookup"><span data-stu-id="d891a-120">Front End pool disaster recovery in Skype for Business Server</span></span>](disaster-recovery.md)
  
[<span data-ttu-id="d891a-121">Skype for Business Server でのプール障害時のユーザー エクスペリエンス</span><span class="sxs-lookup"><span data-stu-id="d891a-121">User experience during pool failure in Skype for Business Server</span></span>](user-experience.md)
  
[<span data-ttu-id="d891a-122">Skype for Business Server でのバック エンド サーバーの高可用性</span><span class="sxs-lookup"><span data-stu-id="d891a-122">Back End Server high availability in Skype for Business Server</span></span>](back-end-server.md)
  
[<span data-ttu-id="d891a-123">Skype for Business Server でのファイル共有の高可用性</span><span class="sxs-lookup"><span data-stu-id="d891a-123">File sharing high availability in Skype for Business Server</span></span>](file-sharing.md)
