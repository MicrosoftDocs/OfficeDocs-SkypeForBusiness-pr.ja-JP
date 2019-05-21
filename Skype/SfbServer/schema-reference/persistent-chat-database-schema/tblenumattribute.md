---
title: tblEnumAttribute
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 17f8b87e-36a6-4f6a-8630-7c76b61a7595
description: tblEnumAttribute は、ノードテーブルで使用される Visibility 属性と Behavior 属性を含む、ハードコーディングされた表です。
ms.openlocfilehash: b326ebe98592daccf7560dc90e299f31c158cd5c
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2019
ms.locfileid: "34295420"
---
# <a name="tblenumattribute"></a><span data-ttu-id="607ed-103">tblEnumAttribute</span><span class="sxs-lookup"><span data-stu-id="607ed-103">tblEnumAttribute</span></span>
 
<span data-ttu-id="607ed-104">tblEnumAttribute は、ノードテーブルで使用される Visibility 属性と Behavior 属性を含む、ハードコーディングされた表です。</span><span class="sxs-lookup"><span data-stu-id="607ed-104">tblEnumAttribute is a hardcoded table that contains the Visibility and Behavior attributes that are used in the Node table.</span></span>
  
<span data-ttu-id="607ed-105">**行**</span><span class="sxs-lookup"><span data-stu-id="607ed-105">**Columns**</span></span>

|<span data-ttu-id="607ed-106">**列**</span><span class="sxs-lookup"><span data-stu-id="607ed-106">**Column**</span></span>|<span data-ttu-id="607ed-107">**型**</span><span class="sxs-lookup"><span data-stu-id="607ed-107">**Type**</span></span>|<span data-ttu-id="607ed-108">**説明**</span><span class="sxs-lookup"><span data-stu-id="607ed-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="607ed-109">attributeID</span><span class="sxs-lookup"><span data-stu-id="607ed-109">attributeID</span></span>  <br/> |<span data-ttu-id="607ed-110">smallint (null ではない)</span><span class="sxs-lookup"><span data-stu-id="607ed-110">smallint, not null</span></span>  <br/> |<span data-ttu-id="607ed-111">属性の ID です。</span><span class="sxs-lookup"><span data-stu-id="607ed-111">ID of the attribute.</span></span>  <br/> |
|<span data-ttu-id="607ed-112">attributeName</span><span class="sxs-lookup"><span data-stu-id="607ed-112">attributeName</span></span>  <br/> |<span data-ttu-id="607ed-113">nvarchar (256)、null ではない</span><span class="sxs-lookup"><span data-stu-id="607ed-113">nvarchar (256), not null</span></span>  <br/> |<span data-ttu-id="607ed-114">属性の名前。</span><span class="sxs-lookup"><span data-stu-id="607ed-114">Name of the attribute.</span></span>  <br/> |
   
<span data-ttu-id="607ed-115">**キー**</span><span class="sxs-lookup"><span data-stu-id="607ed-115">**Key**</span></span>

|<span data-ttu-id="607ed-116">**列**</span><span class="sxs-lookup"><span data-stu-id="607ed-116">**Column**</span></span>|<span data-ttu-id="607ed-117">**説明**</span><span class="sxs-lookup"><span data-stu-id="607ed-117">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="607ed-118">attributeID</span><span class="sxs-lookup"><span data-stu-id="607ed-118">attributeID</span></span>  <br/> |<span data-ttu-id="607ed-119">主キー。</span><span class="sxs-lookup"><span data-stu-id="607ed-119">Primary key.</span></span>  <br/> |
   
<span data-ttu-id="607ed-120">**テーブルの値**</span><span class="sxs-lookup"><span data-stu-id="607ed-120">**Table Values**</span></span>

|<span data-ttu-id="607ed-121">**attributeID**</span><span class="sxs-lookup"><span data-stu-id="607ed-121">**attributeID**</span></span>|<span data-ttu-id="607ed-122">**attributeName**</span><span class="sxs-lookup"><span data-stu-id="607ed-122">**attributeName**</span></span>|
|:-----|:-----|
|<span data-ttu-id="607ed-123">1</span><span class="sxs-lookup"><span data-stu-id="607ed-123">1</span></span>  <br/> |<span data-ttu-id="607ed-124">明確化.</span><span class="sxs-lookup"><span data-stu-id="607ed-124">Visibility.</span></span>  <br/> |
|<span data-ttu-id="607ed-125">2</span><span class="sxs-lookup"><span data-stu-id="607ed-125">2</span></span>  <br/> |<span data-ttu-id="607ed-126">状況.</span><span class="sxs-lookup"><span data-stu-id="607ed-126">Behavior.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="607ed-127">関連項目</span><span class="sxs-lookup"><span data-stu-id="607ed-127">See also</span></span>

[<span data-ttu-id="607ed-128">tblNode</span><span class="sxs-lookup"><span data-stu-id="607ed-128">tblNode</span></span>](tblnode.md)
