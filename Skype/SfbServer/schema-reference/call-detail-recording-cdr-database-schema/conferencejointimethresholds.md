---
title: Skype for Business Server 2015 の ConferenceJoinTimeThresholds テーブル
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 3944d724-bdd8-4d1c-a2af-933ee8141529
description: ConferenceJoinTimeThresholds テーブルには、電話会議の参加時間のサマリーレポートで使用される分類境界が含まれています。 [会議参加時間のサマリー] レポートは、ユーザーが会議に参加するのに必要な時間の概要を示します。これらの時間値は、平均として、または次のいずれかのカテゴリに報告されます。
ms.openlocfilehash: 4b2f27b6ab826ff95c1478cf54e8a21c148b1d3c
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2019
ms.locfileid: "34296498"
---
# <a name="conferencejointimethresholds-table-in-skype-for-business-server-2015"></a><span data-ttu-id="83861-104">Skype for Business Server 2015 の ConferenceJoinTimeThresholds テーブル</span><span class="sxs-lookup"><span data-stu-id="83861-104">ConferenceJoinTimeThresholds table in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="83861-105">ConferenceJoinTimeThresholds テーブルには、電話会議の参加時間のサマリーレポートで使用される分類境界が含まれています。</span><span class="sxs-lookup"><span data-stu-id="83861-105">The ConferenceJoinTimeThresholds table contains the classification boundaries used by the Conference Join Time Summary Report.</span></span> <span data-ttu-id="83861-106">[会議参加時間のサマリー] レポートは、ユーザーが会議に参加するのに必要な時間の概要を示します。これらの時間値は、平均として、または次のいずれかのカテゴリに報告されます。</span><span class="sxs-lookup"><span data-stu-id="83861-106">The Conference Join Time Summary Report summarizes the amount time required for users to successfully join a conference; these time values are reported both as an average and in one of the following categories:</span></span>
  
- <span data-ttu-id="83861-107">2秒未満。</span><span class="sxs-lookup"><span data-stu-id="83861-107">Less than 2 seconds.</span></span>
    
- <span data-ttu-id="83861-108">2秒と5秒の間。</span><span class="sxs-lookup"><span data-stu-id="83861-108">Between 2 second and 5 seconds.</span></span>
    
- <span data-ttu-id="83861-109">5 ~ 10 秒の間。</span><span class="sxs-lookup"><span data-stu-id="83861-109">Between 5 seconds and 10 seconds.</span></span>
    
- <span data-ttu-id="83861-110">10秒以上</span><span class="sxs-lookup"><span data-stu-id="83861-110">More than 10 seconds.</span></span>
    
<span data-ttu-id="83861-111">ConferenceJoinTimeThresholds テーブルには、2秒、5秒、10秒の分類値が含まれています。</span><span class="sxs-lookup"><span data-stu-id="83861-111">The ConferenceJoinTimeThresholds table contains the classification values 2 seconds, 5 seconds, and 10 seconds.</span></span>
  
<span data-ttu-id="83861-112">この表は、Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="83861-112">This table was introduced in Microsoft Lync Server 2013.</span></span>
  
|<span data-ttu-id="83861-113">**列**</span><span class="sxs-lookup"><span data-stu-id="83861-113">**Column**</span></span>|<span data-ttu-id="83861-114">**データ型**</span><span class="sxs-lookup"><span data-stu-id="83861-114">**Data Type**</span></span>|<span data-ttu-id="83861-115">**キー/インデックス**</span><span class="sxs-lookup"><span data-stu-id="83861-115">**Key/Index**</span></span>|<span data-ttu-id="83861-116">**詳細**</span><span class="sxs-lookup"><span data-stu-id="83861-116">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="83861-117">**ThresholdId**</span><span class="sxs-lookup"><span data-stu-id="83861-117">**ThresholdId**</span></span> <br/> |<span data-ttu-id="83861-118">int</span><span class="sxs-lookup"><span data-stu-id="83861-118">int</span></span>  <br/> |<span data-ttu-id="83861-119">Primary</span><span class="sxs-lookup"><span data-stu-id="83861-119">Primary</span></span>  <br/> |<span data-ttu-id="83861-120">分類の一意の識別子。</span><span class="sxs-lookup"><span data-stu-id="83861-120">Unique identifier for the classification.</span></span>  <br/> |
|<span data-ttu-id="83861-121">**ThresholdValue**</span><span class="sxs-lookup"><span data-stu-id="83861-121">**ThresholdValue**</span></span> <br/> |<span data-ttu-id="83861-122">int</span><span class="sxs-lookup"><span data-stu-id="83861-122">int</span></span>  <br/> || <span data-ttu-id="83861-123">分類の上限。</span><span class="sxs-lookup"><span data-stu-id="83861-123">Upper limit for the classification.</span></span> <span data-ttu-id="83861-124">有効な値は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="83861-124">Allowed values are:</span></span> <br/>  <span data-ttu-id="83861-125">2</span><span class="sxs-lookup"><span data-stu-id="83861-125">2</span></span> <br/>  <span data-ttu-id="83861-126">5</span><span class="sxs-lookup"><span data-stu-id="83861-126">5</span></span> <br/>  <span data-ttu-id="83861-127">常用</span><span class="sxs-lookup"><span data-stu-id="83861-127">10</span></span> <br/> |
   

