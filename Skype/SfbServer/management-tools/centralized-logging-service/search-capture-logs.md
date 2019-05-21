---
title: Skype for Business Server 2015 で集中ログ サービスが作成したキャプチャ ログを検索する
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 12/20/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 1b75b218-d84f-47a7-8a0a-b7e016b1cc79
description: '概要: Skype for Business Server 2015 で一元管理されたログサービスキャプチャログの検索と読み取りを行う方法について説明します。'
ms.openlocfilehash: 81bf539c6a06c52354db23bbeea97fb9525cbbd5
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2019
ms.locfileid: "34274374"
---
# <a name="search-capture-logs-created-by-the-centralized-logging-service-in-skype-for-business-server-2015"></a><span data-ttu-id="c5ae2-103">Skype for Business Server 2015 で集中ログ サービスが作成したキャプチャ ログを検索する</span><span class="sxs-lookup"><span data-stu-id="c5ae2-103">Search capture logs created by the Centralized Logging Service in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="c5ae2-104">**概要:** Skype for Business Server 2015 で一元管理されたログサービスのキャプチャログの検索と読み取りを行う方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="c5ae2-104">**Summary:** Learn how to search and read Centralized Logging Service capture logs in Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="c5ae2-105">中央のログサービスの検索機能は、次のような理由で便利で強力です。</span><span class="sxs-lookup"><span data-stu-id="c5ae2-105">The search features in the Centralized Logging Service are useful and powerful for the following reasons:</span></span> 
  
- <span data-ttu-id="c5ae2-106">検索と結果が、定義する条件に基づいて、1 台のコンピューター、プール、サイト、またはグローバル サイトで実行されます。</span><span class="sxs-lookup"><span data-stu-id="c5ae2-106">Your searches and the results are run on a single computer, a pool, a site, or a global scope, based on the criteria you define.</span></span>
    
- <span data-ttu-id="c5ae2-107">広範囲での検索から始めて、時間、コンポーネント、コンピューターなど、検索の条件を絞り込むことができます。</span><span class="sxs-lookup"><span data-stu-id="c5ae2-107">Your searches can be initially broad and then narrowed down to more targeted criteria such as time, component, or computer.</span></span> <span data-ttu-id="c5ae2-108">検索条件が変更されたときに、ログセッションをもう一度実行する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="c5ae2-108">You search against the same logs and don't need to run a logging session again when the search criteria changes.</span></span>
    
- <span data-ttu-id="c5ae2-p102">検索の結果は、スコープ内のすべてのコンピューターとプールから収集され、検索条件のすべての結果を表す 1 つの出力ファイルに集約されます (実行しているシナリオおよびシナリオによって取得されたデータに限定されます)。使い慣れた **Snooper**、**メモ帳**などのツールを使用して、出力ファイルおよび展開全体からのトレース メッセージを読み取ります。</span><span class="sxs-lookup"><span data-stu-id="c5ae2-p102">The results of your search are gathered from all computers and pools in the scope, collected and aggregated into a single output file that represents all results of the search criteria (limited to the scenarios that have been running and the data captured by the scenarios). You use familiar tools such as **Snooper** or **Notepad** to read the output file and the trace messages from across your deployment.</span></span>
    
<span data-ttu-id="c5ae2-p103">個々の各コンピューター上の CLSAgent によって、1 つまたは複数のシナリオに基づいたログが作成されます (1 台のコンピューターあたり 2 つのシナリオをいつでも実行できます)。ログと関連するインデックス ファイルおよびキャッシュ ファイルは、CLSAgent によって管理されます。検索を定義して実行すると、その検索コマンドが CLSAgent に対して取得する情報を指示します。CLSAgent はログ ファイル、キャッシュ ファイル、およびインデックス ファイルに対してクエリを実行し、検索の結果を CLSContoller に返します。CLSController は、検索の範囲内のすべてのコンピューターおよびプールから、検索結果を受け取ります。次に、CLSController はログを集約 (結合) し、最も古いエントリが先頭で、最新のエントリが末尾になるように、時系列に配置します。</span><span class="sxs-lookup"><span data-stu-id="c5ae2-p103">The CLSAgent on each individual computer creates the logs based on the scenario or scenarios (two scenarios per computer can be running at any given time). The logs and their associated index and cache files are managed by the CLSAgent. When you define and execute a search, the search command instructs the CLSAgent on what information should be retrieved. The CLSAgent executes the query against the log files, cache files, and index files and returns the results of the search to the CLSContoller. The CLSController receives the search results from all computers and pools in the scope of the search. The CLSController then aggregates (combines) the logs and puts them into time delta order, oldest entry first, and proceeding in time to the most recent entry last.</span></span>
  
