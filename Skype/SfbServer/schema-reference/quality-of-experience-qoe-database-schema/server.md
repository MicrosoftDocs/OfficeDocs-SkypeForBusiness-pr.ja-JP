---
title: サーバー テーブル
ms.reviewer: ''
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
ms.openlocfilehash: 877743f5d589cd4fea34039786b33bd410069bb3
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "32212110"
---
# <a name="server-table"></a><span data-ttu-id="71723-104">サーバー テーブル</span><span class="sxs-lookup"><span data-stu-id="71723-104">Server table</span></span>
 
<span data-ttu-id="71723-105">サーバーはテーブルをサポートします。</span><span class="sxs-lookup"><span data-stu-id="71723-105">The Server table is a supporting table.</span></span> <span data-ttu-id="71723-106">各レコードは、1 つのサーバーを表します。</span><span class="sxs-lookup"><span data-stu-id="71723-106">Each record represents one server.</span></span> 
  
|<span data-ttu-id="71723-107">**列**</span><span class="sxs-lookup"><span data-stu-id="71723-107">**Column**</span></span>|<span data-ttu-id="71723-108">**データ型**</span><span class="sxs-lookup"><span data-stu-id="71723-108">**Data Type**</span></span>|<span data-ttu-id="71723-109">**キー/インデックス**</span><span class="sxs-lookup"><span data-stu-id="71723-109">**Key/Index**</span></span>|<span data-ttu-id="71723-110">**詳細**</span><span class="sxs-lookup"><span data-stu-id="71723-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="71723-111">**ServerKey**</span><span class="sxs-lookup"><span data-stu-id="71723-111">**ServerKey**</span></span> <br/> |<span data-ttu-id="71723-112">int</span><span class="sxs-lookup"><span data-stu-id="71723-112">int</span></span>  <br/> |<span data-ttu-id="71723-113">Primary</span><span class="sxs-lookup"><span data-stu-id="71723-113">Primary</span></span>  <br/> |<span data-ttu-id="71723-114">サーバーを識別する一意の番号です。</span><span class="sxs-lookup"><span data-stu-id="71723-114">Unique number identifying the server.</span></span>  <br/> |
|<span data-ttu-id="71723-115">**FQDNOrIP**</span><span class="sxs-lookup"><span data-stu-id="71723-115">**FQDNOrIP**</span></span> <br/> |<span data-ttu-id="71723-116">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="71723-116">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="71723-117">インデックス</span><span class="sxs-lookup"><span data-stu-id="71723-117">index</span></span>  <br/> |<span data-ttu-id="71723-118">MAC アドレスの文字列です。</span><span class="sxs-lookup"><span data-stu-id="71723-118">MAC address string.</span></span>  <br/> |
|<span data-ttu-id="71723-119">**ServerType**</span><span class="sxs-lookup"><span data-stu-id="71723-119">**ServerType**</span></span> <br/> |<span data-ttu-id="71723-120">int</span><span class="sxs-lookup"><span data-stu-id="71723-120">int</span></span>  <br/> |<span data-ttu-id="71723-121">外部</span><span class="sxs-lookup"><span data-stu-id="71723-121">Foreign</span></span>  <br/> |<span data-ttu-id="71723-122">1: 仲介サーバー</span><span class="sxs-lookup"><span data-stu-id="71723-122">1: Mediation Server</span></span>  <br/> <span data-ttu-id="71723-123">2: A/V 会議 Server16394: A/V エッジの service32769: ゲートウェイ</span><span class="sxs-lookup"><span data-stu-id="71723-123">2: A/V Conferencing Server16394: A/V Edge service32769: Gateway</span></span>  <br/> |
|<span data-ttu-id="71723-124">**大文字と小文字**</span><span class="sxs-lookup"><span data-stu-id="71723-124">**PoolName**</span></span> <br/> |<span data-ttu-id="71723-125">nvarchar(512)</span><span class="sxs-lookup"><span data-stu-id="71723-125">nvarchar(512)</span></span>  <br/> ||<span data-ttu-id="71723-126">サーバーが所属するプールです。</span><span class="sxs-lookup"><span data-stu-id="71723-126">Pool the server belongs to.</span></span> <span data-ttu-id="71723-127">のみに適用可能、A/V 会議サーバーです。</span><span class="sxs-lookup"><span data-stu-id="71723-127">Only applicable for the A/V Conferencing Server.</span></span>  <br/> |
|<span data-ttu-id="71723-128">**NextUpdateTS**</span><span class="sxs-lookup"><span data-stu-id="71723-128">**NextUpdateTS**</span></span> <br/> |<span data-ttu-id="71723-129">datetime</span><span class="sxs-lookup"><span data-stu-id="71723-129">datetime</span></span>  <br/> ||<span data-ttu-id="71723-130">内部でのみ使用します。</span><span class="sxs-lookup"><span data-stu-id="71723-130">For internal use only.</span></span>  <br/> |
   

