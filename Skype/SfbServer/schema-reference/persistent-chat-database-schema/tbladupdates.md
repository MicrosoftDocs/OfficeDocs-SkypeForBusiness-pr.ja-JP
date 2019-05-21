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
localization_priority: Normal
ms.assetid: ba19fa16-4d2d-4635-ac32-f93e09469546
description: tblADUpdates には、以降の Active Directory 同期手順でまだ処理されていない Active Directory ドメインサービスの変更が含まれています。
ms.openlocfilehash: 3e7788db170539f888923a4600392e19022bbb0e
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2019
ms.locfileid: "34295560"
---
# <a name="tbladupdates"></a><span data-ttu-id="08c86-103">tblADUpdates</span><span class="sxs-lookup"><span data-stu-id="08c86-103">tblADUpdates</span></span>
 
<span data-ttu-id="08c86-104">tblADUpdates には、以降の Active Directory 同期手順でまだ処理されていない Active Directory ドメインサービスの変更が含まれています。</span><span class="sxs-lookup"><span data-stu-id="08c86-104">tblADUpdates contains Active Directory Domain Services changes that have not yet been processed by the later Active Directory Sync steps.</span></span>
  
<span data-ttu-id="08c86-105">**行**</span><span class="sxs-lookup"><span data-stu-id="08c86-105">**Columns**</span></span>

|<span data-ttu-id="08c86-106">**列**</span><span class="sxs-lookup"><span data-stu-id="08c86-106">**Column**</span></span>|<span data-ttu-id="08c86-107">**型**</span><span class="sxs-lookup"><span data-stu-id="08c86-107">**Type**</span></span>|<span data-ttu-id="08c86-108">**説明**</span><span class="sxs-lookup"><span data-stu-id="08c86-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="08c86-109">prinGuid</span><span class="sxs-lookup"><span data-stu-id="08c86-109">prinGuid</span></span>  <br/> |<span data-ttu-id="08c86-110">GUID、null ではない</span><span class="sxs-lookup"><span data-stu-id="08c86-110">GUID, not null</span></span>  <br/> |<span data-ttu-id="08c86-111">変更されたオブジェクトのプリンシパル GUID。</span><span class="sxs-lookup"><span data-stu-id="08c86-111">Principal GUID of the object that changed.</span></span>  <br/> |
|<span data-ttu-id="08c86-112">prinADPath</span><span class="sxs-lookup"><span data-stu-id="08c86-112">prinADPath</span></span>  <br/> |<span data-ttu-id="08c86-113">nvarchar (384)、null ではない</span><span class="sxs-lookup"><span data-stu-id="08c86-113">nvarchar (384), not null</span></span>  <br/> |<span data-ttu-id="08c86-114">オブジェクトの識別名。</span><span class="sxs-lookup"><span data-stu-id="08c86-114">Distinguished name of the object.</span></span>  <br/> |
|<span data-ttu-id="08c86-115">Prin属性が変更されました</span><span class="sxs-lookup"><span data-stu-id="08c86-115">prinAttributesChanged</span></span>  <br/> |<span data-ttu-id="08c86-116">ビット、null ではない</span><span class="sxs-lookup"><span data-stu-id="08c86-116">bit, not null</span></span>  <br/> |<span data-ttu-id="08c86-117">オブジェクトの少なくとも1つの属性が変更された場合は True です。</span><span class="sxs-lookup"><span data-stu-id="08c86-117">True if at least one attribute of the object changed.</span></span>  <br/> |
|<span data-ttu-id="08c86-118">prinMembersChanged</span><span class="sxs-lookup"><span data-stu-id="08c86-118">prinMembersChanged</span></span>  <br/> |<span data-ttu-id="08c86-119">ビット、null ではない</span><span class="sxs-lookup"><span data-stu-id="08c86-119">bit, not null</span></span>  <br/> |<span data-ttu-id="08c86-120">メンバーシップが変更された場合は True です。</span><span class="sxs-lookup"><span data-stu-id="08c86-120">True if the membership changed.</span></span>  <br/> |
|<span data-ttu-id="08c86-121">prinAffiliationsChanged</span><span class="sxs-lookup"><span data-stu-id="08c86-121">prinAffiliationsChanged</span></span>  <br/> |<span data-ttu-id="08c86-122">ビット、null ではない</span><span class="sxs-lookup"><span data-stu-id="08c86-122">bit, not null</span></span>  <br/> |<span data-ttu-id="08c86-123">使用されません。</span><span class="sxs-lookup"><span data-stu-id="08c86-123">Not used.</span></span>  <br/> |
|<span data-ttu-id="08c86-124">プリントが削除されました</span><span class="sxs-lookup"><span data-stu-id="08c86-124">prinDeleted</span></span>  <br/> |<span data-ttu-id="08c86-125">ビット、null ではない</span><span class="sxs-lookup"><span data-stu-id="08c86-125">bit, not null</span></span>  <br/> |<span data-ttu-id="08c86-126">オブジェクトが削除された場合は True。</span><span class="sxs-lookup"><span data-stu-id="08c86-126">True if the object was deleted.</span></span>  <br/> |
|<span data-ttu-id="08c86-127">最終更新日</span><span class="sxs-lookup"><span data-stu-id="08c86-127">lastUpdated</span></span>  <br/> |<span data-ttu-id="08c86-128">datetime。 null ではありません</span><span class="sxs-lookup"><span data-stu-id="08c86-128">datetime, not null</span></span>  <br/> |<span data-ttu-id="08c86-129">行が挿入された時刻のタイムスタンプ。</span><span class="sxs-lookup"><span data-stu-id="08c86-129">Time stamp of when the row was inserted.</span></span>  <br/> |
   

