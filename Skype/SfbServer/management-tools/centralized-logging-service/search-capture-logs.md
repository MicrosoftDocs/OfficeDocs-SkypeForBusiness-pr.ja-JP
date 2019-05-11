---
title: Skype for Business Server 2015 で集中ログ サービスが作成したキャプチャ ログを検索する
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 12/20/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 1b75b218-d84f-47a7-8a0a-b7e016b1cc79
description: '概要: 検索し、ビジネス サーバー 2015 の Skype でのログ サービスの一元的なログを読み取る方法を説明します。'
ms.openlocfilehash: 463daf41d0e1e1e7c5a718adcd48bdb3f227feff
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "33914913"
---
# <a name="search-capture-logs-created-by-the-centralized-logging-service-in-skype-for-business-server-2015"></a><span data-ttu-id="08ee1-103">Skype for Business Server 2015 で集中ログ サービスが作成したキャプチャ ログを検索する</span><span class="sxs-lookup"><span data-stu-id="08ee1-103">Search capture logs created by the Centralized Logging Service in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="08ee1-104">**の概要:** 検索し、ビジネス サーバー 2015 の Skype でのログ サービスの一元的なログを読み取る方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="08ee1-104">**Summary:** Learn how to search and read Centralized Logging Service capture logs in Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="08ee1-105">集中ログ サービスの検索機能は、次のような便利で強力です。</span><span class="sxs-lookup"><span data-stu-id="08ee1-105">The search features in the Centralized Logging Service are useful and powerful for the following reasons:</span></span> 
  
- <span data-ttu-id="08ee1-106">検索と結果が、定義する条件に基づいて、1 台のコンピューター、プール、サイト、またはグローバル サイトで実行されます。</span><span class="sxs-lookup"><span data-stu-id="08ee1-106">Your searches and the results are run on a single computer, a pool, a site, or a global scope, based on the criteria you define.</span></span>
    
- <span data-ttu-id="08ee1-107">広範囲での検索から始めて、時間、コンポーネント、コンピューターなど、検索の条件を絞り込むことができます。</span><span class="sxs-lookup"><span data-stu-id="08ee1-107">Your searches can be initially broad and then narrowed down to more targeted criteria such as time, component, or computer.</span></span> <span data-ttu-id="08ee1-108">同じログに対して検索を実行し、検索条件が変更されたときにもう一度ログ セッションを実行する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="08ee1-108">You search against the same logs and don't need to run a logging session again when the search criteria changes.</span></span>
    
- <span data-ttu-id="08ee1-p102">検索の結果は、スコープ内のすべてのコンピューターとプールから収集され、検索条件のすべての結果を表す 1 つの出力ファイルに集約されます (実行しているシナリオおよびシナリオによって取得されたデータに限定されます)。使い慣れた **Snooper**、**メモ帳**などのツールを使用して、出力ファイルおよび展開全体からのトレース メッセージを読み取ります。</span><span class="sxs-lookup"><span data-stu-id="08ee1-p102">The results of your search are gathered from all computers and pools in the scope, collected and aggregated into a single output file that represents all results of the search criteria (limited to the scenarios that have been running and the data captured by the scenarios). You use familiar tools such as **Snooper** or **Notepad** to read the output file and the trace messages from across your deployment.</span></span>
    
<span data-ttu-id="08ee1-p103">個々の各コンピューター上の CLSAgent によって、1 つまたは複数のシナリオに基づいたログが作成されます (1 台のコンピューターあたり 2 つのシナリオをいつでも実行できます)。ログと関連するインデックス ファイルおよびキャッシュ ファイルは、CLSAgent によって管理されます。検索を定義して実行すると、その検索コマンドが CLSAgent に対して取得する情報を指示します。CLSAgent はログ ファイル、キャッシュ ファイル、およびインデックス ファイルに対してクエリを実行し、検索の結果を CLSContoller に返します。CLSController は、検索の範囲内のすべてのコンピューターおよびプールから、検索結果を受け取ります。次に、CLSController はログを集約 (結合) し、最も古いエントリが先頭で、最新のエントリが末尾になるように、時系列に配置します。</span><span class="sxs-lookup"><span data-stu-id="08ee1-p103">The CLSAgent on each individual computer creates the logs based on the scenario or scenarios (two scenarios per computer can be running at any given time). The logs and their associated index and cache files are managed by the CLSAgent. When you define and execute a search, the search command instructs the CLSAgent on what information should be retrieved. The CLSAgent executes the query against the log files, cache files, and index files and returns the results of the search to the CLSContoller. The CLSController receives the search results from all computers and pools in the scope of the search. The CLSController then aggregates (combines) the logs and puts them into time delta order, oldest entry first, and proceeding in time to the most recent entry last.</span></span>
  
