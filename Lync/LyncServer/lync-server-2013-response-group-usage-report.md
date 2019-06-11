---
title: 'Lync Server 2013: 応答グループの使用状況レポート'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Response Group Usage Report
ms:assetid: 3248b320-a552-400a-8485-6891af4eb0f3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558632(v=OCS.15)
ms:contentKeyID: 48183811
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9334fea5bded88b4f2453f46a0848819743766d9
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34823316"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="response-group-usage-report-in-lync-server-2013"></a><span data-ttu-id="36afe-102">Lync Server 2013 の応答グループの使用状況レポート</span><span class="sxs-lookup"><span data-stu-id="36afe-102">Response Group Usage Report in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="36afe-103">_**最終更新日:** 2013-02-22_</span><span class="sxs-lookup"><span data-stu-id="36afe-103">_**Topic Last Modified:** 2013-02-22_</span></span>

<span data-ttu-id="36afe-104">応答グループアプリケーションは、ダイヤルされた番号に基づいて Microsoft Lync Server 2013 が電話に応答し、電話をルーティングするための手段を提供します。また、必要に応じて、発信者が一連の質問に対する回答を送信することもできます。</span><span class="sxs-lookup"><span data-stu-id="36afe-104">The Response Group application provides a way for Microsoft Lync Server 2013 to answer and route phone calls based on the number that was dialed and, optionally, on the caller's responses to a series of questions.</span></span> <span data-ttu-id="36afe-105">通常、応答グループの通話は個々のユーザーにはルーティングされませんが、エージェントグループとして参照されているユーザーのチームにルーティングされます。</span><span class="sxs-lookup"><span data-stu-id="36afe-105">Typically, Response Group calls are not routed to an individual person but, instead, are routed to a team of people referred to as an agent group.</span></span> <span data-ttu-id="36afe-106">たとえば、ヘルプデスクの電話番号を呼び出すユーザーがいる場合、Lync Server 2013 は、利用可能な最初のヘルプデスクエージェントにその通話を自動的にルーティングすることができます。</span><span class="sxs-lookup"><span data-stu-id="36afe-106">For example, if someone calls the phone number for your help desk, Lync Server 2013 can automatically route that call to the first available help desk agent.</span></span> <span data-ttu-id="36afe-107">または、Lync Server で一連の質問を行うこともできます (ハードウェアの問題が発生した場合は1を押します)。</span><span class="sxs-lookup"><span data-stu-id="36afe-107">Alternatively, Lync Server could ask a series of questions ("Press 1 if you are having hardware problems.</span></span> <span data-ttu-id="36afe-108">ソフトウェアに問題がある場合は、2を押します。</span><span class="sxs-lookup"><span data-stu-id="36afe-108">Press 2 if you are having software problems.</span></span> <span data-ttu-id="36afe-109">ネットワークの問題が発生した場合は、3を押します。 ")次に、それらの質問に対する回答に基づいて、最も適切なヘルプデスクエージェントに通話をルーティングします。</span><span class="sxs-lookup"><span data-stu-id="36afe-109">Press 3 if you are having network problems.") and then route the call to the most appropriate help desk agent based on the answer to those questions.</span></span>

<span data-ttu-id="36afe-110">応答グループの使用レポートでは、すべての応答グループ ワークフローが受け取った着信の数の詳細を確認できます。 次に、提供された通話、応答した通話、および破棄された通話のような、より限定されたカテゴリにそれらの通話を分類します。</span><span class="sxs-lookup"><span data-stu-id="36afe-110">The Response Group Usage Report provides a detailed look at the number of phone calls received by all your Response Group workflows, then breaks those calls down into more finite categories such as Offered calls, Answered calls, and Abandoned calls.</span></span>

