---
title: 集中ログサービスによって作成されたキャプチャログでの検索の使用
description: 集中ログサービスによって作成されたキャプチャログの検索を使用します。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Using search on capture logs created by the Centralized Logging Service
ms:assetid: 1b75b218-d84f-47a7-8a0a-b7e016b1cc79
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ687982(v=OCS.15)
ms:contentKeyID: 49733571
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2f6517dd3a9df749d2fe65f1b594b9d21204d7fa
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48580253"
---
# <a name="using-search-on-capture-logs-created-by-the-centralized-logging-service-in-lync-server-2013"></a><span data-ttu-id="77b53-103">Lync Server 2013 での集中ログサービスによって作成されたキャプチャログでの検索の使用</span><span class="sxs-lookup"><span data-stu-id="77b53-103">Using search on capture logs created by the Centralized Logging Service in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="77b53-104">_**トピックの最終更新日:** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="77b53-104">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="77b53-105">集中ログサービスの検索機能は、次の理由から便利で強力です。</span><span class="sxs-lookup"><span data-stu-id="77b53-105">The search features in the Centralized Logging Service are useful and powerful for the following reasons:</span></span>

  - <span data-ttu-id="77b53-106">検索と結果が、定義する条件に基づいて、1 台のコンピューター、プール、サイト、またはグローバル サイトで実行されます。</span><span class="sxs-lookup"><span data-stu-id="77b53-106">Your searches and the results are run on a single computer, a pool, a site, or a global scope, based on the criteria you define.</span></span>

  - <span data-ttu-id="77b53-p101">広範囲での検索から始めて、時間、コンポーネント、コンピューターなど、検索の条件を絞り込むことができます。検索は同じログに対して行われるため、検索条件を変更したときにログ セッションを再実行する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="77b53-p101">Your searches can be initially broad and then narrowed down to more targeted criteria such as time, component, or computer. You search against the same logs and don’t need to run a logging session again when the search criteria changes.</span></span>

  - <span data-ttu-id="77b53-p102">検索の結果は、スコープ内のすべてのコンピューターとプールから収集され、検索条件のすべての結果を表す 1 つの出力ファイルに集約されます (実行しているシナリオおよびシナリオによって取得されたデータに限定されます)。使い慣れた **Snooper**、**メモ帳**などのツールを使用して、出力ファイルおよび展開全体からのトレース メッセージを読み取ります。</span><span class="sxs-lookup"><span data-stu-id="77b53-p102">The results of your search are gathered from all computers and pools in the scope, collected and aggregated into a single output file that represents all results of the search criteria (limited to the scenarios that have been running and the data captured by the scenarios). You use familiar tools such as **Snooper** or **Notepad** to read the output file and the trace messages from across your deployment.</span></span>

<span data-ttu-id="77b53-p103">個々の各コンピューター上の CLSAgent によって、1 つまたは複数のシナリオに基づいたログが作成されます (1 台のコンピューター当たり 2 つのシナリオをいつでも実行できます)。ログと関連するインデックス ファイルおよびキャッシュ ファイルは、CLSAgent によって管理されます。検索を定義して実行すると、その検索コマンドが CLSAgent に対して取得する情報を指示します。CLSAgent はログ ファイル、キャッシュ ファイル、およびインデックス ファイルに対してクエリを実行し、検索の結果を CLSContoller に返します。CLSController は、検索の範囲内のすべてのコンピューターおよびプールから、検索結果を受け取ります。次に、CLSController はログを集約 (結合) し、最も古いエントリが先頭で、最新のエントリが末尾になるように、時系列に配置します。</span><span class="sxs-lookup"><span data-stu-id="77b53-p103">The CLSAgent on each individual computer creates the logs based on the scenario or scenarios (two scenarios per computer can be running at any given time). The logs and their associated index and cache files are managed by the CLSAgent. When you define and execute a search, the search command instructs the CLSAgent on what information should be retrieved. The CLSAgent executes the query against the log files, cache files, and index files and returns the results of the search to the CLSContoller. The CLSController receives the search results from all computers and pools in the scope of the search. The CLSController then aggregates (combines) the logs and puts them into time delta order, oldest entry first, and proceeding in time to the most recent entry last.</span></span>

