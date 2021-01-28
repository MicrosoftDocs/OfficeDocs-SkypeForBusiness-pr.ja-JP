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
description: Microsoft Teams のアプリ許可ポリシーと、それらを使用して組織内のユーザーが使用できるアプリを制御する方法について説明します。
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.apppermspolicies.overview
- ms.teamsadmincenter.appsetuppolicies.addpinnedapp.permissions
- ms.teamsadmincenter.apppermspolicies.orgwideapps.customapps
- ms.teamsadmincenter.appsetuppolicies.overview
ms.openlocfilehash: aa11b21405079ab26bf1fa9572eb203560c4e461
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49802497"
---
# <a name="manage-app-permission-policies-in-microsoft-teams"></a><span data-ttu-id="c8c60-103">Microsoft Teams のアプリのアクセス許可ポリシーを管理する</span><span class="sxs-lookup"><span data-stu-id="c8c60-103">Manage app permission policies in Microsoft Teams</span></span>

<span data-ttu-id="c8c60-104">管理者であれば、アプリのアクセス許可ポリシーを使用して、組織の Microsoft Teams ユーザーが使用できるアプリを制御できます。</span><span class="sxs-lookup"><span data-stu-id="c8c60-104">As an admin, you can use app permission policies to control what apps are available to Microsoft Teams users in your organization.</span></span> <span data-ttu-id="c8c60-105">すべてのアプリ、または Microsoft、第三者、お客様の組織によって公開されている特定のアプリを許可またはブロックすることができます。</span><span class="sxs-lookup"><span data-stu-id="c8c60-105">You can allow or block all apps or specific apps published by Microsoft, third-parties, and your organization.</span></span> <span data-ttu-id="c8c60-106">アプリをブロックした場合、ポリシーを持つユーザーは、Teams アプリ ストアからアプリをインストールできません。</span><span class="sxs-lookup"><span data-stu-id="c8c60-106">When you block an app, users who have the policy are unable to install it from the Teams app store.</span></span> <span data-ttu-id="c8c60-107">これらのポリシーを管理するには、グローバル管理者または Teams サービス管理者である必要があります。</span><span class="sxs-lookup"><span data-stu-id="c8c60-107">You must be a global admin or Teams service admin to manage these policies.</span></span>

<span data-ttu-id="c8c60-108">アプリのアクセス許可ポリシーは、Microsoft Teams 管理センターで管理します。</span><span class="sxs-lookup"><span data-stu-id="c8c60-108">You manage app permission policies in the Microsoft Teams admin center.</span></span> <span data-ttu-id="c8c60-109">グローバル (組織全体の既定) ポリシーを使用ことも、カスタム ポリシーを作成して割り当てることもできます。</span><span class="sxs-lookup"><span data-stu-id="c8c60-109">You can use the global (Org-wide default) policy or create and assign custom policies.</span></span> <span data-ttu-id="c8c60-110">カスタム ポリシーを作成して割り当てていない場合、組織内のユーザーにはグローバル ポリシーが自動的に適用されます。</span><span class="sxs-lookup"><span data-stu-id="c8c60-110">Users in your organization will automatically get the global policy unless you create and assign a custom policy.</span></span> <span data-ttu-id="c8c60-111">ポリシーを編集既するか割り当てた後、変更が反映されるまでに数時間かかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="c8c60-111">After you edit or assign a policy, it can take a few hours for changes to take effect.</span></span>

![アプリのアクセス許可ポリシーのスクリーンショット](media/app-permission-policies.png)

> [!NOTE]
> <span data-ttu-id="c8c60-113">組織全体のアプリ設定は、グローバル ポリシーや、お客様が作成してユーザーに割り当てるカスタム ポリシーを上書きします。</span><span class="sxs-lookup"><span data-stu-id="c8c60-113">Org-wide app settings override the global policy and any custom policies that you create and assign to users.</span></span>

