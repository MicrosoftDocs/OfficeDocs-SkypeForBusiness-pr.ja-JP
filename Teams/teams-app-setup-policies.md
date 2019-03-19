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
ms.audience: Admin
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Help
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
description: マイクロソフトのチームおよび組織内のユーザーのチームをカスタマイズするのには暗証番号 (pin) のアプリケーションを使用するアプリケーション設定のポリシーについて説明します。
f1keywords:
- ms.teamsadmincenter.apppolicies.setup
ms.openlocfilehash: 29fcd5541e4817a2c5880316bba33d7d55047444
ms.sourcegitcommit: 8e62025d630c511ffb0361b9643d46c762188102
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/19/2019
ms.locfileid: "30664749"
---
# <a name="manage-app-setup-policies-in-microsoft-teams"></a><span data-ttu-id="9e06e-103">Microsoft Teams のアプリのセットアップ ポリシーを管理する</span><span class="sxs-lookup"><span data-stu-id="9e06e-103">Manage app setup policies in Microsoft Teams</span></span>

[!INCLUDE [preview-feature](includes/preview-feature.md)]

<span data-ttu-id="9e06e-104">管理者としては、マイクロソフトのチームは、ユーザーにとって最も重要なアプリケーションを強調表示をカスタマイズするのにはアプリケーションの設定のポリシーを使用できます。</span><span class="sxs-lookup"><span data-stu-id="9e06e-104">As an admin, you can use app setup policies to customize Microsoft Teams to highlight the apps that are most important for your users.</span></span> <span data-ttu-id="9e06e-105">固定し、表示される順序を設定するアプリケーションを選択します。</span><span class="sxs-lookup"><span data-stu-id="9e06e-105">You choose the apps to pin and set the order that they appear.</span></span> <span data-ttu-id="9e06e-106">アプリケーション設定のポリシーを使用するサード ・ パーティまたは組織内の開発者によって構築されたものなど、組織内のユーザーを必要とするアプリケーションを紹介します。</span><span class="sxs-lookup"><span data-stu-id="9e06e-106">App setup policies let you showcase apps that users in your organization need, including ones built by third parties or by developers in your organization.</span></span> <span data-ttu-id="9e06e-107">どの組み込みの機能を管理するアプリケーション設定のポリシーを使用することも表示されます。</span><span class="sxs-lookup"><span data-stu-id="9e06e-107">You can also use app setup policies to manage how built-in features appear.</span></span>

<span data-ttu-id="9e06e-108">アプリケーション バーには、アプリが固定されています。</span><span class="sxs-lookup"><span data-stu-id="9e06e-108">Apps are pinned to the app bar.</span></span> <span data-ttu-id="9e06e-109">これは、チームのデスクトップ クライアント側にし、チームのモバイル クライアント (iOS および Android) の下部にあるバーです。</span><span class="sxs-lookup"><span data-stu-id="9e06e-109">This is the bar on the side of the Teams desktop client and at the bottom of the Teams mobile clients (iOS and Android).</span></span> 

|<span data-ttu-id="9e06e-110">チームのデスクトップ クライアント</span><span class="sxs-lookup"><span data-stu-id="9e06e-110">Teams desktop client</span></span>  |<span data-ttu-id="9e06e-111">モバイル クライアントのチーム</span><span class="sxs-lookup"><span data-stu-id="9e06e-111">Teams mobile client</span></span> |
|---------|---------|
|![app-setup-policies-desktop-app-bar.png](media/app-setup-policies-desktop-app-bar.png)<br>  |   ![app-setup-policies-mobile-app-bar.png](media/app-setup-policies-mobile-app-bar.png)      |

<span data-ttu-id="9e06e-114">マイクロソフトのチームの管理センターでのアプリケーション設定のポリシーを管理します。</span><span class="sxs-lookup"><span data-stu-id="9e06e-114">You manage app setup policies in the Microsoft Teams admin center.</span></span> <span data-ttu-id="9e06e-115">グローバル (組織全体の既定値) ポリシーを使用して、またはカスタム ポリシーを作成してユーザーに割り当てます。</span><span class="sxs-lookup"><span data-stu-id="9e06e-115">You can use the global (Org-wide default) policy or create custom policies and assign them to users.</span></span> <span data-ttu-id="9e06e-116">組織内のユーザーを作成し、カスタム ・ ポリシーを設定しない限り、グローバル ポリシーが自動的に表示されます。</span><span class="sxs-lookup"><span data-stu-id="9e06e-116">Users in your organization will automatically get the global policy unless you create and assign a custom policy.</span></span>

