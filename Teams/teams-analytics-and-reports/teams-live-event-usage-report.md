---
title: Microsoft Teams のライブ イベント使用状況レポート
author: cichur
ms.author: v-cichur
manager: serdars
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: svemu
f1.keywords:
- NOCSH
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
description: Microsoft Teams 管理センターで Teams ライブ イベント使用状況レポートを使用して、組織内の Teams ライブ イベント アクティビティの概要を取得する方法について説明します。
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 971e9bc846ad1a7134c1877a1716fc535ae65e4d
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49809287"
---
# <a name="microsoft-teams-live-event-usage-report"></a><span data-ttu-id="4cc1c-103">Microsoft Teams のライブ イベント使用状況レポート</span><span class="sxs-lookup"><span data-stu-id="4cc1c-103">Microsoft Teams live event usage report</span></span>

<span data-ttu-id="4cc1c-104">Microsoft Teams 管理センターの Teams ライブ イベント使用状況レポートには、組織内で開催されたライブ イベントのアクティビティの概要が表示されます。</span><span class="sxs-lookup"><span data-stu-id="4cc1c-104">The Teams live event usage report in the Microsoft Teams admin center shows you the activity overview for live events held in your organization.</span></span> <span data-ttu-id="4cc1c-105">各イベントの利用状況情報 (イベントの状態、開始時刻、ビュー、実稼働の種類など) を表示できます。</span><span class="sxs-lookup"><span data-stu-id="4cc1c-105">You can view usage information, including event status, start time, views, and production type for each event.</span></span> <span data-ttu-id="4cc1c-106">使用状況の傾向を把握し、組織内の誰がライブ イベントのスケジュール、発表、作成を行うのか確認できます。</span><span class="sxs-lookup"><span data-stu-id="4cc1c-106">You can gain insight into usage trends and see who in your organization schedules, presents, and produces live events.</span></span>

## <a name="view-the-live-event-usage-report"></a><span data-ttu-id="4cc1c-107">ライブ イベントの使用状況レポートを表示する</span><span class="sxs-lookup"><span data-stu-id="4cc1c-107">View the live event usage report</span></span>

1. <span data-ttu-id="4cc1c-108">Microsoft Teams 管理センターの左側のナビゲーションで、**[分析 & レポート]** > **[使用状況レポート]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="4cc1c-108">In the left navigation of the Microsoft Teams admin center, click **Analytics & reports** > **Usage reports**.</span></span> <span data-ttu-id="4cc1c-109">[レポート **の表示] タブの** [ **レポート] で、[Teams** ライブ **イベントの使用状況] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="4cc1c-109">On the **View reports** tab, under **Report**, select **Teams live event usage**.</span></span>
2. <span data-ttu-id="4cc1c-110">[ **日付範囲] で**、定義済みの範囲を選択するか、ユーザー設定の範囲を設定します。</span><span class="sxs-lookup"><span data-stu-id="4cc1c-110">Under **Date range**, select a predefined range or set a custom range.</span></span> <span data-ttu-id="4cc1c-111">範囲を設定して、現在の日付の 6 か月前と後に最大 1 年のデータを表示できます。</span><span class="sxs-lookup"><span data-stu-id="4cc1c-111">You can set a range to show  data up to a year, six months before and after the current date.</span></span>
3. <span data-ttu-id="4cc1c-112">(省略可能)[ **開催者**] で、特定のユーザーが開催したライブ イベントのみを表示することができます。</span><span class="sxs-lookup"><span data-stu-id="4cc1c-112">(Optional) Under **Organizer**, you can choose to show only live events organized by a specific user.</span></span>
4. <span data-ttu-id="4cc1c-113">[レポートの **実行] をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="4cc1c-113">Click **Run report**.</span></span>  

    <span data-ttu-id="4cc1c-114">![吹き出し付き Teams 管理センターの Teams ライブ イベント使用状況レポートのスクリーンショット](../media/teams-live-event-usage-report-with-callouts.png "吹き出し付き Teams 管理センターの Teams ライブ イベント使用状況レポートのスクリーンショット")</span><span class="sxs-lookup"><span data-stu-id="4cc1c-114">![Screenshot of the Teams live event usage report in the Teams admin center with callouts](../media/teams-live-event-usage-report-with-callouts.png "Screenshot of the Teams live event usage report in the Teams admin center with callouts")</span></span>

## <a name="interpret-the-report"></a><span data-ttu-id="4cc1c-115">レポートを解釈する</span><span class="sxs-lookup"><span data-stu-id="4cc1c-115">Interpret the report</span></span>

