---
title: 'Lync Server 2013: 一元ログサービスの概要'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Overview of the Centralized Logging Service
ms:assetid: 975718a0-f3e3-404d-9453-6224e73bfdd0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688145(v=OCS.15)
ms:contentKeyID: 49733746
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 647e6b1e5797b3936dc1fef6023c85ce4baf68b7
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34825444"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="overview-of-the-centralized-logging-service-in-lync-server-2013"></a><span data-ttu-id="4159e-102">Lync Server 2013 の一元管理されたログサービスの概要</span><span class="sxs-lookup"><span data-stu-id="4159e-102">Overview of the Centralized Logging Service in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4159e-103">_**最終更新日:** 2013-02-22_</span><span class="sxs-lookup"><span data-stu-id="4159e-103">_**Topic Last Modified:** 2013-02-22_</span></span>

<span data-ttu-id="4159e-104">一元管理のログサービスは、広範または狭い範囲のデータの収集手段を提供するように設計されています。</span><span class="sxs-lookup"><span data-stu-id="4159e-104">The Centralized Logging Service is designed to provide a means for controlled collection of data—with a broad or narrow scope.</span></span> <span data-ttu-id="4159e-105">展開されているすべてのサーバーからデータを同時に収集したり、トレースするための特定の要素を定義したり、1台のコンピューターから、またはすべてのサーバーからすべてのデータをまとめて検索結果を返すことができます。</span><span class="sxs-lookup"><span data-stu-id="4159e-105">You can collect data from all servers in the deployment concurrently, define specific elements to trace, set trace flags and return search results from a single computer or an aggregation of all data from all servers.</span></span> <span data-ttu-id="4159e-106">一元的なログサービスは、展開されているすべてのサーバーで実行されます。</span><span class="sxs-lookup"><span data-stu-id="4159e-106">The Centralized Logging Service runs on all servers in your deployment.</span></span> <span data-ttu-id="4159e-107">一元ログサービスのアーキテクチャは、次のエージェントとサービスで構成されています。</span><span class="sxs-lookup"><span data-stu-id="4159e-107">The architecture of the Centralized Logging Service is comprised of the following agents and services:</span></span>

  - <span data-ttu-id="4159e-108">*一元管理サービスエージェント*   clsagent は、コントローラーと通信し、管理者によってコントローラーによって発行されたコマンドを受け取るサービス実行可能ファイルです。</span><span class="sxs-lookup"><span data-stu-id="4159e-108">*Centralized Logging Service Agent*   ClsAgent.exe is the service executable that communicates with the controller and receives the commands that the controller is issued by the administrator.</span></span> <span data-ttu-id="4159e-109">エージェントは、各 Lync Server コンピューターでサービスとして実行されます。</span><span class="sxs-lookup"><span data-stu-id="4159e-109">The agent is run as a service on each Lync Server computer.</span></span> <span data-ttu-id="4159e-110">エージェントは、コマンドを受け取ると、そのコマンドを実行し、トレース用に定義されたコンポーネントにメッセージを送信し、トレースログをディスクに書き込みます。</span><span class="sxs-lookup"><span data-stu-id="4159e-110">When the agent receives a command, it executes the command, sends messages to the defined components for tracing, and writes the trace logs to disk.</span></span> <span data-ttu-id="4159e-111">また、コンピューターのトレースログを読み取り、要求された場合にトレースデータをコントローラーに返します。</span><span class="sxs-lookup"><span data-stu-id="4159e-111">It also reads the trace logs for its computer and sends the trace data back to the controller when requested.</span></span> <span data-ttu-id="4159e-112">ClsAgent は、 **tcp 50001**、 **Tcp 50002**、 **tcp 50003**の各ポートでコマンドをリッスンします。</span><span class="sxs-lookup"><span data-stu-id="4159e-112">The ClsAgent listens for commands on the following ports: **TCP 50001**, **TCP 50002**, and **TCP 50003**.</span></span>

  - <span data-ttu-id="4159e-113">*一元管理サービスコントローラー*   clscontroller は、Lync Server 管理シェルと clscontroller 用のコマンド実行エンジンです。</span><span class="sxs-lookup"><span data-stu-id="4159e-113">*Centralized Logging Service Controller*   ClsControllerLib.dll is the command execution engine for the Lync Server Management Shell and for ClsController.exe.</span></span> <span data-ttu-id="4159e-114">ClsAgent Lib は、開始、停止、フラッシュ、検索コマンドを ClsAgent に送信します。</span><span class="sxs-lookup"><span data-stu-id="4159e-114">CLSControllerLib.dll sends Start, Stop, Flush, and Search commands to the ClsAgent.</span></span> <span data-ttu-id="4159e-115">検索コマンドが送信されると、結果として得られたログは Clsコントローラーライブラリに戻され、集計されます。</span><span class="sxs-lookup"><span data-stu-id="4159e-115">When search commands are sent, the resulting logs are returned to the ClsControllerLib.dll and aggregated.</span></span> <span data-ttu-id="4159e-116">コントローラーでは、エージェントへのコマンドの送信、それらのコマンドの状態の受信、検索ログファイルデータの管理は、検索範囲内の任意のコンピューター上のすべてのエージェントから返され、ログデータを意味のある順番に集計する役割を担います。出力セット。</span><span class="sxs-lookup"><span data-stu-id="4159e-116">The controller is responsible for sending commands to the agent, receiving the status of those commands and managing the search log file data as it is returned from all agents on any computer in the search scope, and aggregating the log data into a meaningful and ordered output set.</span></span> <span data-ttu-id="4159e-117">次のトピックの情報は、Lync Server 管理シェルの使用に重点を置いています。</span><span class="sxs-lookup"><span data-stu-id="4159e-117">The information in the following topics is focused on using the Lync Server Management Shell.</span></span> <span data-ttu-id="4159e-118">ClsController は、Lync Server 管理シェルで利用できる機能のサブセットに制限されています。</span><span class="sxs-lookup"><span data-stu-id="4159e-118">ClsController.exe is limited to a subset of the features and functions that are available in the Lync Server Management Shell.</span></span> <span data-ttu-id="4159e-119">ClsController のヘルプは、コマンドラインで、既定のディレクトリ C `ClsController` :\\Program Files\\Common Files\\Microsoft Lync Server 2013\\clscontroller に入力すると、コマンドラインから利用できます。</span><span class="sxs-lookup"><span data-stu-id="4159e-119">Help for ClsController.exe is available at the command line by typing `ClsController` in the default directory C:\\Program Files\\Common Files\\Microsoft Lync Server 2013\\ClsAgent.</span></span>