<span data-ttu-id="9e06e-117">アプリケーションを含めるには、グローバル ポリシーの設定を編集することができます。</span><span class="sxs-lookup"><span data-stu-id="9e06e-117">You can edit the settings in the global policy to include the apps that you want.</span></span> <span data-ttu-id="9e06e-118">チーム、組織内のユーザーのグループごとにカスタマイズする場合は、作成し、1 つまたは複数のカスタム ポリシーを割り当てます。</span><span class="sxs-lookup"><span data-stu-id="9e06e-118">If you want to customize Teams for different groups of users in your organization, create and assign one or more custom policies.</span></span>

![アプリケーション ・ セットアップ ・ policies.png](media/app-setup-policies.png)

> [!NOTE]
> <span data-ttu-id="9e06e-120">ユーザーには、カスタム ポリシーが割り当てられているが場合、は、ユーザーにそのポリシーが適用されます。</span><span class="sxs-lookup"><span data-stu-id="9e06e-120">If a user is assigned a custom policy, that policy applies to the user.</span></span> <span data-ttu-id="9e06e-121">ユーザーには、カスタム ポリシーが割り当てられていない、グローバル ポリシーがユーザーに適用されます。</span><span class="sxs-lookup"><span data-stu-id="9e06e-121">If a user isn't assigned a custom policy, the global policy applies to the user.</span></span>

## <a name="create-a-custom-app-setup-policy"></a><span data-ttu-id="9e06e-122">カスタム アプリケーション設定のポリシーを作成します。</span><span class="sxs-lookup"><span data-stu-id="9e06e-122">Create a custom app setup policy</span></span>

<span data-ttu-id="9e06e-123">マイクロソフトのチームの管理センターを使用すると、カスタム ポリシーを作成します。</span><span class="sxs-lookup"><span data-stu-id="9e06e-123">You can use the Microsoft Teams admin center to create a custom policy.</span></span>

1. <span data-ttu-id="9e06e-124">マイクロソフトのチーム管理センターの左側のナビゲーションで**チームのアプリケーション**に移動する > **のポリシーを設定**します。</span><span class="sxs-lookup"><span data-stu-id="9e06e-124">In the left navigation of the Microsoft Teams admin center, go to **Teams apps** > **Setup policies**.</span></span>
2. <span data-ttu-id="9e06e-125">**新しいポリシー**を選択します。</span><span class="sxs-lookup"><span data-stu-id="9e06e-125">Select **New policy**.</span></span>
3. <span data-ttu-id="9e06e-126">ポリシーのわかりやすい名前を入力し、[**アプリケーションの追加**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="9e06e-126">Enter a descriptive name for the policy, and then click **Add apps**.</span></span>
4. <span data-ttu-id="9e06e-127">**追加には、アプリが固定されている**ウィンドウで、アプリケーションの**追加**] をクリックし、追加する検索します。</span><span class="sxs-lookup"><span data-stu-id="9e06e-127">In the **Add pinned apps** pane, search for the apps you want to add, and then click **Add**.</span></span> <span data-ttu-id="9e06e-128">アプリケーションのアクセス許可ポリシーによってアプリケーションを抽出することもできます。</span><span class="sxs-lookup"><span data-stu-id="9e06e-128">You can also filter apps by app permission policy.</span></span> <span data-ttu-id="9e06e-129">アプリケーションの一覧を選択したら、[**追加**を] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="9e06e-129">When you've chosen your list of apps, click **Add**.</span></span>

     ![アプリケーション ・ セットアップ ・ ポリシーの追加-apps.png](media/app-setup-policies-add-apps.png)

