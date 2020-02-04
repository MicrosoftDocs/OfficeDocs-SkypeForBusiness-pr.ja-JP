---
title: 'Lync Server 2013: ユーザーアクティビティレポート'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: User Activity Report
ms:assetid: 3aa6fef2-ea02-4f0f-93e8-fa2e0a953d79
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558638(v=OCS.15)
ms:contentKeyID: 48183862
ms.date: 02/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 583c647ac3cdab290f1833539abbbd033ea89410
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41744627"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="user-activity-report-in-lync-server-2013"></a><span data-ttu-id="ac026-102">Lync Server 2013 のユーザーアクティビティレポート</span><span class="sxs-lookup"><span data-stu-id="ac026-102">User Activity Report in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ac026-103">_**最終更新日:** 2015-02-27_</span><span class="sxs-lookup"><span data-stu-id="ac026-103">_**Topic Last Modified:** 2015-02-27_</span></span>

<span data-ttu-id="ac026-p101">ユーザー アクティビティ レポートは、特定の期間にユーザーによって実行されたピアツーピアおよび電話会議セッションの詳細な一覧を示します。多くの監視レポートとは異なり、ユーザー アクティビティ レポートは、各呼び出しを個別のユーザーに関連付けます。たとえば、ピアツーピアセッションでは、呼び出しを開始した人 (呼び出し元ユーザー) と呼び出しを受けた人 (呼び出し先ユーザー) の SIP URI が表示されます。電話会議の情報を展開すると、すべての電話会議の参加者と、その電話会議における参加者の役割の一覧が表示されます。</span><span class="sxs-lookup"><span data-stu-id="ac026-p101">The User Activity Report provides a detailed list of the peer-to-peer and conferencing sessions carried out by your users in a given time period. Unlike many of the Monitoring Reports, the User Activity Report ties each call to individual users. For example, peer-to-peer sessions specify the SIP URIs of the person who initiated the call (the From user) and the person who was being called (the To user). If you expand the information for a conference, you'll see a list of all the conference participants and the role they held for that conference.</span></span>

<span data-ttu-id="ac026-p102">ユーザー アクティビティ レポートは、"ヘルプ デスク" レポートと呼ばれることがあります。ヘルプデスク担当者が、特定のユーザーに関するセッション情報を取得するときによくこのレポートを利用するからです。個別のユーザーに対する、または個別のユーザーによる呼び出しは、[ユーザー URI プレフィックス] ボックスにユーザーの SIP URI を入力するだけでフィルターできます。</span><span class="sxs-lookup"><span data-stu-id="ac026-p102">The User Activity Report is sometimes referred to as the "help desk" report. That's because the report is often used by help desk personnel to retrieve session information for a specific user. You can filter for calls made to or made by an individual user simply by typing the user's SIP URI in the User URI prefix box.</span></span>

<span data-ttu-id="ac026-111">この場合、ユーザーアクティビティレポートは、指定された文字列で SIP URI が始まるすべてのユーザーに関する情報を返します。</span><span class="sxs-lookup"><span data-stu-id="ac026-111">If you do this, the User Activity Report will return information for any user whose SIP URI begins with the specified string.</span></span> <span data-ttu-id="ac026-112">たとえば、[URI] ボックスに「 **ken** 」と入力すると、ユーザーアクティビティレポートによって**ken**が検索されます。Myer@litwareinc.com。</span><span class="sxs-lookup"><span data-stu-id="ac026-112">For example, if you type **ken** in the URI box, the User Activity Report will locate **Ken**.Myer@litwareinc.com.</span></span> <span data-ttu-id="ac026-113">ただし、次のユーザーも検索されます。</span><span class="sxs-lookup"><span data-stu-id="ac026-113">However, it will also locate these users:</span></span>

  - <span data-ttu-id="ac026-114">**ken**azi@litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="ac026-114">**ken**azi@litwareinc.com</span></span>

  - <span data-ttu-id="ac026-115">**ken**burg@litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="ac026-115">**ken**burg@litwareinc.com</span></span>

  - <span data-ttu-id="ac026-116">**Ken**.Sanchez@litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="ac026-116">**Ken**.Sanchez@litwareinc.com</span></span>

  - <span data-ttu-id="ac026-117">**Ken**nedy@litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="ac026-117">**Ken**nedy@litwareinc.com</span></span>

<span data-ttu-id="ac026-p104">Ken Myer に関する情報のみを表示するには、検索ボックスに URI をすべて (Ken.Myer@litwareinc.com) 入力するか、または次の例のように、少なくとも組織内の他のユーザーから Ken Myer のみを一意に区別できるだけの文字列を入力します。</span><span class="sxs-lookup"><span data-stu-id="ac026-p104">To ensure that information only for Ken Myer is returned, either type his full URI (Ken.Myer@litwareinc.com) in the search box or at least enough type of Ken’s URI to uniquely distinguish him from other users in your organization. For example:</span></span>

<span data-ttu-id="ac026-120">Ken.my</span><span class="sxs-lookup"><span data-stu-id="ac026-120">Ken.my</span></span>

<div>

## <a name="to-access-the-user-activity-report"></a><span data-ttu-id="ac026-121">ユーザー アクティビティ レポートにアクセスするには</span><span class="sxs-lookup"><span data-stu-id="ac026-121">To access the user activity report</span></span>