<span data-ttu-id="c8c60-114">組織がすでに Teams に参加している場合、Microsoft 365 管理センターの **テナント全体の設定** で構成したアプリ設定は、[[アプリの管理]](manage-apps.md) ページの組織全体のアプリ設定に反映されます。</span><span class="sxs-lookup"><span data-stu-id="c8c60-114">If your organization is already on Teams, the app settings you configured in **Tenant-wide settings** in the Microsoft 365 admin center are reflected in org-wide app settings on the [Manage apps](manage-apps.md) page.</span></span> <span data-ttu-id="c8c60-115">Teams を初めて使用し、始めたばかりの場合、既定では、すべてのアプリがグローバル ポリシーで許可されています。</span><span class="sxs-lookup"><span data-stu-id="c8c60-115">If you're new to Teams and just getting started, by default, all apps are allowed in the global policy.</span></span> <span data-ttu-id="c8c60-116">これには、Microsoft、サードパーティ、および組織が公開したアプリが含まれます。</span><span class="sxs-lookup"><span data-stu-id="c8c60-116">This includes apps published by Microsoft, third-parties, and your organization.</span></span>

<span data-ttu-id="c8c60-117">たとえば、すべてのサードパーティ アプリをブロックし、組織内のHR チームに Microsoft の特定のアプリを許可するとします。</span><span class="sxs-lookup"><span data-stu-id="c8c60-117">Say, for example, you want to block all third-party apps and allow specific apps from Microsoft for the HR team in your organization.</span></span> <span data-ttu-id="c8c60-118">まず、[[アプリの管理]](manage-apps.md) ページに移動し、HR チームに許可するアプリが組織レベルで許可されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="c8c60-118">First, you would go to the [Manage apps](manage-apps.md) page and make sure that the apps that you want to allow for the HR team are allowed at the org level.</span></span> <span data-ttu-id="c8c60-119">次に、HR App Permission Policy という名前のカスタムポリシーを作成し、必要なアプリをブロックして許可するように設定し、HR チームのユーザーに割り当てます。</span><span class="sxs-lookup"><span data-stu-id="c8c60-119">Then, create a custom policy named HR App Permission Policy, set it to block and allow the apps that you want, and assign it to users on the HR team.</span></span>

