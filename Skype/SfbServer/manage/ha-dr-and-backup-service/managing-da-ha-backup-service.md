---
title: 災害復旧、高可用性、およびバックアップ サービスの管理
ms.reviewer: ''
author: heidip
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: ペアのフロント エンド プール内のデータを同期しているバックアップ サービスを維持するためだけでなく、災害リカバリ ・ オペレーションの手順について説明します。
ms.openlocfilehash: 103e0aa274e40fd997981bd6de595ceca089b710
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "32199827"
---
# <a name="managing-skype-for-business-server-disaster-recovery-high-availability-and-backup-service"></a><span data-ttu-id="ebc46-103">Business Server の災害復旧、高可用性、およびバックアップ サービスの Skype を管理します。</span><span class="sxs-lookup"><span data-stu-id="ebc46-103">Managing Skype for Business Server disaster recovery, high availability, and Backup Service</span></span>

<span data-ttu-id="ebc46-104">このセクションでは、ペアのフロント エンド プール内のデータを同期しているバックアップ サービスを維持するためだけでなく、災害リカバリ ・ オペレーションの手順を説明します。</span><span class="sxs-lookup"><span data-stu-id="ebc46-104">This section contains procedures for disaster recovery operations, as well as for maintaining the Backup Service, which synchronizes the data in paired Front End pools.</span></span>

<span data-ttu-id="ebc46-105">フェールオーバーとフェールバックの両方に、障害回復手順は、手動です。</span><span class="sxs-lookup"><span data-stu-id="ebc46-105">Disaster recovery procedures, both failover and failback, are manual.</span></span> <span data-ttu-id="ebc46-106">障害がある場合は、管理者はフェイル オーバー手順を手動で呼び出す必要があります。</span><span class="sxs-lookup"><span data-stu-id="ebc46-106">If there is a disaster, the administrator must manually invoke the failover procedures.</span></span> <span data-ttu-id="ebc46-107">プールが修復された後、同じはフェイル バックに適用されます。</span><span class="sxs-lookup"><span data-stu-id="ebc46-107">The same applies to failback after the pool is repaired.</span></span>

<span data-ttu-id="ebc46-108">ここでディザスタ リカバリの手順は、以下と仮定します。</span><span class="sxs-lookup"><span data-stu-id="ebc46-108">The disaster recovery procedures in this section assume the following:</span></span>

  - <span data-ttu-id="ebc46-109">[高可用性と災害復旧の計画](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md)で説明したように別のサイトにあるペアのフロント エンド プールを使用した展開があります。</span><span class="sxs-lookup"><span data-stu-id="ebc46-109">You have a deployment with paired Front End pools, located in different sites, as described in [Plan for high availability and disaster recovery](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md).</span></span> <span data-ttu-id="ebc46-110">これらのペアになったプールにそれらを同期させてのバックアップ サービスを実行するとします。</span><span class="sxs-lookup"><span data-stu-id="ebc46-110">The Backup Service has been running on these paired pools to keep them synchronized.</span></span>

  - <span data-ttu-id="ebc46-111">中央管理ストアがいずれかのプールでホストされている場合は、作業中のマスターをホストしているこれらのプールと、スタンバイ状態をホストしている他のプールの 1 つで、対になったプールの両方にインストールして実行します。</span><span class="sxs-lookup"><span data-stu-id="ebc46-111">If the Central Management store is hosted on either pool, it is installed and running on both of the paired pools, with one of those pools hosting the active master and the other pool hosting the standby.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="ebc46-112">次の手順で、 *PoolFQDN*パラメーターは、災害の影響を受けるプールの FQDN を参照からリダイレクトされるユーザーに影響をプールではありません。</span><span class="sxs-lookup"><span data-stu-id="ebc46-112">In the following procedures, the *PoolFQDN* parameter refers to the FQDN of the pool that is affected by disaster, not the pool that affected users are being redirected from.</span></span> <span data-ttu-id="ebc46-113">影響を受けるユーザーの同じセットのフェールオーバーとフェールバックの両方のコマンドレット (つまり、最初にフェールオーバーする前にユーザーをホーム サーバー プール) で同じプールを指します。</span><span class="sxs-lookup"><span data-stu-id="ebc46-113">For the same set of affected users, it refers to the same pool in both failover and failback cmdlets (that is, the pool that first homed the users before the failover).</span></span><BR><br><span data-ttu-id="ebc46-114">たとえば、バックアップのプールでは、P2 を P1 がフェイル オーバー ・ プール上のすべてのユーザーがホーム サーバーの場合を想定しています。</span><span class="sxs-lookup"><span data-stu-id="ebc46-114">For example, assume a case in which all users homed on a pool P1 were failed over to the backup pool, P2.</span></span> <span data-ttu-id="ebc46-115">管理者が現在 P2 が P1 でサービスがサービスを提供するすべてのユーザーを移動したい場合、管理者は次の手順に従う必要があります。</span><span class="sxs-lookup"><span data-stu-id="ebc46-115">If the administrator wants to move all the users currently serviced by P2 to be serviced by P1, the administrator must perform the following steps:</span></span> 
> <OL>
> <LI>
> <P><span data-ttu-id="ebc46-116">失敗は、もともと所属していたユーザーに P1、P2 から P1 のすべてをバックアップ、フェイル バックのコマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="ebc46-116">Fail back all the users originally homed on P1 from P2 to P1 using the failback cmdlet.</span></span> <span data-ttu-id="ebc46-117">*PoolFQDN*は、この例では、P1 の FQDN です。</span><span class="sxs-lookup"><span data-stu-id="ebc46-117">In this case, the *PoolFQDN* is P1’s FQDN.</span></span></P>
> <LI>
> <P><span data-ttu-id="ebc46-118">フェイル オーバー、もともと所属していたユーザーに P1、P2 のすべてのフェイル オーバーのコマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="ebc46-118">Fail over all the users originally homed on P2 to P1 using the failover cmdlet.</span></span> <span data-ttu-id="ebc46-119">このケースで、PoolFQDN は、P2 の FQDN です。</span><span class="sxs-lookup"><span data-stu-id="ebc46-119">In this case, the PoolFQDN is P2’s FQDN.</span></span></P>
> <LI>
> <P><span data-ttu-id="ebc46-120">後で、管理者は P2 に P2 ユーザーのフェイル バックしたいと考えていると、PoolFQDN が P2 の FQDN です。</span><span class="sxs-lookup"><span data-stu-id="ebc46-120">If the administrator later wants to fail back those P2 users back to P2, the PoolFQDN is P2’s FQDN.</span></span></P></LI></OL><br><span data-ttu-id="ebc46-121">プールの整合性を保持するために 2 の手順の前に、上記の手順 1 を実行する必要が注意してください。</span><span class="sxs-lookup"><span data-stu-id="ebc46-121">Note that step 1 above must be performed before step 2 to preserve pool integrity.</span></span> <span data-ttu-id="ebc46-122">手順 2 手順 1 の前にしようとすると、手順 2 のコマンドレットは失敗します。</span><span class="sxs-lookup"><span data-stu-id="ebc46-122">If you try step 2 before step 1, the step 2 cmdlet will fail.</span></span>


## <a name="see-also"></a><span data-ttu-id="ebc46-123">関連項目</span><span class="sxs-lookup"><span data-stu-id="ebc46-123">See Also</span></span>

[<span data-ttu-id="ebc46-124">高可用性および障害復旧の計画</span><span class="sxs-lookup"><span data-stu-id="ebc46-124">Plan for high availability and disaster recovery</span></span>](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md) 
  
