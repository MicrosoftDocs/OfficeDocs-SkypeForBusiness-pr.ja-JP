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
localization_priority: Normal
ms.assetid: 9af89d08-d35a-48e8-b56d-6df292f973cc
description: サーバーテーブルは、サポートされているテーブルです。 各レコードは1つのサーバーを表します。
ms.openlocfilehash: 93ba62c262b95b46b76cd445be04a0bc53c5a960
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2019
ms.locfileid: "34294713"
---
# <a name="server-table"></a><span data-ttu-id="06a26-104">サーバー テーブル</span><span class="sxs-lookup"><span data-stu-id="06a26-104">Server table</span></span>
 
<span data-ttu-id="06a26-105">サーバーテーブルは、サポートされているテーブルです。</span><span class="sxs-lookup"><span data-stu-id="06a26-105">The Server table is a supporting table.</span></span> <span data-ttu-id="06a26-106">各レコードは1つのサーバーを表します。</span><span class="sxs-lookup"><span data-stu-id="06a26-106">Each record represents one server.</span></span> 
  
|<span data-ttu-id="06a26-107">**列**</span><span class="sxs-lookup"><span data-stu-id="06a26-107">**Column**</span></span>|<span data-ttu-id="06a26-108">**データ型**</span><span class="sxs-lookup"><span data-stu-id="06a26-108">**Data Type**</span></span>|<span data-ttu-id="06a26-109">**キー/インデックス**</span><span class="sxs-lookup"><span data-stu-id="06a26-109">**Key/Index**</span></span>|<span data-ttu-id="06a26-110">**詳細**</span><span class="sxs-lookup"><span data-stu-id="06a26-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="06a26-111">**ServerKey**</span><span class="sxs-lookup"><span data-stu-id="06a26-111">**ServerKey**</span></span> <br/> |<span data-ttu-id="06a26-112">int</span><span class="sxs-lookup"><span data-stu-id="06a26-112">int</span></span>  <br/> |<span data-ttu-id="06a26-113">Primary</span><span class="sxs-lookup"><span data-stu-id="06a26-113">Primary</span></span>  <br/> |<span data-ttu-id="06a26-114">サーバーを識別する一意の番号。</span><span class="sxs-lookup"><span data-stu-id="06a26-114">Unique number identifying the server.</span></span>  <br/> |
|<span data-ttu-id="06a26-115">**同一の Dnorip**</span><span class="sxs-lookup"><span data-stu-id="06a26-115">**FQDNOrIP**</span></span> <br/> |<span data-ttu-id="06a26-116">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="06a26-116">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="06a26-117">位置</span><span class="sxs-lookup"><span data-stu-id="06a26-117">index</span></span>  <br/> |<span data-ttu-id="06a26-118">MAC アドレス文字列。</span><span class="sxs-lookup"><span data-stu-id="06a26-118">MAC address string.</span></span>  <br/> |
|<span data-ttu-id="06a26-119">**ServerType**</span><span class="sxs-lookup"><span data-stu-id="06a26-119">**ServerType**</span></span> <br/> |<span data-ttu-id="06a26-120">int</span><span class="sxs-lookup"><span data-stu-id="06a26-120">int</span></span>  <br/> |<span data-ttu-id="06a26-121">外部</span><span class="sxs-lookup"><span data-stu-id="06a26-121">Foreign</span></span>  <br/> |<span data-ttu-id="06a26-122">1: 仲介サーバー</span><span class="sxs-lookup"><span data-stu-id="06a26-122">1: Mediation Server</span></span>  <br/> <span data-ttu-id="06a26-123">2: a/v 会議 Server16394: A/V Edge service32769: ゲートウェイ</span><span class="sxs-lookup"><span data-stu-id="06a26-123">2: A/V Conferencing Server16394: A/V Edge service32769: Gateway</span></span>  <br/> |
|<span data-ttu-id="06a26-124">**PoolName**</span><span class="sxs-lookup"><span data-stu-id="06a26-124">**PoolName**</span></span> <br/> |<span data-ttu-id="06a26-125">nvarchar (512)</span><span class="sxs-lookup"><span data-stu-id="06a26-125">nvarchar(512)</span></span>  <br/> ||<span data-ttu-id="06a26-126">サーバーが所属するプール。</span><span class="sxs-lookup"><span data-stu-id="06a26-126">Pool the server belongs to.</span></span> <span data-ttu-id="06a26-127">A/V 会議サーバーにのみ適用されます。</span><span class="sxs-lookup"><span data-stu-id="06a26-127">Only applicable for the A/V Conferencing Server.</span></span>  <br/> |
|<span data-ttu-id="06a26-128">**Nextupdatupdat**</span><span class="sxs-lookup"><span data-stu-id="06a26-128">**NextUpdateTS**</span></span> <br/> |<span data-ttu-id="06a26-129">datetime</span><span class="sxs-lookup"><span data-stu-id="06a26-129">datetime</span></span>  <br/> ||<span data-ttu-id="06a26-130">内部使用のみ。</span><span class="sxs-lookup"><span data-stu-id="06a26-130">For internal use only.</span></span>  <br/> |
   

