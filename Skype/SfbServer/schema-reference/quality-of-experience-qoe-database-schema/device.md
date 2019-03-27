---
title: Device テーブル
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: d5a4f777-bc12-4ce8-bc0d-867d5e22b436
description: デバイス テーブルがさまざまなキャプチャの情報を格納するサポート テーブルまたはデバイスを表示します。 テーブル内の各レコードは、1 つのデバイスを表します。
ms.openlocfilehash: 09af6ee11ebc821d123e847fbad812479d9d7bb0
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/27/2019
ms.locfileid: "30885513"
---
# <a name="device-table"></a><span data-ttu-id="22f45-104">Device テーブル</span><span class="sxs-lookup"><span data-stu-id="22f45-104">Device table</span></span>
 
<span data-ttu-id="22f45-105">デバイス テーブルがさまざまなキャプチャの情報を格納するサポート テーブルまたはデバイスを表示します。</span><span class="sxs-lookup"><span data-stu-id="22f45-105">The Device table is a supporting table that stores information about the various capture or render devices.</span></span> <span data-ttu-id="22f45-106">テーブル内の各レコードは、1 つのデバイスを表します。</span><span class="sxs-lookup"><span data-stu-id="22f45-106">Each record in the table represents one device.</span></span>
  
|<span data-ttu-id="22f45-107">**列**</span><span class="sxs-lookup"><span data-stu-id="22f45-107">**Column**</span></span>|<span data-ttu-id="22f45-108">**データ型**</span><span class="sxs-lookup"><span data-stu-id="22f45-108">**Data Type**</span></span>|<span data-ttu-id="22f45-109">**キー/インデックス**</span><span class="sxs-lookup"><span data-stu-id="22f45-109">**Key/Index**</span></span>|<span data-ttu-id="22f45-110">**詳細**</span><span class="sxs-lookup"><span data-stu-id="22f45-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="22f45-111">**DeviceKey**</span><span class="sxs-lookup"><span data-stu-id="22f45-111">**DeviceKey**</span></span> <br/> |<span data-ttu-id="22f45-112">int</span><span class="sxs-lookup"><span data-stu-id="22f45-112">int</span></span>  <br/> |<span data-ttu-id="22f45-113">Primary</span><span class="sxs-lookup"><span data-stu-id="22f45-113">Primary</span></span>  <br/> |<span data-ttu-id="22f45-114">このデバイスを識別する一意の番号です。</span><span class="sxs-lookup"><span data-stu-id="22f45-114">Unique number identifying this device.</span></span>  <br/> |
|<span data-ttu-id="22f45-115">**デバイス名**</span><span class="sxs-lookup"><span data-stu-id="22f45-115">**DeviceName**</span></span> <br/> |<span data-ttu-id="22f45-116">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="22f45-116">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="22f45-117">デバイス名 + DeviceType が一意では</span><span class="sxs-lookup"><span data-stu-id="22f45-117">DeviceName + DeviceType is unique</span></span>  <br/> |<span data-ttu-id="22f45-118">デバイスの名前です。</span><span class="sxs-lookup"><span data-stu-id="22f45-118">Device name.</span></span>  <br/> |
|<span data-ttu-id="22f45-119">**DeviceType**</span><span class="sxs-lookup"><span data-stu-id="22f45-119">**DeviceType**</span></span> <br/> |<span data-ttu-id="22f45-120">bit</span><span class="sxs-lookup"><span data-stu-id="22f45-120">bit</span></span>  <br/> |<span data-ttu-id="22f45-121">デバイス名 + DeviceType が一意では</span><span class="sxs-lookup"><span data-stu-id="22f45-121">DeviceName + DeviceType is unique</span></span>  <br/> |<span data-ttu-id="22f45-122">デバイスの種類。</span><span class="sxs-lookup"><span data-stu-id="22f45-122">Device type.</span></span> <span data-ttu-id="22f45-123">キャプチャ デバイスは、1、0 は、レンダリング デバイスです。</span><span class="sxs-lookup"><span data-stu-id="22f45-123">1 is a capture device, 0 is a render device.</span></span>  <br/> |
   

