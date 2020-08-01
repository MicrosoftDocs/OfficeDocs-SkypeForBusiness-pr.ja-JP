---
title: Microsoft Teams のデバイス使用状況レポート
author: LanaChin
ms.author: v-lanac
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
description: Microsoft Teams 管理センターの Teams デバイス使用状況レポートを使用して、組織内のユーザーがどのように Teams に接続しているかを確認する方法について説明します。
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: dc36ccca5145bdfdd21e5b398954aec79cd12127
ms.sourcegitcommit: dc3e8ae454c42981f037f4de2e48005428b6078e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/31/2020
ms.locfileid: "46533864"
---
# <a name="microsoft-teams-device-usage-report"></a><span data-ttu-id="a800f-103">Microsoft Teams のデバイス使用状況レポート</span><span class="sxs-lookup"><span data-stu-id="a800f-103">Microsoft Teams device usage report</span></span>

<span data-ttu-id="a800f-104">Microsoft Teams 管理センターの Teams デバイス使用状況レポートでは、ユーザーが Teams に接続する方法についての情報が提供されます。</span><span class="sxs-lookup"><span data-stu-id="a800f-104">The Teams device usage report in the Microsoft Teams admin center provides you with information about how users connect to Teams.</span></span> <span data-ttu-id="a800f-105">レポートを使用すると、外出先でも、モバイルデバイスで何人のチームを使用しているかなど、組織全体で使用されているデバイスを確認できます。</span><span class="sxs-lookup"><span data-stu-id="a800f-105">You can use the report to see the devices that are used across your organization, including how many use Teams from their mobile devices when on-the-go.</span></span>  

## <a name="view-the-device-usage-report"></a><span data-ttu-id="a800f-106">デバイスの使用状況レポートを表示する</span><span class="sxs-lookup"><span data-stu-id="a800f-106">View the device usage report</span></span>

1. <span data-ttu-id="a800f-107">Microsoft Teams 管理センターの左側のナビゲーションで、**[分析およびレポート]** > **[使用状況レポート]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a800f-107">In the left navigation of the Microsoft Teams admin center, click **Analytics & reports** > **Usage reports**.</span></span> <span data-ttu-id="a800f-108">[**レポートの表示**] タブの [**レポート**] で、[**チームデバイスの使用状況**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="a800f-108">On the **View reports** tab, under **Report**, select **Teams device usage**.</span></span>
2. <span data-ttu-id="a800f-109">**[日付の範囲]** ので範囲を選択し、**[レポートの実行]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a800f-109">Under **Date range**, select a range, and then click **Run report**.</span></span>

    <span data-ttu-id="a800f-110">![吹き出し付きの Teams 管理センターの Teams デバイスの使用状況レポートのスクリーンショット](../media/teams-reports-device-usage-with-callouts.png "吹き出し付きの Teams 管理センターの Teams デバイスの使用状況レポートのスクリーンショット")</span><span class="sxs-lookup"><span data-stu-id="a800f-110">![Screenshot of the Teams device usage report in the Teams admin center with callouts](../media/teams-reports-device-usage-with-callouts.png "Screenshot of the Teams device usage report in the Teams admin center  with callouts")</span></span>

## <a name="interpret-the-report"></a><span data-ttu-id="a800f-111">レポートを解釈する</span><span class="sxs-lookup"><span data-stu-id="a800f-111">Interpret the report</span></span>

