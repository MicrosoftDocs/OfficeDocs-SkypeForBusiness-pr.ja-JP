---
title: Microsoft Teams の使用状況レポート
author: LanaChin
ms.author: v-lanac
manager: serdars
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: svemu
localization_priority: Normal
search.appverid: MET150
ms.collection:
- Teams_ITAdmin_Help
- M365-collaboration
description: 自分の組織での Teams のアクティビティの概要を把握するために、Microsoft Teams 管理センターにある Teams の使用状況レポートを、どのように使用するかについて説明します。
appliesto:
- Microsoft Teams
ms.openlocfilehash: 6a31d3a6bf374e512dde0549dbbd59ed90904cd0
ms.sourcegitcommit: a71ad6762e18267faaaac09533bac80a181102af
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/10/2019
ms.locfileid: "37439574"
---
# <a name="microsoft-teams-usage-report"></a><span data-ttu-id="171ff-103">Microsoft Teams の使用状況レポート</span><span class="sxs-lookup"><span data-stu-id="171ff-103">Microsoft Teams usage report</span></span>

<span data-ttu-id="171ff-104">Microsoft Teams 管理センターにある Teams の使用状況レポートは、Teams での使用状況のアクティビティの概要を提供するもので、アクティブなユーザーおよびチャネルの数が含まれており、組織全体で何人のユーザーが通信や共同作業のために Teams を使用しているかをすぐに確認することができます。</span><span class="sxs-lookup"><span data-stu-id="171ff-104">The Teams usage report in the Microsoft Teams admin center gives you an overview of the usage activity in Teams, including the number of active users and channels, so you can quickly see how many users across your organization are using Teams to communicate and collaborate.</span></span> <span data-ttu-id="171ff-105">各チームのアクティブなユーザー、チャネル、ゲスト、およびメッセージの数など、チームでの使用状況に関する情報を表示することができます。</span><span class="sxs-lookup"><span data-stu-id="171ff-105">You can view usage information for  teams, including the number of active users and channels, guests, and messages in each team.</span></span>

## <a name="view-the-report"></a><span data-ttu-id="171ff-106">レポートを表示する</span><span class="sxs-lookup"><span data-stu-id="171ff-106">View the report</span></span>

