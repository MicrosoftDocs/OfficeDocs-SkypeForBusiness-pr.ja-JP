---
title: Microsoft Teams 管理センターでカスタムアプリをアップロードする
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
description: Microsoft Teams 管理センターでカスタムアプリを組織のアプリストアにアップロードする方法について説明します。
ms.openlocfilehash: d43b19f4ada3ce6f0424a324cdea6f194575325b
ms.sourcegitcommit: 43d66693f6f08d4dcade0095bf613240031fec56
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/06/2020
ms.locfileid: "46583646"
---
# <a name="publish-a-custom-app-by-uploading-an-app-package"></a><span data-ttu-id="2e39c-103">アプリパッケージをアップロードしてカスタムアプリを公開する</span><span class="sxs-lookup"><span data-stu-id="2e39c-103">Publish a custom app by uploading an app package</span></span>

> [!NOTE]
> <span data-ttu-id="2e39c-104">カスタム Teams アプリを公開すると、組織のアプリストア内のユーザーがそのアプリを利用できるようになります。</span><span class="sxs-lookup"><span data-stu-id="2e39c-104">When you publish a custom Teams app, it's available to users in your organization's app store.</span></span> <span data-ttu-id="2e39c-105">カスタムアプリを公開する方法は2つあります。また、アプリの入手方法によって異なります。</span><span class="sxs-lookup"><span data-stu-id="2e39c-105">There are two ways to publish a custom app and the way that you use depends on how you get the app.</span></span> <span data-ttu-id="2e39c-106">**この記事では、開発者から送信されたアプリパッケージ (.zip 形式) をアップロードして、カスタムアプリを公開する方法について説明**します。</span><span class="sxs-lookup"><span data-stu-id="2e39c-106">**This article focuses on how to publish a custom app by uploading an app package (in .zip format) that a developer sends you**.</span></span> <span data-ttu-id="2e39c-107">その他の方法 (カスタムアプリを承認する) は、開発者が Teams アプリ申請 API を使用してアプリの<a href="https://docs.microsoft.com/microsoftteams/manage-apps" target="_blank">管理</a>ページに直接アプリを送信するときに使用されます。</span><span class="sxs-lookup"><span data-stu-id="2e39c-107">The other method, approving a custom app, is used when a developer submits an app directly to the <a href="https://docs.microsoft.com/microsoftteams/manage-apps" target="_blank">Manage apps</a> page through the Teams App Submission API.</span></span> <span data-ttu-id="2e39c-108">このメソッドの詳細については、「 <a href="https://docs.microsoft.com/microsoftteams/submit-approve-custom-apps" target="_blank">Teams アプリ申請 API を通じて送信されたカスタムアプリを公開</a>する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2e39c-108">To learn more about that method, see <a href="https://docs.microsoft.com/microsoftteams/submit-approve-custom-apps" target="_blank">Publish a custom app submitted through the Teams App Submission API</a>.</span></span>

<span data-ttu-id="2e39c-109">この記事では、チームアプリを開発から展開に移動する方法についてのエンドツーエンドのガイダンスについて説明します。</span><span class="sxs-lookup"><span data-stu-id="2e39c-109">This article provides end-to-end guidance for how to take your Teams app from development to deployment to discovery.</span></span> <span data-ttu-id="2e39c-110">このガイダンスは、アプリの Teams の側面を中心としており、管理者と IT プロフェッショナルを対象としています。</span><span class="sxs-lookup"><span data-stu-id="2e39c-110">This guidance focuses on the Teams aspects of the app and is intended for admins and IT pros.</span></span> <span data-ttu-id="2e39c-111">Teams アプリの開発の詳細については、 <a href="https://docs.microsoft.com/microsoftteams/platform" target="_blank">teams の開発者向けドキュメント</a>を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2e39c-111">For more information about developing Teams apps, see the <a href="https://docs.microsoft.com/microsoftteams/platform" target="_blank">Teams developer documentation</a>.</span></span>

![開発から展開までのアプリの概要](media/upload-custom-apps.png)

## <a name="develop"></a><span data-ttu-id="2e39c-113">開発</span><span class="sxs-lookup"><span data-stu-id="2e39c-113">Develop</span></span>

