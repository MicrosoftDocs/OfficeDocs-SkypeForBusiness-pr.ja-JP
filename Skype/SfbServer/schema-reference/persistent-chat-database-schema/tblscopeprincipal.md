---
title: tblScopePrincipal
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
ms.assetid: 422d6c7f-7ba7-4dd4-bacc-95ace47959ff
description: tblScopePrincipal には、ノードに割り当てられるスコープが含まれます。
ms.openlocfilehash: efda792ab6f6c6cc7b188a9dffdaa7c324b24797
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49831517"
---
# <a name="tblscopeprincipal"></a><span data-ttu-id="b2328-103">tblScopePrincipal</span><span class="sxs-lookup"><span data-stu-id="b2328-103">tblScopePrincipal</span></span>
 
<span data-ttu-id="b2328-104">tblScopePrincipal には、ノードに割り当てられるスコープが含まれます。</span><span class="sxs-lookup"><span data-stu-id="b2328-104">tblScopePrincipal contains scopes assigned to nodes.</span></span>
  
<span data-ttu-id="b2328-105">**Columns**</span><span class="sxs-lookup"><span data-stu-id="b2328-105">**Columns**</span></span>

|<span data-ttu-id="b2328-106">**列**</span><span class="sxs-lookup"><span data-stu-id="b2328-106">**Column**</span></span>|<span data-ttu-id="b2328-107">**型**</span><span class="sxs-lookup"><span data-stu-id="b2328-107">**Type**</span></span>|<span data-ttu-id="b2328-108">**説明**</span><span class="sxs-lookup"><span data-stu-id="b2328-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="b2328-109">scopeNodeID</span><span class="sxs-lookup"><span data-stu-id="b2328-109">scopeNodeID</span></span>  <br/> |<span data-ttu-id="b2328-110">NULL でない int</span><span class="sxs-lookup"><span data-stu-id="b2328-110">int, not null</span></span>  <br/> |<span data-ttu-id="b2328-111">範囲の適用先ノード ID。</span><span class="sxs-lookup"><span data-stu-id="b2328-111">Node ID that the scope applies to.</span></span>  <br/> |
|<span data-ttu-id="b2328-112">scopePrinID</span><span class="sxs-lookup"><span data-stu-id="b2328-112">scopePrinID</span></span>  <br/> |<span data-ttu-id="b2328-113">NULL でない int</span><span class="sxs-lookup"><span data-stu-id="b2328-113">int, not null</span></span>  <br/> |<span data-ttu-id="b2328-114">プリンシパル ID。</span><span class="sxs-lookup"><span data-stu-id="b2328-114">Principal ID.</span></span>  <br/> |
|<span data-ttu-id="b2328-115">scopeIsDenied</span><span class="sxs-lookup"><span data-stu-id="b2328-115">scopeIsDenied</span></span>  <br/> |<span data-ttu-id="b2328-116">NULL でない bit</span><span class="sxs-lookup"><span data-stu-id="b2328-116">bit, not null</span></span>  <br/> |<span data-ttu-id="b2328-117">スコープの種類が [拒否] の場合は True、[許可] の場合は False。</span><span class="sxs-lookup"><span data-stu-id="b2328-117">True if type of scope is Deny; False if Allow.</span></span>  <br/> |
|<span data-ttu-id="b2328-118">scopeUpdatedBy</span><span class="sxs-lookup"><span data-stu-id="b2328-118">scopeUpdatedBy</span></span>  <br/> |<span data-ttu-id="b2328-119">NULL でない int</span><span class="sxs-lookup"><span data-stu-id="b2328-119">int, not null</span></span>  <br/> |<span data-ttu-id="b2328-120">このエントリを最後に更新したプリンシパルの ID。</span><span class="sxs-lookup"><span data-stu-id="b2328-120">ID of the principal that last updated this entry.</span></span>  <br/> |
   
<span data-ttu-id="b2328-121">**Keys**</span><span class="sxs-lookup"><span data-stu-id="b2328-121">**Keys**</span></span>

|<span data-ttu-id="b2328-122">**列**</span><span class="sxs-lookup"><span data-stu-id="b2328-122">**Column**</span></span>|<span data-ttu-id="b2328-123">**説明**</span><span class="sxs-lookup"><span data-stu-id="b2328-123">**Description**</span></span>|
|:-----|:-----|
|\<scopeNodeID, scopePrinID\>  <br/> |<span data-ttu-id="b2328-124">主キー。</span><span class="sxs-lookup"><span data-stu-id="b2328-124">Primary key.</span></span>  <br/> |
|<span data-ttu-id="b2328-125">scopeNodeID</span><span class="sxs-lookup"><span data-stu-id="b2328-125">scopeNodeID</span></span>  <br/> |<span data-ttu-id="b2328-126">tblNode.nodeID テーブル内の参照による外部キー。</span><span class="sxs-lookup"><span data-stu-id="b2328-126">Foreign key with lookup in tblNode.nodeID table.</span></span>  <br/> |
|<span data-ttu-id="b2328-127">scopePrinID</span><span class="sxs-lookup"><span data-stu-id="b2328-127">scopePrinID</span></span>  <br/> |<span data-ttu-id="b2328-128">tblPrincipal.prinID テーブル内の参照による外部キー。</span><span class="sxs-lookup"><span data-stu-id="b2328-128">Foreign key with lookup in tblPrincipal.prinID table.</span></span>  <br/> |
   

