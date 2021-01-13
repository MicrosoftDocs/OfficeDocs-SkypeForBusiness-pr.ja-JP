---
title: tblPrincipalMeta
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
ms.assetid: 808490d4-7d6d-47a2-b8af-b5940d47073b
description: tblPrincipalMeta には、Active Directory ドメイン サービスから更新する必要があるプリンシパルが含まれます。
ms.openlocfilehash: e10b56a8a3a1c25f73cd1a07f4fdcde18c6f1215
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49831547"
---
# <a name="tblprincipalmeta"></a><span data-ttu-id="2fdf8-103">tblPrincipalMeta</span><span class="sxs-lookup"><span data-stu-id="2fdf8-103">tblPrincipalMeta</span></span>
 
<span data-ttu-id="2fdf8-104">tblPrincipalMeta には、Active Directory ドメイン サービスから更新する必要があるプリンシパルが含まれます。</span><span class="sxs-lookup"><span data-stu-id="2fdf8-104">tblPrincipalMeta contains the principals that have to be refreshed from Active Directory Domain Services.</span></span>
  
<span data-ttu-id="2fdf8-105">**Columns**</span><span class="sxs-lookup"><span data-stu-id="2fdf8-105">**Columns**</span></span>

|<span data-ttu-id="2fdf8-106">**列**</span><span class="sxs-lookup"><span data-stu-id="2fdf8-106">**Column**</span></span>|<span data-ttu-id="2fdf8-107">**型**</span><span class="sxs-lookup"><span data-stu-id="2fdf8-107">**Type**</span></span>|<span data-ttu-id="2fdf8-108">**説明**</span><span class="sxs-lookup"><span data-stu-id="2fdf8-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="2fdf8-109">prinID</span><span class="sxs-lookup"><span data-stu-id="2fdf8-109">prinID</span></span>  <br/> |<span data-ttu-id="2fdf8-110">NULL でない int</span><span class="sxs-lookup"><span data-stu-id="2fdf8-110">int, not null</span></span>  <br/> |<span data-ttu-id="2fdf8-111">プリンシパル ID。</span><span class="sxs-lookup"><span data-stu-id="2fdf8-111">Principal ID.</span></span>  <br/> |
|<span data-ttu-id="2fdf8-112">prinAffiliationsDirty</span><span class="sxs-lookup"><span data-stu-id="2fdf8-112">prinAffiliationsDirty</span></span>  <br/> |<span data-ttu-id="2fdf8-113">NULL でない bit</span><span class="sxs-lookup"><span data-stu-id="2fdf8-113">bit, not null</span></span>  <br/> |<span data-ttu-id="2fdf8-114">プリンシパルの所属を最新の情報に更新する必要がある場合は True。</span><span class="sxs-lookup"><span data-stu-id="2fdf8-114">True if principal affiliations have to be refreshed.</span></span>  <br/> |
|<span data-ttu-id="2fdf8-115">prinAttributesDirty</span><span class="sxs-lookup"><span data-stu-id="2fdf8-115">prinAttributesDirty</span></span>  <br/> |<span data-ttu-id="2fdf8-116">NULL でない bit</span><span class="sxs-lookup"><span data-stu-id="2fdf8-116">bit, not null</span></span>  <br/> |<span data-ttu-id="2fdf8-117">プリンシパル属性を最新の情報に更新する必要がある場合は True。</span><span class="sxs-lookup"><span data-stu-id="2fdf8-117">True if principal attributes have to be refreshed.</span></span>  <br/> |
|<span data-ttu-id="2fdf8-118">prinDeleted</span><span class="sxs-lookup"><span data-stu-id="2fdf8-118">prinDeleted</span></span>  <br/> |<span data-ttu-id="2fdf8-119">NULL でない bit</span><span class="sxs-lookup"><span data-stu-id="2fdf8-119">bit, not null</span></span>  <br/> |<span data-ttu-id="2fdf8-120">プリンシパルが削除されている場合は True。</span><span class="sxs-lookup"><span data-stu-id="2fdf8-120">True if the principal has been deleted.</span></span>  <br/> |
|<span data-ttu-id="2fdf8-121">tryCount</span><span class="sxs-lookup"><span data-stu-id="2fdf8-121">tryCount</span></span>  <br/> |<span data-ttu-id="2fdf8-122">int</span><span class="sxs-lookup"><span data-stu-id="2fdf8-122">int</span></span>  <br/> |<span data-ttu-id="2fdf8-123">それまでに行われた AD DS からプリンシパルを更新する試行の数。</span><span class="sxs-lookup"><span data-stu-id="2fdf8-123">Number of attempts to refresh the principal from AD DS that have happened so far.</span></span>  <br/> |
|<span data-ttu-id="2fdf8-124">lastTry</span><span class="sxs-lookup"><span data-stu-id="2fdf8-124">lastTry</span></span>  <br/> |<span data-ttu-id="2fdf8-125">日付型</span><span class="sxs-lookup"><span data-stu-id="2fdf8-125">datetime</span></span>  <br/> |<span data-ttu-id="2fdf8-p101">プリンシパルを最新の情報に更新する最新の試行からのタイム スタンプ。最新の情報への更新をまだ試みていない場合は NULL になります。</span><span class="sxs-lookup"><span data-stu-id="2fdf8-p101">Time stamp from the latest attempt to refresh the principal. Can be null if no refresh has been attempted yet.</span></span>  <br/> |
|<span data-ttu-id="2fdf8-128">nextTry</span><span class="sxs-lookup"><span data-stu-id="2fdf8-128">nextTry</span></span>  <br/> |<span data-ttu-id="2fdf8-129">日付型</span><span class="sxs-lookup"><span data-stu-id="2fdf8-129">datetime</span></span>  <br/> |<span data-ttu-id="2fdf8-p102">次にスケジュールされている最新の情報への更新のタイム スタンプ。最新の情報への更新がスケジュールされていない場合は NULL になります。</span><span class="sxs-lookup"><span data-stu-id="2fdf8-p102">Time stamp for the next scheduled refresh. Can be null if no further refresh has been scheduled.</span></span>  <br/> |
   
<span data-ttu-id="2fdf8-132">**Keys**</span><span class="sxs-lookup"><span data-stu-id="2fdf8-132">**Keys**</span></span>

|<span data-ttu-id="2fdf8-133">**列**</span><span class="sxs-lookup"><span data-stu-id="2fdf8-133">**Column**</span></span>|<span data-ttu-id="2fdf8-134">**説明**</span><span class="sxs-lookup"><span data-stu-id="2fdf8-134">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="2fdf8-135">prinID</span><span class="sxs-lookup"><span data-stu-id="2fdf8-135">prinID</span></span>  <br/> |<span data-ttu-id="2fdf8-136">主キー。</span><span class="sxs-lookup"><span data-stu-id="2fdf8-136">Primary key.</span></span>  <br/> |
|<span data-ttu-id="2fdf8-137">prinID</span><span class="sxs-lookup"><span data-stu-id="2fdf8-137">prinID</span></span>  <br/> |<span data-ttu-id="2fdf8-138">tblPrincipal.prinID テーブル内の参照による外部キー。</span><span class="sxs-lookup"><span data-stu-id="2fdf8-138">Foreign key with lookup in tblPrincipal.prinID table.</span></span>  <br/> |
   

