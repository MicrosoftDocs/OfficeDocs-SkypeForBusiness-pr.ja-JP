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
description: 組織内のユーザー向け Microsoft Teams でアプリセットアップ ポリシーを使用および管理する方法について説明します。
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.appsetuppolicies.overview
ms.openlocfilehash: a58cbf682760249ee3b269d1765a265cc58d3022
ms.sourcegitcommit: 31a585cc0fe6350efacf3a7771d1e590d5e4233c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/10/2021
ms.locfileid: "50615093"
---
# <a name="manage-app-setup-policies-in-microsoft-teams"></a><span data-ttu-id="ed591-103">Microsoft Teams のアプリのセットアップ ポリシーを管理する</span><span class="sxs-lookup"><span data-stu-id="ed591-103">Manage app setup policies in Microsoft Teams</span></span>

> [!NOTE]
> <span data-ttu-id="ed591-104">組織全体のアプリ設定を有効にした場合は、カスタム アプリの操作を許可すると、Microsoft Teams 管理センターにアプリセットアップ ポリシーがまだ表示されない場合があります。</span><span class="sxs-lookup"><span data-stu-id="ed591-104">If you enabled the org-wide app setting, **Allow interaction with custom apps**, you might not see app setup policies yet in the Microsoft Teams admin center.</span></span> <span data-ttu-id="ed591-105">現在、展開中で、組織で間もなく利用可能になる予定です。</span><span class="sxs-lookup"><span data-stu-id="ed591-105">It's currently being rolled out and will be available soon in your organization.</span></span>

<span data-ttu-id="ed591-106">管理者は、アプリセットアップ ポリシーを使用して、次のタスクを実行できます。</span><span class="sxs-lookup"><span data-stu-id="ed591-106">As an admin, you can use app setup policies to do the following tasks:</span></span>

- <span data-ttu-id="ed591-107">Teams をカスタマイズして、ユーザーにとって最も重要なアプリを強調表示します。</span><span class="sxs-lookup"><span data-stu-id="ed591-107">Customize Teams to highlight the apps that are most important for your users.</span></span> <span data-ttu-id="ed591-108">ピン留めするアプリを選び、表示される順序を設定します。</span><span class="sxs-lookup"><span data-stu-id="ed591-108">You choose the apps to pin and set the order that they appear.</span></span> <span data-ttu-id="ed591-109">アプリをピン留めすると、サードパーティや組織内の開発者が作成したアプリなど、組織内のユーザーが必要とするアプリを紹介できます。</span><span class="sxs-lookup"><span data-stu-id="ed591-109">Pinning apps lets you showcase apps that users in your organization need, including apps built by third parties or by developers in your organization.</span></span>
- <span data-ttu-id="ed591-110">ユーザーがアプリを Teams にピン留めできるかどうかを制御します。</span><span class="sxs-lookup"><span data-stu-id="ed591-110">Control whether users can pin apps to Teams.</span></span>
- <span data-ttu-id="ed591-111">ユーザーの代わりにアプリをインストールします。</span><span class="sxs-lookup"><span data-stu-id="ed591-111">Install apps on behalf of users.</span></span> <span data-ttu-id="ed591-112">ユーザーが Teams を起動するときに、既定でインストールするアプリを選択します。</span><span class="sxs-lookup"><span data-stu-id="ed591-112">You choose which apps are installed by default for users when they start Teams.</span></span> <span data-ttu-id="ed591-113">ユーザーに割り当てられているアプリのアクセス許可ポリシーで許可[](teams-app-permission-policies.md)されている場合でも、ユーザーはアプリを自分でインストールできます。</span><span class="sxs-lookup"><span data-stu-id="ed591-113">Keep in mind that users can still install apps themselves if the [app permission policy](teams-app-permission-policies.md) that's assigned to them allows it.</span></span>

> [!Note]
> <span data-ttu-id="ed591-114">管理者がインストールしたアプリの場合、ユーザーはそれらのアプリをアンインストールできます。</span><span class="sxs-lookup"><span data-stu-id="ed591-114">For apps installed by admins, users can't uninstall those apps.</span></span>

