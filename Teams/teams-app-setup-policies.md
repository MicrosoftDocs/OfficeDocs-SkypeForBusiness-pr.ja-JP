---
title: Microsoft Teams のアプリのセットアップ ポリシーを管理する
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
description: Microsoft Teams のアプリセットアップポリシーの概要と、それらを使ってアプリを固定して組織内のユーザーのためにチームをカスタマイズする方法について説明します。
f1keywords:
- ms.teamsadmincenter.apppolicies.setup
ms.openlocfilehash: f4dd1cac59cd15efa014aa2efbe83b0cb6e4f991
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2019
ms.locfileid: "34294018"
---
# <a name="manage-app-setup-policies-in-microsoft-teams"></a><span data-ttu-id="d0cb5-103">Microsoft Teams のアプリのセットアップ ポリシーを管理する</span><span class="sxs-lookup"><span data-stu-id="d0cb5-103">Manage app setup policies in Microsoft Teams</span></span>

> [!NOTE]
> <span data-ttu-id="d0cb5-104">組織全体のアプリのアクセス許可ポリシー設定を有効にしている場合、**カスタムアプリとの対話を許可**すると、Microsoft Teams 管理センターでまだアプリのセットアップポリシーが表示されない場合があります。</span><span class="sxs-lookup"><span data-stu-id="d0cb5-104">If you enabled the org-wide app permission policy setting, **Allow interaction with custom apps**, you may not see app setup policies yet in the Microsoft Teams admin center.</span></span> <span data-ttu-id="d0cb5-105">この機能は現在展開中であり、間もなく組織内で利用可能になります。</span><span class="sxs-lookup"><span data-stu-id="d0cb5-105">It's currently being rolled out and will be available soon in your organization.</span></span>

<span data-ttu-id="d0cb5-106">管理者は、アプリセットアップポリシーを使って Microsoft Teams をカスタマイズし、ユーザーにとって最も重要なアプリを強調表示することができます。</span><span class="sxs-lookup"><span data-stu-id="d0cb5-106">As an admin, you can use app setup policies to customize Microsoft Teams to highlight the apps that are most important for your users.</span></span> <span data-ttu-id="d0cb5-107">ピン留めするアプリを選択し、表示される順序を設定します。</span><span class="sxs-lookup"><span data-stu-id="d0cb5-107">You choose the apps to pin and set the order that they appear.</span></span> <span data-ttu-id="d0cb5-108">アプリセットアップポリシーを使用すると、サードパーティによって構築されたアプリや組織内の開発者を含め、組織内のユーザーが必要とするアプリを表示できます。</span><span class="sxs-lookup"><span data-stu-id="d0cb5-108">App setup policies let you showcase apps that users in your organization need, including ones built by third parties or by developers in your organization.</span></span> <span data-ttu-id="d0cb5-109">また、アプリセットアップポリシーを使用して、組み込みの機能の表示方法を管理することもできます。</span><span class="sxs-lookup"><span data-stu-id="d0cb5-109">You can also use app setup policies to manage how built-in features appear.</span></span>

<span data-ttu-id="d0cb5-110">アプリはアプリバーに固定されます。</span><span class="sxs-lookup"><span data-stu-id="d0cb5-110">Apps are pinned to the app bar.</span></span> <span data-ttu-id="d0cb5-111">これは、Teams のデスクトップクライアントの側のバーであり、Teams のモバイルクライアント (iOS と Android) の下部にあります。</span><span class="sxs-lookup"><span data-stu-id="d0cb5-111">This is the bar on the side of the Teams desktop client and at the bottom of the Teams mobile clients (iOS and Android).</span></span> 

|<span data-ttu-id="d0cb5-112">Teams のデスクトップクライアント</span><span class="sxs-lookup"><span data-stu-id="d0cb5-112">Teams desktop client</span></span>  |<span data-ttu-id="d0cb5-113">Teams モバイルクライアント</span><span class="sxs-lookup"><span data-stu-id="d0cb5-113">Teams mobile client</span></span> |
|---------|---------|
|![app-setup-policies-desktop-app-bar](media/app-setup-policies-desktop-app-bar.png)<br>  |   ![app-setup-policies-mobile-app-bar](media/app-setup-policies-mobile-app-bar.png)      |