<span data-ttu-id="77b53-117">各検索の後、**Sync-CsClsLogging** コマンドレットが実行されて、検索で使用されるキャッシュ (CLSAgent が管理するキャッシュ ファイルで使用されるものではない) をフラッシュします。</span><span class="sxs-lookup"><span data-stu-id="77b53-117">After each search, the **Sync-CsClsLogging** cmdlet is run and it flushes the cache used by searches (not to be confused with the cache files maintained by the CLSAgent).</span></span> <span data-ttu-id="77b53-118">キャッシュをフラッシュすることで、次の検索操作で CLSController はクリーンなログおよびトレース ファイルのキャプチャ バッファーを使用できます。</span><span class="sxs-lookup"><span data-stu-id="77b53-118">Flushing the cache helps to ensure that there is a clean log and trace file capture buffer at the CLSController for the next search operation.</span></span>

<span data-ttu-id="77b53-119">集中ログサービスから最大のメリットを得るには、検索を構成して、コンピューターからのトレースメッセージのみを返し、調査している問題に関連するプールログのみを取得する方法について十分に理解しておく必要があります。</span><span class="sxs-lookup"><span data-stu-id="77b53-119">To get the most benefit from the Centralized Logging Service, you need a good understanding of how to configure search to return only trace messages from the computer and pool logs that are relevant to the issue that you are researching.</span></span> <span data-ttu-id="77b53-120">問題</span><span class="sxs-lookup"><span data-stu-id="77b53-120">issues</span></span>

<span data-ttu-id="77b53-121">Lync Server 管理シェルを使用して集中ログサービスの検索機能を実行するには、CsAdministrator または CsServerAdministrator の役割ベースのアクセス制御 (RBAC) セキュリティグループのメンバーであるか、またはこれら2つのグループのどちらかを含むカスタムの RBAC の役割を持っている必要があります。</span><span class="sxs-lookup"><span data-stu-id="77b53-121">To run the Centralized Logging Service search functions by using the Lync Server Management Shell, you must be a member of either the CsAdministrator or the CsServerAdministrator role-based access control (RBAC) security groups, or a custom RBAC role that contains either of these two groups.</span></span> <span data-ttu-id="77b53-122">このコマンドレットが割り当てられているすべての RBAC の役割 (自分で作成したカスタムの RBAC の役割を含む) の一覧を返すには、Lync Server 管理シェルまたは Windows PowerShell プロンプトから次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="77b53-122">To return a list of all the RBAC roles that this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Lync Server Management Shell or the Windows PowerShell prompt:</span></span>

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Lync Server 2013 cmdlet"}

<span data-ttu-id="77b53-123">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="77b53-123">For example:</span></span>

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Set-CsClsConfiguration"}

<span data-ttu-id="77b53-124">このトピックの以降の部分では、トラブルシューティングを最適化するための検索の定義方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="77b53-124">The remainder of this topic focuses on how to define a search to optimize your troubleshooting.</span></span>

<div>

## <a name="to-run-a-basic-search-by-using-the-centralized-logging-service"></a><span data-ttu-id="77b53-125">集中ログサービスを使用して基本的な検索を実行するには</span><span class="sxs-lookup"><span data-stu-id="77b53-125">To run a basic search by using the Centralized Logging Service</span></span>

