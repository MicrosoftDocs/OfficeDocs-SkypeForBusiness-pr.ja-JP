---
title: 'Lync Server 2013: 上位エラーレポート'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Top Failures Report
ms:assetid: 438942e2-580a-4b67-9d42-f116111fb26a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558640(v=OCS.15)
ms:contentKeyID: 48184021
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9a62dce5d074b19c2bc8958715ced61bb54a4c8e
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41745237"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="top-failures-report-in-lync-server-2013"></a><span data-ttu-id="35c44-102">Lync Server 2013 の上位エラーレポート</span><span class="sxs-lookup"><span data-stu-id="35c44-102">Top Failures Report in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="35c44-103">_**最終更新日:** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="35c44-103">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="35c44-p101">トップ エラー レポートは、最もよく報告されているエラーに関する情報と、そのエラーの推移を示します。エラーは、次の 2 つのメトリックの組み合わせに基づいています。</span><span class="sxs-lookup"><span data-stu-id="35c44-p101">The Top Failures Report provides a look at the most-commonly reported failures and their trends over time. Failures are based on a combination of the following two metrics:</span></span>

  - <span data-ttu-id="35c44-p102">**診断 ID**。SIP メッセージに添付された一意の識別子 (ms-diagnostics ヘッダーの形式)。診断 ID は、呼び出し関連のエラーのトラブルシューティングに役立つ情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="35c44-p102">**Diagnostic ID**. Unique identifier (in the form of an ms-diagnostics header) that is attached to a SIP message. Diagnostic IDs provide information useful in troubleshooting call-related problems.</span></span>

  - <span data-ttu-id="35c44-109">**応答コード**。</span><span class="sxs-lookup"><span data-stu-id="35c44-109">**Response code**.</span></span> <span data-ttu-id="35c44-110">応答コードは SIP 通信セッションで使用され、SIP 要求に応答します。</span><span class="sxs-lookup"><span data-stu-id="35c44-110">Response codes are used in SIP communication sessions to respond to SIP requests.</span></span> <span data-ttu-id="35c44-111">たとえば、Ken によって INVITE 要求が Pilar Ackerman に送信されたとします (つまり、Ken Myer が Pilar Ackerman を呼び出したとします)。</span><span class="sxs-lookup"><span data-stu-id="35c44-111">For example, suppose Ken sends the INVITE request to Pilar Ackerman (that is, suppose Ken Myer calls Pilar Ackerman).</span></span> <span data-ttu-id="35c44-112">Pilar の回答がある場合、彼女の電話には応答コード 200 (OK) が送信され、Ken の電話では Pilar が応答したことが通知されます。</span><span class="sxs-lookup"><span data-stu-id="35c44-112">If Pilar answers, her phone will send the response code 200 (OK), letting Ken's phone know that Pilar has answered.</span></span> <span data-ttu-id="35c44-113">上位のエラーレポートには、通話の失敗に応じて送信された応答コードのみが含まれます。通話中に発行されたすべての応答コードは、Lync Server によって追跡されません。</span><span class="sxs-lookup"><span data-stu-id="35c44-113">The Top Failures Report only includes response codes that were sent in response to a call failure; Lync Server does not keep track of all the response codes issued during the course of a call.</span></span>

<span data-ttu-id="35c44-114">このレポートでは、エラーが発生したセッションの合計数だけでなく、エラーの影響を受けた合計ユーザー数に関する情報も報告されます。</span><span class="sxs-lookup"><span data-stu-id="35c44-114">Information is reported not only for the total number of sessions where a failure occurred but also for the total number of users who were impacted by the failure.</span></span>

<div>

## <a name="accessing-the-top-failures-report"></a><span data-ttu-id="35c44-115">トップ エラー レポートにアクセスする</span><span class="sxs-lookup"><span data-stu-id="35c44-115">Accessing the Top Failures Report</span></span>

<span data-ttu-id="35c44-116">トップ エラー レポートには、[監視レポート] ホーム ページからアクセスします。</span><span class="sxs-lookup"><span data-stu-id="35c44-116">The Top Failures Report is accessed from the Monitoring Reports home page.</span></span> <span data-ttu-id="35c44-117">報告されたセッションメトリックをクリックすると、 [Lync Server 2013 の [エラーの配布] レポート](lync-server-2013-failure-distribution-report.md)に移動します。</span><span class="sxs-lookup"><span data-stu-id="35c44-117">Clicking the Reported sessions metric will take you to the [Failure Distribution Report in Lync Server 2013](lync-server-2013-failure-distribution-report.md).</span></span>

