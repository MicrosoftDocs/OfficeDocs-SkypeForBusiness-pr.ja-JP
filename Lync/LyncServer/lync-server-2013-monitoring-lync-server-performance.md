---
title: 'Lync Server 2013: Lync Server のパフォーマンスの監視'
description: 'Lync Server 2013: Lync Server のパフォーマンスを監視します。'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Monitoring Lync Server 2013 performance
ms:assetid: 2acfd720-6120-4816-a2d4-30476bd5cd0e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720910(v=OCS.15)
ms:contentKeyID: 63969592
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: efe63a881c9db105fc36a1ccd0b0fdc15086a36f
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48548103"
---
# <a name="monitoring-lync-server-2013-performance"></a><span data-ttu-id="079d1-103">Lync Server 2013 のパフォーマンスの監視</span><span class="sxs-lookup"><span data-stu-id="079d1-103">Monitoring Lync Server 2013 performance</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="079d1-104">_**トピックの最終更新日:** 2014-05-15_</span><span class="sxs-lookup"><span data-stu-id="079d1-104">_**Topic Last Modified:** 2014-05-15_</span></span>

<span data-ttu-id="079d1-105">Lync Server 2013 のパフォーマンスは、ユーザープロファイル、システムアーキテクチャ、ソフトウェア、ハードウェアコンポーネント、ゲートウェイやテレフォニー機器などのサードパーティの統合ポイント、ネットワーク接続とパフォーマンス、windows Active Directory サービスの構成、パフォーマンス、windows オペレーティングシステムの機能に加えて、さまざまな要因の影響を受けます。</span><span class="sxs-lookup"><span data-stu-id="079d1-105">Lync Server 2013 performance is affected by various factors such as user profiles, system architecture, software, hardware components, third-party integration points such as gateways and telephony equipment, network connectivity and performance, Windows Active Directory service configuration and performance in addition to the Windows operating system functionality.</span></span>

<span data-ttu-id="079d1-106">Lync Server 2013 の展開の中核となるのは、実装されているサーバーソフトウェアとハードウェアです。</span><span class="sxs-lookup"><span data-stu-id="079d1-106">At the core of a Lync Server 2013 deployments’ performance is the server software and hardware it is implemented on.</span></span> <span data-ttu-id="079d1-107">一例として、フロントエンドサーバーは、予想される (短期的な) ユーザー負荷に対処するのに十分なハードウェアリソースを備えている必要があります。</span><span class="sxs-lookup"><span data-stu-id="079d1-107">As an example, a front-end server must have sufficient hardware resources to cope with the expected (short-term) user load.</span></span> <span data-ttu-id="079d1-108">サービスを1万ユーザーに提供するためにそれぞれのフロントエンドサーバーが必要な場合は、適切に構成されたサーバーが予想される負荷要件を満たしている必要があります。最終的には、エンドユーザーの最高のパフォーマンスを実現するために役立ちます。</span><span class="sxs-lookup"><span data-stu-id="079d1-108">If a respective front-end server is required to provide services to 10 thousand users, then an adequately configured server must meet the expected load requirements to ultimately help ensure the best possible end-user experience.</span></span>

<span data-ttu-id="079d1-109">そのため、サーバーのパフォーマンスを監視することは、実装されたサーバーインフラストラクチャに、日常のピーク時の負荷要件に適したハードウェアリソースがあるかどうかを測定することが非常に重要です。</span><span class="sxs-lookup"><span data-stu-id="079d1-109">Monitoring server performance is therefore extremely important to gauge whether the implemented server infrastructure have suitable hardware resources for the day-to-day peak-load requirements.</span></span> <span data-ttu-id="079d1-110">監視サーバーのパフォーマンスは、エンドユーザーの操作が影響を受ける前に、管理者が是正措置を適用できるシステムのボトルネックを特定するのに便利です。</span><span class="sxs-lookup"><span data-stu-id="079d1-110">Monitoring server performance helps identify system bottlenecks allowing administrators to apply corrective action before the end-user experience is affected.</span></span> <span data-ttu-id="079d1-111">パフォーマンスデータは、長期の容量計画に使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="079d1-111">The performance data should be used for long-term capacity planning.</span></span>

