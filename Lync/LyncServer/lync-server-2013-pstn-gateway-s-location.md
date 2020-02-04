---
title: 'Lync Server 2013: PSTN ゲートウェイの場所'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: PSTN gateway's location
ms:assetid: 49693a35-fad3-49ee-a71e-c7e4537b79aa
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994031(v=OCS.15)
ms:contentKeyID: 51803940
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b5d15589f37b18015f91e3717e19415d5ade6b6c
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41724747"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="pstn-gateways-location-in-lync-server-2013"></a><span data-ttu-id="54f67-102">Lync Server 2013 の PSTN ゲートウェイの場所</span><span class="sxs-lookup"><span data-stu-id="54f67-102">PSTN gateway's location in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="54f67-103">_**最終更新日:** 2013-03-09_</span><span class="sxs-lookup"><span data-stu-id="54f67-103">_**Topic Last Modified:** 2013-03-09_</span></span>

<span data-ttu-id="54f67-104">PSTN ゲートウェイと Pbx 経由の通話には、そのシステムの場所に応じて位置情報に基づくルーティング制限が必要になることがあります。</span><span class="sxs-lookup"><span data-stu-id="54f67-104">Calls routed via PSTN gateways and PBXs might require Location-Based Routing restrictions depending on the location of such systems.</span></span> <span data-ttu-id="54f67-105">位置情報に基づくルーティングは、トランクごとに細分度で有効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="54f67-105">Location-Based Routing can be enabled at the granularity on a per trunk basis.</span></span>

<span data-ttu-id="54f67-106">場所に基づくルーティングでは、トランクで有効にすると、次のルールが設定されます。</span><span class="sxs-lookup"><span data-stu-id="54f67-106">Location-Based Routing introduces the following set of rules when enabled on a trunk:</span></span>

  - <span data-ttu-id="54f67-107">1回のトランクで位置情報に基づくルーティングが有効になっている場合、そのトランクで定義されたルールは、そのトランクでルーティングされる通話にのみ適用されます。</span><span class="sxs-lookup"><span data-stu-id="54f67-107">When Location-Based Routing is enabled on a per trunk basis, the rules define on that trunk will be applied only to calls routed through that trunk.</span></span>

  - <span data-ttu-id="54f67-108">Pstn tolls が、PSTN ゲートウェイが配置されているネットワークサイトとは異なるネットワークサイトから発信される場合は、場所に基づくルーティングによって、ネットワークサイトと特定のトランクとの関連付けが行われます。</span><span class="sxs-lookup"><span data-stu-id="54f67-108">To prevent PSTN tolls bypass where calls originate from a network site different that the network site where the PSTN gateway is located, Location-Based Routing introduces the association of a network site to a given trunk.</span></span> <span data-ttu-id="54f67-109">これにより、特定のトランクへの通話のルーティングを許可するネットワーク サイトが定義されます。</span><span class="sxs-lookup"><span data-stu-id="54f67-109">This defines the network site that allows calls to be routed to a given trunk.</span></span>

<span data-ttu-id="54f67-110">Trunks ベースのルーティングの場合、次の2つの方法でを有効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="54f67-110">Trunks can be enabled for Location-Based Routing in two ways:</span></span>

  - <span data-ttu-id="54f67-p103">トランクは、通話を PSTN に退出させる PSTN ゲートウェイに対して定義されています。この種のトランクによってルーティングされた着信通話は、トランクと同じネットワーク サイト内にあるエンドポイントにのみルーティングされます。</span><span class="sxs-lookup"><span data-stu-id="54f67-p103">The trunk is defined for a PSTN gateway that egresses calls to the PSTN. Incoming calls routed by a trunk of this type will be routed only to endpoints located within the same network site as the trunk.</span></span>

  - <span data-ttu-id="54f67-113">トランクは、PSTN に着信を転送しない仲介サーバーピアに対して定義されます。これは、固定の場所 (PBX 電話) で従来の電話を使用しているユーザーを対象としています。</span><span class="sxs-lookup"><span data-stu-id="54f67-113">The trunk is defined for a Mediation Server peer that doesn’t egress calls to the PSTN and services users with legacy phones in a static locations (i.e. PBX phones).</span></span> <span data-ttu-id="54f67-114">このような特定の構成の場合、この種のトランクによってルーティングされたすべての着信通話は、トランクと同じネットワーク サイトから発信されていると見なされます。</span><span class="sxs-lookup"><span data-stu-id="54f67-114">For this particular configuration, all incoming calls routed by a trunk of this type will be considered to be originating from the same network site as the trunk.</span></span> <span data-ttu-id="54f67-115">PBX ユーザーからの通話では、トランクと同じネットワークサイトに配置されている Lync ユーザーと同じ場所に基づくルーティングが適用されます。</span><span class="sxs-lookup"><span data-stu-id="54f67-115">Calls from PBX users will have the same Location-Based Routing enforcement as Lync users who are located in the same network site as the trunk.</span></span> <span data-ttu-id="54f67-116">別々のネットワークサイトに配置されている2つの PBX システムが Lync Server 経由で接続されている場合、場所に基づくルーティングによって、あるネットワークサイトの1つの PBX エンドポイントから別のネットワークサイトの別の PBX エンドポイントへのルーティングが許可されます。</span><span class="sxs-lookup"><span data-stu-id="54f67-116">If two PBX systems located in separate network sites are connected through Lync Server, Location-Based Routing will allow routing from one PBX endpoint in one network site to another PBX endpoint in the other network site.</span></span> <span data-ttu-id="54f67-117">このシナリオは、位置に基づくルーティングによってブロックされることはありません。</span><span class="sxs-lookup"><span data-stu-id="54f67-117">This scenario will not be blocked by Location-Based Routing.</span></span> <span data-ttu-id="54f67-118">このシナリオに加えて、同じ場所の Lync ユーザーと同じように、この構成の仲介サーバーピアに接続されたエンドポイントは、PSTN への通話をルーティングしない他の仲介サーバーピアとの間での通話の発信と受信を行うことができます。e: 仲介サーバーピアが関連付けられているネットワークサイトに関係なく、別の PBX に接続されているエンドポイント。</span><span class="sxs-lookup"><span data-stu-id="54f67-118">In addition to this scenario and in a similar way as a Lync user in the same location, endpoints connected to a Mediation Server peer with this configuration will be able to make or receive calls to and from other Mediation Server peer that do not route calls to the PSTN (i.e. an endpoint connected to a different PBX) regardless of the network site to which the Mediation Server peer is associated.</span></span> <span data-ttu-id="54f67-119">PSTN エンドポイントを含むすべての着信通話、発信通話、通話転送、通話転送には、位置に基づくルーティングが適用されます。この仲介サーバーピアのローカルとして定義されている PSTN ゲートウェイのみを使用します。</span><span class="sxs-lookup"><span data-stu-id="54f67-119">All inbound calls, outbound calls, call transfers and call forwards involving PSTN endpoints will be subject to Location Based Routing to use only PSTN gateways that are defined as local to such Mediation Server peer.</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="54f67-120">関連項目</span><span class="sxs-lookup"><span data-stu-id="54f67-120">See Also</span></span>


[<span data-ttu-id="54f67-121">Lync Server 2013 の場所に基づくルーティングのガイダンス</span><span class="sxs-lookup"><span data-stu-id="54f67-121">Guidance for Location-Based Routing in Lync Server 2013</span></span>](lync-server-2013-guidance-for-location-based-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

