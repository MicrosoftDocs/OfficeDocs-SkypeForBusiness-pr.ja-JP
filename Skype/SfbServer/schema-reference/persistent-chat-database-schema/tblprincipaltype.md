---
title: tblPrincipalType
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
ms.assetid: 32e1c1d6-80f4-4624-bf4e-b4c77d3982fa
description: tblPrincipalType には、tblPrincipal テーブルの内容を分類するためのプリンシパルの種類が含まれています。
ms.openlocfilehash: 1aacfdf34689bebc2c7e012c926731ae1f4a8349
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2020
ms.locfileid: "41812935"
---
# <a name="tblprincipaltype"></a><span data-ttu-id="015fb-103">tblPrincipalType</span><span class="sxs-lookup"><span data-stu-id="015fb-103">tblPrincipalType</span></span>
 
<span data-ttu-id="015fb-104">tblPrincipalType には、tblPrincipal テーブルの内容を分類するためのプリンシパルの種類が含まれています。</span><span class="sxs-lookup"><span data-stu-id="015fb-104">tblPrincipalType contains principal types to categorize what is in the tblPrincipal table.</span></span>
  
<span data-ttu-id="015fb-105">**行**</span><span class="sxs-lookup"><span data-stu-id="015fb-105">**Columns**</span></span>

|<span data-ttu-id="015fb-106">**列**</span><span class="sxs-lookup"><span data-stu-id="015fb-106">**Column**</span></span>|<span data-ttu-id="015fb-107">**種類**</span><span class="sxs-lookup"><span data-stu-id="015fb-107">**Type**</span></span>|<span data-ttu-id="015fb-108">**説明**</span><span class="sxs-lookup"><span data-stu-id="015fb-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="015fb-109">ptypeID</span><span class="sxs-lookup"><span data-stu-id="015fb-109">ptypeID</span></span>  <br/> |<span data-ttu-id="015fb-110">smallint (null ではない)</span><span class="sxs-lookup"><span data-stu-id="015fb-110">smallint, not null</span></span>  <br/> |<span data-ttu-id="015fb-111">プリンシパルの種類 ID。</span><span class="sxs-lookup"><span data-stu-id="015fb-111">Principal type ID.</span></span>  <br/> |
|<span data-ttu-id="015fb-112">ptypeDesc</span><span class="sxs-lookup"><span data-stu-id="015fb-112">ptypeDesc</span></span>  <br/> |<span data-ttu-id="015fb-113">nvarchar (256)、null ではない</span><span class="sxs-lookup"><span data-stu-id="015fb-113">nvarchar (256), not null</span></span>  <br/> |<span data-ttu-id="015fb-114">型の説明。</span><span class="sxs-lookup"><span data-stu-id="015fb-114">Description of the type.</span></span>  <br/> |
|<span data-ttu-id="015fb-115">ptypeIsSystemUser 場合</span><span class="sxs-lookup"><span data-stu-id="015fb-115">ptypeIsSystemUser</span></span>  <br/> |<span data-ttu-id="015fb-116">ビット、null ではない</span><span class="sxs-lookup"><span data-stu-id="015fb-116">bit, not null</span></span>  <br/> |<span data-ttu-id="015fb-117">内部目的で使用されるプリンシパルに対応する型の場合は True です。</span><span class="sxs-lookup"><span data-stu-id="015fb-117">True if the type corresponds to the principals that are used for internal purposes.</span></span>  <br/> |
|<span data-ttu-id="015fb-118">ptypeIsUser</span><span class="sxs-lookup"><span data-stu-id="015fb-118">ptypeIsUser</span></span>  <br/> |<span data-ttu-id="015fb-119">ビット、null ではない</span><span class="sxs-lookup"><span data-stu-id="015fb-119">bit, not null</span></span>  <br/> |<span data-ttu-id="015fb-120">型がユーザーの型である場合は True です。</span><span class="sxs-lookup"><span data-stu-id="015fb-120">True if the type is a user type.</span></span>  <br/> |
   
<span data-ttu-id="015fb-121">**Key**</span><span class="sxs-lookup"><span data-stu-id="015fb-121">**Key**</span></span>

|<span data-ttu-id="015fb-122">**列**</span><span class="sxs-lookup"><span data-stu-id="015fb-122">**Column**</span></span>|<span data-ttu-id="015fb-123">**説明**</span><span class="sxs-lookup"><span data-stu-id="015fb-123">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="015fb-124">ptypeID</span><span class="sxs-lookup"><span data-stu-id="015fb-124">ptypeID</span></span>  <br/> |<span data-ttu-id="015fb-125">主キー。</span><span class="sxs-lookup"><span data-stu-id="015fb-125">Primary key.</span></span>  <br/> |
   
<span data-ttu-id="015fb-126">**プリンシパルの値**</span><span class="sxs-lookup"><span data-stu-id="015fb-126">**Principal Values**</span></span>

