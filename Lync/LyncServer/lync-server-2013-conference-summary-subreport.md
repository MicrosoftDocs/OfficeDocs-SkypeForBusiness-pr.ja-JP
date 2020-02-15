---
title: 'Lync Server 2013: 電話会議の概要サブレポート'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Conference Summary Subreport
ms:assetid: 2fc1d2bf-34f5-4093-a6e2-250ec1f1b004
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204779(v=OCS.15)
ms:contentKeyID: 48183742
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d2c31c614298112b91874882df1e4945845b74bd
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2020
ms.locfileid: "42046320"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="conference-summary-subreport-in-lync-server-2013"></a><span data-ttu-id="eceb4-102">Lync Server 2013 の電話会議の概要サブレポート</span><span class="sxs-lookup"><span data-stu-id="eceb4-102">Conference Summary Subreport in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="eceb4-103">_**トピックの最終更新日:** 2012-06-06_</span><span class="sxs-lookup"><span data-stu-id="eceb4-103">_**Topic Last Modified:** 2012-06-06_</span></span>

<span data-ttu-id="eceb4-p101">電話会議の概要サブレポートには、エラーが発生した電話会議セッションの概要が表示されます。これらのエラーが発生したセッションは、フォーカス セッションと MCU セッションというセッションの種類によって分類されます。</span><span class="sxs-lookup"><span data-stu-id="eceb4-p101">The Conference Summary Subreport provides an overall view of failed conference sessions. These failed sessions are further broken down by session type: Focus sessions and MCU sessions.</span></span>

<div>

## <a name="filters"></a><span data-ttu-id="eceb4-106">フィルター</span><span class="sxs-lookup"><span data-stu-id="eceb4-106">Filters</span></span>

<span data-ttu-id="eceb4-p102">フィルターは、細かく絞り込んだデータ セットを返したり、返されたデータをさまざま方法で表示したりする方法として利用できます。次の表に、電話会議の概要サブレポートで使用できるフィルターを示します。</span><span class="sxs-lookup"><span data-stu-id="eceb4-p102">Filters provide a way for you to return a more finely-targeted set of data or to view the returned data in different ways. The following table lists the filters that you can use with the Conference Summary Subreport.</span></span>

