---
title: Lync Server 2013 と Lync Server 2010 の大都市サイト復元の互換性
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Lync Server 2010 metropolitan site resiliency
ms:assetid: 18673ff6-b664-4a57-a89b-cbda8b129e6a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204715(v=OCS.15)
ms:contentKeyID: 48183526
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 04b3cca41b0ea7a7060e6349127dc7c7fb1732ea
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/16/2020
ms.locfileid: "48526054"
---
# <a name="lync-server-2010-metropolitan-site-resiliency"></a><span data-ttu-id="84a02-102">Lync Server 2010 大都市サイト復元</span><span class="sxs-lookup"><span data-stu-id="84a02-102">Lync Server 2010 metropolitan site resiliency</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="84a02-103">_**トピックの最終更新日:** 2014-03-19_</span><span class="sxs-lookup"><span data-stu-id="84a02-103">_**Topic Last Modified:** 2014-03-19_</span></span>

<span data-ttu-id="84a02-104">Lync server 2010 でサポートされている大都市サイト復元ソリューションは、Lync Server 2013 ではサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="84a02-104">The metropolitan site resiliency solution supported for Lync Server 2010 is not supported for Lync Server 2013.</span></span> <span data-ttu-id="84a02-105">このソリューションでは、1 つのフロントエンド プールを同じ大都市圏内の 2 か所のデータ センターにまたがって展開する必要がありました。</span><span class="sxs-lookup"><span data-stu-id="84a02-105">This solution involved spanning a single Front End pool across two data centers in the same metropolitan area.</span></span>

<span data-ttu-id="84a02-106">大都市サイト復元ソリューションは、データセンター全体の損失から復旧するように設計されています。</span><span class="sxs-lookup"><span data-stu-id="84a02-106">The metropolitan site resiliency solution was designed to recover from the loss of a full datacenter.</span></span> <span data-ttu-id="84a02-107">プールを2つのデータセンターにまたがっている場合、通常はフロントエンドの半分を1つのデータセンターに配置し、2番目のデータセンターの残りの半分にします。</span><span class="sxs-lookup"><span data-stu-id="84a02-107">When you span your pool across two datacenters, you typically put half of your front ends in one datacenter and the other half in the second datacenter.</span></span> <span data-ttu-id="84a02-108">データセンター全体を失った場合は、フロントエンドサーバーの半分が失われます。</span><span class="sxs-lookup"><span data-stu-id="84a02-108">If you lose an entire datacenter, you have lost half of your Front End Servers.</span></span> <span data-ttu-id="84a02-109">これにより、Lync Server 2013 のフロントエンドプールの新しい分散システムモデルで問題が発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="84a02-109">This can cause issues with the new distributed system model for Front End Pools in Lync Server 2013.</span></span> <span data-ttu-id="84a02-110">詳細については、「 [Lync Server 2013 でのフロントエンドサーバー、インスタントメッセージング、およびプレゼンスのトポロジとコンポーネント](lync-server-2013-topologies-and-components-for-front-end-servers-instant-messaging-and-presence.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="84a02-110">For more information, see [Topologies and components for Front End Servers, instant messaging, and presence in Lync Server 2013](lync-server-2013-topologies-and-components-for-front-end-servers-instant-messaging-and-presence.md).</span></span>

</div>

<span> </span>

</div>

</div>

</div>

