---
title: 'Lync Server 2013: メディア品質メトリック分布レポート'
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
ms.openlocfilehash: 48ee62d2eee4ab6e18b3c0c07b46f79b779bcce1
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/21/2020
ms.locfileid: "42217683"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="the-media-quality-metrics-distribution-report-in-lync-server-2013"></a><span data-ttu-id="e3f66-102">Lync Server 2013 のメディア品質メトリック分布レポート</span><span class="sxs-lookup"><span data-stu-id="e3f66-102">The Media Quality Metrics Distribution Report in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e3f66-103">_**トピックの最終更新日:** 2012-06-06_</span><span class="sxs-lookup"><span data-stu-id="e3f66-103">_**Topic Last Modified:** 2012-06-06_</span></span>

<span data-ttu-id="e3f66-104">メディア品質メトリック分布レポートを使用すると、ジッターやパケット損失などの qoe (Quality of Experience) 指標の分布値を示すグラフを表示できます。</span><span class="sxs-lookup"><span data-stu-id="e3f66-104">The Media Quality Metrics Distribution Report enables you to see a graph that shows the distribution values for a Quality of Experience metric such as jitter or packet loss.</span></span> <span data-ttu-id="e3f66-105">たとえば、ユーザーが合計10件の通話を行うとします。これらの10の呼び出しでは、次のラウンドトリップ時間が報告されます。</span><span class="sxs-lookup"><span data-stu-id="e3f66-105">For example, suppose your users make a total of 10 phone calls; those 10 calls report the following roundtrip times:</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="e3f66-106">呼び出し番号</span><span class="sxs-lookup"><span data-stu-id="e3f66-106">Call Number</span></span></th>
<th><span data-ttu-id="e3f66-107">往復時間 (ミリ秒)</span><span class="sxs-lookup"><span data-stu-id="e3f66-107">Roundtrip Time (milliseconds)</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e3f66-108">1-d</span><span class="sxs-lookup"><span data-stu-id="e3f66-108">1</span></span></p></td>
<td><p><span data-ttu-id="e3f66-109">50</span><span class="sxs-lookup"><span data-stu-id="e3f66-109">50</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e3f66-110">pbm-2</span><span class="sxs-lookup"><span data-stu-id="e3f66-110">2</span></span></p></td>
<td><p><span data-ttu-id="e3f66-111">50</span><span class="sxs-lookup"><span data-stu-id="e3f66-111">50</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e3f66-112">1/3</span><span class="sxs-lookup"><span data-stu-id="e3f66-112">3</span></span></p></td>
<td><p><span data-ttu-id="e3f66-113">50</span><span class="sxs-lookup"><span data-stu-id="e3f66-113">50</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e3f66-114">2/4</span><span class="sxs-lookup"><span data-stu-id="e3f66-114">4</span></span></p></td>
<td><p><span data-ttu-id="e3f66-115">50</span><span class="sxs-lookup"><span data-stu-id="e3f66-115">50</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e3f66-116">5</span><span class="sxs-lookup"><span data-stu-id="e3f66-116">5</span></span></p></td>
<td><p><span data-ttu-id="e3f66-117">50</span><span class="sxs-lookup"><span data-stu-id="e3f66-117">50</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e3f66-118">6 </span><span class="sxs-lookup"><span data-stu-id="e3f66-118">6</span></span></p></td>
<td><p><span data-ttu-id="e3f66-119">50</span><span class="sxs-lookup"><span data-stu-id="e3f66-119">50</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e3f66-120">7 </span><span class="sxs-lookup"><span data-stu-id="e3f66-120">7</span></span></p></td>
<td><p><span data-ttu-id="e3f66-121">50</span><span class="sxs-lookup"><span data-stu-id="e3f66-121">50</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e3f66-122">8 </span><span class="sxs-lookup"><span data-stu-id="e3f66-122">8</span></span></p></td>
<td><p><span data-ttu-id="e3f66-123">4550</span><span class="sxs-lookup"><span data-stu-id="e3f66-123">4550</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e3f66-124">9 </span><span class="sxs-lookup"><span data-stu-id="e3f66-124">9</span></span></p></td>
<td><p><span data-ttu-id="e3f66-125">50</span><span class="sxs-lookup"><span data-stu-id="e3f66-125">50</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e3f66-126">10 </span><span class="sxs-lookup"><span data-stu-id="e3f66-126">10</span></span></p></td>
<td><p><span data-ttu-id="e3f66-127">50</span><span class="sxs-lookup"><span data-stu-id="e3f66-127">50</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="e3f66-128">これらのラウンドトリップ時間の平均は500ミリ秒 (5000 は10で割る) です。</span><span class="sxs-lookup"><span data-stu-id="e3f66-128">The average for those roundtrip times is 500 milliseconds (5000 divided by 10).</span></span> <span data-ttu-id="e3f66-129">500ミリ秒は、非常に大きな往復時間です。そのため、ネットワークの輻輳に重大な問題があると思われるかもしれません。</span><span class="sxs-lookup"><span data-stu-id="e3f66-129">Five hundred milliseconds is an extremely large roundtrip time; as a result, you might believe that you have a serious problem with network congestion.</span></span> <span data-ttu-id="e3f66-130">(通常、長いラウンドトリップ時間は、ネットワークの過負荷の結果です。)</span><span class="sxs-lookup"><span data-stu-id="e3f66-130">(Long roundtrip times are typically the result of overloaded networks.)</span></span>

