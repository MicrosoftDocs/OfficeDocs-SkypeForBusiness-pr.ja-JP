---
title: 'Lync Server 2013: ユーザーの場所'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: User's location
ms:assetid: ce57941d-086b-448e-8ada-c7d636a2a1c9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994073(v=OCS.15)
ms:contentKeyID: 51803984
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d18ef5092f0506951dd9b431c6a44945b87b7f92
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/19/2020
ms.locfileid: "42140780"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="users-location-in-lync-server-2013"></a><span data-ttu-id="54d7f-102">Lync Server 2013 のユーザーの場所</span><span class="sxs-lookup"><span data-stu-id="54d7f-102">User's location in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="54d7f-103">_**トピックの最終更新日:** 2013-03-09_</span><span class="sxs-lookup"><span data-stu-id="54d7f-103">_**Topic Last Modified:** 2013-03-09_</span></span>

<span data-ttu-id="54d7f-104">場所に基づくルーティングでは、E9-1-1、CAC、および Media バイパスで使用される Lync Server で定義されているものと同じネットワーク地域、サイト、およびサブネットを活用して、通話ルーティング制限を適用して PSTN の有料電話がバイパスされないようにします。</span><span class="sxs-lookup"><span data-stu-id="54d7f-104">Location-Based Routing leverages the same network regions, sites and subnets as defined in Lync Server used by E9-1-1, CAC and Media Bypass to apply call routing restrictions to prevent PSTN toll bypass.</span></span> <span data-ttu-id="54d7f-105">ユーザーの場所は、ユーザーの Lync エンドポイントの IP サブネットによって決まります。</span><span class="sxs-lookup"><span data-stu-id="54d7f-105">A user’s location is determined by the IP subnet of the user’s Lync endpoint(s) are connected from.</span></span> <span data-ttu-id="54d7f-106">各 IP サブネットは、管理者によって定義されたネットワーク領域に集約されたネットワークサイトに関連付けられています。</span><span class="sxs-lookup"><span data-stu-id="54d7f-106">Each IP subnet is associated to a network site, which are aggregated into network regions defined by the administrator.</span></span> <span data-ttu-id="54d7f-107">場所に基づくルーティングは、ユーザーのネットワークサイトに基づいて適用されます。</span><span class="sxs-lookup"><span data-stu-id="54d7f-107">Location-Based Routing is enforced based on the user’s network site.</span></span>

<span data-ttu-id="54d7f-108">場所に基づくルーティングルールは、ネットワークサイト単位で適用されます。つまり、指定された一連のルールが、同じネットワークサイト内に配置された場所に基づいたルーティングで有効になっているすべてのエンドポイントに適用されることを意味します。</span><span class="sxs-lookup"><span data-stu-id="54d7f-108">Location-Based Routing rules are applied on a per network site basis, meaning that a given set of rules will be applied to all endpoints enabled for Location-Based Routing that are located within the same network site.</span></span> <span data-ttu-id="54d7f-109">管理者は、場所に基づいたルーティングを必要とするネットワークサイトに適用できます。</span><span class="sxs-lookup"><span data-stu-id="54d7f-109">Administrators can apply Location-Based Routing to network sites that require it.</span></span>

<span data-ttu-id="54d7f-110">音声ルーティングポリシーをネットワークサイトごとに定義して、PSTN 電話番号を呼び出すためにネットワークサイトに配置されているすべてのユーザーが使用する特定の PSTN ゲートウェイを定義できます。</span><span class="sxs-lookup"><span data-stu-id="54d7f-110">Voice routing policies can be defined on a per network site basis to define a particular PSTN gateway that should be used by all users located in the network site to call PSTN phone numbers.</span></span> <span data-ttu-id="54d7f-111">このような音声ルーティングポリシーは、ユーザーの音声ポリシーによって、場所に基づくルーティングが有効になっているネットワークサイトにある場合に、ユーザーの音声ポリシーによって定義されたルーティングよりも優先されます。場所に基づくルーティング。</span><span class="sxs-lookup"><span data-stu-id="54d7f-111">Such voice routing policies will take precedence over the routing defined by the user’s voice policy when the user is located in a network site enabled for Location-Based Routing, and it will prevent the routing of calls via other PSTN gateways that are enabled for Location-Based Routing.</span></span> <span data-ttu-id="54d7f-112">Lync ユーザーが PSTN 通話を行うと、ユーザーの音声ポリシーによって、ユーザーが通話を行うことを承認できるかどうかが決定されます。</span><span class="sxs-lookup"><span data-stu-id="54d7f-112">When a Lync user places a PSTN call, the user’s voice policy determines whether the user can be authorized to place the call.</span></span> <span data-ttu-id="54d7f-113">ユーザーの音声ポリシーによってユーザーが通話を発信できるようにすると、場所に基づくルーティングによって、呼び出しの出口を決める PSTN ゲートウェイが決まります。</span><span class="sxs-lookup"><span data-stu-id="54d7f-113">If the user’s voice policy allows the user to place the call, Location-Based Routing determines which PSTN gateway the call should egress from.</span></span> <span data-ttu-id="54d7f-114">場所に基づくルーティングでは、ユーザーの場所に基づいて、この判断が行われます。</span><span class="sxs-lookup"><span data-stu-id="54d7f-114">Location-Based Routing makes this determination based on the user’s location.</span></span>

