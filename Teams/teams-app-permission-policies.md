---
title: Microsoft Teams のアプリのアクセス許可ポリシーを管理する
author: lanachin
ms.author: v-lanac
manager: serdars
ms.date: 3/18/2019
ms.reviewer: lajin
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Help
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
description: Microsoft Teams のアプリのアクセス許可ポリシーと、それらを使用して、組織内のユーザーが利用できるアプリを制御する方法について説明します。
f1keywords:
- ms.teamsadmincenter.apppolicies.overview
ms.openlocfilehash: d15346370015843eeb497cce7fa85928e77c96d9
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2019
ms.locfileid: "34298892"
---
# <a name="manage-app-permission-policies-in-microsoft-teams"></a><span data-ttu-id="58c1b-103">Microsoft Teams のアプリのアクセス許可ポリシーを管理する</span><span class="sxs-lookup"><span data-stu-id="58c1b-103">Manage app permission policies in Microsoft Teams</span></span>

> [!INCLUDE [feature coming soon](includes/new-feature-coming-soon-article.md)]

<span data-ttu-id="58c1b-104">管理者は、アプリのアクセス許可ポリシーを使って、組織内の Microsoft Teams ユーザーが利用できるアプリを制御することができます。</span><span class="sxs-lookup"><span data-stu-id="58c1b-104">As an admin, you can use app permission policies to control what apps are available to Microsoft Teams users in your organization.</span></span> <span data-ttu-id="58c1b-105">Microsoft、サードパーティ、組織によって公開されたすべてのアプリまたは特定のアプリを許可またはブロックすることができます。</span><span class="sxs-lookup"><span data-stu-id="58c1b-105">You can allow or block all apps or specific apps published by Microsoft, third-parties, and your organization.</span></span> <span data-ttu-id="58c1b-106">アプリをブロックすると、ユーザーは Teams app store からアプリをインストールできなくなります。</span><span class="sxs-lookup"><span data-stu-id="58c1b-106">When you block an app, users are unable to install it from the Teams app store.</span></span>

<span data-ttu-id="58c1b-107">アプリのアクセス許可ポリシーは、Microsoft Teams 管理センターで管理します。</span><span class="sxs-lookup"><span data-stu-id="58c1b-107">You manage app permission policies in the Microsoft Teams admin center.</span></span> <span data-ttu-id="58c1b-108">組織全体の設定を適用したり、グローバル (組織全体の既定) ポリシーを使用したり、個々のユーザーまたはグループ内のユーザーにカスタムポリシーを作成して割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="58c1b-108">You can apply settings org-wide, use the global (Org-wide default) policy, and create and assign custom policies to individual users or users in a group.</span></span>  

![アプリのアクセス許可ポリシーのスクリーンショット](media/app-permission-policies.png)

> [!NOTE]
> <span data-ttu-id="58c1b-110">組織内のユーザーは、カスタムポリシーを作成して割り当てる場合を除き、自動的にグローバルポリシーを取得します。</span><span class="sxs-lookup"><span data-stu-id="58c1b-110">Users in your organization will automatically get the global policy unless you create and assign a custom policy.</span></span> <span data-ttu-id="58c1b-111">組織全体のアプリ設定は、グローバルポリシーや、作成してユーザーに割り当てるカスタムポリシーを上書きします。</span><span class="sxs-lookup"><span data-stu-id="58c1b-111">Org-wide app settings override the global policy and any custom policies that you create and assign to users.</span></span>

<span data-ttu-id="58c1b-112">たとえば、すべてのサードパーティ製のアプリをブロックして、組織内の HR チーム向けに Microsoft が提供する特定のアプリを許可する必要があるとします。</span><span class="sxs-lookup"><span data-stu-id="58c1b-112">Say, for example, you want to block all third-party apps and allow specific apps from Microsoft for the HR team in your organization.</span></span> <span data-ttu-id="58c1b-113">HR アプリのアクセス許可ポリシーという名前のカスタムポリシーを作成し、必要なアプリをブロックおよび許可するように設定し、人事チームのユーザーに割り当てます。</span><span class="sxs-lookup"><span data-stu-id="58c1b-113">You would create a custom policy named HR App Permission Policy, set it to block and allow the apps that you want, and then assign it to users on the HR team.</span></span>

