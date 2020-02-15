---
title: 'Lync Server 2013: エラー分布レポート'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Failure Distribution Report
ms:assetid: 365c7beb-24d4-40f5-92e7-4978b9688916
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558635(v=OCS.15)
ms:contentKeyID: 48183849
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 291097d645884d4c5146b48a69e5355db71e2193
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2020
ms.locfileid: "42046610"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="failure-distribution-report-in-lync-server-2013"></a><span data-ttu-id="fbe4b-102">Lync Server 2013 のエラー分布レポート</span><span class="sxs-lookup"><span data-stu-id="fbe4b-102">Failure Distribution Report in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="fbe4b-103">_**トピックの最終更新日:** 2012-10-21_</span><span class="sxs-lookup"><span data-stu-id="fbe4b-103">_**Topic Last Modified:** 2012-10-21_</span></span>

<span data-ttu-id="fbe4b-104">エラー分布レポートは、問題の発生したセッションを以下のカテゴリに分類します。</span><span class="sxs-lookup"><span data-stu-id="fbe4b-104">The Failure Distribution Report ranks failed sessions in the following categories:</span></span>

  - <span data-ttu-id="fbe4b-105">[トップの診断理由]</span><span class="sxs-lookup"><span data-stu-id="fbe4b-105">Top diagnostic reasons</span></span>

  - <span data-ttu-id="fbe4b-106">[トップ モダリティ]</span><span class="sxs-lookup"><span data-stu-id="fbe4b-106">Top modalities</span></span>

  - <span data-ttu-id="fbe4b-107">[トップ プール]</span><span class="sxs-lookup"><span data-stu-id="fbe4b-107">Top pools</span></span>

  - <span data-ttu-id="fbe4b-108">[トップ ソース]</span><span class="sxs-lookup"><span data-stu-id="fbe4b-108">Top sources</span></span>

  - <span data-ttu-id="fbe4b-109">[トップ コンポーネント]</span><span class="sxs-lookup"><span data-stu-id="fbe4b-109">Top components</span></span>

  - <span data-ttu-id="fbe4b-110">[トップの発信元ユーザー]</span><span class="sxs-lookup"><span data-stu-id="fbe4b-110">Top from users</span></span>

  - <span data-ttu-id="fbe4b-111">[トップの発信先ユーザー]</span><span class="sxs-lookup"><span data-stu-id="fbe4b-111">Top to users</span></span>

  - <span data-ttu-id="fbe4b-112">[送信元ユーザー エージェント]</span><span class="sxs-lookup"><span data-stu-id="fbe4b-112">Top from user agents</span></span>

<span data-ttu-id="fbe4b-p101">これらのカテゴリを使用して、どこに問題が発生しているか、場合によっては、問題が発生している理由を正確に確認できます。たとえば、特定の日に、問題の発生したオーディオ/ビデオ セッションが 242 個、記録されたとします。エラー分布レポートを調べてみると、これらの問題の発生したセッションのうち、237 が Dublin プールで発生したことが示されることがあります。これらの問題の背後にある原因を追求して、診断する際、このような情報は良い出発点になります。[**トップ プール**] カテゴリの下の Dublin プールをクリックすると、そのプールのエラー分布レポートのみが表示されます。次に Dublin プールでなぜこんなに多くの問題が発生しているかの分析を開始できます。</span><span class="sxs-lookup"><span data-stu-id="fbe4b-p101">You can use these categories to determine exactly where a problem is occurring and, in some cases, why the problem is occurring. For example, suppose you recorded 242 failed audio/video sessions during a given day. If you look at the Failure Distribution Report, it might show that 237 of those failed sessions took place in your Dublin pool. That gives you a good place to start when it comes to tracking down and diagnosing the causes behind those failures. If you click on the Dublin pool under the **Top pools** category, you will see a Failure Distribution Report just for that pool. You can then begin analyzing why the Dublin pool was experiencing so many difficulties.</span></span>

<div>

## <a name="viewing-the-failure-distribution-report"></a><span data-ttu-id="fbe4b-119">エラー分布レポートを表示する</span><span class="sxs-lookup"><span data-stu-id="fbe4b-119">Viewing the Failure Distribution Report</span></span>

<span data-ttu-id="fbe4b-120">以下の任意のレポートで、[**予期されるエラー ボリューム**] または [**予期しないエラー ボリューム**] 測定基準をクリックすることにより、エラー分布レポートにアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="fbe4b-120">You can access the Failure Distribution Report from any of the following reports by clicking either the **Expected failure volume** or the **Unexpected failure volume** metric:</span></span>

  - [<span data-ttu-id="fbe4b-121">Lync Server 2013 のトップエラーレポート</span><span class="sxs-lookup"><span data-stu-id="fbe4b-121">Top Failures Report in Lync Server 2013</span></span>](lync-server-2013-top-failures-report.md)

  - [<span data-ttu-id="fbe4b-122">Lync Server 2013 の電話会議診断レポート</span><span class="sxs-lookup"><span data-stu-id="fbe4b-122">Conference Diagnostic Report in Lync Server 2013</span></span>](lync-server-2013-conference-diagnostic-report.md)

  - [<span data-ttu-id="fbe4b-123">Lync Server 2013 のピアツーピアアクティビティ診断レポート</span><span class="sxs-lookup"><span data-stu-id="fbe4b-123">Peer-to-Peer Activity Diagnostic Report in Lync Server 2013</span></span>](lync-server-2013-peer-to-peer-activity-diagnostic-report.md)

