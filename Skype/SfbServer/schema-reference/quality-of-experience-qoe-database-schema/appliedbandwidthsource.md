---
title: AppliedBandwidthSource テーブル
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 24fb3caf-19b3-4c0a-90d7-ca5d53de32ad
description: AppliedBandwidthSource はテーブルをサポートします。 各レコードは、1 つのソースを表します。
ms.openlocfilehash: 2fed25b6ca2218cb8b7300507b5c8258b2c29798
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "32212356"
---
# <a name="appliedbandwidthsource-table"></a><span data-ttu-id="898fe-104">AppliedBandwidthSource テーブル</span><span class="sxs-lookup"><span data-stu-id="898fe-104">AppliedBandwidthSource table</span></span>
 
<span data-ttu-id="898fe-105">AppliedBandwidthSource はテーブルをサポートします。</span><span class="sxs-lookup"><span data-stu-id="898fe-105">The AppliedBandwidthSource table is a supporting table.</span></span> <span data-ttu-id="898fe-106">各レコードは、1 つのソースを表します。</span><span class="sxs-lookup"><span data-stu-id="898fe-106">Each record represents one source.</span></span>
  
|<span data-ttu-id="898fe-107">**列**</span><span class="sxs-lookup"><span data-stu-id="898fe-107">**Column**</span></span>|<span data-ttu-id="898fe-108">**データ型**</span><span class="sxs-lookup"><span data-stu-id="898fe-108">**Data Type**</span></span>|<span data-ttu-id="898fe-109">**キー/インデックス**</span><span class="sxs-lookup"><span data-stu-id="898fe-109">**Key/Index**</span></span>|<span data-ttu-id="898fe-110">**詳細**</span><span class="sxs-lookup"><span data-stu-id="898fe-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="898fe-111">**AppliedBandwidthSourceKey**</span><span class="sxs-lookup"><span data-stu-id="898fe-111">**AppliedBandwidthSourceKey**</span></span> <br/> |<span data-ttu-id="898fe-112">int</span><span class="sxs-lookup"><span data-stu-id="898fe-112">int</span></span>  <br/> |<span data-ttu-id="898fe-113">Primary</span><span class="sxs-lookup"><span data-stu-id="898fe-113">Primary</span></span>  <br/> |<span data-ttu-id="898fe-114">ソースを識別する一意の番号です。</span><span class="sxs-lookup"><span data-stu-id="898fe-114">Unique number identifying the source.</span></span>  <br/> |
|<span data-ttu-id="898fe-115">**AppliedBandwidthSource**</span><span class="sxs-lookup"><span data-stu-id="898fe-115">**AppliedBandwidthSource**</span></span> <br/> |<span data-ttu-id="898fe-116">varchar(256)</span><span class="sxs-lookup"><span data-stu-id="898fe-116">varchar(256)</span></span>  <br/> |<span data-ttu-id="898fe-117">一意</span><span class="sxs-lookup"><span data-stu-id="898fe-117">Unique</span></span>  <br/> |<span data-ttu-id="898fe-118">これは、適用されている帯域幅のキャップのソースです。</span><span class="sxs-lookup"><span data-stu-id="898fe-118">This is the source of the bandwidth cap being imposed.</span></span> <span data-ttu-id="898fe-119">それは、帯域幅の制限値の取得先 (ポリシー サーバー」、「サーバーを有効にする」または「モダリティ」など) について説明します。</span><span class="sxs-lookup"><span data-stu-id="898fe-119">It describes where the bandwidth limit is coming from (for example, "Policy Server", "TURN Server", or "Modality").</span></span>  <br/> |
   

