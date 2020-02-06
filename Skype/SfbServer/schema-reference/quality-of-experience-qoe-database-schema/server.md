---
title: サーバー テーブル
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
ms.assetid: 9af89d08-d35a-48e8-b56d-6df292f973cc
description: サーバーテーブルは、サポートされているテーブルです。 各レコードは1つのサーバーを表します。
ms.openlocfilehash: e57bb96fd715d67a5b6676a2399dc520f08bac96
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2020
ms.locfileid: "41806135"
---
# <a name="server-table"></a><span data-ttu-id="3c1a5-104">サーバー テーブル</span><span class="sxs-lookup"><span data-stu-id="3c1a5-104">Server table</span></span>
 
<span data-ttu-id="3c1a5-105">サーバーテーブルは、サポートされているテーブルです。</span><span class="sxs-lookup"><span data-stu-id="3c1a5-105">The Server table is a supporting table.</span></span> <span data-ttu-id="3c1a5-106">各レコードは1つのサーバーを表します。</span><span class="sxs-lookup"><span data-stu-id="3c1a5-106">Each record represents one server.</span></span> 
  
|<span data-ttu-id="3c1a5-107">**列**</span><span class="sxs-lookup"><span data-stu-id="3c1a5-107">**Column**</span></span>|<span data-ttu-id="3c1a5-108">**データ型**</span><span class="sxs-lookup"><span data-stu-id="3c1a5-108">**Data Type**</span></span>|<span data-ttu-id="3c1a5-109">**キー/インデックス**</span><span class="sxs-lookup"><span data-stu-id="3c1a5-109">**Key/Index**</span></span>|<span data-ttu-id="3c1a5-110">**詳細**</span><span class="sxs-lookup"><span data-stu-id="3c1a5-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="3c1a5-111">**ServerKey**</span><span class="sxs-lookup"><span data-stu-id="3c1a5-111">**ServerKey**</span></span> <br/> |<span data-ttu-id="3c1a5-112">int</span><span class="sxs-lookup"><span data-stu-id="3c1a5-112">int</span></span>  <br/> |<span data-ttu-id="3c1a5-113">Primary</span><span class="sxs-lookup"><span data-stu-id="3c1a5-113">Primary</span></span>  <br/> |<span data-ttu-id="3c1a5-114">サーバーを識別する一意の番号。</span><span class="sxs-lookup"><span data-stu-id="3c1a5-114">Unique number identifying the server.</span></span>  <br/> |
|<span data-ttu-id="3c1a5-115">**同一の Dnorip**</span><span class="sxs-lookup"><span data-stu-id="3c1a5-115">**FQDNOrIP**</span></span> <br/> |<span data-ttu-id="3c1a5-116">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="3c1a5-116">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="3c1a5-117">位置</span><span class="sxs-lookup"><span data-stu-id="3c1a5-117">index</span></span>  <br/> |<span data-ttu-id="3c1a5-118">MAC アドレス文字列。</span><span class="sxs-lookup"><span data-stu-id="3c1a5-118">MAC address string.</span></span>  <br/> |
|<span data-ttu-id="3c1a5-119">**ServerType**</span><span class="sxs-lookup"><span data-stu-id="3c1a5-119">**ServerType**</span></span> <br/> |<span data-ttu-id="3c1a5-120">int</span><span class="sxs-lookup"><span data-stu-id="3c1a5-120">int</span></span>  <br/> |<span data-ttu-id="3c1a5-121">外部</span><span class="sxs-lookup"><span data-stu-id="3c1a5-121">Foreign</span></span>  <br/> |<span data-ttu-id="3c1a5-122">1: 仲介サーバー</span><span class="sxs-lookup"><span data-stu-id="3c1a5-122">1: Mediation Server</span></span>  <br/> <span data-ttu-id="3c1a5-123">2: a/v 会議 Server16394: A/V Edge service32769: ゲートウェイ</span><span class="sxs-lookup"><span data-stu-id="3c1a5-123">2: A/V Conferencing Server16394: A/V Edge service32769: Gateway</span></span>  <br/> |
|<span data-ttu-id="3c1a5-124">**PoolName**</span><span class="sxs-lookup"><span data-stu-id="3c1a5-124">**PoolName**</span></span> <br/> |<span data-ttu-id="3c1a5-125">nvarchar (512)</span><span class="sxs-lookup"><span data-stu-id="3c1a5-125">nvarchar(512)</span></span>  <br/> ||<span data-ttu-id="3c1a5-126">サーバーが所属するプール。</span><span class="sxs-lookup"><span data-stu-id="3c1a5-126">Pool the server belongs to.</span></span> <span data-ttu-id="3c1a5-127">A/V 会議サーバーにのみ適用されます。</span><span class="sxs-lookup"><span data-stu-id="3c1a5-127">Only applicable for the A/V Conferencing Server.</span></span>  <br/> |
|<span data-ttu-id="3c1a5-128">**Nextupdatupdat**</span><span class="sxs-lookup"><span data-stu-id="3c1a5-128">**NextUpdateTS**</span></span> <br/> |<span data-ttu-id="3c1a5-129">datetime</span><span class="sxs-lookup"><span data-stu-id="3c1a5-129">datetime</span></span>  <br/> ||<span data-ttu-id="3c1a5-130">内部使用のみ。</span><span class="sxs-lookup"><span data-stu-id="3c1a5-130">For internal use only.</span></span>  <br/> |
   

