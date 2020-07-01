---
title: Microsoft Teams のアプリのセットアップ ポリシーを管理する
author: lanachin
ms.author: v-lanac
manager: serdars
ms.reviewer: rarang
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
description: 組織内のユーザーに対して Microsoft Teams でアプリセットアップポリシーを使用および管理する方法について説明します。
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.appsetuppolicies.overview
ms.openlocfilehash: 9ddbcd1a5110cff52ce518cf052279204fc8e2c9
ms.sourcegitcommit: 60b859dcb8ac727a38bf28cdb63ff762e7338af8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/30/2020
ms.locfileid: "44938216"
---
# <a name="manage-app-setup-policies-in-microsoft-teams"></a><span data-ttu-id="cec94-103">Microsoft Teams のアプリのセットアップ ポリシーを管理する</span><span class="sxs-lookup"><span data-stu-id="cec94-103">Manage app setup policies in Microsoft Teams</span></span>

> [!NOTE]
> <span data-ttu-id="cec94-104">組織全体のアプリ設定を有効にしている場合、**カスタムアプリとの対話を許可**すると、Microsoft Teams 管理センターにまだアプリセットアップポリシーが表示されないことがあります。</span><span class="sxs-lookup"><span data-stu-id="cec94-104">If you enabled the org-wide app setting, **Allow interaction with custom apps**, you may not see app setup policies yet in the Microsoft Teams admin center.</span></span> <span data-ttu-id="cec94-105">この機能は現在展開中であり、間もなく組織内で利用可能になります。</span><span class="sxs-lookup"><span data-stu-id="cec94-105">It's currently being rolled out and will be available soon in your organization.</span></span>

<span data-ttu-id="cec94-106">管理者は、アプリ セットアップポリシーを使用して、次の操作を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="cec94-106">As an admin, you can use app setup policies to do the following:</span></span>

