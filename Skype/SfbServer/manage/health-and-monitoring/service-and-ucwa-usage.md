---
title: Skype for Business Server での Mobility Service と UCWA の使用状況の監視
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 8389b37a-ca3e-4047-8b51-85bc07da87e8
description: '概要: Skype for Business Server で Mobility Service (Mcx) と Unified Communications Web API (UCWA) を管理します。'
ms.openlocfilehash: 76bcf8727d3abbb417595f033ce9a59ec00a39ff
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49814247"
---
# <a name="monitor-mobility-service-and-ucwa-usage-in-skype-for-business-server"></a><span data-ttu-id="7f146-103">Skype for Business Server での Mobility Service と UCWA の使用状況の監視</span><span class="sxs-lookup"><span data-stu-id="7f146-103">Monitor Mobility Service and UCWA usage in Skype for Business Server</span></span>
 
<span data-ttu-id="7f146-104">**概要:** Skype for Business Server で Mobility Service (Mcx) と Unified Communications Web API (UCWA) を管理します。</span><span class="sxs-lookup"><span data-stu-id="7f146-104">**Summary:** Manage the Mobility Service (Mcx) and the Unified Communications Web API (UCWA) in Skype for Business Server.</span></span>

> [!NOTE]
> <span data-ttu-id="7f146-105">従来のモバイル クライアントの MCX (モビリティ サービス) サポートは、Skype for Business Server 2019 では利用できなくなりました。</span><span class="sxs-lookup"><span data-stu-id="7f146-105">MCX (Mobility Service) support for legacy mobile clients is no longer available in Skype for Business Server 2019.</span></span> <span data-ttu-id="7f146-106">現在のすべての Skype for Business モバイル クライアントはUnified Communications Web API (UCWA) を使用して、インスタント メッセージング (IM)、プレゼンス、および連絡先をサポートしています。</span><span class="sxs-lookup"><span data-stu-id="7f146-106">All current Skype for Business mobile clients already use Unified Communications Web API (UCWA) to support instant messaging (IM), presence, and contacts.</span></span> <span data-ttu-id="7f146-107">MCX を使用している従来のクライアントを持っているユーザーは、現在のクライアントにアップグレードする必要があります。</span><span class="sxs-lookup"><span data-stu-id="7f146-107">Users with legacy clients using MCX will need to upgrade to a current client.</span></span>
  
<span data-ttu-id="7f146-108">Skype for Business Server Mobility Service (Mcx) および Unified Communications Web API (UCWA) で使用される CPU とメモリを継続的に監視する必要があります。</span><span class="sxs-lookup"><span data-stu-id="7f146-108">On an ongoing basis, you should monitor the CPU and memory that is used by the Skype for Business Server Mobility Service (Mcx) and the Unified Communications Web API (UCWA).</span></span> <span data-ttu-id="7f146-109">使用状況を監視するには、以下を使用できます。</span><span class="sxs-lookup"><span data-stu-id="7f146-109">To monitor usage, you can use the following:</span></span>
  
 <span data-ttu-id="7f146-110">**Unified Communications Web API (UCWA) の場合:**</span><span class="sxs-lookup"><span data-stu-id="7f146-110">**For Unified Communications Web API (UCWA):**</span></span>
  
- <span data-ttu-id="7f146-111">インターネット インフォメーション サービス (IIS) マネージャーの **LyncUcwa** ワーカー プロセス。</span><span class="sxs-lookup"><span data-stu-id="7f146-111">The **LyncUcwa** worker process in Internet Information Services (IIS) Manager.</span></span> <span data-ttu-id="7f146-112">[**ワーカー プロセス**] ウィンドウで、[**CPU %**] および [**プライベート バイト (KB)**] (メモリ) の列を確認します。</span><span class="sxs-lookup"><span data-stu-id="7f146-112">In the **Worker Processes** pane, look at the **CPU %** and **Private Bytes (KB)** (memory) columns.</span></span>
    