|<span data-ttu-id="4cc1c-116">Callout</span><span class="sxs-lookup"><span data-stu-id="4cc1c-116">Callout</span></span> |<span data-ttu-id="4cc1c-117">説明</span><span class="sxs-lookup"><span data-stu-id="4cc1c-117">Description</span></span>  |
|--------|-------------|
|<span data-ttu-id="4cc1c-118">**1**</span><span class="sxs-lookup"><span data-stu-id="4cc1c-118">**1**</span></span>   |<span data-ttu-id="4cc1c-119">Teams のライブ イベント レポートでは、過去 7 日間、28 日間、または設定したユーザー設定の日付範囲の傾向を確認できます。</span><span class="sxs-lookup"><span data-stu-id="4cc1c-119">The Teams live event report can be viewed for trends over the last 7 days, 28 days, or a custom date range that you set.</span></span> |
|<span data-ttu-id="4cc1c-120">**2**</span><span class="sxs-lookup"><span data-stu-id="4cc1c-120">**2**</span></span>   |<span data-ttu-id="4cc1c-121">各レポートには、生成された日付が含されます。</span><span class="sxs-lookup"><span data-stu-id="4cc1c-121">Each report has a date for when it was generated.</span></span> <span data-ttu-id="4cc1c-122">レポートには、ページが更新された場合のほぼリアルタイムのアクティビティが反映されます。</span><span class="sxs-lookup"><span data-stu-id="4cc1c-122">The report reflects near real time activity when the page is refreshed.</span></span> |
|<span data-ttu-id="4cc1c-123">**3**</span><span class="sxs-lookup"><span data-stu-id="4cc1c-123">**3**</span></span>   |<ul><li><span data-ttu-id="4cc1c-124">グラフ上の X 軸はこのレポートで選択した日付範囲です。</span><span class="sxs-lookup"><span data-stu-id="4cc1c-124">The X axis on the chart is the selected date range for the report.</span></span></li> <li> <span data-ttu-id="4cc1c-125">Y 軸は、ビューの総数です。</span><span class="sxs-lookup"><span data-stu-id="4cc1c-125">The Y axis is the total view count.</span></span></li> </ul><span data-ttu-id="4cc1c-126">特定の日付のドットの上にマウス ポインターを置くと、その日付のすべてのライブ イベントのビュー数が表示されます。</span><span class="sxs-lookup"><span data-stu-id="4cc1c-126">Hover over the dot on a given date to see the number of views across all live events on that date.</span></span>|
|<span data-ttu-id="4cc1c-127">**4**</span><span class="sxs-lookup"><span data-stu-id="4cc1c-127">**4**</span></span>   |<span data-ttu-id="4cc1c-128">この表は、各ライブ イベントの内訳を示しています。</span><span class="sxs-lookup"><span data-stu-id="4cc1c-128">The table gives you a breakdown of each live event.</span></span> <ul><li><span data-ttu-id="4cc1c-129">**イベント** はライブ イベントの表示名です。</span><span class="sxs-lookup"><span data-stu-id="4cc1c-129">**Event** is the display name of the live event.</span></span> <span data-ttu-id="4cc1c-130">イベント名をクリックすると、 [イベントの詳細](#view-event-details) が表示されます。</span><span class="sxs-lookup"><span data-stu-id="4cc1c-130">Click the the event name to [get more details](#view-event-details) about the event.</span></span> </li> <li><span data-ttu-id="4cc1c-131">**[開始時刻** ] は、イベントの開始日と時刻を参照します。</span><span class="sxs-lookup"><span data-stu-id="4cc1c-131">**Start Time** refers to the start date and time of the event.</span></span></li> <li><span data-ttu-id="4cc1c-132">**イベントの状態** は、イベントが発生したかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="4cc1c-132">**Event Status** shows whether the event has taken place.</span></span>  </li><li><span data-ttu-id="4cc1c-133">**開催** 者は、イベント 開催者の名前です。</span><span class="sxs-lookup"><span data-stu-id="4cc1c-133">**Organizer** is the name of the event organizer.</span></span></li> <li><span data-ttu-id="4cc1c-134">**発表者** は、イベントの発表者の名前です。</span><span class="sxs-lookup"><span data-stu-id="4cc1c-134">**Presenters** are the names of the  event presenters.</span></span></li><li><span data-ttu-id="4cc1c-135">**プロデューサーは** 、イベント プロデューサーの名前です。</span><span class="sxs-lookup"><span data-stu-id="4cc1c-135">**Producers** are the names of the event producers.</span></span></li><li><span data-ttu-id="4cc1c-136">**ビュー** は、イベントが完了した後の一意のビューの数です。</span><span class="sxs-lookup"><span data-stu-id="4cc1c-136">**Views** is the number of unique views after the event is completed .</span></span></li><li><span data-ttu-id="4cc1c-137">**記録** は、記録設定がオンかオフかを示します。</span><span class="sxs-lookup"><span data-stu-id="4cc1c-137">**Recording** shows whether the recording setting is on or off.</span></span></li><li><span data-ttu-id="4cc1c-138">**実稼働の** 種類は、イベントが Teams で生成されたのか、外部アプリケーションまたはデバイスによって生成されたのかを示します。</span><span class="sxs-lookup"><span data-stu-id="4cc1c-138">**Production Type** shows whether the event is produced in Teams or by an external application or device.</span></span></li></li> </ul><span data-ttu-id="4cc1c-139">ユーザー アカウントが Azure AD に存在しなくなった場合は、ユーザー名がテーブルに "--" として表示されます。</span><span class="sxs-lookup"><span data-stu-id="4cc1c-139">Note that if a user account no longer exists in Azure AD, the user name is displayed as "--" in the table.</span></span> <br><br><span data-ttu-id="4cc1c-140">表に希望する情報を表示するには、表に列を追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4cc1c-140">To see the information that you want in the table, make sure to add the columns to the table.</span></span> |
|<span data-ttu-id="4cc1c-141">**5**</span><span class="sxs-lookup"><span data-stu-id="4cc1c-141">**5**</span></span>   |<span data-ttu-id="4cc1c-142">[**列の編集**] を選択して表で列を追加または削除します。</span><span class="sxs-lookup"><span data-stu-id="4cc1c-142">Select **Edit columns** to add or remove columns in the table.</span></span>|

## <a name="notes"></a><span data-ttu-id="4cc1c-143">備考</span><span class="sxs-lookup"><span data-stu-id="4cc1c-143">Notes</span></span>
<span data-ttu-id="4cc1c-144">現在のレポートの条件に一致する最大 100 のライブ イベントが表示されます。</span><span class="sxs-lookup"><span data-stu-id="4cc1c-144">Showing up to 100 live events that match the current report criteria.</span></span> <span data-ttu-id="4cc1c-145">その他のライブ イベントを表示するには、日付フィルターを適用してリスト サイズを小さくします。</span><span class="sxs-lookup"><span data-stu-id="4cc1c-145">To see more live events, apply date filters to reduce the list size.</span></span>

## <a name="view-event-details"></a><span data-ttu-id="4cc1c-146">イベントの詳細を表示する</span><span class="sxs-lookup"><span data-stu-id="4cc1c-146">View event details</span></span>

<span data-ttu-id="4cc1c-147">ライブ イベントの詳細ページには、ライブ イベントの詳細の概要が表示され、イベントに関連付けられているトランスクリプトやレコーディングを含むすべてのファイルが一覧表示されます。</span><span class="sxs-lookup"><span data-stu-id="4cc1c-147">The live event details page gives you a summary of the details of a live event and lists all the files, including transcripts and recordings, associated with the event.</span></span> <span data-ttu-id="4cc1c-148">ファイル名をクリックして、ファイルを表示またはダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="4cc1c-148">Click a file name to view or download the file.</span></span>

![ライブ イベントの詳細を示すスクリーンショット](../media/teams-live-event-usage-report-event-detail.png)

<span data-ttu-id="4cc1c-150">組織で [ハイ](https://www.hivestreaming.com/partners/integration-partners/microsoft/) ブ eCDN または [Kollective](https://kollective.com) eCDN が有効になっている場合は、パートナー レポートのリンクをクリックして、追加の出席者分析を取得できます。</span><span class="sxs-lookup"><span data-stu-id="4cc1c-150">If your organization is enabled for [Hive](https://www.hivestreaming.com/partners/integration-partners/microsoft/) eCDN or [Kollective](https://kollective.com) eCDN, you can get additional attendee analytics by clicking the partner report link.</span></span>

## <a name="related-topics"></a><span data-ttu-id="4cc1c-151">関連項目</span><span class="sxs-lookup"><span data-stu-id="4cc1c-151">Related topics</span></span>

- [<span data-ttu-id="4cc1c-152">Teams の分析とレポート</span><span class="sxs-lookup"><span data-stu-id="4cc1c-152">Teams analytics and reporting</span></span>](teams-reporting-reference.md)
- [<span data-ttu-id="4cc1c-153">Teams のライブ イベントについて</span><span class="sxs-lookup"><span data-stu-id="4cc1c-153">What are Teams live events?</span></span>](../teams-live-events/what-are-teams-live-events.md)
