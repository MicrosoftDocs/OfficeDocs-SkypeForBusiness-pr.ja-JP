---
title: Teams アプリ提出 API を使用してカスタム アプリを提出および承認する
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
description: Microsoft Teams の Teams アプリ提出 API を使用して送信されるカスタム アプリを承認する方法について説明します。
ms.openlocfilehash: 058911d2d84d71ca6175e2bdeb6866807c218631
ms.sourcegitcommit: f1f3b5220c4b411f2001fbdcbe25ae7c14b94df6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/07/2021
ms.locfileid: "49776888"
---
# <a name="publish-a-custom-app-submitted-through-the-teams-app-submission-api"></a><span data-ttu-id="6291a-103">Teams アプリ提出 API を通じて送信されたカスタム アプリを発行する</span><span class="sxs-lookup"><span data-stu-id="6291a-103">Publish a custom app submitted through the Teams App Submission API</span></span>

## <a name="overview"></a><span data-ttu-id="6291a-104">概要</span><span class="sxs-lookup"><span data-stu-id="6291a-104">Overview</span></span>

> [!NOTE]
> <span data-ttu-id="6291a-105">カスタム Teams アプリを発行すると、組織のアプリ ストアのユーザーが利用できます。</span><span class="sxs-lookup"><span data-stu-id="6291a-105">When you publish a custom Teams app, it's available to users in your organization's app store.</span></span> <span data-ttu-id="6291a-106">カスタム アプリを発行する方法と使い方は、アプリの取得方法によって異なります。</span><span class="sxs-lookup"><span data-stu-id="6291a-106">There are two ways to publish a custom app and the way that you use depends on how you get the app.</span></span> <span data-ttu-id="6291a-107">**この記事では、開発者** が Teams アプリ提出 API を通じて提出するカスタム アプリを承認および公開する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="6291a-107">**This article focuses on how to approve and publish a custom app that a developer submits through the Teams App Submission API**.</span></span> <span data-ttu-id="6291a-108">もう 1 つの方法であるカスタム アプリのアップロードは、開発者から .zip 形式のアプリ パッケージが送信された場合に使用されます。</span><span class="sxs-lookup"><span data-stu-id="6291a-108">The other method, uploading a custom app, is used when a developer sends you an app package in .zip format.</span></span> <span data-ttu-id="6291a-109">この方法の詳細については、「アプリ パッケージをアップロードしてカスタム アプリを発行する <a href="https://docs.microsoft.com/microsoftteams/upload-custom-apps" target="_blank">」を参照してください</a>。</span><span class="sxs-lookup"><span data-stu-id="6291a-109">To learn more about that method, see <a href="https://docs.microsoft.com/microsoftteams/upload-custom-apps" target="_blank">Publish a custom app by uploading an app package</a>.</span></span>

<span data-ttu-id="6291a-110">この記事では、Teams アプリを開発から展開から検出に導く方法について、エンドツーエンドのガイダンスを提供します。</span><span class="sxs-lookup"><span data-stu-id="6291a-110">This article provides end-to-end guidance for how to take your Teams app from development to deployment to discovery.</span></span> <span data-ttu-id="6291a-111">Teams がアプリのライフサイクル全体にわたって提供する接続エクスペリエンスの概要を確認し、組織のアプリ ストアでカスタム アプリを開発、展開、管理する方法を合理化します。</span><span class="sxs-lookup"><span data-stu-id="6291a-111">You'll get an overview of the connected experiences that Teams provides across the app lifecycle to streamline how to develop, deploy, and manage custom apps in your organization's app store.</span></span>

<span data-ttu-id="6291a-112">ライフサイクルの各ステップについて説明します。たとえば、開発者が Teams アプリ提出 API を使用して、Microsoft Teams 管理センターに直接カスタム アプリを送信してレビューおよび承認する方法、組織内のユーザー用アプリを管理するためのポリシーを設定する方法、およびユーザーが Teams でアプリを検出する方法などについて説明します。</span><span class="sxs-lookup"><span data-stu-id="6291a-112">We'll cover each step of the lifecycle, including how developers can use the Teams App Submission API to submit custom apps directly to the Microsoft Teams admin center for you to review and approve, how to set policies to manage apps for users in your organization, and how your users discover them in Teams.</span></span>

