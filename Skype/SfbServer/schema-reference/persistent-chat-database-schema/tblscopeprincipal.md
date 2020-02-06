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
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 422d6c7f-7ba7-4dd4-bacc-95ace47959ff
description: tblScopePrincipal には、ノードに割り当てられたスコープが含まれます。
ms.openlocfilehash: 24a38ef4acf3e0d500c7652f5ca418af585343b6
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2020
ms.locfileid: "41812445"
---
# <a name="tblscopeprincipal"></a><span data-ttu-id="5be04-103">tblScopePrincipal</span><span class="sxs-lookup"><span data-stu-id="5be04-103">tblScopePrincipal</span></span>
 
<span data-ttu-id="5be04-104">tblScopePrincipal には、ノードに割り当てられたスコープが含まれます。</span><span class="sxs-lookup"><span data-stu-id="5be04-104">tblScopePrincipal contains scopes assigned to nodes.</span></span>
  
<span data-ttu-id="5be04-105">**行**</span><span class="sxs-lookup"><span data-stu-id="5be04-105">**Columns**</span></span>

|<span data-ttu-id="5be04-106">**列**</span><span class="sxs-lookup"><span data-stu-id="5be04-106">**Column**</span></span>|<span data-ttu-id="5be04-107">**種類**</span><span class="sxs-lookup"><span data-stu-id="5be04-107">**Type**</span></span>|<span data-ttu-id="5be04-108">**説明**</span><span class="sxs-lookup"><span data-stu-id="5be04-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="5be04-109">scopeNodeID</span><span class="sxs-lookup"><span data-stu-id="5be04-109">scopeNodeID</span></span>  <br/> |<span data-ttu-id="5be04-110">int (null ではない)</span><span class="sxs-lookup"><span data-stu-id="5be04-110">int, not null</span></span>  <br/> |<span data-ttu-id="5be04-111">スコープが適用されるノード ID。</span><span class="sxs-lookup"><span data-stu-id="5be04-111">Node ID that the scope applies to.</span></span>  <br/> |
|<span data-ttu-id="5be04-112">scopePrinID</span><span class="sxs-lookup"><span data-stu-id="5be04-112">scopePrinID</span></span>  <br/> |<span data-ttu-id="5be04-113">int (null ではない)</span><span class="sxs-lookup"><span data-stu-id="5be04-113">int, not null</span></span>  <br/> |<span data-ttu-id="5be04-114">プリンシパル ID。</span><span class="sxs-lookup"><span data-stu-id="5be04-114">Principal ID.</span></span>  <br/> |
|<span data-ttu-id="5be04-115">scopeIsDenied</span><span class="sxs-lookup"><span data-stu-id="5be04-115">scopeIsDenied</span></span>  <br/> |<span data-ttu-id="5be04-116">ビット、null ではない</span><span class="sxs-lookup"><span data-stu-id="5be04-116">bit, not null</span></span>  <br/> |<span data-ttu-id="5be04-117">スコープの型が拒否された場合は True。許可する場合は False。</span><span class="sxs-lookup"><span data-stu-id="5be04-117">True if type of scope is Deny; False if Allow.</span></span>  <br/> |
|<span data-ttu-id="5be04-118">スコープ</span><span class="sxs-lookup"><span data-stu-id="5be04-118">scopeUpdatedBy</span></span>  <br/> |<span data-ttu-id="5be04-119">int (null ではない)</span><span class="sxs-lookup"><span data-stu-id="5be04-119">int, not null</span></span>  <br/> |<span data-ttu-id="5be04-120">このエントリを最後に更新したプリンシパルの ID です。</span><span class="sxs-lookup"><span data-stu-id="5be04-120">ID of the principal that last updated this entry.</span></span>  <br/> |
   
<span data-ttu-id="5be04-121">**機能**</span><span class="sxs-lookup"><span data-stu-id="5be04-121">**Keys**</span></span>

|<span data-ttu-id="5be04-122">**列**</span><span class="sxs-lookup"><span data-stu-id="5be04-122">**Column**</span></span>|<span data-ttu-id="5be04-123">**説明**</span><span class="sxs-lookup"><span data-stu-id="5be04-123">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="5be04-124">\<scopeNodeID、scopePrinID\></span><span class="sxs-lookup"><span data-stu-id="5be04-124">\<scopeNodeID, scopePrinID\></span></span>  <br/> |<span data-ttu-id="5be04-125">主キー。</span><span class="sxs-lookup"><span data-stu-id="5be04-125">Primary key.</span></span>  <br/> |
|<span data-ttu-id="5be04-126">scopeNodeID</span><span class="sxs-lookup"><span data-stu-id="5be04-126">scopeNodeID</span></span>  <br/> |<span data-ttu-id="5be04-127">TblNode テーブルで参照される外部キー。</span><span class="sxs-lookup"><span data-stu-id="5be04-127">Foreign key with lookup in tblNode.nodeID table.</span></span>  <br/> |
|<span data-ttu-id="5be04-128">scopePrinID</span><span class="sxs-lookup"><span data-stu-id="5be04-128">scopePrinID</span></span>  <br/> |<span data-ttu-id="5be04-129">TblPrincipal Id テーブルで参照される外部キー。</span><span class="sxs-lookup"><span data-stu-id="5be04-129">Foreign key with lookup in tblPrincipal.prinID table.</span></span>  <br/> |
   

