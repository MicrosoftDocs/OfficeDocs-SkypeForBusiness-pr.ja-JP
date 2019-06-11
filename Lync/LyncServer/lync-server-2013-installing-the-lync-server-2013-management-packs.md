---
title: 'Lync Server 2013: Lync Server 2013 管理パックのインストール'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: nstalling the Lync Server 2013 management packs
ms:assetid: b800d4ab-fdc8-4c72-a76a-b78932779fe3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205202(v=OCS.15)
ms:contentKeyID: 48185233
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fea443225744bfd0d0e2dfa90a317ffa4cc890ac
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34832992"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="installing-the-lync-server-2013-management-packs"></a><span data-ttu-id="e12b6-102">Lync Server 2013 管理パックのインストール</span><span class="sxs-lookup"><span data-stu-id="e12b6-102">Installing the Lync Server 2013 management packs</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e12b6-103">_**最終更新日:** 2012-10-22_</span><span class="sxs-lookup"><span data-stu-id="e12b6-103">_**Topic Last Modified:** 2012-10-22_</span></span>

<span data-ttu-id="e12b6-104">System Center Operations Manager は、Windows オペレーティングシステムのわずかな部分のみを監視することができます。</span><span class="sxs-lookup"><span data-stu-id="e12b6-104">By itself, System Center Operations Manager has the ability to monitor only a small portion of the Windows operating system.</span></span> <span data-ttu-id="e12b6-105">ただし、system center operations Manager の機能を拡張するには、管理パックをインストールします。このソフトウェアは、System Center Operations Manager が監視できる項目を決定するソフトウェア、それらの項目を監視する方法、アラートの表示方法などを行うことができます。トリガーおよび報告されます。</span><span class="sxs-lookup"><span data-stu-id="e12b6-105">However, you can extend the capabilities of System Center Operations Manager by installing management packs, software that dictates which items System Center Operations Manager can monitor, including how those items should be monitored and how alerts should be triggered and reported.</span></span> <span data-ttu-id="e12b6-106">Microsoft Lync Server 2013 には、次の機能を提供する System Center Operations Manager の2つの管理パックが含まれています。</span><span class="sxs-lookup"><span data-stu-id="e12b6-106">Microsoft Lync Server 2013 includes two System Center Operations Manager management packs that provide the following capabilities:</span></span>

  - <span data-ttu-id="e12b6-107">コンポーネントとユーザー管理パック (Microsoft.LS.2013.Monitoring.ComponentAndUser.mp) は、イベントログに記録された Lync Server の問題を追跡し、パフォーマンスカウンターで登録するか、または通話の詳細レコード (CDR) またはエクスペリエンスの品質 (QoE) に記録します。databases.</span><span class="sxs-lookup"><span data-stu-id="e12b6-107">The Component and User Management Pack (Microsoft.LS.2013.Monitoring.ComponentAndUser.mp) tracks Lync Server issues recorded in event logs, registered by performance counters, or logged in the call detail records (CDR) or the Quality of Experience (QoE) databases.</span></span> <span data-ttu-id="e12b6-108">重大な問題については、System Center Operations Manager を構成して、メール、インスタントメッセージ、またはショートメッセージサービス (SMS) メッセージングを使って管理者にすぐに通知することができます。</span><span class="sxs-lookup"><span data-stu-id="e12b6-108">For critical problems, System Center Operations Manager can be configured to immediately notify administrators via email, instant message, or Short Message Service (SMS) messaging.</span></span> <span data-ttu-id="e12b6-109">SMS は、あるモバイルデバイスから別のモバイルデバイスにテキストメッセージを送信するために使用されるテクノロジです。</span><span class="sxs-lookup"><span data-stu-id="e12b6-109">SMS is the technology used to send text messages from one mobile device to another.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="e12b6-110">Operations Manager の通知の構成の詳細については、TechNet ライブラリの「 <A class=uri href="http://go.microsoft.com/fwlink/p/?linkid=268785">http://go.microsoft.com/fwlink/p/?linkid=268785</A>通知を設定する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e12b6-110">For more information on configuring Operations Manager notification, see Configuring Notification in the TechNet Library at <A class=uri href="http://go.microsoft.com/fwlink/p/?linkid=268785">http://go.microsoft.com/fwlink/p/?linkid=268785</A>.</span></span>

    
    </div>

  - <span data-ttu-id="e12b6-111">アクティブな監視パック (Microsoft.LS.2013.Monitoring.ActiveMonitoring.mp) は、システムにログオンしたり、インスタントメッセージを交換したり、公衆交換電話に入っている電話への通話を発信したりするなど、Lync Server の主要なコンポーネントを事前にテストします。ネットワーク (PSTN)。</span><span class="sxs-lookup"><span data-stu-id="e12b6-111">The Active Monitoring Pack (Microsoft.LS.2013.Monitoring.ActiveMonitoring.mp) proactively tests key Lync Server components such as logging on to the system, exchanging instant messages, or making calls to a phone located on the public switched telephone network (PSTN).</span></span> <span data-ttu-id="e12b6-112">これらのテストは、Lync Server の代理トランザクションコマンドレットを使用して行われます。</span><span class="sxs-lookup"><span data-stu-id="e12b6-112">These tests are conducted using the Lync Server synthetic transaction cmdlets.</span></span> <span data-ttu-id="e12b6-113">たとえば、テスト用の**cgi**コマンドレットを使って、一連のテストユーザー間のインスタントメッセージの会話をシミュレートします。</span><span class="sxs-lookup"><span data-stu-id="e12b6-113">For example, the **Test-CsIM** cmdlet is used to simulate an instant messaging conversation between a pair of test users.</span></span> <span data-ttu-id="e12b6-114">このシミュレートされたメッセージの会話に失敗した場合は、警告が生成されます。</span><span class="sxs-lookup"><span data-stu-id="e12b6-114">If this simulated messaging conversation fails an alert will be generated.</span></span>