![開発から展開まで、アプリの概要](media/custom-app-lifecycle.png)

<span data-ttu-id="6291a-114">このガイダンスでは、アプリの Teams の側面に重点を当て、管理者と IT のプロを対象にしています。</span><span class="sxs-lookup"><span data-stu-id="6291a-114">This guidance focuses on the Teams aspects of the app and is intended for admins and IT pros.</span></span> <span data-ttu-id="6291a-115">Teams アプリの開発の詳細については、Teams の開発者向け <a href="https://docs.microsoft.com/microsoftteams/platform" target="_blank">ドキュメントを参照してください</a>。</span><span class="sxs-lookup"><span data-stu-id="6291a-115">For information about developing Teams apps, see the <a href="https://docs.microsoft.com/microsoftteams/platform" target="_blank">Teams developer documentation</a>.</span></span>

## <a name="develop"></a><span data-ttu-id="6291a-116">開発</span><span class="sxs-lookup"><span data-stu-id="6291a-116">Develop</span></span>

### <a name="create-the-app"></a><span data-ttu-id="6291a-117">アプリを作成する</span><span class="sxs-lookup"><span data-stu-id="6291a-117">Create the app</span></span>

<span data-ttu-id="6291a-118">Microsoft Teams 開発者プラットフォームを使用すると、開発者は独自のアプリとサービスを簡単に統合して生産性を向上させ、意思決定を迅速に行い、既存のコンテンツとワークフローに関する共同作業を作成できます。</span><span class="sxs-lookup"><span data-stu-id="6291a-118">The Microsoft Teams developer platform makes it easy for developers to integrate your own apps and services to improve productivity, make decisions faster, and create collaboration around existing content and workflows.</span></span> <span data-ttu-id="6291a-119">Teams プラットフォーム上に構築されたアプリは、Teams クライアントとサービスとワークフローの間のブリッジであり、コラボレーション プラットフォームのコンテキストに直接取り込むのです。</span><span class="sxs-lookup"><span data-stu-id="6291a-119">Apps built on the Teams platform are bridges between the Teams client and your services and workflows, bringing them directly into the context of your collaboration platform.</span></span> <span data-ttu-id="6291a-120">詳細については、Teams の開発者向け <a href="https://docs.microsoft.com/microsoftteams/platform" target="_blank">ドキュメントを参照してください</a>。</span><span class="sxs-lookup"><span data-stu-id="6291a-120">For more information, go to the <a href="https://docs.microsoft.com/microsoftteams/platform" target="_blank">Teams developer documentation</a>.</span></span>

### <a name="submit-the-app"></a><span data-ttu-id="6291a-121">アプリを送信する</span><span class="sxs-lookup"><span data-stu-id="6291a-121">Submit the app</span></span>

<span data-ttu-id="6291a-122">アプリを実稼働環境で使用する準備ができたら、デベロッパーは Teams アプリ提出 API を使用してアプリを提出できます。アプリは <a href="https://docs.microsoft.com/graph/api/teamsapp-publish?view=graph-rest-1.0&tabs=http#example-2-upload-a-new-application-for-review-to-an-organizations-app-catalog" target="_blank" target="_blank">、Graph API、Visual Studio</a>コードなどの統合された開発環境 (IDE)、または Power Apps や Power Virtual Agents などのプラットフォームから呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="6291a-122">When the app is ready for use in production, the developer can submit the app using the Teams App Submission API, which can be called from <a href="https://docs.microsoft.com/graph/api/teamsapp-publish?view=graph-rest-1.0&tabs=http#example-2-upload-a-new-application-for-review-to-an-organizations-app-catalog" target="_blank" target="_blank">Graph API</a>, an integrated development environment (IDE) such as Visual Studio Code, or a platform such as Power Apps and Power Virtual Agents.</span></span> <span data-ttu-id="6291a-123">これにより、Microsoft Teams 管理センター<a href="https://docs.microsoft.com/microsoftteams/manage-apps" target="_blank"></a>の [アプリの管理] ページでアプリを利用できます。このページでは、管理者はアプリを確認および承認できます。</span><span class="sxs-lookup"><span data-stu-id="6291a-123">Doing this makes the app available on the <a href="https://docs.microsoft.com/microsoftteams/manage-apps" target="_blank">Manage apps</a> page of the Microsoft Teams admin center, where you, the admin, can review and approve it.this</span></span>

