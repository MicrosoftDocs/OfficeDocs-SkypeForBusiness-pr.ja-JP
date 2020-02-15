---
title: 'Lync Server 2013: P2P Summary サブレポート'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: P2P Summary Subreport
ms:assetid: fc36185a-3cc5-4167-8c93-8a755fa75ac7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205416(v=OCS.15)
ms:contentKeyID: 48185950
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 47da588037fd3db70fc277c91b919185f48a9286
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/14/2020
ms.locfileid: "41989732"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="p2p-summary-subreport-in-lync-server-2013"></a><span data-ttu-id="91bbd-102">Lync Server 2013 の P2P 概要サブレポート</span><span class="sxs-lookup"><span data-stu-id="91bbd-102">P2P Summary Subreport in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="91bbd-103">_**トピックの最終更新日:** 2012-10-21_</span><span class="sxs-lookup"><span data-stu-id="91bbd-103">_**Topic Last Modified:** 2012-10-21_</span></span>

<span data-ttu-id="91bbd-104">P2P 概要サブレポートは、エラーが発生したピアツーピア セッションの総合的な概要を示します。</span><span class="sxs-lookup"><span data-stu-id="91bbd-104">The P2P Summary Subreport provides an overall view of your failed peer-to-peer communication sessions.</span></span>

<div>

## <a name="filters"></a><span data-ttu-id="91bbd-105">フィルター</span><span class="sxs-lookup"><span data-stu-id="91bbd-105">Filters</span></span>

<span data-ttu-id="91bbd-p101">フィルターは、細かく絞り込んだデータ セットを返したり、返されたデータをさまざま方法で表示したりする方法として利用できます。次の表に、P2P 概要サブレポートで使用できるフィルターを示します。</span><span class="sxs-lookup"><span data-stu-id="91bbd-p101">Filters provide a way for you to return a more finely targeted set of data or to view the returned data in different ways. The following table lists the filters that you can use with the P2P Summary Subreport.</span></span>

### <a name="p2p-summary-subreport-filters"></a><span data-ttu-id="91bbd-108">P2P 概要サブレポートのフィルター</span><span class="sxs-lookup"><span data-stu-id="91bbd-108">P2P Summary Subreport Filters</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="91bbd-109">名前</span><span class="sxs-lookup"><span data-stu-id="91bbd-109">Name</span></span></th>
<th><span data-ttu-id="91bbd-110">説明</span><span class="sxs-lookup"><span data-stu-id="91bbd-110">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="91bbd-111"><strong>From</strong></span><span class="sxs-lookup"><span data-stu-id="91bbd-111"><strong>From</strong></span></span></p></td>
<td><p><span data-ttu-id="91bbd-p102">時間範囲の開始日と開始時刻。データを時間単位で表示するには、次のように開始日と開始時刻の両方を入力します。</span><span class="sxs-lookup"><span data-stu-id="91bbd-p102">Start date and time for the time range. To view data by hours, enter both the start date and time as follows:</span></span></p>
<p><span data-ttu-id="91bbd-114">7/7/2012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="91bbd-114">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="91bbd-p103">開始時刻を入力しないと、レポートは自動的に指定日の午前 12:00 に開始します。データを日単位で表示するには、次のように日付のみを入力します。</span><span class="sxs-lookup"><span data-stu-id="91bbd-p103">If you do not enter a start time, the report automatically begins at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="91bbd-117">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="91bbd-117">7/7/2012</span></span></p>
<p><span data-ttu-id="91bbd-118">週単位または月単位で表示するには、表示する週または月の任意の日付を入力します (その週または月の最初の日である必要はありません)。</span><span class="sxs-lookup"><span data-stu-id="91bbd-118">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="91bbd-119">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="91bbd-119">7/3/2012</span></span></p>
<p><span data-ttu-id="91bbd-120">週は、常に日曜日から土曜日までです。</span><span class="sxs-lookup"><span data-stu-id="91bbd-120">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="91bbd-121"><strong>To</strong></span><span class="sxs-lookup"><span data-stu-id="91bbd-121"><strong>To</strong></span></span></p></td>
<td><p><span data-ttu-id="91bbd-p104">時間範囲の終了日と終了時刻。データを時間単位で表示するには、次のように終了日と終了時刻の両方を入力します。</span><span class="sxs-lookup"><span data-stu-id="91bbd-p104">End date and time for the time range. To view data by hours, enter both the end date and time as follows:</span></span></p>
<p><span data-ttu-id="91bbd-124">7/7/2012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="91bbd-124">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="91bbd-p105">終了時刻を入力しないと、レポートは自動的に指定日の午前 12:00 に終了します。データを日単位で表示するには、次のように日付のみを入力します。</span><span class="sxs-lookup"><span data-stu-id="91bbd-p105">If you do not enter an end time, the report automatically ends at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="91bbd-127">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="91bbd-127">7/7/2012</span></span></p>
<p><span data-ttu-id="91bbd-128">週単位または月単位で表示するには、表示する週または月の任意の日付を入力します (その週または月の最初の日である必要はありません)。</span><span class="sxs-lookup"><span data-stu-id="91bbd-128">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="91bbd-129">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="91bbd-129">7/3/2012</span></span></p>
<p><span data-ttu-id="91bbd-130">週は、常に日曜日から土曜日までです。</span><span class="sxs-lookup"><span data-stu-id="91bbd-130">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="91bbd-131"><strong>Pool</strong></span><span class="sxs-lookup"><span data-stu-id="91bbd-131"><strong>Pool</strong></span></span></p></td>
<td><p><span data-ttu-id="91bbd-p106">レジストラー プールまたはエッジ サーバーの完全修飾ドメイン名 (FQDN)。個別のプールを選択するか、[<strong>すべて</strong>] をクリックしてすべてのプールのデータを表示できます。このドロップダウン リストは、データベース内のレコードに基づいて自動的に設定されます。</span><span class="sxs-lookup"><span data-stu-id="91bbd-p106">Fully qualified domain name (FQDN) of the Registrar pool or Edge Server. You can either select an individual pool or click <strong>[All]</strong> to view data for all the pools. This drop-down list is automatically populated for you based on the records in the database.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics"></a><span data-ttu-id="91bbd-135">指標</span><span class="sxs-lookup"><span data-stu-id="91bbd-135">Metrics</span></span>