|<span data-ttu-id="015fb-127">**ID**</span><span class="sxs-lookup"><span data-stu-id="015fb-127">**ID**</span></span>|<span data-ttu-id="015fb-128">**役割**</span><span class="sxs-lookup"><span data-stu-id="015fb-128">**Role**</span></span>|<span data-ttu-id="015fb-129">**説明**</span><span class="sxs-lookup"><span data-stu-id="015fb-129">**Description**</span></span>|<span data-ttu-id="015fb-130">**User**</span><span class="sxs-lookup"><span data-stu-id="015fb-130">**User**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="015fb-131">1</span><span class="sxs-lookup"><span data-stu-id="015fb-131">1</span></span>  <br/> |<span data-ttu-id="015fb-132">任意</span><span class="sxs-lookup"><span data-stu-id="015fb-132">Any</span></span>  <br/> |<span data-ttu-id="015fb-133">既知の型のない汎用プリンシパル。</span><span class="sxs-lookup"><span data-stu-id="015fb-133">Generic principal with no known type.</span></span> <span data-ttu-id="015fb-134">TblPrincipal テーブルでは使用されません。</span><span class="sxs-lookup"><span data-stu-id="015fb-134">Not used in tblPrincipal table.</span></span>  <br/> ||
|<span data-ttu-id="015fb-135">両面</span><span class="sxs-lookup"><span data-stu-id="015fb-135">2</span></span>  <br/> |<span data-ttu-id="015fb-136">任意のユーザー</span><span class="sxs-lookup"><span data-stu-id="015fb-136">AnyUser</span></span>  <br/> |<span data-ttu-id="015fb-137">ユーザーの種類の汎用プリンシパル。</span><span class="sxs-lookup"><span data-stu-id="015fb-137">Generic principal of user type.</span></span> <span data-ttu-id="015fb-138">TblPrincipal テーブルでは使用されません。</span><span class="sxs-lookup"><span data-stu-id="015fb-138">Not used in tblPrincipal table.</span></span>  <br/> |<span data-ttu-id="015fb-139">はい</span><span class="sxs-lookup"><span data-stu-id="015fb-139">Yes</span></span>  <br/> |
|<span data-ttu-id="015fb-140">3</span><span class="sxs-lookup"><span data-stu-id="015fb-140">3</span></span>  <br/> |<span data-ttu-id="015fb-141">AnyGroup</span><span class="sxs-lookup"><span data-stu-id="015fb-141">AnyGroup</span></span>  <br/> |<span data-ttu-id="015fb-142">グループの意味を持つ汎用プリンシパル。</span><span class="sxs-lookup"><span data-stu-id="015fb-142">Generic principal with group semantic.</span></span> <span data-ttu-id="015fb-143">TblPrincipal テーブルでは使用されません。</span><span class="sxs-lookup"><span data-stu-id="015fb-143">Not used in tblPrincipal table.</span></span>  <br/> ||
|<span data-ttu-id="015fb-144">4</span><span class="sxs-lookup"><span data-stu-id="015fb-144">4</span></span>  <br/> |<span data-ttu-id="015fb-145">他のお互い</span><span class="sxs-lookup"><span data-stu-id="015fb-145">SystemUser</span></span>  <br/> |<span data-ttu-id="015fb-146">常設チャットサーバーで内部的に使用されているプリンシパル。</span><span class="sxs-lookup"><span data-stu-id="015fb-146">Principal used internally by Persistent Chat Server.</span></span>  <br/> ||
|<span data-ttu-id="015fb-147">5</span><span class="sxs-lookup"><span data-stu-id="015fb-147">5</span></span>  <br/> |<span data-ttu-id="015fb-148">ユーザー</span><span class="sxs-lookup"><span data-stu-id="015fb-148">User</span></span>  <br/> |<span data-ttu-id="015fb-149">標準ユーザー。</span><span class="sxs-lookup"><span data-stu-id="015fb-149">Regular user.</span></span>  <br/> |<span data-ttu-id="015fb-150">はい</span><span class="sxs-lookup"><span data-stu-id="015fb-150">Yes</span></span>  <br/> |
|<span data-ttu-id="015fb-151">個</span><span class="sxs-lookup"><span data-stu-id="015fb-151">8</span></span>  <br/> |<span data-ttu-id="015fb-152">修飾</span><span class="sxs-lookup"><span data-stu-id="015fb-152">DC</span></span>  <br/> |<span data-ttu-id="015fb-153">Active Directory ドメインサービスのドメインコントローラー。</span><span class="sxs-lookup"><span data-stu-id="015fb-153">Active Directory Domain Services domain controller.</span></span>  <br/> ||
|<span data-ttu-id="015fb-154">ファイブ</span><span class="sxs-lookup"><span data-stu-id="015fb-154">9</span></span>  <br/> |<span data-ttu-id="015fb-155">化</span><span class="sxs-lookup"><span data-stu-id="015fb-155">Group</span></span>  <br/> |<span data-ttu-id="015fb-156">Active Directory セキュリティグループ。</span><span class="sxs-lookup"><span data-stu-id="015fb-156">Active Directory security group.</span></span>  <br/> ||
|<span data-ttu-id="015fb-157">常用</span><span class="sxs-lookup"><span data-stu-id="015fb-157">10</span></span>  <br/> |<span data-ttu-id="015fb-158">]</span><span class="sxs-lookup"><span data-stu-id="015fb-158">Folder</span></span>  <br/> |<span data-ttu-id="015fb-159">Active Directory コンテナーまたは組織単位。</span><span class="sxs-lookup"><span data-stu-id="015fb-159">Active Directory container or organizational unit.</span></span>  <br/> ||
   
## <a name="see-also"></a><span data-ttu-id="015fb-160">関連項目</span><span class="sxs-lookup"><span data-stu-id="015fb-160">See also</span></span>

[<span data-ttu-id="015fb-161">tblPrincipal</span><span class="sxs-lookup"><span data-stu-id="015fb-161">tblPrincipal</span></span>](tblprincipal.md)
