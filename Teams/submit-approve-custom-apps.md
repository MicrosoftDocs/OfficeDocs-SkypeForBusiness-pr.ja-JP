---
title: Teams アプリの提出 API を使用して、カスタムアプリを申請して承認する
author: lanachin
ms.author: v-lanac
manager: serdars
ms.reviewer: joglocke, vaibhava
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
f1.keywords:
- NOCSH
localization_priority: Normal
search.appverid: MET150
description: Microsoft Teams で Teams アプリ申請 API を使って送信されたカスタムアプリを承認する方法について説明します。
ms.openlocfilehash: 7168a6cf531890a8e942153cc4d214085d6bc63f
ms.sourcegitcommit: 43d66693f6f08d4dcade0095bf613240031fec56
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/06/2020
ms.locfileid: "46583506"
---
# <a name="publish-a-custom-app-submitted-through-the-teams-app-submission-api"></a><span data-ttu-id="00e2c-103">Teams アプリ申請 API を通じて送信されたカスタムアプリを公開する</span><span class="sxs-lookup"><span data-stu-id="00e2c-103">Publish a custom app submitted through the Teams App Submission API</span></span>

## <a name="overview"></a><span data-ttu-id="00e2c-104">概要</span><span class="sxs-lookup"><span data-stu-id="00e2c-104">Overview</span></span>

> [!NOTE]
> <span data-ttu-id="00e2c-105">カスタム Teams アプリを公開すると、組織のアプリストア内のユーザーがそのアプリを利用できるようになります。</span><span class="sxs-lookup"><span data-stu-id="00e2c-105">When you publish a custom Teams app, it's available to users in your organization's app store.</span></span> <span data-ttu-id="00e2c-106">カスタムアプリを公開する方法は2つあります。また、アプリの入手方法によって異なります。</span><span class="sxs-lookup"><span data-stu-id="00e2c-106">There are two ways to publish a custom app and the way that you use depends on how you get the app.</span></span> <span data-ttu-id="00e2c-107">**この記事では、開発者が Teams アプリ申請 API を通じて提出するカスタムアプリを承認および公開する方法について説明**します。</span><span class="sxs-lookup"><span data-stu-id="00e2c-107">**This article focuses on how to approve and publish a custom app that a developer submits through the Teams App Submission API**.</span></span> <span data-ttu-id="00e2c-108">その他の方法として、カスタムアプリをアップロードすることは、開発者が .zip 形式でアプリパッケージを送信するときに使用されます。</span><span class="sxs-lookup"><span data-stu-id="00e2c-108">The other method, uploading a custom app, is used when a developer sends you an app package in .zip format.</span></span> <span data-ttu-id="00e2c-109">このメソッドの詳細については、「<a href="https://docs.microsoft.com/microsoftteams/upload-custom-apps" target="_blank">アプリパッケージをアップロードしてカスタムアプリを公開</a>する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="00e2c-109">To learn more about that method, see <a href="https://docs.microsoft.com/microsoftteams/upload-custom-apps" target="_blank">Publish a custom app by uploading an app package</a>.</span></span>
 
<span data-ttu-id="00e2c-110">この記事では、チームアプリを開発から展開に移動する方法についてのエンドツーエンドのガイダンスについて説明します。</span><span class="sxs-lookup"><span data-stu-id="00e2c-110">This article provides end-to-end guidance for how to take your Teams app from development to deployment to discovery.</span></span> <span data-ttu-id="00e2c-111">チームがアプリのライフサイクルを通じて提供する接続されたエクスペリエンスの概要について説明します。これにより、組織のアプリストアでカスタムアプリを開発、展開、管理する方法が効率化されます。</span><span class="sxs-lookup"><span data-stu-id="00e2c-111">You'll get an overview of the connected experiences that Teams provides across the app lifecycle to streamline how to develop, deploy, and manage custom apps in your organization's app store.</span></span>

<span data-ttu-id="00e2c-112">ここでは、ライフサイクルの各ステップについて説明します。開発者は、確認と承認のために、アプリを管理するためにポリシーを設定する方法、組織内のユーザーを管理するためのポリシーを設定する方法、ユーザーが Teams でそれらを見つける方法についても説明します。</span><span class="sxs-lookup"><span data-stu-id="00e2c-112">We'll cover each step of the lifecycle, including how developers can use the Teams App Submission API to submit custom apps directly to the Microsoft Teams admin center for you to review and approve, how to set policies to manage apps for users in your organization, and how your users discover them in Teams.</span></span>

