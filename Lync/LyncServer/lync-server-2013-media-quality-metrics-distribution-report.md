---
title: 'Lync Server 2013: メディア品質メトリック分布レポート'
description: 'Lync Server 2013: メディア品質メトリック分布レポート。'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Media Quality Metrics Distribution Report
ms:assetid: d07996e6-b0a5-4ff8-9512-ab707762b4e2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205262(v=OCS.15)
ms:contentKeyID: 48185409
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: def56580477dadf989268e1fc24fcec7776c00d8
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48548153"
---
# <a name="the-media-quality-metrics-distribution-report-in-lync-server-2013"></a><span data-ttu-id="e65e3-103">Lync Server 2013 のメディア品質メトリック分布レポート</span><span class="sxs-lookup"><span data-stu-id="e65e3-103">The Media Quality Metrics Distribution Report in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e65e3-104">_**トピックの最終更新日:** 2012-06-06_</span><span class="sxs-lookup"><span data-stu-id="e65e3-104">_**Topic Last Modified:** 2012-06-06_</span></span>

<span data-ttu-id="e65e3-105">メディア品質メトリック分布レポートを使用すると、ジッターやパケット損失などの qoe (Quality of Experience) 指標の分布値を示すグラフを表示できます。</span><span class="sxs-lookup"><span data-stu-id="e65e3-105">The Media Quality Metrics Distribution Report enables you to see a graph that shows the distribution values for a Quality of Experience metric such as jitter or packet loss.</span></span> <span data-ttu-id="e65e3-106">たとえば、ユーザーが合計10件の通話を行うとします。これらの10の呼び出しでは、次のラウンドトリップ時間が報告されます。</span><span class="sxs-lookup"><span data-stu-id="e65e3-106">For example, suppose your users make a total of 10 phone calls; those 10 calls report the following roundtrip times:</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="e65e3-107">呼び出し番号</span><span class="sxs-lookup"><span data-stu-id="e65e3-107">Call Number</span></span></th>
<th><span data-ttu-id="e65e3-108">往復時間 (ミリ秒)</span><span class="sxs-lookup"><span data-stu-id="e65e3-108">Roundtrip Time (milliseconds)</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e65e3-109">1-d</span><span class="sxs-lookup"><span data-stu-id="e65e3-109">1</span></span></p></td>
<td><p><span data-ttu-id="e65e3-110">50</span><span class="sxs-lookup"><span data-stu-id="e65e3-110">50</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e65e3-111">pbm-2</span><span class="sxs-lookup"><span data-stu-id="e65e3-111">2</span></span></p></td>
<td><p><span data-ttu-id="e65e3-112">50</span><span class="sxs-lookup"><span data-stu-id="e65e3-112">50</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e65e3-113">1/3</span><span class="sxs-lookup"><span data-stu-id="e65e3-113">3</span></span></p></td>
<td><p><span data-ttu-id="e65e3-114">50</span><span class="sxs-lookup"><span data-stu-id="e65e3-114">50</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e65e3-115">4 </span><span class="sxs-lookup"><span data-stu-id="e65e3-115">4</span></span></p></td>
<td><p><span data-ttu-id="e65e3-116">50</span><span class="sxs-lookup"><span data-stu-id="e65e3-116">50</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e65e3-117">5 </span><span class="sxs-lookup"><span data-stu-id="e65e3-117">5</span></span></p></td>
<td><p><span data-ttu-id="e65e3-118">50</span><span class="sxs-lookup"><span data-stu-id="e65e3-118">50</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e65e3-119">6 </span><span class="sxs-lookup"><span data-stu-id="e65e3-119">6</span></span></p></td>
<td><p><span data-ttu-id="e65e3-120">50</span><span class="sxs-lookup"><span data-stu-id="e65e3-120">50</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e65e3-121">7 </span><span class="sxs-lookup"><span data-stu-id="e65e3-121">7</span></span></p></td>
<td><p><span data-ttu-id="e65e3-122">50</span><span class="sxs-lookup"><span data-stu-id="e65e3-122">50</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e65e3-123">8 </span><span class="sxs-lookup"><span data-stu-id="e65e3-123">8</span></span></p></td>
<td><p><span data-ttu-id="e65e3-124">4550</span><span class="sxs-lookup"><span data-stu-id="e65e3-124">4550</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e65e3-125">9 </span><span class="sxs-lookup"><span data-stu-id="e65e3-125">9</span></span></p></td>
<td><p><span data-ttu-id="e65e3-126">50</span><span class="sxs-lookup"><span data-stu-id="e65e3-126">50</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e65e3-127">10  </span><span class="sxs-lookup"><span data-stu-id="e65e3-127">10</span></span></p></td>
<td><p><span data-ttu-id="e65e3-128">50</span><span class="sxs-lookup"><span data-stu-id="e65e3-128">50</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="e65e3-129">これらのラウンドトリップ時間の平均は500ミリ秒 (5000 は10で割る) です。</span><span class="sxs-lookup"><span data-stu-id="e65e3-129">The average for those roundtrip times is 500 milliseconds (5000 divided by 10).</span></span> <span data-ttu-id="e65e3-130">500ミリ秒は、非常に大きな往復時間です。そのため、ネットワークの輻輳に重大な問題があると思われるかもしれません。</span><span class="sxs-lookup"><span data-stu-id="e65e3-130">Five hundred milliseconds is an extremely large roundtrip time; as a result, you might believe that you have a serious problem with network congestion.</span></span> <span data-ttu-id="e65e3-131">(通常、長いラウンドトリップ時間は、ネットワークの過負荷の結果です。)</span><span class="sxs-lookup"><span data-stu-id="e65e3-131">(Long roundtrip times are typically the result of overloaded networks.)</span></span>

