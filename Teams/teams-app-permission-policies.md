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
ms.openlocfilehash: b54a4263adc8e697a19f997ac34018e1e2b2c302
ms.sourcegitcommit: 1807ea5509f8efa6abba8462bce2f3646117e8bf
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/10/2020
ms.locfileid: "44691013"
---
# <a name="manage-app-permission-policies-in-microsoft-teams"></a><span data-ttu-id="ac00e-103">Microsoft Teams のアプリのアクセス許可ポリシーを管理する</span><span class="sxs-lookup"><span data-stu-id="ac00e-103">Manage app permission policies in Microsoft Teams</span></span>

<span data-ttu-id="ac00e-104">管理者であれば、アプリのアクセス許可ポリシーを使用して、組織の Microsoft Teams ユーザーが使用できるアプリを制御できます。</span><span class="sxs-lookup"><span data-stu-id="ac00e-104">As an admin, you can use app permission policies to control what apps are available to Microsoft Teams users in your organization.</span></span> <span data-ttu-id="ac00e-105">すべてのアプリ、または Microsoft、第三者、お客様の組織によって公開されている特定のアプリを許可またはブロックすることができます。</span><span class="sxs-lookup"><span data-stu-id="ac00e-105">You can allow or block all apps or specific apps published by Microsoft, third-parties, and your organization.</span></span> <span data-ttu-id="ac00e-106">アプリをブロックした場合、ポリシーを持つユーザーは、Teams アプリ ストアからアプリをインストールできません。</span><span class="sxs-lookup"><span data-stu-id="ac00e-106">When you block an app, users who have the policy are unable to install it from the Teams app store.</span></span> <span data-ttu-id="ac00e-107">これらのポリシーを管理するには、グローバル管理者または Teams サービス管理者である必要があります。</span><span class="sxs-lookup"><span data-stu-id="ac00e-107">You must be a global admin or Teams service admin to manage these policies.</span></span>

<span data-ttu-id="ac00e-108">アプリのアクセス許可ポリシーは、Microsoft Teams 管理センターで管理します。</span><span class="sxs-lookup"><span data-stu-id="ac00e-108">You manage app permission policies in the Microsoft Teams admin center.</span></span> <span data-ttu-id="ac00e-109">グローバル (組織全体の既定) ポリシーを使用するか、またはグループ内の個々のユーザーまたはユーザーにカスタムポリシーを作成して割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="ac00e-109">You can use the global (Org-wide default) policy or create and assign custom policies to individual users or users in a group.</span></span>  

![アプリのアクセス許可ポリシーのスクリーンショット](media/app-permission-policies.png)

> [!NOTE]
> <span data-ttu-id="ac00e-111">カスタム ポリシーを作成して割り当てていない場合、組織内のユーザーにはグローバル ポリシーが自動的に適用されます。</span><span class="sxs-lookup"><span data-stu-id="ac00e-111">Users in your organization will automatically get the global policy unless you create and assign a custom policy.</span></span> <span data-ttu-id="ac00e-112">組織全体のアプリ設定は、グローバルポリシーや、作成してユーザーに割り当てるカスタムポリシーを上書きします。</span><span class="sxs-lookup"><span data-stu-id="ac00e-112">Org-wide app settings override the global policy and any custom policies that you create and assign to users.</span></span>

<span data-ttu-id="ac00e-113">組織が既に Teams に登録されている場合は、Microsoft 365 管理センターの**テナント全体の設定**で構成したアプリ設定が、[アプリの[管理](manage-apps.md)] ページの組織全体のアプリの設定に反映されます。</span><span class="sxs-lookup"><span data-stu-id="ac00e-113">If your organization is already on Teams, the app settings you configured in **Tenant-wide settings** in the Microsoft 365 admin center are reflected in org-wide app settings on the [Manage apps](manage-apps.md) page.</span></span> <span data-ttu-id="ac00e-114">チームを初めて使い始めたばかりの場合は、既定ではすべてのアプリがグローバルポリシーで許可されています。</span><span class="sxs-lookup"><span data-stu-id="ac00e-114">If you're new to Teams and just getting started, by default, all apps are allowed in the global policy.</span></span> <span data-ttu-id="ac00e-115">これには、Microsoft、サードパーティ、組織によって公開されたアプリが含まれます。</span><span class="sxs-lookup"><span data-stu-id="ac00e-115">This includes apps published by Microsoft, third-parties, and your organization.</span></span>

