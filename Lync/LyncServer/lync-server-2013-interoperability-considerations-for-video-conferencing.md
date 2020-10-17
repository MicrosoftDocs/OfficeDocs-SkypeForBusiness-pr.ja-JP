---
title: 'Lync Server 2013: ビデオ会議の相互運用性に関する考慮事項'
description: 'Lync Server 2013: ビデオ会議の相互運用性に関する考慮事項。'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Interoperability considerations for video conferencing
ms:assetid: 31ead3b5-ed95-42d4-96e2-7d9403d5c026
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204790(v=OCS.15)
ms:contentKeyID: 48183782
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 89675954ea4c4f188f50aab8fb2cb49494bcc247
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48543933"
---
# <a name="interoperability-considerations-for-video-conferencing-in-lync-server-2013"></a><span data-ttu-id="7ec37-103">Lync Server 2013 でのビデオ会議の相互運用性に関する考慮事項</span><span class="sxs-lookup"><span data-stu-id="7ec37-103">Interoperability considerations for video conferencing in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7ec37-104">_**トピックの最終更新日:** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="7ec37-104">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="7ec37-105">このセクションでは、レガシクライアントと Lync Server 2013 プールまたは Lync Server 2013 クライアントと従来のプールとの間に相互運用性がある場合に、移行の共存フェーズのユーザー環境を説明します。</span><span class="sxs-lookup"><span data-stu-id="7ec37-105">This section describes the user experience during the coexistence phase of migration, when there is interoperability between legacy clients and a Lync Server 2013 pool or Lync Server 2013 clients and a legacy pool.</span></span>

<div>

## <a name="lync-server-2013-pools"></a><span data-ttu-id="7ec37-106">Lync Server 2013 プール</span><span class="sxs-lookup"><span data-stu-id="7ec37-106">Lync Server 2013 Pools</span></span>

<span data-ttu-id="7ec37-107">従来のクライアントが Lync Server 2013 プールで使用されている場合、ユーザーには次のような動作が生じます。</span><span class="sxs-lookup"><span data-stu-id="7ec37-107">Users will experience the following behavior when a legacy client is used in a Lync Server 2013 pool:</span></span>

  - <span data-ttu-id="7ec37-108">2 者間通話では、ビデオ解像度はレガシ プールと同じです。</span><span class="sxs-lookup"><span data-stu-id="7ec37-108">For two-party calls, video resolution is the same as in the legacy pool.</span></span>

  - <span data-ttu-id="7ec37-p101">マルチパーティの電話会議、ビデオ解像度、およびビデオ会議の機能は、レガシ プールと同じです。ギャラリー ビューと高解像度は使用できません。</span><span class="sxs-lookup"><span data-stu-id="7ec37-p101">For multiparty conferences, video resolution and video conferencing features are the same as in the legacy pool. Gallery View and high resolution are not available.</span></span>

</div>

<div>

## <a name="legacy-pools"></a><span data-ttu-id="7ec37-111">レガシ プール</span><span class="sxs-lookup"><span data-stu-id="7ec37-111">Legacy Pools</span></span>

<span data-ttu-id="7ec37-112">従来のプールで Lync Server 2013 クライアントが使用されている場合、ユーザーには次のような動作が生じます。</span><span class="sxs-lookup"><span data-stu-id="7ec37-112">Users will experience the following behavior when a Lync Server 2013 client is used in a legacy pool:</span></span>

  - <span data-ttu-id="7ec37-113">2者間通話では、Lync Server 2013 クライアントは次のように新しい機能を使用できます。</span><span class="sxs-lookup"><span data-stu-id="7ec37-113">For two-party calls, Lync Server 2013 clients can use new features as follows:</span></span>
    
      - <span data-ttu-id="7ec37-114">.H は、両方の参加者が Lync Server 2013 クライアントを使用している場合に使用できます。</span><span class="sxs-lookup"><span data-stu-id="7ec37-114">H.264 is available if both participants are using Lync Server 2013 clients.</span></span>
    
      - <span data-ttu-id="7ec37-115">従来のサーバーはインバンドプロビジョニングでこの情報を送信しないため、Lync Server 2013 クライアントは TotalReceiveVideoBitRateKb の既定値を使用します。</span><span class="sxs-lookup"><span data-stu-id="7ec37-115">The Lync Server 2013 client uses the default value for TotalReceiveVideoBitRateKb, since the legacy server doesn’t send this information with in-band provisioning.</span></span>

  - <span data-ttu-id="7ec37-116">マルチパーティの電話会議、ビデオ解像度、およびビデオ会議の機能は、レガシ プール内のレガシ クライアントでのユーザー エクスペリエンスと同じです。</span><span class="sxs-lookup"><span data-stu-id="7ec37-116">For multiparty conferences, video resolution and video conferencing features are the same as experienced by a legacy client in the legacy pool.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="7ec37-117">従来のサーバーが Lync Server 2013 クライアントをホストしている場合は、ビデオ会議の帯域幅を構成して、プール上のすべてのユーザーが低解像度のビデオを受信し、高解像度のビデオを送信できるようにすることができます。</span><span class="sxs-lookup"><span data-stu-id="7ec37-117">When a legacy server hosts a Lync Server 2013 client, it's possible to configure video conferencing bandwidth so that all users on the pool receive only low-resolution video, but send high-resolution video.</span></span> <span data-ttu-id="7ec37-118">この例は、メディア構成で MaxVideoRateAllowed が CIF-250K に設定され、会議ポリシーで VideoBitRateKb が 2000 kbps に設定された場合です。</span><span class="sxs-lookup"><span data-stu-id="7ec37-118">An example of this is when MaxVideoRateAllowed is set to CIF-250K in the media configuration and VideoBitRateKb is set to 2000 kbps in conferencing policy.</span></span> <span data-ttu-id="7ec37-119">この設定では、プール上のユーザーは高解像度を送信できないことになります。</span><span class="sxs-lookup"><span data-stu-id="7ec37-119">The net effect in this situation is that high resolution is not possible for users on the pool.</span></span><BR><span data-ttu-id="7ec37-120">MaxVideoRateAllowed は Lync Server 2013 クライアントでは使用されなくなったため、Lync Server 2013 クライアントが高解像度のビデオを要求することを防ぐことはできません。</span><span class="sxs-lookup"><span data-stu-id="7ec37-120">Because MaxVideoRateAllowed is no longer used for Lync Server 2013 clients, it cannot prevent Lync Server 2013 clients from requesting high-resolution video.</span></span> <span data-ttu-id="7ec37-121">その代わりに、すべてのプール上のユーザーの会議ポリシーで VideoBitRateKb を MaxVideoRateAllowed と同じ値に設定します (つまり、CIF が 250 kbps、VGA が 600 kbps、HD が 1500 kbps に設定されます)。</span><span class="sxs-lookup"><span data-stu-id="7ec37-121">Instead, set VideoBitRateKb in conferencing policy for all users on the pool to the same value as MaxVideoRateAllowed (that is, CIF is set to 250 kbps, or VGA is set to 600 kbps, or HD is set to 1500 kbps).</span></span>



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

