---
title: tblPrincipalAffiliations
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 45fd8484-5837-44d2-85bb-45c83546607c
description: tblPrincipalAffiliations には、Active Directory ドメイン サービスのセキュリティ グループを含むドメイン内の Active Directory コンテナー内の場所でのメンバーシップを表すプリンシパルの所属が含まれています。
ms.openlocfilehash: c93edb552c63ebd4f7344926a7d43858b42506ae
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "32212503"
---
# <a name="tblprincipalaffiliations"></a><span data-ttu-id="e8506-103">tblPrincipalAffiliations</span><span class="sxs-lookup"><span data-stu-id="e8506-103">tblPrincipalAffiliations</span></span>
 
<span data-ttu-id="e8506-104">tblPrincipalAffiliations には、Active Directory ドメイン サービスのセキュリティ グループを含むドメイン内の Active Directory コンテナー内の場所でのメンバーシップを表すプリンシパルの所属が含まれています。</span><span class="sxs-lookup"><span data-stu-id="e8506-104">tblPrincipalAffiliations contains the principal affiliations that describe memberships in locations, including Active Directory Domain Services security groups, in Active Directory containers, in domains.</span></span>
  
<span data-ttu-id="e8506-105">**列**</span><span class="sxs-lookup"><span data-stu-id="e8506-105">**Columns**</span></span>

|<span data-ttu-id="e8506-106">**列**</span><span class="sxs-lookup"><span data-stu-id="e8506-106">**Column**</span></span>|<span data-ttu-id="e8506-107">**型**</span><span class="sxs-lookup"><span data-stu-id="e8506-107">**Type**</span></span>|<span data-ttu-id="e8506-108">**説明**</span><span class="sxs-lookup"><span data-stu-id="e8506-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="e8506-109">principalID</span><span class="sxs-lookup"><span data-stu-id="e8506-109">principalID</span></span>  <br/> |<span data-ttu-id="e8506-110">int 型、null でないです。</span><span class="sxs-lookup"><span data-stu-id="e8506-110">int, not null</span></span>  <br/> |<span data-ttu-id="e8506-111">関連のプリンシパルの ID です。</span><span class="sxs-lookup"><span data-stu-id="e8506-111">ID of the affiliated principal.</span></span>  <br/> |
|<span data-ttu-id="e8506-112">affiliationID</span><span class="sxs-lookup"><span data-stu-id="e8506-112">affiliationID</span></span>  <br/> |<span data-ttu-id="e8506-113">int 型、null でないです。</span><span class="sxs-lookup"><span data-stu-id="e8506-113">int, not null</span></span>  <br/> |<span data-ttu-id="e8506-114">所属を表すプリンシパルの ID です。</span><span class="sxs-lookup"><span data-stu-id="e8506-114">ID of the principal representing the affiliation.</span></span> <span data-ttu-id="e8506-115">(システム ・ ユーザー ・ タイプ) を除く各主体が、自己の所属もします。</span><span class="sxs-lookup"><span data-stu-id="e8506-115">Each principal (except system-user-types) has a self-affiliation as well.</span></span>  <br/> |
|<span data-ttu-id="e8506-116">インデックス</span><span class="sxs-lookup"><span data-stu-id="e8506-116">index</span></span>  <br/> |<span data-ttu-id="e8506-117">int 型、null でないです。</span><span class="sxs-lookup"><span data-stu-id="e8506-117">int, not null</span></span>  <br/> |<span data-ttu-id="e8506-118">インデックスです。</span><span class="sxs-lookup"><span data-stu-id="e8506-118">Index.</span></span> <span data-ttu-id="e8506-119">自己所属の値は-1 になり、他の団体の順番に各 1 \<principalID、affiliationId\>バケットです。</span><span class="sxs-lookup"><span data-stu-id="e8506-119">The value for self-affiliations is -1, and for the other affiliations it increases sequentially from 1 within each \<principalID, affiliationId\> bucket.</span></span>  <br/> |
|<span data-ttu-id="e8506-120">updatedBy</span><span class="sxs-lookup"><span data-stu-id="e8506-120">updatedBy</span></span>  <br/> |<span data-ttu-id="e8506-121">int 型、null でないです。</span><span class="sxs-lookup"><span data-stu-id="e8506-121">int, not null</span></span>  <br/> |<span data-ttu-id="e8506-122">最新のアップデートを行った主体。</span><span class="sxs-lookup"><span data-stu-id="e8506-122">Principal that did the latest update.</span></span> <span data-ttu-id="e8506-123">これは、通常、1 で、作業中のディレクトリ同期です。</span><span class="sxs-lookup"><span data-stu-id="e8506-123">This is usually 1, which means Active Directory Sync.</span></span>  <br/> |
   
<span data-ttu-id="e8506-124">**キー**</span><span class="sxs-lookup"><span data-stu-id="e8506-124">**Keys**</span></span>

|<span data-ttu-id="e8506-125">**列**</span><span class="sxs-lookup"><span data-stu-id="e8506-125">**Columns**</span></span>|<span data-ttu-id="e8506-126">**説明**</span><span class="sxs-lookup"><span data-stu-id="e8506-126">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="e8506-127">\<principalID、インデックス、affiliationID\></span><span class="sxs-lookup"><span data-stu-id="e8506-127">\<principalID, index, affiliationID\></span></span>  <br/> |<span data-ttu-id="e8506-128">プライマリ ・ キーです。</span><span class="sxs-lookup"><span data-stu-id="e8506-128">Primary key.</span></span>  <br/> |
|<span data-ttu-id="e8506-129">principalID</span><span class="sxs-lookup"><span data-stu-id="e8506-129">principalID</span></span>  <br/> |<span data-ttu-id="e8506-130">TblPrincipal.prinID テーブル内の参照と外部キーです。</span><span class="sxs-lookup"><span data-stu-id="e8506-130">Foreign key with lookup in tblPrincipal.prinID table.</span></span>  <br/> |
|<span data-ttu-id="e8506-131">affiliationID</span><span class="sxs-lookup"><span data-stu-id="e8506-131">affiliationID</span></span>  <br/> |<span data-ttu-id="e8506-132">TblPrincipal.prinID テーブル内の参照と外部キーです。</span><span class="sxs-lookup"><span data-stu-id="e8506-132">Foreign key with lookup in tblPrincipal.prinID table.</span></span>  <br/> |
   

