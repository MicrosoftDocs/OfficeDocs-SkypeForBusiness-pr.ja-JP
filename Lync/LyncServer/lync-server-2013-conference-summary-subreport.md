---
title: 'Lync Server 2013: 会議の概要サブレポート'
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
ms.openlocfilehash: 2537cbe959639baee6f0f986b3faea1ebd79b5a8
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41756991"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="conference-summary-subreport-in-lync-server-2013"></a><span data-ttu-id="8101d-102">Lync Server 2013 の会議の概要サブレポート</span><span class="sxs-lookup"><span data-stu-id="8101d-102">Conference Summary Subreport in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8101d-103">_**最終更新日:** 2012-06-06_</span><span class="sxs-lookup"><span data-stu-id="8101d-103">_**Topic Last Modified:** 2012-06-06_</span></span>

<span data-ttu-id="8101d-p101">電話会議の概要サブレポートには、エラーが発生した電話会議セッションの概要が表示されます。これらのエラーが発生したセッションは、フォーカス セッションと MCU セッションというセッションの種類によって分類されます。</span><span class="sxs-lookup"><span data-stu-id="8101d-p101">The Conference Summary Subreport provides an overall view of failed conference sessions. These failed sessions are further broken down by session type: Focus sessions and MCU sessions.</span></span>

<div>

## <a name="filters"></a><span data-ttu-id="8101d-106">フィルター</span><span class="sxs-lookup"><span data-stu-id="8101d-106">Filters</span></span>

<span data-ttu-id="8101d-p102">フィルターは、細かく絞り込んだデータ セットを返したり、返されたデータをさまざまな方法で表示したりする方法として利用できます。次の表に、電話会議の概要サブレポートで使用できるフィルターを示します。</span><span class="sxs-lookup"><span data-stu-id="8101d-p102">Filters provide a way for you to return a more finely-targeted set of data or to view the returned data in different ways. The following table lists the filters that you can use with the Conference Summary Subreport.</span></span>

### <a name="conference-summary-subreport-filters"></a><span data-ttu-id="8101d-109">電話会議の概要サブレポートのフィルター</span><span class="sxs-lookup"><span data-stu-id="8101d-109">Conference Summary Subreport Filters</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="8101d-110">名前</span><span class="sxs-lookup"><span data-stu-id="8101d-110">Name</span></span></th>
<th><span data-ttu-id="8101d-111">説明</span><span class="sxs-lookup"><span data-stu-id="8101d-111">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="8101d-112"><strong>開始</strong></span><span class="sxs-lookup"><span data-stu-id="8101d-112"><strong>From</strong></span></span></p></td>
<td><p><span data-ttu-id="8101d-p103">時間範囲の開始日と開始時刻。データを時間単位で表示するには、次のように開始日と開始時刻の両方を入力します。</span><span class="sxs-lookup"><span data-stu-id="8101d-p103">Start date/time for the time range. To view data by hours, enter both the start date and time as follows:</span></span></p>
<p><span data-ttu-id="8101d-115">7/7/2012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="8101d-115">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="8101d-p104">開始時刻を入力しないと、レポートは自動的に指定日の午前 12:00 に開始します。データを日単位で表示するには、次のように日付のみを入力します。</span><span class="sxs-lookup"><span data-stu-id="8101d-p104">If you do not enter a start time, the report automatically begins at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="8101d-118">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="8101d-118">7/7/2012</span></span></p>
<p><span data-ttu-id="8101d-119">週単位または月単位で表示するには、表示する週または月の任意の日付を入力します (その週または月の最初の日である必要はありません)。</span><span class="sxs-lookup"><span data-stu-id="8101d-119">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="8101d-120">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="8101d-120">7/3/2012</span></span></p>
<p><span data-ttu-id="8101d-121">一週間は、日曜日から始まり、土曜日で終わるものとします。</span><span class="sxs-lookup"><span data-stu-id="8101d-121">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8101d-122"><strong>終了</strong></span><span class="sxs-lookup"><span data-stu-id="8101d-122"><strong>To</strong></span></span></p></td>
<td><p><span data-ttu-id="8101d-p105">時間範囲の終了日と終了時刻。データを時間単位で表示するには、次のように終了日と終了時刻の両方を入力します。</span><span class="sxs-lookup"><span data-stu-id="8101d-p105">End date/time for the time range. To view data by hours, enter both the end date and time as follows:</span></span></p>
<p><span data-ttu-id="8101d-125">7/7/2012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="8101d-125">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="8101d-p106">終了時刻を入力しないと、レポートは自動的に指定日の午前 12:00 に終了します。データを日単位で表示するには、次のように日付のみを入力します。</span><span class="sxs-lookup"><span data-stu-id="8101d-p106">If you do not enter an end time, the report automatically ends at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="8101d-128">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="8101d-128">7/7/2012</span></span></p>
<p><span data-ttu-id="8101d-129">週単位または月単位で表示するには、表示する週または月の任意の日付を入力します (その週または月の最初の日である必要はありません)。</span><span class="sxs-lookup"><span data-stu-id="8101d-129">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="8101d-130">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="8101d-130">7/3/2012</span></span></p>
<p><span data-ttu-id="8101d-131">一週間は、日曜日から始まり、土曜日で終わるものとします。</span><span class="sxs-lookup"><span data-stu-id="8101d-131">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8101d-132"><strong>プール</strong></span><span class="sxs-lookup"><span data-stu-id="8101d-132"><strong>Pool</strong></span></span></p></td>
<td><p><span data-ttu-id="8101d-p107">レジストラー プールまたはエッジ サーバーの完全修飾ドメイン名 (FQDN)。個別のプールを選択するか、[<strong>すべて</strong>] をクリックしてすべてのプールのデータを表示できます。このドロップダウン リストは、データベース内のレコードに基づいて自動的に設定されます。</span><span class="sxs-lookup"><span data-stu-id="8101d-p107">Fully qualified domain name (FQDN) of the Registrar pool or Edge Server. You can either select an individual pool or click <strong>[All]</strong> to view data for all the pools. This drop-down list is automatically populated for you based on the records in the database.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics"></a><span data-ttu-id="8101d-136">指標</span><span class="sxs-lookup"><span data-stu-id="8101d-136">Metrics</span></span>

