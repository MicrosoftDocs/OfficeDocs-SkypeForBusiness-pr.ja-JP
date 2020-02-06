---
title: Skype for Business Server で高可用性と障害回復を計画する
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
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
description: Skype for Business Server は、サーバーのプーリング、プールペアリングを使用した障害回復、および AlwaysOn 可用性グループ、データベースのミラーリング、SQL フェールオーバークラスタリングなど、バックエンドサーバーの高可用性の複数のモードを備えた高可用性機能を提供します。
ms.openlocfilehash: 521ddaa9878ba660e509f248d2f2ffb944608d87
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2020
ms.locfileid: "41815925"
---
# <a name="plan-for-high-availability-and-disaster-recovery-in-skype-for-business-server"></a><span data-ttu-id="1c2ef-103">Skype for Business Server で高可用性と障害回復を計画する</span><span class="sxs-lookup"><span data-stu-id="1c2ef-103">Plan for high availability and disaster recovery in Skype for Business Server</span></span>
 
<span data-ttu-id="1c2ef-104">Skype for Business Server は、サーバーのプーリング、プールペアリングを使用した障害回復、および AlwaysOn 可用性グループ、データベースのミラーリング、SQL フェールオーバークラスタリングなど、バックエンドサーバーの高可用性の複数のモードを備えた高可用性機能を提供します。</span><span class="sxs-lookup"><span data-stu-id="1c2ef-104">Skype for Business Server offers high availability with server pooling, disaster recovery with pool pairing, and several modes of Back End Server high availability, including AlwaysOn Availability groups, database mirroring, and SQL failover clustering.</span></span> 
  
<span data-ttu-id="1c2ef-105">高可用性とは、1つまたは複数のサーバーが停止した場合でも、Skype for Business Server サービスが利用可能であることを確認することを意味します。</span><span class="sxs-lookup"><span data-stu-id="1c2ef-105">High availability refers to making sure that Skype for Business Server services are available even if one or more servers goes down.</span></span> <span data-ttu-id="1c2ef-106">Disaster recovery refers to keeping services going in the event of a natural or human-caused disaster, and preserving as much data from before the disaster as possible.</span><span class="sxs-lookup"><span data-stu-id="1c2ef-106">Disaster recovery refers to keeping services going in the event of a natural or human-caused disaster, and preserving as much data from before the disaster as possible.</span></span>
  
<span data-ttu-id="1c2ef-107">以前のバージョンの Lync Server と同じように、Skype for Business Server のほとんどのサーバーの役割について、高可用性の主な機能は、プールによるサーバーの冗長性です。</span><span class="sxs-lookup"><span data-stu-id="1c2ef-107">As in previous versions of Lync Server, the main high availability feature for most server roles in Skype for Business Server is server redundancy via pooling.</span></span> <span data-ttu-id="1c2ef-108">特定のサーバーの役割を実行するサーバーで障害が発生した場合は、プール内の同じ役割を実行する他のサーバーがそのサーバーの負荷を引き受けます。</span><span class="sxs-lookup"><span data-stu-id="1c2ef-108">If a server running a certain server role fails, the other servers in the pool running the same role take the load of that server.</span></span> <span data-ttu-id="1c2ef-109">同じことが、フロントエンド サーバー、エッジ サーバー、仲介サーバー、およびディレクターでも実行されます。</span><span class="sxs-lookup"><span data-stu-id="1c2ef-109">This applies to Front End Servers, Edge Servers, Mediation Servers, and Directors.</span></span>
  
<span data-ttu-id="1c2ef-110">Skype for Business Server では、フロントエンドプールの障害回復オプションも提供されています。</span><span class="sxs-lookup"><span data-stu-id="1c2ef-110">Skype for Business Server also provides disaster recovery options for Front End pools.</span></span> <span data-ttu-id="1c2ef-111">互いのバックアップとして機能するように、2 つのプールを別々の地理的地域にセットアップできます。</span><span class="sxs-lookup"><span data-stu-id="1c2ef-111">You can set up two pools in different geographical areas to serve as backups for each other.</span></span> <span data-ttu-id="1c2ef-112">これによって、プールまたはサイト全体を停止させた場合に、バックアップ プールが両方のサイトのユーザーにサービスを継続して提供できます。</span><span class="sxs-lookup"><span data-stu-id="1c2ef-112">Then if you have an entire pool or site go down, the backup pool can continue to provide service to users at both sites.</span></span>
  
