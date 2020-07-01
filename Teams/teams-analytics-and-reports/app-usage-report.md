---
title: Microsoft Teams アプリの使用状況レポート
author: LolaJacobsen
ms.author: lolaj
manager: serdars
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: v-quhur
f1.keywords:
- NOCSH
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
description: Microsoft Teams 管理センターで Teams アプリの使用状況レポートを使用する方法について説明します。
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 565a3cb28b73a37162947859effc6ec154b59258
ms.sourcegitcommit: 60b859dcb8ac727a38bf28cdb63ff762e7338af8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/30/2020
ms.locfileid: "44938206"
---
# <a name="microsoft-teams-app-usage-report"></a><span data-ttu-id="00cf3-103">Microsoft Teams アプリの使用状況レポート</span><span class="sxs-lookup"><span data-stu-id="00cf3-103">Microsoft Teams app usage report</span></span>

<span data-ttu-id="00cf3-104">Microsoft Teams 管理センターの Teams アプリの使用状況レポートには、ユーザーが Teams で使用しているアプリに関する情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="00cf3-104">The Teams app usage report in the Microsoft Teams admin center provides you with information about which apps users are using in Teams.</span></span>  

## <a name="view-the-app-usage-report"></a><span data-ttu-id="00cf3-105">アプリの使用状況レポートを表示する</span><span class="sxs-lookup"><span data-stu-id="00cf3-105">View the App Usage report</span></span>

1.  <span data-ttu-id="00cf3-106">管理センターの左のナビゲーションで <https://admin.teams.microsoft.com> 、[分析] をクリックして [**レポート**の \> **利用状況レポート]**& します。</span><span class="sxs-lookup"><span data-stu-id="00cf3-106">In the left navigation of the admin center at <https://admin.teams.microsoft.com>, click **Analytics & reports** \> **Usage reports**.</span></span> <span data-ttu-id="00cf3-107">[**レポートの表示**] タブの [**レポート**] で、[**アプリの利用状況**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="00cf3-107">On the **View reports** tab, under **Report**, select **Apps Usage**.</span></span>

     :::image type="content" source="media/app-usage-report1.png" alt-text="[利用状況レポート] メニュー項目のスクリーンショット":::

2.  <span data-ttu-id="00cf3-109">**[日付の範囲]** の下で、範囲を選択して、**[レポートの実行]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="00cf3-109">Under **Date range**, select a range, and then click **Run report**.</span></span>

      :::image type="content" source="media/app-usage-report2.png" alt-text="アプリの利用状況レポートのスクリーンショット":::

## <a name="interpret-the-report"></a><span data-ttu-id="00cf3-111">レポートを解釈する</span><span class="sxs-lookup"><span data-stu-id="00cf3-111">Interpret the report</span></span>

