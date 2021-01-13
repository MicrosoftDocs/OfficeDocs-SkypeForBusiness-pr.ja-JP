---
title: VoIPDetails ビュー
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
ms.assetid: 14c44736-71ba-4fc5-82c7-1df65bf6261c
description: VoIPDetails ビューには、少なくとも 1 人のユーザーが VoIP ユーザーであるピアツーピア セッションに関する情報が格納されます。 このビューは、Microsoft Lync Server 2013 で導入されました。
ms.openlocfilehash: b42fecc7a0f43f86dba2439a373c7013c605a5e0
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49813077"
---
# <a name="voipdetails-view"></a><span data-ttu-id="b22d3-104">VoIPDetails ビュー</span><span class="sxs-lookup"><span data-stu-id="b22d3-104">VoIPDetails view</span></span>
 
<span data-ttu-id="b22d3-105">VoIPDetails ビューには、少なくとも 1 人のユーザーが VoIP ユーザーであるピアツーピア セッションに関する情報が格納されます。</span><span class="sxs-lookup"><span data-stu-id="b22d3-105">The VoIPDetails view stores information about peer-to-peer sessions, where at least one user is a VoIP user.</span></span> <span data-ttu-id="b22d3-106">このビューは、Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="b22d3-106">This view was introduced in Microsoft Lync Server 2013.</span></span>
  
> [!NOTE]
> <span data-ttu-id="b22d3-107">VoIPDetails ビューには、以下の列に加えて [、SessionDetails](sessiondetails-0.md) ビューのすべての列が含まれます。</span><span class="sxs-lookup"><span data-stu-id="b22d3-107">The VoIPDetails view contains all of the columns in the [SessionDetails view](sessiondetails-0.md) in addition the columns listed below.</span></span>
  
|<span data-ttu-id="b22d3-108">**列**</span><span class="sxs-lookup"><span data-stu-id="b22d3-108">**Column**</span></span>|<span data-ttu-id="b22d3-109">**データ型**</span><span class="sxs-lookup"><span data-stu-id="b22d3-109">**Data Type**</span></span>|<span data-ttu-id="b22d3-110">**詳細**</span><span class="sxs-lookup"><span data-stu-id="b22d3-110">**Details**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="b22d3-111">**FromPhone**</span><span class="sxs-lookup"><span data-stu-id="b22d3-111">**FromPhone**</span></span> <br/> |<span data-ttu-id="b22d3-112">nvarchar(450)</span><span class="sxs-lookup"><span data-stu-id="b22d3-112">nvarchar(450)</span></span>  <br/> |<span data-ttu-id="b22d3-113">セッションを開始したユーザーの 電話 URI。</span><span class="sxs-lookup"><span data-stu-id="b22d3-113">Phone URI of the user who started the session.</span></span>  <br/> |
|<span data-ttu-id="b22d3-114">**ToPhone**</span><span class="sxs-lookup"><span data-stu-id="b22d3-114">**ToPhone**</span></span> <br/> |<span data-ttu-id="b22d3-115">nvarchar(450)</span><span class="sxs-lookup"><span data-stu-id="b22d3-115">nvarchar(450)</span></span>  <br/> |<span data-ttu-id="b22d3-116">セッションに参加したユーザーの 電話 URI。</span><span class="sxs-lookup"><span data-stu-id="b22d3-116">Phone URI of the user who joined the session.</span></span>  <br/> |
|<span data-ttu-id="b22d3-117">**DisconnectedByUri**</span><span class="sxs-lookup"><span data-stu-id="b22d3-117">**DisconnectedByUri**</span></span> <br/> |<span data-ttu-id="b22d3-118">nvarchar(450)</span><span class="sxs-lookup"><span data-stu-id="b22d3-118">nvarchar(450)</span></span>  <br/> |<span data-ttu-id="b22d3-119">セッションを切断したユーザーの URI。</span><span class="sxs-lookup"><span data-stu-id="b22d3-119">URI of the user who disconnected the session.</span></span>  <br/> |
|<span data-ttu-id="b22d3-120">**DisconnectedByUriType**</span><span class="sxs-lookup"><span data-stu-id="b22d3-120">**DisconnectedByUriType**</span></span> <br/> |<span data-ttu-id="b22d3-121">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="b22d3-121">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="b22d3-122">セッションを切断したユーザーの URI の種類。</span><span class="sxs-lookup"><span data-stu-id="b22d3-122">Type of URI of the user who disconnected the session.</span></span> <span data-ttu-id="b22d3-123">詳細については [、UriTypes の表](uritypes.md) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b22d3-123">See the [UriTypes table](uritypes.md) for more information.</span></span> <br/> |
|<span data-ttu-id="b22d3-124">**DisconnectedByTenant**</span><span class="sxs-lookup"><span data-stu-id="b22d3-124">**DisconnectedByTenant**</span></span> <br/> |<span data-ttu-id="b22d3-125">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="b22d3-125">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="b22d3-126">セッションを切断したユーザーのテナント。</span><span class="sxs-lookup"><span data-stu-id="b22d3-126">Tenant of the user who disconnected the session.</span></span>  <br/> |
|<span data-ttu-id="b22d3-127">**DisconnectedByPhone**</span><span class="sxs-lookup"><span data-stu-id="b22d3-127">**DisconnectedByPhone**</span></span> <br/> |<span data-ttu-id="b22d3-128">nvarchar(450)</span><span class="sxs-lookup"><span data-stu-id="b22d3-128">nvarchar(450)</span></span>  <br/> |<span data-ttu-id="b22d3-129">セッションを切断したユーザーの 電話 URI。</span><span class="sxs-lookup"><span data-stu-id="b22d3-129">Phone URI of the user who disconnected the session.</span></span>  <br/> |
|<span data-ttu-id="b22d3-130">**FromMediationServer**</span><span class="sxs-lookup"><span data-stu-id="b22d3-130">**FromMediationServer**</span></span> <br/> |<span data-ttu-id="b22d3-131">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="b22d3-131">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="b22d3-132">セッションを開始したユーザーの仲介サーバー。</span><span class="sxs-lookup"><span data-stu-id="b22d3-132">Mediation Server used by the user who started the session.</span></span>  <br/> |
|<span data-ttu-id="b22d3-133">**ToMediationServer**</span><span class="sxs-lookup"><span data-stu-id="b22d3-133">**ToMediationServer**</span></span> <br/> |<span data-ttu-id="b22d3-134">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="b22d3-134">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="b22d3-135">セッションに参加したユーザーの仲介サーバー。</span><span class="sxs-lookup"><span data-stu-id="b22d3-135">Mediation Server used by the user who joined the session.</span></span>  <br/> |
|<span data-ttu-id="b22d3-136">**FromGateway**</span><span class="sxs-lookup"><span data-stu-id="b22d3-136">**FromGateway**</span></span> <br/> |<span data-ttu-id="b22d3-137">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="b22d3-137">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="b22d3-138">セッションを開始したユーザーが使用するゲートウェイ。</span><span class="sxs-lookup"><span data-stu-id="b22d3-138">Gateway used by the user who started the session.</span></span>  <br/> |
|<span data-ttu-id="b22d3-139">**ToGateway**</span><span class="sxs-lookup"><span data-stu-id="b22d3-139">**ToGateway**</span></span> <br/> |<span data-ttu-id="b22d3-140">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="b22d3-140">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="b22d3-141">セッションに参加したユーザーが使用するゲートウェイ。</span><span class="sxs-lookup"><span data-stu-id="b22d3-141">Gateway used by the user who joined the session.</span></span>  <br/> |
   

