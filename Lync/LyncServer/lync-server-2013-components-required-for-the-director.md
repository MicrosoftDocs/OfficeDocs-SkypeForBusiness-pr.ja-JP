---
title: 'Lync Server 2013: ディレクターに必要なコンポーネント'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Components required for the Director
ms:assetid: 15c7c8d4-b93f-4386-b2d1-d76dab8f801e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398228(v=OCS.15)
ms:contentKeyID: 48183502
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 12db97a72a9882964727edd3084e0bd598527358
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41757091"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="components-required-for-the-director-in-lync-server-2013"></a><span data-ttu-id="9a529-102">Lync Server 2013 のディレクターに必要なコンポーネント</span><span class="sxs-lookup"><span data-stu-id="9a529-102">Components required for the Director in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9a529-103">_**最終更新日:** 2012-09-08_</span><span class="sxs-lookup"><span data-stu-id="9a529-103">_**Topic Last Modified:** 2012-09-08_</span></span>

<span data-ttu-id="9a529-104">ディレクターを作成して構成するために必要なコンポーネントは、ディレクターサーバーの役割を展開することだけです。</span><span class="sxs-lookup"><span data-stu-id="9a529-104">The only component required to create and configure a Director is to deploy the Director server role.</span></span> <span data-ttu-id="9a529-105">これを行うには、トポロジビルダーを使用し、1台のコンピュータープールまたはディレクタープールノードの複数のコンピュータープールを定義します。</span><span class="sxs-lookup"><span data-stu-id="9a529-105">You do this by using Topology Builder and define either a single computer pool or a multiple computer pool in the Director pool node.</span></span> <span data-ttu-id="9a529-106">ディレクターまたはディレクタープールを定義したら、ディレクターになるコンピューターで Lync Server Deployment ウィザードを実行します。</span><span class="sxs-lookup"><span data-stu-id="9a529-106">After you have defined the Director or Director pool, run the Lync Server Deployment Wizard on the computer that will be a Director.</span></span> <span data-ttu-id="9a529-107">ディレクタープールの場合は、プールのメンバーになっている各サーバーで Lync Server Deployment ウィザードを実行します。</span><span class="sxs-lookup"><span data-stu-id="9a529-107">In the case of a Director pool, you run the Lync Server Deployment Wizard on each server that will be a member of the pool.</span></span>

<div>

## <a name="topologies"></a><span data-ttu-id="9a529-108">トポロジー</span><span class="sxs-lookup"><span data-stu-id="9a529-108">Topologies</span></span>

<span data-ttu-id="9a529-109">1つのディレクターサーバーまたはディレクタープールを実装できます。</span><span class="sxs-lookup"><span data-stu-id="9a529-109">You can implement a single Director server or a Director pool.</span></span> <span data-ttu-id="9a529-110">ディレクターは常に個別のサーバーまたはプールであり、Lync Server 2013 では他のサーバーの役割とは関係ありません。</span><span class="sxs-lookup"><span data-stu-id="9a529-110">The Director is always a separate server or pool, not collocated with any other server role in Lync Server 2013.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="9a529-111">ディレクターを展開しない場合は、フロントエンドサーバーまたはフロントエンドプールによってディレクターの役割が想定されます。</span><span class="sxs-lookup"><span data-stu-id="9a529-111">If you do not deploy Directors, the Front End Server or Front End pool will assume the Director role.</span></span>



</div>

<span data-ttu-id="9a529-112">ディレクターのプールは、負荷分散されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="9a529-112">A pool of Directors must be load balanced.</span></span> <span data-ttu-id="9a529-113">次のいずれかの操作を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="9a529-113">You can do one of the following:</span></span>

  - <span data-ttu-id="9a529-114">その他の種類のトラフィックに対して、web サービスとドメインネームシステム (DNS) 負荷分散用のハードウェアロードバランサーを使用するトポロジを作成します。</span><span class="sxs-lookup"><span data-stu-id="9a529-114">Create a topology that uses a hardware load balancer for web services and Domain Name System (DNS) load balancing for the other traffic types.</span></span>
    
    [<span data-ttu-id="9a529-115">拡張ディレクター プール - Lync Server 2013 の DNS 負荷分散とロード バランサー機器</span><span class="sxs-lookup"><span data-stu-id="9a529-115">Scaled Director pool - DNS load balancing and hardware load balancer in Lync Server 2013</span></span>](lync-server-2013-scaled-director-pool-dns-load-balancing-and-hardware-load-balancer.md)

  - <span data-ttu-id="9a529-116">ハードウェアロードバランサーを使用するトポロジを作成して、ディレクタープールに必要な負荷分散を行います。</span><span class="sxs-lookup"><span data-stu-id="9a529-116">Create a topology that uses a hardware load balancer for load balancing needed for the Director pool.</span></span>
    
    [<span data-ttu-id="9a529-117">拡張ディレクター プール - Lync Server 2013 のハードウェア負荷分散</span><span class="sxs-lookup"><span data-stu-id="9a529-117">Scaled Director pool - hardware load balancer in Lync Server 2013</span></span>](lync-server-2013-scaled-director-pool-hardware-load-balancer.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

