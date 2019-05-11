---
title: MonitoredRegionLink テーブル
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: cebda194-7be3-42d6-b6f0-c86f8b0f200a
description: MonitoredRegionLink はテーブルをサポートします。 各レコードは、2 つの国/地域の間の 1 つのリンクを表します。
ms.openlocfilehash: 125f29a25b2ee039649dd47dcc405e208d0cd254
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "33920153"
---
# <a name="monitoredregionlink-table"></a><span data-ttu-id="5d23e-104">MonitoredRegionLink テーブル</span><span class="sxs-lookup"><span data-stu-id="5d23e-104">MonitoredRegionLink table</span></span>
 
<span data-ttu-id="5d23e-105">MonitoredRegionLink はテーブルをサポートします。</span><span class="sxs-lookup"><span data-stu-id="5d23e-105">The MonitoredRegionLink table is a supporting table.</span></span> <span data-ttu-id="5d23e-106">各レコードは、2 つの国/地域の間の 1 つのリンクを表します。</span><span class="sxs-lookup"><span data-stu-id="5d23e-106">Each record represents one link between two countries/regions.</span></span>
  
|<span data-ttu-id="5d23e-107">**列**</span><span class="sxs-lookup"><span data-stu-id="5d23e-107">**Column**</span></span>|<span data-ttu-id="5d23e-108">**データ型**</span><span class="sxs-lookup"><span data-stu-id="5d23e-108">**Data Type**</span></span>|<span data-ttu-id="5d23e-109">**キー/インデックス**</span><span class="sxs-lookup"><span data-stu-id="5d23e-109">**Key/Index**</span></span>|<span data-ttu-id="5d23e-110">**詳細**</span><span class="sxs-lookup"><span data-stu-id="5d23e-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="5d23e-111">**Region1Key**</span><span class="sxs-lookup"><span data-stu-id="5d23e-111">**Region1Key**</span></span> <br/> |<span data-ttu-id="5d23e-112">int</span><span class="sxs-lookup"><span data-stu-id="5d23e-112">int</span></span>  <br/> |<span data-ttu-id="5d23e-113">プライマリ サーバーで、外部</span><span class="sxs-lookup"><span data-stu-id="5d23e-113">Primary, Foreign</span></span>  <br/> |<span data-ttu-id="5d23e-114">[地域テーブル](region.md)から参照されています。</span><span class="sxs-lookup"><span data-stu-id="5d23e-114">Referenced from the [Region table](region.md).</span></span>  <br/> |
|<span data-ttu-id="5d23e-115">**Region2Key**</span><span class="sxs-lookup"><span data-stu-id="5d23e-115">**Region2Key**</span></span> <br/> |<span data-ttu-id="5d23e-116">int</span><span class="sxs-lookup"><span data-stu-id="5d23e-116">int</span></span>  <br/> |<span data-ttu-id="5d23e-117">プライマリ サーバーで、外部</span><span class="sxs-lookup"><span data-stu-id="5d23e-117">Primary, Foreign</span></span>  <br/> |<span data-ttu-id="5d23e-118">[地域テーブル](region.md)から参照されています。</span><span class="sxs-lookup"><span data-stu-id="5d23e-118">Referenced from the [Region table](region.md).</span></span>  <br/> |
   

