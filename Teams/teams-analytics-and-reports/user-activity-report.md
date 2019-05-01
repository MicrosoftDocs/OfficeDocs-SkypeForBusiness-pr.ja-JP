---
title: Microsoft Teams ユーザー アクティビティ レポート
author: LanaChin
ms.author: v-lanac
manager: serdars
ms.date: 04/22/2019
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: svemu
localization_priority: Normal
search.appverid: MET150
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
description: マイクロソフトのチームの管理センターでチームのユーザー アクティビティ レポートを使用して、ユーザーが組織内でチームが使用している方法を参照してくださいする方法について説明します。
appliesto:
- Microsoft Teams
ms.openlocfilehash: dcb4511463a8866448739cafb1661c55481718b2
ms.sourcegitcommit: f29c0c41dc40f7e968a675d2cf10ef17d7e784da
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/30/2019
ms.locfileid: "33495868"
---
# <a name="microsoft-teams-user-activity-report"></a><span data-ttu-id="9422d-103">Microsoft Teams ユーザー アクティビティ レポート</span><span class="sxs-lookup"><span data-stu-id="9422d-103">Microsoft Teams user activity report</span></span>

<span data-ttu-id="9422d-104">チームのユーザー アクティビティ レポートでは、チーム、組織内のユーザーが実行するアクティビティの種類を把握できます。</span><span class="sxs-lookup"><span data-stu-id="9422d-104">The Teams user activity report gives you insight into the types of activities that users in your organization perform in Teams.</span></span> <span data-ttu-id="9422d-105">たとえば、ユーザーの数が 1 対 1 の呼び出しを介して通信、チャネルのメッセージをどのように多くのユーザーが通信して、ユーザー数プライベート チャット メッセージを表示できます。</span><span class="sxs-lookup"><span data-stu-id="9422d-105">For example, you can see how many users communicate through 1:1 calls, how many users communicate through channel messages, and how many users engage in private chat messages.</span></span>

<span data-ttu-id="9422d-106">![マイクロソフト チームの管理センターでチームのユーザー ・ アクティビティ ・ レポートのスクリーン ショット](../media/teams-reports-user-activity.png "マイクロソフト チームの管理センターでチームのユーザー ・ アクティビティ ・ レポートのスクリーン ショット")</span><span class="sxs-lookup"><span data-stu-id="9422d-106">![Screen shot of the Teams user activity report in the Microsoft Teams admin center](../media/teams-reports-user-activity.png "Screen shot of the Teams user activity report in the Microsoft Teams admin center")</span></span>

## <a name="view-the-report"></a><span data-ttu-id="9422d-107">レポートを表示する</span><span class="sxs-lookup"><span data-stu-id="9422d-107">View the report</span></span>