### <a name="create-your-app"></a><span data-ttu-id="2e39c-114">アプリを作成する</span><span class="sxs-lookup"><span data-stu-id="2e39c-114">Create your app</span></span>

<span data-ttu-id="2e39c-115">Microsoft Teams の開発者は、開発者が独自のアプリとサービスを統合して生産性を向上させ、意思決定を迅速化し、既存のコンテンツとワークフローを取り巻くコラボレーションを作成することが容易になります。</span><span class="sxs-lookup"><span data-stu-id="2e39c-115">The Microsoft Teams developer platform makes it easy for developers to integrate your own apps and services to improve productivity, make decisions faster, and create collaboration around existing content and workflows.</span></span> <span data-ttu-id="2e39c-116">Teams プラットフォームで構築されたアプリは、Teams クライアントとサービスとワークフローの間のブリッジであり、コラボレーションプラットフォームのコンテキストに直接移行します。</span><span class="sxs-lookup"><span data-stu-id="2e39c-116">Apps built on the Teams platform are bridges between the Teams client and your services and workflows, bringing them directly into the context of your collaboration platform.</span></span> <span data-ttu-id="2e39c-117">詳細については、「 <a href="https://docs.microsoft.com/microsoftteams/platform" target="_blank">Teams の開発者向けドキュメント</a>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2e39c-117">For more information, go to the <a href="https://docs.microsoft.com/microsoftteams/platform" target="_blank">Teams developer documentation</a>.</span></span>

## <a name="validate"></a><span data-ttu-id="2e39c-118">有効性</span><span class="sxs-lookup"><span data-stu-id="2e39c-118">Validate</span></span>

### <a name="get-the-app-package"></a><span data-ttu-id="2e39c-119">アプリパッケージを取得する</span><span class="sxs-lookup"><span data-stu-id="2e39c-119">Get the app package</span></span>

<span data-ttu-id="2e39c-120">アプリを運用環境で使う準備ができたら、開発者はアプリパッケージを生成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="2e39c-120">When the app is ready for use in production, the developer should produce an app package.</span></span> <span data-ttu-id="2e39c-121">そのためには、<a href="https://docs.microsoft.com/microsoftteams/platform/get-started/get-started-app-studio" target="_blank">アプリ Studio</a>を使うことができます。</span><span class="sxs-lookup"><span data-stu-id="2e39c-121">They can use <a href="https://docs.microsoft.com/microsoftteams/platform/get-started/get-started-app-studio" target="_blank">App Studio</a> for that.</span></span> <span data-ttu-id="2e39c-122">ファイルを .zip 形式で送信します。</span><span class="sxs-lookup"><span data-stu-id="2e39c-122">They'll send you the file in .zip format.</span></span>

<span data-ttu-id="2e39c-123">Microsoft は、<a href="https://docs.microsoft.com/microsoftteams/platform/publishing/office-store-approval" target="_blank">これらのガイドライン</a>を使用して、アプリがグローバルチームアプリストアの品質とセキュリティ標準に準拠していることを確認します。</span><span class="sxs-lookup"><span data-stu-id="2e39c-123">Microsoft uses <a href="https://docs.microsoft.com/microsoftteams/platform/publishing/office-store-approval" target="_blank">these guidelines</a> to ensure apps comply with the quality and security standards of the global Teams apps store.</span></span>

### <a name="allow-trusted-users-to-upload-custom-apps"></a><span data-ttu-id="2e39c-124">信頼されたユーザーによるカスタムアプリのアップロードを許可する</span><span class="sxs-lookup"><span data-stu-id="2e39c-124">Allow trusted users to upload custom apps</span></span>

<span data-ttu-id="2e39c-125">プロダクションテナントでアプリが正常に動作していることを検証するには、ユーザー自身や信頼されたユーザーが、プロダクションテナントでカスタムアプリをアップロードすることを許可する必要があります。</span><span class="sxs-lookup"><span data-stu-id="2e39c-125">To validate that the app is working correctly in your production tenant, you need to allow yourself and/or trusted users to upload custom apps in the production tenant.</span></span> <span data-ttu-id="2e39c-126">これを行うには、<a href="https://docs.microsoft.com/microsoftteams/teams-app-setup-policies" target="_blank">アプリセットアップポリシー</a>を使います。</span><span class="sxs-lookup"><span data-stu-id="2e39c-126">You use <a href="https://docs.microsoft.com/microsoftteams/teams-app-setup-policies" target="_blank">app setup policies</a> to do this.</span></span>