![開発から展開までのアプリの概要](media/custom-app-lifecycle.png)

<span data-ttu-id="00e2c-114">このガイダンスは、アプリの Teams の側面を中心としており、管理者と IT プロフェッショナルを対象としています。</span><span class="sxs-lookup"><span data-stu-id="00e2c-114">This guidance focuses on the Teams aspects of the app and is intended for admins and IT pros.</span></span> <span data-ttu-id="00e2c-115">Teams アプリの開発について詳しくは、 <a href="https://docs.microsoft.com/microsoftteams/platform" target="_blank">teams の開発者向けドキュメント</a>をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="00e2c-115">For information about developing Teams apps, see the <a href="https://docs.microsoft.com/microsoftteams/platform" target="_blank">Teams developer documentation</a>.</span></span>

## <a name="develop"></a><span data-ttu-id="00e2c-116">開発</span><span class="sxs-lookup"><span data-stu-id="00e2c-116">Develop</span></span>

### <a name="create-the-app"></a><span data-ttu-id="00e2c-117">アプリを作成する</span><span class="sxs-lookup"><span data-stu-id="00e2c-117">Create the app</span></span>

<span data-ttu-id="00e2c-118">Microsoft Teams の開発者は、開発者が独自のアプリとサービスを統合して生産性を向上させ、意思決定を迅速化し、既存のコンテンツとワークフローを取り巻くコラボレーションを作成することが容易になります。</span><span class="sxs-lookup"><span data-stu-id="00e2c-118">The Microsoft Teams developer platform makes it easy for developers to integrate your own apps and services to improve productivity, make decisions faster, and create collaboration around existing content and workflows.</span></span> <span data-ttu-id="00e2c-119">Teams プラットフォームで構築されたアプリは、Teams クライアントとサービスとワークフローの間のブリッジであり、コラボレーションプラットフォームのコンテキストに直接移行します。</span><span class="sxs-lookup"><span data-stu-id="00e2c-119">Apps built on the Teams platform are bridges between the Teams client and your services and workflows, bringing them directly into the context of your collaboration platform.</span></span> <span data-ttu-id="00e2c-120">詳細については、「 <a href="https://docs.microsoft.com/microsoftteams/platform" target="_blank">Teams の開発者向けドキュメント</a>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="00e2c-120">For more information, go to the <a href="https://docs.microsoft.com/microsoftteams/platform" target="_blank">Teams developer documentation</a>.</span></span>

### <a name="submit-the-app"></a><span data-ttu-id="00e2c-121">アプリを申請する</span><span class="sxs-lookup"><span data-stu-id="00e2c-121">Submit the app</span></span>

<span data-ttu-id="00e2c-122">アプリを運用環境で使用する準備ができたら、開発者は、Graph API、Visual Studio コードなどの統合開発環境 (IDE)、または Power Apps や Power Virtual Agent などのプラットフォームから呼び出すことができる Teams アプリ申請 API を使ってアプリを申請できます。</span><span class="sxs-lookup"><span data-stu-id="00e2c-122">When the app is ready for use in production, the developer can submit the app using the Teams App Submission API, which can be called from Graph API, an integrated development environment (IDE) such as Visual Studio Code, or a platform such as Power Apps and Power Virtual Agents.</span></span> <span data-ttu-id="00e2c-123">これにより、アプリは Microsoft Teams 管理センターの [<a href="https://docs.microsoft.com/microsoftteams/manage-apps" target="_blank">アプリの管理</a>] ページで利用できるようになります。ここでは、管理者がレビューして承認することができます。</span><span class="sxs-lookup"><span data-stu-id="00e2c-123">Doing this makes the app available on the <a href="https://docs.microsoft.com/microsoftteams/manage-apps" target="_blank">Manage apps</a> page of the Microsoft Teams admin center, where you, the admin, can review and approve it.this</span></span> 

<span data-ttu-id="00e2c-124">Microsoft Graph 上に構築された Teams アプリ申請 API を使用すると、お客様が選択したプラットフォームで組織を開発し、チームのカスタムアプリの申請申請書を自動化できます。</span><span class="sxs-lookup"><span data-stu-id="00e2c-124">The Teams App Submission API, built on Microsoft Graph, allows your organization to develop on the platform of your choice and automates the submission-to-approval process for custom apps on Teams.</span></span>