<span data-ttu-id="079d1-112">[System Center Operations Manager を使用した Lync Server 2013 の監視](lync-server-2013-monitoring-lync-server-with-system-center-operations-manager.md)では、すべてのパフォーマンスオブジェクトとカウンターの詳細情報がリンクされていますが、以下のパフォーマンスカウンターを使用すると、管理者はシステムのパフォーマンスを簡単に確認できます。</span><span class="sxs-lookup"><span data-stu-id="079d1-112">While detailed information on all performance objects and counters to be observed is linked to in [Monitoring Lync Server 2013 with System Center Operations Manager](lync-server-2013-monitoring-lync-server-with-system-center-operations-manager.md), some performance counters that you should follow can provide administrators a quick view of the system performance:</span></span>

  - <span data-ttu-id="079d1-113">フロントエンドサーバーのシステム全体の正常性を追跡するには、まずプロセッサの% processor Time をチェックすることをお勧めし \\ ます。</span><span class="sxs-lookup"><span data-stu-id="079d1-113">To track overall system health of the front-end server, a good starting point is to check Processor\\% Processor Time.</span></span> <span data-ttu-id="079d1-114">値は常に80% 未満である必要があります。</span><span class="sxs-lookup"><span data-stu-id="079d1-114">The value should always be below 80 percent.</span></span>

  - <span data-ttu-id="079d1-115">フロントエンドプールで使用されるバックエンド SQL Server データベースソフトウェアインスタンスのパフォーマンスを追跡するには、次のパフォーマンスカウンターを監視します。</span><span class="sxs-lookup"><span data-stu-id="079d1-115">To track the performance of the back end SQL Server database software instance used by the Front End pool, monitor the following performance counters:</span></span>
    
    <span data-ttu-id="079d1-116">LC: USrv –00– DBStore \\ usrv –002– Queue Latency (ミリ秒)</span><span class="sxs-lookup"><span data-stu-id="079d1-116">LC:USrv – 00 – DBStore\\Usrv – 002 – Queue Latency (msec)</span></span>
    
    <span data-ttu-id="079d1-117">LC: USrv –00– DBStore \\ usrv – 0 04-「ストアドプロシージャ待機時間 (ミリ秒)」</span><span class="sxs-lookup"><span data-stu-id="079d1-117">LC:USrv – 00 – DBStore\\Usrv – 0 04– Sproc Latency (msec)</span></span>
    
    <span data-ttu-id="079d1-118">正常なサーバーが安定した状態で、100ミリ秒の待ち時間の値を表示する必要があり \< ます。</span><span class="sxs-lookup"><span data-stu-id="079d1-118">The healthy server at steady state should show \<100 ms latency values.</span></span> <span data-ttu-id="079d1-119">遅延が12秒に達したときに調整メカニズムによって処理されます。これは、フロントエンドサーバーがバックエンドに対する要求の調整を開始することを意味します。</span><span class="sxs-lookup"><span data-stu-id="079d1-119">The throttling mechanism will engage when latency reaches 12 seconds, which means the front-end server starts throttling requests to the back end.</span></span> <span data-ttu-id="079d1-120">これにより、クライアントは 503 Server のビジー状態のエラーメッセージの受信を開始します。</span><span class="sxs-lookup"><span data-stu-id="079d1-120">This causes clients to start to receive a 503 Server too busy error message.</span></span>

  - <span data-ttu-id="079d1-121">フロントエンドサーバーで処理時間を追跡するには、次のカウンターを監視します。</span><span class="sxs-lookup"><span data-stu-id="079d1-121">To track the processing time at the front-end server, monitor the following counter:</span></span>
    
    <span data-ttu-id="079d1-122">LC: SIP-07-Load Management \\ sip-000-受信メッセージを保持する時間の平均</span><span class="sxs-lookup"><span data-stu-id="079d1-122">LC:SIP - 07 - Load Management\\SIP - 000 - Average Holding Time For Incoming Messages</span></span>
    
    <span data-ttu-id="079d1-123">これはフロントエンドサーバー上の別の調整メカニズムなので、この時点では、フロントエンドの処理時間が長くなります。</span><span class="sxs-lookup"><span data-stu-id="079d1-123">This is another throttling mechanism on the front-end servers, this time starting when the processing time on the front end is high.</span></span> <span data-ttu-id="079d1-124">平均処理時間が6秒を超えている場合、サーバーは調整モードに入り、クライアント接続ごとに1つの未処理のトランザクションのみが許可されます。</span><span class="sxs-lookup"><span data-stu-id="079d1-124">If average processing time is more than six seconds, the server goes into throttling mode and only allows one outstanding transaction per client connection.</span></span>

  - <span data-ttu-id="079d1-125">SQL バックエンドサーバーでメモリの問題を追跡するには、次のカウンターを監視します。</span><span class="sxs-lookup"><span data-stu-id="079d1-125">To track memory issues at SQL Back End Server, monitor the following counter:</span></span>
    
    <span data-ttu-id="079d1-126">SQL Server バッファーマネージャーの \\ ページ寿命の予測</span><span class="sxs-lookup"><span data-stu-id="079d1-126">SQL Server Buffer Manager\\Page life expectancy</span></span>
    
    <span data-ttu-id="079d1-127">最小値 (3600 秒未満) (高遅延書き込み/秒およびチェックポイントページ/秒) は、メモリの負荷を示します。</span><span class="sxs-lookup"><span data-stu-id="079d1-127">A low value, below 3600 seconds (together with high latency writes/sec and checkpoint pages/sec) indicates memory pressure.</span></span>

