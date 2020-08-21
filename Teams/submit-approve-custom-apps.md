---
title: Teams アプリの送信 API を使用してカスタム アプリを送信および承認する
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
description: Microsoft Teams の Teams App Submission API を使用して送信されたカスタム アプリを承認する方法について説明します。
ms.openlocfilehash: bdd13dbe4db46110250ea380eebd0ea1d011a322
ms.sourcegitcommit: bb5229c9f7999358dcf0ba185ecfd7c881627a38
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/20/2020
ms.locfileid: "46824918"
---
# <a name="publish-a-custom-app-submitted-through-the-teams-app-submission-api"></a><span data-ttu-id="95fa2-103">Teams アプリ申請 API から送信されたカスタム アプリを公開する</span><span class="sxs-lookup"><span data-stu-id="95fa2-103">Publish a custom app submitted through the Teams App Submission API</span></span>

## <a name="overview"></a><span data-ttu-id="95fa2-104">概要</span><span class="sxs-lookup"><span data-stu-id="95fa2-104">Overview</span></span>

> [!NOTE]
> <span data-ttu-id="95fa2-105">カスタム Teams アプリを公開すると、組織のアプリ ストアのユーザーが使用できます。</span><span class="sxs-lookup"><span data-stu-id="95fa2-105">When you publish a custom Teams app, it's available to users in your organization's app store.</span></span> <span data-ttu-id="95fa2-106">カスタム アプリを発行する方法は 2 つありますが、アプリの入手方法は異なります。</span><span class="sxs-lookup"><span data-stu-id="95fa2-106">There are two ways to publish a custom app and the way that you use depends on how you get the app.</span></span> <span data-ttu-id="95fa2-107">**この記事では、開発者が Teams App Submission API**を通じて提出するカスタム アプリを承認および公開する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="95fa2-107">**This article focuses on how to approve and publish a custom app that a developer submits through the Teams App Submission API**.</span></span> <span data-ttu-id="95fa2-108">他の方法ではカスタム アプリをアップロードする方法は、開発者からアプリ パッケージを .zip 形式で送信するときに使用されます。</span><span class="sxs-lookup"><span data-stu-id="95fa2-108">The other method, uploading a custom app, is used when a developer sends you an app package in .zip format.</span></span> <span data-ttu-id="95fa2-109">この方法の詳細については、「アプリ <a href="https://docs.microsoft.com/microsoftteams/upload-custom-apps" target="_blank">パッケージをアップロードしてカスタム アプリを公開する」を参照してください</a>。</span><span class="sxs-lookup"><span data-stu-id="95fa2-109">To learn more about that method, see <a href="https://docs.microsoft.com/microsoftteams/upload-custom-apps" target="_blank">Publish a custom app by uploading an app package</a>.</span></span>
 
<span data-ttu-id="95fa2-110">この記事では、Teams アプリを開発から発見まで、開発から発見までの方法について、エンドでのガイダンスを提供します。</span><span class="sxs-lookup"><span data-stu-id="95fa2-110">This article provides end-to-end guidance for how to take your Teams app from development to deployment to discovery.</span></span> <span data-ttu-id="95fa2-111">Teams が組織のアプリ ストアでカスタム アプリを開発、展開、管理する方法を効率化する方法を合理化する、アプリのライフサイクル全体で Teams が提供する接続エクスペリエンスの概要を説明します。</span><span class="sxs-lookup"><span data-stu-id="95fa2-111">You'll get an overview of the connected experiences that Teams provides across the app lifecycle to streamline how to develop, deploy, and manage custom apps in your organization's app store.</span></span>

<span data-ttu-id="95fa2-112">ライフサイクルの各手順について説明します。デベロッパーが Teams App Submission API を使用してカスタム アプリを Microsoft Teams 管理センターに直接送信して、確認および承認する方法、組織内のユーザー用のアプリを管理するポリシーの設定方法、ユーザーが Teams で見つけた方法についても説明します。</span><span class="sxs-lookup"><span data-stu-id="95fa2-112">We'll cover each step of the lifecycle, including how developers can use the Teams App Submission API to submit custom apps directly to the Microsoft Teams admin center for you to review and approve, how to set policies to manage apps for users in your organization, and how your users discover them in Teams.</span></span>

![開発から展開に向かってアプリの概要](media/custom-app-lifecycle.png)

