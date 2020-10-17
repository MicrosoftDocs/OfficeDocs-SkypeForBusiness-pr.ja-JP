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
ms.openlocfilehash: 36001aaf38dc39d0bb4eb7524e41c616b0a1c160
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/16/2020
ms.locfileid: "48530234"
---
# <a name="user-activity-report-in-lync-server-2013"></a><span data-ttu-id="f2d9c-102">Lync Server 2013 のユーザーアクティビティレポート</span><span class="sxs-lookup"><span data-stu-id="f2d9c-102">User Activity Report in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f2d9c-103">_**トピックの最終更新日:** 2015-02-27_</span><span class="sxs-lookup"><span data-stu-id="f2d9c-103">_**Topic Last Modified:** 2015-02-27_</span></span>

<span data-ttu-id="f2d9c-p101">ユーザー アクティビティ レポートは、特定の期間にユーザーによって実行されたピアツーピアおよび電話会議セッションの詳細な一覧を示します。多くの監視レポートとは異なり、ユーザー アクティビティ レポートは、各呼び出しを個別のユーザーに関連付けます。たとえば、ピアツーピアセッションでは、呼び出しを開始した人 (呼び出し元ユーザー) と呼び出しを受けた人 (呼び出し先ユーザー) の SIP URI が示されます。電話会議の情報を展開すると、すべての電話会議の参加者と、その電話会議における参加者の役割の一覧が表示されます。</span><span class="sxs-lookup"><span data-stu-id="f2d9c-p101">The User Activity Report provides a detailed list of the peer-to-peer and conferencing sessions carried out by your users in a given time period. Unlike many of the Monitoring Reports, the User Activity Report ties each call to individual users. For example, peer-to-peer sessions specify the SIP URIs of the person who initiated the call (the From user) and the person who was being called (the To user). If you expand the information for a conference, you'll see a list of all the conference participants and the role they held for that conference.</span></span>

<span data-ttu-id="f2d9c-p102">ユーザー アクティビティ レポートは、"ヘルプ デスク" レポートと呼ばれることがあります。ヘルプデスク担当者が、特定のユーザーに関するセッション情報を取得するときによくこのレポートを利用するからです。個別のユーザーに対する、または個別のユーザーによる呼び出しは、[ユーザー URI プレフィックス] ボックスにユーザーの SIP URI を入力するだけでフィルターできます。</span><span class="sxs-lookup"><span data-stu-id="f2d9c-p102">The User Activity Report is sometimes referred to as the "help desk" report. That's because the report is often used by help desk personnel to retrieve session information for a specific user. You can filter for calls made to or made by an individual user simply by typing the user's SIP URI in the User URI prefix box.</span></span>

<span data-ttu-id="f2d9c-111">この操作を行うと、ユーザー アクティビティ レポートは、SIP URI が指定した文字列で始まるユーザーに関する情報を返します。</span><span class="sxs-lookup"><span data-stu-id="f2d9c-111">If you do this, the User Activity Report will return information for any user whose SIP URI begins with the specified string.</span></span> <span data-ttu-id="f2d9c-112">たとえば、[URI] ボックスに **ken** と入力すると、ユーザー アクティビティ レポートは **Ken**.Myer@litwareinc.com を検索します。</span><span class="sxs-lookup"><span data-stu-id="f2d9c-112">For example, if you type **ken** in the URI box, the User Activity Report will locate **Ken**.Myer@litwareinc.com.</span></span> <span data-ttu-id="f2d9c-113">ただし、次のようなユーザーも検索します。</span><span class="sxs-lookup"><span data-stu-id="f2d9c-113">However, it will also locate these users:</span></span>

  - <span data-ttu-id="f2d9c-114">**ken**azi@litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="f2d9c-114">**ken**azi@litwareinc.com</span></span>

  - <span data-ttu-id="f2d9c-115">**ken**burg@litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="f2d9c-115">**ken**burg@litwareinc.com</span></span>

  - <span data-ttu-id="f2d9c-116">**Ken**.Sanchez@litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="f2d9c-116">**Ken**.Sanchez@litwareinc.com</span></span>

  - <span data-ttu-id="f2d9c-117">**Ken**nedy@litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="f2d9c-117">**Ken**nedy@litwareinc.com</span></span>

<span data-ttu-id="f2d9c-118">Ken Myer の情報のみが返されるようにするには、検索ボックスに完全な URI (Ken.Myer@litwareinc.com) を入力するか、組織内の他のユーザーと個人を区別するために、少なくとも Ken の適切な種類の Ken の URI を入力します。</span><span class="sxs-lookup"><span data-stu-id="f2d9c-118">To ensure that information only for Ken Myer is returned, either type his full URI (Ken.Myer@litwareinc.com) in the search box or at least enough type of Ken’s URI to uniquely distinguish him from other users in your organization.</span></span> <span data-ttu-id="f2d9c-119">たとえば、次のようにします。</span><span class="sxs-lookup"><span data-stu-id="f2d9c-119">For example:</span></span>

<span data-ttu-id="f2d9c-120">Ken.my</span><span class="sxs-lookup"><span data-stu-id="f2d9c-120">Ken.my</span></span>

<div>

## <a name="to-access-the-user-activity-report"></a><span data-ttu-id="f2d9c-121">ユーザー アクティビティ レポートにアクセスするには</span><span class="sxs-lookup"><span data-stu-id="f2d9c-121">To access the user activity report</span></span>

