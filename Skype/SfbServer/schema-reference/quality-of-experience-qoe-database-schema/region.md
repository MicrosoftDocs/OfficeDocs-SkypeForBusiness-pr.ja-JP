---
title: Region テーブル
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 1751a6aa-a6e8-4f16-8eb7-ae731c2e3ee3
description: 領域はテーブルをサポートします。 各レコードは、ネットワーク構成設定で定義されている 1 つの国/地域を表します。
ms.openlocfilehash: 1fcc6c0b4b2d9cbe1edc0a7127cda7f54cd079ed
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/27/2019
ms.locfileid: "30880540"
---
# <a name="region-table"></a><span data-ttu-id="3b8f8-104">Region テーブル</span><span class="sxs-lookup"><span data-stu-id="3b8f8-104">Region table</span></span>
 
<span data-ttu-id="3b8f8-105">領域はテーブルをサポートします。</span><span class="sxs-lookup"><span data-stu-id="3b8f8-105">The Region table is a supporting table.</span></span> <span data-ttu-id="3b8f8-106">各レコードは、ネットワーク構成設定で定義されている 1 つの国/地域を表します。</span><span class="sxs-lookup"><span data-stu-id="3b8f8-106">Each record represents one country/region defined in network configuration setting.</span></span>
  
|<span data-ttu-id="3b8f8-107">**列**</span><span class="sxs-lookup"><span data-stu-id="3b8f8-107">**Column**</span></span>|<span data-ttu-id="3b8f8-108">**データ型**</span><span class="sxs-lookup"><span data-stu-id="3b8f8-108">**Data Type**</span></span>|<span data-ttu-id="3b8f8-109">**キー/インデックス**</span><span class="sxs-lookup"><span data-stu-id="3b8f8-109">**Key/Index**</span></span>|<span data-ttu-id="3b8f8-110">**詳細**</span><span class="sxs-lookup"><span data-stu-id="3b8f8-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="3b8f8-111">**RegionKey**</span><span class="sxs-lookup"><span data-stu-id="3b8f8-111">**RegionKey**</span></span> <br/> |<span data-ttu-id="3b8f8-112">int</span><span class="sxs-lookup"><span data-stu-id="3b8f8-112">int</span></span>  <br/> |<span data-ttu-id="3b8f8-113">Primary</span><span class="sxs-lookup"><span data-stu-id="3b8f8-113">Primary</span></span>  <br/> |<span data-ttu-id="3b8f8-114">国/地域を識別する一意の番号です。</span><span class="sxs-lookup"><span data-stu-id="3b8f8-114">Unique number identifying the country/region.</span></span>  <br/> |
|<span data-ttu-id="3b8f8-115">**RegionName**</span><span class="sxs-lookup"><span data-stu-id="3b8f8-115">**RegionName**</span></span> <br/> |<span data-ttu-id="3b8f8-116">nvarchar (128)</span><span class="sxs-lookup"><span data-stu-id="3b8f8-116">nvarchar(128)</span></span>  <br/> |<span data-ttu-id="3b8f8-117">一意</span><span class="sxs-lookup"><span data-stu-id="3b8f8-117">Unique</span></span>  <br/> |<span data-ttu-id="3b8f8-118">国/地域の名前。</span><span class="sxs-lookup"><span data-stu-id="3b8f8-118">The name of the country/region.</span></span>  <br/> |
   

