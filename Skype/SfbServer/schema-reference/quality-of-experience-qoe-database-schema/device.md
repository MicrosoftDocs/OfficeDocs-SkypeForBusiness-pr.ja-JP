---
title: Device テーブル
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
ms.openlocfilehash: 346ea171b9a0c1b7a874b65a68b582c4167c57fe
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/28/2018
---
# <a name="device-table"></a><span data-ttu-id="ae47e-104">Device テーブル</span><span class="sxs-lookup"><span data-stu-id="ae47e-104">Device table</span></span>
 
<span data-ttu-id="ae47e-105">デバイス テーブルがさまざまなキャプチャの情報を格納するサポート テーブルまたはデバイスを表示します。</span><span class="sxs-lookup"><span data-stu-id="ae47e-105">The Device table is a supporting table that stores information about the various capture or render devices.</span></span> <span data-ttu-id="ae47e-106">テーブル内の各レコードは、1 つのデバイスを表します。</span><span class="sxs-lookup"><span data-stu-id="ae47e-106">Each record in the table represents one device.</span></span>
  
|<span data-ttu-id="ae47e-107">**列**</span><span class="sxs-lookup"><span data-stu-id="ae47e-107">**Column**</span></span>|<span data-ttu-id="ae47e-108">**データ型**</span><span class="sxs-lookup"><span data-stu-id="ae47e-108">**Data Type**</span></span>|<span data-ttu-id="ae47e-109">**キーまたはインデックス**</span><span class="sxs-lookup"><span data-stu-id="ae47e-109">**Key/Index**</span></span>|<span data-ttu-id="ae47e-110">**詳細**</span><span class="sxs-lookup"><span data-stu-id="ae47e-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="ae47e-111">**DeviceKey**</span><span class="sxs-lookup"><span data-stu-id="ae47e-111">**DeviceKey**</span></span> <br/> |<span data-ttu-id="ae47e-112">int</span><span class="sxs-lookup"><span data-stu-id="ae47e-112">int</span></span>  <br/> |<span data-ttu-id="ae47e-113">Primary</span><span class="sxs-lookup"><span data-stu-id="ae47e-113">Primary</span></span>  <br/> |<span data-ttu-id="ae47e-114">このデバイスを識別する一意の番号です。</span><span class="sxs-lookup"><span data-stu-id="ae47e-114">Unique number identifying this device.</span></span>  <br/> |
|<span data-ttu-id="ae47e-115">**デバイス名**</span><span class="sxs-lookup"><span data-stu-id="ae47e-115">**DeviceName**</span></span> <br/> |<span data-ttu-id="ae47e-116">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="ae47e-116">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="ae47e-117">デバイス名 + DeviceType が一意では</span><span class="sxs-lookup"><span data-stu-id="ae47e-117">DeviceName + DeviceType is unique</span></span>  <br/> |<span data-ttu-id="ae47e-118">デバイスの名前です。</span><span class="sxs-lookup"><span data-stu-id="ae47e-118">Device name.</span></span>  <br/> |
|<span data-ttu-id="ae47e-119">**DeviceType**</span><span class="sxs-lookup"><span data-stu-id="ae47e-119">**DeviceType**</span></span> <br/> |<span data-ttu-id="ae47e-120">bit</span><span class="sxs-lookup"><span data-stu-id="ae47e-120">bit</span></span>  <br/> |<span data-ttu-id="ae47e-121">デバイス名 + DeviceType が一意では</span><span class="sxs-lookup"><span data-stu-id="ae47e-121">DeviceName + DeviceType is unique</span></span>  <br/> |<span data-ttu-id="ae47e-122">デバイスの種類。</span><span class="sxs-lookup"><span data-stu-id="ae47e-122">Device type.</span></span> <span data-ttu-id="ae47e-123">キャプチャ デバイスは、1、0 は、レンダリング デバイスです。</span><span class="sxs-lookup"><span data-stu-id="ae47e-123">1 is a capture device, 0 is a render device.</span></span>  <br/> |
   

