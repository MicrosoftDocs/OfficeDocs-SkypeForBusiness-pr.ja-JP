---
title: Skype for Business Server 2015 の ConferenceJoinTimeThresholds テーブル
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 3944d724-bdd8-4d1c-a2af-933ee8141529
description: ConferenceJoinTimeThresholds テーブルには、電話会議参加時間要約レポートによって使用される分類境界が含まれます。電話会議参加時間要約レポートは、ユーザーが問題なく電話会議に参加する目的で必要な時間を集計します。これらの時間値は、平均と、以下のカテゴリの 1 つの両方で報告されます。
ms.openlocfilehash: dfa7293307376b5fb5c86cec6f7504d363b005f5
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49813307"
---
# <a name="conferencejointimethresholds-table-in-skype-for-business-server-2015"></a><span data-ttu-id="90e49-104">Skype for Business Server 2015 の ConferenceJoinTimeThresholds テーブル</span><span class="sxs-lookup"><span data-stu-id="90e49-104">ConferenceJoinTimeThresholds table in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="90e49-p102">ConferenceJoinTimeThresholds テーブルには、電話会議参加時間要約レポートによって使用される分類境界が含まれます。電話会議参加時間要約レポートは、ユーザーが問題なく電話会議に参加する目的で必要な時間を集計します。これらの時間値は、平均と、以下のカテゴリの 1 つの両方で報告されます。</span><span class="sxs-lookup"><span data-stu-id="90e49-p102">The ConferenceJoinTimeThresholds table contains the classification boundaries used by the Conference Join Time Summary Report. The Conference Join Time Summary Report summarizes the amount time required for users to successfully join a conference; these time values are reported both as an average and in one of the following categories:</span></span>
  
- <span data-ttu-id="90e49-107">2 秒未満。</span><span class="sxs-lookup"><span data-stu-id="90e49-107">Less than 2 seconds.</span></span>
    
- <span data-ttu-id="90e49-108">2 ～ 5 秒の間。</span><span class="sxs-lookup"><span data-stu-id="90e49-108">Between 2 second and 5 seconds.</span></span>
    
- <span data-ttu-id="90e49-109">5 ～ 10 秒の間。</span><span class="sxs-lookup"><span data-stu-id="90e49-109">Between 5 seconds and 10 seconds.</span></span>
    
- <span data-ttu-id="90e49-110">10 秒以上。</span><span class="sxs-lookup"><span data-stu-id="90e49-110">More than 10 seconds.</span></span>
    
<span data-ttu-id="90e49-111">ConferenceJoinTimeThresholds テーブルには、2 秒、5 秒、および 10 秒の分類値が含まれます。</span><span class="sxs-lookup"><span data-stu-id="90e49-111">The ConferenceJoinTimeThresholds table contains the classification values 2 seconds, 5 seconds, and 10 seconds.</span></span>
  
<span data-ttu-id="90e49-112">この表は、Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="90e49-112">This table was introduced in Microsoft Lync Server 2013.</span></span>
  
|<span data-ttu-id="90e49-113">**列**</span><span class="sxs-lookup"><span data-stu-id="90e49-113">**Column**</span></span>|<span data-ttu-id="90e49-114">**データ型**</span><span class="sxs-lookup"><span data-stu-id="90e49-114">**Data Type**</span></span>|<span data-ttu-id="90e49-115">**キー/インデックス**</span><span class="sxs-lookup"><span data-stu-id="90e49-115">**Key/Index**</span></span>|<span data-ttu-id="90e49-116">**詳細**</span><span class="sxs-lookup"><span data-stu-id="90e49-116">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="90e49-117">**ThresholdId**</span><span class="sxs-lookup"><span data-stu-id="90e49-117">**ThresholdId**</span></span> <br/> |<span data-ttu-id="90e49-118">int</span><span class="sxs-lookup"><span data-stu-id="90e49-118">int</span></span>  <br/> |<span data-ttu-id="90e49-119">Primary</span><span class="sxs-lookup"><span data-stu-id="90e49-119">Primary</span></span>  <br/> |<span data-ttu-id="90e49-120">分類の一意識別子。</span><span class="sxs-lookup"><span data-stu-id="90e49-120">Unique identifier for the classification.</span></span>  <br/> |
|<span data-ttu-id="90e49-121">**ThresholdValue**</span><span class="sxs-lookup"><span data-stu-id="90e49-121">**ThresholdValue**</span></span> <br/> |<span data-ttu-id="90e49-122">int</span><span class="sxs-lookup"><span data-stu-id="90e49-122">int</span></span>  <br/> || <span data-ttu-id="90e49-p103">分類の上限。有効な値は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="90e49-p103">Upper limit for the classification. Allowed values are:</span></span> <br/>  <span data-ttu-id="90e49-125">2 </span><span class="sxs-lookup"><span data-stu-id="90e49-125">2</span></span> <br/>  <span data-ttu-id="90e49-126">5 </span><span class="sxs-lookup"><span data-stu-id="90e49-126">5</span></span> <br/>  <span data-ttu-id="90e49-127">10 </span><span class="sxs-lookup"><span data-stu-id="90e49-127">10</span></span> <br/> |
   