5. <span data-ttu-id="9e06e-131">**保存**] をクリックし、チームの順序でアプリケーションを配置します。</span><span class="sxs-lookup"><span data-stu-id="9e06e-131">Arrange the apps in the order that you want them to appear in Teams, and then click **Save**.</span></span>

    ![app-setup-policies-new-policy-setup.png](media/app-setup-policies-new-policy-setup.png)

## <a name="edit-an-app-setup-policy"></a><span data-ttu-id="9e06e-133">アプリケーション設定ポリシーを編集します。</span><span class="sxs-lookup"><span data-stu-id="9e06e-133">Edit an app setup policy</span></span>

<span data-ttu-id="9e06e-134">グローバル (組織) のポリシー、カスタム ポリシーを作成するなど、ポリシーを編集するのには、マイクロソフトのチームの管理センターを使用できます。</span><span class="sxs-lookup"><span data-stu-id="9e06e-134">You can use the Microsoft Teams admin center to edit a policy, including the global (Org-wide default) policy and custom policies that you create.</span></span>

1. <span data-ttu-id="9e06e-135">マイクロソフトのチーム管理センターの左側のナビゲーションで**チームのアプリケーション**に移動する > **のポリシーを設定**します。</span><span class="sxs-lookup"><span data-stu-id="9e06e-135">In the left navigation of the Microsoft Teams admin center, go to **Teams apps** > **Setup policies**.</span></span>
2. <span data-ttu-id="9e06e-136">編集するポリシーを選択します。</span><span class="sxs-lookup"><span data-stu-id="9e06e-136">Select the policy you want to edit.</span></span> 
3. <span data-ttu-id="9e06e-137">ここでは、変更します。</span><span class="sxs-lookup"><span data-stu-id="9e06e-137">From here, make the changes that you want.</span></span> <span data-ttu-id="9e06e-138">追加、削除、およびアプリケーションの順序を変更することができます。</span><span class="sxs-lookup"><span data-stu-id="9e06e-138">You can add, remove, and change the order of apps.</span></span>
4. <span data-ttu-id="9e06e-139">**[保存]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="9e06e-139">Click **Save**.</span></span>

## <a name="assign-a-custom-app-setup-policy-to-users"></a><span data-ttu-id="9e06e-140">カスタム アプリケーション設定のポリシーをユーザーに割り当てる</span><span class="sxs-lookup"><span data-stu-id="9e06e-140">Assign a custom app setup policy to users</span></span>

<span data-ttu-id="9e06e-141">カスタム ポリシーを個々 のユーザーまたはセキュリティ グループなど、ユーザーのグループまたは配布グループをカスタム ポリシーを割り当てるには、ビジネスの PowerShell モジュールの Skype を割り当てるには、マイクロソフトのチームの管理センターを使用できます。</span><span class="sxs-lookup"><span data-stu-id="9e06e-141">You can use the Microsoft Teams admin center to assign a custom policy to individual users or the Skype for Business PowerShell module  to assign a custom policy to groups of users, such as a security group or distribution group.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="9e06e-142">PowerShell を使用して、ユーザーにポリシーを割り当てることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="9e06e-142">We recommend using PowerShell only to assign policies to users.</span></span> <span data-ttu-id="9e06e-143">作成、編集、およびポリシーを管理するには、マイクロソフトのチームの管理センターを使用します。</span><span class="sxs-lookup"><span data-stu-id="9e06e-143">Use the Microsoft Teams admin center to create, edit, and manage policies.</span></span>

### <a name="assign-a-custom-app-setup-policy-to-individual-users"></a><span data-ttu-id="9e06e-144">カスタム アプリケーション設定のポリシーを個々 のユーザーに割り当てる</span><span class="sxs-lookup"><span data-stu-id="9e06e-144">Assign a custom app setup policy to individual users</span></span>

