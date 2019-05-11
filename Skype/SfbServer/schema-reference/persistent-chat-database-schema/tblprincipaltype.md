---
title: tblPrincipalType
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 32e1c1d6-80f4-4624-bf4e-b4c77d3982fa
description: tblPrincipalType には、tblPrincipal テーブルに含まれるものを分類するためにプリンシパルの種類が含まれています。
ms.openlocfilehash: 804997c0cb25dff6566d21a26626550982d0075f
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "33924459"
---
# <a name="tblprincipaltype"></a><span data-ttu-id="a3b52-103">tblPrincipalType</span><span class="sxs-lookup"><span data-stu-id="a3b52-103">tblPrincipalType</span></span>
 
<span data-ttu-id="a3b52-104">tblPrincipalType には、tblPrincipal テーブルに含まれるものを分類するためにプリンシパルの種類が含まれています。</span><span class="sxs-lookup"><span data-stu-id="a3b52-104">tblPrincipalType contains principal types to categorize what is in the tblPrincipal table.</span></span>
  
<span data-ttu-id="a3b52-105">**列**</span><span class="sxs-lookup"><span data-stu-id="a3b52-105">**Columns**</span></span>

|<span data-ttu-id="a3b52-106">**列**</span><span class="sxs-lookup"><span data-stu-id="a3b52-106">**Column**</span></span>|<span data-ttu-id="a3b52-107">**型**</span><span class="sxs-lookup"><span data-stu-id="a3b52-107">**Type**</span></span>|<span data-ttu-id="a3b52-108">**説明**</span><span class="sxs-lookup"><span data-stu-id="a3b52-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="a3b52-109">ptypeID</span><span class="sxs-lookup"><span data-stu-id="a3b52-109">ptypeID</span></span>  <br/> |<span data-ttu-id="a3b52-110">smallint、null でないです。</span><span class="sxs-lookup"><span data-stu-id="a3b52-110">smallint, not null</span></span>  <br/> |<span data-ttu-id="a3b52-111">プリンシパルの種類の id。</span><span class="sxs-lookup"><span data-stu-id="a3b52-111">Principal type ID.</span></span>  <br/> |
|<span data-ttu-id="a3b52-112">ptypeDesc</span><span class="sxs-lookup"><span data-stu-id="a3b52-112">ptypeDesc</span></span>  <br/> |<span data-ttu-id="a3b52-113">nvarchar (256)、null でないです。</span><span class="sxs-lookup"><span data-stu-id="a3b52-113">nvarchar (256), not null</span></span>  <br/> |<span data-ttu-id="a3b52-114">型の説明です。</span><span class="sxs-lookup"><span data-stu-id="a3b52-114">Description of the type.</span></span>  <br/> |
|<span data-ttu-id="a3b52-115">ptypeIsSystemUser</span><span class="sxs-lookup"><span data-stu-id="a3b52-115">ptypeIsSystemUser</span></span>  <br/> |<span data-ttu-id="a3b52-116">ビットの null でないです。</span><span class="sxs-lookup"><span data-stu-id="a3b52-116">bit, not null</span></span>  <br/> |<span data-ttu-id="a3b52-117">型が内部のために使用されるプリンシパルに対応している場合は true。</span><span class="sxs-lookup"><span data-stu-id="a3b52-117">True if the type corresponds to the principals that are used for internal purposes.</span></span>  <br/> |
|<span data-ttu-id="a3b52-118">ptypeIsUser</span><span class="sxs-lookup"><span data-stu-id="a3b52-118">ptypeIsUser</span></span>  <br/> |<span data-ttu-id="a3b52-119">ビットの null でないです。</span><span class="sxs-lookup"><span data-stu-id="a3b52-119">bit, not null</span></span>  <br/> |<span data-ttu-id="a3b52-120">True を指定する型は、ユーザーの種類。</span><span class="sxs-lookup"><span data-stu-id="a3b52-120">True if the type is a user type.</span></span>  <br/> |
   
<span data-ttu-id="a3b52-121">**キー**</span><span class="sxs-lookup"><span data-stu-id="a3b52-121">**Key**</span></span>

|<span data-ttu-id="a3b52-122">**列**</span><span class="sxs-lookup"><span data-stu-id="a3b52-122">**Column**</span></span>|<span data-ttu-id="a3b52-123">**説明**</span><span class="sxs-lookup"><span data-stu-id="a3b52-123">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="a3b52-124">ptypeID</span><span class="sxs-lookup"><span data-stu-id="a3b52-124">ptypeID</span></span>  <br/> |<span data-ttu-id="a3b52-125">プライマリ ・ キーです。</span><span class="sxs-lookup"><span data-stu-id="a3b52-125">Primary key.</span></span>  <br/> |
   
<span data-ttu-id="a3b52-126">**プリンシパル値**</span><span class="sxs-lookup"><span data-stu-id="a3b52-126">**Principal Values**</span></span>

