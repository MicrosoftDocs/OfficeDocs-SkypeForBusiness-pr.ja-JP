---
title: 'Lync Server 2013: Mobility Service および UCWA の使用状況の監視'
description: 'Lync Server 2013: Mobility Service および UCWA の使用状況を監視します。'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Monitoring Mobility Service and UCWA usage
ms:assetid: 8389b37a-ca3e-4047-8b51-85bc07da87e8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh690025(v=OCS.15)
ms:contentKeyID: 48184683
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6575941faf904e46cd1f66d7226a16c88e8cbaa3
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48548113"
---
# <a name="monitoring-mobility-service-and-ucwa-usage-in-lync-server-2013"></a><span data-ttu-id="b0f29-103">Lync Server 2013 でのモビリティサービスおよび UCWA の使用状況の監視</span><span class="sxs-lookup"><span data-stu-id="b0f29-103">Monitoring Mobility Service and UCWA usage in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b0f29-104">_**トピックの最終更新日:** 2013-02-14_</span><span class="sxs-lookup"><span data-stu-id="b0f29-104">_**Topic Last Modified:** 2013-02-14_</span></span>

<span data-ttu-id="b0f29-105">継続的に、Lync Server Mobility Service (Mcx) および統合コミュニケーション Web API (UCWA) で使用されている CPU とメモリを監視する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b0f29-105">On an ongoing basis, you should monitor the CPU and memory that is used by the Lync Server Mobility Service (Mcx) and the Unified Communications Web API (UCWA).</span></span> <span data-ttu-id="b0f29-106">使用状況を監視するには、次のものを使用できます。</span><span class="sxs-lookup"><span data-stu-id="b0f29-106">To monitor usage, you can use the following:</span></span>

<span data-ttu-id="b0f29-107">**ユニファイドコミュニケーション Web API (UCWA) の場合:**</span><span class="sxs-lookup"><span data-stu-id="b0f29-107">**For Unified Communications Web API (UCWA):**</span></span>

  - <span data-ttu-id="b0f29-108">インターネットインフォメーションサービス (IIS) マネージャーの **LyncUcwa** ワーカープロセス。</span><span class="sxs-lookup"><span data-stu-id="b0f29-108">The **LyncUcwa** worker process in Internet Information Services (IIS) Manager.</span></span> <span data-ttu-id="b0f29-109">[**ワーカー プロセス**] ウィンドウで、[**CPU %**] および [**プライベート バイト (KB)**] (メモリ) の列を確認します。</span><span class="sxs-lookup"><span data-stu-id="b0f29-109">In the **Worker Processes** pane, look at the **CPU %** and **Private Bytes (KB)** (memory) columns.</span></span>

  - <span data-ttu-id="b0f29-110">[**CPU**] および [**プロセッサ**] パフォーマンス カウンター</span><span class="sxs-lookup"><span data-stu-id="b0f29-110">The **CPU** and **Processor** performance counters.</span></span>

<span data-ttu-id="b0f29-111">ほとんどの展開では、UCWA の CPU 使用率は平均で15% を下回っている必要があります。</span><span class="sxs-lookup"><span data-stu-id="b0f29-111">For most deployments, UCWA CPU usage should be below 15 percent on average.</span></span> <span data-ttu-id="b0f29-112">メモリ使用量は、「 [Lync server 2013 のサーバーのメモリ容量制限の監視](lync-server-2013-monitoring-for-server-memory-capacity-limits.md)」で説明されている制限の範囲内に収まる必要があります。</span><span class="sxs-lookup"><span data-stu-id="b0f29-112">Memory usage should fall within the limits described in [Monitoring for server memory capacity limits in Lync Server 2013](lync-server-2013-monitoring-for-server-memory-capacity-limits.md).</span></span>

<span data-ttu-id="b0f29-113">CPU およびメモリの使用状況カウンターに加えて、次のパフォーマンスカウンターを使用して、サーバーが要求で過負荷になっていないかどうかを判断するのに役立てることができます。</span><span class="sxs-lookup"><span data-stu-id="b0f29-113">In addition to CPU and memory usage counters, you can use the following performance counters to help determine when a server is overloaded with requests:</span></span>

  - <span data-ttu-id="b0f29-114">**LS: WEB-調整と認証 \\WEB:** サーバー上で保留中の web 要求の数を示す、処理中の要求の合計です。</span><span class="sxs-lookup"><span data-stu-id="b0f29-114">**LS:WEB – Throttling and Authentication\\WEB – Total Requests in Processing**, which indicates the number of pending web requests on the server.</span></span> <span data-ttu-id="b0f29-115">このカウンターが1万に達すると、次の要求は失敗し、エラーメッセージ "503-サービスを使用できません。" が表示されます。</span><span class="sxs-lookup"><span data-stu-id="b0f29-115">When this counter reaches 10,000, subsequent requests will fail, with the error message, "503 - Service Unavailable."</span></span>

  - <span data-ttu-id="b0f29-116">**ASP.NET \\Requests** (常に0である必要があります)。</span><span class="sxs-lookup"><span data-stu-id="b0f29-116">**ASP.NET\\Requests Queued** (should always be zero).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="b0f29-117">これらの値と一致するか、それを超える場合は、Web サービスをホストしているコンピューターの CPU、コアの数、およびメモリの正確なサイジングに関する容量計画を再検討して再計算する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b0f29-117">If you meet or exceed these values, you should revisit and re-compute your capacity planning for the correct sizing of CPU, number of cores and memory for the computers hosting the Web services.</span></span>



