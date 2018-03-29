---
title: Conference テーブル
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
ms.openlocfilehash: 0390f1f9da264ab5269c7bfdcb4a86c08097b835
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/28/2018
---
# <a name="conference-table"></a><span data-ttu-id="fbf3b-104">Conference テーブル</span><span class="sxs-lookup"><span data-stu-id="fbf3b-104">Conference table</span></span>
 
<span data-ttu-id="fbf3b-105">会議の表は、補助テーブルです。</span><span class="sxs-lookup"><span data-stu-id="fbf3b-105">The Conference table is a supporting table.</span></span> <span data-ttu-id="fbf3b-106">各レコードは、1 つの会議またはピア ツー ピア セッションを表します。</span><span class="sxs-lookup"><span data-stu-id="fbf3b-106">Each record represents one conference or peer-to-peer session.</span></span>
  
|<span data-ttu-id="fbf3b-107">**列**</span><span class="sxs-lookup"><span data-stu-id="fbf3b-107">**Column**</span></span>|<span data-ttu-id="fbf3b-108">**データ型**</span><span class="sxs-lookup"><span data-stu-id="fbf3b-108">**Data Type**</span></span>|<span data-ttu-id="fbf3b-109">**キーまたはインデックス**</span><span class="sxs-lookup"><span data-stu-id="fbf3b-109">**Key/Index**</span></span>|<span data-ttu-id="fbf3b-110">**詳細**</span><span class="sxs-lookup"><span data-stu-id="fbf3b-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="fbf3b-111">**ConferenceKey**</span><span class="sxs-lookup"><span data-stu-id="fbf3b-111">**ConferenceKey**</span></span> <br/> |<span data-ttu-id="fbf3b-112">int</span><span class="sxs-lookup"><span data-stu-id="fbf3b-112">int</span></span>  <br/> |<span data-ttu-id="fbf3b-113">Primary</span><span class="sxs-lookup"><span data-stu-id="fbf3b-113">Primary</span></span>  <br/> |<span data-ttu-id="fbf3b-114">この会議のレコードを識別する一意の番号です。</span><span class="sxs-lookup"><span data-stu-id="fbf3b-114">Unique number identifying this conference record.</span></span>  <br/> |
|<span data-ttu-id="fbf3b-115">**ConfURI**</span><span class="sxs-lookup"><span data-stu-id="fbf3b-115">**ConfURI**</span></span> <br/> |<span data-ttu-id="fbf3b-116">nvarchar(450)</span><span class="sxs-lookup"><span data-stu-id="fbf3b-116">nvarchar(450)</span></span>  <br/> |<span data-ttu-id="fbf3b-117">一意</span><span class="sxs-lookup"><span data-stu-id="fbf3b-117">unique</span></span>  <br/> |<span data-ttu-id="fbf3b-118">会議 URI は、会議では、DialogID この場合は、ピア ツー ピア セッションです。</span><span class="sxs-lookup"><span data-stu-id="fbf3b-118">Conference URI if this is a conference, or DialogID if this is a peer-to-peer session.</span></span>  <br/> |
|<span data-ttu-id="fbf3b-119">**チェックサム**</span><span class="sxs-lookup"><span data-stu-id="fbf3b-119">**Checksum**</span></span> <br/> |<span data-ttu-id="fbf3b-120">int</span><span class="sxs-lookup"><span data-stu-id="fbf3b-120">int</span></span>  <br/> |<span data-ttu-id="fbf3b-121">インデックス</span><span class="sxs-lookup"><span data-stu-id="fbf3b-121">index</span></span>  <br/> |<span data-ttu-id="fbf3b-122">会議 URI のチェックサムです。</span><span class="sxs-lookup"><span data-stu-id="fbf3b-122">Checksum of the conference URI.</span></span> <span data-ttu-id="fbf3b-123">これは、内部的に使用されます。</span><span class="sxs-lookup"><span data-stu-id="fbf3b-123">This is used internally.</span></span>  <br/> |
|<span data-ttu-id="fbf3b-124">**NextUpdateTS**</span><span class="sxs-lookup"><span data-stu-id="fbf3b-124">**NextUpdateTS**</span></span> <br/> |<span data-ttu-id="fbf3b-125">datetime</span><span class="sxs-lookup"><span data-stu-id="fbf3b-125">datetime</span></span>  <br/> ||<span data-ttu-id="fbf3b-126">内部でのみ使用します。</span><span class="sxs-lookup"><span data-stu-id="fbf3b-126">For internal use only.</span></span>  <br/> |
   

