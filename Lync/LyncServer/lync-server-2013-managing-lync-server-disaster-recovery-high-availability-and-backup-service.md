---
title: Lync Server の障害復旧、高可用性、およびバックアップサービスの管理
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Managing Lync Server disaster recovery, high availability, and Backup Service
ms:assetid: f4cd36fb-ffd6-48fa-b761-e11b3bcff91a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721939(v=OCS.15)
ms:contentKeyID: 49733876
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 83e0446bbc0b39f553ac9a2bcba0af9ceacc421f
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2020
ms.locfileid: "42034407"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="managing-lync-server-2013-disaster-recovery-high-availability-and-backup-service"></a><span data-ttu-id="0d86f-102">Lync Server 2013 の障害復旧、高可用性、およびバックアップサービスの管理</span><span class="sxs-lookup"><span data-stu-id="0d86f-102">Managing Lync Server 2013 disaster recovery, high availability, and Backup Service</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0d86f-103">_**トピックの最終更新日:** 2012-11-12_</span><span class="sxs-lookup"><span data-stu-id="0d86f-103">_**Topic Last Modified:** 2012-11-12_</span></span>

<span data-ttu-id="0d86f-104">このセクションには、障害復旧操作のほか、ペアになったフロントエンドプール内のデータを同期するバックアップサービスの保守の手順が記載されています。</span><span class="sxs-lookup"><span data-stu-id="0d86f-104">This section contains procedures for disaster recovery operations, as well as for maintaining the Backup Service which synchronizes the data in paired Front End pools.</span></span>

<span data-ttu-id="0d86f-p101">障害回復の手順は、フェールオーバーとフェールバックのどちらも、手動によるものです。障害が発生した場合、管理者はフェールオーバーの手順を手動で開始する必要があります。プール修復後のフェールバックにも同じことが当てはまります。</span><span class="sxs-lookup"><span data-stu-id="0d86f-p101">Disaster recovery procedures, both failover and failback, are manual. If there is a disaster, the administrator must manually invoke the failover procedures. The same applies to failback after the pool is repaired.</span></span>

<span data-ttu-id="0d86f-108">このセクションの以降の部分における障害回復の手順では、以下のことを前提としています。</span><span class="sxs-lookup"><span data-stu-id="0d86f-108">The disaster recovery procedures in the rest of this section assume the following:</span></span>

  - <span data-ttu-id="0d86f-109">「 [Lync Server 2013 での高可用性と障害復旧の計画](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md)」で説明されているように、別のサイトにある、ペアのフロントエンドプールを備えた展開を使用している。</span><span class="sxs-lookup"><span data-stu-id="0d86f-109">You have a deployment with paired Front End pools, located in different sites, as described in [Planning for high availability and disaster recovery in Lync Server 2013](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md).</span></span> <span data-ttu-id="0d86f-110">バックアップ サービスは、ペアになったプールの同期を保つためにこれらのプール上で実行されています。</span><span class="sxs-lookup"><span data-stu-id="0d86f-110">The Backup Service has been running on these paired pools to keep them synchronized.</span></span>

  - <span data-ttu-id="0d86f-111">中央管理ストアがどちらのプールでホストされている場合でも、その中の両方のプールにインストールされて実行されており、アクティブなマスターとスタンバイをホストしている他のプールのどちらかによってホストされます。</span><span class="sxs-lookup"><span data-stu-id="0d86f-111">If the Central Management store is hosted on either pool, it is installed and running on both of the paired pools, with one of those pools hosting the active master and the other pool hosting the standby.</span></span>

<div>


