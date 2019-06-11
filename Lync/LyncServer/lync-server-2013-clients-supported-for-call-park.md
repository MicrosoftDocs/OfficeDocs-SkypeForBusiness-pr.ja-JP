---
title: 'Lync Server 2013: コール パークでサポートされているクライアント'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Clients supported for Call Park
ms:assetid: c236d2ba-9d83-418c-9cbc-92541f115fb0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412958(v=OCS.15)
ms:contentKeyID: 48185320
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 46b9ac77a82cf8d833c3f06a8fe3c738e2501937
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34840541"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="clients-supported-for-call-park-in-lync-server-2013"></a><span data-ttu-id="02c8c-102">Lync Server 2013 のコール パークでサポートされているクライアント</span><span class="sxs-lookup"><span data-stu-id="02c8c-102">Clients supported for Call Park in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="02c8c-103">_**最終更新日:** 2012-09-13_</span><span class="sxs-lookup"><span data-stu-id="02c8c-103">_**Topic Last Modified:** 2012-09-13_</span></span>

<span data-ttu-id="02c8c-104">このセクションでは、通話をパークするために使用できるクライアントと、保留中の通話を取得するために使用できるクライアントを示します。</span><span class="sxs-lookup"><span data-stu-id="02c8c-104">This section identifies the clients that can be used to park calls and the clients that can be used to retrieve parked calls.</span></span>

<div>

## <a name="clients-supported-for-parking-calls"></a><span data-ttu-id="02c8c-105">通話の保留をサポートするクライアント</span><span class="sxs-lookup"><span data-stu-id="02c8c-105">Clients Supported for Parking Calls</span></span>

<span data-ttu-id="02c8c-106">IP、構内交換機 (PBX)、公衆交換電話網 (PSTN)、または携帯電話からの通話を保留できます。</span><span class="sxs-lookup"><span data-stu-id="02c8c-106">Calls from any IP, private branch exchange (PBX), public switched telephone network (PSTN), or mobile phone can be parked.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="02c8c-p101">音声通話だけを保留できます。インスタント メッセージと電話会議は保留できません。</span><span class="sxs-lookup"><span data-stu-id="02c8c-p101">Only audio calls can be parked. Instant messages and conferences cannot be parked.</span></span>



</div>

<span data-ttu-id="02c8c-109">次のクライアントでは、通話パークを使って通話をパークできます。</span><span class="sxs-lookup"><span data-stu-id="02c8c-109">The following clients can use Call Park to park calls:</span></span>

  - <span data-ttu-id="02c8c-110">Lync 2013</span><span class="sxs-lookup"><span data-stu-id="02c8c-110">Lync 2013</span></span>

  - <span data-ttu-id="02c8c-111">Lync 2010</span><span class="sxs-lookup"><span data-stu-id="02c8c-111">Lync 2010</span></span>

  - <span data-ttu-id="02c8c-112">Lync 2010 Attendant</span><span class="sxs-lookup"><span data-stu-id="02c8c-112">Lync 2010 Attendant</span></span>

  - <span data-ttu-id="02c8c-113">Lync Phone Edition</span><span class="sxs-lookup"><span data-stu-id="02c8c-113">Lync Phone Edition</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="02c8c-114">携帯電話では、通話パークを使って通話をパークすることはできません。</span><span class="sxs-lookup"><span data-stu-id="02c8c-114">Mobile phones cannot use Call Park to park calls.</span></span>



</div>

</div>

<div>

## <a name="clients-supported-for-retrieving-calls"></a><span data-ttu-id="02c8c-115">通話の取得をサポートするクライアント</span><span class="sxs-lookup"><span data-stu-id="02c8c-115">Clients Supported for Retrieving Calls</span></span>

<span data-ttu-id="02c8c-p102">オービット範囲は仮想の内線番号 (ユーザーまたは電話が割り当てられていない内線番号) のブロックとして構成されます。オービットを仮想の内線番号として構成すると、携帯電話と PSTN 電話は保留された通話を取得できません。</span><span class="sxs-lookup"><span data-stu-id="02c8c-p102">Orbit ranges are configured as blocks of virtual extensions (extensions without an assigned user or phone). When you configure orbits as virtual extensions, mobile phones and PSTN phones cannot retrieve parked calls.</span></span>

<span data-ttu-id="02c8c-118">フェデレーション ユーザーは保留された通話を取得できません。</span><span class="sxs-lookup"><span data-stu-id="02c8c-118">Federated users cannot retrieve parked calls.</span></span>

<span data-ttu-id="02c8c-119">次のクライアントは、コールパークで保留中の通話を取得できます。</span><span class="sxs-lookup"><span data-stu-id="02c8c-119">The following clients can retrieve calls that are parked on Call Park:</span></span>

  - <span data-ttu-id="02c8c-120">Lync 2013</span><span class="sxs-lookup"><span data-stu-id="02c8c-120">Lync 2013</span></span>

  - <span data-ttu-id="02c8c-121">Lync 2010</span><span class="sxs-lookup"><span data-stu-id="02c8c-121">Lync 2010</span></span>

  - <span data-ttu-id="02c8c-122">Lync 2010 Attendant</span><span class="sxs-lookup"><span data-stu-id="02c8c-122">Lync 2010 Attendant</span></span>

  - <span data-ttu-id="02c8c-123">Lync Phone Edition</span><span class="sxs-lookup"><span data-stu-id="02c8c-123">Lync Phone Edition</span></span>

  - <span data-ttu-id="02c8c-124">IP 共通領域電話</span><span class="sxs-lookup"><span data-stu-id="02c8c-124">IP common area phones</span></span>

  - <span data-ttu-id="02c8c-125">一般的な市外局番、構内交換機 (PBX) 電話など、Lync Server 2013 インフラストラクチャに接続されている IP 以外の電話</span><span class="sxs-lookup"><span data-stu-id="02c8c-125">Non-IP phones that are connected to the Lync Server 2013 infrastructure, including common area phones and private branch exchange (PBX) phones</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

