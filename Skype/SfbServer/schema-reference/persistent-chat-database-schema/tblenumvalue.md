---
title: tblEnumValue
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: a33df20c-d19d-4f5c-b012-29dab8fb9200
description: tblEnumValue は、ノードテーブルで使用されている属性の可視性と動作の値を含む、ハードコーディングされた表です。
ms.openlocfilehash: accb9cb4801984bd4b3839cd44e5b7feb8d06baa
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2020
ms.locfileid: "41814605"
---
# <a name="tblenumvalue"></a><span data-ttu-id="15415-103">tblEnumValue</span><span class="sxs-lookup"><span data-stu-id="15415-103">tblEnumValue</span></span>
 
<span data-ttu-id="15415-104">tblEnumValue は、ノードテーブルで使用されている属性の可視性と動作の値を含む、ハードコーディングされた表です。</span><span class="sxs-lookup"><span data-stu-id="15415-104">tblEnumValue is a hardcoded table that contains the Visibility and Behavior values of the attributes that are used in the Node table.</span></span>
  
<span data-ttu-id="15415-105">**行**</span><span class="sxs-lookup"><span data-stu-id="15415-105">**Columns**</span></span>

|<span data-ttu-id="15415-106">**列**</span><span class="sxs-lookup"><span data-stu-id="15415-106">**Column**</span></span>|<span data-ttu-id="15415-107">**種類**</span><span class="sxs-lookup"><span data-stu-id="15415-107">**Type**</span></span>|<span data-ttu-id="15415-108">**説明**</span><span class="sxs-lookup"><span data-stu-id="15415-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="15415-109">valueID</span><span class="sxs-lookup"><span data-stu-id="15415-109">valueID</span></span>  <br/> |<span data-ttu-id="15415-110">smallint (null ではない)</span><span class="sxs-lookup"><span data-stu-id="15415-110">smallint, not null</span></span>  <br/> |<span data-ttu-id="15415-111">値の ID です。</span><span class="sxs-lookup"><span data-stu-id="15415-111">ID of the value.</span></span>  <br/> |
|<span data-ttu-id="15415-112">attributeID</span><span class="sxs-lookup"><span data-stu-id="15415-112">attributeID</span></span>  <br/> |<span data-ttu-id="15415-113">smallint (null ではない)</span><span class="sxs-lookup"><span data-stu-id="15415-113">smallint, not null</span></span>  <br/> |<span data-ttu-id="15415-114">属性の ID です。</span><span class="sxs-lookup"><span data-stu-id="15415-114">ID of the attribute.</span></span>  <br/> |
|<span data-ttu-id="15415-115">attributeValue</span><span class="sxs-lookup"><span data-stu-id="15415-115">attributeValue</span></span>  <br/> |<span data-ttu-id="15415-116">nvarchar (256)、null ではない</span><span class="sxs-lookup"><span data-stu-id="15415-116">nvarchar (256), not null</span></span>  <br/> |<span data-ttu-id="15415-117">値の名前。</span><span class="sxs-lookup"><span data-stu-id="15415-117">Name of the value.</span></span>  <br/> |
   
<span data-ttu-id="15415-118">**機能**</span><span class="sxs-lookup"><span data-stu-id="15415-118">**Keys**</span></span>

|<span data-ttu-id="15415-119">**列**</span><span class="sxs-lookup"><span data-stu-id="15415-119">**Column**</span></span>|<span data-ttu-id="15415-120">**説明**</span><span class="sxs-lookup"><span data-stu-id="15415-120">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="15415-121">valueID</span><span class="sxs-lookup"><span data-stu-id="15415-121">valueID</span></span>  <br/> |<span data-ttu-id="15415-122">主キー。</span><span class="sxs-lookup"><span data-stu-id="15415-122">Primary key.</span></span>  <br/> |
|<span data-ttu-id="15415-123">attributeID</span><span class="sxs-lookup"><span data-stu-id="15415-123">attributeID</span></span>  <br/> |<span data-ttu-id="15415-124">TblEnumAttribute テーブルで参照する外部キー</span><span class="sxs-lookup"><span data-stu-id="15415-124">Foreign key with lookup in tblEnumAttribute.attributeID table.</span></span>  <br/> |
   
<span data-ttu-id="15415-125">**テーブルの値**</span><span class="sxs-lookup"><span data-stu-id="15415-125">**Table Values**</span></span>

|<span data-ttu-id="15415-126">**valueID**</span><span class="sxs-lookup"><span data-stu-id="15415-126">**valueID**</span></span>|<span data-ttu-id="15415-127">**attributeID**</span><span class="sxs-lookup"><span data-stu-id="15415-127">**attributeID**</span></span>|<span data-ttu-id="15415-128">**attributeValue**</span><span class="sxs-lookup"><span data-stu-id="15415-128">**attributeValue**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="15415-129">両面</span><span class="sxs-lookup"><span data-stu-id="15415-129">2</span></span>  <br/> |<span data-ttu-id="15415-130">1</span><span class="sxs-lookup"><span data-stu-id="15415-130">1</span></span>  <br/> |<span data-ttu-id="15415-131">private</span><span class="sxs-lookup"><span data-stu-id="15415-131">private</span></span>  <br/> |
|<span data-ttu-id="15415-132">3</span><span class="sxs-lookup"><span data-stu-id="15415-132">3</span></span>  <br/> |<span data-ttu-id="15415-133">1</span><span class="sxs-lookup"><span data-stu-id="15415-133">1</span></span>  <br/> |<span data-ttu-id="15415-134">種類</span><span class="sxs-lookup"><span data-stu-id="15415-134">scope</span></span>  <br/> |
|<span data-ttu-id="15415-135">4</span><span class="sxs-lookup"><span data-stu-id="15415-135">4</span></span>  <br/> |<span data-ttu-id="15415-136">両面</span><span class="sxs-lookup"><span data-stu-id="15415-136">2</span></span>  <br/> |<span data-ttu-id="15415-137">標準</span><span class="sxs-lookup"><span data-stu-id="15415-137">normal</span></span>  <br/> |
|<span data-ttu-id="15415-138">5</span><span class="sxs-lookup"><span data-stu-id="15415-138">5</span></span>  <br/> |<span data-ttu-id="15415-139">両面</span><span class="sxs-lookup"><span data-stu-id="15415-139">2</span></span>  <br/> |<span data-ttu-id="15415-140">大</span><span class="sxs-lookup"><span data-stu-id="15415-140">auditorium</span></span>  <br/> |
|<span data-ttu-id="15415-141">6</span><span class="sxs-lookup"><span data-stu-id="15415-141">6</span></span>  <br/> |<span data-ttu-id="15415-142">1</span><span class="sxs-lookup"><span data-stu-id="15415-142">1</span></span>  <br/> |<span data-ttu-id="15415-143">開こう</span><span class="sxs-lookup"><span data-stu-id="15415-143">open</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="15415-144">関連項目</span><span class="sxs-lookup"><span data-stu-id="15415-144">See also</span></span>

[<span data-ttu-id="15415-145">tblNode</span><span class="sxs-lookup"><span data-stu-id="15415-145">tblNode</span></span>](tblnode.md)
