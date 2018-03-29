---
title: MonitoredRegionLink テーブル
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
ms.openlocfilehash: 471291788dabee412bffef641624afad2a2c10b4
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/28/2018
---
# <a name="monitoredregionlink-table"></a><span data-ttu-id="96221-104">MonitoredRegionLink テーブル</span><span class="sxs-lookup"><span data-stu-id="96221-104">MonitoredRegionLink table</span></span>
 
<span data-ttu-id="96221-105">MonitoredRegionLink はテーブルをサポートします。</span><span class="sxs-lookup"><span data-stu-id="96221-105">The MonitoredRegionLink table is a supporting table.</span></span> <span data-ttu-id="96221-106">各レコードは、2 つの国/地域の間の 1 つのリンクを表します。</span><span class="sxs-lookup"><span data-stu-id="96221-106">Each record represents one link between two countries/regions.</span></span>
  
|<span data-ttu-id="96221-107">**列**</span><span class="sxs-lookup"><span data-stu-id="96221-107">**Column**</span></span>|<span data-ttu-id="96221-108">**データ型**</span><span class="sxs-lookup"><span data-stu-id="96221-108">**Data Type**</span></span>|<span data-ttu-id="96221-109">**キーまたはインデックス**</span><span class="sxs-lookup"><span data-stu-id="96221-109">**Key/Index**</span></span>|<span data-ttu-id="96221-110">**詳細**</span><span class="sxs-lookup"><span data-stu-id="96221-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="96221-111">**Region1Key**</span><span class="sxs-lookup"><span data-stu-id="96221-111">**Region1Key**</span></span> <br/> |<span data-ttu-id="96221-112">int</span><span class="sxs-lookup"><span data-stu-id="96221-112">int</span></span>  <br/> |<span data-ttu-id="96221-113">プライマリ サーバーで、外部</span><span class="sxs-lookup"><span data-stu-id="96221-113">Primary, Foreign</span></span>  <br/> |<span data-ttu-id="96221-114">[地域テーブル](region.md)から参照されています。</span><span class="sxs-lookup"><span data-stu-id="96221-114">Referenced from the [Region table](region.md).</span></span>  <br/> |
|<span data-ttu-id="96221-115">**Region2Key**</span><span class="sxs-lookup"><span data-stu-id="96221-115">**Region2Key**</span></span> <br/> |<span data-ttu-id="96221-116">int</span><span class="sxs-lookup"><span data-stu-id="96221-116">int</span></span>  <br/> |<span data-ttu-id="96221-117">プライマリ サーバーで、外部</span><span class="sxs-lookup"><span data-stu-id="96221-117">Primary, Foreign</span></span>  <br/> |<span data-ttu-id="96221-118">[地域テーブル](region.md)から参照されています。</span><span class="sxs-lookup"><span data-stu-id="96221-118">Referenced from the [Region table](region.md).</span></span>  <br/> |
   