<span data-ttu-id="ac026-122">ユーザー アクティビティ レポートには、[監視レポート] ホーム ページからアクセスします。</span><span class="sxs-lookup"><span data-stu-id="ac026-122">The User Activity Report is accessed from the Monitoring Reports home page.</span></span> <span data-ttu-id="ac026-123">[Lync Server 2013 で、[IP 電話インベントリ] レポート](lync-server-2013-ip-phone-inventory-report.md)のユーザー URI メトリックをクリックして、ユーザーアクティビティレポートにアクセスすることもできます。</span><span class="sxs-lookup"><span data-stu-id="ac026-123">You can also reach the User Activity Report by clicking the User URI metric on the [IP Phone Inventory Report in Lync Server 2013](lync-server-2013-ip-phone-inventory-report.md).</span></span> <span data-ttu-id="ac026-124">ユーザー アクティビティ レポートで [電話会議 URI] (電話会議の場合) をクリックすると、会議詳細レポートが表示されます。</span><span class="sxs-lookup"><span data-stu-id="ac026-124">From within the User Activity Report, clicking the Conference URI (for a conference) takes you to the Conference Detail Report.</span></span> <span data-ttu-id="ac026-125">同様に、ピアツーピア通話の詳細なメトリックをクリックすると、 [Lync Server 2013 のピアツーピアセッションの詳細レポート](lync-server-2013-peer-to-peer-session-detail-report.md)に移動します。</span><span class="sxs-lookup"><span data-stu-id="ac026-125">Similarly, clicking the Detail metric for a peer-to-peer call takes you to the [Peer-to-Peer Session Detail Report in Lync Server 2013](lync-server-2013-peer-to-peer-session-detail-report.md).</span></span>

</div>

<div>

## <a name="making-the-best-use-of-the-user-activity-report"></a><span data-ttu-id="ac026-126">ユーザー アクティビティ レポートを最大限に利用する</span><span class="sxs-lookup"><span data-stu-id="ac026-126">Making the best use of the user activity report</span></span>

<span data-ttu-id="ac026-127">ユーザーアクティビティレポートには、多くの適切な情報はありますが、情報を見つけるのが難しい場合があります。</span><span class="sxs-lookup"><span data-stu-id="ac026-127">Although there is a lot of good information in the User Activity Report, that information can sometimes be difficult to locate.</span></span> <span data-ttu-id="ac026-128">たとえば、指定した期間中に組織内で実行されるすべてのユーザーアクティビティは、ユーザーアクティビティレポートに含まれます。つまり、レポート内に埋め込まれているということは、Microsoft Lync Server 2013 を実際に何らかの方法で使用したユーザーに関する情報です。</span><span class="sxs-lookup"><span data-stu-id="ac026-128">For example, all the user activity that takes place in your organization during a specified period is included in the User Activity Report; that means that, buried, within the report is information about which users actually used Microsoft Lync Server 2013 in some way.</span></span>

<div>


> [!WARNING]  
> <span data-ttu-id="ac026-129">技術的には、一部のユーザーアクティビティが unrecorded になることもあります。 Lync Server は、すべての通話に関する情報を保持していますが、通話についての情報がデータベースに書き込まれることはありません。</span><span class="sxs-lookup"><span data-stu-id="ac026-129">Technically, it’s possible that some user activity might go unrecorded: while Lync Server strives to keep information about all phone calls it's possible that a call could have been made without the information about that call being written to the database.</span></span> <span data-ttu-id="ac026-130">Lync Server は、非常に正確に表示されるように設計されていますが、Lync Server 2013 の使用方法については、必ずしもはっきりしません。</span><span class="sxs-lookup"><span data-stu-id="ac026-130">Lync Server is designed to give an extremely accurate but not necessarily perfect look at how Lync Server 2013 is being used.</span></span> <span data-ttu-id="ac026-131">(すべての通話の100% が記録されるという保証はありません。 Lync Server の監視を課金システムとして使用しないようにする必要がある理由について説明します)。</span><span class="sxs-lookup"><span data-stu-id="ac026-131">(The fact that there is no guarantee that 100% of all calls are recorded explains why Lync Server monitoring should not be used as a billing system.)</span></span><BR><span data-ttu-id="ac026-132">次に、監視レポートレポートで表示できるのは、最大で1000レコードだけです。</span><span class="sxs-lookup"><span data-stu-id="ac026-132">Second, a Monitoring Report report can only display, at most, 1,000 records.</span></span> <span data-ttu-id="ac026-133">これは、ユーザー アクティビティの量と作業時間によっては、データベースに実際に格納されたデータの一部がクエリでは返されない場合があることを意味します。</span><span class="sxs-lookup"><span data-stu-id="ac026-133">Depending on the amount of user activity you have, and depending on the time period you are working with, that means your query might not return all the data actually stored in the database.</span></span>



