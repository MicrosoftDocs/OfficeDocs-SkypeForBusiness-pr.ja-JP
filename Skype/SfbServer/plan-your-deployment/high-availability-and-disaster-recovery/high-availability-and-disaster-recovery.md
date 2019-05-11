---
title: ビジネスのサーバーに、Skype での高可用性と災害復旧を計画します。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: conceptual
f1_keywords:
- ms.lync.plan.HighAvailabilityType
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 3543eb40-54f4-49ef-a058-03aceed4773a
description: Skype ビジネス サーバーのサーバーのプール、プールの組み合わせ、およびバック エンド サーバーの高可用性、AlwaysOn 可用性グループ、データベース ミラーリングは、SQL フェールオーバー クラスタ リングなどのいくつかのモードでの災害復旧と高可用性を提供します。
ms.openlocfilehash: 8ab0d41b93a47782fce4a44acf1e8305a9ad13e1
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "33910334"
---
# <a name="plan-for-high-availability-and-disaster-recovery-in-skype-for-business-server"></a><span data-ttu-id="5ed8a-103">ビジネスのサーバーに、Skype での高可用性と災害復旧を計画します。</span><span class="sxs-lookup"><span data-stu-id="5ed8a-103">Plan for high availability and disaster recovery in Skype for Business Server</span></span>
 
<span data-ttu-id="5ed8a-104">Skype ビジネス サーバーのサーバーのプール、プールの組み合わせ、およびバック エンド サーバーの高可用性、AlwaysOn 可用性グループ、データベース ミラーリングは、SQL フェールオーバー クラスタ リングなどのいくつかのモードでの災害復旧と高可用性を提供します。</span><span class="sxs-lookup"><span data-stu-id="5ed8a-104">Skype for Business Server offers high availability with server pooling, disaster recovery with pool pairing, and several modes of Back End Server high availability, including AlwaysOn Availability groups, database mirroring, and SQL failover clustering.</span></span> 
  
<span data-ttu-id="5ed8a-105">高可用性は、1 つまたは複数のサーバーがダウンした場合でも、ビジネス サーバー サービスの Skype が利用可能であることを確認することを指します。</span><span class="sxs-lookup"><span data-stu-id="5ed8a-105">High availability refers to making sure that Skype for Business Server services are available even if one or more servers goes down.</span></span> <span data-ttu-id="5ed8a-106">Disaster recovery refers to keeping services going in the event of a natural or human-caused disaster, and preserving as much data from before the disaster as possible.</span><span class="sxs-lookup"><span data-stu-id="5ed8a-106">Disaster recovery refers to keeping services going in the event of a natural or human-caused disaster, and preserving as much data from before the disaster as possible.</span></span>
  
<span data-ttu-id="5ed8a-107">Lync Server の以前のバージョンのように Skype ビジネス サーバー用のほとんどのサーバーの役割の主な高可用性機能はプールを使用してサーバーの冗長性</span><span class="sxs-lookup"><span data-stu-id="5ed8a-107">As in previous versions of Lync Server, the main high availability feature for most server roles in Skype for Business Server is server redundancy via pooling.</span></span> <span data-ttu-id="5ed8a-108">特定のサーバーの役割を実行するサーバーで障害が発生した場合は、プール内の同じ役割を実行する他のサーバーがそのサーバーの負荷を引き受けます。</span><span class="sxs-lookup"><span data-stu-id="5ed8a-108">If a server running a certain server role fails, the other servers in the pool running the same role take the load of that server.</span></span> <span data-ttu-id="5ed8a-109">同じことが、フロントエンド サーバー、エッジ サーバー、仲介サーバー、およびディレクターでも実行されます。</span><span class="sxs-lookup"><span data-stu-id="5ed8a-109">This applies to Front End Servers, Edge Servers, Mediation Servers, and Directors.</span></span>
  