<span data-ttu-id="36afe-111">応答グループの使用レポートを使用する場合の重要なポイントは、報告された通話の種類の違いを理解することです。</span><span class="sxs-lookup"><span data-stu-id="36afe-111">The key to working with the Response Group Usage Report is to understand the difference between the reported call types:</span></span>

  - <span data-ttu-id="36afe-p102">**受信した通話**。 応答グループ アプリケーションのすべてのインスタンスで受信した通話の合計数。</span><span class="sxs-lookup"><span data-stu-id="36afe-p102">**Received calls**. Total number of calls received by all instances of the Response Group application.</span></span>

  - <span data-ttu-id="36afe-p103">**正常な通話**。 応答グループ アプリケーションによって選択された通話の合計数。</span><span class="sxs-lookup"><span data-stu-id="36afe-p103">**Successful calls**. Total number of calls that were picked up by the Response Group application.</span></span>

  - <span data-ttu-id="36afe-p104">**提供された通話**。 応答グループ エージェントによって転送された通話の合計数。</span><span class="sxs-lookup"><span data-stu-id="36afe-p104">**Offered calls**. Total number of calls that were transferred to a Response Group agent.</span></span>

  - <span data-ttu-id="36afe-p105">**応答した通話**。 応答グループ エージェントが実際に応答した通話の合計数。</span><span class="sxs-lookup"><span data-stu-id="36afe-p105">**Answered calls**. Total number of calls that were actually answered by a Response Group agent.</span></span>

  - <span data-ttu-id="36afe-p106">**破棄された通話のパーセンテージ**。 応答グループ アプリケーションによって受信されたが、エージェントが応答しなかった通話のパーセンテージ。 この値は、受信した通話数から応答した通話数を引いた値を受信した通話数で割って計算されます。 たとえば、受信した通話数が 10 件、応答した通話数が 7 件の場合、10 から 7 を引いて 3 件が応答のない通話数として残ります。 この値を 10 で割ると、破棄された通話のパーセンテージは 30% になります。</span><span class="sxs-lookup"><span data-stu-id="36afe-p106">**Percentage of abandoned calls**. Percentage of calls that were received by the Response Group application but were never answered by an agent. This value is calculated by subtracting the Answered calls from the Received calls, and then dividing that value by the number of Received calls. For example, if you received 10 calls and 7 were answered, you would subtract 7 from 10, leaving 3 unanswered calls. That value would then be divided by 10, giving you an abandoned call percentage of 30%.</span></span>

  - <span data-ttu-id="36afe-p107">**転送された通話**。 キューのタイムアウトまたはキューのオーバーフローによって転送された、応答グループの通話の合計数。</span><span class="sxs-lookup"><span data-stu-id="36afe-p107">**Transferred calls**. Total number of Response Group calls that were transferred because of a queue timeout or queue overflow.</span></span>

<span data-ttu-id="36afe-p108">応答グループの使用レポートを見ていて、これらの通話の種類の定義を思い出せない場合は、通話の種類のラベル上にマウス ポインターを置きます。通話の種類の簡単な説明を含むツール ヒントが表示されます。</span><span class="sxs-lookup"><span data-stu-id="36afe-p108">If you are looking at the Response Group Usage Report and can't remember the definition for any of these call types, simply hold your mouse over the appropriate call type label. A tooltip will appear that offers a brief description of the call type.</span></span>

<span data-ttu-id="36afe-p109">応答グループの使用レポートにより、ワークフロー URI (そのワークフローに関連付けられた SIP アドレス) をフィルター処理できます。しかし、ワークフロー URI は実際にはレポート自体に表示されません。どのワークフローでの着信への応答が最も多く、また、どのワークフローでの転送された着信が最も多いかを知るには、適切な指標をクリックして、その特定の期間の応答グループの通話リスト レポートを開きます。このレポートには、ワークフロー URI が示されます。</span><span class="sxs-lookup"><span data-stu-id="36afe-p109">The Response Group Usage Report allows you to filter on a workflow URI (the SIP address associated with that workflow). However, workflow URIs do not actually appear on the report itself. If you would like to know things such as which workflows are answering the most calls or which workflows are experiencing the most transferred calls, click the appropriate metric to open the Response Group Call List Report for that given time period. That reports does list the workflow URIs.</span></span>

<div>

## <a name="accessing-the-response-group-usage-report"></a><span data-ttu-id="36afe-133">応答グループの使用レポート</span><span class="sxs-lookup"><span data-stu-id="36afe-133">Accessing the Response Group Usage Report</span></span>

