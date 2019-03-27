---
title: tblPrincipalType
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 32e1c1d6-80f4-4624-bf4e-b4c77d3982fa
description: tblPrincipalType には、tblPrincipal テーブルに含まれるものを分類するためにプリンシパルの種類が含まれています。
ms.openlocfilehash: ab2cb28971f0564a082e0caed01e7fc622c41201
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/27/2019
ms.locfileid: "30887437"
---
# <a name="tblprincipaltype"></a><span data-ttu-id="b4e4d-103">tblPrincipalType</span><span class="sxs-lookup"><span data-stu-id="b4e4d-103">tblPrincipalType</span></span>
 
<span data-ttu-id="b4e4d-104">tblPrincipalType には、tblPrincipal テーブルに含まれるものを分類するためにプリンシパルの種類が含まれています。</span><span class="sxs-lookup"><span data-stu-id="b4e4d-104">tblPrincipalType contains principal types to categorize what is in the tblPrincipal table.</span></span>
  
<span data-ttu-id="b4e4d-105">**列**</span><span class="sxs-lookup"><span data-stu-id="b4e4d-105">**Columns**</span></span>

|<span data-ttu-id="b4e4d-106">**列**</span><span class="sxs-lookup"><span data-stu-id="b4e4d-106">**Column**</span></span>|<span data-ttu-id="b4e4d-107">**型**</span><span class="sxs-lookup"><span data-stu-id="b4e4d-107">**Type**</span></span>|<span data-ttu-id="b4e4d-108">**説明**</span><span class="sxs-lookup"><span data-stu-id="b4e4d-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="b4e4d-109">ptypeID</span><span class="sxs-lookup"><span data-stu-id="b4e4d-109">ptypeID</span></span>  <br/> |<span data-ttu-id="b4e4d-110">smallint、null でないです。</span><span class="sxs-lookup"><span data-stu-id="b4e4d-110">smallint, not null</span></span>  <br/> |<span data-ttu-id="b4e4d-111">プリンシパルの種類の id。</span><span class="sxs-lookup"><span data-stu-id="b4e4d-111">Principal type ID.</span></span>  <br/> |
|<span data-ttu-id="b4e4d-112">ptypeDesc</span><span class="sxs-lookup"><span data-stu-id="b4e4d-112">ptypeDesc</span></span>  <br/> |<span data-ttu-id="b4e4d-113">nvarchar (256)、null でないです。</span><span class="sxs-lookup"><span data-stu-id="b4e4d-113">nvarchar (256), not null</span></span>  <br/> |<span data-ttu-id="b4e4d-114">型の説明です。</span><span class="sxs-lookup"><span data-stu-id="b4e4d-114">Description of the type.</span></span>  <br/> |
|<span data-ttu-id="b4e4d-115">ptypeIsSystemUser</span><span class="sxs-lookup"><span data-stu-id="b4e4d-115">ptypeIsSystemUser</span></span>  <br/> |<span data-ttu-id="b4e4d-116">ビットの null でないです。</span><span class="sxs-lookup"><span data-stu-id="b4e4d-116">bit, not null</span></span>  <br/> |<span data-ttu-id="b4e4d-117">型が内部のために使用されるプリンシパルに対応している場合は true。</span><span class="sxs-lookup"><span data-stu-id="b4e4d-117">True if the type corresponds to the principals that are used for internal purposes.</span></span>  <br/> |
|<span data-ttu-id="b4e4d-118">ptypeIsUser</span><span class="sxs-lookup"><span data-stu-id="b4e4d-118">ptypeIsUser</span></span>  <br/> |<span data-ttu-id="b4e4d-119">ビットの null でないです。</span><span class="sxs-lookup"><span data-stu-id="b4e4d-119">bit, not null</span></span>  <br/> |<span data-ttu-id="b4e4d-120">True を指定する型は、ユーザーの種類。</span><span class="sxs-lookup"><span data-stu-id="b4e4d-120">True if the type is a user type.</span></span>  <br/> |
   
<span data-ttu-id="b4e4d-121">**キー**</span><span class="sxs-lookup"><span data-stu-id="b4e4d-121">**Key**</span></span>

|<span data-ttu-id="b4e4d-122">**列**</span><span class="sxs-lookup"><span data-stu-id="b4e4d-122">**Column**</span></span>|<span data-ttu-id="b4e4d-123">**説明**</span><span class="sxs-lookup"><span data-stu-id="b4e4d-123">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="b4e4d-124">ptypeID</span><span class="sxs-lookup"><span data-stu-id="b4e4d-124">ptypeID</span></span>  <br/> |<span data-ttu-id="b4e4d-125">プライマリ ・ キーです。</span><span class="sxs-lookup"><span data-stu-id="b4e4d-125">Primary key.</span></span>  <br/> |
   
<span data-ttu-id="b4e4d-126">**プリンシパル値**</span><span class="sxs-lookup"><span data-stu-id="b4e4d-126">**Principal Values**</span></span>