<span data-ttu-id="ac00e-116">たとえば、すべてのサードパーティ製のアプリをブロックして、組織内の HR チーム向けに Microsoft が提供する特定のアプリを許可する必要があるとします。</span><span class="sxs-lookup"><span data-stu-id="ac00e-116">Say, for example, you want to block all third-party apps and allow specific apps from Microsoft for the HR team in your organization.</span></span> <span data-ttu-id="ac00e-117">最初に、[[アプリの管理](manage-apps.md)] ページに移動し、人事チームに許可するアプリが組織レベルで許可されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="ac00e-117">First, you would go to the [Manage apps](manage-apps.md) page and make sure that the apps that you want to allow for the HR team are allowed at the org level.</span></span> <span data-ttu-id="ac00e-118">次に、HR アプリのアクセス許可ポリシーという名前のカスタムポリシーを作成し、必要なアプリをブロックおよび許可するように設定し、人事チームのユーザーに割り当てます。</span><span class="sxs-lookup"><span data-stu-id="ac00e-118">Then, create a custom policy named HR App Permission Policy, set it to block and allow the apps that you want, and assign it to users on the HR team.</span></span>

> [!NOTE]
> <span data-ttu-id="ac00e-119">Microsoft 365 Government-GCC 環境に Teams を展開した場合は、「 [gcc のアプリのアクセス許可ポリシー](#app-permission-policies-for-gcc) 」を参照して、gcc に固有のサードパーティのアプリ設定の詳細を確認してください。</span><span class="sxs-lookup"><span data-stu-id="ac00e-119">If you deployed Teams in a Microsoft 365 Government - GCC environment, see [App permission policies for GCC](#app-permission-policies-for-gcc) to learn more about third-party app settings that are unique to GCC.</span></span>

## <a name="create-a-custom-app-permission-policy"></a><span data-ttu-id="ac00e-120">カスタムアプリのアクセス許可ポリシーを作成する</span><span class="sxs-lookup"><span data-stu-id="ac00e-120">Create a custom app permission policy</span></span>

<span data-ttu-id="ac00e-121">組織内のユーザーグループごとに使用できるアプリを制御する場合は、1つ以上のカスタムアプリのアクセス許可ポリシーを作成して割り当てます。</span><span class="sxs-lookup"><span data-stu-id="ac00e-121">If you want to control the apps that are available for different groups of users in your organization, create and assign one or more custom app permission policies.</span></span> <span data-ttu-id="ac00e-122">Microsoft、サードパーティ、または組織によってアプリが公開されるかどうかに基づいて、個別のカスタムポリシーを作成して割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="ac00e-122">You can create and assign separate custom policies based on whether apps are published by Microsoft, third-parties, or your organization.</span></span> <span data-ttu-id="ac00e-123">組織全体のアプリ設定でサードパーティ製のアプリが無効になっている場合は、カスタムポリシーを作成した後にそれを変更することはできないことに注意してください。</span><span class="sxs-lookup"><span data-stu-id="ac00e-123">It's important to know that after you create a custom policy, you can't change it if third-party apps are disabled in org-wide app settings.</span></span>

1. <span data-ttu-id="ac00e-124">Microsoft Teams 管理センターの左のナビゲーションで、[**チームアプリ**の  >  **アクセス許可ポリシー**] に移動します。</span><span class="sxs-lookup"><span data-stu-id="ac00e-124">In the left navigation of the Microsoft Teams admin center, go to **Teams apps** > **Permission policies**.</span></span>
2. <span data-ttu-id="ac00e-125">**[追加]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ac00e-125">Click **Add**.</span></span> <br>
    <span data-ttu-id="ac00e-126">![新しいアプリのアクセス許可ポリシーのスクリーンショット](media/app-permission-policies-new-policy.png)</span><span class="sxs-lookup"><span data-stu-id="ac00e-126">![Screenshot of new app permission policy](media/app-permission-policies-new-policy.png)</span></span>
3. <span data-ttu-id="ac00e-127">ポリシーの名前と説明を入力します。</span><span class="sxs-lookup"><span data-stu-id="ac00e-127">Enter a name and description for the policy.</span></span>
4. <span data-ttu-id="ac00e-128">[ **Microsoft アプリ**]、[**サードパーティ製アプリ**]、[**カスタムアプリ**] の下で、次のいずれかを選択します。</span><span class="sxs-lookup"><span data-stu-id="ac00e-128">Under **Microsoft apps**, **Third-party apps**, and **Custom apps**, select one of the following:</span></span>

    - <span data-ttu-id="ac00e-129">**すべてのアプリを許可する**</span><span class="sxs-lookup"><span data-stu-id="ac00e-129">**Allow all apps**</span></span>
    - <span data-ttu-id="ac00e-130">**特定のアプリを許可し、他のユーザーをブロックする**</span><span class="sxs-lookup"><span data-stu-id="ac00e-130">**Allow specific apps and block all others**</span></span>
    - <span data-ttu-id="ac00e-131">**特定のアプリをブロックし、他のユーザーをすべて許可する**</span><span class="sxs-lookup"><span data-stu-id="ac00e-131">**Block specific apps and allow all others**</span></span>
    - <span data-ttu-id="ac00e-132">**すべてのアプリをブロックする**</span><span class="sxs-lookup"><span data-stu-id="ac00e-132">**Block all apps**</span></span>

5. <span data-ttu-id="ac00e-133">**[特定のアプリを許可**する] を選んで他のアプリをブロックする場合は、許可するアプリを追加します。</span><span class="sxs-lookup"><span data-stu-id="ac00e-133">If you selected **Allow specific apps and block others**, add the apps that you want to allow:</span></span>

    1. <span data-ttu-id="ac00e-134">[**アプリの許可**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="ac00e-134">Select **Allow apps**.</span></span>
    1. <span data-ttu-id="ac00e-135">許可するアプリを検索し、[**追加**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ac00e-135">Search for the apps that you want to allow, and then click **Add**.</span></span> <span data-ttu-id="ac00e-136">検索結果は、アプリの発行元 (**Microsoft アプリ**、**サードパーティ製のアプリ**、または**カスタムアプリ**) にフィルター処理されます。</span><span class="sxs-lookup"><span data-stu-id="ac00e-136">The search results are filtered to the app publisher (**Microsoft apps**, **Third-party apps**, or **Custom apps**).</span></span>
    1. <span data-ttu-id="ac00e-137">アプリの一覧を選択したら、[**許可**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ac00e-137">When you've chosen the list of apps, click **Allow**.</span></span> 

6. <span data-ttu-id="ac00e-138">同様に、[特定のアプリをブロックする] を選んで、**他のアプリをすべて許可**する場合は、ブロックするアプリを検索して追加し、[**ブロック**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ac00e-138">Similarly, if you selected **Block specific apps and allow all others**, search for and add the apps that you want to block, and then click **Block**.</span></span>
7. <span data-ttu-id="ac00e-139">**[保存]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ac00e-139">Click **Save**.</span></span>

## <a name="edit-an-app-permission-policy"></a><span data-ttu-id="ac00e-140">アプリのアクセス許可ポリシーを編集する</span><span class="sxs-lookup"><span data-stu-id="ac00e-140">Edit an app permission policy</span></span>

<span data-ttu-id="ac00e-141">Microsoft Teams 管理センターを使用して、作成するグローバルポリシーやカスタムポリシーなどのポリシーを編集できます。</span><span class="sxs-lookup"><span data-stu-id="ac00e-141">You can use the Microsoft Teams admin center to edit a policy, including the global policy and custom policies that you create.</span></span>

1. <span data-ttu-id="ac00e-142">Microsoft Teams 管理センターの左のナビゲーションで、[**チームアプリ**の  >  **アクセス許可ポリシー**] に移動します。</span><span class="sxs-lookup"><span data-stu-id="ac00e-142">In the left navigation of the Microsoft Teams admin center, go to **Teams apps** > **Permission policies**.</span></span>
2. <span data-ttu-id="ac00e-143">ポリシー名の左側をクリックしてポリシーを選び、**[編集]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ac00e-143">Select the policy by clicking to the left of the policy name, and then click **Edit**.</span></span>
3. <span data-ttu-id="ac00e-144">ここで、必要な変更を行います。</span><span class="sxs-lookup"><span data-stu-id="ac00e-144">From here, make the changes that you want.</span></span> <span data-ttu-id="ac00e-145">アプリの発行元に基づいて設定を管理し、許可/禁止の設定に基づいてアプリを追加および削除することができます。</span><span class="sxs-lookup"><span data-stu-id="ac00e-145">You can manage settings based on the app publisher and add and remove apps based on the allow/block setting.</span></span>
4. <span data-ttu-id="ac00e-146">**[保存]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ac00e-146">Click **Save**.</span></span>

## <a name="assign-a-custom-app-permission-policy-to-users"></a><span data-ttu-id="ac00e-147">ユーザーにカスタムアプリのアクセス許可ポリシーを割り当てる</span><span class="sxs-lookup"><span data-stu-id="ac00e-147">Assign a custom app permission policy to users</span></span>

<span data-ttu-id="ac00e-148">Microsoft Teams 管理センターを使用して、ユーザー設定のポリシーを1人または複数のユーザーに割り当てることができます。また、グループ内のユーザー (セキュリティグループまたは配布グループ内のすべてのユーザー) にカスタムポリシーを割り当てることもできます。</span><span class="sxs-lookup"><span data-stu-id="ac00e-148">You can use the Microsoft Teams admin center to assign a custom policy to one or more users or the Skype for Business PowerShell module to assign a custom policy to users in a group, such as all users in a security group or distribution group.</span></span>

### <a name="assign-a-custom-app-permission-policy-to-users"></a><span data-ttu-id="ac00e-149">ユーザーにカスタムアプリのアクセス許可ポリシーを割り当てる</span><span class="sxs-lookup"><span data-stu-id="ac00e-149">Assign a custom app permission policy to users</span></span>

<span data-ttu-id="ac00e-150">1人のユーザーにポリシーを割り当てるには、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="ac00e-150">To assign a policy to one user:</span></span>

1. <span data-ttu-id="ac00e-151">Microsoft Teams 管理センターの左側のナビゲーションで、[**ユーザー**] に移動します。</span><span class="sxs-lookup"><span data-stu-id="ac00e-151">In the left navigation of the Microsoft Teams admin center, go to **Users**.</span></span>
2. <span data-ttu-id="ac00e-152">ユーザー名の左側をクリックしてユーザーを選択し、[**編集を設定する**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ac00e-152">Select the user by clicking to the left of the user name, and then click **Edit settings**.</span></span>
3. <span data-ttu-id="ac00e-153">[**アプリのアクセス許可ポリシー**] で、割り当てるアプリのアクセス許可ポリシーを選択し、[**適用**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ac00e-153">Under **App permission policy**, select the app permission policy you want to assign, and then click **Apply**.</span></span>

<span data-ttu-id="ac00e-154">複数のユーザーに同時にポリシーを割り当てるには、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="ac00e-154">To assign a policy to multiple users at a time:</span></span>

1. <span data-ttu-id="ac00e-155">Microsoft Teams 管理センターの左側のナビゲーションで、**[ユーザー]** に移動し、ユーザーを検索するか、表示にフィルターを適用してユーザーを表示します。</span><span class="sxs-lookup"><span data-stu-id="ac00e-155">In the left navigation of the Microsoft Teams admin center, go to **Users**, and then search for the users or filter the view to show the users you want.</span></span>
2. <span data-ttu-id="ac00e-156">[**&#x2713;** (チェックマーク)] の列からユーザーを選択します。</span><span class="sxs-lookup"><span data-stu-id="ac00e-156">In the **&#x2713;** (check mark) column, select the users.</span></span> <span data-ttu-id="ac00e-157">すべてのユーザーを選択するには、表の上部にある [&#x2713; (チェックマーク)] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ac00e-157">To select all users, click the &#x2713; (check mark) at the top of the table.</span></span>
3. <span data-ttu-id="ac00e-158">[**設定の編集**] をクリックし、必要な変更を行い、[**適用**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ac00e-158">Click **Edit settings**, make the changes that you want, and then click **Apply**.</span></span>  

<span data-ttu-id="ac00e-159">または、次の操作も実行できます。</span><span class="sxs-lookup"><span data-stu-id="ac00e-159">Or, you can also do the following:</span></span>

1. <span data-ttu-id="ac00e-160">Microsoft Teams 管理センターの左のナビゲーションで、[**チームアプリ**の  >  **アクセス許可ポリシー**] に移動します。</span><span class="sxs-lookup"><span data-stu-id="ac00e-160">In the left navigation of the Microsoft Teams admin center, go to **Teams apps** > **Permission policies**.</span></span>
2. <span data-ttu-id="ac00e-161">ポリシー名の左側をクリックしてポリシーを選びます。</span><span class="sxs-lookup"><span data-stu-id="ac00e-161">Select the policy by clicking to the left of the policy name.</span></span>
3. <span data-ttu-id="ac00e-162">**[ユーザーを管理する]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="ac00e-162">Select **Manage users**.</span></span>
4. <span data-ttu-id="ac00e-163">[**ユーザーを管理する**] ウィンドウで、表示名またはユーザー名でユーザーを検索し、名前を選択して [**追加**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ac00e-163">In the **Manage users** pane, search for the user by display name or by user name, select the name, and then click **Add**.</span></span> <span data-ttu-id="ac00e-164">追加するユーザーごとに、この手順を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="ac00e-164">Repeat this step for each user that you want to add.</span></span>
5. <span data-ttu-id="ac00e-165">ユーザーの追加が完了したら、[**保存**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ac00e-165">When you're finished adding users, click **Save**.</span></span>

### <a name="assign-a-custom-app-permission-policy-to-users-in-a-group"></a><span data-ttu-id="ac00e-166">カスタムアプリのアクセス許可ポリシーをグループ内のユーザーに割り当てる</span><span class="sxs-lookup"><span data-stu-id="ac00e-166">Assign a custom app permission policy to users in a group</span></span>

<span data-ttu-id="ac00e-167">カスタムアプリのアクセス許可ポリシーは、既に指定した複数のユーザーに割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="ac00e-167">You may want to assign a custom app permission policy to multiple users that you’ve already identified.</span></span> <span data-ttu-id="ac00e-168">たとえば、セキュリティ グループのすべてのユーザーにポリシーを割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="ac00e-168">For example, you may want to assign a policy to all users in a security group.</span></span> <span data-ttu-id="ac00e-169">これを行うには、Graph 用 Azure Active Directory PowerShell モジュールと Skype for Business PowerShell モジュールに接続します。</span><span class="sxs-lookup"><span data-stu-id="ac00e-169">You can do this by connecting to the Azure Active Directory PowerShell for Graph module and the Skype for Business PowerShell module.</span></span> <span data-ttu-id="ac00e-170">PowerShell を使用して Teams を管理する方法の詳細については、「[Teams での PowerShell の概要](teams-powershell-overview.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ac00e-170">For more information about using PowerShell to manage Teams, see [Teams PowerShell Overview](teams-powershell-overview.md).</span></span>

<span data-ttu-id="ac00e-171">この例では、Contoso 製薬 HR プロジェクトグループ内のすべてのユーザーに HR アプリのアクセス許可ポリシーと呼ばれるカスタムアプリのアクセス許可ポリシーを割り当てます。</span><span class="sxs-lookup"><span data-stu-id="ac00e-171">In this example, we assign a custom app permission policy called HR App Permission Policy to all users in the Contoso Pharmaceuticals HR Project group.</span></span>  

> [!NOTE]
> <span data-ttu-id="ac00e-172">まず、 [「単一の Windows PowerShell ウィンドウですべての Microsoft 365 または Office 365 サービスに接続](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-all-office-365-services-in-a-single-windows-powershell-window)する」の手順に従って、Graph モジュール用の Azure Active Directory Powershell と Skype For business powershell モジュールに接続していることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="ac00e-172">Make sure you first connect to the Azure Active Directory PowerShell for Graph module and Skype for Business PowerShell module by following the steps in [Connect to all Microsoft 365 or Office 365 services in a single Windows PowerShell window](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-all-office-365-services-in-a-single-windows-powershell-window).</span></span>

<span data-ttu-id="ac00e-173">特定のグループの GroupObjectId を取得します。</span><span class="sxs-lookup"><span data-stu-id="ac00e-173">Get the GroupObjectId of the particular group.</span></span>
```PowerShell
$group = Get-AzureADGroup -SearchString "Contoso Pharmaceuticals HR Project"
```
<span data-ttu-id="ac00e-174">指定したグループのメンバーを取得します。</span><span class="sxs-lookup"><span data-stu-id="ac00e-174">Get the members of the specified group.</span></span>
```PowerShell
$members = Get-AzureADGroupMember -ObjectId $group.ObjectId -All $true | Where-Object {$_.ObjectType -eq "User"}
```
<span data-ttu-id="ac00e-175">グループ内のすべてのユーザーに特定のアプリのアクセス許可ポリシーを割り当てます。</span><span class="sxs-lookup"><span data-stu-id="ac00e-175">Assign all users in the group to a particular app permission policy.</span></span> <span data-ttu-id="ac00e-176">この例では、HR アプリのアクセス許可ポリシーです。</span><span class="sxs-lookup"><span data-stu-id="ac00e-176">In this example, it's HR App Permission Policy.</span></span>
```PowerShell
$members | ForEach-Object { Grant-CsTeamsAppPermissionPolicy -PolicyName "HR App Permission Policy" -Identity $_.UserPrincipalName}
``` 
<span data-ttu-id="ac00e-177">グループ内のメンバー数によっては、このコマンドの実行に数分かかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="ac00e-177">Depending on the number of members in the group, this command may take several minutes to execute.</span></span>

## <a name="app-permission-policies-for-gcc"></a><span data-ttu-id="ac00e-178">GCC のアプリアクセス許可ポリシー</span><span class="sxs-lookup"><span data-stu-id="ac00e-178">App permission policies for GCC</span></span>

<span data-ttu-id="ac00e-179">Microsoft 365 Government-GCC によるチームの展開では、GCC に固有のサードパーティのアプリ設定について、次の点を理解しておくことが重要です。</span><span class="sxs-lookup"><span data-stu-id="ac00e-179">In a Microsoft 365 Government - GCC deployment of Teams, it's important to know the following about third-party app settings, which are unique to GCC.</span></span>

<span data-ttu-id="ac00e-180">GCC では、すべてのサードパーティ製アプリが既定でブロックされます。</span><span class="sxs-lookup"><span data-stu-id="ac00e-180">In GCC, all third-party apps are blocked by default.</span></span> <span data-ttu-id="ac00e-181">さらに、Microsoft Teams 管理センターの [アプリのアクセス許可ポリシー] ページでサードパーティ製のアプリを管理する方法について、次のメモが表示されます。</span><span class="sxs-lookup"><span data-stu-id="ac00e-181">Additionally, you'll see the following note about managing third-party apps on the app permission policies page in the Microsoft Teams admin center.</span></span>

![GCC のアプリのアクセス許可ポリシーのスクリーンショット](media/app-permission-policies-gcc.png)

<span data-ttu-id="ac00e-183">ユーザーまたは組織内のユーザーのセットに対してサードパーティ製のアプリを有効にするには、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="ac00e-183">To enable a third-party app for a user or a set of users in your organization, do the following:</span></span>

1. <span data-ttu-id="ac00e-184">Microsoft Teams 管理センターの左のナビゲーションで、[**チームアプリ**  >  の**管理**] に移動し、アプリの一覧で、ユーザーのセットに対して許可するサードパーティ製のアプリが組織レベルで**ブロック**されるように設定されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="ac00e-184">In the left navigation of the Microsoft Teams admin center, go to **Teams apps** > **Manage apps**, and then in the list of apps, confirm that the third-party app that you want to allow for a set of users is set to **Blocked** at the org level.</span></span>

2. <span data-ttu-id="ac00e-185">Microsoft Teams 管理センターの左のナビゲーションで、[ **Teams アプリ**の  >  **アクセス許可ポリシー**] に移動し、グローバルポリシーを編集して、サードパーティ製のアプリをブロックします。</span><span class="sxs-lookup"><span data-stu-id="ac00e-185">In the left navigation of the Microsoft Teams admin center, go to **Teams apps** > **Permission policies**, and then edit the global policy to block the third-party app.</span></span> <span data-ttu-id="ac00e-186">その手順は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="ac00e-186">To do this:</span></span>
    1. <span data-ttu-id="ac00e-187">[アプリのアクセス許可ポリシー] ページで、[**グローバル (組織全体の既定)**] をクリックし、[**編集**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ac00e-187">On the App permission policies page, click **Global (Org-wide default)**, and then click **Edit**.</span></span>
    2. <span data-ttu-id="ac00e-188">[**サードパーティのアプリ**] で、[**特定のアプリをブロックする**] を選択し、[その他のすべてのアプリを許可する] を選び、[**保存**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ac00e-188">Under **Third-party apps**, select **Block specific apps and allow all others**, add the app, and then click **Save**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="ac00e-189">組織レベルでアプリを許可するために、次の手順に進む前にこの操作を行うことが重要です。</span><span class="sxs-lookup"><span data-stu-id="ac00e-189">It's important to do this before you go to the next step to allow the app at the org level.</span></span> <span data-ttu-id="ac00e-190">これは、サードパーティのアプリがグローバルアプリのアクセス許可ポリシーでブロックされていない場合に、グローバルポリシーで適用されるすべてのユーザーが、組織レベルで許可したときにサードパーティ製のアプリにアクセスできるためです。</span><span class="sxs-lookup"><span data-stu-id="ac00e-190">This is because if the third-party app isn't blocked in the global app permission policy, all users that the global policy applies to will be able to access the third-party app when you allow it at the org level.</span></span>

3. <span data-ttu-id="ac00e-191">組織レベルでサードパーティ製のアプリを許可します。</span><span class="sxs-lookup"><span data-stu-id="ac00e-191">Allow the third-party app at the org level.</span></span> <span data-ttu-id="ac00e-192">これを行うには、左側のナビゲーションで、[ **Teams アプリ**  >  の**管理**] に移動します。</span><span class="sxs-lookup"><span data-stu-id="ac00e-192">To do this, in the left navigation, go to **Teams apps** > **Manage apps**.</span></span> <span data-ttu-id="ac00e-193">アプリの一覧で、アプリ名の左側をクリックしてアプリを選択し、[**許可**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="ac00e-193">In the list of apps, click to the left of the app name to select the app, and then select **Allow**.</span></span>
4. <span data-ttu-id="ac00e-194">アプリを許可する[カスタムアプリのアクセス許可ポリシーを作成](#create-a-custom-app-permission-policy)し、そのポリシーを目的のユーザーに[割り当て](#assign-a-custom-app-permission-policy-to-users)ます。</span><span class="sxs-lookup"><span data-stu-id="ac00e-194">[Create a custom app permission policy](#create-a-custom-app-permission-policy) to allow the app, and then [assign the policy](#assign-a-custom-app-permission-policy-to-users) to the users you want.</span></span>

## <a name="faq"></a><span data-ttu-id="ac00e-195">FAQ</span><span class="sxs-lookup"><span data-stu-id="ac00e-195">FAQ</span></span>

### <a name="working-with-app-permission-policies"></a><span data-ttu-id="ac00e-196">アプリのアクセス許可ポリシーを使用する</span><span class="sxs-lookup"><span data-stu-id="ac00e-196">Working with app permission policies</span></span>

#### <a name="what-app-interactions-do-permission-policies-affect"></a><span data-ttu-id="ac00e-197">権限ポリシーはどのようなアプリの操作に影響しますか?</span><span class="sxs-lookup"><span data-stu-id="ac00e-197">What app interactions do permission policies affect?</span></span>
<span data-ttu-id="ac00e-198">権限ポリシーは、エンドユーザーのインストール、検出、操作を制御することによって、アプリの使用を制御します。</span><span class="sxs-lookup"><span data-stu-id="ac00e-198">Permission policies govern app usage by controlling installation, discovery, and interaction for end users.</span></span> <span data-ttu-id="ac00e-199">管理者は、割り当てられているアクセス許可ポリシーに関係なく、引き続き Microsoft Teams 管理センターでアプリを管理することができます。</span><span class="sxs-lookup"><span data-stu-id="ac00e-199">Admins can still manage apps in the Microsoft Teams admin center regardless of the permission policies assigned to them.</span></span>

#### <a name="can-i-control-line-of-business-lob-apps"></a><span data-ttu-id="ac00e-200">基幹業務 (LOB) アプリを制御することはできますか?</span><span class="sxs-lookup"><span data-stu-id="ac00e-200">Can I control line of business (LOB) apps?</span></span>
<span data-ttu-id="ac00e-201">はい、アプリのアクセス許可ポリシーを使って、カスタム (LOB) アプリのロールアウトと配布を制御することができます。</span><span class="sxs-lookup"><span data-stu-id="ac00e-201">Yes, you can use app permission policies to control the rollout and distribution of custom (LOB) apps.</span></span> <span data-ttu-id="ac00e-202">ユーザー設定のポリシーを作成するか、またはグローバルポリシーを編集して、組織のニーズに基づいてカスタムアプリを許可またはブロックすることができます。</span><span class="sxs-lookup"><span data-stu-id="ac00e-202">You can create a custom policy or edit the global policy to allow or block custom apps based on the needs of your organization.</span></span>

#### <a name="how-do-app-permission-policies-relate-to-pinned-apps-and-app-setup-policies"></a><span data-ttu-id="ac00e-203">アプリのアクセス許可ポリシーは、固定されたアプリとアプリのセットアップポリシーにどのように関連していますか?</span><span class="sxs-lookup"><span data-stu-id="ac00e-203">How do app permission policies relate to pinned apps and app setup policies?</span></span>

<span data-ttu-id="ac00e-204">アプリのセットアップポリシーは、アプリのアクセス許可ポリシーと一緒に使うことができます。</span><span class="sxs-lookup"><span data-stu-id="ac00e-204">You can use app setup policies together with app permission policies.</span></span> <span data-ttu-id="ac00e-205">事前にピン留めされたアプリは、ユーザーに対して有効になっているアプリのセットから選択されます。</span><span class="sxs-lookup"><span data-stu-id="ac00e-205">Pre-pinned apps are selected from the set of enabled apps for a user.</span></span> <span data-ttu-id="ac00e-206">さらに、ユーザーがアプリのセットアップポリシーでアプリをブロックするアプリのアクセス許可ポリシーを持っている場合、そのアプリは Teams に表示されません。</span><span class="sxs-lookup"><span data-stu-id="ac00e-206">Additionally, if a user has an app permission policy that blocks an app in their app setup policy, that app won't appear in Teams.</span></span>

#### <a name="can-i-use-app-permission-policies-to-restrict-uploading-custom-apps"></a><span data-ttu-id="ac00e-207">アプリのアクセス許可ポリシーを使って、カスタムアプリのアップロードを制限することはできますか?</span><span class="sxs-lookup"><span data-stu-id="ac00e-207">Can I use app permission policies to restrict uploading custom apps?</span></span>

<span data-ttu-id="ac00e-208">[**アプリの管理**] ページまたはアプリのセットアップポリシーで、組織全体の設定を使用して、組織のカスタムアプリのアップロードを制限することができます。</span><span class="sxs-lookup"><span data-stu-id="ac00e-208">You can use org-wide settings on the **Manage apps** page, or app setup policies to restrict uploading custom apps for your organization.</span></span>  

<span data-ttu-id="ac00e-209">特定のユーザーによるカスタムアプリのアップロードを制限するには、カスタムアプリポリシーを使用します。</span><span class="sxs-lookup"><span data-stu-id="ac00e-209">To restrict specific users from uploading custom apps, use custom app policies.</span></span> <span data-ttu-id="ac00e-210">詳細については、「 [Teams でカスタムアプリポリシーと設定を管理](teams-custom-app-policies-and-settings.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ac00e-210">To learn more, see [Manage custom app policies and settings in Teams](teams-custom-app-policies-and-settings.md).</span></span>

#### <a name="does-blocking-an-app-apply-to-teams-mobile-clients"></a><span data-ttu-id="ac00e-211">アプリのブロックは Teams のモバイルクライアントに適用されますか?</span><span class="sxs-lookup"><span data-stu-id="ac00e-211">Does blocking an app apply to Teams mobile clients?</span></span>

<span data-ttu-id="ac00e-212">はい。アプリをブロックすると、そのアプリはすべてのチームクライアントでブロックされます。</span><span class="sxs-lookup"><span data-stu-id="ac00e-212">Yes, when you block an app, that app is blocked across all Teams clients.</span></span>  

### <a name="user-experience"></a><span data-ttu-id="ac00e-213">ユーザー エクスペリエンス</span><span class="sxs-lookup"><span data-stu-id="ac00e-213">User experience</span></span>

#### <a name="what-does-a-user-experience-when-an-app-is-blocked"></a><span data-ttu-id="ac00e-214">アプリがブロックされると、ユーザーエクスペリエンスはどうなりますか?</span><span class="sxs-lookup"><span data-stu-id="ac00e-214">What does a user experience when an app is blocked?</span></span>

<span data-ttu-id="ac00e-215">ブロックされたアプリやその機能 (ボット、タブ、メッセージング拡張機能など) をユーザーが操作することはできません。</span><span class="sxs-lookup"><span data-stu-id="ac00e-215">Users can't interact with a blocked app or its capabilities, such bots, tabs, and messaging extensions.</span></span> <span data-ttu-id="ac00e-216">チームやグループチャットなどの共有コンテキストでも、ボットはそのコンテキストの参加者全員にメッセージを送信できます。</span><span class="sxs-lookup"><span data-stu-id="ac00e-216">In a shared context, such as a team or group chat, bots can still send messages to all participants of that context.</span></span> <span data-ttu-id="ac00e-217">アプリがブロックされると、Teams によってユーザーにユーザーが示されます。</span><span class="sxs-lookup"><span data-stu-id="ac00e-217">Teams indicates to the user when an app is blocked.</span></span>

<span data-ttu-id="ac00e-218">たとえば、アプリがブロックされると、ユーザーは次のいずれも実行できません。</span><span class="sxs-lookup"><span data-stu-id="ac00e-218">For example, when an app is blocked, users can't do any of the following:</span></span>

- <span data-ttu-id="ac00e-219">アプリを個人的に、またはチャットやチームに追加する</span><span class="sxs-lookup"><span data-stu-id="ac00e-219">Add the app personally or to a chat or team</span></span>
- <span data-ttu-id="ac00e-220">アプリのボットにメッセージを送信する</span><span class="sxs-lookup"><span data-stu-id="ac00e-220">Send messages to the app’s bot</span></span>
- <span data-ttu-id="ac00e-221">操作可能なメッセージなど、情報をアプリに送り戻すボタンアクションを実行します。</span><span class="sxs-lookup"><span data-stu-id="ac00e-221">Perform button actions that send information back to the app, such as actionable messages</span></span>  
- <span data-ttu-id="ac00e-222">アプリのタブを表示する</span><span class="sxs-lookup"><span data-stu-id="ac00e-222">View the app’s tab</span></span>
- <span data-ttu-id="ac00e-223">通知を受信するためのコネクタを設定する</span><span class="sxs-lookup"><span data-stu-id="ac00e-223">Set up connectors to receive notifications</span></span>
- <span data-ttu-id="ac00e-224">アプリのメッセージング拡張機能を使用する</span><span class="sxs-lookup"><span data-stu-id="ac00e-224">Use the app’s messaging extension</span></span>

<span data-ttu-id="ac00e-225">従来のポータルでは、組織レベルでのアプリの制御が許可されています。つまり、アプリがブロックされると、組織内のすべてのユーザーに対してブロックされます。</span><span class="sxs-lookup"><span data-stu-id="ac00e-225">The legacy portal allowed controlling apps at the organization level, which means when an app is blocked, it's blocked for all users in the organization.</span></span> <span data-ttu-id="ac00e-226">[[アプリの管理](manage-apps.md)] ページでのアプリのブロックは、まったく同じように動作します。</span><span class="sxs-lookup"><span data-stu-id="ac00e-226">Blocking an app on the [Manage apps](manage-apps.md) page works exactly the same way.</span></span>

<span data-ttu-id="ac00e-227">特定のユーザーに割り当てられたアプリのアクセス許可ポリシーの場合、ボットまたはコネクタ機能を備えたアプリが許可され、その後ブロックされた場合、そのアプリが共有コンテキストの一部のユーザーに対してのみ許可されている場合、そのアプリに対してアクセス許可がないグループチャットまたはチャネルのメンバーは、ボットまたはコネクタが、対話式で操作することはできません。</span><span class="sxs-lookup"><span data-stu-id="ac00e-227">For app permission policies assigned to specific users, if an app with bot or connector capability was allowed and then blocked, and if the app is then allowed only for some users in a shared context, members of a group chat or channel that don't have permission to that app can see the message history and messages that were posted by the bot or connector, but can't interact with it.</span></span>

## <a name="related-topics"></a><span data-ttu-id="ac00e-228">関連項目</span><span class="sxs-lookup"><span data-stu-id="ac00e-228">Related topics</span></span>

- [<span data-ttu-id="ac00e-229">Teams でのアプリの管理設定</span><span class="sxs-lookup"><span data-stu-id="ac00e-229">Admin settings for apps in Teams</span></span>](admin-settings.md)
- [<span data-ttu-id="ac00e-230">チームのユーザーにポリシーを割り当てる</span><span class="sxs-lookup"><span data-stu-id="ac00e-230">Assign policies to your users in Teams</span></span>](assign-policies.md)
