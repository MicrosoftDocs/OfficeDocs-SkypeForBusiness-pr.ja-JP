---
title: 組織の Shifts アプリを管理する
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
description: 組織内の最前線の従業員向け Teams で Shifts アプリを設定および管理する方法について学習します。
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
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/20/2021
ms.locfileid: "49909091"
---
# <a name="manage-the-shifts-app-for-your-organization-in-microsoft-teams"></a><span data-ttu-id="6bfdd-103">Microsoft Teams で組織のシフト アプリを管理する</span><span class="sxs-lookup"><span data-stu-id="6bfdd-103">Manage the Shifts app for your organization in Microsoft Teams</span></span>

> [!IMPORTANT]
> <span data-ttu-id="6bfdd-104">Microsoft StaffHub は 2020 年 6 月 30 日に廃止されました。</span><span class="sxs-lookup"><span data-stu-id="6bfdd-104">Effective June 30, 2020, Microsoft StaffHub has been retired.</span></span> <span data-ttu-id="6bfdd-105">StaffHub の機能を Microsoft Teams に構築しています。</span><span class="sxs-lookup"><span data-stu-id="6bfdd-105">We're building StaffHub capabilities into Microsoft Teams.</span></span> <span data-ttu-id="6bfdd-106">現在、Teams にはシフト アプリのスケジュール管理機能が含まれています。今後、他の機能もロールアウトされる予定です。</span><span class="sxs-lookup"><span data-stu-id="6bfdd-106">Today, Teams includes the Shifts app for schedule management and additional capabilities will roll out over time.</span></span> <span data-ttu-id="6bfdd-107">StaffHub は、2020 年 6 月 30 日にすべてのユーザーの作業を停止しました。</span><span class="sxs-lookup"><span data-stu-id="6bfdd-107">StaffHub stopped working for all users on June 30, 2020.</span></span> <span data-ttu-id="6bfdd-108">StaffHub を開しようとすると、Teams のダウンロードを指示するメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="6bfdd-108">Anyone who tries to open StaffHub is shown a message directing them to download Teams.</span></span> <span data-ttu-id="6bfdd-109">詳細については [、Microsoft StaffHub の廃止に関するページを参照してください](microsoft-staffhub-to-be-retired.md)。</span><span class="sxs-lookup"><span data-stu-id="6bfdd-109">To learn more, see [Microsoft StaffHub has been retired](microsoft-staffhub-to-be-retired.md).</span></span>  

## <a name="overview-of-shifts"></a><span data-ttu-id="6bfdd-110">シフトの概要</span><span class="sxs-lookup"><span data-stu-id="6bfdd-110">Overview of Shifts</span></span>

<span data-ttu-id="6bfdd-111">Microsoft Teams の Shifts アプリでは、Frontline Worker の接続と同期が維持されます。モバイルを最初に構築して、チームの時間管理とコミュニケーションを迅速かつ効果的に行います。</span><span class="sxs-lookup"><span data-stu-id="6bfdd-111">The Shifts app in Microsoft Teams keeps Frontline Workers connected and in sync. It's built mobile first for fast and effective time management and communication for teams.</span></span> <span data-ttu-id="6bfdd-112">シフトを使用すると、Frontline Worker とそのマネージャーはモバイル デバイスを使用してスケジュールを管理し、連絡を取り合います。</span><span class="sxs-lookup"><span data-stu-id="6bfdd-112">Shifts lets Frontline Workers and their managers use their mobile devices to manage schedules and keep in touch.</span></span>

- <span data-ttu-id="6bfdd-113">マネージャーは、チームのシフト スケジュールを作成、更新、および管理します。</span><span class="sxs-lookup"><span data-stu-id="6bfdd-113">Managers create, update, and manage shift schedules for teams.</span></span> <span data-ttu-id="6bfdd-114">マネージャーは、メッセージを 1 人のユーザーに送ることも ("床が汚れています" など)、チーム全体に送ることもできます ("地区本部長があと 20 分で到着します" など)。</span><span class="sxs-lookup"><span data-stu-id="6bfdd-114">They can send messages to one person ("there's a spill on the floor") or the entire team ("the regional GM is arriving in 20 minutes").</span></span> <span data-ttu-id="6bfdd-115">マネージャーは、ポリシー ドキュメント、ニュース速報、およびビデオを送信することもできます。</span><span class="sxs-lookup"><span data-stu-id="6bfdd-115">They can also send policy documents, news bulletins, and videos.</span></span> 
- <span data-ttu-id="6bfdd-116">従業員は今後のシフトの表示、その日に予定されている他のユーザーの確認、シフトの交換または提供の要求、および休みリクエストを行います。</span><span class="sxs-lookup"><span data-stu-id="6bfdd-116">Employees view their upcoming shifts, see who else is scheduled for the day, request to swap or offer a shift, and request time off.</span></span> 