<span data-ttu-id="8101d-137">次の表に、電話会議の概要サブレポートに表示される情報を示します。</span><span class="sxs-lookup"><span data-stu-id="8101d-137">The following table lists the information provided in the Conference Summary Subreport.</span></span>

### <a name="conference-summary-subreport-metrics"></a><span data-ttu-id="8101d-138">電話会議の概要サブレポートの指標</span><span class="sxs-lookup"><span data-stu-id="8101d-138">Conference Summary Subreport Metrics</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="8101d-139">名前</span><span class="sxs-lookup"><span data-stu-id="8101d-139">Name</span></span></th>
<th><span data-ttu-id="8101d-140">この項目での並べ替え</span><span class="sxs-lookup"><span data-stu-id="8101d-140">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="8101d-141">説明</span><span class="sxs-lookup"><span data-stu-id="8101d-141">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="8101d-142"><strong>[電話会議の合計数]</strong></span><span class="sxs-lookup"><span data-stu-id="8101d-142"><strong>Total conferences</strong></span></span></p></td>
<td><p><span data-ttu-id="8101d-143">いいえ</span><span class="sxs-lookup"><span data-stu-id="8101d-143">No</span></span></p></td>
<td><p><span data-ttu-id="8101d-144">開催された電話会議の合計数です。</span><span class="sxs-lookup"><span data-stu-id="8101d-144">Total number of conferences held.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8101d-145"><strong>[電話会議セッションの合計数]</strong></span><span class="sxs-lookup"><span data-stu-id="8101d-145"><strong>Total conference sessions</strong></span></span></p></td>
<td><p><span data-ttu-id="8101d-146">いいえ</span><span class="sxs-lookup"><span data-stu-id="8101d-146">No</span></span></p></td>
<td><p><span data-ttu-id="8101d-p108">電話会議セッションの合計数です。1 つの電話会議に複数のセッションが存在する場合があります。たとえば、1 つの電話会議にフォーカス セッションと MCU セッションの両方が含まれる場合があります。</span><span class="sxs-lookup"><span data-stu-id="8101d-p108">Total number of conference sessions. A single conference can have multiple sessions; for example, a conference might include both a Focus session and an MCU session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8101d-149"><strong>[全体的なセッション エラー率]</strong></span><span class="sxs-lookup"><span data-stu-id="8101d-149"><strong>Overall session failure rate</strong></span></span></p></td>
<td><p><span data-ttu-id="8101d-150">いいえ</span><span class="sxs-lookup"><span data-stu-id="8101d-150">No</span></span></p></td>
<td><p><span data-ttu-id="8101d-151">エラーが発生したすべての電話会議の割合です。</span><span class="sxs-lookup"><span data-stu-id="8101d-151">Percentage of all conferences that failed.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8101d-152"><strong>[フォーカス セッション]</strong></span><span class="sxs-lookup"><span data-stu-id="8101d-152"><strong>Focus sessions</strong></span></span></p></td>
<td><p><span data-ttu-id="8101d-153">いいえ</span><span class="sxs-lookup"><span data-stu-id="8101d-153">No</span></span></p></td>
<td><p><span data-ttu-id="8101d-154">フォーカス セッションの合計数です。</span><span class="sxs-lookup"><span data-stu-id="8101d-154">Total number of Focus sessions.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8101d-155"><strong>[フォーカス エラー率]</strong></span><span class="sxs-lookup"><span data-stu-id="8101d-155"><strong>Focus failure rate</strong></span></span></p></td>
<td><p><span data-ttu-id="8101d-156">いいえ</span><span class="sxs-lookup"><span data-stu-id="8101d-156">No</span></span></p></td>
<td><p><span data-ttu-id="8101d-157">エラーが発生したフォーカス セッションの割合です。</span><span class="sxs-lookup"><span data-stu-id="8101d-157">Percentage of Focus sessions that failed.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8101d-158">[MCU セッション]</span><span class="sxs-lookup"><span data-stu-id="8101d-158">MCU sessions</span></span></p></td>
<td><p><span data-ttu-id="8101d-159">いいえ</span><span class="sxs-lookup"><span data-stu-id="8101d-159">No</span></span></p></td>
<td><p><span data-ttu-id="8101d-160">MCU セッションの合計数です。</span><span class="sxs-lookup"><span data-stu-id="8101d-160">Total number of MCU sessions.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8101d-161"><strong>[MCU エラー率]</strong></span><span class="sxs-lookup"><span data-stu-id="8101d-161"><strong>MCU failure rate</strong></span></span></p></td>
<td><p><span data-ttu-id="8101d-162">いいえ</span><span class="sxs-lookup"><span data-stu-id="8101d-162">No</span></span></p></td>
<td><p><span data-ttu-id="8101d-163">エラーが発生した MCU セッションの割合です。</span><span class="sxs-lookup"><span data-stu-id="8101d-163">Percentage of MCU sessions that failed.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8101d-164"><strong>[MCU セッション (モダリティ別)]</strong></span><span class="sxs-lookup"><span data-stu-id="8101d-164"><strong>MCU sessions by modality</strong></span></span></p></td>
<td><p><span data-ttu-id="8101d-165">いいえ</span><span class="sxs-lookup"><span data-stu-id="8101d-165">No</span></span></p></td>
<td><p><span data-ttu-id="8101d-166">モダリティ (IM 電話会議など) ごとにグループ化した、MCU セッションの合計数です。</span><span class="sxs-lookup"><span data-stu-id="8101d-166">Total number of MCU sessions, grouped by modality (for example, IM conferencing).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8101d-167"><strong>[モダリティ別エラー率]</strong></span><span class="sxs-lookup"><span data-stu-id="8101d-167"><strong>Failure rate by modality</strong></span></span></p></td>
<td><p><span data-ttu-id="8101d-168">不可</span><span class="sxs-lookup"><span data-stu-id="8101d-168">No</span></span></p></td>
<td><p><span data-ttu-id="8101d-169">モダリティ (IM 電話会議など) ごとにグループ化した、エラーが発生した MCU セッションの割合です。</span><span class="sxs-lookup"><span data-stu-id="8101d-169">Percentage of MCU sessions that failed, grouped by modality (for example, IM conferencing).</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