<span data-ttu-id="f2d9c-122">ユーザー アクティビティ レポートには、[監視レポート] ホーム ページからアクセスします。</span><span class="sxs-lookup"><span data-stu-id="f2d9c-122">The User Activity Report is accessed from the Monitoring Reports home page.</span></span> <span data-ttu-id="f2d9c-123">また、 [Lync Server 2013 の IP 電話インベントリレポート](lync-server-2013-ip-phone-inventory-report.md)でユーザー URI 指標をクリックして、ユーザーアクティビティレポートにアクセスすることもできます。</span><span class="sxs-lookup"><span data-stu-id="f2d9c-123">You can also reach the User Activity Report by clicking the User URI metric on the [IP Phone Inventory Report in Lync Server 2013](lync-server-2013-ip-phone-inventory-report.md).</span></span> <span data-ttu-id="f2d9c-124">ユーザー アクティビティ レポート内で、会議 URI (会議用) をクリックすると、会議の詳細レポートが表示されます。</span><span class="sxs-lookup"><span data-stu-id="f2d9c-124">From within the User Activity Report, clicking the Conference URI (for a conference) takes you to the Conference Detail Report.</span></span> <span data-ttu-id="f2d9c-125">同様に、ピアツーピア呼び出しの詳細指標をクリックすると、 [Lync Server 2013 のピアツーピアセッション詳細レポート](lync-server-2013-peer-to-peer-session-detail-report.md)が表示されます。</span><span class="sxs-lookup"><span data-stu-id="f2d9c-125">Similarly, clicking the Detail metric for a peer-to-peer call takes you to the [Peer-to-Peer Session Detail Report in Lync Server 2013](lync-server-2013-peer-to-peer-session-detail-report.md).</span></span>

</div>

<div>

## <a name="making-the-best-use-of-the-user-activity-report"></a><span data-ttu-id="f2d9c-126">ユーザー アクティビティ レポートを最大限活用する</span><span class="sxs-lookup"><span data-stu-id="f2d9c-126">Making the best use of the user activity report</span></span>

<span data-ttu-id="f2d9c-127">ユーザー アクティビティ レポートには、多くの良質な情報が含まれていますが、この情報は見つけにくい場合があります。</span><span class="sxs-lookup"><span data-stu-id="f2d9c-127">Although there is a lot of good information in the User Activity Report, that information can sometimes be difficult to locate.</span></span> <span data-ttu-id="f2d9c-128">たとえば、指定した期間中に組織内で発生するすべてのユーザーアクティビティが、ユーザーアクティビティレポートに含まれています。つまり、何らかの方法で Microsoft Lync Server 2013 を実際に使用したユーザーに関する情報をレポート内に埋め込むことができることを意味します。</span><span class="sxs-lookup"><span data-stu-id="f2d9c-128">For example, all the user activity that takes place in your organization during a specified period is included in the User Activity Report; that means that, buried, within the report is information about which users actually used Microsoft Lync Server 2013 in some way.</span></span>

<div>


> [!WARNING]  
> <span data-ttu-id="f2d9c-129">技術的には、一部のユーザーアクティビティが記録になる可能性があります。 Lync Server は、すべての電話呼び出しに関する情報を保存しようとしていますが、その呼び出しについての情報がないと、データベースへの呼び出しが行われている可能性があります。</span><span class="sxs-lookup"><span data-stu-id="f2d9c-129">Technically, it’s possible that some user activity might go unrecorded: while Lync Server strives to keep information about all phone calls it's possible that a call could have been made without the information about that call being written to the database.</span></span> <span data-ttu-id="f2d9c-130">Lync Server は、非常に正確ですが、Lync Server 2013 がどのように使用されているかについては、必ずしもわかりません。</span><span class="sxs-lookup"><span data-stu-id="f2d9c-130">Lync Server is designed to give an extremely accurate but not necessarily perfect look at how Lync Server 2013 is being used.</span></span> <span data-ttu-id="f2d9c-131">(つまり、すべての通話の100% が記録されるという保証はありません。 Lync Server の監視を課金システムとして使用してはならない理由について説明します)。</span><span class="sxs-lookup"><span data-stu-id="f2d9c-131">(The fact that there is no guarantee that 100% of all calls are recorded explains why Lync Server monitoring should not be used as a billing system.)</span></span><BR><span data-ttu-id="f2d9c-p108">また、監視レポートに表示できるのは最大でも 1,000 レコードです。これは、ユーザー アクティビティの量と作業時間によっては、データベースに実際に格納されたデータの一部がクエリでは返されない場合があることを意味します。</span><span class="sxs-lookup"><span data-stu-id="f2d9c-p108">Second, a Monitoring Report report can only display, at most, 1,000 records. Depending on the amount of user activity you have, and depending on the time period you are working with, that means your query might not return all the data actually stored in the database.</span></span>



</div>

  - <span data-ttu-id="f2d9c-134">この期間内にシステムを実際に使用したのはどのユーザーか。</span><span class="sxs-lookup"><span data-stu-id="f2d9c-134">Which users actually used the system during this time period?</span></span>

  - <span data-ttu-id="f2d9c-135">この期間内に最もアクティブだったのはどのユーザーか。</span><span class="sxs-lookup"><span data-stu-id="f2d9c-135">Which of my users were the most active during this time period?</span></span>

  - <span data-ttu-id="f2d9c-136">通話数が最も多いユーザーが、最も多くのインスタント メッセージング セッションに参加しているユーザーでもあるかどうか。</span><span class="sxs-lookup"><span data-stu-id="f2d9c-136">Are the users who make the most phone calls also the users who participate in the most instant messaging sessions?</span></span>

