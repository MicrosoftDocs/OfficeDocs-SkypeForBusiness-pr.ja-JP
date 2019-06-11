---
title: 'Lync Server 2013: 監視ダッシュボードの使用'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Using the Monitoring Dashboard
ms:assetid: e00e5783-116f-481f-ad17-3af847d6769a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721905(v=OCS.15)
ms:contentKeyID: 49733839
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 50c5a435baf9ef6b2ef24e235270326507b68789
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34848257"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="using-the-monitoring-dashboard-in-lync-server-2013"></a><span data-ttu-id="d4f14-102">Lync Server 2013 での監視ダッシュボードの使用</span><span class="sxs-lookup"><span data-stu-id="d4f14-102">Using the Monitoring Dashboard in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d4f14-103">_**最終更新日:** 2014-02-05_</span><span class="sxs-lookup"><span data-stu-id="d4f14-103">_**Topic Last Modified:** 2014-02-05_</span></span>

<span data-ttu-id="d4f14-104">監視ダッシュボードでは、管理者は Microsoft Lync Server 2013 システム正常性とシステム使用率の概要を簡単に説明します。</span><span class="sxs-lookup"><span data-stu-id="d4f14-104">The Monitoring Dashboard provides administrators with a quick overview of their Microsoft Lync Server 2013 system health and system usage.</span></span> <span data-ttu-id="d4f14-105">このダッシュボードは、主要なシステム指標の集計ビューを表示するように設計されており、次のいずれかを表示します。</span><span class="sxs-lookup"><span data-stu-id="d4f14-105">The Dashboard is designed to show an aggregate view of key system metrics and to do so by displaying either:</span></span>

  - <span data-ttu-id="d4f14-p102">現在の日付の合計。現在の日付で表示される値は、夜中 12 時から現在の時刻 (レポート サーバーのローカル時刻に基づく) までに記録されたデータを表すことに注意してください。つまり、通常は、24 時間ではなく、特定の日付のデータが表示されます。たとえば、サーバーのローカル時刻が午前 8 時の場合、深夜 12 時から現在の時刻の午前 8 時の間には 8 時間あるので、8 時間分のデータが表示されます。</span><span class="sxs-lookup"><span data-stu-id="d4f14-p102">Totals for the current day. Note that values shown for the current day represent data that has been recorded from midnight until the current time (based on the local time of the reporting server). That means that you will typically be viewing data for a partial day and not for a 24-hour period. For example, if the local time of the server is 8:00 AM, you see eight hours’ worth of data because there are eight hours between midnight and the current time of 8:00 AM.</span></span>

  - <span data-ttu-id="d4f14-110">週の合計と過去 6 週間の傾向の合計。</span><span class="sxs-lookup"><span data-stu-id="d4f14-110">Totals for the week, and trend totals for the past six weeks.</span></span>

  - <span data-ttu-id="d4f14-111">月の合計と過去 6 か月の傾向の合計 (システム使用状況のみ)。</span><span class="sxs-lookup"><span data-stu-id="d4f14-111">Totals for the month, and trend totals for the past six months (for system usage only).</span></span>

<span data-ttu-id="d4f14-112">次に、ユーザーが Lync Server 2013 の監視レポートにアクセスするために使用する URL を返すための[Get-CsReportingConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsReportingConfiguration)コマンドレットを使用することができます。</span><span class="sxs-lookup"><span data-stu-id="d4f14-112">Note that you can use the [Get-CsReportingConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsReportingConfiguration) cmdlet to return the URL used for accessing Lync Server 2013 Monitoring Reports:</span></span>

    Get-CsReportingConfiguration

<span data-ttu-id="d4f14-113">既定では、監視ダッシュボードは、現在の週の次の指標 (および過去 6 週間の傾向の合計) を表示します。</span><span class="sxs-lookup"><span data-stu-id="d4f14-113">By default, the Monitoring Dashboard shows data for the following metrics for the current week (and trend totals for the previous six weeks):</span></span>

<div>

## <a name="system-usage-metrics"></a><span data-ttu-id="d4f14-114">システム使用状況の指標</span><span class="sxs-lookup"><span data-stu-id="d4f14-114">System Usage Metrics</span></span>

