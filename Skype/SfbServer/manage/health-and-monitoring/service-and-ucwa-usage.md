---
title: Skype for Business Server 2015 でのモビリティ サービスおよび UCWA の使用状況の監視
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 8389b37a-ca3e-4047-8b51-85bc07da87e8
description: '概要: は移動サービス (Mcx) とユニファイド コミュニケーション Web API (UCWA) をビジネス サーバー 2015 の Skype で管理します。'
ms.openlocfilehash: e71d18fe90eb9a7f2fd7b6563e6d6930f2473e74
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/28/2018
---
# <a name="monitor-mobility-service-and-ucwa-usage-in-skype-for-business-server-2015"></a><span data-ttu-id="eb39d-103">Skype for Business Server 2015 でのモビリティ サービスおよび UCWA の使用状況の監視</span><span class="sxs-lookup"><span data-stu-id="eb39d-103">Monitor Mobility Service and UCWA usage in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="eb39d-104">**の概要:**ビジネス サーバー 2015 の Skype のモビリティ サービス (Mcx) とユニファイド コミュニケーション Web API (UCWA) を管理します。</span><span class="sxs-lookup"><span data-stu-id="eb39d-104">**Summary:** Manage the Mobility Service (Mcx) and the Unified Communications Web API (UCWA) in Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="eb39d-105">、継続的にビジネス サーバー移動サービス (Mcx) と、ユニファイド コミュニケーション Web API (UCWA) は、Skype で使用されるメモリ、CPU を監視する必要があります。</span><span class="sxs-lookup"><span data-stu-id="eb39d-105">On an ongoing basis, you should monitor the CPU and memory that is used by the Skype for Business Server Mobility Service (Mcx) and the Unified Communications Web API (UCWA).</span></span> <span data-ttu-id="eb39d-106">使用状況を監視するには、次のように使用できます。</span><span class="sxs-lookup"><span data-stu-id="eb39d-106">To monitor usage, you can use the following:</span></span>
  
 <span data-ttu-id="eb39d-107">**Unified Communications Web API (UCWA):**</span><span class="sxs-lookup"><span data-stu-id="eb39d-107">**For Unified Communications Web API (UCWA):**</span></span>
  
- <span data-ttu-id="eb39d-108">インターネット インフォメーション サービス (IIS) マネージャーで**LyncUcwa**のワーカー プロセス。</span><span class="sxs-lookup"><span data-stu-id="eb39d-108">The **LyncUcwa** worker process in Internet Information Services (IIS) Manager.</span></span> <span data-ttu-id="eb39d-109">[**ワーカー プロセス**] ウィンドウで、[**CPU %**] および [**プライベート バイト (KB)**] (メモリ) の列を確認します。</span><span class="sxs-lookup"><span data-stu-id="eb39d-109">In the **Worker Processes** pane, look at the **CPU %** and **Private Bytes (KB)** (memory) columns.</span></span>
    
- <span data-ttu-id="eb39d-110">[**CPU**] および [**プロセッサ**] パフォーマンス カウンター。</span><span class="sxs-lookup"><span data-stu-id="eb39d-110">The **CPU** and **Processor** performance counters.</span></span>
    
<span data-ttu-id="eb39d-111">ほとんどの展開で、UCWA の CPU 使用率は平均で 15% を下回っている必要があります。</span><span class="sxs-lookup"><span data-stu-id="eb39d-111">For most deployments, UCWA CPU usage should be below 15 percent on average.</span></span> <span data-ttu-id="eb39d-112">メモリ使用量は、[ビジネス サーバー 2015 の Skype のサーバーのメモリ容量制限のためのモニター](server-memory-capacity-limits.md)で説明されている制限内に収まるようにします。</span><span class="sxs-lookup"><span data-stu-id="eb39d-112">Memory usage should fall within the limits described in [Monitor for server memory capacity limits in Skype for Business Server 2015](server-memory-capacity-limits.md).</span></span>
  
<span data-ttu-id="eb39d-113">CPU とメモリの使用状況カウンターに加えて、以下のパフォーマンス カウンターを使用すると、サーバーが要求で過負荷になっていないかどうかを確認するのに役立つ場合があります。</span><span class="sxs-lookup"><span data-stu-id="eb39d-113">In addition to CPU and memory usage counters, you can use the following performance counters to help determine when a server is overloaded with requests:</span></span>
  
- <span data-ttu-id="eb39d-114">**LS:WEB の調整と Authentication\WEB の合計の要求の処理に**、保留中のサーバー上の web 要求の数を示します。</span><span class="sxs-lookup"><span data-stu-id="eb39d-114">**LS:WEB - Throttling and Authentication\WEB - Total Requests in Processing**, which indicates the number of pending web requests on the server.</span></span> <span data-ttu-id="eb39d-115">このカウンターでは、10,000 に達すると、後続の要求は失敗します、エラー メッセージが「503 - サービスを使用できません」</span><span class="sxs-lookup"><span data-stu-id="eb39d-115">When this counter reaches 10,000, subsequent requests will fail, with the error message, "503 - Service Unavailable."</span></span>
    
