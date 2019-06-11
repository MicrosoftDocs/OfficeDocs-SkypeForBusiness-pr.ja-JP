---
title: 'Lync Server 2013: Lync Server のパフォーマンスを監視する'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Monitoring Lync Server 2013 performance
ms:assetid: 2acfd720-6120-4816-a2d4-30476bd5cd0e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720910(v=OCS.15)
ms:contentKeyID: 63969592
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a9610dddfa9748b7d28dfe040a36214f3f969826
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34826746"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="monitoring-lync-server-2013-performance"></a><span data-ttu-id="bf1d3-102">Lync Server 2013 のパフォーマンスを監視する</span><span class="sxs-lookup"><span data-stu-id="bf1d3-102">Monitoring Lync Server 2013 performance</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="bf1d3-103">_**最終更新日:** 2014-05-15_</span><span class="sxs-lookup"><span data-stu-id="bf1d3-103">_**Topic Last Modified:** 2014-05-15_</span></span>

<span data-ttu-id="bf1d3-104">Lync Server 2013 のパフォーマンスは、ユーザープロファイル、システムアーキテクチャ、ソフトウェア、ハードウェアコンポーネント、ゲートウェイやテレフォニー機器などのサードパーティの統合ポイント、ネットワーク接続とパフォーマンス、Windows など、さまざまな要因によって影響を受けます。Windows オペレーティングシステムの機能に加えて、Active Directory サービスの構成とパフォーマンス。</span><span class="sxs-lookup"><span data-stu-id="bf1d3-104">Lync Server 2013 performance is affected by various factors such as user profiles, system architecture, software, hardware components, third-party integration points such as gateways and telephony equipment, network connectivity and performance, Windows Active Directory service configuration and performance in addition to the Windows operating system functionality.</span></span>

<span data-ttu-id="bf1d3-105">Lync Server 2013 の展開の中核となるのは、サーバーソフトウェアとハードウェアが実装されていることです。</span><span class="sxs-lookup"><span data-stu-id="bf1d3-105">At the core of a Lync Server 2013 deployments’ performance is the server software and hardware it is implemented on.</span></span> <span data-ttu-id="bf1d3-106">例として、フロントエンドサーバーは、予想される (短期的な) ユーザーロードに対処するために十分なハードウェアリソースを持っている必要があります。</span><span class="sxs-lookup"><span data-stu-id="bf1d3-106">As an example, a front-end server must have sufficient hardware resources to cope with the expected (short-term) user load.</span></span> <span data-ttu-id="bf1d3-107">1万ユーザーにサービスを提供するためにそれぞれのフロントエンドサーバーが必要である場合、適切に構成されたサーバーは、期待される負荷要件を満たしていることを前提として、最終的に最高のエンドユーザーエクスペリエンスを実現する必要があります。</span><span class="sxs-lookup"><span data-stu-id="bf1d3-107">If a respective front-end server is required to provide services to 10 thousand users, then an adequately configured server must meet the expected load requirements to ultimately help ensure the best possible end-user experience.</span></span>

<span data-ttu-id="bf1d3-108">このため、実装されたサーバーインフラストラクチャが、日常的な負荷のピーク要件に適したハードウェアリソースを備えているかどうかを測定することが、サーバーのパフォーマンスの監視に非常に重要です。</span><span class="sxs-lookup"><span data-stu-id="bf1d3-108">Monitoring server performance is therefore extremely important to gauge whether the implemented server infrastructure have suitable hardware resources for the day-to-day peak-load requirements.</span></span> <span data-ttu-id="bf1d3-109">サーバーのパフォーマンスを監視することにより、エンドユーザーエクスペリエンスが影響を受ける前に、管理者が是正措置を適用できるシステムボトルネックを特定することができます。</span><span class="sxs-lookup"><span data-stu-id="bf1d3-109">Monitoring server performance helps identify system bottlenecks allowing administrators to apply corrective action before the end-user experience is affected.</span></span> <span data-ttu-id="bf1d3-110">長期的なキャパシティ計画には、パフォーマンスデータを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="bf1d3-110">The performance data should be used for long-term capacity planning.</span></span>