<span data-ttu-id="54d7f-115">ユーザーの場所は、次の方法で分類できます。</span><span class="sxs-lookup"><span data-stu-id="54d7f-115">A user location can be categorized in the following ways:</span></span>

  - <span data-ttu-id="54d7f-116">ユーザーは、同じネットワークサイト (つまり、office) に配置された PSTN ゲートウェイで、場所に基づいたルーティングと彼の DID (直接の外線番号) を使用できる既知のネットワークサイトにあります。</span><span class="sxs-lookup"><span data-stu-id="54d7f-116">The user is located in a known network site enabled for Location-Based Routing and his DID (Direct Inward Dial) number terminates on a PSTN gateway placed in the same network site (i.e. office).</span></span> <span data-ttu-id="54d7f-117">発信通話のルーティングは、ユーザーが配置されているネットワークサイトの音声ルーティングポリシーによって行われます。</span><span class="sxs-lookup"><span data-stu-id="54d7f-117">The routing of outbound calls will be through the voice routing policy of the network site in which the user is located.</span></span> <span data-ttu-id="54d7f-118">ユーザーへの PSTN 通話の着信は、PSTN ゲートウェイと同じネットワークサイトにあるエンドポイントにルーティングされます。</span><span class="sxs-lookup"><span data-stu-id="54d7f-118">Incoming PSTN calls to the user are routed to endpoints that are located in the same network site as the PSTN gateway.</span></span>

  - <span data-ttu-id="54d7f-119">ユーザーは、PSTN ゲートウェイが配置されているネットワークサイトとは異なる、既知のネットワークサイトにあります。</span><span class="sxs-lookup"><span data-stu-id="54d7f-119">The user is located in a known network site that is in different from the network site where the PSTN gateway is located.</span></span> <span data-ttu-id="54d7f-120">(つまり、ユーザーが別の会社のオフィスに旅行した)。</span><span class="sxs-lookup"><span data-stu-id="54d7f-120">(i.e. the user traveled to another corporate office).</span></span> <span data-ttu-id="54d7f-121">発信通話のルーティングは、ユーザーが配置されているネットワークサイトの音声ルーティングポリシーを使用して行われます。</span><span class="sxs-lookup"><span data-stu-id="54d7f-121">The routing of outbound calls will be using the voice routing policy of the network site in which the user is located.</span></span> <span data-ttu-id="54d7f-122">ユーザーへの PSTN 通話の着信は、pstn ゲートウェイ以外のサイトにあるエンドポイントにルーティングされないため、pstn の有料電話番号はバイパスされます。</span><span class="sxs-lookup"><span data-stu-id="54d7f-122">Incoming PSTN calls to the user will not be routed to endpoints that are located in different sites than the PSTN gateway to prevent PSTN toll bypassing.</span></span>

  - <span data-ttu-id="54d7f-123">ユーザーが Lync Server の展開において不明なネットワークサイトに配置されている場合、発信通話のルーティングは、ユーザーに割り当てられた音声ポリシーに基づいて、場所に基づくルーティング制限にバインドされていない PSTN ゲートウェイに基づきます。</span><span class="sxs-lookup"><span data-stu-id="54d7f-123">When a user is located in a network site that is unknown to the Lync Server deployment, the routing of outbound calls will be based on the voice policy assigned to the user to PSTN gateways not bound to Location-Based Routing restrictions.</span></span> <span data-ttu-id="54d7f-124">着信 PSTN 通話は、不明なネットワークサイトに配置されているエンドポイントにルーティングされないため、PSTN の有料通話はバイパスされます。</span><span class="sxs-lookup"><span data-stu-id="54d7f-124">Incoming PSTN calls will not be routed to endpoints that are located in unknown network sites to prevent PSTN toll bypassing.</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="54d7f-125">関連項目</span><span class="sxs-lookup"><span data-stu-id="54d7f-125">See Also</span></span>


[<span data-ttu-id="54d7f-126">Lync Server 2013 での場所に基づくルーティングのガイダンス</span><span class="sxs-lookup"><span data-stu-id="54d7f-126">Guidance for Location-Based Routing in Lync Server 2013</span></span>](lync-server-2013-guidance-for-location-based-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

