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
ms.openlocfilehash: a87ce5f7dd63a78af4a7a1ea5f56aed1cad7263a
ms.sourcegitcommit: 2bb8556650120b4f7cf509d8ff93d7e4d058829b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/02/2021
ms.locfileid: "51574156"
---
# <a name="customize-apps-in-microsoft-teams"></a><span data-ttu-id="31aa3-103">Microsoft Teams でアプリをカスタマイズする</span><span class="sxs-lookup"><span data-stu-id="31aa3-103">Customize apps in Microsoft Teams</span></span>

[!INCLUDE [preview-feature](includes/preview-feature.md)]

 <span data-ttu-id="31aa3-104">Microsoft Teams は、Teams のエクスペリエンスを向上させるアプリのカスタマイズを提供します。</span><span class="sxs-lookup"><span data-stu-id="31aa3-104">Microsoft Teams provides app customization to enhance the Teams experience.</span></span> <span data-ttu-id="31aa3-105">一部のアプリ開発者は、Teams 管理者がアプリをカスタマイズできます。管理者は、Teams 管理センターの [アプリの管理] ページを使用して、組織のニーズに基づいてアプリのプロパティをカスタマイズまたは **ブランド変更** できます。</span><span class="sxs-lookup"><span data-stu-id="31aa3-105">Some app developers allow an app to be customized by the Teams admin. The admin can customize or rebrand the app properties based on the organizational needs using the Teams admin center **Manage apps** page.</span></span> <span data-ttu-id="31aa3-106">カスタマイズできる詳細は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="31aa3-106">The details you can customize are:</span></span>

- <span data-ttu-id="31aa3-107">短い名前</span><span class="sxs-lookup"><span data-stu-id="31aa3-107">Short name</span></span>
- <span data-ttu-id="31aa3-108">簡単な説明</span><span class="sxs-lookup"><span data-stu-id="31aa3-108">Short description</span></span>
- <span data-ttu-id="31aa3-109">完全な説明</span><span class="sxs-lookup"><span data-stu-id="31aa3-109">Full description</span></span>
- <span data-ttu-id="31aa3-110">プライバシー ポリシーの URL</span><span class="sxs-lookup"><span data-stu-id="31aa3-110">Privacy policy URL</span></span>
- <span data-ttu-id="31aa3-111">Web サイトの URL</span><span class="sxs-lookup"><span data-stu-id="31aa3-111">Website URL</span></span>
- <span data-ttu-id="31aa3-112">使用条件の URL</span><span class="sxs-lookup"><span data-stu-id="31aa3-112">Terms of use URL</span></span>
- <span data-ttu-id="31aa3-113">[色] アイコン</span><span class="sxs-lookup"><span data-stu-id="31aa3-113">Color icon</span></span>
- <span data-ttu-id="31aa3-114">アウトライン アイコン</span><span class="sxs-lookup"><span data-stu-id="31aa3-114">Outline icon</span></span>
- <span data-ttu-id="31aa3-115">アクセント カラー</span><span class="sxs-lookup"><span data-stu-id="31aa3-115">Accent color</span></span>

