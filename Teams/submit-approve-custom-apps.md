---
title: Teams アプリ申請 API を使用してカスタム アプリを送信および承認する
author: cichur
ms.author: v-cichur
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
description: Teams App Submission API を使用して送信されるカスタム アプリを承認する方法についてMicrosoft Teams。
ms.openlocfilehash: e544fdc12e17fc8917a2d3b9ce01dfc5985261de
ms.sourcegitcommit: 40f76bc6b5e304faea8516a78f8576ba1cdb7f7c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/12/2021
ms.locfileid: "52337794"
---
# <a name="publish-a-custom-app-submitted-through-the-teams-app-submission-api"></a><span data-ttu-id="4747e-103">Teams App Submission API を使用して送信されたカスタム アプリを発行する</span><span class="sxs-lookup"><span data-stu-id="4747e-103">Publish a custom app submitted through the Teams App Submission API</span></span>

## <a name="overview"></a><span data-ttu-id="4747e-104">概要</span><span class="sxs-lookup"><span data-stu-id="4747e-104">Overview</span></span>

> [!NOTE]
> <span data-ttu-id="4747e-105">カスタム アプリを発行Teams、組織のアプリ ストア内のユーザーが使用できます。</span><span class="sxs-lookup"><span data-stu-id="4747e-105">When you publish a custom Teams app, it's available to users in your organization's app store.</span></span> <span data-ttu-id="4747e-106">カスタム アプリを発行する方法と使用する方法は、アプリの取得方法によって異なります。</span><span class="sxs-lookup"><span data-stu-id="4747e-106">There are two ways to publish a custom app and the way that you use depends on how you get the app.</span></span> <span data-ttu-id="4747e-107">この記事では、開発者がアプリ提出 API を使用して送信するカスタム アプリを承認して発行するTeams **を中心に説明します**。</span><span class="sxs-lookup"><span data-stu-id="4747e-107">**This article focuses on how to approve and publish a custom app that a developer submits through the Teams App Submission API**.</span></span> <span data-ttu-id="4747e-108">カスタム アプリをアップロードするもう 1 つの方法は、開発者がアプリ パッケージをカスタム 形式で.zipされます。</span><span class="sxs-lookup"><span data-stu-id="4747e-108">The other method, uploading a custom app, is used when a developer sends you an app package in .zip format.</span></span> <span data-ttu-id="4747e-109">その方法の詳細については、「アプリ パッケージをアップロードして <a href="/microsoftteams/upload-custom-apps" target="_blank">カスタム アプリを発行する」を参照してください</a>。</span><span class="sxs-lookup"><span data-stu-id="4747e-109">To learn more about that method, see <a href="/microsoftteams/upload-custom-apps" target="_blank">Publish a custom app by uploading an app package</a>.</span></span> <span data-ttu-id="4747e-110">承認アプリ ウィジェットは、テナントGCCできません。</span><span class="sxs-lookup"><span data-stu-id="4747e-110">The approve app widget isn't available in GCC tenants.</span></span> 

> [!IMPORTANT]
> <span data-ttu-id="4747e-111">この方法は現在、一部の環境GCCできません。</span><span class="sxs-lookup"><span data-stu-id="4747e-111">This method is not currently available for GCC environments.</span></span> <span data-ttu-id="4747e-112">カスタム アプリ メソッドの *アップロードを使用する必要* があります。</span><span class="sxs-lookup"><span data-stu-id="4747e-112">You must use the *uploading a custom app* method.</span></span>

<span data-ttu-id="4747e-113">この記事では、開発からデプロイから検出まで、Teamsアプリを使用する方法について、エンド to エンドのガイダンスを提供します。</span><span class="sxs-lookup"><span data-stu-id="4747e-113">This article provides end-to-end guidance for how to take your Teams app from development to deployment to discovery.</span></span> <span data-ttu-id="4747e-114">Teams がアプリのライフサイクル全体にわたって提供する接続エクスペリエンスの概要を確認し、組織のアプリ ストアでカスタム アプリを開発、デプロイ、管理する方法を合理化します。</span><span class="sxs-lookup"><span data-stu-id="4747e-114">You'll get an overview of the connected experiences that Teams provides across the app lifecycle to streamline how to develop, deploy, and manage custom apps in your organization's app store.</span></span>

