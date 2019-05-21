---
title: 障害回復、高可用性、バックアップサービスの管理
ms.reviewer: ''
author: lanachin
ms.author: v-lanac
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 障害回復操作の手順、およびペアリングされたフロントエンドプールのデータを同期するバックアップサービスの維持について説明します。
ms.openlocfilehash: 9664a7d9d48ca084232e2a0473a15d29d970cea6
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2019
ms.locfileid: "34303899"
---
# <a name="managing-skype-for-business-server-disaster-recovery-high-availability-and-backup-service"></a><span data-ttu-id="c49cf-103">Skype for Business Server の災害復旧、高可用性、バックアップサービスの管理</span><span class="sxs-lookup"><span data-stu-id="c49cf-103">Managing Skype for Business Server disaster recovery, high availability, and Backup Service</span></span>

<span data-ttu-id="c49cf-104">このセクションには、障害回復操作の手順に加えて、ペアリングされたフロントエンドプールのデータを同期するバックアップサービスを管理するための手順が含まれています。</span><span class="sxs-lookup"><span data-stu-id="c49cf-104">This section contains procedures for disaster recovery operations, as well as for maintaining the Backup Service, which synchronizes the data in paired Front End pools.</span></span>

<span data-ttu-id="c49cf-105">フェールオーバーとフェールバックの両方の障害回復手順は手動で行うことができます。</span><span class="sxs-lookup"><span data-stu-id="c49cf-105">Disaster recovery procedures, both failover and failback, are manual.</span></span> <span data-ttu-id="c49cf-106">障害が発生した場合、管理者はフェールオーバー手順を手動で呼び出す必要があります。</span><span class="sxs-lookup"><span data-stu-id="c49cf-106">If there is a disaster, the administrator must manually invoke the failover procedures.</span></span> <span data-ttu-id="c49cf-107">プールが修復された後も、フェイルバックにも同じことが適用されます。</span><span class="sxs-lookup"><span data-stu-id="c49cf-107">The same applies to failback after the pool is repaired.</span></span>

<span data-ttu-id="c49cf-108">このセクションの障害回復手順では、次のことを前提としています。</span><span class="sxs-lookup"><span data-stu-id="c49cf-108">The disaster recovery procedures in this section assume the following:</span></span>

  - <span data-ttu-id="c49cf-109">[高可用性と障害復旧の計画](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md)に記載されているように、複数のフロントエンドプールを使用して、さまざまなサイトに存在する展開を利用できます。</span><span class="sxs-lookup"><span data-stu-id="c49cf-109">You have a deployment with paired Front End pools, located in different sites, as described in [Plan for high availability and disaster recovery](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md).</span></span> <span data-ttu-id="c49cf-110">これらのペアのプールでバックアップサービスが実行されているため、同期されません。</span><span class="sxs-lookup"><span data-stu-id="c49cf-110">The Backup Service has been running on these paired pools to keep them synchronized.</span></span>

  - <span data-ttu-id="c49cf-111">中央管理ストアがいずれかのプールでホストされている場合は、これらのペアのプールの両方にインストールされて実行され、アクティブなマスターをホストしているプールと、スタンバイをホストしている他のプールのどちらかになります。</span><span class="sxs-lookup"><span data-stu-id="c49cf-111">If the Central Management store is hosted on either pool, it is installed and running on both of the paired pools, with one of those pools hosting the active master and the other pool hosting the standby.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="c49cf-112">次の手順では、 *Poolfqdn*パラメーターが、障害によって影響を受けるプールの fqdn を示しますが、影響を受けるユーザーがリダイレクトされるプールには関係ありません。</span><span class="sxs-lookup"><span data-stu-id="c49cf-112">In the following procedures, the *PoolFQDN* parameter refers to the FQDN of the pool that is affected by disaster, not the pool that affected users are being redirected from.</span></span> <span data-ttu-id="c49cf-113">影響を受けているユーザーの同じセットの場合、フェールオーバーとフェールバックの両方のコマンドレット (つまり、フェールオーバー前に最初にユーザーをホームにしたプール) で同じプールを参照します。</span><span class="sxs-lookup"><span data-stu-id="c49cf-113">For the same set of affected users, it refers to the same pool in both failover and failback cmdlets (that is, the pool that first homed the users before the failover).</span></span><BR><br><span data-ttu-id="c49cf-114">たとえば、プール P1 に所属しているすべてのユーザーがバックアッププール (P2) にフェールオーバーした場合を想定します。</span><span class="sxs-lookup"><span data-stu-id="c49cf-114">For example, assume a case in which all users homed on a pool P1 were failed over to the backup pool, P2.</span></span> <span data-ttu-id="c49cf-115">管理者が、現在 P2 で処理されているすべてのユーザーを P1 で処理するようにする場合は、管理者は次の手順を実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c49cf-115">If the administrator wants to move all the users currently serviced by P2 to be serviced by P1, the administrator must perform the following steps:</span></span> 
> <OL>
> <LI>
> <P><span data-ttu-id="c49cf-116">フェールバックコマンドレットを使用して、最初に P1 をホームにしたユーザーをすべて P2 から P1 にフェールバックします。</span><span class="sxs-lookup"><span data-stu-id="c49cf-116">Fail back all the users originally homed on P1 from P2 to P1 using the failback cmdlet.</span></span> <span data-ttu-id="c49cf-117">この場合、 *Poolfqdn*は P1's fqdn です。</span><span class="sxs-lookup"><span data-stu-id="c49cf-117">In this case, the *PoolFQDN* is P1’s FQDN.</span></span></P>
> <LI>
> <P><span data-ttu-id="c49cf-118">フェールオーバーコマンドレットを使用して、最初に P2 でホームに所属していたすべてのユーザーをフェールオーバーします。</span><span class="sxs-lookup"><span data-stu-id="c49cf-118">Fail over all the users originally homed on P2 to P1 using the failover cmdlet.</span></span> <span data-ttu-id="c49cf-119">この場合、PoolFQDN は P2's FQDN です。</span><span class="sxs-lookup"><span data-stu-id="c49cf-119">In this case, the PoolFQDN is P2’s FQDN.</span></span></P>
> <LI>
> <P><span data-ttu-id="c49cf-120">後で管理者が p2 に戻すようにしたい場合は、PoolFQDN は P2's FQDN です。</span><span class="sxs-lookup"><span data-stu-id="c49cf-120">If the administrator later wants to fail back those P2 users back to P2, the PoolFQDN is P2’s FQDN.</span></span></P></LI></OL><br><span data-ttu-id="c49cf-121">上記の手順1では、手順2を実行してプールの整合性を維持する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c49cf-121">Note that step 1 above must be performed before step 2 to preserve pool integrity.</span></span> <span data-ttu-id="c49cf-122">手順1より前の手順2を実行した場合は、手順2のコマンドレットが失敗します。</span><span class="sxs-lookup"><span data-stu-id="c49cf-122">If you try step 2 before step 1, the step 2 cmdlet will fail.</span></span>


## <a name="see-also"></a><span data-ttu-id="c49cf-123">関連項目</span><span class="sxs-lookup"><span data-stu-id="c49cf-123">See Also</span></span>

[<span data-ttu-id="c49cf-124">高可用性および障害復旧の計画</span><span class="sxs-lookup"><span data-stu-id="c49cf-124">Plan for high availability and disaster recovery</span></span>](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md) 
  
