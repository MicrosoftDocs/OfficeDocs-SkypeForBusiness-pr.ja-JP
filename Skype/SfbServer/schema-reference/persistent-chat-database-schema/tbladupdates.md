---
title: tblADUpdates
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
ms.assetid: ba19fa16-4d2d-4635-ac32-f93e09469546
description: tblADUpdates には、以降の Active Directory 同期手順でまだ処理されていない Active Directory ドメインサービスの変更が含まれています。
ms.openlocfilehash: 6d50e065bd10e11383f606b2a4dfed0d5584cd1e
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2020
ms.locfileid: "41814685"
---
# <a name="tbladupdates"></a><span data-ttu-id="60815-103">tblADUpdates</span><span class="sxs-lookup"><span data-stu-id="60815-103">tblADUpdates</span></span>
 
<span data-ttu-id="60815-104">tblADUpdates には、以降の Active Directory 同期手順でまだ処理されていない Active Directory ドメインサービスの変更が含まれています。</span><span class="sxs-lookup"><span data-stu-id="60815-104">tblADUpdates contains Active Directory Domain Services changes that have not yet been processed by the later Active Directory Sync steps.</span></span>
  
<span data-ttu-id="60815-105">**行**</span><span class="sxs-lookup"><span data-stu-id="60815-105">**Columns**</span></span>

|<span data-ttu-id="60815-106">**列**</span><span class="sxs-lookup"><span data-stu-id="60815-106">**Column**</span></span>|<span data-ttu-id="60815-107">**種類**</span><span class="sxs-lookup"><span data-stu-id="60815-107">**Type**</span></span>|<span data-ttu-id="60815-108">**説明**</span><span class="sxs-lookup"><span data-stu-id="60815-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="60815-109">prinGuid</span><span class="sxs-lookup"><span data-stu-id="60815-109">prinGuid</span></span>  <br/> |<span data-ttu-id="60815-110">GUID、null ではない</span><span class="sxs-lookup"><span data-stu-id="60815-110">GUID, not null</span></span>  <br/> |<span data-ttu-id="60815-111">変更されたオブジェクトのプリンシパル GUID。</span><span class="sxs-lookup"><span data-stu-id="60815-111">Principal GUID of the object that changed.</span></span>  <br/> |
|<span data-ttu-id="60815-112">prinADPath</span><span class="sxs-lookup"><span data-stu-id="60815-112">prinADPath</span></span>  <br/> |<span data-ttu-id="60815-113">nvarchar (384)、null ではない</span><span class="sxs-lookup"><span data-stu-id="60815-113">nvarchar (384), not null</span></span>  <br/> |<span data-ttu-id="60815-114">オブジェクトの識別名。</span><span class="sxs-lookup"><span data-stu-id="60815-114">Distinguished name of the object.</span></span>  <br/> |
|<span data-ttu-id="60815-115">Prin属性が変更されました</span><span class="sxs-lookup"><span data-stu-id="60815-115">prinAttributesChanged</span></span>  <br/> |<span data-ttu-id="60815-116">ビット、null ではない</span><span class="sxs-lookup"><span data-stu-id="60815-116">bit, not null</span></span>  <br/> |<span data-ttu-id="60815-117">オブジェクトの少なくとも1つの属性が変更された場合は True です。</span><span class="sxs-lookup"><span data-stu-id="60815-117">True if at least one attribute of the object changed.</span></span>  <br/> |
|<span data-ttu-id="60815-118">prinMembersChanged</span><span class="sxs-lookup"><span data-stu-id="60815-118">prinMembersChanged</span></span>  <br/> |<span data-ttu-id="60815-119">ビット、null ではない</span><span class="sxs-lookup"><span data-stu-id="60815-119">bit, not null</span></span>  <br/> |<span data-ttu-id="60815-120">メンバーシップが変更された場合は True です。</span><span class="sxs-lookup"><span data-stu-id="60815-120">True if the membership changed.</span></span>  <br/> |
|<span data-ttu-id="60815-121">prinAffiliationsChanged</span><span class="sxs-lookup"><span data-stu-id="60815-121">prinAffiliationsChanged</span></span>  <br/> |<span data-ttu-id="60815-122">ビット、null ではない</span><span class="sxs-lookup"><span data-stu-id="60815-122">bit, not null</span></span>  <br/> |<span data-ttu-id="60815-123">使用されません。</span><span class="sxs-lookup"><span data-stu-id="60815-123">Not used.</span></span>  <br/> |
|<span data-ttu-id="60815-124">プリントが削除されました</span><span class="sxs-lookup"><span data-stu-id="60815-124">prinDeleted</span></span>  <br/> |<span data-ttu-id="60815-125">ビット、null ではない</span><span class="sxs-lookup"><span data-stu-id="60815-125">bit, not null</span></span>  <br/> |<span data-ttu-id="60815-126">オブジェクトが削除された場合は True。</span><span class="sxs-lookup"><span data-stu-id="60815-126">True if the object was deleted.</span></span>  <br/> |
|<span data-ttu-id="60815-127">最終更新日</span><span class="sxs-lookup"><span data-stu-id="60815-127">lastUpdated</span></span>  <br/> |<span data-ttu-id="60815-128">datetime。 null ではありません</span><span class="sxs-lookup"><span data-stu-id="60815-128">datetime, not null</span></span>  <br/> |<span data-ttu-id="60815-129">行が挿入された時刻のタイムスタンプ。</span><span class="sxs-lookup"><span data-stu-id="60815-129">Time stamp of when the row was inserted.</span></span>  <br/> |
   

