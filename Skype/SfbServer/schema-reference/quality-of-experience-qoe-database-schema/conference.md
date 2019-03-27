---
title: Conference テーブル
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 2a2c327c-4719-42dc-a3bb-6dbc0864d9af
description: 会議の表は、補助テーブルです。 各レコードは、1 つの会議またはピア ツー ピア セッションを表します。
ms.openlocfilehash: bae144ff574f19155e11b8a2fbfd3548df356c2a
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/27/2019
ms.locfileid: "30874040"
---
# <a name="conference-table"></a><span data-ttu-id="926de-104">Conference テーブル</span><span class="sxs-lookup"><span data-stu-id="926de-104">Conference table</span></span>
 
<span data-ttu-id="926de-105">会議の表は、補助テーブルです。</span><span class="sxs-lookup"><span data-stu-id="926de-105">The Conference table is a supporting table.</span></span> <span data-ttu-id="926de-106">各レコードは、1 つの会議またはピア ツー ピア セッションを表します。</span><span class="sxs-lookup"><span data-stu-id="926de-106">Each record represents one conference or peer-to-peer session.</span></span>
  
|<span data-ttu-id="926de-107">**列**</span><span class="sxs-lookup"><span data-stu-id="926de-107">**Column**</span></span>|<span data-ttu-id="926de-108">**データ型**</span><span class="sxs-lookup"><span data-stu-id="926de-108">**Data Type**</span></span>|<span data-ttu-id="926de-109">**キー/インデックス**</span><span class="sxs-lookup"><span data-stu-id="926de-109">**Key/Index**</span></span>|<span data-ttu-id="926de-110">**詳細**</span><span class="sxs-lookup"><span data-stu-id="926de-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="926de-111">**ConferenceKey**</span><span class="sxs-lookup"><span data-stu-id="926de-111">**ConferenceKey**</span></span> <br/> |<span data-ttu-id="926de-112">int</span><span class="sxs-lookup"><span data-stu-id="926de-112">int</span></span>  <br/> |<span data-ttu-id="926de-113">Primary</span><span class="sxs-lookup"><span data-stu-id="926de-113">Primary</span></span>  <br/> |<span data-ttu-id="926de-114">この会議のレコードを識別する一意の番号です。</span><span class="sxs-lookup"><span data-stu-id="926de-114">Unique number identifying this conference record.</span></span>  <br/> |
|<span data-ttu-id="926de-115">**ConfURI**</span><span class="sxs-lookup"><span data-stu-id="926de-115">**ConfURI**</span></span> <br/> |<span data-ttu-id="926de-116">nvarchar(450)</span><span class="sxs-lookup"><span data-stu-id="926de-116">nvarchar(450)</span></span>  <br/> |<span data-ttu-id="926de-117">一意</span><span class="sxs-lookup"><span data-stu-id="926de-117">unique</span></span>  <br/> |<span data-ttu-id="926de-118">会議 URI は、会議では、DialogID この場合は、ピア ツー ピア セッションです。</span><span class="sxs-lookup"><span data-stu-id="926de-118">Conference URI if this is a conference, or DialogID if this is a peer-to-peer session.</span></span>  <br/> |
|<span data-ttu-id="926de-119">**チェックサム**</span><span class="sxs-lookup"><span data-stu-id="926de-119">**Checksum**</span></span> <br/> |<span data-ttu-id="926de-120">int</span><span class="sxs-lookup"><span data-stu-id="926de-120">int</span></span>  <br/> |<span data-ttu-id="926de-121">インデックス</span><span class="sxs-lookup"><span data-stu-id="926de-121">index</span></span>  <br/> |<span data-ttu-id="926de-122">会議 URI のチェックサムです。</span><span class="sxs-lookup"><span data-stu-id="926de-122">Checksum of the conference URI.</span></span> <span data-ttu-id="926de-123">これは、内部的に使用されます。</span><span class="sxs-lookup"><span data-stu-id="926de-123">This is used internally.</span></span>  <br/> |
|<span data-ttu-id="926de-124">**NextUpdateTS**</span><span class="sxs-lookup"><span data-stu-id="926de-124">**NextUpdateTS**</span></span> <br/> |<span data-ttu-id="926de-125">datetime</span><span class="sxs-lookup"><span data-stu-id="926de-125">datetime</span></span>  <br/> ||<span data-ttu-id="926de-126">内部でのみ使用します。</span><span class="sxs-lookup"><span data-stu-id="926de-126">For internal use only.</span></span>  <br/> |
   