<span data-ttu-id="4747e-115">ライフサイクルの各ステップについて説明します。たとえば、開発者が Teams App Submission API を使用してカスタム アプリを Microsoft Teams 管理センターに直接送信してレビューと承認を行う方法、組織内のユーザー向けのアプリを管理するためのポリシーを設定する方法、ユーザーが Teams でアプリを検出する方法などについて説明します。</span><span class="sxs-lookup"><span data-stu-id="4747e-115">We'll cover each step of the lifecycle, including how developers can use the Teams App Submission API to submit custom apps directly to the Microsoft Teams admin center for you to review and approve, how to set policies to manage apps for users in your organization, and how your users discover them in Teams.</span></span>

![開発からデプロイまで、アプリの概要](media/custom-app-lifecycle.png)

<span data-ttu-id="4747e-117">このガイダンスでは、アプリのTeamsに焦点を当て、管理者と IT のプロを対象にしています。</span><span class="sxs-lookup"><span data-stu-id="4747e-117">This guidance focuses on the Teams aspects of the app and is intended for admins and IT pros.</span></span> <span data-ttu-id="4747e-118">アプリの開発の詳細についてはTeams開発者向けドキュメント<a href="/microsoftteams/platform" target="_blank">をTeams参照してください</a>。</span><span class="sxs-lookup"><span data-stu-id="4747e-118">For information about developing Teams apps, see the <a href="/microsoftteams/platform" target="_blank">Teams developer documentation</a>.</span></span>

## <a name="develop"></a><span data-ttu-id="4747e-119">開発</span><span class="sxs-lookup"><span data-stu-id="4747e-119">Develop</span></span>

### <a name="create-the-app"></a><span data-ttu-id="4747e-120">アプリを作成する</span><span class="sxs-lookup"><span data-stu-id="4747e-120">Create the app</span></span>

<span data-ttu-id="4747e-121">開発者Microsoft Teamsプラットフォームを使用すると、開発者は独自のアプリとサービスを簡単に統合して生産性を向上させ、意思決定を迅速に行い、既存のコンテンツやワークフローに関するコラボレーションを作成できます。</span><span class="sxs-lookup"><span data-stu-id="4747e-121">The Microsoft Teams developer platform makes it easy for developers to integrate your own apps and services to improve productivity, make decisions faster, and create collaboration around existing content and workflows.</span></span> <span data-ttu-id="4747e-122">Teams プラットフォーム上に構築されたアプリは、Teams クライアントとサービスとワークフローの間のブリッジであり、コラボレーション プラットフォームのコンテキストに直接取り込む必要があります。</span><span class="sxs-lookup"><span data-stu-id="4747e-122">Apps built on the Teams platform are bridges between the Teams client and your services and workflows, bringing them directly into the context of your collaboration platform.</span></span> <span data-ttu-id="4747e-123">詳細については、開発者向けドキュメント<a href="/microsoftteams/platform" target="_blank">Teams参照してください</a>。</span><span class="sxs-lookup"><span data-stu-id="4747e-123">For more information, go to the <a href="/microsoftteams/platform" target="_blank">Teams developer documentation</a>.</span></span>

### <a name="submit-the-app"></a><span data-ttu-id="4747e-124">アプリを送信する</span><span class="sxs-lookup"><span data-stu-id="4747e-124">Submit the app</span></span>

<span data-ttu-id="4747e-125">アプリを実稼働環境で使用する準備ができたら、開発者は<a href="https://docs.microsoft.com/graph/api/teamsapp-publish?view=graph-rest-beta&tabs=http#example-2-upload-a-new-application-for-review-to-an-organizations-app-catalog" target="_blank" target="_blank">Graph API、Visual Studio Code</a>などの統合された開発環境 (IDE)、または Power Apps や Power Virtual Agents などのプラットフォームから呼び出し可能な Teams アプリ送信 API を使用してアプリを送信できます。</span><span class="sxs-lookup"><span data-stu-id="4747e-125">When the app is ready for use in production, the developer can submit the app using the Teams App Submission API, which can be called from <a href="https://docs.microsoft.com/graph/api/teamsapp-publish?view=graph-rest-beta&tabs=http#example-2-upload-a-new-application-for-review-to-an-organizations-app-catalog" target="_blank" target="_blank">Graph API</a>, an integrated development environment (IDE) such as Visual Studio Code, or a platform such as Power Apps and Power Virtual Agents.</span></span> <span data-ttu-id="4747e-126">これにより、管理者は Microsoft Teams 管理<a href="/microsoftteams/manage-apps" target="_blank"></a>センターの [アプリの管理] ページでアプリを利用できます。このページでは、管理者がアプリを確認および承認できます。</span><span class="sxs-lookup"><span data-stu-id="4747e-126">Doing this makes the app available on the <a href="/microsoftteams/manage-apps" target="_blank">Manage apps</a> page of the Microsoft Teams admin center, where you, the admin, can review and approve it.this</span></span>