<span data-ttu-id="6291a-124"><a href="https://docs.microsoft.com/graph/api/teamsapp-publish?view=graph-rest-1.0&tabs=http#example-2-upload-a-new-application-for-review-to-an-organizations-app-catalog" target="_blank">Microsoft Graph</a>上に構築された Teams アプリ提出 API を使用すると、組織は選択したプラットフォーム上で開発を行い、Teams 上のカスタム アプリの提出から承認へのプロセスを自動化できます。</span><span class="sxs-lookup"><span data-stu-id="6291a-124">The Teams App Submission API, <a href="https://docs.microsoft.com/graph/api/teamsapp-publish?view=graph-rest-1.0&tabs=http#example-2-upload-a-new-application-for-review-to-an-organizations-app-catalog" target="_blank">built on Microsoft Graph</a>, allows your organization to develop on the platform of your choice and automates the submission-to-approval process for custom apps on Teams.</span></span>

<span data-ttu-id="6291a-125">このアプリの提出手順がコード内でどのような外観をVisual Studioします。</span><span class="sxs-lookup"><span data-stu-id="6291a-125">Here's an example of what this app submission step looks like in Visual Studio Code:</span></span>

![アプリを Visual Studio コードで送信する](media/custom-app-lifecycle-submit-app.png)

<span data-ttu-id="6291a-127">これにより、アプリが組織のアプリ ストアにまだ公開されるのではないので、ご安心ください。</span><span class="sxs-lookup"><span data-stu-id="6291a-127">Keep in mind that this doesn't publish the app to your organization's app store yet.</span></span> <span data-ttu-id="6291a-128">この手順では、Microsoft Teams 管理センターにアプリを送信し、組織のアプリ ストアへの公開を承認できます。</span><span class="sxs-lookup"><span data-stu-id="6291a-128">This step submits the app to the Microsoft Teams admin center where you can approve it for publishing to your organization's app store.</span></span>

<span data-ttu-id="6291a-129">Graph API を使用してアプリを送信する方法の詳細については、こちらを参照 <a href="https://docs.microsoft.com/graph/api/teamsapp-publish?view=graph-rest-1.0&tabs=http#example-2-upload-a-new-application-for-review-to-an-organizations-app-catalog" target="_blank">してください</a>。</span><span class="sxs-lookup"><span data-stu-id="6291a-129">For more information about using the Graph API to submit apps, see <a href="https://docs.microsoft.com/graph/api/teamsapp-publish?view=graph-rest-1.0&tabs=http#example-2-upload-a-new-application-for-review-to-an-organizations-app-catalog" target="_blank">here</a>.</span></span>

## <a name="validate"></a><span data-ttu-id="6291a-130">検証</span><span class="sxs-lookup"><span data-stu-id="6291a-130">Validate</span></span>

<span data-ttu-id="6291a-131">Microsoft Teams <a href="https://docs.microsoft.com/microsoftteams/manage-apps" target="_blank">管理センター</a>の [アプリの管理] ページ (左側のナビゲーションで **[Teams** アプリの管理] に移動)、組織のすべての Teams アプリを  >  表示します。</span><span class="sxs-lookup"><span data-stu-id="6291a-131">The <a href="https://docs.microsoft.com/microsoftteams/manage-apps" target="_blank">Manage apps</a> page in the Microsoft Teams admin center (in the left navigation, go to **Teams apps** > **Manage apps**), gives you a view into all Teams apps for your organization.</span></span> <span data-ttu-id="6291a-132">ページ **の上部にある** [承認待ち] ウィジェットでは、カスタム アプリが承認のために送信された時間を確認できます。</span><span class="sxs-lookup"><span data-stu-id="6291a-132">The **Pending approval** widget at the top of the page lets you know when a custom app is submitted for approval.</span></span>

