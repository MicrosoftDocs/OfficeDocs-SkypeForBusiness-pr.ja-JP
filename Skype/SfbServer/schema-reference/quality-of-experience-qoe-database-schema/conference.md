---
title: Conference テーブル
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 2a2c327c-4719-42dc-a3bb-6dbc0864d9af
description: 会議の表は、補助テーブルです。 各レコードは、1 つの会議またはピア ツー ピア セッションを表します。
ms.openlocfilehash: 0914e98aed4aea16e5301ccae454e925663454a5
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "33920167"
---
# <a name="conference-table"></a><span data-ttu-id="1f985-104">Conference テーブル</span><span class="sxs-lookup"><span data-stu-id="1f985-104">Conference table</span></span>
 
<span data-ttu-id="1f985-105">会議の表は、補助テーブルです。</span><span class="sxs-lookup"><span data-stu-id="1f985-105">The Conference table is a supporting table.</span></span> <span data-ttu-id="1f985-106">各レコードは、1 つの会議またはピア ツー ピア セッションを表します。</span><span class="sxs-lookup"><span data-stu-id="1f985-106">Each record represents one conference or peer-to-peer session.</span></span>
  
|<span data-ttu-id="1f985-107">**列**</span><span class="sxs-lookup"><span data-stu-id="1f985-107">**Column**</span></span>|<span data-ttu-id="1f985-108">**データ型**</span><span class="sxs-lookup"><span data-stu-id="1f985-108">**Data Type**</span></span>|<span data-ttu-id="1f985-109">**キー/インデックス**</span><span class="sxs-lookup"><span data-stu-id="1f985-109">**Key/Index**</span></span>|<span data-ttu-id="1f985-110">**詳細**</span><span class="sxs-lookup"><span data-stu-id="1f985-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="1f985-111">**ConferenceKey**</span><span class="sxs-lookup"><span data-stu-id="1f985-111">**ConferenceKey**</span></span> <br/> |<span data-ttu-id="1f985-112">int</span><span class="sxs-lookup"><span data-stu-id="1f985-112">int</span></span>  <br/> |<span data-ttu-id="1f985-113">Primary</span><span class="sxs-lookup"><span data-stu-id="1f985-113">Primary</span></span>  <br/> |<span data-ttu-id="1f985-114">この会議のレコードを識別する一意の番号です。</span><span class="sxs-lookup"><span data-stu-id="1f985-114">Unique number identifying this conference record.</span></span>  <br/> |
|<span data-ttu-id="1f985-115">**ConfURI**</span><span class="sxs-lookup"><span data-stu-id="1f985-115">**ConfURI**</span></span> <br/> |<span data-ttu-id="1f985-116">nvarchar(450)</span><span class="sxs-lookup"><span data-stu-id="1f985-116">nvarchar(450)</span></span>  <br/> |<span data-ttu-id="1f985-117">一意</span><span class="sxs-lookup"><span data-stu-id="1f985-117">unique</span></span>  <br/> |<span data-ttu-id="1f985-118">会議 URI は、会議では、DialogID この場合は、ピア ツー ピア セッションです。</span><span class="sxs-lookup"><span data-stu-id="1f985-118">Conference URI if this is a conference, or DialogID if this is a peer-to-peer session.</span></span>  <br/> |
|<span data-ttu-id="1f985-119">**チェックサム**</span><span class="sxs-lookup"><span data-stu-id="1f985-119">**Checksum**</span></span> <br/> |<span data-ttu-id="1f985-120">int</span><span class="sxs-lookup"><span data-stu-id="1f985-120">int</span></span>  <br/> |<span data-ttu-id="1f985-121">インデックス</span><span class="sxs-lookup"><span data-stu-id="1f985-121">index</span></span>  <br/> |<span data-ttu-id="1f985-122">会議 URI のチェックサムです。</span><span class="sxs-lookup"><span data-stu-id="1f985-122">Checksum of the conference URI.</span></span> <span data-ttu-id="1f985-123">これは、内部的に使用されます。</span><span class="sxs-lookup"><span data-stu-id="1f985-123">This is used internally.</span></span>  <br/> |
|<span data-ttu-id="1f985-124">**NextUpdateTS**</span><span class="sxs-lookup"><span data-stu-id="1f985-124">**NextUpdateTS**</span></span> <br/> |<span data-ttu-id="1f985-125">datetime</span><span class="sxs-lookup"><span data-stu-id="1f985-125">datetime</span></span>  <br/> ||<span data-ttu-id="1f985-126">内部でのみ使用します。</span><span class="sxs-lookup"><span data-stu-id="1f985-126">For internal use only.</span></span>  <br/> |
   