<span data-ttu-id="e12b6-115">Lync Server 2013 に含まれている2つの管理パックには、Microsoft Lync Server 2010 で使用される管理パックに対する多数の拡張機能が含まれています。</span><span class="sxs-lookup"><span data-stu-id="e12b6-115">The two management packs included with Lync Server 2013 include a large number of enhancements over the management packs used with Microsoft Lync Server 2010.</span></span> <span data-ttu-id="e12b6-116">たとえば、Lync Server 2013 コンポーネント管理パックは、Lync Server 自体の監視に限定されているわけではありません。</span><span class="sxs-lookup"><span data-stu-id="e12b6-116">For example, the Lync Server 2013 Component Management Pack is not limited to monitoring Lync Server itself.</span></span> <span data-ttu-id="e12b6-117">Lync Server のイベントログとパフォーマンスカウンターの監視に加えて、コンポーネント管理パックは、次のような重要な項目についてのパフォーマンスを追跡し、警告を発行することもできます。</span><span class="sxs-lookup"><span data-stu-id="e12b6-117">In addition to monitoring event logs and performance counters for Lync Server, the Component Management pack can also track the performance of, and issue alerts for, crucial items such as:</span></span>

  - <span data-ttu-id="e12b6-118">**インターネットインフォメーションサービス (IIS)**   の警告は、インターネットインフォメーションサービスがオフラインになった場合に発行されます。</span><span class="sxs-lookup"><span data-stu-id="e12b6-118">**Internet Information Services (IIS)**   Alerts will be issued if Internet Information Services goes offline.</span></span> <span data-ttu-id="e12b6-119">Lync Server web サービスは IIS に依存しているため、これは重要です。</span><span class="sxs-lookup"><span data-stu-id="e12b6-119">This is important, because the Lync Server web services rely on IIS.</span></span>

  - <span data-ttu-id="e12b6-120">**プロセスの使用状況**   の警告は、システムリソース (利用可能なメモリなど) を低解像度で開始した場合に発行されます。</span><span class="sxs-lookup"><span data-stu-id="e12b6-120">**Process usage**   Alerts will be issued if system resources (such as available memory) begin to run low.</span></span> <span data-ttu-id="e12b6-121">これらの通知は、Lync Server が高いシステム使用を担当していない場合でも発行されます。</span><span class="sxs-lookup"><span data-stu-id="e12b6-121">These alerts will be issued even if Lync Server is not responsible for the high system usage.</span></span>

  - <span data-ttu-id="e12b6-122">**コンピューターの障害イベント**   アラートは、サーバーの実行可能性を早急に示すハードウェアまたはソフトウェアの問題が発生した場合に発行されます。</span><span class="sxs-lookup"><span data-stu-id="e12b6-122">**Computer failure events**   Alerts will be issued in case of a hardware or software issue that threatens the viability of a server.</span></span> <span data-ttu-id="e12b6-123">たとえば、ハードディスクの障害が発生している可能性があるサーバーが表示された場合は、Lync Server の管理者に通知されます。</span><span class="sxs-lookup"><span data-stu-id="e12b6-123">For example, Lync Server administrators will be notified if a server appears to be in danger of experiencing a hard disk failure.</span></span>

