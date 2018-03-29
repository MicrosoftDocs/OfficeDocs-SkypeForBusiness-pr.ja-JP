---
title: サーバー テーブル
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 9af89d08-d35a-48e8-b56d-6df292f973cc
description: サーバーはテーブルをサポートします。 各レコードは、1 つのサーバーを表します。
ms.openlocfilehash: be48b90cc727ebfd0320b38ac0d89a302dab6b07
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/28/2018
---
# <a name="server-table"></a><span data-ttu-id="5c0ed-104">サーバー テーブル</span><span class="sxs-lookup"><span data-stu-id="5c0ed-104">Server table</span></span>
 
<span data-ttu-id="5c0ed-105">サーバーはテーブルをサポートします。</span><span class="sxs-lookup"><span data-stu-id="5c0ed-105">The Server table is a supporting table.</span></span> <span data-ttu-id="5c0ed-106">各レコードは、1 つのサーバーを表します。</span><span class="sxs-lookup"><span data-stu-id="5c0ed-106">Each record represents one server.</span></span> 
  
|<span data-ttu-id="5c0ed-107">**列**</span><span class="sxs-lookup"><span data-stu-id="5c0ed-107">**Column**</span></span>|<span data-ttu-id="5c0ed-108">**データ型**</span><span class="sxs-lookup"><span data-stu-id="5c0ed-108">**Data Type**</span></span>|<span data-ttu-id="5c0ed-109">**キーまたはインデックス**</span><span class="sxs-lookup"><span data-stu-id="5c0ed-109">**Key/Index**</span></span>|<span data-ttu-id="5c0ed-110">**詳細**</span><span class="sxs-lookup"><span data-stu-id="5c0ed-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="5c0ed-111">**ServerKey**</span><span class="sxs-lookup"><span data-stu-id="5c0ed-111">**ServerKey**</span></span> <br/> |<span data-ttu-id="5c0ed-112">int</span><span class="sxs-lookup"><span data-stu-id="5c0ed-112">int</span></span>  <br/> |<span data-ttu-id="5c0ed-113">Primary</span><span class="sxs-lookup"><span data-stu-id="5c0ed-113">Primary</span></span>  <br/> |<span data-ttu-id="5c0ed-114">サーバーを識別する一意の番号です。</span><span class="sxs-lookup"><span data-stu-id="5c0ed-114">Unique number identifying the server.</span></span>  <br/> |
|<span data-ttu-id="5c0ed-115">**FQDNOrIP**</span><span class="sxs-lookup"><span data-stu-id="5c0ed-115">**FQDNOrIP**</span></span> <br/> |<span data-ttu-id="5c0ed-116">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="5c0ed-116">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="5c0ed-117">インデックス</span><span class="sxs-lookup"><span data-stu-id="5c0ed-117">index</span></span>  <br/> |<span data-ttu-id="5c0ed-118">MAC アドレスの文字列です。</span><span class="sxs-lookup"><span data-stu-id="5c0ed-118">MAC address string.</span></span>  <br/> |
|<span data-ttu-id="5c0ed-119">**ServerType**</span><span class="sxs-lookup"><span data-stu-id="5c0ed-119">**ServerType**</span></span> <br/> |<span data-ttu-id="5c0ed-120">int</span><span class="sxs-lookup"><span data-stu-id="5c0ed-120">int</span></span>  <br/> |<span data-ttu-id="5c0ed-121">外部</span><span class="sxs-lookup"><span data-stu-id="5c0ed-121">Foreign</span></span>  <br/> |<span data-ttu-id="5c0ed-122">1: 仲介サーバー</span><span class="sxs-lookup"><span data-stu-id="5c0ed-122">1: Mediation Server</span></span>  <br/> <span data-ttu-id="5c0ed-123">2: A/V 会議 Server16394: A/V エッジの service32769: ゲートウェイ</span><span class="sxs-lookup"><span data-stu-id="5c0ed-123">2: A/V Conferencing Server16394: A/V Edge service32769: Gateway</span></span>  <br/> |
|<span data-ttu-id="5c0ed-124">**大文字と小文字**</span><span class="sxs-lookup"><span data-stu-id="5c0ed-124">**PoolName**</span></span> <br/> |<span data-ttu-id="5c0ed-125">nvarchar(512)</span><span class="sxs-lookup"><span data-stu-id="5c0ed-125">nvarchar(512)</span></span>  <br/> ||<span data-ttu-id="5c0ed-126">サーバーが所属するプールです。</span><span class="sxs-lookup"><span data-stu-id="5c0ed-126">Pool the server belongs to.</span></span> <span data-ttu-id="5c0ed-127">のみに適用可能、A/V 会議サーバーです。</span><span class="sxs-lookup"><span data-stu-id="5c0ed-127">Only applicable for the A/V Conferencing Server.</span></span>  <br/> |
|<span data-ttu-id="5c0ed-128">**NextUpdateTS**</span><span class="sxs-lookup"><span data-stu-id="5c0ed-128">**NextUpdateTS**</span></span> <br/> |<span data-ttu-id="5c0ed-129">datetime</span><span class="sxs-lookup"><span data-stu-id="5c0ed-129">datetime</span></span>  <br/> ||<span data-ttu-id="5c0ed-130">内部でのみ使用します。</span><span class="sxs-lookup"><span data-stu-id="5c0ed-130">For internal use only.</span></span>  <br/> |
   