<span data-ttu-id="4747e-127"><a href="/graph/api/teamsapp-publish?tabs=http&view=graph-rest-beta#example-2-upload-a-new-application-for-review-to-an-organizations-app-catalog" target="_blank">Microsoft Graph</a>上に構築された Teams App Submission API を使用すると、組織は選択したプラットフォーム上で開発し、Teams 上のカスタム アプリの提出から承認へのプロセスを自動化できます。</span><span class="sxs-lookup"><span data-stu-id="4747e-127">The Teams App Submission API, <a href="/graph/api/teamsapp-publish?tabs=http&view=graph-rest-beta#example-2-upload-a-new-application-for-review-to-an-organizations-app-catalog" target="_blank">built on Microsoft Graph</a>, allows your organization to develop on the platform of your choice and automates the submission-to-approval process for custom apps on Teams.</span></span>

<span data-ttu-id="4747e-128">このアプリの提出手順の例を次に示Visual Studio Code。</span><span class="sxs-lookup"><span data-stu-id="4747e-128">Here's an example of what this app submission step looks like in Visual Studio Code:</span></span>

![Visual Studio Code でアプリを送信する](media/custom-app-lifecycle-submit-app.png)

<span data-ttu-id="4747e-130">これにより、組織のアプリ ストアにアプリがまだ発行されていないことに気を付ける必要があります。</span><span class="sxs-lookup"><span data-stu-id="4747e-130">Keep in mind that this doesn't publish the app to your organization's app store yet.</span></span> <span data-ttu-id="4747e-131">この手順では、アプリを Microsoft Teams 管理センターに送信し、組織のアプリ ストアへの発行を承認できます。</span><span class="sxs-lookup"><span data-stu-id="4747e-131">This step submits the app to the Microsoft Teams admin center where you can approve it for publishing to your organization's app store.</span></span>

<span data-ttu-id="4747e-132">Graph API を使用してアプリを送信する方法の詳細については、こちらを参照<a href="/graph/api/teamsapp-publish?tabs=http&view=graph-rest-beta#example-2-upload-a-new-application-for-review-to-an-organizations-app-catalog" target="_blank">してください</a>。</span><span class="sxs-lookup"><span data-stu-id="4747e-132">For more information about using the Graph API to submit apps, see <a href="/graph/api/teamsapp-publish?tabs=http&view=graph-rest-beta#example-2-upload-a-new-application-for-review-to-an-organizations-app-catalog" target="_blank">here</a>.</span></span>

## <a name="validate"></a><span data-ttu-id="4747e-133">検証</span><span class="sxs-lookup"><span data-stu-id="4747e-133">Validate</span></span>

<span data-ttu-id="4747e-134">Microsoft Teams <a href="/microsoftteams/manage-apps" target="_blank"></a>管理センターの [アプリの管理] ページ (左側のナビゲーションの [Teams **アプリの** 管理] に移動します)、組織のすべての Teams アプリを  >  表示します。</span><span class="sxs-lookup"><span data-stu-id="4747e-134">The <a href="/microsoftteams/manage-apps" target="_blank">Manage apps</a> page in the Microsoft Teams admin center (in the left navigation, go to **Teams apps** > **Manage apps**), gives you a view into all Teams apps for your organization.</span></span> <span data-ttu-id="4747e-135">ページ **の上部にある** [承認待ち] ウィジェットでは、カスタム アプリが承認のためにいつ送信されたのか確認できます。</span><span class="sxs-lookup"><span data-stu-id="4747e-135">The **Pending approval** widget at the top of the page lets you know when a custom app is submitted for approval.</span></span>