<span data-ttu-id="fbe4b-124">エラー分布レポートから、以下のいずれかの指標をクリックして、 [Lync Server 2013 のエラーリストレポート](lync-server-2013-failure-list-report.md)を表示できます。</span><span class="sxs-lookup"><span data-stu-id="fbe4b-124">From the Failure Distribution Report, you can click any of the following metrics to view the [Failure List Report in Lync Server 2013](lync-server-2013-failure-list-report.md):</span></span>

  - <span data-ttu-id="fbe4b-125">[トップの診断理由] (セッション)</span><span class="sxs-lookup"><span data-stu-id="fbe4b-125">Top diagnostic reasons (sessions)</span></span>

  - <span data-ttu-id="fbe4b-126">[トップ モダリティ] (セッション)</span><span class="sxs-lookup"><span data-stu-id="fbe4b-126">Top modalities (sessions)</span></span>

  - <span data-ttu-id="fbe4b-127">[トップ プール] (セッション))</span><span class="sxs-lookup"><span data-stu-id="fbe4b-127">Top pools (sessions)</span></span>

  - <span data-ttu-id="fbe4b-128">[トップ ソース] (セッション))</span><span class="sxs-lookup"><span data-stu-id="fbe4b-128">Top sources (sessions)</span></span>

  - <span data-ttu-id="fbe4b-129">[トップ コンポーネント] (セッション)</span><span class="sxs-lookup"><span data-stu-id="fbe4b-129">Top components (sessions)</span></span>

  - <span data-ttu-id="fbe4b-130">[トップの発信元ユーザー] (セッション)</span><span class="sxs-lookup"><span data-stu-id="fbe4b-130">Top from users (sessions)</span></span>

  - <span data-ttu-id="fbe4b-131">[トップの発信先ユーザー] (セッション)</span><span class="sxs-lookup"><span data-stu-id="fbe4b-131">Top to users (sessions)</span></span>

  - <span data-ttu-id="fbe4b-132">[送信元ユーザー エージェント] (セッション)</span><span class="sxs-lookup"><span data-stu-id="fbe4b-132">Top from user agents (sessions)</span></span>

</div>

<div>

## <a name="using-the-failure-distribution-report"></a><span data-ttu-id="fbe4b-133">エラー分布レポートを使用する</span><span class="sxs-lookup"><span data-stu-id="fbe4b-133">Using the Failure Distribution Report</span></span>

<span data-ttu-id="fbe4b-p102">モニターの大きさと画面解像度によっては、エラー分布レポートを画面上で表示するとき、表示されたデータの一部が切り捨てられることがあります。これは、特に、ユーザー エージェントのような非常に長いラベルを持つことがある測定基準で起きます。たとえば、"UCCAPI/4.0.7400.0 OC/4.0.7400.0 (Microsoft Lync 2013) " のような名前のユーザー エージェントは、以下のように一部分のみが画面上に表示されることがあります。</span><span class="sxs-lookup"><span data-stu-id="fbe4b-p102">Depending on your monitor size and screen resolution, it's possible that some of the data shown in the Failure Distribution Report might be truncated when you view it onscreen. This is especially true for metrics such as user agents, which can have very long labels. For example, a user agent with a name like "UCCAPI/4.0.7400.0 OC/4.0.7400.0 (Microsoft Lync 2013)" might only partially appear onscreen:</span></span>

