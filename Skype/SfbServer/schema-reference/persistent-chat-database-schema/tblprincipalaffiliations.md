---
title: tblPrincipalAffiliations
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
ms.assetid: 45fd8484-5837-44d2-85bb-45c83546607c
description: tblPrincipalAffiliations には、active Directory ドメインサービスセキュリティグループなどの場所のメンバーシップを、ドメインの Active Directory コンテナーで説明するプリンシパルの所属が含まれています。
ms.openlocfilehash: 542bcc333d815b0577aec1fb11d4070540150d3c
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2020
ms.locfileid: "41814475"
---
# <a name="tblprincipalaffiliations"></a><span data-ttu-id="c3b01-103">tblPrincipalAffiliations</span><span class="sxs-lookup"><span data-stu-id="c3b01-103">tblPrincipalAffiliations</span></span>
 
<span data-ttu-id="c3b01-104">tblPrincipalAffiliations には、active Directory ドメインサービスセキュリティグループなどの場所のメンバーシップを、ドメインの Active Directory コンテナーで説明するプリンシパルの所属が含まれています。</span><span class="sxs-lookup"><span data-stu-id="c3b01-104">tblPrincipalAffiliations contains the principal affiliations that describe memberships in locations, including Active Directory Domain Services security groups, in Active Directory containers, in domains.</span></span>
  
<span data-ttu-id="c3b01-105">**行**</span><span class="sxs-lookup"><span data-stu-id="c3b01-105">**Columns**</span></span>

|<span data-ttu-id="c3b01-106">**列**</span><span class="sxs-lookup"><span data-stu-id="c3b01-106">**Column**</span></span>|<span data-ttu-id="c3b01-107">**種類**</span><span class="sxs-lookup"><span data-stu-id="c3b01-107">**Type**</span></span>|<span data-ttu-id="c3b01-108">**説明**</span><span class="sxs-lookup"><span data-stu-id="c3b01-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="c3b01-109">principalID</span><span class="sxs-lookup"><span data-stu-id="c3b01-109">principalID</span></span>  <br/> |<span data-ttu-id="c3b01-110">int (null ではない)</span><span class="sxs-lookup"><span data-stu-id="c3b01-110">int, not null</span></span>  <br/> |<span data-ttu-id="c3b01-111">関連主体の ID です。</span><span class="sxs-lookup"><span data-stu-id="c3b01-111">ID of the affiliated principal.</span></span>  <br/> |
|<span data-ttu-id="c3b01-112">affiliationID</span><span class="sxs-lookup"><span data-stu-id="c3b01-112">affiliationID</span></span>  <br/> |<span data-ttu-id="c3b01-113">int (null ではない)</span><span class="sxs-lookup"><span data-stu-id="c3b01-113">int, not null</span></span>  <br/> |<span data-ttu-id="c3b01-114">所属を表すプリンシパルの ID です。</span><span class="sxs-lookup"><span data-stu-id="c3b01-114">ID of the principal representing the affiliation.</span></span> <span data-ttu-id="c3b01-115">各プリンシパル (システムユーザーの種類を除く) には、自己所属も含まれています。</span><span class="sxs-lookup"><span data-stu-id="c3b01-115">Each principal (except system-user-types) has a self-affiliation as well.</span></span>  <br/> |
|<span data-ttu-id="c3b01-116">位置</span><span class="sxs-lookup"><span data-stu-id="c3b01-116">index</span></span>  <br/> |<span data-ttu-id="c3b01-117">int (null ではない)</span><span class="sxs-lookup"><span data-stu-id="c3b01-117">int, not null</span></span>  <br/> |<span data-ttu-id="c3b01-118">位置.</span><span class="sxs-lookup"><span data-stu-id="c3b01-118">Index.</span></span> <span data-ttu-id="c3b01-119">自己所属の値は-1 であり、その他の所属については、principalID の各\<\>バケット内の1から順に1が増加します。</span><span class="sxs-lookup"><span data-stu-id="c3b01-119">The value for self-affiliations is -1, and for the other affiliations it increases sequentially from 1 within each \<principalID, affiliationId\> bucket.</span></span>  <br/> |
|<span data-ttu-id="c3b01-120">updatedBy</span><span class="sxs-lookup"><span data-stu-id="c3b01-120">updatedBy</span></span>  <br/> |<span data-ttu-id="c3b01-121">int (null ではない)</span><span class="sxs-lookup"><span data-stu-id="c3b01-121">int, not null</span></span>  <br/> |<span data-ttu-id="c3b01-122">最新の更新プログラムを実行したプリンシパル。</span><span class="sxs-lookup"><span data-stu-id="c3b01-122">Principal that did the latest update.</span></span> <span data-ttu-id="c3b01-123">これは通常1で、Active Directory の同期を意味します。</span><span class="sxs-lookup"><span data-stu-id="c3b01-123">This is usually 1, which means Active Directory Sync.</span></span>  <br/> |
   
<span data-ttu-id="c3b01-124">**機能**</span><span class="sxs-lookup"><span data-stu-id="c3b01-124">**Keys**</span></span>

|<span data-ttu-id="c3b01-125">**行**</span><span class="sxs-lookup"><span data-stu-id="c3b01-125">**Columns**</span></span>|<span data-ttu-id="c3b01-126">**説明**</span><span class="sxs-lookup"><span data-stu-id="c3b01-126">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="c3b01-127">\<principalID、index、affiliationID\></span><span class="sxs-lookup"><span data-stu-id="c3b01-127">\<principalID, index, affiliationID\></span></span>  <br/> |<span data-ttu-id="c3b01-128">主キー。</span><span class="sxs-lookup"><span data-stu-id="c3b01-128">Primary key.</span></span>  <br/> |
|<span data-ttu-id="c3b01-129">principalID</span><span class="sxs-lookup"><span data-stu-id="c3b01-129">principalID</span></span>  <br/> |<span data-ttu-id="c3b01-130">TblPrincipal Id テーブルで参照される外部キー。</span><span class="sxs-lookup"><span data-stu-id="c3b01-130">Foreign key with lookup in tblPrincipal.prinID table.</span></span>  <br/> |
|<span data-ttu-id="c3b01-131">affiliationID</span><span class="sxs-lookup"><span data-stu-id="c3b01-131">affiliationID</span></span>  <br/> |<span data-ttu-id="c3b01-132">TblPrincipal Id テーブルで参照される外部キー。</span><span class="sxs-lookup"><span data-stu-id="c3b01-132">Foreign key with lookup in tblPrincipal.prinID table.</span></span>  <br/> |
   