<span data-ttu-id="36afe-134">応答グループの使用レポートは、監視レポート ホーム ページからアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="36afe-134">The Response Group Usage Report is accessed from the Monitoring Reports home page.</span></span> <span data-ttu-id="36afe-135">次の指標のいずれかをクリックして、 [Lync Server 2013 の応答グループの通話リストレポート](lync-server-2013-response-group-call-list-report.md)にドリルダウンすることができます。</span><span class="sxs-lookup"><span data-stu-id="36afe-135">You can drill down to the [Response Group Call List Report in Lync Server 2013](lync-server-2013-response-group-call-list-report.md) by clicking any of the following metrics:</span></span>

  - <span data-ttu-id="36afe-136">受信した通話</span><span class="sxs-lookup"><span data-stu-id="36afe-136">Received calls</span></span>

  - <span data-ttu-id="36afe-137">正常な通話</span><span class="sxs-lookup"><span data-stu-id="36afe-137">Successful calls</span></span>

  - <span data-ttu-id="36afe-138">提供された通話</span><span class="sxs-lookup"><span data-stu-id="36afe-138">Offered calls</span></span>

  - <span data-ttu-id="36afe-139">応答した通話</span><span class="sxs-lookup"><span data-stu-id="36afe-139">Answered calls</span></span>

  - <span data-ttu-id="36afe-140">転送された通話</span><span class="sxs-lookup"><span data-stu-id="36afe-140">Transferred calls</span></span>

</div>

<div>

## <a name="making-the-best-use-of-the-response-group-usage-report"></a><span data-ttu-id="36afe-141">応答グループの使用レポートの活用</span><span class="sxs-lookup"><span data-stu-id="36afe-141">Making the Best Use of the Response Group Usage Report</span></span>

<span data-ttu-id="36afe-142">あまり知られていない応答グループの使用レポートの便利な活用法があります。それは、単一の応答グループ ワークフローの利用状況の情報を取得する機能です。</span><span class="sxs-lookup"><span data-stu-id="36afe-142">One of the more interesting uses of the Response Group Usage Report might not be readily apparent: the ability to retrieve usage information for a single Response Group workflow.</span></span>

<div>


> [!WARNING]  
> <span data-ttu-id="36afe-143">応答グループのワークフローは基本的に、ユーザーが特定の電話番号にダイヤルしたときに Lync Server が何を実行するかを決定する一連の手順です。</span><span class="sxs-lookup"><span data-stu-id="36afe-143">A Response Group workflow is basically a set of instructions that determines what Lync Server does when a user dials a particular phone number.</span></span> <span data-ttu-id="36afe-144">このため、各ワークフローは電話番号と一意に関連付けられています。</span><span class="sxs-lookup"><span data-stu-id="36afe-144">To that end, each workflow is uniquely associated with a phone number.</span></span> <span data-ttu-id="36afe-145">この番号に電話がかかると、ワークフローによってその処理方法が決定されます。</span><span class="sxs-lookup"><span data-stu-id="36afe-145">When someone calls that number, the workflow determines how the call will be handled.</span></span> <span data-ttu-id="36afe-146">たとえば、この通話を一連の対話型音声応答 (IVR) の質問に転送して、発信者に追加情報を入力するように案内します ("ハードウェア サポートについては 1 を、ソフトウェア サポートについては 2 を押してください" など)。</span><span class="sxs-lookup"><span data-stu-id="36afe-146">For example, the workflow might cause the call to be routed to a series of interactive voice response (IVR) questions that prompt the caller to enter additional information ("Press 1 for hardware support.</span></span> <span data-ttu-id="36afe-147">または、通話をキューに入れて、エージェントがその通話に応答できるようになるまで発信者を保留します。</span><span class="sxs-lookup"><span data-stu-id="36afe-147">Press 2 for software support.").</span></span> <span data-ttu-id="36afe-148">通話に応答するエージェントが対応できるかどうかも、ワークフローによって決定されます。</span><span class="sxs-lookup"><span data-stu-id="36afe-148">Alternatively, the workflow might cause the call to be placed in a queue , with the caller put on hold until an agent is available to answer the call.</span></span> <span data-ttu-id="36afe-149">つまり、ワークフローを使用して、営業時間 (エージェントが通話に応答できる曜日と時間帯) と休日 (通話に応答できるエージェントがいない日) の両方を構成します。</span><span class="sxs-lookup"><span data-stu-id="36afe-149">The availability of agents to answer calls is also dictated by the workflow: workflows are used to configure both business hours (the days of the week and the times of day when agents are available to answer calls) and holidays (days when no agents are available to answer calls).</span></span> <span data-ttu-id="36afe-150">応答グループ アプリケーションに属する電話番号をダイヤルすると、実質的に応答グループ ワークフローを常に呼び出すことになります。</span><span class="sxs-lookup"><span data-stu-id="36afe-150">Any time you dial a phone number that belongs to the Response Group application you are essentially calling a Response Group workflow.</span></span>



