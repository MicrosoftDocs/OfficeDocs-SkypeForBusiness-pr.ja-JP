---
title: VoIPDetails ビュー
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 14c44736-71ba-4fc5-82c7-1df65bf6261c
description: VoIPDetails ビューには、ピアツーピアセッションに関する情報が格納されます。これは、少なくとも1人のユーザーが VoIP ユーザーである場合です。 このビューは、Microsoft Lync Server 2013 で導入されました。
ms.openlocfilehash: 7f5f1e3cf1540e1a12a9365753e494ff2d8a371e
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2019
ms.locfileid: "34295665"
---
# <a name="voipdetails-view"></a><span data-ttu-id="53b4d-104">VoIPDetails ビュー</span><span class="sxs-lookup"><span data-stu-id="53b4d-104">VoIPDetails view</span></span>
 
<span data-ttu-id="53b4d-105">VoIPDetails ビューには、ピアツーピアセッションに関する情報が格納されます。これは、少なくとも1人のユーザーが VoIP ユーザーである場合です。</span><span class="sxs-lookup"><span data-stu-id="53b4d-105">The VoIPDetails view stores information about peer-to-peer sessions, where at least one user is a VoIP user.</span></span> <span data-ttu-id="53b4d-106">このビューは、Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="53b4d-106">This view was introduced in Microsoft Lync Server 2013.</span></span>
  
> [!NOTE]
> <span data-ttu-id="53b4d-107">VoIPDetails ビューには、次に示す列と共に、 [Sessiondetails ビュー](sessiondetails-0.md)のすべての列が含まれています。</span><span class="sxs-lookup"><span data-stu-id="53b4d-107">The VoIPDetails view contains all of the columns in the [SessionDetails view](sessiondetails-0.md) in addition the columns listed below.</span></span>
  
|<span data-ttu-id="53b4d-108">**列**</span><span class="sxs-lookup"><span data-stu-id="53b4d-108">**Column**</span></span>|<span data-ttu-id="53b4d-109">**データ型**</span><span class="sxs-lookup"><span data-stu-id="53b4d-109">**Data Type**</span></span>|<span data-ttu-id="53b4d-110">**詳細**</span><span class="sxs-lookup"><span data-stu-id="53b4d-110">**Details**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="53b4d-111">**FromPhone**</span><span class="sxs-lookup"><span data-stu-id="53b4d-111">**FromPhone**</span></span> <br/> |<span data-ttu-id="53b4d-112">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="53b4d-112">nvarchar(450)</span></span>  <br/> |<span data-ttu-id="53b4d-113">セッションを開始したユーザーの電話の URI。</span><span class="sxs-lookup"><span data-stu-id="53b4d-113">Phone URI of the user who started the session.</span></span>  <br/> |
|<span data-ttu-id="53b4d-114">**電話番号**</span><span class="sxs-lookup"><span data-stu-id="53b4d-114">**ToPhone**</span></span> <br/> |<span data-ttu-id="53b4d-115">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="53b4d-115">nvarchar(450)</span></span>  <br/> |<span data-ttu-id="53b4d-116">セッションに参加したユーザーの電話の URI。</span><span class="sxs-lookup"><span data-stu-id="53b4d-116">Phone URI of the user who joined the session.</span></span>  <br/> |
|<span data-ttu-id="53b4d-117">**DisconnectedByUri**</span><span class="sxs-lookup"><span data-stu-id="53b4d-117">**DisconnectedByUri**</span></span> <br/> |<span data-ttu-id="53b4d-118">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="53b4d-118">nvarchar(450)</span></span>  <br/> |<span data-ttu-id="53b4d-119">セッションを切断したユーザーの URI。</span><span class="sxs-lookup"><span data-stu-id="53b4d-119">URI of the user who disconnected the session.</span></span>  <br/> |
|<span data-ttu-id="53b4d-120">**Uritん**</span><span class="sxs-lookup"><span data-stu-id="53b4d-120">**DisconnectedByUriType**</span></span> <br/> |<span data-ttu-id="53b4d-121">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="53b4d-121">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="53b4d-122">セッションを切断したユーザーの URI の種類。</span><span class="sxs-lookup"><span data-stu-id="53b4d-122">Type of URI of the user who disconnected the session.</span></span> <span data-ttu-id="53b4d-123">詳細については、 [UriTypes の表](uritypes.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="53b4d-123">See the [UriTypes table](uritypes.md) for more information.</span></span> <br/> |
|<span data-ttu-id="53b4d-124">**テナント**</span><span class="sxs-lookup"><span data-stu-id="53b4d-124">**DisconnectedByTenant**</span></span> <br/> |<span data-ttu-id="53b4d-125">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="53b4d-125">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="53b4d-126">セッションを切断したユーザーのテナント。</span><span class="sxs-lookup"><span data-stu-id="53b4d-126">Tenant of the user who disconnected the session.</span></span>  <br/> |
|<span data-ttu-id="53b4d-127">**DisconnectedByPhone**</span><span class="sxs-lookup"><span data-stu-id="53b4d-127">**DisconnectedByPhone**</span></span> <br/> |<span data-ttu-id="53b4d-128">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="53b4d-128">nvarchar(450)</span></span>  <br/> |<span data-ttu-id="53b4d-129">セッションを切断したユーザーの電話の URI。</span><span class="sxs-lookup"><span data-stu-id="53b4d-129">Phone URI of the user who disconnected the session.</span></span>  <br/> |
|<span data-ttu-id="53b4d-130">**FromMediationServer**</span><span class="sxs-lookup"><span data-stu-id="53b4d-130">**FromMediationServer**</span></span> <br/> |<span data-ttu-id="53b4d-131">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="53b4d-131">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="53b4d-132">セッションを開始したユーザーによって使用された仲介サーバー。</span><span class="sxs-lookup"><span data-stu-id="53b4d-132">Mediation Server used by the user who started the session.</span></span>  <br/> |
|<span data-ttu-id="53b4d-133">**ToMediationServer**</span><span class="sxs-lookup"><span data-stu-id="53b4d-133">**ToMediationServer**</span></span> <br/> |<span data-ttu-id="53b4d-134">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="53b4d-134">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="53b4d-135">セッションに参加したユーザーが使用した仲介サーバー。</span><span class="sxs-lookup"><span data-stu-id="53b4d-135">Mediation Server used by the user who joined the session.</span></span>  <br/> |
|<span data-ttu-id="53b4d-136">**FromGateway**</span><span class="sxs-lookup"><span data-stu-id="53b4d-136">**FromGateway**</span></span> <br/> |<span data-ttu-id="53b4d-137">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="53b4d-137">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="53b4d-138">セッションを開始したユーザーによって使用されたゲートウェイ。</span><span class="sxs-lookup"><span data-stu-id="53b4d-138">Gateway used by the user who started the session.</span></span>  <br/> |
|<span data-ttu-id="53b4d-139">**ToGateway**</span><span class="sxs-lookup"><span data-stu-id="53b4d-139">**ToGateway**</span></span> <br/> |<span data-ttu-id="53b4d-140">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="53b4d-140">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="53b4d-141">セッションに参加したユーザーが使用したゲートウェイ。</span><span class="sxs-lookup"><span data-stu-id="53b4d-141">Gateway used by the user who joined the session.</span></span>  <br/> |
   

