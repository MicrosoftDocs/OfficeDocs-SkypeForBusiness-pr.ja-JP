---
title: 'Lync Server 2013: ユーザーアクティビティレポート'
description: 'Lync Server 2013: ユーザーアクティビティレポート。'
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
ms.openlocfilehash: 0e959020e6ace6c72ecd570039d30a9ecc174c82
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48569833"
---
# <a name="user-activity-report-in-lync-server-2013"></a><span data-ttu-id="3dbdd-103">Lync Server 2013 のユーザーアクティビティレポート</span><span class="sxs-lookup"><span data-stu-id="3dbdd-103">User Activity Report in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3dbdd-104">_**トピックの最終更新日:** 2015-02-27_</span><span class="sxs-lookup"><span data-stu-id="3dbdd-104">_**Topic Last Modified:** 2015-02-27_</span></span>

<span data-ttu-id="3dbdd-p101">ユーザー アクティビティ レポートは、特定の期間にユーザーによって実行されたピアツーピアおよび電話会議セッションの詳細な一覧を示します。多くの監視レポートとは異なり、ユーザー アクティビティ レポートは、各呼び出しを個別のユーザーに関連付けます。たとえば、ピアツーピアセッションでは、呼び出しを開始した人 (呼び出し元ユーザー) と呼び出しを受けた人 (呼び出し先ユーザー) の SIP URI が示されます。電話会議の情報を展開すると、すべての電話会議の参加者と、その電話会議における参加者の役割の一覧が表示されます。</span><span class="sxs-lookup"><span data-stu-id="3dbdd-p101">The User Activity Report provides a detailed list of the peer-to-peer and conferencing sessions carried out by your users in a given time period. Unlike many of the Monitoring Reports, the User Activity Report ties each call to individual users. For example, peer-to-peer sessions specify the SIP URIs of the person who initiated the call (the From user) and the person who was being called (the To user). If you expand the information for a conference, you'll see a list of all the conference participants and the role they held for that conference.</span></span>

<span data-ttu-id="3dbdd-p102">ユーザー アクティビティ レポートは、"ヘルプ デスク" レポートと呼ばれることがあります。ヘルプデスク担当者が、特定のユーザーに関するセッション情報を取得するときによくこのレポートを利用するからです。個別のユーザーに対する、または個別のユーザーによる呼び出しは、[ユーザー URI プレフィックス] ボックスにユーザーの SIP URI を入力するだけでフィルターできます。</span><span class="sxs-lookup"><span data-stu-id="3dbdd-p102">The User Activity Report is sometimes referred to as the "help desk" report. That's because the report is often used by help desk personnel to retrieve session information for a specific user. You can filter for calls made to or made by an individual user simply by typing the user's SIP URI in the User URI prefix box.</span></span>

<span data-ttu-id="3dbdd-112">この操作を行うと、ユーザー アクティビティ レポートは、SIP URI が指定した文字列で始まるユーザーに関する情報を返します。</span><span class="sxs-lookup"><span data-stu-id="3dbdd-112">If you do this, the User Activity Report will return information for any user whose SIP URI begins with the specified string.</span></span> <span data-ttu-id="3dbdd-113">たとえば、[URI] ボックスに **ken** と入力すると、ユーザー アクティビティ レポートは **Ken**.Myer@litwareinc.com を検索します。</span><span class="sxs-lookup"><span data-stu-id="3dbdd-113">For example, if you type **ken** in the URI box, the User Activity Report will locate **Ken**.Myer@litwareinc.com.</span></span> <span data-ttu-id="3dbdd-114">ただし、次のようなユーザーも検索します。</span><span class="sxs-lookup"><span data-stu-id="3dbdd-114">However, it will also locate these users:</span></span>

  - <span data-ttu-id="3dbdd-115">**ken**azi@litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="3dbdd-115">**ken**azi@litwareinc.com</span></span>

  - <span data-ttu-id="3dbdd-116">**ken**burg@litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="3dbdd-116">**ken**burg@litwareinc.com</span></span>

  - <span data-ttu-id="3dbdd-117">**Ken**.Sanchez@litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="3dbdd-117">**Ken**.Sanchez@litwareinc.com</span></span>

  - <span data-ttu-id="3dbdd-118">**Ken**nedy@litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="3dbdd-118">**Ken**nedy@litwareinc.com</span></span>

<span data-ttu-id="3dbdd-119">Ken Myer の情報のみが返されるようにするには、検索ボックスに完全な URI (Ken.Myer@litwareinc.com) を入力するか、組織内の他のユーザーと個人を区別するために、少なくとも Ken の適切な種類の Ken の URI を入力します。</span><span class="sxs-lookup"><span data-stu-id="3dbdd-119">To ensure that information only for Ken Myer is returned, either type his full URI (Ken.Myer@litwareinc.com) in the search box or at least enough type of Ken’s URI to uniquely distinguish him from other users in your organization.</span></span> <span data-ttu-id="3dbdd-120">たとえば、次のようにします。</span><span class="sxs-lookup"><span data-stu-id="3dbdd-120">For example:</span></span>

<span data-ttu-id="3dbdd-121">Ken.my</span><span class="sxs-lookup"><span data-stu-id="3dbdd-121">Ken.my</span></span>

<div>

## <a name="to-access-the-user-activity-report"></a><span data-ttu-id="3dbdd-122">ユーザー アクティビティ レポートにアクセスするには</span><span class="sxs-lookup"><span data-stu-id="3dbdd-122">To access the user activity report</span></span>