<span data-ttu-id="ed591-115">アプリは、Teams デスクトップ クライアントの横と Teams モバイル クライアント (iOS および Android) の下部にあるアプリ バーにピン留めされます。</span><span class="sxs-lookup"><span data-stu-id="ed591-115">Apps are pinned to the app bar, which is the bar on the side of the Teams desktop client and at the bottom of the Teams mobile clients (iOS and Android).</span></span>

|<span data-ttu-id="ed591-116">Teams デスクトップ クライアント</span><span class="sxs-lookup"><span data-stu-id="ed591-116">Teams desktop client</span></span>  |<span data-ttu-id="ed591-117">Teams モバイル クライアント</span><span class="sxs-lookup"><span data-stu-id="ed591-117">Teams mobile client</span></span> |
|---------|---------|
|![Teams デスクトップ クライアント](media/app-setup-policies-desktop-app-bar.png)<br>  |   ![Teams モバイル クライアント](media/mobile-app-ui.png)      |

<span data-ttu-id="ed591-120">管理者がインストールしたアプリを表示するには、アプリ バーで **[...Teams デスクトップおよび** Web クライアント内のその他のアプリと、モバイル クライアントで上にスワイプします。</span><span class="sxs-lookup"><span data-stu-id="ed591-120">To see the apps installed by admins, in the app bar, users select **... More apps** in the Teams desktop and web clients and swipe up in the mobile clients.</span></span>

<span data-ttu-id="ed591-121">Microsoft Teams 管理センターでアプリセットアップ ポリシーを管理します。</span><span class="sxs-lookup"><span data-stu-id="ed591-121">You manage app setup policies in the Microsoft Teams admin center.</span></span> <span data-ttu-id="ed591-122">グローバル (組織全体の既定) ポリシーを使用するか、カスタム ポリシーを作成して割り当てる。</span><span class="sxs-lookup"><span data-stu-id="ed591-122">Use the global (Org-wide default) policy or create and assign custom policies.</span></span>  <span data-ttu-id="ed591-123">カスタム ポリシーを作成して割り当てていない場合、組織内のユーザーにはグローバル ポリシーが自動的に適用されます。</span><span class="sxs-lookup"><span data-stu-id="ed591-123">Users in your organization will automatically get the global policy unless you create and assign a custom policy.</span></span> <span data-ttu-id="ed591-124">これらのポリシーを管理するには、グローバル管理者または Teams サービス管理者である必要があります。</span><span class="sxs-lookup"><span data-stu-id="ed591-124">You must be a global admin or Teams service admin to manage these policies.</span></span>

<span data-ttu-id="ed591-125">グローバル ポリシーの設定を編集して、必要なアプリを含める。</span><span class="sxs-lookup"><span data-stu-id="ed591-125">You edit the settings in the global policy to include the apps that you want.</span></span> <span data-ttu-id="ed591-126">組織内のユーザーのグループごとに Teams をカスタマイズするには、1 つ以上のカスタム ポリシーを作成して割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="ed591-126">To customize Teams for different groups of users in your organization, create and assign one or more custom policies.</span></span>

![[アプリセットアップ ポリシー] ページ](media/app-setup-policies.png)

> [!NOTE]
> <span data-ttu-id="ed591-128">Teams for Education をお持ちである場合は、割り当てアプリが既定でグローバル ポリシーにピン留めされているにもかかわらず、グローバル ポリシーに表示されません。</span><span class="sxs-lookup"><span data-stu-id="ed591-128">If you have Teams for Education, it's important to know that the Assignments app is pinned by default in the global policy even though currently, you don't see it listed in the global policy.</span></span> <span data-ttu-id="ed591-129">これは、Teams クライアントにピン留めされたアプリの一覧で 4 番目のアプリになります。</span><span class="sxs-lookup"><span data-stu-id="ed591-129">It will be the fourth app in the list of pinned apps on Teams clients.</span></span>

## <a name="create-a-custom-app-setup-policy"></a><span data-ttu-id="ed591-130">カスタム アプリセットアップ ポリシーを作成する</span><span class="sxs-lookup"><span data-stu-id="ed591-130">Create a custom app setup policy</span></span>

<span data-ttu-id="ed591-131">Microsoft Teams 管理センターを使用して、カスタム ポリシーを作成できます。</span><span class="sxs-lookup"><span data-stu-id="ed591-131">You can use the Microsoft Teams admin center to create a custom policy.</span></span>

1. <span data-ttu-id="ed591-132">Microsoft Teams 管理センターの左側のナビゲーションで **、Teams アプリのセットアップ** ポリシー  >  **に移動します**。</span><span class="sxs-lookup"><span data-stu-id="ed591-132">In the left navigation of the Microsoft Teams admin center, go to **Teams apps** > **Setup policies**.</span></span>

2. <span data-ttu-id="ed591-133">**[追加]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="ed591-133">Select **Add**.</span></span>

   ![[アプリセットアップ ポリシーの追加] ページ](media/app-setup-policies-add.png)

3. <span data-ttu-id="ed591-135">ポリシーの名前と説明を入力します。</span><span class="sxs-lookup"><span data-stu-id="ed591-135">Enter a name and description for the policy.</span></span>

4. <span data-ttu-id="ed591-136">ユーザーがカスタム アプリ **を** Teams にアップロードできるかどうかに応じて、カスタム アプリのアップロードをオンまたはオフにします。</span><span class="sxs-lookup"><span data-stu-id="ed591-136">Turn on or turn off **Upload custom apps**, depending on whether you want to let users upload custom apps to Teams.</span></span> <span data-ttu-id="ed591-137">組織全体のアプリ設定で [サード パーティ製アプリを許可する] がオフになっている場合、この設定[を変更できません](manage-apps.md#manage-org-wide-app-settings)。</span><span class="sxs-lookup"><span data-stu-id="ed591-137">You can't change this setting if **Allow third-party apps** is turned off in [org-wide app settings](manage-apps.md#manage-org-wide-app-settings).</span></span>

5. <span data-ttu-id="ed591-138">アプリをピン留めしてユーザーがアプリ バーをカスタマイズできるかどうかに応じて、ユーザーのピン留めを許可する機能をオンまたはオフにします。</span><span class="sxs-lookup"><span data-stu-id="ed591-138">Turn on or turn off **Allow user pinning**, depending on whether you want to let users personalize their app bar by pinning apps to it.</span></span>

   > [!NOTE]
   > <span data-ttu-id="ed591-139">[ユーザーのピン留めを許可する] 設定は、Microsoft 365 Government Community Cloud (GCC) 環境 (GCC、GCC High、DoD) の Teams 管理センターで使用できますが、現在は有効な機能はありません。</span><span class="sxs-lookup"><span data-stu-id="ed591-139">The **Allow user pinning** setting is available in the Teams admin center in Microsoft 365 Government Community Cloud (GCC) environments (GCC, GCC High and DoD), but currently it has no effect.</span></span>

6. <span data-ttu-id="ed591-140">ユーザー用のアプリをインストールするには、次のタスクを実行します。</span><span class="sxs-lookup"><span data-stu-id="ed591-140">To install apps for users, do the following tasks:</span></span>

    1. <span data-ttu-id="ed591-141">[インストール **されているアプリ] で、[** アプリの **追加] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="ed591-141">Under **Installed apps**, select **Add apps**.</span></span>

    2. <span data-ttu-id="ed591-142">[インストール済 **みアプリの追加** ] ウィンドウで、ユーザーが Teams を起動するときに自動的にインストールするアプリを検索します。</span><span class="sxs-lookup"><span data-stu-id="ed591-142">In the **Add installed apps** pane, search for the apps you want to automatically install for users when they start Teams.</span></span> <span data-ttu-id="ed591-143">アプリのアクセス許可ポリシーでアプリをフィルター処理することもできます。</span><span class="sxs-lookup"><span data-stu-id="ed591-143">You can also filter apps by app permission policy.</span></span> <span data-ttu-id="ed591-144">アプリの一覧を選択したら、[追加] を選択 **します**。</span><span class="sxs-lookup"><span data-stu-id="ed591-144">When you've chosen your list of apps, select **Add**.</span></span>

       ![[インストールされているアプリの追加] ウィンドウ](media/app-setup-policies-add-installed-apps.png)

7. <span data-ttu-id="ed591-146">アプリをピン留めするには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="ed591-146">To pin apps, do the following steps:</span></span>

    1. <span data-ttu-id="ed591-147">[ピン **留めされたアプリ] で**[アプリの **追加] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="ed591-147">Under **Pinned apps**, select **Add apps**.</span></span>

    2. <span data-ttu-id="ed591-148">[ピン留 **めされたアプリの追加** ] ウィンドウで、追加するアプリを検索し、[追加] を選択 **します**。</span><span class="sxs-lookup"><span data-stu-id="ed591-148">In the **Add pinned apps** pane, search for the apps you want to add, and then select **Add**.</span></span> <span data-ttu-id="ed591-149">アプリのアクセス許可ポリシーでアプリをフィルター処理することもできます。</span><span class="sxs-lookup"><span data-stu-id="ed591-149">You can also filter apps by app permission policy.</span></span> <span data-ttu-id="ed591-150">ピン留めするアプリの一覧を選択したら、[追加] を選択 **します**。</span><span class="sxs-lookup"><span data-stu-id="ed591-150">When you've chosen your list of apps to pin, select **Add**.</span></span>

       ![[ピン留めされたアプリの追加] ウィンドウ](media/app-setup-policies-add-apps.png)

    3. <span data-ttu-id="ed591-152">アプリを Teams に表示する順序で配置し、[保存] を選択 **します**。</span><span class="sxs-lookup"><span data-stu-id="ed591-152">Arrange the apps in the order that you want them to appear in Teams, and then select **Save**.</span></span>

       ![[ピン留めされたアプリ] セクション](media/app-setup-policies-new-policy-setup.png)

## <a name="edit-an-app-setup-policy"></a><span data-ttu-id="ed591-154">アプリセットアップ ポリシーを編集する</span><span class="sxs-lookup"><span data-stu-id="ed591-154">Edit an app setup policy</span></span>

<span data-ttu-id="ed591-155">Microsoft Teams 管理センターを使用して、作成したグローバル (組織全体の既定) ポリシーやカスタム ポリシーなどのポリシーを編集できます。</span><span class="sxs-lookup"><span data-stu-id="ed591-155">You can use the Microsoft Teams admin center to edit a policy, including the global (Org-wide default) policy and custom policies that you create.</span></span>

1. <span data-ttu-id="ed591-156">Microsoft Teams 管理センターの左側のナビゲーションで **、Teams アプリのセットアップ** ポリシー  >  **に移動します**。</span><span class="sxs-lookup"><span data-stu-id="ed591-156">In the left navigation of the Microsoft Teams admin center, go to **Teams apps** > **Setup policies**.</span></span>

2. <span data-ttu-id="ed591-157">ポリシー名の左側をクリックしてポリシーを選び、**[編集]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="ed591-157">Select the policy by clicking to the left of the policy name, and then select **Edit**.</span></span>

3. <span data-ttu-id="ed591-158">ここで、希望する変更を行います。</span><span class="sxs-lookup"><span data-stu-id="ed591-158">From here, make the changes that you want.</span></span>

4. <span data-ttu-id="ed591-159">**[保存]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="ed591-159">Select **Save**.</span></span>

## <a name="assign-a-custom-app-setup-policy-to-users"></a><span data-ttu-id="ed591-160">カスタム アプリセットアップ ポリシーをユーザーに割り当てる</span><span class="sxs-lookup"><span data-stu-id="ed591-160">Assign a custom app setup policy to users</span></span>

[!INCLUDE [assign-policy](includes/assign-policy.md)]

## <a name="faq"></a><span data-ttu-id="ed591-161">よくあるご質問 (FAQ)</span><span class="sxs-lookup"><span data-stu-id="ed591-161">FAQ</span></span>

### <a name="working-with-app-setup-policies"></a><span data-ttu-id="ed591-162">アプリセットアップ ポリシーを使用する</span><span class="sxs-lookup"><span data-stu-id="ed591-162">Working with app setup policies</span></span>

#### <a name="what-built-in-app-setup-policies-are-included-in-the-microsoft-teams-admin-center"></a><span data-ttu-id="ed591-163">Microsoft Teams 管理センターに含まれる組み込みのアプリセットアップ ポリシー</span><span class="sxs-lookup"><span data-stu-id="ed591-163">What built-in app setup policies are included in the Microsoft Teams admin center</span></span>

- <span data-ttu-id="ed591-164">**グローバル (組織全体の既定)**: この既定のポリシーは、別のポリシーを割り当てない限り、組織内のすべてのユーザーに適用されます。</span><span class="sxs-lookup"><span data-stu-id="ed591-164">**Global (Org-wide default)**: This default policy applies to all users in your organization unless you assign another policy.</span></span> <span data-ttu-id="ed591-165">グローバル ポリシーを編集して、ユーザーにとって最も重要なアプリをピン留めします。</span><span class="sxs-lookup"><span data-stu-id="ed591-165">Edit the global policy to pin apps that are most important for your users.</span></span>

- <span data-ttu-id="ed591-166">**FrontlineWorker:** このポリシーは、Frontline Worker 向けです。</span><span class="sxs-lookup"><span data-stu-id="ed591-166">**FrontlineWorker**: This policy is for Frontline Workers.</span></span> <span data-ttu-id="ed591-167">組織内の Frontline Worker に割り当てできます。</span><span class="sxs-lookup"><span data-stu-id="ed591-167">You can assign it to Frontline Workers in your organization.</span></span> <span data-ttu-id="ed591-168">作成するカスタム ポリシーと同様に、設定をアクティブにするにはユーザーにポリシーを割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="ed591-168">It's important to know that like custom policies that you create, you have to assign the policy to users for the settings to be active.</span></span> <span data-ttu-id="ed591-169">詳細については、この記事の「カスタム アプリセットアップ [ポリシーを](#assign-a-custom-app-setup-policy-to-users) ユーザーに割り当てる」セクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="ed591-169">For more information, go to the [Assign a custom app setup policy to users](#assign-a-custom-app-setup-policy-to-users) section of this article.</span></span>

#### <a name="why-cant-i-find-an-app-in-the-add-pinned-apps-pane"></a><span data-ttu-id="ed591-170">[ピン留めされたアプリの追加] ウィンドウでアプリが見当たらない理由</span><span class="sxs-lookup"><span data-stu-id="ed591-170">Why can't I find an app in the Add pinned apps pane</span></span>

<span data-ttu-id="ed591-171">アプリセットアップ ポリシーを使用して、すべてのアプリを Teams にピン留めできない。</span><span class="sxs-lookup"><span data-stu-id="ed591-171">Not all apps can be pinned to Teams through an app setup policy.</span></span> <span data-ttu-id="ed591-172">一部のアプリでは、この機能がサポートされていない場合があります。</span><span class="sxs-lookup"><span data-stu-id="ed591-172">Some apps may not support this functionality.</span></span> <span data-ttu-id="ed591-173">ピン留めできるアプリを見つけるには、[ピン留めされたアプリの追加] ウィンドウ **でアプリを検索** します。</span><span class="sxs-lookup"><span data-stu-id="ed591-173">To find apps that can be pinned, search for the app in the **Add pinned apps** pane.</span></span> <span data-ttu-id="ed591-174">個人用の範囲 (静的なタブ) とボットを含むタブは、Teams デスクトップ クライアントにピン留めできます。これらのアプリは、[ピン留めされたアプリの追加] ウィンドウ **で使用** できます。</span><span class="sxs-lookup"><span data-stu-id="ed591-174">Tabs that have a personal scope (static tabs) and bots can be pinned to the Teams desktop client and these apps are available in the **Add pinned apps** pane.</span></span>

<span data-ttu-id="ed591-175">Teams アプリ ストアには、すべての Teams アプリが一覧表示されます。</span><span class="sxs-lookup"><span data-stu-id="ed591-175">Keep in mind that the Teams app store lists all Teams apps.</span></span> <span data-ttu-id="ed591-176">[ **ピン留めされたアプリの追加** ] ウィンドウには、ポリシーを通じて Teams にピン留めできるアプリだけが含まれます。</span><span class="sxs-lookup"><span data-stu-id="ed591-176">The **Add pinned apps** pane includes only apps that can be pinned to Teams through a policy.</span></span>

#### <a name="im-a-teams-for-education-admin-what-do-i-need-to-know-about-app-setup-policies-in-teams-for-education"></a><span data-ttu-id="ed591-177">私は Teams for Education の管理者です。Teams for Education のアプリセットアップ ポリシーについて知りたい情報</span><span class="sxs-lookup"><span data-stu-id="ed591-177">I'm a Teams for Education admin. What do I need to know about app setup policies in Teams for Education</span></span>

<span data-ttu-id="ed591-178">通話アプリは、Teams for Education では利用できません。</span><span class="sxs-lookup"><span data-stu-id="ed591-178">The Calling app isn't available in Teams for Education.</span></span> <span data-ttu-id="ed591-179">新しいカスタム アプリセットアップ ポリシーを作成すると、通話アプリがアプリの一覧に表示されます。</span><span class="sxs-lookup"><span data-stu-id="ed591-179">When you create a new custom app setup policy, the Calling app is displayed in the list of apps.</span></span> <span data-ttu-id="ed591-180">ただし、アプリは Teams クライアントにピン留めされていないので、Teams for Education ユーザーには Teams の通話アプリは表示されません。</span><span class="sxs-lookup"><span data-stu-id="ed591-180">However, the app isn't pinned to Teams clients and Teams for Education users won't see the Calls app in Teams.</span></span>

#### <a name="how-many-pinned-apps-can-be-added-to-a-policy"></a><span data-ttu-id="ed591-181">ポリシーに追加できるピン留めされたアプリの数</span><span class="sxs-lookup"><span data-stu-id="ed591-181">How many pinned apps can be added to a policy</span></span>

<span data-ttu-id="ed591-182">少なくとも 2 つのアプリを Teams モバイル クライアント (iOS と Android) にピン留めする必要があります。</span><span class="sxs-lookup"><span data-stu-id="ed591-182">A minimum of two apps must be pinned to the Teams mobile clients (iOS and Android).</span></span> <span data-ttu-id="ed591-183">ポリシーのアプリ数が 2 未満の場合、モバイル クライアントはポリシー設定を反映するのではなく、引き続き既存の構成を使用します。</span><span class="sxs-lookup"><span data-stu-id="ed591-183">If a policy has fewer than two apps, the mobile clients won't reflect the policy settings and instead will continue to use the existing configuration.</span></span>

<span data-ttu-id="ed591-184">ポリシーに追加できるピン留めされたアプリの数に制限はありません。</span><span class="sxs-lookup"><span data-stu-id="ed591-184">There's no limit on the number of pinned apps you can add to a policy.</span></span>

#### <a name="how-long-does-it-take-for-policy-changes-to-take-effect"></a><span data-ttu-id="ed591-185">ポリシーの変更が有効にされるのにどれくらい時間がかかるか</span><span class="sxs-lookup"><span data-stu-id="ed591-185">How long does it take for policy changes to take effect</span></span>

<span data-ttu-id="ed591-186">ポリシーを編集既するか割り当てた後、変更が反映されるまでに数時間かかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="ed591-186">After you edit or assign a policy, it can take a few hours for changes to take effect.</span></span>

### <a name="user-experience"></a><span data-ttu-id="ed591-187">ユーザー エクスペリエンス</span><span class="sxs-lookup"><span data-stu-id="ed591-187">User experience</span></span>

#### <a name="how-can-users-see-all-their-pinned-apps-in-teams"></a><span data-ttu-id="ed591-188">ユーザーが Teams でピン留めされたアプリを表示する方法</span><span class="sxs-lookup"><span data-stu-id="ed591-188">How can users see all their pinned apps in Teams</span></span>

<span data-ttu-id="ed591-189">ユーザー用にピン留めされているアプリを表示するには、インストールされているアプリの数と Teams クライアント ウィンドウのサイズによっては、次の操作が必要になる場合があります。</span><span class="sxs-lookup"><span data-stu-id="ed591-189">To view all apps that are pinned for a user, users might have to do the following depending on the number of installed apps and the size of their Teams client window.</span></span>

|<span data-ttu-id="ed591-190">Teams デスクトップ クライアント</span><span class="sxs-lookup"><span data-stu-id="ed591-190">Teams desktop client</span></span> |<span data-ttu-id="ed591-191">Teams モバイル クライアント</span><span class="sxs-lookup"><span data-stu-id="ed591-191">Teams mobile client</span></span> |
|---------|---------|
|<span data-ttu-id="ed591-192">Teams の横にあるアプリ バーで **、[...その他のアプリ**。</span><span class="sxs-lookup"><span data-stu-id="ed591-192">In the app bar on the side of Teams, select **... More apps**.</span></span>| <span data-ttu-id="ed591-193">Teams の下部付近にあるアプリ バーで、上にスワイプします。</span><span class="sxs-lookup"><span data-stu-id="ed591-193">In the app bar near the bottom of Teams, swipe up.</span></span>|
|![Teams デスクトップ クライアントのその他のアプリ](media/app-setup-policies-desktop-more-apps.png)<br>   |![Teams モバイル クライアントのその他のアプリ](media/app-setup-policies-mobile-more-apps.png)  

#### <a name="what-do-i-need-to-know-about-the-teams-mobile-experience"></a><span data-ttu-id="ed591-196">Teams モバイル エクスペリエンスについて知りたい情報</span><span class="sxs-lookup"><span data-stu-id="ed591-196">What do I need to know about the Teams mobile experience</span></span>

<span data-ttu-id="ed591-197">現在、Teams モバイル クライアント (iOS および Android) は、静的タブを含む個人用アプリをサポートしません。</span><span class="sxs-lookup"><span data-stu-id="ed591-197">The Teams mobile clients (iOS and Android) currently don't support personal apps with static tabs.</span></span> <span data-ttu-id="ed591-198">ポリシーに設定されているアプリによっては、Teams デスクトップ クライアントにピン留めされたアプリが Teams モバイル クライアントに表示されない場合があります。</span><span class="sxs-lookup"><span data-stu-id="ed591-198">Depending on the apps set in the policy, apps pinned to the Teams desktop client might not appear in the Teams mobile clients.</span></span> <span data-ttu-id="ed591-199">個人用ボットは、モバイル クライアントのチャットに引き続き表示されます。</span><span class="sxs-lookup"><span data-stu-id="ed591-199">Personal bots will still appear in Chat on mobile clients.</span></span>

<span data-ttu-id="ed591-200">Teams モバイル クライアントを使用すると、ユーザーにはアクティビティ、チャット、Teams などの主要な Teams アプリが表示され、Shifts などの Microsoft の一部のファースト パーティ アプリをピン留めすることができます。</span><span class="sxs-lookup"><span data-stu-id="ed591-200">With the Teams mobile clients, users will see core Teams apps such as Activity, Chat, and Teams, and you can pin some first-party apps from Microsoft, such as Shifts.</span></span>

#### <a name="can-users-change-the-order-of-apps-pinned-through-a-policy"></a><span data-ttu-id="ed591-201">ユーザーがポリシーを使用してピン留めされたアプリの順序を変更できる</span><span class="sxs-lookup"><span data-stu-id="ed591-201">Can users change the order of apps pinned through a policy</span></span>

<span data-ttu-id="ed591-202">[ユーザーのピン留めを許可する] オプションがオンになっている場合、ユーザーは Teams デスクトップクライアントとモバイル クライアントでピン留めされたアプリの **順序を変更** できます。</span><span class="sxs-lookup"><span data-stu-id="ed591-202">Users can change the order of their pinned apps on Teams desktop and mobile clients if the **Allow user pinning** option is turned on.</span></span> <span data-ttu-id="ed591-203">ユーザーは、Teams Web クライアントにピン留めされたアプリの順序を変更することはできません。</span><span class="sxs-lookup"><span data-stu-id="ed591-203">Users can't change the order of their pinned apps on Teams web clients.</span></span>

#### <a name="does-user-pinning-take-precedence"></a><span data-ttu-id="ed591-204">ユーザーのピン留めが優先される</span><span class="sxs-lookup"><span data-stu-id="ed591-204">Does user pinning take precedence</span></span>

<span data-ttu-id="ed591-205">ユーザーに割り当てられたアプリセットアップ ポリシーが変更され、ユーザー アプリのピン留めがブロックされた場合、Teams はアプリ バーにピン留めされたアプリを削除します。</span><span class="sxs-lookup"><span data-stu-id="ed591-205">If the app setup policy assigned to the user is changed to block user app pinning, Teams removes any apps pinned to the app bar.</span></span> <span data-ttu-id="ed591-206">ユーザー アプリのピン留めを許可するポリシーが変更された場合、ユーザーは以前にピン留めしたアプリを再ピン留めする必要があります。</span><span class="sxs-lookup"><span data-stu-id="ed591-206">If the policy is then changed to allow user app pinning, users must repin their previously pinned apps.</span></span>

### <a name="custom-teams-apps"></a><span data-ttu-id="ed591-207">カスタム Teams アプリ</span><span class="sxs-lookup"><span data-stu-id="ed591-207">Custom Teams apps</span></span>

<span data-ttu-id="ed591-208">組織でカスタム Teams アプリを作成し、AppSource またはテナント アプリ カタログに発行しましたが、アプリが Teams のアプリ バーにピン留めされている場合、アプリ アイコンが期待した方法で表示されません。</span><span class="sxs-lookup"><span data-stu-id="ed591-208">My organization built a custom Teams app and published it, either to AppSource or the tenant app catalog, but the app icon isn't displayed as expected when the app is pinned to the app bar in Teams.</span></span> <span data-ttu-id="ed591-209">修正方法</span><span class="sxs-lookup"><span data-stu-id="ed591-209">How do I fix it</span></span>

<span data-ttu-id="ed591-210">アプリを提出する前に、ロゴのガイドラインに従う必要があります。</span><span class="sxs-lookup"><span data-stu-id="ed591-210">Make sure that you follow the logo guidelines before you submit the app.</span></span> <span data-ttu-id="ed591-211">詳細については、「販売者ダッシュボード提出 [のチェックリスト」を参照してください](/microsoftteams/platform/concepts/deploy-and-publish/appsource/prepare/overview)。</span><span class="sxs-lookup"><span data-stu-id="ed591-211">To learn more, see [Checklist for Seller Dashboard submission](/microsoftteams/platform/concepts/deploy-and-publish/appsource/prepare/overview).</span></span>

## <a name="related-topics"></a><span data-ttu-id="ed591-212">関連項目</span><span class="sxs-lookup"><span data-stu-id="ed591-212">Related topics</span></span>

[<span data-ttu-id="ed591-213">Teams でのアプリの管理設定</span><span class="sxs-lookup"><span data-stu-id="ed591-213">Admin settings for apps in Teams</span></span>](admin-settings.md)

[<span data-ttu-id="ed591-214"> Teams でユーザーにポリシーを割り当てる</span><span class="sxs-lookup"><span data-stu-id="ed591-214">Assign policies to your users in Teams</span></span>](assign-policies.md)
