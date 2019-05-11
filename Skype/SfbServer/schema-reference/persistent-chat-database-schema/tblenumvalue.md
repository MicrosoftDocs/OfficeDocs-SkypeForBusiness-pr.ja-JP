---
title: tblEnumValue
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: a33df20c-d19d-4f5c-b012-29dab8fb9200
description: tblEnumValue は、Node テーブルで使用されている属性の表示/非表示と動作の値を含むハードコーディングされたテーブルです。
ms.openlocfilehash: 00ee5a7a7538fa620e438ead5e986f859ef25a6c
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "33929869"
---
# <a name="tblenumvalue"></a><span data-ttu-id="f4eff-103">tblEnumValue</span><span class="sxs-lookup"><span data-stu-id="f4eff-103">tblEnumValue</span></span>
 
<span data-ttu-id="f4eff-104">tblEnumValue は、Node テーブルで使用されている属性の表示/非表示と動作の値を含むハードコーディングされたテーブルです。</span><span class="sxs-lookup"><span data-stu-id="f4eff-104">tblEnumValue is a hardcoded table that contains the Visibility and Behavior values of the attributes that are used in the Node table.</span></span>
  
<span data-ttu-id="f4eff-105">**列**</span><span class="sxs-lookup"><span data-stu-id="f4eff-105">**Columns**</span></span>

|<span data-ttu-id="f4eff-106">**列**</span><span class="sxs-lookup"><span data-stu-id="f4eff-106">**Column**</span></span>|<span data-ttu-id="f4eff-107">**型**</span><span class="sxs-lookup"><span data-stu-id="f4eff-107">**Type**</span></span>|<span data-ttu-id="f4eff-108">**説明**</span><span class="sxs-lookup"><span data-stu-id="f4eff-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="f4eff-109">valueID</span><span class="sxs-lookup"><span data-stu-id="f4eff-109">valueID</span></span>  <br/> |<span data-ttu-id="f4eff-110">smallint、null でないです。</span><span class="sxs-lookup"><span data-stu-id="f4eff-110">smallint, not null</span></span>  <br/> |<span data-ttu-id="f4eff-111">値の ID です。</span><span class="sxs-lookup"><span data-stu-id="f4eff-111">ID of the value.</span></span>  <br/> |
|<span data-ttu-id="f4eff-112">attributeID</span><span class="sxs-lookup"><span data-stu-id="f4eff-112">attributeID</span></span>  <br/> |<span data-ttu-id="f4eff-113">smallint、null でないです。</span><span class="sxs-lookup"><span data-stu-id="f4eff-113">smallint, not null</span></span>  <br/> |<span data-ttu-id="f4eff-114">属性の ID です。</span><span class="sxs-lookup"><span data-stu-id="f4eff-114">ID of the attribute.</span></span>  <br/> |
|<span data-ttu-id="f4eff-115">attributeValue</span><span class="sxs-lookup"><span data-stu-id="f4eff-115">attributeValue</span></span>  <br/> |<span data-ttu-id="f4eff-116">nvarchar (256)、null でないです。</span><span class="sxs-lookup"><span data-stu-id="f4eff-116">nvarchar (256), not null</span></span>  <br/> |<span data-ttu-id="f4eff-117">値の名前です。</span><span class="sxs-lookup"><span data-stu-id="f4eff-117">Name of the value.</span></span>  <br/> |
   
<span data-ttu-id="f4eff-118">**キー**</span><span class="sxs-lookup"><span data-stu-id="f4eff-118">**Keys**</span></span>

