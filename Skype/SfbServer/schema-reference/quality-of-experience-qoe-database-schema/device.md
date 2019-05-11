---
title: Device テーブル
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: d5a4f777-bc12-4ce8-bc0d-867d5e22b436
description: デバイス テーブルがさまざまなキャプチャの情報を格納するサポート テーブルまたはデバイスを表示します。 テーブル内の各レコードは、1 つのデバイスを表します。
ms.openlocfilehash: 0b3c27708cd8e9d1b02914e6f2cba414e353609c
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "33920027"
---
# <a name="device-table"></a><span data-ttu-id="f33b5-104">Device テーブル</span><span class="sxs-lookup"><span data-stu-id="f33b5-104">Device table</span></span>
 
<span data-ttu-id="f33b5-105">デバイス テーブルがさまざまなキャプチャの情報を格納するサポート テーブルまたはデバイスを表示します。</span><span class="sxs-lookup"><span data-stu-id="f33b5-105">The Device table is a supporting table that stores information about the various capture or render devices.</span></span> <span data-ttu-id="f33b5-106">テーブル内の各レコードは、1 つのデバイスを表します。</span><span class="sxs-lookup"><span data-stu-id="f33b5-106">Each record in the table represents one device.</span></span>
  
|<span data-ttu-id="f33b5-107">**列**</span><span class="sxs-lookup"><span data-stu-id="f33b5-107">**Column**</span></span>|<span data-ttu-id="f33b5-108">**データ型**</span><span class="sxs-lookup"><span data-stu-id="f33b5-108">**Data Type**</span></span>|<span data-ttu-id="f33b5-109">**キー/インデックス**</span><span class="sxs-lookup"><span data-stu-id="f33b5-109">**Key/Index**</span></span>|<span data-ttu-id="f33b5-110">**詳細**</span><span class="sxs-lookup"><span data-stu-id="f33b5-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="f33b5-111">**DeviceKey**</span><span class="sxs-lookup"><span data-stu-id="f33b5-111">**DeviceKey**</span></span> <br/> |<span data-ttu-id="f33b5-112">int</span><span class="sxs-lookup"><span data-stu-id="f33b5-112">int</span></span>  <br/> |<span data-ttu-id="f33b5-113">Primary</span><span class="sxs-lookup"><span data-stu-id="f33b5-113">Primary</span></span>  <br/> |<span data-ttu-id="f33b5-114">このデバイスを識別する一意の番号です。</span><span class="sxs-lookup"><span data-stu-id="f33b5-114">Unique number identifying this device.</span></span>  <br/> |
|<span data-ttu-id="f33b5-115">**デバイス名**</span><span class="sxs-lookup"><span data-stu-id="f33b5-115">**DeviceName**</span></span> <br/> |<span data-ttu-id="f33b5-116">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="f33b5-116">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="f33b5-117">デバイス名 + DeviceType が一意では</span><span class="sxs-lookup"><span data-stu-id="f33b5-117">DeviceName + DeviceType is unique</span></span>  <br/> |<span data-ttu-id="f33b5-118">デバイスの名前です。</span><span class="sxs-lookup"><span data-stu-id="f33b5-118">Device name.</span></span>  <br/> |
|<span data-ttu-id="f33b5-119">**DeviceType**</span><span class="sxs-lookup"><span data-stu-id="f33b5-119">**DeviceType**</span></span> <br/> |<span data-ttu-id="f33b5-120">bit</span><span class="sxs-lookup"><span data-stu-id="f33b5-120">bit</span></span>  <br/> |<span data-ttu-id="f33b5-121">デバイス名 + DeviceType が一意では</span><span class="sxs-lookup"><span data-stu-id="f33b5-121">DeviceName + DeviceType is unique</span></span>  <br/> |<span data-ttu-id="f33b5-122">デバイスの種類。</span><span class="sxs-lookup"><span data-stu-id="f33b5-122">Device type.</span></span> <span data-ttu-id="f33b5-123">キャプチャ デバイスは、1、0 は、レンダリング デバイスです。</span><span class="sxs-lookup"><span data-stu-id="f33b5-123">1 is a capture device, 0 is a render device.</span></span>  <br/> |
   

