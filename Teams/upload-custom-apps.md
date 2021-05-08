---
title: アップロード管理センターでカスタム アプリをMicrosoft Teamsする
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
description: カスタム アプリを管理センターの組織のアプリ ストアにアップロードMicrosoft Teams説明します。
ms.openlocfilehash: 9473c8e2fc4284c4ca205666152ef183b0210841
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51115525"
---
# <a name="publish-a-custom-app-by-uploading-an-app-package"></a><span data-ttu-id="94c86-103">アプリ パッケージをアップロードしてカスタム アプリを発行する</span><span class="sxs-lookup"><span data-stu-id="94c86-103">Publish a custom app by uploading an app package</span></span>

> [!NOTE]
> <span data-ttu-id="94c86-104">カスタム アプリを発行Teams、組織のアプリ ストア内のユーザーが使用できます。</span><span class="sxs-lookup"><span data-stu-id="94c86-104">When you publish a custom Teams app, it's available to users in your organization's app store.</span></span> <span data-ttu-id="94c86-105">カスタム アプリを発行する方法と使用する方法は、アプリの取得方法によって異なります。</span><span class="sxs-lookup"><span data-stu-id="94c86-105">There are two ways to publish a custom app and the way that you use depends on how you get the app.</span></span> <span data-ttu-id="94c86-106">**この記事では、** 開発者から送信されたアプリ パッケージ (.zip 形式) をアップロードして、カスタム アプリを発行する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="94c86-106">**This article focuses on how to publish a custom app by uploading an app package (in .zip format) that a developer sends you**.</span></span> <span data-ttu-id="94c86-107">カスタム アプリを承認するもう 1 つの方法は、開発者がアプリの管理ページに<a href="/microsoftteams/manage-apps" target="_blank"></a>アプリを直接送信するときに、Teams アプリ送信 API を使用します。</span><span class="sxs-lookup"><span data-stu-id="94c86-107">The other method, approving a custom app, is used when a developer submits an app directly to the <a href="/microsoftteams/manage-apps" target="_blank">Manage apps</a> page through the Teams App Submission API.</span></span> <span data-ttu-id="94c86-108">その方法の詳細については、「アプリ送信 API を使用して送信されたカスタム アプリを発行Teams<a href="/microsoftteams/submit-approve-custom-apps" target="_blank">参照してください</a>。</span><span class="sxs-lookup"><span data-stu-id="94c86-108">To learn more about that method, see <a href="/microsoftteams/submit-approve-custom-apps" target="_blank">Publish a custom app submitted through the Teams App Submission API</a>.</span></span>

<span data-ttu-id="94c86-109">この記事では、開発からデプロイから検出まで、Teamsアプリを使用する方法について、エンド to エンドのガイダンスを提供します。</span><span class="sxs-lookup"><span data-stu-id="94c86-109">This article provides end-to-end guidance for how to take your Teams app from development to deployment to discovery.</span></span> <span data-ttu-id="94c86-110">このガイダンスでは、アプリのTeamsに焦点を当て、管理者と IT のプロを対象にしています。</span><span class="sxs-lookup"><span data-stu-id="94c86-110">This guidance focuses on the Teams aspects of the app and is intended for admins and IT pros.</span></span> <span data-ttu-id="94c86-111">アプリの開発の詳細については、Teams 開発者向けドキュメント<a href="/microsoftteams/platform" target="_blank">Teams参照してください</a>。</span><span class="sxs-lookup"><span data-stu-id="94c86-111">For more information about developing Teams apps, see the <a href="/microsoftteams/platform" target="_blank">Teams developer documentation</a>.</span></span>

![開発からデプロイまで、アプリの概要](media/upload-custom-apps.png)

## <a name="develop"></a><span data-ttu-id="94c86-113">開発</span><span class="sxs-lookup"><span data-stu-id="94c86-113">Develop</span></span>

### <a name="create-your-app"></a><span data-ttu-id="94c86-114">アプリを作成する</span><span class="sxs-lookup"><span data-stu-id="94c86-114">Create your app</span></span>