<span data-ttu-id="3dbdd-123">ユーザー アクティビティ レポートには、[監視レポート] ホーム ページからアクセスします。</span><span class="sxs-lookup"><span data-stu-id="3dbdd-123">The User Activity Report is accessed from the Monitoring Reports home page.</span></span> <span data-ttu-id="3dbdd-124">また、 [Lync Server 2013 の IP 電話インベントリレポート](lync-server-2013-ip-phone-inventory-report.md)でユーザー URI 指標をクリックして、ユーザーアクティビティレポートにアクセスすることもできます。</span><span class="sxs-lookup"><span data-stu-id="3dbdd-124">You can also reach the User Activity Report by clicking the User URI metric on the [IP Phone Inventory Report in Lync Server 2013](lync-server-2013-ip-phone-inventory-report.md).</span></span> <span data-ttu-id="3dbdd-125">ユーザー アクティビティ レポート内で、会議 URI (会議用) をクリックすると、会議の詳細レポートが表示されます。</span><span class="sxs-lookup"><span data-stu-id="3dbdd-125">From within the User Activity Report, clicking the Conference URI (for a conference) takes you to the Conference Detail Report.</span></span> <span data-ttu-id="3dbdd-126">同様に、ピアツーピア呼び出しの詳細指標をクリックすると、 [Lync Server 2013 のピアツーピアセッション詳細レポート](lync-server-2013-peer-to-peer-session-detail-report.md)が表示されます。</span><span class="sxs-lookup"><span data-stu-id="3dbdd-126">Similarly, clicking the Detail metric for a peer-to-peer call takes you to the [Peer-to-Peer Session Detail Report in Lync Server 2013](lync-server-2013-peer-to-peer-session-detail-report.md).</span></span>

</div>

<div>

## <a name="making-the-best-use-of-the-user-activity-report"></a><span data-ttu-id="3dbdd-127">ユーザー アクティビティ レポートを最大限活用する</span><span class="sxs-lookup"><span data-stu-id="3dbdd-127">Making the best use of the user activity report</span></span>

<span data-ttu-id="3dbdd-128">ユーザー アクティビティ レポートには、多くの良質な情報が含まれていますが、この情報は見つけにくい場合があります。</span><span class="sxs-lookup"><span data-stu-id="3dbdd-128">Although there is a lot of good information in the User Activity Report, that information can sometimes be difficult to locate.</span></span> <span data-ttu-id="3dbdd-129">たとえば、指定した期間中に組織内で発生するすべてのユーザーアクティビティが、ユーザーアクティビティレポートに含まれています。つまり、何らかの方法で Microsoft Lync Server 2013 を実際に使用したユーザーに関する情報をレポート内に埋め込むことができることを意味します。</span><span class="sxs-lookup"><span data-stu-id="3dbdd-129">For example, all the user activity that takes place in your organization during a specified period is included in the User Activity Report; that means that, buried, within the report is information about which users actually used Microsoft Lync Server 2013 in some way.</span></span>

<div>


> [!WARNING]  
> <span data-ttu-id="3dbdd-130">技術的には、一部のユーザーアクティビティが記録になる可能性があります。 Lync Server は、すべての電話呼び出しに関する情報を保存しようとしていますが、その呼び出しについての情報がないと、データベースへの呼び出しが行われている可能性があります。</span><span class="sxs-lookup"><span data-stu-id="3dbdd-130">Technically, it’s possible that some user activity might go unrecorded: while Lync Server strives to keep information about all phone calls it's possible that a call could have been made without the information about that call being written to the database.</span></span> <span data-ttu-id="3dbdd-131">Lync Server は、非常に正確ですが、Lync Server 2013 がどのように使用されているかについては、必ずしもわかりません。</span><span class="sxs-lookup"><span data-stu-id="3dbdd-131">Lync Server is designed to give an extremely accurate but not necessarily perfect look at how Lync Server 2013 is being used.</span></span> <span data-ttu-id="3dbdd-132">(つまり、すべての通話の100% が記録されるという保証はありません。 Lync Server の監視を課金システムとして使用してはならない理由について説明します)。</span><span class="sxs-lookup"><span data-stu-id="3dbdd-132">(The fact that there is no guarantee that 100% of all calls are recorded explains why Lync Server monitoring should not be used as a billing system.)</span></span><BR><span data-ttu-id="3dbdd-p108">また、監視レポートに表示できるのは最大でも 1,000 レコードです。これは、ユーザー アクティビティの量と作業時間によっては、データベースに実際に格納されたデータの一部がクエリでは返されない場合があることを意味します。</span><span class="sxs-lookup"><span data-stu-id="3dbdd-p108">Second, a Monitoring Report report can only display, at most, 1,000 records. Depending on the amount of user activity you have, and depending on the time period you are working with, that means your query might not return all the data actually stored in the database.</span></span>



</div>

  - <span data-ttu-id="3dbdd-135">この期間内にシステムを実際に使用したのはどのユーザーか。</span><span class="sxs-lookup"><span data-stu-id="3dbdd-135">Which users actually used the system during this time period?</span></span>

  - <span data-ttu-id="3dbdd-136">この期間内に最もアクティブだったのはどのユーザーか。</span><span class="sxs-lookup"><span data-stu-id="3dbdd-136">Which of my users were the most active during this time period?</span></span>

  - <span data-ttu-id="3dbdd-137">通話数が最も多いユーザーが、最も多くのインスタント メッセージング セッションに参加しているユーザーでもあるかどうか。</span><span class="sxs-lookup"><span data-stu-id="3dbdd-137">Are the users who make the most phone calls also the users who participate in the most instant messaging sessions?</span></span>