<span data-ttu-id="e3f66-131">実際には、通話の90% は、優れた往復時間でした。結果全体に悪影響を与える1つの呼び出しがあっただけの場合があります。</span><span class="sxs-lookup"><span data-stu-id="e3f66-131">In reality, of course, 90% of your calls had excellent round trip times; you merely had one bad call that skewed the overall results.</span></span> <span data-ttu-id="e3f66-132">平均往復時間を確認するだけの場合は、非常に不正確な結論にジャンプする可能性があります。</span><span class="sxs-lookup"><span data-stu-id="e3f66-132">If you only look at the average roundtrip time you might jump to a very wrong conclusion.</span></span>

<span data-ttu-id="e3f66-133">メディア品質メトリック分布レポートは、指定された指標 (ラウンドトリップ時間など) のグラフィカルな配布を表示することにより、誤った結果にジャンプしないようにします。</span><span class="sxs-lookup"><span data-stu-id="e3f66-133">The Media Quality Metrics Distribution Report helps you avoid jumping to wrong conclusions by showing you a graphical distribution of a specified metric (such as round trip time).</span></span> <span data-ttu-id="e3f66-134">これらのグラフは、9個の優れた通話と、非常に悪い呼び出しがあることを明確にするのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="e3f66-134">These graphs can help make it clear that you had nine very good calls and one very bad call.</span></span> <span data-ttu-id="e3f66-135">確かに、1回の呼び出しをさらに調査する必要がある場合もあります。ただし、この時点では少なくとも、ネットワークに大幅な変更を加える理由がないことを推奨するのは、10件の通話が9つの場合ということです。</span><span class="sxs-lookup"><span data-stu-id="e3f66-135">Admittedly, you might still want to further investigate that one call; however, the fact that 9 out of the 10 calls were very good suggests that there is no reason to make any drastic changes to your network, at least not at this point in time.</span></span>

<div>

## <a name="filters"></a><span data-ttu-id="e3f66-136">フィルター</span><span class="sxs-lookup"><span data-stu-id="e3f66-136">Filters</span></span>

<span data-ttu-id="e3f66-137">フィルターは、細かく絞り込んだデータ セットを返したり、返されたデータをさまざま方法で表示したりする方法として利用できます。</span><span class="sxs-lookup"><span data-stu-id="e3f66-137">Filters provide a way for you to return a more finely-targeted set of data or to view the returned data in different ways.</span></span> <span data-ttu-id="e3f66-138">次の表に、メディア品質メトリック分布レポートで使用できるフィルターを示します。</span><span class="sxs-lookup"><span data-stu-id="e3f66-138">The following table lists the filters that you can use with the Media Quality Metrics Distribution Report.</span></span>

