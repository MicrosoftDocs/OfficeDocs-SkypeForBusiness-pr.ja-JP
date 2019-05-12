---
title: tblEnumAttribute
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 17f8b87e-36a6-4f6a-8630-7c76b61a7595
description: tblEnumAttribute は、Node テーブルで使用されている可視性と動作の属性を含むハードコーディングされたテーブルです。
ms.openlocfilehash: b81e8ae09561220df381290eed212ef752820edd
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "33929953"
---
# <a name="tblenumattribute"></a><span data-ttu-id="c183c-103">tblEnumAttribute</span><span class="sxs-lookup"><span data-stu-id="c183c-103">tblEnumAttribute</span></span>
 
<span data-ttu-id="c183c-104">tblEnumAttribute は、Node テーブルで使用されている可視性と動作の属性を含むハードコーディングされたテーブルです。</span><span class="sxs-lookup"><span data-stu-id="c183c-104">tblEnumAttribute is a hardcoded table that contains the Visibility and Behavior attributes that are used in the Node table.</span></span>
  
<span data-ttu-id="c183c-105">**列**</span><span class="sxs-lookup"><span data-stu-id="c183c-105">**Columns**</span></span>

|<span data-ttu-id="c183c-106">**列**</span><span class="sxs-lookup"><span data-stu-id="c183c-106">**Column**</span></span>|<span data-ttu-id="c183c-107">**型**</span><span class="sxs-lookup"><span data-stu-id="c183c-107">**Type**</span></span>|<span data-ttu-id="c183c-108">**説明**</span><span class="sxs-lookup"><span data-stu-id="c183c-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="c183c-109">attributeID</span><span class="sxs-lookup"><span data-stu-id="c183c-109">attributeID</span></span>  <br/> |<span data-ttu-id="c183c-110">smallint、null でないです。</span><span class="sxs-lookup"><span data-stu-id="c183c-110">smallint, not null</span></span>  <br/> |<span data-ttu-id="c183c-111">属性の ID です。</span><span class="sxs-lookup"><span data-stu-id="c183c-111">ID of the attribute.</span></span>  <br/> |
|<span data-ttu-id="c183c-112">attributeName</span><span class="sxs-lookup"><span data-stu-id="c183c-112">attributeName</span></span>  <br/> |<span data-ttu-id="c183c-113">nvarchar (256)、null でないです。</span><span class="sxs-lookup"><span data-stu-id="c183c-113">nvarchar (256), not null</span></span>  <br/> |<span data-ttu-id="c183c-114">属性の名前です。</span><span class="sxs-lookup"><span data-stu-id="c183c-114">Name of the attribute.</span></span>  <br/> |
   
<span data-ttu-id="c183c-115">**キー**</span><span class="sxs-lookup"><span data-stu-id="c183c-115">**Key**</span></span>

|<span data-ttu-id="c183c-116">**列**</span><span class="sxs-lookup"><span data-stu-id="c183c-116">**Column**</span></span>|<span data-ttu-id="c183c-117">**説明**</span><span class="sxs-lookup"><span data-stu-id="c183c-117">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="c183c-118">attributeID</span><span class="sxs-lookup"><span data-stu-id="c183c-118">attributeID</span></span>  <br/> |<span data-ttu-id="c183c-119">プライマリ ・ キーです。</span><span class="sxs-lookup"><span data-stu-id="c183c-119">Primary key.</span></span>  <br/> |
   
<span data-ttu-id="c183c-120">**テーブルの値**</span><span class="sxs-lookup"><span data-stu-id="c183c-120">**Table Values**</span></span>

|<span data-ttu-id="c183c-121">**attributeID**</span><span class="sxs-lookup"><span data-stu-id="c183c-121">**attributeID**</span></span>|<span data-ttu-id="c183c-122">**attributeName**</span><span class="sxs-lookup"><span data-stu-id="c183c-122">**attributeName**</span></span>|
|:-----|:-----|
|<span data-ttu-id="c183c-123">1</span><span class="sxs-lookup"><span data-stu-id="c183c-123">1</span></span>  <br/> |<span data-ttu-id="c183c-124">表示/非表示にします。</span><span class="sxs-lookup"><span data-stu-id="c183c-124">Visibility.</span></span>  <br/> |
|<span data-ttu-id="c183c-125">2</span><span class="sxs-lookup"><span data-stu-id="c183c-125">2</span></span>  <br/> |<span data-ttu-id="c183c-126">動作します。</span><span class="sxs-lookup"><span data-stu-id="c183c-126">Behavior.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="c183c-127">関連項目</span><span class="sxs-lookup"><span data-stu-id="c183c-127">See also</span></span>

[<span data-ttu-id="c183c-128">tblNode</span><span class="sxs-lookup"><span data-stu-id="c183c-128">tblNode</span></span>](tblnode.md)
