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
ms.openlocfilehash: 4e17e5fc167342c106e7b5354d90c7fc284785c3
ms.sourcegitcommit: b14cfca231b618ec28cf9f4efe11cb3e8aceb34b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/19/2018
ms.locfileid: "19505077"
---
# <a name="tblenumvalue"></a><span data-ttu-id="1a543-103">tblEnumValue</span><span class="sxs-lookup"><span data-stu-id="1a543-103">tblEnumValue</span></span>
 
<span data-ttu-id="1a543-104">tblEnumValue は、Node テーブルで使用されている属性の表示/非表示と動作の値を含むハードコーディングされたテーブルです。</span><span class="sxs-lookup"><span data-stu-id="1a543-104">tblEnumValue is a hardcoded table that contains the Visibility and Behavior values of the attributes that are used in the Node table.</span></span>
  
<span data-ttu-id="1a543-105">**列**</span><span class="sxs-lookup"><span data-stu-id="1a543-105">**Columns**</span></span>

|<span data-ttu-id="1a543-106">**列**</span><span class="sxs-lookup"><span data-stu-id="1a543-106">**Column**</span></span>|<span data-ttu-id="1a543-107">**種類**</span><span class="sxs-lookup"><span data-stu-id="1a543-107">**Type**</span></span>|<span data-ttu-id="1a543-108">**説明**</span><span class="sxs-lookup"><span data-stu-id="1a543-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="1a543-109">valueID</span><span class="sxs-lookup"><span data-stu-id="1a543-109">valueID</span></span>  <br/> |<span data-ttu-id="1a543-110">smallint、null でないです。</span><span class="sxs-lookup"><span data-stu-id="1a543-110">smallint, not null</span></span>  <br/> |<span data-ttu-id="1a543-111">値の ID です。</span><span class="sxs-lookup"><span data-stu-id="1a543-111">ID of the value.</span></span>  <br/> |
|<span data-ttu-id="1a543-112">attributeID</span><span class="sxs-lookup"><span data-stu-id="1a543-112">attributeID</span></span>  <br/> |<span data-ttu-id="1a543-113">smallint、null でないです。</span><span class="sxs-lookup"><span data-stu-id="1a543-113">smallint, not null</span></span>  <br/> |<span data-ttu-id="1a543-114">属性の ID です。</span><span class="sxs-lookup"><span data-stu-id="1a543-114">ID of the attribute.</span></span>  <br/> |
|<span data-ttu-id="1a543-115">attributeValue</span><span class="sxs-lookup"><span data-stu-id="1a543-115">attributeValue</span></span>  <br/> |<span data-ttu-id="1a543-116">nvarchar (256)、null でないです。</span><span class="sxs-lookup"><span data-stu-id="1a543-116">nvarchar (256), not null</span></span>  <br/> |<span data-ttu-id="1a543-117">値の名前です。</span><span class="sxs-lookup"><span data-stu-id="1a543-117">Name of the value.</span></span>  <br/> |
   
<span data-ttu-id="1a543-118">**キー**</span><span class="sxs-lookup"><span data-stu-id="1a543-118">**Keys**</span></span>

|<span data-ttu-id="1a543-119">**列**</span><span class="sxs-lookup"><span data-stu-id="1a543-119">**Column**</span></span>|<span data-ttu-id="1a543-120">**説明**</span><span class="sxs-lookup"><span data-stu-id="1a543-120">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="1a543-121">valueID</span><span class="sxs-lookup"><span data-stu-id="1a543-121">valueID</span></span>  <br/> |<span data-ttu-id="1a543-122">プライマリ ・ キーです。</span><span class="sxs-lookup"><span data-stu-id="1a543-122">Primary key.</span></span>  <br/> |
|<span data-ttu-id="1a543-123">attributeID</span><span class="sxs-lookup"><span data-stu-id="1a543-123">attributeID</span></span>  <br/> |<span data-ttu-id="1a543-124">TblEnumAttribute.attributeID テーブル内の参照と外部キーです。</span><span class="sxs-lookup"><span data-stu-id="1a543-124">Foreign key with lookup in tblEnumAttribute.attributeID table.</span></span>  <br/> |
   
<span data-ttu-id="1a543-125">**テーブルの値**</span><span class="sxs-lookup"><span data-stu-id="1a543-125">**Table Values**</span></span>

|<span data-ttu-id="1a543-126">**valueID**</span><span class="sxs-lookup"><span data-stu-id="1a543-126">**valueID**</span></span>|<span data-ttu-id="1a543-127">**attributeID**</span><span class="sxs-lookup"><span data-stu-id="1a543-127">**attributeID**</span></span>|<span data-ttu-id="1a543-128">**attributeValue**</span><span class="sxs-lookup"><span data-stu-id="1a543-128">**attributeValue**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="1a543-129">2</span><span class="sxs-lookup"><span data-stu-id="1a543-129">2</span></span>  <br/> |<span data-ttu-id="1a543-130">1</span><span class="sxs-lookup"><span data-stu-id="1a543-130">1</span></span>  <br/> |<span data-ttu-id="1a543-131">private</span><span class="sxs-lookup"><span data-stu-id="1a543-131">private</span></span>  <br/> |
|<span data-ttu-id="1a543-132">3</span><span class="sxs-lookup"><span data-stu-id="1a543-132">3</span></span>  <br/> |<span data-ttu-id="1a543-133">1</span><span class="sxs-lookup"><span data-stu-id="1a543-133">1</span></span>  <br/> |<span data-ttu-id="1a543-134">スコープ</span><span class="sxs-lookup"><span data-stu-id="1a543-134">scope</span></span>  <br/> |
|<span data-ttu-id="1a543-135">4</span><span class="sxs-lookup"><span data-stu-id="1a543-135">4</span></span>  <br/> |<span data-ttu-id="1a543-136">2</span><span class="sxs-lookup"><span data-stu-id="1a543-136">2</span></span>  <br/> |<span data-ttu-id="1a543-137">通常</span><span class="sxs-lookup"><span data-stu-id="1a543-137">normal</span></span>  <br/> |
|<span data-ttu-id="1a543-138">5</span><span class="sxs-lookup"><span data-stu-id="1a543-138">5</span></span>  <br/> |<span data-ttu-id="1a543-139">2</span><span class="sxs-lookup"><span data-stu-id="1a543-139">2</span></span>  <br/> |<span data-ttu-id="1a543-140">聴衆</span><span class="sxs-lookup"><span data-stu-id="1a543-140">auditorium</span></span>  <br/> |
|<span data-ttu-id="1a543-141">6</span><span class="sxs-lookup"><span data-stu-id="1a543-141">6</span></span>  <br/> |<span data-ttu-id="1a543-142">1</span><span class="sxs-lookup"><span data-stu-id="1a543-142">1</span></span>  <br/> |<span data-ttu-id="1a543-143">開く</span><span class="sxs-lookup"><span data-stu-id="1a543-143">open</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="1a543-144">関連項目</span><span class="sxs-lookup"><span data-stu-id="1a543-144">See also</span></span>

[<span data-ttu-id="1a543-145">tblNode</span><span class="sxs-lookup"><span data-stu-id="1a543-145">tblNode</span></span>](tblnode.md)