<span data-ttu-id="d4f14-115">**登録**</span><span class="sxs-lookup"><span data-stu-id="d4f14-115">**Registration**</span></span>

  - <span data-ttu-id="d4f14-116">一意のユーザー ログオン</span><span class="sxs-lookup"><span data-stu-id="d4f14-116">Unique user logons</span></span>

<span data-ttu-id="d4f14-117">**ピアツーピア**</span><span class="sxs-lookup"><span data-stu-id="d4f14-117">**Peer-to-peer**</span></span>

  - <span data-ttu-id="d4f14-118">セッションの合計数</span><span class="sxs-lookup"><span data-stu-id="d4f14-118">Total sessions</span></span>

  - <span data-ttu-id="d4f14-119">IM セッション</span><span class="sxs-lookup"><span data-stu-id="d4f14-119">IM sessions</span></span>

  - <span data-ttu-id="d4f14-120">音声セッション</span><span class="sxs-lookup"><span data-stu-id="d4f14-120">Audio sessions</span></span>

  - <span data-ttu-id="d4f14-121">ビデオ セッション</span><span class="sxs-lookup"><span data-stu-id="d4f14-121">Video sessions</span></span>

  - <span data-ttu-id="d4f14-122">アプリケーション共有</span><span class="sxs-lookup"><span data-stu-id="d4f14-122">Application sharing</span></span>

  - <span data-ttu-id="d4f14-123">音声セッションの合計時間 (分)</span><span class="sxs-lookup"><span data-stu-id="d4f14-123">Total audio session minutes</span></span>

  - <span data-ttu-id="d4f14-124">音声セッションの平均時間 (分)</span><span class="sxs-lookup"><span data-stu-id="d4f14-124">Avg. audio session minutes</span></span>

<span data-ttu-id="d4f14-125">**電話会議**</span><span class="sxs-lookup"><span data-stu-id="d4f14-125">**Conference**</span></span>

  - <span data-ttu-id="d4f14-126">電話会議の合計数</span><span class="sxs-lookup"><span data-stu-id="d4f14-126">Total conferences</span></span>

  - <span data-ttu-id="d4f14-127">IM 会議</span><span class="sxs-lookup"><span data-stu-id="d4f14-127">IM conferences</span></span>

  - <span data-ttu-id="d4f14-128">音声ビデオ会議</span><span class="sxs-lookup"><span data-stu-id="d4f14-128">A/V conferences</span></span>

  - <span data-ttu-id="d4f14-129">アプリケーション共有会議</span><span class="sxs-lookup"><span data-stu-id="d4f14-129">Application sharing conferences</span></span>

  - <span data-ttu-id="d4f14-130">Web 会議</span><span class="sxs-lookup"><span data-stu-id="d4f14-130">Web conferences</span></span>

  - <span data-ttu-id="d4f14-131">開催者の合計数</span><span class="sxs-lookup"><span data-stu-id="d4f14-131">Total organizers</span></span>

  - <span data-ttu-id="d4f14-132">音声ビデオ会議の合計時間 (分)</span><span class="sxs-lookup"><span data-stu-id="d4f14-132">Total A/V conference minutes</span></span>

  - <span data-ttu-id="d4f14-133">音声ビデオ会議の平均時間 (分)</span><span class="sxs-lookup"><span data-stu-id="d4f14-133">Avg. A/V conference minutes</span></span>

  - <span data-ttu-id="d4f14-134">PSTN 電話会議の合計数</span><span class="sxs-lookup"><span data-stu-id="d4f14-134">Total PSTN conferences</span></span>

  - <span data-ttu-id="d4f14-135">PSTN 参加者の合計数</span><span class="sxs-lookup"><span data-stu-id="d4f14-135">Total PSTN participants</span></span>

  - <span data-ttu-id="d4f14-136">PSTN 参加者の合計時間 (分)</span><span class="sxs-lookup"><span data-stu-id="d4f14-136">Total PSTN participant minutes</span></span>

<span data-ttu-id="d4f14-137">システム使用状況の指標に加えて、次の指標では、現在の日付および過去 6 日間の合計 ([**週ビュー**] を選択した場合)、または現在の週および過去 6 週間の合計 ([**月ビュー**] を選択した場合) が表示されます。</span><span class="sxs-lookup"><span data-stu-id="d4f14-137">In addition to the System Usage metrics, the following metrics displays total for the current day and the previous six days (if you select **Weekly View**) or for the current week and the past six weeks if you select **Monthly View**.</span></span>

</div>

<div>

