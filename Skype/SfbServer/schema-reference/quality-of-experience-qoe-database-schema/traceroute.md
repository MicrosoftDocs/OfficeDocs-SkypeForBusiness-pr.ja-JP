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
localization_priority: Normal
ms.assetid: b9493cef-6ece-4f13-bf68-dbf132aab4f4
description: TraceRoute テーブルには、通話のルーティング情報が含まれています。 この表は、Microsoft Lync Server 2013 で導入されました。
ms.openlocfilehash: 323f8160e7543c2fa08bebe9d1805355469acfd9
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2019
ms.locfileid: "34294629"
---
# <a name="traceroute-table"></a><span data-ttu-id="6913b-104">TraceRoute テーブル</span><span class="sxs-lookup"><span data-stu-id="6913b-104">TraceRoute table</span></span>
 
<span data-ttu-id="6913b-105">TraceRoute テーブルには、通話のルーティング情報が含まれています。</span><span class="sxs-lookup"><span data-stu-id="6913b-105">The TraceRoute table contains routing information from calls.</span></span> <span data-ttu-id="6913b-106">この表は、Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="6913b-106">This table was introduced in Microsoft Lync Server 2013.</span></span>
  
|<span data-ttu-id="6913b-107">**列**</span><span class="sxs-lookup"><span data-stu-id="6913b-107">**Column**</span></span>|<span data-ttu-id="6913b-108">**データ型**</span><span class="sxs-lookup"><span data-stu-id="6913b-108">**Data Type**</span></span>|<span data-ttu-id="6913b-109">**キー/インデックス**</span><span class="sxs-lookup"><span data-stu-id="6913b-109">**Key/Index**</span></span>|<span data-ttu-id="6913b-110">**詳細**</span><span class="sxs-lookup"><span data-stu-id="6913b-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="6913b-111">**ConferenceDateTime**</span><span class="sxs-lookup"><span data-stu-id="6913b-111">**ConferenceDateTime**</span></span> <br/> |<span data-ttu-id="6913b-112">datetime</span><span class="sxs-lookup"><span data-stu-id="6913b-112">datetime</span></span>  <br/> |<span data-ttu-id="6913b-113">プライマリ、外部</span><span class="sxs-lookup"><span data-stu-id="6913b-113">Primary, Foreign</span></span>  <br/> |<span data-ttu-id="6913b-114">通話が開始された日付と時刻。</span><span class="sxs-lookup"><span data-stu-id="6913b-114">Date and time that the call began.</span></span>  <br/> |
|<span data-ttu-id="6913b-115">**SessionSeq**</span><span class="sxs-lookup"><span data-stu-id="6913b-115">**SessionSeq**</span></span> <br/> |<span data-ttu-id="6913b-116">int</span><span class="sxs-lookup"><span data-stu-id="6913b-116">int</span></span>  <br/> |<span data-ttu-id="6913b-117">プライマリ、外部</span><span class="sxs-lookup"><span data-stu-id="6913b-117">Primary, Foreign</span></span>  <br/> |<span data-ttu-id="6913b-118">同じ日付と同時に開始された可能性がある複数の通話を区別するために使用される一意の識別子。</span><span class="sxs-lookup"><span data-stu-id="6913b-118">Unique identifier used to distinguish between multiple calls that might have begun on the same date and at the same time.</span></span>  <br/> |
|<span data-ttu-id="6913b-119">**MediaLineLabel**</span><span class="sxs-lookup"><span data-stu-id="6913b-119">**MediaLineLabel**</span></span> <br/> |<span data-ttu-id="6913b-120">tinyint</span><span class="sxs-lookup"><span data-stu-id="6913b-120">tinyint</span></span>  <br/> |<span data-ttu-id="6913b-121">プライマリ、外部</span><span class="sxs-lookup"><span data-stu-id="6913b-121">Primary, Foreign</span></span>  <br/> |<span data-ttu-id="6913b-122">通話で使用されるビデオラインの種類を表します。</span><span class="sxs-lookup"><span data-stu-id="6913b-122">Represents the type of video line used in the call.</span></span> <span data-ttu-id="6913b-123">有効な値は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="6913b-123">Allowed values are:</span></span>  <br/> <span data-ttu-id="6913b-124">0-音声</span><span class="sxs-lookup"><span data-stu-id="6913b-124">0 - Audio</span></span>  <br/> <span data-ttu-id="6913b-125">1-ビデオ</span><span class="sxs-lookup"><span data-stu-id="6913b-125">1 - Video</span></span>  <br/> <span data-ttu-id="6913b-126">2-パノラマビデオ</span><span class="sxs-lookup"><span data-stu-id="6913b-126">2 - Panoramic video</span></span>  <br/> <span data-ttu-id="6913b-127">3-アプリケーション/デスクトップ共有</span><span class="sxs-lookup"><span data-stu-id="6913b-127">3 - Application/Desktop sharing</span></span>  <br/> |
|<span data-ttu-id="6913b-128">**FromCaller**</span><span class="sxs-lookup"><span data-stu-id="6913b-128">**FromCaller**</span></span> <br/> |<span data-ttu-id="6913b-129">bit</span><span class="sxs-lookup"><span data-stu-id="6913b-129">bit</span></span>  <br/> |<span data-ttu-id="6913b-130">Primary</span><span class="sxs-lookup"><span data-stu-id="6913b-130">Primary</span></span>  <br/> |<span data-ttu-id="6913b-131">通話を発信したエンドポイント。</span><span class="sxs-lookup"><span data-stu-id="6913b-131">Endpoint that placed the call.</span></span>  <br/> |
|<span data-ttu-id="6913b-132">**ホップ**</span><span class="sxs-lookup"><span data-stu-id="6913b-132">**Hop**</span></span> <br/> |<span data-ttu-id="6913b-133">int</span><span class="sxs-lookup"><span data-stu-id="6913b-133">int</span></span>  <br/> ||<span data-ttu-id="6913b-134">ネットワークホップ/</span><span class="sxs-lookup"><span data-stu-id="6913b-134">Network hop/</span></span>  <br/> |
|<span data-ttu-id="6913b-135">**IPAddressKey**</span><span class="sxs-lookup"><span data-stu-id="6913b-135">**IPAddressKey**</span></span> <br/> |<span data-ttu-id="6913b-136">int</span><span class="sxs-lookup"><span data-stu-id="6913b-136">int</span></span>  <br/> |<span data-ttu-id="6913b-137">外部</span><span class="sxs-lookup"><span data-stu-id="6913b-137">Foreign</span></span>  <br/> |<span data-ttu-id="6913b-138">IP アドレスの一意の識別子。</span><span class="sxs-lookup"><span data-stu-id="6913b-138">Unique identifier for the IP address.</span></span> <span data-ttu-id="6913b-139">IP アドレス情報は、 [IPAddress テーブル](ipaddress.md)に格納されます。</span><span class="sxs-lookup"><span data-stu-id="6913b-139">IP address information is stored in the [IPAddress table](ipaddress.md).</span></span>  <br/> |
|<span data-ttu-id="6913b-140">**RTT**</span><span class="sxs-lookup"><span data-stu-id="6913b-140">**RTT**</span></span> <br/> |<span data-ttu-id="6913b-141">int</span><span class="sxs-lookup"><span data-stu-id="6913b-141">int</span></span>  <br/> ||<span data-ttu-id="6913b-142">往復時間。</span><span class="sxs-lookup"><span data-stu-id="6913b-142">Roundtrip time.</span></span> <span data-ttu-id="6913b-143">往復時間は、ボイスパケットがその宛先に到達し、受信した通知を返信するのにかかる時間を測定します。</span><span class="sxs-lookup"><span data-stu-id="6913b-143">The roundtrip time measures the amount of time it takes for a voice packet to reach its destination and then send back notification that it was received.</span></span>  <br/> |
   

