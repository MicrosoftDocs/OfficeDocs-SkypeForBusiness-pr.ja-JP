---
title: Lync Server 2013 サポートされているプールのペアのオプションとベストプラクティス
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Supported pool pairing options and best practices
ms:assetid: 142caf34-0f20-47f3-9d32-ce25ab622fad
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204697(v=OCS.15)
ms:contentKeyID: 48183478
ms.date: 03/09/2017
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 90e1c28e6c16a7008232ef65d91cd252a3e2855f
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/16/2020
ms.locfileid: "48524014"
---
# <a name="supported-pool-pairing-options-and-best-practices-for-lync-server-2013"></a><span data-ttu-id="30e33-102">Lync Server 2013 でサポートされているプールのペアのオプションとベストプラクティス</span><span class="sxs-lookup"><span data-stu-id="30e33-102">Supported pool pairing options and best practices for Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="30e33-103">_**トピックの最終更新日:** 2017-03-09_</span><span class="sxs-lookup"><span data-stu-id="30e33-103">_**Topic Last Modified:** 2017-03-09_</span></span>

<span data-ttu-id="30e33-p101">相互にペアとなるフロントエンド プールが含まれる 2 つのデータ センター間の距離に制限はありません。同一地域内の 2 つのデータ センターを高速リンクで接続して使用することをお勧めします。2 つのデータ センターが両方とも同時に同じ障害の影響を受けないように、両者を十分に分離することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="30e33-p101">There is no restriction on the distance between two data centers that are to include Front End pools paired with each other. We recommend that you use two data centers in the same world region, with high-speed links between them. It is best if the two data centers are separated enough to avoid a single disaster hitting both at the same time.</span></span>

<span data-ttu-id="30e33-107">異なる地域にある 2 つのデータ センターを使用することもできますが、データ レプリケーションの待ち時間が原因でデータ損失が発生する可能性が高くなります。</span><span class="sxs-lookup"><span data-stu-id="30e33-107">Having two data centers across world regions is possible, but could incur higher data loss due to latency in data replication.</span></span>

<span data-ttu-id="30e33-108">どのプールをペアにするかを計画するときは、次の組み合わせのみがサポートされることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="30e33-108">When you plan which pools to pair, you must keep in mind that only the following pairings are supported:</span></span>

  - <span data-ttu-id="30e33-p102">Enterprise Edition プールとペアにできるのは他の Enterprise Edition プールのみです。同様に、Standard Edition プールとペアにできるのは他の Standard Edition プールのみです。</span><span class="sxs-lookup"><span data-stu-id="30e33-p102">Enterprise Edition pools can be paired only with other Enterprise Edition pools. Similarly, Standard Edition pools can be paired only with other Standard Edition pools.</span></span>

  - <span data-ttu-id="30e33-p103">物理プールとペアにできるのは他の物理プールのみです。同様に、仮想プールとペアにできるのは他の仮想プールのみです。</span><span class="sxs-lookup"><span data-stu-id="30e33-p103">Physical pools can be paired only with other physical pools. Similarly, virtual pools can be paired only with other virtual pools.</span></span>

  - <span data-ttu-id="30e33-113">ペアになっているプールは、同じオペレーティングシステムを実行している必要があります。</span><span class="sxs-lookup"><span data-stu-id="30e33-113">Pools that are paired together must be running the same operating system.</span></span>

<span data-ttu-id="30e33-114">トポロジ ビルダーでもトポロジ検証でも、この推奨事項に従わない方法で 2 つのプールをペアにする操作は阻止されません。</span><span class="sxs-lookup"><span data-stu-id="30e33-114">Neither Topology Builder nor topology validation will prohibit pairing two pools in a way that does not follow these recommendations.</span></span> <span data-ttu-id="30e33-115">たとえば、トポロジ ビルダーでは、Enterprise Edition プールと Standard Edition プールをペアにできます。</span><span class="sxs-lookup"><span data-stu-id="30e33-115">For example, Topology Builder allows you to pair an Enterprise Edition pool with a Standard Edition pool.</span></span> <span data-ttu-id="30e33-116">ただし、これらの種類の組み合わせはサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="30e33-116">However, these types of pairings are not supported.</span></span>

<span data-ttu-id="30e33-117">ペアにするどちらのプールにも、障害発生時に備えて、両方のプールのすべてのユーザーに機能を提供できる処理能力が必要です。</span><span class="sxs-lookup"><span data-stu-id="30e33-117">Each pool in a pair should have the capacity to serve all users from both pools in the event of a disaster.</span></span>

<span data-ttu-id="30e33-118">Enterprise Edition プールをペアにする場合、バックエンド サーバーに高可用性も実装できますが、Standard Edition プールのペアの場合に使用できるのは障害復旧手段のみです。</span><span class="sxs-lookup"><span data-stu-id="30e33-118">If you pair Enterprise Edition pools, you can also implement high availability on the Back End Servers, but for pairs of Standard Edition pools only the disaster recovery measures are available.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

