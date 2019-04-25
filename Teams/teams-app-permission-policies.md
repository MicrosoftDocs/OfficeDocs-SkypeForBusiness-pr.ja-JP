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
ms.audience: Admin
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Help
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
description: マイクロソフトのチームとを使用してどのようなアプリケーションは、組織内のユーザーの使用を制御する方法でアプリケーションのアクセス許可のポリシーについて説明します。
f1keywords:
- ms.teamsadmincenter.apppolicies.overview
ms.openlocfilehash: 8c35871fde876e01bba1ad8a843cd25fa0174c8d
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "32225151"
---
# <a name="manage-app-permission-policies-in-microsoft-teams"></a><span data-ttu-id="6fc09-103">Microsoft Teams のアプリのアクセス許可ポリシーを管理する</span><span class="sxs-lookup"><span data-stu-id="6fc09-103">Manage app permission policies in Microsoft Teams</span></span>

> [!INCLUDE [feature coming soon](includes/new-feature-coming-soon-article.md)]

<span data-ttu-id="6fc09-104">、管理者としては、マイクロソフトのチームのユーザーが組織内で使用できるどのようなアプリケーションを制御するのにアプリケーションのアクセス許可ポリシーを使用できます。</span><span class="sxs-lookup"><span data-stu-id="6fc09-104">As an admin, you can use app permission policies to control what apps are available to Microsoft Teams users in your organization.</span></span> <span data-ttu-id="6fc09-105">許可またはすべてのアプリケーションまたは Microsoft によって発行された特定のアプリケーションをブロックするサード ・ パーティ、および組織。</span><span class="sxs-lookup"><span data-stu-id="6fc09-105">You can allow or block all apps or specific apps published by Microsoft, third-parties, and your organization.</span></span> <span data-ttu-id="6fc09-106">アプリケーションをブロックすると、ユーザーはチームのアプリケーション ストアからダウンロードしてインストールすることではありません。</span><span class="sxs-lookup"><span data-stu-id="6fc09-106">When you block an app, users are unable to install it from the Teams app store.</span></span>

<span data-ttu-id="6fc09-107">マイクロソフトのチームの管理センターでのアプリケーションのアクセス許可ポリシーを管理します。</span><span class="sxs-lookup"><span data-stu-id="6fc09-107">You manage app permission policies in the Microsoft Teams admin center.</span></span> <span data-ttu-id="6fc09-108">組織全体の設定を適用、グローバル (組織全体の既定値) ポリシーを使用し、作成してカスタム ポリシーを個々 のユーザーまたはグループのユーザーに割り当てます。</span><span class="sxs-lookup"><span data-stu-id="6fc09-108">You can apply settings org-wide, use the global (Org-wide default) policy, and create and assign custom policies to individual users or users in a group.</span></span>  

![アプリケーションのアクセス許可ポリシーのスクリーン ショット](media/app-permission-policies.png)

> [!NOTE]
> <span data-ttu-id="6fc09-110">組織内のユーザーを作成し、カスタム ・ ポリシーを設定しない限り、グローバル ポリシーが自動的に表示されます。</span><span class="sxs-lookup"><span data-stu-id="6fc09-110">Users in your organization will automatically get the global policy unless you create and assign a custom policy.</span></span> <span data-ttu-id="6fc09-111">組織全体にわたるアプリケーションの設定は、グローバル ポリシーと、カスタム ・ ポリシーを作成し、ユーザーへの割り当てをオーバーライドします。</span><span class="sxs-lookup"><span data-stu-id="6fc09-111">Org-wide app settings override the global policy and any custom policies that you create and assign to users.</span></span>

<span data-ttu-id="6fc09-112">答えると、たとえば、すべてのサード ・ パーティ製アプリケーションをブロックし、マイクロソフトの人事チーム、組織内の特定のアプリケーションを許可します。</span><span class="sxs-lookup"><span data-stu-id="6fc09-112">Say, for example, you want to block all third-party apps and allow specific apps from Microsoft for the HR team in your organization.</span></span> <span data-ttu-id="6fc09-113">HR アプリケーションのアクセス許可ポリシーをという名前のカスタム ポリシーを作成、ブロックし、必要なアプリケーションを許可するように設定して、人事チームのユーザーに割り当てます。</span><span class="sxs-lookup"><span data-stu-id="6fc09-113">You would create a custom policy named HR App Permission Policy, set it to block and allow the apps that you want, and then assign it to users on the HR team.</span></span>