<div>

## <a name="additional-counters-to-view"></a><span data-ttu-id="079d1-128">表示する追加カウンター</span><span class="sxs-lookup"><span data-stu-id="079d1-128">Additional Counters to View</span></span>

<span data-ttu-id="079d1-129">フロントエンドサーバーからの全体的な状態に関する適切な指標として、いくつかの主要なカウンターがあります。</span><span class="sxs-lookup"><span data-stu-id="079d1-129">There are several key counters that are good indicators of overall health from the front end server.</span></span> <span data-ttu-id="079d1-130">これは包括的なリストではなく、根本原因を特定することを目的としたものではありません。</span><span class="sxs-lookup"><span data-stu-id="079d1-130">This is not a comprehensive list and is not meant to identify root cause.</span></span> <span data-ttu-id="079d1-131">これらのカウンターを使用すると、サーバーの正常性を簡単に確認できます。</span><span class="sxs-lookup"><span data-stu-id="079d1-131">These counters will let you perform a quick check on your server health.</span></span> <span data-ttu-id="079d1-132">プール内の各サーバーでこれらのカウンターを確認することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="079d1-132">We recommend verifying these counters on each of the servers in the pool.</span></span> <span data-ttu-id="079d1-133">サーバーが正常な状態になっている場合、これらのカウンターの値を理解しておくことが重要です。</span><span class="sxs-lookup"><span data-stu-id="079d1-133">It is important to understand what these counter values are when your server is healthy.</span></span> <span data-ttu-id="079d1-134">ユーザーの作業が低下したときに変更された内容を理解するには、ベースラインが必要です。</span><span class="sxs-lookup"><span data-stu-id="079d1-134">A baseline is required to understand what changed when the user experience is degraded.</span></span>

<span data-ttu-id="079d1-135">フロントエンドサーバーは、システム内の他の場所に存在するボトルネックによって発生する可能性のある問題を示すことができます。</span><span class="sxs-lookup"><span data-stu-id="079d1-135">The front-end server can indicate issues that may be caused by bottlenecks elsewhere in the system.</span></span> <span data-ttu-id="079d1-136">これは、システム全体の正常性を確認するときに、最適な開始点となることを意味します。</span><span class="sxs-lookup"><span data-stu-id="079d1-136">This means that it is the best place to start when looking at overall system health.</span></span>

<span data-ttu-id="079d1-137">最初に確認する必要がある2つのカウンターは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="079d1-137">Two additional counters to review first are as follows:</span></span>

