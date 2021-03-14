---
title: 組織のシフト アプリを管理する
author: cichur
ms.author: v-cichur
ms.reviewer: lisawu,gumariam
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
searchScope:
- Microsoft Teams
- Microsoft Cloud for Healthcare
description: Teams で組織の現場担当者向けにシフト アプリを設定および管理する方法を説明します。
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- M365-collaboration
- Teams_ITAdmin_FLW
- microsoftcloud-healthcare
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 218b041d83cde91a23201ab864160ce3b8b7cb6e
ms.sourcegitcommit: fdef9b52247097e5cae64f01b6b2b710c5b203cf
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/20/2021
ms.locfileid: "49909091"
---
# <a name="manage-the-shifts-app-for-your-organization-in-microsoft-teams"></a><span data-ttu-id="25fba-103">Microsoft Teams で組織のシフト アプリを管理する</span><span class="sxs-lookup"><span data-stu-id="25fba-103">Manage the Shifts app for your organization in Microsoft Teams</span></span>

> [!IMPORTANT]
> <span data-ttu-id="25fba-104">2020 年 6 月 30 日をもって、Microsoft Staffhub は廃止されました。</span><span class="sxs-lookup"><span data-stu-id="25fba-104">Effective June 30, 2020, Microsoft StaffHub has been retired.</span></span> <span data-ttu-id="25fba-105">Microsoft では、StaffHub の機能を Microsoft Teams に組み込む作業に取り組んでいます。</span><span class="sxs-lookup"><span data-stu-id="25fba-105">We're building StaffHub capabilities into Microsoft Teams.</span></span> <span data-ttu-id="25fba-106">現在、Teams にはシフト アプリのスケジュール管理機能が含まれています。今後、他の機能もロールアウトされる予定です。</span><span class="sxs-lookup"><span data-stu-id="25fba-106">Today, Teams includes the Shifts app for schedule management and additional capabilities will roll out over time.</span></span> <span data-ttu-id="25fba-107">StaffHub は 2020 年 6 月 30 日をもって、すべてのユーザーがご利用できなくなりました。</span><span class="sxs-lookup"><span data-stu-id="25fba-107">StaffHub stopped working for all users on June 30, 2020.</span></span> <span data-ttu-id="25fba-108">ユーザーが StaffHub を開くと、Teams をダウンロードするように求めるメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="25fba-108">Anyone who tries to open StaffHub is shown a message directing them to download Teams.</span></span> <span data-ttu-id="25fba-109">詳細については、「[Microsoft StaffHub は廃止されました](microsoft-staffhub-to-be-retired.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="25fba-109">To learn more, see [Microsoft StaffHub has been retired](microsoft-staffhub-to-be-retired.md).</span></span>  

## <a name="overview-of-shifts"></a><span data-ttu-id="25fba-110">シフトの概要</span><span class="sxs-lookup"><span data-stu-id="25fba-110">Overview of Shifts</span></span>

<span data-ttu-id="25fba-111">Microsoft Teams のシフト アプリでは、現場担当者との連絡と同期を常に行えます。このアプリは、チームが迅速で効果的な時間管理とコミュニケーションを行えるようにモバイル ファーストで構築されています。</span><span class="sxs-lookup"><span data-stu-id="25fba-111">The Shifts app in Microsoft Teams keeps Frontline Workers connected and in sync. It's built mobile first for fast and effective time management and communication for teams.</span></span> <span data-ttu-id="25fba-112">シフトを使用すると、現場担当者とそのマネージャーは自分のモバイル デバイスを使用して、スケジュールを管理し、連絡を取ることができます。</span><span class="sxs-lookup"><span data-stu-id="25fba-112">Shifts lets Frontline Workers and their managers use their mobile devices to manage schedules and keep in touch.</span></span>

