---
title: 'Lync Server 2013: 応答グループの通話リストレポート'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Response Group Call List Report
ms:assetid: a2d3e08b-511b-4507-abba-8ff71aa27c8e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615443(v=OCS.15)
ms:contentKeyID: 48184954
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9e02c5493f8582d401ea02df3f94cd2df57e0093
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/21/2020
ms.locfileid: "42214893"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="response-group-call-list-report-in-lync-server-2013"></a><span data-ttu-id="7eb0e-102">Lync Server 2013 の応答グループの通話リストレポート</span><span class="sxs-lookup"><span data-stu-id="7eb0e-102">Response Group Call List Report in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7eb0e-103">_**トピックの最終更新日:** 2013-02-22_</span><span class="sxs-lookup"><span data-stu-id="7eb0e-103">_**Topic Last Modified:** 2013-02-22_</span></span>

<span data-ttu-id="7eb0e-104">応答グループアプリケーションは、Microsoft Lync Server 2013 が、ダイヤルされた番号と、必要に応じて発信者の一連の質問に対する応答に基づいて、電話での通話に応答してルーティングする方法を提供します。</span><span class="sxs-lookup"><span data-stu-id="7eb0e-104">The Response Group application provides a way for Microsoft Lync Server 2013 to answer and route phone calls based on the number that was dialed and, optionally, on the caller's responses to a series of questions.</span></span> <span data-ttu-id="7eb0e-105">通常、応答グループの通話は個々のユーザーにルーティングされませんが、代わりにエージェントグループと呼ばれるユーザーのチームにルーティングされます。</span><span class="sxs-lookup"><span data-stu-id="7eb0e-105">Typically, Response Group calls are not routed to an individual person but, instead, are routed to a team of people referred to as an agent group.</span></span> <span data-ttu-id="7eb0e-106">たとえば、ユーザーがヘルプデスクの電話番号を呼び出すと、Lync Server 2013 は、その通話を最初に利用可能なヘルプデスクエージェントに自動的にルーティングすることができます。</span><span class="sxs-lookup"><span data-stu-id="7eb0e-106">For example, if someone calls the phone number for your help desk, Lync Server 2013 can automatically route that call to the first available help desk agent.</span></span> <span data-ttu-id="7eb0e-107">または、Lync Server は一連の質問をすることができます (ハードウェアに問題がある場合は1を押します)。</span><span class="sxs-lookup"><span data-stu-id="7eb0e-107">Alternatively, Lync Server could ask a series of questions ("Press 1 if you are having hardware problems.</span></span> <span data-ttu-id="7eb0e-108">ソフトウェアに問題がある場合は、2を押します。</span><span class="sxs-lookup"><span data-stu-id="7eb0e-108">Press 2 if you are having software problems.</span></span> <span data-ttu-id="7eb0e-109">ネットワークの問題が発生している場合は、3を押します。)その後、質問に対する回答に基づいて、最適なヘルプデスクエージェントに通話をルーティングします。</span><span class="sxs-lookup"><span data-stu-id="7eb0e-109">Press 3 if you are having network problems.") and then route the call to the most appropriate help desk agent based on the answer to those questions.</span></span>