</div>

  - <span data-ttu-id="ac026-134">この期間内にシステムを実際に使用したのはどのユーザーか。</span><span class="sxs-lookup"><span data-stu-id="ac026-134">Which users actually used the system during this time period?</span></span>

  - <span data-ttu-id="ac026-135">この期間内に最もアクティブだったのはどのユーザーか。</span><span class="sxs-lookup"><span data-stu-id="ac026-135">Which of my users were the most active during this time period?</span></span>

  - <span data-ttu-id="ac026-136">通話数が最も多いユーザーが、最も多くのインスタント メッセージング セッションに参加しているユーザーでもあるかどうか。</span><span class="sxs-lookup"><span data-stu-id="ac026-136">Are the users who make the most phone calls also the users who participate in the most instant messaging sessions?</span></span>

<span data-ttu-id="ac026-137">このような情報を確認するには、監視レポートで取得されたデータを Excel スプレッドシートにエクスポートします。</span><span class="sxs-lookup"><span data-stu-id="ac026-137">If you need to answer questions like this, you can export the data retrieved by the Monitoring Reports to an Excel spreadsheet.</span></span> <span data-ttu-id="ac026-138">次に、そのスプレッドシート/カンマ区切り値ファイルを使用して、ユーザー アクティビティ レポートのような方法でデータを分析します。</span><span class="sxs-lookup"><span data-stu-id="ac026-138">You then use that spreadsheet and/or a comma-separated values file to analyze the data in ways that the User Activity Report.</span></span> <span data-ttu-id="ac026-139">たとえば、レポートデータを Excel にエクスポートしてから、カンマ区切り値ファイルにエクスポートするとします。</span><span class="sxs-lookup"><span data-stu-id="ac026-139">For example, suppose you have exported the report data to Excel and then to a comma-separated values file.</span></span> <span data-ttu-id="ac026-140">その時点で、からデータをインポートできます。次のようなコマンドを使用して、Windows PowerShell に CSV ファイルを保存します。</span><span class="sxs-lookup"><span data-stu-id="ac026-140">At that point, you can import the data from the .CSV file to Windows PowerShell by using a command similar to this:</span></span>

    $x = Import-Csv -Path "C:\Data\User_Activity_Report.csv"

<span data-ttu-id="ac026-141">データをインポートした後は、簡単な Windows PowerShell コマンドを使って質問に答えることができます。</span><span class="sxs-lookup"><span data-stu-id="ac026-141">After the data has been imported you can then use simple Windows PowerShell commands to help answer your questions.</span></span> <span data-ttu-id="ac026-142">たとえば、次のコマンドは、少なくとも 1 つのセッションで "呼び出し元ユーザー" としての役割を果たす一意のユーザーの一覧を返します。</span><span class="sxs-lookup"><span data-stu-id="ac026-142">For example, this command returns a list of unique users who served as the "From user" in at least one session:</span></span>

    $x | Group-Object "From user" | Select Name | Sort-Object Name

<span data-ttu-id="ac026-143">つまり、次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="ac026-143">In other words:</span></span>

    Name
    ----
    David.Ahs@litwareinc.com
    Gilead.Amosnino@litwareinc.com
    Henrik.Jensen@litwareinc.com
    Ken.Myer@litwareinc.com
    Pilar.Ackerman@litwareinc.com

