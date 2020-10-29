---
title: 組織のシフトアプリを管理する
author: LanaChin
ms.author: v-lanac
ms.reviewer: lisawu,gumariam
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
searchScope:
- Microsoft Teams
- Microsoft Cloud for Healthcare
description: 組織の Firstline Worker の Teams でシフトアプリを設定および管理する方法について説明します。
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
ms.openlocfilehash: d89ca8938c80b2afb8c1b32a395ab4a984327dcc
ms.sourcegitcommit: 62d5ccf10202a50755166e3b8de0bd31d1f94fef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/28/2020
ms.locfileid: "48790509"
---
# <a name="manage-the-shifts-app-for-your-organization-in-microsoft-teams"></a><span data-ttu-id="cfe5b-103">Microsoft Teams で組織のシフト アプリを管理する</span><span class="sxs-lookup"><span data-stu-id="cfe5b-103">Manage the Shifts app for your organization in Microsoft Teams</span></span>

> [!IMPORTANT]
> <span data-ttu-id="cfe5b-104">2020年6月30日有効な Microsoft StaffHub は廃止されました。</span><span class="sxs-lookup"><span data-stu-id="cfe5b-104">Effective June 30, 2020, Microsoft StaffHub has been retired.</span></span> <span data-ttu-id="cfe5b-105">Microsoft Teams で StaffHub 機能を構築しています。</span><span class="sxs-lookup"><span data-stu-id="cfe5b-105">We're building StaffHub capabilities into Microsoft Teams.</span></span> <span data-ttu-id="cfe5b-106">現在、Teams にはシフト アプリのスケジュール管理機能が含まれています。今後、他の機能もロールアウトされる予定です。</span><span class="sxs-lookup"><span data-stu-id="cfe5b-106">Today, Teams includes the Shifts app for schedule management and additional capabilities will roll out over time.</span></span> <span data-ttu-id="cfe5b-107">2020年6月30日に、StaffHub がすべてのユーザーに対して動作を停止しました。</span><span class="sxs-lookup"><span data-stu-id="cfe5b-107">StaffHub stopped working for all users on June 30, 2020.</span></span> <span data-ttu-id="cfe5b-108">StaffHub を開こうとするユーザーには、チームをダウンロードするように指示するメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="cfe5b-108">Anyone who tries to open StaffHub is shown a message directing them to download Teams.</span></span> <span data-ttu-id="cfe5b-109">詳細については、「 [Microsoft StaffHub が廃止されました](microsoft-staffhub-to-be-retired.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="cfe5b-109">To learn more, see [Microsoft StaffHub has been retired](microsoft-staffhub-to-be-retired.md).</span></span>  

## <a name="overview-of-shifts"></a><span data-ttu-id="cfe5b-110">シフトの概要</span><span class="sxs-lookup"><span data-stu-id="cfe5b-110">Overview of Shifts</span></span>

<span data-ttu-id="cfe5b-111">Microsoft Teams の [シフト] アプリでは、Firstline Worker が接続され、同期されます。モバイル機能を搭載しているので、チームの時間管理とコミュニケーションを迅速かつ効率的に行うことができます。</span><span class="sxs-lookup"><span data-stu-id="cfe5b-111">The Shifts app in Microsoft Teams keeps Firstline Workers connected and in sync. It's built mobile first for fast and effective time management and communication for teams.</span></span> <span data-ttu-id="cfe5b-112">[シフト] では、最初の行の作業者とそのマネージャーは、モバイルデバイスを使ってスケジュールを管理し、連絡を取ることができます。</span><span class="sxs-lookup"><span data-stu-id="cfe5b-112">Shifts lets Firstline Workers and their managers use their mobile devices to manage schedules and keep in touch.</span></span>