1. <span data-ttu-id="9e06e-145">マイクロソフトのチーム管理センターの左側のナビゲーションでは、**ユーザー**に移動し、し、[ユーザー] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="9e06e-145">In the left navigation of the Microsoft Teams admin center, go to **Users**, and then click  the user.</span></span>
2. <span data-ttu-id="9e06e-146">**[割り当てられているポリシー]** の隣にある **[編集]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="9e06e-146">Next to **Assigned policies**, choose **Edit**.</span></span>
3. <span data-ttu-id="9e06e-147">**チームのアプリケーション設定のポリシー**では、アプリケーションの設定ポリシーを割り当てるを選択し、**保存**します。</span><span class="sxs-lookup"><span data-stu-id="9e06e-147">Under **Teams App Setup policy**, select the app setup policy you want to assign, and then choose **Save**.</span></span>

    ![アプリケーション ・ セットアップ ・ ポリシーの割り当て-policy.png](media/app-setup-policies-assign-policy.png)

### <a name="assign-a-custom-app-setup-policy-to-users-in-a-group"></a><span data-ttu-id="9e06e-149">グループ内のユーザーにカスタム アプリケーション設定のポリシーを割り当てる</span><span class="sxs-lookup"><span data-stu-id="9e06e-149">Assign a custom app setup policy to users in a group</span></span>