<span data-ttu-id="bf1d3-111">記録されるすべてのパフォーマンスオブジェクトとカウンターの詳細については、「 [Lync Server 2013 を System Center Operations Manager で監視](lync-server-2013-monitoring-lync-server-with-system-center-operations-manager.md)する」にリンクされていますが、次のいくつかのパフォーマンスカウンターを使用すると、管理者が簡単に表示できます。システムパフォーマンス:</span><span class="sxs-lookup"><span data-stu-id="bf1d3-111">While detailed information on all performance objects and counters to be observed is linked to in [Monitoring Lync Server 2013 with System Center Operations Manager](lync-server-2013-monitoring-lync-server-with-system-center-operations-manager.md), some performance counters that you should follow can provide administrators a quick view of the system performance:</span></span>

  - <span data-ttu-id="bf1d3-112">フロントエンドサーバーの全体的なシステム正常性を追跡するために、まずプロセッサ\\の% プロセッサ時間を確認することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="bf1d3-112">To track overall system health of the front-end server, a good starting point is to check Processor\\% Processor Time.</span></span> <span data-ttu-id="bf1d3-113">値は常に 80% 未満である必要があります。</span><span class="sxs-lookup"><span data-stu-id="bf1d3-113">The value should always be below 80 percent.</span></span>

  - <span data-ttu-id="bf1d3-114">フロントエンドプールによって使用されるバックエンド SQL Server データベースソフトウェアインスタンスのパフォーマンスを追跡するには、次のパフォーマンスカウンターを監視します。</span><span class="sxs-lookup"><span data-stu-id="bf1d3-114">To track the performance of the back end SQL Server database software instance used by the Front End pool, monitor the following performance counters:</span></span>
    
    <span data-ttu-id="bf1d3-115">LC: USrv –00– DBStore\\usrv –002–キューの待機時間 (ミリ秒)</span><span class="sxs-lookup"><span data-stu-id="bf1d3-115">LC:USrv – 00 – DBStore\\Usrv – 002 – Queue Latency (msec)</span></span>
    
    <span data-ttu-id="bf1d3-116">LC: USrv –00– DBStore\\usrv – 0 04 –ストアドプロシージャ待ち時間 (ミリ秒)</span><span class="sxs-lookup"><span data-stu-id="bf1d3-116">LC:USrv – 00 – DBStore\\Usrv – 0 04– Sproc Latency (msec)</span></span>
    
    <span data-ttu-id="bf1d3-117">安定した状態の正常なサーバー \<には、100ミリ秒の値が表示されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="bf1d3-117">The healthy server at steady state should show \<100 ms latency values.</span></span> <span data-ttu-id="bf1d3-118">スロットルメカニズムは、待機時間が12秒に達すると、フロントエンドサーバーがバックエンドの要求の調整を開始することを意味します。</span><span class="sxs-lookup"><span data-stu-id="bf1d3-118">The throttling mechanism will engage when latency reaches 12 seconds, which means the front-end server starts throttling requests to the back end.</span></span> <span data-ttu-id="bf1d3-119">これにより、クライアントは503サーバーがビジー状態のエラーメッセージの受信を開始します。</span><span class="sxs-lookup"><span data-stu-id="bf1d3-119">This causes clients to start to receive a 503 Server too busy error message.</span></span>

  - <span data-ttu-id="bf1d3-120">フロントエンドサーバーでの処理時間を追跡するには、次のカウンターを監視します。</span><span class="sxs-lookup"><span data-stu-id="bf1d3-120">To track the processing time at the front-end server, monitor the following counter:</span></span>
    
    <span data-ttu-id="bf1d3-121">LC: SIP-07-読み込み管理\\sip-000-平均受信メッセージに時間を保持</span><span class="sxs-lookup"><span data-stu-id="bf1d3-121">LC:SIP - 07 - Load Management\\SIP - 000 - Average Holding Time For Incoming Messages</span></span>
    
    <span data-ttu-id="bf1d3-122">これは、フロントエンドサーバー上の別の調整メカニズムであり、フロントエンドの処理時間が長くなったときに開始されます。</span><span class="sxs-lookup"><span data-stu-id="bf1d3-122">This is another throttling mechanism on the front-end servers, this time starting when the processing time on the front end is high.</span></span> <span data-ttu-id="bf1d3-123">平均処理時間が6秒以上の場合、サーバーは調整モードになり、クライアント接続ごとに1つの未処理のトランザクションのみを許可します。</span><span class="sxs-lookup"><span data-stu-id="bf1d3-123">If average processing time is more than six seconds, the server goes into throttling mode and only allows one outstanding transaction per client connection.</span></span>

  - <span data-ttu-id="bf1d3-124">SQL バックエンドサーバーでメモリの問題を追跡するには、次のカウンターを監視します。</span><span class="sxs-lookup"><span data-stu-id="bf1d3-124">To track memory issues at SQL Back End Server, monitor the following counter:</span></span>
    
    <span data-ttu-id="bf1d3-125">SQL Server のバッファー\\マネージャーページの予測期間</span><span class="sxs-lookup"><span data-stu-id="bf1d3-125">SQL Server Buffer Manager\\Page life expectancy</span></span>
    
    <span data-ttu-id="bf1d3-126">低価額は、3600秒未満 (待機時間の高い書き込み/秒とチェックポイントページ/秒) で、メモリの圧迫を示しています。</span><span class="sxs-lookup"><span data-stu-id="bf1d3-126">A low value, below 3600 seconds (together with high latency writes/sec and checkpoint pages/sec) indicates memory pressure.</span></span>