- <span data-ttu-id="cfe5b-113">マネージャーは、チームのシフト スケジュールを作成、更新、および管理します。</span><span class="sxs-lookup"><span data-stu-id="cfe5b-113">Managers create, update, and manage shift schedules for teams.</span></span> <span data-ttu-id="cfe5b-114">マネージャーは、メッセージを 1 人のユーザーに送ることも ("床が汚れています" など)、チーム全体に送ることもできます ("地区本部長があと 20 分で到着します" など)。</span><span class="sxs-lookup"><span data-stu-id="cfe5b-114">They can send messages to one person ("there's a spill on the floor") or the entire team ("the regional GM is arriving in 20 minutes").</span></span> <span data-ttu-id="cfe5b-115">マネージャーは、ポリシー ドキュメント、ニュース速報、およびビデオを送信することもできます。</span><span class="sxs-lookup"><span data-stu-id="cfe5b-115">They can also send policy documents, news bulletins, and videos.</span></span> 
- <span data-ttu-id="cfe5b-116">従業員は、自分の今後のシフトの確認、自分の他にその日にスケジュールが入っている従業員の表示、シフトの入れ替えや申し出のリクエスト、および休暇のリクエストが行えます。</span><span class="sxs-lookup"><span data-stu-id="cfe5b-116">Employees view their upcoming shifts, can see who else is scheduled for the day, request to swap or offer a shift, and request time off.</span></span> 

<span data-ttu-id="cfe5b-117">シフトでは現在、ゲスト ユーザーはサポートされていませんのでご注意ください。</span><span class="sxs-lookup"><span data-stu-id="cfe5b-117">It's important to know that Shifts currently doesn't support guest users.</span></span> <span data-ttu-id="cfe5b-118">つまり、Teams でゲスト アクセスがオンになっていると、チームのゲストをシフト スケジュールに追加することも、チームのゲストがシフト スケジュールを使用することもできません。</span><span class="sxs-lookup"><span data-stu-id="cfe5b-118">This means that guests on a team can't be added to or use shift schedules when Guest access is turned on in Teams.</span></span> 