## <a name="manage-org-wide-app-settings"></a><span data-ttu-id="6fc09-114">組織全体にわたるアプリケーションの設定を管理します。</span><span class="sxs-lookup"><span data-stu-id="6fc09-114">Manage org-wide app settings</span></span>

<span data-ttu-id="6fc09-115">どのアプリケーションは、組織全体で利用可能なコントロールを組織全体にわたるアプリケーションの設定を使用します。</span><span class="sxs-lookup"><span data-stu-id="6fc09-115">Use org-wide app settings to control which apps are available across your organization.</span></span> <span data-ttu-id="6fc09-116">組織全体にわたるアプリケーションの設定は、すべてのユーザーの動作を制御し、ユーザーに割り当てられている他のすべてのアプリケーションのアクセス許可ポリシーをオーバーライドします。</span><span class="sxs-lookup"><span data-stu-id="6fc09-116">Org-wide app settings govern the behavior for all users and override any other app permission policies assigned to users.</span></span> <span data-ttu-id="6fc09-117">組織全体にわたるアプリケーションの設定は直ちに適用され、悪意のあるまたは問題のあるアプリケーションを制御するために使用できます。</span><span class="sxs-lookup"><span data-stu-id="6fc09-117">Org-wide app settings take effect immediately and you can use them to control malicious or problematic apps.</span></span>