<div>

## <a name="additional-counters-to-view"></a><span data-ttu-id="bf1d3-127">表示する追加カウンター</span><span class="sxs-lookup"><span data-stu-id="bf1d3-127">Additional Counters to View</span></span>

<span data-ttu-id="bf1d3-128">フロントエンドサーバーからの全体的な正常性に関する適切な指標として、いくつかの主要なカウンターがあります。</span><span class="sxs-lookup"><span data-stu-id="bf1d3-128">There are several key counters that are good indicators of overall health from the front end server.</span></span> <span data-ttu-id="bf1d3-129">これは包括的なリストではなく、根本原因を特定することを目的としていません。</span><span class="sxs-lookup"><span data-stu-id="bf1d3-129">This is not a comprehensive list and is not meant to identify root cause.</span></span> <span data-ttu-id="bf1d3-130">これらのカウンターを使って、サーバーの正常性に関するクイックチェックを実行できます。</span><span class="sxs-lookup"><span data-stu-id="bf1d3-130">These counters will let you perform a quick check on your server health.</span></span> <span data-ttu-id="bf1d3-131">これらのカウンターは、プール内の各サーバーで確認することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="bf1d3-131">We recommend verifying these counters on each of the servers in the pool.</span></span> <span data-ttu-id="bf1d3-132">サーバーが正常に動作している場合は、これらのカウンター値を理解しておくことが重要です。</span><span class="sxs-lookup"><span data-stu-id="bf1d3-132">It is important to understand what these counter values are when your server is healthy.</span></span> <span data-ttu-id="bf1d3-133">ベースラインは、ユーザーエクスペリエンスが低下したときに何が変更されたかを理解するために必要です。</span><span class="sxs-lookup"><span data-stu-id="bf1d3-133">A baseline is required to understand what changed when the user experience is degraded.</span></span>

<span data-ttu-id="bf1d3-134">フロントエンドサーバーは、システムの他の場所にあるボトルネックによって発生する可能性のある問題を示すことができます。</span><span class="sxs-lookup"><span data-stu-id="bf1d3-134">The front-end server can indicate issues that may be caused by bottlenecks elsewhere in the system.</span></span> <span data-ttu-id="bf1d3-135">これは、システムの正常性を確認するのに最適な場所です。</span><span class="sxs-lookup"><span data-stu-id="bf1d3-135">This means that it is the best place to start when looking at overall system health.</span></span>

<span data-ttu-id="bf1d3-136">最初に確認する2つの追加カウンターは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="bf1d3-136">Two additional counters to review first are as follows:</span></span>

