---
title: Microsoft Teams情報保護ライセンス レポート
author: anandab-msft
ms.author: anandab
manager: serdars
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: ''
f1.keywords:
- NOCSH
localization_priority: Normal
search.appverid: ''
ms.collection:
- M365-collaboration
description: Microsoft Teams 管理センターの Teams Information Protection ライセンス レポートを使用して、組織内のアプリが変更通知イベント サブスクリプション API を使用している方法を確認する方法について説明します。
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: f5652ee503d6810a11f1b152dc0ea2dad23cf4df
ms.sourcegitcommit: 5c68298474d1782e69bde8c0940be7150cb93f6e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/23/2021
ms.locfileid: "53096886"
---
# <a name="microsoft-teams-information-protection-license-report"></a><span data-ttu-id="eb772-103">Microsoft Teams情報保護ライセンス レポート</span><span class="sxs-lookup"><span data-stu-id="eb772-103">Microsoft Teams information protection license report</span></span>

<span data-ttu-id="eb772-104">Teams 情報保護ライセンス レポートは、テナント レベル (/teams/getAllMessage または /chats/getAllMessages) で作成、更新、または削除されたメッセージをリッスンするために、変更通知イベントをサブスクライブしているアプリに関する分析情報を提供します。 [](/graph/api/resources/subscription?view=graph-rest-1.0) [](/graph/api/resources/webhooks?view=graph-rest-1.0)</span><span class="sxs-lookup"><span data-stu-id="eb772-104">The Teams information protection license report gives insight into apps that have [subscribed](/graph/api/resources/subscription?view=graph-rest-1.0) to [change notification](/graph/api/resources/webhooks?view=graph-rest-1.0) events to listen to created, updated, or deleted messages at tenant level (that is, /teams/getAllMessage or /chats/getAllMessages).</span></span> <span data-ttu-id="eb772-105">メッセージに対応する変更通知は、ユーザーが必要なライセンス を持つ場合にのみ正常 [に送信されます](/graph/teams-licenses)。</span><span class="sxs-lookup"><span data-stu-id="eb772-105">A change notification corresponding to the message is sent successfully only when the user has the [required license](/graph/teams-licenses).</span></span>  <span data-ttu-id="eb772-106">特定のユーザーによってトリガーされた変更通知の数を確認できます。</span><span class="sxs-lookup"><span data-stu-id="eb772-106">You can see how many change notifications was triggered by a given user.</span></span>


## <a name="view-the-information-protection-license-report"></a><span data-ttu-id="eb772-107">情報保護ライセンス レポートを表示する</span><span class="sxs-lookup"><span data-stu-id="eb772-107">View the information protection license report</span></span>

<span data-ttu-id="eb772-108">これらの変更を行うには、Teams サービス管理者であることが必要です。</span><span class="sxs-lookup"><span data-stu-id="eb772-108">You must be a Teams service admin to make these changes.</span></span> <span data-ttu-id="eb772-109">「[Teams 管理者ロールを使用してチームを管理する](../using-admin-roles.md)」をご覧いただき、管理者ロールとアクセス許可を取得する方法について読んでください。</span><span class="sxs-lookup"><span data-stu-id="eb772-109">See [Use Teams administrator roles to manage Teams](../using-admin-roles.md) to read about getting admin roles and permissions.</span></span>

1. <span data-ttu-id="eb772-110">管理センターの左側のナビゲーションで、[分析Microsoft Teamsレポート] **& レポート]**  >  **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="eb772-110">In the left navigation of the Microsoft Teams admin center, select **Analytics & reports** > **Usage reports**.</span></span> <span data-ttu-id="eb772-111">[レポートの **表示] タブの** [レポート] **で、[Information** **Protection License] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="eb772-111">On the **View reports** tab, under **Report**, select **Information Protection License**.</span></span>
2. <span data-ttu-id="eb772-112">[ **日付範囲] で** 範囲を選択します。</span><span class="sxs-lookup"><span data-stu-id="eb772-112">Under **Date range**, select a range.</span></span>
3. <span data-ttu-id="eb772-113">[アプリ **] で** アプリを選択し、[レポートの実行] **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="eb772-113">Under **Apps**, select an app and then select **Run report**.</span></span>

    <span data-ttu-id="eb772-114">![吹き出しTeams付き、Teams情報保護ライセンス レポートのスクリーンショット](../media/teams-info-protection-license-report-with-callouts.png "吹き出しTeams付き、Teams情報保護ライセンス レポートのスクリーンショット")</span><span class="sxs-lookup"><span data-stu-id="eb772-114">![Screenshot of the Teams information protection license report in the Teams admin center with callouts](../media/teams-info-protection-license-report-with-callouts.png "Screenshot of the Teams information protection license report in the Teams admin center with callouts")</span></span>

