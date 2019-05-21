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
localization_priority: Normal
ms.assetid: 1751a6aa-a6e8-4f16-8eb7-ae731c2e3ee3
description: Region テーブルはサポートテーブルです。 各レコードは、[ネットワーク構成] の設定で定義された1つの国/地域を表します。
ms.openlocfilehash: 043a6757087399420983dfd35d213703bd506e91
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2019
ms.locfileid: "34294727"
---
# <a name="region-table"></a><span data-ttu-id="5ea36-104">Region テーブル</span><span class="sxs-lookup"><span data-stu-id="5ea36-104">Region table</span></span>
 
<span data-ttu-id="5ea36-105">Region テーブルはサポートテーブルです。</span><span class="sxs-lookup"><span data-stu-id="5ea36-105">The Region table is a supporting table.</span></span> <span data-ttu-id="5ea36-106">各レコードは、[ネットワーク構成] の設定で定義された1つの国/地域を表します。</span><span class="sxs-lookup"><span data-stu-id="5ea36-106">Each record represents one country/region defined in network configuration setting.</span></span>
  
|<span data-ttu-id="5ea36-107">**列**</span><span class="sxs-lookup"><span data-stu-id="5ea36-107">**Column**</span></span>|<span data-ttu-id="5ea36-108">**データ型**</span><span class="sxs-lookup"><span data-stu-id="5ea36-108">**Data Type**</span></span>|<span data-ttu-id="5ea36-109">**キー/インデックス**</span><span class="sxs-lookup"><span data-stu-id="5ea36-109">**Key/Index**</span></span>|<span data-ttu-id="5ea36-110">**詳細**</span><span class="sxs-lookup"><span data-stu-id="5ea36-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="5ea36-111">**RegionKey**</span><span class="sxs-lookup"><span data-stu-id="5ea36-111">**RegionKey**</span></span> <br/> |<span data-ttu-id="5ea36-112">int</span><span class="sxs-lookup"><span data-stu-id="5ea36-112">int</span></span>  <br/> |<span data-ttu-id="5ea36-113">Primary</span><span class="sxs-lookup"><span data-stu-id="5ea36-113">Primary</span></span>  <br/> |<span data-ttu-id="5ea36-114">国または地域を識別する一意の番号。</span><span class="sxs-lookup"><span data-stu-id="5ea36-114">Unique number identifying the country/region.</span></span>  <br/> |
|<span data-ttu-id="5ea36-115">**RegionName**</span><span class="sxs-lookup"><span data-stu-id="5ea36-115">**RegionName**</span></span> <br/> |<span data-ttu-id="5ea36-116">nvarchar(128</span><span class="sxs-lookup"><span data-stu-id="5ea36-116">nvarchar(128)</span></span>  <br/> |<span data-ttu-id="5ea36-117">一意</span><span class="sxs-lookup"><span data-stu-id="5ea36-117">Unique</span></span>  <br/> |<span data-ttu-id="5ea36-118">国または地域の名前。</span><span class="sxs-lookup"><span data-stu-id="5ea36-118">The name of the country/region.</span></span>  <br/> |
   

