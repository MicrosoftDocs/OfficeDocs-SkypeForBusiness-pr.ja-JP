---
title: Microsoft Teams 管理センターでカスタム アプリをアップロードする
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
description: Microsoft Teams 管理センターで組織のアプリ ストアにカスタム アプリをアップロードする方法について説明します。
ms.openlocfilehash: f1b5267fe1003d69c0d91349f5b6bc425df2b038
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49831167"
---
# <a name="publish-a-custom-app-by-uploading-an-app-package"></a><span data-ttu-id="35c60-103">アプリ パッケージをアップロードしてカスタム アプリを発行する</span><span class="sxs-lookup"><span data-stu-id="35c60-103">Publish a custom app by uploading an app package</span></span>

> [!NOTE]
> <span data-ttu-id="35c60-104">カスタム Teams アプリを発行すると、組織のアプリ ストアのユーザーが利用できます。</span><span class="sxs-lookup"><span data-stu-id="35c60-104">When you publish a custom Teams app, it's available to users in your organization's app store.</span></span> <span data-ttu-id="35c60-105">カスタム アプリを発行するには 2 つの方法があります。その使い方は、アプリの取得方法によって異なります。</span><span class="sxs-lookup"><span data-stu-id="35c60-105">There are two ways to publish a custom app and the way that you use depends on how you get the app.</span></span> <span data-ttu-id="35c60-106">**この記事では、開発者** から送信されたアプリ パッケージ (.zip 形式) をアップロードしてカスタム アプリを発行する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="35c60-106">**This article focuses on how to publish a custom app by uploading an app package (in .zip format) that a developer sends you**.</span></span> <span data-ttu-id="35c60-107">もう 1 つの方法であるカスタム アプリの承認は、開発者が Teams アプリ提出<a href="https://docs.microsoft.com/microsoftteams/manage-apps" target="_blank"></a>API を使用してアプリを [アプリの管理] ページに直接送信するときに使用します。</span><span class="sxs-lookup"><span data-stu-id="35c60-107">The other method, approving a custom app, is used when a developer submits an app directly to the <a href="https://docs.microsoft.com/microsoftteams/manage-apps" target="_blank">Manage apps</a> page through the Teams App Submission API.</span></span> <span data-ttu-id="35c60-108">この方法の詳細については、「Teams アプリ提出 API を通じて送信されたカスタム アプリを発行する」 <a href="https://docs.microsoft.com/microsoftteams/submit-approve-custom-apps" target="_blank">を参照してください</a>。</span><span class="sxs-lookup"><span data-stu-id="35c60-108">To learn more about that method, see <a href="https://docs.microsoft.com/microsoftteams/submit-approve-custom-apps" target="_blank">Publish a custom app submitted through the Teams App Submission API</a>.</span></span>

<span data-ttu-id="35c60-109">この記事では、Teams アプリを開発から展開から検出に導く方法について、エンドツーエンドのガイダンスを提供します。</span><span class="sxs-lookup"><span data-stu-id="35c60-109">This article provides end-to-end guidance for how to take your Teams app from development to deployment to discovery.</span></span> <span data-ttu-id="35c60-110">このガイダンスでは、アプリの Teams の側面に重点を当て、管理者と IT のプロを対象にしています。</span><span class="sxs-lookup"><span data-stu-id="35c60-110">This guidance focuses on the Teams aspects of the app and is intended for admins and IT pros.</span></span> <span data-ttu-id="35c60-111">Teams アプリの開発の詳細については、Teams の開発者向け <a href="https://docs.microsoft.com/microsoftteams/platform" target="_blank">ドキュメントを参照してください</a>。</span><span class="sxs-lookup"><span data-stu-id="35c60-111">For more information about developing Teams apps, see the <a href="https://docs.microsoft.com/microsoftteams/platform" target="_blank">Teams developer documentation</a>.</span></span>

![開発から展開まで、アプリの概要](media/upload-custom-apps.png)

## <a name="develop"></a><span data-ttu-id="35c60-113">開発</span><span class="sxs-lookup"><span data-stu-id="35c60-113">Develop</span></span>

### <a name="create-your-app"></a><span data-ttu-id="35c60-114">アプリを作成する</span><span class="sxs-lookup"><span data-stu-id="35c60-114">Create your app</span></span>