<span data-ttu-id="f2d9c-137">このような情報を確認するには、監視レポートで取得されたデータを Excel スプレッドシートにエクスポートします。</span><span class="sxs-lookup"><span data-stu-id="f2d9c-137">If you need to answer questions like this, you can export the data retrieved by the Monitoring Reports to an Excel spreadsheet.</span></span> <span data-ttu-id="f2d9c-138">次に、そのスプレッドシート/コンマ区切り値ファイルを使用して、ユーザー アクティビティ レポートのようなやり方でデータを分析します。</span><span class="sxs-lookup"><span data-stu-id="f2d9c-138">You then use that spreadsheet and/or a comma-separated values file to analyze the data in ways that the User Activity Report.</span></span> <span data-ttu-id="f2d9c-139">たとえば、レポートデータを Excel にエクスポートしてから、コンマ区切り値ファイルにエクスポートするとします。</span><span class="sxs-lookup"><span data-stu-id="f2d9c-139">For example, suppose you have exported the report data to Excel and then to a comma-separated values file.</span></span> <span data-ttu-id="f2d9c-140">この時点で、次のようなコマンドを使用することで、データを .CSV ファイルから Windows PowerShell にインポートできます。</span><span class="sxs-lookup"><span data-stu-id="f2d9c-140">At that point, you can import the data from the .CSV file to Windows PowerShell by using a command similar to this:</span></span>

    $x = Import-Csv -Path "C:\Data\User_Activity_Report.csv"

<span data-ttu-id="f2d9c-141">データがインポートされたら、簡単な Windows PowerShell コマンドを使用して質問に回答する場合に役立てることができます。</span><span class="sxs-lookup"><span data-stu-id="f2d9c-141">After the data has been imported you can then use simple Windows PowerShell commands to help answer your questions.</span></span> <span data-ttu-id="f2d9c-142">たとえば、次のコマンドは、少なくとも 1 つのセッションで "呼び出し元" ユーザーとしての役割を果たす一意のユーザーの一覧を返します。</span><span class="sxs-lookup"><span data-stu-id="f2d9c-142">For example, this command returns a list of unique users who served as the "From user" in at least one session:</span></span>

    $x | Group-Object "From user" | Select Name | Sort-Object Name

<span data-ttu-id="f2d9c-143">つまり、次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="f2d9c-143">In other words:</span></span>

    Name
    ----
    David.Ahs@litwareinc.com
    Gilead.Amosnino@litwareinc.com
    Henrik.Jensen@litwareinc.com
    Ken.Myer@litwareinc.com
    Pilar.Ackerman@litwareinc.com

