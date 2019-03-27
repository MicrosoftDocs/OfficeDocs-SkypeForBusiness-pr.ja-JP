---
title: tblEnumAttribute
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 17f8b87e-36a6-4f6a-8630-7c76b61a7595
description: tblEnumAttribute は、Node テーブルで使用されている可視性と動作の属性を含むハードコーディングされたテーブルです。
ms.openlocfilehash: 7555656f02fa7808e54100c03de8f80e0e078678
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/27/2019
ms.locfileid: "30879701"
---
# <a name="tblenumattribute"></a><span data-ttu-id="1c68a-103">tblEnumAttribute</span><span class="sxs-lookup"><span data-stu-id="1c68a-103">tblEnumAttribute</span></span>
 
<span data-ttu-id="1c68a-104">tblEnumAttribute は、Node テーブルで使用されている可視性と動作の属性を含むハードコーディングされたテーブルです。</span><span class="sxs-lookup"><span data-stu-id="1c68a-104">tblEnumAttribute is a hardcoded table that contains the Visibility and Behavior attributes that are used in the Node table.</span></span>
  
<span data-ttu-id="1c68a-105">**列**</span><span class="sxs-lookup"><span data-stu-id="1c68a-105">**Columns**</span></span>

|<span data-ttu-id="1c68a-106">**列**</span><span class="sxs-lookup"><span data-stu-id="1c68a-106">**Column**</span></span>|<span data-ttu-id="1c68a-107">**型**</span><span class="sxs-lookup"><span data-stu-id="1c68a-107">**Type**</span></span>|<span data-ttu-id="1c68a-108">**説明**</span><span class="sxs-lookup"><span data-stu-id="1c68a-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="1c68a-109">attributeID</span><span class="sxs-lookup"><span data-stu-id="1c68a-109">attributeID</span></span>  <br/> |<span data-ttu-id="1c68a-110">smallint、null でないです。</span><span class="sxs-lookup"><span data-stu-id="1c68a-110">smallint, not null</span></span>  <br/> |<span data-ttu-id="1c68a-111">属性の ID です。</span><span class="sxs-lookup"><span data-stu-id="1c68a-111">ID of the attribute.</span></span>  <br/> |
|<span data-ttu-id="1c68a-112">attributeName</span><span class="sxs-lookup"><span data-stu-id="1c68a-112">attributeName</span></span>  <br/> |<span data-ttu-id="1c68a-113">nvarchar (256)、null でないです。</span><span class="sxs-lookup"><span data-stu-id="1c68a-113">nvarchar (256), not null</span></span>  <br/> |<span data-ttu-id="1c68a-114">属性の名前です。</span><span class="sxs-lookup"><span data-stu-id="1c68a-114">Name of the attribute.</span></span>  <br/> |
   
<span data-ttu-id="1c68a-115">**キー**</span><span class="sxs-lookup"><span data-stu-id="1c68a-115">**Key**</span></span>

|<span data-ttu-id="1c68a-116">**列**</span><span class="sxs-lookup"><span data-stu-id="1c68a-116">**Column**</span></span>|<span data-ttu-id="1c68a-117">**説明**</span><span class="sxs-lookup"><span data-stu-id="1c68a-117">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="1c68a-118">attributeID</span><span class="sxs-lookup"><span data-stu-id="1c68a-118">attributeID</span></span>  <br/> |<span data-ttu-id="1c68a-119">プライマリ ・ キーです。</span><span class="sxs-lookup"><span data-stu-id="1c68a-119">Primary key.</span></span>  <br/> |
   
<span data-ttu-id="1c68a-120">**テーブルの値**</span><span class="sxs-lookup"><span data-stu-id="1c68a-120">**Table Values**</span></span>

|<span data-ttu-id="1c68a-121">**attributeID**</span><span class="sxs-lookup"><span data-stu-id="1c68a-121">**attributeID**</span></span>|<span data-ttu-id="1c68a-122">**attributeName**</span><span class="sxs-lookup"><span data-stu-id="1c68a-122">**attributeName**</span></span>|
|:-----|:-----|
|<span data-ttu-id="1c68a-123">1</span><span class="sxs-lookup"><span data-stu-id="1c68a-123">1</span></span>  <br/> |<span data-ttu-id="1c68a-124">表示/非表示にします。</span><span class="sxs-lookup"><span data-stu-id="1c68a-124">Visibility.</span></span>  <br/> |
|<span data-ttu-id="1c68a-125">2</span><span class="sxs-lookup"><span data-stu-id="1c68a-125">2</span></span>  <br/> |<span data-ttu-id="1c68a-126">動作します。</span><span class="sxs-lookup"><span data-stu-id="1c68a-126">Behavior.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="1c68a-127">関連項目</span><span class="sxs-lookup"><span data-stu-id="1c68a-127">See also</span></span>

[<span data-ttu-id="1c68a-128">tblNode</span><span class="sxs-lookup"><span data-stu-id="1c68a-128">tblNode</span></span>](tblnode.md)
