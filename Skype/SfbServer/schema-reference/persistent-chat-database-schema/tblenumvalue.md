---
title: tblEnumValue
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: a33df20c-d19d-4f5c-b012-29dab8fb9200
description: tblEnumValue は、Node テーブルで使用されている属性の表示/非表示と動作の値を含むハードコーディングされたテーブルです。
ms.openlocfilehash: 579b2747ea753b8a701d11dd806178427cbb27b3
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "32212881"
---
# <a name="tblenumvalue"></a><span data-ttu-id="17d11-103">tblEnumValue</span><span class="sxs-lookup"><span data-stu-id="17d11-103">tblEnumValue</span></span>
 
<span data-ttu-id="17d11-104">tblEnumValue は、Node テーブルで使用されている属性の表示/非表示と動作の値を含むハードコーディングされたテーブルです。</span><span class="sxs-lookup"><span data-stu-id="17d11-104">tblEnumValue is a hardcoded table that contains the Visibility and Behavior values of the attributes that are used in the Node table.</span></span>
  
<span data-ttu-id="17d11-105">**列**</span><span class="sxs-lookup"><span data-stu-id="17d11-105">**Columns**</span></span>

|<span data-ttu-id="17d11-106">**列**</span><span class="sxs-lookup"><span data-stu-id="17d11-106">**Column**</span></span>|<span data-ttu-id="17d11-107">**型**</span><span class="sxs-lookup"><span data-stu-id="17d11-107">**Type**</span></span>|<span data-ttu-id="17d11-108">**説明**</span><span class="sxs-lookup"><span data-stu-id="17d11-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="17d11-109">valueID</span><span class="sxs-lookup"><span data-stu-id="17d11-109">valueID</span></span>  <br/> |<span data-ttu-id="17d11-110">smallint、null でないです。</span><span class="sxs-lookup"><span data-stu-id="17d11-110">smallint, not null</span></span>  <br/> |<span data-ttu-id="17d11-111">値の ID です。</span><span class="sxs-lookup"><span data-stu-id="17d11-111">ID of the value.</span></span>  <br/> |
|<span data-ttu-id="17d11-112">attributeID</span><span class="sxs-lookup"><span data-stu-id="17d11-112">attributeID</span></span>  <br/> |<span data-ttu-id="17d11-113">smallint、null でないです。</span><span class="sxs-lookup"><span data-stu-id="17d11-113">smallint, not null</span></span>  <br/> |<span data-ttu-id="17d11-114">属性の ID です。</span><span class="sxs-lookup"><span data-stu-id="17d11-114">ID of the attribute.</span></span>  <br/> |
|<span data-ttu-id="17d11-115">attributeValue</span><span class="sxs-lookup"><span data-stu-id="17d11-115">attributeValue</span></span>  <br/> |<span data-ttu-id="17d11-116">nvarchar (256)、null でないです。</span><span class="sxs-lookup"><span data-stu-id="17d11-116">nvarchar (256), not null</span></span>  <br/> |<span data-ttu-id="17d11-117">値の名前です。</span><span class="sxs-lookup"><span data-stu-id="17d11-117">Name of the value.</span></span>  <br/> |
   
<span data-ttu-id="17d11-118">**キー**</span><span class="sxs-lookup"><span data-stu-id="17d11-118">**Keys**</span></span>

|<span data-ttu-id="17d11-119">**列**</span><span class="sxs-lookup"><span data-stu-id="17d11-119">**Column**</span></span>|<span data-ttu-id="17d11-120">**説明**</span><span class="sxs-lookup"><span data-stu-id="17d11-120">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="17d11-121">valueID</span><span class="sxs-lookup"><span data-stu-id="17d11-121">valueID</span></span>  <br/> |<span data-ttu-id="17d11-122">プライマリ ・ キーです。</span><span class="sxs-lookup"><span data-stu-id="17d11-122">Primary key.</span></span>  <br/> |
|<span data-ttu-id="17d11-123">attributeID</span><span class="sxs-lookup"><span data-stu-id="17d11-123">attributeID</span></span>  <br/> |<span data-ttu-id="17d11-124">TblEnumAttribute.attributeID テーブル内の参照と外部キーです。</span><span class="sxs-lookup"><span data-stu-id="17d11-124">Foreign key with lookup in tblEnumAttribute.attributeID table.</span></span>  <br/> |
   
<span data-ttu-id="17d11-125">**テーブルの値**</span><span class="sxs-lookup"><span data-stu-id="17d11-125">**Table Values**</span></span>

|<span data-ttu-id="17d11-126">**valueID**</span><span class="sxs-lookup"><span data-stu-id="17d11-126">**valueID**</span></span>|<span data-ttu-id="17d11-127">**attributeID**</span><span class="sxs-lookup"><span data-stu-id="17d11-127">**attributeID**</span></span>|<span data-ttu-id="17d11-128">**attributeValue**</span><span class="sxs-lookup"><span data-stu-id="17d11-128">**attributeValue**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="17d11-129">2</span><span class="sxs-lookup"><span data-stu-id="17d11-129">2</span></span>  <br/> |<span data-ttu-id="17d11-130">1</span><span class="sxs-lookup"><span data-stu-id="17d11-130">1</span></span>  <br/> |<span data-ttu-id="17d11-131">private</span><span class="sxs-lookup"><span data-stu-id="17d11-131">private</span></span>  <br/> |
|<span data-ttu-id="17d11-132">3</span><span class="sxs-lookup"><span data-stu-id="17d11-132">3</span></span>  <br/> |<span data-ttu-id="17d11-133">1</span><span class="sxs-lookup"><span data-stu-id="17d11-133">1</span></span>  <br/> |<span data-ttu-id="17d11-134">スコープ</span><span class="sxs-lookup"><span data-stu-id="17d11-134">scope</span></span>  <br/> |
|<span data-ttu-id="17d11-135">4</span><span class="sxs-lookup"><span data-stu-id="17d11-135">4</span></span>  <br/> |<span data-ttu-id="17d11-136">2</span><span class="sxs-lookup"><span data-stu-id="17d11-136">2</span></span>  <br/> |<span data-ttu-id="17d11-137">通常</span><span class="sxs-lookup"><span data-stu-id="17d11-137">normal</span></span>  <br/> |
|<span data-ttu-id="17d11-138">5</span><span class="sxs-lookup"><span data-stu-id="17d11-138">5</span></span>  <br/> |<span data-ttu-id="17d11-139">2</span><span class="sxs-lookup"><span data-stu-id="17d11-139">2</span></span>  <br/> |<span data-ttu-id="17d11-140">聴衆</span><span class="sxs-lookup"><span data-stu-id="17d11-140">auditorium</span></span>  <br/> |
|<span data-ttu-id="17d11-141">6</span><span class="sxs-lookup"><span data-stu-id="17d11-141">6</span></span>  <br/> |<span data-ttu-id="17d11-142">1</span><span class="sxs-lookup"><span data-stu-id="17d11-142">1</span></span>  <br/> |<span data-ttu-id="17d11-143">開く</span><span class="sxs-lookup"><span data-stu-id="17d11-143">open</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="17d11-144">関連項目</span><span class="sxs-lookup"><span data-stu-id="17d11-144">See also</span></span>

[<span data-ttu-id="17d11-145">tblNode</span><span class="sxs-lookup"><span data-stu-id="17d11-145">tblNode</span></span>](tblnode.md)