<span data-ttu-id="08ee1-117">各検索の後、**Sync-CsClsLogging** コマンドレットが実行されて、検索で使用されるキャッシュ (CLSAgent が管理するキャッシュ ファイルで使用されるものではない) をフラッシュします。</span><span class="sxs-lookup"><span data-stu-id="08ee1-117">After each search, the **Sync-CsClsLogging** cmdlet is run and it flushes the cache used by searches (not to be confused with the cache files maintained by the CLSAgent).</span></span> <span data-ttu-id="08ee1-118">キャッシュをフラッシュすることで、次の検索操作で CLSController はクリーンなログおよびトレース ファイルのキャプチャ バッファーを使用できます。</span><span class="sxs-lookup"><span data-stu-id="08ee1-118">Flushing the cache helps to ensure that there is a clean log and trace file capture buffer at the CLSController for the next search operation.</span></span>
  
<span data-ttu-id="08ee1-119">集中ログ サービスに最も大きなメリットを得るには、調査している問題に関連するコンピューターとプールのログからトレース メッセージのみを返す検索を構成する方法を十分に理解する必要があります。</span><span class="sxs-lookup"><span data-stu-id="08ee1-119">To get the most benefit from the Centralized Logging Service, you need a good understanding of how to configure search to return only trace messages from the computer and pool logs that are relevant to the issue that you are researching.</span></span> <span data-ttu-id="08ee1-120">問題</span><span class="sxs-lookup"><span data-stu-id="08ee1-120">issues</span></span>
  
<span data-ttu-id="08ee1-121">ビジネス サーバー管理シェルには、Skype を使用して、ログ サービスの一元的な検索機能を実行するには、CsAdministrator または CsServerAdministrator の役割に基づくアクセス制御 (RBAC) セキュリティ グループ、またはカスタムの RBAC の役割のいずれかのメンバーをする必要があります。これら 2 つのグループのいずれかが含まれています。</span><span class="sxs-lookup"><span data-stu-id="08ee1-121">To run the Centralized Logging Service search functions by using the Skype for Business Server Management Shell, you must be a member of either the CsAdministrator or the CsServerAdministrator role-based access control (RBAC) security groups, or a custom RBAC role that contains either of these two groups.</span></span> <span data-ttu-id="08ee1-122">(自分で作成したカスタムの RBAC の役割を含む) には、このコマンドレットが割り当てられているすべての RBAC の役割の一覧を返すするには、ビジネスのサーバー管理シェルまたは Windows PowerShell プロンプトに、Skype から次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="08ee1-122">To return a list of all the RBAC roles that this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Skype for Business Server Management Shell or the Windows PowerShell prompt:</span></span>
  
```
Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Skype for Business Server 2015 cmdlet"}
```

<span data-ttu-id="08ee1-123">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="08ee1-123">For example:</span></span>
  
```
Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Set-CsClsConfiguration"}
```

<span data-ttu-id="08ee1-124">このトピックの以降の部分では、トラブルシューティングを最適化するための検索の定義方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="08ee1-124">The remainder of this topic focuses on how to define a search to optimize your troubleshooting.</span></span>
  
### <a name="to-run-a-basic-search-by-using-the-centralized-logging-service"></a><span data-ttu-id="08ee1-125">集中ログ サービスを使用して基本的な検索を実行するには</span><span class="sxs-lookup"><span data-stu-id="08ee1-125">To run a basic search by using the Centralized Logging Service</span></span>

