---
title: Microsoft Teams のアプリのアクセス許可ポリシーを管理する
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
description: Microsoft Teams のアプリのアクセス許可ポリシーと、それらを使用して、組織内のユーザーが利用できるアプリを制御する方法について説明します。
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.apppermspolicies.overview
- ms.teamsadmincenter.appsetuppolicies.addpinnedapp.permissions
- ms.teamsadmincenter.apppermspolicies.orgwideapps.customapps
- ms.teamsadmincenter.appsetuppolicies.overview
ms.openlocfilehash: 15698c7eeb12187ccc510a42b9a6e2120a7907cc
ms.sourcegitcommit: 2467ece95e100a3a3cc2be3538d8eb7d878b3663
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/06/2020
ms.locfileid: "45042995"
---
# <a name="manage-app-permission-policies-in-microsoft-teams"></a><span data-ttu-id="53608-103">Microsoft Teams のアプリのアクセス許可ポリシーを管理する</span><span class="sxs-lookup"><span data-stu-id="53608-103">Manage app permission policies in Microsoft Teams</span></span>

<span data-ttu-id="53608-104">管理者であれば、アプリのアクセス許可ポリシーを使用して、組織の Microsoft Teams ユーザーが使用できるアプリを制御できます。</span><span class="sxs-lookup"><span data-stu-id="53608-104">As an admin, you can use app permission policies to control what apps are available to Microsoft Teams users in your organization.</span></span> <span data-ttu-id="53608-105">すべてのアプリ、または Microsoft、第三者、お客様の組織によって公開されている特定のアプリを許可またはブロックすることができます。</span><span class="sxs-lookup"><span data-stu-id="53608-105">You can allow or block all apps or specific apps published by Microsoft, third-parties, and your organization.</span></span> <span data-ttu-id="53608-106">アプリをブロックした場合、ポリシーを持つユーザーは、Teams アプリ ストアからアプリをインストールできません。</span><span class="sxs-lookup"><span data-stu-id="53608-106">When you block an app, users who have the policy are unable to install it from the Teams app store.</span></span> <span data-ttu-id="53608-107">これらのポリシーを管理するには、グローバル管理者または Teams サービス管理者である必要があります。</span><span class="sxs-lookup"><span data-stu-id="53608-107">You must be a global admin or Teams service admin to manage these policies.</span></span>

<span data-ttu-id="53608-108">アプリのアクセス許可ポリシーは、Microsoft Teams 管理センターで管理します。</span><span class="sxs-lookup"><span data-stu-id="53608-108">You manage app permission policies in the Microsoft Teams admin center.</span></span> <span data-ttu-id="53608-109">グローバル (組織全体の既定) ポリシーを使用するか、カスタムポリシーを作成して割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="53608-109">You can use the global (Org-wide default) policy or create and assign custom policies.</span></span> <span data-ttu-id="53608-110">カスタム ポリシーを作成して割り当てていない場合、組織内のユーザーにはグローバル ポリシーが自動的に適用されます。</span><span class="sxs-lookup"><span data-stu-id="53608-110">Users in your organization will automatically get the global policy unless you create and assign a custom policy.</span></span> <span data-ttu-id="53608-111">ポリシーを編集または割り当てると、変更が有効になるまでに数時間かかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="53608-111">After you edit or assign a policy, it can take a few hours for changes to take effect.</span></span>

![アプリのアクセス許可ポリシーのスクリーンショット](media/app-permission-policies.png)

> [!NOTE]
> <span data-ttu-id="53608-113">組織全体のアプリ設定は、グローバルポリシーや、作成してユーザーに割り当てるカスタムポリシーを上書きします。</span><span class="sxs-lookup"><span data-stu-id="53608-113">Org-wide app settings override the global policy and any custom policies that you create and assign to users.</span></span>