<span data-ttu-id="94c86-115">開発者Microsoft Teamsプラットフォームを使用すると、開発者は独自のアプリとサービスを簡単に統合して生産性を向上させ、意思決定を迅速に行い、既存のコンテンツやワークフローに関するコラボレーションを作成できます。</span><span class="sxs-lookup"><span data-stu-id="94c86-115">The Microsoft Teams developer platform makes it easy for developers to integrate your own apps and services to improve productivity, make decisions faster, and create collaboration around existing content and workflows.</span></span> <span data-ttu-id="94c86-116">Teams プラットフォーム上に構築されたアプリは、Teams クライアントとサービスとワークフローの間のブリッジであり、コラボレーション プラットフォームのコンテキストに直接取り込む必要があります。</span><span class="sxs-lookup"><span data-stu-id="94c86-116">Apps built on the Teams platform are bridges between the Teams client and your services and workflows, bringing them directly into the context of your collaboration platform.</span></span> <span data-ttu-id="94c86-117">詳細については、開発者向けドキュメント<a href="/microsoftteams/platform" target="_blank">Teams参照してください</a>。</span><span class="sxs-lookup"><span data-stu-id="94c86-117">For more information, go to the <a href="/microsoftteams/platform" target="_blank">Teams developer documentation</a>.</span></span>

## <a name="validate"></a><span data-ttu-id="94c86-118">検証</span><span class="sxs-lookup"><span data-stu-id="94c86-118">Validate</span></span>

### <a name="get-the-app-package"></a><span data-ttu-id="94c86-119">アプリ パッケージを取得する</span><span class="sxs-lookup"><span data-stu-id="94c86-119">Get the app package</span></span>

<span data-ttu-id="94c86-120">アプリを実稼働環境で使用する準備ができたら、開発者はアプリ パッケージを生成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="94c86-120">When the app is ready for use in production, the developer should produce an app package.</span></span> <span data-ttu-id="94c86-121">その場合 <a href="/microsoftteams/platform/get-started/get-started-app-studio" target="_blank">、App Studio</a> を使用できます。</span><span class="sxs-lookup"><span data-stu-id="94c86-121">They can use <a href="/microsoftteams/platform/get-started/get-started-app-studio" target="_blank">App Studio</a> for that.</span></span> <span data-ttu-id="94c86-122">ユーザーは、ファイルを別の形式.zipします。</span><span class="sxs-lookup"><span data-stu-id="94c86-122">They'll send you the file in .zip format.</span></span>

<span data-ttu-id="94c86-123">Microsoft では<a href="/microsoftteams/platform/publishing/office-store-approval" target="_blank">、これらのガイドラインを使用</a>して、アプリがグローバルなアプリ ストアの品質とセキュリティ基準に準拠Teamsします。</span><span class="sxs-lookup"><span data-stu-id="94c86-123">Microsoft uses <a href="/microsoftteams/platform/publishing/office-store-approval" target="_blank">these guidelines</a> to ensure apps comply with the quality and security standards of the global Teams apps store.</span></span>

### <a name="allow-trusted-users-to-upload-custom-apps"></a><span data-ttu-id="94c86-124">信頼できるユーザーにカスタム アプリのアップロードを許可する</span><span class="sxs-lookup"><span data-stu-id="94c86-124">Allow trusted users to upload custom apps</span></span>

<span data-ttu-id="94c86-125">アプリが実稼働テナントで正しく動作しているのを検証するには、自分や信頼できるユーザーがカスタム アプリを実稼働テナントにアップロードできる必要があります。</span><span class="sxs-lookup"><span data-stu-id="94c86-125">To validate that the app is working correctly in your production tenant, you need to allow yourself and/or trusted users to upload custom apps in the production tenant.</span></span> <span data-ttu-id="94c86-126">これを行 <a href="/microsoftteams/teams-app-setup-policies" target="_blank">うには、アプリセットアップ ポリシー</a> を使用します。</span><span class="sxs-lookup"><span data-stu-id="94c86-126">You use <a href="/microsoftteams/teams-app-setup-policies" target="_blank">app setup policies</a> to do this.</span></span>

