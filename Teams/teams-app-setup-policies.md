---
title: Microsoft Teams のアプリのセットアップ ポリシーを管理する
author: cichur
ms.author: v-cichur
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
description: 組織内のユーザーに対してアプリ設定ポリシーを使用して管理する方法Microsoft Teamsアプリセットアップ ポリシーを管理する方法について説明します。
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.appsetuppolicies.overview
ms.openlocfilehash: ebfcff8ce7215e34e3c17e9c09f3a56d249d5b40
ms.sourcegitcommit: 1ee9b1857f472a5b95352f7471c0cf21be6ea0c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/27/2021
ms.locfileid: "52059201"
---
# <a name="manage-app-setup-policies-in-microsoft-teams"></a><span data-ttu-id="9944d-103">Microsoft Teams のアプリのセットアップ ポリシーを管理する</span><span class="sxs-lookup"><span data-stu-id="9944d-103">Manage app setup policies in Microsoft Teams</span></span>

<span data-ttu-id="9944d-104">管理者は、アプリセットアップ ポリシーを使用して、次のタスクを実行できます。</span><span class="sxs-lookup"><span data-stu-id="9944d-104">As an admin, you can use app setup policies to do the following tasks:</span></span>

- <span data-ttu-id="9944d-105">Teams をカスタマイズして、ユーザーにとって最も重要なアプリを強調表示します。</span><span class="sxs-lookup"><span data-stu-id="9944d-105">Customize Teams to highlight the apps that are most important for your users.</span></span> <span data-ttu-id="9944d-106">表示される順序をピン留めして設定するアプリを選択します。</span><span class="sxs-lookup"><span data-stu-id="9944d-106">You choose the apps to pin and set the order that they appear.</span></span> <span data-ttu-id="9944d-107">アプリをピン留めすると、サード パーティや組織内の開発者によって構築されたアプリなど、組織内のユーザーが必要とするアプリを紹介できます。</span><span class="sxs-lookup"><span data-stu-id="9944d-107">Pinning apps lets you showcase apps that users in your organization need, including apps built by third parties or by developers in your organization.</span></span>
- <span data-ttu-id="9944d-108">ユーザーがアプリを Teams にピン留めできるかどうかを制御します。</span><span class="sxs-lookup"><span data-stu-id="9944d-108">Control whether users can pin apps to Teams.</span></span>
- <span data-ttu-id="9944d-109">ユーザーに代わってアプリをインストールします。</span><span class="sxs-lookup"><span data-stu-id="9944d-109">Install apps on behalf of users.</span></span> <span data-ttu-id="9944d-110">ユーザーがアプリを起動するときに、既定でインストールするアプリをTeams。</span><span class="sxs-lookup"><span data-stu-id="9944d-110">You choose which apps are installed by default for users when they start Teams.</span></span> <span data-ttu-id="9944d-111">ユーザーに割り当てられているアプリのアクセス許可ポリシーで許可[](teams-app-permission-policies.md)されている場合でも、ユーザーはアプリ自体をインストールできます。</span><span class="sxs-lookup"><span data-stu-id="9944d-111">Keep in mind that users can still install apps themselves if the [app permission policy](teams-app-permission-policies.md) that's assigned to them allows it.</span></span>

> [!Note]
> <span data-ttu-id="9944d-112">管理者がインストールしたアプリの場合、ユーザーはそれらのアプリをアンインストールできない。</span><span class="sxs-lookup"><span data-stu-id="9944d-112">For apps installed by admins, users can't uninstall those apps.</span></span>

<span data-ttu-id="9944d-113">アプリは、Teams デスクトップ クライアントの側と Teams モバイル クライアント (iOS と Android) の下部にあるアプリ バーにピン留めされます。</span><span class="sxs-lookup"><span data-stu-id="9944d-113">Apps are pinned to the app bar, which is the bar on the side of the Teams desktop client and at the bottom of the Teams mobile clients (iOS and Android).</span></span>

