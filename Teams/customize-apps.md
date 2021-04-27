---
title: Teams で Microsoft アプリをカスタマイズする
author: cichur
ms.author: v-cichur
manager: serdars
ms.reviewer: vaagarw
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
description: Microsoft Teams でアプリをカスタマイズする方法について説明します。
ROBOTS: NOINDEX, NOFOLLOW
ms.openlocfilehash: 0f61cd0d56c1c050508e9a716ba9846d99d422ad
ms.sourcegitcommit: 5a39061c2156531f4b7f5f69eecf81a8c8b238d0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/27/2021
ms.locfileid: "52030143"
---
# <a name="customize-apps-in-microsoft-teams"></a><span data-ttu-id="b275f-103">Microsoft Teams でアプリをカスタマイズする</span><span class="sxs-lookup"><span data-stu-id="b275f-103">Customize apps in Microsoft Teams</span></span>

[!INCLUDE [preview-feature](includes/preview-feature.md)]

 <span data-ttu-id="b275f-104">Microsoft Teams では、Teams のエクスペリエンスを向上させるアプリのカスタマイズが提供されます。</span><span class="sxs-lookup"><span data-stu-id="b275f-104">Microsoft Teams provides app customization to enhance the Teams experience.</span></span> <span data-ttu-id="b275f-105">一部のアプリ開発者は、Teams 管理者によってアプリをカスタマイズできます。管理者は、Teams 管理センターの [アプリの管理] ページを使用して、組織のニーズに基づいてアプリのプロパティをカスタマイズまたは再 **ブランド** 化できます。</span><span class="sxs-lookup"><span data-stu-id="b275f-105">Some app developers allow an app to be customized by the Teams admin. The admin can customize or rebrand the app properties based on the organizational needs using the Teams admin center **Manage apps** page.</span></span> <span data-ttu-id="b275f-106">カスタマイズできる詳細は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="b275f-106">The details you can customize are:</span></span>

- <span data-ttu-id="b275f-107">短い名前</span><span class="sxs-lookup"><span data-stu-id="b275f-107">Short name</span></span>
- <span data-ttu-id="b275f-108">簡単な説明</span><span class="sxs-lookup"><span data-stu-id="b275f-108">Short description</span></span>
- <span data-ttu-id="b275f-109">完全な説明</span><span class="sxs-lookup"><span data-stu-id="b275f-109">Full description</span></span>
- <span data-ttu-id="b275f-110">プライバシー ポリシーの URL</span><span class="sxs-lookup"><span data-stu-id="b275f-110">Privacy policy URL</span></span>
- <span data-ttu-id="b275f-111">Web サイトの URL</span><span class="sxs-lookup"><span data-stu-id="b275f-111">Website URL</span></span>
- <span data-ttu-id="b275f-112">利用規約の URL</span><span class="sxs-lookup"><span data-stu-id="b275f-112">Terms of use URL</span></span>
- <span data-ttu-id="b275f-113">[色] アイコン</span><span class="sxs-lookup"><span data-stu-id="b275f-113">Color icon</span></span>
- <span data-ttu-id="b275f-114">[アウトライン] アイコン</span><span class="sxs-lookup"><span data-stu-id="b275f-114">Outline icon</span></span>
- <span data-ttu-id="b275f-115">アクセントの色</span><span class="sxs-lookup"><span data-stu-id="b275f-115">Accent color</span></span>

