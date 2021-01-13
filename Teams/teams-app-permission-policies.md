---
title: Microsoft Teams のアプリのアクセス許可ポリシーを管理する
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
description: Microsoft Teams のアプリのアクセス許可ポリシーと、それらを使用して組織内のユーザーが使用できるアプリを制御する方法について説明します。
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.apppermspolicies.overview
- ms.teamsadmincenter.appsetuppolicies.addpinnedapp.permissions
- ms.teamsadmincenter.apppermspolicies.orgwideapps.customapps
- ms.teamsadmincenter.appsetuppolicies.overview
ms.openlocfilehash: aa11b21405079ab26bf1fa9572eb203560c4e461
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49802497"
---
# <a name="manage-app-permission-policies-in-microsoft-teams"></a><span data-ttu-id="4334b-103">Microsoft Teams のアプリのアクセス許可ポリシーを管理する</span><span class="sxs-lookup"><span data-stu-id="4334b-103">Manage app permission policies in Microsoft Teams</span></span>

<span data-ttu-id="4334b-104">管理者であれば、アプリのアクセス許可ポリシーを使用して、組織の Microsoft Teams ユーザーが使用できるアプリを制御できます。</span><span class="sxs-lookup"><span data-stu-id="4334b-104">As an admin, you can use app permission policies to control what apps are available to Microsoft Teams users in your organization.</span></span> <span data-ttu-id="4334b-105">すべてのアプリ、または Microsoft、第三者、お客様の組織によって公開されている特定のアプリを許可またはブロックすることができます。</span><span class="sxs-lookup"><span data-stu-id="4334b-105">You can allow or block all apps or specific apps published by Microsoft, third-parties, and your organization.</span></span> <span data-ttu-id="4334b-106">アプリをブロックした場合、ポリシーを持つユーザーは、Teams アプリ ストアからアプリをインストールできません。</span><span class="sxs-lookup"><span data-stu-id="4334b-106">When you block an app, users who have the policy are unable to install it from the Teams app store.</span></span> <span data-ttu-id="4334b-107">これらのポリシーを管理するには、グローバル管理者または Teams サービス管理者である必要があります。</span><span class="sxs-lookup"><span data-stu-id="4334b-107">You must be a global admin or Teams service admin to manage these policies.</span></span>

<span data-ttu-id="4334b-108">Microsoft Teams 管理センターでアプリのアクセス許可ポリシーを管理します。</span><span class="sxs-lookup"><span data-stu-id="4334b-108">You manage app permission policies in the Microsoft Teams admin center.</span></span> <span data-ttu-id="4334b-109">グローバル (組織全体の既定) ポリシーを使用するか、カスタム ポリシーを作成して割り当てできます。</span><span class="sxs-lookup"><span data-stu-id="4334b-109">You can use the global (Org-wide default) policy or create and assign custom policies.</span></span> <span data-ttu-id="4334b-110">カスタム ポリシーを作成して割り当てていない場合、組織内のユーザーにはグローバル ポリシーが自動的に適用されます。</span><span class="sxs-lookup"><span data-stu-id="4334b-110">Users in your organization will automatically get the global policy unless you create and assign a custom policy.</span></span> <span data-ttu-id="4334b-111">ポリシーを編集または割り当てると、変更が有効なまで数時間かかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="4334b-111">After you edit or assign a policy, it can take a few hours for changes to take effect.</span></span>

![アプリのアクセス許可ポリシーのスクリーンショット](media/app-permission-policies.png)

> [!NOTE]
> <span data-ttu-id="4334b-113">組織全体のアプリ設定は、グローバル ポリシーと、ユーザーに作成して割り当てるカスタム ポリシーを上書きします。</span><span class="sxs-lookup"><span data-stu-id="4334b-113">Org-wide app settings override the global policy and any custom policies that you create and assign to users.</span></span>