<span data-ttu-id="079d1-138">LC: USrv-00-DBStore \\ usrv-002-キュー待機時間 (ミリ秒)</span><span class="sxs-lookup"><span data-stu-id="079d1-138">LC:USrv-00-DBStore\\Usrv-002-Queue Latency (msec)</span></span>

<span data-ttu-id="079d1-139">LC: USrv-00-DBStore \\ usrv-004-ストアドプロシージャ待機時間 (ミリ秒)</span><span class="sxs-lookup"><span data-stu-id="079d1-139">LC:USrv-00-DBStore\\Usrv-004-Sproc Latency (msec)</span></span>

<span data-ttu-id="079d1-140">Queue latency カウンターは、要求がバックエンドに対してキューにかかった時間を表し、ストアドプロシージャの待機時間は、バックエンドが要求を処理するのにかかった時間を表します。</span><span class="sxs-lookup"><span data-stu-id="079d1-140">The queue latency counter represents the time that a request spent in the queue to the back end and the Sproc latency represents the time that it took for the back end to process the request.</span></span> <span data-ttu-id="079d1-141">何らかの理由で、バックエンドのディスク、メモリ、ネットワーク、およびプロセッサが問題になっている場合、キューの待機時間カウンターは高くなります。</span><span class="sxs-lookup"><span data-stu-id="079d1-141">If, for any reason, disk, memory, network, and processor on the back end are in trouble, the queue latency counter will be high.</span></span>

<span data-ttu-id="079d1-142">また、フロントエンドとバックエンドの間のネットワークの待ち時間が多い場合にも高いことがあります。</span><span class="sxs-lookup"><span data-stu-id="079d1-142">It can also be high if there is high network latency between the front end and the back end.</span></span> <span data-ttu-id="079d1-143">そのため、許容できるキューの遅延は何ですか。</span><span class="sxs-lookup"><span data-stu-id="079d1-143">So what is acceptable queue latency?</span></span>

<span data-ttu-id="079d1-144">フロントエンドサーバーは、12秒以内にバックエンドサーバーへの要求の調整を開始します。</span><span class="sxs-lookup"><span data-stu-id="079d1-144">At 12 seconds, the Front End Servers start throttling requests to the Back End Servers.</span></span> <span data-ttu-id="079d1-145">これは、サーバーがビジー状態–503エラーをクライアントに返し始め始めることを意味します。</span><span class="sxs-lookup"><span data-stu-id="079d1-145">This means the servers start returning Server too busy – 503 errors to the clients.</span></span> <span data-ttu-id="079d1-146">正常なサーバーでは、安定した状態では100ミリ秒未満の DBStore キューの待ち時間が発生していますが、サーバーがオンラインになり、ユーザーがすべて同時にログインしている間は、このカウンターが非常に大きくなり、ヒット数が複数になっている可能性があります。</span><span class="sxs-lookup"><span data-stu-id="079d1-146">A healthy server should have less than 100 msec DBStore queue latencies at steady state, but during times where the server has just come online and users are all logging in at the same time, that counter can be very high and you may even see it hit multiple seconds.</span></span>

<span data-ttu-id="079d1-147">負荷分散された構成では、複数のフロントエンドサーバーでプールが展開されており、"最小数の接続" 用に構成されたロードバランサーを使用している場合があります。</span><span class="sxs-lookup"><span data-stu-id="079d1-147">You may have a load-balanced configuration, where you have a pool deployed with multiple front-end servers and a load balancer that is configured for "least number of connections."</span></span> <span data-ttu-id="079d1-148">この場合、1台のフロントエンドサーバーを再起動すると、再接続を試行するすべてのユーザーが、他のプールメンバーと比較して接続数が少なくなるため、再起動されたサーバーがポイントされます。</span><span class="sxs-lookup"><span data-stu-id="079d1-148">In this case, if one front-end server is restarted, then all users who attempt to reconnect will be pointed to the restarted server, because that server will have fewer connections compared to the other pool members.</span></span> <span data-ttu-id="079d1-149">この間、それぞれのフロントエンドサーバーが過負荷になることがありますが、他のプールメンバーは過負荷になっているとは限りません。</span><span class="sxs-lookup"><span data-stu-id="079d1-149">During this time, the respective front-end server may be overloaded while the other pool members are not.</span></span>

