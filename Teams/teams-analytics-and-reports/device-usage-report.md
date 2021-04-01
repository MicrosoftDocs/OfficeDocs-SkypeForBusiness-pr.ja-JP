---
title: Microsoft Teams のデバイス使用状況レポート
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
description: Microsoft Teams 管理センターで Teams デバイス使用状況レポートを使用して、組織内のユーザーが Teams に接続する方法を確認する方法について説明します。
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 1d47888884ce86bfa56546a9df600ce958380e0d
ms.sourcegitcommit: 66e7b28ba1c0433535eb6a3e7d883851c27d9d1f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/31/2021
ms.locfileid: "51478357"
---
# <a name="microsoft-teams-device-usage-report"></a><span data-ttu-id="f8f67-103">Microsoft Teams のデバイス使用状況レポート</span><span class="sxs-lookup"><span data-stu-id="f8f67-103">Microsoft Teams device usage report</span></span>

<span data-ttu-id="f8f67-104">Microsoft Teams 管理センターの Teams デバイス使用状況レポートには、ユーザーが Teams に接続する方法に関する情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="f8f67-104">The Teams device usage report in the Microsoft Teams admin center provides you with information about how users connect to Teams.</span></span> <span data-ttu-id="f8f67-105">レポートを使用して、組織全体で使用されているデバイスを表示できます。また、移動中にモバイル デバイスから Teams を使用するデバイスの数も含めて表示できます。</span><span class="sxs-lookup"><span data-stu-id="f8f67-105">You can use the report to see the devices that are used across your organization, including how many use Teams from their mobile devices when on-the-go.</span></span>  

## <a name="view-the-device-usage-report"></a><span data-ttu-id="f8f67-106">デバイス使用状況レポートを表示する</span><span class="sxs-lookup"><span data-stu-id="f8f67-106">View the device usage report</span></span>

1. <span data-ttu-id="f8f67-107">Microsoft Teams 管理センターの左側のナビゲーションで、**[分析 & レポート]** > **[使用状況レポート]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f8f67-107">In the left navigation of the Microsoft Teams admin center, click **Analytics & reports** > **Usage reports**.</span></span> <span data-ttu-id="f8f67-108">[レポートの **表示] タブの** [レポート] **で、[Teams** デバイスの **使用状況] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="f8f67-108">On the **View reports** tab, under **Report**, select **Teams device usage**.</span></span>
2. <span data-ttu-id="f8f67-109">**[日付の範囲]** の下で、範囲を選択して、**[レポートの実行]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f8f67-109">Under **Date range**, select a range, and then click **Run report**.</span></span>

    <span data-ttu-id="f8f67-110">![吹き出し付き Teams 管理センターの Teams デバイス使用状況レポートのスクリーンショット](../media/teams-reports-device-usage-with-callouts.png "吹き出し付き Teams 管理センターの Teams デバイス使用状況レポートのスクリーンショット")</span><span class="sxs-lookup"><span data-stu-id="f8f67-110">![Screenshot of the Teams device usage report in the Teams admin center with callouts](../media/teams-reports-device-usage-with-callouts.png "Screenshot of the Teams device usage report in the Teams admin center  with callouts")</span></span>

## <a name="interpret-the-report"></a><span data-ttu-id="f8f67-111">レポートを解釈する</span><span class="sxs-lookup"><span data-stu-id="f8f67-111">Interpret the report</span></span>

