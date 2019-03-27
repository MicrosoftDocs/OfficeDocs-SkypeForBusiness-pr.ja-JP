---
title: NetworkConnectionDetail テーブル
ms.reviewer: ''
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
ms.openlocfilehash: 6df2511c2dfee0158b4633be5dfa8549639cfc6d
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/27/2019
ms.locfileid: "30889057"
---
# <a name="networkconnectiondetail-table"></a><span data-ttu-id="af8bf-104">NetworkConnectionDetail テーブル</span><span class="sxs-lookup"><span data-stu-id="af8bf-104">NetworkConnectionDetail table</span></span>
 
<span data-ttu-id="af8bf-105">NetworkConnectionDetail テーブルは、ネットワーク接続の種類を高品質なエクスペリエンスのデータベース内で使用するネットワーク接続 id にマップします。</span><span class="sxs-lookup"><span data-stu-id="af8bf-105">The NetworkConnectionDetail table maps network connection types to the network connection identifiers used elsewhere in the Quality of Experience database.</span></span> <span data-ttu-id="af8bf-106">このテーブルは、Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="af8bf-106">This table was introduced in Microsoft Lync Server 2013.</span></span>
  
|<span data-ttu-id="af8bf-107">**列**</span><span class="sxs-lookup"><span data-stu-id="af8bf-107">**Column**</span></span>|<span data-ttu-id="af8bf-108">**データ型**</span><span class="sxs-lookup"><span data-stu-id="af8bf-108">**Data Type**</span></span>|<span data-ttu-id="af8bf-109">**キー/インデックス**</span><span class="sxs-lookup"><span data-stu-id="af8bf-109">**Key/Index**</span></span>|<span data-ttu-id="af8bf-110">**詳細**</span><span class="sxs-lookup"><span data-stu-id="af8bf-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="af8bf-111">**NetworkConnectionDetailKey**</span><span class="sxs-lookup"><span data-stu-id="af8bf-111">**NetworkConnectionDetailKey**</span></span> <br/> |<span data-ttu-id="af8bf-112">tinyint</span><span class="sxs-lookup"><span data-stu-id="af8bf-112">tinyint</span></span>  <br/> |<span data-ttu-id="af8bf-113">Primary</span><span class="sxs-lookup"><span data-stu-id="af8bf-113">Primary</span></span>  <br/> |<span data-ttu-id="af8bf-114">ネットワーク接続の種類の一意の識別子です。</span><span class="sxs-lookup"><span data-stu-id="af8bf-114">Unique identifier for the network connection type.</span></span>  <br/> |
|<span data-ttu-id="af8bf-115">**NetworkConnectionDetail**</span><span class="sxs-lookup"><span data-stu-id="af8bf-115">**NetworkConnectionDetail**</span></span> <br/> |<span data-ttu-id="af8bf-116">varchar(256)</span><span class="sxs-lookup"><span data-stu-id="af8bf-116">varchar(256)</span></span>  <br/> |<span data-ttu-id="af8bf-117">一意</span><span class="sxs-lookup"><span data-stu-id="af8bf-117">Unique</span></span>  <br/> |<span data-ttu-id="af8bf-118">NetworkConnectionDetailKey に対応するネットワーク接続の種類です。</span><span class="sxs-lookup"><span data-stu-id="af8bf-118">Network connection type that corresponds to the NetworkConnectionDetailKey.</span></span> <span data-ttu-id="af8bf-119">有効な値は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="af8bf-119">Allowed values are:</span></span>  <br/> <span data-ttu-id="af8bf-120">0--ワイヤード (有線)</span><span class="sxs-lookup"><span data-stu-id="af8bf-120">0 -- Wired</span></span>  <br/> <span data-ttu-id="af8bf-121">1--WiFi</span><span class="sxs-lookup"><span data-stu-id="af8bf-121">1 -- WiFi</span></span>  <br/> <span data-ttu-id="af8bf-122">2--イーサネット</span><span class="sxs-lookup"><span data-stu-id="af8bf-122">2 -- Ethernet</span></span>  <br/> <span data-ttu-id="af8bf-123">3-MobileBB</span><span class="sxs-lookup"><span data-stu-id="af8bf-123">3 -- MobileBB</span></span>  <br/> <span data-ttu-id="af8bf-124">4-その他の</span><span class="sxs-lookup"><span data-stu-id="af8bf-124">4 -- Other</span></span>  <br/> <span data-ttu-id="af8bf-125">5--トンネル</span><span class="sxs-lookup"><span data-stu-id="af8bf-125">5 -- Tunnel</span></span>  <br/> |
   