## <a name="interpret-the-report"></a><span data-ttu-id="eb772-115">レポートを解釈する</span><span class="sxs-lookup"><span data-stu-id="eb772-115">Interpret the report</span></span>

|<span data-ttu-id="eb772-116">Callout</span><span class="sxs-lookup"><span data-stu-id="eb772-116">Callout</span></span> |<span data-ttu-id="eb772-117">説明</span><span class="sxs-lookup"><span data-stu-id="eb772-117">Description</span></span>  |
|--------|-------------|
|<span data-ttu-id="eb772-118">**1**</span><span class="sxs-lookup"><span data-stu-id="eb772-118">**1**</span></span>   |<span data-ttu-id="eb772-119">情報保護ライセンス レポートでは、過去 7 日間、30 日間、または 90 日間の傾向を確認できます。</span><span class="sxs-lookup"><span data-stu-id="eb772-119">The information protection license report can be viewed for trends over the last 7 days, 30, or 90 days.</span></span> |
|<span data-ttu-id="eb772-120">**2**</span><span class="sxs-lookup"><span data-stu-id="eb772-120">**2**</span></span>   |<span data-ttu-id="eb772-121">アプリ名には、日付範囲で選択された過去 n 日間のメッセージの通知イベントを変更するためにサブスクライブしているすべてのアプリの一覧が表示されます。</span><span class="sxs-lookup"><span data-stu-id="eb772-121">App name will display a list of all apps that have subscribed to change notification events of messages in the last n days as selected in the date range.</span></span> |
|<span data-ttu-id="eb772-122">**3**</span><span class="sxs-lookup"><span data-stu-id="eb772-122">**3**</span></span>   |<span data-ttu-id="eb772-123">テーブルには、選択したアプリのユーザーごとの使用状況の内訳が表示されます。</span><span class="sxs-lookup"><span data-stu-id="eb772-123">The table gives you a breakdown of usage per user for the selected app.</span></span><ul><li><span data-ttu-id="eb772-124">**表示名** はユーザーの表示名です。</span><span class="sxs-lookup"><span data-stu-id="eb772-124">**Display name** is the display name of the user.</span></span> <span data-ttu-id="eb772-125">表示名を選択して、管理センターのユーザーの詳細ページMicrosoft Teamsします。</span><span class="sxs-lookup"><span data-stu-id="eb772-125">Select the display name to go to the user's details page in the Microsoft Teams admin center.</span></span></li><li><span data-ttu-id="eb772-126">**Has Required License** is yes if the user has one required licenses as defined (here)[ https://docs.microsoft.com/en-us/graph/teams-licenses ].</span><span class="sxs-lookup"><span data-stu-id="eb772-126">**Has Required License** is yes if the user has one of the required licenses as defined (here)[https://docs.microsoft.com/en-us/graph/teams-licenses].</span></span> <span data-ttu-id="eb772-127">ユーザーが必要なライセンスを持ってない場合は、[ライセンスの割り当て] リンクが表示され、Microsoft 管理センターのユーザーのライセンスの詳細ページに移動します **([** ユーザーのアクティブ ユーザー] >選択  >  します)。</span><span class="sxs-lookup"><span data-stu-id="eb772-127">If the user does not have the required license, the _Assign license_ link is displayed which navigated to the user's license detail page in the Microsoft admin center (**Users** > **Active Users** > select username).</span></span></li><li><span data-ttu-id="eb772-128">**ライセンスで保護されたイベント** は、そのユーザーによって作成、更新、または削除されたメッセージに対してアプリに送信される一意の変更通知イベントの数です。</span><span class="sxs-lookup"><span data-stu-id="eb772-128">**License Protected Events** is the number of unique change notification events sent to the app against a message which was created, updated or deleted by that user.</span></span></li></ul> |
|<span data-ttu-id="eb772-129">**4**</span><span class="sxs-lookup"><span data-stu-id="eb772-129">**4**</span></span>   |<span data-ttu-id="eb772-130">レポートを CSV ファイルにエクスポートしてオフライン分析します。</span><span class="sxs-lookup"><span data-stu-id="eb772-130">Export the report to a CSV file for offline analysis.</span></span> <span data-ttu-id="eb772-131">[**エクスポート] をExcel、[** ダウンロード]**タブを選択** します。[**ダウンロード]** を選択して、準備ができたらレポートをダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="eb772-131">Select **Export to Excel**, and then the **Downloads** tab. Select **Download** to download the report when it's ready.</span></span> |
|<span data-ttu-id="eb772-132">**5**</span><span class="sxs-lookup"><span data-stu-id="eb772-132">**5**</span></span>   |<span data-ttu-id="eb772-133">レポートを CSV ファイルにエクスポートしてオフライン分析します。</span><span class="sxs-lookup"><span data-stu-id="eb772-133">Export the report to a CSV file for offline analysis.</span></span> <span data-ttu-id="eb772-134">[**エクスポート] をExcel、[** ダウンロード]**タブを選択** します。[**ダウンロード]** を選択して、準備ができたらレポートをダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="eb772-134">Select **Export to Excel**, and then the **Downloads** tab. Select **Download** to download the report when it's ready.</span></span> <span data-ttu-id="eb772-135">レポートを Excel で表示すると、ユーザーのユーザー ID とメールアドレスを表す [ID] 列と [電子メール] 列も表示されます。</span><span class="sxs-lookup"><span data-stu-id="eb772-135">When you view the report in Excel, you'll also see an **Id** and **email** column, which represents the User ID and email address of the user.</span></span> |

