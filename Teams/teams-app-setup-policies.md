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
ms.openlocfilehash: ffc2f15cdbef49daf36e09ca9676925ebb1ac99e
ms.sourcegitcommit: 27bfa015413bc7742bca4ea227e0324da0c740d7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/08/2021
ms.locfileid: "50145924"
---
# <a name="manage-app-setup-policies-in-microsoft-teams"></a><span data-ttu-id="3f047-103">Microsoft Teams のアプリのセットアップ ポリシーを管理する</span><span class="sxs-lookup"><span data-stu-id="3f047-103">Manage app setup policies in Microsoft Teams</span></span>

<span data-ttu-id="3f047-104">管理者は、アプリセットアップ ポリシーを使用して、次のタスクを実行できます。</span><span class="sxs-lookup"><span data-stu-id="3f047-104">As an admin, you can use app setup policies to do the following tasks:</span></span>

- <span data-ttu-id="3f047-105">Teams をカスタマイズして、ユーザーにとって最も重要なアプリを強調表示します。</span><span class="sxs-lookup"><span data-stu-id="3f047-105">Customize Teams to highlight the apps that are most important for your users.</span></span> <span data-ttu-id="3f047-106">ピン留めするアプリを選び、表示される順序を設定します。</span><span class="sxs-lookup"><span data-stu-id="3f047-106">You choose the apps to pin and set the order that they appear.</span></span> <span data-ttu-id="3f047-107">アプリをピン留めすると、サードパーティや組織内の開発者が作成したアプリなど、組織内のユーザーが必要とするアプリを紹介できます。</span><span class="sxs-lookup"><span data-stu-id="3f047-107">Pinning apps lets you showcase apps that users in your organization need, including apps built by third parties or by developers in your organization.</span></span>
- <span data-ttu-id="3f047-108">ユーザーがアプリを Teams にピン留めできるかどうかを制御します。</span><span class="sxs-lookup"><span data-stu-id="3f047-108">Control whether users can pin apps to Teams.</span></span>
- <span data-ttu-id="3f047-109">ユーザーに代わって (プレビューで) アプリ **をインストールします**。</span><span class="sxs-lookup"><span data-stu-id="3f047-109">Install apps on behalf of users **(in preview)**.</span></span> <span data-ttu-id="3f047-110">ユーザーが Teams を起動するときに、既定でインストールするアプリを選択します。</span><span class="sxs-lookup"><span data-stu-id="3f047-110">You choose which apps are installed by default for users when they start Teams.</span></span> <span data-ttu-id="3f047-111">ユーザーに割り当てられているアプリのアクセス許可ポリシーで許可[](teams-app-permission-policies.md)されている場合でも、ユーザーはアプリを自分でインストールできます。</span><span class="sxs-lookup"><span data-stu-id="3f047-111">Keep in mind that users can still install apps themselves if the [app permission policy](teams-app-permission-policies.md) that's assigned to them allows it.</span></span>

<span data-ttu-id="3f047-112">アプリは、Teams デスクトップ クライアントの横と Teams モバイル クライアント (iOS および Android) の下部にあるアプリ バーにピン留めされます。</span><span class="sxs-lookup"><span data-stu-id="3f047-112">Apps are pinned to the app bar, which is the bar on the side of the Teams desktop client and at the bottom of the Teams mobile clients (iOS and Android).</span></span>

|<span data-ttu-id="3f047-113">Teams デスクトップ クライアント</span><span class="sxs-lookup"><span data-stu-id="3f047-113">Teams desktop client</span></span>  |<span data-ttu-id="3f047-114">Teams モバイル クライアント</span><span class="sxs-lookup"><span data-stu-id="3f047-114">Teams mobile client</span></span> |
|---------|---------|
|![Teams デスクトップ クライアント](media/app-setup-policies-desktop-app-bar.png)<br>  |   ![Teams モバイル クライアント](media/mobile-app-ui.png)      |