<span data-ttu-id="fbe4b-137">UCCAPI/4.0.7400.0 OC/4.0.7400.0 (Microsoft Ly...</span><span class="sxs-lookup"><span data-stu-id="fbe4b-137">UCCAPI/4.0.7400.0 OC/4.0.7400.0 (Microsoft Ly...</span></span>

<span data-ttu-id="fbe4b-138">この場合、切り捨てられた値の上にマウス ポインターを置くだけでラベル全体を表示できます。</span><span class="sxs-lookup"><span data-stu-id="fbe4b-138">Fortunately, you can see the entire label simply by holding your mouse over the truncated value.</span></span>

<span data-ttu-id="fbe4b-p103">エラー分布レポートを使用してフィルター処理できる、役立つ測定基準の 1 つが診断 ID です。さまざまなレポートで同じ診断 ID が現れている場合、エラー分布レポートでその ID をフィルター処理して、問題の発生したセッション中に、その ID が報告された正確な場所と頻度についてきわめて詳細な情報を得られます。</span><span class="sxs-lookup"><span data-stu-id="fbe4b-p103">One interesting metric that you can filter on by using the Failure Distribution Report is Diagnostic ID. If you see the same Diagnostic ID cropping up in other reports you can filter on that ID in the Failure Distribution Report and get a very detailed look at exactly where, and how often, that ID has been reported during a failed session.</span></span>

</div>

<div>

## <a name="filters"></a><span data-ttu-id="fbe4b-141">フィルター</span><span class="sxs-lookup"><span data-stu-id="fbe4b-141">Filters</span></span>

<span data-ttu-id="fbe4b-p104">フィルターは、必要なデータのみに絞り込んだデータ セットを取得したり、取得したデータを別の方法で表示したりする方法として利用できます。たとえば、エラー分布レポートを使用すると、動作状況の種類 (ピアツーピア セッションまたは電話会議セッション) などにフィルターを適用できます。また、失敗した各セッションに添付される診断 ID によってフィルターを適用することもできます。</span><span class="sxs-lookup"><span data-stu-id="fbe4b-p104">Filters provide a way for you to return a more finely-targeted set of data or to view the returned data in different ways. For example, the Failed Distribution Report enables you to filter on such things as the activity type (peer-to-peer session or conferencing session) or by the diagnostic ID that accompanied each failed session.</span></span>

<span data-ttu-id="fbe4b-144">次の表に、エラー分布レポートで使用できるフィルターを示します。</span><span class="sxs-lookup"><span data-stu-id="fbe4b-144">The following table lists the filters that you can use with the Failure Distribution Report.</span></span>

### <a name="failure-distribution-report-filters"></a><span data-ttu-id="fbe4b-145">エラー分布レポートのフィルター</span><span class="sxs-lookup"><span data-stu-id="fbe4b-145">Failure Distribution Report Filters</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="fbe4b-146">名前</span><span class="sxs-lookup"><span data-stu-id="fbe4b-146">Name</span></span></th>
<th><span data-ttu-id="fbe4b-147">説明</span><span class="sxs-lookup"><span data-stu-id="fbe4b-147">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="fbe4b-148"><strong>From</strong></span><span class="sxs-lookup"><span data-stu-id="fbe4b-148"><strong>From</strong></span></span></p></td>
<td><p><span data-ttu-id="fbe4b-p105">時間範囲の開始日と開始時刻。データを時間単位で表示するには、次のように開始日と開始時刻の両方を入力します。</span><span class="sxs-lookup"><span data-stu-id="fbe4b-p105">Start date/time for the time range. To view data by hours, enter both the start date and time as follows:</span></span></p>
<p><span data-ttu-id="fbe4b-151">7/7/2012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="fbe4b-151">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="fbe4b-p106">開始時刻を入力しないと、レポートは自動的に指定日の午前 12:00 に開始します。データを日単位で表示するには、次のように日付のみを入力します。</span><span class="sxs-lookup"><span data-stu-id="fbe4b-p106">If you do not enter a start time, the report automatically begins at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="fbe4b-154">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="fbe4b-154">7/7/2012</span></span></p>
<p><span data-ttu-id="fbe4b-155">週単位または月単位で表示するには、表示する週または月の任意の日付を入力します (その週または月の最初の日である必要はありません)。</span><span class="sxs-lookup"><span data-stu-id="fbe4b-155">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="fbe4b-156">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="fbe4b-156">7/3/2012</span></span></p>
<p><span data-ttu-id="fbe4b-157">週は、常に日曜日から土曜日までです。</span><span class="sxs-lookup"><span data-stu-id="fbe4b-157">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fbe4b-158"><strong>To</strong></span><span class="sxs-lookup"><span data-stu-id="fbe4b-158"><strong>To</strong></span></span></p></td>
<td><p><span data-ttu-id="fbe4b-p107">時間範囲の終了日と終了時刻。データを時間単位で表示するには、次のように終了日と終了時刻の両方を入力します。</span><span class="sxs-lookup"><span data-stu-id="fbe4b-p107">End date/time for the time range. To view data by hours, enter both the end date and time as follows:</span></span></p>
<p><span data-ttu-id="fbe4b-161">7/7/2012 13:00</span><span class="sxs-lookup"><span data-stu-id="fbe4b-161">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="fbe4b-p108">終了時刻を入力しないと、レポートは自動的に指定日の午前 12:00 に終了します。データを日単位で表示するには、次のように日付のみを入力します。</span><span class="sxs-lookup"><span data-stu-id="fbe4b-p108">If you do not enter an end time, the report automatically ends at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="fbe4b-164">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="fbe4b-164">7/7/2012</span></span></p>
<p><span data-ttu-id="fbe4b-165">週単位または月単位で表示するには、表示する週または月の任意の日付を入力します (その週または月の最初の日である必要はありません)。</span><span class="sxs-lookup"><span data-stu-id="fbe4b-165">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="fbe4b-166">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="fbe4b-166">7/3/2012</span></span></p>
<p><span data-ttu-id="fbe4b-167">週は、常に日曜日から土曜日までです。</span><span class="sxs-lookup"><span data-stu-id="fbe4b-167">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fbe4b-168"><strong>Pool</strong></span><span class="sxs-lookup"><span data-stu-id="fbe4b-168"><strong>Pool</strong></span></span></p></td>
<td><p><span data-ttu-id="fbe4b-p109">レジストラー プールまたはエッジ サーバーの完全修飾ドメイン名 (FQDN)。個別のプールを選択するか、[<strong>すべて</strong>] をクリックしてすべてのプールのデータを表示できます。このドロップダウン リストは、データベース内のレコードに基づいて自動的に設定されます。</span><span class="sxs-lookup"><span data-stu-id="fbe4b-p109">Fully qualified domain name (FQDN) of the Registrar pool or Edge Server. You can either select an individual pool or click <strong>[All]</strong> to view data for all the pools. This drop-down list is automatically populated for you based on the records in the database.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fbe4b-172">[<strong>動作状況の種類</strong>]</span><span class="sxs-lookup"><span data-stu-id="fbe4b-172"><strong>Activity type</strong></span></span></p></td>
<td><p><span data-ttu-id="fbe4b-p110">フィルターを適用する動作状況の種類。次のいずれかを選択します。</span><span class="sxs-lookup"><span data-stu-id="fbe4b-p110">Type of activity to filter on. Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="fbe4b-175">いずれ</span><span class="sxs-lookup"><span data-stu-id="fbe4b-175">[All]</span></span></p></li>
<li><p><span data-ttu-id="fbe4b-176">ピアツーピア</span><span class="sxs-lookup"><span data-stu-id="fbe4b-176">Peer-to-peer</span></span></p></li>
<li><p><span data-ttu-id="fbe4b-177">室</span><span class="sxs-lookup"><span data-stu-id="fbe4b-177">Conference</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fbe4b-178">[<strong>セッション カテゴリ</strong>]</span><span class="sxs-lookup"><span data-stu-id="fbe4b-178"><strong>Session category</strong></span></span></p></td>
<td><p><span data-ttu-id="fbe4b-p111">問題のアクティビティが成功したか失敗したかを示します。次のいずれかを選択します。</span><span class="sxs-lookup"><span data-stu-id="fbe4b-p111">Indicates whether the activity in question succeeded or failed. Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="fbe4b-181">いずれ</span><span class="sxs-lookup"><span data-stu-id="fbe4b-181">[All]</span></span></p></li>
<li><p><span data-ttu-id="fbe4b-182">Success</span><span class="sxs-lookup"><span data-stu-id="fbe4b-182">Success</span></span></p></li>
<li><p><span data-ttu-id="fbe4b-183">[予期されたエラー]</span><span class="sxs-lookup"><span data-stu-id="fbe4b-183">Expected failure</span></span></p></li>
<li><p><span data-ttu-id="fbe4b-184">[予期しないエラー]</span><span class="sxs-lookup"><span data-stu-id="fbe4b-184">Unexpected failure</span></span></p></li>
</ul>
<p><span data-ttu-id="fbe4b-185">&quot;予期される&quot;エラーは、発生が予想されるエラーです。</span><span class="sxs-lookup"><span data-stu-id="fbe4b-185">An &quot;expected failure&quot; is a failure that is expected to happen.</span></span> <span data-ttu-id="fbe4b-186">たとえば、ユーザーが応答不可のステータスを設定した場合、そのユーザーへの呼び出しはエラーとなることが予期されます。</span><span class="sxs-lookup"><span data-stu-id="fbe4b-186">For example, if a user has set his or her status to Do Not Disturb you would expect any call to that user to fail.</span></span> <span data-ttu-id="fbe4b-187">&quot;予期しない&quot;エラーとは、正常なシステムとして表示されるエラーです。</span><span class="sxs-lookup"><span data-stu-id="fbe4b-187">An &quot;unexpected failure&quot; is a failure that occurs in what would appear to be an otherwise healthy system.</span></span> <span data-ttu-id="fbe4b-188">たとえば、発信者が保留にされたときに、通話が終了してはなりません。</span><span class="sxs-lookup"><span data-stu-id="fbe4b-188">For example, a call should not be terminated if the caller is placed on hold.</span></span> <span data-ttu-id="fbe4b-189">そのような状態が発生する場合は、予期しないエラーとしてフラグが設定されます。</span><span class="sxs-lookup"><span data-stu-id="fbe4b-189">If that occurs, that would be flagged as an unexpected failure.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fbe4b-190">[<strong>診断 ID</strong>]</span><span class="sxs-lookup"><span data-stu-id="fbe4b-190"><strong>Diagnostic ID</strong></span></span></p></td>
<td><p><span data-ttu-id="fbe4b-p113">SIP メッセージに添付される一意の識別子 (ms-diagnostics ヘッダー形式)。その情報は、多くの場合、エラーのトラブルシューティングに役立ちます。診断ヘッダーはオプションで (このヘッダーを含まない SIP セッションがある可能性もあります)、診断 ID は、何らかの問題が生じたセッションについてのみ報告されます。</span><span class="sxs-lookup"><span data-stu-id="fbe4b-p113">Unique identifier (in the form of an ms-diagnostics header) attached to a SIP message that often provides information useful in troubleshooting errors. Diagnostics headers are optional (it is possible to have SIP sessions that do not include these headers), and diagnostic IDs are reported only for sessions that experienced problems of some kind.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-top-diagnostic-reasons"></a><span data-ttu-id="fbe4b-193">トップの診断理由の指標</span><span class="sxs-lookup"><span data-stu-id="fbe4b-193">Metrics for Top Diagnostic Reasons</span></span>

<span data-ttu-id="fbe4b-194">次の表に、最も報告される頻度が高い診断 ID に基づいて、エラー分布レポートで提供される情報を示します。</span><span class="sxs-lookup"><span data-stu-id="fbe4b-194">The following table lists the information provided in the Failure Distribution Report based on the most frequently reported diagnostic ID.</span></span>

### <a name="metrics-for-top-diagnostic-reasons"></a><span data-ttu-id="fbe4b-195">トップの診断理由の指標</span><span class="sxs-lookup"><span data-stu-id="fbe4b-195">Metrics for Top Diagnostic Reasons</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="fbe4b-196">名前</span><span class="sxs-lookup"><span data-stu-id="fbe4b-196">Name</span></span></th>
<th><span data-ttu-id="fbe4b-197">この項目での並べ替え</span><span class="sxs-lookup"><span data-stu-id="fbe4b-197">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="fbe4b-198">説明</span><span class="sxs-lookup"><span data-stu-id="fbe4b-198">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="fbe4b-199"><strong>Rank</strong></span><span class="sxs-lookup"><span data-stu-id="fbe4b-199"><strong>Rank</strong></span></span></p></td>
<td><p><span data-ttu-id="fbe4b-200">いいえ</span><span class="sxs-lookup"><span data-stu-id="fbe4b-200">No</span></span></p></td>
<td><p><span data-ttu-id="fbe4b-p114">診断 ID に基づく、失敗したセッションの相対的なランク付け。診断 ID は、エラーのトラブルシューティングに役立つ情報の得られることが多い、SIP メッセージに添付された一意の識別子です (ms-diagnostics ヘッダーの形式)。</span><span class="sxs-lookup"><span data-stu-id="fbe4b-p114">Relative ranking of failed sessions based on diagnostic IDs. The diagnostic ID is a unique identifier (in the form of an ms-diagnostics header) attached to a SIP message that often provides information useful in troubleshooting errors.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fbe4b-203">[<strong>トップの診断理由</strong>]</span><span class="sxs-lookup"><span data-stu-id="fbe4b-203"><strong>Top diagnostic reasons</strong></span></span></p></td>
<td><p><span data-ttu-id="fbe4b-204">いいえ</span><span class="sxs-lookup"><span data-stu-id="fbe4b-204">No</span></span></p></td>
<td><p><span data-ttu-id="fbe4b-205">セッションで生成される診断 ID。</span><span class="sxs-lookup"><span data-stu-id="fbe4b-205">Diagnostic ID generated in a session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fbe4b-206"><strong>セッション</strong></span><span class="sxs-lookup"><span data-stu-id="fbe4b-206"><strong>Sessions</strong></span></span></p></td>
<td><p><span data-ttu-id="fbe4b-207">いいえ</span><span class="sxs-lookup"><span data-stu-id="fbe4b-207">No</span></span></p></td>
<td><p><span data-ttu-id="fbe4b-208">指定された診断 ID が生成された、失敗したセッションの総数。</span><span class="sxs-lookup"><span data-stu-id="fbe4b-208">Total number of failed sessions where the specified diagnostic ID was generated.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-top-modalities"></a><span data-ttu-id="fbe4b-209">トップ モダリティの指標</span><span class="sxs-lookup"><span data-stu-id="fbe4b-209">Metrics for Top Modalities</span></span>

<span data-ttu-id="fbe4b-210">次の表に、最もエラーが発生したセッション モダリティに基づいて、エラー分布レポートで提供される情報を示します。</span><span class="sxs-lookup"><span data-stu-id="fbe4b-210">The following table lists the information provided in the Failure Distribution Report based on the session modalities that experienced the most failures.</span></span>

### <a name="metrics-for-top-modalities"></a><span data-ttu-id="fbe4b-211">トップ モダリティの指標</span><span class="sxs-lookup"><span data-stu-id="fbe4b-211">Metrics for Top Modalities</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="fbe4b-212">名前</span><span class="sxs-lookup"><span data-stu-id="fbe4b-212">Name</span></span></th>
<th><span data-ttu-id="fbe4b-213">この項目での並べ替え</span><span class="sxs-lookup"><span data-stu-id="fbe4b-213">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="fbe4b-214">説明</span><span class="sxs-lookup"><span data-stu-id="fbe4b-214">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="fbe4b-215"><strong>Rank</strong></span><span class="sxs-lookup"><span data-stu-id="fbe4b-215"><strong>Rank</strong></span></span></p></td>
<td><p><span data-ttu-id="fbe4b-216">いいえ</span><span class="sxs-lookup"><span data-stu-id="fbe4b-216">No</span></span></p></td>
<td><p><span data-ttu-id="fbe4b-217">セッションの種類 (たとえば、音声ビデオ会議、ピアツーピアのファイル送信セッション) に基づく、失敗したセッションの相対的なランク付け。</span><span class="sxs-lookup"><span data-stu-id="fbe4b-217">Relative ranking based of failed session based on session type (for example, an audio/video conference or a peer-to-peer file transfer session).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fbe4b-218">[<strong>トップ モダリティ</strong>]</span><span class="sxs-lookup"><span data-stu-id="fbe4b-218"><strong>Top modalities</strong></span></span></p></td>
<td><p><span data-ttu-id="fbe4b-219">いいえ</span><span class="sxs-lookup"><span data-stu-id="fbe4b-219">No</span></span></p></td>
<td><p><span data-ttu-id="fbe4b-220">セッションの種類。</span><span class="sxs-lookup"><span data-stu-id="fbe4b-220">Session type.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fbe4b-221"><strong>セッション</strong></span><span class="sxs-lookup"><span data-stu-id="fbe4b-221"><strong>Sessions</strong></span></span></p></td>
<td><p><span data-ttu-id="fbe4b-222">いいえ</span><span class="sxs-lookup"><span data-stu-id="fbe4b-222">No</span></span></p></td>
<td><p><span data-ttu-id="fbe4b-223">指定されたモダリティが含まれる失敗したセッションの総数。</span><span class="sxs-lookup"><span data-stu-id="fbe4b-223">Total number of failed sessions involving the specified modality.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-top-pools"></a><span data-ttu-id="fbe4b-224">トップ プールの指標</span><span class="sxs-lookup"><span data-stu-id="fbe4b-224">Metrics for Top Pools</span></span>

<span data-ttu-id="fbe4b-225">次の表に、最もエラーが発生したプールに基づいて、エラー分布レポートで提供される情報を示します。</span><span class="sxs-lookup"><span data-stu-id="fbe4b-225">The following table lists the information provided in the Failure Distribution Report based on the pools that experienced the most failures.</span></span>

### <a name="metrics-for-top-pools"></a><span data-ttu-id="fbe4b-226">トップ プールの指標</span><span class="sxs-lookup"><span data-stu-id="fbe4b-226">Metrics for Top Pools</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="fbe4b-227">名前</span><span class="sxs-lookup"><span data-stu-id="fbe4b-227">Name</span></span></th>
<th><span data-ttu-id="fbe4b-228">この項目での並べ替え</span><span class="sxs-lookup"><span data-stu-id="fbe4b-228">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="fbe4b-229">説明</span><span class="sxs-lookup"><span data-stu-id="fbe4b-229">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="fbe4b-230"><strong>Rank</strong></span><span class="sxs-lookup"><span data-stu-id="fbe4b-230"><strong>Rank</strong></span></span></p></td>
<td><p><span data-ttu-id="fbe4b-231">いいえ</span><span class="sxs-lookup"><span data-stu-id="fbe4b-231">No</span></span></p></td>
<td><p><span data-ttu-id="fbe4b-232">セッションが実施されたレジストラープールまたはエッジサーバーに基づく、失敗したセッションの相対的なランク付け。</span><span class="sxs-lookup"><span data-stu-id="fbe4b-232">Relative ranking of failed sessions based on the Registrar pool or Edge Server where the session was conducted.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fbe4b-233">[<strong>トップ プール</strong>]</span><span class="sxs-lookup"><span data-stu-id="fbe4b-233"><strong>Top pools</strong></span></span></p></td>
<td><p><span data-ttu-id="fbe4b-234">いいえ</span><span class="sxs-lookup"><span data-stu-id="fbe4b-234">No</span></span></p></td>
<td><p><span data-ttu-id="fbe4b-235">レジストラープールまたはエッジサーバーの名前。</span><span class="sxs-lookup"><span data-stu-id="fbe4b-235">Name of the Registrar pool or Edge Server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fbe4b-236"><strong>セッション</strong></span><span class="sxs-lookup"><span data-stu-id="fbe4b-236"><strong>Sessions</strong></span></span></p></td>
<td><p><span data-ttu-id="fbe4b-237">いいえ</span><span class="sxs-lookup"><span data-stu-id="fbe4b-237">No</span></span></p></td>
<td><p><span data-ttu-id="fbe4b-238">レジストラープールまたはエッジサーバーあたりの失敗したセッションの合計数。</span><span class="sxs-lookup"><span data-stu-id="fbe4b-238">Total number of failed sessions per Registrar pool or Edge Server.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-top-sources"></a><span data-ttu-id="fbe4b-239">トップ ソースの指標</span><span class="sxs-lookup"><span data-stu-id="fbe4b-239">Metrics for Top Sources</span></span>

<span data-ttu-id="fbe4b-240">次の表に、最もエラーが発生したコンピューターに基づいて、エラー分布レポートで提供される情報を示します。</span><span class="sxs-lookup"><span data-stu-id="fbe4b-240">The following table lists the information provided in the Failure Distribution Report based on the computers that experienced the most failures.</span></span>

### <a name="metrics-for-top-sources"></a><span data-ttu-id="fbe4b-241">トップ ソースの指標</span><span class="sxs-lookup"><span data-stu-id="fbe4b-241">Metrics for Top Sources</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="fbe4b-242">名前</span><span class="sxs-lookup"><span data-stu-id="fbe4b-242">Name</span></span></th>
<th><span data-ttu-id="fbe4b-243">この項目での並べ替え</span><span class="sxs-lookup"><span data-stu-id="fbe4b-243">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="fbe4b-244">説明</span><span class="sxs-lookup"><span data-stu-id="fbe4b-244">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="fbe4b-245"><strong>Rank</strong></span><span class="sxs-lookup"><span data-stu-id="fbe4b-245"><strong>Rank</strong></span></span></p></td>
<td><p><span data-ttu-id="fbe4b-246">いいえ</span><span class="sxs-lookup"><span data-stu-id="fbe4b-246">No</span></span></p></td>
<td><p><span data-ttu-id="fbe4b-247">コンピューターごとの失敗したセッションの相対的なランク付け。</span><span class="sxs-lookup"><span data-stu-id="fbe4b-247">Relative ranking failed sessions per computer.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fbe4b-248">[<strong>トップ ソース</strong>]</span><span class="sxs-lookup"><span data-stu-id="fbe4b-248"><strong>Top sources</strong></span></span></p></td>
<td><p><span data-ttu-id="fbe4b-249">いいえ</span><span class="sxs-lookup"><span data-stu-id="fbe4b-249">No</span></span></p></td>
<td><p><span data-ttu-id="fbe4b-250">失敗したセッションに含まれるコンピューターの名前。</span><span class="sxs-lookup"><span data-stu-id="fbe4b-250">Name of the computer involved in the failed session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fbe4b-251"><strong>セッション</strong></span><span class="sxs-lookup"><span data-stu-id="fbe4b-251"><strong>Sessions</strong></span></span></p></td>
<td><p><span data-ttu-id="fbe4b-252">いいえ</span><span class="sxs-lookup"><span data-stu-id="fbe4b-252">No</span></span></p></td>
<td><p><span data-ttu-id="fbe4b-253">コンピューターごとの失敗したセッションの総数。</span><span class="sxs-lookup"><span data-stu-id="fbe4b-253">Total number of failed sessions per computer.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-top-components"></a><span data-ttu-id="fbe4b-254">トップ コンポーネントの指標</span><span class="sxs-lookup"><span data-stu-id="fbe4b-254">Metrics for Top Components</span></span>

<span data-ttu-id="fbe4b-255">次の表に、最もエラーが発生した Microsoft Lync Server 2010 コンポーネントに基づいて、エラー分布レポートで提供される情報を示します。</span><span class="sxs-lookup"><span data-stu-id="fbe4b-255">The following table lists the information provided in the Failure Distribution Report based on the Microsoft Lync Server 2010 components that experienced the most failures.</span></span>

### <a name="metrics-for-top-components"></a><span data-ttu-id="fbe4b-256">トップ コンポーネントの指標</span><span class="sxs-lookup"><span data-stu-id="fbe4b-256">Metrics for Top Components</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="fbe4b-257">名前</span><span class="sxs-lookup"><span data-stu-id="fbe4b-257">Name</span></span></th>
<th><span data-ttu-id="fbe4b-258">この項目での並べ替え</span><span class="sxs-lookup"><span data-stu-id="fbe4b-258">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="fbe4b-259">説明</span><span class="sxs-lookup"><span data-stu-id="fbe4b-259">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="fbe4b-260"><strong>Rank</strong></span><span class="sxs-lookup"><span data-stu-id="fbe4b-260"><strong>Rank</strong></span></span></p></td>
<td><p><span data-ttu-id="fbe4b-261">いいえ</span><span class="sxs-lookup"><span data-stu-id="fbe4b-261">No</span></span></p></td>
<td><p><span data-ttu-id="fbe4b-262">Lync Server 2010 コンポーネント (ExumRouting、GroupChat、MediationServer など) に基づく、失敗したセッションの相対的なランク付け。</span><span class="sxs-lookup"><span data-stu-id="fbe4b-262">Relative ranking of failed sessions based on Lync Server 2010 component (for example, ExumRouting, GroupChat, or MediationServer).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fbe4b-263">[<strong>トップ コンポーネント</strong>]</span><span class="sxs-lookup"><span data-stu-id="fbe4b-263"><strong>Top components</strong></span></span></p></td>
<td><p><span data-ttu-id="fbe4b-264">いいえ</span><span class="sxs-lookup"><span data-stu-id="fbe4b-264">No</span></span></p></td>
<td><p><span data-ttu-id="fbe4b-265">失敗したセッションに含まれるコンポーネントの名前。</span><span class="sxs-lookup"><span data-stu-id="fbe4b-265">Name of the component involved in the failed session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fbe4b-266"><strong>セッション</strong></span><span class="sxs-lookup"><span data-stu-id="fbe4b-266"><strong>Sessions</strong></span></span></p></td>
<td><p><span data-ttu-id="fbe4b-267">いいえ</span><span class="sxs-lookup"><span data-stu-id="fbe4b-267">No</span></span></p></td>
<td><p><span data-ttu-id="fbe4b-268">コンポーネントごとの失敗したセッションの総数。</span><span class="sxs-lookup"><span data-stu-id="fbe4b-268">Total number of failed sessions per component.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-top-from-users"></a><span data-ttu-id="fbe4b-269">トップの発信元ユーザーの指標</span><span class="sxs-lookup"><span data-stu-id="fbe4b-269">Metrics for Top From Users</span></span>

<span data-ttu-id="fbe4b-270">次の表に、他のユーザーを呼び出したときに最もエラーが発生したユーザー ("発信元" ユーザーと呼ばれる) に基づいて、エラー分布レポートで提供される情報を示します。</span><span class="sxs-lookup"><span data-stu-id="fbe4b-270">The following table lists the information provided in the Failure Distribution Report based on users who experienced the most failures when they tried to call someone else (known as "From" users).</span></span>

### <a name="metrics-for-top-from-users"></a><span data-ttu-id="fbe4b-271">トップの発信元ユーザーの指標</span><span class="sxs-lookup"><span data-stu-id="fbe4b-271">Metrics for Top From Users</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="fbe4b-272">名前</span><span class="sxs-lookup"><span data-stu-id="fbe4b-272">Name</span></span></th>
<th><span data-ttu-id="fbe4b-273">この項目での並べ替え</span><span class="sxs-lookup"><span data-stu-id="fbe4b-273">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="fbe4b-274">説明</span><span class="sxs-lookup"><span data-stu-id="fbe4b-274">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="fbe4b-275"><strong>Rank</strong></span><span class="sxs-lookup"><span data-stu-id="fbe4b-275"><strong>Rank</strong></span></span></p></td>
<td><p><span data-ttu-id="fbe4b-276">いいえ</span><span class="sxs-lookup"><span data-stu-id="fbe4b-276">No</span></span></p></td>
<td><p><span data-ttu-id="fbe4b-277">セッションに招待されたユーザーに基づく、失敗したセッションの相対的なランク付け。</span><span class="sxs-lookup"><span data-stu-id="fbe4b-277">Relative ranking of failed sessions based on the user who was invited to join the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fbe4b-278">[<strong>トップの発信元ユーザー</strong>]</span><span class="sxs-lookup"><span data-stu-id="fbe4b-278"><strong>Top from users</strong></span></span></p></td>
<td><p><span data-ttu-id="fbe4b-279">いいえ</span><span class="sxs-lookup"><span data-stu-id="fbe4b-279">No</span></span></p></td>
<td><p><span data-ttu-id="fbe4b-280">セッションに招待されたユーザーの SIP アドレス。</span><span class="sxs-lookup"><span data-stu-id="fbe4b-280">SIP address of the user invited to join the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fbe4b-281"><strong>セッション</strong></span><span class="sxs-lookup"><span data-stu-id="fbe4b-281"><strong>Sessions</strong></span></span></p></td>
<td><p><span data-ttu-id="fbe4b-282">いいえ</span><span class="sxs-lookup"><span data-stu-id="fbe4b-282">No</span></span></p></td>
<td><p><span data-ttu-id="fbe4b-283">ユーザーごとの失敗したセッションの総数。</span><span class="sxs-lookup"><span data-stu-id="fbe4b-283">Total number of failed sessions per user.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-top-to-users"></a><span data-ttu-id="fbe4b-284">トップの発信先ユーザーの指標</span><span class="sxs-lookup"><span data-stu-id="fbe4b-284">Metrics for Top To Users</span></span>

<span data-ttu-id="fbe4b-285">次の表に、ユーザーが他のユーザーを呼び出したときに最もエラーが発生したユーザー ("発信先" ユーザーと呼ばれる) に基づいて、エラー分布レポートで提供される情報を示します。</span><span class="sxs-lookup"><span data-stu-id="fbe4b-285">The following table lists the information provided in the Failure Distribution Report based on the users who experienced the most failures when another user tried to call them (known as "To" users).</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="fbe4b-286">名前</span><span class="sxs-lookup"><span data-stu-id="fbe4b-286">Name</span></span></th>
<th><span data-ttu-id="fbe4b-287">この項目での並べ替え</span><span class="sxs-lookup"><span data-stu-id="fbe4b-287">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="fbe4b-288">説明</span><span class="sxs-lookup"><span data-stu-id="fbe4b-288">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="fbe4b-289"><strong>Rank</strong></span><span class="sxs-lookup"><span data-stu-id="fbe4b-289"><strong>Rank</strong></span></span></p></td>
<td><p><span data-ttu-id="fbe4b-290">いいえ</span><span class="sxs-lookup"><span data-stu-id="fbe4b-290">No</span></span></p></td>
<td><p><span data-ttu-id="fbe4b-291">セッションを開始したユーザーに基づく、失敗したセッションの相対的なランク付け。</span><span class="sxs-lookup"><span data-stu-id="fbe4b-291">Relative ranking of failed sessions based on the user who initiated the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fbe4b-292">[<strong>トップの発信先ユーザー</strong></span><span class="sxs-lookup"><span data-stu-id="fbe4b-292"><strong>Top to users</strong></span></span></p></td>
<td><p><span data-ttu-id="fbe4b-293">いいえ</span><span class="sxs-lookup"><span data-stu-id="fbe4b-293">No</span></span></p></td>
<td><p><span data-ttu-id="fbe4b-294">セッションを開始したユーザーの SIP アドレス。</span><span class="sxs-lookup"><span data-stu-id="fbe4b-294">SIP address of the user who initiated the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fbe4b-295"><strong>セッション</strong></span><span class="sxs-lookup"><span data-stu-id="fbe4b-295"><strong>Sessions</strong></span></span></p></td>
<td><p><span data-ttu-id="fbe4b-296">いいえ</span><span class="sxs-lookup"><span data-stu-id="fbe4b-296">No</span></span></p></td>
<td><p><span data-ttu-id="fbe4b-297">ユーザーごとの失敗したセッションの総数。</span><span class="sxs-lookup"><span data-stu-id="fbe4b-297">Total number of failed sessions per user.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-top-user-agents"></a><span data-ttu-id="fbe4b-298">トップ ユーザー エージェントの指標</span><span class="sxs-lookup"><span data-stu-id="fbe4b-298">Metrics for Top User Agents</span></span>

<span data-ttu-id="fbe4b-299">次の表に、最もエラーが発生したエンドポイント ソフトウェアに基づいて、エラー分布レポートで提供される情報を示します。</span><span class="sxs-lookup"><span data-stu-id="fbe4b-299">The following table lists the information provided in the Failure Distribution Report based on the endpoint software that experienced the most failures.</span></span>

### <a name="metrics-for-top-user-agents"></a><span data-ttu-id="fbe4b-300">トップ ユーザー エージェントの指標</span><span class="sxs-lookup"><span data-stu-id="fbe4b-300">Metrics for Top User Agents</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="fbe4b-301">名前</span><span class="sxs-lookup"><span data-stu-id="fbe4b-301">Name</span></span></th>
<th><span data-ttu-id="fbe4b-302">この項目での並べ替え</span><span class="sxs-lookup"><span data-stu-id="fbe4b-302">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="fbe4b-303">説明</span><span class="sxs-lookup"><span data-stu-id="fbe4b-303">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="fbe4b-304"><strong>Rank</strong></span><span class="sxs-lookup"><span data-stu-id="fbe4b-304"><strong>Rank</strong></span></span></p></td>
<td><p><span data-ttu-id="fbe4b-305">いいえ</span><span class="sxs-lookup"><span data-stu-id="fbe4b-305">No</span></span></p></td>
<td><p><span data-ttu-id="fbe4b-p115">セッションに含まれるユーザー エージェント (ソフトウェア) に基づく、失敗したセッションの相対的なランク付け。例: RTCC/4.0.0.0 Inbound Routing/4.0.0.0。</span><span class="sxs-lookup"><span data-stu-id="fbe4b-p115">Relative ranking of failed sessions based on the user agent (software) involved in the session. For example: RTCC/4.0.0.0 Inbound Routing/4.0.0.0.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fbe4b-308">[<strong>トップ ユーザー エージェント</strong>]</span><span class="sxs-lookup"><span data-stu-id="fbe4b-308"><strong>Top user agents</strong></span></span></p></td>
<td><p><span data-ttu-id="fbe4b-309">いいえ</span><span class="sxs-lookup"><span data-stu-id="fbe4b-309">No</span></span></p></td>
<td><p><span data-ttu-id="fbe4b-310">失敗したセッションに含まれるユーザー エージェントの名前。</span><span class="sxs-lookup"><span data-stu-id="fbe4b-310">Name of the user agent involved in the failed session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fbe4b-311"><strong>セッション</strong></span><span class="sxs-lookup"><span data-stu-id="fbe4b-311"><strong>Sessions</strong></span></span></p></td>
<td><p><span data-ttu-id="fbe4b-312">いいえ</span><span class="sxs-lookup"><span data-stu-id="fbe4b-312">No</span></span></p></td>
<td><p><span data-ttu-id="fbe4b-313">ユーザー エージェントごとの失敗したセッションの総数。</span><span class="sxs-lookup"><span data-stu-id="fbe4b-313">Total number of failed sessions per user agent.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

