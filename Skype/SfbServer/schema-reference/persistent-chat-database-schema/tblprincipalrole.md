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
localization_priority: Normal
ms.assetid: dcd16dc1-a66c-4720-a48f-ec8b28337383
description: tblPrincipalRole には、ノードに割り当てられている明示的な役割が含まれます。
ms.openlocfilehash: 9675713afba5753378f4d01b70489d0eee93b8bf
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2019
ms.locfileid: "34295238"
---
# <a name="tblprincipalrole"></a><span data-ttu-id="869d0-103">tblPrincipalRole</span><span class="sxs-lookup"><span data-stu-id="869d0-103">tblPrincipalRole</span></span>
 
<span data-ttu-id="869d0-104">tblPrincipalRole には、ノードに割り当てられている明示的な役割が含まれます。</span><span class="sxs-lookup"><span data-stu-id="869d0-104">tblPrincipalRole contains explicit roles assigned to nodes.</span></span>
  
<span data-ttu-id="869d0-105">**行**</span><span class="sxs-lookup"><span data-stu-id="869d0-105">**Columns**</span></span>

|<span data-ttu-id="869d0-106">**列**</span><span class="sxs-lookup"><span data-stu-id="869d0-106">**Column**</span></span>|<span data-ttu-id="869d0-107">**型**</span><span class="sxs-lookup"><span data-stu-id="869d0-107">**Type**</span></span>|<span data-ttu-id="869d0-108">**説明**</span><span class="sxs-lookup"><span data-stu-id="869d0-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="869d0-109">Prinrolid</span><span class="sxs-lookup"><span data-stu-id="869d0-109">prinRoleNodeID</span></span>  <br/> |<span data-ttu-id="869d0-110">int (null ではない)</span><span class="sxs-lookup"><span data-stu-id="869d0-110">int, not null</span></span>  <br/> |<span data-ttu-id="869d0-111">役割が適用されるノード ID。</span><span class="sxs-lookup"><span data-stu-id="869d0-111">Node ID that the role applies to.</span></span>  <br/> |
|<span data-ttu-id="869d0-112">prinRolePrinID</span><span class="sxs-lookup"><span data-stu-id="869d0-112">prinRolePrinID</span></span>  <br/> |<span data-ttu-id="869d0-113">int (null ではない)</span><span class="sxs-lookup"><span data-stu-id="869d0-113">int, not null</span></span>  <br/> |<span data-ttu-id="869d0-114">プリンシパル ID。</span><span class="sxs-lookup"><span data-stu-id="869d0-114">Principal ID.</span></span>  <br/> |
|<span data-ttu-id="869d0-115">prinRoleTypeID</span><span class="sxs-lookup"><span data-stu-id="869d0-115">prinRoleTypeID</span></span>  <br/> |<span data-ttu-id="869d0-116">int (null ではない)</span><span class="sxs-lookup"><span data-stu-id="869d0-116">int, not null</span></span>  <br/> |<span data-ttu-id="869d0-117">役割の種類の ID (tblRoleType から)。</span><span class="sxs-lookup"><span data-stu-id="869d0-117">Role type ID (from tblRoleType).</span></span>  <br/> |
|<span data-ttu-id="869d0-118">prinroleupdat</span><span class="sxs-lookup"><span data-stu-id="869d0-118">prinRoleUpdatedBy</span></span>  <br/> |<span data-ttu-id="869d0-119">int (null ではない)</span><span class="sxs-lookup"><span data-stu-id="869d0-119">int, not null</span></span>  <br/> |<span data-ttu-id="869d0-120">このエントリを最後に更新したプリンシパルの ID です。</span><span class="sxs-lookup"><span data-stu-id="869d0-120">ID of the principal that last updated this entry.</span></span>  <br/> |
   
<span data-ttu-id="869d0-121">**機能**</span><span class="sxs-lookup"><span data-stu-id="869d0-121">**Keys**</span></span>

|<span data-ttu-id="869d0-122">**列**</span><span class="sxs-lookup"><span data-stu-id="869d0-122">**Column**</span></span>|<span data-ttu-id="869d0-123">**説明**</span><span class="sxs-lookup"><span data-stu-id="869d0-123">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="869d0-124">\<Prinroldeid、prinRolePrinID、prinRoleTypeID\></span><span class="sxs-lookup"><span data-stu-id="869d0-124">\<prinRoleNodeID, prinRolePrinID, prinRoleTypeID\></span></span>  <br/> |<span data-ttu-id="869d0-125">主キー。</span><span class="sxs-lookup"><span data-stu-id="869d0-125">Primary key.</span></span>  <br/> |
|<span data-ttu-id="869d0-126">Prinrolid</span><span class="sxs-lookup"><span data-stu-id="869d0-126">prinRoleNodeID</span></span>  <br/> |<span data-ttu-id="869d0-127">TblNode テーブルで参照される外部キー。</span><span class="sxs-lookup"><span data-stu-id="869d0-127">Foreign key with lookup in tblNode.nodeID table.</span></span>  <br/> |
|<span data-ttu-id="869d0-128">prinRolePrinID</span><span class="sxs-lookup"><span data-stu-id="869d0-128">prinRolePrinID</span></span>  <br/> |<span data-ttu-id="869d0-129">TblPrincipal Id テーブルで参照される外部キー。</span><span class="sxs-lookup"><span data-stu-id="869d0-129">Foreign key with lookup in tblPrincipal.prinID table.</span></span>  <br/> |
|<span data-ttu-id="869d0-130">prinRoleTypeID</span><span class="sxs-lookup"><span data-stu-id="869d0-130">prinRoleTypeID</span></span>  <br/> |<span data-ttu-id="869d0-131">TblRoleType の Typeid テーブルで参照される外部キー。</span><span class="sxs-lookup"><span data-stu-id="869d0-131">Foreign key with lookup in tblRoleType.rtypeID table.</span></span>  <br/> |
   

