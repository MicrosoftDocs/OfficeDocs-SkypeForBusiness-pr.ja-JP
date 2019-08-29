---
title: Microsoft Teams のデバイス使用状況レポート
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
description: Microsoft Teams 管理センターの Teams デバイス使用状況レポートを使用して、組織内のユーザーがどのように Teams に接続しているかを確認する方法について説明します。
appliesto:
- Microsoft Teams
ms.openlocfilehash: cfe8b11d633a8848d73e87c8fe0b4ecc8854062f
ms.sourcegitcommit: a5cde2df1aceed9d919ef53281dd0d75f1f5e183
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/29/2019
ms.locfileid: "36667127"
---
# <a name="microsoft-teams-device-usage-report"></a><span data-ttu-id="6a8cf-103">Microsoft Teams のデバイス使用状況レポート</span><span class="sxs-lookup"><span data-stu-id="6a8cf-103">Microsoft Teams device usage report</span></span>

<span data-ttu-id="6a8cf-104">Microsoft Teams 管理センターの Teams デバイス使用状況レポートでは、ユーザーが Teams に接続する方法についての情報が提供されます。</span><span class="sxs-lookup"><span data-stu-id="6a8cf-104">The Teams device usage report in the Microsoft Teams admin center provides you with information about how users connect to Teams.</span></span> <span data-ttu-id="6a8cf-105">レポートを使用すると、外出先でも、モバイルデバイスで何人のチームを使用しているかなど、組織全体で使用されているデバイスを確認できます。</span><span class="sxs-lookup"><span data-stu-id="6a8cf-105">You can use the report to see the devices that are used across your organization, including how many use Teams from their mobile devices when on-the-go.</span></span>  

## <a name="view-the-report"></a><span data-ttu-id="6a8cf-106">レポートを表示する</span><span class="sxs-lookup"><span data-stu-id="6a8cf-106">View the report</span></span>