<span data-ttu-id="e12b6-124">新しい管理パックでも、レポート機能が強化されています。</span><span class="sxs-lookup"><span data-stu-id="e12b6-124">The new management packs also feature enhanced reporting.</span></span> <span data-ttu-id="e12b6-125">Lync Server 2013 の新しいレポートには、次のようなものがあります。</span><span class="sxs-lookup"><span data-stu-id="e12b6-125">New reports for Lync Server 2013 include:</span></span>

  - <span data-ttu-id="e12b6-126">**[終了-終了] シナリオの可用性レポート**   このレポートは、登録やプレゼンスなどの、主要な Lync Server サービスの可用性/稼働時間を詳細に説明します。</span><span class="sxs-lookup"><span data-stu-id="e12b6-126">**End to End Scenario Availability Report**   This report details the availability/uptime for key Lync Server services such as registration or presence.</span></span>

  - <span data-ttu-id="e12b6-127">\*\*\*\*   [パフォーマンスカウンター情報を使用したキャパシティレポート] このレポートには、メモリの可用性やプロセッサ使用率などのシステムコンポーネントの傾向が表示されます。</span><span class="sxs-lookup"><span data-stu-id="e12b6-127">**Capacity Report**   Using performance counter information, this report shows trends for system components such as memory availability and processor usage.</span></span>

  - <span data-ttu-id="e12b6-128">**[コンポーネントレポート**   このレポートには、Lync Server コンポーネントによってグループ化された最上位の通知ジェネレーターが一覧表示されます。</span><span class="sxs-lookup"><span data-stu-id="e12b6-128">**Component Report**   This report lists the top alert generators grouped by Lync Server component.</span></span>

<span data-ttu-id="e12b6-129">これらのデザイン済みレポートに加えて、Lync Server 2013 用の管理パックは、通話の信頼性 (通話詳細の記録で測定された測度) と QoE の状態 (エクスペリエンスの品質で測定される測度) の両方について、自動的に通知を報告します。</span><span class="sxs-lookup"><span data-stu-id="e12b6-129">In addition to these predesigned reports, the management packs for Lync Server 2013 automatically report alerts for both Call Reliability (metrics measured by Call Detail Recording) and QoE states (metrics measured by Quality of Experience).</span></span> <span data-ttu-id="e12b6-130">通話の詳細記録を有効にしている場合は、System Center Operations Manager コンソールから次の手順を実行して、通話の信頼性の警告を確認できます。</span><span class="sxs-lookup"><span data-stu-id="e12b6-130">If you have enabled Call Detail Recording, you can review Call Reliability alerts by completing the following procedure from the System Center Operations Manager console:</span></span>

  - <span data-ttu-id="e12b6-131">[**監視**]、[ **Microsoft Lync Server 2013 正常性**] の順に展開し、[**通話の信頼性とメディアの品質**] を展開して、[通話の**信頼性**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="e12b6-131">Expand **Monitoring**, expand **Microsoft Lync Server 2013 Health**, expand **Call Reliability and Media Quality**, and then click **Call Reliability**.</span></span>

<span data-ttu-id="e12b6-132">エクスペリエンスの警告を表示するには、System Center Operations Manager コンソールから次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="e12b6-132">To view Quality of Experience alerts, complete this procedure from the System Center Operations Manager console:</span></span>

  - <span data-ttu-id="e12b6-133">[**監視**]、[ **Microsoft Lync Server 2013 正常性**] の順に展開し、[**通話の信頼性とメディアの品質**] を展開して、[メディアの**品質**] を展開します。</span><span class="sxs-lookup"><span data-stu-id="e12b6-133">Expand **Monitoring**, expand **Microsoft Lync Server 2013 Health**, expand **Call Reliability and Media Quality**, and then expand **Media Quality**.</span></span>

<span data-ttu-id="e12b6-134">Lync Server 2013 用の管理パックで、Microsoft Lync Server 2010 で使用されるセントラル検出メカニズムではなく、マシンレベルの検出が使用されるようになりました。</span><span class="sxs-lookup"><span data-stu-id="e12b6-134">The management packs for Lync Server 2013 now use machine-level discovery instead of the central discovery mechanism used in Microsoft Lync Server 2010.</span></span> <span data-ttu-id="e12b6-135">つまり、各 System Center agent は基本的に自分自身を検出し、その存在を中央管理サーバーに報告します。</span><span class="sxs-lookup"><span data-stu-id="e12b6-135">This means that each System Center agent essentially discovers itself and reports its existence to the Central Management Server.</span></span> <span data-ttu-id="e12b6-136">マシンレベルの検出を使うと、System Center インフラストラクチャの管理が簡単になり、さまざまなバージョンの Lync Server 管理パック (たとえば、lync Server 2010 用の管理パックと Lync Server 2013 用の管理パック) を使用することができます。せ.</span><span class="sxs-lookup"><span data-stu-id="e12b6-136">Using machine-level discovery simplifies administration of your System Center infrastructure and also allows different versions of the Lync Server management packs (for example, management packs for Lync Server 2010 and management packs for Lync Server 2013) to coexist.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

