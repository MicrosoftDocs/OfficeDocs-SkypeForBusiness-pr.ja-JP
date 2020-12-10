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
ms.openlocfilehash: a23d9f5196f2d537e00c6e049377f9a7d7488654
ms.sourcegitcommit: 4386f4b89331112e0d54943dc3133791d5dca3fb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "49611601"
---
# <a name="manage-app-setup-policies-in-microsoft-teams"></a><span data-ttu-id="6503b-103">Microsoft Teams のアプリのセットアップ ポリシーを管理する</span><span class="sxs-lookup"><span data-stu-id="6503b-103">Manage app setup policies in Microsoft Teams</span></span>

> [!NOTE]
> <span data-ttu-id="6503b-104">組織全体のアプリ設定を有効にしている場合、 **カスタムアプリとの対話を許可** すると、Microsoft Teams 管理センターにまだアプリセットアップポリシーが表示されないことがあります。</span><span class="sxs-lookup"><span data-stu-id="6503b-104">If you enabled the org-wide app setting, **Allow interaction with custom apps**, you may not see app setup policies yet in the Microsoft Teams admin center.</span></span> <span data-ttu-id="6503b-105">この機能は現在展開中であり、間もなく組織内で利用可能になります。</span><span class="sxs-lookup"><span data-stu-id="6503b-105">It's currently being rolled out and will be available soon in your organization.</span></span>

<span data-ttu-id="6503b-106">管理者は、アプリセットアップポリシーを使って、次のタスクを実行できます。</span><span class="sxs-lookup"><span data-stu-id="6503b-106">As an admin, you can use app setup policies to do the following tasks:</span></span>

