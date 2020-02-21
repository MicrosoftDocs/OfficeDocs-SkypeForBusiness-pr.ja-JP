---
title: 'Lync Server 2013: メディア品質概要レポート'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Media Quality Summary Report
ms:assetid: 8bd59ad6-3087-49c8-b692-5573fe2ffcd8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615012(v=OCS.15)
ms:contentKeyID: 48184776
ms.date: 06/29/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: edeec17bccc4c2084f71d3a052d3a44a34f4ed94
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/21/2020
ms.locfileid: "42185187"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="media-quality-summary-report-in-lync-server-2013"></a><span data-ttu-id="86cf9-102">Lync Server 2013 のメディア品質概要レポート</span><span class="sxs-lookup"><span data-stu-id="86cf9-102">Media Quality Summary Report in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="86cf9-103">_**トピックの最終更新日:** 2016-06-29_</span><span class="sxs-lookup"><span data-stu-id="86cf9-103">_**Topic Last Modified:** 2016-06-29_</span></span>

<span data-ttu-id="86cf9-104">メディア品質概要レポートは、組織での通話の品質を解析するのに最良の方法です。このレポートは、次のカテゴリに分類された詳細な QoE (Quality of Experience) 通話指標を提供します。</span><span class="sxs-lookup"><span data-stu-id="86cf9-104">The Media Quality Summary Report is perhaps your best bet for analyzing call quality in your organization: this report provides detailed Quality of Experience (QoE) call metrics broken down into the following categories:</span></span>

  - <span data-ttu-id="86cf9-105">UC ピアツーピア通話 (Microsoft Lync 2013 から Microsoft Lync 2013 通話)</span><span class="sxs-lookup"><span data-stu-id="86cf9-105">UC Peer to Peer Calls (such as a Microsoft Lync 2013 to Microsoft Lync 2013 call)</span></span>

  - <span data-ttu-id="86cf9-106">UC 電話会議セッション</span><span class="sxs-lookup"><span data-stu-id="86cf9-106">UC Conference Sessions</span></span>

  - <span data-ttu-id="86cf9-107">PSTN 電話会議セッション</span><span class="sxs-lookup"><span data-stu-id="86cf9-107">PSTN Conference Sessions</span></span>

  - <span data-ttu-id="86cf9-108">PSTN 通話: メディアのバイパス</span><span class="sxs-lookup"><span data-stu-id="86cf9-108">PSTN Calls: Media Bypass</span></span>

  - <span data-ttu-id="86cf9-109">PSTN 通話 (非バイパス): UC レグ</span><span class="sxs-lookup"><span data-stu-id="86cf9-109">PSTN Calls (Non-Bypass): UC Leg</span></span>

  - <span data-ttu-id="86cf9-110">PSTN 通話 (非バイパス): ゲートウェイ レグ</span><span class="sxs-lookup"><span data-stu-id="86cf9-110">PSTN Calls (Non-Bypass): Gateway Leg</span></span>

  - <span data-ttu-id="86cf9-111">その他の通話の種類</span><span class="sxs-lookup"><span data-stu-id="86cf9-111">Other Call Types</span></span>

<span data-ttu-id="86cf9-112">レポートを初めて開いたとき、これらの各カテゴリの概要情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="86cf9-112">When you first open the report, you see summary information for each of these categories.</span></span> <span data-ttu-id="86cf9-113">レポートを離れずに、各カテゴリを展開して、Office Communicator 2007 R2 から Lync 2013 の呼び出しなどのサブカテゴリを表示できます。</span><span class="sxs-lookup"><span data-stu-id="86cf9-113">Without leaving the report, you can expand each category to look at subcategories such as calls made from Office Communicator 2007 R2 to Lync 2013.</span></span> <span data-ttu-id="86cf9-114">また、これらのサブカテゴリにドリルダウンして、そのサブカテゴリ内の発信された各通話の詳細を表示できます。</span><span class="sxs-lookup"><span data-stu-id="86cf9-114">In turn, you can then drill down into these subcategories to see details about each call made within that subcategory.</span></span>

<span data-ttu-id="86cf9-115">Microsoft Lync Server 2013 のメディア品質概要レポートでは、データがさらに3つの種類の通話 (音声通話、ビデオ通話、およびアプリケーション共有通話) に分割されています。</span><span class="sxs-lookup"><span data-stu-id="86cf9-115">In Microsoft Lync Server 2013 the Media Quality Summary Report further breaks the data down into three call types: audio calls, video calls, and application sharing calls.</span></span> <span data-ttu-id="86cf9-116">通話の各種類について、独自のセクションがレポート内に設けられ、通話指標の独自のカスタム セットが用意されています。</span><span class="sxs-lookup"><span data-stu-id="86cf9-116">Each call type has its own section in the report, and its own custom set of call metrics.</span></span>

<span data-ttu-id="86cf9-117">メディア品質概要レポートでは、有線通話とワイヤレス通話、内部通話と外部通話、VPN 通話と非 VPN 通話を比較できるフィルターも適用できます。</span><span class="sxs-lookup"><span data-stu-id="86cf9-117">The Media Quality Summary Report also allows you to apply filters that enable you to compare the call quality of wired calls vs. wireless calls, internal calls vs. external calls, and VPN calls vs. non-VPN calls.</span></span>

<div>

## <a name="accessing-the-media-quality-summary-report"></a><span data-ttu-id="86cf9-118">メディア品質概要レポートへのアクセス</span><span class="sxs-lookup"><span data-stu-id="86cf9-118">Accessing the Media Quality Summary Report</span></span>

<span data-ttu-id="86cf9-119">メディア品質概要レポートには、監視レポートのホームページからアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="86cf9-119">The Media Quality Summary Report is accessed from the Monitoring Reports home page.</span></span> <span data-ttu-id="86cf9-120">次のいずれかの指標をクリックすると、 [Lync Server 2013 の通話リストレポート](lync-server-2013-call-list-report.md)にドリルダウンできます。</span><span class="sxs-lookup"><span data-stu-id="86cf9-120">You can drill down to the [Call List Report in Lync Server 2013](lync-server-2013-call-list-report.md) by clicking either of the following metrics:</span></span>

  - <span data-ttu-id="86cf9-121">[通話ボリューム]</span><span class="sxs-lookup"><span data-stu-id="86cf9-121">Call volume</span></span>

  - <span data-ttu-id="86cf9-122">[低品質通話のパーセンテージ]</span><span class="sxs-lookup"><span data-stu-id="86cf9-122">Poor call percentage</span></span>

