---
title: Skype for Business Server のモビリティサービスと UCWA の使用状況を監視する
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 8389b37a-ca3e-4047-8b51-85bc07da87e8
description: '概要: Skype for Business Server のモビリティサービス (Mcx) とユニファイドコミュニケーション Web API (UCWA) を管理します。'
ms.openlocfilehash: 7c41e92b144e1bd4d198c5e9d9f90913ce41400e
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2020
ms.locfileid: "41817686"
---
# <a name="monitor-mobility-service-and-ucwa-usage-in-skype-for-business-server"></a><span data-ttu-id="cba14-103">Skype for Business Server のモビリティサービスと UCWA の使用状況を監視する</span><span class="sxs-lookup"><span data-stu-id="cba14-103">Monitor Mobility Service and UCWA usage in Skype for Business Server</span></span>
 
<span data-ttu-id="cba14-104">**概要:** Skype for Business Server のモビリティサービス (Mcx) とユニファイドコミュニケーション Web API (UCWA) を管理します。</span><span class="sxs-lookup"><span data-stu-id="cba14-104">**Summary:** Manage the Mobility Service (Mcx) and the Unified Communications Web API (UCWA) in Skype for Business Server.</span></span>

> [!NOTE]
> <span data-ttu-id="cba14-105">Skype for Business Server 2019 では、従来のモバイルクライアントに対する MCX (モバイルサービス) のサポートは利用できなくなりました。</span><span class="sxs-lookup"><span data-stu-id="cba14-105">MCX (Mobility Service) support for legacy mobile clients is no longer available in Skype for Business Server 2019.</span></span> <span data-ttu-id="cba14-106">現在のすべての Skype for Business のモバイルクライアントでは、インスタントメッセージング (IM)、プレゼンス、連絡先をサポートするために、既にユニファイドコミュニケーション Web API (UCWA) を使用しています。</span><span class="sxs-lookup"><span data-stu-id="cba14-106">All current Skype for Business mobile clients already use Unified Communications Web API (UCWA) to support instant messaging (IM), presence, and contacts.</span></span> <span data-ttu-id="cba14-107">MCX を使用するレガシクライアントを使っているユーザーは、現在のクライアントにアップグレードする必要があります。</span><span class="sxs-lookup"><span data-stu-id="cba14-107">Users with legacy clients using MCX will need to upgrade to a current client.</span></span>
  
<span data-ttu-id="cba14-108">継続的に、Skype for Business Server Mobility Service (Mcx) とユニファイドコミュニケーション Web API (UCWA) で使用されている CPU とメモリを監視する必要があります。</span><span class="sxs-lookup"><span data-stu-id="cba14-108">On an ongoing basis, you should monitor the CPU and memory that is used by the Skype for Business Server Mobility Service (Mcx) and the Unified Communications Web API (UCWA).</span></span> <span data-ttu-id="cba14-109">使用状況を監視するには、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="cba14-109">To monitor usage, you can use the following:</span></span>
  
 <span data-ttu-id="cba14-110">**Unified Communications Web API (UCWA):**</span><span class="sxs-lookup"><span data-stu-id="cba14-110">**For Unified Communications Web API (UCWA):**</span></span>
  
- <span data-ttu-id="cba14-111">インターネットインフォメーションサービス (IIS) マネージャーでの**LyncUcwa** worker プロセス。</span><span class="sxs-lookup"><span data-stu-id="cba14-111">The **LyncUcwa** worker process in Internet Information Services (IIS) Manager.</span></span> <span data-ttu-id="cba14-112">[**ワーカー プロセス**] ウィンドウで、[**CPU %**] および [**プライベート バイト (KB)**] (メモリ) の列を確認します。</span><span class="sxs-lookup"><span data-stu-id="cba14-112">In the **Worker Processes** pane, look at the **CPU %** and **Private Bytes (KB)** (memory) columns.</span></span>
    
- <span data-ttu-id="cba14-113">[**CPU**] および [**プロセッサ**] パフォーマンス カウンター。</span><span class="sxs-lookup"><span data-stu-id="cba14-113">The **CPU** and **Processor** performance counters.</span></span>
    
