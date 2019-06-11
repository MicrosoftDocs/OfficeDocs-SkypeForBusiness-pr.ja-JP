---
title: Lync Server の災害復旧、高可用性、バックアップサービスの管理
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Managing Lync Server disaster recovery, high availability, and Backup Service
ms:assetid: f4cd36fb-ffd6-48fa-b761-e11b3bcff91a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721939(v=OCS.15)
ms:contentKeyID: 49733876
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: cada393fca28895ee5f23a12fdd55eabd211128e
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34828013"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="managing-lync-server-2013-disaster-recovery-high-availability-and-backup-service"></a><span data-ttu-id="f9135-102">Lync Server 2013 の障害復旧、高可用性およびバックアップ サービスの管理</span><span class="sxs-lookup"><span data-stu-id="f9135-102">Managing Lync Server 2013 disaster recovery, high availability, and Backup Service</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f9135-103">_**最終更新日:** 2012-11-12_</span><span class="sxs-lookup"><span data-stu-id="f9135-103">_**Topic Last Modified:** 2012-11-12_</span></span>

<span data-ttu-id="f9135-104">このセクションには、障害回復操作の手順、およびペアリングされたフロントエンドプールのデータを同期するバックアップサービスの保守の手順が含まれています。</span><span class="sxs-lookup"><span data-stu-id="f9135-104">This section contains procedures for disaster recovery operations, as well as for maintaining the Backup Service which synchronizes the data in paired Front End pools.</span></span>

<span data-ttu-id="f9135-105">フェールオーバーとフェールバックの両方の障害回復手順は手動で行うことができます。</span><span class="sxs-lookup"><span data-stu-id="f9135-105">Disaster recovery procedures, both failover and failback, are manual.</span></span> <span data-ttu-id="f9135-106">障害が発生した場合、管理者はフェールオーバー手順を手動で呼び出す必要があります。</span><span class="sxs-lookup"><span data-stu-id="f9135-106">If there is a disaster, the administrator must manually invoke the failover procedures.</span></span> <span data-ttu-id="f9135-107">プールが修復された後も、フェイルバックにも同じことが適用されます。</span><span class="sxs-lookup"><span data-stu-id="f9135-107">The same applies to failback after the pool is repaired.</span></span>

<span data-ttu-id="f9135-108">このセクションの残りの部分では、次のような障害回復手順について説明します。</span><span class="sxs-lookup"><span data-stu-id="f9135-108">The disaster recovery procedures in the rest of this section assume the following:</span></span>

  - <span data-ttu-id="f9135-109">「 [Lync Server 2013 での高可用性と障害回復の計画](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md)」で説明されているように、複数のフロントエンドプールを使用して展開を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="f9135-109">You have a deployment with paired Front End pools, located in different sites, as described in [Planning for high availability and disaster recovery in Lync Server 2013](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md).</span></span> <span data-ttu-id="f9135-110">これらのペアのプールでバックアップサービスが実行されているため、同期されません。</span><span class="sxs-lookup"><span data-stu-id="f9135-110">The Backup Service has been running on these paired pools to keep them synchronized.</span></span>

  - <span data-ttu-id="f9135-111">中央管理ストアがいずれかのプールでホストされている場合は、これらのペアのプールの両方にインストールされて実行され、アクティブなマスターをホストしているプールと、スタンバイをホストしている他のプールのどちらかになります。</span><span class="sxs-lookup"><span data-stu-id="f9135-111">If the Central Management store is hosted on either pool, it is installed and running on both of the paired pools, with one of those pools hosting the active master and the other pool hosting the standby.</span></span>

<div>


