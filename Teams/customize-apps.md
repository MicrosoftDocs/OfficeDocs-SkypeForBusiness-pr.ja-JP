---
title: アプリをカスタマイズMicrosoft Teams
author: cichur
ms.author: v-cichur
manager: serdars
ms.reviewer: v-tbasra
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Help
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
description: アプリをカスタマイズする方法については、Microsoft Teams。
ms.openlocfilehash: a43272c19c00079b5a0f0299a5630ca6e6ec78e5
ms.sourcegitcommit: 40f76bc6b5e304faea8516a78f8576ba1cdb7f7c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/12/2021
ms.locfileid: "52337804"
---
# <a name="customize-apps-in-microsoft-teams"></a><span data-ttu-id="6dd10-103">アプリをカスタマイズMicrosoft Teams</span><span class="sxs-lookup"><span data-stu-id="6dd10-103">Customize apps in Microsoft Teams</span></span>

 <span data-ttu-id="6dd10-104">Microsoft Teamsは、アプリのカスタマイズを提供して、エクスペリエンスをTeamsします。</span><span class="sxs-lookup"><span data-stu-id="6dd10-104">Microsoft Teams provides app customization to enhance the Teams experience.</span></span> <span data-ttu-id="6dd10-105">一部のアプリ開発者は、管理者がアプリをカスタマイズTeamsします。管理者は、管理センターの [アプリの管理] ページを使用して、組織のニーズに基づいてTeamsのカスタマイズまたはブランド変更 **を行** えます。</span><span class="sxs-lookup"><span data-stu-id="6dd10-105">Some app developers allow an app to be customized by the Teams admin. The admin can customize or rebrand the app properties based on the organizational needs using the Teams admin center **Manage apps** page.</span></span> <span data-ttu-id="6dd10-106">カスタマイズできる詳細は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="6dd10-106">The details you can customize are:</span></span>

- <span data-ttu-id="6dd10-107">短い名前</span><span class="sxs-lookup"><span data-stu-id="6dd10-107">Short name</span></span>
- <span data-ttu-id="6dd10-108">簡単な説明</span><span class="sxs-lookup"><span data-stu-id="6dd10-108">Short description</span></span>
- <span data-ttu-id="6dd10-109">完全な説明</span><span class="sxs-lookup"><span data-stu-id="6dd10-109">Full description</span></span>
- <span data-ttu-id="6dd10-110">プライバシー ポリシーの URL</span><span class="sxs-lookup"><span data-stu-id="6dd10-110">Privacy policy URL</span></span>
- <span data-ttu-id="6dd10-111">Web サイトの URL</span><span class="sxs-lookup"><span data-stu-id="6dd10-111">Website URL</span></span>
- <span data-ttu-id="6dd10-112">使用条件 URL</span><span class="sxs-lookup"><span data-stu-id="6dd10-112">Terms of use URL</span></span>
- <span data-ttu-id="6dd10-113">[色] アイコン</span><span class="sxs-lookup"><span data-stu-id="6dd10-113">Color icon</span></span>
- <span data-ttu-id="6dd10-114">アウトライン アイコン</span><span class="sxs-lookup"><span data-stu-id="6dd10-114">Outline icon</span></span>
- <span data-ttu-id="6dd10-115">アクセント カラー</span><span class="sxs-lookup"><span data-stu-id="6dd10-115">Accent color</span></span>

