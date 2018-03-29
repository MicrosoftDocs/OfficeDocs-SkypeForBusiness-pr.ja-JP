---
title: VoIPDetails ビュー
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 14c44736-71ba-4fc5-82c7-1df65bf6261c
description: VoIPDetails ビューでは、ピア ツー ピア セッションでは、少なくとも 1 つは VoIP ユーザーに関する情報を格納します。 このビューは、Microsoft Lync Server 2013 で導入されました。
ms.openlocfilehash: 93c2afb6383817a4d3941d5b427565fb1d0db098
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/28/2018
---
# <a name="voipdetails-view"></a><span data-ttu-id="70de2-104">VoIPDetails ビュー</span><span class="sxs-lookup"><span data-stu-id="70de2-104">VoIPDetails view</span></span>
 
<span data-ttu-id="70de2-105">VoIPDetails ビューでは、ピア ツー ピア セッションでは、少なくとも 1 つは VoIP ユーザーに関する情報を格納します。</span><span class="sxs-lookup"><span data-stu-id="70de2-105">The VoIPDetails view stores information about peer-to-peer sessions, where at least one user is a VoIP user.</span></span> <span data-ttu-id="70de2-106">このビューは、Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="70de2-106">This view was introduced in Microsoft Lync Server 2013.</span></span>
  
> [!NOTE]
> <span data-ttu-id="70de2-107">VoIPDetails ビューが含まれていますすべて[SessionDetails ビュー](sessiondetails-0.md)内の列のさらに以下の列には。</span><span class="sxs-lookup"><span data-stu-id="70de2-107">The VoIPDetails view contains all of the columns in the [SessionDetails view](sessiondetails-0.md) in addition the columns listed below.</span></span>
  
|<span data-ttu-id="70de2-108">**列**</span><span class="sxs-lookup"><span data-stu-id="70de2-108">**Column**</span></span>|<span data-ttu-id="70de2-109">**データ型**</span><span class="sxs-lookup"><span data-stu-id="70de2-109">**Data Type**</span></span>|<span data-ttu-id="70de2-110">**詳細**</span><span class="sxs-lookup"><span data-stu-id="70de2-110">**Details**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="70de2-111">**FromPhone**</span><span class="sxs-lookup"><span data-stu-id="70de2-111">**FromPhone**</span></span> <br/> |<span data-ttu-id="70de2-112">nvarchar(450)</span><span class="sxs-lookup"><span data-stu-id="70de2-112">nvarchar(450)</span></span>  <br/> |<span data-ttu-id="70de2-113">電話セッションを開始したユーザーの URI です。</span><span class="sxs-lookup"><span data-stu-id="70de2-113">Phone URI of the user who started the session.</span></span>  <br/> |
|<span data-ttu-id="70de2-114">**ToPhone**</span><span class="sxs-lookup"><span data-stu-id="70de2-114">**ToPhone**</span></span> <br/> |<span data-ttu-id="70de2-115">nvarchar(450)</span><span class="sxs-lookup"><span data-stu-id="70de2-115">nvarchar(450)</span></span>  <br/> |<span data-ttu-id="70de2-116">電話のセッションに参加したユーザーの URI。</span><span class="sxs-lookup"><span data-stu-id="70de2-116">Phone URI of the user who joined the session.</span></span>  <br/> |
|<span data-ttu-id="70de2-117">**DisconnectedByUri**</span><span class="sxs-lookup"><span data-stu-id="70de2-117">**DisconnectedByUri**</span></span> <br/> |<span data-ttu-id="70de2-118">nvarchar(450)</span><span class="sxs-lookup"><span data-stu-id="70de2-118">nvarchar(450)</span></span>  <br/> |<span data-ttu-id="70de2-119">セッションを切断したユーザーの URI。</span><span class="sxs-lookup"><span data-stu-id="70de2-119">URI of the user who disconnected the session.</span></span>  <br/> |
|<span data-ttu-id="70de2-120">**DisconnectedByUriType**</span><span class="sxs-lookup"><span data-stu-id="70de2-120">**DisconnectedByUriType**</span></span> <br/> |<span data-ttu-id="70de2-121">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="70de2-121">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="70de2-122">セッションを切断したユーザーの URI の種類です。</span><span class="sxs-lookup"><span data-stu-id="70de2-122">Type of URI of the user who disconnected the session.</span></span> <span data-ttu-id="70de2-123">詳細については、 [UriTypes テーブル](uritypes.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="70de2-123">See the [UriTypes table](uritypes.md) for more information.</span></span> <br/> |
|<span data-ttu-id="70de2-124">**DisconnectedByTenant**</span><span class="sxs-lookup"><span data-stu-id="70de2-124">**DisconnectedByTenant**</span></span> <br/> |<span data-ttu-id="70de2-125">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="70de2-125">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="70de2-126">セッションを切断したユーザーのテナントです。</span><span class="sxs-lookup"><span data-stu-id="70de2-126">Tenant of the user who disconnected the session.</span></span>  <br/> |
|<span data-ttu-id="70de2-127">**DisconnectedByPhone**</span><span class="sxs-lookup"><span data-stu-id="70de2-127">**DisconnectedByPhone**</span></span> <br/> |<span data-ttu-id="70de2-128">nvarchar(450)</span><span class="sxs-lookup"><span data-stu-id="70de2-128">nvarchar(450)</span></span>  <br/> |<span data-ttu-id="70de2-129">電話セッションを切断したユーザーの URI です。</span><span class="sxs-lookup"><span data-stu-id="70de2-129">Phone URI of the user who disconnected the session.</span></span>  <br/> |
|<span data-ttu-id="70de2-130">**FromMediationServer**</span><span class="sxs-lookup"><span data-stu-id="70de2-130">**FromMediationServer**</span></span> <br/> |<span data-ttu-id="70de2-131">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="70de2-131">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="70de2-132">仲介サーバーがセッションを開始したユーザーが使用します。</span><span class="sxs-lookup"><span data-stu-id="70de2-132">Mediation Server used by the user who started the session.</span></span>  <br/> |
|<span data-ttu-id="70de2-133">**ToMediationServer**</span><span class="sxs-lookup"><span data-stu-id="70de2-133">**ToMediationServer**</span></span> <br/> |<span data-ttu-id="70de2-134">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="70de2-134">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="70de2-135">仲介サーバーがセッションに参加したユーザーが使用します。</span><span class="sxs-lookup"><span data-stu-id="70de2-135">Mediation Server used by the user who joined the session.</span></span>  <br/> |
|<span data-ttu-id="70de2-136">**FromGateway**</span><span class="sxs-lookup"><span data-stu-id="70de2-136">**FromGateway**</span></span> <br/> |<span data-ttu-id="70de2-137">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="70de2-137">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="70de2-138">ゲートウェイは、セッションを開始したユーザーが使用します。</span><span class="sxs-lookup"><span data-stu-id="70de2-138">Gateway used by the user who started the session.</span></span>  <br/> |
|<span data-ttu-id="70de2-139">**ToGateway**</span><span class="sxs-lookup"><span data-stu-id="70de2-139">**ToGateway**</span></span> <br/> |<span data-ttu-id="70de2-140">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="70de2-140">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="70de2-141">セッションに参加しているユーザーによって使用されるゲートウェイです。</span><span class="sxs-lookup"><span data-stu-id="70de2-141">Gateway used by the user who joined the session.</span></span>  <br/> |
   

