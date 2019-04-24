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
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "32212075"
---
# <a name="traceroute-table"></a><span data-ttu-id="9b00f-104">TraceRoute テーブル</span><span class="sxs-lookup"><span data-stu-id="9b00f-104">TraceRoute table</span></span>
 
<span data-ttu-id="9b00f-105">TraceRoute の表には、呼び出しからのルーティング情報が含まれています。</span><span class="sxs-lookup"><span data-stu-id="9b00f-105">The TraceRoute table contains routing information from calls.</span></span> <span data-ttu-id="9b00f-106">このテーブルは、Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="9b00f-106">This table was introduced in Microsoft Lync Server 2013.</span></span>
  
|<span data-ttu-id="9b00f-107">**列**</span><span class="sxs-lookup"><span data-stu-id="9b00f-107">**Column**</span></span>|<span data-ttu-id="9b00f-108">**データ型**</span><span class="sxs-lookup"><span data-stu-id="9b00f-108">**Data Type**</span></span>|<span data-ttu-id="9b00f-109">**キー/インデックス**</span><span class="sxs-lookup"><span data-stu-id="9b00f-109">**Key/Index**</span></span>|<span data-ttu-id="9b00f-110">**詳細**</span><span class="sxs-lookup"><span data-stu-id="9b00f-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="9b00f-111">**ConferenceDateTime**</span><span class="sxs-lookup"><span data-stu-id="9b00f-111">**ConferenceDateTime**</span></span> <br/> |<span data-ttu-id="9b00f-112">datetime</span><span class="sxs-lookup"><span data-stu-id="9b00f-112">datetime</span></span>  <br/> |<span data-ttu-id="9b00f-113">プライマリ サーバーで、外部</span><span class="sxs-lookup"><span data-stu-id="9b00f-113">Primary, Foreign</span></span>  <br/> |<span data-ttu-id="9b00f-114">日付と時刻の呼び出しを開始しました。</span><span class="sxs-lookup"><span data-stu-id="9b00f-114">Date and time that the call began.</span></span>  <br/> |
|<span data-ttu-id="9b00f-115">**SessionSeq**</span><span class="sxs-lookup"><span data-stu-id="9b00f-115">**SessionSeq**</span></span> <br/> |<span data-ttu-id="9b00f-116">int</span><span class="sxs-lookup"><span data-stu-id="9b00f-116">int</span></span>  <br/> |<span data-ttu-id="9b00f-117">プライマリ サーバーで、外部</span><span class="sxs-lookup"><span data-stu-id="9b00f-117">Primary, Foreign</span></span>  <br/> |<span data-ttu-id="9b00f-118">同時日付けと同時に開始した可能性がある複数の呼び出しを区別するために使用する一意の識別子。</span><span class="sxs-lookup"><span data-stu-id="9b00f-118">Unique identifier used to distinguish between multiple calls that might have begun on the same date and at the same time.</span></span>  <br/> |
|<span data-ttu-id="9b00f-119">**MediaLineLabel**</span><span class="sxs-lookup"><span data-stu-id="9b00f-119">**MediaLineLabel**</span></span> <br/> |<span data-ttu-id="9b00f-120">tinyint</span><span class="sxs-lookup"><span data-stu-id="9b00f-120">tinyint</span></span>  <br/> |<span data-ttu-id="9b00f-121">プライマリ サーバーで、外部</span><span class="sxs-lookup"><span data-stu-id="9b00f-121">Primary, Foreign</span></span>  <br/> |<span data-ttu-id="9b00f-122">呼び出しで使用されているビデオの線の種類を表します。</span><span class="sxs-lookup"><span data-stu-id="9b00f-122">Represents the type of video line used in the call.</span></span> <span data-ttu-id="9b00f-123">有効な値は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="9b00f-123">Allowed values are:</span></span>  <br/> <span data-ttu-id="9b00f-124">0 - オーディオ</span><span class="sxs-lookup"><span data-stu-id="9b00f-124">0 - Audio</span></span>  <br/> <span data-ttu-id="9b00f-125">1-ビデオ</span><span class="sxs-lookup"><span data-stu-id="9b00f-125">1 - Video</span></span>  <br/> <span data-ttu-id="9b00f-126">2-パノラマ ビデオ</span><span class="sxs-lookup"><span data-stu-id="9b00f-126">2 - Panoramic video</span></span>  <br/> <span data-ttu-id="9b00f-127">3-アプリケーションとデスクトップの共有</span><span class="sxs-lookup"><span data-stu-id="9b00f-127">3 - Application/Desktop sharing</span></span>  <br/> |
|<span data-ttu-id="9b00f-128">**FromCaller**</span><span class="sxs-lookup"><span data-stu-id="9b00f-128">**FromCaller**</span></span> <br/> |<span data-ttu-id="9b00f-129">bit</span><span class="sxs-lookup"><span data-stu-id="9b00f-129">bit</span></span>  <br/> |<span data-ttu-id="9b00f-130">Primary</span><span class="sxs-lookup"><span data-stu-id="9b00f-130">Primary</span></span>  <br/> |<span data-ttu-id="9b00f-131">呼び出しを配置するエンドポイントです。</span><span class="sxs-lookup"><span data-stu-id="9b00f-131">Endpoint that placed the call.</span></span>  <br/> |
|<span data-ttu-id="9b00f-132">**ホップ**</span><span class="sxs-lookup"><span data-stu-id="9b00f-132">**Hop**</span></span> <br/> |<span data-ttu-id="9b00f-133">int</span><span class="sxs-lookup"><span data-stu-id="9b00f-133">int</span></span>  <br/> ||<span data-ttu-id="9b00f-134">ネットワーク ホップ/</span><span class="sxs-lookup"><span data-stu-id="9b00f-134">Network hop/</span></span>  <br/> |
|<span data-ttu-id="9b00f-135">**IPAddressKey**</span><span class="sxs-lookup"><span data-stu-id="9b00f-135">**IPAddressKey**</span></span> <br/> |<span data-ttu-id="9b00f-136">int</span><span class="sxs-lookup"><span data-stu-id="9b00f-136">int</span></span>  <br/> |<span data-ttu-id="9b00f-137">外部</span><span class="sxs-lookup"><span data-stu-id="9b00f-137">Foreign</span></span>  <br/> |<span data-ttu-id="9b00f-138">IP アドレスの一意の識別子です。</span><span class="sxs-lookup"><span data-stu-id="9b00f-138">Unique identifier for the IP address.</span></span> <span data-ttu-id="9b00f-139">IP アドレス情報は、 [ip アドレス テーブル](ipaddress.md)に格納されます。</span><span class="sxs-lookup"><span data-stu-id="9b00f-139">IP address information is stored in the [IPAddress table](ipaddress.md).</span></span>  <br/> |
|<span data-ttu-id="9b00f-140">**RTT**</span><span class="sxs-lookup"><span data-stu-id="9b00f-140">**RTT**</span></span> <br/> |<span data-ttu-id="9b00f-141">int</span><span class="sxs-lookup"><span data-stu-id="9b00f-141">int</span></span>  <br/> ||<span data-ttu-id="9b00f-142">ラウンドト リップ時間です。</span><span class="sxs-lookup"><span data-stu-id="9b00f-142">Roundtrip time.</span></span> <span data-ttu-id="9b00f-143">ラウンドト リップ時間は、ボイス パケットが送信先に到達し、バックの通知を受け取ったことを送信するためにかかる時間の量を測定します。</span><span class="sxs-lookup"><span data-stu-id="9b00f-143">The roundtrip time measures the amount of time it takes for a voice packet to reach its destination and then send back notification that it was received.</span></span>  <br/> |
   