- <span data-ttu-id="7f146-113">[**CPU**] および [**プロセッサ**] パフォーマンス カウンター</span><span class="sxs-lookup"><span data-stu-id="7f146-113">The **CPU** and **Processor** performance counters.</span></span>
    
<span data-ttu-id="7f146-114">ほとんどの展開では、UCWA CPU 使用率は平均で 15% を下回る必要があります。</span><span class="sxs-lookup"><span data-stu-id="7f146-114">For most deployments, UCWA CPU usage should be below 15 percent on average.</span></span> <span data-ttu-id="7f146-115">メモリ使用量は、Skype for Business Server のサーバー メモリ容量制限の監視で説明 [されている制限の範囲内に入る必要があります](server-memory-capacity-limits.md)。</span><span class="sxs-lookup"><span data-stu-id="7f146-115">Memory usage should fall within the limits described in [Monitor for server memory capacity limits in Skype for Business Server](server-memory-capacity-limits.md).</span></span>
  
<span data-ttu-id="7f146-116">CPU およびメモリ使用量カウンターに加えて、次のパフォーマンス カウンターを使用して、サーバーが要求で過負荷状態にあるかどうかを判断できます。</span><span class="sxs-lookup"><span data-stu-id="7f146-116">In addition to CPU and memory usage counters, you can use the following performance counters to help determine when a server is overloaded with requests:</span></span>
  
- <span data-ttu-id="7f146-117">**LS:WEB - 調整と認証\WEB - サーバー** 上の保留中の Web 要求の数を示す、処理中の要求の総数。</span><span class="sxs-lookup"><span data-stu-id="7f146-117">**LS:WEB - Throttling and Authentication\WEB - Total Requests in Processing**, which indicates the number of pending web requests on the server.</span></span> <span data-ttu-id="7f146-118">このカウンターが 10,000 に達すると、後続の要求は失敗し、"503 - Service Unavailable" というエラー メッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="7f146-118">When this counter reaches 10,000, subsequent requests will fail, with the error message, "503 - Service Unavailable."</span></span>
    
- <span data-ttu-id="7f146-119">**ASP.NET\Requests Queued** (常にゼロである必要があります)。</span><span class="sxs-lookup"><span data-stu-id="7f146-119">**ASP.NET\Requests Queued** (should always be zero).</span></span>
    
> [!NOTE]
> <span data-ttu-id="7f146-120">これらの値を満たすか、この値を超える場合は、Web サービスをホストするコンピューターの CPU、コア数、およびメモリの適切なサイズ変更に関する容量計画を再検討し、再計算する必要があります。</span><span class="sxs-lookup"><span data-stu-id="7f146-120">If you meet or exceed these values, you should revisit and re-compute your capacity planning for the correct sizing of CPU, number of cores and memory for the computers hosting the web services.</span></span> 
  
 <span data-ttu-id="7f146-121">**Mobility Service (Mcx) の場合:**</span><span class="sxs-lookup"><span data-stu-id="7f146-121">**For the Mobility Service (Mcx):**</span></span>
  
- <span data-ttu-id="7f146-122">インターネット インフォメーション サービス (IIS) マネージャーの **CSIntMcxAppPool** ワーカー プロセスと **CSExtMcxAppPool** ワーカー プロセス。</span><span class="sxs-lookup"><span data-stu-id="7f146-122">The **CSIntMcxAppPool** and **CSExtMcxAppPool** worker processes in Internet Information Services (IIS) Manager.</span></span> <span data-ttu-id="7f146-123">[**ワーカー プロセス**] ウィンドウで、[**CPU %**] および [**プライベート バイト (KB)**] (メモリ) の列を確認します。</span><span class="sxs-lookup"><span data-stu-id="7f146-123">In the **Worker Processes** pane, look at the **CPU %** and **Private Bytes (KB)** (memory) columns.</span></span>
    
- <span data-ttu-id="7f146-124">[**CPU**] および [**プロセッサ**] パフォーマンス カウンター</span><span class="sxs-lookup"><span data-stu-id="7f146-124">The **CPU** and **Processor** performance counters.</span></span>
    