<span data-ttu-id="e65e3-132">実際には、通話の90% は、優れた往復時間でした。結果全体に悪影響を与える1つの呼び出しがあっただけの場合があります。</span><span class="sxs-lookup"><span data-stu-id="e65e3-132">In reality, of course, 90% of your calls had excellent round trip times; you merely had one bad call that skewed the overall results.</span></span> <span data-ttu-id="e65e3-133">平均往復時間を確認するだけの場合は、非常に不正確な結論にジャンプする可能性があります。</span><span class="sxs-lookup"><span data-stu-id="e65e3-133">If you only look at the average roundtrip time you might jump to a very wrong conclusion.</span></span>

<span data-ttu-id="e65e3-134">メディア品質メトリック分布レポートは、指定された指標 (ラウンドトリップ時間など) のグラフィカルな配布を表示することにより、誤った結果にジャンプしないようにします。</span><span class="sxs-lookup"><span data-stu-id="e65e3-134">The Media Quality Metrics Distribution Report helps you avoid jumping to wrong conclusions by showing you a graphical distribution of a specified metric (such as round trip time).</span></span> <span data-ttu-id="e65e3-135">これらのグラフは、9個の優れた通話と、非常に悪い呼び出しがあることを明確にするのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="e65e3-135">These graphs can help make it clear that you had nine very good calls and one very bad call.</span></span> <span data-ttu-id="e65e3-136">確かに、1回の呼び出しをさらに調査する必要がある場合もあります。ただし、この時点では少なくとも、ネットワークに大幅な変更を加える理由がないことを推奨するのは、10件の通話が9つの場合ということです。</span><span class="sxs-lookup"><span data-stu-id="e65e3-136">Admittedly, you might still want to further investigate that one call; however, the fact that 9 out of the 10 calls were very good suggests that there is no reason to make any drastic changes to your network, at least not at this point in time.</span></span>

<div>

## <a name="filters"></a><span data-ttu-id="e65e3-137">フィルター</span><span class="sxs-lookup"><span data-stu-id="e65e3-137">Filters</span></span>

