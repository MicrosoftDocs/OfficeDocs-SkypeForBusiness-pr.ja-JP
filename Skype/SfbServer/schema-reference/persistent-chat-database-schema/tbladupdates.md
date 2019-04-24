---
title: tblADUpdates
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: ba19fa16-4d2d-4635-ac32-f93e09469546
description: tblADUpdates には、後の作業中のディレクトリ同期手順でまだ処理されていない Active Directory ドメイン サービスの変更が含まれています。
ms.openlocfilehash: 0e7bde110ad3d0495cb7ddea55e405eac21d96b4
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "32212643"
---
# <a name="tbladupdates"></a><span data-ttu-id="c067c-103">tblADUpdates</span><span class="sxs-lookup"><span data-stu-id="c067c-103">tblADUpdates</span></span>
 
<span data-ttu-id="c067c-104">tblADUpdates には、後の作業中のディレクトリ同期手順でまだ処理されていない Active Directory ドメイン サービスの変更が含まれています。</span><span class="sxs-lookup"><span data-stu-id="c067c-104">tblADUpdates contains Active Directory Domain Services changes that have not yet been processed by the later Active Directory Sync steps.</span></span>
  
<span data-ttu-id="c067c-105">**列**</span><span class="sxs-lookup"><span data-stu-id="c067c-105">**Columns**</span></span>

|<span data-ttu-id="c067c-106">**列**</span><span class="sxs-lookup"><span data-stu-id="c067c-106">**Column**</span></span>|<span data-ttu-id="c067c-107">**型**</span><span class="sxs-lookup"><span data-stu-id="c067c-107">**Type**</span></span>|<span data-ttu-id="c067c-108">**説明**</span><span class="sxs-lookup"><span data-stu-id="c067c-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="c067c-109">prinGuid</span><span class="sxs-lookup"><span data-stu-id="c067c-109">prinGuid</span></span>  <br/> |<span data-ttu-id="c067c-110">GUID では、null でないです。</span><span class="sxs-lookup"><span data-stu-id="c067c-110">GUID, not null</span></span>  <br/> |<span data-ttu-id="c067c-111">変更されたオブジェクトのプリンシパル GUID。</span><span class="sxs-lookup"><span data-stu-id="c067c-111">Principal GUID of the object that changed.</span></span>  <br/> |
|<span data-ttu-id="c067c-112">prinADPath</span><span class="sxs-lookup"><span data-stu-id="c067c-112">prinADPath</span></span>  <br/> |<span data-ttu-id="c067c-113">nvarchar (384)、null でないです。</span><span class="sxs-lookup"><span data-stu-id="c067c-113">nvarchar (384), not null</span></span>  <br/> |<span data-ttu-id="c067c-114">オブジェクトの識別名です。</span><span class="sxs-lookup"><span data-stu-id="c067c-114">Distinguished name of the object.</span></span>  <br/> |
|<span data-ttu-id="c067c-115">prinAttributesChanged</span><span class="sxs-lookup"><span data-stu-id="c067c-115">prinAttributesChanged</span></span>  <br/> |<span data-ttu-id="c067c-116">ビットの null でないです。</span><span class="sxs-lookup"><span data-stu-id="c067c-116">bit, not null</span></span>  <br/> |<span data-ttu-id="c067c-117">オブジェクトの少なくとも 1 つの属性が変更された場合は true。</span><span class="sxs-lookup"><span data-stu-id="c067c-117">True if at least one attribute of the object changed.</span></span>  <br/> |
|<span data-ttu-id="c067c-118">prinMembersChanged</span><span class="sxs-lookup"><span data-stu-id="c067c-118">prinMembersChanged</span></span>  <br/> |<span data-ttu-id="c067c-119">ビットの null でないです。</span><span class="sxs-lookup"><span data-stu-id="c067c-119">bit, not null</span></span>  <br/> |<span data-ttu-id="c067c-120">メンバーシップが変更された場合は true。</span><span class="sxs-lookup"><span data-stu-id="c067c-120">True if the membership changed.</span></span>  <br/> |
|<span data-ttu-id="c067c-121">prinAffiliationsChanged</span><span class="sxs-lookup"><span data-stu-id="c067c-121">prinAffiliationsChanged</span></span>  <br/> |<span data-ttu-id="c067c-122">ビットの null でないです。</span><span class="sxs-lookup"><span data-stu-id="c067c-122">bit, not null</span></span>  <br/> |<span data-ttu-id="c067c-123">使用されません。</span><span class="sxs-lookup"><span data-stu-id="c067c-123">Not used.</span></span>  <br/> |
|<span data-ttu-id="c067c-124">prinDeleted</span><span class="sxs-lookup"><span data-stu-id="c067c-124">prinDeleted</span></span>  <br/> |<span data-ttu-id="c067c-125">ビットの null でないです。</span><span class="sxs-lookup"><span data-stu-id="c067c-125">bit, not null</span></span>  <br/> |<span data-ttu-id="c067c-126">オブジェクトが削除された場合は true。</span><span class="sxs-lookup"><span data-stu-id="c067c-126">True if the object was deleted.</span></span>  <br/> |
|<span data-ttu-id="c067c-127">lastUpdated</span><span class="sxs-lookup"><span data-stu-id="c067c-127">lastUpdated</span></span>  <br/> |<span data-ttu-id="c067c-128">datetime では、null でないです。</span><span class="sxs-lookup"><span data-stu-id="c067c-128">datetime, not null</span></span>  <br/> |<span data-ttu-id="c067c-129">行が挿入されたときのタイムスタンプです。</span><span class="sxs-lookup"><span data-stu-id="c067c-129">Time stamp of when the row was inserted.</span></span>  <br/> |
   