## <a name="per-user-call-diagnostics"></a><span data-ttu-id="d4f14-138">ユーザーごとの通話診断</span><span class="sxs-lookup"><span data-stu-id="d4f14-138">Per-User Call Diagnostics</span></span>

<span data-ttu-id="d4f14-139">**通話障害が発生したユーザー**</span><span class="sxs-lookup"><span data-stu-id="d4f14-139">**Users with call failures**</span></span>

  - <span data-ttu-id="d4f14-140">通話障害が発生したユーザーの合計数</span><span class="sxs-lookup"><span data-stu-id="d4f14-140">Total users with call failures</span></span>

  - <span data-ttu-id="d4f14-141">通話障害が発生した電話会議の開催者</span><span class="sxs-lookup"><span data-stu-id="d4f14-141">Conference organizers with call failures</span></span>

<span data-ttu-id="d4f14-142">**低品質通話のユーザー**</span><span class="sxs-lookup"><span data-stu-id="d4f14-142">**Users with poor quality calls**</span></span>

  - <span data-ttu-id="d4f14-143">通話の品質が低いユーザーの合計数</span><span class="sxs-lookup"><span data-stu-id="d4f14-143">Total users with poor quality calls</span></span>

</div>

<div>

## <a name="call-diagnostics"></a><span data-ttu-id="d4f14-144">通話診断</span><span class="sxs-lookup"><span data-stu-id="d4f14-144">Call Diagnostics</span></span>

<span data-ttu-id="d4f14-145">ピアツーピア</span><span class="sxs-lookup"><span data-stu-id="d4f14-145">Peer-to-peer</span></span>

  - <span data-ttu-id="d4f14-146">エラー総数</span><span class="sxs-lookup"><span data-stu-id="d4f14-146">Total failures</span></span>

  - <span data-ttu-id="d4f14-147">総合エラー率</span><span class="sxs-lookup"><span data-stu-id="d4f14-147">Overall failure rate</span></span>

  - <span data-ttu-id="d4f14-148">IM エラー率</span><span class="sxs-lookup"><span data-stu-id="d4f14-148">IM failure rate</span></span>

  - <span data-ttu-id="d4f14-149">音声エラー率</span><span class="sxs-lookup"><span data-stu-id="d4f14-149">Audio failure rate</span></span>

  - <span data-ttu-id="d4f14-150">アプリケーション共有エラー率</span><span class="sxs-lookup"><span data-stu-id="d4f14-150">Application sharing failure rate</span></span>

<span data-ttu-id="d4f14-151">電話会議</span><span class="sxs-lookup"><span data-stu-id="d4f14-151">Conference</span></span>

  - <span data-ttu-id="d4f14-152">エラー総数</span><span class="sxs-lookup"><span data-stu-id="d4f14-152">Total failures</span></span>

  - <span data-ttu-id="d4f14-153">総合エラー率</span><span class="sxs-lookup"><span data-stu-id="d4f14-153">Overall failure rate</span></span>

  - <span data-ttu-id="d4f14-154">IM エラー率</span><span class="sxs-lookup"><span data-stu-id="d4f14-154">IM failure rate</span></span>

  - <span data-ttu-id="d4f14-155">音声ビデオ エラー率</span><span class="sxs-lookup"><span data-stu-id="d4f14-155">A/V failure rate</span></span>

  - <span data-ttu-id="d4f14-156">アプリケーション共有エラー率</span><span class="sxs-lookup"><span data-stu-id="d4f14-156">Application sharing failure rate</span></span>

<span data-ttu-id="d4f14-157">エラー セッション発生数の上位 5 サーバー</span><span class="sxs-lookup"><span data-stu-id="d4f14-157">Top five servers by failed sessions</span></span>

</div>

<div>

## <a name="media-quality-diagnostics"></a><span data-ttu-id="d4f14-158">メディア品質診断</span><span class="sxs-lookup"><span data-stu-id="d4f14-158">Media Quality Diagnostics</span></span>

<span data-ttu-id="d4f14-159">ピアツーピア</span><span class="sxs-lookup"><span data-stu-id="d4f14-159">Peer-to-peer</span></span>

  - <span data-ttu-id="d4f14-160">低品質通話の合計数</span><span class="sxs-lookup"><span data-stu-id="d4f14-160">Total poor quality calls</span></span>

  - <span data-ttu-id="d4f14-161">低品質通話のパーセンテージ</span><span class="sxs-lookup"><span data-stu-id="d4f14-161">Poor quality call percentage</span></span>

  - <span data-ttu-id="d4f14-162">低品質な PSTN 通話の数</span><span class="sxs-lookup"><span data-stu-id="d4f14-162">PSTN calls with poor quality</span></span>