<span data-ttu-id="e65e3-138">フィルターは、細かく絞り込んだデータ セットを返したり、返されたデータをさまざま方法で表示したりする方法として利用できます。</span><span class="sxs-lookup"><span data-stu-id="e65e3-138">Filters provide a way for you to return a more finely-targeted set of data or to view the returned data in different ways.</span></span> <span data-ttu-id="e65e3-139">次の表に、メディア品質メトリック分布レポートで使用できるフィルターを示します。</span><span class="sxs-lookup"><span data-stu-id="e65e3-139">The following table lists the filters that you can use with the Media Quality Metrics Distribution Report.</span></span>

### <a name="media-quality-metrics-distribution-report-filters"></a><span data-ttu-id="e65e3-140">メディア品質メトリック分布レポートのフィルター</span><span class="sxs-lookup"><span data-stu-id="e65e3-140">Media Quality Metrics Distribution Report Filters</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="e65e3-141">名前</span><span class="sxs-lookup"><span data-stu-id="e65e3-141">Name</span></span></th>
<th><span data-ttu-id="e65e3-142">説明</span><span class="sxs-lookup"><span data-stu-id="e65e3-142">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e65e3-143"><strong>From</strong></span><span class="sxs-lookup"><span data-stu-id="e65e3-143"><strong>From</strong></span></span></p></td>
<td><p><span data-ttu-id="e65e3-p106">時間範囲の開始日と開始時刻。データを時間単位で表示するには、次のように開始日と開始時刻の両方を入力します。</span><span class="sxs-lookup"><span data-stu-id="e65e3-p106">Start date/time for the time range. To view data by hours, enter both the start date and time as follows:</span></span></p>
<p><span data-ttu-id="e65e3-146">7/7/2012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="e65e3-146">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="e65e3-p107">開始時刻を入力しないと、レポートは自動的に指定日の午前 12:00 に開始します。データを日単位で表示するには、次のように日付のみを入力します。</span><span class="sxs-lookup"><span data-stu-id="e65e3-p107">If you do not enter a start time, the report automatically begins at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="e65e3-149">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="e65e3-149">7/7/2012</span></span></p>
<p><span data-ttu-id="e65e3-150">週単位または月単位で表示するには、表示する週または月の任意の日付を入力します (その週または月の最初の日である必要はありません)。</span><span class="sxs-lookup"><span data-stu-id="e65e3-150">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="e65e3-151">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="e65e3-151">7/3/2012</span></span></p>
<p><span data-ttu-id="e65e3-152">週は、常に日曜日から土曜日までです。</span><span class="sxs-lookup"><span data-stu-id="e65e3-152">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e65e3-153"><strong>To</strong></span><span class="sxs-lookup"><span data-stu-id="e65e3-153"><strong>To</strong></span></span></p></td>
<td><p><span data-ttu-id="e65e3-p108">時間範囲の終了日と終了時刻。データを時間単位で表示するには、次のように終了日と終了時刻の両方を入力します。</span><span class="sxs-lookup"><span data-stu-id="e65e3-p108">End date/time for the time range. To view data by hours, enter both the end date and time as follows:</span></span></p>
<p><span data-ttu-id="e65e3-156">7/7/2012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="e65e3-156">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="e65e3-p109">終了時刻を入力しないと、レポートは自動的に指定日の午前 12:00 に終了します。データを日単位で表示するには、次のように日付のみを入力します。</span><span class="sxs-lookup"><span data-stu-id="e65e3-p109">If you do not enter an end time, the report automatically ends at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="e65e3-159">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="e65e3-159">7/7/2012</span></span></p>
<p><span data-ttu-id="e65e3-160">週単位または月単位で表示するには、表示する週または月の任意の日付を入力します (その週または月の最初の日である必要はありません)。</span><span class="sxs-lookup"><span data-stu-id="e65e3-160">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="e65e3-161">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="e65e3-161">7/3/2012</span></span></p>
<p><span data-ttu-id="e65e3-162">週は、常に日曜日から土曜日までです。</span><span class="sxs-lookup"><span data-stu-id="e65e3-162">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e65e3-163"><strong>X 軸の最小値</strong></span><span class="sxs-lookup"><span data-stu-id="e65e3-163"><strong>Minimum in x axis</strong></span></span></p></td>
<td><p><span data-ttu-id="e65e3-164">グラフの X 軸に表示される最小の値。</span><span class="sxs-lookup"><span data-stu-id="e65e3-164">Lowest value to be displayed on the X axis of the graph.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e65e3-165"><strong>X 軸の最大値</strong></span><span class="sxs-lookup"><span data-stu-id="e65e3-165"><strong>Maximum in x axis</strong></span></span></p></td>
<td><p><span data-ttu-id="e65e3-166">グラフの X 軸に表示される最大値。</span><span class="sxs-lookup"><span data-stu-id="e65e3-166">Highest value to be displayed on the X axis of the graph.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e65e3-167">[<strong>アクセスの種類</strong>]</span><span class="sxs-lookup"><span data-stu-id="e65e3-167"><strong>Access type</strong></span></span></p></td>
<td><p><span data-ttu-id="e65e3-p110">クライアントが通話時に内部ネットワークにログオンしたか、外部ネットワークにログオンしたかを示します。次のいずれかを選択します。</span><span class="sxs-lookup"><span data-stu-id="e65e3-p110">Indicates whether the client was logged on to the internal network or the external network when the call was placed. Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="e65e3-170">[All]</span><span class="sxs-lookup"><span data-stu-id="e65e3-170">[All]</span></span></p></li>
<li><p><span data-ttu-id="e65e3-171">内部</span><span class="sxs-lookup"><span data-stu-id="e65e3-171">Internal</span></span></p></li>
<li><p><span data-ttu-id="e65e3-172">外部</span><span class="sxs-lookup"><span data-stu-id="e65e3-172">External</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e65e3-173"><strong>VPN</strong></span><span class="sxs-lookup"><span data-stu-id="e65e3-173"><strong>VPN</strong></span></span></p></td>
<td><p><span data-ttu-id="e65e3-p111">通話時に外部クライアントが仮想プライベート ネットワーク (VPN) 接続を使用したかどうかを示します。次のいずれかを選択します。</span><span class="sxs-lookup"><span data-stu-id="e65e3-p111">Indicates whether an external client was using a virtual private network (VPN) connection when the call was placed. Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="e65e3-176">[All]</span><span class="sxs-lookup"><span data-stu-id="e65e3-176">[All]</span></span></p></li>
<li><p><span data-ttu-id="e65e3-177">VPN</span><span class="sxs-lookup"><span data-stu-id="e65e3-177">VPN</span></span></p></li>
<li><p><span data-ttu-id="e65e3-178">非 VPN</span><span class="sxs-lookup"><span data-stu-id="e65e3-178">Non-VPN</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e65e3-179">[<strong>ネットワークの種類</strong>]</span><span class="sxs-lookup"><span data-stu-id="e65e3-179"><strong>Network type</strong></span></span></p></td>
<td><p><span data-ttu-id="e65e3-p112">通話時にクライアントが接続したネットワークの種類を示します。次のいずれかを選択します。</span><span class="sxs-lookup"><span data-stu-id="e65e3-p112">Indicates the type of network the client was connected to when the call was placed. Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="e65e3-182">[All]</span><span class="sxs-lookup"><span data-stu-id="e65e3-182">[All]</span></span></p></li>
<li><p><span data-ttu-id="e65e3-183">有線</span><span class="sxs-lookup"><span data-stu-id="e65e3-183">Wired</span></span></p></li>
<li><p><span data-ttu-id="e65e3-184">通信</span><span class="sxs-lookup"><span data-stu-id="e65e3-184">Wireless</span></span></p></li>
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

