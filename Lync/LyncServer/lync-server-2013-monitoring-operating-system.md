---
title: 'Lync Server 2013: オペレーティングシステムの監視'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Monitoring operating system
ms:assetid: 72406d3e-54c8-4796-8d6d-2144a5b6f030
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720918(v=OCS.15)
ms:contentKeyID: 63969617
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a5bd837bab2ca4323dd0fb2f4d29b31d653d37c8
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2020
ms.locfileid: "42047699"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="monitoring-operating-system-in-lync-server-2013"></a><span data-ttu-id="2c577-102">Lync Server 2013 でのオペレーティングシステムの監視</span><span class="sxs-lookup"><span data-stu-id="2c577-102">Monitoring operating system in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2c577-103">_**トピックの最終更新日:** 2015-01-26_</span><span class="sxs-lookup"><span data-stu-id="2c577-103">_**Topic Last Modified:** 2015-01-26_</span></span>

<span data-ttu-id="2c577-104">Lync Server 2013 のすべてのサーバーとコンポーネントのパフォーマンスを監視する必要があります。</span><span class="sxs-lookup"><span data-stu-id="2c577-104">You must monitor the performance of all servers and components in the Lync Server 2013.</span></span> <span data-ttu-id="2c577-105">当然ですが、最も重要なコンポーネントの1つはオペレーティングシステム自体です。</span><span class="sxs-lookup"><span data-stu-id="2c577-105">Obviously, one of the most important components is the operating system itself.</span></span> <span data-ttu-id="2c577-106">Lync Server 2013 でサポートされている x64 エディションは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="2c577-106">Lync Server 2013 supports x64 editions of:</span></span>

  - <span data-ttu-id="2c577-107">Windows Server 2008 R2</span><span class="sxs-lookup"><span data-stu-id="2c577-107">Windows Server 2008 R2</span></span>

  - <span data-ttu-id="2c577-108">Windows Server 2012 と Windows Server 2012 R2</span><span class="sxs-lookup"><span data-stu-id="2c577-108">Windows Server 2012 and Windows Server 2012 R2</span></span>

<span data-ttu-id="2c577-109">オペレーティングシステムを監視する最も透過的な方法は、Windows Server オペレーティングシステム管理パックを使用する方法です。</span><span class="sxs-lookup"><span data-stu-id="2c577-109">The most transparent way to monitor an operating system is by using Windows Server Operating System Management Pack.</span></span> <span data-ttu-id="2c577-110">Windows Server 2012、Windows Server 2012 R2、および Windows Server 2008 R2 を実行しているコンピューターのパフォーマンス、正常性、可用性など、基本的な監視の基本事項を示します。</span><span class="sxs-lookup"><span data-stu-id="2c577-110">It provides the fundamental monitoring basics, such as performance, health, and availability for computers that are running Windows Server 2012, Windows Server 2012 R2, and Windows Server 2008 R2.</span></span>

<span data-ttu-id="2c577-111">重要なイベントとパフォーマンスインジケーターを検出、警告、および自動応答することにより、これらの管理パックでは問題の解決時間が短縮され、Windows Server を実行しているシステムの全体的な可用性とパフォーマンスが向上します。オペレーティングシステム。</span><span class="sxs-lookup"><span data-stu-id="2c577-111">By detecting, alerting, and automatically responding to important events and performance indicators, these management packs reduce resolution times for issues and increase the overall availability and performance of systems that are running the Windows Server operating systems.</span></span>

<span data-ttu-id="2c577-112">System Center Operations Manager 用の Windows Server 管理パックとは別に、次のシステムツールとリソースを使用して、オペレーティングシステムの正常性を監視できます (オペレーティングシステムのバージョンによって異なります)。</span><span class="sxs-lookup"><span data-stu-id="2c577-112">Apart from relevant Windows Server management packs for System Center Operations Manager, the following system tools and resources can be used to monitor the health of the operating system (depending on the operating system version).</span></span>

