---
title: 'Lync Server 2013: 送信呼び出し'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Outgoing calls
ms:assetid: 885ffe6f-cd51-4f21-8d4f-a1ff8d818858
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994049(v=OCS.15)
ms:contentKeyID: 51803960
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ca0cdc7781143b0e76ff83a980f00da58c814f02
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2020
ms.locfileid: "42049569"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="outgoing-calls-in-lync-server-2013"></a><span data-ttu-id="b38d2-102">Lync Server 2013 の送信呼び出し</span><span class="sxs-lookup"><span data-stu-id="b38d2-102">Outgoing calls in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b38d2-103">_**トピックの最終更新日:** 2013-03-09_</span><span class="sxs-lookup"><span data-stu-id="b38d2-103">_**Topic Last Modified:** 2013-03-09_</span></span>

<span data-ttu-id="b38d2-104">場所に基づくルーティングが有効になっているユーザーの発信呼び出しのルーティングは、ユーザーのエンドポイントのネットワーク上の場所によって影響を受けます。</span><span class="sxs-lookup"><span data-stu-id="b38d2-104">The routing of outbound calls of users enabled for Location-Based Routing is affected by the network location of the user’s endpoint.</span></span> <span data-ttu-id="b38d2-105">次の表は、発信者のエンドポイントの場所に応じて、場所に基づくルーティングが発信呼び出しのルーティングにどのように影響するかを示しています。</span><span class="sxs-lookup"><span data-stu-id="b38d2-105">The following table illustrates how Location-Based Routing affects the routing of outbound calls depending on the location of the caller’s endpoint.</span></span>

### <a name="caller-placing-an-outbound-call-to-the-pstn"></a><span data-ttu-id="b38d2-106">発信者が PSTN への発信通話を配置する</span><span class="sxs-lookup"><span data-stu-id="b38d2-106">Caller placing an outbound call to the PSTN</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th></th>
<th><span data-ttu-id="b38d2-107">場所に基づくルーティングが有効なネットワークサイトに配置されたユーザーエンドポイント</span><span class="sxs-lookup"><span data-stu-id="b38d2-107">User endpoint located in a network site enabled for Location-Based Routing</span></span></th>
<th><span data-ttu-id="b38d2-108">不明なネットワークサイトにある、または場所に基づくルーティングが有効になっていないユーザーエンドポイント</span><span class="sxs-lookup"><span data-stu-id="b38d2-108">User endpoint located in unknown network site or not enabled for Location-Based Routing</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="b38d2-109">発信呼び出しの承認</span><span class="sxs-lookup"><span data-stu-id="b38d2-109">Authorization of outbound calls</span></span></p></td>
<td><p><span data-ttu-id="b38d2-110">通話はユーザーの音声ポリシーに基づいて承認されます。</span><span class="sxs-lookup"><span data-stu-id="b38d2-110">Call is authorized based on user’s voice policy</span></span></p></td>
<td><p><span data-ttu-id="b38d2-111">通話はユーザーの音声ポリシーに基づいて承認されます。</span><span class="sxs-lookup"><span data-stu-id="b38d2-111">Call is authorized based on user’s voice policy</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b38d2-112">発信通話のルーティング</span><span class="sxs-lookup"><span data-stu-id="b38d2-112">Routing of outbound call</span></span></p></td>
<td><p><span data-ttu-id="b38d2-113">呼び出しは、ネットワークサイトの音声ルーティングポリシーに従ってルーティングされます。</span><span class="sxs-lookup"><span data-stu-id="b38d2-113">Call is routed according to the network site’s voice routing policy</span></span></p></td>
<td><p><span data-ttu-id="b38d2-114">通話はユーザーの音声ポリシーに従ってルーティングされ、場所に基づくルーティングが有効になっていない場合にのみトランクによってルーティングされます (使用可能な場合)。</span><span class="sxs-lookup"><span data-stu-id="b38d2-114">Call is routed according to user’s voice policy and only through trunks not enabled for Location-Based Routing (if available)</span></span></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="see-also"></a><span data-ttu-id="b38d2-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="b38d2-115">See Also</span></span>


[<span data-ttu-id="b38d2-116">Lync Server 2013 での場所に基づくルーティングのシナリオ</span><span class="sxs-lookup"><span data-stu-id="b38d2-116">Scenarios for Location-Based Routing in Lync Server 2013</span></span>](lync-server-2013-scenarios-for-location-based-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

