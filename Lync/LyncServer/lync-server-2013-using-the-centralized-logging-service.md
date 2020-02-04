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
ms.openlocfilehash: 2fb3687d036f7d72160c8af0e168a40d09c84e4b
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41743977"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="using-the-centralized-logging-service-in-lync-server-2013"></a><span data-ttu-id="513c0-102">Lync Server 2013 での一元管理ログサービスの使用</span><span class="sxs-lookup"><span data-stu-id="513c0-102">Using the Centralized Logging Service in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="513c0-103">_**最終更新日:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="513c0-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="513c0-104">一元管理のログサービスは、Lync Server 2013 の新機能です。</span><span class="sxs-lookup"><span data-stu-id="513c0-104">The Centralized Logging Service is a new feature in Lync Server 2013.</span></span> <span data-ttu-id="513c0-105">これは、以前のリリースで提供された**Ocslogger**と**ocslogger**のツールの拡張機能です。</span><span class="sxs-lookup"><span data-stu-id="513c0-105">It is an enhanced replacement for the **OCSLogger** and **OCSTracer** tools that were provided in previous releases.</span></span> <span data-ttu-id="513c0-106">一元ログサービスを使用して、次のタスクを実行することができます。</span><span class="sxs-lookup"><span data-stu-id="513c0-106">You can use the Centralized Logging Service to perform the following tasks:</span></span>

  - <span data-ttu-id="513c0-107">1つまたは複数のコンピューターとプールで、1つの場所とコマンドからのログの記録を開始します。</span><span class="sxs-lookup"><span data-stu-id="513c0-107">Start logging on one or more computers and pools from a single location and command.</span></span>

  - <span data-ttu-id="513c0-108">1つまたは複数のコンピューターとプールのログの記録を1つの場所とコマンドから停止します。</span><span class="sxs-lookup"><span data-stu-id="513c0-108">Stop logging on one or more computers and pools from a single location and command.</span></span>

  - <span data-ttu-id="513c0-109">1つまたは複数のコンピューターとプールでログを検索し、1つの場所とコマンドを特定します。</span><span class="sxs-lookup"><span data-stu-id="513c0-109">Search logs on one or more computers and pools for a single location and command.</span></span> <span data-ttu-id="513c0-110">[検索] コマンドをカスタマイズして、すべてのコンピューターに保存されているログの総計を返すことも、特定のデータをキャプチャするトリムダウン結果を返すこともできます。</span><span class="sxs-lookup"><span data-stu-id="513c0-110">You can tailor the search command to return the entire aggregation of logs that were captured and stored on all machines, or return a trimmed-down result that captures specific data.</span></span>

  - <span data-ttu-id="513c0-111">ログ セッションの構成は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="513c0-111">Configure logging sessions as follows:</span></span>
    
      - <span data-ttu-id="513c0-112">**シナリオ**を定義するか、既定のシナリオを使用します。</span><span class="sxs-lookup"><span data-stu-id="513c0-112">Define a **Scenario**, or use a default scenario.</span></span> <span data-ttu-id="513c0-113">一元管理サービスの*シナリオ*は、スコープ (グローバルまたはサイト) で構成されています。シナリオ名は、そのシナリオの目的と1つ以上のプロバイダーを識別するために用意されています。</span><span class="sxs-lookup"><span data-stu-id="513c0-113">A *scenario* in Centralized Logging Service is made up of scope (global or site), a scenario name to identify the purpose of the scenario, and one or more providers.</span></span> <span data-ttu-id="513c0-114">コンピューターでは、いつでも2つのシナリオを実行できます。</span><span class="sxs-lookup"><span data-stu-id="513c0-114">You can run two scenarios at any given time on a computer.</span></span>
    
      - <span data-ttu-id="513c0-p104">既存のプロバイダー\*\* を使用するか、新しいプロバイダーを作成します。プロバイダー\*\* では、ログ セッションが収集するもの、詳細さのレベル、追跡するコンポーネント、適用されるフラグを定義します。</span><span class="sxs-lookup"><span data-stu-id="513c0-p104">Use an existing *provider* or create a new provider. A *provider* defines what the logging session collects, what level of detail, what components to trace, and what flags are applied.</span></span>
        
        <div>
        

        > [!TIP]  
        > <span data-ttu-id="513c0-117">OCSLogger を使用したことがあれば、プロバイダー<EM></EM>は、<STRONG>コンポーネント</STRONG>のコレクション (S4、SIPStack など)、<STRONG>ログ タイプ</STRONG> (WPP、EventLog、IIS ログファイルなど)、<STRONG>トレース レベル</STRONG> (すべて、詳細、デバッグなど)、<STRONG>フラグ</STRONG> (TF_COMPONENT、TF_DIAG など) に相当します。</span><span class="sxs-lookup"><span data-stu-id="513c0-117">If you are familiar with OCSLogger, the term <EM>providers</EM> refers to the collection of <STRONG>components</STRONG> (for example, S4, SIPStack), a <STRONG>logging type</STRONG> (for example, WPP, EventLog, or IIS logfile), a <STRONG>tracing level</STRONG> (for example, All, verbose, debug), and <STRONG>flags</STRONG> (for example, TF_COMPONENT, TF_DIAG).</span></span> <span data-ttu-id="513c0-118">これらの項目は、プロバイダー (Windows PowerShell 変数) で定義され、中央の [ログサービス] コマンドに渡されます。</span><span class="sxs-lookup"><span data-stu-id="513c0-118">These items are defined in the provider (a Windows PowerShell variable) and passed into the Centralized Logging Service command.</span></span>

        
        </div>
    
      - <span data-ttu-id="513c0-119">ログを収集するコンピューターとプールを構成します。</span><span class="sxs-lookup"><span data-stu-id="513c0-119">Configure the computers and pools that you want to collect logs from.</span></span>
    
      - <span data-ttu-id="513c0-120">[オプション]**サイト**(そのサイト内のコンピューター上のログキャプチャの実行) または [**グローバル**] (展開のすべてのコンピューターでログのキャプチャを実行する) のログセッションのスコープを定義します。</span><span class="sxs-lookup"><span data-stu-id="513c0-120">Define the scope for the logging session from the options **Site** (run logging captures on computers in that site only), or **Global** (run logging capture on all computers in the deployment).</span></span>