<span data-ttu-id="d4f14-163">電話会議</span><span class="sxs-lookup"><span data-stu-id="d4f14-163">Conference</span></span>

  - <span data-ttu-id="d4f14-164">低品質通話の合計数</span><span class="sxs-lookup"><span data-stu-id="d4f14-164">Total poor quality calls</span></span>

  - <span data-ttu-id="d4f14-165">低品質通話のパーセンテージ</span><span class="sxs-lookup"><span data-stu-id="d4f14-165">Poor quality call percentage</span></span>

  - <span data-ttu-id="d4f14-166">低品質な PSTN 通話の数</span><span class="sxs-lookup"><span data-stu-id="d4f14-166">PSTN calls with poor quality</span></span>

<span data-ttu-id="d4f14-167">低品質通話パーセンテージの上位サーバー</span><span class="sxs-lookup"><span data-stu-id="d4f14-167">Top worst servers by poor quality call percentage</span></span>

</div>

<div>

## <a name="working-with-the-monitoring-dashboard"></a><span data-ttu-id="d4f14-168">監視ダッシュボードの操作</span><span class="sxs-lookup"><span data-stu-id="d4f14-168">Working with the Monitoring Dashboard</span></span>

<span data-ttu-id="d4f14-p103">既に説明したように、既定では、現在の週の合計と過去 6 週間の傾向値が表示されます。現在の月の合計 (および過去 6 か月の傾向値) を表示する場合は、ダッシュボードの右上隅にある [**月ビュー**] をクリックします。月の合計の表示を決定すると、リンク テキストが [**週ビュー**] に変わります。そのリンクをクリックすると、週ビューに再び切り替わります。</span><span class="sxs-lookup"><span data-stu-id="d4f14-p103">As noted, by default totals are shown for the current week and trend values are shown for the past six weeks. If you would prefer to see totals for the current month (as well as trend values for the past six months), click the **Monthly View** link in the upper right corner of the dashboard. If you decide to view monthly totals, the link text will change to **Weekly View**. You can switch back to the weekly view by clicking that link.</span></span>

<div>


> [!TIP]  
> <span data-ttu-id="d4f14-p104">監視ダッシュボードでは、現在の週 (または現在の月) の合計と過去 6 週間 (または過去 6 か月) の傾向値を表示するように制限されています。これらの日時を変更することはできません。たとえば、ダッシュボードを使用して、9 か月前から始まる期間のレポート合計を表示することはできません。</span><span class="sxs-lookup"><span data-stu-id="d4f14-p104">The Monitoring Dashboard restricts you to looking at totals for the current week (or month) and trend values for the past six weeks (or months). You cannot change these dates and times. For example, you cannot use the Dashboard to view report totals for the time period beginning nine months ago.</span></span>



</div>

<span data-ttu-id="d4f14-p105">[**今週**]、[**今月**]、または [**今日**] 列に表示される値は、アイテムに関する詳細情報にリンクされています。その列に表示される列名と値は、選択した指標、および週ビューまたは月ビューのどちらを選択したかに応じて異なることに注意してください。たとえば、[**一意のユーザー ログオン**] 指標で表示される合計をクリックした場合は、指定した期間の [**ユーザー登録レポート**] が表示されます。[**ダッシュボード**] をクリックすると、監視ダッシュボードにいつでも戻ることができます。</span><span class="sxs-lookup"><span data-stu-id="d4f14-p105">The values shown in the **This week**, **This month**, or **Today** columns link you to more detailed information about the item. Keep in mind that the column name and the values displayed in that column will often differ depending on the metric chosen and depending on whether you have selected weekly view or monthly view. For example, if you click the totals shown for the **Unique user logons** metric you will see the **User Registration Report** for the specified time period. You can return to the Monitoring Dashboard at any time by clicking **Dashboard**.</span></span>

<div>


