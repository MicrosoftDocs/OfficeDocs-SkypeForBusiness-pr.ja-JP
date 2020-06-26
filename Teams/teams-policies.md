---
title: Microsoft Teams でチーム ポリシーを管理する
author: lanachin
ms.author: v-lanac
manager: serdars
ms.reviewer: jastark
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
description: ユーザーがチームやチャネルで実行できる操作を制御する組織のチーム ポリシーの使用方法と管理方法について説明します。
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.teams.teamspolicies.new.tooltip.discoverteams
- ms.teamsadmincenter.teams.teamspolicies.new.tooltip.createchannels
- ms.teamsadmincenter.teams.teamsandchannelpolicies.overview
- ms.teamsadmincenter.teamsandchannelpolicies.overview
- ms.teamsadmincenter.teams.teamspolicies.new.tooltip.discover
- ms.teamsadmincenter.teams.teamspolicies.new.tooltip.create
ms.openlocfilehash: b28b61a6b2d4c441fc69d0e50124df50f95b4a49
ms.sourcegitcommit: 2e8a61abdd586bf8f0f88cac3b7d4ca4b9d9be34
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "44889976"
---
# <a name="manage-teams-policies-in-microsoft-teams"></a><span data-ttu-id="979e1-103">Microsoft Teams でチーム ポリシーを管理する</span><span class="sxs-lookup"><span data-stu-id="979e1-103">Manage teams policies in Microsoft Teams</span></span>

<span data-ttu-id="979e1-104">管理者は、Microsoft Teams でチーム ポリシーを使用して、チームやチャネルで組織のユーザーが実行できる操作を制御できます。</span><span class="sxs-lookup"><span data-stu-id="979e1-104">As an admin, you can use teams policies in Microsoft Teams to control what users in your organization can do in teams and channels.</span></span> <span data-ttu-id="979e1-105">たとえば、ユーザーが検索結果とチーム ギャラリーでプライベートのチームを検出できるかどうか、およびユーザーがプライベートのチャネルを作成できるかどうかを設定できます。</span><span class="sxs-lookup"><span data-stu-id="979e1-105">For example, you can set whether users are allowed to discover private teams in search results and in the team gallery and whether users are allowed to create private channels.</span></span>

<span data-ttu-id="979e1-106">チーム ポリシーを管理するには、Microsoft Teams 管理センターで **[Teams]** > **[チーム ポリシー]** の順に移動します。</span><span class="sxs-lookup"><span data-stu-id="979e1-106">You manage teams policies by going to **Teams** > **Teams policies** in the Microsoft Teams admin center.</span></span> <span data-ttu-id="979e1-107">グローバル (組織全体の既定) ポリシーを使用することも、カスタム ポリシーを作成してユーザーに割り当てることもできます。</span><span class="sxs-lookup"><span data-stu-id="979e1-107">You can use the global (Org-wide default) policy or create custom policies and assign them to users.</span></span> <span data-ttu-id="979e1-108">カスタム ポリシーを作成して割り当てていない場合、組織内のユーザーにはグローバル ポリシーが自動的に適用されます。</span><span class="sxs-lookup"><span data-stu-id="979e1-108">Users in your organization will automatically get the global policy unless you create and assign a custom policy.</span></span>

<span data-ttu-id="979e1-109">グローバル ポリシーを編集するか、カスタム ポリシーを作成して割り当てることもできます。</span><span class="sxs-lookup"><span data-stu-id="979e1-109">You can edit the global policy or create and assign a custom policy.</span></span> <span data-ttu-id="979e1-110">ユーザーにカスタム ポリシーが割り当てられると、そのポリシーがユーザーに適用されます。</span><span class="sxs-lookup"><span data-stu-id="979e1-110">If a user is assigned a custom policy, that policy applies to the user.</span></span> <span data-ttu-id="979e1-111">ユーザーにカスタム ポリシーが割り当てられない場合は、グローバル ポリシーがユーザーに適用されます。</span><span class="sxs-lookup"><span data-stu-id="979e1-111">If a user isn't assigned a custom policy, the global policy applies to the user.</span></span> <span data-ttu-id="979e1-112">グローバルポリシーを編集するか、ポリシーを割り当てると、変更が有効になるまでに数時間かかることがあります。</span><span class="sxs-lookup"><span data-stu-id="979e1-112">After you edit the global policy or assign a policy, it can take a few hours for changes to take effect.</span></span>

