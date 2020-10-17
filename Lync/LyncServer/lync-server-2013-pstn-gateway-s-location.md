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
ms.openlocfilehash: 29898244dc0e54da2586d0a58212148c493b96db
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/16/2020
ms.locfileid: "48512444"
---
# <a name="pstn-gateways-location-in-lync-server-2013"></a><span data-ttu-id="cf6fb-102">Lync Server 2013 の PSTN ゲートウェイの場所</span><span class="sxs-lookup"><span data-stu-id="cf6fb-102">PSTN gateway's location in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="cf6fb-103">_**トピックの最終更新日:** 2013-03-09_</span><span class="sxs-lookup"><span data-stu-id="cf6fb-103">_**Topic Last Modified:** 2013-03-09_</span></span>

<span data-ttu-id="cf6fb-104">PSTN ゲートウェイおよび Pbx 経由でルーティングされる通話には、そのようなシステムの場所に応じて Location-Based ルーティング制限が必要になることがあります。</span><span class="sxs-lookup"><span data-stu-id="cf6fb-104">Calls routed via PSTN gateways and PBXs might require Location-Based Routing restrictions depending on the location of such systems.</span></span> <span data-ttu-id="cf6fb-105">Location-Based ルーティングは、トランクごとの粒度で有効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="cf6fb-105">Location-Based Routing can be enabled at the granularity on a per trunk basis.</span></span>

<span data-ttu-id="cf6fb-106">Location-Based ルーティングは、トランクに対して有効になっている場合に次のルールセットを導入します。</span><span class="sxs-lookup"><span data-stu-id="cf6fb-106">Location-Based Routing introduces the following set of rules when enabled on a trunk:</span></span>

  - <span data-ttu-id="cf6fb-107">Location-Based ルーティングがトランクごとに有効になっている場合、そのトランクで定義されたルールは、そのトランク経由でルーティングされる通話にのみ適用されます。</span><span class="sxs-lookup"><span data-stu-id="cf6fb-107">When Location-Based Routing is enabled on a per trunk basis, the rules define on that trunk will be applied only to calls routed through that trunk.</span></span>

  - <span data-ttu-id="cf6fb-108">Pstn ゲートウェイが存在するネットワークサイトとは異なるように、ネットワークサイトから呼び出しが行われる pstn かからないがバイパスされないようにするために、Location-Based ルーティングでは、特定のトランクへのネットワークサイトの関連付けを導入します。</span><span class="sxs-lookup"><span data-stu-id="cf6fb-108">To prevent PSTN tolls bypass where calls originate from a network site different that the network site where the PSTN gateway is located, Location-Based Routing introduces the association of a network site to a given trunk.</span></span> <span data-ttu-id="cf6fb-109">これにより、特定のトランクに対して呼び出しをルーティングできるようにするネットワークサイトが定義されます。</span><span class="sxs-lookup"><span data-stu-id="cf6fb-109">This defines the network site that allows calls to be routed to a given trunk.</span></span>

<span data-ttu-id="cf6fb-110">トランクは、次の2つの方法で Location-Based ルーティングに対して有効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="cf6fb-110">Trunks can be enabled for Location-Based Routing in two ways:</span></span>

  - <span data-ttu-id="cf6fb-111">トランクは、pstn への通話を egresses する PSTN ゲートウェイに対して定義されています。</span><span class="sxs-lookup"><span data-stu-id="cf6fb-111">The trunk is defined for a PSTN gateway that egresses calls to the PSTN.</span></span> <span data-ttu-id="cf6fb-112">この種類のトランクによってルーティングされる着信呼び出しは、トランクと同じネットワークサイト内にあるエンドポイントにのみルーティングされます。</span><span class="sxs-lookup"><span data-stu-id="cf6fb-112">Incoming calls routed by a trunk of this type will be routed only to endpoints located within the same network site as the trunk.</span></span>

  - <span data-ttu-id="cf6fb-113">このトランクは、PSTN への通話を発信しない仲介サーバーピアに対して定義されており、固定の場所 (PBX 電話) で従来の電話を使用しているユーザーをサービスします。</span><span class="sxs-lookup"><span data-stu-id="cf6fb-113">The trunk is defined for a Mediation Server peer that doesn’t egress calls to the PSTN and services users with legacy phones in a static locations (i.e. PBX phones).</span></span> <span data-ttu-id="cf6fb-114">この構成では、この種類のトランクによってルーティングされるすべての着信呼び出しは、トランクと同じネットワークサイトから発信されるものと見なされます。</span><span class="sxs-lookup"><span data-stu-id="cf6fb-114">For this particular configuration, all incoming calls routed by a trunk of this type will be considered to be originating from the same network site as the trunk.</span></span> <span data-ttu-id="cf6fb-115">PBX ユーザーからの呼び出しでは、トランクと同じネットワークサイトにある Lync ユーザーと同じ Location-Based ルーティング強制が適用されます。</span><span class="sxs-lookup"><span data-stu-id="cf6fb-115">Calls from PBX users will have the same Location-Based Routing enforcement as Lync users who are located in the same network site as the trunk.</span></span> <span data-ttu-id="cf6fb-116">別のネットワークサイトにある2つの PBX システムが Lync Server を介して接続されている場合、Location-Based ルーティングによって、あるネットワークサイト内の1つの PBX エンドポイントから別の PBX エンドポイントへのルーティングができます。</span><span class="sxs-lookup"><span data-stu-id="cf6fb-116">If two PBX systems located in separate network sites are connected through Lync Server, Location-Based Routing will allow routing from one PBX endpoint in one network site to another PBX endpoint in the other network site.</span></span> <span data-ttu-id="cf6fb-117">このシナリオは Location-Based ルーティングによってブロックされることはありません。</span><span class="sxs-lookup"><span data-stu-id="cf6fb-117">This scenario will not be blocked by Location-Based Routing.</span></span> <span data-ttu-id="cf6fb-118">このシナリオだけでなく、同じ場所にある Lync ユーザーと同様の方法で、この構成の仲介サーバーピアに接続されているエンドポイントは、仲介サーバーピアが関連付けられているネットワークサイトに関係なく、PSTN (つまり、別の PBX に接続されているエンドポイント) に対して通話を発信または受信できません。</span><span class="sxs-lookup"><span data-stu-id="cf6fb-118">In addition to this scenario and in a similar way as a Lync user in the same location, endpoints connected to a Mediation Server peer with this configuration will be able to make or receive calls to and from other Mediation Server peer that do not route calls to the PSTN (i.e. an endpoint connected to a different PBX) regardless of the network site to which the Mediation Server peer is associated.</span></span> <span data-ttu-id="cf6fb-119">PSTN エンドポイントを使用するすべての着信呼び出し、発信呼び出し、通話転送、および着信転送は、このような仲介サーバーピアのローカルとして定義されている PSTN ゲートウェイのみを使用するために、場所に基づいたルーティングの対象となります。</span><span class="sxs-lookup"><span data-stu-id="cf6fb-119">All inbound calls, outbound calls, call transfers and call forwards involving PSTN endpoints will be subject to Location Based Routing to use only PSTN gateways that are defined as local to such Mediation Server peer.</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="cf6fb-120">関連項目</span><span class="sxs-lookup"><span data-stu-id="cf6fb-120">See Also</span></span>


[<span data-ttu-id="cf6fb-121">Lync Server 2013 での Location-Based ルーティングに関するガイダンス</span><span class="sxs-lookup"><span data-stu-id="cf6fb-121">Guidance for Location-Based Routing in Lync Server 2013</span></span>](lync-server-2013-guidance-for-location-based-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

