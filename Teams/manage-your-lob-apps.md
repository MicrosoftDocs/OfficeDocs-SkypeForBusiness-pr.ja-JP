---
title: Microsoft Teams で基幹業務アプリを管理する
author: lanachin
ms.author: v-lanac
manager: serdars
ms.reviewer: joglocke
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
description: カスタムチームアプリを開発から展開に移動する方法について説明します。
ms.openlocfilehash: 070b0ecbf0ccc9af798e1d3a3c689ce4d4ff4da2
ms.sourcegitcommit: 10046048a670b66d93e8ac3ba7c3ebc9c3c5fc2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/20/2020
ms.locfileid: "42161828"
---
# <a name="manage-your-line-of-business-apps-in-microsoft-teams"></a><span data-ttu-id="c3647-103">Microsoft Teams で基幹業務アプリを管理する</span><span class="sxs-lookup"><span data-stu-id="c3647-103">Manage your line-of-business apps in Microsoft Teams</span></span>

<span data-ttu-id="c3647-104">この記事では、チームアプリを開発から展開に移動する方法についてのエンドツーエンドのガイダンスを提供します。</span><span class="sxs-lookup"><span data-stu-id="c3647-104">This article provides end-to-end guidance for how to take your Teams app from development to deployment.</span></span> <span data-ttu-id="c3647-105">このガイダンスは、アプリの Teams の側面を中心としており、IT 担当者を対象としています。</span><span class="sxs-lookup"><span data-stu-id="c3647-105">This guidance focuses on the Teams aspects of the app and is intended for IT pros.</span></span> <span data-ttu-id="c3647-106">Teams アプリの開発の詳細については、<a href="https://docs.microsoft.com/microsoftteams/platform" target="_blank">こちら</a>を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c3647-106">For more information on developing Teams apps, see <a href="https://docs.microsoft.com/microsoftteams/platform" target="_blank">here</a>.</span></span>

![開発から展開までのアプリの概要](media/manage-your-lob-apps.png)

## <a name="getting-started"></a><span data-ttu-id="c3647-108">はじめに</span><span class="sxs-lookup"><span data-stu-id="c3647-108">Getting started</span></span>

<span data-ttu-id="c3647-109">Teams で基幹業務 (LOB) アプリを作成して管理するには、2つのテナント (開発用と運用用テナントのテストテナント) が必要です。</span><span class="sxs-lookup"><span data-stu-id="c3647-109">To create and manage line-of-business (LOB) apps in Teams, you’ll need two tenants: a test tenant for development and a production tenant.</span></span>

> [!NOTE]
> <span data-ttu-id="c3647-110">まだテスト用のテナントを作成していない場合は、Office 365 開発者プログラムを使用して、簡単にテスト用のデータを作成し、テストデータに設定することができます。</span><span class="sxs-lookup"><span data-stu-id="c3647-110">If you don’t already have a test tenant, you can quickly create one and populate it with test data using the Office 365 Developer Program.</span></span> <span data-ttu-id="c3647-111"><a href="https://developer.microsoft.com/office/dev-program" target="_blank">詳細はこちら</a>をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="c3647-111"><a href="https://developer.microsoft.com/office/dev-program" target="_blank">Learn more here</a>.</span></span>

## <a name="step-1-develop-and-test"></a><span data-ttu-id="c3647-112">手順 1: 開発とテスト</span><span class="sxs-lookup"><span data-stu-id="c3647-112">Step 1: Develop and test</span></span>

### <a name="create-test-users"></a><span data-ttu-id="c3647-113">テストユーザーを作成する</span><span class="sxs-lookup"><span data-stu-id="c3647-113">Create test users</span></span>

<span data-ttu-id="c3647-114">社内または外部の開発者がテストテナントのアカウントを持っているかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="c3647-114">Make sure that your developers, whether in-house or external, have accounts in your test tenant.</span></span> <span data-ttu-id="c3647-115"><a href="https://docs.microsoft.com/office365/admin/add-users/add-users" target="_blank">詳しく</a>は、「ユーザーの追加」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="c3647-115"><a href="https://docs.microsoft.com/office365/admin/add-users/add-users" target="_blank">Learn more about adding users</a>.</span></span>

### <a name="allow-custom-apps-in-the-test-tenant"></a><span data-ttu-id="c3647-116">テストテナントでカスタムアプリを許可する</span><span class="sxs-lookup"><span data-stu-id="c3647-116">Allow custom apps in the test tenant</span></span>