</div>

<div>

## <a name="making-the-best-use-of-the-top-failures-report"></a><span data-ttu-id="35c44-118">トップ エラー レポートを最大限に利用する</span><span class="sxs-lookup"><span data-stu-id="35c44-118">Making the Best Use of the Top Failures Report</span></span>

<span data-ttu-id="35c44-p105">トップ エラー レポートは、一度に最大 5 つの診断 ID に基づいてフィルターできるという点で他とは異なります (通常は、一度の 1 つの項目 (1 つのユーザー SIP アドレスなど) でしかフィルターできません)。複数の診断 ID に基づいてフィルターするには、[診断 ID] ボックスに各 ID をコンマで区切って入力します (コンマの後ろに空白を挿入することもできます)。次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="35c44-p105">The Top Failures Report is unusual in one regard: it allows you to filter on as many as 5 diagnostic IDs at once. (Typically you can only filter on one item – such as one user SIP address – at a time.) To filter on multiple diagnostic IDs, simply enter each ID in the Diagnostic IDs box, separating the IDs by using commas. (If you want to, you can leave a blank space after each comma.) For example:</span></span>

<span data-ttu-id="35c44-122">1011, 2412, 1033, 52116, 1008</span><span class="sxs-lookup"><span data-stu-id="35c44-122">1011, 2412, 1033, 52116, 1008</span></span>

<span data-ttu-id="35c44-123">このように指定すると、この 5 つの診断 ID の少なくとも 1 つを報告した通話エラーのみが表示されます。</span><span class="sxs-lookup"><span data-stu-id="35c44-123">Do that, and only failed calls that reported at least one of those five diagnostic IDs will be displayed.</span></span>

<span data-ttu-id="35c44-p106">応答コードの上にマウスを置くと、その応答コードについて説明するヒントが表示されます。たとえば、応答コード 486 の上にマウスを置くと、次のメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="35c44-p106">If you hold your mouse over a Response code you'll see a tooltip that tells you what the Response code in question means. For example, if you hold the mouse over the Response code 486 you'll see this message:</span></span>

<span data-ttu-id="35c44-126">ここはビジー状態</span><span class="sxs-lookup"><span data-stu-id="35c44-126">Busy Here.</span></span>

</div>

<div>

## <a name="filters"></a><span data-ttu-id="35c44-127">フィルター</span><span class="sxs-lookup"><span data-stu-id="35c44-127">Filters</span></span>

<span data-ttu-id="35c44-p107">フィルターは、必要なデータのみに絞り込んだデータ セットを取得したり、取得したデータを別の方法で表示したりする方法として利用できます。たとえば、トップ エラー レポートを使用すると、取得したデータに動作状況の種類 (ピアツーピア セッションまたは電話会議セッション) などに基づいてフィルターを適用できます。また、エラーが発生したセッションに付属する SIP 応答コードによってフィルターを適用することもできます。データをグループ化する方法を選択することもできます。この場合、使用状況は、時間単位、日単位、週単位、または月単位でグループ化されます。</span><span class="sxs-lookup"><span data-stu-id="35c44-p107">Filters provide a way for you to return a more finely-targeted set of data or to view the returned data in different ways. For example, the Top Failures Report enables you to filter the returned data based on such things as the activity type (peer-to-peer session or conferencing session) or by the SIP response code that accompanied the failed session. You can also choose how data should be grouped. In this case, usages are grouped by hour, day, week, or month.</span></span>

<span data-ttu-id="35c44-132">次の表に、トップ エラー レポートで使用できるフィルターを示します。</span><span class="sxs-lookup"><span data-stu-id="35c44-132">The following table lists the filters that you can use with the Top Failures Report.</span></span>