<span data-ttu-id="53608-114">組織が既に Teams に登録されている場合は、Microsoft 365 管理センターの**テナント全体の設定**で構成したアプリ設定が、[アプリの[管理](manage-apps.md)] ページの組織全体のアプリの設定に反映されます。</span><span class="sxs-lookup"><span data-stu-id="53608-114">If your organization is already on Teams, the app settings you configured in **Tenant-wide settings** in the Microsoft 365 admin center are reflected in org-wide app settings on the [Manage apps](manage-apps.md) page.</span></span> <span data-ttu-id="53608-115">チームを初めて使い始めたばかりの場合は、既定ではすべてのアプリがグローバルポリシーで許可されています。</span><span class="sxs-lookup"><span data-stu-id="53608-115">If you're new to Teams and just getting started, by default, all apps are allowed in the global policy.</span></span> <span data-ttu-id="53608-116">これには、Microsoft、サードパーティ、組織によって公開されたアプリが含まれます。</span><span class="sxs-lookup"><span data-stu-id="53608-116">This includes apps published by Microsoft, third-parties, and your organization.</span></span>

<span data-ttu-id="53608-117">たとえば、すべてのサードパーティ製のアプリをブロックして、組織内の HR チーム向けに Microsoft が提供する特定のアプリを許可する必要があるとします。</span><span class="sxs-lookup"><span data-stu-id="53608-117">Say, for example, you want to block all third-party apps and allow specific apps from Microsoft for the HR team in your organization.</span></span> <span data-ttu-id="53608-118">最初に、[[アプリの管理](manage-apps.md)] ページに移動し、人事チームに許可するアプリが組織レベルで許可されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="53608-118">First, you would go to the [Manage apps](manage-apps.md) page and make sure that the apps that you want to allow for the HR team are allowed at the org level.</span></span> <span data-ttu-id="53608-119">次に、HR アプリのアクセス許可ポリシーという名前のカスタムポリシーを作成し、必要なアプリをブロックおよび許可するように設定し、人事チームのユーザーに割り当てます。</span><span class="sxs-lookup"><span data-stu-id="53608-119">Then, create a custom policy named HR App Permission Policy, set it to block and allow the apps that you want, and assign it to users on the HR team.</span></span>

