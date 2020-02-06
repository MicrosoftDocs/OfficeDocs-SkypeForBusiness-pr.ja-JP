---
title: DeviceDriver テーブル
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
ms.assetid: ca91a0b4-98c0-49f6-af9d-7d0f8ac75f1a
description: DeviceDriver テーブルはサポートされているテーブルです。 各レコードは、キャプチャデバイスまたはレンダーデバイスのいずれかで使用されるドライバーを表します。
ms.openlocfilehash: 8a502a1fc07c3541522931554064f7708b3e6187
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2020
ms.locfileid: "41809715"
---
# <a name="devicedriver-table"></a><span data-ttu-id="612b1-104">DeviceDriver テーブル</span><span class="sxs-lookup"><span data-stu-id="612b1-104">DeviceDriver table</span></span>
 
<span data-ttu-id="612b1-105">DeviceDriver テーブルはサポートされているテーブルです。</span><span class="sxs-lookup"><span data-stu-id="612b1-105">The DeviceDriver table is a supporting table.</span></span> <span data-ttu-id="612b1-106">各レコードは、キャプチャデバイスまたはレンダーデバイスのいずれかで使用されるドライバーを表します。</span><span class="sxs-lookup"><span data-stu-id="612b1-106">Each record represents a driver used by either a capture device or render device.</span></span>
  
|<span data-ttu-id="612b1-107">**列**</span><span class="sxs-lookup"><span data-stu-id="612b1-107">**Column**</span></span>|<span data-ttu-id="612b1-108">**データ型**</span><span class="sxs-lookup"><span data-stu-id="612b1-108">**Data Type**</span></span>|<span data-ttu-id="612b1-109">**キー/インデックス**</span><span class="sxs-lookup"><span data-stu-id="612b1-109">**Key/Index**</span></span>|<span data-ttu-id="612b1-110">**詳細**</span><span class="sxs-lookup"><span data-stu-id="612b1-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="612b1-111">**DeviceDriverKey**</span><span class="sxs-lookup"><span data-stu-id="612b1-111">**DeviceDriverKey**</span></span> <br/> |<span data-ttu-id="612b1-112">int</span><span class="sxs-lookup"><span data-stu-id="612b1-112">int</span></span>  <br/> |<span data-ttu-id="612b1-113">Primary</span><span class="sxs-lookup"><span data-stu-id="612b1-113">Primary</span></span>  <br/> |<span data-ttu-id="612b1-114">このデバイスドライバーレコードを識別する一意の番号です。</span><span class="sxs-lookup"><span data-stu-id="612b1-114">Unique number identifying this device driver record.</span></span>  <br/> |
|<span data-ttu-id="612b1-115">**DeviceDriver**</span><span class="sxs-lookup"><span data-stu-id="612b1-115">**DeviceDriver**</span></span> <br/> |<span data-ttu-id="612b1-116">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="612b1-116">varchar(256)</span></span>  <br/> |<span data-ttu-id="612b1-117">一意</span><span class="sxs-lookup"><span data-stu-id="612b1-117">unique</span></span>  <br/> |<span data-ttu-id="612b1-118">デバイスドライバ名。</span><span class="sxs-lookup"><span data-stu-id="612b1-118">Device driver name.</span></span>  <br/> |
   