1. <span data-ttu-id="6a8cf-107">Microsoft Teams 管理センターの左のナビゲーションで、[**分析] & [レポート**] の順にクリックし、[**レポート**] で [**チームデバイスの使用状況**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="6a8cf-107">In the left navigation of the Microsoft Teams admin center, click **Analytics & reports**, and then under **Report**, select **Teams device usage**.</span></span>
2. <span data-ttu-id="6a8cf-108">[**日付の範囲**] の下で、範囲を選択して、[**レポートの実行**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6a8cf-108">Under **Date range**, select a range, and then click **Run report**.</span></span>

    <span data-ttu-id="6a8cf-109">![吹き出しが表示された teams 管理センターの teams デバイス使用状況レポートのスクリーンショット](../media/teams-reports-device-usage-with-callouts.png "吹き出しが表示された teams 管理センターの teams デバイス使用状況レポートのスクリーンショット")</span><span class="sxs-lookup"><span data-stu-id="6a8cf-109">![Screen shot of the Teams device usage report in the Teams admin center with callouts](../media/teams-reports-device-usage-with-callouts.png "Screen shot of the Teams device usage report in the Teams admin center  with callouts")</span></span>

## <a name="interpret-the-report"></a><span data-ttu-id="6a8cf-110">レポートを解釈する</span><span class="sxs-lookup"><span data-stu-id="6a8cf-110">Interpret the report</span></span>

|<span data-ttu-id="6a8cf-111">コールアウト</span><span class="sxs-lookup"><span data-stu-id="6a8cf-111">Callout</span></span> |<span data-ttu-id="6a8cf-112">説明</span><span class="sxs-lookup"><span data-stu-id="6a8cf-112">Description</span></span>  |
|--------|-------------|
|<span data-ttu-id="6a8cf-113">**1**</span><span class="sxs-lookup"><span data-stu-id="6a8cf-113">**1**</span></span>   |<span data-ttu-id="6a8cf-114">[チームデバイスの使用状況] レポートでは、過去7日間または28日間の傾向を確認できます。</span><span class="sxs-lookup"><span data-stu-id="6a8cf-114">The Teams device usage report can be viewed for trends over the last 7 days or 28 days.</span></span>  |
|<span data-ttu-id="6a8cf-115">**2**</span><span class="sxs-lookup"><span data-stu-id="6a8cf-115">**2**</span></span>   |<span data-ttu-id="6a8cf-116">各レポートには、レポートが生成された日付が含まれています。</span><span class="sxs-lookup"><span data-stu-id="6a8cf-116">Each report has a date for when the report was generated.</span></span> <span data-ttu-id="6a8cf-117">通常、レポートはアクティビティの時刻から 24 ～ 48 時間の遅延を反映します。</span><span class="sxs-lookup"><span data-stu-id="6a8cf-117">The reports usually reflect a 24 to 48 hour latency from time of activity.</span></span> |
|<span data-ttu-id="6a8cf-118">**3**</span><span class="sxs-lookup"><span data-stu-id="6a8cf-118">**3**</span></span>   |<ul><li><span data-ttu-id="6a8cf-119">グラフの X 軸は、Teams に接続するために使用されるさまざまなデバイス (**Windows**、 **Mac**、 **iOS**、 **Android フォン**) を示しています。</span><span class="sxs-lookup"><span data-stu-id="6a8cf-119">The X axis on the chart represents the different devices (**Windows**, **Mac**, **iOS**, **Android Phone**) used to connect to Teams.</span></span> </li><li><span data-ttu-id="6a8cf-120">Y 軸は、選択した期間中にデバイスを使用したユーザーの数です。</span><span class="sxs-lookup"><span data-stu-id="6a8cf-120">The Y axis is the number of users using the device over the selected time period.</span></span></li> </ul><span data-ttu-id="6a8cf-121">デバイスを表すバーの上にマウスポインターを移動すると、そのデバイスを使用して Teams に接続したユーザーの数が表示されます。</span><span class="sxs-lookup"><span data-stu-id="6a8cf-121">Hover over the bar representing a device to see the number of users using the device to connect to Teams.</span></span>|
|<span data-ttu-id="6a8cf-122">**4**</span><span class="sxs-lookup"><span data-stu-id="6a8cf-122">**4**</span></span>   |<span data-ttu-id="6a8cf-123">この表では、ユーザーによるデバイスの使用状況の内訳を示します。</span><span class="sxs-lookup"><span data-stu-id="6a8cf-123">The table gives you a breakdown of device usage by user.</span></span> <ul><li><span data-ttu-id="6a8cf-124">[**表示名**はユーザーの表示名です。</span><span class="sxs-lookup"><span data-stu-id="6a8cf-124">**Display name** is the display name of the user.</span></span> <span data-ttu-id="6a8cf-125">表示名をクリックすると、Microsoft Teams 管理センターのユーザーの設定ページに移動できます。</span><span class="sxs-lookup"><span data-stu-id="6a8cf-125">You can click the display name to go to the user's setting page in the Microsoft Teams admin center.</span></span> </li><li><span data-ttu-id="6a8cf-126">Windows ベースのコンピューターの Teams デスクトップクライアントでユーザーがアクティブになっていた場合は、 **windows**が選択されます。</span><span class="sxs-lookup"><span data-stu-id="6a8cf-126">**Windows** is selected if the user was active in the Teams desktop client on a Windows-based computer.</span></span></li><li><span data-ttu-id="6a8cf-127">**Mac**は、ユーザーが macOS コンピューターの Teams デスクトップクライアントでアクティブになった場合に選択されます。</span><span class="sxs-lookup"><span data-stu-id="6a8cf-127">**Mac** is selected if the user was active in the Teams desktop client on a macOS computer.</span></span> </li> <li><span data-ttu-id="6a8cf-128">ユーザーが iOS の Teams モバイルクライアントでアクティブになっていた場合、 **ios**が選択されます。</span><span class="sxs-lookup"><span data-stu-id="6a8cf-128">**iOS** is selected if the user was active on the Teams mobile client for iOS.</span></span></li><li><span data-ttu-id="6a8cf-129">ユーザーが Android 用の Teams モバイルクライアントでアクティブになっていた場合は、[ **android スマートフォン**を選択します。</span><span class="sxs-lookup"><span data-stu-id="6a8cf-129">**Android phone** is selected if the user was active on the Teams mobile client for Android.</span></span> <li><span data-ttu-id="6a8cf-130">[**最後のアクティビティ**] は、ユーザーが Teams アクティビティに参加した最後の日付 (UTC) です。</span><span class="sxs-lookup"><span data-stu-id="6a8cf-130">**Last activity** is the last date (UTC) that the user participated in a Teams activity.</span></span></li> </ul> <span data-ttu-id="6a8cf-131">ユーザーアカウントが Azure AD に存在しなくなった場合は、ユーザー名がテーブルに "--" として表示されることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="6a8cf-131">Note that if a user account no longer exists in Azure AD, the user name is displayed as "--" in the table.</span></span> <br><br><span data-ttu-id="6a8cf-132">表に希望する情報を表示するには、表に列を追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6a8cf-132">To see the information that you want in the table, make sure to add the columns to the table.</span></span> |
|<span data-ttu-id="6a8cf-133">**5**</span><span class="sxs-lookup"><span data-stu-id="6a8cf-133">**5**</span></span>   |<span data-ttu-id="6a8cf-134">[**列の編集**] を選択して表で列を追加または削除します。</span><span class="sxs-lookup"><span data-stu-id="6a8cf-134">Select **Edit columns** to add or remove columns in the table.</span></span> |
|<span data-ttu-id="6a8cf-135">**6**</span><span class="sxs-lookup"><span data-stu-id="6a8cf-135">**6**</span></span>   |<span data-ttu-id="6a8cf-136">レポートを CSV ファイルにエクスポートしてオフラインで分析することができます。</span><span class="sxs-lookup"><span data-stu-id="6a8cf-136">You can export the report to a CSV file for offline analysis.</span></span> <span data-ttu-id="6a8cf-137">[ **Excel にエクスポート**] をクリックし、[**ダウンロード**] タブの [**ダウンロード**] をクリックして、準備ができたらレポートをダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="6a8cf-137">Click **Export to Excel**, and then on the **Downloads** tab, click **Download** to download the report when it's ready.</span></span><br><br><span data-ttu-id="6a8cf-138">![エクスポートされたレポートが表示されている [ダウンロード] タブのスクリーンショット](../media/teams-reports-export-to-csv.png)</span><span class="sxs-lookup"><span data-stu-id="6a8cf-138">![Screen shot of the Downloads tab showing exported reports](../media/teams-reports-export-to-csv.png)</span></span>|

## <a name="related-topics"></a><span data-ttu-id="6a8cf-139">関連トピック</span><span class="sxs-lookup"><span data-stu-id="6a8cf-139">Related topics</span></span>

- [<span data-ttu-id="6a8cf-140">Teams の分析とレポート</span><span class="sxs-lookup"><span data-stu-id="6a8cf-140">Teams analytics and reporting</span></span>](teams-reporting-reference.md)