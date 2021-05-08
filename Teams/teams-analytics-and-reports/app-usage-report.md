---
title: Microsoft Teams使用状況レポートを作成する
author: SerdarSoysal
ms.author: serdars
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
description: 管理センターでアプリの使用状況Teamsレポートを使用するMicrosoft Teamsします。
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 29e51e91cdc42000350a48dd0d83225e7791aea6
ms.sourcegitcommit: d62e6cefceebe481eb207c59872f1aa67f0fc528
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/05/2021
ms.locfileid: "50460597"
---
# <a name="microsoft-teams-app-usage-report"></a><span data-ttu-id="17501-103">Microsoft Teams使用状況レポートを作成する</span><span class="sxs-lookup"><span data-stu-id="17501-103">Microsoft Teams app usage report</span></span>

<span data-ttu-id="17501-104">Teams管理センターのアプリ使用状況レポートMicrosoft Teams、ユーザーがアプリで使用しているアプリに関する情報Teams。</span><span class="sxs-lookup"><span data-stu-id="17501-104">The Teams app usage report in the Microsoft Teams admin center provides you with information about which apps users are using in Teams.</span></span>  

## <a name="view-the-app-usage-report"></a><span data-ttu-id="17501-105">アプリの使用状況レポートを表示する</span><span class="sxs-lookup"><span data-stu-id="17501-105">View the App Usage report</span></span>