|<span data-ttu-id="f8f67-112">Callout</span><span class="sxs-lookup"><span data-stu-id="f8f67-112">Callout</span></span> |<span data-ttu-id="f8f67-113">説明</span><span class="sxs-lookup"><span data-stu-id="f8f67-113">Description</span></span>  |
|--------|-------------|
|<span data-ttu-id="f8f67-114">**1**</span><span class="sxs-lookup"><span data-stu-id="f8f67-114">**1**</span></span>   |<span data-ttu-id="f8f67-115">Teams デバイスの使用状況レポートでは、過去 7 日間または 30 日間の傾向を確認できます。</span><span class="sxs-lookup"><span data-stu-id="f8f67-115">The Teams device usage report can be viewed for trends over the last 7 days or 30 days.</span></span>  |
|<span data-ttu-id="f8f67-116">**2**</span><span class="sxs-lookup"><span data-stu-id="f8f67-116">**2**</span></span>   |<span data-ttu-id="f8f67-117">各レポートには、レポートが生成された日付が含されます。</span><span class="sxs-lookup"><span data-stu-id="f8f67-117">Each report has a date for when the report was generated.</span></span> <span data-ttu-id="f8f67-118">レポートには通常、アクティビティの時刻から 24 時間の遅延が反映されます。</span><span class="sxs-lookup"><span data-stu-id="f8f67-118">The reports usually reflect a 24 hour latency from time of activity.</span></span> |
|<span data-ttu-id="f8f67-119">**3**</span><span class="sxs-lookup"><span data-stu-id="f8f67-119">**3**</span></span>   |<ul><li><span data-ttu-id="f8f67-120">グラフ上の X 軸は、Teams への接続に使用されるさまざまなデバイス (Windows、Mac、Linux、iOS、Android    **Phone、Web)** を表します。 </span><span class="sxs-lookup"><span data-stu-id="f8f67-120">The X axis on the chart represents the different devices (**Windows**, **Mac**, **Linux**, **iOS**, **Android Phone**, **Web**) used to connect to Teams.</span></span> </li><li><span data-ttu-id="f8f67-121">Y 軸は、選択した期間にデバイスを使用しているユーザーの数です。</span><span class="sxs-lookup"><span data-stu-id="f8f67-121">The Y axis is the number of users using the device over the selected time period.</span></span></li> </ul><span data-ttu-id="f8f67-122">デバイスを表すバーの上にマウス ポインターを置くと、デバイスを使用して Teams に接続しているユーザーの数が表示されます。</span><span class="sxs-lookup"><span data-stu-id="f8f67-122">Hover over the bar representing a device to see the number of users using the device to connect to Teams.</span></span>|
|<span data-ttu-id="f8f67-123">**4**</span><span class="sxs-lookup"><span data-stu-id="f8f67-123">**4**</span></span>   |<span data-ttu-id="f8f67-124">この表は、ユーザー別のデバイス使用状況の内訳を示しています。</span><span class="sxs-lookup"><span data-stu-id="f8f67-124">The table gives you a breakdown of device usage by user.</span></span> <ul><li><span data-ttu-id="f8f67-125">**ユーザー名** はユーザーの表示名です。</span><span class="sxs-lookup"><span data-stu-id="f8f67-125">**Username** is the display name of the user.</span></span> <span data-ttu-id="f8f67-126">表示名をクリックして、Microsoft Teams 管理センターのユーザーの設定ページに移動することができます。</span><span class="sxs-lookup"><span data-stu-id="f8f67-126">You can click the display name to go to the user's setting page in the Microsoft Teams admin center.</span></span> </li><li><span data-ttu-id="f8f67-127">**ユーザー** が Windows ベースのコンピューター上の Teams デスクトップ クライアントでアクティブだった場合、Windows が選択されます。</span><span class="sxs-lookup"><span data-stu-id="f8f67-127">**Windows** is selected if the user was active in the Teams desktop client on a Windows-based computer.</span></span></li><li><span data-ttu-id="f8f67-128">**ユーザー** が macOS コンピューターの Teams デスクトップ クライアントでアクティブだった場合、Mac が選択されます。</span><span class="sxs-lookup"><span data-stu-id="f8f67-128">**Mac** is selected if the user was active in the Teams desktop client on a macOS computer.</span></span> </li> <li><span data-ttu-id="f8f67-129">**ユーザー** が Linux コンピューター上の Teams デスクトップ クライアントでアクティブだった場合、Linux が選択されます。</span><span class="sxs-lookup"><span data-stu-id="f8f67-129">**Linux** is selected if the user was active in the Teams desktop client on a Linux computer.</span></span> </li> <li><span data-ttu-id="f8f67-130">**ユーザーが iOS** 用 Teams モバイル クライアントでアクティブだった場合、iOS が選択されます。</span><span class="sxs-lookup"><span data-stu-id="f8f67-130">**iOS** is selected if the user was active on the Teams mobile client for iOS.</span></span></li><li><span data-ttu-id="f8f67-131">**ユーザーが Android** 用 Teams モバイル クライアントでアクティブだった場合、Android フォンが選択されます。</span><span class="sxs-lookup"><span data-stu-id="f8f67-131">**Android phone** is selected if the user was active on the Teams mobile client for Android.</span></span> <li><li><span data-ttu-id="f8f67-132">**ユーザー** が Teams Web クライアントでアクティブだった場合、Web が選択されます。</span><span class="sxs-lookup"><span data-stu-id="f8f67-132">**Web** is selected if the user was active on the Teams web client.</span></span> <li><span data-ttu-id="f8f67-133">**[最後のアクティビティ]** は、ユーザーが Teams アクティビティに参加した最後の日付 (UTC) を指します。</span><span class="sxs-lookup"><span data-stu-id="f8f67-133">**Last activity** is the last date (UTC) that the user participated in a Teams activity.</span></span></li> </ul> <span data-ttu-id="f8f67-134">ユーザー アカウントが Azure AD に存在しなくなった場合は、ユーザー名がテーブルに "--" として表示されます。</span><span class="sxs-lookup"><span data-stu-id="f8f67-134">Note that if a user account no longer exists in Azure AD, the user name is displayed as "--" in the table.</span></span> <br><br><span data-ttu-id="f8f67-135">表に希望する情報を表示するには、表に列を追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f8f67-135">To see the information that you want in the table, make sure to add the columns to the table.</span></span> |
|<span data-ttu-id="f8f67-136">**5**</span><span class="sxs-lookup"><span data-stu-id="f8f67-136">**5**</span></span>   |<span data-ttu-id="f8f67-137">[**列の編集**] を選択して表で列を追加または削除します。</span><span class="sxs-lookup"><span data-stu-id="f8f67-137">Select **Edit columns** to add or remove columns in the table.</span></span> |
|<span data-ttu-id="f8f67-138">**6**</span><span class="sxs-lookup"><span data-stu-id="f8f67-138">**6**</span></span>   |<span data-ttu-id="f8f67-139">レポートを CSV ファイルにエクスポートすると、オフラインで分析できます。</span><span class="sxs-lookup"><span data-stu-id="f8f67-139">You can export the report to a CSV file for offline analysis.</span></span> <span data-ttu-id="f8f67-140">**[Excel にエクスポート]** をクリックしてから、**[ダウンロード]** タブの **[ダウンロード]** をクリックして、準備のできたレポートをダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="f8f67-140">Click **Export to Excel**, and then on the **Downloads** tab, click **Download** to download the report when it's ready.</span></span><br><br><span data-ttu-id="f8f67-141">![エクスポートされたレポートを示す [ダウンロード] タブのスクリーンショット](../media/teams-reports-export-to-csv.png)</span><span class="sxs-lookup"><span data-stu-id="f8f67-141">![Screenshot of the Downloads tab showing exported reports](../media/teams-reports-export-to-csv.png)</span></span>|