|<span data-ttu-id="b4e4d-127">**ID**</span><span class="sxs-lookup"><span data-stu-id="b4e4d-127">**ID**</span></span>|<span data-ttu-id="b4e4d-128">**[役割]**</span><span class="sxs-lookup"><span data-stu-id="b4e4d-128">**Role**</span></span>|<span data-ttu-id="b4e4d-129">**説明**</span><span class="sxs-lookup"><span data-stu-id="b4e4d-129">**Description**</span></span>|<span data-ttu-id="b4e4d-130">**User**</span><span class="sxs-lookup"><span data-stu-id="b4e4d-130">**User**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="b4e4d-131">1</span><span class="sxs-lookup"><span data-stu-id="b4e4d-131">1</span></span>  <br/> |<span data-ttu-id="b4e4d-132">任意</span><span class="sxs-lookup"><span data-stu-id="b4e4d-132">Any</span></span>  <br/> |<span data-ttu-id="b4e4d-133">ありません既知の型を持つ汎用プリンシパルです。</span><span class="sxs-lookup"><span data-stu-id="b4e4d-133">Generic principal with no known type.</span></span> <span data-ttu-id="b4e4d-134">TblPrincipal テーブルでは使用されません。</span><span class="sxs-lookup"><span data-stu-id="b4e4d-134">Not used in tblPrincipal table.</span></span>  <br/> ||
|<span data-ttu-id="b4e4d-135">2</span><span class="sxs-lookup"><span data-stu-id="b4e4d-135">2</span></span>  <br/> |<span data-ttu-id="b4e4d-136">AnyUser</span><span class="sxs-lookup"><span data-stu-id="b4e4d-136">AnyUser</span></span>  <br/> |<span data-ttu-id="b4e4d-137">ユーザー型の汎用的なプリンシパルです。</span><span class="sxs-lookup"><span data-stu-id="b4e4d-137">Generic principal of user type.</span></span> <span data-ttu-id="b4e4d-138">TblPrincipal テーブルでは使用されません。</span><span class="sxs-lookup"><span data-stu-id="b4e4d-138">Not used in tblPrincipal table.</span></span>  <br/> |<span data-ttu-id="b4e4d-139">はい</span><span class="sxs-lookup"><span data-stu-id="b4e4d-139">Yes</span></span>  <br/> |
|<span data-ttu-id="b4e4d-140">3</span><span class="sxs-lookup"><span data-stu-id="b4e4d-140">3</span></span>  <br/> |<span data-ttu-id="b4e4d-141">AnyGroup</span><span class="sxs-lookup"><span data-stu-id="b4e4d-141">AnyGroup</span></span>  <br/> |<span data-ttu-id="b4e4d-142">グループの意味を持つ汎用プリンシパルです。</span><span class="sxs-lookup"><span data-stu-id="b4e4d-142">Generic principal with group semantic.</span></span> <span data-ttu-id="b4e4d-143">TblPrincipal テーブルでは使用されません。</span><span class="sxs-lookup"><span data-stu-id="b4e4d-143">Not used in tblPrincipal table.</span></span>  <br/> ||
|<span data-ttu-id="b4e4d-144">4</span><span class="sxs-lookup"><span data-stu-id="b4e4d-144">4</span></span>  <br/> |<span data-ttu-id="b4e4d-145">システム ユーザー</span><span class="sxs-lookup"><span data-stu-id="b4e4d-145">SystemUser</span></span>  <br/> |<span data-ttu-id="b4e4d-146">プリンシパルが永続的なチャット サーバーによって内部的に使用します。</span><span class="sxs-lookup"><span data-stu-id="b4e4d-146">Principal used internally by Persistent Chat Server.</span></span>  <br/> ||
|<span data-ttu-id="b4e4d-147">5</span><span class="sxs-lookup"><span data-stu-id="b4e4d-147">5</span></span>  <br/> |<span data-ttu-id="b4e4d-148">ユーザー</span><span class="sxs-lookup"><span data-stu-id="b4e4d-148">User</span></span>  <br/> |<span data-ttu-id="b4e4d-149">正規ユーザーです。</span><span class="sxs-lookup"><span data-stu-id="b4e4d-149">Regular user.</span></span>  <br/> |<span data-ttu-id="b4e4d-150">はい</span><span class="sxs-lookup"><span data-stu-id="b4e4d-150">Yes</span></span>  <br/> |
|<span data-ttu-id="b4e4d-151">8</span><span class="sxs-lookup"><span data-stu-id="b4e4d-151">8</span></span>  <br/> |<span data-ttu-id="b4e4d-152">DC</span><span class="sxs-lookup"><span data-stu-id="b4e4d-152">DC</span></span>  <br/> |<span data-ttu-id="b4e4d-153">Active Directory ドメイン サービス ドメイン コント ローラーです。</span><span class="sxs-lookup"><span data-stu-id="b4e4d-153">Active Directory Domain Services domain controller.</span></span>  <br/> ||
|<span data-ttu-id="b4e4d-154">9</span><span class="sxs-lookup"><span data-stu-id="b4e4d-154">9</span></span>  <br/> |<span data-ttu-id="b4e4d-155">グループ</span><span class="sxs-lookup"><span data-stu-id="b4e4d-155">Group</span></span>  <br/> |<span data-ttu-id="b4e4d-156">Active Directory セキュリティ グループです。</span><span class="sxs-lookup"><span data-stu-id="b4e4d-156">Active Directory security group.</span></span>  <br/> ||
|<span data-ttu-id="b4e4d-157">10</span><span class="sxs-lookup"><span data-stu-id="b4e4d-157">10</span></span>  <br/> |<span data-ttu-id="b4e4d-158">フォルダー</span><span class="sxs-lookup"><span data-stu-id="b4e4d-158">Folder</span></span>  <br/> |<span data-ttu-id="b4e4d-159">Active Directory コンテナーまたは組織単位です。</span><span class="sxs-lookup"><span data-stu-id="b4e4d-159">Active Directory container or organizational unit.</span></span>  <br/> ||
   
## <a name="see-also"></a><span data-ttu-id="b4e4d-160">関連項目</span><span class="sxs-lookup"><span data-stu-id="b4e4d-160">See also</span></span>

[<span data-ttu-id="b4e4d-161">tblPrincipal</span><span class="sxs-lookup"><span data-stu-id="b4e4d-161">tblPrincipal</span></span>](tblprincipal.md)
