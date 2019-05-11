---
title: ビジネス サーバー 2015 の Skype での ConferenceJoinTimeThresholds テーブル
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 3944d724-bdd8-4d1c-a2af-933ee8141529
description: ConferenceJoinTimeThresholds テーブルには、会議への参加時の概要レポートで使用される分類の境界が含まれています。 会議の参加時の要約レポートが正常には会議に参加するユーザーに必要な時間をまとめたもの平均とし、次のカテゴリのいずれかで、これらの時間の値が報告されます。
ms.openlocfilehash: 75df75e16d2a4ed34f667c94f2b2f0960f56e7ff
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "33901437"
---
# <a name="conferencejointimethresholds-table-in-skype-for-business-server-2015"></a><span data-ttu-id="a552c-104">ビジネス サーバー 2015 の Skype での ConferenceJoinTimeThresholds テーブル</span><span class="sxs-lookup"><span data-stu-id="a552c-104">ConferenceJoinTimeThresholds table in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="a552c-105">ConferenceJoinTimeThresholds テーブルには、会議への参加時の概要レポートで使用される分類の境界が含まれています。</span><span class="sxs-lookup"><span data-stu-id="a552c-105">The ConferenceJoinTimeThresholds table contains the classification boundaries used by the Conference Join Time Summary Report.</span></span> <span data-ttu-id="a552c-106">会議の参加時の要約レポートが正常には会議に参加するユーザーに必要な時間をまとめたもの平均とし、次のカテゴリのいずれかで、これらの時間の値が報告されます。</span><span class="sxs-lookup"><span data-stu-id="a552c-106">The Conference Join Time Summary Report summarizes the amount time required for users to successfully join a conference; these time values are reported both as an average and in one of the following categories:</span></span>
  
- <span data-ttu-id="a552c-107">2 秒未満です。</span><span class="sxs-lookup"><span data-stu-id="a552c-107">Less than 2 seconds.</span></span>
    
- <span data-ttu-id="a552c-108">2 秒間、5 秒間です。</span><span class="sxs-lookup"><span data-stu-id="a552c-108">Between 2 second and 5 seconds.</span></span>
    
- <span data-ttu-id="a552c-109">5 秒から 10 秒です。</span><span class="sxs-lookup"><span data-stu-id="a552c-109">Between 5 seconds and 10 seconds.</span></span>
    
- <span data-ttu-id="a552c-110">10 秒より長くします。</span><span class="sxs-lookup"><span data-stu-id="a552c-110">More than 10 seconds.</span></span>
    
<span data-ttu-id="a552c-111">ConferenceJoinTimeThresholds テーブルには、2 秒、5 秒から 10 秒の分類の値が含まれています。</span><span class="sxs-lookup"><span data-stu-id="a552c-111">The ConferenceJoinTimeThresholds table contains the classification values 2 seconds, 5 seconds, and 10 seconds.</span></span>
  
<span data-ttu-id="a552c-112">このテーブルは、Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="a552c-112">This table was introduced in Microsoft Lync Server 2013.</span></span>
  
|<span data-ttu-id="a552c-113">**列**</span><span class="sxs-lookup"><span data-stu-id="a552c-113">**Column**</span></span>|<span data-ttu-id="a552c-114">**データ型**</span><span class="sxs-lookup"><span data-stu-id="a552c-114">**Data Type**</span></span>|<span data-ttu-id="a552c-115">**キー/インデックス**</span><span class="sxs-lookup"><span data-stu-id="a552c-115">**Key/Index**</span></span>|<span data-ttu-id="a552c-116">**詳細**</span><span class="sxs-lookup"><span data-stu-id="a552c-116">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="a552c-117">**ThresholdId**</span><span class="sxs-lookup"><span data-stu-id="a552c-117">**ThresholdId**</span></span> <br/> |<span data-ttu-id="a552c-118">int</span><span class="sxs-lookup"><span data-stu-id="a552c-118">int</span></span>  <br/> |<span data-ttu-id="a552c-119">Primary</span><span class="sxs-lookup"><span data-stu-id="a552c-119">Primary</span></span>  <br/> |<span data-ttu-id="a552c-120">分類の一意の識別子です。</span><span class="sxs-lookup"><span data-stu-id="a552c-120">Unique identifier for the classification.</span></span>  <br/> |
|<span data-ttu-id="a552c-121">**ThresholdValue**</span><span class="sxs-lookup"><span data-stu-id="a552c-121">**ThresholdValue**</span></span> <br/> |<span data-ttu-id="a552c-122">int</span><span class="sxs-lookup"><span data-stu-id="a552c-122">int</span></span>  <br/> || <span data-ttu-id="a552c-123">分類の上限です。</span><span class="sxs-lookup"><span data-stu-id="a552c-123">Upper limit for the classification.</span></span> <span data-ttu-id="a552c-124">有効な値は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="a552c-124">Allowed values are:</span></span> <br/>  <span data-ttu-id="a552c-125">2</span><span class="sxs-lookup"><span data-stu-id="a552c-125">2</span></span> <br/>  <span data-ttu-id="a552c-126">5</span><span class="sxs-lookup"><span data-stu-id="a552c-126">5</span></span> <br/>  <span data-ttu-id="a552c-127">10</span><span class="sxs-lookup"><span data-stu-id="a552c-127">10</span></span> <br/> |
   