## <a name="make-the-user-specific-data-anonymous"></a><span data-ttu-id="f8f67-142">ユーザー固有のデータを匿名にする</span><span class="sxs-lookup"><span data-stu-id="f8f67-142">Make the user specific data anonymous</span></span>

<span data-ttu-id="f8f67-143">Teams デバイスの使用状況レポートのデータを匿名にする場合は、グローバル管理者である必要があります。</span><span class="sxs-lookup"><span data-stu-id="f8f67-143">To make the data in Teams device usage report anonymous, you have to be a global administrator.</span></span> <span data-ttu-id="f8f67-144">これにより、レポートの表示名、メール、AAD ID などの識別可能な情報とそのエクスポートが非表示になります。</span><span class="sxs-lookup"><span data-stu-id="f8f67-144">This will hide identifiable information such as display name, email and AAD ID in report and their export.</span></span>

1. <span data-ttu-id="f8f67-145">Microsoft 365 管理センターで、[設定] の [組織の設定] に移動し、[サービス] タブで [レポート] \> を選択 **します**。 </span><span class="sxs-lookup"><span data-stu-id="f8f67-145">In Microsoft 365 admin center, go to the **Settings** \> **Org Settings**, and under **Services** tab, choose **Reports**.</span></span>
    
2. <span data-ttu-id="f8f67-146">[レポート **] を** 選択し、[匿名識別子 **を表示する] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="f8f67-146">Select **Reports**, and then choose to **Display anonymous identifiers**.</span></span> <span data-ttu-id="f8f67-147">この設定は、Microsoft 365 管理センターの利用状況レポートと Teams 管理センターの両方に適用されます。</span><span class="sxs-lookup"><span data-stu-id="f8f67-147">This setting gets applied both to the usage reports in Microsoft 365 admin center as well as Teams admin center.</span></span>
  
3. <span data-ttu-id="f8f67-148">[変更を **保存] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="f8f67-148">Select **Save changes**.</span></span>

## <a name="related-topics"></a><span data-ttu-id="f8f67-149">関連項目</span><span class="sxs-lookup"><span data-stu-id="f8f67-149">Related topics</span></span>

- [<span data-ttu-id="f8f67-150">Teams の分析とレポート</span><span class="sxs-lookup"><span data-stu-id="f8f67-150">Teams analytics and reporting</span></span>](teams-reporting-reference.md)
