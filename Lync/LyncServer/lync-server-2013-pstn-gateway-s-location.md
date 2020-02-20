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
ms.openlocfilehash: ef9c58115349e8fedaf25d6f8bc4e1991b65a963
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/19/2020
ms.locfileid: "42152311"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="pstn-gateways-location-in-lync-server-2013"></a><span data-ttu-id="be06c-102">Lync Server 2013 の PSTN ゲートウェイの場所</span><span class="sxs-lookup"><span data-stu-id="be06c-102">PSTN gateway's location in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="be06c-103">_**トピックの最終更新日:** 2013-03-09_</span><span class="sxs-lookup"><span data-stu-id="be06c-103">_**Topic Last Modified:** 2013-03-09_</span></span>

<span data-ttu-id="be06c-104">PSTN ゲートウェイおよび Pbx 経由でルーティングされる通話には、そのようなシステムの場所に応じて、場所に基づくルーティング制限が必要になることがあります。</span><span class="sxs-lookup"><span data-stu-id="be06c-104">Calls routed via PSTN gateways and PBXs might require Location-Based Routing restrictions depending on the location of such systems.</span></span> <span data-ttu-id="be06c-105">場所に基づくルーティングは、トランクごとの粒度で有効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="be06c-105">Location-Based Routing can be enabled at the granularity on a per trunk basis.</span></span>

<span data-ttu-id="be06c-106">場所に基づくルーティングでは、トランクに対して有効になっている場合、次のルールセットが導入されます。</span><span class="sxs-lookup"><span data-stu-id="be06c-106">Location-Based Routing introduces the following set of rules when enabled on a trunk:</span></span>

  - <span data-ttu-id="be06c-107">場所に基づくルーティングがトランクごとに有効になっている場合、そのトランクで定義されたルールは、そのトランクを経由してルーティングされる通話にのみ適用されます。</span><span class="sxs-lookup"><span data-stu-id="be06c-107">When Location-Based Routing is enabled on a per trunk basis, the rules define on that trunk will be applied only to calls routed through that trunk.</span></span>

  - <span data-ttu-id="be06c-108">Pstn ゲートウェイが配置されているネットワークサイトとは異なり、ネットワークサイトから呼び出しが行われる pstn かからないがバイパスされないようにするために、場所に基づいたルーティングによって、特定のトランクへのネットワークサイトの関連付けが導入されます。</span><span class="sxs-lookup"><span data-stu-id="be06c-108">To prevent PSTN tolls bypass where calls originate from a network site different that the network site where the PSTN gateway is located, Location-Based Routing introduces the association of a network site to a given trunk.</span></span> <span data-ttu-id="be06c-109">これにより、特定のトランクに対して呼び出しをルーティングできるようにするネットワークサイトが定義されます。</span><span class="sxs-lookup"><span data-stu-id="be06c-109">This defines the network site that allows calls to be routed to a given trunk.</span></span>

<span data-ttu-id="be06c-110">トランクは、次の2つの方法で場所に基づくルーティングに対して有効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="be06c-110">Trunks can be enabled for Location-Based Routing in two ways:</span></span>

  - <span data-ttu-id="be06c-111">トランクは、pstn への通話を egresses する PSTN ゲートウェイに対して定義されています。</span><span class="sxs-lookup"><span data-stu-id="be06c-111">The trunk is defined for a PSTN gateway that egresses calls to the PSTN.</span></span> <span data-ttu-id="be06c-112">この種類のトランクによってルーティングされる着信呼び出しは、トランクと同じネットワークサイト内にあるエンドポイントにのみルーティングされます。</span><span class="sxs-lookup"><span data-stu-id="be06c-112">Incoming calls routed by a trunk of this type will be routed only to endpoints located within the same network site as the trunk.</span></span>

  - <span data-ttu-id="be06c-113">このトランクは、PSTN への通話を発信しない仲介サーバーピアに対して定義されており、固定の場所 (PBX 電話) で従来の電話を使用しているユーザーをサービスします。</span><span class="sxs-lookup"><span data-stu-id="be06c-113">The trunk is defined for a Mediation Server peer that doesn’t egress calls to the PSTN and services users with legacy phones in a static locations (i.e. PBX phones).</span></span> <span data-ttu-id="be06c-114">この構成では、この種類のトランクによってルーティングされるすべての着信呼び出しは、トランクと同じネットワークサイトから発信されるものと見なされます。</span><span class="sxs-lookup"><span data-stu-id="be06c-114">For this particular configuration, all incoming calls routed by a trunk of this type will be considered to be originating from the same network site as the trunk.</span></span> <span data-ttu-id="be06c-115">PBX ユーザーからの呼び出しでは、トランクと同じネットワークサイトにある Lync ユーザーと同じ場所に基づいたルーティングの実施が行われます。</span><span class="sxs-lookup"><span data-stu-id="be06c-115">Calls from PBX users will have the same Location-Based Routing enforcement as Lync users who are located in the same network site as the trunk.</span></span> <span data-ttu-id="be06c-116">別のネットワークサイトにある2つの PBX システムが Lync Server を介して接続されている場合は、場所に基づくルーティングによって、あるネットワークサイト内の1つの PBX エンドポイントから別の PBX エンドポイントへのルーティングが可能になります。</span><span class="sxs-lookup"><span data-stu-id="be06c-116">If two PBX systems located in separate network sites are connected through Lync Server, Location-Based Routing will allow routing from one PBX endpoint in one network site to another PBX endpoint in the other network site.</span></span> <span data-ttu-id="be06c-117">このシナリオは、場所に基づくルーティングによってブロックされることはありません。</span><span class="sxs-lookup"><span data-stu-id="be06c-117">This scenario will not be blocked by Location-Based Routing.</span></span> <span data-ttu-id="be06c-118">このシナリオだけでなく、同じ場所にある Lync ユーザーと同様の方法で、この構成の仲介サーバーピアに接続されているエンドポイントは、PSTN への通話をルーティングしない他の仲介サーバーピアとの通話を発信または受信できます。e.i は、仲介サーバーピアが関連付けられているネットワークサイトに関係なく、別の PBX に接続されたエンドポイントです。</span><span class="sxs-lookup"><span data-stu-id="be06c-118">In addition to this scenario and in a similar way as a Lync user in the same location, endpoints connected to a Mediation Server peer with this configuration will be able to make or receive calls to and from other Mediation Server peer that do not route calls to the PSTN (i.e. an endpoint connected to a different PBX) regardless of the network site to which the Mediation Server peer is associated.</span></span> <span data-ttu-id="be06c-119">PSTN エンドポイントを使用するすべての着信呼び出し、発信呼び出し、通話転送、および着信転送は、このような仲介サーバーピアのローカルとして定義されている PSTN ゲートウェイのみを使用するために、場所に基づいたルーティングの対象となります。</span><span class="sxs-lookup"><span data-stu-id="be06c-119">All inbound calls, outbound calls, call transfers and call forwards involving PSTN endpoints will be subject to Location Based Routing to use only PSTN gateways that are defined as local to such Mediation Server peer.</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="be06c-120">関連項目</span><span class="sxs-lookup"><span data-stu-id="be06c-120">See Also</span></span>


[<span data-ttu-id="be06c-121">Lync Server 2013 での場所に基づくルーティングのガイダンス</span><span class="sxs-lookup"><span data-stu-id="be06c-121">Guidance for Location-Based Routing in Lync Server 2013</span></span>](lync-server-2013-guidance-for-location-based-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