<span data-ttu-id="3f047-117">プレインストールされているアプリを表示するには、アプリ バーで **[...Teams デスクトップおよび** Web クライアント内のその他のアプリと、モバイル クライアントで上にスワイプします。</span><span class="sxs-lookup"><span data-stu-id="3f047-117">To see their pre-installed apps, in the app bar, users select **... More apps** in the Teams desktop and web clients and swipe up in the mobile clients.</span></span>

<span data-ttu-id="3f047-118">Microsoft Teams 管理センターでアプリセットアップ ポリシーを管理します。</span><span class="sxs-lookup"><span data-stu-id="3f047-118">You manage app setup policies in the Microsoft Teams admin center.</span></span> <span data-ttu-id="3f047-119">グローバル (組織全体の既定) ポリシーを使用するか、カスタム ポリシーを作成して割り当てる。</span><span class="sxs-lookup"><span data-stu-id="3f047-119">Use the global (Org-wide default) policy or create and assign custom policies.</span></span>  <span data-ttu-id="3f047-120">カスタム ポリシーを作成して割り当てていない場合、組織内のユーザーにはグローバル ポリシーが自動的に適用されます。</span><span class="sxs-lookup"><span data-stu-id="3f047-120">Users in your organization will automatically get the global policy unless you create and assign a custom policy.</span></span> <span data-ttu-id="3f047-121">これらのポリシーを管理するには、グローバル管理者または Teams サービス管理者である必要があります。</span><span class="sxs-lookup"><span data-stu-id="3f047-121">You must be a global admin or Teams service admin to manage these policies.</span></span>

<span data-ttu-id="3f047-122">グローバル ポリシーの設定を編集して、必要なアプリを含める。</span><span class="sxs-lookup"><span data-stu-id="3f047-122">You edit the settings in the global policy to include the apps that you want.</span></span> <span data-ttu-id="3f047-123">組織内のユーザーのグループごとに Teams をカスタマイズするには、1 つ以上のカスタム ポリシーを作成して割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="3f047-123">To customize Teams for different groups of users in your organization, create and assign one or more custom policies.</span></span>

![[アプリセットアップ ポリシー] ページ](media/app-setup-policies.png)

> [!NOTE]
> <span data-ttu-id="3f047-125">Teams for Education をお持ちである場合は、割り当てアプリが既定でグローバル ポリシーにピン留めされているにもかかわらず、グローバル ポリシーに表示されません。</span><span class="sxs-lookup"><span data-stu-id="3f047-125">If you have Teams for Education, it's important to know that the Assignments app is pinned by default in the global policy even though currently, you don't see it listed in the global policy.</span></span> <span data-ttu-id="3f047-126">これは、Teams クライアントにピン留めされたアプリの一覧で 4 番目のアプリになります。</span><span class="sxs-lookup"><span data-stu-id="3f047-126">It will be the fourth app in the list of pinned apps on Teams clients.</span></span>

## <a name="create-a-custom-app-setup-policy"></a><span data-ttu-id="3f047-127">カスタム アプリセットアップ ポリシーを作成する</span><span class="sxs-lookup"><span data-stu-id="3f047-127">Create a custom app setup policy</span></span>

<span data-ttu-id="3f047-128">Microsoft Teams 管理センターを使用して、カスタム ポリシーを作成できます。</span><span class="sxs-lookup"><span data-stu-id="3f047-128">You can use the Microsoft Teams admin center to create a custom policy.</span></span>

1. <span data-ttu-id="3f047-129">Microsoft Teams 管理センターの左側のナビゲーションで **、Teams アプリのセットアップ** ポリシー  >  **に移動します**。</span><span class="sxs-lookup"><span data-stu-id="3f047-129">In the left navigation of the Microsoft Teams admin center, go to **Teams apps** > **Setup policies**.</span></span>

2. <span data-ttu-id="3f047-130">**[追加]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="3f047-130">Select **Add**.</span></span>

   ![[アプリセットアップ ポリシーの追加] ページ](media/app-setup-policies-add.png)
    
3. <span data-ttu-id="3f047-132">ポリシーの名前と説明を入力します。</span><span class="sxs-lookup"><span data-stu-id="3f047-132">Enter a name and description for the policy.</span></span>

4. <span data-ttu-id="3f047-133">ユーザーがカスタム アプリ **を** Teams にアップロードできるかどうかに応じて、カスタム アプリのアップロードをオンまたはオフにします。</span><span class="sxs-lookup"><span data-stu-id="3f047-133">Turn on or turn off **Upload custom apps**, depending on whether you want to let users upload custom apps to Teams.</span></span> <span data-ttu-id="3f047-134">組織全体のアプリ設定で [サード パーティ製アプリを許可する] がオフになっている場合、この設定[を変更できません](manage-apps.md#manage-org-wide-app-settings)。</span><span class="sxs-lookup"><span data-stu-id="3f047-134">You can't change this setting if **Allow third-party apps** is turned off in [org-wide app settings](manage-apps.md#manage-org-wide-app-settings).</span></span>

5. <span data-ttu-id="3f047-135">アプリをピン留めしてユーザーがアプリ バーをカスタマイズできるかどうかに応じて、ユーザーのピン留めを許可する機能のオンとオフを切り替えます。</span><span class="sxs-lookup"><span data-stu-id="3f047-135">Turn on or turn off **Allow user pinning**, depending on whether you want to let users personalize their app bar by pinning apps to it.</span></span>

   > [!NOTE]
   > <span data-ttu-id="3f047-136">[ユーザーのピン留めを許可する] 設定は、Microsoft 365 Government Community Cloud (GCC) 環境 (GCC、GCC High、DoD) の Teams 管理センターで使用できますが、現在は有効な機能はありません。</span><span class="sxs-lookup"><span data-stu-id="3f047-136">The **Allow user pinning** setting is available in the Teams admin center in Microsoft 365 Government Community Cloud (GCC) environments (GCC, GCC High and DoD), but currently it has no effect.</span></span>

6. <span data-ttu-id="3f047-137">(プレビューで) ユーザー用のアプリをインストール **するには**、次のタスクを実行します。</span><span class="sxs-lookup"><span data-stu-id="3f047-137">To install apps for users **(in preview)**, do the following tasks:</span></span>

    1. <span data-ttu-id="3f047-138">[インストール **されているアプリ] で、[** アプリの **追加] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="3f047-138">Under **Installed apps**, select **Add apps**.</span></span>
    
    2. <span data-ttu-id="3f047-139">[インストール済 **みアプリの追加** ] ウィンドウで、ユーザーが Teams を起動するときに自動的にインストールするアプリを検索します。</span><span class="sxs-lookup"><span data-stu-id="3f047-139">In the **Add installed apps** pane, search for the apps you want to automatically install for users when they start Teams.</span></span> <span data-ttu-id="3f047-140">アプリのアクセス許可ポリシーでアプリをフィルター処理することもできます。</span><span class="sxs-lookup"><span data-stu-id="3f047-140">You can also filter apps by app permission policy.</span></span> <span data-ttu-id="3f047-141">アプリの一覧を選択したら、[追加] を選択 **します**。</span><span class="sxs-lookup"><span data-stu-id="3f047-141">When you've chosen your list of apps, select **Add**.</span></span>

       ![[インストールされているアプリの追加] ウィンドウ](media/app-setup-policies-add-installed-apps.png)

7. <span data-ttu-id="3f047-143">アプリをピン留めするには、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="3f047-143">To pin apps, do the following:</span></span>

    1. <span data-ttu-id="3f047-144">[ピン **留めされたアプリ] で**[アプリの **追加] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="3f047-144">Under **Pinned apps**, select **Add apps**.</span></span>
    
    2. <span data-ttu-id="3f047-145">[ピン留 **めされたアプリの追加]** ウィンドウで、追加するアプリを検索し、[追加] を選択 **します**。</span><span class="sxs-lookup"><span data-stu-id="3f047-145">In the **Add pinned apps** pane, search for the apps you want to add, and then select **Add**.</span></span> <span data-ttu-id="3f047-146">アプリのアクセス許可ポリシーでアプリをフィルター処理することもできます。</span><span class="sxs-lookup"><span data-stu-id="3f047-146">You can also filter apps by app permission policy.</span></span> <span data-ttu-id="3f047-147">ピン留めするアプリの一覧を選択したら、[追加] を選択 **します**。</span><span class="sxs-lookup"><span data-stu-id="3f047-147">When you've chosen your list of apps to pin, select **Add**.</span></span>

       ![[ピン留めされたアプリの追加] ウィンドウ](media/app-setup-policies-add-apps.png)

    3. <span data-ttu-id="3f047-149">アプリを Teams に表示する順序で配置し、[保存] を選択 **します**。</span><span class="sxs-lookup"><span data-stu-id="3f047-149">Arrange the apps in the order that you want them to appear in Teams, and then select **Save**.</span></span>

       ![[ピン留めされたアプリ] セクション](media/app-setup-policies-new-policy-setup.png)

## <a name="edit-an-app-setup-policy"></a><span data-ttu-id="3f047-151">アプリセットアップ ポリシーを編集する</span><span class="sxs-lookup"><span data-stu-id="3f047-151">Edit an app setup policy</span></span>

<span data-ttu-id="3f047-152">Microsoft Teams 管理センターを使用して、作成したグローバル (組織全体の既定) ポリシーやカスタム ポリシーなどのポリシーを編集できます。</span><span class="sxs-lookup"><span data-stu-id="3f047-152">You can use the Microsoft Teams admin center to edit a policy, including the global (Org-wide default) policy and custom policies that you create.</span></span>

1. <span data-ttu-id="3f047-153">Microsoft Teams 管理センターの左側のナビゲーションで **、Teams アプリのセットアップ** ポリシー  >  **に移動します**。</span><span class="sxs-lookup"><span data-stu-id="3f047-153">In the left navigation of the Microsoft Teams admin center, go to **Teams apps** > **Setup policies**.</span></span>

2. <span data-ttu-id="3f047-154">ポリシー名の左側をクリックしてポリシーを選び、**[編集]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="3f047-154">Select the policy by clicking to the left of the policy name, and then select **Edit**.</span></span>

3. <span data-ttu-id="3f047-155">ここで、希望する変更を行います。</span><span class="sxs-lookup"><span data-stu-id="3f047-155">From here, make the changes that you want.</span></span>

4. <span data-ttu-id="3f047-156">**[保存]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="3f047-156">Select **Save**.</span></span>

## <a name="assign-a-custom-app-setup-policy-to-users"></a><span data-ttu-id="3f047-157">カスタム アプリセットアップ ポリシーをユーザーに割り当てる</span><span class="sxs-lookup"><span data-stu-id="3f047-157">Assign a custom app setup policy to users</span></span>

[!INCLUDE [assign-policy](includes/assign-policy.md)]

## <a name="faq"></a><span data-ttu-id="3f047-158">よくあるご質問 (FAQ)</span><span class="sxs-lookup"><span data-stu-id="3f047-158">FAQ</span></span>

### <a name="working-with-app-setup-policies"></a><span data-ttu-id="3f047-159">アプリセットアップ ポリシーを使用する</span><span class="sxs-lookup"><span data-stu-id="3f047-159">Working with app setup policies</span></span>

#### <a name="what-built-in-app-setup-policies-are-included-in-the-microsoft-teams-admin-center"></a><span data-ttu-id="3f047-160">Microsoft Teams 管理センターに含まれる組み込みのアプリセットアップ ポリシー</span><span class="sxs-lookup"><span data-stu-id="3f047-160">What built-in app setup policies are included in the Microsoft Teams admin center</span></span>

- <span data-ttu-id="3f047-161">**グローバル (組織全体の既定)**: この既定のポリシーは、別のポリシーを割り当てない限り、組織内のすべてのユーザーに適用されます。</span><span class="sxs-lookup"><span data-stu-id="3f047-161">**Global (Org-wide default)**: This default policy applies to all users in your organization unless you assign another policy.</span></span> <span data-ttu-id="3f047-162">グローバル ポリシーを編集して、ユーザーにとって最も重要なアプリをピン留めします。</span><span class="sxs-lookup"><span data-stu-id="3f047-162">Edit the global policy to pin apps that are most important for your users.</span></span>

- <span data-ttu-id="3f047-163">**FrontlineWorker:** このポリシーは、Frontline Worker 向けです。</span><span class="sxs-lookup"><span data-stu-id="3f047-163">**FrontlineWorker**: This policy is for Frontline Workers.</span></span> <span data-ttu-id="3f047-164">組織内の Frontline Worker に割り当てできます。</span><span class="sxs-lookup"><span data-stu-id="3f047-164">You can assign it to Frontline Workers in your organization.</span></span> <span data-ttu-id="3f047-165">作成するカスタム ポリシーと同様に、設定をアクティブにするにはユーザーにポリシーを割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="3f047-165">It's important to know that like custom policies that you create, you have to assign the policy to users for the settings to be active.</span></span> <span data-ttu-id="3f047-166">詳細については、この記事の「カスタム アプリセットアップ [ポリシーを](#assign-a-custom-app-setup-policy-to-users) ユーザーに割り当てる」セクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="3f047-166">For more information, go to the [Assign a custom app setup policy to users](#assign-a-custom-app-setup-policy-to-users) section of this article.</span></span>

#### <a name="why-cant-i-find-an-app-in-the-add-pinned-apps-pane"></a><span data-ttu-id="3f047-167">[ピン留めされたアプリの追加] ウィンドウでアプリが見当たらない理由</span><span class="sxs-lookup"><span data-stu-id="3f047-167">Why can't I find an app in the Add pinned apps pane</span></span>

<span data-ttu-id="3f047-168">アプリセットアップ ポリシーを使用して、すべてのアプリを Teams にピン留めできない。</span><span class="sxs-lookup"><span data-stu-id="3f047-168">Not all apps can be pinned to Teams through an app setup policy.</span></span> <span data-ttu-id="3f047-169">一部のアプリでは、この機能がサポートされていない場合があります。</span><span class="sxs-lookup"><span data-stu-id="3f047-169">Some apps may not support this functionality.</span></span> <span data-ttu-id="3f047-170">ピン留めできるアプリを見つけるには、[ピン留めされたアプリの追加] ウィンドウ **でアプリを検索** します。</span><span class="sxs-lookup"><span data-stu-id="3f047-170">To find apps that can be pinned, search for the app in the **Add pinned apps** pane.</span></span> <span data-ttu-id="3f047-171">個人用の範囲 (静的なタブ) とボットを含むタブは、Teams デスクトップ クライアントにピン留めできます。これらのアプリは、[ピン留めされたアプリの追加] ウィンドウ **で使用** できます。</span><span class="sxs-lookup"><span data-stu-id="3f047-171">Tabs that have a personal scope (static tabs) and bots can be pinned to the Teams desktop client and these apps are available in the **Add pinned apps** pane.</span></span>

<span data-ttu-id="3f047-172">Teams アプリ ストアには、すべての Teams アプリが一覧表示されます。</span><span class="sxs-lookup"><span data-stu-id="3f047-172">Keep in mind that the Teams app store lists all Teams apps.</span></span> <span data-ttu-id="3f047-173">[ **ピン留めされたアプリの追加** ] ウィンドウには、ポリシーを通じて Teams にピン留めできるアプリだけが含まれます。</span><span class="sxs-lookup"><span data-stu-id="3f047-173">The **Add pinned apps** pane includes only apps that can be pinned to Teams through a policy.</span></span>

#### <a name="im-a-teams-for-education-admin-what-do-i-need-to-know-about-app-setup-policies-in-teams-for-education"></a><span data-ttu-id="3f047-174">私は Teams for Education の管理者です。Teams for Education のアプリセットアップ ポリシーについて知りたい情報</span><span class="sxs-lookup"><span data-stu-id="3f047-174">I'm a Teams for Education admin. What do I need to know about app setup policies in Teams for Education</span></span>

<span data-ttu-id="3f047-175">通話アプリは、Teams for Education では利用できません。</span><span class="sxs-lookup"><span data-stu-id="3f047-175">The Calling app isn't available in Teams for Education.</span></span> <span data-ttu-id="3f047-176">新しいカスタム アプリセットアップ ポリシーを作成すると、通話アプリがアプリの一覧に表示されます。</span><span class="sxs-lookup"><span data-stu-id="3f047-176">When you create a new custom app setup policy, the Calling app is displayed in the list of apps.</span></span> <span data-ttu-id="3f047-177">ただし、アプリは Teams クライアントにピン留めされていないので、Teams for Education ユーザーには Teams の通話アプリは表示されません。</span><span class="sxs-lookup"><span data-stu-id="3f047-177">However, the app isn't pinned to Teams clients and Teams for Education users won't see the Calls app in Teams.</span></span>

#### <a name="how-many-pinned-apps-can-be-added-to-a-policy"></a><span data-ttu-id="3f047-178">ポリシーに追加できるピン留めされたアプリの数</span><span class="sxs-lookup"><span data-stu-id="3f047-178">How many pinned apps can be added to a policy</span></span>

<span data-ttu-id="3f047-179">少なくとも 2 つのアプリを Teams モバイル クライアント (iOS と Android) にピン留めする必要があります。</span><span class="sxs-lookup"><span data-stu-id="3f047-179">A minimum of two apps must be pinned to the Teams mobile clients (iOS and Android).</span></span> <span data-ttu-id="3f047-180">ポリシーのアプリ数が 2 未満の場合、モバイル クライアントはポリシー設定を反映するのではなく、引き続き既存の構成を使用します。</span><span class="sxs-lookup"><span data-stu-id="3f047-180">If a policy has fewer than two apps, the mobile clients won't reflect the policy settings and instead will continue to use the existing configuration.</span></span>

<span data-ttu-id="3f047-181">ポリシーに追加できるピン留めされたアプリの数に制限はありません。</span><span class="sxs-lookup"><span data-stu-id="3f047-181">There's no limit on the number of pinned apps you can add to a policy.</span></span>

#### <a name="how-long-does-it-take-for-policy-changes-to-take-effect"></a><span data-ttu-id="3f047-182">ポリシーの変更が有効にされるのにどれくらい時間がかかるか</span><span class="sxs-lookup"><span data-stu-id="3f047-182">How long does it take for policy changes to take effect</span></span>

<span data-ttu-id="3f047-183">ポリシーを編集既するか割り当てた後、変更が反映されるまでに数時間かかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="3f047-183">After you edit or assign a policy, it can take a few hours for changes to take effect.</span></span>

### <a name="user-experience"></a><span data-ttu-id="3f047-184">ユーザー エクスペリエンス</span><span class="sxs-lookup"><span data-stu-id="3f047-184">User experience</span></span>

#### <a name="how-can-users-see-all-their-pinned-apps-in-teams"></a><span data-ttu-id="3f047-185">ユーザーが Teams でピン留めされたアプリを表示する方法</span><span class="sxs-lookup"><span data-stu-id="3f047-185">How can users see all their pinned apps in Teams</span></span>

<span data-ttu-id="3f047-186">ユーザー用にピン留めされているアプリを表示するには、インストールされているアプリの数と Teams クライアント ウィンドウのサイズによっては、次の操作が必要になる場合があります。</span><span class="sxs-lookup"><span data-stu-id="3f047-186">To view all apps that are pinned for a user, users might have to do the following depending on the number of installed apps and the size of their Teams client window.</span></span>

|<span data-ttu-id="3f047-187">Teams デスクトップ クライアント</span><span class="sxs-lookup"><span data-stu-id="3f047-187">Teams desktop client</span></span> |<span data-ttu-id="3f047-188">Teams モバイル クライアント</span><span class="sxs-lookup"><span data-stu-id="3f047-188">Teams mobile client</span></span> |
|---------|---------|
|<span data-ttu-id="3f047-189">Teams の横にあるアプリ バーで **、[...その他のアプリ**。</span><span class="sxs-lookup"><span data-stu-id="3f047-189">In the app bar on the side of Teams, select **... More apps**.</span></span>| <span data-ttu-id="3f047-190">Teams の下部付近にあるアプリ バーで、上にスワイプします。</span><span class="sxs-lookup"><span data-stu-id="3f047-190">In the app bar near the bottom of Teams, swipe up.</span></span>|
|![Teams デスクトップ クライアントのその他のアプリ](media/app-setup-policies-desktop-more-apps.png)<br>   |![Teams モバイル クライアントのその他のアプリ](media/app-setup-policies-mobile-more-apps.png)  

#### <a name="what-do-i-need-to-know-about-the-teams-mobile-experience"></a><span data-ttu-id="3f047-193">Teams モバイル エクスペリエンスについて知りたい情報</span><span class="sxs-lookup"><span data-stu-id="3f047-193">What do I need to know about the Teams mobile experience</span></span>

<span data-ttu-id="3f047-194">現在、Teams モバイル クライアント (iOS および Android) は、静的タブを含む個人用アプリをサポートしません。</span><span class="sxs-lookup"><span data-stu-id="3f047-194">The Teams mobile clients (iOS and Android) currently don't support personal apps with static tabs.</span></span> <span data-ttu-id="3f047-195">ポリシーに設定されているアプリによっては、Teams デスクトップ クライアントにピン留めされたアプリが Teams モバイル クライアントに表示されない場合があります。</span><span class="sxs-lookup"><span data-stu-id="3f047-195">Depending on the apps set in the policy, apps pinned to the Teams desktop client might not appear in the Teams mobile clients.</span></span> <span data-ttu-id="3f047-196">個人用ボットは、モバイル クライアントのチャットに引き続き表示されます。</span><span class="sxs-lookup"><span data-stu-id="3f047-196">Personal bots will still appear in Chat on mobile clients.</span></span>

<span data-ttu-id="3f047-197">Teams モバイル クライアントを使用すると、ユーザーにはアクティビティ、チャット、Teams などの主要な Teams アプリが表示され、Shifts などの Microsoft の一部のファースト パーティ アプリをピン留めすることができます。</span><span class="sxs-lookup"><span data-stu-id="3f047-197">With the Teams mobile clients, users will see core Teams apps such as Activity, Chat, and Teams, and you can pin some first-party apps from Microsoft, such as Shifts.</span></span>

#### <a name="can-users-change-the-order-of-apps-pinned-through-a-policy"></a><span data-ttu-id="3f047-198">ユーザーがポリシーを使用してピン留めされたアプリの順序を変更できる</span><span class="sxs-lookup"><span data-stu-id="3f047-198">Can users change the order of apps pinned through a policy</span></span>

<span data-ttu-id="3f047-199">[ユーザーのピン留めを許可する] オプションがオンになっている場合、ユーザーは Teams デスクトップクライアントとモバイル クライアントでピン留めされたアプリの **順序を変更** できます。</span><span class="sxs-lookup"><span data-stu-id="3f047-199">Users can change the order of their pinned apps on Teams desktop and mobile clients if the **Allow user pinning** option is turned on.</span></span> <span data-ttu-id="3f047-200">ユーザーは、Teams Web クライアントにピン留めされたアプリの順序を変更することはできません。</span><span class="sxs-lookup"><span data-stu-id="3f047-200">Users can't change the order of their pinned apps on Teams web clients.</span></span>

#### <a name="does-user-pinning-take-precedence"></a><span data-ttu-id="3f047-201">ユーザーのピン留めが優先される</span><span class="sxs-lookup"><span data-stu-id="3f047-201">Does user pinning take precedence</span></span>

<span data-ttu-id="3f047-202">ユーザーに割り当てられたアプリセットアップ ポリシーが変更され、ユーザー アプリのピン留めがブロックされた場合、Teams はアプリ バーにピン留めされたアプリを削除します。</span><span class="sxs-lookup"><span data-stu-id="3f047-202">If the app setup policy assigned to the user is changed to block user app pinning, Teams removes any apps pinned to the app bar.</span></span> <span data-ttu-id="3f047-203">ユーザー アプリのピン留めを許可するポリシーが変更された場合、ユーザーは以前にピン留めしたアプリを再びピン留めする必要があります。</span><span class="sxs-lookup"><span data-stu-id="3f047-203">If the policy is then changed to allow user app pinning, users must re-pin their previously pinned apps.</span></span>

### <a name="custom-teams-apps"></a><span data-ttu-id="3f047-204">カスタム Teams アプリ</span><span class="sxs-lookup"><span data-stu-id="3f047-204">Custom Teams apps</span></span>

#### <a name="my-organization-built-a-custom-teams-app-and-published-it-either-to-appsource-or-the-tenant-app-catalog-but-the-app-icon-isnt-displayed-as-expected-when-the-app-is-pinned-to-the-app-bar-in-teams-how-do-i-fix-it"></a><span data-ttu-id="3f047-205">組織でカスタム Teams アプリを作成し、AppSource またはテナント アプリ カタログに発行しましたが、アプリが Teams のアプリ バーにピン留めされている場合、アプリ アイコンが期待した方法で表示されません。</span><span class="sxs-lookup"><span data-stu-id="3f047-205">My organization built a custom Teams app and published it, either to AppSource or the tenant app catalog, but the app icon isn't displayed as expected when the app is pinned to the app bar in Teams.</span></span> <span data-ttu-id="3f047-206">修正方法</span><span class="sxs-lookup"><span data-stu-id="3f047-206">How do I fix it</span></span>

<span data-ttu-id="3f047-207">アプリを提出する前に、ロゴのガイドラインに従う必要があります。</span><span class="sxs-lookup"><span data-stu-id="3f047-207">Make sure that you follow the logo guidelines before you submit the app.</span></span> <span data-ttu-id="3f047-208">詳細については、「販売者ダッシュボード提出 [のチェックリスト」を参照してください](/microsoftteams/platform/concepts/deploy-and-publish/appsource/prepare/overview)。</span><span class="sxs-lookup"><span data-stu-id="3f047-208">To learn more, see [Checklist for Seller Dashboard submission](/microsoftteams/platform/concepts/deploy-and-publish/appsource/prepare/overview).</span></span>

## <a name="related-topics"></a><span data-ttu-id="3f047-209">関連項目</span><span class="sxs-lookup"><span data-stu-id="3f047-209">Related topics</span></span>

[<span data-ttu-id="3f047-210">Teams でのアプリの管理設定</span><span class="sxs-lookup"><span data-stu-id="3f047-210">Admin settings for apps in Teams</span></span>](admin-settings.md)

[<span data-ttu-id="3f047-211"> Teams でユーザーにポリシーを割り当てる</span><span class="sxs-lookup"><span data-stu-id="3f047-211">Assign policies to your users in Teams</span></span>](assign-policies.md)
