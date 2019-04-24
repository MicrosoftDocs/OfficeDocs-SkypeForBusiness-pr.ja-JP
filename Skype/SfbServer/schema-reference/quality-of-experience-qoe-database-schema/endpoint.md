---
title: Endpoint テーブル
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 500f330d-4d7d-4e88-b1cc-fef9a9de6b5c
description: エンドポイントはデータベースに記録されているセッションに参加したエンドポイントに関する情報を格納するサポート テーブルです。 テーブル内の各レコードは、1 つのエンドポイントを表します。
ms.openlocfilehash: f9c304408006ef9caf5521b8f0bbe28c2d917abe
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "32212243"
---
# <a name="endpoint-table"></a><span data-ttu-id="69966-104">Endpoint テーブル</span><span class="sxs-lookup"><span data-stu-id="69966-104">Endpoint table</span></span>
 
<span data-ttu-id="69966-105">エンドポイントはデータベースに記録されているセッションに参加したエンドポイントに関する情報を格納するサポート テーブルです。</span><span class="sxs-lookup"><span data-stu-id="69966-105">The Endpoint table is a supporting table that stores information about the endpoints that have participated in sessions recorded in the database.</span></span> <span data-ttu-id="69966-106">テーブル内の各レコードは、1 つのエンドポイントを表します。</span><span class="sxs-lookup"><span data-stu-id="69966-106">Each record in the table represents one endpoint.</span></span>
  
|<span data-ttu-id="69966-107">**列**</span><span class="sxs-lookup"><span data-stu-id="69966-107">**Column**</span></span>|<span data-ttu-id="69966-108">**データ型**</span><span class="sxs-lookup"><span data-stu-id="69966-108">**Data Type**</span></span>|<span data-ttu-id="69966-109">**キー/インデックス**</span><span class="sxs-lookup"><span data-stu-id="69966-109">**Key/Index**</span></span>|<span data-ttu-id="69966-110">**詳細**</span><span class="sxs-lookup"><span data-stu-id="69966-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="69966-111">**EndpointKey**</span><span class="sxs-lookup"><span data-stu-id="69966-111">**EndpointKey**</span></span> <br/> |<span data-ttu-id="69966-112">int</span><span class="sxs-lookup"><span data-stu-id="69966-112">int</span></span>  <br/> |<span data-ttu-id="69966-113">Primary</span><span class="sxs-lookup"><span data-stu-id="69966-113">Primary</span></span>  <br/> |<span data-ttu-id="69966-114">このエンドポイントを識別する一意の番号です。</span><span class="sxs-lookup"><span data-stu-id="69966-114">Unique number identifying this endpoint.</span></span>  <br/> |
|<span data-ttu-id="69966-115">**名前**</span><span class="sxs-lookup"><span data-stu-id="69966-115">**Name**</span></span> <br/> |<span data-ttu-id="69966-116">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="69966-116">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="69966-117">一意</span><span class="sxs-lookup"><span data-stu-id="69966-117">Unique</span></span>  <br/> |<span data-ttu-id="69966-118">エンドポイントの名前です。</span><span class="sxs-lookup"><span data-stu-id="69966-118">Endpoint name.</span></span>  <br/> |
|<span data-ttu-id="69966-119">**OS**</span><span class="sxs-lookup"><span data-stu-id="69966-119">**OS**</span></span> <br/> |<span data-ttu-id="69966-120">nvarchar (128)</span><span class="sxs-lookup"><span data-stu-id="69966-120">nvarchar(128)</span></span>  <br/> | <br/> |<span data-ttu-id="69966-121">エンドポイントのオペレーティング システム (OS)。</span><span class="sxs-lookup"><span data-stu-id="69966-121">Operating system (OS) of the endpoint.</span></span>  <br/> |
|<span data-ttu-id="69966-122">**CPUName**</span><span class="sxs-lookup"><span data-stu-id="69966-122">**CPUName**</span></span> <br/> |<span data-ttu-id="69966-123">nvarchar (128)</span><span class="sxs-lookup"><span data-stu-id="69966-123">nvarchar(128)</span></span>  <br/> ||<span data-ttu-id="69966-124">エンドポイントの CPU の名前です。</span><span class="sxs-lookup"><span data-stu-id="69966-124">CPU name of the endpoint.</span></span>  <br/> |
|<span data-ttu-id="69966-125">**CPUNumberOfCores**</span><span class="sxs-lookup"><span data-stu-id="69966-125">**CPUNumberOfCores**</span></span> <br/> |<span data-ttu-id="69966-126">smallint</span><span class="sxs-lookup"><span data-stu-id="69966-126">smallint</span></span>  <br/> ||<span data-ttu-id="69966-127">エンドポイントの CPU コアの数です。</span><span class="sxs-lookup"><span data-stu-id="69966-127">Number of CPU cores of the endpoint.</span></span>  <br/> |
|<span data-ttu-id="69966-128">**CPUProcessorSpeed**</span><span class="sxs-lookup"><span data-stu-id="69966-128">**CPUProcessorSpeed**</span></span> <br/> |<span data-ttu-id="69966-129">int</span><span class="sxs-lookup"><span data-stu-id="69966-129">int</span></span>  <br/> ||<span data-ttu-id="69966-130">エンドポイントの CPU のプロセッサ速度です。</span><span class="sxs-lookup"><span data-stu-id="69966-130">CPU processor speed of the endpoint.</span></span>  <br/> |
|<span data-ttu-id="69966-131">**VirtualizationFlag**</span><span class="sxs-lookup"><span data-stu-id="69966-131">**VirtualizationFlag**</span></span> <br/> |<span data-ttu-id="69966-132">tinyint</span><span class="sxs-lookup"><span data-stu-id="69966-132">tinyint</span></span>  <br/> || <span data-ttu-id="69966-133">システムが仮想化環境で実行されているかどうかであることを示すビット フラグ。</span><span class="sxs-lookup"><span data-stu-id="69966-133">Bit flag that indicates if the system is running in a virtualized environment:</span></span> <br/>  <span data-ttu-id="69966-134">0x0000 - なし</span><span class="sxs-lookup"><span data-stu-id="69966-134">0x0000 - None</span></span> <br/>  <span data-ttu-id="69966-135">0x0001 - HyperV</span><span class="sxs-lookup"><span data-stu-id="69966-135">0x0001 - HyperV</span></span> <br/>  <span data-ttu-id="69966-136">0x0002 - VMWare</span><span class="sxs-lookup"><span data-stu-id="69966-136">0x0002 - VMWare</span></span> <br/>  <span data-ttu-id="69966-137">0x0004 - 仮想 PC</span><span class="sxs-lookup"><span data-stu-id="69966-137">0x0004 - Virtual PC</span></span> <br/>  <span data-ttu-id="69966-138">0x0008 - Xen PC</span><span class="sxs-lookup"><span data-stu-id="69966-138">0x0008 - Xen PC</span></span> <br/> |
   

