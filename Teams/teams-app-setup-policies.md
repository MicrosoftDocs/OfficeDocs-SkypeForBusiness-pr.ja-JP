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
ms.openlocfilehash: ef4ff711aa385c062ca6d507363b4d1a1a5d88e4
ms.sourcegitcommit: 6a4bd155e73ab21944dd5f4f0c776e4cd0508147
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/24/2020
ms.locfileid: "44868570"
---
# <a name="manage-app-setup-policies-in-microsoft-teams"></a><span data-ttu-id="6583c-103">Microsoft Teams のアプリのセットアップ ポリシーを管理する</span><span class="sxs-lookup"><span data-stu-id="6583c-103">Manage app setup policies in Microsoft Teams</span></span>

> [!NOTE]
> <span data-ttu-id="6583c-104">組織全体のアプリ設定を有効にしている場合、**カスタムアプリとの対話を許可**すると、Microsoft Teams 管理センターにまだアプリセットアップポリシーが表示されないことがあります。</span><span class="sxs-lookup"><span data-stu-id="6583c-104">If you enabled the org-wide app setting, **Allow interaction with custom apps**, you may not see app setup policies yet in the Microsoft Teams admin center.</span></span> <span data-ttu-id="6583c-105">この機能は現在展開中であり、間もなく組織内で利用可能になります。</span><span class="sxs-lookup"><span data-stu-id="6583c-105">It's currently being rolled out and will be available soon in your organization.</span></span>

<span data-ttu-id="6583c-106">管理者は、アプリ セットアップポリシーを使用して、次の操作を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="6583c-106">As an admin, you can use app setup policies to do the following:</span></span>

