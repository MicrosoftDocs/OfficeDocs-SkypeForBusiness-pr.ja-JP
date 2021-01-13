---
title: サーバー テーブル
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
ms.assetid: 9af89d08-d35a-48e8-b56d-6df292f973cc
description: サーバー テーブルは補助的なテーブルです。 個々のレコードが 1 つのサーバーを表します。
ms.openlocfilehash: 7f26ed9053c65acb8cfd2e586edbd77fdfa7472b
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49802707"
---
# <a name="server-table"></a><span data-ttu-id="62027-104">サーバー テーブル</span><span class="sxs-lookup"><span data-stu-id="62027-104">Server table</span></span>
 
<span data-ttu-id="62027-p102">サーバー テーブルは補助的なテーブルです。個々のレコードが 1 つのサーバーを表します。</span><span class="sxs-lookup"><span data-stu-id="62027-p102">The Server table is a supporting table. Each record represents one server.</span></span> 
  
|<span data-ttu-id="62027-107">**列**</span><span class="sxs-lookup"><span data-stu-id="62027-107">**Column**</span></span>|<span data-ttu-id="62027-108">**データ型**</span><span class="sxs-lookup"><span data-stu-id="62027-108">**Data Type**</span></span>|<span data-ttu-id="62027-109">**キー/インデックス**</span><span class="sxs-lookup"><span data-stu-id="62027-109">**Key/Index**</span></span>|<span data-ttu-id="62027-110">**詳細**</span><span class="sxs-lookup"><span data-stu-id="62027-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="62027-111">**ServerKey**</span><span class="sxs-lookup"><span data-stu-id="62027-111">**ServerKey**</span></span> <br/> |<span data-ttu-id="62027-112">int</span><span class="sxs-lookup"><span data-stu-id="62027-112">int</span></span>  <br/> |<span data-ttu-id="62027-113">Primary</span><span class="sxs-lookup"><span data-stu-id="62027-113">Primary</span></span>  <br/> |<span data-ttu-id="62027-114">サーバーを識別する一意の番号。</span><span class="sxs-lookup"><span data-stu-id="62027-114">Unique number identifying the server.</span></span>  <br/> |
|<span data-ttu-id="62027-115">**FQDNOrIP**</span><span class="sxs-lookup"><span data-stu-id="62027-115">**FQDNOrIP**</span></span> <br/> |<span data-ttu-id="62027-116">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="62027-116">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="62027-117">index</span><span class="sxs-lookup"><span data-stu-id="62027-117">index</span></span>  <br/> |<span data-ttu-id="62027-118">MAC アドレス文字列。</span><span class="sxs-lookup"><span data-stu-id="62027-118">MAC address string.</span></span>  <br/> |
|<span data-ttu-id="62027-119">**ServerType**</span><span class="sxs-lookup"><span data-stu-id="62027-119">**ServerType**</span></span> <br/> |<span data-ttu-id="62027-120">int</span><span class="sxs-lookup"><span data-stu-id="62027-120">int</span></span>  <br/> |<span data-ttu-id="62027-121">外部</span><span class="sxs-lookup"><span data-stu-id="62027-121">Foreign</span></span>  <br/> |<span data-ttu-id="62027-122">1: 仲介サーバー</span><span class="sxs-lookup"><span data-stu-id="62027-122">1: Mediation Server</span></span>  <br/> <span data-ttu-id="62027-123">2: 音声ビデオ会議サーバー16394: 音声ビデオ エッジ サービス 32769: ゲートウェイ</span><span class="sxs-lookup"><span data-stu-id="62027-123">2: A/V Conferencing Server16394: A/V Edge service32769: Gateway</span></span>  <br/> |
|<span data-ttu-id="62027-124">**PoolName**</span><span class="sxs-lookup"><span data-stu-id="62027-124">**PoolName**</span></span> <br/> |<span data-ttu-id="62027-125">nvarchar(512)</span><span class="sxs-lookup"><span data-stu-id="62027-125">nvarchar(512)</span></span>  <br/> ||<span data-ttu-id="62027-p103">サーバーが所属するプール。音声ビデオ会議サーバーにのみ適用されます。</span><span class="sxs-lookup"><span data-stu-id="62027-p103">Pool the server belongs to. Only applicable for the A/V Conferencing Server.</span></span>  <br/> |
|<span data-ttu-id="62027-128">**NextUpdateTS**</span><span class="sxs-lookup"><span data-stu-id="62027-128">**NextUpdateTS**</span></span> <br/> |<span data-ttu-id="62027-129">日付型</span><span class="sxs-lookup"><span data-stu-id="62027-129">datetime</span></span>  <br/> ||<span data-ttu-id="62027-130">内部使用のみ。</span><span class="sxs-lookup"><span data-stu-id="62027-130">For internal use only.</span></span>  <br/> |
   

