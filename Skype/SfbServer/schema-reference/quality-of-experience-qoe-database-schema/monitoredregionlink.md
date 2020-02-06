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
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: cebda194-7be3-42d6-b6f0-c86f8b0f200a
description: MonitoredRegionLink テーブルはサポートテーブルです。 各レコードは、2つの国/地域間のリンクを1つ表します。
ms.openlocfilehash: a6b92460e2b097460681023f7d6877f02c046bdc
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2020
ms.locfileid: "41807815"
---
# <a name="monitoredregionlink-table"></a><span data-ttu-id="83eeb-104">MonitoredRegionLink テーブル</span><span class="sxs-lookup"><span data-stu-id="83eeb-104">MonitoredRegionLink table</span></span>
 
<span data-ttu-id="83eeb-105">MonitoredRegionLink テーブルはサポートテーブルです。</span><span class="sxs-lookup"><span data-stu-id="83eeb-105">The MonitoredRegionLink table is a supporting table.</span></span> <span data-ttu-id="83eeb-106">各レコードは、2つの国/地域間のリンクを1つ表します。</span><span class="sxs-lookup"><span data-stu-id="83eeb-106">Each record represents one link between two countries/regions.</span></span>
  
|<span data-ttu-id="83eeb-107">**列**</span><span class="sxs-lookup"><span data-stu-id="83eeb-107">**Column**</span></span>|<span data-ttu-id="83eeb-108">**データ型**</span><span class="sxs-lookup"><span data-stu-id="83eeb-108">**Data Type**</span></span>|<span data-ttu-id="83eeb-109">**キー/インデックス**</span><span class="sxs-lookup"><span data-stu-id="83eeb-109">**Key/Index**</span></span>|<span data-ttu-id="83eeb-110">**詳細**</span><span class="sxs-lookup"><span data-stu-id="83eeb-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="83eeb-111">**Region1Key**</span><span class="sxs-lookup"><span data-stu-id="83eeb-111">**Region1Key**</span></span> <br/> |<span data-ttu-id="83eeb-112">int</span><span class="sxs-lookup"><span data-stu-id="83eeb-112">int</span></span>  <br/> |<span data-ttu-id="83eeb-113">プライマリ、外部</span><span class="sxs-lookup"><span data-stu-id="83eeb-113">Primary, Foreign</span></span>  <br/> |<span data-ttu-id="83eeb-114">[Region テーブル](region.md)から参照されます。</span><span class="sxs-lookup"><span data-stu-id="83eeb-114">Referenced from the [Region table](region.md).</span></span>  <br/> |
|<span data-ttu-id="83eeb-115">**Region2Key**</span><span class="sxs-lookup"><span data-stu-id="83eeb-115">**Region2Key**</span></span> <br/> |<span data-ttu-id="83eeb-116">int</span><span class="sxs-lookup"><span data-stu-id="83eeb-116">int</span></span>  <br/> |<span data-ttu-id="83eeb-117">プライマリ、外部</span><span class="sxs-lookup"><span data-stu-id="83eeb-117">Primary, Foreign</span></span>  <br/> |<span data-ttu-id="83eeb-118">[Region テーブル](region.md)から参照されます。</span><span class="sxs-lookup"><span data-stu-id="83eeb-118">Referenced from the [Region table](region.md).</span></span>  <br/> |
   