|<span data-ttu-id="00cf3-112">Callout</span><span class="sxs-lookup"><span data-stu-id="00cf3-112">Callout</span></span> |<span data-ttu-id="00cf3-113">説明</span><span class="sxs-lookup"><span data-stu-id="00cf3-113">Description</span></span>  |
|--------|-------------|
|<span data-ttu-id="00cf3-114">**1**</span><span class="sxs-lookup"><span data-stu-id="00cf3-114">**1**</span></span>   |<span data-ttu-id="00cf3-115">Teams アプリの使用状況レポートでは、過去7日間、30日間、または90日間の傾向を確認できます。</span><span class="sxs-lookup"><span data-stu-id="00cf3-115">The Teams Apps usage report can be viewed for trends over the last 7, 30 or 90 days.</span></span> |
|<span data-ttu-id="00cf3-116">**2**</span><span class="sxs-lookup"><span data-stu-id="00cf3-116">**2**</span></span>   |<span data-ttu-id="00cf3-117">各レポートには、レポートが生成された日付が含まれています。</span><span class="sxs-lookup"><span data-stu-id="00cf3-117">Each report has a date for when the report was generated.</span></span> <span data-ttu-id="00cf3-118">通常、レポートには、アプリが開かれた時点からの24時間の遅延時間が反映されます。</span><span class="sxs-lookup"><span data-stu-id="00cf3-118">The reports usually reflect a 24-hour latency from the time an app was opened.</span></span> <br><br>![日付範囲が表示されたアプリの利用状況レポートのスクリーンショット](media/app-usage-report3.png)|
|<span data-ttu-id="00cf3-120">**3**</span><span class="sxs-lookup"><span data-stu-id="00cf3-120">**3**</span></span>    | <ul><li><span data-ttu-id="00cf3-121">グラフの X 軸は、特定のレポートに対して選択した日付範囲です。</span><span class="sxs-lookup"><span data-stu-id="00cf3-121">The X axis on the charts is the selected date range for the specific report.</span></span></li><li><span data-ttu-id="00cf3-122">Y 軸は、指定した日にグラフ内にマウスポインターを置いたユーザーの数です。これらのユーザーは、少なくとも1回アプリを開いた後、アクティブなユーザーと見なされ、その後、マウスをポイントしたときに表示される合計に計上されます。</span><span class="sxs-lookup"><span data-stu-id="00cf3-122">The Y axis is the number of users who for the given day hovered over in chart, those users have opened an app at least once and by doing so are considered an Active User and accrue towards the total seen on mouse hover over.</span></span></li></ul>|
|<span data-ttu-id="00cf3-123">**4**</span><span class="sxs-lookup"><span data-stu-id="00cf3-123">**4**</span></span>   |<span data-ttu-id="00cf3-124">特定の日付でのアプリの利用状況を表すドットの上にマウスポインターを移動すると、その日付でアプリのアクティブなユーザーの合計数が表示されます。</span><span class="sxs-lookup"><span data-stu-id="00cf3-124">Hover over the dot representing an Apps Usage on a given date to see the number of instances of that App’s Total Active Users on that given date.</span></span>  |
|<span data-ttu-id="00cf3-125">**5**</span><span class="sxs-lookup"><span data-stu-id="00cf3-125">**5**</span></span>   |<span data-ttu-id="00cf3-126">すべてのアプリが含まれますが、フィルターアイコンを選ぶと追加のフィルターを使用できます。</span><span class="sxs-lookup"><span data-stu-id="00cf3-126">All Apps will be included but by choosing the Filter icon, additional filters are available.</span></span>  |
|<span data-ttu-id="00cf3-127">**6**</span><span class="sxs-lookup"><span data-stu-id="00cf3-127">**6**</span></span>   |<span data-ttu-id="00cf3-128">この表では、アプリ名によってアクティブなユーザーとチームが分類されていることを示します。</span><span class="sxs-lookup"><span data-stu-id="00cf3-128">The table gives you a breakdown of active users and teams by App name.</span></span><br><ul><li><span data-ttu-id="00cf3-129">[**アプリ名**は、Teams で使用されるアプリの表示名です。</span><span class="sxs-lookup"><span data-stu-id="00cf3-129">**App name** is the display name of the app used in Teams.</span></span></li><li><span data-ttu-id="00cf3-130">[**アクティブなユーザー**数」は、指定された期間に少なくとも1回アプリを開いたユーザーの数です。</span><span class="sxs-lookup"><span data-stu-id="00cf3-130">**Active users** is the number of users who opened the app at least once during the specified time period.</span></span></li><li><span data-ttu-id="00cf3-131">[**アプリの種類**] は、"Microsoft" または "サードパーティ" の静的な値です。</span><span class="sxs-lookup"><span data-stu-id="00cf3-131">**App type** is a static value of either “Microsoft” or “Third Party”.</span></span></li><li><span data-ttu-id="00cf3-132">[**アクティブなチーム**] は、チームの少なくとも1人のメンバーが、指定された期間中にアプリを開いたチームの数です。</span><span class="sxs-lookup"><span data-stu-id="00cf3-132">**Active teams** is the number of teams who have opened the App by at least one member of the team and during the specified time periods.</span></span></li><li><span data-ttu-id="00cf3-133">**Publisher**は、アプリのソフトウェア発行元です。</span><span class="sxs-lookup"><span data-stu-id="00cf3-133">**Publisher** is the software publisher of the app.</span></span></li><li><span data-ttu-id="00cf3-134">**バージョン**は、アプリの発行元からの、アプリのソフトウェアバージョンです。</span><span class="sxs-lookup"><span data-stu-id="00cf3-134">**Version** is the software version of the app, from the app publisher.</span></span></li></ul><br><span data-ttu-id="00cf3-135">![アプリの使用状況レポートのスクリーンショット](media/app-usage-report4.png)</span><span class="sxs-lookup"><span data-stu-id="00cf3-135">![Screenshot of an Apps Usage report](media/app-usage-report4.png)</span></span>  |
|<span data-ttu-id="00cf3-136">**7**</span><span class="sxs-lookup"><span data-stu-id="00cf3-136">**7**</span></span>  |<span data-ttu-id="00cf3-137">[**列の編集**] を選択して表で列を追加または削除します。</span><span class="sxs-lookup"><span data-stu-id="00cf3-137">Select **Edit columns** to add or remove columns in the table.</span></span><br><br><span data-ttu-id="00cf3-138">![[列の編集] ページのスクリーンショット](media/app-usage-report5.png)</span><span class="sxs-lookup"><span data-stu-id="00cf3-138">![Screenshot of the Edit columns page](media/app-usage-report5.png)</span></span>  |
|<span data-ttu-id="00cf3-139">**個**</span><span class="sxs-lookup"><span data-stu-id="00cf3-139">**8**</span></span>  |<span data-ttu-id="00cf3-140">レポートを CSV ファイルにエクスポートすると、オフラインで分析できます。</span><span class="sxs-lookup"><span data-stu-id="00cf3-140">You can export the report to a CSV file for offline analysis.</span></span> <span data-ttu-id="00cf3-141">**[Excel にエクスポート]** をクリックしてから、**[ダウンロード]** タブの **[ダウンロード]** をクリックして、準備のできたレポートをダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="00cf3-141">Click **Export to Excel**, and then on the **Downloads** tab, click **Download** to download the report when it's ready.</span></span><br><span data-ttu-id="00cf3-142">![ダウンロードページのスクリーンショット](media/app-usage-report7.png)</span><span class="sxs-lookup"><span data-stu-id="00cf3-142">![Screenshot of Downloads page](media/app-usage-report7.png)</span></span>  |
|<span data-ttu-id="00cf3-143">**ファイブ**</span><span class="sxs-lookup"><span data-stu-id="00cf3-143">**9**</span></span>   |<span data-ttu-id="00cf3-144">Excel でレポートを表示すると、アプリ ID を表す**Id**列も表示されます。</span><span class="sxs-lookup"><span data-stu-id="00cf3-144">When you view the report in Excel, you'll also see an **Id** column, which represents the app ID.</span></span> <span data-ttu-id="00cf3-145">通常、チーム ID は英数字の文字列です。</span><span class="sxs-lookup"><span data-stu-id="00cf3-145">A team ID is typically an alphanumeric string.</span></span> <span data-ttu-id="00cf3-146">**Id**列に \* \* \n \* \* \* と表示されている場合は、ユーザーが情報を削除しようとしたことを意味します。</span><span class="sxs-lookup"><span data-stu-id="00cf3-146">If the **Id** column shows as \*\*\n\*\*\*\*, this means that a user requested their information to be deleted.</span></span><br><span data-ttu-id="00cf3-147">![ダウンロードした Excel レポートのスクリーンショット](media/app-usage-report8.png)</span><span class="sxs-lookup"><span data-stu-id="00cf3-147">![Screenshot of the downloaded Excel report](media/app-usage-report8.png)</span></span>  |

## <a name="related-topics"></a><span data-ttu-id="00cf3-148">関連項目</span><span class="sxs-lookup"><span data-stu-id="00cf3-148">Related topics</span></span>

- [<span data-ttu-id="00cf3-149">Teams の分析とレポート</span><span class="sxs-lookup"><span data-stu-id="00cf3-149">Teams analytics and reporting</span></span>](teams-reporting-reference.md)