<span data-ttu-id="3dbdd-138">このような情報を確認するには、監視レポートで取得されたデータを Excel スプレッドシートにエクスポートします。</span><span class="sxs-lookup"><span data-stu-id="3dbdd-138">If you need to answer questions like this, you can export the data retrieved by the Monitoring Reports to an Excel spreadsheet.</span></span> <span data-ttu-id="3dbdd-139">次に、そのスプレッドシート/コンマ区切り値ファイルを使用して、ユーザー アクティビティ レポートのようなやり方でデータを分析します。</span><span class="sxs-lookup"><span data-stu-id="3dbdd-139">You then use that spreadsheet and/or a comma-separated values file to analyze the data in ways that the User Activity Report.</span></span> <span data-ttu-id="3dbdd-140">たとえば、レポートデータを Excel にエクスポートしてから、コンマ区切り値ファイルにエクスポートするとします。</span><span class="sxs-lookup"><span data-stu-id="3dbdd-140">For example, suppose you have exported the report data to Excel and then to a comma-separated values file.</span></span> <span data-ttu-id="3dbdd-141">この時点で、次のようなコマンドを使用することで、データを .CSV ファイルから Windows PowerShell にインポートできます。</span><span class="sxs-lookup"><span data-stu-id="3dbdd-141">At that point, you can import the data from the .CSV file to Windows PowerShell by using a command similar to this:</span></span>

    $x = Import-Csv -Path "C:\Data\User_Activity_Report.csv"

<span data-ttu-id="3dbdd-142">データがインポートされたら、簡単な Windows PowerShell コマンドを使用して質問に回答する場合に役立てることができます。</span><span class="sxs-lookup"><span data-stu-id="3dbdd-142">After the data has been imported you can then use simple Windows PowerShell commands to help answer your questions.</span></span> <span data-ttu-id="3dbdd-143">たとえば、次のコマンドは、少なくとも 1 つのセッションで "呼び出し元" ユーザーとしての役割を果たす一意のユーザーの一覧を返します。</span><span class="sxs-lookup"><span data-stu-id="3dbdd-143">For example, this command returns a list of unique users who served as the "From user" in at least one session:</span></span>

    $x | Group-Object "From user" | Select Name | Sort-Object Name

<span data-ttu-id="3dbdd-144">つまり、次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="3dbdd-144">In other words:</span></span>

    Name
    ----
    David.Ahs@litwareinc.com
    Gilead.Amosnino@litwareinc.com
    Henrik.Jensen@litwareinc.com
    Ken.Myer@litwareinc.com
    Pilar.Ackerman@litwareinc.com

