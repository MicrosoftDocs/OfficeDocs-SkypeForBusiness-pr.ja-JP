---
title: 'Lync Server 2013: メディア品質指標配布レポート'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Media Quality Metrics Distribution Report
ms:assetid: d07996e6-b0a5-4ff8-9512-ab707762b4e2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205262(v=OCS.15)
ms:contentKeyID: 48185409
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d1d814fd001f3510a7ae83e63746bdc1265932e4
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34827390"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="the-media-quality-metrics-distribution-report-in-lync-server-2013"></a><span data-ttu-id="133ce-102">Lync Server 2013 でのメディア品質指標の配布レポート</span><span class="sxs-lookup"><span data-stu-id="133ce-102">The Media Quality Metrics Distribution Report in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="133ce-103">_**最終更新日:** 2012-06-06_</span><span class="sxs-lookup"><span data-stu-id="133ce-103">_**Topic Last Modified:** 2012-06-06_</span></span>

<span data-ttu-id="133ce-p101">メディア品質メトリック分布レポートでは、ジッターやパケット損失などの QoE (Quality of Experience) 指標の分布値を示すグラフを確認することができます。たとえば、ユーザーが合計で 10 回の通話を行い、この 10 回の通話から以下のようなラウンドトリップ時間が報告されたとします。</span><span class="sxs-lookup"><span data-stu-id="133ce-p101">The Media Quality Metrics Distribution Report enables you to see a graph that shows the distribution values for a Quality of Experience metric such as jitter or packet loss. For example, suppose your users make a total of 10 phone calls; those 10 calls report the following roundtrip times:</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="133ce-106">通話番号</span><span class="sxs-lookup"><span data-stu-id="133ce-106">Call Number</span></span></th>
<th><span data-ttu-id="133ce-107">往復時間 (ミリ秒)</span><span class="sxs-lookup"><span data-stu-id="133ce-107">Roundtrip Time (milliseconds)</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="133ce-108">1</span><span class="sxs-lookup"><span data-stu-id="133ce-108">1</span></span></p></td>
<td><p><span data-ttu-id="133ce-109">50</span><span class="sxs-lookup"><span data-stu-id="133ce-109">50</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="133ce-110">2</span><span class="sxs-lookup"><span data-stu-id="133ce-110">2</span></span></p></td>
<td><p><span data-ttu-id="133ce-111">50</span><span class="sxs-lookup"><span data-stu-id="133ce-111">50</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="133ce-112">3</span><span class="sxs-lookup"><span data-stu-id="133ce-112">3</span></span></p></td>
<td><p><span data-ttu-id="133ce-113">50</span><span class="sxs-lookup"><span data-stu-id="133ce-113">50</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="133ce-114">4</span><span class="sxs-lookup"><span data-stu-id="133ce-114">4</span></span></p></td>
<td><p><span data-ttu-id="133ce-115">50</span><span class="sxs-lookup"><span data-stu-id="133ce-115">50</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="133ce-116">5</span><span class="sxs-lookup"><span data-stu-id="133ce-116">5</span></span></p></td>
<td><p><span data-ttu-id="133ce-117">50</span><span class="sxs-lookup"><span data-stu-id="133ce-117">50</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="133ce-118">6</span><span class="sxs-lookup"><span data-stu-id="133ce-118">6</span></span></p></td>
<td><p><span data-ttu-id="133ce-119">50</span><span class="sxs-lookup"><span data-stu-id="133ce-119">50</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="133ce-120">7</span><span class="sxs-lookup"><span data-stu-id="133ce-120">7</span></span></p></td>
<td><p><span data-ttu-id="133ce-121">50</span><span class="sxs-lookup"><span data-stu-id="133ce-121">50</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="133ce-122">個</span><span class="sxs-lookup"><span data-stu-id="133ce-122">8</span></span></p></td>
<td><p><span data-ttu-id="133ce-123">4550</span><span class="sxs-lookup"><span data-stu-id="133ce-123">4550</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="133ce-124">ファイブ</span><span class="sxs-lookup"><span data-stu-id="133ce-124">9</span></span></p></td>
<td><p><span data-ttu-id="133ce-125">50</span><span class="sxs-lookup"><span data-stu-id="133ce-125">50</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="133ce-126">常用</span><span class="sxs-lookup"><span data-stu-id="133ce-126">10</span></span></p></td>
<td><p><span data-ttu-id="133ce-127">50</span><span class="sxs-lookup"><span data-stu-id="133ce-127">50</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="133ce-128">これらのラウンドトリップ時間の平均は500ミリ秒 (5000 は10で割る) です。</span><span class="sxs-lookup"><span data-stu-id="133ce-128">The average for those roundtrip times is 500 milliseconds (5000 divided by 10).</span></span> <span data-ttu-id="133ce-129">500ミリ秒は非常に大きなラウンドトリップ時間です。その結果、ネットワークの輻輳に対して重大な問題が発生したと判断される可能性があります。</span><span class="sxs-lookup"><span data-stu-id="133ce-129">Five hundred milliseconds is an extremely large roundtrip time; as a result, you might believe that you have a serious problem with network congestion.</span></span> <span data-ttu-id="133ce-130">(ラウンドトリップ時間が長い場合は、通常、ネットワークの過負荷が発生します)。</span><span class="sxs-lookup"><span data-stu-id="133ce-130">(Long roundtrip times are typically the result of overloaded networks.)</span></span>