1. <span data-ttu-id="08ee1-126">Skype for Business Server 管理シェルを以下の手順で起動します。[**スタート**]、[**すべてのプログラム**]、[**Skype for Business 2015**]、[**Skype for Business Server 管理シェル**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="08ee1-126">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
2. <span data-ttu-id="08ee1-127">AlwaysOn シナリオが展開内でグローバル スコープで実行していることを確認し、コマンド プロンプトで次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="08ee1-127">Make sure that you have the AlwaysOn scenario running in your deployment at the global scope and then type the following at a command prompt:</span></span>
    
   ```
   Search-CsClsLogging -OutputFilePath <string value of path and file to write the output file>
   ```

> [!NOTE]
> <span data-ttu-id="08ee1-128">既定では、Search-CsClsLogging は検索の結果をコンソールに送ります。</span><span class="sxs-lookup"><span data-stu-id="08ee1-128">By default, Search-CsClsLogging sends the results of the search to the console.</span></span> <span data-ttu-id="08ee1-129">-OutputFilePath を使用して、検索結果をファイルに保存する場合は、_\<ファイルの絶対パスを文字列\>_。</span><span class="sxs-lookup"><span data-stu-id="08ee1-129">If you want to save the search results to a file, use -OutputFilePath  _\<string fully qualified file path\>_.</span></span> <span data-ttu-id="08ee1-130">-OutputFilePath パラメーターを定義するには、「パスとファイル名 (たとえば引用符で囲まれた文字列の形式でパラメーターの一部としての使用」を指定していますください。C:\LogFiles\SearchOutput.txt)。</span><span class="sxs-lookup"><span data-stu-id="08ee1-130">To define the -OutputFilePath parameter, supply a path and a filename as part of the parameter in a string format enclosed in quotation marks (for example; C:\LogFiles\SearchOutput.txt).</span></span> <span data-ttu-id="08ee1-131">この例では、ディレクトリ C:\LogFiles が存在し、フォルダー内のファイルに対して読み取りと書き込みのアクセス許可 (NTFS の場合は変更のアクセス許可) を持っている必要があります。</span><span class="sxs-lookup"><span data-stu-id="08ee1-131">In this example, you must ensure that the directory C:\LogFiles exists and that you have permissions to Read and Write (NTFS permission Modify) files in the folder.</span></span> <span data-ttu-id="08ee1-132">出力は追加され、上書きはされません。</span><span class="sxs-lookup"><span data-stu-id="08ee1-132">The output is appended to and is not overwritten.</span></span> <span data-ttu-id="08ee1-133">個別のファイルが必要な場合は、検索ごとに個々のファイル名を定義します。</span><span class="sxs-lookup"><span data-stu-id="08ee1-133">If you need separate files, define a distinct file name for each search.</span></span> 
  
<span data-ttu-id="08ee1-134">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="08ee1-134">For example:</span></span>
    
  ```
  Search-CsClsLogging -OutputFilePath "C:\LogFiles\logfile.txt"
  ```

### <a name="to-run-a-basic-search-on-a-pool-or-computer-by-using-the-centralized-logging-service"></a><span data-ttu-id="08ee1-135">集中ログ サービスを使用してプールやコンピューターの基本的な検索を実行するには</span><span class="sxs-lookup"><span data-stu-id="08ee1-135">To run a basic search on a pool or computer by using the Centralized Logging Service</span></span>

1. <span data-ttu-id="08ee1-136">特定のプールやコンピューターの検索を制限するを使用して、コンピューターのパラメーターを引用符で囲まれて、次のように、コンマで区切られたコンピューターの完全修飾名で定義されているコンピューターで。</span><span class="sxs-lookup"><span data-stu-id="08ee1-136">To limit the search to a specific pool or computer, use the -Computers parameter with the computer defined by a computer fully qualified name, enclosed in quotation marks and separated by a comma as follows:</span></span>
    
   ```
   Search-CsClsLogging -Computers <string value of computer names> -OutputFilePath <string value of path and file to write the output file>
   ```

<span data-ttu-id="08ee1-137">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="08ee1-137">For example:</span></span>
    
  ```
  Search-CsClsLogging -Computers "fe01.contoso.net" -OutputFilePath "C:\LogFiles\logfile.txt"
  ```

2. <span data-ttu-id="08ee1-138">複数のコンピューターを検索するには、次に示すように、複数のコンピューター名をそれぞれ引用符で囲み、コンマで区切って入力します。</span><span class="sxs-lookup"><span data-stu-id="08ee1-138">To search more than one computer, type multiple computer names enclosed in quotation marks and separated by commas, such as the following:</span></span>
    
   ```
   Search-CsClsLogging -Computers "fe01.contoso.net", "fe02.contoso.net", "fe03.contoso.net" -OutputFilePath "C:\LogFiles\logfile.txt"
   ```

3. <span data-ttu-id="08ee1-139">変更する 1 台のコンピューターではなくプール全体を検索する場合は、コンマで区切られた、プールまたは引用符で囲まれたプールで、プール、コンピューター名を削除および置換する-コンピューターのパラメーターです。</span><span class="sxs-lookup"><span data-stu-id="08ee1-139">If you need to search an entire pool instead of a single computer, change the -Computers parameter to -Pools, remove the computer name, and replace it with the pool or pools in quotation marks separated by commas.</span></span>
    
    <span data-ttu-id="08ee1-140">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="08ee1-140">For example:</span></span>
    
   ```
   Search-CsClsLogging -Pools "pool01.contoso.net" -OutputFilePath "C:\Logfiles\logfile.txt"
   ```

4. <span data-ttu-id="08ee1-141">検索コマンドを使用して、プールのフロント エンド プール、エッジ プール、永続的なチャット サーバー プール、または、配置内のリソース プールとして定義されている他のユーザーなど、配置内のすべてのプールを使用できます。</span><span class="sxs-lookup"><span data-stu-id="08ee1-141">When using the search commands, pools can be any pool in your deployment, such as Front End pools, Edge pools, Persistent Chat Server pools, or others that are defined as a pool in your deployment.</span></span>
    
    <span data-ttu-id="08ee1-142">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="08ee1-142">For example:</span></span>
    
   ```
   Search-CsClsLogging -Pools "pool01.contoso.net", "pchatpool01.contoso.net", "intedgepool01.contoso.net" -OutputFilePath "C:\Logfiles\logfile.txt"
   ```

### <a name="to-run-a-search-by-using-time-parameters"></a><span data-ttu-id="08ee1-143">時間のパラメーターを使用して検索を実行するには</span><span class="sxs-lookup"><span data-stu-id="08ee1-143">To run a search by using time parameters</span></span>

1. <span data-ttu-id="08ee1-144">Skype for Business Server 管理シェルを以下の手順で起動します。[**スタート**]、[**すべてのプログラム**]、[**Skype for Business 2015**]、[**Skype for Business Server 管理シェル**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="08ee1-144">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
2. <span data-ttu-id="08ee1-145">既定では、検索の時間固有のパラメーターの開始時間は、検索を開始する時間の 25 分前です。</span><span class="sxs-lookup"><span data-stu-id="08ee1-145">By default, the beginning time for a search's time-specific parameters is 25 minutes prior to five minutes after the time you initiate the search.</span></span> <span data-ttu-id="08ee1-146">つまり、検索を 4:00:00 PM に開始する場合、検索の開始時間には 3:35:00 から 4:05:00 PM までと表示されます。</span><span class="sxs-lookup"><span data-stu-id="08ee1-146">In other words, if we search at 4:00:00 PM, then the search start time will show as 3:35:00 PM to 4:05:00 PM.</span></span> <span data-ttu-id="08ee1-147">60 分または現在の時刻より前に 3 時間を検索する場合は、- 開始時刻パラメーターを使用し、検索を開始する時刻を示す日付と時刻の文字列を設定します。</span><span class="sxs-lookup"><span data-stu-id="08ee1-147">If you need to search 60 minutes or 3 hours prior to the current time, use the -StartTime parameter and set the date and time string to indicate the time you want the search to start.</span></span> 
    
    <span data-ttu-id="08ee1-148">などの日付と時刻の範囲を定義するための開始時刻と、終了時刻を使用するを定義できます午前 8 と 9 AM の間で検索 2012/11/20 に、プールに。</span><span class="sxs-lookup"><span data-stu-id="08ee1-148">For example, by using -StartTime and -EndTime to define a time and date range, you can define a search between 8 AM and 9 AM on 11/20/2012 on your pool.</span></span> <span data-ttu-id="08ee1-149">次に示すように、出力パスを設定して、c:\logfile.txt という名前のファイルに結果を書き込むことができます。</span><span class="sxs-lookup"><span data-stu-id="08ee1-149">You can set the output path to write the results to a file named c:\logfile.txt as follows:</span></span>
    
   ```
   Search-CsClsLogging -Pools "pool01.contoso.net" -StartTime "11/20/2012 08:00:00 AM" -EndTime "11/20/2012 09:00:00 AM" -OutputFilePath "C:\Logfiles\logfile.txt"
   ```

> [!NOTE]
> <span data-ttu-id="08ee1-150">日時の文字列は、"日付 時間" と"時間 日付" のどちらででも指定できます。</span><span class="sxs-lookup"><span data-stu-id="08ee1-150">The time and date string that you specify can be "date time" or "time date.</span></span> <span data-ttu-id="08ee1-151">"コマンドが文字列を解析し、適切な値を使用して、日付と時刻からコマンドレットを実行しているマシンでは、ロケールとカルチャの設定をします。</span><span class="sxs-lookup"><span data-stu-id="08ee1-151">" The command will parse the string and use the appropriate values for date and time and your locale and culture settings on the machine you are running cmdlet from.</span></span> 
  
3. <span data-ttu-id="08ee1-152">11/20/2012 11時 00分: 00 AM で始まるログを取得する場合の開始時刻を定義します。</span><span class="sxs-lookup"><span data-stu-id="08ee1-152">If you want to retrieve logs beginning at 11:00:00 AM on 11/20/2012, you define the -StartTime.</span></span> <span data-ttu-id="08ee1-153">検索の既定の時間範囲は、特定終了時刻を定義する場合を除き、30 分です。</span><span class="sxs-lookup"><span data-stu-id="08ee1-153">The default time range for the search is 30 minutes unless you define a specific -EndTime.</span></span> <span data-ttu-id="08ee1-154">検索の結果、定義したコンピューターまたはプールから、11:00:00 AM ～ 11:30:00 AM の範囲のログが返されます。</span><span class="sxs-lookup"><span data-stu-id="08ee1-154">The resulting search will return logs from the defined computer or pools from 11:00:00 AM to 11:30:00 AM.</span></span>
    
<span data-ttu-id="08ee1-155">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="08ee1-155">For example:</span></span>
    
  ```
  Search-CsClsLogging -Pools "pool01.contoso.net" -StartTime "11/20/2012 11:00:00 AM" -OutputFilePath "C:\Logfiles\logfile.txt"
  ```

4. <span data-ttu-id="08ee1-156">特定の期間内には、ログの検索を行うの開始時刻と、終了時刻を定義します。</span><span class="sxs-lookup"><span data-stu-id="08ee1-156">To conduct a search of logs within a specific period of time, define a -StartTime and an -EndTime.</span></span> <span data-ttu-id="08ee1-157">コンピューター edge01.contoso.net における 1 PM から 2:45 PM までのログが必要です。</span><span class="sxs-lookup"><span data-stu-id="08ee1-157">You need logs from 1 PM to 2:45 PM on the computer edge01.contoso.net.</span></span> 
    
<span data-ttu-id="08ee1-158">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="08ee1-158">For example:</span></span>
    
  ```
  Search-CsClsLogging -Computers "edge01.contoso.net" -StartTime "11/20/2012 1:00:00 PM" -EndTime "11/20/2012 2:45:00 PM" -OutputFilePath "C:\Logfiles\logfile.txt"
  ```

### <a name="to-run-an-advanced-search-by-using-other-criteria-and-matching-options"></a><span data-ttu-id="08ee1-159">他の条件および一致オプションを使用して高度な検索を行うには</span><span class="sxs-lookup"><span data-stu-id="08ee1-159">To run an advanced search by using other criteria and matching options</span></span>

1. <span data-ttu-id="08ee1-160">Skype for Business Server 管理シェルを以下の手順で起動します。[**スタート**]、[**すべてのプログラム**]、[**Skype for Business 2015**]、[**Skype for Business Server 管理シェル**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="08ee1-160">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
2. <span data-ttu-id="08ee1-161">特定のコンポーネントのトレースを収集するコマンドを実行するには、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="08ee1-161">To run a command to collect traces for specific components, type the following:</span></span>
    
   ```
   Search-CsClsLogging -Components <components to search on> -OutputFilePath <fully qualified path to output logs>
   ```

<span data-ttu-id="08ee1-162">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="08ee1-162">For example:</span></span>
    
  ```
  Search-CsClsLogging -Components "SIPStack","S4","UserServices" -OutputFilePath "C:\Logfiles\logfile.txt"
  ```

<span data-ttu-id="08ee1-163">検索の結果、過去 30 分の間に展開内のすべてのコンピューターおよびプールで、SIPStack、S4、および UserServices のトレース コンポーネントを持つすべてのログ エントリが返されます。</span><span class="sxs-lookup"><span data-stu-id="08ee1-163">The resulting search returns all log entries that have trace components for SIPStack, S4, and UserServices on all computers and pools in your deployment for the past 30 minutes.</span></span>
    
3. <span data-ttu-id="08ee1-164">Pool01.contoso.net をという名前のフロント エンド プールだけに同じコンポーネントを使用して検索を制限するには、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="08ee1-164">To limit the search with the same components to just your Front End pool named pool01.contoso.net, type:</span></span>
    
   ```
   Search-CsClsLogging -Components "SIPStack","S4","UserServices" -OutputFilePath "C:\Logfiles\logfile.txt"
   ```

4. <span data-ttu-id="08ee1-165">複数のパラメーターを使用するコマンドの既定の検索ロジックでは、定義された各パラメーターに対して論理 OR を使用します。</span><span class="sxs-lookup"><span data-stu-id="08ee1-165">The default search logic for commands with multiple parameters is to use the logical OR with each of the defined parameters.</span></span> <span data-ttu-id="08ee1-166">**MatchAll ・** パラメーターを指定することによって、この動作を変更できます。</span><span class="sxs-lookup"><span data-stu-id="08ee1-166">You can change this behavior by specifying the **-MatchAll** parameter.</span></span> <span data-ttu-id="08ee1-167">これを行うには、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="08ee1-167">To do this, type the following:</span></span>
    
   ```
   Search-CsClsLogging -CallId "d0af828e49fa4dcb99f5f80223a634bc" -Components "SIPStack","S4","UserServices" -MatchAll -OutputFilePath "C:\Logfiles\logfile.txt"
   ```

5. <span data-ttu-id="08ee1-p114">AlwaysOn のように、シナリオが定期的に実行するように設定されている場合、または、長期にわたって実行するシナリオが定義されている場合、ログはローカル コンピューターではなくファイル共有に置かれることがあります。ファイル共有は、New-CsClsConfiguration で新しい構成を作成するとき、または Set-CsClsConfiguration で既存の構成を変更するときに、CacheFileNetworkFolder パラメーターを使用して定義します。検索のログ コレクションにファイル共有を含めない場合は、次に示すように、SkipNetworkLogs パラメーターを使用します。</span><span class="sxs-lookup"><span data-stu-id="08ee1-p114">If your scenarios are set to run constantly, such as AlwaysOn, or you have defined a long-running scenario logs may roll off of the local machine onto the file share. You define the file share by using the CacheFileNetworkFolder parameter by using New-CsClsConfiguration to create a new configuration or modifying an existing configuration with Set-CsClsConfiguration. If you do not want the search to include the file share in the collection of logs to search, use the SkipNetworkLogs parameter as follows:</span></span>
    
   ```
   Search-CsClsLogging -Components "SIPStack","S4","UserServices" -StartTime "11/1/2012 00:00:01 AM" -EndTime "11/20/2012 2:45:00 PM" -SkipNetworkLogs -OutputFilePath "C:\Logfiles\logfile.txt"
   ```

## <a name="read-capture-logs-from-the-centralized-logging-service"></a><span data-ttu-id="08ee1-171">集中ログ サービスからキャプチャしたログの閲覧</span><span class="sxs-lookup"><span data-stu-id="08ee1-171">Read capture logs from the Centralized Logging Service</span></span>

<span data-ttu-id="08ee1-172">集中ログ サービスの本当の利益は、報告された問題を追跡するために使用できるファイルを使用して検索を実行した後に気付きました。</span><span class="sxs-lookup"><span data-stu-id="08ee1-172">You realize the real benefit of the Centralized Logging Service after you run the search and you have a file that you can use to track down a reported problem.</span></span> <span data-ttu-id="08ee1-173">このファイルは、さまざまな方法で読むことができます。</span><span class="sxs-lookup"><span data-stu-id="08ee1-173">There are a number of ways that you can read the file.</span></span> <span data-ttu-id="08ee1-174">出力ファイルは標準のテキスト形式なので、メモ帳など、テキスト ファイルを開いて読むことができる任意のプログラムを使用できます。</span><span class="sxs-lookup"><span data-stu-id="08ee1-174">The output file is in a standard text format and you can use Notepad.exe or any other programs that will allow you to open and read a text file.</span></span> <span data-ttu-id="08ee1-175">サイズの大きいファイルと複雑な問題については、読み取り、集中ログ サービスのログ出力を解析するように設計された Snooper.exe のようなツールを使用できます。</span><span class="sxs-lookup"><span data-stu-id="08ee1-175">For larger files and more complex issues, you could use a tool like Snooper.exe that is designed to read and parse the logging output from the Centralized Logging Service.</span></span> <span data-ttu-id="08ee1-176">Snooper は、個別のダウンロードとして入手可能なデバッグ ツールに含まれています。</span><span class="sxs-lookup"><span data-stu-id="08ee1-176">Snooper is included with the Debug Tools that are available as a separate download.</span></span> <span data-ttu-id="08ee1-177">デバッグ ツールは、ここをダウンロードすることができます: [https://go.microsoft.com/fwlink/?LinkId=285257](https://go.microsoft.com/fwlink/?LinkId=285257)。</span><span class="sxs-lookup"><span data-stu-id="08ee1-177">You can download the Debug Tools here: [https://go.microsoft.com/fwlink/?LinkId=285257](https://go.microsoft.com/fwlink/?LinkId=285257).</span></span> <span data-ttu-id="08ee1-178">デバッグ ツールをインストールすると、ショート カットとメニュー項目は作成されません。</span><span class="sxs-lookup"><span data-stu-id="08ee1-178">When you install the Debug Tools, short cuts and menu items are not created.</span></span> <span data-ttu-id="08ee1-179">デバッグ ツールをインストールした後 Windows エクスプ ローラー、コマンド ライン ウィンドウ、または Skype ビジネス サーバー管理シェルを開きビジネス サーバー 2015\Debugging ツールの C:\Program Files\Skype ディレクトリ (既定の場所) に移動します。</span><span class="sxs-lookup"><span data-stu-id="08ee1-179">After you install the Debug Tools, open Windows Explorer, a command-line window, or Skype for Business Server Management Shell and go to the directory (default location) C:\Program Files\Skype for Business Server 2015\Debugging Tools.</span></span> <span data-ttu-id="08ee1-180">Snooper.exe をダブルクリックして Snooper.exe を指定して、ビジネス サーバー管理シェルのコマンド ・ ラインまたは Skype を使用している場合、[ENTER キーを押します。</span><span class="sxs-lookup"><span data-stu-id="08ee1-180">Double-click Snooper.exe or type Snooper.exe, and then press ENTER if you are using the command line or Skype for Business Server Management Shell.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="08ee1-181">このトピックの目的は、トラブルシューティングの手法を詳細に説明したり議論したりすることではありません。</span><span class="sxs-lookup"><span data-stu-id="08ee1-181">The intent of this topic is not to detail and discuss troubleshooting techniques.</span></span> <span data-ttu-id="08ee1-182">トラブルシューティングとそれに関連するプロセスは、複雑な問題です。</span><span class="sxs-lookup"><span data-stu-id="08ee1-182">Troubleshooting and the processes around it is a complex subject.</span></span> <span data-ttu-id="08ee1-183">基本的なトラブルシューティングおよび特定の作業負荷のトラブルシューティングに関する詳細を参照してください Microsoft Lync Server 2010 リソース キットでの[https://go.microsoft.com/fwlink/p/?linkId=211003](https://go.microsoft.com/fwlink/p/?linkId=211003)。</span><span class="sxs-lookup"><span data-stu-id="08ee1-183">For details about troubleshooting basics and troubleshooting specific workloads, see the Microsoft Lync Server 2010 Resource Kit book at [https://go.microsoft.com/fwlink/p/?linkId=211003](https://go.microsoft.com/fwlink/p/?linkId=211003).</span></span> <span data-ttu-id="08ee1-184">プロセスと手順にも当てはまります Skype をビジネス サーバー 2015。</span><span class="sxs-lookup"><span data-stu-id="08ee1-184">The processes and procedures still apply to Skype for Business Server 2015.</span></span> 
  
### <a name="to-open-a-log-file-in-snooper"></a><span data-ttu-id="08ee1-185">Snooper でログ ファイルを開くには</span><span class="sxs-lookup"><span data-stu-id="08ee1-185">To open a log file in Snooper</span></span>

1. <span data-ttu-id="08ee1-p117">Snooper を使用してログ ファイルを開くためには、ログ ファイルへの読み取りアクセス権が必要です。Snooper を使用してログ ファイルにアクセスするためには、役割ベースのアクセス制御 (RBAC) のセキュリティ グループである CsAdministrator または CsServerAdministrator のメンバーであるか、これらの 2 つのグループのいずれかを含むカスタムの RBAC の役割のメンバーである必要があります。</span><span class="sxs-lookup"><span data-stu-id="08ee1-p117">To use Snooper and open log files, you need read access to the log files. To use Snooper and access the log files you must be a member of the CsAdministrator or the CsServerAdministrator role-based access control (RBAC) security groups, or a custom RBAC role that contains either of these two groups.</span></span> 
    
2. <span data-ttu-id="08ee1-188">デバッグ ツール (LyncDebugTools.msi) のインストール後に、Windows エクスプローラーまたはコマンド ラインを使用して、Snooper.exe が存在するディレクトリに移動します。</span><span class="sxs-lookup"><span data-stu-id="08ee1-188">After the installation of the Debugging Tools (LyncDebugTools.msi), change directory to the location of Snooper.exe using Windows Explorer or from the command line.</span></span> <span data-ttu-id="08ee1-189">既定では、デバッグ ツールは、ビジネス サーバー 2015\Debugging ツールの C:\Program Files\Skype に配置されます。</span><span class="sxs-lookup"><span data-stu-id="08ee1-189">By default, the debugging tools are located in C:\Program Files\Skype for Business Server 2015\Debugging Tools.</span></span> <span data-ttu-id="08ee1-190">Snooper.exe をダブルクリックするか、実行します。</span><span class="sxs-lookup"><span data-stu-id="08ee1-190">Double-click or run Snooper.exe.</span></span>
    
3. <span data-ttu-id="08ee1-191">Snooper を開いたら、[**ファイル**] を右クリックして [**OpenFile**] をクリックします。ログ ファイルを探し、[**開く**] ダイアログ ボックスでファイルを選択して [**開く**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="08ee1-191">After Snooper is open, right-click **File**, click **OpenFile**, find your log files, select a file in the **Open** dialog box, and then click **Open**.</span></span>
    
4. <span data-ttu-id="08ee1-192">ログ ファイルの**トレース**メッセージが表示されるタブは**トレース**で収集されたトレースのメッセージの内容を表示するのには [**メッセージ**] タブをクリックします。</span><span class="sxs-lookup"><span data-stu-id="08ee1-192">The log file's **Trace** messages are displayed on the **Trace** tab. Click the **Messages** tab to view the message contents of the collected traces.</span></span>
    
### <a name="to-display-a-call-flow-diagram"></a><span data-ttu-id="08ee1-193">通話フロー図を表示するには</span><span class="sxs-lookup"><span data-stu-id="08ee1-193">To display a call flow diagram</span></span>

1. <span data-ttu-id="08ee1-p119">Snooper を使用してログ ファイルを開くためには、ログ ファイルへの読み取りアクセス権が必要です。Snooper を使用してログ ファイルにアクセスするためには、役割ベースのアクセス制御 (RBAC) のセキュリティ グループである CsAdministrator または CsServerAdministrator のメンバーであるか、これらの 2 つのグループのいずれかを含むカスタムの RBAC の役割のメンバーである必要があります。</span><span class="sxs-lookup"><span data-stu-id="08ee1-p119">To use Snooper and open log files, you need read access to the log files. To use Snooper and access the log files, you need to be a member of the CsAdministrator or the CsServerAdministrator role-based access control (RBAC) security groups, or a custom RBAC role that contains either of these two groups.</span></span>
    
2. <span data-ttu-id="08ee1-196">ログ ファイルを開いて [**メッセージ**] タブをクリックし、メッセージ ビューで会話を選択するか、[**トレース**] タブでトレース コンポーネントを選択します。</span><span class="sxs-lookup"><span data-stu-id="08ee1-196">Open a log file and click the **Messages** tab, select a conversation in the messages view or select a trace component on the **Trace** tab.</span></span>
    
3. <span data-ttu-id="08ee1-197">[**通話フロー**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="08ee1-197">Click **Call Flow**.</span></span>
    
> [!NOTE]
> <span data-ttu-id="08ee1-198">メッセージまたは呼び出しの流れの一部ではないのトレース] をクリックする場合は、図は表示されず、できる Snooper は、「このメッセージは callfow の対象ではない」という内容下部にステータス メッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="08ee1-198">If you click on a message or trace that is not part of a call flow, the diagram will not appear and a status message appears at the bottom of Snooper stating "This message is not eligible for callfow".</span></span> <span data-ttu-id="08ee1-199">別のメッセージまたはトレースを選択すると、そのメッセージまたはトレースが通話フローに含まれている場合は通話フローが表示されます。</span><span class="sxs-lookup"><span data-stu-id="08ee1-199">Choose another message or trace and the call flow will appear if the message or trace is part of a call flow.</span></span> 
  
4. <span data-ttu-id="08ee1-200">メッセージ間またはトレース線を移動して、通話フロー図が更新されるか変化して、新しい図が表示されるかどうかに注目してください。</span><span class="sxs-lookup"><span data-stu-id="08ee1-200">Move through the Messages or the Trace lines and note whether the call flow diagram updates or changes to display a new diagram.</span></span>
    
5. <span data-ttu-id="08ee1-201">要素にマウスをポイントすると、通話メッセージ、エンドポイント、その他のコンポーネントに関する情報を表示されます。</span><span class="sxs-lookup"><span data-stu-id="08ee1-201">Hover over elements to get information about call messages, endpoints, and other components.</span></span>