- <span data-ttu-id="eb39d-116">**ASP.NET\Requests キュー**(常にゼロのはず)。</span><span class="sxs-lookup"><span data-stu-id="eb39d-116">**ASP.NET\Requests Queued** (should always be zero).</span></span>
    
> [!NOTE]
> <span data-ttu-id="eb39d-117">これらの値に達するか、これらの値を超えた場合、Web サービスをホストしているコンピューターの CPU、コア数、およびメモリの適切な規模設定の容量計画を再検討して、再計算する必要があります。</span><span class="sxs-lookup"><span data-stu-id="eb39d-117">If you meet or exceed these values, you should revisit and re-compute your capacity planning for the correct sizing of CPU, number of cores and memory for the computers hosting the web services.</span></span> 
  
 <span data-ttu-id="eb39d-118">**Mobility Service (Mcx):**</span><span class="sxs-lookup"><span data-stu-id="eb39d-118">**For the Mobility Service (Mcx):**</span></span>
  
- <span data-ttu-id="eb39d-119">**CSIntMcxAppPool** 、 **CSExtMcxAppPool**ワーカー プロセスのインターネット インフォメーション サービス (IIS) マネージャー。</span><span class="sxs-lookup"><span data-stu-id="eb39d-119">The **CSIntMcxAppPool** and **CSExtMcxAppPool** worker processes in Internet Information Services (IIS) Manager.</span></span> <span data-ttu-id="eb39d-120">[**ワーカー プロセス**] ウィンドウで、[**CPU %**] および [**プライベート バイト (KB)**] (メモリ) の列を確認します。</span><span class="sxs-lookup"><span data-stu-id="eb39d-120">In the **Worker Processes** pane, look at the **CPU %** and **Private Bytes (KB)** (memory) columns.</span></span>
    
- <span data-ttu-id="eb39d-121">[**CPU**] および [**プロセッサ**] パフォーマンス カウンター。</span><span class="sxs-lookup"><span data-stu-id="eb39d-121">The **CPU** and **Processor** performance counters.</span></span>
    
<span data-ttu-id="eb39d-122">ほとんどの展開で、Mobility Service の CPU 使用率は平均で 15% を下回っている必要があります。</span><span class="sxs-lookup"><span data-stu-id="eb39d-122">For most deployments, Mobility Service CPU usage should be below 15 percent, on average.</span></span> <span data-ttu-id="eb39d-123">メモリ使用量は、[ビジネス サーバー 2015 の Skype のサーバーのメモリ容量制限のためのモニター](server-memory-capacity-limits.md)で説明されている制限内に収まるようにします。</span><span class="sxs-lookup"><span data-stu-id="eb39d-123">Memory usage should fall within the limits described in [Monitor for server memory capacity limits in Skype for Business Server 2015](server-memory-capacity-limits.md).</span></span>
  
<span data-ttu-id="eb39d-124">CPU とメモリの使用状況カウンターに加えて、以下の ASP.NET パフォーマンス カウンターを使用すると、サーバーが要求で過負荷になっていないかどうかを確認するのに役立つ場合があります。</span><span class="sxs-lookup"><span data-stu-id="eb39d-124">In addition to CPU and memory usage counters, you can use the following ASP.NET performance counters to help determine when a server is overloaded with requests:</span></span>
  
- <span data-ttu-id="eb39d-125">**ASP.NET v2.0.50727\Requests 現在**、保留中のサーバー上の web 要求の数を示します。</span><span class="sxs-lookup"><span data-stu-id="eb39d-125">**ASP.NET v2.0.50727\Requests Current**, which indicates the number of pending web requests on the server.</span></span> <span data-ttu-id="eb39d-126">「503 - サービスを使用できません」のエラー メッセージとそれ以降の要求は失敗しますこのカウンターでは、5,000 に達すると、</span><span class="sxs-lookup"><span data-stu-id="eb39d-126">When this counter reaches 5,000, subsequent requests will fail with the error message, "503 - Service Unavailable."</span></span>
    
- <span data-ttu-id="eb39d-127">**ASP.NET\Requests キュー**(常にゼロのはず)。</span><span class="sxs-lookup"><span data-stu-id="eb39d-127">**ASP.NET\Requests Queued** (should always be zero).</span></span>
    
> [!NOTE]
> <span data-ttu-id="eb39d-128">これらの値に達するか、これらの値を超えた場合、Web サービスをホストしているコンピューターの CPU、コア数、およびメモリの適切な規模設定の容量計画を再検討して、再計算する必要があります。</span><span class="sxs-lookup"><span data-stu-id="eb39d-128">If you meet or exceed these values, you should revisit and recompute your capacity planning for the correct sizing of CPU, number of cores, and memory for the computers hosting the web services.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="eb39d-129">関連項目</span><span class="sxs-lookup"><span data-stu-id="eb39d-129">See also</span></span>

#### 

[<span data-ttu-id="eb39d-130">ビジネス サーバー 2015 の Skype のサーバーのメモリ容量制限のためのモニター</span><span class="sxs-lookup"><span data-stu-id="eb39d-130">Monitor for server memory capacity limits in Skype for Business Server 2015</span></span>](server-memory-capacity-limits.md)

