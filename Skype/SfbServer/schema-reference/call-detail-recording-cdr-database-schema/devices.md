---
title: ビジネス サーバー 2015 の Skype でデバイス ・ テーブル
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 532e2280-4bbc-4a6c-93da-45d9f80a30a0
description: デバイス ・ テーブルは、関連テーブルです。 各レコードは、1 つのデバイス (机上電話) に関する情報を格納します。
ms.openlocfilehash: f770f19fb94bf25bdb4c13e74dc41e05f6674788
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/27/2019
ms.locfileid: "30881703"
---
# <a name="devices-table-in-skype-for-business-server-2015"></a><span data-ttu-id="e030d-104">ビジネス サーバー 2015 の Skype でデバイス ・ テーブル</span><span class="sxs-lookup"><span data-stu-id="e030d-104">Devices table in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="e030d-105">デバイス ・ テーブルは、関連テーブルです。</span><span class="sxs-lookup"><span data-stu-id="e030d-105">The Devices table is a supporting table.</span></span> <span data-ttu-id="e030d-106">各レコードは、1 つのデバイス (机上電話) に関する情報を格納します。</span><span class="sxs-lookup"><span data-stu-id="e030d-106">Each record stores information about one device (desk phone).</span></span>
  
|<span data-ttu-id="e030d-107">**列**</span><span class="sxs-lookup"><span data-stu-id="e030d-107">**Column**</span></span>|<span data-ttu-id="e030d-108">**データ型**</span><span class="sxs-lookup"><span data-stu-id="e030d-108">**Data Type**</span></span>|<span data-ttu-id="e030d-109">**キー/インデックス**</span><span class="sxs-lookup"><span data-stu-id="e030d-109">**Key/Index**</span></span>|<span data-ttu-id="e030d-110">**詳細**</span><span class="sxs-lookup"><span data-stu-id="e030d-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="e030d-111">**DeviceId**</span><span class="sxs-lookup"><span data-stu-id="e030d-111">**DeviceId**</span></span> <br/> |<span data-ttu-id="e030d-112">int</span><span class="sxs-lookup"><span data-stu-id="e030d-112">int</span></span>  <br/> |<span data-ttu-id="e030d-113">Primary</span><span class="sxs-lookup"><span data-stu-id="e030d-113">Primary</span></span>  <br/> |<span data-ttu-id="e030d-114">このハードウェアのバージョンを識別する一意の番号です。</span><span class="sxs-lookup"><span data-stu-id="e030d-114">Unique number identifying this hardware version.</span></span>  <br/> |
|<span data-ttu-id="e030d-115">**ManufacturerId**</span><span class="sxs-lookup"><span data-stu-id="e030d-115">**ManufacturerId**</span></span> <br/> |<span data-ttu-id="e030d-116">int</span><span class="sxs-lookup"><span data-stu-id="e030d-116">int</span></span>  <br/> |<span data-ttu-id="e030d-117">外部</span><span class="sxs-lookup"><span data-stu-id="e030d-117">Foreign</span></span>  <br/> |<span data-ttu-id="e030d-118">このデバイスの製造元です。</span><span class="sxs-lookup"><span data-stu-id="e030d-118">Manufacturer of this device.</span></span> <span data-ttu-id="e030d-119">詳細については、 [Skype のビジネス サーバー 2015 の製造元テーブル](manufacturers.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e030d-119">See the [Manufacturers table in Skype for Business Server 2015](manufacturers.md) for more information.</span></span> <br/> |
|<span data-ttu-id="e030d-120">**HardwareVersionId**</span><span class="sxs-lookup"><span data-stu-id="e030d-120">**HardwareVersionId**</span></span> <br/> |<span data-ttu-id="e030d-121">int</span><span class="sxs-lookup"><span data-stu-id="e030d-121">int</span></span>  <br/> |<span data-ttu-id="e030d-122">外部</span><span class="sxs-lookup"><span data-stu-id="e030d-122">Foreign</span></span>  <br/> |<span data-ttu-id="e030d-123">このデバイスのハードウェア バージョンです。</span><span class="sxs-lookup"><span data-stu-id="e030d-123">Hardware version of this device.</span></span> <span data-ttu-id="e030d-124">詳細については、 [Skype のビジネス サーバー 2015 で HardwareVersions テーブル](hardwareversions.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e030d-124">See the [HardwareVersions table in Skype for Business Server 2015](hardwareversions.md) for more information.</span></span> <br/> |
|<span data-ttu-id="e030d-125">**MacAddress**</span><span class="sxs-lookup"><span data-stu-id="e030d-125">**MacAddress**</span></span> <br/> |<span data-ttu-id="e030d-126">bigint 型の値</span><span class="sxs-lookup"><span data-stu-id="e030d-126">bigint</span></span>  <br/> ||<span data-ttu-id="e030d-127">MAC アドレス</span><span class="sxs-lookup"><span data-stu-id="e030d-127">MAC Address</span></span>  <br/> |
   

