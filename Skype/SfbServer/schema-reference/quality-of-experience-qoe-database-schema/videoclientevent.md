---
title: VideoClientEvent テーブル
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e8ab963b-fe1d-45b3-b9bd-66a5f44c1629
description: 各レコードには、ビデオの呼び出しで 1 つのエンドポイントのクライアント イベントが含まれています。 通常、1 回の呼び出しでは、2 つのレコード用の呼び出し元と呼び出し先の 1 つがあります。
ms.openlocfilehash: 58179630534733985e062bbe0fafa1bbfd8499db
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "33906827"
---
# <a name="videoclientevent-table"></a><span data-ttu-id="8cc3d-104">VideoClientEvent テーブル</span><span class="sxs-lookup"><span data-stu-id="8cc3d-104">VideoClientEvent table</span></span>
 
<span data-ttu-id="8cc3d-105">各レコードには、ビデオの呼び出しで 1 つのエンドポイントのクライアント イベントが含まれています。</span><span class="sxs-lookup"><span data-stu-id="8cc3d-105">Each record contains client event for one endpoint in a video call.</span></span> <span data-ttu-id="8cc3d-106">通常、1 回の呼び出しでは、2 つのレコード用の呼び出し元と呼び出し先の 1 つがあります。</span><span class="sxs-lookup"><span data-stu-id="8cc3d-106">Usually, one call has two records, one for caller and one for callee.</span></span>
  
|<span data-ttu-id="8cc3d-107">**列**</span><span class="sxs-lookup"><span data-stu-id="8cc3d-107">**Column**</span></span>|<span data-ttu-id="8cc3d-108">**データ型**</span><span class="sxs-lookup"><span data-stu-id="8cc3d-108">**Data Type**</span></span>|<span data-ttu-id="8cc3d-109">**キー/インデックス**</span><span class="sxs-lookup"><span data-stu-id="8cc3d-109">**Key/Index**</span></span>|<span data-ttu-id="8cc3d-110">**詳細**</span><span class="sxs-lookup"><span data-stu-id="8cc3d-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="8cc3d-111">**ConferenceDateTime**</span><span class="sxs-lookup"><span data-stu-id="8cc3d-111">**ConferenceDateTime**</span></span> <br/> |<span data-ttu-id="8cc3d-112">datetime</span><span class="sxs-lookup"><span data-stu-id="8cc3d-112">datetime</span></span>  <br/> |<span data-ttu-id="8cc3d-113">Primary</span><span class="sxs-lookup"><span data-stu-id="8cc3d-113">Primary</span></span>  <br/> |<span data-ttu-id="8cc3d-114">[MediaLine テーブル](medialine-0.md)から参照されています。</span><span class="sxs-lookup"><span data-stu-id="8cc3d-114">Referenced from the [MediaLine table](medialine-0.md).</span></span>  <br/> |
|<span data-ttu-id="8cc3d-115">**SessionSeq**</span><span class="sxs-lookup"><span data-stu-id="8cc3d-115">**SessionSeq**</span></span> <br/> |<span data-ttu-id="8cc3d-116">int</span><span class="sxs-lookup"><span data-stu-id="8cc3d-116">int</span></span>  <br/> |<span data-ttu-id="8cc3d-117">Primary</span><span class="sxs-lookup"><span data-stu-id="8cc3d-117">Primary</span></span>  <br/> |<span data-ttu-id="8cc3d-118">[MediaLine テーブル](medialine-0.md)から参照されています。</span><span class="sxs-lookup"><span data-stu-id="8cc3d-118">Referenced from the [MediaLine table](medialine-0.md).</span></span>  <br/> |
|<span data-ttu-id="8cc3d-119">**MediaLineLabel**</span><span class="sxs-lookup"><span data-stu-id="8cc3d-119">**MediaLineLabel**</span></span> <br/> |<span data-ttu-id="8cc3d-120">tinyint</span><span class="sxs-lookup"><span data-stu-id="8cc3d-120">tinyint</span></span>  <br/> |<span data-ttu-id="8cc3d-121">Primary</span><span class="sxs-lookup"><span data-stu-id="8cc3d-121">Primary</span></span>  <br/> |<span data-ttu-id="8cc3d-122">[MediaLine テーブル](medialine-0.md)から参照されています。</span><span class="sxs-lookup"><span data-stu-id="8cc3d-122">Referenced from the [MediaLine table](medialine-0.md).</span></span>  <br/> |
|<span data-ttu-id="8cc3d-123">**FromCaller**</span><span class="sxs-lookup"><span data-stu-id="8cc3d-123">**FromCaller**</span></span> <br/> |<span data-ttu-id="8cc3d-124">bit</span><span class="sxs-lookup"><span data-stu-id="8cc3d-124">bit</span></span>  <br/> |<span data-ttu-id="8cc3d-125">Primary</span><span class="sxs-lookup"><span data-stu-id="8cc3d-125">Primary</span></span>  <br/> |<span data-ttu-id="8cc3d-126">0: 呼び出し先のデータ</span><span class="sxs-lookup"><span data-stu-id="8cc3d-126">0: Callee's data</span></span>  <br/> <span data-ttu-id="8cc3d-127">1: 呼び出し元のデータ</span><span class="sxs-lookup"><span data-stu-id="8cc3d-127">1: Caller's data</span></span>  <br/> |
|<span data-ttu-id="8cc3d-128">**NetworkBandwidthLowEventRatio**</span><span class="sxs-lookup"><span data-stu-id="8cc3d-128">**NetworkBandwidthLowEventRatio**</span></span> <br/> || <br/> |<span data-ttu-id="8cc3d-129">'正しくない' の状態には、LowBandwidth イベントが発生したセッションの割合です。</span><span class="sxs-lookup"><span data-stu-id="8cc3d-129">Percentage of session the LowBandwidth event was fired for 'Bad' state.</span></span> <span data-ttu-id="8cc3d-130">使用可能な帯域幅は、許容可能な音声操作のための十分ではありません。</span><span class="sxs-lookup"><span data-stu-id="8cc3d-130">The available bandwidth is insufficient for an acceptable voice experience.</span></span>  <br/> |
|<span data-ttu-id="8cc3d-131">**NetworkReceiveQualityEventRatio**</span><span class="sxs-lookup"><span data-stu-id="8cc3d-131">**NetworkReceiveQualityEventRatio**</span></span> <br/> || <br/> |<span data-ttu-id="8cc3d-132">'正しくない' の状態には、ReceiveSendQuality イベントが発生したセッションの割合です。</span><span class="sxs-lookup"><span data-stu-id="8cc3d-132">Percentage of session the ReceiveSendQuality event was fired for 'Bad' state.</span></span>  <br/> <span data-ttu-id="8cc3d-133">ジッターまたはパケット損失の点でネットワーク品質は重大であり、受信されているオーディオの品質に影響を与えます。</span><span class="sxs-lookup"><span data-stu-id="8cc3d-133">Network quality in terms of jitter or packet loss is severe and impacts the quality of audio being received.</span></span>  <br/> |
   

