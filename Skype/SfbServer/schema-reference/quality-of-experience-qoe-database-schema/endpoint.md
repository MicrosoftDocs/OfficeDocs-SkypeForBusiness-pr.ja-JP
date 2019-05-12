---
title: Endpoint テーブル
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 500f330d-4d7d-4e88-b1cc-fef9a9de6b5c
description: エンドポイントはデータベースに記録されているセッションに参加したエンドポイントに関する情報を格納するサポート テーブルです。 テーブル内の各レコードは、1 つのエンドポイントを表します。
ms.openlocfilehash: 4917b0817d8fcedbc3a20b2c41d3ed62ce468c5c
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "33920111"
---
# <a name="endpoint-table"></a><span data-ttu-id="8fdb2-104">Endpoint テーブル</span><span class="sxs-lookup"><span data-stu-id="8fdb2-104">Endpoint table</span></span>
 
<span data-ttu-id="8fdb2-105">エンドポイントはデータベースに記録されているセッションに参加したエンドポイントに関する情報を格納するサポート テーブルです。</span><span class="sxs-lookup"><span data-stu-id="8fdb2-105">The Endpoint table is a supporting table that stores information about the endpoints that have participated in sessions recorded in the database.</span></span> <span data-ttu-id="8fdb2-106">テーブル内の各レコードは、1 つのエンドポイントを表します。</span><span class="sxs-lookup"><span data-stu-id="8fdb2-106">Each record in the table represents one endpoint.</span></span>
  
|<span data-ttu-id="8fdb2-107">**列**</span><span class="sxs-lookup"><span data-stu-id="8fdb2-107">**Column**</span></span>|<span data-ttu-id="8fdb2-108">**データ型**</span><span class="sxs-lookup"><span data-stu-id="8fdb2-108">**Data Type**</span></span>|<span data-ttu-id="8fdb2-109">**キー/インデックス**</span><span class="sxs-lookup"><span data-stu-id="8fdb2-109">**Key/Index**</span></span>|<span data-ttu-id="8fdb2-110">**詳細**</span><span class="sxs-lookup"><span data-stu-id="8fdb2-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="8fdb2-111">**EndpointKey**</span><span class="sxs-lookup"><span data-stu-id="8fdb2-111">**EndpointKey**</span></span> <br/> |<span data-ttu-id="8fdb2-112">int</span><span class="sxs-lookup"><span data-stu-id="8fdb2-112">int</span></span>  <br/> |<span data-ttu-id="8fdb2-113">Primary</span><span class="sxs-lookup"><span data-stu-id="8fdb2-113">Primary</span></span>  <br/> |<span data-ttu-id="8fdb2-114">このエンドポイントを識別する一意の番号です。</span><span class="sxs-lookup"><span data-stu-id="8fdb2-114">Unique number identifying this endpoint.</span></span>  <br/> |
|<span data-ttu-id="8fdb2-115">**名前**</span><span class="sxs-lookup"><span data-stu-id="8fdb2-115">**Name**</span></span> <br/> |<span data-ttu-id="8fdb2-116">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="8fdb2-116">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="8fdb2-117">一意</span><span class="sxs-lookup"><span data-stu-id="8fdb2-117">Unique</span></span>  <br/> |<span data-ttu-id="8fdb2-118">エンドポイントの名前です。</span><span class="sxs-lookup"><span data-stu-id="8fdb2-118">Endpoint name.</span></span>  <br/> |
|<span data-ttu-id="8fdb2-119">**OS**</span><span class="sxs-lookup"><span data-stu-id="8fdb2-119">**OS**</span></span> <br/> |<span data-ttu-id="8fdb2-120">nvarchar (128)</span><span class="sxs-lookup"><span data-stu-id="8fdb2-120">nvarchar(128)</span></span>  <br/> | <br/> |<span data-ttu-id="8fdb2-121">エンドポイントのオペレーティング システム (OS)。</span><span class="sxs-lookup"><span data-stu-id="8fdb2-121">Operating system (OS) of the endpoint.</span></span>  <br/> |
|<span data-ttu-id="8fdb2-122">**CPUName**</span><span class="sxs-lookup"><span data-stu-id="8fdb2-122">**CPUName**</span></span> <br/> |<span data-ttu-id="8fdb2-123">nvarchar (128)</span><span class="sxs-lookup"><span data-stu-id="8fdb2-123">nvarchar(128)</span></span>  <br/> ||<span data-ttu-id="8fdb2-124">エンドポイントの CPU の名前です。</span><span class="sxs-lookup"><span data-stu-id="8fdb2-124">CPU name of the endpoint.</span></span>  <br/> |
|<span data-ttu-id="8fdb2-125">**CPUNumberOfCores**</span><span class="sxs-lookup"><span data-stu-id="8fdb2-125">**CPUNumberOfCores**</span></span> <br/> |<span data-ttu-id="8fdb2-126">smallint</span><span class="sxs-lookup"><span data-stu-id="8fdb2-126">smallint</span></span>  <br/> ||<span data-ttu-id="8fdb2-127">エンドポイントの CPU コアの数です。</span><span class="sxs-lookup"><span data-stu-id="8fdb2-127">Number of CPU cores of the endpoint.</span></span>  <br/> |
|<span data-ttu-id="8fdb2-128">**CPUProcessorSpeed**</span><span class="sxs-lookup"><span data-stu-id="8fdb2-128">**CPUProcessorSpeed**</span></span> <br/> |<span data-ttu-id="8fdb2-129">int</span><span class="sxs-lookup"><span data-stu-id="8fdb2-129">int</span></span>  <br/> ||<span data-ttu-id="8fdb2-130">エンドポイントの CPU のプロセッサ速度です。</span><span class="sxs-lookup"><span data-stu-id="8fdb2-130">CPU processor speed of the endpoint.</span></span>  <br/> |
|<span data-ttu-id="8fdb2-131">**VirtualizationFlag**</span><span class="sxs-lookup"><span data-stu-id="8fdb2-131">**VirtualizationFlag**</span></span> <br/> |<span data-ttu-id="8fdb2-132">tinyint</span><span class="sxs-lookup"><span data-stu-id="8fdb2-132">tinyint</span></span>  <br/> || <span data-ttu-id="8fdb2-133">システムが仮想化環境で実行されているかどうかであることを示すビット フラグ。</span><span class="sxs-lookup"><span data-stu-id="8fdb2-133">Bit flag that indicates if the system is running in a virtualized environment:</span></span> <br/>  <span data-ttu-id="8fdb2-134">0x0000 - なし</span><span class="sxs-lookup"><span data-stu-id="8fdb2-134">0x0000 - None</span></span> <br/>  <span data-ttu-id="8fdb2-135">0x0001 - HyperV</span><span class="sxs-lookup"><span data-stu-id="8fdb2-135">0x0001 - HyperV</span></span> <br/>  <span data-ttu-id="8fdb2-136">0x0002 - VMWare</span><span class="sxs-lookup"><span data-stu-id="8fdb2-136">0x0002 - VMWare</span></span> <br/>  <span data-ttu-id="8fdb2-137">0x0004 - 仮想 PC</span><span class="sxs-lookup"><span data-stu-id="8fdb2-137">0x0004 - Virtual PC</span></span> <br/>  <span data-ttu-id="8fdb2-138">0x0008 - Xen PC</span><span class="sxs-lookup"><span data-stu-id="8fdb2-138">0x0008 - Xen PC</span></span> <br/> |
   

