---
title: 'Lync Server 2013: モビリティサービスと UCWA の使用状況を監視する'
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
ms.openlocfilehash: d4968c1a3b3dc30bdab2a3c19fd8e930da6122cb
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41756811"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="monitoring-mobility-service-and-ucwa-usage-in-lync-server-2013"></a><span data-ttu-id="b2c14-102">Lync Server 2013 でのモビリティサービスと UCWA の使用状況の監視</span><span class="sxs-lookup"><span data-stu-id="b2c14-102">Monitoring Mobility Service and UCWA usage in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b2c14-103">_**最終更新日:** 2013-02-14_</span><span class="sxs-lookup"><span data-stu-id="b2c14-103">_**Topic Last Modified:** 2013-02-14_</span></span>

<span data-ttu-id="b2c14-104">継続的に、Lync Server Mobility Service (Mcx) とユニファイドコミュニケーション Web API (UCWA) で使用されている CPU とメモリを監視する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b2c14-104">On an ongoing basis, you should monitor the CPU and memory that is used by the Lync Server Mobility Service (Mcx) and the Unified Communications Web API (UCWA).</span></span> <span data-ttu-id="b2c14-105">使用状況を監視するには、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="b2c14-105">To monitor usage, you can use the following:</span></span>

<span data-ttu-id="b2c14-106">**Unified Communications Web API (UCWA):**</span><span class="sxs-lookup"><span data-stu-id="b2c14-106">**For Unified Communications Web API (UCWA):**</span></span>

  - <span data-ttu-id="b2c14-107">インターネットインフォメーションサービス (IIS) マネージャーでの**LyncUcwa** worker プロセス。</span><span class="sxs-lookup"><span data-stu-id="b2c14-107">The **LyncUcwa** worker process in Internet Information Services (IIS) Manager.</span></span> <span data-ttu-id="b2c14-108">[**ワーカー プロセス**] ウィンドウで、[**CPU %**] および [**プライベート バイト (KB)**] (メモリ) の列を確認します。</span><span class="sxs-lookup"><span data-stu-id="b2c14-108">In the **Worker Processes** pane, look at the **CPU %** and **Private Bytes (KB)** (memory) columns.</span></span>

  - <span data-ttu-id="b2c14-109">[**CPU**] および [**プロセッサ**] パフォーマンス カウンター。</span><span class="sxs-lookup"><span data-stu-id="b2c14-109">The **CPU** and **Processor** performance counters.</span></span>

<span data-ttu-id="b2c14-110">ほとんどの展開で、UCWA の CPU 使用率は平均で 15% を下回っている必要があります。</span><span class="sxs-lookup"><span data-stu-id="b2c14-110">For most deployments, UCWA CPU usage should be below 15 percent on average.</span></span> <span data-ttu-id="b2c14-111">メモリ使用量は、「 [Lync server 2013 でのサーバーメモリ容量の上限を監視](lync-server-2013-monitoring-for-server-memory-capacity-limits.md)する」で説明されている制限内に収まる必要があります。</span><span class="sxs-lookup"><span data-stu-id="b2c14-111">Memory usage should fall within the limits described in [Monitoring for server memory capacity limits in Lync Server 2013](lync-server-2013-monitoring-for-server-memory-capacity-limits.md).</span></span>

<span data-ttu-id="b2c14-112">CPU とメモリの使用状況カウンターに加えて、以下のパフォーマンス カウンターを使用すると、サーバーが要求で過負荷になっていないかどうかを確認するのに役立つ場合があります。</span><span class="sxs-lookup"><span data-stu-id="b2c14-112">In addition to CPU and memory usage counters, you can use the following performance counters to help determine when a server is overloaded with requests:</span></span>

  - <span data-ttu-id="b2c14-113">**LS: web –調整と認証\\WEB –処理中の要求の合計**。サーバー上の保留中の WEB 要求の数を示します。</span><span class="sxs-lookup"><span data-stu-id="b2c14-113">**LS:WEB – Throttling and Authentication\\WEB – Total Requests in Processing**, which indicates the number of pending web requests on the server.</span></span> <span data-ttu-id="b2c14-114">このカウンターが1万に達すると、その後の要求は失敗し、"503-サービスを利用できません" というエラーメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="b2c14-114">When this counter reaches 10,000, subsequent requests will fail, with the error message, "503 - Service Unavailable."</span></span>

  - <span data-ttu-id="b2c14-115">**ASP.NET\\要求はキューに入れら**れます (常に0である必要があります)。</span><span class="sxs-lookup"><span data-stu-id="b2c14-115">**ASP.NET\\Requests Queued** (should always be zero).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="b2c14-116">これらの値を満たしているか、それ以上の場合は、Web サービスをホストしているコンピューターの CPU、コア数、メモリのサイズが適切に調整されるように、キャパシティ計画を再検討して再計算する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b2c14-116">If you meet or exceed these values, you should revisit and re-compute your capacity planning for the correct sizing of CPU, number of cores and memory for the computers hosting the Web services.</span></span>