<span data-ttu-id="079d1-150">ユーザーがサーバーに同時に接続することがないため、パフォーマンスへの影響を軽減するために、時間の経過とともにメンテナンスを実行することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="079d1-150">We recommend that you perform maintenance during off-hours to reduce the performance affect as users will not all be competing to connect to the server at the same time.</span></span>

<span data-ttu-id="079d1-151">前の2つのパフォーマンスカウンターが高い場合は、SQL バックエンドサーバーがボトルネックとなる可能性が高くなります。</span><span class="sxs-lookup"><span data-stu-id="079d1-151">If the previous two performance counters are high, the most likely bottleneck is the SQL Back End Server.</span></span> <span data-ttu-id="079d1-152">確認する次のコンポーネントは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="079d1-152">The next components to confirm are as follows:</span></span>

  - <span data-ttu-id="079d1-153">SQL Server CPU が高すぎませんか?</span><span class="sxs-lookup"><span data-stu-id="079d1-153">Is the SQL Server CPU too high?</span></span> <span data-ttu-id="079d1-154">たとえば、80% より大きいかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="079d1-154">For example, is it greater than 80 percent?</span></span>

  - <span data-ttu-id="079d1-155">ディスク待機時間は長くなりますか?</span><span class="sxs-lookup"><span data-stu-id="079d1-155">Is the disk latency high?</span></span>

<span data-ttu-id="079d1-156">理想的には、RTC データベースと RTCDYN データベースの両方をメモリに格納するのに十分な RAM を用意しています。</span><span class="sxs-lookup"><span data-stu-id="079d1-156">In an ideal world, you have enough RAM to have both the RTC and RTCDYN databases in memory.</span></span> <span data-ttu-id="079d1-157">その後、サーバーがディスクにアクセスする唯一の理由は、ログファイルに書き込み、データベースにフラッシュすることです。</span><span class="sxs-lookup"><span data-stu-id="079d1-157">Then, the only reason the server would be accessing the disk, is to write to the log files and flush to the databases.</span></span> <span data-ttu-id="079d1-158">テストでは、10万ユーザーの展開に 12 GB の RAM があれば十分であることが示されています。</span><span class="sxs-lookup"><span data-stu-id="079d1-158">Tests have shown that 12 GB of RAM is sufficient for 100 thousand user deployments.</span></span> <span data-ttu-id="079d1-159">これは、RTC および RTCDYN データベースのサイズ合計が 12 GB 未満であることを前提としています。</span><span class="sxs-lookup"><span data-stu-id="079d1-159">This assumes that the RTC and RTCDYN databases size totals less than 12 GB.</span></span> <span data-ttu-id="079d1-160">データベースがこれより大きい場合は、追加のメモリが必要になることがあります。</span><span class="sxs-lookup"><span data-stu-id="079d1-160">If your databases are larger than that, then you may need additional memory.</span></span>

<span data-ttu-id="079d1-161">Sql server バッファーマネージャーページの寿命のパフォーマンスカウンターを調べることによって、SQL Server が追加の RAM を必要とするかどうかを判断できます。</span><span class="sxs-lookup"><span data-stu-id="079d1-161">You can determine whether your SQL Server requires additional RAM by reviewing the SQL Server Buffer Manager page life expectancy performance counter.</span></span> <span data-ttu-id="079d1-162">3600未満の値は、メモリの負荷を示します。</span><span class="sxs-lookup"><span data-stu-id="079d1-162">A value less than 3,600 indicates memory pressure.</span></span> <span data-ttu-id="079d1-163">SQL Server はデータベースへの書き込みのみを行う必要があるため、十分なメモリがある場合は、データベースドライブに対する読み取りがほとんどないことを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="079d1-163">You should also see little to no reads on your database drive if you have sufficient memory because SQL Server should only be writing to the database.</span></span>

