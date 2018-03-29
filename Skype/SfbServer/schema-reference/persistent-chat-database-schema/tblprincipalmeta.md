---
title: tblPrincipalMeta
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
ms.openlocfilehash: cfbff018167a3cde68061c3e04eb65d2742e51e9
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/28/2018
---
# <a name="tblprincipalmeta"></a><span data-ttu-id="8fbd9-103">tblPrincipalMeta</span><span class="sxs-lookup"><span data-stu-id="8fbd9-103">tblPrincipalMeta</span></span>
 
<span data-ttu-id="8fbd9-104">tblPrincipalMeta には、Active Directory ドメイン サービスから更新する必要があるプリンシパルが含まれています。</span><span class="sxs-lookup"><span data-stu-id="8fbd9-104">tblPrincipalMeta contains the principals that have to be refreshed from Active Directory Domain Services.</span></span>
  
<span data-ttu-id="8fbd9-105">**列**</span><span class="sxs-lookup"><span data-stu-id="8fbd9-105">**Columns**</span></span>

|<span data-ttu-id="8fbd9-106">**列**</span><span class="sxs-lookup"><span data-stu-id="8fbd9-106">**Column**</span></span>|<span data-ttu-id="8fbd9-107">**タイプ**</span><span class="sxs-lookup"><span data-stu-id="8fbd9-107">**Type**</span></span>|<span data-ttu-id="8fbd9-108">**説明**</span><span class="sxs-lookup"><span data-stu-id="8fbd9-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="8fbd9-109">prinID</span><span class="sxs-lookup"><span data-stu-id="8fbd9-109">prinID</span></span>  <br/> |<span data-ttu-id="8fbd9-110">int 型、null でないです。</span><span class="sxs-lookup"><span data-stu-id="8fbd9-110">int, not null</span></span>  <br/> |<span data-ttu-id="8fbd9-111">プリンシパルの id。</span><span class="sxs-lookup"><span data-stu-id="8fbd9-111">Principal ID.</span></span>  <br/> |
|<span data-ttu-id="8fbd9-112">prinAffiliationsDirty</span><span class="sxs-lookup"><span data-stu-id="8fbd9-112">prinAffiliationsDirty</span></span>  <br/> |<span data-ttu-id="8fbd9-113">ビットの null でないです。</span><span class="sxs-lookup"><span data-stu-id="8fbd9-113">bit, not null</span></span>  <br/> |<span data-ttu-id="8fbd9-114">True の場合、プリンシパルの所属団体があるが更新されます。</span><span class="sxs-lookup"><span data-stu-id="8fbd9-114">True if principal affiliations have to be refreshed.</span></span>  <br/> |
|<span data-ttu-id="8fbd9-115">prinAttributesDirty</span><span class="sxs-lookup"><span data-stu-id="8fbd9-115">prinAttributesDirty</span></span>  <br/> |<span data-ttu-id="8fbd9-116">ビットの null でないです。</span><span class="sxs-lookup"><span data-stu-id="8fbd9-116">bit, not null</span></span>  <br/> |<span data-ttu-id="8fbd9-117">属性が true の場合、プリンシパルでは、更新する必要があります。</span><span class="sxs-lookup"><span data-stu-id="8fbd9-117">True if principal attributes have to be refreshed.</span></span>  <br/> |
|<span data-ttu-id="8fbd9-118">prinDeleted</span><span class="sxs-lookup"><span data-stu-id="8fbd9-118">prinDeleted</span></span>  <br/> |<span data-ttu-id="8fbd9-119">ビットの null でないです。</span><span class="sxs-lookup"><span data-stu-id="8fbd9-119">bit, not null</span></span>  <br/> |<span data-ttu-id="8fbd9-120">プリンシパルが削除された場合は true。</span><span class="sxs-lookup"><span data-stu-id="8fbd9-120">True if the principal has been deleted.</span></span>  <br/> |
|<span data-ttu-id="8fbd9-121">tryCount</span><span class="sxs-lookup"><span data-stu-id="8fbd9-121">tryCount</span></span>  <br/> |<span data-ttu-id="8fbd9-122">int</span><span class="sxs-lookup"><span data-stu-id="8fbd9-122">int</span></span>  <br/> |<span data-ttu-id="8fbd9-123">これまでに発生した AD DS プリンシパルの更新の試行の数です。</span><span class="sxs-lookup"><span data-stu-id="8fbd9-123">Number of attempts to refresh the principal from AD DS that have happened so far.</span></span>  <br/> |
|<span data-ttu-id="8fbd9-124">lastTry</span><span class="sxs-lookup"><span data-stu-id="8fbd9-124">lastTry</span></span>  <br/> |<span data-ttu-id="8fbd9-125">datetime</span><span class="sxs-lookup"><span data-stu-id="8fbd9-125">datetime</span></span>  <br/> |<span data-ttu-id="8fbd9-126">プリンシパルを更新しようとして最新のタイムスタンプです。</span><span class="sxs-lookup"><span data-stu-id="8fbd9-126">Time stamp from the latest attempt to refresh the principal.</span></span> <span data-ttu-id="8fbd9-127">更新が試行されていないまだ場合は、null を指定できます。</span><span class="sxs-lookup"><span data-stu-id="8fbd9-127">Can be null if no refresh has been attempted yet.</span></span>  <br/> |
|<span data-ttu-id="8fbd9-128">nextTry</span><span class="sxs-lookup"><span data-stu-id="8fbd9-128">nextTry</span></span>  <br/> |<span data-ttu-id="8fbd9-129">datetime</span><span class="sxs-lookup"><span data-stu-id="8fbd9-129">datetime</span></span>  <br/> |<span data-ttu-id="8fbd9-130">次のスケジュールされた更新時刻のタイムスタンプ。</span><span class="sxs-lookup"><span data-stu-id="8fbd9-130">Time stamp for the next scheduled refresh.</span></span> <span data-ttu-id="8fbd9-131">更新がスケジュールされてない場合に null を指定できます。</span><span class="sxs-lookup"><span data-stu-id="8fbd9-131">Can be null if no further refresh has been scheduled.</span></span>  <br/> |
   
<span data-ttu-id="8fbd9-132">**キー**</span><span class="sxs-lookup"><span data-stu-id="8fbd9-132">**Keys**</span></span>

|<span data-ttu-id="8fbd9-133">**列**</span><span class="sxs-lookup"><span data-stu-id="8fbd9-133">**Column**</span></span>|<span data-ttu-id="8fbd9-134">**説明**</span><span class="sxs-lookup"><span data-stu-id="8fbd9-134">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="8fbd9-135">prinID</span><span class="sxs-lookup"><span data-stu-id="8fbd9-135">prinID</span></span>  <br/> |<span data-ttu-id="8fbd9-136">プライマリ ・ キーです。</span><span class="sxs-lookup"><span data-stu-id="8fbd9-136">Primary key.</span></span>  <br/> |
|<span data-ttu-id="8fbd9-137">prinID</span><span class="sxs-lookup"><span data-stu-id="8fbd9-137">prinID</span></span>  <br/> |<span data-ttu-id="8fbd9-138">TblPrincipal.prinID テーブル内の参照と外部キーです。</span><span class="sxs-lookup"><span data-stu-id="8fbd9-138">Foreign key with lookup in tblPrincipal.prinID table.</span></span>  <br/> |
   