1. <span data-ttu-id="171ff-107">Microsoft Teams 管理センターの左のナビゲーションで、[**分析] & [レポート** > の**利用状況レポート**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="171ff-107">In the left navigation of the Microsoft Teams admin center, click **Analytics & reports** > **Usage reports**.</span></span> <span data-ttu-id="171ff-108">[**レポートの表示**] タブの [**レポート**] で、[**チームの利用状況**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="171ff-108">On the **View reports** tab, under **Report**, select **Teams usage**.</span></span>
2. <span data-ttu-id="171ff-109">[**日付の範囲**] の下で、範囲を選択して、[**レポートの実行**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="171ff-109">Under **Date range**, select a range, and then click **Run report**.</span></span>

    <span data-ttu-id="171ff-110">![[チーム管理センター] の [チームの利用状況] レポートのスクリーン]ショット。吹き出しが含ま(../media/teams-reports-teams-usage-with-callouts.png "れる teams 管理センターのチーム利用レポートのスクリーン")ショット</span><span class="sxs-lookup"><span data-stu-id="171ff-110">![Screenshot of the Teams usage report in the Teams admin center with callouts](../media/teams-reports-teams-usage-with-callouts.png "Screenshot of the Teams usage report in the Teams admin center with callouts")</span></span>

## <a name="interpret-the-report"></a><span data-ttu-id="171ff-111">レポートを解釈する</span><span class="sxs-lookup"><span data-stu-id="171ff-111">Interpret the report</span></span>

|<span data-ttu-id="171ff-112">コールアウト</span><span class="sxs-lookup"><span data-stu-id="171ff-112">Callout</span></span> |<span data-ttu-id="171ff-113">説明</span><span class="sxs-lookup"><span data-stu-id="171ff-113">Description</span></span>  |
|--------|-------------|
|<span data-ttu-id="171ff-114">**1**</span><span class="sxs-lookup"><span data-stu-id="171ff-114">**1**</span></span>   |<span data-ttu-id="171ff-115">Teams 使用状況アクティビティ レポートでは、過去 7 日間または 28 日間の傾向を確認できます。</span><span class="sxs-lookup"><span data-stu-id="171ff-115">The Teams usage activity report can be viewed for trends over the last 7 days or 28 days.</span></span> |
|<span data-ttu-id="171ff-116">**2**</span><span class="sxs-lookup"><span data-stu-id="171ff-116">**2**</span></span>   |<span data-ttu-id="171ff-p103">各レポートには、このレポートが生成された日付が表示されます。通常、レポートはアクティビティの時刻から 24 から 48 時間の遅延を反映します。</span><span class="sxs-lookup"><span data-stu-id="171ff-p103">Each report has a date for when this report was generated. The reports usually reflect a 24 to 48 hour latency from time of activity.</span></span> |
|<span data-ttu-id="171ff-119">**3**</span><span class="sxs-lookup"><span data-stu-id="171ff-119">**3**</span></span>   |<ul><li><span data-ttu-id="171ff-120">グラフ上の X 軸はこのレポートで選択した日付範囲です。</span><span class="sxs-lookup"><span data-stu-id="171ff-120">The X axis on the chart is the selected date range for the report.</span></span></li> <li> <span data-ttu-id="171ff-121">Y 軸はアクティブな項目またはアクティビティの数です。</span><span class="sxs-lookup"><span data-stu-id="171ff-121">The Y axis is the count of active items or activity.</span></span></li> </ul><span data-ttu-id="171ff-122">特定の日付の項目またはアクティビティを示しているドットの上にマウス カーソルを合わせると、その特定の日付のその項目またはアクティビティのインスタンスの数を見ることができます。</span><span class="sxs-lookup"><span data-stu-id="171ff-122">Hover over the dot representing an item or activity on a given date to see the number of instances of that item or activity on that given date.</span></span>|
|<span data-ttu-id="171ff-123">**4**</span><span class="sxs-lookup"><span data-stu-id="171ff-123">**4**</span></span>   |<span data-ttu-id="171ff-124">凡例の項目をクリックして、グラフに表示する情報をフィルター処理できます。</span><span class="sxs-lookup"><span data-stu-id="171ff-124">You can filter what you see on the chart by clicking an item in the legend.</span></span> <span data-ttu-id="171ff-125">たとえば、[**アクティブなユーザーの合計**]、[**チーム & のアクティブユーザー**]、[**アクティブなチャネル**]、または [**メッセージ**] をクリックして、それぞれに関連する情報のみを表示します。</span><span class="sxs-lookup"><span data-stu-id="171ff-125">For example, click  **Total active users**, **Teams & Channels active users**,  **Active channels**, or **Messages** to see only the info related to each one.</span></span> <span data-ttu-id="171ff-126">この選択を変更しても、表内の情報は変わりません。</span><span class="sxs-lookup"><span data-stu-id="171ff-126">Changing this selection doesn’t change the information in the table.</span></span> |
|<span data-ttu-id="171ff-127">**5**</span><span class="sxs-lookup"><span data-stu-id="171ff-127">**5**</span></span>   |<span data-ttu-id="171ff-128">表によって、チームごとの使用状況の内訳が表示されます。</span><span class="sxs-lookup"><span data-stu-id="171ff-128">The table gives you a breakdown of usage by team.</span></span> <ul><li><span data-ttu-id="171ff-129">**チーム名**は、チームの表示名です。</span><span class="sxs-lookup"><span data-stu-id="171ff-129">**Team name** is the display name of the team.</span></span> <span data-ttu-id="171ff-130">チーム名をクリックすると、Microsoft Teams 管理センターのチームの [設定] ページに移動できます。</span><span class="sxs-lookup"><span data-stu-id="171ff-130">You can click the team name to go to the team's settings page in the Microsoft Teams admin center.</span></span> </li> <li><span data-ttu-id="171ff-131">**プライバシー**では、チームがプライベートなチームであるかパブリックなチームであるかが示されます。</span><span class="sxs-lookup"><span data-stu-id="171ff-131">**Privacy** refers to whether the team is a private team or public team.</span></span></li> <li><span data-ttu-id="171ff-132">**アクティブ ユーザー**は指定された期間でのチーム内のアクティブなユーザーの数です。</span><span class="sxs-lookup"><span data-stu-id="171ff-132">**Active users** is the number of active users in the team in the specified time period.</span></span></li><li><span data-ttu-id="171ff-133">**ゲスト**は指定された期間でのチーム内のゲストの数です。</span><span class="sxs-lookup"><span data-stu-id="171ff-133">**Guests** is the number of guests in the team in the specified time period.</span></span></li> </li> </ul><span data-ttu-id="171ff-134">ユーザーアカウントが Azure AD に存在しなくなった場合は、ユーザー名がテーブルに "--" として表示されることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="171ff-134">Note that if a user account no longer exists in Azure AD, the user name is displayed as "--" in the table.</span></span> <br><br><span data-ttu-id="171ff-135">表に希望する情報を表示するには、表に列を追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="171ff-135">To see the information that you want in the table, make sure to add the columns to the table.</span></span> |
|<span data-ttu-id="171ff-136">**6**</span><span class="sxs-lookup"><span data-stu-id="171ff-136">**6**</span></span>   |<span data-ttu-id="171ff-137">[**列の編集**] を選択して表で列を追加または削除します。</span><span class="sxs-lookup"><span data-stu-id="171ff-137">Select **Edit columns** to add or remove columns in the table.</span></span>|
|<span data-ttu-id="171ff-138">**7**</span><span class="sxs-lookup"><span data-stu-id="171ff-138">**7**</span></span>   |<span data-ttu-id="171ff-139">レポートを CSV ファイルにエクスポートしてオフラインで分析することができます。</span><span class="sxs-lookup"><span data-stu-id="171ff-139">You can export the report to a CSV file for offline analysis.</span></span> <span data-ttu-id="171ff-140">[ **Excel にエクスポート**] をクリックし、[**ダウンロード**] タブの [**ダウンロード**] をクリックして、準備ができたらレポートをダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="171ff-140">Click **Export to Excel**, and then on the **Downloads** tab, click **Download** to download the report when it's ready.</span></span><br><br><span data-ttu-id="171ff-141">![エクスポートされたレポートをダウンロードするための [ダウンロード] タブのスクリーンショット](../media/teams-reports-export-to-csv.png)</span><span class="sxs-lookup"><span data-stu-id="171ff-141">![Screenshot of the Downloads tab showing exported reports to download](../media/teams-reports-export-to-csv.png)</span></span>|

[!INCLUDE [teams-reports-definitions](../includes/teams-reports-definitions.md)]

## <a name="related-topics"></a><span data-ttu-id="171ff-142">関連トピック</span><span class="sxs-lookup"><span data-stu-id="171ff-142">Related topics</span></span>

- [<span data-ttu-id="171ff-143">Teams の分析とレポート</span><span class="sxs-lookup"><span data-stu-id="171ff-143">Teams analytics and reporting</span></span>](teams-reporting-reference.md)
