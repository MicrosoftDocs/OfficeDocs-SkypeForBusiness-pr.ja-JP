---
title: 'Lync Server 2013: 集中ログサービスの使用'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Using the Centralized Logging Service
ms:assetid: 7b05aaef-f0ea-4649-ba8a-02e68b0cdf23
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688101(v=OCS.15)
ms:contentKeyID: 49733700
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1a5aa8e93bed162219da1ad522483d61b003a603
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/21/2020
ms.locfileid: "42212683"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="using-the-centralized-logging-service-in-lync-server-2013"></a><span data-ttu-id="6c523-102">Lync Server 2013 での集中ログサービスの使用</span><span class="sxs-lookup"><span data-stu-id="6c523-102">Using the Centralized Logging Service in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6c523-103">_**トピックの最終更新日:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="6c523-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="6c523-104">集中ログサービスは、Lync Server 2013 の新機能です。</span><span class="sxs-lookup"><span data-stu-id="6c523-104">The Centralized Logging Service is a new feature in Lync Server 2013.</span></span> <span data-ttu-id="6c523-105">以前のリリースで提供されていた **OCSLogger** および **OCSTracer** ツールを拡張したものです。</span><span class="sxs-lookup"><span data-stu-id="6c523-105">It is an enhanced replacement for the **OCSLogger** and **OCSTracer** tools that were provided in previous releases.</span></span> <span data-ttu-id="6c523-106">集中ログサービスを使用して、次のタスクを実行できます。</span><span class="sxs-lookup"><span data-stu-id="6c523-106">You can use the Centralized Logging Service to perform the following tasks:</span></span>

  - <span data-ttu-id="6c523-107">1 つの場所とコマンドから、1 つ以上のコンピューターおよびプールでログを開始します。</span><span class="sxs-lookup"><span data-stu-id="6c523-107">Start logging on one or more computers and pools from a single location and command.</span></span>

  - <span data-ttu-id="6c523-108">1 つの場所とコマンドから、1 つ以上のコンピューターおよびプールのログを停止します。</span><span class="sxs-lookup"><span data-stu-id="6c523-108">Stop logging on one or more computers and pools from a single location and command.</span></span>

  - <span data-ttu-id="6c523-p102">1 つ以上のコンピューターおよびプールで、1 つの場所とコマンドを検索します。検索コマンドを変更して、すべてのコンピューターで取得および格納されたログの集約全体を取得することも、特定のデータに絞り込んだ結果を取得することもできます。</span><span class="sxs-lookup"><span data-stu-id="6c523-p102">Search logs on one or more computers and pools for a single location and command. You can tailor the search command to return the entire aggregation of logs that were captured and stored on all machines, or return a trimmed-down result that captures specific data.</span></span>

  - <span data-ttu-id="6c523-111">ログ セッションの構成は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="6c523-111">Configure logging sessions as follows:</span></span>
    
      - <span data-ttu-id="6c523-112">**シナリオ**を定義するか、既定のシナリオを使用します。</span><span class="sxs-lookup"><span data-stu-id="6c523-112">Define a **Scenario**, or use a default scenario.</span></span> <span data-ttu-id="6c523-113">集中ログサービスの*シナリオ*は、範囲 (グローバルまたはサイト)、シナリオ名、および1つ以上のプロバイダーで構成されます。</span><span class="sxs-lookup"><span data-stu-id="6c523-113">A *scenario* in Centralized Logging Service is made up of scope (global or site), a scenario name to identify the purpose of the scenario, and one or more providers.</span></span> <span data-ttu-id="6c523-114">1 台のコンピューターで同時に 2 つのシナリオを実行できます。</span><span class="sxs-lookup"><span data-stu-id="6c523-114">You can run two scenarios at any given time on a computer.</span></span>
    
      - <span data-ttu-id="6c523-p104">既存のプロバイダー\*\* を使用するか、新しいプロバイダーを作成します。プロバイダー\*\* では、ログ セッションが収集するもの、詳細さのレベル、追跡するコンポーネント、適用されるフラグを定義します。</span><span class="sxs-lookup"><span data-stu-id="6c523-p104">Use an existing *provider* or create a new provider. A *provider* defines what the logging session collects, what level of detail, what components to trace, and what flags are applied.</span></span>
        
        <div>
        

        > [!TIP]  
        > <span data-ttu-id="6c523-117">OCSLogger を使用したことがあれば、プロバイダー<EM></EM>は、<STRONG>コンポーネント</STRONG>のコレクション (S4、SIPStack など)、<STRONG>ログ タイプ</STRONG> (WPP、EventLog、IIS ログファイルなど)、<STRONG>トレース レベル</STRONG> (すべて、詳細、デバッグなど)、<STRONG>フラグ</STRONG> (TF_COMPONENT、TF_DIAG など) に相当します。</span><span class="sxs-lookup"><span data-stu-id="6c523-117">If you are familiar with OCSLogger, the term <EM>providers</EM> refers to the collection of <STRONG>components</STRONG> (for example, S4, SIPStack), a <STRONG>logging type</STRONG> (for example, WPP, EventLog, or IIS logfile), a <STRONG>tracing level</STRONG> (for example, All, verbose, debug), and <STRONG>flags</STRONG> (for example, TF_COMPONENT, TF_DIAG).</span></span> <span data-ttu-id="6c523-118">これらのアイテムは、プロバイダー (Windows PowerShell 変数) で定義され、集中ログサービスコマンドに渡されます。</span><span class="sxs-lookup"><span data-stu-id="6c523-118">These items are defined in the provider (a Windows PowerShell variable) and passed into the Centralized Logging Service command.</span></span>

        
        </div>
    
      - <span data-ttu-id="6c523-119">ログを収集するコンピューターおよびプールを構成します。</span><span class="sxs-lookup"><span data-stu-id="6c523-119">Configure the computers and pools that you want to collect logs from.</span></span>
    
      - <span data-ttu-id="6c523-120">ログ セッションの対象範囲を、**サイト** (そのサイトのコンピューターだけでログ キャプチャを実行します) または**グローバル** (展開のすべてのコンピューターでログ キャプチャを実行します) から定義します。</span><span class="sxs-lookup"><span data-stu-id="6c523-120">Define the scope for the logging session from the options **Site** (run logging captures on computers in that site only), or **Global** (run logging capture on all computers in the deployment).</span></span>

