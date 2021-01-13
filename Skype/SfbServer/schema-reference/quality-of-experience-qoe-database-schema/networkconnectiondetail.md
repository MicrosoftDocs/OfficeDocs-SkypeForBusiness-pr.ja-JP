---
title: NetworkConnectionDetail テーブル
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
ms.assetid: b48cc9a6-5232-48b5-bd20-53b68229336b
description: NetworkConnectionDetail テーブルは、Quality of Experience データベースの他の場所で使用されるネットワーク接続の識別子にネットワーク接続の種類を対応させます。 この表は、Microsoft Lync Server 2013 で導入されました。
ms.openlocfilehash: 2e03e7935370e71a8070ed1882f61ac5480f312e
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49806307"
---
# <a name="networkconnectiondetail-table"></a><span data-ttu-id="0bea0-104">NetworkConnectionDetail テーブル</span><span class="sxs-lookup"><span data-stu-id="0bea0-104">NetworkConnectionDetail table</span></span>
 
<span data-ttu-id="0bea0-105">NetworkConnectionDetail テーブルは、Quality of Experience データベースの他の場所で使用されるネットワーク接続の識別子にネットワーク接続の種類を対応させます。</span><span class="sxs-lookup"><span data-stu-id="0bea0-105">The NetworkConnectionDetail table maps network connection types to the network connection identifiers used elsewhere in the Quality of Experience database.</span></span> <span data-ttu-id="0bea0-106">この表は、Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="0bea0-106">This table was introduced in Microsoft Lync Server 2013.</span></span>
  
|<span data-ttu-id="0bea0-107">**列**</span><span class="sxs-lookup"><span data-stu-id="0bea0-107">**Column**</span></span>|<span data-ttu-id="0bea0-108">**データ型**</span><span class="sxs-lookup"><span data-stu-id="0bea0-108">**Data Type**</span></span>|<span data-ttu-id="0bea0-109">**キー/インデックス**</span><span class="sxs-lookup"><span data-stu-id="0bea0-109">**Key/Index**</span></span>|<span data-ttu-id="0bea0-110">**詳細**</span><span class="sxs-lookup"><span data-stu-id="0bea0-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="0bea0-111">**NetworkConnectionDetailKey**</span><span class="sxs-lookup"><span data-stu-id="0bea0-111">**NetworkConnectionDetailKey**</span></span> <br/> |<span data-ttu-id="0bea0-112">tinyint</span><span class="sxs-lookup"><span data-stu-id="0bea0-112">tinyint</span></span>  <br/> |<span data-ttu-id="0bea0-113">Primary</span><span class="sxs-lookup"><span data-stu-id="0bea0-113">Primary</span></span>  <br/> |<span data-ttu-id="0bea0-114">ネットワーク接続の種類の一意の識別子。</span><span class="sxs-lookup"><span data-stu-id="0bea0-114">Unique identifier for the network connection type.</span></span>  <br/> |
|<span data-ttu-id="0bea0-115">**NetworkConnectionDetail**</span><span class="sxs-lookup"><span data-stu-id="0bea0-115">**NetworkConnectionDetail**</span></span> <br/> |<span data-ttu-id="0bea0-116">varchar(256)</span><span class="sxs-lookup"><span data-stu-id="0bea0-116">varchar(256)</span></span>  <br/> |<span data-ttu-id="0bea0-117">一意</span><span class="sxs-lookup"><span data-stu-id="0bea0-117">Unique</span></span>  <br/> |<span data-ttu-id="0bea0-p103">NetworkConnectionDetailKey に対応するネットワーク接続の種類。有効な値は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="0bea0-p103">Network connection type that corresponds to the NetworkConnectionDetailKey. Allowed values are:</span></span>  <br/> <span data-ttu-id="0bea0-120">0: 有線</span><span class="sxs-lookup"><span data-stu-id="0bea0-120">0 -- Wired</span></span>  <br/> <span data-ttu-id="0bea0-121">1: WiFi</span><span class="sxs-lookup"><span data-stu-id="0bea0-121">1 -- WiFi</span></span>  <br/> <span data-ttu-id="0bea0-122">2: イーサネット</span><span class="sxs-lookup"><span data-stu-id="0bea0-122">2 -- Ethernet</span></span>  <br/> <span data-ttu-id="0bea0-123">3 -- MobileBB</span><span class="sxs-lookup"><span data-stu-id="0bea0-123">3 -- MobileBB</span></span>  <br/> <span data-ttu-id="0bea0-124">4 -- その他</span><span class="sxs-lookup"><span data-stu-id="0bea0-124">4 -- Other</span></span>  <br/> <span data-ttu-id="0bea0-125">5 -- トンネル</span><span class="sxs-lookup"><span data-stu-id="0bea0-125">5 -- Tunnel</span></span>  <br/> |
   