<span data-ttu-id="6291a-133">この表では、新しく送信されたアプリの[発行]の状態が [送信済み] と [ブロック済み]**の状態が** 自動的 **に表示されます**。</span><span class="sxs-lookup"><span data-stu-id="6291a-133">In the table, a newly submitted app automatically shows a **Publishing status** of **Submitted** and **Status** of **Blocked**.</span></span> <span data-ttu-id="6291a-134">[発行状態] **列を** 降順で並べ替え、アプリをすばやく見つける。</span><span class="sxs-lookup"><span data-stu-id="6291a-134">You can sort the **Publishing status** column in descending order to quickly find the app.</span></span>

![<span data-ttu-id="6291a-135">発行の状態</span><span class="sxs-lookup"><span data-stu-id="6291a-135">publishing status</span></span> ](media/custom-app-lifecycle-validate-app.png)

<span data-ttu-id="6291a-136">アプリ名をクリックして、アプリの詳細ページに移動します。</span><span class="sxs-lookup"><span data-stu-id="6291a-136">Click the app name to go to the app details page.</span></span> <span data-ttu-id="6291a-137">[詳細情報 **] タブ** では、説明、状態、提出者、アプリ ID など、アプリに関する詳細を表示できます。</span><span class="sxs-lookup"><span data-stu-id="6291a-137">On the **About** tab, you can view details about the app, including description, status, submitter, and app ID.</span></span>

<span data-ttu-id="6291a-138">送信されたアプリの !app details page](media/custom-app-lifecycle-app-details.png)</span><span class="sxs-lookup"><span data-stu-id="6291a-138">!app details page for a submitted app](media/custom-app-lifecycle-app-details.png)</span></span>

<span data-ttu-id="6291a-139">Graph API を使用して発行の状態を確認する方法の詳細については **、こちらを参照**<a href="https://docs.microsoft.com/graph/api/teamsapp-list?view=graph-rest-1.0&tabs=http#example-3-list-applications-with-a-given-id-and-return-the-submission-review-state" target="_blank">してください</a>。</span><span class="sxs-lookup"><span data-stu-id="6291a-139">For more information about using the Graph API to check the **Publishing status**, see <a href="https://docs.microsoft.com/graph/api/teamsapp-list?view=graph-rest-1.0&tabs=http#example-3-list-applications-with-a-given-id-and-return-the-submission-review-state" target="_blank">here</a>.</span></span>

## <a name="publish"></a><span data-ttu-id="6291a-140">発行</span><span class="sxs-lookup"><span data-stu-id="6291a-140">Publish</span></span>

<span data-ttu-id="6291a-141">アプリをユーザーが利用できる状態に準備ができたら、アプリを発行します。</span><span class="sxs-lookup"><span data-stu-id="6291a-141">When you're ready to make the app available to users, publish the app.</span></span>

1. <span data-ttu-id="6291a-142">Microsoft Teams 管理センターの左側のナビゲーションで、Teams アプリの [アプリの **管理]**  >  **に移動します**。</span><span class="sxs-lookup"><span data-stu-id="6291a-142">In the left navigation of the Microsoft Teams admin center, go to **Teams apps** > **Manage apps**.</span></span>
2. <span data-ttu-id="6291a-143">アプリ名をクリックしてアプリの詳細ページに移動し、[発行の状態] ボックスで [発行] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="6291a-143">Click the app name to go to the app details page, and then in the **Publishing status** box, select **Publish**.</span></span>

    <span data-ttu-id="6291a-144">アプリを発行すると、[発行]**の状態** が[発行済み] に変り、[状態] が **[許可]** に **自動的に変更されます**。</span><span class="sxs-lookup"><span data-stu-id="6291a-144">After you publish the app, the **Publishing status** changes to **Published** and the **Status** automatically changes to **Allowed**.</span></span>

## <a name="set-up-and-manage"></a><span data-ttu-id="6291a-145">セットアップと管理</span><span class="sxs-lookup"><span data-stu-id="6291a-145">Set up and manage</span></span>

### <a name="control-access-to-the-app"></a><span data-ttu-id="6291a-146">アプリへのアクセスを制御する</span><span class="sxs-lookup"><span data-stu-id="6291a-146">Control access to the app</span></span>

