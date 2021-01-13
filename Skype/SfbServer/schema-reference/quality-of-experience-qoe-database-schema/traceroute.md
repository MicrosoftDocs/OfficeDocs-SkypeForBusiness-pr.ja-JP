---
title: TraceRoute テーブル
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: b9493cef-6ece-4f13-bf68-dbf132aab4f4
description: TraceRoute テーブルには、通話からのルーティング情報が含まれています。 この表は、Microsoft Lync Server 2013 で導入されました。
ms.openlocfilehash: 7ecad93cca80a9b7cea73f64158b3c0008a1d6e7
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49831327"
---
# <a name="traceroute-table"></a><span data-ttu-id="b1d4f-104">TraceRoute テーブル</span><span class="sxs-lookup"><span data-stu-id="b1d4f-104">TraceRoute table</span></span>
 
<span data-ttu-id="b1d4f-105">TraceRoute テーブルには、通話からのルーティング情報が含まれています。</span><span class="sxs-lookup"><span data-stu-id="b1d4f-105">The TraceRoute table contains routing information from calls.</span></span> <span data-ttu-id="b1d4f-106">この表は、Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="b1d4f-106">This table was introduced in Microsoft Lync Server 2013.</span></span>
  
|<span data-ttu-id="b1d4f-107">**列**</span><span class="sxs-lookup"><span data-stu-id="b1d4f-107">**Column**</span></span>|<span data-ttu-id="b1d4f-108">**データ型**</span><span class="sxs-lookup"><span data-stu-id="b1d4f-108">**Data Type**</span></span>|<span data-ttu-id="b1d4f-109">**キー/インデックス**</span><span class="sxs-lookup"><span data-stu-id="b1d4f-109">**Key/Index**</span></span>|<span data-ttu-id="b1d4f-110">**詳細**</span><span class="sxs-lookup"><span data-stu-id="b1d4f-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="b1d4f-111">**ConferenceDateTime**</span><span class="sxs-lookup"><span data-stu-id="b1d4f-111">**ConferenceDateTime**</span></span> <br/> |<span data-ttu-id="b1d4f-112">日付型</span><span class="sxs-lookup"><span data-stu-id="b1d4f-112">datetime</span></span>  <br/> |<span data-ttu-id="b1d4f-113">主/プライマリ、外部</span><span class="sxs-lookup"><span data-stu-id="b1d4f-113">Primary, Foreign</span></span>  <br/> |<span data-ttu-id="b1d4f-114">通話が開始された日時。</span><span class="sxs-lookup"><span data-stu-id="b1d4f-114">Date and time that the call began.</span></span>  <br/> |
|<span data-ttu-id="b1d4f-115">**SessionSeq**</span><span class="sxs-lookup"><span data-stu-id="b1d4f-115">**SessionSeq**</span></span> <br/> |<span data-ttu-id="b1d4f-116">int</span><span class="sxs-lookup"><span data-stu-id="b1d4f-116">int</span></span>  <br/> |<span data-ttu-id="b1d4f-117">主/プライマリ、外部</span><span class="sxs-lookup"><span data-stu-id="b1d4f-117">Primary, Foreign</span></span>  <br/> |<span data-ttu-id="b1d4f-118">同じ日付の同じ時刻に開始された可能性がある複数の通話を区別するために使用される一意の識別子。</span><span class="sxs-lookup"><span data-stu-id="b1d4f-118">Unique identifier used to distinguish between multiple calls that might have begun on the same date and at the same time.</span></span>  <br/> |
|<span data-ttu-id="b1d4f-119">**MediaLineLabel**</span><span class="sxs-lookup"><span data-stu-id="b1d4f-119">**MediaLineLabel**</span></span> <br/> |<span data-ttu-id="b1d4f-120">tinyint</span><span class="sxs-lookup"><span data-stu-id="b1d4f-120">tinyint</span></span>  <br/> |<span data-ttu-id="b1d4f-121">主/プライマリ、外部</span><span class="sxs-lookup"><span data-stu-id="b1d4f-121">Primary, Foreign</span></span>  <br/> |<span data-ttu-id="b1d4f-p103">通話で使用されたビデオ回線の種類を表します。有効な値は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="b1d4f-p103">Represents the type of video line used in the call. Allowed values are:</span></span>  <br/> <span data-ttu-id="b1d4f-124">0 - オーディオ</span><span class="sxs-lookup"><span data-stu-id="b1d4f-124">0 - Audio</span></span>  <br/> <span data-ttu-id="b1d4f-125">1 - ビデオ</span><span class="sxs-lookup"><span data-stu-id="b1d4f-125">1 - Video</span></span>  <br/> <span data-ttu-id="b1d4f-126">2 - パノラマ ビデオ</span><span class="sxs-lookup"><span data-stu-id="b1d4f-126">2 - Panoramic video</span></span>  <br/> <span data-ttu-id="b1d4f-127">3 - アプリケーション/デスクトップ共有</span><span class="sxs-lookup"><span data-stu-id="b1d4f-127">3 - Application/Desktop sharing</span></span>  <br/> |
|<span data-ttu-id="b1d4f-128">**FromCaller**</span><span class="sxs-lookup"><span data-stu-id="b1d4f-128">**FromCaller**</span></span> <br/> |<span data-ttu-id="b1d4f-129">bit</span><span class="sxs-lookup"><span data-stu-id="b1d4f-129">bit</span></span>  <br/> |<span data-ttu-id="b1d4f-130">Primary</span><span class="sxs-lookup"><span data-stu-id="b1d4f-130">Primary</span></span>  <br/> |<span data-ttu-id="b1d4f-131">通話を発信したエンドポイント。</span><span class="sxs-lookup"><span data-stu-id="b1d4f-131">Endpoint that placed the call.</span></span>  <br/> |
|<span data-ttu-id="b1d4f-132">**ホップ**</span><span class="sxs-lookup"><span data-stu-id="b1d4f-132">**Hop**</span></span> <br/> |<span data-ttu-id="b1d4f-133">int</span><span class="sxs-lookup"><span data-stu-id="b1d4f-133">int</span></span>  <br/> ||<span data-ttu-id="b1d4f-134">ネットワーク ホップ/</span><span class="sxs-lookup"><span data-stu-id="b1d4f-134">Network hop/</span></span>  <br/> |
|<span data-ttu-id="b1d4f-135">**IPAddressKey**</span><span class="sxs-lookup"><span data-stu-id="b1d4f-135">**IPAddressKey**</span></span> <br/> |<span data-ttu-id="b1d4f-136">int</span><span class="sxs-lookup"><span data-stu-id="b1d4f-136">int</span></span>  <br/> |<span data-ttu-id="b1d4f-137">外部</span><span class="sxs-lookup"><span data-stu-id="b1d4f-137">Foreign</span></span>  <br/> |<span data-ttu-id="b1d4f-138">IP アドレスの一意の識別子。</span><span class="sxs-lookup"><span data-stu-id="b1d4f-138">Unique identifier for the IP address.</span></span> <span data-ttu-id="b1d4f-139">IP アドレス情報は [、IPAddress テーブルに格納されます](ipaddress.md)。</span><span class="sxs-lookup"><span data-stu-id="b1d4f-139">IP address information is stored in the [IPAddress table](ipaddress.md).</span></span>  <br/> |
|<span data-ttu-id="b1d4f-140">**RTT**</span><span class="sxs-lookup"><span data-stu-id="b1d4f-140">**RTT**</span></span> <br/> |<span data-ttu-id="b1d4f-141">int</span><span class="sxs-lookup"><span data-stu-id="b1d4f-141">int</span></span>  <br/> ||<span data-ttu-id="b1d4f-p105">ラウンド トリップ時間。ラウンド トリップ時間は、音声パケットが宛先に到達してから受信通知を送り返すまでにかかる時間を測定します。</span><span class="sxs-lookup"><span data-stu-id="b1d4f-p105">Roundtrip time. The roundtrip time measures the amount of time it takes for a voice packet to reach its destination and then send back notification that it was received.</span></span>  <br/> |
   