<span data-ttu-id="35c60-115">Microsoft Teams 開発者プラットフォームを使用すると、開発者は独自のアプリとサービスを簡単に統合して生産性を向上させ、意思決定を迅速に行い、既存のコンテンツとワークフローに関する共同作業を作成できます。</span><span class="sxs-lookup"><span data-stu-id="35c60-115">The Microsoft Teams developer platform makes it easy for developers to integrate your own apps and services to improve productivity, make decisions faster, and create collaboration around existing content and workflows.</span></span> <span data-ttu-id="35c60-116">Teams プラットフォーム上に構築されたアプリは、Teams クライアントとサービスとワークフローの間のブリッジであり、コラボレーション プラットフォームのコンテキストに直接取り込むのです。</span><span class="sxs-lookup"><span data-stu-id="35c60-116">Apps built on the Teams platform are bridges between the Teams client and your services and workflows, bringing them directly into the context of your collaboration platform.</span></span> <span data-ttu-id="35c60-117">詳細については、Teams の開発者向け <a href="https://docs.microsoft.com/microsoftteams/platform" target="_blank">ドキュメントを参照してください</a>。</span><span class="sxs-lookup"><span data-stu-id="35c60-117">For more information, go to the <a href="https://docs.microsoft.com/microsoftteams/platform" target="_blank">Teams developer documentation</a>.</span></span>

## <a name="validate"></a><span data-ttu-id="35c60-118">検証</span><span class="sxs-lookup"><span data-stu-id="35c60-118">Validate</span></span>

### <a name="get-the-app-package"></a><span data-ttu-id="35c60-119">アプリ パッケージを取得する</span><span class="sxs-lookup"><span data-stu-id="35c60-119">Get the app package</span></span>

<span data-ttu-id="35c60-120">アプリを実稼働環境で使用する準備ができたら、開発者はアプリ パッケージを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="35c60-120">When the app is ready for use in production, the developer should produce an app package.</span></span> <span data-ttu-id="35c60-121">その場合 <a href="https://docs.microsoft.com/microsoftteams/platform/get-started/get-started-app-studio" target="_blank">、App Studio</a> を使用できます。</span><span class="sxs-lookup"><span data-stu-id="35c60-121">They can use <a href="https://docs.microsoft.com/microsoftteams/platform/get-started/get-started-app-studio" target="_blank">App Studio</a> for that.</span></span> <span data-ttu-id="35c60-122">ファイルが .zip 形式で送信されます。</span><span class="sxs-lookup"><span data-stu-id="35c60-122">They'll send you the file in .zip format.</span></span>

<span data-ttu-id="35c60-123">Microsoft では <a href="https://docs.microsoft.com/microsoftteams/platform/publishing/office-store-approval" target="_blank">、これらのガイドラインを使用</a> して、アプリがグローバルな Teams アプリ ストアの品質とセキュリティ標準に準拠します。</span><span class="sxs-lookup"><span data-stu-id="35c60-123">Microsoft uses <a href="https://docs.microsoft.com/microsoftteams/platform/publishing/office-store-approval" target="_blank">these guidelines</a> to ensure apps comply with the quality and security standards of the global Teams apps store.</span></span>

### <a name="allow-trusted-users-to-upload-custom-apps"></a><span data-ttu-id="35c60-124">信頼できるユーザーにカスタム アプリのアップロードを許可する</span><span class="sxs-lookup"><span data-stu-id="35c60-124">Allow trusted users to upload custom apps</span></span>

<span data-ttu-id="35c60-125">実稼働テナントでアプリが正しく動作している検証を行う場合は、自分または信頼できるユーザーが実稼働テナントにカスタム アプリをアップロードできる必要があります。</span><span class="sxs-lookup"><span data-stu-id="35c60-125">To validate that the app is working correctly in your production tenant, you need to allow yourself and/or trusted users to upload custom apps in the production tenant.</span></span> <span data-ttu-id="35c60-126">これを行 <a href="https://docs.microsoft.com/microsoftteams/teams-app-setup-policies" target="_blank">うには、アプリセットアップ</a> ポリシーを使用します。</span><span class="sxs-lookup"><span data-stu-id="35c60-126">You use <a href="https://docs.microsoft.com/microsoftteams/teams-app-setup-policies" target="_blank">app setup policies</a> to do this.</span></span>