<span data-ttu-id="bf1d3-137">LC: USrv-00-DBStore\\usrv-002-キューの待機時間 (ミリ秒)</span><span class="sxs-lookup"><span data-stu-id="bf1d3-137">LC:USrv-00-DBStore\\Usrv-002-Queue Latency (msec)</span></span>

<span data-ttu-id="bf1d3-138">LC: USrv-00-DBStore\\usrv-004-ストアドプロシージャ待ち時間 (ミリ秒)</span><span class="sxs-lookup"><span data-stu-id="bf1d3-138">LC:USrv-00-DBStore\\Usrv-004-Sproc Latency (msec)</span></span>

<span data-ttu-id="bf1d3-139">Queue latency カウンターは、要求がキューでバックエンドに費やした時間を表し、"ストアドプロシージャ待機時間" は、バックエンドが要求を処理するのにかかった時間を表します。</span><span class="sxs-lookup"><span data-stu-id="bf1d3-139">The queue latency counter represents the time that a request spent in the queue to the back end and the Sproc latency represents the time that it took for the back end to process the request.</span></span> <span data-ttu-id="bf1d3-140">何らかの理由で、バックエンドのディスク、メモリ、ネットワーク、プロセッサが問題となっている場合は、キューの待機時間カウンターは高くなります。</span><span class="sxs-lookup"><span data-stu-id="bf1d3-140">If, for any reason, disk, memory, network, and processor on the back end are in trouble, the queue latency counter will be high.</span></span>

<span data-ttu-id="bf1d3-141">また、フロントエンドとバックエンドの間に高いネットワーク待ち時間がある場合にも高い可能性があります。</span><span class="sxs-lookup"><span data-stu-id="bf1d3-141">It can also be high if there is high network latency between the front end and the back end.</span></span> <span data-ttu-id="bf1d3-142">許容されるキューの待ち時間はどのようなものですか?</span><span class="sxs-lookup"><span data-stu-id="bf1d3-142">So what is acceptable queue latency?</span></span>

<span data-ttu-id="bf1d3-143">フロントエンドサーバーは、12秒以内にバックエンドサーバーへの要求の調整を開始します。</span><span class="sxs-lookup"><span data-stu-id="bf1d3-143">At 12 seconds, the Front End Servers start throttling requests to the Back End Servers.</span></span> <span data-ttu-id="bf1d3-144">これは、サーバーがビジー状態になることを意味します–503エラーはクライアントに返されます。</span><span class="sxs-lookup"><span data-stu-id="bf1d3-144">This means the servers start returning Server too busy – 503 errors to the clients.</span></span> <span data-ttu-id="bf1d3-145">正常なサーバーは、安定した状態で100ミリ秒未満の DBStore キューの待ち時間を超えないようにする必要があります。ただし、サーバーがオンラインになり、ユーザーが同時にログインしている場合は、そのカウンターは非常に大きくなる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="bf1d3-145">A healthy server should have less than 100 msec DBStore queue latencies at steady state, but during times where the server has just come online and users are all logging in at the same time, that counter can be very high and you may even see it hit multiple seconds.</span></span>

<span data-ttu-id="bf1d3-146">複数のフロントエンドサーバーと、"最小接続数" に構成されているロードバランサーを使用して展開されたプールを持つ負荷分散構成がある場合があります。</span><span class="sxs-lookup"><span data-stu-id="bf1d3-146">You may have a load-balanced configuration, where you have a pool deployed with multiple front-end servers and a load balancer that is configured for "least number of connections."</span></span> <span data-ttu-id="bf1d3-147">この場合、1つのフロントエンドサーバーが再起動されると、再接続しようとしているすべてのユーザーが、他のプールメンバーと比べて接続数が少なくなります。</span><span class="sxs-lookup"><span data-stu-id="bf1d3-147">In this case, if one front-end server is restarted, then all users who attempt to reconnect will be pointed to the restarted server, because that server will have fewer connections compared to the other pool members.</span></span> <span data-ttu-id="bf1d3-148">このとき、他のプールメンバーではなく、各フロントエンドサーバーが過負荷になることがあります。</span><span class="sxs-lookup"><span data-stu-id="bf1d3-148">During this time, the respective front-end server may be overloaded while the other pool members are not.</span></span>