<span data-ttu-id="5ed8a-110">ビジネス サーバーの Skype は、リカバリ ・ オプションのフロント エンド プールの障害も提供します。</span><span class="sxs-lookup"><span data-stu-id="5ed8a-110">Skype for Business Server also provides disaster recovery options for Front End pools.</span></span> <span data-ttu-id="5ed8a-111">互いのバックアップとして機能するように、2 つのプールを別々の地理的地域にセットアップできます。</span><span class="sxs-lookup"><span data-stu-id="5ed8a-111">You can set up two pools in different geographical areas to serve as backups for each other.</span></span> <span data-ttu-id="5ed8a-112">これによって、プールまたはサイト全体を停止させた場合に、バックアップ プールが両方のサイトのユーザーにサービスを継続して提供できます。</span><span class="sxs-lookup"><span data-stu-id="5ed8a-112">Then if you have an entire pool or site go down, the backup pool can continue to provide service to users at both sites.</span></span>
  
<span data-ttu-id="5ed8a-113">Skype ビジネス サーバーのでは、バック エンド サーバーの高可用性の 4 つのモードもがサポートされています: SQL のミラーリング、AlwaysOn 可用性グループ、AlwaysOn フェールオーバー クラスター インスタンス (FCI)、および SQL フェールオーバー クラスタ リングします。</span><span class="sxs-lookup"><span data-stu-id="5ed8a-113">Skype for Business Server also supports four modes of high availability for your Back End Servers: SQL mirroring, AlwaysOn Availability Groups, AlwaysOn Failover Cluster Instances (FCI), and SQL failover clustering.</span></span>
  
> [!NOTE]
> <span data-ttu-id="5ed8a-114">SQL ミラーリング ビジネス サーバー 2015 の Skype で利用できるが、ビジネス サーバー 2019 の Skype でサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="5ed8a-114">SQL Mirroring is available in Skype for Business Server 2015 but is no longer supported in Skype for Business Server 2019.</span></span> <span data-ttu-id="5ed8a-115">AlwaysOn 可用性グループ、AlwaysOn フェールオーバー クラスター インスタンス (FCI)、および SQL フェールオーバー クラスタ リング手法は、ビジネス サーバー 2019 の Skype で優先します。</span><span class="sxs-lookup"><span data-stu-id="5ed8a-115">The  AlwaysOn Availability Groups, AlwaysOn Failover Cluster Instances (FCI), and SQL failover clustering methods are preferred with Skype for Business Server 2019.</span></span>

> [!NOTE]
> <span data-ttu-id="5ed8a-116">AlwaysOn 可用性グループは、永続的なチャット サーバーではサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="5ed8a-116">AlwaysOn Availability Groups are not supported with Persistent Chat Servers.</span></span> 
  
<span data-ttu-id="5ed8a-117">このセクションでは、これらの機能について説明し、別のサーバーの役割のいくつかに対する高可用性と障害復旧に使用できる手順を取り上げます。</span><span class="sxs-lookup"><span data-stu-id="5ed8a-117">This section explains these features, and also covers what steps you can take for high availability and disaster recovery for some of your other server roles.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="5ed8a-118">関連項目</span><span class="sxs-lookup"><span data-stu-id="5ed8a-118">See also</span></span>

[<span data-ttu-id="5ed8a-119">フロントエンド プールの高可用性と管理</span><span class="sxs-lookup"><span data-stu-id="5ed8a-119">Front End Pool high availability and management</span></span>](high-availability.md)
  
[<span data-ttu-id="5ed8a-120">ビジネス サーバーの前面の Skype で最後のプール災害復旧</span><span class="sxs-lookup"><span data-stu-id="5ed8a-120">Front End pool disaster recovery in Skype for Business Server</span></span>](disaster-recovery.md)
  
[<span data-ttu-id="5ed8a-121">Skype でプールの障害発生時にビジネス サーバー用のユーザー エクスペリエンス</span><span class="sxs-lookup"><span data-stu-id="5ed8a-121">User experience during pool failure in Skype for Business Server</span></span>](user-experience.md)
  
[<span data-ttu-id="5ed8a-122">Skype の最後のサーバーの高可用性をビジネスのサーバーのバックアップします。</span><span class="sxs-lookup"><span data-stu-id="5ed8a-122">Back End Server high availability in Skype for Business Server</span></span>](back-end-server.md)
  
[<span data-ttu-id="5ed8a-123">Skype で高可用性をビジネス サーバーの共有ファイル</span><span class="sxs-lookup"><span data-stu-id="5ed8a-123">File sharing high availability in Skype for Business Server</span></span>](file-sharing.md)