1.  <span data-ttu-id="17501-106">管理センターの左側のナビゲーションで、[分析] をクリックし、[ <https://admin.teams.microsoft.com> **利用状況& レポート** \> **を表示します**。</span><span class="sxs-lookup"><span data-stu-id="17501-106">In the left navigation of the admin center at <https://admin.teams.microsoft.com>, click **Analytics & reports** \> **Usage reports**.</span></span> <span data-ttu-id="17501-107">[レポートの **表示] タブの** [レポート] **で、[アプリ** の使用状況] **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="17501-107">On the **View reports** tab, under **Report**, select **Apps Usage**.</span></span>

     :::image type="content" source="media/app-usage-report1.png" alt-text="[使用状況レポート] メニュー項目のスクリーンショット":::

2.  <span data-ttu-id="17501-109">**[日付の範囲]** の下で、範囲を選択して、**[レポートの実行]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="17501-109">Under **Date range**, select a range, and then click **Run report**.</span></span>

      :::image type="content" source="media/app-usage-report2.png" alt-text="アプリの使用状況レポートのスクリーンショット":::

## <a name="interpret-the-report"></a><span data-ttu-id="17501-111">レポートを解釈する</span><span class="sxs-lookup"><span data-stu-id="17501-111">Interpret the report</span></span>

|<span data-ttu-id="17501-112">Callout</span><span class="sxs-lookup"><span data-stu-id="17501-112">Callout</span></span> |<span data-ttu-id="17501-113">説明</span><span class="sxs-lookup"><span data-stu-id="17501-113">Description</span></span>  |
|--------|-------------|
|<span data-ttu-id="17501-114">**1**</span><span class="sxs-lookup"><span data-stu-id="17501-114">**1**</span></span>   |<span data-ttu-id="17501-115">[Teams アプリの使用状況レポートでは、過去 7 日間、30 日間、または 90 日間の傾向を確認できます。</span><span class="sxs-lookup"><span data-stu-id="17501-115">The Teams Apps usage report can be viewed for trends over the last 7, 30 or 90 days.</span></span> |
|<span data-ttu-id="17501-116">**2**</span><span class="sxs-lookup"><span data-stu-id="17501-116">**2**</span></span>   |<span data-ttu-id="17501-117">各レポートには、レポートが生成された日付があります。</span><span class="sxs-lookup"><span data-stu-id="17501-117">Each report has a date for when the report was generated.</span></span> <span data-ttu-id="17501-118">通常、レポートには、アプリを開いた時刻から 24 時間の待機時間が反映されます。</span><span class="sxs-lookup"><span data-stu-id="17501-118">The reports usually reflect a 24-hour latency from the time an app was opened.</span></span> <br><br>![日付範囲を示すアプリの使用状況レポートのスクリーンショット](media/app-usage-report3.png)|
|<span data-ttu-id="17501-120">**3**</span><span class="sxs-lookup"><span data-stu-id="17501-120">**3**</span></span>    | <ul><li><span data-ttu-id="17501-121">グラフの X 軸は、特定のレポートに対して選択した日付範囲です。</span><span class="sxs-lookup"><span data-stu-id="17501-121">The X axis on the charts is the selected date range for the specific report.</span></span></li><li><span data-ttu-id="17501-122">Y 軸は、特定の日にグラフ内でポイントされたユーザーの数です。これらのユーザーは少なくとも 1 回アプリを開き、これを行ってアクティブ ユーザーと見なされ、マウス ポインターで表示された合計に対して発生します。</span><span class="sxs-lookup"><span data-stu-id="17501-122">The Y axis is the number of users who for the given day hovered over in chart, those users have opened an app at least once and by doing so are considered an Active User and accrue towards the total seen on mouse hover over.</span></span></li></ul>|
|<span data-ttu-id="17501-123">**4**</span><span class="sxs-lookup"><span data-stu-id="17501-123">**4**</span></span>   |<span data-ttu-id="17501-124">指定した日付のアプリの使用状況を表すドットにマウス ポインターを合わせると、その日付のアプリの合計アクティブ ユーザー数が表示されます。</span><span class="sxs-lookup"><span data-stu-id="17501-124">Hover over the dot representing an Apps Usage on a given date to see the number of instances of that App’s Total Active Users on that given date.</span></span>  |
|<span data-ttu-id="17501-125">**5**</span><span class="sxs-lookup"><span data-stu-id="17501-125">**5**</span></span>   |<span data-ttu-id="17501-126">すべてのアプリが含まれますが、[フィルター] アイコンを選択すると、追加のフィルターを使用できます。</span><span class="sxs-lookup"><span data-stu-id="17501-126">All Apps will be included but by choosing the Filter icon, additional filters are available.</span></span>  |
|<span data-ttu-id="17501-127">**6**</span><span class="sxs-lookup"><span data-stu-id="17501-127">**6**</span></span>   |<span data-ttu-id="17501-128">この表は、アクティブなユーザーとチームの内訳をアプリ名別に示しています。</span><span class="sxs-lookup"><span data-stu-id="17501-128">The table gives you a breakdown of active users and teams by App name.</span></span><br><ul><li><span data-ttu-id="17501-129">**[アプリ名**] は、アプリで使用されるアプリの表示Teams。</span><span class="sxs-lookup"><span data-stu-id="17501-129">**App name** is the display name of the app used in Teams.</span></span></li><li><span data-ttu-id="17501-130">**アクティブ ユーザー** とは、指定した期間中にアプリを少なくとも 1 回開いたユーザーの数です。</span><span class="sxs-lookup"><span data-stu-id="17501-130">**Active users** is the number of users who opened the app at least once during the specified time period.</span></span></li><li><span data-ttu-id="17501-131">**アプリの** 種類は、"Microsoft" または "サード パーティ" のいずれかの静的な値です。</span><span class="sxs-lookup"><span data-stu-id="17501-131">**App type** is a static value of either “Microsoft” or “Third Party”.</span></span></li><li><span data-ttu-id="17501-132">**アクティブな** チームとは、チームの少なくとも 1 人のメンバーが指定した期間中にアプリを開いたチームの数です。</span><span class="sxs-lookup"><span data-stu-id="17501-132">**Active teams** is the number of teams who have opened the App by at least one member of the team and during the specified time periods.</span></span></li><li><span data-ttu-id="17501-133">**Publisher** は、アプリのソフトウェア発行元です。</span><span class="sxs-lookup"><span data-stu-id="17501-133">**Publisher** is the software publisher of the app.</span></span></li><li><span data-ttu-id="17501-134">**バージョン** は、アプリの発行元から提供される、アプリのソフトウェア バージョンです。</span><span class="sxs-lookup"><span data-stu-id="17501-134">**Version** is the software version of the app, from the app publisher.</span></span></li></ul><span data-ttu-id="17501-135"><b> 注:</b> 現在、"アクティブ ユーザー" と "アクティブ なチーム" は、チャネルでのみ使用されるアプリに対して計算されます。</span><span class="sxs-lookup"><span data-stu-id="17501-135"><b> Note :</b> Currently, 'Active users' and 'Active teams' are calculated for apps used in channels only.</span></span>     

<br><span data-ttu-id="17501-136">![アプリの使用状況レポートのスクリーンショット| | ](media/app-usage-report4.png) **7**  |[列 **の編集] を** 選択して、テーブルの列を追加または削除します。</span><span class="sxs-lookup"><span data-stu-id="17501-136">![Screenshot of an Apps Usage report](media/app-usage-report4.png)  | |**7**  |Select **Edit columns** to add or remove columns in the table.</span></span><br><br><span data-ttu-id="17501-137">![[列の編集] ページのスクリーンショット| | ](media/app-usage-report5.png) **8 |**  レポートを CSV ファイルにエクスポートして、オフライン分析を行います。</span><span class="sxs-lookup"><span data-stu-id="17501-137">![Screenshot of the Edit columns page](media/app-usage-report5.png)  | |**8**  |You can export the report to a CSV file for offline analysis.</span></span> <span data-ttu-id="17501-138">**[Excel にエクスポート]** をクリックしてから、**[ダウンロード]** タブの **[ダウンロード]** をクリックして、準備のできたレポートをダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="17501-138">Click **Export to Excel**, and then on the **Downloads** tab, click **Download** to download the report when it's ready.</span></span><br><span data-ttu-id="17501-139">![[ダウンロード] ページのスクリーンショット| | ](media/app-usage-report7.png) **9 |** レポートを [ビュー] にExcel、アプリ ID を表す **[ID]** 列も表示されます。</span><span class="sxs-lookup"><span data-stu-id="17501-139">![Screenshot of Downloads page](media/app-usage-report7.png)  | |**9**   |When you view the report in Excel, you'll also see an **Id** column, which represents the app ID.</span></span> <span data-ttu-id="17501-140">通常、チーム ID は英数字の文字列です。</span><span class="sxs-lookup"><span data-stu-id="17501-140">A team ID is typically an alphanumeric string.</span></span> <span data-ttu-id="17501-141">**[Id] 列** に **\n** と表示されている場合は、ユーザーが自分の情報を削除する要求を行いました。</span><span class="sxs-lookup"><span data-stu-id="17501-141">If the **Id** column shows as \*\*\n\*\*\*\*, this means that a user requested their information to be deleted.</span></span><br><span data-ttu-id="17501-142">![ダウンロードしたレポートのExcelスクリーンショット](media/app-usage-report8.png)  |</span><span class="sxs-lookup"><span data-stu-id="17501-142">![Screenshot of the downloaded Excel report](media/app-usage-report8.png)  |</span></span>

## <a name="related-topics"></a><span data-ttu-id="17501-143">関連トピック</span><span class="sxs-lookup"><span data-stu-id="17501-143">Related topics</span></span>

- [<span data-ttu-id="17501-144">Teams の分析とレポート</span><span class="sxs-lookup"><span data-stu-id="17501-144">Teams analytics and reporting</span></span>](teams-reporting-reference.md)