> [!NOTE]
> <span data-ttu-id="35c60-127">検証のために実稼働テナントにアプリをアップロードしても、検証に不安がある場合は、この手順をスキップし、「アップロードとセットアップ、管理」セクションの手順に従[](#upload)って、[](#set-up-and-manage)組織のアプリ ストアに評価されていないアプリを発行します。</span><span class="sxs-lookup"><span data-stu-id="35c60-127">If you're uncomfortable with uploading the app to your production tenant for validation, even for yourself or trusted users, you can skip this step and follow the steps in the [Upload](#upload) and [Set up and manage](#set-up-and-manage) sections to publish the unvalidated app to your organization's app store.</span></span> <span data-ttu-id="35c60-128">その後、そのアプリへのアクセスを自分と信頼するユーザーにのみ制限します。</span><span class="sxs-lookup"><span data-stu-id="35c60-128">Then, restrict access to that app to only yourself and users you trust.</span></span> <span data-ttu-id="35c60-129">これらのユーザーは、組織のアプリ ストアからアプリを取得して検証を実行できます。</span><span class="sxs-lookup"><span data-stu-id="35c60-129">These users can then get the app from your organization's app store to perform validation.</span></span> <span data-ttu-id="35c60-130">アプリが検証された後は、同じアクセス許可ポリシーを使用してアクセスを開き、実稼働用にアプリをロールアウトします。</span><span class="sxs-lookup"><span data-stu-id="35c60-130">After the app is validated, use the same permission policies to open access and roll the app out for production use.</span></span>

<span data-ttu-id="35c60-131">信頼できるユーザーがカスタム アプリをアップロードするには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="35c60-131">To allow trusted users to upload custom apps, follow these steps:</span></span>

1. <span data-ttu-id="35c60-132">カスタム アプリの **組織全体のアプリの操作を許可** する設定を有効にします。</span><span class="sxs-lookup"><span data-stu-id="35c60-132">Turn on the **Allow interaction with custom apps** org-wide app setting.</span></span> <span data-ttu-id="35c60-133">その手順は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="35c60-133">To do this:</span></span>
    1. <span data-ttu-id="35c60-134">Microsoft Teams 管理センターの左側のナビゲーションで **、Teams** アプリの [アプリの管理] に移動し、[組織全体のアプリ設定] を  >  **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="35c60-134">In the left navigation of the Microsoft Teams admin center, go to **Teams apps** > **Manage apps**, and then click **Org-wide app settings**.</span></span>
    2. <span data-ttu-id="35c60-135">[ **カスタム アプリ] で**、[カスタム アプリとの **対話を許可する] を** オンにし、[保存] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="35c60-135">Under **Custom apps**, turn on **Allow interaction with custom apps**, and then click **Save**.</span></span>
2. <span data-ttu-id="35c60-136">グローバル アプリ セットアップ **ポリシーの [カスタム アプリの** アップロード] 設定をオフにします。</span><span class="sxs-lookup"><span data-stu-id="35c60-136">Turn off the **Upload custom apps** setting in the global app setup policy.</span></span> <span data-ttu-id="35c60-137">その手順は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="35c60-137">To do this:</span></span>
    1. <span data-ttu-id="35c60-138">Microsoft Teams 管理センターの左側のナビゲーションで **、Teams アプリ** のセットアップ ポリシーに移動し、グローバル (組織全体の既定) ポリシーを  >  **クリック** します。</span><span class="sxs-lookup"><span data-stu-id="35c60-138">In the left navigation of the Microsoft Teams admin center, go to **Teams apps** > **Setup policies**, and then click the **Global (Org-wide default)** policy.</span></span>
    2. <span data-ttu-id="35c60-139">カスタム アプリの **アップロードをオフにし、[** 保存] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="35c60-139">Turn off **Upload custom apps**, and then click **Save**.</span></span>
3. <span data-ttu-id="35c60-140">カスタム アプリのアップロードを許可する新しいアプリ セットアップ ポリシーを作成し、信頼できるユーザーのセットに割り当てる。</span><span class="sxs-lookup"><span data-stu-id="35c60-140">Create a new app setup policy that allows uploading custom apps and assign it to your set of trusted users.</span></span> <span data-ttu-id="35c60-141">その手順は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="35c60-141">To do this:</span></span>
    1. <span data-ttu-id="35c60-142">Microsoft Teams 管理センターの左側のナビゲーションで **、Teams アプリのセットアップ** ポリシーに移動し、[追加]  >  をクリック **します**。</span><span class="sxs-lookup"><span data-stu-id="35c60-142">In the left navigation of the Microsoft Teams admin center, go to **Teams apps** > **Setup policies**, and then click the **Add**.</span></span> <span data-ttu-id="35c60-143">新しいポリシーに名前と説明を付け、[カスタム アプリのアップロード] をオンにし、[保存] をクリック **します**。</span><span class="sxs-lookup"><span data-stu-id="35c60-143">Give the new policy a name and description, turn on **Upload custom apps**, and then click **Save**.</span></span>
    2. <span data-ttu-id="35c60-144">作成した新しいポリシーを選択し、[ユーザーの管理] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="35c60-144">Select the new policy you created, and then click **Manage users**.</span></span> <span data-ttu-id="35c60-145">ユーザーを検索し、[追加] を **クリックし**、[適用] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="35c60-145">Search for a user, click **Add**, and then click **Apply**.</span></span> <span data-ttu-id="35c60-146">すべての信頼できるユーザーにポリシーを割り当てるには、この手順を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="35c60-146">Repeat this step to assign the policy to all your trusted users.</span></span>

        ![[アプリセットアップ ポリシーの追加] ページのスクリーンショット](media/manage-your-lob-apps-new-app-setup-policy.png)

    <span data-ttu-id="35c60-148">これらのユーザーは、アプリ マニフェストをアップロードして、実稼働テナントでアプリが正しく動作しているのを確認できます。</span><span class="sxs-lookup"><span data-stu-id="35c60-148">These users can now upload the app manifest to validate that the app is working correctly in the production tenant.</span></span>

## <a name="upload"></a><span data-ttu-id="35c60-149">アップロード</span><span class="sxs-lookup"><span data-stu-id="35c60-149">Upload</span></span>

<span data-ttu-id="35c60-150">組織のアプリ ストアのユーザーがアプリを利用するには、アプリをアップロードします。</span><span class="sxs-lookup"><span data-stu-id="35c60-150">To make the app available to users in your organization's app store, upload the app.</span></span> <span data-ttu-id="35c60-151">これは、Microsoft Teams 管理センター <a href="https://docs.microsoft.com/microsoftteams/manage-apps" target="_blank">の [</a> アプリの管理] ページで行います。</span><span class="sxs-lookup"><span data-stu-id="35c60-151">You can do this on the <a href="https://docs.microsoft.com/microsoftteams/manage-apps" target="_blank">Manage apps</a> page of the Microsoft Teams admin center.</span></span>

1. <span data-ttu-id="35c60-152">Microsoft Teams 管理センターの左側のナビゲーションで、Teams アプリの [アプリの **管理]**  >  **に移動します**。</span><span class="sxs-lookup"><span data-stu-id="35c60-152">In the left navigation of the Microsoft Teams admin center, go to **Teams apps** > **Manage apps**.</span></span>
2. <span data-ttu-id="35c60-153">[ **アップロード]** をクリックし **、[ファイルの選択**] をクリックして、開発者から受け取ったアプリ パッケージを選択します。</span><span class="sxs-lookup"><span data-stu-id="35c60-153">Click **Upload**, click **Select a file**, and then select the app package that you received from the developer.</span></span>

   ![管理センターでのアプリのアップロードのスクリーンショット](media/manage-your-lob-apps-upload-new-app.png) 

## <a name="set-up-and-manage"></a><span data-ttu-id="35c60-155">セットアップと管理</span><span class="sxs-lookup"><span data-stu-id="35c60-155">Set up and manage</span></span>

### <a name="control-access-to-the-app"></a><span data-ttu-id="35c60-156">アプリへのアクセスを制御する</span><span class="sxs-lookup"><span data-stu-id="35c60-156">Control access to the app</span></span>

<span data-ttu-id="35c60-157">既定では、組織内のすべてのユーザーは、組織のアプリ ストアでアプリにアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="35c60-157">By default, all users in your organization can access the app in your organization's app store.</span></span> <span data-ttu-id="35c60-158">アプリを使用するアクセス許可を持つユーザーを制限および制御するには、アプリのアクセス許可ポリシーを作成して割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="35c60-158">To restrict and control who has permission to use the app, you can create and assign an app permission policy.</span></span> <span data-ttu-id="35c60-159">詳細については、「Teams でアプリ <a href="https://docs.microsoft.com/microsoftteams/teams-app-permission-policies" target="_blank">のアクセス許可ポリシーを管理する」を参照してください</a>。</span><span class="sxs-lookup"><span data-stu-id="35c60-159">To learn more, see <a href="https://docs.microsoft.com/microsoftteams/teams-app-permission-policies" target="_blank">Manage app permission policies in Teams</a>.</span></span>

### <a name="pin-and-install-the-app-for-users-to-discover"></a><span data-ttu-id="35c60-160">ユーザーが検出するアプリをピン留めしてインストールする</span><span class="sxs-lookup"><span data-stu-id="35c60-160">Pin and install the app for users to discover</span></span>

<span data-ttu-id="35c60-161">既定では、ユーザーが組織のアプリ ストアにアクセスしてアプリを参照または検索する必要があるアプリを見つける場合。</span><span class="sxs-lookup"><span data-stu-id="35c60-161">By default, for users to find the app they have to go to your organization's app store and browse or search for it.</span></span> <span data-ttu-id="35c60-162">ユーザーが簡単にアプリにアクセスするには、アプリを Teams のアプリ バーにピン留めします。</span><span class="sxs-lookup"><span data-stu-id="35c60-162">To make it easy for users to get to the app, you can pin the app to the app bar in Teams.</span></span> <span data-ttu-id="35c60-163">これを行うには、アプリセットアップ ポリシーを作成し、ユーザーに割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="35c60-163">To do this, create an app setup policy and assign it to users.</span></span> <span data-ttu-id="35c60-164">詳細については、「Teams でアプリ <a href="https://docs.microsoft.com/microsoftteams/teams-app-setup-policies" target="_blank">セットアップ ポリシーを管理する」を参照してください</a>。</span><span class="sxs-lookup"><span data-stu-id="35c60-164">To learn more, see <a href="https://docs.microsoft.com/microsoftteams/teams-app-setup-policies" target="_blank">Manage app setup policies in Teams</a>.</span></span>

### <a name="search-the-audit-log-for-teams-app-events"></a><span data-ttu-id="35c60-165">Teams アプリ イベントの監査ログを検索する</span><span class="sxs-lookup"><span data-stu-id="35c60-165">Search the audit log for Teams app events</span></span>

<span data-ttu-id="35c60-166">監査ログを検索して、組織内の Teams アプリのアクティビティを表示できます。</span><span class="sxs-lookup"><span data-stu-id="35c60-166">You can search the audit log to view Teams apps activity in your organization.</span></span> <span data-ttu-id="35c60-167">監査ログを検索する方法と、監査ログに記録されている Teams アクティビティの一覧を表示する方法の詳細については <a href="https://docs.microsoft.com/microsoftteams/audit-log-events" target="_blank">、「Teams</a>でイベントの監査ログを検索する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="35c60-167">To learn more about how to search the audit log and to see a list of Teams activities that are logged in the audit log, see <a href="https://docs.microsoft.com/microsoftteams/audit-log-events" target="_blank">Search the audit log for events in Teams</a>.</span></span>

<span data-ttu-id="35c60-168">監査ログを検索するには、まずセキュリティ/コンプライアンス センターで監査 <a href="https://protection.office.com" target="_blank">&があります</a>。</span><span class="sxs-lookup"><span data-stu-id="35c60-168">Before you can search the audit log, you have to first turn on auditing in the <a href="https://protection.office.com" target="_blank">Security & Compliance Center</a>.</span></span> <span data-ttu-id="35c60-169">詳細については、「監査ログの検索 <a href="https://support.office.com/article/Turn-Office-365-audit-log-search-on-or-off-e893b19a-660c-41f2-9074-d3631c95a014" target="_blank">を有効またはオフにする」を参照してください</a>。</span><span class="sxs-lookup"><span data-stu-id="35c60-169">To learn more, see <a href="https://support.office.com/article/Turn-Office-365-audit-log-search-on-or-off-e893b19a-660c-41f2-9074-d3631c95a014" target="_blank">Turn audit log search on or off</a>.</span></span> <span data-ttu-id="35c60-170">監査データは、監査を有効にした時点からのみ利用できます。</span><span class="sxs-lookup"><span data-stu-id="35c60-170">Keep in mind that audit data is only available from the point at which you turned on auditing.</span></span>

## <a name="discover-and-adopt"></a><span data-ttu-id="35c60-171">検出して採用する</span><span class="sxs-lookup"><span data-stu-id="35c60-171">Discover and adopt</span></span>

<span data-ttu-id="35c60-172">アプリへのアクセス許可を持つユーザーは、組織のアプリ ストアで見つける可能性があります。</span><span class="sxs-lookup"><span data-stu-id="35c60-172">Users who have permissions to the app can find it in your organization's app store.</span></span> <span data-ttu-id="35c60-173">組織の **カスタム アプリを *見つける*** には、[アプリ] ページで [組織名のビルド] に移動します。</span><span class="sxs-lookup"><span data-stu-id="35c60-173">Go to **Built for *Your Organization Name*** on the Apps page to find your organization's custom apps.</span></span>

![<span data-ttu-id="35c60-174">公開済みアプリを示す [アプリ] ページのスクリーンショット</span><span class="sxs-lookup"><span data-stu-id="35c60-174">Screenshot of Apps page showing published app</span></span> ](media/custom-app-lifecycle-discovery.png)

<span data-ttu-id="35c60-175">アプリセットアップ ポリシーを作成して割り当てた場合、アプリは Teams のアプリ バーにピン留めされ、ポリシーが割り当てられたユーザーが簡単にアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="35c60-175">If you created and assigned an app setup policy, the app is pinned to the app bar in Teams for easy access for those users who were assigned the policy.</span></span>

## <a name="update"></a><span data-ttu-id="35c60-176">更新</span><span class="sxs-lookup"><span data-stu-id="35c60-176">Update</span></span>

<span data-ttu-id="35c60-177">アプリを更新するには、開発と検証のセクションの手順に引き[](#develop)続き[従う](#validate)必要があります。</span><span class="sxs-lookup"><span data-stu-id="35c60-177">To update an app, developers should continue to follow the steps in the [Develop](#develop) and [Validate](#validate) sections.</span></span>

<span data-ttu-id="35c60-178">Microsoft Teams 管理センターの [アプリの管理] ページでアプリを更新できます。</span><span class="sxs-lookup"><span data-stu-id="35c60-178">You can update the app on the Manage apps page in the Microsoft Teams admin center.</span></span> <span data-ttu-id="35c60-179">これを行うには、Microsoft Teams 管理センターの左側のナビゲーションで **、Teams** アプリの [アプリの管理] に  >  **移動します**。</span><span class="sxs-lookup"><span data-stu-id="35c60-179">To do this, in the left navigation of the Microsoft Teams admin center, go to **Teams apps** > **Manage apps**.</span></span> <span data-ttu-id="35c60-180">アプリ名をクリックし、[更新] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="35c60-180">Click the app name, and then click **Update**.</span></span> <span data-ttu-id="35c60-181">この設定を行った場合、既存のアプリが置き換わるので、すべてのアプリのアクセス許可ポリシーとアプリセットアップ ポリシーは、更新されたアプリに適用されたままです。</span><span class="sxs-lookup"><span data-stu-id="35c60-181">Doing this replaces the existing app, and all app permission policies and app setup policies remain enforced for the updated app.</span></span>

### <a name="end-user-update-experience"></a><span data-ttu-id="35c60-182">エンド ユーザーの更新エクスペリエンス</span><span class="sxs-lookup"><span data-stu-id="35c60-182">End user update experience</span></span>

<span data-ttu-id="35c60-183">ほとんどの場合、アプリの更新を完了すると、エンド ユーザーに新しいバージョンが自動的に表示されます。</span><span class="sxs-lookup"><span data-stu-id="35c60-183">In most cases, after you complete an app update the new version automatically appears for end users.</span></span> <span data-ttu-id="35c60-184">ただし、Microsoft <a href="https://docs.microsoft.com/microsoftteams/platform/resources/schema/manifest-schema" target="_blank">Teams</a> マニフェストには、完了するためにユーザーの同意が必要な更新プログラムがあります。</span><span class="sxs-lookup"><span data-stu-id="35c60-184">However, there are some updates to the <a href="https://docs.microsoft.com/microsoftteams/platform/resources/schema/manifest-schema" target="_blank">Microsoft Teams manifest</a> that require user acceptance to complete:</span></span>

* <span data-ttu-id="35c60-185">ボットが追加または削除されました</span><span class="sxs-lookup"><span data-stu-id="35c60-185">A bot was added or removed</span></span>
* <span data-ttu-id="35c60-186">既存のボットの "botId" プロパティが変更されました</span><span class="sxs-lookup"><span data-stu-id="35c60-186">An existing bot's "botId" property changed</span></span>
* <span data-ttu-id="35c60-187">既存のボットの "isNotificationOnly" プロパティが変更されました</span><span class="sxs-lookup"><span data-stu-id="35c60-187">An existing bot's "isNotificationOnly" property changed</span></span>
* <span data-ttu-id="35c60-188">ボットの "supportsFiles" プロパティが変更されました</span><span class="sxs-lookup"><span data-stu-id="35c60-188">The bot's "supportsFiles" property changed</span></span>
* <span data-ttu-id="35c60-189">メッセージング拡張機能が追加または削除されました</span><span class="sxs-lookup"><span data-stu-id="35c60-189">A Messaging extension was added or removed</span></span>
* <span data-ttu-id="35c60-190">新しいコネクタが追加されました</span><span class="sxs-lookup"><span data-stu-id="35c60-190">A new connector was added</span></span>
* <span data-ttu-id="35c60-191">新しい静的タブが追加されました</span><span class="sxs-lookup"><span data-stu-id="35c60-191">A new static tab was added</span></span>
* <span data-ttu-id="35c60-192">新しい構成可能なタブが追加されました</span><span class="sxs-lookup"><span data-stu-id="35c60-192">A new configurable tab was added</span></span>
* <span data-ttu-id="35c60-193">"webApplicationInfo" 内のプロパティが変更されました</span><span class="sxs-lookup"><span data-stu-id="35c60-193">Properties inside "webApplicationInfo" changed</span></span>

![新しいバージョンが利用可能なアプリを示すアプリ一覧のスクリーンショット](media/manage-your-custom-apps-update1.png)

![アプリのアップグレード オプションのスクリーンショット](media/manage-your-custom-apps-update2.png)

## <a name="related-topics"></a><span data-ttu-id="35c60-196">関連項目</span><span class="sxs-lookup"><span data-stu-id="35c60-196">Related topics</span></span>

- [<span data-ttu-id="35c60-197">Teams アプリ提出 API を通じて送信されたカスタム アプリを発行する</span><span class="sxs-lookup"><span data-stu-id="35c60-197">Publish a custom app submitted through the Teams App Submission API</span></span>](submit-approve-custom-apps.md)
- [<span data-ttu-id="35c60-198">Microsoft Teams 管理センターでアプリを管理する</span><span class="sxs-lookup"><span data-stu-id="35c60-198">Manage your apps in the Microsoft Teams admin center</span></span>](manage-apps.md)
- [<span data-ttu-id="35c60-199">Teams のカスタム アプリのポリシーと設定を管理する</span><span class="sxs-lookup"><span data-stu-id="35c60-199">Manage custom app policies and settings in Teams</span></span>](teams-custom-app-policies-and-settings.md)
- [<span data-ttu-id="35c60-200">Teams のアプリのアクセス許可ポリシーを管理する</span><span class="sxs-lookup"><span data-stu-id="35c60-200">Manage app permission policies in Teams</span></span>](teams-app-permission-policies.md)
- [<span data-ttu-id="35c60-201">Teams のアプリのセットアップ ポリシーを管理する</span><span class="sxs-lookup"><span data-stu-id="35c60-201">Manage app setup policies in Teams</span></span>](teams-app-setup-policies.md)