<span data-ttu-id="95fa2-114">このガイダンスはアプリの Teams の側の側で注行し、管理者と IT プロフョッショナル向けです。</span><span class="sxs-lookup"><span data-stu-id="95fa2-114">This guidance focuses on the Teams aspects of the app and is intended for admins and IT pros.</span></span> <span data-ttu-id="95fa2-115">Teams アプリの開発について詳しくは <a href="https://docs.microsoft.com/microsoftteams/platform" target="_blank">、Teams 開発者のドキュメントを参照してください</a>。</span><span class="sxs-lookup"><span data-stu-id="95fa2-115">For information about developing Teams apps, see the <a href="https://docs.microsoft.com/microsoftteams/platform" target="_blank">Teams developer documentation</a>.</span></span>

## <a name="develop"></a><span data-ttu-id="95fa2-116">開発</span><span class="sxs-lookup"><span data-stu-id="95fa2-116">Develop</span></span>

### <a name="create-the-app"></a><span data-ttu-id="95fa2-117">アプリを作成する</span><span class="sxs-lookup"><span data-stu-id="95fa2-117">Create the app</span></span>

<span data-ttu-id="95fa2-118">Microsoft Teams 開発者プラットフォームを使用すると、開発者は、生産性を向上させ、優れた事例を上げ、既存のコンテンツとワークフローに関するコラボレーションを作成することが簡単にできるようになります。</span><span class="sxs-lookup"><span data-stu-id="95fa2-118">The Microsoft Teams developer platform makes it easy for developers to integrate your own apps and services to improve productivity, make decisions faster, and create collaboration around existing content and workflows.</span></span> <span data-ttu-id="95fa2-119">Teams プラットフォームに組み込まれたアプリは、Teams クライアントとサービスとワークフローの間にブリッジされ、コラボレーション プラットフォームのコンテキストに直接取り込みます。</span><span class="sxs-lookup"><span data-stu-id="95fa2-119">Apps built on the Teams platform are bridges between the Teams client and your services and workflows, bringing them directly into the context of your collaboration platform.</span></span> <span data-ttu-id="95fa2-120">詳細については、Teams 開発者の <a href="https://docs.microsoft.com/microsoftteams/platform" target="_blank">ドキュメントを参照してください</a>。</span><span class="sxs-lookup"><span data-stu-id="95fa2-120">For more information, go to the <a href="https://docs.microsoft.com/microsoftteams/platform" target="_blank">Teams developer documentation</a>.</span></span>

### <a name="submit-the-app"></a><span data-ttu-id="95fa2-121">アプリを送信する</span><span class="sxs-lookup"><span data-stu-id="95fa2-121">Submit the app</span></span>

