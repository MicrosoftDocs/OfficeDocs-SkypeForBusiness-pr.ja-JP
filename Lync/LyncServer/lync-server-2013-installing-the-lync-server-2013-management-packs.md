---
title: 'Lync Server 2013: Lync Server 2013 管理パックのインストール'
description: 'Lync Server 2013: Lync Server 2013 管理パックのインストール。'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: nstalling the Lync Server 2013 management packs
ms:assetid: b800d4ab-fdc8-4c72-a76a-b78932779fe3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205202(v=OCS.15)
ms:contentKeyID: 48185233
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: cbb50146474211c12dbd95801ed2b20f6bbfd8c9
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48573833"
---
# <a name="installing-the-lync-server-2013-management-packs"></a><span data-ttu-id="09e53-103">Lync Server 2013 管理パックのインストール</span><span class="sxs-lookup"><span data-stu-id="09e53-103">Installing the Lync Server 2013 management packs</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="09e53-104">_**トピックの最終更新日:** 2012-10-22_</span><span class="sxs-lookup"><span data-stu-id="09e53-104">_**Topic Last Modified:** 2012-10-22_</span></span>

<span data-ttu-id="09e53-105">System Center Operations Manager は単独で、Windows オペレーティングシステムのごく一部のみを監視することができます。</span><span class="sxs-lookup"><span data-stu-id="09e53-105">By itself, System Center Operations Manager has the ability to monitor only a small portion of the Windows operating system.</span></span> <span data-ttu-id="09e53-106">ただし、system center operations manager の機能を拡張するには、System center Operations Manager が監視できるアイテムを指定するソフトウェアをインストールします。これには、これらのアイテムを監視する方法や、アラートをトリガーおよびレポートする方法などが含まれます。</span><span class="sxs-lookup"><span data-stu-id="09e53-106">However, you can extend the capabilities of System Center Operations Manager by installing management packs, software that dictates which items System Center Operations Manager can monitor, including how those items should be monitored and how alerts should be triggered and reported.</span></span> <span data-ttu-id="09e53-107">Microsoft Lync Server 2013 には、次の機能を提供する2つの System Center Operations Manager 管理パックが含まれています。</span><span class="sxs-lookup"><span data-stu-id="09e53-107">Microsoft Lync Server 2013 includes two System Center Operations Manager management packs that provide the following capabilities:</span></span>

  - <span data-ttu-id="09e53-108">コンポーネントおよびユーザー管理パック (Microsoft.LS.2013.Monitoring.ComponentAndUser.mp) は、イベントログに記録された Lync Server の問題を追跡し、パフォーマンスカウンターで登録するか、または通話詳細記録 (CDR) または QoE (Quality of Experience) データベースに記録します。</span><span class="sxs-lookup"><span data-stu-id="09e53-108">The Component and User Management Pack (Microsoft.LS.2013.Monitoring.ComponentAndUser.mp) tracks Lync Server issues recorded in event logs, registered by performance counters, or logged in the call detail records (CDR) or the Quality of Experience (QoE) databases.</span></span> <span data-ttu-id="09e53-109">重大な問題については、System Center Operations Manager を構成して、電子メール、インスタントメッセージ、またはショートメッセージサービス (SMS) のメッセージングを介して管理者に即座に通知できます。</span><span class="sxs-lookup"><span data-stu-id="09e53-109">For critical problems, System Center Operations Manager can be configured to immediately notify administrators via email, instant message, or Short Message Service (SMS) messaging.</span></span> <span data-ttu-id="09e53-110">SMS とは、テキスト メッセージをモバイル デバイス間で送信するために使用されるテクノロジです。</span><span class="sxs-lookup"><span data-stu-id="09e53-110">SMS is the technology used to send text messages from one mobile device to another.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="09e53-111">Operations Manager 通知の構成の詳細については、TechNet ライブラリの「通知の構成」を参照してください <A class=uri href="https://go.microsoft.com/fwlink/p/?linkid=268785">https://go.microsoft.com/fwlink/p/?linkid=268785</A> 。</span><span class="sxs-lookup"><span data-stu-id="09e53-111">For more information on configuring Operations Manager notification, see Configuring Notification in the TechNet Library at <A class=uri href="https://go.microsoft.com/fwlink/p/?linkid=268785">https://go.microsoft.com/fwlink/p/?linkid=268785</A>.</span></span>

    
    </div>

  - <span data-ttu-id="09e53-112">アクティブな監視パック (Microsoft.LS.2013.Monitoring.ActiveMonitoring.mp) は、システムへのログオン、インスタントメッセージの交換、または公衆交換電話網 (PSTN) に配置された電話機への通話の作成などの主要な Lync Server コンポーネントを事前にテストします。</span><span class="sxs-lookup"><span data-stu-id="09e53-112">The Active Monitoring Pack (Microsoft.LS.2013.Monitoring.ActiveMonitoring.mp) proactively tests key Lync Server components such as logging on to the system, exchanging instant messages, or making calls to a phone located on the public switched telephone network (PSTN).</span></span> <span data-ttu-id="09e53-113">これらのテストは、Lync Server 代理トランザクションコマンドレットを使用して行われます。</span><span class="sxs-lookup"><span data-stu-id="09e53-113">These tests are conducted using the Lync Server synthetic transaction cmdlets.</span></span> <span data-ttu-id="09e53-114">たとえば、**Test-CsIM** コマンドレットは、1 組のテスト ユーザー間でインスタント メッセージングの会話をシミュレートするために使用されます。</span><span class="sxs-lookup"><span data-stu-id="09e53-114">For example, the **Test-CsIM** cmdlet is used to simulate an instant messaging conversation between a pair of test users.</span></span> <span data-ttu-id="09e53-115">シミュレートされたメッセージングの会話が失敗した場合、通知が生成されます。</span><span class="sxs-lookup"><span data-stu-id="09e53-115">If this simulated messaging conversation fails an alert will be generated.</span></span>