<span data-ttu-id="f2d9c-144">次のコマンドは、ユーザーが参加しているセッションの合計数に基づいて、一意のユーザーの一覧を表示します。</span><span class="sxs-lookup"><span data-stu-id="f2d9c-144">This command lists the unique users (based on the total number of sessions that they participated in:</span></span>

    $x | Group-Object "From user" | Select Count, Name | Sort-Object Count -Descending

<span data-ttu-id="f2d9c-145">このコマンドによって、以下のようなデータが返されます。</span><span class="sxs-lookup"><span data-stu-id="f2d9c-145">That returns data similar to this:</span></span>

    Count    Name
    -----    ----
      523    Ken.Myer@litwareinc.com
       63    David.Ahs@litwareinc.com
       29    Pilar.Ackerman@litwareinc.com
       17    Gilead.Amosnino@litwareinc.com
       10    Henrik.Jensen@litwareinc.com

<span data-ttu-id="f2d9c-146">次のコマンドは、報告されたセッションを、モダリティとしてオーディオが含まれるセッションに制限します。</span><span class="sxs-lookup"><span data-stu-id="f2d9c-146">This command limits the reported sessions to those that included audio as a modality:</span></span>

    $x | Where-Object {$_.Modalities -match "audio"} | Group-Object "From user" | Select Count, Name | Sort-Object Count -Descending

<span data-ttu-id="f2d9c-147">レポートに表示されている診断 ID の上にマウスを置くと、その ID について説明するヒントが表示されます。</span><span class="sxs-lookup"><span data-stu-id="f2d9c-147">If you hold your mouse over any Diagnostic ID shown on the report, a tooltip will appear describing that ID.</span></span>

</div>

<div>

## <a name="filters"></a><span data-ttu-id="f2d9c-148">フィルター</span><span class="sxs-lookup"><span data-stu-id="f2d9c-148">Filters</span></span>

<span data-ttu-id="f2d9c-p111">フィルターは、必要なデータのみに絞り込んだデータ セットを取得したり、取得したデータを別の方法で表示したりする方法として利用できます。たとえば、ユーザー アクティビティ レポートを使用すると、取得したデータに動作状況の種類 (ピアツーピア セッションまたは電話会議セッション) などに基づいてフィルターを適用できます。また、ユーザーの SIP アドレスによってフィルターを適用することもできます (この場合、1 人のユーザーの動作状況を表示できます)。データをグループ化する方法を選択することもできます。この場合、使用状況は、時間単位、日単位、週単位、または月単位でグループ化されます。</span><span class="sxs-lookup"><span data-stu-id="f2d9c-p111">Filters provide a way for you to return a more finely-targeted set of data or to view the returned data in different ways. For example, the User Activity Report enables you to filter the returned data based on such things as activity type (that is, peer-to-peer sessions or conferencing sessions) or by the user's SIP address (allowing you to view the activities for one user). You can also choose how data should be grouped. In this case, usages are grouped by hour, day, week, or month.</span></span>

<span data-ttu-id="f2d9c-153">次の表に、ユーザー アクティビティ レポートで使用できるフィルターを示します。</span><span class="sxs-lookup"><span data-stu-id="f2d9c-153">The following table lists the filters that you can use with the User Activity Report.</span></span>

### <a name="user-activity-report-filters"></a><span data-ttu-id="f2d9c-154">ユーザー アクティビティ レポートのフィルター</span><span class="sxs-lookup"><span data-stu-id="f2d9c-154">User activity report filters</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="f2d9c-155">名前</span><span class="sxs-lookup"><span data-stu-id="f2d9c-155">Name</span></span></th>
<th><span data-ttu-id="f2d9c-156">説明</span><span class="sxs-lookup"><span data-stu-id="f2d9c-156">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="f2d9c-157"><strong>From</strong></span><span class="sxs-lookup"><span data-stu-id="f2d9c-157"><strong>From</strong></span></span></p></td>
<td><p><span data-ttu-id="f2d9c-p112">時間範囲の開始日と開始時刻。データを時間単位で表示するには、次のように開始日と開始時刻の両方を入力します。</span><span class="sxs-lookup"><span data-stu-id="f2d9c-p112">Start date/time for the time range. To view data by hours, enter both the start date and time as follows:</span></span></p>
<p><span data-ttu-id="f2d9c-160">7/17/2012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="f2d9c-160">7/17/12012 1:00 PM</span></span></p>
<p><span data-ttu-id="f2d9c-p113">開始時刻を入力しないと、レポートは自動的に指定日の午前 12:00 に開始します。データを日単位で表示するには、次のように日付のみを入力します。</span><span class="sxs-lookup"><span data-stu-id="f2d9c-p113">If you do not enter a start time, the report automatically begins at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="f2d9c-163">7/17/12012</span><span class="sxs-lookup"><span data-stu-id="f2d9c-163">7/17/12012</span></span></p>
<p><span data-ttu-id="f2d9c-164">週単位または月単位で表示するには、表示する週または月の任意の日付を入力します (その週または月の最初の日である必要はありません)。</span><span class="sxs-lookup"><span data-stu-id="f2d9c-164">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="f2d9c-165">7/13/2012</span><span class="sxs-lookup"><span data-stu-id="f2d9c-165">7/13/2012</span></span></p>
<p><span data-ttu-id="f2d9c-166">週は、常に日曜日から土曜日までです。</span><span class="sxs-lookup"><span data-stu-id="f2d9c-166">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f2d9c-167"><strong>To</strong></span><span class="sxs-lookup"><span data-stu-id="f2d9c-167"><strong>To</strong></span></span></p></td>
<td><p><span data-ttu-id="f2d9c-p114">時間範囲の終了日と終了時刻。データを時間単位で表示するには、次のように終了日と終了時刻の両方を入力します。</span><span class="sxs-lookup"><span data-stu-id="f2d9c-p114">End date/time for the time range. To view data by hours, enter both the end date and time as follows:</span></span></p>
<p><span data-ttu-id="f2d9c-170">7/17/2012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="f2d9c-170">7/17/12012 1:00 PM</span></span></p>
<p><span data-ttu-id="f2d9c-p115">終了時刻を入力しないと、レポートは自動的に指定日の午前 12:00 に終了します。データを日単位で表示するには、次のように日付のみを入力します。</span><span class="sxs-lookup"><span data-stu-id="f2d9c-p115">If you do not enter an end time, the report automatically ends at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="f2d9c-173">7/17/12012</span><span class="sxs-lookup"><span data-stu-id="f2d9c-173">7/17/12012</span></span></p>
<p><span data-ttu-id="f2d9c-174">週単位または月単位で表示するには、表示する週または月の任意の日付を入力します (その週または月の最初の日である必要はありません)。</span><span class="sxs-lookup"><span data-stu-id="f2d9c-174">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="f2d9c-175">7/13/2012</span><span class="sxs-lookup"><span data-stu-id="f2d9c-175">7/13/2012</span></span></p>
<p><span data-ttu-id="f2d9c-176">一週間は、日曜日から始まり、土曜日で終わるものとします。</span><span class="sxs-lookup"><span data-stu-id="f2d9c-176">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f2d9c-177"><strong>アクティビティの種類</strong></span><span class="sxs-lookup"><span data-stu-id="f2d9c-177"><strong>Activity type</strong></span></span></p></td>
<td><p><span data-ttu-id="f2d9c-p116">動作状況の種類。次のいずれかを選択します。</span><span class="sxs-lookup"><span data-stu-id="f2d9c-p116">Type of activity. Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="f2d9c-180">[All]</span><span class="sxs-lookup"><span data-stu-id="f2d9c-180">[All]</span></span></p></li>
<li><p><span data-ttu-id="f2d9c-181">ピアツーピア</span><span class="sxs-lookup"><span data-stu-id="f2d9c-181">Peer-to-peer</span></span></p></li>
<li><p><span data-ttu-id="f2d9c-182">会議</span><span class="sxs-lookup"><span data-stu-id="f2d9c-182">Conference</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f2d9c-183"><strong>モダリティ</strong></span><span class="sxs-lookup"><span data-stu-id="f2d9c-183"><strong>Modality</strong></span></span></p></td>
<td><p><span data-ttu-id="f2d9c-184">使用可能なモダリティは、選択するアクティビティの種類によって異なります。</span><span class="sxs-lookup"><span data-stu-id="f2d9c-184">The Modality available to you varies depending on the select Activity Type.</span></span> <span data-ttu-id="f2d9c-185">アクティビティの種類がピアツーピアの場合、モダリティとして IM、ファイル転送、アプリケーションの共有、音声、またはビデオを選択することが可能です。</span><span class="sxs-lookup"><span data-stu-id="f2d9c-185">If the Activity Type is Peer-to-Peer, you can select IM; File Transfer; Application Sharing; Voice; or Video as the modality.</span></span></p>
<p><span data-ttu-id="f2d9c-186">アクティビティの種類が会議の場合、IM 電話会議、Web 会議、アプリケーションの共有、音声/ビデオ会議、またはテレフォニー会議を選択可能です。</span><span class="sxs-lookup"><span data-stu-id="f2d9c-186">If the Activity Type is Conference, you can select IM Phone conference; Web conference; Application Sharing; Voice/Video conference; or Telephony conference.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f2d9c-187">[<strong>セッション カテゴリ</strong>]</span><span class="sxs-lookup"><span data-stu-id="f2d9c-187"><strong>Session category</strong></span></span></p></td>
<td><p><span data-ttu-id="f2d9c-p118">問題のアクティビティが成功したか失敗したかを示します。次のいずれかを選択します。</span><span class="sxs-lookup"><span data-stu-id="f2d9c-p118">Indicates whether the activity in question succeeded or failed. Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="f2d9c-190">[All]</span><span class="sxs-lookup"><span data-stu-id="f2d9c-190">[All]</span></span></p></li>
<li><p><span data-ttu-id="f2d9c-191">成功</span><span class="sxs-lookup"><span data-stu-id="f2d9c-191">Success</span></span></p></li>
<li><p><span data-ttu-id="f2d9c-192">[予期されたエラー]</span><span class="sxs-lookup"><span data-stu-id="f2d9c-192">Expected failure</span></span></p></li>
<li><p><span data-ttu-id="f2d9c-193">[予期しないエラー]</span><span class="sxs-lookup"><span data-stu-id="f2d9c-193">Unexpected failure</span></span></p></li>
</ul>
<p><span data-ttu-id="f2d9c-194">&quot;予期 &quot; されるエラーは、発生する可能性のあるエラーです。たとえば、ユーザーが自分の状態を [応答不可] に設定している場合は、そのユーザーへの呼び出しが失敗することが予想されます。</span><span class="sxs-lookup"><span data-stu-id="f2d9c-194">An &quot;expected failure&quot; is a failure that is expected to happen; for example, if a user has set his or her status to Do Not Disturb you would expect any call to that user to fail.</span></span> <span data-ttu-id="f2d9c-195">&quot;予期しないエラーと &quot; は、正常なシステムとして表示されるエラーです。</span><span class="sxs-lookup"><span data-stu-id="f2d9c-195">An &quot;unexpected failure&quot; is a failure that occurs in what would appear to be an otherwise healthy system.</span></span> <span data-ttu-id="f2d9c-196">たとえば、発信者が保留にされたときに、通話が終了してはなりません。</span><span class="sxs-lookup"><span data-stu-id="f2d9c-196">For example, a call should not be terminated if the caller is placed on hold.</span></span> <span data-ttu-id="f2d9c-197">そのような状態が発生する場合は、予期しないエラーとしてフラグが設定されます。</span><span class="sxs-lookup"><span data-stu-id="f2d9c-197">If that occurs, that would be flagged as an unexpected failure.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f2d9c-198">[<strong>ユーザー URI プレフィックス</strong>]</span><span class="sxs-lookup"><span data-stu-id="f2d9c-198"><strong>User URI prefix</strong></span></span></p></td>
<td><p><span data-ttu-id="f2d9c-p120">ユーザーの SIP アドレス。たとえば、Ken Myer という名前のユーザーのレコードのみを表示するには、次のように、Ken Myer の SIP アドレスを入力する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f2d9c-p120">SIP address for the user. To view records only for the user Ken Myer you need to enter Ken Myer's SIP address. For example:</span></span></p>
<p><span data-ttu-id="f2d9c-202">sip:kenmyer@litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="f2d9c-202">sip:kenmyer@litwareinc.com</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-peer-to-peer-sessions"></a><span data-ttu-id="f2d9c-203">ピアツーピア セッションの指標</span><span class="sxs-lookup"><span data-stu-id="f2d9c-203">Metrics for peer-to-peer sessions</span></span>

<span data-ttu-id="f2d9c-204">次の表に、ピアツーピア セッション (2 人の参加者だけで行うセッション) について、ユーザー アクティビティ レポートで提供される情報を示します。</span><span class="sxs-lookup"><span data-stu-id="f2d9c-204">The following table lists the information provided in the User Activity Report for peer-to-peer sessions (that is, sessions involving just two participants).</span></span>

### <a name="metrics-for-peer-to-peer-sessions"></a><span data-ttu-id="f2d9c-205">ピアツーピア セッションの指標</span><span class="sxs-lookup"><span data-stu-id="f2d9c-205">Metrics for peer-to-peer sessions</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="f2d9c-206">名前</span><span class="sxs-lookup"><span data-stu-id="f2d9c-206">Name</span></span></th>
<th><span data-ttu-id="f2d9c-207">この項目での並べ替え</span><span class="sxs-lookup"><span data-stu-id="f2d9c-207">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="f2d9c-208">説明</span><span class="sxs-lookup"><span data-stu-id="f2d9c-208">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="f2d9c-209"><strong>詳細</strong></span><span class="sxs-lookup"><span data-stu-id="f2d9c-209"><strong>Detail</strong></span></span></p></td>
<td><p><span data-ttu-id="f2d9c-210">いいえ</span><span class="sxs-lookup"><span data-stu-id="f2d9c-210">No</span></span></p></td>
<td><p><span data-ttu-id="f2d9c-211">この項目をクリックすると、選択されているセッションのピアツーピア セッション詳細レポートが表示されます。</span><span class="sxs-lookup"><span data-stu-id="f2d9c-211">When you click this item, the report shows you the Peer-to-Peer Session Detail Report for the selected session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f2d9c-212">[<strong>移動元ユーザー</strong>]</span><span class="sxs-lookup"><span data-stu-id="f2d9c-212"><strong>From user</strong></span></span></p></td>
<td><p><span data-ttu-id="f2d9c-213">はい</span><span class="sxs-lookup"><span data-stu-id="f2d9c-213">Yes</span></span></p></td>
<td><p><span data-ttu-id="f2d9c-214">ピアツーピア セッションを開始したユーザーの SIP アドレス。</span><span class="sxs-lookup"><span data-stu-id="f2d9c-214">SIP address of the user who initiated the peer-to-peer session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f2d9c-215">[<strong>対象ユーザー</strong>]</span><span class="sxs-lookup"><span data-stu-id="f2d9c-215"><strong>To user</strong></span></span></p></td>
<td><p><span data-ttu-id="f2d9c-216">はい</span><span class="sxs-lookup"><span data-stu-id="f2d9c-216">Yes</span></span></p></td>
<td><p><span data-ttu-id="f2d9c-217">ピアツーピア セッションに参加したユーザーの SIP アドレス。</span><span class="sxs-lookup"><span data-stu-id="f2d9c-217">SIP address of the user who joined the peer-to-peer session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f2d9c-218"><strong>モダリティ</strong></span><span class="sxs-lookup"><span data-stu-id="f2d9c-218"><strong>Modalities</strong></span></span></p></td>
<td><p><span data-ttu-id="f2d9c-219">はい</span><span class="sxs-lookup"><span data-stu-id="f2d9c-219">Yes</span></span></p></td>
<td><p><span data-ttu-id="f2d9c-p121">セッションで使用された通信の種類。たとえば、IM、音声、ファイル送信。</span><span class="sxs-lookup"><span data-stu-id="f2d9c-p121">Type of communication used in the session. For example, IM, audio, or file transfer.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f2d9c-222">[<strong>招待時間</strong>]</span><span class="sxs-lookup"><span data-stu-id="f2d9c-222"><strong>Invite time</strong></span></span></p></td>
<td><p><span data-ttu-id="f2d9c-223">はい</span><span class="sxs-lookup"><span data-stu-id="f2d9c-223">Yes</span></span></p></td>
<td><p><span data-ttu-id="f2d9c-224">ピアツーピア セッションへの最初の招待が送信された日時。</span><span class="sxs-lookup"><span data-stu-id="f2d9c-224">Date and time the initial invitation to join the peer-to-peer session was sent.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f2d9c-225">[<strong>応答時間</strong>]</span><span class="sxs-lookup"><span data-stu-id="f2d9c-225"><strong>Response time</strong></span></span></p></td>
<td><p><span data-ttu-id="f2d9c-226">はい</span><span class="sxs-lookup"><span data-stu-id="f2d9c-226">Yes</span></span></p></td>
<td><p><span data-ttu-id="f2d9c-227">ユーザーがセッションへの &quot; 招待を受け入れた日時 &quot; 。</span><span class="sxs-lookup"><span data-stu-id="f2d9c-227">Date and time that the &quot;To&quot; user accepted the session invitation.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f2d9c-228"><strong>終了時刻</strong></span><span class="sxs-lookup"><span data-stu-id="f2d9c-228"><strong>End time</strong></span></span></p></td>
<td><p><span data-ttu-id="f2d9c-229">はい</span><span class="sxs-lookup"><span data-stu-id="f2d9c-229">Yes</span></span></p></td>
<td><p><span data-ttu-id="f2d9c-230">ピアツーピア セッションが終了した日時。</span><span class="sxs-lookup"><span data-stu-id="f2d9c-230">Date and time the peer-to-peer session ended.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f2d9c-231">[<strong>診断 ID</strong>]</span><span class="sxs-lookup"><span data-stu-id="f2d9c-231"><strong>Diagnostic ID</strong></span></span></p></td>
<td><p><span data-ttu-id="f2d9c-232">はい</span><span class="sxs-lookup"><span data-stu-id="f2d9c-232">Yes</span></span></p></td>
<td><p><span data-ttu-id="f2d9c-p122">SIP メッセージに添付される一意の識別子 (ms-diagnostics ヘッダー形式)。その情報は、多くの場合、エラーのトラブルシューティングに役立ちます。診断ヘッダーはオプションで (このヘッダーを含まない SIP セッションがある可能性もあります)、診断 ID は、何らかの問題が生じたセッションについてのみ報告されます。</span><span class="sxs-lookup"><span data-stu-id="f2d9c-p122">Unique identifier (in the form of an ms-diagnostics header) attached to a SIP message that often provides information useful in troubleshooting errors. Diagnostics headers are optional (it is possible to have SIP sessions that do not include these headers), and diagnostic IDs are reported only for sessions that experienced problems of some kind.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-conferencing-sessions"></a><span data-ttu-id="f2d9c-235">電話会議セッションの指標</span><span class="sxs-lookup"><span data-stu-id="f2d9c-235">Metrics for conferencing sessions</span></span>

<span data-ttu-id="f2d9c-236">次の表に、電話会議セッション (3 人以上の参加者で行うセッション) について、ユーザー アクティビティ レポートで提供される情報を示します。</span><span class="sxs-lookup"><span data-stu-id="f2d9c-236">The following table lists the information provided in the User Activity Report for conferencing sessions (that is, sessions involving three or more participants).</span></span>

### <a name="metrics-for-conferencing-sessions"></a><span data-ttu-id="f2d9c-237">電話会議セッションの指標</span><span class="sxs-lookup"><span data-stu-id="f2d9c-237">Metrics for conferencing sessions</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="f2d9c-238">名前</span><span class="sxs-lookup"><span data-stu-id="f2d9c-238">Name</span></span></th>
<th><span data-ttu-id="f2d9c-239">この項目での並べ替え</span><span class="sxs-lookup"><span data-stu-id="f2d9c-239">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="f2d9c-240">説明</span><span class="sxs-lookup"><span data-stu-id="f2d9c-240">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="f2d9c-241">[<strong>会議 URI</strong>]</span><span class="sxs-lookup"><span data-stu-id="f2d9c-241"><strong>Conference URI</strong></span></span></p></td>
<td><p><span data-ttu-id="f2d9c-242">はい</span><span class="sxs-lookup"><span data-stu-id="f2d9c-242">Yes</span></span></p></td>
<td><p><span data-ttu-id="f2d9c-243">一意の電話会議 ID。</span><span class="sxs-lookup"><span data-stu-id="f2d9c-243">Unique conference identifier.</span></span> <span data-ttu-id="f2d9c-244">この項目をクリックすると、選択されているセッションの会議詳細レポートが表示されます。</span><span class="sxs-lookup"><span data-stu-id="f2d9c-244">When you click this item, the report shows you the Conference Detail Report for the selected session.</span></span> <span data-ttu-id="f2d9c-245">この項目を展開すると、電話会議参加者に関する情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="f2d9c-245">When you expand this item, the report shows you information about the conference participants.</span></span> <span data-ttu-id="f2d9c-246">詳細については、 &quot; &quot; このトピックで後述する「電話会議の参加者の指標」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f2d9c-246">For details, see the &quot;Metrics for Conference Participants&quot; section later in this topic.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f2d9c-247"><strong>開催者</strong></span><span class="sxs-lookup"><span data-stu-id="f2d9c-247"><strong>Organizer</strong></span></span></p></td>
<td><p><span data-ttu-id="f2d9c-248">はい</span><span class="sxs-lookup"><span data-stu-id="f2d9c-248">Yes</span></span></p></td>
<td><p><span data-ttu-id="f2d9c-249">会議を開催したユーザーの SIP アドレス。</span><span class="sxs-lookup"><span data-stu-id="f2d9c-249">SIP address of the user who organized the conference.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f2d9c-250"><strong>Pool</strong></span><span class="sxs-lookup"><span data-stu-id="f2d9c-250"><strong>Pool</strong></span></span></p></td>
<td><p><span data-ttu-id="f2d9c-251">はい</span><span class="sxs-lookup"><span data-stu-id="f2d9c-251">Yes</span></span></p></td>
<td><p><span data-ttu-id="f2d9c-252">電話会議で使用されたエッジ サーバーの名前 (エッジ サーバーが使用された場合)。</span><span class="sxs-lookup"><span data-stu-id="f2d9c-252">Name of the Edge Server (if any) used in the conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f2d9c-253"><strong>開始時刻</strong></span><span class="sxs-lookup"><span data-stu-id="f2d9c-253"><strong>Start time</strong></span></span></p></td>
<td><p><span data-ttu-id="f2d9c-254">はい</span><span class="sxs-lookup"><span data-stu-id="f2d9c-254">Yes</span></span></p></td>
<td><p><span data-ttu-id="f2d9c-255">会議が開始された日時。</span><span class="sxs-lookup"><span data-stu-id="f2d9c-255">Date and time that the conference began.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f2d9c-256"><strong>終了時刻</strong></span><span class="sxs-lookup"><span data-stu-id="f2d9c-256"><strong>End time</strong></span></span></p></td>
<td><p><span data-ttu-id="f2d9c-257">はい</span><span class="sxs-lookup"><span data-stu-id="f2d9c-257">Yes</span></span></p></td>
<td><p><span data-ttu-id="f2d9c-258">会議が終了した日時。</span><span class="sxs-lookup"><span data-stu-id="f2d9c-258">Date and time that the conference ended.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-conference-participants"></a><span data-ttu-id="f2d9c-259">電話会議参加者の指標</span><span class="sxs-lookup"><span data-stu-id="f2d9c-259">Metrics for conference participants</span></span>

<span data-ttu-id="f2d9c-260">次の表に、各電話会議参加者についてユーザー アクティビティ レポートで提供される情報を示します。</span><span class="sxs-lookup"><span data-stu-id="f2d9c-260">The following table lists the information provided in the User Activity Report provides for each participant in a conference.</span></span>

### <a name="metrics-for-conference-participants"></a><span data-ttu-id="f2d9c-261">電話会議参加者の指標</span><span class="sxs-lookup"><span data-stu-id="f2d9c-261">Metrics for conference participants</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="f2d9c-262">名前</span><span class="sxs-lookup"><span data-stu-id="f2d9c-262">Name</span></span></th>
<th><span data-ttu-id="f2d9c-263">この項目での並べ替え</span><span class="sxs-lookup"><span data-stu-id="f2d9c-263">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="f2d9c-264">説明</span><span class="sxs-lookup"><span data-stu-id="f2d9c-264">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="f2d9c-265"><strong>役割</strong></span><span class="sxs-lookup"><span data-stu-id="f2d9c-265"><strong>Role</strong></span></span></p></td>
<td><p><span data-ttu-id="f2d9c-266">いいえ</span><span class="sxs-lookup"><span data-stu-id="f2d9c-266">No</span></span></p></td>
<td><p><span data-ttu-id="f2d9c-267">電話会議におけるユーザーの役割 (発表者など)。</span><span class="sxs-lookup"><span data-stu-id="f2d9c-267">Conference role (for example, Presenter) for the user.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f2d9c-268"><strong>参加者</strong></span><span class="sxs-lookup"><span data-stu-id="f2d9c-268"><strong>Participant</strong></span></span></p></td>
<td><p><span data-ttu-id="f2d9c-269">いいえ</span><span class="sxs-lookup"><span data-stu-id="f2d9c-269">No</span></span></p></td>
<td><p><span data-ttu-id="f2d9c-270">ユーザーの SIP アドレス。</span><span class="sxs-lookup"><span data-stu-id="f2d9c-270">SIP address of the user.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f2d9c-271"><strong>接続</strong></span><span class="sxs-lookup"><span data-stu-id="f2d9c-271"><strong>Connectivity</strong></span></span></p></td>
<td><p><span data-ttu-id="f2d9c-272">いいえ</span><span class="sxs-lookup"><span data-stu-id="f2d9c-272">No</span></span></p></td>
<td><p><span data-ttu-id="f2d9c-273">ネットワーク接続の種類。</span><span class="sxs-lookup"><span data-stu-id="f2d9c-273">Network connection type.</span></span> <span data-ttu-id="f2d9c-274">たとえば、内部 &quot; &quot; 接続の場合は internal、 &quot; ダイヤルイン &quot; ユーザーの場合は PSTN から。</span><span class="sxs-lookup"><span data-stu-id="f2d9c-274">For example &quot;From Internal&quot; for internal connection or &quot;From PSTN&quot; for dial-in users.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f2d9c-275">[<strong>参加時間</strong>]</span><span class="sxs-lookup"><span data-stu-id="f2d9c-275"><strong>Join time</strong></span></span></p></td>
<td><p><span data-ttu-id="f2d9c-276">いいえ</span><span class="sxs-lookup"><span data-stu-id="f2d9c-276">No</span></span></p></td>
<td><p><span data-ttu-id="f2d9c-277">ユーザーが電話会議に参加した日時。</span><span class="sxs-lookup"><span data-stu-id="f2d9c-277">Date and time that the user joined the conference.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f2d9c-278">[<strong>退場時間</strong>]</span><span class="sxs-lookup"><span data-stu-id="f2d9c-278"><strong>Leave time</strong></span></span></p></td>
<td><p><span data-ttu-id="f2d9c-279">いいえ</span><span class="sxs-lookup"><span data-stu-id="f2d9c-279">No</span></span></p></td>
<td><p><span data-ttu-id="f2d9c-280">ユーザーが電話会議から退場した日時。</span><span class="sxs-lookup"><span data-stu-id="f2d9c-280">Date and time that the user left the conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f2d9c-281">[<strong>診断 ID</strong>]</span><span class="sxs-lookup"><span data-stu-id="f2d9c-281"><strong>Diagnostic ID</strong></span></span></p></td>
<td><p><span data-ttu-id="f2d9c-282">いいえ</span><span class="sxs-lookup"><span data-stu-id="f2d9c-282">No</span></span></p></td>
<td><p><span data-ttu-id="f2d9c-p125">SIP メッセージに添付される一意の識別子 (ms-diagnostics ヘッダー形式)。その情報は、多くの場合、エラーのトラブルシューティングに役立ちます。診断ヘッダーはオプションで (このヘッダーを含まない SIP セッションがある可能性もあります)、診断 ID は、何らかの問題が生じたセッションについてのみ報告されます。</span><span class="sxs-lookup"><span data-stu-id="f2d9c-p125">Unique identifier (in the form of an ms-diagnostics header) attached to a SIP message that often provides information useful in troubleshooting errors. Diagnostics headers are optional (it is possible to have SIP sessions that do not include these headers), and diagnostic IDs are reported only for sessions that experienced problems of some kind.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