<span data-ttu-id="4334b-114">組織が既に Teams を使用している場合、Microsoft  365 管理センターのテナント全体の設定で構成したアプリ設定は、[アプリの管理][](manage-apps.md)ページの組織全体のアプリ設定に反映されます。</span><span class="sxs-lookup"><span data-stu-id="4334b-114">If your organization is already on Teams, the app settings you configured in **Tenant-wide settings** in the Microsoft 365 admin center are reflected in org-wide app settings on the [Manage apps](manage-apps.md) page.</span></span> <span data-ttu-id="4334b-115">Teams を使い始め始めたばかりの場合、既定では、すべてのアプリがグローバル ポリシーで許可されます。</span><span class="sxs-lookup"><span data-stu-id="4334b-115">If you're new to Teams and just getting started, by default, all apps are allowed in the global policy.</span></span> <span data-ttu-id="4334b-116">これには、Microsoft、サードパーティ、および組織によって公開されたアプリが含まれます。</span><span class="sxs-lookup"><span data-stu-id="4334b-116">This includes apps published by Microsoft, third-parties, and your organization.</span></span>

<span data-ttu-id="4334b-117">たとえば、すべてのサード パーティ製アプリをブロックし、組織内の人事チームに Microsoft の特定のアプリを許可するとします。</span><span class="sxs-lookup"><span data-stu-id="4334b-117">Say, for example, you want to block all third-party apps and allow specific apps from Microsoft for the HR team in your organization.</span></span> <span data-ttu-id="4334b-118">最初に、[アプリの管理][](manage-apps.md)ページに移動し、人事チームに許可するアプリが組織レベルで許可されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="4334b-118">First, you would go to the [Manage apps](manage-apps.md) page and make sure that the apps that you want to allow for the HR team are allowed at the org level.</span></span> <span data-ttu-id="4334b-119">次に、HR アプリのアクセス許可ポリシーというカスタム ポリシーを作成し、それをブロックし、必要なアプリを許可し、人事チームのユーザーに割り当てる設定を行います。</span><span class="sxs-lookup"><span data-stu-id="4334b-119">Then, create a custom policy named HR App Permission Policy, set it to block and allow the apps that you want, and assign it to users on the HR team.</span></span>

