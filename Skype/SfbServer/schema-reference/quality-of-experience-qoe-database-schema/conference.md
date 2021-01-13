---
title: 会議テーブル
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 2a2c327c-4719-42dc-a3bb-6dbc0864d9af
description: 会議テーブルはサポート テーブルです。 各レコードは、1 つの電話会議またはピアツーピア セッションを表します。
ms.openlocfilehash: 3840ad9bb4f9b0ff0aea5068c73d307d5bd0cf5e
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49802787"
---
# <a name="conference-table"></a><span data-ttu-id="6e3af-104">会議テーブル</span><span class="sxs-lookup"><span data-stu-id="6e3af-104">Conference table</span></span>
 
<span data-ttu-id="6e3af-105">会議テーブルはサポート テーブルです。</span><span class="sxs-lookup"><span data-stu-id="6e3af-105">The Conference table is a supporting table.</span></span> <span data-ttu-id="6e3af-106">各レコードは、1 つの電話会議またはピアツーピア セッションを表します。</span><span class="sxs-lookup"><span data-stu-id="6e3af-106">Each record represents one conference or peer-to-peer session.</span></span>
  
|<span data-ttu-id="6e3af-107">**列**</span><span class="sxs-lookup"><span data-stu-id="6e3af-107">**Column**</span></span>|<span data-ttu-id="6e3af-108">**データ型**</span><span class="sxs-lookup"><span data-stu-id="6e3af-108">**Data Type**</span></span>|<span data-ttu-id="6e3af-109">**キー/インデックス**</span><span class="sxs-lookup"><span data-stu-id="6e3af-109">**Key/Index**</span></span>|<span data-ttu-id="6e3af-110">**詳細**</span><span class="sxs-lookup"><span data-stu-id="6e3af-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="6e3af-111">**ConferenceKey**</span><span class="sxs-lookup"><span data-stu-id="6e3af-111">**ConferenceKey**</span></span> <br/> |<span data-ttu-id="6e3af-112">int</span><span class="sxs-lookup"><span data-stu-id="6e3af-112">int</span></span>  <br/> |<span data-ttu-id="6e3af-113">Primary</span><span class="sxs-lookup"><span data-stu-id="6e3af-113">Primary</span></span>  <br/> |<span data-ttu-id="6e3af-114">この電話会議レコードを識別する一意の番号。</span><span class="sxs-lookup"><span data-stu-id="6e3af-114">Unique number identifying this conference record.</span></span>  <br/> |
|<span data-ttu-id="6e3af-115">**ConfURI**</span><span class="sxs-lookup"><span data-stu-id="6e3af-115">**ConfURI**</span></span> <br/> |<span data-ttu-id="6e3af-116">nvarchar(450)</span><span class="sxs-lookup"><span data-stu-id="6e3af-116">nvarchar(450)</span></span>  <br/> |<span data-ttu-id="6e3af-117">unique</span><span class="sxs-lookup"><span data-stu-id="6e3af-117">unique</span></span>  <br/> |<span data-ttu-id="6e3af-118">これが会議の場合は会議 URI、ピアツーピア セッションの場合は DialogID です。</span><span class="sxs-lookup"><span data-stu-id="6e3af-118">Conference URI if this is a conference, or DialogID if this is a peer-to-peer session.</span></span>  <br/> |
|<span data-ttu-id="6e3af-119">**チェックサム**</span><span class="sxs-lookup"><span data-stu-id="6e3af-119">**Checksum**</span></span> <br/> |<span data-ttu-id="6e3af-120">int</span><span class="sxs-lookup"><span data-stu-id="6e3af-120">int</span></span>  <br/> |<span data-ttu-id="6e3af-121">index</span><span class="sxs-lookup"><span data-stu-id="6e3af-121">index</span></span>  <br/> |<span data-ttu-id="6e3af-122">電話会議 URI のチェックサム。</span><span class="sxs-lookup"><span data-stu-id="6e3af-122">Checksum of the conference URI.</span></span> <span data-ttu-id="6e3af-123">これは内部で使用されます。</span><span class="sxs-lookup"><span data-stu-id="6e3af-123">This is used internally.</span></span>  <br/> |
|<span data-ttu-id="6e3af-124">**NextUpdateTS**</span><span class="sxs-lookup"><span data-stu-id="6e3af-124">**NextUpdateTS**</span></span> <br/> |<span data-ttu-id="6e3af-125">日付型</span><span class="sxs-lookup"><span data-stu-id="6e3af-125">datetime</span></span>  <br/> ||<span data-ttu-id="6e3af-126">内部使用のみ。</span><span class="sxs-lookup"><span data-stu-id="6e3af-126">For internal use only.</span></span>  <br/> |
   

