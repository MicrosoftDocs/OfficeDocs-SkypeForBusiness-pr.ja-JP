---
title: Device テーブル
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: d5a4f777-bc12-4ce8-bc0d-867d5e22b436
description: Device テーブルは、さまざまなキャプチャデバイスやレンダリングデバイスに関する情報を格納するサポートテーブルです。 テーブル内の各レコードは、1つのデバイスを表します。
ms.openlocfilehash: 93e6b2215fa1e20b930d678c45f10e26feffd351
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2020
ms.locfileid: "41810155"
---
# <a name="device-table"></a><span data-ttu-id="c4f29-104">Device テーブル</span><span class="sxs-lookup"><span data-stu-id="c4f29-104">Device table</span></span>
 
<span data-ttu-id="c4f29-105">Device テーブルは、さまざまなキャプチャデバイスやレンダリングデバイスに関する情報を格納するサポートテーブルです。</span><span class="sxs-lookup"><span data-stu-id="c4f29-105">The Device table is a supporting table that stores information about the various capture or render devices.</span></span> <span data-ttu-id="c4f29-106">テーブル内の各レコードは、1つのデバイスを表します。</span><span class="sxs-lookup"><span data-stu-id="c4f29-106">Each record in the table represents one device.</span></span>
  
|<span data-ttu-id="c4f29-107">**列**</span><span class="sxs-lookup"><span data-stu-id="c4f29-107">**Column**</span></span>|<span data-ttu-id="c4f29-108">**データ型**</span><span class="sxs-lookup"><span data-stu-id="c4f29-108">**Data Type**</span></span>|<span data-ttu-id="c4f29-109">**キー/インデックス**</span><span class="sxs-lookup"><span data-stu-id="c4f29-109">**Key/Index**</span></span>|<span data-ttu-id="c4f29-110">**詳細**</span><span class="sxs-lookup"><span data-stu-id="c4f29-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="c4f29-111">**DeviceKey**</span><span class="sxs-lookup"><span data-stu-id="c4f29-111">**DeviceKey**</span></span> <br/> |<span data-ttu-id="c4f29-112">int</span><span class="sxs-lookup"><span data-stu-id="c4f29-112">int</span></span>  <br/> |<span data-ttu-id="c4f29-113">Primary</span><span class="sxs-lookup"><span data-stu-id="c4f29-113">Primary</span></span>  <br/> |<span data-ttu-id="c4f29-114">このデバイスを識別する一意の番号。</span><span class="sxs-lookup"><span data-stu-id="c4f29-114">Unique number identifying this device.</span></span>  <br/> |
|<span data-ttu-id="c4f29-115">**DeviceName**</span><span class="sxs-lookup"><span data-stu-id="c4f29-115">**DeviceName**</span></span> <br/> |<span data-ttu-id="c4f29-116">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="c4f29-116">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="c4f29-117">DeviceName + DeviceType の固有のキー</span><span class="sxs-lookup"><span data-stu-id="c4f29-117">DeviceName + DeviceType is unique</span></span>  <br/> |<span data-ttu-id="c4f29-118">デバイス名。</span><span class="sxs-lookup"><span data-stu-id="c4f29-118">Device name.</span></span>  <br/> |
|<span data-ttu-id="c4f29-119">**DeviceType**</span><span class="sxs-lookup"><span data-stu-id="c4f29-119">**DeviceType**</span></span> <br/> |<span data-ttu-id="c4f29-120">bit</span><span class="sxs-lookup"><span data-stu-id="c4f29-120">bit</span></span>  <br/> |<span data-ttu-id="c4f29-121">DeviceName + DeviceType の固有のキー</span><span class="sxs-lookup"><span data-stu-id="c4f29-121">DeviceName + DeviceType is unique</span></span>  <br/> |<span data-ttu-id="c4f29-122">デバイスの種類。</span><span class="sxs-lookup"><span data-stu-id="c4f29-122">Device type.</span></span> <span data-ttu-id="c4f29-123">1はキャプチャデバイス、0はレンダーデバイスです。</span><span class="sxs-lookup"><span data-stu-id="c4f29-123">1 is a capture device, 0 is a render device.</span></span>  <br/> |
   