<span data-ttu-id="ac026-144">次のコマンドは、ユーザーが参加しているセッションの合計数に基づいて、一意のユーザーの一覧を表示します。</span><span class="sxs-lookup"><span data-stu-id="ac026-144">This command lists the unique users (based on the total number of sessions that they participated in:</span></span>

    $x | Group-Object "From user" | Select Count, Name | Sort-Object Count -Descending

<span data-ttu-id="ac026-145">このコマンドは次のようなデータを返します。</span><span class="sxs-lookup"><span data-stu-id="ac026-145">That returns data similar to this:</span></span>

    Count    Name
    -----    ----
      523    Ken.Myer@litwareinc.com
       63    David.Ahs@litwareinc.com
       29    Pilar.Ackerman@litwareinc.com
       17    Gilead.Amosnino@litwareinc.com
       10    Henrik.Jensen@litwareinc.com

<span data-ttu-id="ac026-146">次のコマンドは、報告されたセッションを、モダリティとしてオーディオが含まれるセッションに制限します。</span><span class="sxs-lookup"><span data-stu-id="ac026-146">This command limits the reported sessions to those that included audio as a modality:</span></span>

    $x | Where-Object {$_.Modalities -match "audio"} | Group-Object "From user" | Select Count, Name | Sort-Object Count -Descending

<span data-ttu-id="ac026-147">レポートに表示されている診断 ID の上にマウスを置くと、その ID について説明するヒントが表示されます。</span><span class="sxs-lookup"><span data-stu-id="ac026-147">If you hold your mouse over any Diagnostic ID shown on the report, a tooltip will appear describing that ID.</span></span>

</div>

<div>

## <a name="filters"></a><span data-ttu-id="ac026-148">フィルター</span><span class="sxs-lookup"><span data-stu-id="ac026-148">Filters</span></span>

<span data-ttu-id="ac026-p111">フィルターは、必要なデータのみに絞り込んだデータ セットを取得したり、取得したデータを別の方法で表示したりする方法として利用できます。たとえば、ユーザー アクティビティ レポートを使用すると、取得したデータに動作状況の種類 (ピアツーピア セッションまたは電話会議セッション) などに基づいてフィルターを適用できます。また、ユーザーの SIP アドレスによってフィルターを適用することもできます (この場合、1 人のユーザーの動作状況を表示できます)。データをグループ化する方法を選択することもできます。この場合、使用状況は、時間単位、日単位、週単位、または月単位でグループ化されます。</span><span class="sxs-lookup"><span data-stu-id="ac026-p111">Filters provide a way for you to return a more finely-targeted set of data or to view the returned data in different ways. For example, the User Activity Report enables you to filter the returned data based on such things as activity type (that is, peer-to-peer sessions or conferencing sessions) or by the user's SIP address (allowing you to view the activities for one user). You can also choose how data should be grouped. In this case, usages are grouped by hour, day, week, or month.</span></span>

<span data-ttu-id="ac026-153">次の表に、ユーザー アクティビティ レポートで使用できるフィルターを示します。</span><span class="sxs-lookup"><span data-stu-id="ac026-153">The following table lists the filters that you can use with the User Activity Report.</span></span>

### <a name="user-activity-report-filters"></a><span data-ttu-id="ac026-154">ユーザー アクティビティ レポートのフィルター</span><span class="sxs-lookup"><span data-stu-id="ac026-154">User activity report filters</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="ac026-155">名前</span><span class="sxs-lookup"><span data-stu-id="ac026-155">Name</span></span></th>
<th><span data-ttu-id="ac026-156">説明</span><span class="sxs-lookup"><span data-stu-id="ac026-156">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ac026-157"><strong>開始</strong></span><span class="sxs-lookup"><span data-stu-id="ac026-157"><strong>From</strong></span></span></p></td>
<td><p><span data-ttu-id="ac026-p112">時間範囲の開始日と開始時刻。データを時間単位で表示するには、次のように開始日と開始時刻の両方を入力します。</span><span class="sxs-lookup"><span data-stu-id="ac026-p112">Start date/time for the time range. To view data by hours, enter both the start date and time as follows:</span></span></p>
<p><span data-ttu-id="ac026-160">7/17/12012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="ac026-160">7/17/12012 1:00 PM</span></span></p>
<p><span data-ttu-id="ac026-p113">開始時刻を入力しないと、レポートは自動的に指定日の午前 12:00 に開始します。データを日単位で表示するには、次のように日付のみを入力します。</span><span class="sxs-lookup"><span data-stu-id="ac026-p113">If you do not enter a start time, the report automatically begins at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="ac026-163">7/17/12012</span><span class="sxs-lookup"><span data-stu-id="ac026-163">7/17/12012</span></span></p>
<p><span data-ttu-id="ac026-164">週単位または月単位で表示するには、表示する週または月の任意の日付を入力します (その週または月の最初の日である必要はありません)。</span><span class="sxs-lookup"><span data-stu-id="ac026-164">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="ac026-165">7/13/2012</span><span class="sxs-lookup"><span data-stu-id="ac026-165">7/13/2012</span></span></p>
<p><span data-ttu-id="ac026-166">一週間は、日曜日から始まり、土曜日で終わるものとします。</span><span class="sxs-lookup"><span data-stu-id="ac026-166">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ac026-167"><strong>終了</strong></span><span class="sxs-lookup"><span data-stu-id="ac026-167"><strong>To</strong></span></span></p></td>
<td><p><span data-ttu-id="ac026-p114">時間範囲の終了日と終了時刻。データを時間単位で表示するには、次のように終了日と終了時刻の両方を入力します。</span><span class="sxs-lookup"><span data-stu-id="ac026-p114">End date/time for the time range. To view data by hours, enter both the end date and time as follows:</span></span></p>
<p><span data-ttu-id="ac026-170">7/17/12012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="ac026-170">7/17/12012 1:00 PM</span></span></p>
<p><span data-ttu-id="ac026-p115">終了時刻を入力しないと、レポートは自動的に指定日の午前 12:00 に終了します。データを日単位で表示するには、次のように日付のみを入力します。</span><span class="sxs-lookup"><span data-stu-id="ac026-p115">If you do not enter an end time, the report automatically ends at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="ac026-173">7/17/12012</span><span class="sxs-lookup"><span data-stu-id="ac026-173">7/17/12012</span></span></p>
<p><span data-ttu-id="ac026-174">週単位または月単位で表示するには、表示する週または月の任意の日付を入力します (その週または月の最初の日である必要はありません)。</span><span class="sxs-lookup"><span data-stu-id="ac026-174">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="ac026-175">7/13/2012</span><span class="sxs-lookup"><span data-stu-id="ac026-175">7/13/2012</span></span></p>
<p><span data-ttu-id="ac026-176">一週間は、日曜日から始まり、土曜日で終わるものとします。</span><span class="sxs-lookup"><span data-stu-id="ac026-176">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ac026-177"><strong>[動作状況の種類]</strong></span><span class="sxs-lookup"><span data-stu-id="ac026-177"><strong>Activity type</strong></span></span></p></td>
<td><p><span data-ttu-id="ac026-p116">動作状況の種類。次のいずれかを選択します。</span><span class="sxs-lookup"><span data-stu-id="ac026-p116">Type of activity. Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="ac026-180">[すべて]</span><span class="sxs-lookup"><span data-stu-id="ac026-180">[All]</span></span></p></li>
<li><p><span data-ttu-id="ac026-181">ピアツーピア</span><span class="sxs-lookup"><span data-stu-id="ac026-181">Peer-to-peer</span></span></p></li>
<li><p><span data-ttu-id="ac026-182">電話会議</span><span class="sxs-lookup"><span data-stu-id="ac026-182">Conference</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ac026-183"><strong>[モダリティ]</strong></span><span class="sxs-lookup"><span data-stu-id="ac026-183"><strong>Modality</strong></span></span></p></td>
<td><p><span data-ttu-id="ac026-184">使用できる [モダリティ] は、選んだ [動作状況の種類] によって異なります。</span><span class="sxs-lookup"><span data-stu-id="ac026-184">The Modality available to you varies depending on the select Activity Type.</span></span> <span data-ttu-id="ac026-185">アクティビティの種類がピアツーピアの場合は、[IM] を選ぶことができます。ファイル送信アプリケーションの共有;トラフィックまたはビデオ。</span><span class="sxs-lookup"><span data-stu-id="ac026-185">If the Activity Type is Peer-to-Peer, you can select IM; File Transfer; Application Sharing; Voice; or Video as the modality.</span></span></p>
<p><span data-ttu-id="ac026-186">[動作状況の種類] が [電話会議] の場合は、[IM 電話会議]、[Web 会議]、[アプリケーション共有]、[音声/ビデオ会議]、[テレフォニー会議] のいずれかを選択できます。</span><span class="sxs-lookup"><span data-stu-id="ac026-186">If the Activity Type is Conference, you can select IM Phone conference; Web conference; Application Sharing; Voice/Video conference; or Telephony conference.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ac026-187"><strong>[セッション カテゴリ]</strong></span><span class="sxs-lookup"><span data-stu-id="ac026-187"><strong>Session category</strong></span></span></p></td>
<td><p><span data-ttu-id="ac026-p118">問題のアクティビティが成功したか失敗したかを示します。次のいずれかを選択します。</span><span class="sxs-lookup"><span data-stu-id="ac026-p118">Indicates whether the activity in question succeeded or failed. Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="ac026-190">[すべて]</span><span class="sxs-lookup"><span data-stu-id="ac026-190">[All]</span></span></p></li>
<li><p><span data-ttu-id="ac026-191">成功</span><span class="sxs-lookup"><span data-stu-id="ac026-191">Success</span></span></p></li>
<li><p><span data-ttu-id="ac026-192">予期されたエラー</span><span class="sxs-lookup"><span data-stu-id="ac026-192">Expected failure</span></span></p></li>
<li><p><span data-ttu-id="ac026-193">予期しないエラー</span><span class="sxs-lookup"><span data-stu-id="ac026-193">Unexpected failure</span></span></p></li>
</ul>
<p><span data-ttu-id="ac026-194">&quot;予期される&quot;エラーは、発生する可能性のあるエラーです。たとえば、ユーザーが自分の状態を [応答不可] に設定している場合、そのユーザーへの任意の呼び出しが失敗すると想定されます。</span><span class="sxs-lookup"><span data-stu-id="ac026-194">An &quot;expected failure&quot; is a failure that is expected to happen; for example, if a user has set his or her status to Do Not Disturb you would expect any call to that user to fail.</span></span> <span data-ttu-id="ac026-195">&quot;予期しない&quot;エラーとは、正常に動作していると思われるエラーです。</span><span class="sxs-lookup"><span data-stu-id="ac026-195">An &quot;unexpected failure&quot; is a failure that occurs in what would appear to be an otherwise healthy system.</span></span> <span data-ttu-id="ac026-196">たとえば、発信者が保留にされたときに、通話が終了してはなりません。</span><span class="sxs-lookup"><span data-stu-id="ac026-196">For example, a call should not be terminated if the caller is placed on hold.</span></span> <span data-ttu-id="ac026-197">そのような状態が発生する場合は、予期しないエラーとしてフラグが設定されます。</span><span class="sxs-lookup"><span data-stu-id="ac026-197">If that occurs, that would be flagged as an unexpected failure.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ac026-198"><strong>[ユーザー URI プレフィックス]</strong></span><span class="sxs-lookup"><span data-stu-id="ac026-198"><strong>User URI prefix</strong></span></span></p></td>
<td><p><span data-ttu-id="ac026-p120">ユーザーの SIP アドレス。たとえば、Ken Myer という名前のユーザーのレコードのみを表示するには、次のように、Ken Myer の SIP アドレスを入力する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ac026-p120">SIP address for the user. To view records only for the user Ken Myer you need to enter Ken Myer's SIP address. For example:</span></span></p>
<p><span data-ttu-id="ac026-202">sip:kenmyer@litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="ac026-202">sip:kenmyer@litwareinc.com</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-peer-to-peer-sessions"></a><span data-ttu-id="ac026-203">ピアツーピア セッションの指標</span><span class="sxs-lookup"><span data-stu-id="ac026-203">Metrics for peer-to-peer sessions</span></span>

<span data-ttu-id="ac026-204">次の表に、ピアツーピア セッション (2 人の参加者だけで行うセッション) について、ユーザー アクティビティ レポートで提供される情報を示します。</span><span class="sxs-lookup"><span data-stu-id="ac026-204">The following table lists the information provided in the User Activity Report for peer-to-peer sessions (that is, sessions involving just two participants).</span></span>

### <a name="metrics-for-peer-to-peer-sessions"></a><span data-ttu-id="ac026-205">ピアツーピア セッションの指標</span><span class="sxs-lookup"><span data-stu-id="ac026-205">Metrics for peer-to-peer sessions</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="ac026-206">名前</span><span class="sxs-lookup"><span data-stu-id="ac026-206">Name</span></span></th>
<th><span data-ttu-id="ac026-207">この項目での並べ替え</span><span class="sxs-lookup"><span data-stu-id="ac026-207">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="ac026-208">説明</span><span class="sxs-lookup"><span data-stu-id="ac026-208">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ac026-209"><strong>[詳細]</strong></span><span class="sxs-lookup"><span data-stu-id="ac026-209"><strong>Detail</strong></span></span></p></td>
<td><p><span data-ttu-id="ac026-210">不可</span><span class="sxs-lookup"><span data-stu-id="ac026-210">No</span></span></p></td>
<td><p><span data-ttu-id="ac026-211">この項目をクリックすると、選択されているセッションのピアツーピア セッション詳細レポートが表示されます。</span><span class="sxs-lookup"><span data-stu-id="ac026-211">When you click this item, the report shows you the Peer-to-Peer Session Detail Report for the selected session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ac026-212"><strong>[送信元ユーザー]</strong></span><span class="sxs-lookup"><span data-stu-id="ac026-212"><strong>From user</strong></span></span></p></td>
<td><p><span data-ttu-id="ac026-213">はい</span><span class="sxs-lookup"><span data-stu-id="ac026-213">Yes</span></span></p></td>
<td><p><span data-ttu-id="ac026-214">ピアツーピア セッションを開始したユーザーの SIP アドレス。</span><span class="sxs-lookup"><span data-stu-id="ac026-214">SIP address of the user who initiated the peer-to-peer session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ac026-215"><strong>[対象ユーザー]</strong></span><span class="sxs-lookup"><span data-stu-id="ac026-215"><strong>To user</strong></span></span></p></td>
<td><p><span data-ttu-id="ac026-216">はい</span><span class="sxs-lookup"><span data-stu-id="ac026-216">Yes</span></span></p></td>
<td><p><span data-ttu-id="ac026-217">ピアツーピア セッションに参加したユーザーの SIP アドレス。</span><span class="sxs-lookup"><span data-stu-id="ac026-217">SIP address of the user who joined the peer-to-peer session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ac026-218"><strong>[モダリティ]</strong></span><span class="sxs-lookup"><span data-stu-id="ac026-218"><strong>Modalities</strong></span></span></p></td>
<td><p><span data-ttu-id="ac026-219">はい</span><span class="sxs-lookup"><span data-stu-id="ac026-219">Yes</span></span></p></td>
<td><p><span data-ttu-id="ac026-p121">セッションで使用された通信の種類。たとえば、IM、音声、ファイル送信。</span><span class="sxs-lookup"><span data-stu-id="ac026-p121">Type of communication used in the session. For example, IM, audio, or file transfer.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ac026-222"><strong>[招待時間]</strong></span><span class="sxs-lookup"><span data-stu-id="ac026-222"><strong>Invite time</strong></span></span></p></td>
<td><p><span data-ttu-id="ac026-223">はい</span><span class="sxs-lookup"><span data-stu-id="ac026-223">Yes</span></span></p></td>
<td><p><span data-ttu-id="ac026-224">ピアツーピア セッションへの最初の招待が送信された日時。</span><span class="sxs-lookup"><span data-stu-id="ac026-224">Date and time the initial invitation to join the peer-to-peer session was sent.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ac026-225"><strong>[応答時間]</strong></span><span class="sxs-lookup"><span data-stu-id="ac026-225"><strong>Response time</strong></span></span></p></td>
<td><p><span data-ttu-id="ac026-226">可</span><span class="sxs-lookup"><span data-stu-id="ac026-226">Yes</span></span></p></td>
<td><p><span data-ttu-id="ac026-227">&quot;ユーザーが&quot;セッション招待を承諾した日付と時刻。</span><span class="sxs-lookup"><span data-stu-id="ac026-227">Date and time that the &quot;To&quot; user accepted the session invitation.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ac026-228"><strong>[終了時刻]</strong></span><span class="sxs-lookup"><span data-stu-id="ac026-228"><strong>End time</strong></span></span></p></td>
<td><p><span data-ttu-id="ac026-229">可</span><span class="sxs-lookup"><span data-stu-id="ac026-229">Yes</span></span></p></td>
<td><p><span data-ttu-id="ac026-230">ピアツーピア セッションが終了した日時。</span><span class="sxs-lookup"><span data-stu-id="ac026-230">Date and time the peer-to-peer session ended.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ac026-231"><strong>[診断 ID]</strong></span><span class="sxs-lookup"><span data-stu-id="ac026-231"><strong>Diagnostic ID</strong></span></span></p></td>
<td><p><span data-ttu-id="ac026-232">はい</span><span class="sxs-lookup"><span data-stu-id="ac026-232">Yes</span></span></p></td>
<td><p><span data-ttu-id="ac026-p122">SIP メッセージに添付される一意の識別子 (ms-diagnostics ヘッダー形式)。その情報は、多くの場合、エラーのトラブルシューティングに役立ちます。診断ヘッダーはオプションで (このヘッダーを含まない SIP セッションがある可能性もあります)、診断 ID は、何らかの問題が生じたセッションについてのみ報告されます。</span><span class="sxs-lookup"><span data-stu-id="ac026-p122">Unique identifier (in the form of an ms-diagnostics header) attached to a SIP message that often provides information useful in troubleshooting errors. Diagnostics headers are optional (it is possible to have SIP sessions that do not include these headers), and diagnostic IDs are reported only for sessions that experienced problems of some kind.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-conferencing-sessions"></a><span data-ttu-id="ac026-235">電話会議セッションの指標</span><span class="sxs-lookup"><span data-stu-id="ac026-235">Metrics for conferencing sessions</span></span>

<span data-ttu-id="ac026-236">次の表に、電話会議セッション (3 人以上の参加者で行うセッション) について、ユーザー アクティビティ レポートで提供される情報を示します。</span><span class="sxs-lookup"><span data-stu-id="ac026-236">The following table lists the information provided in the User Activity Report for conferencing sessions (that is, sessions involving three or more participants).</span></span>

### <a name="metrics-for-conferencing-sessions"></a><span data-ttu-id="ac026-237">電話会議セッションの指標</span><span class="sxs-lookup"><span data-stu-id="ac026-237">Metrics for conferencing sessions</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="ac026-238">名前</span><span class="sxs-lookup"><span data-stu-id="ac026-238">Name</span></span></th>
<th><span data-ttu-id="ac026-239">この項目での並べ替え</span><span class="sxs-lookup"><span data-stu-id="ac026-239">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="ac026-240">説明</span><span class="sxs-lookup"><span data-stu-id="ac026-240">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ac026-241"><strong>[会議 URI]</strong></span><span class="sxs-lookup"><span data-stu-id="ac026-241"><strong>Conference URI</strong></span></span></p></td>
<td><p><span data-ttu-id="ac026-242">可</span><span class="sxs-lookup"><span data-stu-id="ac026-242">Yes</span></span></p></td>
<td><p><span data-ttu-id="ac026-243">一意の電話会議 ID。</span><span class="sxs-lookup"><span data-stu-id="ac026-243">Unique conference identifier.</span></span> <span data-ttu-id="ac026-244">この項目をクリックすると、選択されているセッションの会議詳細レポートが表示されます。</span><span class="sxs-lookup"><span data-stu-id="ac026-244">When you click this item, the report shows you the Conference Detail Report for the selected session.</span></span> <span data-ttu-id="ac026-245">この項目を展開すると、電話会議参加者に関する情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="ac026-245">When you expand this item, the report shows you information about the conference participants.</span></span> <span data-ttu-id="ac026-246">詳細については&quot;、このトピックで&quot;後述する「会議の参加者の指標」セクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="ac026-246">For details, see the &quot;Metrics for Conference Participants&quot; section later in this topic.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ac026-247"><strong>[開催者]</strong></span><span class="sxs-lookup"><span data-stu-id="ac026-247"><strong>Organizer</strong></span></span></p></td>
<td><p><span data-ttu-id="ac026-248">はい</span><span class="sxs-lookup"><span data-stu-id="ac026-248">Yes</span></span></p></td>
<td><p><span data-ttu-id="ac026-249">会議を開催したユーザーの SIP アドレス。</span><span class="sxs-lookup"><span data-stu-id="ac026-249">SIP address of the user who organized the conference.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ac026-250"><strong>プール</strong></span><span class="sxs-lookup"><span data-stu-id="ac026-250"><strong>Pool</strong></span></span></p></td>
<td><p><span data-ttu-id="ac026-251">可</span><span class="sxs-lookup"><span data-stu-id="ac026-251">Yes</span></span></p></td>
<td><p><span data-ttu-id="ac026-252">電話会議で使用されたエッジ サーバーの名前 (エッジ サーバーが使用された場合)。</span><span class="sxs-lookup"><span data-stu-id="ac026-252">Name of the Edge Server (if any) used in the conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ac026-253"><strong>[開始時刻]</strong></span><span class="sxs-lookup"><span data-stu-id="ac026-253"><strong>Start time</strong></span></span></p></td>
<td><p><span data-ttu-id="ac026-254">はい</span><span class="sxs-lookup"><span data-stu-id="ac026-254">Yes</span></span></p></td>
<td><p><span data-ttu-id="ac026-255">会議が開始された日時。</span><span class="sxs-lookup"><span data-stu-id="ac026-255">Date and time that the conference began.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ac026-256"><strong>[終了時刻]</strong></span><span class="sxs-lookup"><span data-stu-id="ac026-256"><strong>End time</strong></span></span></p></td>
<td><p><span data-ttu-id="ac026-257">はい</span><span class="sxs-lookup"><span data-stu-id="ac026-257">Yes</span></span></p></td>
<td><p><span data-ttu-id="ac026-258">会議が終了した日時。</span><span class="sxs-lookup"><span data-stu-id="ac026-258">Date and time that the conference ended.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-conference-participants"></a><span data-ttu-id="ac026-259">電話会議参加者の指標</span><span class="sxs-lookup"><span data-stu-id="ac026-259">Metrics for conference participants</span></span>

<span data-ttu-id="ac026-260">次の表に、各電話会議参加者についてユーザー アクティビティ レポートで提供される情報を示します。</span><span class="sxs-lookup"><span data-stu-id="ac026-260">The following table lists the information provided in the User Activity Report provides for each participant in a conference.</span></span>

### <a name="metrics-for-conference-participants"></a><span data-ttu-id="ac026-261">電話会議参加者の指標</span><span class="sxs-lookup"><span data-stu-id="ac026-261">Metrics for conference participants</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="ac026-262">名前</span><span class="sxs-lookup"><span data-stu-id="ac026-262">Name</span></span></th>
<th><span data-ttu-id="ac026-263">この項目での並べ替え</span><span class="sxs-lookup"><span data-stu-id="ac026-263">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="ac026-264">説明</span><span class="sxs-lookup"><span data-stu-id="ac026-264">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ac026-265"><strong>役割</strong></span><span class="sxs-lookup"><span data-stu-id="ac026-265"><strong>Role</strong></span></span></p></td>
<td><p><span data-ttu-id="ac026-266">いいえ</span><span class="sxs-lookup"><span data-stu-id="ac026-266">No</span></span></p></td>
<td><p><span data-ttu-id="ac026-267">電話会議におけるユーザーの役割 (発表者など)。</span><span class="sxs-lookup"><span data-stu-id="ac026-267">Conference role (for example, Presenter) for the user.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ac026-268"><strong>[参加者]</strong></span><span class="sxs-lookup"><span data-stu-id="ac026-268"><strong>Participant</strong></span></span></p></td>
<td><p><span data-ttu-id="ac026-269">いいえ</span><span class="sxs-lookup"><span data-stu-id="ac026-269">No</span></span></p></td>
<td><p><span data-ttu-id="ac026-270">ユーザーの SIP アドレス。</span><span class="sxs-lookup"><span data-stu-id="ac026-270">SIP address of the user.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ac026-271"><strong>[接続]</strong></span><span class="sxs-lookup"><span data-stu-id="ac026-271"><strong>Connectivity</strong></span></span></p></td>
<td><p><span data-ttu-id="ac026-272">不可</span><span class="sxs-lookup"><span data-stu-id="ac026-272">No</span></span></p></td>
<td><p><span data-ttu-id="ac026-273">ネットワーク接続の種類。</span><span class="sxs-lookup"><span data-stu-id="ac026-273">Network connection type.</span></span> <span data-ttu-id="ac026-274">たとえば、 &quot;内部接続&quot;の場合や&quot;PSTN&quot;からダイヤルインユーザーの場合などです。</span><span class="sxs-lookup"><span data-stu-id="ac026-274">For example &quot;From Internal&quot; for internal connection or &quot;From PSTN&quot; for dial-in users.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ac026-275"><strong>[参加時間]</strong></span><span class="sxs-lookup"><span data-stu-id="ac026-275"><strong>Join time</strong></span></span></p></td>
<td><p><span data-ttu-id="ac026-276">いいえ</span><span class="sxs-lookup"><span data-stu-id="ac026-276">No</span></span></p></td>
<td><p><span data-ttu-id="ac026-277">ユーザーが電話会議に参加した日時。</span><span class="sxs-lookup"><span data-stu-id="ac026-277">Date and time that the user joined the conference.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ac026-278"><strong>[退場時間]</strong></span><span class="sxs-lookup"><span data-stu-id="ac026-278"><strong>Leave time</strong></span></span></p></td>
<td><p><span data-ttu-id="ac026-279">不可</span><span class="sxs-lookup"><span data-stu-id="ac026-279">No</span></span></p></td>
<td><p><span data-ttu-id="ac026-280">ユーザーが電話会議から退場した日時。</span><span class="sxs-lookup"><span data-stu-id="ac026-280">Date and time that the user left the conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ac026-281"><strong>[診断 ID]</strong></span><span class="sxs-lookup"><span data-stu-id="ac026-281"><strong>Diagnostic ID</strong></span></span></p></td>
<td><p><span data-ttu-id="ac026-282">いいえ</span><span class="sxs-lookup"><span data-stu-id="ac026-282">No</span></span></p></td>
<td><p><span data-ttu-id="ac026-p125">SIP メッセージに添付される一意の識別子 (ms-diagnostics ヘッダー形式)。その情報は、多くの場合、エラーのトラブルシューティングに役立ちます。診断ヘッダーはオプションで (このヘッダーを含まない SIP セッションがある可能性もあります)、診断 ID は、何らかの問題が生じたセッションについてのみ報告されます。</span><span class="sxs-lookup"><span data-stu-id="ac026-p125">Unique identifier (in the form of an ms-diagnostics header) attached to a SIP message that often provides information useful in troubleshooting errors. Diagnostics headers are optional (it is possible to have SIP sessions that do not include these headers), and diagnostic IDs are reported only for sessions that experienced problems of some kind.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