</div>

<span data-ttu-id="36afe-p112">ワークフロー URI は応答グループの使用レポートには表示されませんが、場合によっては非常に便利な、単一のワークフローの使用統計を表示できます。たとえば、最近、新しい広告キャンペーンを開始して、その製品に関する問い合わせの状況を知りたいとします。応答グループ ワークフローに、広告キャンペーンに含めた電話番号を関連付けると、問い合わせがあった場合は、その人数を簡単に確認できます。</span><span class="sxs-lookup"><span data-stu-id="36afe-p112">Although workflow URIs do not appear in the Response Group Usage Report, it's still possible to view the usage statistics for a single workflow, something that is often extremely useful. For example, suppose you recently unveiled a new ad campaign and are curious to know whether people are calling in to ask about that product. If you have associated a Response Group workflow with the phone number given in the ad campaign, you can easily check to see how many people (if any) are calling that number.</span></span>

<span data-ttu-id="36afe-154">また同様の手法を使用して、内部ヘルプ デスクまたはカスタマー サービス部門で対応された通話の数を測定することもできます。</span><span class="sxs-lookup"><span data-stu-id="36afe-154">You might also use a similar approach to gauge the number of calls being handled by your internal help desk or your customer service department.</span></span>

<span data-ttu-id="36afe-155">特定のワークフローの使用統計を確認するには、ワークフロー URI ボックスでワークフロー URI を入力します。</span><span class="sxs-lookup"><span data-stu-id="36afe-155">To review usage statistics for a particular workflow, enter the workflow URI in the Workflow URI box.</span></span> <span data-ttu-id="36afe-156">前述のように、ワークフロー URI (ワークフローに関連付けられた SIP アドレス) はレポートに表示されません。</span><span class="sxs-lookup"><span data-stu-id="36afe-156">Of course, as noted, workflow URIs (the SIP address associated with a workflow) do not appear on the report.</span></span> <span data-ttu-id="36afe-157">つまり、ワークフローの URI を確認するには他の方法が必要です。</span><span class="sxs-lookup"><span data-stu-id="36afe-157">That means you need to find some other way to determine the URI of a workflow.</span></span> <span data-ttu-id="36afe-158">そのための方法の1つとして、Windows PowerShell と Lync Server 管理シェルを使用する方法があります。</span><span class="sxs-lookup"><span data-stu-id="36afe-158">One way to do this is to use Windows PowerShell and the Lync Server Management Shell.</span></span> <span data-ttu-id="36afe-159">たとえば、次のコマンドはすべての応答グループ ワークフローの URI を戻します。</span><span class="sxs-lookup"><span data-stu-id="36afe-159">For example, this command returns the URIs for all your Response Group workflows:</span></span>

    Get-CsRgsWorkflow | Select-Object Name, PrimaryUri

<span data-ttu-id="36afe-160">この結果、次のようなデータが戻されます。</span><span class="sxs-lookup"><span data-stu-id="36afe-160">That will return data similar to this:</span></span>

    Name                            PrimaryUri
    ----                            ----------
    Customer Support                sip:support@litwareinc.com
    Help Desk                       sip:helpdesk@litwareinc.com
    New Ad Campaign                 sip:newads@litwareinc.com

