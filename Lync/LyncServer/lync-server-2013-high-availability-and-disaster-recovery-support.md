---
title: 'Lync Server 2013: 高可用性および障害復旧のサポート'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: High availability and disaster recovery support
ms:assetid: 47e77e85-c7c3-4ade-8db7-a34c71aeafd7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204866(v=OCS.15)
ms:contentKeyID: 48184053
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5fa5ec2ad01372d593a4452c352c33dd8077e395
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34833069"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="high-availability-and-disaster-recovery-support-in-lync-server-2013"></a><span data-ttu-id="1b5d2-102">Lync Server 2013 での高可用性および障害復旧のサポート</span><span class="sxs-lookup"><span data-stu-id="1b5d2-102">High availability and disaster recovery support in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1b5d2-103">_**最終更新日:** 2012-09-25_</span><span class="sxs-lookup"><span data-stu-id="1b5d2-103">_**Topic Last Modified:** 2012-09-25_</span></span>

<span data-ttu-id="1b5d2-104">Lync Server 2013 は、プールによるサーバーの冗長性による高可用性を実現します。</span><span class="sxs-lookup"><span data-stu-id="1b5d2-104">Lync Server 2013 provides high availability by server redundancy via pooling.</span></span> <span data-ttu-id="1b5d2-105">特定のサーバーの役割を実行するサーバーで障害が発生した場合は、プール内の同じ役割を実行する他のサーバーがそのサーバーの負荷を引き受けます。</span><span class="sxs-lookup"><span data-stu-id="1b5d2-105">If a server running a certain server role fails, the other servers in the pool running the same role take the load of that server.</span></span> <span data-ttu-id="1b5d2-106">同じことが、フロントエンド サーバー、エッジ サーバー、仲介サーバー、およびディレクターでも実行されます。</span><span class="sxs-lookup"><span data-stu-id="1b5d2-106">This applies to Front End Servers, Edge Servers, Mediation Servers, and Directors.</span></span> <span data-ttu-id="1b5d2-107">サーバーの役割の詳細については、「 [Lync server 2013 のサーバーの役割](lync-server-2013-server-roles.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1b5d2-107">For details about server roles, see [Server roles in Lync Server 2013](lync-server-2013-server-roles.md).</span></span>

<span data-ttu-id="1b5d2-108">また、Lync Server 2013 は、プールのペアリングを有効にすることで、障害回復手段を提供します。</span><span class="sxs-lookup"><span data-stu-id="1b5d2-108">Lync Server 2013 also provides disaster recovery measures by enabling pool pairing.</span></span> <span data-ttu-id="1b5d2-109">このトポロジを展開する場合、フロントエンドプールのペアを指定します。各プールは、別々のデータセンターにあり、各プールは別々の地理的領域に配置されています。</span><span class="sxs-lookup"><span data-stu-id="1b5d2-109">If you deploy this topology, you will designate pairs of Front End pools, with each pool in a pair located in a separate data center, and in a separate geographical area.</span></span> <span data-ttu-id="1b5d2-110">1つのプールまたはサイトがダウンした場合は、サービスの中断を最小限に抑えて、そのプールのユーザーを、ペア内の他のプールを使用するようにリダイレクトすることができます。</span><span class="sxs-lookup"><span data-stu-id="1b5d2-110">If one pool or site goes down, you can redirect the users of that pool to use the other pool in the pair, with minimal interruption of service.</span></span>

<span data-ttu-id="1b5d2-111">Lync Server 2013 では、バックエンドサーバーの高可用性もサポートされています。</span><span class="sxs-lookup"><span data-stu-id="1b5d2-111">Lync Server 2013 also supports Back End Server high availability.</span></span> <span data-ttu-id="1b5d2-112">これは、フロントエンドプール用に2つのバックエンドサーバーを展開し、バックエンドサーバーで実行されているすべての Lync データベースの同期 SQL Server ミラーリングを設定する、オプションのトポロジです。</span><span class="sxs-lookup"><span data-stu-id="1b5d2-112">This is an optional topology in which you deploy two Back End Servers for a Front End pool, and set up synchronous SQL Server mirroring for all the Lync databases running on the Back End Servers.</span></span>

<span data-ttu-id="1b5d2-113">プールのペアリングとバックエンドサーバーのミラーリングの詳細については、「 [Lync Server 2013 での高可用性と障害回復の計画](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1b5d2-113">For details about pool pairing and Back End Server mirroring, see [Planning for high availability and disaster recovery in Lync Server 2013](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md).</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="1b5d2-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="1b5d2-114">See Also</span></span>


[<span data-ttu-id="1b5d2-115">Lync Server 2013 のサーバーの役割</span><span class="sxs-lookup"><span data-stu-id="1b5d2-115">Server roles in Lync Server 2013</span></span>](lync-server-2013-server-roles.md)  
[<span data-ttu-id="1b5d2-116">Lync Server 2013 での高可用性および障害復旧の計画</span><span class="sxs-lookup"><span data-stu-id="1b5d2-116">Planning for high availability and disaster recovery in Lync Server 2013</span></span>](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