<div>

## <a name="windows-server2008r2"></a><span data-ttu-id="2c577-113">Windows Server 2008 R2</span><span class="sxs-lookup"><span data-stu-id="2c577-113">Windows Server 2008 R2</span></span>

<span data-ttu-id="2c577-114">Windows Server 2008 R2 には、管理者が基本的なオペレーティングシステムの監視と管理を支援するための次の追加機能とツールが含まれています。</span><span class="sxs-lookup"><span data-stu-id="2c577-114">Windows Server 2008 R2 includes the following additional features and tools to help administrators with basic operating system monitoring and management:</span></span>

  - <span data-ttu-id="2c577-115">**Windows リソースモニター**は、プロセスやサービスによってシステムリソースがどのように使用されるかを理解するための強力なツールです。</span><span class="sxs-lookup"><span data-stu-id="2c577-115">**Windows Resource Monitor** is a powerful tool for understanding how system resources are used by processes and services.</span></span> <span data-ttu-id="2c577-116">リソースモニターは、リアルタイムでのリソース使用状況の監視に加えて、応答されていないプロセスの分析、ファイルを使用しているアプリケーションの特定、およびプロセスとサービスの制御に役立てることができます。</span><span class="sxs-lookup"><span data-stu-id="2c577-116">In addition to monitoring resource usage in real time, a Resource Monitor can help analyze unresponsive processes, identify which applications are using files, and control processes and services.</span></span>

  - <span data-ttu-id="2c577-117">**信頼性分析コンポーネント**は、システムの使用状況と信頼性に関する詳細な実績情報を提供する、インボックスエージェントです。</span><span class="sxs-lookup"><span data-stu-id="2c577-117">**Reliability Analysis Component** is an in-box agent that provides detailed experience information on system usage and reliability.</span></span> <span data-ttu-id="2c577-118">この情報は、ポータブルリーダーシステムで利用できるようにするために、WMI インターフェイスを通じて公開されます。</span><span class="sxs-lookup"><span data-stu-id="2c577-118">This information is exposed through a WMI interface to make it available for consumption by Portable Readers Systems.</span></span> <span data-ttu-id="2c577-119">WMI インターフェイスを使用して信頼性分析コンポーネントを公開することにより、開発者はアプリケーションを監視および分析し、信頼性とパフォーマンスを向上させることができます。</span><span class="sxs-lookup"><span data-stu-id="2c577-119">By exposing Reliability Analysis Component through a WMI interface, developers can monitor and analyze applications, increasing reliability and performance.</span></span>

  - <span data-ttu-id="2c577-120">**Windows Server 2008 R2**は、組み込みの信頼性分析コンポーネントを使用して、信頼性指数を計算します。これは、時間の経過に伴うシステム全体の使用状況と安定性に関する情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="2c577-120">**Windows Server 2008 R2** uses the built-in Reliability Analysis Component to calculate a reliability index, which provides information about overall system usage and stability over time.</span></span> <span data-ttu-id="2c577-121">また、信頼性分析コンポーネントは、Windows の更新プログラムやアプリケーションのインストールなど、安定性に影響を与える可能性があるシステムへの重要な変更を追跡します。</span><span class="sxs-lookup"><span data-stu-id="2c577-121">The Reliability Analysis Component also keeps track of any important changes to the system that are likely to influence stability, such as Windows updates and application installations.</span></span>

</div>

<div>

## <a name="windows-server2008-windows-reliability-and-performance-monitor"></a><span data-ttu-id="2c577-122">Windows Server 2008 Windows 信頼性およびパフォーマンスモニター</span><span class="sxs-lookup"><span data-stu-id="2c577-122">Windows Server 2008 Windows Reliability and Performance Monitor</span></span>

