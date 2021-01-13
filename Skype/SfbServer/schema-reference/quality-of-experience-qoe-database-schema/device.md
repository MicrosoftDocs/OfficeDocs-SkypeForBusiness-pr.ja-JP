---
title: Device テーブル
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
ms.assetid: d5a4f777-bc12-4ce8-bc0d-867d5e22b436
description: Device テーブルは、さまざまなキャプチャデバイスまたはレンダー デバイスに関する情報を格納するサポート テーブルです。 テーブル内の各レコードは、1 つのデバイスを表します。
ms.openlocfilehash: 818458e41c71398f3df11ac9a47eeee0841c6dca
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49814747"
---
# <a name="device-table"></a><span data-ttu-id="14496-104">Device テーブル</span><span class="sxs-lookup"><span data-stu-id="14496-104">Device table</span></span>
 
<span data-ttu-id="14496-105">Device テーブルは、さまざまなキャプチャデバイスまたはレンダー デバイスに関する情報を格納するサポート テーブルです。</span><span class="sxs-lookup"><span data-stu-id="14496-105">The Device table is a supporting table that stores information about the various capture or render devices.</span></span> <span data-ttu-id="14496-106">テーブル内の各レコードは、1 つのデバイスを表します。</span><span class="sxs-lookup"><span data-stu-id="14496-106">Each record in the table represents one device.</span></span>
  
|<span data-ttu-id="14496-107">**列**</span><span class="sxs-lookup"><span data-stu-id="14496-107">**Column**</span></span>|<span data-ttu-id="14496-108">**データ型**</span><span class="sxs-lookup"><span data-stu-id="14496-108">**Data Type**</span></span>|<span data-ttu-id="14496-109">**キー/インデックス**</span><span class="sxs-lookup"><span data-stu-id="14496-109">**Key/Index**</span></span>|<span data-ttu-id="14496-110">**詳細**</span><span class="sxs-lookup"><span data-stu-id="14496-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="14496-111">**DeviceKey**</span><span class="sxs-lookup"><span data-stu-id="14496-111">**DeviceKey**</span></span> <br/> |<span data-ttu-id="14496-112">int</span><span class="sxs-lookup"><span data-stu-id="14496-112">int</span></span>  <br/> |<span data-ttu-id="14496-113">Primary</span><span class="sxs-lookup"><span data-stu-id="14496-113">Primary</span></span>  <br/> |<span data-ttu-id="14496-114">このデバイスを識別する一意の番号。</span><span class="sxs-lookup"><span data-stu-id="14496-114">Unique number identifying this device.</span></span>  <br/> |
|<span data-ttu-id="14496-115">**DeviceName**</span><span class="sxs-lookup"><span data-stu-id="14496-115">**DeviceName**</span></span> <br/> |<span data-ttu-id="14496-116">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="14496-116">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="14496-117">DeviceName + DeviceType が一意である</span><span class="sxs-lookup"><span data-stu-id="14496-117">DeviceName + DeviceType is unique</span></span>  <br/> |<span data-ttu-id="14496-118">デバイス名。</span><span class="sxs-lookup"><span data-stu-id="14496-118">Device name.</span></span>  <br/> |
|<span data-ttu-id="14496-119">**DeviceType**</span><span class="sxs-lookup"><span data-stu-id="14496-119">**DeviceType**</span></span> <br/> |<span data-ttu-id="14496-120">bit</span><span class="sxs-lookup"><span data-stu-id="14496-120">bit</span></span>  <br/> |<span data-ttu-id="14496-121">DeviceName + DeviceType が一意である</span><span class="sxs-lookup"><span data-stu-id="14496-121">DeviceName + DeviceType is unique</span></span>  <br/> |<span data-ttu-id="14496-122">デバイスの種類。</span><span class="sxs-lookup"><span data-stu-id="14496-122">Device type.</span></span> <span data-ttu-id="14496-123">1 はキャプチャ デバイス、0 はレンダー デバイスです。</span><span class="sxs-lookup"><span data-stu-id="14496-123">1 is a capture device, 0 is a render device.</span></span>  <br/> |
   