<span data-ttu-id="4747e-136">この表では、新しく送信されたアプリの発行状態が [**送信** 済み] と [状態] が [ブロック]**に自動的\*\*\*\*に表示されます**。</span><span class="sxs-lookup"><span data-stu-id="4747e-136">In the table, a newly submitted app automatically shows a **Publishing status** of **Submitted** and **Status** of **Blocked**.</span></span> <span data-ttu-id="4747e-137">[発行状態] **列を降** 順で並べ替え、アプリをすばやく見つける。</span><span class="sxs-lookup"><span data-stu-id="4747e-137">You can sort the **Publishing status** column in descending order to quickly find the app.</span></span>

![<span data-ttu-id="4747e-138">発行の状態</span><span class="sxs-lookup"><span data-stu-id="4747e-138">publishing status</span></span> ](media/custom-app-lifecycle-validate-app.png)

<span data-ttu-id="4747e-139">アプリ名をクリックして、アプリの詳細ページに移動します。</span><span class="sxs-lookup"><span data-stu-id="4747e-139">Click the app name to go to the app details page.</span></span> <span data-ttu-id="4747e-140">**[About] タブ** では、アプリの詳細 (説明、状態、提出者、アプリ ID など) を表示できます。</span><span class="sxs-lookup"><span data-stu-id="4747e-140">On the **About** tab, you can view details about the app, including description, status, submitter, and app ID.</span></span>

![送信されたアプリのアプリの詳細ページ](media/custom-app-lifecycle-app-details.png)

<span data-ttu-id="4747e-142">Graph API を使用して発行の状態を確認する **方法** の詳細については、こちらを参照 <a href="/graph/api/appcatalogs-list-teamsapps?tabs=http&view=graph-rest-beta#example-3-find-application-based-on-the-teams-app-manifest-id" target="_blank">してください</a>。</span><span class="sxs-lookup"><span data-stu-id="4747e-142">For more information about using the Graph API to check the **Publishing status**, see <a href="/graph/api/appcatalogs-list-teamsapps?tabs=http&view=graph-rest-beta#example-3-find-application-based-on-the-teams-app-manifest-id" target="_blank">here</a>.</span></span>

## <a name="publish"></a><span data-ttu-id="4747e-143">発行</span><span class="sxs-lookup"><span data-stu-id="4747e-143">Publish</span></span>

<span data-ttu-id="4747e-144">アプリをユーザーが利用できる状態にできたら、アプリを発行します。</span><span class="sxs-lookup"><span data-stu-id="4747e-144">When you're ready to make the app available to users, publish the app.</span></span>

1. <span data-ttu-id="4747e-145">Microsoft Teams 管理センターの左側のナビゲーションで、**[Teams アプリ]** > **[アプリを管理]** の順に移動します。</span><span class="sxs-lookup"><span data-stu-id="4747e-145">In the left navigation of the Microsoft Teams admin center, go to **Teams apps** > **Manage apps**.</span></span>
2. <span data-ttu-id="4747e-146">アプリ名をクリックしてアプリの詳細ページに移動し、[発行状態]ボックスで [発行] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="4747e-146">Click the app name to go to the app details page, and then in the **Publishing status** box, select **Publish**.</span></span>

    <span data-ttu-id="4747e-147">アプリを発行すると、[発行中 **]** の状態が[発行済み] に変わります。[**状態**] は自動的に [許可] に **変わります**。</span><span class="sxs-lookup"><span data-stu-id="4747e-147">After you publish the app, the **Publishing status** changes to **Published** and the **Status** automatically changes to **Allowed**.</span></span>

## <a name="set-up-and-manage"></a><span data-ttu-id="4747e-148">セットアップと管理</span><span class="sxs-lookup"><span data-stu-id="4747e-148">Set up and manage</span></span>

### <a name="control-access-to-the-app"></a><span data-ttu-id="4747e-149">アプリへのアクセスを制御する</span><span class="sxs-lookup"><span data-stu-id="4747e-149">Control access to the app</span></span>

<span data-ttu-id="4747e-150">既定では、組織内のすべてのユーザーは、組織のアプリ ストア内のアプリにアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="4747e-150">By default, all users in your organization can access the app in your organization's app store.</span></span> <span data-ttu-id="4747e-151">アプリを使用するアクセス許可を持つユーザーを制限および制御するには、アプリのアクセス許可ポリシーを作成して割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="4747e-151">To restrict and control who has permission to use the app, you can create and assign an app permission policy.</span></span> <span data-ttu-id="4747e-152">詳細については、「<a href="/microsoftteams/teams-app-permission-policies" target="_blank">Teams のアプリのアクセス許可ポリシーを管理する</a>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4747e-152">To learn more, see <a href="/microsoftteams/teams-app-permission-policies" target="_blank">Manage app permission policies in Teams</a>.</span></span>