<span data-ttu-id="3dbdd-145">次のコマンドは、ユーザーが参加しているセッションの合計数に基づいて、一意のユーザーの一覧を表示します。</span><span class="sxs-lookup"><span data-stu-id="3dbdd-145">This command lists the unique users (based on the total number of sessions that they participated in:</span></span>

    $x | Group-Object "From user" | Select Count, Name | Sort-Object Count -Descending

<span data-ttu-id="3dbdd-146">このコマンドによって、以下のようなデータが返されます。</span><span class="sxs-lookup"><span data-stu-id="3dbdd-146">That returns data similar to this:</span></span>

    Count    Name
    -----    ----
      523    Ken.Myer@litwareinc.com
       63    David.Ahs@litwareinc.com
       29    Pilar.Ackerman@litwareinc.com
       17    Gilead.Amosnino@litwareinc.com
       10    Henrik.Jensen@litwareinc.com

<span data-ttu-id="3dbdd-147">次のコマンドは、報告されたセッションを、モダリティとしてオーディオが含まれるセッションに制限します。</span><span class="sxs-lookup"><span data-stu-id="3dbdd-147">This command limits the reported sessions to those that included audio as a modality:</span></span>

    $x | Where-Object {$_.Modalities -match "audio"} | Group-Object "From user" | Select Count, Name | Sort-Object Count -Descending

<span data-ttu-id="3dbdd-148">レポートに表示されている診断 ID の上にマウスを置くと、その ID について説明するヒントが表示されます。</span><span class="sxs-lookup"><span data-stu-id="3dbdd-148">If you hold your mouse over any Diagnostic ID shown on the report, a tooltip will appear describing that ID.</span></span>

</div>

<div>

## <a name="filters"></a><span data-ttu-id="3dbdd-149">フィルター</span><span class="sxs-lookup"><span data-stu-id="3dbdd-149">Filters</span></span>

<span data-ttu-id="3dbdd-p111">フィルターは、必要なデータのみに絞り込んだデータ セットを取得したり、取得したデータを別の方法で表示したりする方法として利用できます。たとえば、ユーザー アクティビティ レポートを使用すると、取得したデータに動作状況の種類 (ピアツーピア セッションまたは電話会議セッション) などに基づいてフィルターを適用できます。また、ユーザーの SIP アドレスによってフィルターを適用することもできます (この場合、1 人のユーザーの動作状況を表示できます)。データをグループ化する方法を選択することもできます。この場合、使用状況は、時間単位、日単位、週単位、または月単位でグループ化されます。</span><span class="sxs-lookup"><span data-stu-id="3dbdd-p111">Filters provide a way for you to return a more finely-targeted set of data or to view the returned data in different ways. For example, the User Activity Report enables you to filter the returned data based on such things as activity type (that is, peer-to-peer sessions or conferencing sessions) or by the user's SIP address (allowing you to view the activities for one user). You can also choose how data should be grouped. In this case, usages are grouped by hour, day, week, or month.</span></span>

<span data-ttu-id="3dbdd-154">次の表に、ユーザー アクティビティ レポートで使用できるフィルターを示します。</span><span class="sxs-lookup"><span data-stu-id="3dbdd-154">The following table lists the filters that you can use with the User Activity Report.</span></span>

### <a name="user-activity-report-filters"></a><span data-ttu-id="3dbdd-155">ユーザー アクティビティ レポートのフィルター</span><span class="sxs-lookup"><span data-stu-id="3dbdd-155">User activity report filters</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="3dbdd-156">名前</span><span class="sxs-lookup"><span data-stu-id="3dbdd-156">Name</span></span></th>
<th><span data-ttu-id="3dbdd-157">説明</span><span class="sxs-lookup"><span data-stu-id="3dbdd-157">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="3dbdd-158"><strong>From</strong></span><span class="sxs-lookup"><span data-stu-id="3dbdd-158"><strong>From</strong></span></span></p></td>
<td><p><span data-ttu-id="3dbdd-p112">時間範囲の開始日と開始時刻。データを時間単位で表示するには、次のように開始日と開始時刻の両方を入力します。</span><span class="sxs-lookup"><span data-stu-id="3dbdd-p112">Start date/time for the time range. To view data by hours, enter both the start date and time as follows:</span></span></p>
<p><span data-ttu-id="3dbdd-161">7/17/2012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="3dbdd-161">7/17/12012 1:00 PM</span></span></p>
<p><span data-ttu-id="3dbdd-p113">開始時刻を入力しないと、レポートは自動的に指定日の午前 12:00 に開始します。データを日単位で表示するには、次のように日付のみを入力します。</span><span class="sxs-lookup"><span data-stu-id="3dbdd-p113">If you do not enter a start time, the report automatically begins at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="3dbdd-164">7/17/12012</span><span class="sxs-lookup"><span data-stu-id="3dbdd-164">7/17/12012</span></span></p>
<p><span data-ttu-id="3dbdd-165">週単位または月単位で表示するには、表示する週または月の任意の日付を入力します (その週または月の最初の日である必要はありません)。</span><span class="sxs-lookup"><span data-stu-id="3dbdd-165">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="3dbdd-166">7/13/2012</span><span class="sxs-lookup"><span data-stu-id="3dbdd-166">7/13/2012</span></span></p>
<p><span data-ttu-id="3dbdd-167">週は、常に日曜日から土曜日までです。</span><span class="sxs-lookup"><span data-stu-id="3dbdd-167">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3dbdd-168"><strong>To</strong></span><span class="sxs-lookup"><span data-stu-id="3dbdd-168"><strong>To</strong></span></span></p></td>
<td><p><span data-ttu-id="3dbdd-p114">時間範囲の終了日と終了時刻。データを時間単位で表示するには、次のように終了日と終了時刻の両方を入力します。</span><span class="sxs-lookup"><span data-stu-id="3dbdd-p114">End date/time for the time range. To view data by hours, enter both the end date and time as follows:</span></span></p>
<p><span data-ttu-id="3dbdd-171">7/17/2012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="3dbdd-171">7/17/12012 1:00 PM</span></span></p>
<p><span data-ttu-id="3dbdd-p115">終了時刻を入力しないと、レポートは自動的に指定日の午前 12:00 に終了します。データを日単位で表示するには、次のように日付のみを入力します。</span><span class="sxs-lookup"><span data-stu-id="3dbdd-p115">If you do not enter an end time, the report automatically ends at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="3dbdd-174">7/17/12012</span><span class="sxs-lookup"><span data-stu-id="3dbdd-174">7/17/12012</span></span></p>
<p><span data-ttu-id="3dbdd-175">週単位または月単位で表示するには、表示する週または月の任意の日付を入力します (その週または月の最初の日である必要はありません)。</span><span class="sxs-lookup"><span data-stu-id="3dbdd-175">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="3dbdd-176">7/13/2012</span><span class="sxs-lookup"><span data-stu-id="3dbdd-176">7/13/2012</span></span></p>
<p><span data-ttu-id="3dbdd-177">一週間は、日曜日から始まり、土曜日で終わるものとします。</span><span class="sxs-lookup"><span data-stu-id="3dbdd-177">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3dbdd-178"><strong>アクティビティの種類</strong></span><span class="sxs-lookup"><span data-stu-id="3dbdd-178"><strong>Activity type</strong></span></span></p></td>
<td><p><span data-ttu-id="3dbdd-p116">動作状況の種類。次のいずれかを選択します。</span><span class="sxs-lookup"><span data-stu-id="3dbdd-p116">Type of activity. Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="3dbdd-181">[All]</span><span class="sxs-lookup"><span data-stu-id="3dbdd-181">[All]</span></span></p></li>
<li><p><span data-ttu-id="3dbdd-182">ピアツーピア</span><span class="sxs-lookup"><span data-stu-id="3dbdd-182">Peer-to-peer</span></span></p></li>
<li><p><span data-ttu-id="3dbdd-183">会議</span><span class="sxs-lookup"><span data-stu-id="3dbdd-183">Conference</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3dbdd-184"><strong>モダリティ</strong></span><span class="sxs-lookup"><span data-stu-id="3dbdd-184"><strong>Modality</strong></span></span></p></td>
<td><p><span data-ttu-id="3dbdd-185">使用可能なモダリティは、選択するアクティビティの種類によって異なります。</span><span class="sxs-lookup"><span data-stu-id="3dbdd-185">The Modality available to you varies depending on the select Activity Type.</span></span> <span data-ttu-id="3dbdd-186">アクティビティの種類がピアツーピアの場合、モダリティとして IM、ファイル転送、アプリケーションの共有、音声、またはビデオを選択することが可能です。</span><span class="sxs-lookup"><span data-stu-id="3dbdd-186">If the Activity Type is Peer-to-Peer, you can select IM; File Transfer; Application Sharing; Voice; or Video as the modality.</span></span></p>
<p><span data-ttu-id="3dbdd-187">アクティビティの種類が会議の場合、IM 電話会議、Web 会議、アプリケーションの共有、音声/ビデオ会議、またはテレフォニー会議を選択可能です。</span><span class="sxs-lookup"><span data-stu-id="3dbdd-187">If the Activity Type is Conference, you can select IM Phone conference; Web conference; Application Sharing; Voice/Video conference; or Telephony conference.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3dbdd-188">[<strong>セッション カテゴリ</strong>]</span><span class="sxs-lookup"><span data-stu-id="3dbdd-188"><strong>Session category</strong></span></span></p></td>
<td><p><span data-ttu-id="3dbdd-p118">問題のアクティビティが成功したか失敗したかを示します。次のいずれかを選択します。</span><span class="sxs-lookup"><span data-stu-id="3dbdd-p118">Indicates whether the activity in question succeeded or failed. Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="3dbdd-191">[All]</span><span class="sxs-lookup"><span data-stu-id="3dbdd-191">[All]</span></span></p></li>
<li><p><span data-ttu-id="3dbdd-192">成功</span><span class="sxs-lookup"><span data-stu-id="3dbdd-192">Success</span></span></p></li>
<li><p><span data-ttu-id="3dbdd-193">[予期されたエラー]</span><span class="sxs-lookup"><span data-stu-id="3dbdd-193">Expected failure</span></span></p></li>
<li><p><span data-ttu-id="3dbdd-194">[予期しないエラー]</span><span class="sxs-lookup"><span data-stu-id="3dbdd-194">Unexpected failure</span></span></p></li>
</ul>
<p><span data-ttu-id="3dbdd-195">&quot;予期 &quot; されるエラーは、発生する可能性のあるエラーです。たとえば、ユーザーが自分の状態を [応答不可] に設定している場合は、そのユーザーへの呼び出しが失敗することが予想されます。</span><span class="sxs-lookup"><span data-stu-id="3dbdd-195">An &quot;expected failure&quot; is a failure that is expected to happen; for example, if a user has set his or her status to Do Not Disturb you would expect any call to that user to fail.</span></span> <span data-ttu-id="3dbdd-196">&quot;予期しないエラーと &quot; は、正常なシステムとして表示されるエラーです。</span><span class="sxs-lookup"><span data-stu-id="3dbdd-196">An &quot;unexpected failure&quot; is a failure that occurs in what would appear to be an otherwise healthy system.</span></span> <span data-ttu-id="3dbdd-197">たとえば、発信者が保留にされたときに、通話が終了してはなりません。</span><span class="sxs-lookup"><span data-stu-id="3dbdd-197">For example, a call should not be terminated if the caller is placed on hold.</span></span> <span data-ttu-id="3dbdd-198">そのような状態が発生する場合は、予期しないエラーとしてフラグが設定されます。</span><span class="sxs-lookup"><span data-stu-id="3dbdd-198">If that occurs, that would be flagged as an unexpected failure.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3dbdd-199">[<strong>ユーザー URI プレフィックス</strong>]</span><span class="sxs-lookup"><span data-stu-id="3dbdd-199"><strong>User URI prefix</strong></span></span></p></td>
<td><p><span data-ttu-id="3dbdd-p120">ユーザーの SIP アドレス。たとえば、Ken Myer という名前のユーザーのレコードのみを表示するには、次のように、Ken Myer の SIP アドレスを入力する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3dbdd-p120">SIP address for the user. To view records only for the user Ken Myer you need to enter Ken Myer's SIP address. For example:</span></span></p>
<p><span data-ttu-id="3dbdd-203">sip:kenmyer@litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="3dbdd-203">sip:kenmyer@litwareinc.com</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-peer-to-peer-sessions"></a><span data-ttu-id="3dbdd-204">ピアツーピア セッションの指標</span><span class="sxs-lookup"><span data-stu-id="3dbdd-204">Metrics for peer-to-peer sessions</span></span>

<span data-ttu-id="3dbdd-205">次の表に、ピアツーピア セッション (2 人の参加者だけで行うセッション) について、ユーザー アクティビティ レポートで提供される情報を示します。</span><span class="sxs-lookup"><span data-stu-id="3dbdd-205">The following table lists the information provided in the User Activity Report for peer-to-peer sessions (that is, sessions involving just two participants).</span></span>

### <a name="metrics-for-peer-to-peer-sessions"></a><span data-ttu-id="3dbdd-206">ピアツーピア セッションの指標</span><span class="sxs-lookup"><span data-stu-id="3dbdd-206">Metrics for peer-to-peer sessions</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="3dbdd-207">名前</span><span class="sxs-lookup"><span data-stu-id="3dbdd-207">Name</span></span></th>
<th><span data-ttu-id="3dbdd-208">この項目での並べ替え</span><span class="sxs-lookup"><span data-stu-id="3dbdd-208">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="3dbdd-209">説明</span><span class="sxs-lookup"><span data-stu-id="3dbdd-209">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="3dbdd-210"><strong>詳細</strong></span><span class="sxs-lookup"><span data-stu-id="3dbdd-210"><strong>Detail</strong></span></span></p></td>
<td><p><span data-ttu-id="3dbdd-211">いいえ</span><span class="sxs-lookup"><span data-stu-id="3dbdd-211">No</span></span></p></td>
<td><p><span data-ttu-id="3dbdd-212">この項目をクリックすると、選択されているセッションのピアツーピア セッション詳細レポートが表示されます。</span><span class="sxs-lookup"><span data-stu-id="3dbdd-212">When you click this item, the report shows you the Peer-to-Peer Session Detail Report for the selected session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3dbdd-213">[<strong>移動元ユーザー</strong>]</span><span class="sxs-lookup"><span data-stu-id="3dbdd-213"><strong>From user</strong></span></span></p></td>
<td><p><span data-ttu-id="3dbdd-214">はい</span><span class="sxs-lookup"><span data-stu-id="3dbdd-214">Yes</span></span></p></td>
<td><p><span data-ttu-id="3dbdd-215">ピアツーピア セッションを開始したユーザーの SIP アドレス。</span><span class="sxs-lookup"><span data-stu-id="3dbdd-215">SIP address of the user who initiated the peer-to-peer session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3dbdd-216">[<strong>対象ユーザー</strong>]</span><span class="sxs-lookup"><span data-stu-id="3dbdd-216"><strong>To user</strong></span></span></p></td>
<td><p><span data-ttu-id="3dbdd-217">はい</span><span class="sxs-lookup"><span data-stu-id="3dbdd-217">Yes</span></span></p></td>
<td><p><span data-ttu-id="3dbdd-218">ピアツーピア セッションに参加したユーザーの SIP アドレス。</span><span class="sxs-lookup"><span data-stu-id="3dbdd-218">SIP address of the user who joined the peer-to-peer session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3dbdd-219"><strong>モダリティ</strong></span><span class="sxs-lookup"><span data-stu-id="3dbdd-219"><strong>Modalities</strong></span></span></p></td>
<td><p><span data-ttu-id="3dbdd-220">はい</span><span class="sxs-lookup"><span data-stu-id="3dbdd-220">Yes</span></span></p></td>
<td><p><span data-ttu-id="3dbdd-p121">セッションで使用された通信の種類。たとえば、IM、音声、ファイル送信。</span><span class="sxs-lookup"><span data-stu-id="3dbdd-p121">Type of communication used in the session. For example, IM, audio, or file transfer.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3dbdd-223">[<strong>招待時間</strong>]</span><span class="sxs-lookup"><span data-stu-id="3dbdd-223"><strong>Invite time</strong></span></span></p></td>
<td><p><span data-ttu-id="3dbdd-224">はい</span><span class="sxs-lookup"><span data-stu-id="3dbdd-224">Yes</span></span></p></td>
<td><p><span data-ttu-id="3dbdd-225">ピアツーピア セッションへの最初の招待が送信された日時。</span><span class="sxs-lookup"><span data-stu-id="3dbdd-225">Date and time the initial invitation to join the peer-to-peer session was sent.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3dbdd-226">[<strong>応答時間</strong>]</span><span class="sxs-lookup"><span data-stu-id="3dbdd-226"><strong>Response time</strong></span></span></p></td>
<td><p><span data-ttu-id="3dbdd-227">はい</span><span class="sxs-lookup"><span data-stu-id="3dbdd-227">Yes</span></span></p></td>
<td><p><span data-ttu-id="3dbdd-228">ユーザーがセッションへの &quot; 招待を受け入れた日時 &quot; 。</span><span class="sxs-lookup"><span data-stu-id="3dbdd-228">Date and time that the &quot;To&quot; user accepted the session invitation.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3dbdd-229"><strong>終了時刻</strong></span><span class="sxs-lookup"><span data-stu-id="3dbdd-229"><strong>End time</strong></span></span></p></td>
<td><p><span data-ttu-id="3dbdd-230">はい</span><span class="sxs-lookup"><span data-stu-id="3dbdd-230">Yes</span></span></p></td>
<td><p><span data-ttu-id="3dbdd-231">ピアツーピア セッションが終了した日時。</span><span class="sxs-lookup"><span data-stu-id="3dbdd-231">Date and time the peer-to-peer session ended.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3dbdd-232">[<strong>診断 ID</strong>]</span><span class="sxs-lookup"><span data-stu-id="3dbdd-232"><strong>Diagnostic ID</strong></span></span></p></td>
<td><p><span data-ttu-id="3dbdd-233">はい</span><span class="sxs-lookup"><span data-stu-id="3dbdd-233">Yes</span></span></p></td>
<td><p><span data-ttu-id="3dbdd-p122">SIP メッセージに添付される一意の識別子 (ms-diagnostics ヘッダー形式)。その情報は、多くの場合、エラーのトラブルシューティングに役立ちます。診断ヘッダーはオプションで (このヘッダーを含まない SIP セッションがある可能性もあります)、診断 ID は、何らかの問題が生じたセッションについてのみ報告されます。</span><span class="sxs-lookup"><span data-stu-id="3dbdd-p122">Unique identifier (in the form of an ms-diagnostics header) attached to a SIP message that often provides information useful in troubleshooting errors. Diagnostics headers are optional (it is possible to have SIP sessions that do not include these headers), and diagnostic IDs are reported only for sessions that experienced problems of some kind.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-conferencing-sessions"></a><span data-ttu-id="3dbdd-236">電話会議セッションの指標</span><span class="sxs-lookup"><span data-stu-id="3dbdd-236">Metrics for conferencing sessions</span></span>

<span data-ttu-id="3dbdd-237">次の表に、電話会議セッション (3 人以上の参加者で行うセッション) について、ユーザー アクティビティ レポートで提供される情報を示します。</span><span class="sxs-lookup"><span data-stu-id="3dbdd-237">The following table lists the information provided in the User Activity Report for conferencing sessions (that is, sessions involving three or more participants).</span></span>

### <a name="metrics-for-conferencing-sessions"></a><span data-ttu-id="3dbdd-238">電話会議セッションの指標</span><span class="sxs-lookup"><span data-stu-id="3dbdd-238">Metrics for conferencing sessions</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="3dbdd-239">名前</span><span class="sxs-lookup"><span data-stu-id="3dbdd-239">Name</span></span></th>
<th><span data-ttu-id="3dbdd-240">この項目での並べ替え</span><span class="sxs-lookup"><span data-stu-id="3dbdd-240">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="3dbdd-241">説明</span><span class="sxs-lookup"><span data-stu-id="3dbdd-241">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="3dbdd-242">[<strong>会議 URI</strong>]</span><span class="sxs-lookup"><span data-stu-id="3dbdd-242"><strong>Conference URI</strong></span></span></p></td>
<td><p><span data-ttu-id="3dbdd-243">はい</span><span class="sxs-lookup"><span data-stu-id="3dbdd-243">Yes</span></span></p></td>
<td><p><span data-ttu-id="3dbdd-244">一意の電話会議 ID。</span><span class="sxs-lookup"><span data-stu-id="3dbdd-244">Unique conference identifier.</span></span> <span data-ttu-id="3dbdd-245">この項目をクリックすると、選択されているセッションの会議詳細レポートが表示されます。</span><span class="sxs-lookup"><span data-stu-id="3dbdd-245">When you click this item, the report shows you the Conference Detail Report for the selected session.</span></span> <span data-ttu-id="3dbdd-246">この項目を展開すると、電話会議参加者に関する情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="3dbdd-246">When you expand this item, the report shows you information about the conference participants.</span></span> <span data-ttu-id="3dbdd-247">詳細については、 &quot; &quot; このトピックで後述する「電話会議の参加者の指標」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3dbdd-247">For details, see the &quot;Metrics for Conference Participants&quot; section later in this topic.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3dbdd-248"><strong>開催者</strong></span><span class="sxs-lookup"><span data-stu-id="3dbdd-248"><strong>Organizer</strong></span></span></p></td>
<td><p><span data-ttu-id="3dbdd-249">はい</span><span class="sxs-lookup"><span data-stu-id="3dbdd-249">Yes</span></span></p></td>
<td><p><span data-ttu-id="3dbdd-250">会議を開催したユーザーの SIP アドレス。</span><span class="sxs-lookup"><span data-stu-id="3dbdd-250">SIP address of the user who organized the conference.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3dbdd-251"><strong>Pool</strong></span><span class="sxs-lookup"><span data-stu-id="3dbdd-251"><strong>Pool</strong></span></span></p></td>
<td><p><span data-ttu-id="3dbdd-252">はい</span><span class="sxs-lookup"><span data-stu-id="3dbdd-252">Yes</span></span></p></td>
<td><p><span data-ttu-id="3dbdd-253">電話会議で使用されたエッジ サーバーの名前 (エッジ サーバーが使用された場合)。</span><span class="sxs-lookup"><span data-stu-id="3dbdd-253">Name of the Edge Server (if any) used in the conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3dbdd-254"><strong>開始時刻</strong></span><span class="sxs-lookup"><span data-stu-id="3dbdd-254"><strong>Start time</strong></span></span></p></td>
<td><p><span data-ttu-id="3dbdd-255">はい</span><span class="sxs-lookup"><span data-stu-id="3dbdd-255">Yes</span></span></p></td>
<td><p><span data-ttu-id="3dbdd-256">会議が開始された日時。</span><span class="sxs-lookup"><span data-stu-id="3dbdd-256">Date and time that the conference began.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3dbdd-257"><strong>終了時刻</strong></span><span class="sxs-lookup"><span data-stu-id="3dbdd-257"><strong>End time</strong></span></span></p></td>
<td><p><span data-ttu-id="3dbdd-258">はい</span><span class="sxs-lookup"><span data-stu-id="3dbdd-258">Yes</span></span></p></td>
<td><p><span data-ttu-id="3dbdd-259">会議が終了した日時。</span><span class="sxs-lookup"><span data-stu-id="3dbdd-259">Date and time that the conference ended.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-conference-participants"></a><span data-ttu-id="3dbdd-260">電話会議参加者の指標</span><span class="sxs-lookup"><span data-stu-id="3dbdd-260">Metrics for conference participants</span></span>

<span data-ttu-id="3dbdd-261">次の表に、各電話会議参加者についてユーザー アクティビティ レポートで提供される情報を示します。</span><span class="sxs-lookup"><span data-stu-id="3dbdd-261">The following table lists the information provided in the User Activity Report provides for each participant in a conference.</span></span>

### <a name="metrics-for-conference-participants"></a><span data-ttu-id="3dbdd-262">電話会議参加者の指標</span><span class="sxs-lookup"><span data-stu-id="3dbdd-262">Metrics for conference participants</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="3dbdd-263">名前</span><span class="sxs-lookup"><span data-stu-id="3dbdd-263">Name</span></span></th>
<th><span data-ttu-id="3dbdd-264">この項目での並べ替え</span><span class="sxs-lookup"><span data-stu-id="3dbdd-264">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="3dbdd-265">説明</span><span class="sxs-lookup"><span data-stu-id="3dbdd-265">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="3dbdd-266"><strong>役割</strong></span><span class="sxs-lookup"><span data-stu-id="3dbdd-266"><strong>Role</strong></span></span></p></td>
<td><p><span data-ttu-id="3dbdd-267">いいえ</span><span class="sxs-lookup"><span data-stu-id="3dbdd-267">No</span></span></p></td>
<td><p><span data-ttu-id="3dbdd-268">電話会議におけるユーザーの役割 (発表者など)。</span><span class="sxs-lookup"><span data-stu-id="3dbdd-268">Conference role (for example, Presenter) for the user.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3dbdd-269"><strong>参加者</strong></span><span class="sxs-lookup"><span data-stu-id="3dbdd-269"><strong>Participant</strong></span></span></p></td>
<td><p><span data-ttu-id="3dbdd-270">いいえ</span><span class="sxs-lookup"><span data-stu-id="3dbdd-270">No</span></span></p></td>
<td><p><span data-ttu-id="3dbdd-271">ユーザーの SIP アドレス。</span><span class="sxs-lookup"><span data-stu-id="3dbdd-271">SIP address of the user.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3dbdd-272"><strong>接続</strong></span><span class="sxs-lookup"><span data-stu-id="3dbdd-272"><strong>Connectivity</strong></span></span></p></td>
<td><p><span data-ttu-id="3dbdd-273">いいえ</span><span class="sxs-lookup"><span data-stu-id="3dbdd-273">No</span></span></p></td>
<td><p><span data-ttu-id="3dbdd-274">ネットワーク接続の種類。</span><span class="sxs-lookup"><span data-stu-id="3dbdd-274">Network connection type.</span></span> <span data-ttu-id="3dbdd-275">たとえば、内部 &quot; &quot; 接続の場合は internal、 &quot; ダイヤルイン &quot; ユーザーの場合は PSTN から。</span><span class="sxs-lookup"><span data-stu-id="3dbdd-275">For example &quot;From Internal&quot; for internal connection or &quot;From PSTN&quot; for dial-in users.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3dbdd-276">[<strong>参加時間</strong>]</span><span class="sxs-lookup"><span data-stu-id="3dbdd-276"><strong>Join time</strong></span></span></p></td>
<td><p><span data-ttu-id="3dbdd-277">いいえ</span><span class="sxs-lookup"><span data-stu-id="3dbdd-277">No</span></span></p></td>
<td><p><span data-ttu-id="3dbdd-278">ユーザーが電話会議に参加した日時。</span><span class="sxs-lookup"><span data-stu-id="3dbdd-278">Date and time that the user joined the conference.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3dbdd-279">[<strong>退場時間</strong>]</span><span class="sxs-lookup"><span data-stu-id="3dbdd-279"><strong>Leave time</strong></span></span></p></td>
<td><p><span data-ttu-id="3dbdd-280">いいえ</span><span class="sxs-lookup"><span data-stu-id="3dbdd-280">No</span></span></p></td>
<td><p><span data-ttu-id="3dbdd-281">ユーザーが電話会議から退場した日時。</span><span class="sxs-lookup"><span data-stu-id="3dbdd-281">Date and time that the user left the conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3dbdd-282">[<strong>診断 ID</strong>]</span><span class="sxs-lookup"><span data-stu-id="3dbdd-282"><strong>Diagnostic ID</strong></span></span></p></td>
<td><p><span data-ttu-id="3dbdd-283">いいえ</span><span class="sxs-lookup"><span data-stu-id="3dbdd-283">No</span></span></p></td>
<td><p><span data-ttu-id="3dbdd-p125">SIP メッセージに添付される一意の識別子 (ms-diagnostics ヘッダー形式)。その情報は、多くの場合、エラーのトラブルシューティングに役立ちます。診断ヘッダーはオプションで (このヘッダーを含まない SIP セッションがある可能性もあります)、診断 ID は、何らかの問題が生じたセッションについてのみ報告されます。</span><span class="sxs-lookup"><span data-stu-id="3dbdd-p125">Unique identifier (in the form of an ms-diagnostics header) attached to a SIP message that often provides information useful in troubleshooting errors. Diagnostics headers are optional (it is possible to have SIP sessions that do not include these headers), and diagnostic IDs are reported only for sessions that experienced problems of some kind.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