|<span data-ttu-id="9944d-114">Teams デスクトップ クライアント</span><span class="sxs-lookup"><span data-stu-id="9944d-114">Teams desktop client</span></span>  |<span data-ttu-id="9944d-115">Teams モバイル クライアント</span><span class="sxs-lookup"><span data-stu-id="9944d-115">Teams mobile client</span></span> |
|---------|---------|
|![デスクトップ Teams クライアント](media/app-setup-policies-desktop-app-bar.png)<br>  |   ![モバイル Teamsクライアント](media/mobile-app-ui.png)      |

<span data-ttu-id="9944d-118">管理者がインストールしたアプリを表示するには、アプリ バーで **[...] を選択します。デスクトップおよび** Web クライアントTeamsアプリを追加し、モバイル クライアントで上にスワイプします。</span><span class="sxs-lookup"><span data-stu-id="9944d-118">To see the apps installed by admins, in the app bar, users select **... More apps** in the Teams desktop and web clients and swipe up in the mobile clients.</span></span>

<span data-ttu-id="9944d-119">アプリセットアップ ポリシーは、管理センター Microsoft Teams管理します。</span><span class="sxs-lookup"><span data-stu-id="9944d-119">You manage app setup policies in the Microsoft Teams admin center.</span></span> <span data-ttu-id="9944d-120">グローバル (組織全体の既定) ポリシーを使用するか、カスタム ポリシーを作成して割り当てる。</span><span class="sxs-lookup"><span data-stu-id="9944d-120">Use the global (Org-wide default) policy or create and assign custom policies.</span></span>  <span data-ttu-id="9944d-121">組織内のユーザーに対して、カスタム ポリシーを作成して割り当てていない場合は、グローバル ポリシーが自動的に適用されます。</span><span class="sxs-lookup"><span data-stu-id="9944d-121">Users in your organization will automatically get the global policy unless you create and assign a custom policy.</span></span> <span data-ttu-id="9944d-122">これらのポリシーを管理するには、グローバル管理者または Teams サービス管理者である必要があります。</span><span class="sxs-lookup"><span data-stu-id="9944d-122">You must be a global admin or Teams service admin to manage these policies.</span></span>

<span data-ttu-id="9944d-123">グローバル ポリシーの設定を編集して、必要なアプリを含める。</span><span class="sxs-lookup"><span data-stu-id="9944d-123">You edit the settings in the global policy to include the apps that you want.</span></span> <span data-ttu-id="9944d-124">組織内のTeamsグループに合わせてカスタム ポリシーをカスタマイズするには、1 つ以上のカスタム ポリシーを作成して割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="9944d-124">To customize Teams for different groups of users in your organization, create and assign one or more custom policies.</span></span>

![[アプリセットアップ ポリシー] ページ](media/app-setup-policies.png)

> [!NOTE]
> <span data-ttu-id="9944d-126">Teams for Education を使用している場合は、割り当てアプリが既定でグローバル ポリシーにピン留めされているにもかかわらず、グローバル ポリシーに表示されません。</span><span class="sxs-lookup"><span data-stu-id="9944d-126">If you have Teams for Education, it's important to know that the Assignments app is pinned by default in the global policy even though currently, you don't see it listed in the global policy.</span></span> <span data-ttu-id="9944d-127">これは、クライアント上の固定アプリの一覧で 4 番目Teamsされます。</span><span class="sxs-lookup"><span data-stu-id="9944d-127">It will be the fourth app in the list of pinned apps on Teams clients.</span></span>

## <a name="create-a-custom-app-setup-policy"></a><span data-ttu-id="9944d-128">カスタム アプリ セットアップ ポリシーを作成する</span><span class="sxs-lookup"><span data-stu-id="9944d-128">Create a custom app setup policy</span></span>

<span data-ttu-id="9944d-129">管理センターの Microsoft Teamsを使用して、カスタム ポリシーを作成できます。</span><span class="sxs-lookup"><span data-stu-id="9944d-129">You can use the Microsoft Teams admin center to create a custom policy.</span></span>