<span data-ttu-id="133ce-131">実際には、通話の 90% は、非常に優れた往復時間でした。結果全体に対して1つの不正な通話があっただけです。</span><span class="sxs-lookup"><span data-stu-id="133ce-131">In reality, of course, 90% of your calls had excellent round trip times; you merely had one bad call that skewed the overall results.</span></span> <span data-ttu-id="133ce-132">平均ラウンドトリップ時間のみを表示する場合は、問題が発生する可能性が高くなります。</span><span class="sxs-lookup"><span data-stu-id="133ce-132">If you only look at the average roundtrip time you might jump to a very wrong conclusion.</span></span>

<span data-ttu-id="133ce-p104">メディア品質メトリック分布レポートでは、特定の指標 (ラウンドトリップ時間など) の分布をグラフィカルに表示することによって誤った結論に至るのを防ぎます。このようなグラフでは、9 回の通話はとても良好で、1 回の通話だけが良くなかったという事実がはっきりとわかります。当然ながら、その 1 回の通話についてはさらなる調査が必要ですが、10 回のうち 9 回がとても良好だったという結果は、少なくとも現時点では、ネットワークを大きく変更する理由はないことを示唆しています。</span><span class="sxs-lookup"><span data-stu-id="133ce-p104">The Media Quality Metrics Distribution Report helps you avoid jumping to wrong conclusions by showing you a graphical distribution of a specified metric (such as round trip time). These graphs can help make it clear that you had nine very good calls and one very bad call. Admittedly, you might still want to further investigate that one call; however, the fact that 9 out of the 10 calls were very good suggests that there is no reason to make any drastic changes to your network, at least not at this point in time.</span></span>

<div>

## <a name="filters"></a><span data-ttu-id="133ce-136">フィルター</span><span class="sxs-lookup"><span data-stu-id="133ce-136">Filters</span></span>

<span data-ttu-id="133ce-p105">フィルターは、細かく絞り込んだデータ セットを返したり、返されたデータをさまざまな方法で表示したりする方法として利用できます。次の表に、メディア品質メトリック分布レポートで使用できるフィルターを示します。</span><span class="sxs-lookup"><span data-stu-id="133ce-p105">Filters provide a way for you to return a more finely-targeted set of data or to view the returned data in different ways. The following table lists the filters that you can use with the Media Quality Metrics Distribution Report.</span></span>

