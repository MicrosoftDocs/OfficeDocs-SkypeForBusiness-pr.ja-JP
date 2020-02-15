---
title: 'Lync Server 2013: サーバーのメモリ容量制限の監視'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Monitoring for server memory capacity limits
ms:assetid: 1697ea71-6fcf-480d-b4e9-cd79f94d247e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh689982(v=OCS.15)
ms:contentKeyID: 48183506
ms.date: 12/29/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 45600ed9c822851c89b13cb776bbc58464decde0
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2020
ms.locfileid: "42048100"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="monitoring-for-server-memory-capacity-limits-in-lync-server-2013"></a><span data-ttu-id="69e83-102">Lync Server 2013 でのサーバーのメモリ容量制限の監視</span><span class="sxs-lookup"><span data-stu-id="69e83-102">Monitoring for server memory capacity limits in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="69e83-103">_**トピックの最終更新日:** 2016-12-08_</span><span class="sxs-lookup"><span data-stu-id="69e83-103">_**Topic Last Modified:** 2016-12-08_</span></span>

    Some information in this topic pertains to Cumulative Updates for Lync Server 2013: February 2013.

<div>


> [!WARNING]  
> <span data-ttu-id="69e83-104">このトピックの容量計画を参照する情報は、Lync 2010 モバイルクライアントおよび Mobility Service (Mcx) にのみ関連しています。</span><span class="sxs-lookup"><span data-stu-id="69e83-104">The information in this topic that refers to Capacity Planning pertains only to Lync 2010 Mobile clients and the Mobility Service (Mcx).</span></span> <span data-ttu-id="69e83-105">Lync 2013 Mobile クライアントによって使用される統合コミュニケーション Web API (UCWA) の容量計画は、Lync Server 2013、計画ツールによって提供されます。</span><span class="sxs-lookup"><span data-stu-id="69e83-105">Capacity Planning for the Unified Communications Web API (UCWA), used by the Lync 2013 Mobile clients, is provided by the Lync Server 2013, Planning Tool.</span></span>



</div>

<span data-ttu-id="69e83-106">2つのモビリティパフォーマンスカウンターは、現在の使用状況を判断し、Lync Server 2013 Mobility Service (Mcx) の容量を計画したり、UCWA のメモリ使用量を監視したりするのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="69e83-106">Two mobility performance counters can help you to determine your current usage and help you plan capacity for the Lync Server 2013 Mobility Service (Mcx), as well as to monitor memory usage for UCWA.</span></span> <span data-ttu-id="69e83-107">UCWA では、カウンターカテゴリは**LS: WEB-UCWA**です。</span><span class="sxs-lookup"><span data-stu-id="69e83-107">For UCWA, the counter category is **LS:WEB – UCWA**.</span></span> <span data-ttu-id="69e83-108">Mobility Service (Mcx) の場合、カウンターはカテゴリ**LS: WEB-モバイル通信サービス**の下にあります。</span><span class="sxs-lookup"><span data-stu-id="69e83-108">For the Mobility Service (Mcx), the counters are under the category **LS:WEB - Mobile Communication Service**.</span></span> <span data-ttu-id="69e83-109">監視するカウンターは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="69e83-109">The counters to monitor are:</span></span>

  - <span data-ttu-id="69e83-110">アクティブなプレゼンスサブスクリプションを**持つ現在アクティブなセッション数**(アクティブなプレゼンスサブスクリプションを使用する現在のエンドポイント数) (常時接続されたモバイルユーザーの数)</span><span class="sxs-lookup"><span data-stu-id="69e83-110">**Currently Active Session Count with Active Presence Subscriptions**, which is the current number of endpoints registered through UCWA or the Mobility Service (Mcx) that have active presence subscriptions (number of always-connected mobile users)</span></span>

  - <span data-ttu-id="69e83-111">**現在アクティブなセッション数**。これは、ucwa または Mobility Service で登録されたエンドポイントの現在の数です。</span><span class="sxs-lookup"><span data-stu-id="69e83-111">**Currently Active Session Count**, which is the current number of endpoints registered through UCWA or the Mobility Service</span></span>

<span data-ttu-id="69e83-112">**アクティブなプレゼンスサブスクリプション**と**現在アクティブなセッション数**が少ない状態で、現在アクティブなセッション数の差が少ない場合は、ほとんどのモバイルデバイスユーザーに Android または Nokia モバイルデバイスなどの常時接続デバイスがあることを意味します (mcx のみ)。</span><span class="sxs-lookup"><span data-stu-id="69e83-112">If the difference between **Currently Active Session Count with Active Presence Subscriptions** and **Currently Active Session Count** is small over time, this means that most mobile device users have an always-connected device, such as an Android or Nokia mobile device (for Mcx only).</span></span> <span data-ttu-id="69e83-113">UCWA の常時接続デバイスには、Lync 2013 Mobile クライアントを実行している Apple および Android デバイスが含まれます。</span><span class="sxs-lookup"><span data-stu-id="69e83-113">UCWA always-connected devices include Apple and Android devices running Lync 2013 Mobile clients).</span></span> <span data-ttu-id="69e83-114">**現在アクティブなセッション数**が、アクティブな**プレゼンスサブスクリプションを使用して現在アクティブなセッション数**を超えている場合は、他のユーザーが、Mcx の下で Apple IOS デバイスや Windows Phone などのバックグラウンドエンドポイントデバイスを使用していることを示します。</span><span class="sxs-lookup"><span data-stu-id="69e83-114">If **Currently Active Session Count** is much higher than **Currently Active Session Count with Active Presence Subscriptions**, this indicates that more users are using a background endpoint device, such as an Apple iOS device or Windows Phone under Mcx.</span></span> <span data-ttu-id="69e83-115">(これとして登録されるのは、Windows Phone が唯一の Lync 2013 モバイルクライアントです)。</span><span class="sxs-lookup"><span data-stu-id="69e83-115">(Windows Phone is the only Lync 2013 Mobile client that will register as this).</span></span>