### <a name="pin-and-install-the-app-for-users-to-discover"></a><span data-ttu-id="4747e-153">ユーザーが検出するアプリをピン留めしてインストールする</span><span class="sxs-lookup"><span data-stu-id="4747e-153">Pin and install the app for users to discover</span></span>

<span data-ttu-id="4747e-154">既定では、ユーザーが組織のアプリ ストアにアクセスしてアプリを参照または検索する必要があるアプリを見つける場合。</span><span class="sxs-lookup"><span data-stu-id="4747e-154">By default, for users to find the app they have to go to your organization's app store and browse or search for it.</span></span> <span data-ttu-id="4747e-155">ユーザーがアプリに簡単にアクセスするには、アプリをアプリ バーのアプリ バーにピン留Teams。</span><span class="sxs-lookup"><span data-stu-id="4747e-155">To make it easy for users to get to the app, you can pin the app to the app bar in Teams.</span></span> <span data-ttu-id="4747e-156">これを行うには、アプリセットアップ ポリシーを作成し、ユーザーに割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="4747e-156">To do this, create an app setup policy and assign it to users.</span></span> <span data-ttu-id="4747e-157">詳細については、「<a href="/microsoftteams/teams-app-setup-policies" target="_blank">Teams でアプリの設定ポリシーを管理する</a>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4747e-157">To learn more, see <a href="/microsoftteams/teams-app-setup-policies" target="_blank">Manage app setup policies in Teams</a>.</span></span>

### <a name="search-the-audit-log-for-teams-app-events"></a><span data-ttu-id="4747e-158">監査ログでアプリ イベントTeams検索する</span><span class="sxs-lookup"><span data-stu-id="4747e-158">Search the audit log for Teams app events</span></span>

<span data-ttu-id="4747e-159">監査ログを検索して、組織内のTeamsアクティビティを表示できます。</span><span class="sxs-lookup"><span data-stu-id="4747e-159">You can search the audit log to view Teams apps activity in your organization.</span></span> <span data-ttu-id="4747e-160">監査ログを検索する方法と、監査ログに記録されている Teams アクティビティの一覧を表示する方法の詳細については、「Teams でイベントの監査ログを検索する」<a href="/microsoftteams/audit-log-events" target="_blank">を参照してください</a>。</span><span class="sxs-lookup"><span data-stu-id="4747e-160">To learn more about how to search the audit log and to see a list of Teams activities that are logged in the audit log, see <a href="/microsoftteams/audit-log-events" target="_blank">Search the audit log for events in Teams</a>.</span></span>

<span data-ttu-id="4747e-161">監査ログを検索できるようになるには、最初に<a href="https://protection.office.com" target="_blank">セキュリティ/コンプライアンス センター</a>で監査をオンにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="4747e-161">Before you can search the audit log, you have to first turn on auditing in the <a href="https://protection.office.com" target="_blank">Security & Compliance Center</a>.</span></span> <span data-ttu-id="4747e-162">詳細については、「<a href="https://support.office.com/article/Turn-Office-365-audit-log-search-on-or-off-e893b19a-660c-41f2-9074-d3631c95a014" target="_blank">監査ログの検索を有効または無効にする</a>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4747e-162">To learn more, see <a href="https://support.office.com/article/Turn-Office-365-audit-log-search-on-or-off-e893b19a-660c-41f2-9074-d3631c95a014" target="_blank">Turn audit log search on or off</a>.</span></span> <span data-ttu-id="4747e-163">利用できる監査データは、監査を有効にした時点以降のデータのみであることにご注意ください。</span><span class="sxs-lookup"><span data-stu-id="4747e-163">Keep in mind that audit data is only available from the point at which you turned on auditing.</span></span>

## <a name="discover-and-adopt"></a><span data-ttu-id="4747e-164">検出して採用する</span><span class="sxs-lookup"><span data-stu-id="4747e-164">Discover and adopt</span></span>