<span data-ttu-id="7f146-125">ほとんどの展開では、Mobility Service の CPU 使用率は平均で 15% を下回る必要があります。</span><span class="sxs-lookup"><span data-stu-id="7f146-125">For most deployments, Mobility Service CPU usage should be below 15 percent, on average.</span></span> <span data-ttu-id="7f146-126">メモリ使用量は、Skype for Business Server のサーバー メモリ容量制限の監視で説明 [されている制限の範囲内に入る必要があります](server-memory-capacity-limits.md)。</span><span class="sxs-lookup"><span data-stu-id="7f146-126">Memory usage should fall within the limits described in [Monitor for server memory capacity limits in Skype for Business Server](server-memory-capacity-limits.md).</span></span>
  
<span data-ttu-id="7f146-127">CPU とメモリの使用状況カウンターに加えて、以下の ASP.NET パフォーマンス カウンターを使用すると、サーバーが要求で過負荷になっていないかどうかを確認するのに役立つ場合があります。</span><span class="sxs-lookup"><span data-stu-id="7f146-127">In addition to CPU and memory usage counters, you can use the following ASP.NET performance counters to help determine when a server is overloaded with requests:</span></span>
  
- <span data-ttu-id="7f146-128">**ASP.NET v2.0.50727\Requests Current**。サーバー上の保留中の Web 要求の数を示します。</span><span class="sxs-lookup"><span data-stu-id="7f146-128">**ASP.NET v2.0.50727\Requests Current**, which indicates the number of pending web requests on the server.</span></span> <span data-ttu-id="7f146-129">このカウンターが 5,000 に達すると、後続の要求は失敗し、"503 - サービスを利用できません" というエラー メッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="7f146-129">When this counter reaches 5,000, subsequent requests will fail with the error message, "503 - Service Unavailable."</span></span>
    
- <span data-ttu-id="7f146-130">**ASP.NET\Requests Queued** (常にゼロである必要があります)。</span><span class="sxs-lookup"><span data-stu-id="7f146-130">**ASP.NET\Requests Queued** (should always be zero).</span></span>
    
> [!NOTE]
> <span data-ttu-id="7f146-131">これらの値を満たすか、この値を超える場合は、Web サービスをホストするコンピューターの CPU、コア数、メモリの適切なサイズ変更について、容量計画を再検討して再コンパイルする必要があります。</span><span class="sxs-lookup"><span data-stu-id="7f146-131">If you meet or exceed these values, you should revisit and recompute your capacity planning for the correct sizing of CPU, number of cores, and memory for the computers hosting the web services.</span></span> 

> [!NOTE]
> <span data-ttu-id="7f146-132">従来のモバイル クライアントの MCX (モビリティ サービス) サポートは、Skype for Business Server 2019 では利用できなくなりました。</span><span class="sxs-lookup"><span data-stu-id="7f146-132">MCX (Mobility Service) support for legacy mobile clients is no longer available in Skype for Business Server 2019.</span></span> <span data-ttu-id="7f146-133">現在のすべての Skype for Business モバイル クライアントはUnified Communications Web API (UCWA) を使用して、インスタント メッセージング (IM)、プレゼンス、および連絡先をサポートしています。</span><span class="sxs-lookup"><span data-stu-id="7f146-133">All current Skype for Business mobile clients already use Unified Communications Web API (UCWA) to support instant messaging (IM), presence, and contacts.</span></span> <span data-ttu-id="7f146-134">MCX を使用している従来のクライアントを持っているユーザーは、現在のクライアントにアップグレードする必要があります。</span><span class="sxs-lookup"><span data-stu-id="7f146-134">Users with legacy clients using MCX will need to upgrade to a current client.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="7f146-135">関連項目</span><span class="sxs-lookup"><span data-stu-id="7f146-135">See also</span></span>

[<span data-ttu-id="7f146-136">Skype for Business Server でサーバーのメモリ容量制限を監視する</span><span class="sxs-lookup"><span data-stu-id="7f146-136">Monitor for server memory capacity limits in Skype for Business Server</span></span>](server-memory-capacity-limits.md)
