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
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 532e2280-4bbc-4a6c-93da-45d9f80a30a0
description: Devices テーブルは、サポートテーブルです。 各レコードには、1つのデバイス (卓上電話) に関する情報が格納されます。
ms.openlocfilehash: e53a8947d106d6a92d7cf5cb881f20022e1bac69
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2020
ms.locfileid: "41815285"
---
# <a name="devices-table-in-skype-for-business-server-2015"></a><span data-ttu-id="cdfcc-104">Skype for Business Server 2015 の Devices テーブル</span><span class="sxs-lookup"><span data-stu-id="cdfcc-104">Devices table in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="cdfcc-105">Devices テーブルは、サポートテーブルです。</span><span class="sxs-lookup"><span data-stu-id="cdfcc-105">The Devices table is a supporting table.</span></span> <span data-ttu-id="cdfcc-106">各レコードには、1つのデバイス (卓上電話) に関する情報が格納されます。</span><span class="sxs-lookup"><span data-stu-id="cdfcc-106">Each record stores information about one device (desk phone).</span></span>
  
|<span data-ttu-id="cdfcc-107">**列**</span><span class="sxs-lookup"><span data-stu-id="cdfcc-107">**Column**</span></span>|<span data-ttu-id="cdfcc-108">**データ型**</span><span class="sxs-lookup"><span data-stu-id="cdfcc-108">**Data Type**</span></span>|<span data-ttu-id="cdfcc-109">**キー/インデックス**</span><span class="sxs-lookup"><span data-stu-id="cdfcc-109">**Key/Index**</span></span>|<span data-ttu-id="cdfcc-110">**詳細**</span><span class="sxs-lookup"><span data-stu-id="cdfcc-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="cdfcc-111">**DeviceId**</span><span class="sxs-lookup"><span data-stu-id="cdfcc-111">**DeviceId**</span></span> <br/> |<span data-ttu-id="cdfcc-112">int</span><span class="sxs-lookup"><span data-stu-id="cdfcc-112">int</span></span>  <br/> |<span data-ttu-id="cdfcc-113">Primary</span><span class="sxs-lookup"><span data-stu-id="cdfcc-113">Primary</span></span>  <br/> |<span data-ttu-id="cdfcc-114">このハードウェアバージョンを識別する一意の番号。</span><span class="sxs-lookup"><span data-stu-id="cdfcc-114">Unique number identifying this hardware version.</span></span>  <br/> |
|<span data-ttu-id="cdfcc-115">**Manufacturerid]**</span><span class="sxs-lookup"><span data-stu-id="cdfcc-115">**ManufacturerId**</span></span> <br/> |<span data-ttu-id="cdfcc-116">int</span><span class="sxs-lookup"><span data-stu-id="cdfcc-116">int</span></span>  <br/> |<span data-ttu-id="cdfcc-117">外部</span><span class="sxs-lookup"><span data-stu-id="cdfcc-117">Foreign</span></span>  <br/> |<span data-ttu-id="cdfcc-118">このデバイスの製造元。</span><span class="sxs-lookup"><span data-stu-id="cdfcc-118">Manufacturer of this device.</span></span> <span data-ttu-id="cdfcc-119">詳細については、「 [Skype For Business Server 2015 の製造元の表](manufacturers.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="cdfcc-119">See the [Manufacturers table in Skype for Business Server 2015](manufacturers.md) for more information.</span></span> <br/> |
|<span data-ttu-id="cdfcc-120">**ハードウェアの Versionid**</span><span class="sxs-lookup"><span data-stu-id="cdfcc-120">**HardwareVersionId**</span></span> <br/> |<span data-ttu-id="cdfcc-121">int</span><span class="sxs-lookup"><span data-stu-id="cdfcc-121">int</span></span>  <br/> |<span data-ttu-id="cdfcc-122">外部</span><span class="sxs-lookup"><span data-stu-id="cdfcc-122">Foreign</span></span>  <br/> |<span data-ttu-id="cdfcc-123">このデバイスのハードウェアバージョン。</span><span class="sxs-lookup"><span data-stu-id="cdfcc-123">Hardware version of this device.</span></span> <span data-ttu-id="cdfcc-124">詳細については、「 [Skype For Business Server 2015 のハードウェアバージョン](hardwareversions.md)」の表を参照してください。</span><span class="sxs-lookup"><span data-stu-id="cdfcc-124">See the [HardwareVersions table in Skype for Business Server 2015](hardwareversions.md) for more information.</span></span> <br/> |
|<span data-ttu-id="cdfcc-125">**MacAddress**</span><span class="sxs-lookup"><span data-stu-id="cdfcc-125">**MacAddress**</span></span> <br/> |<span data-ttu-id="cdfcc-126">bigint</span><span class="sxs-lookup"><span data-stu-id="cdfcc-126">bigint</span></span>  <br/> ||<span data-ttu-id="cdfcc-127">MAC アドレス</span><span class="sxs-lookup"><span data-stu-id="cdfcc-127">MAC Address</span></span>  <br/> |
   