- <span data-ttu-id="25fba-113">マネージャーは、チームのシフト スケジュールを作成、更新、および管理します。</span><span class="sxs-lookup"><span data-stu-id="25fba-113">Managers create, update, and manage shift schedules for teams.</span></span> <span data-ttu-id="25fba-114">マネージャーは、メッセージを 1 人のユーザーに送ることも ("床が汚れています" など)、チーム全体に送ることもできます ("地区本部長があと 20 分で到着します" など)。</span><span class="sxs-lookup"><span data-stu-id="25fba-114">They can send messages to one person ("there's a spill on the floor") or the entire team ("the regional GM is arriving in 20 minutes").</span></span> <span data-ttu-id="25fba-115">マネージャーは、ポリシー ドキュメント、ニュース速報、およびビデオを送信することもできます。</span><span class="sxs-lookup"><span data-stu-id="25fba-115">They can also send policy documents, news bulletins, and videos.</span></span> 
- <span data-ttu-id="25fba-116">従業員は、自分の今後のシフトの確認、自分の他にその日にスケジュールが入っている従業員の表示、シフトの入れ替えや申し出のリクエスト、および休暇のリクエストを行います。</span><span class="sxs-lookup"><span data-stu-id="25fba-116">Employees view their upcoming shifts, see who else is scheduled for the day, request to swap or offer a shift, and request time off.</span></span> 

<span data-ttu-id="25fba-117">シフトでは現在、ゲスト ユーザーはサポートされていませんのでご注意ください。</span><span class="sxs-lookup"><span data-stu-id="25fba-117">It's important to know that Shifts currently doesn't support guest users.</span></span> <span data-ttu-id="25fba-118">つまり、Teams でゲスト アクセスがオンになっていると、チームのゲストをシフト スケジュールに追加することも、チームのゲストがシフト スケジュールを使用することもできません。</span><span class="sxs-lookup"><span data-stu-id="25fba-118">This means that guests on a team can't be added to or use shift schedules when Guest access is turned on in Teams.</span></span> 