- <span data-ttu-id="6583c-107">Teams をカスタマイズして、ユーザーにとって最も重要なアプリを強調表示します。</span><span class="sxs-lookup"><span data-stu-id="6583c-107">Customize Teams to highlight the apps that are most important for your users.</span></span> <span data-ttu-id="6583c-108">ピン留めするアプリを選択し、表示される順序を設定します。</span><span class="sxs-lookup"><span data-stu-id="6583c-108">You choose the apps to pin and set the order that they appear.</span></span> <span data-ttu-id="6583c-109">アプリをピン留めすると、サード パーティ製のアプリや組織内の開発者が作成したアプリなど、組織内のユーザーが必要とするアプリを提示できます。</span><span class="sxs-lookup"><span data-stu-id="6583c-109">Pinning apps lets you showcase apps that users in your organization need, including those built by third parties or by developers in your organization.</span></span>
- <span data-ttu-id="6583c-110">ユーザーがアプリを Teams にピン留めできるかどうかを制御します。</span><span class="sxs-lookup"><span data-stu-id="6583c-110">Control whether users can pin apps to Teams.</span></span>
- <span data-ttu-id="6583c-111">[ユーザーの代わりにアプリをインストールする **(プレビュー中)**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="6583c-111">Install apps on behalf of users **(in preview)**.</span></span> <span data-ttu-id="6583c-112">ユーザーが Teams を起動したときに既定でインストールされるアプリを選択します。</span><span class="sxs-lookup"><span data-stu-id="6583c-112">You choose which apps are installed by default for users when they start Teams.</span></span> <span data-ttu-id="6583c-113">ユーザーに割り当てられている[アプリのアクセス許可のポリシー](teams-app-permission-policies.md)で許可されている場合は、ユーザーがアプリ自体をインストールできることを覚えておいてください。</span><span class="sxs-lookup"><span data-stu-id="6583c-113">Keep in mind that users can still install apps themselves if the [app permission policy](teams-app-permission-policies.md) that's assigned to them allows it.</span></span>

<span data-ttu-id="6583c-114">アプリは、アプリ バーにピン留めされます。</span><span class="sxs-lookup"><span data-stu-id="6583c-114">Apps are pinned to the app bar.</span></span> <span data-ttu-id="6583c-115">このバーは、Teams デスクトップ クライアントの横側および Teams モバイル クライアント (iOS および Android) の下側に表示されます。</span><span class="sxs-lookup"><span data-stu-id="6583c-115">This is the bar on the side of the Teams desktop client and at the bottom of the Teams mobile clients (iOS and Android).</span></span>

|<span data-ttu-id="6583c-116">Teams のデスクトップクライアント</span><span class="sxs-lookup"><span data-stu-id="6583c-116">Teams desktop client</span></span>  |<span data-ttu-id="6583c-117">Teams モバイルクライアント</span><span class="sxs-lookup"><span data-stu-id="6583c-117">Teams mobile client</span></span> |
|---------|---------|
|![Teams のデスクトップクライアントを示すスクリーンショット](media/app-setup-policies-desktop-app-bar.png)<br>  |   ![Teams モバイルクライアントを示すスクリーンショット](media/app-setup-policies-mobile-app-bar.png)      |

<span data-ttu-id="6583c-120">アプリバーでプレインストールされているアプリを確認するには、ユーザーが [...] をクリックします **。** チームのデスクトップと web クライアントでその他のアプリを追加し、モバイルクライアントで上にスワイプします。</span><span class="sxs-lookup"><span data-stu-id="6583c-120">To see their pre-installed apps, in the app bar, users click **... More apps** in the Teams desktop and web clients and swipe up in the mobile clients.</span></span>

<span data-ttu-id="6583c-121">アプリセットアップポリシーは、Microsoft Teams 管理センターで管理します。</span><span class="sxs-lookup"><span data-stu-id="6583c-121">You manage app setup policies in the Microsoft Teams admin center.</span></span> <span data-ttu-id="6583c-122">グローバル (組織全体の既定) ポリシーを使用することも、カスタム ポリシーを作成してユーザーに割り当てることもできます。</span><span class="sxs-lookup"><span data-stu-id="6583c-122">You can use the global (Org-wide default) policy or create custom policies and assign them to users.</span></span> <span data-ttu-id="6583c-123">カスタム ポリシーを作成して割り当てていない場合、組織内のユーザーにはグローバル ポリシーが自動的に適用されます。</span><span class="sxs-lookup"><span data-stu-id="6583c-123">Users in your organization will automatically get the global policy unless you create and assign a custom policy.</span></span> <span data-ttu-id="6583c-124">これらのポリシーを管理するには、グローバル管理者または Teams サービス管理者である必要があります。</span><span class="sxs-lookup"><span data-stu-id="6583c-124">You must be a global admin or Teams service admin to manage these policies.</span></span>

<span data-ttu-id="6583c-125">グローバルポリシーの設定を編集して、目的のアプリを含めることができます。</span><span class="sxs-lookup"><span data-stu-id="6583c-125">You can edit the settings in the global policy to include the apps that you want.</span></span> <span data-ttu-id="6583c-126">組織内のさまざまなユーザーグループのチームをカスタマイズする場合は、1つ以上のカスタムポリシーを作成して割り当てます。</span><span class="sxs-lookup"><span data-stu-id="6583c-126">If you want to customize Teams for different groups of users in your organization, create and assign one or more custom policies.</span></span> <span data-ttu-id="6583c-127">ユーザーにカスタム ポリシーが割り当てられると、そのポリシーがユーザーに適用されます。</span><span class="sxs-lookup"><span data-stu-id="6583c-127">If a user is assigned a custom policy, that policy applies to the user.</span></span> <span data-ttu-id="6583c-128">ユーザーにカスタム ポリシーが割り当てられない場合は、グローバル ポリシーがユーザーに適用されます。</span><span class="sxs-lookup"><span data-stu-id="6583c-128">If a user isn't assigned a custom policy, the global policy applies to the user.</span></span>

![[アプリセットアップポリシー] ページを示すスクリーンショット](media/app-setup-policies.png)

> [!NOTE]
> <span data-ttu-id="6583c-130">教育機関向けの Teams をお持ちの場合は、現時点ではグローバルポリシーで割り当てアプリが既定で固定されていることを知っておくことが重要です。現在のところ、グローバルポリシーには表示されません。</span><span class="sxs-lookup"><span data-stu-id="6583c-130">If you have Teams for Education, it's important to know that the Assignments app is pinned by default in the global policy even though currently, you don't see it listed in the global policy.</span></span> <span data-ttu-id="6583c-131">チームクライアントの固定されたアプリの一覧で4番目のアプリになります。</span><span class="sxs-lookup"><span data-stu-id="6583c-131">It will be the fourth app in the list of pinned apps on Teams clients.</span></span>

## <a name="create-a-custom-app-setup-policy"></a><span data-ttu-id="6583c-132">カスタムアプリセットアップポリシーを作成する</span><span class="sxs-lookup"><span data-stu-id="6583c-132">Create a custom app setup policy</span></span>

<span data-ttu-id="6583c-133">Microsoft Teams 管理センターを使用して、カスタムポリシーを作成することができます。</span><span class="sxs-lookup"><span data-stu-id="6583c-133">You can use the Microsoft Teams admin center to create a custom policy.</span></span>

1. <span data-ttu-id="6583c-134">Microsoft Teams 管理センターの左のナビゲーションで、[ **Teams アプリ**  >  **セットアップポリシー**] に移動します。</span><span class="sxs-lookup"><span data-stu-id="6583c-134">In the left navigation of the Microsoft Teams admin center, go to **Teams apps** > **Setup policies**.</span></span>
2. <span data-ttu-id="6583c-135">**[追加]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6583c-135">Click **Add**.</span></span>
    <span data-ttu-id="6583c-136">![[アプリセットアップポリシーの追加] ページを示すスクリーンショット](media/app-setup-policies-add.png)</span><span class="sxs-lookup"><span data-stu-id="6583c-136">![Screenshot showing the Add app setup policies page](media/app-setup-policies-add.png)</span></span>
3. <span data-ttu-id="6583c-137">ポリシーの名前と説明を入力します。</span><span class="sxs-lookup"><span data-stu-id="6583c-137">Enter a name and description for the policy.</span></span>
4. <span data-ttu-id="6583c-138">ユーザーがカスタムアプリをチームにアップロードできるかどうかに応じて、**カスタムアプリのアップロード**を有効または無効にします。</span><span class="sxs-lookup"><span data-stu-id="6583c-138">Turn on or turn off **Upload custom apps**, depending on whether you want to let users upload custom apps to Teams.</span></span> <span data-ttu-id="6583c-139">[組織全体のアプリ設定](manage-apps.md#manage-org-wide-app-settings)で**サードパーティ製のアプリ**が無効になっている場合、この設定を変更することはできません。</span><span class="sxs-lookup"><span data-stu-id="6583c-139">You won't be able to change this setting if **Allow third-party apps** is turned off in [org-wide app settings](manage-apps.md#manage-org-wide-app-settings).</span></span>
5. <span data-ttu-id="6583c-140">ユーザーがアプリをカスタマイズ**できる**ようにするかどうかに応じて、ユーザーの固定を有効または無効にします。</span><span class="sxs-lookup"><span data-stu-id="6583c-140">Turn on or turn off **Allow user pinning**, depending on whether you want to let users personalize their app bar by pinning apps to it.</span></span>
6. <span data-ttu-id="6583c-141">ユーザー用のアプリ **(プレビュー版)** をインストールするには、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="6583c-141">To install apps for users **(in preview)**, do the following:</span></span>

    1. <span data-ttu-id="6583c-142">[**インストールされているアプリ**] で、[**アプリの追加**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6583c-142">Under **Installed apps**, click **Add apps**.</span></span>
    2. <span data-ttu-id="6583c-143">[**インストールされているアプリの追加**] ウィンドウで、ユーザーが Teams を起動したときに自動的にインストールするアプリを検索します。</span><span class="sxs-lookup"><span data-stu-id="6583c-143">In the **Add installed apps** pane, search for the apps you want to automatically install for users when they start Teams.</span></span> <span data-ttu-id="6583c-144">アプリのアクセス許可ポリシーによってアプリをフィルター処理することもできます。</span><span class="sxs-lookup"><span data-stu-id="6583c-144">You can also filter apps by app permission policy.</span></span> <span data-ttu-id="6583c-145">アプリの一覧を選択したら、[**追加**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6583c-145">When you've chosen your list of apps, click **Add**.</span></span>

        ![[インストールされているアプリの追加] ウィンドウを示すスクリーンショット](media/app-setup-policies-add-installed-apps.png)

7. <span data-ttu-id="6583c-147">アプリを固定するには、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="6583c-147">To pin apps, do the following:</span></span>

    1. <span data-ttu-id="6583c-148">[**固定**されたアプリ] で、[**アプリの追加**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6583c-148">Under **Pinned apps**, click **Add apps**.</span></span>
    2. <span data-ttu-id="6583c-149">[固定された**アプリの追加**] ウィンドウで、追加するアプリを検索し、[**追加**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6583c-149">In the **Add pinned apps** pane, search for the apps you want to add, and then click **Add**.</span></span> <span data-ttu-id="6583c-150">アプリのアクセス許可ポリシーによってアプリをフィルター処理することもできます。</span><span class="sxs-lookup"><span data-stu-id="6583c-150">You can also filter apps by app permission policy.</span></span> <span data-ttu-id="6583c-151">ピン留めするアプリのリストを選んだら、[**追加**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6583c-151">When you've chosen your list of apps to pin, click **Add**.</span></span>

         ![[固定アプリの追加] ウィンドウを示すスクリーンショット](media/app-setup-policies-add-apps.png)

    3. <span data-ttu-id="6583c-153">Teams で表示する順序でアプリを配置し、[**保存**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6583c-153">Arrange the apps in the order that you want them to appear in Teams, and then click **Save**.</span></span>

        ![ピン留めされたアプリのセクションを示すスクリーンショット](media/app-setup-policies-new-policy-setup.png)

## <a name="edit-an-app-setup-policy"></a><span data-ttu-id="6583c-155">アプリのセットアップポリシーを編集する</span><span class="sxs-lookup"><span data-stu-id="6583c-155">Edit an app setup policy</span></span>

<span data-ttu-id="6583c-156">Microsoft Teams 管理センターを使って、作成するグローバル (組織全体の既定) ポリシーやカスタムポリシーなどのポリシーを編集できます。</span><span class="sxs-lookup"><span data-stu-id="6583c-156">You can use the Microsoft Teams admin center to edit a policy, including the global (Org-wide default) policy and custom policies that you create.</span></span>

1. <span data-ttu-id="6583c-157">Microsoft Teams 管理センターの左のナビゲーションで、[ **Teams アプリ**  >  **セットアップポリシー**] に移動します。</span><span class="sxs-lookup"><span data-stu-id="6583c-157">In the left navigation of the Microsoft Teams admin center, go to **Teams apps** > **Setup policies**.</span></span>
2. <span data-ttu-id="6583c-158">ポリシー名の左側をクリックしてポリシーを選び、**[編集]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6583c-158">Select the policy by clicking to the left of the policy name, and then click **Edit**.</span></span>
3. <span data-ttu-id="6583c-159">ここで、必要な変更を行います。</span><span class="sxs-lookup"><span data-stu-id="6583c-159">From here, make the changes that you want.</span></span>
4. <span data-ttu-id="6583c-160">**[保存]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6583c-160">Click **Save**.</span></span>

## <a name="assign-a-custom-app-setup-policy-to-users"></a><span data-ttu-id="6583c-161">ユーザーにカスタムアプリセットアップポリシーを割り当てる</span><span class="sxs-lookup"><span data-stu-id="6583c-161">Assign a custom app setup policy to users</span></span>

<span data-ttu-id="6583c-162">Microsoft Teams 管理センターを使用して、カスタムポリシーを個々のユーザーに割り当てるか、Skype for Business PowerShell モジュールを使用して、セキュリティグループ、配布グループなど、グループ内のユーザーにカスタムポリシーを割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="6583c-162">You can use the Microsoft Teams admin center to assign a custom policy to individual users or the Skype for Business PowerShell module  to assign a custom policy to users in a group, such as a security group or distribution group.</span></span>

### <a name="assign-a-custom-app-setup-policy-to-users"></a><span data-ttu-id="6583c-163">ユーザーにカスタムアプリセットアップポリシーを割り当てる</span><span class="sxs-lookup"><span data-stu-id="6583c-163">Assign a custom app setup policy to users</span></span>

<span data-ttu-id="6583c-164">1人のユーザーにポリシーを割り当てるには、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="6583c-164">To assign a policy to one user:</span></span>

1. <span data-ttu-id="6583c-165">Microsoft Teams 管理センターの左側のナビゲーションで、**[ユーザー]** に移動してユーザーをクリックします。</span><span class="sxs-lookup"><span data-stu-id="6583c-165">In the left navigation of the Microsoft Teams admin center, go to **Users**, and then click the user.</span></span>
2. <span data-ttu-id="6583c-166">ユーザー名の左側をクリックしてユーザーを選択し、[**編集を設定する**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6583c-166">Select the user by clicking to the left of the user name, and then click **Edit settings**.</span></span>
3. <span data-ttu-id="6583c-167">[**アプリセットアップポリシー**] で、割り当てるアプリセットアップポリシーを選択し、[**適用**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6583c-167">Under **App setup policy**, select the app setup policy you want to assign, and then click **Apply**.</span></span>

<span data-ttu-id="6583c-168">複数のユーザーに同時にポリシーを割り当てるには、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="6583c-168">To assign a policy to multiple users at a time:</span></span>

1. <span data-ttu-id="6583c-169">Microsoft Teams 管理センターの左側のナビゲーションで、**[ユーザー]** に移動し、ユーザーを検索するか、表示にフィルターを適用してユーザーを表示します。</span><span class="sxs-lookup"><span data-stu-id="6583c-169">In the left navigation of the Microsoft Teams admin center, go to **Users**, and then search for the users or filter the view to show the users you want.</span></span>
2. <span data-ttu-id="6583c-170">[**&#x2713;** (チェックマーク)] の列からユーザーを選択します。</span><span class="sxs-lookup"><span data-stu-id="6583c-170">In the **&#x2713;** (check mark) column, select the users.</span></span> <span data-ttu-id="6583c-171">すべてのユーザーを選択するには、表の上部にある [&#x2713; (チェックマーク)] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6583c-171">To select all users, click the &#x2713; (check mark) at the top of the table.</span></span>
3. <span data-ttu-id="6583c-172">[**設定の編集**] をクリックし、必要な変更を行い、[**適用**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6583c-172">Click **Edit settings**, make the changes that you want, and then click **Apply**.</span></span>  

<span data-ttu-id="6583c-173">または、次の操作も実行できます。</span><span class="sxs-lookup"><span data-stu-id="6583c-173">Or, you can also do the following:</span></span>

1. <span data-ttu-id="6583c-174">Microsoft Teams 管理センターの左のナビゲーションで、[ **Teams アプリ**  >  **セットアップポリシー**] に移動します。</span><span class="sxs-lookup"><span data-stu-id="6583c-174">In the left navigation of the Microsoft Teams admin center, go to **Teams apps** > **Setup policies**.</span></span>
2. <span data-ttu-id="6583c-175">ポリシー名の左側をクリックしてポリシーを選びます。</span><span class="sxs-lookup"><span data-stu-id="6583c-175">Select the policy by clicking to the left of the policy name.</span></span>
3. <span data-ttu-id="6583c-176">[**ユーザーを管理**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="6583c-176">Select **Manage users**.</span></span>
4. <span data-ttu-id="6583c-177">[**ユーザーを管理**] ウィンドウで、表示名またはユーザー名でユーザーを検索し、名前を選択して [**追加**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="6583c-177">In the **Manage users** pane, search for the user by display name or by user name, select the name, and then select **Add**.</span></span> <span data-ttu-id="6583c-178">追加するユーザーごとに、この手順を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="6583c-178">Repeat this step for each user that you want to add.</span></span>
5. <span data-ttu-id="6583c-179">ユーザーの追加が完了したら、[**保存**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="6583c-179">After you finish adding users, select **Save**.</span></span>

### <a name="assign-a-custom-app-setup-policy-to-users-in-a-group"></a><span data-ttu-id="6583c-180">カスタムアプリセットアップポリシーをグループ内のユーザーに割り当てる</span><span class="sxs-lookup"><span data-stu-id="6583c-180">Assign a custom app setup policy to users in a group</span></span>

<span data-ttu-id="6583c-181">カスタムアプリセットアップポリシーは、既に指定した複数のユーザーに割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="6583c-181">You may want to assign a custom app setup policy to multiple users that you've already identified.</span></span> <span data-ttu-id="6583c-182">たとえば、セキュリティ グループのすべてのユーザーにポリシーを割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="6583c-182">For example, you may want to assign a policy to all users in a security group.</span></span> <span data-ttu-id="6583c-183">これを行うには、Graph 用 Azure Active Directory PowerShell モジュールと Skype for Business PowerShell モジュールに接続します。</span><span class="sxs-lookup"><span data-stu-id="6583c-183">You can do this by connecting to the Azure Active Directory PowerShell for Graph module and the Skype for Business PowerShell module.</span></span> <span data-ttu-id="6583c-184">PowerShell を使用して Teams を管理する方法の詳細については、「[Teams での PowerShell の概要](teams-powershell-overview.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6583c-184">For more information about using PowerShell to manage Teams, see [Teams PowerShell Overview](teams-powershell-overview.md).</span></span>

<span data-ttu-id="6583c-185">この例では、"人事アプリセットアップポリシー" というカスタムアプリセットアップポリシーを、Contoso 製薬 HR プロジェクトグループ内のすべてのユーザーに割り当てています。</span><span class="sxs-lookup"><span data-stu-id="6583c-185">In this example, we assign a custom app setup policy called HR App Setup Policy to all users in the Contoso Pharmaceuticals HR Project group.</span></span>  

> [!NOTE]
> <span data-ttu-id="6583c-186">まず、 [「単一の Windows PowerShell ウィンドウですべての Microsoft 365 または Office 365 サービスに接続](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-all-office-365-services-in-a-single-windows-powershell-window)する」の手順に従って、Graph モジュール用の Azure Active Directory Powershell と Skype For business powershell モジュールに接続していることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="6583c-186">Make sure you first connect to the Azure Active Directory PowerShell for Graph module and Skype for Business PowerShell module by following the steps in [Connect to all Microsoft 365 or Office 365 services in a single Windows PowerShell window](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-all-office-365-services-in-a-single-windows-powershell-window).</span></span>

<span data-ttu-id="6583c-187">特定のグループの GroupObjectId を取得します。</span><span class="sxs-lookup"><span data-stu-id="6583c-187">Get the GroupObjectId of the particular group.</span></span>
```PowerShell
$group = Get-AzureADGroup -SearchString "Contoso Pharmaceuticals HR Project"
```
<span data-ttu-id="6583c-188">指定したグループのメンバーを取得します。</span><span class="sxs-lookup"><span data-stu-id="6583c-188">Get the members of the specified group.</span></span>
```PowerShell
$members = Get-AzureADGroupMember -ObjectId $group.ObjectId -All $true | Where-Object {$_.ObjectType -eq "User"}
```
<span data-ttu-id="6583c-189">グループ内のすべてのユーザーを特定のアプリセットアップポリシーに割り当てます。</span><span class="sxs-lookup"><span data-stu-id="6583c-189">Assign all users in the group to a particular app setup policy.</span></span> <span data-ttu-id="6583c-190">この例では、HR アプリのセットアップポリシーです。</span><span class="sxs-lookup"><span data-stu-id="6583c-190">In this example, it's HR App Setup Policy.</span></span>
```PowerShell
$members | ForEach-Object { Grant-CsTeamsAppSetupPolicy -PolicyName "HR App Setup Policy" -Identity $_.UserPrincipalName}
``` 
<span data-ttu-id="6583c-191">グループ内のメンバー数によっては、このコマンドの実行に数分かかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="6583c-191">Depending on the number of members in the group, this command may take several minutes to execute.</span></span>

## <a name="faq"></a><span data-ttu-id="6583c-192">FAQ</span><span class="sxs-lookup"><span data-stu-id="6583c-192">FAQ</span></span>

### <a name="working-with-app-setup-policies"></a><span data-ttu-id="6583c-193">アプリセットアップポリシーを使用する</span><span class="sxs-lookup"><span data-stu-id="6583c-193">Working with app setup policies</span></span>

#### <a name="what-built-in-app-setup-policies-are-included-in-the-microsoft-teams-admin-center"></a><span data-ttu-id="6583c-194">Microsoft Teams 管理センターには、どのような組み込みのアプリセットアップポリシーが含まれていますか?</span><span class="sxs-lookup"><span data-stu-id="6583c-194">What built-in app setup policies are included in the Microsoft Teams admin center?</span></span>

- <span data-ttu-id="6583c-195">**グローバル (組織全体の既定)**: この既定のポリシーは、別のポリシーを割り当てない限り、組織内のすべてのユーザーに適用されます。</span><span class="sxs-lookup"><span data-stu-id="6583c-195">**Global (Org-wide default)**: This default policy applies to all users in your organization unless you assign another policy.</span></span> <span data-ttu-id="6583c-196">グローバルポリシーを編集して、ユーザーにとって最も重要なアプリをピン留めします。</span><span class="sxs-lookup"><span data-stu-id="6583c-196">Edit the global policy to pin apps that are most important for your users.</span></span>
- <span data-ttu-id="6583c-197">**Firstlineworker**: このポリシーは、firstline worker に対して使用されます。</span><span class="sxs-lookup"><span data-stu-id="6583c-197">**FirstLineWorker**: This policy is for Firstline Workers.</span></span> <span data-ttu-id="6583c-198">組織内の Firstline Worker に割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="6583c-198">You can assign it to Firstline Workers in your organization.</span></span> <span data-ttu-id="6583c-199">作成するカスタムポリシーなど、設定をアクティブにするユーザーにポリシーを割り当てる必要があることを知っておくことが重要です。</span><span class="sxs-lookup"><span data-stu-id="6583c-199">It's important to know that like custom policies that you create, you have to assign the policy to users for the settings to be active.</span></span> <span data-ttu-id="6583c-200">詳細については、この記事の「[ユーザーにカスタムアプリセットアップポリシーを割り当てる](#assign-a-custom-app-setup-policy-to-users)」セクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="6583c-200">For more information, go to the [Assign a custom app setup policy to users](#assign-a-custom-app-setup-policy-to-users) section of this article.</span></span>

#### <a name="why-cant-i-find-an-app-in-the-add-pinned-apps-pane"></a><span data-ttu-id="6583c-201">[ピン留めしたアプリの追加] ウィンドウでアプリが見つからないのはなぜですか?</span><span class="sxs-lookup"><span data-stu-id="6583c-201">Why can't I find an app in the Add pinned apps pane?</span></span>

<span data-ttu-id="6583c-202">アプリセットアップポリシーを使用して、すべてのアプリを Teams にピン留めすることはできません。</span><span class="sxs-lookup"><span data-stu-id="6583c-202">Not all apps can be pinned to Teams through an app setup policy.</span></span> <span data-ttu-id="6583c-203">一部のアプリでは、この機能がサポートされていない可能性があります。</span><span class="sxs-lookup"><span data-stu-id="6583c-203">Some apps may not support this functionality.</span></span> <span data-ttu-id="6583c-204">ピン留めできるアプリを見つけるには、[**ピン留め**されたアプリの追加] ウィンドウでアプリを検索します。</span><span class="sxs-lookup"><span data-stu-id="6583c-204">To find apps that can be pinned, search for the app in the **Add pinned apps** pane.</span></span> <span data-ttu-id="6583c-205">個人用のスコープ (静的タブ) とボットを含むタブは、Teams のデスクトップクライアントにピン留めすることができます。これらのアプリは、[固定された**アプリの追加**] ウィンドウで利用できます。</span><span class="sxs-lookup"><span data-stu-id="6583c-205">Tabs that have a personal scope (static tabs) and bots can be pinned to the Teams desktop client and these apps are available in the **Add pinned apps** pane.</span></span>

<span data-ttu-id="6583c-206">Teams app store にはすべての Teams アプリが一覧表示されます。 [**ピン留め**されたアプリの追加] ウィンドウには、ポリシーを通じてチームにピン留めできるアプリのみが含まれていることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="6583c-206">Keep in mind that the Teams app store lists all Teams apps whereas the **Add pinned apps** pane includes only apps that can be pinned to Teams through a policy.</span></span> 

#### <a name="im-a-teams-for-education-admin-what-do-i-need-to-know-about-app-setup-policies-in-teams-for-education"></a><span data-ttu-id="6583c-207">私は教育管理者向けのチームです。教育機関向け Teams のアプリセットアップポリシーについて知っておくべきこと</span><span class="sxs-lookup"><span data-stu-id="6583c-207">I'm a Teams for Education admin. What do I need to know about app setup policies in Teams for Education?</span></span>

<span data-ttu-id="6583c-208">通話アプリは、教育担当の Teams では利用できません。</span><span class="sxs-lookup"><span data-stu-id="6583c-208">The Calling app isn't available in Teams for Education.</span></span> <span data-ttu-id="6583c-209">新しいカスタムアプリのセットアップポリシーを作成すると、アプリの一覧に呼び出し元のアプリが表示されます。</span><span class="sxs-lookup"><span data-stu-id="6583c-209">When you create a new custom app setup policy, the Calling app is displayed in the list of apps.</span></span> <span data-ttu-id="6583c-210">ただし、アプリは Teams クライアントにはピン留めされておらず、教育機関のチームではチーム内の通話アプリを見ることはできません。</span><span class="sxs-lookup"><span data-stu-id="6583c-210">However, the app isn't pinned to Teams clients and Teams for Education users won't see the Calls app in Teams.</span></span>

#### <a name="how-many-pinned-apps-can-be-added-to-a-policy"></a><span data-ttu-id="6583c-211">固定されたアプリの数をポリシーに追加できますか?</span><span class="sxs-lookup"><span data-stu-id="6583c-211">How many pinned apps can be added to a policy?</span></span>

<span data-ttu-id="6583c-212">少なくとも2つのアプリが Teams モバイルクライアント (iOS と Android) にピン留めされている必要があります。</span><span class="sxs-lookup"><span data-stu-id="6583c-212">A minimum of two apps must be pinned to the Teams mobile clients (iOS and Android).</span></span> <span data-ttu-id="6583c-213">ポリシーのアプリが2つ未満の場合、モバイルクライアントはポリシーの設定を反映せず、代わりに既存の構成を使い続けます。</span><span class="sxs-lookup"><span data-stu-id="6583c-213">If a policy has less than two apps, the mobile clients won't reflect the policy settings and instead will continue to use the existing configuration.</span></span>

<span data-ttu-id="6583c-214">ポリシーに追加できる固定されたアプリの数に制限はありません。</span><span class="sxs-lookup"><span data-stu-id="6583c-214">There's no limit on the number of pinned apps you can add to a policy.</span></span>

#### <a name="how-long-does-it-take-for-policy-changes-to-take-effect"></a><span data-ttu-id="6583c-215">ポリシーの変更が有効になるまでにはどのくらいの時間がかかりますか?</span><span class="sxs-lookup"><span data-stu-id="6583c-215">How long does it take for policy changes to take effect?</span></span>

<span data-ttu-id="6583c-216">グローバルポリシーを編集するか、ポリシーを割り当てると、変更が有効になるまでに数時間かかることがあります。</span><span class="sxs-lookup"><span data-stu-id="6583c-216">After you edit the global policy or assign a policy, it can take a few hours for changes to take effect.</span></span>

### <a name="user-experience"></a><span data-ttu-id="6583c-217">ユーザー エクスペリエンス</span><span class="sxs-lookup"><span data-stu-id="6583c-217">User experience</span></span>

#### <a name="how-can-users-see-all-their-pinned-apps-in-teams"></a><span data-ttu-id="6583c-218">ユーザーが Teams で固定されたすべてのアプリを表示するにはどうすればよいですか?</span><span class="sxs-lookup"><span data-stu-id="6583c-218">How can users see all their pinned apps in Teams?</span></span>

<span data-ttu-id="6583c-219">ユーザーに対して固定されているすべてのアプリを表示するには、インストールされているアプリの数とチームクライアントウィンドウのサイズに応じて、次の操作が必要になることがあります。</span><span class="sxs-lookup"><span data-stu-id="6583c-219">To view all apps that are pinned for a user, users may have to do the following depending on the number of installed apps and the size of their Teams client window.</span></span>

|<span data-ttu-id="6583c-220">Teams のデスクトップクライアント</span><span class="sxs-lookup"><span data-stu-id="6583c-220">Teams desktop client</span></span> |<span data-ttu-id="6583c-221">Teams モバイルクライアント</span><span class="sxs-lookup"><span data-stu-id="6583c-221">Teams mobile client</span></span> |
|---------|---------|
|<span data-ttu-id="6583c-222">Teams のサイドにあるアプリバーで、[...] をクリックします。 **その他のアプリ**。</span><span class="sxs-lookup"><span data-stu-id="6583c-222">In the app bar on the side of Teams, click **... More apps**.</span></span>| <span data-ttu-id="6583c-223">チームの下部付近にあるアプリバーで、上にスワイプします。</span><span class="sxs-lookup"><span data-stu-id="6583c-223">In the app bar near the bottom of Teams, swipe up.</span></span>|
|![Teams デスクトップクライアントでその他のアプリを示すスクリーンショット](media/app-setup-policies-desktop-more-apps.png)<br>   |![Teams モバイルクライアントでその他のアプリを示すスクリーンショット](media/app-setup-policies-mobile-more-apps.png)  

#### <a name="what-do-i-need-to-know-about-the-teams-mobile-experience"></a><span data-ttu-id="6583c-226">Teams のモバイルエクスペリエンスについて知っておくべきこと</span><span class="sxs-lookup"><span data-stu-id="6583c-226">What do I need to know about the Teams mobile experience?</span></span>

<span data-ttu-id="6583c-227">現在、Teams モバイルクライアント (iOS と Android) では、静的なタブを持つ個人用アプリはサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="6583c-227">The Teams mobile clients (iOS and Android) currently don't support personal apps with static tabs.</span></span> <span data-ttu-id="6583c-228">ポリシーに設定されているアプリによっては、Teams のデスクトップクライアントに固定されたアプリが Teams のモバイルクライアントに表示されない場合があります。</span><span class="sxs-lookup"><span data-stu-id="6583c-228">Depending on the apps set in the policy, apps pinned to the Teams desktop client might not appear in the Teams mobile clients.</span></span> <span data-ttu-id="6583c-229">携帯電話クライアントのチャットには、個人用のボットが引き続き表示されます。</span><span class="sxs-lookup"><span data-stu-id="6583c-229">Personal bots will still appear in Chat on mobile clients.</span></span>

<span data-ttu-id="6583c-230">Teams のモバイルクライアントでは、ユーザーにはアクティビティ、チャット、Teams などの主要な Teams アプリが表示され、シフトなどの一部のサードパーティ製アプリを Microsoft からピン留めすることができます。</span><span class="sxs-lookup"><span data-stu-id="6583c-230">With the Teams mobile clients, users will see core Teams apps such as Activity, Chat, and Teams, and you can pin some first-party apps from Microsoft, such as Shifts.</span></span>

#### <a name="can-users-change-the-order-of-apps-pinned-through-a-policy"></a><span data-ttu-id="6583c-231">ユーザーはポリシーによって固定されたアプリの順序を変更できますか。</span><span class="sxs-lookup"><span data-stu-id="6583c-231">Can users change the order of apps pinned through a policy?</span></span>

<span data-ttu-id="6583c-232">ユーザーは、[**ユーザーによる固定**] オプションがオンになっている場合は、チームのデスクトップとモバイルクライアントで固定されたアプリの順序を変更できます。</span><span class="sxs-lookup"><span data-stu-id="6583c-232">Users can change the order of their pinned apps on Teams desktop and mobile clients if the **Allow user pinning** option is turned on.</span></span> <span data-ttu-id="6583c-233">ユーザーは、Teams web クライアントで固定されたアプリの順序を変更することはできません。</span><span class="sxs-lookup"><span data-stu-id="6583c-233">Users can't change the order of their pinned apps on Teams web clients.</span></span>

#### <a name="does-user-pinning-take-precedence"></a><span data-ttu-id="6583c-234">ユーザーのピン留めは優先されますか?</span><span class="sxs-lookup"><span data-stu-id="6583c-234">Does user pinning take precedence?</span></span>

<span data-ttu-id="6583c-235">ユーザーに割り当てられているアプリセットアップポリシーが、ユーザーアプリの固定をブロックするように変更されている場合、チームはアプリバーに固定されているすべてのアプリを削除します。</span><span class="sxs-lookup"><span data-stu-id="6583c-235">If the app setup policy assigned to the user is changed to block user app pinning, Teams removes any apps pinned to the app bar.</span></span> <span data-ttu-id="6583c-236">ユーザーアプリの固定を許可するようにポリシーを変更した場合、ユーザーは以前に固定されたアプリを再ピンする必要があります。</span><span class="sxs-lookup"><span data-stu-id="6583c-236">If the policy is then changed to allow user app pinning, users must re-pin their previously pinned apps.</span></span>

### <a name="custom-teams-apps"></a><span data-ttu-id="6583c-237">カスタム Teams アプリ</span><span class="sxs-lookup"><span data-stu-id="6583c-237">Custom Teams apps</span></span>

#### <a name="my-organization-built-a-custom-teams-app-and-published-it-either-to-appsource-or-the-tenant-app-catalog-but-the-app-icon-isnt-displayed-as-expected-when-the-app-is-pinned-to-the-app-bar-in-teams-how-do-i-fix-it"></a><span data-ttu-id="6583c-238">組織では、カスタム Teams アプリを構築し、AppSource またはテナントのアプリカタログに公開していますが、アプリが Teams のアプリバーにピン留めされている場合、アプリのアイコンは期待どおりに表示されません。</span><span class="sxs-lookup"><span data-stu-id="6583c-238">My organization built a custom Teams app and published it, either to AppSource or the tenant app catalog, but the app icon isn't displayed as expected when the app is pinned to the app bar in Teams.</span></span> <span data-ttu-id="6583c-239">問題を解決するにはどうすればよいですか?</span><span class="sxs-lookup"><span data-stu-id="6583c-239">How do I fix it?</span></span>

<span data-ttu-id="6583c-240">アプリを申請する前に、ロゴガイドラインに従っていることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="6583c-240">Make sure that you follow the logo guidelines before you submit the app.</span></span> <span data-ttu-id="6583c-241">詳細については、「[販売業者ダッシュボードの申請のチェックリスト](/microsoftteams/platform/concepts/deploy-and-publish/appsource/prepare/overview)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6583c-241">To learn more, see [Checklist for Seller Dashboard submission](/microsoftteams/platform/concepts/deploy-and-publish/appsource/prepare/overview).</span></span> 

## <a name="related-topics"></a><span data-ttu-id="6583c-242">関連項目</span><span class="sxs-lookup"><span data-stu-id="6583c-242">Related topics</span></span>

- [<span data-ttu-id="6583c-243">Teams でのアプリの管理設定</span><span class="sxs-lookup"><span data-stu-id="6583c-243">Admin settings for apps in Teams</span></span>](admin-settings.md)
- [<span data-ttu-id="6583c-244">チームのユーザーにポリシーを割り当てる</span><span class="sxs-lookup"><span data-stu-id="6583c-244">Assign policies to your users in Teams</span></span>](assign-policies.md)