> [!NOTE]
> <span data-ttu-id="4334b-120">Microsoft 365 Government Community Cloud (GCC) 環境に Teams を展開した場合は [、「Microsoft 365 Government](#manage-org-wide-app-settings-for-microsoft-365-government) の組織全体のアプリ設定を管理する」を参照して、GCC 固有のサード パーティ製アプリ設定の詳細を確認してください。</span><span class="sxs-lookup"><span data-stu-id="4334b-120">If you deployed Teams in a Microsoft 365 Government Community Cloud (GCC) environment, see [Manage org-wide app settings for Microsoft 365 Government](#manage-org-wide-app-settings-for-microsoft-365-government) to learn more about third-party app settings that are unique to GCC.</span></span>

## <a name="create-a-custom-app-permission-policy"></a><span data-ttu-id="4334b-121">カスタム アプリのアクセス許可ポリシーを作成する</span><span class="sxs-lookup"><span data-stu-id="4334b-121">Create a custom app permission policy</span></span>

<span data-ttu-id="4334b-122">組織内のユーザーのグループごとに使用できるアプリを制御する場合は、1 つ以上のカスタム アプリのアクセス許可ポリシーを作成して割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="4334b-122">If you want to control the apps that are available for different groups of users in your organization, create and assign one or more custom app permission policies.</span></span> <span data-ttu-id="4334b-123">アプリが Microsoft、サードパーティ、または組織によって発行されたかどうかに基づいて、個別のカスタム ポリシーを作成して割り当てできます。</span><span class="sxs-lookup"><span data-stu-id="4334b-123">You can create and assign separate custom policies based on whether apps are published by Microsoft, third-parties, or your organization.</span></span> <span data-ttu-id="4334b-124">カスタム ポリシーを作成した後、組織全体のアプリ設定でサード パーティ製アプリが無効になっている場合、ポリシーを変更することはできません。</span><span class="sxs-lookup"><span data-stu-id="4334b-124">It's important to know that after you create a custom policy, you can't change it if third-party apps are disabled in org-wide app settings.</span></span>

1. <span data-ttu-id="4334b-125">Microsoft Teams 管理センターの左側のナビゲーションで **、Teams** アプリのアクセス許可ポリシー  >  **に移動します**。</span><span class="sxs-lookup"><span data-stu-id="4334b-125">In the left navigation of the Microsoft Teams admin center, go to **Teams apps** > **Permission policies**.</span></span>
2. <span data-ttu-id="4334b-126">**[追加]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="4334b-126">Click **Add**.</span></span> <br>
    <span data-ttu-id="4334b-127">![新しいアプリのアクセス許可ポリシーのスクリーンショット](media/app-permission-policies-new-policy.png)</span><span class="sxs-lookup"><span data-stu-id="4334b-127">![Screenshot of new app permission policy](media/app-permission-policies-new-policy.png)</span></span>
3. <span data-ttu-id="4334b-128">ポリシーの名前と説明を入力します。</span><span class="sxs-lookup"><span data-stu-id="4334b-128">Enter a name and description for the policy.</span></span>
4. <span data-ttu-id="4334b-129">**[Microsoft アプリ]、[\*\*\*\*サードパーティ 製アプリ**]、および [**カスタム** アプリ] で、次のいずれかを選択します。</span><span class="sxs-lookup"><span data-stu-id="4334b-129">Under **Microsoft apps**, **Third-party apps**, and **Custom apps**, select one of the following:</span></span>

    - <span data-ttu-id="4334b-130">**すべてのアプリを許可する**</span><span class="sxs-lookup"><span data-stu-id="4334b-130">**Allow all apps**</span></span>
    - <span data-ttu-id="4334b-131">**特定のアプリを許可し、他のすべてのアプリをブロックする**</span><span class="sxs-lookup"><span data-stu-id="4334b-131">**Allow specific apps and block all others**</span></span>
    - <span data-ttu-id="4334b-132">**特定のアプリをブロックし、他のすべてのアプリを許可する**</span><span class="sxs-lookup"><span data-stu-id="4334b-132">**Block specific apps and allow all others**</span></span>
    - <span data-ttu-id="4334b-133">**すべてのアプリをブロックする**</span><span class="sxs-lookup"><span data-stu-id="4334b-133">**Block all apps**</span></span>

5. <span data-ttu-id="4334b-134">[特定のアプリを **許可し、他** のアプリをブロックする] を選択した場合は、許可するアプリを追加します。</span><span class="sxs-lookup"><span data-stu-id="4334b-134">If you selected **Allow specific apps and block others**, add the apps that you want to allow:</span></span>

    1. <span data-ttu-id="4334b-135">[アプリ **の許可] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="4334b-135">Select **Allow apps**.</span></span>
    1. <span data-ttu-id="4334b-136">許可するアプリを検索し、[追加] をクリック **します**。</span><span class="sxs-lookup"><span data-stu-id="4334b-136">Search for the apps that you want to allow, and then click **Add**.</span></span> <span data-ttu-id="4334b-137">検索結果は、アプリの発行元 **(Microsoft** アプリ、 **サードパーティ** 製アプリ、またはカスタム アプリ) に **フィルター処理されます**。</span><span class="sxs-lookup"><span data-stu-id="4334b-137">The search results are filtered to the app publisher (**Microsoft apps**, **Third-party apps**, or **Custom apps**).</span></span>
    1. <span data-ttu-id="4334b-138">アプリの一覧を選択したら、[許可] をクリック **します**。</span><span class="sxs-lookup"><span data-stu-id="4334b-138">When you've chosen the list of apps, click **Allow**.</span></span> 

6. <span data-ttu-id="4334b-139">同様に、[特定のアプリをブロック] を選択し、他のすべてのアプリを許可した場合は、ブロックするアプリを検索して追加し、[ブロック] をクリック **します**。</span><span class="sxs-lookup"><span data-stu-id="4334b-139">Similarly, if you selected **Block specific apps and allow all others**, search for and add the apps that you want to block, and then click **Block**.</span></span>
7. <span data-ttu-id="4334b-140">**[保存]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="4334b-140">Click **Save**.</span></span>

## <a name="edit-an-app-permission-policy"></a><span data-ttu-id="4334b-141">アプリのアクセス許可ポリシーを編集する</span><span class="sxs-lookup"><span data-stu-id="4334b-141">Edit an app permission policy</span></span>

<span data-ttu-id="4334b-142">Microsoft Teams 管理センターを使用して、作成したグローバル ポリシーやカスタム ポリシーなどのポリシーを編集できます。</span><span class="sxs-lookup"><span data-stu-id="4334b-142">You can use the Microsoft Teams admin center to edit a policy, including the global policy and custom policies that you create.</span></span>

1. <span data-ttu-id="4334b-143">Microsoft Teams 管理センターの左側のナビゲーションで **、Teams** アプリのアクセス許可ポリシー  >  **に移動します**。</span><span class="sxs-lookup"><span data-stu-id="4334b-143">In the left navigation of the Microsoft Teams admin center, go to **Teams apps** > **Permission policies**.</span></span>
2. <span data-ttu-id="4334b-144">ポリシー名の左側をクリックしてポリシーを選び、**[編集]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="4334b-144">Select the policy by clicking to the left of the policy name, and then click **Edit**.</span></span>
3. <span data-ttu-id="4334b-145">ここで、希望する変更を行います。</span><span class="sxs-lookup"><span data-stu-id="4334b-145">From here, make the changes that you want.</span></span> <span data-ttu-id="4334b-146">アプリの発行元に基づいて設定を管理し、許可/ブロック設定に基づいてアプリを追加および削除できます。</span><span class="sxs-lookup"><span data-stu-id="4334b-146">You can manage settings based on the app publisher and add and remove apps based on the allow/block setting.</span></span>
4. <span data-ttu-id="4334b-147">**[保存]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="4334b-147">Click **Save**.</span></span>

## <a name="assign-a-custom-app-permission-policy-to-users"></a><span data-ttu-id="4334b-148">カスタム アプリのアクセス許可ポリシーをユーザーに割り当てる</span><span class="sxs-lookup"><span data-stu-id="4334b-148">Assign a custom app permission policy to users</span></span>

[!INCLUDE [assign-policy](includes/assign-policy.md)]

## <a name="manage-org-wide-app-settings-for-microsoft-365-government"></a><span data-ttu-id="4334b-149">Microsoft 365 Government の組織全体のアプリ設定を管理する</span><span class="sxs-lookup"><span data-stu-id="4334b-149">Manage org-wide app settings for Microsoft 365 Government</span></span>  

<span data-ttu-id="4334b-150">Microsoft 365 Government - GCC での Teams の展開では、GCC に固有のサード パーティ製アプリの設定について、次の点を知る必要があります。</span><span class="sxs-lookup"><span data-stu-id="4334b-150">In a Microsoft 365 Government - GCC deployment of Teams, it's important to know the following about third-party app settings, which are unique to GCC.</span></span>

<span data-ttu-id="4334b-151">GCC では、既定では、すべてのサード パーティ製アプリがブロックされます。</span><span class="sxs-lookup"><span data-stu-id="4334b-151">In GCC, all third-party apps are blocked by default.</span></span> <span data-ttu-id="4334b-152">また、Microsoft Teams 管理センターのアプリのアクセス許可ポリシー ページでサード パーティ製アプリを管理する場合は、次の注意が必要です。</span><span class="sxs-lookup"><span data-stu-id="4334b-152">Additionally, you'll see the following note about managing third-party apps on the app permission policies page in the Microsoft Teams admin center.</span></span>

![GCC のアプリのアクセス許可ポリシーのスクリーンショット](media/app-permission-policies-gcc.png)

<span data-ttu-id="4334b-154">組織全体のアプリ設定を使用して、ユーザーがサードパーティ製アプリをインストールできるかどうかを制御します。</span><span class="sxs-lookup"><span data-stu-id="4334b-154">Use org-wide app settings to control whether users can install third-party apps.</span></span> <span data-ttu-id="4334b-155">組織全体のアプリ設定は、すべてのユーザーの動作を制御し、ユーザーに割り当てられている他のアプリのアクセス許可ポリシーを上書きします。</span><span class="sxs-lookup"><span data-stu-id="4334b-155">Org-wide app settings govern the behavior for all users and override any other app permission policies assigned to users.</span></span> <span data-ttu-id="4334b-156">これらのアプリを使用して、悪意のあるアプリや問題のあるアプリを制御できます。</span><span class="sxs-lookup"><span data-stu-id="4334b-156">You can use them to control malicious or problematic apps.</span></span>

1. <span data-ttu-id="4334b-157">[アクセス許可 **ポリシー] ページで** 、組織全体 **のアプリ設定を選択します**。</span><span class="sxs-lookup"><span data-stu-id="4334b-157">On the **Permission policies** page, select **Org-wide app settings**.</span></span> <span data-ttu-id="4334b-158">パネルで必要な設定を構成できます。</span><span class="sxs-lookup"><span data-stu-id="4334b-158">You can then configure the settings you want in the panel.</span></span>

    ![組織全体のアプリ設定のスクリーンショット](media/app-permission-policies-gcc-org-wide.png)
    
2. <span data-ttu-id="4334b-160">サード **パーティ製アプリの下で**、これらの設定をオフまたはオンにし、サード パーティ製アプリへのアクセスを制御します。</span><span class="sxs-lookup"><span data-stu-id="4334b-160">Under **Third-party apps**, turn off or turn on these settings to control access to third-party apps:</span></span>

    - <span data-ttu-id="4334b-161">**サード パーティ製アプリを許可** する: これにより、ユーザーがサード パーティ製アプリを使用できるかどうかが制御されます。</span><span class="sxs-lookup"><span data-stu-id="4334b-161">**Allow third-party apps**: This controls whether users can use third-party apps.</span></span> <span data-ttu-id="4334b-162">この設定をオフにすると、ユーザーはサードパーティ製アプリをインストールしたり使用したりすることはできません。</span><span class="sxs-lookup"><span data-stu-id="4334b-162">If you turn off this setting, your users won't be able to install or use any third-party apps.</span></span> <span data-ttu-id="4334b-163">Microsoft 365 Government - GCC での Teams の展開では、この設定は既定ではオフになっています。</span><span class="sxs-lookup"><span data-stu-id="4334b-163">In a Microsoft 365 Government - GCC deployment of Teams, this setting is off by default.</span></span>
    - <span data-ttu-id="4334b-164">**既定で、** ストアに公開された新しいサード パーティ製アプリを許可する: これにより、Teams アプリ ストアに公開された新しいサード パーティ製アプリが Teams で自動的に利用できるかどうかが制御されます。</span><span class="sxs-lookup"><span data-stu-id="4334b-164">**Allow any new third-party apps published to the store by default**: This controls whether new third-party apps that are published to the Teams app store become automatically available in Teams.</span></span> <span data-ttu-id="4334b-165">このオプションは、サードパーティ製アプリを許可する場合にのみ設定できます。</span><span class="sxs-lookup"><span data-stu-id="4334b-165">You can only set this option if you allow third-party apps.</span></span>

3. <span data-ttu-id="4334b-166">[ **ブロックするアプリ] で**、組織全体でブロックするアプリを追加します。</span><span class="sxs-lookup"><span data-stu-id="4334b-166">Under **Blocked apps**, add the apps you want to block across your organization.</span></span> <span data-ttu-id="4334b-167">Microsoft 365 Government - GCC での Teams の展開では、既定では、すべてのサード パーティ製アプリがこのリストに追加されます。</span><span class="sxs-lookup"><span data-stu-id="4334b-167">In a Microsoft 365 Government - GCC deployment of Teams, all third-party apps are added to this list by default.</span></span> <span data-ttu-id="4334b-168">組織内で許可するサード パーティ製アプリの場合は、このブロックするアプリの一覧からアプリを削除します。</span><span class="sxs-lookup"><span data-stu-id="4334b-168">For any third-party app you want to allow in your organization, remove the app from this blocked apps list.</span></span> <span data-ttu-id="4334b-169">組織全体でアプリをブロックすると、アプリのアクセス許可ポリシーで許可されているかどうかに関係なく、すべてのユーザーに対してアプリが自動的にブロックされます。</span><span class="sxs-lookup"><span data-stu-id="4334b-169">When you block an app org-wide, the app is automatically blocked for all your users, regardless of whether it's allowed in any app permission policies</span></span>
4. <span data-ttu-id="4334b-170">組織 **全体の** アプリ設定を有効にするには、[保存] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="4334b-170">Click **Save** for org-wide app settings to take effect.</span></span>

<span data-ttu-id="4334b-171">前述のように、サード パーティ製アプリを許可するには、グローバル (組織全体の既定) ポリシーを編集して使用するか、カスタム ポリシーを作成して割り当てるかのいずれかです。</span><span class="sxs-lookup"><span data-stu-id="4334b-171">As mentioned earlier, to allow third-party apps, you can either edit and use the global (Org-wide default) policy or create and assign custom policies.</span></span>

## <a name="faq"></a><span data-ttu-id="4334b-172">FAQ</span><span class="sxs-lookup"><span data-stu-id="4334b-172">FAQ</span></span>

### <a name="working-with-app-permission-policies"></a><span data-ttu-id="4334b-173">アプリのアクセス許可ポリシーを使用する</span><span class="sxs-lookup"><span data-stu-id="4334b-173">Working with app permission policies</span></span>

#### <a name="what-app-interactions-do-permission-policies-affect"></a><span data-ttu-id="4334b-174">アクセス許可ポリシーが影響を与えるアプリの相互作用</span><span class="sxs-lookup"><span data-stu-id="4334b-174">What app interactions do permission policies affect?</span></span>
<span data-ttu-id="4334b-175">アクセス許可ポリシーは、エンド ユーザーのインストール、検出、操作を制御することで、アプリの使用状況を制御します。</span><span class="sxs-lookup"><span data-stu-id="4334b-175">Permission policies govern app usage by controlling installation, discovery, and interaction for end users.</span></span> <span data-ttu-id="4334b-176">管理者は、割り当てられているアクセス許可ポリシーに関係なく、Microsoft Teams 管理センターでアプリを管理できます。</span><span class="sxs-lookup"><span data-stu-id="4334b-176">Admins can still manage apps in the Microsoft Teams admin center regardless of the permission policies assigned to them.</span></span>

#### <a name="can-i-control-line-of-business-lob-apps"></a><span data-ttu-id="4334b-177">業務 (LOB) アプリを制御できますか?</span><span class="sxs-lookup"><span data-stu-id="4334b-177">Can I control line of business (LOB) apps?</span></span>
<span data-ttu-id="4334b-178">はい、アプリのアクセス許可ポリシーを使用して、カスタム (LOB) アプリの展開と配布を制御できます。</span><span class="sxs-lookup"><span data-stu-id="4334b-178">Yes, you can use app permission policies to control the rollout and distribution of custom (LOB) apps.</span></span> <span data-ttu-id="4334b-179">カスタム ポリシーを作成するか、グローバル ポリシーを編集して、組織のニーズに基づいてカスタム アプリを許可またはブロックすることができます。</span><span class="sxs-lookup"><span data-stu-id="4334b-179">You can create a custom policy or edit the global policy to allow or block custom apps based on the needs of your organization.</span></span>

#### <a name="how-do-app-permission-policies-relate-to-pinned-apps-and-app-setup-policies"></a><span data-ttu-id="4334b-180">アプリのアクセス許可ポリシーとピン留めされたアプリとアプリセットアップ ポリシーの関連付け</span><span class="sxs-lookup"><span data-stu-id="4334b-180">How do app permission policies relate to pinned apps and app setup policies?</span></span>

<span data-ttu-id="4334b-181">アプリのセットアップ ポリシーとアプリのアクセス許可ポリシーを組み合わせて使用できます。</span><span class="sxs-lookup"><span data-stu-id="4334b-181">You can use app setup policies together with app permission policies.</span></span> <span data-ttu-id="4334b-182">事前にピン留めされたアプリは、ユーザーに対して有効なアプリのセットから選択されます。</span><span class="sxs-lookup"><span data-stu-id="4334b-182">Pre-pinned apps are selected from the set of enabled apps for a user.</span></span> <span data-ttu-id="4334b-183">さらに、ユーザーがアプリのセットアップ ポリシーでアプリをブロックするアプリのアクセス許可ポリシーを持っている場合、そのアプリは Teams に表示されません。</span><span class="sxs-lookup"><span data-stu-id="4334b-183">Additionally, if a user has an app permission policy that blocks an app in their app setup policy, that app won't appear in Teams.</span></span>

#### <a name="can-i-use-app-permission-policies-to-restrict-uploading-custom-apps"></a><span data-ttu-id="4334b-184">アプリのアクセス許可ポリシーを使用してカスタム アプリのアップロードを制限できますか?</span><span class="sxs-lookup"><span data-stu-id="4334b-184">Can I use app permission policies to restrict uploading custom apps?</span></span>

<span data-ttu-id="4334b-185">組織全体の設定を [アプリの管理] ページまたはアプリ設定ポリシーで使用して、組織のカスタム アプリのアップロードを制限できます。</span><span class="sxs-lookup"><span data-stu-id="4334b-185">You can use org-wide settings on the **Manage apps** page, or app setup policies to restrict uploading custom apps for your organization.</span></span>  

<span data-ttu-id="4334b-186">特定のユーザーによるカスタム アプリのアップロードを制限するには、カスタム アプリ ポリシーを使用します。</span><span class="sxs-lookup"><span data-stu-id="4334b-186">To restrict specific users from uploading custom apps, use custom app policies.</span></span> <span data-ttu-id="4334b-187">詳細については、「Teams でカスタム [アプリのポリシーと設定を管理する」を参照してください](teams-custom-app-policies-and-settings.md)。</span><span class="sxs-lookup"><span data-stu-id="4334b-187">To learn more, see [Manage custom app policies and settings in Teams](teams-custom-app-policies-and-settings.md).</span></span>

#### <a name="does-blocking-an-app-apply-to-teams-mobile-clients"></a><span data-ttu-id="4334b-188">アプリのブロックは Teams モバイル クライアントに適用されますか?</span><span class="sxs-lookup"><span data-stu-id="4334b-188">Does blocking an app apply to Teams mobile clients?</span></span>

<span data-ttu-id="4334b-189">はい、アプリをブロックすると、そのアプリはすべての Teams クライアントでブロックされます。</span><span class="sxs-lookup"><span data-stu-id="4334b-189">Yes, when you block an app, that app is blocked across all Teams clients.</span></span>  

### <a name="user-experience"></a><span data-ttu-id="4334b-190">ユーザー エクスペリエンス</span><span class="sxs-lookup"><span data-stu-id="4334b-190">User experience</span></span>

#### <a name="what-does-a-user-experience-when-an-app-is-blocked"></a><span data-ttu-id="4334b-191">アプリがブロックされた場合のユーザー エクスペリエンス</span><span class="sxs-lookup"><span data-stu-id="4334b-191">What does a user experience when an app is blocked?</span></span>

<span data-ttu-id="4334b-192">ブロックされたアプリや、ボット、タブ、メッセージング拡張機能などの機能をユーザーが操作できない。</span><span class="sxs-lookup"><span data-stu-id="4334b-192">Users can't interact with a blocked app or its capabilities, such bots, tabs, and messaging extensions.</span></span> <span data-ttu-id="4334b-193">チームチャットやグループ チャットなどの共有コンテキストでは、ボットは引き続きそのコンテキストのすべての参加者にメッセージを送信できます。</span><span class="sxs-lookup"><span data-stu-id="4334b-193">In a shared context, such as a team or group chat, bots can still send messages to all participants of that context.</span></span> <span data-ttu-id="4334b-194">Teams は、アプリがブロックされた場合にユーザーに示します。</span><span class="sxs-lookup"><span data-stu-id="4334b-194">Teams indicates to the user when an app is blocked.</span></span>

<span data-ttu-id="4334b-195">たとえば、アプリがブロックされた場合、ユーザーは次の操作を行えなされません。</span><span class="sxs-lookup"><span data-stu-id="4334b-195">For example, when an app is blocked, users can't do any of the following:</span></span>

- <span data-ttu-id="4334b-196">アプリを個人またはチャットまたはチームに追加する</span><span class="sxs-lookup"><span data-stu-id="4334b-196">Add the app personally or to a chat or team</span></span>
- <span data-ttu-id="4334b-197">アプリのボットにメッセージを送信する</span><span class="sxs-lookup"><span data-stu-id="4334b-197">Send messages to the app’s bot</span></span>
- <span data-ttu-id="4334b-198">アクション可能なメッセージなど、アプリに情報を送り返すボタン アクションを実行する</span><span class="sxs-lookup"><span data-stu-id="4334b-198">Perform button actions that send information back to the app, such as actionable messages</span></span>  
- <span data-ttu-id="4334b-199">アプリのタブを表示する</span><span class="sxs-lookup"><span data-stu-id="4334b-199">View the app’s tab</span></span>
- <span data-ttu-id="4334b-200">通知を受信するコネクタを設定する</span><span class="sxs-lookup"><span data-stu-id="4334b-200">Set up connectors to receive notifications</span></span>
- <span data-ttu-id="4334b-201">アプリのメッセージング拡張機能を使用する</span><span class="sxs-lookup"><span data-stu-id="4334b-201">Use the app’s messaging extension</span></span>

<span data-ttu-id="4334b-202">従来のポータルでは、組織レベルでアプリを制御する許可がありました。つまり、アプリがブロックされた場合、アプリは組織内のすべてのユーザーに対してブロックされます。</span><span class="sxs-lookup"><span data-stu-id="4334b-202">The legacy portal allowed controlling apps at the organization level, which means when an app is blocked, it's blocked for all users in the organization.</span></span> <span data-ttu-id="4334b-203">[アプリの管理] ページで [アプリをブロックする](manage-apps.md) 方法は、まったく同じです。</span><span class="sxs-lookup"><span data-stu-id="4334b-203">Blocking an app on the [Manage apps](manage-apps.md) page works exactly the same way.</span></span>

<span data-ttu-id="4334b-204">特定のユーザーに割り当てられたアプリのアクセス許可ポリシーの場合、ボットまたはコネクタ機能を持つアプリが許可され、その後ブロックされた場合、アプリが共有コンテキスト内の一部のユーザーに対してのみ許可されている場合、そのアプリへのアクセス許可を持つグループ チャットまたはチャネルのメンバーは、ボットまたはコネクタによって投稿されたメッセージ履歴とメッセージを表示できます。を選択します。ただし、対話操作は行えな</span><span class="sxs-lookup"><span data-stu-id="4334b-204">For app permission policies assigned to specific users, if an app with bot or connector capability was allowed and then blocked, and if the app is then allowed only for some users in a shared context, members of a group chat or channel that don't have permission to that app can see the message history and messages that were posted by the bot or connector, but can't interact with it.</span></span>

## <a name="related-topics"></a><span data-ttu-id="4334b-205">関連項目</span><span class="sxs-lookup"><span data-stu-id="4334b-205">Related topics</span></span>

[<span data-ttu-id="4334b-206">Teams でのアプリの管理設定</span><span class="sxs-lookup"><span data-stu-id="4334b-206">Admin settings for apps in Teams</span></span>](admin-settings.md)

[<span data-ttu-id="4334b-207"> Teams でユーザーにポリシーを割り当てる</span><span class="sxs-lookup"><span data-stu-id="4334b-207">Assign policies to your users in Teams</span></span>](assign-policies.md)