<span data-ttu-id="09e53-116">Lync Server 2013 に含まれている2つの管理パックには、Microsoft Lync Server 2010 で使用される管理パックに対して多くの拡張機能が含まれています。</span><span class="sxs-lookup"><span data-stu-id="09e53-116">The two management packs included with Lync Server 2013 include a large number of enhancements over the management packs used with Microsoft Lync Server 2010.</span></span> <span data-ttu-id="09e53-117">たとえば、Lync server 2013 コンポーネント管理パックは、Lync Server 自体の監視に制限されていません。</span><span class="sxs-lookup"><span data-stu-id="09e53-117">For example, the Lync Server 2013 Component Management Pack is not limited to monitoring Lync Server itself.</span></span> <span data-ttu-id="09e53-118">Lync Server のイベントログとパフォーマンスカウンターの監視に加えて、コンポーネント管理パックは次のような重要なアイテムのパフォーマンスを追跡し、通知を発行することもできます。</span><span class="sxs-lookup"><span data-stu-id="09e53-118">In addition to monitoring event logs and performance counters for Lync Server, the Component Management pack can also track the performance of, and issue alerts for, crucial items such as:</span></span>

  - <span data-ttu-id="09e53-119">**インターネットインフォメーションサービス (IIS)**    インターネットインフォメーションサービスがオフラインになった場合に警告が発行されます。</span><span class="sxs-lookup"><span data-stu-id="09e53-119">**Internet Information Services (IIS)**   Alerts will be issued if Internet Information Services goes offline.</span></span> <span data-ttu-id="09e53-120">これは、Lync Server web サービスが IIS に依存しているためです。</span><span class="sxs-lookup"><span data-stu-id="09e53-120">This is important, because the Lync Server web services rely on IIS.</span></span>

  - <span data-ttu-id="09e53-121">**プロセスの利用状況**    システムリソース (利用可能なメモリなど) が不足し始めたときに警告が発行されます。</span><span class="sxs-lookup"><span data-stu-id="09e53-121">**Process usage**   Alerts will be issued if system resources (such as available memory) begin to run low.</span></span> <span data-ttu-id="09e53-122">これらのアラートは、Lync Server がシステムの高使用率を担当していない場合でも発行されます。</span><span class="sxs-lookup"><span data-stu-id="09e53-122">These alerts will be issued even if Lync Server is not responsible for the high system usage.</span></span>

  - <span data-ttu-id="09e53-123">**コンピュータエラーイベント**    ハードウェアまたはソフトウェアの問題が発生したときに、サーバーの可能性を阻むアラートが発行されます。</span><span class="sxs-lookup"><span data-stu-id="09e53-123">**Computer failure events**   Alerts will be issued in case of a hardware or software issue that threatens the viability of a server.</span></span> <span data-ttu-id="09e53-124">たとえば、Lync Server 管理者は、ハードディスク障害が発生する危険性があると思われる場合に、そのサーバーに通知されます。</span><span class="sxs-lookup"><span data-stu-id="09e53-124">For example, Lync Server administrators will be notified if a server appears to be in danger of experiencing a hard disk failure.</span></span>