> [!IMPORTANT]
> <span data-ttu-id="0d86f-p103">以下の手順では、影響を受けるユーザーのリダイレクト元になるプールではなく、障害の影響を受けるプールの完全修飾 FQDN を PoolFQDN<EM></EM> パラメーターが参照しています。影響を受ける同じユーザー群が同じ場合、このパラメーターはフェールオーバーとフェールバックの各コマンドレットで同じプール (つまり、ユーザーがフェールオーバー前に最初に所属していたプール) を参照します。</span><span class="sxs-lookup"><span data-stu-id="0d86f-p103">In the following procedures, the <EM>PoolFQDN</EM> parameter refers to the FQDN of the pool that is affected by disaster, not the pool that affected users are being redirected from. For the same set of affected users, it refers to the same pool in both failover and failback cmdlets (that is, the pool that first homed the users before the failover).</span></span><BR><span data-ttu-id="0d86f-114">たとえば、プール P1 に所属していたすべてのユーザーがバックアップ プール P2 にフェールオーバーされた場合を想定します。</span><span class="sxs-lookup"><span data-stu-id="0d86f-114">For example, assume a case in which all users homed on a pool P1 were failed over to the backup pool, P2.</span></span> <span data-ttu-id="0d86f-115">管理者が、P2 でサービスを提供しているすべてのユーザーを P1 によって処理するように移行する場合は、管理者は次の手順を実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="0d86f-115">If the administrator wants to move all the users currently serviced by P2 to be serviced by P1, the administrator must perform the following steps:</span></span> 
> <OL>
> <LI>
> <P><span data-ttu-id="0d86f-116">フェールバックコマンドレットを使用して、最初に P1 に所属していたすべてのユーザーを P2 から P1 にフェールバックします。</span><span class="sxs-lookup"><span data-stu-id="0d86f-116">Fail back all the users originally homed on P1 from P2 to P1 using the failback cmdlet.</span></span> <span data-ttu-id="0d86f-117">この場合、PoolFQDN<EM></EM> は P1 の FQDN になります。</span><span class="sxs-lookup"><span data-stu-id="0d86f-117">In this case, the <EM>PoolFQDN</EM> is P1’s FQDN.</span></span></P>
> <LI>
> <P><span data-ttu-id="0d86f-118">フェールオーバーコマンドレットを使用して、最初に P2 に所属していたすべてのユーザーを P1 にフェールオーバーします。</span><span class="sxs-lookup"><span data-stu-id="0d86f-118">Fail over all the users originally homed on P2 to P1 using the failover cmdlet.</span></span> <span data-ttu-id="0d86f-119">この場合、PoolFQDN<EM></EM> は P2 の FQDN になります。</span><span class="sxs-lookup"><span data-stu-id="0d86f-119">In this case, the <EM>PoolFQDN</EM> is P2’s FQDN.</span></span></P>
> <LI>
> <P><span data-ttu-id="0d86f-120">後で管理者がこれらの P2 ユーザーを P2 にフェールバックする場合、 <EM>Poolfqdn</EM>は p2 fqdn になります。</span><span class="sxs-lookup"><span data-stu-id="0d86f-120">If the administrator later wants to fail back those P2 users back to P2, the <EM>PoolFQDN</EM> is P2’s FQDN.</span></span></P></LI></OL><span data-ttu-id="0d86f-121">手順1を実行してから、プールの整合性を保持する必要があることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="0d86f-121">Note that step 1 above must be performed before step 2 to preserve pool integrity.</span></span> <span data-ttu-id="0d86f-122">手順1の前に手順2を実行すると、手順2のコマンドレットは失敗します。</span><span class="sxs-lookup"><span data-stu-id="0d86f-122">If you try step 2 before step 1, the step 2 cmdlet will fail.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="0d86f-123">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="0d86f-123">In This Section</span></span>

  - [<span data-ttu-id="0d86f-124">Lync Server 2013 でのバックアップサービスの構成と監視</span><span class="sxs-lookup"><span data-stu-id="0d86f-124">Configuring and monitoring the Backup Service in Lync Server 2013</span></span>](lync-server-2013-configuring-and-monitoring-the-backup-service.md)

  - [<span data-ttu-id="0d86f-125">Lync Server 2013 でのプールのフェールオーバー</span><span class="sxs-lookup"><span data-stu-id="0d86f-125">Failing over a pool in Lync Server 2013</span></span>](lync-server-2013-failing-over-a-pool.md)

  - [<span data-ttu-id="0d86f-126">Lync Server 2013 でのプールのフェールバック</span><span class="sxs-lookup"><span data-stu-id="0d86f-126">Failing back a pool in Lync Server 2013</span></span>](lync-server-2013-failing-back-a-pool.md)

  - [<span data-ttu-id="0d86f-127">Lync Server 2013 でのミラー化されたデータベースのフェールオーバー</span><span class="sxs-lookup"><span data-stu-id="0d86f-127">Failing over a mirrored database in Lync Server 2013</span></span>](lync-server-2013-failing-over-a-mirrored-database.md)

  - [<span data-ttu-id="0d86f-128">Lync Server 2013 での Lync Server フェデレーションに使用するエッジプールのフェールオーバー</span><span class="sxs-lookup"><span data-stu-id="0d86f-128">Failing over the Edge pool used for Lync Server federation in Lync Server 2013</span></span>](lync-server-2013-failing-over-the-edge-pool-used-for-lync-server-federation.md)

  - [<span data-ttu-id="0d86f-129">Lync Server 2013 での XMPP フェデレーションに使用するエッジプールのフェールオーバー</span><span class="sxs-lookup"><span data-stu-id="0d86f-129">Failing over the Edge pool used for XMPP federation in Lync Server 2013</span></span>](lync-server-2013-failing-over-the-edge-pool-used-for-xmpp-federation.md)

  - [<span data-ttu-id="0d86f-130">Lync server 2013 での Lync Server フェデレーションまたは XMPP フェデレーションに使用するエッジプールのフェールバック</span><span class="sxs-lookup"><span data-stu-id="0d86f-130">Failing back the Edge pool used for Lync Server federation or XMPP federation in Lync Server 2013</span></span>](lync-server-2013-failing-back-the-edge-pool-used-for-lync-server-federation-or-xmpp-federation.md)

  - [<span data-ttu-id="0d86f-131">Lync Server 2013 のフロントエンドプールに関連付けられたエッジプールの変更</span><span class="sxs-lookup"><span data-stu-id="0d86f-131">Changing the Edge pool associated with a Front End pool in Lync Server 2013</span></span>](lync-server-2013-changing-the-edge-pool-associated-with-a-front-end-pool.md)

  - [<span data-ttu-id="0d86f-132">Lync Server 2013 でのバックアップサービスを使用した会議コンテンツの復元</span><span class="sxs-lookup"><span data-stu-id="0d86f-132">Restoring conference contents using the Backup Service in Lync Server 2013</span></span>](lync-server-2013-restoring-conference-contents-using-the-backup-service.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="0d86f-133">関連項目</span><span class="sxs-lookup"><span data-stu-id="0d86f-133">See Also</span></span>


[<span data-ttu-id="0d86f-134">Lync Server 2013 での高可用性および障害復旧の計画</span><span class="sxs-lookup"><span data-stu-id="0d86f-134">Planning for high availability and disaster recovery in Lync Server 2013</span></span>](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

