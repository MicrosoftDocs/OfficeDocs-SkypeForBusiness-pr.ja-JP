---
title: VideoClientEvent テーブル
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
ms.assetid: e8ab963b-fe1d-45b3-b9bd-66a5f44c1629
description: 各レコードには、ビデオ通話の 1 つのエンドポイントのクライアント イベントが含まれる。 通常、1 つの呼び出しには 2 つのレコードがあります。1 つは呼び出し元用で、もう 1 つは呼び出し先用です。
ms.openlocfilehash: bb4a9feca562bed7bdb0080e7f9181003952f5d4
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49821397"
---
# <a name="videoclientevent-table"></a><span data-ttu-id="9acc6-104">VideoClientEvent テーブル</span><span class="sxs-lookup"><span data-stu-id="9acc6-104">VideoClientEvent table</span></span>
 
<span data-ttu-id="9acc6-105">各レコードには、ビデオ通話の 1 つのエンドポイントのクライアント イベントが含まれる。</span><span class="sxs-lookup"><span data-stu-id="9acc6-105">Each record contains client event for one endpoint in a video call.</span></span> <span data-ttu-id="9acc6-106">通常、1 つの呼び出しには、呼び出し元用と呼び出し先用の 2 つのレコードがあります。</span><span class="sxs-lookup"><span data-stu-id="9acc6-106">Usually, one call has two records, one for caller and one for callee.</span></span>
  
|<span data-ttu-id="9acc6-107">**列**</span><span class="sxs-lookup"><span data-stu-id="9acc6-107">**Column**</span></span>|<span data-ttu-id="9acc6-108">**データ型**</span><span class="sxs-lookup"><span data-stu-id="9acc6-108">**Data Type**</span></span>|<span data-ttu-id="9acc6-109">**キー/インデックス**</span><span class="sxs-lookup"><span data-stu-id="9acc6-109">**Key/Index**</span></span>|<span data-ttu-id="9acc6-110">**詳細**</span><span class="sxs-lookup"><span data-stu-id="9acc6-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="9acc6-111">**ConferenceDateTime**</span><span class="sxs-lookup"><span data-stu-id="9acc6-111">**ConferenceDateTime**</span></span> <br/> |<span data-ttu-id="9acc6-112">日付型</span><span class="sxs-lookup"><span data-stu-id="9acc6-112">datetime</span></span>  <br/> |<span data-ttu-id="9acc6-113">Primary</span><span class="sxs-lookup"><span data-stu-id="9acc6-113">Primary</span></span>  <br/> |<span data-ttu-id="9acc6-114">[MediaLine テーブルから参照されます](medialine-0.md)。</span><span class="sxs-lookup"><span data-stu-id="9acc6-114">Referenced from the [MediaLine table](medialine-0.md).</span></span>  <br/> |
|<span data-ttu-id="9acc6-115">**SessionSeq**</span><span class="sxs-lookup"><span data-stu-id="9acc6-115">**SessionSeq**</span></span> <br/> |<span data-ttu-id="9acc6-116">int</span><span class="sxs-lookup"><span data-stu-id="9acc6-116">int</span></span>  <br/> |<span data-ttu-id="9acc6-117">Primary</span><span class="sxs-lookup"><span data-stu-id="9acc6-117">Primary</span></span>  <br/> |<span data-ttu-id="9acc6-118">[MediaLine テーブルから参照されます](medialine-0.md)。</span><span class="sxs-lookup"><span data-stu-id="9acc6-118">Referenced from the [MediaLine table](medialine-0.md).</span></span>  <br/> |
|<span data-ttu-id="9acc6-119">**MediaLineLabel**</span><span class="sxs-lookup"><span data-stu-id="9acc6-119">**MediaLineLabel**</span></span> <br/> |<span data-ttu-id="9acc6-120">tinyint</span><span class="sxs-lookup"><span data-stu-id="9acc6-120">tinyint</span></span>  <br/> |<span data-ttu-id="9acc6-121">Primary</span><span class="sxs-lookup"><span data-stu-id="9acc6-121">Primary</span></span>  <br/> |<span data-ttu-id="9acc6-122">[MediaLine テーブルから参照されます](medialine-0.md)。</span><span class="sxs-lookup"><span data-stu-id="9acc6-122">Referenced from the [MediaLine table](medialine-0.md).</span></span>  <br/> |
|<span data-ttu-id="9acc6-123">**FromCaller**</span><span class="sxs-lookup"><span data-stu-id="9acc6-123">**FromCaller**</span></span> <br/> |<span data-ttu-id="9acc6-124">bit</span><span class="sxs-lookup"><span data-stu-id="9acc6-124">bit</span></span>  <br/> |<span data-ttu-id="9acc6-125">Primary</span><span class="sxs-lookup"><span data-stu-id="9acc6-125">Primary</span></span>  <br/> |<span data-ttu-id="9acc6-126">0: 呼び出し先のデータ</span><span class="sxs-lookup"><span data-stu-id="9acc6-126">0: Callee's data</span></span>  <br/> <span data-ttu-id="9acc6-127">1: 発信者のデータ</span><span class="sxs-lookup"><span data-stu-id="9acc6-127">1: Caller's data</span></span>  <br/> |
|<span data-ttu-id="9acc6-128">**NetworkBandwidthLowEventRatio**</span><span class="sxs-lookup"><span data-stu-id="9acc6-128">**NetworkBandwidthLowEventRatio**</span></span> <br/> || <br/> |<span data-ttu-id="9acc6-129">LowBandwidth イベントが "Bad" 状態で発生したセッションの割合。</span><span class="sxs-lookup"><span data-stu-id="9acc6-129">Percentage of session the LowBandwidth event was fired for 'Bad' state.</span></span> <span data-ttu-id="9acc6-130">使用可能な帯域幅は、許容できる音声エクスペリエンスには不十分です。</span><span class="sxs-lookup"><span data-stu-id="9acc6-130">The available bandwidth is insufficient for an acceptable voice experience.</span></span>  <br/> |
|<span data-ttu-id="9acc6-131">**NetworkReceiveQualityEventRatio**</span><span class="sxs-lookup"><span data-stu-id="9acc6-131">**NetworkReceiveQualityEventRatio**</span></span> <br/> || <br/> |<span data-ttu-id="9acc6-132">ReceiveSendQuality イベントが "Bad" 状態で発生したセッションの割合。</span><span class="sxs-lookup"><span data-stu-id="9acc6-132">Percentage of session the ReceiveSendQuality event was fired for 'Bad' state.</span></span>  <br/> <span data-ttu-id="9acc6-133">ジッターまたはパケット損失の観点から見たネットワーク品質は重大であり、受信する音声の品質に影響します。</span><span class="sxs-lookup"><span data-stu-id="9acc6-133">Network quality in terms of jitter or packet loss is severe and impacts the quality of audio being received.</span></span>  <br/> |
   