## <a name="create-a-custom-teams-policy"></a><span data-ttu-id="979e1-113">カスタムのチーム ポリシーを作成する</span><span class="sxs-lookup"><span data-stu-id="979e1-113">Create a custom teams policy</span></span>

1. <span data-ttu-id="979e1-114">Microsoft Teams 管理センターの左側のナビゲーションで、**[Teams]** > **[チーム ポリシー]** の順に移動します。</span><span class="sxs-lookup"><span data-stu-id="979e1-114">In the left navigation of the Microsoft Teams admin center, go to **Teams** > **Teams policies**.</span></span>
2. <span data-ttu-id="979e1-115">**[追加]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="979e1-115">Click **Add**.</span></span>
3. <span data-ttu-id="979e1-116">ポリシーの名前と説明を入力します。</span><span class="sxs-lookup"><span data-stu-id="979e1-116">Enter a name and description for the policy.</span></span>

    ![チーム ポリシー設定のスクリーンショット](media/teams-policies.png)
4. <span data-ttu-id="979e1-118">希望する設定を選びます。</span><span class="sxs-lookup"><span data-stu-id="979e1-118">Choose the settings that you want:</span></span>

- <span data-ttu-id="979e1-119">プライベート**チームを見つける**(プライベートプレビュー):<a name="discoverteams"> </a>この設定を有効にすると、ユーザーは検索結果とチームギャラリーでプライベートチームを見つけられるようになります。</span><span class="sxs-lookup"><span data-stu-id="979e1-119">**Discover private teams** (in private preview):<a name="discoverteams"> </a> Turn on this setting to allow users to discover private teams in search results and in the team gallery.</span></span>
- <span data-ttu-id="979e1-120">**プライベート チャネルの作成**: <a name="createchannels"> </a>この設定をオンにすると、ユーザーがプライベート チャネルを作成できるようになります。</span><span class="sxs-lookup"><span data-stu-id="979e1-120">**Create private channels**: <a name="createchannels"> </a>Turn on this setting to allow users to create private channels.</span></span>

5. <span data-ttu-id="979e1-121">**[保存]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="979e1-121">Click **Save**.</span></span>

## <a name="edit-a-teams-policy"></a><span data-ttu-id="979e1-122">チーム ポリシーの編集</span><span class="sxs-lookup"><span data-stu-id="979e1-122">Edit a teams policy</span></span>

<span data-ttu-id="979e1-123">グローバル ポリシー、または作成したカスタム ポリシーを編集できます。</span><span class="sxs-lookup"><span data-stu-id="979e1-123">You can edit the global policy or any custom policies that you create.</span></span>

1. <span data-ttu-id="979e1-124">Microsoft Teams 管理センターの左側のナビゲーションで、**[Teams]** > **[チーム ポリシー]** の順に移動します。</span><span class="sxs-lookup"><span data-stu-id="979e1-124">In the left navigation of the Microsoft Teams admin center, go to **Teams** > **Teams policies**.</span></span>
2. <span data-ttu-id="979e1-125">ポリシー名の左側をクリックしてポリシーを選び、**[編集]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="979e1-125">Select the policy by clicking to the left of the policy name, and then click **Edit**.</span></span>
3. <span data-ttu-id="979e1-126">希望する設定をオンまたはオフにしてから、**[保存]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="979e1-126">Turn on or turn off the settings that you want, and then click **Save**.</span></span>

## <a name="assign-a-custom-teams-policy-to-users"></a><span data-ttu-id="979e1-127">ユーザーにカスタムのチーム ポリシーを割り当てる</span><span class="sxs-lookup"><span data-stu-id="979e1-127">Assign a custom teams policy to users</span></span>

<span data-ttu-id="979e1-128">Microsoft Teams 管理センターを使用して、1 つ以上のユーザーまたは Skype for Business PowerShell モジュールにカスタム ポリシーを割り当てることで、セキュリティグループや配布グループなどのユーザーのグループにカスタム ポリシーを割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="979e1-128">You can use the Microsoft Teams admin center to assign a custom policy to one or more users or the Skype for Business PowerShell module to assign a custom policy to groups of users, such as a security group or distribution group.</span></span>

### <a name="assign-a-custom-teams-policy-to-users"></a><span data-ttu-id="979e1-129">ユーザーにカスタムのチーム ポリシーを割り当てる</span><span class="sxs-lookup"><span data-stu-id="979e1-129">Assign a custom teams policy to users</span></span>