<span data-ttu-id="36afe-161">このコマンドは、"New Ad Campaign" という名前の単一のワークフローについての情報を戻します。</span><span class="sxs-lookup"><span data-stu-id="36afe-161">This command returns information for a single workflow, the one with the name New Ad Campaign:</span></span>

    Get-CsRgsWorkflow -Name "New Ad Campaign" | Select-Object Name, PrimaryUri

</div>

<div>

## <a name="filters"></a><span data-ttu-id="36afe-162">フィルター</span><span class="sxs-lookup"><span data-stu-id="36afe-162">Filters</span></span>

<span data-ttu-id="36afe-p114">フィルターは、必要なデータのみに絞り込んだデータ セットを取得したり、取得したデータを別の方法で表示したりする方法として利用できます。たとえば、応答グループの使用レポートを使用すると、すべての応答グループのワークフローのデータを表示したり、個々のワークフローのデータを表示したりできます。データをグループ化する方法を選択することもできます。この場合、使用状況は、時間単位、日単位、週単位、または月単位でグループ化されます。</span><span class="sxs-lookup"><span data-stu-id="36afe-p114">Filters provide a way for you to return a more finely-targeted set of data or to view the returned data in different ways. For example, the Response Group Usage Report enables you to view data for all your Response Group workflows or to view data for an individual workflow. You can also choose how data should be grouped. In this case, usages are grouped by hour, day, week, or month.</span></span>

<span data-ttu-id="36afe-167">次の表に、応答グループの使用レポートで使用できるフィルターを示します。</span><span class="sxs-lookup"><span data-stu-id="36afe-167">The following table lists the filters that you can use with the Response Group Usage Report.</span></span>