### <a name="top-failures-report-filters"></a><span data-ttu-id="35c44-133">トップ エラー レポートのフィルター</span><span class="sxs-lookup"><span data-stu-id="35c44-133">Top Failures Report Filters</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="35c44-134">名前</span><span class="sxs-lookup"><span data-stu-id="35c44-134">Name</span></span></th>
<th><span data-ttu-id="35c44-135">説明</span><span class="sxs-lookup"><span data-stu-id="35c44-135">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="35c44-136"><strong>開始</strong></span><span class="sxs-lookup"><span data-stu-id="35c44-136"><strong>From</strong></span></span></p></td>
<td><p><span data-ttu-id="35c44-p108">時間範囲の開始日と開始時刻。データを時間単位で表示するには、次のように開始日と開始時刻の両方を入力します。</span><span class="sxs-lookup"><span data-stu-id="35c44-p108">Start date/time for the time range. To view data by hours, enter both the start date and time as follows:</span></span></p>
<p><span data-ttu-id="35c44-139">7/7/2012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="35c44-139">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="35c44-p109">開始時刻を入力しないと、レポートは自動的に指定日の午前 12:00 に開始します。データを日単位で表示するには、次のように日付のみを入力します。</span><span class="sxs-lookup"><span data-stu-id="35c44-p109">If you do not enter a start time, the report automatically begins at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="35c44-142">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="35c44-142">7/7/2012</span></span></p>
<p><span data-ttu-id="35c44-143">週単位または月単位で表示するには、表示する週または月の任意の日付を入力します (その週または月の最初の日である必要はありません)。</span><span class="sxs-lookup"><span data-stu-id="35c44-143">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="35c44-144">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="35c44-144">7/3/2012</span></span></p>
<p><span data-ttu-id="35c44-145">一週間は、日曜日から始まり、土曜日で終わるものとします。</span><span class="sxs-lookup"><span data-stu-id="35c44-145">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="35c44-146"><strong>終了</strong></span><span class="sxs-lookup"><span data-stu-id="35c44-146"><strong>To</strong></span></span></p></td>
<td><p><span data-ttu-id="35c44-p110">時間範囲の終了日と終了時刻。データを時間単位で表示するには、次のように終了日と終了時刻の両方を入力します。</span><span class="sxs-lookup"><span data-stu-id="35c44-p110">End date/time for the time range. To view data by hours, enter both the end date and time as follows:</span></span></p>
<p><span data-ttu-id="35c44-149">7/7/2012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="35c44-149">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="35c44-p111">終了時刻を入力しないと、レポートは自動的に指定日の午前 12:00 に終了します。データを日単位で表示するには、次のように日付のみを入力します。</span><span class="sxs-lookup"><span data-stu-id="35c44-p111">If you do not enter an end time, the report automatically ends at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="35c44-152">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="35c44-152">7/7/2012</span></span></p>
<p><span data-ttu-id="35c44-153">週単位または月単位で表示するには、表示する週または月の任意の日付を入力します (その週または月の最初の日である必要はありません)。</span><span class="sxs-lookup"><span data-stu-id="35c44-153">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="35c44-154">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="35c44-154">7/3/2012</span></span></p>
<p><span data-ttu-id="35c44-155">一週間は、日曜日から始まり、土曜日で終わるものとします。</span><span class="sxs-lookup"><span data-stu-id="35c44-155">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="35c44-156"><strong>[動作状況の種類]</strong></span><span class="sxs-lookup"><span data-stu-id="35c44-156"><strong>Activity type</strong></span></span></p></td>
<td><p><span data-ttu-id="35c44-p112">動作状況の種類。次のいずれかを選択します。</span><span class="sxs-lookup"><span data-stu-id="35c44-p112">Type of activity. Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="35c44-159">[すべて]</span><span class="sxs-lookup"><span data-stu-id="35c44-159">[All]</span></span></p></li>
<li><p><span data-ttu-id="35c44-160">ピアツーピア</span><span class="sxs-lookup"><span data-stu-id="35c44-160">Peer-to-peer</span></span></p></li>
<li><p><span data-ttu-id="35c44-161">電話会議</span><span class="sxs-lookup"><span data-stu-id="35c44-161">Conference</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="35c44-162"><strong>[モダリティ]</strong></span><span class="sxs-lookup"><span data-stu-id="35c44-162"><strong>Modality</strong></span></span></p></td>
<td><p><span data-ttu-id="35c44-163">この場合、唯一使用できるオプションは [<strong>すべて</strong>] です。</span><span class="sxs-lookup"><span data-stu-id="35c44-163">At this time the only option available is <strong>[All]</strong>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="35c44-164"><strong>[プール]</strong></span><span class="sxs-lookup"><span data-stu-id="35c44-164"><strong>Pool</strong></span></span></p></td>
<td><p><span data-ttu-id="35c44-p113">レジストラー プールまたはエッジ サーバーの完全修飾ドメイン名 (FQDN)。個別のプールを選択するか、[<strong>すべて</strong>] をクリックしてすべてのプールのデータを表示できます。このドロップダウン リストは、データベース内のレコードに基づいて自動的に設定されます。</span><span class="sxs-lookup"><span data-stu-id="35c44-p113">Fully qualified domain name (FQDN) of the Registrar pool or Edge Server. You can either select an individual pool or click <strong>[All]</strong> to view data for all the pools. This drop-down list is automatically populated for you based on the records in the database.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="35c44-168"><strong>[カテゴリ]</strong></span><span class="sxs-lookup"><span data-stu-id="35c44-168"><strong>Category</strong></span></span></p></td>
<td><p><span data-ttu-id="35c44-p114">発生したエラーの種類。次のいずれかを選択します。</span><span class="sxs-lookup"><span data-stu-id="35c44-p114">Type of failure experienced. Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="35c44-171">予期されたエラーと予期しないエラーの両方</span><span class="sxs-lookup"><span data-stu-id="35c44-171">Both expected and unexpected failure</span></span></p></li>
<li><p><span data-ttu-id="35c44-172">予期しないエラー</span><span class="sxs-lookup"><span data-stu-id="35c44-172">Unexpected failure</span></span></p></li>
</ul>
<p><span data-ttu-id="35c44-173">&quot;予期される&quot;エラーは、発生する可能性のあるエラーです。</span><span class="sxs-lookup"><span data-stu-id="35c44-173">An &quot;expected failure&quot; is a failure that is expected to happen.</span></span> <span data-ttu-id="35c44-174">たとえば、ユーザーが応答不可のステータスを設定した場合、そのユーザーへの呼び出しはエラーとなることが予期されます。</span><span class="sxs-lookup"><span data-stu-id="35c44-174">For example, if a user has set his or her status to Do Not Disturb you would expect any call to that user to fail.</span></span> <span data-ttu-id="35c44-175">&quot;予期しない&quot;エラーとは、正常に動作していると思われるエラーです。</span><span class="sxs-lookup"><span data-stu-id="35c44-175">An &quot;unexpected failure&quot; is a failure that occurs in what would appear to be an otherwise healthy system.</span></span> <span data-ttu-id="35c44-176">たとえば、発信者が保留にされたときに、通話が終了してはなりません。</span><span class="sxs-lookup"><span data-stu-id="35c44-176">For example, a call should not be terminated if the caller is placed on hold.</span></span> <span data-ttu-id="35c44-177">そのような状態が発生する場合は、予期しないエラーとしてフラグが設定されます。</span><span class="sxs-lookup"><span data-stu-id="35c44-177">If that occurs, that would be flagged as an unexpected failure.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="35c44-178"><strong>[応答コード]</strong></span><span class="sxs-lookup"><span data-stu-id="35c44-178"><strong>Response code</strong></span></span></p></td>
<td><p><span data-ttu-id="35c44-p116">会議が失敗したときに送信された SIP 応答コードです。次の例のように、応答コード全体を入力します。</span><span class="sxs-lookup"><span data-stu-id="35c44-p116">SIP response code sent when the conference failed. Enter the entire response code For example:</span></span></p>
<p><span data-ttu-id="35c44-181">400</span><span class="sxs-lookup"><span data-stu-id="35c44-181">400</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="35c44-182"><strong>[診断 ID]</strong></span><span class="sxs-lookup"><span data-stu-id="35c44-182"><strong>Diagnostic ID</strong></span></span></p></td>
<td><p><span data-ttu-id="35c44-p117">SIP メッセージに添付される一意の識別子 (ms-diagnostics ヘッダー形式)。その情報は、多くの場合、エラーのトラブルシューティングに役立ちます。診断ヘッダーはオプションで (このヘッダーを含まない SIP セッションがある可能性もあります)、診断 ID は、何らかの問題が生じたセッションについてのみ報告されます。</span><span class="sxs-lookup"><span data-stu-id="35c44-p117">Unique identifier (in the form of an ms-diagnostics header) attached to a SIP message that often provides information useful in troubleshooting errors. Diagnostics headers are optional (it is possible to have SIP sessions that do not include these headers), and diagnostic IDs are reported only for sessions that experienced problems of some kind.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics"></a><span data-ttu-id="35c44-185">指標</span><span class="sxs-lookup"><span data-stu-id="35c44-185">Metrics</span></span>