<span data-ttu-id="1c2ef-113">Skype for Business Server では、バックエンドサーバーでの高可用性の4つのモード (SQL ミラーリング、AlwaysOn 可用性グループ、AlwaysOn フェールオーバークラスターインスタンス (FCI)、SQL フェールオーバークラスタリング) もサポートされています。</span><span class="sxs-lookup"><span data-stu-id="1c2ef-113">Skype for Business Server also supports four modes of high availability for your Back End Servers: SQL mirroring, AlwaysOn Availability Groups, AlwaysOn Failover Cluster Instances (FCI), and SQL failover clustering.</span></span>
  
> [!NOTE]
> <span data-ttu-id="1c2ef-114">SQL ミラーリングは、Skype for Business Server 2015 では使用できますが、Skype for Business Server 2019 ではサポートされなくなりました。</span><span class="sxs-lookup"><span data-stu-id="1c2ef-114">SQL Mirroring is available in Skype for Business Server 2015 but is no longer supported in Skype for Business Server 2019.</span></span> <span data-ttu-id="1c2ef-115">AlwaysOn 可用性グループ、AlwaysOn フェールオーバークラスターインスタンス (FCI)、SQL フェールオーバークラスタリングの各方法は、Skype for Business Server 2019 で推奨されます。</span><span class="sxs-lookup"><span data-stu-id="1c2ef-115">The  AlwaysOn Availability Groups, AlwaysOn Failover Cluster Instances (FCI), and SQL failover clustering methods are preferred with Skype for Business Server 2019.</span></span>

> [!NOTE]
> <span data-ttu-id="1c2ef-116">AlwaysOn 可用性グループは、常設チャットサーバーではサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="1c2ef-116">AlwaysOn Availability Groups are not supported with Persistent Chat Servers.</span></span> 
  
<span data-ttu-id="1c2ef-117">このセクションでは、これらの機能について説明し、別のサーバーの役割のいくつかに対する高可用性と障害復旧に使用できる手順を取り上げます。</span><span class="sxs-lookup"><span data-stu-id="1c2ef-117">This section explains these features, and also covers what steps you can take for high availability and disaster recovery for some of your other server roles.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="1c2ef-118">関連項目</span><span class="sxs-lookup"><span data-stu-id="1c2ef-118">See also</span></span>

[<span data-ttu-id="1c2ef-119">フロントエンド プールの高可用性と管理</span><span class="sxs-lookup"><span data-stu-id="1c2ef-119">Front End Pool high availability and management</span></span>](high-availability.md)
  
[<span data-ttu-id="1c2ef-120">Skype for Business Server のフロントエンドプールの障害回復</span><span class="sxs-lookup"><span data-stu-id="1c2ef-120">Front End pool disaster recovery in Skype for Business Server</span></span>](disaster-recovery.md)
  
[<span data-ttu-id="1c2ef-121">Skype for Business Server でのプール障害時のユーザーエクスペリエンス</span><span class="sxs-lookup"><span data-stu-id="1c2ef-121">User experience during pool failure in Skype for Business Server</span></span>](user-experience.md)
  
[<span data-ttu-id="1c2ef-122">Skype for Business Server のバックエンドサーバーの高可用性</span><span class="sxs-lookup"><span data-stu-id="1c2ef-122">Back End Server high availability in Skype for Business Server</span></span>](back-end-server.md)
  
[<span data-ttu-id="1c2ef-123">Skype for Business Server でのファイル共有の高可用性</span><span class="sxs-lookup"><span data-stu-id="1c2ef-123">File sharing high availability in Skype for Business Server</span></span>](file-sharing.md)