- <span data-ttu-id="cec94-107">Teams をカスタマイズして、ユーザーにとって最も重要なアプリを強調表示します。</span><span class="sxs-lookup"><span data-stu-id="cec94-107">Customize Teams to highlight the apps that are most important for your users.</span></span> <span data-ttu-id="cec94-108">ピン留めするアプリを選択し、表示される順序を設定します。</span><span class="sxs-lookup"><span data-stu-id="cec94-108">You choose the apps to pin and set the order that they appear.</span></span> <span data-ttu-id="cec94-109">アプリをピン留めすると、サード パーティ製のアプリや組織内の開発者が作成したアプリなど、組織内のユーザーが必要とするアプリを提示できます。</span><span class="sxs-lookup"><span data-stu-id="cec94-109">Pinning apps lets you showcase apps that users in your organization need, including those built by third parties or by developers in your organization.</span></span>
- <span data-ttu-id="cec94-110">ユーザーがアプリを Teams にピン留めできるかどうかを制御します。</span><span class="sxs-lookup"><span data-stu-id="cec94-110">Control whether users can pin apps to Teams.</span></span>
- <span data-ttu-id="cec94-111">[ユーザーの代わりにアプリをインストールする **(プレビュー中)**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="cec94-111">Install apps on behalf of users **(in preview)**.</span></span> <span data-ttu-id="cec94-112">ユーザーが Teams を起動したときに既定でインストールされるアプリを選択します。</span><span class="sxs-lookup"><span data-stu-id="cec94-112">You choose which apps are installed by default for users when they start Teams.</span></span> <span data-ttu-id="cec94-113">ユーザーに割り当てられている[アプリのアクセス許可のポリシー](teams-app-permission-policies.md)で許可されている場合は、ユーザーがアプリ自体をインストールできることを覚えておいてください。</span><span class="sxs-lookup"><span data-stu-id="cec94-113">Keep in mind that users can still install apps themselves if the [app permission policy](teams-app-permission-policies.md) that's assigned to them allows it.</span></span>

<span data-ttu-id="cec94-114">アプリは、アプリ バーにピン留めされます。</span><span class="sxs-lookup"><span data-stu-id="cec94-114">Apps are pinned to the app bar.</span></span> <span data-ttu-id="cec94-115">このバーは、Teams デスクトップ クライアントの横側および Teams モバイル クライアント (iOS および Android) の下側に表示されます。</span><span class="sxs-lookup"><span data-stu-id="cec94-115">This is the bar on the side of the Teams desktop client and at the bottom of the Teams mobile clients (iOS and Android).</span></span>

|<span data-ttu-id="cec94-116">Teams のデスクトップクライアント</span><span class="sxs-lookup"><span data-stu-id="cec94-116">Teams desktop client</span></span>  |<span data-ttu-id="cec94-117">Teams モバイルクライアント</span><span class="sxs-lookup"><span data-stu-id="cec94-117">Teams mobile client</span></span> |
|---------|---------|
|![Teams のデスクトップクライアントを示すスクリーンショット](media/app-setup-policies-desktop-app-bar.png)<br>  |   ![Teams モバイルクライアントを示すスクリーンショット](media/app-setup-policies-mobile-app-bar.png)      |

<span data-ttu-id="cec94-120">アプリバーでプレインストールされているアプリを確認するには、ユーザーが [...] をクリックします **。** チームのデスクトップと web クライアントでその他のアプリを追加し、モバイルクライアントで上にスワイプします。</span><span class="sxs-lookup"><span data-stu-id="cec94-120">To see their pre-installed apps, in the app bar, users click **... More apps** in the Teams desktop and web clients and swipe up in the mobile clients.</span></span>

<span data-ttu-id="cec94-121">アプリセットアップポリシーは、Microsoft Teams 管理センターで管理します。</span><span class="sxs-lookup"><span data-stu-id="cec94-121">You manage app setup policies in the Microsoft Teams admin center.</span></span> <span data-ttu-id="cec94-122">グローバル (組織全体の既定) ポリシーを使用するか、カスタムポリシーを作成して割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="cec94-122">You can use the global (Org-wide default) policy or create and assign custom policies.</span></span>  <span data-ttu-id="cec94-123">カスタム ポリシーを作成して割り当てていない場合、組織内のユーザーにはグローバル ポリシーが自動的に適用されます。</span><span class="sxs-lookup"><span data-stu-id="cec94-123">Users in your organization will automatically get the global policy unless you create and assign a custom policy.</span></span> <span data-ttu-id="cec94-124">これらのポリシーを管理するには、グローバル管理者または Teams サービス管理者である必要があります。</span><span class="sxs-lookup"><span data-stu-id="cec94-124">You must be a global admin or Teams service admin to manage these policies.</span></span>

<span data-ttu-id="cec94-125">グローバルポリシーの設定を編集して、目的のアプリを含めることができます。</span><span class="sxs-lookup"><span data-stu-id="cec94-125">You can edit the settings in the global policy to include the apps that you want.</span></span> <span data-ttu-id="cec94-126">組織内のさまざまなユーザーグループのチームをカスタマイズする場合は、1つ以上のカスタムポリシーを作成して割り当てます。</span><span class="sxs-lookup"><span data-stu-id="cec94-126">If you want to customize Teams for different groups of users in your organization, create and assign one or more custom policies.</span></span>

![[アプリセットアップポリシー] ページを示すスクリーンショット](media/app-setup-policies.png)

> [!NOTE]
> <span data-ttu-id="cec94-128">教育機関向けの Teams をお持ちの場合は、現時点ではグローバルポリシーで割り当てアプリが既定で固定されていることを知っておくことが重要です。現在のところ、グローバルポリシーには表示されません。</span><span class="sxs-lookup"><span data-stu-id="cec94-128">If you have Teams for Education, it's important to know that the Assignments app is pinned by default in the global policy even though currently, you don't see it listed in the global policy.</span></span> <span data-ttu-id="cec94-129">チームクライアントの固定されたアプリの一覧で4番目のアプリになります。</span><span class="sxs-lookup"><span data-stu-id="cec94-129">It will be the fourth app in the list of pinned apps on Teams clients.</span></span>

## <a name="create-a-custom-app-setup-policy"></a><span data-ttu-id="cec94-130">カスタムアプリセットアップポリシーを作成する</span><span class="sxs-lookup"><span data-stu-id="cec94-130">Create a custom app setup policy</span></span>

<span data-ttu-id="cec94-131">Microsoft Teams 管理センターを使用して、カスタムポリシーを作成することができます。</span><span class="sxs-lookup"><span data-stu-id="cec94-131">You can use the Microsoft Teams admin center to create a custom policy.</span></span>

1. <span data-ttu-id="cec94-132">Microsoft Teams 管理センターの左のナビゲーションで、[ **Teams アプリ**  >  **セットアップポリシー**] に移動します。</span><span class="sxs-lookup"><span data-stu-id="cec94-132">In the left navigation of the Microsoft Teams admin center, go to **Teams apps** > **Setup policies**.</span></span>
2. <span data-ttu-id="cec94-133">**[追加]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="cec94-133">Click **Add**.</span></span>
    <span data-ttu-id="cec94-134">![[アプリセットアップポリシーの追加] ページを示すスクリーンショット](media/app-setup-policies-add.png)</span><span class="sxs-lookup"><span data-stu-id="cec94-134">![Screenshot showing the Add app setup policies page](media/app-setup-policies-add.png)</span></span>
3. <span data-ttu-id="cec94-135">ポリシーの名前と説明を入力します。</span><span class="sxs-lookup"><span data-stu-id="cec94-135">Enter a name and description for the policy.</span></span>
4. <span data-ttu-id="cec94-136">ユーザーがカスタムアプリをチームにアップロードできるかどうかに応じて、**カスタムアプリのアップロード**を有効または無効にします。</span><span class="sxs-lookup"><span data-stu-id="cec94-136">Turn on or turn off **Upload custom apps**, depending on whether you want to let users upload custom apps to Teams.</span></span> <span data-ttu-id="cec94-137">[組織全体のアプリ設定](manage-apps.md#manage-org-wide-app-settings)で**サードパーティ製のアプリ**が無効になっている場合、この設定を変更することはできません。</span><span class="sxs-lookup"><span data-stu-id="cec94-137">You won't be able to change this setting if **Allow third-party apps** is turned off in [org-wide app settings](manage-apps.md#manage-org-wide-app-settings).</span></span>
5. <span data-ttu-id="cec94-138">ユーザーがアプリをカスタマイズ**できる**ようにするかどうかに応じて、ユーザーの固定を有効または無効にします。</span><span class="sxs-lookup"><span data-stu-id="cec94-138">Turn on or turn off **Allow user pinning**, depending on whether you want to let users personalize their app bar by pinning apps to it.</span></span>
6. <span data-ttu-id="cec94-139">ユーザー用のアプリ **(プレビュー版)** をインストールするには、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="cec94-139">To install apps for users **(in preview)**, do the following:</span></span>

    1. <span data-ttu-id="cec94-140">[**インストールされているアプリ**] で、[**アプリの追加**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="cec94-140">Under **Installed apps**, click **Add apps**.</span></span>
    2. <span data-ttu-id="cec94-141">[**インストールされているアプリの追加**] ウィンドウで、ユーザーが Teams を起動したときに自動的にインストールするアプリを検索します。</span><span class="sxs-lookup"><span data-stu-id="cec94-141">In the **Add installed apps** pane, search for the apps you want to automatically install for users when they start Teams.</span></span> <span data-ttu-id="cec94-142">アプリのアクセス許可ポリシーによってアプリをフィルター処理することもできます。</span><span class="sxs-lookup"><span data-stu-id="cec94-142">You can also filter apps by app permission policy.</span></span> <span data-ttu-id="cec94-143">アプリの一覧を選択したら、[**追加**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="cec94-143">When you've chosen your list of apps, click **Add**.</span></span>

        ![[インストールされているアプリの追加] ウィンドウを示すスクリーンショット](media/app-setup-policies-add-installed-apps.png)

7. <span data-ttu-id="cec94-145">アプリを固定するには、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="cec94-145">To pin apps, do the following:</span></span>

    1. <span data-ttu-id="cec94-146">[**固定**されたアプリ] で、[**アプリの追加**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="cec94-146">Under **Pinned apps**, click **Add apps**.</span></span>
    2. <span data-ttu-id="cec94-147">[固定された**アプリの追加**] ウィンドウで、追加するアプリを検索し、[**追加**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="cec94-147">In the **Add pinned apps** pane, search for the apps you want to add, and then click **Add**.</span></span> <span data-ttu-id="cec94-148">アプリのアクセス許可ポリシーによってアプリをフィルター処理することもできます。</span><span class="sxs-lookup"><span data-stu-id="cec94-148">You can also filter apps by app permission policy.</span></span> <span data-ttu-id="cec94-149">ピン留めするアプリのリストを選んだら、[**追加**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="cec94-149">When you've chosen your list of apps to pin, click **Add**.</span></span>

         ![[固定アプリの追加] ウィンドウを示すスクリーンショット](media/app-setup-policies-add-apps.png)

    3. <span data-ttu-id="cec94-151">Teams で表示する順序でアプリを配置し、[**保存**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="cec94-151">Arrange the apps in the order that you want them to appear in Teams, and then click **Save**.</span></span>

        ![ピン留めされたアプリのセクションを示すスクリーンショット](media/app-setup-policies-new-policy-setup.png)

## <a name="edit-an-app-setup-policy"></a><span data-ttu-id="cec94-153">アプリのセットアップポリシーを編集する</span><span class="sxs-lookup"><span data-stu-id="cec94-153">Edit an app setup policy</span></span>

<span data-ttu-id="cec94-154">Microsoft Teams 管理センターを使って、作成するグローバル (組織全体の既定) ポリシーやカスタムポリシーなどのポリシーを編集できます。</span><span class="sxs-lookup"><span data-stu-id="cec94-154">You can use the Microsoft Teams admin center to edit a policy, including the global (Org-wide default) policy and custom policies that you create.</span></span>

1. <span data-ttu-id="cec94-155">Microsoft Teams 管理センターの左のナビゲーションで、[ **Teams アプリ**  >  **セットアップポリシー**] に移動します。</span><span class="sxs-lookup"><span data-stu-id="cec94-155">In the left navigation of the Microsoft Teams admin center, go to **Teams apps** > **Setup policies**.</span></span>
2. <span data-ttu-id="cec94-156">ポリシー名の左側をクリックしてポリシーを選び、**[編集]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="cec94-156">Select the policy by clicking to the left of the policy name, and then click **Edit**.</span></span>
3. <span data-ttu-id="cec94-157">ここで、必要な変更を行います。</span><span class="sxs-lookup"><span data-stu-id="cec94-157">From here, make the changes that you want.</span></span>
4. <span data-ttu-id="cec94-158">**[保存]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="cec94-158">Click **Save**.</span></span>

## <a name="assign-a-custom-app-setup-policy-to-users"></a><span data-ttu-id="cec94-159">ユーザーにカスタムアプリセットアップポリシーを割り当てる</span><span class="sxs-lookup"><span data-stu-id="cec94-159">Assign a custom app setup policy to users</span></span>

[!INCLUDE [assign-policy](includes/assign-policy.md)]

## <a name="faq"></a><span data-ttu-id="cec94-160">FAQ</span><span class="sxs-lookup"><span data-stu-id="cec94-160">FAQ</span></span>

### <a name="working-with-app-setup-policies"></a><span data-ttu-id="cec94-161">アプリセットアップポリシーを使用する</span><span class="sxs-lookup"><span data-stu-id="cec94-161">Working with app setup policies</span></span>

#### <a name="what-built-in-app-setup-policies-are-included-in-the-microsoft-teams-admin-center"></a><span data-ttu-id="cec94-162">Microsoft Teams 管理センターには、どのような組み込みのアプリセットアップポリシーが含まれていますか?</span><span class="sxs-lookup"><span data-stu-id="cec94-162">What built-in app setup policies are included in the Microsoft Teams admin center?</span></span>

- <span data-ttu-id="cec94-163">**グローバル (組織全体の既定)**: この既定のポリシーは、別のポリシーを割り当てない限り、組織内のすべてのユーザーに適用されます。</span><span class="sxs-lookup"><span data-stu-id="cec94-163">**Global (Org-wide default)**: This default policy applies to all users in your organization unless you assign another policy.</span></span> <span data-ttu-id="cec94-164">グローバルポリシーを編集して、ユーザーにとって最も重要なアプリをピン留めします。</span><span class="sxs-lookup"><span data-stu-id="cec94-164">Edit the global policy to pin apps that are most important for your users.</span></span>
- <span data-ttu-id="cec94-165">**Firstlineworker**: このポリシーは、firstline worker に対して使用されます。</span><span class="sxs-lookup"><span data-stu-id="cec94-165">**FirstLineWorker**: This policy is for Firstline Workers.</span></span> <span data-ttu-id="cec94-166">組織内の Firstline Worker に割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="cec94-166">You can assign it to Firstline Workers in your organization.</span></span> <span data-ttu-id="cec94-167">作成するカスタムポリシーなど、設定をアクティブにするユーザーにポリシーを割り当てる必要があることを知っておくことが重要です。</span><span class="sxs-lookup"><span data-stu-id="cec94-167">It's important to know that like custom policies that you create, you have to assign the policy to users for the settings to be active.</span></span> <span data-ttu-id="cec94-168">詳細については、この記事の「[ユーザーにカスタムアプリセットアップポリシーを割り当てる](#assign-a-custom-app-setup-policy-to-users)」セクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="cec94-168">For more information, go to the [Assign a custom app setup policy to users](#assign-a-custom-app-setup-policy-to-users) section of this article.</span></span>

#### <a name="why-cant-i-find-an-app-in-the-add-pinned-apps-pane"></a><span data-ttu-id="cec94-169">[ピン留めしたアプリの追加] ウィンドウでアプリが見つからないのはなぜですか?</span><span class="sxs-lookup"><span data-stu-id="cec94-169">Why can't I find an app in the Add pinned apps pane?</span></span>

<span data-ttu-id="cec94-170">アプリセットアップポリシーを使用して、すべてのアプリを Teams にピン留めすることはできません。</span><span class="sxs-lookup"><span data-stu-id="cec94-170">Not all apps can be pinned to Teams through an app setup policy.</span></span> <span data-ttu-id="cec94-171">一部のアプリでは、この機能がサポートされていない可能性があります。</span><span class="sxs-lookup"><span data-stu-id="cec94-171">Some apps may not support this functionality.</span></span> <span data-ttu-id="cec94-172">ピン留めできるアプリを見つけるには、[**ピン留め**されたアプリの追加] ウィンドウでアプリを検索します。</span><span class="sxs-lookup"><span data-stu-id="cec94-172">To find apps that can be pinned, search for the app in the **Add pinned apps** pane.</span></span> <span data-ttu-id="cec94-173">個人用のスコープ (静的タブ) とボットを含むタブは、Teams のデスクトップクライアントにピン留めすることができます。これらのアプリは、[固定された**アプリの追加**] ウィンドウで利用できます。</span><span class="sxs-lookup"><span data-stu-id="cec94-173">Tabs that have a personal scope (static tabs) and bots can be pinned to the Teams desktop client and these apps are available in the **Add pinned apps** pane.</span></span>

<span data-ttu-id="cec94-174">Teams app store にはすべての Teams アプリが一覧表示されます。 [**ピン留め**されたアプリの追加] ウィンドウには、ポリシーを通じてチームにピン留めできるアプリのみが含まれていることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="cec94-174">Keep in mind that the Teams app store lists all Teams apps whereas the **Add pinned apps** pane includes only apps that can be pinned to Teams through a policy.</span></span> 

#### <a name="im-a-teams-for-education-admin-what-do-i-need-to-know-about-app-setup-policies-in-teams-for-education"></a><span data-ttu-id="cec94-175">私は教育管理者向けのチームです。教育機関向け Teams のアプリセットアップポリシーについて知っておくべきこと</span><span class="sxs-lookup"><span data-stu-id="cec94-175">I'm a Teams for Education admin. What do I need to know about app setup policies in Teams for Education?</span></span>

<span data-ttu-id="cec94-176">通話アプリは、教育担当の Teams では利用できません。</span><span class="sxs-lookup"><span data-stu-id="cec94-176">The Calling app isn't available in Teams for Education.</span></span> <span data-ttu-id="cec94-177">新しいカスタムアプリのセットアップポリシーを作成すると、アプリの一覧に呼び出し元のアプリが表示されます。</span><span class="sxs-lookup"><span data-stu-id="cec94-177">When you create a new custom app setup policy, the Calling app is displayed in the list of apps.</span></span> <span data-ttu-id="cec94-178">ただし、アプリは Teams クライアントにはピン留めされておらず、教育機関のチームではチーム内の通話アプリを見ることはできません。</span><span class="sxs-lookup"><span data-stu-id="cec94-178">However, the app isn't pinned to Teams clients and Teams for Education users won't see the Calls app in Teams.</span></span>

#### <a name="how-many-pinned-apps-can-be-added-to-a-policy"></a><span data-ttu-id="cec94-179">固定されたアプリの数をポリシーに追加できますか?</span><span class="sxs-lookup"><span data-stu-id="cec94-179">How many pinned apps can be added to a policy?</span></span>

<span data-ttu-id="cec94-180">少なくとも2つのアプリが Teams モバイルクライアント (iOS と Android) にピン留めされている必要があります。</span><span class="sxs-lookup"><span data-stu-id="cec94-180">A minimum of two apps must be pinned to the Teams mobile clients (iOS and Android).</span></span> <span data-ttu-id="cec94-181">ポリシーのアプリが2つ未満の場合、モバイルクライアントはポリシーの設定を反映せず、代わりに既存の構成を使い続けます。</span><span class="sxs-lookup"><span data-stu-id="cec94-181">If a policy has less than two apps, the mobile clients won't reflect the policy settings and instead will continue to use the existing configuration.</span></span>

<span data-ttu-id="cec94-182">ポリシーに追加できる固定されたアプリの数に制限はありません。</span><span class="sxs-lookup"><span data-stu-id="cec94-182">There's no limit on the number of pinned apps you can add to a policy.</span></span>

#### <a name="how-long-does-it-take-for-policy-changes-to-take-effect"></a><span data-ttu-id="cec94-183">ポリシーの変更が有効になるまでにはどのくらいの時間がかかりますか?</span><span class="sxs-lookup"><span data-stu-id="cec94-183">How long does it take for policy changes to take effect?</span></span>

<span data-ttu-id="cec94-184">ポリシーを編集または割り当てると、変更が有効になるまでに数時間かかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="cec94-184">After you edit or assign a policy, it can take a few hours for changes to take effect.</span></span>

### <a name="user-experience"></a><span data-ttu-id="cec94-185">ユーザー エクスペリエンス</span><span class="sxs-lookup"><span data-stu-id="cec94-185">User experience</span></span>

#### <a name="how-can-users-see-all-their-pinned-apps-in-teams"></a><span data-ttu-id="cec94-186">ユーザーが Teams で固定されたすべてのアプリを表示するにはどうすればよいですか?</span><span class="sxs-lookup"><span data-stu-id="cec94-186">How can users see all their pinned apps in Teams?</span></span>

<span data-ttu-id="cec94-187">ユーザーに対して固定されているすべてのアプリを表示するには、インストールされているアプリの数とチームクライアントウィンドウのサイズに応じて、次の操作が必要になることがあります。</span><span class="sxs-lookup"><span data-stu-id="cec94-187">To view all apps that are pinned for a user, users may have to do the following depending on the number of installed apps and the size of their Teams client window.</span></span>

|<span data-ttu-id="cec94-188">Teams のデスクトップクライアント</span><span class="sxs-lookup"><span data-stu-id="cec94-188">Teams desktop client</span></span> |<span data-ttu-id="cec94-189">Teams モバイルクライアント</span><span class="sxs-lookup"><span data-stu-id="cec94-189">Teams mobile client</span></span> |
|---------|---------|
|<span data-ttu-id="cec94-190">Teams のサイドにあるアプリバーで、[...] をクリックします。 **その他のアプリ**。</span><span class="sxs-lookup"><span data-stu-id="cec94-190">In the app bar on the side of Teams, click **... More apps**.</span></span>| <span data-ttu-id="cec94-191">チームの下部付近にあるアプリバーで、上にスワイプします。</span><span class="sxs-lookup"><span data-stu-id="cec94-191">In the app bar near the bottom of Teams, swipe up.</span></span>|
|![Teams デスクトップクライアントでその他のアプリを示すスクリーンショット](media/app-setup-policies-desktop-more-apps.png)<br>   |![Teams モバイルクライアントでその他のアプリを示すスクリーンショット](media/app-setup-policies-mobile-more-apps.png)  

#### <a name="what-do-i-need-to-know-about-the-teams-mobile-experience"></a><span data-ttu-id="cec94-194">Teams のモバイルエクスペリエンスについて知っておくべきこと</span><span class="sxs-lookup"><span data-stu-id="cec94-194">What do I need to know about the Teams mobile experience?</span></span>

<span data-ttu-id="cec94-195">現在、Teams モバイルクライアント (iOS と Android) では、静的なタブを持つ個人用アプリはサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="cec94-195">The Teams mobile clients (iOS and Android) currently don't support personal apps with static tabs.</span></span> <span data-ttu-id="cec94-196">ポリシーに設定されているアプリによっては、Teams のデスクトップクライアントに固定されたアプリが Teams のモバイルクライアントに表示されない場合があります。</span><span class="sxs-lookup"><span data-stu-id="cec94-196">Depending on the apps set in the policy, apps pinned to the Teams desktop client might not appear in the Teams mobile clients.</span></span> <span data-ttu-id="cec94-197">携帯電話クライアントのチャットには、個人用のボットが引き続き表示されます。</span><span class="sxs-lookup"><span data-stu-id="cec94-197">Personal bots will still appear in Chat on mobile clients.</span></span>

<span data-ttu-id="cec94-198">Teams のモバイルクライアントでは、ユーザーにはアクティビティ、チャット、Teams などの主要な Teams アプリが表示され、シフトなどの一部のサードパーティ製アプリを Microsoft からピン留めすることができます。</span><span class="sxs-lookup"><span data-stu-id="cec94-198">With the Teams mobile clients, users will see core Teams apps such as Activity, Chat, and Teams, and you can pin some first-party apps from Microsoft, such as Shifts.</span></span>

#### <a name="can-users-change-the-order-of-apps-pinned-through-a-policy"></a><span data-ttu-id="cec94-199">ユーザーはポリシーによって固定されたアプリの順序を変更できますか。</span><span class="sxs-lookup"><span data-stu-id="cec94-199">Can users change the order of apps pinned through a policy?</span></span>

<span data-ttu-id="cec94-200">ユーザーは、[**ユーザーによる固定**] オプションがオンになっている場合は、チームのデスクトップとモバイルクライアントで固定されたアプリの順序を変更できます。</span><span class="sxs-lookup"><span data-stu-id="cec94-200">Users can change the order of their pinned apps on Teams desktop and mobile clients if the **Allow user pinning** option is turned on.</span></span> <span data-ttu-id="cec94-201">ユーザーは、Teams web クライアントで固定されたアプリの順序を変更することはできません。</span><span class="sxs-lookup"><span data-stu-id="cec94-201">Users can't change the order of their pinned apps on Teams web clients.</span></span>

#### <a name="does-user-pinning-take-precedence"></a><span data-ttu-id="cec94-202">ユーザーのピン留めは優先されますか?</span><span class="sxs-lookup"><span data-stu-id="cec94-202">Does user pinning take precedence?</span></span>

<span data-ttu-id="cec94-203">ユーザーに割り当てられているアプリセットアップポリシーが、ユーザーアプリの固定をブロックするように変更されている場合、チームはアプリバーに固定されているすべてのアプリを削除します。</span><span class="sxs-lookup"><span data-stu-id="cec94-203">If the app setup policy assigned to the user is changed to block user app pinning, Teams removes any apps pinned to the app bar.</span></span> <span data-ttu-id="cec94-204">ユーザーアプリの固定を許可するようにポリシーを変更した場合、ユーザーは以前に固定されたアプリを再ピンする必要があります。</span><span class="sxs-lookup"><span data-stu-id="cec94-204">If the policy is then changed to allow user app pinning, users must re-pin their previously pinned apps.</span></span>

### <a name="custom-teams-apps"></a><span data-ttu-id="cec94-205">カスタム Teams アプリ</span><span class="sxs-lookup"><span data-stu-id="cec94-205">Custom Teams apps</span></span>

#### <a name="my-organization-built-a-custom-teams-app-and-published-it-either-to-appsource-or-the-tenant-app-catalog-but-the-app-icon-isnt-displayed-as-expected-when-the-app-is-pinned-to-the-app-bar-in-teams-how-do-i-fix-it"></a><span data-ttu-id="cec94-206">組織では、カスタム Teams アプリを構築し、AppSource またはテナントのアプリカタログに公開していますが、アプリが Teams のアプリバーにピン留めされている場合、アプリのアイコンは期待どおりに表示されません。</span><span class="sxs-lookup"><span data-stu-id="cec94-206">My organization built a custom Teams app and published it, either to AppSource or the tenant app catalog, but the app icon isn't displayed as expected when the app is pinned to the app bar in Teams.</span></span> <span data-ttu-id="cec94-207">問題を解決するにはどうすればよいですか?</span><span class="sxs-lookup"><span data-stu-id="cec94-207">How do I fix it?</span></span>

<span data-ttu-id="cec94-208">アプリを申請する前に、ロゴガイドラインに従っていることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="cec94-208">Make sure that you follow the logo guidelines before you submit the app.</span></span> <span data-ttu-id="cec94-209">詳細については、「[販売業者ダッシュボードの申請のチェックリスト](/microsoftteams/platform/concepts/deploy-and-publish/appsource/prepare/overview)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="cec94-209">To learn more, see [Checklist for Seller Dashboard submission](/microsoftteams/platform/concepts/deploy-and-publish/appsource/prepare/overview).</span></span> 

## <a name="related-topics"></a><span data-ttu-id="cec94-210">関連項目</span><span class="sxs-lookup"><span data-stu-id="cec94-210">Related topics</span></span>

[<span data-ttu-id="cec94-211">Teams でのアプリの管理設定</span><span class="sxs-lookup"><span data-stu-id="cec94-211">Admin settings for apps in Teams</span></span>](admin-settings.md)

[<span data-ttu-id="cec94-212">チームのユーザーにポリシーを割り当てる</span><span class="sxs-lookup"><span data-stu-id="cec94-212">Assign policies to your users in Teams</span></span>](assign-policies.md)
