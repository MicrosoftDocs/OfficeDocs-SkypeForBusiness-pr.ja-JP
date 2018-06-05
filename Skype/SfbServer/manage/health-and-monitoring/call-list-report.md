---
title: Skype for Business Server 2015 の応答グループの通話リスト レポート
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: a2d3e08b-511b-4507-abba-8ff71aa27c8e
description: '概要: は、ビジネス サーバー 2015 の Skype で応答グループ アプリケーションについて説明します。'
ms.openlocfilehash: 6f7d2938f02b84942b2dc09e4fc3058ab6ee63db
ms.sourcegitcommit: a79668bb45b73a63bea5c249d76a4c4c2530a096
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/05/2018
ms.locfileid: "19569000"
---
# <a name="response-group-call-list-report-in-skype-for-business-server-2015"></a><span data-ttu-id="a407b-103">Skype for Business Server 2015 の応答グループの通話リスト レポート</span><span class="sxs-lookup"><span data-stu-id="a407b-103">Response Group Call List Report in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="a407b-104">**の概要:** ビジネス サーバー 2015 の Skype で応答グループ アプリケーションについて説明します。</span><span class="sxs-lookup"><span data-stu-id="a407b-104">**Summary:** Learn about the Response Group application in Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="a407b-105">応答グループ アプリケーションに応答するサーバー 2015 のビジネス用の Skype の手段を提供して、ダイヤルされた番号と、必要に応じて、一連の質問に応答を呼び出し元の電話呼び出しのルートがベースします。</span><span class="sxs-lookup"><span data-stu-id="a407b-105">The Response Group application provides a way for Skype for Business Server 2015 to answer and route phone calls based on the number that was dialed and, optionally, on the caller's responses to a series of questions.</span></span> <span data-ttu-id="a407b-106">通常、応答グループの呼び出しは個々 のユーザーにルーティングされていないが、代わりに、エージェント グループと呼ばれる人のチームにルーティングされます。</span><span class="sxs-lookup"><span data-stu-id="a407b-106">Typically, Response Group calls are not routed to an individual person but, instead, are routed to a team of people referred to as an agent group.</span></span> <span data-ttu-id="a407b-107">など、ヘルプ デスクの電話番号を呼び出す他のビジネス サーバー 2015 の Skype にその呼び出しを最初に利用できるヘルプ デスク エージェントがルーティング自動的にできます。</span><span class="sxs-lookup"><span data-stu-id="a407b-107">For example, if someone calls the phone number for your help desk, Skype for Business Server 2015 can automatically route that call to the first available help desk agent.</span></span> <span data-ttu-id="a407b-108">Skype ビジネス サーバーの代わりに、一連の質問 ("キーを押して 1 ハードウェアに問題がある場合に頼むでしょう。</span><span class="sxs-lookup"><span data-stu-id="a407b-108">Alternatively, Skype for Business Server could ask a series of questions ("Press 1 if you are having hardware problems.</span></span> <span data-ttu-id="a407b-109">ソフトウェアに問題がある場合は、2 を押します。</span><span class="sxs-lookup"><span data-stu-id="a407b-109">Press 2 if you are having software problems.</span></span> <span data-ttu-id="a407b-110">3 を押してネットワークに問題がある場合。")それらの質問に対する回答に基づいて、最も適切なヘルプ デスク エージェントへの呼び出しをルーティングします。</span><span class="sxs-lookup"><span data-stu-id="a407b-110">Press 3 if you are having network problems.") and then route the call to the most appropriate help desk agent based on the answer to those questions.</span></span>
  
<span data-ttu-id="a407b-p102">応答グループの通話リスト レポートは、特定の期間に特定の種類の通話に対して行われた通話のコレクションです。応答グループの使用レポート (応答グループの通話リスト レポートを開くには先にこのレポートを開く必要があります) では、次の種類の通話が認識されます。</span><span class="sxs-lookup"><span data-stu-id="a407b-p102">The Response Group Call List Report represents a collection of calls made for a specified period of time and for a specified type of call. The Response Group Usage Report (which must be opened first before you can open the Response Group Call List Report) recognizes the following call types:</span></span>
  
