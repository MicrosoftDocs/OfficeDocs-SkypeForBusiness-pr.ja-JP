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
localization_priority: Normal
ms.assetid: 500f330d-4d7d-4e88-b1cc-fef9a9de6b5c
description: エンドポイントテーブルは、データベースに記録されているセッションに参加しているエンドポイントに関する情報を格納するサポートテーブルです。 テーブル内の各レコードは、1つのエンドポイントを表します。
ms.openlocfilehash: 7d582d382784d04d4495de972aa20673862284f4
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2019
ms.locfileid: "34294993"
---
# <a name="endpoint-table"></a><span data-ttu-id="1d040-104">Endpoint テーブル</span><span class="sxs-lookup"><span data-stu-id="1d040-104">Endpoint table</span></span>
 
<span data-ttu-id="1d040-105">エンドポイントテーブルは、データベースに記録されているセッションに参加しているエンドポイントに関する情報を格納するサポートテーブルです。</span><span class="sxs-lookup"><span data-stu-id="1d040-105">The Endpoint table is a supporting table that stores information about the endpoints that have participated in sessions recorded in the database.</span></span> <span data-ttu-id="1d040-106">テーブル内の各レコードは、1つのエンドポイントを表します。</span><span class="sxs-lookup"><span data-stu-id="1d040-106">Each record in the table represents one endpoint.</span></span>
  
|<span data-ttu-id="1d040-107">**列**</span><span class="sxs-lookup"><span data-stu-id="1d040-107">**Column**</span></span>|<span data-ttu-id="1d040-108">**データ型**</span><span class="sxs-lookup"><span data-stu-id="1d040-108">**Data Type**</span></span>|<span data-ttu-id="1d040-109">**キー/インデックス**</span><span class="sxs-lookup"><span data-stu-id="1d040-109">**Key/Index**</span></span>|<span data-ttu-id="1d040-110">**詳細**</span><span class="sxs-lookup"><span data-stu-id="1d040-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="1d040-111">**EndpointKey**</span><span class="sxs-lookup"><span data-stu-id="1d040-111">**EndpointKey**</span></span> <br/> |<span data-ttu-id="1d040-112">int</span><span class="sxs-lookup"><span data-stu-id="1d040-112">int</span></span>  <br/> |<span data-ttu-id="1d040-113">Primary</span><span class="sxs-lookup"><span data-stu-id="1d040-113">Primary</span></span>  <br/> |<span data-ttu-id="1d040-114">このエンドポイントを識別する一意の番号です。</span><span class="sxs-lookup"><span data-stu-id="1d040-114">Unique number identifying this endpoint.</span></span>  <br/> |
|<span data-ttu-id="1d040-115">**名前**</span><span class="sxs-lookup"><span data-stu-id="1d040-115">**Name**</span></span> <br/> |<span data-ttu-id="1d040-116">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="1d040-116">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="1d040-117">一意</span><span class="sxs-lookup"><span data-stu-id="1d040-117">Unique</span></span>  <br/> |<span data-ttu-id="1d040-118">エンドポイント名。</span><span class="sxs-lookup"><span data-stu-id="1d040-118">Endpoint name.</span></span>  <br/> |
|<span data-ttu-id="1d040-119">**OS**</span><span class="sxs-lookup"><span data-stu-id="1d040-119">**OS**</span></span> <br/> |<span data-ttu-id="1d040-120">nvarchar(128</span><span class="sxs-lookup"><span data-stu-id="1d040-120">nvarchar(128)</span></span>  <br/> | <br/> |<span data-ttu-id="1d040-121">エンドポイントのオペレーティングシステム (OS)。</span><span class="sxs-lookup"><span data-stu-id="1d040-121">Operating system (OS) of the endpoint.</span></span>  <br/> |
|<span data-ttu-id="1d040-122">**CPUName**</span><span class="sxs-lookup"><span data-stu-id="1d040-122">**CPUName**</span></span> <br/> |<span data-ttu-id="1d040-123">nvarchar(128</span><span class="sxs-lookup"><span data-stu-id="1d040-123">nvarchar(128)</span></span>  <br/> ||<span data-ttu-id="1d040-124">エンドポイントの CPU 名。</span><span class="sxs-lookup"><span data-stu-id="1d040-124">CPU name of the endpoint.</span></span>  <br/> |
|<span data-ttu-id="1d040-125">**CPUNumberOfCores**</span><span class="sxs-lookup"><span data-stu-id="1d040-125">**CPUNumberOfCores**</span></span> <br/> |<span data-ttu-id="1d040-126">smallint</span><span class="sxs-lookup"><span data-stu-id="1d040-126">smallint</span></span>  <br/> ||<span data-ttu-id="1d040-127">エンドポイントの CPU コアの数。</span><span class="sxs-lookup"><span data-stu-id="1d040-127">Number of CPU cores of the endpoint.</span></span>  <br/> |
|<span data-ttu-id="1d040-128">**プロセッサーの速度**</span><span class="sxs-lookup"><span data-stu-id="1d040-128">**CPUProcessorSpeed**</span></span> <br/> |<span data-ttu-id="1d040-129">int</span><span class="sxs-lookup"><span data-stu-id="1d040-129">int</span></span>  <br/> ||<span data-ttu-id="1d040-130">エンドポイントの CPU プロセッサの速度。</span><span class="sxs-lookup"><span data-stu-id="1d040-130">CPU processor speed of the endpoint.</span></span>  <br/> |
|<span data-ttu-id="1d040-131">**VirtualizationFlag**</span><span class="sxs-lookup"><span data-stu-id="1d040-131">**VirtualizationFlag**</span></span> <br/> |<span data-ttu-id="1d040-132">tinyint</span><span class="sxs-lookup"><span data-stu-id="1d040-132">tinyint</span></span>  <br/> || <span data-ttu-id="1d040-133">システムが仮想環境で実行されているかどうかを示すビットフラグ。</span><span class="sxs-lookup"><span data-stu-id="1d040-133">Bit flag that indicates if the system is running in a virtualized environment:</span></span> <br/>  <span data-ttu-id="1d040-134">0x0000-なし</span><span class="sxs-lookup"><span data-stu-id="1d040-134">0x0000 - None</span></span> <br/>  <span data-ttu-id="1d040-135">0x0001-HyperV</span><span class="sxs-lookup"><span data-stu-id="1d040-135">0x0001 - HyperV</span></span> <br/>  <span data-ttu-id="1d040-136">0x0002-ヴイエムウェア</span><span class="sxs-lookup"><span data-stu-id="1d040-136">0x0002 - VMWare</span></span> <br/>  <span data-ttu-id="1d040-137">0x0004-仮想 PC</span><span class="sxs-lookup"><span data-stu-id="1d040-137">0x0004 - Virtual PC</span></span> <br/>  <span data-ttu-id="1d040-138">0x0008-Xen PC</span><span class="sxs-lookup"><span data-stu-id="1d040-138">0x0008 - Xen PC</span></span> <br/> |
   

