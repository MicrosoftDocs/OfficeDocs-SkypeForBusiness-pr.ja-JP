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
localization_priority: Normal
ms.assetid: a33df20c-d19d-4f5c-b012-29dab8fb9200
description: tblEnumValue は、ノードテーブルで使用されている属性の可視性と動作の値を含む、ハードコーディングされた表です。
ms.openlocfilehash: bf1ddf75fc7b7fd78c85f47626b465a4d74e5ca2
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2019
ms.locfileid: "34295427"
---
# <a name="tblenumvalue"></a><span data-ttu-id="bdf16-103">tblEnumValue</span><span class="sxs-lookup"><span data-stu-id="bdf16-103">tblEnumValue</span></span>
 
<span data-ttu-id="bdf16-104">tblEnumValue は、ノードテーブルで使用されている属性の可視性と動作の値を含む、ハードコーディングされた表です。</span><span class="sxs-lookup"><span data-stu-id="bdf16-104">tblEnumValue is a hardcoded table that contains the Visibility and Behavior values of the attributes that are used in the Node table.</span></span>
  
<span data-ttu-id="bdf16-105">**行**</span><span class="sxs-lookup"><span data-stu-id="bdf16-105">**Columns**</span></span>

|<span data-ttu-id="bdf16-106">**列**</span><span class="sxs-lookup"><span data-stu-id="bdf16-106">**Column**</span></span>|<span data-ttu-id="bdf16-107">**型**</span><span class="sxs-lookup"><span data-stu-id="bdf16-107">**Type**</span></span>|<span data-ttu-id="bdf16-108">**説明**</span><span class="sxs-lookup"><span data-stu-id="bdf16-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="bdf16-109">valueID</span><span class="sxs-lookup"><span data-stu-id="bdf16-109">valueID</span></span>  <br/> |<span data-ttu-id="bdf16-110">smallint (null ではない)</span><span class="sxs-lookup"><span data-stu-id="bdf16-110">smallint, not null</span></span>  <br/> |<span data-ttu-id="bdf16-111">値の ID です。</span><span class="sxs-lookup"><span data-stu-id="bdf16-111">ID of the value.</span></span>  <br/> |
|<span data-ttu-id="bdf16-112">attributeID</span><span class="sxs-lookup"><span data-stu-id="bdf16-112">attributeID</span></span>  <br/> |<span data-ttu-id="bdf16-113">smallint (null ではない)</span><span class="sxs-lookup"><span data-stu-id="bdf16-113">smallint, not null</span></span>  <br/> |<span data-ttu-id="bdf16-114">属性の ID です。</span><span class="sxs-lookup"><span data-stu-id="bdf16-114">ID of the attribute.</span></span>  <br/> |
|<span data-ttu-id="bdf16-115">attributeValue</span><span class="sxs-lookup"><span data-stu-id="bdf16-115">attributeValue</span></span>  <br/> |<span data-ttu-id="bdf16-116">nvarchar (256)、null ではない</span><span class="sxs-lookup"><span data-stu-id="bdf16-116">nvarchar (256), not null</span></span>  <br/> |<span data-ttu-id="bdf16-117">値の名前。</span><span class="sxs-lookup"><span data-stu-id="bdf16-117">Name of the value.</span></span>  <br/> |
   
<span data-ttu-id="bdf16-118">**機能**</span><span class="sxs-lookup"><span data-stu-id="bdf16-118">**Keys**</span></span>

|<span data-ttu-id="bdf16-119">**列**</span><span class="sxs-lookup"><span data-stu-id="bdf16-119">**Column**</span></span>|<span data-ttu-id="bdf16-120">**説明**</span><span class="sxs-lookup"><span data-stu-id="bdf16-120">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="bdf16-121">valueID</span><span class="sxs-lookup"><span data-stu-id="bdf16-121">valueID</span></span>  <br/> |<span data-ttu-id="bdf16-122">主キー。</span><span class="sxs-lookup"><span data-stu-id="bdf16-122">Primary key.</span></span>  <br/> |
|<span data-ttu-id="bdf16-123">attributeID</span><span class="sxs-lookup"><span data-stu-id="bdf16-123">attributeID</span></span>  <br/> |<span data-ttu-id="bdf16-124">TblEnumAttribute テーブルで参照する外部キー</span><span class="sxs-lookup"><span data-stu-id="bdf16-124">Foreign key with lookup in tblEnumAttribute.attributeID table.</span></span>  <br/> |
   
<span data-ttu-id="bdf16-125">**テーブルの値**</span><span class="sxs-lookup"><span data-stu-id="bdf16-125">**Table Values**</span></span>

|<span data-ttu-id="bdf16-126">**valueID**</span><span class="sxs-lookup"><span data-stu-id="bdf16-126">**valueID**</span></span>|<span data-ttu-id="bdf16-127">**attributeID**</span><span class="sxs-lookup"><span data-stu-id="bdf16-127">**attributeID**</span></span>|<span data-ttu-id="bdf16-128">**attributeValue**</span><span class="sxs-lookup"><span data-stu-id="bdf16-128">**attributeValue**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="bdf16-129">2</span><span class="sxs-lookup"><span data-stu-id="bdf16-129">2</span></span>  <br/> |<span data-ttu-id="bdf16-130">1</span><span class="sxs-lookup"><span data-stu-id="bdf16-130">1</span></span>  <br/> |<span data-ttu-id="bdf16-131">private</span><span class="sxs-lookup"><span data-stu-id="bdf16-131">private</span></span>  <br/> |
|<span data-ttu-id="bdf16-132">3</span><span class="sxs-lookup"><span data-stu-id="bdf16-132">3</span></span>  <br/> |<span data-ttu-id="bdf16-133">1</span><span class="sxs-lookup"><span data-stu-id="bdf16-133">1</span></span>  <br/> |<span data-ttu-id="bdf16-134">種類</span><span class="sxs-lookup"><span data-stu-id="bdf16-134">scope</span></span>  <br/> |
|<span data-ttu-id="bdf16-135">4</span><span class="sxs-lookup"><span data-stu-id="bdf16-135">4</span></span>  <br/> |<span data-ttu-id="bdf16-136">2</span><span class="sxs-lookup"><span data-stu-id="bdf16-136">2</span></span>  <br/> |<span data-ttu-id="bdf16-137">標準</span><span class="sxs-lookup"><span data-stu-id="bdf16-137">normal</span></span>  <br/> |
|<span data-ttu-id="bdf16-138">5</span><span class="sxs-lookup"><span data-stu-id="bdf16-138">5</span></span>  <br/> |<span data-ttu-id="bdf16-139">2</span><span class="sxs-lookup"><span data-stu-id="bdf16-139">2</span></span>  <br/> |<span data-ttu-id="bdf16-140">大</span><span class="sxs-lookup"><span data-stu-id="bdf16-140">auditorium</span></span>  <br/> |
|<span data-ttu-id="bdf16-141">6</span><span class="sxs-lookup"><span data-stu-id="bdf16-141">6</span></span>  <br/> |<span data-ttu-id="bdf16-142">1</span><span class="sxs-lookup"><span data-stu-id="bdf16-142">1</span></span>  <br/> |<span data-ttu-id="bdf16-143">開こう</span><span class="sxs-lookup"><span data-stu-id="bdf16-143">open</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="bdf16-144">関連項目</span><span class="sxs-lookup"><span data-stu-id="bdf16-144">See also</span></span>

[<span data-ttu-id="bdf16-145">tblNode</span><span class="sxs-lookup"><span data-stu-id="bdf16-145">tblNode</span></span>](tblnode.md)
