---
title: VideoClientEvent テーブル
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e8ab963b-fe1d-45b3-b9bd-66a5f44c1629
description: 各レコードには、ビデオ通話での1つのエンドポイントのクライアントイベントが含まれています。 通常、1つの通話には2つのレコードがあります。1つは呼び出し元用、もう1つは呼び出し先用です。
ms.openlocfilehash: b8e93206ea30622baa82adcec5ee9a80235521c5
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2019
ms.locfileid: "34294555"
---
# <a name="videoclientevent-table"></a><span data-ttu-id="a8105-104">VideoClientEvent テーブル</span><span class="sxs-lookup"><span data-stu-id="a8105-104">VideoClientEvent table</span></span>
 
<span data-ttu-id="a8105-105">各レコードには、ビデオ通話での1つのエンドポイントのクライアントイベントが含まれています。</span><span class="sxs-lookup"><span data-stu-id="a8105-105">Each record contains client event for one endpoint in a video call.</span></span> <span data-ttu-id="a8105-106">通常、1つの通話には2つのレコードがあります。1つは呼び出し元用、もう1つは呼び出し先用です。</span><span class="sxs-lookup"><span data-stu-id="a8105-106">Usually, one call has two records, one for caller and one for callee.</span></span>
  
|<span data-ttu-id="a8105-107">**列**</span><span class="sxs-lookup"><span data-stu-id="a8105-107">**Column**</span></span>|<span data-ttu-id="a8105-108">**データ型**</span><span class="sxs-lookup"><span data-stu-id="a8105-108">**Data Type**</span></span>|<span data-ttu-id="a8105-109">**キー/インデックス**</span><span class="sxs-lookup"><span data-stu-id="a8105-109">**Key/Index**</span></span>|<span data-ttu-id="a8105-110">**詳細**</span><span class="sxs-lookup"><span data-stu-id="a8105-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="a8105-111">**ConferenceDateTime**</span><span class="sxs-lookup"><span data-stu-id="a8105-111">**ConferenceDateTime**</span></span> <br/> |<span data-ttu-id="a8105-112">datetime</span><span class="sxs-lookup"><span data-stu-id="a8105-112">datetime</span></span>  <br/> |<span data-ttu-id="a8105-113">Primary</span><span class="sxs-lookup"><span data-stu-id="a8105-113">Primary</span></span>  <br/> |<span data-ttu-id="a8105-114">[MediaLine テーブル](medialine-0.md)から参照されます。</span><span class="sxs-lookup"><span data-stu-id="a8105-114">Referenced from the [MediaLine table](medialine-0.md).</span></span>  <br/> |
|<span data-ttu-id="a8105-115">**SessionSeq**</span><span class="sxs-lookup"><span data-stu-id="a8105-115">**SessionSeq**</span></span> <br/> |<span data-ttu-id="a8105-116">int</span><span class="sxs-lookup"><span data-stu-id="a8105-116">int</span></span>  <br/> |<span data-ttu-id="a8105-117">Primary</span><span class="sxs-lookup"><span data-stu-id="a8105-117">Primary</span></span>  <br/> |<span data-ttu-id="a8105-118">[MediaLine テーブル](medialine-0.md)から参照されます。</span><span class="sxs-lookup"><span data-stu-id="a8105-118">Referenced from the [MediaLine table](medialine-0.md).</span></span>  <br/> |
|<span data-ttu-id="a8105-119">**MediaLineLabel**</span><span class="sxs-lookup"><span data-stu-id="a8105-119">**MediaLineLabel**</span></span> <br/> |<span data-ttu-id="a8105-120">tinyint</span><span class="sxs-lookup"><span data-stu-id="a8105-120">tinyint</span></span>  <br/> |<span data-ttu-id="a8105-121">Primary</span><span class="sxs-lookup"><span data-stu-id="a8105-121">Primary</span></span>  <br/> |<span data-ttu-id="a8105-122">[MediaLine テーブル](medialine-0.md)から参照されます。</span><span class="sxs-lookup"><span data-stu-id="a8105-122">Referenced from the [MediaLine table](medialine-0.md).</span></span>  <br/> |
|<span data-ttu-id="a8105-123">**FromCaller**</span><span class="sxs-lookup"><span data-stu-id="a8105-123">**FromCaller**</span></span> <br/> |<span data-ttu-id="a8105-124">bit</span><span class="sxs-lookup"><span data-stu-id="a8105-124">bit</span></span>  <br/> |<span data-ttu-id="a8105-125">Primary</span><span class="sxs-lookup"><span data-stu-id="a8105-125">Primary</span></span>  <br/> |<span data-ttu-id="a8105-126">0: 呼び出し先のデータ</span><span class="sxs-lookup"><span data-stu-id="a8105-126">0: Callee's data</span></span>  <br/> <span data-ttu-id="a8105-127">1: 発信者のデータ</span><span class="sxs-lookup"><span data-stu-id="a8105-127">1: Caller's data</span></span>  <br/> |
|<span data-ttu-id="a8105-128">**NetworkBandwidthLowEventRatio**</span><span class="sxs-lookup"><span data-stu-id="a8105-128">**NetworkBandwidthLowEventRatio**</span></span> <br/> || <br/> |<span data-ttu-id="a8105-129">セッションのパーセンテージ低帯域幅イベントが ' Bad ' 状態に対して発生しました。</span><span class="sxs-lookup"><span data-stu-id="a8105-129">Percentage of session the LowBandwidth event was fired for 'Bad' state.</span></span> <span data-ttu-id="a8105-130">利用可能な音声エクスペリエンスを実現するには、利用可能な帯域幅が不足しています。</span><span class="sxs-lookup"><span data-stu-id="a8105-130">The available bandwidth is insufficient for an acceptable voice experience.</span></span>  <br/> |
|<span data-ttu-id="a8105-131">**NetworkReceiveQualityEventRatio**</span><span class="sxs-lookup"><span data-stu-id="a8105-131">**NetworkReceiveQualityEventRatio**</span></span> <br/> || <br/> |<span data-ttu-id="a8105-132">セッションのパーセンテージ ReceiveSendQuality イベントが ' Bad ' 状態で発生しました。</span><span class="sxs-lookup"><span data-stu-id="a8105-132">Percentage of session the ReceiveSendQuality event was fired for 'Bad' state.</span></span>  <br/> <span data-ttu-id="a8105-133">ネットワーク品質は、ジッタまたはパケット損失の観点では深刻であり、受信中のオーディオの品質に影響します。</span><span class="sxs-lookup"><span data-stu-id="a8105-133">Network quality in terms of jitter or packet loss is severe and impacts the quality of audio being received.</span></span>  <br/> |
   