<span data-ttu-id="4747e-165">アプリへのアクセス許可を持つユーザーは、組織のアプリ ストアで見つけることができます。</span><span class="sxs-lookup"><span data-stu-id="4747e-165">Users who have permissions to the app can find it in your organization's app store.</span></span> <span data-ttu-id="4747e-166">[アプリ **] ページの *[組織名*** のビルド] に移動して、組織のカスタム アプリを見つける。</span><span class="sxs-lookup"><span data-stu-id="4747e-166">Go to **Built for *Your Organization Name*** on the Apps page to find your organization's custom apps.</span></span>

![<span data-ttu-id="4747e-167">発行済みアプリが表示されている [アプリ] ページ</span><span class="sxs-lookup"><span data-stu-id="4747e-167">Apps page showing published app</span></span> ](media/custom-app-lifecycle-discovery.png)

<span data-ttu-id="4747e-168">アプリセットアップ ポリシーを作成して割り当てた場合、アプリは Teams のアプリ バーにピン留めされ、ポリシーが割り当てられたユーザーに簡単にアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="4747e-168">If you created and assigned an app setup policy, the app is pinned to the app bar in Teams for easy access for those users who were assigned the policy.</span></span>

## <a name="update"></a><span data-ttu-id="4747e-169">更新</span><span class="sxs-lookup"><span data-stu-id="4747e-169">Update</span></span>