<span data-ttu-id="6dd10-116">カスタマイズできる[Teamsの詳細については](https://docs.microsoft.com/microsoftteams/platform/resources/schema/manifest-schema)、マニフェスト スキーマに関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="6dd10-116">See the [Teams Manifest schema](https://docs.microsoft.com/microsoftteams/platform/resources/schema/manifest-schema) for details about the fields that you can customize.</span></span>

> [!NOTE]
> <span data-ttu-id="6dd10-117">現時点では、Government Community Cloud High (GCCH) または国防総省 (DoD) では、アプリのカスタマイズはサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="6dd10-117">Customizing apps isn't supported in Government Community Cloud High (GCCH) or Department of Defense (DoD) at this time.</span></span>

## <a name="customize-the-apps-details"></a><span data-ttu-id="6dd10-118">アプリの詳細をカスタマイズする</span><span class="sxs-lookup"><span data-stu-id="6dd10-118">Customize the app's details</span></span>

<span data-ttu-id="6dd10-119">アプリのカスタマイズを開始するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="6dd10-119">To start customizing an app, complete the following steps:</span></span>

1. <span data-ttu-id="6dd10-120">Teams 管理センターにサインインします。</span><span class="sxs-lookup"><span data-stu-id="6dd10-120">Sign in to the Teams admin center.</span></span>
2. <span data-ttu-id="6dd10-121">[アプリ **Teams展開し、[** アプリの管理]**を選択します**。</span><span class="sxs-lookup"><span data-stu-id="6dd10-121">Expand **Teams Apps** and select **Manage apps**.</span></span>
3. <span data-ttu-id="6dd10-122">アプリの **一覧の [** カスタマイズ可能] 列を確認し、カスタマイズ可能なアプリで並べ替えを行います。</span><span class="sxs-lookup"><span data-stu-id="6dd10-122">Check the **Customizable** column of the apps list and sort by apps that are customizable.</span></span>

   ![並べ替えのカスタマイズ列](media/customize-column.png)

   <span data-ttu-id="6dd10-124">カスタマイズ機能にアクセスするには、次の 3 つのエントリ ポイントがあります。</span><span class="sxs-lookup"><span data-stu-id="6dd10-124">There are three entry points to access the customize feature:</span></span>

   - <span data-ttu-id="6dd10-125">カスタマイズするアプリの横にある を選択し、[カスタマイズ] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="6dd10-125">Select next to the app that you want to customize, and then select **Customize**.</span></span>

     ![選択オプションのカスタマイズ 1](media/select-app-to-customize1.png)

   - <span data-ttu-id="6dd10-127">アプリ名を選択し、[カスタマイズ可能] **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="6dd10-127">Select the app name and then **Customizable**.</span></span>

     ![選択オプションのカスタマイズ 2](media/app-details-customizable.png)

   - <span data-ttu-id="6dd10-129">アプリ名を選択し、[アクション] ドロップダウン **から [カスタマイズ** ] **を選択** します。</span><span class="sxs-lookup"><span data-stu-id="6dd10-129">Select the app name, and then select **Customize** from the **Actions** dropdown.</span></span>

     ![選択オプションのカスタマイズ 3](media/customize-action-menu.png)

4. <span data-ttu-id="6dd10-131">[詳細] **セクションを** 展開し、次のフィールドをカスタマイズします。</span><span class="sxs-lookup"><span data-stu-id="6dd10-131">Expand the **Details** section and customize the following fields:</span></span>

    - <span data-ttu-id="6dd10-132">短い名前</span><span class="sxs-lookup"><span data-stu-id="6dd10-132">Short name</span></span>
    - <span data-ttu-id="6dd10-133">簡単な説明</span><span class="sxs-lookup"><span data-stu-id="6dd10-133">Short description</span></span>
    - <span data-ttu-id="6dd10-134">完全な説明</span><span class="sxs-lookup"><span data-stu-id="6dd10-134">Full description</span></span>
    - <span data-ttu-id="6dd10-135">Web サイト</span><span class="sxs-lookup"><span data-stu-id="6dd10-135">Website</span></span>
    - <span data-ttu-id="6dd10-136">プライバシー ポリシーの URL</span><span class="sxs-lookup"><span data-stu-id="6dd10-136">Privacy policy URL</span></span>
    - <span data-ttu-id="6dd10-137">使用条件 URL</span><span class="sxs-lookup"><span data-stu-id="6dd10-137">Terms of use URL</span></span>

   ![カスタマイズ設定](media/customize-settings.png)

> [!Note]
> <span data-ttu-id="6dd10-139">アプリ開発者がカスタマイズ可能として割り当てたフィールドだけが表示されます。</span><span class="sxs-lookup"><span data-stu-id="6dd10-139">Only the fields that the app developer has assigned as customizable will be visible.</span></span>

5. <span data-ttu-id="6dd10-140">[アイコン] **セクションを** 展開します。</span><span class="sxs-lookup"><span data-stu-id="6dd10-140">Expand the **Icon** section.</span></span>

   <span data-ttu-id="6dd10-141">a.</span><span class="sxs-lookup"><span data-stu-id="6dd10-141">a.</span></span> <span data-ttu-id="6dd10-142">アップロードをクリックします。</span><span class="sxs-lookup"><span data-stu-id="6dd10-142">Upload an icon.</span></span> <span data-ttu-id="6dd10-143">1 つのフルカラー アイコン (192x192) ピクセルを PNG 形式で使用します。</span><span class="sxs-lookup"><span data-stu-id="6dd10-143">Use one full-color icon (192x192) pixel in PNG format.</span></span>

   <span data-ttu-id="6dd10-144">b.</span><span class="sxs-lookup"><span data-stu-id="6dd10-144">b.</span></span> <span data-ttu-id="6dd10-145">アイコンのアウトラインの色を選択します。</span><span class="sxs-lookup"><span data-stu-id="6dd10-145">Choose an icon outline color.</span></span> <span data-ttu-id="6dd10-146">PNG 形式で 1 つの透明なアウトライン (32x32) ピクセルを使用します。</span><span class="sxs-lookup"><span data-stu-id="6dd10-146">Use one transparent outline (32x32) pixel in PNG format.</span></span>

   <span data-ttu-id="6dd10-147">c.</span><span class="sxs-lookup"><span data-stu-id="6dd10-147">c.</span></span> <span data-ttu-id="6dd10-148">アイコンに一致するアプリのアクセント カラーを選択します。</span><span class="sxs-lookup"><span data-stu-id="6dd10-148">Select an app accent color that matches the icon.</span></span>

    ![アイコン パネルの色オプションをカスタマイズする](media/customize-app-colors.png)

6. <span data-ttu-id="6dd10-150">アプリがカスタマイズされた後、[適用] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="6dd10-150">Once your app has been customized, select **Apply**.</span></span>

7. <span data-ttu-id="6dd10-151">[発行 **] を** 選択して、カスタマイズしたアプリを発行します。</span><span class="sxs-lookup"><span data-stu-id="6dd10-151">Select **Publish** to publish the customized app.</span></span>

   <span data-ttu-id="6dd10-152">カスタマイズしたアプリが [アプリの管理] ページ **に表示** されます。</span><span class="sxs-lookup"><span data-stu-id="6dd10-152">The customized app is now listed in your **Manage apps** page.</span></span> <span data-ttu-id="6dd10-153">アプリの機能をカスタマイズしてもアプリのコピーは作成されていないので、アプリのバージョンは 1 つのみです。</span><span class="sxs-lookup"><span data-stu-id="6dd10-153">You'll have only one version of the app, since customizing the app features doesn't create a copy of the app.</span></span>

<span data-ttu-id="6dd10-154">これで、Teamsエンド ユーザーは、カスタマイズされたアプリをTeamsクライアントを開き、カスタマイズされたアプリを表示できます。</span><span class="sxs-lookup"><span data-stu-id="6dd10-154">Now your Teams end users can open their Teams client to see the customized app.</span></span>

   ![カスタム クライアントでのTeamsアプリ](media/contoso-app.png)

### <a name="special-considerations-for-customizing-an-app"></a><span data-ttu-id="6dd10-156">アプリをカスタマイズするための特別な考慮事項</span><span class="sxs-lookup"><span data-stu-id="6dd10-156">Special considerations for customizing an app</span></span>

<span data-ttu-id="6dd10-157">次のメモには、アプリのカスタマイズに関する重要な詳細が含まれています。</span><span class="sxs-lookup"><span data-stu-id="6dd10-157">The following note includes important details about customizing an app.</span></span>

> [!Note]
> - <span data-ttu-id="6dd10-158">アプリとアプリに関連する説明をカスタマイズする場合は、アプリの発行元がドキュメントまたは使用条件で提供する場合は、カスタマイズ ガイドラインに従ってください。</span><span class="sxs-lookup"><span data-stu-id="6dd10-158">When you customize apps, and any description related to an app, ensure that you follow any customization guidelines if provided by the app publisher in their documentation or terms of use.</span></span> <span data-ttu-id="6dd10-159">また、使用するサード パーティのイメージに関する他のユーザーの権利を尊重する責任もあります。</span><span class="sxs-lookup"><span data-stu-id="6dd10-159">You're also responsible for respecting the rights of others regarding any third-party images you might use.</span></span>
> - <span data-ttu-id="6dd10-160">管理者が提供するカスタマイズ データは、最も近いリージョンに格納されます。</span><span class="sxs-lookup"><span data-stu-id="6dd10-160">Admin-provided customization data is stored in the nearest region.</span></span>
> - <span data-ttu-id="6dd10-161">使用条件またはプライバシー ポリシーへのリンクが有効な場合は、お客様が責任を負います。</span><span class="sxs-lookup"><span data-stu-id="6dd10-161">You are responsible for ensuring that links to terms of use or privacy policy are valid.</span></span>
> - <span data-ttu-id="6dd10-162">アプリの発行元がフィールドのカスタマイズを許可しなくなった場合は、アプリの詳細ページに、カスタマイズできないフィールドについて管理者に通知するメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="6dd10-162">In case the app publisher no longer allows a field to be customizable, a message appears on the app details page notifying the admin about the fields that can't be customized any longer.</span></span> <span data-ttu-id="6dd10-163">そのフィールドに加えた変更はすべて、元の値に戻されます。</span><span class="sxs-lookup"><span data-stu-id="6dd10-163">All the changes made to that field will be reverted to the original values.</span></span>
> - <span data-ttu-id="6dd10-164">ユーザーが変更を確認するには、ブランドの変更に最大 24 時間が必要になる場合があります。</span><span class="sxs-lookup"><span data-stu-id="6dd10-164">Changes to branding might require up to 24 hours for the users to see the changes.</span></span>

## <a name="review-app-details"></a><span data-ttu-id="6dd10-165">アプリの詳細を確認する</span><span class="sxs-lookup"><span data-stu-id="6dd10-165">Review app details</span></span>

<span data-ttu-id="6dd10-166">情報を確認するために、アプリの詳細を表示したい場合があります。</span><span class="sxs-lookup"><span data-stu-id="6dd10-166">You might want to see the app details to review the information.</span></span>

1. <span data-ttu-id="6dd10-167">Teams 管理センターにサインインします。</span><span class="sxs-lookup"><span data-stu-id="6dd10-167">Sign in to the Teams admin center.</span></span>

2. <span data-ttu-id="6dd10-168">［**Teams アプリ**］ を開き、［**アプリの管理**］ を選択します。</span><span class="sxs-lookup"><span data-stu-id="6dd10-168">Expand **Teams apps** and select **Manage apps**.</span></span>

3. <span data-ttu-id="6dd10-169">アプリ名を選択します。</span><span class="sxs-lookup"><span data-stu-id="6dd10-169">Select the app name.</span></span>

4. <span data-ttu-id="6dd10-170">元のアプリ名を含むアプリの詳細を表示する 発行元からの **短い名前**。</span><span class="sxs-lookup"><span data-stu-id="6dd10-170">View the app details, including the original app name **Short name from publisher**.</span></span>

   ![アイコン パネル のアプリ名をカスタマイズする](media/original-app-version.png)

   <span data-ttu-id="6dd10-172">[ **発行元の短い** 名前] フィールドは、アプリの短い名前を変更した場合にのみ表示されます。</span><span class="sxs-lookup"><span data-stu-id="6dd10-172">The **Short name from publisher** field is only visible if you've changed the app's short name.</span></span>

## <a name="reset-app-details-to-default"></a><span data-ttu-id="6dd10-173">アプリの詳細を既定にリセットする</span><span class="sxs-lookup"><span data-stu-id="6dd10-173">Reset app details to default</span></span>

<span data-ttu-id="6dd10-174">アプリの詳細は、いつでも元の設定にリセットできます。</span><span class="sxs-lookup"><span data-stu-id="6dd10-174">At any time, you can reset the app details to the original settings.</span></span>

1. <span data-ttu-id="6dd10-175">Teams 管理センターにサインインします。</span><span class="sxs-lookup"><span data-stu-id="6dd10-175">Sign in to the Teams admin center.</span></span>

2. <span data-ttu-id="6dd10-176">[アプリ **Teams展開し、[** アプリの管理]**を選択します**。</span><span class="sxs-lookup"><span data-stu-id="6dd10-176">Expand **Teams Apps** and select **Manage apps**.</span></span>

3. <span data-ttu-id="6dd10-177">アプリ名を選択します。</span><span class="sxs-lookup"><span data-stu-id="6dd10-177">Select the app name.</span></span>

4. <span data-ttu-id="6dd10-178">[アクション **] ドロップダウンから [リセット] を** 選択して既定値 **を設定** します。</span><span class="sxs-lookup"><span data-stu-id="6dd10-178">Select **Reset to default** from the **Actions** dropdown.</span></span>

   ![既定の強調表示にリセットを選択する](media/select-reset.png)

## <a name="frequently-asked-questions"></a><span data-ttu-id="6dd10-180">よく寄せられる質問</span><span class="sxs-lookup"><span data-stu-id="6dd10-180">Frequently asked questions</span></span>

<span data-ttu-id="6dd10-181">**ユーザーがカスタマイズしたアプリを表示するには、どのくらいの時間が必要ですか?**</span><span class="sxs-lookup"><span data-stu-id="6dd10-181">**How long will it take for my users to see the customized app?**</span></span>

<span data-ttu-id="6dd10-182">管理者は管理センターで変更をすぐに確認Teams、エンド ユーザーが変更を確認するには最大 24 時間かかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="6dd10-182">Although the admin can immediately see the changes in Teams Admin Center, it might take up to 24 hours for the end users to see the changes.</span></span>  

<span data-ttu-id="6dd10-183">**アプリ プロバイダーは、顧客のためにアプリをカスタマイズできますか。**</span><span class="sxs-lookup"><span data-stu-id="6dd10-183">**Can the app provider customize the app for its customers?**</span></span>

 <span data-ttu-id="6dd10-184">いいえ。テナントの管理者は、管理センターでテナントのアプリをカスタマイズTeams必要があります。</span><span class="sxs-lookup"><span data-stu-id="6dd10-184">No, the admin of a tenant needs to customize the app for their tenant using the Teams Admin Center.</span></span>

<span data-ttu-id="6dd10-185">**テナント内の現在のカスタム アプリを置き換えるカスタマイズされたアプリは自動的にデプロイされますか?**</span><span class="sxs-lookup"><span data-stu-id="6dd10-185">**Will the customized app automatically get deployed to replace my current custom app in a tenant?**</span></span>

<span data-ttu-id="6dd10-186">いいえ。テナント管理者は、カスタム アプリを手動で削除し、カスタマイズされたバージョンのアプリを発行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6dd10-186">No, the tenant admins will have to manually remove any custom app and publish the customized version of the app.</span></span> <span data-ttu-id="6dd10-187">アプリをカスタマイズし、カスタム アプリとして発行した場合、アプリのカスタマイズ機能を使用してカスタマイズされた新しいアプリは、現在のカスタム アプリに置き換えされません。</span><span class="sxs-lookup"><span data-stu-id="6dd10-187">If you have customized an app and published it as a custom app, the new app customized using the app customization feature won't replace the current custom app.</span></span>  

<span data-ttu-id="6dd10-188">**アプリ使用状況レポートには、カスタマイズされた短い名前などのカスタマイズされた値も表示されますか。**</span><span class="sxs-lookup"><span data-stu-id="6dd10-188">**Will the app usage report also show the customized values such as customized short name?**</span></span>

 <span data-ttu-id="6dd10-189">いいえ。アプリ使用状況レポートには、発行元から送信されたアプリの元の名前が引き続き表示されます。</span><span class="sxs-lookup"><span data-stu-id="6dd10-189">No, the app usage report will still show the original name of the app sent from the publisher.</span></span>

<span data-ttu-id="6dd10-190">**アプリのカスタマイズ機能を使用してカスタマイズできるアプリ**</span><span class="sxs-lookup"><span data-stu-id="6dd10-190">**Which apps can I customize using the app customization feature?**</span></span>

<span data-ttu-id="6dd10-191">カスタマイズできるのは、アプリの発行元がカスタマイズできるアプリのみです。</span><span class="sxs-lookup"><span data-stu-id="6dd10-191">You can only customize apps that have been allowed to be customizable by the app publisher.</span></span> <span data-ttu-id="6dd10-192">アプリの発行元は、顧客がアプリをカスタマイズするためにオプトインする必要があります。</span><span class="sxs-lookup"><span data-stu-id="6dd10-192">The app publisher will need to opt in to allow its customers to customize the app.</span></span>

<span data-ttu-id="6dd10-193">**カスタマイズしたプロパティは、グラフのアクセス許可の同意画面に表示されますか?**</span><span class="sxs-lookup"><span data-stu-id="6dd10-193">**Will the customized properties show up on the graph permission consent screen?**</span></span>

<span data-ttu-id="6dd10-194">いいえ。アクセス許可の同意画面には、発行元から送信された元の値が引き続き表示されます。</span><span class="sxs-lookup"><span data-stu-id="6dd10-194">No, the permission consent screen will still show the original value sent by the publisher.</span></span>

## <a name="related-article"></a><span data-ttu-id="6dd10-195">関連記事</span><span class="sxs-lookup"><span data-stu-id="6dd10-195">Related article</span></span>

- [<span data-ttu-id="6dd10-196">アプリを管理する</span><span class="sxs-lookup"><span data-stu-id="6dd10-196">Manage apps</span></span>](manage-apps.md)
- [<span data-ttu-id="6dd10-197">アプリ ストアをカスタマイズする</span><span class="sxs-lookup"><span data-stu-id="6dd10-197">Customize your app store</span></span>](customize-your-app-store.md)