<span data-ttu-id="00e2c-125">Visual Studio コードのこのアプリの申請手順の例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="00e2c-125">Here's an example of what this app submission step looks like in Visual Studio Code:</span></span>

![Visual Studio コードでのアプリの提出のスクリーンショット](media/custom-app-lifecycle-submit-app.png)

<span data-ttu-id="00e2c-127">これにより、アプリは組織のアプリストアに公開されないことに注意してください。</span><span class="sxs-lookup"><span data-stu-id="00e2c-127">Keep in mind that this doesn't publish the app to your organization's app store yet.</span></span> <span data-ttu-id="00e2c-128">この手順によって、アプリは Microsoft Teams 管理センターに送信され、組織のアプリストアへの発行を承認することができます。</span><span class="sxs-lookup"><span data-stu-id="00e2c-128">This step submits the app to the Microsoft Teams admin center where you can approve it for publishing to your organization's app store.</span></span>

## <a name="validate"></a><span data-ttu-id="00e2c-129">有効性</span><span class="sxs-lookup"><span data-stu-id="00e2c-129">Validate</span></span>

<span data-ttu-id="00e2c-130">Microsoft Teams 管理センターの [<a href="https://docs.microsoft.com/microsoftteams/manage-apps" target="_blank">アプリの管理</a>] ページ (左側のナビゲーションで、[ **Teams アプリ**の管理]) に移動して  >  **Manage apps**、組織のすべての teams アプリを表示することができます。</span><span class="sxs-lookup"><span data-stu-id="00e2c-130">The <a href="https://docs.microsoft.com/microsoftteams/manage-apps" target="_blank">Manage apps</a> page in the Microsoft Teams admin center (in the left navigation, go to **Teams apps** > **Manage apps**), gives you a view into all Teams apps for your organization.</span></span> <span data-ttu-id="00e2c-131">ページの上部にある [**保留中] 承認**ウィジェットを使用すると、ユーザー設定のアプリが承認のために送信された場合に通知を受けることができます。</span><span class="sxs-lookup"><span data-stu-id="00e2c-131">The **Pending approval** widget at the top of the page lets you know when a custom app is submitted for approval.</span></span>

