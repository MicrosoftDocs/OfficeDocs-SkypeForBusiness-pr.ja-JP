---
title: 'Lync Server 2013: 同時呼び出し'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Simultaneous ringing
ms:assetid: df02f919-4d50-4832-9300-6c51f8b4fc56
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994079(v=OCS.15)
ms:contentKeyID: 51803990
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1bcdb0d30bccfe628fd02861d257d79268046b77
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41764513"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="simultaneous-ringing-in-lync-server-2013"></a><span data-ttu-id="a4054-102">Lync Server 2013 での同時呼び出し</span><span class="sxs-lookup"><span data-stu-id="a4054-102">Simultaneous ringing in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a4054-103">_**最終更新日:** 2013-03-09_</span><span class="sxs-lookup"><span data-stu-id="a4054-103">_**Topic Last Modified:** 2013-03-09_</span></span>

<span data-ttu-id="a4054-104">通話先の相手が同時呼び出しを有効にしている場合、位置情報に基づくルーティングは、通話をルーティングする必要があるかどうかを判断するために、発信元の場所と、通話相手のエンドポイントを分析します。</span><span class="sxs-lookup"><span data-stu-id="a4054-104">When the called party has simultaneous ringing enabled, Location-Based Routing analyzes the location of the calling party and the endpoints of the called parties to determine whether the call should be routed.</span></span>

<span data-ttu-id="a4054-105">次の表は、同時呼び出しが構成されたユーザーを示します。同時呼び出しのターゲット ユーザーは、同じネットワーク サイトのユーザー、異なるネットワーク サイトのユーザー、または不明なネットワーク サイトのユーザーです。</span><span class="sxs-lookup"><span data-stu-id="a4054-105">The following table illustrates a user configured with simultaneous ringing, and the simultaneous ringing target is a user in the same network site, in a different network site, or in an unknown network site.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="a4054-106">PSTN 着信の対象</span><span class="sxs-lookup"><span data-stu-id="a4054-106">Incoming PSTN call for</span></span></th>
<th><span data-ttu-id="a4054-107">呼び出し先と同じネットワーク サイトにある</span><span class="sxs-lookup"><span data-stu-id="a4054-107">Located in the same network site as callee</span></span></th>
<th><span data-ttu-id="a4054-108">呼び出し先とは別のネットワーク サイトにある</span><span class="sxs-lookup"><span data-stu-id="a4054-108">Located in different network site than callee</span></span></th>
<th><span data-ttu-id="a4054-109">不明のネットワークサイトに配置されているか、位置情報に基づくルーティング用に有効になっていない</span><span class="sxs-lookup"><span data-stu-id="a4054-109">Located in unknown network site or not enabled for Location-Based Routing</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a4054-110">Lync ユーザー</span><span class="sxs-lookup"><span data-stu-id="a4054-110">Lync user</span></span></p></td>
<td><p><span data-ttu-id="a4054-111">同時呼び出しが許可される</span><span class="sxs-lookup"><span data-stu-id="a4054-111">Simultaneous ring allowed</span></span></p></td>
<td><p><span data-ttu-id="a4054-112">同時呼び出しは許可されない</span><span class="sxs-lookup"><span data-stu-id="a4054-112">Simultaneous ring not allowed</span></span></p></td>
<td><p><span data-ttu-id="a4054-113">同時呼び出しは許可されない</span><span class="sxs-lookup"><span data-stu-id="a4054-113">Simultaneous ring not allowed</span></span></p></td>
</tr>
</tbody>
</table>

  
<span data-ttu-id="a4054-114">次の表は、同じネットワークサイト、別のネットワークサイト、または不明なネットワークサイトの Lync ユーザー (Lync 発信者) からの通話の例を示しています。</span><span class="sxs-lookup"><span data-stu-id="a4054-114">The following table illustrates a call from a Lync user (i.e. Lync caller) in the same network site, in a different network site, or from an unknown network site.</span></span> <span data-ttu-id="a4054-115">呼び出し先には、同時呼び出しのターゲット ユーザーとして、PSTN エンドポイント (携帯電話) が構成されています。</span><span class="sxs-lookup"><span data-stu-id="a4054-115">The callee has a PSTN endpoint (i.e. cellphone) configured as a simultaneous ring target.</span></span> <span data-ttu-id="a4054-116">このシナリオでは、位置情報に基づくルーティングによって、呼び出し元の同時呼び出しターゲット (携帯電話) に呼び出しをルーティングするかどうかが決定されます。</span><span class="sxs-lookup"><span data-stu-id="a4054-116">In this scenario, Location-Based Routing will determine whether the call should be routed to the simultaneous ring target (i.e. cellphone) of the callee or not.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="a4054-117">同時呼び出しのターゲット ユーザー</span><span class="sxs-lookup"><span data-stu-id="a4054-117">Simultaneous ring target</span></span></th>
<th><span data-ttu-id="a4054-118">呼び出し先と同じネットワーク サイトにある</span><span class="sxs-lookup"><span data-stu-id="a4054-118">Located in the same network site as callee</span></span></th>
<th><span data-ttu-id="a4054-119">呼び出し先とは別のネットワーク サイトにある</span><span class="sxs-lookup"><span data-stu-id="a4054-119">Located in different network site than callee</span></span></th>
<th><span data-ttu-id="a4054-120">不明のネットワークサイトに配置されているか、位置情報に基づくルーティング用に有効になっていない</span><span class="sxs-lookup"><span data-stu-id="a4054-120">Located in unknown network site or not enabled for Location-Based Routing</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a4054-121">PSTN エンドポイント</span><span class="sxs-lookup"><span data-stu-id="a4054-121">PSTN endpoint</span></span></p></td>
<td><p><span data-ttu-id="a4054-122">呼び出し元のサイトの音声ルーティング ポリシーによって同時呼び出しが許可される</span><span class="sxs-lookup"><span data-stu-id="a4054-122">Simultaneous ring allowed through the caller’s site voice routing policy</span></span></p></td>
<td><p><span data-ttu-id="a4054-123">呼び出し元のサイトの音声ルーティング ポリシーによって同時呼び出しが許可される</span><span class="sxs-lookup"><span data-stu-id="a4054-123">Simultaneous ring allowed through the caller’s site voice routing policy</span></span></p></td>
<td><p><span data-ttu-id="a4054-124">場所に基づくルーティングが有効になっていないトランクへの呼び出し元の音声ポリシーによって同時呼び出しが許可される</span><span class="sxs-lookup"><span data-stu-id="a4054-124">Simultaneous ring allowed through the caller’s voice policy to trunks not enabled for Location-Based Routing</span></span></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="see-also"></a><span data-ttu-id="a4054-125">関連項目</span><span class="sxs-lookup"><span data-stu-id="a4054-125">See Also</span></span>


[<span data-ttu-id="a4054-126">Lync Server 2013 の場所に基づくルーティングのシナリオ</span><span class="sxs-lookup"><span data-stu-id="a4054-126">Scenarios for Location-Based Routing in Lync Server 2013</span></span>](lync-server-2013-scenarios-for-location-based-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