<span data-ttu-id="079d1-164">サーバーの処理時間が長くなった場合に開始する Lync Server 2013 のフロントエンドサーバーには、追加の調整メカニズムがあります。</span><span class="sxs-lookup"><span data-stu-id="079d1-164">There is an additional throttling mechanism in a Lync Server 2013 Front End Server that starts if the server processing time is high.</span></span> <span data-ttu-id="079d1-165">DBStore の待機時間調整は、SQL Server の待機時間が長い場合にのみ有効になります。</span><span class="sxs-lookup"><span data-stu-id="079d1-165">The DBStore latency throttling is only enabled if the latency to the SQL Server is high.</span></span> <span data-ttu-id="079d1-166">このような調整が有効になる1つの例として、フロントエンドサーバーが CPU にバインドされている場合が挙げられます。</span><span class="sxs-lookup"><span data-stu-id="079d1-166">One example in which such throttling is enabled is if the front-end server is CPU-bound.</span></span>

<span data-ttu-id="079d1-167">サーバー上で、サーバー上の平均処理時間 **(LC: sip-07-負荷管理 \\ sip** -2) が6秒を超えた場合、サーバーは調整モードに入り、クライアント接続ごとに1つの未処理のトランザクションのみをユーザーに提供します。</span><span class="sxs-lookup"><span data-stu-id="079d1-167">If the average processing time **(LC:SIP-07-Load Management\\SIP-000-Average Holding Time For Incoming Messages)** on the server exceeds six seconds, then the server goes into throttling mode and only gives users one outstanding transaction per client connection.</span></span> <span data-ttu-id="079d1-168">処理時間が3秒になると、サーバーは調整モードから切断され、クライアント接続ごとに最大20個の未処理トランザクションをユーザーに提供します。</span><span class="sxs-lookup"><span data-stu-id="079d1-168">Once the processing time drops to three seconds, then the server drops out of throttling mode and gives users up to 20 outstanding transactions per client connection.</span></span> <span data-ttu-id="079d1-169">特定の接続上のトランザクションの数が上記のしきい値を超えた場合、接続はフロー制御としてマークされます。</span><span class="sxs-lookup"><span data-stu-id="079d1-169">Whenever the number of transactions on a specific connection exceeds the threshold above, the connection is marked as flow controlled.</span></span> <span data-ttu-id="079d1-170">その結果、サーバーは、サーバー上で受信を送信しません。 **LC: SIP-01-ピア \\ フロー制御接続** カウンターがインクリメントされます。</span><span class="sxs-lookup"><span data-stu-id="079d1-170">The result is the server does not post any receives on it, and the **LC:SIP-01-Peers\\Flow Controlled Connections** counter is incremented.</span></span> <span data-ttu-id="079d1-171">接続がフロー制御された状態が1分を超えると、サーバーはそれを閉じます。</span><span class="sxs-lookup"><span data-stu-id="079d1-171">If a connection stays in a flow-controlled state for more than one minute, then the server closes it.</span></span> <span data-ttu-id="079d1-172">これは遅延します。</span><span class="sxs-lookup"><span data-stu-id="079d1-172">It does so lazily.</span></span> <span data-ttu-id="079d1-173">接続を確認する機会があれば、それが長時間に制限されているかどうかを判断し、それが1分を超える場合はそれを閉じます。</span><span class="sxs-lookup"><span data-stu-id="079d1-173">When it has an opportunity to check the connection, it determines whether it was throttled for too long and closes it if it has more than one minute.</span></span>

<span data-ttu-id="079d1-174">これらは2つの調整メカニズムであり、サーバーが実行している調整がある場合は、それを要約したパフォーマンスカウンターが1つあります。</span><span class="sxs-lookup"><span data-stu-id="079d1-174">These are the two throttling mechanisms and there is one performance counter that summarizes what, if any, throttling the server is performing.</span></span>

