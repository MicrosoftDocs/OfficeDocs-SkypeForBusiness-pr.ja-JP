---
title: MonitoredRegionLink テーブル
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
ms.assetid: cebda194-7be3-42d6-b6f0-c86f8b0f200a
description: MonitoredRegionLink テーブルは、サポート テーブルです。 各レコードは、2 つの国/地域の間の 1 つのリンクを表します。
ms.openlocfilehash: f30ba249f89a2247e0e03c71fc97f05e69c59bcd
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49806347"
---
# <a name="monitoredregionlink-table"></a><span data-ttu-id="cc941-104">MonitoredRegionLink テーブル</span><span class="sxs-lookup"><span data-stu-id="cc941-104">MonitoredRegionLink table</span></span>
 
<span data-ttu-id="cc941-p102">MonitoredRegionLink テーブルは、サポート テーブルです。各レコードは、2 つの国/地域の間の 1 つのリンクを表します。</span><span class="sxs-lookup"><span data-stu-id="cc941-p102">The MonitoredRegionLink table is a supporting table. Each record represents one link between two countries/regions.</span></span>
  
|<span data-ttu-id="cc941-107">**列**</span><span class="sxs-lookup"><span data-stu-id="cc941-107">**Column**</span></span>|<span data-ttu-id="cc941-108">**データ型**</span><span class="sxs-lookup"><span data-stu-id="cc941-108">**Data Type**</span></span>|<span data-ttu-id="cc941-109">**キー/インデックス**</span><span class="sxs-lookup"><span data-stu-id="cc941-109">**Key/Index**</span></span>|<span data-ttu-id="cc941-110">**詳細**</span><span class="sxs-lookup"><span data-stu-id="cc941-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="cc941-111">**Region1Key**</span><span class="sxs-lookup"><span data-stu-id="cc941-111">**Region1Key**</span></span> <br/> |<span data-ttu-id="cc941-112">int</span><span class="sxs-lookup"><span data-stu-id="cc941-112">int</span></span>  <br/> |<span data-ttu-id="cc941-113">主/プライマリ、外部</span><span class="sxs-lookup"><span data-stu-id="cc941-113">Primary, Foreign</span></span>  <br/> |<span data-ttu-id="cc941-114">Region テーブル [から参照されます](region.md)。</span><span class="sxs-lookup"><span data-stu-id="cc941-114">Referenced from the [Region table](region.md).</span></span>  <br/> |
|<span data-ttu-id="cc941-115">**Region2Key**</span><span class="sxs-lookup"><span data-stu-id="cc941-115">**Region2Key**</span></span> <br/> |<span data-ttu-id="cc941-116">int</span><span class="sxs-lookup"><span data-stu-id="cc941-116">int</span></span>  <br/> |<span data-ttu-id="cc941-117">主/プライマリ、外部</span><span class="sxs-lookup"><span data-stu-id="cc941-117">Primary, Foreign</span></span>  <br/> |<span data-ttu-id="cc941-118">Region テーブル [から参照されます](region.md)。</span><span class="sxs-lookup"><span data-stu-id="cc941-118">Referenced from the [Region table](region.md).</span></span>  <br/> |
   

