---
title: 'Lync Server 2013: コールパークでサポートされているクライアント'
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
ms.openlocfilehash: ee3916e74a68121b027061429bacb44e2dafacdb
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2020
ms.locfileid: "42044219"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="clients-supported-for-call-park-in-lync-server-2013"></a><span data-ttu-id="c43d9-102">Lync Server 2013 のコールパークに対してサポートされているクライアント</span><span class="sxs-lookup"><span data-stu-id="c43d9-102">Clients supported for Call Park in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c43d9-103">_**トピックの最終更新日:** 2012-09-13_</span><span class="sxs-lookup"><span data-stu-id="c43d9-103">_**Topic Last Modified:** 2012-09-13_</span></span>

<span data-ttu-id="c43d9-104">ここでは、通話を保留するために使用できるクライアントと、保留された通話を取得するために使用できるクライアントを示します。</span><span class="sxs-lookup"><span data-stu-id="c43d9-104">This section identifies the clients that can be used to park calls and the clients that can be used to retrieve parked calls.</span></span>

<div>

## <a name="clients-supported-for-parking-calls"></a><span data-ttu-id="c43d9-105">通話の保留をサポートするクライアント</span><span class="sxs-lookup"><span data-stu-id="c43d9-105">Clients Supported for Parking Calls</span></span>

<span data-ttu-id="c43d9-106">IP、構内交換機 (PBX)、公衆交換電話網 (PSTN)、または携帯電話からの通話を保留できます。</span><span class="sxs-lookup"><span data-stu-id="c43d9-106">Calls from any IP, private branch exchange (PBX), public switched telephone network (PSTN), or mobile phone can be parked.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="c43d9-p101">音声通話だけを保留できます。 インスタント メッセージと電話会議は保留できません。</span><span class="sxs-lookup"><span data-stu-id="c43d9-p101">Only audio calls can be parked. Instant messages and conferences cannot be parked.</span></span>



</div>

<span data-ttu-id="c43d9-109">次のクライアントは、コールパークを使用して通話をパークできます。</span><span class="sxs-lookup"><span data-stu-id="c43d9-109">The following clients can use Call Park to park calls:</span></span>

  - <span data-ttu-id="c43d9-110">Lync 2013</span><span class="sxs-lookup"><span data-stu-id="c43d9-110">Lync 2013</span></span>

  - <span data-ttu-id="c43d9-111">Lync 2010</span><span class="sxs-lookup"><span data-stu-id="c43d9-111">Lync 2010</span></span>

  - <span data-ttu-id="c43d9-112">Lync 2010 Attendant</span><span class="sxs-lookup"><span data-stu-id="c43d9-112">Lync 2010 Attendant</span></span>

  - <span data-ttu-id="c43d9-113">Lync Phone Edition</span><span class="sxs-lookup"><span data-stu-id="c43d9-113">Lync Phone Edition</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="c43d9-114">携帯電話は、コールパークを使用して通話をパークすることはできません。</span><span class="sxs-lookup"><span data-stu-id="c43d9-114">Mobile phones cannot use Call Park to park calls.</span></span>



</div>

</div>

<div>

## <a name="clients-supported-for-retrieving-calls"></a><span data-ttu-id="c43d9-115">通話の取得をサポートするクライアント</span><span class="sxs-lookup"><span data-stu-id="c43d9-115">Clients Supported for Retrieving Calls</span></span>

<span data-ttu-id="c43d9-p102">オービット範囲は仮想の内線番号 (ユーザーまたは電話が割り当てられていない内線番号) のブロックとして構成されます。 オービットを仮想の内線番号として構成すると、携帯電話と PSTN 電話は保留された通話を取得できません。</span><span class="sxs-lookup"><span data-stu-id="c43d9-p102">Orbit ranges are configured as blocks of virtual extensions (extensions without an assigned user or phone). When you configure orbits as virtual extensions, mobile phones and PSTN phones cannot retrieve parked calls.</span></span>

<span data-ttu-id="c43d9-118">フェデレーション ユーザーは保留された通話を取得できません。</span><span class="sxs-lookup"><span data-stu-id="c43d9-118">Federated users cannot retrieve parked calls.</span></span>

<span data-ttu-id="c43d9-119">次のクライアントは、コールパークで保留されている通話を取得できます。</span><span class="sxs-lookup"><span data-stu-id="c43d9-119">The following clients can retrieve calls that are parked on Call Park:</span></span>

  - <span data-ttu-id="c43d9-120">Lync 2013</span><span class="sxs-lookup"><span data-stu-id="c43d9-120">Lync 2013</span></span>

  - <span data-ttu-id="c43d9-121">Lync 2010</span><span class="sxs-lookup"><span data-stu-id="c43d9-121">Lync 2010</span></span>

  - <span data-ttu-id="c43d9-122">Lync 2010 Attendant</span><span class="sxs-lookup"><span data-stu-id="c43d9-122">Lync 2010 Attendant</span></span>

  - <span data-ttu-id="c43d9-123">Lync Phone Edition</span><span class="sxs-lookup"><span data-stu-id="c43d9-123">Lync Phone Edition</span></span>

  - <span data-ttu-id="c43d9-124">IP 共通領域電話</span><span class="sxs-lookup"><span data-stu-id="c43d9-124">IP common area phones</span></span>

  - <span data-ttu-id="c43d9-125">共通領域電話、構内交換機 (PBX) 電話を含む、Lync Server 2013 のインフラストラクチャに接続されている非 IP 電話</span><span class="sxs-lookup"><span data-stu-id="c43d9-125">Non-IP phones that are connected to the Lync Server 2013 infrastructure, including common area phones and private branch exchange (PBX) phones</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

