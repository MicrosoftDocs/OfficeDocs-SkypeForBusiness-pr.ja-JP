---
title: Region テーブル
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
ms.assetid: 1751a6aa-a6e8-4f16-8eb7-ae731c2e3ee3
description: Region テーブルはサポートテーブルです。 各レコードは、[ネットワーク構成] の設定で定義された1つの国/地域を表します。
ms.openlocfilehash: 8e3a0bbe37b1197bae1f35b8fc2ac05f54c5846d
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2020
ms.locfileid: "41806225"
---
# <a name="region-table"></a><span data-ttu-id="ce554-104">Region テーブル</span><span class="sxs-lookup"><span data-stu-id="ce554-104">Region table</span></span>
 
<span data-ttu-id="ce554-105">Region テーブルはサポートテーブルです。</span><span class="sxs-lookup"><span data-stu-id="ce554-105">The Region table is a supporting table.</span></span> <span data-ttu-id="ce554-106">各レコードは、[ネットワーク構成] の設定で定義された1つの国/地域を表します。</span><span class="sxs-lookup"><span data-stu-id="ce554-106">Each record represents one country/region defined in network configuration setting.</span></span>
  
|<span data-ttu-id="ce554-107">**列**</span><span class="sxs-lookup"><span data-stu-id="ce554-107">**Column**</span></span>|<span data-ttu-id="ce554-108">**データ型**</span><span class="sxs-lookup"><span data-stu-id="ce554-108">**Data Type**</span></span>|<span data-ttu-id="ce554-109">**キー/インデックス**</span><span class="sxs-lookup"><span data-stu-id="ce554-109">**Key/Index**</span></span>|<span data-ttu-id="ce554-110">**詳細**</span><span class="sxs-lookup"><span data-stu-id="ce554-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="ce554-111">**RegionKey**</span><span class="sxs-lookup"><span data-stu-id="ce554-111">**RegionKey**</span></span> <br/> |<span data-ttu-id="ce554-112">int</span><span class="sxs-lookup"><span data-stu-id="ce554-112">int</span></span>  <br/> |<span data-ttu-id="ce554-113">Primary</span><span class="sxs-lookup"><span data-stu-id="ce554-113">Primary</span></span>  <br/> |<span data-ttu-id="ce554-114">国または地域を識別する一意の番号。</span><span class="sxs-lookup"><span data-stu-id="ce554-114">Unique number identifying the country/region.</span></span>  <br/> |
|<span data-ttu-id="ce554-115">**RegionName**</span><span class="sxs-lookup"><span data-stu-id="ce554-115">**RegionName**</span></span> <br/> |<span data-ttu-id="ce554-116">nvarchar(128</span><span class="sxs-lookup"><span data-stu-id="ce554-116">nvarchar(128)</span></span>  <br/> |<span data-ttu-id="ce554-117">一意</span><span class="sxs-lookup"><span data-stu-id="ce554-117">Unique</span></span>  <br/> |<span data-ttu-id="ce554-118">国または地域の名前。</span><span class="sxs-lookup"><span data-stu-id="ce554-118">The name of the country/region.</span></span>  <br/> |
   