1. <span data-ttu-id="9944d-130">管理センターの左側のナビゲーションMicrosoft Teams、[アプリのセットアップ ポリシー] **Teamsに**  >  **移動します**。</span><span class="sxs-lookup"><span data-stu-id="9944d-130">In the left navigation of the Microsoft Teams admin center, go to **Teams apps** > **Setup policies**.</span></span>

2. <span data-ttu-id="9944d-131">**[追加]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="9944d-131">Select **Add**.</span></span>

   ![[アプリセットアップ ポリシーの追加] ページ](media/app-setup-policies-add.png)

3. <span data-ttu-id="9944d-133">ポリシーの名前と説明を入力します。</span><span class="sxs-lookup"><span data-stu-id="9944d-133">Enter a name and description for the policy.</span></span>

4. <span data-ttu-id="9944d-134">ユーザーがカスタム アプリ **を** アップロードアプリにアップロードできるかどうかに応じて、カスタム アプリを有効またはTeams。</span><span class="sxs-lookup"><span data-stu-id="9944d-134">Turn on or turn off **Upload custom apps**, depending on whether you want to let users upload custom apps to Teams.</span></span> <span data-ttu-id="9944d-135">組織全体のアプリ設定で [サード パーティ製アプリを許可する] がオフになっている場合は、この[設定を変更できません](manage-apps.md#manage-org-wide-app-settings)。</span><span class="sxs-lookup"><span data-stu-id="9944d-135">You can't change this setting if **Allow third-party apps** is turned off in [org-wide app settings](manage-apps.md#manage-org-wide-app-settings).</span></span>

5. <span data-ttu-id="9944d-136">アプリをピン留めしてユーザーがアプリ バーをカスタマイズできるかどうかに応じて、[ユーザーの固定を許可する] をオンまたはオフにします。</span><span class="sxs-lookup"><span data-stu-id="9944d-136">Turn on or turn off **Allow user pinning**, depending on whether you want to let users personalize their app bar by pinning apps to it.</span></span>

   > [!NOTE]
   > <span data-ttu-id="9944d-137">[**ユーザー** のピン留めを許可する] 設定は、Microsoft 365 Government Community Cloud (GCC) 環境 (GCC、GCC High、DoD) の Teams 管理センターで使用できますが、現在は有効です。</span><span class="sxs-lookup"><span data-stu-id="9944d-137">The **Allow user pinning** setting is available in the Teams admin center in Microsoft 365 Government Community Cloud (GCC) environments (GCC, GCC High and DoD), but currently it has no effect.</span></span>

6. <span data-ttu-id="9944d-138">ユーザー用のアプリをインストールするには、次のタスクを実行します。</span><span class="sxs-lookup"><span data-stu-id="9944d-138">To install apps for users, do the following tasks:</span></span>

    1. <span data-ttu-id="9944d-139">[インストール **済みアプリ] で**、[アプリの **追加] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="9944d-139">Under **Installed apps**, select **Add apps**.</span></span>

    2. <span data-ttu-id="9944d-140">[インストール **済みアプリの追加**] ウィンドウで、ユーザーがアプリを起動するときに自動的にインストールするアプリTeams。</span><span class="sxs-lookup"><span data-stu-id="9944d-140">In the **Add installed apps** pane, search for the apps you want to automatically install for users when they start Teams.</span></span> <span data-ttu-id="9944d-141">アプリのアクセス許可ポリシーでアプリをフィルター処理することもできます。</span><span class="sxs-lookup"><span data-stu-id="9944d-141">You can also filter apps by app permission policy.</span></span> <span data-ttu-id="9944d-142">アプリの一覧を選択したら、[追加] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="9944d-142">When you've chosen your list of apps, select **Add**.</span></span>

       ![[インストールされているアプリの追加] ウィンドウ](media/app-setup-policies-add-installed-apps.png)

7. <span data-ttu-id="9944d-144">アプリをピン留めするには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="9944d-144">To pin apps, do the following steps:</span></span>

    1. <span data-ttu-id="9944d-145">[ピン **留めされたアプリ] で**、[アプリの **追加] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="9944d-145">Under **Pinned apps**, select **Add apps**.</span></span>

    2. <span data-ttu-id="9944d-146">[ピン留 **めされたアプリの追加** ] ウィンドウで、追加するアプリを検索し、[追加] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="9944d-146">In the **Add pinned apps** pane, search for the apps you want to add, and then select **Add**.</span></span> <span data-ttu-id="9944d-147">アプリのアクセス許可ポリシーでアプリをフィルター処理することもできます。</span><span class="sxs-lookup"><span data-stu-id="9944d-147">You can also filter apps by app permission policy.</span></span> <span data-ttu-id="9944d-148">ピン留めするアプリの一覧を選択したら、[追加] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="9944d-148">When you've chosen your list of apps to pin, select **Add**.</span></span>

       ![[ピン留めされたアプリの追加] ウィンドウ](media/app-setup-policies-add-apps.png)

    3. <span data-ttu-id="9944d-150">アプリをアプリに表示する順序で並Teams、[保存] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="9944d-150">Arrange the apps in the order that you want them to appear in Teams, and then select **Save**.</span></span>

       ![[ピン留めされたアプリ] セクション](media/app-setup-policies-new-policy-setup.png)

## <a name="edit-an-app-setup-policy"></a><span data-ttu-id="9944d-152">アプリセットアップ ポリシーを編集する</span><span class="sxs-lookup"><span data-stu-id="9944d-152">Edit an app setup policy</span></span>

<span data-ttu-id="9944d-153">Microsoft Teams管理センターを使用して、グローバル (組織全体の既定) ポリシーや作成したカスタム ポリシーなど、ポリシーを編集できます。</span><span class="sxs-lookup"><span data-stu-id="9944d-153">You can use the Microsoft Teams admin center to edit a policy, including the global (Org-wide default) policy and custom policies that you create.</span></span>

1. <span data-ttu-id="9944d-154">管理センターの左側のナビゲーションMicrosoft Teams、[アプリのセットアップ ポリシー] **Teamsに**  >  **移動します**。</span><span class="sxs-lookup"><span data-stu-id="9944d-154">In the left navigation of the Microsoft Teams admin center, go to **Teams apps** > **Setup policies**.</span></span>

2. <span data-ttu-id="9944d-155">ポリシー名の左側をクリックしてポリシーを選び、**[編集]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="9944d-155">Select the policy by clicking to the left of the policy name, and then select **Edit**.</span></span>

3. <span data-ttu-id="9944d-156">ここで、希望する変更を行います。</span><span class="sxs-lookup"><span data-stu-id="9944d-156">From here, make the changes that you want.</span></span>

4. <span data-ttu-id="9944d-157">**[保存]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="9944d-157">Select **Save**.</span></span>

## <a name="assign-a-custom-app-setup-policy-to-users"></a><span data-ttu-id="9944d-158">カスタム アプリセットアップ ポリシーをユーザーに割り当てる</span><span class="sxs-lookup"><span data-stu-id="9944d-158">Assign a custom app setup policy to users</span></span>

[!INCLUDE [assign-policy](includes/assign-policy.md)]

## <a name="faq"></a><span data-ttu-id="9944d-159">よくあるご質問 (FAQ)</span><span class="sxs-lookup"><span data-stu-id="9944d-159">FAQ</span></span>

### <a name="working-with-app-setup-policies"></a><span data-ttu-id="9944d-160">アプリセットアップ ポリシーの操作</span><span class="sxs-lookup"><span data-stu-id="9944d-160">Working with app setup policies</span></span>

#### <a name="what-built-in-app-setup-policies-are-included-in-the-microsoft-teams-admin-center"></a><span data-ttu-id="9944d-161">管理センターに含まれる組み込みのアプリ Microsoft Teamsポリシー</span><span class="sxs-lookup"><span data-stu-id="9944d-161">What built-in app setup policies are included in the Microsoft Teams admin center</span></span>

- <span data-ttu-id="9944d-162">**グローバル (組織全体の既定値)**: この既定のポリシーは、別のポリシーを割り当てない限り、組織内のすべてのユーザーに適用されます。</span><span class="sxs-lookup"><span data-stu-id="9944d-162">**Global (Org-wide default)**: This default policy applies to all users in your organization unless you assign another policy.</span></span> <span data-ttu-id="9944d-163">グローバル ポリシーを編集して、ユーザーにとって最も重要なアプリをピン留めします。</span><span class="sxs-lookup"><span data-stu-id="9944d-163">Edit the global policy to pin apps that are most important for your users.</span></span>

- <span data-ttu-id="9944d-164">**FrontlineWorker:** このポリシーは、Frontline Worker 向けです。</span><span class="sxs-lookup"><span data-stu-id="9944d-164">**FrontlineWorker**: This policy is for Frontline Workers.</span></span> <span data-ttu-id="9944d-165">組織内の Frontline Worker に割り当て可能です。</span><span class="sxs-lookup"><span data-stu-id="9944d-165">You can assign it to Frontline Workers in your organization.</span></span> <span data-ttu-id="9944d-166">作成するカスタム ポリシーと同様に、設定をアクティブにするにはユーザーにポリシーを割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="9944d-166">It's important to know that like custom policies that you create, you have to assign the policy to users for the settings to be active.</span></span> <span data-ttu-id="9944d-167">詳細については、この記事の「 [カスタム](#assign-a-custom-app-setup-policy-to-users) アプリセットアップ ポリシーをユーザーに割り当てる」セクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="9944d-167">For more information, go to the [Assign a custom app setup policy to users](#assign-a-custom-app-setup-policy-to-users) section of this article.</span></span>

#### <a name="why-cant-i-find-an-app-in-the-add-pinned-apps-pane"></a><span data-ttu-id="9944d-168">[ピン留めされたアプリの追加] ウィンドウにアプリが見当たらない理由</span><span class="sxs-lookup"><span data-stu-id="9944d-168">Why can't I find an app in the Add pinned apps pane</span></span>

<span data-ttu-id="9944d-169">すべてのアプリをアプリ セットアップ ポリシーをTeamsにピン留めすることはできません。</span><span class="sxs-lookup"><span data-stu-id="9944d-169">Not all apps can be pinned to Teams through an app setup policy.</span></span> <span data-ttu-id="9944d-170">一部のアプリでは、この機能がサポートされていない場合があります。</span><span class="sxs-lookup"><span data-stu-id="9944d-170">Some apps may not support this functionality.</span></span> <span data-ttu-id="9944d-171">ピン留めできるアプリを見つけるには、[ピン留めされたアプリの追加] **ウィンドウでアプリを検索** します。</span><span class="sxs-lookup"><span data-stu-id="9944d-171">To find apps that can be pinned, search for the app in the **Add pinned apps** pane.</span></span> <span data-ttu-id="9944d-172">個人用スコープ (静的タブ) とボットを持つタブは Teams デスクトップ クライアントにピン留めできます。これらのアプリは、[ピン留めされたアプリの追加] ウィンドウ **で使用** できます。</span><span class="sxs-lookup"><span data-stu-id="9944d-172">Tabs that have a personal scope (static tabs) and bots can be pinned to the Teams desktop client and these apps are available in the **Add pinned apps** pane.</span></span>

<span data-ttu-id="9944d-173">アプリ ストアには、すべてのアプリTeams一覧が表示Teamsしてください。</span><span class="sxs-lookup"><span data-stu-id="9944d-173">Keep in mind that the Teams app store lists all Teams apps.</span></span> <span data-ttu-id="9944d-174">[**ピン留めされたアプリの追加**] ウィンドウには、ポリシーを使用してアプリにピン留Teamsアプリだけが表示されます。</span><span class="sxs-lookup"><span data-stu-id="9944d-174">The **Add pinned apps** pane includes only apps that can be pinned to Teams through a policy.</span></span>

#### <a name="im-a-teams-for-education-admin-what-do-i-need-to-know-about-app-setup-policies-in-teams-for-education"></a><span data-ttu-id="9944d-175">Education 管理者Teamsです。Teams for Education のアプリ セットアップ ポリシーについて知りたい</span><span class="sxs-lookup"><span data-stu-id="9944d-175">I'm a Teams for Education admin. What do I need to know about app setup policies in Teams for Education</span></span>

<span data-ttu-id="9944d-176">通話アプリは、Teams では使用できません。</span><span class="sxs-lookup"><span data-stu-id="9944d-176">The Calling app isn't available in Teams for Education.</span></span> <span data-ttu-id="9944d-177">新しいカスタム アプリセットアップ ポリシーを作成すると、呼び出し元アプリがアプリの一覧に表示されます。</span><span class="sxs-lookup"><span data-stu-id="9944d-177">When you create a new custom app setup policy, the Calling app is displayed in the list of apps.</span></span> <span data-ttu-id="9944d-178">ただし、アプリはクライアントにピン留めTeamsされません。Teams for Education ユーザーは、Teams で通話アプリを表示しません。</span><span class="sxs-lookup"><span data-stu-id="9944d-178">However, the app isn't pinned to Teams clients and Teams for Education users won't see the Calls app in Teams.</span></span>

#### <a name="how-many-pinned-apps-can-be-added-to-a-policy"></a><span data-ttu-id="9944d-179">ポリシーに追加できるピン留めされたアプリの数</span><span class="sxs-lookup"><span data-stu-id="9944d-179">How many pinned apps can be added to a policy</span></span>

<span data-ttu-id="9944d-180">少なくとも 2 つのアプリを、モバイル クライアント (iOS Teams Android) にピン留めする必要があります。</span><span class="sxs-lookup"><span data-stu-id="9944d-180">A minimum of two apps must be pinned to the Teams mobile clients (iOS and Android).</span></span> <span data-ttu-id="9944d-181">ポリシーのアプリ数が 2 未満の場合、モバイル クライアントはポリシー設定を反映しません。代わりに、既存の構成を引き続き使用します。</span><span class="sxs-lookup"><span data-stu-id="9944d-181">If a policy has fewer than two apps, the mobile clients won't reflect the policy settings and instead will continue to use the existing configuration.</span></span>

<span data-ttu-id="9944d-182">ポリシーに追加できる固定アプリの数に制限はありません。</span><span class="sxs-lookup"><span data-stu-id="9944d-182">There's no limit on the number of pinned apps you can add to a policy.</span></span>

#### <a name="how-long-does-it-take-for-policy-changes-to-take-effect"></a><span data-ttu-id="9944d-183">ポリシーの変更が有効にされるのにかかる時間</span><span class="sxs-lookup"><span data-stu-id="9944d-183">How long does it take for policy changes to take effect</span></span>

<span data-ttu-id="9944d-184">ポリシーを編集既するか割り当てた後、変更が反映されるまでに数時間かかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="9944d-184">After you edit or assign a policy, it can take a few hours for changes to take effect.</span></span>

### <a name="user-experience"></a><span data-ttu-id="9944d-185">ユーザー エクスペリエンス</span><span class="sxs-lookup"><span data-stu-id="9944d-185">User experience</span></span>

#### <a name="how-can-users-see-all-their-pinned-apps-in-teams"></a><span data-ttu-id="9944d-186">ユーザーがピン留めされたアプリをすべてのアプリに表示Teams</span><span class="sxs-lookup"><span data-stu-id="9944d-186">How can users see all their pinned apps in Teams</span></span>

<span data-ttu-id="9944d-187">ユーザー用にピン留めされているアプリを表示するには、インストールされているアプリの数とクライアント ウィンドウのサイズに応じて、次Teamsがあります。</span><span class="sxs-lookup"><span data-stu-id="9944d-187">To view all apps that are pinned for a user, users might have to do the following depending on the number of installed apps and the size of their Teams client window.</span></span>

|<span data-ttu-id="9944d-188">Teams デスクトップ クライアント</span><span class="sxs-lookup"><span data-stu-id="9944d-188">Teams desktop client</span></span> |<span data-ttu-id="9944d-189">Teams モバイル クライアント</span><span class="sxs-lookup"><span data-stu-id="9944d-189">Teams mobile client</span></span> |
|---------|---------|
|<span data-ttu-id="9944d-190">アプリの横にあるアプリ バーで、[Teams]**を選択します。その他のアプリ**。</span><span class="sxs-lookup"><span data-stu-id="9944d-190">In the app bar on the side of Teams, select **... More apps**.</span></span>| <span data-ttu-id="9944d-191">アプリ バーの下部付近にあるアプリTeams上にスワイプします。</span><span class="sxs-lookup"><span data-stu-id="9944d-191">In the app bar near the bottom of Teams, swipe up.</span></span>|
|![デスクトップ クライアントのその他Teamsアプリ](media/app-setup-policies-desktop-more-apps.png)<br>   |![モバイル クライアントのアプリTeamsする](media/app-setup-policies-mobile-more-apps.png)  

#### <a name="what-do-i-need-to-know-about-the-teams-mobile-experience"></a><span data-ttu-id="9944d-194">モバイル エクスペリエンスについて知Teams必要がある情報</span><span class="sxs-lookup"><span data-stu-id="9944d-194">What do I need to know about the Teams mobile experience</span></span>

<span data-ttu-id="9944d-195">モバイル Teams (iOS および Android) では、静的タブを含む個人用アプリがサポートされています。</span><span class="sxs-lookup"><span data-stu-id="9944d-195">The Teams mobile clients (iOS and Android) support personal apps with static tabs.</span></span> <span data-ttu-id="9944d-196">デスクトップ クライアントにピンTeamsされたアプリは、モバイル クライアントTeams表示されます。</span><span class="sxs-lookup"><span data-stu-id="9944d-196">Apps pinned to the Teams desktop client will appear in the Teams mobile clients.</span></span> <span data-ttu-id="9944d-197">個人用ボットは、モバイル クライアントのチャットに表示されます。</span><span class="sxs-lookup"><span data-stu-id="9944d-197">Personal bots will appear in Chat on mobile clients.</span></span>

<span data-ttu-id="9944d-198">サード パーティ製アプリ (Teams Store からダウンロードできます) は、モバイルに表示される前に承認される必要があります。</span><span class="sxs-lookup"><span data-stu-id="9944d-198">Third-party apps (which can be downloaded from Teams Store) need to be approved before they show up on mobile.</span></span> <span data-ttu-id="9944d-199">管理者が、Microsoft for Mobile で承認されていないアプリをピンで固定すると、Teams デスクトップに表示されますが、モバイルには表示されません。</span><span class="sxs-lookup"><span data-stu-id="9944d-199">If an admin pins an app, which is unapproved by Microsoft for Mobile, it will show up on the Teams Desktop, but not show up on mobile.</span></span> <span data-ttu-id="9944d-200">詳細については [、「モバイル クライアント](/microsoftteams/platform/tabs/what-are-tabs#mobile-clients) 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9944d-200">See [Mobile clients](/microsoftteams/platform/tabs/what-are-tabs#mobile-clients) for more information.</span></span>

<span data-ttu-id="9944d-201">Teams モバイル クライアントでは、ユーザーにはアクティビティ、チャット、Teams などのコア Teams アプリが表示され、Shifts などの一部のファースト パーティ アプリを Microsoft からピン留めできます。</span><span class="sxs-lookup"><span data-stu-id="9944d-201">With the Teams mobile clients, users will see core Teams apps such as Activity, Chat, and Teams, and you can pin some first-party apps from Microsoft, such as Shifts.</span></span>

#### <a name="can-users-change-the-order-of-apps-pinned-through-a-policy"></a><span data-ttu-id="9944d-202">ユーザーがポリシーを使用してピン留めされたアプリの順序を変更できる</span><span class="sxs-lookup"><span data-stu-id="9944d-202">Can users change the order of apps pinned through a policy</span></span>

<span data-ttu-id="9944d-203">[ユーザーのピン留めを許可する] オプションがオンになっている場合、Teamsクライアント上の固定アプリの **順序を変更** できます。</span><span class="sxs-lookup"><span data-stu-id="9944d-203">Users can change the order of their pinned apps on Teams desktop and mobile clients if the **Allow user pinning** option is turned on.</span></span> <span data-ttu-id="9944d-204">ユーザーは、Web クライアントでピン留めされたアプリのTeams変更することはできません。</span><span class="sxs-lookup"><span data-stu-id="9944d-204">Users can't change the order of their pinned apps on Teams web clients.</span></span>

#### <a name="does-user-pinning-take-precedence"></a><span data-ttu-id="9944d-205">ユーザーのピン留めが優先されますか</span><span class="sxs-lookup"><span data-stu-id="9944d-205">Does user pinning take precedence</span></span>

<span data-ttu-id="9944d-206">管理ピンは常に優先されます。</span><span class="sxs-lookup"><span data-stu-id="9944d-206">Admin pins always take precedence.</span></span> <span data-ttu-id="9944d-207">[ユーザー **固定を許可する]** オプションがオンになっている場合、ユーザーは、管理者固定アプリの下にピン留めされたアプリを保持します。</span><span class="sxs-lookup"><span data-stu-id="9944d-207">If the **Allow user pinning** option is turned on, then users will retain their pinned apps below admin pinned apps.</span></span> <span data-ttu-id="9944d-208">[ユーザー **固定を** 許可する] オプションがオフになっている場合、ユーザーは既存のピンを失い、管理者固定アプリだけがアプリ バーに表示されます。</span><span class="sxs-lookup"><span data-stu-id="9944d-208">If the **Allow user pinning** option is turned off, then users will lose their pre-existing pins, and only admin-pinned apps will be present in the app bar.</span></span>

### <a name="custom-teams-apps"></a><span data-ttu-id="9944d-209">カスタム Teams アプリ</span><span class="sxs-lookup"><span data-stu-id="9944d-209">Custom Teams apps</span></span>

<span data-ttu-id="9944d-210">組織でカスタム Teams アプリを構築し、AppSource またはテナント アプリ カタログに発行しましたが、アプリが Teams のアプリ バーにピン留めされている場合、アプリ アイコンは期待した通り表示されません。</span><span class="sxs-lookup"><span data-stu-id="9944d-210">My organization built a custom Teams app and published it, either to AppSource or the tenant app catalog, but the app icon isn't displayed as expected when the app is pinned to the app bar in Teams.</span></span> <span data-ttu-id="9944d-211">修正方法</span><span class="sxs-lookup"><span data-stu-id="9944d-211">How do I fix it</span></span>

<span data-ttu-id="9944d-212">アプリを送信する前に、ロゴのガイドラインに従う必要があります。</span><span class="sxs-lookup"><span data-stu-id="9944d-212">Make sure that you follow the logo guidelines before you submit the app.</span></span> <span data-ttu-id="9944d-213">詳細については、販売者ダッシュボード提出の [チェックリストに関するページを参照してください](/microsoftteams/platform/concepts/deploy-and-publish/appsource/prepare/overview)。</span><span class="sxs-lookup"><span data-stu-id="9944d-213">To learn more, see [Checklist for Seller Dashboard submission](/microsoftteams/platform/concepts/deploy-and-publish/appsource/prepare/overview).</span></span>

## <a name="related-topics"></a><span data-ttu-id="9944d-214">関連項目</span><span class="sxs-lookup"><span data-stu-id="9944d-214">Related topics</span></span>

[<span data-ttu-id="9944d-215">Teams でのアプリの管理設定</span><span class="sxs-lookup"><span data-stu-id="9944d-215">Admin settings for apps in Teams</span></span>](admin-settings.md)

[<span data-ttu-id="9944d-216"> Teams でユーザーにポリシーを割り当てる</span><span class="sxs-lookup"><span data-stu-id="9944d-216">Assign policies to your users in Teams</span></span>](assign-policies.md)