<span data-ttu-id="bf1d3-149">ユーザーが同時にサーバーに接続していないため、パフォーマンスへの影響を抑えるために、時間の経過と共にメンテナンスを実行することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="bf1d3-149">We recommend that you perform maintenance during off-hours to reduce the performance affect as users will not all be competing to connect to the server at the same time.</span></span>

<span data-ttu-id="bf1d3-150">上記の2つのパフォーマンスカウンターが大きい場合は、SQL バックエンドサーバーである可能性が最も高いと考えられます。</span><span class="sxs-lookup"><span data-stu-id="bf1d3-150">If the previous two performance counters are high, the most likely bottleneck is the SQL Back End Server.</span></span> <span data-ttu-id="bf1d3-151">確認する次のコンポーネントは、次のようになります。</span><span class="sxs-lookup"><span data-stu-id="bf1d3-151">The next components to confirm are as follows:</span></span>

  - <span data-ttu-id="bf1d3-152">SQL Server の CPU が高すぎませんか?</span><span class="sxs-lookup"><span data-stu-id="bf1d3-152">Is the SQL Server CPU too high?</span></span> <span data-ttu-id="bf1d3-153">たとえば、80パーセントより大きいかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="bf1d3-153">For example, is it greater than 80 percent?</span></span>

  - <span data-ttu-id="bf1d3-154">ディスク待ち時間は高ですか?</span><span class="sxs-lookup"><span data-stu-id="bf1d3-154">Is the disk latency high?</span></span>

<span data-ttu-id="bf1d3-155">理想的には、RTC と RTCDYN の両方のデータベースをメモリに保持するための十分な RAM があります。</span><span class="sxs-lookup"><span data-stu-id="bf1d3-155">In an ideal world, you have enough RAM to have both the RTC and RTCDYN databases in memory.</span></span> <span data-ttu-id="bf1d3-156">その後、サーバーがディスクにアクセスする理由は、ログファイルに書き込みを行い、データベースにフラッシュすることだけです。</span><span class="sxs-lookup"><span data-stu-id="bf1d3-156">Then, the only reason the server would be accessing the disk, is to write to the log files and flush to the databases.</span></span> <span data-ttu-id="bf1d3-157">このテストでは、10万のユーザー展開には 12 GB の RAM が十分であることが示されています。</span><span class="sxs-lookup"><span data-stu-id="bf1d3-157">Tests have shown that 12 GB of RAM is sufficient for 100 thousand user deployments.</span></span> <span data-ttu-id="bf1d3-158">これは、RTC と RTCDYN データベースの合計サイズが 12 GB 未満であることを前提としています。</span><span class="sxs-lookup"><span data-stu-id="bf1d3-158">This assumes that the RTC and RTCDYN databases size totals less than 12 GB.</span></span> <span data-ttu-id="bf1d3-159">データベースがそれよりも大きい場合は、メモリを追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="bf1d3-159">If your databases are larger than that, then you may need additional memory.</span></span>

<span data-ttu-id="bf1d3-160">Sql Server バッファーマネージャーのページ寿命の予測のパフォーマンスカウンターを確認すると、SQL Server で追加の RAM が必要かどうかを判断できます。</span><span class="sxs-lookup"><span data-stu-id="bf1d3-160">You can determine whether your SQL Server requires additional RAM by reviewing the SQL Server Buffer Manager page life expectancy performance counter.</span></span> <span data-ttu-id="bf1d3-161">3600より小さい値は、メモリの負荷を示します。</span><span class="sxs-lookup"><span data-stu-id="bf1d3-161">A value less than 3,600 indicates memory pressure.</span></span> <span data-ttu-id="bf1d3-162">また、SQL Server はデータベースへの書き込みのみを行う必要があるため、十分なメモリがある場合は、データベースドライブに対する読み取りはほとんど必要ありません。</span><span class="sxs-lookup"><span data-stu-id="bf1d3-162">You should also see little to no reads on your database drive if you have sufficient memory because SQL Server should only be writing to the database.</span></span>