|<span data-ttu-id="a3b52-127">**ID**</span><span class="sxs-lookup"><span data-stu-id="a3b52-127">**ID**</span></span>|<span data-ttu-id="a3b52-128">**[役割]**</span><span class="sxs-lookup"><span data-stu-id="a3b52-128">**Role**</span></span>|<span data-ttu-id="a3b52-129">**説明**</span><span class="sxs-lookup"><span data-stu-id="a3b52-129">**Description**</span></span>|<span data-ttu-id="a3b52-130">**User**</span><span class="sxs-lookup"><span data-stu-id="a3b52-130">**User**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="a3b52-131">1</span><span class="sxs-lookup"><span data-stu-id="a3b52-131">1</span></span>  <br/> |<span data-ttu-id="a3b52-132">任意</span><span class="sxs-lookup"><span data-stu-id="a3b52-132">Any</span></span>  <br/> |<span data-ttu-id="a3b52-133">ありません既知の型を持つ汎用プリンシパルです。</span><span class="sxs-lookup"><span data-stu-id="a3b52-133">Generic principal with no known type.</span></span> <span data-ttu-id="a3b52-134">TblPrincipal テーブルでは使用されません。</span><span class="sxs-lookup"><span data-stu-id="a3b52-134">Not used in tblPrincipal table.</span></span>  <br/> ||
|<span data-ttu-id="a3b52-135">2</span><span class="sxs-lookup"><span data-stu-id="a3b52-135">2</span></span>  <br/> |<span data-ttu-id="a3b52-136">AnyUser</span><span class="sxs-lookup"><span data-stu-id="a3b52-136">AnyUser</span></span>  <br/> |<span data-ttu-id="a3b52-137">ユーザー型の汎用的なプリンシパルです。</span><span class="sxs-lookup"><span data-stu-id="a3b52-137">Generic principal of user type.</span></span> <span data-ttu-id="a3b52-138">TblPrincipal テーブルでは使用されません。</span><span class="sxs-lookup"><span data-stu-id="a3b52-138">Not used in tblPrincipal table.</span></span>  <br/> |<span data-ttu-id="a3b52-139">はい</span><span class="sxs-lookup"><span data-stu-id="a3b52-139">Yes</span></span>  <br/> |
|<span data-ttu-id="a3b52-140">3</span><span class="sxs-lookup"><span data-stu-id="a3b52-140">3</span></span>  <br/> |<span data-ttu-id="a3b52-141">AnyGroup</span><span class="sxs-lookup"><span data-stu-id="a3b52-141">AnyGroup</span></span>  <br/> |<span data-ttu-id="a3b52-142">グループの意味を持つ汎用プリンシパルです。</span><span class="sxs-lookup"><span data-stu-id="a3b52-142">Generic principal with group semantic.</span></span> <span data-ttu-id="a3b52-143">TblPrincipal テーブルでは使用されません。</span><span class="sxs-lookup"><span data-stu-id="a3b52-143">Not used in tblPrincipal table.</span></span>  <br/> ||
|<span data-ttu-id="a3b52-144">4</span><span class="sxs-lookup"><span data-stu-id="a3b52-144">4</span></span>  <br/> |<span data-ttu-id="a3b52-145">システム ユーザー</span><span class="sxs-lookup"><span data-stu-id="a3b52-145">SystemUser</span></span>  <br/> |<span data-ttu-id="a3b52-146">プリンシパルが永続的なチャット サーバーによって内部的に使用します。</span><span class="sxs-lookup"><span data-stu-id="a3b52-146">Principal used internally by Persistent Chat Server.</span></span>  <br/> ||
|<span data-ttu-id="a3b52-147">5</span><span class="sxs-lookup"><span data-stu-id="a3b52-147">5</span></span>  <br/> |<span data-ttu-id="a3b52-148">ユーザー</span><span class="sxs-lookup"><span data-stu-id="a3b52-148">User</span></span>  <br/> |<span data-ttu-id="a3b52-149">正規ユーザーです。</span><span class="sxs-lookup"><span data-stu-id="a3b52-149">Regular user.</span></span>  <br/> |<span data-ttu-id="a3b52-150">はい</span><span class="sxs-lookup"><span data-stu-id="a3b52-150">Yes</span></span>  <br/> |
|<span data-ttu-id="a3b52-151">8</span><span class="sxs-lookup"><span data-stu-id="a3b52-151">8</span></span>  <br/> |<span data-ttu-id="a3b52-152">DC</span><span class="sxs-lookup"><span data-stu-id="a3b52-152">DC</span></span>  <br/> |<span data-ttu-id="a3b52-153">Active Directory ドメイン サービス ドメイン コント ローラーです。</span><span class="sxs-lookup"><span data-stu-id="a3b52-153">Active Directory Domain Services domain controller.</span></span>  <br/> ||
|<span data-ttu-id="a3b52-154">9</span><span class="sxs-lookup"><span data-stu-id="a3b52-154">9</span></span>  <br/> |<span data-ttu-id="a3b52-155">グループ</span><span class="sxs-lookup"><span data-stu-id="a3b52-155">Group</span></span>  <br/> |<span data-ttu-id="a3b52-156">Active Directory セキュリティ グループです。</span><span class="sxs-lookup"><span data-stu-id="a3b52-156">Active Directory security group.</span></span>  <br/> ||
|<span data-ttu-id="a3b52-157">10</span><span class="sxs-lookup"><span data-stu-id="a3b52-157">10</span></span>  <br/> |<span data-ttu-id="a3b52-158">フォルダー</span><span class="sxs-lookup"><span data-stu-id="a3b52-158">Folder</span></span>  <br/> |<span data-ttu-id="a3b52-159">Active Directory コンテナーまたは組織単位です。</span><span class="sxs-lookup"><span data-stu-id="a3b52-159">Active Directory container or organizational unit.</span></span>  <br/> ||
   
## <a name="see-also"></a><span data-ttu-id="a3b52-160">関連項目</span><span class="sxs-lookup"><span data-stu-id="a3b52-160">See also</span></span>

[<span data-ttu-id="a3b52-161">tblPrincipal</span><span class="sxs-lookup"><span data-stu-id="a3b52-161">tblPrincipal</span></span>](tblprincipal.md)