<span data-ttu-id="6291a-147">既定では、組織内のすべてのユーザーは、組織のアプリ ストアでアプリにアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="6291a-147">By default, all users in your organization can access the app in your organization's app store.</span></span> <span data-ttu-id="6291a-148">アプリを使用するアクセス許可を持つユーザーを制限および制御するには、アプリのアクセス許可ポリシーを作成して割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="6291a-148">To restrict and control who has permission to use the app, you can create and assign an app permission policy.</span></span> <span data-ttu-id="6291a-149">詳細については、「Teams でアプリ <a href="https://docs.microsoft.com/microsoftteams/teams-app-permission-policies" target="_blank">のアクセス許可ポリシーを管理する」を参照してください</a>。</span><span class="sxs-lookup"><span data-stu-id="6291a-149">To learn more, see <a href="https://docs.microsoft.com/microsoftteams/teams-app-permission-policies" target="_blank">Manage app permission policies in Teams</a>.</span></span>

### <a name="pin-and-install-the-app-for-users-to-discover"></a><span data-ttu-id="6291a-150">ユーザーが検出するアプリをピン留めしてインストールする</span><span class="sxs-lookup"><span data-stu-id="6291a-150">Pin and install the app for users to discover</span></span>

<span data-ttu-id="6291a-151">既定では、ユーザーが組織のアプリ ストアにアクセスしてアプリを参照または検索する必要があるアプリを見つける場合。</span><span class="sxs-lookup"><span data-stu-id="6291a-151">By default, for users to find the app they have to go to your organization's app store and browse or search for it.</span></span> <span data-ttu-id="6291a-152">ユーザーが簡単にアプリにアクセスするには、アプリを Teams のアプリ バーにピン留めします。</span><span class="sxs-lookup"><span data-stu-id="6291a-152">To make it easy for users to get to the app, you can pin the app to the app bar in Teams.</span></span> <span data-ttu-id="6291a-153">これを行うには、アプリセットアップ ポリシーを作成し、ユーザーに割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="6291a-153">To do this, create an app setup policy and assign it to users.</span></span> <span data-ttu-id="6291a-154">詳細については、「Teams でアプリ <a href="https://docs.microsoft.com/microsoftteams/teams-app-setup-policies" target="_blank">セットアップ ポリシーを管理する」を参照してください</a>。</span><span class="sxs-lookup"><span data-stu-id="6291a-154">To learn more, see <a href="https://docs.microsoft.com/microsoftteams/teams-app-setup-policies" target="_blank">Manage app setup policies in Teams</a>.</span></span>

### <a name="search-the-audit-log-for-teams-app-events"></a><span data-ttu-id="6291a-155">Teams アプリ イベントの監査ログを検索する</span><span class="sxs-lookup"><span data-stu-id="6291a-155">Search the audit log for Teams app events</span></span>

<span data-ttu-id="6291a-156">監査ログを検索して、組織内の Teams アプリのアクティビティを表示できます。</span><span class="sxs-lookup"><span data-stu-id="6291a-156">You can search the audit log to view Teams apps activity in your organization.</span></span> <span data-ttu-id="6291a-157">監査ログを検索する方法と、監査ログに記録されている Teams アクティビティの一覧を表示する方法の詳細については <a href="https://docs.microsoft.com/microsoftteams/audit-log-events" target="_blank">、「Teams</a>でイベントの監査ログを検索する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6291a-157">To learn more about how to search the audit log and to see a list of Teams activities that are logged in the audit log, see <a href="https://docs.microsoft.com/microsoftteams/audit-log-events" target="_blank">Search the audit log for events in Teams</a>.</span></span>

<span data-ttu-id="6291a-158">監査ログを検索するには、まずセキュリティ/コンプライアンス センターで監査 <a href="https://protection.office.com" target="_blank">を&があります</a>。</span><span class="sxs-lookup"><span data-stu-id="6291a-158">Before you can search the audit log, you have to first turn on auditing in the <a href="https://protection.office.com" target="_blank">Security & Compliance Center</a>.</span></span> <span data-ttu-id="6291a-159">詳細については、「監査ログの <a href="https://support.office.com/article/Turn-Office-365-audit-log-search-on-or-off-e893b19a-660c-41f2-9074-d3631c95a014" target="_blank">検索を有効またはオフにする」を参照してください</a>。</span><span class="sxs-lookup"><span data-stu-id="6291a-159">To learn more, see <a href="https://support.office.com/article/Turn-Office-365-audit-log-search-on-or-off-e893b19a-660c-41f2-9074-d3631c95a014" target="_blank">Turn audit log search on or off</a>.</span></span> <span data-ttu-id="6291a-160">監査データは、監査を有効にした時点からのみ利用できます。</span><span class="sxs-lookup"><span data-stu-id="6291a-160">Keep in mind that audit data is only available from the point at which you turned on auditing.</span></span>