- <span data-ttu-id="a407b-p103">**受信した通話**。応答グループ アプリケーションのすべてのインスタンスで受信した通話の合計数。</span><span class="sxs-lookup"><span data-stu-id="a407b-p103">**Received calls**. Total number of calls received by all instances of the Response Group application.</span></span>
    
- <span data-ttu-id="a407b-p104">**正常な通話**。応答グループ アプリケーションによって選択された通話の合計数。</span><span class="sxs-lookup"><span data-stu-id="a407b-p104">**Successful calls**. Total number of calls that were picked up by the Response Group application.</span></span>
    
- <span data-ttu-id="a407b-p105">**提供された通話**。応答グループ エージェントによって転送された通話の合計数。</span><span class="sxs-lookup"><span data-stu-id="a407b-p105">**Offered calls**. Total number of calls that were transferred to a Response Group agent.</span></span>
    
- <span data-ttu-id="a407b-p106">**応答した通話**。応答グループ エージェントが実際に応答した通話の合計数。</span><span class="sxs-lookup"><span data-stu-id="a407b-p106">**Answered calls**. Total number of calls that were actually answered by a Response Group agent.</span></span>
    
- <span data-ttu-id="a407b-121">**放棄された呼び出しの割合です。**</span><span class="sxs-lookup"><span data-stu-id="a407b-121">**Percentage of abandoned calls.**</span></span> <span data-ttu-id="a407b-122">応答グループ アプリケーションによって受信されたが、エージェントが応答しなかった通話のパーセンテージ。</span><span class="sxs-lookup"><span data-stu-id="a407b-122">Percentage of calls that were received by the Response Group application but were never answered by an agent.</span></span> <span data-ttu-id="a407b-123">この値は、受信した通話数から応答した通話数を引いた値を受信した通話数で割って計算されます。</span><span class="sxs-lookup"><span data-stu-id="a407b-123">This value is calculated by subtracting the Answered calls from the Received calls, and then dividing that value by the number of Received calls.</span></span> <span data-ttu-id="a407b-124">たとえば、受信した通話数が 10 件、応答した通話数が 7 件の場合、10 から 7 を引いて 3 件が応答のない通話数として残ります。</span><span class="sxs-lookup"><span data-stu-id="a407b-124">For example, if you received 10 calls and 7 were answered, you would subtract 7 from 10, leaving 3 unanswered calls.</span></span> <span data-ttu-id="a407b-125">この値を 10 で割ると、破棄された通話のパーセンテージは 30% になります。</span><span class="sxs-lookup"><span data-stu-id="a407b-125">That value would then be divided by 10, giving you an abandoned call percentage of 30%.</span></span>
    
- <span data-ttu-id="a407b-p108">**転送された通話**。キューのタイムアウトまたはキューのオーバーフローによって転送された、応答グループの通話の合計数。</span><span class="sxs-lookup"><span data-stu-id="a407b-p108">**Transferred calls**. Total number of Response Group calls that were transferred because of a queue timeout or queue overflow.</span></span>
    
## <a name="accessing-the-response-group-call-list-report"></a><span data-ttu-id="a407b-128">応答グループの通話リスト レポートへのアクセス</span><span class="sxs-lookup"><span data-stu-id="a407b-128">Accessing the Response Group Call List Report</span></span>

<span data-ttu-id="a407b-129">応答グループを呼び出す] ボックスの一覧レポートは、[ビジネス サーバー 2015 の Skype で応答グループの使用状況レポート](response-group-usage-report.md)に次の測定値のいずれかをクリックしてのみアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="a407b-129">The Response Group Call List Report can only be accessed by clicking one of the following metrics found on the [Response Group Usage Report in Skype for Business Server 2015](response-group-usage-report.md):</span></span>
  
- <span data-ttu-id="a407b-130">受信した通話</span><span class="sxs-lookup"><span data-stu-id="a407b-130">Received calls</span></span>
    
- <span data-ttu-id="a407b-131">正常な通話</span><span class="sxs-lookup"><span data-stu-id="a407b-131">Successful calls</span></span>
    
