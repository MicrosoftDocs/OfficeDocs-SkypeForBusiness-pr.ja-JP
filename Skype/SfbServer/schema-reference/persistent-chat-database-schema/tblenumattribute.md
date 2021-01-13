---
title: tblEnumAttribute
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
ms.assetid: 17f8b87e-36a6-4f6a-8630-7c76b61a7595
description: tblEnumAttribute は、Node テーブルで使用される表示および動作属性を含むハードコードされたテーブルです。
ms.openlocfilehash: 698eda1e6e815ad4de4042312be1738a3a41d1f2
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49809717"
---
# <a name="tblenumattribute"></a><span data-ttu-id="ed337-103">tblEnumAttribute</span><span class="sxs-lookup"><span data-stu-id="ed337-103">tblEnumAttribute</span></span>
 
<span data-ttu-id="ed337-104">tblEnumAttribute は、Node テーブルで使用される表示および動作属性を含むハードコードされたテーブルです。</span><span class="sxs-lookup"><span data-stu-id="ed337-104">tblEnumAttribute is a hardcoded table that contains the Visibility and Behavior attributes that are used in the Node table.</span></span>
  
<span data-ttu-id="ed337-105">**Columns**</span><span class="sxs-lookup"><span data-stu-id="ed337-105">**Columns**</span></span>

|<span data-ttu-id="ed337-106">**列**</span><span class="sxs-lookup"><span data-stu-id="ed337-106">**Column**</span></span>|<span data-ttu-id="ed337-107">**型**</span><span class="sxs-lookup"><span data-stu-id="ed337-107">**Type**</span></span>|<span data-ttu-id="ed337-108">**説明**</span><span class="sxs-lookup"><span data-stu-id="ed337-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="ed337-109">attributeID</span><span class="sxs-lookup"><span data-stu-id="ed337-109">attributeID</span></span>  <br/> |<span data-ttu-id="ed337-110">NULL でない smallint</span><span class="sxs-lookup"><span data-stu-id="ed337-110">smallint, not null</span></span>  <br/> |<span data-ttu-id="ed337-111">属性の ID。</span><span class="sxs-lookup"><span data-stu-id="ed337-111">ID of the attribute.</span></span>  <br/> |
|<span data-ttu-id="ed337-112">attributeName</span><span class="sxs-lookup"><span data-stu-id="ed337-112">attributeName</span></span>  <br/> |<span data-ttu-id="ed337-113">NULL でない nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="ed337-113">nvarchar (256), not null</span></span>  <br/> |<span data-ttu-id="ed337-114">属性の名前。</span><span class="sxs-lookup"><span data-stu-id="ed337-114">Name of the attribute.</span></span>  <br/> |
   
<span data-ttu-id="ed337-115">**キー**</span><span class="sxs-lookup"><span data-stu-id="ed337-115">**Key**</span></span>

|<span data-ttu-id="ed337-116">**列**</span><span class="sxs-lookup"><span data-stu-id="ed337-116">**Column**</span></span>|<span data-ttu-id="ed337-117">**説明**</span><span class="sxs-lookup"><span data-stu-id="ed337-117">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="ed337-118">attributeID</span><span class="sxs-lookup"><span data-stu-id="ed337-118">attributeID</span></span>  <br/> |<span data-ttu-id="ed337-119">主キー。</span><span class="sxs-lookup"><span data-stu-id="ed337-119">Primary key.</span></span>  <br/> |
   
<span data-ttu-id="ed337-120">**テーブル値**</span><span class="sxs-lookup"><span data-stu-id="ed337-120">**Table Values**</span></span>

|<span data-ttu-id="ed337-121">**attributeID**</span><span class="sxs-lookup"><span data-stu-id="ed337-121">**attributeID**</span></span>|<span data-ttu-id="ed337-122">**attributeName**</span><span class="sxs-lookup"><span data-stu-id="ed337-122">**attributeName**</span></span>|
|:-----|:-----|
|<span data-ttu-id="ed337-123">1 </span><span class="sxs-lookup"><span data-stu-id="ed337-123">1</span></span>  <br/> |<span data-ttu-id="ed337-124">可視性。</span><span class="sxs-lookup"><span data-stu-id="ed337-124">Visibility.</span></span>  <br/> |
|<span data-ttu-id="ed337-125">2 </span><span class="sxs-lookup"><span data-stu-id="ed337-125">2</span></span>  <br/> |<span data-ttu-id="ed337-126">動作。</span><span class="sxs-lookup"><span data-stu-id="ed337-126">Behavior.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="ed337-127">関連項目</span><span class="sxs-lookup"><span data-stu-id="ed337-127">See also</span></span>

[<span data-ttu-id="ed337-128">tblNode</span><span class="sxs-lookup"><span data-stu-id="ed337-128">tblNode</span></span>](tblnode.md)