|<span data-ttu-id="f4eff-119">**列**</span><span class="sxs-lookup"><span data-stu-id="f4eff-119">**Column**</span></span>|<span data-ttu-id="f4eff-120">**説明**</span><span class="sxs-lookup"><span data-stu-id="f4eff-120">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="f4eff-121">valueID</span><span class="sxs-lookup"><span data-stu-id="f4eff-121">valueID</span></span>  <br/> |<span data-ttu-id="f4eff-122">プライマリ ・ キーです。</span><span class="sxs-lookup"><span data-stu-id="f4eff-122">Primary key.</span></span>  <br/> |
|<span data-ttu-id="f4eff-123">attributeID</span><span class="sxs-lookup"><span data-stu-id="f4eff-123">attributeID</span></span>  <br/> |<span data-ttu-id="f4eff-124">TblEnumAttribute.attributeID テーブル内の参照と外部キーです。</span><span class="sxs-lookup"><span data-stu-id="f4eff-124">Foreign key with lookup in tblEnumAttribute.attributeID table.</span></span>  <br/> |
   
<span data-ttu-id="f4eff-125">**テーブルの値**</span><span class="sxs-lookup"><span data-stu-id="f4eff-125">**Table Values**</span></span>

|<span data-ttu-id="f4eff-126">**valueID**</span><span class="sxs-lookup"><span data-stu-id="f4eff-126">**valueID**</span></span>|<span data-ttu-id="f4eff-127">**attributeID**</span><span class="sxs-lookup"><span data-stu-id="f4eff-127">**attributeID**</span></span>|<span data-ttu-id="f4eff-128">**attributeValue**</span><span class="sxs-lookup"><span data-stu-id="f4eff-128">**attributeValue**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="f4eff-129">2</span><span class="sxs-lookup"><span data-stu-id="f4eff-129">2</span></span>  <br/> |<span data-ttu-id="f4eff-130">1</span><span class="sxs-lookup"><span data-stu-id="f4eff-130">1</span></span>  <br/> |<span data-ttu-id="f4eff-131">private</span><span class="sxs-lookup"><span data-stu-id="f4eff-131">private</span></span>  <br/> |
|<span data-ttu-id="f4eff-132">3</span><span class="sxs-lookup"><span data-stu-id="f4eff-132">3</span></span>  <br/> |<span data-ttu-id="f4eff-133">1</span><span class="sxs-lookup"><span data-stu-id="f4eff-133">1</span></span>  <br/> |<span data-ttu-id="f4eff-134">スコープ</span><span class="sxs-lookup"><span data-stu-id="f4eff-134">scope</span></span>  <br/> |
|<span data-ttu-id="f4eff-135">4</span><span class="sxs-lookup"><span data-stu-id="f4eff-135">4</span></span>  <br/> |<span data-ttu-id="f4eff-136">2</span><span class="sxs-lookup"><span data-stu-id="f4eff-136">2</span></span>  <br/> |<span data-ttu-id="f4eff-137">通常</span><span class="sxs-lookup"><span data-stu-id="f4eff-137">normal</span></span>  <br/> |
|<span data-ttu-id="f4eff-138">5</span><span class="sxs-lookup"><span data-stu-id="f4eff-138">5</span></span>  <br/> |<span data-ttu-id="f4eff-139">2</span><span class="sxs-lookup"><span data-stu-id="f4eff-139">2</span></span>  <br/> |<span data-ttu-id="f4eff-140">聴衆</span><span class="sxs-lookup"><span data-stu-id="f4eff-140">auditorium</span></span>  <br/> |
|<span data-ttu-id="f4eff-141">6</span><span class="sxs-lookup"><span data-stu-id="f4eff-141">6</span></span>  <br/> |<span data-ttu-id="f4eff-142">1</span><span class="sxs-lookup"><span data-stu-id="f4eff-142">1</span></span>  <br/> |<span data-ttu-id="f4eff-143">開く</span><span class="sxs-lookup"><span data-stu-id="f4eff-143">open</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="f4eff-144">関連項目</span><span class="sxs-lookup"><span data-stu-id="f4eff-144">See also</span></span>

[<span data-ttu-id="f4eff-145">tblNode</span><span class="sxs-lookup"><span data-stu-id="f4eff-145">tblNode</span></span>](tblnode.md)