## <a name="discover-and-adopt"></a><span data-ttu-id="6291a-161">検出して採用する</span><span class="sxs-lookup"><span data-stu-id="6291a-161">Discover and adopt</span></span>

<span data-ttu-id="6291a-162">アプリへのアクセス許可を持つユーザーは、組織のアプリ ストアで見つける可能性があります。</span><span class="sxs-lookup"><span data-stu-id="6291a-162">Users who have permissions to the app can find it in your organization's app store.</span></span> <span data-ttu-id="6291a-163">[アプリ **] ページの *[組織*** 名のビルド] に移動して、組織のカスタム アプリを見つける。</span><span class="sxs-lookup"><span data-stu-id="6291a-163">Go to **Built for *Your Organization Name*** on the Apps page to find your organization's custom apps.</span></span>

![<span data-ttu-id="6291a-164">公開済みアプリが表示されている [アプリ] ページ</span><span class="sxs-lookup"><span data-stu-id="6291a-164">Apps page showing published app</span></span> ](media/custom-app-lifecycle-discovery.png)

<span data-ttu-id="6291a-165">アプリセットアップ ポリシーを作成して割り当てた場合、アプリは Teams のアプリ バーにピン留めされ、ポリシーが割り当てられたユーザーに簡単にアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="6291a-165">If you created and assigned an app setup policy, the app is pinned to the app bar in Teams for easy access for those users who were assigned the policy.</span></span>

## <a name="update"></a><span data-ttu-id="6291a-166">更新</span><span class="sxs-lookup"><span data-stu-id="6291a-166">Update</span></span>