<span data-ttu-id="4159e-120">**ClsController と ClsAgent の通信**</span><span class="sxs-lookup"><span data-stu-id="4159e-120">**ClsController communications to ClsAgent**</span></span>

<span data-ttu-id="4159e-121">![CLSController と Clscontroller の間のリレーションシップ。](images/JJ688145.68c90811-5cf9-4a84-95b7-ea9ffc61eac4(OCS.15).jpg "CLSController と Clscontroller の間のリレーションシップ。")</span><span class="sxs-lookup"><span data-stu-id="4159e-121">![Relationship between CLSController and CLSAgent.](images/JJ688145.68c90811-5cf9-4a84-95b7-ea9ffc61eac4(OCS.15).jpg "Relationship between CLSController and CLSAgent.")</span></span>

<span data-ttu-id="4159e-122">Windows Server のコマンドラインインターフェイスまたは Lync Server 管理シェルを使用して、コマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="4159e-122">You issue commands using the Windows Server command-line interface or using the Lync Server Management Shell.</span></span> <span data-ttu-id="4159e-123">コマンドは、ログインしているコンピューターで実行され、ローカルまたは展開内の他のコンピューターやプールに送信されます。</span><span class="sxs-lookup"><span data-stu-id="4159e-123">The commands are executed on the computer you are logged in to and sent to the ClsAgent locally or to the other computers and pools in your deployment.</span></span>