<span data-ttu-id="bf1d3-163">サーバーの処理時間が長い場合は、Lync Server 2013 フロントエンドサーバーに追加の調整メカニズムが用意されています。</span><span class="sxs-lookup"><span data-stu-id="bf1d3-163">There is an additional throttling mechanism in a Lync Server 2013 Front End Server that starts if the server processing time is high.</span></span> <span data-ttu-id="bf1d3-164">DBStore の待機時間の調整は、SQL Server への待機時間が長い場合にのみ有効になります。</span><span class="sxs-lookup"><span data-stu-id="bf1d3-164">The DBStore latency throttling is only enabled if the latency to the SQL Server is high.</span></span> <span data-ttu-id="bf1d3-165">このような調整が有効になる1つの例は、フロントエンドサーバーが CPU にバインドされている場合です。</span><span class="sxs-lookup"><span data-stu-id="bf1d3-165">One example in which such throttling is enabled is if the front-end server is CPU-bound.</span></span>

<span data-ttu-id="bf1d3-166">平均処理時間 **(LC: sip-07-[読み込み\\管理 sip-000-平均受信メッセージ])** が6秒を超える場合、サーバーは調整モードになり、ユーザーには1つの未処理のトランザクションが含まれます。クライアント接続。</span><span class="sxs-lookup"><span data-stu-id="bf1d3-166">If the average processing time **(LC:SIP-07-Load Management\\SIP-000-Average Holding Time For Incoming Messages)** on the server exceeds six seconds, then the server goes into throttling mode and only gives users one outstanding transaction per client connection.</span></span> <span data-ttu-id="bf1d3-167">処理時間が3秒に低下すると、サーバーは調整モードを終了し、クライアント接続あたり最大20個の未処理トランザクションをユーザーに提供します。</span><span class="sxs-lookup"><span data-stu-id="bf1d3-167">Once the processing time drops to three seconds, then the server drops out of throttling mode and gives users up to 20 outstanding transactions per client connection.</span></span> <span data-ttu-id="bf1d3-168">特定の接続のトランザクション数が上記のしきい値を超えている場合、接続はフロー制御としてマークされます。</span><span class="sxs-lookup"><span data-stu-id="bf1d3-168">Whenever the number of transactions on a specific connection exceeds the threshold above, the connection is marked as flow controlled.</span></span> <span data-ttu-id="bf1d3-169">結果としてサーバーでは、受信は何も送信されず、 **LC: SIP-01\\-ピアフロー制御接続**カウンターがインクリメントされます。</span><span class="sxs-lookup"><span data-stu-id="bf1d3-169">The result is the server does not post any receives on it, and the **LC:SIP-01-Peers\\Flow Controlled Connections** counter is incremented.</span></span> <span data-ttu-id="bf1d3-170">接続がフロー制御された状態の1分以上続く場合は、サーバーによって閉じられます。</span><span class="sxs-lookup"><span data-stu-id="bf1d3-170">If a connection stays in a flow-controlled state for more than one minute, then the server closes it.</span></span> <span data-ttu-id="bf1d3-171">これは、それほど簡単ではありません。</span><span class="sxs-lookup"><span data-stu-id="bf1d3-171">It does so lazily.</span></span> <span data-ttu-id="bf1d3-172">接続を確認する機会がある場合は、時間がかかりすぎているかどうかを判断し、1分以上ある場合はそれを閉じます。</span><span class="sxs-lookup"><span data-stu-id="bf1d3-172">When it has an opportunity to check the connection, it determines whether it was throttled for too long and closes it if it has more than one minute.</span></span>

<span data-ttu-id="bf1d3-173">これらは2つの調整メカニズムであり、サーバーが実行している調整がある場合はそれを要約する1つのパフォーマンスカウンターがあります。</span><span class="sxs-lookup"><span data-stu-id="bf1d3-173">These are the two throttling mechanisms and there is one performance counter that summarizes what, if any, throttling the server is performing.</span></span>