<span data-ttu-id="513c0-121">一元的なログサービスは非常に強力であり、問題のトラブルシューティングを行うために、大規模または小規模のニーズをすべて満たすことができます。</span><span class="sxs-lookup"><span data-stu-id="513c0-121">The Centralized Logging Service is extremely powerful and can meet nearly all of the needs for troubleshooting problems—large or small.</span></span> <span data-ttu-id="513c0-122">根本原因の分析からパフォーマンスの問題を解決するために、一元管理サービスは、どの管理者にとっても重要なツールである場合があります。</span><span class="sxs-lookup"><span data-stu-id="513c0-122">From root cause analysis to performance problems, the Centralized Logging Service can be an important tool for any administrator.</span></span> <span data-ttu-id="513c0-123">すべての例は、Lync Server 管理シェルを使用して表示されます。</span><span class="sxs-lookup"><span data-stu-id="513c0-123">All examples are shown using the Lync Server Management Shell.</span></span> <span data-ttu-id="513c0-124">一元管理されたログサービスのコマンドラインコンポーネントが、" **Clscontroller .exe**" と呼ばれています。</span><span class="sxs-lookup"><span data-stu-id="513c0-124">There is a command-line component for the Centralized Logging Service called **CLSController.exe**.</span></span> <span data-ttu-id="513c0-125">ツール自体を通じてコマンドラインツールのヘルプが提供されます。</span><span class="sxs-lookup"><span data-stu-id="513c0-125">Help is provided for the command-line tool through the tool itself.</span></span> <span data-ttu-id="513c0-126">ただし、コマンドラインから実行できる関数のセットは限られています。</span><span class="sxs-lookup"><span data-stu-id="513c0-126">However, there is a limited set of functions that you can execute from the command line.</span></span> <span data-ttu-id="513c0-127">Lync Server 管理シェルを使用すると、より広範で構成可能な機能セットにアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="513c0-127">By using Lync Server Management Shell, you have access to a much larger and much more configurable set of features.</span></span> <span data-ttu-id="513c0-128">一元管理サービスを使用する場合は、常に Lync Server 管理シェルを最初に考慮する方法として検討する必要があります。</span><span class="sxs-lookup"><span data-stu-id="513c0-128">You should always consider Lync Server Management Shell as the first and foremost method when using the Centralized Logging Service.</span></span>

<span data-ttu-id="513c0-129">このセクションのトピックでは、一元管理サービスの使用方法と、さまざまな機能の使い方の例について説明します。</span><span class="sxs-lookup"><span data-stu-id="513c0-129">The topics in this section explain how to use the Centralized Logging Service and examples of how to use its many features.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="513c0-130">このセクション中</span><span class="sxs-lookup"><span data-stu-id="513c0-130">In This Section</span></span>

  - [<span data-ttu-id="513c0-131">Lync Server 2013 の一元管理されたログサービスの概要</span><span class="sxs-lookup"><span data-stu-id="513c0-131">Overview of the Centralized Logging Service in Lync Server 2013</span></span>](lync-server-2013-overview-of-the-centralized-logging-service.md)

  - [<span data-ttu-id="513c0-132">Lync Server 2013 で中央集中ログサービスの構成設定を管理する</span><span class="sxs-lookup"><span data-stu-id="513c0-132">Managing the Centralized Logging Service configuration settings in Lync Server 2013</span></span>](lync-server-2013-managing-the-centralized-logging-service-configuration-settings.md)

  - [<span data-ttu-id="513c0-133">Lync Server 2013 の一元ログサービスの構成設定について</span><span class="sxs-lookup"><span data-stu-id="513c0-133">Understanding Centralized Logging Service configuration settings in Lync Server 2013</span></span>](lync-server-2013-understanding-centralized-logging-service-configuration-settings.md)

  - [<span data-ttu-id="513c0-134">Lync Server 2013 でログをキャプチャするために、一元ログサービスの開始を使用する</span><span class="sxs-lookup"><span data-stu-id="513c0-134">Using Start for the Centralized Logging Service to capture logs in Lync Server 2013</span></span>](lync-server-2013-using-start-for-the-centralized-logging-service-to-capture-logs.md)

  - [<span data-ttu-id="513c0-135">Lync Server 2013 の中央集中ログサービスに対して Stop を使用する</span><span class="sxs-lookup"><span data-stu-id="513c0-135">Using Stop for the Centralized Logging Service in Lync Server 2013</span></span>](lync-server-2013-using-stop-for-the-centralized-logging-service.md)

  - [<span data-ttu-id="513c0-136">Lync Server 2013 の中央集中ログサービスで作成されたキャプチャログでの検索の使用</span><span class="sxs-lookup"><span data-stu-id="513c0-136">Using search on capture logs created by the Centralized Logging Service in Lync Server 2013</span></span>](lync-server-2013-using-search-on-capture-logs-created-by-the-centralized-logging-service.md)

  - [<span data-ttu-id="513c0-137">Lync Server 2013 の一元ログサービスからのキャプチャログの読み取り</span><span class="sxs-lookup"><span data-stu-id="513c0-137">Reading capture logs from the Centralized Logging Service in Lync Server 2013</span></span>](lync-server-2013-reading-capture-logs-from-the-centralized-logging-service.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