<span data-ttu-id="6291a-167">アプリを更新するには、開発セクションの手順に引き続き従う [必要](#develop) があります。</span><span class="sxs-lookup"><span data-stu-id="6291a-167">To update an app, developers should continue to follow the steps in the [Develop](#develop) section.</span></span>

<span data-ttu-id="6291a-168">公開済みカスタム アプリに更新プログラムを送信すると、[アプリの管理] ページの[承認待ち] ウィジェットに<a href="https://docs.microsoft.com/microsoftteams/manage-apps" target="_blank">通知が表示</a>されます。</span><span class="sxs-lookup"><span data-stu-id="6291a-168">When the developer submits an update to a published custom app, you'll get notified in the **Pending approval** widget of the <a href="https://docs.microsoft.com/microsoftteams/manage-apps" target="_blank">Manage apps</a> page.</span></span> <span data-ttu-id="6291a-169">表では、アプリの **発行状態** が [更新が送信されました **] に設定されます**。</span><span class="sxs-lookup"><span data-stu-id="6291a-169">In the table, the **Publishing status** of the app will be set to **Update submitted**.</span></span>

![<span data-ttu-id="6291a-170">保留中の要求とアプリの状態を表示する [アプリの管理] ページ</span><span class="sxs-lookup"><span data-stu-id="6291a-170">Manage apps page showing pending requests and app status</span></span> ](media/custom-app-lifecycle-update-submitted.png)

<span data-ttu-id="6291a-171">アプリの更新プログラムを確認して公開するには、次の方法を実行します。</span><span class="sxs-lookup"><span data-stu-id="6291a-171">To review and publish an app update:</span></span>

1. <span data-ttu-id="6291a-172">Microsoft Teams 管理センターの左側のナビゲーションで、Teams アプリの [アプリの **管理]**  >  **に移動します**。</span><span class="sxs-lookup"><span data-stu-id="6291a-172">In the left navigation of the Microsoft Teams admin center, go to **Teams apps** > **Manage apps**.</span></span>
2. <span data-ttu-id="6291a-173">アプリ名をクリックしてアプリの詳細ページに移動し、[更新可能] を選択して更新の詳細を確認します。</span><span class="sxs-lookup"><span data-stu-id="6291a-173">Click the app name to go to the app details page, and then select **Update available** to review details of the update.</span></span>

    ![アプリの詳細ページ](media/custom-app-lifecycle-update-app.png)
3. <span data-ttu-id="6291a-175">準備ができたら、[発行] を **選択して** 更新プログラムを公開します。</span><span class="sxs-lookup"><span data-stu-id="6291a-175">When you're ready, select **Publish** to publish the update.</span></span> <span data-ttu-id="6291a-176">これにより、既存のアプリが置き換え、バージョン番号が更新され、[発行] の状態が **[発行済** み] に **変更されます**。</span><span class="sxs-lookup"><span data-stu-id="6291a-176">Doing this replaces the existing app, updates the version number, and changes the **Publishing status** to **Published**.</span></span> <span data-ttu-id="6291a-177">すべてのアプリのアクセス許可ポリシーとアプリセットアップ ポリシーは、更新されたアプリに適用されたままです。</span><span class="sxs-lookup"><span data-stu-id="6291a-177">All app permission policies and app setup policies remain enforced for the updated app.</span></span>

    <span data-ttu-id="6291a-178">更新プログラムを拒否した場合、以前のバージョンのアプリは発行されたままです。</span><span class="sxs-lookup"><span data-stu-id="6291a-178">If you reject the update, the earlier version of the app remains published.</span></span>

<span data-ttu-id="6291a-179">次の注意が必要です。</span><span class="sxs-lookup"><span data-stu-id="6291a-179">Keep in mind the following:</span></span>

- <span data-ttu-id="6291a-180">アプリが承認されると、誰でもアプリに更新を送信できます。</span><span class="sxs-lookup"><span data-stu-id="6291a-180">When an app is approved, any one can submit an update to the app.</span></span> <span data-ttu-id="6291a-181">つまり、アプリを最初に送信した開発者を含む他の開発者は、アプリに更新プログラムを送信できます。</span><span class="sxs-lookup"><span data-stu-id="6291a-181">This means other developers, including the developer who originally submitted the app, can submit an update to the app.</span></span>
- <span data-ttu-id="6291a-182">開発者がアプリを提出し、要求が保留中の場合、同じ開発者だけがアプリに更新を送信できます。</span><span class="sxs-lookup"><span data-stu-id="6291a-182">When a developer submits an app and the request is pending, only that same developer can submit an update to the app.</span></span> <span data-ttu-id="6291a-183">他の開発者は、アプリが承認された後にのみ更新プログラムを提出できます。</span><span class="sxs-lookup"><span data-stu-id="6291a-183">Other developers can submit an update only after the app is approved.</span></span>

<span data-ttu-id="6291a-184">Graph API を使用してアプリを更新する方法の詳細については、こちらを参照 <a href="https://docs.microsoft.com/graph/api/teamsapp-update?view=graph-rest-1.0#example-2-update-a-previously-reviewed-and-published-application-to-the-teams-app-catalog" target="_blank">してください</a>。</span><span class="sxs-lookup"><span data-stu-id="6291a-184">For more information about using the Graph API to update apps, see <a href="https://docs.microsoft.com/graph/api/teamsapp-update?view=graph-rest-1.0#example-2-update-a-previously-reviewed-and-published-application-to-the-teams-app-catalog" target="_blank">here</a>.</span></span>

### <a name="update-experience-for-users"></a><span data-ttu-id="6291a-185">ユーザーの更新エクスペリエンス</span><span class="sxs-lookup"><span data-stu-id="6291a-185">Update experience for users</span></span>

<span data-ttu-id="6291a-186">ほとんどの場合、アプリの更新プログラムを発行すると、ユーザーに新しいバージョンが自動的に表示されます。</span><span class="sxs-lookup"><span data-stu-id="6291a-186">In most cases, after you publish an app update, the new version automatically appears for users.</span></span> <span data-ttu-id="6291a-187">ただし、Microsoft <a href="https://docs.microsoft.com/microsoftteams/platform/resources/schema/manifest-schema" target="_blank">Teams</a> マニフェストには、完了するためにユーザーの同意が必要な更新プログラムがあります。</span><span class="sxs-lookup"><span data-stu-id="6291a-187">However, there are some updates to the <a href="https://docs.microsoft.com/microsoftteams/platform/resources/schema/manifest-schema" target="_blank">Microsoft Teams manifest</a> that require user acceptance to complete:</span></span>

* <span data-ttu-id="6291a-188">ボットが追加または削除されました</span><span class="sxs-lookup"><span data-stu-id="6291a-188">A bot was added or removed</span></span>
* <span data-ttu-id="6291a-189">既存のボットの "botId" プロパティが変更されました</span><span class="sxs-lookup"><span data-stu-id="6291a-189">An existing bot's "botId" property changed</span></span>
* <span data-ttu-id="6291a-190">既存のボットの "isNotificationOnly" プロパティが変更されました</span><span class="sxs-lookup"><span data-stu-id="6291a-190">An existing bot's "isNotificationOnly" property changed</span></span>
* <span data-ttu-id="6291a-191">ボットの "supportsFiles" プロパティが変更されました</span><span class="sxs-lookup"><span data-stu-id="6291a-191">The bot's "supportsFiles" property changed</span></span>
* <span data-ttu-id="6291a-192">メッセージング拡張機能が追加または削除されました</span><span class="sxs-lookup"><span data-stu-id="6291a-192">A messaging extension was added or removed</span></span>
* <span data-ttu-id="6291a-193">新しいコネクタが追加されました</span><span class="sxs-lookup"><span data-stu-id="6291a-193">A new connector was added</span></span>
* <span data-ttu-id="6291a-194">新しい静的タブが追加されました</span><span class="sxs-lookup"><span data-stu-id="6291a-194">A new static tab was added</span></span>
* <span data-ttu-id="6291a-195">新しい構成可能なタブが追加されました</span><span class="sxs-lookup"><span data-stu-id="6291a-195">A new configurable tab was added</span></span>
* <span data-ttu-id="6291a-196">"webApplicationInfo" 内のプロパティが変更されました</span><span class="sxs-lookup"><span data-stu-id="6291a-196">Properties inside "webApplicationInfo" changed</span></span>

![利用可能な新しいバージョン](media/manage-your-custom-apps-update1.png)

![アプリのアップグレード オプション](media/manage-your-custom-apps-update2.png)

## <a name="related-topics"></a><span data-ttu-id="6291a-199">関連トピック</span><span class="sxs-lookup"><span data-stu-id="6291a-199">Related topics</span></span>

- [<span data-ttu-id="6291a-200">アプリ パッケージをアップロードしてカスタム アプリを発行する</span><span class="sxs-lookup"><span data-stu-id="6291a-200">Publish a custom app by uploading an app package</span></span>](upload-custom-apps.md)
- [<span data-ttu-id="6291a-201">Microsoft Teams 管理センターでアプリを管理する</span><span class="sxs-lookup"><span data-stu-id="6291a-201">Manage your apps in the Microsoft Teams admin center</span></span>](manage-apps.md)
- [<span data-ttu-id="6291a-202">Teams のカスタム アプリのポリシーと設定を管理する</span><span class="sxs-lookup"><span data-stu-id="6291a-202">Manage custom app policies and settings in Teams</span></span>](teams-custom-app-policies-and-settings.md)
- [<span data-ttu-id="6291a-203">Teams のアプリのアクセス許可ポリシーを管理する</span><span class="sxs-lookup"><span data-stu-id="6291a-203">Manage app permission policies in Teams</span></span>](teams-app-permission-policies.md)
- [<span data-ttu-id="6291a-204">Teams のアプリのセットアップ ポリシーを管理する</span><span class="sxs-lookup"><span data-stu-id="6291a-204">Manage app setup policies in Teams</span></span>](teams-app-setup-policies.md)
- <span data-ttu-id="6291a-205"><a href="https://docs.microsoft.com/graph/api/resources/teamsapp?view=graph-rest-1.0" target="_blank">Teams アプリ用 Microsoft Graph API</a></span><span class="sxs-lookup"><span data-stu-id="6291a-205"><a href="https://docs.microsoft.com/graph/api/resources/teamsapp?view=graph-rest-1.0" target="_blank">Microsoft Graph API for Teams apps</a></span></span>