### <a name="conference-summary-subreport-filters"></a><span data-ttu-id="eceb4-109">電話会議の概要サブレポートのフィルター</span><span class="sxs-lookup"><span data-stu-id="eceb4-109">Conference Summary Subreport Filters</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="eceb4-110">名前</span><span class="sxs-lookup"><span data-stu-id="eceb4-110">Name</span></span></th>
<th><span data-ttu-id="eceb4-111">説明</span><span class="sxs-lookup"><span data-stu-id="eceb4-111">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="eceb4-112"><strong>From</strong></span><span class="sxs-lookup"><span data-stu-id="eceb4-112"><strong>From</strong></span></span></p></td>
<td><p><span data-ttu-id="eceb4-p103">時間範囲の開始日と開始時刻。データを時間単位で表示するには、次のように開始日と開始時刻の両方を入力します。</span><span class="sxs-lookup"><span data-stu-id="eceb4-p103">Start date/time for the time range. To view data by hours, enter both the start date and time as follows:</span></span></p>
<p><span data-ttu-id="eceb4-115">7/7/2012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="eceb4-115">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="eceb4-p104">開始時刻を入力しないと、レポートは自動的に指定日の午前 12:00 に開始します。データを日単位で表示するには、次のように日付のみを入力します。</span><span class="sxs-lookup"><span data-stu-id="eceb4-p104">If you do not enter a start time, the report automatically begins at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="eceb4-118">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="eceb4-118">7/7/2012</span></span></p>
<p><span data-ttu-id="eceb4-119">週単位または月単位で表示するには、表示する週または月の任意の日付を入力します (その週または月の最初の日である必要はありません)。</span><span class="sxs-lookup"><span data-stu-id="eceb4-119">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="eceb4-120">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="eceb4-120">7/3/2012</span></span></p>
<p><span data-ttu-id="eceb4-121">週は、常に日曜日から土曜日までです。</span><span class="sxs-lookup"><span data-stu-id="eceb4-121">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="eceb4-122"><strong>To</strong></span><span class="sxs-lookup"><span data-stu-id="eceb4-122"><strong>To</strong></span></span></p></td>
<td><p><span data-ttu-id="eceb4-p105">時間範囲の終了日と終了時刻。データを時間単位で表示するには、次のように終了日と終了時刻の両方を入力します。</span><span class="sxs-lookup"><span data-stu-id="eceb4-p105">End date/time for the time range. To view data by hours, enter both the end date and time as follows:</span></span></p>
<p><span data-ttu-id="eceb4-125">7/7/2012 13:00</span><span class="sxs-lookup"><span data-stu-id="eceb4-125">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="eceb4-p106">終了時刻を入力しないと、レポートは自動的に指定日の午前 12:00 に終了します。データを日単位で表示するには、次のように日付のみを入力します。</span><span class="sxs-lookup"><span data-stu-id="eceb4-p106">If you do not enter an end time, the report automatically ends at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="eceb4-128">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="eceb4-128">7/7/2012</span></span></p>
<p><span data-ttu-id="eceb4-129">週単位または月単位で表示するには、表示する週または月の任意の日付を入力します (その週または月の最初の日である必要はありません)。</span><span class="sxs-lookup"><span data-stu-id="eceb4-129">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="eceb4-130">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="eceb4-130">7/3/2012</span></span></p>
<p><span data-ttu-id="eceb4-131">週は、常に日曜日から土曜日までです。</span><span class="sxs-lookup"><span data-stu-id="eceb4-131">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="eceb4-132"><strong>Pool</strong></span><span class="sxs-lookup"><span data-stu-id="eceb4-132"><strong>Pool</strong></span></span></p></td>
<td><p><span data-ttu-id="eceb4-p107">レジストラー プールまたはエッジ サーバーの完全修飾ドメイン名 (FQDN)。個別のプールを選択するか、[<strong>すべて</strong>] をクリックしてすべてのプールのデータを表示できます。このドロップダウン リストは、データベース内のレコードに基づいて自動的に設定されます。</span><span class="sxs-lookup"><span data-stu-id="eceb4-p107">Fully qualified domain name (FQDN) of the Registrar pool or Edge Server. You can either select an individual pool or click <strong>[All]</strong> to view data for all the pools. This drop-down list is automatically populated for you based on the records in the database.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics"></a><span data-ttu-id="eceb4-136">指標</span><span class="sxs-lookup"><span data-stu-id="eceb4-136">Metrics</span></span>

<span data-ttu-id="eceb4-137">次の表に、電話会議の概要サブレポートに表示される情報を示します。</span><span class="sxs-lookup"><span data-stu-id="eceb4-137">The following table lists the information provided in the Conference Summary Subreport.</span></span>