- <span data-ttu-id="6503b-107">Teams をカスタマイズして、ユーザーにとって最も重要なアプリを強調表示します。</span><span class="sxs-lookup"><span data-stu-id="6503b-107">Customize Teams to highlight the apps that are most important for your users.</span></span> <span data-ttu-id="6503b-108">ピン留めするアプリを選択し、表示される順序を設定します。</span><span class="sxs-lookup"><span data-stu-id="6503b-108">You choose the apps to pin and set the order that they appear.</span></span> <span data-ttu-id="6503b-109">アプリを固定すると、サードパーティによって構築されたアプリや組織内の開発者によって構築されたアプリなど、組織内のユーザーが必要とするアプリを紹介できます。</span><span class="sxs-lookup"><span data-stu-id="6503b-109">Pinning apps lets you showcase apps that users in your organization need, including apps built by third parties or by developers in your organization.</span></span>
- <span data-ttu-id="6503b-110">ユーザーがアプリを Teams にピン留めできるかどうかを制御します。</span><span class="sxs-lookup"><span data-stu-id="6503b-110">Control whether users can pin apps to Teams.</span></span>
- <span data-ttu-id="6503b-111">[ユーザーの代わりにアプリをインストールする **(プレビュー中)**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="6503b-111">Install apps on behalf of users **(in preview)**.</span></span> <span data-ttu-id="6503b-112">ユーザーが Teams を起動したときに既定でインストールされるアプリを選択します。</span><span class="sxs-lookup"><span data-stu-id="6503b-112">You choose which apps are installed by default for users when they start Teams.</span></span> <span data-ttu-id="6503b-113">ユーザーに割り当てられている [アプリのアクセス許可のポリシー](teams-app-permission-policies.md) で許可されている場合は、ユーザーがアプリ自体をインストールできることを覚えておいてください。</span><span class="sxs-lookup"><span data-stu-id="6503b-113">Keep in mind that users can still install apps themselves if the [app permission policy](teams-app-permission-policies.md) that's assigned to them allows it.</span></span>

<span data-ttu-id="6503b-114">アプリは、Teams のデスクトップクライアントの側のバーであり、Teams のモバイルクライアント (iOS と Android) の下部にある、アプリバーに固定されています。</span><span class="sxs-lookup"><span data-stu-id="6503b-114">Apps are pinned to the app bar, which is the bar on the side of the Teams desktop client and at the bottom of the Teams mobile clients (iOS and Android).</span></span>

|<span data-ttu-id="6503b-115">Teams のデスクトップクライアント</span><span class="sxs-lookup"><span data-stu-id="6503b-115">Teams desktop client</span></span>  |<span data-ttu-id="6503b-116">Teams モバイルクライアント</span><span class="sxs-lookup"><span data-stu-id="6503b-116">Teams mobile client</span></span> |
|---------|---------|
|![Teams のデスクトップクライアント](media/app-setup-policies-desktop-app-bar.png)<br>  |   ![Teams モバイルクライアント](media/mobile-app-ui.png)      |

<span data-ttu-id="6503b-119">アプリバーでプレインストールされているアプリを確認するには、[ユーザー] を選択します **。** チームのデスクトップと web クライアントでその他のアプリを追加し、モバイルクライアントで上にスワイプします。</span><span class="sxs-lookup"><span data-stu-id="6503b-119">To see their pre-installed apps, in the app bar, users select **... More apps** in the Teams desktop and web clients and swipe up in the mobile clients.</span></span>

<span data-ttu-id="6503b-120">アプリセットアップポリシーは、Microsoft Teams 管理センターで管理します。</span><span class="sxs-lookup"><span data-stu-id="6503b-120">You manage app setup policies in the Microsoft Teams admin center.</span></span> <span data-ttu-id="6503b-121">グローバル (組織全体の既定) ポリシーを使用するか、カスタムポリシーを作成して割り当てます。</span><span class="sxs-lookup"><span data-stu-id="6503b-121">Use the global (Org-wide default) policy or create and assign custom policies.</span></span>  <span data-ttu-id="6503b-122">カスタム ポリシーを作成して割り当てていない場合、組織内のユーザーにはグローバル ポリシーが自動的に適用されます。</span><span class="sxs-lookup"><span data-stu-id="6503b-122">Users in your organization will automatically get the global policy unless you create and assign a custom policy.</span></span> <span data-ttu-id="6503b-123">これらのポリシーを管理するには、グローバル管理者または Teams サービス管理者である必要があります。</span><span class="sxs-lookup"><span data-stu-id="6503b-123">You must be a global admin or Teams service admin to manage these policies.</span></span>

<span data-ttu-id="6503b-124">グローバルポリシーの設定を編集して、目的のアプリを含めます。</span><span class="sxs-lookup"><span data-stu-id="6503b-124">You edit the settings in the global policy to include the apps that you want.</span></span> <span data-ttu-id="6503b-125">組織内のさまざまなユーザーグループのチームをカスタマイズするには、1つ以上のカスタムポリシーを作成して割り当てます。</span><span class="sxs-lookup"><span data-stu-id="6503b-125">To customize Teams for different groups of users in your organization, create and assign one or more custom policies.</span></span>

![[アプリセットアップポリシー] ページ](media/app-setup-policies.png)

> [!NOTE]
> <span data-ttu-id="6503b-127">教育機関向けの Teams をお持ちの場合は、現時点ではグローバルポリシーで割り当てアプリが既定で固定されていることを知っておくことが重要です。現在のところ、グローバルポリシーには表示されません。</span><span class="sxs-lookup"><span data-stu-id="6503b-127">If you have Teams for Education, it's important to know that the Assignments app is pinned by default in the global policy even though currently, you don't see it listed in the global policy.</span></span> <span data-ttu-id="6503b-128">チームクライアントの固定されたアプリの一覧で4番目のアプリになります。</span><span class="sxs-lookup"><span data-stu-id="6503b-128">It will be the fourth app in the list of pinned apps on Teams clients.</span></span>

## <a name="create-a-custom-app-setup-policy"></a><span data-ttu-id="6503b-129">カスタムアプリセットアップポリシーを作成する</span><span class="sxs-lookup"><span data-stu-id="6503b-129">Create a custom app setup policy</span></span>

<span data-ttu-id="6503b-130">Microsoft Teams 管理センターを使用して、カスタムポリシーを作成することができます。</span><span class="sxs-lookup"><span data-stu-id="6503b-130">You can use the Microsoft Teams admin center to create a custom policy.</span></span>

1. <span data-ttu-id="6503b-131">Microsoft Teams 管理センターの左のナビゲーションで、[ **Teams アプリ**  >  **セットアップポリシー**] に移動します。</span><span class="sxs-lookup"><span data-stu-id="6503b-131">In the left navigation of the Microsoft Teams admin center, go to **Teams apps** > **Setup policies**.</span></span>

2. <span data-ttu-id="6503b-132">**[追加]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="6503b-132">Select **Add**.</span></span>

   ![[アプリセットアップポリシーの追加] ページ](media/app-setup-policies-add.png)
    
3. <span data-ttu-id="6503b-134">ポリシーの名前と説明を入力します。</span><span class="sxs-lookup"><span data-stu-id="6503b-134">Enter a name and description for the policy.</span></span>

4. <span data-ttu-id="6503b-135">ユーザーがカスタムアプリをチームにアップロードできるかどうかに応じて、 **カスタムアプリのアップロード** を有効または無効にします。</span><span class="sxs-lookup"><span data-stu-id="6503b-135">Turn on or turn off **Upload custom apps**, depending on whether you want to let users upload custom apps to Teams.</span></span> <span data-ttu-id="6503b-136">[組織全体のアプリ設定](manage-apps.md#manage-org-wide-app-settings)で **サードパーティ製のアプリ** が無効になっている場合、この設定を変更することはできません。</span><span class="sxs-lookup"><span data-stu-id="6503b-136">You can't change this setting if **Allow third-party apps** is turned off in [org-wide app settings](manage-apps.md#manage-org-wide-app-settings).</span></span>

5. <span data-ttu-id="6503b-137">ユーザーがアプリをカスタマイズ **できる** ようにするかどうかに応じて、ユーザーの固定を有効または無効にします。</span><span class="sxs-lookup"><span data-stu-id="6503b-137">Turn on or turn off **Allow user pinning**, depending on whether you want to let users personalize their app bar by pinning apps to it.</span></span>

   > [!NOTE]
   > <span data-ttu-id="6503b-138">[ **ユーザーの固定設定を許可する** ] 設定は、Microsoft 365 Government Community Cloud (gcc) 環境 (GCC、gcc High、DoD) の Teams 管理センターで使用できますが、現時点では効果はありません。</span><span class="sxs-lookup"><span data-stu-id="6503b-138">The **Allow user pinning** setting is available in the Teams admin center in Microsoft 365 Government Community Cloud (GCC) environments (GCC, GCC High and DoD), but currently it has no effect.</span></span>

6. <span data-ttu-id="6503b-139">ユーザー用のアプリ **(プレビュー版)** をインストールするには、次のタスクを実行します。</span><span class="sxs-lookup"><span data-stu-id="6503b-139">To install apps for users **(in preview)**, do the following tasks:</span></span>

    1. <span data-ttu-id="6503b-140">[ **インストールされているアプリ**] で、[ **アプリの追加**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="6503b-140">Under **Installed apps**, select **Add apps**.</span></span>
    
    2. <span data-ttu-id="6503b-141">[ **インストールされているアプリの追加** ] ウィンドウで、ユーザーが Teams を起動したときに自動的にインストールするアプリを検索します。</span><span class="sxs-lookup"><span data-stu-id="6503b-141">In the **Add installed apps** pane, search for the apps you want to automatically install for users when they start Teams.</span></span> <span data-ttu-id="6503b-142">アプリのアクセス許可ポリシーによってアプリをフィルター処理することもできます。</span><span class="sxs-lookup"><span data-stu-id="6503b-142">You can also filter apps by app permission policy.</span></span> <span data-ttu-id="6503b-143">アプリの一覧を選択したら、[ **追加**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="6503b-143">When you've chosen your list of apps, select **Add**.</span></span>

       ![[インストールされているアプリの追加] ウィンドウ](media/app-setup-policies-add-installed-apps.png)

7. <span data-ttu-id="6503b-145">アプリを固定するには、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="6503b-145">To pin apps, do the following:</span></span>

    1. <span data-ttu-id="6503b-146">[ **固定** されたアプリ] で、[ **アプリの追加**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="6503b-146">Under **Pinned apps**, select **Add apps**.</span></span>
    
    2. <span data-ttu-id="6503b-147">[固定された **アプリの追加** ] ウィンドウで、追加するアプリを検索し、[ **追加**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="6503b-147">In the **Add pinned apps** pane, search for the apps you want to add, and then select **Add**.</span></span> <span data-ttu-id="6503b-148">アプリのアクセス許可ポリシーによってアプリをフィルター処理することもできます。</span><span class="sxs-lookup"><span data-stu-id="6503b-148">You can also filter apps by app permission policy.</span></span> <span data-ttu-id="6503b-149">ピン留めするアプリのリストを選択したら、[ **追加**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="6503b-149">When you've chosen your list of apps to pin, select **Add**.</span></span>

       ![[固定アプリの追加] ウィンドウ](media/app-setup-policies-add-apps.png)

    3. <span data-ttu-id="6503b-151">Teams で表示する順序でアプリを配置し、[ **保存**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="6503b-151">Arrange the apps in the order that you want them to appear in Teams, and then select **Save**.</span></span>

       ![[固定されたアプリ] セクション](media/app-setup-policies-new-policy-setup.png)

## <a name="edit-an-app-setup-policy"></a><span data-ttu-id="6503b-153">アプリのセットアップポリシーを編集する</span><span class="sxs-lookup"><span data-stu-id="6503b-153">Edit an app setup policy</span></span>

<span data-ttu-id="6503b-154">Microsoft Teams 管理センターを使って、作成するグローバル (組織全体の既定) ポリシーやカスタムポリシーなどのポリシーを編集できます。</span><span class="sxs-lookup"><span data-stu-id="6503b-154">You can use the Microsoft Teams admin center to edit a policy, including the global (Org-wide default) policy and custom policies that you create.</span></span>

1. <span data-ttu-id="6503b-155">Microsoft Teams 管理センターの左のナビゲーションで、[ **Teams アプリ**  >  **セットアップポリシー**] に移動します。</span><span class="sxs-lookup"><span data-stu-id="6503b-155">In the left navigation of the Microsoft Teams admin center, go to **Teams apps** > **Setup policies**.</span></span>

2. <span data-ttu-id="6503b-156">ポリシー名の左側をクリックしてポリシーを選択し、[ **編集**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="6503b-156">Select the policy by clicking to the left of the policy name, and then select **Edit**.</span></span>

3. <span data-ttu-id="6503b-157">ここで、必要な変更を行います。</span><span class="sxs-lookup"><span data-stu-id="6503b-157">From here, make the changes that you want.</span></span>

4. <span data-ttu-id="6503b-158">**[保存]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="6503b-158">Select **Save**.</span></span>

## <a name="assign-a-custom-app-setup-policy-to-users"></a><span data-ttu-id="6503b-159">ユーザーにカスタムアプリセットアップポリシーを割り当てる</span><span class="sxs-lookup"><span data-stu-id="6503b-159">Assign a custom app setup policy to users</span></span>

[!INCLUDE [assign-policy](includes/assign-policy.md)]

## <a name="faq"></a><span data-ttu-id="6503b-160">FAQ</span><span class="sxs-lookup"><span data-stu-id="6503b-160">FAQ</span></span>

### <a name="working-with-app-setup-policies"></a><span data-ttu-id="6503b-161">アプリセットアップポリシーを使用する</span><span class="sxs-lookup"><span data-stu-id="6503b-161">Working with app setup policies</span></span>

#### <a name="what-built-in-app-setup-policies-are-included-in-the-microsoft-teams-admin-center"></a><span data-ttu-id="6503b-162">Microsoft Teams 管理センターには、組み込みのアプリセットアップポリシーが含まれています。</span><span class="sxs-lookup"><span data-stu-id="6503b-162">What built-in app setup policies are included in the Microsoft Teams admin center</span></span>

- <span data-ttu-id="6503b-163">**グローバル (組織全体の既定)**: この既定のポリシーは、別のポリシーを割り当てない限り、組織内のすべてのユーザーに適用されます。</span><span class="sxs-lookup"><span data-stu-id="6503b-163">**Global (Org-wide default)**: This default policy applies to all users in your organization unless you assign another policy.</span></span> <span data-ttu-id="6503b-164">グローバルポリシーを編集して、ユーザーにとって最も重要なアプリをピン留めします。</span><span class="sxs-lookup"><span data-stu-id="6503b-164">Edit the global policy to pin apps that are most important for your users.</span></span>

- <span data-ttu-id="6503b-165">**Firstlineworker**: このポリシーは、firstline worker に対して使用されます。</span><span class="sxs-lookup"><span data-stu-id="6503b-165">**FirstLineWorker**: This policy is for Firstline Workers.</span></span> <span data-ttu-id="6503b-166">組織内の Firstline Worker に割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="6503b-166">You can assign it to Firstline Workers in your organization.</span></span> <span data-ttu-id="6503b-167">作成するカスタムポリシーなど、設定をアクティブにするユーザーにポリシーを割り当てる必要があることを知っておくことが重要です。</span><span class="sxs-lookup"><span data-stu-id="6503b-167">It's important to know that like custom policies that you create, you have to assign the policy to users for the settings to be active.</span></span> <span data-ttu-id="6503b-168">詳細については、この記事の「 [ユーザーにカスタムアプリセットアップポリシーを割り当てる](#assign-a-custom-app-setup-policy-to-users) 」セクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="6503b-168">For more information, go to the [Assign a custom app setup policy to users](#assign-a-custom-app-setup-policy-to-users) section of this article.</span></span>

#### <a name="why-cant-i-find-an-app-in-the-add-pinned-apps-pane"></a><span data-ttu-id="6503b-169">[ピン留めしたアプリの追加] ウィンドウでアプリが見つからないのはなぜですか。</span><span class="sxs-lookup"><span data-stu-id="6503b-169">Why can't I find an app in the Add pinned apps pane</span></span>

<span data-ttu-id="6503b-170">アプリセットアップポリシーを使用して、すべてのアプリを Teams にピン留めすることはできません。</span><span class="sxs-lookup"><span data-stu-id="6503b-170">Not all apps can be pinned to Teams through an app setup policy.</span></span> <span data-ttu-id="6503b-171">一部のアプリでは、この機能がサポートされていない可能性があります。</span><span class="sxs-lookup"><span data-stu-id="6503b-171">Some apps may not support this functionality.</span></span> <span data-ttu-id="6503b-172">ピン留めできるアプリを見つけるには、[ **ピン留め** されたアプリの追加] ウィンドウでアプリを検索します。</span><span class="sxs-lookup"><span data-stu-id="6503b-172">To find apps that can be pinned, search for the app in the **Add pinned apps** pane.</span></span> <span data-ttu-id="6503b-173">個人用のスコープ (静的タブ) とボットを含むタブは、Teams のデスクトップクライアントにピン留めすることができます。これらのアプリは、[固定された **アプリの追加** ] ウィンドウで利用できます。</span><span class="sxs-lookup"><span data-stu-id="6503b-173">Tabs that have a personal scope (static tabs) and bots can be pinned to the Teams desktop client and these apps are available in the **Add pinned apps** pane.</span></span>

<span data-ttu-id="6503b-174">Teams アプリストアには、すべての Teams アプリが一覧表示されていることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="6503b-174">Keep in mind that the Teams app store lists all Teams apps.</span></span> <span data-ttu-id="6503b-175">[ **固定アプリの追加** ] ウィンドウには、ポリシーを通じてチームにピン留めできるアプリのみが含まれています。</span><span class="sxs-lookup"><span data-stu-id="6503b-175">The **Add pinned apps** pane includes only apps that can be pinned to Teams through a policy.</span></span>

#### <a name="im-a-teams-for-education-admin-what-do-i-need-to-know-about-app-setup-policies-in-teams-for-education"></a><span data-ttu-id="6503b-176">私は教育管理者向けのチームです。Teams で教育機関向けアプリセットアップポリシーについて知っておくべきこと</span><span class="sxs-lookup"><span data-stu-id="6503b-176">I'm a Teams for Education admin. What do I need to know about app setup policies in Teams for Education</span></span>

<span data-ttu-id="6503b-177">通話アプリは、教育担当の Teams では利用できません。</span><span class="sxs-lookup"><span data-stu-id="6503b-177">The Calling app isn't available in Teams for Education.</span></span> <span data-ttu-id="6503b-178">新しいカスタムアプリのセットアップポリシーを作成すると、アプリの一覧に呼び出し元のアプリが表示されます。</span><span class="sxs-lookup"><span data-stu-id="6503b-178">When you create a new custom app setup policy, the Calling app is displayed in the list of apps.</span></span> <span data-ttu-id="6503b-179">ただし、アプリは Teams クライアントにはピン留めされておらず、教育機関のチームではチーム内の通話アプリを見ることはできません。</span><span class="sxs-lookup"><span data-stu-id="6503b-179">However, the app isn't pinned to Teams clients and Teams for Education users won't see the Calls app in Teams.</span></span>

#### <a name="how-many-pinned-apps-can-be-added-to-a-policy"></a><span data-ttu-id="6503b-180">固定されたアプリの数をポリシーに追加する方法</span><span class="sxs-lookup"><span data-stu-id="6503b-180">How many pinned apps can be added to a policy</span></span>

<span data-ttu-id="6503b-181">少なくとも2つのアプリが Teams モバイルクライアント (iOS と Android) にピン留めされている必要があります。</span><span class="sxs-lookup"><span data-stu-id="6503b-181">A minimum of two apps must be pinned to the Teams mobile clients (iOS and Android).</span></span> <span data-ttu-id="6503b-182">ポリシーのアプリが2つ未満の場合、モバイルクライアントはポリシーの設定を反映せず、代わりに既存の構成を使い続けます。</span><span class="sxs-lookup"><span data-stu-id="6503b-182">If a policy has fewer than two apps, the mobile clients won't reflect the policy settings and instead will continue to use the existing configuration.</span></span>

<span data-ttu-id="6503b-183">ポリシーに追加できる固定されたアプリの数に制限はありません。</span><span class="sxs-lookup"><span data-stu-id="6503b-183">There's no limit on the number of pinned apps you can add to a policy.</span></span>

#### <a name="how-long-does-it-take-for-policy-changes-to-take-effect"></a><span data-ttu-id="6503b-184">ポリシーの変更が有効になるまでにかかる時間</span><span class="sxs-lookup"><span data-stu-id="6503b-184">How long does it take for policy changes to take effect</span></span>

<span data-ttu-id="6503b-185">ポリシーを編集または割り当てると、変更が有効になるまでに数時間かかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="6503b-185">After you edit or assign a policy, it can take a few hours for changes to take effect.</span></span>

### <a name="user-experience"></a><span data-ttu-id="6503b-186">ユーザー エクスペリエンス</span><span class="sxs-lookup"><span data-stu-id="6503b-186">User experience</span></span>

#### <a name="how-can-users-see-all-their-pinned-apps-in-teams"></a><span data-ttu-id="6503b-187">ユーザーが Teams で固定されたすべてのアプリを表示するにはどうすればよいですか?</span><span class="sxs-lookup"><span data-stu-id="6503b-187">How can users see all their pinned apps in Teams</span></span>

<span data-ttu-id="6503b-188">ユーザーに対して固定されているすべてのアプリを表示するには、インストールされているアプリの数とチームクライアントウィンドウのサイズに応じて、次の操作が必要になることがあります。</span><span class="sxs-lookup"><span data-stu-id="6503b-188">To view all apps that are pinned for a user, users might have to do the following depending on the number of installed apps and the size of their Teams client window.</span></span>

|<span data-ttu-id="6503b-189">Teams のデスクトップクライアント</span><span class="sxs-lookup"><span data-stu-id="6503b-189">Teams desktop client</span></span> |<span data-ttu-id="6503b-190">Teams モバイルクライアント</span><span class="sxs-lookup"><span data-stu-id="6503b-190">Teams mobile client</span></span> |
|---------|---------|
|<span data-ttu-id="6503b-191">Teams のサイドにあるアプリバーで、[...] を選びます。 **その他のアプリ**。</span><span class="sxs-lookup"><span data-stu-id="6503b-191">In the app bar on the side of Teams, select **... More apps**.</span></span>| <span data-ttu-id="6503b-192">チームの下部付近にあるアプリバーで、上にスワイプします。</span><span class="sxs-lookup"><span data-stu-id="6503b-192">In the app bar near the bottom of Teams, swipe up.</span></span>|
|![Teams デスクトップクライアントでのその他のアプリ](media/app-setup-policies-desktop-more-apps.png)<br>   |![Teams モバイルクライアントでのその他のアプリ](media/app-setup-policies-mobile-more-apps.png)  

#### <a name="what-do-i-need-to-know-about-the-teams-mobile-experience"></a><span data-ttu-id="6503b-195">Teams モバイルエクスペリエンスについて知っておくべきこと</span><span class="sxs-lookup"><span data-stu-id="6503b-195">What do I need to know about the Teams mobile experience</span></span>

<span data-ttu-id="6503b-196">現在、Teams モバイルクライアント (iOS と Android) では、静的なタブを持つ個人用アプリはサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="6503b-196">The Teams mobile clients (iOS and Android) currently don't support personal apps with static tabs.</span></span> <span data-ttu-id="6503b-197">ポリシーに設定されているアプリによっては、Teams のデスクトップクライアントに固定されたアプリが Teams のモバイルクライアントに表示されない場合があります。</span><span class="sxs-lookup"><span data-stu-id="6503b-197">Depending on the apps set in the policy, apps pinned to the Teams desktop client might not appear in the Teams mobile clients.</span></span> <span data-ttu-id="6503b-198">携帯電話クライアントのチャットには、個人用のボットが引き続き表示されます。</span><span class="sxs-lookup"><span data-stu-id="6503b-198">Personal bots will still appear in Chat on mobile clients.</span></span>

<span data-ttu-id="6503b-199">Teams のモバイルクライアントでは、ユーザーにはアクティビティ、チャット、Teams などの主要な Teams アプリが表示され、シフトなどの一部のサードパーティ製アプリを Microsoft からピン留めすることができます。</span><span class="sxs-lookup"><span data-stu-id="6503b-199">With the Teams mobile clients, users will see core Teams apps such as Activity, Chat, and Teams, and you can pin some first-party apps from Microsoft, such as Shifts.</span></span>

#### <a name="can-users-change-the-order-of-apps-pinned-through-a-policy"></a><span data-ttu-id="6503b-200">ユーザーがポリシーによって固定されたアプリの順序を変更できる</span><span class="sxs-lookup"><span data-stu-id="6503b-200">Can users change the order of apps pinned through a policy</span></span>

<span data-ttu-id="6503b-201">ユーザーは、[ **ユーザーによる固定** ] オプションがオンになっている場合は、チームのデスクトップとモバイルクライアントで固定されたアプリの順序を変更できます。</span><span class="sxs-lookup"><span data-stu-id="6503b-201">Users can change the order of their pinned apps on Teams desktop and mobile clients if the **Allow user pinning** option is turned on.</span></span> <span data-ttu-id="6503b-202">ユーザーは、Teams web クライアントで固定されたアプリの順序を変更することはできません。</span><span class="sxs-lookup"><span data-stu-id="6503b-202">Users can't change the order of their pinned apps on Teams web clients.</span></span>

#### <a name="does-user-pinning-take-precedence"></a><span data-ttu-id="6503b-203">ユーザーによる固定が優先される</span><span class="sxs-lookup"><span data-stu-id="6503b-203">Does user pinning take precedence</span></span>

<span data-ttu-id="6503b-204">ユーザーに割り当てられているアプリセットアップポリシーが、ユーザーアプリの固定をブロックするように変更されている場合、チームはアプリバーに固定されているすべてのアプリを削除します。</span><span class="sxs-lookup"><span data-stu-id="6503b-204">If the app setup policy assigned to the user is changed to block user app pinning, Teams removes any apps pinned to the app bar.</span></span> <span data-ttu-id="6503b-205">ユーザーアプリの固定を許可するようにポリシーを変更した場合、ユーザーは以前に固定されたアプリを再ピンする必要があります。</span><span class="sxs-lookup"><span data-stu-id="6503b-205">If the policy is then changed to allow user app pinning, users must re-pin their previously pinned apps.</span></span>

### <a name="custom-teams-apps"></a><span data-ttu-id="6503b-206">カスタム Teams アプリ</span><span class="sxs-lookup"><span data-stu-id="6503b-206">Custom Teams apps</span></span>

#### <a name="my-organization-built-a-custom-teams-app-and-published-it-either-to-appsource-or-the-tenant-app-catalog-but-the-app-icon-isnt-displayed-as-expected-when-the-app-is-pinned-to-the-app-bar-in-teams-how-do-i-fix-it"></a><span data-ttu-id="6503b-207">組織では、カスタム Teams アプリを構築し、AppSource またはテナントのアプリカタログに公開していますが、アプリが Teams のアプリバーにピン留めされている場合、アプリのアイコンは期待どおりに表示されません。</span><span class="sxs-lookup"><span data-stu-id="6503b-207">My organization built a custom Teams app and published it, either to AppSource or the tenant app catalog, but the app icon isn't displayed as expected when the app is pinned to the app bar in Teams.</span></span> <span data-ttu-id="6503b-208">問題を解決するにはどうすればよいですか?</span><span class="sxs-lookup"><span data-stu-id="6503b-208">How do I fix it</span></span>

<span data-ttu-id="6503b-209">アプリを申請する前に、ロゴガイドラインに従っていることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="6503b-209">Make sure that you follow the logo guidelines before you submit the app.</span></span> <span data-ttu-id="6503b-210">詳細については、「 [販売業者ダッシュボードの申請のチェックリスト](/microsoftteams/platform/concepts/deploy-and-publish/appsource/prepare/overview)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6503b-210">To learn more, see [Checklist for Seller Dashboard submission](/microsoftteams/platform/concepts/deploy-and-publish/appsource/prepare/overview).</span></span>

## <a name="related-topics"></a><span data-ttu-id="6503b-211">関連項目</span><span class="sxs-lookup"><span data-stu-id="6503b-211">Related topics</span></span>

[<span data-ttu-id="6503b-212">Teams でのアプリの管理設定</span><span class="sxs-lookup"><span data-stu-id="6503b-212">Admin settings for apps in Teams</span></span>](admin-settings.md)

[<span data-ttu-id="6503b-213">チームのユーザーにポリシーを割り当てる</span><span class="sxs-lookup"><span data-stu-id="6503b-213">Assign policies to your users in Teams</span></span>](assign-policies.md)
