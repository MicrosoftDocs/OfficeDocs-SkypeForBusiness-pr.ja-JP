---
title: NetworkConnectionDetail テーブル
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b48cc9a6-5232-48b5-bd20-53b68229336b
description: NetworkConnectionDetail テーブルは、ネットワーク接続の種類を、エクスペリエンスデータベースの他の場所で使用されていたネットワーク接続識別子にマップします。 この表は、Microsoft Lync Server 2013 で導入されました。
ms.openlocfilehash: c13725e7df8a164766faa6847fc8097a24a9df53
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2019
ms.locfileid: "34294818"
---
# <a name="networkconnectiondetail-table"></a><span data-ttu-id="aa092-104">NetworkConnectionDetail テーブル</span><span class="sxs-lookup"><span data-stu-id="aa092-104">NetworkConnectionDetail table</span></span>
 
<span data-ttu-id="aa092-105">NetworkConnectionDetail テーブルは、ネットワーク接続の種類を、エクスペリエンスデータベースの他の場所で使用されていたネットワーク接続識別子にマップします。</span><span class="sxs-lookup"><span data-stu-id="aa092-105">The NetworkConnectionDetail table maps network connection types to the network connection identifiers used elsewhere in the Quality of Experience database.</span></span> <span data-ttu-id="aa092-106">この表は、Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="aa092-106">This table was introduced in Microsoft Lync Server 2013.</span></span>
  
|<span data-ttu-id="aa092-107">**列**</span><span class="sxs-lookup"><span data-stu-id="aa092-107">**Column**</span></span>|<span data-ttu-id="aa092-108">**データ型**</span><span class="sxs-lookup"><span data-stu-id="aa092-108">**Data Type**</span></span>|<span data-ttu-id="aa092-109">**キー/インデックス**</span><span class="sxs-lookup"><span data-stu-id="aa092-109">**Key/Index**</span></span>|<span data-ttu-id="aa092-110">**詳細**</span><span class="sxs-lookup"><span data-stu-id="aa092-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="aa092-111">**Networkconnectionのキー**</span><span class="sxs-lookup"><span data-stu-id="aa092-111">**NetworkConnectionDetailKey**</span></span> <br/> |<span data-ttu-id="aa092-112">tinyint</span><span class="sxs-lookup"><span data-stu-id="aa092-112">tinyint</span></span>  <br/> |<span data-ttu-id="aa092-113">Primary</span><span class="sxs-lookup"><span data-stu-id="aa092-113">Primary</span></span>  <br/> |<span data-ttu-id="aa092-114">ネットワーク接続の種類を表す一意の識別子です。</span><span class="sxs-lookup"><span data-stu-id="aa092-114">Unique identifier for the network connection type.</span></span>  <br/> |
|<span data-ttu-id="aa092-115">**NetworkConnectionDetail**</span><span class="sxs-lookup"><span data-stu-id="aa092-115">**NetworkConnectionDetail**</span></span> <br/> |<span data-ttu-id="aa092-116">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="aa092-116">varchar(256)</span></span>  <br/> |<span data-ttu-id="aa092-117">一意</span><span class="sxs-lookup"><span data-stu-id="aa092-117">Unique</span></span>  <br/> |<span data-ttu-id="aa092-118">ネットワーク接続の種類。ネットワーク接続の種類キーに対応しています。</span><span class="sxs-lookup"><span data-stu-id="aa092-118">Network connection type that corresponds to the NetworkConnectionDetailKey.</span></span> <span data-ttu-id="aa092-119">有効な値は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="aa092-119">Allowed values are:</span></span>  <br/> <span data-ttu-id="aa092-120">0--有線</span><span class="sxs-lookup"><span data-stu-id="aa092-120">0 -- Wired</span></span>  <br/> <span data-ttu-id="aa092-121">1--WiFi</span><span class="sxs-lookup"><span data-stu-id="aa092-121">1 -- WiFi</span></span>  <br/> <span data-ttu-id="aa092-122">2--イーサネット</span><span class="sxs-lookup"><span data-stu-id="aa092-122">2 -- Ethernet</span></span>  <br/> <span data-ttu-id="aa092-123">MobileBB</span><span class="sxs-lookup"><span data-stu-id="aa092-123">3 -- MobileBB</span></span>  <br/> <span data-ttu-id="aa092-124">4--その他</span><span class="sxs-lookup"><span data-stu-id="aa092-124">4 -- Other</span></span>  <br/> <span data-ttu-id="aa092-125">5--トンネル</span><span class="sxs-lookup"><span data-stu-id="aa092-125">5 -- Tunnel</span></span>  <br/> |
   

