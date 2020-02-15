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
ms.openlocfilehash: 4e3104da5e7d351bda26698087e97106cafbdff4
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2020
ms.locfileid: "42037507"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="simultaneous-ringing-in-lync-server-2013"></a><span data-ttu-id="c2d9a-102">Lync Server 2013 での同時呼び出し</span><span class="sxs-lookup"><span data-stu-id="c2d9a-102">Simultaneous ringing in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c2d9a-103">_**トピックの最終更新日:** 2013-03-09_</span><span class="sxs-lookup"><span data-stu-id="c2d9a-103">_**Topic Last Modified:** 2013-03-09_</span></span>

<span data-ttu-id="c2d9a-104">呼び出し先に同時呼び出しが有効になっている場合、場所に基づくルーティングによって、呼び出し元の場所と、呼び出された相手のエンドポイントが分析され、呼び出しがルーティングされるかどうかが判断されます。</span><span class="sxs-lookup"><span data-stu-id="c2d9a-104">When the called party has simultaneous ringing enabled, Location-Based Routing analyzes the location of the calling party and the endpoints of the called parties to determine whether the call should be routed.</span></span>

<span data-ttu-id="c2d9a-105">次の表は、ユーザーが同時呼び出しを使用して構成されており、同時呼び出し先が、同じネットワークサイト、別のネットワークサイト、または不明なネットワークサイト内のユーザーであることを示しています。</span><span class="sxs-lookup"><span data-stu-id="c2d9a-105">The following table illustrates a user configured with simultaneous ringing, and the simultaneous ringing target is a user in the same network site, in a different network site, or in an unknown network site.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="c2d9a-106">の PSTN 通話の着信</span><span class="sxs-lookup"><span data-stu-id="c2d9a-106">Incoming PSTN call for</span></span></th>
<th><span data-ttu-id="c2d9a-107">呼び出し先と同じネットワークサイトに配置されている</span><span class="sxs-lookup"><span data-stu-id="c2d9a-107">Located in the same network site as callee</span></span></th>
<th><span data-ttu-id="c2d9a-108">呼び出し先が異なるネットワークサイトにある</span><span class="sxs-lookup"><span data-stu-id="c2d9a-108">Located in different network site than callee</span></span></th>
<th><span data-ttu-id="c2d9a-109">不明なネットワークサイトに配置されているか、場所に基づくルーティングが有効になっていません</span><span class="sxs-lookup"><span data-stu-id="c2d9a-109">Located in unknown network site or not enabled for Location-Based Routing</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c2d9a-110">Lync ユーザー</span><span class="sxs-lookup"><span data-stu-id="c2d9a-110">Lync user</span></span></p></td>
<td><p><span data-ttu-id="c2d9a-111">同時呼び出し許可</span><span class="sxs-lookup"><span data-stu-id="c2d9a-111">Simultaneous ring allowed</span></span></p></td>
<td><p><span data-ttu-id="c2d9a-112">同時呼び出しを許可しない</span><span class="sxs-lookup"><span data-stu-id="c2d9a-112">Simultaneous ring not allowed</span></span></p></td>
<td><p><span data-ttu-id="c2d9a-113">同時呼び出しを許可しない</span><span class="sxs-lookup"><span data-stu-id="c2d9a-113">Simultaneous ring not allowed</span></span></p></td>
</tr>
</tbody>
</table>

  
<span data-ttu-id="c2d9a-114">次の表は、同一のネットワークサイト、別のネットワークサイト、または不明なネットワークサイトにある Lync ユーザー (Lync 発信者) からの呼び出しを示しています。</span><span class="sxs-lookup"><span data-stu-id="c2d9a-114">The following table illustrates a call from a Lync user (i.e. Lync caller) in the same network site, in a different network site, or from an unknown network site.</span></span> <span data-ttu-id="c2d9a-115">呼び出し先には、同時呼び出しのターゲットとして構成されている PSTN エンドポイント (携帯電話) があります。</span><span class="sxs-lookup"><span data-stu-id="c2d9a-115">The callee has a PSTN endpoint (i.e. cellphone) configured as a simultaneous ring target.</span></span> <span data-ttu-id="c2d9a-116">このシナリオでは、場所に基づくルーティングによって、呼び出し先 (携帯電話) の同時呼び出し先 (つまり、) に通話をルーティングする必要があるかどうかが判断されます。</span><span class="sxs-lookup"><span data-stu-id="c2d9a-116">In this scenario, Location-Based Routing will determine whether the call should be routed to the simultaneous ring target (i.e. cellphone) of the callee or not.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="c2d9a-117">同時呼び出しのターゲット</span><span class="sxs-lookup"><span data-stu-id="c2d9a-117">Simultaneous ring target</span></span></th>
<th><span data-ttu-id="c2d9a-118">呼び出し先と同じネットワークサイトに配置されている</span><span class="sxs-lookup"><span data-stu-id="c2d9a-118">Located in the same network site as callee</span></span></th>
<th><span data-ttu-id="c2d9a-119">呼び出し先が異なるネットワークサイトにある</span><span class="sxs-lookup"><span data-stu-id="c2d9a-119">Located in different network site than callee</span></span></th>
<th><span data-ttu-id="c2d9a-120">不明なネットワークサイトに配置されているか、場所に基づくルーティングが有効になっていません</span><span class="sxs-lookup"><span data-stu-id="c2d9a-120">Located in unknown network site or not enabled for Location-Based Routing</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c2d9a-121">PSTN エンドポイント</span><span class="sxs-lookup"><span data-stu-id="c2d9a-121">PSTN endpoint</span></span></p></td>
<td><p><span data-ttu-id="c2d9a-122">発信者のサイトの音声ルーティングポリシーを使用して同時呼び出しが許可される</span><span class="sxs-lookup"><span data-stu-id="c2d9a-122">Simultaneous ring allowed through the caller’s site voice routing policy</span></span></p></td>
<td><p><span data-ttu-id="c2d9a-123">発信者のサイトの音声ルーティングポリシーを使用して同時呼び出しが許可される</span><span class="sxs-lookup"><span data-stu-id="c2d9a-123">Simultaneous ring allowed through the caller’s site voice routing policy</span></span></p></td>
<td><p><span data-ttu-id="c2d9a-124">発信者の音声ポリシーによって、場所に基づくルーティングが有効になっていないトランクに対して同時呼び出しが許可されている</span><span class="sxs-lookup"><span data-stu-id="c2d9a-124">Simultaneous ring allowed through the caller’s voice policy to trunks not enabled for Location-Based Routing</span></span></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="see-also"></a><span data-ttu-id="c2d9a-125">関連項目</span><span class="sxs-lookup"><span data-stu-id="c2d9a-125">See Also</span></span>


[<span data-ttu-id="c2d9a-126">Lync Server 2013 での場所に基づくルーティングのシナリオ</span><span class="sxs-lookup"><span data-stu-id="c2d9a-126">Scenarios for Location-Based Routing in Lync Server 2013</span></span>](lync-server-2013-scenarios-for-location-based-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

