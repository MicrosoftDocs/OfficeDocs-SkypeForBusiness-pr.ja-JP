---
title: Endpoint テーブル
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
ms.assetid: 500f330d-4d7d-4e88-b1cc-fef9a9de6b5c
description: Endpoint テーブルは、データベースに記録されたセッションに参加したエンドポイントに関する情報を格納するサポート テーブルです。 テーブル内の各レコードは、1 つのエンドポイントを表します。
ms.openlocfilehash: 9caa0571e562a84c1678208f0e70c27317deda3c
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49823067"
---
# <a name="endpoint-table"></a><span data-ttu-id="487e7-104">Endpoint テーブル</span><span class="sxs-lookup"><span data-stu-id="487e7-104">Endpoint table</span></span>
 
<span data-ttu-id="487e7-105">Endpoint テーブルは、データベースに記録されたセッションに参加したエンドポイントに関する情報を格納するサポート テーブルです。</span><span class="sxs-lookup"><span data-stu-id="487e7-105">The Endpoint table is a supporting table that stores information about the endpoints that have participated in sessions recorded in the database.</span></span> <span data-ttu-id="487e7-106">テーブル内の各レコードは、1 つのエンドポイントを表します。</span><span class="sxs-lookup"><span data-stu-id="487e7-106">Each record in the table represents one endpoint.</span></span>
  
|<span data-ttu-id="487e7-107">**列**</span><span class="sxs-lookup"><span data-stu-id="487e7-107">**Column**</span></span>|<span data-ttu-id="487e7-108">**データ型**</span><span class="sxs-lookup"><span data-stu-id="487e7-108">**Data Type**</span></span>|<span data-ttu-id="487e7-109">**キー/インデックス**</span><span class="sxs-lookup"><span data-stu-id="487e7-109">**Key/Index**</span></span>|<span data-ttu-id="487e7-110">**詳細**</span><span class="sxs-lookup"><span data-stu-id="487e7-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="487e7-111">**EndpointKey**</span><span class="sxs-lookup"><span data-stu-id="487e7-111">**EndpointKey**</span></span> <br/> |<span data-ttu-id="487e7-112">int</span><span class="sxs-lookup"><span data-stu-id="487e7-112">int</span></span>  <br/> |<span data-ttu-id="487e7-113">Primary</span><span class="sxs-lookup"><span data-stu-id="487e7-113">Primary</span></span>  <br/> |<span data-ttu-id="487e7-114">このエンドポイントを識別する一意の番号。</span><span class="sxs-lookup"><span data-stu-id="487e7-114">Unique number identifying this endpoint.</span></span>  <br/> |
|<span data-ttu-id="487e7-115">**名前**</span><span class="sxs-lookup"><span data-stu-id="487e7-115">**Name**</span></span> <br/> |<span data-ttu-id="487e7-116">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="487e7-116">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="487e7-117">一意</span><span class="sxs-lookup"><span data-stu-id="487e7-117">Unique</span></span>  <br/> |<span data-ttu-id="487e7-118">エンドポイント名。</span><span class="sxs-lookup"><span data-stu-id="487e7-118">Endpoint name.</span></span>  <br/> |
|<span data-ttu-id="487e7-119">**OS**</span><span class="sxs-lookup"><span data-stu-id="487e7-119">**OS**</span></span> <br/> |<span data-ttu-id="487e7-120">nvarchar(128)</span><span class="sxs-lookup"><span data-stu-id="487e7-120">nvarchar(128)</span></span>  <br/> | <br/> |<span data-ttu-id="487e7-121">エンドポイントのオペレーティング システム (OS)。</span><span class="sxs-lookup"><span data-stu-id="487e7-121">Operating system (OS) of the endpoint.</span></span>  <br/> |
|<span data-ttu-id="487e7-122">**CPUName**</span><span class="sxs-lookup"><span data-stu-id="487e7-122">**CPUName**</span></span> <br/> |<span data-ttu-id="487e7-123">nvarchar(128)</span><span class="sxs-lookup"><span data-stu-id="487e7-123">nvarchar(128)</span></span>  <br/> ||<span data-ttu-id="487e7-124">エンドポイントの CPU 名。</span><span class="sxs-lookup"><span data-stu-id="487e7-124">CPU name of the endpoint.</span></span>  <br/> |
|<span data-ttu-id="487e7-125">**CPUNumberOfCores**</span><span class="sxs-lookup"><span data-stu-id="487e7-125">**CPUNumberOfCores**</span></span> <br/> |<span data-ttu-id="487e7-126">smallint</span><span class="sxs-lookup"><span data-stu-id="487e7-126">smallint</span></span>  <br/> ||<span data-ttu-id="487e7-127">エンドポイントの CPU コアの数。</span><span class="sxs-lookup"><span data-stu-id="487e7-127">Number of CPU cores of the endpoint.</span></span>  <br/> |
|<span data-ttu-id="487e7-128">**CPUProcessorSpeed**</span><span class="sxs-lookup"><span data-stu-id="487e7-128">**CPUProcessorSpeed**</span></span> <br/> |<span data-ttu-id="487e7-129">int</span><span class="sxs-lookup"><span data-stu-id="487e7-129">int</span></span>  <br/> ||<span data-ttu-id="487e7-130">エンドポイントの CPU プロセッサ速度。</span><span class="sxs-lookup"><span data-stu-id="487e7-130">CPU processor speed of the endpoint.</span></span>  <br/> |
|<span data-ttu-id="487e7-131">**VirtualizationFlag**</span><span class="sxs-lookup"><span data-stu-id="487e7-131">**VirtualizationFlag**</span></span> <br/> |<span data-ttu-id="487e7-132">tinyint</span><span class="sxs-lookup"><span data-stu-id="487e7-132">tinyint</span></span>  <br/> || <span data-ttu-id="487e7-133">仮想化環境でシステムが実行されるかどうかを示すビット フラグ:</span><span class="sxs-lookup"><span data-stu-id="487e7-133">Bit flag that indicates if the system is running in a virtualized environment:</span></span> <br/>  <span data-ttu-id="487e7-134">0x0000 - なし</span><span class="sxs-lookup"><span data-stu-id="487e7-134">0x0000 - None</span></span> <br/>  <span data-ttu-id="487e7-135">0x0001 - HyperV</span><span class="sxs-lookup"><span data-stu-id="487e7-135">0x0001 - HyperV</span></span> <br/>  <span data-ttu-id="487e7-136">0x0002 - VMWare</span><span class="sxs-lookup"><span data-stu-id="487e7-136">0x0002 - VMWare</span></span> <br/>  <span data-ttu-id="487e7-137">0x0004 - 仮想 PC</span><span class="sxs-lookup"><span data-stu-id="487e7-137">0x0004 - Virtual PC</span></span> <br/>  <span data-ttu-id="487e7-138">0x0008 - Xen PC</span><span class="sxs-lookup"><span data-stu-id="487e7-138">0x0008 - Xen PC</span></span> <br/> |
   