<span data-ttu-id="4159e-124">ClsAgent は、すべてのインデックスファイルを管理します。ローカルコンピューターにあるファイルをキャッシュします。</span><span class="sxs-lookup"><span data-stu-id="4159e-124">ClsAgent maintains an index file of all .CACHE files that it has on the local machine.</span></span> <span data-ttu-id="4159e-125">ClsAgent は、オプション CacheFileLocalFolders によって定義されたボリューム間で均等に分散されるように、各ボリュームの 80% を消費しないように割り当てます (つまり、ローカルキャッシュの場所と割合は、 **Set-CsClsConfiguration**コマンドレット)。</span><span class="sxs-lookup"><span data-stu-id="4159e-125">ClsAgent allocates them so that they are evenly distributed across volumes defined by the option CacheFileLocalFolders, never consuming more than 80% of each volume (that is, the local cache location and the percentage is configurable using the **Set-CsClsConfiguration** cmdlet).</span></span> <span data-ttu-id="4159e-126">ClsAgent は、ローカルコンピューターから古いキャッシュされたイベントトレースログ (.etl) ファイルを処理する責任も担います。</span><span class="sxs-lookup"><span data-stu-id="4159e-126">ClsAgent is also responsible for aging old cached event trace log (.etl) files off the local machine.</span></span> <span data-ttu-id="4159e-127">2週間後 (つまり、 **Set-CsClsConfiguration**コマンドレットを使用して期間を構成できます)、これらのファイルはファイル共有にコピーされ、ローカルコンピューターから削除されます。</span><span class="sxs-lookup"><span data-stu-id="4159e-127">After two weeks (that is, the timeframe is configurable using the **Set-CsClsConfiguration** cmdlet) these files are copied to a file share and deleted from the local computer.</span></span> <span data-ttu-id="4159e-128">詳細については、「 [Set-CsClsConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsClsConfiguration)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4159e-128">For details, see [Set-CsClsConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsClsConfiguration).</span></span> <span data-ttu-id="4159e-129">検索要求を受信すると、検索条件を使ってキャッシュされた一連の .etl ファイルが選択され、エージェントによって管理されているインデックス内の値に基づいて検索が実行されます。</span><span class="sxs-lookup"><span data-stu-id="4159e-129">When a search request is received, the search criteria is used to select the set of cached .etl files to perform the search based on the values in the index maintained by the agent.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="4159e-p106">ローカル コンピューターからファイル共有に移動されたファイルを ClsAgent で検索できます。ClsAgent がファイルをファイル共有に移動すると、ファイルのエージングと削除は ClsAgent で管理されません。ファイル共有内のファイルのサイズを監視し、ファイルを削除またはアーカイブするための管理タスクを定義する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4159e-p106">Files that are moved to the file share from the local computer can be searched by ClsAgent. Once ClsAgent moves the files to the file share, the aging and removal of files is not maintained by ClsAgent. You should define an administrative task to monitor the size of the files in the file share and delete them or archive them.</span></span>



</div>

