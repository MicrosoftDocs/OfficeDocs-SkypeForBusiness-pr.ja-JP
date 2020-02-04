---
title: Lync Server 2013 でサポートされているプールペアリングオプションとベストプラクティス
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
ms.openlocfilehash: 9090fefba4b80f14382b9b43b5e9ced7cb36b2e0
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41764333"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="supported-pool-pairing-options-and-best-practices-for-lync-server-2013"></a><span data-ttu-id="524f0-102">サポートされているプールペアリングオプションと Lync Server 2013 のベストプラクティス</span><span class="sxs-lookup"><span data-stu-id="524f0-102">Supported pool pairing options and best practices for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="524f0-103">_**最終更新日:** 2017-03-09_</span><span class="sxs-lookup"><span data-stu-id="524f0-103">_**Topic Last Modified:** 2017-03-09_</span></span>

<span data-ttu-id="524f0-104">2つのデータセンター間の距離には制限はありません。これによって、フロントエンドプールが互いにペアリングされます。</span><span class="sxs-lookup"><span data-stu-id="524f0-104">There is no restriction on the distance between two data centers that are to include Front End pools paired with each other.</span></span> <span data-ttu-id="524f0-105">同じワールドリージョンの2つのデータセンターを使用して、その間に高速リンクを使用することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="524f0-105">We recommend that you use two data centers in the same world region, with high-speed links between them.</span></span> <span data-ttu-id="524f0-106">この2つのデータセンターは、1つの災害が同時に発生するのを避けるために、十分に分離されていることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="524f0-106">It is best if the two data centers are separated enough to avoid a single disaster hitting both at the same time.</span></span>

<span data-ttu-id="524f0-107">世界各地の2つのデータセンターを使用することは可能ですが、データレプリケーションの遅延によるデータ損失の増加につながる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="524f0-107">Having two data centers across world regions is possible, but could incur higher data loss due to latency in data replication.</span></span>

<span data-ttu-id="524f0-108">どのプールをペアにするかを計画する場合、サポートされるのは次の組み合わせのみであることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="524f0-108">When you plan which pools to pair, you must keep in mind that only the following pairings are supported:</span></span>

  - <span data-ttu-id="524f0-109">Enterprise Edition プールとペアにできるのは他の Enterprise Edition プールのみです。</span><span class="sxs-lookup"><span data-stu-id="524f0-109">Enterprise Edition pools can be paired only with other Enterprise Edition pools.</span></span> <span data-ttu-id="524f0-110">同様に、Standard Edition プールとペアにできるのは他の Standard Edition プールのみです。</span><span class="sxs-lookup"><span data-stu-id="524f0-110">Similarly, Standard Edition pools can be paired only with other Standard Edition pools.</span></span>

  - <span data-ttu-id="524f0-111">物理プールとペアにできるのは他の物理プールのみです。</span><span class="sxs-lookup"><span data-stu-id="524f0-111">Physical pools can be paired only with other physical pools.</span></span> <span data-ttu-id="524f0-112">同様に、仮想プールとペアにできるのは他の仮想プールのみです。</span><span class="sxs-lookup"><span data-stu-id="524f0-112">Similarly, virtual pools can be paired only with other virtual pools.</span></span>

  - <span data-ttu-id="524f0-113">ペアリングされているプールは、同じオペレーティングシステムを実行している必要があります。</span><span class="sxs-lookup"><span data-stu-id="524f0-113">Pools that are paired together must be running the same operating system.</span></span>

<span data-ttu-id="524f0-p104">トポロジ ビルダーでもトポロジ検証でも、この推奨事項に従わない方法で 2 つのプールをペアにする操作は阻止されません。たとえば、トポロジ ビルダーでは、Enterprise Edition プールと Standard Edition プールをペアにできます。ただし、そのような組み合わせのペアはサポートされません。</span><span class="sxs-lookup"><span data-stu-id="524f0-p104">Neither Topology Builder nor topology validation will prohibit pairing two pools in a way that does not follow these recommendations. For example, Topology Builder allows you to pair an Enterprise Edition pool with a Standard Edition pool. However, these types of pairings are not supported.</span></span>

<span data-ttu-id="524f0-117">1組の各プールには、障害が発生した場合に両方のプールのすべてのユーザーに対してサービスを提供する能力が必要です。</span><span class="sxs-lookup"><span data-stu-id="524f0-117">Each pool in a pair should have the capacity to serve all users from both pools in the event of a disaster.</span></span>

<span data-ttu-id="524f0-118">Enterprise Edition プールをペアとして使用する場合は、バックエンドサーバーに高可用性を実装することもできますが、Standard Edition プールのペアには、障害回復の手段のみが用意されています。</span><span class="sxs-lookup"><span data-stu-id="524f0-118">If you pair Enterprise Edition pools, you can also implement high availability on the Back End Servers, but for pairs of Standard Edition pools only the disaster recovery measures are available.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