<span data-ttu-id="95fa2-122">アプリが実用環境で使用できるようになったら、デベロッパーは Teams アプリ提出 API からアプリを提出できます。これを使用すると、グラフ API から呼び出すことができます。これには <a href="https://docs.microsoft.com/graph/api/teamsapp-publish?view=graph-rest-1.0&tabs=http#example-2-upload-a-new-application-for-review-to-an-organizations-app-catalog" target="_blank">、グラフ API</a>から、統合開発環境 (IDE) (Visual Studio コードなどの統合開発環境 (IDE) や Power Apps や Power 仮想エージェントなどのプラットフォームを行うことができます。</span><span class="sxs-lookup"><span data-stu-id="95fa2-122">When the app is ready for use in production, the developer can submit the app using the Teams App Submission API, which can be called from <a href="https://docs.microsoft.com/graph/api/teamsapp-publish?view=graph-rest-1.0&tabs=http#example-2-upload-a-new-application-for-review-to-an-organizations-app-catalog" target="_blank">Graph API</a>, an integrated development environment (IDE) such as Visual Studio Code, or a platform such as Power Apps and Power Virtual Agents.</span></span> <span data-ttu-id="95fa2-123">これにより、アプリは Microsoft Teams 管理<a href="https://docs.microsoft.com/microsoftteams/manage-apps" target="_blank">Manage apps</a>センターの [アプリの管理] ページで利用できるようになります。このページは管理者が確認して承認することができます。これを行うことができます。</span><span class="sxs-lookup"><span data-stu-id="95fa2-123">Doing this makes the app available on the <a href="https://docs.microsoft.com/microsoftteams/manage-apps" target="_blank">Manage apps</a> page of the Microsoft Teams admin center, where you, the admin, can review and approve it.this</span></span> 

<span data-ttu-id="95fa2-124"><a href="https://docs.microsoft.com/graph/api/teamsapp-publish?view=graph-rest-1.0&tabs=http#example-2-upload-a-new-application-for-review-to-an-organizations-app-catalog" target="_blank">Microsoft Graph</a>上に組み込まれた Teams アプリの提出 API を使用すると、組織は選択したプラットフォームで開発し、Teams 上のカスタム アプリの申請を自動化できます。</span><span class="sxs-lookup"><span data-stu-id="95fa2-124">The Teams App Submission API, <a href="https://docs.microsoft.com/graph/api/teamsapp-publish?view=graph-rest-1.0&tabs=http#example-2-upload-a-new-application-for-review-to-an-organizations-app-catalog" target="_blank">built on Microsoft Graph</a>, allows your organization to develop on the platform of your choice and automates the submission-to-approval process for custom apps on Teams.</span></span>

<span data-ttu-id="95fa2-125">以下に、このアプリの送信手順の例は、コード コーVisual Studioです。</span><span class="sxs-lookup"><span data-stu-id="95fa2-125">Here's an example of what this app submission step looks like in Visual Studio Code:</span></span>

![[ビデオ コード] でアプリを送信するVisual Studioスクリーンショット](media/custom-app-lifecycle-submit-app.png)

<span data-ttu-id="95fa2-127">アプリは、まだ組織のアプリ ストアに発行されないのでご確認ください。</span><span class="sxs-lookup"><span data-stu-id="95fa2-127">Keep in mind that this doesn't publish the app to your organization's app store yet.</span></span> <span data-ttu-id="95fa2-128">この手順では、アプリを Microsoft Teams 管理センターに送信します。アプリは、組織のアプリ ストアに発行する承認を承認できます。</span><span class="sxs-lookup"><span data-stu-id="95fa2-128">This step submits the app to the Microsoft Teams admin center where you can approve it for publishing to your organization's app store.</span></span>

<span data-ttu-id="95fa2-129">Graph API を使用してアプリを送信する方法の詳細については、ここを <a href="https://docs.microsoft.com/graph/api/teamsapp-publish?view=graph-rest-1.0&tabs=http#example-2-upload-a-new-application-for-review-to-an-organizations-app-catalog" target="_blank">参照してください</a>。</span><span class="sxs-lookup"><span data-stu-id="95fa2-129">For more information about using the Graph API to submit apps, see <a href="https://docs.microsoft.com/graph/api/teamsapp-publish?view=graph-rest-1.0&tabs=http#example-2-upload-a-new-application-for-review-to-an-organizations-app-catalog" target="_blank">here</a>.</span></span>

## <a name="validate"></a><span data-ttu-id="95fa2-130">検証</span><span class="sxs-lookup"><span data-stu-id="95fa2-130">Validate</span></span>

<span data-ttu-id="95fa2-131">Microsoft Teams<a href="https://docs.microsoft.com/microsoftteams/manage-apps" target="_blank">管理センター</a>の [アプリの管理] ページ (左側のナビゲーションの **[Teams アプリ**  >  **の**管理] に移動)、組織のすべての Teams アプリを表示できます。</span><span class="sxs-lookup"><span data-stu-id="95fa2-131">The <a href="https://docs.microsoft.com/microsoftteams/manage-apps" target="_blank">Manage apps</a> page in the Microsoft Teams admin center (in the left navigation, go to **Teams apps** > **Manage apps**), gives you a view into all Teams apps for your organization.</span></span> <span data-ttu-id="95fa2-132">ページ **の上部にある** [承認保留] ウィジェットによって、カスタム アプリが承認のために送信された時点を知ることができます。</span><span class="sxs-lookup"><span data-stu-id="95fa2-132">The **Pending approval** widget at the top of the page lets you know when a custom app is submitted for approval.</span></span>

<span data-ttu-id="95fa2-133">テーブルでは、新しく送信されたアプリに自動的に [送信済み]**Publishing status**および [**Submitted**禁止済み] の [**送信済**み] の [発行状況 **] が自動的に表示されます**。</span><span class="sxs-lookup"><span data-stu-id="95fa2-133">In the table, a newly submitted app automatically shows a **Publishing status** of **Submitted** and **Status** of **Blocked**.</span></span> <span data-ttu-id="95fa2-134">[発行状況 **] 列を** 降順で並べ替えると、アプリをすばやく見つけることができます。</span><span class="sxs-lookup"><span data-stu-id="95fa2-134">You can sort the **Publishing status** column in descending order to quickly find the app.</span></span>

![<span data-ttu-id="95fa2-135">保留中の要求とアプリの状態を示す [アプリの管理] ページのスクリーンショット</span><span class="sxs-lookup"><span data-stu-id="95fa2-135">Screenshot of Manage apps page showing pending requests and app status</span></span> ](media/custom-app-lifecycle-validate-app.png)

<span data-ttu-id="95fa2-136">アプリ名をクリックしてアプリの詳細ページに移動します。</span><span class="sxs-lookup"><span data-stu-id="95fa2-136">Click the app name to go to the app details page.</span></span> <span data-ttu-id="95fa2-137">[ユーザー **情報]** タブでは、説明、状態、送信者、アプリ ID など、アプリの詳細を確認できます。</span><span class="sxs-lookup"><span data-stu-id="95fa2-137">On the **About** tab, you can view details about the app, including description, status, submitter, and app ID.</span></span>

![送信されたアプリのアプリの詳細ページのスクリーンショット](media/custom-app-lifecycle-app-details.png)

<span data-ttu-id="95fa2-139">グラフ API を使用して発行状況を確認する方法の **詳細については、** ここを <a href="https://docs.microsoft.com/graph/api/teamsapp-list?view=graph-rest-1.0&tabs=http#example-3-list-applications-with-a-given-id-and-return-the-submission-review-state" target="_blank">参照してください</a>。</span><span class="sxs-lookup"><span data-stu-id="95fa2-139">For more information about using the Graph API to check the **Publishing status**, see <a href="https://docs.microsoft.com/graph/api/teamsapp-list?view=graph-rest-1.0&tabs=http#example-3-list-applications-with-a-given-id-and-return-the-submission-review-state" target="_blank">here</a>.</span></span>

## <a name="publish"></a><span data-ttu-id="95fa2-140">公開</span><span class="sxs-lookup"><span data-stu-id="95fa2-140">Publish</span></span>

<span data-ttu-id="95fa2-141">アプリをユーザーが使いやすくする準備ができたら、アプリを発行します。</span><span class="sxs-lookup"><span data-stu-id="95fa2-141">When you're ready to make the app available to users, publish the app.</span></span>

1. <span data-ttu-id="95fa2-142">Microsoft Teams 管理センターの左側のナビゲーションで、Teams アプリの管理**アプリ**  >  **に移動します**。</span><span class="sxs-lookup"><span data-stu-id="95fa2-142">In the left navigation of the Microsoft Teams admin center, go to **Teams apps** > **Manage apps**.</span></span>
2. <span data-ttu-id="95fa2-143">アプリ名をクリックしてアプリの詳細ページに移動し、[発行] **ス** テータス ボックスで [発行] を選 **びます**。</span><span class="sxs-lookup"><span data-stu-id="95fa2-143">Click the app name to go to the app details page, and then in the **Publishing status** box, select **Publish**.</span></span>

    <span data-ttu-id="95fa2-144">アプリを発行すると、発行状況が **[発** 行済み] **に変** 化し **、状態が** [許可] に **自動的に変更されます**。</span><span class="sxs-lookup"><span data-stu-id="95fa2-144">After you publish the app, the **Publishing status** changes to **Published** and the **Status** automatically changes to **Allowed**.</span></span>

## <a name="set-up-and-manage"></a><span data-ttu-id="95fa2-145">セットアップと管理</span><span class="sxs-lookup"><span data-stu-id="95fa2-145">Set up and manage</span></span>

### <a name="control-access-to-the-app"></a><span data-ttu-id="95fa2-146">アプリへのアクセスを制御する</span><span class="sxs-lookup"><span data-stu-id="95fa2-146">Control access to the app</span></span>

<span data-ttu-id="95fa2-147">既定では、組織内のすべてのユーザーは、組織のアプリ ストア内のアプリにアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="95fa2-147">By default, all users in your organization can access the app in your organization's app store.</span></span> <span data-ttu-id="95fa2-148">アプリを使用するアクセス許可を持つユーザーを制限および制御するには、アプリのアクセス許可ポリシーを作成して割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="95fa2-148">To restrict and control who has permission to use the app, you can create and assign an app permission policy.</span></span> <span data-ttu-id="95fa2-149">詳細については <a href="https://docs.microsoft.com/microsoftteams/teams-app-permission-policies" target="_blank">、Teams でアプリのアクセス許可ポリシーを管理する方法に関するセクションを参照してください</a>。</span><span class="sxs-lookup"><span data-stu-id="95fa2-149">To learn more, see <a href="https://docs.microsoft.com/microsoftteams/teams-app-permission-policies" target="_blank">Manage app permission policies in Teams</a>.</span></span>

### <a name="pin-and-install-the-app-for-users-to-discover"></a><span data-ttu-id="95fa2-150">ユーザーが見つけたいアプリをピン留みしてインストールする</span><span class="sxs-lookup"><span data-stu-id="95fa2-150">Pin and install the app for users to discover</span></span>

<span data-ttu-id="95fa2-151">既定では、ユーザーが組織のアプリ ストアにアクセスして参照または検索する必要があるアプリを見つけるために既定で使用できます。</span><span class="sxs-lookup"><span data-stu-id="95fa2-151">By default, for users to find the app they have to go to your organization's app store and browse or search for it.</span></span> <span data-ttu-id="95fa2-152">ユーザーがアプリに簡単にアクセスできるようにするには、アプリを Teams のアプリ バーにピンピン表示することができます。</span><span class="sxs-lookup"><span data-stu-id="95fa2-152">To make it easy for users to get to the app, you can pin the app to the app bar in Teams.</span></span> <span data-ttu-id="95fa2-153">これを行うには、アプリのセットアップ ポリシーを作成してユーザーに割り当てます。</span><span class="sxs-lookup"><span data-stu-id="95fa2-153">To do this, create an app setup policy and assign it to users.</span></span> <span data-ttu-id="95fa2-154">詳細については <a href="https://docs.microsoft.com/microsoftteams/teams-app-setup-policies" target="_blank">、Teams でアプリのセットアップ ポリシーを管理する方法を参照してください</a>。</span><span class="sxs-lookup"><span data-stu-id="95fa2-154">To learn more, see <a href="https://docs.microsoft.com/microsoftteams/teams-app-setup-policies" target="_blank">Manage app setup policies in Teams</a>.</span></span>

### <a name="search-the-audit-log-for-teams-app-events"></a><span data-ttu-id="95fa2-155">監査ログで Teams アプリのイベントを検索する</span><span class="sxs-lookup"><span data-stu-id="95fa2-155">Search the audit log for Teams app events</span></span>

<span data-ttu-id="95fa2-156">監査ログを検索して、組織内の Teams アプリ アクティビティを表示できます。</span><span class="sxs-lookup"><span data-stu-id="95fa2-156">You can search the audit log to view Teams apps activity in your organization.</span></span> <span data-ttu-id="95fa2-157">監査ログを検索する方法と監査ログに記録されている Teams アクティビティの一覧を表示する方法については <a href="https://docs.microsoft.com/microsoftteams/audit-log-events" target="_blank">、「Teams での</a>イベントを検索する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="95fa2-157">To learn more about how to search the audit log and to see a list of Teams activities that are logged in the audit log, see <a href="https://docs.microsoft.com/microsoftteams/audit-log-events" target="_blank">Search the audit log for events in Teams</a>.</span></span>

<span data-ttu-id="95fa2-158">監査ログを検索する前に、まず監査ログをセキュリティ <a href="https://protection.office.com" target="_blank">センターから有効に &する必要があります</a>。</span><span class="sxs-lookup"><span data-stu-id="95fa2-158">Before you can search the audit log, you have to first turn on auditing in the <a href="https://protection.office.com" target="_blank">Security & Compliance Center</a>.</span></span> <span data-ttu-id="95fa2-159">詳細については、「 <a href="https://support.office.com/article/Turn-Office-365-audit-log-search-on-or-off-e893b19a-660c-41f2-9074-d3631c95a014" target="_blank">監査ログの検索を有効または無効にする」を参照してください</a>。</span><span class="sxs-lookup"><span data-stu-id="95fa2-159">To learn more, see <a href="https://support.office.com/article/Turn-Office-365-audit-log-search-on-or-off-e893b19a-660c-41f2-9074-d3631c95a014" target="_blank">Turn audit log search on or off</a>.</span></span> <span data-ttu-id="95fa2-160">監査データは監査を有効にした時点からのみ利用できる点にごごご確認ください。</span><span class="sxs-lookup"><span data-stu-id="95fa2-160">Keep in mind that audit data is only available from the point at which you turned on auditing.</span></span>

## <a name="discover-and-adopt"></a><span data-ttu-id="95fa2-161">検出とアドプット</span><span class="sxs-lookup"><span data-stu-id="95fa2-161">Discover and adopt</span></span>

<span data-ttu-id="95fa2-162">アプリに対するアクセス許可を持つユーザーは、組織のアプリ ストアでそのアプリを見つけることができます。</span><span class="sxs-lookup"><span data-stu-id="95fa2-162">Users who have permissions to the app can find it in your organization's app store.</span></span> <span data-ttu-id="95fa2-163">[アプリ **] ページ *で組織名の*** 組み込みに移動して、組織のカスタム アプリを見つけます。</span><span class="sxs-lookup"><span data-stu-id="95fa2-163">Go to **Built for *Your Organization Name*** on the Apps page to find your organization's custom apps.</span></span>

![<span data-ttu-id="95fa2-164">公開済みアプリを示す [アプリ] ページのスクリーンショット</span><span class="sxs-lookup"><span data-stu-id="95fa2-164">Screenshot of Apps page showing published app</span></span> ](media/custom-app-lifecycle-discovery.png)

<span data-ttu-id="95fa2-165">アプリセットアップ ポリシーを作成して割り当てた場合、そのアプリは Teams のアプリ バーにピンンンされ、ポリシーが割り当てられたユーザーに簡単にアクセスできるようになります。</span><span class="sxs-lookup"><span data-stu-id="95fa2-165">If you created and assigned an app setup policy, the app is pinned to the app bar in Teams for easy access for those users who were assigned the policy.</span></span>

## <a name="update"></a><span data-ttu-id="95fa2-166">更新する</span><span class="sxs-lookup"><span data-stu-id="95fa2-166">Update</span></span>

<span data-ttu-id="95fa2-167">アプリを更新するには、開発者は引き続き [開発] セクションの手順に [従う必要](#develop) があります。</span><span class="sxs-lookup"><span data-stu-id="95fa2-167">To update an app, developers should continue to follow the steps in the [Develop](#develop) section.</span></span>

<span data-ttu-id="95fa2-168">公開済みカスタム アプリの更新を開発者が送信すると、[アプリの管理] ページの [承認**Pending approval**保留中] ウィジェットに<a href="https://docs.microsoft.com/microsoftteams/manage-apps" target="_blank">、ポ</a>ップアップが表示されます。</span><span class="sxs-lookup"><span data-stu-id="95fa2-168">When the developer submits an update to a published custom app, you'll get notified in the **Pending approval** widget of the <a href="https://docs.microsoft.com/microsoftteams/manage-apps" target="_blank">Manage apps</a> page.</span></span> <span data-ttu-id="95fa2-169">表では、アプリ **の [発行状況** ] が [更新] **に設定されます**。</span><span class="sxs-lookup"><span data-stu-id="95fa2-169">In the table, the **Publishing status** of the app will be set to **Update submitted**.</span></span>

![<span data-ttu-id="95fa2-170">保留中の要求とアプリの状態を示す [アプリの管理] ページのスクリーンショット</span><span class="sxs-lookup"><span data-stu-id="95fa2-170">Screenshot of Manage apps page showing pending requests and app status</span></span> ](media/custom-app-lifecycle-update-submitted.png)

<span data-ttu-id="95fa2-171">アプリの更新を確認して公開するには:</span><span class="sxs-lookup"><span data-stu-id="95fa2-171">To review and publish an app update:</span></span>

1. <span data-ttu-id="95fa2-172">Microsoft Teams 管理センターの左側のナビゲーションで、Teams アプリの管理**アプリ**  >  **に移動します**。</span><span class="sxs-lookup"><span data-stu-id="95fa2-172">In the left navigation of the Microsoft Teams admin center, go to **Teams apps** > **Manage apps**.</span></span>
2. <span data-ttu-id="95fa2-173">アプリ名をクリックしてアプリの詳細ページに移動し、[ **更新プログラム] を** 選択して更新プログラムの詳細を確認します。</span><span class="sxs-lookup"><span data-stu-id="95fa2-173">Click the app name to go to the app details page, and then select **Update available** to review details of the update.</span></span>

    ![<span data-ttu-id="95fa2-174">保留中の要求とアプリの状態を示す [アプリの管理] ページのスクリーンショット</span><span class="sxs-lookup"><span data-stu-id="95fa2-174">Screenshot of Manage apps page showing pending requests and app status</span></span> ](media/custom-app-lifecycle-update-app.png)
3. <span data-ttu-id="95fa2-175">準備ができたら、[公開] **を選択して** 更新プログラムを公開します。</span><span class="sxs-lookup"><span data-stu-id="95fa2-175">When you're ready, select **Publish** to publish the update.</span></span> <span data-ttu-id="95fa2-176">この操作を行うと、既存のアプリが置き換えられます。バージョン番号が更新され、 **発行状況が [発行済** み **] に変更されます**。</span><span class="sxs-lookup"><span data-stu-id="95fa2-176">Doing this replaces the existing app, updates the version number, and changes the **Publishing status** to **Published**.</span></span> <span data-ttu-id="95fa2-177">すべてのアプリのアクセス許可ポリシーとアプリのセットアップ ポリシーは、更新されたアプリで適用されたままです。</span><span class="sxs-lookup"><span data-stu-id="95fa2-177">All app permission policies and app setup policies remain enforced for the updated app.</span></span>

    <span data-ttu-id="95fa2-178">更新プログラムを拒否すると、以前のバージョンのアプリが公開されたままです。</span><span class="sxs-lookup"><span data-stu-id="95fa2-178">If you reject the update, the earlier version of the app remains published.</span></span>

<span data-ttu-id="95fa2-179">次の操作を行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="95fa2-179">Keep in mind the following:</span></span>

- <span data-ttu-id="95fa2-180">アプリが承認されると、すべてのユーザーがアプリの更新を送信できます。</span><span class="sxs-lookup"><span data-stu-id="95fa2-180">When an app is approved, any one can submit an update to the app.</span></span> <span data-ttu-id="95fa2-181">つまり、元にアプリを送信したデベロッパーなど、他のデベロッパーは、アプリの更新を送信できます。</span><span class="sxs-lookup"><span data-stu-id="95fa2-181">This means other developers, including the developer who originally submitted the app, can submit an update to the app.</span></span>
- <span data-ttu-id="95fa2-182">開発者がアプリを送信し、要求が保留中の場合、同じ開発者のみがアプリの更新を送信できます。</span><span class="sxs-lookup"><span data-stu-id="95fa2-182">When a developer submits an app and the request is pending, only that same developer can submit an update to the app.</span></span> <span data-ttu-id="95fa2-183">他のデベロッパーは、アプリが承認された後でのみ更新プログラムを送信できます。</span><span class="sxs-lookup"><span data-stu-id="95fa2-183">Other developers can submit an update only after the app is approved.</span></span>

<span data-ttu-id="95fa2-184">グラフ API を使用してアプリを更新する方法の詳細については、ここを <a href="https://docs.microsoft.com/graph/api/teamsapp-update?view=graph-rest-1.0#example-2-update-a-previously-reviewed-and-published-application-to-the-teams-app-catalog" target="_blank">参照してください</a>。</span><span class="sxs-lookup"><span data-stu-id="95fa2-184">For more information about using the Graph API to update apps, see <a href="https://docs.microsoft.com/graph/api/teamsapp-update?view=graph-rest-1.0#example-2-update-a-previously-reviewed-and-published-application-to-the-teams-app-catalog" target="_blank">here</a>.</span></span>

### <a name="update-experience-for-users"></a><span data-ttu-id="95fa2-185">ユーザー向けの更新操作</span><span class="sxs-lookup"><span data-stu-id="95fa2-185">Update experience for users</span></span>

<span data-ttu-id="95fa2-186">ほとんどの場合、アプリの更新プログラムを発行すると、新しいバージョンがユーザーに自動的に表示されます。</span><span class="sxs-lookup"><span data-stu-id="95fa2-186">In most cases, after you publish an app update, the new version automatically appears for users.</span></span> <span data-ttu-id="95fa2-187">ただし、ユーザーが完了する必要がある Microsoft Teams マニ <a href="https://docs.microsoft.com/microsoftteams/platform/resources/schema/manifest-schema" target="_blank">フェ</a> ストには、次のような更新があります。</span><span class="sxs-lookup"><span data-stu-id="95fa2-187">However, there are some updates to the <a href="https://docs.microsoft.com/microsoftteams/platform/resources/schema/manifest-schema" target="_blank">Microsoft Teams manifest</a> that require user acceptance to complete:</span></span>

* <span data-ttu-id="95fa2-188">ボットが追加または削除されました</span><span class="sxs-lookup"><span data-stu-id="95fa2-188">A bot was added or removed</span></span>
* <span data-ttu-id="95fa2-189">既存のボットの "botId" プロパティが変更されました</span><span class="sxs-lookup"><span data-stu-id="95fa2-189">An existing bot's "botId" property changed</span></span>
* <span data-ttu-id="95fa2-190">既存のボットの "isNotificationOnly" プロパティが変更されました</span><span class="sxs-lookup"><span data-stu-id="95fa2-190">An existing bot's "isNotificationOnly" property changed</span></span>
* <span data-ttu-id="95fa2-191">ボットの "supportsFiles" プロパティが変更されました</span><span class="sxs-lookup"><span data-stu-id="95fa2-191">The bot's "supportsFiles" property changed</span></span>
* <span data-ttu-id="95fa2-192">メッセージングの拡張機能が追加または削除されました</span><span class="sxs-lookup"><span data-stu-id="95fa2-192">A messaging extension was added or removed</span></span>
* <span data-ttu-id="95fa2-193">新しいコネクタが追加されました</span><span class="sxs-lookup"><span data-stu-id="95fa2-193">A new connector was added</span></span>
* <span data-ttu-id="95fa2-194">新しい統計タブが追加されました</span><span class="sxs-lookup"><span data-stu-id="95fa2-194">A new static tab was added</span></span>
* <span data-ttu-id="95fa2-195">新しい構成可能なタブが追加されました</span><span class="sxs-lookup"><span data-stu-id="95fa2-195">A new configurable tab was added</span></span>
* <span data-ttu-id="95fa2-196">"webApplicationInfo" 内のプロパティが変更されました</span><span class="sxs-lookup"><span data-stu-id="95fa2-196">Properties inside "webApplicationInfo" changed</span></span>

![新しいバージョンが使用可能なアプリを示すスクリーンショット](media/manage-your-custom-apps-update1.png)

![アプリのアップグレード オプションのスクリーンショット](media/manage-your-custom-apps-update2.png)

## <a name="related-topics"></a><span data-ttu-id="95fa2-199">関連項目</span><span class="sxs-lookup"><span data-stu-id="95fa2-199">Related topics</span></span>

- [<span data-ttu-id="95fa2-200">アプリ パッケージをアップロードしてカスタム アプリを発行する</span><span class="sxs-lookup"><span data-stu-id="95fa2-200">Publish a custom app by uploading an app package</span></span>](upload-custom-apps.md)
- [<span data-ttu-id="95fa2-201">Microsoft Teams 管理センターでアプリを管理する</span><span class="sxs-lookup"><span data-stu-id="95fa2-201">Manage your apps in the Microsoft Teams admin center</span></span>](manage-apps.md)
- [<span data-ttu-id="95fa2-202">Teams のカスタム アプリのポリシーと設定を管理する</span><span class="sxs-lookup"><span data-stu-id="95fa2-202">Manage custom app policies and settings in Teams</span></span>](teams-custom-app-policies-and-settings.md)
- [<span data-ttu-id="95fa2-203">Teams のアプリのアクセス許可ポリシーを管理する</span><span class="sxs-lookup"><span data-stu-id="95fa2-203">Manage app permission policies in Teams</span></span>](teams-app-permission-policies.md)
- [<span data-ttu-id="95fa2-204">Teams のアプリのセットアップ ポリシーを管理する</span><span class="sxs-lookup"><span data-stu-id="95fa2-204">Manage app setup policies in Teams</span></span>](teams-app-setup-policies.md)
- <span data-ttu-id="95fa2-205"><a href="https://docs.microsoft.com/graph/api/resources/teamsapp?view=graph-rest-1.0" target="_blank">Teams アプリ用の Microsoft Graph API</a></span><span class="sxs-lookup"><span data-stu-id="95fa2-205"><a href="https://docs.microsoft.com/graph/api/resources/teamsapp?view=graph-rest-1.0" target="_blank">Microsoft Graph API for Teams apps</a></span></span>
