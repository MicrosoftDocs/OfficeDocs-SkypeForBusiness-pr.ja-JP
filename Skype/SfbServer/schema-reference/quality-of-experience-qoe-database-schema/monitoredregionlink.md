---
title: MonitoredRegionLink テーブル
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: cebda194-7be3-42d6-b6f0-c86f8b0f200a
description: MonitoredRegionLink テーブルはサポートテーブルです。 各レコードは、2つの国/地域間のリンクを1つ表します。
ms.openlocfilehash: fdace97e0a7c9685f59471074cca64ede4fcc63d
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2019
ms.locfileid: "34294874"
---
# <a name="monitoredregionlink-table"></a><span data-ttu-id="9895d-104">MonitoredRegionLink テーブル</span><span class="sxs-lookup"><span data-stu-id="9895d-104">MonitoredRegionLink table</span></span>
 
<span data-ttu-id="9895d-105">MonitoredRegionLink テーブルはサポートテーブルです。</span><span class="sxs-lookup"><span data-stu-id="9895d-105">The MonitoredRegionLink table is a supporting table.</span></span> <span data-ttu-id="9895d-106">各レコードは、2つの国/地域間のリンクを1つ表します。</span><span class="sxs-lookup"><span data-stu-id="9895d-106">Each record represents one link between two countries/regions.</span></span>
  
|<span data-ttu-id="9895d-107">**列**</span><span class="sxs-lookup"><span data-stu-id="9895d-107">**Column**</span></span>|<span data-ttu-id="9895d-108">**データ型**</span><span class="sxs-lookup"><span data-stu-id="9895d-108">**Data Type**</span></span>|<span data-ttu-id="9895d-109">**キー/インデックス**</span><span class="sxs-lookup"><span data-stu-id="9895d-109">**Key/Index**</span></span>|<span data-ttu-id="9895d-110">**詳細**</span><span class="sxs-lookup"><span data-stu-id="9895d-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="9895d-111">**Region1Key**</span><span class="sxs-lookup"><span data-stu-id="9895d-111">**Region1Key**</span></span> <br/> |<span data-ttu-id="9895d-112">int</span><span class="sxs-lookup"><span data-stu-id="9895d-112">int</span></span>  <br/> |<span data-ttu-id="9895d-113">プライマリ、外部</span><span class="sxs-lookup"><span data-stu-id="9895d-113">Primary, Foreign</span></span>  <br/> |<span data-ttu-id="9895d-114">[Region テーブル](region.md)から参照されます。</span><span class="sxs-lookup"><span data-stu-id="9895d-114">Referenced from the [Region table](region.md).</span></span>  <br/> |
|<span data-ttu-id="9895d-115">**Region2Key**</span><span class="sxs-lookup"><span data-stu-id="9895d-115">**Region2Key**</span></span> <br/> |<span data-ttu-id="9895d-116">int</span><span class="sxs-lookup"><span data-stu-id="9895d-116">int</span></span>  <br/> |<span data-ttu-id="9895d-117">プライマリ、外部</span><span class="sxs-lookup"><span data-stu-id="9895d-117">Primary, Foreign</span></span>  <br/> |<span data-ttu-id="9895d-118">[Region テーブル](region.md)から参照されます。</span><span class="sxs-lookup"><span data-stu-id="9895d-118">Referenced from the [Region table](region.md).</span></span>  <br/> |
   

