---
title: 'Lync Server 2013: オペレーティング システムの監視'
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
ms.openlocfilehash: 42ac03f61fca5717d279d39e703a8ffa97e8c2cf
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41756791"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="monitoring-operating-system-in-lync-server-2013"></a><span data-ttu-id="4c4c4-102">Lync Server 2013 でのオペレーティング システムの監視</span><span class="sxs-lookup"><span data-stu-id="4c4c4-102">Monitoring operating system in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4c4c4-103">_**最終更新日:** 2015-01-26_</span><span class="sxs-lookup"><span data-stu-id="4c4c4-103">_**Topic Last Modified:** 2015-01-26_</span></span>

<span data-ttu-id="4c4c4-104">Lync Server 2013 のすべてのサーバーとコンポーネントのパフォーマンスを監視する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4c4c4-104">You must monitor the performance of all servers and components in the Lync Server 2013.</span></span> <span data-ttu-id="4c4c4-105">当然ですが、最も重要なコンポーネントの 1 つはオペレーティング システム自体です。</span><span class="sxs-lookup"><span data-stu-id="4c4c4-105">Obviously, one of the most important components is the operating system itself.</span></span> <span data-ttu-id="4c4c4-106">Lync Server 2013 は、次の x64 エディションをサポートしています。</span><span class="sxs-lookup"><span data-stu-id="4c4c4-106">Lync Server 2013 supports x64 editions of:</span></span>

  - <span data-ttu-id="4c4c4-107">Windows Server 2008 R2</span><span class="sxs-lookup"><span data-stu-id="4c4c4-107">Windows Server 2008 R2</span></span>

  - <span data-ttu-id="4c4c4-108">Windows Server 2012 および Windows Server 2012 R2</span><span class="sxs-lookup"><span data-stu-id="4c4c4-108">Windows Server 2012 and Windows Server 2012 R2</span></span>

<span data-ttu-id="4c4c4-109">オペレーティングシステムを監視する最も透過的な方法は、Windows Server オペレーティングシステム管理パックを使用することです。</span><span class="sxs-lookup"><span data-stu-id="4c4c4-109">The most transparent way to monitor an operating system is by using Windows Server Operating System Management Pack.</span></span> <span data-ttu-id="4c4c4-110">Windows Server 2012、Windows server 2012 R2、Windows Server 2008 R2 を実行しているコンピューターのパフォーマンス、正常性、および可用性など、基本的な監視の基本を提供します。</span><span class="sxs-lookup"><span data-stu-id="4c4c4-110">It provides the fundamental monitoring basics, such as performance, health, and availability for computers that are running Windows Server 2012, Windows Server 2012 R2, and Windows Server 2008 R2.</span></span>

<span data-ttu-id="4c4c4-111">これらの管理パックは、重要なイベントと業績評価指標を検出、通知、自動応答することによって、問題の解決時間を短縮し、Windows サーバーを実行しているシステムの全体的な可用性とパフォーマンスを向上させます。オペレーティングシステム。</span><span class="sxs-lookup"><span data-stu-id="4c4c4-111">By detecting, alerting, and automatically responding to important events and performance indicators, these management packs reduce resolution times for issues and increase the overall availability and performance of systems that are running the Windows Server operating systems.</span></span>

<span data-ttu-id="4c4c4-112">System Center Operations Manager 用の Windows Server 管理パックとは別に、次のシステムツールとリソースを使用して、オペレーティングシステムの正常性を監視することができます (オペレーティングシステムのバージョンによって異なります)。</span><span class="sxs-lookup"><span data-stu-id="4c4c4-112">Apart from relevant Windows Server management packs for System Center Operations Manager, the following system tools and resources can be used to monitor the health of the operating system (depending on the operating system version).</span></span>

<div>

## <a name="windows-server2008r2"></a><span data-ttu-id="4c4c4-113">Windows Server 2008 R2</span><span class="sxs-lookup"><span data-stu-id="4c4c4-113">Windows Server 2008 R2</span></span>