<span data-ttu-id="7eb0e-p102">応答グループの通話リスト レポートは、特定の期間に特定の種類の通話に対して行われた通話のコレクションです。応答グループの使用レポート (応答グループの通話リスト レポートを開くには先にこのレポートを開く必要があります) では、次の種類の通話が認識されます。</span><span class="sxs-lookup"><span data-stu-id="7eb0e-p102">The Response Group Call List Report represents a collection of calls made for a specified period of time and for a specified type of call. The Response Group Usage Report (which must be opened first before you can open the Response Group Call List Report) recognizes the following call types:</span></span>

  - <span data-ttu-id="7eb0e-p103">**受信した通話**。応答グループ アプリケーションのすべてのインスタンスで受信した通話の合計数。</span><span class="sxs-lookup"><span data-stu-id="7eb0e-p103">**Received calls**. Total number of calls received by all instances of the Response Group application.</span></span>

  - <span data-ttu-id="7eb0e-114">**正常な通話**。</span><span class="sxs-lookup"><span data-stu-id="7eb0e-114">**Successful calls**.</span></span> <span data-ttu-id="7eb0e-115">応答グループアプリケーションによって処理された通話の合計数。</span><span class="sxs-lookup"><span data-stu-id="7eb0e-115">Total number of calls that were picked up by the Response Group application.</span></span>

  - <span data-ttu-id="7eb0e-p105">**提供された通話**。応答グループ エージェントによって転送された通話の合計数。</span><span class="sxs-lookup"><span data-stu-id="7eb0e-p105">**Offered calls**. Total number of calls that were transferred to a Response Group agent.</span></span>

  - <span data-ttu-id="7eb0e-p106">**応答した通話**。応答グループ エージェントが実際に応答した通話の合計数。</span><span class="sxs-lookup"><span data-stu-id="7eb0e-p106">**Answered calls**. Total number of calls that were actually answered by a Response Group agent.</span></span>

  - <span data-ttu-id="7eb0e-120">破棄された通話のパーセンテージ。</span><span class="sxs-lookup"><span data-stu-id="7eb0e-120">Percentage of abandoned calls.</span></span> <span data-ttu-id="7eb0e-121">応答グループ アプリケーションによって受信されたが、エージェントが応答しなかった通話のパーセンテージ。</span><span class="sxs-lookup"><span data-stu-id="7eb0e-121">Percentage of calls that were received by the Response Group application but were never answered by an agent.</span></span> <span data-ttu-id="7eb0e-122">この値は、受信した通話数から応答した通話数を引いた値を受信した通話数で割って計算されます。</span><span class="sxs-lookup"><span data-stu-id="7eb0e-122">This value is calculated by subtracting the Answered calls from the Received calls, and then dividing that value by the number of Received calls.</span></span> <span data-ttu-id="7eb0e-123">たとえば、受信した通話数が 10 件、応答した通話数が 7 件の場合、10 から 7 を引いて 3 件が応答のない通話数として残ります。</span><span class="sxs-lookup"><span data-stu-id="7eb0e-123">For example, if you received 10 calls and 7 were answered, you would subtract 7 from 10, leaving 3 unanswered calls.</span></span> <span data-ttu-id="7eb0e-124">この値を 10 で割ると、破棄された通話のパーセンテージは 30% になります。</span><span class="sxs-lookup"><span data-stu-id="7eb0e-124">That value would then be divided by 10, giving you an abandoned call percentage of 30%.</span></span>

  - <span data-ttu-id="7eb0e-p108">**転送された通話**。キューのタイムアウトまたはキューのオーバーフローによって転送された、応答グループの通話の合計数。</span><span class="sxs-lookup"><span data-stu-id="7eb0e-p108">**Transferred calls**. Total number of Response Group calls that were transferred because of a queue timeout or queue overflow.</span></span>

<div>

## <a name="accessing-the-response-group-call-list-report"></a><span data-ttu-id="7eb0e-127">応答グループの通話リスト レポートへのアクセス</span><span class="sxs-lookup"><span data-stu-id="7eb0e-127">Accessing the Response Group Call List Report</span></span>

<span data-ttu-id="7eb0e-128">応答グループの通話リストレポートにアクセスするには、 [Lync Server 2013 の応答グループの使用状況レポート](lync-server-2013-response-group-usage-report.md)にある次のいずれかの指標をクリックする必要があります。</span><span class="sxs-lookup"><span data-stu-id="7eb0e-128">The Response Group Call List Report can only be accessed by clicking one of the following metrics found on the [Response Group Usage Report in Lync Server 2013](lync-server-2013-response-group-usage-report.md):</span></span>

  - <span data-ttu-id="7eb0e-129">[受信した通話]</span><span class="sxs-lookup"><span data-stu-id="7eb0e-129">Received calls</span></span>

  - <span data-ttu-id="7eb0e-130">[正常な通話]</span><span class="sxs-lookup"><span data-stu-id="7eb0e-130">Successful calls</span></span>

  - <span data-ttu-id="7eb0e-131">[提供された通話]</span><span class="sxs-lookup"><span data-stu-id="7eb0e-131">Offered calls</span></span>

  - <span data-ttu-id="7eb0e-132">[応答した通話]</span><span class="sxs-lookup"><span data-stu-id="7eb0e-132">Answered calls</span></span>

  - <span data-ttu-id="7eb0e-133">転送された通話</span><span class="sxs-lookup"><span data-stu-id="7eb0e-133">Transferred calls</span></span>