> [!NOTE]
> <span data-ttu-id="94c86-127">検証のためにアプリを実稼働テナントにアップロードする場合は、この手順をスキップし[、「アップロード」](#upload)セクションと「セットアップと管理」セクションの手順に従って、検証されていないアプリを[](#set-up-and-manage)組織のアプリ ストアに発行できます。</span><span class="sxs-lookup"><span data-stu-id="94c86-127">If you're uncomfortable with uploading the app to your production tenant for validation, even for yourself or trusted users, you can skip this step and follow the steps in the [Upload](#upload) and [Set up and manage](#set-up-and-manage) sections to publish the unvalidated app to your organization's app store.</span></span> <span data-ttu-id="94c86-128">その後、そのアプリへのアクセスを自分と信頼できるユーザーにのみ制限します。</span><span class="sxs-lookup"><span data-stu-id="94c86-128">Then, restrict access to that app to only yourself and users you trust.</span></span> <span data-ttu-id="94c86-129">これらのユーザーは、検証を実行するために、組織のアプリ ストアからアプリを取得できます。</span><span class="sxs-lookup"><span data-stu-id="94c86-129">These users can then get the app from your organization's app store to perform validation.</span></span> <span data-ttu-id="94c86-130">アプリが検証された後、同じアクセス許可ポリシーを使用して、アクセス権を開き、アプリを実稼働環境で使用するためにロールアウトします。</span><span class="sxs-lookup"><span data-stu-id="94c86-130">After the app is validated, use the same permission policies to open access and roll the app out for production use.</span></span>

<span data-ttu-id="94c86-131">信頼できるユーザーにカスタム アプリのアップロードを許可するには、次の手順に従います。</span><span class="sxs-lookup"><span data-stu-id="94c86-131">To allow trusted users to upload custom apps, follow these steps:</span></span>

1. <span data-ttu-id="94c86-132">[カスタム アプリ **との対話を許可する] 組織全体** のアプリ設定を有効にします。</span><span class="sxs-lookup"><span data-stu-id="94c86-132">Turn on the **Allow interaction with custom apps** org-wide app setting.</span></span> <span data-ttu-id="94c86-133">その手順は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="94c86-133">To do this:</span></span>
    1. <span data-ttu-id="94c86-134">管理センターの左側の Microsoft Teamsナビゲーションで、[Teams **アプリ** の管理] に移動し、[組織全体のアプリ設定]  >  **をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="94c86-134">In the left navigation of the Microsoft Teams admin center, go to **Teams apps** > **Manage apps**, and then click **Org-wide app settings**.</span></span>
    2. <span data-ttu-id="94c86-135">[ **カスタム アプリ] で**、[カスタム アプリとの対話を許可する] **をオンに** し、[保存] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="94c86-135">Under **Custom apps**, turn on **Allow interaction with custom apps**, and then click **Save**.</span></span>
2. <span data-ttu-id="94c86-136">グローバル アプリセットアップ **ポリシーアップロードカスタム** アプリの設定をオフにします。</span><span class="sxs-lookup"><span data-stu-id="94c86-136">Turn off the **Upload custom apps** setting in the global app setup policy.</span></span> <span data-ttu-id="94c86-137">その手順は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="94c86-137">To do this:</span></span>
    1. <span data-ttu-id="94c86-138">Microsoft Teams 管理センターの左側のナビゲーションで、[Teams **アプリ** のセットアップ ポリシー] に移動し、[グローバル (組織全体の既定) ポリシー]  >  **をクリック** します。</span><span class="sxs-lookup"><span data-stu-id="94c86-138">In the left navigation of the Microsoft Teams admin center, go to **Teams apps** > **Setup policies**, and then click the **Global (Org-wide default)** policy.</span></span>
    2. <span data-ttu-id="94c86-139">カスタム アプリ **をアップロードをオフにし、[** 保存] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="94c86-139">Turn off **Upload custom apps**, and then click **Save**.</span></span>
3. <span data-ttu-id="94c86-140">カスタム アプリをアップロードして信頼できるユーザーのセットに割り当て可能な新しいアプリ セットアップ ポリシーを作成します。</span><span class="sxs-lookup"><span data-stu-id="94c86-140">Create a new app setup policy that allows uploading custom apps and assign it to your set of trusted users.</span></span> <span data-ttu-id="94c86-141">その手順は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="94c86-141">To do this:</span></span>
    1. <span data-ttu-id="94c86-142">管理センターの左側のナビゲーションMicrosoft Teamsアプリのセットアップ Teams **に** 移動し、[追加]  >  をクリック **します**。</span><span class="sxs-lookup"><span data-stu-id="94c86-142">In the left navigation of the Microsoft Teams admin center, go to **Teams apps** > **Setup policies**, and then click the **Add**.</span></span> <span data-ttu-id="94c86-143">新しいポリシーに名前と説明を付け、カスタム アップロード **を有効に** し、[保存] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="94c86-143">Give the new policy a name and description, turn on **Upload custom apps**, and then click **Save**.</span></span>
    2. <span data-ttu-id="94c86-144">作成した新しいポリシーを選択し、[ユーザーの管理] **をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="94c86-144">Select the new policy you created, and then click **Manage users**.</span></span> <span data-ttu-id="94c86-145">ユーザーを検索し、[追加] **をクリックして**、[適用] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="94c86-145">Search for a user, click **Add**, and then click **Apply**.</span></span> <span data-ttu-id="94c86-146">この手順を繰り返して、信頼できるすべてのユーザーにポリシーを割り当てる。</span><span class="sxs-lookup"><span data-stu-id="94c86-146">Repeat this step to assign the policy to all your trusted users.</span></span>

        ![[アプリのセットアップ ポリシーの追加] ページのスクリーンショット](media/manage-your-lob-apps-new-app-setup-policy.png)

    <span data-ttu-id="94c86-148">これらのユーザーは、アプリ マニフェストをアップロードして、アプリが実稼働テナントで正しく動作しているのを検証できます。</span><span class="sxs-lookup"><span data-stu-id="94c86-148">These users can now upload the app manifest to validate that the app is working correctly in the production tenant.</span></span>

## <a name="upload"></a><span data-ttu-id="94c86-149">アップロード</span><span class="sxs-lookup"><span data-stu-id="94c86-149">Upload</span></span>

<span data-ttu-id="94c86-150">組織のアプリ ストア内のユーザーがアプリを利用するには、アプリをアップロードします。</span><span class="sxs-lookup"><span data-stu-id="94c86-150">To make the app available to users in your organization's app store, upload the app.</span></span> <span data-ttu-id="94c86-151">管理センターの [<a href="/microsoftteams/manage-apps" target="_blank">アプリの管理</a>] ページMicrosoft Teamsできます。</span><span class="sxs-lookup"><span data-stu-id="94c86-151">You can do this on the <a href="/microsoftteams/manage-apps" target="_blank">Manage apps</a> page of the Microsoft Teams admin center.</span></span>

1. <span data-ttu-id="94c86-152">Microsoft Teams 管理センターの左側のナビゲーションで、**[Teams アプリ]** > **[アプリを管理]** の順に移動します。</span><span class="sxs-lookup"><span data-stu-id="94c86-152">In the left navigation of the Microsoft Teams admin center, go to **Teams apps** > **Manage apps**.</span></span>
2. <span data-ttu-id="94c86-153">**[アップロード]** をクリックし **、[ファイルの** 選択] をクリックし、開発者から受け取ったアプリ パッケージを選択します。</span><span class="sxs-lookup"><span data-stu-id="94c86-153">Click **Upload**, click **Select a file**, and then select the app package that you received from the developer.</span></span>

   ![管理センターでのアプリのアップロードのスクリーンショット](media/manage-your-lob-apps-upload-new-app.png) 

## <a name="set-up-and-manage"></a><span data-ttu-id="94c86-155">セットアップと管理</span><span class="sxs-lookup"><span data-stu-id="94c86-155">Set up and manage</span></span>

### <a name="control-access-to-the-app"></a><span data-ttu-id="94c86-156">アプリへのアクセスを制御する</span><span class="sxs-lookup"><span data-stu-id="94c86-156">Control access to the app</span></span>

<span data-ttu-id="94c86-157">既定では、組織内のすべてのユーザーは、組織のアプリ ストア内のアプリにアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="94c86-157">By default, all users in your organization can access the app in your organization's app store.</span></span> <span data-ttu-id="94c86-158">アプリを使用するアクセス許可を持つユーザーを制限および制御するには、アプリのアクセス許可ポリシーを作成して割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="94c86-158">To restrict and control who has permission to use the app, you can create and assign an app permission policy.</span></span> <span data-ttu-id="94c86-159">詳細については、「<a href="/microsoftteams/teams-app-permission-policies" target="_blank">Teams のアプリのアクセス許可ポリシーを管理する</a>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="94c86-159">To learn more, see <a href="/microsoftteams/teams-app-permission-policies" target="_blank">Manage app permission policies in Teams</a>.</span></span>

### <a name="pin-and-install-the-app-for-users-to-discover"></a><span data-ttu-id="94c86-160">ユーザーが検出するアプリをピン留めしてインストールする</span><span class="sxs-lookup"><span data-stu-id="94c86-160">Pin and install the app for users to discover</span></span>

<span data-ttu-id="94c86-161">既定では、ユーザーが組織のアプリ ストアにアクセスしてアプリを参照または検索する必要があるアプリを見つける場合。</span><span class="sxs-lookup"><span data-stu-id="94c86-161">By default, for users to find the app they have to go to your organization's app store and browse or search for it.</span></span> <span data-ttu-id="94c86-162">ユーザーがアプリに簡単にアクセスするには、アプリをアプリ バーのアプリ バーにピン留Teams。</span><span class="sxs-lookup"><span data-stu-id="94c86-162">To make it easy for users to get to the app, you can pin the app to the app bar in Teams.</span></span> <span data-ttu-id="94c86-163">これを行うには、アプリセットアップ ポリシーを作成し、ユーザーに割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="94c86-163">To do this, create an app setup policy and assign it to users.</span></span> <span data-ttu-id="94c86-164">詳細については、「<a href="/microsoftteams/teams-app-setup-policies" target="_blank">Teams でアプリの設定ポリシーを管理する</a>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="94c86-164">To learn more, see <a href="/microsoftteams/teams-app-setup-policies" target="_blank">Manage app setup policies in Teams</a>.</span></span>

### <a name="search-the-audit-log-for-teams-app-events"></a><span data-ttu-id="94c86-165">監査ログでアプリ イベントTeams検索する</span><span class="sxs-lookup"><span data-stu-id="94c86-165">Search the audit log for Teams app events</span></span>

<span data-ttu-id="94c86-166">監査ログを検索して、組織内のTeamsアクティビティを表示できます。</span><span class="sxs-lookup"><span data-stu-id="94c86-166">You can search the audit log to view Teams apps activity in your organization.</span></span> <span data-ttu-id="94c86-167">監査ログを検索する方法と、監査ログに記録されている Teams アクティビティの一覧を表示する方法の詳細については、「Teams でイベントの監査ログを検索する」<a href="/microsoftteams/audit-log-events" target="_blank">を参照してください</a>。</span><span class="sxs-lookup"><span data-stu-id="94c86-167">To learn more about how to search the audit log and to see a list of Teams activities that are logged in the audit log, see <a href="/microsoftteams/audit-log-events" target="_blank">Search the audit log for events in Teams</a>.</span></span>

<span data-ttu-id="94c86-168">監査ログを検索できるようになるには、最初に<a href="https://protection.office.com" target="_blank">セキュリティ/コンプライアンス センター</a>で監査をオンにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="94c86-168">Before you can search the audit log, you have to first turn on auditing in the <a href="https://protection.office.com" target="_blank">Security & Compliance Center</a>.</span></span> <span data-ttu-id="94c86-169">詳細については、「<a href="https://support.office.com/article/Turn-Office-365-audit-log-search-on-or-off-e893b19a-660c-41f2-9074-d3631c95a014" target="_blank">監査ログの検索を有効または無効にする</a>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="94c86-169">To learn more, see <a href="https://support.office.com/article/Turn-Office-365-audit-log-search-on-or-off-e893b19a-660c-41f2-9074-d3631c95a014" target="_blank">Turn audit log search on or off</a>.</span></span> <span data-ttu-id="94c86-170">利用できる監査データは、監査を有効にした時点以降のデータのみであることにご注意ください。</span><span class="sxs-lookup"><span data-stu-id="94c86-170">Keep in mind that audit data is only available from the point at which you turned on auditing.</span></span>

## <a name="discover-and-adopt"></a><span data-ttu-id="94c86-171">検出して採用する</span><span class="sxs-lookup"><span data-stu-id="94c86-171">Discover and adopt</span></span>

<span data-ttu-id="94c86-172">アプリへのアクセス許可を持つユーザーは、組織のアプリ ストアで見つけることができます。</span><span class="sxs-lookup"><span data-stu-id="94c86-172">Users who have permissions to the app can find it in your organization's app store.</span></span> <span data-ttu-id="94c86-173">[アプリ **] ページの *[組織名*** のビルド] に移動して、組織のカスタム アプリを見つける。</span><span class="sxs-lookup"><span data-stu-id="94c86-173">Go to **Built for *Your Organization Name*** on the Apps page to find your organization's custom apps.</span></span>

![<span data-ttu-id="94c86-174">発行されたアプリを示す [アプリ] ページのスクリーンショット</span><span class="sxs-lookup"><span data-stu-id="94c86-174">Screenshot of Apps page showing published app</span></span> ](media/custom-app-lifecycle-discovery.png)

<span data-ttu-id="94c86-175">アプリセットアップ ポリシーを作成して割り当てた場合、アプリは Teams のアプリ バーにピン留めされ、ポリシーが割り当てられたユーザーに簡単にアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="94c86-175">If you created and assigned an app setup policy, the app is pinned to the app bar in Teams for easy access for those users who were assigned the policy.</span></span>

## <a name="update"></a><span data-ttu-id="94c86-176">更新</span><span class="sxs-lookup"><span data-stu-id="94c86-176">Update</span></span>

<span data-ttu-id="94c86-177">アプリを更新するには、開発者は引き続き「開発と検証」セクションの[手順](#develop)[に](#validate)従う必要があります。</span><span class="sxs-lookup"><span data-stu-id="94c86-177">To update an app, developers should continue to follow the steps in the [Develop](#develop) and [Validate](#validate) sections.</span></span>

<span data-ttu-id="94c86-178">アプリは、管理センターの [アプリの管理] ページMicrosoft Teams更新できます。</span><span class="sxs-lookup"><span data-stu-id="94c86-178">You can update the app on the Manage apps page in the Microsoft Teams admin center.</span></span> <span data-ttu-id="94c86-179">これを行うには、管理センターの左側のナビゲーションMicrosoft Teamsアプリの管理Teams **に**  >  **移動します**。</span><span class="sxs-lookup"><span data-stu-id="94c86-179">To do this, in the left navigation of the Microsoft Teams admin center, go to **Teams apps** > **Manage apps**.</span></span> <span data-ttu-id="94c86-180">アプリ名をクリックし、[更新] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="94c86-180">Click the app name, and then click **Update**.</span></span> <span data-ttu-id="94c86-181">これにより、既存のアプリが置き換え、すべてのアプリアクセス許可ポリシーとアプリセットアップ ポリシーが、更新されたアプリに適用されたままです。</span><span class="sxs-lookup"><span data-stu-id="94c86-181">Doing this replaces the existing app, and all app permission policies and app setup policies remain enforced for the updated app.</span></span>

### <a name="end-user-update-experience"></a><span data-ttu-id="94c86-182">エンド ユーザーの更新エクスペリエンス</span><span class="sxs-lookup"><span data-stu-id="94c86-182">End user update experience</span></span>

<span data-ttu-id="94c86-183">ほとんどの場合、アプリの更新を完了すると、エンド ユーザーに対して新しいバージョンが自動的に表示されます。</span><span class="sxs-lookup"><span data-stu-id="94c86-183">In most cases, after you complete an app update the new version automatically appears for end users.</span></span> <span data-ttu-id="94c86-184">ただし、完了するためにユーザーの受け入れを<a href="/microsoftteams/platform/resources/schema/manifest-schema" target="_blank">必要Microsoft Teamsマニフェスト</a>にはいくつかの更新があります。</span><span class="sxs-lookup"><span data-stu-id="94c86-184">However, there are some updates to the <a href="/microsoftteams/platform/resources/schema/manifest-schema" target="_blank">Microsoft Teams manifest</a> that require user acceptance to complete:</span></span>

* <span data-ttu-id="94c86-185">ボットが追加または削除されました</span><span class="sxs-lookup"><span data-stu-id="94c86-185">A bot was added or removed</span></span>
* <span data-ttu-id="94c86-186">既存のボットの "botId" プロパティが変更されました</span><span class="sxs-lookup"><span data-stu-id="94c86-186">An existing bot's "botId" property changed</span></span>
* <span data-ttu-id="94c86-187">既存のボットの "isNotificationOnly" プロパティが変更されました</span><span class="sxs-lookup"><span data-stu-id="94c86-187">An existing bot's "isNotificationOnly" property changed</span></span>
* <span data-ttu-id="94c86-188">ボットの "supportsFiles" プロパティが変更されました</span><span class="sxs-lookup"><span data-stu-id="94c86-188">The bot's "supportsFiles" property changed</span></span>
* <span data-ttu-id="94c86-189">メッセージング拡張機能が追加または削除されました</span><span class="sxs-lookup"><span data-stu-id="94c86-189">A Messaging extension was added or removed</span></span>
* <span data-ttu-id="94c86-190">新しいコネクタが追加されました</span><span class="sxs-lookup"><span data-stu-id="94c86-190">A new connector was added</span></span>
* <span data-ttu-id="94c86-191">新しい静的タブが追加されました</span><span class="sxs-lookup"><span data-stu-id="94c86-191">A new static tab was added</span></span>
* <span data-ttu-id="94c86-192">新しい構成可能なタブが追加されました</span><span class="sxs-lookup"><span data-stu-id="94c86-192">A new configurable tab was added</span></span>
* <span data-ttu-id="94c86-193">"webApplicationInfo" 内のプロパティが変更されました</span><span class="sxs-lookup"><span data-stu-id="94c86-193">Properties inside "webApplicationInfo" changed</span></span>

![新しいバージョンが利用可能なアプリを示すアプリの一覧のスクリーンショット](media/manage-your-custom-apps-update1.png)

![アプリのアップグレード オプションのスクリーンショット](media/manage-your-custom-apps-update2.png)

## <a name="related-topics"></a><span data-ttu-id="94c86-196">関連トピック</span><span class="sxs-lookup"><span data-stu-id="94c86-196">Related topics</span></span>

- [<span data-ttu-id="94c86-197">Teams App Submission API を使用して送信されたカスタム アプリを発行する</span><span class="sxs-lookup"><span data-stu-id="94c86-197">Publish a custom app submitted through the Teams App Submission API</span></span>](submit-approve-custom-apps.md)
- [<span data-ttu-id="94c86-198">管理センターでアプリMicrosoft Teams管理する</span><span class="sxs-lookup"><span data-stu-id="94c86-198">Manage your apps in the Microsoft Teams admin center</span></span>](manage-apps.md)
- [<span data-ttu-id="94c86-199">Teams のカスタム アプリのポリシーと設定を管理する</span><span class="sxs-lookup"><span data-stu-id="94c86-199">Manage custom app policies and settings in Teams</span></span>](teams-custom-app-policies-and-settings.md)
- [<span data-ttu-id="94c86-200">Teams のアプリのアクセス許可ポリシーを管理する</span><span class="sxs-lookup"><span data-stu-id="94c86-200">Manage app permission policies in Teams</span></span>](teams-app-permission-policies.md)
- [<span data-ttu-id="94c86-201">Teams のアプリのセットアップ ポリシーを管理する</span><span class="sxs-lookup"><span data-stu-id="94c86-201">Manage app setup policies in Teams</span></span>](teams-app-setup-policies.md)