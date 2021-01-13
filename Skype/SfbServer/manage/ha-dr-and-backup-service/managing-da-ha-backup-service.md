---
title: 障害復旧、高可用性、およびバックアップ サービスの管理
ms.reviewer: ''
author: cichur
ms.author: v-cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: 障害復旧操作の手順と、ペアのフロント エンド プールのデータを同期するバックアップ サービスを維持する手順について説明します。
ms.openlocfilehash: e486a71203b64b4fc351888869ac64a24689ba7b
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49817157"
---
# <a name="managing-skype-for-business-server-disaster-recovery-high-availability-and-backup-service"></a><span data-ttu-id="77110-103">Skype for Business Server の障害復旧、高可用性、およびバックアップ サービスの管理</span><span class="sxs-lookup"><span data-stu-id="77110-103">Managing Skype for Business Server disaster recovery, high availability, and Backup Service</span></span>

<span data-ttu-id="77110-104">このセクションでは、障害復旧操作の手順と、ペアのフロント エンド プール内のデータを同期するバックアップ サービスを維持するための手順について説明します。</span><span class="sxs-lookup"><span data-stu-id="77110-104">This section contains procedures for disaster recovery operations, as well as for maintaining the Backup Service, which synchronizes the data in paired Front End pools.</span></span>

<span data-ttu-id="77110-p101">障害回復の手順は、フェールオーバーとフェールバックのどちらも、手動によるものです。障害が発生した場合、管理者はフェールオーバーの手順を手動で開始する必要があります。プール修復後のフェールバックにも同じことが当てはまります。</span><span class="sxs-lookup"><span data-stu-id="77110-p101">Disaster recovery procedures, both failover and failback, are manual. If there is a disaster, the administrator must manually invoke the failover procedures. The same applies to failback after the pool is repaired.</span></span>

<span data-ttu-id="77110-108">このセクションの障害復旧手順では、以下を前提とします。</span><span class="sxs-lookup"><span data-stu-id="77110-108">The disaster recovery procedures in this section assume the following:</span></span>

  - <span data-ttu-id="77110-109">「高可用性と障害復旧の計画」で説明するように、ペアのフロント エンド プールが異なるサイト [に展開されている](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md)。</span><span class="sxs-lookup"><span data-stu-id="77110-109">You have a deployment with paired Front End pools, located in different sites, as described in [Plan for high availability and disaster recovery](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md).</span></span> <span data-ttu-id="77110-110">バックアップ サービスは、ペアになったプールの同期を保つためにこれらのプール上で実行されています。</span><span class="sxs-lookup"><span data-stu-id="77110-110">The Backup Service has been running on these paired pools to keep them synchronized.</span></span>

  - <span data-ttu-id="77110-111">中央管理ストアがいずれかのプールでホストされている場合、そのストアはペアのプールの両方にインストールされ、実行されます。これらのプールの 1 つはアクティブ マスターをホストし、もう 1 つはスタンバイをホストするプールです。</span><span class="sxs-lookup"><span data-stu-id="77110-111">If the Central Management store is hosted on either pool, it is installed and running on both of the paired pools, with one of those pools hosting the active master and the other pool hosting the standby.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="77110-p103">以下の手順では、影響を受けるユーザーのリダイレクト元になるプールではなく、障害の影響を受けるプールの完全修飾 FQDN を PoolFQDN \*\* パラメーターが参照しています。影響を受ける同じユーザー群が同じ場合、このパラメーターはフェールオーバーとフェールバックの各コマンドレットで同じプール (つまり、ユーザーがフェールオーバー前に最初に所属していたプール) を参照します。</span><span class="sxs-lookup"><span data-stu-id="77110-p103">In the following procedures, the *PoolFQDN* parameter refers to the FQDN of the pool that is affected by disaster, not the pool that affected users are being redirected from. For the same set of affected users, it refers to the same pool in both failover and failback cmdlets (that is, the pool that first homed the users before the failover).</span></span><BR><br><span data-ttu-id="77110-114">たとえば、プール P1 に所属していたすべてのユーザーがバックアップ プール P2 にフェールオーバーされた場合を想定します。</span><span class="sxs-lookup"><span data-stu-id="77110-114">For example, assume a case in which all users homed on a pool P1 were failed over to the backup pool, P2.</span></span> <span data-ttu-id="77110-115">管理者が P2 によって現在サービスを受け取っているすべてのユーザーを P1 によって処理される移動する場合、管理者は次の手順を実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="77110-115">If the administrator wants to move all the users currently serviced by P2 to be serviced by P1, the administrator must perform the following steps:</span></span> 
> <OL>
> <LI>
> <P><span data-ttu-id="77110-116">フェールバック コマンドレットを使用して、当初 P1 にホームだったすべてのユーザーを P2 から P1 にフェールバックします。</span><span class="sxs-lookup"><span data-stu-id="77110-116">Fail back all the users originally homed on P1 from P2 to P1 using the failback cmdlet.</span></span> <span data-ttu-id="77110-117">この場合、PoolFQDN \*\* は P1 の FQDN になります。</span><span class="sxs-lookup"><span data-stu-id="77110-117">In this case, the *PoolFQDN* is P1’s FQDN.</span></span></P>
> <LI>
> <P><span data-ttu-id="77110-118">フェールオーバー コマンドレットを使用して、当初 P2 から P1 にいたすべてのユーザーをフェールオーバーします。</span><span class="sxs-lookup"><span data-stu-id="77110-118">Fail over all the users originally homed on P2 to P1 using the failover cmdlet.</span></span> <span data-ttu-id="77110-119">この場合、PoolFQDN は P2 の FQDN になります。</span><span class="sxs-lookup"><span data-stu-id="77110-119">In this case, the PoolFQDN is P2’s FQDN.</span></span></P>
> <LI>
> <P><span data-ttu-id="77110-120">後で管理者が P2 ユーザーを P2 にフェールバックする場合、PoolFQDN は P2 の FQDN になります。</span><span class="sxs-lookup"><span data-stu-id="77110-120">If the administrator later wants to fail back those P2 users back to P2, the PoolFQDN is P2’s FQDN.</span></span></P></LI></OL><br><span data-ttu-id="77110-121">プールの整合性を維持するには、上記の手順 1 を手順 2 の前に実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="77110-121">Note that step 1 above must be performed before step 2 to preserve pool integrity.</span></span> <span data-ttu-id="77110-122">手順 1 の前に手順 2 を実行すると、手順 2 のコマンドレットは失敗します。</span><span class="sxs-lookup"><span data-stu-id="77110-122">If you try step 2 before step 1, the step 2 cmdlet will fail.</span></span>


## <a name="see-also"></a><span data-ttu-id="77110-123">関連項目</span><span class="sxs-lookup"><span data-stu-id="77110-123">See Also</span></span>

[<span data-ttu-id="77110-124">高可用性と障害復旧を計画する</span><span class="sxs-lookup"><span data-stu-id="77110-124">Plan for high availability and disaster recovery</span></span>](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md) 
  