> [!NOTE]
> <span data-ttu-id="2e39c-127">自分や信頼されたユーザーであっても、検証のためにアプリを運用テナントにアップロードすることを希望している場合は、この手順をスキップし、「セクションの[アップロード](#upload)と[設定および管理](#set-up-and-manage)」の手順に従って、unvalidated アプリを組織のアプリストアに公開してください。</span><span class="sxs-lookup"><span data-stu-id="2e39c-127">If you're uncomfortable with uploading the app to your production tenant for validation, even for yourself or trusted users, you can skip this step and follow the steps in the [Upload](#upload) and [Set up and manage](#set-up-and-manage) sections to publish the unvalidated app to your organization's app store.</span></span> <span data-ttu-id="2e39c-128">その後、そのアプリへのアクセスを、信頼できる自分とユーザーのみに制限します。</span><span class="sxs-lookup"><span data-stu-id="2e39c-128">Then, restrict access to that app to only yourself and users you trust.</span></span> <span data-ttu-id="2e39c-129">次に、これらのユーザーは、組織のアプリストアからアプリを取得して検証を実行することができます。</span><span class="sxs-lookup"><span data-stu-id="2e39c-129">These users can then get the app from your organization's app store to perform validation.</span></span> <span data-ttu-id="2e39c-130">アプリを検証した後で、同じアクセス許可ポリシーを使用して access を開き、運用のためにアプリをロールアウトします。</span><span class="sxs-lookup"><span data-stu-id="2e39c-130">After the app is validated, use the same permission policies to open access and roll the app out for production use.</span></span>

<span data-ttu-id="2e39c-131">信頼されたユーザーに対してカスタムアプリのアップロードを許可するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="2e39c-131">To allow trusted users to upload custom apps, follow these steps:</span></span>

1. <span data-ttu-id="2e39c-132">[**カスタムアプリの組織全体での操作を許可する**] 設定をオンにします。</span><span class="sxs-lookup"><span data-stu-id="2e39c-132">Turn on the **Allow interaction with custom apps** org-wide app setting.</span></span> <span data-ttu-id="2e39c-133">その手順は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="2e39c-133">To do this:</span></span>
    1. <span data-ttu-id="2e39c-134">Microsoft Teams 管理センターの左のナビゲーションで、[ **Teams アプリ**の管理] に移動し、  >  **Manage apps**[**組織全体のアプリの設定**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="2e39c-134">In the left navigation of the Microsoft Teams admin center, go to **Teams apps** > **Manage apps**, and then click **Org-wide app settings**.</span></span>
    2. <span data-ttu-id="2e39c-135">[**カスタムアプリ**] の下で、[**カスタムアプリでの操作を許可**する] をオンにし、[**保存**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="2e39c-135">Under **Custom apps**, turn on **Allow interaction with custom apps**, and then click **Save**.</span></span>
2. <span data-ttu-id="2e39c-136">グローバルアプリセットアップポリシーで [**カスタムアプリのアップロード**] 設定をオフにします。</span><span class="sxs-lookup"><span data-stu-id="2e39c-136">Turn off the **Upload custom apps** setting in the global app setup policy.</span></span> <span data-ttu-id="2e39c-137">その手順は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="2e39c-137">To do this:</span></span>
    1. <span data-ttu-id="2e39c-138">Microsoft Teams 管理センターの左のナビゲーションで、[ **Teams アプリ**  >  **セットアップポリシー**] に移動し、[**グローバル (組織全体の既定)** ] ポリシーをクリックします。</span><span class="sxs-lookup"><span data-stu-id="2e39c-138">In the left navigation of the Microsoft Teams admin center, go to **Teams apps** > **Setup policies**, and then click the **Global (Org-wide default)** policy.</span></span>
    2. <span data-ttu-id="2e39c-139">[**カスタムアプリのアップロード**] をオフにして、[**保存**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="2e39c-139">Turn off **Upload custom apps**, and then click **Save**.</span></span>
3. <span data-ttu-id="2e39c-140">カスタムアプリをアップロードして、信頼されたユーザーのセットに割り当てることができる新しいアプリのセットアップポリシーを作成します。</span><span class="sxs-lookup"><span data-stu-id="2e39c-140">Create a new app setup policy that allows uploading custom apps and assign it to your set of trusted users.</span></span> <span data-ttu-id="2e39c-141">その手順は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="2e39c-141">To do this:</span></span>
    1. <span data-ttu-id="2e39c-142">Microsoft Teams 管理センターの左のナビゲーションで、[ **Teams アプリ**  >  **セットアップポリシー**] に移動し、[**追加**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="2e39c-142">In the left navigation of the Microsoft Teams admin center, go to **Teams apps** > **Setup policies**, and then click the **Add**.</span></span> <span data-ttu-id="2e39c-143">新しいポリシーに名前と説明を付け、[**カスタムアプリのアップロード**] をオンにして、[**保存**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="2e39c-143">Give the new policy a name and description, turn on **Upload custom apps**, and then click **Save**.</span></span>
    2. <span data-ttu-id="2e39c-144">作成した新しいポリシーを選択し、[**ユーザーの管理**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="2e39c-144">Select the new policy you created, and then click **Manage users**.</span></span> <span data-ttu-id="2e39c-145">ユーザーを検索し、[**追加**] をクリックして、[**適用**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="2e39c-145">Search for a user, click **Add**, and then click **Apply**.</span></span> <span data-ttu-id="2e39c-146">この手順を繰り返して、すべての信頼できるユーザーにポリシーを割り当てます。</span><span class="sxs-lookup"><span data-stu-id="2e39c-146">Repeat this step to assign the policy to all your trusted users.</span></span>

        ![[アプリセットアップポリシーの追加] ページのスクリーンショット](media/manage-your-lob-apps-new-app-setup-policy.png)

    <span data-ttu-id="2e39c-148">これらのユーザーは、アプリマニフェストをアップロードして、アプリが運用テナントで正常に動作していることを確認できます。</span><span class="sxs-lookup"><span data-stu-id="2e39c-148">These users can now upload the app manifest to validate that the app is working correctly in the production tenant.</span></span>

## <a name="upload"></a><span data-ttu-id="2e39c-149">アルバム</span><span class="sxs-lookup"><span data-stu-id="2e39c-149">Upload</span></span>

<span data-ttu-id="2e39c-150">組織の app store のユーザーがアプリを利用できるようにするには、アプリをアップロードします。</span><span class="sxs-lookup"><span data-stu-id="2e39c-150">To make the app available to users in your organization's app store, upload the app.</span></span> <span data-ttu-id="2e39c-151">これは、Microsoft Teams 管理センターの [<a href="https://docs.microsoft.com/microsoftteams/manage-apps" target="_blank">アプリの管理</a>] ページで行うことができます。</span><span class="sxs-lookup"><span data-stu-id="2e39c-151">You can do this on the <a href="https://docs.microsoft.com/microsoftteams/manage-apps" target="_blank">Manage apps</a> page of the Microsoft Teams admin center.</span></span>

1. <span data-ttu-id="2e39c-152">Microsoft Teams 管理センターの左のナビゲーションで、[ **Teams アプリ**の管理] に移動  >  **Manage apps**します。</span><span class="sxs-lookup"><span data-stu-id="2e39c-152">In the left navigation of the Microsoft Teams admin center, go to **Teams apps** > **Manage apps**.</span></span>
2. <span data-ttu-id="2e39c-153">[**アップロード**] をクリックし、[**ファイルの選択**] をクリックして、開発者から受け取ったアプリパッケージを選択します。</span><span class="sxs-lookup"><span data-stu-id="2e39c-153">Click **Upload**, click **Select a file**, and then select the app package that you received from the developer.</span></span>

   ![管理センターでのアプリのアップロードのスクリーンショット](media/manage-your-lob-apps-upload-new-app.png) 

## <a name="set-up-and-manage"></a><span data-ttu-id="2e39c-155">設定と管理</span><span class="sxs-lookup"><span data-stu-id="2e39c-155">Set up and manage</span></span>

### <a name="control-access-to-the-app"></a><span data-ttu-id="2e39c-156">アプリへのアクセスを制御する</span><span class="sxs-lookup"><span data-stu-id="2e39c-156">Control access to the app</span></span>

<span data-ttu-id="2e39c-157">既定では、組織内のすべてのユーザーが、組織のアプリストアのアプリにアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="2e39c-157">By default, all users in your organization can access the app in your organization's app store.</span></span> <span data-ttu-id="2e39c-158">アプリを使う権限を持つユーザーを制限および制御するには、アプリのアクセス許可ポリシーを作成して割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="2e39c-158">To restrict and control who has permission to use the app, you can create and assign an app permission policy.</span></span> <span data-ttu-id="2e39c-159">詳細については、「 <a href="https://docs.microsoft.com/microsoftteams/teams-app-permission-policies" target="_blank">Teams でアプリのアクセス許可ポリシーを管理</a>する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2e39c-159">To learn more, see <a href="https://docs.microsoft.com/microsoftteams/teams-app-permission-policies" target="_blank">Manage app permission policies in Teams</a>.</span></span>

### <a name="pin-and-install-the-app-for-users-to-discover"></a><span data-ttu-id="2e39c-160">ユーザーが検出できるようにアプリを固定してインストールする</span><span class="sxs-lookup"><span data-stu-id="2e39c-160">Pin and install the app for users to discover</span></span>

<span data-ttu-id="2e39c-161">既定では、ユーザーがアプリを見つけるには、組織のアプリストアに移動し、それを参照または検索する必要があります。</span><span class="sxs-lookup"><span data-stu-id="2e39c-161">By default, for users to find the app they have to go to your organization's app store and browse or search for it.</span></span> <span data-ttu-id="2e39c-162">ユーザーがアプリを簡単に利用できるようにするために、アプリを Teams のアプリバーにピン留めすることができます。</span><span class="sxs-lookup"><span data-stu-id="2e39c-162">To make it easy for users to get to the app, you can pin the app to the app bar in Teams.</span></span> <span data-ttu-id="2e39c-163">これを行うには、アプリのセットアップポリシーを作成し、ユーザーに割り当てます。</span><span class="sxs-lookup"><span data-stu-id="2e39c-163">To do this, create an app setup policy and assign it to users.</span></span> <span data-ttu-id="2e39c-164">詳細については、「 <a href="https://docs.microsoft.com/microsoftteams/teams-app-setup-policies" target="_blank">Teams でアプリセットアップポリシーを管理</a>する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2e39c-164">To learn more, see <a href="https://docs.microsoft.com/microsoftteams/teams-app-setup-policies" target="_blank">Manage app setup policies in Teams</a>.</span></span>

### <a name="search-the-audit-log-for-teams-app-events"></a><span data-ttu-id="2e39c-165">チームアプリイベントの監査ログを検索する</span><span class="sxs-lookup"><span data-stu-id="2e39c-165">Search the audit log for Teams app events</span></span>

<span data-ttu-id="2e39c-166">監査ログを検索して、組織内の Teams アプリのアクティビティを表示できます。</span><span class="sxs-lookup"><span data-stu-id="2e39c-166">You can search the audit log to view Teams apps activity in your organization.</span></span> <span data-ttu-id="2e39c-167">監査ログを検索し、監査ログに記録されている Teams アクティビティの一覧を表示する方法の詳細については、「 <a href="https://docs.microsoft.com/microsoftteams/audit-log-events" target="_blank">Teams のイベントの監査ログを検索</a>する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2e39c-167">To learn more about how to search the audit log and to see a list of Teams activities that are logged in the audit log, see <a href="https://docs.microsoft.com/microsoftteams/audit-log-events" target="_blank">Search the audit log for events in Teams</a>.</span></span>

<span data-ttu-id="2e39c-168">監査ログを検索する前に、まず<a href="https://protection.office.com" target="_blank">セキュリティ & コンプライアンスセンター</a>で監査を有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="2e39c-168">Before you can search the audit log, you have to first turn on auditing in the <a href="https://protection.office.com" target="_blank">Security & Compliance Center</a>.</span></span> <span data-ttu-id="2e39c-169">詳細については、「<a href="https://support.office.com/article/Turn-Office-365-audit-log-search-on-or-off-e893b19a-660c-41f2-9074-d3631c95a014" target="_blank">監査ログの検索を有効または無効に</a>する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2e39c-169">To learn more, see <a href="https://support.office.com/article/Turn-Office-365-audit-log-search-on-or-off-e893b19a-660c-41f2-9074-d3631c95a014" target="_blank">Turn audit log search on or off</a>.</span></span> <span data-ttu-id="2e39c-170">監査データは、監査を有効にした時点でのみ利用可能であることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="2e39c-170">Keep in mind that audit data is only available from the point at which you turned on auditing.</span></span>

## <a name="discover-and-adopt"></a><span data-ttu-id="2e39c-171">発見と採用</span><span class="sxs-lookup"><span data-stu-id="2e39c-171">Discover and adopt</span></span>

<span data-ttu-id="2e39c-172">アプリへのアクセス許可を持つユーザーは、そのアプリを組織のアプリストアで見つけることができます。</span><span class="sxs-lookup"><span data-stu-id="2e39c-172">Users who have permissions to the app can find it in your organization's app store.</span></span> <span data-ttu-id="2e39c-173">[アプリ] ページで [ \***組織名に合わせ\*て作成**済み] に移動して、組織のカスタムアプリを見つけます。</span><span class="sxs-lookup"><span data-stu-id="2e39c-173">Go to **Built for *Your Organization Name*** on the Apps page to find your organization's custom apps.</span></span>

![<span data-ttu-id="2e39c-174">公開されたアプリが表示されている [アプリ] ページのスクリーンショット</span><span class="sxs-lookup"><span data-stu-id="2e39c-174">Screenshot of Apps page showing published app</span></span> ](media/custom-app-lifecycle-discovery.png)

<span data-ttu-id="2e39c-175">アプリのセットアップポリシーを作成して割り当てた場合、アプリは、ポリシーが割り当てられたユーザーに対して簡単にアクセスできるように、Teams のアプリバーに固定されます。</span><span class="sxs-lookup"><span data-stu-id="2e39c-175">If you created and assigned an app setup policy, the app is pinned to the app bar in Teams for easy access for those users who were assigned the policy.</span></span>

## <a name="update"></a><span data-ttu-id="2e39c-176">更新する</span><span class="sxs-lookup"><span data-stu-id="2e39c-176">Update</span></span>

<span data-ttu-id="2e39c-177">アプリを更新するには、開発者はセクション「[開発](#develop)と[検証](#validate)」の手順に従って続行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="2e39c-177">To update an app, developers should continue to follow the steps in the [Develop](#develop) and [Validate](#validate) sections.</span></span>

<span data-ttu-id="2e39c-178">Microsoft Teams 管理センターの [アプリの管理] ページでアプリを更新することができます。</span><span class="sxs-lookup"><span data-stu-id="2e39c-178">You can update the app on the Manage apps page in the Microsoft Teams admin center.</span></span> <span data-ttu-id="2e39c-179">これを行うには、Microsoft Teams 管理センターの左のナビゲーションで、[ **Teams アプリ**の管理] に移動  >  **Manage apps**します。</span><span class="sxs-lookup"><span data-stu-id="2e39c-179">To do this, in the left navigation of the Microsoft Teams admin center, go to **Teams apps** > **Manage apps**.</span></span> <span data-ttu-id="2e39c-180">アプリ名をクリックし、[**更新**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="2e39c-180">Click the app name, and then click **Update**.</span></span> <span data-ttu-id="2e39c-181">この操作を行うと既存のアプリが置き換えられ、アプリのすべてのアクセス許可ポリシーとアプリのセットアップポリシーは、更新されたアプリに適用されたままになります。</span><span class="sxs-lookup"><span data-stu-id="2e39c-181">Doing this replaces the existing app, and all app permission policies and app setup policies remain enforced for the updated app.</span></span>

### <a name="end-user-update-experience"></a><span data-ttu-id="2e39c-182">エンドユーザーによる更新エクスペリエンス</span><span class="sxs-lookup"><span data-stu-id="2e39c-182">End user update experience</span></span>

<span data-ttu-id="2e39c-183">ほとんどの場合、アプリの更新が完了すると、新しいバージョンはエンドユーザーに対して自動的に表示されます。</span><span class="sxs-lookup"><span data-stu-id="2e39c-183">In most cases, after you complete an app update the new version automatically appears for end users.</span></span> <span data-ttu-id="2e39c-184">ただし、 <a href="https://docs.microsoft.com/microsoftteams/platform/resources/schema/manifest-schema" target="_blank">Microsoft Teams マニフェスト</a>には、ユーザーの承認を必要とする次のような更新があります。</span><span class="sxs-lookup"><span data-stu-id="2e39c-184">However, there are some updates to the <a href="https://docs.microsoft.com/microsoftteams/platform/resources/schema/manifest-schema" target="_blank">Microsoft Teams manifest</a> that require user acceptance to complete:</span></span>

* <span data-ttu-id="2e39c-185">ボットが追加または削除された</span><span class="sxs-lookup"><span data-stu-id="2e39c-185">A bot was added or removed</span></span>
* <span data-ttu-id="2e39c-186">既存のボットの "botId" プロパティが変更されました</span><span class="sxs-lookup"><span data-stu-id="2e39c-186">An existing bot's "botId" property changed</span></span>
* <span data-ttu-id="2e39c-187">既存のボットの "isNotificationOnly" プロパティが変更されました</span><span class="sxs-lookup"><span data-stu-id="2e39c-187">An existing bot's "isNotificationOnly" property changed</span></span>
* <span data-ttu-id="2e39c-188">ボットの "supportsFiles" プロパティが変更されました</span><span class="sxs-lookup"><span data-stu-id="2e39c-188">The bot's "supportsFiles" property changed</span></span>
* <span data-ttu-id="2e39c-189">メッセージング拡張機能が追加または削除されました</span><span class="sxs-lookup"><span data-stu-id="2e39c-189">A Messaging extension was added or removed</span></span>
* <span data-ttu-id="2e39c-190">新しいコネクタが追加されました</span><span class="sxs-lookup"><span data-stu-id="2e39c-190">A new connector was added</span></span>
* <span data-ttu-id="2e39c-191">新しい静的タブが追加されました</span><span class="sxs-lookup"><span data-stu-id="2e39c-191">A new static tab was added</span></span>
* <span data-ttu-id="2e39c-192">新しい [構成可能] タブが追加されました</span><span class="sxs-lookup"><span data-stu-id="2e39c-192">A new configurable tab was added</span></span>
* <span data-ttu-id="2e39c-193">"WebApplicationInfo" 内のプロパティが変更されました</span><span class="sxs-lookup"><span data-stu-id="2e39c-193">Properties inside "webApplicationInfo" changed</span></span>

![新しいバージョンが利用可能なアプリが表示されているアプリの一覧のスクリーンショット](media/manage-your-custom-apps-update1.png)

![アプリのアップグレードオプションのスクリーンショット](media/manage-your-custom-apps-update2.png)

## <a name="related-topics"></a><span data-ttu-id="2e39c-196">関連トピック</span><span class="sxs-lookup"><span data-stu-id="2e39c-196">Related topics</span></span>

- [<span data-ttu-id="2e39c-197">Teams アプリ申請 API を通じて送信されたカスタムアプリを公開する</span><span class="sxs-lookup"><span data-stu-id="2e39c-197">Publish a custom app submitted through the Teams App Submission API</span></span>](submit-approve-custom-apps.md)
- [<span data-ttu-id="2e39c-198">Microsoft Teams 管理センターでアプリを管理する</span><span class="sxs-lookup"><span data-stu-id="2e39c-198">Manage your apps in the Microsoft Teams admin center</span></span>](manage-apps.md)
- [<span data-ttu-id="2e39c-199">Teams のカスタム アプリのポリシーと設定を管理する</span><span class="sxs-lookup"><span data-stu-id="2e39c-199">Manage custom app policies and settings in Teams</span></span>](teams-custom-app-policies-and-settings.md)
- [<span data-ttu-id="2e39c-200">Teams のアプリのアクセス許可ポリシーを管理する</span><span class="sxs-lookup"><span data-stu-id="2e39c-200">Manage app permission policies in Teams</span></span>](teams-app-permission-policies.md)
- [<span data-ttu-id="2e39c-201">Teams のアプリのセットアップ ポリシーを管理する</span><span class="sxs-lookup"><span data-stu-id="2e39c-201">Manage app setup policies in Teams</span></span>](teams-app-setup-policies.md)
