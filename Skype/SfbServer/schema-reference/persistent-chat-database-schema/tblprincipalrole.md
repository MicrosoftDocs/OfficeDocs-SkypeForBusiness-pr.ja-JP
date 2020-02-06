---
title: tblPrincipalRole
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
ms.assetid: dcd16dc1-a66c-4720-a48f-ec8b28337383
description: tblPrincipalRole には、ノードに割り当てられている明示的な役割が含まれます。
ms.openlocfilehash: 1cc606ec3825bb664d4123154e97fabb15678cfd
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2020
ms.locfileid: "41813365"
---
# <a name="tblprincipalrole"></a><span data-ttu-id="3499a-103">tblPrincipalRole</span><span class="sxs-lookup"><span data-stu-id="3499a-103">tblPrincipalRole</span></span>
 
<span data-ttu-id="3499a-104">tblPrincipalRole には、ノードに割り当てられている明示的な役割が含まれます。</span><span class="sxs-lookup"><span data-stu-id="3499a-104">tblPrincipalRole contains explicit roles assigned to nodes.</span></span>
  
<span data-ttu-id="3499a-105">**行**</span><span class="sxs-lookup"><span data-stu-id="3499a-105">**Columns**</span></span>

|<span data-ttu-id="3499a-106">**列**</span><span class="sxs-lookup"><span data-stu-id="3499a-106">**Column**</span></span>|<span data-ttu-id="3499a-107">**種類**</span><span class="sxs-lookup"><span data-stu-id="3499a-107">**Type**</span></span>|<span data-ttu-id="3499a-108">**説明**</span><span class="sxs-lookup"><span data-stu-id="3499a-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="3499a-109">Prinrolid</span><span class="sxs-lookup"><span data-stu-id="3499a-109">prinRoleNodeID</span></span>  <br/> |<span data-ttu-id="3499a-110">int (null ではない)</span><span class="sxs-lookup"><span data-stu-id="3499a-110">int, not null</span></span>  <br/> |<span data-ttu-id="3499a-111">役割が適用されるノード ID。</span><span class="sxs-lookup"><span data-stu-id="3499a-111">Node ID that the role applies to.</span></span>  <br/> |
|<span data-ttu-id="3499a-112">prinRolePrinID</span><span class="sxs-lookup"><span data-stu-id="3499a-112">prinRolePrinID</span></span>  <br/> |<span data-ttu-id="3499a-113">int (null ではない)</span><span class="sxs-lookup"><span data-stu-id="3499a-113">int, not null</span></span>  <br/> |<span data-ttu-id="3499a-114">プリンシパル ID。</span><span class="sxs-lookup"><span data-stu-id="3499a-114">Principal ID.</span></span>  <br/> |
|<span data-ttu-id="3499a-115">prinRoleTypeID</span><span class="sxs-lookup"><span data-stu-id="3499a-115">prinRoleTypeID</span></span>  <br/> |<span data-ttu-id="3499a-116">int (null ではない)</span><span class="sxs-lookup"><span data-stu-id="3499a-116">int, not null</span></span>  <br/> |<span data-ttu-id="3499a-117">役割の種類の ID (tblRoleType から)。</span><span class="sxs-lookup"><span data-stu-id="3499a-117">Role type ID (from tblRoleType).</span></span>  <br/> |
|<span data-ttu-id="3499a-118">prinroleupdat</span><span class="sxs-lookup"><span data-stu-id="3499a-118">prinRoleUpdatedBy</span></span>  <br/> |<span data-ttu-id="3499a-119">int (null ではない)</span><span class="sxs-lookup"><span data-stu-id="3499a-119">int, not null</span></span>  <br/> |<span data-ttu-id="3499a-120">このエントリを最後に更新したプリンシパルの ID です。</span><span class="sxs-lookup"><span data-stu-id="3499a-120">ID of the principal that last updated this entry.</span></span>  <br/> |
   
<span data-ttu-id="3499a-121">**機能**</span><span class="sxs-lookup"><span data-stu-id="3499a-121">**Keys**</span></span>

|<span data-ttu-id="3499a-122">**列**</span><span class="sxs-lookup"><span data-stu-id="3499a-122">**Column**</span></span>|<span data-ttu-id="3499a-123">**説明**</span><span class="sxs-lookup"><span data-stu-id="3499a-123">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="3499a-124">\<Prinroldeid、prinRolePrinID、prinRoleTypeID\></span><span class="sxs-lookup"><span data-stu-id="3499a-124">\<prinRoleNodeID, prinRolePrinID, prinRoleTypeID\></span></span>  <br/> |<span data-ttu-id="3499a-125">主キー。</span><span class="sxs-lookup"><span data-stu-id="3499a-125">Primary key.</span></span>  <br/> |
|<span data-ttu-id="3499a-126">Prinrolid</span><span class="sxs-lookup"><span data-stu-id="3499a-126">prinRoleNodeID</span></span>  <br/> |<span data-ttu-id="3499a-127">TblNode テーブルで参照される外部キー。</span><span class="sxs-lookup"><span data-stu-id="3499a-127">Foreign key with lookup in tblNode.nodeID table.</span></span>  <br/> |
|<span data-ttu-id="3499a-128">prinRolePrinID</span><span class="sxs-lookup"><span data-stu-id="3499a-128">prinRolePrinID</span></span>  <br/> |<span data-ttu-id="3499a-129">TblPrincipal Id テーブルで参照される外部キー。</span><span class="sxs-lookup"><span data-stu-id="3499a-129">Foreign key with lookup in tblPrincipal.prinID table.</span></span>  <br/> |
|<span data-ttu-id="3499a-130">prinRoleTypeID</span><span class="sxs-lookup"><span data-stu-id="3499a-130">prinRoleTypeID</span></span>  <br/> |<span data-ttu-id="3499a-131">TblRoleType の Typeid テーブルで参照される外部キー。</span><span class="sxs-lookup"><span data-stu-id="3499a-131">Foreign key with lookup in tblRoleType.rtypeID table.</span></span>  <br/> |
   

