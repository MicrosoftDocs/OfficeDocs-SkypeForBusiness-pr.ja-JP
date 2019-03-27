---
title: MonitoredRegionLink テーブル
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: cebda194-7be3-42d6-b6f0-c86f8b0f200a
description: MonitoredRegionLink はテーブルをサポートします。 各レコードは、2 つの国/地域の間の 1 つのリンクを表します。
ms.openlocfilehash: 0df5cd8abe957ed952bdf656a67e1d423cc57f33
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/27/2019
ms.locfileid: "30884415"
---
# <a name="monitoredregionlink-table"></a><span data-ttu-id="95ee4-104">MonitoredRegionLink テーブル</span><span class="sxs-lookup"><span data-stu-id="95ee4-104">MonitoredRegionLink table</span></span>
 
<span data-ttu-id="95ee4-105">MonitoredRegionLink はテーブルをサポートします。</span><span class="sxs-lookup"><span data-stu-id="95ee4-105">The MonitoredRegionLink table is a supporting table.</span></span> <span data-ttu-id="95ee4-106">各レコードは、2 つの国/地域の間の 1 つのリンクを表します。</span><span class="sxs-lookup"><span data-stu-id="95ee4-106">Each record represents one link between two countries/regions.</span></span>
  
|<span data-ttu-id="95ee4-107">**列**</span><span class="sxs-lookup"><span data-stu-id="95ee4-107">**Column**</span></span>|<span data-ttu-id="95ee4-108">**データ型**</span><span class="sxs-lookup"><span data-stu-id="95ee4-108">**Data Type**</span></span>|<span data-ttu-id="95ee4-109">**キー/インデックス**</span><span class="sxs-lookup"><span data-stu-id="95ee4-109">**Key/Index**</span></span>|<span data-ttu-id="95ee4-110">**詳細**</span><span class="sxs-lookup"><span data-stu-id="95ee4-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="95ee4-111">**Region1Key**</span><span class="sxs-lookup"><span data-stu-id="95ee4-111">**Region1Key**</span></span> <br/> |<span data-ttu-id="95ee4-112">int</span><span class="sxs-lookup"><span data-stu-id="95ee4-112">int</span></span>  <br/> |<span data-ttu-id="95ee4-113">プライマリ サーバーで、外部</span><span class="sxs-lookup"><span data-stu-id="95ee4-113">Primary, Foreign</span></span>  <br/> |<span data-ttu-id="95ee4-114">[地域テーブル](region.md)から参照されています。</span><span class="sxs-lookup"><span data-stu-id="95ee4-114">Referenced from the [Region table](region.md).</span></span>  <br/> |
|<span data-ttu-id="95ee4-115">**Region2Key**</span><span class="sxs-lookup"><span data-stu-id="95ee4-115">**Region2Key**</span></span> <br/> |<span data-ttu-id="95ee4-116">int</span><span class="sxs-lookup"><span data-stu-id="95ee4-116">int</span></span>  <br/> |<span data-ttu-id="95ee4-117">プライマリ サーバーで、外部</span><span class="sxs-lookup"><span data-stu-id="95ee4-117">Primary, Foreign</span></span>  <br/> |<span data-ttu-id="95ee4-118">[地域テーブル](region.md)から参照されています。</span><span class="sxs-lookup"><span data-stu-id="95ee4-118">Referenced from the [Region table](region.md).</span></span>  <br/> |
   