## <a name="make-the-user-specific-data-anonymous"></a><span data-ttu-id="eb772-136">ユーザー固有のデータを匿名にする</span><span class="sxs-lookup"><span data-stu-id="eb772-136">Make the user-specific data anonymous</span></span>

<span data-ttu-id="eb772-137">ユーザー アクティビティ レポートのTeamsを匿名にする場合は、グローバル管理者である必要があります。</span><span class="sxs-lookup"><span data-stu-id="eb772-137">To make the data in the Teams user activity report anonymous, you have to be a global administrator.</span></span> <span data-ttu-id="eb772-138">これにより、レポートとそのエクスポートの表示名、電子メール、Azure AD ID などの識別可能な情報が非表示になります。</span><span class="sxs-lookup"><span data-stu-id="eb772-138">This will hide identifiable information such as display name, email, and Azure AD ID in reports and their exports.</span></span>

1. <span data-ttu-id="eb772-139">[組織] Microsoft 365 管理センター に移動し、[設定] タブ設定 [レポート] を \> 選択 **します**。 </span><span class="sxs-lookup"><span data-stu-id="eb772-139">In the Microsoft 365 admin center, go to **Settings** \> **Org Settings**, and under the **Services** tab, choose **Reports**.</span></span>
    
2. <span data-ttu-id="eb772-140">[ **レポート]** を選択し、[匿名識別子 **を表示する] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="eb772-140">Select **Reports**, and then choose to **Display anonymous identifiers**.</span></span> <span data-ttu-id="eb772-141">この設定は、管理センターと管理センターの使用状況Microsoft 365 管理センター両方Teams適用されます。</span><span class="sxs-lookup"><span data-stu-id="eb772-141">This setting gets applied both to the usage reports in the Microsoft 365 admin center and the Teams admin center.</span></span>
  
3. <span data-ttu-id="eb772-142">[変更の **保存] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="eb772-142">Select **Save changes**.</span></span>