### <a name="media-quality-metrics-distribution-report-filters"></a><span data-ttu-id="133ce-139">メディア品質メトリック分布レポートのフィルター</span><span class="sxs-lookup"><span data-stu-id="133ce-139">Media Quality Metrics Distribution Report Filters</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="133ce-140">名前</span><span class="sxs-lookup"><span data-stu-id="133ce-140">Name</span></span></th>
<th><span data-ttu-id="133ce-141">説明</span><span class="sxs-lookup"><span data-stu-id="133ce-141">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="133ce-142"><strong>開始</strong></span><span class="sxs-lookup"><span data-stu-id="133ce-142"><strong>From</strong></span></span></p></td>
<td><p><span data-ttu-id="133ce-p106">時間範囲の開始日と開始時刻。データを時間単位で表示するには、次のように開始日と開始時刻の両方を入力します。</span><span class="sxs-lookup"><span data-stu-id="133ce-p106">Start date/time for the time range. To view data by hours, enter both the start date and time as follows:</span></span></p>
<p><span data-ttu-id="133ce-145">7/7/2012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="133ce-145">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="133ce-p107">開始時刻を入力しないと、レポートは自動的に指定日の午前 12:00 に開始します。データを日単位で表示するには、次のように日付のみを入力します。</span><span class="sxs-lookup"><span data-stu-id="133ce-p107">If you do not enter a start time, the report automatically begins at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="133ce-148">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="133ce-148">7/7/2012</span></span></p>
<p><span data-ttu-id="133ce-149">週単位または月単位で表示するには、表示する週または月の任意の日付を入力します (その週または月の最初の日である必要はありません)。</span><span class="sxs-lookup"><span data-stu-id="133ce-149">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="133ce-150">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="133ce-150">7/3/2012</span></span></p>
<p><span data-ttu-id="133ce-151">一週間は、日曜日から始まり、土曜日で終わるものとします。</span><span class="sxs-lookup"><span data-stu-id="133ce-151">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="133ce-152"><strong>終了</strong></span><span class="sxs-lookup"><span data-stu-id="133ce-152"><strong>To</strong></span></span></p></td>
<td><p><span data-ttu-id="133ce-p108">時間範囲の終了日と終了時刻。データを時間単位で表示するには、次のように終了日と終了時刻の両方を入力します。</span><span class="sxs-lookup"><span data-stu-id="133ce-p108">End date/time for the time range. To view data by hours, enter both the end date and time as follows:</span></span></p>
<p><span data-ttu-id="133ce-155">7/7/2012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="133ce-155">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="133ce-p109">終了時刻を入力しないと、レポートは自動的に指定日の午前 12:00 に終了します。データを日単位で表示するには、次のように日付のみを入力します。</span><span class="sxs-lookup"><span data-stu-id="133ce-p109">If you do not enter an end time, the report automatically ends at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="133ce-158">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="133ce-158">7/7/2012</span></span></p>
<p><span data-ttu-id="133ce-159">週単位または月単位で表示するには、表示する週または月の任意の日付を入力します (その週または月の最初の日である必要はありません)。</span><span class="sxs-lookup"><span data-stu-id="133ce-159">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="133ce-160">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="133ce-160">7/3/2012</span></span></p>
<p><span data-ttu-id="133ce-161">一週間は、日曜日から始まり、土曜日で終わるものとします。</span><span class="sxs-lookup"><span data-stu-id="133ce-161">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="133ce-162"><strong>x 軸の最小値</strong></span><span class="sxs-lookup"><span data-stu-id="133ce-162"><strong>Minimum in x axis</strong></span></span></p></td>
<td><p><span data-ttu-id="133ce-163">グラフの X 軸に表示される最小の値。</span><span class="sxs-lookup"><span data-stu-id="133ce-163">Lowest value to be displayed on the X axis of the graph.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="133ce-164"><strong>x 軸の最大値</strong></span><span class="sxs-lookup"><span data-stu-id="133ce-164"><strong>Maximum in x axis</strong></span></span></p></td>
<td><p><span data-ttu-id="133ce-165">グラフの X 軸に表示される最大の値。</span><span class="sxs-lookup"><span data-stu-id="133ce-165">Highest value to be displayed on the X axis of the graph.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="133ce-166"><strong>アクセスの種類</strong></span><span class="sxs-lookup"><span data-stu-id="133ce-166"><strong>Access type</strong></span></span></p></td>
<td><p><span data-ttu-id="133ce-p110">クライアントが通話時に内部ネットワークにログオンしたか、外部ネットワークにログオンしたかを示します。次のいずれかを選択します。</span><span class="sxs-lookup"><span data-stu-id="133ce-p110">Indicates whether the client was logged on to the internal network or the external network when the call was placed. Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="133ce-169">[すべて]</span><span class="sxs-lookup"><span data-stu-id="133ce-169">[All]</span></span></p></li>
<li><p><span data-ttu-id="133ce-170">内部</span><span class="sxs-lookup"><span data-stu-id="133ce-170">Internal</span></span></p></li>
<li><p><span data-ttu-id="133ce-171">外部</span><span class="sxs-lookup"><span data-stu-id="133ce-171">External</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="133ce-172"><strong>VPN</strong></span><span class="sxs-lookup"><span data-stu-id="133ce-172"><strong>VPN</strong></span></span></p></td>
<td><p><span data-ttu-id="133ce-p111">通話時に外部クライアントが仮想プライベート ネットワーク (VPN) 接続を使用したかどうかを示します。次のいずれかを選択します。</span><span class="sxs-lookup"><span data-stu-id="133ce-p111">Indicates whether an external client was using a virtual private network (VPN) connection when the call was placed. Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="133ce-175">[すべて]</span><span class="sxs-lookup"><span data-stu-id="133ce-175">[All]</span></span></p></li>
<li><p><span data-ttu-id="133ce-176">VPN</span><span class="sxs-lookup"><span data-stu-id="133ce-176">VPN</span></span></p></li>
<li><p><span data-ttu-id="133ce-177">非 VPN</span><span class="sxs-lookup"><span data-stu-id="133ce-177">Non-VPN</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="133ce-178"><strong>ネットワークの種類</strong></span><span class="sxs-lookup"><span data-stu-id="133ce-178"><strong>Network type</strong></span></span></p></td>
<td><p><span data-ttu-id="133ce-p112">通話時にクライアントが接続したネットワークの種類を示します。次のいずれかを選択します。</span><span class="sxs-lookup"><span data-stu-id="133ce-p112">Indicates the type of network the client was connected to when the call was placed. Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="133ce-181">[すべて]</span><span class="sxs-lookup"><span data-stu-id="133ce-181">[All]</span></span></p></li>
<li><p><span data-ttu-id="133ce-182">有線</span><span class="sxs-lookup"><span data-stu-id="133ce-182">Wired</span></span></p></li>
<li><p><span data-ttu-id="133ce-183">ワイヤレス</span><span class="sxs-lookup"><span data-stu-id="133ce-183">Wireless</span></span></p></li>
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

