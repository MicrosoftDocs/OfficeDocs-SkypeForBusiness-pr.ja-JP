---
title: AppliedBandwidthSource テーブル
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 24fb3caf-19b3-4c0a-90d7-ca5d53de32ad
description: AppliedBandwidthSource テーブルは、サポートテーブルです。 各レコードは1つのソースを表します。
ms.openlocfilehash: 6d40701b74dd5e7312a504127675eed686de7321
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2019
ms.locfileid: "34295112"
---
# <a name="appliedbandwidthsource-table"></a><span data-ttu-id="49f92-104">AppliedBandwidthSource テーブル</span><span class="sxs-lookup"><span data-stu-id="49f92-104">AppliedBandwidthSource table</span></span>
 
<span data-ttu-id="49f92-105">AppliedBandwidthSource テーブルは、サポートテーブルです。</span><span class="sxs-lookup"><span data-stu-id="49f92-105">The AppliedBandwidthSource table is a supporting table.</span></span> <span data-ttu-id="49f92-106">各レコードは1つのソースを表します。</span><span class="sxs-lookup"><span data-stu-id="49f92-106">Each record represents one source.</span></span>
  
|<span data-ttu-id="49f92-107">**列**</span><span class="sxs-lookup"><span data-stu-id="49f92-107">**Column**</span></span>|<span data-ttu-id="49f92-108">**データ型**</span><span class="sxs-lookup"><span data-stu-id="49f92-108">**Data Type**</span></span>|<span data-ttu-id="49f92-109">**キー/インデックス**</span><span class="sxs-lookup"><span data-stu-id="49f92-109">**Key/Index**</span></span>|<span data-ttu-id="49f92-110">**詳細**</span><span class="sxs-lookup"><span data-stu-id="49f92-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="49f92-111">**AppliedBandwidthSourceKey**</span><span class="sxs-lookup"><span data-stu-id="49f92-111">**AppliedBandwidthSourceKey**</span></span> <br/> |<span data-ttu-id="49f92-112">int</span><span class="sxs-lookup"><span data-stu-id="49f92-112">int</span></span>  <br/> |<span data-ttu-id="49f92-113">Primary</span><span class="sxs-lookup"><span data-stu-id="49f92-113">Primary</span></span>  <br/> |<span data-ttu-id="49f92-114">ソースを識別する一意の番号。</span><span class="sxs-lookup"><span data-stu-id="49f92-114">Unique number identifying the source.</span></span>  <br/> |
|<span data-ttu-id="49f92-115">**AppliedBandwidthSource**</span><span class="sxs-lookup"><span data-stu-id="49f92-115">**AppliedBandwidthSource**</span></span> <br/> |<span data-ttu-id="49f92-116">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="49f92-116">varchar(256)</span></span>  <br/> |<span data-ttu-id="49f92-117">一意</span><span class="sxs-lookup"><span data-stu-id="49f92-117">Unique</span></span>  <br/> |<span data-ttu-id="49f92-118">これは、適用される帯域幅の上限のソースです。</span><span class="sxs-lookup"><span data-stu-id="49f92-118">This is the source of the bandwidth cap being imposed.</span></span> <span data-ttu-id="49f92-119">帯域幅の制限の対象となる場所 (たとえば、"Policy Server"、"TURN Server"、"モダリティ" など) について説明します。</span><span class="sxs-lookup"><span data-stu-id="49f92-119">It describes where the bandwidth limit is coming from (for example, "Policy Server", "TURN Server", or "Modality").</span></span>  <br/> |
   