<span data-ttu-id="c5ae2-117">各検索の後、**Sync-CsClsLogging** コマンドレットが実行されて、検索で使用されるキャッシュ (CLSAgent が管理するキャッシュ ファイルで使用されるものではない) をフラッシュします。</span><span class="sxs-lookup"><span data-stu-id="c5ae2-117">After each search, the **Sync-CsClsLogging** cmdlet is run and it flushes the cache used by searches (not to be confused with the cache files maintained by the CLSAgent).</span></span> <span data-ttu-id="c5ae2-118">キャッシュをフラッシュすることで、次の検索操作で CLSController はクリーンなログおよびトレース ファイルのキャプチャ バッファーを使用できます。</span><span class="sxs-lookup"><span data-stu-id="c5ae2-118">Flushing the cache helps to ensure that there is a clean log and trace file capture buffer at the CLSController for the next search operation.</span></span>
  
<span data-ttu-id="c5ae2-119">一元管理サービスを最大限に活用するには、検索の構成方法についてよく理解しておく必要があります。これは、コンピューターからのトレースメッセージだけを返し、調査中の問題に関連するプールログのみを返すようにするためです。</span><span class="sxs-lookup"><span data-stu-id="c5ae2-119">To get the most benefit from the Centralized Logging Service, you need a good understanding of how to configure search to return only trace messages from the computer and pool logs that are relevant to the issue that you are researching.</span></span> <span data-ttu-id="c5ae2-120">問題</span><span class="sxs-lookup"><span data-stu-id="c5ae2-120">issues</span></span>
  
<span data-ttu-id="c5ae2-121">Skype for Business Server 管理シェルを使用して集中ログサービスの検索機能を実行するには、CsAdministrator または CsServerAdministrator の役割ベースのアクセス制御 (RBAC) セキュリティグループ、またはカスタム RBAC ロールのいずれかのメンバーである必要があります。この2つのグループのいずれかが含まれます。</span><span class="sxs-lookup"><span data-stu-id="c5ae2-121">To run the Centralized Logging Service search functions by using the Skype for Business Server Management Shell, you must be a member of either the CsAdministrator or the CsServerAdministrator role-based access control (RBAC) security groups, or a custom RBAC role that contains either of these two groups.</span></span> <span data-ttu-id="c5ae2-122">このコマンドレットが割り当てられているすべての RBAC ロールの一覧 (自分自身で作成したカスタム RBAC ロールを含む) を返すには、Skype for Business Server 管理シェルまたは Windows PowerShell プロンプトから次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="c5ae2-122">To return a list of all the RBAC roles that this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Skype for Business Server Management Shell or the Windows PowerShell prompt:</span></span>
  
```
Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Skype for Business Server 2015 cmdlet"}
```

<span data-ttu-id="c5ae2-123">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="c5ae2-123">For example:</span></span>
  
```
Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Set-CsClsConfiguration"}
```

<span data-ttu-id="c5ae2-124">このトピックの以降の部分では、トラブルシューティングを最適化するための検索の定義方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="c5ae2-124">The remainder of this topic focuses on how to define a search to optimize your troubleshooting.</span></span>
  
### <a name="to-run-a-basic-search-by-using-the-centralized-logging-service"></a><span data-ttu-id="c5ae2-125">中央集中ログサービスを使用して基本的な検索を実行するには</span><span class="sxs-lookup"><span data-stu-id="c5ae2-125">To run a basic search by using the Centralized Logging Service</span></span>