> [!IMPORTANT]
> <span data-ttu-id="f9135-112">次の手順では、 <EM>Poolfqdn</EM>パラメーターが、障害によって影響を受けるプールの fqdn を示しますが、影響を受けるユーザーがリダイレクトされるプールには関係ありません。</span><span class="sxs-lookup"><span data-stu-id="f9135-112">In the following procedures, the <EM>PoolFQDN</EM> parameter refers to the FQDN of the pool that is affected by disaster, not the pool that affected users are being redirected from.</span></span> <span data-ttu-id="f9135-113">影響を受けているユーザーの同じセットの場合、フェールオーバーとフェールバックの両方のコマンドレット (つまり、フェールオーバー前に最初にユーザーをホームにしたプール) で同じプールを参照します。</span><span class="sxs-lookup"><span data-stu-id="f9135-113">For the same set of affected users, it refers to the same pool in both failover and failback cmdlets (that is, the pool that first homed the users before the failover).</span></span><BR><span data-ttu-id="f9135-114">たとえば、プール P1 に所属しているすべてのユーザーがバックアッププール (P2) にフェールオーバーした場合を想定します。</span><span class="sxs-lookup"><span data-stu-id="f9135-114">For example, assume a case in which all users homed on a pool P1 were failed over to the backup pool, P2.</span></span> <span data-ttu-id="f9135-115">管理者が、現在 P2 で処理されているすべてのユーザーを P1 で処理するようにする場合は、管理者は次の手順を実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f9135-115">If the administrator wants to move all the users currently serviced by P2 to be serviced by P1, the administrator must perform the following steps:</span></span> 
> <OL>
> <LI>
> <P><span data-ttu-id="f9135-116">フェールバックコマンドレットを使用して、最初に P1 をホームにしたユーザーをすべて P2 から P1 にフェールバックします。</span><span class="sxs-lookup"><span data-stu-id="f9135-116">Fail back all the users originally homed on P1 from P2 to P1 using the failback cmdlet.</span></span> <span data-ttu-id="f9135-117">この場合、 <EM>Poolfqdn</EM>は P1's fqdn です。</span><span class="sxs-lookup"><span data-stu-id="f9135-117">In this case, the <EM>PoolFQDN</EM> is P1’s FQDN.</span></span></P>
> <LI>
> <P><span data-ttu-id="f9135-118">フェールオーバーコマンドレットを使用して、最初に P2 でホームに所属していたすべてのユーザーをフェールオーバーします。</span><span class="sxs-lookup"><span data-stu-id="f9135-118">Fail over all the users originally homed on P2 to P1 using the failover cmdlet.</span></span> <span data-ttu-id="f9135-119">この場合、 <EM>Poolfqdn</EM>は P2's fqdn です。</span><span class="sxs-lookup"><span data-stu-id="f9135-119">In this case, the <EM>PoolFQDN</EM> is P2’s FQDN.</span></span></P>
> <LI>
> <P><span data-ttu-id="f9135-120">後で管理者が p2 に戻すようにしたい場合は、 <EM>Poolfqdn</EM>は P2's fqdn です。</span><span class="sxs-lookup"><span data-stu-id="f9135-120">If the administrator later wants to fail back those P2 users back to P2, the <EM>PoolFQDN</EM> is P2’s FQDN.</span></span></P></LI></OL><span data-ttu-id="f9135-121">上記の手順1では、手順2を実行してプールの整合性を維持する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f9135-121">Note that step 1 above must be performed before step 2 to preserve pool integrity.</span></span> <span data-ttu-id="f9135-122">手順1より前の手順2を実行した場合は、手順2のコマンドレットが失敗します。</span><span class="sxs-lookup"><span data-stu-id="f9135-122">If you try step 2 before step 1, the step 2 cmdlet will fail.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="f9135-123">このセクション中</span><span class="sxs-lookup"><span data-stu-id="f9135-123">In This Section</span></span>

  - [<span data-ttu-id="f9135-124">Lync Server 2013 でのバックアップ サービスの構成と監視</span><span class="sxs-lookup"><span data-stu-id="f9135-124">Configuring and monitoring the Backup Service in Lync Server 2013</span></span>](lync-server-2013-configuring-and-monitoring-the-backup-service.md)

  - [<span data-ttu-id="f9135-125">Lync Server 2013 でのプールのフェールオーバー</span><span class="sxs-lookup"><span data-stu-id="f9135-125">Failing over a pool in Lync Server 2013</span></span>](lync-server-2013-failing-over-a-pool.md)

  - [<span data-ttu-id="f9135-126">Lync Server 2013 でのプールのフェールバック</span><span class="sxs-lookup"><span data-stu-id="f9135-126">Failing back a pool in Lync Server 2013</span></span>](lync-server-2013-failing-back-a-pool.md)

  - [<span data-ttu-id="f9135-127">Lync Server 2013 でのミラー化データベースのフェールオーバー</span><span class="sxs-lookup"><span data-stu-id="f9135-127">Failing over a mirrored database in Lync Server 2013</span></span>](lync-server-2013-failing-over-a-mirrored-database.md)

  - [<span data-ttu-id="f9135-128">Lync Server 2013 での Lync Server フェデレーションに使用するエッジ プールのフェールオーバー</span><span class="sxs-lookup"><span data-stu-id="f9135-128">Failing over the Edge pool used for Lync Server federation in Lync Server 2013</span></span>](lync-server-2013-failing-over-the-edge-pool-used-for-lync-server-federation.md)

  - [<span data-ttu-id="f9135-129">Lync Server 2013 での、XMPP フェデレーションに使用するエッジ プールのフェールオーバー</span><span class="sxs-lookup"><span data-stu-id="f9135-129">Failing over the Edge pool used for XMPP federation in Lync Server 2013</span></span>](lync-server-2013-failing-over-the-edge-pool-used-for-xmpp-federation.md)

  - [<span data-ttu-id="f9135-130">Lync Server 2013 での Lync Server フェデレーションまたは XMPP フェデレーションに使用するエッジ プールのフェールバック</span><span class="sxs-lookup"><span data-stu-id="f9135-130">Failing back the Edge pool used for Lync Server federation or XMPP federation in Lync Server 2013</span></span>](lync-server-2013-failing-back-the-edge-pool-used-for-lync-server-federation-or-xmpp-federation.md)

  - [<span data-ttu-id="f9135-131">Lync Server 2013 でのフロント エンド プールに関連付けられたエッジ プールの変更</span><span class="sxs-lookup"><span data-stu-id="f9135-131">Changing the Edge pool associated with a Front End pool in Lync Server 2013</span></span>](lync-server-2013-changing-the-edge-pool-associated-with-a-front-end-pool.md)

  - [<span data-ttu-id="f9135-132">Lync Server 2013 でのバックアップ サービスを使用した会議コンテンツの復元</span><span class="sxs-lookup"><span data-stu-id="f9135-132">Restoring conference contents using the Backup Service in Lync Server 2013</span></span>](lync-server-2013-restoring-conference-contents-using-the-backup-service.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="f9135-133">関連項目</span><span class="sxs-lookup"><span data-stu-id="f9135-133">See Also</span></span>


[<span data-ttu-id="f9135-134">Lync Server 2013 での高可用性および障害復旧の計画</span><span class="sxs-lookup"><span data-stu-id="f9135-134">Planning for high availability and disaster recovery in Lync Server 2013</span></span>](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

