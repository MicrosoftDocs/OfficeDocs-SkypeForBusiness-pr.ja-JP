---
title: 'Lync Server 2013: 場所の傾向レポート'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Location Trend Report
ms:assetid: 61e2db3c-9f10-4411-8e7e-c6950faf8533
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204941(v=OCS.15)
ms:contentKeyID: 48184280
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e74cf4e763272f2309e358120abb12b0424aa40b
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2020
ms.locfileid: "42030941"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="location-trend-report-in-lync-server-2013"></a><span data-ttu-id="cd62c-102">Lync Server 2013 の場所の傾向レポート</span><span class="sxs-lookup"><span data-stu-id="cd62c-102">Location Trend Report in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="cd62c-103">_**トピックの最終更新日:** 2012-06-06_</span><span class="sxs-lookup"><span data-stu-id="cd62c-103">_**Topic Last Modified:** 2012-06-06_</span></span>

<span data-ttu-id="cd62c-104">場所の傾向レポートは、ネットワークの場所の通話品質に関する傾向情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="cd62c-104">The Location Trend Report provides call quality trend information for network locations.</span></span>

<div>

## <a name="filters"></a><span data-ttu-id="cd62c-105">フィルター</span><span class="sxs-lookup"><span data-stu-id="cd62c-105">Filters</span></span>

<span data-ttu-id="cd62c-p101">フィルターは、細かく絞り込んだデータ セットを返したり、返されたデータをさまざま方法で表示したりする方法として利用できます。たとえば、場所の傾向レポートでは、返されたデータをアクセスの種類 (内部アクセスまたは外部アクセス) や有線/ワイヤレス ネットワーク接続でフィルターできます。データをグループ化する方法も選択できます。この場合は、時間、日、または週を基準に通話がグループ化されます。</span><span class="sxs-lookup"><span data-stu-id="cd62c-p101">Filters provide a way for you to return a more finely-targeted set of data or to view the returned data in different ways. For example, the Location Trend Report enables you to filter the returned data by such things as access type (that is, interval access vs. external access) or by wired/wireless network connection. You can also choose how data should be grouped. In this case, calls are grouped by hour, day, or week.</span></span>

<span data-ttu-id="cd62c-110">次の表に、場所の傾向レポートで使用できるフィルターを示します。</span><span class="sxs-lookup"><span data-stu-id="cd62c-110">The following table lists the filters that you can use with the Location Trend Report.</span></span>

