---
title: tblScopePrincipal
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 422d6c7f-7ba7-4dd4-bacc-95ace47959ff
description: tblScopePrincipal には、ノードに割り当てられたスコープが含まれています。
ms.openlocfilehash: f682c8a2235ef30cda365bc5950cbfb123840595
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "33924928"
---
# <a name="tblscopeprincipal"></a><span data-ttu-id="b725a-103">tblScopePrincipal</span><span class="sxs-lookup"><span data-stu-id="b725a-103">tblScopePrincipal</span></span>
 
<span data-ttu-id="b725a-104">tblScopePrincipal には、ノードに割り当てられたスコープが含まれています。</span><span class="sxs-lookup"><span data-stu-id="b725a-104">tblScopePrincipal contains scopes assigned to nodes.</span></span>
  
<span data-ttu-id="b725a-105">**列**</span><span class="sxs-lookup"><span data-stu-id="b725a-105">**Columns**</span></span>

|<span data-ttu-id="b725a-106">**列**</span><span class="sxs-lookup"><span data-stu-id="b725a-106">**Column**</span></span>|<span data-ttu-id="b725a-107">**型**</span><span class="sxs-lookup"><span data-stu-id="b725a-107">**Type**</span></span>|<span data-ttu-id="b725a-108">**説明**</span><span class="sxs-lookup"><span data-stu-id="b725a-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="b725a-109">scopeNodeID</span><span class="sxs-lookup"><span data-stu-id="b725a-109">scopeNodeID</span></span>  <br/> |<span data-ttu-id="b725a-110">int 型、null でないです。</span><span class="sxs-lookup"><span data-stu-id="b725a-110">int, not null</span></span>  <br/> |<span data-ttu-id="b725a-111">スコープを適用するノードの ID。</span><span class="sxs-lookup"><span data-stu-id="b725a-111">Node ID that the scope applies to.</span></span>  <br/> |
|<span data-ttu-id="b725a-112">scopePrinID</span><span class="sxs-lookup"><span data-stu-id="b725a-112">scopePrinID</span></span>  <br/> |<span data-ttu-id="b725a-113">int 型、null でないです。</span><span class="sxs-lookup"><span data-stu-id="b725a-113">int, not null</span></span>  <br/> |<span data-ttu-id="b725a-114">プリンシパルの id。</span><span class="sxs-lookup"><span data-stu-id="b725a-114">Principal ID.</span></span>  <br/> |
|<span data-ttu-id="b725a-115">scopeIsDenied</span><span class="sxs-lookup"><span data-stu-id="b725a-115">scopeIsDenied</span></span>  <br/> |<span data-ttu-id="b725a-116">ビットの null でないです。</span><span class="sxs-lookup"><span data-stu-id="b725a-116">bit, not null</span></span>  <br/> |<span data-ttu-id="b725a-117">True の場合、スコープの種類は、拒否します。False の場合に使用できます。</span><span class="sxs-lookup"><span data-stu-id="b725a-117">True if type of scope is Deny; False if Allow.</span></span>  <br/> |
|<span data-ttu-id="b725a-118">scopeUpdatedBy</span><span class="sxs-lookup"><span data-stu-id="b725a-118">scopeUpdatedBy</span></span>  <br/> |<span data-ttu-id="b725a-119">int 型、null でないです。</span><span class="sxs-lookup"><span data-stu-id="b725a-119">int, not null</span></span>  <br/> |<span data-ttu-id="b725a-120">このエントリを最後に更新したプリンシパルの ID です。</span><span class="sxs-lookup"><span data-stu-id="b725a-120">ID of the principal that last updated this entry.</span></span>  <br/> |
   
<span data-ttu-id="b725a-121">**キー**</span><span class="sxs-lookup"><span data-stu-id="b725a-121">**Keys**</span></span>

|<span data-ttu-id="b725a-122">**列**</span><span class="sxs-lookup"><span data-stu-id="b725a-122">**Column**</span></span>|<span data-ttu-id="b725a-123">**説明**</span><span class="sxs-lookup"><span data-stu-id="b725a-123">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="b725a-124">\<scopeNodeID、scopePrinID\></span><span class="sxs-lookup"><span data-stu-id="b725a-124">\<scopeNodeID, scopePrinID\></span></span>  <br/> |<span data-ttu-id="b725a-125">プライマリ ・ キーです。</span><span class="sxs-lookup"><span data-stu-id="b725a-125">Primary key.</span></span>  <br/> |
|<span data-ttu-id="b725a-126">scopeNodeID</span><span class="sxs-lookup"><span data-stu-id="b725a-126">scopeNodeID</span></span>  <br/> |<span data-ttu-id="b725a-127">TblNode.nodeID テーブル内の参照と外部キーです。</span><span class="sxs-lookup"><span data-stu-id="b725a-127">Foreign key with lookup in tblNode.nodeID table.</span></span>  <br/> |
|<span data-ttu-id="b725a-128">scopePrinID</span><span class="sxs-lookup"><span data-stu-id="b725a-128">scopePrinID</span></span>  <br/> |<span data-ttu-id="b725a-129">TblPrincipal.prinID テーブル内の参照と外部キーです。</span><span class="sxs-lookup"><span data-stu-id="b725a-129">Foreign key with lookup in tblPrincipal.prinID table.</span></span>  <br/> |
   

