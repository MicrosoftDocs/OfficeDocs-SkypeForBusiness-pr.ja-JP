---
title: tblScopePrincipal
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 422d6c7f-7ba7-4dd4-bacc-95ace47959ff
description: tblScopePrincipal には、ノードに割り当てられたスコープが含まれています。
ms.openlocfilehash: e93b92280605dfe01f288435c7cb42b724c22064
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "32212398"
---
# <a name="tblscopeprincipal"></a><span data-ttu-id="5ebeb-103">tblScopePrincipal</span><span class="sxs-lookup"><span data-stu-id="5ebeb-103">tblScopePrincipal</span></span>
 
<span data-ttu-id="5ebeb-104">tblScopePrincipal には、ノードに割り当てられたスコープが含まれています。</span><span class="sxs-lookup"><span data-stu-id="5ebeb-104">tblScopePrincipal contains scopes assigned to nodes.</span></span>
  
<span data-ttu-id="5ebeb-105">**列**</span><span class="sxs-lookup"><span data-stu-id="5ebeb-105">**Columns**</span></span>

|<span data-ttu-id="5ebeb-106">**列**</span><span class="sxs-lookup"><span data-stu-id="5ebeb-106">**Column**</span></span>|<span data-ttu-id="5ebeb-107">**型**</span><span class="sxs-lookup"><span data-stu-id="5ebeb-107">**Type**</span></span>|<span data-ttu-id="5ebeb-108">**説明**</span><span class="sxs-lookup"><span data-stu-id="5ebeb-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="5ebeb-109">scopeNodeID</span><span class="sxs-lookup"><span data-stu-id="5ebeb-109">scopeNodeID</span></span>  <br/> |<span data-ttu-id="5ebeb-110">int 型、null でないです。</span><span class="sxs-lookup"><span data-stu-id="5ebeb-110">int, not null</span></span>  <br/> |<span data-ttu-id="5ebeb-111">スコープを適用するノードの ID。</span><span class="sxs-lookup"><span data-stu-id="5ebeb-111">Node ID that the scope applies to.</span></span>  <br/> |
|<span data-ttu-id="5ebeb-112">scopePrinID</span><span class="sxs-lookup"><span data-stu-id="5ebeb-112">scopePrinID</span></span>  <br/> |<span data-ttu-id="5ebeb-113">int 型、null でないです。</span><span class="sxs-lookup"><span data-stu-id="5ebeb-113">int, not null</span></span>  <br/> |<span data-ttu-id="5ebeb-114">プリンシパルの id。</span><span class="sxs-lookup"><span data-stu-id="5ebeb-114">Principal ID.</span></span>  <br/> |
|<span data-ttu-id="5ebeb-115">scopeIsDenied</span><span class="sxs-lookup"><span data-stu-id="5ebeb-115">scopeIsDenied</span></span>  <br/> |<span data-ttu-id="5ebeb-116">ビットの null でないです。</span><span class="sxs-lookup"><span data-stu-id="5ebeb-116">bit, not null</span></span>  <br/> |<span data-ttu-id="5ebeb-117">True の場合、スコープの種類は、拒否します。False の場合に使用できます。</span><span class="sxs-lookup"><span data-stu-id="5ebeb-117">True if type of scope is Deny; False if Allow.</span></span>  <br/> |
|<span data-ttu-id="5ebeb-118">scopeUpdatedBy</span><span class="sxs-lookup"><span data-stu-id="5ebeb-118">scopeUpdatedBy</span></span>  <br/> |<span data-ttu-id="5ebeb-119">int 型、null でないです。</span><span class="sxs-lookup"><span data-stu-id="5ebeb-119">int, not null</span></span>  <br/> |<span data-ttu-id="5ebeb-120">このエントリを最後に更新したプリンシパルの ID です。</span><span class="sxs-lookup"><span data-stu-id="5ebeb-120">ID of the principal that last updated this entry.</span></span>  <br/> |
   
<span data-ttu-id="5ebeb-121">**キー**</span><span class="sxs-lookup"><span data-stu-id="5ebeb-121">**Keys**</span></span>

|<span data-ttu-id="5ebeb-122">**列**</span><span class="sxs-lookup"><span data-stu-id="5ebeb-122">**Column**</span></span>|<span data-ttu-id="5ebeb-123">**説明**</span><span class="sxs-lookup"><span data-stu-id="5ebeb-123">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="5ebeb-124">\<scopeNodeID、scopePrinID\></span><span class="sxs-lookup"><span data-stu-id="5ebeb-124">\<scopeNodeID, scopePrinID\></span></span>  <br/> |<span data-ttu-id="5ebeb-125">プライマリ ・ キーです。</span><span class="sxs-lookup"><span data-stu-id="5ebeb-125">Primary key.</span></span>  <br/> |
|<span data-ttu-id="5ebeb-126">scopeNodeID</span><span class="sxs-lookup"><span data-stu-id="5ebeb-126">scopeNodeID</span></span>  <br/> |<span data-ttu-id="5ebeb-127">TblNode.nodeID テーブル内の参照と外部キーです。</span><span class="sxs-lookup"><span data-stu-id="5ebeb-127">Foreign key with lookup in tblNode.nodeID table.</span></span>  <br/> |
|<span data-ttu-id="5ebeb-128">scopePrinID</span><span class="sxs-lookup"><span data-stu-id="5ebeb-128">scopePrinID</span></span>  <br/> |<span data-ttu-id="5ebeb-129">TblPrincipal.prinID テーブル内の参照と外部キーです。</span><span class="sxs-lookup"><span data-stu-id="5ebeb-129">Foreign key with lookup in tblPrincipal.prinID table.</span></span>  <br/> |
   