<span data-ttu-id="31aa3-116">カスタマイズできる [フィールドの詳細については](https://docs.microsoft.com/microsoftteams/platform/resources/schema/manifest-schema) 、Teams マニフェスト スキーマを参照してください。</span><span class="sxs-lookup"><span data-stu-id="31aa3-116">See the [Teams Manifest schema](https://docs.microsoft.com/microsoftteams/platform/resources/schema/manifest-schema) for details about the fields that you can customize.</span></span>

## <a name="customize-the-apps-details"></a><span data-ttu-id="31aa3-117">アプリの詳細をカスタマイズする</span><span class="sxs-lookup"><span data-stu-id="31aa3-117">Customize the app's details</span></span>

<span data-ttu-id="31aa3-118">アプリのカスタマイズを開始するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="31aa3-118">To start customizing an app, complete the following steps:</span></span>

1. <span data-ttu-id="31aa3-119">Teams 管理センターにサインインします。</span><span class="sxs-lookup"><span data-stu-id="31aa3-119">Sign in to the Teams admin center.</span></span>
2. <span data-ttu-id="31aa3-120">Teams アプリ **を展開し、[** アプリの **管理] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="31aa3-120">Expand **Teams Apps** and select **Manage apps**.</span></span>
3. <span data-ttu-id="31aa3-121">アプリ一 **覧の [** カスタマイズ可能] 列を確認し、カスタマイズ可能なアプリで並べ替えを行います。</span><span class="sxs-lookup"><span data-stu-id="31aa3-121">Check the **Customizable** column of the apps list and sort by apps that are customizable.</span></span>

   ![並べ替えのカスタマイズ列](media/customize-column.png)

   <span data-ttu-id="31aa3-123">カスタマイズ機能にアクセスするには、次の 3 つのエントリ ポイントがあります。</span><span class="sxs-lookup"><span data-stu-id="31aa3-123">There are three entry points to access the customize feature:</span></span>

   - <span data-ttu-id="31aa3-124">カスタマイズするアプリの横を選択し、[カスタマイズ] を選択 **します**。</span><span class="sxs-lookup"><span data-stu-id="31aa3-124">Select next to the app that you want to customize, and then select **Customize**.</span></span>

     ![選択オプションのカスタマイズ 1](media/select-app-to-customize1.png)

   - <span data-ttu-id="31aa3-126">アプリ名を選択し、[カスタマイズ **可能] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="31aa3-126">Select the app name and then **Customizable**.</span></span>

     ![選択オプションのカスタマイズ 2](media/app-details-customizable.png)

   - <span data-ttu-id="31aa3-128">アプリ名を選択し、[アクション] ドロップダウン **から** [カスタマイズ] **を選択** します。</span><span class="sxs-lookup"><span data-stu-id="31aa3-128">Select the app name, and then select **Customize** from the **Actions** dropdown.</span></span>

     ![選択オプションのカスタマイズ 3](media/customize-action-menu.png)

4. <span data-ttu-id="31aa3-130">[詳細] **セクションを** 展開し、次のフィールドをカスタマイズします。</span><span class="sxs-lookup"><span data-stu-id="31aa3-130">Expand the **Details** section and customize the following fields:</span></span>

    - <span data-ttu-id="31aa3-131">短い名前</span><span class="sxs-lookup"><span data-stu-id="31aa3-131">Short name</span></span>
    - <span data-ttu-id="31aa3-132">簡単な説明</span><span class="sxs-lookup"><span data-stu-id="31aa3-132">Short description</span></span>
    - <span data-ttu-id="31aa3-133">完全な説明</span><span class="sxs-lookup"><span data-stu-id="31aa3-133">Full description</span></span>
    - <span data-ttu-id="31aa3-134">Web サイト</span><span class="sxs-lookup"><span data-stu-id="31aa3-134">Website</span></span>
    - <span data-ttu-id="31aa3-135">プライバシー ポリシーの URL</span><span class="sxs-lookup"><span data-stu-id="31aa3-135">Privacy policy URL</span></span>
    - <span data-ttu-id="31aa3-136">使用条件の URL</span><span class="sxs-lookup"><span data-stu-id="31aa3-136">Terms of use URL</span></span>

   ![設定のカスタマイズ](media/customize-settings.png)

> [!Note]
> <span data-ttu-id="31aa3-138">アプリ開発者がカスタマイズ可能として割り当てたフィールドだけが表示されます。</span><span class="sxs-lookup"><span data-stu-id="31aa3-138">Only the fields that the app developer has assigned as customizable will be visible.</span></span>

5. <span data-ttu-id="31aa3-139">[アイコン] **セクションを展開** します。</span><span class="sxs-lookup"><span data-stu-id="31aa3-139">Expand the **Icon** section.</span></span>

   <span data-ttu-id="31aa3-140">a.</span><span class="sxs-lookup"><span data-stu-id="31aa3-140">a.</span></span> <span data-ttu-id="31aa3-141">アイコンをアップロードします。</span><span class="sxs-lookup"><span data-stu-id="31aa3-141">Upload an icon.</span></span> <span data-ttu-id="31aa3-142">1 つのフル カラー アイコン (192x192) ピクセルを PNG 形式で使用します。</span><span class="sxs-lookup"><span data-stu-id="31aa3-142">Use one full-color icon (192x192) pixel in PNG format.</span></span>

   <span data-ttu-id="31aa3-143">b.</span><span class="sxs-lookup"><span data-stu-id="31aa3-143">b.</span></span> <span data-ttu-id="31aa3-144">アイコンの輪郭の色を選択します。</span><span class="sxs-lookup"><span data-stu-id="31aa3-144">Choose an icon outline color.</span></span> <span data-ttu-id="31aa3-145">PNG 形式で 1 つの透明なアウトライン (32x32) ピクセルを使用します。</span><span class="sxs-lookup"><span data-stu-id="31aa3-145">Use one transparent outline (32x32) pixel in PNG format.</span></span>

   <span data-ttu-id="31aa3-146">c.</span><span class="sxs-lookup"><span data-stu-id="31aa3-146">c.</span></span> <span data-ttu-id="31aa3-147">アイコンに一致するアプリのアクセント カラーを選択します。</span><span class="sxs-lookup"><span data-stu-id="31aa3-147">Select an app accent color that matches the icon.</span></span>

    ![アイコン パネルの色オプションをカスタマイズする](media/customize-app-colors.png)

6. <span data-ttu-id="31aa3-149">アプリをカスタマイズしたら、[適用] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="31aa3-149">Once your app has been customized, select **Apply**.</span></span>

7. <span data-ttu-id="31aa3-150">[発行 **] を** 選び、カスタマイズしたアプリを公開します。</span><span class="sxs-lookup"><span data-stu-id="31aa3-150">Select **Publish** to publish the customized app.</span></span>

   <span data-ttu-id="31aa3-151">カスタマイズしたアプリが [アプリの管理] ページ **に表示** されます。</span><span class="sxs-lookup"><span data-stu-id="31aa3-151">The customized app is now listed in your **Manage apps** page.</span></span> <span data-ttu-id="31aa3-152">アプリの機能をカスタマイズしてもアプリのコピーは作成できないので、アプリのバージョンは 1 つのみです。</span><span class="sxs-lookup"><span data-stu-id="31aa3-152">You'll have only one version of the app, since customizing the app features doesn't create a copy of the app.</span></span>

<span data-ttu-id="31aa3-153">Teams のエンド ユーザーは Teams クライアントを開き、カスタマイズされたアプリを表示できます。</span><span class="sxs-lookup"><span data-stu-id="31aa3-153">Now your Teams end users can open their Teams client to see the customized app.</span></span>

   ![Teams クライアントでカスタマイズされたアプリ](media/find-customized-app.png)

### <a name="special-considerations-for-customizing-an-app"></a><span data-ttu-id="31aa3-155">アプリをカスタマイズするための特別な考慮事項</span><span class="sxs-lookup"><span data-stu-id="31aa3-155">Special considerations for customizing an app</span></span>

<span data-ttu-id="31aa3-156">次のメモには、アプリのカスタマイズに関する重要な詳細が含まれています。</span><span class="sxs-lookup"><span data-stu-id="31aa3-156">The following note includes important details about customizing an app.</span></span>

> [!Note]
> - <span data-ttu-id="31aa3-157">アプリ、およびアプリに関連する説明をカスタマイズする場合は、アプリの発行元がドキュメントまたは使用条件で提供するカスタマイズ ガイドラインに従ってください。</span><span class="sxs-lookup"><span data-stu-id="31aa3-157">When you customize apps, and any description related to an app, ensure that you follow any customization guidelines if provided by the app publisher in their documentation or terms of use.</span></span> <span data-ttu-id="31aa3-158">お客様は、お客様が使用するサード パーティ製の画像に関して、他のユーザーの権利を尊重する責任も負います。</span><span class="sxs-lookup"><span data-stu-id="31aa3-158">You're also responsible for respecting the rights of others regarding any third-party images you might use.</span></span>
> - <span data-ttu-id="31aa3-159">管理者が提供するカスタマイズ データは、最も近い地域に保存されます。</span><span class="sxs-lookup"><span data-stu-id="31aa3-159">Admin-provided customization data is stored in the nearest region.</span></span>
> - <span data-ttu-id="31aa3-160">お客様は、使用条件またはプライバシー ポリシーへのリンクが有効か確認する責任があります。</span><span class="sxs-lookup"><span data-stu-id="31aa3-160">You are responsible for ensuring that links to terms of use or privacy policy are valid.</span></span>
> - <span data-ttu-id="31aa3-161">アプリの発行元がフィールドをカスタマイズできなくなった場合、カスタマイズできないフィールドについて管理者に通知するメッセージがアプリの詳細ページに表示されます。</span><span class="sxs-lookup"><span data-stu-id="31aa3-161">In case the app publisher no longer allows a field to be customizable, a message appears on the app details page notifying the admin about the fields that can't be customized any longer.</span></span> <span data-ttu-id="31aa3-162">そのフィールドに加えた変更はすべて、元の値に戻されます。</span><span class="sxs-lookup"><span data-stu-id="31aa3-162">All the changes made to that field will be reverted to the original values.</span></span>
> - <span data-ttu-id="31aa3-163">ユーザーが変更を確認するには、ブランドの変更に最大 24 時間が必要な場合があります。</span><span class="sxs-lookup"><span data-stu-id="31aa3-163">Changes to branding might require up to 24 hours for the users to see the changes.</span></span>

## <a name="review-app-details"></a><span data-ttu-id="31aa3-164">アプリの詳細を確認する</span><span class="sxs-lookup"><span data-stu-id="31aa3-164">Review app details</span></span>

<span data-ttu-id="31aa3-165">情報を確認するために、アプリの詳細を表示したい場合があります。</span><span class="sxs-lookup"><span data-stu-id="31aa3-165">You might want to see the app details to review the information.</span></span>

1. <span data-ttu-id="31aa3-166">Teams 管理センターにサインインします。</span><span class="sxs-lookup"><span data-stu-id="31aa3-166">Sign in to the Teams admin center.</span></span>

2. <span data-ttu-id="31aa3-167">［**Teams アプリ**］ を開き、［**アプリの管理**］ を選択します。</span><span class="sxs-lookup"><span data-stu-id="31aa3-167">Expand **Teams apps** and select **Manage apps**.</span></span>

3. <span data-ttu-id="31aa3-168">アプリ名を選択します。</span><span class="sxs-lookup"><span data-stu-id="31aa3-168">Select the app name.</span></span>

4. <span data-ttu-id="31aa3-169">Publisher から提供された元のアプリ名の短い名前を含 **む、アプリの詳細を表示します**。</span><span class="sxs-lookup"><span data-stu-id="31aa3-169">View the app details, including the original app name **Short name from publisher**.</span></span>

   ![アイコン パネル アプリ名をカスタマイズする](media/app-details-original-name.png)

   <span data-ttu-id="31aa3-171">[ **発行元からの短い** 名前] フィールドは、アプリの短い名前を変更した場合にのみ表示されます。</span><span class="sxs-lookup"><span data-stu-id="31aa3-171">The **Short name from publisher** field is only visible if you've changed the app's short name.</span></span>

## <a name="reset-app-details-to-default"></a><span data-ttu-id="31aa3-172">アプリの詳細を既定にリセットする</span><span class="sxs-lookup"><span data-stu-id="31aa3-172">Reset app details to default</span></span>

<span data-ttu-id="31aa3-173">アプリの詳細は、いつでも元の設定にリセットできます。</span><span class="sxs-lookup"><span data-stu-id="31aa3-173">At any time, you can reset the app details to the original settings.</span></span>

1. <span data-ttu-id="31aa3-174">Teams 管理センターにサインインします。</span><span class="sxs-lookup"><span data-stu-id="31aa3-174">Sign in to the Teams admin center.</span></span>

2. <span data-ttu-id="31aa3-175">Teams アプリ **を展開し、[** アプリの **管理] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="31aa3-175">Expand **Teams Apps** and select **Manage apps**.</span></span>

3. <span data-ttu-id="31aa3-176">アプリ名を選択します。</span><span class="sxs-lookup"><span data-stu-id="31aa3-176">Select the app name.</span></span>

4. <span data-ttu-id="31aa3-177">[アクション **] ドロップダウンから [リセット]** を選び、既定値 **を設定** します。</span><span class="sxs-lookup"><span data-stu-id="31aa3-177">Select **Reset to default** from the **Actions** dropdown.</span></span>

   ![[リセットして既定に戻す] が強調表示されている状態を選択する](media/select-reset.png)

## <a name="frequently-asked-questions"></a><span data-ttu-id="31aa3-179">よく寄せられる質問</span><span class="sxs-lookup"><span data-stu-id="31aa3-179">Frequently asked questions</span></span>

<span data-ttu-id="31aa3-180">**ユーザーがカスタマイズしたアプリを表示するには、どのくらい時間が必要ですか?**</span><span class="sxs-lookup"><span data-stu-id="31aa3-180">**How long will it take for my users to see the customized app?**</span></span>

<span data-ttu-id="31aa3-181">管理者は Teams 管理センターで変更をすぐに確認することができますが、エンド ユーザーが変更を確認するには最大で 24 時間かかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="31aa3-181">Although the admin can immediately see the changes in Teams Admin Center, it might take up to 24 hours for the end users to see the changes.</span></span>  

<span data-ttu-id="31aa3-182">**アプリ プロバイダーは顧客のためにアプリをカスタマイズできますか?**</span><span class="sxs-lookup"><span data-stu-id="31aa3-182">**Can the app provider customize the app for its customers?**</span></span>

 <span data-ttu-id="31aa3-183">いいえ、テナントの管理者は、Teams 管理センターを使用して、テナント用にアプリをカスタマイズする必要があります。</span><span class="sxs-lookup"><span data-stu-id="31aa3-183">No, the admin of a tenant needs to customize the app for their tenant using the Teams Admin Center.</span></span>

<span data-ttu-id="31aa3-184">**テナント内の現在のカスタム アプリを置き換えるカスタマイズされたアプリは自動的に展開されますか?**</span><span class="sxs-lookup"><span data-stu-id="31aa3-184">**Will the customized app automatically get deployed to replace my current custom app in a tenant?**</span></span>

<span data-ttu-id="31aa3-185">いいえ、テナント管理者はカスタム アプリを手動で削除し、カスタマイズされたバージョンのアプリを公開する必要があります。</span><span class="sxs-lookup"><span data-stu-id="31aa3-185">No, the tenant admins will have to manually remove any custom app and publish the customized version of the app.</span></span> <span data-ttu-id="31aa3-186">アプリをカスタマイズし、カスタム アプリとして公開した場合、アプリのカスタマイズ機能を使用してカスタマイズされた新しいアプリは、現在のカスタム アプリに置き換えされません。</span><span class="sxs-lookup"><span data-stu-id="31aa3-186">If you have customized an app and published it as a custom app, the new app customized using the app customization feature won't replace the current custom app.</span></span>  

<span data-ttu-id="31aa3-187">**アプリの使用状況レポートには、カスタマイズした短い名前などのカスタマイズした値も表示されますか?**</span><span class="sxs-lookup"><span data-stu-id="31aa3-187">**Will the app usage report also show the customized values such as customized short name?**</span></span>

 <span data-ttu-id="31aa3-188">いいえ、アプリの使用状況レポートには、発行元から送信されたアプリの元の名前が引き続き表示されます。</span><span class="sxs-lookup"><span data-stu-id="31aa3-188">No, the app usage report will still show the original name of the app sent from the publisher.</span></span>

<span data-ttu-id="31aa3-189">**アプリのカスタマイズ機能を使用してカスタマイズできるアプリ**</span><span class="sxs-lookup"><span data-stu-id="31aa3-189">**Which apps can I customize using the app customization feature?**</span></span>

<span data-ttu-id="31aa3-190">カスタマイズできるのは、アプリ発行元によってカスタマイズが許可されているアプリのみです。</span><span class="sxs-lookup"><span data-stu-id="31aa3-190">You can only customize apps that have been allowed to be customizable by the app publisher.</span></span> <span data-ttu-id="31aa3-191">アプリの発行元は、お客様がアプリをカスタマイズすることを許可するためにオプトインする必要があります。</span><span class="sxs-lookup"><span data-stu-id="31aa3-191">The app publisher will need to opt in to allow its customers to customize the app.</span></span>

<span data-ttu-id="31aa3-192">**カスタマイズしたプロパティは、グラフのアクセス許可の同意画面に表示されますか?**</span><span class="sxs-lookup"><span data-stu-id="31aa3-192">**Will the customized properties show up on the graph permission consent screen?**</span></span>

<span data-ttu-id="31aa3-193">いいえ、アクセス許可の同意画面には、発行元から送信された元の値が引き続き表示されます。</span><span class="sxs-lookup"><span data-stu-id="31aa3-193">No, the permission consent screen will still show the original value sent by the publisher.</span></span>

## <a name="related-article"></a><span data-ttu-id="31aa3-194">関連記事</span><span class="sxs-lookup"><span data-stu-id="31aa3-194">Related article</span></span>

- [<span data-ttu-id="31aa3-195">アプリを管理する</span><span class="sxs-lookup"><span data-stu-id="31aa3-195">Manage apps</span></span>](manage-apps.md)
- [<span data-ttu-id="31aa3-196">アプリ ストアをカスタマイズする</span><span class="sxs-lookup"><span data-stu-id="31aa3-196">Customize your app store</span></span>](customize-your-app-store.md)