<span data-ttu-id="979e1-130">1人のユーザーにポリシーを割り当てるには、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="979e1-130">To assign a policy to one user:</span></span>

1. <span data-ttu-id="979e1-131">Microsoft Teams 管理センターの左側のナビゲーションで、**[ユーザー]** に移動してユーザーをクリックします。</span><span class="sxs-lookup"><span data-stu-id="979e1-131">In the left navigation of the Microsoft Teams admin center, go to **Users**, and then click the user.</span></span>
2. <span data-ttu-id="979e1-132">**[ポリシー]** をクリックし、**[割り当てられたポリシー]** の横にある **[編集]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="979e1-132">Click **Policies**, and then next to **Assigned policies**, click **Edit**.</span></span>
3. <span data-ttu-id="979e1-133">**[チーム ポリシー]** で割り当てるポリシーを選択し、**[保存]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="979e1-133">Under **Teams policies**, select the policy you want to assign, and then click **Save**.</span></span>

<span data-ttu-id="979e1-134">複数のユーザーに同時にポリシーを割り当てるには、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="979e1-134">To assign a policy to multiple users at a time:</span></span>

1. <span data-ttu-id="979e1-135">Microsoft Teams 管理センターの左側のナビゲーションで、**[ユーザー]** に移動し、ユーザーを検索するか、表示にフィルターを適用してユーザーを表示します。</span><span class="sxs-lookup"><span data-stu-id="979e1-135">In the left navigation of the Microsoft Teams admin center, go to **Users**, and then search for the users or filter the view to show the users you want.</span></span>
2. <span data-ttu-id="979e1-136">[**&#x2713;** (チェックマーク)] の列からユーザーを選択します。</span><span class="sxs-lookup"><span data-stu-id="979e1-136">In the **&#x2713;** (check mark) column, select the users.</span></span> <span data-ttu-id="979e1-137">すべてのユーザーを選択するには、表の上部にある [&#x2713; (チェックマーク)] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="979e1-137">To select all users, click the &#x2713; (check mark) at the top of the table.</span></span>
3. <span data-ttu-id="979e1-138">[**設定の編集**] をクリックし、必要な変更を行い、[**適用**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="979e1-138">Click **Edit settings**, make the changes that you want, and then click **Apply**.</span></span>  

<span data-ttu-id="979e1-139">または、次の操作も実行できます。</span><span class="sxs-lookup"><span data-stu-id="979e1-139">Or, you can also do the following:</span></span>

1. <span data-ttu-id="979e1-140">Microsoft Teams 管理センターの左側のナビゲーションで、**[Teams]** > **[チーム ポリシー]** の順に移動します。</span><span class="sxs-lookup"><span data-stu-id="979e1-140">In the left navigation of the Microsoft Teams admin center, go to **Teams** > **Teams policies**.</span></span>
2. <span data-ttu-id="979e1-141">ポリシー名の左側をクリックしてポリシーを選びます。</span><span class="sxs-lookup"><span data-stu-id="979e1-141">Select the policy by clicking to the left of the policy name.</span></span>
3. <span data-ttu-id="979e1-142">[**ユーザーを管理**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="979e1-142">Select **Manage users**.</span></span>
4. <span data-ttu-id="979e1-143">[**ユーザーを管理**] ウィンドウで、表示名またはユーザー名でユーザーを検索し、名前を選択して [**追加**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="979e1-143">In the **Manage users** pane, search for the user by display name or by user name, select the name, and then select **Add**.</span></span> <span data-ttu-id="979e1-144">追加するユーザーごとに、この手順を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="979e1-144">Repeat this step for each user that you want to add.</span></span>
5. <span data-ttu-id="979e1-145">ユーザーの追加が完了したら、[**保存**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="979e1-145">When you're finished adding users, click **Save**.</span></span>

### <a name="assign-a-custom-teams-policy-to-users-in-a-group"></a><span data-ttu-id="979e1-146">グループのユーザーにカスタムのチーム ポリシーを割り当てる</span><span class="sxs-lookup"><span data-stu-id="979e1-146">Assign a custom teams policy to users in a group</span></span>

<span data-ttu-id="979e1-147">ユーザー設定のチームポリシーは、既に特定した複数のユーザーに割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="979e1-147">You may want to assign a custom teams policy to multiple users that you've already identified.</span></span> <span data-ttu-id="979e1-148">たとえば、セキュリティ グループのすべてのユーザーにポリシーを割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="979e1-148">For example, you may want to assign a policy to all users in a security group.</span></span> <span data-ttu-id="979e1-149">これを行うには、Graph 用 Azure Active Directory PowerShell モジュールと Skype for Business PowerShell モジュールに接続します。</span><span class="sxs-lookup"><span data-stu-id="979e1-149">You can do this by connecting to the Azure Active Directory PowerShell for Graph module and the Skype for Business PowerShell module.</span></span> <span data-ttu-id="979e1-150">PowerShell を使用して Teams を管理する方法の詳細については、「[Teams での PowerShell の概要](teams-powershell-overview.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="979e1-150">For more information about using PowerShell to manage Teams, see [Teams PowerShell Overview](teams-powershell-overview.md).</span></span>

<span data-ttu-id="979e1-151">この例では、「Marketing Teams Policy」という名前のチーム ポリシーを、Contoso マーケティング グループのすべてのユーザーに割り当てます。</span><span class="sxs-lookup"><span data-stu-id="979e1-151">In this example, we assign a teams policy called Marketing Teams Policy to all users in the Contoso Marketing group.</span></span>  

> [!NOTE]
> <span data-ttu-id="979e1-152">まず、 [「単一の Windows PowerShell ウィンドウですべての Microsoft 365 または Office 365 サービスに接続](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-all-office-365-services-in-a-single-windows-powershell-window)する」の手順に従って、Graph モジュール用の Azure Active Directory Powershell と Skype For business powershell モジュールに接続していることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="979e1-152">Make sure you first connect to the Azure Active Directory PowerShell for Graph module and Skype for Business PowerShell module by following the steps in [Connect to all Microsoft 365 or Office 365 services in a single Windows PowerShell window](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-all-office-365-services-in-a-single-windows-powershell-window).</span></span>

<span data-ttu-id="979e1-153">特定のグループの GroupObjectId を取得します。</span><span class="sxs-lookup"><span data-stu-id="979e1-153">Get the GroupObjectId of the particular group.</span></span>
```PowerShell
$group = Get-AzureADGroup -SearchString "Contoso Marketing"
```
<span data-ttu-id="979e1-154">指定したグループのメンバーを取得します。</span><span class="sxs-lookup"><span data-stu-id="979e1-154">Get the members of the specified group.</span></span>
```PowerShell
$members = Get-AzureADGroupMember -ObjectId $group.ObjectId -All $true | Where-Object {$_.ObjectType -eq "User"}
```
<span data-ttu-id="979e1-155">グループ内のすべてのユーザーを特定のチーム ポリシーに割り当てる。</span><span class="sxs-lookup"><span data-stu-id="979e1-155">Assign all users in the group to a particular teams policy.</span></span> <span data-ttu-id="979e1-156">この例では、Marketing Teams Policy です。</span><span class="sxs-lookup"><span data-stu-id="979e1-156">In this example, it's Marketing Teams Policy.</span></span>
```PowerShell
$members | ForEach-Object { Grant-CsTeamsChannelsPolicy -PolicyName "Marketing Teams Policy" -Identity $_.UserPrincipalName}
``` 
<span data-ttu-id="979e1-157">グループ内のメンバー数によっては、このコマンドの実行に数分かかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="979e1-157">Depending on the number of members in the group, this command may take several minutes to execute.</span></span>

## <a name="related-topics"></a><span data-ttu-id="979e1-158">関連項目</span><span class="sxs-lookup"><span data-stu-id="979e1-158">Related topics</span></span>

- [<span data-ttu-id="979e1-159">Teams でプライベート チームの検索を管理する</span><span class="sxs-lookup"><span data-stu-id="979e1-159">Manage discovery of private teams in Teams</span></span>](manage-discovery-of-private-teams.md)
- [<span data-ttu-id="979e1-160">Teams のプライベート チャネル</span><span class="sxs-lookup"><span data-stu-id="979e1-160">Private channels in Teams</span></span>](private-channels.md)
- [<span data-ttu-id="979e1-161">チームのユーザーにポリシーを割り当てる</span><span class="sxs-lookup"><span data-stu-id="979e1-161">Assign policies to your users in Teams</span></span>](assign-policies.md)
