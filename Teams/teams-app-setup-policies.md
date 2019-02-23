---
title: Microsoft Teams のアプリのセットアップ ポリシーを管理する
author: lanachin
ms.author: v-lanac
manager: serdars
ms.date: 2/11/2019
ms.reviewer: larryjin
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
description: マイクロソフトのチームおよび組織内のユーザーのチームをカスタマイズするのには暗証番号 (pin) のアプリケーションを使用するアプリケーション設定のポリシーについて説明します。
ROBOTS: NOINDEX, NOFOLLOW
ms.openlocfilehash: 4e6ad41dac9021079bffa80284809733c39f3cc9
ms.sourcegitcommit: ad126165b6440b98e550ab48e6b3491aeba9402b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/22/2019
ms.locfileid: "30205764"
---
# <a name="manage-app-setup-policies-in-microsoft-teams"></a><span data-ttu-id="1377b-103">Microsoft Teams のアプリのセットアップ ポリシーを管理する</span><span class="sxs-lookup"><span data-stu-id="1377b-103">Manage app setup policies in Microsoft Teams</span></span>

> [!INCLUDE [Preview customer token](includes/preview-feature.md)]

<span data-ttu-id="1377b-104">管理者としては、マイクロソフトのチームは、ユーザーにとって最も重要なアプリケーションを強調表示をカスタマイズするのにはアプリケーションの設定のポリシーを使用できます。</span><span class="sxs-lookup"><span data-stu-id="1377b-104">As an admin, you can use app setup policies to customize Microsoft Teams to highlight the apps that are most important for your users.</span></span> <span data-ttu-id="1377b-105">固定し、表示される順序を設定するアプリケーションを選択します。</span><span class="sxs-lookup"><span data-stu-id="1377b-105">You choose the apps to pin and set the order that they appear.</span></span> <span data-ttu-id="1377b-106">アプリケーション設定のポリシーを使用するサード ・ パーティまたは組織内の開発者によって構築されたものなど、組織内のユーザーを必要とするアプリケーションを紹介します。</span><span class="sxs-lookup"><span data-stu-id="1377b-106">App setup policies let you showcase apps that users in your organization need, including ones built by third parties or by developers in your organization.</span></span> <span data-ttu-id="1377b-107">どの組み込みの機能を管理するアプリケーション設定のポリシーを使用することも表示されます。</span><span class="sxs-lookup"><span data-stu-id="1377b-107">You can also use app setup policies to manage how built-in features appear.</span></span>

<span data-ttu-id="1377b-108">アプリケーション バーには、アプリが固定されています。</span><span class="sxs-lookup"><span data-stu-id="1377b-108">Apps are pinned to the app bar.</span></span> <span data-ttu-id="1377b-109">これは、チームのデスクトップ クライアント側にし、チームのモバイル クライアント (iOS および Android) の下部にあるバーです。</span><span class="sxs-lookup"><span data-stu-id="1377b-109">This is the bar on the side of the Teams desktop client and at the bottom of the Teams mobile clients (iOS and Android).</span></span> 

|<span data-ttu-id="1377b-110">チームのデスクトップ クライアント</span><span class="sxs-lookup"><span data-stu-id="1377b-110">Teams desktop client</span></span>  |<span data-ttu-id="1377b-111">モバイル クライアントのチーム</span><span class="sxs-lookup"><span data-stu-id="1377b-111">Teams mobile client</span></span> |
|---------|---------|
|![app-setup-policies-desktop-app-bar.png](media/app-setup-policies-desktop-app-bar.png)<br>  |   ![app-setup-policies-mobile-app-bar.png](media/app-setup-policies-mobile-app-bar.png)      |