<span data-ttu-id="9e06e-150">既に認められた複数のユーザーにカスタム アプリケーション設定ポリシーを設定することがあります。</span><span class="sxs-lookup"><span data-stu-id="9e06e-150">You may want to assign a custom app setup policy to multiple users that you’ve already identified.</span></span> <span data-ttu-id="9e06e-151">などのセキュリティ グループ内のすべてのユーザーにポリシーを設定する場合があります。</span><span class="sxs-lookup"><span data-stu-id="9e06e-151">For example, you may want to assign a policy to all users in a security group.</span></span> <span data-ttu-id="9e06e-152">グラフ モジュールの Azure Active Directory PowerShell およびビジネスの PowerShell モジュールの Skype への接続で、これを行うことができます。</span><span class="sxs-lookup"><span data-stu-id="9e06e-152">You can do this by connecting to the Azure Active Directory PowerShell for Graph module and the Skype for Business PowerShell module.</span></span> <span data-ttu-id="9e06e-153">PowerShell を使用して Teams を管理する方法の詳細については、「[Teams での PowerShell の概要](teams-powershell-overview.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9e06e-153">For more information about using PowerShell to manage Teams, see [Teams PowerShell Overview](teams-powershell-overview.md).</span></span>

<span data-ttu-id="9e06e-154">この例では、contoso 社の製薬会社の人事プロジェクト グループ内のすべてのユーザーに HR アプリケーションのセットアップのポリシーと呼ばれるカスタム アプリケーション設定のポリシーを割り当てます。</span><span class="sxs-lookup"><span data-stu-id="9e06e-154">In this example, we assign a custom app setup policy called HR App Setup Policy to all users in the Contoso Pharmaceuticals HR Project group.</span></span>  

> [!NOTE]
> <span data-ttu-id="9e06e-155">「[単一の Windows PowerShell ウィンドウですべての Office 365 サービスに接続する](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-all-office-365-services-in-a-single-windows-powershell-window)」の手順に従って、必ず最初に Azure Active Directory PowerShell for Graph モジュールと Skype for Business PowerShell モジュールに接続してください。</span><span class="sxs-lookup"><span data-stu-id="9e06e-155">Make sure you first connect to the Azure Active Directory PowerShell for Graph module and Skype for Business PowerShell module by following the steps in [Connect to all Office 365 services in a single Windows PowerShell window](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-all-office-365-services-in-a-single-windows-powershell-window).</span></span>

<span data-ttu-id="9e06e-156">特定のグループの GroupObjectId を取得します。</span><span class="sxs-lookup"><span data-stu-id="9e06e-156">Get the GroupObjectId of the particular group.</span></span>
```
$group = Get-AzureADGroup -SearchString "Contoso Pharmaceuticals HR Project"
```
<span data-ttu-id="9e06e-157">指定したグループのメンバーを取得します。</span><span class="sxs-lookup"><span data-stu-id="9e06e-157">Get the members of the specified group.</span></span>
```
$members = Get-AzureADGroupMember -ObjectId $group.ObjectId -All $true | Where-Object {$_.ObjectType -eq "User"}
```
<span data-ttu-id="9e06e-158">特定アプリケーションの設定のポリシーをグループ内のすべてのユーザーを割り当てます。</span><span class="sxs-lookup"><span data-stu-id="9e06e-158">Assign all users in the group to a particular app setup policy.</span></span> <span data-ttu-id="9e06e-159">この例では、HR アプリケーションの設定のポリシーを勧めします。</span><span class="sxs-lookup"><span data-stu-id="9e06e-159">In this example, it's HR App Setup Policy.</span></span>
```
$members | ForEach-Object { Grant-CsTeamsAppSetupPolicy -PolicyName "HR App Setup Policy" -Identity $_.EmailAddress}
``` 
<span data-ttu-id="9e06e-160">グループ内のメンバー数によっては、このコマンドの実行に数分かかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="9e06e-160">Depending on the number of members in the group, this command may take several minutes to execute.</span></span>

## <a name="faq"></a><span data-ttu-id="9e06e-161">FAQ</span><span class="sxs-lookup"><span data-stu-id="9e06e-161">FAQ</span></span>

### <a name="working-with-app-setup-policies"></a><span data-ttu-id="9e06e-162">アプリケーション設定のポリシーを使用します。</span><span class="sxs-lookup"><span data-stu-id="9e06e-162">Working with app setup policies</span></span>

#### <a name="what-built-in-app-setup-policies-are-included-in-the-microsoft-teams-admin-center"></a><span data-ttu-id="9e06e-163">マイクロソフトのチームの管理センターでは、どのような組み込みのアプリケーション設定のポリシーが含まれますか。</span><span class="sxs-lookup"><span data-stu-id="9e06e-163">What built-in app setup policies are included in the Microsoft Teams admin center?</span></span>

- <span data-ttu-id="9e06e-164">**グローバル (組織全体の既定値)**: 別のポリシーを割り当てない限り、組織内のすべてのユーザーがこの既定のポリシーが適用されます。</span><span class="sxs-lookup"><span data-stu-id="9e06e-164">**Global (Org-wide default)**: This default policy applies to all users in your organization unless you assign another policy.</span></span> <span data-ttu-id="9e06e-165">暗証番号 (pin) アプリでは、ユーザーにとって最も重要なグローバル ポリシーを編集します。</span><span class="sxs-lookup"><span data-stu-id="9e06e-165">Edit the global policy to pin apps that are most important for your users.</span></span>
- <span data-ttu-id="9e06e-166">**FirstLineWorker**: このポリシーは、先頭行の作業者に対して。</span><span class="sxs-lookup"><span data-stu-id="9e06e-166">**FirstLineWorker**: This policy is for firstline workers.</span></span> <span data-ttu-id="9e06e-167">先頭行の作業者に、組織内、ことを割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="9e06e-167">You can assign it to firstline workers in your organization.</span></span> <span data-ttu-id="9e06e-168">カスタム ポリシーを作成することによりのようなあること設定をアクティブにするためにユーザーにポリシーを割り当てることを知っているが重要です。</span><span class="sxs-lookup"><span data-stu-id="9e06e-168">It's important to know that like custom policies that you create, you have to assign the policy to users for the settings to be active.</span></span> <span data-ttu-id="9e06e-169">詳細については、この資料の「[カスタム アプリケーション設定のポリシーをユーザーに割り当てる](#assign-a-custom-app-setup-policy-to-users)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9e06e-169">For more information, go to the [Assign a custom app setup policy to users](#assign-a-custom-app-setup-policy-to-users) section of this article.</span></span>

#### <a name="why-cant-i-find-an-app-in-the-add-pinned-apps-pane"></a><span data-ttu-id="9e06e-170">固定されたアプリケーションの追加] ウィンドウでアプリケーションを見つけることができないのはなぜでしょうか。</span><span class="sxs-lookup"><span data-stu-id="9e06e-170">Why can't I find an app in the Add pinned apps pane?</span></span>

<span data-ttu-id="9e06e-171">すべてのアプリケーション追加するにはチーム、アプリケーション設定のポリシーを使用します。</span><span class="sxs-lookup"><span data-stu-id="9e06e-171">Not all apps can be pinned to Teams through an app setup policy.</span></span> <span data-ttu-id="9e06e-172">いくつかのアプリケーションは、この機能をサポートしない可能性があります。</span><span class="sxs-lookup"><span data-stu-id="9e06e-172">Some apps may not support this functionality.</span></span> <span data-ttu-id="9e06e-173">固定できるアプリケーションを見つけるには、アプリケーションの**追加には、アプリが固定されている**ウィンドウ内の検索してください。</span><span class="sxs-lookup"><span data-stu-id="9e06e-173">To find apps that can be pinned, search for the app in the **Add pinned apps** pane.</span></span> <span data-ttu-id="9e06e-174">チームのデスクトップ クライアントに個人の範囲 (静的タブ)、bot が設定されているタブを固定することができます、これらのアプリケーションの**追加には、アプリが固定されている**ウィンドウで利用可能なです。</span><span class="sxs-lookup"><span data-stu-id="9e06e-174">Tabs that have a personal scope (static tabs) and bots can be pinned to the Teams desktop client and these apps are available in the **Add pinned apps** pane.</span></span>

<span data-ttu-id="9e06e-175">チームのアプリケーション ストアでは、**固定されている追加のアプリケーション**ウィンドウに追加するにはチームのポリシーを使用するアプリケーションのみが含まれていますに、チームのすべてのアプリケーションが一覧表示されることに留意してください。</span><span class="sxs-lookup"><span data-stu-id="9e06e-175">Keep in mind that the Teams app store lists all Teams apps whereas the **Add pinned apps** pane includes only apps that can be pinned to Teams through a policy.</span></span> 

#### <a name="im-a-teams-for-education-admin-what-do-i-need-to-know-about-app-setup-policies-in-teams-for-education"></a><span data-ttu-id="9e06e-176">私は、チームの管理者の教育教育のチームでのアプリケーション設定のポリシーについて理解するには何が必要でしょうか。</span><span class="sxs-lookup"><span data-stu-id="9e06e-176">I'm a Teams for Education admin. What do I need to know about app setup policies in Teams for Education?</span></span>

<span data-ttu-id="9e06e-177">通話アプリでは、チームの教育では使用できません。</span><span class="sxs-lookup"><span data-stu-id="9e06e-177">The Calling app isn't available in Teams for Education.</span></span> <span data-ttu-id="9e06e-178">新しいカスタム アプリケーション設定のポリシーを作成するときは、アプリの一覧で通話アプリが表示されます。</span><span class="sxs-lookup"><span data-stu-id="9e06e-178">When you create a new custom app setup policy, the Calling app is displayed in the list of apps.</span></span> <span data-ttu-id="9e06e-179">ただし、アプリケーションは、クライアントのチームに固定表示されていないし、教育のユーザーのチームがチームでの呼び出しアプリケーションに表示されません。</span><span class="sxs-lookup"><span data-stu-id="9e06e-179">However, the app isn't pinned to Teams clients and Teams for Education users won't see the Calls app in Teams.</span></span> 

#### <a name="how-many-apps-can-be-added-to-a-policy"></a><span data-ttu-id="9e06e-180">どのように多くのアプリケーションは、ポリシーに追加できますか。</span><span class="sxs-lookup"><span data-stu-id="9e06e-180">How many apps can be added to a policy?</span></span>

<span data-ttu-id="9e06e-181">最低 2 つのアプリケーションは、チームのモバイル クライアント (iOS および Android) に固定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9e06e-181">A minimum of two apps must be pinned to the Teams mobile clients (iOS and Android).</span></span> <span data-ttu-id="9e06e-182">ポリシーに 2 つ以上のアプリケーションがある場合は、モバイル クライアントはポリシーの設定は反映されず、代わりには引き続き既存の構成を使用します。</span><span class="sxs-lookup"><span data-stu-id="9e06e-182">If a policy has less than two apps, the mobile clients won't reflect the policy settings and instead will continue to use the existing configuration.</span></span>

#### <a name="how-long-does-it-take-for-policy-changes-to-take-effect"></a><span data-ttu-id="9e06e-183">ポリシーの変更を有効にするためにどのくらい時間がかかりますか。</span><span class="sxs-lookup"><span data-stu-id="9e06e-183">How long does it take for policy changes to take effect?</span></span>

<span data-ttu-id="9e06e-184">グローバル ポリシーを編集またはポリシーを設定すると、変更を反映させるには、最大で 24 時間がかかることができます。</span><span class="sxs-lookup"><span data-stu-id="9e06e-184">After you edit the global policy or assign a policy, it can take up to 24 hours for changes to take effect.</span></span>

### <a name="user-experience"></a><span data-ttu-id="9e06e-185">ユーザー エクスペリエンス</span><span class="sxs-lookup"><span data-stu-id="9e06e-185">User experience</span></span>

#### <a name="how-can-users-see-all-their-pinned-apps-in-teams"></a><span data-ttu-id="9e06e-186">ユーザーはチーム内のすべてが固定されたアプリをどのように表示できますか。</span><span class="sxs-lookup"><span data-stu-id="9e06e-186">How can users see all their pinned apps in Teams?</span></span>

<span data-ttu-id="9e06e-187">ユーザーが指定されているすべてのアプリケーションを表示するには、ユーザーはインストールされたアプリの数とそのチームのクライアント ウィンドウのサイズに応じて以下を実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9e06e-187">To view all apps that are pinned for a user, users may have to do the following depending on the number of installed apps and the size of their Teams client window.</span></span>

|<span data-ttu-id="9e06e-188">チームのデスクトップ クライアント</span><span class="sxs-lookup"><span data-stu-id="9e06e-188">Teams desktop client</span></span> |<span data-ttu-id="9e06e-189">モバイル クライアントのチーム</span><span class="sxs-lookup"><span data-stu-id="9e06e-189">Teams mobile client</span></span> |
|---------|---------|
|<span data-ttu-id="9e06e-190">チームの横に、アプリケーション バーでは、**をクリックします。複数のアプリケーション**。</span><span class="sxs-lookup"><span data-stu-id="9e06e-190">In the app bar on the side of Teams, click **... More apps**.</span></span>| <span data-ttu-id="9e06e-191">チームの下部にあるアプリケーション バーを機械に通します。</span><span class="sxs-lookup"><span data-stu-id="9e06e-191">In the app bar near the bottom of Teams, swipe up.</span></span>|
|![app-setup-policies-desktop-more-apps.png](media/app-setup-policies-desktop-more-apps.png)<br>   |![app-setup-policies-mobile-more-apps.png](media/app-setup-policies-mobile-more-apps.png)  

#### <a name="what-do-i-need-to-know-about-the-teams-mobile-experience"></a><span data-ttu-id="9e06e-194">チーム モバイル エクスペリエンスについて理解するには何が必要でしょうか。</span><span class="sxs-lookup"><span data-stu-id="9e06e-194">What do I need to know about the Teams mobile experience?</span></span>

<span data-ttu-id="9e06e-195">チームのモバイル クライアント (iOS および Android) 静的タブで個人用のアプリケーションが現在サポートされていません。</span><span class="sxs-lookup"><span data-stu-id="9e06e-195">The Teams mobile clients (iOS and Android) currently don't support personal apps with static tabs.</span></span> <span data-ttu-id="9e06e-196">アプリケーション ポリシーの設定によってチームのデスクトップ クライアントに固定されているアプリケーションは、可能性があります、チームのモバイル クライアントでは表示されません。</span><span class="sxs-lookup"><span data-stu-id="9e06e-196">Depending on the apps set in the policy, apps pinned to the Teams desktop client might not appear in the Teams mobile clients.</span></span> <span data-ttu-id="9e06e-197">個人 bot は、モバイル クライアントのチャットにも表示されます。</span><span class="sxs-lookup"><span data-stu-id="9e06e-197">Personal bots will still appear in Chat on mobile clients.</span></span>

<span data-ttu-id="9e06e-198">チームのモバイル クライアントでは、ユーザーはアクティビティ、チャット、チームなどのコア ・ チームのアプリケーションを参照してくださいし、シフトなど、マイクロソフトからいくつかのファースト パーティのアプリケーションを固定することができます。</span><span class="sxs-lookup"><span data-stu-id="9e06e-198">With the Teams mobile clients, users will see core Teams apps such as Activity, Chat, and Teams, and you can pin some first-party apps from Microsoft, such as Shifts.</span></span>

#### <a name="can-users-change-the-order-of-apps-pinned-through-a-policy"></a><span data-ttu-id="9e06e-199">ユーザーは、ポリシーによって固定されているアプリケーションの順序を変更できますか。</span><span class="sxs-lookup"><span data-stu-id="9e06e-199">Can users change the order of apps pinned through a policy?</span></span>

<span data-ttu-id="9e06e-200">現時点では、ユーザーは、チームのモバイル クライアントではなくチームのデスクトップまたは web クライアントは、固定されたアプリケーションの順序を変更することができます。</span><span class="sxs-lookup"><span data-stu-id="9e06e-200">Currently, users can change the order of their pinned apps on Teams mobile clients but not on the Teams desktop or web clients.</span></span> 

### <a name="custom-teams-apps"></a><span data-ttu-id="9e06e-201">サバイバル-カスタム アプリケーション</span><span class="sxs-lookup"><span data-stu-id="9e06e-201">Custom Teams apps</span></span>

#### <a name="my-organization-built-a-custom-teams-app-and-published-it-either-to-appsource-or-the-tenant-app-catalog-but-the-app-icon-isnt-displayed-as-expected-when-the-app-is-pinned-to-the-app-bar-in-teams-how-do-i-fix-it"></a><span data-ttu-id="9e06e-202">自分の所属組織のカスタム チームのアプリケーションをビルドおよび発行、AppSource またはテナント アプリケーション カタログには、アプリケーションをチームでアプリケーション バーを固定するときに期待どおりにアプリケーションのアイコンが表示されていません。</span><span class="sxs-lookup"><span data-stu-id="9e06e-202">My organization built a custom Teams app and published it, either to AppSource or the Tenant app catalog, but the app icon isn't displayed as expected when the app is pinned to the app bar in Teams.</span></span> <span data-ttu-id="9e06e-203">どのように修正しますか。</span><span class="sxs-lookup"><span data-stu-id="9e06e-203">How do I fix it?</span></span> 

<span data-ttu-id="9e06e-204">アプリケーションを送信する前に、ロゴのガイドラインに従うことを確認します。</span><span class="sxs-lookup"><span data-stu-id="9e06e-204">Make sure that you follow the logo guidelines before you submit the app.</span></span> <span data-ttu-id="9e06e-205">詳細については、[販売者のダッシュ ボードの提出書類のチェックリスト](https://docs.microsoft.com/microsoftteams/platform/publishing/office-store-checklist)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9e06e-205">To learn more, see [Checklist for Seller Dashboard submission](https://docs.microsoft.com/microsoftteams/platform/publishing/office-store-checklist).</span></span> 

 ## <a name="related-topics"></a><span data-ttu-id="9e06e-206">関連項目</span><span class="sxs-lookup"><span data-stu-id="9e06e-206">Related topics</span></span>
- [<span data-ttu-id="9e06e-207">Teams でのアプリの管理設定</span><span class="sxs-lookup"><span data-stu-id="9e06e-207">Admin settings for apps in Teams</span></span>](admin-settings.md)
- [<span data-ttu-id="9e06e-208">チームでのアプリケーションのアクセス許可ポリシーを管理します。</span><span class="sxs-lookup"><span data-stu-id="9e06e-208">Manage app permission policies in Teams</span></span>](teams-app-permission-policies.md)
- [<span data-ttu-id="9e06e-209">カスタム アプリケーションのポリシーおよびチームの設定を管理します。</span><span class="sxs-lookup"><span data-stu-id="9e06e-209">Manage custom app policies and settings in Teams</span></span>](teams-custom-app-policies-and-settings.md)
- [<span data-ttu-id="9e06e-210">テナント アプリケーション カタログにチームのクライアントからアプリケーションを発行します。</span><span class="sxs-lookup"><span data-stu-id="9e06e-210">Publish an app to the Tenant Apps Catalog from the Teams client</span></span>](tenant-apps-catalog-teams.md)
