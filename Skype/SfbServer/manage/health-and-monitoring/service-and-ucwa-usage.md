---
title: ビジネス サーバーの Skype での移動サービスおよび UCWA の使用状況を監視します。
ms.reviewer: ''
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 8389b37a-ca3e-4047-8b51-85bc07da87e8
description: '概要: は、サーバーのビジネスのモビリティ サービス (Mcx)、Skype では、ユニファイド コミュニケーション Web API (UCWA) を管理します。'
ms.openlocfilehash: 79516ec6cf5371061a0287e70e6ed81f8b2a5395
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "32197500"
---
# <a name="monitor-mobility-service-and-ucwa-usage-in-skype-for-business-server"></a><span data-ttu-id="e8f18-103">ビジネス サーバーの Skype での移動サービスおよび UCWA の使用状況を監視します。</span><span class="sxs-lookup"><span data-stu-id="e8f18-103">Monitor Mobility Service and UCWA usage in Skype for Business Server</span></span>
 
<span data-ttu-id="e8f18-104">**の概要:** ビジネス サーバーの移動サービス (Mcx)、Skype では、ユニファイド コミュニケーション Web API (UCWA) を管理します。</span><span class="sxs-lookup"><span data-stu-id="e8f18-104">**Summary:** Manage the Mobility Service (Mcx) and the Unified Communications Web API (UCWA) in Skype for Business Server.</span></span>

> [!NOTE]
> <span data-ttu-id="e8f18-105">従来のモバイル クライアント用の MCX (移動サービス) サポートがビジネス サーバー 2019 の Skype で利用可能ではありません。</span><span class="sxs-lookup"><span data-stu-id="e8f18-105">MCX (Mobility Service) support for legacy mobile clients is no longer available in Skype for Business Server 2019.</span></span> <span data-ttu-id="e8f18-106">ビジネスのモバイル クライアントのすべての現在 Skype は、インスタント メッセージング (IM)、プレゼンス、および取引先担当者をサポートするために既にユニファイド コミュニケーション Web API (UCWA) を使用します。</span><span class="sxs-lookup"><span data-stu-id="e8f18-106">All current Skype for Business mobile clients already use Unified Communications Web API (UCWA) to support instant messaging (IM), presence, and contacts.</span></span> <span data-ttu-id="e8f18-107">MCX を使用する従来のクライアントを持つユーザーは、現在のクライアントにアップグレードする必要があります。</span><span class="sxs-lookup"><span data-stu-id="e8f18-107">Users with legacy clients using MCX will need to upgrade to a current client.</span></span>
  
<span data-ttu-id="e8f18-108">、継続的にビジネス サーバー移動サービス (Mcx) と、ユニファイド コミュニケーション Web API (UCWA) は、Skype で使用されるメモリ、CPU を監視する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e8f18-108">On an ongoing basis, you should monitor the CPU and memory that is used by the Skype for Business Server Mobility Service (Mcx) and the Unified Communications Web API (UCWA).</span></span> <span data-ttu-id="e8f18-109">使用状況を監視するには、次のように使用できます。</span><span class="sxs-lookup"><span data-stu-id="e8f18-109">To monitor usage, you can use the following:</span></span>
  
 <span data-ttu-id="e8f18-110">**Unified Communications Web API (UCWA):**</span><span class="sxs-lookup"><span data-stu-id="e8f18-110">**For Unified Communications Web API (UCWA):**</span></span>
  
- <span data-ttu-id="e8f18-111">インターネット インフォメーション サービス (IIS) マネージャーで**LyncUcwa**のワーカー プロセス。</span><span class="sxs-lookup"><span data-stu-id="e8f18-111">The **LyncUcwa** worker process in Internet Information Services (IIS) Manager.</span></span> <span data-ttu-id="e8f18-112">[**ワーカー プロセス**] ウィンドウで、[**CPU %**] および [**プライベート バイト (KB)**] (メモリ) の列を確認します。</span><span class="sxs-lookup"><span data-stu-id="e8f18-112">In the **Worker Processes** pane, look at the **CPU %** and **Private Bytes (KB)** (memory) columns.</span></span>
    