</div>

<span data-ttu-id="b2c14-117">**Mobility Service (Mcx):**</span><span class="sxs-lookup"><span data-stu-id="b2c14-117">**For the Mobility Service (Mcx):**</span></span>

  - <span data-ttu-id="b2c14-118">**Csintmcxapppool**と**csextmcxapppool**ワーカープロセス (インターネットインフォメーションサービス (IIS) マネージャー)。</span><span class="sxs-lookup"><span data-stu-id="b2c14-118">The **CSIntMcxAppPool** and **CSExtMcxAppPool** worker processes in Internet Information Services (IIS) Manager.</span></span> <span data-ttu-id="b2c14-119">[**ワーカー プロセス**] ウィンドウで、[**CPU %**] および [**プライベート バイト (KB)**] (メモリ) の列を確認します。</span><span class="sxs-lookup"><span data-stu-id="b2c14-119">In the **Worker Processes** pane, look at the **CPU %** and **Private Bytes (KB)** (memory) columns.</span></span>

  - <span data-ttu-id="b2c14-120">[**CPU**] および [**プロセッサ**] パフォーマンス カウンター。</span><span class="sxs-lookup"><span data-stu-id="b2c14-120">The **CPU** and **Processor** performance counters.</span></span>

<span data-ttu-id="b2c14-121">ほとんどの展開で、Mobility Service の CPU 使用率は平均で 15% を下回っている必要があります。</span><span class="sxs-lookup"><span data-stu-id="b2c14-121">For most deployments, Mobility Service CPU usage should be below 15 percent, on average.</span></span> <span data-ttu-id="b2c14-122">メモリ使用量は、「 [Lync server 2013 でのサーバーメモリ容量の上限を監視](lync-server-2013-monitoring-for-server-memory-capacity-limits.md)する」で説明されている制限内に収まる必要があります。</span><span class="sxs-lookup"><span data-stu-id="b2c14-122">Memory usage should fall within the limits described in [Monitoring for server memory capacity limits in Lync Server 2013](lync-server-2013-monitoring-for-server-memory-capacity-limits.md).</span></span>

<span data-ttu-id="b2c14-123">CPU とメモリの使用状況カウンターに加えて、以下の ASP.NET パフォーマンス カウンターを使用すると、サーバーが要求で過負荷になっていないかどうかを確認するのに役立つ場合があります。</span><span class="sxs-lookup"><span data-stu-id="b2c14-123">In addition to CPU and memory usage counters, you can use the following ASP.NET performance counters to help determine when a server is overloaded with requests:</span></span>

  - <span data-ttu-id="b2c14-124">**ASP.NET v 2.0.50727\\要求 Current**は、サーバー上の保留中の web 要求の数を示します。</span><span class="sxs-lookup"><span data-stu-id="b2c14-124">**ASP.NET v2.0.50727\\Requests Current**, which indicates the number of pending web requests on the server.</span></span> <span data-ttu-id="b2c14-125">このカウンターが5000に達すると、その後の要求は失敗し、"503-サービスを利用できません" というエラーメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="b2c14-125">When this counter reaches 5,000, subsequent requests will fail with the error message, "503 - Service Unavailable."</span></span>

  - <span data-ttu-id="b2c14-126">**ASP.NET\\要求はキューに入れら**れます (常に0である必要があります)。</span><span class="sxs-lookup"><span data-stu-id="b2c14-126">**ASP.NET\\Requests Queued** (should always be zero).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="b2c14-127">これらの値を満たしている、または超える場合は、Web サービスをホストしているコンピューターの CPU、コア数、メモリの適切なサイズ変更のために、キャパシティ計画を再検討して再計算する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b2c14-127">If you meet or exceed these values, you should revisit and recompute your capacity planning for the correct sizing of CPU, number of cores, and memory for the computers hosting the Web services.</span></span>



</div>

<div>

## <a name="see-also"></a><span data-ttu-id="b2c14-128">関連項目</span><span class="sxs-lookup"><span data-stu-id="b2c14-128">See Also</span></span>


[<span data-ttu-id="b2c14-129">Lync Server 2013 でのサーバーメモリ容量の上限を監視する</span><span class="sxs-lookup"><span data-stu-id="b2c14-129">Monitoring for server memory capacity limits in Lync Server 2013</span></span>](lync-server-2013-monitoring-for-server-memory-capacity-limits.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