<span data-ttu-id="35c44-186">次の表に、トップ エラー レポートで提供される情報を示します。</span><span class="sxs-lookup"><span data-stu-id="35c44-186">The following table lists the information provided in the Top Failures Report.</span></span>

### <a name="top-failures-report-metrics"></a><span data-ttu-id="35c44-187">トップ エラー レポートの指標</span><span class="sxs-lookup"><span data-stu-id="35c44-187">Top Failures Report Metrics</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="35c44-188">名前</span><span class="sxs-lookup"><span data-stu-id="35c44-188">Name</span></span></th>
<th><span data-ttu-id="35c44-189">この項目での並べ替え</span><span class="sxs-lookup"><span data-stu-id="35c44-189">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="35c44-190">説明</span><span class="sxs-lookup"><span data-stu-id="35c44-190">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="35c44-191"><strong>[ランク]</strong></span><span class="sxs-lookup"><span data-stu-id="35c44-191"><strong>Rank</strong></span></span></p></td>
<td><p><span data-ttu-id="35c44-192">はい</span><span class="sxs-lookup"><span data-stu-id="35c44-192">Yes</span></span></p></td>
<td><p><span data-ttu-id="35c44-193">報告されたセッションの数に基づく相対的なランク。</span><span class="sxs-lookup"><span data-stu-id="35c44-193">Relative rank based on the number of reported sessions.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="35c44-194"><strong>[報告されたセッション]</strong></span><span class="sxs-lookup"><span data-stu-id="35c44-194"><strong>Reported sessions</strong></span></span></p></td>
<td><p><span data-ttu-id="35c44-195">はい</span><span class="sxs-lookup"><span data-stu-id="35c44-195">Yes</span></span></p></td>
<td><p><span data-ttu-id="35c44-196">診断 ID と SIP 応答コードに基づく、失敗したセッションの総数。</span><span class="sxs-lookup"><span data-stu-id="35c44-196">Total number of failed sessions based on diagnostic ID and SIP response code.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="35c44-197"><strong>[影響を受けたユーザー]</strong></span><span class="sxs-lookup"><span data-stu-id="35c44-197"><strong>Users impacted</strong></span></span></p></td>
<td><p><span data-ttu-id="35c44-198">可</span><span class="sxs-lookup"><span data-stu-id="35c44-198">Yes</span></span></p></td>
<td><p><span data-ttu-id="35c44-199">失敗したセッションの影響を受けたユーザーの総数。</span><span class="sxs-lookup"><span data-stu-id="35c44-199">Total number of users affected by the failed session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="35c44-200"><strong>[エラー情報]</strong></span><span class="sxs-lookup"><span data-stu-id="35c44-200"><strong>Failure information</strong></span></span></p></td>
<td><p><span data-ttu-id="35c44-201">いいえ</span><span class="sxs-lookup"><span data-stu-id="35c44-201">No</span></span></p></td>
<td><p><span data-ttu-id="35c44-202">診断 ID、SIP 応答コード、セッションの失敗理由など、失敗の詳細情報。</span><span class="sxs-lookup"><span data-stu-id="35c44-202">Detailed information about the failure, including diagnostic ID, SIP response code, and description of why the session failed.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="35c44-203"><strong>[過去の傾向]</strong></span><span class="sxs-lookup"><span data-stu-id="35c44-203"><strong>Trend in the past</strong></span></span></p></td>
<td><p><span data-ttu-id="35c44-204">不可</span><span class="sxs-lookup"><span data-stu-id="35c44-204">No</span></span></p></td>
<td><p><span data-ttu-id="35c44-205">失敗したセッションの推移をグラフで示します。</span><span class="sxs-lookup"><span data-stu-id="35c44-205">Graphs failed sessions over time.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