<span data-ttu-id="4c4c4-114">Windows Server 2008 R2 には、管理者がオペレーティングシステムの基本的な監視と管理を支援するための、次の追加の機能とツールが含まれています。</span><span class="sxs-lookup"><span data-stu-id="4c4c4-114">Windows Server 2008 R2 includes the following additional features and tools to help administrators with basic operating system monitoring and management:</span></span>

  - <span data-ttu-id="4c4c4-p103">**リソース モニター** は、プロセスやサービスでシステム リソースがどのように使用されているかを確認できる高性能なツールです。リアルタイムでのリソースの使用状況の監視に加え、ファイル、コントロール プロセス、およびサービスを使用しているアプリケーションを特定します。</span><span class="sxs-lookup"><span data-stu-id="4c4c4-p103">**Windows Resource Monitor** is a powerful tool for understanding how system resources are used by processes and services. In addition to monitoring resource usage in real time, a Resource Monitor can help analyze unresponsive processes, identify which applications are using files, and control processes and services.</span></span>

  - <span data-ttu-id="4c4c4-p104">**信頼性分析コンポーネント** は、システムの使用状況および信頼性に関する詳細な経験情報を提供する受信箱形式のエージェントです。この情報は、WMI インターフェイスを通じて公開され、ポータブル リーダー システムで活用できます。信頼性分析コンポーネントを、WMI インターフェイスを通じて公開することにより、開発者はアプリケーションを監視および解析して信頼性やパフォーマンスを向上させることができます。</span><span class="sxs-lookup"><span data-stu-id="4c4c4-p104">**Reliability Analysis Component** is an in-box agent that provides detailed experience information on system usage and reliability. This information is exposed through a WMI interface to make it available for consumption by Portable Readers Systems. By exposing Reliability Analysis Component through a WMI interface, developers can monitor and analyze applications, increasing reliability and performance.</span></span>

  - <span data-ttu-id="4c4c4-120">**Windows Server 2008 R2**は、組み込みの信頼性分析コンポーネントを使って信頼性インデックスを計算します。これにより、システム全体の使用状況と安定性に関する情報が提供されます。</span><span class="sxs-lookup"><span data-stu-id="4c4c4-120">**Windows Server 2008 R2** uses the built-in Reliability Analysis Component to calculate a reliability index, which provides information about overall system usage and stability over time.</span></span> <span data-ttu-id="4c4c4-121">The Reliability Analysis Component also keeps track of any important changes to the system that are likely to influence stability, such as Windows updates and application installations.</span><span class="sxs-lookup"><span data-stu-id="4c4c4-121">The Reliability Analysis Component also keeps track of any important changes to the system that are likely to influence stability, such as Windows updates and application installations.</span></span>

</div>

<div>

## <a name="windows-server2008-windows-reliability-and-performance-monitor"></a><span data-ttu-id="4c4c4-122">Windows Server 2008 Windows 信頼性とパフォーマンスモニター</span><span class="sxs-lookup"><span data-stu-id="4c4c4-122">Windows Server 2008 Windows Reliability and Performance Monitor</span></span>

<span data-ttu-id="4c4c4-p106">Windows 信頼性およびパフォーマンス モニターはパフォーマンス ログと警告、サーバー パフォーマンス アドバイザー、およびシステム モニターなどの従来のスタンドアロン ツールの機能を組み合わせた MMC スナップインです。</span><span class="sxs-lookup"><span data-stu-id="4c4c4-p106">Windows Reliability and Performance Monitor is an MMC Snap-in that combines the functionality of previous stand-alone tools including Performance Logs and Alerts, Server Performance Advisor, and System Monitor. It provides a graphical interface for customizing performance data collection and Event Trace Sessions.</span></span>

<span data-ttu-id="4c4c4-125">これは、システムへの変更を追跡し、システムの安定性の変化を比較してこれらの関係をグラフ形式で表示する MMC スナップインである信頼性モニターも含んでいます。</span><span class="sxs-lookup"><span data-stu-id="4c4c4-125">It also includes Reliability Monitor, an MMC Snap-in that tracks changes to the system and compares them to changes in system stability, and it provides a graphical view of their relationship.</span></span>

</div>

<div>

## <a name="windows-reliability-and-performance-monitor"></a><span data-ttu-id="4c4c4-126">Windows 信頼性およびパフォーマンス モニター</span><span class="sxs-lookup"><span data-stu-id="4c4c4-126">Windows Reliability and Performance Monitor</span></span>

<span data-ttu-id="4c4c4-127">Windows の信頼性とパフォーマンスモニターは、パフォーマンスログと警告などの以前のスタンドアロンツールの機能を組み合わせたものですが、Windows Server 2008 には新しい機能も用意されています。Windows Server 2008 R2 (次のような)。</span><span class="sxs-lookup"><span data-stu-id="4c4c4-127">While Windows Reliability and Performance Monitor combine functionalities of some former stand-alone tools such as Performance Logs and Alerts, and System Monitor and Server Performance Advisor, it also provides some new functionality to Windows Server 2008 and Windows Server 2008 R2, such as the following:</span></span>

  - <span data-ttu-id="4c4c4-128">データ コレクター セット</span><span class="sxs-lookup"><span data-stu-id="4c4c4-128">Data Collector Sets</span></span>

  - <span data-ttu-id="4c4c4-129">リソース ビュー</span><span class="sxs-lookup"><span data-stu-id="4c4c4-129">Resource View</span></span>

  - <span data-ttu-id="4c4c4-130">信頼性モニター</span><span class="sxs-lookup"><span data-stu-id="4c4c4-130">Reliability Monitor</span></span>

  - <span data-ttu-id="4c4c4-131">ログ作成用のウィザードおよびテンプレート</span><span class="sxs-lookup"><span data-stu-id="4c4c4-131">Wizards and templates for creating logs</span></span>

