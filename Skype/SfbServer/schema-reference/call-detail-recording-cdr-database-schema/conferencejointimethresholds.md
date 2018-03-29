---
title: ビジネス サーバー 2015 の Skype での ConferenceJoinTimeThresholds テーブル
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 3944d724-bdd8-4d1c-a2af-933ee8141529
description: ConferenceJoinTimeThresholds テーブルには、会議への参加時の概要レポートで使用される分類の境界が含まれています。 会議の参加時の要約レポートが正常には会議に参加するユーザーに必要な時間をまとめたもの平均とし、次のカテゴリのいずれかで、これらの時間の値が報告されます。
ms.openlocfilehash: 3646337c9e9f20ac0b1dabfdd5504ce83dfa5c40
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/28/2018
---
# <a name="conferencejointimethresholds-table-in-skype-for-business-server-2015"></a><span data-ttu-id="eef8b-104">ビジネス サーバー 2015 の Skype での ConferenceJoinTimeThresholds テーブル</span><span class="sxs-lookup"><span data-stu-id="eef8b-104">ConferenceJoinTimeThresholds table in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="eef8b-105">ConferenceJoinTimeThresholds テーブルには、会議への参加時の概要レポートで使用される分類の境界が含まれています。</span><span class="sxs-lookup"><span data-stu-id="eef8b-105">The ConferenceJoinTimeThresholds table contains the classification boundaries used by the Conference Join Time Summary Report.</span></span> <span data-ttu-id="eef8b-106">会議の参加時の要約レポートが正常には会議に参加するユーザーに必要な時間をまとめたもの平均とし、次のカテゴリのいずれかで、これらの時間の値が報告されます。</span><span class="sxs-lookup"><span data-stu-id="eef8b-106">The Conference Join Time Summary Report summarizes the amount time required for users to successfully join a conference; these time values are reported both as an average and in one of the following categories:</span></span>
  
- <span data-ttu-id="eef8b-107">2 秒未満です。</span><span class="sxs-lookup"><span data-stu-id="eef8b-107">Less than 2 seconds.</span></span>
    
- <span data-ttu-id="eef8b-108">2 秒間、5 秒間です。</span><span class="sxs-lookup"><span data-stu-id="eef8b-108">Between 2 second and 5 seconds.</span></span>
    
- <span data-ttu-id="eef8b-109">5 秒から 10 秒です。</span><span class="sxs-lookup"><span data-stu-id="eef8b-109">Between 5 seconds and 10 seconds.</span></span>
    
- <span data-ttu-id="eef8b-110">10 秒より長くします。</span><span class="sxs-lookup"><span data-stu-id="eef8b-110">More than 10 seconds.</span></span>
    
<span data-ttu-id="eef8b-111">ConferenceJoinTimeThresholds テーブルには、2 秒、5 秒から 10 秒の分類の値が含まれています。</span><span class="sxs-lookup"><span data-stu-id="eef8b-111">The ConferenceJoinTimeThresholds table contains the classification values 2 seconds, 5 seconds, and 10 seconds.</span></span>
  
<span data-ttu-id="eef8b-112">このテーブルは、Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="eef8b-112">This table was introduced in Microsoft Lync Server 2013.</span></span>
  
|<span data-ttu-id="eef8b-113">**列**</span><span class="sxs-lookup"><span data-stu-id="eef8b-113">**Column**</span></span>|<span data-ttu-id="eef8b-114">**データ型**</span><span class="sxs-lookup"><span data-stu-id="eef8b-114">**Data Type**</span></span>|<span data-ttu-id="eef8b-115">**キーまたはインデックス**</span><span class="sxs-lookup"><span data-stu-id="eef8b-115">**Key/Index**</span></span>|<span data-ttu-id="eef8b-116">**詳細**</span><span class="sxs-lookup"><span data-stu-id="eef8b-116">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="eef8b-117">**ThresholdId**</span><span class="sxs-lookup"><span data-stu-id="eef8b-117">**ThresholdId**</span></span> <br/> |<span data-ttu-id="eef8b-118">int</span><span class="sxs-lookup"><span data-stu-id="eef8b-118">int</span></span>  <br/> |<span data-ttu-id="eef8b-119">Primary</span><span class="sxs-lookup"><span data-stu-id="eef8b-119">Primary</span></span>  <br/> |<span data-ttu-id="eef8b-120">分類の一意の識別子です。</span><span class="sxs-lookup"><span data-stu-id="eef8b-120">Unique identifier for the classification.</span></span>  <br/> |
|<span data-ttu-id="eef8b-121">**ThresholdValue**</span><span class="sxs-lookup"><span data-stu-id="eef8b-121">**ThresholdValue**</span></span> <br/> |<span data-ttu-id="eef8b-122">int</span><span class="sxs-lookup"><span data-stu-id="eef8b-122">int</span></span>  <br/> || <span data-ttu-id="eef8b-123">分類の上限です。</span><span class="sxs-lookup"><span data-stu-id="eef8b-123">Upper limit for the classification.</span></span> <span data-ttu-id="eef8b-124">有効な値は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="eef8b-124">Allowed values are:</span></span> <br/>  <span data-ttu-id="eef8b-125">2</span><span class="sxs-lookup"><span data-stu-id="eef8b-125">2</span></span> <br/>  <span data-ttu-id="eef8b-126">5</span><span class="sxs-lookup"><span data-stu-id="eef8b-126">5</span></span> <br/>  <span data-ttu-id="eef8b-127">10</span><span class="sxs-lookup"><span data-stu-id="eef8b-127">10</span></span> <br/> |
   

