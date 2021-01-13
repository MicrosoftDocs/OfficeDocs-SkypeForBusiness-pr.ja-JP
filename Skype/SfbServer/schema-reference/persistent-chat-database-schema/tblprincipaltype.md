---
title: tblPrincipalType
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
ms.assetid: 32e1c1d6-80f4-4624-bf4e-b4c77d3982fa
description: tblPrincipal テーブルには、tblPrincipal テーブルの内容を分類するプリンシパル型が含まれます。
ms.openlocfilehash: 110818db0fb3c742491adfeed23362a2bcbebab2
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49831537"
---
# <a name="tblprincipaltype"></a><span data-ttu-id="7cf21-103">tblPrincipalType</span><span class="sxs-lookup"><span data-stu-id="7cf21-103">tblPrincipalType</span></span>
 
<span data-ttu-id="7cf21-104">tblPrincipal テーブルには、tblPrincipal テーブルの内容を分類するプリンシパル型が含まれます。</span><span class="sxs-lookup"><span data-stu-id="7cf21-104">tblPrincipalType contains principal types to categorize what is in the tblPrincipal table.</span></span>
  
<span data-ttu-id="7cf21-105">**Columns**</span><span class="sxs-lookup"><span data-stu-id="7cf21-105">**Columns**</span></span>

|<span data-ttu-id="7cf21-106">**列**</span><span class="sxs-lookup"><span data-stu-id="7cf21-106">**Column**</span></span>|<span data-ttu-id="7cf21-107">**型**</span><span class="sxs-lookup"><span data-stu-id="7cf21-107">**Type**</span></span>|<span data-ttu-id="7cf21-108">**説明**</span><span class="sxs-lookup"><span data-stu-id="7cf21-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="7cf21-109">ptypeID</span><span class="sxs-lookup"><span data-stu-id="7cf21-109">ptypeID</span></span>  <br/> |<span data-ttu-id="7cf21-110">NULL でない smallint</span><span class="sxs-lookup"><span data-stu-id="7cf21-110">smallint, not null</span></span>  <br/> |<span data-ttu-id="7cf21-111">プリンシパル型 ID。</span><span class="sxs-lookup"><span data-stu-id="7cf21-111">Principal type ID.</span></span>  <br/> |
|<span data-ttu-id="7cf21-112">ptypeDesc</span><span class="sxs-lookup"><span data-stu-id="7cf21-112">ptypeDesc</span></span>  <br/> |<span data-ttu-id="7cf21-113">NULL でない nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="7cf21-113">nvarchar (256), not null</span></span>  <br/> |<span data-ttu-id="7cf21-114">型の説明。</span><span class="sxs-lookup"><span data-stu-id="7cf21-114">Description of the type.</span></span>  <br/> |
|<span data-ttu-id="7cf21-115">ptypeIsSystemUser</span><span class="sxs-lookup"><span data-stu-id="7cf21-115">ptypeIsSystemUser</span></span>  <br/> |<span data-ttu-id="7cf21-116">NULL でない bit</span><span class="sxs-lookup"><span data-stu-id="7cf21-116">bit, not null</span></span>  <br/> |<span data-ttu-id="7cf21-117">型が内部の用途で使用されるプリンシパルに対応する場合、True。</span><span class="sxs-lookup"><span data-stu-id="7cf21-117">True if the type corresponds to the principals that are used for internal purposes.</span></span>  <br/> |
|<span data-ttu-id="7cf21-118">ptypeIsUser</span><span class="sxs-lookup"><span data-stu-id="7cf21-118">ptypeIsUser</span></span>  <br/> |<span data-ttu-id="7cf21-119">NULL でない bit</span><span class="sxs-lookup"><span data-stu-id="7cf21-119">bit, not null</span></span>  <br/> |<span data-ttu-id="7cf21-120">型がユーザー型の場合、True。</span><span class="sxs-lookup"><span data-stu-id="7cf21-120">True if the type is a user type.</span></span>  <br/> |
   
<span data-ttu-id="7cf21-121">**キー**</span><span class="sxs-lookup"><span data-stu-id="7cf21-121">**Key**</span></span>

|<span data-ttu-id="7cf21-122">**列**</span><span class="sxs-lookup"><span data-stu-id="7cf21-122">**Column**</span></span>|<span data-ttu-id="7cf21-123">**説明**</span><span class="sxs-lookup"><span data-stu-id="7cf21-123">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="7cf21-124">ptypeID</span><span class="sxs-lookup"><span data-stu-id="7cf21-124">ptypeID</span></span>  <br/> |<span data-ttu-id="7cf21-125">主キー。</span><span class="sxs-lookup"><span data-stu-id="7cf21-125">Primary key.</span></span>  <br/> |
   
<span data-ttu-id="7cf21-126">**プリンシパル値**</span><span class="sxs-lookup"><span data-stu-id="7cf21-126">**Principal Values**</span></span>