<span data-ttu-id="4159e-133">**Snooper.exe** や、テキスト ファイルを読み取ることのできるツール (**Notepad.exe** など) を含むさまざまなツールを使用して、結果のログ ファイルの読み取りと分析を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="4159e-133">The resulting log files can be read and analyzed using a variety of tools, including **Snooper.exe** and any tool that can read a text file, such as **Notepad.exe**.</span></span> <span data-ttu-id="4159e-134">Snooper は Lync Server 2013 デバッグツールの一部であり、Web から[http://go.microsoft.com/fwlink/?LinkId=285257](http://go.microsoft.com/fwlink/?linkid=285257)ダウンロードできます。</span><span class="sxs-lookup"><span data-stu-id="4159e-134">Snooper.exe is part of the Lync Server 2013 Debug Tools and is available as a Web download from [http://go.microsoft.com/fwlink/?LinkId=285257](http://go.microsoft.com/fwlink/?linkid=285257).</span></span>

<span data-ttu-id="4159e-135">OCSLogger と同様に、一元管理サービスには、追跡対象となるいくつかのコンポーネントがあり、TF\_コンポーネントや tf\_DIAG などのフラグを選択するオプションが用意されています。</span><span class="sxs-lookup"><span data-stu-id="4159e-135">Like OCSLogger, the Centralized Logging Service has several components to trace against, and provides options to select flags, such as TF\_COMPONENT and TF\_DIAG.</span></span> <span data-ttu-id="4159e-136">一元管理サービスは、OCSLogger の [ログレベル] オプションも保持します。</span><span class="sxs-lookup"><span data-stu-id="4159e-136">Centralized Logging Service also retains the logging level options of OCSLogger.</span></span>

<span data-ttu-id="4159e-137">コマンドラインの ClsController を介して Lync Server 管理シェルを使用する最も重要な利点は、問題スペース、カスタムフラグ、およびログレベルを対象とする、選択したプロバイダーを使用して新しいシナリオを構成して定義できることです。</span><span class="sxs-lookup"><span data-stu-id="4159e-137">The most important advantage to using the Lync Server Management Shell over the command-line ClsController is that you can configure and define new scenarios using selected providers that target the problem space, custom flags, and logging levels.</span></span> <span data-ttu-id="4159e-138">ClsController で使用可能なシナリオは、実行可能ファイル用に定義されるシナリオに制限されます。</span><span class="sxs-lookup"><span data-stu-id="4159e-138">The scenarios available to ClsController are limited to those that are defined for the executable.</span></span>

<span data-ttu-id="4159e-p110">以前のバージョンでは、管理者とサポート担当者が展開内のコンピューターからトレース ファイルを収集できるようにするために OCSLogger.exe が提供されていました。OCSLogger には、長所と同時に短所も存在しました。ログは一度に 1 台のコンピューター上でしか収集できませんでした。OCSLogger のコピーを使用して複数のコンピューターにログオンすることは可能でしたが、最終的にログが複数作成され、結果を集計するのが容易ではありませんでした。</span><span class="sxs-lookup"><span data-stu-id="4159e-p110">In previous versions, OCSLogger.exe was provided to enable administrators and support personnel to collect trace files from computers in the deployment. OCSLogger, for all of its strengths, had a shortcoming. You could only collect logs on one computer at a given time. You could log on to multiple computers by using separate copies of OCSLogger, but you ended up with multiple logs and no easy way to aggregate the results.</span></span>

<span data-ttu-id="4159e-p111">ユーザーがログの検索を要求すると、ClsController が (選択したシナリオに基づいて) 要求の送信先コンピューターを特定します。また、.etl ファイルが保存されているファイル共有に検索を送信する必要があるかどうかを判断します。検索結果が ClsController に返されると、コントローラーが結果をマージして時系列の 1 つの結果セットを作成し、ユーザーに提供します。ユーザーは、ローカル コンピューターに検索結果を保存して、以降の分析に使用できます。</span><span class="sxs-lookup"><span data-stu-id="4159e-p111">When a user requests a log search, the ClsController determines which machines to send the request to (that is, based on the scenarios selected). It also determines whether the search needs to be sent to the file share where the saved .etl files are located. When the search results are returned to the ClsController, the controller merges the results into a single time-ordered result set that is presented to the user. Users can save the search results to their local machine for further analysis.</span></span>

<span data-ttu-id="4159e-p112">ログ記録セッションを開始したら、解決しようとする問題に関連するシナリオを指定します。常に実行することのできるシナリオは 2 つあります。そのうちの 1 つは AlwaysOn シナリオにする必要があります。名前が示すとおり、このシナリオを展開内で常に実行し、すべてのコンピューター、プール、およびコンポーネントに関する情報を収集する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4159e-p112">When you start a logging session, you specify scenarios that are relative to the problem that you are trying to resolve. You can have two scenarios running at any time. One of these two scenarios should be the AlwaysOn scenario. As the name implies, it should always be running in your deployment, collecting information on all computers, pools, and components.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="4159e-151">既定では、AlwaysOn シナリオは展開内で実行されません。</span><span class="sxs-lookup"><span data-stu-id="4159e-151">By default, the AlwaysOn scenario is not running in your deployment.</span></span> <span data-ttu-id="4159e-152">このシナリオは明示的に開始する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4159e-152">You must explicitly start the scenario.</span></span> <span data-ttu-id="4159e-153">開始したシナリオは明示的に停止されるまで実行され、実行状態はコンピューターを再起動しても保持されます。</span><span class="sxs-lookup"><span data-stu-id="4159e-153">Once started, it will continue to run until explicitly stopped, and the running state will persist through reboots of the computers.</span></span> <span data-ttu-id="4159e-154">シナリオの開始と停止の詳細については、「サーバー <A href="lync-server-2013-using-start-for-the-centralized-logging-service-to-capture-logs.md">2013 でログをキャプチャ</A>して lync server <A href="lync-server-2013-using-stop-for-the-centralized-logging-service.md">2013 の中央集中ログサービスの [停止</A>] を使う」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4159e-154">For details on starting and stopping scenarios, see <A href="lync-server-2013-using-start-for-the-centralized-logging-service-to-capture-logs.md">Using Start for the Centralized Logging Service to capture logs in Lync Server 2013</A> and <A href="lync-server-2013-using-stop-for-the-centralized-logging-service.md">Using Stop for the Centralized Logging Service in Lync Server 2013</A>.</span></span>



</div>

<span data-ttu-id="4159e-p114">問題が発生した場合は、報告された問題に関連する 2 つ目のシナリオを開始します。問題を再現し、2 つ目のシナリオのログ記録を停止します。報告された問題に関連するログの検索を開始します。集計されたログのコレクションによって、展開のサイト スコープまたはグローバル スコープ内のすべてのコンピューターからのトレース メッセージを含むログ ファイルが生成されます。分析可能なデータ以上のデータが検索から返された場合は (通常、信号対ノイズ比とも呼ばれ、この場合はノイズが多すぎる状態です)、パラメーターを絞り込んで別の検索を実行します。この時点で、問題を明確にするために役立つパターンの特定を開始できます。最終的には、いくつかの絞り込み検索を実行した後で問題に関連するデータが見つかり、根本原因を特定できます。</span><span class="sxs-lookup"><span data-stu-id="4159e-p114">When a problem occurs, start a second scenario that relates to the problem reported. Reproduce the problem, and stop the logging for the second scenario. Begin your log searches relative to the problem reported. The aggregated collection of logs produces a log file that contains trace messages from all computers in your site or global scope of your deployment. If the search returns more data than you can feasibly analyze (typically known as a signal-to-noise ratio, where the noise is too high), you run another search with narrower parameters. At this point, you can begin to notice patterns that show up and can help you get a clearer focus on the problem. Ultimately, after you perform a couple of refined searches you can find data that is relevant to the problem and figure out the root cause.</span></span>

<div>


> [!TIP]  
> <span data-ttu-id="4159e-162">Lync Server で問題のシナリオを提示された場合は、まず「問題について何を知っていますか?」というメッセージを表示します。</span><span class="sxs-lookup"><span data-stu-id="4159e-162">When presented with a problem scenario in Lync Server, start by asking yourself “What do I already know about the problem?”</span></span> <span data-ttu-id="4159e-163">問題の境界を定量化すると、Lync Server の運用エンティティの一部を削除することができます。</span><span class="sxs-lookup"><span data-stu-id="4159e-163">If you quantify the problem boundaries, you can eliminate a large part of the operational entities in Lync Server.</span></span><BR><span data-ttu-id="4159e-164">ユーザーが連絡先を検索するときに現在の結果を取得していないことがわかっているシナリオ例を検討します。</span><span class="sxs-lookup"><span data-stu-id="4159e-164">Consider an example scenario where you know that users are not getting current results when looking for a contact.</span></span> <span data-ttu-id="4159e-165">メディアコンポーネント、エンタープライズ Voip、会議、その他のコンポーネントで問題があるかどうかを調べるポイントはありません。</span><span class="sxs-lookup"><span data-stu-id="4159e-165">There is no point in looking for problems in the media components, Enterprise Voice, conferencing, and a number of other components.</span></span> <span data-ttu-id="4159e-166">実際はどこに問題が存在するのか (クライアントなのか、サーバー側の問題なのか) がわからないためです。</span><span class="sxs-lookup"><span data-stu-id="4159e-166">What you may not know is where the problem actually is: on the client, or is this a server-side problem?</span></span> <span data-ttu-id="4159e-167">連絡先は、ユーザーレプリケーターによって Active Directory から収集され、アドレス帳サーバー (ABServer) を介してクライアントに配信されます。</span><span class="sxs-lookup"><span data-stu-id="4159e-167">Contacts are collected from Active Directory by the User Replicator and delivered to the client by way of the Address Book Server (ABServer).</span></span> <span data-ttu-id="4159e-168">ABServer は、既定では午前 1 時 30 分に (ユーザー レプリケーターが更新内容を書き込む) RTC データベースから更新を取得してアドレス帳ファイルにまとめます。</span><span class="sxs-lookup"><span data-stu-id="4159e-168">The ABServer gets its updates from the RTC database (where User Replicator wrote them) and collects them into address book files, by default – 1:30 AM.</span></span> <span data-ttu-id="4159e-169">Lync Server クライアントはランダムなスケジュールで新しいアドレス帳を取得します。</span><span class="sxs-lookup"><span data-stu-id="4159e-169">The Lync Server clients retrieve the new address book on a randomized schedule.</span></span> <span data-ttu-id="4159e-170">プロセスがどのように動作するかがわかっているため、ユーザーレプリケーターによって Active Directory から収集されたデータに関連する問題の可能性を検索したり、ABServer がアドレス帳ファイルを取得して作成したりすることはありません。アドレス帳ファイルをダウンロードしています。</span><span class="sxs-lookup"><span data-stu-id="4159e-170">Because you know how the process works, you can reduce your search for the potential cause to an issue related to data being collected from Active Directory by the User Replicator, the ABServer not retrieving and creating the address book files, or the clients not downloading the address book file.</span></span>



</div>

</div>

<span> </span>

</div>

</div>

</div>

