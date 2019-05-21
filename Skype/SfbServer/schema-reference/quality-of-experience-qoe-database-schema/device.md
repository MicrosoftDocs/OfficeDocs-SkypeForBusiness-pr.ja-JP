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
localization_priority: Normal
ms.assetid: d5a4f777-bc12-4ce8-bc0d-867d5e22b436
description: Device テーブルは、さまざまなキャプチャデバイスやレンダリングデバイスに関する情報を格納するサポートテーブルです。 テーブル内の各レコードは、1つのデバイスを表します。
ms.openlocfilehash: a73deac9bec6ce4515eaffc256179b10d1f27106
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2019
ms.locfileid: "34295007"
---
# <a name="device-table"></a><span data-ttu-id="10b6f-104">Device テーブル</span><span class="sxs-lookup"><span data-stu-id="10b6f-104">Device table</span></span>
 
<span data-ttu-id="10b6f-105">Device テーブルは、さまざまなキャプチャデバイスやレンダリングデバイスに関する情報を格納するサポートテーブルです。</span><span class="sxs-lookup"><span data-stu-id="10b6f-105">The Device table is a supporting table that stores information about the various capture or render devices.</span></span> <span data-ttu-id="10b6f-106">テーブル内の各レコードは、1つのデバイスを表します。</span><span class="sxs-lookup"><span data-stu-id="10b6f-106">Each record in the table represents one device.</span></span>
  
|<span data-ttu-id="10b6f-107">**列**</span><span class="sxs-lookup"><span data-stu-id="10b6f-107">**Column**</span></span>|<span data-ttu-id="10b6f-108">**データ型**</span><span class="sxs-lookup"><span data-stu-id="10b6f-108">**Data Type**</span></span>|<span data-ttu-id="10b6f-109">**キー/インデックス**</span><span class="sxs-lookup"><span data-stu-id="10b6f-109">**Key/Index**</span></span>|<span data-ttu-id="10b6f-110">**詳細**</span><span class="sxs-lookup"><span data-stu-id="10b6f-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="10b6f-111">**DeviceKey**</span><span class="sxs-lookup"><span data-stu-id="10b6f-111">**DeviceKey**</span></span> <br/> |<span data-ttu-id="10b6f-112">int</span><span class="sxs-lookup"><span data-stu-id="10b6f-112">int</span></span>  <br/> |<span data-ttu-id="10b6f-113">Primary</span><span class="sxs-lookup"><span data-stu-id="10b6f-113">Primary</span></span>  <br/> |<span data-ttu-id="10b6f-114">このデバイスを識別する一意の番号。</span><span class="sxs-lookup"><span data-stu-id="10b6f-114">Unique number identifying this device.</span></span>  <br/> |
|<span data-ttu-id="10b6f-115">**DeviceName**</span><span class="sxs-lookup"><span data-stu-id="10b6f-115">**DeviceName**</span></span> <br/> |<span data-ttu-id="10b6f-116">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="10b6f-116">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="10b6f-117">DeviceName + DeviceType の固有のキー</span><span class="sxs-lookup"><span data-stu-id="10b6f-117">DeviceName + DeviceType is unique</span></span>  <br/> |<span data-ttu-id="10b6f-118">デバイス名。</span><span class="sxs-lookup"><span data-stu-id="10b6f-118">Device name.</span></span>  <br/> |
|<span data-ttu-id="10b6f-119">**DeviceType**</span><span class="sxs-lookup"><span data-stu-id="10b6f-119">**DeviceType**</span></span> <br/> |<span data-ttu-id="10b6f-120">bit</span><span class="sxs-lookup"><span data-stu-id="10b6f-120">bit</span></span>  <br/> |<span data-ttu-id="10b6f-121">DeviceName + DeviceType の固有のキー</span><span class="sxs-lookup"><span data-stu-id="10b6f-121">DeviceName + DeviceType is unique</span></span>  <br/> |<span data-ttu-id="10b6f-122">デバイスの種類。</span><span class="sxs-lookup"><span data-stu-id="10b6f-122">Device type.</span></span> <span data-ttu-id="10b6f-123">1はキャプチャデバイス、0はレンダーデバイスです。</span><span class="sxs-lookup"><span data-stu-id="10b6f-123">1 is a capture device, 0 is a render device.</span></span>  <br/> |
   