1. <span data-ttu-id="6fc09-118">マイクロソフトのチーム管理センターの左側のナビゲーションでは、**チームのアプリケーション**に移動 > **のアクセス許可ポリシー**です。</span><span class="sxs-lookup"><span data-stu-id="6fc09-118">In the left navigation of the Microsoft Teams admin center, go to **Teams app** > **Permission policies**.</span></span>
2. <span data-ttu-id="6fc09-119">**組織全体の設定**を選択します。</span><span class="sxs-lookup"><span data-stu-id="6fc09-119">Select **Org-wide settings**.</span></span> <span data-ttu-id="6fc09-120">パネルで、目的の設定を構成できます。</span><span class="sxs-lookup"><span data-stu-id="6fc09-120">You can then configure the settings you want in the panel.</span></span> 
<span data-ttu-id="6fc09-121">![組織全体にわたるアプリケーションの設定のスクリーン ショット](media/app-permission-policies-org-wide-settings.png)</span><span class="sxs-lookup"><span data-stu-id="6fc09-121">![Screen shot of org-wide app settings](media/app-permission-policies-org-wide-settings.png)</span></span>
3. <span data-ttu-id="6fc09-122">**サード ・ パーティ製のアプリケーション**では、[無効にするか、サード ・ パーティ製のアプリケーションへのアクセスを制御するためのこれらの設定を有効にします。</span><span class="sxs-lookup"><span data-stu-id="6fc09-122">Under **Third-party apps**, turn off or turn on these settings to control access to third-party apps:</span></span>

    - <span data-ttu-id="6fc09-123">**チームでサード ・ パーティ製アプリケーションを許可する**: これは、ユーザーがサードパーティ製アプリケーションを使用できるかどうかを制御します。</span><span class="sxs-lookup"><span data-stu-id="6fc09-123">**Allow third-party apps in Teams**: This controls whether users can use third-party apps.</span></span>
    - <span data-ttu-id="6fc09-124">**新しいサード ・ パーティ製アプリケーションが既定のストアに公開を許可する**: このチームに自動的に利用可能になるチームのアプリケーションに公開されている新しいサード ・ パーティ製アプリケーションを格納するかどうかを制御します。</span><span class="sxs-lookup"><span data-stu-id="6fc09-124">**Allow any new third-party apps published to the store by default**: This controls whether new third-party apps that are published to the Teams app store become automatically available in Teams.</span></span> <span data-ttu-id="6fc09-125">サード ・ パーティ製のアプリケーションを許可する場合にのみ、このオプションを設定できます。</span><span class="sxs-lookup"><span data-stu-id="6fc09-125">You can only set this option if you allow third-party apps.</span></span>

4. <span data-ttu-id="6fc09-126">**カスタム アプリケーション**では、[オフにするか、**カスタム アプリケーションと相互作用を許可する**を有効にします。</span><span class="sxs-lookup"><span data-stu-id="6fc09-126">Under **Custom apps**, turn off or turn on **Allow interaction with custom apps**.</span></span> <span data-ttu-id="6fc09-127">この設定は、ユーザーが、(sideloaded) のカスタム アプリケーションと対話できるかどうかを制御します。</span><span class="sxs-lookup"><span data-stu-id="6fc09-127">This setting controls whether users can interact with custom (sideloaded) apps.</span></span> <span data-ttu-id="6fc09-128">これはカスタム アプリケーションのユーザーが*アップロード*を許可することに留意してください。</span><span class="sxs-lookup"><span data-stu-id="6fc09-128">Keep in mind that this is different from allowing users to *upload* custom apps.</span></span>
5. <span data-ttu-id="6fc09-129">**ブロックのアプリケーション**では、[検索し、組織全体をブロックするアプリケーションを追加します。</span><span class="sxs-lookup"><span data-stu-id="6fc09-129">Under **Blocked apps**, search for and add the apps that you want to block across your organization.</span></span> <span data-ttu-id="6fc09-130">テナント アプリケーション カタログまたはチームのアプリケーション ストアからアプリケーションを選択できます。</span><span class="sxs-lookup"><span data-stu-id="6fc09-130">You can choose apps from the tenant app catalog or the Teams app store.</span></span>
6. <span data-ttu-id="6fc09-131">有効にするために組織全体にわたるアプリケーションの設定の**保存**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6fc09-131">Click **Save** for org-wide app settings to take effect.</span></span>

## <a name="create-a-custom-app-permission-policy"></a><span data-ttu-id="6fc09-132">カスタム アプリケーションのアクセス許可ポリシーを作成します。</span><span class="sxs-lookup"><span data-stu-id="6fc09-132">Create a custom app permission policy</span></span>

<span data-ttu-id="6fc09-133">ユーザーが組織内の別のグループで利用可能なアプリケーションを制御する場合は、作成し、1 つまたは複数のカスタム アプリケーションのアクセス許可ポリシーを割り当てます。</span><span class="sxs-lookup"><span data-stu-id="6fc09-133">If you want to control the apps that are available for different groups of users in your organization, create and assign one or more custom app permission policies.</span></span> <span data-ttu-id="6fc09-134">作成し、Microsoft がアプリケーションを発行するかどうかに基づいて別のカスタム ポリシーを割り当てることができます第三者、または組織。</span><span class="sxs-lookup"><span data-stu-id="6fc09-134">You can create and assign separate custom policies based on whether apps are published by Microsoft, third-parties, or your organization.</span></span> <span data-ttu-id="6fc09-135">カスタム ポリシーを作成したら、変更することできません、サード ・ パーティ製のアプリケーションは、組織全体の設定で無効になっている場合を知っているが重要です。</span><span class="sxs-lookup"><span data-stu-id="6fc09-135">It's important to know that after you create a custom policy, you can't change it if third-party apps are disabled in org-wide settings.</span></span> 

1. <span data-ttu-id="6fc09-136">マイクロソフトのチーム管理センターの左側のナビゲーションでは、**チームのアプリケーション**に移動 > **のアクセス許可ポリシー**です。</span><span class="sxs-lookup"><span data-stu-id="6fc09-136">In the left navigation of the Microsoft Teams admin center, go to **Teams app** > **Permission policies**.</span></span>
2. <span data-ttu-id="6fc09-137">**新しいポリシー**を選択します。</span><span class="sxs-lookup"><span data-stu-id="6fc09-137">Select **New policy**.</span></span>
    <span data-ttu-id="6fc09-138">![新しいアプリケーションのアクセス許可ポリシーのスクリーン ショット](media/app-permission-policies-new-policy.png)</span><span class="sxs-lookup"><span data-stu-id="6fc09-138">![Screen shot of new app permission policy](media/app-permission-policies-new-policy.png)</span></span>
3. <span data-ttu-id="6fc09-139">ポリシーのわかりやすい名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="6fc09-139">Enter a descriptive name for the policy.</span></span>
4. <span data-ttu-id="6fc09-140">[ **Microsoft アプリケーション**、**サード パーティ製のアプリケーション**では、**テナントのアプリケーション**には、次のいずれかを選択します。</span><span class="sxs-lookup"><span data-stu-id="6fc09-140">Under **Microsoft apps**, **Third-party apps**, and **Tenant apps**, select one of the following:</span></span>

    - <span data-ttu-id="6fc09-141">**すべてのアプリケーションを許可します。**</span><span class="sxs-lookup"><span data-stu-id="6fc09-141">**Allow all apps**</span></span>
    - <span data-ttu-id="6fc09-142">**特定のアプリケーションを許可し、他のすべてのユーザーをブロックします。**</span><span class="sxs-lookup"><span data-stu-id="6fc09-142">**Allow specific apps and block all others**</span></span>
    - <span data-ttu-id="6fc09-143">**特定のアプリケーションをブロックし、他のすべてのユーザーを許可します。**</span><span class="sxs-lookup"><span data-stu-id="6fc09-143">**Block specific apps and allow all others**</span></span>
    - <span data-ttu-id="6fc09-144">**すべてのアプリケーションをブロックします。**</span><span class="sxs-lookup"><span data-stu-id="6fc09-144">**Block all apps**</span></span>

5. <span data-ttu-id="6fc09-145">**特定のアプリケーションを許可し他のユーザーをブロック**] を選択した場合は、許可するアプリケーションを追加します。</span><span class="sxs-lookup"><span data-stu-id="6fc09-145">If you selected **Allow specific apps and block others**, add the apps that you want to allow:</span></span>

    1. <span data-ttu-id="6fc09-146">**アプリケーションを許可する**を選択します。</span><span class="sxs-lookup"><span data-stu-id="6fc09-146">Select **Allow apps**.</span></span>
    1. <span data-ttu-id="6fc09-147">許可、し、[**追加**] をクリックするアプリケーションを検索します。</span><span class="sxs-lookup"><span data-stu-id="6fc09-147">Search for the apps that you want to allow, and then click **Add**.</span></span> <span data-ttu-id="6fc09-148">アプリケーションの発行元 (**マイクロソフトのアプリケーション**や**サード ・ パーティ製のアプリケーション**では、**テナントのアプリケーション**) には、検索結果がフィルター処理されます。</span><span class="sxs-lookup"><span data-stu-id="6fc09-148">The search results are filtered to the app publisher (**Microsoft apps**, **Third-party apps**, or **Tenant apps**).</span></span>
    1. <span data-ttu-id="6fc09-149">アプリケーションの一覧を選択したら、[**許可**を] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6fc09-149">When you've chosen the list of apps, click **Allow**.</span></span>

6. <span data-ttu-id="6fc09-150">同様に、**特定のアプリケーションをブロックし他のすべてのユーザーを許可する**] を選択した場合は、検索し、ブロックするアプリケーションを追加します。</span><span class="sxs-lookup"><span data-stu-id="6fc09-150">Similarly, if you selected **Block specific apps and allow all others**, search for and add the apps that you want to block.</span></span>
7. <span data-ttu-id="6fc09-151">**[保存]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6fc09-151">Click **Save**.</span></span>

## <a name="edit-an-app-permission-policy"></a><span data-ttu-id="6fc09-152">アプリケーションのアクセス許可ポリシーを編集します。</span><span class="sxs-lookup"><span data-stu-id="6fc09-152">Edit an app permission policy</span></span>

<span data-ttu-id="6fc09-153">グローバル (組織) のポリシー、カスタム ポリシーを作成するなど、ポリシーを編集するのには、マイクロソフトのチームの管理センターを使用できます。</span><span class="sxs-lookup"><span data-stu-id="6fc09-153">You can use the Microsoft Teams admin center to edit a policy, including the global (Org-wide default) policy and custom policies that you create.</span></span> 

1. <span data-ttu-id="6fc09-154">マイクロソフトのチーム管理センターの左側のナビゲーションでは、**チームのアプリケーション**に移動 > **のアクセス許可ポリシー**です。</span><span class="sxs-lookup"><span data-stu-id="6fc09-154">In the left navigation of the Microsoft Teams admin center, go to **Teams app** > **Permission policies**.</span></span>
2. <span data-ttu-id="6fc09-155">編集するポリシーを選択します。</span><span class="sxs-lookup"><span data-stu-id="6fc09-155">Select the policy you want to edit.</span></span>
3. <span data-ttu-id="6fc09-156">ここでは、変更します。</span><span class="sxs-lookup"><span data-stu-id="6fc09-156">From here, make the changes that you want.</span></span> <span data-ttu-id="6fc09-157">ベースのアプリケーションのパブリッシャーの設定を管理し、追加し、許可/禁止の設定に基づくアプリケーションを削除できます。</span><span class="sxs-lookup"><span data-stu-id="6fc09-157">You can manage settings based on the app publisher and add and remove apps based on the allow/block setting.</span></span>
4. <span data-ttu-id="6fc09-158">**[保存]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6fc09-158">Click **Save**.</span></span>

## <a name="assign-a-custom-app-permission-policy-to-users"></a><span data-ttu-id="6fc09-159">カスタム アプリケーションのアクセス許可ポリシーをユーザーに割り当てる</span><span class="sxs-lookup"><span data-stu-id="6fc09-159">Assign a custom app permission policy to users</span></span>

<span data-ttu-id="6fc09-160">カスタム ポリシーを個々 のユーザーまたはセキュリティ グループまたは配布グループのすべてのユーザーなど、複数のユーザーにカスタム ポリシーを割り当てるには、ビジネスの PowerShell モジュールの Skype を割り当てるには、マイクロソフトのチームの管理センターを使用できます。</span><span class="sxs-lookup"><span data-stu-id="6fc09-160">You can use the Microsoft Teams admin center to assign a custom policy to individual users or the Skype for Business PowerShell module to assign a custom policy to multiple users, such as all users in a security group or distribution group.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="6fc09-161">PowerShell を使用して、ユーザーにポリシーを割り当てることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="6fc09-161">We recommend using PowerShell only to assign policies to users.</span></span> <span data-ttu-id="6fc09-162">作成、編集、およびポリシーを管理するには、マイクロソフトのチームの管理センターを使用します。</span><span class="sxs-lookup"><span data-stu-id="6fc09-162">Use the Microsoft Teams admin center to create, edit, and manage policies.</span></span>

### <a name="assign-a-custom-app-permission-policy-to-individual-users"></a><span data-ttu-id="6fc09-163">カスタム アプリケーションのアクセス許可ポリシーを個々 のユーザーに割り当てる</span><span class="sxs-lookup"><span data-stu-id="6fc09-163">Assign a custom app permission policy to individual users</span></span>

1. <span data-ttu-id="6fc09-164">Microsoft Teams 管理センターの左側のナビゲーションで、**[ユーザー]** に移動してユーザーをクリックします。</span><span class="sxs-lookup"><span data-stu-id="6fc09-164">In the left navigation of the Microsoft Teams admin center, go to **Users**, and then click the user.</span></span>
2. <span data-ttu-id="6fc09-165">**[割り当てられているポリシー]** の隣にある **[編集]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="6fc09-165">Next to **Assigned policies**, choose **Edit**.</span></span>
3. <span data-ttu-id="6fc09-166">**アプリケーションのアクセス許可ポリシー**では、割り当てる、アプリケーションのアクセス許可ポリシーを選択し、**保存**します。</span><span class="sxs-lookup"><span data-stu-id="6fc09-166">Under **App permission policy**, select the app permission policy you want to assign, and then choose **Save**.</span></span>

    ![アプリケーションのセットアップのアクセス許可の割り当て-policy.png](media/app-permission-policies-assign-policy.png)

<span data-ttu-id="6fc09-168">割り当てることも、アプリケーションのアクセス許可ポリシーを 1 つまたは複数のユーザーとして次のように。</span><span class="sxs-lookup"><span data-stu-id="6fc09-168">You can also assign an app permission policy to one or more users as follows:</span></span>

1. <span data-ttu-id="6fc09-169">**マイクロソフトのチーム管理センター**を参照して > **チームのアプリ** > **のアクセス許可ポリシー**です。</span><span class="sxs-lookup"><span data-stu-id="6fc09-169">Go to **Microsoft Teams admin center** > **Teams apps** > **Permission policies**.</span></span>
2. <span data-ttu-id="6fc09-170">ポリシーを選択するには、ポリシー名の左側にクリックします。</span><span class="sxs-lookup"><span data-stu-id="6fc09-170">Select the policy by clicking to the left of the policy name.</span></span>
3. <span data-ttu-id="6fc09-171">**ユーザーの管理**を選択します。</span><span class="sxs-lookup"><span data-stu-id="6fc09-171">Select **Manage users**.</span></span>
4. <span data-ttu-id="6fc09-172">**ユーザーの管理**ウィンドウで、表示名、ユーザー名、ユーザーの検索、名を選択し、[**追加**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6fc09-172">In the **Manage users** pane, search for the user by display name or by user name, select the name, and then select **Add**.</span></span> <span data-ttu-id="6fc09-173">追加するユーザーごとにこの手順を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="6fc09-173">Repeat this step for each user that you want to add.</span></span>
5. <span data-ttu-id="6fc09-174">ユーザーの追加が完了したら、[**保存**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="6fc09-174">When you are finished adding users, select **Save**.</span></span>
 

### <a name="assign-a-custom-app-permission-policy-to-users-in-a-group"></a><span data-ttu-id="6fc09-175">グループ内のユーザーにアプリケーションのカスタム アクセス許可ポリシーを割り当てる</span><span class="sxs-lookup"><span data-stu-id="6fc09-175">Assign a custom app permission policy to users in a group</span></span>

<span data-ttu-id="6fc09-176">既に認められた複数のユーザーがカスタム アプリケーションのアクセス許可ポリシーを割り当てるにはすることがあります。</span><span class="sxs-lookup"><span data-stu-id="6fc09-176">You may want to assign a custom app permission policy to multiple users that you’ve already identified.</span></span> <span data-ttu-id="6fc09-177">などのセキュリティ グループ内のすべてのユーザーにポリシーを設定する場合があります。</span><span class="sxs-lookup"><span data-stu-id="6fc09-177">For example, you may want to assign a policy to all users in a security group.</span></span> <span data-ttu-id="6fc09-178">グラフ モジュールの Azure Active Directory PowerShell およびビジネスの PowerShell モジュールの Skype への接続で、これを行うことができます。</span><span class="sxs-lookup"><span data-stu-id="6fc09-178">You can do this by connecting to the Azure Active Directory PowerShell for Graph module and the Skype for Business PowerShell module.</span></span> <span data-ttu-id="6fc09-179">PowerShell を使用して Teams を管理する方法の詳細については、「[Teams での PowerShell の概要](teams-powershell-overview.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6fc09-179">For more information about using PowerShell to manage Teams, see [Teams PowerShell Overview](teams-powershell-overview.md).</span></span>

<span data-ttu-id="6fc09-180">この例では、contoso 社の製薬会社の人事プロジェクト グループ内のすべてのユーザーに HR アプリケーションのアクセス許可ポリシーと呼ばれるカスタム アプリケーションのアクセス許可ポリシーを割り当てます。</span><span class="sxs-lookup"><span data-stu-id="6fc09-180">In this example, we assign a custom app permission policy called HR App Permission Policy to all users in the Contoso Pharmaceuticals HR Project group.</span></span>  

> [!NOTE]
> <span data-ttu-id="6fc09-181">「[単一の Windows PowerShell ウィンドウですべての Office 365 サービスに接続する](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-all-office-365-services-in-a-single-windows-powershell-window)」の手順に従って、必ず最初に Azure Active Directory PowerShell for Graph モジュールと Skype for Business PowerShell モジュールに接続してください。</span><span class="sxs-lookup"><span data-stu-id="6fc09-181">Make sure you first connect to the Azure Active Directory PowerShell for Graph module and Skype for Business PowerShell module by following the steps in [Connect to all Office 365 services in a single Windows PowerShell window](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-all-office-365-services-in-a-single-windows-powershell-window).</span></span>

<span data-ttu-id="6fc09-182">特定のグループの GroupObjectId を取得します。</span><span class="sxs-lookup"><span data-stu-id="6fc09-182">Get the GroupObjectId of the particular group.</span></span>
```
$group = Get-AzureADGroup -SearchString "Contoso Pharmaceuticals HR Project"
```
<span data-ttu-id="6fc09-183">指定したグループのメンバーを取得します。</span><span class="sxs-lookup"><span data-stu-id="6fc09-183">Get the members of the specified group.</span></span>
```
$members = Get-AzureADGroupMember -ObjectId $group.ObjectId -All $true | Where-Object {$_.ObjectType -eq "User"}
```
<span data-ttu-id="6fc09-184">グループ内のすべてのユーザーを特定のアプリケーションのアクセス許可ポリシーを割り当てます。</span><span class="sxs-lookup"><span data-stu-id="6fc09-184">Assign all users in the group to a particular app permission policy.</span></span> <span data-ttu-id="6fc09-185">この例では、HR アプリケーションのアクセス許可ポリシーを勧めします。</span><span class="sxs-lookup"><span data-stu-id="6fc09-185">In this example, it's HR App Permission Policy.</span></span>
```
$members | ForEach-Object { Grant-CsTeamsAppPermissionPolicy -PolicyName "HR App Permission Policy" -Identity $_.EmailAddress}
``` 
<span data-ttu-id="6fc09-186">グループ内のメンバー数によっては、このコマンドの実行に数分かかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="6fc09-186">Depending on the number of members in the group, this command may take several minutes to execute.</span></span>

## <a name="faq"></a><span data-ttu-id="6fc09-187">FAQ</span><span class="sxs-lookup"><span data-stu-id="6fc09-187">FAQ</span></span>

### <a name="working-with-app-permission-policies"></a><span data-ttu-id="6fc09-188">アプリケーションのアクセス許可ポリシーを使用します。</span><span class="sxs-lookup"><span data-stu-id="6fc09-188">Working with app permission policies</span></span>

#### <a name="can-i-control-line-of-business-lob-apps"></a><span data-ttu-id="6fc09-189">基幹業務 (LOB) アプリケーションを制御することができますか。</span><span class="sxs-lookup"><span data-stu-id="6fc09-189">Can I control line of business (LOB) apps?</span></span>

<span data-ttu-id="6fc09-190">はい、ロールアウトおよびカスタム (LOB) アプリケーションの配布を制御するのにアプリケーションのアクセス許可ポリシーを使用できます。</span><span class="sxs-lookup"><span data-stu-id="6fc09-190">Yes, you can use app permission policies to control the rollout and distribution of custom (LOB) apps.</span></span>

#### <a name="how-do-app-permission-policies-relate-to-pinned-apps-and-app-setup-policies"></a><span data-ttu-id="6fc09-191">固定されたアプリケーションおよびアプリケーション設定のポリシーをアプリケーションのアクセス許可ポリシーを関連付ける方法はでしょうか。</span><span class="sxs-lookup"><span data-stu-id="6fc09-191">How do app permission policies relate to pinned apps and app setup policies?</span></span>

<span data-ttu-id="6fc09-192">アプリケーションのアクセス許可ポリシーとアプリケーション設定のポリシーを使用することができます。</span><span class="sxs-lookup"><span data-stu-id="6fc09-192">You can use app setup policies together with app permission policies.</span></span> <span data-ttu-id="6fc09-193">事前に固定されているアプリケーションは、ユーザーの有効なアプリケーションのセットから選択されます。</span><span class="sxs-lookup"><span data-stu-id="6fc09-193">Pre-pinned apps are selected from the set of enabled apps for a user.</span></span> <span data-ttu-id="6fc09-194">さらに、ユーザーにアプリケーションの設定ポリシーでアプリケーションをブロックするアプリケーションのアクセス許可ポリシーがある場合は、そのアプリケーションがチームに表示されません。</span><span class="sxs-lookup"><span data-stu-id="6fc09-194">Additionally, if a user has an app permission policy that blocks an app in their app setup policy, that app won't appear in Teams.</span></span>

#### <a name="can-i-use-app-permission-policies-to-restrict-uploading-custom-apps-also-known-as-sideloading"></a><span data-ttu-id="6fc09-195">カスタム アプリケーション (sideloading とも呼ばれます) のアップロードを制限するためにアプリケーションのアクセス許可ポリシーを使用できますか。</span><span class="sxs-lookup"><span data-stu-id="6fc09-195">Can I use app permission policies to restrict uploading custom apps (also known as sideloading)?</span></span>

<span data-ttu-id="6fc09-196">カスタム アプリケーションのアップロードを制限する方法の詳細については、[カスタム アプリケーションのポリシーを管理しチームの設定](teams-custom-app-policies-and-settings.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6fc09-196">To learn more about how to restrict uploading custom apps, see [Manage custom app policies and settings in Teams](teams-custom-app-policies-and-settings.md).</span></span>

#### <a name="how-long-does-it-take-for-policy-changes-to-take-effect"></a><span data-ttu-id="6fc09-197">ポリシーの変更を有効にするためにどのくらい時間がかかりますか。</span><span class="sxs-lookup"><span data-stu-id="6fc09-197">How long does it take for policy changes to take effect?</span></span>

<span data-ttu-id="6fc09-198">グローバル ポリシーを編集した場合、またはユーザーにポリシーを設定した後、変更を反映させるには、最大で 24 時間がかかります。</span><span class="sxs-lookup"><span data-stu-id="6fc09-198">After you edit the global policy or assign a policy to users, it can take up to 24 hours for changes to take effect.</span></span> <span data-ttu-id="6fc09-199">組織全体にわたるアプリケーションの設定は直ちに有効にします。</span><span class="sxs-lookup"><span data-stu-id="6fc09-199">Org-wide app settings take effect immediately.</span></span>

#### <a name="does-blocking-an-app-apply-to-teams-mobile-clients"></a><span data-ttu-id="6fc09-200">アプリケーションをブロックする、チームのモバイル クライアントに適用しますか。</span><span class="sxs-lookup"><span data-stu-id="6fc09-200">Does blocking an app apply to Teams mobile clients?</span></span>

<span data-ttu-id="6fc09-201">はい、アプリを禁止すると、そのアプリケーションはチームのすべてのクライアント間でブロックされます。</span><span class="sxs-lookup"><span data-stu-id="6fc09-201">Yes, when you block an app, that app is blocked across all Teams clients.</span></span>  

### <a name="user-experience"></a><span data-ttu-id="6fc09-202">ユーザー エクスペリエンス</span><span class="sxs-lookup"><span data-stu-id="6fc09-202">User experience</span></span>

#### <a name="what-does-a-user-experience-when-an-app-is-blocked"></a><span data-ttu-id="6fc09-203">内容はユーザーが発生するアプリケーションがブロックされたときですか。</span><span class="sxs-lookup"><span data-stu-id="6fc09-203">What does a user experience when an app is blocked?</span></span>

<span data-ttu-id="6fc09-204">ユーザーは、ブロックされているアプリケーションやその機能、そのようなボット、タブ、およびメッセージングの拡張機能と対話できません。</span><span class="sxs-lookup"><span data-stu-id="6fc09-204">Users can't interact with a blocked app or its capabilities, such bots, tabs, and messaging extensions.</span></span> <span data-ttu-id="6fc09-205">チームまたはグループのチャットなどの共有コンテキストの bot がそのコンテキストのすべての参加者のメッセージを送信することもできます。</span><span class="sxs-lookup"><span data-stu-id="6fc09-205">In a shared context, such as a team or group chat, bots can still send messages to all participants of that context.</span></span> <span data-ttu-id="6fc09-206">チームは、アプリケーションがブロックされたとき、ユーザーに指示します。</span><span class="sxs-lookup"><span data-stu-id="6fc09-206">Teams indicates to the user when an app is blocked.</span></span> 

<span data-ttu-id="6fc09-207">などのアプリケーションがブロックされると、ユーザーできません操作を行います次のいずれか。</span><span class="sxs-lookup"><span data-stu-id="6fc09-207">For example, when an app is blocked, users can't do any of the following:</span></span>

- <span data-ttu-id="6fc09-208">個人またはチャットには、アプリケーションを追加またはチーム</span><span class="sxs-lookup"><span data-stu-id="6fc09-208">Add the app personally or to a chat or team</span></span>
- <span data-ttu-id="6fc09-209">アプリケーションの下辺にメッセージを送信します。</span><span class="sxs-lookup"><span data-stu-id="6fc09-209">Send messages to the app’s bot</span></span>
- <span data-ttu-id="6fc09-210">実践的なメッセージなど、アプリケーションに情報を送信するボタンの操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="6fc09-210">Perform button actions that send information back to the app, such as actionable messages</span></span>  
- <span data-ttu-id="6fc09-211">アプリケーションのタブを表示します。</span><span class="sxs-lookup"><span data-stu-id="6fc09-211">View the app’s tab</span></span>
- <span data-ttu-id="6fc09-212">通知を受信するコネクタを設定します。</span><span class="sxs-lookup"><span data-stu-id="6fc09-212">Set up connectors to receive notifications</span></span>
- <span data-ttu-id="6fc09-213">アプリケーションのメッセージングの拡張機能を使用します。</span><span class="sxs-lookup"><span data-stu-id="6fc09-213">Use the app’s messaging extension</span></span>

 ## <a name="related-topics"></a><span data-ttu-id="6fc09-214">関連トピック</span><span class="sxs-lookup"><span data-stu-id="6fc09-214">Related topics</span></span>
- [<span data-ttu-id="6fc09-215">Teams でのアプリの管理設定</span><span class="sxs-lookup"><span data-stu-id="6fc09-215">Admin settings for apps in Teams</span></span>](admin-settings.md)
- [<span data-ttu-id="6fc09-216">Teams のアプリのセットアップ ポリシーを管理する</span><span class="sxs-lookup"><span data-stu-id="6fc09-216">Manage app setup policies in Teams</span></span>](teams-app-setup-policies.md)
- [<span data-ttu-id="6fc09-217">Teams のカスタム アプリのポリシーと設定を管理する</span><span class="sxs-lookup"><span data-stu-id="6fc09-217">Manage custom app policies and settings in Teams</span></span>](teams-custom-app-policies-and-settings.md)
