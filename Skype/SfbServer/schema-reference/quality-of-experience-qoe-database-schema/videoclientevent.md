---
title: VideoClientEvent テーブル
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e8ab963b-fe1d-45b3-b9bd-66a5f44c1629
description: 各レコードには、ビデオの呼び出しで 1 つのエンドポイントのクライアント イベントが含まれています。 通常、1 回の呼び出しでは、2 つのレコード用の呼び出し元と呼び出し先の 1 つがあります。
ms.openlocfilehash: b0c73cb3bc07a3e258f66555993698c21a978250
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/28/2018
---
# <a name="videoclientevent-table"></a><span data-ttu-id="6ec0b-104">VideoClientEvent テーブル</span><span class="sxs-lookup"><span data-stu-id="6ec0b-104">VideoClientEvent table</span></span>
 
<span data-ttu-id="6ec0b-105">各レコードには、ビデオの呼び出しで 1 つのエンドポイントのクライアント イベントが含まれています。</span><span class="sxs-lookup"><span data-stu-id="6ec0b-105">Each record contains client event for one endpoint in a video call.</span></span> <span data-ttu-id="6ec0b-106">通常、1 回の呼び出しでは、2 つのレコード用の呼び出し元と呼び出し先の 1 つがあります。</span><span class="sxs-lookup"><span data-stu-id="6ec0b-106">Usually, one call has two records, one for caller and one for callee.</span></span>
  
|<span data-ttu-id="6ec0b-107">**列**</span><span class="sxs-lookup"><span data-stu-id="6ec0b-107">**Column**</span></span>|<span data-ttu-id="6ec0b-108">**データ型**</span><span class="sxs-lookup"><span data-stu-id="6ec0b-108">**Data Type**</span></span>|<span data-ttu-id="6ec0b-109">**キーまたはインデックス**</span><span class="sxs-lookup"><span data-stu-id="6ec0b-109">**Key/Index**</span></span>|<span data-ttu-id="6ec0b-110">**詳細**</span><span class="sxs-lookup"><span data-stu-id="6ec0b-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="6ec0b-111">**ConferenceDateTime**</span><span class="sxs-lookup"><span data-stu-id="6ec0b-111">**ConferenceDateTime**</span></span> <br/> |<span data-ttu-id="6ec0b-112">datetime</span><span class="sxs-lookup"><span data-stu-id="6ec0b-112">datetime</span></span>  <br/> |<span data-ttu-id="6ec0b-113">Primary</span><span class="sxs-lookup"><span data-stu-id="6ec0b-113">Primary</span></span>  <br/> |<span data-ttu-id="6ec0b-114">[MediaLine テーブル](medialine-0.md)から参照されています。</span><span class="sxs-lookup"><span data-stu-id="6ec0b-114">Referenced from the [MediaLine table](medialine-0.md).</span></span>  <br/> |
|<span data-ttu-id="6ec0b-115">**SessionSeq**</span><span class="sxs-lookup"><span data-stu-id="6ec0b-115">**SessionSeq**</span></span> <br/> |<span data-ttu-id="6ec0b-116">int</span><span class="sxs-lookup"><span data-stu-id="6ec0b-116">int</span></span>  <br/> |<span data-ttu-id="6ec0b-117">Primary</span><span class="sxs-lookup"><span data-stu-id="6ec0b-117">Primary</span></span>  <br/> |<span data-ttu-id="6ec0b-118">[MediaLine テーブル](medialine-0.md)から参照されています。</span><span class="sxs-lookup"><span data-stu-id="6ec0b-118">Referenced from the [MediaLine table](medialine-0.md).</span></span>  <br/> |
|<span data-ttu-id="6ec0b-119">**MediaLineLabel**</span><span class="sxs-lookup"><span data-stu-id="6ec0b-119">**MediaLineLabel**</span></span> <br/> |<span data-ttu-id="6ec0b-120">tinyint</span><span class="sxs-lookup"><span data-stu-id="6ec0b-120">tinyint</span></span>  <br/> |<span data-ttu-id="6ec0b-121">Primary</span><span class="sxs-lookup"><span data-stu-id="6ec0b-121">Primary</span></span>  <br/> |<span data-ttu-id="6ec0b-122">[MediaLine テーブル](medialine-0.md)から参照されています。</span><span class="sxs-lookup"><span data-stu-id="6ec0b-122">Referenced from the [MediaLine table](medialine-0.md).</span></span>  <br/> |
|<span data-ttu-id="6ec0b-123">**FromCaller**</span><span class="sxs-lookup"><span data-stu-id="6ec0b-123">**FromCaller**</span></span> <br/> |<span data-ttu-id="6ec0b-124">bit</span><span class="sxs-lookup"><span data-stu-id="6ec0b-124">bit</span></span>  <br/> |<span data-ttu-id="6ec0b-125">Primary</span><span class="sxs-lookup"><span data-stu-id="6ec0b-125">Primary</span></span>  <br/> |<span data-ttu-id="6ec0b-126">0: 呼び出し先のデータ</span><span class="sxs-lookup"><span data-stu-id="6ec0b-126">0: Callee's data</span></span>  <br/> <span data-ttu-id="6ec0b-127">1: 呼び出し元のデータ</span><span class="sxs-lookup"><span data-stu-id="6ec0b-127">1: Caller's data</span></span>  <br/> |
|<span data-ttu-id="6ec0b-128">**NetworkBandwidthLowEventRatio**</span><span class="sxs-lookup"><span data-stu-id="6ec0b-128">**NetworkBandwidthLowEventRatio**</span></span> <br/> || <br/> |<span data-ttu-id="6ec0b-129">'正しくない' の状態には、LowBandwidth イベントが発生したセッションの割合です。</span><span class="sxs-lookup"><span data-stu-id="6ec0b-129">Percentage of session the LowBandwidth event was fired for 'Bad' state.</span></span> <span data-ttu-id="6ec0b-130">使用可能な帯域幅は、許容可能な音声操作のための十分ではありません。</span><span class="sxs-lookup"><span data-stu-id="6ec0b-130">The available bandwidth is insufficient for an acceptable voice experience.</span></span>  <br/> |
|<span data-ttu-id="6ec0b-131">**NetworkReceiveQualityEventRatio**</span><span class="sxs-lookup"><span data-stu-id="6ec0b-131">**NetworkReceiveQualityEventRatio**</span></span> <br/> || <br/> |<span data-ttu-id="6ec0b-132">'正しくない' の状態には、ReceiveSendQuality イベントが発生したセッションの割合です。</span><span class="sxs-lookup"><span data-stu-id="6ec0b-132">Percentage of session the ReceiveSendQuality event was fired for 'Bad' state.</span></span>  <br/> <span data-ttu-id="6ec0b-133">ジッターまたはパケット損失の点でネットワーク品質は重大であり、受信されているオーディオの品質に影響を与えます。</span><span class="sxs-lookup"><span data-stu-id="6ec0b-133">Network quality in terms of jitter or packet loss is severe and impacts the quality of audio being received.</span></span>  <br/> |
   

