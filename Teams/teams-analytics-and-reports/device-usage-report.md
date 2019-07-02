---
title: Microsoft Teams のデバイス使用状況レポート
author: LanaChin
ms.author: v-lanac
manager: serdars
ms.date: 04/24/2019
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: svemu
localization_priority: Normal
search.appverid: MET150
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
description: Microsoft Teams 管理センターの Teams デバイス使用状況レポートを使用して、組織内のユーザーがどのように Teams に接続しているかを確認する方法について説明します。
appliesto:
- Microsoft Teams
ms.openlocfilehash: 86d8e2dc145aa8538326b42f5110de69542e8453
ms.sourcegitcommit: 5791b98589e64df2e2bcd96f05fd2f869a65861f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/02/2019
ms.locfileid: "35420013"
---
# <a name="microsoft-teams-device-usage-report"></a><span data-ttu-id="b3dfc-103">Microsoft Teams のデバイス使用状況レポート</span><span class="sxs-lookup"><span data-stu-id="b3dfc-103">Microsoft Teams device usage report</span></span>

<span data-ttu-id="b3dfc-104">Microsoft Teams 管理センターの Teams デバイス使用状況レポートでは、ユーザーが Teams に接続する方法についての情報が提供されます。</span><span class="sxs-lookup"><span data-stu-id="b3dfc-104">The Teams device usage report in the Microsoft Teams admin center provides you with information about how users connect to Teams.</span></span> <span data-ttu-id="b3dfc-105">レポートを使用すると、外出先でも、モバイルデバイスで何人のチームを使用しているかなど、組織全体で使用されているデバイスを確認できます。</span><span class="sxs-lookup"><span data-stu-id="b3dfc-105">You can use the report to see the devices that are used across your organization, including how many use Teams from their mobile devices when on-the-go.</span></span>  

<span data-ttu-id="b3dfc-106">![管理センターでの Teams デバイスの使用状況レポートのスクリーンショット](../media/teams-reports-device-usage.png "Microsoft teams 管理センターの Teams デバイス使用状況レポートのスクリーンショット")</span><span class="sxs-lookup"><span data-stu-id="b3dfc-106">![Screen shot of the Teams device usage report in the admin center](../media/teams-reports-device-usage.png "Screen shot of the Teams device usage report in the Microsoft Teams admin center")</span></span>

## <a name="view-the-report"></a><span data-ttu-id="b3dfc-107">レポートを表示する</span><span class="sxs-lookup"><span data-stu-id="b3dfc-107">View the report</span></span>