> [!TIP]  
> <span data-ttu-id="d4f14-180">ダッシュボードの右上隅にある [<STRONG>レポート</STRONG>] リンクをクリックして、監視サーバーレポートのホームページにアクセスすることもできます。</span><span class="sxs-lookup"><span data-stu-id="d4f14-180">You can also access the Monitoring Server Reports home page by clicking the <STRONG>Reports</STRONG> link in the upper right corner of the Dashboard.</span></span>



</div>

<span data-ttu-id="d4f14-181">[**傾向**] 列には、過去 6 週間 (または、指標および時間間隔に応じて、過去 6 日間または過去 6 か月) の合計を表す簡単な折れ線グラフが表示されます。</span><span class="sxs-lookup"><span data-stu-id="d4f14-181">The **Trend** column displays a simple line graph that shows totals for the past six weeks (or, depending on the metric and the time interval, the past six days or the past six months).</span></span> <span data-ttu-id="d4f14-182">これらの簡単な折れ線グラフは、各期間の 1 つの未分類のデータ点 (たとえば、過去 6 週間それぞれの 1 つの未分類のデータ点) を表示します。</span><span class="sxs-lookup"><span data-stu-id="d4f14-182">These simple line graphs display one unlabeled data point for each time period (for example, one unlabeled data point for each of the past six weeks).</span></span> <span data-ttu-id="d4f14-183">ただし、マウス ポインターをグラフ上に合わせると、これらのグラフの実際の値を取得できます。</span><span class="sxs-lookup"><span data-stu-id="d4f14-183">However, you can retrieve actual values for these graphs by holding your mouse pointer over the graph.</span></span> <span data-ttu-id="d4f14-184">この場合、ヒントにはグラフ内の最大値と最小値が表示されます。</span><span class="sxs-lookup"><span data-stu-id="d4f14-184">In that case, a tooltip shows you the maximum and minimum values in the graph.</span></span>

</div>

<div>

## <a name="exporting-data-from-the-monitoring-dashboard"></a><span data-ttu-id="d4f14-185">監視ダッシュボードからのデータ エクスポート</span><span class="sxs-lookup"><span data-stu-id="d4f14-185">Exporting Data from the Monitoring Dashboard</span></span>

<span data-ttu-id="d4f14-p107">監視ダッシュボードは、現在のダッシュボード ビューをエクスポートするさまざまな方法を備えています。ダッシュボードのツールバーには、緑の矢印が付いたフロッピー ディスクのように見えるアイコンがあります。このアイコンをクリックすると、次のデータ エクスポート形式がリストされたドロップダウン リストが表示されます。</span><span class="sxs-lookup"><span data-stu-id="d4f14-p107">The Monitoring Dashboard provides a number of ways to export the current dashboard view. On the Dashboard toolbar, you'll see an icon that looks like a floppy disk with a green arrow attached to it. If you click this icon, a dropdown list will appear giving you the following data export formats:</span></span>

  - <span data-ttu-id="d4f14-189">レポート データが含まれている XML ファイル</span><span class="sxs-lookup"><span data-stu-id="d4f14-189">XML file with report data</span></span>

  - <span data-ttu-id="d4f14-190">CSV (コンマ区切り)</span><span class="sxs-lookup"><span data-stu-id="d4f14-190">CSV (comma delimited)</span></span>

  - <span data-ttu-id="d4f14-191">PDF</span><span class="sxs-lookup"><span data-stu-id="d4f14-191">PDF</span></span>

  - <span data-ttu-id="d4f14-192">MHTML (Web アーカイブ)</span><span class="sxs-lookup"><span data-stu-id="d4f14-192">MHTML (web archive)</span></span>

  - <span data-ttu-id="d4f14-193">Excel</span><span class="sxs-lookup"><span data-stu-id="d4f14-193">Excel</span></span>

  - <span data-ttu-id="d4f14-194">TIFF ファイル</span><span class="sxs-lookup"><span data-stu-id="d4f14-194">TIFF file</span></span>

  - <span data-ttu-id="d4f14-195">Word</span><span class="sxs-lookup"><span data-stu-id="d4f14-195">Word</span></span>