<span data-ttu-id="1377b-114">マイクロソフトのチームの管理センターでのアプリケーション設定のポリシーを管理します。</span><span class="sxs-lookup"><span data-stu-id="1377b-114">You manage app setup policies in the Microsoft Teams admin center.</span></span> <span data-ttu-id="1377b-115">グローバル (組織全体の既定値) ポリシーを使用して、またはカスタム ポリシーを作成してユーザーに割り当てます。</span><span class="sxs-lookup"><span data-stu-id="1377b-115">You can use the global (Org-wide default) policy or create custom policies and assign them to users.</span></span> <span data-ttu-id="1377b-116">組織内のユーザーを作成し、カスタム ・ ポリシーを設定しない限り、グローバル ポリシーが自動的に表示されます。</span><span class="sxs-lookup"><span data-stu-id="1377b-116">Users in your organization will automatically get the global policy unless you create and assign a custom policy.</span></span>

<span data-ttu-id="1377b-117">アプリケーションを含めるには、グローバル ポリシーの設定を編集することができます。</span><span class="sxs-lookup"><span data-stu-id="1377b-117">You can edit the settings in the global policy to include the apps that you want.</span></span> <span data-ttu-id="1377b-118">チーム、組織内のユーザーのグループごとにカスタマイズする場合は、作成し、1 つまたは複数のカスタム ポリシーを割り当てます。</span><span class="sxs-lookup"><span data-stu-id="1377b-118">If you want to customize Teams for different groups of users in your organization, create and assign one or more custom policies.</span></span>

![アプリケーション ・ セットアップ ・ policies.png](media/app-setup-policies.png)

> [!NOTE]
> <span data-ttu-id="1377b-120">ユーザーには、カスタム ポリシーが割り当てられているが場合、は、ユーザーにそのポリシーが適用されます。</span><span class="sxs-lookup"><span data-stu-id="1377b-120">If a user is assigned a custom policy, that policy applies to the user.</span></span> <span data-ttu-id="1377b-121">ユーザーには、カスタム ポリシーが割り当てられていない、グローバル ポリシーがユーザーに適用されます。</span><span class="sxs-lookup"><span data-stu-id="1377b-121">If a user isn't assigned a custom policy, the global policy applies to the user.</span></span>

## <a name="create-a-custom-app-setup-policy"></a><span data-ttu-id="1377b-122">カスタム アプリケーション設定のポリシーを作成します。</span><span class="sxs-lookup"><span data-stu-id="1377b-122">Create a custom app setup policy</span></span>

<span data-ttu-id="1377b-123">マイクロソフトのチーム管理センターまたは Windows PowerShell を使用すると、カスタム ポリシーを作成します。</span><span class="sxs-lookup"><span data-stu-id="1377b-123">You can use the Microsoft Teams admin center or Windows PowerShell to create a custom policy.</span></span>

1. <span data-ttu-id="1377b-124">マイクロソフトのチーム管理センターの左側のナビゲーションでは、**チームのアプリケーション**に移動 > **アプリケーションの設定のポリシー**です。</span><span class="sxs-lookup"><span data-stu-id="1377b-124">In the left navigation of the Microsoft Teams admin center, go to **Teams app** > **App setup policies**.</span></span>
2. <span data-ttu-id="1377b-125">**新しいポリシー**を選択します。</span><span class="sxs-lookup"><span data-stu-id="1377b-125">Select **New policy**.</span></span>
3. <span data-ttu-id="1377b-126">ポリシーのわかりやすい名前を入力し、[**アプリケーションの追加**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="1377b-126">Enter a descriptive name for the policy, and then click **Add apps**.</span></span>
4. <span data-ttu-id="1377b-127">**追加には、アプリが固定されている**ウィンドウで、アプリケーションの**追加**] をクリックし、追加する検索します。</span><span class="sxs-lookup"><span data-stu-id="1377b-127">In the **Add pinned apps** pane, search for the apps you want to add, and then click **Add**.</span></span>  <span data-ttu-id="1377b-128">すべてのアプリケーションの一覧を表示するには、**チームのアプリケーションの保存**を選択します。</span><span class="sxs-lookup"><span data-stu-id="1377b-128">To see a list of all    apps, select **Teams app store**.</span></span> <span data-ttu-id="1377b-129">アプリケーションの一覧を選択したら、[**追加**を] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="1377b-129">When you've chosen your list of apps, click **Add**.</span></span>

     ![アプリケーション ・ セットアップ ・ ポリシーの追加-apps.png](media/app-setup-policies-add-apps.png)

