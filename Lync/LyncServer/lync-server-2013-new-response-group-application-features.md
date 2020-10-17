---
title: 'Lync Server 2013: 新しい応答グループアプリケーションの機能'
description: 'Lync Server 2013: 新しい応答グループアプリケーションの機能。'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: New Response Group application features
ms:assetid: 569544b4-fa97-429b-97e6-568afab6c19b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398373(v=OCS.15)
ms:contentKeyID: 48184196
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 191d3867758da427ade3470e78abfd417f6f00de
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48541963"
---
# <a name="new-response-group-application-features-in-lync-server-2013"></a><span data-ttu-id="9e783-103">Lync Server 2013 の新しい応答グループアプリケーション機能</span><span class="sxs-lookup"><span data-stu-id="9e783-103">New Response Group application features in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9e783-104">_**トピックの最終更新日:** 2012-10-29_</span><span class="sxs-lookup"><span data-stu-id="9e783-104">_**Topic Last Modified:** 2012-10-29_</span></span>

<span data-ttu-id="9e783-105">応答グループ アプリケーションを使用すると、カスタマー サービス、社内のヘルプ デスク、またはある部門の一般的な電話サポートなど、特定の目的のために指定したユーザーに着信通話をルーティングして待機させることができます。</span><span class="sxs-lookup"><span data-stu-id="9e783-105">With the Response Group application, you can route and queue incoming calls to designated persons for special purposes, such as customer service, an internal help desk, or general telephone support for a department.</span></span>

<span data-ttu-id="9e783-106">Lync Server 2013 の新しい応答グループアプリケーション機能は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="9e783-106">The following Response Group application features are new in Lync Server 2013:</span></span>

  - <span data-ttu-id="9e783-107">**マネージャーの役割**</span><span class="sxs-lookup"><span data-stu-id="9e783-107">**Manager role**</span></span>
    
    <span data-ttu-id="9e783-108">Lync Server 2013 には、新しい応答グループマネージャーの役割が導入されています。</span><span class="sxs-lookup"><span data-stu-id="9e783-108">Lync Server 2013 introduces a new Response Group Manager role.</span></span> <span data-ttu-id="9e783-109">応答グループには、応答グループマネージャーと応答グループ管理という2つの管理役割があります。</span><span class="sxs-lookup"><span data-stu-id="9e783-109">Now there are two management roles for response groups: Response Group Manager and Response Group Administrator.</span></span> <span data-ttu-id="9e783-110">応答グループ管理者は、すべての応答グループに対して任意の要素を構成できますが、マネージャーは、自分が所有する応答グループに対してのみ特定の要素のみを構成できます。</span><span class="sxs-lookup"><span data-stu-id="9e783-110">While Response Group Administrators can still configure any element for any response group, Managers can configure only certain elements, only for response groups they own.</span></span>
    
    <span data-ttu-id="9e783-111">管理モデルのこの強化により、特に大規模な展開シナリオで応答グループの拡張性にメリットがもたらされます。</span><span class="sxs-lookup"><span data-stu-id="9e783-111">This improvement in the administration model benefits Response Group scalability, especially for large deployment scenarios.</span></span>

  - <span data-ttu-id="9e783-112">**高可用性**</span><span class="sxs-lookup"><span data-stu-id="9e783-112">**High availability**</span></span>
    
    <span data-ttu-id="9e783-113">応答グループアプリケーションの高可用性サポートは、SQL Server ミラーリングの形式で、Lync Server 2013 の高可用性の全体的な構成および展開の一部として有効になっています。</span><span class="sxs-lookup"><span data-stu-id="9e783-113">High availability support for the Response Group application, in the form of SQL Server mirroring, is enabled as part of the overall configuration and deployment of high availability for Lync Server 2013.</span></span> <span data-ttu-id="9e783-114">高可用性を構成すると、プライマリ バックエンド サーバーへの接続が失われた場合でも、ミラー化されたバックエンド サーバーを利用できるため、応答グループの機能に影響を及ぼすことはありません。</span><span class="sxs-lookup"><span data-stu-id="9e783-114">If you configure for high availability and lose connectivity to the primary back-end server, Response Group functionality is not affected by leveraging the mirrored back-end server.</span></span>
    
    <span data-ttu-id="9e783-115">応答グループアプリケーションの SQL Server ミラーリングのサポートは、Lync Server 2013 高可用性構成の外部で個別に有効化または構成することはできません。</span><span class="sxs-lookup"><span data-stu-id="9e783-115">Support for SQL Server mirroring for the Response Group application can’t be individually enabled or configured outside of the overall Lync Server 2013 high availability configuration.</span></span>

  - <span data-ttu-id="9e783-116">**障害回復**</span><span class="sxs-lookup"><span data-stu-id="9e783-116">**Disaster recovery**</span></span>
    
    <span data-ttu-id="9e783-117">応答グループアプリケーションの障害復旧のサポートは、対になっているフロントエンドプールの構成および展開の一環として有効になります。これは、Lync Server 2013 の障害復旧構成全体の一部です。</span><span class="sxs-lookup"><span data-stu-id="9e783-117">Disaster recovery support for the Response Group application is enabled as part of the configuration and deployment of the paired Front End pools, which are part of the overall Lync Server 2013 disaster recovery configuration.</span></span> <span data-ttu-id="9e783-118">また、応答グループのインポート/エクスポート コマンドレットは、バックアップ プールへのフェールオーバー プロセスと、プライマリ プールまたは新しいプールへのフェールバック プロセスをサポートします。</span><span class="sxs-lookup"><span data-stu-id="9e783-118">In addition, Response Group import and export cmdlets support the failover process to the backup pool and the failback process to the primary pool or to a new pool.</span></span> <span data-ttu-id="9e783-119">プライマリ プールで機能停止が発生した場合、応答グループをバックアップ プールにフェールオーバーし、機能が回復したら、プライマリ プールまたは新しいプールにフェールバックできます。</span><span class="sxs-lookup"><span data-stu-id="9e783-119">If an outage occurs in the primary pool, response groups can be failed over to the backup pool, and then failed back to the primary pool or to a new pool when the outage is over.</span></span>

<div id="sectionSection0" class="section">

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="9e783-120">関連項目</span><span class="sxs-lookup"><span data-stu-id="9e783-120">See Also</span></span>


[<span data-ttu-id="9e783-121">Lync Server 2013 での応答グループの計画</span><span class="sxs-lookup"><span data-stu-id="9e783-121">Planning for response groups in Lync Server 2013</span></span>](lync-server-2013-planning-for-response-groups.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