<span data-ttu-id="c3647-117">テストに必要なアクセス権を開発者に提供するために、テストテナントのすべてのユーザーがカスタムアプリ (サイドローディングとも呼ばれます) をアップロードすることを許可します。</span><span class="sxs-lookup"><span data-stu-id="c3647-117">To give developers the access they need for testing, allow all users in the test tenant to upload custom apps (also known as sideloading).</span></span> <span data-ttu-id="c3647-118">これにより、開発者は、アプリを Teams apps ストアに提出せずに、個人向けまたはテスト用テナント全体で使用するカスタムアプリをアップロードすることができます。</span><span class="sxs-lookup"><span data-stu-id="c3647-118">This lets developers upload a custom app to be used personally or across the test tenant without having to submit the app to the Teams apps store.</span></span> <span data-ttu-id="c3647-119">カスタムアプリをアップロードすると、配布する前に開発者がアプリをテストすることができます。</span><span class="sxs-lookup"><span data-stu-id="c3647-119">Uploading a custom app lets developers test an app before you distribute it more widely.</span></span>

<span data-ttu-id="c3647-120">ユーザーがカスタムアプリをアップロードすることを許可するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="c3647-120">To allow users to upload custom apps, follow these steps:</span></span>

1. <span data-ttu-id="c3647-121">[**カスタムアプリの組織全体での操作を許可する**] 設定をオンにします。</span><span class="sxs-lookup"><span data-stu-id="c3647-121">Turn on the **Allow interaction with custom apps** org-wide app setting.</span></span> <span data-ttu-id="c3647-122">その手順は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="c3647-122">To do this:</span></span>
    1. <span data-ttu-id="c3647-123"><a href="https://admin.teams.microsoft.com/" target="_blank">Microsoft Teams 管理センター</a>の左のナビゲーションで、[ **Teams アプリ** > の**管理**] に移動し、[**組織全体のアプリの設定**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c3647-123">In the left navigation of the <a href="https://admin.teams.microsoft.com/" target="_blank">Microsoft Teams admin center</a>, go to **Teams apps** > **Manage apps**, and then click **Org-wide app settings**.</span></span>
    2. <span data-ttu-id="c3647-124">[**カスタムアプリ**] の下で、[**カスタムアプリでの操作を許可**する] をオンにし、[**保存**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c3647-124">Under **Custom apps**, turn on **Allow interaction with custom apps**, and then click **Save**.</span></span>

    !["カスタムアプリでの操作を許可する" 組織全体でのアプリ設定のスクリーンショット](media/manage-your-lob-apps-org-wide-custom-apps.png)

2. <span data-ttu-id="c3647-126">グローバルアプリセットアップポリシーで [**カスタムアプリのアップロード**] 設定をオンにします。</span><span class="sxs-lookup"><span data-stu-id="c3647-126">Turn on the **Upload custom apps** setting in the global app setup policy.</span></span> <span data-ttu-id="c3647-127">その手順は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="c3647-127">To do this:</span></span>
    1. <span data-ttu-id="c3647-128"><a href="https://admin.teams.microsoft.com/" target="_blank">Microsoft Teams 管理センター</a>の左のナビゲーションで、[ **Teams アプリ** > **セットアップポリシー**] に移動し、[**グローバル (組織全体の既定)** ] ポリシーをクリックします。</span><span class="sxs-lookup"><span data-stu-id="c3647-128">In the left navigation of the <a href="https://admin.teams.microsoft.com/" target="_blank">Microsoft Teams admin center</a>, go to **Teams apps** > **Setup policies**, and then click the **Global (Org-wide default)** policy.</span></span>
    2. <span data-ttu-id="c3647-129">[**カスタムアプリのアップロード**] をオンにし、[**保存**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c3647-129">Turn on **Upload custom apps**, and then click **Save**.</span></span>

    !["カスタムアプリのアップロード" アプリセットアップポリシーの設定のスクリーンショット](media/manage-your-lob-apps-app-setup-custom-apps.png)

> [!NOTE]
> <span data-ttu-id="c3647-131">チームレベルで [カスタムアプリのアップロード] 設定もあります。</span><span class="sxs-lookup"><span data-stu-id="c3647-131">There's also an upload custom app setting at the team level.</span></span> <span data-ttu-id="c3647-132">この設定は既定でオンになっています。</span><span class="sxs-lookup"><span data-stu-id="c3647-132">By default this setting is on.</span></span> <span data-ttu-id="c3647-133">ただし、開発者がカスタムアプリをチームにアップロードできない場合は、次の手順に従って設定を<a href="https://docs.microsoft.com/microsoftteams/teams-custom-app-policies-and-settings#configure-the-team-custom-app-setting" target="_blank">確認します</a>。</span><span class="sxs-lookup"><span data-stu-id="c3647-133">However, if developers are unable to upload a custom app to a team, check the setting by following the steps <a href="https://docs.microsoft.com/microsoftteams/teams-custom-app-policies-and-settings#configure-the-team-custom-app-setting" target="_blank">here</a>.</span></span>

### <a name="create-your-app"></a><span data-ttu-id="c3647-134">アプリを作成する</span><span class="sxs-lookup"><span data-stu-id="c3647-134">Create your app</span></span>

<span data-ttu-id="c3647-135">これで、開発者はアプリを作成するために必要なものを取得できるようになりました。</span><span class="sxs-lookup"><span data-stu-id="c3647-135">Developers should now have what they need to create your app.</span></span> <span data-ttu-id="c3647-136">これについて<a href="https://docs.microsoft.com/microsoftteams/platform" target="_blank">は、こちら</a>をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="c3647-136">See <a href="https://docs.microsoft.com/microsoftteams/platform" target="_blank">here</a> for guidance on that.</span></span>

## <a name="step-2-validate-in-production"></a><span data-ttu-id="c3647-137">手順 2: 運用環境で検証する</span><span class="sxs-lookup"><span data-stu-id="c3647-137">Step 2: Validate in production</span></span>

### <a name="get-the-app-package"></a><span data-ttu-id="c3647-138">アプリパッケージを取得する</span><span class="sxs-lookup"><span data-stu-id="c3647-138">Get the app package</span></span>

<span data-ttu-id="c3647-139">アプリを運用環境で使う準備ができたら、開発者はアプリパッケージを生成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c3647-139">When the app is ready for use in production, the developer should produce an app package.</span></span> <span data-ttu-id="c3647-140">そのためには、<a href="https://docs.microsoft.com/microsoftteams/platform/get-started/get-started-app-studio" target="_blank">アプリ Studio</a>を使うことができます。</span><span class="sxs-lookup"><span data-stu-id="c3647-140">They can use <a href="https://docs.microsoft.com/microsoftteams/platform/get-started/get-started-app-studio" target="_blank">App Studio</a> for that.</span></span> <span data-ttu-id="c3647-141">ファイルを .zip 形式で送信します。</span><span class="sxs-lookup"><span data-stu-id="c3647-141">They'll send you the file in .zip format.</span></span>

<span data-ttu-id="c3647-142">Microsoft は、<a href="https://docs.microsoft.com/microsoftteams/platform/publishing/office-store-approval" target="_blank">これらのガイドライン</a>を使用して、アプリがグローバルチームアプリストアの品質とセキュリティ標準に準拠していることを確認します。</span><span class="sxs-lookup"><span data-stu-id="c3647-142">Microsoft uses <a href="https://docs.microsoft.com/microsoftteams/platform/publishing/office-store-approval" target="_blank">these guidelines</a> to ensure apps comply with the quality and security standards of the global Teams apps store.</span></span>

### <a name="allow-trusted-users-to-upload-custom-apps-in-the-production-tenant"></a><span data-ttu-id="c3647-143">信頼されたユーザーに対して、プロダクションテナントのカスタムアプリのアップロードを許可する</span><span class="sxs-lookup"><span data-stu-id="c3647-143">Allow trusted users to upload custom apps in the production tenant</span></span>

<span data-ttu-id="c3647-144">プロダクションテナントでアプリが正常に動作していることを確認するには、カスタムアプリをアップロードするために、自分と組織の信頼できるユーザーを許可する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c3647-144">To validate that the app is working correctly in your production tenant, you need to allow yourself and/or trusted users in your organization to upload custom apps.</span></span>  <span data-ttu-id="c3647-145">前の<a href="https://docs.microsoft.com/microsoftteams/manage-your-lob-apps#allow-custom-apps-in-the-test-tenant" target="_blank">手順</a>と同じように、アプリセットアップポリシーを使ってこの操作を行います。</span><span class="sxs-lookup"><span data-stu-id="c3647-145">Much like in the earlier <a href="https://docs.microsoft.com/microsoftteams/manage-your-lob-apps#allow-custom-apps-in-the-test-tenant" target="_blank">step</a>, you use app setup policies to do this.</span></span>

> [!NOTE]
> <span data-ttu-id="c3647-146">自分や信頼されたユーザーの場合でも、検証のためにアプリを運用テナントにアップロードすることができない場合は、この手順をスキップして、手順3と4を実行して、unvalidated アプリをテナントアプリストアにアップロードします。</span><span class="sxs-lookup"><span data-stu-id="c3647-146">If you’re uncomfortable with uploading the app to your production tenant for validation, even for yourself or trusted users, you can skip this step and follow steps 3 and 4 to upload the unvalidated app to your tenant app store.</span></span> <span data-ttu-id="c3647-147">その後、そのアプリへのアクセスを、信頼できる自分とユーザーのみに制限します。</span><span class="sxs-lookup"><span data-stu-id="c3647-147">Then, restrict access to that app to only yourself and users you trust.</span></span> <span data-ttu-id="c3647-148">これらのユーザーは、テナントアプリストアからアプリを取得して検証を実行することができます。</span><span class="sxs-lookup"><span data-stu-id="c3647-148">These users can then get the app from the tenant app store to perform validation.</span></span> <span data-ttu-id="c3647-149">アプリを検証した後で、同じアクセス許可ポリシーを使用して access を開き、運用のためにアプリをロールアウトします。</span><span class="sxs-lookup"><span data-stu-id="c3647-149">After the app is validated, use the same permission policies to open access and roll the app out for production use.</span></span>

<span data-ttu-id="c3647-150">信頼されたユーザーに対してカスタムアプリのアップロードを許可するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="c3647-150">To allow trusted users to upload custom apps, follow these steps:</span></span>

1. <span data-ttu-id="c3647-151">[**カスタムアプリの組織全体での操作を許可する**] 設定をオンにします。</span><span class="sxs-lookup"><span data-stu-id="c3647-151">Turn on the **Allow interaction with custom apps** org-wide app setting.</span></span> <span data-ttu-id="c3647-152">その手順は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="c3647-152">To do this:</span></span>
    1. <span data-ttu-id="c3647-153"><a href="https://admin.teams.microsoft.com/" target="_blank">Microsoft Teams 管理センター</a>の左のナビゲーションで、[ **Teams アプリ** > の**管理**] に移動し、[**組織全体のアプリの設定**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c3647-153">In the left navigation of the <a href="https://admin.teams.microsoft.com/" target="_blank">Microsoft Teams admin center</a>, go to **Teams apps** > **Manage apps**, and then click **Org-wide app settings**.</span></span>
    2. <span data-ttu-id="c3647-154">[**カスタムアプリ**] の下で、[**カスタムアプリでの操作を許可**する] をオンにし、[**保存**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c3647-154">Under **Custom apps**, turn on **Allow interaction with custom apps**, and then click **Save**.</span></span>
2. <span data-ttu-id="c3647-155">グローバルアプリセットアップポリシーで [**カスタムアプリのアップロード**] 設定をオフにします。</span><span class="sxs-lookup"><span data-stu-id="c3647-155">Turn off the **Upload custom apps** setting in the global app setup policy.</span></span> <span data-ttu-id="c3647-156">その手順は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="c3647-156">To do this:</span></span>
    1. <span data-ttu-id="c3647-157"><a href="https://admin.teams.microsoft.com/" target="_blank">Microsoft Teams 管理センター</a>の左のナビゲーションで、[ **Teams アプリ** > **セットアップポリシー**] に移動し、[**グローバル (組織全体の既定)** ] ポリシーをクリックします。</span><span class="sxs-lookup"><span data-stu-id="c3647-157">In the left navigation of the <a href="https://admin.teams.microsoft.com/" target="_blank">Microsoft Teams admin center</a>, go to **Teams apps** > **Setup policies**, and then click the **Global (Org-wide default)** policy.</span></span>
    2. <span data-ttu-id="c3647-158">[**カスタムアプリのアップロード**] をオフにして、[**保存**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c3647-158">Turn off **Upload custom apps**, and then click **Save**.</span></span>
3. <span data-ttu-id="c3647-159">カスタムアプリをアップロードして、信頼されたユーザーのセットに割り当てることができる新しいアプリのセットアップポリシーを作成します。</span><span class="sxs-lookup"><span data-stu-id="c3647-159">Create a new app setup policy that allows uploading custom apps and assign it to your set of trusted users.</span></span> <span data-ttu-id="c3647-160">その手順は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="c3647-160">To do this:</span></span>
    1. <span data-ttu-id="c3647-161"><a href="https://admin.teams.microsoft.com/" target="_blank">Microsoft Teams 管理センター</a>の左のナビゲーションで、[ **Teams アプリ** > **セットアップポリシー**] に移動し、[**追加**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c3647-161">In the left navigation of the <a href="https://admin.teams.microsoft.com/" target="_blank">Microsoft Teams admin center</a>, go to **Teams apps** > **Setup policies**, and then click the **Add**.</span></span> <span data-ttu-id="c3647-162">新しいポリシーに名前と説明を付け、[**カスタムアプリのアップロード**] をオンにして、[**保存**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c3647-162">Give the new policy a name and description, turn on **Upload custom apps**, and then click **Save**.</span></span>
    2. <span data-ttu-id="c3647-163">作成した新しいポリシーを選択し、[**ユーザーの管理**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c3647-163">Select the new policy you created, and then click **Manage users**.</span></span> <span data-ttu-id="c3647-164">ユーザーを検索し、[**追加**] をクリックして、[**適用**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c3647-164">Search for a user, click **Add**, and then click **Apply**.</span></span> <span data-ttu-id="c3647-165">この手順を繰り返して、すべての信頼できるユーザーにポリシーを割り当てます。</span><span class="sxs-lookup"><span data-stu-id="c3647-165">Repeat this step to assign the policy to all your trusted users.</span></span>

        ![[アプリセットアップポリシーの追加] ページのスクリーンショット](media/manage-your-lob-apps-new-app-setup-policy.png)

    <span data-ttu-id="c3647-167">これらのユーザーは、アプリマニフェストをアップロードして、アプリが運用テナントで正常に動作していることを確認できます。</span><span class="sxs-lookup"><span data-stu-id="c3647-167">These users can now upload the app manifest to validate that the app is working correctly in the production tenant.</span></span>

## <a name="step-3-upload-to-the-tenant-app-catalog"></a><span data-ttu-id="c3647-168">手順 3: テナントアプリカタログにアップロードする</span><span class="sxs-lookup"><span data-stu-id="c3647-168">Step 3: Upload to the tenant app catalog</span></span>

<span data-ttu-id="c3647-169">テナント app store のユーザーがアプリを利用できるようにするには、アプリをアップロードします。</span><span class="sxs-lookup"><span data-stu-id="c3647-169">To make the app available to users in the tenant app store, upload the app.</span></span> <span data-ttu-id="c3647-170">この操作を行うには、 <a href="https://docs.microsoft.com/microsoftteams/tenant-apps-catalog-teams#go-to-the-tenant-apps-catalog" target="_blank">teams デスクトップクライアント</a>または Microsoft Teams 管理センターの [[アプリの管理](manage-apps.md)] ページを使用します。</span><span class="sxs-lookup"><span data-stu-id="c3647-170">You can do this <a href="https://docs.microsoft.com/microsoftteams/tenant-apps-catalog-teams#go-to-the-tenant-apps-catalog" target="_blank"> using the Teams desktop client</a> or on the [Manage apps](manage-apps.md) page of the Microsoft Teams admin center.</span></span>

<span data-ttu-id="c3647-171">ここでは、Teams デスクトップクライアントの [アップロード] オプションのスクリーンショットを示します。</span><span class="sxs-lookup"><span data-stu-id="c3647-171">Here's a screenshot of the the upload option in the Teams desktop client.</span></span>

![[アプリ] ページのスクリーンショット](media/manage-your-lob-apps-store.png)

<span data-ttu-id="c3647-173">Microsoft Teams 管理センターの [**アプリの管理**] ページの [アップロード] オプションのスクリーンショットを次に示します。</span><span class="sxs-lookup"><span data-stu-id="c3647-173">Here's a screenshot of the upload option on the **Manage apps** page in the Microsoft Teams admin center.</span></span>

![管理センターの [アプリの管理] ページのスクリーンショット](media/manage-your-lob-apps-upload-new-app.png)

## <a name="step-4-configure-and-assign-permissions"></a><span data-ttu-id="c3647-175">手順 4: 権限を構成して割り当てる</span><span class="sxs-lookup"><span data-stu-id="c3647-175">Step 4: Configure and assign permissions</span></span>

### <a name="control-access-to-the-app"></a><span data-ttu-id="c3647-176">アプリへのアクセスを制御する</span><span class="sxs-lookup"><span data-stu-id="c3647-176">Control access to the app</span></span>

<span data-ttu-id="c3647-177">既定では、すべてのユーザーが Teams apps ストアでこのアプリにアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="c3647-177">By default, all users have access to this app in the the Teams apps store.</span></span> <span data-ttu-id="c3647-178">アプリを使用する権限を持つユーザーを制限および制御するには、新しいアプリのアクセス許可ポリシーを作成して割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="c3647-178">To restrict and control who has permission to use the app, you can create and assign a new app permission policy.</span></span> <span data-ttu-id="c3647-179"><a href="https://docs.microsoft.com/microsoftteams/teams-app-permission-policies#create-a-custom-app-permission-policy" target="_blank">次の手順を</a>実行します。</span><span class="sxs-lookup"><span data-stu-id="c3647-179">Follow the steps <a href="https://docs.microsoft.com/microsoftteams/teams-app-permission-policies#create-a-custom-app-permission-policy" target="_blank">here</a>.</span></span>

![[アプリのアクセス許可ポリシーの追加] ページのスクリーンショット](media/manage-your-lob-apps-new-app-permission-policy.png)

### <a name="pin-the-app-for-users-to-discover"></a><span data-ttu-id="c3647-181">ユーザーが検出できるようにアプリを固定する</span><span class="sxs-lookup"><span data-stu-id="c3647-181">Pin the app for users to discover</span></span>

<span data-ttu-id="c3647-182">既定では、ユーザーがこのアプリを見つけるには、Teams アプリストアに移動して、それを参照または検索する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c3647-182">By default, for users to find this app they would have to go to Teams apps store and browse or search for it.</span></span> <span data-ttu-id="c3647-183">ユーザーがアプリを簡単に利用できるようにするために、アプリを Teams のアプリバーにピン留めすることができます。</span><span class="sxs-lookup"><span data-stu-id="c3647-183">To make it easy for users to get to the app, you can pin the app to the app bar in Teams.</span></span> <span data-ttu-id="c3647-184">これを行うには、新しいアプリセットアップポリシーを作成し、ユーザーに割り当てます。</span><span class="sxs-lookup"><span data-stu-id="c3647-184">To do this, create a new app setup policy and assign it to users.</span></span> <span data-ttu-id="c3647-185"><a href="https://docs.microsoft.com/microsoftteams/teams-app-setup-policies#create-a-custom-app-setup-policy" target="_blank">次の手順を</a>実行します。</span><span class="sxs-lookup"><span data-stu-id="c3647-185">Follow the steps  <a href="https://docs.microsoft.com/microsoftteams/teams-app-setup-policies#create-a-custom-app-setup-policy" target="_blank">here</a>.</span></span>

![[固定されたアプリの追加] ウィンドウのスクリーンショット](media/manage-your-lob-apps-pinned-apps.png)

## <a name="step-5-update-the-app"></a><span data-ttu-id="c3647-187">手順 5: アプリを更新する</span><span class="sxs-lookup"><span data-stu-id="c3647-187">Step 5: Update the app</span></span>

![開発から展開までのアプリの概要](media/manage-your-lob-apps-update.png)

<span data-ttu-id="c3647-189">アプリを更新するには、開発者が[手順 1](#step-1-develop-and-test)と[手順 2](#step-2-validate-in-production)に従って続行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c3647-189">To update an app, developers should continue to follow [step 1](#step-1-develop-and-test) and [step 2](#step-2-validate-in-production).</span></span>

<span data-ttu-id="c3647-190">テナントアプリカタログを使用して、アプリを更新することができます。</span><span class="sxs-lookup"><span data-stu-id="c3647-190">You can update the app through the tenant app catalog.</span></span> <span data-ttu-id="c3647-191">これを行うには、Teams デスクトップクライアントで、**テナント名&lt;&gt;用に構築**された**アプリ** > に移動し、[.. **.** ] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c3647-191">To do this, in the Teams desktop client, go to **Apps** > **Built for &lt;Your tenant name&gt;**, click **…**</span></span> <span data-ttu-id="c3647-192">をクリックし、アプリの右上隅にある [**更新**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c3647-192">in the upper-right corner of the app, and then click **Update**.</span></span> <span data-ttu-id="c3647-193">この操作を行うと、テナントアプリカタログの既存のアプリは置き換えられ、すべてのアクセス許可ポリシーとセットアップポリシーは、更新されたアプリに適用されたままになります。</span><span class="sxs-lookup"><span data-stu-id="c3647-193">Doing this replaces the existing app in the tenant app catalog, and all permission policies and setup policies remain enforced for the updated app.</span></span> 

![アプリページ上のアプリの更新のスクリーンショット](media/manage-your-lob-apps-update-app.png)