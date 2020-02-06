---
title: tblPrincipalMeta
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
ms.assetid: 808490d4-7d6d-47a2-b8af-b5940d47073b
description: tblPrincipalMeta には、Active Directory ドメインサービスから更新する必要があるプリンシパルが含まれています。
ms.openlocfilehash: c76f4a74b3f627d360a2d745e46b6f2dac26bff0
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2020
ms.locfileid: "41813575"
---
# <a name="tblprincipalmeta"></a><span data-ttu-id="b98c6-103">tblPrincipalMeta</span><span class="sxs-lookup"><span data-stu-id="b98c6-103">tblPrincipalMeta</span></span>
 
<span data-ttu-id="b98c6-104">tblPrincipalMeta には、Active Directory ドメインサービスから更新する必要があるプリンシパルが含まれています。</span><span class="sxs-lookup"><span data-stu-id="b98c6-104">tblPrincipalMeta contains the principals that have to be refreshed from Active Directory Domain Services.</span></span>
  
<span data-ttu-id="b98c6-105">**行**</span><span class="sxs-lookup"><span data-stu-id="b98c6-105">**Columns**</span></span>

|<span data-ttu-id="b98c6-106">**列**</span><span class="sxs-lookup"><span data-stu-id="b98c6-106">**Column**</span></span>|<span data-ttu-id="b98c6-107">**種類**</span><span class="sxs-lookup"><span data-stu-id="b98c6-107">**Type**</span></span>|<span data-ttu-id="b98c6-108">**説明**</span><span class="sxs-lookup"><span data-stu-id="b98c6-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="b98c6-109">prinID</span><span class="sxs-lookup"><span data-stu-id="b98c6-109">prinID</span></span>  <br/> |<span data-ttu-id="b98c6-110">int (null ではない)</span><span class="sxs-lookup"><span data-stu-id="b98c6-110">int, not null</span></span>  <br/> |<span data-ttu-id="b98c6-111">プリンシパル ID。</span><span class="sxs-lookup"><span data-stu-id="b98c6-111">Principal ID.</span></span>  <br/> |
|<span data-ttu-id="b98c6-112">prinAffiliationsDirty</span><span class="sxs-lookup"><span data-stu-id="b98c6-112">prinAffiliationsDirty</span></span>  <br/> |<span data-ttu-id="b98c6-113">ビット、null ではない</span><span class="sxs-lookup"><span data-stu-id="b98c6-113">bit, not null</span></span>  <br/> |<span data-ttu-id="b98c6-114">プリンシパルの所属を更新する必要がある場合は True。</span><span class="sxs-lookup"><span data-stu-id="b98c6-114">True if principal affiliations have to be refreshed.</span></span>  <br/> |
|<span data-ttu-id="b98c6-115">Prin属性のダーティ</span><span class="sxs-lookup"><span data-stu-id="b98c6-115">prinAttributesDirty</span></span>  <br/> |<span data-ttu-id="b98c6-116">ビット、null ではない</span><span class="sxs-lookup"><span data-stu-id="b98c6-116">bit, not null</span></span>  <br/> |<span data-ttu-id="b98c6-117">プリンシパル属性を更新する必要がある場合は True。</span><span class="sxs-lookup"><span data-stu-id="b98c6-117">True if principal attributes have to be refreshed.</span></span>  <br/> |
|<span data-ttu-id="b98c6-118">プリントが削除されました</span><span class="sxs-lookup"><span data-stu-id="b98c6-118">prinDeleted</span></span>  <br/> |<span data-ttu-id="b98c6-119">ビット、null ではない</span><span class="sxs-lookup"><span data-stu-id="b98c6-119">bit, not null</span></span>  <br/> |<span data-ttu-id="b98c6-120">プリンシパルが削除された場合は True。</span><span class="sxs-lookup"><span data-stu-id="b98c6-120">True if the principal has been deleted.</span></span>  <br/> |
|<span data-ttu-id="b98c6-121">tryCount</span><span class="sxs-lookup"><span data-stu-id="b98c6-121">tryCount</span></span>  <br/> |<span data-ttu-id="b98c6-122">int</span><span class="sxs-lookup"><span data-stu-id="b98c6-122">int</span></span>  <br/> |<span data-ttu-id="b98c6-123">これまでに発生した、AD DS からプリンシパルを更新しようとした回数。</span><span class="sxs-lookup"><span data-stu-id="b98c6-123">Number of attempts to refresh the principal from AD DS that have happened so far.</span></span>  <br/> |
|<span data-ttu-id="b98c6-124">最終試用</span><span class="sxs-lookup"><span data-stu-id="b98c6-124">lastTry</span></span>  <br/> |<span data-ttu-id="b98c6-125">datetime</span><span class="sxs-lookup"><span data-stu-id="b98c6-125">datetime</span></span>  <br/> |<span data-ttu-id="b98c6-126">プリンシパルを最新の状態に更新しようとしたときのタイムスタンプ。</span><span class="sxs-lookup"><span data-stu-id="b98c6-126">Time stamp from the latest attempt to refresh the principal.</span></span> <span data-ttu-id="b98c6-127">更新をまだ実行していない場合は、null を指定できます。</span><span class="sxs-lookup"><span data-stu-id="b98c6-127">Can be null if no refresh has been attempted yet.</span></span>  <br/> |
|<span data-ttu-id="b98c6-128">nextTry</span><span class="sxs-lookup"><span data-stu-id="b98c6-128">nextTry</span></span>  <br/> |<span data-ttu-id="b98c6-129">datetime</span><span class="sxs-lookup"><span data-stu-id="b98c6-129">datetime</span></span>  <br/> |<span data-ttu-id="b98c6-130">スケジュールされている次回の更新のタイムスタンプ。</span><span class="sxs-lookup"><span data-stu-id="b98c6-130">Time stamp for the next scheduled refresh.</span></span> <span data-ttu-id="b98c6-131">それ以降の更新がスケジュールされていない場合は、null を指定できます。</span><span class="sxs-lookup"><span data-stu-id="b98c6-131">Can be null if no further refresh has been scheduled.</span></span>  <br/> |
   
<span data-ttu-id="b98c6-132">**機能**</span><span class="sxs-lookup"><span data-stu-id="b98c6-132">**Keys**</span></span>

|<span data-ttu-id="b98c6-133">**列**</span><span class="sxs-lookup"><span data-stu-id="b98c6-133">**Column**</span></span>|<span data-ttu-id="b98c6-134">**説明**</span><span class="sxs-lookup"><span data-stu-id="b98c6-134">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="b98c6-135">prinID</span><span class="sxs-lookup"><span data-stu-id="b98c6-135">prinID</span></span>  <br/> |<span data-ttu-id="b98c6-136">主キー。</span><span class="sxs-lookup"><span data-stu-id="b98c6-136">Primary key.</span></span>  <br/> |
|<span data-ttu-id="b98c6-137">prinID</span><span class="sxs-lookup"><span data-stu-id="b98c6-137">prinID</span></span>  <br/> |<span data-ttu-id="b98c6-138">TblPrincipal Id テーブルで参照される外部キー。</span><span class="sxs-lookup"><span data-stu-id="b98c6-138">Foreign key with lookup in tblPrincipal.prinID table.</span></span>  <br/> |
   