<span data-ttu-id="4c4c4-p107">**データ コレクター セット**は、異なるパフォーマンス監視シナリオで使用できるようにデータ コレクターを再利用可能な要素にグループ分けします。データ コレクターのグループをデータ コレクター セットに格納した後、スケジュールなどの操作を、1 つのプロパティ変更を通じて全体のセットに適用できます。Windows 信頼性およびパフォーマンス モニターは既定のデータ コレクター セットテンプレートを含んでいます。これらのテンプレートは管理者がサーバーの役割や監視シナリオに固有のパフォーマンス データの収集をすぐに開始したいときに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="4c4c4-p107">**Data Collector Set** groups data collectors into reusable elements for use with different performance monitoring scenarios. After a group of data collectors are stored as a Data Collector Set, operations such as scheduling can be applied to the whole set through a single property change.Windows Reliability and Performance Monitor includes default Data Collector Set templates to help system administrators begin immediately collecting performance data that is specific to a server role or monitoring scenario.</span></span>

<span data-ttu-id="4c4c4-p108">Windows 信頼性およびパフォーマンス モニターのホーム ページは、新しい**リソース ビュー**画面で、CPU、ディスク、ネットワーク、メモリ使用量の概要をリアルタイムでグラフ形式で表示します。これらの監視対象要素を展開することにより、システム管理者はプロセスが使用しているリソースを特定できます。Windows の以前のバージョンでは、このリアルタイムのプロセス固有のデータはタスク マネージャーで限られた形式でのみ利用可能でした。</span><span class="sxs-lookup"><span data-stu-id="4c4c4-p108">The home page of Windows Reliability and Performance Monitor is the new **Resource View** screen, which provides a real-time graphical overview of CPU, disk, network, and memory usage. By expanding each of these monitored elements, system administrators can identify which processes are using which resources. In earlier versions of Windows, this real-time, process-specific data was available only in limited form in Task Manager.</span></span>

<span data-ttu-id="4c4c4-p109">**信頼性モニター** は予期しない問題によりシステムの信頼性が低下しているかどうかを反映するシステム安定性指標を計算します。安定性指標の経時変化のグラフでは、問題が発生し始めた日付をすばやく特定できます。付随するシステム安定性レポートは、信頼性が低下した原因のトラブルシューティングに役立つ詳細情報を提供します。システムに対する変更 (アプリケーションのインストールや削除、オペレーティング システムの更新、またはドライバーの追加または変更) とエラー (アプリケーション エラー、オペレーティング システムのクラッシュ、またはハードウェア エラー) を並べて表示することにより、問題に対応する戦略をすばやく作成できます。</span><span class="sxs-lookup"><span data-stu-id="4c4c4-p109">**Reliability Monitor** calculates a System Stability Index that reflects whether unexpected issues reduced the reliability of the system. A graph of the Stability Index over time quickly identifies dates when issues began to occur. The accompanying System Stability Report provides details to help troubleshoot the cause of reduced reliability. By viewing changes to the system (installation or removal of applications, updates to the operating system, or addition or modification of drivers) side by side with failures (application failures, operating system crashes, or hardware failures), a strategy for addressing the issues can be developed quickly.</span></span>

<span data-ttu-id="4c4c4-p110">ログ ファイルへのカウンターの追加や開始、停止、および期間のスケジュールを、**ウィザード インターフェイス**を通じて実行できるようになりました。さらに、この構成をテンプレートとして保存することにより、システム管理者はデータ コレクターの選択やプロセスのスケジュールを繰り返すことなく別のコンピューター上で同じログを収集できます。パフォーマンス ログと警告機能は、任意のデータ コレクター セットで使用できるように Windows 信頼性およびパフォーマンス モニターに統合されました。</span><span class="sxs-lookup"><span data-stu-id="4c4c4-p110">Adding counters to log files and scheduling their start, stop, and duration can now be performed through a **Wizard interface**. In addition, saving this configuration as a template enables system administrators to collect the same log on other computers without repeating the data collector selection and scheduling processes. Performance Logs and Alerts features were incorporated into the Windows Reliability and Performance Monitor for use with any Data Collector Set.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

