---
title: 'Lync Server 2013: Location-Based ルーティングの概要'
description: 'Lync Server 2013: Location-Based ルーティングの概要。'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Overview of Location-Based Routing
ms:assetid: 4aa494bd-0d66-4335-b9e8-f758d44a7202
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994032(v=OCS.15)
ms:contentKeyID: 51803941
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0b1e026791a8562629231b91b58d7e7eff569ffa
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48562813"
---
# <a name="overview-of-location-based-routing-in-lync-server-2013"></a><span data-ttu-id="0ed01-103">Lync Server 2013 での Location-Based ルーティングの概要</span><span class="sxs-lookup"><span data-stu-id="0ed01-103">Overview of Location-Based Routing in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0ed01-104">_**トピックの最終更新日:** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="0ed01-104">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="0ed01-105">Location-Based ルーティングでは、国内および国際間の PSTN 通話のルーティングを変更する新しいルールのセットを導入して、有料のバイパスを防ぐことができます。</span><span class="sxs-lookup"><span data-stu-id="0ed01-105">Location-Based Routing introduces a new set of rules that modifies the routing of national and international PSTN calls to prevent toll bypass.</span></span> <span data-ttu-id="0ed01-106">Location-Based ルーティングでは、これらのルールを特定の地域、特定のゲートウェイ、または特定のユーザーのセットに限定するための柔軟性が提供されます。</span><span class="sxs-lookup"><span data-stu-id="0ed01-106">Location-Based Routing provides the flexibility to scope these rules to specific regions, specific gateways or to specific set of users only.</span></span>

<span data-ttu-id="0ed01-107">次のシナリオでは、Location-Based ルーティングによって適用される可能性のある主な種類の制限について説明します。</span><span class="sxs-lookup"><span data-stu-id="0ed01-107">The following scenarios illustrate the main types of restrictions Location-Based Routing can enforce:</span></span>

  - <span data-ttu-id="0ed01-108">[出口呼び出し] – Location-Based ルーティングは、発信者が PSTN 有料電話のバイパスを阻止する pstn ゲートウェイからの出口に対して発信呼び出しを強制することができます。これにより、発信者とは別の地域にある PSTN ゲートウェイからの呼び出しを阻止することができます。</span><span class="sxs-lookup"><span data-stu-id="0ed01-108">Egress calls – Location-Based Routing can enforce outgoing calls to egress from a PSTN gateway that is located in the same region as where the caller is to prevent PSTN toll bypass, which prevents calls to egress from a PSTN gateway located in a different region as the caller.</span></span>

  - <span data-ttu-id="0ed01-109">受信呼び出し– Location-Based ルーティングは、着信呼び出しをルーティングする PSTN ゲートウェイが Lync ユーザーと同じ地域にない場合に、Lync エンドポイントを着信させないようにすることができます。</span><span class="sxs-lookup"><span data-stu-id="0ed01-109">Ingress calls – Location-Based Routing can prevent incoming PSTN calls to ring Lync endpoints if the PSTN gateway routing the incoming call is not located in the same region as the called Lync user.</span></span>

  - <span data-ttu-id="0ed01-110">不明地域– Location-Based ルーティングによって、不定の場所にあるユーザーとの間で送受信される PSTN 通話を制限します (つまり、リモートユーザーがインターネットから接続するか、または不明な地域に配置されます)。</span><span class="sxs-lookup"><span data-stu-id="0ed01-110">Unknown regions – Location-Based Routing restricts incoming and outgoing PSTN calls to and from users that are located in undetermined locations (i.e. remote users connecting from the Internet or located in unknown regions).</span></span>

  - <span data-ttu-id="0ed01-111">国際地域– Location-Based ルーティングは、ユーザーの場所にローカルなゲートウェイが見つからない場合に、国際 PSTN ゲートウェイを経由して発信通話のルーティングを強制します。</span><span class="sxs-lookup"><span data-stu-id="0ed01-111">International regions – Location-Based Routing enforces routing of outgoing calls through international PSTN gateways if a gateway local to the user’s location cannot be found.</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="0ed01-112">関連項目</span><span class="sxs-lookup"><span data-stu-id="0ed01-112">See Also</span></span>


[<span data-ttu-id="0ed01-113">Lync Server 2013 での Location-Based ルーティングの計画</span><span class="sxs-lookup"><span data-stu-id="0ed01-113">Planning for Location-Based Routing in Lync Server 2013</span></span>](lync-server-2013-planning-for-location-based-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