> [!NOTE]
> <span data-ttu-id="c8c60-120">Teams を Microsoft 365 Government Community Cloud (GCC) 環境に展開した場合は、「[Microsoft 365 Government の組織全体のアプリ設定の管理](#manage-org-wide-app-settings-for-microsoft-365-government)」を参照して、GCC に固有のサードパーティ アプリ設定の詳細を確認してください。</span><span class="sxs-lookup"><span data-stu-id="c8c60-120">If you deployed Teams in a Microsoft 365 Government Community Cloud (GCC) environment, see [Manage org-wide app settings for Microsoft 365 Government](#manage-org-wide-app-settings-for-microsoft-365-government) to learn more about third-party app settings that are unique to GCC.</span></span>

## <a name="create-a-custom-app-permission-policy"></a><span data-ttu-id="c8c60-121">カスタムアプリのアクセス許可ポリシーを作成する</span><span class="sxs-lookup"><span data-stu-id="c8c60-121">Create a custom app permission policy</span></span>

<span data-ttu-id="c8c60-122">組織内のユーザー グループごとに利用できるアプリを制御する場合は、1 つ以上のカスタムアプリ権限ポリシーを作成して割り当てます。</span><span class="sxs-lookup"><span data-stu-id="c8c60-122">If you want to control the apps that are available for different groups of users in your organization, create and assign one or more custom app permission policies.</span></span> <span data-ttu-id="c8c60-123">アプリが Microsoft、サードパーティ、または組織のうちどこで公開されているかに基づいて、個別のカスタム ポリシーを作成し、割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="c8c60-123">You can create and assign separate custom policies based on whether apps are published by Microsoft, third-parties, or your organization.</span></span> <span data-ttu-id="c8c60-124">カスタムポリシーを作成した後、組織全体のアプリ設定でサード パーティのアプリが無効になっている場合、ポリシーを変更できないのでご注意ください。</span><span class="sxs-lookup"><span data-stu-id="c8c60-124">It's important to know that after you create a custom policy, you can't change it if third-party apps are disabled in org-wide app settings.</span></span>

1. <span data-ttu-id="c8c60-125">Microsoft Teams 管理センターの左側のナビゲーションで、**[Teams アプリ]** > **[アクセス許可ポリシー]** の順に移動します。</span><span class="sxs-lookup"><span data-stu-id="c8c60-125">In the left navigation of the Microsoft Teams admin center, go to **Teams apps** > **Permission policies**.</span></span>
2. <span data-ttu-id="c8c60-126">**[追加]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c8c60-126">Click **Add**.</span></span> <br>
    <span data-ttu-id="c8c60-127">![新しいアプリのアクセス許可ポリシーのスクリーン ショット](media/app-permission-policies-new-policy.png)</span><span class="sxs-lookup"><span data-stu-id="c8c60-127">![Screenshot of new app permission policy](media/app-permission-policies-new-policy.png)</span></span>
3. <span data-ttu-id="c8c60-128">ポリシーの名前と説明を入力します。</span><span class="sxs-lookup"><span data-stu-id="c8c60-128">Enter a name and description for the policy.</span></span>
4. <span data-ttu-id="c8c60-129">**[Microsoft アプリ]**、**[サードパーティアプリ]**、および **[カスタムアプリ]** で、次のいずれかを選択します。</span><span class="sxs-lookup"><span data-stu-id="c8c60-129">Under **Microsoft apps**, **Third-party apps**, and **Custom apps**, select one of the following:</span></span>

    - <span data-ttu-id="c8c60-130">**すべてのアプリを許可する**</span><span class="sxs-lookup"><span data-stu-id="c8c60-130">**Allow all apps**</span></span>
    - <span data-ttu-id="c8c60-131">**特定のアプリを許可し、他のすべてのアプリを禁止する**</span><span class="sxs-lookup"><span data-stu-id="c8c60-131">**Allow specific apps and block all others**</span></span>
    - <span data-ttu-id="c8c60-132">**特定のアプリをブロックし、他のすべてのアプリを許可する**</span><span class="sxs-lookup"><span data-stu-id="c8c60-132">**Block specific apps and allow all others**</span></span>
    - <span data-ttu-id="c8c60-133">**[すべてのアプリをブロック]**</span><span class="sxs-lookup"><span data-stu-id="c8c60-133">**Block all apps**</span></span>

5. <span data-ttu-id="c8c60-134">**[特定のアプリを許可し、他のアプリをブロックする]** を選択した場合は、以下の手順で許可するアプリを追加します。</span><span class="sxs-lookup"><span data-stu-id="c8c60-134">If you selected **Allow specific apps and block others**, add the apps that you want to allow:</span></span>

    1. <span data-ttu-id="c8c60-135">**[アプリを許可]** を選びます。</span><span class="sxs-lookup"><span data-stu-id="c8c60-135">Select **Allow apps**.</span></span>
    1. <span data-ttu-id="c8c60-136">許可するアプリを検索し、**[追加]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c8c60-136">Search for the apps that you want to allow, and then click **Add**.</span></span> <span data-ttu-id="c8c60-137">検索結果は、アプリの発行元 (**Microsoft アプリ**、**サードパーティ アプリ**、または **カスタム アプリ**) にフィルターされます。</span><span class="sxs-lookup"><span data-stu-id="c8c60-137">The search results are filtered to the app publisher (**Microsoft apps**, **Third-party apps**, or **Custom apps**).</span></span>
    1. <span data-ttu-id="c8c60-138">アプリのリストを選択したら、**[許可]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c8c60-138">When you've chosen the list of apps, click **Allow**.</span></span> 

6. <span data-ttu-id="c8c60-139">同様に、**[特定のアプリをブロックして他のすべてのアプリを許可する]** を選択した場合は、ブロックするアプリを検索して追加し、**[ブロック]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c8c60-139">Similarly, if you selected **Block specific apps and allow all others**, search for and add the apps that you want to block, and then click **Block**.</span></span>
7. <span data-ttu-id="c8c60-140">**[保存]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c8c60-140">Click **Save**.</span></span>

## <a name="edit-an-app-permission-policy"></a><span data-ttu-id="c8c60-141">アプリのアクセス許可ポリシーを編集する</span><span class="sxs-lookup"><span data-stu-id="c8c60-141">Edit an app permission policy</span></span>

<span data-ttu-id="c8c60-142">Microsoft Teams 管理センターを使用して、作成したグローバル ポリシーやカスタム ポリシーなどのポリシーを編集できます。</span><span class="sxs-lookup"><span data-stu-id="c8c60-142">You can use the Microsoft Teams admin center to edit a policy, including the global policy and custom policies that you create.</span></span>

1. <span data-ttu-id="c8c60-143">Microsoft Teams 管理センターの左側のナビゲーションで、**[Teams アプリ]** > **[アクセス許可ポリシー]** の順に移動します。</span><span class="sxs-lookup"><span data-stu-id="c8c60-143">In the left navigation of the Microsoft Teams admin center, go to **Teams apps** > **Permission policies**.</span></span>
2. <span data-ttu-id="c8c60-144">ポリシー名の左側をクリックしてポリシーを選び、**[編集]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c8c60-144">Select the policy by clicking to the left of the policy name, and then click **Edit**.</span></span>
3. <span data-ttu-id="c8c60-145">ここで、希望する変更を行います。</span><span class="sxs-lookup"><span data-stu-id="c8c60-145">From here, make the changes that you want.</span></span> <span data-ttu-id="c8c60-146">アプリの発行元に基づいて設定を管理し、許可/ブロック設定に基づいてアプリの追加や削除を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="c8c60-146">You can manage settings based on the app publisher and add and remove apps based on the allow/block setting.</span></span>
4. <span data-ttu-id="c8c60-147">**[保存]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c8c60-147">Click **Save**.</span></span>

## <a name="assign-a-custom-app-permission-policy-to-users"></a><span data-ttu-id="c8c60-148">カスタム アプリのアクセス許可ポリシーをユーザーに割り当てる</span><span class="sxs-lookup"><span data-stu-id="c8c60-148">Assign a custom app permission policy to users</span></span>

[!INCLUDE [assign-policy](includes/assign-policy.md)]

## <a name="manage-org-wide-app-settings-for-microsoft-365-government"></a><span data-ttu-id="c8c60-149">Microsoft 365 Government の組織全体のアプリ設定を管理する</span><span class="sxs-lookup"><span data-stu-id="c8c60-149">Manage org-wide app settings for Microsoft 365 Government</span></span>  

<span data-ttu-id="c8c60-150">Microsoft 365 Government - Teams の GCC 展開では、GCC に固有のサードパーティ アプリ設定について次のことを知っておくことが重要です。</span><span class="sxs-lookup"><span data-stu-id="c8c60-150">In a Microsoft 365 Government - GCC deployment of Teams, it's important to know the following about third-party app settings, which are unique to GCC.</span></span>

<span data-ttu-id="c8c60-151">GCC では、すべてのサードパーティ アプリが既定でブロックされています。</span><span class="sxs-lookup"><span data-stu-id="c8c60-151">In GCC, all third-party apps are blocked by default.</span></span> <span data-ttu-id="c8c60-152">さらに、Microsoft Teams 管理センターのアプリのアクセス許可ポリシー ページに、サードパーティ アプリの管理に関する次の注意事項が表示されます。</span><span class="sxs-lookup"><span data-stu-id="c8c60-152">Additionally, you'll see the following note about managing third-party apps on the app permission policies page in the Microsoft Teams admin center.</span></span>

![GCC 内のアプリのアクセス許可ポリシーのスクリーンショット](media/app-permission-policies-gcc.png)

<span data-ttu-id="c8c60-154">組織全体のアプリ設定を使用して、ユーザーがサード パーティのアプリをインストールできるかどうかを制御します。</span><span class="sxs-lookup"><span data-stu-id="c8c60-154">Use org-wide app settings to control whether users can install third-party apps.</span></span> <span data-ttu-id="c8c60-155">組織全体のアプリ設定は、すべてのユーザーの動作を管理し、ユーザーに割り当てられた他のアプリ権限ポリシーを上書きします。</span><span class="sxs-lookup"><span data-stu-id="c8c60-155">Org-wide app settings govern the behavior for all users and override any other app permission policies assigned to users.</span></span> <span data-ttu-id="c8c60-156">それらを使用して、悪意のあるアプリや問題のあるアプリを制御できます。</span><span class="sxs-lookup"><span data-stu-id="c8c60-156">You can use them to control malicious or problematic apps.</span></span>

1. <span data-ttu-id="c8c60-157">**[権限ポリシー]** ページで、**[組織全体のアプリ設定]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="c8c60-157">On the **Permission policies** page, select **Org-wide app settings**.</span></span> <span data-ttu-id="c8c60-158">次に、パネルで必要な設定を構成できます。</span><span class="sxs-lookup"><span data-stu-id="c8c60-158">You can then configure the settings you want in the panel.</span></span>

    ![組織全体のアプリ設定のスクリーンショット](media/app-permission-policies-gcc-org-wide.png)
    
2. <span data-ttu-id="c8c60-160">**[サードパーティ アプリ]** で、次の設定をオフまたはオンにして、サードパーティ アプリへのアクセスを制御します。</span><span class="sxs-lookup"><span data-stu-id="c8c60-160">Under **Third-party apps**, turn off or turn on these settings to control access to third-party apps:</span></span>

    - <span data-ttu-id="c8c60-161">**[サードパーティ アプリを許可する]**: ここで、ユーザーがサードパーティ アプリを使用できるかどうかを制御します。</span><span class="sxs-lookup"><span data-stu-id="c8c60-161">**Allow third-party apps**: This controls whether users can use third-party apps.</span></span> <span data-ttu-id="c8c60-162">この設定をオフにすると、ユーザーはサードパーティ アプリをインストールしたり使用したりできなくなります。</span><span class="sxs-lookup"><span data-stu-id="c8c60-162">If you turn off this setting, your users won't be able to install or use any third-party apps.</span></span> <span data-ttu-id="c8c60-163">Microsoft 365 Governmentの場合 - Teams の GCC 展開では、この設定は既定でオフになっています。</span><span class="sxs-lookup"><span data-stu-id="c8c60-163">In a Microsoft 365 Government - GCC deployment of Teams, this setting is off by default.</span></span>
    - <span data-ttu-id="c8c60-164">**ストアに公開された新しいサードパーティ アプリを既定で許可する**: ここでは、Teams アプリ ストアに公開された新しいサードパーティ アプリを Teams で自動的に利用可能にするかどうかを制御します。</span><span class="sxs-lookup"><span data-stu-id="c8c60-164">**Allow any new third-party apps published to the store by default**: This controls whether new third-party apps that are published to the Teams app store become automatically available in Teams.</span></span> <span data-ttu-id="c8c60-165">このオプションは、サードパーティのアプリを許可する場合にのみ設定できます。</span><span class="sxs-lookup"><span data-stu-id="c8c60-165">You can only set this option if you allow third-party apps.</span></span>

3. <span data-ttu-id="c8c60-166">**[ブロック済みのアプリ]** で、組織全体でブロックするアプリを追加します。</span><span class="sxs-lookup"><span data-stu-id="c8c60-166">Under **Blocked apps**, add the apps you want to block across your organization.</span></span> <span data-ttu-id="c8c60-167">Microsoft 365 Government の場合 - Teams の GCC 展開では、すべてのサードパーティ アプリが既定でこのリストに追加されます。</span><span class="sxs-lookup"><span data-stu-id="c8c60-167">In a Microsoft 365 Government - GCC deployment of Teams, all third-party apps are added to this list by default.</span></span> <span data-ttu-id="c8c60-168">組織で許可するサードパーティのアプリについては、このブロック済みのアプリのリストからアプリを削除します。</span><span class="sxs-lookup"><span data-stu-id="c8c60-168">For any third-party app you want to allow in your organization, remove the app from this blocked apps list.</span></span> <span data-ttu-id="c8c60-169">組織全体でアプリをブロックすると、アプリのアクセス許可ポリシーで許可されているかどうかに関係なく、アプリはすべてのユーザーに対して自動的にブロックされます</span><span class="sxs-lookup"><span data-stu-id="c8c60-169">When you block an app org-wide, the app is automatically blocked for all your users, regardless of whether it's allowed in any app permission policies</span></span>
4. <span data-ttu-id="c8c60-170">組織全体のアプリ設定を有効にするには、**[保存]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c8c60-170">Click **Save** for org-wide app settings to take effect.</span></span>

<span data-ttu-id="c8c60-171">前述のように、サードパーティのアプリを許可するには、グローバル (組織全体の既定) ポリシーを編集して使用するか、カスタム ポリシーを作成して割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="c8c60-171">As mentioned earlier, to allow third-party apps, you can either edit and use the global (Org-wide default) policy or create and assign custom policies.</span></span>

## <a name="faq"></a><span data-ttu-id="c8c60-172">よくあるご質問 (FAQ)</span><span class="sxs-lookup"><span data-stu-id="c8c60-172">FAQ</span></span>

### <a name="working-with-app-permission-policies"></a><span data-ttu-id="c8c60-173">アプリのアクセス許可ポリシーを操作する</span><span class="sxs-lookup"><span data-stu-id="c8c60-173">Working with app permission policies</span></span>

#### <a name="what-app-interactions-do-permission-policies-affect"></a><span data-ttu-id="c8c60-174">アクセス許可ポリシーはどのアプリの相互作用に影響しますか?</span><span class="sxs-lookup"><span data-stu-id="c8c60-174">What app interactions do permission policies affect?</span></span>
<span data-ttu-id="c8c60-175">アクセス許可ポリシーは、エンド ユーザーのインストール、検出、操作を制御することでアプリの使用を管理します。</span><span class="sxs-lookup"><span data-stu-id="c8c60-175">Permission policies govern app usage by controlling installation, discovery, and interaction for end users.</span></span> <span data-ttu-id="c8c60-176">管理者は、割り当てられたアクセス許可ポリシーに関係なく、Microsoft Teams 管理センターでアプリを管理できます。</span><span class="sxs-lookup"><span data-stu-id="c8c60-176">Admins can still manage apps in the Microsoft Teams admin center regardless of the permission policies assigned to them.</span></span>

#### <a name="can-i-control-line-of-business-lob-apps"></a><span data-ttu-id="c8c60-177">基幹業務 (LOB) アプリを制御できますか?</span><span class="sxs-lookup"><span data-stu-id="c8c60-177">Can I control line of business (LOB) apps?</span></span>
<span data-ttu-id="c8c60-178">はい。アプリのアクセス許可ポリシーを使用して、カスタム (LOB) アプリのロールアウトと配布を制御できます。</span><span class="sxs-lookup"><span data-stu-id="c8c60-178">Yes, you can use app permission policies to control the rollout and distribution of custom (LOB) apps.</span></span> <span data-ttu-id="c8c60-179">カスタム ポリシーを作成するか、グローバル ポリシーを編集して、組織のニーズに基づいてカスタム アプリを許可またはブロックできます。</span><span class="sxs-lookup"><span data-stu-id="c8c60-179">You can create a custom policy or edit the global policy to allow or block custom apps based on the needs of your organization.</span></span>

#### <a name="how-do-app-permission-policies-relate-to-pinned-apps-and-app-setup-policies"></a><span data-ttu-id="c8c60-180">アプリのアクセス許可ポリシーは、固定されたアプリおよびアプリの設定ポリシーにどのように関連していますか?</span><span class="sxs-lookup"><span data-stu-id="c8c60-180">How do app permission policies relate to pinned apps and app setup policies?</span></span>

<span data-ttu-id="c8c60-181">アプリの設定ポリシーは、アプリのアクセス許可ポリシーと一緒に使用できます。</span><span class="sxs-lookup"><span data-stu-id="c8c60-181">You can use app setup policies together with app permission policies.</span></span> <span data-ttu-id="c8c60-182">事前に固定されたアプリは、ユーザーに対して有効になっているアプリのセットから選択されます。</span><span class="sxs-lookup"><span data-stu-id="c8c60-182">Pre-pinned apps are selected from the set of enabled apps for a user.</span></span> <span data-ttu-id="c8c60-183">さらに、ユーザーがアプリの設定ポリシーでアプリをブロックするアプリのアクセス許可ポリシーを持っている場合、そのアプリは Teams に表示されません。</span><span class="sxs-lookup"><span data-stu-id="c8c60-183">Additionally, if a user has an app permission policy that blocks an app in their app setup policy, that app won't appear in Teams.</span></span>

#### <a name="can-i-use-app-permission-policies-to-restrict-uploading-custom-apps"></a><span data-ttu-id="c8c60-184">アプリのアクセス許可ポリシーを使用して、カスタム アプリのアップロードを制限できますか?</span><span class="sxs-lookup"><span data-stu-id="c8c60-184">Can I use app permission policies to restrict uploading custom apps?</span></span>

<span data-ttu-id="c8c60-185">**[アプリの管理]** ページの組織全体の設定、またはアプリの設定ポリシーを使用して、組織のカスタム アプリのアップロードを制限できます。</span><span class="sxs-lookup"><span data-stu-id="c8c60-185">You can use org-wide settings on the **Manage apps** page, or app setup policies to restrict uploading custom apps for your organization.</span></span>  

<span data-ttu-id="c8c60-186">特定のユーザーによるカスタム アプリのアップロードを制限するには、カスタムアプリ ポリシーを使用します。</span><span class="sxs-lookup"><span data-stu-id="c8c60-186">To restrict specific users from uploading custom apps, use custom app policies.</span></span> <span data-ttu-id="c8c60-187">詳細については、「[Teams のカスタム アプリのポリシーと設定を管理する](teams-custom-app-policies-and-settings.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="c8c60-187">To learn more, see [Manage custom app policies and settings in Teams](teams-custom-app-policies-and-settings.md).</span></span>

#### <a name="does-blocking-an-app-apply-to-teams-mobile-clients"></a><span data-ttu-id="c8c60-188">アプリのブロックは Teams モバイル クライアントに適用されますか?</span><span class="sxs-lookup"><span data-stu-id="c8c60-188">Does blocking an app apply to Teams mobile clients?</span></span>

<span data-ttu-id="c8c60-189">はい、アプリをブロックすると、そのアプリはすべての Teams クライアントでブロックされます。</span><span class="sxs-lookup"><span data-stu-id="c8c60-189">Yes, when you block an app, that app is blocked across all Teams clients.</span></span>  

### <a name="user-experience"></a><span data-ttu-id="c8c60-190">ユーザー エクスペリエンス</span><span class="sxs-lookup"><span data-stu-id="c8c60-190">User experience</span></span>

#### <a name="what-does-a-user-experience-when-an-app-is-blocked"></a><span data-ttu-id="c8c60-191">アプリがブロックされたとき、ユーザー エクスペリエンスはどうなりますか?</span><span class="sxs-lookup"><span data-stu-id="c8c60-191">What does a user experience when an app is blocked?</span></span>

<span data-ttu-id="c8c60-192">ユーザーは、ブロックされたアプリや、ボット、タブ、メッセージング拡張機能といった機能を操作できません。</span><span class="sxs-lookup"><span data-stu-id="c8c60-192">Users can't interact with a blocked app or its capabilities, such bots, tabs, and messaging extensions.</span></span> <span data-ttu-id="c8c60-193">チーム チャットやグループ チャットなどの共有コンテキストでは、ボットはそのコンテキストのすべての参加者に引き続きメッセージを送信できます。</span><span class="sxs-lookup"><span data-stu-id="c8c60-193">In a shared context, such as a team or group chat, bots can still send messages to all participants of that context.</span></span> <span data-ttu-id="c8c60-194">Teams は、アプリがブロックされたことをユーザーに知らせます。</span><span class="sxs-lookup"><span data-stu-id="c8c60-194">Teams indicates to the user when an app is blocked.</span></span>

<span data-ttu-id="c8c60-195">たとえば、アプリがブロックされている場合、ユーザーは次のいずれも実行できません。</span><span class="sxs-lookup"><span data-stu-id="c8c60-195">For example, when an app is blocked, users can't do any of the following:</span></span>

- <span data-ttu-id="c8c60-196">アプリの個人的な、またはチャットやチームへの追加</span><span class="sxs-lookup"><span data-stu-id="c8c60-196">Add the app personally or to a chat or team</span></span>
- <span data-ttu-id="c8c60-197">アプリのボットへのメッセージの送信</span><span class="sxs-lookup"><span data-stu-id="c8c60-197">Send messages to the app’s bot</span></span>
- <span data-ttu-id="c8c60-198">アクション可能なメッセージなど、情報をアプリに送り返すボタン アクションの実行</span><span class="sxs-lookup"><span data-stu-id="c8c60-198">Perform button actions that send information back to the app, such as actionable messages</span></span>  
- <span data-ttu-id="c8c60-199">アプリのタブを表示する</span><span class="sxs-lookup"><span data-stu-id="c8c60-199">View the app’s tab</span></span>
- <span data-ttu-id="c8c60-200">通知を受信するためのコネクタの設定</span><span class="sxs-lookup"><span data-stu-id="c8c60-200">Set up connectors to receive notifications</span></span>
- <span data-ttu-id="c8c60-201">アプリのメッセージング拡張機能の使用</span><span class="sxs-lookup"><span data-stu-id="c8c60-201">Use the app’s messaging extension</span></span>

<span data-ttu-id="c8c60-202">従来のポータルでは、組織レベルでアプリを制御できました。これはアプリがブロックされると、組織内のすべてのユーザーに対してブロックされることを意味します。</span><span class="sxs-lookup"><span data-stu-id="c8c60-202">The legacy portal allowed controlling apps at the organization level, which means when an app is blocked, it's blocked for all users in the organization.</span></span> <span data-ttu-id="c8c60-203">[[アプリの管理]](manage-apps.md) ページでアプリをブロックするのとまったく同じように機能します。</span><span class="sxs-lookup"><span data-stu-id="c8c60-203">Blocking an app on the [Manage apps](manage-apps.md) page works exactly the same way.</span></span>

<span data-ttu-id="c8c60-204">特定のユーザーに割り当てられたアプリのアクセス許可ポリシーで、ボットまたはコネクタ機能を備えたアプリを許可してからブロックした場合、およびアプリが共有コンテキスト内の一部のユーザーに対してのみ許可した場合、グループ チャットまたはチャネルのメンバーは許可されません そのアプリへのアクセス許可を持っている場合、ボットまたはコネクタによって投稿されたメッセージ履歴とメッセージを表示できますが、そのボットやコネクタと対話することはできません。</span><span class="sxs-lookup"><span data-stu-id="c8c60-204">For app permission policies assigned to specific users, if an app with bot or connector capability was allowed and then blocked, and if the app is then allowed only for some users in a shared context, members of a group chat or channel that don't have permission to that app can see the message history and messages that were posted by the bot or connector, but can't interact with it.</span></span>

## <a name="related-topics"></a><span data-ttu-id="c8c60-205">関連項目</span><span class="sxs-lookup"><span data-stu-id="c8c60-205">Related topics</span></span>

[<span data-ttu-id="c8c60-206">Teams でのアプリの管理設定</span><span class="sxs-lookup"><span data-stu-id="c8c60-206">Admin settings for apps in Teams</span></span>](admin-settings.md)

[<span data-ttu-id="c8c60-207"> Teams でユーザーにポリシーを割り当てる</span><span class="sxs-lookup"><span data-stu-id="c8c60-207">Assign policies to your users in Teams</span></span>](assign-policies.md)