<span data-ttu-id="079d1-175">**LC: SIP-04-応答 \\ sip-053-ローカル503応答/秒**</span><span class="sxs-lookup"><span data-stu-id="079d1-175">**LC:SIP-04-Responses\\SIP-053-Local 503 Responses/sec**</span></span>

  - <span data-ttu-id="079d1-176">前のカウンターの "Local" という用語は、ローカルに生成された応答を意味します。</span><span class="sxs-lookup"><span data-stu-id="079d1-176">The term "Local" in the previous counter refers to locally generated responses.</span></span>

  - <span data-ttu-id="079d1-177">503コードは、サーバーを使用できないことに対応します。これは、正常なサーバー上に503コードが表示されないようにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="079d1-177">The 503 code corresponds to server unavailable—where you should not see any 503 codes on a healthy server.</span></span> <span data-ttu-id="079d1-178">サーバーがオンラインになるまでの期間中に、一部の503コードが表示されることがあります。</span><span class="sxs-lookup"><span data-stu-id="079d1-178">During the period after a server is just brought online, you may see some 503 codes.</span></span> <span data-ttu-id="079d1-179">すべてのユーザーが再度サインインして、サーバーが安定した状態に戻ると、503コードを追加する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="079d1-179">When all of the users sign back in and the server returns to a stable state, there should no additional 503 codes.</span></span>

<span data-ttu-id="079d1-180">**LC: SIP-04-応答 \\ sip-074-ローカル504応答/秒**</span><span class="sxs-lookup"><span data-stu-id="079d1-180">**LC:SIP-04-Responses\\SIP-074-Local 504 Responses/sec**</span></span>

<span data-ttu-id="079d1-181">このパフォーマンスカウンターは、他のサーバーとの接続の問題を示し、接続中に接続または遅延が発生したことを示します。</span><span class="sxs-lookup"><span data-stu-id="079d1-181">This performance counter indicates connectivity issues with other servers and it can indicate failures to connect or delays in connecting.</span></span> <span data-ttu-id="079d1-182">504エラーが表示される場合は、次のパフォーマンスカウンターをチェックする必要があります。</span><span class="sxs-lookup"><span data-stu-id="079d1-182">If you are seeing 504 errors then the following performance counter should be checked.</span></span>

<span data-ttu-id="079d1-183">**LC: SIP-01-ピア \\ sip-017-未完了の送信**</span><span class="sxs-lookup"><span data-stu-id="079d1-183">**LC:SIP-01-Peers\\SIP-017-Sends Outstanding**</span></span>

<span data-ttu-id="079d1-184">このカウンターは、キューに入っている発信された要求と応答の数を示します。</span><span class="sxs-lookup"><span data-stu-id="079d1-184">This counter indicates the number of outgoing queued requests and responses.</span></span> <span data-ttu-id="079d1-185">このカウンターが大きい場合、問題はローカルサーバーではない可能性が高くなります。</span><span class="sxs-lookup"><span data-stu-id="079d1-185">If this counter is high then the issue is most likely not on the local server.</span></span> <span data-ttu-id="079d1-186">ネットワーク待機時間の問題がある場合は、このカウンターが大きいことに注意してください。</span><span class="sxs-lookup"><span data-stu-id="079d1-186">Note that this counter can be high if there are network latency issues.</span></span> <span data-ttu-id="079d1-187">また、ローカルネットワークアダプターに関する問題を示している場合もありますが、リモートサーバー上の問題が原因である可能性が高くなります。</span><span class="sxs-lookup"><span data-stu-id="079d1-187">It could also indicate issues with the local network adapter, but is more likely caused by an issue on a remote server.</span></span> <span data-ttu-id="079d1-188">このカウンターは、通信しようとしているプールが過負荷になっている場合に、ディレクターサーバーにとって高い可能性が高くなります。</span><span class="sxs-lookup"><span data-stu-id="079d1-188">This counter would most likely be high on a Director server when the pool it is trying to communicate with is overloaded.</span></span> <span data-ttu-id="079d1-189">このカウンターのキーは、合計だけでなく、インスタンスを検索することです。</span><span class="sxs-lookup"><span data-stu-id="079d1-189">The key with this counter is to look at the instances, not just the total.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

