---
title: 'Lync Server 2013: イベントログの確認'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Checking event logs
ms:assetid: 5500720d-c628-4dbd-84bc-a5becc39b99c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720914(v=OCS.15)
ms:contentKeyID: 63969602
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: edbd977eb8023d5001a5b8e4a6a1c706eea84fc4
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/16/2020
ms.locfileid: "48526194"
---
# <a name="checking-event-logs-in-lync-server-2013"></a><span data-ttu-id="b9b21-102">Lync Server 2013 でのイベントログの確認</span><span class="sxs-lookup"><span data-stu-id="b9b21-102">Checking event logs in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b9b21-103">_**トピックの最終更新日:** 2014-08-06_</span><span class="sxs-lookup"><span data-stu-id="b9b21-103">_**Topic Last Modified:** 2014-08-06_</span></span>

<span data-ttu-id="b9b21-104">[Windows イベントビューアー](https://go.microsoft.com/fwlink/p/?linkid=314067)を使用して、イベントログを表示したり、サービスの障害、AD DS のレプリケーションエラー、および仮想メモリやディスク容量などのシステムリソースに関する警告を取得したりできます。</span><span class="sxs-lookup"><span data-stu-id="b9b21-104">You can use [Windows Event Viewer](https://go.microsoft.com/fwlink/p/?linkid=314067) to view event logs and obtain information about service failures, replication errors in the AD DS, and warnings about system resources such as virtual memory and disk space.</span></span> <span data-ttu-id="b9b21-105">イベントビューアーは、Windows Server 2008 および2012に含まれています。</span><span class="sxs-lookup"><span data-stu-id="b9b21-105">Event Viewer is included with Windows Server 2008 and 2012.</span></span>

<span data-ttu-id="b9b21-106">Lync Server 2013 ログツールで、デバッグセッションを終了するときに、Snooper ツールを使用してログファイルを表示するには、[ **ログファイルの分析** ] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b9b21-106">In the Lync Server 2013 Logging Tool, when you end the debug session, click **Analyze Log Files** to view the log files by using the Snooper tool.</span></span>

<span data-ttu-id="b9b21-107">イベントビューアーは、アプリケーション、セキュリティ、およびシステムイベントに関するログをコンピューターに保持します。</span><span class="sxs-lookup"><span data-stu-id="b9b21-107">Event Viewer maintains logs about application, security, and system events on the computer.</span></span> <span data-ttu-id="b9b21-108">Lync Server 2013 と Windows は両方とも、イベントログに警告とエラーの状態を報告します。</span><span class="sxs-lookup"><span data-stu-id="b9b21-108">Both Lync Server 2013 and Windows report warnings and error conditions to the event logs.</span></span> <span data-ttu-id="b9b21-109">そのため、毎日イベントログを確認します。</span><span class="sxs-lookup"><span data-stu-id="b9b21-109">Therefore, review event logs daily.</span></span>

<span data-ttu-id="b9b21-110">イベントビューアーを使用して、次のことを行います。</span><span class="sxs-lookup"><span data-stu-id="b9b21-110">Use Event Viewer to:</span></span>

  - <span data-ttu-id="b9b21-111">イベントログを表示および管理します。</span><span class="sxs-lookup"><span data-stu-id="b9b21-111">View and manage event logs.</span></span>

  - <span data-ttu-id="b9b21-112">解決する必要があるハードウェア、ソフトウェア、およびシステムの問題に関する情報を取得します。</span><span class="sxs-lookup"><span data-stu-id="b9b21-112">Obtain information about hardware, software, and system issues that must be resolved.</span></span>

  - <span data-ttu-id="b9b21-113">今後のアクションを必要とする傾向を特定します。</span><span class="sxs-lookup"><span data-stu-id="b9b21-113">Identify trends that require future action.</span></span>

<span data-ttu-id="b9b21-114">Windows Server オペレーティングシステムで Lync Server を実行しているサーバーは、次の4種類のログにイベントを記録します。</span><span class="sxs-lookup"><span data-stu-id="b9b21-114">A server that is running Lync Server on a Windows Server operating system records events in four types of logs:</span></span>

  - <span data-ttu-id="b9b21-115">**アプリケーションログ**    アプリケーションログには、アプリケーションまたはプログラムによって記録されたイベントが含まれます。</span><span class="sxs-lookup"><span data-stu-id="b9b21-115">**Application logs**   The Application log contains events logged by applications or programs.</span></span> <span data-ttu-id="b9b21-116">開発者は、どのイベントをログに記録するかを決定します。</span><span class="sxs-lookup"><span data-stu-id="b9b21-116">Developers determine which events to log.</span></span> <span data-ttu-id="b9b21-117">たとえば、データベースプログラムでは、アプリケーションログにファイルエラーが記録されることがあります。</span><span class="sxs-lookup"><span data-stu-id="b9b21-117">For example, a database program might record a file error in the Application log.</span></span> <span data-ttu-id="b9b21-118">ほとんどの Lync Server 2013 関連イベントは、アプリケーションログに記録されます。</span><span class="sxs-lookup"><span data-stu-id="b9b21-118">Most Lync Server 2013-related events appear in the Application log.</span></span>

  - <span data-ttu-id="b9b21-119">**セキュリティログ**    セキュリティログには、ファイルやその他のオブジェクトの作成、オープン、削除などのリソース使用に関連するイベントに加えて、有効かつ無効なログオン試行などのイベントが記録されます。</span><span class="sxs-lookup"><span data-stu-id="b9b21-119">**Security logs**   The Security log records events such as valid and not valid logon tries in addition to events related to resource use such as creating, opening, or deleting files or other objects.</span></span> <span data-ttu-id="b9b21-120">たとえば、ログオン監査が有効になっている場合、システムへのログオン試行はセキュリティログに記録されます。</span><span class="sxs-lookup"><span data-stu-id="b9b21-120">For example, if logon auditing is enabled, attempts to log on to the system are recorded in the Security log.</span></span>

  - <span data-ttu-id="b9b21-121">**システムログ**    システムログには、Windows システムコンポーネントによって記録されたイベントが含まれます。</span><span class="sxs-lookup"><span data-stu-id="b9b21-121">**System logs**   The System log contains events logged by Windows system components.</span></span> <span data-ttu-id="b9b21-122">たとえば、起動時に読み込まれるドライバーまたはその他のシステムコンポーネントの障害は、システムログに記録されます。</span><span class="sxs-lookup"><span data-stu-id="b9b21-122">For example, the failure of a driver or other system component to load during startup is recorded in the System log.</span></span> <span data-ttu-id="b9b21-123">システムコンポーネントによってログに記録されるイベントの種類は、サーバーによってあらかじめ決められています。</span><span class="sxs-lookup"><span data-stu-id="b9b21-123">The event types logged by system components are predetermined by the server.</span></span>

  - <span data-ttu-id="b9b21-124">**Lync Server 2013**    ログツールは、認証、接続、ユーザー操作に関連する重要なイベントを記録します。</span><span class="sxs-lookup"><span data-stu-id="b9b21-124">**Lync Server 2013**   The logging tool records significant events related to authentication, connections, and user actions.</span></span> <span data-ttu-id="b9b21-125">診断ログを有効にした後、ログエントリをイベントビューアーで表示できます。</span><span class="sxs-lookup"><span data-stu-id="b9b21-125">After enabling diagnostic logging, you can view the log entries in Event Viewer.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="b9b21-126">Microsoft カスタマーサポートサービスから指示があった場合を除いて、[最大ログ出力] の設定は使用しないことをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="b9b21-126">We do not recommend that you use the maximum logging settings unless you are instructed to do this by Microsoft Customer Support Services.</span></span> <span data-ttu-id="b9b21-127">最大ログは大量のリソースを消費することがあり、多くの "誤検知" を与える可能性があります。エラーは、最大ログ出力でのみ記録されますが、実際には問題の原因ではないと考えられます。</span><span class="sxs-lookup"><span data-stu-id="b9b21-127">Maximum logging drains significant resources and can give many “false positives,” that is, errors that get logged only at maximum logging but are really expected and are not a cause of concern.</span></span> <span data-ttu-id="b9b21-128">また、診断ログを完全に有効にしないことをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="b9b21-128">We also recommend that you do not enable diagnostic logging permanently.</span></span> <span data-ttu-id="b9b21-129">トラブルシューティング時にのみ使用します。</span><span class="sxs-lookup"><span data-stu-id="b9b21-129">Use it only when troubleshooting.</span></span>



</div>

<span data-ttu-id="b9b21-130">各イベントビューアーログで、Lync Server 2013 は情報イベント、警告イベント、およびエラーイベントを記録します。</span><span class="sxs-lookup"><span data-stu-id="b9b21-130">Within each Event Viewer log, Lync Server 2013 records informational, warning, and error events.</span></span> <span data-ttu-id="b9b21-131">これらのログを注意深く監視して、Lync Server 2013 サーバー上で実行されているトランザクションの種類を追跡します。</span><span class="sxs-lookup"><span data-stu-id="b9b21-131">Monitor these logs closely to track the types of transactions being conducted on the Lync Server 2013 servers.</span></span> <span data-ttu-id="b9b21-132">ログを定期的にアーカイブするか、または自動ロールオーバーを使用して、空き領域が不足しないようにしてください。</span><span class="sxs-lookup"><span data-stu-id="b9b21-132">You should periodically archive the logs or use automatic rollover to avoid running out of space.</span></span> <span data-ttu-id="b9b21-133">ログファイルは、有限の容量を占有することがあるため、ログのサイズを増やし (たとえば、50 MB に)、上書きするように設定して、Lync Server 2013 サーバーが新しいイベントを引き続き書き込むことができるようにします。</span><span class="sxs-lookup"><span data-stu-id="b9b21-133">Because log files can occupy a finite amount of space, increase the log size (for example, to 50 MB) and set it to overwrite so that the Lync Server 2013 Server can continue to write new events.</span></span>

<span data-ttu-id="b9b21-134">次のツールとテクノロジを使用して、イベントログの管理を自動化することもできます。</span><span class="sxs-lookup"><span data-stu-id="b9b21-134">You can also automate event log administration by using the following tools and technologies:</span></span>

  - <span data-ttu-id="b9b21-135">System Center Operations Manager は、Lync Server 2013 サーバーの正常性と使用状況を監視します。</span><span class="sxs-lookup"><span data-stu-id="b9b21-135">System Center Operations Manager monitors the health and use of Lync Server 2013 servers.</span></span> <span data-ttu-id="b9b21-136">Lync server 2013 Operations Manager 用管理パックは、Lync Server 2013 を実行しているサーバーに特別な監視を提供することによって、Operations Manager を拡張します。</span><span class="sxs-lookup"><span data-stu-id="b9b21-136">Lync Server 2013 Management Pack for Operations Manager extends Operations Manager by providing specialized monitoring for servers that are running Lync Server 2013.</span></span>

  - <span data-ttu-id="b9b21-137">Operations Manager 用 Lync Server 2013 管理パックは、Lync Server 2013 の Standard Edition および Enterprise Edition を監視します。</span><span class="sxs-lookup"><span data-stu-id="b9b21-137">The Lync Server 2013 Management Pack for Operations Manager monitors Standard and Enterprise Edition of Lync Server 2013.</span></span> <span data-ttu-id="b9b21-138">このリリースには、以前は個別の管理パックであった QoE (Quality of Experience) 管理パックも組み込まれています。</span><span class="sxs-lookup"><span data-stu-id="b9b21-138">This release also incorporates the Quality of Experience (QoE) Management Pack which was previously a separate management pack.</span></span>

<span data-ttu-id="b9b21-139">監視対象の種類は、イベントログエントリ、パフォーマンスカウンター、QoE のステートフル監視です。</span><span class="sxs-lookup"><span data-stu-id="b9b21-139">Monitored types are event log entries, performance counters and stateful monitoring of QoE.</span></span> <span data-ttu-id="b9b21-140">このバージョンの管理パックは、Lync Server 2013 および2010のみを監視し、Office Communications Server 2007 を監視するために使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="b9b21-140">This version of the management pack only monitors Lync Server 2013 and 2010, and cannot be used to monitor Office Communications Server 2007.</span></span>

<span data-ttu-id="b9b21-141">管理パックには、次の機能があります。</span><span class="sxs-lookup"><span data-stu-id="b9b21-141">The management pack provides the following features:</span></span>

  - <span data-ttu-id="b9b21-142">サービスに影響するイベントを示すアラート</span><span class="sxs-lookup"><span data-stu-id="b9b21-142">Alerts indicating service affecting events</span></span>

  - <span data-ttu-id="b9b21-143">構成、およびその他のサービス以外の影響に関する問題を示すアラート</span><span class="sxs-lookup"><span data-stu-id="b9b21-143">Alerts indicating configuration, and other non-service impacting issues</span></span>

  - <span data-ttu-id="b9b21-144">Lync Server サービスの状態監視</span><span class="sxs-lookup"><span data-stu-id="b9b21-144">State monitoring of Lync Server services</span></span>

  - <span data-ttu-id="b9b21-145">製品ナレッジ: 特定された問題の原因と解決策</span><span class="sxs-lookup"><span data-stu-id="b9b21-145">Product knowledge: Cause and resolution of identified issues</span></span>

<span data-ttu-id="b9b21-146">Lync Server 2013 管理パックの詳細については、「 [System Center Operations Manager で Lync server 2013 を監視](lync-server-2013-monitoring-lync-server-with-system-center-operations-manager.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b9b21-146">For more information about Lync Server 2013 Management Pack, refer to [Monitoring Lync Server 2013 with System Center Operations Manager](lync-server-2013-monitoring-lync-server-with-system-center-operations-manager.md).</span></span>

<span data-ttu-id="b9b21-147">**イベントのくし形**    イベントマス目ツールは、複数のコンピューターのイベントログから特定のイベントを1か所にまとめて収集します。</span><span class="sxs-lookup"><span data-stu-id="b9b21-147">**Event Comb**   The Event Comb tool collects specific events from the event logs of several computers to one central location.</span></span> <span data-ttu-id="b9b21-148">指定したイベント Id またはイベントソースのみを報告することができます。</span><span class="sxs-lookup"><span data-stu-id="b9b21-148">It lets you report on only the event IDs or event sources it specifies.</span></span> <span data-ttu-id="b9b21-149">イベントの詳細については、「 [アカウントのロックアウトおよび管理ツール](https://go.microsoft.com/fwlink/?linkid=35607) の web サイト」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b9b21-149">For more information about Event Comb, see the [Account Lockout and Management Tools](https://go.microsoft.com/fwlink/?linkid=35607) website.</span></span>

<span data-ttu-id="b9b21-150">**イベントトリガー**    Windows Server 2012 では、管理者がプログラムを実行したり、電子メールメッセージを送信したり、画面上のメッセージを表示したりすることができます。</span><span class="sxs-lookup"><span data-stu-id="b9b21-150">**Event triggers**   In Windows Server 2012 you can "Attach a Task to This Event" within the Windows Event Viewer—where an administrator can either run a program, send an email message or display an on-screen message.</span></span> <span data-ttu-id="b9b21-151">この機能の詳細については、「Windows Server 2008 R2 のトピック」を参照してください。特定のイベントへの応答として [タスクを実行](https://technet.microsoft.com/library/cc748900.aspx)します。</span><span class="sxs-lookup"><span data-stu-id="b9b21-151">For more information about this feature, see the Windows Server 2008 R2 topic [Run a Task in Response to a Given Event](https://technet.microsoft.com/library/cc748900.aspx).</span></span> <span data-ttu-id="b9b21-152">また、' Eventtrigger.exe ' などのコマンドラインツールを使用して、イベントログを作成および照会したり、特定のログイベントにプログラムを関連付けしたりすることもできます。</span><span class="sxs-lookup"><span data-stu-id="b9b21-152">You can also use command-line tools such as ‘Eventtrigger.exe’ to create and query event logs and associate programs with particular logged events.</span></span> <span data-ttu-id="b9b21-153">Eventtriggers.exe を使用すると、特定のイベントが発生したときにプログラムを実行するイベントトリガーを作成できます。</span><span class="sxs-lookup"><span data-stu-id="b9b21-153">By using Eventtriggers.exe, you can create event triggers that run programs when specific events occur.</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="b9b21-154">関連項目</span><span class="sxs-lookup"><span data-stu-id="b9b21-154">See Also</span></span>


[<span data-ttu-id="b9b21-155">Windows イベントビューアー</span><span class="sxs-lookup"><span data-stu-id="b9b21-155">Windows Event Viewer</span></span>](https://go.microsoft.com/fwlink/p/?linkid=314067)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

