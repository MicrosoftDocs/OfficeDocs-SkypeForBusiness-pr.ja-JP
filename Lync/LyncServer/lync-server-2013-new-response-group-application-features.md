---
title: 'Lync Server 2013: 新しい応答グループ アプリケーションの機能'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: New Response Group application features
ms:assetid: 569544b4-fa97-429b-97e6-568afab6c19b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398373(v=OCS.15)
ms:contentKeyID: 48184196
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 33dd01cf7516f950e58dbc90ee09b06901bccf74
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34826151"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="new-response-group-application-features-in-lync-server-2013"></a><span data-ttu-id="a0ccf-102">Lync Server 2013 の新しい応答グループ アプリケーションの機能</span><span class="sxs-lookup"><span data-stu-id="a0ccf-102">New Response Group application features in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a0ccf-103">_**最終更新日:** 2012-10-29_</span><span class="sxs-lookup"><span data-stu-id="a0ccf-103">_**Topic Last Modified:** 2012-10-29_</span></span>

<span data-ttu-id="a0ccf-104">応答グループアプリケーションを使用すると、顧客サービス、社内ヘルプデスク、または部門の一般的な電話のサポートなどの特殊な目的のために、指定したユーザーへの着信通話をルーティングしてキューに登録することができます。</span><span class="sxs-lookup"><span data-stu-id="a0ccf-104">With the Response Group application, you can route and queue incoming calls to designated persons for special purposes, such as customer service, an internal help desk, or general telephone support for a department.</span></span>

<span data-ttu-id="a0ccf-105">次の応答グループアプリケーション機能は、Lync Server 2013 で新しく追加されています。</span><span class="sxs-lookup"><span data-stu-id="a0ccf-105">The following Response Group application features are new in Lync Server 2013:</span></span>

  - <span data-ttu-id="a0ccf-106">**管理職の役割**</span><span class="sxs-lookup"><span data-stu-id="a0ccf-106">**Manager role**</span></span>
    
    <span data-ttu-id="a0ccf-107">Lync Server 2013 で、新しい応答グループマネージャーの役割が導入されます。</span><span class="sxs-lookup"><span data-stu-id="a0ccf-107">Lync Server 2013 introduces a new Response Group Manager role.</span></span> <span data-ttu-id="a0ccf-108">応答グループには、応答グループマネージャーと応答グループの管理者の2つの役割があります。</span><span class="sxs-lookup"><span data-stu-id="a0ccf-108">Now there are two management roles for response groups: Response Group Manager and Response Group Administrator.</span></span> <span data-ttu-id="a0ccf-109">グループ管理者は応答グループの要素をまだ構成できますが、マネージャーは、所有する応答グループに対してのみ、特定の要素のみを構成できます。</span><span class="sxs-lookup"><span data-stu-id="a0ccf-109">While Response Group Administrators can still configure any element for any response group, Managers can configure only certain elements, only for response groups they own.</span></span>
    
    <span data-ttu-id="a0ccf-110">特に大規模な展開シナリオの場合、管理モデルの改善による応答グループのスケーラビリティが向上します。</span><span class="sxs-lookup"><span data-stu-id="a0ccf-110">This improvement in the administration model benefits Response Group scalability, especially for large deployment scenarios.</span></span>

  - <span data-ttu-id="a0ccf-111">**高可用性**</span><span class="sxs-lookup"><span data-stu-id="a0ccf-111">**High availability**</span></span>
    
    <span data-ttu-id="a0ccf-112">応答グループアプリケーションの高可用性サポートは、SQL Server のミラーリングの形式でサポートされており、Lync Server 2013 の高可用性の構成と展開の一部として有効になっています。</span><span class="sxs-lookup"><span data-stu-id="a0ccf-112">High availability support for the Response Group application, in the form of SQL Server mirroring, is enabled as part of the overall configuration and deployment of high availability for Lync Server 2013.</span></span> <span data-ttu-id="a0ccf-113">高可用性を実現するように構成し、プライマリバックエンドサーバーへの接続が切断されている場合、ミラーリングされたバックエンドサーバーを活用しても、応答グループの機能に影響はありません。</span><span class="sxs-lookup"><span data-stu-id="a0ccf-113">If you configure for high availability and lose connectivity to the primary back-end server, Response Group functionality is not affected by leveraging the mirrored back-end server.</span></span>
    
    <span data-ttu-id="a0ccf-114">応答グループアプリケーションの SQL Server ミラーリングのサポートは、全体的な Lync Server 2013 高可用性構成の外部で個別に有効にしたり構成したりすることはできません。</span><span class="sxs-lookup"><span data-stu-id="a0ccf-114">Support for SQL Server mirroring for the Response Group application can’t be individually enabled or configured outside of the overall Lync Server 2013 high availability configuration.</span></span>

  - <span data-ttu-id="a0ccf-115">**障害復旧**</span><span class="sxs-lookup"><span data-stu-id="a0ccf-115">**Disaster recovery**</span></span>
    
    <span data-ttu-id="a0ccf-116">応答グループアプリケーションの障害回復のサポートは、すべての Lync Server 2013 の障害回復構成の一部である、ペアリングされたフロントエンドプールの構成と展開の一環として有効になります。</span><span class="sxs-lookup"><span data-stu-id="a0ccf-116">Disaster recovery support for the Response Group application is enabled as part of the configuration and deployment of the paired Front End pools, which are part of the overall Lync Server 2013 disaster recovery configuration.</span></span> <span data-ttu-id="a0ccf-117">さらに、応答グループのインポートとエクスポートのコマンドレットでは、バックアッププールへのフェールオーバープロセスと、プライマリプールまたは新しいプールへのフェールバック処理がサポートされています。</span><span class="sxs-lookup"><span data-stu-id="a0ccf-117">In addition, Response Group import and export cmdlets support the failover process to the backup pool and the failback process to the primary pool or to a new pool.</span></span> <span data-ttu-id="a0ccf-118">プライマリプールで障害が発生した場合、応答グループはバックアッププールにフェールオーバーされ、停止したときにプライマリプールまたは新しいプールにフェールバックすることができます。</span><span class="sxs-lookup"><span data-stu-id="a0ccf-118">If an outage occurs in the primary pool, response groups can be failed over to the backup pool, and then failed back to the primary pool or to a new pool when the outage is over.</span></span>

<div id="sectionSection0" class="section">

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="a0ccf-119">関連項目</span><span class="sxs-lookup"><span data-stu-id="a0ccf-119">See Also</span></span>


[<span data-ttu-id="a0ccf-120">Lync Server 2013 での応答グループの計画</span><span class="sxs-lookup"><span data-stu-id="a0ccf-120">Planning for response groups in Lync Server 2013</span></span>](lync-server-2013-planning-for-response-groups.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