- <span data-ttu-id="a407b-132">提供された通話</span><span class="sxs-lookup"><span data-stu-id="a407b-132">Offered calls</span></span>
    
- <span data-ttu-id="a407b-133">応答した通話</span><span class="sxs-lookup"><span data-stu-id="a407b-133">Answered calls</span></span>
    
- <span data-ttu-id="a407b-134">転送された通話</span><span class="sxs-lookup"><span data-stu-id="a407b-134">Transferred calls</span></span>
    
## <a name="making-the-best-use-of-the-response-group-call-list-report"></a><span data-ttu-id="a407b-135">応答グループの通話リスト レポートの活用</span><span class="sxs-lookup"><span data-stu-id="a407b-135">Making the Best Use of the Response Group Call List Report</span></span>

<span data-ttu-id="a407b-p109">応答グループの通話リスト レポートでは、表示されるデータを、特定の応答グループ ワークフローに関連する通話のみに限定することができます。そのためには、[ワークフロー URI] ボックスにワークフロー URI (ワークフローの SIP アドレス) を入力する必要があります。ただし、その前に、まず [ワークフロー URI] ボックスを表示する必要があります。応答グループの通話リスト レポートのフィルター オプションを表示するには、レポート ウィンドウの左上の部分にある [パラメーターの表示/非表示] ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="a407b-p109">The Response Group Call List Report allows you to limit the displayed data to calls involving a particular Response Group workflow. To do that, you need to enter the workflow URI (the workflow's SIP address) in the Workflow URI box. Before you can do that, however, you must actually be able to see the Workflow URI box. To display the filtering options for the Response Group Call List Report, click the Show/Hide Parameters button in the upper left-hand portion of the report window.</span></span>
  
<span data-ttu-id="a407b-140">応答グループの通話リストで応答コードまたは診断 ID の上にマウス ポインターを置いてもこれらの指標の情報は表示されません。</span><span class="sxs-lookup"><span data-stu-id="a407b-140">Note that the Response Group Call List does not display information about either the Response code or the Diagnostic ID if you hold the mouse over either of those metrics.</span></span> <span data-ttu-id="a407b-141">詳細については、必要な場合は、応答コード、診断の ID に注意してくださいし、[ビジネス サーバー 2015 の Skype のエラー レポートの一番上](top-failures-report.md)にそれらの値を検索し、可能性があります。</span><span class="sxs-lookup"><span data-stu-id="a407b-141">If you need more information, you might note the Response code and/or Diagnostic ID, and then search for those values in the [Top Failures Report in Skype for Business Server 2015](top-failures-report.md).</span></span>
  
<span data-ttu-id="a407b-142">たとえば、最も多くの通話を受信したワークフローはどれかを調べるには、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="a407b-142">a question like this one: "Which individual workflow received the most calls?", you can do the following:</span></span>
  
1. <span data-ttu-id="a407b-p111">応答グループの使用レポートで、目的の期間を設定し、[受信した通話] 指標をクリックします。応答グループの通話リスト レポートが開きます。</span><span class="sxs-lookup"><span data-stu-id="a407b-p111">On the Response Group Usage Report, set the desired time period and then click the Received Calls metric. That will open the Response Group Call List Report.</span></span>
    
2. <span data-ttu-id="a407b-p112">応答グループの通話リスト レポートに表示されたデータをエクスポートします。たとえば、データを Microsoft Excel 形式でエクスポートして、Excel で CSV (コンマ区切り値) ファイルに変換することができます。</span><span class="sxs-lookup"><span data-stu-id="a407b-p112">Export the data shown on the Response Group Call List Report. For example, you might export the data in Microsoft Excel format, and then use Excel to convert that data to a comma-separated values file.</span></span>
    
3. <span data-ttu-id="a407b-147">Windows PowerShell を使用して分析を実行します。</span><span class="sxs-lookup"><span data-stu-id="a407b-147">Run your analyses using Windows PowerShell.</span></span>
    
<span data-ttu-id="a407b-148">たとえば、C:\Data\Response_Group_Call_List_Report.csv というファイルにデータを保存した場合は、次のコマンドを使用して、レポートに含まれている各ワークフローが受信した通話の合計数を取得できます。</span><span class="sxs-lookup"><span data-stu-id="a407b-148">For example, if you have saved the data to a file named C:\Data\Response_Group_Call_List_Report.csv, you can then use the following command to return the total number of received calls for each workflow listed in the report:</span></span>
  
```
$calls = Import-Csv -Path "C:\ Data\Response_Group_Call_List_Report.csv"
$calls | Group-Object Workflow | Select-Object Count, Name | Sort-Object Count -Descending
```

<span data-ttu-id="a407b-149">次のような情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="a407b-149">That will information similar to this:</span></span>
  
<pre>
Count    Name
-----    ----
  160    Redmond Help Desk
   47    Dublin Help Desk
   31    North America Customer Support
   16    EMEA Customer Support
   14    Employment Opportunities
</pre>

## <a name="filters"></a><span data-ttu-id="a407b-150">フィルター</span><span class="sxs-lookup"><span data-stu-id="a407b-150">Filters</span></span>

<span data-ttu-id="a407b-p113">フィルターは、細かく絞り込んだデータ セットを返したり、返されたデータをさまざまな方法で表示したりする方法として利用できます。次の表に、応答グループの通話リスト レポートで使用できるフィルターを示します。</span><span class="sxs-lookup"><span data-stu-id="a407b-p113">Filters provide a way for you to return a more finely-targeted set of data or to view the returned data in different ways. The following table lists the filters that you can use with the Response Group Call List Report.</span></span>
  
<span data-ttu-id="a407b-153">**応答グループ通話リスト レポートのフィルター**</span><span class="sxs-lookup"><span data-stu-id="a407b-153">**Response Group Call List Report Filters**</span></span>

|<span data-ttu-id="a407b-154">**名**</span><span class="sxs-lookup"><span data-stu-id="a407b-154">**Name**</span></span>|<span data-ttu-id="a407b-155">**説明**</span><span class="sxs-lookup"><span data-stu-id="a407b-155">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="a407b-156">**[開始]**</span><span class="sxs-lookup"><span data-stu-id="a407b-156">**From**</span></span> <br/> |<span data-ttu-id="a407b-p114">時間範囲の開始日と開始時刻。データを時間単位で表示するには、次のように開始日と開始時刻の両方を入力します。</span><span class="sxs-lookup"><span data-stu-id="a407b-p114">Start date/time for the time range. To view data by hours, enter both the start date and time as follows:</span></span>  <br/> <span data-ttu-id="a407b-159">7/7/2015 13:00</span><span class="sxs-lookup"><span data-stu-id="a407b-159">7/7/2015 1:00 PM</span></span>  <br/> <span data-ttu-id="a407b-p115">開始時刻を入力しないと、レポートは自動的に指定日の午前 12:00 に開始します。データを日単位で表示するには、次のように日付のみを入力します。</span><span class="sxs-lookup"><span data-stu-id="a407b-p115">If you do not enter a start time, the report automatically begins at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span>  <br/> <span data-ttu-id="a407b-162">7/7/2015</span><span class="sxs-lookup"><span data-stu-id="a407b-162">7/7/2015</span></span>  <br/> <span data-ttu-id="a407b-163">週単位または月単位で表示するには、表示する週または月の任意の日付を入力します (その週または月の最初の日である必要はありません)。</span><span class="sxs-lookup"><span data-stu-id="a407b-163">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span>  <br/> <span data-ttu-id="a407b-164">7/3/2015</span><span class="sxs-lookup"><span data-stu-id="a407b-164">7/3/2015</span></span>  <br/> <span data-ttu-id="a407b-165">一週間は、日曜日から始まり、土曜日で終わるものとします。</span><span class="sxs-lookup"><span data-stu-id="a407b-165">Weeks always run from Sunday through Saturday.</span></span>  <br/> |
|<span data-ttu-id="a407b-166">**[終了]**</span><span class="sxs-lookup"><span data-stu-id="a407b-166">**To**</span></span> <br/> |<span data-ttu-id="a407b-p116">時間範囲の終了日と終了時刻。データを時間単位で表示するには、次のように終了日と終了時刻の両方を入力します。</span><span class="sxs-lookup"><span data-stu-id="a407b-p116">End date/time for the time range. To view data by hours, enter both the end date and time as follows:</span></span>  <br/> <span data-ttu-id="a407b-169">7/7/2015 13:00</span><span class="sxs-lookup"><span data-stu-id="a407b-169">7/7/2015 1:00 PM</span></span>  <br/> <span data-ttu-id="a407b-p117">終了時刻を入力しないと、レポートは自動的に指定日の午前 12:00 に終了します。データを日単位で表示するには、次のように日付のみを入力します。</span><span class="sxs-lookup"><span data-stu-id="a407b-p117">If you do not enter an end time, the report automatically ends at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span>  <br/> <span data-ttu-id="a407b-172">7/7/2015</span><span class="sxs-lookup"><span data-stu-id="a407b-172">7/7/2015</span></span>  <br/> <span data-ttu-id="a407b-173">週単位または月単位で表示するには、表示する週または月の任意の日付を入力します (その週または月の最初の日である必要はありません)。</span><span class="sxs-lookup"><span data-stu-id="a407b-173">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span>  <br/> <span data-ttu-id="a407b-174">7/3/2015</span><span class="sxs-lookup"><span data-stu-id="a407b-174">7/3/2015</span></span>  <br/> <span data-ttu-id="a407b-175">一週間は、日曜日から始まり、土曜日で終わるものとします。</span><span class="sxs-lookup"><span data-stu-id="a407b-175">Weeks always run from Sunday through Saturday.</span></span>  <br/> |
|<span data-ttu-id="a407b-176">**[ワークフロー URI]**</span><span class="sxs-lookup"><span data-stu-id="a407b-176">**Workflow URI**</span></span> <br/> |<span data-ttu-id="a407b-p118">返されるデータを、指定されている応答グループ ワークフローに制限できます。このフィルターを使用するには、ワークフローの SIP アドレスを入力します。次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="a407b-p118">Enables you to limit the returned data to the specified Response Group workflow. To use this filter, enter the Workflow SIP address. For example:</span></span>  <br/> <span data-ttu-id="a407b-180">sip:helpdesk@litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="a407b-180">sip:helpdesk@litwareinc.com</span></span>  <br/> |
|<span data-ttu-id="a407b-181">**[通話]**</span><span class="sxs-lookup"><span data-stu-id="a407b-181">**Calls**</span></span> <br/> | <span data-ttu-id="a407b-182">次のいずれかの通話の種類を選択できます。</span><span class="sxs-lookup"><span data-stu-id="a407b-182">You can select one of the following call types:</span></span> <br/>  <span data-ttu-id="a407b-183">受信した通話</span><span class="sxs-lookup"><span data-stu-id="a407b-183">Received Calls</span></span> <br/>  <span data-ttu-id="a407b-184">正常な通話</span><span class="sxs-lookup"><span data-stu-id="a407b-184">Successful Calls</span></span> <br/>  <span data-ttu-id="a407b-185">提供された通話</span><span class="sxs-lookup"><span data-stu-id="a407b-185">Offered Calls</span></span> <br/>  <span data-ttu-id="a407b-186">応答した通話</span><span class="sxs-lookup"><span data-stu-id="a407b-186">Answered Calls</span></span> <br/>  <span data-ttu-id="a407b-187">転送された通話</span><span class="sxs-lookup"><span data-stu-id="a407b-187">Transferred Calls</span></span> <br/> |
   
## <a name="metrics"></a><span data-ttu-id="a407b-188">指標</span><span class="sxs-lookup"><span data-stu-id="a407b-188">Metrics</span></span>

<span data-ttu-id="a407b-189">次の表に、応答グループの通話リスト レポートで、応答グループ アプリケーションが受信した通話ごとに提供される情報を示します。</span><span class="sxs-lookup"><span data-stu-id="a407b-189">The following table lists the information provided in the Response Group Call List Report for each call received by the Response Group application.</span></span>
  
<span data-ttu-id="a407b-190">**応答グループ通話リスト レポートの判断基準**</span><span class="sxs-lookup"><span data-stu-id="a407b-190">**Response Group Call List Report Metrics**</span></span>

|<span data-ttu-id="a407b-191">**名**</span><span class="sxs-lookup"><span data-stu-id="a407b-191">**Name**</span></span>|<span data-ttu-id="a407b-192">**この項目を並べ替えることができますか。**</span><span class="sxs-lookup"><span data-stu-id="a407b-192">**Can you sort on this item?**</span></span>|<span data-ttu-id="a407b-193">**説明**</span><span class="sxs-lookup"><span data-stu-id="a407b-193">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="a407b-194">**[発信者]**</span><span class="sxs-lookup"><span data-stu-id="a407b-194">**Caller**</span></span> <br/> |<span data-ttu-id="a407b-195">不可</span><span class="sxs-lookup"><span data-stu-id="a407b-195">No</span></span>  <br/> |<span data-ttu-id="a407b-196">発信者の SIP アドレス。</span><span class="sxs-lookup"><span data-stu-id="a407b-196">SIP address of the caller.</span></span>  <br/> |
|<span data-ttu-id="a407b-197">**[ワークフロー]**</span><span class="sxs-lookup"><span data-stu-id="a407b-197">**Workflow**</span></span> <br/> |<span data-ttu-id="a407b-198">不可</span><span class="sxs-lookup"><span data-stu-id="a407b-198">No</span></span>  <br/> |<span data-ttu-id="a407b-199">応答グループ ワークフローの SIP アドレス。</span><span class="sxs-lookup"><span data-stu-id="a407b-199">SIP address of the Response Group workflow.</span></span>  <br/> |
|<span data-ttu-id="a407b-200">**[開始時刻]**</span><span class="sxs-lookup"><span data-stu-id="a407b-200">**Start time**</span></span> <br/> |<span data-ttu-id="a407b-201">不可</span><span class="sxs-lookup"><span data-stu-id="a407b-201">No</span></span>  <br/> |<span data-ttu-id="a407b-202">通話が開始された日時。</span><span class="sxs-lookup"><span data-stu-id="a407b-202">Date and time that the call started.</span></span>  <br/> |
|<span data-ttu-id="a407b-203">**[終了時刻]**</span><span class="sxs-lookup"><span data-stu-id="a407b-203">**End time**</span></span> <br/> |<span data-ttu-id="a407b-204">不可</span><span class="sxs-lookup"><span data-stu-id="a407b-204">No</span></span>  <br/> |<span data-ttu-id="a407b-205">通話が終了した日時。</span><span class="sxs-lookup"><span data-stu-id="a407b-205">Date and time that the call ended.</span></span>  <br/> |
|<span data-ttu-id="a407b-206">**[応答コード]**</span><span class="sxs-lookup"><span data-stu-id="a407b-206">**Response code**</span></span> <br/> |<span data-ttu-id="a407b-207">不可</span><span class="sxs-lookup"><span data-stu-id="a407b-207">No</span></span>  <br/> |<span data-ttu-id="a407b-208">セッションが失敗したときに送信された SIP 応答コード。</span><span class="sxs-lookup"><span data-stu-id="a407b-208">SIP response code sent when the session failed.</span></span>  <br/> |
|<span data-ttu-id="a407b-209">**[診断 ID]**</span><span class="sxs-lookup"><span data-stu-id="a407b-209">**Diagnostic ID**</span></span> <br/> |<span data-ttu-id="a407b-210">不可</span><span class="sxs-lookup"><span data-stu-id="a407b-210">No</span></span>  <br/> |<span data-ttu-id="a407b-211">SIP メッセージに (ms-diagnostics ヘッダーの形で) 添付された一意の識別子。多くの場合、この情報はトラブルシューティングに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="a407b-211">Unique identifier (in the form of an ms-diagnostics header) attached to a SIP message that often provides information useful in troubleshooting errors.</span></span>  <br/> |
   