<span data-ttu-id="b275f-116">カスタマイズできる [フィールドの詳細については](https://docs.microsoft.com/microsoftteams/platform/resources/schema/manifest-schema) 、Teams マニフェスト スキーマを参照してください。</span><span class="sxs-lookup"><span data-stu-id="b275f-116">See the [Teams Manifest schema](https://docs.microsoft.com/microsoftteams/platform/resources/schema/manifest-schema) for details about the fields that you can customize.</span></span>

> [!NOTE]
> <span data-ttu-id="b275f-117">現時点では、Government Community Cloud High (GCCH) または国防総省 (DoD) では、アプリのカスタマイズはサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="b275f-117">Customizing apps isn't supported in Government Community Cloud High (GCCH) or Department of Defense (DoD) at this time.</span></span>

## <a name="customize-the-apps-details"></a><span data-ttu-id="b275f-118">アプリの詳細をカスタマイズする</span><span class="sxs-lookup"><span data-stu-id="b275f-118">Customize the app's details</span></span>

<span data-ttu-id="b275f-119">アプリのカスタマイズを開始するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="b275f-119">To start customizing an app, complete the following steps:</span></span>

1. <span data-ttu-id="b275f-120">Teams 管理センターにサインインします。</span><span class="sxs-lookup"><span data-stu-id="b275f-120">Sign in to the Teams admin center.</span></span>
2. <span data-ttu-id="b275f-121">[Teams **Apps] を展開し** 、[アプリの **管理] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="b275f-121">Expand **Teams Apps** and select **Manage apps**.</span></span>
3. <span data-ttu-id="b275f-122">アプリの **一覧の** [カスタマイズ可能] 列を確認し、カスタマイズ可能なアプリで並べ替えを行います。</span><span class="sxs-lookup"><span data-stu-id="b275f-122">Check the **Customizable** column of the apps list and sort by apps that are customizable.</span></span>

   ![並べ替えのカスタマイズ列](media/customize-column.png)

   <span data-ttu-id="b275f-124">カスタマイズ機能にアクセスするには、次の 3 つのエントリ ポイントがあります。</span><span class="sxs-lookup"><span data-stu-id="b275f-124">There are three entry points to access the customize feature:</span></span>

   - <span data-ttu-id="b275f-125">カスタマイズするアプリの横で選択し、[カスタマイズ] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="b275f-125">Select next to the app that you want to customize, and then select **Customize**.</span></span>

     ![[選択のカスタマイズ] オプション 1](media/select-app-to-customize1.png)

   - <span data-ttu-id="b275f-127">アプリ名を選択し、[カスタマイズ可能 **] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="b275f-127">Select the app name and then **Customizable**.</span></span>

     ![[選択のカスタマイズ] オプション 2](media/app-details-customizable.png)

   - <span data-ttu-id="b275f-129">アプリ名を選択し、[アクション] ドロップダウン **から [カスタマイズ** ] **を選択** します。</span><span class="sxs-lookup"><span data-stu-id="b275f-129">Select the app name, and then select **Customize** from the **Actions** dropdown.</span></span>

     ![[選択のカスタマイズ] オプション 3](media/customize-action-menu.png)

4. <span data-ttu-id="b275f-131">[詳細] **セクションを** 展開し、次のフィールドをカスタマイズします。</span><span class="sxs-lookup"><span data-stu-id="b275f-131">Expand the **Details** section and customize the following fields:</span></span>

    - <span data-ttu-id="b275f-132">短い名前</span><span class="sxs-lookup"><span data-stu-id="b275f-132">Short name</span></span>
    - <span data-ttu-id="b275f-133">簡単な説明</span><span class="sxs-lookup"><span data-stu-id="b275f-133">Short description</span></span>
    - <span data-ttu-id="b275f-134">完全な説明</span><span class="sxs-lookup"><span data-stu-id="b275f-134">Full description</span></span>
    - <span data-ttu-id="b275f-135">Web サイト</span><span class="sxs-lookup"><span data-stu-id="b275f-135">Website</span></span>
    - <span data-ttu-id="b275f-136">プライバシー ポリシーの URL</span><span class="sxs-lookup"><span data-stu-id="b275f-136">Privacy policy URL</span></span>
    - <span data-ttu-id="b275f-137">利用規約の URL</span><span class="sxs-lookup"><span data-stu-id="b275f-137">Terms of use URL</span></span>

   ![設定をカスタマイズする](media/customize-settings.png)

> [!Note]
> <span data-ttu-id="b275f-139">アプリ開発者がカスタマイズ可能として割り当てたフィールドだけが表示されます。</span><span class="sxs-lookup"><span data-stu-id="b275f-139">Only the fields that the app developer has assigned as customizable will be visible.</span></span>

5. <span data-ttu-id="b275f-140">[アイコン] **セクションを展開** します。</span><span class="sxs-lookup"><span data-stu-id="b275f-140">Expand the **Icon** section.</span></span>

   <span data-ttu-id="b275f-141">a.</span><span class="sxs-lookup"><span data-stu-id="b275f-141">a.</span></span> <span data-ttu-id="b275f-142">アイコンをアップロードします。</span><span class="sxs-lookup"><span data-stu-id="b275f-142">Upload an icon.</span></span> <span data-ttu-id="b275f-143">1 つのフルカラー アイコン (192x192) ピクセルを PNG 形式で使用します。</span><span class="sxs-lookup"><span data-stu-id="b275f-143">Use one full-color icon (192x192) pixel in PNG format.</span></span>

   <span data-ttu-id="b275f-144">b.</span><span class="sxs-lookup"><span data-stu-id="b275f-144">b.</span></span> <span data-ttu-id="b275f-145">アイコンのアウトラインの色を選択します。</span><span class="sxs-lookup"><span data-stu-id="b275f-145">Choose an icon outline color.</span></span> <span data-ttu-id="b275f-146">PNG 形式で 1 つの透明なアウトライン (32x32) ピクセルを使用します。</span><span class="sxs-lookup"><span data-stu-id="b275f-146">Use one transparent outline (32x32) pixel in PNG format.</span></span>

   <span data-ttu-id="b275f-147">c.</span><span class="sxs-lookup"><span data-stu-id="b275f-147">c.</span></span> <span data-ttu-id="b275f-148">アイコンに一致するアプリのアクセントカラーを選択します。</span><span class="sxs-lookup"><span data-stu-id="b275f-148">Select an app accent color that matches the icon.</span></span>

    ![アイコン パネルの色オプションをカスタマイズする](media/customize-app-colors.png)

6. <span data-ttu-id="b275f-150">アプリをカスタマイズしたら、[適用] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="b275f-150">Once your app has been customized, select **Apply**.</span></span>

7. <span data-ttu-id="b275f-151">[発行 **] を** 選択して、カスタマイズしたアプリを発行します。</span><span class="sxs-lookup"><span data-stu-id="b275f-151">Select **Publish** to publish the customized app.</span></span>

   <span data-ttu-id="b275f-152">カスタマイズしたアプリが [アプリの管理] ページ **に表示** されます。</span><span class="sxs-lookup"><span data-stu-id="b275f-152">The customized app is now listed in your **Manage apps** page.</span></span> <span data-ttu-id="b275f-153">アプリの機能をカスタマイズしてもアプリのコピーは作成できないので、アプリのバージョンは 1 つのみです。</span><span class="sxs-lookup"><span data-stu-id="b275f-153">You'll have only one version of the app, since customizing the app features doesn't create a copy of the app.</span></span>

<span data-ttu-id="b275f-154">これで、Teams エンド ユーザーは Teams クライアントを開き、カスタマイズされたアプリを表示できます。</span><span class="sxs-lookup"><span data-stu-id="b275f-154">Now your Teams end users can open their Teams client to see the customized app.</span></span>

   ![Teams クライアントでカスタマイズされたアプリ](media/contoso-app.png)

### <a name="special-considerations-for-customizing-an-app"></a><span data-ttu-id="b275f-156">アプリをカスタマイズするための特別な考慮事項</span><span class="sxs-lookup"><span data-stu-id="b275f-156">Special considerations for customizing an app</span></span>

<span data-ttu-id="b275f-157">次のノートには、アプリのカスタマイズに関する重要な詳細が含まれています。</span><span class="sxs-lookup"><span data-stu-id="b275f-157">The following note includes important details about customizing an app.</span></span>

> [!Note]
> - <span data-ttu-id="b275f-158">アプリとアプリに関連する説明をカスタマイズする場合は、アプリの発行元がドキュメントまたは使用条件で提供する場合は、カスタマイズガイドラインに従ってください。</span><span class="sxs-lookup"><span data-stu-id="b275f-158">When you customize apps, and any description related to an app, ensure that you follow any customization guidelines if provided by the app publisher in their documentation or terms of use.</span></span> <span data-ttu-id="b275f-159">また、使用する可能性のあるサードパーティの画像に関して、他のユーザーの権利を尊重する責任も負います。</span><span class="sxs-lookup"><span data-stu-id="b275f-159">You're also responsible for respecting the rights of others regarding any third-party images you might use.</span></span>
> - <span data-ttu-id="b275f-160">管理者が指定したカスタマイズ データは、最も近いリージョンに格納されます。</span><span class="sxs-lookup"><span data-stu-id="b275f-160">Admin-provided customization data is stored in the nearest region.</span></span>
> - <span data-ttu-id="b275f-161">利用規約またはプライバシー ポリシーへのリンクが有効な場合は、お客様が責任を負います。</span><span class="sxs-lookup"><span data-stu-id="b275f-161">You are responsible for ensuring that links to terms of use or privacy policy are valid.</span></span>
> - <span data-ttu-id="b275f-162">アプリ発行元がフィールドをカスタマイズできなくなった場合は、アプリの詳細ページに、カスタマイズできないフィールドについて管理者に通知するメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="b275f-162">In case the app publisher no longer allows a field to be customizable, a message appears on the app details page notifying the admin about the fields that can't be customized any longer.</span></span> <span data-ttu-id="b275f-163">そのフィールドに加えた変更はすべて、元の値に戻されます。</span><span class="sxs-lookup"><span data-stu-id="b275f-163">All the changes made to that field will be reverted to the original values.</span></span>
> - <span data-ttu-id="b275f-164">ユーザーが変更を表示するには、ブランドの変更に最大 24 時間が必要になる場合があります。</span><span class="sxs-lookup"><span data-stu-id="b275f-164">Changes to branding might require up to 24 hours for the users to see the changes.</span></span>

## <a name="review-app-details"></a><span data-ttu-id="b275f-165">アプリの詳細を確認する</span><span class="sxs-lookup"><span data-stu-id="b275f-165">Review app details</span></span>

<span data-ttu-id="b275f-166">アプリの詳細を確認して情報を確認したい場合があります。</span><span class="sxs-lookup"><span data-stu-id="b275f-166">You might want to see the app details to review the information.</span></span>

1. <span data-ttu-id="b275f-167">Teams 管理センターにサインインします。</span><span class="sxs-lookup"><span data-stu-id="b275f-167">Sign in to the Teams admin center.</span></span>

2. <span data-ttu-id="b275f-168">［**Teams アプリ**］ を開き、［**アプリの管理**］ を選択します。</span><span class="sxs-lookup"><span data-stu-id="b275f-168">Expand **Teams apps** and select **Manage apps**.</span></span>

3. <span data-ttu-id="b275f-169">アプリ名を選択します。</span><span class="sxs-lookup"><span data-stu-id="b275f-169">Select the app name.</span></span>

4. <span data-ttu-id="b275f-170">元のアプリ名を含むアプリの詳細を表示 **するパブリッシャーからの短い名前**。</span><span class="sxs-lookup"><span data-stu-id="b275f-170">View the app details, including the original app name **Short name from publisher**.</span></span>

   ![アイコン パネルのアプリ名をカスタマイズする](media/original-app-version.png)

   <span data-ttu-id="b275f-172">[ **発行元からの短い** 名前] フィールドは、アプリの短い名前を変更した場合にのみ表示されます。</span><span class="sxs-lookup"><span data-stu-id="b275f-172">The **Short name from publisher** field is only visible if you've changed the app's short name.</span></span>

## <a name="reset-app-details-to-default"></a><span data-ttu-id="b275f-173">アプリの詳細を既定にリセットする</span><span class="sxs-lookup"><span data-stu-id="b275f-173">Reset app details to default</span></span>

<span data-ttu-id="b275f-174">アプリの詳細は、いつでも元の設定にリセットできます。</span><span class="sxs-lookup"><span data-stu-id="b275f-174">At any time, you can reset the app details to the original settings.</span></span>

1. <span data-ttu-id="b275f-175">Teams 管理センターにサインインします。</span><span class="sxs-lookup"><span data-stu-id="b275f-175">Sign in to the Teams admin center.</span></span>

2. <span data-ttu-id="b275f-176">[Teams **Apps] を展開し** 、[アプリの **管理] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="b275f-176">Expand **Teams Apps** and select **Manage apps**.</span></span>

3. <span data-ttu-id="b275f-177">アプリ名を選択します。</span><span class="sxs-lookup"><span data-stu-id="b275f-177">Select the app name.</span></span>

4. <span data-ttu-id="b275f-178">[アクション **] ドロップダウンから [既定値に** リセット] **を選択** します。</span><span class="sxs-lookup"><span data-stu-id="b275f-178">Select **Reset to default** from the **Actions** dropdown.</span></span>

   ![[リセット] を選択して既定の強調表示に戻す](media/select-reset.png)

## <a name="frequently-asked-questions"></a><span data-ttu-id="b275f-180">よく寄せられる質問</span><span class="sxs-lookup"><span data-stu-id="b275f-180">Frequently asked questions</span></span>

<span data-ttu-id="b275f-181">**ユーザーがカスタマイズしたアプリを表示するにはどのくらいの時間が必要ですか?**</span><span class="sxs-lookup"><span data-stu-id="b275f-181">**How long will it take for my users to see the customized app?**</span></span>

<span data-ttu-id="b275f-182">管理者は Teams 管理センターで変更をすぐに確認することができますが、エンド ユーザーが変更を確認するには、最大で 24 時間かかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="b275f-182">Although the admin can immediately see the changes in Teams Admin Center, it might take up to 24 hours for the end users to see the changes.</span></span>  

<span data-ttu-id="b275f-183">**アプリ プロバイダーは、顧客向けアプリをカスタマイズできますか?**</span><span class="sxs-lookup"><span data-stu-id="b275f-183">**Can the app provider customize the app for its customers?**</span></span>

 <span data-ttu-id="b275f-184">いいえ、テナントの管理者は、Teams 管理センターを使用してテナントのアプリをカスタマイズする必要があります。</span><span class="sxs-lookup"><span data-stu-id="b275f-184">No, the admin of a tenant needs to customize the app for their tenant using the Teams Admin Center.</span></span>

<span data-ttu-id="b275f-185">**テナント内の現在のカスタム アプリを置き換えるカスタマイズされたアプリは自動的にデプロイされますか?**</span><span class="sxs-lookup"><span data-stu-id="b275f-185">**Will the customized app automatically get deployed to replace my current custom app in a tenant?**</span></span>

<span data-ttu-id="b275f-186">いいえ、テナント管理者はカスタム アプリを手動で削除し、カスタマイズされたバージョンのアプリを発行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b275f-186">No, the tenant admins will have to manually remove any custom app and publish the customized version of the app.</span></span> <span data-ttu-id="b275f-187">アプリをカスタマイズし、カスタム アプリとして発行した場合、アプリのカスタマイズ機能を使用してカスタマイズされた新しいアプリは、現在のカスタム アプリに置き換えされません。</span><span class="sxs-lookup"><span data-stu-id="b275f-187">If you have customized an app and published it as a custom app, the new app customized using the app customization feature won't replace the current custom app.</span></span>  

<span data-ttu-id="b275f-188">**アプリ使用状況レポートには、カスタマイズされた短い名前などのカスタマイズされた値も表示されますか。**</span><span class="sxs-lookup"><span data-stu-id="b275f-188">**Will the app usage report also show the customized values such as customized short name?**</span></span>

 <span data-ttu-id="b275f-189">いいえ、アプリ使用状況レポートには、発行元から送信されたアプリの元の名前が引き続き表示されます。</span><span class="sxs-lookup"><span data-stu-id="b275f-189">No, the app usage report will still show the original name of the app sent from the publisher.</span></span>

<span data-ttu-id="b275f-190">**アプリのカスタマイズ機能を使用してカスタマイズできるアプリ**</span><span class="sxs-lookup"><span data-stu-id="b275f-190">**Which apps can I customize using the app customization feature?**</span></span>

<span data-ttu-id="b275f-191">カスタマイズできるのは、アプリ発行元がカスタマイズが許可されているアプリのみです。</span><span class="sxs-lookup"><span data-stu-id="b275f-191">You can only customize apps that have been allowed to be customizable by the app publisher.</span></span> <span data-ttu-id="b275f-192">アプリの発行元は、顧客がアプリをカスタマイズすることを許可するためにオプトインする必要があります。</span><span class="sxs-lookup"><span data-stu-id="b275f-192">The app publisher will need to opt in to allow its customers to customize the app.</span></span>

<span data-ttu-id="b275f-193">**カスタマイズされたプロパティは、グラフのアクセス許可の同意画面に表示されますか?**</span><span class="sxs-lookup"><span data-stu-id="b275f-193">**Will the customized properties show up on the graph permission consent screen?**</span></span>

<span data-ttu-id="b275f-194">いいえ、アクセス許可の同意画面には、発行元から送信された元の値が引き続き表示されます。</span><span class="sxs-lookup"><span data-stu-id="b275f-194">No, the permission consent screen will still show the original value sent by the publisher.</span></span>

## <a name="related-article"></a><span data-ttu-id="b275f-195">関連記事</span><span class="sxs-lookup"><span data-stu-id="b275f-195">Related article</span></span>

- [<span data-ttu-id="b275f-196">アプリを管理する</span><span class="sxs-lookup"><span data-stu-id="b275f-196">Manage apps</span></span>](manage-apps.md)
- [<span data-ttu-id="b275f-197">アプリ ストアをカスタマイズする</span><span class="sxs-lookup"><span data-stu-id="b275f-197">Customize your app store</span></span>](customize-your-app-store.md)
