---
title: 'Lync Server 2013: コールパークでサポートされているクライアント'
description: 'Lync Server 2013: コールパークに対してサポートされているクライアント。'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Clients supported for Call Park
ms:assetid: c236d2ba-9d83-418c-9cbc-92541f115fb0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412958(v=OCS.15)
ms:contentKeyID: 48185320
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a923f0e62c246a12b811628d578ab571f4f13e36
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48543493"
---
# <a name="clients-supported-for-call-park-in-lync-server-2013"></a><span data-ttu-id="517c0-103">Lync Server 2013 のコールパークに対してサポートされているクライアント</span><span class="sxs-lookup"><span data-stu-id="517c0-103">Clients supported for Call Park in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="517c0-104">_**トピックの最終更新日:** 2012-09-13_</span><span class="sxs-lookup"><span data-stu-id="517c0-104">_**Topic Last Modified:** 2012-09-13_</span></span>

<span data-ttu-id="517c0-105">ここでは、通話を保留するために使用できるクライアントと、保留された通話を取得するために使用できるクライアントを示します。</span><span class="sxs-lookup"><span data-stu-id="517c0-105">This section identifies the clients that can be used to park calls and the clients that can be used to retrieve parked calls.</span></span>

<div>

## <a name="clients-supported-for-parking-calls"></a><span data-ttu-id="517c0-106">通話の保留をサポートするクライアント</span><span class="sxs-lookup"><span data-stu-id="517c0-106">Clients Supported for Parking Calls</span></span>

<span data-ttu-id="517c0-107">IP、構内交換機 (PBX)、公衆交換電話網 (PSTN)、または携帯電話からの通話を保留できます。</span><span class="sxs-lookup"><span data-stu-id="517c0-107">Calls from any IP, private branch exchange (PBX), public switched telephone network (PSTN), or mobile phone can be parked.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="517c0-p101">音声通話だけを保留できます。 インスタント メッセージと電話会議は保留できません。</span><span class="sxs-lookup"><span data-stu-id="517c0-p101">Only audio calls can be parked. Instant messages and conferences cannot be parked.</span></span>



</div>

<span data-ttu-id="517c0-110">次のクライアントは、コールパークを使用して通話をパークできます。</span><span class="sxs-lookup"><span data-stu-id="517c0-110">The following clients can use Call Park to park calls:</span></span>

  - <span data-ttu-id="517c0-111">Lync 2013</span><span class="sxs-lookup"><span data-stu-id="517c0-111">Lync 2013</span></span>

  - <span data-ttu-id="517c0-112">Lync 2010</span><span class="sxs-lookup"><span data-stu-id="517c0-112">Lync 2010</span></span>

  - <span data-ttu-id="517c0-113">Lync 2010 Attendant</span><span class="sxs-lookup"><span data-stu-id="517c0-113">Lync 2010 Attendant</span></span>

  - <span data-ttu-id="517c0-114">Lync Phone Edition</span><span class="sxs-lookup"><span data-stu-id="517c0-114">Lync Phone Edition</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="517c0-115">携帯電話は、コールパークを使用して通話をパークすることはできません。</span><span class="sxs-lookup"><span data-stu-id="517c0-115">Mobile phones cannot use Call Park to park calls.</span></span>



</div>

</div>

<div>

## <a name="clients-supported-for-retrieving-calls"></a><span data-ttu-id="517c0-116">通話の取得をサポートするクライアント</span><span class="sxs-lookup"><span data-stu-id="517c0-116">Clients Supported for Retrieving Calls</span></span>

<span data-ttu-id="517c0-p102">オービット範囲は仮想の内線番号 (ユーザーまたは電話が割り当てられていない内線番号) のブロックとして構成されます。 オービットを仮想の内線番号として構成すると、携帯電話と PSTN 電話は保留された通話を取得できません。</span><span class="sxs-lookup"><span data-stu-id="517c0-p102">Orbit ranges are configured as blocks of virtual extensions (extensions without an assigned user or phone). When you configure orbits as virtual extensions, mobile phones and PSTN phones cannot retrieve parked calls.</span></span>

<span data-ttu-id="517c0-119">フェデレーション ユーザーは保留された通話を取得できません。</span><span class="sxs-lookup"><span data-stu-id="517c0-119">Federated users cannot retrieve parked calls.</span></span>

<span data-ttu-id="517c0-120">次のクライアントは、コールパークで保留されている通話を取得できます。</span><span class="sxs-lookup"><span data-stu-id="517c0-120">The following clients can retrieve calls that are parked on Call Park:</span></span>

  - <span data-ttu-id="517c0-121">Lync 2013</span><span class="sxs-lookup"><span data-stu-id="517c0-121">Lync 2013</span></span>

  - <span data-ttu-id="517c0-122">Lync 2010</span><span class="sxs-lookup"><span data-stu-id="517c0-122">Lync 2010</span></span>

  - <span data-ttu-id="517c0-123">Lync 2010 Attendant</span><span class="sxs-lookup"><span data-stu-id="517c0-123">Lync 2010 Attendant</span></span>

  - <span data-ttu-id="517c0-124">Lync Phone Edition</span><span class="sxs-lookup"><span data-stu-id="517c0-124">Lync Phone Edition</span></span>

  - <span data-ttu-id="517c0-125">IP 共通領域電話</span><span class="sxs-lookup"><span data-stu-id="517c0-125">IP common area phones</span></span>

  - <span data-ttu-id="517c0-126">共通領域電話、構内交換機 (PBX) 電話を含む、Lync Server 2013 のインフラストラクチャに接続されている非 IP 電話</span><span class="sxs-lookup"><span data-stu-id="517c0-126">Non-IP phones that are connected to the Lync Server 2013 infrastructure, including common area phones and private branch exchange (PBX) phones</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