<span data-ttu-id="d4f14-196">現在のダッシュボード ビュー (およびその値) をエクスポートするには、目的のエクスポート オプションをクリックします。</span><span class="sxs-lookup"><span data-stu-id="d4f14-196">To export the current dashboard view (and its values), click the desired export option.</span></span> <span data-ttu-id="d4f14-197">Lync Server 2013 は、指定された形式でレポートを生成し、そのレポートを開くか保存するかを選択できます。</span><span class="sxs-lookup"><span data-stu-id="d4f14-197">Lync Server 2013 generates a report in the specified format and then give you the option of opening that report or saving it.</span></span> <span data-ttu-id="d4f14-198">既定では、Lync Server によってレポート**監視ダッシュボード**のタイトルが設定され、[ダウンロード] フォルダーに保存されていることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="d4f14-198">Note that, by default, Lync Server titles the report **Monitoring Dashboard** and saves it to your Downloads folder.</span></span> <span data-ttu-id="d4f14-199">レポートに別の名前を付ける場合、またはレポートを異なるフォルダーに保存する場合は、[**保存**] ボタンの横にある矢印をクリックし、[**名前を付けて保存**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d4f14-199">To give the report a different name or to store it in a different folder, click the arrow next to the **Save** button and then click **Save As**.</span></span> <span data-ttu-id="d4f14-200">レポートを [**監視ダッシュボード**] という名前でダッシュボード フォルダーに保存しても問題ない場合は、[**保存**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d4f14-200">If you are fine with name **Monitoring Dashboard** and with having the report saved in the Downloads folder you can just click the **Save** button.</span></span>

<span data-ttu-id="d4f14-p109">ダッシュボード データをエクスポートしようとすると、[**セキュリティの警告**] ダイアログ ボックスと "現在のセキュリティ設定では、このファイルをダウンロードできません。" というメッセージが表示される可能性があります。このダイアログ ボックスとメッセージが表示された場合は、次の操作を実行してください。</span><span class="sxs-lookup"><span data-stu-id="d4f14-p109">It's possible that, when you try to export dashboard data, a **Security Alert** dialog box will appear along with the message "Your current settings do not allow this file to be downloaded." If that occurs, do the following:</span></span>

  - <span data-ttu-id="d4f14-203">Internet Explorer で、[**インターネット オプション**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d4f14-203">In Internet Explorer, select **Internet Options**.</span></span>

  - <span data-ttu-id="d4f14-204">[**インターネット オプション**] ダイアログ ボックスの [**セキュリティ**] タブで、[**信頼済みサイト**] をクリックし、[**サイト**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d4f14-204">In the **Internet Options** dialog box, on the **Security** tab, click **Trusted sites** and then click **Sites**.</span></span>

  - <span data-ttu-id="d4f14-205">[**信頼済みサイト**] ダイアログボックスの [**追加**] をクリックして、lync server 2013 レポートを実行している lync server 2013 を信頼済み web サイトのコレクションに追加します。</span><span class="sxs-lookup"><span data-stu-id="d4f14-205">In the **Trusted sites** dialog box, click **Add** to add the Lync Server 2013 that is running Lync Server 2013 Reports to the collections of trusted websites.</span></span>

  - <span data-ttu-id="d4f14-206">[**閉じる**] をクリックし、[**OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d4f14-206">Click **Close** and then click **OK**.</span></span>

<span data-ttu-id="d4f14-p110">次に、変更が反映される前に、監視ダッシュボードを更新する必要があります。監視ダッシュボードを更新するには、F5 キーを押すか、ダッシュボードのツールバーにある [**更新**] アイコンをクリックします ([**更新**] アイコンは緑の矢印のペアを囲んだ丸いアイコンです)。</span><span class="sxs-lookup"><span data-stu-id="d4f14-p110">You will then need to refresh the Monitoring Dashboard before the changes take effect. To do that, either press F5 or click the **Refresh** icon in the Dashboard toolbar. (The **Refresh** icon is a circle with a pair of green arrows in it.)</span></span>

<span data-ttu-id="d4f14-p111">最新の監視ダッシュボード データへのリンクがあるライブ データ フィードが含まれた Excel スプレッドシートを作成することもできます。ライブ データ フィードのファイルを作成するには、ツールバーにあるオレンジ色の [**データ フィードへのエクスポート**] アイコンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="d4f14-p111">You can also create an Excel spreadsheet that includes live data feeds, which includes links to the latest Monitoring Dashboard data. To create a live data feed file, click the orange **Export to Data Feed** icon in the toolbar.</span></span>

<span data-ttu-id="d4f14-212">現在のダッシュボードを印刷する場合は、ツールバーのプリンター アイコンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="d4f14-212">If you would prefer to print the current Dashboard then click the printer icon in the toolbar.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

