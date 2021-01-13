---
title: tblADUpdates
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
ms.assetid: ba19fa16-4d2d-4635-ac32-f93e09469546
description: tblADUpdates には、後の Active Directory 同期手順でまだ処理されていない Active Directory ドメイン サービスの変更が含まれます。
ms.openlocfilehash: 16bb393eb57e7aaf8d3fea7001157eaabbe70c52
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49821387"
---
# <a name="tbladupdates"></a><span data-ttu-id="2a0cd-103">tblADUpdates</span><span class="sxs-lookup"><span data-stu-id="2a0cd-103">tblADUpdates</span></span>
 
<span data-ttu-id="2a0cd-104">tblADUpdates には、後の Active Directory 同期手順でまだ処理されていない Active Directory ドメイン サービスの変更が含まれます。</span><span class="sxs-lookup"><span data-stu-id="2a0cd-104">tblADUpdates contains Active Directory Domain Services changes that have not yet been processed by the later Active Directory Sync steps.</span></span>
  
<span data-ttu-id="2a0cd-105">**Columns**</span><span class="sxs-lookup"><span data-stu-id="2a0cd-105">**Columns**</span></span>

|<span data-ttu-id="2a0cd-106">**列**</span><span class="sxs-lookup"><span data-stu-id="2a0cd-106">**Column**</span></span>|<span data-ttu-id="2a0cd-107">**型**</span><span class="sxs-lookup"><span data-stu-id="2a0cd-107">**Type**</span></span>|<span data-ttu-id="2a0cd-108">**説明**</span><span class="sxs-lookup"><span data-stu-id="2a0cd-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="2a0cd-109">prinGuid</span><span class="sxs-lookup"><span data-stu-id="2a0cd-109">prinGuid</span></span>  <br/> |<span data-ttu-id="2a0cd-110">NULL でない GUID</span><span class="sxs-lookup"><span data-stu-id="2a0cd-110">GUID, not null</span></span>  <br/> |<span data-ttu-id="2a0cd-111">変更したオブジェクトのプリンシパル GUID。</span><span class="sxs-lookup"><span data-stu-id="2a0cd-111">Principal GUID of the object that changed.</span></span>  <br/> |
|<span data-ttu-id="2a0cd-112">prinADPath</span><span class="sxs-lookup"><span data-stu-id="2a0cd-112">prinADPath</span></span>  <br/> |<span data-ttu-id="2a0cd-113">NULL でない nvarchar (384)</span><span class="sxs-lookup"><span data-stu-id="2a0cd-113">nvarchar (384), not null</span></span>  <br/> |<span data-ttu-id="2a0cd-114">オブジェクトの識別名。</span><span class="sxs-lookup"><span data-stu-id="2a0cd-114">Distinguished name of the object.</span></span>  <br/> |
|<span data-ttu-id="2a0cd-115">prinAttributesChanged</span><span class="sxs-lookup"><span data-stu-id="2a0cd-115">prinAttributesChanged</span></span>  <br/> |<span data-ttu-id="2a0cd-116">NULL でない bit</span><span class="sxs-lookup"><span data-stu-id="2a0cd-116">bit, not null</span></span>  <br/> |<span data-ttu-id="2a0cd-117">オブジェクトの属性が 1 つ以上変更された場合は True。</span><span class="sxs-lookup"><span data-stu-id="2a0cd-117">True if at least one attribute of the object changed.</span></span>  <br/> |
|<span data-ttu-id="2a0cd-118">prinMembersChanged</span><span class="sxs-lookup"><span data-stu-id="2a0cd-118">prinMembersChanged</span></span>  <br/> |<span data-ttu-id="2a0cd-119">NULL でない bit</span><span class="sxs-lookup"><span data-stu-id="2a0cd-119">bit, not null</span></span>  <br/> |<span data-ttu-id="2a0cd-120">メンバーシップが変更された場合は True。</span><span class="sxs-lookup"><span data-stu-id="2a0cd-120">True if the membership changed.</span></span>  <br/> |
|<span data-ttu-id="2a0cd-121">prinAffiliationsChanged</span><span class="sxs-lookup"><span data-stu-id="2a0cd-121">prinAffiliationsChanged</span></span>  <br/> |<span data-ttu-id="2a0cd-122">NULL でない bit</span><span class="sxs-lookup"><span data-stu-id="2a0cd-122">bit, not null</span></span>  <br/> |<span data-ttu-id="2a0cd-123">不使用。</span><span class="sxs-lookup"><span data-stu-id="2a0cd-123">Not used.</span></span>  <br/> |
|<span data-ttu-id="2a0cd-124">prinDeleted</span><span class="sxs-lookup"><span data-stu-id="2a0cd-124">prinDeleted</span></span>  <br/> |<span data-ttu-id="2a0cd-125">NULL でない bit</span><span class="sxs-lookup"><span data-stu-id="2a0cd-125">bit, not null</span></span>  <br/> |<span data-ttu-id="2a0cd-126">オブジェクトが削除された場合は True。</span><span class="sxs-lookup"><span data-stu-id="2a0cd-126">True if the object was deleted.</span></span>  <br/> |
|<span data-ttu-id="2a0cd-127">lastUpdated</span><span class="sxs-lookup"><span data-stu-id="2a0cd-127">lastUpdated</span></span>  <br/> |<span data-ttu-id="2a0cd-128">NULL でない datetime</span><span class="sxs-lookup"><span data-stu-id="2a0cd-128">datetime, not null</span></span>  <br/> |<span data-ttu-id="2a0cd-129">行が挿入された時点のタイムスタンプ。</span><span class="sxs-lookup"><span data-stu-id="2a0cd-129">Time stamp of when the row was inserted.</span></span>  <br/> |
   

