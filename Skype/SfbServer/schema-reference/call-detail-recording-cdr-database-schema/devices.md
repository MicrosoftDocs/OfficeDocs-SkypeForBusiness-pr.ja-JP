---
title: Skype for Business Server 2015 の Devices テーブル
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 532e2280-4bbc-4a6c-93da-45d9f80a30a0
description: Devices テーブルは、サポートテーブルです。 各レコードには、1つのデバイス (卓上電話) に関する情報が格納されます。
ms.openlocfilehash: 145637b6385677007efa47cd21b3f0ea7d7f88f2
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2019
ms.locfileid: "34296379"
---
# <a name="devices-table-in-skype-for-business-server-2015"></a><span data-ttu-id="4b1c9-104">Skype for Business Server 2015 の Devices テーブル</span><span class="sxs-lookup"><span data-stu-id="4b1c9-104">Devices table in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="4b1c9-105">Devices テーブルは、サポートテーブルです。</span><span class="sxs-lookup"><span data-stu-id="4b1c9-105">The Devices table is a supporting table.</span></span> <span data-ttu-id="4b1c9-106">各レコードには、1つのデバイス (卓上電話) に関する情報が格納されます。</span><span class="sxs-lookup"><span data-stu-id="4b1c9-106">Each record stores information about one device (desk phone).</span></span>
  
|<span data-ttu-id="4b1c9-107">**列**</span><span class="sxs-lookup"><span data-stu-id="4b1c9-107">**Column**</span></span>|<span data-ttu-id="4b1c9-108">**データ型**</span><span class="sxs-lookup"><span data-stu-id="4b1c9-108">**Data Type**</span></span>|<span data-ttu-id="4b1c9-109">**キー/インデックス**</span><span class="sxs-lookup"><span data-stu-id="4b1c9-109">**Key/Index**</span></span>|<span data-ttu-id="4b1c9-110">**詳細**</span><span class="sxs-lookup"><span data-stu-id="4b1c9-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="4b1c9-111">**DeviceId**</span><span class="sxs-lookup"><span data-stu-id="4b1c9-111">**DeviceId**</span></span> <br/> |<span data-ttu-id="4b1c9-112">int</span><span class="sxs-lookup"><span data-stu-id="4b1c9-112">int</span></span>  <br/> |<span data-ttu-id="4b1c9-113">Primary</span><span class="sxs-lookup"><span data-stu-id="4b1c9-113">Primary</span></span>  <br/> |<span data-ttu-id="4b1c9-114">このハードウェアバージョンを識別する一意の番号。</span><span class="sxs-lookup"><span data-stu-id="4b1c9-114">Unique number identifying this hardware version.</span></span>  <br/> |
|<span data-ttu-id="4b1c9-115">**Manufacturerid]**</span><span class="sxs-lookup"><span data-stu-id="4b1c9-115">**ManufacturerId**</span></span> <br/> |<span data-ttu-id="4b1c9-116">int</span><span class="sxs-lookup"><span data-stu-id="4b1c9-116">int</span></span>  <br/> |<span data-ttu-id="4b1c9-117">外部</span><span class="sxs-lookup"><span data-stu-id="4b1c9-117">Foreign</span></span>  <br/> |<span data-ttu-id="4b1c9-118">このデバイスの製造元。</span><span class="sxs-lookup"><span data-stu-id="4b1c9-118">Manufacturer of this device.</span></span> <span data-ttu-id="4b1c9-119">詳細については、「 [Skype For Business Server 2015 の製造元の表](manufacturers.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4b1c9-119">See the [Manufacturers table in Skype for Business Server 2015](manufacturers.md) for more information.</span></span> <br/> |
|<span data-ttu-id="4b1c9-120">**ハードウェアの Versionid**</span><span class="sxs-lookup"><span data-stu-id="4b1c9-120">**HardwareVersionId**</span></span> <br/> |<span data-ttu-id="4b1c9-121">int</span><span class="sxs-lookup"><span data-stu-id="4b1c9-121">int</span></span>  <br/> |<span data-ttu-id="4b1c9-122">外部</span><span class="sxs-lookup"><span data-stu-id="4b1c9-122">Foreign</span></span>  <br/> |<span data-ttu-id="4b1c9-123">このデバイスのハードウェアバージョン。</span><span class="sxs-lookup"><span data-stu-id="4b1c9-123">Hardware version of this device.</span></span> <span data-ttu-id="4b1c9-124">詳細については、「 [Skype For Business Server 2015 のハードウェアバージョン](hardwareversions.md)」の表を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4b1c9-124">See the [HardwareVersions table in Skype for Business Server 2015](hardwareversions.md) for more information.</span></span> <br/> |
|<span data-ttu-id="4b1c9-125">**MacAddress**</span><span class="sxs-lookup"><span data-stu-id="4b1c9-125">**MacAddress**</span></span> <br/> |<span data-ttu-id="4b1c9-126">bigint</span><span class="sxs-lookup"><span data-stu-id="4b1c9-126">bigint</span></span>  <br/> ||<span data-ttu-id="4b1c9-127">MAC アドレス</span><span class="sxs-lookup"><span data-stu-id="4b1c9-127">MAC Address</span></span>  <br/> |
   