<span data-ttu-id="4747e-170">アプリを更新するには、開発者は引き続き「開発」セクションの手順に [従う必要](#develop) があります。</span><span class="sxs-lookup"><span data-stu-id="4747e-170">To update an app, developers should continue to follow the steps in the [Develop](#develop) section.</span></span>

<span data-ttu-id="4747e-171">開発者が公開済みカスタム アプリに更新を送信すると、[アプリの管理] ページの[承認待ち] ウィジェットで<a href="/microsoftteams/manage-apps" target="_blank">通知が表示</a>されます。</span><span class="sxs-lookup"><span data-stu-id="4747e-171">When the developer submits an update to a published custom app, you'll get notified in the **Pending approval** widget of the <a href="/microsoftteams/manage-apps" target="_blank">Manage apps</a> page.</span></span> <span data-ttu-id="4747e-172">この表では、アプリ **の発行状態** が [Update submitted ] に **設定されます**。</span><span class="sxs-lookup"><span data-stu-id="4747e-172">In the table, the **Publishing status** of the app will be set to **Update submitted**.</span></span>

![<span data-ttu-id="4747e-173">保留中の要求とアプリの状態を示す [アプリの管理] ページ</span><span class="sxs-lookup"><span data-stu-id="4747e-173">Manage apps page showing pending requests and app status</span></span> ](media/custom-app-lifecycle-update-submitted.png)

<span data-ttu-id="4747e-174">アプリの更新プログラムを確認して発行するには:</span><span class="sxs-lookup"><span data-stu-id="4747e-174">To review and publish an app update:</span></span>

1. <span data-ttu-id="4747e-175">Microsoft Teams 管理センターの左側のナビゲーションで、**[Teams アプリ]** > **[アプリを管理]** の順に移動します。</span><span class="sxs-lookup"><span data-stu-id="4747e-175">In the left navigation of the Microsoft Teams admin center, go to **Teams apps** > **Manage apps**.</span></span>
2. <span data-ttu-id="4747e-176">アプリ名をクリックしてアプリの詳細ページに移動し、[利用可能な更新] を選択して更新の詳細を確認します。</span><span class="sxs-lookup"><span data-stu-id="4747e-176">Click the app name to go to the app details page, and then select **Update available** to review details of the update.</span></span>

    ![アプリの詳細ページ](media/custom-app-lifecycle-update-app.png)
3. <span data-ttu-id="4747e-178">準備ができたら、[発行] を **選択して** 更新プログラムを発行します。</span><span class="sxs-lookup"><span data-stu-id="4747e-178">When you're ready, select **Publish** to publish the update.</span></span> <span data-ttu-id="4747e-179">これにより、既存のアプリが置き換え、バージョン番号が更新され、[発行中] の状態 **が [発行済** み] に **変更されます**。</span><span class="sxs-lookup"><span data-stu-id="4747e-179">Doing this replaces the existing app, updates the version number, and changes the **Publishing status** to **Published**.</span></span> <span data-ttu-id="4747e-180">すべてのアプリアクセス許可ポリシーとアプリ設定ポリシーは、更新されたアプリに適用されたままです。</span><span class="sxs-lookup"><span data-stu-id="4747e-180">All app permission policies and app setup policies remain enforced for the updated app.</span></span>

    <span data-ttu-id="4747e-181">更新を拒否した場合、以前のバージョンのアプリは発行されたままです。</span><span class="sxs-lookup"><span data-stu-id="4747e-181">If you reject the update, the earlier version of the app remains published.</span></span>

<span data-ttu-id="4747e-182">次の注意が必要です。</span><span class="sxs-lookup"><span data-stu-id="4747e-182">Keep in mind the following:</span></span>

- <span data-ttu-id="4747e-183">アプリが承認されると、誰でもアプリに更新を送信できます。</span><span class="sxs-lookup"><span data-stu-id="4747e-183">When an app is approved, any one can submit an update to the app.</span></span> <span data-ttu-id="4747e-184">つまり、アプリを最初に送信した開発者を含む他の開発者は、アプリに更新プログラムを送信できます。</span><span class="sxs-lookup"><span data-stu-id="4747e-184">This means other developers, including the developer who originally submitted the app, can submit an update to the app.</span></span>
- <span data-ttu-id="4747e-185">開発者がアプリを送信し、要求が保留中の場合、同じ開発者だけがアプリに更新を送信できます。</span><span class="sxs-lookup"><span data-stu-id="4747e-185">When a developer submits an app and the request is pending, only that same developer can submit an update to the app.</span></span> <span data-ttu-id="4747e-186">他の開発者は、アプリが承認された後にのみ更新を送信できます。</span><span class="sxs-lookup"><span data-stu-id="4747e-186">Other developers can submit an update only after the app is approved.</span></span>

<span data-ttu-id="4747e-187">Graph API を使用してアプリを更新する方法の詳細については、こちらを参照<a href="/graph/api/teamsapp-update?view=graph-rest-beta#example-2-update-a-previously-reviewed-and-published-application-to-the-teams-app-catalog" target="_blank">してください</a>。</span><span class="sxs-lookup"><span data-stu-id="4747e-187">For more information about using the Graph API to update apps, see <a href="/graph/api/teamsapp-update?view=graph-rest-beta#example-2-update-a-previously-reviewed-and-published-application-to-the-teams-app-catalog" target="_blank">here</a>.</span></span>

## <a name="related-topics"></a><span data-ttu-id="4747e-188">関連トピック</span><span class="sxs-lookup"><span data-stu-id="4747e-188">Related topics</span></span>

- [<span data-ttu-id="4747e-189">アプリ パッケージをアップロードしてカスタム アプリを発行する</span><span class="sxs-lookup"><span data-stu-id="4747e-189">Publish a custom app by uploading an app package</span></span>](upload-custom-apps.md)
- [<span data-ttu-id="4747e-190">管理センターでアプリMicrosoft Teams管理する</span><span class="sxs-lookup"><span data-stu-id="4747e-190">Manage your apps in the Microsoft Teams admin center</span></span>](manage-apps.md)
- [<span data-ttu-id="4747e-191">Teams のカスタム アプリのポリシーと設定を管理する</span><span class="sxs-lookup"><span data-stu-id="4747e-191">Manage custom app policies and settings in Teams</span></span>](teams-custom-app-policies-and-settings.md)
- [<span data-ttu-id="4747e-192">Teams のアプリのアクセス許可ポリシーを管理する</span><span class="sxs-lookup"><span data-stu-id="4747e-192">Manage app permission policies in Teams</span></span>](teams-app-permission-policies.md)
- [<span data-ttu-id="4747e-193">Teams のアプリのセットアップ ポリシーを管理する</span><span class="sxs-lookup"><span data-stu-id="4747e-193">Manage app setup policies in Teams</span></span>](teams-app-setup-policies.md)
- <span data-ttu-id="4747e-194"><a href="/graph/api/resources/teamsapp?view=graph-rest-beta" target="_blank">Microsoft Graph アプリ用 Teams API</a></span><span class="sxs-lookup"><span data-stu-id="4747e-194"><a href="/graph/api/resources/teamsapp?view=graph-rest-beta" target="_blank">Microsoft Graph API for Teams apps</a></span></span>