</div>

<div>

## <a name="making-the-best-use-of-the-response-group-call-list-report"></a><span data-ttu-id="7eb0e-134">応答グループの通話リスト レポートの活用</span><span class="sxs-lookup"><span data-stu-id="7eb0e-134">Making the Best Use of the Response Group Call List Report</span></span>

<span data-ttu-id="7eb0e-p109">応答グループの通話リスト レポートでは、表示されるデータを、特定の応答グループ ワークフローに関連する通話のみに限定することができます。そのためには、[ワークフロー URI] ボックスにワークフロー URI (ワークフローの SIP アドレス) を入力する必要があります。ただし、その前に、まず [ワークフロー URI] ボックスを表示する必要があります。応答グループの通話リスト レポートのフィルター オプションを表示するには、レポート ウィンドウの左上の部分にある [パラメーターの表示/非表示] ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="7eb0e-p109">The Response Group Call List Report allows you to limit the displayed data to calls involving a particular Response Group workflow. To do that, you need to enter the workflow URI (the workflow's SIP address) in the Workflow URI box. Before you can do that, however, you must actually be able to see the Workflow URI box. To display the filtering options for the Response Group Call List Report, click the Show/Hide Parameters button in the upper left-hand portion of the report window.</span></span>

<span data-ttu-id="7eb0e-139">応答グループの通話リストで応答コードまたは診断 ID の上にマウス ポインターを置いてもこれらの指標の情報は表示されません。</span><span class="sxs-lookup"><span data-stu-id="7eb0e-139">Note that the Response Group Call List does not display information about either the Response code or the Diagnostic ID if you hold the mouse over either of those metrics.</span></span> <span data-ttu-id="7eb0e-140">詳細が必要な場合は、応答コードや診断 ID を書き留めておいて、 [Lync Server 2013 のトップエラーレポート](lync-server-2013-top-failures-report.md)でこれらの値を検索することがあります。</span><span class="sxs-lookup"><span data-stu-id="7eb0e-140">If you need more information, you might note the Response code and/or Diagnostic ID, and then search for those values in the [Top Failures Report in Lync Server 2013](lync-server-2013-top-failures-report.md).</span></span>

<span data-ttu-id="7eb0e-141">たとえば、最も多くの通話を受信したワークフローはどれかを調べるには、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="7eb0e-141">a question like this one: "Which individual workflow received the most calls?", you can do the following:</span></span>

1.  <span data-ttu-id="7eb0e-p111">応答グループの使用レポートで、目的の期間を設定し、[受信した通話] 指標をクリックします。応答グループの通話リスト レポートが開きます。</span><span class="sxs-lookup"><span data-stu-id="7eb0e-p111">On the Response Group Usage Report, set the desired time period and then click the Received Calls metric. That will open the Response Group Call List Report.</span></span>

2.  <span data-ttu-id="7eb0e-p112">応答グループの通話リスト レポートに表示されたデータをエクスポートします。たとえば、データを Microsoft Excel 形式でエクスポートして、Excel で CSV (コンマ区切り値) ファイルに変換することができます。</span><span class="sxs-lookup"><span data-stu-id="7eb0e-p112">Export the data shown on the Response Group Call List Report. For example, you might export the data in Microsoft Excel format, and then use Excel to convert that data to a comma-separated values file.</span></span>

3.  <span data-ttu-id="7eb0e-146">Windows PowerShell を使用して分析を実行します。</span><span class="sxs-lookup"><span data-stu-id="7eb0e-146">Run your analyses using Windows PowerShell.</span></span>

<span data-ttu-id="7eb0e-147">たとえば、データを C\\: データ\\応答\_グループ\_の呼び出し\_リスト\_.csv に保存した場合、次のコマンドを使用して、レポートに一覧表示されている各ワークフローの受信呼び出しの合計数を取得できます。</span><span class="sxs-lookup"><span data-stu-id="7eb0e-147">For example, if you have saved the data to a file named C:\\Data\\Response\_Group\_Call\_List\_Report.csv, you can then use the following command to return the total number of received calls for each workflow listed in the report:</span></span>

    $calls = Import-Csv -Path "C:\ Data\Response_Group_Call_List_Report.csv"
    $calls | Group-Object Workflow | Select-Object Count, Name | Sort-Object Count -Descending

<span data-ttu-id="7eb0e-148">次のような情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="7eb0e-148">That will information similar to this:</span></span>

    Count    Name
    -----    ----
      160    Redmond Help Desk
       47    Dublin Help Desk
       31    North America Customer Support
       16    EMEA Customer Support
       14    Employment Opportunities

</div>

<div>

## <a name="filters"></a><span data-ttu-id="7eb0e-149">フィルター</span><span class="sxs-lookup"><span data-stu-id="7eb0e-149">Filters</span></span>

<span data-ttu-id="7eb0e-p113">フィルターは、細かく絞り込んだデータ セットを返したり、返されたデータをさまざま方法で表示したりする方法として利用できます。次の表に、応答グループの通話リスト レポートで使用できるフィルターを示します。</span><span class="sxs-lookup"><span data-stu-id="7eb0e-p113">Filters provide a way for you to return a more finely-targeted set of data or to view the returned data in different ways. The following table lists the filters that you can use with the Response Group Call List Report.</span></span>

### <a name="response-group-call-list-report-filters"></a><span data-ttu-id="7eb0e-152">応答グループの通話リスト レポートのフィルター</span><span class="sxs-lookup"><span data-stu-id="7eb0e-152">Response Group Call List Report Filters</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="7eb0e-153">名前</span><span class="sxs-lookup"><span data-stu-id="7eb0e-153">Name</span></span></th>
<th><span data-ttu-id="7eb0e-154">説明</span><span class="sxs-lookup"><span data-stu-id="7eb0e-154">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="7eb0e-155"><strong>From</strong></span><span class="sxs-lookup"><span data-stu-id="7eb0e-155"><strong>From</strong></span></span></p></td>
<td><p><span data-ttu-id="7eb0e-p114">時間範囲の開始日と開始時刻。データを時間単位で表示するには、次のように開始日と開始時刻の両方を入力します。</span><span class="sxs-lookup"><span data-stu-id="7eb0e-p114">Start date/time for the time range. To view data by hours, enter both the start date and time as follows:</span></span></p>
<p><span data-ttu-id="7eb0e-158">7/7/2012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="7eb0e-158">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="7eb0e-p115">開始時刻を入力しないと、レポートは自動的に指定日の午前 12:00 に開始します。データを日単位で表示するには、次のように日付のみを入力します。</span><span class="sxs-lookup"><span data-stu-id="7eb0e-p115">If you do not enter a start time, the report automatically begins at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="7eb0e-161">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="7eb0e-161">7/7/2012</span></span></p>
<p><span data-ttu-id="7eb0e-162">週単位または月単位で表示するには、表示する週または月の任意の日付を入力します (その週または月の最初の日である必要はありません)。</span><span class="sxs-lookup"><span data-stu-id="7eb0e-162">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="7eb0e-163">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="7eb0e-163">7/3/2012</span></span></p>
<p><span data-ttu-id="7eb0e-164">一週間は、日曜日から始まり、土曜日で終わるものとします。</span><span class="sxs-lookup"><span data-stu-id="7eb0e-164">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7eb0e-165"><strong>To</strong></span><span class="sxs-lookup"><span data-stu-id="7eb0e-165"><strong>To</strong></span></span></p></td>
<td><p><span data-ttu-id="7eb0e-p116">時間範囲の終了日と終了時刻。データを時間単位で表示するには、次のように終了日と終了時刻の両方を入力します。</span><span class="sxs-lookup"><span data-stu-id="7eb0e-p116">End date/time for the time range. To view data by hours, enter both the end date and time as follows:</span></span></p>
<p><span data-ttu-id="7eb0e-168">7/7/2012 13:00</span><span class="sxs-lookup"><span data-stu-id="7eb0e-168">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="7eb0e-p117">終了時刻を入力しないと、レポートは自動的に指定日の午前 12:00 に終了します。データを日単位で表示するには、次のように日付のみを入力します。</span><span class="sxs-lookup"><span data-stu-id="7eb0e-p117">If you do not enter an end time, the report automatically ends at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="7eb0e-171">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="7eb0e-171">7/7/2012</span></span></p>
<p><span data-ttu-id="7eb0e-172">週単位または月単位で表示するには、表示する週または月の任意の日付を入力します (その週または月の最初の日である必要はありません)。</span><span class="sxs-lookup"><span data-stu-id="7eb0e-172">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="7eb0e-173">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="7eb0e-173">7/3/2012</span></span></p>
<p><span data-ttu-id="7eb0e-174">週は、常に日曜日から土曜日までです。</span><span class="sxs-lookup"><span data-stu-id="7eb0e-174">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7eb0e-175">[<strong>ワークフロー URI</strong>]</span><span class="sxs-lookup"><span data-stu-id="7eb0e-175"><strong>Workflow URI</strong></span></span></p></td>
<td><p><span data-ttu-id="7eb0e-p118">返されるデータを、指定されている応答グループ ワークフローに制限できます。このフィルターを使用するには、ワークフローの SIP アドレスを入力します。次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="7eb0e-p118">Enables you to limit the returned data to the specified Response Group workflow. To use this filter, enter the Workflow SIP address. For example:</span></span></p>
<p><span data-ttu-id="7eb0e-179">sip:helpdesk@litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="7eb0e-179">sip:helpdesk@litwareinc.com</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7eb0e-180"><strong>通話</strong></span><span class="sxs-lookup"><span data-stu-id="7eb0e-180"><strong>Calls</strong></span></span></p></td>
<td><p><span data-ttu-id="7eb0e-181">次のいずれかの通話の種類を選択できます。</span><span class="sxs-lookup"><span data-stu-id="7eb0e-181">You can select one of the following call types:</span></span></p>
<ul>
<li><p><span data-ttu-id="7eb0e-182">受信した通話</span><span class="sxs-lookup"><span data-stu-id="7eb0e-182">Received Calls</span></span></p></li>
<li><p><span data-ttu-id="7eb0e-183">正常な通話</span><span class="sxs-lookup"><span data-stu-id="7eb0e-183">Successful Calls</span></span></p></li>
<li><p><span data-ttu-id="7eb0e-184">提供された通話</span><span class="sxs-lookup"><span data-stu-id="7eb0e-184">Offered Calls</span></span></p></li>
<li><p><span data-ttu-id="7eb0e-185">応答した通話</span><span class="sxs-lookup"><span data-stu-id="7eb0e-185">Answered Calls</span></span></p></li>
<li><p><span data-ttu-id="7eb0e-186">転送された通話</span><span class="sxs-lookup"><span data-stu-id="7eb0e-186">Transferred Calls</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics"></a><span data-ttu-id="7eb0e-187">指標</span><span class="sxs-lookup"><span data-stu-id="7eb0e-187">Metrics</span></span>

<span data-ttu-id="7eb0e-188">次の表に、応答グループの通話リスト レポートで、応答グループ アプリケーションが受信した通話ごとに提供される情報を示します。</span><span class="sxs-lookup"><span data-stu-id="7eb0e-188">The following table lists the information provided in the Response Group Call List Report for each call received by the Response Group application.</span></span>

### <a name="response-group-call-list-report-metrics"></a><span data-ttu-id="7eb0e-189">応答グループの通話リスト レポートの指標</span><span class="sxs-lookup"><span data-stu-id="7eb0e-189">Response Group Call List Report Metrics</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="7eb0e-190">名前</span><span class="sxs-lookup"><span data-stu-id="7eb0e-190">Name</span></span></th>
<th><span data-ttu-id="7eb0e-191">この項目での並べ替え</span><span class="sxs-lookup"><span data-stu-id="7eb0e-191">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="7eb0e-192">説明</span><span class="sxs-lookup"><span data-stu-id="7eb0e-192">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="7eb0e-193"><strong>Caller</strong></span><span class="sxs-lookup"><span data-stu-id="7eb0e-193"><strong>Caller</strong></span></span></p></td>
<td><p><span data-ttu-id="7eb0e-194">いいえ</span><span class="sxs-lookup"><span data-stu-id="7eb0e-194">No</span></span></p></td>
<td><p><span data-ttu-id="7eb0e-195">発信者の SIP アドレス。</span><span class="sxs-lookup"><span data-stu-id="7eb0e-195">SIP address of the caller.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7eb0e-196"><strong>ワークフロー</strong></span><span class="sxs-lookup"><span data-stu-id="7eb0e-196"><strong>Workflow</strong></span></span></p></td>
<td><p><span data-ttu-id="7eb0e-197">いいえ</span><span class="sxs-lookup"><span data-stu-id="7eb0e-197">No</span></span></p></td>
<td><p><span data-ttu-id="7eb0e-198">応答グループ ワークフローの SIP アドレス。</span><span class="sxs-lookup"><span data-stu-id="7eb0e-198">SIP address of the Response Group workflow.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7eb0e-199">[<strong>開始時刻</strong>]</span><span class="sxs-lookup"><span data-stu-id="7eb0e-199"><strong>Start time</strong></span></span></p></td>
<td><p><span data-ttu-id="7eb0e-200">いいえ</span><span class="sxs-lookup"><span data-stu-id="7eb0e-200">No</span></span></p></td>
<td><p><span data-ttu-id="7eb0e-201">通話が開始された日時。</span><span class="sxs-lookup"><span data-stu-id="7eb0e-201">Date and time that the call started.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7eb0e-202">[<strong>終了時刻</strong>]</span><span class="sxs-lookup"><span data-stu-id="7eb0e-202"><strong>End time</strong></span></span></p></td>
<td><p><span data-ttu-id="7eb0e-203">いいえ</span><span class="sxs-lookup"><span data-stu-id="7eb0e-203">No</span></span></p></td>
<td><p><span data-ttu-id="7eb0e-204">通話が終了した日時。</span><span class="sxs-lookup"><span data-stu-id="7eb0e-204">Date and time that the call ended.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7eb0e-205">[<strong>応答コード</strong>]</span><span class="sxs-lookup"><span data-stu-id="7eb0e-205"><strong>Response code</strong></span></span></p></td>
<td><p><span data-ttu-id="7eb0e-206">いいえ</span><span class="sxs-lookup"><span data-stu-id="7eb0e-206">No</span></span></p></td>
<td><p><span data-ttu-id="7eb0e-207">セッションが失敗したときに送信された SIP 応答コード。</span><span class="sxs-lookup"><span data-stu-id="7eb0e-207">SIP response code sent when the session failed.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7eb0e-208">[<strong>診断 ID</strong>]</span><span class="sxs-lookup"><span data-stu-id="7eb0e-208"><strong>Diagnostic ID</strong></span></span></p></td>
<td><p><span data-ttu-id="7eb0e-209">いいえ</span><span class="sxs-lookup"><span data-stu-id="7eb0e-209">No</span></span></p></td>
<td><p><span data-ttu-id="7eb0e-210">SIP メッセージに (ms-diagnostics ヘッダーの形で) 添付された一意の識別子。多くの場合、この情報はトラブルシューティングに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="7eb0e-210">Unique identifier (in the form of an ms-diagnostics header) attached to a SIP message that often provides information useful in troubleshooting errors.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