> [!Note]
> <span data-ttu-id="cfe5b-119">さまざまなプラットフォームのシフト機能について詳しくは、「 [プラットフォームごとの Teams の機能](https://support.microsoft.com/office/teams-features-by-platform-debe7ff4-7db4-4138-b7d0-fcc276f392d3)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="cfe5b-119">For details about Shifts capabilities on different platforms, see [Teams features by platform](https://support.microsoft.com/office/teams-features-by-platform-debe7ff4-7db4-4138-b7d0-fcc276f392d3).</span></span>

## <a name="availability-of-shifts"></a><span data-ttu-id="cfe5b-120">シフトの可用性</span><span class="sxs-lookup"><span data-stu-id="cfe5b-120">Availability of Shifts</span></span>

<span data-ttu-id="cfe5b-121">シフトは、Teams が利用できるすべての Enterprise Sku で利用できます。</span><span class="sxs-lookup"><span data-stu-id="cfe5b-121">Shifts is available in all Enterprise SKUs where Teams is available.</span></span>

## <a name="location-of-shifts-data"></a><span data-ttu-id="cfe5b-122">シフトのデータの場所</span><span class="sxs-lookup"><span data-stu-id="cfe5b-122">Location of Shifts data</span></span>

<span data-ttu-id="cfe5b-123">現在、シフトのデータは、北米、西ヨーロッパ、およびアジア太平洋にあるデータ センターの Azure に保存されています。</span><span class="sxs-lookup"><span data-stu-id="cfe5b-123">Shifts data is currently stored in Azure in data centers in North America, Western Europe, and Asia Pacific.</span></span> <span data-ttu-id="cfe5b-124">データが保存される場所の詳細については、「[データの保存場所](http://o365datacentermap.azurewebsites.net/)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="cfe5b-124">For more information about where data is stored, see [Where is my data](http://o365datacentermap.azurewebsites.net/)?</span></span>

## <a name="set-up-shifts"></a><span data-ttu-id="cfe5b-125">シフトのセットアップ</span><span class="sxs-lookup"><span data-stu-id="cfe5b-125">Set up Shifts</span></span>

### <a name="enable-or-disable-shifts-in-your-organization"></a><span data-ttu-id="cfe5b-126">組織のシフトを有効または無効にする</span><span class="sxs-lookup"><span data-stu-id="cfe5b-126">Enable or disable Shifts in your organization</span></span>

<span data-ttu-id="cfe5b-127">シフトは、組織内のすべての Teams ユーザーに対して既定で有効になっています。</span><span class="sxs-lookup"><span data-stu-id="cfe5b-127">Shifts is enabled by default for all Teams users in your organization.</span></span> <span data-ttu-id="cfe5b-128">Microsoft Teams 管理センターの [ [アプリの管理](../../manage-apps.md) ] ページで、組織レベルでアプリをオンまたはオフにすることができます。</span><span class="sxs-lookup"><span data-stu-id="cfe5b-128">You can turn off or turn on the app at the org level on the [Manage apps](../../manage-apps.md) page in the Microsoft Teams admin center.</span></span>

1. <span data-ttu-id="cfe5b-129">Microsoft Teams 管理センターの左のナビゲーションで、[ **Teams アプリ** の管理] に移動  >  **Manage apps** します。</span><span class="sxs-lookup"><span data-stu-id="cfe5b-129">In the left navigation of the Microsoft Teams admin center, go to **Teams apps** > **Manage apps** .</span></span>
2. <span data-ttu-id="cfe5b-130">アプリの一覧で、次のいずれかの操作を行います。</span><span class="sxs-lookup"><span data-stu-id="cfe5b-130">In the list of apps, do one of the following:</span></span>

    - <span data-ttu-id="cfe5b-131">組織のシフトをオフにするには、[シフト] アプリを検索して選択し、[ **ブロック** ] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="cfe5b-131">To turn off Shifts for your organization, search for the Shifts app, select it, and then click **Block** .</span></span>
    - <span data-ttu-id="cfe5b-132">組織のシフトを有効にするには、[シフト] アプリを検索して選択し、[ **許可** ] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="cfe5b-132">To turn on Shifts for your organization, search for the Shifts app, select it, and then click **Allow** .</span></span>

### <a name="enable-or-disable-shifts-for-specific-users-in-your-organization"></a><span data-ttu-id="cfe5b-133">組織内の特定のユーザーのシフトを有効または無効にする</span><span class="sxs-lookup"><span data-stu-id="cfe5b-133">Enable or disable Shifts for specific users in your organization</span></span>

<span data-ttu-id="cfe5b-134">組織内の特定のユーザーによるシフトの使用を許可またはブロックするには、[ [アプリの管理](../../manage-apps.md) ] ページで組織のシフトが有効になっていることを確認してから、カスタムのアプリのアクセス許可ポリシーを作成して、それらのユーザーに割り当てます。</span><span class="sxs-lookup"><span data-stu-id="cfe5b-134">To allow or block specific users in your organization from using Shifts, make sure Shifts is turned on for your organization on the [Manage apps](../../manage-apps.md) page, and then create a custom app permission policy and assign it to those users.</span></span> <span data-ttu-id="cfe5b-135">詳細については、「 [Teams でアプリのアクセス許可ポリシーを管理](../../teams-app-permission-policies.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="cfe5b-135">To learn more, see [Manage app permission policies in Teams](../../teams-app-permission-policies.md).</span></span>

### <a name="use-the-firstlineworker-app-setup-policy-to-pin-shifts-to-teams"></a><span data-ttu-id="cfe5b-136">FirstlineWorker アプリのセットアップポリシーを使用して、チームにシフトをピン留めする</span><span class="sxs-lookup"><span data-stu-id="cfe5b-136">Use the FirstlineWorker app setup policy to pin Shifts to Teams</span></span>

<span data-ttu-id="cfe5b-137">アプリ セットアップ ポリシーを使用すると、組織内のユーザーにとって最も重要なアプリを強調表示するように Teams をカスタマイズできます。</span><span class="sxs-lookup"><span data-stu-id="cfe5b-137">App setup policies let you customize Teams to highlight the apps that are most important for users in your organization.</span></span> <span data-ttu-id="cfe5b-138">ポリシーに設定されたアプリは、アプリ バー (Teams デスクトップ クライアントの横、および Teams モバイル クライアントの一番下にある) にピン留めされ、ユーザーはそこからすばやく簡単にアプリにアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="cfe5b-138">The apps set in a policy are pinned to the app bar&mdash;the bar on the side of the Teams desktop client and at the bottom of the Teams mobile clients&mdash;where users can quickly and easily access them.</span></span>
 
<span data-ttu-id="cfe5b-139">Teams には、組織内の Firstline Worker に割り当てることができる、FirstlineWorker アプリセットアップポリシーが組み込まれています。</span><span class="sxs-lookup"><span data-stu-id="cfe5b-139">Teams includes a built-in FirstlineWorker app setup policy that you can assign to Firstline Workers in your organization.</span></span> <span data-ttu-id="cfe5b-140">既定では、ポリシーにはアクティビティ、シフト、チャット、および通話の各アプリが含まれています。</span><span class="sxs-lookup"><span data-stu-id="cfe5b-140">By default, the policy includes the Activity, Shifts, Chat, and Calling apps.</span></span> 

<span data-ttu-id="cfe5b-141">Firstlineworker ポリシーを表示するには、Microsoft Teams 管理センターの左側のナビゲーションで、[ **Teams アプリ**  >  **アプリセットアップポリシー** ] に移動します。</span><span class="sxs-lookup"><span data-stu-id="cfe5b-141">To view the FirstlineWorker policy, in the left navigation of the Microsoft Teams admin center, go to **Teams app** > **App setup policies** .</span></span>

<span data-ttu-id="cfe5b-142">![FirstlineWorker アプリセットアップポリシーのスクリーンショット](../../media/firstline-worker-app-setup-policy.png "Microsoft Teams 管理センターの FirstlineWorker アプリセットアップポリシーのスクリーンショット")</span><span class="sxs-lookup"><span data-stu-id="cfe5b-142">![Screenshot of the FirstlineWorker app setup policy](../../media/firstline-worker-app-setup-policy.png "Screenshot of the FirstlineWorker app setup policy in the Microsoft Teams admin center")</span></span>

#### <a name="assign-the-firstlineworker-app-setup-policy-to-users"></a><span data-ttu-id="cfe5b-143">FirstLineWorker アプリのセットアップ ポリシーをユーザーに割り当てる</span><span class="sxs-lookup"><span data-stu-id="cfe5b-143">Assign the FirstlineWorker app setup policy to users</span></span>

[!INCLUDE [assign-policy](../../includes/assign-policy.md)]

## <a name="search-the-audit-log-for-shifts-events"></a><span data-ttu-id="cfe5b-144">監査ログでシフトイベントを検索する</span><span class="sxs-lookup"><span data-stu-id="cfe5b-144">Search the audit log for Shifts events</span></span>

<span data-ttu-id="cfe5b-145">**(プレビュー段階)**</span><span class="sxs-lookup"><span data-stu-id="cfe5b-145">**(in preview)**</span></span>

<span data-ttu-id="cfe5b-146">監査ログを検索して、組織内のシフトアクティビティを表示できます。</span><span class="sxs-lookup"><span data-stu-id="cfe5b-146">You can search the audit log to view Shifts activity in your organization.</span></span>  <span data-ttu-id="cfe5b-147">監査ログを検索し、監査ログに記録されている [シフトアクティビティ](../../audit-log-events.md#shifts-in-teams-activities) の一覧を表示する方法の詳細については、「 [Teams のイベントの監査ログを検索](../../audit-log-events.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="cfe5b-147">To learn more about how to search the audit log and to see a list of [Shifts activities](../../audit-log-events.md#shifts-in-teams-activities) that are logged in the audit log, see [Search the audit log for events in Teams](../../audit-log-events.md).</span></span>

<span data-ttu-id="cfe5b-148">監査ログを検索する前に、まず [セキュリティ & コンプライアンスセンター](https://protection.office.com)で監査を有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="cfe5b-148">Before you can search the audit log, you have to first turn on auditing in the [Security & Compliance Center](https://protection.office.com).</span></span> <span data-ttu-id="cfe5b-149">詳細については、「 [監査ログの検索を有効または無効に](https://support.office.com/article/Turn-Office-365-audit-log-search-on-or-off-e893b19a-660c-41f2-9074-d3631c95a014)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="cfe5b-149">To learn more, see [Turn audit log search on or off](https://support.office.com/article/Turn-Office-365-audit-log-search-on-or-off-e893b19a-660c-41f2-9074-d3631c95a014).</span></span> <span data-ttu-id="cfe5b-150">監査データは、監査を有効にした時点でのみ利用可能であることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="cfe5b-150">Keep in mind that audit data is only available from the point at which you turned on auditing.</span></span>

## <a name="related-topics"></a><span data-ttu-id="cfe5b-151">関連項目</span><span class="sxs-lookup"><span data-stu-id="cfe5b-151">Related topics</span></span>

- [<span data-ttu-id="cfe5b-152">Firstline Worker のヘルプをシフトする</span><span class="sxs-lookup"><span data-stu-id="cfe5b-152">Shifts Help for Firstline Workers</span></span>](https://support.office.com/article/apps-and-services-cc1fba57-9900-4634-8306-2360a40c665b)
- [<span data-ttu-id="cfe5b-153">チームのユーザーにポリシーを割り当てる</span><span class="sxs-lookup"><span data-stu-id="cfe5b-153">Assign policies to your users in Teams</span></span>](../../assign-policies.md)
