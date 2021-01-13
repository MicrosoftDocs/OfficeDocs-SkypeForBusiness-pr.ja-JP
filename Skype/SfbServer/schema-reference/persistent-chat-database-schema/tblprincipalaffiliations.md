---
title: tblPrincipalAffiliations
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
ms.assetid: 45fd8484-5837-44d2-85bb-45c83546607c
description: tblPrincipalAffiliations には、Active Directory ドメイン サービス セキュリティ グループを含む、ドメイン内の Active Directory コンテナー内の場所のメンバーシップを記述するプリンシパルの所属が含まれます。
ms.openlocfilehash: 149bb1b4603fa0f0e1909298659b881000464275
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49815867"
---
# <a name="tblprincipalaffiliations"></a><span data-ttu-id="e2baf-103">tblPrincipalAffiliations</span><span class="sxs-lookup"><span data-stu-id="e2baf-103">tblPrincipalAffiliations</span></span>
 
<span data-ttu-id="e2baf-104">tblPrincipalAffiliations には、Active Directory ドメイン サービス セキュリティ グループを含む、ドメイン内の Active Directory コンテナー内の場所のメンバーシップを記述するプリンシパルの所属が含まれます。</span><span class="sxs-lookup"><span data-stu-id="e2baf-104">tblPrincipalAffiliations contains the principal affiliations that describe memberships in locations, including Active Directory Domain Services security groups, in Active Directory containers, in domains.</span></span>
  
<span data-ttu-id="e2baf-105">**Columns**</span><span class="sxs-lookup"><span data-stu-id="e2baf-105">**Columns**</span></span>

|<span data-ttu-id="e2baf-106">**列**</span><span class="sxs-lookup"><span data-stu-id="e2baf-106">**Column**</span></span>|<span data-ttu-id="e2baf-107">**型**</span><span class="sxs-lookup"><span data-stu-id="e2baf-107">**Type**</span></span>|<span data-ttu-id="e2baf-108">**説明**</span><span class="sxs-lookup"><span data-stu-id="e2baf-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="e2baf-109">principalID</span><span class="sxs-lookup"><span data-stu-id="e2baf-109">principalID</span></span>  <br/> |<span data-ttu-id="e2baf-110">NULL でない int</span><span class="sxs-lookup"><span data-stu-id="e2baf-110">int, not null</span></span>  <br/> |<span data-ttu-id="e2baf-111">所属プリンシパルの ID。</span><span class="sxs-lookup"><span data-stu-id="e2baf-111">ID of the affiliated principal.</span></span>  <br/> |
|<span data-ttu-id="e2baf-112">affiliationID</span><span class="sxs-lookup"><span data-stu-id="e2baf-112">affiliationID</span></span>  <br/> |<span data-ttu-id="e2baf-113">NULL でない int</span><span class="sxs-lookup"><span data-stu-id="e2baf-113">int, not null</span></span>  <br/> |<span data-ttu-id="e2baf-p101">所属を表すプリンシパルの ID。各プリンシパル (system-user-types 除く) には自己所属も含まれます。</span><span class="sxs-lookup"><span data-stu-id="e2baf-p101">ID of the principal representing the affiliation. Each principal (except system-user-types) has a self-affiliation as well.</span></span>  <br/> |
|<span data-ttu-id="e2baf-116">index</span><span class="sxs-lookup"><span data-stu-id="e2baf-116">index</span></span>  <br/> |<span data-ttu-id="e2baf-117">NULL でない int</span><span class="sxs-lookup"><span data-stu-id="e2baf-117">int, not null</span></span>  <br/> |<span data-ttu-id="e2baf-118">インデックス。</span><span class="sxs-lookup"><span data-stu-id="e2baf-118">Index.</span></span> <span data-ttu-id="e2baf-119">自己所属の値は -1 で、他の所属の場合は各バケット内で 1 から順番に増加 \<principalID, affiliationId\> します。</span><span class="sxs-lookup"><span data-stu-id="e2baf-119">The value for self-affiliations is -1, and for the other affiliations it increases sequentially from 1 within each \<principalID, affiliationId\> bucket.</span></span>  <br/> |
|<span data-ttu-id="e2baf-120">updatedBy</span><span class="sxs-lookup"><span data-stu-id="e2baf-120">updatedBy</span></span>  <br/> |<span data-ttu-id="e2baf-121">NULL でない int</span><span class="sxs-lookup"><span data-stu-id="e2baf-121">int, not null</span></span>  <br/> |<span data-ttu-id="e2baf-p103">最新の更新を実行したプリンシパル。通常は、Active Directory の同期を意味する 1 です。</span><span class="sxs-lookup"><span data-stu-id="e2baf-p103">Principal that did the latest update. This is usually 1, which means Active Directory Sync.</span></span>  <br/> |
   
<span data-ttu-id="e2baf-124">**Keys**</span><span class="sxs-lookup"><span data-stu-id="e2baf-124">**Keys**</span></span>

|<span data-ttu-id="e2baf-125">**Columns**</span><span class="sxs-lookup"><span data-stu-id="e2baf-125">**Columns**</span></span>|<span data-ttu-id="e2baf-126">**説明**</span><span class="sxs-lookup"><span data-stu-id="e2baf-126">**Description**</span></span>|
|:-----|:-----|
|\<principalID, index, affiliationID\>  <br/> |<span data-ttu-id="e2baf-127">主キー。</span><span class="sxs-lookup"><span data-stu-id="e2baf-127">Primary key.</span></span>  <br/> |
|<span data-ttu-id="e2baf-128">principalID</span><span class="sxs-lookup"><span data-stu-id="e2baf-128">principalID</span></span>  <br/> |<span data-ttu-id="e2baf-129">tblPrincipal.prinID テーブル内の参照による外部キー。</span><span class="sxs-lookup"><span data-stu-id="e2baf-129">Foreign key with lookup in tblPrincipal.prinID table.</span></span>  <br/> |
|<span data-ttu-id="e2baf-130">affiliationID</span><span class="sxs-lookup"><span data-stu-id="e2baf-130">affiliationID</span></span>  <br/> |<span data-ttu-id="e2baf-131">tblPrincipal.prinID テーブル内の参照による外部キー。</span><span class="sxs-lookup"><span data-stu-id="e2baf-131">Foreign key with lookup in tblPrincipal.prinID table.</span></span>  <br/> |
   

