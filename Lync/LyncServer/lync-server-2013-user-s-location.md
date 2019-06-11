---
title: 'Lync Server 2013: ユーザーの場所'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: User's location
ms:assetid: ce57941d-086b-448e-8ada-c7d636a2a1c9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994073(v=OCS.15)
ms:contentKeyID: 51803984
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4e9eac8fce71d99e0817c57841e2539ed6423f2a
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34848339"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="users-location-in-lync-server-2013"></a><span data-ttu-id="0c5b8-102">Lync Server 2013 のユーザーの場所</span><span class="sxs-lookup"><span data-stu-id="0c5b8-102">User's location in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0c5b8-103">_**最終更新日:** 2013-03-09_</span><span class="sxs-lookup"><span data-stu-id="0c5b8-103">_**Topic Last Modified:** 2013-03-09_</span></span>

<span data-ttu-id="0c5b8-104">位置情報に基づくルーティングでは、E9 によって使用されている Lync Server で定義されているものと同じネットワーク領域、サイト、サブネットを活用します。これには、着信ルーティングの制限を適用して、PSTN の有料サービスを回避するための通話ルーティング制限を適用します。</span><span class="sxs-lookup"><span data-stu-id="0c5b8-104">Location-Based Routing leverages the same network regions, sites and subnets as defined in Lync Server used by E9-1-1, CAC and Media Bypass to apply call routing restrictions to prevent PSTN toll bypass.</span></span> <span data-ttu-id="0c5b8-105">ユーザーの位置情報は、ユーザーの Lync エンドポイントの IP サブネットによって接続されます。</span><span class="sxs-lookup"><span data-stu-id="0c5b8-105">A user’s location is determined by the IP subnet of the user’s Lync endpoint(s) are connected from.</span></span> <span data-ttu-id="0c5b8-106">各 IP サブネットは、ネットワーク サイトに関連付けられ、管理者が定義したネットワーク地域に集約されます。</span><span class="sxs-lookup"><span data-stu-id="0c5b8-106">Each IP subnet is associated to a network site, which are aggregated into network regions defined by the administrator.</span></span> <span data-ttu-id="0c5b8-107">場所に基づくルーティングは、ユーザーのネットワーク サイトに基づいて適用されます。</span><span class="sxs-lookup"><span data-stu-id="0c5b8-107">Location-Based Routing is enforced based on the user’s network site.</span></span>

<span data-ttu-id="0c5b8-108">位置に基づくルーティングルールは、ネットワークサイトベースで適用されます。つまり、同じネットワークサイト内に配置されている、位置情報に基づくルーティングで有効になっているすべてのエンドポイントに、指定したルールセットが適用されます。</span><span class="sxs-lookup"><span data-stu-id="0c5b8-108">Location-Based Routing rules are applied on a per network site basis, meaning that a given set of rules will be applied to all endpoints enabled for Location-Based Routing that are located within the same network site.</span></span> <span data-ttu-id="0c5b8-109">管理者は、必要なネットワークサイトに位置情報に基づくルーティングを適用できます。</span><span class="sxs-lookup"><span data-stu-id="0c5b8-109">Administrators can apply Location-Based Routing to network sites that require it.</span></span>

<span data-ttu-id="0c5b8-110">ボイスルーティングポリシーは、ネットワークサイトごとに定義できます。このような特定の PSTN ゲートウェイは、ネットワークサイト内のすべてのユーザーが PSTN 電話番号に発信するために使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="0c5b8-110">Voice routing policies can be defined on a per network site basis to define a particular PSTN gateway that should be used by all users located in the network site to call PSTN phone numbers.</span></span> <span data-ttu-id="0c5b8-111">このような音声ルーティングポリシーは、ユーザーのボイスポリシーによって定義されたルーティングよりも、位置ベースのルーティングが有効になっているネットワークサイトに配置されている場合に優先されます。位置情報に基づくルーティング。</span><span class="sxs-lookup"><span data-stu-id="0c5b8-111">Such voice routing policies will take precedence over the routing defined by the user’s voice policy when the user is located in a network site enabled for Location-Based Routing, and it will prevent the routing of calls via other PSTN gateways that are enabled for Location-Based Routing.</span></span> <span data-ttu-id="0c5b8-112">Lync ユーザーが PSTN 通話を発信すると、ユーザーの音声ポリシーによって、そのユーザーが通話を発信することを許可されているかどうかが決定されます。</span><span class="sxs-lookup"><span data-stu-id="0c5b8-112">When a Lync user places a PSTN call, the user’s voice policy determines whether the user can be authorized to place the call.</span></span> <span data-ttu-id="0c5b8-113">ユーザーの音声ポリシーで通話を発信できる場合は、位置ベースのルーティングによって、通話の発信元となる PSTN ゲートウェイが決まります。</span><span class="sxs-lookup"><span data-stu-id="0c5b8-113">If the user’s voice policy allows the user to place the call, Location-Based Routing determines which PSTN gateway the call should egress from.</span></span> <span data-ttu-id="0c5b8-114">位置に基づくルーティングでは、ユーザーの位置に基づいてこの決定が行われます。</span><span class="sxs-lookup"><span data-stu-id="0c5b8-114">Location-Based Routing makes this determination based on the user’s location.</span></span>