### <a name="media-quality-metrics-distribution-report-filters"></a><span data-ttu-id="e3f66-139">メディア品質メトリック分布レポートのフィルター</span><span class="sxs-lookup"><span data-stu-id="e3f66-139">Media Quality Metrics Distribution Report Filters</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="e3f66-140">名前</span><span class="sxs-lookup"><span data-stu-id="e3f66-140">Name</span></span></th>
<th><span data-ttu-id="e3f66-141">説明</span><span class="sxs-lookup"><span data-stu-id="e3f66-141">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e3f66-142"><strong>From</strong></span><span class="sxs-lookup"><span data-stu-id="e3f66-142"><strong>From</strong></span></span></p></td>
<td><p><span data-ttu-id="e3f66-p106">時間範囲の開始日と開始時刻。データを時間単位で表示するには、次のように開始日と開始時刻の両方を入力します。</span><span class="sxs-lookup"><span data-stu-id="e3f66-p106">Start date/time for the time range. To view data by hours, enter both the start date and time as follows:</span></span></p>
<p><span data-ttu-id="e3f66-145">7/7/2012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="e3f66-145">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="e3f66-p107">開始時刻を入力しないと、レポートは自動的に指定日の午前 12:00 に開始します。データを日単位で表示するには、次のように日付のみを入力します。</span><span class="sxs-lookup"><span data-stu-id="e3f66-p107">If you do not enter a start time, the report automatically begins at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="e3f66-148">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="e3f66-148">7/7/2012</span></span></p>
<p><span data-ttu-id="e3f66-149">週単位または月単位で表示するには、表示する週または月の任意の日付を入力します (その週または月の最初の日である必要はありません)。</span><span class="sxs-lookup"><span data-stu-id="e3f66-149">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="e3f66-150">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="e3f66-150">7/3/2012</span></span></p>
<p><span data-ttu-id="e3f66-151">週は、常に日曜日から土曜日までです。</span><span class="sxs-lookup"><span data-stu-id="e3f66-151">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e3f66-152"><strong>To</strong></span><span class="sxs-lookup"><span data-stu-id="e3f66-152"><strong>To</strong></span></span></p></td>
<td><p><span data-ttu-id="e3f66-p108">時間範囲の終了日と終了時刻。データを時間単位で表示するには、次のように終了日と終了時刻の両方を入力します。</span><span class="sxs-lookup"><span data-stu-id="e3f66-p108">End date/time for the time range. To view data by hours, enter both the end date and time as follows:</span></span></p>
<p><span data-ttu-id="e3f66-155">7/7/2012 13:00</span><span class="sxs-lookup"><span data-stu-id="e3f66-155">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="e3f66-p109">終了時刻を入力しないと、レポートは自動的に指定日の午前 12:00 に終了します。データを日単位で表示するには、次のように日付のみを入力します。</span><span class="sxs-lookup"><span data-stu-id="e3f66-p109">If you do not enter an end time, the report automatically ends at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="e3f66-158">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="e3f66-158">7/7/2012</span></span></p>
<p><span data-ttu-id="e3f66-159">週単位または月単位で表示するには、表示する週または月の任意の日付を入力します (その週または月の最初の日である必要はありません)。</span><span class="sxs-lookup"><span data-stu-id="e3f66-159">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="e3f66-160">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="e3f66-160">7/3/2012</span></span></p>
<p><span data-ttu-id="e3f66-161">週は、常に日曜日から土曜日までです。</span><span class="sxs-lookup"><span data-stu-id="e3f66-161">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e3f66-162"><strong>X 軸の最小値</strong></span><span class="sxs-lookup"><span data-stu-id="e3f66-162"><strong>Minimum in x axis</strong></span></span></p></td>
<td><p><span data-ttu-id="e3f66-163">グラフの X 軸に表示される最小の値。</span><span class="sxs-lookup"><span data-stu-id="e3f66-163">Lowest value to be displayed on the X axis of the graph.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e3f66-164"><strong>X 軸の最大値</strong></span><span class="sxs-lookup"><span data-stu-id="e3f66-164"><strong>Maximum in x axis</strong></span></span></p></td>
<td><p><span data-ttu-id="e3f66-165">グラフの X 軸に表示される最大値。</span><span class="sxs-lookup"><span data-stu-id="e3f66-165">Highest value to be displayed on the X axis of the graph.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e3f66-166">[<strong>アクセスの種類</strong>]</span><span class="sxs-lookup"><span data-stu-id="e3f66-166"><strong>Access type</strong></span></span></p></td>
<td><p><span data-ttu-id="e3f66-p110">クライアントが通話時に内部ネットワークにログオンしたか、外部ネットワークにログオンしたかを示します。次のいずれかを選択します。</span><span class="sxs-lookup"><span data-stu-id="e3f66-p110">Indicates whether the client was logged on to the internal network or the external network when the call was placed. Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="e3f66-169">いずれ</span><span class="sxs-lookup"><span data-stu-id="e3f66-169">[All]</span></span></p></li>
<li><p><span data-ttu-id="e3f66-170">内部</span><span class="sxs-lookup"><span data-stu-id="e3f66-170">Internal</span></span></p></li>
<li><p><span data-ttu-id="e3f66-171">External</span><span class="sxs-lookup"><span data-stu-id="e3f66-171">External</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e3f66-172"><strong>VPN</strong></span><span class="sxs-lookup"><span data-stu-id="e3f66-172"><strong>VPN</strong></span></span></p></td>
<td><p><span data-ttu-id="e3f66-p111">通話時に外部クライアントが仮想プライベート ネットワーク (VPN) 接続を使用したかどうかを示します。次のいずれかを選択します。</span><span class="sxs-lookup"><span data-stu-id="e3f66-p111">Indicates whether an external client was using a virtual private network (VPN) connection when the call was placed. Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="e3f66-175">いずれ</span><span class="sxs-lookup"><span data-stu-id="e3f66-175">[All]</span></span></p></li>
<li><p><span data-ttu-id="e3f66-176">VPN</span><span class="sxs-lookup"><span data-stu-id="e3f66-176">VPN</span></span></p></li>
<li><p><span data-ttu-id="e3f66-177">非 VPN</span><span class="sxs-lookup"><span data-stu-id="e3f66-177">Non-VPN</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e3f66-178">[<strong>ネットワークの種類</strong>]</span><span class="sxs-lookup"><span data-stu-id="e3f66-178"><strong>Network type</strong></span></span></p></td>
<td><p><span data-ttu-id="e3f66-p112">通話時にクライアントが接続したネットワークの種類を示します。次のいずれかを選択します。</span><span class="sxs-lookup"><span data-stu-id="e3f66-p112">Indicates the type of network the client was connected to when the call was placed. Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="e3f66-181">いずれ</span><span class="sxs-lookup"><span data-stu-id="e3f66-181">[All]</span></span></p></li>
<li><p><span data-ttu-id="e3f66-182">有線</span><span class="sxs-lookup"><span data-stu-id="e3f66-182">Wired</span></span></p></li>
<li><p><span data-ttu-id="e3f66-183">通信</span><span class="sxs-lookup"><span data-stu-id="e3f66-183">Wireless</span></span></p></li>
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