1. <span data-ttu-id="c5ae2-126">Skype for Business Server 管理シェルを以下の手順で起動します。[**スタート**]、[**すべてのプログラム**]、[**Skype for Business 2015**]、[**Skype for Business Server 管理シェル**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="c5ae2-126">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
2. <span data-ttu-id="c5ae2-127">AlwaysOn シナリオが展開内でグローバル スコープで実行していることを確認し、コマンド プロンプトで次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="c5ae2-127">Make sure that you have the AlwaysOn scenario running in your deployment at the global scope and then type the following at a command prompt:</span></span>
    
   ```
   Search-CsClsLogging -OutputFilePath <string value of path and file to write the output file>
   ```

> [!NOTE]
> <span data-ttu-id="c5ae2-128">既定では、Search-CsClsLogging は検索の結果をコンソールに送ります。</span><span class="sxs-lookup"><span data-stu-id="c5ae2-128">By default, Search-CsClsLogging sends the results of the search to the console.</span></span> <span data-ttu-id="c5ae2-129">検索結果をファイルに保存する場合は、-outputfilepath _ \<文字列の完全修飾ファイルパス\>_ を使用します。</span><span class="sxs-lookup"><span data-stu-id="c5ae2-129">If you want to save the search results to a file, use -OutputFilePath  _\<string fully qualified file path\>_.</span></span> <span data-ttu-id="c5ae2-130">-OutputFilePath パラメーターを定義するには、パスとファイル名を引用符で囲まれた文字列形式でパラメーターの一部として指定します (例:C:\LogFiles\SearchOutput.txt).</span><span class="sxs-lookup"><span data-stu-id="c5ae2-130">To define the -OutputFilePath parameter, supply a path and a filename as part of the parameter in a string format enclosed in quotation marks (for example; C:\LogFiles\SearchOutput.txt).</span></span> <span data-ttu-id="c5ae2-131">この例では、ディレクトリ C:\LogFiles が存在し、フォルダー内のファイルに対して読み取りと書き込みのアクセス許可 (NTFS の場合は変更のアクセス許可) を持っている必要があります。</span><span class="sxs-lookup"><span data-stu-id="c5ae2-131">In this example, you must ensure that the directory C:\LogFiles exists and that you have permissions to Read and Write (NTFS permission Modify) files in the folder.</span></span> <span data-ttu-id="c5ae2-132">出力は追加され、上書きはされません。</span><span class="sxs-lookup"><span data-stu-id="c5ae2-132">The output is appended to and is not overwritten.</span></span> <span data-ttu-id="c5ae2-133">個別のファイルが必要な場合は、検索ごとに個々のファイル名を定義します。</span><span class="sxs-lookup"><span data-stu-id="c5ae2-133">If you need separate files, define a distinct file name for each search.</span></span> 
  
<span data-ttu-id="c5ae2-134">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="c5ae2-134">For example:</span></span>
    
  ```
  Search-CsClsLogging -OutputFilePath "C:\LogFiles\logfile.txt"
  ```

### <a name="to-run-a-basic-search-on-a-pool-or-computer-by-using-the-centralized-logging-service"></a><span data-ttu-id="c5ae2-135">集中ログサービスを使用してプールまたはコンピューターで基本的な検索を実行するには</span><span class="sxs-lookup"><span data-stu-id="c5ae2-135">To run a basic search on a pool or computer by using the Centralized Logging Service</span></span>

1. <span data-ttu-id="c5ae2-136">検索を特定のプールまたはコンピューターに限定するには、コンピューターのパラメーターを、引用符で囲まれ、次のようにコンマで区切って、コンピューターの完全修飾名で指定します。</span><span class="sxs-lookup"><span data-stu-id="c5ae2-136">To limit the search to a specific pool or computer, use the -Computers parameter with the computer defined by a computer fully qualified name, enclosed in quotation marks and separated by a comma as follows:</span></span>
    
   ```
   Search-CsClsLogging -Computers <string value of computer names> -OutputFilePath <string value of path and file to write the output file>
   ```

<span data-ttu-id="c5ae2-137">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="c5ae2-137">For example:</span></span>
    
  ```
  Search-CsClsLogging -Computers "fe01.contoso.net" -OutputFilePath "C:\LogFiles\logfile.txt"
  ```

2. <span data-ttu-id="c5ae2-138">複数のコンピューターを検索するには、次に示すように、複数のコンピューター名をそれぞれ引用符で囲み、コンマで区切って入力します。</span><span class="sxs-lookup"><span data-stu-id="c5ae2-138">To search more than one computer, type multiple computer names enclosed in quotation marks and separated by commas, such as the following:</span></span>
    
   ```
   Search-CsClsLogging -Computers "fe01.contoso.net", "fe02.contoso.net", "fe03.contoso.net" -OutputFilePath "C:\LogFiles\logfile.txt"
   ```

3. <span data-ttu-id="c5ae2-139">1台のコンピューターではなくプール全体を検索する必要がある場合は、-Computers のパラメーターを [プール] に変更し、コンピューター名を削除して、そのプールまたはプールをコンマで区切って引用符で囲みます。</span><span class="sxs-lookup"><span data-stu-id="c5ae2-139">If you need to search an entire pool instead of a single computer, change the -Computers parameter to -Pools, remove the computer name, and replace it with the pool or pools in quotation marks separated by commas.</span></span>
    
    <span data-ttu-id="c5ae2-140">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="c5ae2-140">For example:</span></span>
    
   ```
   Search-CsClsLogging -Pools "pool01.contoso.net" -OutputFilePath "C:\Logfiles\logfile.txt"
   ```

4. <span data-ttu-id="c5ae2-141">検索コマンドを使用する場合、プールには、フロントエンドプール、エッジプール、常設チャットサーバープールなどの展開内の任意のプールを使うことができます。また、展開のプールとして定義されている他のプールにすることもできます。</span><span class="sxs-lookup"><span data-stu-id="c5ae2-141">When using the search commands, pools can be any pool in your deployment, such as Front End pools, Edge pools, Persistent Chat Server pools, or others that are defined as a pool in your deployment.</span></span>
    
    <span data-ttu-id="c5ae2-142">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="c5ae2-142">For example:</span></span>
    
   ```
   Search-CsClsLogging -Pools "pool01.contoso.net", "pchatpool01.contoso.net", "intedgepool01.contoso.net" -OutputFilePath "C:\Logfiles\logfile.txt"
   ```

### <a name="to-run-a-search-by-using-time-parameters"></a><span data-ttu-id="c5ae2-143">時間のパラメーターを使用して検索を実行するには</span><span class="sxs-lookup"><span data-stu-id="c5ae2-143">To run a search by using time parameters</span></span>

1. <span data-ttu-id="c5ae2-144">Skype for Business Server 管理シェルを以下の手順で起動します。[**スタート**]、[**すべてのプログラム**]、[**Skype for Business 2015**]、[**Skype for Business Server 管理シェル**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="c5ae2-144">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
2. <span data-ttu-id="c5ae2-145">既定では、検索の時間固有のパラメーターの開始時間は、検索を開始する時間の 25 分前です。</span><span class="sxs-lookup"><span data-stu-id="c5ae2-145">By default, the beginning time for a search's time-specific parameters is 25 minutes prior to five minutes after the time you initiate the search.</span></span> <span data-ttu-id="c5ae2-146">つまり、検索を 4:00:00 PM に開始する場合、検索の開始時間には 3:35:00 から 4:05:00 PM までと表示されます。</span><span class="sxs-lookup"><span data-stu-id="c5ae2-146">In other words, if we search at 4:00:00 PM, then the search start time will show as 3:35:00 PM to 4:05:00 PM.</span></span> <span data-ttu-id="c5ae2-147">現在の時刻の前に60分または3時間を検索する必要がある場合は、-StartTime パラメーターを使用し、日付と時刻の文字列を設定して、検索を開始する時刻を指定します。</span><span class="sxs-lookup"><span data-stu-id="c5ae2-147">If you need to search 60 minutes or 3 hours prior to the current time, use the -StartTime parameter and set the date and time string to indicate the time you want the search to start.</span></span> 
    
    <span data-ttu-id="c5ae2-148">たとえば、-StartTime と-EndTime を使用して時刻と日付の範囲を定義することによって、プールの11/20/2012 で、午前8時から9時までの間に検索を定義できます。</span><span class="sxs-lookup"><span data-stu-id="c5ae2-148">For example, by using -StartTime and -EndTime to define a time and date range, you can define a search between 8 AM and 9 AM on 11/20/2012 on your pool.</span></span> <span data-ttu-id="c5ae2-149">次に示すように、出力パスを設定して、c:\logfile.txt という名前のファイルに結果を書き込むことができます。</span><span class="sxs-lookup"><span data-stu-id="c5ae2-149">You can set the output path to write the results to a file named c:\logfile.txt as follows:</span></span>
    
   ```
   Search-CsClsLogging -Pools "pool01.contoso.net" -StartTime "11/20/2012 08:00:00 AM" -EndTime "11/20/2012 09:00:00 AM" -OutputFilePath "C:\Logfiles\logfile.txt"
   ```

> [!NOTE]
> <span data-ttu-id="c5ae2-150">日時の文字列は、"日付 時間" と"時間 日付" のどちらででも指定できます。</span><span class="sxs-lookup"><span data-stu-id="c5ae2-150">The time and date string that you specify can be "date time" or "time date.</span></span> <span data-ttu-id="c5ae2-151">"コマンドは文字列を解析し、コマンドレットを実行しているコンピューター上の、日付と時刻の適切な値、およびロケールとカルチャの設定を使います。</span><span class="sxs-lookup"><span data-stu-id="c5ae2-151">" The command will parse the string and use the appropriate values for date and time and your locale and culture settings on the machine you are running cmdlet from.</span></span> 
  
3. <span data-ttu-id="c5ae2-152">11/20/2012 の 11:00:00 AM から始まるログを取得する場合は、-StartTime を定義します。</span><span class="sxs-lookup"><span data-stu-id="c5ae2-152">If you want to retrieve logs beginning at 11:00:00 AM on 11/20/2012, you define the -StartTime.</span></span> <span data-ttu-id="c5ae2-153">特定の終了日を定義しない限り、検索の既定の時間範囲は30分です。</span><span class="sxs-lookup"><span data-stu-id="c5ae2-153">The default time range for the search is 30 minutes unless you define a specific -EndTime.</span></span> <span data-ttu-id="c5ae2-154">検索の結果、定義したコンピューターまたはプールから、11:00:00 AM ～ 11:30:00 AM の範囲のログが返されます。</span><span class="sxs-lookup"><span data-stu-id="c5ae2-154">The resulting search will return logs from the defined computer or pools from 11:00:00 AM to 11:30:00 AM.</span></span>
    
<span data-ttu-id="c5ae2-155">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="c5ae2-155">For example:</span></span>
    
  ```
  Search-CsClsLogging -Pools "pool01.contoso.net" -StartTime "11/20/2012 11:00:00 AM" -OutputFilePath "C:\Logfiles\logfile.txt"
  ```

4. <span data-ttu-id="c5ae2-156">指定した期間内にログの検索を実行するには、-StartTime と-EndTime の定義を行います。</span><span class="sxs-lookup"><span data-stu-id="c5ae2-156">To conduct a search of logs within a specific period of time, define a -StartTime and an -EndTime.</span></span> <span data-ttu-id="c5ae2-157">コンピューター edge01.contoso.net における 1 PM から 2:45 PM までのログが必要です。</span><span class="sxs-lookup"><span data-stu-id="c5ae2-157">You need logs from 1 PM to 2:45 PM on the computer edge01.contoso.net.</span></span> 
    
<span data-ttu-id="c5ae2-158">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="c5ae2-158">For example:</span></span>
    
  ```
  Search-CsClsLogging -Computers "edge01.contoso.net" -StartTime "11/20/2012 1:00:00 PM" -EndTime "11/20/2012 2:45:00 PM" -OutputFilePath "C:\Logfiles\logfile.txt"
  ```

### <a name="to-run-an-advanced-search-by-using-other-criteria-and-matching-options"></a><span data-ttu-id="c5ae2-159">他の条件および一致オプションを使用して高度な検索を行うには</span><span class="sxs-lookup"><span data-stu-id="c5ae2-159">To run an advanced search by using other criteria and matching options</span></span>

1. <span data-ttu-id="c5ae2-160">Skype for Business Server 管理シェルを以下の手順で起動します。[**スタート**]、[**すべてのプログラム**]、[**Skype for Business 2015**]、[**Skype for Business Server 管理シェル**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="c5ae2-160">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
2. <span data-ttu-id="c5ae2-161">特定のコンポーネントのトレースを収集するコマンドを実行するには、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="c5ae2-161">To run a command to collect traces for specific components, type the following:</span></span>
    
   ```
   Search-CsClsLogging -Components <components to search on> -OutputFilePath <fully qualified path to output logs>
   ```

<span data-ttu-id="c5ae2-162">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="c5ae2-162">For example:</span></span>
    
  ```
  Search-CsClsLogging -Components "SIPStack","S4","UserServices" -OutputFilePath "C:\Logfiles\logfile.txt"
  ```

<span data-ttu-id="c5ae2-163">検索の結果、過去 30 分の間に展開内のすべてのコンピューターおよびプールで、SIPStack、S4、および UserServices のトレース コンポーネントを持つすべてのログ エントリが返されます。</span><span class="sxs-lookup"><span data-stu-id="c5ae2-163">The resulting search returns all log entries that have trace components for SIPStack, S4, and UserServices on all computers and pools in your deployment for the past 30 minutes.</span></span>
    
3. <span data-ttu-id="c5ae2-164">同じコンポーネントを使用して、pool01.contoso.net という名前のフロントエンドプールに検索を限定するには、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="c5ae2-164">To limit the search with the same components to just your Front End pool named pool01.contoso.net, type:</span></span>
    
   ```
   Search-CsClsLogging -Components "SIPStack","S4","UserServices" -OutputFilePath "C:\Logfiles\logfile.txt"
   ```

4. <span data-ttu-id="c5ae2-165">複数のパラメーターを使用するコマンドの既定の検索ロジックでは、定義された各パラメーターに対して論理 OR を使用します。</span><span class="sxs-lookup"><span data-stu-id="c5ae2-165">The default search logic for commands with multiple parameters is to use the logical OR with each of the defined parameters.</span></span> <span data-ttu-id="c5ae2-166">この動作を変更するには、 **-matchall**パラメーターを指定します。</span><span class="sxs-lookup"><span data-stu-id="c5ae2-166">You can change this behavior by specifying the **-MatchAll** parameter.</span></span> <span data-ttu-id="c5ae2-167">これを行うには、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="c5ae2-167">To do this, type the following:</span></span>
    
   ```
   Search-CsClsLogging -CallId "d0af828e49fa4dcb99f5f80223a634bc" -Components "SIPStack","S4","UserServices" -MatchAll -OutputFilePath "C:\Logfiles\logfile.txt"
   ```

5. <span data-ttu-id="c5ae2-p114">AlwaysOn のように、シナリオが定期的に実行するように設定されている場合、または、長期にわたって実行するシナリオが定義されている場合、ログはローカル コンピューターではなくファイル共有に置かれることがあります。ファイル共有は、New-CsClsConfiguration で新しい構成を作成するとき、または Set-CsClsConfiguration で既存の構成を変更するときに、CacheFileNetworkFolder パラメーターを使用して定義します。検索のログ コレクションにファイル共有を含めない場合は、次に示すように、SkipNetworkLogs パラメーターを使用します。</span><span class="sxs-lookup"><span data-stu-id="c5ae2-p114">If your scenarios are set to run constantly, such as AlwaysOn, or you have defined a long-running scenario logs may roll off of the local machine onto the file share. You define the file share by using the CacheFileNetworkFolder parameter by using New-CsClsConfiguration to create a new configuration or modifying an existing configuration with Set-CsClsConfiguration. If you do not want the search to include the file share in the collection of logs to search, use the SkipNetworkLogs parameter as follows:</span></span>
    
   ```
   Search-CsClsLogging -Components "SIPStack","S4","UserServices" -StartTime "11/1/2012 00:00:01 AM" -EndTime "11/20/2012 2:45:00 PM" -SkipNetworkLogs -OutputFilePath "C:\Logfiles\logfile.txt"
   ```

## <a name="read-capture-logs-from-the-centralized-logging-service"></a><span data-ttu-id="c5ae2-171">集中ログ サービスからキャプチャしたログの閲覧</span><span class="sxs-lookup"><span data-stu-id="c5ae2-171">Read capture logs from the Centralized Logging Service</span></span>

<span data-ttu-id="c5ae2-172">検索を実行した後で一元管理サービスの実際の利点を実感し、報告された問題を追跡するために使用できるファイルを用意しています。</span><span class="sxs-lookup"><span data-stu-id="c5ae2-172">You realize the real benefit of the Centralized Logging Service after you run the search and you have a file that you can use to track down a reported problem.</span></span> <span data-ttu-id="c5ae2-173">このファイルは、さまざまな方法で読むことができます。</span><span class="sxs-lookup"><span data-stu-id="c5ae2-173">There are a number of ways that you can read the file.</span></span> <span data-ttu-id="c5ae2-174">出力ファイルは標準のテキスト形式なので、メモ帳など、テキスト ファイルを開いて読むことができる任意のプログラムを使用できます。</span><span class="sxs-lookup"><span data-stu-id="c5ae2-174">The output file is in a standard text format and you can use Notepad.exe or any other programs that will allow you to open and read a text file.</span></span> <span data-ttu-id="c5ae2-175">大規模なファイルとより複雑な問題については、一元管理サービスからのログ出力の読み取りと解析のために設計された Snooper などのツールを使うことができます。</span><span class="sxs-lookup"><span data-stu-id="c5ae2-175">For larger files and more complex issues, you could use a tool like Snooper.exe that is designed to read and parse the logging output from the Centralized Logging Service.</span></span> <span data-ttu-id="c5ae2-176">Snooper は、個別のダウンロードとして入手可能なデバッグ ツールに含まれています。</span><span class="sxs-lookup"><span data-stu-id="c5ae2-176">Snooper is included with the Debug Tools that are available as a separate download.</span></span> <span data-ttu-id="c5ae2-177">デバッグツールは、次[https://go.microsoft.com/fwlink/?LinkId=285257](https://go.microsoft.com/fwlink/?LinkId=285257)のページからダウンロードできます。</span><span class="sxs-lookup"><span data-stu-id="c5ae2-177">You can download the Debug Tools here: [https://go.microsoft.com/fwlink/?LinkId=285257](https://go.microsoft.com/fwlink/?LinkId=285257).</span></span> <span data-ttu-id="c5ae2-178">デバッグツールをインストールすると、ショートカットとメニュー項目は作成されません。</span><span class="sxs-lookup"><span data-stu-id="c5ae2-178">When you install the Debug Tools, short cuts and menu items are not created.</span></span> <span data-ttu-id="c5ae2-179">デバッグツールをインストールしたら、Windows エクスプローラー、コマンドラインウィンドウ、または Skype for Business Server Management Shell を開いて、ディレクトリ (既定の場所) C:\Program Files\Skype for Business Server 2015 \ デバッグツールを開きます。</span><span class="sxs-lookup"><span data-stu-id="c5ae2-179">After you install the Debug Tools, open Windows Explorer, a command-line window, or Skype for Business Server Management Shell and go to the directory (default location) C:\Program Files\Skype for Business Server 2015\Debugging Tools.</span></span> <span data-ttu-id="c5ae2-180">Snooper をダブルクリックするか、Snooper を入力して、コマンドラインまたは Skype for Business Server Management Shell を使用している場合は、ENTER キーを押します。</span><span class="sxs-lookup"><span data-stu-id="c5ae2-180">Double-click Snooper.exe or type Snooper.exe, and then press ENTER if you are using the command line or Skype for Business Server Management Shell.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="c5ae2-181">このトピックの目的は、トラブルシューティングの手法を詳細に説明したり議論したりすることではありません。</span><span class="sxs-lookup"><span data-stu-id="c5ae2-181">The intent of this topic is not to detail and discuss troubleshooting techniques.</span></span> <span data-ttu-id="c5ae2-182">トラブルシューティングとそれに関連するプロセスは、複雑な問題です。</span><span class="sxs-lookup"><span data-stu-id="c5ae2-182">Troubleshooting and the processes around it is a complex subject.</span></span> <span data-ttu-id="c5ae2-183">基本的なトラブルシューティングと特定のワークロードのトラブルシューティングの詳細については、「 [https://go.microsoft.com/fwlink/p/?linkId=211003](https://go.microsoft.com/fwlink/p/?linkId=211003)Microsoft Lync Server 2010 リソースキット」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c5ae2-183">For details about troubleshooting basics and troubleshooting specific workloads, see the Microsoft Lync Server 2010 Resource Kit book at [https://go.microsoft.com/fwlink/p/?linkId=211003](https://go.microsoft.com/fwlink/p/?linkId=211003).</span></span> <span data-ttu-id="c5ae2-184">プロセスと手順は、引き続き Skype for Business Server 2015 にも適用されます。</span><span class="sxs-lookup"><span data-stu-id="c5ae2-184">The processes and procedures still apply to Skype for Business Server 2015.</span></span> 
  
### <a name="to-open-a-log-file-in-snooper"></a><span data-ttu-id="c5ae2-185">Snooper でログ ファイルを開くには</span><span class="sxs-lookup"><span data-stu-id="c5ae2-185">To open a log file in Snooper</span></span>

1. <span data-ttu-id="c5ae2-p117">Snooper を使用してログ ファイルを開くためには、ログ ファイルへの読み取りアクセス権が必要です。Snooper を使用してログ ファイルにアクセスするためには、役割ベースのアクセス制御 (RBAC) のセキュリティ グループである CsAdministrator または CsServerAdministrator のメンバーであるか、これらの 2 つのグループのいずれかを含むカスタムの RBAC の役割のメンバーである必要があります。</span><span class="sxs-lookup"><span data-stu-id="c5ae2-p117">To use Snooper and open log files, you need read access to the log files. To use Snooper and access the log files you must be a member of the CsAdministrator or the CsServerAdministrator role-based access control (RBAC) security groups, or a custom RBAC role that contains either of these two groups.</span></span> 
    
2. <span data-ttu-id="c5ae2-188">デバッグ ツール (LyncDebugTools.msi) のインストール後に、Windows エクスプローラーまたはコマンド ラインを使用して、Snooper.exe が存在するディレクトリに移動します。</span><span class="sxs-lookup"><span data-stu-id="c5ae2-188">After the installation of the Debugging Tools (LyncDebugTools.msi), change directory to the location of Snooper.exe using Windows Explorer or from the command line.</span></span> <span data-ttu-id="c5ae2-189">既定では、デバッグツールは、C:\Program Files\Skype for Business Server 2015 \ デバッグツールにあります。</span><span class="sxs-lookup"><span data-stu-id="c5ae2-189">By default, the debugging tools are located in C:\Program Files\Skype for Business Server 2015\Debugging Tools.</span></span> <span data-ttu-id="c5ae2-190">Snooper.exe をダブルクリックするか、実行します。</span><span class="sxs-lookup"><span data-stu-id="c5ae2-190">Double-click or run Snooper.exe.</span></span>
    
3. <span data-ttu-id="c5ae2-191">Snooper を開いたら、[**ファイル**] を右クリックして [**OpenFile**] をクリックします。ログ ファイルを探し、[**開く**] ダイアログ ボックスでファイルを選択して [**開く**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c5ae2-191">After Snooper is open, right-click **File**, click **OpenFile**, find your log files, select a file in the **Open** dialog box, and then click **Open**.</span></span>
    
4. <span data-ttu-id="c5ae2-192">ログファイルの**トレース**メッセージが [**トレース**] タブに表示されます。収集されたトレースのメッセージの内容を表示するには、[**メッセージ**] タブをクリックします。</span><span class="sxs-lookup"><span data-stu-id="c5ae2-192">The log file's **Trace** messages are displayed on the **Trace** tab. Click the **Messages** tab to view the message contents of the collected traces.</span></span>
    
### <a name="to-display-a-call-flow-diagram"></a><span data-ttu-id="c5ae2-193">通話フロー図を表示するには</span><span class="sxs-lookup"><span data-stu-id="c5ae2-193">To display a call flow diagram</span></span>

1. <span data-ttu-id="c5ae2-p119">Snooper を使用してログ ファイルを開くためには、ログ ファイルへの読み取りアクセス権が必要です。Snooper を使用してログ ファイルにアクセスするためには、役割ベースのアクセス制御 (RBAC) のセキュリティ グループである CsAdministrator または CsServerAdministrator のメンバーであるか、これらの 2 つのグループのいずれかを含むカスタムの RBAC の役割のメンバーである必要があります。</span><span class="sxs-lookup"><span data-stu-id="c5ae2-p119">To use Snooper and open log files, you need read access to the log files. To use Snooper and access the log files, you need to be a member of the CsAdministrator or the CsServerAdministrator role-based access control (RBAC) security groups, or a custom RBAC role that contains either of these two groups.</span></span>
    
2. <span data-ttu-id="c5ae2-196">ログ ファイルを開いて [**メッセージ**] タブをクリックし、メッセージ ビューで会話を選択するか、[**トレース**] タブでトレース コンポーネントを選択します。</span><span class="sxs-lookup"><span data-stu-id="c5ae2-196">Open a log file and click the **Messages** tab, select a conversation in the messages view or select a trace component on the **Trace** tab.</span></span>
    
3. <span data-ttu-id="c5ae2-197">[**通話フロー**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c5ae2-197">Click **Call Flow**.</span></span>
    
> [!NOTE]
> <span data-ttu-id="c5ae2-198">コールフローの一部ではないメッセージまたはトレースをクリックすると、図面が表示されず、Snooper の下部に状態メッセージが表示されます。 "このメッセージは、呼び出しの対象になりません" と表示されます。</span><span class="sxs-lookup"><span data-stu-id="c5ae2-198">If you click on a message or trace that is not part of a call flow, the diagram will not appear and a status message appears at the bottom of Snooper stating "This message is not eligible for callfow".</span></span> <span data-ttu-id="c5ae2-199">別のメッセージまたはトレースを選択すると、そのメッセージまたはトレースが通話フローに含まれている場合は通話フローが表示されます。</span><span class="sxs-lookup"><span data-stu-id="c5ae2-199">Choose another message or trace and the call flow will appear if the message or trace is part of a call flow.</span></span> 
  
4. <span data-ttu-id="c5ae2-200">メッセージ間またはトレース線を移動して、通話フロー図が更新されるか変化して、新しい図が表示されるかどうかに注目してください。</span><span class="sxs-lookup"><span data-stu-id="c5ae2-200">Move through the Messages or the Trace lines and note whether the call flow diagram updates or changes to display a new diagram.</span></span>
    
5. <span data-ttu-id="c5ae2-201">要素にマウスをポイントすると、通話メッセージ、エンドポイント、その他のコンポーネントに関する情報を表示されます。</span><span class="sxs-lookup"><span data-stu-id="c5ae2-201">Hover over elements to get information about call messages, endpoints, and other components.</span></span>
