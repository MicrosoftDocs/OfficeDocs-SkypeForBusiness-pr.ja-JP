---
title: tblPrincipalMeta
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 808490d4-7d6d-47a2-b8af-b5940d47073b
description: tblPrincipalMeta には、Active Directory ドメイン サービスから更新する必要があるプリンシパルが含まれています。
ms.openlocfilehash: 049a273f7134ecb945e62da39469bcaf0defbffb
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "32212433"
---
# <a name="tblprincipalmeta"></a><span data-ttu-id="96c33-103">tblPrincipalMeta</span><span class="sxs-lookup"><span data-stu-id="96c33-103">tblPrincipalMeta</span></span>
 
<span data-ttu-id="96c33-104">tblPrincipalMeta には、Active Directory ドメイン サービスから更新する必要があるプリンシパルが含まれています。</span><span class="sxs-lookup"><span data-stu-id="96c33-104">tblPrincipalMeta contains the principals that have to be refreshed from Active Directory Domain Services.</span></span>
  
<span data-ttu-id="96c33-105">**列**</span><span class="sxs-lookup"><span data-stu-id="96c33-105">**Columns**</span></span>

|<span data-ttu-id="96c33-106">**列**</span><span class="sxs-lookup"><span data-stu-id="96c33-106">**Column**</span></span>|<span data-ttu-id="96c33-107">**型**</span><span class="sxs-lookup"><span data-stu-id="96c33-107">**Type**</span></span>|<span data-ttu-id="96c33-108">**説明**</span><span class="sxs-lookup"><span data-stu-id="96c33-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="96c33-109">prinID</span><span class="sxs-lookup"><span data-stu-id="96c33-109">prinID</span></span>  <br/> |<span data-ttu-id="96c33-110">int 型、null でないです。</span><span class="sxs-lookup"><span data-stu-id="96c33-110">int, not null</span></span>  <br/> |<span data-ttu-id="96c33-111">プリンシパルの id。</span><span class="sxs-lookup"><span data-stu-id="96c33-111">Principal ID.</span></span>  <br/> |
|<span data-ttu-id="96c33-112">prinAffiliationsDirty</span><span class="sxs-lookup"><span data-stu-id="96c33-112">prinAffiliationsDirty</span></span>  <br/> |<span data-ttu-id="96c33-113">ビットの null でないです。</span><span class="sxs-lookup"><span data-stu-id="96c33-113">bit, not null</span></span>  <br/> |<span data-ttu-id="96c33-114">True の場合、プリンシパルの所属団体があるが更新されます。</span><span class="sxs-lookup"><span data-stu-id="96c33-114">True if principal affiliations have to be refreshed.</span></span>  <br/> |
|<span data-ttu-id="96c33-115">prinAttributesDirty</span><span class="sxs-lookup"><span data-stu-id="96c33-115">prinAttributesDirty</span></span>  <br/> |<span data-ttu-id="96c33-116">ビットの null でないです。</span><span class="sxs-lookup"><span data-stu-id="96c33-116">bit, not null</span></span>  <br/> |<span data-ttu-id="96c33-117">属性が true の場合、プリンシパルでは、更新する必要があります。</span><span class="sxs-lookup"><span data-stu-id="96c33-117">True if principal attributes have to be refreshed.</span></span>  <br/> |
|<span data-ttu-id="96c33-118">prinDeleted</span><span class="sxs-lookup"><span data-stu-id="96c33-118">prinDeleted</span></span>  <br/> |<span data-ttu-id="96c33-119">ビットの null でないです。</span><span class="sxs-lookup"><span data-stu-id="96c33-119">bit, not null</span></span>  <br/> |<span data-ttu-id="96c33-120">プリンシパルが削除された場合は true。</span><span class="sxs-lookup"><span data-stu-id="96c33-120">True if the principal has been deleted.</span></span>  <br/> |
|<span data-ttu-id="96c33-121">tryCount</span><span class="sxs-lookup"><span data-stu-id="96c33-121">tryCount</span></span>  <br/> |<span data-ttu-id="96c33-122">int</span><span class="sxs-lookup"><span data-stu-id="96c33-122">int</span></span>  <br/> |<span data-ttu-id="96c33-123">これまでに発生した AD DS プリンシパルの更新の試行の数です。</span><span class="sxs-lookup"><span data-stu-id="96c33-123">Number of attempts to refresh the principal from AD DS that have happened so far.</span></span>  <br/> |
|<span data-ttu-id="96c33-124">lastTry</span><span class="sxs-lookup"><span data-stu-id="96c33-124">lastTry</span></span>  <br/> |<span data-ttu-id="96c33-125">datetime</span><span class="sxs-lookup"><span data-stu-id="96c33-125">datetime</span></span>  <br/> |<span data-ttu-id="96c33-126">プリンシパルを更新しようとして最新のタイムスタンプです。</span><span class="sxs-lookup"><span data-stu-id="96c33-126">Time stamp from the latest attempt to refresh the principal.</span></span> <span data-ttu-id="96c33-127">更新が試行されていないまだ場合は、null を指定できます。</span><span class="sxs-lookup"><span data-stu-id="96c33-127">Can be null if no refresh has been attempted yet.</span></span>  <br/> |
|<span data-ttu-id="96c33-128">nextTry</span><span class="sxs-lookup"><span data-stu-id="96c33-128">nextTry</span></span>  <br/> |<span data-ttu-id="96c33-129">datetime</span><span class="sxs-lookup"><span data-stu-id="96c33-129">datetime</span></span>  <br/> |<span data-ttu-id="96c33-130">次のスケジュールされた更新時刻のタイムスタンプ。</span><span class="sxs-lookup"><span data-stu-id="96c33-130">Time stamp for the next scheduled refresh.</span></span> <span data-ttu-id="96c33-131">更新がスケジュールされてない場合に null を指定できます。</span><span class="sxs-lookup"><span data-stu-id="96c33-131">Can be null if no further refresh has been scheduled.</span></span>  <br/> |
   
<span data-ttu-id="96c33-132">**キー**</span><span class="sxs-lookup"><span data-stu-id="96c33-132">**Keys**</span></span>

|<span data-ttu-id="96c33-133">**列**</span><span class="sxs-lookup"><span data-stu-id="96c33-133">**Column**</span></span>|<span data-ttu-id="96c33-134">**説明**</span><span class="sxs-lookup"><span data-stu-id="96c33-134">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="96c33-135">prinID</span><span class="sxs-lookup"><span data-stu-id="96c33-135">prinID</span></span>  <br/> |<span data-ttu-id="96c33-136">プライマリ ・ キーです。</span><span class="sxs-lookup"><span data-stu-id="96c33-136">Primary key.</span></span>  <br/> |
|<span data-ttu-id="96c33-137">prinID</span><span class="sxs-lookup"><span data-stu-id="96c33-137">prinID</span></span>  <br/> |<span data-ttu-id="96c33-138">TblPrincipal.prinID テーブル内の参照と外部キーです。</span><span class="sxs-lookup"><span data-stu-id="96c33-138">Foreign key with lookup in tblPrincipal.prinID table.</span></span>  <br/> |
   