<span data-ttu-id="86cf9-123">また、次のいずれかの音声通話指標をクリックすることによって、メディア品質メトリック分布レポートにアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="86cf9-123">In addition, you can access the Media Quality Metrics Distribution Report by clicking any of the following audio call metrics:</span></span>

  - <span data-ttu-id="86cf9-124">[往復 (ミリ秒)]</span><span class="sxs-lookup"><span data-stu-id="86cf9-124">Round trip (ms)</span></span>

  - <span data-ttu-id="86cf9-125">[低下 (MOS)]</span><span class="sxs-lookup"><span data-stu-id="86cf9-125">Degradation (MOS)</span></span>

  - <span data-ttu-id="86cf9-126">[パケット損失]</span><span class="sxs-lookup"><span data-stu-id="86cf9-126">Packet loss</span></span>

  - <span data-ttu-id="86cf9-127">[往復 (ミリ秒)]</span><span class="sxs-lookup"><span data-stu-id="86cf9-127">Jitter (ms)</span></span>

  - <span data-ttu-id="86cf9-128">[ヒーラー隠し比率]</span><span class="sxs-lookup"><span data-stu-id="86cf9-128">Healer concealed ratio</span></span>

  - <span data-ttu-id="86cf9-129">[ヒーラー引き伸ばし比率]</span><span class="sxs-lookup"><span data-stu-id="86cf9-129">Healer stretched ratio</span></span>

  - <span data-ttu-id="86cf9-130">[ヒーラー圧縮比率]</span><span class="sxs-lookup"><span data-stu-id="86cf9-130">Healer compressed ratio</span></span>

</div>

<div>

## <a name="filters"></a><span data-ttu-id="86cf9-131">フィルター</span><span class="sxs-lookup"><span data-stu-id="86cf9-131">Filters</span></span>

<span data-ttu-id="86cf9-p104">フィルターは、細かく絞り込んだデータ セットを返したり、返されたデータをさまざま方法で表示したりする方法として利用できます。たとえば、メディア品質概要レポートでは、返されたデータをアクセスの種類 (つまり、内部アクセスまたは外部アクセス) のようなことや有線/ワイヤレス ネットワーク接続でフィルターできます。また、データをグループ化する方法を選択することもできます。この場合は、通話が、時間、日、週、または月を基準にグループ化されています。</span><span class="sxs-lookup"><span data-stu-id="86cf9-p104">Filters provide a way for you to return a more finely-targeted set of data or to view the returned data in different ways. For example, the Media Quality Summary Report enables you to filter the returned data by such things as access type (that is, interval access vs. external access) or by wired/wireless network connection. You can also choose how data should be grouped. In this case, calls are grouped by hour, day, week, or month.</span></span>

<span data-ttu-id="86cf9-136">次の表に、メディア品質概要レポートで使用できるフィルターを示します。</span><span class="sxs-lookup"><span data-stu-id="86cf9-136">The following table lists the filters that you can use with the Media Quality Summary Report.</span></span>

### <a name="media-quality-summary-report-filters"></a><span data-ttu-id="86cf9-137">メディア品質概要レポートのフィルター</span><span class="sxs-lookup"><span data-stu-id="86cf9-137">Media Quality Summary Report Filters</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="86cf9-138">名前</span><span class="sxs-lookup"><span data-stu-id="86cf9-138">Name</span></span></th>
<th><span data-ttu-id="86cf9-139">説明</span><span class="sxs-lookup"><span data-stu-id="86cf9-139">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="86cf9-140"><strong>From</strong></span><span class="sxs-lookup"><span data-stu-id="86cf9-140"><strong>From</strong></span></span></p></td>
<td><p><span data-ttu-id="86cf9-p105">時間範囲の開始日と開始時刻。データを時間単位で表示するには、次のように開始日と開始時刻の両方を入力します。</span><span class="sxs-lookup"><span data-stu-id="86cf9-p105">Start date/time for the time range. To view data by hours, enter both the start date and time as follows:</span></span></p>
<p><span data-ttu-id="86cf9-143">7/7/2012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="86cf9-143">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="86cf9-p106">開始時刻を入力しないと、レポートは自動的に指定日の午前 12:00 に開始します。データを日単位で表示するには、次のように日付のみを入力します。</span><span class="sxs-lookup"><span data-stu-id="86cf9-p106">If you do not enter a start time, the report automatically begins at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="86cf9-146">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="86cf9-146">7/7/2012</span></span></p>
<p><span data-ttu-id="86cf9-147">週単位または月単位で表示するには、表示する週または月の任意の日付を入力します (その週または月の最初の日である必要はありません)。</span><span class="sxs-lookup"><span data-stu-id="86cf9-147">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="86cf9-148">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="86cf9-148">7/3/2012</span></span></p>
<p><span data-ttu-id="86cf9-149">一週間は、日曜日から始まり、土曜日で終わるものとします。</span><span class="sxs-lookup"><span data-stu-id="86cf9-149">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="86cf9-150"><strong>To</strong></span><span class="sxs-lookup"><span data-stu-id="86cf9-150"><strong>To</strong></span></span></p></td>
<td><p><span data-ttu-id="86cf9-p107">時間範囲の終了日と終了時刻。データを時間単位で表示するには、次のように終了日と終了時刻の両方を入力します。</span><span class="sxs-lookup"><span data-stu-id="86cf9-p107">End date/time for the time range. To view data by hours, enter both the end date and time as follows:</span></span></p>
<p><span data-ttu-id="86cf9-153">7/7/2012 13:00</span><span class="sxs-lookup"><span data-stu-id="86cf9-153">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="86cf9-p108">終了時刻を入力しないと、レポートは自動的に指定日の午前 12:00 に終了します。データを日単位で表示するには、次のように日付のみを入力します。</span><span class="sxs-lookup"><span data-stu-id="86cf9-p108">If you do not enter an end time, the report automatically ends at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="86cf9-156">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="86cf9-156">7/7/2012</span></span></p>
<p><span data-ttu-id="86cf9-157">週単位または月単位で表示するには、表示する週または月の任意の日付を入力します (その週または月の最初の日である必要はありません)。</span><span class="sxs-lookup"><span data-stu-id="86cf9-157">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="86cf9-158">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="86cf9-158">7/3/2012</span></span></p>
<p><span data-ttu-id="86cf9-159">週は、常に日曜日から土曜日までです。</span><span class="sxs-lookup"><span data-stu-id="86cf9-159">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="86cf9-160">[<strong>アクセスの種類</strong>]</span><span class="sxs-lookup"><span data-stu-id="86cf9-160"><strong>Access type</strong></span></span></p></td>
<td><p><span data-ttu-id="86cf9-p109">クライアントが通話時に内部ネットワークにログオンしたか、外部ネットワークにログオンしたかを示します。次のいずれかを選択します。</span><span class="sxs-lookup"><span data-stu-id="86cf9-p109">Indicates whether the client was logged on to the internal network or the external network when the call was placed. Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="86cf9-163">いずれ</span><span class="sxs-lookup"><span data-stu-id="86cf9-163">[All]</span></span></p></li>
<li><p><span data-ttu-id="86cf9-164">内部</span><span class="sxs-lookup"><span data-stu-id="86cf9-164">Internal</span></span></p></li>
<li><p><span data-ttu-id="86cf9-165">External</span><span class="sxs-lookup"><span data-stu-id="86cf9-165">External</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="86cf9-166">[<strong>ネットワークの種類</strong>]</span><span class="sxs-lookup"><span data-stu-id="86cf9-166"><strong>Network type</strong></span></span></p></td>
<td><p><span data-ttu-id="86cf9-p110">通話時にクライアントが接続したネットワークの種類を示します。次のいずれかを選択します。</span><span class="sxs-lookup"><span data-stu-id="86cf9-p110">Indicates the type of network the client was connected to when the call was placed. Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="86cf9-169">いずれ</span><span class="sxs-lookup"><span data-stu-id="86cf9-169">[All]</span></span></p></li>
<li><p><span data-ttu-id="86cf9-170">有線</span><span class="sxs-lookup"><span data-stu-id="86cf9-170">Wired</span></span></p></li>
<li><p><span data-ttu-id="86cf9-171">通信</span><span class="sxs-lookup"><span data-stu-id="86cf9-171">Wireless</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="86cf9-172"><strong>VPN</strong></span><span class="sxs-lookup"><span data-stu-id="86cf9-172"><strong>VPN</strong></span></span></p></td>
<td><p><span data-ttu-id="86cf9-p111">通話時に外部クライアントが仮想プライベート ネットワーク (VPN) 接続を使用したかどうかを示します。次のいずれかを選択します。</span><span class="sxs-lookup"><span data-stu-id="86cf9-p111">Indicates whether an external client was using a virtual private network (VPN) connection when the call was placed. Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="86cf9-175">いずれ</span><span class="sxs-lookup"><span data-stu-id="86cf9-175">[All]</span></span></p></li>
<li><p><span data-ttu-id="86cf9-176">VPN</span><span class="sxs-lookup"><span data-stu-id="86cf9-176">VPN</span></span></p></li>
<li><p><span data-ttu-id="86cf9-177">非 VPN</span><span class="sxs-lookup"><span data-stu-id="86cf9-177">Non-VPN</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics"></a><span data-ttu-id="86cf9-178">指標</span><span class="sxs-lookup"><span data-stu-id="86cf9-178">Metrics</span></span>