<span data-ttu-id="6c523-121">集中ログサービスは非常に強力であり、問題のトラブルシューティングに関するほぼすべてのニーズを満たすことができます (大規模または小規模)。</span><span class="sxs-lookup"><span data-stu-id="6c523-121">The Centralized Logging Service is extremely powerful and can meet nearly all of the needs for troubleshooting problems—large or small.</span></span> <span data-ttu-id="6c523-122">根本原因の分析からパフォーマンスの問題まで、集中ログサービスは任意の管理者にとって重要なツールとなります。</span><span class="sxs-lookup"><span data-stu-id="6c523-122">From root cause analysis to performance problems, the Centralized Logging Service can be an important tool for any administrator.</span></span> <span data-ttu-id="6c523-123">すべての例は、Lync Server 管理シェルを使用して表示されます。</span><span class="sxs-lookup"><span data-stu-id="6c523-123">All examples are shown using the Lync Server Management Shell.</span></span> <span data-ttu-id="6c523-124">**Clscontroller**という名前の集中ログサービス用のコマンドラインコンポーネントがあります。</span><span class="sxs-lookup"><span data-stu-id="6c523-124">There is a command-line component for the Centralized Logging Service called **CLSController.exe**.</span></span> <span data-ttu-id="6c523-125">ヘルプはコマンドライン ツール自体で提供されています。</span><span class="sxs-lookup"><span data-stu-id="6c523-125">Help is provided for the command-line tool through the tool itself.</span></span> <span data-ttu-id="6c523-126">ただし、コマンド ラインから実行できる限られた機能のセットがあります。</span><span class="sxs-lookup"><span data-stu-id="6c523-126">However, there is a limited set of functions that you can execute from the command line.</span></span> <span data-ttu-id="6c523-127">Lync Server 管理シェルを使用すると、はるかに多くの構成可能な機能セットにアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="6c523-127">By using Lync Server Management Shell, you have access to a much larger and much more configurable set of features.</span></span> <span data-ttu-id="6c523-128">集中ログサービスを使用する場合は、常に Lync Server 管理シェルを最初に検討する方法として考慮する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6c523-128">You should always consider Lync Server Management Shell as the first and foremost method when using the Centralized Logging Service.</span></span>

<span data-ttu-id="6c523-129">このセクションのトピックでは、集中ログサービスを使用する方法と、さまざまな機能の使用方法の例について説明します。</span><span class="sxs-lookup"><span data-stu-id="6c523-129">The topics in this section explain how to use the Centralized Logging Service and examples of how to use its many features.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="6c523-130">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="6c523-130">In This Section</span></span>

  - [<span data-ttu-id="6c523-131">Lync Server 2013 の集中ログサービスの概要</span><span class="sxs-lookup"><span data-stu-id="6c523-131">Overview of the Centralized Logging Service in Lync Server 2013</span></span>](lync-server-2013-overview-of-the-centralized-logging-service.md)

  - [<span data-ttu-id="6c523-132">Lync Server 2013 での集中ログサービスの構成設定の管理</span><span class="sxs-lookup"><span data-stu-id="6c523-132">Managing the Centralized Logging Service configuration settings in Lync Server 2013</span></span>](lync-server-2013-managing-the-centralized-logging-service-configuration-settings.md)

  - [<span data-ttu-id="6c523-133">Lync Server 2013 での集中ログサービスの構成設定について</span><span class="sxs-lookup"><span data-stu-id="6c523-133">Understanding Centralized Logging Service configuration settings in Lync Server 2013</span></span>](lync-server-2013-understanding-centralized-logging-service-configuration-settings.md)

  - [<span data-ttu-id="6c523-134">Lync Server 2013 でログをキャプチャするための集中ログサービスの Start の使用</span><span class="sxs-lookup"><span data-stu-id="6c523-134">Using Start for the Centralized Logging Service to capture logs in Lync Server 2013</span></span>](lync-server-2013-using-start-for-the-centralized-logging-service-to-capture-logs.md)

  - [<span data-ttu-id="6c523-135">Lync Server 2013 での集中ログサービスの Stop の使用</span><span class="sxs-lookup"><span data-stu-id="6c523-135">Using Stop for the Centralized Logging Service in Lync Server 2013</span></span>](lync-server-2013-using-stop-for-the-centralized-logging-service.md)

  - [<span data-ttu-id="6c523-136">Lync Server 2013 での集中ログサービスによって作成されたキャプチャログでの検索の使用</span><span class="sxs-lookup"><span data-stu-id="6c523-136">Using search on capture logs created by the Centralized Logging Service in Lync Server 2013</span></span>](lync-server-2013-using-search-on-capture-logs-created-by-the-centralized-logging-service.md)

  - [<span data-ttu-id="6c523-137">Lync Server 2013 の集中ログサービスからキャプチャログを読み取る</span><span class="sxs-lookup"><span data-stu-id="6c523-137">Reading capture logs from the Centralized Logging Service in Lync Server 2013</span></span>](lync-server-2013-reading-capture-logs-from-the-centralized-logging-service.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

