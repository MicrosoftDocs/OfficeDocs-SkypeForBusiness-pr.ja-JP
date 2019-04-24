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
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "32212594"
---
# <a name="tblenumattribute"></a><span data-ttu-id="4c07e-103">tblEnumAttribute</span><span class="sxs-lookup"><span data-stu-id="4c07e-103">tblEnumAttribute</span></span>
 
<span data-ttu-id="4c07e-104">tblEnumAttribute は、Node テーブルで使用されている可視性と動作の属性を含むハードコーディングされたテーブルです。</span><span class="sxs-lookup"><span data-stu-id="4c07e-104">tblEnumAttribute is a hardcoded table that contains the Visibility and Behavior attributes that are used in the Node table.</span></span>
  
<span data-ttu-id="4c07e-105">**列**</span><span class="sxs-lookup"><span data-stu-id="4c07e-105">**Columns**</span></span>

|<span data-ttu-id="4c07e-106">**列**</span><span class="sxs-lookup"><span data-stu-id="4c07e-106">**Column**</span></span>|<span data-ttu-id="4c07e-107">**型**</span><span class="sxs-lookup"><span data-stu-id="4c07e-107">**Type**</span></span>|<span data-ttu-id="4c07e-108">**説明**</span><span class="sxs-lookup"><span data-stu-id="4c07e-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="4c07e-109">attributeID</span><span class="sxs-lookup"><span data-stu-id="4c07e-109">attributeID</span></span>  <br/> |<span data-ttu-id="4c07e-110">smallint、null でないです。</span><span class="sxs-lookup"><span data-stu-id="4c07e-110">smallint, not null</span></span>  <br/> |<span data-ttu-id="4c07e-111">属性の ID です。</span><span class="sxs-lookup"><span data-stu-id="4c07e-111">ID of the attribute.</span></span>  <br/> |
|<span data-ttu-id="4c07e-112">attributeName</span><span class="sxs-lookup"><span data-stu-id="4c07e-112">attributeName</span></span>  <br/> |<span data-ttu-id="4c07e-113">nvarchar (256)、null でないです。</span><span class="sxs-lookup"><span data-stu-id="4c07e-113">nvarchar (256), not null</span></span>  <br/> |<span data-ttu-id="4c07e-114">属性の名前です。</span><span class="sxs-lookup"><span data-stu-id="4c07e-114">Name of the attribute.</span></span>  <br/> |
   
<span data-ttu-id="4c07e-115">**キー**</span><span class="sxs-lookup"><span data-stu-id="4c07e-115">**Key**</span></span>

|<span data-ttu-id="4c07e-116">**列**</span><span class="sxs-lookup"><span data-stu-id="4c07e-116">**Column**</span></span>|<span data-ttu-id="4c07e-117">**説明**</span><span class="sxs-lookup"><span data-stu-id="4c07e-117">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="4c07e-118">attributeID</span><span class="sxs-lookup"><span data-stu-id="4c07e-118">attributeID</span></span>  <br/> |<span data-ttu-id="4c07e-119">プライマリ ・ キーです。</span><span class="sxs-lookup"><span data-stu-id="4c07e-119">Primary key.</span></span>  <br/> |
   
<span data-ttu-id="4c07e-120">**テーブルの値**</span><span class="sxs-lookup"><span data-stu-id="4c07e-120">**Table Values**</span></span>

|<span data-ttu-id="4c07e-121">**attributeID**</span><span class="sxs-lookup"><span data-stu-id="4c07e-121">**attributeID**</span></span>|<span data-ttu-id="4c07e-122">**attributeName**</span><span class="sxs-lookup"><span data-stu-id="4c07e-122">**attributeName**</span></span>|
|:-----|:-----|
|<span data-ttu-id="4c07e-123">1</span><span class="sxs-lookup"><span data-stu-id="4c07e-123">1</span></span>  <br/> |<span data-ttu-id="4c07e-124">表示/非表示にします。</span><span class="sxs-lookup"><span data-stu-id="4c07e-124">Visibility.</span></span>  <br/> |
|<span data-ttu-id="4c07e-125">2</span><span class="sxs-lookup"><span data-stu-id="4c07e-125">2</span></span>  <br/> |<span data-ttu-id="4c07e-126">動作します。</span><span class="sxs-lookup"><span data-stu-id="4c07e-126">Behavior.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="4c07e-127">関連項目</span><span class="sxs-lookup"><span data-stu-id="4c07e-127">See also</span></span>

[<span data-ttu-id="4c07e-128">tblNode</span><span class="sxs-lookup"><span data-stu-id="4c07e-128">tblNode</span></span>](tblnode.md)