<span data-ttu-id="cba14-114">ほとんどの展開で、UCWA の CPU 使用率は平均で 15% を下回っている必要があります。</span><span class="sxs-lookup"><span data-stu-id="cba14-114">For most deployments, UCWA CPU usage should be below 15 percent on average.</span></span> <span data-ttu-id="cba14-115">メモリ使用量は、「 [Skype For Business server のサーバーメモリ容量の上限](server-memory-capacity-limits.md)」に記載されている制限内に収まっている必要があります。</span><span class="sxs-lookup"><span data-stu-id="cba14-115">Memory usage should fall within the limits described in [Monitor for server memory capacity limits in Skype for Business Server](server-memory-capacity-limits.md).</span></span>
  
<span data-ttu-id="cba14-116">CPU とメモリの使用状況カウンターに加えて、以下のパフォーマンス カウンターを使用すると、サーバーが要求で過負荷になっていないかどうかを確認するのに役立つ場合があります。</span><span class="sxs-lookup"><span data-stu-id="cba14-116">In addition to CPU and memory usage counters, you can use the following performance counters to help determine when a server is overloaded with requests:</span></span>
  
- <span data-ttu-id="cba14-117">**LS: web の調整と Authentication\WEB-処理中の要求合計**。サーバー上の保留中の WEB 要求の数を示します。</span><span class="sxs-lookup"><span data-stu-id="cba14-117">**LS:WEB - Throttling and Authentication\WEB - Total Requests in Processing**, which indicates the number of pending web requests on the server.</span></span> <span data-ttu-id="cba14-118">このカウンターが1万に達すると、その後の要求は失敗し、"503-サービスを利用できません" というエラーメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="cba14-118">When this counter reaches 10,000, subsequent requests will fail, with the error message, "503 - Service Unavailable."</span></span>
    
- <span data-ttu-id="cba14-119">**ASP.NET\Requests Queued** (常にゼロである必要があります)。</span><span class="sxs-lookup"><span data-stu-id="cba14-119">**ASP.NET\Requests Queued** (should always be zero).</span></span>
    
> [!NOTE]
> <span data-ttu-id="cba14-120">これらの値に達するか、これらの値を超えた場合、Web サービスをホストしているコンピューターの CPU、コア数、およびメモリの適切な規模設定の容量計画を再検討して、再計算する必要があります。</span><span class="sxs-lookup"><span data-stu-id="cba14-120">If you meet or exceed these values, you should revisit and re-compute your capacity planning for the correct sizing of CPU, number of cores and memory for the computers hosting the web services.</span></span> 
  
 <span data-ttu-id="cba14-121">**Mobility Service (Mcx):**</span><span class="sxs-lookup"><span data-stu-id="cba14-121">**For the Mobility Service (Mcx):**</span></span>
  
- <span data-ttu-id="cba14-122">**Csintmcxapppool**と**csextmcxapppool**ワーカープロセス (インターネットインフォメーションサービス (IIS) マネージャー)。</span><span class="sxs-lookup"><span data-stu-id="cba14-122">The **CSIntMcxAppPool** and **CSExtMcxAppPool** worker processes in Internet Information Services (IIS) Manager.</span></span> <span data-ttu-id="cba14-123">[**ワーカー プロセス**] ウィンドウで、[**CPU %**] および [**プライベート バイト (KB)**] (メモリ) の列を確認します。</span><span class="sxs-lookup"><span data-stu-id="cba14-123">In the **Worker Processes** pane, look at the **CPU %** and **Private Bytes (KB)** (memory) columns.</span></span>
    
- <span data-ttu-id="cba14-124">[**CPU**] および [**プロセッサ**] パフォーマンス カウンター。</span><span class="sxs-lookup"><span data-stu-id="cba14-124">The **CPU** and **Processor** performance counters.</span></span>
    
