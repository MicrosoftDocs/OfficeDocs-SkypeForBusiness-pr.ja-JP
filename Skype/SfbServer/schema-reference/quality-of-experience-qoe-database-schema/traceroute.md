---
title: TraceRoute テーブル
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: b9493cef-6ece-4f13-bf68-dbf132aab4f4
description: TraceRoute テーブルには、通話のルーティング情報が含まれています。 この表は、Microsoft Lync Server 2013 で導入されました。
ms.openlocfilehash: e257bf6d89d04cd0f4784e62e7ac2876b6ede7e5
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2020
ms.locfileid: "41805115"
---
# <a name="traceroute-table"></a><span data-ttu-id="ddfbb-104">TraceRoute テーブル</span><span class="sxs-lookup"><span data-stu-id="ddfbb-104">TraceRoute table</span></span>
 
<span data-ttu-id="ddfbb-105">TraceRoute テーブルには、通話のルーティング情報が含まれています。</span><span class="sxs-lookup"><span data-stu-id="ddfbb-105">The TraceRoute table contains routing information from calls.</span></span> <span data-ttu-id="ddfbb-106">この表は、Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="ddfbb-106">This table was introduced in Microsoft Lync Server 2013.</span></span>
  
|<span data-ttu-id="ddfbb-107">**列**</span><span class="sxs-lookup"><span data-stu-id="ddfbb-107">**Column**</span></span>|<span data-ttu-id="ddfbb-108">**データ型**</span><span class="sxs-lookup"><span data-stu-id="ddfbb-108">**Data Type**</span></span>|<span data-ttu-id="ddfbb-109">**キー/インデックス**</span><span class="sxs-lookup"><span data-stu-id="ddfbb-109">**Key/Index**</span></span>|<span data-ttu-id="ddfbb-110">**詳細**</span><span class="sxs-lookup"><span data-stu-id="ddfbb-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="ddfbb-111">**ConferenceDateTime**</span><span class="sxs-lookup"><span data-stu-id="ddfbb-111">**ConferenceDateTime**</span></span> <br/> |<span data-ttu-id="ddfbb-112">datetime</span><span class="sxs-lookup"><span data-stu-id="ddfbb-112">datetime</span></span>  <br/> |<span data-ttu-id="ddfbb-113">プライマリ、外部</span><span class="sxs-lookup"><span data-stu-id="ddfbb-113">Primary, Foreign</span></span>  <br/> |<span data-ttu-id="ddfbb-114">通話が開始された日付と時刻。</span><span class="sxs-lookup"><span data-stu-id="ddfbb-114">Date and time that the call began.</span></span>  <br/> |
|<span data-ttu-id="ddfbb-115">**SessionSeq**</span><span class="sxs-lookup"><span data-stu-id="ddfbb-115">**SessionSeq**</span></span> <br/> |<span data-ttu-id="ddfbb-116">int</span><span class="sxs-lookup"><span data-stu-id="ddfbb-116">int</span></span>  <br/> |<span data-ttu-id="ddfbb-117">プライマリ、外部</span><span class="sxs-lookup"><span data-stu-id="ddfbb-117">Primary, Foreign</span></span>  <br/> |<span data-ttu-id="ddfbb-118">同じ日付と同時に開始された可能性がある複数の通話を区別するために使用される一意の識別子。</span><span class="sxs-lookup"><span data-stu-id="ddfbb-118">Unique identifier used to distinguish between multiple calls that might have begun on the same date and at the same time.</span></span>  <br/> |
|<span data-ttu-id="ddfbb-119">**MediaLineLabel**</span><span class="sxs-lookup"><span data-stu-id="ddfbb-119">**MediaLineLabel**</span></span> <br/> |<span data-ttu-id="ddfbb-120">tinyint</span><span class="sxs-lookup"><span data-stu-id="ddfbb-120">tinyint</span></span>  <br/> |<span data-ttu-id="ddfbb-121">プライマリ、外部</span><span class="sxs-lookup"><span data-stu-id="ddfbb-121">Primary, Foreign</span></span>  <br/> |<span data-ttu-id="ddfbb-122">通話で使用されるビデオラインの種類を表します。</span><span class="sxs-lookup"><span data-stu-id="ddfbb-122">Represents the type of video line used in the call.</span></span> <span data-ttu-id="ddfbb-123">有効な値は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="ddfbb-123">Allowed values are:</span></span>  <br/> <span data-ttu-id="ddfbb-124">0-音声</span><span class="sxs-lookup"><span data-stu-id="ddfbb-124">0 - Audio</span></span>  <br/> <span data-ttu-id="ddfbb-125">1-ビデオ</span><span class="sxs-lookup"><span data-stu-id="ddfbb-125">1 - Video</span></span>  <br/> <span data-ttu-id="ddfbb-126">2-パノラマビデオ</span><span class="sxs-lookup"><span data-stu-id="ddfbb-126">2 - Panoramic video</span></span>  <br/> <span data-ttu-id="ddfbb-127">3-アプリケーション/デスクトップ共有</span><span class="sxs-lookup"><span data-stu-id="ddfbb-127">3 - Application/Desktop sharing</span></span>  <br/> |
|<span data-ttu-id="ddfbb-128">**FromCaller**</span><span class="sxs-lookup"><span data-stu-id="ddfbb-128">**FromCaller**</span></span> <br/> |<span data-ttu-id="ddfbb-129">bit</span><span class="sxs-lookup"><span data-stu-id="ddfbb-129">bit</span></span>  <br/> |<span data-ttu-id="ddfbb-130">Primary</span><span class="sxs-lookup"><span data-stu-id="ddfbb-130">Primary</span></span>  <br/> |<span data-ttu-id="ddfbb-131">通話を発信したエンドポイント。</span><span class="sxs-lookup"><span data-stu-id="ddfbb-131">Endpoint that placed the call.</span></span>  <br/> |
|<span data-ttu-id="ddfbb-132">**ホップ**</span><span class="sxs-lookup"><span data-stu-id="ddfbb-132">**Hop**</span></span> <br/> |<span data-ttu-id="ddfbb-133">int</span><span class="sxs-lookup"><span data-stu-id="ddfbb-133">int</span></span>  <br/> ||<span data-ttu-id="ddfbb-134">ネットワークホップ/</span><span class="sxs-lookup"><span data-stu-id="ddfbb-134">Network hop/</span></span>  <br/> |
|<span data-ttu-id="ddfbb-135">**IPAddressKey**</span><span class="sxs-lookup"><span data-stu-id="ddfbb-135">**IPAddressKey**</span></span> <br/> |<span data-ttu-id="ddfbb-136">int</span><span class="sxs-lookup"><span data-stu-id="ddfbb-136">int</span></span>  <br/> |<span data-ttu-id="ddfbb-137">外部</span><span class="sxs-lookup"><span data-stu-id="ddfbb-137">Foreign</span></span>  <br/> |<span data-ttu-id="ddfbb-138">IP アドレスの一意の識別子。</span><span class="sxs-lookup"><span data-stu-id="ddfbb-138">Unique identifier for the IP address.</span></span> <span data-ttu-id="ddfbb-139">IP アドレス情報は、 [IPAddress テーブル](ipaddress.md)に格納されます。</span><span class="sxs-lookup"><span data-stu-id="ddfbb-139">IP address information is stored in the [IPAddress table](ipaddress.md).</span></span>  <br/> |
|<span data-ttu-id="ddfbb-140">**RTT**</span><span class="sxs-lookup"><span data-stu-id="ddfbb-140">**RTT**</span></span> <br/> |<span data-ttu-id="ddfbb-141">int</span><span class="sxs-lookup"><span data-stu-id="ddfbb-141">int</span></span>  <br/> ||<span data-ttu-id="ddfbb-142">往復時間。</span><span class="sxs-lookup"><span data-stu-id="ddfbb-142">Roundtrip time.</span></span> <span data-ttu-id="ddfbb-143">往復時間は、ボイスパケットがその宛先に到達し、受信した通知を返信するのにかかる時間を測定します。</span><span class="sxs-lookup"><span data-stu-id="ddfbb-143">The roundtrip time measures the amount of time it takes for a voice packet to reach its destination and then send back notification that it was received.</span></span>  <br/> |
   

