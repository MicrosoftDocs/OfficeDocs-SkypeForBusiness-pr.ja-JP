---
title: tblPrincipalRole
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
ms.assetid: dcd16dc1-a66c-4720-a48f-ec8b28337383
description: tblPrincipalRole には、ノードに割り当てられた明示的な役割が含まれます。
ms.openlocfilehash: 13c9c25db9ba1dbe281947468bbd834e80417899
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49831557"
---
# <a name="tblprincipalrole"></a><span data-ttu-id="56e05-103">tblPrincipalRole</span><span class="sxs-lookup"><span data-stu-id="56e05-103">tblPrincipalRole</span></span>
 
<span data-ttu-id="56e05-104">tblPrincipalRole には、ノードに割り当てられた明示的な役割が含まれます。</span><span class="sxs-lookup"><span data-stu-id="56e05-104">tblPrincipalRole contains explicit roles assigned to nodes.</span></span>
  
<span data-ttu-id="56e05-105">**Columns**</span><span class="sxs-lookup"><span data-stu-id="56e05-105">**Columns**</span></span>

|<span data-ttu-id="56e05-106">**列**</span><span class="sxs-lookup"><span data-stu-id="56e05-106">**Column**</span></span>|<span data-ttu-id="56e05-107">**型**</span><span class="sxs-lookup"><span data-stu-id="56e05-107">**Type**</span></span>|<span data-ttu-id="56e05-108">**説明**</span><span class="sxs-lookup"><span data-stu-id="56e05-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="56e05-109">prinRoleNodeID</span><span class="sxs-lookup"><span data-stu-id="56e05-109">prinRoleNodeID</span></span>  <br/> |<span data-ttu-id="56e05-110">NULL でない int</span><span class="sxs-lookup"><span data-stu-id="56e05-110">int, not null</span></span>  <br/> |<span data-ttu-id="56e05-111">ロールが適用されるノード ID。</span><span class="sxs-lookup"><span data-stu-id="56e05-111">Node ID that the role applies to.</span></span>  <br/> |
|<span data-ttu-id="56e05-112">prinRolePrinID</span><span class="sxs-lookup"><span data-stu-id="56e05-112">prinRolePrinID</span></span>  <br/> |<span data-ttu-id="56e05-113">NULL でない int</span><span class="sxs-lookup"><span data-stu-id="56e05-113">int, not null</span></span>  <br/> |<span data-ttu-id="56e05-114">プリンシパル ID。</span><span class="sxs-lookup"><span data-stu-id="56e05-114">Principal ID.</span></span>  <br/> |
|<span data-ttu-id="56e05-115">prinRoleTypeID</span><span class="sxs-lookup"><span data-stu-id="56e05-115">prinRoleTypeID</span></span>  <br/> |<span data-ttu-id="56e05-116">NULL でない int</span><span class="sxs-lookup"><span data-stu-id="56e05-116">int, not null</span></span>  <br/> |<span data-ttu-id="56e05-117">ロールの種類 ID (tblRoleType から)。</span><span class="sxs-lookup"><span data-stu-id="56e05-117">Role type ID (from tblRoleType).</span></span>  <br/> |
|<span data-ttu-id="56e05-118">prinRoleUpdatedBy</span><span class="sxs-lookup"><span data-stu-id="56e05-118">prinRoleUpdatedBy</span></span>  <br/> |<span data-ttu-id="56e05-119">NULL でない int</span><span class="sxs-lookup"><span data-stu-id="56e05-119">int, not null</span></span>  <br/> |<span data-ttu-id="56e05-120">このエントリを最後に更新したプリンシパルの ID。</span><span class="sxs-lookup"><span data-stu-id="56e05-120">ID of the principal that last updated this entry.</span></span>  <br/> |
   
<span data-ttu-id="56e05-121">**Keys**</span><span class="sxs-lookup"><span data-stu-id="56e05-121">**Keys**</span></span>

|<span data-ttu-id="56e05-122">**列**</span><span class="sxs-lookup"><span data-stu-id="56e05-122">**Column**</span></span>|<span data-ttu-id="56e05-123">**説明**</span><span class="sxs-lookup"><span data-stu-id="56e05-123">**Description**</span></span>|
|:-----|:-----|
|\<prinRoleNodeID, prinRolePrinID, prinRoleTypeID\>  <br/> |<span data-ttu-id="56e05-124">主キー。</span><span class="sxs-lookup"><span data-stu-id="56e05-124">Primary key.</span></span>  <br/> |
|<span data-ttu-id="56e05-125">prinRoleNodeID</span><span class="sxs-lookup"><span data-stu-id="56e05-125">prinRoleNodeID</span></span>  <br/> |<span data-ttu-id="56e05-126">tblNode.nodeID テーブル内の参照による外部キー。</span><span class="sxs-lookup"><span data-stu-id="56e05-126">Foreign key with lookup in tblNode.nodeID table.</span></span>  <br/> |
|<span data-ttu-id="56e05-127">prinRolePrinID</span><span class="sxs-lookup"><span data-stu-id="56e05-127">prinRolePrinID</span></span>  <br/> |<span data-ttu-id="56e05-128">tblPrincipal.prinID テーブル内の参照による外部キー。</span><span class="sxs-lookup"><span data-stu-id="56e05-128">Foreign key with lookup in tblPrincipal.prinID table.</span></span>  <br/> |
|<span data-ttu-id="56e05-129">prinRoleTypeID</span><span class="sxs-lookup"><span data-stu-id="56e05-129">prinRoleTypeID</span></span>  <br/> |<span data-ttu-id="56e05-130">tblRoleType.rtypeID テーブルを参照する外部キー。</span><span class="sxs-lookup"><span data-stu-id="56e05-130">Foreign key with lookup in tblRoleType.rtypeID table.</span></span>  <br/> |
   