### <a name="response-group-usage-report-filters"></a><span data-ttu-id="36afe-168">応答グループの使用レポートのフィルター</span><span class="sxs-lookup"><span data-stu-id="36afe-168">Response Group Usage Report Filters</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="36afe-169">名前</span><span class="sxs-lookup"><span data-stu-id="36afe-169">Name</span></span></th>
<th><span data-ttu-id="36afe-170">説明</span><span class="sxs-lookup"><span data-stu-id="36afe-170">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="36afe-171"><strong>開始</strong></span><span class="sxs-lookup"><span data-stu-id="36afe-171"><strong>From</strong></span></span></p></td>
<td><p><span data-ttu-id="36afe-p115">時間範囲の開始日と開始時刻。データを時間単位で表示するには、次のように開始日と開始時刻の両方を入力します。</span><span class="sxs-lookup"><span data-stu-id="36afe-p115">Start date/time for the time range. To view data by hours, enter both the start date and time as follows:</span></span></p>
<p><span data-ttu-id="36afe-174">7/7/2012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="36afe-174">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="36afe-p116">開始時刻を入力しないと、レポートは自動的に指定日の午前 12:00 に開始します。データを日単位で表示するには、次のように日付のみを入力します。</span><span class="sxs-lookup"><span data-stu-id="36afe-p116">If you do not enter a start time, the report automatically begins at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="36afe-177">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="36afe-177">7/7/2012</span></span></p>
<p><span data-ttu-id="36afe-178">週単位または月単位で表示するには、表示する週または月の任意の日付を入力します (その週または月の最初の日である必要はありません)。</span><span class="sxs-lookup"><span data-stu-id="36afe-178">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="36afe-179">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="36afe-179">7/3/2012</span></span></p>
<p><span data-ttu-id="36afe-180">一週間は、日曜日から始まり、土曜日で終わるものとします。</span><span class="sxs-lookup"><span data-stu-id="36afe-180">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="36afe-181"><strong>終了</strong></span><span class="sxs-lookup"><span data-stu-id="36afe-181"><strong>To</strong></span></span></p></td>
<td><p><span data-ttu-id="36afe-p117">時間範囲の終了日と終了時刻。データを時間単位で表示するには、次のように終了日と終了時刻の両方を入力します。</span><span class="sxs-lookup"><span data-stu-id="36afe-p117">End date/time for the time range. To view data by hours, enter both the end date and time as follows:</span></span></p>
<p><span data-ttu-id="36afe-184">7/7/2012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="36afe-184">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="36afe-p118">終了時刻を入力しないと、レポートは自動的に指定日の午前 12:00 に終了します。データを日単位で表示するには、次のように日付のみを入力します。</span><span class="sxs-lookup"><span data-stu-id="36afe-p118">If you do not enter an end time, the report automatically ends at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="36afe-187">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="36afe-187">7/7/2012</span></span></p>
<p><span data-ttu-id="36afe-188">週単位または月単位で表示するには、表示する週または月の任意の日付を入力します (その週または月の最初の日である必要はありません)。</span><span class="sxs-lookup"><span data-stu-id="36afe-188">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="36afe-189">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="36afe-189">7/3/2012</span></span></p>
<p><span data-ttu-id="36afe-190">一週間は、日曜日から始まり、土曜日で終わるものとします。</span><span class="sxs-lookup"><span data-stu-id="36afe-190">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="36afe-191"><strong>[間隔]</strong></span><span class="sxs-lookup"><span data-stu-id="36afe-191"><strong>Interval</strong></span></span></p></td>
<td><p><span data-ttu-id="36afe-p119">時間間隔です。次のいずれかを選択します。</span><span class="sxs-lookup"><span data-stu-id="36afe-p119">Time interval. Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="36afe-194">毎時 (最大 25 時間の表示が可能)</span><span class="sxs-lookup"><span data-stu-id="36afe-194">Hourly (a maximum of 25 hours can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="36afe-195">毎日 (最大 31 日の表示が可能)</span><span class="sxs-lookup"><span data-stu-id="36afe-195">Daily (a maximum of 31 days can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="36afe-196">毎週 (最大 12 週の表示が可能)</span><span class="sxs-lookup"><span data-stu-id="36afe-196">Weekly (a maximum of 12 weeks can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="36afe-197">毎月 (最大 12 か月の表示が可能)</span><span class="sxs-lookup"><span data-stu-id="36afe-197">Monthly (a maximum of 12 months can be displayed)</span></span></p></li>
</ul>
<p><span data-ttu-id="36afe-198">入力した開始日と終了日が選択した間隔で使用できる値の最大数を超える場合は、最大数の値 (開始日からカウント) のみが表示されます。</span><span class="sxs-lookup"><span data-stu-id="36afe-198">If the start and end dates exceed the maximum number of values allowed for the selected interval, only the maximum number of values (starting from the start date) is displayed.</span></span> <span data-ttu-id="36afe-199">たとえば、開始日が7/7/2012 で、終了日が2/28/2012 の [日] 間隔を選択した場合は、8/7/2012 12:00 AM から 9/7/2012 12:00 AM (つまり、31日分のデータ) のデータが表示されます。</span><span class="sxs-lookup"><span data-stu-id="36afe-199">For example, if you select the Daily interval with a start date of 7/7/2012 and an end date of 2/28/2012, data is displayed for the days 8/7/2012 12:00 AM to 9/7/2012 12:00 AM (that is, a total of 31 days' worth of data).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="36afe-200"><strong>[ワークフロー URI]</strong></span><span class="sxs-lookup"><span data-stu-id="36afe-200"><strong>Workflow URI</strong></span></span></p></td>
<td><p><span data-ttu-id="36afe-p121">返されるデータを、指定されている応答グループ ワークフローに制限できます。このフィルターを使用するには、ワークフローの SIP アドレスを入力します。次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="36afe-p121">Enables you to limit the returned data to the specified Response Group workflow. To use this filter, enter the Workflow SIP address. For example:</span></span></p>
<p><span data-ttu-id="36afe-204">sip:helpdesk@litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="36afe-204">sip:helpdesk@litwareinc.com</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics"></a><span data-ttu-id="36afe-205">指標</span><span class="sxs-lookup"><span data-stu-id="36afe-205">Metrics</span></span>

<span data-ttu-id="36afe-206">次の表に、応答グループの使用レポートで提供される情報を示します。</span><span class="sxs-lookup"><span data-stu-id="36afe-206">The following table lists the information provided in the Response Group Usage Report.</span></span>

### <a name="response-group-usage-report-metrics"></a><span data-ttu-id="36afe-207">応答グループの使用レポートの指標</span><span class="sxs-lookup"><span data-stu-id="36afe-207">Response Group Usage Report Metrics</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="36afe-208">名前</span><span class="sxs-lookup"><span data-stu-id="36afe-208">Name</span></span></th>
<th><span data-ttu-id="36afe-209">この項目での並べ替え</span><span class="sxs-lookup"><span data-stu-id="36afe-209">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="36afe-210">説明</span><span class="sxs-lookup"><span data-stu-id="36afe-210">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="36afe-211"><strong>[毎時]</strong></span><span class="sxs-lookup"><span data-stu-id="36afe-211"><strong>Hourly</strong></span></span></p>
<p><span data-ttu-id="36afe-212"><strong>[毎日]</strong></span><span class="sxs-lookup"><span data-stu-id="36afe-212"><strong>Daily</strong></span></span></p>
<p><span data-ttu-id="36afe-213"><strong>[毎週]</strong></span><span class="sxs-lookup"><span data-stu-id="36afe-213"><strong>Weekly</strong></span></span></p>
<p><span data-ttu-id="36afe-214"><strong>[毎月]</strong></span><span class="sxs-lookup"><span data-stu-id="36afe-214"><strong>Monthly</strong></span></span></p></td>
<td><p><span data-ttu-id="36afe-215">いいえ</span><span class="sxs-lookup"><span data-stu-id="36afe-215">No</span></span></p></td>
<td><p><span data-ttu-id="36afe-216">選択されている時間間隔を示します。</span><span class="sxs-lookup"><span data-stu-id="36afe-216">Indicates the selected time interval.</span></span> <span data-ttu-id="36afe-217">必要に応じて、特定の時間間隔をクリックして、その間隔の詳細な情報を表示できます。</span><span class="sxs-lookup"><span data-stu-id="36afe-217">Where applicable, you can click a given time interval to view detailed information for that interval.</span></span> <span data-ttu-id="36afe-218">たとえば、毎日の間隔を使用していて、[7/7/2012] をクリックすると、その日付のユーザー登録アクティビティの時間の内訳が表示されます。</span><span class="sxs-lookup"><span data-stu-id="36afe-218">For example, if you are using the Daily interval and you click 7/7/2012, you see an hourly breakdown of user registration activity for that date.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="36afe-219"><strong>[受信した通話]</strong></span><span class="sxs-lookup"><span data-stu-id="36afe-219"><strong>Received calls</strong></span></span></p></td>
<td><p><span data-ttu-id="36afe-220">いいえ</span><span class="sxs-lookup"><span data-stu-id="36afe-220">No</span></span></p></td>
<td><p><span data-ttu-id="36afe-p123">応答グループ アプリケーションのすべてのインスタンスで受信した通話の合計数。この項目をクリックすると、選択されている期間の応答グループの通話リスト レポートが表示されます。</span><span class="sxs-lookup"><span data-stu-id="36afe-p123">Total number of calls received by all instances of the Response Group application. When you click this item, the report shows you the Response Group Call List report for the selected time period.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="36afe-223"><strong>[正常な通話]</strong></span><span class="sxs-lookup"><span data-stu-id="36afe-223"><strong>Successful calls</strong></span></span></p></td>
<td><p><span data-ttu-id="36afe-224">いいえ</span><span class="sxs-lookup"><span data-stu-id="36afe-224">No</span></span></p></td>
<td><p><span data-ttu-id="36afe-p124">応答グループ アプリケーションによって選択された通話の合計数。この項目をクリックすると、選択されている期間の応答グループの通話リスト レポートが表示されます。</span><span class="sxs-lookup"><span data-stu-id="36afe-p124">Total number of calls that were picked up the Response Group application. When you click this item, the report shows you the Response Group Call List report for the selected time period.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="36afe-227"><strong>[提供された通話]</strong></span><span class="sxs-lookup"><span data-stu-id="36afe-227"><strong>Offered calls</strong></span></span></p></td>
<td><p><span data-ttu-id="36afe-228">いいえ</span><span class="sxs-lookup"><span data-stu-id="36afe-228">No</span></span></p></td>
<td><p><span data-ttu-id="36afe-p125">応答グループ エージェントによって転送された通話の合計数。この項目をクリックすると、選択されている期間の応答グループの通話リスト レポートが表示されます。</span><span class="sxs-lookup"><span data-stu-id="36afe-p125">Total number of calls that were transferred to a Response Group agent. When you click this item, the report shows you the Response Group Call List report for the selected time period.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="36afe-231"><strong>[応答した通話]</strong></span><span class="sxs-lookup"><span data-stu-id="36afe-231"><strong>Answered calls</strong></span></span></p></td>
<td><p><span data-ttu-id="36afe-232">いいえ</span><span class="sxs-lookup"><span data-stu-id="36afe-232">No</span></span></p></td>
<td><p><span data-ttu-id="36afe-p126">応答グループ エージェントが実際に応答した通話の合計数。この項目をクリックすると、選択されている期間の応答グループの通話リスト レポートが表示されます。</span><span class="sxs-lookup"><span data-stu-id="36afe-p126">Total number of calls that were actually answered by a Response Group agent. When you click this item, the report shows you the Response Group Call List report for the selected time period.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="36afe-235"><strong>[破棄された通話のパーセンテージ]</strong></span><span class="sxs-lookup"><span data-stu-id="36afe-235"><strong>Percentage of abandoned calls</strong></span></span></p></td>
<td><p><span data-ttu-id="36afe-236">いいえ</span><span class="sxs-lookup"><span data-stu-id="36afe-236">No</span></span></p></td>
<td><p><span data-ttu-id="36afe-p127">応答グループ アプリケーションによって受信されたが、エージェントが応答しなかった通話の合計数。これは、受信した通話数から応答した通話数を引いた値を受信した通話数で割って計算されます。たとえば、受信した通話数が 10 件、応答した通話数が 7 件の場合、10 から 7 を引いて 3 件が応答のない通話数として残ります。この値を 10 で割ると、破棄された通話のパーセンテージは 30% になります。</span><span class="sxs-lookup"><span data-stu-id="36afe-p127">Total number of calls that were received by the Response Group application but were never answered by an agent. This is calculated by subtracting the Answered calls from the Received calls, and then dividing that value by the number of received calls. For example, if you have 10 received calls and seven were answered, you would subtract seven from 10, leaving three unanswered calls. That value would then be divided by 10, giving you an abandoned call percentage of 30%.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="36afe-241"><strong>[エージェントの平均通話時間]</strong></span><span class="sxs-lookup"><span data-stu-id="36afe-241"><strong>Average call minutes by agent</strong></span></span></p></td>
<td><p><span data-ttu-id="36afe-242">いいえ</span><span class="sxs-lookup"><span data-stu-id="36afe-242">No</span></span></p></td>
<td><p><span data-ttu-id="36afe-243">応答グループ エージェントの平均通話時間。</span><span class="sxs-lookup"><span data-stu-id="36afe-243">Average amount of time a Response Group agent spent on a call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="36afe-244"><strong>[転送された通話]</strong></span><span class="sxs-lookup"><span data-stu-id="36afe-244"><strong>Transferred calls</strong></span></span></p></td>
<td><p><span data-ttu-id="36afe-245">不可</span><span class="sxs-lookup"><span data-stu-id="36afe-245">No</span></span></p></td>
<td><p><span data-ttu-id="36afe-p128">キューのタイムアウトまたはキューのオーバーフローによって転送された、応答グループの通話の合計数。この項目をクリックすると、選択されている期間の応答グループの通話リスト レポートが表示されます。</span><span class="sxs-lookup"><span data-stu-id="36afe-p128">Total number of Response Group calls that were transferred because of a queue timeout or queue overflow. When you click this item, the report shows you the Response Group Call List report for the selected time period.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