1. <span data-ttu-id="9422d-108">マイクロソフトのチーム管理センターの左側のナビゲーションでには、 **& レポートの分析**] をクリックし、[**レポート**] で [**チームのユーザーの利用状況**を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9422d-108">Go to the Microsoft Teams admin center, in the left navigation, click **Analytics & reports**, and then under **Report**, select **Teams user activity**.</span></span> 
2. <span data-ttu-id="9422d-109">[**日付の範囲**] の下で、範囲を選択して、[**レポートの実行**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="9422d-109">Under **Date range**, select a range, and then click **Run report**.</span></span> 

## <a name="interpret-the-report"></a><span data-ttu-id="9422d-110">レポートを解釈する</span><span class="sxs-lookup"><span data-stu-id="9422d-110">Interpret the report</span></span>

<span data-ttu-id="9422d-111">![コールアウトの番号とマイクロソフトのチーム管理センターでチームのユーザー アクティビティ レポートのスクリーン ショット](../media/teams-reports-user-activity-with-callouts.png "コールアウトの番号とマイクロソフトのチーム管理センターでチームのユーザー アクティビティ レポートのスクリーン ショット")</span><span class="sxs-lookup"><span data-stu-id="9422d-111">![Screenshot of the Teams user activity report in the Microsoft Teams admin center with numbered callouts](../media/teams-reports-user-activity-with-callouts.png "Screenshot of the Teams user activity report in the Microsoft Teams admin center with numbered callouts")</span></span>

|<span data-ttu-id="9422d-112">コールアウト</span><span class="sxs-lookup"><span data-stu-id="9422d-112">Callout</span></span> |<span data-ttu-id="9422d-113">説明</span><span class="sxs-lookup"><span data-stu-id="9422d-113">Description</span></span>  |
|--------|-------------|
|<span data-ttu-id="9422d-114">**1**</span><span class="sxs-lookup"><span data-stu-id="9422d-114">**1**</span></span>   |<span data-ttu-id="9422d-115">最後の 7 日間または 28 日間での傾向のチームのユーザー アクティビティ レポートを表示できます。</span><span class="sxs-lookup"><span data-stu-id="9422d-115">The Teams user activity report can be viewed for trends over the last 7 days or 28 days.</span></span> |
|<span data-ttu-id="9422d-116">**2**</span><span class="sxs-lookup"><span data-stu-id="9422d-116">**2**</span></span>   |<span data-ttu-id="9422d-p102">各レポートには、このレポートが生成された日付が表示されます。通常、レポートはアクティビティの時刻から 24 から 48 時間の遅延を反映します。</span><span class="sxs-lookup"><span data-stu-id="9422d-p102">Each report has a date for when this report was generated. The reports usually reflect a 24 to 48 hour latency from time of activity.</span></span> |
|<span data-ttu-id="9422d-119">**3**</span><span class="sxs-lookup"><span data-stu-id="9422d-119">**3**</span></span>   |<ul><li><span data-ttu-id="9422d-120">グラフの X 軸は、特定のレポートの選択した日付範囲です。</span><span class="sxs-lookup"><span data-stu-id="9422d-120">The X axis on the charts is the selected date range for the specific report.</span></span> </li><li><span data-ttu-id="9422d-121">Y 軸は、活動に参加しているユーザーの数です。</span><span class="sxs-lookup"><span data-stu-id="9422d-121">The Y axis is the number of users participating in the activity.</span></span></li></ul><span data-ttu-id="9422d-122">その特定の日にそのアクティビティのインスタンスの数を表示する特定の日に活動を表すドット上に置きます。</span><span class="sxs-lookup"><span data-stu-id="9422d-122">Hover over the dot representing an activity on a given date to see the number of instances of that activity on that given date.</span></span> |
|<span data-ttu-id="9422d-123">**4**</span><span class="sxs-lookup"><span data-stu-id="9422d-123">**4**</span></span>   |<span data-ttu-id="9422d-124">凡例の項目をクリックして、グラフに表示する情報をフィルター処理できます。</span><span class="sxs-lookup"><span data-stu-id="9422d-124">You can filter what you see on the chart by clicking an item in the legend.</span></span> <span data-ttu-id="9422d-125">たとえば、それぞれに関連する情報のみを表示するのには**1:1 の呼び出し**、**チャネルのメッセージ**、**チャット**をしたりメッセージをクリックします。</span><span class="sxs-lookup"><span data-stu-id="9422d-125">For example, click **1:1 calls**, **Channel messages**, or **Chat messages** to see only the info related to each one.</span></span> <span data-ttu-id="9422d-126">選択範囲を変更すると、テーブル内の情報は変更されません。</span><span class="sxs-lookup"><span data-stu-id="9422d-126">Changing the selection doesn’t change the information in the table.</span></span> |
|<span data-ttu-id="9422d-127">**5**</span><span class="sxs-lookup"><span data-stu-id="9422d-127">**5**</span></span>   |<span data-ttu-id="9422d-128">表では、ユーザーによる使用状況の内訳を示します。</span><span class="sxs-lookup"><span data-stu-id="9422d-128">The table gives you a breakdown of usage by user.</span></span>   <ul><li><span data-ttu-id="9422d-129">**表示名**は、ユーザーの表示名です。</span><span class="sxs-lookup"><span data-stu-id="9422d-129">**Display name** is the display name of the user.</span></span> <span data-ttu-id="9422d-130">マイクロソフトのチームの管理センターでユーザーの設定] ページに移動するのには表示名をクリックすることができます。</span><span class="sxs-lookup"><span data-stu-id="9422d-130">You can click the display name to go to the user's setting page in the Microsoft Teams admin center.</span></span></li><li><span data-ttu-id="9422d-131">**1:1 の呼び出し**はユーザーが参加している 1 対 1 の呼び出しの数を指定された期間中にします。</span><span class="sxs-lookup"><span data-stu-id="9422d-131">**1:1 calls** is the number of 1:1 calls that the user participated in during the specified time period.</span></span></li><li><span data-ttu-id="9422d-132">**チャネル メッセージ**は、ユーザーが転記される一意のメッセージの数を指定された期間中にチーム チャットにします。</span><span class="sxs-lookup"><span data-stu-id="9422d-132">**Channel messages** is the number of unique messages that the user posted in a team chat during the specified time period.</span></span></li> <li><span data-ttu-id="9422d-133">**チャット メッセージ**は、ユーザーで転記いるプライベート チャット指定された期間中に一意のメッセージの数です。</span><span class="sxs-lookup"><span data-stu-id="9422d-133">**Chat messages** is the number of unique messages that the user posted in a private chat during the specified time period.</span></span></li>  <li><span data-ttu-id="9422d-134">**最後のアクティビティ**は、ユーザーがチームの活動に参加した最後の日付 (UTC) です。</span><span class="sxs-lookup"><span data-stu-id="9422d-134">**Last activity** is the last date (UTC) that the user participated in a Teams activity.</span></span></li> </ul><span data-ttu-id="9422d-135">表に希望する情報を表示するには、表に列を追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9422d-135">To see the information that you want in the table, make sure to add the columns to the table.</span></span>
|<span data-ttu-id="9422d-136">**6**</span><span class="sxs-lookup"><span data-stu-id="9422d-136">**6**</span></span>   |<span data-ttu-id="9422d-137">[**列の編集**] を選択して表で列を追加または削除します。</span><span class="sxs-lookup"><span data-stu-id="9422d-137">Select **Edit columns** to add or remove columns in the table.</span></span> |
|<span data-ttu-id="9422d-138">**7**</span><span class="sxs-lookup"><span data-stu-id="9422d-138">**7**</span></span>   |<span data-ttu-id="9422d-139">オフラインで分析できる CSV ファイルにレポートをエクスポートすることができます。</span><span class="sxs-lookup"><span data-stu-id="9422d-139">You can export the report to a CSV file for offline analysis.</span></span> <span data-ttu-id="9422d-140">[ **Excel にエクスポート**する] をクリックし、[**ダウンロード**] タブの [**ダウンロード**の準備ができたときに、レポートをダウンロードする] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="9422d-140">Click **Export to Excel**, and then on the **Downloads** tab, click **Download** to download the report when it's ready.</span></span><br><span data-ttu-id="9422d-141">![ダウンロードするレポートをエクスポートするかを示す [ダウンロード] タブのスクリーン ショット](../media/teams-reports-export-to-csv.png)</span><span class="sxs-lookup"><span data-stu-id="9422d-141">![Screen shot of the Downloads tab showing exported reports to download](../media/teams-reports-export-to-csv.png)</span></span>||

## <a name="related-topics"></a><span data-ttu-id="9422d-142">関連トピック</span><span class="sxs-lookup"><span data-stu-id="9422d-142">Related topics</span></span>
- [<span data-ttu-id="9422d-143">Teams の分析とレポート</span><span class="sxs-lookup"><span data-stu-id="9422d-143">Teams analytics and reporting</span></span>](teams-reporting-reference.md)
- [<span data-ttu-id="9422d-144">Teams の使用状況レポート</span><span class="sxs-lookup"><span data-stu-id="9422d-144">Teams usage report</span></span>](teams-usage-report.md)
- [<span data-ttu-id="9422d-145">Teams のデバイス使用状況レポート</span><span class="sxs-lookup"><span data-stu-id="9422d-145">Teams device usage report</span></span>](device-usage-report.md)