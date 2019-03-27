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
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/27/2019
ms.locfileid: "30885625"
---
# <a name="tblscopeprincipal"></a><span data-ttu-id="fdf70-103">tblScopePrincipal</span><span class="sxs-lookup"><span data-stu-id="fdf70-103">tblScopePrincipal</span></span>
 
<span data-ttu-id="fdf70-104">tblScopePrincipal には、ノードに割り当てられたスコープが含まれています。</span><span class="sxs-lookup"><span data-stu-id="fdf70-104">tblScopePrincipal contains scopes assigned to nodes.</span></span>
  
<span data-ttu-id="fdf70-105">**列**</span><span class="sxs-lookup"><span data-stu-id="fdf70-105">**Columns**</span></span>

|<span data-ttu-id="fdf70-106">**列**</span><span class="sxs-lookup"><span data-stu-id="fdf70-106">**Column**</span></span>|<span data-ttu-id="fdf70-107">**型**</span><span class="sxs-lookup"><span data-stu-id="fdf70-107">**Type**</span></span>|<span data-ttu-id="fdf70-108">**説明**</span><span class="sxs-lookup"><span data-stu-id="fdf70-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="fdf70-109">scopeNodeID</span><span class="sxs-lookup"><span data-stu-id="fdf70-109">scopeNodeID</span></span>  <br/> |<span data-ttu-id="fdf70-110">int 型、null でないです。</span><span class="sxs-lookup"><span data-stu-id="fdf70-110">int, not null</span></span>  <br/> |<span data-ttu-id="fdf70-111">スコープを適用するノードの ID。</span><span class="sxs-lookup"><span data-stu-id="fdf70-111">Node ID that the scope applies to.</span></span>  <br/> |
|<span data-ttu-id="fdf70-112">scopePrinID</span><span class="sxs-lookup"><span data-stu-id="fdf70-112">scopePrinID</span></span>  <br/> |<span data-ttu-id="fdf70-113">int 型、null でないです。</span><span class="sxs-lookup"><span data-stu-id="fdf70-113">int, not null</span></span>  <br/> |<span data-ttu-id="fdf70-114">プリンシパルの id。</span><span class="sxs-lookup"><span data-stu-id="fdf70-114">Principal ID.</span></span>  <br/> |
|<span data-ttu-id="fdf70-115">scopeIsDenied</span><span class="sxs-lookup"><span data-stu-id="fdf70-115">scopeIsDenied</span></span>  <br/> |<span data-ttu-id="fdf70-116">ビットの null でないです。</span><span class="sxs-lookup"><span data-stu-id="fdf70-116">bit, not null</span></span>  <br/> |<span data-ttu-id="fdf70-117">True の場合、スコープの種類は、拒否します。False の場合に使用できます。</span><span class="sxs-lookup"><span data-stu-id="fdf70-117">True if type of scope is Deny; False if Allow.</span></span>  <br/> |
|<span data-ttu-id="fdf70-118">scopeUpdatedBy</span><span class="sxs-lookup"><span data-stu-id="fdf70-118">scopeUpdatedBy</span></span>  <br/> |<span data-ttu-id="fdf70-119">int 型、null でないです。</span><span class="sxs-lookup"><span data-stu-id="fdf70-119">int, not null</span></span>  <br/> |<span data-ttu-id="fdf70-120">このエントリを最後に更新したプリンシパルの ID です。</span><span class="sxs-lookup"><span data-stu-id="fdf70-120">ID of the principal that last updated this entry.</span></span>  <br/> |
   
<span data-ttu-id="fdf70-121">**キー**</span><span class="sxs-lookup"><span data-stu-id="fdf70-121">**Keys**</span></span>

|<span data-ttu-id="fdf70-122">**列**</span><span class="sxs-lookup"><span data-stu-id="fdf70-122">**Column**</span></span>|<span data-ttu-id="fdf70-123">**説明**</span><span class="sxs-lookup"><span data-stu-id="fdf70-123">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="fdf70-124">\<scopeNodeID、scopePrinID\></span><span class="sxs-lookup"><span data-stu-id="fdf70-124">\<scopeNodeID, scopePrinID\></span></span>  <br/> |<span data-ttu-id="fdf70-125">プライマリ ・ キーです。</span><span class="sxs-lookup"><span data-stu-id="fdf70-125">Primary key.</span></span>  <br/> |
|<span data-ttu-id="fdf70-126">scopeNodeID</span><span class="sxs-lookup"><span data-stu-id="fdf70-126">scopeNodeID</span></span>  <br/> |<span data-ttu-id="fdf70-127">TblNode.nodeID テーブル内の参照と外部キーです。</span><span class="sxs-lookup"><span data-stu-id="fdf70-127">Foreign key with lookup in tblNode.nodeID table.</span></span>  <br/> |
|<span data-ttu-id="fdf70-128">scopePrinID</span><span class="sxs-lookup"><span data-stu-id="fdf70-128">scopePrinID</span></span>  <br/> |<span data-ttu-id="fdf70-129">TblPrincipal.prinID テーブル内の参照と外部キーです。</span><span class="sxs-lookup"><span data-stu-id="fdf70-129">Foreign key with lookup in tblPrincipal.prinID table.</span></span>  <br/> |
   