|<span data-ttu-id="7cf21-127">**ID**</span><span class="sxs-lookup"><span data-stu-id="7cf21-127">**ID**</span></span>|<span data-ttu-id="7cf21-128">**ロール**</span><span class="sxs-lookup"><span data-stu-id="7cf21-128">**Role**</span></span>|<span data-ttu-id="7cf21-129">**説明**</span><span class="sxs-lookup"><span data-stu-id="7cf21-129">**Description**</span></span>|<span data-ttu-id="7cf21-130">**ユーザー**</span><span class="sxs-lookup"><span data-stu-id="7cf21-130">**User**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="7cf21-131">1 </span><span class="sxs-lookup"><span data-stu-id="7cf21-131">1</span></span>  <br/> |<span data-ttu-id="7cf21-132">任意</span><span class="sxs-lookup"><span data-stu-id="7cf21-132">Any</span></span>  <br/> |<span data-ttu-id="7cf21-p101">既知の型を持たない汎用的なプリンシパル。tblPrincipal テーブルでは使用されません。</span><span class="sxs-lookup"><span data-stu-id="7cf21-p101">Generic principal with no known type. Not used in tblPrincipal table.</span></span>  <br/> ||
|<span data-ttu-id="7cf21-135">2 </span><span class="sxs-lookup"><span data-stu-id="7cf21-135">2</span></span>  <br/> |<span data-ttu-id="7cf21-136">AnyUser</span><span class="sxs-lookup"><span data-stu-id="7cf21-136">AnyUser</span></span>  <br/> |<span data-ttu-id="7cf21-p102">ユーザー型の汎用的なプリンシパル。tblPrincipal テーブルでは使用されません。</span><span class="sxs-lookup"><span data-stu-id="7cf21-p102">Generic principal of user type. Not used in tblPrincipal table.</span></span>  <br/> |<span data-ttu-id="7cf21-139">はい</span><span class="sxs-lookup"><span data-stu-id="7cf21-139">Yes</span></span>  <br/> |
|<span data-ttu-id="7cf21-140">3 </span><span class="sxs-lookup"><span data-stu-id="7cf21-140">3</span></span>  <br/> |<span data-ttu-id="7cf21-141">AnyGroup</span><span class="sxs-lookup"><span data-stu-id="7cf21-141">AnyGroup</span></span>  <br/> |<span data-ttu-id="7cf21-p103">グループ セマンティックを持つ汎用的なプリンシパル。tblPrincipal テーブルでは使用されません。</span><span class="sxs-lookup"><span data-stu-id="7cf21-p103">Generic principal with group semantic. Not used in tblPrincipal table.</span></span>  <br/> ||
|<span data-ttu-id="7cf21-144">4 </span><span class="sxs-lookup"><span data-stu-id="7cf21-144">4</span></span>  <br/> |<span data-ttu-id="7cf21-145">SystemUser</span><span class="sxs-lookup"><span data-stu-id="7cf21-145">SystemUser</span></span>  <br/> |<span data-ttu-id="7cf21-146">常設チャット サーバーによって内部的に使用されるプリンシパル。</span><span class="sxs-lookup"><span data-stu-id="7cf21-146">Principal used internally by Persistent Chat Server.</span></span>  <br/> ||
|<span data-ttu-id="7cf21-147">5 </span><span class="sxs-lookup"><span data-stu-id="7cf21-147">5</span></span>  <br/> |<span data-ttu-id="7cf21-148">User</span><span class="sxs-lookup"><span data-stu-id="7cf21-148">User</span></span>  <br/> |<span data-ttu-id="7cf21-149">標準のユーザー</span><span class="sxs-lookup"><span data-stu-id="7cf21-149">Regular user.</span></span>  <br/> |<span data-ttu-id="7cf21-150">はい</span><span class="sxs-lookup"><span data-stu-id="7cf21-150">Yes</span></span>  <br/> |
|<span data-ttu-id="7cf21-151">8 </span><span class="sxs-lookup"><span data-stu-id="7cf21-151">8</span></span>  <br/> |<span data-ttu-id="7cf21-152">DC</span><span class="sxs-lookup"><span data-stu-id="7cf21-152">DC</span></span>  <br/> |<span data-ttu-id="7cf21-153">Active Directory ドメイン サービス ドメイン コントローラー。</span><span class="sxs-lookup"><span data-stu-id="7cf21-153">Active Directory Domain Services domain controller.</span></span>  <br/> ||
|<span data-ttu-id="7cf21-154">9 </span><span class="sxs-lookup"><span data-stu-id="7cf21-154">9</span></span>  <br/> |<span data-ttu-id="7cf21-155">Group</span><span class="sxs-lookup"><span data-stu-id="7cf21-155">Group</span></span>  <br/> |<span data-ttu-id="7cf21-156">Active Directory セキュリティ グループ。</span><span class="sxs-lookup"><span data-stu-id="7cf21-156">Active Directory security group.</span></span>  <br/> ||
|<span data-ttu-id="7cf21-157">10 </span><span class="sxs-lookup"><span data-stu-id="7cf21-157">10</span></span>  <br/> |<span data-ttu-id="7cf21-158">フォルダー</span><span class="sxs-lookup"><span data-stu-id="7cf21-158">Folder</span></span>  <br/> |<span data-ttu-id="7cf21-159">Active Directory コンテナーまたは組織単位。</span><span class="sxs-lookup"><span data-stu-id="7cf21-159">Active Directory container or organizational unit.</span></span>  <br/> ||
   
## <a name="see-also"></a><span data-ttu-id="7cf21-160">関連項目</span><span class="sxs-lookup"><span data-stu-id="7cf21-160">See also</span></span>

[<span data-ttu-id="7cf21-161">tblPrincipal</span><span class="sxs-lookup"><span data-stu-id="7cf21-161">tblPrincipal</span></span>](tblprincipal.md)