<span data-ttu-id="86cf9-179">次の表に、メディア品質概要レポートで提供される情報を示します。</span><span class="sxs-lookup"><span data-stu-id="86cf9-179">The following table lists the information provided in the Media Quality Summary Report.</span></span>

### <a name="media-quality-summary-report-metrics-audio-call-summary"></a><span data-ttu-id="86cf9-180">メディア品質概要レポートの指標: 音声通話の概要</span><span class="sxs-lookup"><span data-stu-id="86cf9-180">Media Quality Summary Report Metrics: Audio Call Summary</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="86cf9-181">名前</span><span class="sxs-lookup"><span data-stu-id="86cf9-181">Name</span></span></th>
<th><span data-ttu-id="86cf9-182">この項目での並べ替え</span><span class="sxs-lookup"><span data-stu-id="86cf9-182">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="86cf9-183">説明</span><span class="sxs-lookup"><span data-stu-id="86cf9-183">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="86cf9-184">[<strong>通話の種類/エンドポイントの種類</strong>]</span><span class="sxs-lookup"><span data-stu-id="86cf9-184"><strong>Call type/Endpoint type</strong></span></span></p></td>
<td><p><span data-ttu-id="86cf9-185">いいえ</span><span class="sxs-lookup"><span data-stu-id="86cf9-185">No</span></span></p></td>
<td><p><span data-ttu-id="86cf9-p112">この項目をクリックすると、その種類に基づく通話の詳細情報がレポートに表示されます。通話の種類は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="86cf9-p112">When you click this item, the report shows detailed information about calls based on that type. Call types include:</span></span></p>
<ul>
<li><p><span data-ttu-id="86cf9-188">UC ピアツーピア通話</span><span class="sxs-lookup"><span data-stu-id="86cf9-188">UC Peer-to-Peer Calls</span></span></p></li>
<li><p><span data-ttu-id="86cf9-189">UC 電話会議セッション</span><span class="sxs-lookup"><span data-stu-id="86cf9-189">UC Conference Sessions</span></span></p></li>
<li><p><span data-ttu-id="86cf9-190">PSTN 電話会議セッション</span><span class="sxs-lookup"><span data-stu-id="86cf9-190">PSTN Conference Sessions</span></span></p></li>
<li><p><span data-ttu-id="86cf9-191">PSTN 通話: メディアのバイパス</span><span class="sxs-lookup"><span data-stu-id="86cf9-191">PSTN Calls: Media Bypass</span></span></p></li>
<li><p><span data-ttu-id="86cf9-192">PSTN 通話 (非バイパス): UC レグ</span><span class="sxs-lookup"><span data-stu-id="86cf9-192">PSTN Calls (Non-Bypass): UC Leg</span></span></p></li>
<li><p><span data-ttu-id="86cf9-193">PSTN 通話 (非バイパス): ゲートウェイ レグ</span><span class="sxs-lookup"><span data-stu-id="86cf9-193">PSTN Calls (Non-Bypass): Gateway Leg</span></span></p></li>
<li><p><span data-ttu-id="86cf9-194">その他の通話の種類</span><span class="sxs-lookup"><span data-stu-id="86cf9-194">Other Call Types</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="86cf9-195">[<strong>通話ボリューム</strong>]</span><span class="sxs-lookup"><span data-stu-id="86cf9-195"><strong>Call volume</strong></span></span></p></td>
<td><p><span data-ttu-id="86cf9-196">いいえ</span><span class="sxs-lookup"><span data-stu-id="86cf9-196">No</span></span></p></td>
<td><p><span data-ttu-id="86cf9-197">通話の種類当たりの通話の総数。</span><span class="sxs-lookup"><span data-stu-id="86cf9-197">Total number of calls per call type.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="86cf9-198">[<strong>低品質通話のパーセンテージ</strong>]</span><span class="sxs-lookup"><span data-stu-id="86cf9-198"><strong>Poor call percentage</strong></span></span></p></td>
<td><p><span data-ttu-id="86cf9-199">いいえ</span><span class="sxs-lookup"><span data-stu-id="86cf9-199">No</span></span></p></td>
<td><p><span data-ttu-id="86cf9-p113">低品質として分類される通話の総数。低品質通話とは、少なくとも 1 つの測定指標が許容値を超えている通話 (たとえば、過剰なジッターが発生した通話) のことです。</span><span class="sxs-lookup"><span data-stu-id="86cf9-p113">Total number of calls classified as poor. A poor call is any call which at least one of the measured metrics exceeded the allowed value (for example, a call that experienced excessive jitter).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="86cf9-202">[<strong>通話ボリューム (ワイヤレス通話)</strong>]</span><span class="sxs-lookup"><span data-stu-id="86cf9-202"><strong>Call volume (wireless call)</strong></span></span></p></td>
<td><p><span data-ttu-id="86cf9-203">いいえ</span><span class="sxs-lookup"><span data-stu-id="86cf9-203">No</span></span></p></td>
<td><p><span data-ttu-id="86cf9-204">ワイヤレス接続を使用した通話の総数。</span><span class="sxs-lookup"><span data-stu-id="86cf9-204">Total number of calls that used a wireless connection.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="86cf9-205">[<strong>通話ボリューム (VPN 通話)</strong>]</span><span class="sxs-lookup"><span data-stu-id="86cf9-205"><strong>Call volume (VPN call)</strong></span></span></p></td>
<td><p><span data-ttu-id="86cf9-206">いいえ</span><span class="sxs-lookup"><span data-stu-id="86cf9-206">No</span></span></p></td>
<td><p><span data-ttu-id="86cf9-207">VPN 接続を使用した通話の総数。</span><span class="sxs-lookup"><span data-stu-id="86cf9-207">Total number of calls that used a VPN connection.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="86cf9-208">[<strong>通話ボリューム (外部通話)</strong>]</span><span class="sxs-lookup"><span data-stu-id="86cf9-208"><strong>Call volume (external call)</strong></span></span></p></td>
<td><p><span data-ttu-id="86cf9-209">いいえ</span><span class="sxs-lookup"><span data-stu-id="86cf9-209">No</span></span></p></td>
<td><p><span data-ttu-id="86cf9-210">外部接続 (つまり、内部ネットワークの外側の接続) を使用した通話の数。</span><span class="sxs-lookup"><span data-stu-id="86cf9-210">Number of calls that used an external connection (that is, a connection outside the internal network).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="86cf9-211">[<strong>往復 (ミリ秒)</strong>]</span><span class="sxs-lookup"><span data-stu-id="86cf9-211"><strong>Round trip (ms)</strong></span></span></p></td>
<td><p><span data-ttu-id="86cf9-212">いいえ</span><span class="sxs-lookup"><span data-stu-id="86cf9-212">No</span></span></p></td>
<td><p><span data-ttu-id="86cf9-p114">リアルタイム転送プロトコル (RTP) パケットが別のエンドポイントとの間を往復するのに要する平均時間 (ミリ秒単位)。100 ミリ秒以下の往復時間が許容できる品質と見なされます。</span><span class="sxs-lookup"><span data-stu-id="86cf9-p114">Average amount of (in milliseconds) required for a real-time transport protocol (RTP) packet to travel to another endpoint and then back. Round-trip times of 100 milliseconds or less are considered of acceptable quality.</span></span></p>
<p><span data-ttu-id="86cf9-p115">この値が高い場合は、国際通話ルーティング、ルーティングの構成ミス、メディア サーバーの過負荷などの原因が考えられます。その結果、双方向のリアルタイムの音声会話が困難になります。</span><span class="sxs-lookup"><span data-stu-id="86cf9-p115">High round-trip values can be caused by international call routing, a routing misconfiguration, or an overloaded media server. High round-trip times result in difficulties with two-way, real-time audio conversations.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="86cf9-217">[<strong>低下 (MOS)</strong>]</span><span class="sxs-lookup"><span data-stu-id="86cf9-217"><strong>Degradation (MOS)</strong></span></span></p></td>
<td><p><span data-ttu-id="86cf9-218">いいえ</span><span class="sxs-lookup"><span data-stu-id="86cf9-218">No</span></span></p></td>
<td><p><span data-ttu-id="86cf9-219">通話時に発生した平均オピニオン値 (MOS) 低下の平均値。</span><span class="sxs-lookup"><span data-stu-id="86cf9-219">Average amount of mean opinion score (MOS) degradation experienced during a call.</span></span> <span data-ttu-id="86cf9-220">低下の値範囲は、最低 0.0 から最高 5.0 までとなります。</span><span class="sxs-lookup"><span data-stu-id="86cf9-220">Degradation values can range from a low of 0.0 to a high of 5.0.</span></span> <span data-ttu-id="86cf9-221">0.5 以下の値は、許容される低下を表します。</span><span class="sxs-lookup"><span data-stu-id="86cf9-221">A value of 0.5 or less represents acceptable degradation.</span></span> <span data-ttu-id="86cf9-222">従来、平均オピニオン値は、ユーザーが通話の品質を 1 から 5 の範囲で評価することによって計算されていました。</span><span class="sxs-lookup"><span data-stu-id="86cf9-222">Historically, mean options scores were calculated by having users rate the quality of a call on a scale of 1-to-5.</span></span> <span data-ttu-id="86cf9-223">Lync Server では、Lync Server は一連のアルゴリズムを使用して、ユーザーが通話を評価する方法を予測します。</span><span class="sxs-lookup"><span data-stu-id="86cf9-223">In Lync Server, Lync Server uses a set of algorithms to predict how users would have rated a call.</span></span></p>
<p><span data-ttu-id="86cf9-p117">この値が高い場合は、輻輳、帯域幅の不足、ワイヤレスの輻輳または干渉、メディア サーバーやエンドポイントの過負荷などの原因が考えられます。その結果、音声のひずみや欠落が生じます。</span><span class="sxs-lookup"><span data-stu-id="86cf9-p117">High degradation values can be caused by congestion, lack of bandwidth, wireless congestion or interference, or an overloaded media server or endpoint. High degradation results in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="86cf9-226">[<strong>パケット損失</strong>]</span><span class="sxs-lookup"><span data-stu-id="86cf9-226"><strong>Packet loss</strong></span></span></p></td>
<td><p><span data-ttu-id="86cf9-227">いいえ</span><span class="sxs-lookup"><span data-stu-id="86cf9-227">No</span></span></p></td>
<td><p><span data-ttu-id="86cf9-p118">RTP パケットの平均損失率 (パケット損失は、RTP パケット (音声およびビデオをインターネット上で転送する場合に使用されるプロトコル) が宛先に到達できなかった場合に発生します)。通常、この値が高い場合は、輻輳、帯域幅の不足、ワイヤレスの輻輳または干渉、メディア サーバーの過負荷などの原因が考えられます。その結果、一般に音声のひずみや欠落が生じます。</span><span class="sxs-lookup"><span data-stu-id="86cf9-p118">Average rate of RTP packet loss. (Packet loss occurs when RTP packets, a protocol used for transmitting audio and video across the Internet, failed to reach their destination.) High loss rates are generally caused by congestion, lack of bandwidth, wireless congestion or interference, or an overloaded media server. Packet loss typically results in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="86cf9-231">[<strong>ジッター</strong>]</span><span class="sxs-lookup"><span data-stu-id="86cf9-231"><strong>Jitter (ms)</strong></span></span></p></td>
<td><p><span data-ttu-id="86cf9-232">いいえ</span><span class="sxs-lookup"><span data-stu-id="86cf9-232">No</span></span></p></td>
<td><p><span data-ttu-id="86cf9-233">RTP パケットの着信間に検出された平均ジッター (ジッターとは、通話の "揺れ" の測定値です)。</span><span class="sxs-lookup"><span data-stu-id="86cf9-233">Average jitter detected between RTP packet arrivals.</span></span> <span data-ttu-id="86cf9-234">(ジッターは、通話の&quot;過&quot;の測定値です)。高ジッター値は、通常、混雑または過負荷のメディアサーバーによって発生し、その結果、音声がひずむか失われます。</span><span class="sxs-lookup"><span data-stu-id="86cf9-234">(Jitter is a measure of the &quot;shakiness&quot; of a call.) High jitter values are typically caused by congestion or an overloaded media server, and result in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="86cf9-235">[<strong>ヒーラー隠し比率</strong>]</span><span class="sxs-lookup"><span data-stu-id="86cf9-235"><strong>Healer concealed ratio</strong></span></span></p></td>
<td><p><span data-ttu-id="86cf9-236">いいえ</span><span class="sxs-lookup"><span data-stu-id="86cf9-236">No</span></span></p></td>
<td><p><span data-ttu-id="86cf9-p120">サンプルの合計数に対する隠しオーディオ サンプルの平均比率 (隠しオーディオ サンプルとは、突然遷移を取り除くために使用される手法です。突然遷移は、通常、ネットワーク パケットの削除が原因で発生します)。この値が高い場合は、パケット損失やジッターのために高いレベルで損失の隠蔽が適用されています。その結果、音声のひずみや欠落が生じます。</span><span class="sxs-lookup"><span data-stu-id="86cf9-p120">Average ratio of concealed audio samples to the total to the total number of samples. (A concealed audio sample is a technique used to smooth out the abrupt transition that would usually be caused by dropped network packets.) High values indicate significant levels of loss concealment applied caused by packet loss or jitter, and results in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="86cf9-239">[<strong>ヒーラー引き伸ばし比率</strong>]</span><span class="sxs-lookup"><span data-stu-id="86cf9-239"><strong>Healer stretched ratio</strong></span></span></p></td>
<td><p><span data-ttu-id="86cf9-240">いいえ</span><span class="sxs-lookup"><span data-stu-id="86cf9-240">No</span></span></p></td>
<td><p><span data-ttu-id="86cf9-p121">サンプルの合計数に対する引き伸ばされたオーディオ サンプルの平均比率 (引き伸ばされたオーディオとは、ネットワーク パケットの削除が検出されたときに通話の品質を維持できるように拡張されたオーディオのことです)。この値が高い場合は、ジッターのために高いレベルでサンプルの引き伸ばしが行われています。その結果、音声が機械のように聞こえたりひずんで聞こえたりします。</span><span class="sxs-lookup"><span data-stu-id="86cf9-p121">Average ratio of stretched audio samples to the total to the total number of samples. (Stretched audio is audio that has been expanded to help maintain call quality when a dropped network packet has been detected.) High values indicate significant levels of sample stretching caused by jitter, and result in audio sounding robotic or distorted.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="86cf9-243">[<strong>ヒーラー圧縮比率</strong>]</span><span class="sxs-lookup"><span data-stu-id="86cf9-243"><strong>Healer compressed ratio</strong></span></span></p></td>
<td><p><span data-ttu-id="86cf9-244">いいえ</span><span class="sxs-lookup"><span data-stu-id="86cf9-244">No</span></span></p></td>
<td><p><span data-ttu-id="86cf9-p122">サンプルの合計数に対する圧縮オーディオ サンプルの平均比率 (圧縮オーディオとは、ネットワーク パケットの削除が検出されたときに通話の品質を維持できるように圧縮されたオーディオのことです)。この値が高い場合は、ジッターのために高いレベルでサンプルの圧縮が行われています。その結果、音声が早送りされたように聞こえたりひずんで聞こえたりします。</span><span class="sxs-lookup"><span data-stu-id="86cf9-p122">Average ratio of compressed audio samples to the total number of samples. (Compressed audio is audio that has been compressed to help maintain call quality when a dropped network packet has been detected.) High values indicate significant levels of sample compression caused by jitter, and result in audio sounding accelerated or distorted.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="media-quality-summary-report-metrics-video-call-summary"></a><span data-ttu-id="86cf9-247">メディア品質概要レポートの指標: ビデオ通話の概要</span><span class="sxs-lookup"><span data-stu-id="86cf9-247">Media Quality Summary Report Metrics: Video Call Summary</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="86cf9-248">名前</span><span class="sxs-lookup"><span data-stu-id="86cf9-248">Name</span></span></th>
<th><span data-ttu-id="86cf9-249">この項目での並べ替え</span><span class="sxs-lookup"><span data-stu-id="86cf9-249">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="86cf9-250">説明</span><span class="sxs-lookup"><span data-stu-id="86cf9-250">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="86cf9-251">[<strong>通話の種類/エンドポイントの種類</strong>]</span><span class="sxs-lookup"><span data-stu-id="86cf9-251"><strong>Call type/Endpoint type</strong></span></span></p></td>
<td><p><span data-ttu-id="86cf9-252">いいえ</span><span class="sxs-lookup"><span data-stu-id="86cf9-252">No</span></span></p></td>
<td><p><span data-ttu-id="86cf9-p123">この項目をクリックすると、その種類に基づく通話の詳細情報がレポートに表示されます。通話の種類は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="86cf9-p123">When you click this item, the report shows detailed information about calls based on that type. Call types include:</span></span></p>
<ul>
<li><p><span data-ttu-id="86cf9-255">UC ピアツーピア通話</span><span class="sxs-lookup"><span data-stu-id="86cf9-255">UC Peer-to-Peer Calls</span></span></p></li>
<li><p><span data-ttu-id="86cf9-256">UC 電話会議セッション</span><span class="sxs-lookup"><span data-stu-id="86cf9-256">UC Conference Sessions</span></span></p></li>
<li><p><span data-ttu-id="86cf9-257">PSTN 電話会議セッション</span><span class="sxs-lookup"><span data-stu-id="86cf9-257">PSTN Conference Sessions</span></span></p></li>
<li><p><span data-ttu-id="86cf9-258">PSTN 通話: メディアのバイパス</span><span class="sxs-lookup"><span data-stu-id="86cf9-258">PSTN Calls: Media Bypass</span></span></p></li>
<li><p><span data-ttu-id="86cf9-259">PSTN 通話 (非バイパス): UC レグ</span><span class="sxs-lookup"><span data-stu-id="86cf9-259">PSTN Calls (Non-Bypass): UC Leg</span></span></p></li>
<li><p><span data-ttu-id="86cf9-260">PSTN 通話 (非バイパス): ゲートウェイ レグ</span><span class="sxs-lookup"><span data-stu-id="86cf9-260">PSTN Calls (Non-Bypass): Gateway Leg</span></span></p></li>
<li><p><span data-ttu-id="86cf9-261">その他の通話の種類</span><span class="sxs-lookup"><span data-stu-id="86cf9-261">Other Call Types</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="86cf9-262">[<strong>通話ボリューム</strong>]</span><span class="sxs-lookup"><span data-stu-id="86cf9-262"><strong>Call volume</strong></span></span></p></td>
<td><p><span data-ttu-id="86cf9-263">いいえ</span><span class="sxs-lookup"><span data-stu-id="86cf9-263">No</span></span></p></td>
<td><p><span data-ttu-id="86cf9-264">通話の種類当たりの通話の総数。</span><span class="sxs-lookup"><span data-stu-id="86cf9-264">Total number of calls per call type.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="86cf9-265">[<strong>低品質通話のパーセンテージ</strong>]</span><span class="sxs-lookup"><span data-stu-id="86cf9-265"><strong>Poor call percentage</strong></span></span></p></td>
<td><p><span data-ttu-id="86cf9-266">いいえ</span><span class="sxs-lookup"><span data-stu-id="86cf9-266">No</span></span></p></td>
<td><p><span data-ttu-id="86cf9-p124">低品質として分類される通話の総数。低品質通話とは、少なくとも 1 つの測定指標が許容値を超えている通話 (たとえば、過剰なジッターが発生した通話) のことです。</span><span class="sxs-lookup"><span data-stu-id="86cf9-p124">Total number of calls classified as poor. A poor call is any call which at least one of the measured metrics exceeded the allowed value (for example, a call that experienced excessive jitter).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="86cf9-269">[<strong>通話ボリューム (ワイヤレス通話)</strong>]</span><span class="sxs-lookup"><span data-stu-id="86cf9-269"><strong>Call volume (wireless call)</strong></span></span></p></td>
<td><p><span data-ttu-id="86cf9-270">いいえ</span><span class="sxs-lookup"><span data-stu-id="86cf9-270">No</span></span></p></td>
<td><p><span data-ttu-id="86cf9-271">ワイヤレス接続を使用した通話の総数。</span><span class="sxs-lookup"><span data-stu-id="86cf9-271">Total number of calls that used a wireless connection.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="86cf9-272">[<strong>通話ボリューム (VPN 通話)</strong>]</span><span class="sxs-lookup"><span data-stu-id="86cf9-272"><strong>Call volume (VPN call)</strong></span></span></p></td>
<td><p><span data-ttu-id="86cf9-273">いいえ</span><span class="sxs-lookup"><span data-stu-id="86cf9-273">No</span></span></p></td>
<td><p><span data-ttu-id="86cf9-274">VPN 接続を使用した通話の総数。</span><span class="sxs-lookup"><span data-stu-id="86cf9-274">Total number of calls that used a VPN connection.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="86cf9-275">[<strong>通話ボリューム (外部通話)</strong>]</span><span class="sxs-lookup"><span data-stu-id="86cf9-275"><strong>Call volume (external call)</strong></span></span></p></td>
<td><p><span data-ttu-id="86cf9-276">いいえ</span><span class="sxs-lookup"><span data-stu-id="86cf9-276">No</span></span></p></td>
<td><p><span data-ttu-id="86cf9-277">外部接続 (つまり、内部ネットワークの外側の接続) を使用した通話の数。</span><span class="sxs-lookup"><span data-stu-id="86cf9-277">Number of calls that used an external connection (that is, a connection outside the internal network).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="86cf9-278">[<strong>Avg bit-rate (Kbits/s)</strong>]</span><span class="sxs-lookup"><span data-stu-id="86cf9-278"><strong>Avg bit-rate (Kbits/s)</strong></span></span></p></td>
<td><p><span data-ttu-id="86cf9-279">いいえ</span><span class="sxs-lookup"><span data-stu-id="86cf9-279">No</span></span></p></td>
<td><p><span data-ttu-id="86cf9-280">平均ビデオ ビット レート (1 秒あたりのキロビット)。</span><span class="sxs-lookup"><span data-stu-id="86cf9-280">Average video bit rate (in kilobits per second).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="86cf9-281">[<strong>Low bit-rate %</strong>]</span><span class="sxs-lookup"><span data-stu-id="86cf9-281"><strong>Low bit-rate %</strong></span></span></p></td>
<td><p><span data-ttu-id="86cf9-282">いいえ</span><span class="sxs-lookup"><span data-stu-id="86cf9-282">No</span></span></p></td>
<td><p><span data-ttu-id="86cf9-283">ビット レートが低い通話のパーセンテージ。</span><span class="sxs-lookup"><span data-stu-id="86cf9-283">Percentage of the call where the bit rate was low.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="86cf9-284">[<strong>Outbound packet loss</strong>]</span><span class="sxs-lookup"><span data-stu-id="86cf9-284"><strong>Outbound packet loss</strong></span></span></p></td>
<td><p><span data-ttu-id="86cf9-285">いいえ</span><span class="sxs-lookup"><span data-stu-id="86cf9-285">No</span></span></p></td>
<td><p><span data-ttu-id="86cf9-p125">送信パケットのリアルタイム転送プロトコル (RTP) パケット損失 (パケット損失は、RTP パケット、つまりインターネット経由で音声とビデオを転送するために使われるプロトコルの一種で、パケットが宛先に到達できなかったときに発生します)。この値が高い場合は、輻輳、帯域幅の不足、ワイヤレスの輻輳または干渉、メディア サーバーの過負荷などの原因が考えられます。パケット損失が発生すると、通常、音声のひずみや欠落が生じます。</span><span class="sxs-lookup"><span data-stu-id="86cf9-p125">Real-Time Transport Protocol (RTP) packet loss for outbound packets. (Packet loss occurs when RTP packets, a protocol used for transmitting audio and video across the Internet, failed to reach their destination.) High loss rates are generally caused by congestion, lack of bandwidth, wireless congestion or interference, or an overloaded media server. Packet loss typically results in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="86cf9-289">[<strong>フリーズ フレーム %</strong>]</span><span class="sxs-lookup"><span data-stu-id="86cf9-289"><strong>Frozen frame %</strong></span></span></p></td>
<td><p><span data-ttu-id="86cf9-290">いいえ</span><span class="sxs-lookup"><span data-stu-id="86cf9-290">No</span></span></p></td>
<td><p><span data-ttu-id="86cf9-p126">"フリーズ" フレームのパーセンテージ。フリーズ フレームでは、通話の音声部分が続いていてもビデオの進行が停止します。</span><span class="sxs-lookup"><span data-stu-id="86cf9-p126">Percentage of “frozen” frames. In a frozen frame, the video stops advancing while the audio portion of the call continues.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="86cf9-293">[<strong>Outbound avg frame rate</strong>]</span><span class="sxs-lookup"><span data-stu-id="86cf9-293"><strong>Outbound avg frame rate</strong></span></span></p></td>
<td><p><span data-ttu-id="86cf9-294">いいえ</span><span class="sxs-lookup"><span data-stu-id="86cf9-294">No</span></span></p></td>
<td><p><span data-ttu-id="86cf9-295">通話時の送信の平均フレーム レート。</span><span class="sxs-lookup"><span data-stu-id="86cf9-295">Average frame rate for outbound transmissions during the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="86cf9-296">[<strong>Inbound avg frame rate</strong>]</span><span class="sxs-lookup"><span data-stu-id="86cf9-296"><strong>Inbound avg frame rate</strong></span></span></p></td>
<td><p><span data-ttu-id="86cf9-297">いいえ</span><span class="sxs-lookup"><span data-stu-id="86cf9-297">No</span></span></p></td>
<td><p><span data-ttu-id="86cf9-298">通話時の受信の平均フレーム レート。</span><span class="sxs-lookup"><span data-stu-id="86cf9-298">Average frame rate for incoming transmissions during the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="86cf9-299">[<strong>Inbound low frame rate %</strong>]</span><span class="sxs-lookup"><span data-stu-id="86cf9-299"><strong>Inbound low frame rate %</strong></span></span></p></td>
<td><p><span data-ttu-id="86cf9-300">いいえ</span><span class="sxs-lookup"><span data-stu-id="86cf9-300">No</span></span></p></td>
<td><p><span data-ttu-id="86cf9-301">着信ビデオのビット レートが低い通話のパーセンテージ。</span><span class="sxs-lookup"><span data-stu-id="86cf9-301">Percentage of the call where the bit rate for incoming video was low.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="86cf9-302">[<strong>Client health %</strong>]</span><span class="sxs-lookup"><span data-stu-id="86cf9-302"><strong>Client health %</strong></span></span></p></td>
<td></td>
<td><p><span data-ttu-id="86cf9-303">通話時のクライアント デバイスの相対的な正常性を示します。</span><span class="sxs-lookup"><span data-stu-id="86cf9-303">Indicates the relative health of the client device during the call.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="media-quality-summary-report-metrics-application-sharing-call-summary"></a><span data-ttu-id="86cf9-304">メディア品質概要レポートの指標: アプリケーション共有の通話の概要</span><span class="sxs-lookup"><span data-stu-id="86cf9-304">Media Quality Summary Report Metrics: Application Sharing Call Summary</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="86cf9-305">名前</span><span class="sxs-lookup"><span data-stu-id="86cf9-305">Name</span></span></th>
<th><span data-ttu-id="86cf9-306">この項目での並べ替え</span><span class="sxs-lookup"><span data-stu-id="86cf9-306">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="86cf9-307">説明</span><span class="sxs-lookup"><span data-stu-id="86cf9-307">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="86cf9-308">[<strong>通話の種類/エンドポイントの種類</strong>]</span><span class="sxs-lookup"><span data-stu-id="86cf9-308"><strong>Call type/Endpoint type</strong></span></span></p></td>
<td><p><span data-ttu-id="86cf9-309">いいえ</span><span class="sxs-lookup"><span data-stu-id="86cf9-309">No</span></span></p></td>
<td><p><span data-ttu-id="86cf9-p127">この項目をクリックすると、その種類に基づく通話の詳細情報がレポートに表示されます。通話の種類は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="86cf9-p127">When you click this item, the report shows detailed information about calls based on that type. Call types include:</span></span></p>
<ul>
<li><p><span data-ttu-id="86cf9-312">UC ピアツーピア通話</span><span class="sxs-lookup"><span data-stu-id="86cf9-312">UC Peer-to-Peer Calls</span></span></p></li>
<li><p><span data-ttu-id="86cf9-313">UC 電話会議セッション</span><span class="sxs-lookup"><span data-stu-id="86cf9-313">UC Conference Sessions</span></span></p></li>
<li><p><span data-ttu-id="86cf9-314">PSTN 電話会議セッション</span><span class="sxs-lookup"><span data-stu-id="86cf9-314">PSTN Conference Sessions</span></span></p></li>
<li><p><span data-ttu-id="86cf9-315">PSTN 通話: メディアのバイパス</span><span class="sxs-lookup"><span data-stu-id="86cf9-315">PSTN Calls: Media Bypass</span></span></p></li>
<li><p><span data-ttu-id="86cf9-316">PSTN 通話 (非バイパス): UC レグ</span><span class="sxs-lookup"><span data-stu-id="86cf9-316">PSTN Calls (Non-Bypass): UC Leg</span></span></p></li>
<li><p><span data-ttu-id="86cf9-317">PSTN 通話 (非バイパス): ゲートウェイ レグ</span><span class="sxs-lookup"><span data-stu-id="86cf9-317">PSTN Calls (Non-Bypass): Gateway Leg</span></span></p></li>
<li><p><span data-ttu-id="86cf9-318">その他の通話の種類</span><span class="sxs-lookup"><span data-stu-id="86cf9-318">Other Call Types</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="86cf9-319">[<strong>通話ボリューム</strong>]</span><span class="sxs-lookup"><span data-stu-id="86cf9-319"><strong>Call volume</strong></span></span></p></td>
<td><p><span data-ttu-id="86cf9-320">いいえ</span><span class="sxs-lookup"><span data-stu-id="86cf9-320">No</span></span></p></td>
<td><p><span data-ttu-id="86cf9-321">通話の種類当たりの通話の総数。</span><span class="sxs-lookup"><span data-stu-id="86cf9-321">Total number of calls per call type.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="86cf9-322">[<strong>低品質通話のパーセンテージ</strong>]</span><span class="sxs-lookup"><span data-stu-id="86cf9-322"><strong>Poor call percentage</strong></span></span></p></td>
<td><p><span data-ttu-id="86cf9-323">いいえ</span><span class="sxs-lookup"><span data-stu-id="86cf9-323">No</span></span></p></td>
<td><p><span data-ttu-id="86cf9-p128">低品質として分類される通話の総数。低品質通話とは、少なくとも 1 つの測定指標が許容値を超えている通話 (たとえば、過剰なジッターが発生した通話) のことです。</span><span class="sxs-lookup"><span data-stu-id="86cf9-p128">Total number of calls classified as poor. A poor call is any call which at least one of the measured metrics exceeded the allowed value (for example, a call that experienced excessive jitter).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="86cf9-326">[<strong>通話ボリューム (ワイヤレス通話)</strong>]</span><span class="sxs-lookup"><span data-stu-id="86cf9-326"><strong>Call volume (wireless call)</strong></span></span></p></td>
<td><p><span data-ttu-id="86cf9-327">いいえ</span><span class="sxs-lookup"><span data-stu-id="86cf9-327">No</span></span></p></td>
<td><p><span data-ttu-id="86cf9-328">ワイヤレス接続を使用した通話の総数。</span><span class="sxs-lookup"><span data-stu-id="86cf9-328">Total number of calls that used a wireless connection.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="86cf9-329">[<strong>通話ボリューム (VPN 通話)</strong>]</span><span class="sxs-lookup"><span data-stu-id="86cf9-329"><strong>Call volume (VPN call)</strong></span></span></p></td>
<td><p><span data-ttu-id="86cf9-330">いいえ</span><span class="sxs-lookup"><span data-stu-id="86cf9-330">No</span></span></p></td>
<td><p><span data-ttu-id="86cf9-331">VPN 接続を使用した通話の総数。</span><span class="sxs-lookup"><span data-stu-id="86cf9-331">Total number of calls that used a VPN connection.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="86cf9-332">[<strong>通話ボリューム (外部通話)</strong>]</span><span class="sxs-lookup"><span data-stu-id="86cf9-332"><strong>Call volume (external call)</strong></span></span></p></td>
<td><p><span data-ttu-id="86cf9-333">いいえ</span><span class="sxs-lookup"><span data-stu-id="86cf9-333">No</span></span></p></td>
<td><p><span data-ttu-id="86cf9-334">外部接続 (つまり、内部ネットワークの外側の接続) を使用した通話の数。</span><span class="sxs-lookup"><span data-stu-id="86cf9-334">Number of calls that used an external connection (that is, a connection outside the internal network).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="86cf9-335">[<strong>ジッター (ミリ秒)</strong>]</span><span class="sxs-lookup"><span data-stu-id="86cf9-335"><strong>Jitter (ms)</strong></span></span></p></td>
<td><p><span data-ttu-id="86cf9-336">いいえ</span><span class="sxs-lookup"><span data-stu-id="86cf9-336">No</span></span></p></td>
<td><p><span data-ttu-id="86cf9-337">RTP パケットの着信間に検出された平均ジッター (ジッターとは、通話の "揺れ" の測定値です)。</span><span class="sxs-lookup"><span data-stu-id="86cf9-337">Average jitter detected between RTP packet arrivals.</span></span> <span data-ttu-id="86cf9-338">(ジッターは、通話の&quot;過&quot;の測定値です)。高ジッター値は、通常、混雑または過負荷のメディアサーバーによって発生し、その結果、音声がひずむか失われます。</span><span class="sxs-lookup"><span data-stu-id="86cf9-338">(Jitter is a measure of the &quot;shakiness&quot; of a call.) High jitter values are typically caused by congestion or an overloaded media server, and result in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="86cf9-339">[<strong>Relative one way delay burst density (ms)</strong>]</span><span class="sxs-lookup"><span data-stu-id="86cf9-339"><strong>Avg. relative one way</strong></span></span></p></td>
<td><p><span data-ttu-id="86cf9-340">いいえ</span><span class="sxs-lookup"><span data-stu-id="86cf9-340">No</span></span></p></td>
<td><p><span data-ttu-id="86cf9-p130">2 つのメディア エンドポイント間の相対的な一方向の平均遅延。これは、1 ホップの遅延の測定です。</span><span class="sxs-lookup"><span data-stu-id="86cf9-p130">Average relative one-way delay between two media endpoints. This is a single-hop latency measure.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="86cf9-343">[<strong>RDP Tile processing latency burst density (ms)</strong>]</span><span class="sxs-lookup"><span data-stu-id="86cf9-343"><strong>Avg. RDP tile processing latency</strong></span></span></p></td>
<td><p><span data-ttu-id="86cf9-344">いいえ</span><span class="sxs-lookup"><span data-stu-id="86cf9-344">No</span></span></p></td>
<td><p><span data-ttu-id="86cf9-345">表示セッション中の AS 会議サーバーでの RDP タイル処理の平均遅延。</span><span class="sxs-lookup"><span data-stu-id="86cf9-345">The average RDP tile processing latency in the AS Conferencing Server over the duration of the viewing session.</span></span> <span data-ttu-id="86cf9-346">平均値が高いと、表示の際に遅延時間が長くなり、ネットワークの遅延が生じます。</span><span class="sxs-lookup"><span data-stu-id="86cf9-346">A high average reflects a longer delay in the viewing experience, and includes network latency.</span></span> <span data-ttu-id="86cf9-347">過負荷の会議サーバーでは平均遅延が大きくなる場合があります。</span><span class="sxs-lookup"><span data-stu-id="86cf9-347">An overloaded conferencing server may experience higher average delays.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="86cf9-348">[<strong>損失した合計タイル %</strong>]</span><span class="sxs-lookup"><span data-stu-id="86cf9-348"><strong>Total spoiled tile %</strong></span></span></p></td>
<td><p><span data-ttu-id="86cf9-349">いいえ</span><span class="sxs-lookup"><span data-stu-id="86cf9-349">No</span></span></p></td>
<td><p><span data-ttu-id="86cf9-350">損失した RDP タイル数のパーセンテージ。</span><span class="sxs-lookup"><span data-stu-id="86cf9-350">Total percentage of spoiled RDP tiles.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

