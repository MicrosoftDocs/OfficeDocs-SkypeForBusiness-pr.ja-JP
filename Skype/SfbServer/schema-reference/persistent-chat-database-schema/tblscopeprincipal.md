---
title: tblScopePrincipal
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 422d6c7f-7ba7-4dd4-bacc-95ace47959ff
description: tblScopePrincipal には、ノードに割り当てられたスコープが含まれます。
ms.openlocfilehash: 2fd8e434710c7bcd266c427fa492e23adacedb22
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2019
ms.locfileid: "34295196"
---
# <a name="tblscopeprincipal"></a><span data-ttu-id="e2fce-103">tblScopePrincipal</span><span class="sxs-lookup"><span data-stu-id="e2fce-103">tblScopePrincipal</span></span>
 
<span data-ttu-id="e2fce-104">tblScopePrincipal には、ノードに割り当てられたスコープが含まれます。</span><span class="sxs-lookup"><span data-stu-id="e2fce-104">tblScopePrincipal contains scopes assigned to nodes.</span></span>
  
<span data-ttu-id="e2fce-105">**行**</span><span class="sxs-lookup"><span data-stu-id="e2fce-105">**Columns**</span></span>

|<span data-ttu-id="e2fce-106">**列**</span><span class="sxs-lookup"><span data-stu-id="e2fce-106">**Column**</span></span>|<span data-ttu-id="e2fce-107">**型**</span><span class="sxs-lookup"><span data-stu-id="e2fce-107">**Type**</span></span>|<span data-ttu-id="e2fce-108">**説明**</span><span class="sxs-lookup"><span data-stu-id="e2fce-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="e2fce-109">scopeNodeID</span><span class="sxs-lookup"><span data-stu-id="e2fce-109">scopeNodeID</span></span>  <br/> |<span data-ttu-id="e2fce-110">int (null ではない)</span><span class="sxs-lookup"><span data-stu-id="e2fce-110">int, not null</span></span>  <br/> |<span data-ttu-id="e2fce-111">スコープが適用されるノード ID。</span><span class="sxs-lookup"><span data-stu-id="e2fce-111">Node ID that the scope applies to.</span></span>  <br/> |
|<span data-ttu-id="e2fce-112">scopePrinID</span><span class="sxs-lookup"><span data-stu-id="e2fce-112">scopePrinID</span></span>  <br/> |<span data-ttu-id="e2fce-113">int (null ではない)</span><span class="sxs-lookup"><span data-stu-id="e2fce-113">int, not null</span></span>  <br/> |<span data-ttu-id="e2fce-114">プリンシパル ID。</span><span class="sxs-lookup"><span data-stu-id="e2fce-114">Principal ID.</span></span>  <br/> |
|<span data-ttu-id="e2fce-115">scopeIsDenied</span><span class="sxs-lookup"><span data-stu-id="e2fce-115">scopeIsDenied</span></span>  <br/> |<span data-ttu-id="e2fce-116">ビット、null ではない</span><span class="sxs-lookup"><span data-stu-id="e2fce-116">bit, not null</span></span>  <br/> |<span data-ttu-id="e2fce-117">スコープの型が拒否された場合は True。許可する場合は False。</span><span class="sxs-lookup"><span data-stu-id="e2fce-117">True if type of scope is Deny; False if Allow.</span></span>  <br/> |
|<span data-ttu-id="e2fce-118">スコープ</span><span class="sxs-lookup"><span data-stu-id="e2fce-118">scopeUpdatedBy</span></span>  <br/> |<span data-ttu-id="e2fce-119">int (null ではない)</span><span class="sxs-lookup"><span data-stu-id="e2fce-119">int, not null</span></span>  <br/> |<span data-ttu-id="e2fce-120">このエントリを最後に更新したプリンシパルの ID です。</span><span class="sxs-lookup"><span data-stu-id="e2fce-120">ID of the principal that last updated this entry.</span></span>  <br/> |
   
<span data-ttu-id="e2fce-121">**機能**</span><span class="sxs-lookup"><span data-stu-id="e2fce-121">**Keys**</span></span>

|<span data-ttu-id="e2fce-122">**列**</span><span class="sxs-lookup"><span data-stu-id="e2fce-122">**Column**</span></span>|<span data-ttu-id="e2fce-123">**説明**</span><span class="sxs-lookup"><span data-stu-id="e2fce-123">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="e2fce-124">\<scopeNodeID、scopePrinID\></span><span class="sxs-lookup"><span data-stu-id="e2fce-124">\<scopeNodeID, scopePrinID\></span></span>  <br/> |<span data-ttu-id="e2fce-125">主キー。</span><span class="sxs-lookup"><span data-stu-id="e2fce-125">Primary key.</span></span>  <br/> |
|<span data-ttu-id="e2fce-126">scopeNodeID</span><span class="sxs-lookup"><span data-stu-id="e2fce-126">scopeNodeID</span></span>  <br/> |<span data-ttu-id="e2fce-127">TblNode テーブルで参照される外部キー。</span><span class="sxs-lookup"><span data-stu-id="e2fce-127">Foreign key with lookup in tblNode.nodeID table.</span></span>  <br/> |
|<span data-ttu-id="e2fce-128">scopePrinID</span><span class="sxs-lookup"><span data-stu-id="e2fce-128">scopePrinID</span></span>  <br/> |<span data-ttu-id="e2fce-129">TblPrincipal Id テーブルで参照される外部キー。</span><span class="sxs-lookup"><span data-stu-id="e2fce-129">Foreign key with lookup in tblPrincipal.prinID table.</span></span>  <br/> |
   