|<span data-ttu-id="a800f-112">Callout</span><span class="sxs-lookup"><span data-stu-id="a800f-112">Callout</span></span> |<span data-ttu-id="a800f-113">説明</span><span class="sxs-lookup"><span data-stu-id="a800f-113">Description</span></span>  |
|--------|-------------|
|<span data-ttu-id="a800f-114">**1**</span><span class="sxs-lookup"><span data-stu-id="a800f-114">**1**</span></span>   |<span data-ttu-id="a800f-115">[チームデバイスの使用状況] レポートでは、過去7日間または30日間の傾向を確認できます。</span><span class="sxs-lookup"><span data-stu-id="a800f-115">The Teams device usage report can be viewed for trends over the last 7 days or 30 days.</span></span>  |
|<span data-ttu-id="a800f-116">**2**</span><span class="sxs-lookup"><span data-stu-id="a800f-116">**2**</span></span>   |<span data-ttu-id="a800f-117">各レポートには、レポートが生成された日付が含まれています。</span><span class="sxs-lookup"><span data-stu-id="a800f-117">Each report has a date for when the report was generated.</span></span> <span data-ttu-id="a800f-118">通常、レポートには、アクティビティの時間から24時間の待ち時間が反映されます。</span><span class="sxs-lookup"><span data-stu-id="a800f-118">The reports usually reflect a 24 hour latency from time of activity.</span></span> |
|<span data-ttu-id="a800f-119">**3**</span><span class="sxs-lookup"><span data-stu-id="a800f-119">**3**</span></span>   |<ul><li><span data-ttu-id="a800f-120">グラフの X 軸は、Teams に接続するために使用されるさまざまなデバイス (**Windows**、 **Mac**、 **Linux**、 **iOS**、 **Android フォン**、 **Web**) を示しています。</span><span class="sxs-lookup"><span data-stu-id="a800f-120">The X axis on the chart represents the different devices (**Windows**, **Mac**, **Linux**, **iOS**, **Android Phone**, **Web**) used to connect to Teams.</span></span> </li><li><span data-ttu-id="a800f-121">Y 軸は、選択した期間中にデバイスを使用したユーザーの数です。</span><span class="sxs-lookup"><span data-stu-id="a800f-121">The Y axis is the number of users using the device over the selected time period.</span></span></li> </ul><span data-ttu-id="a800f-122">デバイスを表すバーの上にマウスポインターを移動すると、そのデバイスを使用して Teams に接続したユーザーの数が表示されます。</span><span class="sxs-lookup"><span data-stu-id="a800f-122">Hover over the bar representing a device to see the number of users using the device to connect to Teams.</span></span>|
|<span data-ttu-id="a800f-123">**4**</span><span class="sxs-lookup"><span data-stu-id="a800f-123">**4**</span></span>   |<span data-ttu-id="a800f-124">この表では、ユーザーによるデバイスの使用状況の内訳を示します。</span><span class="sxs-lookup"><span data-stu-id="a800f-124">The table gives you a breakdown of device usage by user.</span></span> <ul><li><span data-ttu-id="a800f-125">**Username**はユーザーの表示名です。</span><span class="sxs-lookup"><span data-stu-id="a800f-125">**Username** is the display name of the user.</span></span> <span data-ttu-id="a800f-126">表示名をクリックして、Microsoft Teams 管理センターのユーザーの設定ページに移動することができます。</span><span class="sxs-lookup"><span data-stu-id="a800f-126">You can click the display name to go to the user's setting page in the Microsoft Teams admin center.</span></span> </li><li><span data-ttu-id="a800f-127">Windows ベースのコンピューターの Teams デスクトップクライアントでユーザーがアクティブになっていた場合は、 **windows**が選択されます。</span><span class="sxs-lookup"><span data-stu-id="a800f-127">**Windows** is selected if the user was active in the Teams desktop client on a Windows-based computer.</span></span></li><li><span data-ttu-id="a800f-128">**Mac**は、ユーザーが macOS コンピューターの Teams デスクトップクライアントでアクティブになった場合に選択されます。</span><span class="sxs-lookup"><span data-stu-id="a800f-128">**Mac** is selected if the user was active in the Teams desktop client on a macOS computer.</span></span> </li> <li><span data-ttu-id="a800f-129">ユーザーが Linux コンピューターの Teams デスクトップクライアントでアクティブになった場合、 **linux**が選択されます。</span><span class="sxs-lookup"><span data-stu-id="a800f-129">**Linux** is selected if the user was active in the Teams desktop client on a Linux computer.</span></span> </li> <li><span data-ttu-id="a800f-130">ユーザーが iOS の Teams モバイルクライアントでアクティブになっていた場合、 **ios**が選択されます。</span><span class="sxs-lookup"><span data-stu-id="a800f-130">**iOS** is selected if the user was active on the Teams mobile client for iOS.</span></span></li><li><span data-ttu-id="a800f-131">ユーザーが Android 用の Teams モバイルクライアントでアクティブになっていた場合は、[ **android スマートフォン**を選択します。</span><span class="sxs-lookup"><span data-stu-id="a800f-131">**Android phone** is selected if the user was active on the Teams mobile client for Android.</span></span> <li><li><span data-ttu-id="a800f-132">ユーザーが Teams web クライアントでアクティブになっていた場合は、[ **Web**に選択されています。</span><span class="sxs-lookup"><span data-stu-id="a800f-132">**Web** is selected if the user was active on the Teams web client.</span></span> <li><span data-ttu-id="a800f-133">**[最後のアクティビティ]** は、ユーザーが Teams アクティビティに参加した最後の日付 (UTC) を指します。</span><span class="sxs-lookup"><span data-stu-id="a800f-133">**Last activity** is the last date (UTC) that the user participated in a Teams activity.</span></span></li> </ul> <span data-ttu-id="a800f-134">ユーザー アカウントが Azure AD に存在しなくなった場合は、ユーザー名がテーブルに "--" として表示されます。</span><span class="sxs-lookup"><span data-stu-id="a800f-134">Note that if a user account no longer exists in Azure AD, the user name is displayed as "--" in the table.</span></span> <br><br><span data-ttu-id="a800f-135">表に希望する情報を表示するには、表に列を追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a800f-135">To see the information that you want in the table, make sure to add the columns to the table.</span></span> |
|<span data-ttu-id="a800f-136">**5**</span><span class="sxs-lookup"><span data-stu-id="a800f-136">**5**</span></span>   |<span data-ttu-id="a800f-137">[**列の編集**] を選択して表で列を追加または削除します。</span><span class="sxs-lookup"><span data-stu-id="a800f-137">Select **Edit columns** to add or remove columns in the table.</span></span> |
|<span data-ttu-id="a800f-138">**6**</span><span class="sxs-lookup"><span data-stu-id="a800f-138">**6**</span></span>   |<span data-ttu-id="a800f-139">レポートを CSV ファイルにエクスポートすると、オフラインで分析できます。</span><span class="sxs-lookup"><span data-stu-id="a800f-139">You can export the report to a CSV file for offline analysis.</span></span> <span data-ttu-id="a800f-140">**[Excel にエクスポート]** をクリックしてから、**[ダウンロード]** タブの **[ダウンロード]** をクリックして、準備のできたレポートをダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="a800f-140">Click **Export to Excel**, and then on the **Downloads** tab, click **Download** to download the report when it's ready.</span></span><br><br><span data-ttu-id="a800f-141">![エクスポートされたレポートが表示されている [ダウンロード] タブのスクリーンショット](../media/teams-reports-export-to-csv.png)</span><span class="sxs-lookup"><span data-stu-id="a800f-141">![Screenshot of the Downloads tab showing exported reports](../media/teams-reports-export-to-csv.png)</span></span>|

## <a name="related-topics"></a><span data-ttu-id="a800f-142">関連項目</span><span class="sxs-lookup"><span data-stu-id="a800f-142">Related topics</span></span>

- [<span data-ttu-id="a800f-143">Teams の分析とレポート</span><span class="sxs-lookup"><span data-stu-id="a800f-143">Teams analytics and reporting</span></span>](teams-reporting-reference.md)
