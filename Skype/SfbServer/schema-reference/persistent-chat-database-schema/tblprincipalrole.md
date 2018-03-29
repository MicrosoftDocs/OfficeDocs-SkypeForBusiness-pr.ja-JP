---
title: tblPrincipalRole
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: dcd16dc1-a66c-4720-a48f-ec8b28337383
description: tblPrincipalRole には、ノードに割り当てられている、明確な役割が含まれています。
ms.openlocfilehash: 0e6c7f60f372bc14542567ccaa1b1b1a837c6c6d
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/28/2018
---
# <a name="tblprincipalrole"></a><span data-ttu-id="5c0df-103">tblPrincipalRole</span><span class="sxs-lookup"><span data-stu-id="5c0df-103">tblPrincipalRole</span></span>
 
<span data-ttu-id="5c0df-104">tblPrincipalRole には、ノードに割り当てられている、明確な役割が含まれています。</span><span class="sxs-lookup"><span data-stu-id="5c0df-104">tblPrincipalRole contains explicit roles assigned to nodes.</span></span>
  
<span data-ttu-id="5c0df-105">**列**</span><span class="sxs-lookup"><span data-stu-id="5c0df-105">**Columns**</span></span>

|<span data-ttu-id="5c0df-106">**列**</span><span class="sxs-lookup"><span data-stu-id="5c0df-106">**Column**</span></span>|<span data-ttu-id="5c0df-107">**タイプ**</span><span class="sxs-lookup"><span data-stu-id="5c0df-107">**Type**</span></span>|<span data-ttu-id="5c0df-108">**説明**</span><span class="sxs-lookup"><span data-stu-id="5c0df-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="5c0df-109">prinRoleNodeID</span><span class="sxs-lookup"><span data-stu-id="5c0df-109">prinRoleNodeID</span></span>  <br/> |<span data-ttu-id="5c0df-110">int 型、null でないです。</span><span class="sxs-lookup"><span data-stu-id="5c0df-110">int, not null</span></span>  <br/> |<span data-ttu-id="5c0df-111">ロールに適用するノードの ID。</span><span class="sxs-lookup"><span data-stu-id="5c0df-111">Node ID that the role applies to.</span></span>  <br/> |
|<span data-ttu-id="5c0df-112">prinRolePrinID</span><span class="sxs-lookup"><span data-stu-id="5c0df-112">prinRolePrinID</span></span>  <br/> |<span data-ttu-id="5c0df-113">int 型、null でないです。</span><span class="sxs-lookup"><span data-stu-id="5c0df-113">int, not null</span></span>  <br/> |<span data-ttu-id="5c0df-114">プリンシパルの id。</span><span class="sxs-lookup"><span data-stu-id="5c0df-114">Principal ID.</span></span>  <br/> |
|<span data-ttu-id="5c0df-115">prinRoleTypeID</span><span class="sxs-lookup"><span data-stu-id="5c0df-115">prinRoleTypeID</span></span>  <br/> |<span data-ttu-id="5c0df-116">int 型、null でないです。</span><span class="sxs-lookup"><span data-stu-id="5c0df-116">int, not null</span></span>  <br/> |<span data-ttu-id="5c0df-117">(TblRoleType) からの役割の種類の ID です。</span><span class="sxs-lookup"><span data-stu-id="5c0df-117">Role type ID (from tblRoleType).</span></span>  <br/> |
|<span data-ttu-id="5c0df-118">prinRoleUpdatedBy</span><span class="sxs-lookup"><span data-stu-id="5c0df-118">prinRoleUpdatedBy</span></span>  <br/> |<span data-ttu-id="5c0df-119">int 型、null でないです。</span><span class="sxs-lookup"><span data-stu-id="5c0df-119">int, not null</span></span>  <br/> |<span data-ttu-id="5c0df-120">このエントリを最後に更新したプリンシパルの ID です。</span><span class="sxs-lookup"><span data-stu-id="5c0df-120">ID of the principal that last updated this entry.</span></span>  <br/> |
   
<span data-ttu-id="5c0df-121">**キー**</span><span class="sxs-lookup"><span data-stu-id="5c0df-121">**Keys**</span></span>

|<span data-ttu-id="5c0df-122">**列**</span><span class="sxs-lookup"><span data-stu-id="5c0df-122">**Column**</span></span>|<span data-ttu-id="5c0df-123">**説明**</span><span class="sxs-lookup"><span data-stu-id="5c0df-123">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="5c0df-124">\<prinRoleNodeID、prinRolePrinID、prinRoleTypeID\></span><span class="sxs-lookup"><span data-stu-id="5c0df-124">\<prinRoleNodeID, prinRolePrinID, prinRoleTypeID\></span></span>  <br/> |<span data-ttu-id="5c0df-125">プライマリ ・ キーです。</span><span class="sxs-lookup"><span data-stu-id="5c0df-125">Primary key.</span></span>  <br/> |
|<span data-ttu-id="5c0df-126">prinRoleNodeID</span><span class="sxs-lookup"><span data-stu-id="5c0df-126">prinRoleNodeID</span></span>  <br/> |<span data-ttu-id="5c0df-127">TblNode.nodeID テーブル内の参照と外部キーです。</span><span class="sxs-lookup"><span data-stu-id="5c0df-127">Foreign key with lookup in tblNode.nodeID table.</span></span>  <br/> |
|<span data-ttu-id="5c0df-128">prinRolePrinID</span><span class="sxs-lookup"><span data-stu-id="5c0df-128">prinRolePrinID</span></span>  <br/> |<span data-ttu-id="5c0df-129">TblPrincipal.prinID テーブル内の参照と外部キーです。</span><span class="sxs-lookup"><span data-stu-id="5c0df-129">Foreign key with lookup in tblPrincipal.prinID table.</span></span>  <br/> |
|<span data-ttu-id="5c0df-130">prinRoleTypeID</span><span class="sxs-lookup"><span data-stu-id="5c0df-130">prinRoleTypeID</span></span>  <br/> |<span data-ttu-id="5c0df-131">TblRoleType.rtypeID テーブル内の参照と外部キーです。</span><span class="sxs-lookup"><span data-stu-id="5c0df-131">Foreign key with lookup in tblRoleType.rtypeID table.</span></span>  <br/> |
   