<span data-ttu-id="0c5b8-115">ユーザーの場所は、次の方法で分類できます。</span><span class="sxs-lookup"><span data-stu-id="0c5b8-115">A user location can be categorized in the following ways:</span></span>

  - <span data-ttu-id="0c5b8-116">ユーザーは、同じネットワークサイト (office など) に配置された PSTN ゲートウェイで、位置情報に基づくルーティングと彼の DID (直接の内部のダイヤル) 番号を有効にした既知のネットワークサイトに存在します。</span><span class="sxs-lookup"><span data-stu-id="0c5b8-116">The user is located in a known network site enabled for Location-Based Routing and his DID (Direct Inward Dial) number terminates on a PSTN gateway placed in the same network site (i.e. office).</span></span> <span data-ttu-id="0c5b8-117">発信通話のルーティングは、ユーザーが配置されているネットワークサイトの音声ルーティングポリシーを通じて行われます。</span><span class="sxs-lookup"><span data-stu-id="0c5b8-117">The routing of outbound calls will be through the voice routing policy of the network site in which the user is located.</span></span> <span data-ttu-id="0c5b8-118">ユーザーへの着信 PSTN 通話は、PSTN ゲートウェイと同じネットワークサイトに配置されているエンドポイントにルーティングされます。</span><span class="sxs-lookup"><span data-stu-id="0c5b8-118">Incoming PSTN calls to the user are routed to endpoints that are located in the same network site as the PSTN gateway.</span></span>

  - <span data-ttu-id="0c5b8-p105">ユーザーが、PSTN ゲートウェイがあるネットワーク サイトとは異なる既知のネットワーク サイトに位置する (ユーザーが企業内の別のオフィスに出張している場合など)。発信通話のルーティングでは、ユーザーが位置するネットワーク サイトの音声ルーティング ポリシーを使用します。PSTN 料が適切に課金されるようにするために、ユーザーへの着信した PSTN 通話は、PSTN ゲートウェイとは異なるサイトにあるエンドポイントにルーティングされません。</span><span class="sxs-lookup"><span data-stu-id="0c5b8-p105">The user is located in a known network site that is in different from the network site where the PSTN gateway is located. (i.e. the user traveled to another corporate office). The routing of outbound calls will be using the voice routing policy of the network site in which the user is located. Incoming PSTN calls to the user will not be routed to endpoints that are located in different sites than the PSTN gateway to prevent PSTN toll bypassing.</span></span>

  - <span data-ttu-id="0c5b8-123">Lync Server の展開には未知のネットワークサイトにいるユーザーがいる場合、発信通話のルーティングは、ユーザーに割り当てられているボイスポリシーに基づいて、位置に基づくルーティングの制限にバインドされていない PSTN ゲートウェイになります。</span><span class="sxs-lookup"><span data-stu-id="0c5b8-123">When a user is located in a network site that is unknown to the Lync Server deployment, the routing of outbound calls will be based on the voice policy assigned to the user to PSTN gateways not bound to Location-Based Routing restrictions.</span></span> <span data-ttu-id="0c5b8-124">PSTN 料が適切に課金されるようにするために、着信した PSTN 通話は、不明なネットワーク サイトにあるエンドポイントにルーティングされません。</span><span class="sxs-lookup"><span data-stu-id="0c5b8-124">Incoming PSTN calls will not be routed to endpoints that are located in unknown network sites to prevent PSTN toll bypassing.</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="0c5b8-125">関連項目</span><span class="sxs-lookup"><span data-stu-id="0c5b8-125">See Also</span></span>


[<span data-ttu-id="0c5b8-126">Lync Server 2013 の場所に基づくルーティングのガイダンス</span><span class="sxs-lookup"><span data-stu-id="0c5b8-126">Guidance for Location-Based Routing in Lync Server 2013</span></span>](lync-server-2013-guidance-for-location-based-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