<span data-ttu-id="d0cb5-116">アプリセットアップポリシーは、Microsoft Teams 管理センターで管理します。</span><span class="sxs-lookup"><span data-stu-id="d0cb5-116">You manage app setup policies in the Microsoft Teams admin center.</span></span> <span data-ttu-id="d0cb5-117">グローバル (組織全体の既定) ポリシーを使用するか、カスタムポリシーを作成してユーザーに割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="d0cb5-117">You can use the global (Org-wide default) policy or create custom policies and assign them to users.</span></span> <span data-ttu-id="d0cb5-118">組織内のユーザーは、カスタムポリシーを作成して割り当てる場合を除き、自動的にグローバルポリシーを取得します。</span><span class="sxs-lookup"><span data-stu-id="d0cb5-118">Users in your organization will automatically get the global policy unless you create and assign a custom policy.</span></span>

<span data-ttu-id="d0cb5-119">グローバルポリシーの設定を編集して、目的のアプリを含めることができます。</span><span class="sxs-lookup"><span data-stu-id="d0cb5-119">You can edit the settings in the global policy to include the apps that you want.</span></span> <span data-ttu-id="d0cb5-120">組織内のさまざまなユーザーグループのチームをカスタマイズする場合は、1つ以上のカスタムポリシーを作成して割り当てます。</span><span class="sxs-lookup"><span data-stu-id="d0cb5-120">If you want to customize Teams for different groups of users in your organization, create and assign one or more custom policies.</span></span> <span data-ttu-id="d0cb5-121">ユーザーにカスタムポリシーが割り当てられている場合は、そのポリシーがユーザーに適用されます。</span><span class="sxs-lookup"><span data-stu-id="d0cb5-121">If a user is assigned a custom policy, that policy applies to the user.</span></span> <span data-ttu-id="d0cb5-122">ユーザーにカスタムポリシーが割り当てられていない場合は、グローバルポリシーがユーザーに適用されます。</span><span class="sxs-lookup"><span data-stu-id="d0cb5-122">If a user isn't assigned a custom policy, the global policy applies to the user.</span></span>

![app-setup-policies](media/app-setup-policies.png)

> [!NOTE]
> <span data-ttu-id="d0cb5-124">教育機関向けの Teams をお持ちの場合は、現時点ではグローバルポリシーで割り当てアプリが既定で固定されていることを知っておくことが重要です。現在のところ、グローバルポリシーには表示されません。</span><span class="sxs-lookup"><span data-stu-id="d0cb5-124">If you have Teams for Education, it's important to know that the Assignments app is pinned by default in the global policy even though currently, you don't see it listed in the global policy.</span></span> <span data-ttu-id="d0cb5-125">チームクライアントの固定されたアプリの一覧で4番目のアプリになります。</span><span class="sxs-lookup"><span data-stu-id="d0cb5-125">It will be the fourth app in the list of pinned apps on Teams clients.</span></span>

## <a name="create-a-custom-app-setup-policy"></a><span data-ttu-id="d0cb5-126">カスタムアプリセットアップポリシーを作成する</span><span class="sxs-lookup"><span data-stu-id="d0cb5-126">Create a custom app setup policy</span></span>

<span data-ttu-id="d0cb5-127">Microsoft Teams 管理センターを使用して、カスタムポリシーを作成することができます。</span><span class="sxs-lookup"><span data-stu-id="d0cb5-127">You can use the Microsoft Teams admin center to create a custom policy.</span></span>