<span data-ttu-id="2c577-123">Windows 信頼性およびパフォーマンスモニターは、パフォーマンスログと警告、サーバーパフォーマンスアドバイザー、システムモニターなど、以前のスタンドアロンツールの機能を組み合わせた MMC スナップインです。</span><span class="sxs-lookup"><span data-stu-id="2c577-123">Windows Reliability and Performance Monitor is an MMC Snap-in that combines the functionality of previous stand-alone tools including Performance Logs and Alerts, Server Performance Advisor, and System Monitor.</span></span> <span data-ttu-id="2c577-124">これにより、パフォーマンスデータの収集とイベントトレースセッションをカスタマイズするためのグラフィカルインターフェイスが提供されます。</span><span class="sxs-lookup"><span data-stu-id="2c577-124">It provides a graphical interface for customizing performance data collection and Event Trace Sessions.</span></span>

<span data-ttu-id="2c577-125">また、システムに加えられた変更を追跡し、それらをシステムの安定性の変化と比較する MMC スナップインである信頼性モニターも含まれており、それらの関係をグラフィカルに示しています。</span><span class="sxs-lookup"><span data-stu-id="2c577-125">It also includes Reliability Monitor, an MMC Snap-in that tracks changes to the system and compares them to changes in system stability, and it provides a graphical view of their relationship.</span></span>

</div>

<div>

## <a name="windows-reliability-and-performance-monitor"></a><span data-ttu-id="2c577-126">Windows 信頼性およびパフォーマンスモニター</span><span class="sxs-lookup"><span data-stu-id="2c577-126">Windows Reliability and Performance Monitor</span></span>

<span data-ttu-id="2c577-127">Windows 信頼性およびパフォーマンスモニターは、パフォーマンスログと警告などの以前のスタンドアロンツールの機能と、システムモニターおよびサーバーパフォーマンスアドバイザーを組み合わせていますが、Windows Server 2008 に新しい機能も提供します。Windows Server 2008 R2。次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="2c577-127">While Windows Reliability and Performance Monitor combine functionalities of some former stand-alone tools such as Performance Logs and Alerts, and System Monitor and Server Performance Advisor, it also provides some new functionality to Windows Server 2008 and Windows Server 2008 R2, such as the following:</span></span>

  - <span data-ttu-id="2c577-128">データコレクターセット</span><span class="sxs-lookup"><span data-stu-id="2c577-128">Data Collector Sets</span></span>

  - <span data-ttu-id="2c577-129">リソースビュー</span><span class="sxs-lookup"><span data-stu-id="2c577-129">Resource View</span></span>

  - <span data-ttu-id="2c577-130">信頼性モニター</span><span class="sxs-lookup"><span data-stu-id="2c577-130">Reliability Monitor</span></span>

  - <span data-ttu-id="2c577-131">ログ作成用のウィザードとテンプレート</span><span class="sxs-lookup"><span data-stu-id="2c577-131">Wizards and templates for creating logs</span></span>

<span data-ttu-id="2c577-132">**データコレクターセット**は、さまざまなパフォーマンス監視シナリオで使用するために、データコレクターを再利用可能な要素にグループ化します。</span><span class="sxs-lookup"><span data-stu-id="2c577-132">**Data Collector Set** groups data collectors into reusable elements for use with different performance monitoring scenarios.</span></span> <span data-ttu-id="2c577-133">データコレクターのグループがデータコレクターセットとして格納されると、1つのプロパティの変更によって、スケジューリングなどの操作をセット全体に適用できるようになります。Windows 信頼性およびパフォーマンスモニターには、システム管理者がサーバーの役割または監視シナリオに固有のパフォーマンスデータをすぐに収集できるようにするための既定のデータコレクターセットテンプレートが含まれています。</span><span class="sxs-lookup"><span data-stu-id="2c577-133">After a group of data collectors are stored as a Data Collector Set, operations such as scheduling can be applied to the whole set through a single property change.Windows Reliability and Performance Monitor includes default Data Collector Set templates to help system administrators begin immediately collecting performance data that is specific to a server role or monitoring scenario.</span></span>

