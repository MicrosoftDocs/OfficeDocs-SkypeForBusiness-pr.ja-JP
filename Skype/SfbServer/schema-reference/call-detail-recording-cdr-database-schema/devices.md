---
title: Skype for Business Server 2015 の Devices テーブル
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 532e2280-4bbc-4a6c-93da-45d9f80a30a0
description: Devices テーブルは、サポート テーブルです。 各レコードには、1 つのデバイス (卓上電話) に関する情報が格納されます。
ms.openlocfilehash: da0d6ea8143fb8c81225e885fba1f05a90e2fda5
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49831817"
---
# <a name="devices-table-in-skype-for-business-server-2015"></a><span data-ttu-id="4aa83-104">Skype for Business Server 2015 の Devices テーブル</span><span class="sxs-lookup"><span data-stu-id="4aa83-104">Devices table in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="4aa83-105">Devices テーブルは、サポート テーブルです。</span><span class="sxs-lookup"><span data-stu-id="4aa83-105">The Devices table is a supporting table.</span></span> <span data-ttu-id="4aa83-106">各レコードには、1 つのデバイス (卓上電話) に関する情報が格納されます。</span><span class="sxs-lookup"><span data-stu-id="4aa83-106">Each record stores information about one device (desk phone).</span></span>
  
|<span data-ttu-id="4aa83-107">**列**</span><span class="sxs-lookup"><span data-stu-id="4aa83-107">**Column**</span></span>|<span data-ttu-id="4aa83-108">**データ型**</span><span class="sxs-lookup"><span data-stu-id="4aa83-108">**Data Type**</span></span>|<span data-ttu-id="4aa83-109">**キー/インデックス**</span><span class="sxs-lookup"><span data-stu-id="4aa83-109">**Key/Index**</span></span>|<span data-ttu-id="4aa83-110">**詳細**</span><span class="sxs-lookup"><span data-stu-id="4aa83-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="4aa83-111">**DeviceId**</span><span class="sxs-lookup"><span data-stu-id="4aa83-111">**DeviceId**</span></span> <br/> |<span data-ttu-id="4aa83-112">int</span><span class="sxs-lookup"><span data-stu-id="4aa83-112">int</span></span>  <br/> |<span data-ttu-id="4aa83-113">Primary</span><span class="sxs-lookup"><span data-stu-id="4aa83-113">Primary</span></span>  <br/> |<span data-ttu-id="4aa83-114">このハードウェア バージョンを識別する一意の番号。</span><span class="sxs-lookup"><span data-stu-id="4aa83-114">Unique number identifying this hardware version.</span></span>  <br/> |
|<span data-ttu-id="4aa83-115">**ManufacturerId**</span><span class="sxs-lookup"><span data-stu-id="4aa83-115">**ManufacturerId**</span></span> <br/> |<span data-ttu-id="4aa83-116">int</span><span class="sxs-lookup"><span data-stu-id="4aa83-116">int</span></span>  <br/> |<span data-ttu-id="4aa83-117">外部</span><span class="sxs-lookup"><span data-stu-id="4aa83-117">Foreign</span></span>  <br/> |<span data-ttu-id="4aa83-118">このデバイスの製造元。</span><span class="sxs-lookup"><span data-stu-id="4aa83-118">Manufacturer of this device.</span></span> <span data-ttu-id="4aa83-119">詳細については [、Skype for Business Server 2015 の Manufacturers の表](manufacturers.md) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4aa83-119">See the [Manufacturers table in Skype for Business Server 2015](manufacturers.md) for more information.</span></span> <br/> |
|<span data-ttu-id="4aa83-120">**HardwareVersionId**</span><span class="sxs-lookup"><span data-stu-id="4aa83-120">**HardwareVersionId**</span></span> <br/> |<span data-ttu-id="4aa83-121">int</span><span class="sxs-lookup"><span data-stu-id="4aa83-121">int</span></span>  <br/> |<span data-ttu-id="4aa83-122">外部</span><span class="sxs-lookup"><span data-stu-id="4aa83-122">Foreign</span></span>  <br/> |<span data-ttu-id="4aa83-123">このデバイスのハードウェア バージョン。</span><span class="sxs-lookup"><span data-stu-id="4aa83-123">Hardware version of this device.</span></span> <span data-ttu-id="4aa83-124">詳細については [、Skype for Business Server 2015 の HardwareVersions の表](hardwareversions.md) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4aa83-124">See the [HardwareVersions table in Skype for Business Server 2015](hardwareversions.md) for more information.</span></span> <br/> |
|<span data-ttu-id="4aa83-125">**MacAddress**</span><span class="sxs-lookup"><span data-stu-id="4aa83-125">**MacAddress**</span></span> <br/> |<span data-ttu-id="4aa83-126">bigint</span><span class="sxs-lookup"><span data-stu-id="4aa83-126">bigint</span></span>  <br/> ||<span data-ttu-id="4aa83-127">MAC アドレス</span><span class="sxs-lookup"><span data-stu-id="4aa83-127">MAC Address</span></span>  <br/> |
   