- <span data-ttu-id="e8f18-113">[**CPU**] および [**プロセッサ**] パフォーマンス カウンター。</span><span class="sxs-lookup"><span data-stu-id="e8f18-113">The **CPU** and **Processor** performance counters.</span></span>
    
<span data-ttu-id="e8f18-114">ほとんどの展開で、UCWA の CPU 使用率は平均で 15% を下回っている必要があります。</span><span class="sxs-lookup"><span data-stu-id="e8f18-114">For most deployments, UCWA CPU usage should be below 15 percent on average.</span></span> <span data-ttu-id="e8f18-115">メモリ使用量は、 [Skype ビジネス サーバー用にサーバーのメモリ容量制限のためのモニター](server-memory-capacity-limits.md)で説明されている制限内に収まるようにします。</span><span class="sxs-lookup"><span data-stu-id="e8f18-115">Memory usage should fall within the limits described in [Monitor for server memory capacity limits in Skype for Business Server](server-memory-capacity-limits.md).</span></span>
  
<span data-ttu-id="e8f18-116">CPU とメモリの使用状況カウンターに加えて、以下のパフォーマンス カウンターを使用すると、サーバーが要求で過負荷になっていないかどうかを確認するのに役立つ場合があります。</span><span class="sxs-lookup"><span data-stu-id="e8f18-116">In addition to CPU and memory usage counters, you can use the following performance counters to help determine when a server is overloaded with requests:</span></span>
  
- <span data-ttu-id="e8f18-117">**LS:WEB の調整と Authentication\WEB の合計の要求の処理に**、保留中のサーバー上の web 要求の数を示します。</span><span class="sxs-lookup"><span data-stu-id="e8f18-117">**LS:WEB - Throttling and Authentication\WEB - Total Requests in Processing**, which indicates the number of pending web requests on the server.</span></span> <span data-ttu-id="e8f18-118">このカウンターでは、10,000 に達すると、後続の要求は失敗します、エラー メッセージが「503 - サービスを使用できません」</span><span class="sxs-lookup"><span data-stu-id="e8f18-118">When this counter reaches 10,000, subsequent requests will fail, with the error message, "503 - Service Unavailable."</span></span>
    
- <span data-ttu-id="e8f18-119">**ASP.NET\Requests Queued** (常にゼロである必要があります)。</span><span class="sxs-lookup"><span data-stu-id="e8f18-119">**ASP.NET\Requests Queued** (should always be zero).</span></span>
    
> [!NOTE]
> <span data-ttu-id="e8f18-120">これらの値に達するか、これらの値を超えた場合、Web サービスをホストしているコンピューターの CPU、コア数、およびメモリの適切な規模設定の容量計画を再検討して、再計算する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e8f18-120">If you meet or exceed these values, you should revisit and re-compute your capacity planning for the correct sizing of CPU, number of cores and memory for the computers hosting the web services.</span></span> 
  
 <span data-ttu-id="e8f18-121">**Mobility Service (Mcx):**</span><span class="sxs-lookup"><span data-stu-id="e8f18-121">**For the Mobility Service (Mcx):**</span></span>
  
- <span data-ttu-id="e8f18-122">**CSIntMcxAppPool** 、 **CSExtMcxAppPool**ワーカー プロセスのインターネット インフォメーション サービス (IIS) マネージャー。</span><span class="sxs-lookup"><span data-stu-id="e8f18-122">The **CSIntMcxAppPool** and **CSExtMcxAppPool** worker processes in Internet Information Services (IIS) Manager.</span></span> <span data-ttu-id="e8f18-123">[**ワーカー プロセス**] ウィンドウで、[**CPU %**] および [**プライベート バイト (KB)**] (メモリ) の列を確認します。</span><span class="sxs-lookup"><span data-stu-id="e8f18-123">In the **Worker Processes** pane, look at the **CPU %** and **Private Bytes (KB)** (memory) columns.</span></span>
    
- <span data-ttu-id="e8f18-124">[**CPU**] および [**プロセッサ**] パフォーマンス カウンター。</span><span class="sxs-lookup"><span data-stu-id="e8f18-124">The **CPU** and **Processor** performance counters.</span></span>
    