1. <span data-ttu-id="d0cb5-128">Microsoft Teams 管理センターの左のナビゲーションで、[ **Teams アプリ** > **セットアップポリシー**] に移動します。</span><span class="sxs-lookup"><span data-stu-id="d0cb5-128">In the left navigation of the Microsoft Teams admin center, go to **Teams apps** > **Setup policies**.</span></span>
2. <span data-ttu-id="d0cb5-129">[**新しいポリシー**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="d0cb5-129">Select **New policy**.</span></span>
3. <span data-ttu-id="d0cb5-130">ポリシーのわかりやすい名前を入力し、[**アプリの追加**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d0cb5-130">Enter a descriptive name for the policy, and then click **Add apps**.</span></span>
4. <span data-ttu-id="d0cb5-131">ユーザーがカスタムアプリを Teams にアップロードできるようにするかどうかに応じて、[**カスタムアプリのアップロードを許可**する] をオンまたはオフにします。</span><span class="sxs-lookup"><span data-stu-id="d0cb5-131">Turn on or turn off **Allow uploading custom apps**, depending on whether you want to let users upload custom apps to Teams.</span></span>
5. <span data-ttu-id="d0cb5-132">[固定された**アプリの追加**] ウィンドウで、追加するアプリを検索し、[**追加**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d0cb5-132">In the **Add pinned apps** pane, search for the apps you want to add, and then click **Add**.</span></span> <span data-ttu-id="d0cb5-133">アプリのアクセス許可ポリシーによってアプリをフィルター処理することもできます。</span><span class="sxs-lookup"><span data-stu-id="d0cb5-133">You can also filter apps by app permission policy.</span></span> <span data-ttu-id="d0cb5-134">アプリの一覧を選択したら、[**追加**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d0cb5-134">When you've chosen your list of apps, click **Add**.</span></span>

     ![app-setup-policies-add-apps](media/app-setup-policies-add-apps.png)

6. <span data-ttu-id="d0cb5-136">Teams で表示する順序でアプリを配置し、[**保存**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d0cb5-136">Arrange the apps in the order that you want them to appear in Teams, and then click **Save**.</span></span>

    ![app-setup-policies-new-policy-setup](media/app-setup-policies-new-policy-setup.png)

## <a name="edit-an-app-setup-policy"></a><span data-ttu-id="d0cb5-138">アプリのセットアップポリシーを編集する</span><span class="sxs-lookup"><span data-stu-id="d0cb5-138">Edit an app setup policy</span></span>

<span data-ttu-id="d0cb5-139">Microsoft Teams 管理センターを使って、作成するグローバル (組織全体の既定) ポリシーやカスタムポリシーなどのポリシーを編集できます。</span><span class="sxs-lookup"><span data-stu-id="d0cb5-139">You can use the Microsoft Teams admin center to edit a policy, including the global (Org-wide default) policy and custom policies that you create.</span></span>

1. <span data-ttu-id="d0cb5-140">Microsoft Teams 管理センターの左のナビゲーションで、[ **Teams アプリ** > **セットアップポリシー**] に移動します。</span><span class="sxs-lookup"><span data-stu-id="d0cb5-140">In the left navigation of the Microsoft Teams admin center, go to **Teams apps** > **Setup policies**.</span></span>
2. <span data-ttu-id="d0cb5-141">編集するポリシーを選択します。</span><span class="sxs-lookup"><span data-stu-id="d0cb5-141">Select the policy you want to edit.</span></span> 
3. <span data-ttu-id="d0cb5-142">ここで、必要な変更を行います。</span><span class="sxs-lookup"><span data-stu-id="d0cb5-142">From here, make the changes that you want.</span></span> <span data-ttu-id="d0cb5-143">アプリの順序を追加、削除、変更できます。</span><span class="sxs-lookup"><span data-stu-id="d0cb5-143">You can add, remove, and change the order of apps.</span></span>
4. <span data-ttu-id="d0cb5-144">[**保存**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d0cb5-144">Click **Save**.</span></span>

## <a name="assign-a-custom-app-setup-policy-to-users"></a><span data-ttu-id="d0cb5-145">ユーザーにカスタムアプリセットアップポリシーを割り当てる</span><span class="sxs-lookup"><span data-stu-id="d0cb5-145">Assign a custom app setup policy to users</span></span>

<span data-ttu-id="d0cb5-146">Microsoft Teams 管理センターを使用して、カスタムポリシーを個々のユーザーに割り当てるか、Skype for Business PowerShell モジュールを使用して、セキュリティグループや配布グループなどのユーザーグループにカスタムポリシーを割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="d0cb5-146">You can use the Microsoft Teams admin center to assign a custom policy to individual users or the Skype for Business PowerShell module  to assign a custom policy to groups of users, such as a security group or distribution group.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="d0cb5-147">ユーザーにポリシーを割り当てるには、PowerShell を使用することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="d0cb5-147">We recommend using PowerShell only to assign policies to users.</span></span> <span data-ttu-id="d0cb5-148">Microsoft Teams 管理センターを使って、ポリシーを作成、編集、管理します。</span><span class="sxs-lookup"><span data-stu-id="d0cb5-148">Use the Microsoft Teams admin center to create, edit, and manage policies.</span></span>

### <a name="assign-a-custom-app-setup-policy-to-individual-users"></a><span data-ttu-id="d0cb5-149">カスタムアプリセットアップポリシーを個々のユーザーに割り当てる</span><span class="sxs-lookup"><span data-stu-id="d0cb5-149">Assign a custom app setup policy to individual users</span></span>

1. <span data-ttu-id="d0cb5-150">Microsoft Teams 管理センターの左のナビゲーションで、[**ユーザー**] に移動し、ユーザーをクリックします。</span><span class="sxs-lookup"><span data-stu-id="d0cb5-150">In the left navigation of the Microsoft Teams admin center, go to **Users**, and then click  the user.</span></span>
2. <span data-ttu-id="d0cb5-151">**[割り当てられているポリシー]** の隣にある **[編集]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="d0cb5-151">Next to **Assigned policies**, choose **Edit**.</span></span>
3. <span data-ttu-id="d0cb5-152">[ **Teams アプリセットアップポリシー**] で、割り当てるアプリセットアップポリシーを選択し、[**保存**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="d0cb5-152">Under **Teams App Setup policy**, select the app setup policy you want to assign, and then choose **Save**.</span></span>

    ![app-setup-policies-assign-policy](media/app-setup-policies-assign-policy.png)

<span data-ttu-id="d0cb5-154">また、次のように、1人または複数のユーザーにアプリセットアップポリシーを割り当てることもできます。</span><span class="sxs-lookup"><span data-stu-id="d0cb5-154">You can also assign an app setup policy to one or more users as follows:</span></span>

1. <span data-ttu-id="d0cb5-155">**Microsoft teams 管理センター** > **Teams アプリ** > **セットアップポリシー**に移動します。</span><span class="sxs-lookup"><span data-stu-id="d0cb5-155">Go to **Microsoft Teams admin center** > **Teams apps** > **Setup policies**.</span></span>
2. <span data-ttu-id="d0cb5-156">ポリシー名の左側をクリックして、ポリシーを選択します。</span><span class="sxs-lookup"><span data-stu-id="d0cb5-156">Select the policy by clicking to the left of the policy name.</span></span>
3. <span data-ttu-id="d0cb5-157">[**ユーザーの管理**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="d0cb5-157">Select **Manage users**.</span></span>
4. <span data-ttu-id="d0cb5-158">[**ユーザーの管理**] ウィンドウで、[表示名] または [ユーザー名] でユーザーを検索し、名前を選択して [**追加**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="d0cb5-158">In the **Manage users** pane, search for the user by display name or by user name, select the name, and then select **Add**.</span></span> <span data-ttu-id="d0cb5-159">追加するユーザーごとに、この手順を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="d0cb5-159">Repeat this step for each user that you want to add.</span></span>
5. <span data-ttu-id="d0cb5-160">ユーザーの追加が完了したら、[**保存**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="d0cb5-160">When you are finished adding users, select **Save**.</span></span>

### <a name="assign-a-custom-app-setup-policy-to-users-in-a-group"></a><span data-ttu-id="d0cb5-161">カスタムアプリセットアップポリシーをグループ内のユーザーに割り当てる</span><span class="sxs-lookup"><span data-stu-id="d0cb5-161">Assign a custom app setup policy to users in a group</span></span>

<span data-ttu-id="d0cb5-162">カスタムアプリセットアップポリシーは、既に指定した複数のユーザーに割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="d0cb5-162">You may want to assign a custom app setup policy to multiple users that you’ve already identified.</span></span> <span data-ttu-id="d0cb5-163">たとえば、セキュリティグループ内のすべてのユーザーにポリシーを割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="d0cb5-163">For example, you may want to assign a policy to all users in a security group.</span></span> <span data-ttu-id="d0cb5-164">これを行うには、Azure Active Directory PowerShell for Graph モジュールと Skype for Business PowerShell モジュールに接続します。</span><span class="sxs-lookup"><span data-stu-id="d0cb5-164">You can do this by connecting to the Azure Active Directory PowerShell for Graph module and the Skype for Business PowerShell module.</span></span> <span data-ttu-id="d0cb5-165">PowerShell を使用して Teams を管理する方法の詳細については、「[Teams での PowerShell の概要](teams-powershell-overview.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d0cb5-165">For more information about using PowerShell to manage Teams, see [Teams PowerShell Overview](teams-powershell-overview.md).</span></span>

<span data-ttu-id="d0cb5-166">この例では、"人事アプリセットアップポリシー" というカスタムアプリセットアップポリシーを、Contoso 製薬 HR プロジェクトグループ内のすべてのユーザーに割り当てています。</span><span class="sxs-lookup"><span data-stu-id="d0cb5-166">In this example, we assign a custom app setup policy called HR App Setup Policy to all users in the Contoso Pharmaceuticals HR Project group.</span></span>  

> [!NOTE]
> <span data-ttu-id="d0cb5-167">「[単一の Windows PowerShell ウィンドウですべての Office 365 サービスに接続する](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-all-office-365-services-in-a-single-windows-powershell-window)」の手順に従って、必ず最初に Azure Active Directory PowerShell for Graph モジュールと Skype for Business PowerShell モジュールに接続してください。</span><span class="sxs-lookup"><span data-stu-id="d0cb5-167">Make sure you first connect to the Azure Active Directory PowerShell for Graph module and Skype for Business PowerShell module by following the steps in [Connect to all Office 365 services in a single Windows PowerShell window](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-all-office-365-services-in-a-single-windows-powershell-window).</span></span>

<span data-ttu-id="d0cb5-168">特定のグループの GroupObjectId を取得します。</span><span class="sxs-lookup"><span data-stu-id="d0cb5-168">Get the GroupObjectId of the particular group.</span></span>
```
$group = Get-AzureADGroup -SearchString "Contoso Pharmaceuticals HR Project"
```
<span data-ttu-id="d0cb5-169">指定したグループのメンバーを取得します。</span><span class="sxs-lookup"><span data-stu-id="d0cb5-169">Get the members of the specified group.</span></span>
```
$members = Get-AzureADGroupMember -ObjectId $group.ObjectId -All $true | Where-Object {$_.ObjectType -eq "User"}
```
<span data-ttu-id="d0cb5-170">グループ内のすべてのユーザーを特定のアプリセットアップポリシーに割り当てます。</span><span class="sxs-lookup"><span data-stu-id="d0cb5-170">Assign all users in the group to a particular app setup policy.</span></span> <span data-ttu-id="d0cb5-171">この例では、HR アプリのセットアップポリシーです。</span><span class="sxs-lookup"><span data-stu-id="d0cb5-171">In this example, it's HR App Setup Policy.</span></span>
```
$members | ForEach-Object { Grant-CsTeamsAppSetupPolicy -PolicyName "HR App Setup Policy" -Identity $_.EmailAddress}
``` 
<span data-ttu-id="d0cb5-172">グループ内のメンバー数によっては、このコマンドの実行に数分かかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="d0cb5-172">Depending on the number of members in the group, this command may take several minutes to execute.</span></span>

## <a name="faq"></a><span data-ttu-id="d0cb5-173">FAQ</span><span class="sxs-lookup"><span data-stu-id="d0cb5-173">FAQ</span></span>

### <a name="working-with-app-setup-policies"></a><span data-ttu-id="d0cb5-174">アプリセットアップポリシーを使用する</span><span class="sxs-lookup"><span data-stu-id="d0cb5-174">Working with app setup policies</span></span>

#### <a name="what-built-in-app-setup-policies-are-included-in-the-microsoft-teams-admin-center"></a><span data-ttu-id="d0cb5-175">Microsoft Teams 管理センターには、どのような組み込みのアプリセットアップポリシーが含まれていますか?</span><span class="sxs-lookup"><span data-stu-id="d0cb5-175">What built-in app setup policies are included in the Microsoft Teams admin center?</span></span>

- <span data-ttu-id="d0cb5-176">**グローバル (組織全体の既定)**: この既定のポリシーは、別のポリシーを割り当てない限り、組織内のすべてのユーザーに適用されます。</span><span class="sxs-lookup"><span data-stu-id="d0cb5-176">**Global (Org-wide default)**: This default policy applies to all users in your organization unless you assign another policy.</span></span> <span data-ttu-id="d0cb5-177">グローバルポリシーを編集して、ユーザーにとって最も重要なアプリをピン留めします。</span><span class="sxs-lookup"><span data-stu-id="d0cb5-177">Edit the global policy to pin apps that are most important for your users.</span></span>
- <span data-ttu-id="d0cb5-178">**Firstlineworker**: このポリシーは、firstline worker に対して使用されます。</span><span class="sxs-lookup"><span data-stu-id="d0cb5-178">**FirstLineWorker**: This policy is for firstline workers.</span></span> <span data-ttu-id="d0cb5-179">組織内の firstline worker に割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="d0cb5-179">You can assign it to firstline workers in your organization.</span></span> <span data-ttu-id="d0cb5-180">作成するカスタムポリシーなど、設定をアクティブにするユーザーにポリシーを割り当てる必要があることを知っておくことが重要です。</span><span class="sxs-lookup"><span data-stu-id="d0cb5-180">It's important to know that like custom policies that you create, you have to assign the policy to users for the settings to be active.</span></span> <span data-ttu-id="d0cb5-181">詳細については、この記事の「[ユーザーにカスタムアプリセットアップポリシーを割り当てる](#assign-a-custom-app-setup-policy-to-users)」セクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="d0cb5-181">For more information, go to the [Assign a custom app setup policy to users](#assign-a-custom-app-setup-policy-to-users) section of this article.</span></span>

#### <a name="why-cant-i-find-an-app-in-the-add-pinned-apps-pane"></a><span data-ttu-id="d0cb5-182">[ピン留めしたアプリの追加] ウィンドウでアプリが見つからないのはなぜですか?</span><span class="sxs-lookup"><span data-stu-id="d0cb5-182">Why can't I find an app in the Add pinned apps pane?</span></span>

<span data-ttu-id="d0cb5-183">アプリセットアップポリシーを使用して、すべてのアプリを Teams にピン留めすることはできません。</span><span class="sxs-lookup"><span data-stu-id="d0cb5-183">Not all apps can be pinned to Teams through an app setup policy.</span></span> <span data-ttu-id="d0cb5-184">一部のアプリでは、この機能がサポートされていない可能性があります。</span><span class="sxs-lookup"><span data-stu-id="d0cb5-184">Some apps may not support this functionality.</span></span> <span data-ttu-id="d0cb5-185">ピン留めできるアプリを見つけるには、[**ピン留め**されたアプリの追加] ウィンドウでアプリを検索します。</span><span class="sxs-lookup"><span data-stu-id="d0cb5-185">To find apps that can be pinned, search for the app in the **Add pinned apps** pane.</span></span> <span data-ttu-id="d0cb5-186">個人用のスコープ (静的タブ) とボットを含むタブは、Teams のデスクトップクライアントにピン留めすることができます。これらのアプリは、[固定された**アプリの追加**] ウィンドウで利用できます。</span><span class="sxs-lookup"><span data-stu-id="d0cb5-186">Tabs that have a personal scope (static tabs) and bots can be pinned to the Teams desktop client and these apps are available in the **Add pinned apps** pane.</span></span>

<span data-ttu-id="d0cb5-187">Teams app store にはすべての Teams アプリが一覧表示されます。 [**ピン留め**されたアプリの追加] ウィンドウには、ポリシーを通じてチームにピン留めできるアプリのみが含まれていることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="d0cb5-187">Keep in mind that the Teams app store lists all Teams apps whereas the **Add pinned apps** pane includes only apps that can be pinned to Teams through a policy.</span></span> 

#### <a name="im-a-teams-for-education-admin-what-do-i-need-to-know-about-app-setup-policies-in-teams-for-education"></a><span data-ttu-id="d0cb5-188">私は教育管理者向けのチームです。教育機関向け Teams のアプリセットアップポリシーについて知っておくべきこと</span><span class="sxs-lookup"><span data-stu-id="d0cb5-188">I'm a Teams for Education admin. What do I need to know about app setup policies in Teams for Education?</span></span>

- <span data-ttu-id="d0cb5-189">通話アプリは、教育担当の Teams では利用できません。</span><span class="sxs-lookup"><span data-stu-id="d0cb5-189">The Calling app isn't available in Teams for Education.</span></span> <span data-ttu-id="d0cb5-190">新しいカスタムアプリのセットアップポリシーを作成すると、アプリの一覧に呼び出し元のアプリが表示されます。</span><span class="sxs-lookup"><span data-stu-id="d0cb5-190">When you create a new custom app setup policy, the Calling app is displayed in the list of apps.</span></span> <span data-ttu-id="d0cb5-191">ただし、アプリは Teams クライアントにはピン留めされておらず、教育機関のチームではチーム内の通話アプリを見ることはできません。</span><span class="sxs-lookup"><span data-stu-id="d0cb5-191">However, the app isn't pinned to Teams clients and Teams for Education users won't see the Calls app in Teams.</span></span> 

- <span data-ttu-id="d0cb5-192">現時点では、Teams Android アプリの教育機関向けの Teams では、ポリシーの変更は反映されません。</span><span class="sxs-lookup"><span data-stu-id="d0cb5-192">Currently, policy changes aren't reflected for Teams for Education users on the Teams Android app.</span></span> <span data-ttu-id="d0cb5-193">現在、教育機関向けの Teams のポリシーの変更をサポートする新しいバージョンのアプリを開発しています。</span><span class="sxs-lookup"><span data-stu-id="d0cb5-193">We're working on a new version of the app that supports policy changes for Teams for Education.</span></span>

#### <a name="how-many-apps-can-be-added-to-a-policy"></a><span data-ttu-id="d0cb5-194">ポリシーに追加できるアプリの数を教えてください。</span><span class="sxs-lookup"><span data-stu-id="d0cb5-194">How many apps can be added to a policy?</span></span>

<span data-ttu-id="d0cb5-195">少なくとも2つのアプリが Teams モバイルクライアント (iOS と Android) にピン留めされている必要があります。</span><span class="sxs-lookup"><span data-stu-id="d0cb5-195">A minimum of two apps must be pinned to the Teams mobile clients (iOS and Android).</span></span> <span data-ttu-id="d0cb5-196">ポリシーのアプリが2つ未満の場合、モバイルクライアントはポリシーの設定を反映せず、代わりに既存の構成を使い続けます。</span><span class="sxs-lookup"><span data-stu-id="d0cb5-196">If a policy has less than two apps, the mobile clients won't reflect the policy settings and instead will continue to use the existing configuration.</span></span>

#### <a name="how-long-does-it-take-for-policy-changes-to-take-effect"></a><span data-ttu-id="d0cb5-197">ポリシーの変更が有効になるまでにはどのくらいの時間がかかりますか?</span><span class="sxs-lookup"><span data-stu-id="d0cb5-197">How long does it take for policy changes to take effect?</span></span>

<span data-ttu-id="d0cb5-198">グローバルポリシーを編集するか、ポリシーを割り当てると、変更が有効になるまで最大24時間かかることがあります。</span><span class="sxs-lookup"><span data-stu-id="d0cb5-198">After you edit the global policy or assign a policy, it can take up to 24 hours for changes to take effect.</span></span>

### <a name="user-experience"></a><span data-ttu-id="d0cb5-199">ユーザー エクスペリエンス</span><span class="sxs-lookup"><span data-stu-id="d0cb5-199">User experience</span></span>

#### <a name="how-can-users-see-all-their-pinned-apps-in-teams"></a><span data-ttu-id="d0cb5-200">ユーザーが Teams で固定されたすべてのアプリを表示するにはどうすればよいですか?</span><span class="sxs-lookup"><span data-stu-id="d0cb5-200">How can users see all their pinned apps in Teams?</span></span>

<span data-ttu-id="d0cb5-201">ユーザーに対して固定されているすべてのアプリを表示するには、インストールされているアプリの数とチームクライアントウィンドウのサイズに応じて、次の操作が必要になることがあります。</span><span class="sxs-lookup"><span data-stu-id="d0cb5-201">To view all apps that are pinned for a user, users may have to do the following depending on the number of installed apps and the size of their Teams client window.</span></span>

|<span data-ttu-id="d0cb5-202">Teams のデスクトップクライアント</span><span class="sxs-lookup"><span data-stu-id="d0cb5-202">Teams desktop client</span></span> |<span data-ttu-id="d0cb5-203">Teams モバイルクライアント</span><span class="sxs-lookup"><span data-stu-id="d0cb5-203">Teams mobile client</span></span> |
|---------|---------|
|<span data-ttu-id="d0cb5-204">Teams のサイドにあるアプリバーで、[...] をクリックします。 **その他のアプリ**。</span><span class="sxs-lookup"><span data-stu-id="d0cb5-204">In the app bar on the side of Teams, click **... More apps**.</span></span>| <span data-ttu-id="d0cb5-205">チームの下部付近にあるアプリバーで、上にスワイプします。</span><span class="sxs-lookup"><span data-stu-id="d0cb5-205">In the app bar near the bottom of Teams, swipe up.</span></span>|
|![app-setup-policies-desktop-more-apps](media/app-setup-policies-desktop-more-apps.png)<br>   |![app-setup-policies-mobile-more-apps](media/app-setup-policies-mobile-more-apps.png)  

#### <a name="what-do-i-need-to-know-about-the-teams-mobile-experience"></a><span data-ttu-id="d0cb5-208">Teams のモバイルエクスペリエンスについて知っておくべきこと</span><span class="sxs-lookup"><span data-stu-id="d0cb5-208">What do I need to know about the Teams mobile experience?</span></span>

<span data-ttu-id="d0cb5-209">現在、Teams モバイルクライアント (iOS と Android) では、静的なタブを持つ個人用アプリはサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="d0cb5-209">The Teams mobile clients (iOS and Android) currently don't support personal apps with static tabs.</span></span> <span data-ttu-id="d0cb5-210">ポリシーに設定されているアプリによっては、Teams のデスクトップクライアントに固定されたアプリが Teams のモバイルクライアントに表示されない場合があります。</span><span class="sxs-lookup"><span data-stu-id="d0cb5-210">Depending on the apps set in the policy, apps pinned to the Teams desktop client might not appear in the Teams mobile clients.</span></span> <span data-ttu-id="d0cb5-211">携帯電話クライアントのチャットには、個人用のボットが引き続き表示されます。</span><span class="sxs-lookup"><span data-stu-id="d0cb5-211">Personal bots will still appear in Chat on mobile clients.</span></span>

<span data-ttu-id="d0cb5-212">Teams のモバイルクライアントでは、ユーザーにはアクティビティ、チャット、Teams などの主要な Teams アプリが表示され、シフトなどの一部のサードパーティ製アプリを Microsoft からピン留めすることができます。</span><span class="sxs-lookup"><span data-stu-id="d0cb5-212">With the Teams mobile clients, users will see core Teams apps such as Activity, Chat, and Teams, and you can pin some first-party apps from Microsoft, such as Shifts.</span></span> 

#### <a name="can-users-change-the-order-of-apps-pinned-through-a-policy"></a><span data-ttu-id="d0cb5-213">ユーザーはポリシーによって固定されたアプリの順序を変更できますか。</span><span class="sxs-lookup"><span data-stu-id="d0cb5-213">Can users change the order of apps pinned through a policy?</span></span>

<span data-ttu-id="d0cb5-214">現時点では、ユーザーはチームのモバイルクライアントで固定されたアプリの順序を変更できますが、Teams のデスクトップや web クライアントでは変更できません。</span><span class="sxs-lookup"><span data-stu-id="d0cb5-214">Currently, users can change the order of their pinned apps on Teams mobile clients but not on the Teams desktop or web clients.</span></span> 

### <a name="custom-teams-apps"></a><span data-ttu-id="d0cb5-215">カスタム Teams アプリ</span><span class="sxs-lookup"><span data-stu-id="d0cb5-215">Custom Teams apps</span></span>

#### <a name="my-organization-built-a-custom-teams-app-and-published-it-either-to-appsource-or-the-tenant-app-catalog-but-the-app-icon-isnt-displayed-as-expected-when-the-app-is-pinned-to-the-app-bar-in-teams-how-do-i-fix-it"></a><span data-ttu-id="d0cb5-216">組織では、カスタム Teams アプリを構築し、AppSource またはテナントのアプリカタログに公開していますが、アプリが Teams のアプリバーにピン留めされている場合、アプリのアイコンは期待どおりに表示されません。</span><span class="sxs-lookup"><span data-stu-id="d0cb5-216">My organization built a custom Teams app and published it, either to AppSource or the Tenant app catalog, but the app icon isn't displayed as expected when the app is pinned to the app bar in Teams.</span></span> <span data-ttu-id="d0cb5-217">問題を解決するにはどうすればよいですか?</span><span class="sxs-lookup"><span data-stu-id="d0cb5-217">How do I fix it?</span></span> 

<span data-ttu-id="d0cb5-218">アプリを申請する前に、ロゴガイドラインに従っていることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="d0cb5-218">Make sure that you follow the logo guidelines before you submit the app.</span></span> <span data-ttu-id="d0cb5-219">詳細については、「[販売業者ダッシュボードの申請のチェックリスト](https://docs.microsoft.com/microsoftteams/platform/publishing/office-store-checklist)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d0cb5-219">To learn more, see [Checklist for Seller Dashboard submission](https://docs.microsoft.com/microsoftteams/platform/publishing/office-store-checklist).</span></span> 

 ## <a name="related-topics"></a><span data-ttu-id="d0cb5-220">関連トピック</span><span class="sxs-lookup"><span data-stu-id="d0cb5-220">Related topics</span></span>
- [<span data-ttu-id="d0cb5-221">Teams でのアプリの管理設定</span><span class="sxs-lookup"><span data-stu-id="d0cb5-221">Admin settings for apps in Teams</span></span>](admin-settings.md)
- [<span data-ttu-id="d0cb5-222">Teams のアプリのアクセス許可ポリシーを管理する</span><span class="sxs-lookup"><span data-stu-id="d0cb5-222">Manage app permission policies in Teams</span></span>](teams-app-permission-policies.md)
- [<span data-ttu-id="d0cb5-223">Teams のカスタム アプリのポリシーと設定を管理する</span><span class="sxs-lookup"><span data-stu-id="d0cb5-223">Manage custom app policies and settings in Teams</span></span>](teams-custom-app-policies-and-settings.md)
- [<span data-ttu-id="d0cb5-224">Teams クライアントからテナントアプリカタログにアプリを発行する</span><span class="sxs-lookup"><span data-stu-id="d0cb5-224">Publish an app to the Tenant Apps Catalog from the Teams client</span></span>](tenant-apps-catalog-teams.md)
