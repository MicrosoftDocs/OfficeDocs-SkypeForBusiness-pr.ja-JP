---
title: 'Lync Server 2013: 高可用性および障害復旧のサポート'
description: 'Lync Server 2013: 高可用性および障害復旧のサポート。'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: High availability and disaster recovery support
ms:assetid: 47e77e85-c7c3-4ade-8db7-a34c71aeafd7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204866(v=OCS.15)
ms:contentKeyID: 48184053
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a8113c6b54cbb55e8149f8d6dd1b53ccbdc9436d
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48552793"
---
# <a name="high-availability-and-disaster-recovery-support-in-lync-server-2013"></a><span data-ttu-id="802ba-103">Lync Server 2013 での高可用性および障害復旧のサポート</span><span class="sxs-lookup"><span data-stu-id="802ba-103">High availability and disaster recovery support in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="802ba-104">_**トピックの最終更新日:** 2012-09-25_</span><span class="sxs-lookup"><span data-stu-id="802ba-104">_**Topic Last Modified:** 2012-09-25_</span></span>

<span data-ttu-id="802ba-105">Lync Server 2013 では、プールによるサーバー冗長性による高可用性が提供されます。</span><span class="sxs-lookup"><span data-stu-id="802ba-105">Lync Server 2013 provides high availability by server redundancy via pooling.</span></span> <span data-ttu-id="802ba-106">あるサーバーの役割を実行しているサーバーが失敗すると、プール内で同じサーバーの役割を実行している別のサーバーがそのサーバーの負荷を引き継ぎます。</span><span class="sxs-lookup"><span data-stu-id="802ba-106">If a server running a certain server role fails, the other servers in the pool running the same role take the load of that server.</span></span> <span data-ttu-id="802ba-107">これはフロントエンド サーバー、エッジ サーバー、仲介サーバー、およびディレクターに適用されます。</span><span class="sxs-lookup"><span data-stu-id="802ba-107">This applies to Front End Servers, Edge Servers, Mediation Servers, and Directors.</span></span> <span data-ttu-id="802ba-108">サーバーの役割の詳細については、「 [Lync server 2013 のサーバーの役割](lync-server-2013-server-roles.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="802ba-108">For details about server roles, see [Server roles in Lync Server 2013](lync-server-2013-server-roles.md).</span></span>

<span data-ttu-id="802ba-109">Lync Server 2013 では、プールのペアリングを有効にすることで、障害復旧の手段を提供します。</span><span class="sxs-lookup"><span data-stu-id="802ba-109">Lync Server 2013 also provides disaster recovery measures by enabling pool pairing.</span></span> <span data-ttu-id="802ba-110">このトポロジを展開する場合は、フロントエンドプールのペアを指定し、各プールを別々のデータセンターに配置し、個別の地理的領域に配置します。</span><span class="sxs-lookup"><span data-stu-id="802ba-110">If you deploy this topology, you will designate pairs of Front End pools, with each pool in a pair located in a separate data center, and in a separate geographical area.</span></span> <span data-ttu-id="802ba-111">1つのプールまたはサイトに障害が発生した場合は、サービスの中断を最小限に抑えて、そのプールのユーザーがペアの他のプールを使用するようにリダイレクトすることができます。</span><span class="sxs-lookup"><span data-stu-id="802ba-111">If one pool or site goes down, you can redirect the users of that pool to use the other pool in the pair, with minimal interruption of service.</span></span>

<span data-ttu-id="802ba-112">Lync Server 2013 では、バックエンドサーバーの高可用性もサポートしています。</span><span class="sxs-lookup"><span data-stu-id="802ba-112">Lync Server 2013 also supports Back End Server high availability.</span></span> <span data-ttu-id="802ba-113">これは、フロントエンドプール用に2台のバックエンドサーバーを展開し、バックエンドサーバーで実行されているすべての Lync データベースに対して同期 SQL Server ミラーリングをセットアップする、オプションのトポロジです。</span><span class="sxs-lookup"><span data-stu-id="802ba-113">This is an optional topology in which you deploy two Back End Servers for a Front End pool, and set up synchronous SQL Server mirroring for all the Lync databases running on the Back End Servers.</span></span>

<span data-ttu-id="802ba-114">プールのペアリングとバックエンドサーバーのミラーリングの詳細については、「 [Lync Server 2013 での高可用性と障害復旧の計画](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="802ba-114">For details about pool pairing and Back End Server mirroring, see [Planning for high availability and disaster recovery in Lync Server 2013](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md).</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="802ba-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="802ba-115">See Also</span></span>


[<span data-ttu-id="802ba-116">Lync Server 2013 のサーバーの役割</span><span class="sxs-lookup"><span data-stu-id="802ba-116">Server roles in Lync Server 2013</span></span>](lync-server-2013-server-roles.md)  
[<span data-ttu-id="802ba-117">Lync Server 2013 での高可用性および障害復旧の計画</span><span class="sxs-lookup"><span data-stu-id="802ba-117">Planning for high availability and disaster recovery in Lync Server 2013</span></span>](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