> [!NOTE]
> <span data-ttu-id="53608-120">Microsoft 365 Government Community Cloud (GCC) 環境に Teams を展開した場合は、「 [microsoft 365 government の組織全体のアプリ設定を管理](#manage-org-wide-app-settings-for-microsoft-365-government)する」を参照してください。これは、GCC 固有のサードパーティのアプリ設定の詳細について説明します。</span><span class="sxs-lookup"><span data-stu-id="53608-120">If you deployed Teams in a Microsoft 365 Government Community Cloud (GCC) environment, see [Manage org-wide app settings for Microsoft 365 Government](#manage-org-wide-app-settings-for-microsoft-365-government) to learn more about third-party app settings that are unique to GCC.</span></span>

## <a name="create-a-custom-app-permission-policy"></a><span data-ttu-id="53608-121">カスタムアプリのアクセス許可ポリシーを作成する</span><span class="sxs-lookup"><span data-stu-id="53608-121">Create a custom app permission policy</span></span>

<span data-ttu-id="53608-122">組織内のユーザーグループごとに使用できるアプリを制御する場合は、1つ以上のカスタムアプリのアクセス許可ポリシーを作成して割り当てます。</span><span class="sxs-lookup"><span data-stu-id="53608-122">If you want to control the apps that are available for different groups of users in your organization, create and assign one or more custom app permission policies.</span></span> <span data-ttu-id="53608-123">Microsoft、サードパーティ、または組織によってアプリが公開されるかどうかに基づいて、個別のカスタムポリシーを作成して割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="53608-123">You can create and assign separate custom policies based on whether apps are published by Microsoft, third-parties, or your organization.</span></span> <span data-ttu-id="53608-124">組織全体のアプリ設定でサードパーティ製のアプリが無効になっている場合は、カスタムポリシーを作成した後にそれを変更することはできないことに注意してください。</span><span class="sxs-lookup"><span data-stu-id="53608-124">It's important to know that after you create a custom policy, you can't change it if third-party apps are disabled in org-wide app settings.</span></span>

1. <span data-ttu-id="53608-125">Microsoft Teams 管理センターの左のナビゲーションで、[**チームアプリ**の  >  **アクセス許可ポリシー**] に移動します。</span><span class="sxs-lookup"><span data-stu-id="53608-125">In the left navigation of the Microsoft Teams admin center, go to **Teams apps** > **Permission policies**.</span></span>
2. <span data-ttu-id="53608-126">**[追加]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="53608-126">Click **Add**.</span></span> <br>
    <span data-ttu-id="53608-127">![新しいアプリのアクセス許可ポリシーのスクリーンショット](media/app-permission-policies-new-policy.png)</span><span class="sxs-lookup"><span data-stu-id="53608-127">![Screenshot of new app permission policy](media/app-permission-policies-new-policy.png)</span></span>
3. <span data-ttu-id="53608-128">ポリシーの名前と説明を入力します。</span><span class="sxs-lookup"><span data-stu-id="53608-128">Enter a name and description for the policy.</span></span>
4. <span data-ttu-id="53608-129">[ **Microsoft アプリ**]、[**サードパーティ製アプリ**]、[**カスタムアプリ**] の下で、次のいずれかを選択します。</span><span class="sxs-lookup"><span data-stu-id="53608-129">Under **Microsoft apps**, **Third-party apps**, and **Custom apps**, select one of the following:</span></span>

    - <span data-ttu-id="53608-130">**すべてのアプリを許可する**</span><span class="sxs-lookup"><span data-stu-id="53608-130">**Allow all apps**</span></span>
    - <span data-ttu-id="53608-131">**特定のアプリを許可し、他のユーザーをブロックする**</span><span class="sxs-lookup"><span data-stu-id="53608-131">**Allow specific apps and block all others**</span></span>
    - <span data-ttu-id="53608-132">**特定のアプリをブロックし、他のユーザーをすべて許可する**</span><span class="sxs-lookup"><span data-stu-id="53608-132">**Block specific apps and allow all others**</span></span>
    - <span data-ttu-id="53608-133">**すべてのアプリをブロックする**</span><span class="sxs-lookup"><span data-stu-id="53608-133">**Block all apps**</span></span>

5. <span data-ttu-id="53608-134">**[特定のアプリを許可**する] を選んで他のアプリをブロックする場合は、許可するアプリを追加します。</span><span class="sxs-lookup"><span data-stu-id="53608-134">If you selected **Allow specific apps and block others**, add the apps that you want to allow:</span></span>

    1. <span data-ttu-id="53608-135">[**アプリの許可**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="53608-135">Select **Allow apps**.</span></span>
    1. <span data-ttu-id="53608-136">許可するアプリを検索し、[**追加**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="53608-136">Search for the apps that you want to allow, and then click **Add**.</span></span> <span data-ttu-id="53608-137">検索結果は、アプリの発行元 (**Microsoft アプリ**、**サードパーティ製のアプリ**、または**カスタムアプリ**) にフィルター処理されます。</span><span class="sxs-lookup"><span data-stu-id="53608-137">The search results are filtered to the app publisher (**Microsoft apps**, **Third-party apps**, or **Custom apps**).</span></span>
    1. <span data-ttu-id="53608-138">アプリの一覧を選択したら、[**許可**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="53608-138">When you've chosen the list of apps, click **Allow**.</span></span> 

6. <span data-ttu-id="53608-139">同様に、[特定のアプリをブロックする] を選んで、**他のアプリをすべて許可**する場合は、ブロックするアプリを検索して追加し、[**ブロック**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="53608-139">Similarly, if you selected **Block specific apps and allow all others**, search for and add the apps that you want to block, and then click **Block**.</span></span>
7. <span data-ttu-id="53608-140">[**保存**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="53608-140">Click **Save**.</span></span>

## <a name="edit-an-app-permission-policy"></a><span data-ttu-id="53608-141">アプリのアクセス許可ポリシーを編集する</span><span class="sxs-lookup"><span data-stu-id="53608-141">Edit an app permission policy</span></span>

<span data-ttu-id="53608-142">Microsoft Teams 管理センターを使用して、作成するグローバルポリシーやカスタムポリシーなどのポリシーを編集できます。</span><span class="sxs-lookup"><span data-stu-id="53608-142">You can use the Microsoft Teams admin center to edit a policy, including the global policy and custom policies that you create.</span></span>

1. <span data-ttu-id="53608-143">Microsoft Teams 管理センターの左のナビゲーションで、[**チームアプリ**の  >  **アクセス許可ポリシー**] に移動します。</span><span class="sxs-lookup"><span data-stu-id="53608-143">In the left navigation of the Microsoft Teams admin center, go to **Teams apps** > **Permission policies**.</span></span>
2. <span data-ttu-id="53608-144">ポリシー名の左側をクリックしてポリシーを選び、**[編集]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="53608-144">Select the policy by clicking to the left of the policy name, and then click **Edit**.</span></span>
3. <span data-ttu-id="53608-145">ここで、必要な変更を行います。</span><span class="sxs-lookup"><span data-stu-id="53608-145">From here, make the changes that you want.</span></span> <span data-ttu-id="53608-146">アプリの発行元に基づいて設定を管理し、許可/禁止の設定に基づいてアプリを追加および削除することができます。</span><span class="sxs-lookup"><span data-stu-id="53608-146">You can manage settings based on the app publisher and add and remove apps based on the allow/block setting.</span></span>
4. <span data-ttu-id="53608-147">[**保存**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="53608-147">Click **Save**.</span></span>

## <a name="assign-a-custom-app-permission-policy-to-users"></a><span data-ttu-id="53608-148">ユーザーにカスタムアプリのアクセス許可ポリシーを割り当てる</span><span class="sxs-lookup"><span data-stu-id="53608-148">Assign a custom app permission policy to users</span></span>

[!INCLUDE [assign-policy](includes/assign-policy.md)]

## <a name="manage-org-wide-app-settings-for-microsoft-365-government"></a><span data-ttu-id="53608-149">Microsoft 365 Government の組織全体のアプリ設定を管理する</span><span class="sxs-lookup"><span data-stu-id="53608-149">Manage org-wide app settings for Microsoft 365 Government</span></span>  

<span data-ttu-id="53608-150">Microsoft 365 Government-GCC によるチームの展開では、GCC に固有のサードパーティのアプリ設定について、次の点を理解しておくことが重要です。</span><span class="sxs-lookup"><span data-stu-id="53608-150">In a Microsoft 365 Government - GCC deployment of Teams, it's important to know the following about third-party app settings, which are unique to GCC.</span></span>

<span data-ttu-id="53608-151">GCC では、すべてのサードパーティ製アプリが既定でブロックされます。</span><span class="sxs-lookup"><span data-stu-id="53608-151">In GCC, all third-party apps are blocked by default.</span></span> <span data-ttu-id="53608-152">さらに、Microsoft Teams 管理センターの [アプリのアクセス許可ポリシー] ページでサードパーティ製のアプリを管理する方法について、次のメモが表示されます。</span><span class="sxs-lookup"><span data-stu-id="53608-152">Additionally, you'll see the following note about managing third-party apps on the app permission policies page in the Microsoft Teams admin center.</span></span>

![GCC のアプリのアクセス許可ポリシーのスクリーンショット](media/app-permission-policies-gcc.png)

<span data-ttu-id="53608-154">組織全体のアプリ設定を使用して、ユーザーがサードパーティ製のアプリをインストールできるかどうかを制御します。</span><span class="sxs-lookup"><span data-stu-id="53608-154">Use org-wide app settings to control whether users can install third-party apps.</span></span> <span data-ttu-id="53608-155">組織全体のアプリの設定では、すべてのユーザーに対する動作が管理され、ユーザーに割り当てられている他のアプリのアクセス許可ポリシーは上書きされます。</span><span class="sxs-lookup"><span data-stu-id="53608-155">Org-wide app settings govern the behavior for all users and override any other app permission policies assigned to users.</span></span> <span data-ttu-id="53608-156">これらを使って、悪意のあるアプリや問題のあるアプリを制御することができます。</span><span class="sxs-lookup"><span data-stu-id="53608-156">You can use them to control malicious or problematic apps.</span></span>

1. <span data-ttu-id="53608-157">[**アクセス許可ポリシー** ] ページで、[**組織全体のアプリの設定**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="53608-157">On the **Permission policies** page, select **Org-wide app settings**.</span></span> <span data-ttu-id="53608-158">次に、パネルで設定を構成することができます。</span><span class="sxs-lookup"><span data-stu-id="53608-158">You can then configure the settings you want in the panel.</span></span>

    ![組織全体のアプリ設定のスクリーンショット](media/app-permission-policies-gcc-org-wide.png)
    
2. <span data-ttu-id="53608-160">サード**パーティ**製のアプリで、次の設定を有効または無効にして、サードパーティ製のアプリへのアクセスを制御します。</span><span class="sxs-lookup"><span data-stu-id="53608-160">Under **Third-party apps**, turn off or turn on these settings to control access to third-party apps:</span></span>

    - <span data-ttu-id="53608-161">**サードパーティ製のアプリを許可する**: ユーザーがサードパーティ製のアプリを使えるかどうかを制御します。</span><span class="sxs-lookup"><span data-stu-id="53608-161">**Allow third-party apps**: This controls whether users can use third-party apps.</span></span> <span data-ttu-id="53608-162">この設定をオフにすると、ユーザーはサードパーティ製のアプリをインストールまたは使用することができなくなります。</span><span class="sxs-lookup"><span data-stu-id="53608-162">If you turn off this setting, your users won't be able to install or use any third-party apps.</span></span> <span data-ttu-id="53608-163">Microsoft 365 Government-GCC による Teams の展開では、この設定は既定で無効になっています。</span><span class="sxs-lookup"><span data-stu-id="53608-163">In a Microsoft 365 Government - GCC deployment of Teams, this setting is off by default.</span></span>
    - <span data-ttu-id="53608-164">**既定でストアに公開**されている新しいサードパーティのアプリを許可します。これは、teams app store に公開された新しいサードパーティアプリが teams で自動的に使用できるようになるかどうかを制御します。</span><span class="sxs-lookup"><span data-stu-id="53608-164">**Allow any new third-party apps published to the store by default**: This controls whether new third-party apps that are published to the Teams app store become automatically available in Teams.</span></span> <span data-ttu-id="53608-165">このオプションを設定するには、サードパーティ製のアプリを許可する必要があります。</span><span class="sxs-lookup"><span data-stu-id="53608-165">You can only set this option if you allow third-party apps.</span></span>

3. <span data-ttu-id="53608-166">[**ブロックするアプリ**] で、組織全体でブロックするアプリを追加します。</span><span class="sxs-lookup"><span data-stu-id="53608-166">Under **Blocked apps**, add the apps you want to block across your organization.</span></span> <span data-ttu-id="53608-167">Microsoft 365 Government-GCC による Teams の展開では、すべてのサードパーティ製アプリが既定でこのリストに追加されます。</span><span class="sxs-lookup"><span data-stu-id="53608-167">In a Microsoft 365 Government - GCC deployment of Teams, all third-party apps are added to this list by default.</span></span> <span data-ttu-id="53608-168">組織で許可するサードパーティ製のアプリの場合は、このアプリの一覧からアプリを削除します。</span><span class="sxs-lookup"><span data-stu-id="53608-168">For any third-party app you want to allow in your organization, remove the app from this blocked apps list.</span></span> <span data-ttu-id="53608-169">アプリを組織全体でブロックすると、アプリのアクセス許可ポリシーで許可されているかどうかに関係なく、すべてのユーザーに対してアプリが自動的にブロックされます。</span><span class="sxs-lookup"><span data-stu-id="53608-169">When you block an app org-wide, the app is automatically blocked for all your users, regardless of whether it's allowed in any app permission policies</span></span>
4. <span data-ttu-id="53608-170">組織全体のアプリ設定を有効にするには、[**保存**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="53608-170">Click **Save** for org-wide app settings to take effect.</span></span>

<span data-ttu-id="53608-171">前に説明したように、サードパーティ製のアプリを許可するには、グローバル (組織全体の既定) ポリシーを編集して使用するか、またはカスタムポリシーを作成して割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="53608-171">As mentioned earlier, to allow third-party apps, you can either edit and use the global (Org-wide default) policy or create and assign custom policies.</span></span>

## <a name="faq"></a><span data-ttu-id="53608-172">FAQ</span><span class="sxs-lookup"><span data-stu-id="53608-172">FAQ</span></span>

### <a name="working-with-app-permission-policies"></a><span data-ttu-id="53608-173">アプリのアクセス許可ポリシーを使用する</span><span class="sxs-lookup"><span data-stu-id="53608-173">Working with app permission policies</span></span>

#### <a name="what-app-interactions-do-permission-policies-affect"></a><span data-ttu-id="53608-174">権限ポリシーはどのようなアプリの操作に影響しますか?</span><span class="sxs-lookup"><span data-stu-id="53608-174">What app interactions do permission policies affect?</span></span>
<span data-ttu-id="53608-175">権限ポリシーは、エンドユーザーのインストール、検出、操作を制御することによって、アプリの使用を制御します。</span><span class="sxs-lookup"><span data-stu-id="53608-175">Permission policies govern app usage by controlling installation, discovery, and interaction for end users.</span></span> <span data-ttu-id="53608-176">管理者は、割り当てられているアクセス許可ポリシーに関係なく、引き続き Microsoft Teams 管理センターでアプリを管理することができます。</span><span class="sxs-lookup"><span data-stu-id="53608-176">Admins can still manage apps in the Microsoft Teams admin center regardless of the permission policies assigned to them.</span></span>

#### <a name="can-i-control-line-of-business-lob-apps"></a><span data-ttu-id="53608-177">基幹業務 (LOB) アプリを制御することはできますか?</span><span class="sxs-lookup"><span data-stu-id="53608-177">Can I control line of business (LOB) apps?</span></span>
<span data-ttu-id="53608-178">はい、アプリのアクセス許可ポリシーを使って、カスタム (LOB) アプリのロールアウトと配布を制御することができます。</span><span class="sxs-lookup"><span data-stu-id="53608-178">Yes, you can use app permission policies to control the rollout and distribution of custom (LOB) apps.</span></span> <span data-ttu-id="53608-179">ユーザー設定のポリシーを作成するか、またはグローバルポリシーを編集して、組織のニーズに基づいてカスタムアプリを許可またはブロックすることができます。</span><span class="sxs-lookup"><span data-stu-id="53608-179">You can create a custom policy or edit the global policy to allow or block custom apps based on the needs of your organization.</span></span>

#### <a name="how-do-app-permission-policies-relate-to-pinned-apps-and-app-setup-policies"></a><span data-ttu-id="53608-180">アプリのアクセス許可ポリシーは、固定されたアプリとアプリのセットアップポリシーにどのように関連していますか?</span><span class="sxs-lookup"><span data-stu-id="53608-180">How do app permission policies relate to pinned apps and app setup policies?</span></span>

<span data-ttu-id="53608-181">アプリのセットアップポリシーは、アプリのアクセス許可ポリシーと一緒に使うことができます。</span><span class="sxs-lookup"><span data-stu-id="53608-181">You can use app setup policies together with app permission policies.</span></span> <span data-ttu-id="53608-182">事前にピン留めされたアプリは、ユーザーに対して有効になっているアプリのセットから選択されます。</span><span class="sxs-lookup"><span data-stu-id="53608-182">Pre-pinned apps are selected from the set of enabled apps for a user.</span></span> <span data-ttu-id="53608-183">さらに、ユーザーがアプリのセットアップポリシーでアプリをブロックするアプリのアクセス許可ポリシーを持っている場合、そのアプリは Teams に表示されません。</span><span class="sxs-lookup"><span data-stu-id="53608-183">Additionally, if a user has an app permission policy that blocks an app in their app setup policy, that app won't appear in Teams.</span></span>

#### <a name="can-i-use-app-permission-policies-to-restrict-uploading-custom-apps"></a><span data-ttu-id="53608-184">アプリのアクセス許可ポリシーを使って、カスタムアプリのアップロードを制限することはできますか?</span><span class="sxs-lookup"><span data-stu-id="53608-184">Can I use app permission policies to restrict uploading custom apps?</span></span>

<span data-ttu-id="53608-185">[**アプリの管理**] ページまたはアプリのセットアップポリシーで、組織全体の設定を使用して、組織のカスタムアプリのアップロードを制限することができます。</span><span class="sxs-lookup"><span data-stu-id="53608-185">You can use org-wide settings on the **Manage apps** page, or app setup policies to restrict uploading custom apps for your organization.</span></span>  

<span data-ttu-id="53608-186">特定のユーザーによるカスタムアプリのアップロードを制限するには、カスタムアプリポリシーを使用します。</span><span class="sxs-lookup"><span data-stu-id="53608-186">To restrict specific users from uploading custom apps, use custom app policies.</span></span> <span data-ttu-id="53608-187">詳細については、「 [Teams でカスタムアプリポリシーと設定を管理](teams-custom-app-policies-and-settings.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="53608-187">To learn more, see [Manage custom app policies and settings in Teams](teams-custom-app-policies-and-settings.md).</span></span>

#### <a name="does-blocking-an-app-apply-to-teams-mobile-clients"></a><span data-ttu-id="53608-188">アプリのブロックは Teams のモバイルクライアントに適用されますか?</span><span class="sxs-lookup"><span data-stu-id="53608-188">Does blocking an app apply to Teams mobile clients?</span></span>

<span data-ttu-id="53608-189">はい。アプリをブロックすると、そのアプリはすべてのチームクライアントでブロックされます。</span><span class="sxs-lookup"><span data-stu-id="53608-189">Yes, when you block an app, that app is blocked across all Teams clients.</span></span>  

### <a name="user-experience"></a><span data-ttu-id="53608-190">ユーザー エクスペリエンス</span><span class="sxs-lookup"><span data-stu-id="53608-190">User experience</span></span>

#### <a name="what-does-a-user-experience-when-an-app-is-blocked"></a><span data-ttu-id="53608-191">アプリがブロックされると、ユーザーエクスペリエンスはどうなりますか?</span><span class="sxs-lookup"><span data-stu-id="53608-191">What does a user experience when an app is blocked?</span></span>

<span data-ttu-id="53608-192">ブロックされたアプリやその機能 (ボット、タブ、メッセージング拡張機能など) をユーザーが操作することはできません。</span><span class="sxs-lookup"><span data-stu-id="53608-192">Users can't interact with a blocked app or its capabilities, such bots, tabs, and messaging extensions.</span></span> <span data-ttu-id="53608-193">チームやグループチャットなどの共有コンテキストでも、ボットはそのコンテキストの参加者全員にメッセージを送信できます。</span><span class="sxs-lookup"><span data-stu-id="53608-193">In a shared context, such as a team or group chat, bots can still send messages to all participants of that context.</span></span> <span data-ttu-id="53608-194">アプリがブロックされると、Teams によってユーザーにユーザーが示されます。</span><span class="sxs-lookup"><span data-stu-id="53608-194">Teams indicates to the user when an app is blocked.</span></span>

<span data-ttu-id="53608-195">たとえば、アプリがブロックされると、ユーザーは次のいずれも実行できません。</span><span class="sxs-lookup"><span data-stu-id="53608-195">For example, when an app is blocked, users can't do any of the following:</span></span>

- <span data-ttu-id="53608-196">アプリを個人的に、またはチャットやチームに追加する</span><span class="sxs-lookup"><span data-stu-id="53608-196">Add the app personally or to a chat or team</span></span>
- <span data-ttu-id="53608-197">アプリのボットにメッセージを送信する</span><span class="sxs-lookup"><span data-stu-id="53608-197">Send messages to the app’s bot</span></span>
- <span data-ttu-id="53608-198">操作可能なメッセージなど、情報をアプリに送り戻すボタンアクションを実行します。</span><span class="sxs-lookup"><span data-stu-id="53608-198">Perform button actions that send information back to the app, such as actionable messages</span></span>  
- <span data-ttu-id="53608-199">アプリのタブを表示する</span><span class="sxs-lookup"><span data-stu-id="53608-199">View the app’s tab</span></span>
- <span data-ttu-id="53608-200">通知を受信するためのコネクタを設定する</span><span class="sxs-lookup"><span data-stu-id="53608-200">Set up connectors to receive notifications</span></span>
- <span data-ttu-id="53608-201">アプリのメッセージング拡張機能を使用する</span><span class="sxs-lookup"><span data-stu-id="53608-201">Use the app’s messaging extension</span></span>

<span data-ttu-id="53608-202">従来のポータルでは、組織レベルでのアプリの制御が許可されています。つまり、アプリがブロックされると、組織内のすべてのユーザーに対してブロックされます。</span><span class="sxs-lookup"><span data-stu-id="53608-202">The legacy portal allowed controlling apps at the organization level, which means when an app is blocked, it's blocked for all users in the organization.</span></span> <span data-ttu-id="53608-203">[[アプリの管理](manage-apps.md)] ページでのアプリのブロックは、まったく同じように動作します。</span><span class="sxs-lookup"><span data-stu-id="53608-203">Blocking an app on the [Manage apps](manage-apps.md) page works exactly the same way.</span></span>

<span data-ttu-id="53608-204">特定のユーザーに割り当てられたアプリのアクセス許可ポリシーの場合、ボットまたはコネクタ機能を備えたアプリが許可され、その後ブロックされた場合、そのアプリが共有コンテキストの一部のユーザーに対してのみ許可されている場合、そのアプリに対してアクセス許可がないグループチャットまたはチャネルのメンバーは、ボットまたはコネクタが、対話式で操作することはできません。</span><span class="sxs-lookup"><span data-stu-id="53608-204">For app permission policies assigned to specific users, if an app with bot or connector capability was allowed and then blocked, and if the app is then allowed only for some users in a shared context, members of a group chat or channel that don't have permission to that app can see the message history and messages that were posted by the bot or connector, but can't interact with it.</span></span>

## <a name="related-topics"></a><span data-ttu-id="53608-205">関連トピック</span><span class="sxs-lookup"><span data-stu-id="53608-205">Related topics</span></span>

[<span data-ttu-id="53608-206">Teams でのアプリの管理設定</span><span class="sxs-lookup"><span data-stu-id="53608-206">Admin settings for apps in Teams</span></span>](admin-settings.md)

[<span data-ttu-id="53608-207">チームのユーザーにポリシーを割り当てる</span><span class="sxs-lookup"><span data-stu-id="53608-207">Assign policies to your users in Teams</span></span>](assign-policies.md)