</div>

<span data-ttu-id="b0f29-118">**Mobility Service (Mcx) の場合:**</span><span class="sxs-lookup"><span data-stu-id="b0f29-118">**For the Mobility Service (Mcx):**</span></span>

  - <span data-ttu-id="b0f29-119">インターネットインフォメーションサービス (IIS) マネージャーの **Csintmcxapppool** および **csextmcxapppool** ワーカープロセス。</span><span class="sxs-lookup"><span data-stu-id="b0f29-119">The **CSIntMcxAppPool** and **CSExtMcxAppPool** worker processes in Internet Information Services (IIS) Manager.</span></span> <span data-ttu-id="b0f29-120">[**ワーカー プロセス**] ウィンドウで、[**CPU %**] および [**プライベート バイト (KB)**] (メモリ) の列を確認します。</span><span class="sxs-lookup"><span data-stu-id="b0f29-120">In the **Worker Processes** pane, look at the **CPU %** and **Private Bytes (KB)** (memory) columns.</span></span>

  - <span data-ttu-id="b0f29-121">[**CPU**] および [**プロセッサ**] パフォーマンス カウンター</span><span class="sxs-lookup"><span data-stu-id="b0f29-121">The **CPU** and **Processor** performance counters.</span></span>

<span data-ttu-id="b0f29-122">ほとんどの展開では、モビリティサービスの CPU 使用率は平均で15% を下回っている必要があります。</span><span class="sxs-lookup"><span data-stu-id="b0f29-122">For most deployments, Mobility Service CPU usage should be below 15 percent, on average.</span></span> <span data-ttu-id="b0f29-123">メモリ使用量は、「 [Lync server 2013 のサーバーのメモリ容量制限の監視](lync-server-2013-monitoring-for-server-memory-capacity-limits.md)」で説明されている制限の範囲内に収まる必要があります。</span><span class="sxs-lookup"><span data-stu-id="b0f29-123">Memory usage should fall within the limits described in [Monitoring for server memory capacity limits in Lync Server 2013](lync-server-2013-monitoring-for-server-memory-capacity-limits.md).</span></span>

<span data-ttu-id="b0f29-124">CPU とメモリの使用状況カウンターに加えて、以下の ASP.NET パフォーマンス カウンターを使用すると、サーバーが要求で過負荷になっていないかどうかを確認するのに役立つ場合があります。</span><span class="sxs-lookup"><span data-stu-id="b0f29-124">In addition to CPU and memory usage counters, you can use the following ASP.NET performance counters to help determine when a server is overloaded with requests:</span></span>

  - <span data-ttu-id="b0f29-125">**ASP.NET v v2.0.50727 \\Current を要求**します。これは、サーバー上で保留中の web 要求の数を示します。</span><span class="sxs-lookup"><span data-stu-id="b0f29-125">**ASP.NET v2.0.50727\\Requests Current**, which indicates the number of pending web requests on the server.</span></span> <span data-ttu-id="b0f29-126">このカウンターが5000に達すると、以降の要求は失敗し、"503-サービスは使用できません" というエラーメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="b0f29-126">When this counter reaches 5,000, subsequent requests will fail with the error message, "503 - Service Unavailable."</span></span>

  - <span data-ttu-id="b0f29-127">**ASP.NET \\Requests** (常に0である必要があります)。</span><span class="sxs-lookup"><span data-stu-id="b0f29-127">**ASP.NET\\Requests Queued** (should always be zero).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="b0f29-128">これらの値と一致するか、それを超えた場合は、Web サービスをホストしているコンピューターの CPU、コア数、およびメモリの正確なサイジングを行うために、容量計画を再検討して再計算する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b0f29-128">If you meet or exceed these values, you should revisit and recompute your capacity planning for the correct sizing of CPU, number of cores, and memory for the computers hosting the Web services.</span></span>



</div>

<div>

## <a name="see-also"></a><span data-ttu-id="b0f29-129">関連項目</span><span class="sxs-lookup"><span data-stu-id="b0f29-129">See Also</span></span>


[<span data-ttu-id="b0f29-130">Lync Server 2013 でのサーバーのメモリ容量制限の監視</span><span class="sxs-lookup"><span data-stu-id="b0f29-130">Monitoring for server memory capacity limits in Lync Server 2013</span></span>](lync-server-2013-monitoring-for-server-memory-capacity-limits.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

