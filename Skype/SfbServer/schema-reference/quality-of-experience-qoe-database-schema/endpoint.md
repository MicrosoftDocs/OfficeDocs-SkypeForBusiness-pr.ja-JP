---
title: Endpoint テーブル
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
ms.assetid: 500f330d-4d7d-4e88-b1cc-fef9a9de6b5c
description: エンドポイントテーブルは、データベースに記録されているセッションに参加しているエンドポイントに関する情報を格納するサポートテーブルです。 テーブル内の各レコードは、1つのエンドポイントを表します。
ms.openlocfilehash: b64b19a3149fa3d490ea8dc957699c0a114f763c
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2020
ms.locfileid: "41809555"
---
# <a name="endpoint-table"></a><span data-ttu-id="2f04b-104">Endpoint テーブル</span><span class="sxs-lookup"><span data-stu-id="2f04b-104">Endpoint table</span></span>
 
<span data-ttu-id="2f04b-105">エンドポイントテーブルは、データベースに記録されているセッションに参加しているエンドポイントに関する情報を格納するサポートテーブルです。</span><span class="sxs-lookup"><span data-stu-id="2f04b-105">The Endpoint table is a supporting table that stores information about the endpoints that have participated in sessions recorded in the database.</span></span> <span data-ttu-id="2f04b-106">テーブル内の各レコードは、1つのエンドポイントを表します。</span><span class="sxs-lookup"><span data-stu-id="2f04b-106">Each record in the table represents one endpoint.</span></span>
  
|<span data-ttu-id="2f04b-107">**列**</span><span class="sxs-lookup"><span data-stu-id="2f04b-107">**Column**</span></span>|<span data-ttu-id="2f04b-108">**データ型**</span><span class="sxs-lookup"><span data-stu-id="2f04b-108">**Data Type**</span></span>|<span data-ttu-id="2f04b-109">**キー/インデックス**</span><span class="sxs-lookup"><span data-stu-id="2f04b-109">**Key/Index**</span></span>|<span data-ttu-id="2f04b-110">**詳細**</span><span class="sxs-lookup"><span data-stu-id="2f04b-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="2f04b-111">**EndpointKey**</span><span class="sxs-lookup"><span data-stu-id="2f04b-111">**EndpointKey**</span></span> <br/> |<span data-ttu-id="2f04b-112">int</span><span class="sxs-lookup"><span data-stu-id="2f04b-112">int</span></span>  <br/> |<span data-ttu-id="2f04b-113">Primary</span><span class="sxs-lookup"><span data-stu-id="2f04b-113">Primary</span></span>  <br/> |<span data-ttu-id="2f04b-114">このエンドポイントを識別する一意の番号です。</span><span class="sxs-lookup"><span data-stu-id="2f04b-114">Unique number identifying this endpoint.</span></span>  <br/> |
|<span data-ttu-id="2f04b-115">**名前**</span><span class="sxs-lookup"><span data-stu-id="2f04b-115">**Name**</span></span> <br/> |<span data-ttu-id="2f04b-116">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="2f04b-116">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="2f04b-117">一意</span><span class="sxs-lookup"><span data-stu-id="2f04b-117">Unique</span></span>  <br/> |<span data-ttu-id="2f04b-118">エンドポイント名。</span><span class="sxs-lookup"><span data-stu-id="2f04b-118">Endpoint name.</span></span>  <br/> |
|<span data-ttu-id="2f04b-119">**OS**</span><span class="sxs-lookup"><span data-stu-id="2f04b-119">**OS**</span></span> <br/> |<span data-ttu-id="2f04b-120">nvarchar(128</span><span class="sxs-lookup"><span data-stu-id="2f04b-120">nvarchar(128)</span></span>  <br/> | <br/> |<span data-ttu-id="2f04b-121">エンドポイントのオペレーティングシステム (OS)。</span><span class="sxs-lookup"><span data-stu-id="2f04b-121">Operating system (OS) of the endpoint.</span></span>  <br/> |
|<span data-ttu-id="2f04b-122">**CPUName**</span><span class="sxs-lookup"><span data-stu-id="2f04b-122">**CPUName**</span></span> <br/> |<span data-ttu-id="2f04b-123">nvarchar(128</span><span class="sxs-lookup"><span data-stu-id="2f04b-123">nvarchar(128)</span></span>  <br/> ||<span data-ttu-id="2f04b-124">エンドポイントの CPU 名。</span><span class="sxs-lookup"><span data-stu-id="2f04b-124">CPU name of the endpoint.</span></span>  <br/> |
|<span data-ttu-id="2f04b-125">**CPUNumberOfCores**</span><span class="sxs-lookup"><span data-stu-id="2f04b-125">**CPUNumberOfCores**</span></span> <br/> |<span data-ttu-id="2f04b-126">smallint</span><span class="sxs-lookup"><span data-stu-id="2f04b-126">smallint</span></span>  <br/> ||<span data-ttu-id="2f04b-127">エンドポイントの CPU コアの数。</span><span class="sxs-lookup"><span data-stu-id="2f04b-127">Number of CPU cores of the endpoint.</span></span>  <br/> |
|<span data-ttu-id="2f04b-128">**プロセッサーの速度**</span><span class="sxs-lookup"><span data-stu-id="2f04b-128">**CPUProcessorSpeed**</span></span> <br/> |<span data-ttu-id="2f04b-129">int</span><span class="sxs-lookup"><span data-stu-id="2f04b-129">int</span></span>  <br/> ||<span data-ttu-id="2f04b-130">エンドポイントの CPU プロセッサの速度。</span><span class="sxs-lookup"><span data-stu-id="2f04b-130">CPU processor speed of the endpoint.</span></span>  <br/> |
|<span data-ttu-id="2f04b-131">**VirtualizationFlag**</span><span class="sxs-lookup"><span data-stu-id="2f04b-131">**VirtualizationFlag**</span></span> <br/> |<span data-ttu-id="2f04b-132">tinyint</span><span class="sxs-lookup"><span data-stu-id="2f04b-132">tinyint</span></span>  <br/> || <span data-ttu-id="2f04b-133">システムが仮想環境で実行されているかどうかを示すビットフラグ。</span><span class="sxs-lookup"><span data-stu-id="2f04b-133">Bit flag that indicates if the system is running in a virtualized environment:</span></span> <br/>  <span data-ttu-id="2f04b-134">0x0000-なし</span><span class="sxs-lookup"><span data-stu-id="2f04b-134">0x0000 - None</span></span> <br/>  <span data-ttu-id="2f04b-135">0x0001-HyperV</span><span class="sxs-lookup"><span data-stu-id="2f04b-135">0x0001 - HyperV</span></span> <br/>  <span data-ttu-id="2f04b-136">0x0002-ヴイエムウェア</span><span class="sxs-lookup"><span data-stu-id="2f04b-136">0x0002 - VMWare</span></span> <br/>  <span data-ttu-id="2f04b-137">0x0004-仮想 PC</span><span class="sxs-lookup"><span data-stu-id="2f04b-137">0x0004 - Virtual PC</span></span> <br/>  <span data-ttu-id="2f04b-138">0x0008-Xen PC</span><span class="sxs-lookup"><span data-stu-id="2f04b-138">0x0008 - Xen PC</span></span> <br/> |
   

