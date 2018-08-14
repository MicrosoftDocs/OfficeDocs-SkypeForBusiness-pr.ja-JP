---
title: tblEnumAttribute
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
ms.openlocfilehash: bd386bc77d15c627597a5680277235a05d0c8039
ms.sourcegitcommit: b14cfca231b618ec28cf9f4efe11cb3e8aceb34b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/19/2018
ms.locfileid: "19504867"
---
# <a name="tblenumattribute"></a><span data-ttu-id="3ea50-103">tblEnumAttribute</span><span class="sxs-lookup"><span data-stu-id="3ea50-103">tblEnumAttribute</span></span>
 
<span data-ttu-id="3ea50-104">tblEnumAttribute は、Node テーブルで使用されている可視性と動作の属性を含むハードコーディングされたテーブルです。</span><span class="sxs-lookup"><span data-stu-id="3ea50-104">tblEnumAttribute is a hardcoded table that contains the Visibility and Behavior attributes that are used in the Node table.</span></span>
  
<span data-ttu-id="3ea50-105">**列**</span><span class="sxs-lookup"><span data-stu-id="3ea50-105">**Columns**</span></span>

|<span data-ttu-id="3ea50-106">**列**</span><span class="sxs-lookup"><span data-stu-id="3ea50-106">**Column**</span></span>|<span data-ttu-id="3ea50-107">**種類**</span><span class="sxs-lookup"><span data-stu-id="3ea50-107">**Type**</span></span>|<span data-ttu-id="3ea50-108">**説明**</span><span class="sxs-lookup"><span data-stu-id="3ea50-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="3ea50-109">attributeID</span><span class="sxs-lookup"><span data-stu-id="3ea50-109">attributeID</span></span>  <br/> |<span data-ttu-id="3ea50-110">smallint、null でないです。</span><span class="sxs-lookup"><span data-stu-id="3ea50-110">smallint, not null</span></span>  <br/> |<span data-ttu-id="3ea50-111">属性の ID です。</span><span class="sxs-lookup"><span data-stu-id="3ea50-111">ID of the attribute.</span></span>  <br/> |
|<span data-ttu-id="3ea50-112">attributeName</span><span class="sxs-lookup"><span data-stu-id="3ea50-112">attributeName</span></span>  <br/> |<span data-ttu-id="3ea50-113">nvarchar (256)、null でないです。</span><span class="sxs-lookup"><span data-stu-id="3ea50-113">nvarchar (256), not null</span></span>  <br/> |<span data-ttu-id="3ea50-114">属性の名前です。</span><span class="sxs-lookup"><span data-stu-id="3ea50-114">Name of the attribute.</span></span>  <br/> |
   
<span data-ttu-id="3ea50-115">**キー**</span><span class="sxs-lookup"><span data-stu-id="3ea50-115">**Key**</span></span>

|<span data-ttu-id="3ea50-116">**列**</span><span class="sxs-lookup"><span data-stu-id="3ea50-116">**Column**</span></span>|<span data-ttu-id="3ea50-117">**説明**</span><span class="sxs-lookup"><span data-stu-id="3ea50-117">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="3ea50-118">attributeID</span><span class="sxs-lookup"><span data-stu-id="3ea50-118">attributeID</span></span>  <br/> |<span data-ttu-id="3ea50-119">プライマリ ・ キーです。</span><span class="sxs-lookup"><span data-stu-id="3ea50-119">Primary key.</span></span>  <br/> |
   
<span data-ttu-id="3ea50-120">**テーブルの値**</span><span class="sxs-lookup"><span data-stu-id="3ea50-120">**Table Values**</span></span>

|<span data-ttu-id="3ea50-121">**attributeID**</span><span class="sxs-lookup"><span data-stu-id="3ea50-121">**attributeID**</span></span>|<span data-ttu-id="3ea50-122">**attributeName**</span><span class="sxs-lookup"><span data-stu-id="3ea50-122">**attributeName**</span></span>|
|:-----|:-----|
|<span data-ttu-id="3ea50-123">1</span><span class="sxs-lookup"><span data-stu-id="3ea50-123">1</span></span>  <br/> |<span data-ttu-id="3ea50-124">表示/非表示にします。</span><span class="sxs-lookup"><span data-stu-id="3ea50-124">Visibility.</span></span>  <br/> |
|<span data-ttu-id="3ea50-125">2</span><span class="sxs-lookup"><span data-stu-id="3ea50-125">2</span></span>  <br/> |<span data-ttu-id="3ea50-126">動作します。</span><span class="sxs-lookup"><span data-stu-id="3ea50-126">Behavior.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="3ea50-127">関連項目</span><span class="sxs-lookup"><span data-stu-id="3ea50-127">See also</span></span>

[<span data-ttu-id="3ea50-128">tblNode</span><span class="sxs-lookup"><span data-stu-id="3ea50-128">tblNode</span></span>](tblnode.md)