5. <span data-ttu-id="1377b-131">**保存**] をクリックし、チームの順序でアプリケーションを配置します。</span><span class="sxs-lookup"><span data-stu-id="1377b-131">Arrange the apps in the order that you want them to appear in Teams, and then click **Save**.</span></span>

    ![app-setup-policies-new-policy-setup.png](media/app-setup-policies-new-policy-setup.png)

## <a name="edit-an-app-setup-policy"></a><span data-ttu-id="1377b-133">アプリケーション設定ポリシーを編集します。</span><span class="sxs-lookup"><span data-stu-id="1377b-133">Edit an app setup policy</span></span>

<span data-ttu-id="1377b-134">グローバル (組織) のポリシー、カスタム ポリシーを作成するなど、ポリシーを編集するのには、マイクロソフトのチーム管理センターまたは Windows PowerShell を使用できます。</span><span class="sxs-lookup"><span data-stu-id="1377b-134">You can use the Microsoft Teams admin center or Windows PowerShell to edit a policy, including the global (Org-wide default) policy and custom policies that you create.</span></span> 

1. <span data-ttu-id="1377b-135">マイクロソフトのチーム管理センターの左側のナビゲーションでは、**チームのアプリケーション**に移動 > **アプリケーションの設定のポリシー**です。</span><span class="sxs-lookup"><span data-stu-id="1377b-135">In the left navigation of the Microsoft Teams admin center, go to **Teams app** > **App setup policies**.</span></span>
2. <span data-ttu-id="1377b-136">編集するポリシーを選択します。</span><span class="sxs-lookup"><span data-stu-id="1377b-136">Select the policy you want to edit.</span></span> 
3. <span data-ttu-id="1377b-137">ここでは、変更します。</span><span class="sxs-lookup"><span data-stu-id="1377b-137">From here, make the changes that you want.</span></span> <span data-ttu-id="1377b-138">追加、削除、およびアプリケーションの順序を変更することができます。</span><span class="sxs-lookup"><span data-stu-id="1377b-138">You can add, remove, and change the order of apps.</span></span>
4. <span data-ttu-id="1377b-139">[**保存**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="1377b-139">Click **Save**.</span></span> 

## <a name="assign-a-custom-app-setup-policy-to-users"></a><span data-ttu-id="1377b-140">カスタム アプリケーション設定のポリシーをユーザーに割り当てる</span><span class="sxs-lookup"><span data-stu-id="1377b-140">Assign a custom app setup policy to users</span></span>

<span data-ttu-id="1377b-141">個々 のユーザーまたはセキュリティ グループなど、ユーザーのグループまたは配布グループをカスタム ポリシーを割り当てるには、Windows PowerShell にカスタム ポリシーを設定するのには、マイクロソフトのチームの管理センターを使用できます。</span><span class="sxs-lookup"><span data-stu-id="1377b-141">You can use the Microsoft Teams admin center to assign a custom policy to individual users or Windows PowerShell to assign a custom policy to groups of users, such as a security group or distribution group.</span></span>

### <a name="assign-a-custom-app-setup-policy-to-individual-users"></a><span data-ttu-id="1377b-142">カスタム アプリケーション設定のポリシーを個々 のユーザーに割り当てる</span><span class="sxs-lookup"><span data-stu-id="1377b-142">Assign a custom app setup policy to individual users</span></span>

1. <span data-ttu-id="1377b-143">マイクロソフトのチーム管理センターの左側のナビゲーションでは、**ユーザー**に移動し、し、[ユーザー] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="1377b-143">In the left navigation of the Microsoft Teams admin center, go to **Users**, and then click       the user.</span></span>
2. <span data-ttu-id="1377b-144">**割り当てポリシー**] の横にある [**編集**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="1377b-144">Next to **Assigned policies**, choose **Edit**.</span></span>
3. <span data-ttu-id="1377b-145">**チームのアプリケーション設定のポリシー**では、アプリケーションの設定ポリシーを割り当てるを選択し、**保存**します。</span><span class="sxs-lookup"><span data-stu-id="1377b-145">Under **Teams App Setup policy**, select the app setup policy you want to assign, and then choose **Save**.</span></span>

    ![アプリケーション ・ セットアップ ・ ポリシーの割り当て-policy.png](media/app-setup-policies-assign-policy.png)

### <a name="assign-a-custom-app-setup-policy-to-users-in-a-group"></a><span data-ttu-id="1377b-147">グループ内のユーザーにカスタム アプリケーション設定のポリシーを割り当てる</span><span class="sxs-lookup"><span data-stu-id="1377b-147">Assign a custom app setup policy to users in a group</span></span>

<span data-ttu-id="1377b-148">既に認められた複数のユーザーにカスタム アプリケーション設定ポリシーを設定することがあります。</span><span class="sxs-lookup"><span data-stu-id="1377b-148">You may want to assign a custom app setup policy to multiple users that you’ve already identified.</span></span> <span data-ttu-id="1377b-149">などのセキュリティ グループ内のすべてのユーザーにポリシーを設定する場合があります。</span><span class="sxs-lookup"><span data-stu-id="1377b-149">For example, you may want to assign a policy to all users in a security group.</span></span> <span data-ttu-id="1377b-150">グラフ モジュールの Azure Active Directory PowerShell およびビジネスの PowerShell モジュールの Skype への接続で、これを行うことができます。</span><span class="sxs-lookup"><span data-stu-id="1377b-150">You can do this by connecting to the Azure Active Directory PowerShell for Graph module and the Skype for Business PowerShell module.</span></span> <span data-ttu-id="1377b-151">PowerShell を使用して、チームを管理する詳細については、[チームの PowerShell の概要](teams-powershell-overview.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1377b-151">For more information about using PowerShell to manage Teams, see [Teams PowerShell Overview](teams-powershell-overview.md).</span></span>

<span data-ttu-id="1377b-152">この例では、contoso 社の製薬会社の人事プロジェクト グループ内のすべてのユーザーに HR アプリケーションのセットアップのポリシーと呼ばれるカスタム アプリケーション設定のポリシーを割り当てます。</span><span class="sxs-lookup"><span data-stu-id="1377b-152">In this example, we assign a custom app setup policy called HR App Setup Policy to all users in the Contoso Pharmaceuticals HR Project group.</span></span>  

> [!NOTE]
> <span data-ttu-id="1377b-153">[1 つの Windows PowerShell のウィンドウ内のすべての Office 365 サービスへの接続](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-all-office-365-services-in-a-single-windows-powershell-window)の手順を実行して、まずグラフ モジュールの Azure Active Directory PowerShell およびビジネスの PowerShell モジュールの Skype に接続することを確認します。</span><span class="sxs-lookup"><span data-stu-id="1377b-153">Make sure you first connect to the Azure Active Directory PowerShell for Graph module and Skype for Business PowerShell module by following the steps in [Connect to all Office 365 services in a single Windows PowerShell window](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-all-office-365-services-in-a-single-windows-powershell-window).</span></span>

<span data-ttu-id="1377b-154">特定のグループの GroupObjectId を取得します。</span><span class="sxs-lookup"><span data-stu-id="1377b-154">Get the GroupObjectId of the particular group.</span></span>
```
$group = Get-AzureADGroup -SearchString "Contoso Pharmaceuticals HR Project"
```
<span data-ttu-id="1377b-155">指定されたグループのメンバーを取得します。</span><span class="sxs-lookup"><span data-stu-id="1377b-155">Get the members of the specified group.</span></span>
```
$members = Get-AzureADGroupMember -ObjectId $group.ObjectId -All $true | Where-Object {$_.ObjectType -eq "User"}
```
<span data-ttu-id="1377b-156">特定アプリケーションの設定のポリシーをグループ内のすべてのユーザーを割り当てます。</span><span class="sxs-lookup"><span data-stu-id="1377b-156">Assign all users in the group to a particular app setup policy.</span></span> <span data-ttu-id="1377b-157">この例では、HR アプリケーションの設定のポリシーを勧めします。</span><span class="sxs-lookup"><span data-stu-id="1377b-157">In this example, it's HR App Setup Policy.</span></span>
```
$members | ForEach-Object { Grant-CsTeamsAppSetupPolicy -PolicyName "HR App Setup Policy" -Identity $_.EmailAddress}
``` 
<span data-ttu-id="1377b-158">数によっては、グループ内のメンバーのこのコマンドは、実行するのに数分をかかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="1377b-158">Depending on the number of members in the group, this command may take several minutes to execute.</span></span>

## <a name="faq"></a><span data-ttu-id="1377b-159">FAQ</span><span class="sxs-lookup"><span data-stu-id="1377b-159">FAQ</span></span>

### <a name="working-with-app-setup-policies"></a><span data-ttu-id="1377b-160">アプリケーション設定のポリシーを使用します。</span><span class="sxs-lookup"><span data-stu-id="1377b-160">Working with app setup policies</span></span>

#### <a name="what-built-in-app-setup-policies-are-included-in-the-microsoft-teams-admin-center"></a><span data-ttu-id="1377b-161">マイクロソフトのチームの管理センターでは、どのような組み込みのアプリケーション設定のポリシーが含まれますか。</span><span class="sxs-lookup"><span data-stu-id="1377b-161">What built-in app setup policies are included in the Microsoft Teams admin center?</span></span>

- <span data-ttu-id="1377b-162">**グローバル (組織全体の既定値)**: 別のポリシーを割り当てない限り、組織内のすべてのユーザーがこの既定のポリシーが適用されます。</span><span class="sxs-lookup"><span data-stu-id="1377b-162">**Global (Org-wide default)**: This default policy applies to all users in your organization unless you assign another policy.</span></span> <span data-ttu-id="1377b-163">暗証番号 (pin) アプリでは、ユーザーにとって最も重要なグローバル ポリシーを編集します。</span><span class="sxs-lookup"><span data-stu-id="1377b-163">Edit the global policy to pin apps that are most important for your users.</span></span>
- <span data-ttu-id="1377b-164">**FirstLineWorker**: このポリシーは、先頭行の作業者に対して。</span><span class="sxs-lookup"><span data-stu-id="1377b-164">**FirstLineWorker**: This policy is for firstline workers.</span></span> <span data-ttu-id="1377b-165">先頭行の作業者に、組織内、ことを割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="1377b-165">You can assign it to firstline workers in your organization.</span></span> <span data-ttu-id="1377b-166">カスタム ポリシーを作成することによりのようなあること設定をアクティブにするためにユーザーにポリシーを割り当てることを知っているが重要です。</span><span class="sxs-lookup"><span data-stu-id="1377b-166">It's important to know that like custom policies that you create, you have to assign the policy to users for the settings to be active.</span></span> <span data-ttu-id="1377b-167">詳細については、この資料の「[カスタム アプリケーション設定のポリシーをユーザーに割り当てる](#assign-a-custom-app-setup-policy-to-users)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1377b-167">For more information, go to the [Assign a custom app setup policy to users](#assign-a-custom-app-setup-policy-to-users) section of this article.</span></span>

#### <a name="why-cant-i-find-an-app-in-the-add-pinned-apps-pane"></a><span data-ttu-id="1377b-168">固定されたアプリケーションの追加] ウィンドウでアプリケーションを見つけることができないのはなぜでしょうか。</span><span class="sxs-lookup"><span data-stu-id="1377b-168">Why can't I find an app in the Add pinned apps pane?</span></span>

<span data-ttu-id="1377b-169">すべてのアプリケーション追加するにはチーム、アプリケーション設定のポリシーを使用します。</span><span class="sxs-lookup"><span data-stu-id="1377b-169">Not all apps can be pinned to Teams through an app setup policy.</span></span> <span data-ttu-id="1377b-170">いくつかのアプリケーションは、この機能をサポートしない可能性があります。</span><span class="sxs-lookup"><span data-stu-id="1377b-170">Some apps may not support this functionality.</span></span> <span data-ttu-id="1377b-171">固定できるアプリケーションを見つけるには、アプリケーションの**追加には、アプリが固定されている**ウィンドウ内の検索してください。</span><span class="sxs-lookup"><span data-stu-id="1377b-171">To find apps that can be pinned, search for the app in the **Add pinned apps** pane.</span></span> <span data-ttu-id="1377b-172">チームのデスクトップ クライアントに個人の範囲 (静的タブ)、bot が設定されているタブを固定することができます、これらのアプリケーションの**追加には、アプリが固定されている**ウィンドウで利用可能なです。</span><span class="sxs-lookup"><span data-stu-id="1377b-172">Tabs that have a personal scope (static tabs) and bots can be pinned to the Teams desktop client and these apps are available in the **Add pinned apps** pane.</span></span>

<span data-ttu-id="1377b-173">チームのアプリケーション ストアでは、**固定されている追加のアプリケーション**ウィンドウに追加するにはチームのポリシーを使用するアプリケーションのみが含まれていますに、チームのすべてのアプリケーションが一覧表示されることに留意してください。</span><span class="sxs-lookup"><span data-stu-id="1377b-173">Keep in mind that the Teams app store lists all Teams apps whereas the **Add pinned apps** pane includes only apps that can be pinned to Teams through a policy.</span></span> 

#### <a name="im-a-teams-for-education-admin-what-do-i-need-to-know-about-app-setup-policies-in-teams-for-education"></a><span data-ttu-id="1377b-174">私は、チームの管理者の教育教育のチームでのアプリケーション設定のポリシーについて理解するには何が必要でしょうか。</span><span class="sxs-lookup"><span data-stu-id="1377b-174">I'm a Teams for Education admin. What do I need to know about app setup policies in Teams for Education?</span></span>

<span data-ttu-id="1377b-175">通話アプリでは、チームの教育では使用できません。</span><span class="sxs-lookup"><span data-stu-id="1377b-175">The Calling app isn't available in Teams for Education.</span></span> <span data-ttu-id="1377b-176">新しいカスタム アプリケーション設定のポリシーを作成するときは、アプリの一覧で通話アプリが表示されます。</span><span class="sxs-lookup"><span data-stu-id="1377b-176">When you create a new custom app setup policy, the Calling app is displayed in the list of apps.</span></span> <span data-ttu-id="1377b-177">ただし、アプリケーションは、クライアントのチームに固定表示されていないし、教育のユーザーのチームがチームでの呼び出しアプリケーションに表示されません。</span><span class="sxs-lookup"><span data-stu-id="1377b-177">However, the app isn't pinned to Teams clients and Teams for Education users won't see the Calls app in Teams.</span></span> 

#### <a name="how-many-apps-can-be-added-to-a-policy"></a><span data-ttu-id="1377b-178">どのように多くのアプリケーションは、ポリシーに追加できますか。</span><span class="sxs-lookup"><span data-stu-id="1377b-178">How many apps can be added to a policy?</span></span>

<span data-ttu-id="1377b-179">最低 2 つのアプリケーションは、チームのモバイル クライアント (iOS および Android) に固定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="1377b-179">A minimum of two apps must be pinned to the Teams mobile clients (iOS and Android).</span></span> <span data-ttu-id="1377b-180">ポリシーに 2 つ以上のアプリケーションがある場合は、モバイル クライアントはポリシーの設定は反映されず、代わりには引き続き既存の構成を使用します。</span><span class="sxs-lookup"><span data-stu-id="1377b-180">If a policy has less than two apps, the mobile clients won't reflect the policy settings and instead will continue to use the existing configuration.</span></span>

#### <a name="how-long-does-it-take-for-policy-changes-to-take-effect"></a><span data-ttu-id="1377b-181">ポリシーの変更を有効にするためにどのくらい時間がかかりますか。</span><span class="sxs-lookup"><span data-stu-id="1377b-181">How long does it take for policy changes to take effect?</span></span>

<span data-ttu-id="1377b-182">グローバル ポリシーを編集またはポリシーを設定すると、変更を反映させるには、最大で 24 時間がかかることができます。</span><span class="sxs-lookup"><span data-stu-id="1377b-182">After you edit the global policy or assign a policy, it can take up to 24 hours for changes to take effect.</span></span>

### <a name="user-experience"></a><span data-ttu-id="1377b-183">ユーザー エクスペリエンス</span><span class="sxs-lookup"><span data-stu-id="1377b-183">User experience</span></span>

#### <a name="how-can-users-see-all-their-pinned-apps-in-teams"></a><span data-ttu-id="1377b-184">ユーザーはチーム内のすべてが固定されたアプリをどのように表示できますか。</span><span class="sxs-lookup"><span data-stu-id="1377b-184">How can users see all their pinned apps in Teams?</span></span>

<span data-ttu-id="1377b-185">ユーザーが指定されているすべてのアプリケーションを表示するには、ユーザーはインストールされたアプリの数とそのチームのクライアント ウィンドウのサイズに応じて以下を実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="1377b-185">To view all apps that are pinned for a user, users may have to do the following depending on the number of installed apps and the size of their Teams client window.</span></span>

|<span data-ttu-id="1377b-186">チームのデスクトップ クライアント</span><span class="sxs-lookup"><span data-stu-id="1377b-186">Teams desktop client</span></span> |<span data-ttu-id="1377b-187">モバイル クライアントのチーム</span><span class="sxs-lookup"><span data-stu-id="1377b-187">Teams mobile client</span></span> |
|---------|---------|
|<span data-ttu-id="1377b-188">チームの横に、アプリケーション バーでは、**をクリックします。複数のアプリケーション**。</span><span class="sxs-lookup"><span data-stu-id="1377b-188">In the app bar on the side of Teams, click **... More apps**.</span></span>| <span data-ttu-id="1377b-189">チームの下部にあるアプリケーション バーを機械に通します。</span><span class="sxs-lookup"><span data-stu-id="1377b-189">In the app bar near the bottom of Teams, swipe up.</span></span>|
|![app-setup-policies-desktop-more-apps.png](media/app-setup-policies-desktop-more-apps.png)<br>   |![app-setup-policies-mobile-more-apps.png](media/app-setup-policies-mobile-more-apps.png)  

#### <a name="what-do-i-need-to-know-about-the-teams-mobile-experience"></a><span data-ttu-id="1377b-192">チーム モバイル エクスペリエンスについて理解するには何が必要でしょうか。</span><span class="sxs-lookup"><span data-stu-id="1377b-192">What do I need to know about the Teams mobile experience?</span></span>

<span data-ttu-id="1377b-193">チームのモバイル クライアント (iOS および Android) 静的タブで個人用のアプリケーションが現在サポートされていません。</span><span class="sxs-lookup"><span data-stu-id="1377b-193">The Teams mobile clients (iOS and Android) currently don't support personal apps with static tabs.</span></span> <span data-ttu-id="1377b-194">アプリケーション ポリシーの設定によってチームのデスクトップ クライアントに固定されているアプリケーションは、可能性があります、チームのモバイル クライアントでは表示されません。</span><span class="sxs-lookup"><span data-stu-id="1377b-194">Depending on the apps set in the policy, apps pinned to the Teams desktop client might not appear in the Teams mobile clients.</span></span> <span data-ttu-id="1377b-195">個人 bot は、モバイル クライアントのチャットにも表示されます。</span><span class="sxs-lookup"><span data-stu-id="1377b-195">Personal bots will still appear in Chat on mobile clients.</span></span>

<span data-ttu-id="1377b-196">チームのモバイル クライアントでは、ユーザーはアクティビティ、チャット、チームなどのコア ・ チームのアプリケーションを参照してくださいし、シフトなど、マイクロソフトからいくつかのファースト パーティのアプリケーションを固定することができます。</span><span class="sxs-lookup"><span data-stu-id="1377b-196">With the Teams mobile clients, users will see core Teams apps such as Activity, Chat, and Teams, and you can pin some first-party apps from Microsoft, such as Shifts.</span></span>

#### <a name="can-users-change-the-order-of-apps-pinned-through-a-policy"></a><span data-ttu-id="1377b-197">ユーザーは、ポリシーによって固定されているアプリケーションの順序を変更できますか。</span><span class="sxs-lookup"><span data-stu-id="1377b-197">Can users change the order of apps pinned through a policy?</span></span>

<span data-ttu-id="1377b-198">現時点では、ユーザーは、チームのモバイル クライアントではなくチームのデスクトップまたは web クライアントは、固定されたアプリケーションの順序を変更することができます。</span><span class="sxs-lookup"><span data-stu-id="1377b-198">Currently, users can change the order of their pinned apps on Teams mobile clients but not on the Teams desktop or web clients.</span></span> 

### <a name="custom-teams-apps"></a><span data-ttu-id="1377b-199">サバイバル-カスタム アプリケーション</span><span class="sxs-lookup"><span data-stu-id="1377b-199">Custom Teams apps</span></span>

#### <a name="my-organization-built-a-custom-teams-app-and-published-it-through-appsource-but-the-app-icon-isnt-displayed-as-expected-when-the-app-is-pinned-to-the-app-bar-in-teams-how-do-i-fix-it"></a><span data-ttu-id="1377b-200">自分の所属組織がカスタム チームのアプリケーションをビルドし、AppSource を公開していますが、アプリケーションをチームでアプリケーション バーを固定するときに期待どおりにアプリケーションのアイコンが表示されていません。</span><span class="sxs-lookup"><span data-stu-id="1377b-200">My organization built a custom Teams app and published it through AppSource but the app icon isn't displayed as expected when the app is pinned to the app bar in Teams.</span></span> <span data-ttu-id="1377b-201">どのように修正しますか。</span><span class="sxs-lookup"><span data-stu-id="1377b-201">How do I fix it?</span></span> 

<span data-ttu-id="1377b-202">アプリケーションを送信する前に、ロゴのガイドラインに従うことを確認します。</span><span class="sxs-lookup"><span data-stu-id="1377b-202">Make sure that you follow the logo guidelines before you submit the app.</span></span> <span data-ttu-id="1377b-203">詳細については、[販売者のダッシュ ボードの提出書類のチェックリスト](https://docs.microsoft.com/microsoftteams/platform/publishing/office-store-checklist)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1377b-203">To learn more, see [Checklist for Seller Dashboard submission](https://docs.microsoft.com/microsoftteams/platform/publishing/office-store-checklist).</span></span> 

 ## <a name="related-topics"></a><span data-ttu-id="1377b-204">関連トピック</span><span class="sxs-lookup"><span data-stu-id="1377b-204">Related topics</span></span>
- [<span data-ttu-id="1377b-205">テナント アプリケーション カタログにチームのクライアントからアプリケーションを発行します。</span><span class="sxs-lookup"><span data-stu-id="1377b-205">Publish an app to the Tenant Apps Catalog from the Teams client</span></span>](tenant-apps-catalog-teams.md)
