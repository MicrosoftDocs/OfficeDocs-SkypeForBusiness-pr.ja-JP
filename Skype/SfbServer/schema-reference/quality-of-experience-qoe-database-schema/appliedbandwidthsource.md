---
title: AppliedBandwidthSource テーブル
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
ms.assetid: 24fb3caf-19b3-4c0a-90d7-ca5d53de32ad
description: AppliedBandwidthSource テーブルはサポート テーブルです。 各レコードは 1 つのソースを表します。
ms.openlocfilehash: bf7e1be3b98bcd56fea16dbd7aa7171b056a7f3c
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49831407"
---
# <a name="appliedbandwidthsource-table"></a><span data-ttu-id="b9101-104">AppliedBandwidthSource テーブル</span><span class="sxs-lookup"><span data-stu-id="b9101-104">AppliedBandwidthSource table</span></span>
 
<span data-ttu-id="b9101-p102">AppliedBandwidthSource テーブルはサポート テーブルです。各レコードは 1 つのソースを表します。</span><span class="sxs-lookup"><span data-stu-id="b9101-p102">The AppliedBandwidthSource table is a supporting table. Each record represents one source.</span></span>
  
|<span data-ttu-id="b9101-107">**列**</span><span class="sxs-lookup"><span data-stu-id="b9101-107">**Column**</span></span>|<span data-ttu-id="b9101-108">**データ型**</span><span class="sxs-lookup"><span data-stu-id="b9101-108">**Data Type**</span></span>|<span data-ttu-id="b9101-109">**キー/インデックス**</span><span class="sxs-lookup"><span data-stu-id="b9101-109">**Key/Index**</span></span>|<span data-ttu-id="b9101-110">**詳細**</span><span class="sxs-lookup"><span data-stu-id="b9101-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="b9101-111">**AppliedBandwidthSourceKey**</span><span class="sxs-lookup"><span data-stu-id="b9101-111">**AppliedBandwidthSourceKey**</span></span> <br/> |<span data-ttu-id="b9101-112">int</span><span class="sxs-lookup"><span data-stu-id="b9101-112">int</span></span>  <br/> |<span data-ttu-id="b9101-113">Primary</span><span class="sxs-lookup"><span data-stu-id="b9101-113">Primary</span></span>  <br/> |<span data-ttu-id="b9101-114">ソースを示す一意の番号です。</span><span class="sxs-lookup"><span data-stu-id="b9101-114">Unique number identifying the source.</span></span>  <br/> |
|<span data-ttu-id="b9101-115">**AppliedBandwidthSource**</span><span class="sxs-lookup"><span data-stu-id="b9101-115">**AppliedBandwidthSource**</span></span> <br/> |<span data-ttu-id="b9101-116">varchar(256)</span><span class="sxs-lookup"><span data-stu-id="b9101-116">varchar(256)</span></span>  <br/> |<span data-ttu-id="b9101-117">一意</span><span class="sxs-lookup"><span data-stu-id="b9101-117">Unique</span></span>  <br/> |<span data-ttu-id="b9101-118">適用されている帯域幅キャップのソースです。</span><span class="sxs-lookup"><span data-stu-id="b9101-118">This is the source of the bandwidth cap being imposed.</span></span> <span data-ttu-id="b9101-119">帯域幅制限の適用先 ("Policy Server"、"TURN Server"、"Modality" など) について説明します。</span><span class="sxs-lookup"><span data-stu-id="b9101-119">It describes where the bandwidth limit is coming from (for example, "Policy Server", "TURN Server", or "Modality").</span></span>  <br/> |
   