<span data-ttu-id="6bfdd-117">シフトでは現在、ゲスト ユーザーはサポートされていませんのでご注意ください。</span><span class="sxs-lookup"><span data-stu-id="6bfdd-117">It's important to know that Shifts currently doesn't support guest users.</span></span> <span data-ttu-id="6bfdd-118">つまり、Teams でゲスト アクセスがオンになっていると、チームのゲストをシフト スケジュールに追加することも、チームのゲストがシフト スケジュールを使用することもできません。</span><span class="sxs-lookup"><span data-stu-id="6bfdd-118">This means that guests on a team can't be added to or use shift schedules when Guest access is turned on in Teams.</span></span> 

> [!Note]
> <span data-ttu-id="6bfdd-119">さまざまなプラットフォームでの Shifts 機能の詳細については、プラットフォーム別 [の Teams の機能を参照してください](https://support.microsoft.com/office/teams-features-by-platform-debe7ff4-7db4-4138-b7d0-fcc276f392d3)。</span><span class="sxs-lookup"><span data-stu-id="6bfdd-119">For details about Shifts capabilities on different platforms, see [Teams features by platform](https://support.microsoft.com/office/teams-features-by-platform-debe7ff4-7db4-4138-b7d0-fcc276f392d3).</span></span>

## <a name="availability-of-shifts"></a><span data-ttu-id="6bfdd-120">シフトの可用性</span><span class="sxs-lookup"><span data-stu-id="6bfdd-120">Availability of Shifts</span></span>

<span data-ttu-id="6bfdd-121">シフトは、Teams が利用可能なすべてのエンタープライズ SKU で利用できます。</span><span class="sxs-lookup"><span data-stu-id="6bfdd-121">Shifts is available in all Enterprise SKUs where Teams is available.</span></span>

## <a name="location-of-shifts-data"></a><span data-ttu-id="6bfdd-122">シフトのデータの場所</span><span class="sxs-lookup"><span data-stu-id="6bfdd-122">Location of Shifts data</span></span>

<span data-ttu-id="6bfdd-123">現在、シフトのデータは、北米、西ヨーロッパ、およびアジア太平洋にあるデータ センターの Azure に保存されています。</span><span class="sxs-lookup"><span data-stu-id="6bfdd-123">Shifts data is currently stored in Azure in data centers in North America, Western Europe, and Asia Pacific.</span></span> <span data-ttu-id="6bfdd-124">データが保存される場所の詳細については、「[データの保存場所](http://o365datacentermap.azurewebsites.net/)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6bfdd-124">For more information about where data is stored, see [Where is my data](http://o365datacentermap.azurewebsites.net/)?</span></span>

## <a name="set-up-shifts"></a><span data-ttu-id="6bfdd-125">シフトのセットアップ</span><span class="sxs-lookup"><span data-stu-id="6bfdd-125">Set up Shifts</span></span>

### <a name="enable-or-disable-shifts-in-your-organization"></a><span data-ttu-id="6bfdd-126">組織のシフトを有効または無効にする</span><span class="sxs-lookup"><span data-stu-id="6bfdd-126">Enable or disable Shifts in your organization</span></span>

<span data-ttu-id="6bfdd-127">シフトは、組織内のすべての Teams ユーザーに対して既定で有効になっています。</span><span class="sxs-lookup"><span data-stu-id="6bfdd-127">Shifts is enabled by default for all Teams users in your organization.</span></span> <span data-ttu-id="6bfdd-128">Microsoft Teams 管理センターの [アプリの管理] ページ[](../../manage-apps.md)で、組織レベルでアプリをオフまたはオンにできます。</span><span class="sxs-lookup"><span data-stu-id="6bfdd-128">You can turn off or turn on the app at the org level on the [Manage apps](../../manage-apps.md) page in the Microsoft Teams admin center.</span></span>

1. <span data-ttu-id="6bfdd-129">Microsoft Teams 管理センターの左側のナビゲーションで、Teams アプリの [アプリの **管理]**  >  **に移動します**。</span><span class="sxs-lookup"><span data-stu-id="6bfdd-129">In the left navigation of the Microsoft Teams admin center, go to **Teams apps** > **Manage apps**.</span></span>
2. <span data-ttu-id="6bfdd-130">アプリの一覧で、次のいずれかの操作を行います。</span><span class="sxs-lookup"><span data-stu-id="6bfdd-130">In the list of apps, do one of the following actions:</span></span>

    - <span data-ttu-id="6bfdd-131">組織の Shifts をオフにする場合は、Shifts アプリを検索して選択し、[ブロック] を選択 **します**。</span><span class="sxs-lookup"><span data-stu-id="6bfdd-131">To turn off Shifts for your organization, search for the Shifts app, select it, and then select **Block**.</span></span>
    - <span data-ttu-id="6bfdd-132">組織の Shifts を有効にする場合は、Shifts アプリを検索して選択し、[許可] を選択 **します**。</span><span class="sxs-lookup"><span data-stu-id="6bfdd-132">To turn on Shifts for your organization, search for the Shifts app, select it, and then select **Allow**.</span></span>

### <a name="enable-or-disable-shifts-for-specific-users-in-your-organization"></a><span data-ttu-id="6bfdd-133">組織内の特定のユーザーに対して Shifts を有効または無効にする</span><span class="sxs-lookup"><span data-stu-id="6bfdd-133">Enable or disable Shifts for specific users in your organization</span></span>

<span data-ttu-id="6bfdd-134">組織内の特定のユーザーに対して Shifts の使用を許可またはブロックするには、[アプリの管理] ページ[](../../manage-apps.md)で組織の Shifts が有効になっていることを確認し、カスタム アプリのアクセス許可ポリシーを作成して、それらのユーザーに割り当てします。</span><span class="sxs-lookup"><span data-stu-id="6bfdd-134">To allow or block specific users in your organization from using Shifts, make sure Shifts is turned on for your organization on the [Manage apps](../../manage-apps.md) page, and then create a custom app permission policy and assign it to those users.</span></span> <span data-ttu-id="6bfdd-135">詳細については、「Teams でアプリ [のアクセス許可ポリシーを管理する」を参照してください](../../teams-app-permission-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="6bfdd-135">To learn more, see [Manage app permission policies in Teams](../../teams-app-permission-policies.md).</span></span>

### <a name="use-the-frontlineworker-app-setup-policy-to-pin-shifts-to-teams"></a><span data-ttu-id="6bfdd-136">FrontlineWorker アプリのセットアップ ポリシーを使用して、Shifts を Teams にピン留めする</span><span class="sxs-lookup"><span data-stu-id="6bfdd-136">Use the FrontlineWorker app setup policy to pin Shifts to Teams</span></span>

<span data-ttu-id="6bfdd-137">アプリ セットアップ ポリシーを使用すると、組織内のユーザーにとって最も重要なアプリを強調表示するように Teams をカスタマイズできます。</span><span class="sxs-lookup"><span data-stu-id="6bfdd-137">App setup policies let you customize Teams to highlight the apps that are most important for users in your organization.</span></span> <span data-ttu-id="6bfdd-138">ポリシーに設定されたアプリは、アプリ バー (Teams デスクトップ クライアントの横、および Teams モバイル クライアントの一番下にある) にピン留めされ、ユーザーはそこからすばやく簡単にアプリにアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="6bfdd-138">The apps set in a policy are pinned to the app bar&mdash;the bar on the side of the Teams desktop client and at the bottom of the Teams mobile clients&mdash;where users can quickly and easily access them.</span></span>
 
<span data-ttu-id="6bfdd-139">Teams には、組織内の Frontline Worker に割り当て可能な組み込みの FrontlineWorker アプリセットアップ ポリシーが含まれています。</span><span class="sxs-lookup"><span data-stu-id="6bfdd-139">Teams includes a built-in FrontlineWorker app setup policy that you can assign to Frontline Workers in your organization.</span></span> <span data-ttu-id="6bfdd-140">既定では、ポリシーにはアクティビティ、シフト、チャット、および通話の各アプリが含まれています。</span><span class="sxs-lookup"><span data-stu-id="6bfdd-140">By default, the policy includes the Activity, Shifts, Chat, and Calling apps.</span></span> 

<span data-ttu-id="6bfdd-141">FrontlineWorker ポリシーを表示するには、Microsoft Teams 管理センターの左側のナビゲーションで **、Teams** アプリアプリのセットアップ ポリシー  >  **に移動します**。</span><span class="sxs-lookup"><span data-stu-id="6bfdd-141">To view the FrontlineWorker policy, in the left navigation of the Microsoft Teams admin center, go to **Teams app** > **App setup policies**.</span></span>

<span data-ttu-id="6bfdd-142">![FrontlineWorker アプリのセットアップ ポリシーのスクリーンショット](../../media/firstline-worker-app-setup-policy.png "Microsoft Teams 管理センターの FrontlineWorker アプリセットアップ ポリシーのスクリーンショット")</span><span class="sxs-lookup"><span data-stu-id="6bfdd-142">![Screenshot of the FrontlineWorker app setup policy](../../media/firstline-worker-app-setup-policy.png "Screenshot of the FrontlineWorker app setup policy in the Microsoft Teams admin center")</span></span>

#### <a name="assign-the-frontlineworker-app-setup-policy-to-users"></a><span data-ttu-id="6bfdd-143">FrontlineWorker アプリのセットアップ ポリシーをユーザーに割り当てる</span><span class="sxs-lookup"><span data-stu-id="6bfdd-143">Assign the FrontlineWorker app setup policy to users</span></span>

[!INCLUDE [assign-policy](../../includes/assign-policy.md)]

## <a name="search-the-audit-log-for-shifts-events"></a><span data-ttu-id="6bfdd-144">監査ログで Shifts イベントを検索する</span><span class="sxs-lookup"><span data-stu-id="6bfdd-144">Search the audit log for Shifts events</span></span>

<span data-ttu-id="6bfdd-145">**(プレビュー段階)**</span><span class="sxs-lookup"><span data-stu-id="6bfdd-145">**(in preview)**</span></span>

<span data-ttu-id="6bfdd-146">監査ログを検索して、組織内のシフト アクティビティを表示できます。</span><span class="sxs-lookup"><span data-stu-id="6bfdd-146">You can search the audit log to view Shifts activity in your organization.</span></span>  <span data-ttu-id="6bfdd-147">監査ログを検索する方法と、監査ログに記録された [シフト](../../audit-log-events.md#shifts-in-teams-activities) アクティビティの一覧を表示する方法の詳細については [、「Teams](../../audit-log-events.md)でイベントの監査ログを検索する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6bfdd-147">To learn more about how to search the audit log and to see a list of [Shifts activities](../../audit-log-events.md#shifts-in-teams-activities) that are logged in the audit log, see [Search the audit log for events in Teams](../../audit-log-events.md).</span></span>

<span data-ttu-id="6bfdd-148">監査ログを検索するには、まずセキュリティ/コンプライアンス センターで監査 [&があります](https://protection.office.com)。</span><span class="sxs-lookup"><span data-stu-id="6bfdd-148">Before you can search the audit log, you have to first turn on auditing in the [Security & Compliance Center](https://protection.office.com).</span></span> <span data-ttu-id="6bfdd-149">詳細については、「監査ログの検索 [を有効またはオフにする」を参照してください](https://support.office.com/article/Turn-Office-365-audit-log-search-on-or-off-e893b19a-660c-41f2-9074-d3631c95a014)。</span><span class="sxs-lookup"><span data-stu-id="6bfdd-149">To learn more, see [Turn audit log search on or off](https://support.office.com/article/Turn-Office-365-audit-log-search-on-or-off-e893b19a-660c-41f2-9074-d3631c95a014).</span></span> <span data-ttu-id="6bfdd-150">監査データは、監査を有効にした時点からのみ利用できます。</span><span class="sxs-lookup"><span data-stu-id="6bfdd-150">Keep in mind that audit data is only available from the point at which you turned on auditing.</span></span>

## <a name="related-topics"></a><span data-ttu-id="6bfdd-151">関連項目</span><span class="sxs-lookup"><span data-stu-id="6bfdd-151">Related topics</span></span>

- [<span data-ttu-id="6bfdd-152">最前線の従業員向けシフト ヘルプ</span><span class="sxs-lookup"><span data-stu-id="6bfdd-152">Shifts Help for Frontline Workers</span></span>](https://support.office.com/article/apps-and-services-cc1fba57-9900-4634-8306-2360a40c665b)
- [<span data-ttu-id="6bfdd-153"> Teams でユーザーにポリシーを割り当てる</span><span class="sxs-lookup"><span data-stu-id="6bfdd-153">Assign policies to your users in Teams</span></span>](../../assign-policies.md)
