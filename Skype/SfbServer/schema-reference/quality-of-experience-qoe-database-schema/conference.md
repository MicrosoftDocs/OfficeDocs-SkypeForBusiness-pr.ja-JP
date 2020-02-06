---
title: Conference テーブル
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 2a2c327c-4719-42dc-a3bb-6dbc0864d9af
description: 会議の表は、サポートされているテーブルです。 各レコードは、1つの会議またはピアツーピアセッションを表します。
ms.openlocfilehash: 95e08861adaca2e76144f35037626e7b03afd962
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2020
ms.locfileid: "41810305"
---
# <a name="conference-table"></a><span data-ttu-id="cc75b-104">Conference テーブル</span><span class="sxs-lookup"><span data-stu-id="cc75b-104">Conference table</span></span>
 
<span data-ttu-id="cc75b-105">会議の表は、サポートされているテーブルです。</span><span class="sxs-lookup"><span data-stu-id="cc75b-105">The Conference table is a supporting table.</span></span> <span data-ttu-id="cc75b-106">各レコードは、1つの会議またはピアツーピアセッションを表します。</span><span class="sxs-lookup"><span data-stu-id="cc75b-106">Each record represents one conference or peer-to-peer session.</span></span>
  
|<span data-ttu-id="cc75b-107">**列**</span><span class="sxs-lookup"><span data-stu-id="cc75b-107">**Column**</span></span>|<span data-ttu-id="cc75b-108">**データ型**</span><span class="sxs-lookup"><span data-stu-id="cc75b-108">**Data Type**</span></span>|<span data-ttu-id="cc75b-109">**キー/インデックス**</span><span class="sxs-lookup"><span data-stu-id="cc75b-109">**Key/Index**</span></span>|<span data-ttu-id="cc75b-110">**詳細**</span><span class="sxs-lookup"><span data-stu-id="cc75b-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="cc75b-111">**ConferenceKey**</span><span class="sxs-lookup"><span data-stu-id="cc75b-111">**ConferenceKey**</span></span> <br/> |<span data-ttu-id="cc75b-112">int</span><span class="sxs-lookup"><span data-stu-id="cc75b-112">int</span></span>  <br/> |<span data-ttu-id="cc75b-113">Primary</span><span class="sxs-lookup"><span data-stu-id="cc75b-113">Primary</span></span>  <br/> |<span data-ttu-id="cc75b-114">この会議レコードを識別する一意の番号です。</span><span class="sxs-lookup"><span data-stu-id="cc75b-114">Unique number identifying this conference record.</span></span>  <br/> |
|<span data-ttu-id="cc75b-115">**ConfURI**</span><span class="sxs-lookup"><span data-stu-id="cc75b-115">**ConfURI**</span></span> <br/> |<span data-ttu-id="cc75b-116">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="cc75b-116">nvarchar(450)</span></span>  <br/> |<span data-ttu-id="cc75b-117">一意</span><span class="sxs-lookup"><span data-stu-id="cc75b-117">unique</span></span>  <br/> |<span data-ttu-id="cc75b-118">会議の URI (会議の場合) または [この Id がピアツーピアセッションの場合] です。</span><span class="sxs-lookup"><span data-stu-id="cc75b-118">Conference URI if this is a conference, or DialogID if this is a peer-to-peer session.</span></span>  <br/> |
|<span data-ttu-id="cc75b-119">**サム**</span><span class="sxs-lookup"><span data-stu-id="cc75b-119">**Checksum**</span></span> <br/> |<span data-ttu-id="cc75b-120">int</span><span class="sxs-lookup"><span data-stu-id="cc75b-120">int</span></span>  <br/> |<span data-ttu-id="cc75b-121">位置</span><span class="sxs-lookup"><span data-stu-id="cc75b-121">index</span></span>  <br/> |<span data-ttu-id="cc75b-122">会議 URI のチェックサム。</span><span class="sxs-lookup"><span data-stu-id="cc75b-122">Checksum of the conference URI.</span></span> <span data-ttu-id="cc75b-123">これは内部的に使用されます。</span><span class="sxs-lookup"><span data-stu-id="cc75b-123">This is used internally.</span></span>  <br/> |
|<span data-ttu-id="cc75b-124">**Nextupdatupdat**</span><span class="sxs-lookup"><span data-stu-id="cc75b-124">**NextUpdateTS**</span></span> <br/> |<span data-ttu-id="cc75b-125">datetime</span><span class="sxs-lookup"><span data-stu-id="cc75b-125">datetime</span></span>  <br/> ||<span data-ttu-id="cc75b-126">内部使用のみ。</span><span class="sxs-lookup"><span data-stu-id="cc75b-126">For internal use only.</span></span>  <br/> |
   