### <a name="conference-summary-subreport-metrics"></a><span data-ttu-id="eceb4-138">電話会議の概要サブレポートの指標</span><span class="sxs-lookup"><span data-stu-id="eceb4-138">Conference Summary Subreport Metrics</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="eceb4-139">名前</span><span class="sxs-lookup"><span data-stu-id="eceb4-139">Name</span></span></th>
<th><span data-ttu-id="eceb4-140">この項目での並べ替え</span><span class="sxs-lookup"><span data-stu-id="eceb4-140">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="eceb4-141">説明</span><span class="sxs-lookup"><span data-stu-id="eceb4-141">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="eceb4-142">[<strong>電話会議の合計数</strong>]</span><span class="sxs-lookup"><span data-stu-id="eceb4-142"><strong>Total conferences</strong></span></span></p></td>
<td><p><span data-ttu-id="eceb4-143">いいえ</span><span class="sxs-lookup"><span data-stu-id="eceb4-143">No</span></span></p></td>
<td><p><span data-ttu-id="eceb4-144">開催された電話会議の合計数です。</span><span class="sxs-lookup"><span data-stu-id="eceb4-144">Total number of conferences held.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="eceb4-145">[<strong>電話会議セッションの合計数</strong>]</span><span class="sxs-lookup"><span data-stu-id="eceb4-145"><strong>Total conference sessions</strong></span></span></p></td>
<td><p><span data-ttu-id="eceb4-146">いいえ</span><span class="sxs-lookup"><span data-stu-id="eceb4-146">No</span></span></p></td>
<td><p><span data-ttu-id="eceb4-p108">電話会議セッションの合計数です。1 つの電話会議に複数のセッションが存在する場合があります。たとえば、1 つの電話会議にフォーカス セッションと MCU セッションの両方が含まれる場合があります。</span><span class="sxs-lookup"><span data-stu-id="eceb4-p108">Total number of conference sessions. A single conference can have multiple sessions; for example, a conference might include both a Focus session and an MCU session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="eceb4-149">[<strong>全体的なセッション エラー率</strong>]</span><span class="sxs-lookup"><span data-stu-id="eceb4-149"><strong>Overall session failure rate</strong></span></span></p></td>
<td><p><span data-ttu-id="eceb4-150">いいえ</span><span class="sxs-lookup"><span data-stu-id="eceb4-150">No</span></span></p></td>
<td><p><span data-ttu-id="eceb4-151">エラーが発生したすべての電話会議の割合です。</span><span class="sxs-lookup"><span data-stu-id="eceb4-151">Percentage of all conferences that failed.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="eceb4-152">[<strong>フォーカス セッション</strong>]</span><span class="sxs-lookup"><span data-stu-id="eceb4-152"><strong>Focus sessions</strong></span></span></p></td>
<td><p><span data-ttu-id="eceb4-153">いいえ</span><span class="sxs-lookup"><span data-stu-id="eceb4-153">No</span></span></p></td>
<td><p><span data-ttu-id="eceb4-154">フォーカス セッションの合計数です。</span><span class="sxs-lookup"><span data-stu-id="eceb4-154">Total number of Focus sessions.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="eceb4-155">[<strong>フォーカス エラー率</strong>]</span><span class="sxs-lookup"><span data-stu-id="eceb4-155"><strong>Focus failure rate</strong></span></span></p></td>
<td><p><span data-ttu-id="eceb4-156">いいえ</span><span class="sxs-lookup"><span data-stu-id="eceb4-156">No</span></span></p></td>
<td><p><span data-ttu-id="eceb4-157">エラーが発生したフォーカス セッションの割合です。</span><span class="sxs-lookup"><span data-stu-id="eceb4-157">Percentage of Focus sessions that failed.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="eceb4-158">[MCU セッション]</span><span class="sxs-lookup"><span data-stu-id="eceb4-158">MCU sessions</span></span></p></td>
<td><p><span data-ttu-id="eceb4-159">いいえ</span><span class="sxs-lookup"><span data-stu-id="eceb4-159">No</span></span></p></td>
<td><p><span data-ttu-id="eceb4-160">MCU セッションの合計数です。</span><span class="sxs-lookup"><span data-stu-id="eceb4-160">Total number of MCU sessions.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="eceb4-161">[<strong>MCU エラー率</strong>]</span><span class="sxs-lookup"><span data-stu-id="eceb4-161"><strong>MCU failure rate</strong></span></span></p></td>
<td><p><span data-ttu-id="eceb4-162">いいえ</span><span class="sxs-lookup"><span data-stu-id="eceb4-162">No</span></span></p></td>
<td><p><span data-ttu-id="eceb4-163">エラーが発生した MCU セッションの割合です。</span><span class="sxs-lookup"><span data-stu-id="eceb4-163">Percentage of MCU sessions that failed.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="eceb4-164">[<strong>MCU セッション (モダリティ別)</strong>]</span><span class="sxs-lookup"><span data-stu-id="eceb4-164"><strong>MCU sessions by modality</strong></span></span></p></td>
<td><p><span data-ttu-id="eceb4-165">いいえ</span><span class="sxs-lookup"><span data-stu-id="eceb4-165">No</span></span></p></td>
<td><p><span data-ttu-id="eceb4-166">モダリティ (IM 電話会議など) ごとにグループ化した、MCU セッションの合計数です。</span><span class="sxs-lookup"><span data-stu-id="eceb4-166">Total number of MCU sessions, grouped by modality (for example, IM conferencing).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="eceb4-167">[<strong>エラー率 (モダリティ別)</strong>]</span><span class="sxs-lookup"><span data-stu-id="eceb4-167"><strong>Failure rate by modality</strong></span></span></p></td>
<td><p><span data-ttu-id="eceb4-168">いいえ</span><span class="sxs-lookup"><span data-stu-id="eceb4-168">No</span></span></p></td>
<td><p><span data-ttu-id="eceb4-169">モダリティ (IM 電話会議など) ごとにグループ化した、エラーが発生した MCU セッションの割合です。</span><span class="sxs-lookup"><span data-stu-id="eceb4-169">Percentage of MCU sessions that failed, grouped by modality (for example, IM conferencing).</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