<span data-ttu-id="2c577-134">Windows 信頼性およびパフォーマンスモニターのホームページは、新しい**リソースビュー**画面で、CPU、ディスク、ネットワーク、およびメモリの使用状況についてグラフィカルな概要をリアルタイムで提供します。</span><span class="sxs-lookup"><span data-stu-id="2c577-134">The home page of Windows Reliability and Performance Monitor is the new **Resource View** screen, which provides a real-time graphical overview of CPU, disk, network, and memory usage.</span></span> <span data-ttu-id="2c577-135">これらの監視対象要素をそれぞれ展開することで、システム管理者はどのプロセスがどのリソースを使用しているかを特定できます。</span><span class="sxs-lookup"><span data-stu-id="2c577-135">By expanding each of these monitored elements, system administrators can identify which processes are using which resources.</span></span> <span data-ttu-id="2c577-136">以前のバージョンの Windows では、このリアルタイムのプロセス固有のデータは、タスクマネージャーでは限られた形式でしか使用できませんでした。</span><span class="sxs-lookup"><span data-stu-id="2c577-136">In earlier versions of Windows, this real-time, process-specific data was available only in limited form in Task Manager.</span></span>

<span data-ttu-id="2c577-137">**信頼性モニター**が予期しない問題によってシステムの信頼性が低下したかどうかを示すシステム安定性指数を計算します。</span><span class="sxs-lookup"><span data-stu-id="2c577-137">**Reliability Monitor** calculates a System Stability Index that reflects whether unexpected issues reduced the reliability of the system.</span></span> <span data-ttu-id="2c577-138">時間の経過に伴う安定性インデックスのグラフは、問題が発生し始めた日付をすばやく特定します。</span><span class="sxs-lookup"><span data-stu-id="2c577-138">A graph of the Stability Index over time quickly identifies dates when issues began to occur.</span></span> <span data-ttu-id="2c577-139">付随するシステム安定性レポートには、信頼性の低下の原因をトラブルシューティングするのに役立つ詳細が記載されています。</span><span class="sxs-lookup"><span data-stu-id="2c577-139">The accompanying System Stability Report provides details to help troubleshoot the cause of reduced reliability.</span></span> <span data-ttu-id="2c577-140">システムに加えられた変更 (アプリケーションのインストールまたは削除、オペレーティングシステムの更新、またはドライバーの追加または変更) を、障害 (アプリケーション障害、オペレーティングシステムのクラッシュ、またはハードウェアの障害) と共に並べて表示することによって、問題を迅速に解決することができます。</span><span class="sxs-lookup"><span data-stu-id="2c577-140">By viewing changes to the system (installation or removal of applications, updates to the operating system, or addition or modification of drivers) side by side with failures (application failures, operating system crashes, or hardware failures), a strategy for addressing the issues can be developed quickly.</span></span>

<span data-ttu-id="2c577-141">**ウィザードインターフェイス**を使用して、ログファイルにカウンターを追加し、開始、停止、および期間をスケジュールできるようになりました。</span><span class="sxs-lookup"><span data-stu-id="2c577-141">Adding counters to log files and scheduling their start, stop, and duration can now be performed through a **Wizard interface**.</span></span> <span data-ttu-id="2c577-142">さらに、この構成をテンプレートとして保存することで、システム管理者はデータコレクターの選択とスケジューリングプロセスを繰り返さずに、他のコンピューターで同じログを収集できます。</span><span class="sxs-lookup"><span data-stu-id="2c577-142">In addition, saving this configuration as a template enables system administrators to collect the same log on other computers without repeating the data collector selection and scheduling processes.</span></span> <span data-ttu-id="2c577-143">パフォーマンスログと警告機能は、任意のデータコレクターセットで使用するために、Windows 信頼性およびパフォーマンスモニターに組み込まれました。</span><span class="sxs-lookup"><span data-stu-id="2c577-143">Performance Logs and Alerts features were incorporated into the Windows Reliability and Performance Monitor for use with any Data Collector Set.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