## <a name="manage-org-wide-app-settings"></a><span data-ttu-id="58c1b-114">組織全体のアプリ設定を管理する</span><span class="sxs-lookup"><span data-stu-id="58c1b-114">Manage org-wide app settings</span></span>

<span data-ttu-id="58c1b-115">組織全体で利用可能なアプリを管理するには、組織全体のアプリ設定を使います。</span><span class="sxs-lookup"><span data-stu-id="58c1b-115">Use org-wide app settings to control which apps are available across your organization.</span></span> <span data-ttu-id="58c1b-116">組織全体のアプリの設定では、すべてのユーザーに対する動作が管理され、ユーザーに割り当てられている他のアプリのアクセス許可ポリシーは上書きされます。</span><span class="sxs-lookup"><span data-stu-id="58c1b-116">Org-wide app settings govern the behavior for all users and override any other app permission policies assigned to users.</span></span> <span data-ttu-id="58c1b-117">組織全体のアプリの設定はすぐに有効になり、悪意のあるアプリや問題のあるアプリの制御に使用できます。</span><span class="sxs-lookup"><span data-stu-id="58c1b-117">Org-wide app settings take effect immediately and you can use them to control malicious or problematic apps.</span></span>

1. <span data-ttu-id="58c1b-118">Microsoft Teams 管理センターの左のナビゲーションで、[ **Teams アプリ** > の**権限ポリシー**] に移動します。</span><span class="sxs-lookup"><span data-stu-id="58c1b-118">In the left navigation of the Microsoft Teams admin center, go to **Teams app** > **Permission policies**.</span></span>
2. <span data-ttu-id="58c1b-119">[**組織全体の設定**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="58c1b-119">Select **Org-wide settings**.</span></span> <span data-ttu-id="58c1b-120">次に、パネルで設定を構成することができます。</span><span class="sxs-lookup"><span data-stu-id="58c1b-120">You can then configure the settings you want in the panel.</span></span> 
<span data-ttu-id="58c1b-121">![組織全体のアプリ設定のスクリーンショット](media/app-permission-policies-org-wide-settings.png)</span><span class="sxs-lookup"><span data-stu-id="58c1b-121">![Screen shot of org-wide app settings](media/app-permission-policies-org-wide-settings.png)</span></span>
3. <span data-ttu-id="58c1b-122">サード**パーティ**製のアプリで、次の設定を有効または無効にして、サードパーティ製のアプリへのアクセスを制御します。</span><span class="sxs-lookup"><span data-stu-id="58c1b-122">Under **Third-party apps**, turn off or turn on these settings to control access to third-party apps:</span></span>

    - <span data-ttu-id="58c1b-123">**Teams でサードパーティ製アプリを許可する**: ユーザーがサードパーティ製のアプリを使えるかどうかを制御します。</span><span class="sxs-lookup"><span data-stu-id="58c1b-123">**Allow third-party apps in Teams**: This controls whether users can use third-party apps.</span></span>
    - <span data-ttu-id="58c1b-124">**既定でストアに公開**されている新しいサードパーティのアプリを許可します。これは、teams app store に公開された新しいサードパーティアプリが teams で自動的に使用できるようになるかどうかを制御します。</span><span class="sxs-lookup"><span data-stu-id="58c1b-124">**Allow any new third-party apps published to the store by default**: This controls whether new third-party apps that are published to the Teams app store become automatically available in Teams.</span></span> <span data-ttu-id="58c1b-125">このオプションを設定するには、サードパーティ製のアプリを許可する必要があります。</span><span class="sxs-lookup"><span data-stu-id="58c1b-125">You can only set this option if you allow third-party apps.</span></span>

4. <span data-ttu-id="58c1b-126">[**カスタムアプリ**] の下で、[**カスタムアプリとの対話を許可する**] をオンまたはオフにします。</span><span class="sxs-lookup"><span data-stu-id="58c1b-126">Under **Custom apps**, turn off or turn on **Allow interaction with custom apps**.</span></span> <span data-ttu-id="58c1b-127">この設定は、ユーザーがカスタム (サイドローディング) アプリを操作できるかどうかを制御します。</span><span class="sxs-lookup"><span data-stu-id="58c1b-127">This setting controls whether users can interact with custom (sideloaded) apps.</span></span> <span data-ttu-id="58c1b-128">これは、ユーザーがカスタムアプリを*アップロード*することを許可することとは異なります。</span><span class="sxs-lookup"><span data-stu-id="58c1b-128">Keep in mind that this is different from allowing users to *upload* custom apps.</span></span>
5. <span data-ttu-id="58c1b-129">[**ブロックするアプリ**] で、組織全体でブロックするアプリを検索して追加します。</span><span class="sxs-lookup"><span data-stu-id="58c1b-129">Under **Blocked apps**, search for and add the apps that you want to block across your organization.</span></span> <span data-ttu-id="58c1b-130">テナントアプリカタログまたは Teams app store からアプリを選ぶことができます。</span><span class="sxs-lookup"><span data-stu-id="58c1b-130">You can choose apps from the tenant app catalog or the Teams app store.</span></span>
6. <span data-ttu-id="58c1b-131">組織全体のアプリ設定を有効にするには、[**保存**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="58c1b-131">Click **Save** for org-wide app settings to take effect.</span></span>

## <a name="create-a-custom-app-permission-policy"></a><span data-ttu-id="58c1b-132">カスタムアプリのアクセス許可ポリシーを作成する</span><span class="sxs-lookup"><span data-stu-id="58c1b-132">Create a custom app permission policy</span></span>

<span data-ttu-id="58c1b-133">組織内のユーザーグループごとに使用できるアプリを制御する場合は、1つ以上のカスタムアプリのアクセス許可ポリシーを作成して割り当てます。</span><span class="sxs-lookup"><span data-stu-id="58c1b-133">If you want to control the apps that are available for different groups of users in your organization, create and assign one or more custom app permission policies.</span></span> <span data-ttu-id="58c1b-134">Microsoft、サードパーティ、または組織によってアプリが公開されるかどうかに基づいて、個別のカスタムポリシーを作成して割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="58c1b-134">You can create and assign separate custom policies based on whether apps are published by Microsoft, third-parties, or your organization.</span></span> <span data-ttu-id="58c1b-135">組織全体の設定でサードパーティ製のアプリが無効になっている場合は、カスタムポリシーを作成した後に変更することはできないことを知っておくことが重要です。</span><span class="sxs-lookup"><span data-stu-id="58c1b-135">It's important to know that after you create a custom policy, you can't change it if third-party apps are disabled in org-wide settings.</span></span> 

1. <span data-ttu-id="58c1b-136">Microsoft Teams 管理センターの左のナビゲーションで、[ **Teams アプリ** > の**権限ポリシー**] に移動します。</span><span class="sxs-lookup"><span data-stu-id="58c1b-136">In the left navigation of the Microsoft Teams admin center, go to **Teams app** > **Permission policies**.</span></span>
2. <span data-ttu-id="58c1b-137">[**新しいポリシー**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="58c1b-137">Select **New policy**.</span></span>
    <span data-ttu-id="58c1b-138">![新しいアプリのアクセス許可ポリシーのスクリーンショット](media/app-permission-policies-new-policy.png)</span><span class="sxs-lookup"><span data-stu-id="58c1b-138">![Screen shot of new app permission policy](media/app-permission-policies-new-policy.png)</span></span>
3. <span data-ttu-id="58c1b-139">ポリシーのわかりやすい名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="58c1b-139">Enter a descriptive name for the policy.</span></span>
4. <span data-ttu-id="58c1b-140">[ **Microsoft アプリ**]、[**サードパーティ製アプリ**]、[**テナントアプリ**] の下で、次のいずれかを選択します。</span><span class="sxs-lookup"><span data-stu-id="58c1b-140">Under **Microsoft apps**, **Third-party apps**, and **Tenant apps**, select one of the following:</span></span>

    - <span data-ttu-id="58c1b-141">**すべてのアプリを許可する**</span><span class="sxs-lookup"><span data-stu-id="58c1b-141">**Allow all apps**</span></span>
    - <span data-ttu-id="58c1b-142">**特定のアプリを許可し、他のユーザーをブロックする**</span><span class="sxs-lookup"><span data-stu-id="58c1b-142">**Allow specific apps and block all others**</span></span>
    - <span data-ttu-id="58c1b-143">**特定のアプリをブロックし、他のユーザーをすべて許可する**</span><span class="sxs-lookup"><span data-stu-id="58c1b-143">**Block specific apps and allow all others**</span></span>
    - <span data-ttu-id="58c1b-144">**すべてのアプリをブロックする**</span><span class="sxs-lookup"><span data-stu-id="58c1b-144">**Block all apps**</span></span>

5. <span data-ttu-id="58c1b-145">**[特定のアプリを許可**する] を選んで他のアプリをブロックする場合は、許可するアプリを追加します。</span><span class="sxs-lookup"><span data-stu-id="58c1b-145">If you selected **Allow specific apps and block others**, add the apps that you want to allow:</span></span>

    1. <span data-ttu-id="58c1b-146">[**アプリの許可**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="58c1b-146">Select **Allow apps**.</span></span>
    1. <span data-ttu-id="58c1b-147">許可するアプリを検索し、[**追加**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="58c1b-147">Search for the apps that you want to allow, and then click **Add**.</span></span> <span data-ttu-id="58c1b-148">検索結果は、アプリの発行元 (**Microsoft アプリ**、**サードパーティ製のアプリ**、**テナントアプリ**) にフィルター処理されます。</span><span class="sxs-lookup"><span data-stu-id="58c1b-148">The search results are filtered to the app publisher (**Microsoft apps**, **Third-party apps**, or **Tenant apps**).</span></span>
    1. <span data-ttu-id="58c1b-149">アプリの一覧を選択したら、[**許可**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="58c1b-149">When you've chosen the list of apps, click **Allow**.</span></span>

6. <span data-ttu-id="58c1b-150">同様に、[**特定のアプリをブロック**する] を選択した場合は、ブロックするアプリを検索して追加します。</span><span class="sxs-lookup"><span data-stu-id="58c1b-150">Similarly, if you selected **Block specific apps and allow all others**, search for and add the apps that you want to block.</span></span>
7. <span data-ttu-id="58c1b-151">[**保存**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="58c1b-151">Click **Save**.</span></span>

## <a name="edit-an-app-permission-policy"></a><span data-ttu-id="58c1b-152">アプリのアクセス許可ポリシーを編集する</span><span class="sxs-lookup"><span data-stu-id="58c1b-152">Edit an app permission policy</span></span>

<span data-ttu-id="58c1b-153">Microsoft Teams 管理センターを使って、作成するグローバル (組織全体の既定) ポリシーやカスタムポリシーなどのポリシーを編集できます。</span><span class="sxs-lookup"><span data-stu-id="58c1b-153">You can use the Microsoft Teams admin center to edit a policy, including the global (Org-wide default) policy and custom policies that you create.</span></span> 

1. <span data-ttu-id="58c1b-154">Microsoft Teams 管理センターの左のナビゲーションで、[ **Teams アプリ** > の**権限ポリシー**] に移動します。</span><span class="sxs-lookup"><span data-stu-id="58c1b-154">In the left navigation of the Microsoft Teams admin center, go to **Teams app** > **Permission policies**.</span></span>
2. <span data-ttu-id="58c1b-155">編集するポリシーを選択します。</span><span class="sxs-lookup"><span data-stu-id="58c1b-155">Select the policy you want to edit.</span></span>
3. <span data-ttu-id="58c1b-156">ここで、必要な変更を行います。</span><span class="sxs-lookup"><span data-stu-id="58c1b-156">From here, make the changes that you want.</span></span> <span data-ttu-id="58c1b-157">アプリの発行元に基づいて設定を管理し、許可/禁止の設定に基づいてアプリを追加および削除することができます。</span><span class="sxs-lookup"><span data-stu-id="58c1b-157">You can manage settings based on the app publisher and add and remove apps based on the allow/block setting.</span></span>
4. <span data-ttu-id="58c1b-158">[**保存**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="58c1b-158">Click **Save**.</span></span>

## <a name="assign-a-custom-app-permission-policy-to-users"></a><span data-ttu-id="58c1b-159">ユーザーにカスタムアプリのアクセス許可ポリシーを割り当てる</span><span class="sxs-lookup"><span data-stu-id="58c1b-159">Assign a custom app permission policy to users</span></span>

<span data-ttu-id="58c1b-160">Microsoft Teams 管理センターを使用して、カスタムポリシーを個々のユーザーに割り当てるか、Skype for Business PowerShell モジュールを使用して、セキュリティグループまたは配布グループ内のすべてのユーザーなどのカスタムポリシーを複数のユーザーに割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="58c1b-160">You can use the Microsoft Teams admin center to assign a custom policy to individual users or the Skype for Business PowerShell module to assign a custom policy to multiple users, such as all users in a security group or distribution group.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="58c1b-161">ユーザーにポリシーを割り当てるには、PowerShell を使用することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="58c1b-161">We recommend using PowerShell only to assign policies to users.</span></span> <span data-ttu-id="58c1b-162">Microsoft Teams 管理センターを使って、ポリシーを作成、編集、管理します。</span><span class="sxs-lookup"><span data-stu-id="58c1b-162">Use the Microsoft Teams admin center to create, edit, and manage policies.</span></span>

### <a name="assign-a-custom-app-permission-policy-to-individual-users"></a><span data-ttu-id="58c1b-163">カスタムアプリのアクセス許可ポリシーを個々のユーザーに割り当てる</span><span class="sxs-lookup"><span data-stu-id="58c1b-163">Assign a custom app permission policy to individual users</span></span>

1. <span data-ttu-id="58c1b-164">Microsoft Teams 管理センターの左側のナビゲーションで、**[ユーザー]** に移動してユーザーをクリックします。</span><span class="sxs-lookup"><span data-stu-id="58c1b-164">In the left navigation of the Microsoft Teams admin center, go to **Users**, and then click the user.</span></span>
2. <span data-ttu-id="58c1b-165">**[割り当てられているポリシー]** の隣にある **[編集]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="58c1b-165">Next to **Assigned policies**, choose **Edit**.</span></span>
3. <span data-ttu-id="58c1b-166">[**アプリのアクセス許可ポリシー**] で、割り当てるアプリのアクセス許可ポリシーを選択し、[**保存**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="58c1b-166">Under **App permission policy**, select the app permission policy you want to assign, and then choose **Save**.</span></span>

    ![app-setup-permission-assign-policy](media/app-permission-policies-assign-policy.png)

<span data-ttu-id="58c1b-168">また、次のように、1人または複数のユーザーにアプリのアクセス許可ポリシーを割り当てることもできます。</span><span class="sxs-lookup"><span data-stu-id="58c1b-168">You can also assign an app permission policy to one or more users as follows:</span></span>

1. <span data-ttu-id="58c1b-169">**Microsoft teams 管理センター** > の**teams アプリ** > の**アクセス許可ポリシー**に移動します。</span><span class="sxs-lookup"><span data-stu-id="58c1b-169">Go to **Microsoft Teams admin center** > **Teams apps** > **Permission policies**.</span></span>
2. <span data-ttu-id="58c1b-170">ポリシー名の左側をクリックして、ポリシーを選択します。</span><span class="sxs-lookup"><span data-stu-id="58c1b-170">Select the policy by clicking to the left of the policy name.</span></span>
3. <span data-ttu-id="58c1b-171">[**ユーザーの管理**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="58c1b-171">Select **Manage users**.</span></span>
4. <span data-ttu-id="58c1b-172">[**ユーザーの管理**] ウィンドウで、[表示名] または [ユーザー名] でユーザーを検索し、名前を選択して [**追加**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="58c1b-172">In the **Manage users** pane, search for the user by display name or by user name, select the name, and then select **Add**.</span></span> <span data-ttu-id="58c1b-173">追加するユーザーごとに、この手順を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="58c1b-173">Repeat this step for each user that you want to add.</span></span>
5. <span data-ttu-id="58c1b-174">ユーザーの追加が完了したら、[**保存**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="58c1b-174">When you are finished adding users, select **Save**.</span></span>
 

### <a name="assign-a-custom-app-permission-policy-to-users-in-a-group"></a><span data-ttu-id="58c1b-175">カスタムアプリのアクセス許可ポリシーをグループ内のユーザーに割り当てる</span><span class="sxs-lookup"><span data-stu-id="58c1b-175">Assign a custom app permission policy to users in a group</span></span>

<span data-ttu-id="58c1b-176">カスタムアプリのアクセス許可ポリシーは、既に指定した複数のユーザーに割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="58c1b-176">You may want to assign a custom app permission policy to multiple users that you’ve already identified.</span></span> <span data-ttu-id="58c1b-177">たとえば、セキュリティグループ内のすべてのユーザーにポリシーを割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="58c1b-177">For example, you may want to assign a policy to all users in a security group.</span></span> <span data-ttu-id="58c1b-178">これを行うには、Azure Active Directory PowerShell for Graph モジュールと Skype for Business PowerShell モジュールに接続します。</span><span class="sxs-lookup"><span data-stu-id="58c1b-178">You can do this by connecting to the Azure Active Directory PowerShell for Graph module and the Skype for Business PowerShell module.</span></span> <span data-ttu-id="58c1b-179">PowerShell を使用して Teams を管理する方法の詳細については、「[Teams での PowerShell の概要](teams-powershell-overview.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="58c1b-179">For more information about using PowerShell to manage Teams, see [Teams PowerShell Overview](teams-powershell-overview.md).</span></span>

<span data-ttu-id="58c1b-180">この例では、Contoso 製薬 HR プロジェクトグループ内のすべてのユーザーに HR アプリのアクセス許可ポリシーと呼ばれるカスタムアプリのアクセス許可ポリシーを割り当てます。</span><span class="sxs-lookup"><span data-stu-id="58c1b-180">In this example, we assign a custom app permission policy called HR App Permission Policy to all users in the Contoso Pharmaceuticals HR Project group.</span></span>  

> [!NOTE]
> <span data-ttu-id="58c1b-181">「[単一の Windows PowerShell ウィンドウですべての Office 365 サービスに接続する](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-all-office-365-services-in-a-single-windows-powershell-window)」の手順に従って、必ず最初に Azure Active Directory PowerShell for Graph モジュールと Skype for Business PowerShell モジュールに接続してください。</span><span class="sxs-lookup"><span data-stu-id="58c1b-181">Make sure you first connect to the Azure Active Directory PowerShell for Graph module and Skype for Business PowerShell module by following the steps in [Connect to all Office 365 services in a single Windows PowerShell window](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-all-office-365-services-in-a-single-windows-powershell-window).</span></span>

<span data-ttu-id="58c1b-182">特定のグループの GroupObjectId を取得します。</span><span class="sxs-lookup"><span data-stu-id="58c1b-182">Get the GroupObjectId of the particular group.</span></span>
```
$group = Get-AzureADGroup -SearchString "Contoso Pharmaceuticals HR Project"
```
<span data-ttu-id="58c1b-183">指定したグループのメンバーを取得します。</span><span class="sxs-lookup"><span data-stu-id="58c1b-183">Get the members of the specified group.</span></span>
```
$members = Get-AzureADGroupMember -ObjectId $group.ObjectId -All $true | Where-Object {$_.ObjectType -eq "User"}
```
<span data-ttu-id="58c1b-184">グループ内のすべてのユーザーに特定のアプリのアクセス許可ポリシーを割り当てます。</span><span class="sxs-lookup"><span data-stu-id="58c1b-184">Assign all users in the group to a particular app permission policy.</span></span> <span data-ttu-id="58c1b-185">この例では、HR アプリのアクセス許可ポリシーです。</span><span class="sxs-lookup"><span data-stu-id="58c1b-185">In this example, it's HR App Permission Policy.</span></span>
```
$members | ForEach-Object { Grant-CsTeamsAppPermissionPolicy -PolicyName "HR App Permission Policy" -Identity $_.EmailAddress}
``` 
<span data-ttu-id="58c1b-186">グループ内のメンバー数によっては、このコマンドの実行に数分かかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="58c1b-186">Depending on the number of members in the group, this command may take several minutes to execute.</span></span>

## <a name="faq"></a><span data-ttu-id="58c1b-187">FAQ</span><span class="sxs-lookup"><span data-stu-id="58c1b-187">FAQ</span></span>

### <a name="working-with-app-permission-policies"></a><span data-ttu-id="58c1b-188">アプリのアクセス許可ポリシーを使用する</span><span class="sxs-lookup"><span data-stu-id="58c1b-188">Working with app permission policies</span></span>

#### <a name="can-i-control-line-of-business-lob-apps"></a><span data-ttu-id="58c1b-189">基幹業務 (LOB) アプリを制御することはできますか?</span><span class="sxs-lookup"><span data-stu-id="58c1b-189">Can I control line of business (LOB) apps?</span></span>

<span data-ttu-id="58c1b-190">はい、アプリのアクセス許可ポリシーを使って、カスタム (LOB) アプリのロールアウトと配布を制御することができます。</span><span class="sxs-lookup"><span data-stu-id="58c1b-190">Yes, you can use app permission policies to control the rollout and distribution of custom (LOB) apps.</span></span>

#### <a name="how-do-app-permission-policies-relate-to-pinned-apps-and-app-setup-policies"></a><span data-ttu-id="58c1b-191">アプリのアクセス許可ポリシーは、固定されたアプリとアプリのセットアップポリシーにどのように関連していますか?</span><span class="sxs-lookup"><span data-stu-id="58c1b-191">How do app permission policies relate to pinned apps and app setup policies?</span></span>

<span data-ttu-id="58c1b-192">アプリのセットアップポリシーは、アプリのアクセス許可ポリシーと一緒に使うことができます。</span><span class="sxs-lookup"><span data-stu-id="58c1b-192">You can use app setup policies together with app permission policies.</span></span> <span data-ttu-id="58c1b-193">事前にピン留めされたアプリは、ユーザーに対して有効になっているアプリのセットから選択されます。</span><span class="sxs-lookup"><span data-stu-id="58c1b-193">Pre-pinned apps are selected from the set of enabled apps for a user.</span></span> <span data-ttu-id="58c1b-194">さらに、ユーザーがアプリのセットアップポリシーでアプリをブロックするアプリのアクセス許可ポリシーを持っている場合、そのアプリは Teams に表示されません。</span><span class="sxs-lookup"><span data-stu-id="58c1b-194">Additionally, if a user has an app permission policy that blocks an app in their app setup policy, that app won't appear in Teams.</span></span>

#### <a name="can-i-use-app-permission-policies-to-restrict-uploading-custom-apps-also-known-as-sideloading"></a><span data-ttu-id="58c1b-195">アプリのアクセス許可ポリシーを使って、(サイドローディングとも呼ばれる) カスタムアプリのアップロードを制限することはできますか?</span><span class="sxs-lookup"><span data-stu-id="58c1b-195">Can I use app permission policies to restrict uploading custom apps (also known as sideloading)?</span></span>

<span data-ttu-id="58c1b-196">カスタムアプリのアップロードを制限する方法の詳細については、「 [Teams でカスタムアプリポリシーと設定を管理](teams-custom-app-policies-and-settings.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="58c1b-196">To learn more about how to restrict uploading custom apps, see [Manage custom app policies and settings in Teams](teams-custom-app-policies-and-settings.md).</span></span>

#### <a name="how-long-does-it-take-for-policy-changes-to-take-effect"></a><span data-ttu-id="58c1b-197">ポリシーの変更が有効になるまでにはどのくらいの時間がかかりますか?</span><span class="sxs-lookup"><span data-stu-id="58c1b-197">How long does it take for policy changes to take effect?</span></span>

<span data-ttu-id="58c1b-198">グローバルポリシーを編集するか、ポリシーをユーザーに割り当てると、変更が有効になるまで最大24時間かかることがあります。</span><span class="sxs-lookup"><span data-stu-id="58c1b-198">After you edit the global policy or assign a policy to users, it can take up to 24 hours for changes to take effect.</span></span> <span data-ttu-id="58c1b-199">組織全体のアプリの設定はすぐに有効になります。</span><span class="sxs-lookup"><span data-stu-id="58c1b-199">Org-wide app settings take effect immediately.</span></span>

#### <a name="does-blocking-an-app-apply-to-teams-mobile-clients"></a><span data-ttu-id="58c1b-200">アプリのブロックは Teams のモバイルクライアントに適用されますか?</span><span class="sxs-lookup"><span data-stu-id="58c1b-200">Does blocking an app apply to Teams mobile clients?</span></span>

<span data-ttu-id="58c1b-201">はい。アプリをブロックすると、そのアプリはすべてのチームクライアントでブロックされます。</span><span class="sxs-lookup"><span data-stu-id="58c1b-201">Yes, when you block an app, that app is blocked across all Teams clients.</span></span>  

### <a name="user-experience"></a><span data-ttu-id="58c1b-202">ユーザー エクスペリエンス</span><span class="sxs-lookup"><span data-stu-id="58c1b-202">User experience</span></span>

#### <a name="what-does-a-user-experience-when-an-app-is-blocked"></a><span data-ttu-id="58c1b-203">アプリがブロックされると、ユーザーエクスペリエンスはどうなりますか?</span><span class="sxs-lookup"><span data-stu-id="58c1b-203">What does a user experience when an app is blocked?</span></span>

<span data-ttu-id="58c1b-204">ブロックされたアプリやその機能 (ボット、タブ、メッセージング拡張機能など) をユーザーが操作することはできません。</span><span class="sxs-lookup"><span data-stu-id="58c1b-204">Users can't interact with a blocked app or its capabilities, such bots, tabs, and messaging extensions.</span></span> <span data-ttu-id="58c1b-205">チームやグループチャットなどの共有コンテキストでも、ボットはそのコンテキストの参加者全員にメッセージを送信できます。</span><span class="sxs-lookup"><span data-stu-id="58c1b-205">In a shared context, such as a team or group chat, bots can still send messages to all participants of that context.</span></span> <span data-ttu-id="58c1b-206">アプリがブロックされると、Teams によってユーザーにユーザーが示されます。</span><span class="sxs-lookup"><span data-stu-id="58c1b-206">Teams indicates to the user when an app is blocked.</span></span> 

<span data-ttu-id="58c1b-207">たとえば、アプリがブロックされると、ユーザーは次のいずれも実行できません。</span><span class="sxs-lookup"><span data-stu-id="58c1b-207">For example, when an app is blocked, users can't do any of the following:</span></span>

- <span data-ttu-id="58c1b-208">アプリを個人的に、またはチャットやチームに追加する</span><span class="sxs-lookup"><span data-stu-id="58c1b-208">Add the app personally or to a chat or team</span></span>
- <span data-ttu-id="58c1b-209">アプリのボットにメッセージを送信する</span><span class="sxs-lookup"><span data-stu-id="58c1b-209">Send messages to the app’s bot</span></span>
- <span data-ttu-id="58c1b-210">操作可能なメッセージなど、情報をアプリに送り戻すボタンアクションを実行します。</span><span class="sxs-lookup"><span data-stu-id="58c1b-210">Perform button actions that send information back to the app, such as actionable messages</span></span>  
- <span data-ttu-id="58c1b-211">アプリのタブを表示する</span><span class="sxs-lookup"><span data-stu-id="58c1b-211">View the app’s tab</span></span>
- <span data-ttu-id="58c1b-212">通知を受信するためのコネクタを設定する</span><span class="sxs-lookup"><span data-stu-id="58c1b-212">Set up connectors to receive notifications</span></span>
- <span data-ttu-id="58c1b-213">アプリのメッセージング拡張機能を使用する</span><span class="sxs-lookup"><span data-stu-id="58c1b-213">Use the app’s messaging extension</span></span>

 ## <a name="related-topics"></a><span data-ttu-id="58c1b-214">関連トピック</span><span class="sxs-lookup"><span data-stu-id="58c1b-214">Related topics</span></span>
- [<span data-ttu-id="58c1b-215">Teams でのアプリの管理設定</span><span class="sxs-lookup"><span data-stu-id="58c1b-215">Admin settings for apps in Teams</span></span>](admin-settings.md)
- [<span data-ttu-id="58c1b-216">Teams のアプリのセットアップ ポリシーを管理する</span><span class="sxs-lookup"><span data-stu-id="58c1b-216">Manage app setup policies in Teams</span></span>](teams-app-setup-policies.md)
- [<span data-ttu-id="58c1b-217">Teams のカスタム アプリのポリシーと設定を管理する</span><span class="sxs-lookup"><span data-stu-id="58c1b-217">Manage custom app policies and settings in Teams</span></span>](teams-custom-app-policies-and-settings.md)