<span data-ttu-id="91bbd-136">次の表に、P2P 概要サブレポートで提供される情報を示します。</span><span class="sxs-lookup"><span data-stu-id="91bbd-136">The following table lists the information provided in the P2P Summary Subreport.</span></span>

### <a name="p2p-summary-subreport-metrics"></a><span data-ttu-id="91bbd-137">P2P 概要サブレポートの指標</span><span class="sxs-lookup"><span data-stu-id="91bbd-137">P2P Summary Subreport Metrics</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="91bbd-138">名前</span><span class="sxs-lookup"><span data-stu-id="91bbd-138">Name</span></span></th>
<th><span data-ttu-id="91bbd-139">この項目での並べ替え</span><span class="sxs-lookup"><span data-stu-id="91bbd-139">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="91bbd-140">説明</span><span class="sxs-lookup"><span data-stu-id="91bbd-140">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="91bbd-141">[<strong>セッションの合計数</strong>]</span><span class="sxs-lookup"><span data-stu-id="91bbd-141"><strong>Total sessions</strong></span></span></p></td>
<td><p><span data-ttu-id="91bbd-142">いいえ</span><span class="sxs-lookup"><span data-stu-id="91bbd-142">No</span></span></p></td>
<td><p><span data-ttu-id="91bbd-143">セッションの総数です。成功したセッション、失敗したセッション (予期されるエラーと予期しないエラーの両方)、およびどちらにも分類されないセッションを含みます。</span><span class="sxs-lookup"><span data-stu-id="91bbd-143">Total number of sessions, including successful sessions, failed sessions (both expected failures and unexpected failures), and uncategorized sessions.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="91bbd-144">[<strong>エラー率</strong>]</span><span class="sxs-lookup"><span data-stu-id="91bbd-144"><strong>Failure rate</strong></span></span></p></td>
<td><p><span data-ttu-id="91bbd-145">いいえ</span><span class="sxs-lookup"><span data-stu-id="91bbd-145">No</span></span></p></td>
<td><p><span data-ttu-id="91bbd-146">エラーが発生したピアツーピア セッションの割合です。</span><span class="sxs-lookup"><span data-stu-id="91bbd-146">Percentage of peer-to-peer sessions that failed.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="91bbd-147">[<strong>モダリティ別セッション</strong>]</span><span class="sxs-lookup"><span data-stu-id="91bbd-147"><strong>Sessions by Modality</strong></span></span></p></td>
<td><p><span data-ttu-id="91bbd-148">いいえ</span><span class="sxs-lookup"><span data-stu-id="91bbd-148">No</span></span></p></td>
<td><p><span data-ttu-id="91bbd-149">モダリティによってグループ化されたセッションの合計数 (たとえば、インスタント メッセージング)。</span><span class="sxs-lookup"><span data-stu-id="91bbd-149">Total number of sessions grouped by modality (for example, instant messaging).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="91bbd-150">[<strong>モダリティ別エラー率</strong>]</span><span class="sxs-lookup"><span data-stu-id="91bbd-150"><strong>Failure rate by modality</strong></span></span></p></td>
<td><p><span data-ttu-id="91bbd-151">いいえ</span><span class="sxs-lookup"><span data-stu-id="91bbd-151">No</span></span></p></td>
<td><p><span data-ttu-id="91bbd-152">モダリティによってグループ化された失敗したセッションの合計数 (たとえば、インスタント メッセージング)。</span><span class="sxs-lookup"><span data-stu-id="91bbd-152">Total number of failed sessions grouped by modality (for example, instant messaging).</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