1. <span data-ttu-id="b3dfc-108">Microsoft Teams 管理センターに移動し、左のナビゲーションで [**分析] & [レポート**] をクリックして、[**レポート**] で [**チームデバイスの使用状況**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="b3dfc-108">Go to the Microsoft Teams admin center, in the left navigation, click **Analytics & reports**, and then under **Report**, select **Teams device usage**.</span></span> 
2. <span data-ttu-id="b3dfc-109">[**日付の範囲**] の下で、範囲を選択して、[**レポートの実行**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b3dfc-109">Under **Date range**, select a range, and then click **Run report**.</span></span> 

## <a name="interpret-the-report"></a><span data-ttu-id="b3dfc-110">レポートを解釈する</span><span class="sxs-lookup"><span data-stu-id="b3dfc-110">Interpret the report</span></span>

<span data-ttu-id="b3dfc-111">![管理センターでの Teams デバイスの使用状況レポートのスクリーンショット](../media/teams-reports-device-usage-with-callouts.png "番号付き吹き出しが表示された Microsoft teams 管理センターの teams デバイス使用状況レポートのスクリーンショット")</span><span class="sxs-lookup"><span data-stu-id="b3dfc-111">![Screen shot of the Teams device usage report in the admin center](../media/teams-reports-device-usage-with-callouts.png "Screen shot of the Teams device usage report in the Microsoft Teams admin center with numbered callouts")</span></span>

|<span data-ttu-id="b3dfc-112">コールアウト</span><span class="sxs-lookup"><span data-stu-id="b3dfc-112">Callout</span></span> |<span data-ttu-id="b3dfc-113">説明</span><span class="sxs-lookup"><span data-stu-id="b3dfc-113">Description</span></span>  |
|--------|-------------|
|<span data-ttu-id="b3dfc-114">**1**</span><span class="sxs-lookup"><span data-stu-id="b3dfc-114">**1**</span></span>   |<span data-ttu-id="b3dfc-115">[チームデバイスの使用状況] レポートでは、過去7日間または28日間の傾向を確認できます。</span><span class="sxs-lookup"><span data-stu-id="b3dfc-115">The Teams device usage report can be viewed for trends over the last 7 days or 28 days.</span></span>  |
|<span data-ttu-id="b3dfc-116">**2**</span><span class="sxs-lookup"><span data-stu-id="b3dfc-116">**2**</span></span>   |<span data-ttu-id="b3dfc-117">各レポートには、レポートが生成された日付が含まれています。</span><span class="sxs-lookup"><span data-stu-id="b3dfc-117">Each report has a date for when the report was generated.</span></span> <span data-ttu-id="b3dfc-118">通常、レポートはアクティビティの時刻から 24 ～ 48 時間の遅延を反映します。</span><span class="sxs-lookup"><span data-stu-id="b3dfc-118">The reports usually reflect a 24 to 48 hour latency from time of activity.</span></span> |
|<span data-ttu-id="b3dfc-119">**3**</span><span class="sxs-lookup"><span data-stu-id="b3dfc-119">**3**</span></span>   |<ul><li><span data-ttu-id="b3dfc-120">グラフの X 軸は、Teams に接続するために使用されるさまざまなデバイス (**Windows**、 **Mac**、 **iOS**、 **Android フォン**) を示しています。</span><span class="sxs-lookup"><span data-stu-id="b3dfc-120">The X axis on the chart represents the different devices (**Windows**, **Mac**, **iOS**, **Android Phone**) used to connect to Teams.</span></span> </li><li><span data-ttu-id="b3dfc-121">Y 軸は、選択した期間中にデバイスを使用したユーザーの数です。</span><span class="sxs-lookup"><span data-stu-id="b3dfc-121">The Y axis is the number of users using the device over the selected time period.</span></span></li> </ul><span data-ttu-id="b3dfc-122">デバイスを表すバーの上にマウスポインターを移動すると、そのデバイスを使用して Teams に接続したユーザーの数が表示されます。</span><span class="sxs-lookup"><span data-stu-id="b3dfc-122">Hover over the bar representing a device to see the number of users using the device to connect to Teams.</span></span>|
|<span data-ttu-id="b3dfc-123">**4**</span><span class="sxs-lookup"><span data-stu-id="b3dfc-123">**4**</span></span>   |<span data-ttu-id="b3dfc-124">この表では、ユーザーによるデバイスの使用状況の内訳を示します。</span><span class="sxs-lookup"><span data-stu-id="b3dfc-124">The table gives you a breakdown of device usage by user.</span></span> <ul><li><span data-ttu-id="b3dfc-125">[**表示名**はユーザーの表示名です。</span><span class="sxs-lookup"><span data-stu-id="b3dfc-125">**Display name** is the display name of the user.</span></span> <span data-ttu-id="b3dfc-126">表示名をクリックすると、Microsoft Teams 管理センターのユーザーの設定ページに移動できます。</span><span class="sxs-lookup"><span data-stu-id="b3dfc-126">You can click the display name to go to the user's setting page in the Microsoft Teams admin center.</span></span> </li><li><span data-ttu-id="b3dfc-127">Windows ベースのコンピューターの Teams デスクトップクライアントでユーザーがアクティブになっていた場合は、 **windows**が選択されます。</span><span class="sxs-lookup"><span data-stu-id="b3dfc-127">**Windows** is selected if the user was active in the Teams desktop client on a Windows-based computer.</span></span></li><li><span data-ttu-id="b3dfc-128">**Mac**は、ユーザーが macOS コンピューターの Teams デスクトップクライアントでアクティブになった場合に選択されます。</span><span class="sxs-lookup"><span data-stu-id="b3dfc-128">**Mac** is selected if the user was active in the Teams desktop client on a macOS computer.</span></span> </li> <li><span data-ttu-id="b3dfc-129">ユーザーが iOS の Teams モバイルクライアントでアクティブになっていた場合、 **ios**が選択されます。</span><span class="sxs-lookup"><span data-stu-id="b3dfc-129">**iOS** is selected if the user was active on the Teams mobile client for iOS.</span></span></li><li><span data-ttu-id="b3dfc-130">ユーザーが Android 用の Teams モバイルクライアントでアクティブになっていた場合は、[ **android スマートフォン**を選択します。</span><span class="sxs-lookup"><span data-stu-id="b3dfc-130">**Android phone** is selected if the user was active on the Teams mobile client for Android.</span></span> <li><span data-ttu-id="b3dfc-131">[**最後のアクティビティ**] は、ユーザーが Teams アクティビティに参加した最後の日付 (UTC) です。</span><span class="sxs-lookup"><span data-stu-id="b3dfc-131">**Last activity** is the last date (UTC) that the user participated in a Teams activity.</span></span></li> </ul> <span data-ttu-id="b3dfc-132">ユーザーアカウントが Azure AD に存在しなくなった場合は、ユーザー名がテーブルに "--" として表示されることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="b3dfc-132">Note that if a user account no longer exists in Azure AD, the user name is displayed as "--" in the table.</span></span> <br><br><span data-ttu-id="b3dfc-133">表に希望する情報を表示するには、表に列を追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b3dfc-133">To see the information that you want in the table, make sure to add the columns to the table.</span></span> |
|<span data-ttu-id="b3dfc-134">**5**</span><span class="sxs-lookup"><span data-stu-id="b3dfc-134">**5**</span></span>   |<span data-ttu-id="b3dfc-135">[**列の編集**] を選択して表で列を追加または削除します。</span><span class="sxs-lookup"><span data-stu-id="b3dfc-135">Select **Edit columns** to add or remove columns in the table.</span></span> |
|<span data-ttu-id="b3dfc-136">**6**</span><span class="sxs-lookup"><span data-stu-id="b3dfc-136">**6**</span></span>   |<span data-ttu-id="b3dfc-137">レポートを CSV ファイルにエクスポートしてオフラインで分析することができます。</span><span class="sxs-lookup"><span data-stu-id="b3dfc-137">You can export the report to a CSV file for offline analysis.</span></span> <span data-ttu-id="b3dfc-138">[ **Excel にエクスポート**] をクリックし、[**ダウンロード**] タブの [**ダウンロード**] をクリックして、準備ができたらレポートをダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="b3dfc-138">Click **Export to Excel**, and then on the **Downloads** tab, click **Download** to download the report when it's ready.</span></span><br><span data-ttu-id="b3dfc-139">![エクスポートされたレポートが表示されている [ダウンロード] タブのスクリーンショット](../media/teams-reports-export-to-csv.png)</span><span class="sxs-lookup"><span data-stu-id="b3dfc-139">![Screen shot of the Downloads tab showing exported reports](../media/teams-reports-export-to-csv.png)</span></span>|

## <a name="related-topics"></a><span data-ttu-id="b3dfc-140">関連トピック</span><span class="sxs-lookup"><span data-stu-id="b3dfc-140">Related topics</span></span>
- [<span data-ttu-id="b3dfc-141">Teams の分析とレポート</span><span class="sxs-lookup"><span data-stu-id="b3dfc-141">Teams analytics and reporting</span></span>](teams-reporting-reference.md)