<span data-ttu-id="00e2c-132">表では、新しく送信されたアプリには、**送信\*\*\*\*状態**と**ブロック\*\*\*\*状態**が自動的に表示されます。</span><span class="sxs-lookup"><span data-stu-id="00e2c-132">In the table, a newly submitted app automatically shows a **Publishing status** of **Submitted** and **Status** of **Blocked**.</span></span> <span data-ttu-id="00e2c-133">アプリをすばやく見つけるために、[**発行の状態**」列を降順で並べ替えることができます。</span><span class="sxs-lookup"><span data-stu-id="00e2c-133">You can sort the **Publishing status** column in descending order to quickly find the app.</span></span>

![<span data-ttu-id="00e2c-134">保留中の要求とアプリの状態を示す [アプリの管理] ページのスクリーンショット</span><span class="sxs-lookup"><span data-stu-id="00e2c-134">Screenshot of Manage apps page showing pending requests and app status</span></span> ](media/custom-app-lifecycle-validate-app.png)

<span data-ttu-id="00e2c-135">アプリ名をクリックして、[アプリの詳細] ページに移動します。</span><span class="sxs-lookup"><span data-stu-id="00e2c-135">Click the app name to go to the app details page.</span></span> <span data-ttu-id="00e2c-136">[**バージョン情報**] タブには、説明、状態、送信者、アプリ ID など、アプリに関する詳細が表示されます。</span><span class="sxs-lookup"><span data-stu-id="00e2c-136">On the **About** tab, you can view details about the app, including description, status, submitter, and app ID.</span></span>

![送信されたアプリのアプリの詳細ページのスクリーンショット](media/custom-app-lifecycle-app-details.png)

## <a name="publish"></a><span data-ttu-id="00e2c-138">出版</span><span class="sxs-lookup"><span data-stu-id="00e2c-138">Publish</span></span>

<span data-ttu-id="00e2c-139">アプリをユーザーが利用できるようにする準備ができたら、アプリを公開します。</span><span class="sxs-lookup"><span data-stu-id="00e2c-139">When you're ready to make the app available to users, publish the app.</span></span>

1. <span data-ttu-id="00e2c-140">Microsoft Teams 管理センターの左のナビゲーションで、[ **Teams アプリ**の管理] に移動  >  **Manage apps**します。</span><span class="sxs-lookup"><span data-stu-id="00e2c-140">In the left navigation of the Microsoft Teams admin center, go to **Teams apps** > **Manage apps**.</span></span>
2. <span data-ttu-id="00e2c-141">アプリ名をクリックして [アプリの詳細] ページに移動し、[**発行の状態**] ボックスで [**発行**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="00e2c-141">Click the app name to go to the app details page, and then in the **Publishing status** box, select **Publish**.</span></span>

    <span data-ttu-id="00e2c-142">アプリを公開すると、**発行の状態**が [**公開済み**] に変わり、**状態**が [許可] に自動的に変更**さ**れます。</span><span class="sxs-lookup"><span data-stu-id="00e2c-142">After you publish the app, the **Publishing status** changes to **Published** and the **Status** automatically changes to **Allowed**.</span></span>

## <a name="set-up-and-manage"></a><span data-ttu-id="00e2c-143">設定と管理</span><span class="sxs-lookup"><span data-stu-id="00e2c-143">Set up and manage</span></span>

### <a name="control-access-to-the-app"></a><span data-ttu-id="00e2c-144">アプリへのアクセスを制御する</span><span class="sxs-lookup"><span data-stu-id="00e2c-144">Control access to the app</span></span>

<span data-ttu-id="00e2c-145">既定では、組織内のすべてのユーザーが、組織のアプリストアのアプリにアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="00e2c-145">By default, all users in your organization can access the app in your organization's app store.</span></span> <span data-ttu-id="00e2c-146">アプリを使う権限を持つユーザーを制限および制御するには、アプリのアクセス許可ポリシーを作成して割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="00e2c-146">To restrict and control who has permission to use the app, you can create and assign an app permission policy.</span></span> <span data-ttu-id="00e2c-147">詳細については、「 <a href="https://docs.microsoft.com/microsoftteams/teams-app-permission-policies" target="_blank">Teams でアプリのアクセス許可ポリシーを管理</a>する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="00e2c-147">To learn more, see <a href="https://docs.microsoft.com/microsoftteams/teams-app-permission-policies" target="_blank">Manage app permission policies in Teams</a>.</span></span>

### <a name="pin-and-install-the-app-for-users-to-discover"></a><span data-ttu-id="00e2c-148">ユーザーが検出できるようにアプリを固定してインストールする</span><span class="sxs-lookup"><span data-stu-id="00e2c-148">Pin and install the app for users to discover</span></span>

<span data-ttu-id="00e2c-149">既定では、ユーザーがアプリを見つけるには、組織のアプリストアに移動し、それを参照または検索する必要があります。</span><span class="sxs-lookup"><span data-stu-id="00e2c-149">By default, for users to find the app they have to go to your organization's app store and browse or search for it.</span></span> <span data-ttu-id="00e2c-150">ユーザーがアプリを簡単に利用できるようにするために、アプリを Teams のアプリバーにピン留めすることができます。</span><span class="sxs-lookup"><span data-stu-id="00e2c-150">To make it easy for users to get to the app, you can pin the app to the app bar in Teams.</span></span> <span data-ttu-id="00e2c-151">これを行うには、アプリのセットアップポリシーを作成し、ユーザーに割り当てます。</span><span class="sxs-lookup"><span data-stu-id="00e2c-151">To do this, create an app setup policy and assign it to users.</span></span> <span data-ttu-id="00e2c-152">詳細については、「 <a href="https://docs.microsoft.com/microsoftteams/teams-app-setup-policies" target="_blank">Teams でアプリセットアップポリシーを管理</a>する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="00e2c-152">To learn more, see <a href="https://docs.microsoft.com/microsoftteams/teams-app-setup-policies" target="_blank">Manage app setup policies in Teams</a>.</span></span>

### <a name="search-the-audit-log-for-teams-app-events"></a><span data-ttu-id="00e2c-153">チームアプリイベントの監査ログを検索する</span><span class="sxs-lookup"><span data-stu-id="00e2c-153">Search the audit log for Teams app events</span></span>

<span data-ttu-id="00e2c-154">監査ログを検索して、組織内の Teams アプリのアクティビティを表示できます。</span><span class="sxs-lookup"><span data-stu-id="00e2c-154">You can search the audit log to view Teams apps activity in your organization.</span></span> <span data-ttu-id="00e2c-155">監査ログを検索し、監査ログに記録されている Teams アクティビティの一覧を表示する方法の詳細については、「 <a href="https://docs.microsoft.com/microsoftteams/audit-log-events" target="_blank">Teams のイベントの監査ログを検索</a>する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="00e2c-155">To learn more about how to search the audit log and to see a list of Teams activities that are logged in the audit log, see <a href="https://docs.microsoft.com/microsoftteams/audit-log-events" target="_blank">Search the audit log for events in Teams</a>.</span></span>

<span data-ttu-id="00e2c-156">監査ログを検索する前に、まず<a href="https://protection.office.com" target="_blank">セキュリティ & コンプライアンスセンター</a>で監査を有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="00e2c-156">Before you can search the audit log, you have to first turn on auditing in the <a href="https://protection.office.com" target="_blank">Security & Compliance Center</a>.</span></span> <span data-ttu-id="00e2c-157">詳細については、「<a href="https://support.office.com/article/Turn-Office-365-audit-log-search-on-or-off-e893b19a-660c-41f2-9074-d3631c95a014" target="_blank">監査ログの検索を有効または無効に</a>する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="00e2c-157">To learn more, see <a href="https://support.office.com/article/Turn-Office-365-audit-log-search-on-or-off-e893b19a-660c-41f2-9074-d3631c95a014" target="_blank">Turn audit log search on or off</a>.</span></span> <span data-ttu-id="00e2c-158">監査データは、監査を有効にした時点でのみ利用可能であることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="00e2c-158">Keep in mind that audit data is only available from the point at which you turned on auditing.</span></span>

## <a name="discover-and-adopt"></a><span data-ttu-id="00e2c-159">発見と採用</span><span class="sxs-lookup"><span data-stu-id="00e2c-159">Discover and adopt</span></span>

<span data-ttu-id="00e2c-160">アプリへのアクセス許可を持つユーザーは、そのアプリを組織のアプリストアで見つけることができます。</span><span class="sxs-lookup"><span data-stu-id="00e2c-160">Users who have permissions to the app can find it in your organization's app store.</span></span> <span data-ttu-id="00e2c-161">[アプリ] ページで [ \***組織名に合わせ\*て作成**済み] に移動して、組織のカスタムアプリを見つけます。</span><span class="sxs-lookup"><span data-stu-id="00e2c-161">Go to **Built for *Your Organization Name*** on the Apps page to find your organization's custom apps.</span></span>

![<span data-ttu-id="00e2c-162">公開されたアプリが表示されている [アプリ] ページのスクリーンショット</span><span class="sxs-lookup"><span data-stu-id="00e2c-162">Screenshot of Apps page showing published app</span></span> ](media/custom-app-lifecycle-discovery.png)

<span data-ttu-id="00e2c-163">アプリのセットアップポリシーを作成して割り当てた場合、アプリは、ポリシーが割り当てられたユーザーに対して簡単にアクセスできるように、Teams のアプリバーに固定されます。</span><span class="sxs-lookup"><span data-stu-id="00e2c-163">If you created and assigned an app setup policy, the app is pinned to the app bar in Teams for easy access for those users who were assigned the policy.</span></span>

## <a name="update"></a><span data-ttu-id="00e2c-164">更新する</span><span class="sxs-lookup"><span data-stu-id="00e2c-164">Update</span></span>

<span data-ttu-id="00e2c-165">アプリを更新するには、開発者は「[開発](#develop)」セクションの手順に従って続行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="00e2c-165">To update an app, developers should continue to follow the steps in the [Develop](#develop) section.</span></span>

<span data-ttu-id="00e2c-166">開発者が公開されたカスタムアプリへの更新を送信すると、[<a href="https://docs.microsoft.com/microsoftteams/manage-apps" target="_blank">アプリの管理</a>] ページの [**保留中の承認**ウィジェット] に通知が表示されます。</span><span class="sxs-lookup"><span data-stu-id="00e2c-166">When the developer submits an update to a published custom app, you'll get notified in the **Pending approval** widget of the <a href="https://docs.microsoft.com/microsoftteams/manage-apps" target="_blank">Manage apps</a> page.</span></span> <span data-ttu-id="00e2c-167">表では、アプリの**発行の状態**が [**更新送信**済み] に設定されます。</span><span class="sxs-lookup"><span data-stu-id="00e2c-167">In the table, the **Publishing status** of the app will be set to **Update submitted**.</span></span>

![<span data-ttu-id="00e2c-168">保留中の要求とアプリの状態を示す [アプリの管理] ページのスクリーンショット</span><span class="sxs-lookup"><span data-stu-id="00e2c-168">Screenshot of Manage apps page showing pending requests and app status</span></span> ](media/custom-app-lifecycle-update-submitted.png)

<span data-ttu-id="00e2c-169">アプリの更新を確認して公開するには、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="00e2c-169">To review and publish an app update:</span></span>

1. <span data-ttu-id="00e2c-170">Microsoft Teams 管理センターの左のナビゲーションで、[ **Teams アプリ**の管理] に移動  >  **Manage apps**します。</span><span class="sxs-lookup"><span data-stu-id="00e2c-170">In the left navigation of the Microsoft Teams admin center, go to **Teams apps** > **Manage apps**.</span></span>
2. <span data-ttu-id="00e2c-171">アプリ名をクリックして [アプリの詳細] ページに移動し、[**利用可能な更新**] を選択して、更新プログラムの詳細を確認します。</span><span class="sxs-lookup"><span data-stu-id="00e2c-171">Click the app name to go to the app details page, and then select **Update available** to review details of the update.</span></span>

    ![<span data-ttu-id="00e2c-172">保留中の要求とアプリの状態を示す [アプリの管理] ページのスクリーンショット</span><span class="sxs-lookup"><span data-stu-id="00e2c-172">Screenshot of Manage apps page showing pending requests and app status</span></span> ](media/custom-app-lifecycle-update-app.png)
3. <span data-ttu-id="00e2c-173">準備ができたら、[**発行**] を選択して更新を公開します。</span><span class="sxs-lookup"><span data-stu-id="00e2c-173">When you're ready, select **Publish** to publish the update.</span></span> <span data-ttu-id="00e2c-174">この操作を行うと、既存のアプリが置き換えられ、バージョン番号が更新され、**発行の状態**が [**公開済み**] に変わります。</span><span class="sxs-lookup"><span data-stu-id="00e2c-174">Doing this replaces the existing app, updates the version number, and changes the **Publishing status** to **Published**.</span></span> <span data-ttu-id="00e2c-175">更新されたアプリには、すべてのアプリのアクセス許可ポリシーとアプリのセットアップポリシーが適用されます。</span><span class="sxs-lookup"><span data-stu-id="00e2c-175">All app permission policies and app setup policies remain enforced for the updated app.</span></span>

    <span data-ttu-id="00e2c-176">更新プログラムを拒否した場合、以前のバージョンのアプリは公開されたままになります。</span><span class="sxs-lookup"><span data-stu-id="00e2c-176">If you reject the update, the earlier version of the app remains published.</span></span>

<span data-ttu-id="00e2c-177">次の点に注意してください。</span><span class="sxs-lookup"><span data-stu-id="00e2c-177">Keep in mind the following:</span></span>

- <span data-ttu-id="00e2c-178">アプリが承認されると、アプリに更新プログラムを送信できます。</span><span class="sxs-lookup"><span data-stu-id="00e2c-178">When an app is approved, any one can submit an update to the app.</span></span> <span data-ttu-id="00e2c-179">これは、アプリを最初に提出した開発者を含め、他の開発者がアプリに更新プログラムを提出できることを意味します。</span><span class="sxs-lookup"><span data-stu-id="00e2c-179">This means other developers, including the developer who originally submitted the app, can submit an update to the app.</span></span>
- <span data-ttu-id="00e2c-180">開発者がアプリを送信したときに要求が保留になっている場合、その開発者だけがアプリに更新を送信できます。</span><span class="sxs-lookup"><span data-stu-id="00e2c-180">When a developer submits an app and the request is pending, only that same developer can submit an update to the app.</span></span> <span data-ttu-id="00e2c-181">他の開発者は、アプリが承認された後にのみ更新プログラムを送信できます。</span><span class="sxs-lookup"><span data-stu-id="00e2c-181">Other developers can submit an update only after the app is approved.</span></span>

### <a name="update-experience-for-users"></a><span data-ttu-id="00e2c-182">ユーザー向けの更新エクスペリエンス</span><span class="sxs-lookup"><span data-stu-id="00e2c-182">Update experience for users</span></span>

<span data-ttu-id="00e2c-183">ほとんどの場合、アプリの更新プログラムを公開すると、新しいバージョンが自動的にユーザーに表示されます。</span><span class="sxs-lookup"><span data-stu-id="00e2c-183">In most cases, after you publish an app update, the new version automatically appears for users.</span></span> <span data-ttu-id="00e2c-184">ただし、 <a href="https://docs.microsoft.com/microsoftteams/platform/resources/schema/manifest-schema" target="_blank">Microsoft Teams マニフェスト</a>には、ユーザーの承認を必要とする次のような更新があります。</span><span class="sxs-lookup"><span data-stu-id="00e2c-184">However, there are some updates to the <a href="https://docs.microsoft.com/microsoftteams/platform/resources/schema/manifest-schema" target="_blank">Microsoft Teams manifest</a> that require user acceptance to complete:</span></span>

* <span data-ttu-id="00e2c-185">ボットが追加または削除された</span><span class="sxs-lookup"><span data-stu-id="00e2c-185">A bot was added or removed</span></span>
* <span data-ttu-id="00e2c-186">既存のボットの "botId" プロパティが変更されました</span><span class="sxs-lookup"><span data-stu-id="00e2c-186">An existing bot's "botId" property changed</span></span>
* <span data-ttu-id="00e2c-187">既存のボットの "isNotificationOnly" プロパティが変更されました</span><span class="sxs-lookup"><span data-stu-id="00e2c-187">An existing bot's "isNotificationOnly" property changed</span></span>
* <span data-ttu-id="00e2c-188">ボットの "supportsFiles" プロパティが変更されました</span><span class="sxs-lookup"><span data-stu-id="00e2c-188">The bot's "supportsFiles" property changed</span></span>
* <span data-ttu-id="00e2c-189">メッセージング拡張機能が追加または削除されました</span><span class="sxs-lookup"><span data-stu-id="00e2c-189">A messaging extension was added or removed</span></span>
* <span data-ttu-id="00e2c-190">新しいコネクタが追加されました</span><span class="sxs-lookup"><span data-stu-id="00e2c-190">A new connector was added</span></span>
* <span data-ttu-id="00e2c-191">新しい静的タブが追加されました</span><span class="sxs-lookup"><span data-stu-id="00e2c-191">A new static tab was added</span></span>
* <span data-ttu-id="00e2c-192">新しい [構成可能] タブが追加されました</span><span class="sxs-lookup"><span data-stu-id="00e2c-192">A new configurable tab was added</span></span>
* <span data-ttu-id="00e2c-193">"WebApplicationInfo" 内のプロパティが変更されました</span><span class="sxs-lookup"><span data-stu-id="00e2c-193">Properties inside "webApplicationInfo" changed</span></span>

![新しいバージョンが使用可能なアプリを示すスクリーンショット](media/manage-your-custom-apps-update1.png)

![アプリのアップグレードオプションのスクリーンショット](media/manage-your-custom-apps-update2.png)

## <a name="related-topics"></a><span data-ttu-id="00e2c-196">関連トピック</span><span class="sxs-lookup"><span data-stu-id="00e2c-196">Related topics</span></span>

- [<span data-ttu-id="00e2c-197">アプリパッケージをアップロードしてカスタムアプリを公開する</span><span class="sxs-lookup"><span data-stu-id="00e2c-197">Publish a custom app by uploading an app package</span></span>](upload-custom-apps.md)
- [<span data-ttu-id="00e2c-198">Microsoft Teams 管理センターでアプリを管理する</span><span class="sxs-lookup"><span data-stu-id="00e2c-198">Manage your apps in the Microsoft Teams admin center</span></span>](manage-apps.md)
- [<span data-ttu-id="00e2c-199">Teams のカスタム アプリのポリシーと設定を管理する</span><span class="sxs-lookup"><span data-stu-id="00e2c-199">Manage custom app policies and settings in Teams</span></span>](teams-custom-app-policies-and-settings.md)
- [<span data-ttu-id="00e2c-200">Teams のアプリのアクセス許可ポリシーを管理する</span><span class="sxs-lookup"><span data-stu-id="00e2c-200">Manage app permission policies in Teams</span></span>](teams-app-permission-policies.md)
- [<span data-ttu-id="00e2c-201">Teams のアプリのセットアップ ポリシーを管理する</span><span class="sxs-lookup"><span data-stu-id="00e2c-201">Manage app setup policies in Teams</span></span>](teams-app-setup-policies.md)
