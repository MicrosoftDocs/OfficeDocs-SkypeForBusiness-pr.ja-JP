---
title: tblEnumValue
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
ms.openlocfilehash: 4957f87401dc93cc98d18fa5b1844e13daaefabd
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/28/2018
---
# <a name="tblenumvalue"></a><span data-ttu-id="248a8-103">tblEnumValue</span><span class="sxs-lookup"><span data-stu-id="248a8-103">tblEnumValue</span></span>
 
<span data-ttu-id="248a8-104">tblEnumValue は、Node テーブルで使用されている属性の表示/非表示と動作の値を含むハードコーディングされたテーブルです。</span><span class="sxs-lookup"><span data-stu-id="248a8-104">tblEnumValue is a hardcoded table that contains the Visibility and Behavior values of the attributes that are used in the Node table.</span></span>
  
<span data-ttu-id="248a8-105">**列**</span><span class="sxs-lookup"><span data-stu-id="248a8-105">**Columns**</span></span>

|<span data-ttu-id="248a8-106">**列**</span><span class="sxs-lookup"><span data-stu-id="248a8-106">**Column**</span></span>|<span data-ttu-id="248a8-107">**タイプ**</span><span class="sxs-lookup"><span data-stu-id="248a8-107">**Type**</span></span>|<span data-ttu-id="248a8-108">**説明**</span><span class="sxs-lookup"><span data-stu-id="248a8-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="248a8-109">valueID</span><span class="sxs-lookup"><span data-stu-id="248a8-109">valueID</span></span>  <br/> |<span data-ttu-id="248a8-110">smallint、null でないです。</span><span class="sxs-lookup"><span data-stu-id="248a8-110">smallint, not null</span></span>  <br/> |<span data-ttu-id="248a8-111">値の ID です。</span><span class="sxs-lookup"><span data-stu-id="248a8-111">ID of the value.</span></span>  <br/> |
|<span data-ttu-id="248a8-112">attributeID</span><span class="sxs-lookup"><span data-stu-id="248a8-112">attributeID</span></span>  <br/> |<span data-ttu-id="248a8-113">smallint、null でないです。</span><span class="sxs-lookup"><span data-stu-id="248a8-113">smallint, not null</span></span>  <br/> |<span data-ttu-id="248a8-114">属性の ID です。</span><span class="sxs-lookup"><span data-stu-id="248a8-114">ID of the attribute.</span></span>  <br/> |
|<span data-ttu-id="248a8-115">attributeValue</span><span class="sxs-lookup"><span data-stu-id="248a8-115">attributeValue</span></span>  <br/> |<span data-ttu-id="248a8-116">nvarchar (256)、null でないです。</span><span class="sxs-lookup"><span data-stu-id="248a8-116">nvarchar (256), not null</span></span>  <br/> |<span data-ttu-id="248a8-117">値の名前です。</span><span class="sxs-lookup"><span data-stu-id="248a8-117">Name of the value.</span></span>  <br/> |
   
<span data-ttu-id="248a8-118">**キー**</span><span class="sxs-lookup"><span data-stu-id="248a8-118">**Keys**</span></span>

|<span data-ttu-id="248a8-119">**列**</span><span class="sxs-lookup"><span data-stu-id="248a8-119">**Column**</span></span>|<span data-ttu-id="248a8-120">**説明**</span><span class="sxs-lookup"><span data-stu-id="248a8-120">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="248a8-121">valueID</span><span class="sxs-lookup"><span data-stu-id="248a8-121">valueID</span></span>  <br/> |<span data-ttu-id="248a8-122">プライマリ ・ キーです。</span><span class="sxs-lookup"><span data-stu-id="248a8-122">Primary key.</span></span>  <br/> |
|<span data-ttu-id="248a8-123">attributeID</span><span class="sxs-lookup"><span data-stu-id="248a8-123">attributeID</span></span>  <br/> |<span data-ttu-id="248a8-124">TblEnumAttribute.attributeID テーブル内の参照と外部キーです。</span><span class="sxs-lookup"><span data-stu-id="248a8-124">Foreign key with lookup in tblEnumAttribute.attributeID table.</span></span>  <br/> |
   
<span data-ttu-id="248a8-125">**テーブルの値**</span><span class="sxs-lookup"><span data-stu-id="248a8-125">**Table Values**</span></span>

|<span data-ttu-id="248a8-126">**valueID**</span><span class="sxs-lookup"><span data-stu-id="248a8-126">**valueID**</span></span>|<span data-ttu-id="248a8-127">**attributeID**</span><span class="sxs-lookup"><span data-stu-id="248a8-127">**attributeID**</span></span>|<span data-ttu-id="248a8-128">**attributeValue**</span><span class="sxs-lookup"><span data-stu-id="248a8-128">**attributeValue**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="248a8-129">2</span><span class="sxs-lookup"><span data-stu-id="248a8-129">2</span></span>  <br/> |<span data-ttu-id="248a8-130">1</span><span class="sxs-lookup"><span data-stu-id="248a8-130">1</span></span>  <br/> |<span data-ttu-id="248a8-131">private</span><span class="sxs-lookup"><span data-stu-id="248a8-131">private</span></span>  <br/> |
|<span data-ttu-id="248a8-132">3</span><span class="sxs-lookup"><span data-stu-id="248a8-132">3</span></span>  <br/> |<span data-ttu-id="248a8-133">1</span><span class="sxs-lookup"><span data-stu-id="248a8-133">1</span></span>  <br/> |<span data-ttu-id="248a8-134">スコープ</span><span class="sxs-lookup"><span data-stu-id="248a8-134">scope</span></span>  <br/> |
|<span data-ttu-id="248a8-135">4</span><span class="sxs-lookup"><span data-stu-id="248a8-135">4</span></span>  <br/> |<span data-ttu-id="248a8-136">2</span><span class="sxs-lookup"><span data-stu-id="248a8-136">2</span></span>  <br/> |<span data-ttu-id="248a8-137">通常</span><span class="sxs-lookup"><span data-stu-id="248a8-137">normal</span></span>  <br/> |
|<span data-ttu-id="248a8-138">5</span><span class="sxs-lookup"><span data-stu-id="248a8-138">5</span></span>  <br/> |<span data-ttu-id="248a8-139">2</span><span class="sxs-lookup"><span data-stu-id="248a8-139">2</span></span>  <br/> |<span data-ttu-id="248a8-140">聴衆</span><span class="sxs-lookup"><span data-stu-id="248a8-140">auditorium</span></span>  <br/> |
|<span data-ttu-id="248a8-141">6</span><span class="sxs-lookup"><span data-stu-id="248a8-141">6</span></span>  <br/> |<span data-ttu-id="248a8-142">1</span><span class="sxs-lookup"><span data-stu-id="248a8-142">1</span></span>  <br/> |<span data-ttu-id="248a8-143">開く</span><span class="sxs-lookup"><span data-stu-id="248a8-143">open</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="248a8-144">関連項目</span><span class="sxs-lookup"><span data-stu-id="248a8-144">See also</span></span>

#### 

[<span data-ttu-id="248a8-145">tblNode</span><span class="sxs-lookup"><span data-stu-id="248a8-145">tblNode</span></span>](tblnode.md)

