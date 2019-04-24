---
title: tblPrincipalRole
ms.reviewer: ''
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
ms.openlocfilehash: 69cfb0cb2b821064801a07510758514bb5d33128
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "32212454"
---
# <a name="tblprincipalrole"></a><span data-ttu-id="b7310-103">tblPrincipalRole</span><span class="sxs-lookup"><span data-stu-id="b7310-103">tblPrincipalRole</span></span>
 
<span data-ttu-id="b7310-104">tblPrincipalRole には、ノードに割り当てられている、明確な役割が含まれています。</span><span class="sxs-lookup"><span data-stu-id="b7310-104">tblPrincipalRole contains explicit roles assigned to nodes.</span></span>
  
<span data-ttu-id="b7310-105">**列**</span><span class="sxs-lookup"><span data-stu-id="b7310-105">**Columns**</span></span>

|<span data-ttu-id="b7310-106">**列**</span><span class="sxs-lookup"><span data-stu-id="b7310-106">**Column**</span></span>|<span data-ttu-id="b7310-107">**型**</span><span class="sxs-lookup"><span data-stu-id="b7310-107">**Type**</span></span>|<span data-ttu-id="b7310-108">**説明**</span><span class="sxs-lookup"><span data-stu-id="b7310-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="b7310-109">prinRoleNodeID</span><span class="sxs-lookup"><span data-stu-id="b7310-109">prinRoleNodeID</span></span>  <br/> |<span data-ttu-id="b7310-110">int 型、null でないです。</span><span class="sxs-lookup"><span data-stu-id="b7310-110">int, not null</span></span>  <br/> |<span data-ttu-id="b7310-111">ロールに適用するノードの ID。</span><span class="sxs-lookup"><span data-stu-id="b7310-111">Node ID that the role applies to.</span></span>  <br/> |
|<span data-ttu-id="b7310-112">prinRolePrinID</span><span class="sxs-lookup"><span data-stu-id="b7310-112">prinRolePrinID</span></span>  <br/> |<span data-ttu-id="b7310-113">int 型、null でないです。</span><span class="sxs-lookup"><span data-stu-id="b7310-113">int, not null</span></span>  <br/> |<span data-ttu-id="b7310-114">プリンシパルの id。</span><span class="sxs-lookup"><span data-stu-id="b7310-114">Principal ID.</span></span>  <br/> |
|<span data-ttu-id="b7310-115">prinRoleTypeID</span><span class="sxs-lookup"><span data-stu-id="b7310-115">prinRoleTypeID</span></span>  <br/> |<span data-ttu-id="b7310-116">int 型、null でないです。</span><span class="sxs-lookup"><span data-stu-id="b7310-116">int, not null</span></span>  <br/> |<span data-ttu-id="b7310-117">(TblRoleType) からの役割の種類の ID です。</span><span class="sxs-lookup"><span data-stu-id="b7310-117">Role type ID (from tblRoleType).</span></span>  <br/> |
|<span data-ttu-id="b7310-118">prinRoleUpdatedBy</span><span class="sxs-lookup"><span data-stu-id="b7310-118">prinRoleUpdatedBy</span></span>  <br/> |<span data-ttu-id="b7310-119">int 型、null でないです。</span><span class="sxs-lookup"><span data-stu-id="b7310-119">int, not null</span></span>  <br/> |<span data-ttu-id="b7310-120">このエントリを最後に更新したプリンシパルの ID です。</span><span class="sxs-lookup"><span data-stu-id="b7310-120">ID of the principal that last updated this entry.</span></span>  <br/> |
   
<span data-ttu-id="b7310-121">**キー**</span><span class="sxs-lookup"><span data-stu-id="b7310-121">**Keys**</span></span>

|<span data-ttu-id="b7310-122">**列**</span><span class="sxs-lookup"><span data-stu-id="b7310-122">**Column**</span></span>|<span data-ttu-id="b7310-123">**説明**</span><span class="sxs-lookup"><span data-stu-id="b7310-123">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="b7310-124">\<prinRoleNodeID、prinRolePrinID、prinRoleTypeID\></span><span class="sxs-lookup"><span data-stu-id="b7310-124">\<prinRoleNodeID, prinRolePrinID, prinRoleTypeID\></span></span>  <br/> |<span data-ttu-id="b7310-125">プライマリ ・ キーです。</span><span class="sxs-lookup"><span data-stu-id="b7310-125">Primary key.</span></span>  <br/> |
|<span data-ttu-id="b7310-126">prinRoleNodeID</span><span class="sxs-lookup"><span data-stu-id="b7310-126">prinRoleNodeID</span></span>  <br/> |<span data-ttu-id="b7310-127">TblNode.nodeID テーブル内の参照と外部キーです。</span><span class="sxs-lookup"><span data-stu-id="b7310-127">Foreign key with lookup in tblNode.nodeID table.</span></span>  <br/> |
|<span data-ttu-id="b7310-128">prinRolePrinID</span><span class="sxs-lookup"><span data-stu-id="b7310-128">prinRolePrinID</span></span>  <br/> |<span data-ttu-id="b7310-129">TblPrincipal.prinID テーブル内の参照と外部キーです。</span><span class="sxs-lookup"><span data-stu-id="b7310-129">Foreign key with lookup in tblPrincipal.prinID table.</span></span>  <br/> |
|<span data-ttu-id="b7310-130">prinRoleTypeID</span><span class="sxs-lookup"><span data-stu-id="b7310-130">prinRoleTypeID</span></span>  <br/> |<span data-ttu-id="b7310-131">TblRoleType.rtypeID テーブル内の参照と外部キーです。</span><span class="sxs-lookup"><span data-stu-id="b7310-131">Foreign key with lookup in tblRoleType.rtypeID table.</span></span>  <br/> |
   