<span data-ttu-id="bf1d3-174">**LC: SIP-04-応答\\SIP-053-ローカル503応答/秒**</span><span class="sxs-lookup"><span data-stu-id="bf1d3-174">**LC:SIP-04-Responses\\SIP-053-Local 503 Responses/sec**</span></span>

  - <span data-ttu-id="bf1d3-175">前のカウンターの "Local" という用語は、ローカルで生成された応答を指します。</span><span class="sxs-lookup"><span data-stu-id="bf1d3-175">The term "Local" in the previous counter refers to locally generated responses.</span></span>

  - <span data-ttu-id="bf1d3-176">503コードは、使用できないサーバー (正常なサーバーに503コードが表示されない) に対応しています。</span><span class="sxs-lookup"><span data-stu-id="bf1d3-176">The 503 code corresponds to server unavailable—where you should not see any 503 codes on a healthy server.</span></span> <span data-ttu-id="bf1d3-177">サーバーがオンラインになるまでの期間中に、503コードが表示されることがあります。</span><span class="sxs-lookup"><span data-stu-id="bf1d3-177">During the period after a server is just brought online, you may see some 503 codes.</span></span> <span data-ttu-id="bf1d3-178">すべてのユーザーが再びサインインしたときに、サーバーが安定した状態に戻ると、追加の503コードは表示されません。</span><span class="sxs-lookup"><span data-stu-id="bf1d3-178">When all of the users sign back in and the server returns to a stable state, there should no additional 503 codes.</span></span>

<span data-ttu-id="bf1d3-179">**LC: SIP-04-応答\\SIP-074-ローカル504応答/秒**</span><span class="sxs-lookup"><span data-stu-id="bf1d3-179">**LC:SIP-04-Responses\\SIP-074-Local 504 Responses/sec**</span></span>

<span data-ttu-id="bf1d3-180">このパフォーマンスカウンターは、他のサーバーとの接続の問題を示し、接続中の接続の失敗や遅延を示します。</span><span class="sxs-lookup"><span data-stu-id="bf1d3-180">This performance counter indicates connectivity issues with other servers and it can indicate failures to connect or delays in connecting.</span></span> <span data-ttu-id="bf1d3-181">504エラーが表示される場合は、次のパフォーマンスカウンターをチェックする必要があります。</span><span class="sxs-lookup"><span data-stu-id="bf1d3-181">If you are seeing 504 errors then the following performance counter should be checked.</span></span>

<span data-ttu-id="bf1d3-182">**LC: SIP-01-ピア\\SIP-017-未処理の送信**</span><span class="sxs-lookup"><span data-stu-id="bf1d3-182">**LC:SIP-01-Peers\\SIP-017-Sends Outstanding**</span></span>

<span data-ttu-id="bf1d3-183">このカウンターは、キューに入れられた発信要求と返信の数を示します。</span><span class="sxs-lookup"><span data-stu-id="bf1d3-183">This counter indicates the number of outgoing queued requests and responses.</span></span> <span data-ttu-id="bf1d3-184">このカウンターが大きい場合、問題はローカルサーバーではない可能性が高いと考えられます。</span><span class="sxs-lookup"><span data-stu-id="bf1d3-184">If this counter is high then the issue is most likely not on the local server.</span></span> <span data-ttu-id="bf1d3-185">ネットワーク待ち時間の問題がある場合は、このカウンターを高くすることができます。</span><span class="sxs-lookup"><span data-stu-id="bf1d3-185">Note that this counter can be high if there are network latency issues.</span></span> <span data-ttu-id="bf1d3-186">また、ローカルネットワークアダプターで問題が発生している可能性もありますが、リモートサーバー上の問題が原因である可能性が高くなります。</span><span class="sxs-lookup"><span data-stu-id="bf1d3-186">It could also indicate issues with the local network adapter, but is more likely caused by an issue on a remote server.</span></span> <span data-ttu-id="bf1d3-187">このカウンターは、通信しようとしているプールが過負荷状態になっているときに、ディレクターサーバーで高い可能性が高いと考えられます。</span><span class="sxs-lookup"><span data-stu-id="bf1d3-187">This counter would most likely be high on a Director server when the pool it is trying to communicate with is overloaded.</span></span> <span data-ttu-id="bf1d3-188">このカウンターのキーは、合計だけでなく、インスタンスを確認することです。</span><span class="sxs-lookup"><span data-stu-id="bf1d3-188">The key with this counter is to look at the instances, not just the total.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

