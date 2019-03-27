---
title: TraceRoute テーブル
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b9493cef-6ece-4f13-bf68-dbf132aab4f4
description: TraceRoute の表には、呼び出しからのルーティング情報が含まれています。 このテーブルは、Microsoft Lync Server 2013 で導入されました。
ms.openlocfilehash: 741eaabbe94ee1849bd5a7d5e516714861658d7e
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/27/2019
ms.locfileid: "30884902"
---
# <a name="traceroute-table"></a><span data-ttu-id="ee9ae-104">TraceRoute テーブル</span><span class="sxs-lookup"><span data-stu-id="ee9ae-104">TraceRoute table</span></span>
 
<span data-ttu-id="ee9ae-105">TraceRoute の表には、呼び出しからのルーティング情報が含まれています。</span><span class="sxs-lookup"><span data-stu-id="ee9ae-105">The TraceRoute table contains routing information from calls.</span></span> <span data-ttu-id="ee9ae-106">このテーブルは、Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="ee9ae-106">This table was introduced in Microsoft Lync Server 2013.</span></span>
  
|<span data-ttu-id="ee9ae-107">**列**</span><span class="sxs-lookup"><span data-stu-id="ee9ae-107">**Column**</span></span>|<span data-ttu-id="ee9ae-108">**データ型**</span><span class="sxs-lookup"><span data-stu-id="ee9ae-108">**Data Type**</span></span>|<span data-ttu-id="ee9ae-109">**キー/インデックス**</span><span class="sxs-lookup"><span data-stu-id="ee9ae-109">**Key/Index**</span></span>|<span data-ttu-id="ee9ae-110">**詳細**</span><span class="sxs-lookup"><span data-stu-id="ee9ae-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="ee9ae-111">**ConferenceDateTime**</span><span class="sxs-lookup"><span data-stu-id="ee9ae-111">**ConferenceDateTime**</span></span> <br/> |<span data-ttu-id="ee9ae-112">datetime</span><span class="sxs-lookup"><span data-stu-id="ee9ae-112">datetime</span></span>  <br/> |<span data-ttu-id="ee9ae-113">プライマリ サーバーで、外部</span><span class="sxs-lookup"><span data-stu-id="ee9ae-113">Primary, Foreign</span></span>  <br/> |<span data-ttu-id="ee9ae-114">日付と時刻の呼び出しを開始しました。</span><span class="sxs-lookup"><span data-stu-id="ee9ae-114">Date and time that the call began.</span></span>  <br/> |
|<span data-ttu-id="ee9ae-115">**SessionSeq**</span><span class="sxs-lookup"><span data-stu-id="ee9ae-115">**SessionSeq**</span></span> <br/> |<span data-ttu-id="ee9ae-116">int</span><span class="sxs-lookup"><span data-stu-id="ee9ae-116">int</span></span>  <br/> |<span data-ttu-id="ee9ae-117">プライマリ サーバーで、外部</span><span class="sxs-lookup"><span data-stu-id="ee9ae-117">Primary, Foreign</span></span>  <br/> |<span data-ttu-id="ee9ae-118">同時日付けと同時に開始した可能性がある複数の呼び出しを区別するために使用する一意の識別子。</span><span class="sxs-lookup"><span data-stu-id="ee9ae-118">Unique identifier used to distinguish between multiple calls that might have begun on the same date and at the same time.</span></span>  <br/> |
|<span data-ttu-id="ee9ae-119">**MediaLineLabel**</span><span class="sxs-lookup"><span data-stu-id="ee9ae-119">**MediaLineLabel**</span></span> <br/> |<span data-ttu-id="ee9ae-120">tinyint</span><span class="sxs-lookup"><span data-stu-id="ee9ae-120">tinyint</span></span>  <br/> |<span data-ttu-id="ee9ae-121">プライマリ サーバーで、外部</span><span class="sxs-lookup"><span data-stu-id="ee9ae-121">Primary, Foreign</span></span>  <br/> |<span data-ttu-id="ee9ae-122">呼び出しで使用されているビデオの線の種類を表します。</span><span class="sxs-lookup"><span data-stu-id="ee9ae-122">Represents the type of video line used in the call.</span></span> <span data-ttu-id="ee9ae-123">有効な値は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="ee9ae-123">Allowed values are:</span></span>  <br/> <span data-ttu-id="ee9ae-124">0 - オーディオ</span><span class="sxs-lookup"><span data-stu-id="ee9ae-124">0 - Audio</span></span>  <br/> <span data-ttu-id="ee9ae-125">1-ビデオ</span><span class="sxs-lookup"><span data-stu-id="ee9ae-125">1 - Video</span></span>  <br/> <span data-ttu-id="ee9ae-126">2-パノラマ ビデオ</span><span class="sxs-lookup"><span data-stu-id="ee9ae-126">2 - Panoramic video</span></span>  <br/> <span data-ttu-id="ee9ae-127">3-アプリケーションとデスクトップの共有</span><span class="sxs-lookup"><span data-stu-id="ee9ae-127">3 - Application/Desktop sharing</span></span>  <br/> |
|<span data-ttu-id="ee9ae-128">**FromCaller**</span><span class="sxs-lookup"><span data-stu-id="ee9ae-128">**FromCaller**</span></span> <br/> |<span data-ttu-id="ee9ae-129">bit</span><span class="sxs-lookup"><span data-stu-id="ee9ae-129">bit</span></span>  <br/> |<span data-ttu-id="ee9ae-130">Primary</span><span class="sxs-lookup"><span data-stu-id="ee9ae-130">Primary</span></span>  <br/> |<span data-ttu-id="ee9ae-131">呼び出しを配置するエンドポイントです。</span><span class="sxs-lookup"><span data-stu-id="ee9ae-131">Endpoint that placed the call.</span></span>  <br/> |
|<span data-ttu-id="ee9ae-132">**ホップ**</span><span class="sxs-lookup"><span data-stu-id="ee9ae-132">**Hop**</span></span> <br/> |<span data-ttu-id="ee9ae-133">int</span><span class="sxs-lookup"><span data-stu-id="ee9ae-133">int</span></span>  <br/> ||<span data-ttu-id="ee9ae-134">ネットワーク ホップ/</span><span class="sxs-lookup"><span data-stu-id="ee9ae-134">Network hop/</span></span>  <br/> |
|<span data-ttu-id="ee9ae-135">**IPAddressKey**</span><span class="sxs-lookup"><span data-stu-id="ee9ae-135">**IPAddressKey**</span></span> <br/> |<span data-ttu-id="ee9ae-136">int</span><span class="sxs-lookup"><span data-stu-id="ee9ae-136">int</span></span>  <br/> |<span data-ttu-id="ee9ae-137">外部</span><span class="sxs-lookup"><span data-stu-id="ee9ae-137">Foreign</span></span>  <br/> |<span data-ttu-id="ee9ae-138">IP アドレスの一意の識別子です。</span><span class="sxs-lookup"><span data-stu-id="ee9ae-138">Unique identifier for the IP address.</span></span> <span data-ttu-id="ee9ae-139">IP アドレス情報は、 [ip アドレス テーブル](ipaddress.md)に格納されます。</span><span class="sxs-lookup"><span data-stu-id="ee9ae-139">IP address information is stored in the [IPAddress table](ipaddress.md).</span></span>  <br/> |
|<span data-ttu-id="ee9ae-140">**RTT**</span><span class="sxs-lookup"><span data-stu-id="ee9ae-140">**RTT**</span></span> <br/> |<span data-ttu-id="ee9ae-141">int</span><span class="sxs-lookup"><span data-stu-id="ee9ae-141">int</span></span>  <br/> ||<span data-ttu-id="ee9ae-142">ラウンドト リップ時間です。</span><span class="sxs-lookup"><span data-stu-id="ee9ae-142">Roundtrip time.</span></span> <span data-ttu-id="ee9ae-143">ラウンドト リップ時間は、ボイス パケットが送信先に到達し、バックの通知を受け取ったことを送信するためにかかる時間の量を測定します。</span><span class="sxs-lookup"><span data-stu-id="ee9ae-143">The roundtrip time measures the amount of time it takes for a voice packet to reach its destination and then send back notification that it was received.</span></span>  <br/> |
   