<span data-ttu-id="cba14-125">ほとんどの展開で、Mobility Service の CPU 使用率は平均で 15% を下回っている必要があります。</span><span class="sxs-lookup"><span data-stu-id="cba14-125">For most deployments, Mobility Service CPU usage should be below 15 percent, on average.</span></span> <span data-ttu-id="cba14-126">メモリ使用量は、「 [Skype For Business server のサーバーメモリ容量の上限](server-memory-capacity-limits.md)」に記載されている制限内に収まっている必要があります。</span><span class="sxs-lookup"><span data-stu-id="cba14-126">Memory usage should fall within the limits described in [Monitor for server memory capacity limits in Skype for Business Server](server-memory-capacity-limits.md).</span></span>
  
<span data-ttu-id="cba14-127">CPU とメモリの使用状況カウンターに加えて、以下の ASP.NET パフォーマンス カウンターを使用すると、サーバーが要求で過負荷になっていないかどうかを確認するのに役立つ場合があります。</span><span class="sxs-lookup"><span data-stu-id="cba14-127">In addition to CPU and memory usage counters, you can use the following ASP.NET performance counters to help determine when a server is overloaded with requests:</span></span>
  
- <span data-ttu-id="cba14-128">**ASP.NET v 2.0.50727 \ 要求電流**は、サーバー上の保留中の web 要求の数を示します。</span><span class="sxs-lookup"><span data-stu-id="cba14-128">**ASP.NET v2.0.50727\Requests Current**, which indicates the number of pending web requests on the server.</span></span> <span data-ttu-id="cba14-129">このカウンターが5000に達すると、その後の要求は失敗し、"503-サービスを利用できません" というエラーメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="cba14-129">When this counter reaches 5,000, subsequent requests will fail with the error message, "503 - Service Unavailable."</span></span>
    
- <span data-ttu-id="cba14-130">**ASP.NET\Requests Queued** (常にゼロである必要があります)。</span><span class="sxs-lookup"><span data-stu-id="cba14-130">**ASP.NET\Requests Queued** (should always be zero).</span></span>
    
> [!NOTE]
> <span data-ttu-id="cba14-131">これらの値に達するか、これらの値を超えた場合、Web サービスをホストしているコンピューターの CPU、コア数、およびメモリの適切な規模設定の容量計画を再検討して、再計算する必要があります。</span><span class="sxs-lookup"><span data-stu-id="cba14-131">If you meet or exceed these values, you should revisit and recompute your capacity planning for the correct sizing of CPU, number of cores, and memory for the computers hosting the web services.</span></span> 

> [!NOTE]
> <span data-ttu-id="cba14-132">Skype for Business Server 2019 では、従来のモバイルクライアントに対する MCX (モバイルサービス) のサポートは利用できなくなりました。</span><span class="sxs-lookup"><span data-stu-id="cba14-132">MCX (Mobility Service) support for legacy mobile clients is no longer available in Skype for Business Server 2019.</span></span> <span data-ttu-id="cba14-133">現在のすべての Skype for Business のモバイルクライアントでは、インスタントメッセージング (IM)、プレゼンス、連絡先をサポートするために、既にユニファイドコミュニケーション Web API (UCWA) を使用しています。</span><span class="sxs-lookup"><span data-stu-id="cba14-133">All current Skype for Business mobile clients already use Unified Communications Web API (UCWA) to support instant messaging (IM), presence, and contacts.</span></span> <span data-ttu-id="cba14-134">MCX を使用するレガシクライアントを使っているユーザーは、現在のクライアントにアップグレードする必要があります。</span><span class="sxs-lookup"><span data-stu-id="cba14-134">Users with legacy clients using MCX will need to upgrade to a current client.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="cba14-135">関連項目</span><span class="sxs-lookup"><span data-stu-id="cba14-135">See also</span></span>

[<span data-ttu-id="cba14-136">Skype for Business Server でサーバーのメモリ容量の上限を監視する</span><span class="sxs-lookup"><span data-stu-id="cba14-136">Monitor for server memory capacity limits in Skype for Business Server</span></span>](server-memory-capacity-limits.md)