> [!Note]
> <span data-ttu-id="25fba-119">さまざまなプラットフォームでの Shifts 機能の詳細については、「[プラットフォームごとの Teams の機能](https://support.microsoft.com/office/teams-features-by-platform-debe7ff4-7db4-4138-b7d0-fcc276f392d3)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="25fba-119">For details about Shifts capabilities on different platforms, see [Teams features by platform](https://support.microsoft.com/office/teams-features-by-platform-debe7ff4-7db4-4138-b7d0-fcc276f392d3).</span></span>

## <a name="availability-of-shifts"></a><span data-ttu-id="25fba-120">シフトの可用性</span><span class="sxs-lookup"><span data-stu-id="25fba-120">Availability of Shifts</span></span>

<span data-ttu-id="25fba-121">シフトは、Teams が使用可能なすべてのエンタープライズ SKU で使用できます。</span><span class="sxs-lookup"><span data-stu-id="25fba-121">Shifts is available in all Enterprise SKUs where Teams is available.</span></span>

## <a name="location-of-shifts-data"></a><span data-ttu-id="25fba-122">シフトのデータの場所</span><span class="sxs-lookup"><span data-stu-id="25fba-122">Location of Shifts data</span></span>

<span data-ttu-id="25fba-123">現在、シフトのデータは、北米、西ヨーロッパ、およびアジア太平洋にあるデータ センターの Azure に保存されています。</span><span class="sxs-lookup"><span data-stu-id="25fba-123">Shifts data is currently stored in Azure in data centers in North America, Western Europe, and Asia Pacific.</span></span> <span data-ttu-id="25fba-124">データが保存される場所の詳細については、「[データの保存場所](http://o365datacentermap.azurewebsites.net/)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="25fba-124">For more information about where data is stored, see [Where is my data](http://o365datacentermap.azurewebsites.net/)?</span></span>

## <a name="set-up-shifts"></a><span data-ttu-id="25fba-125">シフトのセットアップ</span><span class="sxs-lookup"><span data-stu-id="25fba-125">Set up Shifts</span></span>

### <a name="enable-or-disable-shifts-in-your-organization"></a><span data-ttu-id="25fba-126">組織のシフトを有効または無効にする</span><span class="sxs-lookup"><span data-stu-id="25fba-126">Enable or disable Shifts in your organization</span></span>

<span data-ttu-id="25fba-127">シフトは、組織内のすべての Teams ユーザーに対して既定で有効になっています。</span><span class="sxs-lookup"><span data-stu-id="25fba-127">Shifts is enabled by default for all Teams users in your organization.</span></span> <span data-ttu-id="25fba-128">組織レベルでアプリをオフまたはオンにするには、Microsoft Teams 管理センターの [[アプリを管理]](../../manage-apps.md) ページで行います。</span><span class="sxs-lookup"><span data-stu-id="25fba-128">You can turn off or turn on the app at the org level on the [Manage apps](../../manage-apps.md) page in the Microsoft Teams admin center.</span></span>

1. <span data-ttu-id="25fba-129">Microsoft Teams 管理センターの左側のナビゲーションで、**[Teams アプリ]** > **[アプリを管理]** の順に移動します。</span><span class="sxs-lookup"><span data-stu-id="25fba-129">In the left navigation of the Microsoft Teams admin center, go to **Teams apps** > **Manage apps**.</span></span>
2. <span data-ttu-id="25fba-130">アプリ リストで、次のいずれかの操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="25fba-130">In the list of apps, do one of the following actions:</span></span>

    - <span data-ttu-id="25fba-131">組織のシフトをオフにするには、シフト アプリを検索して選択し、**[ブロック]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="25fba-131">To turn off Shifts for your organization, search for the Shifts app, select it, and then select **Block**.</span></span>
    - <span data-ttu-id="25fba-132">組織のシフトをオンにするには、シフト アプリを検索して選択し、**[許可]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="25fba-132">To turn on Shifts for your organization, search for the Shifts app, select it, and then select **Allow**.</span></span>

### <a name="enable-or-disable-shifts-for-specific-users-in-your-organization"></a><span data-ttu-id="25fba-133">組織内の特定のユーザーのシフトを有効または無効にする</span><span class="sxs-lookup"><span data-stu-id="25fba-133">Enable or disable Shifts for specific users in your organization</span></span>

<span data-ttu-id="25fba-134">組織内の特定のユーザーによるシフトの使用を許可またはブロックするには、[[アプリの管理]](../../manage-apps.md) ページで組織のシフトがオンになっていることを確認してからカスタムのアプリのアクセス許可ポリシーを作成し、それらのユーザーに割り当てます。</span><span class="sxs-lookup"><span data-stu-id="25fba-134">To allow or block specific users in your organization from using Shifts, make sure Shifts is turned on for your organization on the [Manage apps](../../manage-apps.md) page, and then create a custom app permission policy and assign it to those users.</span></span> <span data-ttu-id="25fba-135">詳細については、「[Teams のアプリのアクセス許可ポリシーを管理する](../../teams-app-permission-policies.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="25fba-135">To learn more, see [Manage app permission policies in Teams](../../teams-app-permission-policies.md).</span></span>

### <a name="use-the-frontlineworker-app-setup-policy-to-pin-shifts-to-teams"></a><span data-ttu-id="25fba-136">現場担当者のアプリ セットアップ ポリシーを使用してシフトを Teams にピン留めする</span><span class="sxs-lookup"><span data-stu-id="25fba-136">Use the FrontlineWorker app setup policy to pin Shifts to Teams</span></span>

<span data-ttu-id="25fba-137">アプリ セットアップ ポリシーを使用すると、組織内のユーザーにとって最も重要なアプリを強調表示するように Teams をカスタマイズできます。</span><span class="sxs-lookup"><span data-stu-id="25fba-137">App setup policies let you customize Teams to highlight the apps that are most important for users in your organization.</span></span> <span data-ttu-id="25fba-138">ポリシーに設定されたアプリは、アプリ バー (Teams デスクトップ クライアントの横、および Teams モバイル クライアントの一番下にある) にピン留めされ、ユーザーはそこからすばやく簡単にアプリにアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="25fba-138">The apps set in a policy are pinned to the app bar&mdash;the bar on the side of the Teams desktop client and at the bottom of the Teams mobile clients&mdash;where users can quickly and easily access them.</span></span>
 
<span data-ttu-id="25fba-139">Teams には組み込みの現場担当者アプリ セットアップ ポリシーが含まれており、これを組織内の現場担当者に割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="25fba-139">Teams includes a built-in FrontlineWorker app setup policy that you can assign to Frontline Workers in your organization.</span></span> <span data-ttu-id="25fba-140">既定では、ポリシーにはアクティビティ、シフト、チャット、および通話の各アプリが含まれています。</span><span class="sxs-lookup"><span data-stu-id="25fba-140">By default, the policy includes the Activity, Shifts, Chat, and Calling apps.</span></span> 

<span data-ttu-id="25fba-141">現場担当者ポリシーを表示するには、Microsoft Teams 管理センターの左側のナビゲーションで、**[Teams アプリ]** > **[アプリ セットアップ ポリシー]** の順に移動します。</span><span class="sxs-lookup"><span data-stu-id="25fba-141">To view the FrontlineWorker policy, in the left navigation of the Microsoft Teams admin center, go to **Teams app** > **App setup policies**.</span></span>

<span data-ttu-id="25fba-142">![現場担当者アプリのセットアップ ポリシーのスクリーンショット](../../media/firstline-worker-app-setup-policy.png "Microsoft Teams 管理センターの現場担当者アプリのセットアップ ポリシーのスクリーンショット")</span><span class="sxs-lookup"><span data-stu-id="25fba-142">![Screenshot of the FrontlineWorker app setup policy](../../media/firstline-worker-app-setup-policy.png "Screenshot of the FrontlineWorker app setup policy in the Microsoft Teams admin center")</span></span>

#### <a name="assign-the-frontlineworker-app-setup-policy-to-users"></a><span data-ttu-id="25fba-143">現場担当者アプリのセットアップ ポリシーをユーザーに割り当てる</span><span class="sxs-lookup"><span data-stu-id="25fba-143">Assign the FrontlineWorker app setup policy to users</span></span>

[!INCLUDE [assign-policy](../../includes/assign-policy.md)]

## <a name="search-the-audit-log-for-shifts-events"></a><span data-ttu-id="25fba-144">Teams でシフト イベントの監査ログを検索する</span><span class="sxs-lookup"><span data-stu-id="25fba-144">Search the audit log for Shifts events</span></span>

<span data-ttu-id="25fba-145">**(プレビュー段階)**</span><span class="sxs-lookup"><span data-stu-id="25fba-145">**(in preview)**</span></span>

<span data-ttu-id="25fba-146">監査ログを検索して、組織内のシフト アクティビティを表示できます。</span><span class="sxs-lookup"><span data-stu-id="25fba-146">You can search the audit log to view Shifts activity in your organization.</span></span>  <span data-ttu-id="25fba-147">監査ログを検索する方法と、監査ログに記録されている [Shifts アクティビティ](../../audit-log-events.md#shifts-in-teams-activities)のリストを確認するには、「[Teams 内でイベントの監査ログを検索する](../../audit-log-events.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="25fba-147">To learn more about how to search the audit log and to see a list of [Shifts activities](../../audit-log-events.md#shifts-in-teams-activities) that are logged in the audit log, see [Search the audit log for events in Teams](../../audit-log-events.md).</span></span>

<span data-ttu-id="25fba-148">監査ログを検索できるようになるには、最初に[セキュリティ/コンプライアンス センター](https://protection.office.com)で監査をオンにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="25fba-148">Before you can search the audit log, you have to first turn on auditing in the [Security & Compliance Center](https://protection.office.com).</span></span> <span data-ttu-id="25fba-149">詳細については、「[監査ログの検索を有効または無効にする](https://support.office.com/article/Turn-Office-365-audit-log-search-on-or-off-e893b19a-660c-41f2-9074-d3631c95a014)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="25fba-149">To learn more, see [Turn audit log search on or off](https://support.office.com/article/Turn-Office-365-audit-log-search-on-or-off-e893b19a-660c-41f2-9074-d3631c95a014).</span></span> <span data-ttu-id="25fba-150">利用できる監査データは、監査を有効にした時点以降のデータのみであることにご注意ください。</span><span class="sxs-lookup"><span data-stu-id="25fba-150">Keep in mind that audit data is only available from the point at which you turned on auditing.</span></span>

## <a name="related-topics"></a><span data-ttu-id="25fba-151">関連トピック</span><span class="sxs-lookup"><span data-stu-id="25fba-151">Related topics</span></span>

- [<span data-ttu-id="25fba-152">現場担当者向けのシフトのヘルプ</span><span class="sxs-lookup"><span data-stu-id="25fba-152">Shifts Help for Frontline Workers</span></span>](https://support.office.com/article/apps-and-services-cc1fba57-9900-4634-8306-2360a40c665b)
- [<span data-ttu-id="25fba-153">Teams でユーザーにポリシーを割り当てる</span><span class="sxs-lookup"><span data-stu-id="25fba-153">Assign policies to your users in Teams</span></span>](../../assign-policies.md)
