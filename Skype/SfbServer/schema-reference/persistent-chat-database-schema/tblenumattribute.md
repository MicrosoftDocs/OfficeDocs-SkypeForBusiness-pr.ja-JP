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
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 17f8b87e-36a6-4f6a-8630-7c76b61a7595
description: tblEnumAttribute は、ノードテーブルで使用される Visibility 属性と Behavior 属性を含む、ハードコーディングされた表です。
ms.openlocfilehash: 8244e2fb6ace6c4ed73f017f52df0c85d1f02315
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2020
ms.locfileid: "41814615"
---
# <a name="tblenumattribute"></a><span data-ttu-id="b9814-103">tblEnumAttribute</span><span class="sxs-lookup"><span data-stu-id="b9814-103">tblEnumAttribute</span></span>
 
<span data-ttu-id="b9814-104">tblEnumAttribute は、ノードテーブルで使用される Visibility 属性と Behavior 属性を含む、ハードコーディングされた表です。</span><span class="sxs-lookup"><span data-stu-id="b9814-104">tblEnumAttribute is a hardcoded table that contains the Visibility and Behavior attributes that are used in the Node table.</span></span>
  
<span data-ttu-id="b9814-105">**行**</span><span class="sxs-lookup"><span data-stu-id="b9814-105">**Columns**</span></span>

|<span data-ttu-id="b9814-106">**列**</span><span class="sxs-lookup"><span data-stu-id="b9814-106">**Column**</span></span>|<span data-ttu-id="b9814-107">**種類**</span><span class="sxs-lookup"><span data-stu-id="b9814-107">**Type**</span></span>|<span data-ttu-id="b9814-108">**説明**</span><span class="sxs-lookup"><span data-stu-id="b9814-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="b9814-109">attributeID</span><span class="sxs-lookup"><span data-stu-id="b9814-109">attributeID</span></span>  <br/> |<span data-ttu-id="b9814-110">smallint (null ではない)</span><span class="sxs-lookup"><span data-stu-id="b9814-110">smallint, not null</span></span>  <br/> |<span data-ttu-id="b9814-111">属性の ID です。</span><span class="sxs-lookup"><span data-stu-id="b9814-111">ID of the attribute.</span></span>  <br/> |
|<span data-ttu-id="b9814-112">attributeName</span><span class="sxs-lookup"><span data-stu-id="b9814-112">attributeName</span></span>  <br/> |<span data-ttu-id="b9814-113">nvarchar (256)、null ではない</span><span class="sxs-lookup"><span data-stu-id="b9814-113">nvarchar (256), not null</span></span>  <br/> |<span data-ttu-id="b9814-114">属性の名前。</span><span class="sxs-lookup"><span data-stu-id="b9814-114">Name of the attribute.</span></span>  <br/> |
   
<span data-ttu-id="b9814-115">**Key**</span><span class="sxs-lookup"><span data-stu-id="b9814-115">**Key**</span></span>

|<span data-ttu-id="b9814-116">**列**</span><span class="sxs-lookup"><span data-stu-id="b9814-116">**Column**</span></span>|<span data-ttu-id="b9814-117">**説明**</span><span class="sxs-lookup"><span data-stu-id="b9814-117">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="b9814-118">attributeID</span><span class="sxs-lookup"><span data-stu-id="b9814-118">attributeID</span></span>  <br/> |<span data-ttu-id="b9814-119">主キー。</span><span class="sxs-lookup"><span data-stu-id="b9814-119">Primary key.</span></span>  <br/> |
   
<span data-ttu-id="b9814-120">**テーブルの値**</span><span class="sxs-lookup"><span data-stu-id="b9814-120">**Table Values**</span></span>

|<span data-ttu-id="b9814-121">**attributeID**</span><span class="sxs-lookup"><span data-stu-id="b9814-121">**attributeID**</span></span>|<span data-ttu-id="b9814-122">**attributeName**</span><span class="sxs-lookup"><span data-stu-id="b9814-122">**attributeName**</span></span>|
|:-----|:-----|
|<span data-ttu-id="b9814-123">1</span><span class="sxs-lookup"><span data-stu-id="b9814-123">1</span></span>  <br/> |<span data-ttu-id="b9814-124">明確化.</span><span class="sxs-lookup"><span data-stu-id="b9814-124">Visibility.</span></span>  <br/> |
|<span data-ttu-id="b9814-125">両面</span><span class="sxs-lookup"><span data-stu-id="b9814-125">2</span></span>  <br/> |<span data-ttu-id="b9814-126">状況.</span><span class="sxs-lookup"><span data-stu-id="b9814-126">Behavior.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="b9814-127">関連項目</span><span class="sxs-lookup"><span data-stu-id="b9814-127">See also</span></span>

[<span data-ttu-id="b9814-128">tblNode</span><span class="sxs-lookup"><span data-stu-id="b9814-128">tblNode</span></span>](tblnode.md)