1.  <span data-ttu-id="77b53-126">Lync Server 管理シェルを以下の手順で起動します。[**スタート**]、[**すべてのプログラム**]、[**Microsoft Lync Server 2013**]、[**Lync Server 管理シェル**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="77b53-126">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="77b53-127">AlwaysOn シナリオが展開内でグローバル スコープで実行していることを確認し、コマンド プロンプトで次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="77b53-127">Make sure that you have the AlwaysOn scenario running in your deployment at the global scope and then type the following at a command prompt:</span></span>
    
        Search-CsClsLogging -OutputFilePath <string value of path and file to write the output file>
    
    <div>
    

    > [!NOTE]
    > <span data-ttu-id="77b53-128">既定では、Search-CsClsLogging は検索の結果をコンソールに送ります。</span><span class="sxs-lookup"><span data-stu-id="77b53-128">By default, Search-CsClsLogging sends the results of the search to the console.</span></span> <span data-ttu-id="77b53-129">検索結果をファイルに保存する場合は、– OutputFilePath &lt; 文字列の完全修飾ファイルパスを使用し &gt; ます。</span><span class="sxs-lookup"><span data-stu-id="77b53-129">If you want to save the search results to a file, use –OutputFilePath &lt;string fully qualified file path&gt;.</span></span> <span data-ttu-id="77b53-130">–OutputFilePath パラメーターを定義するには、パラメーターにパスとファイル名を文字列形式で指定し、引用符で囲みます (たとえば、C:\LogFiles\SearchOutput.txt)。</span><span class="sxs-lookup"><span data-stu-id="77b53-130">To define the –OutputFilePath parameter, supply a path and a filename as part of the parameter in a string format enclosed in quotation marks (for example; C:\LogFiles\SearchOutput.txt).</span></span> <span data-ttu-id="77b53-131">この例では、ディレクトリ C:\LogFiles が存在し、フォルダー内のファイルに対して読み取りと書き込みのアクセス許可 (NTFS の場合は変更のアクセス許可) を持っている必要があります。</span><span class="sxs-lookup"><span data-stu-id="77b53-131">In this example, you must ensure that the directory C:\LogFiles exists and that you have permissions to Read and Write (NTFS permission Modify) files in the folder.</span></span> <span data-ttu-id="77b53-132">出力は追加され、上書きはされません。</span><span class="sxs-lookup"><span data-stu-id="77b53-132">The output is appended to and is not overwritten.</span></span> <span data-ttu-id="77b53-133">個別のファイルが必要な場合は、検索ごとに個々のファイル名を定義します。</span><span class="sxs-lookup"><span data-stu-id="77b53-133">If you need separate files, define a distinct file name for each search.</span></span>

    
    </div>
    
    <span data-ttu-id="77b53-134">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="77b53-134">For example:</span></span>
    
        Search-CsClsLogging -OutputFilePath "C:\LogFiles\logfile.txt"

</div>

<div>

## <a name="to-run-a-basic-search-on-a-pool-or-computer-by-using-the-centralized-logging-service"></a><span data-ttu-id="77b53-135">集中ログサービスを使用してプールまたはコンピューターで基本的な検索を実行するには</span><span class="sxs-lookup"><span data-stu-id="77b53-135">To run a basic search on a pool or computer by using the Centralized Logging Service</span></span>

1.  <span data-ttu-id="77b53-136">検索を特定のプールまたはコンピューターに限定するには、–Computers パラメーターを使用し、コンピューターの完全修飾名で定義されるコンピューターを引用符で囲み、コンマで区切って指定します。</span><span class="sxs-lookup"><span data-stu-id="77b53-136">To limit the search to a specific pool or computer, use the –Computers parameter with the computer defined by a computer fully qualified name, enclosed in quotation marks and separated by a comma as follows:</span></span>
    
        Search-CsClsLogging -Computers <string value of computer names> -OutputFilePath <string value of path and file to write the output file>
    
    <span data-ttu-id="77b53-137">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="77b53-137">For example:</span></span>
    
        Search-CsClsLogging -Computers "fe01.contoso.net" -OutputFilePath "C:\LogFiles\logfile.txt"

2.  <span data-ttu-id="77b53-138">複数のコンピューターを検索するには、次に示すように、複数のコンピューター名をそれぞれ引用符で囲み、コンマで区切って入力します。</span><span class="sxs-lookup"><span data-stu-id="77b53-138">To search more than one computer, type multiple computer names enclosed in quotation marks and separated by commas, such as the following:</span></span>
    
        Search-CsClsLogging -Computers "fe01.contoso.net", "fe02.contoso.net", "fe03.contoso.net" -OutputFilePath "C:\LogFiles\logfile.txt"

3.  <span data-ttu-id="77b53-139">1 台のコンピューターではなくプール全体を検索する必要がある場合は、–Computers パラメーターを –Pools に変更し、コンピューター名を削除して、1 つまたは複数のプールに置き換えます。各プールは引用符で囲み、コンマで区切ります。</span><span class="sxs-lookup"><span data-stu-id="77b53-139">If you need to search an entire pool instead of a single computer, change the –Computers parameter to –Pools, remove the computer name, and replace it with the pool or pools in quotation marks separated by commas.</span></span>
    
    <span data-ttu-id="77b53-140">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="77b53-140">For example:</span></span>
    
        Search-CsClsLogging -Pools "pool01.contoso.net" -OutputFilePath "C:\Logfiles\logfile.txt"

4.  <span data-ttu-id="77b53-141">検索コマンドを使用する場合、プールには、フロントエンドプール、エッジプール、常設チャットサーバープール、または展開でプールとして定義されている他の任意のプールを指定できます。</span><span class="sxs-lookup"><span data-stu-id="77b53-141">When using the search commands, pools can be any pool in your deployment, such as Front End pools, Edge pools, Persistent Chat Server pools, or others that are defined as a pool in your deployment.</span></span>
    
    <span data-ttu-id="77b53-142">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="77b53-142">For example:</span></span>
    
        Search-CsClsLogging -Pools "pool01.contoso.net", "pchatpool01.contoso.net", "intedgepool01.contoso.net" -OutputFilePath "C:\Logfiles\logfile.txt"

</div>

<div>

## <a name="to-run-a-search-by-using-time-parameters"></a><span data-ttu-id="77b53-143">時間のパラメーターを使用して検索を実行するには</span><span class="sxs-lookup"><span data-stu-id="77b53-143">To run a search by using time parameters</span></span>

1.  <span data-ttu-id="77b53-144">Lync Server 管理シェルを以下の手順で起動します。[**スタート**]、[**すべてのプログラム**]、[**Microsoft Lync Server 2013**]、[**Lync Server 管理シェル**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="77b53-144">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="77b53-p108">既定では、検索の時間固有のパラメーターの開始時間は、検索を開始する時間の 30 分前です。つまり、検索を 4:00:00 PM に開始する場合、定義するコンピューターおよびプールのログは 3:30:00 PM から 4:00:00 PM まで検索されます。現在の時刻より 60 分または 3 時間前を検索する必要がある場合は、–StartTime パラメーターを使用して、検索を開始する時間を表す日時文字列を設定します。</span><span class="sxs-lookup"><span data-stu-id="77b53-p108">By default, the beginning time for a search's time-specific parameters is 30 minutes prior to the time you initiate the search. In other words, if you initiate your search at 4:00:00 PM, the search will search the logs for the computers and pools that you define from 3:30:00 PM until 4:00:00 PM. If you need to search 60 minutes or 3 hours prior to the current time, use the –StartTime parameter and set the date and time string to indicate the time you want the search to start.</span></span>
    
    <span data-ttu-id="77b53-148">たとえば、–StartTime および –EndTime を使用して日時の範囲を定義することにより、11/20/2012 8 AM ～ 9 AM の間のプールでの検索を定義できます。</span><span class="sxs-lookup"><span data-stu-id="77b53-148">For example, by using –StartTime and –EndTime to define a time and date range, you can define a search between 8 AM and 9 AM on 11/20/2012 on your pool.</span></span> <span data-ttu-id="77b53-149">出力パスを設定して、次のように c:logfile.txt という名前のファイルに結果を書き込むことができ \\ ます。</span><span class="sxs-lookup"><span data-stu-id="77b53-149">You can set the output path to write the results to a file named c:\\logfile.txt as follows:</span></span>
    
        Search-CsClsLogging -Pools "pool01.contoso.net" -StartTime "11/20/2012 08:00:00 AM" -EndTime "11/20/2012 09:00:00 AM" -OutputFilePath "C:\Logfiles\logfile.txt"
    
    <div>
    

    > [!NOTE]
    > <span data-ttu-id="77b53-150">指定した時刻と日付の文字列は、"日付時間" または "時間日付" にすることができます。</span><span class="sxs-lookup"><span data-stu-id="77b53-150">The time and date string that you specify can be "date time" or "time date.</span></span> <span data-ttu-id="77b53-151">"コマンドは文字列を解析し、日付と時刻に適切な値を使用します。</span><span class="sxs-lookup"><span data-stu-id="77b53-151">" The command will parse the string and use the appropriate values for date and time.</span></span>

    
    </div>

3.  <span data-ttu-id="77b53-p111">11/20/2012 11:00:00 AM から始まるログを取得するには、–StartTime を定義します。既定の検索時間は、特定の –EndTime を定義しない限り、30 分です。検索の結果、定義したコンピューターまたはプールから、11:00:00 AM ～ 11:30:00 AM の範囲のログが返されます。</span><span class="sxs-lookup"><span data-stu-id="77b53-p111">If you want to retrieve logs beginning at 11:00:00 AM on 11/20/2012, you define the –StartTime. The default time range for the search is 30 minutes unless you define a specific –EndTime. The resulting search will return logs from the defined computer or pools from 11:00:00 AM to 11:30:00 AM.</span></span>
    
    <span data-ttu-id="77b53-155">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="77b53-155">For example:</span></span>
    
        Search-CsClsLogging -Pools "pool01.contoso.net" -StartTime "11/20/2012 11:00:00 AM" -OutputFilePath "C:\Logfiles\logfile.txt"

4.  <span data-ttu-id="77b53-p112">特定の時間内でログの検索を行うには、–StartTime および –EndTime を定義します。コンピューター edge01.contoso.net における 1 PM から 2:45 PM までのログが必要です。</span><span class="sxs-lookup"><span data-stu-id="77b53-p112">To conduct a search of logs within a specific period of time, define a –StartTime and an –EndTime. You need logs from 1 PM to 2:45 PM on the computer edge01.contoso.net.</span></span>
    
    <span data-ttu-id="77b53-158">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="77b53-158">For example:</span></span>
    
        Search-CsClsLogging -Computers "edge01.contoso.net" -StartTime "11/20/2012 1:00:00 PM" -EndTime "11/20/2012 2:45:00 PM" -OutputFilePath "C:\Logfiles\logfile.txt"

</div>

<div>

## <a name="to-run-an-advanced-search-by-using-other-criteria-and-matching-options"></a><span data-ttu-id="77b53-159">他の条件および一致オプションを使用して高度な検索を行うには</span><span class="sxs-lookup"><span data-stu-id="77b53-159">To run an advanced search by using other criteria and matching options</span></span>

1.  <span data-ttu-id="77b53-160">Lync Server 管理シェルを以下の手順で起動します。[**スタート**]、[**すべてのプログラム**]、[**Microsoft Lync Server 2013**]、[**Lync Server 管理シェル**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="77b53-160">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="77b53-161">特定のコンポーネントのトレースを収集するコマンドを実行するには、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="77b53-161">To run a command to collect traces for specific components, type the following:</span></span>
    
        Search-CsClsLogging -Components <components to search on> -OutputFilePath <fully qualified path to output logs>
    
    <span data-ttu-id="77b53-162">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="77b53-162">For example:</span></span>
    
        Search-CsClsLogging -Components "SIPStack","S4","UserServices" -OutputFilePath "C:\Logfiles\logfile.txt"
    
    <span data-ttu-id="77b53-163">検索の結果、過去 30 分の間に展開内のすべてのコンピューターおよびプールで、SIPStack、S4、および UserServices のトレース コンポーネントを持つすべてのログ エントリが返されます。</span><span class="sxs-lookup"><span data-stu-id="77b53-163">The resulting search returns all log entries that have trace components for SIPStack, S4, and UserServices on all computers and pools in your deployment for the past 30 minutes.</span></span>

3.  <span data-ttu-id="77b53-164">同じコンポーネントの検索を pool01.contoso.net という名前のフロントエンドプールだけに限定するには、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="77b53-164">To limit the search with the same components to just your Front End pool named pool01.contoso.net, type:</span></span>
    
        Search-CsClsLogging -Components "SIPStack","S4","UserServices" -OutputFilePath "C:\Logfiles\logfile.txt"

4.  <span data-ttu-id="77b53-p113">複数のパラメーターを使用するコマンドの既定の検索ロジックでは、定義された各パラメーターに対して論理 OR を使用します。この動作は、**–MatchAll** パラメーターを指定することで変更できます。これを行うには、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="77b53-p113">The default search logic for commands with multiple parameters is to use the logical OR with each of the defined parameters. You can change this behavior by specifying the **–MatchAll** parameter. To do this, type the following:</span></span>
    
        Search-CsClsLogging -CallId "d0af828e49fa4dcb99f5f80223a634bc" -Components "SIPStack","S4","UserServices" -MatchAll -OutputFilePath "C:\Logfiles\logfile.txt"

5.  <span data-ttu-id="77b53-p114">AlwaysOn のように、シナリオが定期的に実行するように設定されている場合、または、長期にわたって実行するシナリオが定義されている場合、ログはローカル コンピューターではなくファイル共有に置かれることがあります。ファイル共有は、New-CsClsConfiguration で新しい構成を作成するとき、または Set-CsClsConfiguration で既存の構成を変更するときに、CacheFileNetworkFolder パラメーターを使用して定義します。検索のログ コレクションにファイル共有を含めない場合は、次に示すように、SkipNetworkLogs パラメーターを使用します。</span><span class="sxs-lookup"><span data-stu-id="77b53-p114">If your scenarios are set to run constantly, such as AlwaysOn, or you have defined a long-running scenario logs may roll off of the local machine onto the file share. You define the file share by using the CacheFileNetworkFolder parameter by using New-CsClsConfiguration to create a new configuration or modifying an existing configuration with Set-CsClsConfiguration. If you do not want the search to include the file share in the collection of logs to search, use the SkipNetworkLogs parameter as follows:</span></span>
    
        Search-CsClsLogging -Components "SIPStack","S4","UserServices" -StartTime "11/1/2012 00:00:01 AM" -EndTime "11/20/2012 2:45:00 PM" -SkipNetworkLogs -OutputFilePath "C:\Logfiles\logfile.txt"

</div>

</div>

<span> </span>

</div>

</div>

</div>

