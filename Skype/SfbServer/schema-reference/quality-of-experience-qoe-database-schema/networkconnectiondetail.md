---
title: NetworkConnectionDetail テーブル
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b48cc9a6-5232-48b5-bd20-53b68229336b
description: NetworkConnectionDetail テーブルは、ネットワーク接続の種類を高品質なエクスペリエンスのデータベース内で使用するネットワーク接続 id にマップします。 このテーブルは、Microsoft Lync Server 2013 で導入されました。
ms.openlocfilehash: cc1eb91d3c633ed9455a0476b613430dfa8e3d6b
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/28/2018
---
# <a name="networkconnectiondetail-table"></a><span data-ttu-id="2f103-104">NetworkConnectionDetail テーブル</span><span class="sxs-lookup"><span data-stu-id="2f103-104">NetworkConnectionDetail table</span></span>
 
<span data-ttu-id="2f103-105">NetworkConnectionDetail テーブルは、ネットワーク接続の種類を高品質なエクスペリエンスのデータベース内で使用するネットワーク接続 id にマップします。</span><span class="sxs-lookup"><span data-stu-id="2f103-105">The NetworkConnectionDetail table maps network connection types to the network connection identifiers used elsewhere in the Quality of Experience database.</span></span> <span data-ttu-id="2f103-106">このテーブルは、Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="2f103-106">This table was introduced in Microsoft Lync Server 2013.</span></span>
  
|<span data-ttu-id="2f103-107">**列**</span><span class="sxs-lookup"><span data-stu-id="2f103-107">**Column**</span></span>|<span data-ttu-id="2f103-108">**データ型**</span><span class="sxs-lookup"><span data-stu-id="2f103-108">**Data Type**</span></span>|<span data-ttu-id="2f103-109">**キーまたはインデックス**</span><span class="sxs-lookup"><span data-stu-id="2f103-109">**Key/Index**</span></span>|<span data-ttu-id="2f103-110">**詳細**</span><span class="sxs-lookup"><span data-stu-id="2f103-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="2f103-111">**NetworkConnectionDetailKey**</span><span class="sxs-lookup"><span data-stu-id="2f103-111">**NetworkConnectionDetailKey**</span></span> <br/> |<span data-ttu-id="2f103-112">tinyint</span><span class="sxs-lookup"><span data-stu-id="2f103-112">tinyint</span></span>  <br/> |<span data-ttu-id="2f103-113">Primary</span><span class="sxs-lookup"><span data-stu-id="2f103-113">Primary</span></span>  <br/> |<span data-ttu-id="2f103-114">ネットワーク接続の種類の一意の識別子です。</span><span class="sxs-lookup"><span data-stu-id="2f103-114">Unique identifier for the network connection type.</span></span>  <br/> |
|<span data-ttu-id="2f103-115">**NetworkConnectionDetail**</span><span class="sxs-lookup"><span data-stu-id="2f103-115">**NetworkConnectionDetail**</span></span> <br/> |<span data-ttu-id="2f103-116">varchar(256)</span><span class="sxs-lookup"><span data-stu-id="2f103-116">varchar(256)</span></span>  <br/> |<span data-ttu-id="2f103-117">一意</span><span class="sxs-lookup"><span data-stu-id="2f103-117">Unique</span></span>  <br/> |<span data-ttu-id="2f103-118">NetworkConnectionDetailKey に対応するネットワーク接続の種類です。</span><span class="sxs-lookup"><span data-stu-id="2f103-118">Network connection type that corresponds to the NetworkConnectionDetailKey.</span></span> <span data-ttu-id="2f103-119">有効な値は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="2f103-119">Allowed values are:</span></span>  <br/> <span data-ttu-id="2f103-120">0--ワイヤード (有線)</span><span class="sxs-lookup"><span data-stu-id="2f103-120">0 -- Wired</span></span>  <br/> <span data-ttu-id="2f103-121">1--WiFi</span><span class="sxs-lookup"><span data-stu-id="2f103-121">1 -- WiFi</span></span>  <br/> <span data-ttu-id="2f103-122">2--イーサネット</span><span class="sxs-lookup"><span data-stu-id="2f103-122">2 -- Ethernet</span></span>  <br/> <span data-ttu-id="2f103-123">3-MobileBB</span><span class="sxs-lookup"><span data-stu-id="2f103-123">3 -- MobileBB</span></span>  <br/> <span data-ttu-id="2f103-124">4-その他の</span><span class="sxs-lookup"><span data-stu-id="2f103-124">4 -- Other</span></span>  <br/> <span data-ttu-id="2f103-125">5--トンネル</span><span class="sxs-lookup"><span data-stu-id="2f103-125">5 -- Tunnel</span></span>  <br/> |
   

