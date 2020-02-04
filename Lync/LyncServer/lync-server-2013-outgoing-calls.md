---
title: 'Lync Server 2013: 発信通話'
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
ms.openlocfilehash: 1a353cecbf1cdc1ff411c2cfe7c57edcd909c5c8
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41755641"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="outgoing-calls-in-lync-server-2013"></a><span data-ttu-id="0749b-102">Lync Server 2013 の発信通話</span><span class="sxs-lookup"><span data-stu-id="0749b-102">Outgoing calls in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0749b-103">_**最終更新日:** 2013-03-09_</span><span class="sxs-lookup"><span data-stu-id="0749b-103">_**Topic Last Modified:** 2013-03-09_</span></span>

<span data-ttu-id="0749b-104">場所に基づくルーティングが有効になっているユーザーの発信通話のルーティングは、ユーザーのエンドポイントのネットワークの場所によって影響を受けます。</span><span class="sxs-lookup"><span data-stu-id="0749b-104">The routing of outbound calls of users enabled for Location-Based Routing is affected by the network location of the user’s endpoint.</span></span> <span data-ttu-id="0749b-105">次の表では、呼び出し元のエンドポイントの場所に応じて、発信通話のルーティングが位置情報に基づくルーティングにどのように影響するかを示しています。</span><span class="sxs-lookup"><span data-stu-id="0749b-105">The following table illustrates how Location-Based Routing affects the routing of outbound calls depending on the location of the caller’s endpoint.</span></span>

### <a name="caller-placing-an-outbound-call-to-the-pstn"></a><span data-ttu-id="0749b-106">発信者から PSTN への発信通話</span><span class="sxs-lookup"><span data-stu-id="0749b-106">Caller placing an outbound call to the PSTN</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th></th>
<th><span data-ttu-id="0749b-107">ユーザーのエンドポイントが、場所に基づくルーティングが有効なネットワーク サイトにある</span><span class="sxs-lookup"><span data-stu-id="0749b-107">User endpoint located in a network site enabled for Location-Based Routing</span></span></th>
<th><span data-ttu-id="0749b-108">ユーザーのエンドポイントが不明なネットワーク サイトまたは場所に基づくルーティングが有効でないネットワーク サイトにある</span><span class="sxs-lookup"><span data-stu-id="0749b-108">User endpoint located in unknown network site or not enabled for Location-Based Routing</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="0749b-109">発信の承認</span><span class="sxs-lookup"><span data-stu-id="0749b-109">Authorization of outbound calls</span></span></p></td>
<td><p><span data-ttu-id="0749b-110">通話はユーザーの音声ポリシーに基づいて承認される</span><span class="sxs-lookup"><span data-stu-id="0749b-110">Call is authorized based on user’s voice policy</span></span></p></td>
<td><p><span data-ttu-id="0749b-111">通話はユーザーの音声ポリシーに基づいて承認される</span><span class="sxs-lookup"><span data-stu-id="0749b-111">Call is authorized based on user’s voice policy</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0749b-112">発信通話のルーティング</span><span class="sxs-lookup"><span data-stu-id="0749b-112">Routing of outbound call</span></span></p></td>
<td><p><span data-ttu-id="0749b-113">通話はネットワーク サイトの音声ルーティング ポリシーに従ってルーティングされる</span><span class="sxs-lookup"><span data-stu-id="0749b-113">Call is routed according to the network site’s voice routing policy</span></span></p></td>
<td><p><span data-ttu-id="0749b-114">通話はユーザーの音声ポリシーに従い、場所に基づくルーティングが有効になっていないトランク (使用可能な場合) のみを経由してルーティングされる</span><span class="sxs-lookup"><span data-stu-id="0749b-114">Call is routed according to user’s voice policy and only through trunks not enabled for Location-Based Routing (if available)</span></span></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="see-also"></a><span data-ttu-id="0749b-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="0749b-115">See Also</span></span>


[<span data-ttu-id="0749b-116">Lync Server 2013 の場所に基づくルーティングのシナリオ</span><span class="sxs-lookup"><span data-stu-id="0749b-116">Scenarios for Location-Based Routing in Lync Server 2013</span></span>](lync-server-2013-scenarios-for-location-based-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

