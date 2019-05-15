---
title: tblPrincipalAffiliations
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 45fd8484-5837-44d2-85bb-45c83546607c
description: tblPrincipalAffiliations には、Active Directory ドメイン サービスのセキュリティ グループを含むドメイン内の Active Directory コンテナー内の場所でのメンバーシップを表すプリンシパルの所属が含まれています。
ms.openlocfilehash: fb1bd8eb7291ba001a5c23240c2de70aaff048b1
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "33929820"
---
# <a name="tblprincipalaffiliations"></a><span data-ttu-id="a134e-103">tblPrincipalAffiliations</span><span class="sxs-lookup"><span data-stu-id="a134e-103">tblPrincipalAffiliations</span></span>
 
<span data-ttu-id="a134e-104">tblPrincipalAffiliations には、Active Directory ドメイン サービスのセキュリティ グループを含むドメイン内の Active Directory コンテナー内の場所でのメンバーシップを表すプリンシパルの所属が含まれています。</span><span class="sxs-lookup"><span data-stu-id="a134e-104">tblPrincipalAffiliations contains the principal affiliations that describe memberships in locations, including Active Directory Domain Services security groups, in Active Directory containers, in domains.</span></span>
  
<span data-ttu-id="a134e-105">**列**</span><span class="sxs-lookup"><span data-stu-id="a134e-105">**Columns**</span></span>

|<span data-ttu-id="a134e-106">**列**</span><span class="sxs-lookup"><span data-stu-id="a134e-106">**Column**</span></span>|<span data-ttu-id="a134e-107">**型**</span><span class="sxs-lookup"><span data-stu-id="a134e-107">**Type**</span></span>|<span data-ttu-id="a134e-108">**説明**</span><span class="sxs-lookup"><span data-stu-id="a134e-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="a134e-109">principalID</span><span class="sxs-lookup"><span data-stu-id="a134e-109">principalID</span></span>  <br/> |<span data-ttu-id="a134e-110">int 型、null でないです。</span><span class="sxs-lookup"><span data-stu-id="a134e-110">int, not null</span></span>  <br/> |<span data-ttu-id="a134e-111">関連のプリンシパルの ID です。</span><span class="sxs-lookup"><span data-stu-id="a134e-111">ID of the affiliated principal.</span></span>  <br/> |
|<span data-ttu-id="a134e-112">affiliationID</span><span class="sxs-lookup"><span data-stu-id="a134e-112">affiliationID</span></span>  <br/> |<span data-ttu-id="a134e-113">int 型、null でないです。</span><span class="sxs-lookup"><span data-stu-id="a134e-113">int, not null</span></span>  <br/> |<span data-ttu-id="a134e-114">所属を表すプリンシパルの ID です。</span><span class="sxs-lookup"><span data-stu-id="a134e-114">ID of the principal representing the affiliation.</span></span> <span data-ttu-id="a134e-115">(システム ・ ユーザー ・ タイプ) を除く各主体が、自己の所属もします。</span><span class="sxs-lookup"><span data-stu-id="a134e-115">Each principal (except system-user-types) has a self-affiliation as well.</span></span>  <br/> |
|<span data-ttu-id="a134e-116">インデックス</span><span class="sxs-lookup"><span data-stu-id="a134e-116">index</span></span>  <br/> |<span data-ttu-id="a134e-117">int 型、null でないです。</span><span class="sxs-lookup"><span data-stu-id="a134e-117">int, not null</span></span>  <br/> |<span data-ttu-id="a134e-118">インデックスです。</span><span class="sxs-lookup"><span data-stu-id="a134e-118">Index.</span></span> <span data-ttu-id="a134e-119">自己所属の値は-1 になり、他の団体の順番に各 1 \<principalID、affiliationId\>バケットです。</span><span class="sxs-lookup"><span data-stu-id="a134e-119">The value for self-affiliations is -1, and for the other affiliations it increases sequentially from 1 within each \<principalID, affiliationId\> bucket.</span></span>  <br/> |
|<span data-ttu-id="a134e-120">updatedBy</span><span class="sxs-lookup"><span data-stu-id="a134e-120">updatedBy</span></span>  <br/> |<span data-ttu-id="a134e-121">int 型、null でないです。</span><span class="sxs-lookup"><span data-stu-id="a134e-121">int, not null</span></span>  <br/> |<span data-ttu-id="a134e-122">最新のアップデートを行った主体。</span><span class="sxs-lookup"><span data-stu-id="a134e-122">Principal that did the latest update.</span></span> <span data-ttu-id="a134e-123">これは、通常、1 で、作業中のディレクトリ同期です。</span><span class="sxs-lookup"><span data-stu-id="a134e-123">This is usually 1, which means Active Directory Sync.</span></span>  <br/> |
   
<span data-ttu-id="a134e-124">**キー**</span><span class="sxs-lookup"><span data-stu-id="a134e-124">**Keys**</span></span>

|<span data-ttu-id="a134e-125">**列**</span><span class="sxs-lookup"><span data-stu-id="a134e-125">**Columns**</span></span>|<span data-ttu-id="a134e-126">**説明**</span><span class="sxs-lookup"><span data-stu-id="a134e-126">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="a134e-127">\<principalID、インデックス、affiliationID\></span><span class="sxs-lookup"><span data-stu-id="a134e-127">\<principalID, index, affiliationID\></span></span>  <br/> |<span data-ttu-id="a134e-128">プライマリ ・ キーです。</span><span class="sxs-lookup"><span data-stu-id="a134e-128">Primary key.</span></span>  <br/> |
|<span data-ttu-id="a134e-129">principalID</span><span class="sxs-lookup"><span data-stu-id="a134e-129">principalID</span></span>  <br/> |<span data-ttu-id="a134e-130">TblPrincipal.prinID テーブル内の参照と外部キーです。</span><span class="sxs-lookup"><span data-stu-id="a134e-130">Foreign key with lookup in tblPrincipal.prinID table.</span></span>  <br/> |
|<span data-ttu-id="a134e-131">affiliationID</span><span class="sxs-lookup"><span data-stu-id="a134e-131">affiliationID</span></span>  <br/> |<span data-ttu-id="a134e-132">TblPrincipal.prinID テーブル内の参照と外部キーです。</span><span class="sxs-lookup"><span data-stu-id="a134e-132">Foreign key with lookup in tblPrincipal.prinID table.</span></span>  <br/> |
   