<span data-ttu-id="09e53-125">新しい管理パックは、拡張されたレポート機能も備えています。</span><span class="sxs-lookup"><span data-stu-id="09e53-125">The new management packs also feature enhanced reporting.</span></span> <span data-ttu-id="09e53-126">Lync Server 2013 の新しいレポートは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="09e53-126">New reports for Lync Server 2013 include:</span></span>

  - <span data-ttu-id="09e53-127">**エンドツーエンドシナリオの可用性レポート**    このレポートでは、登録やプレゼンスなど、主要な Lync Server サービスの可用性/稼働時間を詳細に説明します。</span><span class="sxs-lookup"><span data-stu-id="09e53-127">**End to End Scenario Availability Report**   This report details the availability/uptime for key Lync Server services such as registration or presence.</span></span>

  - <span data-ttu-id="09e53-128">**容量レポート**    このレポートは、パフォーマンスカウンターの情報を使用して、メモリの可用性やプロセッサの使用率などのシステムコンポーネントの傾向を示します。</span><span class="sxs-lookup"><span data-stu-id="09e53-128">**Capacity Report**   Using performance counter information, this report shows trends for system components such as memory availability and processor usage.</span></span>

  - <span data-ttu-id="09e53-129">**コンポーネントレポート**    このレポートには、Lync Server コンポーネントによってグループ化された上位の通知ジェネレーターが一覧表示されます。</span><span class="sxs-lookup"><span data-stu-id="09e53-129">**Component Report**   This report lists the top alert generators grouped by Lync Server component.</span></span>

<span data-ttu-id="09e53-130">これらの設計済みレポートに加えて、Lync Server 2013 用の管理パックは、通話の信頼性 (通話詳細記録で測定された測定基準) と QoE の状態 (品質不足の測定基準) の両方に関する通知を自動的に報告します。</span><span class="sxs-lookup"><span data-stu-id="09e53-130">In addition to these predesigned reports, the management packs for Lync Server 2013 automatically report alerts for both Call Reliability (metrics measured by Call Detail Recording) and QoE states (metrics measured by Quality of Experience).</span></span> <span data-ttu-id="09e53-131">通話詳細記録を有効にしている場合は、System Center Operations Manager コンソールから次の手順を実行して、通話の信頼性に関する警告を確認できます。</span><span class="sxs-lookup"><span data-stu-id="09e53-131">If you have enabled Call Detail Recording, you can review Call Reliability alerts by completing the following procedure from the System Center Operations Manager console:</span></span>

  - <span data-ttu-id="09e53-132">[**監視**]、[**Microsoft Lync Server 2013 Health**]、[**Call Reliability and Media Quality**] の順に展開し、[**Call Reliability**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="09e53-132">Expand **Monitoring**, expand **Microsoft Lync Server 2013 Health**, expand **Call Reliability and Media Quality**, and then click **Call Reliability**.</span></span>

<span data-ttu-id="09e53-133">Qoe (Quality of Experience) の警告を表示するには、System Center Operations Manager コンソールから次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="09e53-133">To view Quality of Experience alerts, complete this procedure from the System Center Operations Manager console:</span></span>

  - <span data-ttu-id="09e53-134">[**監視**]、[**Microsoft Lync Server 2013 Health**]、[**Call Reliability and Media Quality**]、[**Media Quality**] の順に展開します。</span><span class="sxs-lookup"><span data-stu-id="09e53-134">Expand **Monitoring**, expand **Microsoft Lync Server 2013 Health**, expand **Call Reliability and Media Quality**, and then expand **Media Quality**.</span></span>

<span data-ttu-id="09e53-135">Lync Server 2013 用の管理パックは、Microsoft Lync Server 2010 で使用される中央の検出メカニズムではなく、マシンレベルの検出を使用するようになりました。</span><span class="sxs-lookup"><span data-stu-id="09e53-135">The management packs for Lync Server 2013 now use machine-level discovery instead of the central discovery mechanism used in Microsoft Lync Server 2010.</span></span> <span data-ttu-id="09e53-136">つまり、各システムセンターエージェントは本質的に自分自身を検出し、その存在を中央管理サーバーに報告します。</span><span class="sxs-lookup"><span data-stu-id="09e53-136">This means that each System Center agent essentially discovers itself and reports its existence to the Central Management Server.</span></span> <span data-ttu-id="09e53-137">コンピューターレベルの検出を使用すると、システムセンターインフラストラクチャの管理が簡単になります。また、lync server 管理パックのさまざまなバージョン (lync server 2010 用の管理パック、Lync Server 2013 用の管理パック) を共存させることもできます。</span><span class="sxs-lookup"><span data-stu-id="09e53-137">Using machine-level discovery simplifies administration of your System Center infrastructure and also allows different versions of the Lync Server management packs (for example, management packs for Lync Server 2010 and management packs for Lync Server 2013) to coexist.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

