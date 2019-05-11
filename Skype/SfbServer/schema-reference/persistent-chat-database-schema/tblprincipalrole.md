---
title: tblPrincipalRole
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: dcd16dc1-a66c-4720-a48f-ec8b28337383
description: tblPrincipalRole には、ノードに割り当てられている、明確な役割が含まれています。
ms.openlocfilehash: 7c144f2f531af58c7c5693b28b224a2ee4456783
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "33904182"
---
# <a name="tblprincipalrole"></a><span data-ttu-id="63c6b-103">tblPrincipalRole</span><span class="sxs-lookup"><span data-stu-id="63c6b-103">tblPrincipalRole</span></span>
 
<span data-ttu-id="63c6b-104">tblPrincipalRole には、ノードに割り当てられている、明確な役割が含まれています。</span><span class="sxs-lookup"><span data-stu-id="63c6b-104">tblPrincipalRole contains explicit roles assigned to nodes.</span></span>
  
<span data-ttu-id="63c6b-105">**列**</span><span class="sxs-lookup"><span data-stu-id="63c6b-105">**Columns**</span></span>

|<span data-ttu-id="63c6b-106">**列**</span><span class="sxs-lookup"><span data-stu-id="63c6b-106">**Column**</span></span>|<span data-ttu-id="63c6b-107">**型**</span><span class="sxs-lookup"><span data-stu-id="63c6b-107">**Type**</span></span>|<span data-ttu-id="63c6b-108">**説明**</span><span class="sxs-lookup"><span data-stu-id="63c6b-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="63c6b-109">prinRoleNodeID</span><span class="sxs-lookup"><span data-stu-id="63c6b-109">prinRoleNodeID</span></span>  <br/> |<span data-ttu-id="63c6b-110">int 型、null でないです。</span><span class="sxs-lookup"><span data-stu-id="63c6b-110">int, not null</span></span>  <br/> |<span data-ttu-id="63c6b-111">ロールに適用するノードの ID。</span><span class="sxs-lookup"><span data-stu-id="63c6b-111">Node ID that the role applies to.</span></span>  <br/> |
|<span data-ttu-id="63c6b-112">prinRolePrinID</span><span class="sxs-lookup"><span data-stu-id="63c6b-112">prinRolePrinID</span></span>  <br/> |<span data-ttu-id="63c6b-113">int 型、null でないです。</span><span class="sxs-lookup"><span data-stu-id="63c6b-113">int, not null</span></span>  <br/> |<span data-ttu-id="63c6b-114">プリンシパルの id。</span><span class="sxs-lookup"><span data-stu-id="63c6b-114">Principal ID.</span></span>  <br/> |
|<span data-ttu-id="63c6b-115">prinRoleTypeID</span><span class="sxs-lookup"><span data-stu-id="63c6b-115">prinRoleTypeID</span></span>  <br/> |<span data-ttu-id="63c6b-116">int 型、null でないです。</span><span class="sxs-lookup"><span data-stu-id="63c6b-116">int, not null</span></span>  <br/> |<span data-ttu-id="63c6b-117">(TblRoleType) からの役割の種類の ID です。</span><span class="sxs-lookup"><span data-stu-id="63c6b-117">Role type ID (from tblRoleType).</span></span>  <br/> |
|<span data-ttu-id="63c6b-118">prinRoleUpdatedBy</span><span class="sxs-lookup"><span data-stu-id="63c6b-118">prinRoleUpdatedBy</span></span>  <br/> |<span data-ttu-id="63c6b-119">int 型、null でないです。</span><span class="sxs-lookup"><span data-stu-id="63c6b-119">int, not null</span></span>  <br/> |<span data-ttu-id="63c6b-120">このエントリを最後に更新したプリンシパルの ID です。</span><span class="sxs-lookup"><span data-stu-id="63c6b-120">ID of the principal that last updated this entry.</span></span>  <br/> |
   
<span data-ttu-id="63c6b-121">**キー**</span><span class="sxs-lookup"><span data-stu-id="63c6b-121">**Keys**</span></span>

|<span data-ttu-id="63c6b-122">**列**</span><span class="sxs-lookup"><span data-stu-id="63c6b-122">**Column**</span></span>|<span data-ttu-id="63c6b-123">**説明**</span><span class="sxs-lookup"><span data-stu-id="63c6b-123">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="63c6b-124">\<prinRoleNodeID、prinRolePrinID、prinRoleTypeID\></span><span class="sxs-lookup"><span data-stu-id="63c6b-124">\<prinRoleNodeID, prinRolePrinID, prinRoleTypeID\></span></span>  <br/> |<span data-ttu-id="63c6b-125">プライマリ ・ キーです。</span><span class="sxs-lookup"><span data-stu-id="63c6b-125">Primary key.</span></span>  <br/> |
|<span data-ttu-id="63c6b-126">prinRoleNodeID</span><span class="sxs-lookup"><span data-stu-id="63c6b-126">prinRoleNodeID</span></span>  <br/> |<span data-ttu-id="63c6b-127">TblNode.nodeID テーブル内の参照と外部キーです。</span><span class="sxs-lookup"><span data-stu-id="63c6b-127">Foreign key with lookup in tblNode.nodeID table.</span></span>  <br/> |
|<span data-ttu-id="63c6b-128">prinRolePrinID</span><span class="sxs-lookup"><span data-stu-id="63c6b-128">prinRolePrinID</span></span>  <br/> |<span data-ttu-id="63c6b-129">TblPrincipal.prinID テーブル内の参照と外部キーです。</span><span class="sxs-lookup"><span data-stu-id="63c6b-129">Foreign key with lookup in tblPrincipal.prinID table.</span></span>  <br/> |
|<span data-ttu-id="63c6b-130">prinRoleTypeID</span><span class="sxs-lookup"><span data-stu-id="63c6b-130">prinRoleTypeID</span></span>  <br/> |<span data-ttu-id="63c6b-131">TblRoleType.rtypeID テーブル内の参照と外部キーです。</span><span class="sxs-lookup"><span data-stu-id="63c6b-131">Foreign key with lookup in tblRoleType.rtypeID table.</span></span>  <br/> |
   