<span data-ttu-id="e8f18-125">ほとんどの展開で、Mobility Service の CPU 使用率は平均で 15% を下回っている必要があります。</span><span class="sxs-lookup"><span data-stu-id="e8f18-125">For most deployments, Mobility Service CPU usage should be below 15 percent, on average.</span></span> <span data-ttu-id="e8f18-126">メモリ使用量は、 [Skype ビジネス サーバー用にサーバーのメモリ容量制限のためのモニター](server-memory-capacity-limits.md)で説明されている制限内に収まるようにします。</span><span class="sxs-lookup"><span data-stu-id="e8f18-126">Memory usage should fall within the limits described in [Monitor for server memory capacity limits in Skype for Business Server](server-memory-capacity-limits.md).</span></span>
  
<span data-ttu-id="e8f18-127">CPU とメモリの使用状況カウンターに加えて、以下の ASP.NET パフォーマンス カウンターを使用すると、サーバーが要求で過負荷になっていないかどうかを確認するのに役立つ場合があります。</span><span class="sxs-lookup"><span data-stu-id="e8f18-127">In addition to CPU and memory usage counters, you can use the following ASP.NET performance counters to help determine when a server is overloaded with requests:</span></span>
  
- <span data-ttu-id="e8f18-128">**ASP.NET v2.0.50727\Requests 現在**、保留中のサーバー上の web 要求の数を示します。</span><span class="sxs-lookup"><span data-stu-id="e8f18-128">**ASP.NET v2.0.50727\Requests Current**, which indicates the number of pending web requests on the server.</span></span> <span data-ttu-id="e8f18-129">「503 - サービスを使用できません」のエラー メッセージとそれ以降の要求は失敗しますこのカウンターでは、5,000 に達すると、</span><span class="sxs-lookup"><span data-stu-id="e8f18-129">When this counter reaches 5,000, subsequent requests will fail with the error message, "503 - Service Unavailable."</span></span>
    
- <span data-ttu-id="e8f18-130">**ASP.NET\Requests Queued** (常にゼロである必要があります)。</span><span class="sxs-lookup"><span data-stu-id="e8f18-130">**ASP.NET\Requests Queued** (should always be zero).</span></span>
    
> [!NOTE]
> <span data-ttu-id="e8f18-131">これらの値に達するか、これらの値を超えた場合、Web サービスをホストしているコンピューターの CPU、コア数、およびメモリの適切な規模設定の容量計画を再検討して、再計算する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e8f18-131">If you meet or exceed these values, you should revisit and recompute your capacity planning for the correct sizing of CPU, number of cores, and memory for the computers hosting the web services.</span></span> 

> [!NOTE]
> <span data-ttu-id="e8f18-132">従来のモバイル クライアント用の MCX (移動サービス) サポートがビジネス サーバー 2019 の Skype で利用可能ではありません。</span><span class="sxs-lookup"><span data-stu-id="e8f18-132">MCX (Mobility Service) support for legacy mobile clients is no longer available in Skype for Business Server 2019.</span></span> <span data-ttu-id="e8f18-133">ビジネスのモバイル クライアントのすべての現在 Skype は、インスタント メッセージング (IM)、プレゼンス、および取引先担当者をサポートするために既にユニファイド コミュニケーション Web API (UCWA) を使用します。</span><span class="sxs-lookup"><span data-stu-id="e8f18-133">All current Skype for Business mobile clients already use Unified Communications Web API (UCWA) to support instant messaging (IM), presence, and contacts.</span></span> <span data-ttu-id="e8f18-134">MCX を使用する従来のクライアントを持つユーザーは、現在のクライアントにアップグレードする必要があります。</span><span class="sxs-lookup"><span data-stu-id="e8f18-134">Users with legacy clients using MCX will need to upgrade to a current client.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="e8f18-135">関連項目</span><span class="sxs-lookup"><span data-stu-id="e8f18-135">See also</span></span>

[<span data-ttu-id="e8f18-136">Skype ビジネス サーバー用にサーバーのメモリ容量制限のためのモニター</span><span class="sxs-lookup"><span data-stu-id="e8f18-136">Monitor for server memory capacity limits in Skype for Business Server</span></span>](server-memory-capacity-limits.md)
