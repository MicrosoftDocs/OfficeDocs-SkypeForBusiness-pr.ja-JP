---
title: tblEnumValue
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
ms.assetid: a33df20c-d19d-4f5c-b012-29dab8fb9200
description: tblEnumValue は、ノード テーブルで使われる属性の Visibility (表示設定) 値と Behavior (動作) 値を含む、ハードコードされたテーブルです。
ms.openlocfilehash: a13bfbe79d1eb118f0727f390816a26d35a508d0
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49816027"
---
# <a name="tblenumvalue"></a><span data-ttu-id="e3880-103">tblEnumValue</span><span class="sxs-lookup"><span data-stu-id="e3880-103">tblEnumValue</span></span>
 
<span data-ttu-id="e3880-104">tblEnumValue は、ノード テーブルで使われる属性の Visibility (表示設定) 値と Behavior (動作) 値を含む、ハードコードされたテーブルです。</span><span class="sxs-lookup"><span data-stu-id="e3880-104">tblEnumValue is a hardcoded table that contains the Visibility and Behavior values of the attributes that are used in the Node table.</span></span>
  
<span data-ttu-id="e3880-105">**Columns**</span><span class="sxs-lookup"><span data-stu-id="e3880-105">**Columns**</span></span>

|<span data-ttu-id="e3880-106">**列**</span><span class="sxs-lookup"><span data-stu-id="e3880-106">**Column**</span></span>|<span data-ttu-id="e3880-107">**型**</span><span class="sxs-lookup"><span data-stu-id="e3880-107">**Type**</span></span>|<span data-ttu-id="e3880-108">**説明**</span><span class="sxs-lookup"><span data-stu-id="e3880-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="e3880-109">valueID</span><span class="sxs-lookup"><span data-stu-id="e3880-109">valueID</span></span>  <br/> |<span data-ttu-id="e3880-110">NULL でない smallint</span><span class="sxs-lookup"><span data-stu-id="e3880-110">smallint, not null</span></span>  <br/> |<span data-ttu-id="e3880-111">値の ID。</span><span class="sxs-lookup"><span data-stu-id="e3880-111">ID of the value.</span></span>  <br/> |
|<span data-ttu-id="e3880-112">attributeID</span><span class="sxs-lookup"><span data-stu-id="e3880-112">attributeID</span></span>  <br/> |<span data-ttu-id="e3880-113">NULL でない smallint</span><span class="sxs-lookup"><span data-stu-id="e3880-113">smallint, not null</span></span>  <br/> |<span data-ttu-id="e3880-114">属性の ID。</span><span class="sxs-lookup"><span data-stu-id="e3880-114">ID of the attribute.</span></span>  <br/> |
|<span data-ttu-id="e3880-115">attributeValue</span><span class="sxs-lookup"><span data-stu-id="e3880-115">attributeValue</span></span>  <br/> |<span data-ttu-id="e3880-116">NULL でない nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="e3880-116">nvarchar (256), not null</span></span>  <br/> |<span data-ttu-id="e3880-117">値の名前。</span><span class="sxs-lookup"><span data-stu-id="e3880-117">Name of the value.</span></span>  <br/> |
   
<span data-ttu-id="e3880-118">**Keys**</span><span class="sxs-lookup"><span data-stu-id="e3880-118">**Keys**</span></span>

|<span data-ttu-id="e3880-119">**列**</span><span class="sxs-lookup"><span data-stu-id="e3880-119">**Column**</span></span>|<span data-ttu-id="e3880-120">**説明**</span><span class="sxs-lookup"><span data-stu-id="e3880-120">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="e3880-121">valueID</span><span class="sxs-lookup"><span data-stu-id="e3880-121">valueID</span></span>  <br/> |<span data-ttu-id="e3880-122">主キー。</span><span class="sxs-lookup"><span data-stu-id="e3880-122">Primary key.</span></span>  <br/> |
|<span data-ttu-id="e3880-123">attributeID</span><span class="sxs-lookup"><span data-stu-id="e3880-123">attributeID</span></span>  <br/> |<span data-ttu-id="e3880-124">tblEnumAttribute.attributeID テーブルを参照する外部キー。</span><span class="sxs-lookup"><span data-stu-id="e3880-124">Foreign key with lookup in tblEnumAttribute.attributeID table.</span></span>  <br/> |
   
<span data-ttu-id="e3880-125">**テーブル値**</span><span class="sxs-lookup"><span data-stu-id="e3880-125">**Table Values**</span></span>

|<span data-ttu-id="e3880-126">**valueID**</span><span class="sxs-lookup"><span data-stu-id="e3880-126">**valueID**</span></span>|<span data-ttu-id="e3880-127">**attributeID**</span><span class="sxs-lookup"><span data-stu-id="e3880-127">**attributeID**</span></span>|<span data-ttu-id="e3880-128">**attributeValue**</span><span class="sxs-lookup"><span data-stu-id="e3880-128">**attributeValue**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="e3880-129">2 </span><span class="sxs-lookup"><span data-stu-id="e3880-129">2</span></span>  <br/> |<span data-ttu-id="e3880-130">1 </span><span class="sxs-lookup"><span data-stu-id="e3880-130">1</span></span>  <br/> |<span data-ttu-id="e3880-131">private</span><span class="sxs-lookup"><span data-stu-id="e3880-131">private</span></span>  <br/> |
|<span data-ttu-id="e3880-132">3 </span><span class="sxs-lookup"><span data-stu-id="e3880-132">3</span></span>  <br/> |<span data-ttu-id="e3880-133">1 </span><span class="sxs-lookup"><span data-stu-id="e3880-133">1</span></span>  <br/> |<span data-ttu-id="e3880-134">scope</span><span class="sxs-lookup"><span data-stu-id="e3880-134">scope</span></span>  <br/> |
|<span data-ttu-id="e3880-135">4 </span><span class="sxs-lookup"><span data-stu-id="e3880-135">4</span></span>  <br/> |<span data-ttu-id="e3880-136">2 </span><span class="sxs-lookup"><span data-stu-id="e3880-136">2</span></span>  <br/> |<span data-ttu-id="e3880-137">normal</span><span class="sxs-lookup"><span data-stu-id="e3880-137">normal</span></span>  <br/> |
|<span data-ttu-id="e3880-138">5 </span><span class="sxs-lookup"><span data-stu-id="e3880-138">5</span></span>  <br/> |<span data-ttu-id="e3880-139">2 </span><span class="sxs-lookup"><span data-stu-id="e3880-139">2</span></span>  <br/> |<span data-ttu-id="e3880-140">講堂</span><span class="sxs-lookup"><span data-stu-id="e3880-140">auditorium</span></span>  <br/> |
|<span data-ttu-id="e3880-141">6 </span><span class="sxs-lookup"><span data-stu-id="e3880-141">6</span></span>  <br/> |<span data-ttu-id="e3880-142">1 </span><span class="sxs-lookup"><span data-stu-id="e3880-142">1</span></span>  <br/> |<span data-ttu-id="e3880-143">open</span><span class="sxs-lookup"><span data-stu-id="e3880-143">open</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="e3880-144">関連項目</span><span class="sxs-lookup"><span data-stu-id="e3880-144">See also</span></span>

[<span data-ttu-id="e3880-145">tblNode</span><span class="sxs-lookup"><span data-stu-id="e3880-145">tblNode</span></span>](tblnode.md)