### <a name="location-trend-report-filters"></a><span data-ttu-id="cd62c-111">場所の傾向レポートのフィルター</span><span class="sxs-lookup"><span data-stu-id="cd62c-111">Location Trend Report Filters</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="cd62c-112">名前</span><span class="sxs-lookup"><span data-stu-id="cd62c-112">Name</span></span></th>
<th><span data-ttu-id="cd62c-113">説明</span><span class="sxs-lookup"><span data-stu-id="cd62c-113">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="cd62c-114"><strong>From</strong></span><span class="sxs-lookup"><span data-stu-id="cd62c-114"><strong>From</strong></span></span></p></td>
<td><p><span data-ttu-id="cd62c-p102">時間範囲の開始日と開始時刻。データを時間単位で表示するには、次のように開始日と開始時刻の両方を入力します。</span><span class="sxs-lookup"><span data-stu-id="cd62c-p102">Start date/time for the time range. To view data by hours, enter both the start date and time as follows:</span></span></p>
<p><span data-ttu-id="cd62c-117">7/7/2012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="cd62c-117">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="cd62c-p103">開始時刻を入力しないと、レポートは自動的に指定日の午前 12:00 に開始します。データを日単位で表示するには、次のように日付のみを入力します。</span><span class="sxs-lookup"><span data-stu-id="cd62c-p103">If you do not enter a start time, the report automatically begins at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="cd62c-120">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="cd62c-120">7/7/2012</span></span></p>
<p><span data-ttu-id="cd62c-121">週単位または月単位で表示するには、表示する週または月の任意の日付を入力します (その週または月の最初の日である必要はありません)。</span><span class="sxs-lookup"><span data-stu-id="cd62c-121">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="cd62c-122">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="cd62c-122">7/3/2012</span></span></p>
<p><span data-ttu-id="cd62c-123">週は、常に日曜日から土曜日までです。</span><span class="sxs-lookup"><span data-stu-id="cd62c-123">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cd62c-124"><strong>To</strong></span><span class="sxs-lookup"><span data-stu-id="cd62c-124"><strong>To</strong></span></span></p></td>
<td><p><span data-ttu-id="cd62c-p104">時間範囲の終了日と終了時刻。データを時間単位で表示するには、次のように終了日と終了時刻の両方を入力します。</span><span class="sxs-lookup"><span data-stu-id="cd62c-p104">End date/time for the time range. To view data by hours, enter both the end date and time as follows:</span></span></p>
<p><span data-ttu-id="cd62c-127">7/7/2012 13:00</span><span class="sxs-lookup"><span data-stu-id="cd62c-127">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="cd62c-p105">終了時刻を入力しないと、レポートは自動的に指定日の午前 12:00 に終了します。データを日単位で表示するには、次のように日付のみを入力します。</span><span class="sxs-lookup"><span data-stu-id="cd62c-p105">If you do not enter an end time, the report automatically ends at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="cd62c-130">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="cd62c-130">7/7/2012</span></span></p>
<p><span data-ttu-id="cd62c-131">週単位または月単位で表示するには、表示する週または月の任意の日付を入力します (その週または月の最初の日である必要はありません)。</span><span class="sxs-lookup"><span data-stu-id="cd62c-131">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="cd62c-132">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="cd62c-132">7/3/2012</span></span></p>
<p><span data-ttu-id="cd62c-133">週は、常に日曜日から土曜日までです。</span><span class="sxs-lookup"><span data-stu-id="cd62c-133">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cd62c-134"><strong>間隔</strong></span><span class="sxs-lookup"><span data-stu-id="cd62c-134"><strong>Interval</strong></span></span></p></td>
<td><p><span data-ttu-id="cd62c-p106">時間間隔です。次のいずれかを選択します。</span><span class="sxs-lookup"><span data-stu-id="cd62c-p106">Time interval. Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="cd62c-137">時間単位 (最大 25 時間の表示が可能)</span><span class="sxs-lookup"><span data-stu-id="cd62c-137">Hourly (a maximum of 25 hours can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="cd62c-138">日単位 (最大 31 日の表示が可能)</span><span class="sxs-lookup"><span data-stu-id="cd62c-138">Daily (a maximum of 31 days can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="cd62c-139">週単位 (最大 12 週の表示が可能)</span><span class="sxs-lookup"><span data-stu-id="cd62c-139">Weekly (a maximum of 12 weeks can be displayed)</span></span></p></li>
</ul>
<p><span data-ttu-id="cd62c-p107">入力した開始日と終了日が選択した間隔で使用できる値の最大数を超える場合は、最大数の値 (開始日からカウント) のみが表示されます。たとえば、開始日と終了日をそれぞれ 2012/8/7 (2012 年 8 月 7 日)、2012/9/28 (2012 年 9 月 28 日) として毎日の間隔を選択しても、2012 年 8 月 7 日の午前 12:00 から 2012 年 9 月 7 日の午前 12:00 までの日付のデータ (つまり、合計 31 日分のデータのみ) が表示されることになります。</span><span class="sxs-lookup"><span data-stu-id="cd62c-p107">If the start and end dates exceed the maximum number of values allowed for the selected interval, only the maximum number of values (starting from the start date) is displayed. For example, if you select the Daily interval with a start date of 1/1/2011 and an end date of 2/28/2011, data is displayed for the days 8/1/2011 12:00 AM to 9/1/2011 12:00 AM (that is, a total of 31 days' worth of data).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cd62c-142">[<strong>アクセスの種類</strong>]</span><span class="sxs-lookup"><span data-stu-id="cd62c-142"><strong>Access type</strong></span></span></p></td>
<td><p><span data-ttu-id="cd62c-p108">クライアントが通話時に内部ネットワークにログオンしたか、外部ネットワークにログオンしたかを示します。次のいずれかを選択します。</span><span class="sxs-lookup"><span data-stu-id="cd62c-p108">Indicates whether the client was logged on to the internal network or the external network when the call was placed. Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="cd62c-145">いずれ</span><span class="sxs-lookup"><span data-stu-id="cd62c-145">[All]</span></span></p></li>
<li><p><span data-ttu-id="cd62c-146">内部</span><span class="sxs-lookup"><span data-stu-id="cd62c-146">Internal</span></span></p></li>
<li><p><span data-ttu-id="cd62c-147">External</span><span class="sxs-lookup"><span data-stu-id="cd62c-147">External</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cd62c-148">[<strong>ネットワークの種類</strong>]</span><span class="sxs-lookup"><span data-stu-id="cd62c-148"><strong>Network type</strong></span></span></p></td>
<td><p><span data-ttu-id="cd62c-p109">通話時にクライアントが接続したネットワークの種類を示します。次のいずれかを選択します。</span><span class="sxs-lookup"><span data-stu-id="cd62c-p109">Indicates the type of network the client was connected to when the call was placed. Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="cd62c-151">いずれ</span><span class="sxs-lookup"><span data-stu-id="cd62c-151">[All]</span></span></p></li>
<li><p><span data-ttu-id="cd62c-152">有線</span><span class="sxs-lookup"><span data-stu-id="cd62c-152">Wired</span></span></p></li>
<li><p><span data-ttu-id="cd62c-153">通信</span><span class="sxs-lookup"><span data-stu-id="cd62c-153">Wireless</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cd62c-154"><strong>VPN</strong></span><span class="sxs-lookup"><span data-stu-id="cd62c-154"><strong>VPN</strong></span></span></p></td>
<td><p><span data-ttu-id="cd62c-p110">通話時に外部クライアントが仮想プライベート ネットワーク (VPN) 接続を使用したかどうかを示します。次のいずれかを選択します。</span><span class="sxs-lookup"><span data-stu-id="cd62c-p110">Indicates whether an external client was using a virtual private network (VPN) connection when the call was placed. Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="cd62c-157">いずれ</span><span class="sxs-lookup"><span data-stu-id="cd62c-157">[All]</span></span></p></li>
<li><p><span data-ttu-id="cd62c-158">VPN</span><span class="sxs-lookup"><span data-stu-id="cd62c-158">VPN</span></span></p></li>
<li><p><span data-ttu-id="cd62c-159">非 VPN</span><span class="sxs-lookup"><span data-stu-id="cd62c-159">Non-VPN</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