<span data-ttu-id="69e83-116">**アクティブなプレゼンスサブスクリプション**と、**現在アクティブなセッション数**のパフォーマンスカウンターに関する制限を設定する必要があります。これには、予想される使用状況、容量計画の結果、モビリティサービスおよびその他のフロントエンドサーバーカウンターの継続的な監視に基づきます。</span><span class="sxs-lookup"><span data-stu-id="69e83-116">You should set a limit on the **Currently Active Session Count with Active Presence Subscriptions** and **Currently Active Session Count** performance counters based on your expected usage, capacity planning results, and ongoing monitoring of Mobility Service and other Front End Server counters.</span></span> <span data-ttu-id="69e83-117">設定する制限によって、サーバーの容量を評価し、容量を超えたときにアラートを発生させることができます。</span><span class="sxs-lookup"><span data-stu-id="69e83-117">The limits you set should enable you to evaluate server capacity and raise alerts when capacity is exceeded.</span></span>

<span data-ttu-id="69e83-118">適切な制限を決定するには、まず、Mobility Service のフロントエンドサーバーで使用可能なメモリ容量を特定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="69e83-118">To determine the appropriate limits, you need to first determine how much memory is available on the Front End Server for the Mobility Service.</span></span> <span data-ttu-id="69e83-119">カウンターを監視して、次の式に従って、容量の増設を計画する必要があるかどうかを判断します。</span><span class="sxs-lookup"><span data-stu-id="69e83-119">Monitor the counters to determine when you need to plan for extra capacity, according to the following formula:</span></span>

<span data-ttu-id="69e83-120">Mcx Mobility Service (MB) によって使用された合計メモリ = 164 + (400 + \* 134)/1024**現在アクティブなセッション数がアクティブプレゼンスサブスクリプション**+ 400/1024 \* (現在アクティブな**セッション数**がアクティブな**プレゼンスサブスクリプションで現在**アクティブなセッション数)</span><span class="sxs-lookup"><span data-stu-id="69e83-120">Total memory used by the Mcx Mobility Service (MB) = 164 + (400 + 134) / 1024 \* **Currently Active Session Count with Active Presence Subscriptions** + 400 / 1024 \* (**Currently Active Session Count** – **Currently Active Session Count with Active Presence Subscriptions**)</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="69e83-121">Microsoft Lync Server 2010 の容量計算機は、スプレッドシートを使用して、サーバーの要件 (CPU、メモリ、ハードドライブなど) を決定するための計画を可能にするすべての式で事前設定されています。</span><span class="sxs-lookup"><span data-stu-id="69e83-121">The Microsoft Lync Server 2010 Capacity Calculator is a spreadsheet that is prepopulated with all of the formulas that enable a planner to determine what the requirements will be for the servers, including CPU, memory, and hard drive.</span></span> <span data-ttu-id="69e83-122">スプレッドシートと関連するドキュメントは、次の場所にダウンロードできます。<A href="https://go.microsoft.com/fwlink/p/?linkid=212657">https://go.microsoft.com/fwlink/p/?LinkID=212657</A></span><span class="sxs-lookup"><span data-stu-id="69e83-122">You can download the spreadsheet and an associated document at: <A href="https://go.microsoft.com/fwlink/p/?linkid=212657">https://go.microsoft.com/fwlink/p/?LinkID=212657</A></span></span>



</div>

<span data-ttu-id="69e83-123">フロントエンドサーバーは、フェールオーバー時に Mobility Service をサポートするのに十分な空きメモリを必要とします。</span><span class="sxs-lookup"><span data-stu-id="69e83-123">The Front End Server needs enough available memory to support the Mobility Service in failover situations.</span></span> <span data-ttu-id="69e83-124">Mobility Service で使用するメモリ容量を計画するには、[**使用可能\\なメモリ mb** ] カウンターを使用するか、前述の式を使用して、フロントエンドサーバーで現在使用可能なメモリを監視できます。</span><span class="sxs-lookup"><span data-stu-id="69e83-124">You can monitor the current available memory on the Front End Server by using the **Memory\\Available Mbytes** counter, or by using the equation mentioned earlier, to plan for the amount of memory that you expect the Mobility Service to use.</span></span>

<span data-ttu-id="69e83-125">必要な数のモビリティユーザーを計画する場合、フロントエンドサーバーで使用可能なメモリ容量が 1500 MB 未満である場合は、Mobility Service をサポートするためにハードウェアを追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="69e83-125">If the amount of memory available on the Front End Server is lower than 1,500 MB when you plan for the expected number of mobility users, you need to add more hardware to support the Mobility Service.</span></span> <span data-ttu-id="69e83-126">詳細については、「操作」のドキュメントの「 [Lync Server 2013 でのパフォーマンスを監視する](lync-server-2013-monitoring-mobility-for-performance.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="69e83-126">For more details, see [Monitoring mobility for performance in Lync Server 2013](lync-server-2013-monitoring-mobility-for-performance.md) in the Operations documentation.</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="69e83-127">関連項目</span><span class="sxs-lookup"><span data-stu-id="69e83-127">See Also</span></span>


[<span data-ttu-id="69e83-128">Lync Server 2013 でのパフォーマンスのためのモビリティの監視</span><span class="sxs-lookup"><span data-stu-id="69e83-128">Monitoring mobility for performance in Lync Server 2013</span></span>](lync-server-2013-monitoring-mobility-for-performance.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

